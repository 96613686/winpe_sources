# NtUserEnableMouseInPointerForThread

- ea: `0x180009460`
- end: `0x180009478`
- name: `NtUserEnableMouseInPointerForThread`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009460`

## pseudocode

```c
__int64 NtUserEnableMouseInPointerForThread()
{
  __int64 result; // rax

  result = 5134;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009460  mov     r10, rcx
0x180009463  mov     eax, 140Eh
0x180009468  test    byte ptr ds:7FFE0308h, 1
0x180009470  jnz     short loc_180009475
0x180009472  syscall; Low latency system call
0x180009474  retn
0x180009475  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009477  retn
```
