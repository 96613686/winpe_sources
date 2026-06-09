# CEngineLocaleHandler::FormatDisplayText(ushort const *,ushort const *,ulong,ulong,ulong,SPPHRASEELEMENT *,ulong,ulong,SPPHRASEREPLACEMENT * * *,ulong *,ulong *,ulong *,uchar *,uchar *,int *,ushort const *)

- ea: `0x1800cf4d0`
- end: `0x1800d034f`
- name: `?FormatDisplayText@CEngineLocaleHandler@@UEAAJPEBG0KKKPEAUSPPHRASEELEMENT@@KKPEAPEAPEAUSPPHRASEREPLACEMENT@@PEAK33PEAE4PEAH0@Z`
- size: `3711`
- prototype: `__int64 __fastcall(CEngineLocaleHandler *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, char, struct SPPHRASEELEMENT *, unsigned int, unsigned int, struct SPPHRASEREPLACEMENT ***, unsigned int *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned __int8 *, int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002470`
- `0x1800035b0`
- `0x180004312`
- `0x1800c942c`
- `0x1800c963c`
- `0x1800c973c`
- `0x1800cf2b8`
- `0x1800cf344`
- `0x1800cf4d0`
- `0x1800d0358`
- `0x1800d1378`
- `0x1800f6bc8`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800cf9cf`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800cfcdc`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800cf9cf`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800cfcdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d0049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d0049`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandler::FormatDisplayText(
        CEngineLocaleHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        char a6,
        struct SPPHRASEELEMENT *a7,
        unsigned int a8,
        unsigned int a9,
        struct SPPHRASEREPLACEMENT ***a10,
        unsigned int *a11,
        unsigned int *a12,
        unsigned int *a13,
        unsigned __int8 *a14,
        unsigned __int8 *a15,
        int *a16,
        unsigned __int16 *a17)
{
  CEngineLocaleHandler *v17; // r14
  unsigned int v19; // r12d
  int v20; // edi
  char *v21; // rdx
  _DWORD *v22; // r10
  __int64 v23; // rax
  bool v24; // cf
  unsigned __int64 v25; // rax
  char *v26; // rax
  const struct CSrTokenDL *v27; // r15
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  char *v30; // rax
  char *v31; // rsi
  unsigned int v32; // r13d
  __int64 v33; // r12
  unsigned __int16 **v34; // rdi
  const unsigned __int16 *pszDisplayText; // r8
  CSrTokenDL *v36; // rcx
  unsigned int v37; // ebx
  unsigned int v38; // r13d
  bool v39; // zf
  struct CSrTokenDL *v40; // r12
  unsigned int v41; // eax
  __int64 v42; // rcx
  unsigned int v43; // r12d
  char *v44; // r13
  unsigned int v45; // eax
  unsigned int v46; // r8d
  unsigned int v47; // ecx
  unsigned int v48; // r13d
  unsigned int v49; // r12d
  char *v50; // rbx
  __int64 v51; // rax
  unsigned int v52; // r9d
  __int64 v53; // rcx
  __int64 v54; // rbx
  int v55; // eax
  int v56; // ecx
  CSrTokenDL *v57; // r12
  char *v58; // rbx
  char *v59; // r8
  char *v60; // r13
  int v61; // r9d
  char *v62; // rax
  int v63; // eax
  unsigned int v64; // ebx
  int v65; // r12d
  __int64 v66; // r14
  char *v67; // rbx
  int v68; // esi
  int v69; // eax
  int v70; // ebx
  unsigned int v71; // r9d
  char v72; // al
  unsigned int v73; // r13d
  int v74; // r11d
  int v75; // r8d
  __int64 v76; // r9
  __int16 *v77; // rbx
  __int16 *v78; // rcx
  __int16 j; // ax
  int v80; // ecx
  unsigned __int64 v81; // rax
  unsigned int v82; // r11d
  unsigned int v83; // ecx
  __int64 v84; // rax
  int v85; // r8d
  unsigned int v86; // edi
  char *v87; // r13
  __int64 v88; // r9
  LPCWSTR v89; // rcx
  char *v90; // rax
  signed __int64 v91; // rcx
  int v92; // r8d
  unsigned int v93; // ebx
  unsigned int v94; // r9d
  unsigned int v95; // r8d
  char *v96; // r10
  __int64 v97; // rcx
  __int64 v98; // rax
  unsigned int v99; // r10d
  unsigned int v100; // ecx
  __int64 v101; // rdi
  unsigned int k; // r9d
  __int64 v103; // r8
  __int64 v104; // r8
  __int64 v105; // r8
  unsigned int v106; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v107; // [rsp+5Ch] [rbp-4Dh]
  unsigned int v108; // [rsp+60h] [rbp-49h]
  int v109; // [rsp+64h] [rbp-45h]
  unsigned int v110; // [rsp+68h] [rbp-41h] BYREF
  void *Base; // [rsp+70h] [rbp-39h]
  char *i; // [rsp+78h] [rbp-31h]
  struct SPPHRASEREPLACEMENT **v113; // [rsp+80h] [rbp-29h] BYREF
  char *v114; // [rsp+88h] [rbp-21h]
  char *v115; // [rsp+90h] [rbp-19h]
  __int64 v116; // [rsp+98h] [rbp-11h]
  int v117[18]; // [rsp+A0h] [rbp-9h] BYREF
  const unsigned __int16 *v120; // [rsp+108h] [rbp+5Fh]
  unsigned int v121; // [rsp+108h] [rbp+5Fh]

  v120 = a3;
  v17 = this;
  if ( !a3 )
    v120 = &a2[a5 + (unsigned __int64)a4];
  if ( a13 )
    *a13 = 0;
  if ( (!a10 || !a9) && (a6 & 3) != 0 )
    return 2147942487LL;
  v113 = 0;
  v19 = a8;
  v20 = (*(__int64 (__fastcall **)(CEngineLocaleHandler *, _QWORD, _QWORD, struct SPPHRASEREPLACEMENT ***))(*(_QWORD *)this + 280LL))(
          this,
          a9,
          a8,
          &v113);
  v109 = v20;
  if ( a9 > (*(unsigned int (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)v17 + 408LL))(v17) )
    a9 = (*(__int64 (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)v17 + 408LL))(v17);
  v22 = 0;
  if ( v20 < 0 )
  {
    v31 = 0;
    i = 0;
    v27 = 0;
    v44 = 0;
    Base = 0;
    goto LABEL_73;
  }
  v114 = (char *)a8;
  v23 = 40LL * a8;
  if ( !is_mul_ok(a8, 0x28u) )
    v23 = -1;
  v24 = __CFADD__(v23, 8);
  v25 = v23 + 8;
  if ( v24 )
    v25 = -1;
  v26 = (char *)CWinHeap::Alloc((CWinHeap *)&g_heap, v25, 0);
  i = v26;
  if ( v26 )
  {
    *(_QWORD *)v26 = a8;
    v27 = (const struct CSrTokenDL *)(v26 + 8);
    `eh vector constructor iterator'(
      v26 + 8,
      0x28u,
      a8,
      (void (*)(void *))CSrTokenDL::CSrTokenDL,
      (void (*)(void *))CSrTokenDL::~CSrTokenDL);
  }
  else
  {
    v27 = 0;
  }
  v114 = (char *)a8;
  v28 = 40LL * a8;
  if ( !is_mul_ok(a8, 0x28u) )
    v28 = -1;
  v24 = __CFADD__(v28, 8);
  v29 = v28 + 8;
  if ( v24 )
    v29 = -1;
  v30 = (char *)CWinHeap::Alloc((CWinHeap *)&g_heap, v29, 0);
  Base = v30;
  v22 = 0;
  if ( v30 )
  {
    *(_QWORD *)v30 = a8;
    v31 = v30 + 8;
    i = v30 + 8;
    `eh vector constructor iterator'(
      v30 + 8,
      0x28u,
      a8,
      (void (*)(void *))CSrTokenDL::CSrTokenDL,
      (void (*)(void *))CSrTokenDL::~CSrTokenDL);
    v22 = 0;
  }
  else
  {
    v31 = 0;
    i = 0;
  }
  if ( !v27 || !v31 )
  {
    v44 = v31;
    Base = v31;
    v20 = -2147024882;
    v109 = -2147024882;
    i = v31;
LABEL_73:
    v37 = 0;
    v108 = 0;
    v43 = 0;
    v107 = 0;
    goto LABEL_58;
  }
  v32 = 0;
  if ( a8 )
  {
    v33 = 0;
    do
    {
      v34 = (unsigned __int16 **)((char *)v27 + 40 * v33);
      pszDisplayText = a7[v33].pszDisplayText;
      *((_DWORD *)v27 + 10 * v33 + 9) = 0;
      CSrTokenDL::SetAnyViaCopy(
        (CSrTokenDL *)(5 * v33 + 1),
        (unsigned __int16 **)v27 + 5 * v33 + 1,
        pszDisplayText,
        1u,
        1u,
        (unsigned int *)v27 + 10 * v33 + 9);
      CSrTokenDL::SetAnyViaCopy(v36, v34, a7[v33].pszLexicalForm, 1u, 1u, 0);
      *((_DWORD *)v34 + 5) = v32;
      v34[3] = (unsigned __int16 *)1;
      *((_BYTE *)v34 + 16) = 0;
      ++v32;
      ++v33;
    }
    while ( v32 < a8 );
    v31 = i;
    v17 = this;
    v19 = a8;
  }
  v20 = CEngineLocaleHandler::EnsureWordParser(v17);
  v109 = v20;
  v22 = 0;
  v37 = 0;
  v108 = 0;
  if ( v20 < 0 || (a6 & 1) == 0 )
  {
    Base = v31;
    goto LABEL_48;
  }
  Base = v31;
  if ( !*((_QWORD *)v17 + 13) )
  {
LABEL_48:
    v40 = (struct CSrTokenDL *)v31;
    goto LABEL_49;
  }
  v38 = 0;
  v39 = v19 == 0;
  v40 = (struct CSrTokenDL *)v31;
  if ( !v39 )
  {
    v41 = a8;
    do
    {
      if ( v20 < 0 )
        break;
      LODWORD(v116) = v41 - v38;
      v106 = 0;
      v42 = *((_QWORD *)v17 + 13);
      v114 = 0;
      if ( v42 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, const struct CSrTokenDL *, _QWORD))(*(_QWORD *)v42 + 56LL))(
                v42,
                v27,
                v38);
        v109 = v20;
        v22 = 0;
      }
      if ( v20 >= 0 )
      {
        if ( *((_DWORD *)v17 + 37) != 1
          || (v20 = (*(__int64 (__fastcall **)(CEngineLocaleHandler *, const struct CSrTokenDL *, _QWORD))(*(_QWORD *)v17 + 384LL))(
                      v17,
                      v27,
                      v38),
              v109 = v20,
              v22 = 0,
              v20 >= 0) )
        {
          ++v38;
        }
      }
      v41 = a8;
    }
    while ( a8 > v38 );
    goto LABEL_50;
  }
  v108 = 0;
