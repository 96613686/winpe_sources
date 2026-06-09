# NtUserAttachThreadInput

- ea: `0x180002dc0`
- end: `0x180002dd8`
- name: `NtUserAttachThreadInput`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002dc0`

## pseudocode

```c
__int64 NtUserAttachThreadInput()
{
  __int64 result; // rax

  result = 4313;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002dc0  mov     r10, rcx
0x180002dc3  mov     eax, 10D9h
0x180002dc8  test    byte ptr ds:7FFE0308h, 1
0x180002dd0  jnz     short loc_180002DD5
0x180002dd2  syscall; Low latency system call
0x180002dd4  retn
0x180002dd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002dd7  retn
```
