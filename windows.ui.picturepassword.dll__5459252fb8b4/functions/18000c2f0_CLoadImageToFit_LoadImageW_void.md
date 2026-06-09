# CLoadImageToFit::LoadImageW(void)

- ea: `0x18000c2f0`
- end: `0x18000c42f`
- name: `?LoadImageW@CLoadImageToFit@@MEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(CLoadImageToFit *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800043a4`
- `0x180007e30`
- `0x18000ba94`
- `0x18000bb80`
- `0x18000be48`
- `0x18000c050`
- `0x18000c2f0`
- `0x18000c558`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c333`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c333`

## pseudocode

```c
__int64 __fastcall CLoadImageToFit::LoadImageW(CLoadImageToFit *this)
{
  HRESULT Instance; // ebx
  __int64 v3; // r8
  bool v4; // dl
  _BYTE v6[32]; // [rsp+30h] [rbp-20h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+68h] [rbp+18h] BYREF
  struct IWICBitmapSource *v8; // [rsp+70h] [rbp+20h] BYREF

  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppv);
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
                 *((_QWORD *)this + 12),
                 0,
                 0,
                 0);
    if ( Instance >= 0 )
    {
      v8 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v8);
      Instance = LoadImageWithWIC(ppv, *((_QWORD *)this + 12), v3, &v8, 0, 0);
      if ( Instance >= 0 )
      {
        CWICBitmapHelper::CWICBitmapHelper((CWICBitmapHelper *)v6, ppv, v8);
        Instance = CWICBitmapHelper::Scale(v6, 1, (char *)this + 104);
        if ( Instance >= 0 )
        {
          Instance = CWICBitmapHelper::Crop((CWICBitmapHelper *)v6, (const struct tagRECT *)this + 7);
          if ( Instance >= 0 )
          {
            Instance = CWICBitmapHelper::Scale(v6, 0, (char *)this + 128);
            if ( Instance >= 0 )
              Instance = CWICBitmapHelper::GetHBITMAP((CWICBitmapHelper *)v6, v4, (HBITMAP *)this + 11);
          }
        }
        CWICBitmapHelper::~CWICBitmapHelper((CWICBitmapHelper *)v6);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v8);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000c2f0  mov     [rsp-8+arg_0], rbx
0x18000c2f5  mov     [rsp-8+arg_18], rdi
0x18000c2fa  push    rbp
0x18000c2fb  mov     rbp, rsp
0x18000c2fe  sub     rsp, 50h
0x18000c302  mov     rdi, rcx
0x18000c305  mov     [rbp+arg_8], 0
0x18000c30d  lea     rcx, [rbp+arg_8]
0x18000c311  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c316  xor     edx, edx; pUnkOuter
0x18000c318  lea     rax, [rbp+arg_8]
0x18000c31c  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000c323  mov     [rsp+50h+ppv], rax; ppv
0x18000c328  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000c32f  lea     r8d, [rdx+1]; dwClsContext
0x18000c333  call    cs:__imp_CoCreateInstance
0x18000c339  mov     ebx, eax
0x18000c33b  test    eax, eax
0x18000c33d  js      loc_18000C414
0x18000c343  mov     rcx, [rdi+60h]
0x18000c347  xor     edx, edx
0x18000c349  xor     r9d, r9d
0x18000c34c  xor     r8d, r8d
0x18000c34f  mov     rax, [rcx]
0x18000c352  mov     rax, [rax+28h]
0x18000c356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c35b  mov     ebx, eax
0x18000c35d  test    eax, eax
0x18000c35f  js      loc_18000C414
0x18000c365  lea     rcx, [rbp+arg_10]
0x18000c369  mov     [rbp+arg_10], 0
0x18000c371  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c376  mov     rdx, [rdi+60h]
0x18000c37a  lea     r9, [rbp+arg_10]
0x18000c37e  mov     rcx, [rbp+arg_8]
0x18000c382  mov     [rsp+50h+var_28], 0
0x18000c38b  mov     [rsp+50h+ppv], 0
0x18000c394  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x18000c399  mov     ebx, eax
0x18000c39b  test    eax, eax
0x18000c39d  js      short loc_18000C40B
0x18000c39f  mov     r8, [rbp+arg_10]; struct IWICBitmapSource *
0x18000c3a3  lea     rcx, [rbp+var_20]; this
0x18000c3a7  mov     rdx, [rbp+arg_8]; struct IWICImagingFactory *
0x18000c3ab  call    ??0CWICBitmapHelper@@QEAA@PEAUIWICImagingFactory@@PEAUIWICBitmapSource@@@Z; CWICBitmapHelper::CWICBitmapHelper(IWICImagingFactory *,IWICBitmapSource *)
0x18000c3b0  lea     r8, [rdi+68h]
0x18000c3b4  mov     edx, 1
0x18000c3b9  lea     rcx, [rbp+var_20]
0x18000c3bd  call    ?Scale@CWICBitmapHelper@@QEAAJW4SCALE_RULE@@AEBUtagSIZE@@@Z; CWICBitmapHelper::Scale(SCALE_RULE,tagSIZE const &)
0x18000c3c2  mov     ebx, eax
0x18000c3c4  test    eax, eax
0x18000c3c6  js      short loc_18000C402
0x18000c3c8  lea     rdx, [rdi+70h]; struct tagRECT *
0x18000c3cc  lea     rcx, [rbp+var_20]; this
0x18000c3d0  call    ?Crop@CWICBitmapHelper@@QEAAJAEBUtagRECT@@@Z; CWICBitmapHelper::Crop(tagRECT const &)
0x18000c3d5  mov     ebx, eax
0x18000c3d7  test    eax, eax
0x18000c3d9  js      short loc_18000C402
0x18000c3db  lea     r8, [rdi+80h]
0x18000c3e2  xor     edx, edx
0x18000c3e4  lea     rcx, [rbp+var_20]
0x18000c3e8  call    ?Scale@CWICBitmapHelper@@QEAAJW4SCALE_RULE@@AEBUtagSIZE@@@Z; CWICBitmapHelper::Scale(SCALE_RULE,tagSIZE const &)
0x18000c3ed  mov     ebx, eax
0x18000c3ef  test    eax, eax
0x18000c3f1  js      short loc_18000C402
0x18000c3f3  lea     r8, [rdi+58h]; HBITMAP *
0x18000c3f7  lea     rcx, [rbp+var_20]; this
0x18000c3fb  call    ?GetHBITMAP@CWICBitmapHelper@@QEAAJ_NPEAPEAUHBITMAP__@@@Z; CWICBitmapHelper::GetHBITMAP(bool,HBITMAP__ * *)
0x18000c400  mov     ebx, eax
0x18000c402  lea     rcx, [rbp+var_20]; this
0x18000c406  call    ??1CWICBitmapHelper@@UEAA@XZ; CWICBitmapHelper::~CWICBitmapHelper(void)
0x18000c40b  lea     rcx, [rbp+arg_10]
0x18000c40f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c414  lea     rcx, [rbp+arg_8]
0x18000c418  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c41d  mov     rdi, [rsp+50h+arg_18]
0x18000c422  mov     eax, ebx
0x18000c424  mov     rbx, [rsp+50h+arg_0]
0x18000c429  add     rsp, 50h
0x18000c42d  pop     rbp
0x18000c42e  retn
```
