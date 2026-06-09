# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001dba8`
- end: `0x18001dd0e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001eca8`

## callees

- `0x180005df4`
- `0x18001d6f8`
- `0x18001d714`
- `0x18001dba8`
- `0x18001ea60`
- `0x18001f868`
- `0x180020da0`
- `0x18002182c`
- `0x180022310`
- `0x1800225fc`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dbe0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dbe0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dc25`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dc25`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001dba8  mov     [rsp-8+arg_10], rbx
0x18001dbad  mov     [rsp-8+arg_18], rdi
0x18001dbb2  push    rbp
0x18001dbb3  lea     rbp, [rsp-170h]
0x18001dbbb  sub     rsp, 270h
0x18001dbc2  mov     rax, cs:__security_cookie
0x18001dbc9  xor     rax, rsp
0x18001dbcc  mov     [rbp+170h+var_10], rax
0x18001dbd3  mov     rdi, rdx
0x18001dbd6  mov     qword ptr [rdx], 0
0x18001dbdd  mov     rbx, rcx
0x18001dbe0  call    cs:__imp_GetCurrentProcessId
0x18001dbe6  mov     [rsp+270h+var_248], rbx
0x18001dbeb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001dbf2  mov     r9d, eax
0x18001dbf5  mov     [rsp+270h+var_250], 130h; int
0x18001dbfd  mov     edx, 104h; unsigned __int64
0x18001dc02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dc07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dc0c  mov     r9d, 1F0001h; dwDesiredAccess
0x18001dc12  mov     [rsp+270h+var_240], 0
0x18001dc1b  xor     r8d, r8d; dwFlags
0x18001dc1e  lea     rdx, [rsp+270h+Name]; lpName
0x18001dc23  xor     ecx, ecx; lpMutexAttributes
0x18001dc25  call    cs:__imp_CreateMutexExW
0x18001dc2b  mov     rdx, rax
0x18001dc2e  lea     rcx, [rsp+270h+var_240]
0x18001dc33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001dc38  cmp     [rsp+270h+var_240], 0
0x18001dc3e  jnz     short loc_18001DC49
0x18001dc40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001dc45  mov     ebx, eax
0x18001dc47  jmp     short loc_18001DCBC
0x18001dc49  lea     rdx, [rsp+270h+var_238]
0x18001dc4e  lea     rcx, [rsp+270h+var_240]
0x18001dc53  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001dc58  lea     rdx, [rsp+270h+var_230]; void **
0x18001dc5d  mov     [rsp+270h+var_230], 0
0x18001dc66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dc6b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001dc70  mov     ebx, eax
0x18001dc72  test    eax, eax
0x18001dc74  jns     short loc_18001DC9D
0x18001dc76  mov     edx, 12Eh; void *
0x18001dc7b  mov     rcx, [rbp+178h]; this
0x18001dc82  lea     r8, aWil; "wil"
0x18001dc89  mov     r9d, eax; char *
0x18001dc8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dc91  lea     rcx, [rsp+270h+var_238]
0x18001dc96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dc9b  jmp     short loc_18001DCBC
0x18001dc9d  mov     rcx, [rsp+270h+var_230]
0x18001dca2  test    rcx, rcx
0x18001dca5  jz      short loc_18001DCEC
0x18001dca7  mov     [rdi], rcx
0x18001dcaa  mov     eax, [rcx]
0x18001dcac  inc     eax
0x18001dcae  mov     [rcx], eax
0x18001dcb0  lea     rcx, [rsp+270h+var_238]
0x18001dcb5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dcba  xor     ebx, ebx
0x18001dcbc  lea     rcx, [rsp+270h+var_240]
0x18001dcc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dcc6  mov     eax, ebx
0x18001dcc8  mov     rcx, [rbp+170h+var_10]
0x18001dccf  xor     rcx, rsp; StackCookie
0x18001dcd2  call    __security_check_cookie
0x18001dcd7  lea     r11, [rsp+270h+var_s0]
0x18001dcdf  mov     rbx, [r11+20h]
0x18001dce3  mov     rdi, [r11+28h]
0x18001dce7  mov     rsp, r11
0x18001dcea  pop     rbp
0x18001dceb  retn
0x18001dcec  mov     r8, rdi
0x18001dcef  lea     rdx, [rsp+270h+var_240]
0x18001dcf4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dcf9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001dcfe  mov     ebx, eax
0x18001dd00  test    eax, eax
0x18001dd02  jns     short loc_18001DCB0
0x18001dd04  mov     edx, 137h
0x18001dd09  jmp     loc_18001DC7B
```
