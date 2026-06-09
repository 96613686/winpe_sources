# ZwFlipObjectRemovePoolBuffer

- ea: `0x180004420`
- end: `0x180004438`
- name: `ZwFlipObjectRemovePoolBuffer`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004420`

## pseudocode

```c
__int64 ZwFlipObjectRemovePoolBuffer()
{
  __int64 result; // rax

  result = 4492;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004420  mov     r10, rcx
0x180004423  mov     eax, 118Ch
0x180004428  test    byte ptr ds:7FFE0308h, 1
0x180004430  jnz     short loc_180004435
0x180004432  syscall; Low latency system call
0x180004434  retn
0x180004435  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004437  retn
```
