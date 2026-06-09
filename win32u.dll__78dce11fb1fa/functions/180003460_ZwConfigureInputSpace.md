# ZwConfigureInputSpace

- ea: `0x180003460`
- end: `0x180003478`
- name: `ZwConfigureInputSpace`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003460`

## pseudocode

```c
__int64 ZwConfigureInputSpace()
{
  __int64 result; // rax

  result = 4366;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003460  mov     r10, rcx
0x180003463  mov     eax, 110Eh
0x180003468  test    byte ptr ds:7FFE0308h, 1
0x180003470  jnz     short loc_180003475
0x180003472  syscall; Low latency system call
0x180003474  retn
0x180003475  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003477  retn
```
