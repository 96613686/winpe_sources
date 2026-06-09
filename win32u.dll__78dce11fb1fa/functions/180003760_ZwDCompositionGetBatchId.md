# ZwDCompositionGetBatchId

- ea: `0x180003760`
- end: `0x180003778`
- name: `ZwDCompositionGetBatchId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003760`

## pseudocode

```c
__int64 ZwDCompositionGetBatchId()
{
  __int64 result; // rax

  result = 4390;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003760  mov     r10, rcx
0x180003763  mov     eax, 1126h
0x180003768  test    byte ptr ds:7FFE0308h, 1
0x180003770  jnz     short loc_180003775
0x180003772  syscall; Low latency system call
0x180003774  retn
0x180003775  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003777  retn
```
