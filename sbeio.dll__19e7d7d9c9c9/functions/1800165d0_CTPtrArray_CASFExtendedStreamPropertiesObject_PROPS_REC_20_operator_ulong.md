# CTPtrArray<CASFExtendedStreamPropertiesObject::PROPS_REC,20>::operator[](ulong)

- ea: `0x1800165d0`
- end: `0x180016663`
- name: `??A?$CTPtrArray@UPROPS_REC@CASFExtendedStreamPropertiesObject@@$0BE@@@QEBAPEAUPROPS_REC@CASFExtendedStreamPropertiesObject@@K@Z`
- size: `147`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a860`
- `0x1800130e8`
- `0x180018344`
- `0x180019390`
- `0x18001e5a0`

## callees

- `0x1800165d0`

## pseudocode

```c
__int64 __fastcall CTPtrArray<CASFExtendedStreamPropertiesObject::PROPS_REC,20>::operator[](
        __int64 a1,
        unsigned int a2)
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
          & *((_BYTE *)&CTSparseBlock<unsigned long,CASFExtendedStreamPropertiesObject::PROPS_REC *,20,1>::s_bSingleBitMasks
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
0x1800165d0  mov     [rsp+arg_0], rbx
0x1800165d5  xor     r8d, r8d
0x1800165d8  mov     r10d, edx
0x1800165db  mov     r11, rcx
0x1800165de  cmp     edx, [rcx+0D8h]
0x1800165e4  jnb     short loc_180016642
0x1800165e6  mov     r9, rcx
0x1800165e9  mov     edx, 1
0x1800165ee  test    r9, r9
0x1800165f1  jz      short loc_180016652
0x1800165f3  mov     ecx, [r9+8]
0x1800165f7  cmp     r10d, ecx
0x1800165fa  jb      short loc_180016604
0x1800165fc  lea     eax, [rcx+14h]
0x1800165ff  cmp     r10d, eax
0x180016602  jb      short loc_18001660D
0x180016604  mov     r9, [r9+0C0h]
0x18001660b  jmp     short loc_1800165E9
0x18001660d  sub     r10d, ecx
0x180016610  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUPROPS_REC@CASFExtendedStreamPropertiesObject@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFExtendedStreamPropertiesObject::PROPS_REC *,20,1>::s_bSingleBitMasks
0x180016617  mov     ecx, r10d
0x18001661a  mov     eax, r10d
0x18001661d  shr     rax, 3
0x180016621  and     ecx, 7
0x180016624  mov     al, [rax+r9+18h]
0x180016629  test    [rcx+rbx], al
0x18001662c  jz      short loc_180016652
0x18001662e  mov     r8, [r9+r10*8+20h]
0x180016633  xor     ecx, ecx
0x180016635  xor     eax, eax
0x180016637  test    ecx, ecx
0x180016639  cmovns  rax, r8
0x18001663d  mov     r8, rax
0x180016640  jns     short loc_180016644
0x180016642  xor     edx, edx
0x180016644  mov     rbx, [rsp+arg_0]
0x180016649  neg     edx
0x18001664b  sbb     rax, rax
0x18001664e  and     rax, r8
0x180016651  retn
0x180016652  mov     ecx, 80004005h
0x180016657  test    [r11+0Ch], dl
0x18001665b  jz      short loc_180016635
0x18001665d  mov     r8, [r11+10h]
0x180016661  jmp     short loc_180016644
```
