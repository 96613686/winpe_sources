# ZwDCompositionBoostCompositorClock

- ea: `0x180003540`
- end: `0x180003558`
- name: `ZwDCompositionBoostCompositorClock`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003540`

## pseudocode

```c
__int64 ZwDCompositionBoostCompositorClock()
{
  __int64 result; // rax

  result = 4373;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003540  mov     r10, rcx
0x180003543  mov     eax, 1115h
0x180003548  test    byte ptr ds:7FFE0308h, 1
0x180003550  jnz     short loc_180003555
0x180003552  syscall; Low latency system call
0x180003554  retn
0x180003555  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003557  retn
```
