# ATL::AtlThrowImpl(long)

- ea: `0x180003b70`
- end: `0x180003b8f`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x180002364`
- `0x180002fd8`
- `0x180005e28`
- `0x1800069d0`
- `0x180006a9c`
- `0x1800075cc`
- `0x1800076a0`
- `0x18000a900`
- `0x18000a970`
- `0x18000a9e0`
- `0x18000aa70`
- `0x18000aae0`
- `0x18000ac00`
- `0x18000ac90`
- `0x18000ad50`
- `0x18000ade0`
- `0x18000ae70`
- `0x18000aee0`
- `0x18000f1e8`
- `0x18000f500`
- `0x18000f68c`
- `0x18000f804`
- `0x18000fe34`
- `0x18000fe68`
- `0x18001008c`
- `0x180010440`
- `0x1800109ec`
- `0x1800111c8`
- `0x180011800`
- `0x180011b0c`
- `0x1800125c4`
- `0x1800128e8`
- `0x180012cac`
- `0x180013070`

## callees

- `0x180009994`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180003B8ELL);
}

```

## disassembly

```asm
0x180003b70  sub     rsp, 28h
0x180003b74  cmp     ecx, 8007000Eh
0x180003b7a  mov     eax, 0C000001Dh
0x180003b7f  mov     edx, 0C0000017h; unsigned int
0x180003b84  cmovz   eax, edx
0x180003b87  mov     ecx, eax; unsigned int
0x180003b89  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
