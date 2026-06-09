# SkmiProcessDriverReadOnlyData

- ea: `0x14007b814`
- end: `0x14007c134`
- name: `SkmiProcessDriverReadOnlyData`
- size: `2336`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14007a358`

## callees

- `0x140003780`
- `0x140020360`
- `0x140020424`
- `0x140025024`
- `0x140027ac0`
- `0x14002b534`
- `0x14002e70c`
- `0x140031460`
- `0x14007b814`
- `0x140081290`
- `0x1400d7280`
- `0x1400f9660`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiProcessDriverReadOnlyData(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rdx
  int v3; // ebx
  unsigned int *v4; // r14
  bool i; // zf
  __int64 v7; // rbx
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned __int64 v13; // rdi
  __int64 v14; // r12
  __int64 PteTrace; // rax
  int v16; // r9d
  __int64 v17; // r13
  PVOID *v18; // r15
  PVOID StackBase; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r13
  PVOID *v27; // r15
  PVOID v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  int v34; // ecx
  __int64 v35; // r13
  unsigned __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // r15
  PVOID *v39; // rdi
  PVOID v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  _WORD *v43; // rcx
  unsigned int v44; // r15d
  __int64 SystemPtes; // rax
  __int64 v46; // rsi
  __int64 v47; // rdi
  unsigned __int64 v48; // rax
  unsigned __int64 v49; // rdi
  _QWORD *v50; // r13
  unsigned __int64 v51; // rbx
  unsigned int v52; // r12d
  __int64 v53; // rax
  __int64 v54; // r15
  PVOID *v55; // r14
  PVOID v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  unsigned __int64 v59; // rax
  _QWORD *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r8
  int v63; // edx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r9
  __int64 v67; // r8
  __int64 v68; // rcx
  _QWORD *v69; // rcx
  unsigned __int64 v70; // rbx
  __int64 v71; // rdi
  unsigned __int64 j; // r15
  __int64 v73; // rsi
  __int64 v74; // rax
  int v75; // r9d
  __int64 v76; // r13
  PVOID *v77; // r14
  __int64 v78; // rdx
  _QWORD *v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rdi
  __int64 v82; // r9
  volatile signed __int32 *v83; // r8
  unsigned int v84; // eax
  unsigned int *v85; // [rsp+30h] [rbp-D0h]
  __int64 v86; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v87; // [rsp+40h] [rbp-C0h]
  __int64 v88; // [rsp+48h] [rbp-B8h]
  __int64 v89; // [rsp+50h] [rbp-B0h]
  _BYTE v90[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v91; // [rsp+160h] [rbp+60h]
  char v92; // [rsp+164h] [rbp+64h]
  char v93; // [rsp+165h] [rbp+65h]
  _UNKNOWN *retaddr; // [rsp+1B8h] [rbp+B8h]
  __int64 BackTraceHash; // [rsp+1C0h] [rbp+C0h] BYREF
  _WORD *v96; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v97; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v98; // [rsp+1D8h] [rbp+D8h]

  BackTraceHash = a1;
  v1 = SkmiNtosNar;
  memset_0(v90, 0, 0x108u);
  v2 = *(_QWORD *)(v1 + 24) + 0x8000000000LL;
  v97 = 0;
  BackTraceHash = 0;
  RtlImageNtHeaderEx(1, v2, 0, &BackTraceHash);
  v3 = *(unsigned __int16 *)(BackTraceHash + 6);
  v4 = (unsigned int *)(*(unsigned __int16 *)(BackTraceHash + 20) + BackTraceHash + 24);
  for ( i = v3 == 0; ; i = v3-- == 1 )
  {
    v85 = v4;
    if ( i )
      return 3221225595LL;
    if ( !memcmp(v4, "CFGRO", 8u) )
      break;
    v4 += 10;
  }
  v7 = ((*(_QWORD *)(v1 + 24) >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL;
  v8 = v4[3];
  v88 = v7;
  v9 = v8 + *(_QWORD *)(v1 + 24);
  v89 = v9;
  if ( (*(_BYTE *)(v1 + 78) & 8) != 0 )
  {
    v10 = (((v7 + 8 * ((unsigned __int64)(unsigned int)v8 >> 12)) >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v11 = v4[2] + 4095LL;
    v98 = v10;
    v87 = (((v7 + 8 * ((unsigned __int64)(unsigned int)v8 >> 12) + 8 * (((unsigned __int64)(v8 & 0xFFF) + v11) >> 12) - 8) >> 9)
         & 0x7FFFFFFFF8LL)
        - 0x98000000000LL;
    v96 = (_WORD *)(qword_140156AE0 + ((v9 >> 20) & 0xFFFFFFE));
    if ( v10 <= v87 )
    {
      while ( 1 )
      {
        v12 = *(_QWORD *)v10;
        if ( !(unsigned int)SkmiAllocatePhysicalPage(0, 4, &v97) )
          return 3221225626LL;
        v86 = (v97 & 0xFFFFFFFFFFLL) << 12;
        v13 = v86 | 0x63;
        v14 = (__int64)(v10 << 25) >> 16;
        PteTrace = SkmiGetPteTrace(0, v10, 0, 0, *(_QWORD *)v10);
        v17 = PteTrace;
        if ( PteTrace )
        {
          v18 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v16 + 64));
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            StackBase = KeGetPcr()->NtTib.StackBase;
            if ( StackBase )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v18, (PULONG)&BackTraceHash) )
              {
                *(_QWORD *)(v17 + 40) = retaddr;
                *v18 = (PVOID)SkmiGetInstructionPointer(v21, v20);
              }
            }
          }
        }
        if ( v10 >= 0xFFFFF6FB7DBED000uLL && v10 < 0xFFFFF6FB7DBED800uLL )
        {
          v22 = KeGetPcr()->NtTib.StackBase;
          v23 = v22 ? v22[10] : 0LL;
          v24 = *(_QWORD *)(v23 + 232);
          if ( v24 )
            *(_QWORD *)(v24 + 8 * (((__int64)v10 >> 3) & 0x1FF)) = 0;
        }
        *(_QWORD *)v10 = 0;
        SkeFlushSingleCurrentTb(v14);
        v25 = SkmiGetPteTrace(0, v10, 0, v13, *(_QWORD *)v10);
        v26 = v25;
        if ( v25 )
        {
          v27 = (PVOID *)(v25 + 32);
          memset_0((void *)(v25 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v28 = KeGetPcr()->NtTib.StackBase;
            if ( v28 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v28, 8u, v27, (PULONG)&BackTraceHash) )
              {
                *(_QWORD *)(v26 + 40) = retaddr;
                *v27 = (PVOID)SkmiGetInstructionPointer(v30, v29);
              }
            }
          }
        }
        if ( v10 >= 0xFFFFF6FB7DBED000uLL && v10 < 0xFFFFF6FB7DBED800uLL )
        {
          v31 = KeGetPcr()->NtTib.StackBase;
          v32 = v31 ? v31[10] : 0LL;
          v33 = *(_QWORD *)(v32 + 232);
          if ( v33 )
          {
            v34 = SkiKvaShadowMode;
            *(_QWORD *)(v33 + 8 * (((__int64)v10 >> 3) & 0x1FF)) = v13;
            if ( v34 != 2 )
              v13 = v86 | 0x8000000000000063uLL;
          }
        }
        *(_QWORD *)v10 = v13;
        v35 = 512;
        v36 = v12 & 0xFFFFFFFFFF000LL | 0xB21;
        do
        {
          v37 = SkmiGetPteTrace(0, v14, 0, v36, *(_QWORD *)v14);
          v38 = v37;
          if ( v37 )
          {
            v39 = (PVOID *)(v37 + 32);
            memset_0((void *)(v37 + 32), 0, 0x40u);
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v40 = KeGetPcr()->NtTib.StackBase;
              if ( v40 )
              {
                if ( !RtlCaptureStackBackTrace((ULONG)v40, 8u, v39, (PULONG)&BackTraceHash) )
                {
                  *(_QWORD *)(v38 + 40) = retaddr;
                  *v39 = (PVOID)SkmiGetInstructionPointer(v42, v41);
                }
              }
            }
          }
          *(_QWORD *)v14 = v36;
          v14 += 8;
          v36 = (v36 + 4096) ^ ((v36 + 4096) ^ v36) & 0xFFF0000000000FFFuLL;
          --v35;
        }
        while ( v35 );
        v43 = v96;
        v4 = v85;
        v98 += 8LL;
        v10 = v98;
        *v96 = 0;
        v96 = v43 + 1;
        if ( v10 > v87 )
        {
          v7 = v88;
          break;
        }
      }
    }
  }
  if ( v4[2] < 0x18 )
    return 3221225595LL;
  v44 = ((v4[2] & 0xFFF) != 0) + (v4[2] >> 12);
  LODWORD(BackTraceHash) = v44;
  SystemPtes = SkmiAllocateSystemPtes(&SkmiSystemPtes);
  v46 = SystemPtes;
  if ( !SystemPtes )
    return 3221225626LL;
  v47 = SystemPtes << 25;
  v48 = (unsigned __int64)v4[3] >> 12;
  v49 = v47 >> 16;
  v98 = v49;
  v50 = (_QWORD *)(v7 + 8 * v48);
  v51 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
  v52 = v44;
  if ( v44 )
  {
    do
    {
      v51 = *v50 ^ (*v50 ^ v51) & 0xFFF0000000000FFFuLL;
      v53 = SkmiGetPteTrace(0, v46, 0, v51, *(_QWORD *)v46);
      v54 = v53;
      if ( v53 )
      {
        v55 = (PVOID *)(v53 + 32);
        memset_0((void *)(v53 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v56 = KeGetPcr()->NtTib.StackBase;
          if ( v56 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v56, 8u, v55, (PULONG)&v96) )
            {
              *(_QWORD *)(v54 + 40) = retaddr;
              *v55 = (PVOID)SkmiGetInstructionPointer(v58, v57);
            }
          }
        }
      }
      v59 = v51;
      if ( (unsigned __int64)v46 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v46 < 0xFFFFF6FB7DBED800uLL )
      {
        v60 = KeGetPcr()->NtTib.StackBase;
        v61 = v60 ? v60[10] : 0LL;
        v62 = *(_QWORD *)(v61 + 232);
        if ( v62 )
        {
          v63 = SkiKvaShadowMode;
          *(_QWORD *)(v62 + 8 * ((v46 >> 3) & 0x1FF)) = v51;
          if ( v63 != 2 && (v51 & 1) != 0 )
            v59 = v51 | 0x8000000000000000uLL;
        }
      }
      *(_QWORD *)v46 = v59;
      ++v50;
      v46 += 8;
      --v52;
    }
    while ( v52 );
    v49 = v98;
    v44 = BackTraceHash;
  }
  v64 = *(_QWORD *)v49;
  v65 = SkmiNtosNar;
  v66 = *(_QWORD *)(v49 + 16) - v89;
  SkmiNtCfgroAddress = v89;
  v67 = v64 - v89;
  v93 = -1;
  v68 = *(_QWORD *)(SkmiNtosNar + 32);
  *(_QWORD *)(v67 + v49 + 16) = *(_QWORD *)(SkmiNtosNar + 24) + *(unsigned int *)(v68 + 32);
  *(_DWORD *)(v67 + v49 + 36) = *(_DWORD *)(v68 + 36);
  *(_QWORD *)(v67 + v49 + 24) = *(_QWORD *)(v65 + 24);
  *(_DWORD *)(v67 + v49 + 32) = *(_DWORD *)(v65 + 64) << 12;
  SkmmNtFunctionTable = *(_OWORD *)(v66 + v49);
  xmmword_1401566D0 = *(_OWORD *)(v66 + v49 + 16);
  xmmword_1401566E0 = *(_OWORD *)(v66 + v49 + 32);
  xmmword_1401566F0 = *(_OWORD *)(v66 + v49 + 48);
  xmmword_140156700 = *(_OWORD *)(v66 + v49 + 64);
  qword_140156710 = *(_QWORD *)(v66 + v49 + 80);
  SkmiBatchFlushTbRange(v49, v44, v90);
  v70 = (unsigned int)BackTraceHash;
  v71 = ((v49 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  for ( j = 0; j < v70; *(_QWORD *)v73 = 0 )
  {
    v73 = v71 + 8 * j;
    v74 = SkmiGetPteTrace(0, (int)v71 + 8 * (int)j, 0, 0, *(_QWORD *)v73);
    v76 = v74;
    if ( v74 )
    {
      v77 = (PVOID *)(v74 + 32);
      memset_0((void *)(v74 + 32), 0, (unsigned int)(v75 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v69 = KeGetPcr()->NtTib.StackBase;
        if ( v69 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v69, 8u, v77, (PULONG)&BackTraceHash) )
          {
            *(_QWORD *)(v76 + 40) = retaddr;
            *v77 = (PVOID)SkmiGetInstructionPointer(v69, v78);
          }
        }
      }
    }
    if ( (unsigned __int64)v73 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v73 < 0xFFFFF6FB7DBED800uLL )
    {
      v79 = KeGetPcr()->NtTib.StackBase;
      v69 = v79 ? (_QWORD *)v79[10] : 0LL;
      v80 = v69[29];
      if ( v80 )
        *(_QWORD *)(v80 + 8 * ((v73 >> 3) & 0x1FF)) = 0;
    }
    ++j;
  }
  if ( v92 )
  {
    LOBYTE(v69) = v93;
    SkeFlushEntireTb(v69, 0);
  }
  else if ( v91 )
  {
    LOBYTE(v69) = v93;
    SkeFlushRangeListTb(v69, 0, v91, v90);
  }
  v81 = (v71 - SkmiSystemPtes) >> 3;
  v82 = v81 & 0x1F;
  v83 = (volatile signed __int32 *)(qword_140156F78 + 4 * ((unsigned __int64)(unsigned int)v81 >> 5));
  if ( v82 + v70 > 0x20 )
  {
    if ( (v81 & 0x1F) != 0 )
    {
      _InterlockedAnd(v83, ~(((1 << (32 - (v81 & 0x1F))) - 1) << v82));
      v70 -= 32 - (unsigned int)(v81 & 0x1F);
      ++v83;
    }
    while ( v70 >= 0x20 )
    {
      *v83++ = 0;
      v70 -= 32LL;
    }
    if ( !v70 )
      return 0;
    v84 = -1 << v70;
    goto LABEL_91;
  }
  if ( v70 != 32 )
  {
    v84 = ~(((1 << v70) - 1) << v82);
LABEL_91:
    _InterlockedAnd(v83, v84);
    return 0;
  }
  *v83 = 0;
  return 0;
}

```

