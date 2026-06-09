# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140007300`
- end: `0x14000747b`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400075a0`

## callees

- `0x140007154`
- `0x140007224`
- `0x140007300`

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
0x140007300  mov     [rsp+arg_0], rbx
0x140007305  mov     [rsp+arg_8], rsi
0x14000730a  push    rdi
0x14000730b  sub     rsp, 20h
0x14000730f  xor     eax, eax
0x140007311  xorps   xmm0, xmm0
0x140007314  mov     esi, r9d
0x140007317  mov     r11, rdx
0x14000731a  mov     r9, rcx
0x14000731d  mov     r10d, r8d
0x140007320  movups  xmmword ptr [rcx], xmm0
0x140007323  mov     [rcx+10h], rax
0x140007327  test    r8d, r8d
0x14000732a  jz      loc_14000745D
0x140007330  sub     r10d, 1
0x140007334  jz      loc_140007450
0x14000733a  sub     r10d, 1
0x14000733e  jz      loc_1400073D7
0x140007344  sub     r10d, 1
0x140007348  jz      loc_1400073D7
0x14000734e  sub     r10d, 1
0x140007352  jz      loc_14000745D
0x140007358  sub     r10d, 1
0x14000735c  jz      loc_140007450
0x140007362  sub     r10d, 1
0x140007366  jz      short loc_1400073D7
0x140007368  cmp     r10d, 1
0x14000736c  jz      short loc_1400073D7
0x14000736e  lea     ebx, [r8-140h]
0x140007375  lea     r10d, [rax+1]
0x140007379  cmp     ebx, 40h ; '@'
0x14000737c  jge     short loc_1400073C6
0x14000737e  mov     eax, [rdx+4]
0x140007381  lea     ecx, [r10+0Fh]
0x140007385  mov     edi, ebx
0x140007387  shl     edi, 5
0x14000738a  test    cl, al
0x14000738c  jz      short loc_14000739F
0x14000738e  mov     edx, eax
0x140007390  shr     edx, 5
0x140007393  and     edx, 3Fh
0x140007396  cmp     edx, ebx
0x140007398  jnz     short loc_14000739F
0x14000739a  mov     edx, r10d
0x14000739d  jmp     short loc_1400073A1
0x14000739f  xor     edx, edx
0x1400073a1  mov     [r9+10h], edx
0x1400073a5  mov     edx, edi
0x1400073a7  xor     edx, eax
0x1400073a9  and     edx, 7E0h
0x1400073af  xor     edx, eax
0x1400073b1  or      edx, ecx
0x1400073b3  lock cmpxchg [r11+4], edx
0x1400073b9  jnz     short loc_14000738A
0x1400073bb  cmp     dword ptr [r9+10h], 0
0x1400073c0  jnz     loc_140007468
0x1400073c6  mov     [r9+8], r8d
0x1400073ca  mov     [r9+4], r10d
0x1400073ce  mov     [r9+0Ch], esi
0x1400073d2  jmp     loc_140007468
0x1400073d7  xor     ecx, ecx
0x1400073d9  sub     r8d, 2
0x1400073dd  jz      short loc_140007405
0x1400073df  sub     r8d, 1
0x1400073e3  jz      short loc_1400073FE
0x1400073e5  sub     r8d, 3
0x1400073e9  jz      short loc_1400073F7
0x1400073eb  cmp     r8d, 1
0x1400073ef  jnz     short loc_14000740A
0x1400073f1  lea     ecx, [r8+0Fh]
0x1400073f5  jmp     short loc_14000740A
0x1400073f7  mov     ecx, 4
0x1400073fc  jmp     short loc_14000740A
0x1400073fe  mov     ecx, 8
0x140007403  jmp     short loc_14000740A
0x140007405  mov     ecx, 2
0x14000740a  mov     edx, [rdx]
0x14000740c  mov     r10d, 1
0x140007412  xor     eax, eax
0x140007414  mov     r8d, ecx
0x140007417  or      r8d, edx
0x14000741a  cmp     r8d, edx
0x14000741d  mov     ebx, r8d
0x140007420  setz    al
0x140007423  or      ebx, r10d
0x140007426  cmp     r8d, edx
0x140007429  mov     [r9+10h], eax
0x14000742d  mov     eax, edx
0x14000742f  cmovz   ebx, r8d
0x140007433  lock cmpxchg [r11], ebx
0x140007438  jz      short loc_14000743E
0x14000743a  mov     edx, eax
0x14000743c  jmp     short loc_140007412
0x14000743e  test    r10b, bl
0x140007441  jz      short loc_140007448
0x140007443  test    r10b, dl
0x140007446  jz      short loc_14000744B
0x140007448  xor     r10d, r10d
0x14000744b  mov     [r9], r10d
0x14000744e  jmp     short loc_140007468
0x140007450  mov     edx, r8d
0x140007453  mov     rcx, r11
0x140007456  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000745b  jmp     short loc_140007468
0x14000745d  mov     edx, r8d
0x140007460  mov     rcx, r11
0x140007463  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140007468  mov     rbx, [rsp+28h+arg_0]
0x14000746d  mov     rax, r9
0x140007470  mov     rsi, [rsp+28h+arg_8]
0x140007475  add     rsp, 20h
0x140007479  pop     rdi
0x14000747a  retn
```
