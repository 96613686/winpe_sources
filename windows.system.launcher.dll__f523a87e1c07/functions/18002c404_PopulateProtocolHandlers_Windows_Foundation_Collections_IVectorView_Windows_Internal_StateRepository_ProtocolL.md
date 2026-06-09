# PopulateProtocolHandlers(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ProtocolLauncherInfo *> *,LaunchQuerySupportInternalType,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ProtocolLauncherInfo *> * *)

- ea: `0x18002c404`
- end: `0x18002c730`
- name: `?PopulateProtocolHandlers@@YAJPEAU?$IVectorView@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@W4LaunchQuerySupportInternalType@@PEAPEAU1234@@Z`
- size: `812`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002beec`
- `0x18002c1c4`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180021a88`
- `0x1800243f4`
- `0x18002c404`
- `0x18002ca80`
- `0x180111010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002c5d1`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x18002c5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c5c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c5c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c66d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c595`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c66d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c70a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PopulateProtocolHandlers(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  int v13; // esi
  int v14; // r15d
  int v15; // eax
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  PCWSTR StringRawBuffer; // rax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  char *v26; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  __int64 v29; // [rsp+38h] [rbp-28h] BYREF
  int v30; // [rsp+40h] [rbp-20h] BYREF
  char **v31; // [rsp+48h] [rbp-18h]
  int v32; // [rsp+50h] [rbp-10h]
  __int64 v33; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v35; // [rsp+B0h] [rbp+50h] BYREF
  int v36; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ProtocolLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0>>(
         v6,
         &v28);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v7,
      (int)v26);
LABEL_38:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    return v8;
  }
  LODWORD(v26) = 0;
  v29 = a1;
  v31 = &v26;
  v32 = 0;
  v33 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &v30);
  *(_DWORD *)v31 = v9;
  if ( v9 >= 0 && v30 )
  {
    v10 = v29;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v12 = v11(v10, 0, &v33);
    *(_DWORD *)v31 = v12;
  }
  v13 = 0;
  v14 = v30;
  while ( v13 != v14 && *(int *)v31 >= 0 )
  {
    if ( (unsigned __int8)ShouldExcludeAssociationForBrowserReplacment<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IProtocolLauncherInfo> const &>(&v33) )
      goto LABEL_23;
    string = 0;
    v19 = v33;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 120LL);
    WindowsDeleteString(0);
    string = 0;
    v21 = v20(v19, &string);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v21,
        (int)v26);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v24 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v8;
    }
    v36 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    GetEffectivePackageStatusForUser(0, StringRawBuffer, &v36);
    if ( (v36 & 0x10) == 0 )
    {
      v35 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 64LL))(v33, &v35);
      v8 = v23;
      if ( v23 < 0 )
      {
        v25 = 718;
        goto LABEL_36;
      }
      if ( a2 )
      {
        if ( a2 != 1 || v35 )
        {
LABEL_21:
          v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 104LL))(v28, v33);
          v8 = v23;
          if ( v23 < 0 )
          {
            v25 = 736;
LABEL_36:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
              (const char *)(unsigned int)v23,
              (int)v26);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            goto LABEL_38;
          }
        }
      }
      else if ( v35 != 1 )
      {
        goto LABEL_21;
      }
    }
    WindowsDeleteString(string);
    string = 0;
LABEL_23:
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(
      &v29,
      (unsigned int)++v13);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v8 = (unsigned int)v26;
  if ( (int)v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v26,
      (int)v26);
    v18 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v28 + 64LL))(v28, a3);
    v8 = v15;
    if ( v15 >= 0 )
    {
      v8 = 0;
      goto LABEL_38;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v15,
      (int)v26);
    v16 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002c404  mov     [rsp-38h+arg_0], rbx
0x18002c409  push    rbp
0x18002c40a  push    rsi
0x18002c40b  push    rdi
0x18002c40c  push    r12
0x18002c40e  push    r13
0x18002c410  push    r14
0x18002c412  push    r15
0x18002c414  mov     rbp, rsp
0x18002c417  sub     rsp, 60h
0x18002c41b  mov     r12, r8
0x18002c41e  mov     r14d, edx
0x18002c421  mov     rdi, rcx
0x18002c424  xor     r13d, r13d
0x18002c427  mov     [r8], r13
0x18002c42a  mov     [rbp+var_30], r13
0x18002c42e  lea     rcx, [rbp+var_30]
0x18002c432  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c437  lea     rdx, [rbp+var_30]
0x18002c43b  call    ??$CreateExternalObjectVector@VProtocolLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVProtocolLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::ProtocolLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::ProtocolLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::ProtocolLauncherInfo *>,0> * *)
0x18002c440  mov     ebx, eax
0x18002c442  test    eax, eax
0x18002c444  js      loc_18002C6A0
0x18002c44a  mov     dword ptr [rbp+var_40], r13d
0x18002c44e  mov     [rbp+var_28], rdi
0x18002c452  lea     rax, [rbp+var_40]
0x18002c456  mov     [rbp+var_18], rax
0x18002c45a  mov     [rbp+var_10], r13d
0x18002c45e  mov     [rbp+var_8], r13
0x18002c462  mov     rax, [rdi]
0x18002c465  lea     rdx, [rbp+var_20]
0x18002c469  mov     rcx, rdi
0x18002c46c  mov     rax, [rax+38h]
0x18002c470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c475  mov     rcx, [rbp+var_18]
0x18002c479  mov     [rcx], eax
0x18002c47b  test    eax, eax
0x18002c47d  js      short loc_18002C4B0
0x18002c47f  cmp     [rbp+var_20], r13d
0x18002c483  jbe     short loc_18002C4B0
0x18002c485  mov     rdi, [rbp+var_28]
0x18002c489  mov     rax, [rdi]
0x18002c48c  mov     rbx, [rax+30h]
0x18002c490  lea     rcx, [rbp+var_8]
0x18002c494  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c499  lea     r8, [rbp+var_8]
0x18002c49d  xor     edx, edx
0x18002c49f  mov     rcx, rdi
0x18002c4a2  mov     rax, rbx
0x18002c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4aa  mov     rcx, [rbp+var_18]
0x18002c4ae  mov     [rcx], eax
0x18002c4b0  mov     esi, r13d
0x18002c4b3  mov     r15d, [rbp+var_20]
0x18002c4b7  mov     rax, [rbp+var_18]
0x18002c4bb  cmp     esi, r15d
0x18002c4be  jnz     loc_18002C6BA
0x18002c4c4  lea     rcx, [rbp+var_8]
0x18002c4c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c4cd  mov     ebx, dword ptr [rbp+var_40]
0x18002c4d0  test    ebx, ebx
0x18002c4d2  js      short loc_18002C53E
0x18002c4d4  mov     rcx, [rbp+var_30]
0x18002c4d8  mov     rax, [rcx]
0x18002c4db  mov     rdx, r12
0x18002c4de  mov     rax, [rax+40h]
0x18002c4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4e7  mov     ebx, eax
0x18002c4e9  test    eax, eax
0x18002c4eb  jns     loc_18002C71F
0x18002c4f1  mov     rcx, [rbp+38h]; this
0x18002c4f5  mov     r9d, eax; char *
0x18002c4f8  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c4ff  mov     edx, 2E5h; void *
0x18002c504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c509  nop
0x18002c50a  mov     rcx, [rbp+var_30]
0x18002c50e  test    rcx, rcx
0x18002c511  jz      short loc_18002C524
0x18002c513  mov     [rbp+var_30], r13
0x18002c517  mov     rax, [rcx]
0x18002c51a  mov     rax, [rax+10h]
0x18002c51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c523  nop
0x18002c524  mov     eax, ebx
0x18002c526  mov     rbx, [rsp+60h+arg_0]
0x18002c52e  add     rsp, 60h
0x18002c532  pop     r15
0x18002c534  pop     r14
0x18002c536  pop     r13
0x18002c538  pop     r12
0x18002c53a  pop     rdi
0x18002c53b  pop     rsi
0x18002c53c  pop     rbp
0x18002c53d  retn
0x18002c53e  mov     rcx, [rbp+38h]; this
0x18002c542  mov     r9d, ebx; char *
0x18002c545  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c54c  mov     edx, 2E4h; void *
0x18002c551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c556  nop
0x18002c557  mov     rcx, [rbp+var_30]
0x18002c55b  test    rcx, rcx
0x18002c55e  jz      short loc_18002C571
0x18002c560  mov     [rbp+var_30], r13
0x18002c564  mov     rdx, [rcx]
0x18002c567  mov     rax, [rdx+10h]
0x18002c56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c570  nop
0x18002c571  jmp     short loc_18002C524
0x18002c573  lea     rcx, [rbp+var_8]
0x18002c577  call    ??$ShouldExcludeAssociationForBrowserReplacment@AEBV?$ComPtr@UIProtocolLauncherInfo@StateRepository@Internal@Windows@@@WRL@Microsoft@@@@YA_NAEBV?$ComPtr@UIProtocolLauncherInfo@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; ShouldExcludeAssociationForBrowserReplacment<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IProtocolLauncherInfo> const &>(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IProtocolLauncherInfo> const &)
0x18002c57c  test    al, al
0x18002c57e  jnz     loc_18002C63E
0x18002c584  mov     [rbp+string], r13
0x18002c588  mov     rdi, [rbp+var_8]
0x18002c58c  mov     rax, [rdi]
0x18002c58f  mov     rbx, [rax+78h]
0x18002c593  xor     ecx, ecx; string
0x18002c595  call    cs:__imp_WindowsDeleteString
0x18002c59b  mov     [rbp+string], r13
0x18002c59f  lea     rdx, [rbp+string]
0x18002c5a3  mov     rcx, rdi
0x18002c5a6  mov     rax, rbx
0x18002c5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5ae  mov     ebx, eax
0x18002c5b0  test    eax, eax
0x18002c5b2  js      loc_18002C650
0x18002c5b8  mov     [rbp+arg_18], r13d
0x18002c5bc  xor     edx, edx; length
0x18002c5be  mov     rcx, [rbp+string]; string
0x18002c5c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c5c8  lea     r8, [rbp+arg_18]
0x18002c5cc  mov     rdx, rax
0x18002c5cf  xor     ecx, ecx
0x18002c5d1  call    cs:__imp_GetEffectivePackageStatusForUser
0x18002c5d7  test    byte ptr [rbp+arg_18], 10h
0x18002c5db  jnz     short loc_18002C630
0x18002c5dd  mov     [rbp+arg_10], r13d
0x18002c5e1  mov     rcx, [rbp+var_8]
0x18002c5e5  mov     rax, [rcx]
0x18002c5e8  lea     rdx, [rbp+arg_10]
0x18002c5ec  mov     rax, [rax+40h]
0x18002c5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5f5  mov     ebx, eax
0x18002c5f7  test    eax, eax
0x18002c5f9  js      loc_18002C6ED
0x18002c5ff  test    r14d, r14d
0x18002c602  jz      loc_18002C6D7
0x18002c608  cmp     r14d, 1
0x18002c60c  jz      loc_18002C6C8
0x18002c612  mov     rcx, [rbp+var_30]
0x18002c616  mov     rax, [rcx]
0x18002c619  mov     rdx, [rbp+var_8]
0x18002c61d  mov     rax, [rax+68h]
0x18002c621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c626  mov     ebx, eax
0x18002c628  test    eax, eax
0x18002c62a  js      loc_18002C6E6
0x18002c630  mov     rcx, [rbp+string]; string
0x18002c634  call    cs:__imp_WindowsDeleteString
0x18002c63a  mov     [rbp+string], r13
0x18002c63e  inc     esi
0x18002c640  mov     edx, esi
0x18002c642  lea     rcx, [rbp+var_28]
0x18002c646  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVAppUriHandlerGroup@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerGroup *>>::get_at_current(uint)
0x18002c64b  jmp     loc_18002C4B7
0x18002c650  mov     rcx, [rbp+38h]; this
0x18002c654  mov     r9d, ebx; char *
0x18002c657  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c65e  mov     edx, 2C6h; void *
0x18002c663  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c668  nop
0x18002c669  mov     rcx, [rbp+string]; string
0x18002c66d  call    cs:__imp_WindowsDeleteString
0x18002c673  mov     [rbp+string], r13
0x18002c677  lea     rcx, [rbp+var_8]
0x18002c67b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c680  nop
0x18002c681  mov     rcx, [rbp+var_30]
0x18002c685  test    rcx, rcx
0x18002c688  jz      short loc_18002C69B
0x18002c68a  mov     [rbp+var_30], r13
0x18002c68e  mov     rax, [rcx]
0x18002c691  mov     rax, [rax+10h]
0x18002c695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c69a  nop
0x18002c69b  jmp     loc_18002C524
0x18002c6a0  mov     rcx, [rbp+38h]; this
0x18002c6a4  mov     r9d, eax; char *
0x18002c6a7  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c6ae  mov     edx, 2B8h; void *
0x18002c6b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6b8  jmp     short loc_18002C722
0x18002c6ba  cmp     [rax], r13d
0x18002c6bd  jl      loc_18002C4C4
0x18002c6c3  jmp     loc_18002C573
0x18002c6c8  cmp     [rbp+arg_10], r13d
0x18002c6cc  jnz     loc_18002C612
0x18002c6d2  jmp     loc_18002C630
0x18002c6d7  cmp     [rbp+arg_10], 1
0x18002c6db  jz      loc_18002C630
0x18002c6e1  jmp     loc_18002C612
0x18002c6e6  mov     edx, 2E0h
0x18002c6eb  jmp     short loc_18002C6F2
0x18002c6ed  mov     edx, 2CEh; void *
0x18002c6f2  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002c6f9  mov     r9d, eax; char *
0x18002c6fc  mov     rcx, [rbp+38h]; this
0x18002c700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c705  nop
0x18002c706  mov     rcx, [rbp+string]; string
0x18002c70a  call    cs:__imp_WindowsDeleteString
0x18002c710  mov     [rbp+string], r13
0x18002c714  lea     rcx, [rbp+var_8]
0x18002c718  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c71d  jmp     short loc_18002C722
0x18002c71f  mov     ebx, r13d
0x18002c722  lea     rcx, [rbp+var_30]
0x18002c726  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c72b  jmp     loc_18002C524
```
