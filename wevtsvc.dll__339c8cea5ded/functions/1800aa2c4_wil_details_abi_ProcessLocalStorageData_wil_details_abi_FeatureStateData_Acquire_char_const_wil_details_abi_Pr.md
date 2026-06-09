# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800aa2c4`
- end: `0x1800aa423`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800aa484`

## callees

- `0x18009a534`
- `0x18009aee0`
- `0x1800a1df4`
- `0x1800a1e10`
- `0x1800a6270`
- `0x1800a67f0`
- `0x1800a68a8`
- `0x1800a788c`
- `0x1800a7a4c`
- `0x1800aa2c4`
- `0x1800aa91c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aa341`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800aa341`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa2fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa2fc`

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
0x1800aa2c4  mov     [rsp-8+arg_10], rbx
0x1800aa2c9  mov     [rsp-8+arg_18], rdi
0x1800aa2ce  push    rbp
0x1800aa2cf  lea     rbp, [rsp-170h]
0x1800aa2d7  sub     rsp, 270h
0x1800aa2de  mov     rax, cs:__security_cookie
0x1800aa2e5  xor     rax, rsp
0x1800aa2e8  mov     [rbp+170h+var_10], rax
0x1800aa2ef  mov     rdi, rdx
0x1800aa2f2  mov     qword ptr [rdx], 0
0x1800aa2f9  mov     rbx, rcx
0x1800aa2fc  call    cs:__imp_GetCurrentProcessId
0x1800aa302  mov     [rsp+270h+var_248], rbx
0x1800aa307  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800aa30e  mov     r9d, eax
0x1800aa311  mov     [rsp+270h+var_250], 130h; int
0x1800aa319  mov     edx, 104h; unsigned __int64
0x1800aa31e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800aa323  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800aa328  mov     r9d, 1F0001h; dwDesiredAccess
0x1800aa32e  mov     [rsp+270h+var_240], 0
0x1800aa337  xor     r8d, r8d; dwFlags
0x1800aa33a  lea     rdx, [rsp+270h+Name]; lpName
0x1800aa33f  xor     ecx, ecx; lpMutexAttributes
0x1800aa341  call    cs:__imp_CreateMutexExW
0x1800aa347  mov     rdx, rax
0x1800aa34a  lea     rcx, [rsp+270h+var_240]
0x1800aa34f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800aa354  cmp     [rsp+270h+var_240], 0
0x1800aa35a  jnz     short loc_1800AA365
0x1800aa35c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800aa361  mov     ebx, eax
0x1800aa363  jmp     short loc_1800AA3D1
0x1800aa365  lea     rdx, [rsp+270h+var_238]
0x1800aa36a  lea     rcx, [rsp+270h+var_240]
0x1800aa36f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800aa374  lea     rdx, [rsp+270h+var_230]; void **
0x1800aa379  mov     [rsp+270h+var_230], 0
0x1800aa382  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800aa387  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800aa38c  mov     ebx, eax
0x1800aa38e  test    eax, eax
0x1800aa390  jns     short loc_1800AA3B2
0x1800aa392  mov     edx, 12Eh; void *
0x1800aa397  mov     rcx, [rbp+178h]; this
0x1800aa39e  mov     r9d, eax; char *
0x1800aa3a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aa3a6  lea     rcx, [rsp+270h+var_238]
0x1800aa3ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aa3b0  jmp     short loc_1800AA3D1
0x1800aa3b2  mov     rcx, [rsp+270h+var_230]
0x1800aa3b7  test    rcx, rcx
0x1800aa3ba  jz      short loc_1800AA401
0x1800aa3bc  mov     [rdi], rcx
0x1800aa3bf  mov     eax, [rcx]
0x1800aa3c1  inc     eax
0x1800aa3c3  mov     [rcx], eax
0x1800aa3c5  lea     rcx, [rsp+270h+var_238]
0x1800aa3ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aa3cf  xor     ebx, ebx
0x1800aa3d1  lea     rcx, [rsp+270h+var_240]
0x1800aa3d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800aa3db  mov     eax, ebx
0x1800aa3dd  mov     rcx, [rbp+170h+var_10]
0x1800aa3e4  xor     rcx, rsp; StackCookie
0x1800aa3e7  call    __security_check_cookie
0x1800aa3ec  lea     r11, [rsp+270h+var_s0]
0x1800aa3f4  mov     rbx, [r11+20h]
0x1800aa3f8  mov     rdi, [r11+28h]
0x1800aa3fc  mov     rsp, r11
0x1800aa3ff  pop     rbp
0x1800aa400  retn
0x1800aa401  mov     r8, rdi
0x1800aa404  lea     rdx, [rsp+270h+var_240]
0x1800aa409  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800aa40e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800aa413  mov     ebx, eax
0x1800aa415  test    eax, eax
0x1800aa417  jns     short loc_1800AA3C5
0x1800aa419  mov     edx, 137h
0x1800aa41e  jmp     loc_1800AA397
```
