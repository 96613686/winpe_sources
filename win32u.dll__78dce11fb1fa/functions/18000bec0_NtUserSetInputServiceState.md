# NtUserSetInputServiceState

- ea: `0x18000bec0`
- end: `0x18000bed8`
- name: `NtUserSetInputServiceState`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bec0`

## pseudocode

```c
__int64 NtUserSetInputServiceState()
{
  __int64 result; // rax

  result = 5473;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000bec0  mov     r10, rcx
0x18000bec3  mov     eax, 1561h
0x18000bec8  test    byte ptr ds:7FFE0308h, 1
0x18000bed0  jnz     short loc_18000BED5
0x18000bed2  syscall; Low latency system call
0x18000bed4  retn
0x18000bed5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000bed7  retn
```
