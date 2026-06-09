# NtUpdateInputSinkTransforms

- ea: `0x180008800`
- end: `0x180008818`
- name: `NtUpdateInputSinkTransforms`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008800`

## pseudocode

```c
__int64 NtUpdateInputSinkTransforms()
{
  __int64 result; // rax

  result = 5035;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008800  mov     r10, rcx
0x180008803  mov     eax, 13ABh
0x180008808  test    byte ptr ds:7FFE0308h, 1
0x180008810  jnz     short loc_180008815
0x180008812  syscall; Low latency system call
0x180008814  retn
0x180008815  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008817  retn
```
