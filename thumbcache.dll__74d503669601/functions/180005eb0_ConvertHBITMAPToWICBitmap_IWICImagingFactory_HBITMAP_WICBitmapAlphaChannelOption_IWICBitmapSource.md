# ConvertHBITMAPToWICBitmap(IWICImagingFactory *,HBITMAP__ *,WICBitmapAlphaChannelOption,IWICBitmapSource * *)

- ea: `0x180005eb0`
- end: `0x180005ff9`
- name: `?ConvertHBITMAPToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@W4WICBitmapAlphaChannelOption@@PEAPEAUIWICBitmapSource@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, HBITMAP, enum WICBitmapAlphaChannelOption, struct IWICBitmapSource **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006dcc`
- `0x180007cb0`

## callees

- `0x180003624`
- `0x180005eb0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005fe3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005fe3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ConvertHBITMAPToWICBitmap(
        struct IWICImagingFactory *a1,
        HBITMAP a2,
        __int64 a3,
        struct IWICBitmapSource **a4)
{
  struct IWICImagingFactory *v6; // rbx
  HRESULT (__stdcall *CreateBitmapFromHBITMAP)(IWICImagingFactory *, HBITMAP, HPALETTE, WICBitmapAlphaChannelOption, IWICBitmap **); // rdi
  HRESULT v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, struct IWICBitmapSource **); // rcx
  LPVOID v10; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, struct IWICBitmapSource **); // [rsp+38h] [rbp-18h] BYREF

  v6 = a1;
  *a4 = 0;
  ppv = a1;
  if ( a1 )
  {
    ((void (__fastcall *)(struct IWICImagingFactory *, HBITMAP, __int64))a1->lpVtbl->AddRef)(a1, a2, a3);
    v6 = (struct IWICImagingFactory *)ppv;
  }
  if ( !v6 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v8 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
    if ( v8 < 0 )
      goto LABEL_8;
    v6 = (struct IWICImagingFactory *)ppv;
  }
  v13 = 0;
  CreateBitmapFromHBITMAP = v6->lpVtbl->CreateBitmapFromHBITMAP;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v8 = ((__int64 (__fastcall *)(struct IWICImagingFactory *, HBITMAP, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IWICBitmapSource **)))CreateBitmapFromHBITMAP)(
         v6,
         a2,
         0,
         0,
         &v13);
  if ( v8 >= 0 )
    v8 = (**v13)(v13, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, a4);
  v9 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IWICBitmapSource **)))(*v9)[2])(v9);
  }
LABEL_8:
  v10 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005eb0  mov     [rsp-18h+arg_0], rbx
0x180005eb5  mov     [rsp-18h+arg_10], rsi
0x180005eba  push    rbp
0x180005ebb  push    rdi
0x180005ebc  push    r14
0x180005ebe  mov     rbp, rsp
0x180005ec1  sub     rsp, 50h
0x180005ec5  mov     rax, cs:__security_cookie
0x180005ecc  xor     rax, rsp
0x180005ecf  mov     [rbp+var_10], rax
0x180005ed3  mov     rsi, r9
0x180005ed6  mov     r14, rdx
0x180005ed9  mov     rbx, rcx
0x180005edc  mov     qword ptr [r9], 0
0x180005ee3  mov     [rbp+var_20], rcx
0x180005ee7  test    rcx, rcx
0x180005eea  jz      short loc_180005EFC
0x180005eec  mov     rax, [rcx]
0x180005eef  mov     rax, [rax+8]
0x180005ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef8  mov     rbx, [rbp+var_20]
0x180005efc  test    rbx, rbx
0x180005eff  jz      loc_180005FBD
0x180005f05  mov     [rbp+var_18], 0
0x180005f0d  mov     rax, [rbx]
0x180005f10  mov     rdi, [rax+0A8h]
0x180005f17  lea     rcx, [rbp+var_18]
0x180005f1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005f20  lea     rax, [rbp+var_18]
0x180005f24  mov     [rsp+50h+ppv], rax
0x180005f29  xor     r9d, r9d
0x180005f2c  xor     r8d, r8d
0x180005f2f  mov     rdx, r14
0x180005f32  mov     rcx, rbx
0x180005f35  mov     rax, rdi
0x180005f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3d  mov     ebx, eax
0x180005f3f  test    eax, eax
0x180005f41  js      short loc_180005F5E
0x180005f43  mov     rcx, [rbp+var_18]
0x180005f47  mov     rax, [rcx]
0x180005f4a  mov     r8, rsi
0x180005f4d  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180005f54  mov     rax, [rax]
0x180005f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f5c  mov     ebx, eax
0x180005f5e  mov     rcx, [rbp+var_18]
0x180005f62  test    rcx, rcx
0x180005f65  jz      short loc_180005F7C
0x180005f67  mov     [rbp+var_18], 0
0x180005f6f  mov     rax, [rcx]
0x180005f72  mov     rax, [rax+10h]
0x180005f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7b  nop
0x180005f7c  mov     rcx, [rbp+var_20]
0x180005f80  test    rcx, rcx
0x180005f83  jz      short loc_180005F9A
0x180005f85  mov     [rbp+var_20], 0
0x180005f8d  mov     rax, [rcx]
0x180005f90  mov     rax, [rax+10h]
0x180005f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f99  nop
0x180005f9a  mov     eax, ebx
0x180005f9c  mov     rcx, [rbp+var_10]
0x180005fa0  xor     rcx, rsp; StackCookie
0x180005fa3  call    __security_check_cookie
0x180005fa8  lea     r11, [rsp+50h+var_s0]
0x180005fad  mov     rbx, [r11+20h]
0x180005fb1  mov     rsi, [r11+30h]
0x180005fb5  mov     rsp, r11
0x180005fb8  pop     r14
0x180005fba  pop     rdi
0x180005fbb  pop     rbp
0x180005fbc  retn
0x180005fbd  lea     rcx, [rbp+var_20]
0x180005fc1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005fc6  lea     rax, [rbp+var_20]
0x180005fca  mov     [rsp+50h+ppv], rax; ppv
0x180005fcf  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180005fd6  xor     edx, edx; pUnkOuter
0x180005fd8  lea     r8d, [rdx+1]; dwClsContext
0x180005fdc  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180005fe3  call    cs:__imp_CoCreateInstance
0x180005fe9  mov     ebx, eax
0x180005feb  test    eax, eax
0x180005fed  js      short loc_180005F7C
0x180005fef  mov     rbx, [rbp+var_20]
0x180005ff3  jmp     loc_180005F05
```
