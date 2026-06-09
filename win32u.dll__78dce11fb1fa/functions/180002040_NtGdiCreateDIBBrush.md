# NtGdiCreateDIBBrush

- ea: `0x180002040`
- end: `0x180002058`
- name: `NtGdiCreateDIBBrush`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002040`

## pseudocode

```c
__int64 NtGdiCreateDIBBrush()
{
  __int64 result; // rax

  result = 4205;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002040  mov     r10, rcx
0x180002043  mov     eax, 106Dh
0x180002048  test    byte ptr ds:7FFE0308h, 1
0x180002050  jnz     short loc_180002055
0x180002052  syscall; Low latency system call
0x180002054  retn
0x180002055  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002057  retn
```
