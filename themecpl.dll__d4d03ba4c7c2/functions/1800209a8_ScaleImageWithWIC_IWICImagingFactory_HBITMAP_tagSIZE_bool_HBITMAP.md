# ScaleImageWithWIC(IWICImagingFactory *,HBITMAP__ *,tagSIZE,bool,HBITMAP__ * *)

- ea: `0x1800209a8`
- end: `0x180020b9c`
- name: `?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@UtagSIZE@@_NPEAPEAU2@@Z`
- size: `500`
- prototype: `int(struct IWICImagingFactory *, HBITMAP, struct tagSIZE, bool, HBITMAP *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022030`
- `0x180038020`
- `0x180038924`

## callees

- `0x18002001c`
- `0x180020174`
- `0x1800209a8`
- `0x180020ba4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800209f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020ad5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800209f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020ad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ScaleImageWithWIC(
        struct IWICBitmapSource *a1,
        HBITMAP a2,
        struct tagSIZE a3,
        __int64 a4,
        HBITMAP *ppv)
{
  HBITMAP *v7; // rsi
  HRESULT Instance; // edi
  bool v9; // r9
  struct IWICBitmapSource *v10; // rcx
  struct IWICImagingFactory *v11; // rcx
  struct IWICBitmapSource *v12; // rbx
  enum WICBitmapDitherType v13; // r9d
  struct IWICBitmapSource *v14; // rcx
  HBITMAP *v15; // rcx
  struct IWICBitmapSource *v16; // rcx
  struct IWICBitmapSource *v17; // rcx
  struct IWICBitmapSource *v19; // [rsp+30h] [rbp-28h] BYREF
  struct IWICBitmapSource *v20; // [rsp+38h] [rbp-20h] BYREF
  struct _GUID v21; // [rsp+40h] [rbp-18h] BYREF
  struct IWICBitmapSource *v22; // [rsp+90h] [rbp+38h] BYREF

  v22 = a1;
  v7 = ppv;
  *ppv = 0;
  v20 = 0;
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    v22 = 0;
    Instance = (*((__int64 (__fastcall **)(HBITMAP *, HBITMAP, _QWORD, _QWORD, struct IWICBitmapSource **))*ppv + 21))(
                 ppv,
                 a2,
                 0,
                 0,
                 &v22);
    if ( Instance >= 0 )
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *, struct IWICBitmapSource **))v22->lpVtbl->QueryInterface)(
                   v22,
                   &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94,
                   &v20);
    v10 = v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v10->lpVtbl->Release)(v10);
    }
  }
  v11 = (struct IWICImagingFactory *)ppv;
  if ( ppv )
  {
    ppv = 0;
    ((void (__fastcall *)(struct IWICImagingFactory *))v11->lpVtbl->Release)(v11);
  }
  if ( Instance >= 0 )
  {
    v19 = 0;
    Instance = ScaleImageWithWIC(v11, v20, a3, v9, &v19);
    if ( Instance >= 0 )
    {
      v12 = v19;
      *v7 = 0;
      ppv = 0;
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v22 = 0;
        v21 = GUID_WICPixelFormat32bppBGRA;
        Instance = ConvertWICBitmapPixelFormat((struct IWICImagingFactory *)ppv, v12, &v21, v13, &v22);
        if ( Instance >= 0 )
          Instance = Convert32bppWICBitmapSourceToHBITMAP(v22, v7);
        v14 = v22;
        if ( v22 )
        {
          v22 = 0;
          ((void (__fastcall *)(struct IWICBitmapSource *))v14->lpVtbl->Release)(v14);
        }
      }
      v15 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*((void (__fastcall **)(HBITMAP *))*v15 + 2))(v15);
      }
    }
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v16->lpVtbl->Release)(v16);
    }
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *))v17->lpVtbl->Release)(v17);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800209a8  mov     [rsp-30h+arg_0], rcx
0x1800209ad  push    rbp
0x1800209ae  push    rbx
0x1800209af  push    rsi
0x1800209b0  push    rdi
0x1800209b1  push    r14
0x1800209b3  push    r15
0x1800209b5  mov     rbp, rsp
0x1800209b8  sub     rsp, 58h
0x1800209bc  mov     rbx, r8
0x1800209bf  mov     r14, rdx
0x1800209c2  xor     r15d, r15d
0x1800209c5  mov     rsi, [rbp+arg_20]
0x1800209c9  mov     [rsi], r15
0x1800209cc  mov     [rbp+var_20], r15
0x1800209d0  mov     [rbp+arg_20], r15
0x1800209d4  lea     rax, [rbp+arg_20]
0x1800209d8  mov     [rsp+58h+ppv], rax; ppv
0x1800209dd  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800209e4  xor     edx, edx; pUnkOuter
0x1800209e6  lea     r8d, [r15+1]; dwClsContext
0x1800209ea  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800209f1  call    cs:__imp_CoCreateInstance
0x1800209f8  nop     dword ptr [rax+rax+00h]
0x1800209fd  mov     edi, eax
0x1800209ff  test    eax, eax
0x180020a01  js      short loc_180020A68
0x180020a03  mov     [rbp+arg_0], r15
0x180020a07  mov     rcx, [rbp+arg_20]
0x180020a0b  mov     rax, [rcx]
0x180020a0e  lea     rdx, [rbp+arg_0]
0x180020a12  mov     [rsp+58h+ppv], rdx
0x180020a17  xor     r9d, r9d
0x180020a1a  xor     r8d, r8d
0x180020a1d  mov     rdx, r14
0x180020a20  mov     rax, [rax+0A8h]
0x180020a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a2c  mov     edi, eax
0x180020a2e  test    eax, eax
0x180020a30  js      short loc_180020A4E
0x180020a32  mov     rcx, [rbp+arg_0]
0x180020a36  mov     rax, [rcx]
0x180020a39  lea     r8, [rbp+var_20]
0x180020a3d  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180020a44  mov     rax, [rax]
0x180020a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a4c  mov     edi, eax
0x180020a4e  mov     rcx, [rbp+arg_0]
0x180020a52  test    rcx, rcx
0x180020a55  jz      short loc_180020A68
0x180020a57  mov     [rbp+arg_0], r15
0x180020a5b  mov     rax, [rcx]
0x180020a5e  mov     rax, [rax+10h]
0x180020a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a67  nop
0x180020a68  mov     rcx, [rbp+arg_20]
0x180020a6c  test    rcx, rcx
0x180020a6f  jz      short loc_180020A82
0x180020a71  mov     [rbp+arg_20], r15
0x180020a75  mov     rax, [rcx]
0x180020a78  mov     rax, [rax+10h]
0x180020a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a81  nop
0x180020a82  test    edi, edi
0x180020a84  js      loc_180020B72
0x180020a8a  mov     [rbp+var_28], r15
0x180020a8e  lea     rax, [rbp+var_28]
0x180020a92  mov     [rsp+58h+ppv], rax; struct IWICBitmapSource **
0x180020a97  mov     r8, rbx; struct tagSIZE
0x180020a9a  mov     rdx, [rbp+var_20]; struct IWICBitmapSource *
0x180020a9e  call    ?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)
0x180020aa3  mov     edi, eax
0x180020aa5  test    eax, eax
0x180020aa7  js      loc_180020B58
0x180020aad  mov     rbx, [rbp+var_28]
0x180020ab1  mov     [rsi], r15
0x180020ab4  mov     [rbp+arg_20], r15
0x180020ab8  lea     rax, [rbp+arg_20]
0x180020abc  mov     [rsp+58h+ppv], rax; ppv
0x180020ac1  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180020ac8  xor     edx, edx; pUnkOuter
0x180020aca  lea     r8d, [rdx+1]; dwClsContext
0x180020ace  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180020ad5  call    cs:__imp_CoCreateInstance
0x180020adc  nop     dword ptr [rax+rax+00h]
0x180020ae1  mov     edi, eax
0x180020ae3  test    eax, eax
0x180020ae5  js      short loc_180020B3E
0x180020ae7  mov     [rbp+arg_0], r15
0x180020aeb  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180020af2  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180020af7  lea     rax, [rbp+arg_0]
0x180020afb  mov     [rsp+58h+ppv], rax; struct IWICBitmapSource **
0x180020b00  lea     r8, [rbp+var_18]; struct _GUID *
0x180020b04  mov     rdx, rbx; struct IWICBitmapSource *
0x180020b07  mov     rcx, [rbp+arg_20]; struct IWICImagingFactory *
0x180020b0b  call    ?ConvertWICBitmapPixelFormat@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@U_GUID@@W4WICBitmapDitherType@@PEAPEAU2@@Z; ConvertWICBitmapPixelFormat(IWICImagingFactory *,IWICBitmapSource *,_GUID,WICBitmapDitherType,IWICBitmapSource * *)
0x180020b10  mov     edi, eax
0x180020b12  test    eax, eax
0x180020b14  js      short loc_180020B24
0x180020b16  mov     rdx, rsi; HBITMAP *
0x180020b19  mov     rcx, [rbp+arg_0]; struct IWICBitmapSource *
0x180020b1d  call    ?Convert32bppWICBitmapSourceToHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; Convert32bppWICBitmapSourceToHBITMAP(IWICBitmapSource *,HBITMAP__ * *)
0x180020b22  mov     edi, eax
0x180020b24  mov     rcx, [rbp+arg_0]
0x180020b28  test    rcx, rcx
0x180020b2b  jz      short loc_180020B3E
0x180020b2d  mov     [rbp+arg_0], r15
0x180020b31  mov     rax, [rcx]
0x180020b34  mov     rax, [rax+10h]
0x180020b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b3d  nop
0x180020b3e  mov     rcx, [rbp+arg_20]
0x180020b42  test    rcx, rcx
0x180020b45  jz      short loc_180020B58
0x180020b47  mov     [rbp+arg_20], r15
0x180020b4b  mov     rax, [rcx]
0x180020b4e  mov     rax, [rax+10h]
0x180020b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b57  nop
0x180020b58  mov     rcx, [rbp+var_28]
0x180020b5c  test    rcx, rcx
0x180020b5f  jz      short loc_180020B72
0x180020b61  mov     [rbp+var_28], r15
0x180020b65  mov     rax, [rcx]
0x180020b68  mov     rax, [rax+10h]
0x180020b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b71  nop
0x180020b72  mov     rcx, [rbp+var_20]
0x180020b76  test    rcx, rcx
0x180020b79  jz      short loc_180020B8C
0x180020b7b  mov     [rbp+var_20], r15
0x180020b7f  mov     rax, [rcx]
0x180020b82  mov     rax, [rax+10h]
0x180020b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b8b  nop
0x180020b8c  mov     eax, edi
0x180020b8e  add     rsp, 58h
0x180020b92  pop     r15
0x180020b94  pop     r14
0x180020b96  pop     rdi
0x180020b97  pop     rsi
0x180020b98  pop     rbx
0x180020b99  pop     rbp
0x180020b9a  retn
```
