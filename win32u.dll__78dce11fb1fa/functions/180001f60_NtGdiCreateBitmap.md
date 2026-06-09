# NtGdiCreateBitmap

- ea: `0x180001f60`
- end: `0x180001f78`
- name: `NtGdiCreateBitmap`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001f60`

## pseudocode

```c
__int64 NtGdiCreateBitmap()
{
  __int64 result; // rax

  result = 4198;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001f60  mov     r10, rcx
0x180001f63  mov     eax, 1066h
0x180001f68  test    byte ptr ds:7FFE0308h, 1
0x180001f70  jnz     short loc_180001F75
0x180001f72  syscall; Low latency system call
0x180001f74  retn
0x180001f75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001f77  retn
```
