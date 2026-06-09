# ATL::AtlThrowImpl(long)

- ea: `0x140003298`
- end: `0x1400032b7`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140002424`
- `0x140002928`
- `0x140002a54`
- `0x140002bfc`
- `0x1400030b8`
- `0x140003a88`
- `0x140003f2c`
- `0x140004698`
- `0x140004954`
- `0x140005bb4`

## callees

- `0x140005b9c`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  DWORD v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1);
  JUMPOUT(0x1400032B6LL);
}

```

## disassembly

```asm
0x140003298  sub     rsp, 28h
0x14000329c  cmp     ecx, 8007000Eh
0x1400032a2  mov     eax, 0C000001Dh
0x1400032a7  mov     edx, 0C0000017h; unsigned int
0x1400032ac  cmovz   eax, edx
0x1400032af  mov     ecx, eax; unsigned int
0x1400032b1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
