# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002b860`
- end: `0x18002b9e9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033c6c`

## callees

- `0x18000c584`
- `0x18000c7c4`
- `0x18002b860`
- `0x18002ba20`
- `0x18002c00c`
- `0x18002c090`
- `0x18002c1d4`
- `0x18002c2f8`
- `0x18002d7bc`
- `0x1800342b8`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b8dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002b8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b898`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  _DWORD *v8; // rcx
  int v10; // eax
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
    if ( Pointer >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a2 = v13;
        ++*v8;
      }
      else
      {
        v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v10,
            120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18002b860  mov     [rsp-8+arg_10], rbx
0x18002b865  mov     [rsp-8+arg_18], rdi
0x18002b86a  push    rbp
0x18002b86b  lea     rbp, [rsp-170h]
0x18002b873  sub     rsp, 270h
0x18002b87a  mov     rax, cs:__security_cookie
0x18002b881  xor     rax, rsp
0x18002b884  mov     [rbp+170h+var_10], rax
0x18002b88b  mov     rdi, rdx
0x18002b88e  mov     rbx, rcx
0x18002b891  mov     qword ptr [rdx], 0
0x18002b898  call    cs:__imp_GetCurrentProcessId
0x18002b89e  mov     r9d, eax
0x18002b8a1  mov     [rsp+270h+var_248], rbx
0x18002b8a6  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002b8ae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002b8b5  mov     edx, 104h; unsigned __int64
0x18002b8ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b8bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b8c4  mov     [rsp+270h+var_240], 0
0x18002b8cd  mov     r9d, 1F0001h; dwDesiredAccess
0x18002b8d3  xor     r8d, r8d; dwFlags
0x18002b8d6  lea     rdx, [rsp+270h+Name]; lpName
0x18002b8db  xor     ecx, ecx; lpMutexAttributes
0x18002b8dd  call    cs:__imp_CreateMutexExW
0x18002b8e3  mov     rdx, rax
0x18002b8e6  lea     rcx, [rsp+270h+var_240]
0x18002b8eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002b8f0  cmp     [rsp+270h+var_240], 0
0x18002b8f6  jnz     short loc_18002B901
0x18002b8f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002b8fd  mov     ebx, eax
0x18002b8ff  jmp     short loc_18002B978
0x18002b901  lea     rdx, [rsp+270h+var_238]
0x18002b906  lea     rcx, [rsp+270h+var_240]
0x18002b90b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002b910  nop
0x18002b911  mov     [rsp+270h+var_230], 0
0x18002b91a  lea     rdx, [rsp+270h+var_230]; void **
0x18002b91f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b924  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002b929  mov     ebx, eax
0x18002b92b  test    eax, eax
0x18002b92d  jns     short loc_18002B958
0x18002b92f  mov     rcx, [rbp+178h]; this
0x18002b936  mov     r9d, eax; char *
0x18002b939  lea     r8, aWil; "wil"
0x18002b940  mov     edx, 12Eh; void *
0x18002b945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b94a  nop
0x18002b94b  lea     rcx, [rsp+270h+var_238]
0x18002b950  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b955  nop
0x18002b956  jmp     short loc_18002B978
0x18002b958  mov     rcx, [rsp+270h+var_230]
0x18002b95d  test    rcx, rcx
0x18002b960  jz      short loc_18002B9A8
0x18002b962  mov     [rdi], rcx
0x18002b965  mov     eax, [rcx]
0x18002b967  inc     eax
0x18002b969  mov     [rcx], eax
0x18002b96b  lea     rcx, [rsp+270h+var_238]
0x18002b970  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b975  nop
0x18002b976  xor     ebx, ebx
0x18002b978  lea     rcx, [rsp+270h+var_240]
0x18002b97d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b982  mov     eax, ebx
0x18002b984  mov     rcx, [rbp+170h+var_10]
0x18002b98b  xor     rcx, rsp; StackCookie
0x18002b98e  call    __security_check_cookie
0x18002b993  lea     r11, [rsp+270h+var_s0]
0x18002b99b  mov     rbx, [r11+20h]
0x18002b99f  mov     rdi, [r11+28h]
0x18002b9a3  mov     rsp, r11
0x18002b9a6  pop     rbp
0x18002b9a7  retn
0x18002b9a8  mov     r8, rdi
0x18002b9ab  lea     rdx, [rsp+270h+var_240]
0x18002b9b0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b9b5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002b9ba  mov     ebx, eax
0x18002b9bc  test    eax, eax
0x18002b9be  jns     short loc_18002B96B
0x18002b9c0  mov     rcx, [rbp+178h]; this
0x18002b9c7  mov     r9d, eax; char *
0x18002b9ca  lea     r8, aWil; "wil"
0x18002b9d1  mov     edx, 137h; void *
0x18002b9d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b9db  nop
0x18002b9dc  lea     rcx, [rsp+270h+var_238]
0x18002b9e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b9e6  nop
0x18002b9e7  jmp     short loc_18002B978
```
