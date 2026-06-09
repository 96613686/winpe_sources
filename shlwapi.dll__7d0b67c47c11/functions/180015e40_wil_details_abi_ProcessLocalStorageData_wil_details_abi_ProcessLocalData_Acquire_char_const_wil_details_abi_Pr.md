# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180015e40`
- end: `0x180015fa6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180016878`

## callees

- `0x180004e64`
- `0x180010740`
- `0x180010a18`
- `0x1800110d8`
- `0x180012550`
- `0x180015de8`
- `0x180015e04`
- `0x180015e40`
- `0x1800173f4`
- `0x1800177f4`
- `0x1800178a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015ebd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180015ebd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015e78`

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
0x180015e40  mov     [rsp-8+arg_10], rbx
0x180015e45  mov     [rsp-8+arg_18], rdi
0x180015e4a  push    rbp
0x180015e4b  lea     rbp, [rsp-170h]
0x180015e53  sub     rsp, 270h
0x180015e5a  mov     rax, cs:__security_cookie
0x180015e61  xor     rax, rsp
0x180015e64  mov     [rbp+170h+var_10], rax
0x180015e6b  mov     rdi, rdx
0x180015e6e  mov     qword ptr [rdx], 0
0x180015e75  mov     rbx, rcx
0x180015e78  call    cs:__imp_GetCurrentProcessId
0x180015e7e  mov     [rsp+270h+var_248], rbx
0x180015e83  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180015e8a  mov     r9d, eax
0x180015e8d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180015e95  mov     edx, 104h; unsigned __int64
0x180015e9a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180015e9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015ea4  mov     r9d, 1F0001h; dwDesiredAccess
0x180015eaa  mov     [rsp+270h+var_240], 0
0x180015eb3  xor     r8d, r8d; dwFlags
0x180015eb6  lea     rdx, [rsp+270h+Name]; lpName
0x180015ebb  xor     ecx, ecx; lpMutexAttributes
0x180015ebd  call    cs:__imp_CreateMutexExW
0x180015ec3  mov     rdx, rax
0x180015ec6  lea     rcx, [rsp+270h+var_240]
0x180015ecb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015ed0  cmp     [rsp+270h+var_240], 0
0x180015ed6  jnz     short loc_180015EE1
0x180015ed8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015edd  mov     ebx, eax
0x180015edf  jmp     short loc_180015F54
0x180015ee1  lea     rdx, [rsp+270h+var_238]
0x180015ee6  lea     rcx, [rsp+270h+var_240]
0x180015eeb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180015ef0  lea     rdx, [rsp+270h+var_230]; void **
0x180015ef5  mov     [rsp+270h+var_230], 0
0x180015efe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180015f03  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180015f08  mov     ebx, eax
0x180015f0a  test    eax, eax
0x180015f0c  jns     short loc_180015F35
0x180015f0e  mov     edx, 12Eh; void *
0x180015f13  mov     rcx, [rbp+178h]; this
0x180015f1a  lea     r8, aWil; "wil"
0x180015f21  mov     r9d, eax; char *
0x180015f24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f29  lea     rcx, [rsp+270h+var_238]
0x180015f2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015f33  jmp     short loc_180015F54
0x180015f35  mov     rcx, [rsp+270h+var_230]
0x180015f3a  test    rcx, rcx
0x180015f3d  jz      short loc_180015F84
0x180015f3f  mov     [rdi], rcx
0x180015f42  mov     eax, [rcx]
0x180015f44  inc     eax
0x180015f46  mov     [rcx], eax
0x180015f48  lea     rcx, [rsp+270h+var_238]
0x180015f4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015f52  xor     ebx, ebx
0x180015f54  lea     rcx, [rsp+270h+var_240]
0x180015f59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015f5e  mov     eax, ebx
0x180015f60  mov     rcx, [rbp+170h+var_10]
0x180015f67  xor     rcx, rsp; StackCookie
0x180015f6a  call    __security_check_cookie
0x180015f6f  lea     r11, [rsp+270h+var_s0]
0x180015f77  mov     rbx, [r11+20h]
0x180015f7b  mov     rdi, [r11+28h]
0x180015f7f  mov     rsp, r11
0x180015f82  pop     rbp
0x180015f83  retn
0x180015f84  mov     r8, rdi
0x180015f87  lea     rdx, [rsp+270h+var_240]
0x180015f8c  lea     rcx, [rsp+270h+Name]
0x180015f91  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180015f96  mov     ebx, eax
0x180015f98  test    eax, eax
0x180015f9a  jns     short loc_180015F48
0x180015f9c  mov     edx, 137h
0x180015fa1  jmp     loc_180015F13
```
