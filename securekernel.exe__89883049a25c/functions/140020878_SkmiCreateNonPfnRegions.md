# SkmiCreateNonPfnRegions

- ea: `0x140020878`
- end: `0x140020ae5`
- name: `SkmiCreateNonPfnRegions`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140050fcc`

## callees

- `0x140012ea4`
- `0x140020878`
- `0x1400213f8`
- `0x14002c6f0`
- `0x1400393a4`
- `0x14004c5d4`

## pseudocode

```c
__int64 __fastcall SkmiCreateNonPfnRegions(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rcx
  __int64 InitialNonPfnRegion; // rdi
  __int64 i; // rbx
  __int64 *v6; // rbx
  BOOL v7; // ebp
  unsigned int v8; // eax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rsi
  _QWORD *v11; // rax
  unsigned int v12; // eax
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  _QWORD **v19; // rax
  _QWORD *v20; // rcx
  unsigned __int64 v21; // rax

  v3 = 0;
  SkmiNonPfnRegionTree = 0;
  InitialNonPfnRegion = 0;
  SkmiNonPfnRegionTreeLock = 0;
  for ( i = *(_QWORD *)SkmiMemoryDescriptorListHead; ; i = *v6 )
  {
    v6 = (__int64 *)(i + 0x8000000000LL);
    if ( v6 == (__int64 *)SkmiMemoryDescriptorListHead )
      break;
    v7 = (unsigned int)(*((_DWORD *)v6 + 6) - 38) <= 2;
    if ( !v3 )
      goto LABEL_16;
    if ( (unsigned int)(*((_DWORD *)v6 + 6) - 38) <= 2 && v3 == v6[4] )
    {
LABEL_20:
      v3 = v6[4] + v6[5];
      continue;
    }
    v8 = *(_DWORD *)(InitialNonPfnRegion + 24);
    v9 = v3 >> 18;
    if ( (unsigned int)v9 <= v8 )
      goto LABEL_15;
    LOBYTE(a3) = 0;
    *(_DWORD *)(InitialNonPfnRegion + 28) = v9 - v8;
    v10 = (_QWORD *)SkmiNonPfnRegionTree;
    if ( !SkmiNonPfnRegionTree )
      goto LABEL_14;
    while ( (int)SkmiCompareNonPfnRegionNodes(InitialNonPfnRegion, v10, a3) >= 0 )
    {
      v11 = (_QWORD *)v10[1];
      if ( !v11 )
      {
        LOBYTE(a3) = 1;
        goto LABEL_14;
      }
LABEL_12:
      v10 = v11;
    }
    v11 = (_QWORD *)*v10;
    if ( *v10 )
      goto LABEL_12;
    LOBYTE(a3) = 0;
LABEL_14:
    RtlAvlInsertNodeEx(&SkmiNonPfnRegionTree, v10, a3, InitialNonPfnRegion);
    InitialNonPfnRegion = 0;
LABEL_15:
    v3 = 0;
LABEL_16:
    if ( v7 )
    {
      if ( InitialNonPfnRegion || (InitialNonPfnRegion = SkmiAllocateInitialNonPfnRegion()) != 0 )
      {
        *(_DWORD *)(InitialNonPfnRegion + 24) = (unsigned __int64)(v6[4] + 0x3FFFF) >> 18;
        goto LABEL_20;
      }
      return 0;
    }
  }
  if ( !v3 )
    goto LABEL_32;
  v12 = *(_DWORD *)(InitialNonPfnRegion + 24);
  v13 = v3 >> 18;
  if ( (unsigned int)v13 <= v12 )
    goto LABEL_32;
  LOBYTE(a3) = 0;
  *(_DWORD *)(InitialNonPfnRegion + 28) = v13 - v12;
  v14 = (_QWORD *)SkmiNonPfnRegionTree;
  if ( !SkmiNonPfnRegionTree )
    goto LABEL_31;
  while ( 2 )
  {
    if ( (int)SkmiCompareNonPfnRegionNodes(InitialNonPfnRegion, v14, a3) >= 0 )
    {
      v15 = (_QWORD *)v14[1];
      if ( !v15 )
      {
        LOBYTE(a3) = 1;
        goto LABEL_31;
      }
      goto LABEL_29;
    }
    v15 = (_QWORD *)*v14;
    if ( *v14 )
    {
LABEL_29:
      v14 = v15;
      continue;
    }
    break;
  }
  LOBYTE(a3) = 0;
LABEL_31:
  RtlAvlInsertNodeEx(&SkmiNonPfnRegionTree, v14, a3, InitialNonPfnRegion);
LABEL_32:
  v16 = (_QWORD *)SkmiNonPfnRegionTree;
  v17 = 0;
  while ( v16 )
  {
    v17 = (unsigned __int64)v16;
    v16 = (_QWORD *)*v16;
  }
  if ( v17 )
  {
    if ( !(unsigned int)SkmiAllocateGapFrames(
                          (((unsigned __int64)qword_140156C20 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL,
                          4) )
      return 0;
    while ( v17 )
    {
      if ( (unsigned __int64)*(unsigned int *)(v17 + 24) << 18 > 0xFFFFFFFFFFLL )
        __fastfail(0x3Fu);
      v18 = ((unsigned __int64)*(unsigned int *)(v17 + 24) << 21) - 0x180000000000LL;
      if ( (int)SkmiFillSparseMappingGaps(v18, v18 + ((unsigned __int64)*(unsigned int *)(v17 + 28) << 21), 4) < 0 )
        return 0;
      v19 = *(_QWORD ***)(v17 + 8);
      if ( v19 )
      {
        v20 = *v19;
        if ( *v19 )
        {
          do
          {
            v17 = (unsigned __int64)v20;
            v20 = (_QWORD *)*v20;
          }
          while ( v20 );
        }
        else
        {
          v17 = *(_QWORD *)(v17 + 8);
        }
      }
      else
      {
        do
        {
          v21 = v17;
          v17 = *(_QWORD *)(v17 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        }
        while ( v17 && *(_QWORD *)v17 != v21 );
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140020878  push    rbx
0x14002087a  push    rbp
0x14002087b  push    rsi
0x14002087c  push    rdi
0x14002087d  push    r14
0x14002087f  sub     rsp, 20h
0x140020883  mov     rax, cs:SkmiMemoryDescriptorListHead
0x14002088a  xor     ecx, ecx
0x14002088c  mov     cs:SkmiNonPfnRegionTree, 0
0x140020897  xor     edi, edi
0x140020899  mov     cs:SkmiNonPfnRegionTreeLock, 0
0x1400208a3  mov     r14, 8000000000h
0x1400208ad  mov     rbx, [rax]
0x1400208b0  add     rbx, r14
0x1400208b3  cmp     rbx, cs:SkmiMemoryDescriptorListHead
0x1400208ba  jz      loc_140020984
0x1400208c0  mov     eax, [rbx+18h]
0x1400208c3  xor     ebp, ebp
0x1400208c5  sub     eax, 26h ; '&'
0x1400208c8  cmp     eax, 2
0x1400208cb  setbe   bpl
0x1400208cf  test    rcx, rcx
0x1400208d2  jz      short loc_140020944
0x1400208d4  test    ebp, ebp
0x1400208d6  jz      short loc_1400208E2
0x1400208d8  cmp     rcx, [rbx+20h]
0x1400208dc  jz      loc_140020974
0x1400208e2  mov     eax, [rdi+18h]
0x1400208e5  shr     rcx, 12h
0x1400208e9  cmp     ecx, eax
0x1400208eb  jbe     short loc_140020942
0x1400208ed  sub     ecx, eax
0x1400208ef  xor     r8b, r8b
0x1400208f2  mov     [rdi+1Ch], ecx
0x1400208f5  mov     rsi, cs:SkmiNonPfnRegionTree
0x1400208fc  test    rsi, rsi
0x1400208ff  jz      short loc_14002092E
0x140020901  mov     rdx, rsi
0x140020904  mov     rcx, rdi
0x140020907  call    SkmiCompareNonPfnRegionNodes
0x14002090c  test    eax, eax
0x14002090e  js      short loc_14002091E
0x140020910  mov     rax, [rsi+8]
0x140020914  test    rax, rax
0x140020917  jnz     short loc_140020926
0x140020919  mov     r8b, 1
0x14002091c  jmp     short loc_14002092E
0x14002091e  mov     rax, [rsi]
0x140020921  test    rax, rax
0x140020924  jz      short loc_14002092B
0x140020926  mov     rsi, rax
0x140020929  jmp     short loc_140020901
0x14002092b  xor     r8b, r8b
0x14002092e  mov     r9, rdi
0x140020931  lea     rcx, SkmiNonPfnRegionTree
0x140020938  mov     rdx, rsi
0x14002093b  call    RtlAvlInsertNodeEx
0x140020940  xor     edi, edi
0x140020942  xor     ecx, ecx
0x140020944  test    ebp, ebp
0x140020946  jz      short loc_14002097C
0x140020948  test    rcx, rcx
0x14002094b  jnz     short loc_140020974
0x14002094d  test    rdi, rdi
0x140020950  jnz     short loc_140020963
0x140020952  call    SkmiAllocateInitialNonPfnRegion
0x140020957  mov     rdi, rax
0x14002095a  test    rax, rax
0x14002095d  jz      loc_140020AD0
0x140020963  mov     rax, [rbx+20h]
0x140020967  add     rax, 3FFFFh
0x14002096d  shr     rax, 12h
0x140020971  mov     [rdi+18h], eax
0x140020974  mov     rcx, [rbx+28h]
0x140020978  add     rcx, [rbx+20h]
0x14002097c  mov     rbx, [rbx]
0x14002097f  jmp     loc_1400208B0
0x140020984  test    rcx, rcx
0x140020987  jz      short loc_1400209E7
0x140020989  mov     eax, [rdi+18h]
0x14002098c  shr     rcx, 12h
0x140020990  cmp     ecx, eax
0x140020992  jbe     short loc_1400209E7
0x140020994  sub     ecx, eax
0x140020996  xor     r8b, r8b
0x140020999  mov     [rdi+1Ch], ecx
0x14002099c  mov     rbx, cs:SkmiNonPfnRegionTree
0x1400209a3  test    rbx, rbx
0x1400209a6  jz      short loc_1400209D5
0x1400209a8  mov     rdx, rbx
0x1400209ab  mov     rcx, rdi
0x1400209ae  call    SkmiCompareNonPfnRegionNodes
0x1400209b3  test    eax, eax
0x1400209b5  js      short loc_1400209C5
0x1400209b7  mov     rax, [rbx+8]
0x1400209bb  test    rax, rax
0x1400209be  jnz     short loc_1400209CD
0x1400209c0  mov     r8b, 1
0x1400209c3  jmp     short loc_1400209D5
0x1400209c5  mov     rax, [rbx]
0x1400209c8  test    rax, rax
0x1400209cb  jz      short loc_1400209D2
0x1400209cd  mov     rbx, rax
0x1400209d0  jmp     short loc_1400209A8
0x1400209d2  xor     r8b, r8b
0x1400209d5  mov     r9, rdi
0x1400209d8  lea     rcx, SkmiNonPfnRegionTree
0x1400209df  mov     rdx, rbx
0x1400209e2  call    RtlAvlInsertNodeEx
0x1400209e7  mov     rax, cs:SkmiNonPfnRegionTree
0x1400209ee  xor     ebx, ebx
0x1400209f0  jmp     short loc_1400209F8
0x1400209f2  mov     rbx, rax
0x1400209f5  mov     rax, [rax]
0x1400209f8  test    rax, rax
0x1400209fb  jnz     short loc_1400209F2
0x1400209fd  test    rbx, rbx
0x140020a00  jz      loc_140020AD4
0x140020a06  mov     rcx, cs:qword_140156C20
0x140020a0d  mov     rax, 7FFFFFFFF8h
0x140020a17  shr     rcx, 9
0x140020a1b  and     rcx, rax
0x140020a1e  mov     rax, 0FFFFF68000000000h
0x140020a28  mov     esi, 4
0x140020a2d  add     rcx, rax
0x140020a30  mov     edx, esi
0x140020a32  call    SkmiAllocateGapFrames
0x140020a37  test    eax, eax
0x140020a39  jz      loc_140020AD0
0x140020a3f  mov     rdi, 0FFFFE80000000000h
0x140020a49  test    rbx, rbx
0x140020a4c  jz      loc_140020AD4
0x140020a52  mov     edx, [rbx+18h]
0x140020a55  shl     rdx, 12h
0x140020a59  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x140020a63  mov     rax, rdi
0x140020a66  sub     rcx, rax
0x140020a69  sar     rcx, 3
0x140020a6d  cmp     rdx, rcx
0x140020a70  ja      short loc_140020AC9
0x140020a72  mov     rax, rdi
0x140020a75  lea     rcx, [rax+rdx*8]
0x140020a79  mov     r8d, esi
0x140020a7c  mov     edx, [rbx+1Ch]
0x140020a7f  shl     rdx, 15h
0x140020a83  add     rdx, rcx
0x140020a86  call    SkmiFillSparseMappingGaps
0x140020a8b  test    eax, eax
0x140020a8d  js      short loc_140020AD0
0x140020a8f  mov     rax, [rbx+8]
0x140020a93  test    rax, rax
0x140020a96  jz      short loc_140020ABA
0x140020a98  mov     rcx, [rax]
0x140020a9b  test    rcx, rcx
0x140020a9e  jz      short loc_140020AB0
0x140020aa0  mov     rax, [rcx]
0x140020aa3  mov     rbx, rcx
0x140020aa6  mov     rcx, rax
0x140020aa9  test    rax, rax
0x140020aac  jnz     short loc_140020AA0
0x140020aae  jmp     short loc_140020A49
0x140020ab0  mov     rbx, rax
0x140020ab3  jmp     short loc_140020A49
0x140020ab5  cmp     [rbx], rax
0x140020ab8  jz      short loc_140020A49
0x140020aba  mov     rax, rbx
0x140020abd  mov     rbx, [rbx+10h]
0x140020ac1  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140020ac5  jnz     short loc_140020AB5
0x140020ac7  jmp     short loc_140020A49
0x140020ac9  mov     ecx, 3Fh ; '?'
0x140020ace  int     29h; Win8: RtlFailFast(ecx)
0x140020ad0  xor     eax, eax
0x140020ad2  jmp     short loc_140020AD9
0x140020ad4  mov     eax, 1
0x140020ad9  add     rsp, 20h
0x140020add  pop     r14
0x140020adf  pop     rdi
0x140020ae0  pop     rsi
0x140020ae1  pop     rbp
0x140020ae2  pop     rbx
0x140020ae3  retn
```
