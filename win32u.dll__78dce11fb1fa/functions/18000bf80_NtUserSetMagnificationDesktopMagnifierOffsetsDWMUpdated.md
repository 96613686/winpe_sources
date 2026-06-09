# NtUserSetMagnificationDesktopMagnifierOffsetsDWMUpdated

- ea: `0x18000bf80`
- end: `0x18000bf98`
- name: `NtUserSetMagnificationDesktopMagnifierOffsetsDWMUpdated`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000bf80`

## pseudocode

```c
__int64 NtUserSetMagnificationDesktopMagnifierOffsetsDWMUpdated()
{
  __int64 result; // rax

  result = 5479;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000bf80  mov     r10, rcx
0x18000bf83  mov     eax, 1567h
0x18000bf88  test    byte ptr ds:7FFE0308h, 1
0x18000bf90  jnz     short loc_18000BF95
0x18000bf92  syscall; Low latency system call
0x18000bf94  retn
0x18000bf95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000bf97  retn
```
