# HTTP2TimeoutTargetConnection::CancelTimeout(TimerContext *)

- ea: `0x180005ba8`
- end: `0x180005c12`
- name: `?CancelTimeout@HTTP2TimeoutTargetConnection@@QEAAXPEAUTimerContext@@@Z`
- size: `106`
- prototype: `void __fastcall(HTTP2TimeoutTargetConnection *__hidden this, struct TimerContext *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005ae8`
- `0x18000dfe8`
- `0x180013920`
- `0x1800158e0`

## callees

- `0x180005ba8`

## import_xrefs

- `ntdll!DbgPrint` at `0x180005be1`
- `ntdll!DbgPrint` at `0x180005c00`
- `ntdll!DbgPrint` at `0x180005be1`
- `ntdll!DbgPrint` at `0x180005c00`
- `KERNEL32!GetLastError` at `0x180005bd2`
- `KERNEL32!GetLastError` at `0x180005bd2`
- `KERNEL32!Sleep` at `0x180005bec`
- `KERNEL32!Sleep` at `0x180005bec`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180005bc8`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180005bc8`

## string_xrefs

- `0x180005bda`: `RPC: DeleteTimerQueueTimer failed: %d\n`
- `0x180005bf9`: `RPC: DeleteTimerQueueTimer repeatedly failed - execution can't proceed.\n`

## pseudocode

```c
void __fastcall HTTP2TimeoutTargetConnection::CancelTimeout(
        HTTP2TimeoutTargetConnection *this,
        struct TimerContext *a2)
{
  int v2; // edi
  void *v3; // rbx
  DWORD LastError; // eax

  v2 = 0;
  v3 = (void *)_InterlockedExchange64((volatile __int64 *)a2 + 1, 0);
  if ( v3 )
  {
    while ( !DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      DbgPrint("RPC: DeleteTimerQueueTimer failed: %d\n", LastError);
      Sleep(0xAu);
      if ( (unsigned int)++v2 >= 0xA )
      {
        DbgPrint("RPC: DeleteTimerQueueTimer repeatedly failed - execution can't proceed.\n");
        __debugbreak();
      }
    }
  }
}

```

## disassembly

```asm
0x180005ba8  mov     [rsp+arg_0], rbx
0x180005bad  push    rdi
0x180005bae  sub     rsp, 20h
0x180005bb2  xor     ebx, ebx
0x180005bb4  xor     edi, edi
0x180005bb6  xchg    rbx, [rdx+8]
0x180005bba  test    rbx, rbx
0x180005bbd  jz      short loc_180005C07
0x180005bbf  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180005bc3  mov     rdx, rbx; Timer
0x180005bc6  xor     ecx, ecx; TimerQueue
0x180005bc8  call    cs:__imp_DeleteTimerQueueTimer
0x180005bce  test    eax, eax
0x180005bd0  jnz     short loc_180005C07
0x180005bd2  call    cs:__imp_GetLastError
0x180005bd8  mov     edx, eax
0x180005bda  lea     rcx, Format; "RPC: DeleteTimerQueueTimer failed: %d\n"
0x180005be1  call    cs:__imp_DbgPrint
0x180005be7  mov     ecx, 0Ah; dwMilliseconds
0x180005bec  call    cs:__imp_Sleep
0x180005bf2  inc     edi
0x180005bf4  cmp     edi, 0Ah
0x180005bf7  jb      short loc_180005BBF
0x180005bf9  lea     rcx, aRpcDeletetimer_0; "RPC: DeleteTimerQueueTimer repeatedly f"...
0x180005c00  call    cs:__imp_DbgPrint
0x180005c06  int     3; Trap to Debugger
0x180005c07  mov     rbx, [rsp+28h+arg_0]
0x180005c0c  add     rsp, 20h
0x180005c10  pop     rdi
0x180005c11  retn
```
