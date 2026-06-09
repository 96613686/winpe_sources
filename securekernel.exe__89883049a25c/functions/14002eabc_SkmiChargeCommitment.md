# SkmiChargeCommitment

- ea: `0x14002eabc`
- end: `0x14002f3f0`
- name: `SkmiChargeCommitment`
- size: `2356`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14001ed6c`
- `0x1400280b0`
- `0x1400603cc`
- `0x140065d00`
- `0x1400661e4`
- `0x140066464`
- `0x14006779c`
- `0x14006a4b8`

## callees

- `0x1400017f4`
- `0x140002410`
- `0x140003780`
- `0x14000e460`
- `0x1400143a8`
- `0x140020194`
- `0x1400202b0`
- `0x140024724`
- `0x14002b534`
- `0x14002eabc`
- `0x14002f3f8`
- `0x140030f10`
- `0x140031460`
- `0x14003148c`
- `0x14007fd10`
- `0x1400801c0`
- `0x140080338`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiChargeCommitment(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v3; // rsi
  __int64 v4; // r14
  unsigned __int64 v5; // rcx
  __int64 CurrentIrql; // r15
  unsigned __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // edi
  unsigned int v11; // edx
  unsigned __int64 v12; // r14
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rbx
  __int64 PteTrace; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r15
  PVOID *v24; // rsi
  PVOID StackBase; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rcx
  int v29; // ecx
  __int64 v30; // rbx
  __int64 v31; // rsi
  __int64 v32; // rax
  __int64 v33; // r15
  PVOID *v34; // r14
  PVOID v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  int v41; // ecx
  int v42; // eax
  unsigned __int64 v43; // rsi
  __int64 v44; // r14
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // r13
  PVOID *v51; // r15
  PVOID v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  _QWORD *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rdx
  int v58; // ecx
  __int64 v59; // rbx
  __int64 v60; // r12
  __int64 v61; // rax
  __int64 v62; // r8
  __int64 v63; // r13
  PVOID *v64; // r15
  PVOID v65; // rcx
  USHORT v66; // ax
  __int64 v67; // rdx
  __int64 v68; // rcx
  _QWORD *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rdx
  int v72; // ecx
  unsigned __int64 v73; // r14
  __int64 v74; // rax
  __int64 v75; // r15
  PVOID *v76; // rbx
  PVOID v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rcx
  _QWORD *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rsi
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v86; // [rsp+38h] [rbp-31h]
  __int64 v87; // [rsp+40h] [rbp-29h]
  __int64 v88; // [rsp+48h] [rbp-21h]
  __int64 v89; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v90; // [rsp+58h] [rbp-11h] BYREF
  __int128 v91; // [rsp+60h] [rbp-9h]
  __int64 v92; // [rsp+70h] [rbp+7h]
  __int64 v93; // [rsp+78h] [rbp+Fh]
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+5Fh]

  v86 = a2;
  v87 = a1;
  v90 = SkmiSystemPartition;
  v2 = SkmiTotalCommitment;
  v3 = a2;
  v4 = a1;
  v92 = 0;
  v91 = 0;
  v89 = 0;
  v93 = 0;
  do
  {
    if ( a2 + v2 < v2 )
      return 3221225773LL;
    v5 = v2;
    v2 = _InterlockedCompareExchange64(&SkmiTotalCommitment, a2 + v2, v2);
  }
  while ( v2 != v5 );
  CurrentIrql = KeGetCurrentIrql();
  v88 = CurrentIrql;
  __writecr8(2u);
  SkAcquireSpinLockExclusiveAtDpcLevel(v4 + 124);
  v7 = v3 + *(_QWORD *)(v4 + 128);
  if ( v7 >= v3 )
  {
    v8 = 0;
    *(_QWORD *)(v4 + 128) = v7;
  }
  else
  {
    v8 = -1073741523;
  }
  *(_DWORD *)(v4 + 124) = 0;
  SkTrackSpinLockRelease();
  if ( v8 >= 0 )
  {
    v10 = 1;
LABEL_10:
    v9 = SkmiCheckTableSize;
    if ( SkmiCheckTableSize >= (unsigned __int64)SkmiTotalCommitment )
    {
      v8 = 0;
    }
    else
    {
      if ( (v10 & 2) != 0 )
        goto LABEL_14;
      if ( (unsigned int)SkmiAllocatePhysicalPage(0, 0, &v89) )
      {
        v10 |= 2u;
LABEL_14:
        v8 = SkmiPreparePteAllocation(&v90);
        if ( v8 >= 0 )
        {
          SkAcquireSpinLockExclusiveAtDpcLevel(&SkmiIntegrityExpansionLock);
          while ( SkmiCheckTableSize < (unsigned __int64)SkmiTotalCommitment )
          {
            if ( (v10 & 2) == 0 )
            {
              if ( !(unsigned int)SkmiTryAllocatePhysicalPage(SkmiSystemPartition, 0, 1, &v89) )
                goto LABEL_97;
              v10 |= 2u;
            }
            v11 = SkmiFreeIntegrityPte;
            if ( !SkmiFreeIntegrityPte )
            {
              v12 = (((unsigned __int64)qword_140156B50 >> 9) & 0x7FFFFFFFF8LL)
                  + 8LL * (unsigned int)SkmiNextIntegrityPte
                  - 0x98000000000LL;
              v13 = SkiAttachProcess(PsIumSystemProcess);
              SkAcquireSpinLockExclusiveAtDpcLevel(&SkmiKernelPteLock);
              v14 = SkmiCommitPte(v12, &v90, 0);
              SkmiKernelPteLock = 0;
              SkTrackSpinLockRelease();
              SkiAttachProcess(v13);
              if ( !v14 )
              {
LABEL_97:
                SkmiIntegrityExpansionLock = 0;
                SkTrackSpinLockRelease();
                goto LABEL_10;
              }
              *(_QWORD *)BackTraceHash = 4098;
              SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v15, v16, v17);
              v18 = *(_QWORD *)BackTraceHash | 0x80000000LL;
              PteTrace = SkmiGetPteTrace(0, v12, 0, BackTraceHash[0] | 0x80000000, *(_QWORD *)v12);
              v23 = PteTrace;
              if ( PteTrace )
              {
                v24 = (PVOID *)(PteTrace + 32);
                memset_0((void *)(PteTrace + 32), 0, 0x40u);
                if ( (SkmiFlags & 0x400000) != 0 )
                {
                  StackBase = KeGetPcr()->NtTib.StackBase;
                  if ( StackBase )
                  {
                    if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v24, BackTraceHash) )
                    {
                      *(_QWORD *)(v23 + 40) = retaddr;
                      *v24 = (PVOID)SkmiGetInstructionPointer(v26, v20);
                    }
                  }
                }
              }
              if ( v12 >= 0xFFFFF6FB7DBED000uLL && v12 < 0xFFFFF6FB7DBED800uLL )
              {
                v27 = KeGetPcr()->NtTib.StackBase;
                v28 = v27 ? v27[10] : 0LL;
                v20 = *(_QWORD *)(v28 + 232);
                if ( v20 )
                {
                  v29 = SkiKvaShadowMode;
                  *(_QWORD *)(v20 + 8 * (((__int64)v12 >> 3) & 0x1FF)) = v18;
                  if ( v29 != 2 && (v18 & 1) != 0 )
                    v18 |= 0x8000000000000000uLL;
                }
              }
              *(_QWORD *)v12 = v18;
              *(_QWORD *)BackTraceHash = 0x20000001002LL;
              SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v20, v21, v22);
              v30 = *(_QWORD *)BackTraceHash;
              v31 = v12 + 8;
              v32 = SkmiGetPteTrace(0, (int)v12 + 8, 0, BackTraceHash[0], *(_QWORD *)(v12 + 8));
              v33 = v32;
              if ( v32 )
              {
                v34 = (PVOID *)(v32 + 32);
                memset_0((void *)(v32 + 32), 0, 0x40u);
                if ( (SkmiFlags & 0x400000) != 0 )
                {
                  v35 = KeGetPcr()->NtTib.StackBase;
                  if ( v35 )
                  {
                    if ( !RtlCaptureStackBackTrace((ULONG)v35, 8u, v34, BackTraceHash) )
                    {
                      *(_QWORD *)(v33 + 40) = retaddr;
                      *v34 = (PVOID)SkmiGetInstructionPointer(v37, v36);
                    }
                  }
                }
              }
              if ( (unsigned __int64)v31 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v31 < 0xFFFFF6FB7DBED800uLL )
              {
                v38 = KeGetPcr()->NtTib.StackBase;
                v39 = v38 ? v38[10] : 0LL;
                v40 = *(_QWORD *)(v39 + 232);
                if ( v40 )
                {
                  v41 = SkiKvaShadowMode;
                  *(_QWORD *)(v40 + 8 * ((v31 >> 3) & 0x1FF)) = v30;
                  if ( v41 != 2 && (v30 & 1) != 0 )
                    v30 |= 0x8000000000000000uLL;
                }
              }
              v11 = SkmiNextIntegrityPte;
              SkmiFreeIntegrityPte = SkmiNextIntegrityPte;
              v42 = SkmiNextIntegrityPte + 512;
              *(_QWORD *)v31 = v30;
              SkmiNextIntegrityPte = v42;
            }
            v43 = (((unsigned __int64)qword_140156B50 >> 9) & 0x7FFFFFFFF8LL) + 8LL * v11 - 0x98000000000LL;
            *(_QWORD *)BackTraceHash = *(_QWORD *)v43;
            SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash);
            if ( (BackTraceHash[0] & 0x80000000) != 0 )
            {
              ++SkmiFreeIntegrityPte;
              v44 = v43 + 8;
              *(_QWORD *)BackTraceHash = *(_QWORD *)(v43 + 8);
              SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash);
              if ( BackTraceHash[1] == 2 )
              {
                *(_QWORD *)BackTraceHash = v46 & 0xFFFFFFFF7FFFFFFFuLL;
                SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v45, v46 & 0xFFFFFFFF7FFFFFFFuLL, v47);
                v48 = *(_QWORD *)BackTraceHash;
                v49 = SkmiGetPteTrace(0, (int)v43 + 8, 0, BackTraceHash[0], *(_QWORD *)v44);
                v50 = v49;
                if ( v49 )
                {
                  v51 = (PVOID *)(v49 + 32);
                  memset_0((void *)(v49 + 32), 0, 0x40u);
                  if ( (SkmiFlags & 0x400000) != 0 )
                  {
                    v52 = KeGetPcr()->NtTib.StackBase;
                    if ( v52 )
                    {
                      if ( !RtlCaptureStackBackTrace((ULONG)v52, 8u, v51, BackTraceHash) )
                      {
                        *(_QWORD *)(v50 + 40) = retaddr;
                        *v51 = (PVOID)SkmiGetInstructionPointer(v54, v53);
                      }
                    }
                  }
                }
                if ( (unsigned __int64)v44 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v44 < 0xFFFFF6FB7DBED800uLL )
                {
                  v55 = KeGetPcr()->NtTib.StackBase;
                  v56 = v55 ? v55[10] : 0LL;
                  v57 = *(_QWORD *)(v56 + 232);
                  if ( v57 )
                  {
                    v58 = SkiKvaShadowMode;
                    *(_QWORD *)(v57 + 8 * ((v44 >> 3) & 0x1FF)) = v48;
                    if ( v58 != 2 && (v48 & 1) != 0 )
                      v48 |= 0x8000000000000000uLL;
                  }
                }
                *(_QWORD *)v44 = v48;
              }
              else
              {
                *(_QWORD *)BackTraceHash = BackTraceHash[0] | ((BackTraceHash[1] - 1LL) << 32);
                SKMI_SWIZZLE_INVALID_PTE(BackTraceHash, v45, v46, v47);
                v59 = *(_QWORD *)BackTraceHash;
                v60 = v43 + 16;
                v61 = SkmiGetPteTrace(0, (int)v43 + 16, 0, BackTraceHash[0], *(_QWORD *)(v43 + 16));
                v62 = 0;
                v63 = v61;
                if ( v61 )
                {
                  v64 = (PVOID *)(v61 + 32);
                  memset_0((void *)(v61 + 32), 0, 0x40u);
                  v62 = 0;
                  if ( (SkmiFlags & 0x400000) != 0 )
                  {
                    v65 = KeGetPcr()->NtTib.StackBase;
                    if ( v65 )
                    {
                      v66 = RtlCaptureStackBackTrace((ULONG)v65, 8u, v64, BackTraceHash);
                      v62 = 0;
                      if ( !v66 )
                      {
                        *(_QWORD *)(v63 + 40) = retaddr;
                        *v64 = (PVOID)SkmiGetInstructionPointer(v68, v67);
                      }
                    }
                  }
                }
                if ( (unsigned __int64)v60 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v60 < 0xFFFFF6FB7DBED800uLL )
                {
                  v69 = KeGetPcr()->NtTib.StackBase;
                  v70 = v69 ? v69[10] : v62;
                  v71 = *(_QWORD *)(v70 + 232);
                  if ( v71 )
                  {
                    v72 = SkiKvaShadowMode;
                    *(_QWORD *)(v71 + 8 * ((v60 >> 3) & 0x1FF)) = v59;
                    if ( v72 != 2 && (v59 & 1) != 0 )
                      v59 |= 0x8000000000000000uLL;
                  }
                }
                *(_QWORD *)v60 = v59;
                *(_QWORD *)v44 = *(_QWORD *)v43;
              }
            }
            else
            {
              SkmiFreeIntegrityPte = BackTraceHash[1];
            }
            v73 = (((16 * (v89 & 0xFFFFFFFFFFLL)) | word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
            v74 = SkmiGetPteTrace(0, v43, 0, (((16 * (_DWORD)v89) | word_140156D90 & 1) << 8) | 0x63u, *(_QWORD *)v43);
            v75 = v74;
            if ( v74 )
            {
              v76 = (PVOID *)(v74 + 32);
              memset_0((void *)(v74 + 32), 0, 0x40u);
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                v77 = KeGetPcr()->NtTib.StackBase;
                if ( v77 )
                {
                  if ( !RtlCaptureStackBackTrace((ULONG)v77, 8u, v76, BackTraceHash) )
                  {
                    *(_QWORD *)(v75 + 40) = retaddr;
                    *v76 = (PVOID)SkmiGetInstructionPointer(v79, v78);
                  }
                }
              }
            }
            if ( v43 >= 0xFFFFF6FB7DBED000uLL && v43 < 0xFFFFF6FB7DBED800uLL )
            {
              v80 = KeGetPcr()->NtTib.StackBase;
              v81 = v80 ? v80[10] : 0LL;
              v82 = *(_QWORD *)(v81 + 232);
              if ( v82 )
                *(_QWORD *)(v82 + 8 * (((__int64)v43 >> 3) & 0x1FF)) = v73;
            }
            *(_QWORD *)v43 = v73;
            v83 = (__int64)(v43 << 25) >> 16;
            *(_DWORD *)(v83 + 8) = 0;
            *(_DWORD *)(v83 + 12) = 255;
            SkAcquireSpinLockExclusiveAtDpcLevel(&SkmiIntegrityListLock);
            SkmiInsertIntegrityPage(&SkmiEmptyIntegrityPages, v83, 1);
            v10 &= ~2u;
            SkmiCheckTableSize += 170;
            SkmiIntegrityListLock = 0;
            SkTrackSpinLockRelease();
          }
          v8 = 0;
          SkmiIntegrityExpansionLock = 0;
          SkTrackSpinLockRelease();
        }
        goto LABEL_102;
      }
      v8 = -1073741670;
    }
LABEL_102:
    LOBYTE(CurrentIrql) = v88;
    v4 = v87;
    v3 = v86;
    goto LABEL_103;
  }
  LOBYTE(v10) = 0;
  _InterlockedAdd64(&SkmiTotalCommitment, -(__int64)v3);
LABEL_103:
  LOBYTE(v9) = CurrentIrql;
  SkeLowerIrql(v9);
  if ( v8 < 0 )
  {
    if ( (v10 & 1) != 0 )
      SkmiReturnCommitment(v4, v3);
    else
      SkmiTrimIntegrityTable();
  }
  if ( (v10 & 2) != 0 )
    SkmiFreePhysicalPage(0, v89);
  SkmiFreePteAllocation(&v90);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002eabc  mov     [rsp-8+arg_10], rbx
0x14002eac1  push    rbp
0x14002eac2  push    rsi
0x14002eac3  push    rdi
0x14002eac4  push    r12
0x14002eac6  push    r13
0x14002eac8  push    r14
0x14002eaca  push    r15
0x14002eacc  lea     rbp, [rsp-27h]
0x14002ead1  sub     rsp, 90h
0x14002ead8  mov     rax, cs:__security_cookie
0x14002eadf  xor     rax, rsp
0x14002eae2  mov     [rbp+57h+var_40], rax
0x14002eae6  xor     r12d, r12d
0x14002eae9  mov     [rbp+57h+var_88], rdx
0x14002eaed  lea     rax, SkmiSystemPartition
0x14002eaf4  mov     [rbp+57h+var_80], rcx
0x14002eaf8  xorps   xmm0, xmm0
0x14002eafb  mov     [rbp+57h+var_68], rax
0x14002eaff  mov     rax, cs:SkmiTotalCommitment
0x14002eb06  mov     rsi, rdx
0x14002eb09  mov     r14, rcx
0x14002eb0c  mov     [rbp+57h+var_50], r12
0x14002eb10  movdqu  [rbp+57h+var_60], xmm0
0x14002eb15  mov     [rbp+57h+var_70], r12
0x14002eb19  mov     [rbp+57h+var_48], r12
0x14002eb1d  lea     rdx, [rsi+rax]
0x14002eb21  cmp     rdx, rax
0x14002eb24  jb      loc_14002F3C3
0x14002eb2a  mov     rcx, rax
0x14002eb2d  lock cmpxchg cs:SkmiTotalCommitment, rdx
0x14002eb36  cmp     rax, rcx
0x14002eb39  jnz     short loc_14002EB1D
0x14002eb3b  mov     r15, cr8
0x14002eb3f  mov     [rbp+57h+var_78], r15
0x14002eb43  mov     r13d, 2
0x14002eb49  mov     cr8, r13
0x14002eb4d  lea     rcx, [r14+7Ch]
0x14002eb51  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14002eb56  mov     rcx, [r14+80h]
0x14002eb5d  add     rcx, rsi
0x14002eb60  cmp     rcx, rsi
0x14002eb63  jnb     short loc_14002EB6C
0x14002eb65  mov     ebx, 0C000012Dh
0x14002eb6a  jmp     short loc_14002EB76
0x14002eb6c  mov     ebx, r12d
0x14002eb6f  mov     [r14+80h], rcx
0x14002eb76  mov     [r14+7Ch], r12d
0x14002eb7a  call    SkTrackSpinLockRelease
0x14002eb7f  test    ebx, ebx
0x14002eb81  jns     short loc_14002EB99
0x14002eb83  mov     rax, rsi
0x14002eb86  mov     edi, r12d
0x14002eb89  neg     rax
0x14002eb8c  lock add cs:SkmiTotalCommitment, rax
0x14002eb94  jmp     loc_14002F382
0x14002eb99  mov     edi, 1
0x14002eb9e  mov     r15d, 80000000h
0x14002eba4  mov     rsi, 0FFFFF68000000000h
0x14002ebae  mov     r14, 7FFFFFFFF8h
0x14002ebb8  mov     rcx, cs:SkmiCheckTableSize
0x14002ebbf  mov     rax, cs:SkmiTotalCommitment
0x14002ebc6  cmp     rcx, rax
0x14002ebc9  jnb     loc_14002F373
0x14002ebcf  test    r13b, dil
0x14002ebd2  jnz     short loc_14002EBEC
0x14002ebd4  lea     r8, [rbp+57h+var_70]
0x14002ebd8  xor     edx, edx
0x14002ebda  xor     ecx, ecx
0x14002ebdc  call    SkmiAllocatePhysicalPage
0x14002ebe1  test    eax, eax
0x14002ebe3  jz      loc_14002F35B
0x14002ebe9  or      edi, r13d
0x14002ebec  lea     rcx, [rbp+57h+var_68]
0x14002ebf0  call    SkmiPreparePteAllocation
0x14002ebf5  mov     ebx, eax
0x14002ebf7  test    eax, eax
0x14002ebf9  js      loc_14002F376
0x14002ebff  lea     rcx, SkmiIntegrityExpansionLock
0x14002ec06  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14002ec0b  mov     rcx, cs:SkmiCheckTableSize
0x14002ec12  mov     rax, cs:SkmiTotalCommitment
0x14002ec19  cmp     rcx, rax
0x14002ec1c  jnb     loc_14002F362
0x14002ec22  test    r13b, dil
0x14002ec25  jnz     short loc_14002EC48
0x14002ec27  xor     edx, edx
0x14002ec29  lea     r9, [rbp+57h+var_70]
0x14002ec2d  lea     rcx, SkmiSystemPartition
0x14002ec34  lea     r8d, [rdx+1]
0x14002ec38  call    SkmiTryAllocatePhysicalPage
0x14002ec3d  test    eax, eax
0x14002ec3f  jz      loc_14002F339
0x14002ec45  or      edi, r13d
0x14002ec48  mov     edx, cs:SkmiFreeIntegrityPte
0x14002ec4e  test    edx, edx
0x14002ec50  jnz     loc_14002EEF8
0x14002ec56  mov     rcx, cs:qword_140156B50
0x14002ec5d  mov     eax, cs:SkmiNextIntegrityPte
0x14002ec63  shr     rcx, 9
0x14002ec67  and     rcx, r14
0x14002ec6a  lea     r14, [rcx+rax*8]
0x14002ec6e  mov     rax, rsi
0x14002ec71  mov     rcx, cs:PsIumSystemProcess
0x14002ec78  add     r14, rax
0x14002ec7b  call    SkiAttachProcess
0x14002ec80  lea     rcx, SkmiKernelPteLock
0x14002ec87  mov     rsi, rax
0x14002ec8a  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14002ec8f  xor     r8d, r8d
0x14002ec92  lea     rdx, [rbp+57h+var_68]
0x14002ec96  mov     rcx, r14
0x14002ec99  call    SkmiCommitPte
0x14002ec9e  mov     ebx, eax
0x14002eca0  mov     cs:SkmiKernelPteLock, r12d
0x14002eca7  call    SkTrackSpinLockRelease
0x14002ecac  mov     rcx, rsi
0x14002ecaf  call    SkiAttachProcess
0x14002ecb4  test    ebx, ebx
0x14002ecb6  jz      loc_14002F34A
0x14002ecbc  lea     rcx, [rbp+57h+BackTraceHash]
0x14002ecc0  mov     qword ptr [rbp+57h+BackTraceHash], 1002h
0x14002ecc8  call    SKMI_SWIZZLE_INVALID_PTE
0x14002eccd  mov     rax, [r14]
0x14002ecd0  xor     r8d, r8d
0x14002ecd3  mov     rbx, qword ptr [rbp+57h+BackTraceHash]
0x14002ecd7  mov     rdx, r14
0x14002ecda  or      rbx, r15
0x14002ecdd  mov     [rsp+0C0h+var_A0], rax
0x14002ece2  mov     r9, rbx
0x14002ece5  xor     ecx, ecx
0x14002ece7  call    SkmiGetPteTrace
0x14002ecec  mov     r15, rax
0x14002ecef  test    rax, rax
0x14002ecf2  jz      short loc_14002ED46
0x14002ecf4  xor     edx, edx; Val
0x14002ecf6  lea     rsi, [rax+20h]
0x14002ecfa  mov     rcx, rsi; void *
0x14002ecfd  lea     r8d, [rdx+40h]; Size
0x14002ed01  call    memset_0
0x14002ed06  test    cs:SkmiFlags, 400000h
0x14002ed10  jz      short loc_14002ED46
0x14002ed12  mov     rcx, gs:8; FramesToSkip
0x14002ed1b  test    rcx, rcx
0x14002ed1e  jz      short loc_14002ED46
0x14002ed20  lea     r9, [rbp+57h+BackTraceHash]; BackTraceHash
0x14002ed24  mov     r8, rsi; BackTrace
0x14002ed27  mov     edx, 8; FramesToCapture
0x14002ed2c  call    RtlCaptureStackBackTrace
0x14002ed31  test    ax, ax
0x14002ed34  jnz     short loc_14002ED46
0x14002ed36  mov     rax, [rbp+5Fh]
0x14002ed3a  mov     [r15+28h], rax
0x14002ed3e  call    SkmiGetInstructionPointer
0x14002ed43  mov     [rsi], rax
0x14002ed46  mov     rax, 0FFFFF6FB7DBED000h
0x14002ed50  mov     rax, rax
0x14002ed53  cmp     r14, rax
0x14002ed56  jb      short loc_14002EDBA
0x14002ed58  mov     rax, 0FFFFF6FB7DBED800h
0x14002ed62  mov     rax, rax
0x14002ed65  cmp     r14, rax
0x14002ed68  jnb     short loc_14002EDBA
0x14002ed6a  mov     rax, gs:8
0x14002ed73  test    rax, rax
0x14002ed76  jz      short loc_14002ED7E
0x14002ed78  mov     rcx, [rax+50h]
0x14002ed7c  jmp     short loc_14002ED81
0x14002ed7e  mov     rcx, r12
0x14002ed81  mov     rdx, [rcx+0E8h]
0x14002ed88  test    rdx, rdx
0x14002ed8b  jz      short loc_14002EDBA
0x14002ed8d  mov     ecx, cs:SkiKvaShadowMode
0x14002ed93  mov     rax, r14
0x14002ed96  sar     rax, 3
0x14002ed9a  and     eax, 1FFh
0x14002ed9f  mov     [rdx+rax*8], rbx
0x14002eda3  cmp     ecx, r13d
0x14002eda6  jz      short loc_14002EDBA
0x14002eda8  test    bl, 1
0x14002edab  jz      short loc_14002EDBA
0x14002edad  mov     rax, 8000000000000000h
0x14002edb7  or      rbx, rax
0x14002edba  mov     rax, 20000001002h
0x14002edc4  mov     [r14], rbx
0x14002edc7  lea     rcx, [rbp+57h+BackTraceHash]
0x14002edcb  mov     qword ptr [rbp+57h+BackTraceHash], rax
0x14002edcf  call    SKMI_SWIZZLE_INVALID_PTE
0x14002edd4  mov     rbx, qword ptr [rbp+57h+BackTraceHash]
0x14002edd8  lea     rsi, [r14+8]
0x14002eddc  mov     rax, [rsi]
0x14002eddf  mov     r9, rbx
0x14002ede2  xor     r8d, r8d
0x14002ede5  mov     [rsp+0C0h+var_A0], rax
0x14002edea  mov     rdx, rsi
0x14002eded  xor     ecx, ecx
0x14002edef  call    SkmiGetPteTrace
0x14002edf4  mov     r15, rax
0x14002edf7  test    rax, rax
0x14002edfa  jz      short loc_14002EE4E
0x14002edfc  xor     edx, edx; Val
0x14002edfe  lea     r14, [rax+20h]
0x14002ee02  mov     rcx, r14; void *
0x14002ee05  lea     r8d, [rdx+40h]; Size
0x14002ee09  call    memset_0
0x14002ee0e  test    cs:SkmiFlags, 400000h
0x14002ee18  jz      short loc_14002EE4E
0x14002ee1a  mov     rcx, gs:8; FramesToSkip
0x14002ee23  test    rcx, rcx
0x14002ee26  jz      short loc_14002EE4E
0x14002ee28  lea     r9, [rbp+57h+BackTraceHash]; BackTraceHash
0x14002ee2c  mov     r8, r14; BackTrace
0x14002ee2f  mov     edx, 8; FramesToCapture
0x14002ee34  call    RtlCaptureStackBackTrace
0x14002ee39  test    ax, ax
0x14002ee3c  jnz     short loc_14002EE4E
0x14002ee3e  mov     rax, [rbp+5Fh]
0x14002ee42  mov     [r15+28h], rax
0x14002ee46  call    SkmiGetInstructionPointer
0x14002ee4b  mov     [r14], rax
0x14002ee4e  mov     rax, 0FFFFF6FB7DBED000h
0x14002ee58  mov     rax, rax
0x14002ee5b  cmp     rsi, rax
0x14002ee5e  jb      short loc_14002EEC2
0x14002ee60  mov     rax, 0FFFFF6FB7DBED800h
0x14002ee6a  mov     rax, rax
0x14002ee6d  cmp     rsi, rax
0x14002ee70  jnb     short loc_14002EEC2
0x14002ee72  mov     rax, gs:8
0x14002ee7b  test    rax, rax
0x14002ee7e  jz      short loc_14002EE86
0x14002ee80  mov     rcx, [rax+50h]
0x14002ee84  jmp     short loc_14002EE89
0x14002ee86  mov     rcx, r12
0x14002ee89  mov     rdx, [rcx+0E8h]
0x14002ee90  test    rdx, rdx
0x14002ee93  jz      short loc_14002EEC2
0x14002ee95  mov     ecx, cs:SkiKvaShadowMode
0x14002ee9b  mov     rax, rsi
0x14002ee9e  sar     rax, 3
0x14002eea2  and     eax, 1FFh
0x14002eea7  mov     [rdx+rax*8], rbx
0x14002eeab  cmp     ecx, r13d
0x14002eeae  jz      short loc_14002EEC2
0x14002eeb0  test    bl, 1
0x14002eeb3  jz      short loc_14002EEC2
0x14002eeb5  mov     rax, 8000000000000000h
0x14002eebf  or      rbx, rax
0x14002eec2  mov     eax, cs:SkmiNextIntegrityPte
0x14002eec8  mov     r15d, 80000000h
0x14002eece  mov     edx, eax
0x14002eed0  mov     cs:SkmiFreeIntegrityPte, eax
0x14002eed6  add     eax, 200h
0x14002eedb  mov     [rsi], rbx
0x14002eede  mov     cs:SkmiNextIntegrityPte, eax
0x14002eee4  mov     r14, 7FFFFFFFF8h
0x14002eeee  mov     rsi, 0FFFFF68000000000h
0x14002eef8  mov     rcx, cs:qword_140156B50
0x14002eeff  shr     rcx, 9
0x14002ef03  and     rcx, r14
0x14002ef06  mov     eax, edx
0x14002ef08  lea     rcx, [rcx+rax*8]
0x14002ef0c  mov     rax, rsi
0x14002ef0f  lea     rsi, [rcx+rax]
0x14002ef13  mov     rax, [rsi]
0x14002ef16  lea     rcx, [rbp+57h+BackTraceHash]
0x14002ef1a  mov     qword ptr [rbp+57h+BackTraceHash], rax
0x14002ef1e  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14002ef23  mov     r8, qword ptr [rbp+57h+BackTraceHash]
0x14002ef27  test    r15, r8
0x14002ef2a  jnz     short loc_14002EF3C
0x14002ef2c  shr     r8, 20h
0x14002ef30  mov     cs:SkmiFreeIntegrityPte, r8d
0x14002ef37  jmp     loc_14002F1AE
0x14002ef3c  inc     cs:SkmiFreeIntegrityPte
0x14002ef42  lea     r14, [rsi+8]
0x14002ef46  mov     rax, [r14]
0x14002ef49  lea     rcx, [rbp+57h+BackTraceHash]
0x14002ef4d  mov     qword ptr [rbp+57h+BackTraceHash], rax
0x14002ef51  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14002ef56  mov     rcx, qword ptr [rbp+57h+BackTraceHash]
0x14002ef5a  shr     rcx, 20h
0x14002ef5e  cmp     ecx, r13d
0x14002ef61  jnz     loc_14002F081
0x14002ef67  mov     rax, 0FFFFFFFF7FFFFFFFh
0x14002ef71  lea     rcx, [rbp+57h+BackTraceHash]
0x14002ef75  and     r8, rax
0x14002ef78  mov     qword ptr [rbp+57h+BackTraceHash], r8
0x14002ef7c  call    SKMI_SWIZZLE_INVALID_PTE
0x14002ef81  mov     rax, [r14]
0x14002ef84  xor     r8d, r8d
0x14002ef87  mov     rbx, qword ptr [rbp+57h+BackTraceHash]
0x14002ef8b  mov     rdx, r14
0x14002ef8e  mov     r9, rbx
0x14002ef91  mov     [rsp+0C0h+var_A0], rax
0x14002ef96  xor     ecx, ecx
0x14002ef98  call    SkmiGetPteTrace
0x14002ef9d  mov     r13, rax
0x14002efa0  test    rax, rax
0x14002efa3  jz      short loc_14002EFF7
  ... truncated ...
```
