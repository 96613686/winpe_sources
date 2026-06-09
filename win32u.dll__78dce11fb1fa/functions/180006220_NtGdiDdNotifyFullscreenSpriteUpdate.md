# NtGdiDdNotifyFullscreenSpriteUpdate

- ea: `0x180006220`
- end: `0x180006238`
- name: `NtGdiDdNotifyFullscreenSpriteUpdate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006220`

## pseudocode

```c
__int64 NtGdiDdNotifyFullscreenSpriteUpdate()
{
  __int64 result; // rax

  result = 4732;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180006220  mov     r10, rcx
0x180006223  mov     eax, 127Ch
0x180006228  test    byte ptr ds:7FFE0308h, 1
0x180006230  jnz     short loc_180006235
0x180006232  syscall; Low latency system call
0x180006234  retn
0x180006235  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180006237  retn
```
