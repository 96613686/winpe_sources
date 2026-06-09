# LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)

- ea: `0x180007e30`
- end: `0x180007fce`
- name: `?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, __int64, __int64, struct IWICBitmapSource **, struct IWICBitmapFrameDecode *, struct IWICBitmapDecoder *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008558`
- `0x18000c180`
- `0x18000c2f0`
- `0x180013980`

## callees

- `0x1800043a4`
- `0x180007e30`
- `0x18000aa58`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ebf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007ebf`

## pseudocode

```c
__int64 __fastcall LoadImageWithWIC(
        struct IWICImagingFactory *a1,
        __int64 a2,
        __int64 a3,
        struct IWICBitmapSource **a4,
        struct IWICBitmapFrameDecode *a5,
        struct IWICBitmapDecoder *a6)
{
  struct IWICBitmapFrameDecode *v6; // rsi
  struct IWICBitmapDecoder *v9; // r14
  struct IWICImagingFactory *v10; // rbx
  HRESULT Instance; // ebx
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rdi
  struct IWICBitmapDecoder *v13; // rdi
  HRESULT (__stdcall *GetFrame)(IWICBitmapDecoder *, UINT, IWICBitmapFrameDecode **); // rbx
  struct IWICImagingFactory *ppv; // [rsp+60h] [rbp+30h] BYREF

