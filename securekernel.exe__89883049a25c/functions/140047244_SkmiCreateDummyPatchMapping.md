# SkmiCreateDummyPatchMapping

- ea: `0x140047244`
- end: `0x140047abf`
- name: `SkmiCreateDummyPatchMapping`
- size: `2171`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140049388`

## callees

- `0x140003780`
- `0x140014740`
- `0x1400241cc`
- `0x140027ac0`
- `0x14002b534`
- `0x140030f10`
- `0x140047244`
- `0x140081290`
- `0x1400a78dc`
- `0x1400f9780`
- `0x1400f9a80`
- `0x1400fe238`
- `0x1400fe2b4`

## pseudocode

```c
__int64 __fastcall SkmiCreateDummyPatchMapping(char **a1, int *a2, unsigned int a3, __int64 *a4)
{
  char *v4; // r10
  unsigned int v6; // r9d
  __int64 SystemPtes; // rax
  unsigned __int64 v11; // rbx
  int v12; // r8d
  char *v13; // rax
  int v14; // r14d
  int v15; // edx
  unsigned int v16; // ecx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r13
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // r8
  char *v22; // r9
  bool v23; // zf
  char *v24; // r10
  char *v25; // r11
  __int64 v26; // r9
  bool v27; // al
  char *v28; // rdx
  __int64 v29; // r12
  __int64 PteTrace; // rax
  __int64 v31; // r15
  PVOID *v32; // r14
  PVOID StackBase; // rcx
  USHORT v34; // ax
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  _QWORD *v38; // rcx
  char *v39; // rdx
  __int64 v40; // r8
  int v41; // edx
  char *v42; // rax
  ULONG v43; // ecx
  __int64 v44; // rdx
  ULONG v45; // eax
  ULONG v46; // r15d
  char *v47; // rcx
  __int64 v48; // r14
  unsigned __int64 v49; // rbx
  __int64 v50; // rax
  __int64 v51; // r13
  PVOID *v52; // r12
  PVOID v53; // rcx
  USHORT v54; // ax
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  char *v58; // rcx
  __int64 v59; // rdx
  int v60; // ecx
  unsigned int v61; // r14d
  unsigned int v62; // r12d
  char *v63; // r13
  __int64 v64; // rax
  unsigned int v65; // r15d
  unsigned __int64 v66; // rbx
  __int64 v67; // r15
  __int64 v68; // rax
  __int64 v69; // r13
  PVOID *v70; // r12
  PVOID v71; // rcx
  USHORT v72; // ax
  __int64 v73; // rdx
  __int64 v74; // rcx
  _QWORD *v75; // rax
  char *v76; // rcx
  __int64 v77; // rdx
  int v78; // ecx
  char *v79; // rbx
  int v80; // esi
  char *v81; // r14
  char *v82; // r15
  char *v83; // r12
  __int64 v84; // r9
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-30h] BYREF
  int v86; // [rsp+38h] [rbp-28h]
  ULONG v87; // [rsp+3Ch] [rbp-24h] BYREF
  unsigned __int64 v88; // [rsp+40h] [rbp-20h] BYREF
  char *v89; // [rsp+48h] [rbp-18h]
  __int64 v90; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v92; // [rsp+A0h] [rbp+40h] BYREF
  int *v93; // [rsp+A8h] [rbp+48h]
  unsigned int v94; // [rsp+B0h] [rbp+50h]

  v94 = a3;
  v4 = 0;
  BackTraceHash[0] = 0;
  v6 = a3;
  v92 = 0;
  if ( a1 )
  {
    *(_OWORD *)a4 = *(_OWORD *)a1;
    *((_OWORD *)a4 + 1) = *((_OWORD *)a1 + 1);
    *((_OWORD *)a4 + 2) = *((_OWORD *)a1 + 2);
    *((_OWORD *)a4 + 3) = *((_OWORD *)a1 + 3);
    *((_OWORD *)a4 + 4) = *((_OWORD *)a1 + 4);
    *((_OWORD *)a4 + 5) = *((_OWORD *)a1 + 5);
    *((_OWORD *)a4 + 6) = *((_OWORD *)a1 + 6);
    *((_OWORD *)a4 + 7) = *((_OWORD *)a1 + 7);
    *((_OWORD *)a4 + 8) = *((_OWORD *)a1 + 8);
    *((_OWORD *)a4 + 9) = *((_OWORD *)a1 + 9);
    *((_OWORD *)a4 + 10) = *((_OWORD *)a1 + 10);
    *((_OWORD *)a4 + 11) = *((_OWORD *)a1 + 11);
    *((_OWORD *)a4 + 12) = *((_OWORD *)a1 + 12);
    SystemPtes = SkmiAllocateSystemPtes((__int64)&SkmiSystemPtes, *((_DWORD *)a1 + 37));
    v4 = 0;
    v89 = (char *)SystemPtes;
    if ( !SystemPtes )
      return 3221225626LL;
    a4[1] = SystemPtes;
    v6 = v94;
    *a4 = SystemPtes << 25 >> 16;
    a4[3] = (__int64)((SystemPtes << 25) + ((unsigned __int64)*((unsigned int *)a4 + 38) << 28)) >> 16;
  }
  else
  {
    v89 = (char *)a4[1];
  }
  v11 = ((unsigned __int64)(word_140156D90 & 1) << 8) | 0x8000000000000063uLL;
  v88 = v11;
