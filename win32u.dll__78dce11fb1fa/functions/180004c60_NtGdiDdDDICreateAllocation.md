# NtGdiDdDDICreateAllocation

- ea: `0x180004c60`
- end: `0x180004c78`
- name: `NtGdiDdDDICreateAllocation`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c60`

## pseudocode

```c
__int64 NtGdiDdDDICreateAllocation()
{
  __int64 result; // rax

  result = 4558;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004c60  mov     r10, rcx
0x180004c63  mov     eax, 11CEh
0x180004c68  test    byte ptr ds:7FFE0308h, 1
0x180004c70  jnz     short loc_180004C75
0x180004c72  syscall; Low latency system call
0x180004c74  retn
0x180004c75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004c77  retn
```
