# ZwDCompositionSetChildRootVisual

- ea: `0x180003a40`
- end: `0x180003a58`
- name: `ZwDCompositionSetChildRootVisual`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a40`

## pseudocode

```c
__int64 ZwDCompositionSetChildRootVisual()
{
  __int64 result; // rax

  result = 4413;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003a40  mov     r10, rcx
0x180003a43  mov     eax, 113Dh
0x180003a48  test    byte ptr ds:7FFE0308h, 1
0x180003a50  jnz     short loc_180003A55
0x180003a52  syscall; Low latency system call
0x180003a54  retn
0x180003a55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003a57  retn
```
