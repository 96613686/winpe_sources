# NtGdiConfigureOPMProtectedOutput

- ea: `0x1800047a0`
- end: `0x1800047b8`
- name: `NtGdiConfigureOPMProtectedOutput`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800047a0`

## pseudocode

```c
__int64 NtGdiConfigureOPMProtectedOutput()
{
  __int64 result; // rax

  result = 4520;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800047a0  mov     r10, rcx
0x1800047a3  mov     eax, 11A8h
0x1800047a8  test    byte ptr ds:7FFE0308h, 1
0x1800047b0  jnz     short loc_1800047B5
0x1800047b2  syscall; Low latency system call
0x1800047b4  retn
0x1800047b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800047b7  retn
```
