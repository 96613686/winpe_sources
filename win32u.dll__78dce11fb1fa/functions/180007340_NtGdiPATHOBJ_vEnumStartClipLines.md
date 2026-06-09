# NtGdiPATHOBJ_vEnumStartClipLines

- ea: `0x180007340`
- end: `0x180007358`
- name: `NtGdiPATHOBJ_vEnumStartClipLines`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007340`

## pseudocode

```c
__int64 NtGdiPATHOBJ_vEnumStartClipLines()
{
  __int64 result; // rax

  result = 4869;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007340  mov     r10, rcx
0x180007343  mov     eax, 1305h
0x180007348  test    byte ptr ds:7FFE0308h, 1
0x180007350  jnz     short loc_180007355
0x180007352  syscall; Low latency system call
0x180007354  retn
0x180007355  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007357  retn
```
