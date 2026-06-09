# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001da3c`
- end: `0x18001dba2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ec48`

## callees

- `0x180005df4`
- `0x18001d6f8`
- `0x18001d714`
- `0x18001da3c`
- `0x18001ea60`
- `0x18001f734`
- `0x180020da0`
- `0x18002182c`
- `0x180022310`
- `0x1800225fc`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001da74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001da74`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dab9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dab9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18001da3c  mov     [rsp-8+arg_10], rbx
0x18001da41  mov     [rsp-8+arg_18], rdi
0x18001da46  push    rbp
0x18001da47  lea     rbp, [rsp-170h]
0x18001da4f  sub     rsp, 270h
0x18001da56  mov     rax, cs:__security_cookie
0x18001da5d  xor     rax, rsp
0x18001da60  mov     [rbp+170h+var_10], rax
0x18001da67  mov     rdi, rdx
0x18001da6a  mov     qword ptr [rdx], 0
0x18001da71  mov     rbx, rcx
0x18001da74  call    cs:__imp_GetCurrentProcessId
0x18001da7a  mov     [rsp+270h+var_248], rbx
0x18001da7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001da86  mov     r9d, eax
0x18001da89  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001da91  mov     edx, 104h; unsigned __int64
0x18001da96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001da9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001daa0  mov     r9d, 1F0001h; dwDesiredAccess
0x18001daa6  mov     [rsp+270h+var_240], 0
0x18001daaf  xor     r8d, r8d; dwFlags
0x18001dab2  lea     rdx, [rsp+270h+Name]; lpName
0x18001dab7  xor     ecx, ecx; lpMutexAttributes
0x18001dab9  call    cs:__imp_CreateMutexExW
0x18001dabf  mov     rdx, rax
0x18001dac2  lea     rcx, [rsp+270h+var_240]
0x18001dac7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001dacc  cmp     [rsp+270h+var_240], 0
0x18001dad2  jnz     short loc_18001DADD
0x18001dad4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001dad9  mov     ebx, eax
0x18001dadb  jmp     short loc_18001DB50
0x18001dadd  lea     rdx, [rsp+270h+var_238]
0x18001dae2  lea     rcx, [rsp+270h+var_240]
0x18001dae7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001daec  lea     rdx, [rsp+270h+var_230]; void **
0x18001daf1  mov     [rsp+270h+var_230], 0
0x18001dafa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001daff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001db04  mov     ebx, eax
0x18001db06  test    eax, eax
0x18001db08  jns     short loc_18001DB31
0x18001db0a  mov     edx, 12Eh; void *
0x18001db0f  mov     rcx, [rbp+178h]; this
0x18001db16  lea     r8, aWil; "wil"
0x18001db1d  mov     r9d, eax; char *
0x18001db20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db25  lea     rcx, [rsp+270h+var_238]
0x18001db2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db2f  jmp     short loc_18001DB50
0x18001db31  mov     rcx, [rsp+270h+var_230]
0x18001db36  test    rcx, rcx
0x18001db39  jz      short loc_18001DB80
0x18001db3b  mov     [rdi], rcx
0x18001db3e  mov     eax, [rcx]
0x18001db40  inc     eax
0x18001db42  mov     [rcx], eax
0x18001db44  lea     rcx, [rsp+270h+var_238]
0x18001db49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db4e  xor     ebx, ebx
0x18001db50  lea     rcx, [rsp+270h+var_240]
0x18001db55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db5a  mov     eax, ebx
0x18001db5c  mov     rcx, [rbp+170h+var_10]
0x18001db63  xor     rcx, rsp; StackCookie
0x18001db66  call    __security_check_cookie
0x18001db6b  lea     r11, [rsp+270h+var_s0]
0x18001db73  mov     rbx, [r11+20h]
0x18001db77  mov     rdi, [r11+28h]
0x18001db7b  mov     rsp, r11
0x18001db7e  pop     rbp
0x18001db7f  retn
0x18001db80  mov     r8, rdi
0x18001db83  lea     rdx, [rsp+270h+var_240]
0x18001db88  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001db8d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001db92  mov     ebx, eax
0x18001db94  test    eax, eax
0x18001db96  jns     short loc_18001DB44
0x18001db98  mov     edx, 137h
0x18001db9d  jmp     loc_18001DB0F
```
