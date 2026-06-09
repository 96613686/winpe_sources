# NtGdiEngCreateDeviceSurface

- ea: `0x180006520`
- end: `0x180006538`
- name: `NtGdiEngCreateDeviceSurface`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006520`

## pseudocode

```c
__int64 NtGdiEngCreateDeviceSurface()
{
  __int64 result; // rax

  result = 4756;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006520  mov     r10, rcx
0x180006523  mov     eax, 1294h
0x180006528  test    byte ptr ds:7FFE0308h, 1
0x180006530  jnz     short loc_180006535
0x180006532  syscall; Low latency system call
0x180006534  retn
0x180006535  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006537  retn
```
