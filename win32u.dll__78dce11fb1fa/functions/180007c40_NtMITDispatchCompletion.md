# NtMITDispatchCompletion

- ea: `0x180007c40`
- end: `0x180007c58`
- name: `NtMITDispatchCompletion`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007c40`

## pseudocode

```c
__int64 NtMITDispatchCompletion()
{
  __int64 result; // rax

  result = 4941;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007c40  mov     r10, rcx
0x180007c43  mov     eax, 134Dh
0x180007c48  test    byte ptr ds:7FFE0308h, 1
0x180007c50  jnz     short loc_180007C55
0x180007c52  syscall; Low latency system call
0x180007c54  retn
0x180007c55  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007c57  retn
```
