# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x18000dd14`
- end: `0x18000dd76`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `98`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ab2c`
- `0x18000b92c`
- `0x18000d040`
- `0x18000e390`
- `0x18001486c`
- `0x180018384`
- `0x180018468`
- `0x180018660`
- `0x180019098`
- `0x18001e14c`
- `0x18001ff88`

## callees

- `0x18000b87c`
- `0x18000dd14`
- `0x18000df1c`

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
0x18000dd14  sub     rsp, 28h
0x18000dd18  mov     r9, rcx
0x18000dd1b  mov     r8d, edx
0x18000dd1e  mov     rcx, [rcx]
0x18000dd21  cmp     [rcx-10h], edx
0x18000dd24  cmovg   r8d, [rcx-10h]
0x18000dd29  cmp     dword ptr [rcx-8], 1
0x18000dd2d  jle     short loc_18000DD3E
0x18000dd2f  mov     edx, r8d
0x18000dd32  mov     rcx, r9
0x18000dd35  add     rsp, 28h
0x18000dd39  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18000dd3e  mov     ecx, [rcx-0Ch]
0x18000dd41  cmp     ecx, r8d
0x18000dd44  jge     short loc_18000DD70
0x18000dd46  cmp     ecx, 40000000h
0x18000dd4c  jle     short loc_18000DD55
0x18000dd4e  mov     eax, 100000h
0x18000dd53  jmp     short loc_18000DD5C
0x18000dd55  mov     eax, ecx
0x18000dd57  cdq
0x18000dd58  sub     eax, edx
0x18000dd5a  sar     eax, 1
0x18000dd5c  add     eax, ecx
0x18000dd5e  mov     rcx, r9
0x18000dd61  cmp     eax, r8d
0x18000dd64  cmovge  r8d, eax
0x18000dd68  mov     edx, r8d
0x18000dd6b  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x18000dd70  add     rsp, 28h
0x18000dd74  retn
```
