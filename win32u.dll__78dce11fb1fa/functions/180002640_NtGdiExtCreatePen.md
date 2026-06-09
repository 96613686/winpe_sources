# NtGdiExtCreatePen

- ea: `0x180002640`
- end: `0x180002658`
- name: `NtGdiExtCreatePen`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002640`

## pseudocode

```c
__int64 NtGdiExtCreatePen()
{
  __int64 result; // rax

  result = 4253;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002640  mov     r10, rcx
0x180002643  mov     eax, 109Dh
0x180002648  test    byte ptr ds:7FFE0308h, 1
0x180002650  jnz     short loc_180002655
0x180002652  syscall; Low latency system call
0x180002654  retn
0x180002655  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002657  retn
```
