# CTDynArray<unsigned __int64,20>::operator[](ulong)

- ea: `0x18000d7ac`
- end: `0x18000d811`
- name: `??A?$CTDynArray@_K$0BE@@@QEBA_KK@Z`
- size: `101`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d930`
- `0x18000e4e0`
- `0x18000e580`
- `0x18000e720`
- `0x18000e990`
- `0x18000ef60`

## callees

- `0x18000d7ac`

## pseudocode

```c
__int64 __fastcall CTDynArray<unsigned __int64,20>::operator[](__int64 a1, unsigned int a2)
{
  __int64 v2; // r10
  __int64 i; // r8
  unsigned int v5; // ecx
  unsigned int v6; // edx

  v2 = 0;
  if ( a2 < *(_DWORD *)(a1 + 216) )
  {
    for ( i = a1; i; i = *(_QWORD *)(i + 192) )
    {
      v5 = *(_DWORD *)(i + 8);
      if ( a2 >= v5 && a2 < v5 + 20 )
      {
        v6 = a2 - v5;
        if ( (*(_BYTE *)(((unsigned __int64)v6 >> 3) + i + 24)
            & *((_BYTE *)&CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks + (v6 & 7))) != 0 )
          return *(_QWORD *)(i + 8LL * v6 + 32);
        break;
      }
    }
    if ( (*(_BYTE *)(a1 + 12) & 1) != 0 )
      return *(_QWORD *)(a1 + 16);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d7ac  xor     r10d, r10d
0x18000d7af  mov     r9, rcx
0x18000d7b2  cmp     edx, [rcx+0D8h]
0x18000d7b8  jnb     short loc_18000D80D
0x18000d7ba  mov     r8, rcx
0x18000d7bd  test    r8, r8
0x18000d7c0  jz      short loc_18000D802
0x18000d7c2  mov     ecx, [r8+8]
0x18000d7c6  cmp     edx, ecx
0x18000d7c8  jb      short loc_18000D7D1
0x18000d7ca  lea     eax, [rcx+14h]
0x18000d7cd  cmp     edx, eax
0x18000d7cf  jb      short loc_18000D7DA
0x18000d7d1  mov     r8, [r8+0C0h]
0x18000d7d8  jmp     short loc_18000D7BD
0x18000d7da  sub     edx, ecx
0x18000d7dc  mov     ecx, edx
0x18000d7de  mov     eax, edx
0x18000d7e0  and     ecx, 7
0x18000d7e3  shr     rax, 3
0x18000d7e7  mov     r11d, edx
0x18000d7ea  lea     rdx, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks
0x18000d7f1  mov     al, [rax+r8+18h]
0x18000d7f6  test    [rcx+rdx], al
0x18000d7f9  jz      short loc_18000D802
0x18000d7fb  mov     r10, [r8+r11*8+20h]
0x18000d800  jmp     short loc_18000D80D
0x18000d802  test    byte ptr [r9+0Ch], 1
0x18000d807  jz      short loc_18000D80D
0x18000d809  mov     r10, [r9+10h]
0x18000d80d  mov     rax, r10
0x18000d810  retn
```
