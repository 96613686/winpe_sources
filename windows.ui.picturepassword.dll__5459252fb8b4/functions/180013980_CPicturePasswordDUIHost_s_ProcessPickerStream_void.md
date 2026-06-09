# CPicturePasswordDUIHost::s_ProcessPickerStream(void *)

- ea: `0x180013980`
- end: `0x180013b7f`
- name: `?s_ProcessPickerStream@CPicturePasswordDUIHost@@KAKPEAX@Z`
- size: `511`
- prototype: `__int64 __fastcall(CPrivateNotificationWindow **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002610`
- `0x1800043a4`
- `0x18000772c`
- `0x180007e30`
- `0x180011250`
- `0x1800136a8`
- `0x180013980`
- `0x180015e38`
- `0x1800189c4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a3c`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::s_ProcessPickerStream(CPrivateNotificationWindow **a1)
{
  LPARAM v2; // rsi
  struct IStream *v3; // rbx
  int Instance; // edi
  int v5; // eax
  __int64 v6; // r8
  int StreamOfWICBitmapSourceWithOptions; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-29h]
  struct IWICImagingFactory *v10; // [rsp+30h] [rbp-19h] BYREF
  struct IStream *v11; // [rsp+38h] [rbp-11h] BYREF
  struct IWICBitmapSource *v12; // [rsp+40h] [rbp-9h] BYREF
  struct IWICBitmapFrameDecode *v13; // [rsp+48h] [rbp-1h] BYREF
  struct IWICBitmapSource *v14; // [rsp+50h] [rbp+7h] BYREF
  LPARAM v15; // [rsp+58h] [rbp+Fh] BYREF
  GUID v16; // [rsp+60h] [rbp+17h] BYREF
  __int128 v17; // [rsp+70h] [rbp+27h] BYREF

  v2 = 0;
  v15 = 0;
  v11 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v11);
  v3 = 0;
  v11 = 0;
  v10 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v10);
  Instance = CMarshaledInterface::_Unmarshal(
               (CMarshaledInterface *)(a1 + 3),
               &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea,
               (void **)&v10,
               0);
  if ( Instance >= 0 )
  {
    v5 = StorageFileToStream((struct Windows::Storage::IStorageFile *)v10, &v11);
    v3 = v11;
    Instance = v5;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v10);
  if ( Instance >= 0 )
  {
    v10 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v10);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&v10);
    if ( Instance >= 0 )
    {
      v14 = 0;
      v13 = 0;
      v17 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v13);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v14);
      Instance = LoadImageWithWIC(
                   v10,
                   (__int64)v3,
                   v6,
                   &v14,
                   (struct IWICBitmapFrameDecode *)&v13,
                   (struct IWICBitmapDecoder *)&v17);
      if ( Instance >= 0 )
      {
        v12 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v12);
        Instance = ColorCorrectImageWithWIC(v10, v13, (struct IWICColorTransform *)v14, &v12);
        if ( Instance >= 0 )
        {
          v16 = GUID_WICPixelFormat32bppBGRA;
          StreamOfWICBitmapSourceWithOptions = GetStreamOfWICBitmapSourceWithOptions(
                                                 v10,
                                                 (__int64)v12,
                                                 (__int64)&v17,
                                                 (__int128 *)&v16,
                                                 (__int64)ppv,
                                                 &v15);
          v2 = v15;
          Instance = StreamOfWICBitmapSourceWithOptions;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v12);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v13);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v10);
  }
  if ( !CPrivateNotificationWindow::PostNotification(a1[2], 0x402u, Instance, v2) && v2 )
    (*(void (__fastcall **)(LPARAM))(*(_QWORD *)v2 + 16LL))(v2);
  (*(void (__fastcall **)(CPrivateNotificationWindow **, __int64))*a1)(a1, 1);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013980  mov     [rsp-8+arg_8], rbx
