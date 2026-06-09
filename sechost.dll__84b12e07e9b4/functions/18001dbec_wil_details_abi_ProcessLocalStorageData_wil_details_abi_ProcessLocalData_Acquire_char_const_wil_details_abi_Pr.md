# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001dbec`
- end: `0x18001dd81`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001e63c`

## callees

- `0x18001b194`
- `0x18001c370`
- `0x18001db6c`
- `0x18001db88`
- `0x18001dbec`
- `0x18001eb9c`
- `0x18001f044`
- `0x18001f378`
- `0x18001f5a4`
- `0x18001f650`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dc24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dc24`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dc69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001dc69`

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
0x18001dbec  mov     [rsp-8+arg_10], rbx
0x18001dbf1  mov     [rsp-8+arg_18], rdi
0x18001dbf6  push    rbp
0x18001dbf7  lea     rbp, [rsp-170h]
0x18001dbff  sub     rsp, 270h
0x18001dc06  mov     rax, cs:__security_cookie
0x18001dc0d  xor     rax, rsp
0x18001dc10  mov     [rbp+170h+var_10], rax
0x18001dc17  mov     rdi, rdx
0x18001dc1a  mov     qword ptr [rdx], 0
0x18001dc21  mov     rbx, rcx
0x18001dc24  call    cs:__imp_GetCurrentProcessId
0x18001dc2a  mov     [rsp+270h+var_248], rbx
0x18001dc2f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001dc36  mov     r9d, eax
0x18001dc39  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001dc41  mov     edx, 104h; unsigned __int64
0x18001dc46  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dc4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dc50  mov     r9d, 1F0001h; dwDesiredAccess
0x18001dc56  mov     [rsp+270h+var_240], 0
0x18001dc5f  xor     r8d, r8d; dwFlags
0x18001dc62  lea     rdx, [rsp+270h+Name]; lpName
0x18001dc67  xor     ecx, ecx; lpMutexAttributes
0x18001dc69  call    cs:__imp_CreateMutexExW
0x18001dc6f  mov     rdx, rax
0x18001dc72  lea     rcx, [rsp+270h+var_240]
0x18001dc77  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001dc7c  cmp     [rsp+270h+var_240], 0
0x18001dc82  jnz     short loc_18001DC90
0x18001dc84  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001dc89  mov     ebx, eax
0x18001dc8b  jmp     loc_18001DD2C
0x18001dc90  lea     rdx, [rsp+270h+var_238]
0x18001dc95  lea     rcx, [rsp+270h+var_240]
0x18001dc9a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001dc9f  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18001dca4  mov     [rsp+270h+var_230], 0
0x18001dcad  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dcb2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001dcb7  mov     ebx, eax
0x18001dcb9  test    eax, eax
0x18001dcbb  jns     short loc_18001DD05
0x18001dcbd  mov     rcx, [rbp+178h]; this
0x18001dcc4  mov     r9d, eax; char *
0x18001dcc7  mov     edx, 66h ; 'f'; void *
0x18001dccc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcd1  mov     rcx, [rbp+178h]; this
0x18001dcd8  mov     r9d, ebx; char *
0x18001dcdb  mov     edx, 6Fh ; 'o'; void *
0x18001dce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dce5  mov     r9d, ebx; char *
0x18001dce8  mov     edx, 12Eh; void *
0x18001dced  mov     rcx, [rbp+178h]; this
0x18001dcf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcf9  lea     rcx, [rsp+270h+var_238]
0x18001dcfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dd03  jmp     short loc_18001DD2C
0x18001dd05  mov     rax, [rsp+270h+var_230]
0x18001dd0a  lea     rcx, ds:0[rax*4]
0x18001dd12  test    rcx, rcx
0x18001dd15  jz      short loc_18001DD5C
0x18001dd17  mov     [rdi], rcx
0x18001dd1a  mov     eax, [rcx]
0x18001dd1c  inc     eax
0x18001dd1e  mov     [rcx], eax
0x18001dd20  lea     rcx, [rsp+270h+var_238]
0x18001dd25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dd2a  xor     ebx, ebx
0x18001dd2c  lea     rcx, [rsp+270h+var_240]
0x18001dd31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dd36  mov     eax, ebx
0x18001dd38  mov     rcx, [rbp+170h+var_10]
0x18001dd3f  xor     rcx, rsp; StackCookie
0x18001dd42  call    __security_check_cookie
0x18001dd47  lea     r11, [rsp+270h+var_s0]
0x18001dd4f  mov     rbx, [r11+20h]
0x18001dd53  mov     rdi, [r11+28h]
0x18001dd57  mov     rsp, r11
0x18001dd5a  pop     rbp
0x18001dd5b  retn
0x18001dd5c  mov     r8, rdi
0x18001dd5f  lea     rdx, [rsp+270h+var_240]
0x18001dd64  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dd69  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001dd6e  mov     ebx, eax
0x18001dd70  test    eax, eax
0x18001dd72  jns     short loc_18001DD20
0x18001dd74  mov     r9d, eax
0x18001dd77  mov     edx, 137h
0x18001dd7c  jmp     loc_18001DCED
```
