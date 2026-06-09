# ZwDCompositionReleaseAllResources

- ea: `0x180003960`
- end: `0x180003978`
- name: `ZwDCompositionReleaseAllResources`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003960`

## pseudocode

```c
__int64 ZwDCompositionReleaseAllResources()
{
  __int64 result; // rax

  result = 4406;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003960  mov     r10, rcx
0x180003963  mov     eax, 1136h
0x180003968  test    byte ptr ds:7FFE0308h, 1
0x180003970  jnz     short loc_180003975
0x180003972  syscall; Low latency system call
0x180003974  retn
0x180003975  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003977  retn
```
