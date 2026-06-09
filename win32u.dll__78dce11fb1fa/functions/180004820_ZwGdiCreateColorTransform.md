# ZwGdiCreateColorTransform

- ea: `0x180004820`
- end: `0x180004838`
- name: `ZwGdiCreateColorTransform`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004820`

## pseudocode

```c
__int64 ZwGdiCreateColorTransform()
{
  __int64 result; // rax

  result = 4524;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180004820  mov     r10, rcx
0x180004823  mov     eax, 11ACh
0x180004828  test    byte ptr ds:7FFE0308h, 1
0x180004830  jnz     short loc_180004835
0x180004832  syscall; Low latency system call
0x180004834  retn
0x180004835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180004837  retn
```
