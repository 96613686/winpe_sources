# NtGdiDdDDISubmitCommandToHwQueue

- ea: `0x180006000`
- end: `0x180006018`
- name: `NtGdiDdDDISubmitCommandToHwQueue`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006000`

## pseudocode

```c
__int64 NtGdiDdDDISubmitCommandToHwQueue()
{
  __int64 result; // rax

  result = 4715;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006000  mov     r10, rcx
0x180006003  mov     eax, 126Bh
0x180006008  test    byte ptr ds:7FFE0308h, 1
0x180006010  jnz     short loc_180006015
0x180006012  syscall; Low latency system call
0x180006014  retn
0x180006015  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006017  retn
```
