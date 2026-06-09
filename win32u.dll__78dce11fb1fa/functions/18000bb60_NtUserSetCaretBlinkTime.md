# NtUserSetCaretBlinkTime

- ea: `0x18000bb60`
- end: `0x18000bb78`
- name: `NtUserSetCaretBlinkTime`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bb60`

## pseudocode

```c
__int64 NtUserSetCaretBlinkTime()
{
  __int64 result; // rax

  result = 5446;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000bb60  mov     r10, rcx
0x18000bb63  mov     eax, 1546h
0x18000bb68  test    byte ptr ds:7FFE0308h, 1
0x18000bb70  jnz     short loc_18000BB75
0x18000bb72  syscall; Low latency system call
0x18000bb74  retn
0x18000bb75  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000bb77  retn
```
