# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003d5dc`
- end: `0x18003d73b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003ed20`

## callees

- `0x180026e90`
- `0x180039d80`
- `0x18003a560`
- `0x18003cd18`
- `0x18003cd34`
- `0x18003d5dc`
- `0x180040428`
- `0x180042730`
- `0x1800435dc`
- `0x1800443c4`
- `0x180044554`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d659`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003d659`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d614`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d614`

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
0x18003d5dc  mov     [rsp-8+arg_10], rbx
0x18003d5e1  mov     [rsp-8+arg_18], rdi
0x18003d5e6  push    rbp
0x18003d5e7  lea     rbp, [rsp-170h]
0x18003d5ef  sub     rsp, 270h
0x18003d5f6  mov     rax, cs:__security_cookie
0x18003d5fd  xor     rax, rsp
0x18003d600  mov     [rbp+170h+var_10], rax
0x18003d607  mov     rdi, rdx
0x18003d60a  mov     qword ptr [rdx], 0
0x18003d611  mov     rbx, rcx
0x18003d614  call    cs:__imp_GetCurrentProcessId
0x18003d61a  mov     [rsp+270h+var_248], rbx
0x18003d61f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003d626  mov     r9d, eax
0x18003d629  mov     [rsp+270h+var_250], 130h; int
0x18003d631  mov     edx, 104h; unsigned __int64
0x18003d636  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d63b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d640  mov     r9d, 1F0001h; dwDesiredAccess
0x18003d646  mov     [rsp+270h+var_240], 0
0x18003d64f  xor     r8d, r8d; dwFlags
0x18003d652  lea     rdx, [rsp+270h+Name]; lpName
0x18003d657  xor     ecx, ecx; lpMutexAttributes
0x18003d659  call    cs:__imp_CreateMutexExW
0x18003d65f  mov     rdx, rax
0x18003d662  lea     rcx, [rsp+270h+var_240]
0x18003d667  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003d66c  cmp     [rsp+270h+var_240], 0
0x18003d672  jnz     short loc_18003D67D
0x18003d674  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003d679  mov     ebx, eax
0x18003d67b  jmp     short loc_18003D6E9
0x18003d67d  lea     rdx, [rsp+270h+var_238]
0x18003d682  lea     rcx, [rsp+270h+var_240]
0x18003d687  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003d68c  lea     rdx, [rsp+270h+var_230]; void **
0x18003d691  mov     [rsp+270h+var_230], 0
0x18003d69a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d69f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003d6a4  mov     ebx, eax
0x18003d6a6  test    eax, eax
0x18003d6a8  jns     short loc_18003D6CA
0x18003d6aa  mov     edx, 12Eh; void *
0x18003d6af  mov     rcx, [rbp+178h]; this
0x18003d6b6  mov     r9d, eax; char *
0x18003d6b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d6be  lea     rcx, [rsp+270h+var_238]
0x18003d6c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d6c8  jmp     short loc_18003D6E9
0x18003d6ca  mov     rcx, [rsp+270h+var_230]
0x18003d6cf  test    rcx, rcx
0x18003d6d2  jz      short loc_18003D719
0x18003d6d4  mov     [rdi], rcx
0x18003d6d7  mov     eax, [rcx]
0x18003d6d9  inc     eax
0x18003d6db  mov     [rcx], eax
0x18003d6dd  lea     rcx, [rsp+270h+var_238]
0x18003d6e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d6e7  xor     ebx, ebx
0x18003d6e9  lea     rcx, [rsp+270h+var_240]
0x18003d6ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d6f3  mov     eax, ebx
0x18003d6f5  mov     rcx, [rbp+170h+var_10]
0x18003d6fc  xor     rcx, rsp; StackCookie
0x18003d6ff  call    __security_check_cookie
0x18003d704  lea     r11, [rsp+270h+var_s0]
0x18003d70c  mov     rbx, [r11+20h]
0x18003d710  mov     rdi, [r11+28h]
0x18003d714  mov     rsp, r11
0x18003d717  pop     rbp
0x18003d718  retn
0x18003d719  mov     r8, rdi
0x18003d71c  lea     rdx, [rsp+270h+var_240]
0x18003d721  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003d726  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003d72b  mov     ebx, eax
0x18003d72d  test    eax, eax
0x18003d72f  jns     short loc_18003D6DD
0x18003d731  mov     edx, 137h
0x18003d736  jmp     loc_18003D6AF
```