LABEL_49:
  i = v31;
LABEL_50:
  v107 = 0;
  if ( v20 >= 0 && (a6 & 2) != 0 )
  {
    v20 = CEngineLocaleHandler::EnsureShortcut(v17);
    v109 = v20;
    v22 = 0;
    if ( v20 >= 0 )
    {
      if ( *((_QWORD *)v17 + 14) )
      {
        v106 = 0;
        LODWORD(v21) = (_DWORD)v40;
        v115 = (char *)v40;
        if ( a8 )
        {
          v20 = CShortcutTF::Parse(*((CShortcutTF **)v17 + 14), v27, 0, a8, a9, v40, &v106);
          v109 = v20;
          v107 = v106;
          v22 = 0;
        }
      }
    }
    v43 = v107;
  }
  else
  {
    v43 = 0;
  }
  v44 = (char *)Base;
LABEL_58:
  v117[0] = 0;
  if ( v20 < 0 )
    goto LABEL_78;
  v45 = 0;
  v106 = 0;
  if ( (a6 & 2) != 0 && *((_DWORD *)v17 + 36) )
  {
    LODWORD(v115) = v43;
    qsort(v44, v43, 0x28u, CompToken);
    v20 = CEngineLocaleHandler::EnsureTransducer(v17);
    v109 = v20;
    v22 = 0;
    if ( v20 < 0 )
      goto LABEL_78;
    if ( *((_QWORD *)v17 + 16) )
    {
      v110 = 0;
      v46 = 0;
      v47 = v43;
      v21 = &v44[40 * v43];
      v114 = v21;
      if ( v43 )
      {
        v48 = v106;
        v49 = 0;
        v50 = v21;
        do
        {
          if ( v20 < 0 )
            break;
          v51 = 5LL * v49;
          v116 = v51;
          v52 = *(_DWORD *)&v31[40 * v49 + 20] - v46;
          if ( v52 )
          {
            v20 = ParseITN(
                    *((struct ITransducer **)v17 + 16),
                    v27,
                    v46,
                    v52,
                    a9,
                    (struct CSrTokenDL *)&v50[40 * v48],
                    &v110,
                    v17,
                    v117,
                    a17);
            v48 += v110;
            v51 = v116;
            v47 = (unsigned int)v115;
            v22 = 0;
          }
          v46 = *(_DWORD *)&v31[8 * v51 + 20] + *(_DWORD *)&v31[8 * v51 + 24];
          ++v49;
        }
        while ( v49 < v47 );
        v106 = v48;
        v109 = v20;
        v37 = v108;
        v44 = (char *)Base;
        v43 = v107;
        v21 = v114;
      }
      if ( v46 >= a8 )
      {
        v45 = v106;
      }
      else
      {
        v20 = ParseITN(
                *((struct ITransducer **)v17 + 16),
                v27,
                v46,
                a8 - v46,
                a9,
                (struct CSrTokenDL *)&v21[40 * v106],
                &v110,
                v17,
                v117,
                a17);
        v109 = v20;
        v45 = v110 + v106;
        v22 = 0;
      }
      if ( v20 < 0 )
        goto LABEL_78;
    }
    else
    {
      v45 = v106;
    }
  }
  v64 = v43 + v45 + v37;
  qsort(v44, v64, 0x28u, CompToken);
  v65 = a8 - 1;
  v44 = &v44[40 * a8 - 40];
  LODWORD(v21) = v64 - 1;
  v22 = 0;
  if ( (int)(v64 - 1) >= 0 )
  {
    v66 = (int)v21;
    v67 = (char *)Base;
    v68 = (int)v21;
    do
    {
      v114 = &v67[40 * v66];
      v69 = *((_DWORD *)v114 + 5) + *((_DWORD *)v114 + 6);
      if ( v69 <= (unsigned int)v65 && v69 <= v65 )
      {
        v70 = *((_DWORD *)v114 + 5) + *((_DWORD *)v114 + 6);
        do
        {
          CSrTokenDL::operator=((unsigned __int16 **)v44);
          v44 -= 40;
          --v65;
        }
        while ( v65 >= v70 );
        v67 = (char *)Base;
      }
      CSrTokenDL::operator=((unsigned __int16 **)v44);
      v44 -= 40;
      v65 = *((_DWORD *)v114 + 5) - 1;
      --v68;
      --v66;
    }
    while ( v68 >= 0 );
    v31 = i;
    v17 = this;
    v22 = 0;
  }
  if ( v65 >= 0 )
  {
    do
    {
      CSrTokenDL::operator=((unsigned __int16 **)v44);
      v44 -= 40;
      --v65;
    }
    while ( v65 >= 0 );
    v22 = 0;
    v108 = 0;
    goto LABEL_79;
  }
