# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18007f4e4`
- end: `0x18007f68b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180097f60`

## callees

- `0x180061e54`
- `0x180061f48`
- `0x1800623e4`
- `0x180071328`
- `0x18007f4e4`
- `0x18007f694`
- `0x180080308`
- `0x180081a68`
- `0x180083064`
- `0x180095130`
- `0x1800990a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007f55e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18007f55e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f519`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  int Pointer; // eax
  unsigned int v9; // edi
  void *v10; // rdx
  _DWORD *v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rdx
  void *v15; // rdx
  wil::details *v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v18; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v16 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    Mutex);
  v6 = v16;
  if ( !v16 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v16,
    v17);
  v18 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  v9 = Pointer;
  if ( Pointer < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      120);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    wil::details::CloseHandle(v6, v10);
    return v9;
  }
  v11 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v11;
LABEL_12:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    if ( v6 )
      wil::details::CloseHandle(v6, v15);
    return 0;
  }
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 120);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x18007f4e4  mov     [rsp-8+arg_10], rbx
0x18007f4e9  push    rbp
0x18007f4ea  push    rsi
0x18007f4eb  push    rdi
0x18007f4ec  lea     rbp, [rsp-170h]
0x18007f4f4  sub     rsp, 270h
0x18007f4fb  mov     rax, cs:__security_cookie
0x18007f502  xor     rax, rsp
0x18007f505  mov     [rbp+180h+var_20], rax
0x18007f50c  mov     rsi, rdx
0x18007f50f  mov     qword ptr [rdx], 0
0x18007f516  mov     rbx, rcx
0x18007f519  call    cs:__imp_GetCurrentProcessId
0x18007f51f  mov     [rsp+280h+var_258], rbx
0x18007f524  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18007f52b  mov     r9d, eax
0x18007f52e  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18007f536  mov     edx, 104h; unsigned __int64
0x18007f53b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18007f540  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f545  mov     r9d, 1F0001h; dwDesiredAccess
0x18007f54b  mov     [rsp+280h+var_250], 0
0x18007f554  xor     r8d, r8d; dwFlags
0x18007f557  lea     rdx, [rsp+280h+Name]; lpName
0x18007f55c  xor     ecx, ecx; lpMutexAttributes
0x18007f55e  call    cs:__imp_CreateMutexExW
0x18007f564  mov     rdx, rax
0x18007f567  lea     rcx, [rsp+280h+var_250]
0x18007f56c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007f571  mov     rbx, [rsp+280h+var_250]
0x18007f576  test    rbx, rbx
0x18007f579  jnz     short loc_18007F585
0x18007f57b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18007f580  jmp     loc_18007F669
0x18007f585  lea     rdx, [rsp+280h+var_248]
0x18007f58a  lea     rcx, [rsp+280h+var_250]
0x18007f58f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18007f594  lea     rdx, [rsp+280h+var_240]; void **
0x18007f599  mov     [rsp+280h+var_240], 0
0x18007f5a2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18007f5a7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18007f5ac  mov     edi, eax
0x18007f5ae  test    eax, eax
0x18007f5b0  jns     short loc_18007F5E6
0x18007f5b2  mov     rcx, [rbp+188h]; this
0x18007f5b9  lea     r8, aWil; "wil"
0x18007f5c0  mov     r9d, eax; char *
0x18007f5c3  mov     edx, 12Eh; void *
0x18007f5c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f5cd  lea     rcx, [rsp+280h+var_248]
0x18007f5d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f5d7  mov     rcx, rbx; this
0x18007f5da  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18007f5df  mov     eax, edi
0x18007f5e1  jmp     loc_18007F669
0x18007f5e6  mov     rcx, [rsp+280h+var_240]
0x18007f5eb  test    rcx, rcx
0x18007f5ee  jz      short loc_18007F5FB
0x18007f5f0  mov     [rsi], rcx
0x18007f5f3  mov     eax, [rcx]
0x18007f5f5  inc     eax
0x18007f5f7  mov     [rcx], eax
0x18007f5f9  jmp     short loc_18007F650
0x18007f5fb  mov     r8, rsi
0x18007f5fe  lea     rdx, [rsp+280h+var_250]
0x18007f603  lea     rcx, [rsp+280h+Name]
0x18007f608  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18007f60d  mov     ebx, eax
0x18007f60f  test    eax, eax
0x18007f611  jns     short loc_18007F64B
0x18007f613  mov     rcx, [rbp+188h]; this
0x18007f61a  lea     r8, aWil; "wil"
0x18007f621  mov     r9d, eax; char *
0x18007f624  mov     edx, 137h; void *
0x18007f629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007f62e  lea     rcx, [rsp+280h+var_248]
0x18007f633  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f638  mov     rcx, [rsp+280h+var_250]; this
0x18007f63d  test    rcx, rcx
0x18007f640  jz      short loc_18007F647
0x18007f642  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18007f647  mov     eax, ebx
0x18007f649  jmp     short loc_18007F669
0x18007f64b  mov     rbx, [rsp+280h+var_250]
0x18007f650  lea     rcx, [rsp+280h+var_248]
0x18007f655  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007f65a  test    rbx, rbx
0x18007f65d  jz      short loc_18007F667
0x18007f65f  mov     rcx, rbx; this
0x18007f662  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18007f667  xor     eax, eax
0x18007f669  mov     rcx, [rbp+180h+var_20]
0x18007f670  xor     rcx, rsp; StackCookie
0x18007f673  call    __security_check_cookie
0x18007f678  mov     rbx, [rsp+280h+arg_10]
0x18007f680  add     rsp, 270h
0x18007f687  pop     rdi
0x18007f688  pop     rsi
0x18007f689  pop     rbp
0x18007f68a  retn
```
