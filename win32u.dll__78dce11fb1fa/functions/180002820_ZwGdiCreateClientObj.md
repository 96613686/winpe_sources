# ZwGdiCreateClientObj

- ea: `0x180002820`
- end: `0x180002838`
- name: `ZwGdiCreateClientObj`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002820`

## pseudocode

```c
__int64 ZwGdiCreateClientObj()
{
  __int64 result; // rax

  result = 4268;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180002820  mov     r10, rcx
0x180002823  mov     eax, 10ACh
0x180002828  test    byte ptr ds:7FFE0308h, 1
0x180002830  jnz     short loc_180002835
0x180002832  syscall; Low latency system call
0x180002834  retn
0x180002835  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180002837  retn
```
