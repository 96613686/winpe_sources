# NtGdiCreatePatternBrushInternal

- ea: `0x180002700`
- end: `0x180002718`
- name: `NtGdiCreatePatternBrushInternal`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002700`

## pseudocode

```c
__int64 NtGdiCreatePatternBrushInternal()
{
  __int64 result; // rax

  result = 4259;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002700  mov     r10, rcx
0x180002703  mov     eax, 10A3h
0x180002708  test    byte ptr ds:7FFE0308h, 1
0x180002710  jnz     short loc_180002715
0x180002712  syscall; Low latency system call
0x180002714  retn
0x180002715  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002717  retn
```
