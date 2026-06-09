# NtGdiDdDDICreateSwapChain

- ea: `0x180004e20`
- end: `0x180004e38`
- name: `NtGdiDdDDICreateSwapChain`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004e20`

## pseudocode

```c
__int64 NtGdiDdDDICreateSwapChain()
{
  __int64 result; // rax

  result = 4572;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004e20  mov     r10, rcx
0x180004e23  mov     eax, 11DCh
0x180004e28  test    byte ptr ds:7FFE0308h, 1
0x180004e30  jnz     short loc_180004E35
0x180004e32  syscall; Low latency system call
0x180004e34  retn
0x180004e35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004e37  retn
```
