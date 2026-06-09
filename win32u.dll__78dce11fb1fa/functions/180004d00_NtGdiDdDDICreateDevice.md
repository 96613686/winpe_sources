# NtGdiDdDDICreateDevice

- ea: `0x180004d00`
- end: `0x180004d18`
- name: `NtGdiDdDDICreateDevice`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004d00`

## pseudocode

```c
__int64 NtGdiDdDDICreateDevice()
{
  __int64 result; // rax

  result = 4563;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004d00  mov     r10, rcx
0x180004d03  mov     eax, 11D3h
0x180004d08  test    byte ptr ds:7FFE0308h, 1
0x180004d10  jnz     short loc_180004D15
0x180004d12  syscall; Low latency system call
0x180004d14  retn
0x180004d15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004d17  retn
```
