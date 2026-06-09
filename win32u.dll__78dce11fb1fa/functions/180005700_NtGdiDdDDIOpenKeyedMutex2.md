# NtGdiDdDDIOpenKeyedMutex2

- ea: `0x180005700`
- end: `0x180005718`
- name: `NtGdiDdDDIOpenKeyedMutex2`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005700`

## pseudocode

```c
__int64 NtGdiDdDDIOpenKeyedMutex2()
{
  __int64 result; // rax

  result = 4643;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005700  mov     r10, rcx
0x180005703  mov     eax, 1223h
0x180005708  test    byte ptr ds:7FFE0308h, 1
0x180005710  jnz     short loc_180005715
0x180005712  syscall; Low latency system call
0x180005714  retn
0x180005715  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005717  retn
```
