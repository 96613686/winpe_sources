# WinHvpOnCallCompletionDpcRoutine

- ea: `0x1400079f0`
- end: `0x140007a3a`
- name: `WinHvpOnCallCompletionDpcRoutine`
- size: `74`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400024d0`
- `0x1400079f0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140007a07`
- `ntoskrnl!KeSetEvent` at `0x140007a1f`
- `ntoskrnl!KeSetEvent` at `0x140007a07`
- `ntoskrnl!KeSetEvent` at `0x140007a1f`

## pseudocode

```c
void __fastcall WinHvpOnCallCompletionDpcRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        char *SystemArgument1,
        PVOID SystemArgument2)
{
  if ( SystemArgument1 )
  {
    KeSetEvent((PRKEVENT)(SystemArgument1 + 160), 0, 0);
    WinHvpDereferencePartition(SystemArgument1);
  }
  else
  {
    KeSetEvent(&WinHvpGlobalAsyncEvent, 0, 0);
  }
}

```

## disassembly

```asm
0x1400079f0  push    rbx
0x1400079f2  sub     rsp, 20h
0x1400079f6  xor     edx, edx; Increment
0x1400079f8  mov     rbx, r8
0x1400079fb  test    r8, r8
0x1400079fe  jnz     short loc_140007A15
0x140007a00  lea     rcx, WinHvpGlobalAsyncEvent; Event
0x140007a07  call    cs:__imp_KeSetEvent
0x140007a0e  nop     dword ptr [rax+rax+00h]
0x140007a13  jmp     short loc_140007A33
0x140007a15  lea     rcx, [r8+0A0h]; Event
0x140007a1c  xor     r8d, r8d; Wait
0x140007a1f  call    cs:__imp_KeSetEvent
0x140007a26  nop     dword ptr [rax+rax+00h]
0x140007a2b  mov     rcx, rbx
0x140007a2e  call    WinHvpDereferencePartition
0x140007a33  add     rsp, 20h
0x140007a37  pop     rbx
0x140007a38  retn
```
