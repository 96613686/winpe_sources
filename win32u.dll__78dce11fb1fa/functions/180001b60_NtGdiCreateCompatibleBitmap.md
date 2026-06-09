# NtGdiCreateCompatibleBitmap

- ea: `0x180001b60`
- end: `0x180001b78`
- name: `NtGdiCreateCompatibleBitmap`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b60`

## pseudocode

```c
__int64 NtGdiCreateCompatibleBitmap()
{
  __int64 result; // rax

  result = 4166;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001b60  mov     r10, rcx
0x180001b63  mov     eax, 1046h
0x180001b68  test    byte ptr ds:7FFE0308h, 1
0x180001b70  jnz     short loc_180001B75
0x180001b72  syscall; Low latency system call
0x180001b74  retn
0x180001b75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001b77  retn
```
