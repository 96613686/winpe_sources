# ATL::AtlThrowImpl(long)

- ea: `0x18000335c`
- end: `0x18000337b`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000291c`
- `0x180002c98`
- `0x1800031c0`
- `0x1800031f8`
- `0x180003c7c`
- `0x1800043c0`
- `0x18000459c`
- `0x180007b54`
- `0x180007d28`
- `0x18000824c`

## callees

- `0x180005404`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x18000337ALL);
}

```

## disassembly

```asm
0x18000335c  sub     rsp, 28h
0x180003360  cmp     ecx, 8007000Eh
0x180003366  mov     eax, 0C000001Dh
0x18000336b  mov     edx, 0C0000017h; unsigned int
0x180003370  cmovz   eax, edx
0x180003373  mov     ecx, eax; unsigned int
0x180003375  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
