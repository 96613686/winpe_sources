# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18003fa78`
- end: `0x18003fbe4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180042288`

## callees

- `0x180028014`
- `0x18003c374`
- `0x18003cb60`
- `0x18003f2fc`
- `0x18003f31c`
- `0x18003fa78`
- `0x180042bfc`
- `0x180045100`
- `0x180046064`
- `0x180046f54`
- `0x180047100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fafb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fafb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fab0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fab0`

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
0x18003fa78  mov     [rsp-8+arg_10], rbx
0x18003fa7d  mov     [rsp-8+arg_18], rdi
0x18003fa82  push    rbp
0x18003fa83  lea     rbp, [rsp-170h]
0x18003fa8b  sub     rsp, 270h
0x18003fa92  mov     rax, cs:__security_cookie
0x18003fa99  xor     rax, rsp
0x18003fa9c  mov     [rbp+170h+var_10], rax
0x18003faa3  mov     rdi, rdx
0x18003faa6  mov     qword ptr [rdx], 0
0x18003faad  mov     rbx, rcx
0x18003fab0  call    cs:__imp_GetCurrentProcessId
0x18003fab7  nop     dword ptr [rax+rax+00h]
0x18003fabc  mov     [rsp+270h+var_248], rbx
0x18003fac1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003fac8  mov     r9d, eax
0x18003facb  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003fad3  mov     edx, 104h; unsigned __int64
0x18003fad8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fadd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fae2  mov     r9d, 1F0001h; dwDesiredAccess
0x18003fae8  mov     [rsp+270h+var_240], 0
0x18003faf1  xor     r8d, r8d; dwFlags
0x18003faf4  lea     rdx, [rsp+270h+Name]; lpName
0x18003faf9  xor     ecx, ecx; lpMutexAttributes
0x18003fafb  call    cs:__imp_CreateMutexExW
0x18003fb02  nop     dword ptr [rax+rax+00h]
0x18003fb07  mov     rdx, rax
0x18003fb0a  lea     rcx, [rsp+270h+var_240]
0x18003fb0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003fb14  cmp     [rsp+270h+var_240], 0
0x18003fb1a  jnz     short loc_18003FB25
0x18003fb1c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003fb21  mov     ebx, eax
0x18003fb23  jmp     short loc_18003FB91
0x18003fb25  lea     rdx, [rsp+270h+var_238]
0x18003fb2a  lea     rcx, [rsp+270h+var_240]
0x18003fb2f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003fb34  lea     rdx, [rsp+270h+var_230]; void **
0x18003fb39  mov     [rsp+270h+var_230], 0
0x18003fb42  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fb47  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003fb4c  mov     ebx, eax
0x18003fb4e  test    eax, eax
0x18003fb50  jns     short loc_18003FB72
0x18003fb52  mov     edx, 12Eh; void *
0x18003fb57  mov     rcx, [rbp+178h]; this
0x18003fb5e  mov     r9d, eax; char *
0x18003fb61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb66  lea     rcx, [rsp+270h+var_238]
0x18003fb6b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fb70  jmp     short loc_18003FB91
0x18003fb72  mov     rcx, [rsp+270h+var_230]
0x18003fb77  test    rcx, rcx
0x18003fb7a  jz      short loc_18003FBC2
0x18003fb7c  mov     [rdi], rcx
0x18003fb7f  mov     eax, [rcx]
0x18003fb81  inc     eax
0x18003fb83  mov     [rcx], eax
0x18003fb85  lea     rcx, [rsp+270h+var_238]
0x18003fb8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fb8f  xor     ebx, ebx
0x18003fb91  lea     rcx, [rsp+270h+var_240]
0x18003fb96  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fb9b  mov     eax, ebx
0x18003fb9d  mov     rcx, [rbp+170h+var_10]
0x18003fba4  xor     rcx, rsp; StackCookie
0x18003fba7  call    __security_check_cookie
0x18003fbac  lea     r11, [rsp+270h+var_s0]
0x18003fbb4  mov     rbx, [r11+20h]
0x18003fbb8  mov     rdi, [r11+28h]
0x18003fbbc  mov     rsp, r11
0x18003fbbf  pop     rbp
0x18003fbc0  retn
0x18003fbc2  mov     r8, rdi
0x18003fbc5  lea     rdx, [rsp+270h+var_240]
0x18003fbca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003fbcf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003fbd4  mov     ebx, eax
0x18003fbd6  test    eax, eax
0x18003fbd8  jns     short loc_18003FB85
0x18003fbda  mov     edx, 137h
0x18003fbdf  jmp     loc_18003FB57
```
