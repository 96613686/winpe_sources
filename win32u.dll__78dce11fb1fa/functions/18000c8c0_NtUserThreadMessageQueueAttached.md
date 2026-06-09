# NtUserThreadMessageQueueAttached

- ea: `0x18000c8c0`
- end: `0x18000c8d8`
- name: `NtUserThreadMessageQueueAttached`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c8c0`

## pseudocode

```c
__int64 NtUserThreadMessageQueueAttached()
{
  __int64 result; // rax

  result = 5553;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000c8c0  mov     r10, rcx
0x18000c8c3  mov     eax, 15B1h
0x18000c8c8  test    byte ptr ds:7FFE0308h, 1
0x18000c8d0  jnz     short loc_18000C8D5
0x18000c8d2  syscall; Low latency system call
0x18000c8d4  retn
0x18000c8d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000c8d7  retn
```
