# NtMITAccessibilityTimerNotification

- ea: `0x180007b80`
- end: `0x180007b98`
- name: `NtMITAccessibilityTimerNotification`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007b80`

## pseudocode

```c
__int64 NtMITAccessibilityTimerNotification()
{
  __int64 result; // rax

  result = 4935;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007b80  mov     r10, rcx
0x180007b83  mov     eax, 1347h
0x180007b88  test    byte ptr ds:7FFE0308h, 1
0x180007b90  jnz     short loc_180007B95
0x180007b92  syscall; Low latency system call
0x180007b94  retn
0x180007b95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007b97  retn
```
