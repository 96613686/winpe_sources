# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023738`
- end: `0x180023897`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024854`

## callees

- `0x18001006c`
- `0x1800121e0`
- `0x18001233c`
- `0x180012394`
- `0x180022f4c`
- `0x180022f68`
- `0x180023738`
- `0x180026968`
- `0x180028324`
- `0x180029af8`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023770`
- `KERNEL32!CreateMutexExW` at `0x1800237b5`
- `KERNEL32!CreateMutexExW` at `0x1800237b5`

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
0x180023738  mov     [rsp-8+arg_10], rbx
0x18002373d  mov     [rsp-8+arg_18], rdi
0x180023742  push    rbp
0x180023743  lea     rbp, [rsp-170h]
0x18002374b  sub     rsp, 270h
0x180023752  mov     rax, cs:__security_cookie
0x180023759  xor     rax, rsp
0x18002375c  mov     [rbp+170h+var_10], rax
0x180023763  mov     rdi, rdx
0x180023766  mov     qword ptr [rdx], 0
0x18002376d  mov     rbx, rcx
0x180023770  call    cs:__imp_GetCurrentProcessId
0x180023776  mov     [rsp+270h+var_248], rbx
0x18002377b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023782  mov     r9d, eax
0x180023785  mov     [rsp+270h+var_250], 130h; int
0x18002378d  mov     edx, 104h; unsigned __int64
0x180023792  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023797  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002379c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800237a2  mov     [rsp+270h+var_240], 0
0x1800237ab  xor     r8d, r8d; dwFlags
0x1800237ae  lea     rdx, [rsp+270h+Name]; lpName
0x1800237b3  xor     ecx, ecx; lpMutexAttributes
0x1800237b5  call    cs:__imp_CreateMutexExW
0x1800237bb  mov     rdx, rax
0x1800237be  lea     rcx, [rsp+270h+var_240]
0x1800237c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800237c8  cmp     [rsp+270h+var_240], 0
0x1800237ce  jnz     short loc_1800237D9
0x1800237d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800237d5  mov     ebx, eax
0x1800237d7  jmp     short loc_180023845
0x1800237d9  lea     rdx, [rsp+270h+var_238]
0x1800237de  lea     rcx, [rsp+270h+var_240]
0x1800237e3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800237e8  lea     rdx, [rsp+270h+var_230]; void **
0x1800237ed  mov     [rsp+270h+var_230], 0
0x1800237f6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800237fb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023800  mov     ebx, eax
0x180023802  test    eax, eax
0x180023804  jns     short loc_180023826
0x180023806  mov     edx, 12Eh; void *
0x18002380b  mov     rcx, [rbp+178h]; this
0x180023812  mov     r9d, eax; char *
0x180023815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002381a  lea     rcx, [rsp+270h+var_238]
0x18002381f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023824  jmp     short loc_180023845
0x180023826  mov     rcx, [rsp+270h+var_230]
0x18002382b  test    rcx, rcx
0x18002382e  jz      short loc_180023875
0x180023830  mov     [rdi], rcx
0x180023833  mov     eax, [rcx]
0x180023835  inc     eax
0x180023837  mov     [rcx], eax
0x180023839  lea     rcx, [rsp+270h+var_238]
0x18002383e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023843  xor     ebx, ebx
0x180023845  lea     rcx, [rsp+270h+var_240]
0x18002384a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002384f  mov     eax, ebx
0x180023851  mov     rcx, [rbp+170h+var_10]
0x180023858  xor     rcx, rsp; StackCookie
0x18002385b  call    __security_check_cookie
0x180023860  lea     r11, [rsp+270h+var_s0]
0x180023868  mov     rbx, [r11+20h]
0x18002386c  mov     rdi, [r11+28h]
0x180023870  mov     rsp, r11
0x180023873  pop     rbp
0x180023874  retn
0x180023875  mov     r8, rdi
0x180023878  lea     rdx, [rsp+270h+var_240]
0x18002387d  lea     rcx, [rsp+270h+Name]
0x180023882  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023887  mov     ebx, eax
0x180023889  test    eax, eax
0x18002388b  jns     short loc_180023839
0x18002388d  mov     edx, 137h
0x180023892  jmp     loc_18002380B
```
