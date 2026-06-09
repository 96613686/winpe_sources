# WxProxyManager::CreateProxyOperation(IProxyOperation * *)

- ea: `0x180073640`
- end: `0x18007380f`
- name: `?CreateProxyOperation@WxProxyManager@@UEAAJPEAPEAUIProxyOperation@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(WxProxyManager *__hidden this, struct IProxyOperation **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180073640`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800736e5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800736e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800736a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800736a8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007368b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007368b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073779`

## pseudocode

```c
__int64 __fastcall WxProxyManager::CreateProxyOperation(WxProxyManager *this, struct IProxyOperation **a2)
{
  HANDLE CurrentThread; // rax
  char *v5; // rax
  char *v6; // rbx
  signed int v7; // edi
  char *v8; // rsi
  __int64 v9; // rcx
  struct IProxyOperation *v10; // rsi
  signed int LastError; // eax
  void *TokenHandle; // [rsp+28h] [rbp-30h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    v5 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
    v6 = v5;
    if ( v5 )
    {
      memset_0(v5 + 20, 0, 0x6Cu);
      *(_QWORD *)v6 = &WxGetProxyContext::`vftable'{for `RefCountContext'};
      *((_QWORD *)v6 + 1) = &WxGetProxyContext::`vftable'{for `IProxyOperation'};
      *((_DWORD *)v6 + 4) = 1;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 15) = 0;
      *((_QWORD *)v6 + 12) = 0;
      *((_DWORD *)v6 + 5) = 0;
      *((_DWORD *)v6 + 26) = 0;
      *((_QWORD *)v6 + 14) = 0;
      v7 = 0;
      *((_QWORD *)v6 + 14) = TokenHandle;
      TokenHandle = 0;
      v8 = (char *)this - 8;
      if ( v8 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = *((_QWORD *)v6 + 8);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)v6 + 8) = v8;
      v10 = (struct IProxyOperation *)((unsigned __int64)(v6 + 8) & -(__int64)(v6 != 0));
      if ( v10 )
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 8LL))((unsigned __int64)(v6 + 8) & -(__int64)(v6 != 0));
      *a2 = v10;
    }
    else
    {
      v6 = 0;
      v7 = -2147024882;
    }
  }
  else
  {
    v6 = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147418113;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180073640  mov     [rsp+arg_10], rbx
0x180073645  mov     [rsp+arg_18], rbp
0x18007364a  push    rsi
0x18007364b  push    rdi
0x18007364c  push    r14
0x18007364e  sub     rsp, 40h
0x180073652  mov     rax, cs:__security_cookie
0x180073659  xor     rax, rsp
0x18007365c  mov     [rsp+58h+var_28], rax
0x180073661  xor     ebp, ebp
0x180073663  mov     r14, rdx
0x180073666  mov     [rsp+58h+var_34], ebp
0x18007366a  mov     rsi, rcx
0x18007366d  mov     [rsp+58h+TokenHandle], rbp
0x180073672  call    cs:__imp_GetCurrentThread
0x180073678  lea     edi, [rbp+1]
0x18007367b  mov     edx, 2000Ch; DesiredAccess
0x180073680  mov     r8d, edi; OpenAsSelf
0x180073683  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180073688  mov     rcx, rax; ThreadHandle
0x18007368b  call    cs:__imp_OpenThreadToken
0x180073691  test    eax, eax
0x180073693  jz      loc_1800737BA
0x180073699  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800736a0  xor     edx, edx; dwFlags
0x1800736a2  mov     r8d, 80h; dwBytes
0x1800736a8  call    cs:__imp_HeapAlloc
0x1800736ae  mov     rbx, rax
0x1800736b1  test    rax, rax
0x1800736b4  jz      loc_1800737FA
0x1800736ba  xor     edx, edx; Val
0x1800736bc  lea     rcx, [rax+14h]; void *
0x1800736c0  lea     r8d, [rdx+6Ch]; Size
0x1800736c4  call    memset_0
0x1800736c9  lea     rax, ??_7WxGetProxyContext@@6BRefCountContext@@@; const WxGetProxyContext::`vftable'{for `RefCountContext'}
0x1800736d0  mov     [rbx], rax
0x1800736d3  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800736d7  lea     rax, ??_7WxGetProxyContext@@6BIProxyOperation@@@; const WxGetProxyContext::`vftable'{for `IProxyOperation'}
0x1800736de  mov     [rbx+8], rax
0x1800736e2  mov     [rbx+10h], edi
0x1800736e5  call    cs:__imp_InitializeCriticalSection
0x1800736eb  mov     [rbx+40h], rbp
0x1800736ef  mov     [rbx+48h], rbp
0x1800736f3  mov     [rbx+50h], rbp
0x1800736f7  mov     [rbx+58h], rbp
0x1800736fb  mov     [rbx+78h], rbp
0x1800736ff  mov     [rbx+60h], rbp
0x180073703  mov     [rbx+14h], ebp
0x180073706  mov     [rbx+68h], ebp
0x180073709  mov     [rbx+70h], rbp
0x18007370d  mov     rax, [rsp+58h+TokenHandle]
0x180073712  mov     edi, ebp
0x180073714  mov     [rbx+70h], rax
0x180073718  mov     [rsp+58h+TokenHandle], rbp
0x18007371d  add     rsi, 0FFFFFFFFFFFFFFF8h
0x180073721  jz      short loc_180073732
0x180073723  mov     rax, [rsi]
0x180073726  mov     rcx, rsi
0x180073729  mov     rax, [rax+8]
0x18007372d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073732  mov     rcx, [rbx+40h]
0x180073736  test    rcx, rcx
0x180073739  jz      short loc_180073747
0x18007373b  mov     rax, [rcx]
0x18007373e  mov     rax, [rax+10h]
0x180073742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073747  mov     [rbx+40h], rsi
0x18007374b  lea     rcx, [rbx+8]
0x18007374f  mov     rax, rbx
0x180073752  neg     rax
0x180073755  sbb     rsi, rsi
0x180073758  and     rsi, rcx
0x18007375b  jz      short loc_18007376C
0x18007375d  mov     rax, [rsi]
0x180073760  mov     rcx, rsi
0x180073763  mov     rax, [rax+8]
0x180073767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007376c  mov     [r14], rsi
0x18007376f  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180073774  test    rcx, rcx
0x180073777  jz      short loc_180073784
0x180073779  call    cs:__imp_CloseHandle
0x18007377f  mov     [rsp+58h+TokenHandle], rbp
0x180073784  test    rbx, rbx
0x180073787  jz      short loc_180073798
0x180073789  mov     rcx, [rbx]
0x18007378c  mov     rax, [rcx+8]
0x180073790  mov     rcx, rbx
0x180073793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073798  mov     eax, edi
0x18007379a  mov     rcx, [rsp+58h+var_28]
0x18007379f  xor     rcx, rsp; StackCookie
0x1800737a2  call    __security_check_cookie
0x1800737a7  mov     rbx, [rsp+58h+arg_10]
0x1800737ac  mov     rbp, [rsp+58h+arg_18]
0x1800737b1  add     rsp, 40h
0x1800737b5  pop     r14
0x1800737b7  pop     rdi
0x1800737b8  pop     rsi
0x1800737b9  retn
0x1800737ba  call    cs:__imp_GetLastError
0x1800737c0  cmp     eax, 3F0h
0x1800737c5  jz      loc_180073699
0x1800737cb  mov     rbx, rbp
0x1800737ce  call    cs:__imp_GetLastError
0x1800737d4  mov     edi, eax
0x1800737d6  test    eax, eax
0x1800737d8  jle     short loc_1800737E3
0x1800737da  movzx   edi, ax
0x1800737dd  or      edi, 80070000h
0x1800737e3  test    edi, edi
0x1800737e5  mov     [rsp+58h+var_34], 400h
0x1800737ed  mov     eax, 8000FFFFh
0x1800737f2  cmovns  edi, eax
0x1800737f5  jmp     loc_18007376F
0x1800737fa  mov     rbx, rbp
0x1800737fd  mov     [rsp+58h+var_34], 403h
0x180073805  mov     edi, 8007000Eh
0x18007380a  jmp     loc_18007376F
```
