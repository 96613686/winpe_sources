# NtUserSetThreadState

- ea: `0x180002b60`
- end: `0x180002b78`
- name: `NtUserSetThreadState`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b60`

## pseudocode

```c
__int64 NtUserSetThreadState()
{
  __int64 result; // rax

  result = 4294;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002b60  mov     r10, rcx
0x180002b63  mov     eax, 10C6h
0x180002b68  test    byte ptr ds:7FFE0308h, 1
0x180002b70  jnz     short loc_180002B75
0x180002b72  syscall; Low latency system call
0x180002b74  retn
0x180002b75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002b77  retn
```
