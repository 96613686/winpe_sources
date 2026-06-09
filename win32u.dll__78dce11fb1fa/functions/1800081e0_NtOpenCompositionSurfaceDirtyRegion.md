# NtOpenCompositionSurfaceDirtyRegion

- ea: `0x1800081e0`
- end: `0x1800081f8`
- name: `NtOpenCompositionSurfaceDirtyRegion`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800081e0`

## pseudocode

```c
__int64 NtOpenCompositionSurfaceDirtyRegion()
{
  __int64 result; // rax

  result = 4986;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800081e0  mov     r10, rcx
0x1800081e3  mov     eax, 137Ah
0x1800081e8  test    byte ptr ds:7FFE0308h, 1
0x1800081f0  jnz     short loc_1800081F5
0x1800081f2  syscall; Low latency system call
0x1800081f4  retn
0x1800081f5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800081f7  retn
```
