# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000ae24`
- end: `0x18000ae86`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003358`
- `0x1800048cc`
- `0x18000897c`

## callees

- `0x18000481c`
- `0x18000ae24`
- `0x18000afcc`

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
0x18000ae24  sub     rsp, 28h
0x18000ae28  mov     r9, rcx
0x18000ae2b  mov     r8d, edx
0x18000ae2e  mov     rcx, [rcx]
0x18000ae31  cmp     [rcx-10h], edx
0x18000ae34  cmovg   r8d, [rcx-10h]
0x18000ae39  cmp     dword ptr [rcx-8], 1
0x18000ae3d  jle     short loc_18000AE4E
0x18000ae3f  mov     edx, r8d
0x18000ae42  mov     rcx, r9
0x18000ae45  add     rsp, 28h
0x18000ae49  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000ae4e  mov     ecx, [rcx-0Ch]
0x18000ae51  cmp     ecx, r8d
0x18000ae54  jge     short loc_18000AE80
0x18000ae56  cmp     ecx, 40000000h
0x18000ae5c  jle     short loc_18000AE65
0x18000ae5e  mov     eax, 100000h
0x18000ae63  jmp     short loc_18000AE6C
0x18000ae65  mov     eax, ecx
0x18000ae67  cdq
0x18000ae68  sub     eax, edx
0x18000ae6a  sar     eax, 1
0x18000ae6c  add     eax, ecx
0x18000ae6e  mov     rcx, r9
0x18000ae71  cmp     eax, r8d
0x18000ae74  cmovge  r8d, eax
0x18000ae78  mov     edx, r8d
0x18000ae7b  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000ae80  add     rsp, 28h
0x18000ae84  retn
```
