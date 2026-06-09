# NtGdiCreatePaletteInternal

- ea: `0x180002660`
- end: `0x180002678`
- name: `NtGdiCreatePaletteInternal`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002660`

## pseudocode

```c
__int64 NtGdiCreatePaletteInternal()
{
  __int64 result; // rax

  result = 4254;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002660  mov     r10, rcx
0x180002663  mov     eax, 109Eh
0x180002668  test    byte ptr ds:7FFE0308h, 1
0x180002670  jnz     short loc_180002675
0x180002672  syscall; Low latency system call
0x180002674  retn
0x180002675  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002677  retn
```
