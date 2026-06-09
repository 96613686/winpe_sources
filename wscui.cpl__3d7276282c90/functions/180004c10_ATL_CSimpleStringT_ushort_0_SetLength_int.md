# ATL::CSimpleStringT<ushort,0>::SetLength(int)

- ea: `0x180004c10`
- end: `0x180004c3f`
- name: `?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `47`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180004930`
- `0x180004aa4`
- `0x180004c48`
- `0x180004dfc`
- `0x180004e9c`
- `0x180005178`
- `0x1800055b0`
- `0x180005658`

## callees

- `0x1800044f8`
- `0x180004c10`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetLength(_QWORD *a1, int a2)
{
  __int64 result; // rax

  if ( a2 < 0 || a2 > *(_DWORD *)(*a1 - 12LL) )
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16LL) = a2;
  result = 0;
  *(_WORD *)(*a1 + 2LL * a2) = 0;
  return result;
}

```

## disassembly

```asm
0x180004c10  sub     rsp, 28h
0x180004c14  test    edx, edx
0x180004c16  js      short loc_180004C34
0x180004c18  mov     rax, [rcx]
0x180004c1b  cmp     edx, [rax-0Ch]
0x180004c1e  jg      short loc_180004C34
0x180004c20  mov     [rax-10h], edx
0x180004c23  xor     eax, eax
0x180004c25  mov     rcx, [rcx]
0x180004c28  movsxd  rdx, edx
0x180004c2b  mov     [rcx+rdx*2], ax
0x180004c2f  add     rsp, 28h
0x180004c33  retn
0x180004c34  mov     ecx, 80070057h; int
0x180004c39  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
