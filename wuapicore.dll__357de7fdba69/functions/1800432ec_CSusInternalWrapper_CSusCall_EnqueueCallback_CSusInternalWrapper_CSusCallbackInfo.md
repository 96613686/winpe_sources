# CSusInternalWrapper::CSusCall::EnqueueCallback(CSusInternalWrapper::CSusCallbackInfo *)

- ea: `0x1800432ec`
- end: `0x18004348b`
- name: `?EnqueueCallback@CSusCall@CSusInternalWrapper@@IEAAJPEAVCSusCallbackInfo@2@@Z`
- size: `415`
- prototype: `__int64 __fastcall(PVOID Parameter, struct CSusInternalWrapper::CSusCallbackInfo *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180043c00`
- `0x180043f60`
- `0x1800440b0`
- `0x1800443e0`
- `0x180048a10`
- `0x180049190`

## callees

- `0x1800432ec`
- `0x18008dff0`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004343d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004343d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004330f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004330f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043388`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800433e3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800433e3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004336d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004336d`

## string_xrefs

- `0x180043391`: `create callback timer`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::CSusCall::EnqueueCallback(
        char *Parameter,
        struct CSusInternalWrapper::CSusCallbackInfo *a2)
{
  void *v4; // rdx
  signed int LastError; // eax
  signed int v6; // edi
  signed int v7; // eax
  __int64 v8; // rdx
  char *v9; // rcx
  _QWORD *v10; // rax
  bool v11; // zf
  _QWORD *v13; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 96));
  if ( *((_DWORD *)Parameter + 20) )
  {
LABEL_19:
    if ( !a2 )
    {
LABEL_26:
      v6 = 0;
      goto LABEL_27;
    }
    v8 = *((_QWORD *)Parameter + 7);
    v9 = (char *)a2 + 8;
    *((_QWORD *)Parameter + 9) = v8;
    ++*((_DWORD *)Parameter + 16);
    *((_QWORD *)a2 + 1) = v8;
    if ( v8 )
    {
      *((_QWORD *)a2 + 2) = *(_QWORD *)(v8 + 8);
      *(_QWORD *)(v8 + 8) = v9;
      v13 = (_QWORD *)*((_QWORD *)a2 + 2);
      if ( v13 )
      {
        *v13 = v9;
        goto LABEL_25;
      }
    }
    else
    {
      v10 = (_QWORD *)*((_QWORD *)Parameter + 6);
      if ( v10 )
        *v10 = v9;
      *((_QWORD *)a2 + 2) = *((_QWORD *)Parameter + 6);
      v11 = *((_QWORD *)Parameter + 7) == 0;
      *((_QWORD *)Parameter + 6) = v9;
      if ( !v11 )
        goto LABEL_25;
    }
    *((_QWORD *)Parameter + 7) = v9;
LABEL_25:
    *((_QWORD *)Parameter + 9) = v9;
    goto LABEL_26;
  }
  v4 = (void *)*((_QWORD *)Parameter + 17);
  if ( v4 )
  {
    while ( !DeleteTimerQueueTimer(0, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      if ( v6 >= 0 )
        v6 = -2147418113;
      if ( !(unsigned int)NeedToRetryAfterWait(v6, L"wait for callback timer to exit") )
        goto LABEL_27;
      v4 = (void *)*((_QWORD *)Parameter + 17);
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 8LL))(Parameter);
  do
  {
    if ( CreateTimerQueueTimer(
           (PHANDLE)Parameter + 17,
           0,
           CSusInternalWrapper::CSusCall::CallbackWorker,
           Parameter,
           0,
           0,
           0x108u) )
    {
      *((_DWORD *)Parameter + 20) = 1;
      goto LABEL_19;
    }
    v7 = GetLastError();
    v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 <= 0 )
      v6 = v7;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
  while ( (unsigned int)NeedToRetryAfterWait(v6, L"create callback timer") );
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
LABEL_27:
  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 96));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800432ec  mov     rax, rsp