LABEL_65:
  while ( a2 )
  {
    v12 = *a2;
    v87 = v12;
    if ( !v12 )
      break;
    v13 = (char *)a4[9];
    v93 = ++a2;
    v14 = v12 & 0xFFF;
    v86 = v14;
    v15 = *((_DWORD *)v13 + 24);
    if ( v12 < 0 )
    {
      if ( v15 )
      {
        v16 = (unsigned int)v4;
        v17 = 0x8000;
      }
      else
      {
        v16 = 1;
        v17 = 0x4000;
      }
    }
    else
    {
      v16 = (unsigned int)v4;
      LOBYTE(v16) = v15 != 0;
      v17 = v15 != 0 ? 0x4000 : 0x8000;
    }
    if ( (v12 & v17) != 0 && (!v16 || (v12 & 0xFC000) == 0x5C000) )
    {
      if ( (v12 & 0xFFF) != 0 )
      {
        v18 = v16;
        v90 = v16;
        while ( 1 )
        {
          RtlDetermineHotPatchExtent(v12, a2[v18], v12, (unsigned int)BackTraceHash, (__int64)&v92);
          v19 = BackTraceHash[0];
          v4 = 0;
          if ( !a1 || !a1[17] )
            goto LABEL_35;
          v20 = (unsigned __int64)a1[16];
          if ( BackTraceHash[0] < v20 )
          {
            v21 = v92 - BackTraceHash[0] + 1;
            if ( v92 - BackTraceHash[0] != -1 )
              break;
          }
LABEL_62:
          v6 = v94;
          --v14;
          v12 = v87;
          v18 = v90;
          v86 = v14;
          a2 += v94;
          v93 = a2;
          if ( !v14 )
            goto LABEL_65;
        }
        v22 = a1[17];
        if ( v21 == 1 )
        {
          v23 = _bittest64(
                  (const signed __int64 *)&v22[8 * ((unsigned __int64)BackTraceHash[0] >> 6)],
                  BackTraceHash[0] & 0x3F) == 0;
          goto LABEL_33;
        }
        if ( v20 - BackTraceHash[0] < v21 )
          goto LABEL_62;
        v24 = &v22[8 * ((unsigned __int64)BackTraceHash[0] >> 6)];
        v25 = &v22[8 * ((v21 + BackTraceHash[0] - 1LL) >> 6)];
        v26 = *(_QWORD *)v24;
        if ( v24 == v25 )
        {
          v27 = ((0xFFFFFFFFFFFFFFFFuLL >> (64 - ((unsigned __int8)v92 - LOBYTE(BackTraceHash[0]) + 1)) << SLOBYTE(BackTraceHash[0]))
               & v26) == 0;
          v4 = 0;
        }
        else
        {
          if ( ((-1LL << SLOBYTE(BackTraceHash[0])) & v26) != 0 )
          {
            v4 = 0;
            goto LABEL_62;
          }
          v28 = v24 + 8;
          v4 = 0;
          while ( v28 != v25 )
          {
            if ( *(_QWORD *)v28 )
              goto LABEL_62;
            v28 += 8;
          }
          v23 = ((0xFFFFFFFFFFFFFFFFuLL >> ~(_BYTE)v92) & *(_QWORD *)v28) == 0;
LABEL_33:
          v27 = v23;
        }
        if ( !v27 )
          goto LABEL_62;
LABEL_35:
        if ( BackTraceHash[0] > v92 )
          goto LABEL_62;
        while ( 2 )
        {
          v29 = (__int64)&v89[8 * v19];
          *(_QWORD *)BackTraceHash = *(_QWORD *)v29;
          if ( (BackTraceHash[0] & 1) == 0 )
          {
            if ( a1 )
            {
              if ( !(unsigned int)SkmiAllocateSinglePage(0, &v88) )
                goto LABEL_120;
              v11 = v88;
LABEL_45:
              PteTrace = SkmiGetPteTrace(0, v29, 0, v11, *(_QWORD *)v29);
              v31 = PteTrace;
              if ( PteTrace )
              {
                v32 = (PVOID *)(PteTrace + 32);
                memset_0((void *)(PteTrace + 32), 0, 0x40u);
                v4 = 0;
                if ( (SkmiFlags & 0x400000) != 0 )
                {
                  StackBase = KeGetPcr()->NtTib.StackBase;
                  if ( StackBase )
                  {
                    v34 = RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v32, BackTraceHash);
                    v4 = 0;
                    if ( !v34 )
                    {
                      *(_QWORD *)(v31 + 40) = retaddr;
                      *v32 = (PVOID)SkmiGetInstructionPointer(v36, v35);
                    }
                  }
                }
              }
              v37 = v11;
              if ( (unsigned __int64)v29 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v29 < 0xFFFFF6FB7DBED800uLL )
              {
                v38 = KeGetPcr()->NtTib.StackBase;
                if ( v38 )
                  v39 = (char *)v38[10];
                else
                  v39 = v4;
                v40 = *((_QWORD *)v39 + 29);
                if ( v40 )
                {
                  v41 = SkiKvaShadowMode;
                  *(_QWORD *)(v40 + 8 * ((v29 >> 3) & 0x1FF)) = v11;
                  if ( v41 != 2 && (v11 & 1) != 0 )
                    v37 = v11 | 0x8000000000000000uLL;
                }
              }
              *(_QWORD *)v29 = v37;
            }
            else if ( (char *)a4[15] == v4
                   || (unsigned int)v19 >= (unsigned __int64)a4[14]
                   || !_bittest64(
                         (const signed __int64 *)(a4[15] + 8 * ((unsigned __int64)(unsigned int)v19 >> 6)),
                         v19 & 0x3F) )
            {
              SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash);
              v11 = *(_QWORD *)BackTraceHash & 0xFFFFFFFFFF000LL | v11 & 0xFFF0000000000FFFuLL;
              v88 = v11;
              goto LABEL_45;
            }
          }
          v19 = (unsigned int)(v19 + 1);
          BackTraceHash[0] = v19;
          if ( (unsigned int)v19 > v92 )
          {
            v14 = v86;
            a2 = v93;
            goto LABEL_62;
          }
          continue;
        }
      }
    }
    else
    {
      a2 += v6 * v14;
    }
  }
  if ( !a1 )
    return 0;
  v42 = a1[9];
  v43 = *((_DWORD *)v42 + 16);
  v44 = *((_QWORD *)v42 + 11);
  v45 = (unsigned int)v4;
  v86 = (int)v4;
  v90 = v44;
  v87 = v43;
  if ( !v43 )
  {
LABEL_91:
    v61 = *((_DWORD *)a1 + 38);
    v62 = *((_DWORD *)a1[9] + 15) + v61 - 1;
    v92 = v62;
    if ( v61 <= v62 )
    {
      v63 = v89;
      v64 = v61;
      v65 = v61;
      do
      {
        if ( *(char **)&v63[8 * v64] == v4 )
        {
          if ( !(unsigned int)SkmiAllocateSinglePage(0, &v88) )
            goto LABEL_120;
          v66 = v88;
          v67 = (__int64)&v63[8 * v65];
          v68 = SkmiGetPteTrace(0, v67, 0, v88, *(_QWORD *)v67);
          v69 = v68;
          if ( v68 )
          {
            v70 = (PVOID *)(v68 + 32);
            memset_0((void *)(v68 + 32), 0, (unsigned int)((_DWORD)v4 + 64));
            v4 = 0;
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              v71 = KeGetPcr()->NtTib.StackBase;
              if ( v71 )
              {
                v72 = RtlCaptureStackBackTrace((ULONG)v71, 8u, v70, &v87);
                v4 = 0;
                if ( !v72 )
                {
                  *(_QWORD *)(v69 + 40) = retaddr;
                  *v70 = (PVOID)SkmiGetInstructionPointer(v74, v73);
                }
              }
            }
            v62 = v92;
          }
          if ( (unsigned __int64)v67 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v67 < 0xFFFFF6FB7DBED800uLL )
          {
            v75 = KeGetPcr()->NtTib.StackBase;
            v76 = v75 ? (char *)v75[10] : v4;
            v77 = *((_QWORD *)v76 + 29);
            if ( v77 )
            {
              v78 = SkiKvaShadowMode;
              *(_QWORD *)(v77 + 8 * ((v67 >> 3) & 0x1FF)) = v66;
              if ( v78 != 2 && (v66 & 1) != 0 )
                v66 |= 0x8000000000000000uLL;
            }
          }
          v63 = v89;
          *(_QWORD *)v67 = v66;
        }
        v64 = ++v61;
        v65 = v61;
      }
      while ( v61 <= v62 );
    }
    v79 = (char *)*a4;
    v80 = *((_DWORD *)a1 + 37);
    v81 = a1[2];
    v82 = *a1;
    if ( v80 )
    {
      v83 = v89;
      do
      {
        if ( *(char **)v83 != v4 )
        {
          memmove(v79, v82, 0x1000u);
          if ( ((_DWORD)a1[25] & 1) != 0 )
            SkpgVerifyPage(v81, 0x40000000, v79, v84);
          v4 = 0;
        }
        v83 += 8;
        v81 += 4096;
        v82 += 4096;
        v79 += 4096;
        --v80;
      }
      while ( v80 );
    }
    return 0;
  }
  while ( 1 )
  {
    if ( (unsigned __int8)RtlDetermineHotPatchUndoExtent(v44, v44, v45, (unsigned int)BackTraceHash, (__int64)&v92) )
    {
      v46 = BackTraceHash[0];
      if ( BackTraceHash[0] <= v92 )
        break;
    }
LABEL_90:
    v45 = v86 + 1;
    v86 = v45;
    if ( v45 >= v87 )
      goto LABEL_91;
  }
  v47 = v89;
  while ( 1 )
  {
    v48 = (__int64)&v47[8 * v46];
    *(_QWORD *)BackTraceHash = *(_QWORD *)v48;
    if ( (BackTraceHash[0] & 1) == 0 )
      break;
LABEL_88:
    BackTraceHash[0] = ++v46;
    if ( v46 > v92 )
    {
      LODWORD(v44) = v90;
      goto LABEL_90;
    }
  }
  if ( (unsigned int)SkmiAllocateSinglePage(0, &v88) )
  {
    v49 = v88;
    v50 = SkmiGetPteTrace(0, v48, 0, v88, *(_QWORD *)v48);
    v51 = v50;
    if ( v50 )
    {
      v52 = (PVOID *)(v50 + 32);
      memset_0((void *)(v50 + 32), 0, (unsigned int)((_DWORD)v4 + 64));
      v4 = 0;
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v53 = KeGetPcr()->NtTib.StackBase;
        if ( v53 )
        {
          v54 = RtlCaptureStackBackTrace((ULONG)v53, 8u, v52, BackTraceHash);
          v4 = 0;
          if ( !v54 )
          {
            *(_QWORD *)(v51 + 40) = retaddr;
            *v52 = (PVOID)SkmiGetInstructionPointer(v56, v55);
          }
        }
      }
    }
    if ( (unsigned __int64)v48 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v48 < 0xFFFFF6FB7DBED800uLL )
    {
      v57 = KeGetPcr()->NtTib.StackBase;
      v58 = v57 ? (char *)v57[10] : v4;
      v59 = *((_QWORD *)v58 + 29);
      if ( v59 )
      {
        v60 = SkiKvaShadowMode;
        *(_QWORD *)(v59 + 8 * ((v48 >> 3) & 0x1FF)) = v49;
        if ( v60 != 2 && (v49 & 1) != 0 )
          v49 |= 0x8000000000000000uLL;
      }
    }
    v47 = v89;
    *(_QWORD *)v48 = v49;
    goto LABEL_88;
  }
