# NtDCompositionCreateRemoteTexture

- ea: `0x180003660`
- end: `0x180003678`
- name: `NtDCompositionCreateRemoteTexture`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003660`

## pseudocode

```c
__int64 NtDCompositionCreateRemoteTexture()
{
  __int64 result; // rax

  result = 4382;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003660  mov     r10, rcx
0x180003663  mov     eax, 111Eh
0x180003668  test    byte ptr ds:7FFE0308h, 1
0x180003670  jnz     short loc_180003675
0x180003672  syscall; Low latency system call
0x180003674  retn
0x180003675  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003677  retn
```
