# NtDCompositionWaitForChannel

- ea: `0x180003b20`
- end: `0x180003b38`
- name: `NtDCompositionWaitForChannel`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003b20`

## pseudocode

```c
__int64 NtDCompositionWaitForChannel()
{
  __int64 result; // rax

  result = 4420;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003b20  mov     r10, rcx
0x180003b23  mov     eax, 1144h
0x180003b28  test    byte ptr ds:7FFE0308h, 1
0x180003b30  jnz     short loc_180003B35
0x180003b32  syscall; Low latency system call
0x180003b34  retn
0x180003b35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003b37  retn
```
