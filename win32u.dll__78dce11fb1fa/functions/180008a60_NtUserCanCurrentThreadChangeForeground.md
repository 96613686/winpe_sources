# NtUserCanCurrentThreadChangeForeground

- ea: `0x180008a60`
- end: `0x180008a78`
- name: `NtUserCanCurrentThreadChangeForeground`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008a60`

## pseudocode

```c
__int64 NtUserCanCurrentThreadChangeForeground()
{
  __int64 result; // rax

  result = 5054;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008a60  mov     r10, rcx
0x180008a63  mov     eax, 13BEh
0x180008a68  test    byte ptr ds:7FFE0308h, 1
0x180008a70  jnz     short loc_180008A75
0x180008a72  syscall; Low latency system call
0x180008a74  retn
0x180008a75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008a77  retn
```
