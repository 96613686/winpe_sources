# GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)

- ea: `0x18000772c`
- end: `0x1800078d0`
- name: `?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int128 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008558`
- `0x180013980`

## callees

- `0x1800043a4`
- `0x180006154`
- `0x18000772c`
- `0x180007dfc`
- `0x18000ba14`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000779b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000779b`

## pseudocode

```c
__int64 __fastcall GetStreamOfWICBitmapSourceWithOptions(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        __int64 a5,
        _QWORD *a6)
{
  _QWORD *v6; // rsi
  HRESULT v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int64, GUID *, _QWORD **); // rbx
  __int64 v15; // rbx
  _QWORD v17[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF

  v6 = a6;
  ppv = a1;
  *a6 = 0;
  if ( a1 && ((*(void (__fastcall **)(void *))(*(_QWORD *)a1 + 8LL))(a1), ppv)
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv),
        v10 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv),
        v10 >= 0) )
  {
    v17[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
    v10 = SHCreateMemoryStream(v12, v11, v17);
    if ( v10 >= 0 )
    {
      v13 = ppv;
      a6 = 0;
      v14 = *(__int64 (__fastcall **)(LPVOID, __int64, GUID *, _QWORD **))(*(_QWORD *)ppv + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a6);
      v10 = v14(v13, a3, &GUID_VendorMicrosoft, &a6);
      if ( v10 >= 0 )
      {
        v15 = v17[0];
        v10 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64))(*a6 + 24LL))(a6, v17[0], 2);
        if ( v10 >= 0 )
        {
          v18 = *a4;
          v10 = AddFrameToWICBitmap(ppv, a6, a2, &v18);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD *))(*a6 + 88LL))(a6);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 40LL))(
                      v15,
                      *(_QWORD *)&`GetStreamOfWICBitmapSourceWithOptions'::`23'::lnBeginning,
                      0,
                      0);
              if ( v10 >= 0 )
              {
                Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::InternalAddRef(v17);
                v10 = 0;
                *v6 = v15;
              }
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a6);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v17);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000772c  mov     [rsp-28h+arg_8], rbx
0x180007731  mov     [rsp-28h+arg_10], rsi
0x180007736  push    rbp
0x180007737  push    rdi
0x180007738  push    r12
0x18000773a  push    r14
0x18000773c  push    r15
0x18000773e  mov     rbp, rsp
0x180007741  sub     rsp, 50h
0x180007745  mov     rsi, [rbp+arg_28]
0x180007749  mov     r15, r9
0x18000774c  mov     [rbp+arg_0], rcx
0x180007750  mov     r14, r8
0x180007753  mov     r12, rdx
0x180007756  mov     qword ptr [rsi], 0
0x18000775d  test    rcx, rcx
0x180007760  jz      short loc_180007775
0x180007762  mov     rax, [rcx]
0x180007765  mov     rax, [rax+8]
0x180007769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776e  cmp     [rbp+arg_0], 0
0x180007773  jnz     short loc_1800077AB
0x180007775  lea     rcx, [rbp+arg_0]
0x180007779  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000777e  xor     edx, edx; pUnkOuter
0x180007780  lea     rax, [rbp+arg_0]
0x180007784  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000778b  mov     [rsp+50h+ppv], rax; ppv
0x180007790  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180007797  lea     r8d, [rdx+1]; dwClsContext
0x18000779b  call    cs:__imp_CoCreateInstance
0x1800077a1  mov     edi, eax
0x1800077a3  test    eax, eax
0x1800077a5  js      loc_1800078AC
0x1800077ab  lea     rcx, [rbp+var_20]
0x1800077af  mov     [rbp+var_20], 0
0x1800077b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800077bc  lea     r8, [rbp+var_20]
0x1800077c0  call    SHCreateMemoryStream
0x1800077c5  mov     edi, eax
0x1800077c7  test    eax, eax
0x1800077c9  js      loc_1800078A3
0x1800077cf  mov     rdi, [rbp+arg_0]
0x1800077d3  lea     rcx, [rbp+arg_28]
0x1800077d7  mov     [rbp+arg_28], 0
0x1800077df  mov     rax, [rdi]
0x1800077e2  mov     rbx, [rax+40h]
0x1800077e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800077eb  lea     r9, [rbp+arg_28]
0x1800077ef  mov     rdx, r14
0x1800077f2  lea     r8, GUID_VendorMicrosoft
0x1800077f9  mov     rcx, rdi
0x1800077fc  mov     rax, rbx
0x1800077ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007804  mov     edi, eax
0x180007806  test    eax, eax
0x180007808  js      loc_18000789A
0x18000780e  mov     rcx, [rbp+arg_28]
0x180007812  mov     r8d, 2
0x180007818  mov     rbx, [rbp+var_20]
0x18000781c  mov     rdx, rbx
0x18000781f  mov     rax, [rcx]
0x180007822  mov     rax, [rax+18h]
0x180007826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782b  mov     edi, eax
0x18000782d  test    eax, eax
0x18000782f  js      short loc_18000789A
0x180007831  movaps  xmm0, xmmword ptr [r15]
0x180007835  lea     r9, [rbp+var_10]
0x180007839  mov     rdx, [rbp+arg_28]
0x18000783d  mov     r8, r12
0x180007840  mov     rcx, [rbp+arg_0]
0x180007844  movdqa  [rbp+var_10], xmm0
0x180007849  call    ?AddFrameToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapEncoder@@PEAUIWICBitmapSource@@U_GUID@@W4EncodingOptions@@@Z; AddFrameToWICBitmap(IWICImagingFactory *,IWICBitmapEncoder *,IWICBitmapSource *,_GUID,EncodingOptions)
0x18000784e  mov     edi, eax
0x180007850  test    eax, eax
0x180007852  js      short loc_18000789A
0x180007854  mov     rcx, [rbp+arg_28]
0x180007858  mov     rax, [rcx]
0x18000785b  mov     rax, [rax+58h]
0x18000785f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007864  mov     edi, eax
0x180007866  test    eax, eax
0x180007868  js      short loc_18000789A
0x18000786a  mov     rax, [rbx]
0x18000786d  xor     r9d, r9d
0x180007870  mov     rdx, cs:?lnBeginning@?BH@??GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U4@W4EncodingOptions@@PEAPEAUIStream@@@Z@4T_LARGE_INTEGER@@B; _LARGE_INTEGER const `GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)'::`23'::lnBeginning
0x180007877  xor     r8d, r8d
0x18000787a  mov     rcx, rbx
0x18000787d  mov     rax, [rax+28h]
0x180007881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007886  mov     edi, eax
0x180007888  test    eax, eax
0x18000788a  js      short loc_18000789A
0x18000788c  lea     rcx, [rbp+var_20]
0x180007890  call    ?InternalAddRef@?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::InternalAddRef(void)
0x180007895  xor     edi, edi
0x180007897  mov     [rsi], rbx
0x18000789a  lea     rcx, [rbp+arg_28]
0x18000789e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800078a3  lea     rcx, [rbp+var_20]
0x1800078a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800078ac  lea     rcx, [rbp+arg_0]
0x1800078b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800078b5  lea     r11, [rsp+50h+var_s0]
0x1800078ba  mov     eax, edi
0x1800078bc  mov     rbx, [r11+38h]
0x1800078c0  mov     rsi, [r11+40h]
0x1800078c4  mov     rsp, r11
0x1800078c7  pop     r15
0x1800078c9  pop     r14
0x1800078cb  pop     r12
0x1800078cd  pop     rdi
0x1800078ce  pop     rbp
0x1800078cf  retn
```
