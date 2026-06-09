# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140011e3c`
- end: `0x140011fb8`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140012048`

## callees

- `0x140011c90`
- `0x140011d60`
- `0x140011e3c`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
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
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x140011e3c  mov     [rsp+arg_0], rbx
0x140011e41  mov     [rsp+arg_8], rsi
0x140011e46  push    rdi
0x140011e47  sub     rsp, 20h
0x140011e4b  xor     eax, eax
0x140011e4d  xorps   xmm0, xmm0
0x140011e50  mov     esi, r9d
0x140011e53  mov     r11, rdx
0x140011e56  mov     r9, rcx
0x140011e59  mov     r10d, r8d
0x140011e5c  movups  xmmword ptr [rcx], xmm0
0x140011e5f  mov     [rcx+10h], rax
0x140011e63  test    r8d, r8d
0x140011e66  jz      loc_140011F99
0x140011e6c  sub     r10d, 1
0x140011e70  jz      loc_140011F8C
0x140011e76  sub     r10d, 1
0x140011e7a  jz      loc_140011F13
0x140011e80  sub     r10d, 1
0x140011e84  jz      loc_140011F13
0x140011e8a  sub     r10d, 1
0x140011e8e  jz      loc_140011F99
0x140011e94  sub     r10d, 1
0x140011e98  jz      loc_140011F8C
0x140011e9e  sub     r10d, 1
0x140011ea2  jz      short loc_140011F13
0x140011ea4  cmp     r10d, 1
0x140011ea8  jz      short loc_140011F13
0x140011eaa  lea     ebx, [r8-140h]
0x140011eb1  lea     r10d, [rax+1]
0x140011eb5  cmp     ebx, 40h ; '@'
0x140011eb8  jge     short loc_140011F02
0x140011eba  mov     eax, [rdx+4]
0x140011ebd  lea     ecx, [r10+0Fh]
0x140011ec1  mov     edi, ebx
0x140011ec3  shl     edi, 5
0x140011ec6  test    cl, al
0x140011ec8  jz      short loc_140011EDB
0x140011eca  mov     edx, eax
0x140011ecc  shr     edx, 5
0x140011ecf  and     edx, 3Fh
0x140011ed2  cmp     edx, ebx
0x140011ed4  jnz     short loc_140011EDB
0x140011ed6  mov     edx, r10d
0x140011ed9  jmp     short loc_140011EDD
0x140011edb  xor     edx, edx
0x140011edd  mov     [r9+10h], edx
0x140011ee1  mov     edx, edi
0x140011ee3  xor     edx, eax
0x140011ee5  and     edx, 7E0h
0x140011eeb  xor     edx, eax
0x140011eed  or      edx, ecx
0x140011eef  lock cmpxchg [r11+4], edx
0x140011ef5  jnz     short loc_140011EC6
0x140011ef7  cmp     dword ptr [r9+10h], 0
0x140011efc  jnz     loc_140011FA4
0x140011f02  mov     [r9+8], r8d
0x140011f06  mov     [r9+4], r10d
0x140011f0a  mov     [r9+0Ch], esi
0x140011f0e  jmp     loc_140011FA4
0x140011f13  xor     ecx, ecx
0x140011f15  sub     r8d, 2
0x140011f19  jz      short loc_140011F41
0x140011f1b  sub     r8d, 1
0x140011f1f  jz      short loc_140011F3A
0x140011f21  sub     r8d, 3
0x140011f25  jz      short loc_140011F33
0x140011f27  cmp     r8d, 1
0x140011f2b  jnz     short loc_140011F46
0x140011f2d  lea     ecx, [r8+0Fh]
0x140011f31  jmp     short loc_140011F46
0x140011f33  mov     ecx, 4
0x140011f38  jmp     short loc_140011F46
0x140011f3a  mov     ecx, 8
0x140011f3f  jmp     short loc_140011F46
0x140011f41  mov     ecx, 2
0x140011f46  mov     edx, [rdx]
0x140011f48  mov     r10d, 1
0x140011f4e  xor     eax, eax
0x140011f50  mov     r8d, ecx
0x140011f53  or      r8d, edx
0x140011f56  cmp     r8d, edx
0x140011f59  mov     ebx, r8d
0x140011f5c  setz    al
0x140011f5f  or      ebx, r10d
0x140011f62  cmp     r8d, edx
0x140011f65  mov     [r9+10h], eax
0x140011f69  mov     eax, edx
0x140011f6b  cmovz   ebx, r8d
0x140011f6f  lock cmpxchg [r11], ebx
0x140011f74  jz      short loc_140011F7A
0x140011f76  mov     edx, eax
0x140011f78  jmp     short loc_140011F4E
0x140011f7a  test    r10b, bl
0x140011f7d  jz      short loc_140011F84
0x140011f7f  test    r10b, dl
0x140011f82  jz      short loc_140011F87
0x140011f84  xor     r10d, r10d
0x140011f87  mov     [r9], r10d
0x140011f8a  jmp     short loc_140011FA4
0x140011f8c  mov     edx, r8d
0x140011f8f  mov     rcx, r11
0x140011f92  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140011f97  jmp     short loc_140011FA4
0x140011f99  mov     edx, r8d
0x140011f9c  mov     rcx, r11
0x140011f9f  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140011fa4  mov     rbx, [rsp+28h+arg_0]
0x140011fa9  mov     rax, r9
0x140011fac  mov     rsi, [rsp+28h+arg_8]
0x140011fb1  add     rsp, 20h
0x140011fb5  pop     rdi
0x140011fb6  retn
```
