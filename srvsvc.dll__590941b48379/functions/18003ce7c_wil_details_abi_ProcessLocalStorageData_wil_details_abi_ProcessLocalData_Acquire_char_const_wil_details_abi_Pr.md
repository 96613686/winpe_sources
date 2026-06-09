# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003ce7c`
- end: `0x18003cfdb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003dd7c`

## callees

- `0x18001deb0`
- `0x18003cbc4`
- `0x18003cbe0`
- `0x18003ce7c`
- `0x18003dba8`
- `0x18003e900`
- `0x18003faa4`
- `0x180040000`
- `0x180040330`
- `0x180040a04`
- `0x180040ce8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ceb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ceb4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003cef9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003cef9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18003ce7c  mov     [rsp-8+arg_10], rbx
0x18003ce81  mov     [rsp-8+arg_18], rdi
0x18003ce86  push    rbp
0x18003ce87  lea     rbp, [rsp-170h]
0x18003ce8f  sub     rsp, 270h
0x18003ce96  mov     rax, cs:__security_cookie
0x18003ce9d  xor     rax, rsp
0x18003cea0  mov     [rbp+170h+var_10], rax
0x18003cea7  mov     rdi, rdx
0x18003ceaa  mov     qword ptr [rdx], 0
0x18003ceb1  mov     rbx, rcx
0x18003ceb4  call    cs:__imp_GetCurrentProcessId
0x18003ceba  mov     [rsp+270h+var_248], rbx
0x18003cebf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003cec6  mov     r9d, eax
0x18003cec9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003ced1  mov     edx, 104h; unsigned __int64
0x18003ced6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003cedb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003cee0  mov     r9d, 1F0001h; dwDesiredAccess
0x18003cee6  mov     [rsp+270h+var_240], 0
0x18003ceef  xor     r8d, r8d; dwFlags
0x18003cef2  lea     rdx, [rsp+270h+Name]; lpName
0x18003cef7  xor     ecx, ecx; lpMutexAttributes
0x18003cef9  call    cs:__imp_CreateMutexExW
0x18003ceff  mov     rdx, rax
0x18003cf02  lea     rcx, [rsp+270h+var_240]
0x18003cf07  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003cf0c  cmp     [rsp+270h+var_240], 0
0x18003cf12  jnz     short loc_18003CF1D
0x18003cf14  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003cf19  mov     ebx, eax
0x18003cf1b  jmp     short loc_18003CF89
0x18003cf1d  lea     rdx, [rsp+270h+var_238]
0x18003cf22  lea     rcx, [rsp+270h+var_240]
0x18003cf27  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003cf2c  lea     rdx, [rsp+270h+var_230]; void **
0x18003cf31  mov     [rsp+270h+var_230], 0
0x18003cf3a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003cf3f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003cf44  mov     ebx, eax
0x18003cf46  test    eax, eax
0x18003cf48  jns     short loc_18003CF6A
0x18003cf4a  mov     edx, 12Eh; void *
0x18003cf4f  mov     rcx, [rbp+178h]; this
0x18003cf56  mov     r9d, eax; char *
0x18003cf59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cf5e  lea     rcx, [rsp+270h+var_238]
0x18003cf63  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003cf68  jmp     short loc_18003CF89
0x18003cf6a  mov     rcx, [rsp+270h+var_230]
0x18003cf6f  test    rcx, rcx
0x18003cf72  jz      short loc_18003CFB9
0x18003cf74  mov     [rdi], rcx
0x18003cf77  mov     eax, [rcx]
0x18003cf79  inc     eax
0x18003cf7b  mov     [rcx], eax
0x18003cf7d  lea     rcx, [rsp+270h+var_238]
0x18003cf82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003cf87  xor     ebx, ebx
0x18003cf89  lea     rcx, [rsp+270h+var_240]
0x18003cf8e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003cf93  mov     eax, ebx
0x18003cf95  mov     rcx, [rbp+170h+var_10]
0x18003cf9c  xor     rcx, rsp; StackCookie
0x18003cf9f  call    __security_check_cookie
0x18003cfa4  lea     r11, [rsp+270h+var_s0]
0x18003cfac  mov     rbx, [r11+20h]
0x18003cfb0  mov     rdi, [r11+28h]
0x18003cfb4  mov     rsp, r11
0x18003cfb7  pop     rbp
0x18003cfb8  retn
0x18003cfb9  mov     r8, rdi
0x18003cfbc  lea     rdx, [rsp+270h+var_240]
0x18003cfc1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003cfc6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003cfcb  mov     ebx, eax
0x18003cfcd  test    eax, eax
0x18003cfcf  jns     short loc_18003CF7D
0x18003cfd1  mov     edx, 137h
0x18003cfd6  jmp     loc_18003CF4F
```
