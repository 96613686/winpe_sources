# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000cb18`
- end: `0x18000cc8f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008650`

## callees

- `0x18000c96c`
- `0x18000ca3c`
- `0x18000cb18`

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
0x18000cb18  mov     [rsp+arg_0], rbx
0x18000cb1d  push    rdi
0x18000cb1e  sub     rsp, 20h
0x18000cb22  xor     eax, eax
0x18000cb24  xorps   xmm0, xmm0
0x18000cb27  mov     r10, rdx
0x18000cb2a  mov     rbx, rcx
0x18000cb2d  mov     r9d, r8d
0x18000cb30  movups  xmmword ptr [rcx], xmm0
0x18000cb33  mov     [rcx+10h], rax
0x18000cb37  test    r8d, r8d
0x18000cb3a  jz      loc_18000CC73
0x18000cb40  sub     r9d, 1
0x18000cb44  jz      loc_18000CC63
0x18000cb4a  sub     r9d, 1
0x18000cb4e  jz      loc_18000CBEB
0x18000cb54  sub     r9d, 1
0x18000cb58  jz      loc_18000CBEB
0x18000cb5e  sub     r9d, 1
0x18000cb62  jz      loc_18000CC73
0x18000cb68  sub     r9d, 1
0x18000cb6c  jz      loc_18000CC63
0x18000cb72  sub     r9d, 1
0x18000cb76  jz      short loc_18000CBEB
0x18000cb78  cmp     r9d, 1
0x18000cb7c  jz      short loc_18000CBEB
0x18000cb7e  lea     r11d, [r8-140h]
0x18000cb85  lea     r9d, [rax+1]
0x18000cb89  cmp     r11d, 40h ; '@'
0x18000cb8d  jge     short loc_18000CBD7
0x18000cb8f  mov     eax, [rdx+4]
0x18000cb92  lea     ecx, [r9+0Fh]
0x18000cb96  mov     edi, r11d
0x18000cb99  shl     edi, 5
0x18000cb9c  test    cl, al
0x18000cb9e  jz      short loc_18000CBB2
0x18000cba0  mov     edx, eax
0x18000cba2  shr     edx, 5
0x18000cba5  and     edx, 3Fh
0x18000cba8  cmp     edx, r11d
0x18000cbab  jnz     short loc_18000CBB2
0x18000cbad  mov     edx, r9d
0x18000cbb0  jmp     short loc_18000CBB4
0x18000cbb2  xor     edx, edx
0x18000cbb4  mov     [rbx+10h], edx
0x18000cbb7  mov     edx, edi
0x18000cbb9  xor     edx, eax
0x18000cbbb  and     edx, 7E0h
0x18000cbc1  xor     edx, eax
0x18000cbc3  or      edx, ecx
0x18000cbc5  lock cmpxchg [r10+4], edx
0x18000cbcb  jnz     short loc_18000CB9C
0x18000cbcd  cmp     dword ptr [rbx+10h], 0
0x18000cbd1  jnz     loc_18000CC81
0x18000cbd7  mov     [rbx+8], r8d
0x18000cbdb  mov     [rbx+4], r9d
0x18000cbdf  mov     dword ptr [rbx+0Ch], 0
0x18000cbe6  jmp     loc_18000CC81
0x18000cbeb  xor     ecx, ecx
0x18000cbed  sub     r8d, 2
0x18000cbf1  jz      short loc_18000CC19
0x18000cbf3  sub     r8d, 1
0x18000cbf7  jz      short loc_18000CC12
0x18000cbf9  sub     r8d, 3
0x18000cbfd  jz      short loc_18000CC0B
0x18000cbff  cmp     r8d, 1
0x18000cc03  jnz     short loc_18000CC1E
0x18000cc05  lea     ecx, [r8+0Fh]
0x18000cc09  jmp     short loc_18000CC1E
0x18000cc0b  mov     ecx, 4
0x18000cc10  jmp     short loc_18000CC1E
0x18000cc12  mov     ecx, 8
0x18000cc17  jmp     short loc_18000CC1E
0x18000cc19  mov     ecx, 2
0x18000cc1e  mov     edx, [rdx]
0x18000cc20  mov     r9d, 1
0x18000cc26  xor     eax, eax
0x18000cc28  mov     r8d, ecx
0x18000cc2b  or      r8d, edx
0x18000cc2e  cmp     r8d, edx
0x18000cc31  mov     r11d, r8d
0x18000cc34  setz    al
0x18000cc37  or      r11d, r9d
0x18000cc3a  cmp     r8d, edx
0x18000cc3d  mov     [rbx+10h], eax
0x18000cc40  mov     eax, edx
0x18000cc42  cmovz   r11d, r8d
0x18000cc46  lock cmpxchg [r10], r11d
0x18000cc4b  jz      short loc_18000CC51
0x18000cc4d  mov     edx, eax
0x18000cc4f  jmp     short loc_18000CC26
0x18000cc51  test    r9b, r11b
0x18000cc54  jz      short loc_18000CC5B
0x18000cc56  test    r9b, dl
0x18000cc59  jz      short loc_18000CC5E
0x18000cc5b  xor     r9d, r9d
0x18000cc5e  mov     [rbx], r9d
0x18000cc61  jmp     short loc_18000CC81
0x18000cc63  mov     r9, rbx
0x18000cc66  mov     edx, r8d
0x18000cc69  mov     rcx, r10
0x18000cc6c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000cc71  jmp     short loc_18000CC81
0x18000cc73  mov     r9, rbx
0x18000cc76  mov     edx, r8d
0x18000cc79  mov     rcx, r10
0x18000cc7c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000cc81  mov     rax, rbx
0x18000cc84  mov     rbx, [rsp+28h+arg_0]
0x18000cc89  add     rsp, 20h
0x18000cc8d  pop     rdi
0x18000cc8e  retn
```
