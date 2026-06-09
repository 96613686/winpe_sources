# NtGdiEngStrokeAndFillPath

- ea: `0x180006720`
- end: `0x180006738`
- name: `NtGdiEngStrokeAndFillPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006720`

## pseudocode

```c
__int64 NtGdiEngStrokeAndFillPath()
{
  __int64 result; // rax

  result = 4772;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006720  mov     r10, rcx
0x180006723  mov     eax, 12A4h
0x180006728  test    byte ptr ds:7FFE0308h, 1
0x180006730  jnz     short loc_180006735
0x180006732  syscall; Low latency system call
0x180006734  retn
0x180006735  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006737  retn
```
