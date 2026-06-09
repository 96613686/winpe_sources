# ZwDCompositionRegisterVirtualDesktopVisual

- ea: `0x180003940`
- end: `0x180003958`
- name: `ZwDCompositionRegisterVirtualDesktopVisual`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003940`

## pseudocode

```c
__int64 ZwDCompositionRegisterVirtualDesktopVisual()
{
  __int64 result; // rax

  result = 4405;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003940  mov     r10, rcx
0x180003943  mov     eax, 1135h
0x180003948  test    byte ptr ds:7FFE0308h, 1
0x180003950  jnz     short loc_180003955
0x180003952  syscall; Low latency system call
0x180003954  retn
0x180003955  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003957  retn
```
