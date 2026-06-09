# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c5e8`
- end: `0x18000c7bd`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800336cc`

## callees

- `0x18000c584`
- `0x18000c5e8`
- `0x18000c7c4`
- `0x18000c82c`
- `0x18002ba20`
- `0x18002c090`
- `0x18002c1d4`
- `0x18002c2f8`
- `0x18002cc4c`
- `0x18002d7bc`
- `0x180034450`
- `0x180034bf8`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c662`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c61d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c61d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned int v11; // edi
  void *v12; // rdx
  _DWORD *v13; // rcx
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  v6 = v18;
  if ( !v18 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v18,
    &v19);
  v20 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
  v11 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v14 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v15,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        goto LABEL_10;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    v14 = 0;
LABEL_10:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    return v14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66,
    (unsigned int)"wil",
    (const char *)(unsigned int)ValueInternal,
    304);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v11, v16);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v11, v17);
  if ( v19 )
    wil::details::ReleaseMutex(v19, v12);
  wil::details::CloseHandle(v6, v12);
  return v11;
}

```

## disassembly

```asm
0x18000c5e8  mov     [rsp-8+arg_10], rbx
0x18000c5ed  push    rbp
0x18000c5ee  push    rsi
0x18000c5ef  push    rdi
0x18000c5f0  lea     rbp, [rsp-170h]
0x18000c5f8  sub     rsp, 270h
0x18000c5ff  mov     rax, cs:__security_cookie
0x18000c606  xor     rax, rsp
0x18000c609  mov     [rbp+180h+var_20], rax
0x18000c610  mov     rsi, rdx
0x18000c613  mov     rbx, rcx
0x18000c616  mov     qword ptr [rdx], 0
0x18000c61d  call    cs:__imp_GetCurrentProcessId
0x18000c623  mov     r9d, eax
0x18000c626  mov     [rsp+280h+var_258], rbx
0x18000c62b  mov     [rsp+280h+var_260], 130h; int
0x18000c633  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c63a  mov     edx, 104h; unsigned __int64
0x18000c63f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c644  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c649  mov     [rsp+280h+var_250], 0
0x18000c652  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c658  xor     r8d, r8d; dwFlags
0x18000c65b  lea     rdx, [rsp+280h+Name]; lpName
0x18000c660  xor     ecx, ecx; lpMutexAttributes
0x18000c662  call    cs:__imp_CreateMutexExW
0x18000c668  mov     rdx, rax
0x18000c66b  lea     rcx, [rsp+280h+var_250]
0x18000c670  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c675  mov     rbx, [rsp+280h+var_250]
0x18000c67a  test    rbx, rbx
0x18000c67d  jnz     short loc_18000C68A
0x18000c67f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c684  nop
0x18000c685  jmp     loc_18000C75A
0x18000c68a  lea     rdx, [rsp+280h+var_248]
0x18000c68f  lea     rcx, [rsp+280h+var_250]
0x18000c694  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c699  nop
0x18000c69a  mov     [rsp+280h+var_240], 0
0x18000c6a3  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x18000c6a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c6ad  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c6b2  mov     edi, eax
0x18000c6b4  test    eax, eax
0x18000c6b6  jns     short loc_18000C726
0x18000c6b8  mov     rcx, [rbp+188h]; this
0x18000c6bf  mov     r9d, eax; char *
0x18000c6c2  lea     r8, aWil; "wil"
0x18000c6c9  mov     edx, 66h ; 'f'; void *
0x18000c6ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6d3  mov     rcx, [rbp+188h]; this
0x18000c6da  mov     r9d, edi; char *
0x18000c6dd  lea     r8, aWil; "wil"
0x18000c6e4  mov     edx, 6Fh ; 'o'; void *
0x18000c6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6ee  mov     rcx, [rbp+188h]; this
0x18000c6f5  mov     r9d, edi; char *
0x18000c6f8  lea     r8, aWil; "wil"
0x18000c6ff  mov     edx, 12Eh; void *
0x18000c704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c709  nop
0x18000c70a  mov     rcx, [rsp+280h+var_248]; this
0x18000c70f  test    rcx, rcx
0x18000c712  jz      short loc_18000C71A
0x18000c714  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000c719  nop
0x18000c71a  mov     rcx, rbx; this
0x18000c71d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000c722  mov     eax, edi
0x18000c724  jmp     short loc_18000C75A
0x18000c726  mov     rax, [rsp+280h+var_240]
0x18000c72b  lea     rcx, ds:0[rax*4]
0x18000c733  test    rcx, rcx
0x18000c736  jz      short loc_18000C77C
0x18000c738  mov     [rsi], rcx
0x18000c73b  mov     eax, [rcx]
0x18000c73d  inc     eax
0x18000c73f  mov     [rcx], eax
0x18000c741  lea     rcx, [rsp+280h+var_248]
0x18000c746  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c74b  nop
0x18000c74c  xor     ebx, ebx
0x18000c74e  lea     rcx, [rsp+280h+var_250]
0x18000c753  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c758  mov     eax, ebx
0x18000c75a  mov     rcx, [rbp+180h+var_20]
0x18000c761  xor     rcx, rsp; StackCookie
0x18000c764  call    __security_check_cookie
0x18000c769  mov     rbx, [rsp+280h+arg_10]
0x18000c771  add     rsp, 270h
0x18000c778  pop     rdi
0x18000c779  pop     rsi
0x18000c77a  pop     rbp
0x18000c77b  retn
0x18000c77c  mov     r8, rsi
0x18000c77f  lea     rdx, [rsp+280h+var_250]
0x18000c784  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c789  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c78e  mov     ebx, eax
0x18000c790  test    eax, eax
0x18000c792  jns     short loc_18000C741
0x18000c794  mov     rcx, [rbp+188h]; this
0x18000c79b  mov     r9d, eax; char *
0x18000c79e  lea     r8, aWil; "wil"
0x18000c7a5  mov     edx, 137h; void *
0x18000c7aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7af  nop
0x18000c7b0  lea     rcx, [rsp+280h+var_248]
0x18000c7b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c7ba  nop
0x18000c7bb  jmp     short loc_18000C74E
```
