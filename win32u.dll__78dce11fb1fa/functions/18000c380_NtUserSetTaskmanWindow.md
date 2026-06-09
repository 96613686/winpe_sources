# NtUserSetTaskmanWindow

- ea: `0x18000c380`
- end: `0x18000c398`
- name: `NtUserSetTaskmanWindow`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c380`

## pseudocode

```c
__int64 NtUserSetTaskmanWindow()
{
  __int64 result; // rax

  result = 5511;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000c380  mov     r10, rcx
0x18000c383  mov     eax, 1587h
0x18000c388  test    byte ptr ds:7FFE0308h, 1
0x18000c390  jnz     short loc_18000C395
0x18000c392  syscall; Low latency system call
0x18000c394  retn
0x18000c395  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000c397  retn
```
