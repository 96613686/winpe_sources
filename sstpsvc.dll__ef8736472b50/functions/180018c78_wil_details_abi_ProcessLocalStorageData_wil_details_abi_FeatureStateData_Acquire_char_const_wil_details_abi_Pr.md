# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180018c78`
- end: `0x180018de4`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019ba0`

## callees

- `0x1800177cc`
- `0x180018828`
- `0x180018848`
- `0x180018c78`
- `0x180019950`
- `0x18001a74c`
- `0x18001b87c`
- `0x18001c070`
- `0x18001c794`
- `0x18001ca0c`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018cfb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180018cfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018cb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018cb0`

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
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180018c78  mov     [rsp-8+arg_10], rbx
0x180018c7d  mov     [rsp-8+arg_18], rdi
0x180018c82  push    rbp
0x180018c83  lea     rbp, [rsp-170h]
0x180018c8b  sub     rsp, 270h
0x180018c92  mov     rax, cs:__security_cookie
0x180018c99  xor     rax, rsp
0x180018c9c  mov     [rbp+170h+var_10], rax
0x180018ca3  mov     rdi, rdx
0x180018ca6  mov     qword ptr [rdx], 0
0x180018cad  mov     rbx, rcx
0x180018cb0  call    cs:__imp_GetCurrentProcessId
0x180018cb7  nop     dword ptr [rax+rax+00h]
0x180018cbc  mov     [rsp+270h+var_248], rbx
0x180018cc1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180018cc8  mov     r9d, eax
0x180018ccb  mov     [rsp+270h+var_250], 130h; int
0x180018cd3  mov     edx, 104h; unsigned __int64
0x180018cd8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018cdd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018ce2  mov     r9d, 1F0001h; dwDesiredAccess
0x180018ce8  mov     [rsp+270h+var_240], 0
0x180018cf1  xor     r8d, r8d; dwFlags
0x180018cf4  lea     rdx, [rsp+270h+Name]; lpName
0x180018cf9  xor     ecx, ecx; lpMutexAttributes
0x180018cfb  call    cs:__imp_CreateMutexExW
0x180018d02  nop     dword ptr [rax+rax+00h]
0x180018d07  mov     rdx, rax
0x180018d0a  lea     rcx, [rsp+270h+var_240]
0x180018d0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180018d14  cmp     [rsp+270h+var_240], 0
0x180018d1a  jnz     short loc_180018D25
0x180018d1c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018d21  mov     ebx, eax
0x180018d23  jmp     short loc_180018D91
0x180018d25  lea     rdx, [rsp+270h+var_238]
0x180018d2a  lea     rcx, [rsp+270h+var_240]
0x180018d2f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180018d34  lea     rdx, [rsp+270h+var_230]; void **
0x180018d39  mov     [rsp+270h+var_230], 0
0x180018d42  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018d47  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180018d4c  mov     ebx, eax
0x180018d4e  test    eax, eax
0x180018d50  jns     short loc_180018D72
0x180018d52  mov     edx, 12Eh; void *
0x180018d57  mov     rcx, [rbp+178h]; this
0x180018d5e  mov     r9d, eax; char *
0x180018d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d66  lea     rcx, [rsp+270h+var_238]
0x180018d6b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018d70  jmp     short loc_180018D91
0x180018d72  mov     rcx, [rsp+270h+var_230]
0x180018d77  test    rcx, rcx
0x180018d7a  jz      short loc_180018DC2
0x180018d7c  mov     [rdi], rcx
0x180018d7f  mov     eax, [rcx]
0x180018d81  inc     eax
0x180018d83  mov     [rcx], eax
0x180018d85  lea     rcx, [rsp+270h+var_238]
0x180018d8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018d8f  xor     ebx, ebx
0x180018d91  lea     rcx, [rsp+270h+var_240]
0x180018d96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018d9b  mov     eax, ebx
0x180018d9d  mov     rcx, [rbp+170h+var_10]
0x180018da4  xor     rcx, rsp; StackCookie
0x180018da7  call    __security_check_cookie
0x180018dac  lea     r11, [rsp+270h+var_s0]
0x180018db4  mov     rbx, [r11+20h]
0x180018db8  mov     rdi, [r11+28h]
0x180018dbc  mov     rsp, r11
0x180018dbf  pop     rbp
0x180018dc0  retn
0x180018dc2  mov     r8, rdi
0x180018dc5  lea     rdx, [rsp+270h+var_240]
0x180018dca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180018dcf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180018dd4  mov     ebx, eax
0x180018dd6  test    eax, eax
0x180018dd8  jns     short loc_180018D85
0x180018dda  mov     edx, 137h
0x180018ddf  jmp     loc_180018D57
```
