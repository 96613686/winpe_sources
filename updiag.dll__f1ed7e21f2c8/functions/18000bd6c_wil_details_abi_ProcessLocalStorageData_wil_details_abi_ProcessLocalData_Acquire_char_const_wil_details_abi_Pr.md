# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000bd6c`
- end: `0x18000bf62`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000b444`

## callees

- `0x180008ad4`
- `0x18000a738`
- `0x18000ad5c`
- `0x18000ada0`
- `0x18000adbc`
- `0x18000af60`
- `0x18000bd6c`
- `0x18000c18c`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bee8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000be45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000be45`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bde3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000bde3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bda7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bda7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be05`

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
0x18000bd6c  mov     [rsp-8+arg_10], rbx
0x18000bd71  mov     [rsp-8+arg_18], rsi
0x18000bd76  push    rbp
0x18000bd77  push    rdi
0x18000bd78  push    r14
0x18000bd7a  lea     rbp, [rsp-160h]
0x18000bd82  sub     rsp, 260h
0x18000bd89  mov     rax, cs:__security_cookie
0x18000bd90  xor     rax, rsp
0x18000bd93  mov     [rbp+170h+var_20], rax
0x18000bd9a  mov     r14, rdx
0x18000bd9d  mov     qword ptr [rdx], 0
0x18000bda4  mov     rbx, rcx
0x18000bda7  call    cs:__imp_GetCurrentProcessId
0x18000bdad  mov     [rsp+270h+var_248], rbx
0x18000bdb2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000bdb9  mov     r9d, eax
0x18000bdbc  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000bdc4  mov     edx, 104h; unsigned __int64
0x18000bdc9  lea     rcx, [rsp+270h+Name]; Buffer
0x18000bdce  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000bdd3  mov     r9d, 1F0001h; dwDesiredAccess
0x18000bdd9  lea     rdx, [rsp+270h+Name]; lpName
0x18000bdde  xor     r8d, r8d; dwFlags
0x18000bde1  xor     ecx, ecx; lpMutexAttributes
0x18000bde3  call    cs:__imp_CreateMutexExW
0x18000bde9  mov     [rsp+270h+var_240], rax
0x18000bdee  mov     rbx, rax
0x18000bdf1  test    rax, rax
0x18000bdf4  jnz     short loc_18000BE3C
0x18000bdf6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bdfb  mov     edi, eax
0x18000bdfd  test    rbx, rbx
0x18000be00  jz      short loc_18000BE13
0x18000be02  mov     rcx, rbx; hObject
0x18000be05  call    cs:__imp_CloseHandle
0x18000be0b  test    eax, eax
0x18000be0d  jz      loc_18000BF50
0x18000be13  mov     eax, edi
0x18000be15  mov     rcx, [rbp+170h+var_20]
0x18000be1c  xor     rcx, rsp; StackCookie
0x18000be1f  call    __security_check_cookie
0x18000be24  lea     r11, [rsp+270h+var_10]
0x18000be2c  mov     rbx, [r11+30h]
0x18000be30  mov     rsi, [r11+38h]
0x18000be34  mov     rsp, r11
0x18000be37  pop     r14
0x18000be39  pop     rdi
0x18000be3a  pop     rbp
0x18000be3b  retn
0x18000be3c  xor     r8d, r8d; bAlertable
0x18000be3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000be42  mov     rcx, rbx; hHandle
0x18000be45  call    cs:__imp_WaitForSingleObjectEx
0x18000be4b  cmp     eax, 102h
0x18000be50  jz      short loc_18000BE62
0x18000be52  test    eax, 0FFFFFF7Fh
0x18000be57  jnz     loc_18000BF31
0x18000be5d  mov     rsi, rbx
0x18000be60  jmp     short loc_18000BE64
0x18000be62  xor     esi, esi
0x18000be64  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000be69  mov     [rsp+270h+var_238], 0
0x18000be72  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000be77  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000be7c  mov     edi, eax
0x18000be7e  test    eax, eax
0x18000be80  jns     short loc_18000BEBF
0x18000be82  mov     rcx, [rbp+178h]; this
0x18000be89  lea     r8, aWil; "wil"
0x18000be90  mov     r9d, eax; char *
0x18000be93  mov     edx, 64h ; 'd'; void *
0x18000be98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be9d  mov     rcx, [rbp+178h]; this
0x18000bea4  lea     r8, aWil; "wil"
0x18000beab  mov     r9d, edi; char *
0x18000beae  mov     edx, 6Dh ; 'm'; void *
0x18000beb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000beb8  mov     edx, 12Bh
0x18000bebd  jmp     short loc_18000BF19
0x18000bebf  mov     rax, [rsp+270h+var_238]
0x18000bec4  lea     rcx, ds:0[rax*4]
0x18000becc  test    rcx, rcx
0x18000becf  jz      short loc_18000BEF7
0x18000bed1  mov     [r14], rcx
0x18000bed4  mov     eax, [rcx]
0x18000bed6  inc     eax
0x18000bed8  mov     [rcx], eax
0x18000beda  xor     edi, edi
0x18000bedc  test    rsi, rsi
0x18000bedf  jz      loc_18000BDFD
0x18000bee5  mov     rcx, rsi; hMutex
0x18000bee8  call    cs:__imp_ReleaseMutex
0x18000beee  test    eax, eax
0x18000bef0  jz      short loc_18000BF3E
0x18000bef2  jmp     loc_18000BDFD
0x18000bef7  mov     r8, r14
0x18000befa  lea     rdx, [rsp+270h+var_240]
0x18000beff  lea     rcx, [rsp+270h+Name]
0x18000bf04  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000bf09  mov     rbx, [rsp+270h+var_240]
0x18000bf0e  mov     edi, eax
0x18000bf10  test    eax, eax
0x18000bf12  jns     short loc_18000BEDA
0x18000bf14  mov     edx, 134h; void *
0x18000bf19  mov     rcx, [rbp+178h]; this
0x18000bf20  lea     r8, aWil; "wil"
0x18000bf27  mov     r9d, edi; char *
0x18000bf2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf2f  jmp     short loc_18000BEDC
0x18000bf31  mov     rcx, [rbp+178h]; this
0x18000bf38  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bf3e  mov     rcx, [rbp+178h]; this
0x18000bf45  mov     edx, 9DBh; void *
0x18000bf4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bf50  mov     rcx, [rbp+178h]; this
0x18000bf57  mov     edx, 9D1h; void *
0x18000bf5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
