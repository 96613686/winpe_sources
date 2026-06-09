# WskSyncIrpCompletionRoutine

- ea: `0x14000a970`
- end: `0x14000a995`
- name: `WskSyncIrpCompletionRoutine`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000a97e`
- `ntoskrnl!KeSetEvent` at `0x14000a97e`

## pseudocode

```c
__int64 __fastcall WskSyncIrpCompletionRoutine(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 2, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000a970  sub     rsp, 28h
0x14000a974  mov     rcx, r8; Event
0x14000a977  xor     r8d, r8d; Wait
0x14000a97a  lea     edx, [r8+2]; Increment
0x14000a97e  call    cs:__imp_KeSetEvent
0x14000a985  nop     dword ptr [rax+rax+00h]
0x14000a98a  mov     eax, 0C0000016h
0x14000a98f  add     rsp, 28h
0x14000a993  retn
```
