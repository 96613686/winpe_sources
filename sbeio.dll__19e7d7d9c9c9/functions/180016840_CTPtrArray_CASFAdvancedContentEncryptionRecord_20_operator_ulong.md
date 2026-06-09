# CTPtrArray<CASFAdvancedContentEncryptionRecord,20>::operator[](ulong)

- ea: `0x180016840`
- end: `0x1800168d3`
- name: `??A?$CTPtrArray@VCASFAdvancedContentEncryptionRecord@@$0BE@@@QEBAPEAVCASFAdvancedContentEncryptionRecord@@K@Z`
- size: `147`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180015874`
- `0x1800183f0`
- `0x18001da90`
- `0x1800209d0`
- `0x180025d40`

## callees

- `0x180016840`

## pseudocode

```c
__int64 __fastcall CTPtrArray<CASFAdvancedContentEncryptionRecord,20>::operator[](__int64 a1, unsigned int a2)
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
          & *((_BYTE *)&CTSparseBlock<unsigned long,CASFAdvancedContentEncryptionRecord *,20,1>::s_bSingleBitMasks
            + (v8 & 7))) != 0 )
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
0x180016840  mov     [rsp+arg_0], rbx
0x180016845  xor     r8d, r8d
0x180016848  mov     r10d, edx
0x18001684b  mov     r11, rcx
0x18001684e  cmp     edx, [rcx+0D8h]
0x180016854  jnb     short loc_1800168B2
0x180016856  mov     r9, rcx
0x180016859  mov     edx, 1
0x18001685e  test    r9, r9
0x180016861  jz      short loc_1800168C2
0x180016863  mov     ecx, [r9+8]
0x180016867  cmp     r10d, ecx
0x18001686a  jb      short loc_180016874
0x18001686c  lea     eax, [rcx+14h]
0x18001686f  cmp     r10d, eax
0x180016872  jb      short loc_18001687D
0x180016874  mov     r9, [r9+0C0h]
0x18001687b  jmp     short loc_180016859
0x18001687d  sub     r10d, ecx
0x180016880  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAVCASFAdvancedContentEncryptionRecord@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFAdvancedContentEncryptionRecord *,20,1>::s_bSingleBitMasks
0x180016887  mov     ecx, r10d
0x18001688a  mov     eax, r10d
0x18001688d  shr     rax, 3
0x180016891  and     ecx, 7
0x180016894  mov     al, [rax+r9+18h]
0x180016899  test    [rcx+rbx], al
0x18001689c  jz      short loc_1800168C2
0x18001689e  mov     r8, [r9+r10*8+20h]
0x1800168a3  xor     ecx, ecx
0x1800168a5  xor     eax, eax
0x1800168a7  test    ecx, ecx
0x1800168a9  cmovns  rax, r8
0x1800168ad  mov     r8, rax
0x1800168b0  jns     short loc_1800168B4
0x1800168b2  xor     edx, edx
0x1800168b4  mov     rbx, [rsp+arg_0]
0x1800168b9  neg     edx
0x1800168bb  sbb     rax, rax
0x1800168be  and     rax, r8
0x1800168c1  retn
0x1800168c2  mov     ecx, 80004005h
0x1800168c7  test    [r11+0Ch], dl
0x1800168cb  jz      short loc_1800168A5
0x1800168cd  mov     r8, [r11+10h]
0x1800168d1  jmp     short loc_1800168B4
```
