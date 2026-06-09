# NtCompositorNotifyExitWindows

- ea: `0x180003440`
- end: `0x180003458`
- name: `NtCompositorNotifyExitWindows`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003440`

## pseudocode

```c
__int64 NtCompositorNotifyExitWindows()
{
  __int64 result; // rax

  result = 4365;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003440  mov     r10, rcx
0x180003443  mov     eax, 110Dh
0x180003448  test    byte ptr ds:7FFE0308h, 1
0x180003450  jnz     short loc_180003455
0x180003452  syscall; Low latency system call
0x180003454  retn
0x180003455  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003457  retn
```
