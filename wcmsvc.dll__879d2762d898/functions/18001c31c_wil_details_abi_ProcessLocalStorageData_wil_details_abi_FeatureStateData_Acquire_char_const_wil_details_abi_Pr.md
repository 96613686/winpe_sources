# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001c31c`
- end: `0x18001c521`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18009034c`

## callees

- `0x18001c254`
- `0x18001c31c`
- `0x18001d1f4`
- `0x18001d308`
- `0x18003a024`
- `0x180060e08`
- `0x1800622cc`
- `0x180073f00`
- `0x180084f50`
- `0x180087ab8`
- `0x180088110`
- `0x180090aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c393`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c393`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c3bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c3bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c357`

## string_xrefs

- `0x18001c3d6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v20 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
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
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v18);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_14;
    }
    v6 = v20;
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
0x18001c31c  mov     [rsp-8+arg_10], rbx
0x18001c321  mov     [rsp-8+arg_18], rsi
0x18001c326  push    rbp
0x18001c327  push    rdi
0x18001c328  push    r14
0x18001c32a  lea     rbp, [rsp-170h]
0x18001c332  sub     rsp, 270h
0x18001c339  mov     rax, cs:__security_cookie
0x18001c340  xor     rax, rsp
0x18001c343  mov     [rbp+180h+var_20], rax
0x18001c34a  mov     r14, rdx
0x18001c34d  mov     qword ptr [rdx], 0
0x18001c354  mov     rbx, rcx
0x18001c357  call    cs:__imp_GetCurrentProcessId
0x18001c35d  mov     [rsp+280h+var_258], rbx
0x18001c362  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001c369  mov     r9d, eax
0x18001c36c  mov     [rsp+280h+var_260], 130h; int
0x18001c374  mov     edx, 104h; unsigned __int64
0x18001c379  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c37e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c383  mov     r9d, 1F0001h; dwDesiredAccess
0x18001c389  lea     rdx, [rsp+280h+Name]; lpName
0x18001c38e  xor     r8d, r8d; dwFlags
0x18001c391  xor     ecx, ecx; lpMutexAttributes
0x18001c393  call    cs:__imp_CreateMutexExW
0x18001c399  mov     [rsp+280h+var_250], rax
0x18001c39e  mov     rbx, rax
0x18001c3a1  test    rax, rax
0x18001c3a4  jnz     short loc_18001C3B2
0x18001c3a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c3ab  mov     ebx, eax
0x18001c3ad  jmp     loc_18001C4CB
0x18001c3b2  xor     r8d, r8d; bAlertable
0x18001c3b5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c3b8  mov     rcx, rbx; hHandle
0x18001c3bb  call    cs:__imp_WaitForSingleObjectEx
0x18001c3c1  cmp     eax, 102h
0x18001c3c6  jz      short loc_18001C3ED
0x18001c3c8  test    eax, 0FFFFFF7Fh
0x18001c3cd  jz      short loc_18001C3E8
0x18001c3cf  mov     rcx, [rbp+188h]; this
0x18001c3d6  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c3dd  mov     edx, 0E01h; void *
0x18001c3e2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001c3e8  mov     rdi, rbx
0x18001c3eb  jmp     short loc_18001C3EF
0x18001c3ed  xor     edi, edi
0x18001c3ef  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18001c3f4  mov     [rsp+280h+var_240], rdi
0x18001c3f9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c3fe  mov     [rsp+280h+var_248], 0
0x18001c407  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001c40c  mov     esi, eax
0x18001c40e  test    eax, eax
0x18001c410  jns     short loc_18001C471
0x18001c412  mov     rcx, [rbp+188h]; this
0x18001c419  lea     r8, aWil; "wil"
0x18001c420  mov     r9d, eax; char *
0x18001c423  mov     edx, 66h ; 'f'; void *
0x18001c428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c42d  mov     rcx, [rbp+188h]; this
0x18001c434  lea     r8, aWil; "wil"
0x18001c43b  mov     r9d, esi; char *
0x18001c43e  mov     edx, 6Fh ; 'o'; void *
0x18001c443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c448  mov     rcx, [rbp+188h]; this
0x18001c44f  lea     r8, aWil; "wil"
0x18001c456  mov     r9d, esi; char *
0x18001c459  mov     edx, 12Eh; void *
0x18001c45e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c463  lea     rcx, [rsp+280h+var_240]
0x18001c468  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c46d  mov     ebx, esi
0x18001c46f  jmp     short loc_18001C4CB
0x18001c471  mov     rax, [rsp+280h+var_248]
0x18001c476  lea     rcx, ds:0[rax*4]
0x18001c47e  test    rcx, rcx
0x18001c481  jz      short loc_18001C48E
0x18001c483  mov     [r14], rcx
0x18001c486  mov     eax, [rcx]
0x18001c488  inc     eax
0x18001c48a  mov     [rcx], eax
0x18001c48c  jmp     short loc_18001C4DE
0x18001c48e  mov     r8, r14
0x18001c491  lea     rdx, [rsp+280h+var_250]
0x18001c496  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c49b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001c4a0  mov     ebx, eax
0x18001c4a2  test    eax, eax
0x18001c4a4  jns     short loc_18001C4D9
0x18001c4a6  mov     rcx, [rbp+188h]; this
0x18001c4ad  lea     r8, aWil; "wil"
0x18001c4b4  mov     r9d, eax; char *
0x18001c4b7  mov     edx, 137h; void *
0x18001c4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c4c1  lea     rcx, [rsp+280h+var_240]
0x18001c4c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c4cb  lea     rcx, [rsp+280h+var_250]
0x18001c4d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c4d5  mov     eax, ebx
0x18001c4d7  jmp     short loc_18001C4FA
0x18001c4d9  mov     rbx, [rsp+280h+var_250]
0x18001c4de  test    rdi, rdi
0x18001c4e1  jz      short loc_18001C4EB
0x18001c4e3  mov     rcx, rdi; this
0x18001c4e6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18001c4eb  test    rbx, rbx
0x18001c4ee  jz      short loc_18001C4F8
0x18001c4f0  mov     rcx, rbx; this
0x18001c4f3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001c4f8  xor     eax, eax
0x18001c4fa  mov     rcx, [rbp+180h+var_20]
0x18001c501  xor     rcx, rsp; StackCookie
0x18001c504  call    __security_check_cookie
0x18001c509  lea     r11, [rsp+280h+var_10]
0x18001c511  mov     rbx, [r11+30h]
0x18001c515  mov     rsi, [r11+38h]
0x18001c519  mov     rsp, r11
0x18001c51c  pop     r14
0x18001c51e  pop     rdi
0x18001c51f  pop     rbp
0x18001c520  retn
```
