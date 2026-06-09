# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000aac4`
- end: `0x18000ac3a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003fa0`

## callees

- `0x18000aac4`
- `0x18000ac40`
- `0x18001a2ac`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18000aac4  push    rbx
0x18000aac6  sub     rsp, 20h
0x18000aaca  xor     eax, eax
0x18000aacc  xorps   xmm0, xmm0
0x18000aacf  mov     r10, rdx
0x18000aad2  mov     rbx, rcx
0x18000aad5  mov     r9d, r8d
0x18000aad8  movups  xmmword ptr [rcx], xmm0
0x18000aadb  mov     [rcx+10h], rax
0x18000aadf  test    r8d, r8d
0x18000aae2  jz      loc_18000AC23
0x18000aae8  sub     r9d, 1
0x18000aaec  jz      loc_18000AC13
0x18000aaf2  sub     r9d, 1
0x18000aaf6  jz      loc_18000AB97
0x18000aafc  sub     r9d, 1
0x18000ab00  jz      loc_18000AB97
0x18000ab06  sub     r9d, 1
0x18000ab0a  jz      loc_18000AC23
0x18000ab10  sub     r9d, 1
0x18000ab14  jz      loc_18000AC13
0x18000ab1a  sub     r9d, 1
0x18000ab1e  jz      short loc_18000AB97
0x18000ab20  cmp     r9d, 1
0x18000ab24  jz      short loc_18000AB97
0x18000ab26  lea     r9d, [r8-140h]
0x18000ab2d  cmp     r9d, 40h ; '@'
0x18000ab31  jge     short loc_18000AB80
0x18000ab33  mov     eax, [rdx+4]
0x18000ab36  mov     r11d, r9d
0x18000ab39  shl     r11d, 5
0x18000ab3d  mov     ecx, 10h
0x18000ab42  test    cl, al
0x18000ab44  jz      short loc_18000AB5A
0x18000ab46  mov     edx, eax
0x18000ab48  shr     edx, 5
0x18000ab4b  and     edx, 3Fh
0x18000ab4e  cmp     edx, r9d
0x18000ab51  jnz     short loc_18000AB5A
0x18000ab53  mov     edx, 1
0x18000ab58  jmp     short loc_18000AB5C
0x18000ab5a  xor     edx, edx
0x18000ab5c  mov     [rbx+10h], edx
0x18000ab5f  mov     edx, r11d
0x18000ab62  xor     edx, eax
0x18000ab64  and     edx, 7E0h
0x18000ab6a  xor     edx, eax
0x18000ab6c  or      edx, ecx
0x18000ab6e  lock cmpxchg [r10+4], edx
0x18000ab74  jnz     short loc_18000AB42
0x18000ab76  cmp     dword ptr [rbx+10h], 0
0x18000ab7a  jnz     loc_18000AC31
0x18000ab80  mov     [rbx+8], r8d
0x18000ab84  mov     dword ptr [rbx+4], 1
0x18000ab8b  mov     dword ptr [rbx+0Ch], 0
0x18000ab92  jmp     loc_18000AC31
0x18000ab97  xor     ecx, ecx
0x18000ab99  sub     r8d, 2
0x18000ab9d  jz      short loc_18000ABC5
0x18000ab9f  sub     r8d, 1
0x18000aba3  jz      short loc_18000ABBE
0x18000aba5  sub     r8d, 3
0x18000aba9  jz      short loc_18000ABB7
0x18000abab  cmp     r8d, 1
0x18000abaf  jnz     short loc_18000ABCA
0x18000abb1  lea     ecx, [r8+0Fh]
0x18000abb5  jmp     short loc_18000ABCA
0x18000abb7  mov     ecx, 4
0x18000abbc  jmp     short loc_18000ABCA
0x18000abbe  mov     ecx, 8
0x18000abc3  jmp     short loc_18000ABCA
0x18000abc5  mov     ecx, 2
0x18000abca  mov     edx, [rdx]
0x18000abcc  xor     eax, eax
0x18000abce  mov     r8d, ecx
0x18000abd1  or      r8d, edx
0x18000abd4  cmp     r8d, edx
0x18000abd7  mov     r9d, r8d
0x18000abda  setz    al
0x18000abdd  or      r9d, 1
0x18000abe1  cmp     r8d, edx
0x18000abe4  mov     [rbx+10h], eax
0x18000abe7  mov     eax, edx
0x18000abe9  cmovz   r9d, r8d
0x18000abed  lock cmpxchg [r10], r9d
0x18000abf2  jz      short loc_18000ABF8
0x18000abf4  mov     edx, eax
0x18000abf6  jmp     short loc_18000ABCC
0x18000abf8  test    r9b, 1
0x18000abfc  setnz   cl
0x18000abff  test    dl, 1
0x18000ac02  setz    al
0x18000ac05  test    al, cl
0x18000ac07  mov     eax, 0
0x18000ac0c  setnz   al
0x18000ac0f  mov     [rbx], eax
0x18000ac11  jmp     short loc_18000AC31
0x18000ac13  mov     r9, rbx
0x18000ac16  mov     edx, r8d
0x18000ac19  mov     rcx, r10
0x18000ac1c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ac21  jmp     short loc_18000AC31
0x18000ac23  mov     r9, rbx
0x18000ac26  mov     edx, r8d
0x18000ac29  mov     rcx, r10
0x18000ac2c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000ac31  mov     rax, rbx
0x18000ac34  add     rsp, 20h
0x18000ac38  pop     rbx
0x18000ac39  retn
```
