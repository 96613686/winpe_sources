# ZwGdiCreateCompatibleDC

- ea: `0x180001c80`
- end: `0x180001c98`
- name: `ZwGdiCreateCompatibleDC`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c80`

## pseudocode

```c
__int64 ZwGdiCreateCompatibleDC()
{
  __int64 result; // rax

  result = 4175;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001c80  mov     r10, rcx
0x180001c83  mov     eax, 104Fh
0x180001c88  test    byte ptr ds:7FFE0308h, 1
0x180001c90  jnz     short loc_180001C95
0x180001c92  syscall; Low latency system call
0x180001c94  retn
0x180001c95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001c97  retn
```
