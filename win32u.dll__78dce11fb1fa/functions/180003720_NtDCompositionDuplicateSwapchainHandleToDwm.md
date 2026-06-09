# NtDCompositionDuplicateSwapchainHandleToDwm

- ea: `0x180003720`
- end: `0x180003738`
- name: `NtDCompositionDuplicateSwapchainHandleToDwm`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003720`

## pseudocode

```c
__int64 NtDCompositionDuplicateSwapchainHandleToDwm()
{
  __int64 result; // rax

  result = 4388;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003720  mov     r10, rcx
0x180003723  mov     eax, 1124h
0x180003728  test    byte ptr ds:7FFE0308h, 1
0x180003730  jnz     short loc_180003735
0x180003732  syscall; Low latency system call
0x180003734  retn
0x180003735  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003737  retn
```
