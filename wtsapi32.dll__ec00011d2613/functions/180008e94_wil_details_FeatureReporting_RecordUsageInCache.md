# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180008e94`
- end: `0x180009010`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009094`
- `0x1800110f0`

## callees

- `0x180008ce8`
- `0x180008db8`
- `0x180008e94`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_31;
  }
  if ( a3 - 6 >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)(a3 - 320) >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  for ( i = *a2; ; i = v17 )
  {
    v16 = i | v11 | 1;
    v6[4] = (i | v11) == i;
    if ( (i | v11) == i )
      v16 = i | v11;
    v17 = _InterlockedCompareExchange(a2, v16, i);
    if ( i == v17 )
      break;
  }
  *v6 = (v16 & 1) != 0 && (i & 1) == 0;
  return v6;
}

```

## disassembly

```asm
0x180008e94  mov     [rsp+arg_0], rbx
0x180008e99  push    rdi
0x180008e9a  sub     rsp, 20h
0x180008e9e  xor     eax, eax
0x180008ea0  xorps   xmm0, xmm0
0x180008ea3  mov     edi, r9d
0x180008ea6  mov     r11, rdx
0x180008ea9  mov     r9, rcx
0x180008eac  mov     r10d, r8d
0x180008eaf  movups  xmmword ptr [rcx], xmm0
0x180008eb2  mov     [rcx+10h], rax
0x180008eb6  test    r8d, r8d
0x180008eb9  jz      loc_180008FF7
0x180008ebf  sub     r10d, 1
0x180008ec3  jz      loc_180008FEA
0x180008ec9  sub     r10d, 1
0x180008ecd  jz      loc_180008F6C
0x180008ed3  sub     r10d, 1
0x180008ed7  jz      loc_180008F6C
0x180008edd  sub     r10d, 1
0x180008ee1  jz      loc_180008FF7
0x180008ee7  sub     r10d, 1
0x180008eeb  jz      loc_180008FEA
0x180008ef1  sub     r10d, 1
0x180008ef5  jz      short loc_180008F6C
0x180008ef7  cmp     r10d, 1
0x180008efb  jz      short loc_180008F6C
0x180008efd  lea     r10d, [r8-140h]
0x180008f04  cmp     r10d, 40h ; '@'
0x180008f08  jge     short loc_180008F57
0x180008f0a  mov     eax, [rdx+4]
0x180008f0d  mov     ebx, r10d
0x180008f10  shl     ebx, 5
0x180008f13  mov     ecx, 10h
0x180008f18  test    cl, al
0x180008f1a  jz      short loc_180008F30
0x180008f1c  mov     edx, eax
0x180008f1e  shr     edx, 5
0x180008f21  and     edx, 3Fh
0x180008f24  cmp     edx, r10d
0x180008f27  jnz     short loc_180008F30
0x180008f29  mov     edx, 1
0x180008f2e  jmp     short loc_180008F32
0x180008f30  xor     edx, edx
0x180008f32  mov     [r9+10h], edx
0x180008f36  mov     edx, ebx
0x180008f38  xor     edx, eax
0x180008f3a  and     edx, 7E0h
0x180008f40  xor     edx, eax
0x180008f42  or      edx, ecx
0x180008f44  lock cmpxchg [r11+4], edx
0x180008f4a  jnz     short loc_180008F18
0x180008f4c  cmp     dword ptr [r9+10h], 0
0x180008f51  jnz     loc_180009002
0x180008f57  mov     [r9+8], r8d
0x180008f5b  mov     dword ptr [r9+4], 1
0x180008f63  mov     [r9+0Ch], edi
0x180008f67  jmp     loc_180009002
0x180008f6c  xor     ecx, ecx
0x180008f6e  sub     r8d, 2
0x180008f72  jz      short loc_180008F9A
0x180008f74  sub     r8d, 1
0x180008f78  jz      short loc_180008F93
0x180008f7a  sub     r8d, 3
0x180008f7e  jz      short loc_180008F8C
0x180008f80  cmp     r8d, 1
0x180008f84  jnz     short loc_180008F9F
0x180008f86  lea     ecx, [r8+0Fh]
0x180008f8a  jmp     short loc_180008F9F
0x180008f8c  mov     ecx, 4
0x180008f91  jmp     short loc_180008F9F
0x180008f93  mov     ecx, 8
0x180008f98  jmp     short loc_180008F9F
0x180008f9a  mov     ecx, 2
0x180008f9f  mov     edx, [rdx]
0x180008fa1  xor     eax, eax
0x180008fa3  mov     r8d, ecx
0x180008fa6  or      r8d, edx
0x180008fa9  cmp     r8d, edx
0x180008fac  mov     r10d, r8d
0x180008faf  setz    al
0x180008fb2  or      r10d, 1
0x180008fb6  cmp     r8d, edx
0x180008fb9  mov     [r9+10h], eax
0x180008fbd  mov     eax, edx
0x180008fbf  cmovz   r10d, r8d
0x180008fc3  lock cmpxchg [r11], r10d
0x180008fc8  jz      short loc_180008FCE
0x180008fca  mov     edx, eax
0x180008fcc  jmp     short loc_180008FA1
0x180008fce  test    r10b, 1
0x180008fd2  setnz   cl
0x180008fd5  test    dl, 1
0x180008fd8  setz    al
0x180008fdb  test    al, cl
0x180008fdd  mov     eax, 0
0x180008fe2  setnz   al
0x180008fe5  mov     [r9], eax
0x180008fe8  jmp     short loc_180009002
0x180008fea  mov     edx, r8d
0x180008fed  mov     rcx, r11
0x180008ff0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180008ff5  jmp     short loc_180009002
0x180008ff7  mov     edx, r8d
0x180008ffa  mov     rcx, r11
0x180008ffd  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180009002  mov     rbx, [rsp+28h+arg_0]
0x180009007  mov     rax, r9
0x18000900a  add     rsp, 20h
0x18000900e  pop     rdi
0x18000900f  retn
```
