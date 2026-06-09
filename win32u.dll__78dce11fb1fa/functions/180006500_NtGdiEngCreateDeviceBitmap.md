# NtGdiEngCreateDeviceBitmap

- ea: `0x180006500`
- end: `0x180006518`
- name: `NtGdiEngCreateDeviceBitmap`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006500`

## pseudocode

```c
__int64 NtGdiEngCreateDeviceBitmap()
{
  __int64 result; // rax

  result = 4755;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006500  mov     r10, rcx
0x180006503  mov     eax, 1293h
0x180006508  test    byte ptr ds:7FFE0308h, 1
0x180006510  jnz     short loc_180006515
0x180006512  syscall; Low latency system call
0x180006514  retn
0x180006515  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006517  retn
```
