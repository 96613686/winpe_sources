# NtUserCompositionInputSinkViewInstanceIdFromPoint

- ea: `0x180008c60`
- end: `0x180008c78`
- name: `NtUserCompositionInputSinkViewInstanceIdFromPoint`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008c60`

## pseudocode

```c
__int64 NtUserCompositionInputSinkViewInstanceIdFromPoint()
{
  __int64 result; // rax

  result = 5070;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008c60  mov     r10, rcx
0x180008c63  mov     eax, 13CEh
0x180008c68  test    byte ptr ds:7FFE0308h, 1
0x180008c70  jnz     short loc_180008C75
0x180008c72  syscall; Low latency system call
0x180008c74  retn
0x180008c75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008c77  retn
```
