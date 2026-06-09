# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140017a10`
- end: `0x140017b8c`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017c1c`

## callees

- `0x140017864`
- `0x140017934`
- `0x140017a10`

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
0x140017a10  mov     [rsp+arg_0], rbx
0x140017a15  mov     [rsp+arg_8], rsi
0x140017a1a  push    rdi
0x140017a1b  sub     rsp, 20h
0x140017a1f  xor     eax, eax
0x140017a21  xorps   xmm0, xmm0
0x140017a24  mov     esi, r9d
0x140017a27  mov     r11, rdx
0x140017a2a  mov     r9, rcx
0x140017a2d  mov     r10d, r8d
0x140017a30  movups  xmmword ptr [rcx], xmm0
0x140017a33  mov     [rcx+10h], rax
0x140017a37  test    r8d, r8d
0x140017a3a  jz      loc_140017B6D
0x140017a40  sub     r10d, 1
0x140017a44  jz      loc_140017B60
0x140017a4a  sub     r10d, 1
0x140017a4e  jz      loc_140017AE7
0x140017a54  sub     r10d, 1
0x140017a58  jz      loc_140017AE7
0x140017a5e  sub     r10d, 1
0x140017a62  jz      loc_140017B6D
0x140017a68  sub     r10d, 1
0x140017a6c  jz      loc_140017B60
0x140017a72  sub     r10d, 1
0x140017a76  jz      short loc_140017AE7
0x140017a78  cmp     r10d, 1
0x140017a7c  jz      short loc_140017AE7
0x140017a7e  lea     ebx, [r8-140h]
0x140017a85  lea     r10d, [rax+1]
0x140017a89  cmp     ebx, 40h ; '@'
0x140017a8c  jge     short loc_140017AD6
0x140017a8e  mov     eax, [rdx+4]
0x140017a91  lea     ecx, [r10+0Fh]
0x140017a95  mov     edi, ebx
0x140017a97  shl     edi, 5
0x140017a9a  test    cl, al
0x140017a9c  jz      short loc_140017AAF
0x140017a9e  mov     edx, eax
0x140017aa0  shr     edx, 5
0x140017aa3  and     edx, 3Fh
0x140017aa6  cmp     edx, ebx
0x140017aa8  jnz     short loc_140017AAF
0x140017aaa  mov     edx, r10d
0x140017aad  jmp     short loc_140017AB1
0x140017aaf  xor     edx, edx
0x140017ab1  mov     [r9+10h], edx
0x140017ab5  mov     edx, edi
0x140017ab7  xor     edx, eax
0x140017ab9  and     edx, 7E0h
0x140017abf  xor     edx, eax
0x140017ac1  or      edx, ecx
0x140017ac3  lock cmpxchg [r11+4], edx
0x140017ac9  jnz     short loc_140017A9A
0x140017acb  cmp     dword ptr [r9+10h], 0
0x140017ad0  jnz     loc_140017B78
0x140017ad6  mov     [r9+8], r8d
0x140017ada  mov     [r9+4], r10d
0x140017ade  mov     [r9+0Ch], esi
0x140017ae2  jmp     loc_140017B78
0x140017ae7  xor     ecx, ecx
0x140017ae9  sub     r8d, 2
0x140017aed  jz      short loc_140017B15
0x140017aef  sub     r8d, 1
0x140017af3  jz      short loc_140017B0E
0x140017af5  sub     r8d, 3
0x140017af9  jz      short loc_140017B07
0x140017afb  cmp     r8d, 1
0x140017aff  jnz     short loc_140017B1A
0x140017b01  lea     ecx, [r8+0Fh]
0x140017b05  jmp     short loc_140017B1A
0x140017b07  mov     ecx, 4
0x140017b0c  jmp     short loc_140017B1A
0x140017b0e  mov     ecx, 8
0x140017b13  jmp     short loc_140017B1A
0x140017b15  mov     ecx, 2
0x140017b1a  mov     edx, [rdx]
0x140017b1c  mov     r10d, 1
0x140017b22  xor     eax, eax
0x140017b24  mov     r8d, ecx
0x140017b27  or      r8d, edx
0x140017b2a  cmp     r8d, edx
0x140017b2d  mov     ebx, r8d
0x140017b30  setz    al
0x140017b33  or      ebx, r10d
0x140017b36  cmp     r8d, edx
0x140017b39  mov     [r9+10h], eax
0x140017b3d  mov     eax, edx
0x140017b3f  cmovz   ebx, r8d
0x140017b43  lock cmpxchg [r11], ebx
0x140017b48  jz      short loc_140017B4E
0x140017b4a  mov     edx, eax
0x140017b4c  jmp     short loc_140017B22
0x140017b4e  test    r10b, bl
0x140017b51  jz      short loc_140017B58
0x140017b53  test    r10b, dl
0x140017b56  jz      short loc_140017B5B
0x140017b58  xor     r10d, r10d
0x140017b5b  mov     [r9], r10d
0x140017b5e  jmp     short loc_140017B78
0x140017b60  mov     edx, r8d
0x140017b63  mov     rcx, r11
0x140017b66  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140017b6b  jmp     short loc_140017B78
0x140017b6d  mov     edx, r8d
0x140017b70  mov     rcx, r11
0x140017b73  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140017b78  mov     rbx, [rsp+28h+arg_0]
0x140017b7d  mov     rax, r9
0x140017b80  mov     rsi, [rsp+28h+arg_8]
0x140017b85  add     rsp, 20h
0x140017b89  pop     rdi
0x140017b8a  retn
```
