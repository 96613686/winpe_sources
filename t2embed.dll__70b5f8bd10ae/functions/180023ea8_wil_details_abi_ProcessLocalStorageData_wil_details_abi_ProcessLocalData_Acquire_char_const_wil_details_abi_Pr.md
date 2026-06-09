# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180023ea8`
- end: `0x18002403d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002492c`

## callees

- `0x180023ce0`
- `0x180023cfc`
- `0x180023ea8`
- `0x1800246e8`
- `0x180025070`
- `0x180025a84`
- `0x180026b20`
- `0x180026c30`
- `0x180026ff0`
- `0x18002709c`
- `0x18002a590`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180023f25`
- `KERNEL32!CreateMutexExW` at `0x180023f25`
- `KERNEL32!GetCurrentProcessId` at `0x180023ee0`
- `KERNEL32!GetCurrentProcessId` at `0x180023ee0`

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
0x180023ea8  mov     [rsp-8+arg_10], rbx
0x180023ead  mov     [rsp-8+arg_18], rdi
0x180023eb2  push    rbp
0x180023eb3  lea     rbp, [rsp-170h]
0x180023ebb  sub     rsp, 270h
0x180023ec2  mov     rax, cs:__security_cookie
0x180023ec9  xor     rax, rsp
0x180023ecc  mov     [rbp+170h+var_10], rax
0x180023ed3  mov     rdi, rdx
0x180023ed6  mov     qword ptr [rdx], 0
0x180023edd  mov     rbx, rcx
0x180023ee0  call    cs:__imp_GetCurrentProcessId
0x180023ee6  mov     [rsp+270h+var_248], rbx
0x180023eeb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023ef2  mov     r9d, eax
0x180023ef5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180023efd  mov     edx, 104h; unsigned __int64
0x180023f02  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023f07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023f0c  mov     r9d, 1F0001h; dwDesiredAccess
0x180023f12  mov     [rsp+270h+var_240], 0
0x180023f1b  xor     r8d, r8d; dwFlags
0x180023f1e  lea     rdx, [rsp+270h+Name]; lpName
0x180023f23  xor     ecx, ecx; lpMutexAttributes
0x180023f25  call    cs:__imp_CreateMutexExW
0x180023f2b  mov     rdx, rax
0x180023f2e  lea     rcx, [rsp+270h+var_240]
0x180023f33  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023f38  cmp     [rsp+270h+var_240], 0
0x180023f3e  jnz     short loc_180023F4C
0x180023f40  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023f45  mov     ebx, eax
0x180023f47  jmp     loc_180023FE8
0x180023f4c  lea     rdx, [rsp+270h+var_238]
0x180023f51  lea     rcx, [rsp+270h+var_240]
0x180023f56  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023f5b  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180023f60  mov     [rsp+270h+var_230], 0
0x180023f69  lea     rcx, [rsp+270h+Name]; pszSrc
0x180023f6e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180023f73  mov     ebx, eax
0x180023f75  test    eax, eax
0x180023f77  jns     short loc_180023FC1
0x180023f79  mov     rcx, [rbp+178h]; this
0x180023f80  mov     r9d, eax; char *
0x180023f83  mov     edx, 66h ; 'f'; void *
0x180023f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f8d  mov     rcx, [rbp+178h]; this
0x180023f94  mov     r9d, ebx; char *
0x180023f97  mov     edx, 6Fh ; 'o'; void *
0x180023f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fa1  mov     r9d, ebx; char *
0x180023fa4  mov     edx, 12Eh; void *
0x180023fa9  mov     rcx, [rbp+178h]; this
0x180023fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fb5  lea     rcx, [rsp+270h+var_238]
0x180023fba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023fbf  jmp     short loc_180023FE8
0x180023fc1  mov     rax, [rsp+270h+var_230]
0x180023fc6  lea     rcx, ds:0[rax*4]
0x180023fce  test    rcx, rcx
0x180023fd1  jz      short loc_180024018
0x180023fd3  mov     [rdi], rcx
0x180023fd6  mov     eax, [rcx]
0x180023fd8  inc     eax
0x180023fda  mov     [rcx], eax
0x180023fdc  lea     rcx, [rsp+270h+var_238]
0x180023fe1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023fe6  xor     ebx, ebx
0x180023fe8  lea     rcx, [rsp+270h+var_240]
0x180023fed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023ff2  mov     eax, ebx
0x180023ff4  mov     rcx, [rbp+170h+var_10]
0x180023ffb  xor     rcx, rsp; StackCookie
0x180023ffe  call    __security_check_cookie
0x180024003  lea     r11, [rsp+270h+var_s0]
0x18002400b  mov     rbx, [r11+20h]
0x18002400f  mov     rdi, [r11+28h]
0x180024013  mov     rsp, r11
0x180024016  pop     rbp
0x180024017  retn
0x180024018  mov     r8, rdi
0x18002401b  lea     rdx, [rsp+270h+var_240]
0x180024020  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180024025  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002402a  mov     ebx, eax
0x18002402c  test    eax, eax
0x18002402e  jns     short loc_180023FDC
0x180024030  mov     r9d, eax
0x180024033  mov     edx, 137h
0x180024038  jmp     loc_180023FA9
```
