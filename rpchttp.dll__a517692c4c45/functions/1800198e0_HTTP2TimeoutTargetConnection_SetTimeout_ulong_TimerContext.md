# HTTP2TimeoutTargetConnection::SetTimeout(ulong,TimerContext *)

- ea: `0x1800198e0`
- end: `0x180019920`
- name: `?SetTimeout@HTTP2TimeoutTargetConnection@@QEAAJKPEAUTimerContext@@@Z`
- size: `64`
- prototype: `int(HTTP2TimeoutTargetConnection *__hidden this, unsigned int, struct TimerContext *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dfe8`
- `0x180013920`
- `0x1800158e0`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18001990c`
- `KERNEL32!CreateTimerQueueTimer` at `0x18001990c`

## pseudocode

```c
__int64 __fastcall HTTP2TimeoutTargetConnection::SetTimeout(HTTP2TimeoutTargetConnection *this, __int64 a2, void **a3)
{
  return !CreateTimerQueueTimer(a3 + 1, 0, HTTP2TimeoutTimerCallback, a3, 0xDBBA0u, 0, 0x10u) ? 0xE : 0;
}

```

## disassembly

```asm
0x1800198e0  sub     rsp, 48h
0x1800198e4  lea     rcx, [r8+8]; phNewTimer
0x1800198e8  mov     [rsp+48h+Flags], 10h; Flags
0x1800198f0  mov     r9, r8; Parameter
0x1800198f3  mov     [rsp+48h+Period], 0; Period
0x1800198fb  lea     r8, ?HTTP2TimeoutTimerCallback@@YAXPEAXE@Z; Callback
0x180019902  mov     [rsp+48h+DueTime], 0DBBA0h; DueTime
0x18001990a  xor     edx, edx; TimerQueue
0x18001990c  call    cs:__imp_CreateTimerQueueTimer
0x180019912  neg     eax
0x180019914  sbb     eax, eax
0x180019916  not     eax
0x180019918  and     eax, 0Eh
0x18001991b  add     rsp, 48h
0x18001991f  retn
```
