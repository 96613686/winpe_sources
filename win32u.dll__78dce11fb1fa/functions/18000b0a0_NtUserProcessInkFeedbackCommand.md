# NtUserProcessInkFeedbackCommand

- ea: `0x18000b0a0`
- end: `0x18000b0b8`
- name: `NtUserProcessInkFeedbackCommand`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b0a0`

## pseudocode

```c
__int64 NtUserProcessInkFeedbackCommand()
{
  __int64 result; // rax

  result = 5360;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b0a0  mov     r10, rcx
0x18000b0a3  mov     eax, 14F0h
0x18000b0a8  test    byte ptr ds:7FFE0308h, 1
0x18000b0b0  jnz     short loc_18000B0B5
0x18000b0b2  syscall; Low latency system call
0x18000b0b4  retn
0x18000b0b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b0b7  retn
```
