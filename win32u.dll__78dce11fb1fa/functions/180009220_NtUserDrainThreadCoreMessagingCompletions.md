# NtUserDrainThreadCoreMessagingCompletions

- ea: `0x180009220`
- end: `0x180009238`
- name: `NtUserDrainThreadCoreMessagingCompletions`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009220`

## pseudocode

```c
__int64 NtUserDrainThreadCoreMessagingCompletions()
{
  __int64 result; // rax

  result = 5116;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009220  mov     r10, rcx
0x180009223  mov     eax, 13FCh
0x180009228  test    byte ptr ds:7FFE0308h, 1
0x180009230  jnz     short loc_180009235
0x180009232  syscall; Low latency system call
0x180009234  retn
0x180009235  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009237  retn
```
