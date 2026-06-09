# ZwDCompositionCreateBufferCollection

- ea: `0x180003600`
- end: `0x180003618`
- name: `ZwDCompositionCreateBufferCollection`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003600`

## pseudocode

```c
__int64 ZwDCompositionCreateBufferCollection()
{
  __int64 result; // rax

  result = 4379;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003600  mov     r10, rcx
0x180003603  mov     eax, 111Bh
0x180003608  test    byte ptr ds:7FFE0308h, 1
0x180003610  jnz     short loc_180003615
0x180003612  syscall; Low latency system call
0x180003614  retn
0x180003615  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003617  retn
```
