# NtGdiRemoveFontResourceW

- ea: `0x180007460`
- end: `0x180007478`
- name: `NtGdiRemoveFontResourceW`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007460`

## pseudocode

```c
__int64 NtGdiRemoveFontResourceW()
{
  __int64 result; // rax

  result = 4878;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007460  mov     r10, rcx
0x180007463  mov     eax, 130Eh
0x180007468  test    byte ptr ds:7FFE0308h, 1
0x180007470  jnz     short loc_180007475
0x180007472  syscall; Low latency system call
0x180007474  retn
0x180007475  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007477  retn
```
