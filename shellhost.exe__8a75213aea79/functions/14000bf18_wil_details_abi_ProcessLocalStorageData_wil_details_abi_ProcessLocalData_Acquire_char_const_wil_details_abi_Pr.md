# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000bf18`
- end: `0x14000c0bf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400477f8`

## callees

- `0x14000bf18`
- `0x14000c0c8`
- `0x14000c0e4`
- `0x14000c118`
- `0x14000c16c`
- `0x14000c190`
- `0x14000c1f4`
- `0x14000c254`
- `0x14000d218`
- `0x14000f7e0`
- `0x1400480e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000bf92`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000bf92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bf4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bf4d`

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
0x14000bf18  mov     [rsp-8+arg_10], rbx
0x14000bf1d  push    rbp
0x14000bf1e  push    rsi
0x14000bf1f  push    rdi
0x14000bf20  lea     rbp, [rsp-170h]
0x14000bf28  sub     rsp, 270h
0x14000bf2f  mov     rax, cs:__security_cookie
0x14000bf36  xor     rax, rsp
0x14000bf39  mov     [rbp+180h+var_20], rax
0x14000bf40  mov     rsi, rdx
0x14000bf43  mov     qword ptr [rdx], 0
0x14000bf4a  mov     rbx, rcx
0x14000bf4d  call    cs:__imp_GetCurrentProcessId
0x14000bf53  mov     [rsp+280h+var_258], rbx
0x14000bf58  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000bf5f  mov     r9d, eax
0x14000bf62  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x14000bf6a  mov     edx, 104h; unsigned __int64
0x14000bf6f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000bf74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bf79  mov     r9d, 1F0001h; dwDesiredAccess
0x14000bf7f  mov     [rsp+280h+var_250], 0
0x14000bf88  xor     r8d, r8d; dwFlags
0x14000bf8b  lea     rdx, [rsp+280h+Name]; lpName
0x14000bf90  xor     ecx, ecx; lpMutexAttributes
0x14000bf92  call    cs:__imp_CreateMutexExW
0x14000bf98  mov     rdx, rax
0x14000bf9b  lea     rcx, [rsp+280h+var_250]
0x14000bfa0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000bfa5  mov     rbx, [rsp+280h+var_250]
0x14000bfaa  test    rbx, rbx
0x14000bfad  jnz     short loc_14000BFB9
0x14000bfaf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000bfb4  jmp     loc_14000C09D
0x14000bfb9  lea     rdx, [rsp+280h+var_248]
0x14000bfbe  lea     rcx, [rsp+280h+var_250]
0x14000bfc3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000bfc8  lea     rdx, [rsp+280h+var_240]; void **
0x14000bfcd  mov     [rsp+280h+var_240], 0
0x14000bfd6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000bfdb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000bfe0  mov     edi, eax
0x14000bfe2  test    eax, eax
0x14000bfe4  jns     short loc_14000C01A
0x14000bfe6  mov     rcx, [rbp+188h]; this
0x14000bfed  lea     r8, aWil; "wil"
0x14000bff4  mov     r9d, eax; char *
0x14000bff7  mov     edx, 12Eh; void *
0x14000bffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c001  lea     rcx, [rsp+280h+var_248]
0x14000c006  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c00b  mov     rcx, rbx; this
0x14000c00e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000c013  mov     eax, edi
0x14000c015  jmp     loc_14000C09D
0x14000c01a  mov     rcx, [rsp+280h+var_240]
0x14000c01f  test    rcx, rcx
0x14000c022  jz      short loc_14000C02F
0x14000c024  mov     [rsi], rcx
0x14000c027  mov     eax, [rcx]
0x14000c029  inc     eax
0x14000c02b  mov     [rcx], eax
0x14000c02d  jmp     short loc_14000C084
0x14000c02f  mov     r8, rsi
0x14000c032  lea     rdx, [rsp+280h+var_250]
0x14000c037  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c03c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000c041  mov     ebx, eax
0x14000c043  test    eax, eax
0x14000c045  jns     short loc_14000C07F
0x14000c047  mov     rcx, [rbp+188h]; this
0x14000c04e  lea     r8, aWil; "wil"
0x14000c055  mov     r9d, eax; char *
0x14000c058  mov     edx, 137h; void *
0x14000c05d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c062  lea     rcx, [rsp+280h+var_248]
0x14000c067  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c06c  mov     rcx, [rsp+280h+var_250]; this
0x14000c071  test    rcx, rcx
0x14000c074  jz      short loc_14000C07B
0x14000c076  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000c07b  mov     eax, ebx
0x14000c07d  jmp     short loc_14000C09D
0x14000c07f  mov     rbx, [rsp+280h+var_250]
0x14000c084  lea     rcx, [rsp+280h+var_248]
0x14000c089  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c08e  test    rbx, rbx
0x14000c091  jz      short loc_14000C09B
0x14000c093  mov     rcx, rbx; this
0x14000c096  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000c09b  xor     eax, eax
0x14000c09d  mov     rcx, [rbp+180h+var_20]
0x14000c0a4  xor     rcx, rsp; StackCookie
0x14000c0a7  call    __security_check_cookie
0x14000c0ac  mov     rbx, [rsp+280h+arg_10]
0x14000c0b4  add     rsp, 270h
0x14000c0bb  pop     rdi
0x14000c0bc  pop     rsi
0x14000c0bd  pop     rbp
0x14000c0be  retn
```
