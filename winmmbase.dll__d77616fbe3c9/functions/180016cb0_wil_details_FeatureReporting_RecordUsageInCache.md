# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180016cb0`
- end: `0x180016e27`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800158f8`

## callees

- `0x180016b04`
- `0x180016bd4`
- `0x180016cb0`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x180016cb0  mov     [rsp+arg_0], rbx
0x180016cb5  push    rdi
0x180016cb6  sub     rsp, 20h
0x180016cba  xor     eax, eax
0x180016cbc  xorps   xmm0, xmm0
0x180016cbf  mov     r10, rdx
0x180016cc2  mov     rbx, rcx
0x180016cc5  mov     r9d, r8d
0x180016cc8  movups  xmmword ptr [rcx], xmm0
0x180016ccb  mov     [rcx+10h], rax
0x180016ccf  test    r8d, r8d
0x180016cd2  jz      loc_180016E0B
0x180016cd8  sub     r9d, 1
0x180016cdc  jz      loc_180016DFB
0x180016ce2  sub     r9d, 1
0x180016ce6  jz      loc_180016D83
0x180016cec  sub     r9d, 1
0x180016cf0  jz      loc_180016D83
0x180016cf6  sub     r9d, 1
0x180016cfa  jz      loc_180016E0B
0x180016d00  sub     r9d, 1
0x180016d04  jz      loc_180016DFB
0x180016d0a  sub     r9d, 1
0x180016d0e  jz      short loc_180016D83
0x180016d10  cmp     r9d, 1
0x180016d14  jz      short loc_180016D83
0x180016d16  lea     r11d, [r8-140h]
0x180016d1d  lea     r9d, [rax+1]
0x180016d21  cmp     r11d, 40h ; '@'
0x180016d25  jge     short loc_180016D6F
0x180016d27  mov     eax, [rdx+4]
0x180016d2a  lea     ecx, [r9+0Fh]
0x180016d2e  mov     edi, r11d
0x180016d31  shl     edi, 5
0x180016d34  test    cl, al
0x180016d36  jz      short loc_180016D4A
0x180016d38  mov     edx, eax
0x180016d3a  shr     edx, 5
0x180016d3d  and     edx, 3Fh
0x180016d40  cmp     edx, r11d
0x180016d43  jnz     short loc_180016D4A
0x180016d45  mov     edx, r9d
0x180016d48  jmp     short loc_180016D4C
0x180016d4a  xor     edx, edx
0x180016d4c  mov     [rbx+10h], edx
0x180016d4f  mov     edx, edi
0x180016d51  xor     edx, eax
0x180016d53  and     edx, 7E0h
0x180016d59  xor     edx, eax
0x180016d5b  or      edx, ecx
0x180016d5d  lock cmpxchg [r10+4], edx
0x180016d63  jnz     short loc_180016D34
0x180016d65  cmp     dword ptr [rbx+10h], 0
0x180016d69  jnz     loc_180016E19
0x180016d6f  mov     [rbx+8], r8d
0x180016d73  mov     [rbx+4], r9d
0x180016d77  mov     dword ptr [rbx+0Ch], 0
0x180016d7e  jmp     loc_180016E19
0x180016d83  xor     ecx, ecx
0x180016d85  sub     r8d, 2
0x180016d89  jz      short loc_180016DB1
0x180016d8b  sub     r8d, 1
0x180016d8f  jz      short loc_180016DAA
0x180016d91  sub     r8d, 3
0x180016d95  jz      short loc_180016DA3
0x180016d97  cmp     r8d, 1
0x180016d9b  jnz     short loc_180016DB6
0x180016d9d  lea     ecx, [r8+0Fh]
0x180016da1  jmp     short loc_180016DB6
0x180016da3  mov     ecx, 4
0x180016da8  jmp     short loc_180016DB6
0x180016daa  mov     ecx, 8
0x180016daf  jmp     short loc_180016DB6
0x180016db1  mov     ecx, 2
0x180016db6  mov     edx, [rdx]
0x180016db8  mov     r9d, 1
0x180016dbe  xor     eax, eax
0x180016dc0  mov     r8d, ecx
0x180016dc3  or      r8d, edx
0x180016dc6  cmp     r8d, edx
0x180016dc9  mov     r11d, r8d
0x180016dcc  setz    al
0x180016dcf  or      r11d, r9d
0x180016dd2  cmp     r8d, edx
0x180016dd5  mov     [rbx+10h], eax
0x180016dd8  mov     eax, edx
0x180016dda  cmovz   r11d, r8d
0x180016dde  lock cmpxchg [r10], r11d
0x180016de3  jz      short loc_180016DE9
0x180016de5  mov     edx, eax
0x180016de7  jmp     short loc_180016DBE
0x180016de9  test    r9b, r11b
0x180016dec  jz      short loc_180016DF3
0x180016dee  test    r9b, dl
0x180016df1  jz      short loc_180016DF6
0x180016df3  xor     r9d, r9d
0x180016df6  mov     [rbx], r9d
0x180016df9  jmp     short loc_180016E19
0x180016dfb  mov     r9, rbx
0x180016dfe  mov     edx, r8d
0x180016e01  mov     rcx, r10
0x180016e04  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180016e09  jmp     short loc_180016E19
0x180016e0b  mov     r9, rbx
0x180016e0e  mov     edx, r8d
0x180016e11  mov     rcx, r10
0x180016e14  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180016e19  mov     rax, rbx
0x180016e1c  mov     rbx, [rsp+28h+arg_0]
0x180016e21  add     rsp, 20h
0x180016e25  pop     rdi
0x180016e26  retn
```
