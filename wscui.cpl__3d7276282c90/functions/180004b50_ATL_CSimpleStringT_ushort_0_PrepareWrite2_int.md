# ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)

- ea: `0x180004b50`
- end: `0x180004bb6`
- name: `?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z`
- size: `102`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180004aa4`
- `0x180004c48`
- `0x180004e9c`
- `0x180005178`
- `0x1800055b0`
- `0x180005658`

## callees

- `0x18000498c`
- `0x180004b50`
- `0x180004bbc`

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
0x180004b50  sub     rsp, 28h
0x180004b54  mov     r9, rcx
0x180004b57  mov     r8d, edx
0x180004b5a  mov     rcx, [rcx]
0x180004b5d  cmp     [rcx-10h], edx
0x180004b60  cmovg   r8d, [rcx-10h]
0x180004b65  cmp     dword ptr [rcx-8], 1
0x180004b69  jle     short loc_180004B7A
0x180004b6b  mov     edx, r8d
0x180004b6e  mov     rcx, r9
0x180004b71  add     rsp, 28h
0x180004b75  jmp     ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180004b7a  mov     ecx, [rcx-0Ch]
0x180004b7d  cmp     ecx, r8d
0x180004b80  jge     short loc_180004BB1
0x180004b82  cmp     ecx, 40000000h
0x180004b88  jle     short loc_180004B91
0x180004b8a  mov     eax, 100000h
0x180004b8f  jmp     short loc_180004B9D
0x180004b91  mov     eax, ecx
0x180004b93  mov     r10d, 2
0x180004b99  cdq
0x180004b9a  idiv    r10d
0x180004b9d  add     eax, ecx
0x180004b9f  mov     rcx, r9
0x180004ba2  cmp     eax, r8d
0x180004ba5  cmovge  r8d, eax
0x180004ba9  mov     edx, r8d
0x180004bac  call    ?Reallocate@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Reallocate(int)
0x180004bb1  add     rsp, 28h
0x180004bb5  retn
```
