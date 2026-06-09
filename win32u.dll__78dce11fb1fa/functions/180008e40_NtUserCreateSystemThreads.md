# NtUserCreateSystemThreads

- ea: `0x180008e40`
- end: `0x180008e58`
- name: `NtUserCreateSystemThreads`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008e40`

## pseudocode

```c
__int64 NtUserCreateSystemThreads()
{
  __int64 result; // rax

  result = 5085;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008e40  mov     r10, rcx
0x180008e43  mov     eax, 13DDh
0x180008e48  test    byte ptr ds:7FFE0308h, 1
0x180008e50  jnz     short loc_180008E55
0x180008e52  syscall; Low latency system call
0x180008e54  retn
0x180008e55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008e57  retn
```
