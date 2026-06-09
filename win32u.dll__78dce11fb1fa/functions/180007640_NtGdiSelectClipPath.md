# NtGdiSelectClipPath

- ea: `0x180007640`
- end: `0x180007658`
- name: `NtGdiSelectClipPath`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007640`

## pseudocode

```c
__int64 NtGdiSelectClipPath()
{
  __int64 result; // rax

  result = 4893;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180007640  mov     r10, rcx
0x180007643  mov     eax, 131Dh
0x180007648  test    byte ptr ds:7FFE0308h, 1
0x180007650  jnz     short loc_180007655
0x180007652  syscall; Low latency system call
0x180007654  retn
0x180007655  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180007657  retn
```
