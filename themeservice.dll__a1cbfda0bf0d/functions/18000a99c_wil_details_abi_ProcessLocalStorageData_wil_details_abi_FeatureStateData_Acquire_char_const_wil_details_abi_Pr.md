# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a99c`
- end: `0x18000aafb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000abfc`

## callees

- `0x180002ae0`
- `0x180006aa4`
- `0x180008730`
- `0x18000874c`
- `0x180009b20`
- `0x180009f08`
- `0x18000a288`
- `0x18000a334`
- `0x18000a99c`
- `0x18000b6cc`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000aa19`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000aa19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a9d4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000a99c  mov     [rsp-8+arg_10], rbx
0x18000a9a1  mov     [rsp-8+arg_18], rdi
0x18000a9a6  push    rbp
0x18000a9a7  lea     rbp, [rsp-170h]
0x18000a9af  sub     rsp, 270h
0x18000a9b6  mov     rax, cs:__security_cookie
0x18000a9bd  xor     rax, rsp
0x18000a9c0  mov     [rbp+170h+var_10], rax
0x18000a9c7  mov     rdi, rdx
0x18000a9ca  mov     qword ptr [rdx], 0
0x18000a9d1  mov     rbx, rcx
0x18000a9d4  call    cs:__imp_GetCurrentProcessId
0x18000a9da  mov     [rsp+270h+var_248], rbx
0x18000a9df  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a9e6  mov     r9d, eax
0x18000a9e9  mov     [rsp+270h+var_250], 130h; int
0x18000a9f1  mov     edx, 104h; unsigned __int64
0x18000a9f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a9fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000aa00  mov     r9d, 1F0001h; dwDesiredAccess
0x18000aa06  mov     [rsp+270h+var_240], 0
0x18000aa0f  xor     r8d, r8d; dwFlags
0x18000aa12  lea     rdx, [rsp+270h+Name]; lpName
0x18000aa17  xor     ecx, ecx; lpMutexAttributes
0x18000aa19  call    cs:__imp_CreateMutexExW
0x18000aa1f  mov     rdx, rax
0x18000aa22  lea     rcx, [rsp+270h+var_240]
0x18000aa27  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000aa2c  cmp     [rsp+270h+var_240], 0
0x18000aa32  jnz     short loc_18000AA3D
0x18000aa34  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000aa39  mov     ebx, eax
0x18000aa3b  jmp     short loc_18000AAA9
0x18000aa3d  lea     rdx, [rsp+270h+var_238]
0x18000aa42  lea     rcx, [rsp+270h+var_240]
0x18000aa47  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000aa4c  lea     rdx, [rsp+270h+var_230]; void **
0x18000aa51  mov     [rsp+270h+var_230], 0
0x18000aa5a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aa5f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000aa64  mov     ebx, eax
0x18000aa66  test    eax, eax
0x18000aa68  jns     short loc_18000AA8A
0x18000aa6a  mov     edx, 12Eh; void *
0x18000aa6f  mov     rcx, [rbp+178h]; this
0x18000aa76  mov     r9d, eax; char *
0x18000aa79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa7e  lea     rcx, [rsp+270h+var_238]
0x18000aa83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aa88  jmp     short loc_18000AAA9
0x18000aa8a  mov     rcx, [rsp+270h+var_230]
0x18000aa8f  test    rcx, rcx
0x18000aa92  jz      short loc_18000AAD9
0x18000aa94  mov     [rdi], rcx
0x18000aa97  mov     eax, [rcx]
0x18000aa99  inc     eax
0x18000aa9b  mov     [rcx], eax
0x18000aa9d  lea     rcx, [rsp+270h+var_238]
0x18000aaa2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aaa7  xor     ebx, ebx
0x18000aaa9  lea     rcx, [rsp+270h+var_240]
0x18000aaae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aab3  mov     eax, ebx
0x18000aab5  mov     rcx, [rbp+170h+var_10]
0x18000aabc  xor     rcx, rsp; StackCookie
0x18000aabf  call    __security_check_cookie
0x18000aac4  lea     r11, [rsp+270h+var_s0]
0x18000aacc  mov     rbx, [r11+20h]
0x18000aad0  mov     rdi, [r11+28h]
0x18000aad4  mov     rsp, r11
0x18000aad7  pop     rbp
0x18000aad8  retn
0x18000aad9  mov     r8, rdi
0x18000aadc  lea     rdx, [rsp+270h+var_240]
0x18000aae1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aae6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000aaeb  mov     ebx, eax
0x18000aaed  test    eax, eax
0x18000aaef  jns     short loc_18000AA9D
0x18000aaf1  mov     edx, 137h
0x18000aaf6  jmp     loc_18000AA6F
```
