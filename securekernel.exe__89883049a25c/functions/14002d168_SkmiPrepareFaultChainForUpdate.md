# SkmiPrepareFaultChainForUpdate

- ea: `0x14002d168`
- end: `0x14002d84e`
- name: `SkmiPrepareFaultChainForUpdate`
- size: `1766`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002a04`
- `0x140072884`
- `0x140072fc4`

## callees

- `0x140002410`
- `0x140003780`
- `0x140009890`
- `0x140011780`
- `0x140014c80`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020424`
- `0x14002b534`
- `0x14002d168`
- `0x14002f3f8`
- `0x140030f10`
- `0x14003a9c0`
- `0x140066168`
- `0x1400802ac`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiPrepareFaultChainForUpdate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r10
  int v9; // r14d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 v14; // r11
  unsigned __int64 v15; // r15
  signed __int64 v16; // rbx
  unsigned __int64 v17; // rdi
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 PteTrace; // rax
  __int64 v23; // r11
  __int64 v24; // r9
  __int64 v25; // rsi
  PVOID *v26; // rdi
  PVOID StackBase; // rcx
  USHORT v28; // ax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // edx
  __int64 v36; // rcx
  signed __int64 v37; // rsi
  int v38; // r9d
  int v39; // eax
  __int64 v40; // r10
  unsigned __int64 v41; // r9
  __int64 v42; // r13
  __int64 DataTraceEntry; // rcx
  signed __int64 v44; // r9
  __int64 v45; // r10
  signed __int64 v46; // rax
  __int64 v47; // rax
  PVOID *v48; // rbx
  PVOID v49; // rcx
  USHORT v50; // ax
  __int64 v51; // rcx
  __int64 InstructionPointer; // rax
  __int64 *v53; // rax
  __int64 v54; // rax
  __int64 v55; // rsi
  PVOID *v56; // rbx
  PVOID v57; // rcx
  USHORT v58; // ax
  __int64 v59; // rcx
  _QWORD *v60; // rax
  __int64 v61; // rcx
  int v62; // ecx
  unsigned int v64; // r15d
  __int64 *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rsi
  PVOID *v68; // rdi
  PVOID v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  _QWORD *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rdx
  int v75; // ecx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v77; // [rsp+38h] [rbp-8h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+38h]

  if ( (unsigned int)SkmiIsLeafPteValid(a2) )
  {
    v9 = 2;
    *(_QWORD *)BackTraceHash = (v8 - SkmiState) << 16;
    SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v6, v7, 0);
    v15 = *(_QWORD *)BackTraceHash & 0xFFFFFFFFFFFFBFFFuLL;
    while ( 1 )
    {
LABEL_3:
      *(_QWORD *)(v13 + 8) = v13;
      *(_QWORD *)v13 = v13;
      v16 = *(_QWORD *)a2;
      *(_QWORD *)BackTraceHash = v16;
      if ( !v16 )
        return 3221225477LL;
      v17 = v16;
      while ( 1 )
      {
        if ( (v17 & 1) != 0 )
        {
          if ( a5 == (_DWORD)v12 )
          {
            SKMI_PAGE_SECURITY(256, a4, a2, BackTraceHash);
            return 3221225506LL;
          }
          if ( (v9 & 1) == 0 )
          {
            SkAcquireSpinLockExclusiveAtDpcLevel(v14 + 192);
            v13 = a3;
            v9 |= 1u;
            v14 = a1;
            v12 = 0;
            goto LABEL_3;
          }
          ++*(_QWORD *)(v14 + 200);
          v18 = (v17 >> 5) & 1;
          *(_QWORD *)BackTraceHash = v17 & 0xFFFFFFFFFF000LL
                                   | (v17 >> 45) & 0x400
                                   | (32 * (SKMI_GET_PROTECTION_FROM_VALID_PTE(BackTraceHash, v10, v11) & 0x1F))
                                   | 0x802;
          SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v19, v20, v21);
          v16 = *(_QWORD *)BackTraceHash;
          PteTrace = SkmiGetPteTrace(0, a2, 0, BackTraceHash[0], *(_QWORD *)a2);
          v24 = 0;
          v25 = PteTrace;
          if ( PteTrace )
          {
            v26 = (PVOID *)(PteTrace + 32);
            memset_0((void *)(PteTrace + 32), 0, 0x40u);
            v24 = 0;
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              StackBase = KeGetPcr()->NtTib.StackBase;
              if ( StackBase )
              {
                v28 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v26, BackTraceHash);
                v24 = 0;
                if ( !v28 )
                {
                  *(_QWORD *)(v25 + 40) = retaddr;
                  *v26 = (PVOID)SkmiGetInstructionPointer(v30, v29);
                }
              }
            }
            v23 = a1;
          }
          v31 = v16;
          if ( (unsigned __int64)a2 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a2 < 0xFFFFF6FB7DBED800uLL )
          {
            v32 = KeGetPcr()->NtTib.StackBase;
            v33 = v32 ? v32[10] : v24;
            v34 = *(_QWORD *)(v33 + 232);
            if ( v34 )
            {
              v35 = SkiKvaShadowMode;
              *(_QWORD *)(v34 + 8 * ((a2 >> 3) & 0x1FF)) = v16;
              if ( v35 != 2 && (v16 & 1) != 0 )
                v31 = v16 | 0x8000000000000000uLL;
            }
          }
          *(_QWORD *)a2 = v31;
          v36 = a2 << 25 >> 16;
          *(_QWORD *)BackTraceHash = v36;
          LOBYTE(v36) = -1;
          SkeFlushRangeListTb(v36, v23, 1, BackTraceHash);
          v9 &= ~2u;
          if ( (v16 & 0x400) != 0 )
          {
            SkmiInvalidateVadPages(a1, a2, a2);
            v16 = *(_QWORD *)a2;
          }
          v14 = a1;
          v12 = 0;
        }
        else
        {
          v18 = v12;
        }
        if ( (v9 & 1) != 0 )
        {
          *(_DWORD *)(v14 + 192) = v12;
          SkTrackSpinLockRelease();
          v9 &= ~1u;
          v12 = 0;
        }
        v15 = (v18 << 14) | v15 & 0xFFFFFFFFFFFFBFFFuLL;
        v37 = v16;
        if ( !v16 || (v16 & 2) != 0 )
        {
          v40 = a3;
          v39 = 1;
          v42 = a3;
          v41 = v15;
          *(_QWORD *)(a3 + 16) = v16;
        }
        else
        {
          if ( (v16 & 0x8000) != 0 )
          {
            _mm_pause();
            v13 = a3;
            goto LABEL_67;
          }
          *(_QWORD *)BackTraceHash = v16;
          SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash);
          v39 = v38;
          v40 = a3;
          v41 = v16;
          v42 = SkmiState + (*(__int64 *)BackTraceHash >> 16);
        }
        *(_DWORD *)(v40 + 32) = v39;
        DataTraceEntry = SkmiAllocateDataTraceEntry(0, a2, v11, v41 | 0x8000);
        v46 = _InterlockedCompareExchange64((volatile signed __int64 *)a2, v44, v16);
        v17 = v46;
        if ( DataTraceEntry )
        {
          if ( v46 == v16 )
            break;
        }
        v12 = 0;
