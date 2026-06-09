# ZwDCompositionGetFrameStatistics

- ea: `0x180003840`
- end: `0x180003858`
- name: `ZwDCompositionGetFrameStatistics`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003840`

## pseudocode

```c
__int64 ZwDCompositionGetFrameStatistics()
{
  __int64 result; // rax

  result = 4397;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003840  mov     r10, rcx
0x180003843  mov     eax, 112Dh
0x180003848  test    byte ptr ds:7FFE0308h, 1
0x180003850  jnz     short loc_180003855
0x180003852  syscall; Low latency system call
0x180003854  retn
0x180003855  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003857  retn
```