LABEL_78:
  v108 = 0;
  if ( v20 < 0 )
  {
LABEL_114:
    v57 = (CSrTokenDL *)Base;
    goto LABEL_115;
  }
LABEL_79:
  v53 = *((_QWORD *)v17 + 13);
  if ( !v53 )
    goto LABEL_114;
  *(_QWORD *)(v53 + 8) = *((_QWORD *)v17 + 16);
  v54 = *((_QWORD *)v17 + 13);
  v55 = (*(__int64 (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)v17 + 408LL))(v17);
  v56 = 0;
  if ( v55 )
    v56 = v55;
  *(_DWORD *)(v54 + 16) = v56;
  v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, unsigned __int8 *))(**((_QWORD **)v17 + 13) + 32LL))(
          *((_QWORD *)v17 + 13),
          a2,
          a4,
          a5,
          a14);
  v109 = v20;
  v22 = 0;
  v57 = (CSrTokenDL *)Base;
  if ( v20 >= 0 )
  {
    v58 = v44 + 40;
    v59 = (char *)Base;
    v114 = (char *)Base;
    v60 = 0;
    LODWORD(v21) = 0;
    v106 = 0;
    v61 = 0;
    v62 = &v31[40 * a8];
    for ( i = v62; ; v62 = i )
    {
      if ( v58 >= v62 && !(_DWORD)v21 )
      {
        if ( v20 >= 0 && a15 )
        {
          v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int8 *, unsigned int *))(**((_QWORD **)v17 + 13) + 40LL))(
                  *((_QWORD *)v17 + 13),
                  v120,
                  a15,
                  &v106);
          v109 = v20;
          v22 = 0;
        }
        break;
      }
      if ( v20 < 0 )
        break;
      v110 = 0;
      if ( !*((_DWORD *)v58 + 8) || (v63 = 1, v61) )
        v63 = 0;
      *((_DWORD *)v58 + 8) = v63;
      v20 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, unsigned int *, unsigned int *))(**((_QWORD **)v17 + 13)
                                                                                              + 48LL))(
              *((_QWORD *)v17 + 13),
              v58,
              v59,
              &v110,
              &v106);
      v109 = v20;
      v59 = v114;
      v61 = *((_DWORD *)v114 + 7);
      v22 = 0;
      LODWORD(v21) = v106;
      if ( v20 >= 0 )
      {
        if ( v106 )
        {
          if ( !v60 )
          {
            v60 = v58;
            v58 = (char *)v27 + 40 * *((unsigned int *)v58 + 5);
            continue;
          }
          if ( 0xCCCCCCCCCCCCCCCDuLL * ((v58 - (char *)v27) >> 3) - *((unsigned int *)v60 + 5) == *((_DWORD *)v60 + 6)
                                                                                                - 1 )
          {
            v58 = v60;
            v60 = 0;
            LODWORD(v21) = 0;
            v106 = 0;
          }
        }
        v59 = &v114[40 * v110];
        v114 = v59;
        v108 += v110;
        v58 += 40;
      }
    }
  }
