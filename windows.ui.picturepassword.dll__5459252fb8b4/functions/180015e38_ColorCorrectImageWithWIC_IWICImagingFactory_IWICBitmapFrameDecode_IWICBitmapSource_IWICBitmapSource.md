# ColorCorrectImageWithWIC(IWICImagingFactory *,IWICBitmapFrameDecode *,IWICBitmapSource *,IWICBitmapSource * *)

- ea: `0x180015e38`
- end: `0x180015f26`
- name: `?ColorCorrectImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAPEAU3@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, struct IWICBitmapFrameDecode *, struct IWICColorTransform *, struct IWICBitmapSource **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013980`

## callees

- `0x1800043a4`
- `0x180015e38`
- `0x180015f2c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015ea3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015ea3`

## pseudocode

```c
__int64 __fastcall ColorCorrectImageWithWIC(
        struct IWICImagingFactory *a1,
        struct IWICBitmapFrameDecode *a2,
        struct IWICColorTransform *a3,
        struct IWICBitmapSource **a4)
{
  HRESULT v8; // edi
  struct IWICColorTransform *v9; // rcx
  __int64 (__fastcall **lpVtbl)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **); // rax
  struct IWICColorTransform *v12; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  ppv = a1;
  if ( a1 && (((void (__fastcall *)(struct IWICImagingFactory *))a1->lpVtbl->AddRef)(a1), ppv)
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv),
        v8 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv),
        v8 >= 0) )
  {
    v12 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    if ( (int)_GetsRGBTransformer(a2, (struct IWICBitmapSource *)a3, a1, &v12) < 0 )
    {
      lpVtbl = (__int64 (__fastcall **)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **))a3->lpVtbl;
      v9 = a3;
    }
    else
    {
      v9 = v12;
      lpVtbl = (__int64 (__fastcall **)(struct IWICColorTransform *, GUID *, struct IWICBitmapSource **))v12->lpVtbl;
    }
    v8 = (*lpVtbl)(v9, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015e38  mov     [rsp+arg_8], rbx
0x180015e3d  mov     [rsp+arg_10], rbp
0x180015e42  push    rsi
0x180015e43  push    rdi
0x180015e44  push    r14
0x180015e46  sub     rsp, 30h
0x180015e4a  mov     qword ptr [r9], 0
0x180015e51  mov     rsi, r9
0x180015e54  mov     [rsp+48h+arg_18], rcx
0x180015e59  mov     r14, r8
0x180015e5c  mov     rbp, rdx
0x180015e5f  mov     rbx, rcx
0x180015e62  test    rcx, rcx
0x180015e65  jz      short loc_180015E7B
0x180015e67  mov     rax, [rcx]
0x180015e6a  mov     rax, [rax+8]
0x180015e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e73  cmp     [rsp+48h+arg_18], 0
0x180015e79  jnz     short loc_180015EAF
0x180015e7b  lea     rcx, [rsp+48h+arg_18]
0x180015e80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015e85  xor     edx, edx; pUnkOuter
0x180015e87  lea     rax, [rsp+48h+arg_18]
0x180015e8c  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180015e93  mov     [rsp+48h+ppv], rax; ppv
0x180015e98  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180015e9f  lea     r8d, [rdx+1]; dwClsContext
0x180015ea3  call    cs:__imp_CoCreateInstance
0x180015ea9  mov     edi, eax
0x180015eab  test    eax, eax
0x180015ead  js      short loc_180015F07
0x180015eaf  lea     rcx, [rsp+48h+arg_0]
0x180015eb4  mov     [rsp+48h+arg_0], 0
0x180015ebd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015ec2  lea     r9, [rsp+48h+arg_0]; struct IWICColorTransform **
0x180015ec7  mov     r8, rbx; struct IWICImagingFactory *
0x180015eca  mov     rdx, r14; struct IWICBitmapSource *
0x180015ecd  mov     rcx, rbp; struct IWICBitmapFrameDecode *
0x180015ed0  call    ?_GetsRGBTransformer@@YAJPEAUIWICBitmapFrameDecode@@PEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUIWICColorTransform@@@Z; _GetsRGBTransformer(IWICBitmapFrameDecode *,IWICBitmapSource *,IWICImagingFactory *,IWICColorTransform * *)
0x180015ed5  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180015edc  mov     r8, rsi
0x180015edf  test    eax, eax
0x180015ee1  js      short loc_180015EED
0x180015ee3  mov     rcx, [rsp+48h+arg_0]
0x180015ee8  mov     rax, [rcx]
0x180015eeb  jmp     short loc_180015EF3
0x180015eed  mov     rax, [r14]
0x180015ef0  mov     rcx, r14
0x180015ef3  mov     rax, [rax]
0x180015ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015efb  lea     rcx, [rsp+48h+arg_0]
0x180015f00  mov     edi, eax
0x180015f02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015f07  lea     rcx, [rsp+48h+arg_18]
0x180015f0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015f11  mov     rbx, [rsp+48h+arg_8]
0x180015f16  mov     eax, edi
0x180015f18  mov     rbp, [rsp+48h+arg_10]
0x180015f1d  add     rsp, 30h
0x180015f21  pop     r14
0x180015f23  pop     rdi
0x180015f24  pop     rsi
0x180015f25  retn
```
