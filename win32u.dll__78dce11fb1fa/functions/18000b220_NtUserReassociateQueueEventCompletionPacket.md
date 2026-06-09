# NtUserReassociateQueueEventCompletionPacket

- ea: `0x18000b220`
- end: `0x18000b238`
- name: `NtUserReassociateQueueEventCompletionPacket`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b220`

## pseudocode

```c
__int64 NtUserReassociateQueueEventCompletionPacket()
{
  __int64 result; // rax

  result = 5372;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b220  mov     r10, rcx
0x18000b223  mov     eax, 14FCh
0x18000b228  test    byte ptr ds:7FFE0308h, 1
0x18000b230  jnz     short loc_18000B235
0x18000b232  syscall; Low latency system call
0x18000b234  retn
0x18000b235  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b237  retn
```
