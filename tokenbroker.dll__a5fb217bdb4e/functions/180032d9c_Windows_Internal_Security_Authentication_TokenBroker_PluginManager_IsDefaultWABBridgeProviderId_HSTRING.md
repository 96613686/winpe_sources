# Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsDefaultWABBridgeProviderId(HSTRING__ *)

- ea: `0x180032d9c`
- end: `0x1800330c4`
- name: `?IsDefaultWABBridgeProviderId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA_NPEAUHSTRING__@@@Z`
- size: `808`
- prototype: `bool __fastcall(HSTRING)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031270`
- `0x1800323a0`
- `0x18006e064`

## callees

- `0x180007350`
- `0x180032d9c`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800330a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800330b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032e3b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800330a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800330b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032dfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032f99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033039`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180032e91`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180032e91`

## string_xrefs

- `0x180032e61`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsDefaultWABBridgeProviderId(
        HSTRING a1)
{
  unsigned __int64 v2; // rbx
  HSTRING v3; // rbx
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, HSTRING, __int64 *); // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _BYTE v19[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v20; // [rsp+38h] [rbp-71h] BYREF
  __int64 v21; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+48h] [rbp-61h] BYREF
  __int64 v23; // [rsp+50h] [rbp-59h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-51h] BYREF
  HSTRING string; // [rsp+60h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-41h] BYREF
  HSTRING v27; // [rsp+80h] [rbp-29h] BYREF
  HSTRING_HEADER v28; // [rsp+88h] [rbp-21h] BYREF
  HSTRING v29; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING_HEADER v30; // [rsp+A8h] [rbp-1h] BYREF

  if ( !a1 || !word_1801765B0 )
    return 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  if ( WindowsCreateStringReference(L"https://", 8u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = -1;
  do
    ++v2;
  while ( *(&word_1801765B0 + v2) );
  if ( v2 > 0xFFFFFFFF )
  {
    LODWORD(v2) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(&word_1801765B0, v2, &v30, &v29);
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &v28, &v27) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = v27;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  if ( (int)RoGetActivationFactory(v3, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v20) < 0
    || (v4 = v20,
        v5 = *(int (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v20 + 56LL),
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22),
        v5(v4, string, v29, &v22) < 0)
    || (v6 = v20,
        v7 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v20 + 48LL),
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23),
        v7(v6, a1, &v23) < 0) )
  {
LABEL_21:
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 0;
  }
  v24 = 0;
  if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 64LL))(v23, &v24) < 0 )
  {
LABEL_19:
    if ( v24 )
      WindowsDeleteString(v24);
    goto LABEL_21;
  }
  v21 = 0;
  v8 = v20;
  v9 = *(int (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v20 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  if ( v9(v8, string, v24, &v21) < 0
    || (v19[0] = 0, (*(int (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v21 + 168LL))(v21, v22, v19) < 0)
    || !v19[0] )
  {
    v10 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    goto LABEL_19;
  }
  v15 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  if ( v24 )
    WindowsDeleteString(v24);
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 1;
}

```

## disassembly

