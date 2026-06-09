# NtUserQueryInformationThread

- ea: `0x18000b140`
- end: `0x18000b158`
- name: `NtUserQueryInformationThread`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b140`

## pseudocode

```c
__int64 NtUserQueryInformationThread()
{
  __int64 result; // rax

  result = 5365;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b140  mov     r10, rcx
0x18000b143  mov     eax, 14F5h
0x18000b148  test    byte ptr ds:7FFE0308h, 1
0x18000b150  jnz     short loc_18000B155
0x18000b152  syscall; Low latency system call
0x18000b154  retn
0x18000b155  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b157  retn
```