LABEL_42:
        v16 = v17;
        *(_QWORD *)BackTraceHash = v17;
        if ( v17 == v37 )
          goto LABEL_47;
        v14 = a1;
      }
      v47 = SkmiGetPteTrace(DataTraceEntry, a2, 0, v44, v16);
      v12 = 0;
      v77 = v47;
      if ( !v47 )
        goto LABEL_42;
      v48 = (PVOID *)(v47 + 32);
      memset_0((void *)(v47 + 32), 0, 0x40u);
      v12 = 0;
      if ( (SkmiFlags & 0x400000) == 0 )
        break;
      v49 = KeGetPcr()->NtTib.StackBase;
      if ( !v49 )
        break;
      v50 = RtlCaptureStackBackTrace((ULONG)v49, 8u, v48, BackTraceHash);
      v12 = 0;
      if ( v50 )
        break;
      v51 = v77;
      *(_QWORD *)(v77 + 40) = retaddr;
      InstructionPointer = SkmiGetInstructionPointer(v51, v10);
      v45 = a3;
      *v48 = (PVOID)InstructionPointer;
      v16 = v17;
LABEL_47:
      if ( v42 == v45 || (*(_DWORD *)(v42 + 32) & 1) == 0 )
      {
        if ( (*(_QWORD *)(v42 + 16) & 0x800LL) == 0
          || (*(_QWORD *)BackTraceHash = *(_QWORD *)(v42 + 16),
              SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash),
              ((*(_QWORD *)BackTraceHash >> 12) & 0xFFFFFFFFFFLL) == a4) )
        {
          if ( v42 == v45 )
          {
            v16 = v15;
          }
          else
          {
            v65 = *(__int64 **)(v42 + 8);
            if ( *v65 != v42 )
LABEL_74:
              __fastfail(3u);
            *(_QWORD *)v45 = v42;
            *(_QWORD *)(v45 + 8) = v65;
            *v65 = v45;
            *(_QWORD *)(v42 + 8) = v45;
            v16 = SkmiMoveToHeadOfFaultChain(v45, v42);
          }
          *(_DWORD *)(v45 + 32) |= 1u;
          v64 = v12;
        }
        else
        {
          v64 = -1073741800;
          LOBYTE(v9) = -3;
        }
        v66 = SkmiGetPteTrace(0, a2, 0, v16, *(_QWORD *)a2);
        v67 = v66;
        if ( v66 )
        {
          v68 = (PVOID *)(v66 + 32);
          memset_0((void *)(v66 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v69 = KeGetPcr()->NtTib.StackBase;
            if ( v69 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v69, 8u, v68, BackTraceHash) )
              {
                *(_QWORD *)(v67 + 40) = retaddr;
                *v68 = (PVOID)SkmiGetInstructionPointer(v71, v70);
              }
            }
          }
        }
        if ( (unsigned __int64)a2 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a2 < 0xFFFFF6FB7DBED800uLL )
        {
          v72 = KeGetPcr()->NtTib.StackBase;
          v73 = v72 ? v72[10] : 0LL;
          v74 = *(_QWORD *)(v73 + 232);
          if ( v74 )
          {
            v75 = SkiKvaShadowMode;
            *(_QWORD *)(v74 + 8 * ((a2 >> 3) & 0x1FF)) = v16;
            if ( v75 != 2 && (v16 & 1) != 0 )
              v16 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)a2 = v16;
        if ( (v9 & 2) != 0 )
        {
          SkAcquireSpinLockSharedAtDpcLevel(a1 + 192);
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 192));
          SkTrackSpinLockRelease();
        }
        return v64;
      }
      v53 = *(__int64 **)(v42 + 8);
      if ( *v53 != v42 )
        goto LABEL_74;
      *(_QWORD *)v45 = v42;
      *(_QWORD *)(v45 + 8) = v53;
      *v53 = v45;
      *(_QWORD *)(v42 + 8) = v45;
      v54 = SkmiGetPteTrace(0, a2, 0, v17, *(_QWORD *)a2);
      v12 = 0;
      v55 = v54;
      if ( v54 )
      {
        v56 = (PVOID *)(v54 + 32);
        memset_0((void *)(v54 + 32), 0, 0x40u);
        v12 = 0;
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v57 = KeGetPcr()->NtTib.StackBase;
          if ( v57 )
          {
            v58 = RtlCaptureStackBackTrace((ULONG)v57, 8u, v56, BackTraceHash);
            v12 = 0;
            if ( !v58 )
            {
              *(_QWORD *)(v55 + 40) = retaddr;
              *v56 = (PVOID)SkmiGetInstructionPointer(v59, v10);
            }
          }
        }
        v13 = a3;
      }
      if ( (unsigned __int64)a2 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a2 < 0xFFFFF6FB7DBED800uLL )
      {
        v60 = KeGetPcr()->NtTib.StackBase;
        if ( v60 )
          v61 = v60[10];
        else
          v61 = v12;
        v10 = *(_QWORD *)(v61 + 232);
        if ( v10 )
        {
          v62 = SkiKvaShadowMode;
          *(_QWORD *)(v10 + 8 * ((a2 >> 3) & 0x1FF)) = v17;
          if ( v62 != 2 && (v17 & 1) != 0 )
            v17 |= 0x8000000000000000uLL;
        }
      }
      v14 = a1;
      *(_QWORD *)a2 = v17;
      if ( !*(_DWORD *)(v13 + 32) )
      {
        do
          _mm_pause();
        while ( !*(_DWORD *)(v13 + 32) );
LABEL_67:
        v14 = a1;
      }
    }
    v45 = a3;
    goto LABEL_42;
  }
  return 3221225477LL;
}

