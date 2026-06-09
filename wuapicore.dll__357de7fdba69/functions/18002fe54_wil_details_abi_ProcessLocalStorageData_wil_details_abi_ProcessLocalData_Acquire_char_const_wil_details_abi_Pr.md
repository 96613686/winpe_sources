# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002fe54`
- end: `0x18003004a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18002f37c`

## callees

- `0x180006ac4`
- `0x180006d4c`
- `0x18002e270`
- `0x18002ece8`
- `0x18002ed04`
- `0x18002ee98`
- `0x18002fe54`
- `0x180030274`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002fecb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002fecb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ff2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002ff2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ffd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002ffd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002fe8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002fe8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002feed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002feed`

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
0x18002fe54  mov     [rsp-8+arg_10], rbx
0x18002fe59  mov     [rsp-8+arg_18], rsi
0x18002fe5e  push    rbp
0x18002fe5f  push    rdi
0x18002fe60  push    r14
0x18002fe62  lea     rbp, [rsp-160h]
0x18002fe6a  sub     rsp, 260h
0x18002fe71  mov     rax, cs:__security_cookie
0x18002fe78  xor     rax, rsp
0x18002fe7b  mov     [rbp+170h+var_20], rax
0x18002fe82  mov     r14, rdx
0x18002fe85  mov     qword ptr [rdx], 0
0x18002fe8c  mov     rbx, rcx
0x18002fe8f  call    cs:__imp_GetCurrentProcessId
0x18002fe95  mov     [rsp+270h+var_248], rbx
0x18002fe9a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002fea1  mov     r9d, eax
0x18002fea4  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18002feac  mov     edx, 104h; unsigned __int64
0x18002feb1  lea     rcx, [rsp+270h+Name]; Buffer
0x18002feb6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002febb  mov     r9d, 1F0001h; dwDesiredAccess
0x18002fec1  lea     rdx, [rsp+270h+Name]; lpName
0x18002fec6  xor     r8d, r8d; dwFlags
0x18002fec9  xor     ecx, ecx; lpMutexAttributes
0x18002fecb  call    cs:__imp_CreateMutexExW
0x18002fed1  mov     [rsp+270h+var_240], rax
0x18002fed6  mov     rbx, rax
0x18002fed9  test    rax, rax
0x18002fedc  jnz     short loc_18002FF24
0x18002fede  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002fee3  mov     edi, eax
0x18002fee5  test    rbx, rbx
0x18002fee8  jz      short loc_18002FEFB
0x18002feea  mov     rcx, rbx; hObject
0x18002feed  call    cs:__imp_CloseHandle
0x18002fef3  test    eax, eax
0x18002fef5  jz      loc_180030038
0x18002fefb  mov     eax, edi
0x18002fefd  mov     rcx, [rbp+170h+var_20]
0x18002ff04  xor     rcx, rsp; StackCookie
0x18002ff07  call    __security_check_cookie
0x18002ff0c  lea     r11, [rsp+270h+var_10]
0x18002ff14  mov     rbx, [r11+30h]
0x18002ff18  mov     rsi, [r11+38h]
0x18002ff1c  mov     rsp, r11
0x18002ff1f  pop     r14
0x18002ff21  pop     rdi
0x18002ff22  pop     rbp
0x18002ff23  retn
0x18002ff24  xor     r8d, r8d; bAlertable
0x18002ff27  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ff2a  mov     rcx, rbx; hHandle
0x18002ff2d  call    cs:__imp_WaitForSingleObjectEx
0x18002ff33  cmp     eax, 102h
0x18002ff38  jz      short loc_18002FF4A
0x18002ff3a  test    eax, 0FFFFFF7Fh
0x18002ff3f  jnz     loc_180030019
0x18002ff45  mov     rsi, rbx
0x18002ff48  jmp     short loc_18002FF4C
0x18002ff4a  xor     esi, esi
0x18002ff4c  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18002ff51  mov     [rsp+270h+var_238], 0
0x18002ff5a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18002ff5f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18002ff64  mov     edi, eax
0x18002ff66  test    eax, eax
0x18002ff68  jns     short loc_18002FFA7
0x18002ff6a  mov     rcx, [rbp+178h]; this
0x18002ff71  lea     r8, aWil; "wil"
0x18002ff78  mov     r9d, eax; char *
0x18002ff7b  mov     edx, 64h ; 'd'; void *
0x18002ff80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff85  mov     rcx, [rbp+178h]; this
0x18002ff8c  lea     r8, aWil; "wil"
0x18002ff93  mov     r9d, edi; char *
0x18002ff96  mov     edx, 6Dh ; 'm'; void *
0x18002ff9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ffa0  mov     edx, 12Bh
0x18002ffa5  jmp     short loc_180030001
0x18002ffa7  mov     rax, [rsp+270h+var_238]
0x18002ffac  lea     rcx, ds:0[rax*4]
0x18002ffb4  test    rcx, rcx
0x18002ffb7  jz      short loc_18002FFDF
0x18002ffb9  mov     [r14], rcx
0x18002ffbc  mov     eax, [rcx]
0x18002ffbe  inc     eax
0x18002ffc0  mov     [rcx], eax
0x18002ffc2  xor     edi, edi
0x18002ffc4  test    rsi, rsi
0x18002ffc7  jz      loc_18002FEE5
0x18002ffcd  mov     rcx, rsi; hMutex
0x18002ffd0  call    cs:__imp_ReleaseMutex
0x18002ffd6  test    eax, eax
0x18002ffd8  jz      short loc_180030026
0x18002ffda  jmp     loc_18002FEE5
0x18002ffdf  mov     r8, r14
0x18002ffe2  lea     rdx, [rsp+270h+var_240]
0x18002ffe7  lea     rcx, [rsp+270h+Name]
0x18002ffec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002fff1  mov     rbx, [rsp+270h+var_240]
0x18002fff6  mov     edi, eax
0x18002fff8  test    eax, eax
0x18002fffa  jns     short loc_18002FFC2
0x18002fffc  mov     edx, 134h; void *
0x180030001  mov     rcx, [rbp+178h]; this
0x180030008  lea     r8, aWil; "wil"
0x18003000f  mov     r9d, edi; char *
0x180030012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030017  jmp     short loc_18002FFC4
0x180030019  mov     rcx, [rbp+178h]; this
0x180030020  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180030026  mov     rcx, [rbp+178h]; this
0x18003002d  mov     edx, 9DBh; void *
0x180030032  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030038  mov     rcx, [rbp+178h]; this
0x18003003f  mov     edx, 9D1h; void *
0x180030044  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
