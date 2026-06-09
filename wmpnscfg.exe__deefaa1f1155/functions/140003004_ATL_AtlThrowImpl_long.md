# ATL::AtlThrowImpl(long)

- ea: `0x140003004`
- end: `0x140003023`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023b8`
- `0x14000259c`
- `0x1400028bc`
- `0x140002e98`
- `0x140002ecc`
- `0x14000326c`
- `0x140003620`
- `0x140003924`
- `0x140003fac`
- `0x140004190`
- `0x14000491c`
- `0x140004cc8`
- `0x140005658`
- `0x140006d7c`
- `0x140006fe8`
- `0x140007224`
- `0x140007258`

## callees

- `0x14000539c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x140003022LL);
}

```

## disassembly

```asm
0x140003004  sub     rsp, 28h
0x140003008  cmp     ecx, 8007000Eh
0x14000300e  mov     eax, 0C000001Dh
0x140003013  mov     edx, 0C0000017h; unsigned int
0x140003018  cmovz   eax, edx
0x14000301b  mov     ecx, eax; unsigned int
0x14000301d  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
