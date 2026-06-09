# NtGdiCreateColorSpace

- ea: `0x180003380`
- end: `0x180003398`
- name: `NtGdiCreateColorSpace`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003380`

## pseudocode

```c
__int64 NtGdiCreateColorSpace()
{
  __int64 result; // rax

  result = 4359;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003380  mov     r10, rcx
0x180003383  mov     eax, 1107h
0x180003388  test    byte ptr ds:7FFE0308h, 1
0x180003390  jnz     short loc_180003395
0x180003392  syscall; Low latency system call
0x180003394  retn
0x180003395  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003397  retn
```
