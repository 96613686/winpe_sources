# NtGdiSetLinkedUFIs

- ea: `0x180007740`
- end: `0x180007758`
- name: `NtGdiSetLinkedUFIs`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007740`

## pseudocode

```c
__int64 NtGdiSetLinkedUFIs()
{
  __int64 result; // rax

  result = 4901;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007740  mov     r10, rcx
0x180007743  mov     eax, 1325h
0x180007748  test    byte ptr ds:7FFE0308h, 1
0x180007750  jnz     short loc_180007755
0x180007752  syscall; Low latency system call
0x180007754  retn
0x180007755  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007757  retn
```
