# ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x180006880`
- end: `0x180006955`
- name: `?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008558`
- `0x18000c050`

## callees

- `0x1800043a4`
- `0x180006570`
- `0x1800067b8`
- `0x180006880`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800068de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800068de`

## pseudocode

```c
__int64 __fastcall ConvertWICBitmapToHBITMAP(struct IWICImagingFactory *a1, struct IWICBitmapSource *a2, HBITMAP *a3)
{
  HRESULT Instance; // ebx
  enum WICBitmapDitherType v6; // r9d
  struct _GUID v8; // [rsp+30h] [rbp-10h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+60h] [rbp+20h] BYREF
  struct IWICBitmapSource *v10; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  ppv = a1;
  if ( a1 && (((void (__fastcall *)(struct IWICImagingFactory *))a1->lpVtbl->AddRef)(a1), ppv)
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv),
        Instance = CoCreateInstance(
                     &CLSID_WICImagingFactory2,
                     0,
                     1u,
                     &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                     (LPVOID *)&ppv),
        Instance >= 0) )
  {
    v10 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    v8 = GUID_WICPixelFormat32bppBGRA;
    Instance = ConvertWICBitmapPixelFormat(ppv, a2, &v8, v6, &v10);
    if ( Instance >= 0 )
      Instance = Convert32bppWICBitmapSourceToHBITMAP(v10, a3);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180006880  mov     [rsp-18h+arg_8], rbx
0x180006885  push    rbp
0x180006886  push    rsi
0x180006887  push    rdi
0x180006888  mov     rbp, rsp
0x18000688b  sub     rsp, 40h
0x18000688f  mov     qword ptr [r8], 0
0x180006896  mov     rdi, r8
0x180006899  mov     [rbp+arg_0], rcx
0x18000689d  mov     rsi, rdx
0x1800068a0  test    rcx, rcx
0x1800068a3  jz      short loc_1800068B8
0x1800068a5  mov     rax, [rcx]
0x1800068a8  mov     rax, [rax+8]
0x1800068ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b1  cmp     [rbp+arg_0], 0
0x1800068b6  jnz     short loc_1800068EA
0x1800068b8  lea     rcx, [rbp+arg_0]
0x1800068bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800068c1  xor     edx, edx; pUnkOuter
0x1800068c3  lea     rax, [rbp+arg_0]
0x1800068c7  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800068ce  mov     [rsp+40h+ppv], rax; ppv
0x1800068d3  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800068da  lea     r8d, [rdx+1]; dwClsContext
0x1800068de  call    cs:__imp_CoCreateInstance
0x1800068e4  mov     ebx, eax
0x1800068e6  test    eax, eax
0x1800068e8  js      short loc_18000693D
0x1800068ea  lea     rcx, [rbp+arg_10]
0x1800068ee  mov     [rbp+arg_10], 0
0x1800068f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800068fb  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180006902  mov     rcx, [rbp+arg_0]; struct IWICImagingFactory *
0x180006906  lea     rax, [rbp+arg_10]
0x18000690a  lea     r8, [rbp+var_10]; struct _GUID *
0x18000690e  mov     [rsp+40h+ppv], rax; struct IWICBitmapSource **
0x180006913  mov     rdx, rsi; struct IWICBitmapSource *
0x180006916  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18000691b  call    ?ConvertWICBitmapPixelFormat@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@U_GUID@@W4WICBitmapDitherType@@PEAPEAU2@@Z; ConvertWICBitmapPixelFormat(IWICImagingFactory *,IWICBitmapSource *,_GUID,WICBitmapDitherType,IWICBitmapSource * *)
0x180006920  mov     ebx, eax
0x180006922  test    eax, eax
0x180006924  js      short loc_180006934
0x180006926  mov     rcx, [rbp+arg_10]; struct IWICBitmapSource *
0x18000692a  mov     rdx, rdi; HBITMAP *
0x18000692d  call    ?Convert32bppWICBitmapSourceToHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; Convert32bppWICBitmapSourceToHBITMAP(IWICBitmapSource *,HBITMAP__ * *)
0x180006932  mov     ebx, eax
0x180006934  lea     rcx, [rbp+arg_10]
0x180006938  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000693d  lea     rcx, [rbp+arg_0]
0x180006941  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006946  mov     eax, ebx
0x180006948  mov     rbx, [rsp+40h+arg_8]
0x18000694d  add     rsp, 40h
0x180006951  pop     rdi
0x180006952  pop     rsi
0x180006953  pop     rbp
0x180006954  retn
```
