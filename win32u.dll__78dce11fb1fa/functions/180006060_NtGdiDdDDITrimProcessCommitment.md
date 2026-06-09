# NtGdiDdDDITrimProcessCommitment

- ea: `0x180006060`
- end: `0x180006078`
- name: `NtGdiDdDDITrimProcessCommitment`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006060`

## pseudocode

```c
__int64 NtGdiDdDDITrimProcessCommitment()
{
  __int64 result; // rax

  result = 4718;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006060  mov     r10, rcx
0x180006063  mov     eax, 126Eh
0x180006068  test    byte ptr ds:7FFE0308h, 1
0x180006070  jnz     short loc_180006075
0x180006072  syscall; Low latency system call
0x180006074  retn
0x180006075  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006077  retn
```
