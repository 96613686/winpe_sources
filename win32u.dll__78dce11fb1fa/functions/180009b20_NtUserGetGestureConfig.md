# NtUserGetGestureConfig

- ea: `0x180009b20`
- end: `0x180009b38`
- name: `NtUserGetGestureConfig`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009b20`

## pseudocode

```c
__int64 NtUserGetGestureConfig()
{
  __int64 result; // rax

  result = 5188;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009b20  mov     r10, rcx
0x180009b23  mov     eax, 1444h
0x180009b28  test    byte ptr ds:7FFE0308h, 1
0x180009b30  jnz     short loc_180009B35
0x180009b32  syscall; Low latency system call
0x180009b34  retn
0x180009b35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009b37  retn
```
