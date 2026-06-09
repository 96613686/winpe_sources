# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000fec4`
- end: `0x1800100e0`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003048c`

## callees

- `0x18000fec4`
- `0x1800100f0`
- `0x1800105b8`
- `0x18001cc38`
- `0x18002283c`
- `0x1800228e8`
- `0x180023fe8`
- `0x180026b64`
- `0x18002b1b0`
- `0x18002f91c`
- `0x18003098c`
- `0x180032714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ff3b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ff3b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff63`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ff63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000feff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000feff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001009b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001009b`

## string_xrefs

- `0x18000ff7e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  wil::details *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
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
  v24[0] = v11;
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v23, (bool *)v10);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
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
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
      goto LABEL_14;
    }
    v6 = v22;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
  {
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18000fec4  mov     [rsp-8+arg_10], rbx
0x18000fec9  mov     [rsp-8+arg_18], rsi
0x18000fece  push    rbp
0x18000fecf  push    rdi
0x18000fed0  push    r14
0x18000fed2  lea     rbp, [rsp-170h]
0x18000feda  sub     rsp, 270h
0x18000fee1  mov     rax, cs:__security_cookie
0x18000fee8  xor     rax, rsp
0x18000feeb  mov     [rbp+180h+var_20], rax
0x18000fef2  mov     r14, rdx
0x18000fef5  mov     qword ptr [rdx], 0
0x18000fefc  mov     rbx, rcx
0x18000feff  call    cs:__imp_GetCurrentProcessId
0x18000ff05  mov     [rsp+280h+var_258], rbx
0x18000ff0a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ff11  mov     r9d, eax
0x18000ff14  mov     [rsp+280h+var_260], 130h; int
0x18000ff1c  mov     edx, 104h; unsigned __int64
0x18000ff21  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ff26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ff2b  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ff31  lea     rdx, [rsp+280h+Name]; lpName
0x18000ff36  xor     r8d, r8d; dwFlags
0x18000ff39  xor     ecx, ecx; lpMutexAttributes
0x18000ff3b  call    cs:__imp_CreateMutexExW
0x18000ff41  mov     [rsp+280h+var_250], rax
0x18000ff46  mov     rbx, rax
0x18000ff49  test    rax, rax
0x18000ff4c  jnz     short loc_18000FF5A
0x18000ff4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ff53  mov     ebx, eax
0x18000ff55  jmp     loc_180010073
0x18000ff5a  xor     r8d, r8d; bAlertable
0x18000ff5d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ff60  mov     rcx, rbx; hHandle
0x18000ff63  call    cs:__imp_WaitForSingleObjectEx
0x18000ff69  cmp     eax, 102h
0x18000ff6e  jz      short loc_18000FF95
0x18000ff70  test    eax, 0FFFFFF7Fh
0x18000ff75  jz      short loc_18000FF90
0x18000ff77  mov     rcx, [rbp+188h]; this
0x18000ff7e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ff85  mov     edx, 0E01h; void *
0x18000ff8a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ff90  mov     rdi, rbx
0x18000ff93  jmp     short loc_18000FF97
0x18000ff95  xor     edi, edi
0x18000ff97  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18000ff9c  mov     [rsp+280h+var_240], rdi
0x18000ffa1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000ffa6  mov     [rsp+280h+var_248], 0
0x18000ffaf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000ffb4  mov     esi, eax
0x18000ffb6  test    eax, eax
0x18000ffb8  jns     short loc_180010019
0x18000ffba  mov     rcx, [rbp+188h]; this
0x18000ffc1  lea     r8, aWil; "wil"
0x18000ffc8  mov     r9d, eax; char *
0x18000ffcb  mov     edx, 66h ; 'f'; void *
0x18000ffd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffd5  mov     rcx, [rbp+188h]; this
0x18000ffdc  lea     r8, aWil; "wil"
0x18000ffe3  mov     r9d, esi; char *
0x18000ffe6  mov     edx, 6Fh ; 'o'; void *
0x18000ffeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fff0  mov     rcx, [rbp+188h]; this
0x18000fff7  lea     r8, aWil; "wil"
0x18000fffe  mov     r9d, esi; char *
0x180010001  mov     edx, 12Eh; void *
0x180010006  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001000b  lea     rcx, [rsp+280h+var_240]
0x180010010  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010015  mov     ebx, esi
0x180010017  jmp     short loc_180010073
0x180010019  mov     rax, [rsp+280h+var_248]
0x18001001e  lea     rcx, ds:0[rax*4]
0x180010026  test    rcx, rcx
0x180010029  jz      short loc_180010036
0x18001002b  mov     [r14], rcx
0x18001002e  mov     eax, [rcx]
0x180010030  inc     eax
0x180010032  mov     [rcx], eax
0x180010034  jmp     short loc_180010086
0x180010036  mov     r8, r14
0x180010039  lea     rdx, [rsp+280h+var_250]
0x18001003e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010043  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180010048  mov     ebx, eax
0x18001004a  test    eax, eax
0x18001004c  jns     short loc_180010081
0x18001004e  mov     rcx, [rbp+188h]; this
0x180010055  lea     r8, aWil; "wil"
0x18001005c  mov     r9d, eax; char *
0x18001005f  mov     edx, 137h; void *
0x180010064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010069  lea     rcx, [rsp+280h+var_240]
0x18001006e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180010073  lea     rcx, [rsp+280h+var_250]
0x180010078  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001007d  mov     eax, ebx
0x18001007f  jmp     short loc_1800100B9
0x180010081  mov     rbx, [rsp+280h+var_250]
0x180010086  test    rdi, rdi
0x180010089  jz      short loc_180010093
0x18001008b  mov     rcx, rdi; this
0x18001008e  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180010093  test    rbx, rbx
0x180010096  jz      short loc_1800100B7
0x180010098  mov     rcx, rbx; hObject
0x18001009b  call    cs:__imp_CloseHandle
0x1800100a1  test    eax, eax
0x1800100a3  jnz     short loc_1800100B7
0x1800100a5  mov     rcx, [rbp+188h]; this
0x1800100ac  mov     edx, 0A0Bh; void *
0x1800100b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800100b7  xor     eax, eax
0x1800100b9  mov     rcx, [rbp+180h+var_20]
0x1800100c0  xor     rcx, rsp; StackCookie
0x1800100c3  call    __security_check_cookie
0x1800100c8  lea     r11, [rsp+280h+var_10]
0x1800100d0  mov     rbx, [r11+30h]
0x1800100d4  mov     rsi, [r11+38h]
0x1800100d8  mov     rsp, r11
0x1800100db  pop     r14
0x1800100dd  pop     rdi
0x1800100de  pop     rbp
0x1800100df  retn
```
