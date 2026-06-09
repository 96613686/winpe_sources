# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c5a8`
- end: `0x18000c71d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d498`

## callees

- `0x180007ab4`
- `0x180008a90`
- `0x18000a61c`
- `0x18000bfb4`
- `0x18000bfd4`
- `0x18000c5a8`
- `0x18000e39c`
- `0x18000fdc0`
- `0x180010544`
- `0x180010ce4`
- `0x180010f48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c62b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c62b`

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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18000c5a8  mov     [rsp-8+arg_10], rbx
0x18000c5ad  mov     [rsp-8+arg_18], rdi
0x18000c5b2  push    rbp
0x18000c5b3  lea     rbp, [rsp-170h]
0x18000c5bb  sub     rsp, 270h
0x18000c5c2  mov     rax, cs:__security_cookie
0x18000c5c9  xor     rax, rsp
0x18000c5cc  mov     [rbp+170h+var_10], rax
0x18000c5d3  mov     rdi, rdx
0x18000c5d6  mov     qword ptr [rdx], 0
0x18000c5dd  mov     rbx, rcx
0x18000c5e0  call    cs:__imp_GetCurrentProcessId
0x18000c5e7  nop     dword ptr [rax+rax+00h]
0x18000c5ec  mov     [rsp+270h+var_248], rbx
0x18000c5f1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c5f8  mov     r9d, eax
0x18000c5fb  mov     [rsp+270h+var_250], 130h; int
0x18000c603  mov     edx, 104h; unsigned __int64
0x18000c608  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c60d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c612  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c618  mov     [rsp+270h+var_240], 0
0x18000c621  xor     r8d, r8d; dwFlags
0x18000c624  lea     rdx, [rsp+270h+Name]; lpName
0x18000c629  xor     ecx, ecx; lpMutexAttributes
0x18000c62b  call    cs:__imp_CreateMutexExW
0x18000c632  nop     dword ptr [rax+rax+00h]
0x18000c637  mov     rdx, rax
0x18000c63a  lea     rcx, [rsp+270h+var_240]
0x18000c63f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c644  cmp     [rsp+270h+var_240], 0
0x18000c64a  jnz     short loc_18000C655
0x18000c64c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c651  mov     ebx, eax
0x18000c653  jmp     short loc_18000C6CA
0x18000c655  lea     rdx, [rsp+270h+var_238]
0x18000c65a  mov     [rsp+270h+var_238], 0
0x18000c663  lea     rcx, [rsp+270h+var_240]
0x18000c668  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000c66d  lea     rdx, [rsp+270h+var_230]; void **
0x18000c672  mov     [rsp+270h+var_230], 0
0x18000c67b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c680  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000c685  mov     ebx, eax
0x18000c687  test    eax, eax
0x18000c689  jns     short loc_18000C6AB
0x18000c68b  mov     edx, 12Eh; void *
0x18000c690  mov     rcx, [rbp+178h]; this
0x18000c697  mov     r9d, eax; char *
0x18000c69a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c69f  lea     rcx, [rsp+270h+var_238]
0x18000c6a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6a9  jmp     short loc_18000C6CA
0x18000c6ab  mov     rcx, [rsp+270h+var_230]
0x18000c6b0  test    rcx, rcx
0x18000c6b3  jz      short loc_18000C6FB
0x18000c6b5  mov     [rdi], rcx
0x18000c6b8  mov     eax, [rcx]
0x18000c6ba  inc     eax
0x18000c6bc  mov     [rcx], eax
0x18000c6be  lea     rcx, [rsp+270h+var_238]
0x18000c6c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6c8  xor     ebx, ebx
0x18000c6ca  lea     rcx, [rsp+270h+var_240]
0x18000c6cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6d4  mov     eax, ebx
0x18000c6d6  mov     rcx, [rbp+170h+var_10]
0x18000c6dd  xor     rcx, rsp; StackCookie
0x18000c6e0  call    __security_check_cookie
0x18000c6e5  lea     r11, [rsp+270h+var_s0]
0x18000c6ed  mov     rbx, [r11+20h]
0x18000c6f1  mov     rdi, [r11+28h]
0x18000c6f5  mov     rsp, r11
0x18000c6f8  pop     rbp
0x18000c6f9  retn
0x18000c6fb  mov     r8, rdi
0x18000c6fe  lea     rdx, [rsp+270h+var_240]
0x18000c703  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000c708  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c70d  mov     ebx, eax
0x18000c70f  test    eax, eax
0x18000c711  jns     short loc_18000C6BE
0x18000c713  mov     edx, 137h
0x18000c718  jmp     loc_18000C690
```
