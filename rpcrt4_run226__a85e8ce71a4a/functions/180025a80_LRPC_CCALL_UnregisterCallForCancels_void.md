# LRPC_CCALL::UnregisterCallForCancels(void)

- ea: `0x180025a80`
- end: `0x180025bed`
- name: `?UnregisterCallForCancels@LRPC_CCALL@@UEAAXXZ`
- size: `365`
- prototype: `void __fastcall(LRPC_CCALL *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800952b0`
- `0x1800a05d0`

## callees

- `0x180025a80`
- `0x180025c00`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180025b69`
- `KERNELBASE!Sleep` at `0x180025b69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025be2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025be2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025bb5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025bb5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180025bc8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180025bc8`

## pseudocode

```c
void __fastcall LRPC_CCALL::UnregisterCallForCancels(LRPC_CCALL *this)
{
  unsigned __int64 ReservedForNtRpc; // rbx
  signed __int64 v3; // rbp
  signed __int64 v4; // rdi
  __int64 v5; // rax

  if ( (*((_DWORD *)this + 72) & 0x800) != 0
    && (!(*(unsigned int (__fastcall **)(LRPC_CCALL *))(*(_QWORD *)this + 288LL))(this)
     || !*(_DWORD *)(*((_QWORD *)this + 74) + 8LL)) )
  {
    ReservedForNtRpc = (unsigned __int64)NtCurrentTeb()->ReservedForNtRpc;
    if ( ReservedForNtRpc )
    {
      ReservedForNtRpc ^= 0xABABABABDEDEDEDEuLL;
      if ( *(HANDLE *)(ReservedForNtRpc + 16) != NtCurrentTeb()->ClientId.UniqueThread )
        __fastfail(0x1Eu);
    }
    v3 = *((_QWORD *)this + 104);
    do
    {
      v4 = *(_QWORD *)(ReservedForNtRpc + 72);
      if ( (LRPC_CCALL *)(v4 & 0xFFFFFFFFFFFFFFFCuLL) != this )
      {
        RpcpReportFatalError(21, this);
        __debugbreak();
      }
      while ( (*(_QWORD *)(ReservedForNtRpc + 72) & 1) != 0 )
        Sleep(0xAu);
    }
    while ( v4 != _InterlockedCompareExchange64((volatile signed __int64 *)(ReservedForNtRpc + 72), v3, v4) );
    v5 = *((_QWORD *)this + 105);
    *((_QWORD *)this + 104) = 0;
    if ( v5 )
    {
      _InterlockedOr((volatile signed __int32 *)this + 72, 0x10000u);
      if ( *((_QWORD *)this + 105) )
      {
        ResetEvent(*(HANDLE *)(ReservedForNtRpc + 24));
        DeleteTimerQueueTimer(0, *((HANDLE *)this + 105), *(HANDLE *)(ReservedForNtRpc + 24));
        _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
        WaitForSingleObject(*(HANDLE *)(ReservedForNtRpc + 24), 0xFFFFFFFF);
      }
      else
      {
        _InterlockedAnd((volatile signed __int32 *)this + 72, 0xFFFEFFFF);
      }
    }
  }
}

```

## disassembly

```asm
0x180025a80  push    rsi
0x180025a82  sub     rsp, 20h
0x180025a86  mov     eax, [rcx+120h]
0x180025a8c  mov     rsi, rcx
0x180025a8f  bt      eax, 0Bh
0x180025a93  jnb     loc_180025B49
0x180025a99  mov     rax, [rcx]
0x180025a9c  mov     rax, [rax+120h]
0x180025aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aa8  test    eax, eax
0x180025aaa  jnz     loc_180025B9E
0x180025ab0  mov     [rsp+28h+arg_0], rbx
0x180025ab5  mov     rbx, gs:30h
0x180025abe  mov     rbx, [rbx+1698h]
0x180025ac5  test    rbx, rbx
0x180025ac8  jz      short loc_180025AEA
0x180025aca  mov     rax, 0ABABABABDEDEDEDEh
0x180025ad4  xor     rbx, rax
0x180025ad7  mov     rax, gs:30h
0x180025ae0  mov     rcx, [rax+48h]
0x180025ae4  cmp     [rbx+10h], rcx
0x180025ae8  jnz     short loc_180025B5D
0x180025aea  mov     [rsp+28h+arg_8], rbp
0x180025aef  mov     rbp, [rsi+340h]
0x180025af6  mov     [rsp+28h+arg_10], rdi
0x180025afb  nop     dword ptr [rax+rax+00h]
0x180025b00  mov     rdi, [rbx+48h]
0x180025b04  mov     rax, rdi
0x180025b07  and     rax, 0FFFFFFFFFFFFFFFCh
0x180025b0b  cmp     rax, rsi
0x180025b0e  jnz     short loc_180025B4F
0x180025b10  mov     rax, [rbx+48h]
0x180025b14  test    al, 1
0x180025b16  jnz     short loc_180025B64
0x180025b18  mov     rax, rdi
0x180025b1b  lock cmpxchg [rbx+48h], rbp
0x180025b21  jnz     short loc_180025B00
0x180025b23  mov     rax, [rsi+348h]
0x180025b2a  mov     qword ptr [rsi+340h], 0
0x180025b35  test    rax, rax
0x180025b38  jnz     short loc_180025B7A
0x180025b3a  mov     rbp, [rsp+28h+arg_8]
0x180025b3f  mov     rdi, [rsp+28h+arg_10]
0x180025b44  mov     rbx, [rsp+28h+arg_0]
0x180025b49  add     rsp, 20h
0x180025b4d  pop     rsi
0x180025b4e  retn
0x180025b4f  mov     rdx, rsi
0x180025b52  mov     ecx, 15h
0x180025b57  call    RpcpReportFatalError
0x180025b5c  int     3; Trap to Debugger
0x180025b5d  mov     ecx, 1Eh
0x180025b62  int     29h; Win8: RtlFailFast(ecx)
0x180025b64  mov     ecx, 0Ah; dwMilliseconds
0x180025b69  call    cs:__imp_Sleep
0x180025b6f  mov     rcx, [rbx+48h]
0x180025b73  test    cl, 1
0x180025b76  jz      short loc_180025B18
0x180025b78  jmp     short loc_180025B64
0x180025b7a  lock or dword ptr [rsi+120h], 10000h
0x180025b85  mov     rax, [rsi+348h]
0x180025b8c  test    rax, rax
0x180025b8f  jnz     short loc_180025BB1
0x180025b91  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180025b9c  jmp     short loc_180025B3A
0x180025b9e  mov     rax, [rsi+250h]
0x180025ba5  cmp     dword ptr [rax+8], 0
0x180025ba9  jz      loc_180025AB0
0x180025baf  jmp     short loc_180025B49
0x180025bb1  mov     rcx, [rbx+18h]; hEvent
0x180025bb5  call    cs:__imp_ResetEvent
0x180025bbb  mov     r8, [rbx+18h]; CompletionEvent
0x180025bbf  xor     ecx, ecx; TimerQueue
0x180025bc1  mov     rdx, [rsi+348h]; Timer
0x180025bc8  call    cs:__imp_DeleteTimerQueueTimer
0x180025bce  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180025bd9  mov     rcx, [rbx+18h]; hHandle
0x180025bdd  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180025be2  call    cs:__imp_WaitForSingleObject
0x180025be8  jmp     loc_180025B3A
```
