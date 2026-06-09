# NtTokenManagerCreateFlipObjectTokenHandle

- ea: `0x180008780`
- end: `0x180008798`
- name: `NtTokenManagerCreateFlipObjectTokenHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008780`

## pseudocode

```c
__int64 NtTokenManagerCreateFlipObjectTokenHandle()
{
  __int64 result; // rax

  result = 5031;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008780  mov     r10, rcx
0x180008783  mov     eax, 13A7h
0x180008788  test    byte ptr ds:7FFE0308h, 1
0x180008790  jnz     short loc_180008795
0x180008792  syscall; Low latency system call
0x180008794  retn
0x180008795  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008797  retn
```
