# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009a28`
- end: `0x180009c1e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800094c0`

## callees

- `0x180005d80`
- `0x180006858`
- `0x1800080c0`
- `0x180008bf8`
- `0x180008c14`
- `0x180008fe4`
- `0x180009a28`
- `0x180009e48`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a63`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a9f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009a9f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009b01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009b01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009ba4`

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
0x180009a28  mov     [rsp-8+arg_10], rbx
0x180009a2d  mov     [rsp-8+arg_18], rsi
0x180009a32  push    rbp
0x180009a33  push    rdi
0x180009a34  push    r14
0x180009a36  lea     rbp, [rsp-160h]
0x180009a3e  sub     rsp, 260h
0x180009a45  mov     rax, cs:__security_cookie
0x180009a4c  xor     rax, rsp
0x180009a4f  mov     [rbp+170h+var_20], rax
0x180009a56  mov     r14, rdx
0x180009a59  mov     qword ptr [rdx], 0
0x180009a60  mov     rbx, rcx
0x180009a63  call    cs:__imp_GetCurrentProcessId
0x180009a69  mov     [rsp+270h+var_248], rbx
0x180009a6e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009a75  mov     r9d, eax
0x180009a78  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180009a80  mov     edx, 104h; unsigned __int64
0x180009a85  lea     rcx, [rsp+270h+Name]; Buffer
0x180009a8a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009a8f  mov     r9d, 1F0001h; dwDesiredAccess
0x180009a95  lea     rdx, [rsp+270h+Name]; lpName
0x180009a9a  xor     r8d, r8d; dwFlags
0x180009a9d  xor     ecx, ecx; lpMutexAttributes
0x180009a9f  call    cs:__imp_CreateMutexExW
0x180009aa5  mov     [rsp+270h+var_240], rax
0x180009aaa  mov     rbx, rax
0x180009aad  test    rax, rax
0x180009ab0  jnz     short loc_180009AF8
0x180009ab2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009ab7  mov     edi, eax
0x180009ab9  test    rbx, rbx
0x180009abc  jz      short loc_180009ACF
0x180009abe  mov     rcx, rbx; hObject
0x180009ac1  call    cs:__imp_CloseHandle
0x180009ac7  test    eax, eax
0x180009ac9  jz      loc_180009C0C
0x180009acf  mov     eax, edi
0x180009ad1  mov     rcx, [rbp+170h+var_20]
0x180009ad8  xor     rcx, rsp; StackCookie
0x180009adb  call    __security_check_cookie
0x180009ae0  lea     r11, [rsp+270h+var_10]
0x180009ae8  mov     rbx, [r11+30h]
0x180009aec  mov     rsi, [r11+38h]
0x180009af0  mov     rsp, r11
0x180009af3  pop     r14
0x180009af5  pop     rdi
0x180009af6  pop     rbp
0x180009af7  retn
0x180009af8  xor     r8d, r8d; bAlertable
0x180009afb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009afe  mov     rcx, rbx; hHandle
0x180009b01  call    cs:__imp_WaitForSingleObjectEx
0x180009b07  cmp     eax, 102h
0x180009b0c  jz      short loc_180009B1E
0x180009b0e  test    eax, 0FFFFFF7Fh
0x180009b13  jnz     loc_180009BED
0x180009b19  mov     rsi, rbx
0x180009b1c  jmp     short loc_180009B20
0x180009b1e  xor     esi, esi
0x180009b20  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180009b25  mov     [rsp+270h+var_238], 0
0x180009b2e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180009b33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180009b38  mov     edi, eax
0x180009b3a  test    eax, eax
0x180009b3c  jns     short loc_180009B7B
0x180009b3e  mov     rcx, [rbp+178h]; this
0x180009b45  lea     r8, aWil; "wil"
0x180009b4c  mov     r9d, eax; char *
0x180009b4f  mov     edx, 64h ; 'd'; void *
0x180009b54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b59  mov     rcx, [rbp+178h]; this
0x180009b60  lea     r8, aWil; "wil"
0x180009b67  mov     r9d, edi; char *
0x180009b6a  mov     edx, 6Dh ; 'm'; void *
0x180009b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b74  mov     edx, 12Bh
0x180009b79  jmp     short loc_180009BD5
0x180009b7b  mov     rax, [rsp+270h+var_238]
0x180009b80  lea     rcx, ds:0[rax*4]
0x180009b88  test    rcx, rcx
0x180009b8b  jz      short loc_180009BB3
0x180009b8d  mov     [r14], rcx
0x180009b90  mov     eax, [rcx]
0x180009b92  inc     eax
0x180009b94  mov     [rcx], eax
0x180009b96  xor     edi, edi
0x180009b98  test    rsi, rsi
0x180009b9b  jz      loc_180009AB9
0x180009ba1  mov     rcx, rsi; hMutex
0x180009ba4  call    cs:__imp_ReleaseMutex
0x180009baa  test    eax, eax
0x180009bac  jz      short loc_180009BFA
0x180009bae  jmp     loc_180009AB9
0x180009bb3  mov     r8, r14
0x180009bb6  lea     rdx, [rsp+270h+var_240]
0x180009bbb  lea     rcx, [rsp+270h+Name]
0x180009bc0  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180009bc5  mov     rbx, [rsp+270h+var_240]
0x180009bca  mov     edi, eax
0x180009bcc  test    eax, eax
0x180009bce  jns     short loc_180009B96
0x180009bd0  mov     edx, 134h; void *
0x180009bd5  mov     rcx, [rbp+178h]; this
0x180009bdc  lea     r8, aWil; "wil"
0x180009be3  mov     r9d, edi; char *
0x180009be6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009beb  jmp     short loc_180009B98
0x180009bed  mov     rcx, [rbp+178h]; this
0x180009bf4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009bfa  mov     rcx, [rbp+178h]; this
0x180009c01  mov     edx, 9DBh; void *
0x180009c06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c0c  mov     rcx, [rbp+178h]; this
0x180009c13  mov     edx, 9D1h; void *
0x180009c18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
