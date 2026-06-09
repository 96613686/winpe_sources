# NtUserCheckImeShowStatusInThread

- ea: `0x180008b00`
- end: `0x180008b18`
- name: `NtUserCheckImeShowStatusInThread`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008b00`

## pseudocode

```c
__int64 NtUserCheckImeShowStatusInThread()
{
  __int64 result; // rax

  result = 5059;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008b00  mov     r10, rcx
0x180008b03  mov     eax, 13C3h
0x180008b08  test    byte ptr ds:7FFE0308h, 1
0x180008b10  jnz     short loc_180008B15
0x180008b12  syscall; Low latency system call
0x180008b14  retn
0x180008b15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008b17  retn
```
