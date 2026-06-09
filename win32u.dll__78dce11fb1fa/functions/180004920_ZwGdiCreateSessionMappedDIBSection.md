# ZwGdiCreateSessionMappedDIBSection

- ea: `0x180004920`
- end: `0x180004938`
- name: `ZwGdiCreateSessionMappedDIBSection`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004920`

## pseudocode

```c
__int64 ZwGdiCreateSessionMappedDIBSection()
{
  __int64 result; // rax

  result = 4532;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004920  mov     r10, rcx
0x180004923  mov     eax, 11B4h
0x180004928  test    byte ptr ds:7FFE0308h, 1
0x180004930  jnz     short loc_180004935
0x180004932  syscall; Low latency system call
0x180004934  retn
0x180004935  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004937  retn
```
