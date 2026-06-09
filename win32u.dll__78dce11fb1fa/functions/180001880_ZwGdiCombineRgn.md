# ZwGdiCombineRgn

- ea: `0x180001880`
- end: `0x180001898`
- name: `ZwGdiCombineRgn`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001880`

## pseudocode

```c
__int64 ZwGdiCombineRgn()
{
  __int64 result; // rax

  result = 4143;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180001880  mov     r10, rcx
0x180001883  mov     eax, 102Fh
0x180001888  test    byte ptr ds:7FFE0308h, 1
0x180001890  jnz     short loc_180001895
0x180001892  syscall; Low latency system call
0x180001894  retn
0x180001895  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180001897  retn
```
