# NtGdiHfontCreate

- ea: `0x180001d80`
- end: `0x180001d98`
- name: `NtGdiHfontCreate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001d80`

## pseudocode

```c
__int64 NtGdiHfontCreate()
{
  __int64 result; // rax

  result = 4183;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001d80  mov     r10, rcx
0x180001d83  mov     eax, 1057h
0x180001d88  test    byte ptr ds:7FFE0308h, 1
0x180001d90  jnz     short loc_180001D95
0x180001d92  syscall; Low latency system call
0x180001d94  retn
0x180001d95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001d97  retn
```
