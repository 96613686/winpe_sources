# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180028c3c`
- end: `0x180028d9b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180029ac0`

## callees

- `0x180026148`
- `0x180026580`
- `0x180026a30`
- `0x180028aa8`
- `0x180028ac4`
- `0x180028c3c`
- `0x18002a2f8`
- `0x18002b410`
- `0x18002bba8`
- `0x18002c3c4`
- `0x18002c500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028cb9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028c74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028c74`

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
0x180028c3c  mov     [rsp-8+arg_10], rbx
0x180028c41  mov     [rsp-8+arg_18], rdi
0x180028c46  push    rbp
0x180028c47  lea     rbp, [rsp-170h]
0x180028c4f  sub     rsp, 270h
0x180028c56  mov     rax, cs:__security_cookie
0x180028c5d  xor     rax, rsp
0x180028c60  mov     [rbp+170h+var_10], rax
0x180028c67  mov     rdi, rdx
0x180028c6a  mov     qword ptr [rdx], 0
0x180028c71  mov     rbx, rcx
0x180028c74  call    cs:__imp_GetCurrentProcessId
0x180028c7a  mov     [rsp+270h+var_248], rbx
0x180028c7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180028c86  mov     r9d, eax
0x180028c89  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180028c91  mov     edx, 104h; unsigned __int64
0x180028c96  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028c9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028ca0  mov     r9d, 1F0001h; dwDesiredAccess
0x180028ca6  mov     [rsp+270h+var_240], 0
0x180028caf  xor     r8d, r8d; dwFlags
0x180028cb2  lea     rdx, [rsp+270h+Name]; lpName
0x180028cb7  xor     ecx, ecx; lpMutexAttributes
0x180028cb9  call    cs:__imp_CreateMutexExW
0x180028cbf  mov     rdx, rax
0x180028cc2  lea     rcx, [rsp+270h+var_240]
0x180028cc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028ccc  cmp     [rsp+270h+var_240], 0
0x180028cd2  jnz     short loc_180028CDD
0x180028cd4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028cd9  mov     ebx, eax
0x180028cdb  jmp     short loc_180028D49
0x180028cdd  lea     rdx, [rsp+270h+var_238]
0x180028ce2  lea     rcx, [rsp+270h+var_240]
0x180028ce7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180028cec  lea     rdx, [rsp+270h+var_230]; void **
0x180028cf1  mov     [rsp+270h+var_230], 0
0x180028cfa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028cff  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180028d04  mov     ebx, eax
0x180028d06  test    eax, eax
0x180028d08  jns     short loc_180028D2A
0x180028d0a  mov     edx, 12Eh; void *
0x180028d0f  mov     rcx, [rbp+178h]; this
0x180028d16  mov     r9d, eax; char *
0x180028d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d1e  lea     rcx, [rsp+270h+var_238]
0x180028d23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028d28  jmp     short loc_180028D49
0x180028d2a  mov     rcx, [rsp+270h+var_230]
0x180028d2f  test    rcx, rcx
0x180028d32  jz      short loc_180028D79
0x180028d34  mov     [rdi], rcx
0x180028d37  mov     eax, [rcx]
0x180028d39  inc     eax
0x180028d3b  mov     [rcx], eax
0x180028d3d  lea     rcx, [rsp+270h+var_238]
0x180028d42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028d47  xor     ebx, ebx
0x180028d49  lea     rcx, [rsp+270h+var_240]
0x180028d4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028d53  mov     eax, ebx
0x180028d55  mov     rcx, [rbp+170h+var_10]
0x180028d5c  xor     rcx, rsp; StackCookie
0x180028d5f  call    __security_check_cookie
0x180028d64  lea     r11, [rsp+270h+var_s0]
0x180028d6c  mov     rbx, [r11+20h]
0x180028d70  mov     rdi, [r11+28h]
0x180028d74  mov     rsp, r11
0x180028d77  pop     rbp
0x180028d78  retn
0x180028d79  mov     r8, rdi
0x180028d7c  lea     rdx, [rsp+270h+var_240]
0x180028d81  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028d86  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180028d8b  mov     ebx, eax
0x180028d8d  test    eax, eax
0x180028d8f  jns     short loc_180028D3D
0x180028d91  mov     edx, 137h
0x180028d96  jmp     loc_180028D0F
```
