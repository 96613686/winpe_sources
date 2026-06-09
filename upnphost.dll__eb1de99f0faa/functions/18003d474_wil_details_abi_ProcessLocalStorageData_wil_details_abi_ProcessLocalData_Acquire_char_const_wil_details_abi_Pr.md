# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003d474`
- end: `0x18003d5d3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003f9f8`

## callees

- `0x180026e90`
- `0x180039d80`
- `0x18003a560`
- `0x18003cd18`
- `0x18003cd34`
- `0x18003d474`
- `0x180040304`
- `0x180042730`
- `0x1800435dc`
- `0x1800443c4`
- `0x180044554`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d4f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d4f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d4ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d4ac`

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
0x18003d474  mov     [rsp-8+arg_10], rbx
0x18003d479  mov     [rsp-8+arg_18], rdi
0x18003d47e  push    rbp
0x18003d47f  lea     rbp, [rsp-170h]
0x18003d487  sub     rsp, 270h
0x18003d48e  mov     rax, cs:__security_cookie
0x18003d495  xor     rax, rsp
0x18003d498  mov     [rbp+170h+var_10], rax
0x18003d49f  mov     rdi, rdx
0x18003d4a2  mov     qword ptr [rdx], 0
0x18003d4a9  mov     rbx, rcx
0x18003d4ac  call    cs:__imp_GetCurrentProcessId
0x18003d4b2  mov     [rsp+270h+var_248], rbx
0x18003d4b7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003d4be  mov     r9d, eax
0x18003d4c1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003d4c9  mov     edx, 104h; unsigned __int64
0x18003d4ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d4d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d4d8  mov     r9d, 1F0001h; dwDesiredAccess
0x18003d4de  mov     [rsp+270h+var_240], 0
0x18003d4e7  xor     r8d, r8d; dwFlags
0x18003d4ea  lea     rdx, [rsp+270h+Name]; lpName
0x18003d4ef  xor     ecx, ecx; lpMutexAttributes
0x18003d4f1  call    cs:__imp_CreateMutexExW
0x18003d4f7  mov     rdx, rax
0x18003d4fa  lea     rcx, [rsp+270h+var_240]
0x18003d4ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003d504  cmp     [rsp+270h+var_240], 0
0x18003d50a  jnz     short loc_18003D515
0x18003d50c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003d511  mov     ebx, eax
0x18003d513  jmp     short loc_18003D581
0x18003d515  lea     rdx, [rsp+270h+var_238]
0x18003d51a  lea     rcx, [rsp+270h+var_240]
0x18003d51f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003d524  lea     rdx, [rsp+270h+var_230]; void **
0x18003d529  mov     [rsp+270h+var_230], 0
0x18003d532  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d537  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003d53c  mov     ebx, eax
0x18003d53e  test    eax, eax
0x18003d540  jns     short loc_18003D562
0x18003d542  mov     edx, 12Eh; void *
0x18003d547  mov     rcx, [rbp+178h]; this
0x18003d54e  mov     r9d, eax; char *
0x18003d551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d556  lea     rcx, [rsp+270h+var_238]
0x18003d55b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d560  jmp     short loc_18003D581
0x18003d562  mov     rcx, [rsp+270h+var_230]
0x18003d567  test    rcx, rcx
0x18003d56a  jz      short loc_18003D5B1
0x18003d56c  mov     [rdi], rcx
0x18003d56f  mov     eax, [rcx]
0x18003d571  inc     eax
0x18003d573  mov     [rcx], eax
0x18003d575  lea     rcx, [rsp+270h+var_238]
0x18003d57a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d57f  xor     ebx, ebx
0x18003d581  lea     rcx, [rsp+270h+var_240]
0x18003d586  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d58b  mov     eax, ebx
0x18003d58d  mov     rcx, [rbp+170h+var_10]
0x18003d594  xor     rcx, rsp; StackCookie
0x18003d597  call    __security_check_cookie
0x18003d59c  lea     r11, [rsp+270h+var_s0]
0x18003d5a4  mov     rbx, [r11+20h]
0x18003d5a8  mov     rdi, [r11+28h]
0x18003d5ac  mov     rsp, r11
0x18003d5af  pop     rbp
0x18003d5b0  retn
0x18003d5b1  mov     r8, rdi
0x18003d5b4  lea     rdx, [rsp+270h+var_240]
0x18003d5b9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d5be  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003d5c3  mov     ebx, eax
0x18003d5c5  test    eax, eax
0x18003d5c7  jns     short loc_18003D575
0x18003d5c9  mov     edx, 137h
0x18003d5ce  jmp     loc_18003D547
```
