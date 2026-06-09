# ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)

- ea: `0x180046e90`
- end: `0x180046f94`
- name: `?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z`
- size: `260`
- prototype: `int(struct IWICImagingFactory *, struct IWICBitmapSource *, struct tagSIZE, bool, struct IWICBitmapSource **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004636c`

## callees

- `0x180003624`
- `0x1800060a4`
- `0x180006490`
- `0x180006c70`
- `0x180035830`
- `0x180046e90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046eff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046eff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScaleImageWithWIC(
        struct IWICImagingFactory *a1,
        struct IWICBitmapSource *a2,
        struct tagSIZE a3,
        __int64 a4,
        struct IWICBitmapSource **a5)
{
  HRESULT Instance; // edi
  enum WICBitmapDitherType v8; // r9d
  enum WICBitmapInterpolationMode v9; // r8d
  bool ppv; // [rsp+20h] [rbp-40h]
  struct _GUID v12; // [rsp+30h] [rbp-30h] BYREF
  struct IWICImagingFactory *v13; // [rsp+40h] [rbp-20h] BYREF
  struct IWICBitmapSource *v14; // [rsp+48h] [rbp-18h] BYREF

  *a5 = 0;
  v13 = a1;
  Microsoft::WRL::ComPtr<IBitmapResult>::InternalAddRef(&v13);
  if ( v13
    || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13),
        Instance = CoCreateInstance(
                     &CLSID_WICImagingFactory2,
                     0,
                     1u,
                     &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                     (LPVOID *)&v13),
        Instance >= 0) )
  {
    v14 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v12 = GUID_WICPixelFormat32bppPBGRA;
    Instance = ConvertWICBitmapPixelFormat(v13, a2, &v12, v8, &v14);
    if ( Instance >= 0 )
      Instance = ScaleWICBitmapSource(v13, v14, v9, a3, ppv, a5);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180046e90  mov     [rsp-18h+arg_0], rbx
0x180046e95  mov     [rsp-18h+arg_18], rsi
0x180046e9a  push    rbp
0x180046e9b  push    rdi
0x180046e9c  push    r14
0x180046e9e  mov     rbp, rsp
0x180046ea1  sub     rsp, 60h
0x180046ea5  mov     rax, cs:__security_cookie
0x180046eac  xor     rax, rsp
0x180046eaf  mov     [rbp+var_10], rax
0x180046eb3  mov     rbx, r8
0x180046eb6  mov     r14, rdx
0x180046eb9  mov     rsi, [rbp+arg_20]
0x180046ebd  mov     qword ptr [rsi], 0
0x180046ec4  mov     [rbp+var_20], rcx
0x180046ec8  lea     rcx, [rbp+var_20]
0x180046ecc  call    ?InternalAddRef@?$ComPtr@UIBitmapResult@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IBitmapResult>::InternalAddRef(void)
0x180046ed1  nop
0x180046ed2  cmp     [rbp+var_20], 0
0x180046ed7  jnz     short loc_180046F0B
0x180046ed9  lea     rcx, [rbp+var_20]
0x180046edd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046ee2  lea     rax, [rbp+var_20]
0x180046ee6  mov     [rsp+60h+ppv], rax; ppv
0x180046eeb  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180046ef2  xor     edx, edx; pUnkOuter
0x180046ef4  lea     r8d, [rdx+1]; dwClsContext
0x180046ef8  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180046eff  call    cs:__imp_CoCreateInstance
0x180046f05  mov     edi, eax
0x180046f07  test    eax, eax
0x180046f09  js      short loc_180046F68
0x180046f0b  mov     [rbp+var_18], 0
0x180046f13  lea     rcx, [rbp+var_18]
0x180046f17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046f1c  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x180046f23  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x180046f28  lea     rax, [rbp+var_18]
0x180046f2c  mov     [rsp+60h+ppv], rax; bool
0x180046f31  lea     r8, [rbp+var_30]; struct _GUID *
0x180046f35  mov     rdx, r14; struct IWICBitmapSource *
0x180046f38  mov     rcx, [rbp+var_20]; struct IWICImagingFactory *
0x180046f3c  call    ?ConvertWICBitmapPixelFormat@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@U_GUID@@W4WICBitmapDitherType@@PEAPEAU2@@Z; ConvertWICBitmapPixelFormat(IWICImagingFactory *,IWICBitmapSource *,_GUID,WICBitmapDitherType,IWICBitmapSource * *)
0x180046f41  mov     edi, eax
0x180046f43  test    eax, eax
0x180046f45  js      short loc_180046F5E
0x180046f47  mov     [rsp+60h+var_38], rsi; struct IWICBitmapSource **
0x180046f4c  mov     r9, rbx; struct tagSIZE
0x180046f4f  mov     rdx, [rbp+var_18]; struct IWICBitmapSource *
0x180046f53  mov     rcx, [rbp+var_20]; struct IWICImagingFactory *
0x180046f57  call    ?ScaleWICBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@W4WICBitmapInterpolationMode@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleWICBitmapSource(IWICImagingFactory *,IWICBitmapSource *,WICBitmapInterpolationMode,tagSIZE,bool,IWICBitmapSource * *)
0x180046f5c  mov     edi, eax
0x180046f5e  lea     rcx, [rbp+var_18]
0x180046f62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046f67  nop
0x180046f68  lea     rcx, [rbp+var_20]
0x180046f6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046f71  mov     eax, edi
0x180046f73  mov     rcx, [rbp+var_10]
0x180046f77  xor     rcx, rsp; StackCookie
0x180046f7a  call    __security_check_cookie
0x180046f7f  lea     r11, [rsp+60h+var_s0]
0x180046f84  mov     rbx, [r11+20h]
0x180046f88  mov     rsi, [r11+38h]
0x180046f8c  mov     rsp, r11
0x180046f8f  pop     r14
0x180046f91  pop     rdi
0x180046f92  pop     rbp
0x180046f93  retn
```
