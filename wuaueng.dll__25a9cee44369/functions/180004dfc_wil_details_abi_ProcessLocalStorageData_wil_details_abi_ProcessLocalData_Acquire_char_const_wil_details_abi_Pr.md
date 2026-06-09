# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004dfc`
- end: `0x180004ff2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180004070`

## callees

- `0x180001ca8`
- `0x1800027b0`
- `0x180003760`
- `0x1800037a4`
- `0x1800037c0`
- `0x180003b94`
- `0x180004dfc`
- `0x18000521c`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004ed5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004ed5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e73`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004e73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004e37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e95`

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
0x180004dfc  mov     [rsp-8+arg_10], rbx
0x180004e01  mov     [rsp-8+arg_18], rsi
0x180004e06  push    rbp
0x180004e07  push    rdi
0x180004e08  push    r14
0x180004e0a  lea     rbp, [rsp-160h]
0x180004e12  sub     rsp, 260h
0x180004e19  mov     rax, cs:__security_cookie
0x180004e20  xor     rax, rsp
0x180004e23  mov     [rbp+170h+var_20], rax
0x180004e2a  mov     r14, rdx
0x180004e2d  mov     qword ptr [rdx], 0
0x180004e34  mov     rbx, rcx
0x180004e37  call    cs:__imp_GetCurrentProcessId
0x180004e3d  mov     [rsp+270h+var_248], rbx
0x180004e42  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004e49  mov     r9d, eax
0x180004e4c  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004e54  mov     edx, 104h; unsigned __int64
0x180004e59  lea     rcx, [rsp+270h+Name]; Buffer
0x180004e5e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004e63  mov     r9d, 1F0001h; dwDesiredAccess
0x180004e69  lea     rdx, [rsp+270h+Name]; lpName
0x180004e6e  xor     r8d, r8d; dwFlags
0x180004e71  xor     ecx, ecx; lpMutexAttributes
0x180004e73  call    cs:__imp_CreateMutexExW
0x180004e79  mov     [rsp+270h+var_240], rax
0x180004e7e  mov     rbx, rax
0x180004e81  test    rax, rax
0x180004e84  jnz     short loc_180004ECC
0x180004e86  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004e8b  mov     edi, eax
0x180004e8d  test    rbx, rbx
0x180004e90  jz      short loc_180004EA3
0x180004e92  mov     rcx, rbx; hObject
0x180004e95  call    cs:__imp_CloseHandle
0x180004e9b  test    eax, eax
0x180004e9d  jz      loc_180004FE0
0x180004ea3  mov     eax, edi
0x180004ea5  mov     rcx, [rbp+170h+var_20]
0x180004eac  xor     rcx, rsp; StackCookie
0x180004eaf  call    __security_check_cookie
0x180004eb4  lea     r11, [rsp+270h+var_10]
0x180004ebc  mov     rbx, [r11+30h]
0x180004ec0  mov     rsi, [r11+38h]
0x180004ec4  mov     rsp, r11
0x180004ec7  pop     r14
0x180004ec9  pop     rdi
0x180004eca  pop     rbp
0x180004ecb  retn
0x180004ecc  xor     r8d, r8d; bAlertable
0x180004ecf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004ed2  mov     rcx, rbx; hHandle
0x180004ed5  call    cs:__imp_WaitForSingleObjectEx
0x180004edb  cmp     eax, 102h
0x180004ee0  jz      short loc_180004EF2
0x180004ee2  test    eax, 0FFFFFF7Fh
0x180004ee7  jnz     loc_180004FC1
0x180004eed  mov     rsi, rbx
0x180004ef0  jmp     short loc_180004EF4
0x180004ef2  xor     esi, esi
0x180004ef4  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180004ef9  mov     [rsp+270h+var_238], 0
0x180004f02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180004f07  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180004f0c  mov     edi, eax
0x180004f0e  test    eax, eax
0x180004f10  jns     short loc_180004F4F
0x180004f12  mov     rcx, [rbp+178h]; this
0x180004f19  lea     r8, aWil; "wil"
0x180004f20  mov     r9d, eax; char *
0x180004f23  mov     edx, 64h ; 'd'; void *
0x180004f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f2d  mov     rcx, [rbp+178h]; this
0x180004f34  lea     r8, aWil; "wil"
0x180004f3b  mov     r9d, edi; char *
0x180004f3e  mov     edx, 6Dh ; 'm'; void *
0x180004f43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f48  mov     edx, 12Bh
0x180004f4d  jmp     short loc_180004FA9
0x180004f4f  mov     rax, [rsp+270h+var_238]
0x180004f54  lea     rcx, ds:0[rax*4]
0x180004f5c  test    rcx, rcx
0x180004f5f  jz      short loc_180004F87
0x180004f61  mov     [r14], rcx
0x180004f64  mov     eax, [rcx]
0x180004f66  inc     eax
0x180004f68  mov     [rcx], eax
0x180004f6a  xor     edi, edi
0x180004f6c  test    rsi, rsi
0x180004f6f  jz      loc_180004E8D
0x180004f75  mov     rcx, rsi; hMutex
0x180004f78  call    cs:__imp_ReleaseMutex
0x180004f7e  test    eax, eax
0x180004f80  jz      short loc_180004FCE
0x180004f82  jmp     loc_180004E8D
0x180004f87  mov     r8, r14
0x180004f8a  lea     rdx, [rsp+270h+var_240]
0x180004f8f  lea     rcx, [rsp+270h+Name]
0x180004f94  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004f99  mov     rbx, [rsp+270h+var_240]
0x180004f9e  mov     edi, eax
0x180004fa0  test    eax, eax
0x180004fa2  jns     short loc_180004F6A
0x180004fa4  mov     edx, 134h; void *
0x180004fa9  mov     rcx, [rbp+178h]; this
0x180004fb0  lea     r8, aWil; "wil"
0x180004fb7  mov     r9d, edi; char *
0x180004fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fbf  jmp     short loc_180004F6C
0x180004fc1  mov     rcx, [rbp+178h]; this
0x180004fc8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004fce  mov     rcx, [rbp+178h]; this
0x180004fd5  mov     edx, 9DBh; void *
0x180004fda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004fe0  mov     rcx, [rbp+178h]; this
0x180004fe7  mov     edx, 9D1h; void *
0x180004fec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
