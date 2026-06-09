# NtGdiCreateRectRgn

- ea: `0x180002220`
- end: `0x180002238`
- name: `NtGdiCreateRectRgn`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002220`

## pseudocode

```c
__int64 NtGdiCreateRectRgn()
{
  __int64 result; // rax

  result = 4220;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002220  mov     r10, rcx
0x180002223  mov     eax, 107Ch
0x180002228  test    byte ptr ds:7FFE0308h, 1
0x180002230  jnz     short loc_180002235
0x180002232  syscall; Low latency system call
0x180002234  retn
0x180002235  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002237  retn
```
