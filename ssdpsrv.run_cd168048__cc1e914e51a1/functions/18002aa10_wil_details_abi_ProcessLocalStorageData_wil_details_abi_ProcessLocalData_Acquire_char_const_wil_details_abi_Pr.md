# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002aa10`
- end: `0x18002ab7c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002b9ac`

## callees

- `0x180027ee4`
- `0x180028328`
- `0x1800287d0`
- `0x18002a86c`
- `0x18002a88c`
- `0x18002aa10`
- `0x18002c2a0`
- `0x18002d39c`
- `0x18002dab4`
- `0x18002e364`
- `0x18002e4b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002aa93`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002aa93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002aa48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002aa48`

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
0x18002aa10  mov     [rsp-8+arg_10], rbx
0x18002aa15  mov     [rsp-8+arg_18], rdi
0x18002aa1a  push    rbp
0x18002aa1b  lea     rbp, [rsp-170h]
0x18002aa23  sub     rsp, 270h
0x18002aa2a  mov     rax, cs:__security_cookie
0x18002aa31  xor     rax, rsp
0x18002aa34  mov     [rbp+170h+var_10], rax
0x18002aa3b  mov     rdi, rdx
0x18002aa3e  mov     qword ptr [rdx], 0
0x18002aa45  mov     rbx, rcx
0x18002aa48  call    cs:__imp_GetCurrentProcessId
0x18002aa4f  nop     dword ptr [rax+rax+00h]
0x18002aa54  mov     [rsp+270h+var_248], rbx
0x18002aa59  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002aa60  mov     r9d, eax
0x18002aa63  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002aa6b  mov     edx, 104h; unsigned __int64
0x18002aa70  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002aa75  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002aa7a  mov     r9d, 1F0001h; dwDesiredAccess
0x18002aa80  mov     [rsp+270h+var_240], 0
0x18002aa89  xor     r8d, r8d; dwFlags
0x18002aa8c  lea     rdx, [rsp+270h+Name]; lpName
0x18002aa91  xor     ecx, ecx; lpMutexAttributes
0x18002aa93  call    cs:__imp_CreateMutexExW
0x18002aa9a  nop     dword ptr [rax+rax+00h]
0x18002aa9f  mov     rdx, rax
0x18002aaa2  lea     rcx, [rsp+270h+var_240]
0x18002aaa7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002aaac  cmp     [rsp+270h+var_240], 0
0x18002aab2  jnz     short loc_18002AABD
0x18002aab4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002aab9  mov     ebx, eax
0x18002aabb  jmp     short loc_18002AB29
0x18002aabd  lea     rdx, [rsp+270h+var_238]
0x18002aac2  lea     rcx, [rsp+270h+var_240]
0x18002aac7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002aacc  lea     rdx, [rsp+270h+var_230]; void **
0x18002aad1  mov     [rsp+270h+var_230], 0
0x18002aada  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002aadf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002aae4  mov     ebx, eax
0x18002aae6  test    eax, eax
0x18002aae8  jns     short loc_18002AB0A
0x18002aaea  mov     edx, 12Eh; void *
0x18002aaef  mov     rcx, [rbp+178h]; this
0x18002aaf6  mov     r9d, eax; char *
0x18002aaf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aafe  lea     rcx, [rsp+270h+var_238]
0x18002ab03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ab08  jmp     short loc_18002AB29
0x18002ab0a  mov     rcx, [rsp+270h+var_230]
0x18002ab0f  test    rcx, rcx
0x18002ab12  jz      short loc_18002AB5A
0x18002ab14  mov     [rdi], rcx
0x18002ab17  mov     eax, [rcx]
0x18002ab19  inc     eax
0x18002ab1b  mov     [rcx], eax
0x18002ab1d  lea     rcx, [rsp+270h+var_238]
0x18002ab22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ab27  xor     ebx, ebx
0x18002ab29  lea     rcx, [rsp+270h+var_240]
0x18002ab2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ab33  mov     eax, ebx
0x18002ab35  mov     rcx, [rbp+170h+var_10]
0x18002ab3c  xor     rcx, rsp; StackCookie
0x18002ab3f  call    __security_check_cookie
0x18002ab44  lea     r11, [rsp+270h+var_s0]
0x18002ab4c  mov     rbx, [r11+20h]
0x18002ab50  mov     rdi, [r11+28h]
0x18002ab54  mov     rsp, r11
0x18002ab57  pop     rbp
0x18002ab58  retn
0x18002ab5a  mov     r8, rdi
0x18002ab5d  lea     rdx, [rsp+270h+var_240]
0x18002ab62  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002ab67  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002ab6c  mov     ebx, eax
0x18002ab6e  test    eax, eax
0x18002ab70  jns     short loc_18002AB1D
0x18002ab72  mov     edx, 137h
0x18002ab77  jmp     loc_18002AAEF
```
