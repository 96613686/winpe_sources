# NtMITCoreMsgKOpenConnectionTo

- ea: `0x180007be0`
- end: `0x180007bf8`
- name: `NtMITCoreMsgKOpenConnectionTo`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007be0`

## pseudocode

```c
__int64 NtMITCoreMsgKOpenConnectionTo()
{
  __int64 result; // rax

  result = 4938;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007be0  mov     r10, rcx
0x180007be3  mov     eax, 134Ah
0x180007be8  test    byte ptr ds:7FFE0308h, 1
0x180007bf0  jnz     short loc_180007BF5
0x180007bf2  syscall; Low latency system call
0x180007bf4  retn
0x180007bf5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007bf7  retn
```
