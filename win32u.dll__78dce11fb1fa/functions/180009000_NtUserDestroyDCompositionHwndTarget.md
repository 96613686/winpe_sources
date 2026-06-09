# NtUserDestroyDCompositionHwndTarget

- ea: `0x180009000`
- end: `0x180009018`
- name: `NtUserDestroyDCompositionHwndTarget`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009000`

## pseudocode

```c
__int64 NtUserDestroyDCompositionHwndTarget()
{
  __int64 result; // rax

  result = 5099;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009000  mov     r10, rcx
0x180009003  mov     eax, 13EBh
0x180009008  test    byte ptr ds:7FFE0308h, 1
0x180009010  jnz     short loc_180009015
0x180009012  syscall; Low latency system call
0x180009014  retn
0x180009015  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009017  retn
```
