# ZwFlipObjectRemoveContent

- ea: `0x180004400`
- end: `0x180004418`
- name: `ZwFlipObjectRemoveContent`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004400`

## pseudocode

```c
__int64 ZwFlipObjectRemoveContent()
{
  __int64 result; // rax

  result = 4491;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004400  mov     r10, rcx
0x180004403  mov     eax, 118Bh
0x180004408  test    byte ptr ds:7FFE0308h, 1
0x180004410  jnz     short loc_180004415
0x180004412  syscall; Low latency system call
0x180004414  retn
0x180004415  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004417  retn
```
