# SXWriter::putDocumentLocator(ISAXLocator *)

- ea: `0x100408df0`
- end: `0x100408e02`
- name: `?putDocumentLocator@SXWriter@@UEAAJPEAUISAXLocator@@@Z`
- size: `18`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, struct ISAXLocator *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100408df0`

## pseudocode

```c
__int64 __fastcall SXWriter::putDocumentLocator(SXWriter *this, struct ISAXLocator *a2)
{
  if ( !a2 )
    return 2147942487LL;
  *((_QWORD *)this + 9) = a2;
  return 0;
}

```

## disassembly

```asm
0x100408df0  test    rdx, rdx
0x100408df3  jnz     short loc_100408DFB
0x100408df5  mov     eax, 80070057h
0x100408dfa  retn
0x100408dfb  mov     [rcx+48h], rdx
0x100408dff  xor     eax, eax
0x100408e01  retn
```
