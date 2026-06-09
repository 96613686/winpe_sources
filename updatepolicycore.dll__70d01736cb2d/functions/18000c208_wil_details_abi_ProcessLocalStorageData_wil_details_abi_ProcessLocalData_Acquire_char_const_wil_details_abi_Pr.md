# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000c208`
- end: `0x18000c3fe`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000b1a8`

## callees

- `0x1800090a8`
- `0x180009b10`
- `0x18000aac0`
- `0x18000ab04`
- `0x18000ab20`
- `0x18000acc4`
- `0x18000c208`
- `0x18000c628`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c384`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c384`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c2e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c2e1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c27f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c243`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2a1`

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
  __int64 v8; // r8
  const char *v9; // r9
  DWORD v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // r9
  void *v15; // rsi
  int ValueInternal; // eax
  __int64 v17; // rdx
  _DWORD *v18; // rcx
  __int64 v19; // r8
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
0x18000c208  mov     [rsp-8+arg_10], rbx
0x18000c20d  mov     [rsp-8+arg_18], rsi
0x18000c212  push    rbp
0x18000c213  push    rdi
0x18000c214  push    r14
0x18000c216  lea     rbp, [rsp-160h]
0x18000c21e  sub     rsp, 260h
0x18000c225  mov     rax, cs:__security_cookie
0x18000c22c  xor     rax, rsp
0x18000c22f  mov     [rbp+170h+var_20], rax
0x18000c236  mov     r14, rdx
0x18000c239  mov     qword ptr [rdx], 0
0x18000c240  mov     rbx, rcx
0x18000c243  call    cs:__imp_GetCurrentProcessId
0x18000c249  mov     [rsp+270h+var_248], rbx
0x18000c24e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c255  mov     r9d, eax
0x18000c258  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000c260  mov     edx, 104h; unsigned __int64
0x18000c265  lea     rcx, [rsp+270h+Name]; Buffer
0x18000c26a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c26f  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c275  lea     rdx, [rsp+270h+Name]; lpName
0x18000c27a  xor     r8d, r8d; dwFlags
0x18000c27d  xor     ecx, ecx; lpMutexAttributes
0x18000c27f  call    cs:__imp_CreateMutexExW
0x18000c285  mov     [rsp+270h+var_240], rax
0x18000c28a  mov     rbx, rax
0x18000c28d  test    rax, rax
0x18000c290  jnz     short loc_18000C2D8
0x18000c292  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c297  mov     edi, eax
0x18000c299  test    rbx, rbx
0x18000c29c  jz      short loc_18000C2AF
0x18000c29e  mov     rcx, rbx; hObject
0x18000c2a1  call    cs:__imp_CloseHandle
0x18000c2a7  test    eax, eax
0x18000c2a9  jz      loc_18000C3EC
0x18000c2af  mov     eax, edi
0x18000c2b1  mov     rcx, [rbp+170h+var_20]
0x18000c2b8  xor     rcx, rsp; StackCookie
0x18000c2bb  call    __security_check_cookie
0x18000c2c0  lea     r11, [rsp+270h+var_10]
0x18000c2c8  mov     rbx, [r11+30h]
0x18000c2cc  mov     rsi, [r11+38h]
0x18000c2d0  mov     rsp, r11
0x18000c2d3  pop     r14
0x18000c2d5  pop     rdi
0x18000c2d6  pop     rbp
0x18000c2d7  retn
0x18000c2d8  xor     r8d, r8d; bAlertable
0x18000c2db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c2de  mov     rcx, rbx; hHandle
0x18000c2e1  call    cs:__imp_WaitForSingleObjectEx
0x18000c2e7  cmp     eax, 102h
0x18000c2ec  jz      short loc_18000C2FE
0x18000c2ee  test    eax, 0FFFFFF7Fh
0x18000c2f3  jnz     loc_18000C3CD
0x18000c2f9  mov     rsi, rbx
0x18000c2fc  jmp     short loc_18000C300
0x18000c2fe  xor     esi, esi
0x18000c300  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000c305  mov     [rsp+270h+var_238], 0
0x18000c30e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000c313  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000c318  mov     edi, eax
0x18000c31a  test    eax, eax
0x18000c31c  jns     short loc_18000C35B
0x18000c31e  mov     rcx, [rbp+178h]; this
0x18000c325  lea     r8, aWil; "wil"
0x18000c32c  mov     r9d, eax; char *
0x18000c32f  mov     edx, 64h ; 'd'; void *
0x18000c334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c339  mov     rcx, [rbp+178h]; this
0x18000c340  lea     r8, aWil; "wil"
0x18000c347  mov     r9d, edi; char *
0x18000c34a  mov     edx, 6Dh ; 'm'; void *
0x18000c34f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c354  mov     edx, 12Bh
0x18000c359  jmp     short loc_18000C3B5
0x18000c35b  mov     rax, [rsp+270h+var_238]
0x18000c360  lea     rcx, ds:0[rax*4]
0x18000c368  test    rcx, rcx
0x18000c36b  jz      short loc_18000C393
0x18000c36d  mov     [r14], rcx
0x18000c370  mov     eax, [rcx]
0x18000c372  inc     eax
0x18000c374  mov     [rcx], eax
0x18000c376  xor     edi, edi
0x18000c378  test    rsi, rsi
0x18000c37b  jz      loc_18000C299
0x18000c381  mov     rcx, rsi; hMutex
0x18000c384  call    cs:__imp_ReleaseMutex
0x18000c38a  test    eax, eax
0x18000c38c  jz      short loc_18000C3DA
0x18000c38e  jmp     loc_18000C299
0x18000c393  mov     r8, r14
0x18000c396  lea     rdx, [rsp+270h+var_240]
0x18000c39b  lea     rcx, [rsp+270h+Name]
0x18000c3a0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000c3a5  mov     rbx, [rsp+270h+var_240]
0x18000c3aa  mov     edi, eax
0x18000c3ac  test    eax, eax
0x18000c3ae  jns     short loc_18000C376
0x18000c3b0  mov     edx, 134h; void *
0x18000c3b5  mov     rcx, [rbp+178h]; this
0x18000c3bc  lea     r8, aWil; "wil"
0x18000c3c3  mov     r9d, edi; char *
0x18000c3c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3cb  jmp     short loc_18000C378
0x18000c3cd  mov     rcx, [rbp+178h]; this
0x18000c3d4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000c3da  mov     rcx, [rbp+178h]; this
0x18000c3e1  mov     edx, 9DBh; void *
0x18000c3e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c3ec  mov     rcx, [rbp+178h]; this
0x18000c3f3  mov     edx, 9D1h; void *
0x18000c3f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
