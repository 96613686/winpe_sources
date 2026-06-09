# ZwGdiBeginPath

- ea: `0x180003140`
- end: `0x180003158`
- name: `ZwGdiBeginPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003140`

## pseudocode

```c
__int64 ZwGdiBeginPath()
{
  __int64 result; // rax

  result = 4341;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003140  mov     r10, rcx
0x180003143  mov     eax, 10F5h
0x180003148  test    byte ptr ds:7FFE0308h, 1
0x180003150  jnz     short loc_180003155
0x180003152  syscall; Low latency system call
0x180003154  retn
0x180003155  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003157  retn
```
