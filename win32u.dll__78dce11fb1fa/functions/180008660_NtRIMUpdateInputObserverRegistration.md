# NtRIMUpdateInputObserverRegistration

- ea: `0x180008660`
- end: `0x180008678`
- name: `NtRIMUpdateInputObserverRegistration`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008660`

## pseudocode

```c
__int64 NtRIMUpdateInputObserverRegistration()
{
  __int64 result; // rax

  result = 5022;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180008660  mov     r10, rcx
0x180008663  mov     eax, 139Eh
0x180008668  test    byte ptr ds:7FFE0308h, 1
0x180008670  jnz     short loc_180008675
0x180008672  syscall; Low latency system call
0x180008674  retn
0x180008675  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180008677  retn
```
