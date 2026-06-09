# NtUnBindCompositionSurface

- ea: `0x1800087e0`
- end: `0x1800087f8`
- name: `NtUnBindCompositionSurface`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800087e0`

## pseudocode

```c
__int64 NtUnBindCompositionSurface()
{
  __int64 result; // rax

  result = 5034;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800087e0  mov     r10, rcx
0x1800087e3  mov     eax, 13AAh
0x1800087e8  test    byte ptr ds:7FFE0308h, 1
0x1800087f0  jnz     short loc_1800087F5
0x1800087f2  syscall; Low latency system call
0x1800087f4  retn
0x1800087f5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800087f7  retn
```
