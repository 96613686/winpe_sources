# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180020678`
- end: `0x180020824`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180028260`

## callees

- `0x18000df38`
- `0x18000e568`
- `0x18000e588`
- `0x180012408`
- `0x180013178`
- `0x18001385c`
- `0x180020678`
- `0x18002082c`
- `0x1800208a8`
- `0x1800286b4`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800206b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800206b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800206fb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800206fb`

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
  void *v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  void *v16; // rdx
  _DWORD *v17; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v20 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v22 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v22,
    Mutex);
  if ( !v22 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_12;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v22,
    &v23);
  v24 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v24, v8);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v11, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v12, (const char *)LastErrorFailHr, v21);
    v14 = LastErrorFailHr;
    v15 = 302;
    goto LABEL_5;
  }
  v17 = (_DWORD *)(4 * v24);
  if ( 4 * v24 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v19 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v19;
    if ( v19 < 0 )
    {
      v14 = (unsigned int)v19;
      v15 = 311;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v15, v13, (const char *)v14, v20);
      if ( v23 )
        wil::details::ReleaseMutex(v23, v16);
      goto LABEL_12;
    }
  }
  if ( v23 )
    wil::details::ReleaseMutex(v23, v10);
  LastErrorFailHr = 0;
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180020678  mov     [rsp-8+arg_10], rbx
0x18002067d  mov     [rsp-8+arg_18], rdi
0x180020682  push    rbp
0x180020683  lea     rbp, [rsp-170h]
0x18002068b  sub     rsp, 270h
0x180020692  mov     rax, cs:__security_cookie
0x180020699  xor     rax, rsp
0x18002069c  mov     [rbp+170h+var_10], rax
0x1800206a3  mov     rdi, rdx
0x1800206a6  mov     qword ptr [rdx], 0
0x1800206ad  mov     rbx, rcx
0x1800206b0  call    cs:__imp_GetCurrentProcessId
0x1800206b7  nop     dword ptr [rax+rax+00h]
0x1800206bc  mov     [rsp+270h+var_248], rbx
0x1800206c1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800206c8  mov     r9d, eax
0x1800206cb  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800206d3  mov     edx, 104h; unsigned __int64
0x1800206d8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800206dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800206e2  mov     r9d, 1F0001h; dwDesiredAccess
0x1800206e8  mov     [rsp+270h+var_240], 0
0x1800206f1  xor     r8d, r8d; dwFlags
0x1800206f4  lea     rdx, [rsp+270h+Name]; lpName
0x1800206f9  xor     ecx, ecx; lpMutexAttributes
0x1800206fb  call    cs:__imp_CreateMutexExW
0x180020702  nop     dword ptr [rax+rax+00h]
0x180020707  mov     rdx, rax
0x18002070a  lea     rcx, [rsp+270h+var_240]
0x18002070f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020714  cmp     [rsp+270h+var_240], 0
0x18002071a  jnz     short loc_180020728
0x18002071c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020721  mov     ebx, eax
0x180020723  jmp     loc_1800207CE
0x180020728  lea     rdx, [rsp+270h+var_238]
0x18002072d  lea     rcx, [rsp+270h+var_240]
0x180020732  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180020737  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18002073c  mov     [rsp+270h+var_230], 0
0x180020745  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002074a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002074f  mov     ebx, eax
0x180020751  test    eax, eax
0x180020753  jns     short loc_1800207A2
0x180020755  mov     rcx, [rbp+178h]; this
0x18002075c  mov     r9d, eax; char *
0x18002075f  mov     edx, 66h ; 'f'; void *
0x180020764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020769  mov     rcx, [rbp+178h]; this
0x180020770  mov     r9d, ebx; char *
0x180020773  mov     edx, 6Fh ; 'o'; void *
0x180020778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002077d  mov     r9d, ebx; char *
0x180020780  mov     edx, 12Eh; void *
0x180020785  mov     rcx, [rbp+178h]; this
0x18002078c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020791  mov     rcx, [rsp+270h+var_238]; this
0x180020796  test    rcx, rcx
0x180020799  jz      short loc_1800207CE
0x18002079b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800207a0  jmp     short loc_1800207CE
0x1800207a2  mov     rax, [rsp+270h+var_230]
0x1800207a7  lea     rcx, ds:0[rax*4]
0x1800207af  test    rcx, rcx
0x1800207b2  jz      short loc_1800207FF
0x1800207b4  mov     [rdi], rcx
0x1800207b7  mov     eax, [rcx]
0x1800207b9  inc     eax
0x1800207bb  mov     [rcx], eax
0x1800207bd  mov     rcx, [rsp+270h+var_238]; this
0x1800207c2  test    rcx, rcx
0x1800207c5  jz      short loc_1800207CC
0x1800207c7  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800207cc  xor     ebx, ebx
0x1800207ce  lea     rcx, [rsp+270h+var_240]
0x1800207d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800207d8  mov     eax, ebx
0x1800207da  mov     rcx, [rbp+170h+var_10]
0x1800207e1  xor     rcx, rsp; StackCookie
0x1800207e4  call    __security_check_cookie
0x1800207e9  lea     r11, [rsp+270h+var_s0]
0x1800207f1  mov     rbx, [r11+20h]
0x1800207f5  mov     rdi, [r11+28h]
0x1800207f9  mov     rsp, r11
0x1800207fc  pop     rbp
0x1800207fd  retn
0x1800207ff  mov     r8, rdi
0x180020802  lea     rdx, [rsp+270h+var_240]
0x180020807  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002080c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180020811  mov     ebx, eax
0x180020813  test    eax, eax
0x180020815  jns     short loc_1800207BD
0x180020817  mov     r9d, eax
0x18002081a  mov     edx, 137h
0x18002081f  jmp     loc_180020785
```
