# ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)

- ea: `0x180004d04`
- end: `0x180004d13`
- name: `?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000498c`
- `0x180004bbc`
- `0x180004dfc`
- `0x180004f20`
- `0x180005220`

## callees

- `0x1800044f8`

## pseudocode

```c
void __noreturn ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException()
{
  ATL::AtlThrowImpl(-2147024882);
}

```

## disassembly

```asm
0x180004d04  sub     rsp, 28h
0x180004d08  mov     ecx, 8007000Eh; int
0x180004d0d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
