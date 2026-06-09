# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001f930`
- end: `0x18001fa99`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020718`

## callees

- `0x180003514`
- `0x180003554`
- `0x180003690`
- `0x1800049d0`
- `0x180004a60`
- `0x180019b2c`
- `0x18001f038`
- `0x18001f930`
- `0x18001faa0`
- `0x180021ec0`
- `0x180025958`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f9ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f968`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f968`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(v12);
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
    __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001f930  mov     [rsp-8+arg_10], rbx
0x18001f935  mov     [rsp-8+arg_18], rdi
0x18001f93a  push    rbp
0x18001f93b  lea     rbp, [rsp-170h]
0x18001f943  sub     rsp, 270h
0x18001f94a  mov     rax, cs:__security_cookie
0x18001f951  xor     rax, rsp
0x18001f954  mov     [rbp+170h+var_10], rax
0x18001f95b  mov     rdi, rdx
0x18001f95e  mov     rbx, rcx
0x18001f961  mov     qword ptr [rdx], 0
0x18001f968  call    cs:__imp_GetCurrentProcessId
0x18001f96e  mov     r9d, eax
0x18001f971  mov     [rsp+270h+var_248], rbx
0x18001f976  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001f97e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f985  mov     edx, 104h; unsigned __int64
0x18001f98a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f98f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f994  mov     [rsp+270h+var_240], 0
0x18001f99d  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f9a3  xor     r8d, r8d; dwFlags
0x18001f9a6  lea     rdx, [rsp+270h+Name]; lpName
0x18001f9ab  xor     ecx, ecx; lpMutexAttributes
0x18001f9ad  call    cs:__imp_CreateMutexExW
0x18001f9b3  mov     rdx, rax
0x18001f9b6  lea     rcx, [rsp+270h+var_240]
0x18001f9bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f9c0  cmp     [rsp+270h+var_240], 0
0x18001f9c6  jnz     short loc_18001F9D1
0x18001f9c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f9cd  mov     ebx, eax
0x18001f9cf  jmp     short loc_18001FA46
0x18001f9d1  lea     rdx, [rsp+270h+var_238]
0x18001f9d6  lea     rcx, [rsp+270h+var_240]
0x18001f9db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f9e0  nop
0x18001f9e1  mov     [rsp+270h+var_230], 0
0x18001f9ea  lea     rdx, [rsp+270h+var_230]; void **
0x18001f9ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f9f4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001f9f9  mov     ebx, eax
0x18001f9fb  test    eax, eax
0x18001f9fd  jns     short loc_18001FA27
0x18001f9ff  mov     edx, 12Eh; void *
0x18001fa04  lea     r8, aWil; "wil"
0x18001fa0b  mov     r9d, eax; char *
0x18001fa0e  mov     rcx, [rbp+178h]; this
0x18001fa15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa1a  nop
0x18001fa1b  lea     rcx, [rsp+270h+var_238]
0x18001fa20  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18001fa25  jmp     short loc_18001FA46
0x18001fa27  mov     rcx, [rsp+270h+var_230]
0x18001fa2c  test    rcx, rcx
0x18001fa2f  jz      short loc_18001FA76
0x18001fa31  mov     [rdi], rcx
0x18001fa34  mov     eax, [rcx]
0x18001fa36  inc     eax
0x18001fa38  mov     [rcx], eax
0x18001fa3a  lea     rcx, [rsp+270h+var_238]
0x18001fa3f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ
0x18001fa44  xor     ebx, ebx
0x18001fa46  lea     rcx, [rsp+270h+var_240]
0x18001fa4b  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18001fa50  mov     eax, ebx
0x18001fa52  mov     rcx, [rbp+170h+var_10]
0x18001fa59  xor     rcx, rsp; StackCookie
0x18001fa5c  call    __security_check_cookie
0x18001fa61  lea     r11, [rsp+270h+var_s0]
0x18001fa69  mov     rbx, [r11+20h]
0x18001fa6d  mov     rdi, [r11+28h]
0x18001fa71  mov     rsp, r11
0x18001fa74  pop     rbp
0x18001fa75  retn
0x18001fa76  mov     r8, rdi
0x18001fa79  lea     rdx, [rsp+270h+var_240]
0x18001fa7e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fa83  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001fa88  mov     ebx, eax
0x18001fa8a  test    eax, eax
0x18001fa8c  jns     short loc_18001FA3A
0x18001fa8e  mov     edx, 137h
0x18001fa93  jmp     loc_18001FA04
```
