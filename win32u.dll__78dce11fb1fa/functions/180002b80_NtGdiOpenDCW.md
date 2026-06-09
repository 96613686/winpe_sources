# NtGdiOpenDCW

- ea: `0x180002b80`
- end: `0x180002b98`
- name: `NtGdiOpenDCW`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b80`

## pseudocode

```c
__int64 NtGdiOpenDCW()
{
  __int64 result; // rax

  result = 4295;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002b80  mov     r10, rcx
0x180002b83  mov     eax, 10C7h
0x180002b88  test    byte ptr ds:7FFE0308h, 1
0x180002b90  jnz     short loc_180002B95
0x180002b92  syscall; Low latency system call
0x180002b94  retn
0x180002b95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002b97  retn
```
