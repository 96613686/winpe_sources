# SkmiCompleteEnclaveContainerFault

- ea: `0x140083bc8`
- end: `0x1400843c1`
- name: `SkmiCompleteEnclaveContainerFault`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400855c0`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x14000b980`
- `0x14000e460`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020424`
- `0x14002aeac`
- `0x14002b534`
- `0x140071224`
- `0x140071374`
- `0x140081290`
- `0x140083bc8`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCompleteEnclaveContainerFault(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  __int64 v7; // rbx
  bool v9; // cf
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  char v15; // r9
  __int64 v16; // r8
  _BYTE *v17; // rdx
  unsigned int v18; // r14d
  __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned int v21; // r12d
  unsigned __int64 v22; // rsi
  __int64 v23; // rax
  __int64 v24; // r15
  unsigned __int64 v25; // rbx
  __int64 v26; // rax
  __int64 PteTrace; // rax
  unsigned __int64 v28; // r10
  __int64 v29; // r11
  PVOID *v30; // r12
  PVOID StackBase; // rcx
  USHORT v32; // ax
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  int v39; // edx
  __int64 v40; // rax
  __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rax
  ULONG_PTR v44; // r12
  ULONG_PTR v45; // rbx
  __int64 v46; // rax
  __int64 v47; // r14
  PVOID *v48; // rsi
  PVOID v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  int v55; // ecx
  _QWORD *v56; // rax
  ULONG_PTR v57; // rsi
  ULONG_PTR v58; // rbx
  __int64 v59; // rax
  unsigned __int64 v60; // rcx
  __int64 v61; // r15
  PVOID *v62; // r14
  __int64 v63; // rdx
  _QWORD *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r14
  unsigned int i; // ecx
  __int64 v68; // rdi
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // r15
  PVOID *v72; // rsi
  PVOID v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rcx
  _QWORD *v76; // rax
  __int64 v77; // rcx
  __int64 v78; // rdx
  int v79; // ecx
  char v80; // [rsp+30h] [rbp-61h]
  unsigned int v81; // [rsp+34h] [rbp-5Dh]
  int v82; // [rsp+38h] [rbp-59h]
  ULONG BackTraceHash; // [rsp+3Ch] [rbp-55h] BYREF
  __int64 v84; // [rsp+40h] [rbp-51h]
  __int64 v85; // [rsp+48h] [rbp-49h] BYREF
  ULONG_PTR v86; // [rsp+50h] [rbp-41h]
  __int64 v87; // [rsp+58h] [rbp-39h]
  __int64 v88; // [rsp+60h] [rbp-31h]
  __int128 v89; // [rsp+68h] [rbp-29h]
  _QWORD *v90; // [rsp+78h] [rbp-19h]
  _QWORD v91[3]; // [rsp+80h] [rbp-11h]
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+57h]

  v87 = a1;
  v90 = 0;
  v7 = *(_QWORD *)(a1 + 624);
  v9 = (*a4 & 0x20000000000000LL) != 0;
  v89 = 0;
  v82 = v9 ? 4 : 1;
  if ( *(_QWORD *)(v7 + 200) != a5 )
    return 3221225494LL;
  v11 = a3;
  v12 = 3;
  do
  {
    --v12;
    v11 = ((v11 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    *((_QWORD *)&v89 + v12) = v11;
  }
  while ( v12 );
  v13 = v7 + 8;
  v88 = v7 + 8;
  while ( 1 )
  {
    v15 = SkAcquireSpinLockExclusive(v13);
    v80 = v15;
    if ( *(_QWORD *)(v7 + 200) != a5 )
    {
      v20 = -1073741802;
      goto LABEL_101;
    }
    v16 = 0;
    do
    {
      v17 = (_BYTE *)*((_QWORD *)&v89 + v16);
      if ( (*v17 & 1) == 0 )
        break;
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < 3 );
    v18 = 3 - v16;
    if ( (_DWORD)v16 == 3 )
      break;
    v19 = *(_QWORD *)(a2 + 240);
    while ( _interlockedbittestandset((volatile signed __int32 *)v19, 0) )
      _mm_pause();
    if ( *(_DWORD *)(v19 + 4) >= v18 )
      break;
    LOBYTE(v17) = v15;
    **(_DWORD **)(a2 + 240) = 0;
    SkReleaseSpinLockExclusive(v7 + 8, v17);
    SkmiReplenishPartitionPages(a2, v18);
    v13 = v7 + 8;
  }
  v86 = *a4 & 0xFFFFFFFFFFFFFLL;
  if ( (unsigned int)SkmiIncrementSharedPageReferenceCount(v86) )
  {
    v21 = 0;
    v22 = *(_QWORD *)(v7 + 64) >> 12;
    v81 = 0;
    do
    {
      v23 = v21;
      v24 = *((_QWORD *)&v89 + v21);
      v25 = *(_QWORD *)v24;
      if ( *(_QWORD *)v24 )
      {
        v22 = (v25 >> 12) & 0xFFFFFFFFFFLL;
      }
      else
      {
        v26 = SkmiObtainEnclaveContainerPage(a2, 0xFFFFFFFFFFLL);
        v84 = v26;
        if ( !--v18 )
          **(_DWORD **)(a2 + 240) = 0;
        v25 = ((v26 & 0xFFFFFFFFFFLL) << 12) | 0x67;
        PteTrace = SkmiGetPteTrace(0, v24, 0, ((_DWORD)v26 << 12) | 0x67u, *(_QWORD *)v24);
        v85 = PteTrace;
        if ( PteTrace )
        {
          v30 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          v29 = 0;
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              v32 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v30, &BackTraceHash);
              v29 = 0;
              if ( !v32 )
              {
                v34 = v85;
                *(_QWORD *)(v85 + 40) = retaddr;
                *v30 = (PVOID)SkmiGetInstructionPointer(v34, v33);
              }
            }
          }
          v28 = v84;
          v21 = v81;
        }
        v35 = v25;
        if ( (unsigned __int64)v24 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v24 < 0xFFFFF6FB7DBED800uLL )
        {
          v36 = KeGetPcr()->NtTib.StackBase;
          v37 = v36 ? v36[10] : v29;
          v38 = *(_QWORD *)(v37 + 232);
          if ( v38 )
          {
            v39 = SkiKvaShadowMode;
            *(_QWORD *)(v38 + 8 * ((v24 >> 3) & 0x1FF)) = v25;
            if ( v39 != 2 )
              v35 = v25 | 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v24 = v35;
        if ( v22 > 0xFFFFFFFFFFLL )
          __fastfail(0x3Fu);
        v40 = *(_QWORD *)(8 * v22 - 0x180000000000LL);
        v41 = v40 + 1;
        v42 = (v40 ^ (v40 + 1)) & 0xFFFFF00000000000uLL;
        v23 = v21;
        *(_QWORD *)(8 * v22 - 0x180000000000LL) = v41 ^ v42;
        v22 = v28;
      }
      v81 = ++v21;
      v91[v23] = v25 | 0x80000000000000LL;
    }
    while ( v21 < 3 );
    v43 = *(_QWORD *)a3;
    v44 = v86;
    if ( *(_QWORD *)a3 )
    {
      v57 = (v43 >> 12) & 0xFFFFFFFFFFLL;
      if ( v86 != v57 || (v82 & 4) != 0 && (v43 & 2) == 0 )
      {
        v58 = (v86 << 12) ^ (SkmiProtectionToPte[v82] ^ (v86 << 12)) & 0xFFF0000000000FFFuLL | 4;
        v59 = SkmiGetPteTrace(0, a3, 0, v58, *(_QWORD *)a3);
        v61 = v59;
        if ( v59 )
        {
          v62 = (PVOID *)(v59 + 32);
          memset_0((void *)(v59 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v60 = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
            if ( v60 )
            {
              if ( !RtlCaptureStackBackTrace(v60, 8u, v62, &BackTraceHash) )
              {
                *(_QWORD *)(v61 + 40) = retaddr;
                *v62 = (PVOID)SkmiGetInstructionPointer(v60, v63);
              }
            }
          }
        }
        if ( (unsigned __int64)a3 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a3 < 0xFFFFF6FB7DBED800uLL )
        {
          v64 = KeGetPcr()->NtTib.StackBase;
          v60 = v64 ? v64[10] : 0LL;
          v65 = *(_QWORD *)(v60 + 232);
          if ( v65 )
          {
            v60 = (unsigned int)SkiKvaShadowMode;
            *(_QWORD *)(v65 + 8 * ((a3 >> 3) & 0x1FF)) = v58;
            if ( (_DWORD)v60 != 2 && (v58 & 1) != 0 )
              v58 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)a3 = v58;
        if ( v44 != v57 )
        {
          LOBYTE(v60) = -1;
          v85 = a3 << 25 >> 16;
          SkeFlushRangeListTb(v60, 0, 1, &v85);
        }
      }
      SkmiDecrementPageReferenceCount(v57);
    }
    else
    {
      v45 = (v86 << 12) ^ (SkmiProtectionToPte[v82] ^ (v86 << 12)) & 0xFFF0000000000FFFuLL | 4;
      v46 = SkmiGetPteTrace(
              0,
              a3,
              0,
              ((_DWORD)v86 << 12) ^ (LODWORD(SkmiProtectionToPte[v82]) ^ ((_DWORD)v86 << 12)) & 0xFFF | 4u,
              *(_QWORD *)a3);
      v47 = v46;
      if ( v46 )
      {
        v48 = (PVOID *)(v46 + 32);
        memset_0((void *)(v46 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v49 = KeGetPcr()->NtTib.StackBase;
          if ( v49 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v49, 8u, v48, &BackTraceHash) )
            {
              *(_QWORD *)(v47 + 40) = retaddr;
              *v48 = (PVOID)SkmiGetInstructionPointer(v51, v50);
            }
          }
        }
      }
      if ( (unsigned __int64)a3 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)a3 < 0xFFFFF6FB7DBED800uLL )
      {
        v52 = KeGetPcr()->NtTib.StackBase;
        v53 = v52 ? v52[10] : 0LL;
        v54 = *(_QWORD *)(v53 + 232);
        if ( v54 )
        {
          v55 = SkiKvaShadowMode;
          *(_QWORD *)(v54 + 8 * ((a3 >> 3) & 0x1FF)) = v45;
          if ( v55 != 2 && (v45 & 1) != 0 )
            v45 |= 0x8000000000000000uLL;
        }
      }
      v56 = v90;
      *(_QWORD *)a3 = v45;
      *(_QWORD *)(8 * ((*v56 >> 12) & 0xFFFFFFFFFFLL) - 0x180000000000LL) = (*(_QWORD *)(8
                                                                                       * ((*v56 >> 12) & 0xFFFFFFFFFFLL)
                                                                                       - 0x180000000000LL)
                                                                           + 1LL)
                                                                          ^ (*(_QWORD *)(8
                                                                                       * ((*v56 >> 12) & 0xFFFFFFFFFFLL)
                                                                                       - 0x180000000000LL)
                                                                           ^ (*(_QWORD *)(8
                                                                                        * ((*v56 >> 12) & 0xFFFFFFFFFFLL)
                                                                                        - 0x180000000000LL)
                                                                            + 1LL))
                                                                          & 0xFFFFF00000000000uLL;
    }
    v66 = v87;
    SkiAttachProcess(v87);
    if ( (*(_DWORD *)(v66 + 676) & 1) == 0 )
    {
      SkAcquireSpinLockSharedAtDpcLevel(v66 + 8);
      for ( i = 0; i < 3; ++i )
      {
        v68 = *((_QWORD *)&v89 + i);
        if ( !*(_QWORD *)v68 )
        {
          v69 = v91[i];
          v70 = SkmiGetPteTrace(0, *((_QWORD *)&v89 + i), 0, v69, *(_QWORD *)v68);
          v71 = v70;
          if ( v70 )
          {
            v72 = (PVOID *)(v70 + 32);
            memset_0((void *)(v70 + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v73 = KeGetPcr()->NtTib.StackBase;
              if ( v73 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v73, 8u, v72, &BackTraceHash) )
                {
                  *(_QWORD *)(v71 + 40) = retaddr;
                  *v72 = (PVOID)SkmiGetInstructionPointer(v75, v74);
                }
              }
            }
          }
          if ( (unsigned __int64)v68 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v68 < 0xFFFFF6FB7DBED800uLL )
          {
            v76 = KeGetPcr()->NtTib.StackBase;
            if ( v76 )
              v77 = v76[10];
            else
              v77 = 0;
            v78 = *(_QWORD *)(v77 + 232);
            if ( v78 )
            {
              v79 = SkiKvaShadowMode;
              *(_QWORD *)(v78 + 8 * ((v68 >> 3) & 0x1FF)) = v69;
              if ( v79 != 2 && (v69 & 1) != 0 )
                v69 |= 0x8000000000000000uLL;
            }
          }
          *(_QWORD *)v68 = v69;
          break;
        }
        if ( *(_QWORD *)v68 == v91[i] )
          break;
      }
      _InterlockedDecrement((volatile signed __int32 *)(v66 + 8));
      SkTrackSpinLockRelease();
    }
    v20 = 0;
  }
  else
  {
    v20 = -1073741790;
    **(_DWORD **)(a2 + 240) = 0;
  }
  v15 = v80;
LABEL_101:
  LOBYTE(v14) = v15;
  SkReleaseSpinLockExclusive(v88, v14);
  return v20;
}

```

