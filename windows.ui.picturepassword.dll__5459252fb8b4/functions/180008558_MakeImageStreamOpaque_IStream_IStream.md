# MakeImageStreamOpaque(IStream *,IStream * *)

- ea: `0x180008558`
- end: `0x180008695`
- name: `?MakeImageStreamOpaque@@YAJPEAUIStream@@PEAPEAU1@@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ad34`

## callees

- `0x1800043a4`
- `0x1800066bc`
- `0x180006880`
- `0x18000772c`
- `0x180007e30`
- `0x180008558`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800085a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800085a2`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180008665`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180008665`

## pseudocode

```c
__int64 __fastcall MakeImageStreamOpaque(struct IStream *a1, struct IStream **a2)
{
  int Instance; // ebx
  __int64 v5; // r8
  __int64 v6; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  HGDIOBJ ho; // [rsp+30h] [rbp-20h] BYREF
  GUID v10; // [rsp+40h] [rbp-10h] BYREF
  struct IWICImagingFactory *v11; // [rsp+78h] [rbp+28h] BYREF
  struct IWICBitmapSource *v12; // [rsp+80h] [rbp+30h] BYREF
  struct IWICBitmapSource *v13; // [rsp+88h] [rbp+38h] BYREF

  *a2 = 0;
  v11 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v11);
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v11);
  if ( Instance >= 0 )
  {
    v13 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v13);
    Instance = LoadImageWithWIC(v11, (__int64)a1, v5, &v13, 0, 0);
    if ( Instance >= 0 )
    {
      ho = 0;
      Instance = ConvertWICBitmapToHBITMAP(v11, v13, (HBITMAP *)&ho);
      if ( Instance >= 0 )
      {
        v12 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v12);
        Instance = ConvertHBITMAPToWICBitmap(v11, (HBITMAP)ho, v6, &v12);
        if ( Instance >= 0 )
        {
          v10 = GUID_WICPixelFormat32bppBGRA;
          Instance = GetStreamOfWICBitmapSourceWithOptions(
                       v11,
                       (__int64)v12,
                       (__int64)&GUID_ContainerFormatPng,
                       (__int128 *)&v10,
                       (__int64)ppv,
                       a2);
        }
        DeleteObject(ho);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v12);
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v13);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180008558  mov     [rsp-18h+arg_0], rbx
0x18000855d  push    rbp
0x18000855e  push    rsi
0x18000855f  push    rdi
0x180008560  mov     rbp, rsp
0x180008563  sub     rsp, 50h
0x180008567  mov     rdi, rcx
0x18000856a  mov     qword ptr [rdx], 0
0x180008571  lea     rcx, [rbp+arg_8]
0x180008575  mov     [rbp+arg_8], 0
0x18000857d  mov     rsi, rdx
0x180008580  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008585  xor     edx, edx; pUnkOuter
0x180008587  lea     rax, [rbp+arg_8]
0x18000858b  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180008592  mov     [rsp+50h+ppv], rax; ppv
0x180008597  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000859e  lea     r8d, [rdx+1]; dwClsContext
0x1800085a2  call    cs:__imp_CoCreateInstance
0x1800085a8  mov     ebx, eax
0x1800085aa  test    eax, eax
0x1800085ac  js      loc_18000867D
0x1800085b2  lea     rcx, [rbp+arg_18]
0x1800085b6  mov     [rbp+arg_18], 0
0x1800085be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800085c3  mov     rcx, [rbp+arg_8]
0x1800085c7  lea     r9, [rbp+arg_18]
0x1800085cb  mov     rdx, rdi
0x1800085ce  mov     [rsp+50h+var_28], 0
0x1800085d7  mov     [rsp+50h+ppv], 0
0x1800085e0  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x1800085e5  mov     ebx, eax
0x1800085e7  test    eax, eax
0x1800085e9  js      loc_180008674
0x1800085ef  mov     rdx, [rbp+arg_18]; struct IWICBitmapSource *
0x1800085f3  lea     r8, [rbp+ho]; HBITMAP *
0x1800085f7  mov     rcx, [rbp+arg_8]; struct IWICImagingFactory *
0x1800085fb  mov     [rbp+ho], 0
0x180008603  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x180008608  mov     ebx, eax
0x18000860a  test    eax, eax
0x18000860c  js      short loc_180008674
0x18000860e  lea     rcx, [rbp+arg_10]
0x180008612  mov     [rbp+arg_10], 0
0x18000861a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000861f  mov     rdx, [rbp+ho]; HBITMAP
0x180008623  lea     r9, [rbp+arg_10]; struct IWICBitmapSource **
0x180008627  mov     rcx, [rbp+arg_8]; struct IWICImagingFactory *
0x18000862b  call    ?ConvertHBITMAPToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@W4WICBitmapAlphaChannelOption@@PEAPEAUIWICBitmapSource@@@Z; ConvertHBITMAPToWICBitmap(IWICImagingFactory *,HBITMAP__ *,WICBitmapAlphaChannelOption,IWICBitmapSource * *)
0x180008630  mov     ebx, eax
0x180008632  test    eax, eax
0x180008634  js      short loc_180008661
0x180008636  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x18000863d  mov     rdx, [rbp+arg_10]
0x180008641  lea     r9, [rbp+var_10]
0x180008645  mov     rcx, [rbp+arg_8]
0x180008649  lea     r8, GUID_ContainerFormatPng
0x180008650  movdqu  [rbp+var_10], xmm0
0x180008655  mov     [rsp+50h+var_28], rsi
0x18000865a  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x18000865f  mov     ebx, eax
0x180008661  mov     rcx, [rbp+ho]; ho
0x180008665  call    cs:__imp_DeleteObject
0x18000866b  lea     rcx, [rbp+arg_10]
0x18000866f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008674  lea     rcx, [rbp+arg_18]
0x180008678  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000867d  lea     rcx, [rbp+arg_8]
0x180008681  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008686  mov     eax, ebx
0x180008688  mov     rbx, [rsp+50h+arg_0]
0x18000868d  add     rsp, 50h
0x180008691  pop     rdi
0x180008692  pop     rsi
0x180008693  pop     rbp
0x180008694  retn
```
