# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400114bc`
- end: `0x140011639`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400116bc`

## callees

- `0x140011310`
- `0x1400113e0`
- `0x1400114bc`

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
0x1400114bc  mov     [rsp+arg_0], rbx
0x1400114c1  push    rdi
0x1400114c2  sub     rsp, 20h
0x1400114c6  xor     eax, eax
0x1400114c8  xorps   xmm0, xmm0
0x1400114cb  mov     edi, r9d
0x1400114ce  mov     r11, rdx
0x1400114d1  mov     r9, rcx
0x1400114d4  mov     r10d, r8d
0x1400114d7  movups  xmmword ptr [rcx], xmm0
0x1400114da  mov     [rcx+10h], rax
0x1400114de  test    r8d, r8d
0x1400114e1  jz      loc_14001161F
0x1400114e7  sub     r10d, 1
0x1400114eb  jz      loc_140011612
0x1400114f1  sub     r10d, 1
0x1400114f5  jz      loc_140011594
0x1400114fb  sub     r10d, 1
0x1400114ff  jz      loc_140011594
0x140011505  sub     r10d, 1
0x140011509  jz      loc_14001161F
0x14001150f  sub     r10d, 1
0x140011513  jz      loc_140011612
0x140011519  sub     r10d, 1
0x14001151d  jz      short loc_140011594
0x14001151f  cmp     r10d, 1
0x140011523  jz      short loc_140011594
0x140011525  lea     r10d, [r8-140h]
0x14001152c  cmp     r10d, 40h ; '@'
0x140011530  jge     short loc_14001157F
0x140011532  mov     eax, [rdx+4]
0x140011535  mov     ebx, r10d
0x140011538  shl     ebx, 5
0x14001153b  mov     ecx, 10h
0x140011540  test    cl, al
0x140011542  jz      short loc_140011558
0x140011544  mov     edx, eax
0x140011546  shr     edx, 5
0x140011549  and     edx, 3Fh
0x14001154c  cmp     edx, r10d
0x14001154f  jnz     short loc_140011558
0x140011551  mov     edx, 1
0x140011556  jmp     short loc_14001155A
0x140011558  xor     edx, edx
0x14001155a  mov     [r9+10h], edx
0x14001155e  mov     edx, ebx
0x140011560  xor     edx, eax
0x140011562  and     edx, 7E0h
0x140011568  xor     edx, eax
0x14001156a  or      edx, ecx
0x14001156c  lock cmpxchg [r11+4], edx
0x140011572  jnz     short loc_140011540
0x140011574  cmp     dword ptr [r9+10h], 0
0x140011579  jnz     loc_14001162A
0x14001157f  mov     [r9+8], r8d
0x140011583  mov     dword ptr [r9+4], 1
0x14001158b  mov     [r9+0Ch], edi
0x14001158f  jmp     loc_14001162A
0x140011594  xor     ecx, ecx
0x140011596  sub     r8d, 2
0x14001159a  jz      short loc_1400115C2
0x14001159c  sub     r8d, 1
0x1400115a0  jz      short loc_1400115BB
0x1400115a2  sub     r8d, 3
0x1400115a6  jz      short loc_1400115B4
0x1400115a8  cmp     r8d, 1
0x1400115ac  jnz     short loc_1400115C7
0x1400115ae  lea     ecx, [r8+0Fh]
0x1400115b2  jmp     short loc_1400115C7
0x1400115b4  mov     ecx, 4
0x1400115b9  jmp     short loc_1400115C7
0x1400115bb  mov     ecx, 8
0x1400115c0  jmp     short loc_1400115C7
0x1400115c2  mov     ecx, 2
0x1400115c7  mov     edx, [rdx]
0x1400115c9  xor     eax, eax
0x1400115cb  mov     r8d, ecx
0x1400115ce  or      r8d, edx
0x1400115d1  cmp     r8d, edx
0x1400115d4  mov     r10d, r8d
0x1400115d7  setz    al
0x1400115da  or      r10d, 1
0x1400115de  cmp     r8d, edx
0x1400115e1  mov     [r9+10h], eax
0x1400115e5  mov     eax, edx
0x1400115e7  cmovz   r10d, r8d
0x1400115eb  lock cmpxchg [r11], r10d
0x1400115f0  jz      short loc_1400115F6
0x1400115f2  mov     edx, eax
0x1400115f4  jmp     short loc_1400115C9
0x1400115f6  test    r10b, 1
0x1400115fa  setnz   cl
0x1400115fd  test    dl, 1
0x140011600  setz    al
0x140011603  test    al, cl
0x140011605  mov     eax, 0
0x14001160a  setnz   al
0x14001160d  mov     [r9], eax
0x140011610  jmp     short loc_14001162A
0x140011612  mov     edx, r8d
0x140011615  mov     rcx, r11
0x140011618  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14001161d  jmp     short loc_14001162A
0x14001161f  mov     edx, r8d
0x140011622  mov     rcx, r11
0x140011625  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14001162a  mov     rbx, [rsp+28h+arg_0]
0x14001162f  mov     rax, r9
0x140011632  add     rsp, 20h
0x140011636  pop     rdi
0x140011637  retn
```
