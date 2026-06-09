# StopIdleTimer

- ea: `0x14002a018`
- end: `0x14002a0a8`
- name: `StopIdleTimer`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006af8`
- `0x140029e6c`
- `0x140029f14`

## callees

- `0x1400088b4`
- `0x14002a018`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14002a035`
- `ntoskrnl!KeCancelTimer` at `0x14002a035`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002a041`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14002a041`

## string_xrefs

- `0x14002a06e`: `noIdleDpcPendingEvent (wait for DPC to complete)`

## pseudocode

```c
NTSTATUS __fastcall StopIdleTimer(__int64 a1)
{
  int v2; // edx
  _QWORD *v3; // rdi
  NTSTATUS result; // eax

  if ( *(_BYTE *)(a1 + 1376) != 1 )
  {
    KeCancelTimer((PKTIMER)(a1 + 704));
    KeFlushQueuedDpcs();
    v3 = (_QWORD *)(a1 + 1368);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 4;
      WPP_RECORDER_SF_(*v3, v2, 2, 52, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
    }
    return WaitForSignal((PVOID)(a1 + 768), "noIdleDpcPendingEvent (wait for DPC to complete)", *v3);
  }
  return result;
}

```

## disassembly

```asm
0x14002a018  mov     [rsp+arg_0], rbx
0x14002a01d  push    rdi
0x14002a01e  sub     rsp, 30h
0x14002a022  cmp     byte ptr [rcx+560h], 1
0x14002a029  mov     rbx, rcx
0x14002a02c  jz      short loc_14002A07A
0x14002a02e  add     rcx, 2C0h; PKTIMER
0x14002a035  call    cs:__imp_KeCancelTimer
0x14002a03c  nop     dword ptr [rax+rax+00h]
0x14002a041  call    cs:__imp_KeFlushQueuedDpcs
0x14002a048  nop     dword ptr [rax+rax+00h]
0x14002a04d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a054  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a05b  lea     rdi, [rbx+558h]
0x14002a062  jnz     short loc_14002A086
0x14002a064  mov     r8, [rdi]
0x14002a067  lea     rcx, [rbx+300h]; Object
0x14002a06e  lea     rdx, aNoidledpcpendi; "noIdleDpcPendingEvent (wait for DPC to "...
0x14002a075  call    WaitForSignal
0x14002a07a  mov     rbx, [rsp+38h+arg_0]
0x14002a07f  add     rsp, 30h
0x14002a083  pop     rdi
0x14002a084  retn
0x14002a086  mov     rcx, [rdi]
0x14002a089  lea     rax, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x14002a090  mov     r9d, 34h ; '4'
0x14002a096  mov     [rsp+38h+var_18], rax
0x14002a09b  mov     dl, 4
0x14002a09d  lea     r8d, [r9-32h]
0x14002a0a1  call    WPP_RECORDER_SF_
0x14002a0a6  jmp     short loc_14002A064
```
