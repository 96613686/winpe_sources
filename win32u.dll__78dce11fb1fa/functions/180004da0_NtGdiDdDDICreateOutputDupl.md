# NtGdiDdDDICreateOutputDupl

- ea: `0x180004da0`
- end: `0x180004db8`
- name: `NtGdiDdDDICreateOutputDupl`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004da0`

## pseudocode

```c
__int64 NtGdiDdDDICreateOutputDupl()
{
  __int64 result; // rax

  result = 4568;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004da0  mov     r10, rcx
0x180004da3  mov     eax, 11D8h
0x180004da8  test    byte ptr ds:7FFE0308h, 1
0x180004db0  jnz     short loc_180004DB5
0x180004db2  syscall; Low latency system call
0x180004db4  retn
0x180004db5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004db7  retn
```
