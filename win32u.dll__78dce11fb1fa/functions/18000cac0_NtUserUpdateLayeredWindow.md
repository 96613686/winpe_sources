# NtUserUpdateLayeredWindow

- ea: `0x18000cac0`
- end: `0x18000cad8`
- name: `NtUserUpdateLayeredWindow`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000cac0`

## pseudocode

```c
__int64 NtUserUpdateLayeredWindow()
{
  __int64 result; // rax

  result = 5569;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18000cac0  mov     r10, rcx
0x18000cac3  mov     eax, 15C1h
0x18000cac8  test    byte ptr ds:7FFE0308h, 1
0x18000cad0  jnz     short loc_18000CAD5
0x18000cad2  syscall; Low latency system call
0x18000cad4  retn
0x18000cad5  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18000cad7  retn
```
