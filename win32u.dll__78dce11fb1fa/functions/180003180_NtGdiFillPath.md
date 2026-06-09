# NtGdiFillPath

- ea: `0x180003180`
- end: `0x180003198`
- name: `NtGdiFillPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003180`

## pseudocode

```c
__int64 NtGdiFillPath()
{
  __int64 result; // rax

  result = 4343;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003180  mov     r10, rcx
0x180003183  mov     eax, 10F7h
0x180003188  test    byte ptr ds:7FFE0308h, 1
0x180003190  jnz     short loc_180003195
0x180003192  syscall; Low latency system call
0x180003194  retn
0x180003195  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003197  retn
```