  v6 = a5;
  *a4 = 0;
  if ( v6 )
    v6->lpVtbl = 0;
  v9 = a6;
  if ( a6 )
    *(GUID *)&a6->lpVtbl = GUID_NULL;
  ppv = a1;
  if ( !a1 || (((void (__fastcall *)(struct IWICImagingFactory *))a1->lpVtbl->AddRef)(a1), (v10 = ppv) == 0) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppv);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_18;
    v10 = ppv;
  }
  a6 = 0;
  CreateDecoderFromStream = v10->lpVtbl->CreateDecoderFromStream;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&a6);
  Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64, GUID *, _QWORD, struct IWICBitmapDecoder **))CreateDecoderFromStream)(
               v10,
               a2,
               &GUID_VendorMicrosoftBuiltIn,
               0,
               &a6);
  if ( Instance >= 0 )
  {
    if ( !v9
      || (Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, struct IWICBitmapDecoder *))a6->lpVtbl->GetContainerFormat)(
                       a6,
                       v9),
          Instance >= 0) )
    {
      v13 = a6;
      a5 = 0;
      GetFrame = a6->lpVtbl->GetFrame;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&a5);
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))GetFrame)(
                   v13,
                   0,
                   &a5);
      if ( Instance >= 0 )
      {
        Instance = WICOrientateFrame(ppv, a6, a5, 1, a4);
        if ( Instance >= 0 )
        {
          if ( v6 )
          {
            v6->lpVtbl = (struct IWICBitmapFrameDecodeVtbl *)a5;
            a5 = 0;
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&a5);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&a6);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180007e30  mov     [rsp-28h+arg_8], rbx
0x180007e35  mov     [rsp-28h+arg_10], rsi
0x180007e3a  push    rbp
0x180007e3b  push    rdi
0x180007e3c  push    r12
0x180007e3e  push    r14
0x180007e40  push    r15
0x180007e42  mov     rbp, rsp
0x180007e45  sub     rsp, 30h
0x180007e49  mov     rsi, [rbp+arg_20]
0x180007e4d  mov     r15, r9
0x180007e50  mov     qword ptr [r9], 0
0x180007e57  mov     r12, rdx
0x180007e5a  test    rsi, rsi
0x180007e5d  jz      short loc_180007E66
0x180007e5f  mov     qword ptr [rsi], 0
0x180007e66  mov     r14, [rbp+arg_28]
0x180007e6a  test    r14, r14
0x180007e6d  jz      short loc_180007E7B
0x180007e6f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007e76  movdqu  xmmword ptr [r14], xmm0
0x180007e7b  mov     [rbp+arg_0], rcx
0x180007e7f  test    rcx, rcx
0x180007e82  jz      short loc_180007E99
0x180007e84  mov     rax, [rcx]
0x180007e87  mov     rax, [rax+8]
0x180007e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e90  mov     rbx, [rbp+arg_0]
0x180007e94  test    rbx, rbx
0x180007e97  jnz     short loc_180007ED3
0x180007e99  lea     rcx, [rbp+arg_0]
0x180007e9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007ea2  xor     edx, edx; pUnkOuter
0x180007ea4  lea     rax, [rbp+arg_0]
0x180007ea8  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180007eaf  mov     [rsp+30h+ppv], rax; ppv
0x180007eb4  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180007ebb  lea     r8d, [rdx+1]; dwClsContext
0x180007ebf  call    cs:__imp_CoCreateInstance
0x180007ec5  mov     ebx, eax
0x180007ec7  test    eax, eax
0x180007ec9  js      loc_180007FAC
0x180007ecf  mov     rbx, [rbp+arg_0]
0x180007ed3  mov     [rbp+arg_28], 0
0x180007edb  lea     rcx, [rbp+arg_28]
0x180007edf  mov     rax, [rbx]
0x180007ee2  mov     rdi, [rax+20h]
0x180007ee6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007eeb  lea     rax, [rbp+arg_28]
0x180007eef  xor     r9d, r9d
0x180007ef2  mov     [rsp+30h+ppv], rax
0x180007ef7  lea     r8, GUID_VendorMicrosoftBuiltIn
0x180007efe  mov     rax, rdi
0x180007f01  mov     rdx, r12
0x180007f04  mov     rcx, rbx
0x180007f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0c  mov     ebx, eax
0x180007f0e  test    eax, eax
0x180007f10  js      loc_180007FA3
0x180007f16  test    r14, r14
0x180007f19  jz      short loc_180007F34
0x180007f1b  mov     rcx, [rbp+arg_28]
0x180007f1f  mov     rdx, r14
0x180007f22  mov     rax, [rcx]
0x180007f25  mov     rax, [rax+28h]
0x180007f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2e  mov     ebx, eax
0x180007f30  test    eax, eax
0x180007f32  js      short loc_180007FA3
0x180007f34  mov     rdi, [rbp+arg_28]
0x180007f38  lea     rcx, [rbp+arg_20]
0x180007f3c  mov     [rbp+arg_20], 0
0x180007f44  mov     rax, [rdi]
0x180007f47  mov     rbx, [rax+68h]
0x180007f4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007f50  lea     r8, [rbp+arg_20]
0x180007f54  xor     edx, edx
0x180007f56  mov     rcx, rdi
0x180007f59  mov     rax, rbx
0x180007f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f61  mov     ebx, eax
0x180007f63  test    eax, eax
0x180007f65  js      short loc_180007F9A
0x180007f67  mov     r8, [rbp+arg_20]; struct IWICBitmapFrameDecode *
0x180007f6b  mov     r9b, 1; bool
0x180007f6e  mov     rdx, [rbp+arg_28]; struct IWICBitmapDecoder *
0x180007f72  mov     rcx, [rbp+arg_0]; struct IWICImagingFactory *
0x180007f76  mov     [rsp+30h+ppv], r15; struct IWICBitmapSource **
0x180007f7b  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x180007f80  mov     ebx, eax
0x180007f82  test    eax, eax
0x180007f84  js      short loc_180007F9A
0x180007f86  test    rsi, rsi
0x180007f89  jz      short loc_180007F9A
0x180007f8b  mov     rax, [rbp+arg_20]
0x180007f8f  mov     [rsi], rax
0x180007f92  mov     [rbp+arg_20], 0
0x180007f9a  lea     rcx, [rbp+arg_20]
0x180007f9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007fa3  lea     rcx, [rbp+arg_28]
0x180007fa7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007fac  lea     rcx, [rbp+arg_0]
0x180007fb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180007fb5  mov     rsi, [rsp+30h+arg_10]
0x180007fba  mov     eax, ebx
0x180007fbc  mov     rbx, [rsp+30h+arg_8]
0x180007fc1  add     rsp, 30h
0x180007fc5  pop     r15
0x180007fc7  pop     r14
0x180007fc9  pop     r12
0x180007fcb  pop     rdi
0x180007fcc  pop     rbp
0x180007fcd  retn
```
