# NtDxgkVailPromoteCompositionSurface

- ea: `0x180004180`
- end: `0x180004198`
- name: `NtDxgkVailPromoteCompositionSurface`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004180`

## pseudocode

```c
__int64 NtDxgkVailPromoteCompositionSurface()
{
  __int64 result; // rax

  result = 4471;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004180  mov     r10, rcx
0x180004183  mov     eax, 1177h
0x180004188  test    byte ptr ds:7FFE0308h, 1
0x180004190  jnz     short loc_180004195
0x180004192  syscall; Low latency system call
0x180004194  retn
0x180004195  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004197  retn
```
