# NtDCompositionRegisterThumbnailVisual

- ea: `0x180003920`
- end: `0x180003938`
- name: `NtDCompositionRegisterThumbnailVisual`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003920`

## pseudocode

```c
__int64 NtDCompositionRegisterThumbnailVisual()
{
  __int64 result; // rax

  result = 4404;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x180003920  mov     r10, rcx
0x180003923  mov     eax, 1134h
0x180003928  test    byte ptr ds:7FFE0308h, 1
0x180003930  jnz     short loc_180003935
0x180003932  syscall; Low latency system call
0x180003934  retn
0x180003935  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x180003937  retn
```
