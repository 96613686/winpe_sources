# NtGdiCreateBitmapFromDxSurface2

- ea: `0x180004800`
- end: `0x180004818`
- name: `NtGdiCreateBitmapFromDxSurface2`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004800`

## pseudocode

```c
__int64 NtGdiCreateBitmapFromDxSurface2()
{
  __int64 result; // rax

  result = 4523;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004800  mov     r10, rcx
0x180004803  mov     eax, 11ABh
0x180004808  test    byte ptr ds:7FFE0308h, 1
0x180004810  jnz     short loc_180004815
0x180004812  syscall; Low latency system call
0x180004814  retn
0x180004815  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004817  retn
```
