---
layout: post
title: Unity에서 Android 네이티브 코드 사용하기
subtitle: 2020-05-24 ~ 2021-06-02 (2주)
categories: zest.Activities  
tags: [Unity, Android, AndroidNative, LocalStorage, Texture2D, Collaboration]  
---

## 캐릭터 옷 갈아입히기  
<iframe width="560" height="315" src="https://www.youtube.com/embed/bqZkXvOmhbk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 기획  
- 2D아바타 커스터마이징 시스템.  
- 유니티에서 안드로이드 네이티브 코드 사용.  
- 안드로이드 내부 저장소에 접근하여 파일 쓰기.  

## 명세  
- 제목_ 캐릭터 옷 갈아입히기(ChangeClothesYH)  
- 기간_ 2020-05-24 ~ 2021-06-02 (2주)  
- 팀원_ 2명  
- 결과_ APK Build

## Code.
**안드로이드 객체 생성.**  
``` csharp
var unityPlayer = new AndroidJavaClass("com.unity3d.player.UnityPlayer");
AndroidJavaObject _activity = unityPlayer.GetStatic<AndroidJavaObject>("currentActivity");
```  
<br>

**Texture2D 데이터를 안드로이드 객체로 변환.**  
``` csharp
public static AndroidJavaObject Texture2DToAndroidBitmap(Texture2D texture2D)
{
    byte[] encoded = texture2D.EncodeToPNG();
    using (var bf = new AndroidJavaClass("android.graphics.BitmapFactory"))
    {
        return bf.CallStatic<AndroidJavaObject>("decodeByteArray", encoded, 0, encoded.Length);
    }
}
```  
<br>

**로컬저장소 쓰기 접근.**  
``` csharp
private const string MediaStoreImagesMediaClass = "android.provider.MediaStore$Images$Media";
public static void SaveImageToGallery(Texture2D texture2D, string title, string description)
{
    using (var mediaClass = new AndroidJavaClass(MediaStoreImagesMediaClass))
    {
        using (var cr = Activity.Call<AndroidJavaObject>("getContentResolver"))
        {
            var image = Texture2DToAndroidBitmap(texture2D);
            mediaClass.CallStatic<string>("insertImage", cr, image, title, description);
        }
    }
}
```  
