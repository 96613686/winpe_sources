# NtGdiDdDDIOpenSyncObjectFromNtHandle2

- ea: `0x180005800`
- end: `0x180005818`
- name: `NtGdiDdDDIOpenSyncObjectFromNtHandle2`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005800`

## pseudocode

```c
__int64 NtGdiDdDDIOpenSyncObjectFromNtHandle2()
{
  __int64 result; // rax

  result = 4651;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005800  mov     r10, rcx
0x180005803  mov     eax, 122Bh
0x180005808  test    byte ptr ds:7FFE0308h, 1
0x180005810  jnz     short loc_180005815
0x180005812  syscall; Low latency system call
0x180005814  retn
0x180005815  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005817  retn
```
