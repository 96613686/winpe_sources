# NtUserLockWindowUpdate

- ea: `0x1800030e0`
- end: `0x1800030f8`
- name: `NtUserLockWindowUpdate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800030e0`

## pseudocode

```c
__int64 NtUserLockWindowUpdate()
{
  __int64 result; // rax

  result = 4338;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x1800030e0  mov     r10, rcx
0x1800030e3  mov     eax, 10F2h
0x1800030e8  test    byte ptr ds:7FFE0308h, 1
0x1800030f0  jnz     short loc_1800030F5
0x1800030f2  syscall; Low latency system call
0x1800030f4  retn
0x1800030f5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x1800030f7  retn
```
