# NtGdiDdDDISubmitCommand

- ea: `0x180005fe0`
- end: `0x180005ff8`
- name: `NtGdiDdDDISubmitCommand`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005fe0`

## pseudocode

```c
__int64 NtGdiDdDDISubmitCommand()
{
  __int64 result; // rax

  result = 4714;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005fe0  mov     r10, rcx
0x180005fe3  mov     eax, 126Ah
0x180005fe8  test    byte ptr ds:7FFE0308h, 1
0x180005ff0  jnz     short loc_180005FF5
0x180005ff2  syscall; Low latency system call
0x180005ff4  retn
0x180005ff5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005ff7  retn
```
