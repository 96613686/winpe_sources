# NtUserScaleSystemMetricForDPIWithoutCache

- ea: `0x18000b9a0`
- end: `0x18000b9b8`
- name: `NtUserScaleSystemMetricForDPIWithoutCache`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b9a0`

## pseudocode

```c
__int64 NtUserScaleSystemMetricForDPIWithoutCache()
{
  __int64 result; // rax

  result = 5432;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b9a0  mov     r10, rcx
0x18000b9a3  mov     eax, 1538h
0x18000b9a8  test    byte ptr ds:7FFE0308h, 1
0x18000b9b0  jnz     short loc_18000B9B5
0x18000b9b2  syscall; Low latency system call
0x18000b9b4  retn
0x18000b9b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b9b7  retn
```
