# ZwDCompositionEnableMMCSS

- ea: `0x180003740`
- end: `0x180003758`
- name: `ZwDCompositionEnableMMCSS`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003740`

## pseudocode

```c
__int64 ZwDCompositionEnableMMCSS()
{
  __int64 result; // rax

  result = 4389;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003740  mov     r10, rcx
0x180003743  mov     eax, 1125h
0x180003748  test    byte ptr ds:7FFE0308h, 1
0x180003750  jnz     short loc_180003755
0x180003752  syscall; Low latency system call
0x180003754  retn
0x180003755  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003757  retn
```
