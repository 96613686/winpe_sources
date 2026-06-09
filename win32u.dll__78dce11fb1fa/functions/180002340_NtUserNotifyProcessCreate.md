# NtUserNotifyProcessCreate

- ea: `0x180002340`
- end: `0x180002358`
- name: `NtUserNotifyProcessCreate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002340`

## pseudocode

```c
__int64 NtUserNotifyProcessCreate()
{
  __int64 result; // rax

  result = 4229;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002340  mov     r10, rcx
0x180002343  mov     eax, 1085h
0x180002348  test    byte ptr ds:7FFE0308h, 1
0x180002350  jnz     short loc_180002355
0x180002352  syscall; Low latency system call
0x180002354  retn
0x180002355  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002357  retn
```
