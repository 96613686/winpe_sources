# NtUserSetFullscreenMagnifierOffsetsDWMUpdated

- ea: `0x18000be20`
- end: `0x18000be38`
- name: `NtUserSetFullscreenMagnifierOffsetsDWMUpdated`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000be20`

## pseudocode

```c
__int64 NtUserSetFullscreenMagnifierOffsetsDWMUpdated()
{
  __int64 result; // rax

  result = 5468;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000be20  mov     r10, rcx
0x18000be23  mov     eax, 155Ch
0x18000be28  test    byte ptr ds:7FFE0308h, 1
0x18000be30  jnz     short loc_18000BE35
0x18000be32  syscall; Low latency system call
0x18000be34  retn
0x18000be35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000be37  retn
```
