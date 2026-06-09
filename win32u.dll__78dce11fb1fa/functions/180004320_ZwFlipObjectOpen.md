# ZwFlipObjectOpen

- ea: `0x180004320`
- end: `0x180004338`
- name: `ZwFlipObjectOpen`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004320`

## pseudocode

```c
__int64 ZwFlipObjectOpen()
{
  __int64 result; // rax

  result = 4484;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004320  mov     r10, rcx
0x180004323  mov     eax, 1184h
0x180004328  test    byte ptr ds:7FFE0308h, 1
0x180004330  jnz     short loc_180004335
0x180004332  syscall; Low latency system call
0x180004334  retn
0x180004335  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004337  retn
```
