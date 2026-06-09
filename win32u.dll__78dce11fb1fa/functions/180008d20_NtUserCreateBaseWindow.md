# NtUserCreateBaseWindow

- ea: `0x180008d20`
- end: `0x180008d38`
- name: `NtUserCreateBaseWindow`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008d20`

## pseudocode

```c
__int64 NtUserCreateBaseWindow()
{
  __int64 result; // rax

  result = 5076;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008d20  mov     r10, rcx
0x180008d23  mov     eax, 13D4h
0x180008d28  test    byte ptr ds:7FFE0308h, 1
0x180008d30  jnz     short loc_180008D35
0x180008d32  syscall; Low latency system call
0x180008d34  retn
0x180008d35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008d37  retn
```