## disassembly

```asm
0x14007b814  mov     [rsp-8+BackTraceHash], rcx
0x14007b819  push    rbp
0x14007b81a  push    rbx
0x14007b81b  push    rsi
0x14007b81c  push    rdi
0x14007b81d  push    r12
0x14007b81f  push    r13
0x14007b821  push    r14
0x14007b823  push    r15
0x14007b825  lea     rbp, [rsp-78h]
0x14007b82a  sub     rsp, 178h
0x14007b831  mov     rdi, cs:SkmiNtosNar
0x14007b838  lea     rcx, [rsp+1B0h+var_150]; void *
0x14007b83d  xor     edx, edx; Val
0x14007b83f  mov     r8d, 108h; Size
0x14007b845  call    memset_0
0x14007b84a  mov     rdx, [rdi+18h]
0x14007b84e  lea     r9, [rbp+0B0h+BackTraceHash]
0x14007b855  xor     r15d, r15d
0x14007b858  mov     rax, 8000000000h
0x14007b862  add     rdx, rax
0x14007b865  mov     [rbp+0B0h+arg_10], r15
0x14007b86c  xor     r8d, r8d
0x14007b86f  mov     [rbp+0B0h+BackTraceHash], r15
0x14007b876  lea     ecx, [r15+1]
0x14007b87a  call    RtlImageNtHeaderEx
0x14007b87f  mov     rcx, [rbp+0B0h+BackTraceHash]
0x14007b886  movzx   eax, word ptr [rcx+14h]
0x14007b88a  lea     r14, [rcx+18h]
0x14007b88e  movzx   ebx, word ptr [rcx+6]
0x14007b892  add     r14, rax
0x14007b895  test    ebx, ebx
0x14007b897  jmp     short loc_14007B8B9
0x14007b899  mov     r8d, 8; Size
0x14007b89f  lea     rdx, aCfgro; "CFGRO"
0x14007b8a6  mov     rcx, r14; Buf1
0x14007b8a9  call    memcmp
0x14007b8ae  test    eax, eax
0x14007b8b0  jz      short loc_14007B8DA
0x14007b8b2  add     r14, 28h ; '('
0x14007b8b6  add     ebx, 0FFFFFFFFh
0x14007b8b9  mov     [rsp+1B0h+var_180], r14
0x14007b8be  jnz     short loc_14007B899
0x14007b8c0  mov     eax, 0C000007Bh
0x14007b8c5  add     rsp, 178h
0x14007b8cc  pop     r15
0x14007b8ce  pop     r14
0x14007b8d0  pop     r13
0x14007b8d2  pop     r12
0x14007b8d4  pop     rdi
0x14007b8d5  pop     rsi
0x14007b8d6  pop     rbx
0x14007b8d7  pop     rbp
0x14007b8d8  retn
0x14007b8da  mov     rcx, [rdi+18h]
0x14007b8de  mov     r9, 7FFFFFFFF8h
0x14007b8e8  mov     rbx, rcx
0x14007b8eb  shr     rbx, 9
0x14007b8ef  and     rbx, r9
0x14007b8f2  mov     rdx, 0FFFFF60000000000h
0x14007b8fc  add     rbx, rdx
0x14007b8ff  mov     r13, 0FFFFF68000000000h
0x14007b909  test    byte ptr [rdi+4Eh], 8
0x14007b90d  mov     r12, 8000000000000063h
0x14007b917  mov     edx, [r14+0Ch]
0x14007b91b  mov     [rsp+1B0h+var_168], rbx
0x14007b920  lea     r8, [rdx+rcx]
0x14007b924  mov     [rsp+1B0h+var_160], r8
0x14007b929  jz      loc_14007BCDE
0x14007b92f  mov     eax, edx
0x14007b931  shr     rax, 0Ch
0x14007b935  lea     rcx, [rbx+rax*8]
0x14007b939  mov     rsi, rcx
0x14007b93c  shr     rsi, 9
0x14007b940  and     rsi, r9
0x14007b943  mov     rax, r13
0x14007b946  add     rsi, rax
0x14007b949  and     edx, 0FFFh
0x14007b94f  mov     eax, [r14+8]
0x14007b953  add     rax, 0FFFh
0x14007b959  mov     [rbp+0B0h+arg_18], rsi
0x14007b960  add     rax, rdx
0x14007b963  shr     rax, 0Ch
0x14007b967  lea     rcx, [rcx+rax*8]
0x14007b96b  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14007b96f  shr     rcx, 9
0x14007b973  and     rcx, r9
0x14007b976  mov     rax, r13
0x14007b979  add     rcx, rax
0x14007b97c  mov     rdi, r8
0x14007b97f  shr     rdi, 14h
0x14007b983  and     edi, 0FFFFFFEh
0x14007b989  mov     [rsp+1B0h+var_170], rcx
0x14007b98e  add     rdi, cs:qword_140156AE0
0x14007b995  mov     [rbp+0B0h+arg_8], rdi
0x14007b99c  cmp     rsi, rcx
0x14007b99f  ja      loc_14007BCDE
0x14007b9a5  mov     rbx, [rsi]
0x14007b9a8  lea     r8, [rbp+0B0h+arg_10]
0x14007b9af  mov     edx, 4
0x14007b9b4  xor     ecx, ecx
0x14007b9b6  call    SkmiAllocatePhysicalPage
0x14007b9bb  test    eax, eax
0x14007b9bd  jz      loc_14007BD1C
0x14007b9c3  mov     rax, [rbp+0B0h+arg_10]
0x14007b9ca  mov     rcx, 0FFFFFFFFFFh
0x14007b9d4  and     rax, rcx
0x14007b9d7  mov     r12, rsi
0x14007b9da  shl     rax, 0Ch
0x14007b9de  mov     rdi, rax
0x14007b9e1  mov     [rsp+1B0h+var_178], rax
0x14007b9e6  or      rdi, 63h
0x14007b9ea  shl     r12, 19h
0x14007b9ee  mov     rax, r13
0x14007b9f1  shl     rax, 19h
0x14007b9f5  xor     r9d, r9d
0x14007b9f8  sub     r12, rax
0x14007b9fb  xor     r8d, r8d
0x14007b9fe  mov     rax, [rsi]
0x14007ba01  mov     rdx, rsi
0x14007ba04  xor     ecx, ecx
0x14007ba06  mov     [rsp+1B0h+var_190], rax
0x14007ba0b  sar     r12, 10h
0x14007ba0f  call    SkmiGetPteTrace
0x14007ba14  mov     r13, rax
0x14007ba17  test    rax, rax
0x14007ba1a  jz      short loc_14007BA77
0x14007ba1c  lea     r15, [rax+20h]
0x14007ba20  xor     edx, edx; Val
0x14007ba22  mov     rcx, r15; void *
0x14007ba25  lea     r8d, [r9+40h]; Size
0x14007ba29  call    memset_0
0x14007ba2e  test    cs:SkmiFlags, 400000h
0x14007ba38  jz      short loc_14007BA74
0x14007ba3a  mov     rcx, gs:8; FramesToSkip
0x14007ba43  test    rcx, rcx
0x14007ba46  jz      short loc_14007BA74
0x14007ba48  lea     r9, [rbp+0B0h+BackTraceHash]; BackTraceHash
0x14007ba4f  mov     r8, r15; BackTrace
0x14007ba52  mov     edx, 8; FramesToCapture
0x14007ba57  call    RtlCaptureStackBackTrace
0x14007ba5c  test    ax, ax
0x14007ba5f  jnz     short loc_14007BA74
0x14007ba61  mov     rax, [rbp+0B8h]
0x14007ba68  mov     [r13+28h], rax
0x14007ba6c  call    SkmiGetInstructionPointer
0x14007ba71  mov     [r15], rax
0x14007ba74  xor     r15d, r15d
0x14007ba77  mov     rax, 0FFFFF6FB7DBED000h
0x14007ba81  mov     rax, rax
0x14007ba84  cmp     rsi, rax
0x14007ba87  jb      short loc_14007BACE
0x14007ba89  mov     rax, 0FFFFF6FB7DBED800h
0x14007ba93  mov     rax, rax
0x14007ba96  cmp     rsi, rax
0x14007ba99  jnb     short loc_14007BACE
0x14007ba9b  mov     rax, gs:8
0x14007baa4  test    rax, rax
0x14007baa7  jz      short loc_14007BAAF
0x14007baa9  mov     rcx, [rax+50h]
0x14007baad  jmp     short loc_14007BAB2
0x14007baaf  mov     rcx, r15
0x14007bab2  mov     rdx, [rcx+0E8h]
0x14007bab9  test    rdx, rdx
0x14007babc  jz      short loc_14007BACE
0x14007babe  mov     rax, rsi
0x14007bac1  sar     rax, 3
0x14007bac5  and     eax, 1FFh
0x14007baca  mov     [rdx+rax*8], r15
0x14007bace  mov     rcx, r12
0x14007bad1  mov     [rsi], r15
0x14007bad4  call    SkeFlushSingleCurrentTb
0x14007bad9  mov     rax, [rsi]
0x14007badc  mov     r9, rdi
0x14007badf  xor     r8d, r8d
0x14007bae2  mov     [rsp+1B0h+var_190], rax
0x14007bae7  mov     rdx, rsi
0x14007baea  xor     ecx, ecx
0x14007baec  call    SkmiGetPteTrace
0x14007baf1  mov     r13, rax
0x14007baf4  test    rax, rax
0x14007baf7  jz      short loc_14007BB54
0x14007baf9  xor     edx, edx; Val
0x14007bafb  lea     r15, [rax+20h]
0x14007baff  mov     rcx, r15; void *
0x14007bb02  lea     r8d, [rdx+40h]; Size
0x14007bb06  call    memset_0
0x14007bb0b  test    cs:SkmiFlags, 400000h
0x14007bb15  jz      short loc_14007BB51
0x14007bb17  mov     rcx, gs:8; FramesToSkip
0x14007bb20  test    rcx, rcx
0x14007bb23  jz      short loc_14007BB51
0x14007bb25  lea     r9, [rbp+0B0h+BackTraceHash]; BackTraceHash
0x14007bb2c  mov     r8, r15; BackTrace
0x14007bb2f  mov     edx, 8; FramesToCapture
0x14007bb34  call    RtlCaptureStackBackTrace
0x14007bb39  test    ax, ax
0x14007bb3c  jnz     short loc_14007BB51
0x14007bb3e  mov     rax, [rbp+0B8h]
0x14007bb45  mov     [r13+28h], rax
0x14007bb49  call    SkmiGetInstructionPointer
0x14007bb4e  mov     [r15], rax
0x14007bb51  xor     r15d, r15d
0x14007bb54  mov     rax, 0FFFFF6FB7DBED000h
0x14007bb5e  mov     rax, rax
0x14007bb61  cmp     rsi, rax
0x14007bb64  jb      short loc_14007BBC8
0x14007bb66  mov     rax, 0FFFFF6FB7DBED800h
0x14007bb70  mov     rax, rax
0x14007bb73  cmp     rsi, rax
0x14007bb76  jnb     short loc_14007BBC8
0x14007bb78  mov     rax, gs:8
0x14007bb81  test    rax, rax
0x14007bb84  jz      short loc_14007BB8C
0x14007bb86  mov     rcx, [rax+50h]
0x14007bb8a  jmp     short loc_14007BB8F
0x14007bb8c  mov     rcx, r15
0x14007bb8f  mov     rdx, [rcx+0E8h]
0x14007bb96  test    rdx, rdx
0x14007bb99  jz      short loc_14007BBC8
0x14007bb9b  mov     ecx, cs:SkiKvaShadowMode
0x14007bba1  mov     rax, rsi
0x14007bba4  sar     rax, 3
0x14007bba8  and     eax, 1FFh
0x14007bbad  mov     [rdx+rax*8], rdi
0x14007bbb1  cmp     ecx, 2
0x14007bbb4  jz      short loc_14007BBC8
0x14007bbb6  mov     rdi, [rsp+1B0h+var_178]
0x14007bbbb  mov     rax, 8000000000000063h
0x14007bbc5  or      rdi, rax
0x14007bbc8  mov     rax, 0FFFFFFFFFF000h
0x14007bbd2  mov     [rsi], rdi
0x14007bbd5  and     rbx, rax
0x14007bbd8  mov     r13d, 200h
0x14007bbde  or      rbx, 0B21h
0x14007bbe5  mov     rsi, 0FFF0000000000FFFh
0x14007bbef  mov     rax, [r12]
0x14007bbf3  mov     r9, rbx
0x14007bbf6  xor     r8d, r8d
0x14007bbf9  mov     [rsp+1B0h+var_190], rax
0x14007bbfe  mov     rdx, r12
0x14007bc01  xor     ecx, ecx
0x14007bc03  call    SkmiGetPteTrace
0x14007bc08  mov     r15, rax
0x14007bc0b  test    rax, rax
0x14007bc0e  jz      short loc_14007BC68
0x14007bc10  xor     edx, edx; Val
0x14007bc12  lea     rdi, [rax+20h]
0x14007bc16  mov     rcx, rdi; void *
0x14007bc19  lea     r8d, [rdx+40h]; Size
0x14007bc1d  call    memset_0
0x14007bc22  test    cs:SkmiFlags, 400000h
0x14007bc2c  jz      short loc_14007BC68
0x14007bc2e  mov     rcx, gs:8; FramesToSkip
0x14007bc37  test    rcx, rcx
0x14007bc3a  jz      short loc_14007BC68
0x14007bc3c  lea     r9, [rbp+0B0h+BackTraceHash]; BackTraceHash
0x14007bc43  mov     r8, rdi; BackTrace
0x14007bc46  mov     edx, 8; FramesToCapture
0x14007bc4b  call    RtlCaptureStackBackTrace
0x14007bc50  test    ax, ax
0x14007bc53  jnz     short loc_14007BC68
0x14007bc55  mov     rax, [rbp+0B8h]
0x14007bc5c  mov     [r15+28h], rax
0x14007bc60  call    SkmiGetInstructionPointer
0x14007bc65  mov     [rdi], rax
0x14007bc68  mov     [r12], rbx
0x14007bc6c  lea     rcx, [rbx+1000h]
0x14007bc73  xor     rbx, rcx
0x14007bc76  add     r12, 8
0x14007bc7a  and     rbx, rsi
0x14007bc7d  xor     rbx, rcx
0x14007bc80  sub     r13, 1
0x14007bc84  jnz     loc_14007BBEF
0x14007bc8a  mov     rcx, [rbp+0B0h+arg_8]
0x14007bc91  xor     r15d, r15d
0x14007bc94  mov     rsi, [rbp+0B0h+arg_18]
0x14007bc9b  mov     r14, [rsp+1B0h+var_180]
0x14007bca0  add     rsi, 8
0x14007bca4  mov     [rbp+0B0h+arg_18], rsi
0x14007bcab  mov     [rcx], r15w
0x14007bcaf  add     rcx, 2
0x14007bcb3  mov     [rbp+0B0h+arg_8], rcx
0x14007bcba  mov     r13, 0FFFFF68000000000h
0x14007bcc4  cmp     rsi, [rsp+1B0h+var_170]
0x14007bcc9  jbe     loc_14007B9A5
0x14007bccf  mov     rbx, [rsp+1B0h+var_168]
0x14007bcd4  mov     r12, 8000000000000063h
0x14007bcde  mov     ecx, [r14+8]
0x14007bce2  cmp     ecx, 18h
0x14007bce5  jb      loc_14007B8C0
0x14007bceb  test    ecx, 0FFFh
0x14007bcf1  mov     eax, r15d
0x14007bcf4  setnz   al
0x14007bcf7  shr     ecx, 0Ch
0x14007bcfa  lea     r15d, [rax+rcx]
0x14007bcfe  mov     edx, r15d
0x14007bd01  mov     dword ptr [rbp+0B0h+BackTraceHash], r15d
0x14007bd08  lea     rcx, SkmiSystemPtes
0x14007bd0f  call    SkmiAllocateSystemPtes
  ... truncated ...
```
