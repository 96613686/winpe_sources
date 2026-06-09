# SkmiCopyKernelImagePage

- ea: `0x1400720b8`
- end: `0x14007258d`
- name: `SkmiCopyKernelImagePage`
- size: `1237`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400111d0`

## callees

- `0x140002ef0`
- `0x140003780`
- `0x14000b980`
- `0x14000e130`
- `0x14000e410`
- `0x14000e810`
- `0x14000ff70`
- `0x140010b90`
- `0x1400130a0`
- `0x140013bf8`
- `0x140014c80`
- `0x140014d64`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020424`
- `0x14002b534`
- `0x140050ba4`
- `0x14005fc00`
- `0x140060370`
- `0x1400720b8`
- `0x14007357c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyKernelImagePage(
        ULONG_PTR a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        ULONG_PTR a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // rbx
  int v11; // edi
  char v12; // al
  __int64 v13; // r13
  char v14; // r14
  __int64 v15; // rdx
  unsigned int v16; // r12d
  int v17; // ecx
  volatile signed __int64 *ValidNteAddress; // rax
  __int64 v19; // r8
  volatile signed __int64 *v20; // rsi
  unsigned __int64 v21; // r14
  __int64 v22; // rcx
  bool v23; // zf
  signed __int64 v24; // rax
  unsigned int v25; // eax
  __int64 Nar; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r10
  unsigned __int64 v35; // r14
  __int64 v36; // r14
  __int64 PteTrace; // rax
  PVOID StackBase; // rcx
  __int64 v39; // r12
  PVOID *v40; // r15
  __int64 v41; // rdx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v43; // [rsp+38h] [rbp-18h]
  __int64 v44; // [rsp+40h] [rbp-10h] BYREF
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+38h]

  v6 = a5;
  *(_QWORD *)BackTraceHash = 0;
  if ( a5 )
  {
    a5 >>= 12;
    if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&a5, 1, 0x8001u) )
    {
      SKMI_PAGE_SECURITY(323, v6 >> 12, 0, 0);
      return 3221225539LL;
    }
  }
  v11 = SkobReferenceObjectByHandle(a2, 0, 1, (__int64)&SkmiImageType, BackTraceHash, 0);
  if ( v11 >= 0 )
  {
    v12 = SkAcquireSpinLockShared(&SkmiNteLock);
    v13 = *(_QWORD *)BackTraceHash;
    v14 = v12;
    LOBYTE(a5) = v12;
    if ( a3 >= *(unsigned int *)(*(_QWORD *)BackTraceHash + 4LL) )
    {
      SKMI_IMAGE_SECURITY(290, 0, BackTraceHash[0], a3, 0);
      v11 = -1073741800;
LABEL_71:
      if ( v14 != -1 )
      {
        LOBYTE(v15) = v14;
        RtlpReleasePropStoreLockShared(&SkmiNteLock, v15);
      }
      SkobDereferenceObject(v13);
      goto LABEL_74;
    }
    _mm_lfence();
    v16 = (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)BackTraceHash + 8LL) + 8 * a3) >> 5) & 0x1F;
    if ( !v16 )
    {
      v17 = 291;
LABEL_9:
      SKMI_IMAGE_SECURITY(v17, 0, BackTraceHash[0], a3, 0);
      v11 = -1073741819;
      goto LABEL_71;
    }
    if ( ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)BackTraceHash + 8LL) + 8 * a3) >> 5) & 4) != 0 )
    {
      if ( ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)BackTraceHash + 8LL) + 8 * a3) >> 5) & 2) == 0 )
      {
        v17 = 292;
        goto LABEL_9;
      }
      v16 = 3;
    }
    v11 = SkmiLockImageShared(*(_QWORD *)BackTraceHash);
    if ( v11 >= 0 )
    {
      ValidNteAddress = (volatile signed __int64 *)SkmiGetValidNteAddress(a6, v15, 0);
      v20 = ValidNteAddress;
      if ( ValidNteAddress )
      {
        _m_prefetchw((const void *)ValidNteAddress);
LABEL_18:
        v21 = *v20;
        *(_QWORD *)BackTraceHash = *v20;
        do
        {
          if ( (v21 & 0x200) == 0 )
          {
            v22 = 289;
LABEL_68:
            SKMI_PAGE_SECURITY(v22, a4, v20, BackTraceHash);
            v11 = -1073741819;
            goto LABEL_69;
          }
          if ( (v21 & 0x801) == 1 || (v21 & 0x100) != 0 )
          {
            if ( (v21 & 0x400) != 0 )
            {
              _mm_pause();
              goto LABEL_18;
            }
            if ( (v21 & 0x400000000000000LL) == 0 )
            {
              v22 = 299;
              goto LABEL_68;
            }
            if ( (v21 & 0x901) == 0x100 )
            {
              v22 = 297;
              goto LABEL_68;
            }
            if ( !v6 )
            {
              v22 = 298;
              goto LABEL_68;
            }
          }
          else
          {
            if ( (v21 & 0x400) != 0 )
            {
              v22 = 293;
              goto LABEL_68;
            }
            if ( (v21 & 0x400000000000000LL) == 0 || ((v21 >> 16) & 0xFFFFF) != a3 )
            {
              v22 = 294;
              goto LABEL_68;
            }
          }
          v24 = _InterlockedCompareExchange64(v20, v21 | 0x400, v21);
          v23 = v21 == v24;
          v21 = v24;
          *(_QWORD *)BackTraceHash = v24;
        }
        while ( !v23 );
        v25 = v24 & 0x800;
        v44 = v25;
        if ( !v25 && (v21 & 1) != 0 || (v21 & 0x100) != 0 )
        {
          SkAcquireSpinLockSharedAtDpcLevel(&SkmiNarSpinLock);
          Nar = SkmiLocateNar(a6);
          _InterlockedDecrement(&SkmiNarSpinLock);
          v43 = Nar;
          SkTrackSpinLockRelease();
          v27 = v43;
          v28 = (unsigned __int64)(a6 - *(_QWORD *)(v43 + 24)) >> 12;
        }
        else
        {
          v27 = *(_QWORD *)(SkmiNarTable + 8LL * (unsigned __int16)(v21 >> 36));
          v28 = (v21 >> 16) & 0xFFFFF;
        }
        if ( v13 != *(_QWORD *)(v27 + 48) )
        {
          v29 = 295;
          goto LABEL_40;
        }
        if ( (unsigned int)v28 != a3 )
        {
          v29 = 300;
LABEL_40:
          SKMI_PAGE_SECURITY(v29, a4, v20, BackTraceHash);
          v11 = -1073741819;
LABEL_41:
          _InterlockedAnd64(v20, 0xFFFFFFFFFFFFFBFFuLL);
          goto LABEL_69;
        }
        v11 = SkmiCopyOnWrite(v13, a3, a1, 0, a4, *(_QWORD *)(v27 + 24));
        if ( v11 < 0 )
          goto LABEL_41;
        SkmiAcquireNteAssertionLock(v30, v15, v31, v32);
        if ( v6 )
        {
          SkmiUpdateNormalPte(v6, v33, a4);
          v34 = 0;
        }
        if ( (SkmiFlags & 0x800000) == 0 || v44 == v34 && (v21 & 1) != 0 || (v21 & 0x100) != 0 )
          v35 = (a4 << 12) ^ (SkmiProtectionToPte[v16] ^ (a4 << 12)) & 0xFFF0000000000FFFuLL;
        else
          v35 = ((a4 & 0xFFFFFFFFFFLL | ((unsigned __int64)v16 << 47)) << 12) | 0x100;
        v36 = v35 | 0x200;
        PteTrace = SkmiGetPteTrace(0, (_DWORD)v20, 0, v36, *v20);
        v39 = PteTrace;
        if ( PteTrace )
        {
          v40 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v40, BackTraceHash) )
              {
                *(_QWORD *)(v39 + 40) = retaddr;
                *v40 = (PVOID)SkmiGetInstructionPointer(StackBase, v41);
              }
            }
          }
        }
        LOBYTE(StackBase) = 2;
        *v20 = v36;
        SkmiReleaseNteAssertionLock(StackBase);
        if ( (SkmiFlags & 0x800000) != 0 && ((v36 & 0x801) != 0 || (v36 & 0x100) == 0) )
        {
          if ( (SkmiFlags & 0x1000000) != 0 )
          {
            v44 = a6;
            SkeFlushRangeListTb(0, 0, 1, &v44);
          }
          SkmiDecrementPageReferenceCount(a1);
        }
LABEL_69:
        v14 = a5;
      }
      else
      {
        SKMI_PAGE_SECURITY(296, a4, v19, 0);
        v11 = -1073741819;
      }
      _InterlockedDecrement((volatile signed __int32 *)(v13 + 136));
    }
    goto LABEL_71;
  }
LABEL_74:
  if ( v6 )
    SkmiDecrementPageReferenceCount(v6 >> 12);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400720b8  mov     [rsp-38h+arg_8], rbx
0x1400720bd  mov     qword ptr [rsp-38h+arg_10], r8
0x1400720c2  mov     [rsp-38h+BugCheckParameter3], rcx
0x1400720c7  push    rbp
0x1400720c8  push    rsi
0x1400720c9  push    rdi
0x1400720ca  push    r12
0x1400720cc  push    r13
0x1400720ce  push    r14
0x1400720d0  push    r15
0x1400720d2  mov     rbp, rsp
0x1400720d5  sub     rsp, 50h
0x1400720d9  mov     rbx, [rbp+arg_20]
0x1400720dd  xor     r12d, r12d
0x1400720e0  mov     qword ptr [rbp+BackTraceHash], r12
0x1400720e4  mov     r15, r9
0x1400720e7  mov     rsi, r8
0x1400720ea  mov     r14, rdx
0x1400720ed  test    rbx, rbx
0x1400720f0  jz      short loc_140072132
0x1400720f2  mov     rdi, rbx
0x1400720f5  lea     edx, [r12+1]
0x1400720fa  sar     rdi, 0Ch
0x1400720fe  lea     rcx, [rbp+arg_20]
0x140072102  mov     r8d, 8001h
0x140072108  mov     [rbp+arg_20], rdi
0x14007210c  call    SkmiClaimPhysicalPages
0x140072111  test    eax, eax
0x140072113  jnz     short loc_140072132
0x140072115  xor     r9d, r9d
0x140072118  xor     r8d, r8d
0x14007211b  mov     rdx, rdi
0x14007211e  mov     ecx, 143h
0x140072123  call    SKMI_PAGE_SECURITY
0x140072128  mov     eax, 0C0000043h
0x14007212d  jmp     loc_140072574
0x140072132  lea     rax, [rbp+BackTraceHash]
0x140072136  mov     [rsp+50h+var_28], r12
0x14007213b  lea     r9, SkmiImageType
0x140072142  mov     [rsp+50h+var_30], rax
0x140072147  mov     r8b, 1
0x14007214a  xor     edx, edx
0x14007214c  mov     rcx, r14
0x14007214f  call    SkobReferenceObjectByHandle
0x140072154  mov     edi, eax
0x140072156  test    eax, eax
0x140072158  js      loc_140072561
0x14007215e  lea     rcx, SkmiNteLock
0x140072165  call    SkAcquireSpinLockShared
0x14007216a  mov     r13, qword ptr [rbp+BackTraceHash]
0x14007216e  mov     r14b, al
0x140072171  mov     byte ptr [rbp+arg_20], al
0x140072174  mov     ecx, [r13+4]
0x140072178  cmp     rsi, rcx
0x14007217b  jb      short loc_14007219E
0x14007217d  mov     r9, rsi
0x140072180  mov     [rsp+50h+var_30], r12
0x140072185  mov     r8, r13
0x140072188  xor     edx, edx
0x14007218a  mov     ecx, 122h
0x14007218f  call    SKMI_IMAGE_SECURITY
0x140072194  mov     edi, 0C0000018h
0x140072199  jmp     loc_140072544
0x14007219e  lfence
0x1400721a1  mov     rax, [r13+8]
0x1400721a5  mov     r12d, [rax+rsi*8]
0x1400721a9  shr     r12, 5
0x1400721ad  and     r12d, 1Fh
0x1400721b1  jnz     short loc_1400721D7
0x1400721b3  mov     ecx, 123h
0x1400721b8  xor     r12d, r12d
0x1400721bb  xor     edx, edx
0x1400721bd  mov     r8, r13
0x1400721c0  mov     [rsp+50h+var_30], r12
0x1400721c5  mov     r9, rsi
0x1400721c8  call    SKMI_IMAGE_SECURITY
0x1400721cd  mov     edi, 0C0000005h
0x1400721d2  jmp     loc_140072544
0x1400721d7  test    r12b, 4
0x1400721db  jz      short loc_1400721F0
0x1400721dd  test    r12b, 2
0x1400721e1  jnz     short loc_1400721EA
0x1400721e3  mov     ecx, 124h
0x1400721e8  jmp     short loc_1400721B8
0x1400721ea  mov     r12d, 3
0x1400721f0  mov     rcx, r13
0x1400721f3  call    SkmiLockImageShared
0x1400721f8  xor     r8d, r8d
0x1400721fb  mov     edi, eax
0x1400721fd  test    eax, eax
0x1400721ff  js      loc_140072544
0x140072205  mov     rcx, [rbp+arg_28]
0x140072209  call    SkmiGetValidNteAddress
0x14007220e  mov     rsi, rax
0x140072211  test    rax, rax
0x140072214  jnz     short loc_140072230
0x140072216  xor     r9d, r9d
0x140072219  mov     rdx, r15
0x14007221c  mov     ecx, 128h
0x140072221  call    SKMI_PAGE_SECURITY
0x140072226  mov     edi, 0C0000005h
0x14007222b  jmp     loc_14007253C
0x140072230  prefetchw byte ptr [rax]
0x140072233  mov     rdi, qword ptr [rbp+arg_10]
0x140072237  mov     edx, 400h
0x14007223c  mov     r10d, 100h
0x140072242  mov     r11d, 0FFFFFh
0x140072248  mov     r14, [rsi]
0x14007224b  mov     qword ptr [rbp+BackTraceHash], r14
0x14007224f  bt      r14, 9
0x140072254  jnb     loc_14007251F
0x14007225a  mov     rax, r14
0x14007225d  and     eax, 801h
0x140072262  cmp     rax, 1
0x140072266  jz      short loc_140072296
0x140072268  test    r10, r14
0x14007226b  jnz     short loc_140072296
0x14007226d  test    rdx, r14
0x140072270  jnz     loc_140072334
0x140072276  bt      r14, 3Ah ; ':'
0x14007227b  jnb     short loc_14007228C
0x14007227d  mov     rax, r14
0x140072280  shr     rax, 10h
0x140072284  and     rax, r11
0x140072287  cmp     rax, rdi
0x14007228a  jz      short loc_1400722C5
0x14007228c  mov     ecx, 126h
0x140072291  jmp     loc_140072524
0x140072296  test    rdx, r14
0x140072299  jnz     loc_14007232D
0x14007229f  bt      r14, 3Ah ; ':'
0x1400722a4  jnb     loc_140072518
0x1400722aa  mov     rcx, r14
0x1400722ad  and     ecx, 901h
0x1400722b3  cmp     rcx, r10
0x1400722b6  jz      loc_140072511
0x1400722bc  test    rbx, rbx
0x1400722bf  jz      loc_14007250A
0x1400722c5  mov     rcx, r14
0x1400722c8  mov     rax, r14
0x1400722cb  or      rcx, rdx
0x1400722ce  lock cmpxchg [rsi], rcx
0x1400722d3  mov     r14, rax
0x1400722d6  mov     qword ptr [rbp+BackTraceHash], rax
0x1400722da  jnz     loc_14007224F
0x1400722e0  and     eax, 800h
0x1400722e5  mov     [rbp+var_10], rax
0x1400722e9  jnz     short loc_1400722F1
0x1400722eb  test    r14b, 1
0x1400722ef  jnz     short loc_1400722F6
0x1400722f1  test    r10, r14
0x1400722f4  jz      short loc_14007233E
0x1400722f6  lea     rcx, SkmiNarSpinLock
0x1400722fd  call    SkAcquireSpinLockSharedAtDpcLevel
0x140072302  mov     rcx, [rbp+arg_28]
0x140072306  call    SkmiLocateNar
0x14007230b  lock dec cs:SkmiNarSpinLock
0x140072312  mov     [rbp+var_18], rax
0x140072316  call    SkTrackSpinLockRelease
0x14007231b  mov     rdx, [rbp+var_18]
0x14007231f  mov     rcx, [rbp+arg_28]
0x140072323  sub     rcx, [rdx+18h]
0x140072327  shr     rcx, 0Ch
0x14007232b  jmp     short loc_14007235D
0x14007232d  pause
0x14007232f  jmp     loc_140072248
0x140072334  mov     ecx, 125h
0x140072339  jmp     loc_140072524
0x14007233e  mov     rax, r14
0x140072341  shr     rax, 24h
0x140072345  movzx   ecx, ax
0x140072348  mov     rax, cs:SkmiNarTable
0x14007234f  mov     rdx, [rax+rcx*8]
0x140072353  mov     rcx, r14
0x140072356  shr     rcx, 10h
0x14007235a  and     rcx, r11
0x14007235d  cmp     r13, [rdx+30h]
0x140072361  jz      short loc_140072389
0x140072363  mov     ecx, 127h
0x140072368  mov     rdx, r15
0x14007236b  lea     r9, [rbp+BackTraceHash]
0x14007236f  mov     r8, rsi
0x140072372  call    SKMI_PAGE_SECURITY
0x140072377  mov     edi, 0C0000005h
0x14007237c  lock and qword ptr [rsi], 0FFFFFFFFFFFFFBFFh
0x140072384  jmp     loc_140072538
0x140072389  mov     eax, ecx
0x14007238b  cmp     rax, rdi
0x14007238e  jz      short loc_140072397
0x140072390  mov     ecx, 12Ch
0x140072395  jmp     short loc_140072368
0x140072397  mov     rax, [rdx+18h]
0x14007239b  xor     r9d, r9d; int
0x14007239e  mov     r8, [rbp+BugCheckParameter3]; int
0x1400723a2  mov     rdx, rdi; int
0x1400723a5  mov     [rsp+50h+var_28], rax; __int64
0x1400723aa  mov     rcx, r13; int
0x1400723ad  mov     [rsp+50h+var_30], r15; BugCheckParameter3
0x1400723b2  call    SkmiCopyOnWrite
0x1400723b7  xor     r10d, r10d
0x1400723ba  mov     edi, eax
0x1400723bc  test    eax, eax
0x1400723be  js      short loc_14007237C
0x1400723c0  call    SkmiAcquireNteAssertionLock
0x1400723c5  test    rbx, rbx
0x1400723c8  jz      short loc_1400723D8
0x1400723ca  mov     r8, r15
0x1400723cd  mov     rcx, rbx
0x1400723d0  call    SkmiUpdateNormalPte
0x1400723d5  xor     r10d, r10d
0x1400723d8  test    cs:SkmiFlags, 800000h
0x1400723e2  jz      short loc_14007241A
0x1400723e4  cmp     [rbp+var_10], r10
0x1400723e8  jnz     short loc_1400723F0
0x1400723ea  test    r14b, 1
0x1400723ee  jnz     short loc_14007241A
0x1400723f0  mov     ecx, 100h
0x1400723f5  test    rcx, r14
0x1400723f8  jnz     short loc_14007241A
0x1400723fa  mov     r14d, r12d
0x1400723fd  mov     rax, 0FFFFFFFFFFh
0x140072407  shl     r14, 2Fh
0x14007240b  and     r15, rax
0x14007240e  or      r14, r15
0x140072411  shl     r14, 0Ch
0x140072415  or      r14, rcx
0x140072418  jmp     short loc_14007243F
0x14007241a  mov     eax, r12d
0x14007241d  lea     rcx, SkmiProtectionToPte
0x140072424  shl     r15, 0Ch
0x140072428  mov     r14, r15
0x14007242b  xor     r14, [rcx+rax*8]
0x14007242f  mov     rax, 0FFF0000000000FFFh
0x140072439  and     r14, rax
0x14007243c  xor     r14, r15
0x14007243f  mov     rax, [rsi]
0x140072442  bts     r14, 9
0x140072447  mov     r9, r14
0x14007244a  mov     [rsp+50h+var_30], rax
0x14007244f  xor     r8d, r8d
0x140072452  mov     rdx, rsi
0x140072455  xor     ecx, ecx
0x140072457  call    SkmiGetPteTrace
0x14007245c  mov     r12, rax
0x14007245f  test    rax, rax
0x140072462  jz      short loc_1400724B7
0x140072464  xor     edx, edx; Val
0x140072466  lea     r15, [rax+20h]
0x14007246a  mov     rcx, r15; void *
0x14007246d  lea     r8d, [rdx+40h]; Size
0x140072471  call    memset_0
0x140072476  test    cs:SkmiFlags, 400000h
0x140072480  jz      short loc_1400724B7
0x140072482  mov     rcx, gs:8; FramesToSkip
0x14007248b  test    rcx, rcx
0x14007248e  jz      short loc_1400724B7
0x140072490  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x140072494  mov     r8, r15; BackTrace
0x140072497  mov     edx, 8; FramesToCapture
0x14007249c  call    RtlCaptureStackBackTrace
0x1400724a1  test    ax, ax
0x1400724a4  jnz     short loc_1400724B7
0x1400724a6  mov     rax, [rbp+38h]
0x1400724aa  mov     [r12+28h], rax
0x1400724af  call    SkmiGetInstructionPointer
0x1400724b4  mov     [r15], rax
0x1400724b7  mov     cl, 2
0x1400724b9  mov     [rsi], r14
0x1400724bc  call    SkmiReleaseNteAssertionLock
0x1400724c1  test    cs:SkmiFlags, 800000h
0x1400724cb  jz      short loc_140072538
0x1400724cd  test    r14, 801h
0x1400724d4  jnz     short loc_1400724DD
0x1400724d6  bt      r14, 8
0x1400724db  jb      short loc_140072538
0x1400724dd  test    byte ptr cs:SkmiFlags+3, 1
0x1400724e4  jz      short loc_1400724FF
0x1400724e6  mov     rax, [rbp+arg_28]
0x1400724ea  lea     r9, [rbp+var_10]
0x1400724ee  xor     edx, edx
0x1400724f0  mov     [rbp+var_10], rax
0x1400724f4  xor     ecx, ecx
0x1400724f6  lea     r8d, [rdx+1]
0x1400724fa  call    SkeFlushRangeListTb
0x1400724ff  mov     rcx, [rbp+BugCheckParameter3]; BugCheckParameter3
0x140072503  call    SkmiDecrementPageReferenceCount
0x140072508  jmp     short loc_140072538
0x14007250a  mov     ecx, 12Ah
0x14007250f  jmp     short loc_140072524
0x140072511  mov     ecx, 129h
0x140072516  jmp     short loc_140072524
0x140072518  mov     ecx, 12Bh
0x14007251d  jmp     short loc_140072524
0x14007251f  mov     ecx, 121h
0x140072524  lea     r9, [rbp+BackTraceHash]
0x140072528  mov     r8, rsi
0x14007252b  mov     rdx, r15
0x14007252e  call    SKMI_PAGE_SECURITY
0x140072533  mov     edi, 0C0000005h
0x140072538  mov     r14b, byte ptr [rbp+arg_20]
  ... truncated ...
```
