# NtGdiCreateOPMProtectedOutputs

- ea: `0x1800048c0`
- end: `0x1800048d8`
- name: `NtGdiCreateOPMProtectedOutputs`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800048c0`

## pseudocode

```c
__int64 NtGdiCreateOPMProtectedOutputs()
{
  __int64 result; // rax

  result = 4529;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800048c0  mov     r10, rcx
0x1800048c3  mov     eax, 11B1h
0x1800048c8  test    byte ptr ds:7FFE0308h, 1
0x1800048d0  jnz     short loc_1800048D5
0x1800048d2  syscall; Low latency system call
0x1800048d4  retn
0x1800048d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800048d7  retn
```
