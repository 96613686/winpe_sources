# ATL::AtlCrtErrorCheck(int)

- ea: `0x180003b44`
- end: `0x180003b88`
- name: `?AtlCrtErrorCheck@ATL@@YAHH@Z`
- size: `68`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030dc`
- `0x180003968`
- `0x180004d18`
- `0x1800055a0`

## callees

- `0x180003b44`
- `0x180003ca8`

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
0x180003b44  sub     rsp, 28h
0x180003b48  test    ecx, ecx
0x180003b4a  jz      short loc_180003B81
0x180003b4c  cmp     ecx, 0Ch
0x180003b4f  jz      short loc_180003B76
0x180003b51  cmp     ecx, 16h
0x180003b54  jz      short loc_180003B6B
0x180003b56  cmp     ecx, 22h ; '"'
0x180003b59  jz      short loc_180003B6B
0x180003b5b  cmp     ecx, 50h ; 'P'
0x180003b5e  jz      short loc_180003B81
0x180003b60  mov     ecx, 80004005h; int
0x180003b65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003b6b  mov     ecx, 80070057h; int
0x180003b70  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003b76  mov     ecx, 8007000Eh; int
0x180003b7b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003b81  mov     eax, ecx
0x180003b83  add     rsp, 28h
0x180003b87  retn
```