LABEL_120:
  SkmiFreeDummyPatchMapping(a4);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140047244  mov     [rsp-38h+arg_18], rbx
0x140047249  mov     [rsp-38h+arg_10], r8d
0x14004724e  push    rbp
0x14004724f  push    rsi
0x140047250  push    rdi
0x140047251  push    r12
0x140047253  push    r13
0x140047255  push    r14
0x140047257  push    r15
0x140047259  mov     rbp, rsp
0x14004725c  sub     rsp, 60h
0x140047260  xor     r10d, r10d
0x140047263  mov     rsi, r9
0x140047266  mov     [rbp+BackTraceHash], r10d
0x14004726a  mov     r9d, r8d
0x14004726d  mov     [rbp+arg_0], r10d
0x140047271  mov     r12, rdx
0x140047274  mov     rdi, rcx
0x140047277  test    rcx, rcx
0x14004727a  jz      loc_14004736D
0x140047280  movups  xmm0, xmmword ptr [rcx]
0x140047283  movups  xmmword ptr [rsi], xmm0
0x140047286  movups  xmm1, xmmword ptr [rcx+10h]
0x14004728a  movups  xmmword ptr [rsi+10h], xmm1
0x14004728e  movups  xmm0, xmmword ptr [rcx+20h]
0x140047292  movups  xmmword ptr [rsi+20h], xmm0
0x140047296  movups  xmm1, xmmword ptr [rcx+30h]
0x14004729a  movups  xmmword ptr [rsi+30h], xmm1
0x14004729e  movups  xmm0, xmmword ptr [rcx+40h]
0x1400472a2  movups  xmmword ptr [rsi+40h], xmm0
0x1400472a6  movups  xmm1, xmmword ptr [rcx+50h]
0x1400472aa  movups  xmmword ptr [rsi+50h], xmm1
0x1400472ae  movups  xmm0, xmmword ptr [rcx+60h]
0x1400472b2  movups  xmmword ptr [rsi+60h], xmm0
0x1400472b6  movups  xmm1, xmmword ptr [rcx+70h]
0x1400472ba  movups  xmmword ptr [rsi+70h], xmm1
0x1400472be  movups  xmm0, xmmword ptr [rcx+80h]
0x1400472c5  movups  xmmword ptr [rsi+80h], xmm0
0x1400472cc  movups  xmm1, xmmword ptr [rcx+90h]
0x1400472d3  movups  xmmword ptr [rsi+90h], xmm1
0x1400472da  movups  xmm0, xmmword ptr [rcx+0A0h]
0x1400472e1  movups  xmmword ptr [rsi+0A0h], xmm0
0x1400472e8  movups  xmm1, xmmword ptr [rcx+0B0h]
0x1400472ef  movups  xmmword ptr [rsi+0B0h], xmm1
0x1400472f6  movups  xmm0, xmmword ptr [rcx+0C0h]
0x1400472fd  movups  xmmword ptr [rsi+0C0h], xmm0
0x140047304  mov     edx, [rcx+94h]
0x14004730a  lea     rcx, SkmiSystemPtes
0x140047311  call    SkmiAllocateSystemPtes
0x140047316  xor     r10d, r10d
0x140047319  mov     [rbp+var_18], rax
0x14004731d  test    rax, rax
0x140047320  jnz     short loc_14004732C
0x140047322  mov     eax, 0C000009Ah
0x140047327  jmp     loc_140047A99
0x14004732c  mov     rcx, rax
0x14004732f  mov     [rsi+8], rax
0x140047333  shl     rcx, 19h
0x140047337  mov     rax, 0FFFFF68000000000h
0x140047341  mov     r9d, [rbp+arg_10]
0x140047345  shl     rax, 19h
0x140047349  sub     rcx, rax
0x14004734c  mov     rax, rcx
0x14004734f  sar     rax, 10h
0x140047353  mov     [rsi], rax
0x140047356  mov     eax, [rsi+98h]
0x14004735c  shl     rax, 1Ch
0x140047360  add     rax, rcx
0x140047363  sar     rax, 10h
0x140047367  mov     [rsi+18h], rax
0x14004736b  jmp     short loc_140047375
0x14004736d  mov     rax, [rsi+8]
0x140047371  mov     [rbp+var_18], rax
0x140047375  movzx   ebx, byte ptr cs:word_140156D90
0x14004737c  mov     rax, 8000000000000063h
0x140047386  and     ebx, 1
0x140047389  shl     rbx, 8
0x14004738d  or      rbx, rax
0x140047390  mov     [rbp+var_20], rbx
0x140047394  jmp     loc_140047723
0x140047399  mov     r8d, [r12]
0x14004739d  mov     [rbp+var_24], r8d
0x1400473a1  test    r8d, r8d
0x1400473a4  jz      loc_14004772C
0x1400473aa  mov     rax, [rsi+48h]
0x1400473ae  add     r12, 4
0x1400473b2  mov     r14d, r8d
0x1400473b5  mov     [rbp+arg_8], r12
0x1400473b9  and     r14d, 0FFFh
0x1400473c0  mov     [rbp+var_28], r14d
0x1400473c4  mov     edx, [rax+60h]
0x1400473c7  test    r8d, r8d
0x1400473ca  js      short loc_1400473E4
0x1400473cc  test    edx, edx
0x1400473ce  mov     ecx, r10d
0x1400473d1  setnz   cl
0x1400473d4  neg     edx
0x1400473d6  sbb     eax, eax
0x1400473d8  and     eax, 0FFFFC000h
0x1400473dd  add     eax, 8000h
0x1400473e2  jmp     short loc_1400473FA
0x1400473e4  test    edx, edx
0x1400473e6  jnz     short loc_1400473F2
0x1400473e8  lea     ecx, [rdx+1]
0x1400473eb  mov     eax, 4000h
0x1400473f0  jmp     short loc_1400473FA
0x1400473f2  mov     ecx, r10d
0x1400473f5  mov     eax, 8000h
0x1400473fa  test    eax, r8d
0x1400473fd  jz      loc_14004771B
0x140047403  test    ecx, ecx
0x140047405  jz      short loc_14004741A
0x140047407  mov     eax, r8d
0x14004740a  and     eax, 0FC000h
0x14004740f  cmp     eax, 5C000h
0x140047414  jnz     loc_14004771B
0x14004741a  test    r14d, r14d
0x14004741d  jz      loc_140047723
0x140047423  mov     eax, ecx
0x140047425  mov     [rbp+var_10], rax
0x140047429  mov     edx, [r12+rax*4]
0x14004742d  lea     rcx, [rbp+arg_0]
0x140047431  mov     [rsp+60h+var_40], rcx
0x140047436  lea     r9, [rbp+BackTraceHash]
0x14004743a  mov     ecx, r8d
0x14004743d  call    RtlDetermineHotPatchExtent
0x140047442  mov     r13d, [rbp+BackTraceHash]
0x140047446  xor     r10d, r10d
0x140047449  test    rdi, rdi
0x14004744c  jz      loc_14004753F
0x140047452  cmp     [rdi+88h], r10
0x140047459  jz      loc_14004753F
0x14004745f  mov     rcx, [rdi+80h]
0x140047466  mov     edx, r13d
0x140047469  cmp     r13, rcx
0x14004746c  jnb     loc_1400476F5
0x140047472  mov     r8d, [rbp+arg_0]
0x140047476  sub     r8d, r13d
0x140047479  add     r8d, 1
0x14004747d  jz      loc_1400476F5
0x140047483  mov     r9, [rdi+88h]
0x14004748a  cmp     r8, 1
0x14004748e  jnz     short loc_1400474A8
0x140047490  mov     eax, edx
0x140047492  shr     rdx, 6
0x140047496  and     eax, 3Fh
0x140047499  bt      [r9+rdx*8], rax
0x14004749e  setb    al
0x1400474a1  test    al, al
0x1400474a3  jmp     loc_140047534
0x1400474a8  sub     rcx, rdx
0x1400474ab  cmp     rcx, r8
0x1400474ae  jb      loc_1400476F5
0x1400474b4  mov     rax, rdx
0x1400474b7  lea     r15, [r13-1]
0x1400474bb  shr     rax, 6
0x1400474bf  add     r15, r8
0x1400474c2  lea     r10, [r9+rax*8]
0x1400474c6  mov     rax, r15
0x1400474c9  shr     rax, 6
0x1400474cd  lea     r11, [r9+rax*8]
0x1400474d1  mov     r9, [r10]
0x1400474d4  cmp     r10, r11
0x1400474d7  jnz     short loc_1400474F9
0x1400474d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400474dd  mov     ecx, 40h ; '@'
0x1400474e2  sub     cl, r8b
0x1400474e5  shr     rax, cl
0x1400474e8  mov     rcx, rdx
0x1400474eb  shl     rax, cl
0x1400474ee  test    r9, rax
0x1400474f1  setz    al
0x1400474f4  xor     r10d, r10d
0x1400474f7  jmp     short loc_140047537
0x1400474f9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400474fd  mov     rcx, rdx
0x140047500  mov     rax, r8
0x140047503  shl     rax, cl
0x140047506  test    r9, rax
0x140047509  jnz     short loc_140047585
0x14004750b  lea     rdx, [r10+8]
0x14004750f  xor     r10d, r10d
0x140047512  cmp     rdx, r11
0x140047515  jz      short loc_140047526
0x140047517  cmp     [rdx], r10
0x14004751a  jnz     loc_1400476F5
0x140047520  add     rdx, 8
0x140047524  jmp     short loc_140047512
0x140047526  mov     cl, r15b
0x140047529  mov     rax, r8
0x14004752c  not     cl
0x14004752e  shr     rax, cl
0x140047531  test    [rdx], rax
0x140047534  setz    al
0x140047537  test    al, al
0x140047539  jz      loc_1400476F5
0x14004753f  cmp     r13d, [rbp+arg_0]
0x140047543  ja      loc_1400476F5
0x140047549  mov     rax, [rbp+var_18]
0x14004754d  mov     edx, r13d
0x140047550  lea     r12, [rax+r13*8]
0x140047554  mov     rax, [r12]
0x140047558  mov     qword ptr [rbp+BackTraceHash], rax
0x14004755c  test    al, 1
0x14004755e  jnz     loc_1400476DC
0x140047564  test    rdi, rdi
0x140047567  jz      short loc_14004758D
0x140047569  lea     rdx, [rbp+var_20]
0x14004756d  xor     ecx, ecx
0x14004756f  call    SkmiAllocateSinglePage
0x140047574  xor     r10d, r10d
0x140047577  test    eax, eax
0x140047579  jz      loc_140047AB2
0x14004757f  mov     rbx, [rbp+var_20]
0x140047583  jmp     short loc_1400475E8
0x140047585  xor     r10d, r10d
0x140047588  jmp     loc_1400476F5
0x14004758d  cmp     [rsi+78h], r10
0x140047591  jz      short loc_1400475BA
0x140047593  mov     rax, [rsi+70h]
0x140047597  cmp     rdx, rax
0x14004759a  jnb     short loc_1400475BA
0x14004759c  mov     rax, [rsi+78h]
0x1400475a0  mov     rcx, rdx
0x1400475a3  shr     rdx, 6
0x1400475a7  and     ecx, 3Fh
0x1400475aa  bt      [rax+rdx*8], rcx
0x1400475af  setb    al
0x1400475b2  test    al, al
0x1400475b4  jnz     loc_1400476DC
0x1400475ba  lea     rcx, [rbp+BackTraceHash]
0x1400475be  call    SKMI_UNSWIZZLE_INVALID_PTE
0x1400475c3  mov     rax, 0FFF0000000000FFFh
0x1400475cd  mov     rcx, 0FFFFFFFFFF000h
0x1400475d7  and     rbx, rax
0x1400475da  mov     rax, qword ptr [rbp+BackTraceHash]
0x1400475de  and     rax, rcx
0x1400475e1  or      rbx, rax
0x1400475e4  mov     [rbp+var_20], rbx
0x1400475e8  mov     rax, [r12]
0x1400475ec  mov     r9, rbx
0x1400475ef  xor     r8d, r8d
0x1400475f2  mov     [rsp+60h+var_40], rax
0x1400475f7  mov     rdx, r12
0x1400475fa  xor     ecx, ecx
0x1400475fc  call    SkmiGetPteTrace
0x140047601  mov     r15, rax
0x140047604  test    rax, rax
0x140047607  jz      short loc_140047660
0x140047609  xor     edx, edx; Val
0x14004760b  lea     r14, [rax+20h]
0x14004760f  mov     rcx, r14; void *
0x140047612  lea     r8d, [rdx+40h]; Size
0x140047616  call    memset_0
0x14004761b  xor     r10d, r10d
0x14004761e  test    cs:SkmiFlags, 400000h
0x140047628  jz      short loc_140047660
0x14004762a  mov     rcx, gs:8; FramesToSkip
0x140047633  test    rcx, rcx
0x140047636  jz      short loc_140047660
0x140047638  lea     r9, [rbp+BackTraceHash]; BackTraceHash
0x14004763c  mov     r8, r14; BackTrace
0x14004763f  lea     edx, [r10+8]; FramesToCapture
0x140047643  call    RtlCaptureStackBackTrace
0x140047648  xor     r10d, r10d
0x14004764b  test    ax, ax
0x14004764e  jnz     short loc_140047660
0x140047650  mov     rax, [rbp+38h]
0x140047654  mov     [r15+28h], rax
0x140047658  call    SkmiGetInstructionPointer
0x14004765d  mov     [r14], rax
0x140047660  mov     rax, rbx
0x140047663  mov     rcx, 0FFFFF6FB7DBED000h
0x14004766d  mov     rcx, rcx
0x140047670  cmp     r12, rcx
0x140047673  jb      short loc_1400476D8
0x140047675  mov     rcx, 0FFFFF6FB7DBED800h
0x14004767f  mov     rcx, rcx
0x140047682  cmp     r12, rcx
0x140047685  jnb     short loc_1400476D8
0x140047687  mov     rcx, gs:8
0x140047690  test    rcx, rcx
0x140047693  jz      short loc_14004769B
0x140047695  mov     rdx, [rcx+50h]
0x140047699  jmp     short loc_14004769E
0x14004769b  mov     rdx, r10
0x14004769e  mov     r8, [rdx+0E8h]
0x1400476a5  test    r8, r8
0x1400476a8  jz      short loc_1400476D8
0x1400476aa  mov     edx, cs:SkiKvaShadowMode
0x1400476b0  mov     rcx, r12
0x1400476b3  sar     rcx, 3
0x1400476b7  and     ecx, 1FFh
0x1400476bd  mov     [r8+rcx*8], rbx
0x1400476c1  cmp     edx, 2
0x1400476c4  jz      short loc_1400476D8
0x1400476c6  test    bl, 1
0x1400476c9  jz      short loc_1400476D8
0x1400476cb  mov     rcx, 8000000000000000h
0x1400476d5  or      rax, rcx
  ... truncated ...
```
