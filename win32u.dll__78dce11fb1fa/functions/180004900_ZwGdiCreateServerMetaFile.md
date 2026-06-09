# ZwGdiCreateServerMetaFile

- ea: `0x180004900`
- end: `0x180004918`
- name: `ZwGdiCreateServerMetaFile`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004900`

## pseudocode

```c
__int64 ZwGdiCreateServerMetaFile()
{
  __int64 result; // rax

  result = 4531;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004900  mov     r10, rcx
0x180004903  mov     eax, 11B3h
0x180004908  test    byte ptr ds:7FFE0308h, 1
0x180004910  jnz     short loc_180004915
0x180004912  syscall; Low latency system call
0x180004914  retn
0x180004915  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004917  retn
```