LABEL_115:
  v71 = a8;
  if ( a8 )
  {
    v72 = (*(__int64 (__fastcall **)(CEngineLocaleHandler *))(*(_QWORD *)v17 + 416LL))(v17);
    v22 = 0;
    v73 = v108;
    if ( v72 )
    {
      v74 = 0;
      v75 = 1;
      if ( v108 )
      {
        v76 = 0;
        do
        {
          LODWORD(v21) = 5 * v76;
          v77 = *(__int16 **)&v31[40 * v76 + 8];
          v78 = v77;
          for ( j = *v77; j && (unsigned __int16)(j - 11904) <= 0xD17Du; j = *v78 )
            ++v78;
          if ( *v78 )
          {
            v80 = 0;
            v81 = -1;
            do
              ++v81;
            while ( v77[v81] );
            if ( v81 <= 1 )
            {
              if ( !v74 )
              {
                if ( v75 )
                  v31[40 * v76 + 16] = 2;
                else
                  v31[40 * v76 + 16] |= 2u;
              }
              v75 = 0;
            }
            else
            {
              v31[40 * v76 + 16] = 2;
              v75 = 1;
            }
          }
          else
          {
            v80 = 1;
            v75 = 1;
          }
          v74 = v80;
          LODWORD(v22) = (_DWORD)v22 + 1;
          ++v76;
        }
        while ( (unsigned int)v22 < v73 );
        v17 = this;
        v22 = 0;
      }
    }
    v71 = a8;
  }
  else
  {
    v73 = v108;
  }
  if ( v20 < 0 )
    goto LABEL_185;
  v82 = 0;
  LODWORD(v116) = 0;
  v83 = 0;
  v107 = 0;
  if ( !v73 )
    goto LABEL_181;
  v84 = v73 - 1;
  LODWORD(v21) = 5 * v84;
  v85 = *((_DWORD *)v57 + 10 * v84 + 5);
  v121 = 0;
  if ( v85 + *((_DWORD *)v57 + 10 * v84 + 6) < v71 )
    *((_DWORD *)v57 + 10 * v84 + 6) = v71 - v85;
  v114 = 0;
  v86 = 0;
  do
  {
    v87 = &v31[40 * (_QWORD)v22];
    v88 = *((unsigned int *)v87 + 5);
    if ( !v113 )
    {
LABEL_178:
      a7[v88].bDisplayAttributes = v87[16];
      goto LABEL_179;
    }
    if ( *((_DWORD *)v87 + 6) == 1 )
    {
      v89 = a7[v88].pszDisplayText;
      v90 = (char *)*((_QWORD *)v87 + 1);
      if ( v89 )
      {
        if ( v90 && *((_DWORD *)v87 + 9) == 1 )
        {
          v91 = (char *)v89 - v90;
          do
          {
            LODWORD(v21) = *(unsigned __int16 *)&v90[v91];
            v92 = *(unsigned __int16 *)v90 - (_DWORD)v21;
            if ( v92 )
              break;
            v90 += 2;
          }
          while ( (_DWORD)v21 );
          if ( !v92 )
            goto LABEL_178;
        }
      }
      else if ( !v90 )
      {
        goto LABEL_178;
      }
    }
    v93 = 0;
    LODWORD(v21) = 0;
    v106 = 0;
    v94 = 0;
    v110 = 0;
    v95 = a9;
    if ( a9 )
    {
      do
      {
        if ( v94 >= *((_DWORD *)v87 + 9) )
          break;
        v96 = 0;
        i = 0;
        v97 = *((_QWORD *)v87 + 1) + 2LL * (unsigned int)v21;
        if ( v97 )
        {
          v98 = -1;
          do
            ++v98;
          while ( *(_WORD *)(v97 + 2 * v98) );
          v115 = (char *)v98;
          Base = (void *)(2LL * (unsigned int)(v98 + 1));
          v96 = (char *)CoTaskMemAlloc((SIZE_T)Base);
          i = v96;
          if ( v96 )
          {
            memcpy_0(v96, (const void *)(*((_QWORD *)v87 + 1) + 2LL * v106), (size_t)Base);
            v96 = i;
          }
          v106 += (_DWORD)v115 + 1;
          v94 = v110;
          v82 = v116;
          v95 = a9;
        }
        if ( v93 && v82 )
        {
          v99 = v86 * (v94 + 1);
          while ( v93 < v99 && v93 < v95 )
          {
            v100 = v93 - v86 * v94;
            v101 = 0;
            for ( k = 0; k < v82; ++k )
            {
              v103 = v101;
              v113[v93][v103].pszReplacementText = v113[v100][v101].pszReplacementText;
              v113[v93][v103].ulFirstElement = v113[v100][v101].ulFirstElement;
              v113[v93][v103].ulCountOfElements = v113[v100][v101].ulCountOfElements;
              v113[v93][v103].bDisplayAttributes = v113[v100][v101++].bDisplayAttributes;
            }
            v17 = this;
            v94 = v110;
            v86 = v107;
            v115 = v31;
            v104 = v82;
            v113[v93][v104].pszReplacementText = (LPCWSTR)i;
            v113[v93][v104].ulFirstElement = *((_DWORD *)v57 + 10 * v121 + 5);
            v113[v93][v104].ulCountOfElements = *((_DWORD *)v57 + 10 * v121 + 6);
            v113[v93++][v104].bDisplayAttributes = *((_BYTE *)v57 + 40 * v121 + 16);
            v31 = v115;
            v95 = a9;
          }
        }
        else
        {
          while ( v93 <= v94 || v93 < v86 )
          {
            v105 = v82;
            v113[v93][v105].pszReplacementText = (LPCWSTR)v96;
            v113[v93][v105].ulFirstElement = *((_DWORD *)v57 + 10 * v121 + 5);
            v113[v93][v105].ulCountOfElements = *((_DWORD *)v57 + 10 * v121 + 6);
            v113[v93++][v105].bDisplayAttributes = *((_BYTE *)v57 + 40 * v121 + 16);
            v94 = v110;
          }
          v17 = this;
          v95 = a9;
        }
        v110 = ++v94;
        LODWORD(v21) = v106;
      }
      while ( v93 < v95 );
      v22 = v114;
    }
    LODWORD(v116) = ++v82;
    v86 = v93;
    v107 = v93;
LABEL_179:
    ++v121;
    v22 = (_DWORD *)((char *)v22 + 1);
    v114 = (char *)v22;
    v73 = v108;
  }
  while ( v121 < v108 );
  v20 = v109;
  v83 = v107;