## disassembly

```asm
0x140083bc8  push    rbp
0x140083bca  push    rbx
0x140083bcb  push    rsi
0x140083bcc  push    rdi
0x140083bcd  push    r12
0x140083bcf  push    r13
0x140083bd1  push    r14
0x140083bd3  push    r15
0x140083bd5  lea     rbp, [rsp-17h]
0x140083bda  sub     rsp, 0A8h
0x140083be1  mov     rax, cs:__security_cookie
0x140083be8  xor     rax, rsp
0x140083beb  mov     [rbp+4Fh+var_48], rax
0x140083bef  mov     rsi, [rbp+4Fh+arg_20]
0x140083bf3  mov     rax, rcx
0x140083bf6  mov     [rbp+4Fh+var_88], rcx
0x140083bfa  xorps   xmm0, xmm0
0x140083bfd  xor     ecx, ecx
0x140083bff  mov     r15, r9
0x140083c02  mov     [rbp+4Fh+var_68], rcx
0x140083c06  mov     rdi, r8
0x140083c09  mov     rbx, [rax+270h]
0x140083c10  mov     rcx, 20000000000000h
0x140083c1a  mov     rax, [r9]
0x140083c1d  mov     r13, rdx
0x140083c20  and     rax, rcx
0x140083c23  neg     rax
0x140083c26  movups  [rbp+4Fh+var_78], xmm0
0x140083c2a  sbb     r12d, r12d
0x140083c2d  and     r12d, 3
0x140083c31  inc     r12d
0x140083c34  mov     [rbp+4Fh+var_A8], r12d
0x140083c38  cmp     [rbx+0C8h], rsi
0x140083c3f  jz      short loc_140083C4B
0x140083c41  mov     eax, 0C0000016h
0x140083c46  jmp     loc_1400843A0
0x140083c4b  mov     rcx, rdi
0x140083c4e  mov     r8, 0FFFFF68000000000h
0x140083c58  mov     edx, 3
0x140083c5d  shr     rcx, 9
0x140083c61  mov     rax, 7FFFFFFFF8h
0x140083c6b  and     rcx, rax
0x140083c6e  dec     rdx
0x140083c71  mov     rax, r8
0x140083c74  add     rcx, rax
0x140083c77  mov     qword ptr [rbp+rdx*8+4Fh+var_78], rcx
0x140083c7c  test    rdx, rdx
0x140083c7f  jnz     short loc_140083C5D
0x140083c81  lea     rax, [rbx+8]
0x140083c85  mov     [rbp+4Fh+var_80], rax
0x140083c89  mov     rcx, rax
0x140083c8c  call    SkAcquireSpinLockExclusive
0x140083c91  mov     r9b, al
0x140083c94  mov     [rbp+4Fh+var_B0], al
0x140083c97  cmp     [rbx+0C8h], rsi
0x140083c9e  jnz     loc_14008438D
0x140083ca4  xor     r8d, r8d
0x140083ca7  mov     rdx, qword ptr [rbp+r8*8+4Fh+var_78]
0x140083cac  test    byte ptr [rdx], 1
0x140083caf  jz      short loc_140083CBA
0x140083cb1  inc     r8d
0x140083cb4  cmp     r8d, 3
0x140083cb8  jb      short loc_140083CA7
0x140083cba  mov     r14d, 3
0x140083cc0  sub     r14d, r8d
0x140083cc3  jz      short loc_140083D07
0x140083cc5  mov     rax, [r13+0F0h]
0x140083ccc  jmp     short loc_140083CD0
0x140083cce  pause
0x140083cd0  lock bts dword ptr [rax], 0
0x140083cd5  jb      short loc_140083CCE
0x140083cd7  cmp     [rax+4], r14d
0x140083cdb  jnb     short loc_140083D07
0x140083cdd  mov     rax, [r13+0F0h]
0x140083ce4  lea     rcx, [rbx+8]
0x140083ce8  mov     dl, r9b
0x140083ceb  mov     dword ptr [rax], 0
0x140083cf1  call    SkReleaseSpinLockExclusive
0x140083cf6  mov     edx, r14d
0x140083cf9  mov     rcx, r13
0x140083cfc  call    SkmiReplenishPartitionPages
0x140083d01  lea     rax, [rbx+8]
0x140083d05  jmp     short loc_140083C89
0x140083d07  mov     rax, [r15]
0x140083d0a  mov     rcx, 0FFFFFFFFFFFFFh
0x140083d14  and     rax, rcx
0x140083d17  mov     edx, r12d
0x140083d1a  mov     rcx, rax; BugCheckParameter3
0x140083d1d  mov     [rbp+4Fh+var_90], rax
0x140083d21  call    SkmiIncrementSharedPageReferenceCount
0x140083d26  xor     r11d, r11d
0x140083d29  test    eax, eax
0x140083d2b  jnz     short loc_140083D45
0x140083d2d  mov     rax, [r13+0F0h]
0x140083d34  mov     ebx, 0C0000022h
0x140083d39  mov     [rax], r11d
0x140083d3c  mov     r9b, [rbp+4Fh+var_B0]
0x140083d40  jmp     loc_140084392
0x140083d45  mov     rsi, [rbx+40h]
0x140083d49  mov     r12d, r11d
0x140083d4c  shr     rsi, 0Ch
0x140083d50  mov     rdx, 0FFFFFFFFFFh
0x140083d5a  mov     [rbp+4Fh+var_AC], r11d
0x140083d5e  mov     eax, r12d
0x140083d61  mov     r15, qword ptr [rbp+rax*8+4Fh+var_78]
0x140083d66  mov     rbx, [r15]
0x140083d69  test    rbx, rbx
0x140083d6c  jnz     loc_140083F08
0x140083d72  mov     rcx, r13
0x140083d75  call    SkmiObtainEnclaveContainerPage
0x140083d7a  xor     r11d, r11d
0x140083d7d  mov     [rbp+4Fh+var_A0], rax
0x140083d81  mov     r10, rax
0x140083d84  sub     r14d, 1
0x140083d88  jnz     short loc_140083D94
0x140083d8a  mov     rcx, [r13+0F0h]
0x140083d91  mov     [rcx], r11d
0x140083d94  mov     rbx, rax
0x140083d97  xor     r8d, r8d
0x140083d9a  mov     rax, 0FFFFFFFFFFh
0x140083da4  mov     rdx, r15
0x140083da7  and     rbx, rax
0x140083daa  xor     ecx, ecx
0x140083dac  mov     rax, [r15]
0x140083daf  shl     rbx, 0Ch
0x140083db3  or      rbx, 67h
0x140083db7  mov     [rsp+0E0h+var_C0], rax
0x140083dbc  mov     r9, rbx
0x140083dbf  call    SkmiGetPteTrace
0x140083dc4  mov     [rbp+4Fh+var_98], rax
0x140083dc8  test    rax, rax
0x140083dcb  jz      short loc_140083E31
0x140083dcd  xor     edx, edx; Val
0x140083dcf  lea     r12, [rax+20h]
0x140083dd3  mov     rcx, r12; void *
0x140083dd6  lea     r8d, [rdx+40h]; Size
0x140083dda  call    memset_0
0x140083ddf  xor     r11d, r11d
0x140083de2  test    cs:SkmiFlags, 400000h
0x140083dec  jz      short loc_140083E29
0x140083dee  mov     rcx, gs:8; FramesToSkip
0x140083df7  test    rcx, rcx
0x140083dfa  jz      short loc_140083E29
0x140083dfc  lea     r9, [rbp+4Fh+BackTraceHash]; BackTraceHash
0x140083e00  mov     r8, r12; BackTrace
0x140083e03  lea     edx, [r11+8]; FramesToCapture
0x140083e07  call    RtlCaptureStackBackTrace
0x140083e0c  xor     r11d, r11d
0x140083e0f  test    ax, ax
0x140083e12  jnz     short loc_140083E29
0x140083e14  mov     rax, [rbp+57h]
0x140083e18  mov     rcx, [rbp+4Fh+var_98]
0x140083e1c  mov     [rcx+28h], rax
0x140083e20  call    SkmiGetInstructionPointer
0x140083e25  mov     [r12], rax
0x140083e29  mov     r10, [rbp+4Fh+var_A0]
0x140083e2d  mov     r12d, [rbp+4Fh+var_AC]
0x140083e31  mov     rax, rbx
0x140083e34  mov     rcx, 0FFFFF6FB7DBED000h
0x140083e3e  mov     rcx, rcx
0x140083e41  cmp     r15, rcx
0x140083e44  jb      short loc_140083EA4
0x140083e46  mov     rcx, 0FFFFF6FB7DBED800h
0x140083e50  mov     rcx, rcx
0x140083e53  cmp     r15, rcx
0x140083e56  jnb     short loc_140083EA4
0x140083e58  mov     rcx, gs:8
0x140083e61  test    rcx, rcx
0x140083e64  jz      short loc_140083E6C
0x140083e66  mov     rdx, [rcx+50h]
0x140083e6a  jmp     short loc_140083E6F
0x140083e6c  mov     rdx, r11
0x140083e6f  mov     r8, [rdx+0E8h]
0x140083e76  test    r8, r8
0x140083e79  jz      short loc_140083EA4
0x140083e7b  mov     edx, cs:SkiKvaShadowMode
0x140083e81  mov     rcx, r15
0x140083e84  sar     rcx, 3
0x140083e88  and     ecx, 1FFh
0x140083e8e  mov     [r8+rcx*8], rbx
0x140083e92  cmp     edx, 2
0x140083e95  jz      short loc_140083EA4
0x140083e97  mov     rcx, 8000000000000000h
0x140083ea1  or      rax, rcx
0x140083ea4  mov     [r15], rax
0x140083ea7  mov     rax, 0FFFFEFFFFFFFFFFFh
0x140083eb1  mov     rcx, rax
0x140083eb4  mov     r15, 0FFFFE80000000000h
0x140083ebe  mov     rax, r15
0x140083ec1  sub     rcx, rax
0x140083ec4  sar     rcx, 3
0x140083ec8  cmp     rsi, rcx
0x140083ecb  ja      loc_1400840C1
0x140083ed1  mov     r8, r15
0x140083ed4  mov     rax, [r8+rsi*8]
0x140083ed8  lea     rcx, [rax+1]
0x140083edc  mov     rdx, rcx
0x140083edf  xor     rdx, rax
0x140083ee2  mov     rax, 0FFFFF00000000000h
0x140083eec  and     rdx, rax
0x140083eef  mov     eax, r12d
0x140083ef2  xor     rdx, rcx
0x140083ef5  mov     [r8+rsi*8], rdx
0x140083ef9  mov     rsi, r10
0x140083efc  mov     rdx, 0FFFFFFFFFFh
0x140083f06  jmp     short loc_140083F1C
0x140083f08  mov     rsi, rbx
0x140083f0b  mov     r15, 0FFFFE80000000000h
0x140083f15  shr     rsi, 0Ch
0x140083f19  and     rsi, rdx
0x140083f1c  inc     r12d
0x140083f1f  mov     rcx, 80000000000000h
0x140083f29  or      rbx, rcx
0x140083f2c  mov     [rbp+4Fh+var_AC], r12d
0x140083f30  mov     [rbp+rax*8+4Fh+var_60], rbx
0x140083f35  cmp     r12d, 3
0x140083f39  jb      loc_140083D5E
0x140083f3f  mov     rax, [rdi]
0x140083f42  xor     r13d, r13d
0x140083f45  mov     r12, [rbp+4Fh+var_90]
0x140083f49  test    rax, rax
0x140083f4c  jnz     loc_1400840C8
0x140083f52  mov     eax, [rbp+4Fh+var_A8]
0x140083f55  lea     rdx, SkmiProtectionToPte
0x140083f5c  shl     r12, 0Ch
0x140083f60  xor     r8d, r8d
0x140083f63  mov     rbx, r12
0x140083f66  xor     ecx, ecx
0x140083f68  xor     rbx, [rdx+rax*8]
0x140083f6c  mov     rax, 0FFF0000000000FFFh
0x140083f76  and     rbx, rax
0x140083f79  mov     rdx, rdi
0x140083f7c  mov     rax, [rdi]
0x140083f7f  xor     rbx, r12
0x140083f82  or      rbx, 4
0x140083f86  mov     [rsp+0E0h+var_C0], rax
0x140083f8b  mov     r9, rbx
0x140083f8e  call    SkmiGetPteTrace
0x140083f93  mov     r14, rax
0x140083f96  test    rax, rax
0x140083f99  jz      short loc_140083FEC
0x140083f9b  lea     rsi, [rax+20h]
0x140083f9f  xor     edx, edx; Val
0x140083fa1  mov     rcx, rsi; void *
0x140083fa4  lea     r8d, [r13+40h]; Size
0x140083fa8  call    memset_0
0x140083fad  test    cs:SkmiFlags, 400000h
0x140083fb7  jz      short loc_140083FEC
0x140083fb9  mov     rcx, gs:8; FramesToSkip
0x140083fc2  test    rcx, rcx
0x140083fc5  jz      short loc_140083FEC
0x140083fc7  lea     r9, [rbp+4Fh+BackTraceHash]; BackTraceHash
0x140083fcb  mov     r8, rsi; BackTrace
0x140083fce  lea     edx, [r13+8]; FramesToCapture
0x140083fd2  call    RtlCaptureStackBackTrace
0x140083fd7  test    ax, ax
0x140083fda  jnz     short loc_140083FEC
0x140083fdc  mov     rax, [rbp+57h]
0x140083fe0  mov     [r14+28h], rax
0x140083fe4  call    SkmiGetInstructionPointer
0x140083fe9  mov     [rsi], rax
0x140083fec  mov     r12, 0FFFFF6FB7DBED000h
0x140083ff6  mov     rax, r12
0x140083ff9  cmp     rdi, rax
0x140083ffc  jb      short loc_140084060
0x140083ffe  mov     rax, 0FFFFF6FB7DBED800h
0x140084008  mov     rax, rax
0x14008400b  cmp     rdi, rax
0x14008400e  jnb     short loc_140084060
0x140084010  mov     rax, gs:8
0x140084019  test    rax, rax
0x14008401c  jz      short loc_140084024
0x14008401e  mov     rcx, [rax+50h]
0x140084022  jmp     short loc_140084027
0x140084024  mov     rcx, r13
0x140084027  mov     rdx, [rcx+0E8h]
0x14008402e  test    rdx, rdx
0x140084031  jz      short loc_140084060
0x140084033  mov     ecx, cs:SkiKvaShadowMode
0x140084039  mov     rax, rdi
0x14008403c  sar     rax, 3
0x140084040  and     eax, 1FFh
0x140084045  mov     [rdx+rax*8], rbx
0x140084049  cmp     ecx, 2
0x14008404c  jz      short loc_140084060
0x14008404e  test    bl, 1
0x140084051  jz      short loc_140084060
0x140084053  mov     rax, 8000000000000000h
0x14008405d  or      rbx, rax
0x140084060  mov     rax, [rbp+4Fh+var_68]
0x140084064  mov     [rdi], rbx
0x140084067  mov     r9, [rax]
0x14008406a  mov     rax, 0FFFFFFFFFFh
0x140084074  shr     r9, 0Ch
0x140084078  and     r9, rax
0x14008407b  mov     rax, 0FFFFEFFFFFFFFFFFh
0x140084085  mov     rcx, rax
0x140084088  mov     rax, r15
0x14008408b  sub     rcx, rax
0x14008408e  sar     rcx, 3
  ... truncated ...
```
