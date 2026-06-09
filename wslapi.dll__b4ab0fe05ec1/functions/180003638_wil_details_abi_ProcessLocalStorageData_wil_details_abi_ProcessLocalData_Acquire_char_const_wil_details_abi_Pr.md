# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003638`
- end: `0x1800037eb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `435`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000413c`

## callees

- `0x180001dc0`
- `0x1800034e4`
- `0x180003500`
- `0x180003638`
- `0x180003ef8`
- `0x1800048b8`
- `0x180004fd4`
- `0x18000552c`
- `0x1800056a8`
- `0x1800059d8`
- `0x180005acc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003670`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003670`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  bool v8; // dl
  bool *v9; // r9
  int ValueInternal; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _DWORD *v13; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v16 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v18 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v18,
    Mutex);
  if ( v18 )
  {
    v19 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v18,
      &v19);
    v20 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v8, &v20, v9);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v17);
      v11 = LastErrorFailHr;
      v12 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v12, (unsigned int)"wil", (const char *)v11, v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
      goto LABEL_9;
    }
    v13 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v13;
      ++*v13;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v15;
      if ( v15 < 0 )
      {
        v11 = (unsigned int)v15;
        v12 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v18,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003638  mov     [rsp-8+arg_10], rbx
0x18000363d  mov     [rsp-8+arg_18], rdi
0x180003642  push    rbp
0x180003643  lea     rbp, [rsp-170h]
0x18000364b  sub     rsp, 270h
0x180003652  mov     rax, cs:__security_cookie
0x180003659  xor     rax, rsp
0x18000365c  mov     [rbp+170h+var_10], rax
0x180003663  mov     rdi, rdx
0x180003666  mov     qword ptr [rdx], 0
0x18000366d  mov     rbx, rcx
0x180003670  call    cs:__imp_GetCurrentProcessId
0x180003676  mov     [rsp+270h+var_248], rbx
0x18000367b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003682  mov     r9d, eax
0x180003685  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000368d  mov     edx, 104h; unsigned __int64
0x180003692  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003697  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000369c  mov     r9d, 1F0001h; dwDesiredAccess
0x1800036a2  mov     [rsp+270h+var_240], 0
0x1800036ab  xor     r8d, r8d; dwFlags
0x1800036ae  lea     rdx, [rsp+270h+Name]; lpName
0x1800036b3  xor     ecx, ecx; lpMutexAttributes
0x1800036b5  call    cs:__imp_CreateMutexExW
0x1800036bb  mov     rdx, rax
0x1800036be  lea     rcx, [rsp+270h+var_240]
0x1800036c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800036c8  cmp     [rsp+270h+var_240], 0
0x1800036ce  jnz     short loc_1800036DC
0x1800036d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800036d5  mov     ebx, eax
0x1800036d7  jmp     loc_180003796
0x1800036dc  lea     rdx, [rsp+270h+var_238]
0x1800036e1  mov     [rsp+270h+var_238], 0
0x1800036ea  lea     rcx, [rsp+270h+var_240]
0x1800036ef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800036f4  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x1800036f9  mov     [rsp+270h+var_230], 0
0x180003702  lea     rcx, [rsp+270h+Name]; pszSrc
0x180003707  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000370c  mov     ebx, eax
0x18000370e  test    eax, eax
0x180003710  jns     short loc_18000376F
0x180003712  mov     rcx, [rbp+178h]; this
0x180003719  lea     r8, aWil; "wil"
0x180003720  mov     r9d, eax; char *
0x180003723  mov     edx, 66h ; 'f'; void *
0x180003728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000372d  mov     rcx, [rbp+178h]; this
0x180003734  lea     r8, aWil; "wil"
0x18000373b  mov     r9d, ebx; char *
0x18000373e  mov     edx, 6Fh ; 'o'; void *
0x180003743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003748  mov     r9d, ebx; char *
0x18000374b  mov     edx, 12Eh; void *
0x180003750  mov     rcx, [rbp+178h]; this
0x180003757  lea     r8, aWil; "wil"
0x18000375e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003763  lea     rcx, [rsp+270h+var_238]
0x180003768  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000376d  jmp     short loc_180003796
0x18000376f  mov     rax, [rsp+270h+var_230]
0x180003774  lea     rcx, ds:0[rax*4]
0x18000377c  test    rcx, rcx
0x18000377f  jz      short loc_1800037C6
0x180003781  mov     [rdi], rcx
0x180003784  mov     eax, [rcx]
0x180003786  inc     eax
0x180003788  mov     [rcx], eax
0x18000378a  lea     rcx, [rsp+270h+var_238]
0x18000378f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003794  xor     ebx, ebx
0x180003796  lea     rcx, [rsp+270h+var_240]
0x18000379b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800037a0  mov     eax, ebx
0x1800037a2  mov     rcx, [rbp+170h+var_10]
0x1800037a9  xor     rcx, rsp; StackCookie
0x1800037ac  call    __security_check_cookie
0x1800037b1  lea     r11, [rsp+270h+var_s0]
0x1800037b9  mov     rbx, [r11+20h]
0x1800037bd  mov     rdi, [r11+28h]
0x1800037c1  mov     rsp, r11
0x1800037c4  pop     rbp
0x1800037c5  retn
0x1800037c6  mov     r8, rdi
0x1800037c9  lea     rdx, [rsp+270h+var_240]
0x1800037ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800037d3  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800037d8  mov     ebx, eax
0x1800037da  test    eax, eax
0x1800037dc  jns     short loc_18000378A
0x1800037de  mov     r9d, eax
0x1800037e1  mov     edx, 137h
0x1800037e6  jmp     loc_180003750
```
