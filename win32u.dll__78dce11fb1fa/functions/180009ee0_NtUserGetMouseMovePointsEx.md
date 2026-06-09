# NtUserGetMouseMovePointsEx

- ea: `0x180009ee0`
- end: `0x180009ef8`
- name: `NtUserGetMouseMovePointsEx`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009ee0`

## pseudocode

```c
__int64 NtUserGetMouseMovePointsEx()
{
  __int64 result; // rax

  result = 5218;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009ee0  mov     r10, rcx
0x180009ee3  mov     eax, 1462h
0x180009ee8  test    byte ptr ds:7FFE0308h, 1
0x180009ef0  jnz     short loc_180009EF5
0x180009ef2  syscall; Low latency system call
0x180009ef4  retn
0x180009ef5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009ef7  retn
```
