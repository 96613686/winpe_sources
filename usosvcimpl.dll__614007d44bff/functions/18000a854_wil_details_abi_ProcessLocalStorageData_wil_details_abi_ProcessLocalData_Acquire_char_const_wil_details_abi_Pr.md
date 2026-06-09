# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a854`
- end: `0x18000aa4f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000955c`

## callees

- `0x18000775c`
- `0x1800081c0`
- `0x180008e64`
- `0x180008ea8`
- `0x180008ec4`
- `0x180009080`
- `0x18000a854`
- `0x18000acb8`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a9d0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a92d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a92d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a88f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a88f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ed`

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
  bool v12; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xC2D, v13, v14);
    v15 = v6;
  }
  v25 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v12, &v25, (bool *)v14);
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
0x18000a854  mov     [rsp-8+arg_10], rbx
0x18000a859  mov     [rsp-8+arg_18], rsi
0x18000a85e  push    rbp
0x18000a85f  push    rdi
0x18000a860  push    r14
0x18000a862  lea     rbp, [rsp-160h]
0x18000a86a  sub     rsp, 260h
0x18000a871  mov     rax, cs:__security_cookie
0x18000a878  xor     rax, rsp
0x18000a87b  mov     [rbp+170h+var_20], rax
0x18000a882  mov     r14, rdx
0x18000a885  mov     qword ptr [rdx], 0
0x18000a88c  mov     rbx, rcx
0x18000a88f  call    cs:__imp_GetCurrentProcessId
0x18000a895  mov     [rsp+270h+var_248], rbx
0x18000a89a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a8a1  mov     r9d, eax
0x18000a8a4  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a8ac  mov     edx, 104h; unsigned __int64
0x18000a8b1  lea     rcx, [rsp+270h+Name]; Buffer
0x18000a8b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000a8bb  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a8c1  lea     rdx, [rsp+270h+Name]; lpName
0x18000a8c6  xor     r8d, r8d; dwFlags
0x18000a8c9  xor     ecx, ecx; lpMutexAttributes
0x18000a8cb  call    cs:__imp_CreateMutexExW
0x18000a8d1  mov     [rsp+270h+var_240], rax
0x18000a8d6  mov     rbx, rax
0x18000a8d9  test    rax, rax
0x18000a8dc  jnz     short loc_18000A924
0x18000a8de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a8e3  mov     edi, eax
0x18000a8e5  test    rbx, rbx
0x18000a8e8  jz      short loc_18000A8FB
0x18000a8ea  mov     rcx, rbx; hObject
0x18000a8ed  call    cs:__imp_CloseHandle
0x18000a8f3  test    eax, eax
0x18000a8f5  jz      loc_18000AA3D
0x18000a8fb  mov     eax, edi
0x18000a8fd  mov     rcx, [rbp+170h+var_20]
0x18000a904  xor     rcx, rsp; StackCookie
0x18000a907  call    __security_check_cookie
0x18000a90c  lea     r11, [rsp+270h+var_10]
0x18000a914  mov     rbx, [r11+30h]
0x18000a918  mov     rsi, [r11+38h]
0x18000a91c  mov     rsp, r11
0x18000a91f  pop     r14
0x18000a921  pop     rdi
0x18000a922  pop     rbp
0x18000a923  retn
0x18000a924  xor     r8d, r8d; bAlertable
0x18000a927  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a92a  mov     rcx, rbx; hHandle
0x18000a92d  call    cs:__imp_WaitForSingleObjectEx
0x18000a933  cmp     eax, 102h
0x18000a938  jz      short loc_18000A94A
0x18000a93a  test    eax, 0FFFFFF7Fh
0x18000a93f  jnz     loc_18000AA19
0x18000a945  mov     rsi, rbx
0x18000a948  jmp     short loc_18000A94C
0x18000a94a  xor     esi, esi
0x18000a94c  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000a951  mov     [rsp+270h+var_238], 0
0x18000a95a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a95f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000a964  mov     edi, eax
0x18000a966  test    eax, eax
0x18000a968  jns     short loc_18000A9A7
0x18000a96a  mov     rcx, [rbp+178h]; this
0x18000a971  lea     r8, aWil; "wil"
0x18000a978  mov     r9d, eax; char *
0x18000a97b  mov     edx, 64h ; 'd'; void *
0x18000a980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a985  mov     rcx, [rbp+178h]; this
0x18000a98c  lea     r8, aWil; "wil"
0x18000a993  mov     r9d, edi; char *
0x18000a996  mov     edx, 6Dh ; 'm'; void *
0x18000a99b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9a0  mov     edx, 12Bh
0x18000a9a5  jmp     short loc_18000AA01
0x18000a9a7  mov     rax, [rsp+270h+var_238]
0x18000a9ac  lea     rcx, ds:0[rax*4]
0x18000a9b4  test    rcx, rcx
0x18000a9b7  jz      short loc_18000A9DF
0x18000a9b9  mov     [r14], rcx
0x18000a9bc  mov     eax, [rcx]
0x18000a9be  inc     eax
0x18000a9c0  mov     [rcx], eax
0x18000a9c2  xor     edi, edi
0x18000a9c4  test    rsi, rsi
0x18000a9c7  jz      loc_18000A8E5
0x18000a9cd  mov     rcx, rsi; hMutex
0x18000a9d0  call    cs:__imp_ReleaseMutex
0x18000a9d6  test    eax, eax
0x18000a9d8  jz      short loc_18000AA2B
0x18000a9da  jmp     loc_18000A8E5
0x18000a9df  mov     r8, r14
0x18000a9e2  lea     rdx, [rsp+270h+var_240]
0x18000a9e7  lea     rcx, [rsp+270h+Name]
0x18000a9ec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a9f1  mov     rbx, [rsp+270h+var_240]
0x18000a9f6  mov     edi, eax
0x18000a9f8  test    eax, eax
0x18000a9fa  jns     short loc_18000A9C2
0x18000a9fc  mov     edx, 134h; void *
0x18000aa01  mov     rcx, [rbp+178h]; this
0x18000aa08  lea     r8, aWil; "wil"
0x18000aa0f  mov     r9d, edi; char *
0x18000aa12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa17  jmp     short loc_18000A9C4
0x18000aa19  mov     rcx, [rbp+178h]; this
0x18000aa20  mov     edx, 0C2Dh; void *
0x18000aa25  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000aa2b  mov     rcx, [rbp+178h]; this
0x18000aa32  mov     edx, 9DBh; void *
0x18000aa37  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aa3d  mov     rcx, [rbp+178h]; this
0x18000aa44  mov     edx, 9D1h; void *
0x18000aa49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
