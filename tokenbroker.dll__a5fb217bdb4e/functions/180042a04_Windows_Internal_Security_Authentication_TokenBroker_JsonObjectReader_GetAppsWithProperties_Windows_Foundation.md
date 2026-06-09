# Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetAppsWithProperties(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x180042a04`
- end: `0x180042f10`
- name: `?GetAppsWithProperties@JsonObjectReader@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@6@@Z`
- size: `1292`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037330`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180042a04`
- `0x180042f18`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042dd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042e9e`

## string_xrefs

- `0x180042c20`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042c89`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042d1f`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042db5`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042e4b`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042e83`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042ed8`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`
- `0x180042efd`: `onecore\ds\security\tokenbroker\datastore\lib\jsonformat.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::JsonObjectReader::GetAppsWithProperties(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // [rsp+20h] [rbp-20h] BYREF
  __int64 v44; // [rsp+28h] [rbp-18h] BYREF
  __int64 v45; // [rsp+30h] [rbp-10h] BYREF
  HSTRING string; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  char v48; // [rsp+70h] [rbp+30h] BYREF
  __int64 v49; // [rsp+78h] [rbp+38h] BYREF

  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
         v4,
         &v43);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A1,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v5,
      v43);
    v40 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v6;
  }
  v44 = 0;
  v7 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 32);
  v8 = **v7;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v9 = v8(v7, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v44);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v9,
      v43);
LABEL_70:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    return v6;
  }
  v49 = 0;
  v10 = v44;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v12 = v11(v10, &v49);
  v6 = v12;
  if ( v12 < 0 )
  {
    v41 = (unsigned int)v12;
    v42 = 1191;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)v41,
      v43);
LABEL_69:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    goto LABEL_70;
  }
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v49 + 56LL))(v49, &v48);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
      (const char *)(unsigned int)v13,
      v43);
    v25 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
  }
  else
  {
    while ( v48 )
    {
      v45 = 0;
      string = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 48LL))(v49, &v45);
      v6 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B1,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v14,
          v43);
        if ( string )
          WindowsDeleteString(string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_69;
      }
      v15 = v45;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v17 = v16(v15, &string);
      v6 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B2,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v17,
          v43);
        if ( string )
          WindowsDeleteString(string);
        v32 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v33 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v34 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v35 = v43;
        if ( v43 )
        {
          v43 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        return v6;
      }
      v18 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v43 + 104LL))(v43, string);
      v6 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B3,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v18,
          v43);
        if ( string )
          WindowsDeleteString(string);
        v36 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        }
        v37 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        v38 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        }
        v39 = v43;
        if ( v43 )
        {
          v43 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
        return v6;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v49 + 64LL))(v49, &v48);
      v6 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B4,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\jsonformat.cpp",
          (const char *)(unsigned int)v19,
          v43);
        if ( string )
          WindowsDeleteString(string);
        v28 = v45;
        if ( v45 )
        {
          v45 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
        v31 = v43;
        if ( v43 )
        {
          v43 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        return v6;
      }
      if ( string )
        WindowsDeleteString(string);
      v20 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 64LL))(v43, a2);
    if ( (v6 & 0x80000000) != 0 )
    {
      v41 = v6;
      v42 = 1207;
      goto LABEL_74;
    }
    v21 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180042a04  mov     [rsp-18h+arg_0], rbx
0x180042a09  mov     [rsp-18h+arg_8], rsi
0x180042a0e  push    rbp
0x180042a0f  push    rdi
0x180042a10  push    r14
0x180042a12  mov     rbp, rsp
0x180042a15  sub     rsp, 40h
0x180042a19  mov     rsi, rdx
0x180042a1c  mov     rdi, rcx
0x180042a1f  xor     r14d, r14d
0x180042a22  mov     [rbp+var_20], r14
0x180042a26  lea     rcx, [rbp+var_20]
0x180042a2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042a2f  lea     rdx, [rbp+var_20]
0x180042a33  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180042a38  mov     ebx, eax
0x180042a3a  test    eax, eax
0x180042a3c  js      loc_180042E44
0x180042a42  mov     [rbp+var_18], r14
0x180042a46  mov     rdi, [rdi+20h]
0x180042a4a  mov     rax, [rdi]
0x180042a4d  mov     rbx, [rax]
0x180042a50  lea     rcx, [rbp+var_18]
0x180042a54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042a59  lea     r8, [rbp+var_18]
0x180042a5d  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x180042a64  mov     rcx, rdi
0x180042a67  mov     rax, rbx
0x180042a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a6f  mov     ebx, eax
0x180042a71  test    eax, eax
0x180042a73  js      loc_180042ED1
0x180042a79  mov     [rbp+arg_18], r14
0x180042a7d  mov     rdi, [rbp+var_18]
0x180042a81  mov     rax, [rdi]
0x180042a84  mov     rbx, [rax+30h]
0x180042a88  lea     rcx, [rbp+arg_18]
0x180042a8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042a91  lea     rdx, [rbp+arg_18]
0x180042a95  mov     rcx, rdi
0x180042a98  mov     rax, rbx
0x180042a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042aa0  mov     ebx, eax
0x180042aa2  test    eax, eax
0x180042aa4  js      loc_180042EEB
0x180042aaa  mov     [rbp+arg_10], r14b
0x180042aae  mov     rcx, [rbp+arg_18]
0x180042ab2  mov     rax, [rcx]
0x180042ab5  lea     rdx, [rbp+arg_10]
0x180042ab9  mov     rax, [rax+38h]
0x180042abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ac2  mov     ebx, eax
0x180042ac4  test    eax, eax
0x180042ac6  js      loc_180042C19
0x180042acc  cmp     [rbp+arg_10], r14b
0x180042ad0  jz      loc_180042B99
0x180042ad6  mov     [rbp+var_10], r14
0x180042ada  mov     [rbp+string], r14
0x180042ade  mov     rcx, [rbp+arg_18]
0x180042ae2  mov     rax, [rcx]
0x180042ae5  lea     rdx, [rbp+var_10]
0x180042ae9  mov     rax, [rax+30h]
0x180042aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042af2  mov     ebx, eax
0x180042af4  test    eax, eax
0x180042af6  js      loc_180042E7C
0x180042afc  mov     rdi, [rbp+var_10]
0x180042b00  mov     rax, [rdi]
0x180042b03  mov     rbx, [rax+30h]
0x180042b07  mov     rcx, [rbp+string]; string
0x180042b0b  call    cs:__imp_WindowsDeleteString
0x180042b11  mov     [rbp+string], r14
0x180042b15  lea     rdx, [rbp+string]
0x180042b19  mov     rcx, rdi
0x180042b1c  mov     rax, rbx
0x180042b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b24  mov     ebx, eax
0x180042b26  test    eax, eax
0x180042b28  js      loc_180042D18
0x180042b2e  mov     rcx, [rbp+var_20]
0x180042b32  mov     rax, [rcx]
0x180042b35  mov     rdx, [rbp+string]
0x180042b39  mov     rax, [rax+68h]
0x180042b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b42  mov     ebx, eax
0x180042b44  test    eax, eax
0x180042b46  js      loc_180042DAE
0x180042b4c  mov     rcx, [rbp+arg_18]
0x180042b50  mov     rax, [rcx]
0x180042b53  lea     rdx, [rbp+arg_10]
0x180042b57  mov     rax, [rax+40h]
0x180042b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b60  mov     ebx, eax
0x180042b62  test    eax, eax
0x180042b64  js      loc_180042C82
0x180042b6a  mov     rcx, [rbp+string]; string
0x180042b6e  test    rcx, rcx
0x180042b71  jz      short loc_180042B7A
0x180042b73  call    cs:__imp_WindowsDeleteString
0x180042b79  nop
0x180042b7a  mov     rcx, [rbp+var_10]
0x180042b7e  test    rcx, rcx
0x180042b81  jz      short loc_180042B94
0x180042b83  mov     [rbp+var_10], r14
0x180042b87  mov     rax, [rcx]
0x180042b8a  mov     rax, [rax+10h]
0x180042b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b93  nop
0x180042b94  jmp     loc_180042ACC
0x180042b99  mov     rcx, [rbp+var_20]
0x180042b9d  mov     rax, [rcx]
0x180042ba0  mov     rdx, rsi
0x180042ba3  mov     rax, [rax+40h]
0x180042ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bac  mov     ebx, eax
0x180042bae  test    eax, eax
0x180042bb0  js      loc_180042EF5
0x180042bb6  mov     rcx, [rbp+arg_18]
0x180042bba  test    rcx, rcx
0x180042bbd  jz      short loc_180042BD0
0x180042bbf  mov     [rbp+arg_18], r14
0x180042bc3  mov     rax, [rcx]
0x180042bc6  mov     rax, [rax+10h]
0x180042bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bcf  nop
0x180042bd0  mov     rcx, [rbp+var_18]
0x180042bd4  test    rcx, rcx
0x180042bd7  jz      short loc_180042BEA
0x180042bd9  mov     [rbp+var_18], r14
0x180042bdd  mov     rax, [rcx]
0x180042be0  mov     rax, [rax+10h]
0x180042be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042be9  nop
0x180042bea  mov     rcx, [rbp+var_20]
0x180042bee  test    rcx, rcx
0x180042bf1  jz      short loc_180042C04
0x180042bf3  mov     [rbp+var_20], r14
0x180042bf7  mov     rax, [rcx]
0x180042bfa  mov     rax, [rax+10h]
0x180042bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c03  nop
0x180042c04  mov     eax, ebx
0x180042c06  mov     rbx, [rsp+40h+arg_0]
0x180042c0b  mov     rsi, [rsp+40h+arg_8]
0x180042c10  add     rsp, 40h
0x180042c14  pop     r14
0x180042c16  pop     rdi
0x180042c17  pop     rbp
0x180042c18  retn
0x180042c19  mov     rcx, [rbp+18h]; this
0x180042c1d  mov     r9d, ebx; char *
0x180042c20  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180042c27  mov     edx, 4AAh; void *
0x180042c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c31  nop
0x180042c32  mov     rcx, [rbp+arg_18]
0x180042c36  test    rcx, rcx
0x180042c39  jz      short loc_180042C4C
0x180042c3b  mov     [rbp+arg_18], r14
0x180042c3f  mov     rax, [rcx]
0x180042c42  mov     rax, [rax+10h]
0x180042c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c4b  nop
0x180042c4c  mov     rcx, [rbp+var_18]
0x180042c50  test    rcx, rcx
0x180042c53  jz      short loc_180042C66
0x180042c55  mov     [rbp+var_18], r14
0x180042c59  mov     rax, [rcx]
0x180042c5c  mov     rax, [rax+10h]
0x180042c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c65  nop
0x180042c66  mov     rcx, [rbp+var_20]
0x180042c6a  test    rcx, rcx
0x180042c6d  jz      short loc_180042C80
0x180042c6f  mov     [rbp+var_20], r14
0x180042c73  mov     rax, [rcx]
0x180042c76  mov     rax, [rax+10h]
0x180042c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c7f  nop
0x180042c80  jmp     short loc_180042C04
0x180042c82  mov     rcx, [rbp+18h]; this
0x180042c86  mov     r9d, ebx; char *
0x180042c89  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180042c90  mov     edx, 4B4h; void *
0x180042c95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c9a  nop
0x180042c9b  mov     rcx, [rbp+string]; string
0x180042c9f  test    rcx, rcx
0x180042ca2  jz      short loc_180042CAB
0x180042ca4  call    cs:__imp_WindowsDeleteString
0x180042caa  nop
0x180042cab  mov     rcx, [rbp+var_10]
0x180042caf  test    rcx, rcx
0x180042cb2  jz      short loc_180042CC5
0x180042cb4  mov     [rbp+var_10], r14
0x180042cb8  mov     rax, [rcx]
0x180042cbb  mov     rax, [rax+10h]
0x180042cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cc4  nop
0x180042cc5  mov     rcx, [rbp+arg_18]
0x180042cc9  test    rcx, rcx
0x180042ccc  jz      short loc_180042CDF
0x180042cce  mov     [rbp+arg_18], r14
0x180042cd2  mov     rax, [rcx]
0x180042cd5  mov     rax, [rax+10h]
0x180042cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cde  nop
0x180042cdf  mov     rcx, [rbp+var_18]
0x180042ce3  test    rcx, rcx
0x180042ce6  jz      short loc_180042CF9
0x180042ce8  mov     [rbp+var_18], r14
0x180042cec  mov     rax, [rcx]
0x180042cef  mov     rax, [rax+10h]
0x180042cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cf8  nop
0x180042cf9  mov     rcx, [rbp+var_20]
0x180042cfd  test    rcx, rcx
0x180042d00  jz      short loc_180042D13
0x180042d02  mov     [rbp+var_20], r14
0x180042d06  mov     rax, [rcx]
0x180042d09  mov     rax, [rax+10h]
0x180042d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d12  nop
0x180042d13  jmp     loc_180042C04
0x180042d18  mov     rcx, [rbp+18h]; this
0x180042d1c  mov     r9d, ebx; char *
0x180042d1f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180042d26  mov     edx, 4B2h; void *
0x180042d2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042d30  nop
0x180042d31  mov     rcx, [rbp+string]; string
0x180042d35  test    rcx, rcx
0x180042d38  jz      short loc_180042D41
0x180042d3a  call    cs:__imp_WindowsDeleteString
0x180042d40  nop
0x180042d41  mov     rcx, [rbp+var_10]
0x180042d45  test    rcx, rcx
0x180042d48  jz      short loc_180042D5B
0x180042d4a  mov     [rbp+var_10], r14
0x180042d4e  mov     rax, [rcx]
0x180042d51  mov     rax, [rax+10h]
0x180042d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d5a  nop
0x180042d5b  mov     rcx, [rbp+arg_18]
0x180042d5f  test    rcx, rcx
0x180042d62  jz      short loc_180042D75
0x180042d64  mov     [rbp+arg_18], r14
0x180042d68  mov     rax, [rcx]
0x180042d6b  mov     rax, [rax+10h]
0x180042d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d74  nop
0x180042d75  mov     rcx, [rbp+var_18]
0x180042d79  test    rcx, rcx
0x180042d7c  jz      short loc_180042D8F
0x180042d7e  mov     [rbp+var_18], r14
0x180042d82  mov     rax, [rcx]
0x180042d85  mov     rax, [rax+10h]
0x180042d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d8e  nop
0x180042d8f  mov     rcx, [rbp+var_20]
0x180042d93  test    rcx, rcx
0x180042d96  jz      short loc_180042DA9
0x180042d98  mov     [rbp+var_20], r14
0x180042d9c  mov     rax, [rcx]
0x180042d9f  mov     rax, [rax+10h]
0x180042da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042da8  nop
0x180042da9  jmp     loc_180042C04
0x180042dae  mov     rcx, [rbp+18h]; this
0x180042db2  mov     r9d, ebx; char *
0x180042db5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180042dbc  mov     edx, 4B3h; void *
0x180042dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042dc6  nop
0x180042dc7  mov     rcx, [rbp+string]; string
0x180042dcb  test    rcx, rcx
0x180042dce  jz      short loc_180042DD7
0x180042dd0  call    cs:__imp_WindowsDeleteString
0x180042dd6  nop
0x180042dd7  mov     rcx, [rbp+var_10]
0x180042ddb  test    rcx, rcx
0x180042dde  jz      short loc_180042DF1
0x180042de0  mov     [rbp+var_10], r14
0x180042de4  mov     rax, [rcx]
0x180042de7  mov     rax, [rax+10h]
0x180042deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042df0  nop
0x180042df1  mov     rcx, [rbp+arg_18]
0x180042df5  test    rcx, rcx
0x180042df8  jz      short loc_180042E0B
0x180042dfa  mov     [rbp+arg_18], r14
0x180042dfe  mov     rax, [rcx]
0x180042e01  mov     rax, [rax+10h]
0x180042e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e0a  nop
0x180042e0b  mov     rcx, [rbp+var_18]
0x180042e0f  test    rcx, rcx
0x180042e12  jz      short loc_180042E25
0x180042e14  mov     [rbp+var_18], r14
0x180042e18  mov     rax, [rcx]
  ... truncated ...
```
