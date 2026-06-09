# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001075c`
- end: `0x1800108d4`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000aa18`

## callees

- `0x1800105b0`
- `0x180010680`
- `0x18001075c`

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
0x18001075c  mov     [rsp+arg_0], rbx
0x180010761  push    rdi
0x180010762  sub     rsp, 20h
0x180010766  xor     eax, eax
0x180010768  xorps   xmm0, xmm0
0x18001076b  mov     r10, rdx
0x18001076e  mov     rbx, rcx
0x180010771  mov     r9d, r8d
0x180010774  movups  xmmword ptr [rcx], xmm0
0x180010777  mov     [rcx+10h], rax
0x18001077b  test    r8d, r8d
0x18001077e  jz      loc_1800108B7
0x180010784  sub     r9d, 1
0x180010788  jz      loc_1800108A7
0x18001078e  sub     r9d, 1
0x180010792  jz      loc_18001082F
0x180010798  sub     r9d, 1
0x18001079c  jz      loc_18001082F
0x1800107a2  sub     r9d, 1
0x1800107a6  jz      loc_1800108B7
0x1800107ac  sub     r9d, 1
0x1800107b0  jz      loc_1800108A7
0x1800107b6  sub     r9d, 1
0x1800107ba  jz      short loc_18001082F
0x1800107bc  cmp     r9d, 1
0x1800107c0  jz      short loc_18001082F
0x1800107c2  lea     r11d, [r8-140h]
0x1800107c9  lea     r9d, [rax+1]
0x1800107cd  cmp     r11d, 40h ; '@'
0x1800107d1  jge     short loc_18001081B
0x1800107d3  mov     eax, [rdx+4]
0x1800107d6  lea     ecx, [r9+0Fh]
0x1800107da  mov     edi, r11d
0x1800107dd  shl     edi, 5
0x1800107e0  test    cl, al
0x1800107e2  jz      short loc_1800107F6
0x1800107e4  mov     edx, eax
0x1800107e6  shr     edx, 5
0x1800107e9  and     edx, 3Fh
0x1800107ec  cmp     edx, r11d
0x1800107ef  jnz     short loc_1800107F6
0x1800107f1  mov     edx, r9d
0x1800107f4  jmp     short loc_1800107F8
0x1800107f6  xor     edx, edx
0x1800107f8  mov     [rbx+10h], edx
0x1800107fb  mov     edx, edi
0x1800107fd  xor     edx, eax
0x1800107ff  and     edx, 7E0h
0x180010805  xor     edx, eax
0x180010807  or      edx, ecx
0x180010809  lock cmpxchg [r10+4], edx
0x18001080f  jnz     short loc_1800107E0
0x180010811  cmp     dword ptr [rbx+10h], 0
0x180010815  jnz     loc_1800108C5
0x18001081b  mov     [rbx+8], r8d
0x18001081f  mov     [rbx+4], r9d
0x180010823  mov     dword ptr [rbx+0Ch], 0
0x18001082a  jmp     loc_1800108C5
0x18001082f  xor     ecx, ecx
0x180010831  sub     r8d, 2
0x180010835  jz      short loc_18001085D
0x180010837  sub     r8d, 1
0x18001083b  jz      short loc_180010856
0x18001083d  sub     r8d, 3
0x180010841  jz      short loc_18001084F
0x180010843  cmp     r8d, 1
0x180010847  jnz     short loc_180010862
0x180010849  lea     ecx, [r8+0Fh]
0x18001084d  jmp     short loc_180010862
0x18001084f  mov     ecx, 4
0x180010854  jmp     short loc_180010862
0x180010856  mov     ecx, 8
0x18001085b  jmp     short loc_180010862
0x18001085d  mov     ecx, 2
0x180010862  mov     edx, [rdx]
0x180010864  mov     r9d, 1
0x18001086a  xor     eax, eax
0x18001086c  mov     r8d, ecx
0x18001086f  or      r8d, edx
0x180010872  cmp     r8d, edx
0x180010875  mov     r11d, r8d
0x180010878  setz    al
0x18001087b  or      r11d, r9d
0x18001087e  cmp     r8d, edx
0x180010881  mov     [rbx+10h], eax
0x180010884  mov     eax, edx
0x180010886  cmovz   r11d, r8d
0x18001088a  lock cmpxchg [r10], r11d
0x18001088f  jz      short loc_180010895
0x180010891  mov     edx, eax
0x180010893  jmp     short loc_18001086A
0x180010895  test    r9b, r11b
0x180010898  jz      short loc_18001089F
0x18001089a  test    r9b, dl
0x18001089d  jz      short loc_1800108A2
0x18001089f  xor     r9d, r9d
0x1800108a2  mov     [rbx], r9d
0x1800108a5  jmp     short loc_1800108C5
0x1800108a7  mov     r9, rbx
0x1800108aa  mov     edx, r8d
0x1800108ad  mov     rcx, r10
0x1800108b0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800108b5  jmp     short loc_1800108C5
0x1800108b7  mov     r9, rbx
0x1800108ba  mov     edx, r8d
0x1800108bd  mov     rcx, r10
0x1800108c0  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800108c5  mov     rax, rbx
0x1800108c8  mov     rbx, [rsp+28h+arg_0]
0x1800108cd  add     rsp, 20h
0x1800108d1  pop     rdi
0x1800108d2  retn
```
