# NtUserGetComboBoxInfo

- ea: `0x180009900`
- end: `0x180009918`
- name: `NtUserGetComboBoxInfo`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009900`

## pseudocode

```c
__int64 NtUserGetComboBoxInfo()
{
  __int64 result; // rax

  result = 5171;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180009900  mov     r10, rcx
0x180009903  mov     eax, 1433h
0x180009908  test    byte ptr ds:7FFE0308h, 1
0x180009910  jnz     short loc_180009915
0x180009912  syscall; Low latency system call
0x180009914  retn
0x180009915  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180009917  retn
```
