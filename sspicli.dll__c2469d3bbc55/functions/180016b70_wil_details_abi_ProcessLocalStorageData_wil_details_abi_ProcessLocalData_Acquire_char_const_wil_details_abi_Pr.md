# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180016b70`
- end: `0x180016ccf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001ea74`

## callees

- `0x180012260`
- `0x1800149dc`
- `0x180016100`
- `0x180016174`
- `0x180016b70`
- `0x180016cd8`
- `0x180016cf4`
- `0x180016d28`
- `0x180017278`
- `0x18001eb38`
- `0x180022190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016bed`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180016bed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016ba8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016ba8`

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
0x180016b70  mov     [rsp-8+arg_10], rbx
0x180016b75  mov     [rsp-8+arg_18], rdi
0x180016b7a  push    rbp
0x180016b7b  lea     rbp, [rsp-170h]
0x180016b83  sub     rsp, 270h
0x180016b8a  mov     rax, cs:__security_cookie
0x180016b91  xor     rax, rsp
0x180016b94  mov     [rbp+170h+var_10], rax
0x180016b9b  mov     rdi, rdx
0x180016b9e  mov     qword ptr [rdx], 0
0x180016ba5  mov     rbx, rcx
0x180016ba8  call    cs:__imp_GetCurrentProcessId
0x180016bae  mov     [rsp+270h+var_248], rbx
0x180016bb3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180016bba  mov     r9d, eax
0x180016bbd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180016bc5  mov     edx, 104h; unsigned __int64
0x180016bca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016bcf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016bd4  mov     r9d, 1F0001h; dwDesiredAccess
0x180016bda  mov     [rsp+270h+var_240], 0
0x180016be3  xor     r8d, r8d; dwFlags
0x180016be6  lea     rdx, [rsp+270h+Name]; lpName
0x180016beb  xor     ecx, ecx; lpMutexAttributes
0x180016bed  call    cs:__imp_CreateMutexExW
0x180016bf3  mov     rdx, rax
0x180016bf6  lea     rcx, [rsp+270h+var_240]
0x180016bfb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016c00  cmp     [rsp+270h+var_240], 0
0x180016c06  jnz     short loc_180016C11
0x180016c08  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016c0d  mov     ebx, eax
0x180016c0f  jmp     short loc_180016C7D
0x180016c11  lea     rdx, [rsp+270h+var_238]
0x180016c16  lea     rcx, [rsp+270h+var_240]
0x180016c1b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180016c20  lea     rdx, [rsp+270h+var_230]; void **
0x180016c25  mov     [rsp+270h+var_230], 0
0x180016c2e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016c33  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180016c38  mov     ebx, eax
0x180016c3a  test    eax, eax
0x180016c3c  jns     short loc_180016C5E
0x180016c3e  mov     edx, 12Eh; void *
0x180016c43  mov     rcx, [rbp+178h]; this
0x180016c4a  mov     r9d, eax; char *
0x180016c4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c52  lea     rcx, [rsp+270h+var_238]
0x180016c57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016c5c  jmp     short loc_180016C7D
0x180016c5e  mov     rcx, [rsp+270h+var_230]
0x180016c63  test    rcx, rcx
0x180016c66  jz      short loc_180016CAD
0x180016c68  mov     [rdi], rcx
0x180016c6b  mov     eax, [rcx]
0x180016c6d  inc     eax
0x180016c6f  mov     [rcx], eax
0x180016c71  lea     rcx, [rsp+270h+var_238]
0x180016c76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016c7b  xor     ebx, ebx
0x180016c7d  lea     rcx, [rsp+270h+var_240]
0x180016c82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016c87  mov     eax, ebx
0x180016c89  mov     rcx, [rbp+170h+var_10]
0x180016c90  xor     rcx, rsp; StackCookie
0x180016c93  call    __security_check_cookie
0x180016c98  lea     r11, [rsp+270h+var_s0]
0x180016ca0  mov     rbx, [r11+20h]
0x180016ca4  mov     rdi, [r11+28h]
0x180016ca8  mov     rsp, r11
0x180016cab  pop     rbp
0x180016cac  retn
0x180016cad  mov     r8, rdi
0x180016cb0  lea     rdx, [rsp+270h+var_240]
0x180016cb5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180016cba  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180016cbf  mov     ebx, eax
0x180016cc1  test    eax, eax
0x180016cc3  jns     short loc_180016C71
0x180016cc5  mov     edx, 137h
0x180016cca  jmp     loc_180016C43
```