0x1800432ef  mov     [rax+8], rbx
0x1800432f3  mov     [rax+10h], rbp
0x1800432f7  mov     [rax+18h], rsi
0x1800432fb  mov     [rax+20h], rdi
0x1800432ff  push    r14
0x180043301  sub     rsp, 40h
0x180043305  mov     rbx, rcx
0x180043308  mov     rsi, rdx
0x18004330b  add     rcx, 60h ; '`'; lpCriticalSection
0x18004330f  call    cs:__imp_EnterCriticalSection
0x180043315  cmp     dword ptr [rbx+50h], 0
0x180043319  jnz     loc_1800433F4
0x18004331f  lea     r14, [rbx+88h]
0x180043326  mov     rdx, [r14]
0x180043329  test    rdx, rdx
0x18004332c  jz      short loc_180043377
0x18004332e  jmp     short loc_180043367
0x180043330  call    cs:__imp_GetLastError
0x180043336  movzx   edi, ax
0x180043339  lea     rdx, aWaitForCallbac; "wait for callback timer to exit"
0x180043340  or      edi, 80070000h
0x180043346  test    eax, eax
0x180043348  cmovle  edi, eax
0x18004334b  mov     eax, 8000FFFFh
0x180043350  test    edi, edi
0x180043352  cmovns  edi, eax
0x180043355  mov     ecx, edi; int
0x180043357  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x18004335c  test    eax, eax
0x18004335e  jz      loc_180043439
0x180043364  mov     rdx, [r14]; Timer
0x180043367  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18004336b  xor     ecx, ecx; TimerQueue
0x18004336d  call    cs:__imp_DeleteTimerQueueTimer
0x180043373  test    eax, eax
0x180043375  jz      short loc_180043330
0x180043377  mov     rax, [rbx]
0x18004337a  mov     rcx, rbx
0x18004337d  mov     rax, [rax+8]
0x180043381  call    _guard_dispatch_icall
0x180043386  jmp     short loc_1800433BC
0x180043388  call    cs:__imp_GetLastError
0x18004338e  movzx   edi, ax
0x180043391  lea     rdx, aCreateCallback_1; "create callback timer"
0x180043398  or      edi, 80070000h
0x18004339e  test    eax, eax
0x1800433a0  cmovle  edi, eax
0x1800433a3  mov     eax, 8000FFFFh
0x1800433a8  test    edi, edi
0x1800433aa  cmovns  edi, eax
0x1800433ad  mov     ecx, edi; int
0x1800433af  call    ?NeedToRetryAfterWait@@YAHJPEB_W@Z; NeedToRetryAfterWait(long,wchar_t const *)
0x1800433b4  test    eax, eax
0x1800433b6  jz      loc_180043460
0x1800433bc  mov     [rsp+48h+Flags], 108h; Flags
0x1800433c4  lea     r8, ?CallbackWorker@CSusCall@CSusInternalWrapper@@CAXPEAXE@Z; Callback
0x1800433cb  mov     [rsp+48h+Period], 0; Period
0x1800433d3  mov     r9, rbx; Parameter
0x1800433d6  xor     edx, edx; TimerQueue
0x1800433d8  mov     [rsp+48h+DueTime], 0; DueTime
0x1800433e0  mov     rcx, r14; phNewTimer
0x1800433e3  call    cs:__imp_CreateTimerQueueTimer
0x1800433e9  test    eax, eax
0x1800433eb  jz      short loc_180043388
0x1800433ed  mov     dword ptr [rbx+50h], 1
0x1800433f4  test    rsi, rsi
0x1800433f7  jz      short loc_180043437
0x1800433f9  mov     rdx, [rbx+38h]
0x1800433fd  lea     rcx, [rsi+8]
0x180043401  mov     [rbx+48h], rdx
0x180043405  inc     dword ptr [rbx+40h]
0x180043408  mov     [rcx], rdx
0x18004340b  test    rdx, rdx
0x18004340e  jnz     short loc_180043471
0x180043410  mov     rax, [rbx+30h]
0x180043414  test    rax, rax
0x180043417  jz      short loc_18004341C
0x180043419  mov     [rax], rcx
0x18004341c  mov     rax, [rbx+30h]
0x180043420  mov     [rsi+10h], rax
0x180043424  cmp     qword ptr [rbx+38h], 0
0x180043429  mov     [rbx+30h], rcx
0x18004342d  jnz     short loc_180043433
0x18004342f  mov     [rbx+38h], rcx
0x180043433  mov     [rbx+48h], rcx
0x180043437  xor     edi, edi
0x180043439  lea     rcx, [rbx+60h]; lpCriticalSection
0x18004343d  call    cs:__imp_LeaveCriticalSection
0x180043443  mov     rbx, [rsp+48h+arg_0]
0x180043448  mov     eax, edi
0x18004344a  mov     rdi, [rsp+48h+arg_18]
0x18004344f  mov     rbp, [rsp+48h+arg_8]
0x180043454  mov     rsi, [rsp+48h+arg_10]
0x180043459  add     rsp, 40h
0x18004345d  pop     r14
0x18004345f  retn
0x180043460  mov     rax, [rbx]
0x180043463  mov     rcx, rbx
0x180043466  mov     rax, [rax+10h]
0x18004346a  call    _guard_dispatch_icall
0x18004346f  jmp     short loc_180043439
0x180043471  mov     rax, [rdx+8]
0x180043475  mov     [rsi+10h], rax
0x180043479  mov     [rdx+8], rcx
0x18004347d  mov     rax, [rsi+10h]
0x180043481  test    rax, rax
0x180043484  jz      short loc_18004342F
0x180043486  mov     [rax], rcx
0x180043489  jmp     short loc_180043433
```
