# NtUserCreateMenu

- ea: `0x180008dc0`
- end: `0x180008dd8`
- name: `NtUserCreateMenu`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008dc0`

## pseudocode

```c
__int64 NtUserCreateMenu()
{
  __int64 result; // rax

  result = 5081;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008dc0  mov     r10, rcx
0x180008dc3  mov     eax, 13D9h
0x180008dc8  test    byte ptr ds:7FFE0308h, 1
0x180008dd0  jnz     short loc_180008DD5
0x180008dd2  syscall; Low latency system call
0x180008dd4  retn
0x180008dd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008dd7  retn
```
