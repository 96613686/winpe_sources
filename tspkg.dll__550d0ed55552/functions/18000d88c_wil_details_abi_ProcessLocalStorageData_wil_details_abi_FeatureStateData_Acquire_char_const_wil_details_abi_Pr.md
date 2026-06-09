# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000d88c`
- end: `0x18000d9eb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e508`

## callees

- `0x18000a858`
- `0x18000a9b4`
- `0x18000aa00`
- `0x18000b550`
- `0x18000d554`
- `0x18000d570`
- `0x18000d88c`
- `0x18000fefc`
- `0x180010190`
- `0x180010934`
- `0x180010b24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d909`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d909`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d8c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d8c4`

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
0x18000d88c  mov     [rsp-8+arg_10], rbx
0x18000d891  mov     [rsp-8+arg_18], rdi
0x18000d896  push    rbp
0x18000d897  lea     rbp, [rsp-170h]
0x18000d89f  sub     rsp, 270h
0x18000d8a6  mov     rax, cs:__security_cookie
0x18000d8ad  xor     rax, rsp
0x18000d8b0  mov     [rbp+170h+var_10], rax
0x18000d8b7  mov     rdi, rdx
0x18000d8ba  mov     qword ptr [rdx], 0
0x18000d8c1  mov     rbx, rcx
0x18000d8c4  call    cs:__imp_GetCurrentProcessId
0x18000d8ca  mov     [rsp+270h+var_248], rbx
0x18000d8cf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d8d6  mov     r9d, eax
0x18000d8d9  mov     [rsp+270h+var_250], 130h; int
0x18000d8e1  mov     edx, 104h; unsigned __int64
0x18000d8e6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d8eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d8f0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d8f6  mov     [rsp+270h+var_240], 0
0x18000d8ff  xor     r8d, r8d; dwFlags
0x18000d902  lea     rdx, [rsp+270h+Name]; lpName
0x18000d907  xor     ecx, ecx; lpMutexAttributes
0x18000d909  call    cs:__imp_CreateMutexExW
0x18000d90f  mov     rdx, rax
0x18000d912  lea     rcx, [rsp+270h+var_240]
0x18000d917  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000d91c  cmp     [rsp+270h+var_240], 0
0x18000d922  jnz     short loc_18000D92D
0x18000d924  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d929  mov     ebx, eax
0x18000d92b  jmp     short loc_18000D999
0x18000d92d  lea     rdx, [rsp+270h+var_238]
0x18000d932  lea     rcx, [rsp+270h+var_240]
0x18000d937  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000d93c  lea     rdx, [rsp+270h+var_230]; void **
0x18000d941  mov     [rsp+270h+var_230], 0
0x18000d94a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d94f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000d954  mov     ebx, eax
0x18000d956  test    eax, eax
0x18000d958  jns     short loc_18000D97A
0x18000d95a  mov     edx, 12Eh; void *
0x18000d95f  mov     rcx, [rbp+178h]; this
0x18000d966  mov     r9d, eax; char *
0x18000d969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d96e  lea     rcx, [rsp+270h+var_238]
0x18000d973  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d978  jmp     short loc_18000D999
0x18000d97a  mov     rcx, [rsp+270h+var_230]
0x18000d97f  test    rcx, rcx
0x18000d982  jz      short loc_18000D9C9
0x18000d984  mov     [rdi], rcx
0x18000d987  mov     eax, [rcx]
0x18000d989  inc     eax
0x18000d98b  mov     [rcx], eax
0x18000d98d  lea     rcx, [rsp+270h+var_238]
0x18000d992  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d997  xor     ebx, ebx
0x18000d999  lea     rcx, [rsp+270h+var_240]
0x18000d99e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d9a3  mov     eax, ebx
0x18000d9a5  mov     rcx, [rbp+170h+var_10]
0x18000d9ac  xor     rcx, rsp; StackCookie
0x18000d9af  call    __security_check_cookie
0x18000d9b4  lea     r11, [rsp+270h+var_s0]
0x18000d9bc  mov     rbx, [r11+20h]
0x18000d9c0  mov     rdi, [r11+28h]
0x18000d9c4  mov     rsp, r11
0x18000d9c7  pop     rbp
0x18000d9c8  retn
0x18000d9c9  mov     r8, rdi
0x18000d9cc  lea     rdx, [rsp+270h+var_240]
0x18000d9d1  lea     rcx, [rsp+270h+Name]
0x18000d9d6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d9db  mov     ebx, eax
0x18000d9dd  test    eax, eax
0x18000d9df  jns     short loc_18000D98D
0x18000d9e1  mov     edx, 137h
0x18000d9e6  jmp     loc_18000D95F
```