LABEL_181:
  if ( a12 )
    *a12 = v82;
  if ( a11 )
    *a11 = v83;
LABEL_185:
  if ( a13 )
    *a13 = v73;
  if ( a16 )
    *a16 = v117[0];
  if ( v27 )
    CSrTokenDL::`vector deleting destructor'(v27, (unsigned int)v21);
  if ( v57 )
    CSrTokenDL::`vector deleting destructor'(v57, (unsigned int)v21);
  if ( v20 < 0 )
  {
    if ( a9 )
      (*(void (__fastcall **)(CEngineLocaleHandler *, struct SPPHRASEREPLACEMENT **, _QWORD, _QWORD))(*(_QWORD *)v17 + 128LL))(
        v17,
        v113,
        a8,
        a9);
    v113 = 0;
  }
  if ( a10 )
    *a10 = v113;
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1800cf4d0  mov     rax, rsp
0x1800cf4d3  mov     [rax+20h], r9d
0x1800cf4d7  mov     [rax+18h], r8
0x1800cf4db  mov     [rax+10h], rdx
0x1800cf4df  mov     [rax+8], rcx
0x1800cf4e3  push    rbp
0x1800cf4e4  push    rbx
0x1800cf4e5  push    rsi
0x1800cf4e6  push    rdi
0x1800cf4e7  push    r12
0x1800cf4e9  push    r13
0x1800cf4eb  push    r14
0x1800cf4ed  push    r15
0x1800cf4ef  lea     rbp, [rax-47h]
0x1800cf4f3  sub     rsp, 0A8h
0x1800cf4fa  mov     r14, rcx
0x1800cf4fd  xor     ecx, ecx
0x1800cf4ff  test    r8, r8
0x1800cf502  jnz     short loc_1800CF515
0x1800cf504  mov     r8d, r9d
0x1800cf507  mov     eax, [rbp+3Fh+arg_20]
0x1800cf50a  add     r8, rax
0x1800cf50d  lea     rax, [rdx+r8*2]
0x1800cf511  mov     [rbp+3Fh+arg_10], rax
0x1800cf515  mov     rax, [rbp+3Fh+arg_60]
0x1800cf51c  test    rax, rax
0x1800cf51f  jz      short loc_1800CF523
0x1800cf521  mov     [rax], ecx
0x1800cf523  mov     ebx, [rbp+3Fh+arg_40]
0x1800cf529  cmp     [rbp+3Fh+arg_48], rcx
0x1800cf530  jz      short loc_1800CF536
0x1800cf532  test    ebx, ebx
0x1800cf534  jnz     short loc_1800CF546
0x1800cf536  test    [rbp+3Fh+arg_28], 3
0x1800cf53a  jz      short loc_1800CF546
0x1800cf53c  mov     eax, 80070057h
0x1800cf541  jmp     loc_1800D033B
0x1800cf546  mov     [rbp+3Fh+var_68], rcx
0x1800cf54a  mov     rax, [r14]
0x1800cf54d  lea     r9, [rbp+3Fh+var_68]
0x1800cf551  mov     r12d, [rbp+3Fh+arg_38]
0x1800cf558  mov     r8d, r12d
0x1800cf55b  mov     edx, ebx
0x1800cf55d  mov     rcx, r14
0x1800cf560  mov     rax, [rax+118h]
0x1800cf567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf56c  mov     edi, eax
0x1800cf56e  mov     [rbp+3Fh+var_84], eax
0x1800cf571  mov     rax, [r14]
0x1800cf574  mov     rcx, r14
0x1800cf577  mov     rax, [rax+198h]
0x1800cf57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf583  cmp     ebx, eax
0x1800cf585  jbe     short loc_1800CF59F
0x1800cf587  mov     rax, [r14]
0x1800cf58a  mov     rcx, r14
0x1800cf58d  mov     rax, [rax+198h]
0x1800cf594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf599  mov     [rbp+3Fh+arg_40], eax
0x1800cf59f  mov     r13d, 28h ; '('
0x1800cf5a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800cf5a9  xor     r10d, r10d
0x1800cf5ac  test    edi, edi
0x1800cf5ae  js      loc_1800CFB63
0x1800cf5b4  mov     rbx, r12
0x1800cf5b7  mov     [rbp+3Fh+var_60], rbx
0x1800cf5bb  mov     eax, r13d
0x1800cf5be  mul     r12
0x1800cf5c1  cmovb   rax, rsi
0x1800cf5c5  add     rax, 8
0x1800cf5c9  cmovb   rax, rsi
0x1800cf5cd  xor     r8d, r8d; bool
0x1800cf5d0  mov     rdx, rax; unsigned __int64
0x1800cf5d3  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800cf5da  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800cf5df  mov     [rbp+3Fh+var_70], rax
0x1800cf5e3  lea     rdi, ??1CSrTokenDL@@QEAA@XZ; CSrTokenDL::~CSrTokenDL(void)
0x1800cf5ea  xor     edx, edx
0x1800cf5ec  test    rax, rax
0x1800cf5ef  jz      short loc_1800CF614
0x1800cf5f1  mov     [rax], rbx
0x1800cf5f4  lea     r15, [rax+8]
0x1800cf5f8  mov     [rsp+0E0h+var_C0], rdi; void (*)(void *)
0x1800cf5fd  lea     r9, ??0CSrTokenDL@@QEAA@XZ; void (*)(void *)
0x1800cf604  mov     r8, rbx; unsigned __int64
0x1800cf607  mov     edx, r13d; unsigned __int64
0x1800cf60a  mov     rcx, r15; void *
0x1800cf60d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800cf612  jmp     short loc_1800CF617
0x1800cf614  mov     r15, rdx
0x1800cf617  mov     [rbp+3Fh+var_60], rbx
0x1800cf61b  mov     rax, r13
0x1800cf61e  mul     rbx
0x1800cf621  cmovb   rax, rsi
0x1800cf625  add     rax, 8
0x1800cf629  cmovb   rax, rsi
0x1800cf62d  xor     r8d, r8d; bool
0x1800cf630  mov     rdx, rax; unsigned __int64
0x1800cf633  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800cf63a  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800cf63f  mov     [rbp+3Fh+Base], rax
0x1800cf643  xor     r10d, r10d
0x1800cf646  test    rax, rax
0x1800cf649  jz      short loc_1800CF675
0x1800cf64b  mov     [rax], rbx
0x1800cf64e  lea     rsi, [rax+8]
0x1800cf652  mov     [rbp+3Fh+var_70], rsi
0x1800cf656  mov     [rsp+0E0h+var_C0], rdi; void (*)(void *)
0x1800cf65b  lea     r9, ??0CSrTokenDL@@QEAA@XZ; void (*)(void *)
0x1800cf662  mov     r8, rbx; unsigned __int64
0x1800cf665  mov     rdx, r13; unsigned __int64
0x1800cf668  mov     rcx, rsi; void *
0x1800cf66b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800cf670  xor     r10d, r10d
0x1800cf673  jmp     short loc_1800CF67C
0x1800cf675  mov     rsi, r10
0x1800cf678  mov     [rbp+3Fh+var_70], r10
0x1800cf67c  test    r15, r15
0x1800cf67f  jz      loc_1800CFB3E
0x1800cf685  test    rsi, rsi
0x1800cf688  jz      loc_1800CFB3E
0x1800cf68e  mov     r13d, r10d
0x1800cf691  test    r12d, r12d
0x1800cf694  jz      loc_1800CF734
0x1800cf69a  mov     r12, r10
0x1800cf69d  mov     r14d, [rbp+3Fh+arg_38]
0x1800cf6a4  mov     rsi, [rbp+3Fh+arg_30]
0x1800cf6a8  lea     rcx, [r12+r12*4]
0x1800cf6ac  lea     rdi, [r15+rcx*8]
0x1800cf6b0  imul    rbx, r12, 38h ; '8'
0x1800cf6b4  mov     r8, [rbx+rsi+18h]; unsigned __int16 *
0x1800cf6b9  lea     rax, ds:24h[rcx*8]
0x1800cf6c1  add     rax, r15
0x1800cf6c4  mov     [rax], r10d
0x1800cf6c7  lea     rcx, [rcx+1]; this
0x1800cf6cb  lea     rdx, [r15+rcx*8]; unsigned __int16 **
0x1800cf6cf  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x1800cf6d4  mov     dword ptr [rsp+0E0h+var_C0], 1; unsigned int
0x1800cf6dc  mov     r9d, 1; unsigned int
0x1800cf6e2  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800cf6e7  xor     edx, edx
0x1800cf6e9  mov     [rsp+0E0h+var_B8], rdx; unsigned int *
0x1800cf6ee  mov     dword ptr [rsp+0E0h+var_C0], 1; unsigned int
0x1800cf6f6  lea     r9d, [rdx+1]; unsigned int
0x1800cf6fa  mov     r8, [rbx+rsi+20h]; unsigned __int16 *
0x1800cf6ff  mov     rdx, rdi; unsigned __int16 **
0x1800cf702  call    ?SetAnyViaCopy@CSrTokenDL@@QEAAJPEAPEAGPEBGKKPEAK@Z; CSrTokenDL::SetAnyViaCopy(ushort * *,ushort const *,ulong,ulong,ulong *)
0x1800cf707  mov     [rdi+14h], r13d
0x1800cf70b  mov     qword ptr [rdi+18h], 1
0x1800cf713  xor     r10d, r10d
0x1800cf716  mov     [rdi+10h], r10b
0x1800cf71a  inc     r13d
0x1800cf71d  inc     r12
0x1800cf720  cmp     r13d, r14d
0x1800cf723  jb      short loc_1800CF6A8
0x1800cf725  mov     rsi, [rbp+3Fh+var_70]
0x1800cf729  mov     r14, [rbp+3Fh+arg_0]
0x1800cf72d  mov     r12d, [rbp+3Fh+arg_38]
0x1800cf734  mov     rcx, r14; this
0x1800cf737  call    ?EnsureWordParser@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureWordParser(void)
0x1800cf73c  mov     edi, eax
0x1800cf73e  mov     [rbp+3Fh+var_84], eax
0x1800cf741  xor     r10d, r10d
0x1800cf744  mov     ebx, r10d
0x1800cf747  mov     [rbp+3Fh+var_88], ebx
0x1800cf74a  test    eax, eax
0x1800cf74c  js      loc_1800CF863
0x1800cf752  test    [rbp+3Fh+arg_28], 1
0x1800cf756  jz      loc_1800CF863
0x1800cf75c  mov     [rbp+3Fh+Base], rsi
0x1800cf760  cmp     [r14+68h], r10
0x1800cf764  jz      loc_1800CF867
0x1800cf76a  mov     r13d, r10d
0x1800cf76d  test    r12d, r12d
0x1800cf770  mov     r12, rsi
0x1800cf773  jz      loc_1800CF85E
0x1800cf779  mov     eax, [rbp+3Fh+arg_38]
0x1800cf77f  test    edi, edi
0x1800cf781  js      loc_1800CF86E
0x1800cf787  mov     r9d, eax
0x1800cf78a  sub     r9d, r13d
0x1800cf78d  mov     dword ptr [rbp+3Fh+var_50], r9d
0x1800cf791  mov     eax, r10d
0x1800cf794  mov     [rbp+3Fh+var_90], eax
0x1800cf797  mov     rcx, [r14+68h]
0x1800cf79b  mov     r8d, ebx
0x1800cf79e  mov     [rbp+3Fh+var_60], r8
0x1800cf7a2  test    rcx, rcx
0x1800cf7a5  jz      short loc_1800CF7F1
0x1800cf7a7  mov     rdx, [rcx]
0x1800cf7aa  lea     rax, [r8+r8*4]
0x1800cf7ae  lea     r8, [rsi+rax*8]
0x1800cf7b2  mov     rax, [rdx+38h]
0x1800cf7b6  mov     edx, [r14+98h]
0x1800cf7bd  mov     dword ptr [rsp+0E0h+var_B0], edx
0x1800cf7c1  lea     rdx, [rbp+3Fh+var_90]
0x1800cf7c5  mov     [rsp+0E0h+var_B8], rdx
0x1800cf7ca  mov     [rsp+0E0h+var_C0], r8
0x1800cf7cf  mov     r8d, r13d
0x1800cf7d2  mov     rdx, r15
0x1800cf7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf7da  mov     edi, eax
0x1800cf7dc  mov     [rbp+3Fh+var_84], eax
0x1800cf7df  mov     eax, [rbp+3Fh+var_90]
0x1800cf7e2  xor     r10d, r10d
0x1800cf7e5  test    eax, eax
0x1800cf7e7  jnz     short loc_1800CF838
0x1800cf7e9  mov     r8, [rbp+3Fh+var_60]
0x1800cf7ed  mov     r9d, dword ptr [rbp+3Fh+var_50]
0x1800cf7f1  test    edi, edi
0x1800cf7f3  js      short loc_1800CF84D
0x1800cf7f5  cmp     dword ptr [r14+94h], 1
0x1800cf7fd  jnz     short loc_1800CF83C
0x1800cf7ff  mov     rcx, [r14]
0x1800cf802  lea     rax, [r8+r8*4]
0x1800cf806  lea     rdx, [rsi+rax*8]
0x1800cf80a  mov     rax, [rcx+180h]
0x1800cf811  lea     rcx, [rbp+3Fh+var_90]
0x1800cf815  mov     [rsp+0E0h+var_B8], rcx
0x1800cf81a  mov     [rsp+0E0h+var_C0], rdx
0x1800cf81f  mov     r8d, r13d
0x1800cf822  mov     rdx, r15
0x1800cf825  mov     rcx, r14
0x1800cf828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf82d  mov     edi, eax
0x1800cf82f  mov     [rbp+3Fh+var_84], eax
0x1800cf832  mov     eax, [rbp+3Fh+var_90]
0x1800cf835  xor     r10d, r10d
0x1800cf838  test    edi, edi
0x1800cf83a  js      short loc_1800CF84D
0x1800cf83c  test    eax, eax
0x1800cf83e  jz      short loc_1800CF84A
0x1800cf840  inc     ebx
0x1800cf842  mov     [rbp+3Fh+var_88], ebx
0x1800cf845  add     r13d, eax
0x1800cf848  jmp     short loc_1800CF84D
0x1800cf84a  inc     r13d
0x1800cf84d  mov     eax, [rbp+3Fh+arg_38]
0x1800cf853  cmp     eax, r13d
0x1800cf856  ja      loc_1800CF77F
0x1800cf85c  jmp     short loc_1800CF86E
0x1800cf85e  mov     [rbp+3Fh+var_88], ebx
0x1800cf861  jmp     short loc_1800CF86A
0x1800cf863  mov     [rbp+3Fh+Base], rsi
0x1800cf867  mov     r12, rsi
0x1800cf86a  mov     [rbp+3Fh+var_70], rsi
0x1800cf86e  mov     r13d, r10d
0x1800cf871  mov     [rbp+3Fh+var_8C], r10d
0x1800cf875  test    edi, edi
0x1800cf877  js      loc_1800CFB76
0x1800cf87d  test    [rbp+3Fh+arg_28], 2
0x1800cf881  jz      loc_1800CFB76
0x1800cf887  mov     rcx, r14; this
0x1800cf88a  call    ?EnsureShortcut@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureShortcut(void)
0x1800cf88f  mov     edi, eax
0x1800cf891  mov     [rbp+3Fh+var_84], eax
0x1800cf894  xor     r10d, r10d
0x1800cf897  test    eax, eax
0x1800cf899  js      loc_1800CF985
0x1800cf89f  cmp     [r14+70h], r10
0x1800cf8a3  jz      loc_1800CF985
0x1800cf8a9  mov     [rbp+3Fh+var_90], r10d
0x1800cf8ad  mov     r8d, r10d; unsigned int
0x1800cf8b0  mov     eax, ebx
0x1800cf8b2  lea     rcx, [rax+rax*4]
0x1800cf8b6  lea     rdx, [r12+rcx*8]
0x1800cf8ba  mov     [rbp+3Fh+var_58], rdx
0x1800cf8be  mov     r12d, r10d
0x1800cf8c1  test    ebx, ebx
0x1800cf8c3  jz      short loc_1800CF937
0x1800cf8c5  test    edi, edi
0x1800cf8c7  js      short loc_1800CF930
0x1800cf8c9  mov     eax, r12d
0x1800cf8cc  lea     rax, [rax+rax*4]
0x1800cf8d0  mov     [rbp+3Fh+var_60], rax
0x1800cf8d4  mov     r9d, [rsi+rax*8+14h]
0x1800cf8d9  sub     r9d, r8d; unsigned int
0x1800cf8dc  jz      short loc_1800CF91E
0x1800cf8de  mov     eax, r13d
0x1800cf8e1  lea     rcx, [rax+rax*4]
0x1800cf8e5  lea     rax, [rdx+rcx*8]
0x1800cf8e9  lea     rcx, [rbp+3Fh+var_90]
0x1800cf8ed  mov     [rsp+0E0h+var_B0], rcx; unsigned int *
0x1800cf8f2  mov     [rsp+0E0h+var_B8], rax; struct CSrTokenDL *
0x1800cf8f7  mov     eax, [rbp+3Fh+arg_40]
0x1800cf8fd  mov     dword ptr [rsp+0E0h+var_C0], eax; unsigned int
0x1800cf901  mov     rdx, r15; struct CSrTokenDL *
0x1800cf904  mov     rcx, [r14+70h]; this
0x1800cf908  call    ?Parse@CShortcutTF@@QEAAJPEBVCSrTokenDL@@KKKPEAV2@PEAK@Z; CShortcutTF::Parse(CSrTokenDL const *,ulong,ulong,ulong,CSrTokenDL *,ulong *)
0x1800cf90d  mov     edi, eax
0x1800cf90f  add     r13d, [rbp+3Fh+var_90]
0x1800cf913  mov     rax, [rbp+3Fh+var_60]
0x1800cf917  mov     rdx, [rbp+3Fh+var_58]
0x1800cf91b  xor     r10d, r10d
0x1800cf91e  mov     r8d, [rsi+rax*8+18h]
0x1800cf923  add     r8d, [rsi+rax*8+14h]; unsigned int
0x1800cf928  inc     r12d
0x1800cf92b  cmp     r12d, ebx
0x1800cf92e  jb      short loc_1800CF8C5
0x1800cf930  mov     [rbp+3Fh+var_8C], r13d
  ... truncated ...
```
