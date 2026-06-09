# NtGdiDdDDIDispMgrCreate

- ea: `0x180005020`
- end: `0x180005038`
- name: `NtGdiDdDDIDispMgrCreate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005020`

## pseudocode

```c
__int64 NtGdiDdDDIDispMgrCreate()
{
  __int64 result; // rax

  result = 4588;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005020  mov     r10, rcx
0x180005023  mov     eax, 11ECh
0x180005028  test    byte ptr ds:7FFE0308h, 1
0x180005030  jnz     short loc_180005035
0x180005032  syscall; Low latency system call
0x180005034  retn
0x180005035  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005037  retn
```
