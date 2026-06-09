# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18008651c`
- end: `0x180086691`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180086938`

## callees

- `0x180071c14`
- `0x1800722f0`
- `0x1800861fc`
- `0x18008621c`
- `0x18008651c`
- `0x180087e64`
- `0x180088c40`
- `0x180089208`
- `0x180089994`
- `0x180089a54`
- `0x180089de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086554`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008659f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18008659f`

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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(pszDest, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x18008651c  mov     [rsp-8+arg_10], rbx
0x180086521  mov     [rsp-8+arg_18], rdi
0x180086526  push    rbp
0x180086527  lea     rbp, [rsp-170h]
0x18008652f  sub     rsp, 270h
0x180086536  mov     rax, cs:__security_cookie
0x18008653d  xor     rax, rsp
0x180086540  mov     [rbp+170h+var_10], rax
0x180086547  mov     rdi, rdx
0x18008654a  mov     qword ptr [rdx], 0
0x180086551  mov     rbx, rcx
0x180086554  call    cs:__imp_GetCurrentProcessId
0x18008655b  nop     dword ptr [rax+rax+00h]
0x180086560  mov     [rsp+270h+var_248], rbx
0x180086565  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18008656c  mov     r9d, eax
0x18008656f  mov     [rsp+270h+var_250], 130h; int
0x180086577  mov     edx, 104h; cchDest
0x18008657c  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180086581  call    StringCchPrintfW
0x180086586  mov     r9d, 1F0001h; dwDesiredAccess
0x18008658c  mov     [rsp+270h+var_240], 0
0x180086595  xor     r8d, r8d; dwFlags
0x180086598  lea     rdx, [rsp+270h+pszDest]; lpName
0x18008659d  xor     ecx, ecx; lpMutexAttributes
0x18008659f  call    cs:__imp_CreateMutexExW
0x1800865a6  nop     dword ptr [rax+rax+00h]
0x1800865ab  mov     rdx, rax
0x1800865ae  lea     rcx, [rsp+270h+var_240]
0x1800865b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800865b8  cmp     [rsp+270h+var_240], 0
0x1800865be  jnz     short loc_1800865C9
0x1800865c0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800865c5  mov     ebx, eax
0x1800865c7  jmp     short loc_18008663E
0x1800865c9  lea     rdx, [rsp+270h+var_238]
0x1800865ce  mov     [rsp+270h+var_238], 0
0x1800865d7  lea     rcx, [rsp+270h+var_240]
0x1800865dc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800865e1  lea     rdx, [rsp+270h+var_230]; void **
0x1800865e6  mov     [rsp+270h+var_230], 0
0x1800865ef  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800865f4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800865f9  mov     ebx, eax
0x1800865fb  test    eax, eax
0x1800865fd  jns     short loc_18008661F
0x1800865ff  mov     edx, 12Eh; void *
0x180086604  mov     rcx, [rbp+178h]; this
0x18008660b  mov     r9d, eax; char *
0x18008660e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086613  lea     rcx, [rsp+270h+var_238]
0x180086618  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008661d  jmp     short loc_18008663E
0x18008661f  mov     rcx, [rsp+270h+var_230]
0x180086624  test    rcx, rcx
0x180086627  jz      short loc_18008666F
0x180086629  mov     [rdi], rcx
0x18008662c  mov     eax, [rcx]
0x18008662e  inc     eax
0x180086630  mov     [rcx], eax
0x180086632  lea     rcx, [rsp+270h+var_238]
0x180086637  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008663c  xor     ebx, ebx
0x18008663e  lea     rcx, [rsp+270h+var_240]
0x180086643  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180086648  mov     eax, ebx
0x18008664a  mov     rcx, [rbp+170h+var_10]
0x180086651  xor     rcx, rsp; StackCookie
0x180086654  call    __security_check_cookie
0x180086659  lea     r11, [rsp+270h+var_s0]
0x180086661  mov     rbx, [r11+20h]
0x180086665  mov     rdi, [r11+28h]
0x180086669  mov     rsp, r11
0x18008666c  pop     rbp
0x18008666d  retn
0x18008666f  mov     r8, rdi
0x180086672  lea     rdx, [rsp+270h+var_240]
0x180086677  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18008667c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180086681  mov     ebx, eax
0x180086683  test    eax, eax
0x180086685  jns     short loc_180086632
0x180086687  mov     edx, 137h
0x18008668c  jmp     loc_180086604
```
