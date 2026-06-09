# NtUserCheckWindowThreadDesktop

- ea: `0x180008b60`
- end: `0x180008b78`
- name: `NtUserCheckWindowThreadDesktop`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008b60`

## pseudocode

```c
__int64 NtUserCheckWindowThreadDesktop()
{
  __int64 result; // rax

  result = 5062;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008b60  mov     r10, rcx
0x180008b63  mov     eax, 13C6h
0x180008b68  test    byte ptr ds:7FFE0308h, 1
0x180008b70  jnz     short loc_180008B75
0x180008b72  syscall; Low latency system call
0x180008b74  retn
0x180008b75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008b77  retn
```
