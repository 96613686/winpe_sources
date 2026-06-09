# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000bd68`
- end: `0x14000bf0f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140046878`

## callees

- `0x14000bd68`
- `0x14000c0c8`
- `0x14000c0e4`
- `0x14000c118`
- `0x14000c16c`
- `0x14000c190`
- `0x14000c1f4`
- `0x14000c254`
- `0x14000d218`
- `0x14000f7e0`
- `0x140048230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000bde2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000bde2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bd9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000bd9d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      304);
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
  v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v6 = v16;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v12, 304);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
  if ( v16 )
    wil::details::CloseHandle(v16, v14);
  return v13;
}

```

## disassembly

```asm
0x14000bd68  mov     [rsp-8+arg_10], rbx
0x14000bd6d  push    rbp
0x14000bd6e  push    rsi
0x14000bd6f  push    rdi
0x14000bd70  lea     rbp, [rsp-170h]
0x14000bd78  sub     rsp, 270h
0x14000bd7f  mov     rax, cs:__security_cookie
0x14000bd86  xor     rax, rsp
0x14000bd89  mov     [rbp+180h+var_20], rax
0x14000bd90  mov     rsi, rdx
0x14000bd93  mov     qword ptr [rdx], 0
0x14000bd9a  mov     rbx, rcx
0x14000bd9d  call    cs:__imp_GetCurrentProcessId
0x14000bda3  mov     [rsp+280h+var_258], rbx
0x14000bda8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000bdaf  mov     r9d, eax
0x14000bdb2  mov     [rsp+280h+var_260], 130h; int
0x14000bdba  mov     edx, 104h; unsigned __int64
0x14000bdbf  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000bdc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000bdc9  mov     r9d, 1F0001h; dwDesiredAccess
0x14000bdcf  mov     [rsp+280h+var_250], 0
0x14000bdd8  xor     r8d, r8d; dwFlags
0x14000bddb  lea     rdx, [rsp+280h+Name]; lpName
0x14000bde0  xor     ecx, ecx; lpMutexAttributes
0x14000bde2  call    cs:__imp_CreateMutexExW
0x14000bde8  mov     rdx, rax
0x14000bdeb  lea     rcx, [rsp+280h+var_250]
0x14000bdf0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000bdf5  mov     rbx, [rsp+280h+var_250]
0x14000bdfa  test    rbx, rbx
0x14000bdfd  jnz     short loc_14000BE09
0x14000bdff  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000be04  jmp     loc_14000BEED
0x14000be09  lea     rdx, [rsp+280h+var_248]
0x14000be0e  lea     rcx, [rsp+280h+var_250]
0x14000be13  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000be18  lea     rdx, [rsp+280h+var_240]; void **
0x14000be1d  mov     [rsp+280h+var_240], 0
0x14000be26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000be2b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000be30  mov     edi, eax
0x14000be32  test    eax, eax
0x14000be34  jns     short loc_14000BE6A
0x14000be36  mov     rcx, [rbp+188h]; this
0x14000be3d  lea     r8, aWil; "wil"
0x14000be44  mov     r9d, eax; char *
0x14000be47  mov     edx, 12Eh; void *
0x14000be4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000be51  lea     rcx, [rsp+280h+var_248]
0x14000be56  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000be5b  mov     rcx, rbx; this
0x14000be5e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000be63  mov     eax, edi
0x14000be65  jmp     loc_14000BEED
0x14000be6a  mov     rcx, [rsp+280h+var_240]
0x14000be6f  test    rcx, rcx
0x14000be72  jz      short loc_14000BE7F
0x14000be74  mov     [rsi], rcx
0x14000be77  mov     eax, [rcx]
0x14000be79  inc     eax
0x14000be7b  mov     [rcx], eax
0x14000be7d  jmp     short loc_14000BED4
0x14000be7f  mov     r8, rsi
0x14000be82  lea     rdx, [rsp+280h+var_250]
0x14000be87  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000be8c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000be91  mov     ebx, eax
0x14000be93  test    eax, eax
0x14000be95  jns     short loc_14000BECF
0x14000be97  mov     rcx, [rbp+188h]; this
0x14000be9e  lea     r8, aWil; "wil"
0x14000bea5  mov     r9d, eax; char *
0x14000bea8  mov     edx, 137h; void *
0x14000bead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000beb2  lea     rcx, [rsp+280h+var_248]
0x14000beb7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bebc  mov     rcx, [rsp+280h+var_250]; this
0x14000bec1  test    rcx, rcx
0x14000bec4  jz      short loc_14000BECB
0x14000bec6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000becb  mov     eax, ebx
0x14000becd  jmp     short loc_14000BEED
0x14000becf  mov     rbx, [rsp+280h+var_250]
0x14000bed4  lea     rcx, [rsp+280h+var_248]
0x14000bed9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000bede  test    rbx, rbx
0x14000bee1  jz      short loc_14000BEEB
0x14000bee3  mov     rcx, rbx; this
0x14000bee6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000beeb  xor     eax, eax
0x14000beed  mov     rcx, [rbp+180h+var_20]
0x14000bef4  xor     rcx, rsp; StackCookie
0x14000bef7  call    __security_check_cookie
0x14000befc  mov     rbx, [rsp+280h+arg_10]
0x14000bf04  add     rsp, 270h
0x14000bf0b  pop     rdi
0x14000bf0c  pop     rsi
0x14000bf0d  pop     rbp
0x14000bf0e  retn
```
