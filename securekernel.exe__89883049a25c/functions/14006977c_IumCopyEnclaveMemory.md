# IumCopyEnclaveMemory

- ea: `0x14006977c`
- end: `0x14006a196`
- name: `IumCopyEnclaveMemory`
- size: `2586`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, char)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x140002410`
- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x14000e810`
- `0x14000ff70`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020360`
- `0x14002b534`
- `0x14006977c`
- `0x14006ab08`
- `0x1400801fc`
- `0x140081290`
- `0x1400855c0`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall IumCopyEnclaveMemory(__int64 a1, __int64 a2, unsigned __int64 a3, char a4)
{
  _QWORD *StackBase; // rax
  char v5; // r13
  unsigned __int64 v6; // rbp
  __int64 v7; // r12
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r8
  int v12; // edx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  __int64 result; // rax
  volatile signed __int32 *v16; // r15
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 *ValidEnclaveContainerPte; // rax
  unsigned __int64 v21; // rdi
  unsigned __int64 *ValidPteAddress; // rax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // rdx
  unsigned int v27; // r8d
  __int64 HyperspacePte; // r15
  __int64 *v29; // rax
  __int64 v30; // r13
  unsigned __int64 v31; // rdi
  __int64 PteTrace; // rax
  int v33; // r10d
  __int64 v34; // r11
  __int64 v35; // rbp
  PVOID *v36; // rsi
  PVOID v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  int v43; // ecx
  unsigned __int64 v44; // rbx
  __int64 v45; // rax
  __int64 v46; // rsi
  PVOID *v47; // rdi
  PVOID v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rdx
  int v54; // ecx
  const void *v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rax
  unsigned __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // r11
  __int64 v61; // rbp
  PVOID *v62; // rsi
  PVOID v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // rcx
  _QWORD *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rdx
  int v69; // ecx
  unsigned __int64 v70; // rdi
  __int64 v71; // rax
  __int64 v72; // rsi
  PVOID *v73; // rbx
  PVOID v74; // rcx
  __int64 v75; // rdx
  __int64 v76; // rcx
  _QWORD *v77; // rax
  __int64 v78; // rcx
  __int64 v79; // rdx
  int v80; // ecx
  __int64 v81; // rax
  int v82; // r9d
  __int64 v83; // rdi
  PVOID *v84; // rbx
  PVOID v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // rcx
  __int64 v90; // rdx
  __int64 v91; // rax
  int v92; // r9d
  __int64 v93; // rdi
  PVOID *v94; // rbx
  PVOID v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rcx
  _QWORD *v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rdx
  __int64 v101; // rdx
  int v102; // edx
  __int64 v103; // rcx
  __int64 v104; // rdx
  unsigned int v105; // ebx
  __int64 v106; // rdx
  char v107; // [rsp+30h] [rbp-68h]
  unsigned int Size; // [rsp+34h] [rbp-64h]
  ULONG Size_4; // [rsp+38h] [rbp-60h] BYREF
  volatile signed __int32 *v110; // [rsp+40h] [rbp-58h]
  __int64 v111; // [rsp+48h] [rbp-50h]
  __int64 v112; // [rsp+50h] [rbp-48h]
  unsigned __int64 v113; // [rsp+58h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int64 v115; // [rsp+B0h] [rbp+18h]

  v115 = a3;
  StackBase = KeGetPcr()->NtTib.StackBase;
  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( !StackBase )
    return 3221225500LL;
  v8 = StackBase[10];
  if ( !v8 || (*(_DWORD *)v8 & 0x200) == 0 )
    return 3221225500LL;
  v9 = a1;
  if ( !a4 )
  {
    v9 = a2;
    v7 = a1;
  }
  v113 = v9;
  v10 = v9 + a3;
  if ( v9 + a3 <= v9 )
    return 3221225713LL;
  v11 = v7 + a3;
  if ( v11 <= v7 )
    return 3221225713LL;
  v12 = *(_DWORD *)(v8 + 568);
  v13 = *(unsigned int *)(v8 + 560) | ((unsigned __int64)(v12 & 0xFFF) << 32);
  if ( v9 >> 12 < v13 )
    return 3221225496LL;
  v14 = *(unsigned int *)(v8 + 564) | ((unsigned __int64)(v12 & 0xFFF000) << 20);
  if ( (v10 - 1) >> 12 >= v14 )
    return 3221225496LL;
  if ( (unsigned __int64)v7 >> 12 >= v13 )
  {
    if ( (unsigned __int64)v7 >> 12 <= v14 || v11 > 0x7FFFFFFF0000LL || v7 >> 47 != -1 && v7 >> 47 != 0 )
      return 3221225496LL;
  }
  else if ( (v11 - 1) >> 12 >= v13 )
  {
    return 3221225496LL;
  }
  v16 = (volatile signed __int32 *)(v8 + 192);
  v110 = (volatile signed __int32 *)(v8 + 192);
  v17 = v8 + 8;
LABEL_17:
  v107 = SkAcquireSpinLockShared(*(_QWORD *)(v8 + 624) + 192LL);
  v18 = *(_QWORD *)(*(_QWORD *)(v8 + 624) + 208LL);
  if ( *(_QWORD *)(v8 + 208) != v18 )
  {
    SkAcquireSpinLockExclusiveAtDpcLevel(v16);
    if ( *(_QWORD *)(v8 + 208) != v18 )
    {
      LOBYTE(v19) = -1;
      SkeFlushEntireTb(v19, v8);
      *(_QWORD *)(v8 + 208) = v18;
    }
    *(_DWORD *)(v8 + 192) = 0;
    SkTrackSpinLockRelease();
  }
  SkAcquireSpinLockSharedAtDpcLevel(v17);
  SkAcquireSpinLockSharedAtDpcLevel(v16);
  while ( v6 )
  {
    ValidEnclaveContainerPte = (unsigned __int64 *)SkmiGetValidEnclaveContainerPte(v7);
    if ( !ValidEnclaveContainerPte
      || (v21 = *ValidEnclaveContainerPte, (*(_BYTE *)ValidEnclaveContainerPte & 3) == 1) && !v5
      || (v21 & 1) == 0 )
    {
      v16 = v110;
      _InterlockedDecrement(v110);
      SkTrackSpinLockRelease();
      v17 = v8 + 8;
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 8));
      SkTrackSpinLockRelease();
      LOBYTE(v104) = v107;
      RtlpReleasePropStoreLockShared(*(_QWORD *)(v8 + 624) + 192LL, v104);
      v102 = v7;
      v103 = (-(__int64)(v5 != 0) & 0xFFFFFFFFFFFFFFFEuLL) + 131074;
      goto LABEL_123;
    }
    ValidPteAddress = (unsigned __int64 *)SkmiGetValidPteAddress(v9, 0);
    if ( !ValidPteAddress )
      goto LABEL_121;
    v23 = *ValidPteAddress;
    if ( (*(_BYTE *)ValidPteAddress & 3) == 1 && v5 )
    {
      v105 = -1073741819;
      goto LABEL_127;
    }
    if ( (v23 & 1) == 0 )
    {
LABEL_121:
      v16 = v110;
      _InterlockedDecrement(v110);
      SkTrackSpinLockRelease();
      v17 = v8 + 8;
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 8));
      SkTrackSpinLockRelease();
      LOBYTE(v101) = v107;
      RtlpReleasePropStoreLockShared(*(_QWORD *)(v8 + 624) + 192LL, v101);
      v102 = v9;
      v103 = v5 != 0 ? 2 : 0;
LABEL_123:
      result = SkmmAccessFault(v103, v102, 1);
      if ( (int)result < 0 )
        return result;
      v110 = v16;
      goto LABEL_17;
    }
    v24 = v21 >> 12;
    v25 = v23 >> 12;
    v111 = (unsigned int)v9;
    v26 = 4096 - (unsigned int)(v9 & 0xFFF);
    if ( v26 > v6 )
      LODWORD(v26) = v6;
    v112 = (unsigned int)v7;
    v27 = 4096 - (v7 & 0xFFF);
    if ( (unsigned int)(v7 & 0xFFF) + (unsigned int)v26 <= 0x1000 )
      v27 = v26;
    Size = v27;
    HyperspacePte = SkmiGetHyperspacePte();
    v29 = (__int64 *)SkmiGetHyperspacePte();
    v30 = (__int64)v29;
    if ( a4 )
    {
      v31 = (v24 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
      PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v31, *(_QWORD *)HyperspacePte);
      v35 = PteTrace;
      if ( PteTrace )
      {
        v36 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v33 + 64));
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v37 = KeGetPcr()->NtTib.StackBase;
          if ( v37 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v37, 8u, v36, &Size_4) )
            {
              *(_QWORD *)(v35 + 40) = retaddr;
              *v36 = (PVOID)SkmiGetInstructionPointer(v39, v38);
            }
          }
        }
        v34 = 0xFFFFFFFFFF000LL;
      }
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
      {
        v40 = KeGetPcr()->NtTib.StackBase;
        v41 = v40 ? v40[10] : 0LL;
        v42 = *(_QWORD *)(v41 + 232);
        if ( v42 )
        {
          v43 = SkiKvaShadowMode;
          *(_QWORD *)(v42 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v31;
          if ( v43 != 2 && (v31 & 1) != 0 )
            v31 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)HyperspacePte = v31;
      v44 = v34 & (v25 << 12) ^ 0x8000000000000063uLL;
      v45 = SkmiGetPteTrace(0, v30, 0, v44, *(_QWORD *)v30);
      v46 = v45;
      if ( v45 )
      {
        v47 = (PVOID *)(v45 + 32);
        memset_0((void *)(v45 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v48 = KeGetPcr()->NtTib.StackBase;
          if ( v48 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v48, 8u, v47, &Size_4) )
            {
              *(_QWORD *)(v46 + 40) = retaddr;
              *v47 = (PVOID)SkmiGetInstructionPointer(v50, v49);
            }
          }
        }
      }
      if ( (unsigned __int64)v30 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v30 < 0xFFFFF6FB7DBED800uLL )
      {
        v51 = KeGetPcr()->NtTib.StackBase;
        v52 = v51 ? v51[10] : 0LL;
        v53 = *(_QWORD *)(v52 + 232);
        if ( v53 )
        {
          v54 = SkiKvaShadowMode;
          *(_QWORD *)(v53 + 8 * ((v30 >> 3) & 0x1FF)) = v44;
          if ( v54 != 2 && (v44 & 1) != 0 )
            v44 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v30 = v44;
      v55 = (const void *)((v112 & 0xFFF) + (HyperspacePte << 25 >> 16));
      v56 = v30 << 25;
      v57 = v111 & 0xFFF;
    }
    else
    {
      v58 = (v25 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
      v59 = SkmiGetPteTrace(0, (_DWORD)v29, 0, v58, *v29);
      v61 = v59;
      if ( v59 )
      {
        v62 = (PVOID *)(v59 + 32);
        memset_0((void *)(v59 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v63 = KeGetPcr()->NtTib.StackBase;
          if ( v63 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v63, 8u, v62, &Size_4) )
            {
              *(_QWORD *)(v61 + 40) = retaddr;
              *v62 = (PVOID)SkmiGetInstructionPointer(v65, v64);
            }
          }
        }
        v60 = 0xFFFFFFFFFF000LL;
      }
      if ( (unsigned __int64)v30 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v30 < 0xFFFFF6FB7DBED800uLL )
      {
        v66 = KeGetPcr()->NtTib.StackBase;
        v67 = v66 ? v66[10] : 0LL;
        v68 = *(_QWORD *)(v67 + 232);
        if ( v68 )
        {
          v69 = SkiKvaShadowMode;
          *(_QWORD *)(v68 + 8 * ((v30 >> 3) & 0x1FF)) = v58;
          if ( v69 != 2 && (v58 & 1) != 0 )
            v58 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v30 = v58;
      v70 = v60 & (v24 << 12) ^ 0x8000000000000063uLL;
      v71 = SkmiGetPteTrace(0, HyperspacePte, 0, v70, *(_QWORD *)HyperspacePte);
      v72 = v71;
      if ( v71 )
      {
        v73 = (PVOID *)(v71 + 32);
        memset_0((void *)(v71 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v74 = KeGetPcr()->NtTib.StackBase;
          if ( v74 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v74, 8u, v73, &Size_4) )
            {
              *(_QWORD *)(v72 + 40) = retaddr;
              *v73 = (PVOID)SkmiGetInstructionPointer(v76, v75);
            }
          }
        }
      }
      if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
        && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
      {
        v77 = KeGetPcr()->NtTib.StackBase;
        v78 = v77 ? v77[10] : 0LL;
        v79 = *(_QWORD *)(v78 + 232);
        if ( v79 )
        {
          v80 = SkiKvaShadowMode;
          *(_QWORD *)(v79 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v70;
          if ( v80 != 2 && (v70 & 1) != 0 )
            v70 |= 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)HyperspacePte = v70;
      v55 = (const void *)((v111 & 0xFFF) + (v30 << 25 >> 16));
      v56 = HyperspacePte << 25;
      v57 = v112 & 0xFFF;
    }
    memmove((void *)(v57 + (v56 >> 16)), v55, Size);
    v81 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
    v83 = v81;
    if ( v81 )
    {
      v84 = (PVOID *)(v81 + 32);
      memset_0((void *)(v81 + 32), 0, (unsigned int)(v82 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v85 = KeGetPcr()->NtTib.StackBase;
        if ( v85 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v85, 8u, v84, &Size_4) )
          {
            *(_QWORD *)(v83 + 40) = retaddr;
            *v84 = (PVOID)SkmiGetInstructionPointer(v87, v86);
          }
        }
      }
    }
    if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
      && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
    {
      v88 = KeGetPcr()->NtTib.StackBase;
      v89 = v88 ? v88[10] : 0LL;
      v90 = *(_QWORD *)(v89 + 232);
      if ( v90 )
        *(_QWORD *)(v90 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)HyperspacePte = 0;
    SkmiReleaseHyperspacePte(HyperspacePte);
    v91 = SkmiGetPteTrace(0, v30, 0, 0, *(_QWORD *)v30);
    v93 = v91;
    if ( v91 )
    {
      v94 = (PVOID *)(v91 + 32);
      memset_0((void *)(v91 + 32), 0, (unsigned int)(v92 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v95 = KeGetPcr()->NtTib.StackBase;
        if ( v95 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v95, 8u, v94, &Size_4) )
          {
            *(_QWORD *)(v93 + 40) = retaddr;
            *v94 = (PVOID)SkmiGetInstructionPointer(v97, v96);
          }
        }
      }
    }
    if ( (unsigned __int64)v30 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v30 < 0xFFFFF6FB7DBED800uLL )
    {
      v98 = KeGetPcr()->NtTib.StackBase;
      if ( v98 )
        v99 = v98[10];
      else
        v99 = 0;
      v100 = *(_QWORD *)(v99 + 232);
      if ( v100 )
        *(_QWORD *)(v100 + 8 * ((v30 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)v30 = 0;
    SkmiReleaseHyperspacePte(v30);
    v5 = a4;
    v6 = v115 - Size;
    v9 = Size + v113;
    v115 = v6;
    v113 = v9;
    v7 += Size;
  }
  v105 = 0;
LABEL_127:
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 192));
  SkTrackSpinLockRelease();
  _InterlockedDecrement((volatile signed __int32 *)(v8 + 8));
  SkTrackSpinLockRelease();
  LOBYTE(v106) = v107;
  RtlpReleasePropStoreLockShared(*(_QWORD *)(v8 + 624) + 192LL, v106);
  return v105;
}

```

