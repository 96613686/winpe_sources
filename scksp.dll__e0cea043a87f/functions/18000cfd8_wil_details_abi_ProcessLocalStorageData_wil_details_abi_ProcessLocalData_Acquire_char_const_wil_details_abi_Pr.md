# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000cfd8`
- end: `0x18000d13a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e5b0`

## callees

- `0x18000cc00`
- `0x18000cc1c`
- `0x18000cfd8`
- `0x18000e3c8`
- `0x18000f2cc`
- `0x180010c8c`
- `0x18001147c`
- `0x180011900`
- `0x18001232c`
- `0x18001265c`
- `0x18003c240`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d010`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d010`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d055`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000d055`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18000cfd8  mov     [rsp-8+arg_10], rbx
0x18000cfdd  mov     [rsp-8+arg_18], rdi
0x18000cfe2  push    rbp
0x18000cfe3  lea     rbp, [rsp-170h]
0x18000cfeb  sub     rsp, 270h
0x18000cff2  mov     rax, cs:__security_cookie
0x18000cff9  xor     rax, rsp
0x18000cffc  mov     [rbp+170h+var_10], rax
0x18000d003  mov     rdi, rdx
0x18000d006  mov     rbx, rcx
0x18000d009  mov     qword ptr [rdx], 0
0x18000d010  call    cs:__imp_GetCurrentProcessId
0x18000d016  mov     r9d, eax
0x18000d019  mov     [rsp+270h+var_248], rbx
0x18000d01e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000d026  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000d02d  mov     edx, 104h; unsigned __int64
0x18000d032  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d037  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d03c  mov     [rsp+270h+var_240], 0
0x18000d045  mov     r9d, 1F0001h; dwDesiredAccess
0x18000d04b  xor     r8d, r8d; dwFlags
0x18000d04e  lea     rdx, [rsp+270h+Name]; lpName
0x18000d053  xor     ecx, ecx; lpMutexAttributes
0x18000d055  call    cs:__imp_CreateMutexExW
0x18000d05b  mov     rdx, rax
0x18000d05e  lea     rcx, [rsp+270h+var_240]
0x18000d063  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000d068  cmp     [rsp+270h+var_240], 0
0x18000d06e  jnz     short loc_18000D079
0x18000d070  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d075  mov     ebx, eax
0x18000d077  jmp     short loc_18000D0E7
0x18000d079  lea     rdx, [rsp+270h+var_238]
0x18000d07e  lea     rcx, [rsp+270h+var_240]
0x18000d083  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000d088  nop
0x18000d089  mov     [rsp+270h+var_230], 0
0x18000d092  lea     rdx, [rsp+270h+var_230]; void **
0x18000d097  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d09c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000d0a1  mov     ebx, eax
0x18000d0a3  test    eax, eax
0x18000d0a5  jns     short loc_18000D0C8
0x18000d0a7  mov     edx, 12Eh; void *
0x18000d0ac  mov     r9d, eax; char *
0x18000d0af  mov     rcx, [rbp+178h]; this
0x18000d0b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d0bb  nop
0x18000d0bc  lea     rcx, [rsp+270h+var_238]
0x18000d0c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d0c6  jmp     short loc_18000D0E7
0x18000d0c8  mov     rcx, [rsp+270h+var_230]
0x18000d0cd  test    rcx, rcx
0x18000d0d0  jz      short loc_18000D117
0x18000d0d2  mov     [rdi], rcx
0x18000d0d5  mov     eax, [rcx]
0x18000d0d7  inc     eax
0x18000d0d9  mov     [rcx], eax
0x18000d0db  lea     rcx, [rsp+270h+var_238]
0x18000d0e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d0e5  xor     ebx, ebx
0x18000d0e7  lea     rcx, [rsp+270h+var_240]
0x18000d0ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d0f1  mov     eax, ebx
0x18000d0f3  mov     rcx, [rbp+170h+var_10]
0x18000d0fa  xor     rcx, rsp; StackCookie
0x18000d0fd  call    __security_check_cookie
0x18000d102  lea     r11, [rsp+270h+var_s0]
0x18000d10a  mov     rbx, [r11+20h]
0x18000d10e  mov     rdi, [r11+28h]
0x18000d112  mov     rsp, r11
0x18000d115  pop     rbp
0x18000d116  retn
0x18000d117  mov     r8, rdi
0x18000d11a  lea     rdx, [rsp+270h+var_240]
0x18000d11f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000d124  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000d129  mov     ebx, eax
0x18000d12b  test    eax, eax
0x18000d12d  jns     short loc_18000D0DB
0x18000d12f  mov     edx, 137h
0x18000d134  jmp     loc_18000D0AC
```
