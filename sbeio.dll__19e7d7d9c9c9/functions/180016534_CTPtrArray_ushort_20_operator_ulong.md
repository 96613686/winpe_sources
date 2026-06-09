# CTPtrArray<ushort,20>::operator[](ulong)

- ea: `0x180016534`
- end: `0x1800165c7`
- name: `??A?$CTPtrArray@G$0BE@@@QEBAPEAGK@Z`
- size: `147`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800182d4`
- `0x18001a640`
- `0x18001ae50`
- `0x18001c560`
- `0x18001f400`
- `0x180026420`

## callees

- `0x180016534`

## pseudocode

```c
__int64 __fastcall CTPtrArray<unsigned short,20>::operator[](__int64 a1, unsigned int a2)
{
  __int64 v2; // r8
  __int64 i; // r9
  int v6; // edx
  unsigned int v7; // ecx
  __int64 v8; // r10
  int v9; // ecx
  __int64 v10; // rax

  v2 = 0;
  if ( a2 >= *(_DWORD *)(a1 + 216) )
    goto LABEL_12;
  for ( i = a1; ; i = *(_QWORD *)(i + 192) )
  {
    v6 = 1;
    if ( !i )
      break;
    v7 = *(_DWORD *)(i + 8);
    if ( a2 >= v7 && a2 < v7 + 20 )
    {
      v8 = a2 - v7;
      if ( (*(_BYTE *)(((unsigned __int64)(unsigned int)v8 >> 3) + i + 24)
          & *((_BYTE *)&CTSparseBlock<unsigned long,unsigned short *,20,1>::s_bSingleBitMasks + (v8 & 7))) != 0 )
      {
        v2 = *(_QWORD *)(i + 8 * v8 + 32);
        v9 = 0;
        goto LABEL_9;
      }
      break;
    }
  }
  v9 = -2147467259;
  if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 16);
    return v2 & -(__int64)(v6 != 0);
  }
LABEL_9:
  v10 = 0;
  if ( v9 >= 0 )
    v10 = v2;
  v2 = v10;
  if ( v9 < 0 )
LABEL_12:
    v6 = 0;
  return v2 & -(__int64)(v6 != 0);
}

```

## disassembly

```asm
0x180016534  mov     [rsp+arg_0], rbx
0x180016539  xor     r8d, r8d
0x18001653c  mov     r10d, edx
0x18001653f  mov     r11, rcx
0x180016542  cmp     edx, [rcx+0D8h]
0x180016548  jnb     short loc_1800165A6
0x18001654a  mov     r9, rcx
0x18001654d  mov     edx, 1
0x180016552  test    r9, r9
0x180016555  jz      short loc_1800165B6
0x180016557  mov     ecx, [r9+8]
0x18001655b  cmp     r10d, ecx
0x18001655e  jb      short loc_180016568
0x180016560  lea     eax, [rcx+14h]
0x180016563  cmp     r10d, eax
0x180016566  jb      short loc_180016571
0x180016568  mov     r9, [r9+0C0h]
0x18001656f  jmp     short loc_18001654D
0x180016571  sub     r10d, ecx
0x180016574  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAG$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,ushort *,20,1>::s_bSingleBitMasks
0x18001657b  mov     ecx, r10d
0x18001657e  mov     eax, r10d
0x180016581  shr     rax, 3
0x180016585  and     ecx, 7
0x180016588  mov     al, [rax+r9+18h]
0x18001658d  test    [rcx+rbx], al
0x180016590  jz      short loc_1800165B6
0x180016592  mov     r8, [r9+r10*8+20h]
0x180016597  xor     ecx, ecx
0x180016599  xor     eax, eax
0x18001659b  test    ecx, ecx
0x18001659d  cmovns  rax, r8
0x1800165a1  mov     r8, rax
0x1800165a4  jns     short loc_1800165A8
0x1800165a6  xor     edx, edx
0x1800165a8  mov     rbx, [rsp+arg_0]
0x1800165ad  neg     edx
0x1800165af  sbb     rax, rax
0x1800165b2  and     rax, r8
0x1800165b5  retn
0x1800165b6  mov     ecx, 80004005h
0x1800165bb  test    [r11+0Ch], dl
0x1800165bf  jz      short loc_180016599
0x1800165c1  mov     r8, [r11+10h]
0x1800165c5  jmp     short loc_1800165A8
```
