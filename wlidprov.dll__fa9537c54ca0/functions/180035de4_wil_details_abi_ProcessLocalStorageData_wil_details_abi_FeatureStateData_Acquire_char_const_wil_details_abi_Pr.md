# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180035de4`
- end: `0x180035f4a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800361b8`

## callees

- `0x180011010`
- `0x180015a04`
- `0x1800165f0`
- `0x180016758`
- `0x18001a0d0`
- `0x18002070c`
- `0x180020728`
- `0x180022438`
- `0x1800228c0`
- `0x1800229b0`
- `0x180035de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035e61`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180035e61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035e1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035e1c`

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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180035de4  mov     [rsp-8+arg_10], rbx
0x180035de9  mov     [rsp-8+arg_18], rdi
0x180035dee  push    rbp
0x180035def  lea     rbp, [rsp-170h]
0x180035df7  sub     rsp, 270h
0x180035dfe  mov     rax, cs:__security_cookie
0x180035e05  xor     rax, rsp
0x180035e08  mov     [rbp+170h+var_10], rax
0x180035e0f  mov     rdi, rdx
0x180035e12  mov     qword ptr [rdx], 0
0x180035e19  mov     rbx, rcx
0x180035e1c  call    cs:__imp_GetCurrentProcessId
0x180035e22  mov     [rsp+270h+var_248], rbx
0x180035e27  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180035e2e  mov     r9d, eax
0x180035e31  mov     [rsp+270h+var_250], 130h; int
0x180035e39  mov     edx, 104h; unsigned __int64
0x180035e3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035e43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035e48  mov     r9d, 1F0001h; dwDesiredAccess
0x180035e4e  mov     [rsp+270h+var_240], 0
0x180035e57  xor     r8d, r8d; dwFlags
0x180035e5a  lea     rdx, [rsp+270h+Name]; lpName
0x180035e5f  xor     ecx, ecx; lpMutexAttributes
0x180035e61  call    cs:__imp_CreateMutexExW
0x180035e67  mov     rdx, rax
0x180035e6a  lea     rcx, [rsp+270h+var_240]
0x180035e6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180035e74  cmp     [rsp+270h+var_240], 0
0x180035e7a  jnz     short loc_180035E85
0x180035e7c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180035e81  mov     ebx, eax
0x180035e83  jmp     short loc_180035EF8
0x180035e85  lea     rdx, [rsp+270h+var_238]
0x180035e8a  lea     rcx, [rsp+270h+var_240]
0x180035e8f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180035e94  lea     rdx, [rsp+270h+var_230]; void **
0x180035e99  mov     [rsp+270h+var_230], 0
0x180035ea2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035ea7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180035eac  mov     ebx, eax
0x180035eae  test    eax, eax
0x180035eb0  jns     short loc_180035ED9
0x180035eb2  mov     edx, 12Eh; void *
0x180035eb7  mov     rcx, [rbp+178h]; this
0x180035ebe  lea     r8, aWil; "wil"
0x180035ec5  mov     r9d, eax; char *
0x180035ec8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ecd  lea     rcx, [rsp+270h+var_238]
0x180035ed2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035ed7  jmp     short loc_180035EF8
0x180035ed9  mov     rcx, [rsp+270h+var_230]
0x180035ede  test    rcx, rcx
0x180035ee1  jz      short loc_180035F28
0x180035ee3  mov     [rdi], rcx
0x180035ee6  mov     eax, [rcx]
0x180035ee8  inc     eax
0x180035eea  mov     [rcx], eax
0x180035eec  lea     rcx, [rsp+270h+var_238]
0x180035ef1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035ef6  xor     ebx, ebx
0x180035ef8  lea     rcx, [rsp+270h+var_240]
0x180035efd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035f02  mov     eax, ebx
0x180035f04  mov     rcx, [rbp+170h+var_10]
0x180035f0b  xor     rcx, rsp; StackCookie
0x180035f0e  call    __security_check_cookie
0x180035f13  lea     r11, [rsp+270h+var_s0]
0x180035f1b  mov     rbx, [r11+20h]
0x180035f1f  mov     rdi, [r11+28h]
0x180035f23  mov     rsp, r11
0x180035f26  pop     rbp
0x180035f27  retn
0x180035f28  mov     r8, rdi
0x180035f2b  lea     rdx, [rsp+270h+var_240]
0x180035f30  lea     rcx, [rsp+270h+Name]
0x180035f35  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180035f3a  mov     ebx, eax
0x180035f3c  test    eax, eax
0x180035f3e  jns     short loc_180035EEC
0x180035f40  mov     edx, 137h
0x180035f45  jmp     loc_180035EB7
```
