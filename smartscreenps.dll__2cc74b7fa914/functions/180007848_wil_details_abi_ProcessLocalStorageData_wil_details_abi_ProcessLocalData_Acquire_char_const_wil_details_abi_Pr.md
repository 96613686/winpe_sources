# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007848`
- end: `0x1800079f2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008328`

## callees

- `0x180001590`
- `0x1800076fc`
- `0x180007718`
- `0x180007848`
- `0x180008088`
- `0x180008acc`
- `0x180009094`
- `0x1800095ec`
- `0x180009798`
- `0x180009ab0`
- `0x180009ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800078c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800078c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007880`

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
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  _DWORD *v12; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v15 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v17 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v17,
    Mutex);
  if ( v17 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v17,
      v18);
    v19 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v19, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueInternal,
        120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastErrorFailHr, v16);
      v10 = LastErrorFailHr;
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (unsigned int)"wil", (const char *)v10, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
      goto LABEL_9;
    }
    v12 = (_DWORD *)(4 * v19);
    if ( 4 * v19 )
    {
      *a2 = v12;
      ++*v12;
    }
    else
    {
      v14 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v14;
      if ( v14 < 0 )
      {
        v10 = (unsigned int)v14;
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180007848  mov     [rsp-8+arg_10], rbx
0x18000784d  mov     [rsp-8+arg_18], rdi
0x180007852  push    rbp
0x180007853  lea     rbp, [rsp-170h]
0x18000785b  sub     rsp, 270h
0x180007862  mov     rax, cs:__security_cookie
0x180007869  xor     rax, rsp
0x18000786c  mov     [rbp+170h+var_10], rax
0x180007873  mov     rdi, rdx
0x180007876  mov     qword ptr [rdx], 0
0x18000787d  mov     rbx, rcx
0x180007880  call    cs:__imp_GetCurrentProcessId
0x180007886  mov     [rsp+270h+var_248], rbx
0x18000788b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007892  mov     r9d, eax
0x180007895  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000789d  mov     edx, 104h; unsigned __int64
0x1800078a2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800078a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800078ac  mov     r9d, 1F0001h; dwDesiredAccess
0x1800078b2  mov     [rsp+270h+var_240], 0
0x1800078bb  xor     r8d, r8d; dwFlags
0x1800078be  lea     rdx, [rsp+270h+Name]; lpName
0x1800078c3  xor     ecx, ecx; lpMutexAttributes
0x1800078c5  call    cs:__imp_CreateMutexExW
0x1800078cb  mov     rdx, rax
0x1800078ce  lea     rcx, [rsp+270h+var_240]
0x1800078d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800078d8  cmp     [rsp+270h+var_240], 0
0x1800078de  jnz     short loc_1800078EC
0x1800078e0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800078e5  mov     ebx, eax
0x1800078e7  jmp     loc_18000799D
0x1800078ec  lea     rdx, [rsp+270h+var_238]
0x1800078f1  lea     rcx, [rsp+270h+var_240]
0x1800078f6  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800078fb  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x180007900  mov     [rsp+270h+var_230], 0
0x180007909  lea     rcx, [rsp+270h+Name]; pszSrc
0x18000790e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007913  mov     ebx, eax
0x180007915  test    eax, eax
0x180007917  jns     short loc_180007976
0x180007919  mov     rcx, [rbp+178h]; this
0x180007920  lea     r8, aWil; "wil"
0x180007927  mov     r9d, eax; char *
0x18000792a  mov     edx, 66h ; 'f'; void *
0x18000792f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007934  mov     rcx, [rbp+178h]; this
0x18000793b  lea     r8, aWil; "wil"
0x180007942  mov     r9d, ebx; char *
0x180007945  mov     edx, 6Fh ; 'o'; void *
0x18000794a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000794f  mov     r9d, ebx; char *
0x180007952  mov     edx, 12Eh; void *
0x180007957  mov     rcx, [rbp+178h]; this
0x18000795e  lea     r8, aWil; "wil"
0x180007965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000796a  lea     rcx, [rsp+270h+var_238]
0x18000796f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007974  jmp     short loc_18000799D
0x180007976  mov     rax, [rsp+270h+var_230]
0x18000797b  lea     rcx, ds:0[rax*4]
0x180007983  test    rcx, rcx
0x180007986  jz      short loc_1800079CD
0x180007988  mov     [rdi], rcx
0x18000798b  mov     eax, [rcx]
0x18000798d  inc     eax
0x18000798f  mov     [rcx], eax
0x180007991  lea     rcx, [rsp+270h+var_238]
0x180007996  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000799b  xor     ebx, ebx
0x18000799d  lea     rcx, [rsp+270h+var_240]
0x1800079a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800079a7  mov     eax, ebx
0x1800079a9  mov     rcx, [rbp+170h+var_10]
0x1800079b0  xor     rcx, rsp; StackCookie
0x1800079b3  call    __security_check_cookie
0x1800079b8  lea     r11, [rsp+270h+var_s0]
0x1800079c0  mov     rbx, [r11+20h]
0x1800079c4  mov     rdi, [r11+28h]
0x1800079c8  mov     rsp, r11
0x1800079cb  pop     rbp
0x1800079cc  retn
0x1800079cd  mov     r8, rdi
0x1800079d0  lea     rdx, [rsp+270h+var_240]
0x1800079d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800079da  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800079df  mov     ebx, eax
0x1800079e1  test    eax, eax
0x1800079e3  jns     short loc_180007991
0x1800079e5  mov     r9d, eax
0x1800079e8  mov     edx, 137h
0x1800079ed  jmp     loc_180007957
```
