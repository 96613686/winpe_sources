# LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)

- ea: `0x180004e90`
- end: `0x180005071`
- name: `?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z`
- size: `481`
- prototype: `int __high(struct IWICImagingFactory *, struct IStream *, enum LOAD_IMAGE_WITH_WIC_OPTION, struct IWICBitmapSource **, struct IWICBitmapFrameDecode **, struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007cb0`
- `0x18004636c`

## callees

- `0x180003624`
- `0x180004e90`
- `0x180005078`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000505b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000505b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LoadImageWithWIC(
        struct IWICImagingFactory *a1,
        __int64 a2,
        int a3,
        struct IWICBitmapSource **a4,
        __int64 a5,
        GUID *a6)
{
  struct IWICImagingFactory *v9; // rbx
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rdi
  HRESULT Instance; // ebx
  struct IWICBitmapDecoder *v12; // rdi
  HRESULT (__stdcall *GetFrame)(IWICBitmapDecoder *, UINT, IWICBitmapFrameDecode **); // rbx
  struct IWICBitmapFrameDecode *v14; // rcx
  struct IWICBitmapDecoder *v15; // rcx
  struct IWICImagingFactory *v16; // rcx
  struct IWICBitmapDecoder *v18; // [rsp+30h] [rbp-20h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+38h] [rbp-18h] BYREF
  struct IWICBitmapFrameDecode *v20; // [rsp+40h] [rbp-10h] BYREF

  v9 = a1;
  *a4 = 0;
  if ( a6 )
    *a6 = GUID_NULL;
  ppv = a1;
  if ( a1 )
  {
    ((void (__fastcall *)(struct IWICImagingFactory *))a1->lpVtbl->AddRef)(a1);
    v9 = ppv;
  }
  if ( !v9 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_15;
    v9 = ppv;
  }
  v18 = 0;
  CreateDecoderFromStream = v9->lpVtbl->CreateDecoderFromStream;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64, GUID *, _QWORD, struct IWICBitmapDecoder **))CreateDecoderFromStream)(
               v9,
               a2,
               &GUID_VendorMicrosoftBuiltIn,
               0,
               &v18);
  if ( Instance >= 0 )
  {
    if ( !a6
      || (Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, GUID *))v18->lpVtbl->GetContainerFormat)(
                       v18,
                       a6),
          Instance >= 0) )
    {
      v20 = 0;
      v12 = v18;
      GetFrame = v18->lpVtbl->GetFrame;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))GetFrame)(
                   v12,
                   0,
                   &v20);
      if ( Instance >= 0 )
        Instance = WICOrientateFrame(ppv, v18, v20, a3 == 2, a4);
      v14 = v20;
      if ( v20 )
      {
        v20 = 0;
        ((void (__fastcall *)(struct IWICBitmapFrameDecode *))v14->lpVtbl->Release)(v14);
      }
    }
  }
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v15->lpVtbl->Release)(v15);
  }
