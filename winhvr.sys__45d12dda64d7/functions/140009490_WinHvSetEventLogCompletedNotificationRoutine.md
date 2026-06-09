# WinHvSetEventLogCompletedNotificationRoutine

- ea: `0x140009490`
- end: `0x140009498`
- name: `WinHvSetEventLogCompletedNotificationRoutine`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall WinHvSetEventLogCompletedNotificationRoutine(__int64 a1)
{
  WinHvpEventLogCompletedNotificationRoutine = a1;
}

```

## disassembly

```asm
0x140009490  mov     cs:WinHvpEventLogCompletedNotificationRoutine, rcx
0x140009497  retn
```
