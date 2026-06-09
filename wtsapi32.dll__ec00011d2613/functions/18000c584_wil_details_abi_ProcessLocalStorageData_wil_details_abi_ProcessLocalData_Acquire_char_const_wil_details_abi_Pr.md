# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c584`
- end: `0x18000c72e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d0d8`

## callees

- `0x18000bf8c`
- `0x18000bfa8`
- `0x18000c584`
- `0x18000ce38`
- `0x18000d9d4`
- `0x18000dfb8`
- `0x18000e32c`
- `0x18000e43c`
- `0x18000eb18`
- `0x18000ebc4`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c601`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c601`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000c584  mov     [rsp-8+arg_10], rbx
0x18000c589  mov     [rsp-8+arg_18], rdi
0x18000c58e  push    rbp
0x18000c58f  lea     rbp, [rsp-170h]
0x18000c597  sub     rsp, 270h
0x18000c59e  mov     rax, cs:__security_cookie
0x18000c5a5  xor     rax, rsp
0x18000c5a8  mov     [rbp+170h+var_10], rax
0x18000c5af  mov     rdi, rdx
0x18000c5b2  mov     qword ptr [rdx], 0
0x18000c5b9  mov     rbx, rcx
0x18000c5bc  call    cs:__imp_GetCurrentProcessId
0x18000c5c2  mov     [rsp+270h+var_248], rbx
0x18000c5c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c5ce  mov     r9d, eax
0x18000c5d1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000c5d9  mov     edx, 104h; unsigned __int64
0x18000c5de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c5e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c5e8  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c5ee  mov     [rsp+270h+var_240], 0
0x18000c5f7  xor     r8d, r8d; dwFlags
0x18000c5fa  lea     rdx, [rsp+270h+Name]; lpName
0x18000c5ff  xor     ecx, ecx; lpMutexAttributes
0x18000c601  call    cs:__imp_CreateMutexExW
0x18000c607  mov     rdx, rax
0x18000c60a  lea     rcx, [rsp+270h+var_240]
0x18000c60f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c614  cmp     [rsp+270h+var_240], 0
0x18000c61a  jnz     short loc_18000C628
0x18000c61c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c621  mov     ebx, eax
0x18000c623  jmp     loc_18000C6D9
0x18000c628  lea     rdx, [rsp+270h+var_238]
0x18000c62d  lea     rcx, [rsp+270h+var_240]
0x18000c632  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c637  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18000c63c  mov     [rsp+270h+var_230], 0
0x18000c645  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c64a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c64f  mov     ebx, eax
0x18000c651  test    eax, eax
0x18000c653  jns     short loc_18000C6B2
0x18000c655  mov     rcx, [rbp+178h]; this
0x18000c65c  lea     r8, aWil; "wil"
0x18000c663  mov     r9d, eax; char *
0x18000c666  mov     edx, 66h ; 'f'; void *
0x18000c66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c670  mov     rcx, [rbp+178h]; this
0x18000c677  lea     r8, aWil; "wil"
0x18000c67e  mov     r9d, ebx; char *
0x18000c681  mov     edx, 6Fh ; 'o'; void *
0x18000c686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c68b  mov     r9d, ebx; char *
0x18000c68e  mov     edx, 12Eh; void *
0x18000c693  mov     rcx, [rbp+178h]; this
0x18000c69a  lea     r8, aWil; "wil"
0x18000c6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6a6  lea     rcx, [rsp+270h+var_238]
0x18000c6ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6b0  jmp     short loc_18000C6D9
0x18000c6b2  mov     rax, [rsp+270h+var_230]
0x18000c6b7  lea     rcx, ds:0[rax*4]
0x18000c6bf  test    rcx, rcx
0x18000c6c2  jz      short loc_18000C709
0x18000c6c4  mov     [rdi], rcx
0x18000c6c7  mov     eax, [rcx]
0x18000c6c9  inc     eax
0x18000c6cb  mov     [rcx], eax
0x18000c6cd  lea     rcx, [rsp+270h+var_238]
0x18000c6d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6d7  xor     ebx, ebx
0x18000c6d9  lea     rcx, [rsp+270h+var_240]
0x18000c6de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6e3  mov     eax, ebx
0x18000c6e5  mov     rcx, [rbp+170h+var_10]
0x18000c6ec  xor     rcx, rsp; StackCookie
0x18000c6ef  call    __security_check_cookie
0x18000c6f4  lea     r11, [rsp+270h+var_s0]
0x18000c6fc  mov     rbx, [r11+20h]
0x18000c700  mov     rdi, [r11+28h]
0x18000c704  mov     rsp, r11
0x18000c707  pop     rbp
0x18000c708  retn
0x18000c709  mov     r8, rdi
0x18000c70c  lea     rdx, [rsp+270h+var_240]
0x18000c711  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c716  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c71b  mov     ebx, eax
0x18000c71d  test    eax, eax
0x18000c71f  jns     short loc_18000C6CD
0x18000c721  mov     r9d, eax
0x18000c724  mov     edx, 137h
0x18000c729  jmp     loc_18000C693
```
