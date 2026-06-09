# NtModerncoreCreateGDIHwndTarget

- ea: `0x180008000`
- end: `0x180008018`
- name: `NtModerncoreCreateGDIHwndTarget`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008000`

## pseudocode

```c
__int64 NtModerncoreCreateGDIHwndTarget()
{
  __int64 result; // rax

  result = 4971;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008000  mov     r10, rcx
0x180008003  mov     eax, 136Bh
0x180008008  test    byte ptr ds:7FFE0308h, 1
0x180008010  jnz     short loc_180008015
0x180008012  syscall; Low latency system call
0x180008014  retn
0x180008015  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008017  retn
```
