# SkmmCreateSparseTable

- ea: `0x14002341c`
- end: `0x140023b4f`
- name: `SkmmCreateSparseTable`
- size: `1843`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x14006011c`
- `0x140075554`
- `0x1400984d8`

## callees

- `0x140003780`
- `0x140020360`
- `0x140020424`
- `0x14002341c`
- `0x14002467c`
- `0x140024724`
- `0x140024fac`
- `0x140027ac0`
- `0x14002b534`
- `0x14003a0e0`
- `0x140050b48`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateSparseTable(__int64 a1, unsigned int a2, ULONG a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // r15d
  unsigned int v7; // ebx
  __int64 SystemPtes; // rax
  __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  unsigned int i; // r15d
  __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  __int64 PteTrace; // rax
  __int64 v15; // r13
  PVOID *v16; // r15
  PVOID StackBase; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v24; // rax
  unsigned int v26; // r12d
  unsigned __int64 v27; // rbx
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // r13
  PVOID *v31; // r15
  PVOID v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  int v38; // ecx
  unsigned __int64 v39; // r12
  unsigned int v40; // r15d
  unsigned int v41; // r14d
  __int64 v42; // rsi
  unsigned __int64 v43; // rbx
  __int64 v44; // rax
  int v45; // r9d
  __int64 v46; // r10
  __int64 v47; // r13
  PVOID *v48; // r12
  PVOID v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // rbx
  __int64 v58; // rax
  _QWORD *v59; // rcx
  int v60; // r9d
  __int64 v61; // r15
  PVOID *v62; // rsi
  __int64 v63; // rdx
  _QWORD *v64; // rax
  __int64 v65; // rdx
  int v66; // eax
  __int64 *v67; // rcx
  __int64 v68; // rdi
  unsigned __int64 v69; // [rsp+30h] [rbp-D0h] BYREF
  ULONG BackTraceHash; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v71; // [rsp+40h] [rbp-C0h]
  _BYTE v72[256]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v73; // [rsp+150h] [rbp+50h]
  char v74; // [rsp+154h] [rbp+54h]
  char v75; // [rsp+155h] [rbp+55h]
  _UNKNOWN *retaddr; // [rsp+1A8h] [rbp+A8h]
  unsigned int v78; // [rsp+1B8h] [rbp+B8h]
  ULONG v79; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned int v80; // [rsp+1C8h] [rbp+C8h]

  v79 = a3;
  v3 = a3;
  v4 = a1;
  memset_0(v72, 0, 0x108u);
  *(_DWORD *)(v4 + 16) = a2;
  *(_QWORD *)(v4 + 8) = 0;
  *(_QWORD *)(v4 + 20) = 0;
  v6 = (((8LL * a2) & 0xFFF) != 0) + (unsigned int)((8 * (unsigned __int64)a2) >> 12);
  v78 = v6;
  v7 = ((unsigned __int64)(8 * v3 + 8) >> 12) + (((8 * v3 + 8) & 0xFFF) != 0);
  v80 = v7;
  if ( v6 > 0x200 )
  {
    SystemPtes = SkmiAllocateSystemPtes(
                   (__int64)&SkmiLargePdes,
                   (unsigned int)((8 * (unsigned __int64)v6) >> 12) + (((8LL * v6) & 0xFFF) != 0));
    v9 = SystemPtes;
    if ( SystemPtes )
    {
      v69 = 99;
      v10 = SystemPtes << 25 >> 16;
      v71 = v10;
      *(_QWORD *)v4 = (__int64)(v10 << 25) >> 16;
      for ( i = ((8 * (unsigned __int64)v7) >> 12) + (((8LL * v7) & 0xFFF) != 0); ; --i )
      {
        v78 = i;
        if ( !i )
        {
          v7 = v80;
          goto LABEL_26;
        }
        if ( !(unsigned int)SkmiAllocateZeroedPage(0, &v69) )
          break;
        v13 = v69;
        PteTrace = SkmiGetPteTrace(0, v9, 0, v69, *(_QWORD *)v9);
        v15 = PteTrace;
        if ( PteTrace )
        {
          v16 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v16, &BackTraceHash) )
              {
                *(_QWORD *)(v15 + 40) = retaddr;
                *v16 = (PVOID)SkmiGetInstructionPointer(v19, v18);
              }
            }
          }
          i = v78;
        }
        if ( (unsigned __int64)v9 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v9 < 0xFFFFF6FB7DBED800uLL )
        {
          v20 = KeGetPcr()->NtTib.StackBase;
          if ( v20 )
            v21 = v20[10];
          else
            v21 = 0;
          v22 = *(_QWORD *)(v21 + 232);
          if ( v22 )
          {
            v23 = SkiKvaShadowMode;
            *(_QWORD *)(v22 + 8 * ((v9 >> 3) & 0x1FF)) = v13;
            if ( v23 != 2 && (v13 & 1) != 0 )
              v13 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v9 = v13;
        v9 += 8;
        ++*(_DWORD *)(v4 + 24);
      }
      v7 = v80;
LABEL_45:
      v39 = *(_QWORD *)v4;
      LOBYTE(v12) = -1;
      v75 = -1;
      v40 = 0;
      v69 = v39;
      if ( v7 )
      {
        v41 = v80;
        do
        {
          v42 = v10 + 8LL * v40;
          v43 = *(_QWORD *)v42;
          if ( (*(_QWORD *)v42 & 1) != 0 )
          {
            v44 = SkmiGetPteTrace(0, (unsigned int)v10 + 8 * v40, 0, 0, *(_QWORD *)v42);
            v47 = v44;
            if ( v44 )
            {
              v48 = (PVOID *)(v44 + 32);
              memset_0((void *)(v44 + 32), 0, (unsigned int)(v45 + 64));
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                v49 = KeGetPcr()->NtTib.StackBase;
                if ( v49 )
                {
                  if ( !RtlCaptureStackBackTrace((ULONG)v49, 8u, v48, &v79) )
                  {
                    *(_QWORD *)(v47 + 40) = retaddr;
                    *v48 = (PVOID)SkmiGetInstructionPointer(v51, v50);
                  }
                }
              }
              v39 = v69;
              v46 = 0xFFFFFFFFFFLL;
            }
            if ( (unsigned __int64)v42 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v42 < 0xFFFFF6FB7DBED800uLL )
            {
              v52 = KeGetPcr()->NtTib.StackBase;
              v53 = v52 ? v52[10] : 0LL;
              v54 = *(_QWORD *)(v53 + 232);
              if ( v54 )
                *(_QWORD *)(v54 + 8 * ((v42 >> 3) & 0x1FF)) = 0;
            }
            *(_QWORD *)v42 = 0;
            SkmiFreePhysicalPage(0, v46 & (v43 >> 12));
            SkmiBatchFlushSingleTb(v39, v72, v55, v56);
          }
          v39 += 4096LL;
          ++v40;
          v69 = v39;
        }
        while ( v40 < v41 );
        LOBYTE(v12) = v75;
        v4 = a1;
      }
      if ( *(_DWORD *)(v4 + 24) )
      {
        v57 = ((v10 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
        do
        {
          SkmiFreePhysicalPage(0, (*(_QWORD *)v57 >> 12) & 0xFFFFFFFFFFLL);
          v58 = SkmiGetPteTrace(0, v57, 0, 0, *(_QWORD *)v57);
          v61 = v58;
          if ( v58 )
          {
            v62 = (PVOID *)(v58 + 32);
            memset_0((void *)(v58 + 32), 0, (unsigned int)(v60 + 64));
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v59 = KeGetPcr()->NtTib.StackBase;
              if ( v59 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v59, 8u, v62, &v79) )
                {
                  *(_QWORD *)(v61 + 40) = retaddr;
                  *v62 = (PVOID)SkmiGetInstructionPointer(v59, v63);
                }
              }
            }
          }
          if ( (unsigned __int64)v57 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v57 < 0xFFFFF6FB7DBED800uLL )
          {
            v64 = KeGetPcr()->NtTib.StackBase;
            v59 = v64 ? (_QWORD *)v64[10] : 0LL;
            v65 = v59[29];
            if ( v65 )
              *(_QWORD *)(v65 + 8 * ((v57 >> 3) & 0x1FF)) = 0;
          }
          *(_QWORD *)v57 = 0;
          v57 += 8;
          v66 = *(_DWORD *)(v4 + 24) - 1;
          *(_DWORD *)(v4 + 24) = v66;
        }
        while ( v66 );
        LOBYTE(v59) = -1;
        SkeFlushEntireTb(v59, 0);
        v67 = qword_140156E70;
        v68 = v71 - SkmiLargePdes;
      }
      else
      {
        if ( v74 )
        {
          SkeFlushEntireTb(v12, 0);
        }
        else if ( v73 )
        {
          SkeFlushRangeListTb(v12, 0, v73, v72);
        }
        v68 = v10 - SkmiSystemPtes;
        v67 = &qword_140156F70;
      }
      RtlInterlockedClearBitRunEx(v67, (unsigned int)(v68 >> 3), v78);
    }
    return 3221225626LL;
  }
  v24 = SkmiAllocateSystemPtes((__int64)&SkmiSystemPtes, v6);
  v71 = v24;
  v10 = v24;
  if ( !v24 )
    return 3221225626LL;
  *(_QWORD *)v4 = v24 << 25 >> 16;
LABEL_26:
  v26 = 0;
  v69 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
  while ( v26 < v7 )
  {
    if ( !(unsigned int)SkmiAllocateZeroedPage(0, &v69) )
      goto LABEL_45;
    v27 = v69;
    v28 = v10 + 8LL * v26;
    v29 = SkmiGetPteTrace(0, (unsigned int)v10 + 8 * v26, 0, v69, *(_QWORD *)v28);
    v30 = v29;
    if ( v29 )
    {
      v31 = (PVOID *)(v29 + 32);
      memset_0((void *)(v29 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v32 = KeGetPcr()->NtTib.StackBase;
        if ( v32 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v32, 8u, v31, &BackTraceHash) )
          {
            *(_QWORD *)(v30 + 40) = retaddr;
            *v31 = (PVOID)SkmiGetInstructionPointer(v34, v33);
          }
        }
      }
    }
    if ( (unsigned __int64)v28 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v28 < 0xFFFFF6FB7DBED800uLL )
    {
      v35 = KeGetPcr()->NtTib.StackBase;
      v36 = v35 ? v35[10] : 0LL;
      v37 = *(_QWORD *)(v36 + 232);
      if ( v37 )
      {
        v38 = SkiKvaShadowMode;
        *(_QWORD *)(v37 + 8 * ((v28 >> 3) & 0x1FF)) = v27;
        if ( v38 != 2 && (v27 & 1) != 0 )
          v27 |= 0x8000000000000000uLL;
      }
    }
    *(_QWORD *)v28 = v27;
    *(_DWORD *)(v4 + 12) += 512;
    v7 = v80;
    ++v26;
  }
  if ( *(_DWORD *)(v4 + 12) > v79 + 1 )
    SkmiAddSparseTableFreeEntries(v4);
  return 0;
}

```

