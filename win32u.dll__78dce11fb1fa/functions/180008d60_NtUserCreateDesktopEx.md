# NtUserCreateDesktopEx

- ea: `0x180008d60`
- end: `0x180008d78`
- name: `NtUserCreateDesktopEx`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008d60`

## pseudocode

```c
__int64 NtUserCreateDesktopEx()
{
  __int64 result; // rax

  result = 5078;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008d60  mov     r10, rcx
0x180008d63  mov     eax, 13D6h
0x180008d68  test    byte ptr ds:7FFE0308h, 1
0x180008d70  jnz     short loc_180008D75
0x180008d72  syscall; Low latency system call
0x180008d74  retn
0x180008d75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008d77  retn
```
