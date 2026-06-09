# ZwDCompositionProcessChannelBatchBuffer

- ea: `0x180003900`
- end: `0x180003918`
- name: `ZwDCompositionProcessChannelBatchBuffer`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003900`

## pseudocode

```c
__int64 ZwDCompositionProcessChannelBatchBuffer()
{
  __int64 result; // rax

  result = 4403;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003900  mov     r10, rcx
0x180003903  mov     eax, 1133h
0x180003908  test    byte ptr ds:7FFE0308h, 1
0x180003910  jnz     short loc_180003915
0x180003912  syscall; Low latency system call
0x180003914  retn
0x180003915  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003917  retn
```
