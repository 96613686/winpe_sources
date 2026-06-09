# NtGdiCreateMetafileDC

- ea: `0x180004880`
- end: `0x180004898`
- name: `NtGdiCreateMetafileDC`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004880`

## pseudocode

```c
__int64 NtGdiCreateMetafileDC()
{
  __int64 result; // rax

  result = 4527;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004880  mov     r10, rcx
0x180004883  mov     eax, 11AFh
0x180004888  test    byte ptr ds:7FFE0308h, 1
0x180004890  jnz     short loc_180004895
0x180004892  syscall; Low latency system call
0x180004894  retn
0x180004895  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004897  retn
```
