# NtGdiComputeXformCoefficients

- ea: `0x180002300`
- end: `0x180002318`
- name: `NtGdiComputeXformCoefficients`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002300`

## pseudocode

```c
__int64 NtGdiComputeXformCoefficients()
{
  __int64 result; // rax

  result = 4227;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002300  mov     r10, rcx
0x180002303  mov     eax, 1083h
0x180002308  test    byte ptr ds:7FFE0308h, 1
0x180002310  jnz     short loc_180002315
0x180002312  syscall; Low latency system call
0x180002314  retn
0x180002315  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002317  retn
```
