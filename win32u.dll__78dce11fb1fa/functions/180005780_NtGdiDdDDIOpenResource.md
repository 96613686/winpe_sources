# NtGdiDdDDIOpenResource

- ea: `0x180005780`
- end: `0x180005798`
- name: `NtGdiDdDDIOpenResource`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005780`

## pseudocode

```c
__int64 NtGdiDdDDIOpenResource()
{
  __int64 result; // rax

  result = 4647;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005780  mov     r10, rcx
0x180005783  mov     eax, 1227h
0x180005788  test    byte ptr ds:7FFE0308h, 1
0x180005790  jnz     short loc_180005795
0x180005792  syscall; Low latency system call
0x180005794  retn
0x180005795  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005797  retn
```
