# ZwDCompositionGetFrameIdFromBatchId

- ea: `0x180003800`
- end: `0x180003818`
- name: `ZwDCompositionGetFrameIdFromBatchId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003800`

## pseudocode

```c
__int64 ZwDCompositionGetFrameIdFromBatchId()
{
  __int64 result; // rax

  result = 4395;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003800  mov     r10, rcx
0x180003803  mov     eax, 112Bh
0x180003808  test    byte ptr ds:7FFE0308h, 1
0x180003810  jnz     short loc_180003815
0x180003812  syscall; Low latency system call
0x180003814  retn
0x180003815  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003817  retn
```
