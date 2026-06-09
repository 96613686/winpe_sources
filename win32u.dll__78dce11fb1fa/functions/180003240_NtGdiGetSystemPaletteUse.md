# NtGdiGetSystemPaletteUse

- ea: `0x180003240`
- end: `0x180003258`
- name: `NtGdiGetSystemPaletteUse`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003240`

## pseudocode

```c
__int64 NtGdiGetSystemPaletteUse()
{
  __int64 result; // rax

  result = 4349;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003240  mov     r10, rcx
0x180003243  mov     eax, 10FDh
0x180003248  test    byte ptr ds:7FFE0308h, 1
0x180003250  jnz     short loc_180003255
0x180003252  syscall; Low latency system call
0x180003254  retn
0x180003255  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003257  retn
```
