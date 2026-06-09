# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180026b64`
- end: `0x180026cca`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002d04c`

## callees

- `0x180016ae8`
- `0x1800205e4`
- `0x1800228ec`
- `0x180026b64`
- `0x180026cd0`
- `0x180026cec`
- `0x180026d88`
- `0x180029408`
- `0x1800296d4`
- `0x18002e3b0`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026be1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026be1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026b9c`

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
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x180026b64  mov     [rsp-8+arg_10], rbx
0x180026b69  mov     [rsp-8+arg_18], rdi
0x180026b6e  push    rbp
0x180026b6f  lea     rbp, [rsp-170h]
0x180026b77  sub     rsp, 270h
0x180026b7e  mov     rax, cs:__security_cookie
0x180026b85  xor     rax, rsp
0x180026b88  mov     [rbp+170h+var_10], rax
0x180026b8f  mov     rdi, rdx
0x180026b92  mov     qword ptr [rdx], 0
0x180026b99  mov     rbx, rcx
0x180026b9c  call    cs:__imp_GetCurrentProcessId
0x180026ba2  mov     [rsp+270h+var_248], rbx
0x180026ba7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180026bae  mov     r9d, eax
0x180026bb1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180026bb9  mov     edx, 104h; unsigned __int64
0x180026bbe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026bc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026bc8  mov     r9d, 1F0001h; dwDesiredAccess
0x180026bce  mov     [rsp+270h+var_240], 0
0x180026bd7  xor     r8d, r8d; dwFlags
0x180026bda  lea     rdx, [rsp+270h+Name]; lpName
0x180026bdf  xor     ecx, ecx; lpMutexAttributes
0x180026be1  call    cs:__imp_CreateMutexExW
0x180026be7  mov     rdx, rax
0x180026bea  lea     rcx, [rsp+270h+var_240]
0x180026bef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180026bf4  cmp     [rsp+270h+var_240], 0
0x180026bfa  jnz     short loc_180026C05
0x180026bfc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180026c01  mov     ebx, eax
0x180026c03  jmp     short loc_180026C78
0x180026c05  lea     rdx, [rsp+270h+var_238]
0x180026c0a  lea     rcx, [rsp+270h+var_240]
0x180026c0f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180026c14  lea     rdx, [rsp+270h+var_230]; void **
0x180026c19  mov     [rsp+270h+var_230], 0
0x180026c22  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180026c27  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180026c2c  mov     ebx, eax
0x180026c2e  test    eax, eax
0x180026c30  jns     short loc_180026C59
0x180026c32  mov     edx, 12Eh; void *
0x180026c37  mov     rcx, [rbp+178h]; this
0x180026c3e  lea     r8, aWil; "wil"
0x180026c45  mov     r9d, eax; char *
0x180026c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c4d  lea     rcx, [rsp+270h+var_238]
0x180026c52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c57  jmp     short loc_180026C78
0x180026c59  mov     rcx, [rsp+270h+var_230]
0x180026c5e  test    rcx, rcx
0x180026c61  jz      short loc_180026CA8
0x180026c63  mov     [rdi], rcx
0x180026c66  mov     eax, [rcx]
0x180026c68  inc     eax
0x180026c6a  mov     [rcx], eax
0x180026c6c  lea     rcx, [rsp+270h+var_238]
0x180026c71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c76  xor     ebx, ebx
0x180026c78  lea     rcx, [rsp+270h+var_240]
0x180026c7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026c82  mov     eax, ebx
0x180026c84  mov     rcx, [rbp+170h+var_10]
0x180026c8b  xor     rcx, rsp; StackCookie
0x180026c8e  call    __security_check_cookie
0x180026c93  lea     r11, [rsp+270h+var_s0]
0x180026c9b  mov     rbx, [r11+20h]
0x180026c9f  mov     rdi, [r11+28h]
0x180026ca3  mov     rsp, r11
0x180026ca6  pop     rbp
0x180026ca7  retn
0x180026ca8  mov     r8, rdi
0x180026cab  lea     rdx, [rsp+270h+var_240]
0x180026cb0  lea     rcx, [rsp+270h+Name]
0x180026cb5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180026cba  mov     ebx, eax
0x180026cbc  test    eax, eax
0x180026cbe  jns     short loc_180026C6C
0x180026cc0  mov     edx, 137h
0x180026cc5  jmp     loc_180026C37
```
