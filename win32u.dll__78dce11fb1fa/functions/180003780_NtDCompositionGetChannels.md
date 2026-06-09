# NtDCompositionGetChannels

- ea: `0x180003780`
- end: `0x180003798`
- name: `NtDCompositionGetChannels`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003780`

## pseudocode

```c
__int64 NtDCompositionGetChannels()
{
  __int64 result; // rax

  result = 4391;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003780  mov     r10, rcx
0x180003783  mov     eax, 1127h
0x180003788  test    byte ptr ds:7FFE0308h, 1
0x180003790  jnz     short loc_180003795
0x180003792  syscall; Low latency system call
0x180003794  retn
0x180003795  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003797  retn
```