## disassembly

```asm
0x14002341c  mov     [rsp-8+arg_10], r8d
0x140023421  mov     [rsp-8+arg_0], rcx
0x140023426  push    rbp
0x140023427  push    rbx
0x140023428  push    rsi
0x140023429  push    rdi
0x14002342a  push    r12
0x14002342c  push    r13
0x14002342e  push    r14
0x140023430  push    r15
0x140023432  lea     rbp, [rsp-68h]
0x140023437  sub     rsp, 168h
0x14002343e  mov     esi, r8d
0x140023441  mov     r14, rcx
0x140023444  mov     ebx, edx
0x140023446  lea     rcx, [rsp+1A0h+var_150]; void *
0x14002344b  xor     edx, edx; Val
0x14002344d  mov     r8d, 108h; Size
0x140023453  call    memset_0
0x140023458  xor     r13d, r13d
0x14002345b  mov     [r14+10h], ebx
0x14002345f  mov     ecx, ebx
0x140023461  mov     [r14+8], r13
0x140023465  shl     rcx, 3
0x140023469  mov     eax, r13d
0x14002346c  mov     r12d, 0FFFh
0x140023472  mov     [r14+14h], r13
0x140023476  test    r12, rcx
0x140023479  mov     ebx, r13d
0x14002347c  setnz   al
0x14002347f  shr     rcx, 0Ch
0x140023483  lea     r15d, [rax+rcx]
0x140023487  lea     rax, ds:8[rsi*8]
0x14002348f  mov     [rbp+0A0h+arg_8], r15d
0x140023496  test    r12, rax
0x140023499  setnz   bl
0x14002349c  shr     rax, 0Ch
0x1400234a0  add     ebx, eax
0x1400234a2  mov     [rbp+0A0h+arg_18], ebx
0x1400234a8  cmp     r15d, 200h
0x1400234af  jbe     loc_14002366D
0x1400234b5  mov     edx, r13d
0x1400234b8  mov     eax, r15d
0x1400234bb  shl     rax, 3
0x1400234bf  lea     rcx, SkmiLargePdes
0x1400234c6  test    r12, rax
0x1400234c9  setnz   dl
0x1400234cc  shr     rax, 0Ch
0x1400234d0  add     edx, eax
0x1400234d2  call    SkmiAllocateSystemPtes
0x1400234d7  mov     rsi, rax
0x1400234da  test    rax, rax
0x1400234dd  jz      loc_140023689
0x1400234e3  mov     rdx, 0FFFFF68000000000h
0x1400234ed  mov     rcx, rdx
0x1400234f0  mov     rdi, rax
0x1400234f3  shl     rcx, 19h
0x1400234f7  shl     rdi, 19h
0x1400234fb  mov     r15d, r13d
0x1400234fe  sub     rdi, rcx
0x140023501  mov     [rsp+1A0h+var_170], 63h ; 'c'
0x14002350a  sar     rdi, 10h
0x14002350e  mov     rax, rdi
0x140023511  mov     [rsp+1A0h+var_160], rdi
0x140023516  shl     rax, 19h
0x14002351a  sub     rax, rcx
0x14002351d  sar     rax, 10h
0x140023521  mov     [r14], rax
0x140023524  mov     eax, ebx
0x140023526  shl     rax, 3
0x14002352a  test    r12, rax
0x14002352d  setnz   r15b
0x140023531  shr     rax, 0Ch
0x140023535  add     r15d, eax
0x140023538  mov     [rbp+0A0h+arg_8], r15d
0x14002353f  test    r15d, r15d
0x140023542  jz      loc_1400236B7
0x140023548  lea     rdx, [rsp+1A0h+var_170]
0x14002354d  xor     ecx, ecx
0x14002354f  call    SkmiAllocateZeroedPage
0x140023554  test    eax, eax
0x140023556  jz      loc_140023814
0x14002355c  mov     rax, [rsi]
0x14002355f  xor     r8d, r8d
0x140023562  mov     rbx, [rsp+1A0h+var_170]
0x140023567  mov     rdx, rsi
0x14002356a  mov     r9, rbx
0x14002356d  mov     [rsp+1A0h+var_180], rax
0x140023572  xor     ecx, ecx
0x140023574  call    SkmiGetPteTrace
0x140023579  mov     r13, rax
0x14002357c  test    rax, rax
0x14002357f  jz      short loc_1400235DE
0x140023581  xor     edx, edx; Val
0x140023583  lea     r15, [rax+20h]
0x140023587  mov     rcx, r15; void *
0x14002358a  lea     r8d, [rdx+40h]; Size
0x14002358e  call    memset_0
0x140023593  test    cs:SkmiFlags, 400000h
0x14002359d  jz      short loc_1400235D7
0x14002359f  mov     rcx, gs:8; FramesToSkip
0x1400235a8  test    rcx, rcx
0x1400235ab  jz      short loc_1400235D7
0x1400235ad  lea     r9, [rsp+1A0h+BackTraceHash]; BackTraceHash
0x1400235b2  mov     r8, r15; BackTrace
0x1400235b5  mov     edx, 8; FramesToCapture
0x1400235ba  call    RtlCaptureStackBackTrace
0x1400235bf  test    ax, ax
0x1400235c2  jnz     short loc_1400235D7
0x1400235c4  mov     rax, [rbp+0A8h]
0x1400235cb  mov     [r13+28h], rax
0x1400235cf  call    SkmiGetInstructionPointer
0x1400235d4  mov     [r15], rax
0x1400235d7  mov     r15d, [rbp+0A0h+arg_8]
0x1400235de  mov     rax, 0FFFFF6FB7DBED000h
0x1400235e8  mov     rax, rax
0x1400235eb  cmp     rsi, rax
0x1400235ee  jb      short loc_140023657
0x1400235f0  mov     rax, 0FFFFF6FB7DBED800h
0x1400235fa  mov     rax, rax
0x1400235fd  xor     r13d, r13d
0x140023600  cmp     rsi, rax
0x140023603  jnb     short loc_14002365A
0x140023605  mov     rax, gs:8
0x14002360e  test    rax, rax
0x140023611  jz      short loc_140023619
0x140023613  mov     rcx, [rax+50h]
0x140023617  jmp     short loc_14002361C
0x140023619  mov     rcx, r13
0x14002361c  mov     rdx, [rcx+0E8h]
0x140023623  test    rdx, rdx
0x140023626  jz      short loc_14002365A
0x140023628  mov     ecx, cs:SkiKvaShadowMode
0x14002362e  mov     rax, rsi
0x140023631  sar     rax, 3
0x140023635  and     eax, 1FFh
0x14002363a  mov     [rdx+rax*8], rbx
0x14002363e  cmp     ecx, 2
0x140023641  jz      short loc_14002365A
0x140023643  test    bl, 1
0x140023646  jz      short loc_14002365A
0x140023648  mov     rax, 8000000000000000h
0x140023652  or      rbx, rax
0x140023655  jmp     short loc_14002365A
0x140023657  xor     r13d, r13d
0x14002365a  mov     [rsi], rbx
0x14002365d  add     rsi, 8
0x140023661  inc     dword ptr [r14+18h]
0x140023665  dec     r15d
0x140023668  jmp     loc_140023538
0x14002366d  mov     edx, r15d
0x140023670  lea     rcx, SkmiSystemPtes
0x140023677  call    SkmiAllocateSystemPtes
0x14002367c  mov     [rsp+1A0h+var_160], rax
0x140023681  mov     rdi, rax
0x140023684  test    rax, rax
0x140023687  jnz     short loc_140023693
0x140023689  mov     eax, 0C000009Ah
0x14002368e  jmp     loc_140023B3A
0x140023693  mov     rcx, rax
0x140023696  mov     rax, 0FFFFF68000000000h
0x1400236a0  shl     rcx, 19h
0x1400236a4  mov     rax, rax
0x1400236a7  shl     rax, 19h
0x1400236ab  sub     rcx, rax
0x1400236ae  sar     rcx, 10h
0x1400236b2  mov     [r14], rcx
0x1400236b5  jmp     short loc_1400236BD
0x1400236b7  mov     ebx, [rbp+0A0h+arg_18]
0x1400236bd  movzx   eax, byte ptr cs:word_140156D90
0x1400236c4  mov     rcx, 8000000000000063h
0x1400236ce  and     eax, 1
0x1400236d1  mov     r12d, r13d
0x1400236d4  shl     rax, 8
0x1400236d8  or      rax, rcx
0x1400236db  mov     [rsp+1A0h+var_170], rax
0x1400236e0  cmp     r12d, ebx
0x1400236e3  jnb     loc_140023B22
0x1400236e9  lea     rdx, [rsp+1A0h+var_170]
0x1400236ee  xor     ecx, ecx
0x1400236f0  call    SkmiAllocateZeroedPage
0x1400236f5  test    eax, eax
0x1400236f7  jz      loc_14002381A
0x1400236fd  mov     rbx, [rsp+1A0h+var_170]
0x140023702  xor     r8d, r8d
0x140023705  mov     eax, r12d
0x140023708  mov     r9, rbx
0x14002370b  xor     ecx, ecx
0x14002370d  lea     rsi, [rdi+rax*8]
0x140023711  mov     rax, [rsi]
0x140023714  mov     rdx, rsi
0x140023717  mov     [rsp+1A0h+var_180], rax
0x14002371c  call    SkmiGetPteTrace
0x140023721  mov     r13, rax
0x140023724  test    rax, rax
0x140023727  jz      short loc_14002377F
0x140023729  xor     edx, edx; Val
0x14002372b  lea     r15, [rax+20h]
0x14002372f  mov     rcx, r15; void *
0x140023732  lea     r8d, [rdx+40h]; Size
0x140023736  call    memset_0
0x14002373b  test    cs:SkmiFlags, 400000h
0x140023745  jz      short loc_14002377F
0x140023747  mov     rcx, gs:8; FramesToSkip
0x140023750  test    rcx, rcx
0x140023753  jz      short loc_14002377F
0x140023755  lea     r9, [rsp+1A0h+BackTraceHash]; BackTraceHash
0x14002375a  mov     r8, r15; BackTrace
0x14002375d  mov     edx, 8; FramesToCapture
0x140023762  call    RtlCaptureStackBackTrace
0x140023767  test    ax, ax
0x14002376a  jnz     short loc_14002377F
0x14002376c  mov     rax, [rbp+0A8h]
0x140023773  mov     [r13+28h], rax
0x140023777  call    SkmiGetInstructionPointer
0x14002377c  mov     [r15], rax
0x14002377f  mov     rax, 0FFFFF6FB7DBED000h
0x140023789  mov     rax, rax
0x14002378c  cmp     rsi, rax
0x14002378f  jb      short loc_1400237F8
0x140023791  mov     rax, 0FFFFF6FB7DBED800h
0x14002379b  mov     rax, rax
0x14002379e  xor     r13d, r13d
0x1400237a1  cmp     rsi, rax
0x1400237a4  jnb     short loc_1400237FB
0x1400237a6  mov     rax, gs:8
0x1400237af  test    rax, rax
0x1400237b2  jz      short loc_1400237BA
0x1400237b4  mov     rcx, [rax+50h]
0x1400237b8  jmp     short loc_1400237BD
0x1400237ba  mov     rcx, r13
0x1400237bd  mov     rdx, [rcx+0E8h]
0x1400237c4  test    rdx, rdx
0x1400237c7  jz      short loc_1400237FB
0x1400237c9  mov     ecx, cs:SkiKvaShadowMode
0x1400237cf  mov     rax, rsi
0x1400237d2  sar     rax, 3
0x1400237d6  and     eax, 1FFh
0x1400237db  mov     [rdx+rax*8], rbx
0x1400237df  cmp     ecx, 2
0x1400237e2  jz      short loc_1400237FB
0x1400237e4  test    bl, 1
0x1400237e7  jz      short loc_1400237FB
0x1400237e9  mov     rax, 8000000000000000h
0x1400237f3  or      rbx, rax
0x1400237f6  jmp     short loc_1400237FB
0x1400237f8  xor     r13d, r13d
0x1400237fb  mov     [rsi], rbx
0x1400237fe  add     dword ptr [r14+0Ch], 200h
0x140023806  mov     ebx, [rbp+0A0h+arg_18]
0x14002380c  inc     r12d
0x14002380f  jmp     loc_1400236E0
0x140023814  mov     ebx, [rbp+0A0h+arg_18]
0x14002381a  mov     r12, [r14]
0x14002381d  mov     cl, 0FFh
0x14002381f  mov     [rbp+0A0h+var_4B], cl
0x140023822  mov     r15d, r13d
0x140023825  mov     [rsp+1A0h+var_170], r12
0x14002382a  mov     r10, 0FFFFFFFFFFh
0x140023834  test    ebx, ebx
0x140023836  jz      loc_14002398A
0x14002383c  mov     r14d, [rbp+0A0h+arg_18]
0x140023843  mov     eax, r15d
0x140023846  lea     rsi, [rdi+rax*8]
0x14002384a  mov     rbx, [rsi]
0x14002384d  test    bl, 1
0x140023850  jz      loc_140023968
0x140023856  mov     rax, [rsi]
0x140023859  xor     r9d, r9d
0x14002385c  xor     r8d, r8d
0x14002385f  mov     [rsp+1A0h+var_180], rax
0x140023864  mov     rdx, rsi
0x140023867  xor     ecx, ecx
0x140023869  call    SkmiGetPteTrace
0x14002386e  mov     r13, rax
0x140023871  test    rax, rax
0x140023874  jz      short loc_1400238DE
0x140023876  lea     r12, [rax+20h]
0x14002387a  xor     edx, edx; Val
0x14002387c  mov     rcx, r12; void *
0x14002387f  lea     r8d, [r9+40h]; Size
0x140023883  call    memset_0
0x140023888  test    cs:SkmiFlags, 400000h
0x140023892  jz      short loc_1400238CF
0x140023894  mov     rcx, gs:8; FramesToSkip
0x14002389d  test    rcx, rcx
0x1400238a0  jz      short loc_1400238CF
0x1400238a2  lea     r9, [rbp+0A0h+arg_10]; BackTraceHash
0x1400238a9  mov     r8, r12; BackTrace
0x1400238ac  mov     edx, 8; FramesToCapture
0x1400238b1  call    RtlCaptureStackBackTrace
0x1400238b6  test    ax, ax
0x1400238b9  jnz     short loc_1400238CF
0x1400238bb  mov     rax, [rbp+0A8h]
0x1400238c2  mov     [r13+28h], rax
0x1400238c6  call    SkmiGetInstructionPointer
0x1400238cb  mov     [r12], rax
0x1400238cf  mov     r12, [rsp+1A0h+var_170]
0x1400238d4  mov     r10, 0FFFFFFFFFFh
0x1400238de  mov     rax, 0FFFFF6FB7DBED000h
  ... truncated ...
```
