# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003fbec`
- end: `0x18003fd58`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180041540`

## callees

- `0x180028014`
- `0x18003c374`
- `0x18003cb60`
- `0x18003f2fc`
- `0x18003f31c`
- `0x18003fbec`
- `0x180042d20`
- `0x180045100`
- `0x180046064`
- `0x180046f54`
- `0x180047100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fc6f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fc6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fc24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fc24`

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
0x18003fbec  mov     [rsp-8+arg_10], rbx
0x18003fbf1  mov     [rsp-8+arg_18], rdi
0x18003fbf6  push    rbp
0x18003fbf7  lea     rbp, [rsp-170h]
0x18003fbff  sub     rsp, 270h
0x18003fc06  mov     rax, cs:__security_cookie
0x18003fc0d  xor     rax, rsp
0x18003fc10  mov     [rbp+170h+var_10], rax
0x18003fc17  mov     rdi, rdx
0x18003fc1a  mov     qword ptr [rdx], 0
0x18003fc21  mov     rbx, rcx
0x18003fc24  call    cs:__imp_GetCurrentProcessId
0x18003fc2b  nop     dword ptr [rax+rax+00h]
0x18003fc30  mov     [rsp+270h+var_248], rbx
0x18003fc35  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003fc3c  mov     r9d, eax
0x18003fc3f  mov     [rsp+270h+var_250], 130h; int
0x18003fc47  mov     edx, 104h; unsigned __int64
0x18003fc4c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fc51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fc56  mov     r9d, 1F0001h; dwDesiredAccess
0x18003fc5c  mov     [rsp+270h+var_240], 0
0x18003fc65  xor     r8d, r8d; dwFlags
0x18003fc68  lea     rdx, [rsp+270h+Name]; lpName
0x18003fc6d  xor     ecx, ecx; lpMutexAttributes
0x18003fc6f  call    cs:__imp_CreateMutexExW
0x18003fc76  nop     dword ptr [rax+rax+00h]
0x18003fc7b  mov     rdx, rax
0x18003fc7e  lea     rcx, [rsp+270h+var_240]
0x18003fc83  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003fc88  cmp     [rsp+270h+var_240], 0
0x18003fc8e  jnz     short loc_18003FC99
0x18003fc90  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003fc95  mov     ebx, eax
0x18003fc97  jmp     short loc_18003FD05
0x18003fc99  lea     rdx, [rsp+270h+var_238]
0x18003fc9e  lea     rcx, [rsp+270h+var_240]
0x18003fca3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003fca8  lea     rdx, [rsp+270h+var_230]; void **
0x18003fcad  mov     [rsp+270h+var_230], 0
0x18003fcb6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fcbb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003fcc0  mov     ebx, eax
0x18003fcc2  test    eax, eax
0x18003fcc4  jns     short loc_18003FCE6
0x18003fcc6  mov     edx, 12Eh; void *
0x18003fccb  mov     rcx, [rbp+178h]; this
0x18003fcd2  mov     r9d, eax; char *
0x18003fcd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fcda  lea     rcx, [rsp+270h+var_238]
0x18003fcdf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fce4  jmp     short loc_18003FD05
0x18003fce6  mov     rcx, [rsp+270h+var_230]
0x18003fceb  test    rcx, rcx
0x18003fcee  jz      short loc_18003FD36
0x18003fcf0  mov     [rdi], rcx
0x18003fcf3  mov     eax, [rcx]
0x18003fcf5  inc     eax
0x18003fcf7  mov     [rcx], eax
0x18003fcf9  lea     rcx, [rsp+270h+var_238]
0x18003fcfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fd03  xor     ebx, ebx
0x18003fd05  lea     rcx, [rsp+270h+var_240]
0x18003fd0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fd0f  mov     eax, ebx
0x18003fd11  mov     rcx, [rbp+170h+var_10]
0x18003fd18  xor     rcx, rsp; StackCookie
0x18003fd1b  call    __security_check_cookie
0x18003fd20  lea     r11, [rsp+270h+var_s0]
0x18003fd28  mov     rbx, [r11+20h]
0x18003fd2c  mov     rdi, [r11+28h]
0x18003fd30  mov     rsp, r11
0x18003fd33  pop     rbp
0x18003fd34  retn
0x18003fd36  mov     r8, rdi
0x18003fd39  lea     rdx, [rsp+270h+var_240]
0x18003fd3e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fd43  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003fd48  mov     ebx, eax
0x18003fd4a  test    eax, eax
0x18003fd4c  jns     short loc_18003FCF9
0x18003fd4e  mov     edx, 137h
0x18003fd53  jmp     loc_18003FCCB
```
