# GetStreamFromHBITMAP(HBITMAP__ *,BITMAP_VERSION,WTS_STREAMTYPE *,_GUID const &,void * *)

- ea: `0x180006dcc`
- end: `0x180006f46`
- name: `?GetStreamFromHBITMAP@@YAJPEAUHBITMAP__@@W4BITMAP_VERSION@@PEAW4WTS_STREAMTYPE@@AEBU_GUID@@PEAPEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006c40`

## callees

- `0x180003624`
- `0x180005eb0`
- `0x180006588`
- `0x180006dcc`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetStreamFromHBITMAP(HBITMAP a1, __int64 a2, _DWORD *a3, __int64 a4, _QWORD *a5)
{
  int Instance; // ebx
  enum WICBitmapAlphaChannelOption v7; // r8d
  IStream *v8; // rcx
  struct IWICBitmapSource *v9; // rcx
  struct IWICImagingFactory *v10; // rcx
  IStream *v12[2]; // [rsp+30h] [rbp-40h] BYREF
  GUID v13; // [rsp+40h] [rbp-30h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+50h] [rbp-20h] BYREF
  struct IWICBitmapSource *v15; // [rsp+58h] [rbp-18h] BYREF

  *a5 = 0;
  *a3 = 2;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v15 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    Instance = ConvertHBITMAPToWICBitmap(ppv, a1, v7, &v15);
    if ( Instance >= 0 )
    {
      v12[0] = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
      v13 = GUID_WICPixelFormat32bppBGRA;
      Instance = GetStreamOfWICBitmapSourceWithOptions(
                   ppv,
                   (__int64)v15,
                   (__int64)&GUID_ContainerFormatBmp,
                   (__int128 *)&v13,
                   1,
                   v12);
      if ( Instance >= 0 )
        Instance = (**(__int64 (__fastcall ***)(IStream *, GUID *, _QWORD *))v12[0])(
                     v12[0],
                     &GUID_0000000c_0000_0000_c000_000000000046,
                     a5);
      v8 = v12[0];
      if ( v12[0] )
      {
        v12[0] = 0;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v9->lpVtbl->Release)(v9);
    }
  }
  v10 = ppv;
  if ( ppv )
  {
    ppv = 0;
    ((void (__fastcall *)(struct IWICImagingFactory *))v10->lpVtbl->Release)(v10);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180006dcc  mov     [rsp-18h+arg_8], rbx
0x180006dd1  push    rbp
0x180006dd2  push    rsi
0x180006dd3  push    rdi
0x180006dd4  mov     rbp, rsp
0x180006dd7  sub     rsp, 70h
0x180006ddb  mov     rax, cs:__security_cookie
0x180006de2  xor     rax, rsp
0x180006de5  mov     [rbp+var_10], rax
0x180006de9  mov     rdi, rcx
0x180006dec  mov     rsi, [rbp+arg_20]
0x180006df0  mov     qword ptr [rsi], 0
0x180006df7  mov     dword ptr [r8], 2
0x180006dfe  mov     [rbp+var_20], 0
0x180006e06  lea     rcx, [rbp+var_20]
0x180006e0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006e0f  lea     rax, [rbp+var_20]
0x180006e13  mov     [rsp+70h+ppv], rax; ppv
0x180006e18  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180006e1f  xor     edx, edx; pUnkOuter
0x180006e21  lea     r8d, [rdx+1]; dwClsContext
0x180006e25  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006e2c  call    cs:__imp_CoCreateInstance
0x180006e32  mov     ebx, eax
0x180006e34  test    eax, eax
0x180006e36  js      loc_180006F0A
0x180006e3c  mov     [rbp+var_18], 0
0x180006e44  lea     rcx, [rbp+var_18]
0x180006e48  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006e4d  lea     r9, [rbp+var_18]; struct IWICBitmapSource **
0x180006e51  mov     rdx, rdi; HBITMAP
0x180006e54  mov     rcx, [rbp+var_20]; struct IWICImagingFactory *
0x180006e58  call    ?ConvertHBITMAPToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@W4WICBitmapAlphaChannelOption@@PEAPEAUIWICBitmapSource@@@Z; ConvertHBITMAPToWICBitmap(IWICImagingFactory *,HBITMAP__ *,WICBitmapAlphaChannelOption,IWICBitmapSource * *)
0x180006e5d  mov     ebx, eax
0x180006e5f  test    eax, eax
0x180006e61  js      loc_180006EEC
0x180006e67  mov     [rbp+var_40], 0
0x180006e6f  lea     rcx, [rbp+var_40]
0x180006e73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006e78  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180006e7f  movdqu  [rbp+var_30], xmm0
0x180006e84  lea     rax, [rbp+var_40]
0x180006e88  mov     [rsp+70h+var_48], rax
0x180006e8d  mov     dword ptr [rsp+70h+ppv], 1
0x180006e95  lea     r9, [rbp+var_30]
0x180006e99  lea     r8, GUID_ContainerFormatBmp
0x180006ea0  mov     rdx, [rbp+var_18]
0x180006ea4  mov     rcx, [rbp+var_20]
0x180006ea8  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x180006ead  mov     ebx, eax
0x180006eaf  test    eax, eax
0x180006eb1  js      short loc_180006ECE
0x180006eb3  mov     rcx, [rbp+var_40]
0x180006eb7  mov     rax, [rcx]
0x180006eba  mov     r8, rsi
0x180006ebd  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180006ec4  mov     rax, [rax]
0x180006ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ecc  mov     ebx, eax
0x180006ece  mov     rcx, [rbp+var_40]
0x180006ed2  test    rcx, rcx
0x180006ed5  jz      short loc_180006EEC
0x180006ed7  mov     [rbp+var_40], 0
0x180006edf  mov     rax, [rcx]
0x180006ee2  mov     rax, [rax+10h]
0x180006ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eeb  nop
0x180006eec  mov     rcx, [rbp+var_18]
0x180006ef0  test    rcx, rcx
0x180006ef3  jz      short loc_180006F0A
0x180006ef5  mov     [rbp+var_18], 0
0x180006efd  mov     rax, [rcx]
0x180006f00  mov     rax, [rax+10h]
0x180006f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f09  nop
0x180006f0a  mov     rcx, [rbp+var_20]
0x180006f0e  test    rcx, rcx
0x180006f11  jz      short loc_180006F28
0x180006f13  mov     [rbp+var_20], 0
0x180006f1b  mov     rax, [rcx]
0x180006f1e  mov     rax, [rax+10h]
0x180006f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f27  nop
0x180006f28  mov     eax, ebx
0x180006f2a  mov     rcx, [rbp+var_10]
0x180006f2e  xor     rcx, rsp; StackCookie
0x180006f31  call    __security_check_cookie
0x180006f36  mov     rbx, [rsp+70h+arg_8]
0x180006f3e  add     rsp, 70h
0x180006f42  pop     rdi
0x180006f43  pop     rsi
0x180006f44  pop     rbp
0x180006f45  retn
```