```asm
0x180032d9c  push    rbp
0x180032d9e  push    rbx
0x180032d9f  push    rsi
0x180032da0  push    rdi
0x180032da1  push    r12
0x180032da3  push    r14
0x180032da5  lea     rbp, [rsp-2Fh]
0x180032daa  sub     rsp, 0D8h
0x180032db1  mov     rax, cs:__security_cookie
0x180032db8  xor     rax, rsp
0x180032dbb  mov     [rbp+57h+var_40], rax
0x180032dbf  mov     rsi, rcx
0x180032dc2  xor     r14d, r14d
0x180032dc5  test    rcx, rcx
0x180032dc8  jz      loc_180032FEE
0x180032dce  cmp     cs:word_1801765B0, r14w
0x180032dd6  jz      loc_180032FEE
0x180032ddc  mov     [rbp+57h+var_C8], r14
0x180032de0  mov     [rbp+57h+var_B0], r14
0x180032de4  mov     [rbp+57h+var_B8], r14
0x180032de8  lea     r9, [rbp+57h+string]; string
0x180032dec  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180032df0  lea     edx, [r14+8]; length
0x180032df4  lea     rcx, aHttps; "https://"
0x180032dfb  call    cs:__imp_WindowsCreateStringReference
0x180032e01  mov     edi, 0C000000Dh
0x180032e06  test    eax, eax
0x180032e08  js      loc_180033095
0x180032e0e  lea     r12, word_1801765B0
0x180032e15  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180032e19  inc     rbx
0x180032e1c  cmp     [r12+rbx*2], r14w
0x180032e21  jnz     short loc_180032E19
0x180032e23  mov     eax, 0FFFFFFFFh
0x180032e28  cmp     rbx, rax
0x180032e2b  jbe     short loc_180032E41
0x180032e2d  mov     ebx, eax
0x180032e2f  xor     r9d, r9d; lpArguments
0x180032e32  xor     r8d, r8d; nNumberOfArguments
0x180032e35  lea     edx, [r9+1]; dwExceptionFlags
0x180032e39  mov     ecx, edi; dwExceptionCode
0x180032e3b  call    cs:__imp_RaiseException
0x180032e41  lea     r9, [rbp+57h+var_60]; string
0x180032e45  lea     r8, [rbp+57h+var_58]; hstringHeader
0x180032e49  mov     edx, ebx; length
0x180032e4b  mov     rcx, r12; sourceString
0x180032e4e  call    cs:__imp_WindowsCreateStringReference
0x180032e54  lea     r9, [rbp+57h+var_80]; string
0x180032e58  lea     r8, [rbp+57h+var_78]; hstringHeader
0x180032e5c  mov     edx, 16h; length
0x180032e61  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180032e68  call    cs:__imp_WindowsCreateStringReference
0x180032e6e  test    eax, eax
0x180032e70  js      loc_1800330AC
0x180032e76  mov     rbx, [rbp+57h+var_80]
0x180032e7a  lea     rcx, [rbp+57h+var_C8]
0x180032e7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032e83  lea     r8, [rbp+57h+var_C8]
0x180032e87  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180032e8e  mov     rcx, rbx
0x180032e91  call    cs:__imp_RoGetActivationFactory
0x180032e97  test    eax, eax
0x180032e99  js      loc_180032FA0
0x180032e9f  mov     rdi, [rbp+57h+var_C8]
0x180032ea3  mov     rax, [rdi]
0x180032ea6  mov     rbx, [rax+38h]
0x180032eaa  lea     rcx, [rbp+57h+var_B8]
0x180032eae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032eb3  lea     r9, [rbp+57h+var_B8]
0x180032eb7  mov     r8, [rbp+57h+var_60]
0x180032ebb  mov     rdx, [rbp+57h+string]
0x180032ebf  mov     rcx, rdi
0x180032ec2  mov     rax, rbx
0x180032ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eca  test    eax, eax
0x180032ecc  js      loc_180032FA0
0x180032ed2  mov     rdi, [rbp+57h+var_C8]
0x180032ed6  mov     rax, [rdi]
0x180032ed9  mov     rbx, [rax+30h]
0x180032edd  lea     rcx, [rbp+57h+var_B0]
0x180032ee1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032ee6  lea     r8, [rbp+57h+var_B0]
0x180032eea  mov     rdx, rsi
0x180032eed  mov     rcx, rdi
0x180032ef0  mov     rax, rbx
0x180032ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ef8  test    eax, eax
0x180032efa  js      loc_180032FA0
0x180032f00  mov     [rbp+57h+var_A8], r14
0x180032f04  mov     rcx, [rbp+57h+var_B0]
0x180032f08  mov     rax, [rcx]
0x180032f0b  lea     rdx, [rbp+57h+var_A8]
0x180032f0f  mov     rax, [rax+40h]
0x180032f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f18  test    eax, eax
0x180032f1a  js      short loc_180032F90
0x180032f1c  mov     [rbp+57h+var_C0], r14
0x180032f20  mov     rdi, [rbp+57h+var_C8]
0x180032f24  mov     rax, [rdi]
0x180032f27  mov     rbx, [rax+38h]
0x180032f2b  lea     rcx, [rbp+57h+var_C0]
0x180032f2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032f34  lea     r9, [rbp+57h+var_C0]
0x180032f38  mov     r8, [rbp+57h+var_A8]
0x180032f3c  mov     rdx, [rbp+57h+string]
0x180032f40  mov     rcx, rdi
0x180032f43  mov     rax, rbx
0x180032f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f4b  test    eax, eax
0x180032f4d  js      short loc_180032F76
0x180032f4f  mov     [rbp+57h+var_D0], r14b
0x180032f53  mov     rcx, [rbp+57h+var_C0]
0x180032f57  mov     rax, [rcx]
0x180032f5a  lea     r8, [rbp+57h+var_D0]
0x180032f5e  mov     rdx, [rbp+57h+var_B8]
0x180032f62  mov     rax, [rax+0A8h]
0x180032f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f6e  test    eax, eax
0x180032f70  jns     loc_18003300C
0x180032f76  mov     rcx, [rbp+57h+var_C0]
0x180032f7a  test    rcx, rcx
0x180032f7d  jz      short loc_180032F90
0x180032f7f  mov     [rbp+57h+var_C0], r14
0x180032f83  mov     rax, [rcx]
0x180032f86  mov     rax, [rax+10h]
0x180032f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f8f  nop
0x180032f90  mov     rcx, [rbp+57h+var_A8]; string
0x180032f94  test    rcx, rcx
0x180032f97  jz      short loc_180032FA0
0x180032f99  call    cs:__imp_WindowsDeleteString
0x180032f9f  nop
0x180032fa0  mov     rcx, [rbp+57h+var_B8]
0x180032fa4  test    rcx, rcx
0x180032fa7  jz      short loc_180032FBA
0x180032fa9  mov     [rbp+57h+var_B8], r14
0x180032fad  mov     rax, [rcx]
0x180032fb0  mov     rax, [rax+10h]
0x180032fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fb9  nop
0x180032fba  mov     rcx, [rbp+57h+var_B0]
0x180032fbe  test    rcx, rcx
0x180032fc1  jz      short loc_180032FD4
0x180032fc3  mov     [rbp+57h+var_B0], r14
0x180032fc7  mov     rax, [rcx]
0x180032fca  mov     rax, [rax+10h]
0x180032fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fd3  nop
0x180032fd4  mov     rcx, [rbp+57h+var_C8]
0x180032fd8  test    rcx, rcx
0x180032fdb  jz      short loc_180032FEE
0x180032fdd  mov     [rbp+57h+var_C8], r14
0x180032fe1  mov     rax, [rcx]
0x180032fe4  mov     rax, [rax+10h]
0x180032fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fed  nop
0x180032fee  xor     al, al
0x180032ff0  mov     rcx, [rbp+57h+var_40]
0x180032ff4  xor     rcx, rsp; StackCookie
0x180032ff7  call    __security_check_cookie
0x180032ffc  add     rsp, 0D8h
0x180033003  pop     r14
0x180033005  pop     r12
0x180033007  pop     rdi
0x180033008  pop     rsi
0x180033009  pop     rbx
0x18003300a  pop     rbp
0x18003300b  retn
0x18003300c  cmp     [rbp+57h+var_D0], r14b
0x180033010  jz      loc_180032F76
0x180033016  mov     rcx, [rbp+57h+var_C0]
0x18003301a  test    rcx, rcx
0x18003301d  jz      short loc_180033030
0x18003301f  mov     [rbp+57h+var_C0], r14
0x180033023  mov     rax, [rcx]
0x180033026  mov     rax, [rax+10h]
0x18003302a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003302f  nop
0x180033030  mov     rcx, [rbp+57h+var_A8]; string
0x180033034  test    rcx, rcx
0x180033037  jz      short loc_180033040
0x180033039  call    cs:__imp_WindowsDeleteString
0x18003303f  nop
0x180033040  mov     rcx, [rbp+57h+var_B8]
0x180033044  test    rcx, rcx
0x180033047  jz      short loc_18003305A
0x180033049  mov     [rbp+57h+var_B8], r14
0x18003304d  mov     rax, [rcx]
0x180033050  mov     rax, [rax+10h]
0x180033054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033059  nop
0x18003305a  mov     rcx, [rbp+57h+var_B0]
0x18003305e  test    rcx, rcx
0x180033061  jz      short loc_180033074
0x180033063  mov     [rbp+57h+var_B0], r14
0x180033067  mov     rax, [rcx]
0x18003306a  mov     rax, [rax+10h]
0x18003306e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033073  nop
0x180033074  mov     rcx, [rbp+57h+var_C8]
0x180033078  test    rcx, rcx
0x18003307b  jz      short loc_18003308E
0x18003307d  mov     [rbp+57h+var_C8], r14
0x180033081  mov     rdx, [rcx]
0x180033084  mov     rax, [rdx+10h]
0x180033088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003308d  nop
0x18003308e  mov     al, 1
0x180033090  jmp     loc_180032FF0
0x180033095  xor     r9d, r9d; lpArguments
0x180033098  xor     r8d, r8d; nNumberOfArguments
0x18003309b  lea     edx, [r9+1]; dwExceptionFlags
0x18003309f  mov     ecx, edi; dwExceptionCode
0x1800330a1  call    cs:__imp_RaiseException
0x1800330a7  jmp     loc_180032E0E
0x1800330ac  xor     r9d, r9d; lpArguments
0x1800330af  xor     r8d, r8d; nNumberOfArguments
0x1800330b2  lea     edx, [r9+1]; dwExceptionFlags
0x1800330b6  mov     ecx, edi; dwExceptionCode
0x1800330b8  call    cs:__imp_RaiseException
0x1800330be  jmp     loc_180032E76
```
