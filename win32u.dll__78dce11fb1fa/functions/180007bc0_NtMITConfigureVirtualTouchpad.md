# NtMITConfigureVirtualTouchpad

- ea: `0x180007bc0`
- end: `0x180007bd8`
- name: `NtMITConfigureVirtualTouchpad`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007bc0`

## pseudocode

```c
__int64 NtMITConfigureVirtualTouchpad()
{
  __int64 result; // rax

  result = 4937;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007bc0  mov     r10, rcx
0x180007bc3  mov     eax, 1349h
0x180007bc8  test    byte ptr ds:7FFE0308h, 1
0x180007bd0  jnz     short loc_180007BD5
0x180007bd2  syscall; Low latency system call
0x180007bd4  retn
0x180007bd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007bd7  retn
```
