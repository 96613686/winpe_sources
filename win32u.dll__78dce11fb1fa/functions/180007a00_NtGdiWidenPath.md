# NtGdiWidenPath

- ea: `0x180007a00`
- end: `0x180007a18`
- name: `NtGdiWidenPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007a00`

## pseudocode

```c
__int64 NtGdiWidenPath()
{
  __int64 result; // rax

  result = 4923;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007a00  mov     r10, rcx
0x180007a03  mov     eax, 133Bh
0x180007a08  test    byte ptr ds:7FFE0308h, 1
0x180007a10  jnz     short loc_180007A15
0x180007a12  syscall; Low latency system call
0x180007a14  retn
0x180007a15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007a17  retn
```
