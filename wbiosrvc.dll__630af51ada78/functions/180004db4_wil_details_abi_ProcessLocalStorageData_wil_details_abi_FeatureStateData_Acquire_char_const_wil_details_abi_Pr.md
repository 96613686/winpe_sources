# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180004db4`
- end: `0x180004fab`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004d5c`

## callees

- `0x1800041d4`
- `0x180004a6c`
- `0x180004db4`
- `0x180005a68`
- `0x180005c34`
- `0x18005388c`
- `0x180056ce0`
- `0x180058948`
- `0x18005cc74`
- `0x180060150`
- `0x1800602b4`
- `0x180060964`
- `0x180068f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004e64`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e34`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004def`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004def`

## string_xrefs

- `0x180004e7f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v23 = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v20);
    v15 = v14;
    v16 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)v15, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return v14;
  }
  v17 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = (unsigned int)v18;
      v16 = 311;
      goto LABEL_14;
    }
    v6 = (wil::details *)hHandle;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x180004db4  mov     [rsp-8+arg_10], rbx
0x180004db9  mov     [rsp-8+arg_18], rsi
0x180004dbe  push    rbp
0x180004dbf  push    rdi
0x180004dc0  push    r14
0x180004dc2  lea     rbp, [rsp-170h]
0x180004dca  sub     rsp, 270h
0x180004dd1  mov     rax, cs:__security_cookie
0x180004dd8  xor     rax, rsp
0x180004ddb  mov     [rbp+180h+var_20], rax
0x180004de2  mov     r14, rdx
0x180004de5  mov     qword ptr [rdx], 0
0x180004dec  mov     rbx, rcx
0x180004def  call    cs:__imp_GetCurrentProcessId
0x180004df5  mov     [rsp+280h+var_258], rbx
0x180004dfa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e01  mov     r9d, eax
0x180004e04  mov     [rsp+280h+var_260], 130h; int
0x180004e0c  mov     edx, 104h; unsigned __int64
0x180004e11  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004e16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004e1b  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e21  mov     [rsp+280h+hHandle], 0
0x180004e2a  xor     r8d, r8d; dwFlags
0x180004e2d  lea     rdx, [rsp+280h+Name]; lpName
0x180004e32  xor     ecx, ecx; lpMutexAttributes
0x180004e34  call    cs:__imp_CreateMutexExW
0x180004e3a  mov     rdx, rax
0x180004e3d  lea     rcx, [rsp+280h+hHandle]
0x180004e42  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004e47  mov     rbx, [rsp+280h+hHandle]
0x180004e4c  test    rbx, rbx
0x180004e4f  jnz     short loc_180004E5B
0x180004e51  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e56  jmp     loc_180004F84
0x180004e5b  xor     r8d, r8d; bAlertable
0x180004e5e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004e61  mov     rcx, rbx; hHandle
0x180004e64  call    cs:__imp_WaitForSingleObjectEx
0x180004e6a  cmp     eax, 102h
0x180004e6f  jz      short loc_180004E96
0x180004e71  test    eax, 0FFFFFF7Fh
0x180004e76  jz      short loc_180004E91
0x180004e78  mov     rcx, [rbp+188h]; this
0x180004e7f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004e86  mov     edx, 0E01h; void *
0x180004e8b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004e91  mov     rsi, rbx
0x180004e94  jmp     short loc_180004E98
0x180004e96  xor     esi, esi
0x180004e98  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180004e9d  mov     [rsp+280h+var_240], rsi
0x180004ea2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004ea7  mov     [rsp+280h+var_248], 0
0x180004eb0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004eb5  mov     edi, eax
0x180004eb7  test    eax, eax
0x180004eb9  jns     short loc_180004EFB
0x180004ebb  mov     rcx, [rbp+188h]; this
0x180004ec2  lea     r8, aWil; "wil"
0x180004ec9  mov     r9d, eax; char *
0x180004ecc  mov     edx, 66h ; 'f'; void *
0x180004ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ed6  mov     rcx, [rbp+188h]; this
0x180004edd  lea     r8, aWil; "wil"
0x180004ee4  mov     r9d, edi; char *
0x180004ee7  mov     edx, 6Fh ; 'o'; void *
0x180004eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ef1  mov     r9d, edi
0x180004ef4  mov     edx, 12Eh
0x180004ef9  jmp     short loc_180004F38
0x180004efb  mov     rax, [rsp+280h+var_248]
0x180004f00  lea     rcx, ds:0[rax*4]
0x180004f08  test    rcx, rcx
0x180004f0b  jz      short loc_180004F18
0x180004f0d  mov     [r14], rcx
0x180004f10  mov     eax, [rcx]
0x180004f12  inc     eax
0x180004f14  mov     [rcx], eax
0x180004f16  jmp     short loc_180004F68
0x180004f18  mov     r8, r14
0x180004f1b  lea     rdx, [rsp+280h+hHandle]
0x180004f20  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004f25  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004f2a  mov     edi, eax
0x180004f2c  test    eax, eax
0x180004f2e  jns     short loc_180004F63
0x180004f30  mov     r9d, eax; char *
0x180004f33  mov     edx, 137h; void *
0x180004f38  mov     rcx, [rbp+188h]; this
0x180004f3f  lea     r8, aWil; "wil"
0x180004f46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f4b  lea     rcx, [rsp+280h+var_240]
0x180004f50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f55  lea     rcx, [rsp+280h+hHandle]
0x180004f5a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004f5f  mov     eax, edi
0x180004f61  jmp     short loc_180004F84
0x180004f63  mov     rbx, [rsp+280h+hHandle]
0x180004f68  test    rsi, rsi
0x180004f6b  jz      short loc_180004F75
0x180004f6d  mov     rcx, rsi; this
0x180004f70  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180004f75  test    rbx, rbx
0x180004f78  jz      short loc_180004F82
0x180004f7a  mov     rcx, rbx; this
0x180004f7d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f82  xor     eax, eax
0x180004f84  mov     rcx, [rbp+180h+var_20]
0x180004f8b  xor     rcx, rsp; StackCookie
0x180004f8e  call    __security_check_cookie
0x180004f93  lea     r11, [rsp+280h+var_10]
0x180004f9b  mov     rbx, [r11+30h]
0x180004f9f  mov     rsi, [r11+38h]
0x180004fa3  mov     rsp, r11
0x180004fa6  pop     r14
0x180004fa8  pop     rdi
0x180004fa9  pop     rbp
0x180004faa  retn
```
