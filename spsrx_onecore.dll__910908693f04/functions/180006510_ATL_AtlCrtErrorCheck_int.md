# ATL::AtlCrtErrorCheck(int)

- ea: `0x180006510`
- end: `0x180006554`
- name: `?AtlCrtErrorCheck@ATL@@YAHH@Z`
- size: `68`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b00`
- `0x1800062dc`
- `0x180006598`
- `0x180007120`
- `0x1800078ec`

## callees

- `0x180006510`
- `0x1800068ec`

## pseudocode

```c
__int64 __fastcall ATL::AtlCrtErrorCheck(unsigned int a1)
{
  if ( a1 )
  {
    if ( a1 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( a1 == 22 || a1 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( a1 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  return a1;
}

```

## disassembly

```asm
0x180006510  sub     rsp, 28h
0x180006514  test    ecx, ecx
0x180006516  jz      short loc_18000652C
0x180006518  cmp     ecx, 0Ch
0x18000651b  jz      short loc_180006549
0x18000651d  cmp     ecx, 16h
0x180006520  jz      short loc_18000653E
0x180006522  cmp     ecx, 22h ; '"'
0x180006525  jz      short loc_18000653E
0x180006527  cmp     ecx, 50h ; 'P'
0x18000652a  jnz     short loc_180006533
0x18000652c  mov     eax, ecx
0x18000652e  add     rsp, 28h
0x180006532  retn
0x180006533  mov     ecx, 80004005h; int
0x180006538  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000653e  mov     ecx, 80070057h; int
0x180006543  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006549  mov     ecx, 8007000Eh; int
0x18000654e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
