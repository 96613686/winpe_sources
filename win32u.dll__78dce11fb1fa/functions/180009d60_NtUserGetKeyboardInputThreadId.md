# NtUserGetKeyboardInputThreadId

- ea: `0x180009d60`
- end: `0x180009d78`
- name: `NtUserGetKeyboardInputThreadId`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009d60`

## pseudocode

```c
__int64 NtUserGetKeyboardInputThreadId()
{
  __int64 result; // rax

  result = 5206;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009d60  mov     r10, rcx
0x180009d63  mov     eax, 1456h
0x180009d68  test    byte ptr ds:7FFE0308h, 1
0x180009d70  jnz     short loc_180009D75
0x180009d72  syscall; Low latency system call
0x180009d74  retn
0x180009d75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009d77  retn
```
