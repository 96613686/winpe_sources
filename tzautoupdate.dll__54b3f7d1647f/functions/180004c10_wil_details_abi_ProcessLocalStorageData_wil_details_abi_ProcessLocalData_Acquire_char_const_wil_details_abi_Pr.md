# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004c10`
- end: `0x180004d76`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006434`

## callees

- `0x1800046b8`
- `0x1800046d4`
- `0x180004c10`
- `0x180006108`
- `0x180006eec`
- `0x18000885c`
- `0x180008ff0`
- `0x1800096b4`
- `0x18000af9c`
- `0x18000b734`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c8d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004c48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004c48`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004c10  mov     [rsp-8+arg_10], rbx
0x180004c15  mov     [rsp-8+arg_18], rdi
0x180004c1a  push    rbp
0x180004c1b  lea     rbp, [rsp-170h]
0x180004c23  sub     rsp, 270h
0x180004c2a  mov     rax, cs:__security_cookie
0x180004c31  xor     rax, rsp
0x180004c34  mov     [rbp+170h+var_10], rax
0x180004c3b  mov     rdi, rdx
0x180004c3e  mov     qword ptr [rdx], 0
0x180004c45  mov     rbx, rcx
0x180004c48  call    cs:__imp_GetCurrentProcessId
0x180004c4e  mov     [rsp+270h+var_248], rbx
0x180004c53  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004c5a  mov     r9d, eax
0x180004c5d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004c65  mov     edx, 104h; unsigned __int64
0x180004c6a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004c6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004c74  mov     r9d, 1F0001h; dwDesiredAccess
0x180004c7a  mov     [rsp+270h+var_240], 0
0x180004c83  xor     r8d, r8d; dwFlags
0x180004c86  lea     rdx, [rsp+270h+Name]; lpName
0x180004c8b  xor     ecx, ecx; lpMutexAttributes
0x180004c8d  call    cs:__imp_CreateMutexExW
0x180004c93  mov     rdx, rax
0x180004c96  lea     rcx, [rsp+270h+var_240]
0x180004c9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004ca0  cmp     [rsp+270h+var_240], 0
0x180004ca6  jnz     short loc_180004CB1
0x180004ca8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004cad  mov     ebx, eax
0x180004caf  jmp     short loc_180004D24
0x180004cb1  lea     rdx, [rsp+270h+var_238]
0x180004cb6  lea     rcx, [rsp+270h+var_240]
0x180004cbb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004cc0  lea     rdx, [rsp+270h+var_230]; void **
0x180004cc5  mov     [rsp+270h+var_230], 0
0x180004cce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004cd3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004cd8  mov     ebx, eax
0x180004cda  test    eax, eax
0x180004cdc  jns     short loc_180004D05
0x180004cde  mov     edx, 12Eh; void *
0x180004ce3  mov     rcx, [rbp+178h]; this
0x180004cea  lea     r8, aWil; "wil"
0x180004cf1  mov     r9d, eax; char *
0x180004cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004cf9  lea     rcx, [rsp+270h+var_238]
0x180004cfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004d03  jmp     short loc_180004D24
0x180004d05  mov     rcx, [rsp+270h+var_230]
0x180004d0a  test    rcx, rcx
0x180004d0d  jz      short loc_180004D54
0x180004d0f  mov     [rdi], rcx
0x180004d12  mov     eax, [rcx]
0x180004d14  inc     eax
0x180004d16  mov     [rcx], eax
0x180004d18  lea     rcx, [rsp+270h+var_238]
0x180004d1d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004d22  xor     ebx, ebx
0x180004d24  lea     rcx, [rsp+270h+var_240]
0x180004d29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004d2e  mov     eax, ebx
0x180004d30  mov     rcx, [rbp+170h+var_10]
0x180004d37  xor     rcx, rsp; StackCookie
0x180004d3a  call    __security_check_cookie
0x180004d3f  lea     r11, [rsp+270h+var_s0]
0x180004d47  mov     rbx, [r11+20h]
0x180004d4b  mov     rdi, [r11+28h]
0x180004d4f  mov     rsp, r11
0x180004d52  pop     rbp
0x180004d53  retn
0x180004d54  mov     r8, rdi
0x180004d57  lea     rdx, [rsp+270h+var_240]
0x180004d5c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d61  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004d66  mov     ebx, eax
0x180004d68  test    eax, eax
0x180004d6a  jns     short loc_180004D18
0x180004d6c  mov     edx, 137h
0x180004d71  jmp     loc_180004CE3
```
