# NtDCompositionReleaseRemoteTexture

- ea: `0x180003980`
- end: `0x180003998`
- name: `NtDCompositionReleaseRemoteTexture`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003980`

## pseudocode

```c
__int64 NtDCompositionReleaseRemoteTexture()
{
  __int64 result; // rax

  result = 4407;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003980  mov     r10, rcx
0x180003983  mov     eax, 1137h
0x180003988  test    byte ptr ds:7FFE0308h, 1
0x180003990  jnz     short loc_180003995
0x180003992  syscall; Low latency system call
0x180003994  retn
0x180003995  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003997  retn
```