## disassembly

```asm
0x14006977c  mov     [rsp+arg_0], rbx
0x140069781  mov     [rsp+arg_18], r9b
0x140069786  mov     [rsp+arg_10], r8
0x14006978b  push    rbp
0x14006978c  push    rsi
0x14006978d  push    rdi
0x14006978e  push    r12
0x140069790  push    r13
0x140069792  push    r14
0x140069794  push    r15
0x140069796  sub     rsp, 60h
0x14006979a  mov     rax, gs:8
0x1400697a3  mov     r13b, r9b
0x1400697a6  mov     rbp, r8
0x1400697a9  mov     r12, rdx
0x1400697ac  test    rax, rax
0x1400697af  jz      loc_14006A178
0x1400697b5  mov     r14, [rax+50h]
0x1400697b9  test    r14, r14
0x1400697bc  jz      loc_14006A178
0x1400697c2  test    dword ptr [r14], 200h
0x1400697c9  jz      loc_14006A178
0x1400697cf  test    r9b, r9b
0x1400697d2  mov     rsi, rcx
0x1400697d5  cmovz   rsi, rdx
0x1400697d9  cmovz   r12, rcx
0x1400697dd  mov     [rsp+98h+var_40], rsi
0x1400697e2  lea     r9, [rsi+r8]
0x1400697e6  cmp     r9, rsi
0x1400697e9  jbe     loc_14006A171
0x1400697ef  add     r8, r12
0x1400697f2  cmp     r8, r12
0x1400697f5  jbe     loc_14006A171
0x1400697fb  mov     eax, [r14+230h]
0x140069802  mov     edx, [r14+238h]
0x140069809  mov     ecx, edx
0x14006980b  and     ecx, 0FFFh
0x140069811  shl     rcx, 20h
0x140069815  or      rcx, rax
0x140069818  mov     rax, rsi
0x14006981b  shr     rax, 0Ch
0x14006981f  cmp     rax, rcx
0x140069822  jb      short loc_14006985E
0x140069824  mov     eax, [r14+234h]
0x14006982b  and     edx, 0FFF000h
0x140069831  shl     rdx, 14h
0x140069835  or      rdx, rax
0x140069838  lea     rax, [r9-1]
0x14006983c  shr     rax, 0Ch
0x140069840  cmp     rax, rdx
0x140069843  jnb     short loc_14006985E
0x140069845  mov     rax, r12
0x140069848  shr     rax, 0Ch
0x14006984c  cmp     rax, rcx
0x14006984f  jnb     short loc_140069868
0x140069851  lea     rax, [r8-1]
0x140069855  shr     rax, 0Ch
0x140069859  cmp     rax, rcx
0x14006985c  jb      short loc_14006988C
0x14006985e  mov     eax, 0C0000018h
0x140069863  jmp     loc_14006A17D
0x140069868  cmp     rax, rdx
0x14006986b  jbe     short loc_14006985E
0x14006986d  mov     rax, 7FFFFFFF0000h
0x140069877  cmp     r8, rax
0x14006987a  ja      short loc_14006985E
0x14006987c  mov     rax, r12
0x14006987f  sar     rax, 2Fh
0x140069883  inc     rax
0x140069886  cmp     rax, 1
0x14006988a  ja      short loc_14006985E
0x14006988c  lea     rax, [r14+0C0h]
0x140069893  mov     r15, rax
0x140069896  mov     [rsp+98h+var_58], rax
0x14006989b  lea     rdi, [r14+8]
0x14006989f  mov     rcx, [r14+270h]
0x1400698a6  add     rcx, 0C0h
0x1400698ad  call    SkAcquireSpinLockShared
0x1400698b2  mov     rcx, [r14+270h]
0x1400698b9  mov     [rsp+98h+var_68], al
0x1400698bd  mov     rbx, [rcx+0D0h]
0x1400698c4  cmp     [r14+0D0h], rbx
0x1400698cb  jz      short loc_1400698FF
0x1400698cd  mov     rcx, r15
0x1400698d0  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x1400698d5  cmp     [r14+0D0h], rbx
0x1400698dc  jz      short loc_1400698EF
0x1400698de  mov     rdx, r14
0x1400698e1  mov     cl, 0FFh
0x1400698e3  call    SkeFlushEntireTb
0x1400698e8  mov     [r14+0D0h], rbx
0x1400698ef  mov     dword ptr [r14+0C0h], 0
0x1400698fa  call    SkTrackSpinLockRelease
0x1400698ff  mov     rcx, rdi
0x140069902  call    SkAcquireSpinLockSharedAtDpcLevel
0x140069907  mov     rcx, r15
0x14006990a  call    SkAcquireSpinLockSharedAtDpcLevel
0x14006990f  xor     r10d, r10d
0x140069912  test    rbp, rbp
0x140069915  jz      loc_14006A13C
0x14006991b  mov     rcx, r12
0x14006991e  call    SkmiGetValidEnclaveContainerPte
0x140069923  test    rax, rax
0x140069926  jz      loc_14006A0D5
0x14006992c  mov     rdi, [rax]
0x14006992f  mov     al, [rax]
0x140069931  and     al, 3
0x140069933  cmp     al, 1
0x140069935  jnz     short loc_140069940
0x140069937  test    r13b, r13b
0x14006993a  jz      loc_14006A0D5
0x140069940  test    dil, 1
0x140069944  jz      loc_14006A0D5
0x14006994a  xor     edx, edx
0x14006994c  mov     rcx, rsi
0x14006994f  call    SkmiGetValidPteAddress
0x140069954  test    rax, rax
0x140069957  jz      loc_14006A092
0x14006995d  mov     rbx, [rax]
0x140069960  mov     al, [rax]
0x140069962  and     al, 3
0x140069964  cmp     al, 1
0x140069966  jnz     short loc_140069971
0x140069968  test    r13b, r13b
0x14006996b  jnz     loc_14006A135
0x140069971  test    bl, 1
0x140069974  jz      loc_14006A092
0x14006997a  mov     ecx, esi
0x14006997c  shr     rdi, 0Ch
0x140069980  and     ecx, 0FFFh
0x140069986  shr     rbx, 0Ch
0x14006998a  mov     r9d, 1000h
0x140069990  mov     eax, esi
0x140069992  mov     edx, r9d
0x140069995  mov     [rsp+98h+var_50], rax
0x14006999a  sub     edx, ecx
0x14006999c  cmp     rdx, rbp
0x14006999f  jbe     short loc_1400699A3
0x1400699a1  mov     edx, ebp
0x1400699a3  mov     eax, r12d
0x1400699a6  mov     r8d, r9d
0x1400699a9  mov     [rsp+98h+var_48], rax
0x1400699ae  and     eax, 0FFFh
0x1400699b3  sub     r8d, eax
0x1400699b6  lea     ecx, [rax+rdx]
0x1400699b9  cmp     ecx, r9d
0x1400699bc  cmovbe  r8d, edx
0x1400699c0  mov     dword ptr [rsp+98h+Size], r8d
0x1400699c5  call    SkmiGetHyperspacePte
0x1400699ca  mov     r15, rax
0x1400699cd  call    SkmiGetHyperspacePte
0x1400699d2  xor     r10d, r10d
0x1400699d5  xor     r8d, r8d
0x1400699d8  mov     r13, rax
0x1400699db  mov     r11, 0FFFFFFFFFF000h
0x1400699e5  mov     rax, 8000000000000021h
0x1400699ef  cmp     [rsp+98h+arg_18], r10b
0x1400699f7  jz      loc_140069C4D
0x1400699fd  mov     rcx, [r15]
0x140069a00  mov     rdx, r15
0x140069a03  shl     rdi, 0Ch
0x140069a07  mov     [rsp+98h+var_78], rcx
0x140069a0c  and     rdi, r11
0x140069a0f  xor     rdi, rax
0x140069a12  xor     ecx, ecx
0x140069a14  mov     r9, rdi
0x140069a17  call    SkmiGetPteTrace
0x140069a1c  mov     rbp, rax
0x140069a1f  test    rax, rax
0x140069a22  jz      short loc_140069A85
0x140069a24  lea     rsi, [rax+20h]
0x140069a28  xor     edx, edx; Val
0x140069a2a  mov     rcx, rsi; void *
0x140069a2d  lea     r8d, [r10+40h]; Size
0x140069a31  call    memset_0
0x140069a36  test    cs:SkmiFlags, 400000h
0x140069a40  jz      short loc_140069A7B
0x140069a42  mov     rcx, gs:8; FramesToSkip
0x140069a4b  test    rcx, rcx
0x140069a4e  jz      short loc_140069A7B
0x140069a50  lea     r9, [rsp+98h+Size+4]; BackTraceHash
0x140069a55  mov     r8, rsi; BackTrace
0x140069a58  mov     edx, 8; FramesToCapture
0x140069a5d  call    RtlCaptureStackBackTrace
0x140069a62  test    ax, ax
0x140069a65  jnz     short loc_140069A7B
0x140069a67  mov     rax, [rsp+98h]
0x140069a6f  mov     [rbp+28h], rax
0x140069a73  call    SkmiGetInstructionPointer
0x140069a78  mov     [rsi], rax
0x140069a7b  mov     r11, 0FFFFFFFFFF000h
0x140069a85  mov     rax, 0FFFFF6FB7DBED000h
0x140069a8f  mov     rax, rax
0x140069a92  cmp     r15, rax
0x140069a95  jb      short loc_140069AFE
0x140069a97  mov     rax, 0FFFFF6FB7DBED800h
0x140069aa1  mov     rax, rax
0x140069aa4  xor     ebp, ebp
0x140069aa6  cmp     r15, rax
0x140069aa9  jnb     short loc_140069B00
0x140069aab  mov     rax, gs:8
0x140069ab4  test    rax, rax
0x140069ab7  jz      short loc_140069ABF
0x140069ab9  mov     rcx, [rax+50h]
0x140069abd  jmp     short loc_140069AC2
0x140069abf  mov     rcx, rbp
0x140069ac2  mov     rdx, [rcx+0E8h]
0x140069ac9  test    rdx, rdx
0x140069acc  jz      short loc_140069B00
0x140069ace  mov     ecx, cs:SkiKvaShadowMode
0x140069ad4  mov     rax, r15
0x140069ad7  sar     rax, 3
0x140069adb  and     eax, 1FFh
0x140069ae0  mov     [rdx+rax*8], rdi
0x140069ae4  cmp     ecx, 2
0x140069ae7  jz      short loc_140069B00
0x140069ae9  test    dil, 1
0x140069aed  jz      short loc_140069B00
0x140069aef  mov     rax, 8000000000000000h
0x140069af9  or      rdi, rax
0x140069afc  jmp     short loc_140069B00
0x140069afe  xor     ebp, ebp
0x140069b00  shl     rbx, 0Ch
0x140069b04  mov     rax, 8000000000000063h
0x140069b0e  mov     [r15], rdi
0x140069b11  and     rbx, r11
0x140069b14  xor     rbx, rax
0x140069b17  xor     r8d, r8d
0x140069b1a  mov     rax, [r13+0]
0x140069b1e  mov     r9, rbx
0x140069b21  mov     rdx, r13
0x140069b24  mov     [rsp+98h+var_78], rax
0x140069b29  xor     ecx, ecx
0x140069b2b  call    SkmiGetPteTrace
0x140069b30  mov     rsi, rax
0x140069b33  test    rax, rax
0x140069b36  jz      short loc_140069B8F
0x140069b38  xor     edx, edx; Val
0x140069b3a  lea     rdi, [rax+20h]
0x140069b3e  mov     rcx, rdi; void *
0x140069b41  lea     r8d, [rdx+40h]; Size
0x140069b45  call    memset_0
0x140069b4a  test    cs:SkmiFlags, 400000h
0x140069b54  jz      short loc_140069B8F
0x140069b56  mov     rcx, gs:8; FramesToSkip
0x140069b5f  test    rcx, rcx
0x140069b62  jz      short loc_140069B8F
0x140069b64  lea     r9, [rsp+98h+Size+4]; BackTraceHash
0x140069b69  mov     r8, rdi; BackTrace
0x140069b6c  mov     edx, 8; FramesToCapture
0x140069b71  call    RtlCaptureStackBackTrace
0x140069b76  test    ax, ax
0x140069b79  jnz     short loc_140069B8F
0x140069b7b  mov     rax, [rsp+98h]
0x140069b83  mov     [rsi+28h], rax
0x140069b87  call    SkmiGetInstructionPointer
0x140069b8c  mov     [rdi], rax
0x140069b8f  mov     rax, 0FFFFF6FB7DBED000h
0x140069b99  mov     rax, rax
0x140069b9c  cmp     r13, rax
0x140069b9f  jb      short loc_140069C03
0x140069ba1  mov     rax, 0FFFFF6FB7DBED800h
0x140069bab  mov     rax, rax
0x140069bae  cmp     r13, rax
0x140069bb1  jnb     short loc_140069C03
0x140069bb3  mov     rax, gs:8
0x140069bbc  test    rax, rax
0x140069bbf  jz      short loc_140069BC7
0x140069bc1  mov     rcx, [rax+50h]
0x140069bc5  jmp     short loc_140069BCA
0x140069bc7  mov     rcx, rbp
0x140069bca  mov     rdx, [rcx+0E8h]
0x140069bd1  test    rdx, rdx
0x140069bd4  jz      short loc_140069C03
0x140069bd6  mov     ecx, cs:SkiKvaShadowMode
0x140069bdc  mov     rax, r13
0x140069bdf  sar     rax, 3
0x140069be3  and     eax, 1FFh
0x140069be8  mov     [rdx+rax*8], rbx
0x140069bec  cmp     ecx, 2
0x140069bef  jz      short loc_140069C03
0x140069bf1  test    bl, 1
0x140069bf4  jz      short loc_140069C03
0x140069bf6  mov     rax, 8000000000000000h
0x140069c00  or      rbx, rax
0x140069c03  mov     [r13+0], rbx
0x140069c07  mov     rax, 0FFFFF68000000000h
0x140069c11  mov     rax, rax
0x140069c14  mov     rcx, [rsp+98h+var_48]
0x140069c19  mov     ebx, 0FFFh
0x140069c1e  and     rcx, rbx
0x140069c21  shl     rax, 19h
0x140069c25  mov     rdx, r15
0x140069c28  shl     rdx, 19h
0x140069c2c  sub     rdx, rax
0x140069c2f  sar     rdx, 10h
0x140069c33  add     rdx, rcx
0x140069c36  mov     rcx, r13
0x140069c39  shl     rcx, 19h
0x140069c3d  sub     rcx, rax
  ... truncated ...
```
