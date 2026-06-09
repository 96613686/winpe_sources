# NtUserGetResizeDCompositionSynchronizationObject

- ea: `0x18000a2e0`
- end: `0x18000a2f8`
- name: `NtUserGetResizeDCompositionSynchronizationObject`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a2e0`

## pseudocode

```c
__int64 NtUserGetResizeDCompositionSynchronizationObject()
{
  __int64 result; // rax

  result = 5250;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000a2e0  mov     r10, rcx
0x18000a2e3  mov     eax, 1482h
0x18000a2e8  test    byte ptr ds:7FFE0308h, 1
0x18000a2f0  jnz     short loc_18000A2F5
0x18000a2f2  syscall; Low latency system call
0x18000a2f4  retn
0x18000a2f5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000a2f7  retn
```
