# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180028da4`
- end: `0x180028f03`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180029104`

## callees

- `0x180026148`
- `0x180026580`
- `0x180026a30`
- `0x180028aa8`
- `0x180028ac4`
- `0x180028da4`
- `0x18002a41c`
- `0x18002b410`
- `0x18002bba8`
- `0x18002c3c4`
- `0x18002c500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028e21`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028e21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028ddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028ddc`

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
0x180028da4  mov     [rsp-8+arg_10], rbx
0x180028da9  mov     [rsp-8+arg_18], rdi
0x180028dae  push    rbp
0x180028daf  lea     rbp, [rsp-170h]
0x180028db7  sub     rsp, 270h
0x180028dbe  mov     rax, cs:__security_cookie
0x180028dc5  xor     rax, rsp
0x180028dc8  mov     [rbp+170h+var_10], rax
0x180028dcf  mov     rdi, rdx
0x180028dd2  mov     qword ptr [rdx], 0
0x180028dd9  mov     rbx, rcx
0x180028ddc  call    cs:__imp_GetCurrentProcessId
0x180028de2  mov     [rsp+270h+var_248], rbx
0x180028de7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180028dee  mov     r9d, eax
0x180028df1  mov     [rsp+270h+var_250], 130h; int
0x180028df9  mov     edx, 104h; unsigned __int64
0x180028dfe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028e03  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028e08  mov     r9d, 1F0001h; dwDesiredAccess
0x180028e0e  mov     [rsp+270h+var_240], 0
0x180028e17  xor     r8d, r8d; dwFlags
0x180028e1a  lea     rdx, [rsp+270h+Name]; lpName
0x180028e1f  xor     ecx, ecx; lpMutexAttributes
0x180028e21  call    cs:__imp_CreateMutexExW
0x180028e27  mov     rdx, rax
0x180028e2a  lea     rcx, [rsp+270h+var_240]
0x180028e2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028e34  cmp     [rsp+270h+var_240], 0
0x180028e3a  jnz     short loc_180028E45
0x180028e3c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028e41  mov     ebx, eax
0x180028e43  jmp     short loc_180028EB1
0x180028e45  lea     rdx, [rsp+270h+var_238]
0x180028e4a  lea     rcx, [rsp+270h+var_240]
0x180028e4f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180028e54  lea     rdx, [rsp+270h+var_230]; void **
0x180028e59  mov     [rsp+270h+var_230], 0
0x180028e62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028e67  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180028e6c  mov     ebx, eax
0x180028e6e  test    eax, eax
0x180028e70  jns     short loc_180028E92
0x180028e72  mov     edx, 12Eh; void *
0x180028e77  mov     rcx, [rbp+178h]; this
0x180028e7e  mov     r9d, eax; char *
0x180028e81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028e86  lea     rcx, [rsp+270h+var_238]
0x180028e8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028e90  jmp     short loc_180028EB1
0x180028e92  mov     rcx, [rsp+270h+var_230]
0x180028e97  test    rcx, rcx
0x180028e9a  jz      short loc_180028EE1
0x180028e9c  mov     [rdi], rcx
0x180028e9f  mov     eax, [rcx]
0x180028ea1  inc     eax
0x180028ea3  mov     [rcx], eax
0x180028ea5  lea     rcx, [rsp+270h+var_238]
0x180028eaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028eaf  xor     ebx, ebx
0x180028eb1  lea     rcx, [rsp+270h+var_240]
0x180028eb6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028ebb  mov     eax, ebx
0x180028ebd  mov     rcx, [rbp+170h+var_10]
0x180028ec4  xor     rcx, rsp; StackCookie
0x180028ec7  call    __security_check_cookie
0x180028ecc  lea     r11, [rsp+270h+var_s0]
0x180028ed4  mov     rbx, [r11+20h]
0x180028ed8  mov     rdi, [r11+28h]
0x180028edc  mov     rsp, r11
0x180028edf  pop     rbp
0x180028ee0  retn
0x180028ee1  mov     r8, rdi
0x180028ee4  lea     rdx, [rsp+270h+var_240]
0x180028ee9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028eee  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180028ef3  mov     ebx, eax
0x180028ef5  test    eax, eax
0x180028ef7  jns     short loc_180028EA5
0x180028ef9  mov     edx, 137h
0x180028efe  jmp     loc_180028E77
```
