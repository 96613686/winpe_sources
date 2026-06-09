# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000c228`
- end: `0x18000c289`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006e30`
- `0x180009128`
- `0x180010d8c`
- `0x180011584`

## callees

- `0x180008150`
- `0x18000c228`
- `0x18000c7d0`

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
0x18000c228  sub     rsp, 28h
0x18000c22c  mov     r9, rcx
0x18000c22f  mov     r8d, edx
0x18000c232  mov     rcx, [rcx]
0x18000c235  cmp     [rcx-10h], edx
0x18000c238  cmovg   r8d, [rcx-10h]
0x18000c23d  cmp     dword ptr [rcx-8], 1
0x18000c241  jle     short loc_18000C252
0x18000c243  mov     edx, r8d
0x18000c246  mov     rcx, r9
0x18000c249  add     rsp, 28h
0x18000c24d  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000c252  mov     ecx, [rcx-0Ch]
0x18000c255  cmp     ecx, r8d
0x18000c258  jge     short loc_18000C284
0x18000c25a  cmp     ecx, 40000000h
0x18000c260  jle     short loc_18000C269
0x18000c262  mov     eax, 100000h
0x18000c267  jmp     short loc_18000C270
0x18000c269  mov     eax, ecx
0x18000c26b  cdq
0x18000c26c  sub     eax, edx
0x18000c26e  sar     eax, 1
0x18000c270  add     eax, ecx
0x18000c272  mov     rcx, r9
0x18000c275  cmp     eax, r8d
0x18000c278  cmovge  r8d, eax
0x18000c27c  mov     edx, r8d
0x18000c27f  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000c284  add     rsp, 28h
0x18000c288  retn
```
