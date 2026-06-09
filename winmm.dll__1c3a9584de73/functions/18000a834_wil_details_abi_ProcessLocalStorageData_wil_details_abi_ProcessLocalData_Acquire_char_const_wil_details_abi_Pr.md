# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a834`
- end: `0x18000a996`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180017d10`

## callees

- `0x1800087ac`
- `0x180008a9c`
- `0x180009fd8`
- `0x18000a3b0`
- `0x18000a834`
- `0x18000a9a8`
- `0x18000a9c4`
- `0x18000a9f8`
- `0x18000b5d0`
- `0x18000c990`
- `0x180018290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a86c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a86c`

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
0x18000a834  mov     [rsp-8+arg_10], rbx
0x18000a839  mov     [rsp-8+arg_18], rdi
0x18000a83e  push    rbp
0x18000a83f  lea     rbp, [rsp-170h]
0x18000a847  sub     rsp, 270h
0x18000a84e  mov     rax, cs:__security_cookie
0x18000a855  xor     rax, rsp
0x18000a858  mov     [rbp+170h+var_10], rax
0x18000a85f  mov     rdi, rdx
0x18000a862  mov     rbx, rcx
0x18000a865  mov     qword ptr [rdx], 0
0x18000a86c  call    cs:__imp_GetCurrentProcessId
0x18000a872  mov     r9d, eax
0x18000a875  mov     [rsp+270h+var_248], rbx
0x18000a87a  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a882  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a889  mov     edx, 104h; unsigned __int64
0x18000a88e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a893  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a898  mov     [rsp+270h+var_240], 0
0x18000a8a1  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a8a7  xor     r8d, r8d; dwFlags
0x18000a8aa  lea     rdx, [rsp+270h+Name]; lpName
0x18000a8af  xor     ecx, ecx; lpMutexAttributes
0x18000a8b1  call    cs:__imp_CreateMutexExW
0x18000a8b7  mov     rdx, rax
0x18000a8ba  lea     rcx, [rsp+270h+var_240]
0x18000a8bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a8c4  cmp     [rsp+270h+var_240], 0
0x18000a8ca  jnz     short loc_18000A8D5
0x18000a8cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a8d1  mov     ebx, eax
0x18000a8d3  jmp     short loc_18000A943
0x18000a8d5  lea     rdx, [rsp+270h+var_238]
0x18000a8da  lea     rcx, [rsp+270h+var_240]
0x18000a8df  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000a8e4  nop
0x18000a8e5  mov     [rsp+270h+var_230], 0
0x18000a8ee  lea     rdx, [rsp+270h+var_230]; void **
0x18000a8f3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a8f8  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000a8fd  mov     ebx, eax
0x18000a8ff  test    eax, eax
0x18000a901  jns     short loc_18000A924
0x18000a903  mov     edx, 12Eh; void *
0x18000a908  mov     r9d, eax; char *
0x18000a90b  mov     rcx, [rbp+178h]; this
0x18000a912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a917  nop
0x18000a918  lea     rcx, [rsp+270h+var_238]
0x18000a91d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a922  jmp     short loc_18000A943
0x18000a924  mov     rcx, [rsp+270h+var_230]
0x18000a929  test    rcx, rcx
0x18000a92c  jz      short loc_18000A973
0x18000a92e  mov     [rdi], rcx
0x18000a931  mov     eax, [rcx]
0x18000a933  inc     eax
0x18000a935  mov     [rcx], eax
0x18000a937  lea     rcx, [rsp+270h+var_238]
0x18000a93c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a941  xor     ebx, ebx
0x18000a943  lea     rcx, [rsp+270h+var_240]
0x18000a948  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a94d  mov     eax, ebx
0x18000a94f  mov     rcx, [rbp+170h+var_10]
0x18000a956  xor     rcx, rsp; StackCookie
0x18000a959  call    __security_check_cookie
0x18000a95e  lea     r11, [rsp+270h+var_s0]
0x18000a966  mov     rbx, [r11+20h]
0x18000a96a  mov     rdi, [r11+28h]
0x18000a96e  mov     rsp, r11
0x18000a971  pop     rbp
0x18000a972  retn
0x18000a973  mov     r8, rdi
0x18000a976  lea     rdx, [rsp+270h+var_240]
0x18000a97b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a980  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a985  mov     ebx, eax
0x18000a987  test    eax, eax
0x18000a989  jns     short loc_18000A937
0x18000a98b  mov     edx, 137h
0x18000a990  jmp     loc_18000A908
```
