# ZwGdiAnyLinkedFonts

- ea: `0x180004580`
- end: `0x180004598`
- name: `ZwGdiAnyLinkedFonts`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004580`

## pseudocode

```c
__int64 ZwGdiAnyLinkedFonts()
{
  __int64 result; // rax

  result = 4503;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004580  mov     r10, rcx
0x180004583  mov     eax, 1197h
0x180004588  test    byte ptr ds:7FFE0308h, 1
0x180004590  jnz     short loc_180004595
0x180004592  syscall; Low latency system call
0x180004594  retn
0x180004595  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004597  retn
```
