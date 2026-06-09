# NtCompositionSetDropTarget

- ea: `0x180003420`
- end: `0x180003438`
- name: `NtCompositionSetDropTarget`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003420`

## pseudocode

```c
__int64 NtCompositionSetDropTarget()
{
  __int64 result; // rax

  result = 4364;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003420  mov     r10, rcx
0x180003423  mov     eax, 110Ch
0x180003428  test    byte ptr ds:7FFE0308h, 1
0x180003430  jnz     short loc_180003435
0x180003432  syscall; Low latency system call
0x180003434  retn
0x180003435  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003437  retn
```
