# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180015490`
- end: `0x180015625`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180015ac8`

## callees

- `0x180005718`
- `0x180015410`
- `0x18001542c`
- `0x180015490`
- `0x180015954`
- `0x180015fd8`
- `0x180016340`
- `0x18001664c`
- `0x1800168f8`
- `0x1800169b8`
- `0x180016c50`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18001550d`
- `KERNEL32!CreateMutexExW` at `0x18001550d`
- `KERNEL32!GetCurrentProcessId` at `0x1800154c8`
- `KERNEL32!GetCurrentProcessId` at `0x1800154c8`

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
0x180015490  mov     [rsp-8+arg_10], rbx
0x180015495  mov     [rsp-8+arg_18], rdi
0x18001549a  push    rbp
0x18001549b  lea     rbp, [rsp-170h]
0x1800154a3  sub     rsp, 270h
0x1800154aa  mov     rax, cs:__security_cookie
0x1800154b1  xor     rax, rsp
0x1800154b4  mov     [rbp+170h+var_10], rax
0x1800154bb  mov     rdi, rdx
0x1800154be  mov     qword ptr [rdx], 0
0x1800154c5  mov     rbx, rcx
0x1800154c8  call    cs:__imp_GetCurrentProcessId
0x1800154ce  mov     [rsp+270h+var_248], rbx
0x1800154d3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800154da  mov     r9d, eax
0x1800154dd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800154e5  mov     edx, 104h; unsigned __int64
0x1800154ea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800154ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800154f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800154fa  mov     [rsp+270h+var_240], 0
0x180015503  xor     r8d, r8d; dwFlags
0x180015506  lea     rdx, [rsp+270h+Name]; lpName
0x18001550b  xor     ecx, ecx; lpMutexAttributes
0x18001550d  call    cs:__imp_CreateMutexExW
0x180015513  mov     rdx, rax
0x180015516  lea     rcx, [rsp+270h+var_240]
0x18001551b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015520  cmp     [rsp+270h+var_240], 0
0x180015526  jnz     short loc_180015534
0x180015528  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001552d  mov     ebx, eax
0x18001552f  jmp     loc_1800155D0
0x180015534  lea     rdx, [rsp+270h+var_238]
0x180015539  lea     rcx, [rsp+270h+var_240]
0x18001553e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180015543  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180015548  mov     [rsp+270h+var_230], 0
0x180015551  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180015556  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001555b  mov     ebx, eax
0x18001555d  test    eax, eax
0x18001555f  jns     short loc_1800155A9
0x180015561  mov     rcx, [rbp+178h]; this
0x180015568  mov     r9d, eax; char *
0x18001556b  mov     edx, 66h ; 'f'; void *
0x180015570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015575  mov     rcx, [rbp+178h]; this
0x18001557c  mov     r9d, ebx; char *
0x18001557f  mov     edx, 6Fh ; 'o'; void *
0x180015584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015589  mov     r9d, ebx; char *
0x18001558c  mov     edx, 12Eh; void *
0x180015591  mov     rcx, [rbp+178h]; this
0x180015598  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001559d  lea     rcx, [rsp+270h+var_238]
0x1800155a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800155a7  jmp     short loc_1800155D0
0x1800155a9  mov     rax, [rsp+270h+var_230]
0x1800155ae  lea     rcx, ds:0[rax*4]
0x1800155b6  test    rcx, rcx
0x1800155b9  jz      short loc_180015600
0x1800155bb  mov     [rdi], rcx
0x1800155be  mov     eax, [rcx]
0x1800155c0  inc     eax
0x1800155c2  mov     [rcx], eax
0x1800155c4  lea     rcx, [rsp+270h+var_238]
0x1800155c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800155ce  xor     ebx, ebx
0x1800155d0  lea     rcx, [rsp+270h+var_240]
0x1800155d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800155da  mov     eax, ebx
0x1800155dc  mov     rcx, [rbp+170h+var_10]
0x1800155e3  xor     rcx, rsp; StackCookie
0x1800155e6  call    __security_check_cookie
0x1800155eb  lea     r11, [rsp+270h+var_s0]
0x1800155f3  mov     rbx, [r11+20h]
0x1800155f7  mov     rdi, [r11+28h]
0x1800155fb  mov     rsp, r11
0x1800155fe  pop     rbp
0x1800155ff  retn
0x180015600  mov     r8, rdi
0x180015603  lea     rdx, [rsp+270h+var_240]
0x180015608  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001560d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180015612  mov     ebx, eax
0x180015614  test    eax, eax
0x180015616  jns     short loc_1800155C4
0x180015618  mov     r9d, eax
0x18001561b  mov     edx, 137h
0x180015620  jmp     loc_180015591
```
