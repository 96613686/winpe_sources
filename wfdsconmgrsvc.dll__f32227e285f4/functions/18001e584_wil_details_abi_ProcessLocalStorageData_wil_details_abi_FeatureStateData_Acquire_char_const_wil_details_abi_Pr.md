# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001e584`
- end: `0x18001e6e3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001f2f4`

## callees

- `0x180002600`
- `0x18001e080`
- `0x18001e09c`
- `0x18001e584`
- `0x18001f138`
- `0x18001ffdc`
- `0x18002102c`
- `0x18002179c`
- `0x180021b78`
- `0x180022394`
- `0x180022658`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e5bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e5bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e601`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001e601`

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
0x18001e584  mov     [rsp-8+arg_10], rbx
0x18001e589  mov     [rsp-8+arg_18], rdi
0x18001e58e  push    rbp
0x18001e58f  lea     rbp, [rsp-170h]
0x18001e597  sub     rsp, 270h
0x18001e59e  mov     rax, cs:__security_cookie
0x18001e5a5  xor     rax, rsp
0x18001e5a8  mov     [rbp+170h+var_10], rax
0x18001e5af  mov     rdi, rdx
0x18001e5b2  mov     qword ptr [rdx], 0
0x18001e5b9  mov     rbx, rcx
0x18001e5bc  call    cs:__imp_GetCurrentProcessId
0x18001e5c2  mov     [rsp+270h+var_248], rbx
0x18001e5c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001e5ce  mov     r9d, eax
0x18001e5d1  mov     [rsp+270h+var_250], 130h; int
0x18001e5d9  mov     edx, 104h; unsigned __int64
0x18001e5de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e5e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e5e8  mov     r9d, 1F0001h; dwDesiredAccess
0x18001e5ee  mov     [rsp+270h+var_240], 0
0x18001e5f7  xor     r8d, r8d; dwFlags
0x18001e5fa  lea     rdx, [rsp+270h+Name]; lpName
0x18001e5ff  xor     ecx, ecx; lpMutexAttributes
0x18001e601  call    cs:__imp_CreateMutexExW
0x18001e607  mov     rdx, rax
0x18001e60a  lea     rcx, [rsp+270h+var_240]
0x18001e60f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001e614  cmp     [rsp+270h+var_240], 0
0x18001e61a  jnz     short loc_18001E625
0x18001e61c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e621  mov     ebx, eax
0x18001e623  jmp     short loc_18001E691
0x18001e625  lea     rdx, [rsp+270h+var_238]
0x18001e62a  lea     rcx, [rsp+270h+var_240]
0x18001e62f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001e634  lea     rdx, [rsp+270h+var_230]; void **
0x18001e639  mov     [rsp+270h+var_230], 0
0x18001e642  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e647  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001e64c  mov     ebx, eax
0x18001e64e  test    eax, eax
0x18001e650  jns     short loc_18001E672
0x18001e652  mov     edx, 12Eh; void *
0x18001e657  mov     rcx, [rbp+178h]; this
0x18001e65e  mov     r9d, eax; char *
0x18001e661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e666  lea     rcx, [rsp+270h+var_238]
0x18001e66b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e670  jmp     short loc_18001E691
0x18001e672  mov     rcx, [rsp+270h+var_230]
0x18001e677  test    rcx, rcx
0x18001e67a  jz      short loc_18001E6C1
0x18001e67c  mov     [rdi], rcx
0x18001e67f  mov     eax, [rcx]
0x18001e681  inc     eax
0x18001e683  mov     [rcx], eax
0x18001e685  lea     rcx, [rsp+270h+var_238]
0x18001e68a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e68f  xor     ebx, ebx
0x18001e691  lea     rcx, [rsp+270h+var_240]
0x18001e696  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001e69b  mov     eax, ebx
0x18001e69d  mov     rcx, [rbp+170h+var_10]
0x18001e6a4  xor     rcx, rsp; StackCookie
0x18001e6a7  call    __security_check_cookie
0x18001e6ac  lea     r11, [rsp+270h+var_s0]
0x18001e6b4  mov     rbx, [r11+20h]
0x18001e6b8  mov     rdi, [r11+28h]
0x18001e6bc  mov     rsp, r11
0x18001e6bf  pop     rbp
0x18001e6c0  retn
0x18001e6c1  mov     r8, rdi
0x18001e6c4  lea     rdx, [rsp+270h+var_240]
0x18001e6c9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001e6ce  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001e6d3  mov     ebx, eax
0x18001e6d5  test    eax, eax
0x18001e6d7  jns     short loc_18001E685
0x18001e6d9  mov     edx, 137h
0x18001e6de  jmp     loc_18001E657
```
