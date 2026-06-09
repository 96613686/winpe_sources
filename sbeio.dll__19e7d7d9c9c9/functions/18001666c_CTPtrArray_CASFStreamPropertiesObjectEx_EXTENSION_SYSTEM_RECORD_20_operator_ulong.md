# CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::operator[](ulong)

- ea: `0x18001666c`
- end: `0x1800166ff`
- name: `??A?$CTPtrArray@U_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@QEBAPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@K@Z`
- size: `147`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009bc0`
- `0x180017588`
- `0x180018074`
- `0x18001a4e0`
- `0x18001f0c0`
- `0x1800262e0`

## callees

- `0x18001666c`

## pseudocode

```c
__int64 __fastcall CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::operator[](
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
          & (unsigned __int8)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks[v8 & 7]) != 0 )
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
0x18001666c  mov     [rsp+arg_0], rbx
0x180016671  xor     r8d, r8d
0x180016674  mov     r10d, edx
0x180016677  mov     r11, rcx
0x18001667a  cmp     edx, [rcx+0D8h]
0x180016680  jnb     short loc_1800166DE
0x180016682  mov     r9, rcx
0x180016685  mov     edx, 1
0x18001668a  test    r9, r9
0x18001668d  jz      short loc_1800166EE
0x18001668f  mov     ecx, [r9+8]
0x180016693  cmp     r10d, ecx
0x180016696  jb      short loc_1800166A0
0x180016698  lea     eax, [rcx+14h]
0x18001669b  cmp     r10d, eax
0x18001669e  jb      short loc_1800166A9
0x1800166a0  mov     r9, [r9+0C0h]
0x1800166a7  jmp     short loc_180016685
0x1800166a9  sub     r10d, ecx
0x1800166ac  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks
0x1800166b3  mov     ecx, r10d
0x1800166b6  mov     eax, r10d
0x1800166b9  shr     rax, 3
0x1800166bd  and     ecx, 7
0x1800166c0  mov     al, [rax+r9+18h]
0x1800166c5  test    [rcx+rbx], al
0x1800166c8  jz      short loc_1800166EE
0x1800166ca  mov     r8, [r9+r10*8+20h]
0x1800166cf  xor     ecx, ecx
0x1800166d1  xor     eax, eax
0x1800166d3  test    ecx, ecx
0x1800166d5  cmovns  rax, r8
0x1800166d9  mov     r8, rax
0x1800166dc  jns     short loc_1800166E0
0x1800166de  xor     edx, edx
0x1800166e0  mov     rbx, [rsp+arg_0]
0x1800166e5  neg     edx
0x1800166e7  sbb     rax, rax
0x1800166ea  and     rax, r8
0x1800166ed  retn
0x1800166ee  mov     ecx, 80004005h
0x1800166f3  test    [r11+0Ch], dl
0x1800166f7  jz      short loc_1800166D1
0x1800166f9  mov     r8, [r11+10h]
0x1800166fd  jmp     short loc_1800166E0
```