```

## disassembly

```asm
0x14002d168  mov     rax, rsp
0x14002d16b  mov     [rax+10h], rbx
0x14002d16f  mov     [rax+20h], r9
0x14002d173  mov     [rax+18h], r8
0x14002d177  mov     [rax+8], rcx
0x14002d17b  push    rbp
0x14002d17c  push    rsi
0x14002d17d  push    rdi
0x14002d17e  push    r12
0x14002d180  push    r13
0x14002d182  push    r14
0x14002d184  push    r15
0x14002d186  mov     rbp, rsp
0x14002d189  sub     rsp, 40h
0x14002d18d  mov     r11, rcx
0x14002d190  mov     r10, r8
0x14002d193  mov     rcx, rdx
0x14002d196  mov     r12, rdx
0x14002d199  call    SkmiIsLeafPteValid
0x14002d19e  xor     r9d, r9d
0x14002d1a1  test    eax, eax
0x14002d1a3  jz      loc_14002D830
0x14002d1a9  mov     rax, r10
0x14002d1ac  lea     rcx, [rbp+BackTraceHash]
0x14002d1b0  sub     rax, cs:SkmiState
0x14002d1b7  lea     r14d, [r9+2]
0x14002d1bb  shl     rax, 10h
0x14002d1bf  mov     qword ptr [rbp+BackTraceHash], rax
0x14002d1c3  call    SKMI_SWIZZLE_INVALID_PTE
0x14002d1c8  mov     r15, qword ptr [rbp+BackTraceHash]
0x14002d1cc  btr     r15, 0Eh
0x14002d1d1  mov     [r10+8], r10
0x14002d1d5  mov     [r10], r10
0x14002d1d8  mov     rbx, [r12]
0x14002d1dc  mov     qword ptr [rbp+BackTraceHash], rbx
0x14002d1e0  test    rbx, rbx
0x14002d1e3  jz      loc_14002D830
0x14002d1e9  mov     rdi, rbx
0x14002d1ec  test    dil, 1
0x14002d1f0  jz      loc_14002D3C2
0x14002d1f6  cmp     [rbp+arg_20], r9d
0x14002d1fa  jz      loc_14002D67E
0x14002d200  test    r14b, 1
0x14002d204  jz      loc_14002D4EC
0x14002d20a  inc     qword ptr [r11+0C8h]
0x14002d211  lea     rcx, [rbp+BackTraceHash]
0x14002d215  mov     r13, rdi
0x14002d218  shr     r13, 5
0x14002d21c  and     r13d, 1
0x14002d220  call    SKMI_GET_PROTECTION_FROM_VALID_PTE
0x14002d225  and     eax, 1Fh
0x14002d228  mov     rcx, rdi
0x14002d22b  shr     rcx, 2Dh
0x14002d22f  and     ecx, 400h
0x14002d235  shl     rax, 5
0x14002d239  or      rax, rcx
0x14002d23c  mov     rcx, 0FFFFFFFFFF000h
0x14002d246  and     rdi, rcx
0x14002d249  lea     rcx, [rbp+BackTraceHash]
0x14002d24d  or      rax, rdi
0x14002d250  or      rax, 802h
0x14002d256  mov     qword ptr [rbp+BackTraceHash], rax
0x14002d25a  call    SKMI_SWIZZLE_INVALID_PTE
0x14002d25f  mov     r9, qword ptr [rbp+BackTraceHash]
0x14002d263  xor     r8d, r8d
0x14002d266  mov     rax, [r12]
0x14002d26a  mov     rdx, r12
0x14002d26d  mov     qword ptr [rbp+BackTraceHash], r9
0x14002d271  xor     ecx, ecx
0x14002d273  mov     rbx, qword ptr [rbp+BackTraceHash]
0x14002d277  mov     r9, rbx
0x14002d27a  mov     [rsp+40h+var_20], rax
0x14002d27f  call    SkmiGetPteTrace
0x14002d284  xor     r9d, r9d
0x14002d287  mov     rsi, rax
0x14002d28a  test    rax, rax
0x14002d28d  jz      short loc_14002D2EB
0x14002d28f  lea     rdi, [rax+20h]
0x14002d293  xor     edx, edx; Val
0x14002d295  mov     rcx, rdi; void *
0x14002d298  lea     r8d, [r9+40h]; Size
0x14002d29c  call    memset_0
0x14002d2a1  xor     r9d, r9d
0x14002d2a4  test    cs:SkmiFlags, 400000h
0x14002d2ae  jz      short loc_14002D2E7
0x14002d2b0  mov     rcx, gs:8; FramesToSkip
0x14002d2b9  test    rcx, rcx
0x14002d2bc  jz      short loc_14002D2E7
0x14002d2be  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14002d2c2  mov     r8, rdi; BackTrace
0x14002d2c5  mov     edx, 8; FramesToCapture
0x14002d2ca  call    RtlCaptureStackBackTrace
0x14002d2cf  xor     r9d, r9d
0x14002d2d2  test    ax, ax
0x14002d2d5  jnz     short loc_14002D2E7
0x14002d2d7  mov     rax, [rbp+38h]
0x14002d2db  mov     [rsi+28h], rax
0x14002d2df  call    SkmiGetInstructionPointer
0x14002d2e4  mov     [rdi], rax
0x14002d2e7  mov     r11, [rbp+arg_0]
0x14002d2eb  mov     rax, rbx
0x14002d2ee  mov     rcx, 0FFFFF6FB7DBED000h
0x14002d2f8  mov     rcx, rcx
0x14002d2fb  cmp     r12, rcx
0x14002d2fe  jb      short loc_14002D363
0x14002d300  mov     rcx, 0FFFFF6FB7DBED800h
0x14002d30a  mov     rcx, rcx
0x14002d30d  cmp     r12, rcx
0x14002d310  jnb     short loc_14002D363
0x14002d312  mov     rcx, gs:8
0x14002d31b  test    rcx, rcx
0x14002d31e  jz      short loc_14002D326
0x14002d320  mov     rdx, [rcx+50h]
0x14002d324  jmp     short loc_14002D329
0x14002d326  mov     rdx, r9
0x14002d329  mov     r8, [rdx+0E8h]
0x14002d330  test    r8, r8
0x14002d333  jz      short loc_14002D363
0x14002d335  mov     edx, cs:SkiKvaShadowMode
0x14002d33b  mov     rcx, r12
0x14002d33e  sar     rcx, 3
0x14002d342  and     ecx, 1FFh
0x14002d348  mov     [r8+rcx*8], rbx
0x14002d34c  cmp     edx, 2
0x14002d34f  jz      short loc_14002D363
0x14002d351  test    bl, 1
0x14002d354  jz      short loc_14002D363
0x14002d356  mov     rcx, 8000000000000000h
0x14002d360  or      rax, rcx
0x14002d363  mov     rcx, r12
0x14002d366  mov     [r12], rax
0x14002d36a  shl     rcx, 19h
0x14002d36e  mov     rax, 0FFFFF68000000000h
0x14002d378  shl     rax, 19h
0x14002d37c  lea     r9, [rbp+BackTraceHash]
0x14002d380  sub     rcx, rax
0x14002d383  mov     r8d, 1
0x14002d389  sar     rcx, 10h
0x14002d38d  mov     rdx, r11
0x14002d390  mov     qword ptr [rbp+BackTraceHash], rcx
0x14002d394  mov     cl, 0FFh
0x14002d396  call    SkeFlushRangeListTb
0x14002d39b  and     r14d, 0FFFFFFFDh
0x14002d39f  bt      rbx, 0Ah
0x14002d3a4  jnb     short loc_14002D3B9
0x14002d3a6  mov     rcx, [rbp+arg_0]
0x14002d3aa  mov     r8, r12
0x14002d3ad  mov     rdx, r12
0x14002d3b0  call    SkmiInvalidateVadPages
0x14002d3b5  mov     rbx, [r12]
0x14002d3b9  mov     r11, [rbp+arg_0]
0x14002d3bd  xor     r9d, r9d
0x14002d3c0  jmp     short loc_14002D3C5
0x14002d3c2  mov     r13, r9
0x14002d3c5  test    r14b, 1
0x14002d3c9  jz      short loc_14002D3DE
0x14002d3cb  mov     [r11+0C0h], r9d
0x14002d3d2  call    SkTrackSpinLockRelease
0x14002d3d7  and     r14d, 0FFFFFFFEh
0x14002d3db  xor     r9d, r9d
0x14002d3de  btr     r15, 0Eh
0x14002d3e3  shl     r13, 0Eh
0x14002d3e7  or      r15, r13
0x14002d3ea  mov     rsi, rbx
0x14002d3ed  test    rbx, rbx
0x14002d3f0  jz      short loc_14002D42B
0x14002d3f2  test    sil, 2
0x14002d3f6  jnz     short loc_14002D42B
0x14002d3f8  bt      rbx, 0Fh
0x14002d3fd  jb      loc_14002D50C
0x14002d403  lea     rcx, [rbp+BackTraceHash]
0x14002d407  mov     qword ptr [rbp+BackTraceHash], rbx
0x14002d40b  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14002d410  mov     r13, qword ptr [rbp+BackTraceHash]
0x14002d414  mov     eax, r9d
0x14002d417  mov     r10, [rbp+arg_10]
0x14002d41b  mov     r9, rbx
0x14002d41e  sar     r13, 10h
0x14002d422  add     r13, cs:SkmiState
0x14002d429  jmp     short loc_14002D43E
0x14002d42b  mov     r10, [rbp+arg_10]
0x14002d42f  mov     eax, 1
0x14002d434  mov     r13, r10
0x14002d437  mov     r9, r15
0x14002d43a  mov     [r10+10h], rbx
0x14002d43e  bts     r9, 0Fh
0x14002d443  mov     [r10+20h], eax
0x14002d447  mov     rdx, r12
0x14002d44a  xor     ecx, ecx
0x14002d44c  call    SkmiAllocateDataTraceEntry
0x14002d451  mov     rcx, rax
0x14002d454  mov     rax, rsi
0x14002d457  lock cmpxchg [r12], r9
0x14002d45d  mov     rdi, rax
0x14002d460  test    rcx, rcx
0x14002d463  jz      short loc_14002D4D4
0x14002d465  cmp     rax, rsi
0x14002d468  jnz     short loc_14002D4D4
0x14002d46a  xor     r8d, r8d
0x14002d46d  mov     [rsp+40h+var_20], rsi
0x14002d472  mov     rdx, r12
0x14002d475  call    SkmiGetPteTrace
0x14002d47a  xor     r9d, r9d
0x14002d47d  mov     [rbp+var_8], rax
0x14002d481  test    rax, rax
0x14002d484  jz      short loc_14002D4D7
0x14002d486  lea     rbx, [rax+20h]
0x14002d48a  xor     edx, edx; Val
0x14002d48c  mov     rcx, rbx; void *
0x14002d48f  lea     r8d, [r9+40h]; Size
0x14002d493  call    memset_0
0x14002d498  xor     r9d, r9d
0x14002d49b  test    cs:SkmiFlags, 400000h
0x14002d4a5  jz      short loc_14002D4CE
0x14002d4a7  mov     rcx, gs:8; FramesToSkip
0x14002d4b0  test    rcx, rcx
0x14002d4b3  jz      short loc_14002D4CE
0x14002d4b5  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14002d4b9  mov     r8, rbx; BackTrace
0x14002d4bc  mov     edx, 8; FramesToCapture
0x14002d4c1  call    RtlCaptureStackBackTrace
0x14002d4c6  xor     r9d, r9d
0x14002d4c9  test    ax, ax
0x14002d4cc  jz      short loc_14002D517
0x14002d4ce  mov     r10, [rbp+arg_10]
0x14002d4d2  jmp     short loc_14002D4D7
0x14002d4d4  xor     r9d, r9d
0x14002d4d7  mov     rbx, rdi
0x14002d4da  mov     qword ptr [rbp+BackTraceHash], rbx
0x14002d4de  cmp     rdi, rsi
0x14002d4e1  jz      short loc_14002D532
0x14002d4e3  mov     r11, [rbp+arg_0]
0x14002d4e7  jmp     loc_14002D1EC
0x14002d4ec  lea     rcx, [r11+0C0h]
0x14002d4f3  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14002d4f8  mov     r10, [rbp+arg_10]
0x14002d4fc  or      r14d, 1
0x14002d500  mov     r11, [rbp+arg_0]
0x14002d504  xor     r9d, r9d
0x14002d507  jmp     loc_14002D1D1
0x14002d50c  pause
0x14002d50e  mov     r10, [rbp+arg_10]
0x14002d512  jmp     loc_14002D675
0x14002d517  mov     rax, [rbp+38h]
0x14002d51b  mov     rcx, [rbp+var_8]
0x14002d51f  mov     [rcx+28h], rax
0x14002d523  call    SkmiGetInstructionPointer
0x14002d528  mov     r10, [rbp+arg_10]
0x14002d52c  mov     [rbx], rax
0x14002d52f  mov     rbx, rdi
0x14002d532  cmp     r13, r10
0x14002d535  jz      loc_14002D69D
0x14002d53b  mov     eax, [r13+20h]
0x14002d53f  test    al, 1
0x14002d541  jz      loc_14002D69D
0x14002d547  mov     rax, [r13+8]
0x14002d54b  cmp     [rax], r13
0x14002d54e  jnz     loc_14002D6EC
0x14002d554  mov     [r10], r13
0x14002d557  mov     r9, rdi
0x14002d55a  mov     [r10+8], rax
0x14002d55e  xor     r8d, r8d
0x14002d561  mov     [rax], r10
0x14002d564  mov     rdx, r12
0x14002d567  mov     [r13+8], r10
0x14002d56b  xor     ecx, ecx
0x14002d56d  mov     rax, [r12]
0x14002d571  mov     [rsp+40h+var_20], rax
0x14002d576  call    SkmiGetPteTrace
0x14002d57b  xor     r9d, r9d
0x14002d57e  mov     rsi, rax
0x14002d581  test    rax, rax
0x14002d584  jz      short loc_14002D5E2
0x14002d586  lea     rbx, [rax+20h]
0x14002d58a  xor     edx, edx; Val
0x14002d58c  mov     rcx, rbx; void *
0x14002d58f  lea     r8d, [r9+40h]; Size
0x14002d593  call    memset_0
0x14002d598  xor     r9d, r9d
0x14002d59b  test    cs:SkmiFlags, 400000h
0x14002d5a5  jz      short loc_14002D5DE
0x14002d5a7  mov     rcx, gs:8; FramesToSkip
0x14002d5b0  test    rcx, rcx
0x14002d5b3  jz      short loc_14002D5DE
0x14002d5b5  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14002d5b9  mov     r8, rbx; BackTrace
0x14002d5bc  mov     edx, 8; FramesToCapture
0x14002d5c1  call    RtlCaptureStackBackTrace
0x14002d5c6  xor     r9d, r9d
0x14002d5c9  test    ax, ax
0x14002d5cc  jnz     short loc_14002D5DE
0x14002d5ce  mov     rax, [rbp+38h]
0x14002d5d2  mov     [rsi+28h], rax
0x14002d5d6  call    SkmiGetInstructionPointer
0x14002d5db  mov     [rbx], rax
0x14002d5de  mov     r10, [rbp+arg_10]
0x14002d5e2  mov     rax, 0FFFFF6FB7DBED000h
0x14002d5ec  mov     rax, rax
0x14002d5ef  cmp     r12, rax
0x14002d5f2  jb      short loc_14002D657
  ... truncated ...
```
