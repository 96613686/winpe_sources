# NtUserLayoutCompleted

- ea: `0x18000ab80`
- end: `0x18000ab98`
- name: `NtUserLayoutCompleted`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ab80`

## pseudocode

```c
__int64 NtUserLayoutCompleted()
{
  __int64 result; // rax

  result = 5319;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000ab80  mov     r10, rcx
0x18000ab83  mov     eax, 14C7h
0x18000ab88  test    byte ptr ds:7FFE0308h, 1
0x18000ab90  jnz     short loc_18000AB95
0x18000ab92  syscall; Low latency system call
0x18000ab94  retn
0x18000ab95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000ab97  retn
```