0x180013985  mov     [rsp-8+arg_10], rsi
0x18001398a  push    rbp
0x18001398b  push    rdi
0x18001398c  push    r14
0x18001398e  lea     rbp, [rsp-47h]
0x180013993  sub     rsp, 90h
0x18001399a  mov     rax, cs:__security_cookie
0x1800139a1  xor     rax, rsp
0x1800139a4  mov     [rbp+57h+var_20], rax
0x1800139a8  mov     r14, rcx
0x1800139ab  xor     esi, esi
0x1800139ad  lea     rcx, [rbp+57h+var_68]
0x1800139b1  mov     [rbp+57h+var_48], rsi
0x1800139b5  mov     [rbp+57h+var_68], rsi
0x1800139b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800139be  xor     ebx, ebx
0x1800139c0  lea     rcx, [rbp+57h+var_70]
0x1800139c4  mov     [rbp+57h+var_68], rbx
0x1800139c8  mov     [rbp+57h+var_70], rbx
0x1800139cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800139d1  lea     rcx, [r14+18h]; this
0x1800139d5  xor     r9d, r9d; bool
0x1800139d8  lea     r8, [rbp+57h+var_70]; void **
0x1800139dc  lea     rdx, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea; struct _GUID *
0x1800139e3  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x1800139e8  mov     edi, eax
0x1800139ea  test    eax, eax
0x1800139ec  js      short loc_180013A01
0x1800139ee  mov     rcx, [rbp+57h+var_70]; struct Windows::Storage::IStorageFile *
0x1800139f2  lea     rdx, [rbp+57h+var_68]; struct IStream **
0x1800139f6  call    ?StorageFileToStream@@YAJPEAUIStorageFile@Storage@Windows@@PEAPEAUIStream@@@Z; StorageFileToStream(Windows::Storage::IStorageFile *,IStream * *)
0x1800139fb  mov     rbx, [rbp+57h+var_68]
0x1800139ff  mov     edi, eax
0x180013a01  lea     rcx, [rbp+57h+var_70]
0x180013a05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013a0a  test    edi, edi
0x180013a0c  js      loc_180013B11
0x180013a12  lea     rcx, [rbp+57h+var_70]
0x180013a16  mov     [rbp+57h+var_70], rsi
0x180013a1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013a1f  xor     edx, edx; pUnkOuter
0x180013a21  lea     rax, [rbp+57h+var_70]
0x180013a25  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180013a2c  mov     [rsp+0A0h+ppv], rax; ppv
0x180013a31  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180013a38  lea     r8d, [rdx+1]; dwClsContext
0x180013a3c  call    cs:__imp_CoCreateInstance
0x180013a42  mov     edi, eax
0x180013a44  test    eax, eax
0x180013a46  js      loc_180013B08
0x180013a4c  xorps   xmm0, xmm0
0x180013a4f  mov     [rbp+57h+var_50], rsi
0x180013a53  lea     rcx, [rbp+57h+var_58]
0x180013a57  mov     [rbp+57h+var_58], rsi
0x180013a5b  movups  [rbp+57h+var_30], xmm0
0x180013a5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013a64  lea     rcx, [rbp+57h+var_50]
0x180013a68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013a6d  mov     rcx, [rbp+57h+var_70]
0x180013a71  lea     rax, [rbp+57h+var_30]
0x180013a75  mov     [rsp+0A0h+var_78], rax
0x180013a7a  lea     r9, [rbp+57h+var_50]
0x180013a7e  lea     rax, [rbp+57h+var_58]
0x180013a82  mov     rdx, rbx
0x180013a85  mov     [rsp+0A0h+ppv], rax
0x180013a8a  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x180013a8f  mov     edi, eax
0x180013a91  test    eax, eax
0x180013a93  js      short loc_180013AF6
0x180013a95  lea     rcx, [rbp+57h+var_60]
0x180013a99  mov     [rbp+57h+var_60], rsi
0x180013a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013aa2  mov     r8, [rbp+57h+var_50]; struct IWICBitmapSource *
0x180013aa6  lea     r9, [rbp+57h+var_60]; struct IWICBitmapSource **
0x180013aaa  mov     rdx, [rbp+57h+var_58]; struct IWICBitmapFrameDecode *
0x180013aae  mov     rcx, [rbp+57h+var_70]; struct IWICImagingFactory *
0x180013ab2  call    ?ColorCorrectImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAPEAU3@@Z; ColorCorrectImageWithWIC(IWICImagingFactory *,IWICBitmapFrameDecode *,IWICBitmapSource *,IWICBitmapSource * *)
0x180013ab7  mov     edi, eax
0x180013ab9  test    eax, eax
0x180013abb  js      short loc_180013AED
0x180013abd  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180013ac4  mov     rdx, [rbp+57h+var_60]
0x180013ac8  lea     rax, [rbp+57h+var_48]
0x180013acc  mov     rcx, [rbp+57h+var_70]
0x180013ad0  lea     r9, [rbp+57h+var_40]
0x180013ad4  lea     r8, [rbp+57h+var_30]
0x180013ad8  mov     [rsp+0A0h+var_78], rax
0x180013add  movdqu  [rbp+57h+var_40], xmm0
0x180013ae2  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x180013ae7  mov     rsi, [rbp+57h+var_48]
0x180013aeb  mov     edi, eax
0x180013aed  lea     rcx, [rbp+57h+var_60]
0x180013af1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013af6  lea     rcx, [rbp+57h+var_58]
0x180013afa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013aff  lea     rcx, [rbp+57h+var_50]
0x180013b03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013b08  lea     rcx, [rbp+57h+var_70]
0x180013b0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013b11  mov     rcx, [r14+10h]; this
0x180013b15  mov     r9, rsi; __int64
0x180013b18  movsxd  r8, edi; unsigned __int64
0x180013b1b  mov     edx, 402h; unsigned int
0x180013b20  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x180013b25  test    al, al
0x180013b27  jnz     short loc_180013B3D
0x180013b29  test    rsi, rsi
0x180013b2c  jz      short loc_180013B3D
0x180013b2e  mov     rax, [rsi]
0x180013b31  mov     rcx, rsi
0x180013b34  mov     rax, [rax+10h]
0x180013b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b3d  mov     rax, [r14]
0x180013b40  mov     edx, 1
0x180013b45  mov     rcx, r14
0x180013b48  mov     rax, [rax]
0x180013b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b50  lea     rcx, [rbp+57h+var_68]
0x180013b54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013b59  mov     eax, edi
0x180013b5b  mov     rcx, [rbp+57h+var_20]
0x180013b5f  xor     rcx, rsp; StackCookie
0x180013b62  call    __security_check_cookie
0x180013b67  lea     r11, [rsp+0A0h+var_10]
0x180013b6f  mov     rbx, [r11+28h]
0x180013b73  mov     rsi, [r11+30h]
0x180013b77  mov     rsp, r11
0x180013b7a  pop     r14
0x180013b7c  pop     rdi
0x180013b7d  pop     rbp
0x180013b7e  retn
```
