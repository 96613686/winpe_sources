# NtDCompositionTelemetrySetApplicationId

- ea: `0x180003ae0`
- end: `0x180003af8`
- name: `NtDCompositionTelemetrySetApplicationId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003ae0`

## pseudocode

```c
__int64 NtDCompositionTelemetrySetApplicationId()
{
  __int64 result; // rax

  result = 4418;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003ae0  mov     r10, rcx
0x180003ae3  mov     eax, 1142h
0x180003ae8  test    byte ptr ds:7FFE0308h, 1
0x180003af0  jnz     short loc_180003AF5
0x180003af2  syscall; Low latency system call
0x180003af4  retn
0x180003af5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003af7  retn
```
