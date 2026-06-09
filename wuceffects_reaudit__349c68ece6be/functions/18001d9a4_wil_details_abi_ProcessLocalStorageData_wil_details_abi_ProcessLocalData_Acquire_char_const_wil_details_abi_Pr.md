# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001d9a4`
- end: `0x18001db4b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002389c`

## callees

- `0x180018cbc`
- `0x180019008`
- `0x18001c18c`
- `0x18001c264`
- `0x18001d9a4`
- `0x18001db54`
- `0x18001db70`
- `0x18001dc0c`
- `0x18001dc90`
- `0x180021060`
- `0x180023afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001da1e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001da1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d9d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d9d9`

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
0x18001d9a4  mov     [rsp-8+arg_10], rbx
0x18001d9a9  push    rbp
0x18001d9aa  push    rsi
0x18001d9ab  push    rdi
0x18001d9ac  lea     rbp, [rsp-170h]
0x18001d9b4  sub     rsp, 270h
0x18001d9bb  mov     rax, cs:__security_cookie
0x18001d9c2  xor     rax, rsp
0x18001d9c5  mov     [rbp+180h+var_20], rax
0x18001d9cc  mov     rsi, rdx
0x18001d9cf  mov     qword ptr [rdx], 0
0x18001d9d6  mov     rbx, rcx
0x18001d9d9  call    cs:__imp_GetCurrentProcessId
0x18001d9df  mov     [rsp+280h+var_258], rbx
0x18001d9e4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001d9eb  mov     r9d, eax
0x18001d9ee  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18001d9f6  mov     edx, 104h; unsigned __int64
0x18001d9fb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001da00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001da05  mov     r9d, 1F0001h; dwDesiredAccess
0x18001da0b  mov     [rsp+280h+var_250], 0
0x18001da14  xor     r8d, r8d; dwFlags
0x18001da17  lea     rdx, [rsp+280h+Name]; lpName
0x18001da1c  xor     ecx, ecx; lpMutexAttributes
0x18001da1e  call    cs:__imp_CreateMutexExW
0x18001da24  mov     rdx, rax
0x18001da27  lea     rcx, [rsp+280h+var_250]
0x18001da2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001da31  mov     rbx, [rsp+280h+var_250]
0x18001da36  test    rbx, rbx
0x18001da39  jnz     short loc_18001DA45
0x18001da3b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001da40  jmp     loc_18001DB29
0x18001da45  lea     rdx, [rsp+280h+var_248]
0x18001da4a  lea     rcx, [rsp+280h+var_250]
0x18001da4f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001da54  lea     rdx, [rsp+280h+var_240]; void **
0x18001da59  mov     [rsp+280h+var_240], 0
0x18001da62  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001da67  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001da6c  mov     edi, eax
0x18001da6e  test    eax, eax
0x18001da70  jns     short loc_18001DAA6
0x18001da72  mov     rcx, [rbp+188h]; this
0x18001da79  lea     r8, aWil; "wil"
0x18001da80  mov     r9d, eax; char *
0x18001da83  mov     edx, 12Eh; void *
0x18001da88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da8d  lea     rcx, [rsp+280h+var_248]
0x18001da92  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001da97  mov     rcx, rbx; this
0x18001da9a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001da9f  mov     eax, edi
0x18001daa1  jmp     loc_18001DB29
0x18001daa6  mov     rcx, [rsp+280h+var_240]
0x18001daab  test    rcx, rcx
0x18001daae  jz      short loc_18001DABB
0x18001dab0  mov     [rsi], rcx
0x18001dab3  mov     eax, [rcx]
0x18001dab5  inc     eax
0x18001dab7  mov     [rcx], eax
0x18001dab9  jmp     short loc_18001DB10
0x18001dabb  mov     r8, rsi
0x18001dabe  lea     rdx, [rsp+280h+var_250]
0x18001dac3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001dac8  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001dacd  mov     ebx, eax
0x18001dacf  test    eax, eax
0x18001dad1  jns     short loc_18001DB0B
0x18001dad3  mov     rcx, [rbp+188h]; this
0x18001dada  lea     r8, aWil; "wil"
0x18001dae1  mov     r9d, eax; char *
0x18001dae4  mov     edx, 137h; void *
0x18001dae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001daee  lea     rcx, [rsp+280h+var_248]
0x18001daf3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001daf8  mov     rcx, [rsp+280h+var_250]; this
0x18001dafd  test    rcx, rcx
0x18001db00  jz      short loc_18001DB07
0x18001db02  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001db07  mov     eax, ebx
0x18001db09  jmp     short loc_18001DB29
0x18001db0b  mov     rbx, [rsp+280h+var_250]
0x18001db10  lea     rcx, [rsp+280h+var_248]
0x18001db15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db1a  test    rbx, rbx
0x18001db1d  jz      short loc_18001DB27
0x18001db1f  mov     rcx, rbx; this
0x18001db22  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001db27  xor     eax, eax
0x18001db29  mov     rcx, [rbp+180h+var_20]
0x18001db30  xor     rcx, rsp; StackCookie
0x18001db33  call    __security_check_cookie
0x18001db38  mov     rbx, [rsp+280h+arg_10]
0x18001db40  add     rsp, 270h
0x18001db47  pop     rdi
0x18001db48  pop     rsi
0x18001db49  pop     rbp
0x18001db4a  retn
```
