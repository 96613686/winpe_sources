# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800157cc`
- end: `0x180015948`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015a7c`

## callees

- `0x180015620`
- `0x1800156f0`
- `0x1800157cc`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  _DWORD *v6; // r9
  int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
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
0x1800157cc  mov     [rsp+arg_0], rbx
0x1800157d1  push    rdi
0x1800157d2  sub     rsp, 20h
0x1800157d6  xor     eax, eax
0x1800157d8  xorps   xmm0, xmm0
0x1800157db  mov     edi, r9d
0x1800157de  mov     r11, rdx
0x1800157e1  mov     r9, rcx
0x1800157e4  mov     r10d, r8d
0x1800157e7  movups  xmmword ptr [rcx], xmm0
0x1800157ea  mov     [rcx+10h], rax
0x1800157ee  test    r8d, r8d
0x1800157f1  jz      loc_18001592F
0x1800157f7  sub     r10d, 1
0x1800157fb  jz      loc_180015922
0x180015801  sub     r10d, 1
0x180015805  jz      loc_1800158A4
0x18001580b  sub     r10d, 1
0x18001580f  jz      loc_1800158A4
0x180015815  sub     r10d, 1
0x180015819  jz      loc_18001592F
0x18001581f  sub     r10d, 1
0x180015823  jz      loc_180015922
0x180015829  sub     r10d, 1
0x18001582d  jz      short loc_1800158A4
0x18001582f  cmp     r10d, 1
0x180015833  jz      short loc_1800158A4
0x180015835  lea     r10d, [r8-140h]
0x18001583c  cmp     r10d, 40h ; '@'
0x180015840  jge     short loc_18001588F
0x180015842  mov     eax, [rdx+4]
0x180015845  mov     ebx, r10d
0x180015848  shl     ebx, 5
0x18001584b  mov     ecx, 10h
0x180015850  test    cl, al
0x180015852  jz      short loc_180015868
0x180015854  mov     edx, eax
0x180015856  shr     edx, 5
0x180015859  and     edx, 3Fh
0x18001585c  cmp     edx, r10d
0x18001585f  jnz     short loc_180015868
0x180015861  mov     edx, 1
0x180015866  jmp     short loc_18001586A
0x180015868  xor     edx, edx
0x18001586a  mov     [r9+10h], edx
0x18001586e  mov     edx, ebx
0x180015870  xor     edx, eax
0x180015872  and     edx, 7E0h
0x180015878  xor     edx, eax
0x18001587a  or      edx, ecx
0x18001587c  lock cmpxchg [r11+4], edx
0x180015882  jnz     short loc_180015850
0x180015884  cmp     dword ptr [r9+10h], 0
0x180015889  jnz     loc_18001593A
0x18001588f  mov     [r9+8], r8d
0x180015893  mov     dword ptr [r9+4], 1
0x18001589b  mov     [r9+0Ch], edi
0x18001589f  jmp     loc_18001593A
0x1800158a4  xor     ecx, ecx
0x1800158a6  sub     r8d, 2
0x1800158aa  jz      short loc_1800158D2
0x1800158ac  sub     r8d, 1
0x1800158b0  jz      short loc_1800158CB
0x1800158b2  sub     r8d, 3
0x1800158b6  jz      short loc_1800158C4
0x1800158b8  cmp     r8d, 1
0x1800158bc  jnz     short loc_1800158D7
0x1800158be  lea     ecx, [r8+0Fh]
0x1800158c2  jmp     short loc_1800158D7
0x1800158c4  mov     ecx, 4
0x1800158c9  jmp     short loc_1800158D7
0x1800158cb  mov     ecx, 8
0x1800158d0  jmp     short loc_1800158D7
0x1800158d2  mov     ecx, 2
0x1800158d7  mov     edx, [rdx]
0x1800158d9  xor     eax, eax
0x1800158db  mov     r8d, ecx
0x1800158de  or      r8d, edx
0x1800158e1  cmp     r8d, edx
0x1800158e4  mov     r10d, r8d
0x1800158e7  setz    al
0x1800158ea  or      r10d, 1
0x1800158ee  cmp     r8d, edx
0x1800158f1  mov     [r9+10h], eax
0x1800158f5  mov     eax, edx
0x1800158f7  cmovz   r10d, r8d
0x1800158fb  lock cmpxchg [r11], r10d
0x180015900  jz      short loc_180015906
0x180015902  mov     edx, eax
0x180015904  jmp     short loc_1800158D9
0x180015906  test    r10b, 1
0x18001590a  setnz   cl
0x18001590d  test    dl, 1
0x180015910  setz    al
0x180015913  test    al, cl
0x180015915  mov     eax, 0
0x18001591a  setnz   al
0x18001591d  mov     [r9], eax
0x180015920  jmp     short loc_18001593A
0x180015922  mov     edx, r8d
0x180015925  mov     rcx, r11
0x180015928  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18001592d  jmp     short loc_18001593A
0x18001592f  mov     edx, r8d
0x180015932  mov     rcx, r11
0x180015935  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18001593a  mov     rbx, [rsp+28h+arg_0]
0x18001593f  mov     rax, r9
0x180015942  add     rsp, 20h
0x180015946  pop     rdi
0x180015947  retn
```
