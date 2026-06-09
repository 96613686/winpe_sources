# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x140004cc8`
- end: `0x140004cd7`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400022cc`
- `0x1400032f4`
- `0x140003c78`

## callees

- `0x140003004`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x140004cc8  sub     rsp, 28h
0x140004ccc  mov     ecx, 8007000Eh; int
0x140004cd1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
