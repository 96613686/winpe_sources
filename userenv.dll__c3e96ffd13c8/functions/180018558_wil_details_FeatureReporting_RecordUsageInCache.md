# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180018558`
- end: `0x1800186cf`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016e5c`

## callees

- `0x1800183ac`
- `0x18001847c`
- `0x180018558`

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
0x180018558  mov     [rsp+arg_0], rbx
0x18001855d  push    rdi
0x18001855e  sub     rsp, 20h
0x180018562  xor     eax, eax
0x180018564  xorps   xmm0, xmm0
0x180018567  mov     r10, rdx
0x18001856a  mov     rbx, rcx
0x18001856d  mov     r9d, r8d
0x180018570  movups  xmmword ptr [rcx], xmm0
0x180018573  mov     [rcx+10h], rax
0x180018577  test    r8d, r8d
0x18001857a  jz      loc_1800186B3
0x180018580  sub     r9d, 1
0x180018584  jz      loc_1800186A3
0x18001858a  sub     r9d, 1
0x18001858e  jz      loc_18001862B
0x180018594  sub     r9d, 1
0x180018598  jz      loc_18001862B
0x18001859e  sub     r9d, 1
0x1800185a2  jz      loc_1800186B3
0x1800185a8  sub     r9d, 1
0x1800185ac  jz      loc_1800186A3
0x1800185b2  sub     r9d, 1
0x1800185b6  jz      short loc_18001862B
0x1800185b8  cmp     r9d, 1
0x1800185bc  jz      short loc_18001862B
0x1800185be  lea     r11d, [r8-140h]
0x1800185c5  lea     r9d, [rax+1]
0x1800185c9  cmp     r11d, 40h ; '@'
0x1800185cd  jge     short loc_180018617
0x1800185cf  mov     eax, [rdx+4]
0x1800185d2  lea     ecx, [r9+0Fh]
0x1800185d6  mov     edi, r11d
0x1800185d9  shl     edi, 5
0x1800185dc  test    cl, al
0x1800185de  jz      short loc_1800185F2
0x1800185e0  mov     edx, eax
0x1800185e2  shr     edx, 5
0x1800185e5  and     edx, 3Fh
0x1800185e8  cmp     edx, r11d
0x1800185eb  jnz     short loc_1800185F2
0x1800185ed  mov     edx, r9d
0x1800185f0  jmp     short loc_1800185F4
0x1800185f2  xor     edx, edx
0x1800185f4  mov     [rbx+10h], edx
0x1800185f7  mov     edx, edi
0x1800185f9  xor     edx, eax
0x1800185fb  and     edx, 7E0h
0x180018601  xor     edx, eax
0x180018603  or      edx, ecx
0x180018605  lock cmpxchg [r10+4], edx
0x18001860b  jnz     short loc_1800185DC
0x18001860d  cmp     dword ptr [rbx+10h], 0
0x180018611  jnz     loc_1800186C1
0x180018617  mov     [rbx+8], r8d
0x18001861b  mov     [rbx+4], r9d
0x18001861f  mov     dword ptr [rbx+0Ch], 0
0x180018626  jmp     loc_1800186C1
0x18001862b  xor     ecx, ecx
0x18001862d  sub     r8d, 2
0x180018631  jz      short loc_180018659
0x180018633  sub     r8d, 1
0x180018637  jz      short loc_180018652
0x180018639  sub     r8d, 3
0x18001863d  jz      short loc_18001864B
0x18001863f  cmp     r8d, 1
0x180018643  jnz     short loc_18001865E
0x180018645  lea     ecx, [r8+0Fh]
0x180018649  jmp     short loc_18001865E
0x18001864b  mov     ecx, 4
0x180018650  jmp     short loc_18001865E
0x180018652  mov     ecx, 8
0x180018657  jmp     short loc_18001865E
0x180018659  mov     ecx, 2
0x18001865e  mov     edx, [rdx]
0x180018660  mov     r9d, 1
0x180018666  xor     eax, eax
0x180018668  mov     r8d, ecx
0x18001866b  or      r8d, edx
0x18001866e  cmp     r8d, edx
0x180018671  mov     r11d, r8d
0x180018674  setz    al
0x180018677  or      r11d, r9d
0x18001867a  cmp     r8d, edx
0x18001867d  mov     [rbx+10h], eax
0x180018680  mov     eax, edx
0x180018682  cmovz   r11d, r8d
0x180018686  lock cmpxchg [r10], r11d
0x18001868b  jz      short loc_180018691
0x18001868d  mov     edx, eax
0x18001868f  jmp     short loc_180018666
0x180018691  test    r9b, r11b
0x180018694  jz      short loc_18001869B
0x180018696  test    r9b, dl
0x180018699  jz      short loc_18001869E
0x18001869b  xor     r9d, r9d
0x18001869e  mov     [rbx], r9d
0x1800186a1  jmp     short loc_1800186C1
0x1800186a3  mov     r9, rbx
0x1800186a6  mov     edx, r8d
0x1800186a9  mov     rcx, r10
0x1800186ac  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800186b1  jmp     short loc_1800186C1
0x1800186b3  mov     r9, rbx
0x1800186b6  mov     edx, r8d
0x1800186b9  mov     rcx, r10
0x1800186bc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800186c1  mov     rax, rbx
0x1800186c4  mov     rbx, [rsp+28h+arg_0]
0x1800186c9  add     rsp, 20h
0x1800186cd  pop     rdi
0x1800186ce  retn
```
