# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006808`
- end: `0x180006967`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007730`

## callees

- `0x180002ae0`
- `0x1800063ec`
- `0x180006408`
- `0x180006808`
- `0x180007548`
- `0x1800081dc`
- `0x1800093ec`
- `0x180009b50`
- `0x180009e4c`
- `0x18000a53c`
- `0x18000a854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006885`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006840`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180006808  mov     [rsp-8+arg_10], rbx
0x18000680d  mov     [rsp-8+arg_18], rdi
0x180006812  push    rbp
0x180006813  lea     rbp, [rsp-170h]
0x18000681b  sub     rsp, 270h
0x180006822  mov     rax, cs:__security_cookie
0x180006829  xor     rax, rsp
0x18000682c  mov     [rbp+170h+var_10], rax
0x180006833  mov     rdi, rdx
0x180006836  mov     qword ptr [rdx], 0
0x18000683d  mov     rbx, rcx
0x180006840  call    cs:__imp_GetCurrentProcessId
0x180006846  mov     [rsp+270h+var_248], rbx
0x18000684b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006852  mov     r9d, eax
0x180006855  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000685d  mov     edx, 104h; unsigned __int64
0x180006862  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006867  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000686c  mov     r9d, 1F0001h; dwDesiredAccess
0x180006872  mov     [rsp+270h+var_240], 0
0x18000687b  xor     r8d, r8d; dwFlags
0x18000687e  lea     rdx, [rsp+270h+Name]; lpName
0x180006883  xor     ecx, ecx; lpMutexAttributes
0x180006885  call    cs:__imp_CreateMutexExW
0x18000688b  mov     rdx, rax
0x18000688e  lea     rcx, [rsp+270h+var_240]
0x180006893  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006898  cmp     [rsp+270h+var_240], 0
0x18000689e  jnz     short loc_1800068A9
0x1800068a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800068a5  mov     ebx, eax
0x1800068a7  jmp     short loc_180006915
0x1800068a9  lea     rdx, [rsp+270h+var_238]
0x1800068ae  lea     rcx, [rsp+270h+var_240]
0x1800068b3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800068b8  lea     rdx, [rsp+270h+var_230]; void **
0x1800068bd  mov     [rsp+270h+var_230], 0
0x1800068c6  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800068cb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800068d0  mov     ebx, eax
0x1800068d2  test    eax, eax
0x1800068d4  jns     short loc_1800068F6
0x1800068d6  mov     edx, 12Eh; void *
0x1800068db  mov     rcx, [rbp+178h]; this
0x1800068e2  mov     r9d, eax; char *
0x1800068e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068ea  lea     rcx, [rsp+270h+var_238]
0x1800068ef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800068f4  jmp     short loc_180006915
0x1800068f6  mov     rcx, [rsp+270h+var_230]
0x1800068fb  test    rcx, rcx
0x1800068fe  jz      short loc_180006945
0x180006900  mov     [rdi], rcx
0x180006903  mov     eax, [rcx]
0x180006905  inc     eax
0x180006907  mov     [rcx], eax
0x180006909  lea     rcx, [rsp+270h+var_238]
0x18000690e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006913  xor     ebx, ebx
0x180006915  lea     rcx, [rsp+270h+var_240]
0x18000691a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000691f  mov     eax, ebx
0x180006921  mov     rcx, [rbp+170h+var_10]
0x180006928  xor     rcx, rsp; StackCookie
0x18000692b  call    __security_check_cookie
0x180006930  lea     r11, [rsp+270h+var_s0]
0x180006938  mov     rbx, [r11+20h]
0x18000693c  mov     rdi, [r11+28h]
0x180006940  mov     rsp, r11
0x180006943  pop     rbp
0x180006944  retn
0x180006945  mov     r8, rdi
0x180006948  lea     rdx, [rsp+270h+var_240]
0x18000694d  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006952  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006957  mov     ebx, eax
0x180006959  test    eax, eax
0x18000695b  jns     short loc_180006909
0x18000695d  mov     edx, 137h
0x180006962  jmp     loc_1800068DB
```
