# NtUserEnableIAMAccess

- ea: `0x180009400`
- end: `0x180009418`
- name: `NtUserEnableIAMAccess`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009400`

## pseudocode

```c
__int64 NtUserEnableIAMAccess()
{
  __int64 result; // rax

  result = 5131;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009400  mov     r10, rcx
0x180009403  mov     eax, 140Bh
0x180009408  test    byte ptr ds:7FFE0308h, 1
0x180009410  jnz     short loc_180009415
0x180009412  syscall; Low latency system call
0x180009414  retn
0x180009415  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009417  retn
```
