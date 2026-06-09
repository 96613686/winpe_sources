# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800362a8`
- end: `0x180036414`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800366c8`

## callees

- `0x18003339c`
- `0x1800339f8`
- `0x180034510`
- `0x180035f54`
- `0x180035f74`
- `0x1800362a8`
- `0x180037988`
- `0x18003860c`
- `0x180038f0c`
- `0x180039674`
- `0x1800397e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003632b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003632b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800362e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800362e0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800362a8  mov     [rsp-8+arg_10], rbx
0x1800362ad  mov     [rsp-8+arg_18], rdi
0x1800362b2  push    rbp
0x1800362b3  lea     rbp, [rsp-170h]
0x1800362bb  sub     rsp, 270h
0x1800362c2  mov     rax, cs:__security_cookie
0x1800362c9  xor     rax, rsp
0x1800362cc  mov     [rbp+170h+var_10], rax
0x1800362d3  mov     rdi, rdx
0x1800362d6  mov     qword ptr [rdx], 0
0x1800362dd  mov     rbx, rcx
0x1800362e0  call    cs:__imp_GetCurrentProcessId
0x1800362e7  nop     dword ptr [rax+rax+00h]
0x1800362ec  mov     [rsp+270h+var_248], rbx
0x1800362f1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800362f8  mov     r9d, eax
0x1800362fb  mov     [rsp+270h+var_250], 130h; int
0x180036303  mov     edx, 104h; cchDest
0x180036308  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003630d  call    StringCchPrintfW
0x180036312  mov     r9d, 1F0001h; dwDesiredAccess
0x180036318  mov     [rsp+270h+var_240], 0
0x180036321  xor     r8d, r8d; dwFlags
0x180036324  lea     rdx, [rsp+270h+pszDest]; lpName
0x180036329  xor     ecx, ecx; lpMutexAttributes
0x18003632b  call    cs:__imp_CreateMutexExW
0x180036332  nop     dword ptr [rax+rax+00h]
0x180036337  mov     rdx, rax
0x18003633a  lea     rcx, [rsp+270h+var_240]
0x18003633f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180036344  cmp     [rsp+270h+var_240], 0
0x18003634a  jnz     short loc_180036355
0x18003634c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180036351  mov     ebx, eax
0x180036353  jmp     short loc_1800363C1
0x180036355  lea     rdx, [rsp+270h+var_238]
0x18003635a  lea     rcx, [rsp+270h+var_240]
0x18003635f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180036364  lea     rdx, [rsp+270h+var_230]; void **
0x180036369  mov     [rsp+270h+var_230], 0
0x180036372  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180036377  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003637c  mov     ebx, eax
0x18003637e  test    eax, eax
0x180036380  jns     short loc_1800363A2
0x180036382  mov     edx, 12Eh; void *
0x180036387  mov     rcx, [rbp+178h]; this
0x18003638e  mov     r9d, eax; char *
0x180036391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036396  lea     rcx, [rsp+270h+var_238]
0x18003639b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800363a0  jmp     short loc_1800363C1
0x1800363a2  mov     rcx, [rsp+270h+var_230]
0x1800363a7  test    rcx, rcx
0x1800363aa  jz      short loc_1800363F2
0x1800363ac  mov     [rdi], rcx
0x1800363af  mov     eax, [rcx]
0x1800363b1  inc     eax
0x1800363b3  mov     [rcx], eax
0x1800363b5  lea     rcx, [rsp+270h+var_238]
0x1800363ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800363bf  xor     ebx, ebx
0x1800363c1  lea     rcx, [rsp+270h+var_240]
0x1800363c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800363cb  mov     eax, ebx
0x1800363cd  mov     rcx, [rbp+170h+var_10]
0x1800363d4  xor     rcx, rsp; StackCookie
0x1800363d7  call    __security_check_cookie
0x1800363dc  lea     r11, [rsp+270h+var_s0]
0x1800363e4  mov     rbx, [r11+20h]
0x1800363e8  mov     rdi, [r11+28h]
0x1800363ec  mov     rsp, r11
0x1800363ef  pop     rbp
0x1800363f0  retn
0x1800363f2  mov     r8, rdi
0x1800363f5  lea     rdx, [rsp+270h+var_240]
0x1800363fa  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800363ff  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180036404  mov     ebx, eax
0x180036406  test    eax, eax
0x180036408  jns     short loc_1800363B5
0x18003640a  mov     edx, 137h
0x18003640f  jmp     loc_180036387
```
