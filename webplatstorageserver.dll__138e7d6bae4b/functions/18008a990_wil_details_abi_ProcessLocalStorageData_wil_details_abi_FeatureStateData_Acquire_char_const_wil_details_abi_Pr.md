# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18008a990`
- end: `0x18008aaff`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18008ab78`

## callees

- `0x180027550`
- `0x18006fb88`
- `0x180071508`
- `0x180080fb0`
- `0x180089038`
- `0x180089054`
- `0x180089f34`
- `0x18008a190`
- `0x18008a248`
- `0x18008a990`
- `0x18008b114`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008a9c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008a9c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008aa0d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008aa0d`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
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
    v12 = 0;
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18008a990  mov     [rsp-8+arg_10], rbx
0x18008a995  mov     [rsp-8+arg_18], rdi
0x18008a99a  push    rbp
0x18008a99b  lea     rbp, [rsp-170h]
0x18008a9a3  sub     rsp, 270h
0x18008a9aa  mov     rax, cs:__security_cookie
0x18008a9b1  xor     rax, rsp
0x18008a9b4  mov     [rbp+170h+var_10], rax
0x18008a9bb  mov     rdi, rdx
0x18008a9be  mov     qword ptr [rdx], 0
0x18008a9c5  mov     rbx, rcx
0x18008a9c8  call    cs:__imp_GetCurrentProcessId
0x18008a9ce  mov     [rsp+270h+var_248], rbx
0x18008a9d3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18008a9da  mov     r9d, eax
0x18008a9dd  mov     [rsp+270h+var_250], 130h; int
0x18008a9e5  mov     edx, 104h; unsigned __int64
0x18008a9ea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008a9ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008a9f4  mov     r9d, 1F0001h; dwDesiredAccess
0x18008a9fa  mov     [rsp+270h+var_240], 0
0x18008aa03  xor     r8d, r8d; dwFlags
0x18008aa06  lea     rdx, [rsp+270h+Name]; lpName
0x18008aa0b  xor     ecx, ecx; lpMutexAttributes
0x18008aa0d  call    cs:__imp_CreateMutexExW
0x18008aa13  mov     rdx, rax
0x18008aa16  lea     rcx, [rsp+270h+var_240]
0x18008aa1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18008aa20  cmp     [rsp+270h+var_240], 0
0x18008aa26  jnz     short loc_18008AA31
0x18008aa28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18008aa2d  mov     ebx, eax
0x18008aa2f  jmp     short loc_18008AAAD
0x18008aa31  lea     rdx, [rsp+270h+var_238]
0x18008aa36  mov     [rsp+270h+var_238], 0
0x18008aa3f  lea     rcx, [rsp+270h+var_240]
0x18008aa44  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18008aa49  lea     rdx, [rsp+270h+var_230]; void **
0x18008aa4e  mov     [rsp+270h+var_230], 0
0x18008aa57  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008aa5c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18008aa61  mov     ebx, eax
0x18008aa63  test    eax, eax
0x18008aa65  jns     short loc_18008AA8E
0x18008aa67  mov     edx, 12Eh; void *
0x18008aa6c  mov     rcx, [rbp+178h]; this
0x18008aa73  lea     r8, aWil; "wil"
0x18008aa7a  mov     r9d, eax; char *
0x18008aa7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008aa82  lea     rcx, [rsp+270h+var_238]
0x18008aa87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008aa8c  jmp     short loc_18008AAAD
0x18008aa8e  mov     rcx, [rsp+270h+var_230]
0x18008aa93  test    rcx, rcx
0x18008aa96  jz      short loc_18008AADD
0x18008aa98  mov     [rdi], rcx
0x18008aa9b  mov     eax, [rcx]
0x18008aa9d  inc     eax
0x18008aa9f  mov     [rcx], eax
0x18008aaa1  lea     rcx, [rsp+270h+var_238]
0x18008aaa6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008aaab  xor     ebx, ebx
0x18008aaad  lea     rcx, [rsp+270h+var_240]
0x18008aab2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008aab7  mov     eax, ebx
0x18008aab9  mov     rcx, [rbp+170h+var_10]
0x18008aac0  xor     rcx, rsp; StackCookie
0x18008aac3  call    __security_check_cookie
0x18008aac8  lea     r11, [rsp+270h+var_s0]
0x18008aad0  mov     rbx, [r11+20h]
0x18008aad4  mov     rdi, [r11+28h]
0x18008aad8  mov     rsp, r11
0x18008aadb  pop     rbp
0x18008aadc  retn
0x18008aadd  mov     r8, rdi
0x18008aae0  lea     rdx, [rsp+270h+var_240]
0x18008aae5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18008aaea  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18008aaef  mov     ebx, eax
0x18008aaf1  test    eax, eax
0x18008aaf3  jns     short loc_18008AAA1
0x18008aaf5  mov     edx, 137h
0x18008aafa  jmp     loc_18008AA6C
```
