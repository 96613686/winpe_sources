# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007ad8`
- end: `0x180007cce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180006b04`

## callees

- `0x180004924`
- `0x180005450`
- `0x180006400`
- `0x180006444`
- `0x180006460`
- `0x180006620`
- `0x180007ad8`
- `0x180007ef8`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007bb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007c54`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007c54`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007b4f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007b4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b71`

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
0x180007ad8  mov     [rsp-8+arg_10], rbx
0x180007add  mov     [rsp-8+arg_18], rsi
0x180007ae2  push    rbp
0x180007ae3  push    rdi
0x180007ae4  push    r14
0x180007ae6  lea     rbp, [rsp-160h]
0x180007aee  sub     rsp, 260h
0x180007af5  mov     rax, cs:__security_cookie
0x180007afc  xor     rax, rsp
0x180007aff  mov     [rbp+170h+var_20], rax
0x180007b06  mov     r14, rdx
0x180007b09  mov     qword ptr [rdx], 0
0x180007b10  mov     rbx, rcx
0x180007b13  call    cs:__imp_GetCurrentProcessId
0x180007b19  mov     [rsp+270h+var_248], rbx
0x180007b1e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007b25  mov     r9d, eax
0x180007b28  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180007b30  mov     edx, 104h; unsigned __int64
0x180007b35  lea     rcx, [rsp+270h+Name]; Buffer
0x180007b3a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180007b3f  mov     r9d, 1F0001h; dwDesiredAccess
0x180007b45  lea     rdx, [rsp+270h+Name]; lpName
0x180007b4a  xor     r8d, r8d; dwFlags
0x180007b4d  xor     ecx, ecx; lpMutexAttributes
0x180007b4f  call    cs:__imp_CreateMutexExW
0x180007b55  mov     [rsp+270h+var_240], rax
0x180007b5a  mov     rbx, rax
0x180007b5d  test    rax, rax
0x180007b60  jnz     short loc_180007BA8
0x180007b62  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007b67  mov     edi, eax
0x180007b69  test    rbx, rbx
0x180007b6c  jz      short loc_180007B7F
0x180007b6e  mov     rcx, rbx; hObject
0x180007b71  call    cs:__imp_CloseHandle
0x180007b77  test    eax, eax
0x180007b79  jz      loc_180007CBC
0x180007b7f  mov     eax, edi
0x180007b81  mov     rcx, [rbp+170h+var_20]
0x180007b88  xor     rcx, rsp; StackCookie
0x180007b8b  call    __security_check_cookie
0x180007b90  lea     r11, [rsp+270h+var_10]
0x180007b98  mov     rbx, [r11+30h]
0x180007b9c  mov     rsi, [r11+38h]
0x180007ba0  mov     rsp, r11
0x180007ba3  pop     r14
0x180007ba5  pop     rdi
0x180007ba6  pop     rbp
0x180007ba7  retn
0x180007ba8  xor     r8d, r8d; bAlertable
0x180007bab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007bae  mov     rcx, rbx; hHandle
0x180007bb1  call    cs:__imp_WaitForSingleObjectEx
0x180007bb7  cmp     eax, 102h
0x180007bbc  jz      short loc_180007BCE
0x180007bbe  test    eax, 0FFFFFF7Fh
0x180007bc3  jnz     loc_180007C9D
0x180007bc9  mov     rsi, rbx
0x180007bcc  jmp     short loc_180007BD0
0x180007bce  xor     esi, esi
0x180007bd0  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180007bd5  mov     [rsp+270h+var_238], 0
0x180007bde  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180007be3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180007be8  mov     edi, eax
0x180007bea  test    eax, eax
0x180007bec  jns     short loc_180007C2B
0x180007bee  mov     rcx, [rbp+178h]; this
0x180007bf5  lea     r8, aWil; "wil"
0x180007bfc  mov     r9d, eax; char *
0x180007bff  mov     edx, 64h ; 'd'; void *
0x180007c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c09  mov     rcx, [rbp+178h]; this
0x180007c10  lea     r8, aWil; "wil"
0x180007c17  mov     r9d, edi; char *
0x180007c1a  mov     edx, 6Dh ; 'm'; void *
0x180007c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c24  mov     edx, 12Bh
0x180007c29  jmp     short loc_180007C85
0x180007c2b  mov     rax, [rsp+270h+var_238]
0x180007c30  lea     rcx, ds:0[rax*4]
0x180007c38  test    rcx, rcx
0x180007c3b  jz      short loc_180007C63
0x180007c3d  mov     [r14], rcx
0x180007c40  mov     eax, [rcx]
0x180007c42  inc     eax
0x180007c44  mov     [rcx], eax
0x180007c46  xor     edi, edi
0x180007c48  test    rsi, rsi
0x180007c4b  jz      loc_180007B69
0x180007c51  mov     rcx, rsi; hMutex
0x180007c54  call    cs:__imp_ReleaseMutex
0x180007c5a  test    eax, eax
0x180007c5c  jz      short loc_180007CAA
0x180007c5e  jmp     loc_180007B69
0x180007c63  mov     r8, r14
0x180007c66  lea     rdx, [rsp+270h+var_240]
0x180007c6b  lea     rcx, [rsp+270h+Name]
0x180007c70  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180007c75  mov     rbx, [rsp+270h+var_240]
0x180007c7a  mov     edi, eax
0x180007c7c  test    eax, eax
0x180007c7e  jns     short loc_180007C46
0x180007c80  mov     edx, 134h; void *
0x180007c85  mov     rcx, [rbp+178h]; this
0x180007c8c  lea     r8, aWil; "wil"
0x180007c93  mov     r9d, edi; char *
0x180007c96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c9b  jmp     short loc_180007C48
0x180007c9d  mov     rcx, [rbp+178h]; this
0x180007ca4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007caa  mov     rcx, [rbp+178h]; this
0x180007cb1  mov     edx, 9DBh; void *
0x180007cb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007cbc  mov     rcx, [rbp+178h]; this
0x180007cc3  mov     edx, 9D1h; void *
0x180007cc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
