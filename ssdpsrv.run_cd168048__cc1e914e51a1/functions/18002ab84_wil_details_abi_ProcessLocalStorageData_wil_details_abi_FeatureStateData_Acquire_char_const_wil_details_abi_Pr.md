# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18002ab84`
- end: `0x18002acf0`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002afa8`

## callees

- `0x180027ee4`
- `0x180028328`
- `0x1800287d0`
- `0x18002a86c`
- `0x18002a88c`
- `0x18002ab84`
- `0x18002c3c4`
- `0x18002d39c`
- `0x18002dab4`
- `0x18002e364`
- `0x18002e4b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002ac07`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002ac07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002abbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002abbc`

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
0x18002ab84  mov     [rsp-8+arg_10], rbx
0x18002ab89  mov     [rsp-8+arg_18], rdi
0x18002ab8e  push    rbp
0x18002ab8f  lea     rbp, [rsp-170h]
0x18002ab97  sub     rsp, 270h
0x18002ab9e  mov     rax, cs:__security_cookie
0x18002aba5  xor     rax, rsp
0x18002aba8  mov     [rbp+170h+var_10], rax
0x18002abaf  mov     rdi, rdx
0x18002abb2  mov     qword ptr [rdx], 0
0x18002abb9  mov     rbx, rcx
0x18002abbc  call    cs:__imp_GetCurrentProcessId
0x18002abc3  nop     dword ptr [rax+rax+00h]
0x18002abc8  mov     [rsp+270h+var_248], rbx
0x18002abcd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002abd4  mov     r9d, eax
0x18002abd7  mov     [rsp+270h+var_250], 130h; int
0x18002abdf  mov     edx, 104h; unsigned __int64
0x18002abe4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002abe9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002abee  mov     r9d, 1F0001h; dwDesiredAccess
0x18002abf4  mov     [rsp+270h+var_240], 0
0x18002abfd  xor     r8d, r8d; dwFlags
0x18002ac00  lea     rdx, [rsp+270h+Name]; lpName
0x18002ac05  xor     ecx, ecx; lpMutexAttributes
0x18002ac07  call    cs:__imp_CreateMutexExW
0x18002ac0e  nop     dword ptr [rax+rax+00h]
0x18002ac13  mov     rdx, rax
0x18002ac16  lea     rcx, [rsp+270h+var_240]
0x18002ac1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002ac20  cmp     [rsp+270h+var_240], 0
0x18002ac26  jnz     short loc_18002AC31
0x18002ac28  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002ac2d  mov     ebx, eax
0x18002ac2f  jmp     short loc_18002AC9D
0x18002ac31  lea     rdx, [rsp+270h+var_238]
0x18002ac36  lea     rcx, [rsp+270h+var_240]
0x18002ac3b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002ac40  lea     rdx, [rsp+270h+var_230]; void **
0x18002ac45  mov     [rsp+270h+var_230], 0
0x18002ac4e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002ac53  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002ac58  mov     ebx, eax
0x18002ac5a  test    eax, eax
0x18002ac5c  jns     short loc_18002AC7E
0x18002ac5e  mov     edx, 12Eh; void *
0x18002ac63  mov     rcx, [rbp+178h]; this
0x18002ac6a  mov     r9d, eax; char *
0x18002ac6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac72  lea     rcx, [rsp+270h+var_238]
0x18002ac77  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ac7c  jmp     short loc_18002AC9D
0x18002ac7e  mov     rcx, [rsp+270h+var_230]
0x18002ac83  test    rcx, rcx
0x18002ac86  jz      short loc_18002ACCE
0x18002ac88  mov     [rdi], rcx
0x18002ac8b  mov     eax, [rcx]
0x18002ac8d  inc     eax
0x18002ac8f  mov     [rcx], eax
0x18002ac91  lea     rcx, [rsp+270h+var_238]
0x18002ac96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ac9b  xor     ebx, ebx
0x18002ac9d  lea     rcx, [rsp+270h+var_240]
0x18002aca2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002aca7  mov     eax, ebx
0x18002aca9  mov     rcx, [rbp+170h+var_10]
0x18002acb0  xor     rcx, rsp; StackCookie
0x18002acb3  call    __security_check_cookie
0x18002acb8  lea     r11, [rsp+270h+var_s0]
0x18002acc0  mov     rbx, [r11+20h]
0x18002acc4  mov     rdi, [r11+28h]
0x18002acc8  mov     rsp, r11
0x18002accb  pop     rbp
0x18002accc  retn
0x18002acce  mov     r8, rdi
0x18002acd1  lea     rdx, [rsp+270h+var_240]
0x18002acd6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002acdb  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002ace0  mov     ebx, eax
0x18002ace2  test    eax, eax
0x18002ace4  jns     short loc_18002AC91
0x18002ace6  mov     edx, 137h
0x18002aceb  jmp     loc_18002AC63
```
