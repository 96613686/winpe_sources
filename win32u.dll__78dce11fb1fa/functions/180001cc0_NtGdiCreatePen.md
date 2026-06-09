# NtGdiCreatePen

- ea: `0x180001cc0`
- end: `0x180001cd8`
- name: `NtGdiCreatePen`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001cc0`

## pseudocode

```c
__int64 NtGdiCreatePen()
{
  __int64 result; // rax

  result = 4177;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001cc0  mov     r10, rcx
0x180001cc3  mov     eax, 1051h
0x180001cc8  test    byte ptr ds:7FFE0308h, 1
0x180001cd0  jnz     short loc_180001CD5
0x180001cd2  syscall; Low latency system call
0x180001cd4  retn
0x180001cd5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001cd7  retn
```
