# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180034d54`
- end: `0x180034f81`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180034cfc`

## callees

- `0x180034d54`
- `0x180034f88`
- `0x180034fec`
- `0x180035454`
- `0x180035484`
- `0x18003bf2c`
- `0x1800422d8`
- `0x180043820`
- `0x180043c48`
- `0x180048554`
- `0x180049210`
- `0x180079490`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180034d8f`
- `KERNEL32!GetCurrentProcessId` at `0x180034d8f`
- `KERNEL32!CreateMutexExW` at `0x180034dd1`
- `KERNEL32!CreateMutexExW` at `0x180034dd1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180034df7`
- `KERNEL32!WaitForSingleObjectEx` at `0x180034df7`

## string_xrefs

- `0x180034f04`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v7; // eax
  bool v8; // dl
  char *v9; // r9
  wil::details *v10; // rdi
  int ValueInternal; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // esi
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  void *v17; // rdx
  _DWORD *v19; // rcx
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v27; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v25 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 0;
  }
  else
  {
    if ( (v7 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = v6;
  }
  v27 = v10;
  v26 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v26, (bool *)v9);
  v14 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v19 = (_DWORD *)(4 * v26);
    if ( 4 * v26 )
    {
      *a2 = v19;
      ++*v19;
    }
    else
    {
      v20 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v22 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v21, (const char *)(unsigned int)v20, 304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
        return v22;
      }
      v6 = v25;
    }
    if ( v10 )
      wil::details::ReleaseMutex(v10, v12);
    if ( v6 )
      wil::details::CloseHandle(v6, v12);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v23);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v24);
    if ( v10 )
      wil::details::ReleaseMutex(v10, v17);
    wil::details::CloseHandle(v6, v17);
    return v14;
  }
}

```

## disassembly

```asm
0x180034d54  mov     [rsp-8+arg_10], rbx
0x180034d59  mov     [rsp-8+arg_18], rsi
0x180034d5e  push    rbp
0x180034d5f  push    rdi
0x180034d60  push    r14
0x180034d62  lea     rbp, [rsp-170h]
0x180034d6a  sub     rsp, 270h
0x180034d71  mov     rax, cs:__security_cookie
0x180034d78  xor     rax, rsp
0x180034d7b  mov     [rbp+180h+var_20], rax
0x180034d82  mov     r14, rdx
0x180034d85  mov     qword ptr [rdx], 0
0x180034d8c  mov     rbx, rcx
0x180034d8f  call    cs:__imp_GetCurrentProcessId
0x180034d96  nop     dword ptr [rax+rax+00h]
0x180034d9b  mov     [rsp+280h+var_258], rbx
0x180034da0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180034da7  mov     r9d, eax
0x180034daa  mov     [rsp+280h+var_260], 130h; int
0x180034db2  mov     edx, 104h; unsigned __int64
0x180034db7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180034dbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034dc1  mov     r9d, 1F0001h; dwDesiredAccess
0x180034dc7  lea     rdx, [rsp+280h+Name]; lpName
0x180034dcc  xor     r8d, r8d; dwFlags
0x180034dcf  xor     ecx, ecx; lpMutexAttributes
0x180034dd1  call    cs:__imp_CreateMutexExW
0x180034dd8  nop     dword ptr [rax+rax+00h]
0x180034ddd  mov     [rsp+280h+var_250], rax
0x180034de2  mov     rbx, rax
0x180034de5  test    rax, rax
0x180034de8  jz      loc_180034E94
0x180034dee  xor     r8d, r8d; bAlertable
0x180034df1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180034df4  mov     rcx, rax; hHandle
0x180034df7  call    cs:__imp_WaitForSingleObjectEx
0x180034dfe  nop     dword ptr [rax+rax+00h]
0x180034e03  cmp     eax, 102h
0x180034e08  jz      loc_180034EC1
0x180034e0e  test    eax, 0FFFFFF7Fh
0x180034e13  jnz     loc_180034EFD
0x180034e19  mov     rdi, rbx
0x180034e1c  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180034e21  mov     [rsp+280h+var_240], rdi
0x180034e26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180034e2b  mov     [rsp+280h+var_248], 0
0x180034e34  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180034e39  mov     esi, eax
0x180034e3b  test    eax, eax
0x180034e3d  jns     loc_180034EC8
0x180034e43  mov     rcx, [rbp+188h]; this
0x180034e4a  mov     r9d, eax; char *
0x180034e4d  mov     edx, 66h ; 'f'; void *
0x180034e52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e57  mov     rcx, [rbp+188h]; this
0x180034e5e  mov     r9d, esi; char *
0x180034e61  mov     edx, 6Fh ; 'o'; void *
0x180034e66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e6b  mov     rcx, [rbp+188h]; this
0x180034e72  mov     r9d, esi; char *
0x180034e75  mov     edx, 12Eh; void *
0x180034e7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034e7f  test    rdi, rdi
0x180034e82  jnz     loc_180034F16
0x180034e88  mov     rcx, rbx; this
0x180034e8b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180034e90  mov     eax, esi
0x180034e92  jmp     short loc_180034E99
0x180034e94  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034e99  mov     rcx, [rbp+180h+var_20]
0x180034ea0  xor     rcx, rsp; StackCookie
0x180034ea3  call    __security_check_cookie
0x180034ea8  lea     r11, [rsp+280h+var_10]
0x180034eb0  mov     rbx, [r11+30h]
0x180034eb4  mov     rsi, [r11+38h]
0x180034eb8  mov     rsp, r11
0x180034ebb  pop     r14
0x180034ebd  pop     rdi
0x180034ebe  pop     rbp
0x180034ebf  retn
0x180034ec1  xor     edi, edi
0x180034ec3  jmp     loc_180034E1C
0x180034ec8  mov     rax, [rsp+280h+var_248]
0x180034ecd  lea     rcx, ds:0[rax*4]
0x180034ed5  test    rcx, rcx
0x180034ed8  jz      short loc_180034F23
0x180034eda  mov     [r14], rcx
0x180034edd  mov     eax, [rcx]
0x180034edf  inc     eax
0x180034ee1  mov     [rcx], eax
0x180034ee3  test    rdi, rdi
0x180034ee6  jnz     loc_180034F74
0x180034eec  test    rbx, rbx
0x180034eef  jz      short loc_180034EF9
0x180034ef1  mov     rcx, rbx; this
0x180034ef4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180034ef9  xor     eax, eax
0x180034efb  jmp     short loc_180034E99
0x180034efd  mov     rcx, [rbp+188h]; this
0x180034f04  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f0b  mov     edx, 0E01h; void *
0x180034f10  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180034f16  mov     rcx, rdi; this
0x180034f19  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180034f1e  jmp     loc_180034E88
0x180034f23  mov     r8, r14
0x180034f26  lea     rdx, [rsp+280h+var_250]
0x180034f2b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180034f30  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180034f35  mov     ebx, eax
0x180034f37  test    eax, eax
0x180034f39  jns     short loc_180034F6A
0x180034f3b  mov     rcx, [rbp+188h]; this
0x180034f42  mov     r9d, eax; char *
0x180034f45  mov     edx, 137h; void *
0x180034f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034f4f  lea     rcx, [rsp+280h+var_240]
0x180034f54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034f59  lea     rcx, [rsp+280h+var_250]
0x180034f5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034f63  mov     eax, ebx
0x180034f65  jmp     loc_180034E99
0x180034f6a  mov     rbx, [rsp+280h+var_250]
0x180034f6f  jmp     loc_180034EE3
0x180034f74  mov     rcx, rdi; this
0x180034f77  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180034f7c  jmp     loc_180034EEC
```
