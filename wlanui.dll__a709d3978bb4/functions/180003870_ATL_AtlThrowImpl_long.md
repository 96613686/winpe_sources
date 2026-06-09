# ATL::AtlThrowImpl(long)

- ea: `0x180003870`
- end: `0x18000388f`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dc8`
- `0x1800030f4`
- `0x1800035f8`
- `0x18000362c`
- `0x18000418c`
- `0x180004828`
- `0x1800049ec`
- `0x180006e30`
- `0x180009128`
- `0x18000d6fc`
- `0x18000fa44`
- `0x180010d8c`
- `0x180011308`
- `0x180011584`

## callees

- `0x180005b7c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x18000388ELL);
}

```

## disassembly

```asm
0x180003870  sub     rsp, 28h
0x180003874  cmp     ecx, 8007000Eh
0x18000387a  mov     eax, 0C000001Dh
0x18000387f  mov     edx, 0C0000017h; unsigned int
0x180003884  cmovz   eax, edx
0x180003887  mov     ecx, eax; unsigned int
0x180003889  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
