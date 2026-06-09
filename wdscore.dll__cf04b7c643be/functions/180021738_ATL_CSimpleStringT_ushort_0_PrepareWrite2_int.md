# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180021738`
- end: `0x18002179f`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180021414`
- `0x1800214d8`
- `0x180021b44`

## callees

- `0x180020f80`
- `0x180021738`
- `0x1800217a8`

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
0x180021738  sub     rsp, 28h
0x18002173c  mov     r9, rcx
0x18002173f  mov     r8d, edx
0x180021742  mov     rcx, [rcx]
0x180021745  cmp     [rcx-10h], edx
0x180021748  cmovg   r8d, [rcx-10h]
0x18002174d  cmp     dword ptr [rcx-8], 1
0x180021751  jle     short loc_180021762
0x180021753  mov     edx, r8d
0x180021756  mov     rcx, r9
0x180021759  add     rsp, 28h
0x18002175d  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180021762  mov     ecx, [rcx-0Ch]
0x180021765  cmp     ecx, r8d
0x180021768  jge     short loc_180021799
0x18002176a  cmp     ecx, 40000000h
0x180021770  jle     short loc_180021779
0x180021772  mov     eax, 100000h
0x180021777  jmp     short loc_180021785
0x180021779  mov     eax, ecx
0x18002177b  mov     r10d, 2
0x180021781  cdq
0x180021782  idiv    r10d
0x180021785  add     eax, ecx
0x180021787  mov     rcx, r9
0x18002178a  cmp     eax, r8d
0x18002178d  cmovge  r8d, eax
0x180021791  mov     edx, r8d
0x180021794  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180021799  add     rsp, 28h
0x18002179d  retn
```
