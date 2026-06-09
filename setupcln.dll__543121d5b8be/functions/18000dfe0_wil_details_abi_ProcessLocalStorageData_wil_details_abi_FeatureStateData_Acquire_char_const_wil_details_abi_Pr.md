# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000dfe0`
- end: `0x18000e142`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000f03c`

## callees

- `0x180007f88`
- `0x18000d998`
- `0x18000d9b4`
- `0x18000dfe0`
- `0x18000ebb8`
- `0x18000fbbc`
- `0x180010cdc`
- `0x18001176c`
- `0x180011e44`
- `0x180012718`
- `0x1800131e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e05d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e05d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e018`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e018`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000dfe0  mov     [rsp-8+arg_10], rbx
0x18000dfe5  mov     [rsp-8+arg_18], rdi
0x18000dfea  push    rbp
0x18000dfeb  lea     rbp, [rsp-170h]
0x18000dff3  sub     rsp, 270h
0x18000dffa  mov     rax, cs:__security_cookie
0x18000e001  xor     rax, rsp
0x18000e004  mov     [rbp+170h+var_10], rax
0x18000e00b  mov     rdi, rdx
0x18000e00e  mov     rbx, rcx
0x18000e011  mov     qword ptr [rdx], 0
0x18000e018  call    cs:__imp_GetCurrentProcessId
0x18000e01e  mov     r9d, eax
0x18000e021  mov     [rsp+270h+var_248], rbx
0x18000e026  mov     [rsp+270h+var_250], 130h; int
0x18000e02e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000e035  mov     edx, 104h; unsigned __int64
0x18000e03a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e03f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e044  mov     [rsp+270h+var_240], 0
0x18000e04d  mov     r9d, 1F0001h; dwDesiredAccess
0x18000e053  xor     r8d, r8d; dwFlags
0x18000e056  lea     rdx, [rsp+270h+Name]; lpName
0x18000e05b  xor     ecx, ecx; lpMutexAttributes
0x18000e05d  call    cs:__imp_CreateMutexExW
0x18000e063  mov     rdx, rax
0x18000e066  lea     rcx, [rsp+270h+var_240]
0x18000e06b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e070  cmp     [rsp+270h+var_240], 0
0x18000e076  jnz     short loc_18000E081
0x18000e078  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e07d  mov     ebx, eax
0x18000e07f  jmp     short loc_18000E0EF
0x18000e081  lea     rdx, [rsp+270h+var_238]
0x18000e086  lea     rcx, [rsp+270h+var_240]
0x18000e08b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000e090  nop
0x18000e091  mov     [rsp+270h+var_230], 0
0x18000e09a  lea     rdx, [rsp+270h+var_230]; void **
0x18000e09f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e0a4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000e0a9  mov     ebx, eax
0x18000e0ab  test    eax, eax
0x18000e0ad  jns     short loc_18000E0D0
0x18000e0af  mov     edx, 12Eh; void *
0x18000e0b4  mov     r9d, eax; char *
0x18000e0b7  mov     rcx, [rbp+178h]; this
0x18000e0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0c3  nop
0x18000e0c4  lea     rcx, [rsp+270h+var_238]
0x18000e0c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0ce  jmp     short loc_18000E0EF
0x18000e0d0  mov     rcx, [rsp+270h+var_230]
0x18000e0d5  test    rcx, rcx
0x18000e0d8  jz      short loc_18000E11F
0x18000e0da  mov     [rdi], rcx
0x18000e0dd  mov     eax, [rcx]
0x18000e0df  inc     eax
0x18000e0e1  mov     [rcx], eax
0x18000e0e3  lea     rcx, [rsp+270h+var_238]
0x18000e0e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0ed  xor     ebx, ebx
0x18000e0ef  lea     rcx, [rsp+270h+var_240]
0x18000e0f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0f9  mov     eax, ebx
0x18000e0fb  mov     rcx, [rbp+170h+var_10]
0x18000e102  xor     rcx, rsp; StackCookie
0x18000e105  call    __security_check_cookie
0x18000e10a  lea     r11, [rsp+270h+var_s0]
0x18000e112  mov     rbx, [r11+20h]
0x18000e116  mov     rdi, [r11+28h]
0x18000e11a  mov     rsp, r11
0x18000e11d  pop     rbp
0x18000e11e  retn
0x18000e11f  mov     r8, rdi
0x18000e122  lea     rdx, [rsp+270h+var_240]
0x18000e127  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e12c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000e131  mov     ebx, eax
0x18000e133  test    eax, eax
0x18000e135  jns     short loc_18000E0E3
0x18000e137  mov     edx, 137h
0x18000e13c  jmp     loc_18000E0B4
```
