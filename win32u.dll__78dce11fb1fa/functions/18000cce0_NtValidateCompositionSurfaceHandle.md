# NtValidateCompositionSurfaceHandle

- ea: `0x18000cce0`
- end: `0x18000ccf8`
- name: `NtValidateCompositionSurfaceHandle`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cce0`

## pseudocode

```c
__int64 NtValidateCompositionSurfaceHandle()
{
  __int64 result; // rax

  result = 5586;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000cce0  mov     r10, rcx
0x18000cce3  mov     eax, 15D2h
0x18000cce8  test    byte ptr ds:7FFE0308h, 1
0x18000ccf0  jnz     short loc_18000CCF5
0x18000ccf2  syscall; Low latency system call
0x18000ccf4  retn
0x18000ccf5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000ccf7  retn
```
