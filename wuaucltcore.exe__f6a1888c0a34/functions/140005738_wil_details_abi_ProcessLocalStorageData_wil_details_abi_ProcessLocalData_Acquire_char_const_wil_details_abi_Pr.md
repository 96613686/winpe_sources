# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005738`
- end: `0x14000592e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140004550`

## callees

- `0x140002ac0`
- `0x140002d48`
- `0x140003288`
- `0x140003e94`
- `0x140003eb0`
- `0x140004074`
- `0x140005738`
- `0x140005b58`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005773`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400057af`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400057af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400058b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400058b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005811`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005811`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400057d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400057d1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  unsigned int LastErrorFailHr; // edi
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // r9
  void *v15; // rsi
  int ValueInternal; // eax
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  unsigned int v19; // r8d
  const char *v20; // r9
  int v21; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  HANDLE v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v22 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v24 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v11 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v11 == 258 )
  {
    v15 = 0;
  }
  else
  {
    if ( (v11 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v12, v13, v14);
    v15 = v6;
  }
  v25 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v12, &v25, (bool *)v14);
  LastErrorFailHr = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, (unsigned int)"wil", (const char *)LastErrorFailHr, v23);
    v17 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v17, (unsigned int)"wil", (const char *)LastErrorFailHr, v22);
    goto LABEL_15;
  }
  v18 = (_DWORD *)(4 * v25);
  if ( 4 * v25 )
  {
    *a2 = v18;
    ++*v18;
  }
  else
  {
    v21 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            Name,
            &v24,
            a2);
    v6 = v24;
    LastErrorFailHr = v21;
    if ( v21 < 0 )
    {
      v17 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v15 && !ReleaseMutex(v15) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DB, v19, v20);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v8, v9);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140005738  mov     [rsp-8+arg_10], rbx
0x14000573d  mov     [rsp-8+arg_18], rsi
0x140005742  push    rbp
0x140005743  push    rdi
0x140005744  push    r14
0x140005746  lea     rbp, [rsp-160h]
0x14000574e  sub     rsp, 260h
0x140005755  mov     rax, cs:__security_cookie
0x14000575c  xor     rax, rsp
0x14000575f  mov     [rbp+170h+var_20], rax
0x140005766  mov     r14, rdx
0x140005769  mov     qword ptr [rdx], 0
0x140005770  mov     rbx, rcx
0x140005773  call    cs:__imp_GetCurrentProcessId
0x140005779  mov     [rsp+270h+var_248], rbx
0x14000577e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005785  mov     r9d, eax
0x140005788  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140005790  mov     edx, 104h; unsigned __int64
0x140005795  lea     rcx, [rsp+270h+Name]; Buffer
0x14000579a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000579f  mov     r9d, 1F0001h; dwDesiredAccess
0x1400057a5  lea     rdx, [rsp+270h+Name]; lpName
0x1400057aa  xor     r8d, r8d; dwFlags
0x1400057ad  xor     ecx, ecx; lpMutexAttributes
0x1400057af  call    cs:__imp_CreateMutexExW
0x1400057b5  mov     [rsp+270h+var_240], rax
0x1400057ba  mov     rbx, rax
0x1400057bd  test    rax, rax
0x1400057c0  jnz     short loc_140005808
0x1400057c2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400057c7  mov     edi, eax
0x1400057c9  test    rbx, rbx
0x1400057cc  jz      short loc_1400057DF
0x1400057ce  mov     rcx, rbx; hObject
0x1400057d1  call    cs:__imp_CloseHandle
0x1400057d7  test    eax, eax
0x1400057d9  jz      loc_14000591C
0x1400057df  mov     eax, edi
0x1400057e1  mov     rcx, [rbp+170h+var_20]
0x1400057e8  xor     rcx, rsp; StackCookie
0x1400057eb  call    __security_check_cookie
0x1400057f0  lea     r11, [rsp+270h+var_10]
0x1400057f8  mov     rbx, [r11+30h]
0x1400057fc  mov     rsi, [r11+38h]
0x140005800  mov     rsp, r11
0x140005803  pop     r14
0x140005805  pop     rdi
0x140005806  pop     rbp
0x140005807  retn
0x140005808  xor     r8d, r8d; bAlertable
0x14000580b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000580e  mov     rcx, rbx; hHandle
0x140005811  call    cs:__imp_WaitForSingleObjectEx
0x140005817  cmp     eax, 102h
0x14000581c  jz      short loc_14000582E
0x14000581e  test    eax, 0FFFFFF7Fh
0x140005823  jnz     loc_1400058FD
0x140005829  mov     rsi, rbx
0x14000582c  jmp     short loc_140005830
0x14000582e  xor     esi, esi
0x140005830  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x140005835  mov     [rsp+270h+var_238], 0
0x14000583e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005843  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140005848  mov     edi, eax
0x14000584a  test    eax, eax
0x14000584c  jns     short loc_14000588B
0x14000584e  mov     rcx, [rbp+178h]; this
0x140005855  lea     r8, aWil; "wil"
0x14000585c  mov     r9d, eax; char *
0x14000585f  mov     edx, 64h ; 'd'; void *
0x140005864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005869  mov     rcx, [rbp+178h]; this
0x140005870  lea     r8, aWil; "wil"
0x140005877  mov     r9d, edi; char *
0x14000587a  mov     edx, 6Dh ; 'm'; void *
0x14000587f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005884  mov     edx, 12Bh
0x140005889  jmp     short loc_1400058E5
0x14000588b  mov     rax, [rsp+270h+var_238]
0x140005890  lea     rcx, ds:0[rax*4]
0x140005898  test    rcx, rcx
0x14000589b  jz      short loc_1400058C3
0x14000589d  mov     [r14], rcx
0x1400058a0  mov     eax, [rcx]
0x1400058a2  inc     eax
0x1400058a4  mov     [rcx], eax
0x1400058a6  xor     edi, edi
0x1400058a8  test    rsi, rsi
0x1400058ab  jz      loc_1400057C9
0x1400058b1  mov     rcx, rsi; hMutex
0x1400058b4  call    cs:__imp_ReleaseMutex
0x1400058ba  test    eax, eax
0x1400058bc  jz      short loc_14000590A
0x1400058be  jmp     loc_1400057C9
0x1400058c3  mov     r8, r14
0x1400058c6  lea     rdx, [rsp+270h+var_240]
0x1400058cb  lea     rcx, [rsp+270h+Name]
0x1400058d0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400058d5  mov     rbx, [rsp+270h+var_240]
0x1400058da  mov     edi, eax
0x1400058dc  test    eax, eax
0x1400058de  jns     short loc_1400058A6
0x1400058e0  mov     edx, 134h; void *
0x1400058e5  mov     rcx, [rbp+178h]; this
0x1400058ec  lea     r8, aWil; "wil"
0x1400058f3  mov     r9d, edi; char *
0x1400058f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058fb  jmp     short loc_1400058A8
0x1400058fd  mov     rcx, [rbp+178h]; this
0x140005904  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000590a  mov     rcx, [rbp+178h]; this
0x140005911  mov     edx, 9DBh; void *
0x140005916  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000591c  mov     rcx, [rbp+178h]; this
0x140005923  mov     edx, 9D1h; void *
0x140005928  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
