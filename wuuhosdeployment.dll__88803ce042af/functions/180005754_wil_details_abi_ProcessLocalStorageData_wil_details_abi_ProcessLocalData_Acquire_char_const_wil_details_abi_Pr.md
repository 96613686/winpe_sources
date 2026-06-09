# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005754`
- end: `0x18000594a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180004060`

## callees

- `0x180001e8c`
- `0x1800029a0`
- `0x180003950`
- `0x180003994`
- `0x1800039b0`
- `0x180003b84`
- `0x180005754`
- `0x180005b74`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800058d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800058d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000582d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000582d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800057cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000578f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000578f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057ed`

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
0x180005754  mov     [rsp-8+arg_10], rbx
0x180005759  mov     [rsp-8+arg_18], rsi
0x18000575e  push    rbp
0x18000575f  push    rdi
0x180005760  push    r14
0x180005762  lea     rbp, [rsp-160h]
0x18000576a  sub     rsp, 260h
0x180005771  mov     rax, cs:__security_cookie
0x180005778  xor     rax, rsp
0x18000577b  mov     [rbp+170h+var_20], rax
0x180005782  mov     r14, rdx
0x180005785  mov     qword ptr [rdx], 0
0x18000578c  mov     rbx, rcx
0x18000578f  call    cs:__imp_GetCurrentProcessId
0x180005795  mov     [rsp+270h+var_248], rbx
0x18000579a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800057a1  mov     r9d, eax
0x1800057a4  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800057ac  mov     edx, 104h; unsigned __int64
0x1800057b1  lea     rcx, [rsp+270h+Name]; Buffer
0x1800057b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800057bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800057c1  lea     rdx, [rsp+270h+Name]; lpName
0x1800057c6  xor     r8d, r8d; dwFlags
0x1800057c9  xor     ecx, ecx; lpMutexAttributes
0x1800057cb  call    cs:__imp_CreateMutexExW
0x1800057d1  mov     [rsp+270h+var_240], rax
0x1800057d6  mov     rbx, rax
0x1800057d9  test    rax, rax
0x1800057dc  jnz     short loc_180005824
0x1800057de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800057e3  mov     edi, eax
0x1800057e5  test    rbx, rbx
0x1800057e8  jz      short loc_1800057FB
0x1800057ea  mov     rcx, rbx; hObject
0x1800057ed  call    cs:__imp_CloseHandle
0x1800057f3  test    eax, eax
0x1800057f5  jz      loc_180005938
0x1800057fb  mov     eax, edi
0x1800057fd  mov     rcx, [rbp+170h+var_20]
0x180005804  xor     rcx, rsp; StackCookie
0x180005807  call    __security_check_cookie
0x18000580c  lea     r11, [rsp+270h+var_10]
0x180005814  mov     rbx, [r11+30h]
0x180005818  mov     rsi, [r11+38h]
0x18000581c  mov     rsp, r11
0x18000581f  pop     r14
0x180005821  pop     rdi
0x180005822  pop     rbp
0x180005823  retn
0x180005824  xor     r8d, r8d; bAlertable
0x180005827  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000582a  mov     rcx, rbx; hHandle
0x18000582d  call    cs:__imp_WaitForSingleObjectEx
0x180005833  cmp     eax, 102h
0x180005838  jz      short loc_18000584A
0x18000583a  test    eax, 0FFFFFF7Fh
0x18000583f  jnz     loc_180005919
0x180005845  mov     rsi, rbx
0x180005848  jmp     short loc_18000584C
0x18000584a  xor     esi, esi
0x18000584c  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180005851  mov     [rsp+270h+var_238], 0
0x18000585a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000585f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005864  mov     edi, eax
0x180005866  test    eax, eax
0x180005868  jns     short loc_1800058A7
0x18000586a  mov     rcx, [rbp+178h]; this
0x180005871  lea     r8, aWil; "wil"
0x180005878  mov     r9d, eax; char *
0x18000587b  mov     edx, 64h ; 'd'; void *
0x180005880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005885  mov     rcx, [rbp+178h]; this
0x18000588c  lea     r8, aWil; "wil"
0x180005893  mov     r9d, edi; char *
0x180005896  mov     edx, 6Dh ; 'm'; void *
0x18000589b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800058a0  mov     edx, 12Bh
0x1800058a5  jmp     short loc_180005901
0x1800058a7  mov     rax, [rsp+270h+var_238]
0x1800058ac  lea     rcx, ds:0[rax*4]
0x1800058b4  test    rcx, rcx
0x1800058b7  jz      short loc_1800058DF
0x1800058b9  mov     [r14], rcx
0x1800058bc  mov     eax, [rcx]
0x1800058be  inc     eax
0x1800058c0  mov     [rcx], eax
0x1800058c2  xor     edi, edi
0x1800058c4  test    rsi, rsi
0x1800058c7  jz      loc_1800057E5
0x1800058cd  mov     rcx, rsi; hMutex
0x1800058d0  call    cs:__imp_ReleaseMutex
0x1800058d6  test    eax, eax
0x1800058d8  jz      short loc_180005926
0x1800058da  jmp     loc_1800057E5
0x1800058df  mov     r8, r14
0x1800058e2  lea     rdx, [rsp+270h+var_240]
0x1800058e7  lea     rcx, [rsp+270h+Name]
0x1800058ec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800058f1  mov     rbx, [rsp+270h+var_240]
0x1800058f6  mov     edi, eax
0x1800058f8  test    eax, eax
0x1800058fa  jns     short loc_1800058C2
0x1800058fc  mov     edx, 134h; void *
0x180005901  mov     rcx, [rbp+178h]; this
0x180005908  lea     r8, aWil; "wil"
0x18000590f  mov     r9d, edi; char *
0x180005912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005917  jmp     short loc_1800058C4
0x180005919  mov     rcx, [rbp+178h]; this
0x180005920  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005926  mov     rcx, [rbp+178h]; this
0x18000592d  mov     edx, 9DBh; void *
0x180005932  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005938  mov     rcx, [rbp+178h]; this
0x18000593f  mov     edx, 9D1h; void *
0x180005944  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
