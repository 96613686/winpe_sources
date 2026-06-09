# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800d72a8`
- end: `0x1800d743d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800d7d74`

## callees

- `0x1800034b0`
- `0x1800060c0`
- `0x1800d7150`
- `0x1800d716c`
- `0x1800d72a8`
- `0x1800d7b18`
- `0x1800d8498`
- `0x1800d8924`
- `0x1800d8e5c`
- `0x1800d91fc`
- `0x1800d9300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800d7325`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800d7325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d72e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d72e0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800d72a8  mov     [rsp-8+arg_10], rbx
0x1800d72ad  mov     [rsp-8+arg_18], rdi
0x1800d72b2  push    rbp
0x1800d72b3  lea     rbp, [rsp-170h]
0x1800d72bb  sub     rsp, 270h
0x1800d72c2  mov     rax, cs:__security_cookie
0x1800d72c9  xor     rax, rsp
0x1800d72cc  mov     [rbp+170h+var_10], rax
0x1800d72d3  mov     rdi, rdx
0x1800d72d6  mov     qword ptr [rdx], 0
0x1800d72dd  mov     rbx, rcx
0x1800d72e0  call    cs:__imp_GetCurrentProcessId
0x1800d72e6  mov     [rsp+270h+var_248], rbx
0x1800d72eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800d72f2  mov     r9d, eax
0x1800d72f5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800d72fd  mov     edx, 104h; unsigned __int64
0x1800d7302  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d7307  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d730c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800d7312  mov     [rsp+270h+var_240], 0
0x1800d731b  xor     r8d, r8d; dwFlags
0x1800d731e  lea     rdx, [rsp+270h+Name]; lpName
0x1800d7323  xor     ecx, ecx; lpMutexAttributes
0x1800d7325  call    cs:__imp_CreateMutexExW
0x1800d732b  mov     rdx, rax
0x1800d732e  lea     rcx, [rsp+270h+var_240]
0x1800d7333  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800d7338  cmp     [rsp+270h+var_240], 0
0x1800d733e  jnz     short loc_1800D734C
0x1800d7340  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800d7345  mov     ebx, eax
0x1800d7347  jmp     loc_1800D73E8
0x1800d734c  lea     rdx, [rsp+270h+var_238]
0x1800d7351  lea     rcx, [rsp+270h+var_240]
0x1800d7356  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800d735b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800d7360  mov     [rsp+270h+var_230], 0
0x1800d7369  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d736e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800d7373  mov     ebx, eax
0x1800d7375  test    eax, eax
0x1800d7377  jns     short loc_1800D73C1
0x1800d7379  mov     rcx, [rbp+178h]; this
0x1800d7380  mov     r9d, eax; char *
0x1800d7383  mov     edx, 66h ; 'f'; void *
0x1800d7388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d738d  mov     rcx, [rbp+178h]; this
0x1800d7394  mov     r9d, ebx; char *
0x1800d7397  mov     edx, 6Fh ; 'o'; void *
0x1800d739c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d73a1  mov     r9d, ebx; char *
0x1800d73a4  mov     edx, 12Eh; void *
0x1800d73a9  mov     rcx, [rbp+178h]; this
0x1800d73b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d73b5  lea     rcx, [rsp+270h+var_238]
0x1800d73ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d73bf  jmp     short loc_1800D73E8
0x1800d73c1  mov     rax, [rsp+270h+var_230]
0x1800d73c6  lea     rcx, ds:0[rax*4]
0x1800d73ce  test    rcx, rcx
0x1800d73d1  jz      short loc_1800D7418
0x1800d73d3  mov     [rdi], rcx
0x1800d73d6  mov     eax, [rcx]
0x1800d73d8  inc     eax
0x1800d73da  mov     [rcx], eax
0x1800d73dc  lea     rcx, [rsp+270h+var_238]
0x1800d73e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d73e6  xor     ebx, ebx
0x1800d73e8  lea     rcx, [rsp+270h+var_240]
0x1800d73ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800d73f2  mov     eax, ebx
0x1800d73f4  mov     rcx, [rbp+170h+var_10]
0x1800d73fb  xor     rcx, rsp; StackCookie
0x1800d73fe  call    __security_check_cookie
0x1800d7403  lea     r11, [rsp+270h+var_s0]
0x1800d740b  mov     rbx, [r11+20h]
0x1800d740f  mov     rdi, [r11+28h]
0x1800d7413  mov     rsp, r11
0x1800d7416  pop     rbp
0x1800d7417  retn
0x1800d7418  mov     r8, rdi
0x1800d741b  lea     rdx, [rsp+270h+var_240]
0x1800d7420  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800d7425  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800d742a  mov     ebx, eax
0x1800d742c  test    eax, eax
0x1800d742e  jns     short loc_1800D73DC
0x1800d7430  mov     r9d, eax
0x1800d7433  mov     edx, 137h
0x1800d7438  jmp     loc_1800D73A9
```
