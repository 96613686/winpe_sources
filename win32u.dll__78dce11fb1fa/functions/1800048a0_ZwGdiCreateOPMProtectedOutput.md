# ZwGdiCreateOPMProtectedOutput

- ea: `0x1800048a0`
- end: `0x1800048b8`
- name: `ZwGdiCreateOPMProtectedOutput`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800048a0`

## pseudocode

```c
__int64 ZwGdiCreateOPMProtectedOutput()
{
  __int64 result; // rax

  result = 4528;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800048a0  mov     r10, rcx
0x1800048a3  mov     eax, 11B0h
0x1800048a8  test    byte ptr ds:7FFE0308h, 1
0x1800048b0  jnz     short loc_1800048B5
0x1800048b2  syscall; Low latency system call
0x1800048b4  retn
0x1800048b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800048b7  retn
```
