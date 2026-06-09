# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a47c`
- end: `0x18000a5e2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180003074`

## callees

- `0x180004fdc`
- `0x180005130`
- `0x180005cc0`
- `0x1800078b0`
- `0x1800078cc`
- `0x1800095c0`
- `0x180009728`
- `0x180009ad8`
- `0x180009bd4`
- `0x18000a47c`
- `0x18000ac00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a4f9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a4f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a4b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a4b4`

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
  HANDLE v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
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
      &v12);
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
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
0x18000a47c  mov     [rsp-8+arg_10], rbx
0x18000a481  mov     [rsp-8+arg_18], rdi
0x18000a486  push    rbp
0x18000a487  lea     rbp, [rsp-170h]
0x18000a48f  sub     rsp, 270h
0x18000a496  mov     rax, cs:__security_cookie
0x18000a49d  xor     rax, rsp
0x18000a4a0  mov     [rbp+170h+var_10], rax
0x18000a4a7  mov     rdi, rdx
0x18000a4aa  mov     qword ptr [rdx], 0
0x18000a4b1  mov     rbx, rcx
0x18000a4b4  call    cs:__imp_GetCurrentProcessId
0x18000a4ba  mov     [rsp+270h+var_248], rbx
0x18000a4bf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a4c6  mov     r9d, eax
0x18000a4c9  mov     [rsp+270h+var_250], 130h; int
0x18000a4d1  mov     edx, 104h; unsigned __int64
0x18000a4d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a4db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a4e0  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a4e6  mov     [rsp+270h+var_240], 0
0x18000a4ef  xor     r8d, r8d; dwFlags
0x18000a4f2  lea     rdx, [rsp+270h+Name]; lpName
0x18000a4f7  xor     ecx, ecx; lpMutexAttributes
0x18000a4f9  call    cs:__imp_CreateMutexExW
0x18000a4ff  mov     rdx, rax
0x18000a502  lea     rcx, [rsp+270h+var_240]
0x18000a507  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a50c  cmp     [rsp+270h+var_240], 0
0x18000a512  jnz     short loc_18000A51D
0x18000a514  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a519  mov     ebx, eax
0x18000a51b  jmp     short loc_18000A590
0x18000a51d  lea     rdx, [rsp+270h+var_238]
0x18000a522  lea     rcx, [rsp+270h+var_240]
0x18000a527  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a52c  lea     rdx, [rsp+270h+var_230]; void **
0x18000a531  mov     [rsp+270h+var_230], 0
0x18000a53a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a53f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a544  mov     ebx, eax
0x18000a546  test    eax, eax
0x18000a548  jns     short loc_18000A571
0x18000a54a  mov     edx, 12Eh; void *
0x18000a54f  mov     rcx, [rbp+178h]; this
0x18000a556  lea     r8, aWil; "wil"
0x18000a55d  mov     r9d, eax; char *
0x18000a560  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a565  lea     rcx, [rsp+270h+var_238]
0x18000a56a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a56f  jmp     short loc_18000A590
0x18000a571  mov     rcx, [rsp+270h+var_230]
0x18000a576  test    rcx, rcx
0x18000a579  jz      short loc_18000A5C0
0x18000a57b  mov     [rdi], rcx
0x18000a57e  mov     eax, [rcx]
0x18000a580  inc     eax
0x18000a582  mov     [rcx], eax
0x18000a584  lea     rcx, [rsp+270h+var_238]
0x18000a589  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a58e  xor     ebx, ebx
0x18000a590  lea     rcx, [rsp+270h+var_240]
0x18000a595  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a59a  mov     eax, ebx
0x18000a59c  mov     rcx, [rbp+170h+var_10]
0x18000a5a3  xor     rcx, rsp; StackCookie
0x18000a5a6  call    __security_check_cookie
0x18000a5ab  lea     r11, [rsp+270h+var_s0]
0x18000a5b3  mov     rbx, [r11+20h]
0x18000a5b7  mov     rdi, [r11+28h]
0x18000a5bb  mov     rsp, r11
0x18000a5be  pop     rbp
0x18000a5bf  retn
0x18000a5c0  mov     r8, rdi
0x18000a5c3  lea     rdx, [rsp+270h+var_240]
0x18000a5c8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a5cd  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a5d2  mov     ebx, eax
0x18000a5d4  test    eax, eax
0x18000a5d6  jns     short loc_18000A584
0x18000a5d8  mov     edx, 137h
0x18000a5dd  jmp     loc_18000A54F
```
