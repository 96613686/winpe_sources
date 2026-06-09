# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x1800079ec`
- end: `0x180007a52`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: `void __fastcall(__int64 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800073a8`
- `0x180008b7c`

## callees

- `0x1800064c4`
- `0x1800079ec`
- `0x180008218`

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
0x1800079ec  sub     rsp, 28h
0x1800079f0  mov     r9, rcx
0x1800079f3  mov     r8d, edx
0x1800079f6  mov     rcx, [rcx]
0x1800079f9  cmp     [rcx-10h], edx
0x1800079fc  cmovg   r8d, [rcx-10h]
0x180007a01  cmp     dword ptr [rcx-8], 1
0x180007a05  jle     short loc_180007A16
0x180007a07  mov     edx, r8d
0x180007a0a  mov     rcx, r9
0x180007a0d  add     rsp, 28h
0x180007a11  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180007a16  mov     ecx, [rcx-0Ch]
0x180007a19  cmp     ecx, r8d
0x180007a1c  jge     short loc_180007A4D
0x180007a1e  cmp     ecx, 40000000h
0x180007a24  jle     short loc_180007A2D
0x180007a26  mov     eax, 100000h
0x180007a2b  jmp     short loc_180007A39
0x180007a2d  mov     eax, ecx
0x180007a2f  mov     r10d, 2
0x180007a35  cdq
0x180007a36  idiv    r10d
0x180007a39  add     eax, ecx
0x180007a3b  mov     rcx, r9
0x180007a3e  cmp     eax, r8d
0x180007a41  cmovge  r8d, eax
0x180007a45  mov     edx, r8d
0x180007a48  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180007a4d  add     rsp, 28h
0x180007a51  retn
```
