# ZwDCompositionGetFrameSurfaceUpdates

- ea: `0x180003860`
- end: `0x180003878`
- name: `ZwDCompositionGetFrameSurfaceUpdates`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003860`

## pseudocode

```c
__int64 ZwDCompositionGetFrameSurfaceUpdates()
{
  __int64 result; // rax

  result = 4398;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003860  mov     r10, rcx
0x180003863  mov     eax, 112Eh
0x180003868  test    byte ptr ds:7FFE0308h, 1
0x180003870  jnz     short loc_180003875
0x180003872  syscall; Low latency system call
0x180003874  retn
0x180003875  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003877  retn
```
