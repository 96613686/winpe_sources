# CTPtrArray<uchar,20>::operator[](ulong)

- ea: `0x180007e38`
- end: `0x180007ecb`
- name: `??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z`
- size: `147`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bd8`
- `0x1800088e0`
- `0x180008f10`
- `0x180009060`
- `0x180009f64`
- `0x18000a860`
- `0x18000ae90`
- `0x18000bd30`
- `0x18000d67c`
- `0x18000dbb0`
- `0x18000dfe0`
- `0x18000e5c0`
- `0x18000e7c0`
- `0x18000e8e0`
- `0x18000ea20`
- `0x18000ebd0`
- `0x18000ed10`
- `0x18000fe30`
- `0x18000ff40`
- `0x180010060`
- `0x180010ef0`
- `0x1800117c0`
- `0x18001184c`
- `0x1800118f8`

## callees

- `0x180007e38`

## pseudocode

```c
__int64 __fastcall CTPtrArray<unsigned char,20>::operator[](__int64 a1, unsigned int a2)
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
          & *((_BYTE *)&CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks + (v8 & 7))) != 0 )
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
0x180007e38  mov     [rsp+arg_0], rbx
0x180007e3d  xor     r8d, r8d
0x180007e40  mov     r10d, edx
0x180007e43  mov     r11, rcx
0x180007e46  cmp     edx, [rcx+0D8h]
0x180007e4c  jnb     short loc_180007EAA
0x180007e4e  mov     r9, rcx
0x180007e51  mov     edx, 1
0x180007e56  test    r9, r9
0x180007e59  jz      short loc_180007EBA
0x180007e5b  mov     ecx, [r9+8]
0x180007e5f  cmp     r10d, ecx
0x180007e62  jb      short loc_180007E6C
0x180007e64  lea     eax, [rcx+14h]
0x180007e67  cmp     r10d, eax
0x180007e6a  jb      short loc_180007E75
0x180007e6c  mov     r9, [r9+0C0h]
0x180007e73  jmp     short loc_180007E51
0x180007e75  sub     r10d, ecx
0x180007e78  lea     rbx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks
0x180007e7f  mov     ecx, r10d
0x180007e82  mov     eax, r10d
0x180007e85  shr     rax, 3
0x180007e89  and     ecx, 7
0x180007e8c  mov     al, [rax+r9+18h]
0x180007e91  test    [rcx+rbx], al
0x180007e94  jz      short loc_180007EBA
0x180007e96  mov     r8, [r9+r10*8+20h]
0x180007e9b  xor     ecx, ecx
0x180007e9d  xor     eax, eax
0x180007e9f  test    ecx, ecx
0x180007ea1  cmovns  rax, r8
0x180007ea5  mov     r8, rax
0x180007ea8  jns     short loc_180007EAC
0x180007eaa  xor     edx, edx
0x180007eac  mov     rbx, [rsp+arg_0]
0x180007eb1  neg     edx
0x180007eb3  sbb     rax, rax
0x180007eb6  and     rax, r8
0x180007eb9  retn
0x180007eba  mov     ecx, 80004005h
0x180007ebf  test    [r11+0Ch], dl
0x180007ec3  jz      short loc_180007E9D
0x180007ec5  mov     r8, [r11+10h]
0x180007ec9  jmp     short loc_180007EAC
```
