# ATL::AtlThrowImpl(long)

- ea: `0x180014564`
- end: `0x180014583`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800146e8`
- `0x180014774`
- `0x180014878`
- `0x180014a14`
- `0x180014cdc`
- `0x180014eac`
- `0x1800153e8`
- `0x1800154d4`
- `0x1800159f8`
- `0x180015cdc`
- `0x180015d70`

## callees

- `0x1800152cc`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180014582LL);
}

```

## disassembly

```asm
0x180014564  sub     rsp, 28h
0x180014568  cmp     ecx, 8007000Eh
0x18001456e  mov     eax, 0C000001Dh
0x180014573  mov     edx, 0C0000017h; unsigned int
0x180014578  cmovz   eax, edx
0x18001457b  mov     ecx, eax; unsigned int
0x18001457d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
