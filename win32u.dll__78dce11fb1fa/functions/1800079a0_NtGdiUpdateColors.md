# NtGdiUpdateColors

- ea: `0x1800079a0`
- end: `0x1800079b8`
- name: `NtGdiUpdateColors`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800079a0`

## pseudocode

```c
__int64 NtGdiUpdateColors()
{
  __int64 result; // rax

  result = 4920;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800079a0  mov     r10, rcx
0x1800079a3  mov     eax, 1338h
0x1800079a8  test    byte ptr ds:7FFE0308h, 1
0x1800079b0  jnz     short loc_1800079B5
0x1800079b2  syscall; Low latency system call
0x1800079b4  retn
0x1800079b5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800079b7  retn
```
