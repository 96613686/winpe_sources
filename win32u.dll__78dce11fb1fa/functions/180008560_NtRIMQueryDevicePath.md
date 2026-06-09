# NtRIMQueryDevicePath

- ea: `0x180008560`
- end: `0x180008578`
- name: `NtRIMQueryDevicePath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008560`

## pseudocode

```c
__int64 NtRIMQueryDevicePath()
{
  __int64 result; // rax

  result = 5014;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008560  mov     r10, rcx
0x180008563  mov     eax, 1396h
0x180008568  test    byte ptr ds:7FFE0308h, 1
0x180008570  jnz     short loc_180008575
0x180008572  syscall; Low latency system call
0x180008574  retn
0x180008575  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008577  retn
```
