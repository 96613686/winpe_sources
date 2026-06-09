# NtUserInitThreadCoreMessagingIocp2

- ea: `0x18000a7c0`
- end: `0x18000a7d8`
- name: `NtUserInitThreadCoreMessagingIocp2`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a7c0`

## pseudocode

```c
__int64 NtUserInitThreadCoreMessagingIocp2()
{
  __int64 result; // rax

  result = 5289;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000a7c0  mov     r10, rcx
0x18000a7c3  mov     eax, 14A9h
0x18000a7c8  test    byte ptr ds:7FFE0308h, 1
0x18000a7d0  jnz     short loc_18000A7D5
0x18000a7d2  syscall; Low latency system call
0x18000a7d4  retn
0x18000a7d5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000a7d7  retn
```
