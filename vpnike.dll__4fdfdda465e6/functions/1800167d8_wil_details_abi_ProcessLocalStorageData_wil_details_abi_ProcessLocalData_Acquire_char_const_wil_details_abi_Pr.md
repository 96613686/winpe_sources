# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800167d8`
- end: `0x180016937`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018cdc`

## callees

- `0x180016284`
- `0x1800162a0`
- `0x1800167d8`
- `0x180018918`
- `0x18001a314`
- `0x18001e08c`
- `0x18001ee3c`
- `0x180020340`
- `0x18002065c`
- `0x180020bdc`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016855`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016855`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016810`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016810`

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
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(pszDest);
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
0x1800167d8  mov     [rsp-8+arg_10], rbx
0x1800167dd  mov     [rsp-8+arg_18], rdi
0x1800167e2  push    rbp
0x1800167e3  lea     rbp, [rsp-170h]
0x1800167eb  sub     rsp, 270h
0x1800167f2  mov     rax, cs:__security_cookie
0x1800167f9  xor     rax, rsp
0x1800167fc  mov     [rbp+170h+var_10], rax
0x180016803  mov     rdi, rdx
0x180016806  mov     qword ptr [rdx], 0
0x18001680d  mov     rbx, rcx
0x180016810  call    cs:__imp_GetCurrentProcessId
0x180016816  mov     [rsp+270h+var_248], rbx
0x18001681b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180016822  mov     r9d, eax
0x180016825  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001682d  mov     edx, 104h; cchDest
0x180016832  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180016837  call    StringCchPrintfW
0x18001683c  mov     r9d, 1F0001h; dwDesiredAccess
0x180016842  mov     [rsp+270h+var_240], 0
0x18001684b  xor     r8d, r8d; dwFlags
0x18001684e  lea     rdx, [rsp+270h+pszDest]; lpName
0x180016853  xor     ecx, ecx; lpMutexAttributes
0x180016855  call    cs:__imp_CreateMutexExW
0x18001685b  mov     rdx, rax
0x18001685e  lea     rcx, [rsp+270h+var_240]
0x180016863  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016868  cmp     [rsp+270h+var_240], 0
0x18001686e  jnz     short loc_180016879
0x180016870  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016875  mov     ebx, eax
0x180016877  jmp     short loc_1800168E5
0x180016879  lea     rdx, [rsp+270h+var_238]
0x18001687e  lea     rcx, [rsp+270h+var_240]
0x180016883  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180016888  lea     rdx, [rsp+270h+var_230]; void **
0x18001688d  mov     [rsp+270h+var_230], 0
0x180016896  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001689b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800168a0  mov     ebx, eax
0x1800168a2  test    eax, eax
0x1800168a4  jns     short loc_1800168C6
0x1800168a6  mov     edx, 12Eh; void *
0x1800168ab  mov     rcx, [rbp+178h]; this
0x1800168b2  mov     r9d, eax; char *
0x1800168b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168ba  lea     rcx, [rsp+270h+var_238]
0x1800168bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168c4  jmp     short loc_1800168E5
0x1800168c6  mov     rcx, [rsp+270h+var_230]
0x1800168cb  test    rcx, rcx
0x1800168ce  jz      short loc_180016915
0x1800168d0  mov     [rdi], rcx
0x1800168d3  mov     eax, [rcx]
0x1800168d5  inc     eax
0x1800168d7  mov     [rcx], eax
0x1800168d9  lea     rcx, [rsp+270h+var_238]
0x1800168de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168e3  xor     ebx, ebx
0x1800168e5  lea     rcx, [rsp+270h+var_240]
0x1800168ea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800168ef  mov     eax, ebx
0x1800168f1  mov     rcx, [rbp+170h+var_10]
0x1800168f8  xor     rcx, rsp; StackCookie
0x1800168fb  call    __security_check_cookie
0x180016900  lea     r11, [rsp+270h+var_s0]
0x180016908  mov     rbx, [r11+20h]
0x18001690c  mov     rdi, [r11+28h]
0x180016910  mov     rsp, r11
0x180016913  pop     rbp
0x180016914  retn
0x180016915  mov     r8, rdi
0x180016918  lea     rdx, [rsp+270h+var_240]
0x18001691d  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016922  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180016927  mov     ebx, eax
0x180016929  test    eax, eax
0x18001692b  jns     short loc_1800168D9
0x18001692d  mov     edx, 137h
0x180016932  jmp     loc_1800168AB
```
