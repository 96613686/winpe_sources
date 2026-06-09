# NtGdiCreateDIBitmapInternal

- ea: `0x180002560`
- end: `0x180002578`
- name: `NtGdiCreateDIBitmapInternal`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002560`

## pseudocode

```c
__int64 NtGdiCreateDIBitmapInternal()
{
  __int64 result; // rax

  result = 4246;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002560  mov     r10, rcx
0x180002563  mov     eax, 1096h
0x180002568  test    byte ptr ds:7FFE0308h, 1
0x180002570  jnz     short loc_180002575
0x180002572  syscall; Low latency system call
0x180002574  retn
0x180002575  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002577  retn
```
