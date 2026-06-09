# ConvertHBITMAPToWICBitmap(IWICImagingFactory *,HBITMAP__ *,WICBitmapAlphaChannelOption,IWICBitmapSource * *)

- ea: `0x1800066bc`
- end: `0x1800067b1`
- name: `?ConvertHBITMAPToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@W4WICBitmapAlphaChannelOption@@PEAPEAUIWICBitmapSource@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(struct IWICImagingFactory *, HBITMAP, __int64, struct IWICBitmapSource **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008558`

## callees

- `0x1800043a4`
- `0x1800066bc`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000671d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000671d`

## pseudocode

```c
__int64 __fastcall ConvertHBITMAPToWICBitmap(
        struct IWICImagingFactory *a1,
        HBITMAP a2,
        __int64 a3,
        struct IWICBitmapSource **a4)
{
  LPVOID v6; // rbx
  HRESULT v7; // ebx
  __int64 (__fastcall *v8)(LPVOID, HBITMAP, _QWORD, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct IWICBitmapSource **)); // rdi
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IWICBitmapSource **); // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  ppv = a1;
  if ( !a1
    || (((void (__fastcall *)(struct IWICImagingFactory *, HBITMAP, __int64))a1->lpVtbl->AddRef)(a1, a2, a3),
        (v6 = ppv) == 0) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v7 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
    if ( v7 < 0 )
      goto LABEL_8;
    v6 = ppv;
  }
  v11 = 0;
  v8 = *(__int64 (__fastcall **)(LPVOID, HBITMAP, _QWORD, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct IWICBitmapSource **)))(*(_QWORD *)v6 + 168LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  v7 = v8(v6, a2, 0, 2, &v11);
  if ( v7 >= 0 )
    v7 = (**v11)(v11, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94, a4);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
LABEL_8:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800066bc  mov     [rsp+arg_8], rbx
0x1800066c1  push    rbp
0x1800066c2  push    rsi
0x1800066c3  push    rdi
0x1800066c4  sub     rsp, 30h
0x1800066c8  mov     qword ptr [r9], 0
0x1800066cf  mov     rsi, r9
0x1800066d2  mov     [rsp+48h+arg_0], rcx
0x1800066d7  mov     rbp, rdx
0x1800066da  test    rcx, rcx
0x1800066dd  jz      short loc_1800066F5
0x1800066df  mov     rax, [rcx]
0x1800066e2  mov     rax, [rax+8]
0x1800066e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066eb  mov     rbx, [rsp+48h+arg_0]
0x1800066f0  test    rbx, rbx
0x1800066f3  jnz     short loc_18000672E
0x1800066f5  lea     rcx, [rsp+48h+arg_0]
0x1800066fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800066ff  xor     edx, edx; pUnkOuter
0x180006701  lea     rax, [rsp+48h+arg_0]
0x180006706  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000670d  mov     [rsp+48h+ppv], rax; ppv
0x180006712  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006719  lea     r8d, [rdx+1]; dwClsContext
0x18000671d  call    cs:__imp_CoCreateInstance
0x180006723  mov     ebx, eax
0x180006725  test    eax, eax
0x180006727  js      short loc_180006798
0x180006729  mov     rbx, [rsp+48h+arg_0]
0x18000672e  mov     [rsp+48h+arg_18], 0
0x180006737  lea     rcx, [rsp+48h+arg_18]
0x18000673c  mov     rax, [rbx]
0x18000673f  mov     rdi, [rax+0A8h]
0x180006746  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000674b  lea     rax, [rsp+48h+arg_18]
0x180006750  mov     r9d, 2
0x180006756  mov     [rsp+48h+ppv], rax
0x18000675b  xor     r8d, r8d
0x18000675e  mov     rax, rdi
0x180006761  mov     rdx, rbp
0x180006764  mov     rcx, rbx
0x180006767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000676c  mov     ebx, eax
0x18000676e  test    eax, eax
0x180006770  js      short loc_18000678E
0x180006772  mov     rcx, [rsp+48h+arg_18]
0x180006777  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x18000677e  mov     r8, rsi
0x180006781  mov     rax, [rcx]
0x180006784  mov     rax, [rax]
0x180006787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678c  mov     ebx, eax
0x18000678e  lea     rcx, [rsp+48h+arg_18]
0x180006793  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006798  lea     rcx, [rsp+48h+arg_0]
0x18000679d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800067a2  mov     eax, ebx
0x1800067a4  mov     rbx, [rsp+48h+arg_8]
0x1800067a9  add     rsp, 30h
0x1800067ad  pop     rdi
0x1800067ae  pop     rsi
0x1800067af  pop     rbp
0x1800067b0  retn
```
