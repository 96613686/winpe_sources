# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180005bb8`
- end: `0x180005c1e`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a88`

## callees

- `0x180004ba0`
- `0x180005bb8`
- `0x1800063b0`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(__int64 *a1, int a2)
{
  int v3; // r8d
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // eax
  int v7; // eax

  v3 = a2;
  v4 = *a1;
  if ( *(_DWORD *)(v4 - 16) > a2 )
    v3 = *(_DWORD *)(v4 - 16);
  if ( *(int *)(v4 - 8) <= 1 )
  {
    v5 = *(_DWORD *)(v4 - 12);
    if ( v5 < v3 )
    {
      if ( v5 <= 0x40000000 )
        v6 = v5 / 2;
      else
        v6 = 0x100000;
      v7 = v5 + v6;
      if ( v7 >= v3 )
        v3 = v7;
      ATL::CSimpleStringT<unsigned short,0>::Reallocate(a1, (unsigned int)v3);
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v3);
  }
}

```

## disassembly

```asm
0x180005bb8  sub     rsp, 28h
0x180005bbc  mov     r9, rcx
0x180005bbf  mov     r8d, edx
0x180005bc2  mov     rcx, [rcx]
0x180005bc5  cmp     [rcx-10h], edx
0x180005bc8  cmovg   r8d, [rcx-10h]
0x180005bcd  cmp     dword ptr [rcx-8], 1
0x180005bd1  jle     short loc_180005BE2
0x180005bd3  mov     edx, r8d
0x180005bd6  mov     rcx, r9
0x180005bd9  add     rsp, 28h
0x180005bdd  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180005be2  mov     ecx, [rcx-0Ch]
0x180005be5  cmp     ecx, r8d
0x180005be8  jge     short loc_180005C19
0x180005bea  cmp     ecx, 40000000h
0x180005bf0  jle     short loc_180005BF9
0x180005bf2  mov     eax, 100000h
0x180005bf7  jmp     short loc_180005C05
0x180005bf9  mov     eax, ecx
0x180005bfb  mov     r10d, 2
0x180005c01  cdq
0x180005c02  idiv    r10d
0x180005c05  add     eax, ecx
0x180005c07  mov     rcx, r9
0x180005c0a  cmp     eax, r8d
0x180005c0d  cmovge  r8d, eax
0x180005c11  mov     edx, r8d
0x180005c14  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180005c19  add     rsp, 28h
0x180005c1d  retn
```
