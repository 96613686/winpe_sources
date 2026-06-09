# NtTokenManagerCreateFlipObjectReturnTokenHandle

- ea: `0x180008760`
- end: `0x180008778`
- name: `NtTokenManagerCreateFlipObjectReturnTokenHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008760`

## pseudocode

```c
__int64 NtTokenManagerCreateFlipObjectReturnTokenHandle()
{
  __int64 result; // rax

  result = 5030;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008760  mov     r10, rcx
0x180008763  mov     eax, 13A6h
0x180008768  test    byte ptr ds:7FFE0308h, 1
0x180008770  jnz     short loc_180008775
0x180008772  syscall; Low latency system call
0x180008774  retn
0x180008775  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008777  retn
```
