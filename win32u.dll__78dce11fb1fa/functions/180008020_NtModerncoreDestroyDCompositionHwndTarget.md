# NtModerncoreDestroyDCompositionHwndTarget

- ea: `0x180008020`
- end: `0x180008038`
- name: `NtModerncoreDestroyDCompositionHwndTarget`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008020`

## pseudocode

```c
__int64 NtModerncoreDestroyDCompositionHwndTarget()
{
  __int64 result; // rax

  result = 4972;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008020  mov     r10, rcx
0x180008023  mov     eax, 136Ch
0x180008028  test    byte ptr ds:7FFE0308h, 1
0x180008030  jnz     short loc_180008035
0x180008032  syscall; Low latency system call
0x180008034  retn
0x180008035  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008037  retn
```
