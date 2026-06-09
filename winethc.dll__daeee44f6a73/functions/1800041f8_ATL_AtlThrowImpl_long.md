# ATL::AtlThrowImpl(long)

- ea: `0x1800041f8`
- end: `0x180004217`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180003358`
- `0x180003814`
- `0x180003b40`
- `0x180004074`
- `0x1800040ac`
- `0x1800048cc`
- `0x18000897c`
- `0x18000ab0c`
- `0x18000b518`
- `0x18000b6fc`
- `0x18000cb40`
- `0x180010ae4`
- `0x180010cb8`
- `0x1800111dc`

## callees

- `0x18000d798`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180004216LL);
}

```

## disassembly

```asm
0x1800041f8  sub     rsp, 28h
0x1800041fc  cmp     ecx, 8007000Eh
0x180004202  mov     eax, 0C000001Dh
0x180004207  mov     edx, 0C0000017h; unsigned int
0x18000420c  cmovz   eax, edx
0x18000420f  mov     ecx, eax; unsigned int
0x180004211  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