LABEL_15:
  v16 = ppv;
  if ( ppv )
  {
    ppv = 0;
    ((void (__fastcall *)(struct IWICImagingFactory *))v16->lpVtbl->Release)(v16);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004e90  mov     [rsp-28h+arg_0], rbx
0x180004e95  mov     [rsp-28h+arg_10], rsi
0x180004e9a  push    rbp
0x180004e9b  push    rdi
0x180004e9c  push    r12
0x180004e9e  push    r14
0x180004ea0  push    r15
0x180004ea2  mov     rbp, rsp
0x180004ea5  sub     rsp, 50h
0x180004ea9  mov     rax, cs:__security_cookie
0x180004eb0  xor     rax, rsp
0x180004eb3  mov     [rbp+var_8], rax
0x180004eb7  mov     r14, r9
0x180004eba  mov     r15d, r8d
0x180004ebd  mov     r12, rdx
0x180004ec0  mov     rbx, rcx
0x180004ec3  mov     rsi, [rbp+arg_28]
0x180004ec7  mov     qword ptr [r9], 0
0x180004ece  test    rsi, rsi
0x180004ed1  jz      short loc_180004EDE
0x180004ed3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180004eda  movdqu  xmmword ptr [rsi], xmm0
0x180004ede  mov     [rbp+var_18], rcx
0x180004ee2  test    rcx, rcx
0x180004ee5  jz      short loc_180004EF7
0x180004ee7  mov     rax, [rcx]
0x180004eea  mov     rax, [rax+8]
0x180004eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef3  mov     rbx, [rbp+var_18]
0x180004ef7  test    rbx, rbx
0x180004efa  jz      loc_180005035
0x180004f00  mov     [rbp+var_20], 0
0x180004f08  mov     rax, [rbx]
0x180004f0b  mov     rdi, [rax+20h]
0x180004f0f  lea     rcx, [rbp+var_20]
0x180004f13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004f18  lea     rax, [rbp+var_20]
0x180004f1c  mov     [rsp+50h+ppv], rax
0x180004f21  xor     r9d, r9d
0x180004f24  lea     r8, GUID_VendorMicrosoftBuiltIn
0x180004f2b  mov     rdx, r12
0x180004f2e  mov     rcx, rbx
0x180004f31  mov     rax, rdi
0x180004f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f39  mov     ebx, eax
0x180004f3b  test    eax, eax
0x180004f3d  js      loc_180004FD2
0x180004f43  test    rsi, rsi
0x180004f46  jz      short loc_180004F61
0x180004f48  mov     rcx, [rbp+var_20]
0x180004f4c  mov     rax, [rcx]
0x180004f4f  mov     rdx, rsi
0x180004f52  mov     rax, [rax+28h]
0x180004f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5b  mov     ebx, eax
0x180004f5d  test    eax, eax
0x180004f5f  js      short loc_180004FD2
0x180004f61  mov     [rbp+var_10], 0
0x180004f69  mov     rdi, [rbp+var_20]
0x180004f6d  mov     rax, [rdi]
0x180004f70  mov     rbx, [rax+68h]
0x180004f74  lea     rcx, [rbp+var_10]
0x180004f78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004f7d  lea     r8, [rbp+var_10]
0x180004f81  xor     edx, edx
0x180004f83  mov     rcx, rdi
0x180004f86  mov     rax, rbx
0x180004f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f8e  mov     ebx, eax
0x180004f90  test    eax, eax
0x180004f92  js      short loc_180004FB4
0x180004f94  cmp     r15d, 2
0x180004f98  setz    r9b; bool
0x180004f9c  mov     [rsp+50h+ppv], r14; struct IWICBitmapSource **
0x180004fa1  mov     r8, [rbp+var_10]; struct IWICBitmapFrameDecode *
0x180004fa5  mov     rdx, [rbp+var_20]; struct IWICBitmapDecoder *
0x180004fa9  mov     rcx, [rbp+var_18]; struct IWICImagingFactory *
0x180004fad  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x180004fb2  mov     ebx, eax
0x180004fb4  mov     rcx, [rbp+var_10]
0x180004fb8  test    rcx, rcx
0x180004fbb  jz      short loc_180004FD2
0x180004fbd  mov     [rbp+var_10], 0
0x180004fc5  mov     rax, [rcx]
0x180004fc8  mov     rax, [rax+10h]
0x180004fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd1  nop
0x180004fd2  mov     rcx, [rbp+var_20]
0x180004fd6  test    rcx, rcx
0x180004fd9  jz      short loc_180004FF0
0x180004fdb  mov     [rbp+var_20], 0
0x180004fe3  mov     rax, [rcx]
0x180004fe6  mov     rax, [rax+10h]
0x180004fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fef  nop
0x180004ff0  mov     rcx, [rbp+var_18]
0x180004ff4  test    rcx, rcx
0x180004ff7  jz      short loc_18000500E
0x180004ff9  mov     [rbp+var_18], 0
0x180005001  mov     rax, [rcx]
0x180005004  mov     rax, [rax+10h]
0x180005008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500d  nop
0x18000500e  mov     eax, ebx
0x180005010  mov     rcx, [rbp+var_8]
0x180005014  xor     rcx, rsp; StackCookie
0x180005017  call    __security_check_cookie
0x18000501c  lea     r11, [rsp+50h+var_s0]
0x180005021  mov     rbx, [r11+30h]
0x180005025  mov     rsi, [r11+40h]
0x180005029  mov     rsp, r11
0x18000502c  pop     r15
0x18000502e  pop     r14
0x180005030  pop     r12
0x180005032  pop     rdi
0x180005033  pop     rbp
0x180005034  retn
0x180005035  lea     rcx, [rbp+var_18]
0x180005039  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000503e  lea     rax, [rbp+var_18]
0x180005042  mov     [rsp+50h+ppv], rax; ppv
0x180005047  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000504e  xor     edx, edx; pUnkOuter
0x180005050  lea     r8d, [rdx+1]; dwClsContext
0x180005054  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000505b  call    cs:__imp_CoCreateInstance
0x180005061  mov     ebx, eax
0x180005063  test    eax, eax
0x180005065  js      short loc_180004FF0
0x180005067  mov     rbx, [rbp+var_18]
0x18000506b  jmp     loc_180004F00
```
