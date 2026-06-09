# NtGdiSetSystemPaletteUse

- ea: `0x180007820`
- end: `0x180007838`
- name: `NtGdiSetSystemPaletteUse`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007820`

## pseudocode

```c
__int64 NtGdiSetSystemPaletteUse()
{
  __int64 result; // rax

  result = 4908;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007820  mov     r10, rcx
0x180007823  mov     eax, 132Ch
0x180007828  test    byte ptr ds:7FFE0308h, 1
0x180007830  jnz     short loc_180007835
0x180007832  syscall; Low latency system call
0x180007834  retn
0x180007835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007837  retn
```
