# NtGdiEndPath

- ea: `0x180003160`
- end: `0x180003178`
- name: `NtGdiEndPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003160`

## pseudocode

```c
__int64 NtGdiEndPath()
{
  __int64 result; // rax

  result = 4342;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003160  mov     r10, rcx
0x180003163  mov     eax, 10F6h
0x180003168  test    byte ptr ds:7FFE0308h, 1
0x180003170  jnz     short loc_180003175
0x180003172  syscall; Low latency system call
0x180003174  retn
0x180003175  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003177  retn
```
