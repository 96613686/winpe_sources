# LRPC_CCALL::UnregisterCallForCancels(void)

- ea: `0x180026c60`
- end: `0x180026de6`
- name: `?UnregisterCallForCancels@LRPC_CCALL@@UEAAXXZ`
- size: `390`
- prototype: `void __fastcall(LRPC_CCALL *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800989c0`
- `0x1800a3c70`

## callees

- `0x180026c60`
- `0x180026df0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x180026d4a`
- `KERNELBASE!Sleep` at `0x180026d4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026dd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026dd5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026d9c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026d9c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026db5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180026db5`

## pseudocode

```c
void __fastcall LRPC_CCALL::UnregisterCallForCancels(LRPC_CCALL *this)
{
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned __int64 ReservedForNtRpc; // rbx
  signed __int64 v5; // rbp
  signed __int64 v6; // rdi
  __int64 v7; // rax

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
    v5 = *((_QWORD *)this + 104);
    do
    {
      v6 = *(_QWORD *)(ReservedForNtRpc + 72);
      if ( (LRPC_CCALL *)(v6 & 0xFFFFFFFFFFFFFFFCuLL) != this )
      {
        RpcpReportFatalError(21, this, v2, v3);
        __debugbreak();
      }
      while ( (*(_QWORD *)(ReservedForNtRpc + 72) & 1) != 0 )
        Sleep(0xAu);
    }
    while ( v6 != _InterlockedCompareExchange64((volatile signed __int64 *)(ReservedForNtRpc + 72), v5, v6) );
    v7 = *((_QWORD *)this + 105);
    *((_QWORD *)this + 104) = 0;
    if ( v7 )
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
0x180026c60  push    rsi
0x180026c62  sub     rsp, 20h
0x180026c66  mov     eax, [rcx+120h]
0x180026c6c  mov     rsi, rcx
0x180026c6f  bt      eax, 0Bh
0x180026c73  jnb     loc_180026D29
0x180026c79  mov     rax, [rcx]
0x180026c7c  mov     rax, [rax+120h]
0x180026c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c88  test    eax, eax
0x180026c8a  jnz     loc_180026D85
0x180026c90  mov     [rsp+28h+arg_0], rbx
0x180026c95  mov     rbx, gs:30h
0x180026c9e  mov     rbx, [rbx+1698h]
0x180026ca5  test    rbx, rbx
0x180026ca8  jz      short loc_180026CCA
0x180026caa  mov     rax, 0ABABABABDEDEDEDEh
0x180026cb4  xor     rbx, rax
0x180026cb7  mov     rax, gs:30h
0x180026cc0  mov     rcx, [rax+48h]
0x180026cc4  cmp     [rbx+10h], rcx
0x180026cc8  jnz     short loc_180026D3E
0x180026cca  mov     [rsp+28h+arg_8], rbp
0x180026ccf  mov     rbp, [rsi+340h]
0x180026cd6  mov     [rsp+28h+arg_10], rdi
0x180026cdb  nop     dword ptr [rax+rax+00h]
0x180026ce0  mov     rdi, [rbx+48h]
0x180026ce4  mov     rax, rdi
0x180026ce7  and     rax, 0FFFFFFFFFFFFFFFCh
0x180026ceb  cmp     rax, rsi
0x180026cee  jnz     short loc_180026D30
0x180026cf0  mov     rax, [rbx+48h]
0x180026cf4  test    al, 1
0x180026cf6  jnz     short loc_180026D45
0x180026cf8  mov     rax, rdi
0x180026cfb  lock cmpxchg [rbx+48h], rbp
0x180026d01  jnz     short loc_180026CE0
0x180026d03  mov     rax, [rsi+348h]
0x180026d0a  mov     qword ptr [rsi+340h], 0
0x180026d15  test    rax, rax
0x180026d18  jnz     short loc_180026D61
0x180026d1a  mov     rbp, [rsp+28h+arg_8]
0x180026d1f  mov     rdi, [rsp+28h+arg_10]
0x180026d24  mov     rbx, [rsp+28h+arg_0]
0x180026d29  add     rsp, 20h
0x180026d2d  pop     rsi
0x180026d2e  retn
0x180026d30  mov     rdx, rsi
0x180026d33  mov     ecx, 15h
0x180026d38  call    RpcpReportFatalError
0x180026d3d  int     3; Trap to Debugger
0x180026d3e  mov     ecx, 1Eh
0x180026d43  int     29h; Win8: RtlFailFast(ecx)
0x180026d45  mov     ecx, 0Ah; dwMilliseconds
0x180026d4a  call    cs:__imp_Sleep
0x180026d51  nop     dword ptr [rax+rax+00h]
0x180026d56  mov     rcx, [rbx+48h]
0x180026d5a  test    cl, 1
0x180026d5d  jz      short loc_180026CF8
0x180026d5f  jmp     short loc_180026D45
0x180026d61  lock or dword ptr [rsi+120h], 10000h
0x180026d6c  mov     rax, [rsi+348h]
0x180026d73  test    rax, rax
0x180026d76  jnz     short loc_180026D98
0x180026d78  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180026d83  jmp     short loc_180026D1A
0x180026d85  mov     rax, [rsi+250h]
0x180026d8c  cmp     dword ptr [rax+8], 0
0x180026d90  jz      loc_180026C90
0x180026d96  jmp     short loc_180026D29
0x180026d98  mov     rcx, [rbx+18h]; hEvent
0x180026d9c  call    cs:__imp_ResetEvent
0x180026da3  nop     dword ptr [rax+rax+00h]
0x180026da8  mov     r8, [rbx+18h]; CompletionEvent
0x180026dac  xor     ecx, ecx; TimerQueue
0x180026dae  mov     rdx, [rsi+348h]; Timer
0x180026db5  call    cs:__imp_DeleteTimerQueueTimer
0x180026dbc  nop     dword ptr [rax+rax+00h]
0x180026dc1  lock and dword ptr [rsi+120h], 0FFFEFFFFh
0x180026dcc  mov     rcx, [rbx+18h]; hHandle
0x180026dd0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180026dd5  call    cs:__imp_WaitForSingleObject
0x180026ddc  nop     dword ptr [rax+rax+00h]
0x180026de1  jmp     loc_180026D1A
```
