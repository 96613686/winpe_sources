# GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)

- ea: `0x180006588`
- end: `0x1800067b3`
- name: `?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006dcc`
- `0x1800078c4`

## callees

- `0x180003624`
- `0x180006588`
- `0x1800067bc`
- `0x1800067ec`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006798`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006798`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetStreamOfWICBitmapSourceWithOptions(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        int a5,
        IStream **a6)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // ebx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, __int64, GUID *, __int64 *); // rbx
  IStream *v14; // rcx
  __int64 v15; // rdx
  LPVOID v16; // rcx
  IStream *v18[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF

  *a6 = 0;
  ppv = a1;
  if ( a1 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)a1 + 8LL))(a1);
    a1 = ppv;
  }
  if ( a1
    || (Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv),
        v11 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv),
        v11 >= 0) )
  {
    v18[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
    v11 = SHCreateMemoryStream(v10, v9, v18);
    if ( v11 < 0 )
    {
      v14 = v18[0];
    }
    else
    {
      v20 = 0;
      v12 = ppv;
      v13 = *(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64 *))(*(_QWORD *)ppv + 64LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      v11 = v13(v12, a3, &GUID_VendorMicrosoft, &v20);
      if ( v11 < 0
        || (v11 = (*(__int64 (__fastcall **)(__int64, IStream *, __int64))(*(_QWORD *)v20 + 24LL))(v20, v18[0], 2),
            v11 < 0)
        || (v19 = *a4, v11 = AddFrameToWICBitmap(ppv, v20, a2, &v19, a5), v11 < 0)
        || (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 88LL))(v20), v11 < 0)
        || (v11 = (*(__int64 (__fastcall **)(IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)v18[0] + 40LL))(
                    v18[0],
                    `GetStreamOfWICBitmapSourceWithOptions'::`23'::lnBeginning,
                    0,
                    0),
            v11 < 0) )
      {
        v14 = v18[0];
      }
      else
      {
        v14 = v18[0];
        if ( v18[0] )
        {
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)v18[0] + 8LL))(v18[0]);
          v14 = v18[0];
        }
        *a6 = v14;
        v11 = 0;
      }
      v15 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v14 = v18[0];
      }
    }
    if ( v14 )
    {
      v18[0] = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  v16 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006588  push    rbp
0x18000658a  push    rbx
0x18000658b  push    rsi
0x18000658c  push    rdi
0x18000658d  push    r12
0x18000658f  push    r14
0x180006591  push    r15
0x180006593  mov     rbp, rsp
0x180006596  sub     rsp, 70h
0x18000659a  mov     rax, cs:__security_cookie
0x1800065a1  xor     rax, rsp
0x1800065a4  mov     [rbp+var_10], rax
0x1800065a8  mov     r12, r9
0x1800065ab  mov     r14, r8
0x1800065ae  mov     r15, rdx
0x1800065b1  mov     rsi, [rbp+arg_28]
0x1800065b5  mov     qword ptr [rsi], 0
0x1800065bc  mov     [rbp+var_18], rcx
0x1800065c0  test    rcx, rcx
0x1800065c3  jz      short loc_1800065D5
0x1800065c5  mov     rax, [rcx]
0x1800065c8  mov     rax, [rax+8]
0x1800065cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d1  mov     rcx, [rbp+var_18]
0x1800065d5  test    rcx, rcx
0x1800065d8  jz      loc_180006772
0x1800065de  mov     [rbp+var_40], 0
0x1800065e6  lea     rcx, [rbp+var_40]
0x1800065ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800065ef  lea     r8, [rbp+var_40]
0x1800065f3  call    SHCreateMemoryStream
0x1800065f8  mov     ebx, eax
0x1800065fa  test    eax, eax
0x1800065fc  js      loc_1800067A9
0x180006602  mov     [rbp+var_20], 0
0x18000660a  mov     rdi, [rbp+var_18]
0x18000660e  mov     rax, [rdi]
0x180006611  mov     rbx, [rax+40h]
0x180006615  lea     rcx, [rbp+var_20]
0x180006619  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000661e  lea     r9, [rbp+var_20]
0x180006622  lea     r8, GUID_VendorMicrosoft
0x180006629  mov     rdx, r14
0x18000662c  mov     rcx, rdi
0x18000662f  mov     rax, rbx
0x180006632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006637  mov     ebx, eax
0x180006639  test    eax, eax
0x18000663b  js      loc_18000676C
0x180006641  mov     rcx, [rbp+var_20]
0x180006645  mov     rax, [rcx]
0x180006648  mov     r8d, 2
0x18000664e  mov     rdx, [rbp+var_40]
0x180006652  mov     rax, [rax+18h]
0x180006656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665b  mov     ebx, eax
0x18000665d  test    eax, eax
0x18000665f  js      loc_18000676C
0x180006665  movaps  xmm0, xmmword ptr [r12]
0x18000666a  movdqa  [rbp+var_30], xmm0
0x18000666f  mov     eax, [rbp+arg_20]
0x180006672  mov     dword ptr [rsp+70h+ppv], eax
0x180006676  lea     r9, [rbp+var_30]
0x18000667a  mov     r8, r15
0x18000667d  mov     rdx, [rbp+var_20]
0x180006681  mov     rcx, [rbp+var_18]
0x180006685  call    ?AddFrameToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapEncoder@@PEAUIWICBitmapSource@@U_GUID@@W4EncodingOptions@@@Z; AddFrameToWICBitmap(IWICImagingFactory *,IWICBitmapEncoder *,IWICBitmapSource *,_GUID,EncodingOptions)
0x18000668a  mov     ebx, eax
0x18000668c  test    eax, eax
0x18000668e  js      loc_18000676C
0x180006694  mov     rcx, [rbp+var_20]
0x180006698  mov     rax, [rcx]
0x18000669b  mov     rax, [rax+58h]
0x18000669f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a4  mov     ebx, eax
0x1800066a6  test    eax, eax
0x1800066a8  js      loc_18000676C
0x1800066ae  mov     rcx, [rbp+var_40]
0x1800066b2  mov     rax, [rcx]
0x1800066b5  xor     r9d, r9d
0x1800066b8  xor     r8d, r8d
0x1800066bb  mov     rdx, cs:?lnBeginning@?BH@??GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U4@W4EncodingOptions@@PEAPEAUIStream@@@Z@4T_LARGE_INTEGER@@B; _LARGE_INTEGER const `GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)'::`23'::lnBeginning
0x1800066c2  mov     rax, [rax+28h]
0x1800066c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066cb  mov     ebx, eax
0x1800066cd  test    eax, eax
0x1800066cf  js      loc_18000676C
0x1800066d5  mov     rcx, [rbp+var_40]
0x1800066d9  test    rcx, rcx
0x1800066dc  jz      short loc_1800066EE
0x1800066de  mov     rax, [rcx]
0x1800066e1  mov     rax, [rax+8]
0x1800066e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ea  mov     rcx, [rbp+var_40]
0x1800066ee  mov     [rsi], rcx
0x1800066f1  xor     ebx, ebx
0x1800066f3  mov     rdx, [rbp+var_20]
0x1800066f7  test    rdx, rdx
0x1800066fa  jz      short loc_180006717
0x1800066fc  mov     [rbp+var_20], 0
0x180006704  mov     rax, [rdx]
0x180006707  mov     rcx, rdx
0x18000670a  mov     rax, [rax+10h]
0x18000670e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006713  mov     rcx, [rbp+var_40]
0x180006717  test    rcx, rcx
0x18000671a  jz      short loc_180006731
0x18000671c  mov     [rbp+var_40], 0
0x180006724  mov     rax, [rcx]
0x180006727  mov     rax, [rax+10h]
0x18000672b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006730  nop
0x180006731  mov     rcx, [rbp+var_18]
0x180006735  test    rcx, rcx
0x180006738  jz      short loc_18000674F
0x18000673a  mov     [rbp+var_18], 0
0x180006742  mov     rax, [rcx]
0x180006745  mov     rax, [rax+10h]
0x180006749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674e  nop
0x18000674f  mov     eax, ebx
0x180006751  mov     rcx, [rbp+var_10]
0x180006755  xor     rcx, rsp; StackCookie
0x180006758  call    __security_check_cookie
0x18000675d  add     rsp, 70h
0x180006761  pop     r15
0x180006763  pop     r14
0x180006765  pop     r12
0x180006767  pop     rdi
0x180006768  pop     rsi
0x180006769  pop     rbx
0x18000676a  pop     rbp
0x18000676b  retn
0x18000676c  mov     rcx, [rbp+var_40]
0x180006770  jmp     short loc_1800066F3
0x180006772  lea     rcx, [rbp+var_18]
0x180006776  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000677b  lea     rax, [rbp+var_18]
0x18000677f  mov     [rsp+70h+ppv], rax; ppv
0x180006784  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18000678b  xor     edx, edx; pUnkOuter
0x18000678d  lea     r8d, [rdx+1]; dwClsContext
0x180006791  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006798  call    cs:__imp_CoCreateInstance
0x18000679e  mov     ebx, eax
0x1800067a0  test    eax, eax
0x1800067a2  js      short loc_180006731
0x1800067a4  jmp     loc_1800065DE
0x1800067a9  mov     rcx, [rbp+var_40]
0x1800067ad  jmp     loc_180006717
```
