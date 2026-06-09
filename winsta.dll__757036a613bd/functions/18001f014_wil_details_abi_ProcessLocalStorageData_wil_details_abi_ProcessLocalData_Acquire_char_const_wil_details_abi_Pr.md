# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001f014`
- end: `0x18001f1b3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002680c`

## callees

- `0x18000c368`
- `0x18000e350`
- `0x18000e36c`
- `0x1800116d4`
- `0x1800127fc`
- `0x1800129f8`
- `0x18001f014`
- `0x18001f1bc`
- `0x18001f234`
- `0x180026c44`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f04c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f04c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f091`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001f091`

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
0x18001f014  mov     [rsp-8+arg_10], rbx
0x18001f019  mov     [rsp-8+arg_18], rdi
0x18001f01e  push    rbp
0x18001f01f  lea     rbp, [rsp-170h]
0x18001f027  sub     rsp, 270h
0x18001f02e  mov     rax, cs:__security_cookie
0x18001f035  xor     rax, rsp
0x18001f038  mov     [rbp+170h+var_10], rax
0x18001f03f  mov     rdi, rdx
0x18001f042  mov     qword ptr [rdx], 0
0x18001f049  mov     rbx, rcx
0x18001f04c  call    cs:__imp_GetCurrentProcessId
0x18001f052  mov     [rsp+270h+var_248], rbx
0x18001f057  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001f05e  mov     r9d, eax
0x18001f061  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001f069  mov     edx, 104h; unsigned __int64
0x18001f06e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f073  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f078  mov     r9d, 1F0001h; dwDesiredAccess
0x18001f07e  mov     [rsp+270h+var_240], 0
0x18001f087  xor     r8d, r8d; dwFlags
0x18001f08a  lea     rdx, [rsp+270h+Name]; lpName
0x18001f08f  xor     ecx, ecx; lpMutexAttributes
0x18001f091  call    cs:__imp_CreateMutexExW
0x18001f097  mov     rdx, rax
0x18001f09a  lea     rcx, [rsp+270h+var_240]
0x18001f09f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001f0a4  cmp     [rsp+270h+var_240], 0
0x18001f0aa  jnz     short loc_18001F0B8
0x18001f0ac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001f0b1  mov     ebx, eax
0x18001f0b3  jmp     loc_18001F15E
0x18001f0b8  lea     rdx, [rsp+270h+var_238]
0x18001f0bd  lea     rcx, [rsp+270h+var_240]
0x18001f0c2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001f0c7  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x18001f0cc  mov     [rsp+270h+var_230], 0
0x18001f0d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f0da  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001f0df  mov     ebx, eax
0x18001f0e1  test    eax, eax
0x18001f0e3  jns     short loc_18001F132
0x18001f0e5  mov     rcx, [rbp+178h]; this
0x18001f0ec  mov     r9d, eax; char *
0x18001f0ef  mov     edx, 66h ; 'f'; void *
0x18001f0f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0f9  mov     rcx, [rbp+178h]; this
0x18001f100  mov     r9d, ebx; char *
0x18001f103  mov     edx, 6Fh ; 'o'; void *
0x18001f108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f10d  mov     r9d, ebx; char *
0x18001f110  mov     edx, 12Eh; void *
0x18001f115  mov     rcx, [rbp+178h]; this
0x18001f11c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f121  mov     rcx, [rsp+270h+var_238]; this
0x18001f126  test    rcx, rcx
0x18001f129  jz      short loc_18001F15E
0x18001f12b  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001f130  jmp     short loc_18001F15E
0x18001f132  mov     rax, [rsp+270h+var_230]
0x18001f137  lea     rcx, ds:0[rax*4]
0x18001f13f  test    rcx, rcx
0x18001f142  jz      short loc_18001F18E
0x18001f144  mov     [rdi], rcx
0x18001f147  mov     eax, [rcx]
0x18001f149  inc     eax
0x18001f14b  mov     [rcx], eax
0x18001f14d  mov     rcx, [rsp+270h+var_238]; this
0x18001f152  test    rcx, rcx
0x18001f155  jz      short loc_18001F15C
0x18001f157  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001f15c  xor     ebx, ebx
0x18001f15e  lea     rcx, [rsp+270h+var_240]
0x18001f163  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f168  mov     eax, ebx
0x18001f16a  mov     rcx, [rbp+170h+var_10]
0x18001f171  xor     rcx, rsp; StackCookie
0x18001f174  call    __security_check_cookie
0x18001f179  lea     r11, [rsp+270h+var_s0]
0x18001f181  mov     rbx, [r11+20h]
0x18001f185  mov     rdi, [r11+28h]
0x18001f189  mov     rsp, r11
0x18001f18c  pop     rbp
0x18001f18d  retn
0x18001f18e  mov     r8, rdi
0x18001f191  lea     rdx, [rsp+270h+var_240]
0x18001f196  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001f19b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001f1a0  mov     ebx, eax
0x18001f1a2  test    eax, eax
0x18001f1a4  jns     short loc_18001F14D
0x18001f1a6  mov     r9d, eax
0x18001f1a9  mov     edx, 137h
0x18001f1ae  jmp     loc_18001F115
```
