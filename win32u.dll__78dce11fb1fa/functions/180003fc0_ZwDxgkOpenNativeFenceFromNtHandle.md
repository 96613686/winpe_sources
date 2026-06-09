# ZwDxgkOpenNativeFenceFromNtHandle

- ea: `0x180003fc0`
- end: `0x180003fd8`
- name: `ZwDxgkOpenNativeFenceFromNtHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003fc0`

## pseudocode

```c
__int64 ZwDxgkOpenNativeFenceFromNtHandle()
{
  __int64 result; // rax

  result = 4457;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003fc0  mov     r10, rcx
0x180003fc3  mov     eax, 1169h
0x180003fc8  test    byte ptr ds:7FFE0308h, 1
0x180003fd0  jnz     short loc_180003FD5
0x180003fd2  syscall; Low latency system call
0x180003fd4  retn
0x180003fd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003fd7  retn
```
