# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003682c`
- end: `0x18003698b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180038ae0`

## callees

- `0x180001600`
- `0x180036338`
- `0x180036354`
- `0x18003682c`
- `0x180038408`
- `0x18003980c`
- `0x18003acf8`
- `0x18003b9ac`
- `0x18003c484`
- `0x18003c768`
- `0x18003d3dc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180036864`
- `KERNEL32!GetCurrentProcessId` at `0x180036864`
- `KERNEL32!CreateMutexExW` at `0x1800368a9`
- `KERNEL32!CreateMutexExW` at `0x1800368a9`

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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(pszDest);
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
0x18003682c  mov     [rsp-8+arg_10], rbx
0x180036831  mov     [rsp-8+arg_18], rdi
0x180036836  push    rbp
0x180036837  lea     rbp, [rsp-170h]
0x18003683f  sub     rsp, 270h
0x180036846  mov     rax, cs:__security_cookie
0x18003684d  xor     rax, rsp
0x180036850  mov     [rbp+170h+var_10], rax
0x180036857  mov     rdi, rdx
0x18003685a  mov     qword ptr [rdx], 0
0x180036861  mov     rbx, rcx
0x180036864  call    cs:__imp_GetCurrentProcessId
0x18003686a  mov     [rsp+270h+var_248], rbx
0x18003686f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180036876  mov     r9d, eax
0x180036879  mov     [rsp+270h+var_250], 130h; int
0x180036881  mov     edx, 104h; cchDest
0x180036886  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003688b  call    StringCchPrintfW
0x180036890  mov     r9d, 1F0001h; dwDesiredAccess
0x180036896  mov     [rsp+270h+var_240], 0
0x18003689f  xor     r8d, r8d; dwFlags
0x1800368a2  lea     rdx, [rsp+270h+pszDest]; lpName
0x1800368a7  xor     ecx, ecx; lpMutexAttributes
0x1800368a9  call    cs:__imp_CreateMutexExW
0x1800368af  mov     rdx, rax
0x1800368b2  lea     rcx, [rsp+270h+var_240]
0x1800368b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800368bc  cmp     [rsp+270h+var_240], 0
0x1800368c2  jnz     short loc_1800368CD
0x1800368c4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800368c9  mov     ebx, eax
0x1800368cb  jmp     short loc_180036939
0x1800368cd  lea     rdx, [rsp+270h+var_238]
0x1800368d2  lea     rcx, [rsp+270h+var_240]
0x1800368d7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800368dc  lea     rdx, [rsp+270h+var_230]; void **
0x1800368e1  mov     [rsp+270h+var_230], 0
0x1800368ea  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800368ef  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800368f4  mov     ebx, eax
0x1800368f6  test    eax, eax
0x1800368f8  jns     short loc_18003691A
0x1800368fa  mov     edx, 12Eh; void *
0x1800368ff  mov     rcx, [rbp+178h]; this
0x180036906  mov     r9d, eax; char *
0x180036909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003690e  lea     rcx, [rsp+270h+var_238]
0x180036913  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036918  jmp     short loc_180036939
0x18003691a  mov     rcx, [rsp+270h+var_230]
0x18003691f  test    rcx, rcx
0x180036922  jz      short loc_180036969
0x180036924  mov     [rdi], rcx
0x180036927  mov     eax, [rcx]
0x180036929  inc     eax
0x18003692b  mov     [rcx], eax
0x18003692d  lea     rcx, [rsp+270h+var_238]
0x180036932  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036937  xor     ebx, ebx
0x180036939  lea     rcx, [rsp+270h+var_240]
0x18003693e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036943  mov     eax, ebx
0x180036945  mov     rcx, [rbp+170h+var_10]
0x18003694c  xor     rcx, rsp; StackCookie
0x18003694f  call    __security_check_cookie
0x180036954  lea     r11, [rsp+270h+var_s0]
0x18003695c  mov     rbx, [r11+20h]
0x180036960  mov     rdi, [r11+28h]
0x180036964  mov     rsp, r11
0x180036967  pop     rbp
0x180036968  retn
0x180036969  mov     r8, rdi
0x18003696c  lea     rdx, [rsp+270h+var_240]
0x180036971  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180036976  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003697b  mov     ebx, eax
0x18003697d  test    eax, eax
0x18003697f  jns     short loc_18003692D
0x180036981  mov     edx, 137h
0x180036986  jmp     loc_1800368FF
```
