# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x140003bf8`
- end: `0x140003c59`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400023b8`
- `0x140003620`
- `0x14000491c`
- `0x140005658`
- `0x140006d7c`

## callees

- `0x1400032f4`
- `0x140003bf8`
- `0x140003c78`

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
0x140003bf8  sub     rsp, 28h
0x140003bfc  mov     r9, rcx
0x140003bff  mov     r8d, edx
0x140003c02  mov     rcx, [rcx]
0x140003c05  cmp     [rcx-10h], edx
0x140003c08  cmovg   r8d, [rcx-10h]
0x140003c0d  cmp     dword ptr [rcx-8], 1
0x140003c11  jle     short loc_140003C22
0x140003c13  mov     edx, r8d
0x140003c16  mov     rcx, r9
0x140003c19  add     rsp, 28h
0x140003c1d  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x140003c22  mov     ecx, [rcx-0Ch]
0x140003c25  cmp     ecx, r8d
0x140003c28  jge     short loc_140003C54
0x140003c2a  cmp     ecx, 40000000h
0x140003c30  jle     short loc_140003C39
0x140003c32  mov     eax, 100000h
0x140003c37  jmp     short loc_140003C40
0x140003c39  mov     eax, ecx
0x140003c3b  cdq
0x140003c3c  sub     eax, edx
0x140003c3e  sar     eax, 1
0x140003c40  add     eax, ecx
0x140003c42  mov     rcx, r9
0x140003c45  cmp     eax, r8d
0x140003c48  cmovge  r8d, eax
0x140003c4c  mov     edx, r8d
0x140003c4f  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x140003c54  add     rsp, 28h
0x140003c58  retn
```
