# NtSetCompositionSurfaceBufferUsage

- ea: `0x180008680`
- end: `0x180008698`
- name: `NtSetCompositionSurfaceBufferUsage`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008680`

## pseudocode

```c
__int64 NtSetCompositionSurfaceBufferUsage()
{
  __int64 result; // rax

  result = 5023;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008680  mov     r10, rcx
0x180008683  mov     eax, 139Fh
0x180008688  test    byte ptr ds:7FFE0308h, 1
0x180008690  jnz     short loc_180008695
0x180008692  syscall; Low latency system call
0x180008694  retn
0x180008695  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008697  retn
```
