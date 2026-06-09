# CLoadImageToFill::LoadImageW(void)

- ea: `0x18000c180`
- end: `0x18000c2dd`
- name: `?LoadImageW@CLoadImageToFill@@MEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(CLoadImageToFill *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800043a4`
- `0x180007e30`
- `0x18000ba94`
- `0x18000bb80`
- `0x18000c050`
- `0x18000c180`
- `0x18000c558`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c1bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c1bc`

## pseudocode

```c
__int64 __fastcall CLoadImageToFill::LoadImageW(CLoadImageToFill *this)
{
  HRESULT Instance; // ebx
  __int64 v3; // r8
  bool v4; // dl
  struct IWICBitmapSource *v6; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v7[16]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v8; // [rsp+48h] [rbp-8h]
  __int64 v9; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v10; // [rsp+80h] [rbp+30h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+88h] [rbp+38h] BYREF

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
      v6 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v6);
      Instance = LoadImageWithWIC(ppv, *((_QWORD *)this + 12), v3, &v6, 0, 0);
      if ( Instance >= 0 )
      {
        CWICBitmapHelper::CWICBitmapHelper((CWICBitmapHelper *)v7, ppv, v6);
        Instance = CWICBitmapHelper::Scale(v7, 1, (char *)this + 104);
        if ( Instance >= 0 )
        {
          LODWORD(v9) = 0;
          v10 = 0;
          Instance = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v8 + 24LL))(
                       v8,
                       &v9,
                       &v10);
          if ( Instance >= 0 )
          {
            if ( (unsigned int)v9 > 0x7FFFFFFF || v10 > 0x7FFFFFFF )
            {
              Instance = -2147024362;
            }
            else
            {
              HIDWORD(v9) = v10;
              *((_QWORD *)this + 14) = v9;
              Instance = CWICBitmapHelper::GetHBITMAP((CWICBitmapHelper *)v7, v4, (HBITMAP *)this + 11);
            }
          }
        }
        CWICBitmapHelper::~CWICBitmapHelper((CWICBitmapHelper *)v7);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v6);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000c180  push    rbp
0x18000c182  push    rbx
0x18000c183  push    rdi
0x18000c184  mov     rbp, rsp
0x18000c187  sub     rsp, 50h
0x18000c18b  mov     rdi, rcx
0x18000c18e  mov     [rbp+arg_18], 0
0x18000c196  lea     rcx, [rbp+arg_18]
0x18000c19a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c19f  xor     edx, edx; pUnkOuter
0x18000c1a1  lea     rax, [rbp+arg_18]
0x18000c1a5  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000c1ac  mov     [rsp+50h+ppv], rax; ppv
0x18000c1b1  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000c1b8  lea     r8d, [rdx+1]; dwClsContext
0x18000c1bc  call    cs:__imp_CoCreateInstance
0x18000c1c2  mov     ebx, eax
0x18000c1c4  test    eax, eax
0x18000c1c6  js      loc_18000C2CA
0x18000c1cc  mov     rcx, [rdi+60h]
0x18000c1d0  xor     edx, edx
0x18000c1d2  xor     r9d, r9d
0x18000c1d5  xor     r8d, r8d
0x18000c1d8  mov     rax, [rcx]
0x18000c1db  mov     rax, [rax+28h]
0x18000c1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1e4  mov     ebx, eax
0x18000c1e6  test    eax, eax
0x18000c1e8  js      loc_18000C2CA
0x18000c1ee  lea     rcx, [rbp+var_20]
0x18000c1f2  mov     [rbp+var_20], 0
0x18000c1fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c1ff  mov     rdx, [rdi+60h]
0x18000c203  lea     r9, [rbp+var_20]
0x18000c207  mov     rcx, [rbp+arg_18]
0x18000c20b  mov     [rsp+50h+var_28], 0
0x18000c214  mov     [rsp+50h+ppv], 0
0x18000c21d  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x18000c222  mov     ebx, eax
0x18000c224  test    eax, eax
0x18000c226  js      loc_18000C2C1
0x18000c22c  mov     r8, [rbp+var_20]; struct IWICBitmapSource *
0x18000c230  lea     rcx, [rbp+var_18]; this
0x18000c234  mov     rdx, [rbp+arg_18]; struct IWICImagingFactory *
0x18000c238  call    ??0CWICBitmapHelper@@QEAA@PEAUIWICImagingFactory@@PEAUIWICBitmapSource@@@Z; CWICBitmapHelper::CWICBitmapHelper(IWICImagingFactory *,IWICBitmapSource *)
0x18000c23d  lea     r8, [rdi+68h]
0x18000c241  mov     edx, 1
0x18000c246  lea     rcx, [rbp+var_18]
0x18000c24a  call    ?Scale@CWICBitmapHelper@@QEAAJW4SCALE_RULE@@AEBUtagSIZE@@@Z; CWICBitmapHelper::Scale(SCALE_RULE,tagSIZE const &)
0x18000c24f  mov     ebx, eax
0x18000c251  test    eax, eax
0x18000c253  js      short loc_18000C2B8
0x18000c255  mov     rcx, [rbp+var_8]
0x18000c259  lea     r8, [rbp+arg_10]
0x18000c25d  mov     dword ptr [rbp+arg_8], 0
0x18000c264  lea     rdx, [rbp+arg_8]
0x18000c268  mov     [rbp+arg_10], 0
0x18000c26f  mov     rax, [rcx]
0x18000c272  mov     rax, [rax+18h]
0x18000c276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c27b  mov     ebx, eax
0x18000c27d  test    eax, eax
0x18000c27f  js      short loc_18000C2B8
0x18000c281  mov     eax, dword ptr [rbp+arg_8]
0x18000c284  mov     ecx, 7FFFFFFFh
0x18000c289  cmp     eax, ecx
0x18000c28b  ja      short loc_18000C2B3
0x18000c28d  mov     dword ptr [rbp+arg_8], eax
0x18000c290  mov     eax, [rbp+arg_10]
0x18000c293  cmp     eax, ecx
0x18000c295  ja      short loc_18000C2B3
0x18000c297  mov     dword ptr [rbp+arg_8+4], eax
0x18000c29a  lea     r8, [rdi+58h]; HBITMAP *
0x18000c29e  mov     rax, [rbp+arg_8]
0x18000c2a2  lea     rcx, [rbp+var_18]; this
0x18000c2a6  mov     [rdi+70h], rax
0x18000c2aa  call    ?GetHBITMAP@CWICBitmapHelper@@QEAAJ_NPEAPEAUHBITMAP__@@@Z; CWICBitmapHelper::GetHBITMAP(bool,HBITMAP__ * *)
0x18000c2af  mov     ebx, eax
0x18000c2b1  jmp     short loc_18000C2B8
0x18000c2b3  mov     ebx, 80070216h
0x18000c2b8  lea     rcx, [rbp+var_18]; this
0x18000c2bc  call    ??1CWICBitmapHelper@@UEAA@XZ; CWICBitmapHelper::~CWICBitmapHelper(void)
0x18000c2c1  lea     rcx, [rbp+var_20]
0x18000c2c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c2ca  lea     rcx, [rbp+arg_18]
0x18000c2ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000c2d3  mov     eax, ebx
0x18000c2d5  add     rsp, 50h
0x18000c2d9  pop     rdi
0x18000c2da  pop     rbx
0x18000c2db  pop     rbp
0x18000c2dc  retn
```
