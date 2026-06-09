# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007654`
- end: `0x18000784a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `502`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180006568`

## callees

- `0x180004558`
- `0x180004f80`
- `0x180005e80`
- `0x180005ec4`
- `0x180005ee0`
- `0x180006084`
- `0x180007654`
- `0x180007a74`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800076cb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800076cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000772d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000772d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000768f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000768f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ed`

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
0x180007654  mov     [rsp-8+arg_10], rbx
0x180007659  mov     [rsp-8+arg_18], rsi
0x18000765e  push    rbp
0x18000765f  push    rdi
0x180007660  push    r14
0x180007662  lea     rbp, [rsp-160h]
0x18000766a  sub     rsp, 260h
0x180007671  mov     rax, cs:__security_cookie
0x180007678  xor     rax, rsp
0x18000767b  mov     [rbp+170h+var_20], rax
0x180007682  mov     r14, rdx
0x180007685  mov     qword ptr [rdx], 0
0x18000768c  mov     rbx, rcx
0x18000768f  call    cs:__imp_GetCurrentProcessId
0x180007695  mov     [rsp+270h+var_248], rbx
0x18000769a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800076a1  mov     r9d, eax
0x1800076a4  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800076ac  mov     edx, 104h; unsigned __int64
0x1800076b1  lea     rcx, [rsp+270h+Name]; Buffer
0x1800076b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800076bb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800076c1  lea     rdx, [rsp+270h+Name]; lpName
0x1800076c6  xor     r8d, r8d; dwFlags
0x1800076c9  xor     ecx, ecx; lpMutexAttributes
0x1800076cb  call    cs:__imp_CreateMutexExW
0x1800076d1  mov     [rsp+270h+var_240], rax
0x1800076d6  mov     rbx, rax
0x1800076d9  test    rax, rax
0x1800076dc  jnz     short loc_180007724
0x1800076de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800076e3  mov     edi, eax
0x1800076e5  test    rbx, rbx
0x1800076e8  jz      short loc_1800076FB
0x1800076ea  mov     rcx, rbx; hObject
0x1800076ed  call    cs:__imp_CloseHandle
0x1800076f3  test    eax, eax
0x1800076f5  jz      loc_180007838
0x1800076fb  mov     eax, edi
0x1800076fd  mov     rcx, [rbp+170h+var_20]
0x180007704  xor     rcx, rsp; StackCookie
0x180007707  call    __security_check_cookie
0x18000770c  lea     r11, [rsp+270h+var_10]
0x180007714  mov     rbx, [r11+30h]
0x180007718  mov     rsi, [r11+38h]
0x18000771c  mov     rsp, r11
0x18000771f  pop     r14
0x180007721  pop     rdi
0x180007722  pop     rbp
0x180007723  retn
0x180007724  xor     r8d, r8d; bAlertable
0x180007727  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000772a  mov     rcx, rbx; hHandle
0x18000772d  call    cs:__imp_WaitForSingleObjectEx
0x180007733  cmp     eax, 102h
0x180007738  jz      short loc_18000774A
0x18000773a  test    eax, 0FFFFFF7Fh
0x18000773f  jnz     loc_180007819
0x180007745  mov     rsi, rbx
0x180007748  jmp     short loc_18000774C
0x18000774a  xor     esi, esi
0x18000774c  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x180007751  mov     [rsp+270h+var_238], 0
0x18000775a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000775f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180007764  mov     edi, eax
0x180007766  test    eax, eax
0x180007768  jns     short loc_1800077A7
0x18000776a  mov     rcx, [rbp+178h]; this
0x180007771  lea     r8, aWil; "wil"
0x180007778  mov     r9d, eax; char *
0x18000777b  mov     edx, 64h ; 'd'; void *
0x180007780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007785  mov     rcx, [rbp+178h]; this
0x18000778c  lea     r8, aWil; "wil"
0x180007793  mov     r9d, edi; char *
0x180007796  mov     edx, 6Dh ; 'm'; void *
0x18000779b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077a0  mov     edx, 12Bh
0x1800077a5  jmp     short loc_180007801
0x1800077a7  mov     rax, [rsp+270h+var_238]
0x1800077ac  lea     rcx, ds:0[rax*4]
0x1800077b4  test    rcx, rcx
0x1800077b7  jz      short loc_1800077DF
0x1800077b9  mov     [r14], rcx
0x1800077bc  mov     eax, [rcx]
0x1800077be  inc     eax
0x1800077c0  mov     [rcx], eax
0x1800077c2  xor     edi, edi
0x1800077c4  test    rsi, rsi
0x1800077c7  jz      loc_1800076E5
0x1800077cd  mov     rcx, rsi; hMutex
0x1800077d0  call    cs:__imp_ReleaseMutex
0x1800077d6  test    eax, eax
0x1800077d8  jz      short loc_180007826
0x1800077da  jmp     loc_1800076E5
0x1800077df  mov     r8, r14
0x1800077e2  lea     rdx, [rsp+270h+var_240]
0x1800077e7  lea     rcx, [rsp+270h+Name]
0x1800077ec  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800077f1  mov     rbx, [rsp+270h+var_240]
0x1800077f6  mov     edi, eax
0x1800077f8  test    eax, eax
0x1800077fa  jns     short loc_1800077C2
0x1800077fc  mov     edx, 134h; void *
0x180007801  mov     rcx, [rbp+178h]; this
0x180007808  lea     r8, aWil; "wil"
0x18000780f  mov     r9d, edi; char *
0x180007812  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007817  jmp     short loc_1800077C4
0x180007819  mov     rcx, [rbp+178h]; this
0x180007820  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007826  mov     rcx, [rbp+178h]; this
0x18000782d  mov     edx, 9DBh; void *
0x180007832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007838  mov     rcx, [rbp+178h]; this
0x18000783f  mov     edx, 9D1h; void *
0x180007844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
