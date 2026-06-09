# NtGdiGetUFIPathname

- ea: `0x180007080`
- end: `0x180007098`
- name: `NtGdiGetUFIPathname`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007080`

## pseudocode

```c
__int64 NtGdiGetUFIPathname()
{
  __int64 result; // rax

  result = 4847;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007080  mov     r10, rcx
0x180007083  mov     eax, 12EFh
0x180007088  test    byte ptr ds:7FFE0308h, 1
0x180007090  jnz     short loc_180007095
0x180007092  syscall; Low latency system call
0x180007094  retn
0x180007095  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007097  retn
```
