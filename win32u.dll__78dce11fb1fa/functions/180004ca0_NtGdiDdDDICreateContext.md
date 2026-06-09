# NtGdiDdDDICreateContext

- ea: `0x180004ca0`
- end: `0x180004cb8`
- name: `NtGdiDdDDICreateContext`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ca0`

## pseudocode

```c
__int64 NtGdiDdDDICreateContext()
{
  __int64 result; // rax

  result = 4560;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004ca0  mov     r10, rcx
0x180004ca3  mov     eax, 11D0h
0x180004ca8  test    byte ptr ds:7FFE0308h, 1
0x180004cb0  jnz     short loc_180004CB5
0x180004cb2  syscall; Low latency system call
0x180004cb4  retn
0x180004cb5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004cb7  retn
```
