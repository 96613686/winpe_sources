# NtGdiDwmCreatedBitmapRemotingOutput

- ea: `0x180006340`
- end: `0x180006358`
- name: `NtGdiDwmCreatedBitmapRemotingOutput`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006340`

## pseudocode

```c
__int64 NtGdiDwmCreatedBitmapRemotingOutput()
{
  __int64 result; // rax

  result = 4741;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006340  mov     r10, rcx
0x180006343  mov     eax, 1285h
0x180006348  test    byte ptr ds:7FFE0308h, 1
0x180006350  jnz     short loc_180006355
0x180006352  syscall; Low latency system call
0x180006354  retn
0x180006355  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006357  retn
```
