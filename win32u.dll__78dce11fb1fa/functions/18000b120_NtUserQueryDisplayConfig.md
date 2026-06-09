# NtUserQueryDisplayConfig

- ea: `0x18000b120`
- end: `0x18000b138`
- name: `NtUserQueryDisplayConfig`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b120`

## pseudocode

```c
__int64 NtUserQueryDisplayConfig()
{
  __int64 result; // rax

  result = 5364;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000b120  mov     r10, rcx
0x18000b123  mov     eax, 14F4h
0x18000b128  test    byte ptr ds:7FFE0308h, 1
0x18000b130  jnz     short loc_18000B135
0x18000b132  syscall; Low latency system call
0x18000b134  retn
0x18000b135  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000b137  retn
```
