# NtGdiDdDDIMakeResident

- ea: `0x180005540`
- end: `0x180005558`
- name: `NtGdiDdDDIMakeResident`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005540`

## pseudocode

```c
__int64 NtGdiDdDDIMakeResident()
{
  __int64 result; // rax

  result = 4629;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180005540  mov     r10, rcx
0x180005543  mov     eax, 1215h
0x180005548  test    byte ptr ds:7FFE0308h, 1
0x180005550  jnz     short loc_180005555
0x180005552  syscall; Low latency system call
0x180005554  retn
0x180005555  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180005557  retn
```
