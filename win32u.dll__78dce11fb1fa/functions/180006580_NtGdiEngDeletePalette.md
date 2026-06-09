# NtGdiEngDeletePalette

- ea: `0x180006580`
- end: `0x180006598`
- name: `NtGdiEngDeletePalette`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006580`

## pseudocode

```c
__int64 NtGdiEngDeletePalette()
{
  __int64 result; // rax

  result = 4759;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006580  mov     r10, rcx
0x180006583  mov     eax, 1297h
0x180006588  test    byte ptr ds:7FFE0308h, 1
0x180006590  jnz     short loc_180006595
0x180006592  syscall; Low latency system call
0x180006594  retn
0x180006595  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006597  retn
```
