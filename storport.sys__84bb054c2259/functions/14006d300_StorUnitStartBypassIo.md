# StorUnitStartBypassIo

- ea: `0x14006d300`
- end: `0x14006e79c`
- name: `StorUnitStartBypassIo`
- size: `5276`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400173f0`
- `0x140017b80`
- `0x14006d1c0`
- `0x14006d298`
- `0x14006d300`
- `0x14006f610`
- `0x1400848c4`
- `0x1400a6f90`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d39a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d69f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d9a4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006daf2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006dc62`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006df80`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e160`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e3ae`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e5ad`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e6fe`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d39a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d69f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006d9a4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006daf2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006dc62`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006df80`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e160`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e3ae`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e5ad`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14006e6fe`
- `ntoskrnl!IofCompleteRequest` at `0x14006d64b`
- `ntoskrnl!IofCompleteRequest` at `0x14006d95c`
- `ntoskrnl!IofCompleteRequest` at `0x14006df10`
- `ntoskrnl!IofCompleteRequest` at `0x14006d64b`
- `ntoskrnl!IofCompleteRequest` at `0x14006d95c`
- `ntoskrnl!IofCompleteRequest` at `0x14006df10`

## pseudocode

```c
__int64 __fastcall StorUnitStartBypassIo(__int64 a1, __int64 a2)
{
  int *v2; // r9
  int v5; // ebx
  int v6; // ecx
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int8 *v9; // rdx
  int v10; // eax
  int *v11; // rax
  __int64 *v12; // rdx
  __int64 v13; // rdx
  char v14; // si
  unsigned int v15; // r12d
  unsigned __int8 v16; // r10
  char *v17; // r11
  char v18; // r13
  _BYTE *v19; // r9
  unsigned int v20; // r15d
  unsigned __int64 v21; // r14
  __int64 v22; // r8
  int v23; // ecx
  char v24; // cl
  char v25; // r14
  char v26; // r11
  _BYTE *v27; // rax
  char v28; // r8
  char *v29; // r8
  unsigned int v30; // eax
  bool v31; // zf
  unsigned int v32; // ebx
  int *v33; // rsi
  __int64 v34; // r14
  unsigned __int64 v35; // rcx
  unsigned __int8 *v36; // rdx
  int v37; // eax
  int *v38; // rax
  __int64 *v39; // rdx
  __int64 v40; // rdx
  char v41; // si
  int v42; // eax
  unsigned int v43; // r12d
  unsigned __int8 v44; // r11
  char *v45; // r10
  _BYTE *v46; // r9
  unsigned int v47; // r15d
  char v48; // r13
  unsigned __int64 v49; // r14
  __int64 v50; // r8
  int v51; // ecx
  char v52; // r15
  char v53; // cl
  char v54; // r14
  char v55; // r8
  char v56; // r10
  _BYTE *v57; // rax
  char *v58; // r8
  unsigned int v59; // eax
  __int64 v60; // r14
  unsigned int v61; // r12d
  unsigned int v62; // r15d
  char v63; // r13
  unsigned __int64 v64; // r14
  int v65; // ecx
  char v66; // cl
  __int64 v67; // rax
  unsigned int v68; // r12d
  unsigned int v69; // r15d
  char v70; // r13
  unsigned __int64 v71; // r14
  int v72; // ecx
  _DWORD *v73; // rax
  __int64 v74; // rax
  unsigned __int64 v75; // rcx
  __int64 v76; // rdx
  int *v77; // rax
  __int64 *v78; // rdx
  __int64 v79; // rdx
  unsigned int v80; // r12d
  unsigned __int8 v81; // r11
  char *v82; // r10
  _BYTE *v83; // r9
  unsigned int v84; // r15d
  char v85; // r13
  unsigned __int64 v86; // r14
  __int64 v87; // r8
  int v88; // ecx
  char v89; // r15
  char v90; // cl
  char v91; // r14
  char v92; // r10
  _BYTE *v93; // rax
  char v94; // r8
  char *v95; // r8
  unsigned int v96; // eax
  __int64 v97; // r15
  int v98; // r8d
  unsigned int v99; // r12d
  unsigned int v100; // r15d
  char v101; // r13
  unsigned __int64 v102; // r14
  __int64 v103; // r8
  int v104; // ecx
  __int64 v105; // rcx
  __int64 v106; // rax
  __int64 v107; // rdx
  int v108; // eax
  unsigned int v109; // r12d
  unsigned __int8 v110; // r11
  char *v111; // r10
  _BYTE *v112; // r9
  unsigned int v113; // r15d
  char v114; // r13
  unsigned __int64 v115; // r14
  __int64 v116; // r8
  int v117; // ecx
  char v118; // r15
  char v119; // cl
  char v120; // r14
  char v121; // r10
  _BYTE *v122; // rax
  char v123; // r8
  char *v124; // r8
  unsigned int v125; // eax
  unsigned int v126; // r12d
  unsigned int v127; // r15d
  char v128; // r13
  unsigned __int64 v129; // r14
  int v130; // ecx
  _BYTE *v131; // r8
  unsigned int v132; // r11d
  unsigned int v133; // r10d
  __int64 v134; // rcx
  unsigned __int64 v135; // r9
  __int64 v136; // rdx
  int v137; // ecx
  int v138; // ecx
  __int64 v139; // r8
  unsigned __int64 v140; // rcx
  unsigned int v141; // r12d
  unsigned int v142; // r15d
  char v143; // r13
  unsigned __int64 v144; // r14
  int v145; // ecx
  __int64 v146; // rdx
  __int64 v147; // rax
  char v149; // [rsp+60h] [rbp-29h]
  char v150; // [rsp+60h] [rbp-29h]
  char v151; // [rsp+60h] [rbp-29h]
  char v152; // [rsp+60h] [rbp-29h]
  char v153; // [rsp+60h] [rbp-29h]
  int *v154; // [rsp+68h] [rbp-21h]
  int v155; // [rsp+70h] [rbp-19h]
  int v156; // [rsp+74h] [rbp-15h]
  __int128 v158; // [rsp+80h] [rbp-9h] BYREF
  __int128 v159; // [rsp+90h] [rbp+7h] BYREF

  v2 = *(int **)(a1 + 64);
  v154 = v2;
  LOBYTE(v5) = 0;
  v6 = *v2;
  *(_QWORD *)(a2 + 184) -= 72LL;
  --*(_BYTE *)(a2 + 67);
  v7 = *(_QWORD *)(a2 + 184);
  v159 = 0;
  *(_QWORD *)(v7 + 40) = a1;
  if ( v6 != 1431193940 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741823;
    if ( v31 )
      goto LABEL_66;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v9 = *(unsigned __int8 **)(a2 + 184);
    if ( *v9 != 14 )
    {
      v10 = *v9 - 15;
      if ( *v9 != 15 )
      {
LABEL_5:
        if ( v10 != 12 )
          goto LABEL_66;
        if ( v9[1] == 7 && !*((_DWORD *)v9 + 2) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v11 = *(int **)(a2 + 56);
            if ( v11 )
              v5 = *v11;
            McTemplateK0pqd_EtwWriteTransfer(v8, (_DWORD)v9, (unsigned int)&v158, a2, v5, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_66;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_66;
        v12 = EventPnpRequestComplete;
LABEL_65:
        McTemplateK0pd_EtwWriteTransfer(v8, v12, &v158, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_66;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_66;
      v13 = *((_QWORD *)v9 + 1);
      v14 = 1;
      if ( *(_BYTE *)(v13 + 2) == 40 )
      {
        if ( *(_DWORD *)(v13 + 20) )
          goto LABEL_66;
        v15 = *(_DWORD *)(v13 + 56);
        if ( !v15 )
          goto LABEL_66;
        v16 = 0;
        v149 = 0;
        v17 = 0;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        while ( 1 )
        {
          v8 = *(unsigned int *)(v13 + 4LL * v20 + 120);
          if ( (unsigned int)v8 >= 0x80 )
          {
            v21 = *(unsigned int *)(v13 + 16);
            if ( (unsigned int)v8 < (unsigned int)v21 )
            {
              v22 = (unsigned int)v8;
              v23 = *(_DWORD *)(v8 + v13) - 64;
              if ( v23 )
              {
                LODWORD(v8) = v23 - 1;
                if ( (_DWORD)v8 )
                {
                  if ( (_DWORD)v8 == 1 )
                  {
                    LODWORD(v8) = v22 + 40;
                    if ( v22 + 40 <= v21 )
                    {
                      if ( *(_DWORD *)(v22 + v13 + 12) )
                        v17 = (char *)(v22 + v13 + 32);
                      v19 = *(_BYTE **)(v22 + v13 + 24);
                      goto LABEL_39;
                    }
                  }
                }
                else
                {
                  LODWORD(v8) = v22 + 56;
                  if ( v22 + 56 <= v21 )
                  {
                    v149 = 1;
                    if ( *(_BYTE *)(v22 + v13 + 10) )
                      v17 = (char *)(v22 + v13 + 24);
                    v18 = *(_BYTE *)(v22 + v13 + 8);
                    v19 = *(_BYTE **)(v22 + v13 + 16);
                    v16 = *(_BYTE *)(v22 + v13 + 9);
                  }
                }
              }
              else
              {
                LODWORD(v8) = v22 + 40;
                if ( v22 + 40 <= v21 )
                {
                  if ( *(_BYTE *)(v22 + v13 + 10) )
                    v17 = (char *)(v22 + v13 + 24);
                  v19 = *(_BYTE **)(v22 + v13 + 16);
LABEL_39:
                  v16 = *(_BYTE *)(v22 + v13 + 9);
                  v18 = *(_BYTE *)(v22 + v13 + 8);
LABEL_40:
                  if ( v17 )
                  {
                    v24 = *v17;
                    goto LABEL_43;
                  }
                  goto LABEL_66;
                }
              }
              if ( v149 )
                goto LABEL_40;
            }
          }
          if ( ++v20 >= v15 )
            goto LABEL_40;
        }
      }
      v24 = *(_BYTE *)(v13 + 72);
      v19 = *(_BYTE **)(v13 + 32);
      v16 = *(_BYTE *)(v13 + 11);
      v18 = *(_BYTE *)(v13 + 4);
      if ( *(_BYTE *)(v13 + 2) )
        goto LABEL_66;
LABEL_43:
      LOBYTE(v8) = v24 - 8;
      if ( (v8 & 0x5D) == 0 )
      {
        v25 = *(_BYTE *)(v13 + 3);
        if ( v25 == 1 || !v19 || !v16 )
          goto LABEL_60;
        LOBYTE(v13) = 0;
        v8 = (unsigned __int64)&v19[v16];
        v26 = 0;
        v27 = v19 + 8;
        v28 = 0;
        if ( (unsigned __int8)((*v19 & 0x7F) - 114) <= 1u )
        {
          if ( (unsigned __int64)v27 <= v8 )
          {
            v26 = v19[2];
            LOBYTE(v13) = v19[1] & 0xF;
            v28 = v19[3];
            goto LABEL_59;
          }
        }
        else if ( (unsigned __int64)v27 <= v8 )
        {
          v29 = v19 + 13;
          LOBYTE(v13) = v19[2] & 0xF;
          v30 = v16;
          if ( (unsigned int)(unsigned __int8)v19[7] + 8 <= v16 )
            v30 = (unsigned __int8)v19[7] + 8;
          v8 = (unsigned __int64)&v19[v30];
          if ( (unsigned __int64)v29 <= v8 )
            v26 = v19[12];
          if ( (unsigned __int64)(v19 + 14) > v8 )
            v28 = 0;
          else
            v28 = *v29;
LABEL_59:
          if ( v14 )
          {
LABEL_61:
            McTemplateK0pduuuuup_EtwWriteTransfer(
              v8,
              v13,
              (unsigned int)&v158,
              a2,
              *(_DWORD *)(a2 + 48),
              v25,
              v18,
              v13,
              v26,
              v28,
              a2);
            goto LABEL_66;
          }
LABEL_60:
          LOBYTE(v13) = 0;
          v26 = 0;
          v28 = 0;
          goto LABEL_61;
        }
        v14 = 0;
        goto LABEL_59;
      }
LABEL_66:
      IofCompleteRequest((PIRP)a2, 0);
      v32 = -1073741823;
      goto LABEL_67;
    }
    goto LABEL_62;
  }
  v34 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v34 != 15 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v31 )
      goto LABEL_132;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v36 = *(unsigned __int8 **)(a2 + 184);
    if ( *v36 != 14 )
    {
      v37 = *v36 - 15;
      if ( *v36 != 15 )
      {
LABEL_72:
        if ( v37 != 12 )
          goto LABEL_132;
        if ( v36[1] == 7 && !*((_DWORD *)v36 + 2) )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v38 = *(int **)(a2 + 56);
            if ( v38 )
              v5 = *v38;
            McTemplateK0pqd_EtwWriteTransfer(v35, (_DWORD)v36, (unsigned int)&v158, a2, v5, *(_DWORD *)(a2 + 48));
          }
          goto LABEL_132;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_132;
        v39 = EventPnpRequestComplete;
LABEL_131:
        McTemplateK0pd_EtwWriteTransfer(v35, v39, &v158, a2, *(_DWORD *)(a2 + 48));
        goto LABEL_132;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_132;
      v40 = *((_QWORD *)v36 + 1);
      v41 = 1;
      v42 = *(unsigned __int8 *)(v40 + 2);
      if ( (_BYTE)v42 == 40 )
      {
        if ( !*(_DWORD *)(v40 + 20) )
        {
          v43 = *(_DWORD *)(v40 + 56);
          if ( v43 )
          {
            v44 = 0;
            v150 = 0;
            v45 = 0;
            v46 = 0;
            v47 = 0;
            v48 = 0;
            while ( 1 )
            {
              v35 = *(unsigned int *)(v40 + 4LL * v47 + 120);
              if ( (unsigned int)v35 >= 0x80 )
              {
                v49 = *(unsigned int *)(v40 + 16);
                if ( (unsigned int)v35 < (unsigned int)v49 )
                {
                  v50 = (unsigned int)v35;
                  v51 = *(_DWORD *)(v40 + v35) - 64;
                  if ( v51 )
                  {
                    LODWORD(v35) = v51 - 1;
                    if ( (_DWORD)v35 )
                    {
                      if ( (_DWORD)v35 == 1 )
                      {
                        LODWORD(v35) = v50 + 40;
                        if ( v50 + 40 <= v49 )
                          goto LABEL_92;
                      }
                    }
                    else
                    {
                      LODWORD(v35) = v50 + 56;
                      if ( v50 + 56 <= v49 )
                      {
                        v48 = 1;
                        if ( *(_BYTE *)(v40 + v50 + 10) )
                          v45 = (char *)(v50 + v40 + 24);
                        v46 = *(_BYTE **)(v40 + v50 + 16);
                        v44 = *(_BYTE *)(v40 + v50 + 9);
                        v150 = *(_BYTE *)(v40 + v50 + 8);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v35) = v50 + 40;
                    if ( v50 + 40 <= v49 )
                      goto LABEL_106;
                  }
                  if ( v48 )
                    goto LABEL_103;
                }
              }
              if ( ++v47 >= v43 )
                goto LABEL_103;
            }
          }
        }
        goto LABEL_132;
      }
      goto LABEL_109;
    }
LABEL_129:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_132;
    v39 = EventNonReadWriteRequestComplete;
    goto LABEL_131;
  }
  v60 = *(_QWORD *)(v34 + 8);
  if ( !v60 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v31 )
      goto LABEL_132;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v36 = *(unsigned __int8 **)(a2 + 184);
    if ( *v36 == 14 )
      goto LABEL_129;
    v37 = *v36 - 15;
    if ( *v36 != 15 )
      goto LABEL_72;
    if ( byte_140177431 >= 0 )
      goto LABEL_132;
    v40 = *((_QWORD *)v36 + 1);
    v41 = 1;
    v42 = *(unsigned __int8 *)(v40 + 2);
    if ( (_BYTE)v42 == 40 )
    {
      if ( !*(_DWORD *)(v40 + 20) )
      {
        v61 = *(_DWORD *)(v40 + 56);
        if ( v61 )
        {
          v44 = 0;
          v150 = 0;
          v45 = 0;
          v46 = 0;
          v62 = 0;
          v63 = 0;
          while ( 1 )
          {
            v35 = *(unsigned int *)(v40 + 4LL * v62 + 120);
            if ( (unsigned int)v35 >= 0x80 )
            {
              v64 = *(unsigned int *)(v40 + 16);
              if ( (unsigned int)v35 < (unsigned int)v64 )
              {
                v50 = (unsigned int)v35;
                v65 = *(_DWORD *)(v40 + v35) - 64;
                if ( v65 )
                {
                  LODWORD(v35) = v65 - 1;
                  if ( (_DWORD)v35 )
                  {
                    if ( (_DWORD)v35 == 1 )
                    {
                      LODWORD(v35) = v50 + 40;
                      if ( v50 + 40 <= v64 )
                        goto LABEL_92;
                    }
                  }
                  else
                  {
                    LODWORD(v35) = v50 + 56;
                    if ( v50 + 56 <= v64 )
                    {
                      v63 = 1;
                      if ( *(_BYTE *)(v40 + v50 + 10) )
                        v45 = (char *)(v50 + v40 + 24);
                      v46 = *(_BYTE **)(v40 + v50 + 16);
                      v44 = *(_BYTE *)(v40 + v50 + 9);
                      v150 = *(_BYTE *)(v40 + v50 + 8);
                    }
                  }
                }
                else
                {
                  LODWORD(v35) = v50 + 40;
                  if ( v50 + 40 <= v64 )
                    goto LABEL_106;
                }
                if ( v63 )
                  goto LABEL_103;
              }
            }
            if ( ++v62 >= v61 )
              goto LABEL_103;
          }
        }
      }
      goto LABEL_132;
    }
LABEL_109:
    v52 = *(_BYTE *)(v40 + 4);
    v44 = *(_BYTE *)(v40 + 11);
    v46 = *(_BYTE **)(v40 + 32);
    v53 = *(_BYTE *)(v40 + 72);
    if ( v42 )
      goto LABEL_132;
LABEL_110:
    LOBYTE(v35) = v53 - 8;
    if ( (v35 & 0x5D) == 0 )
    {
      v54 = *(_BYTE *)(v40 + 3);
      if ( v54 == 1 || !v46 || !v44 )
        goto LABEL_127;
      v55 = 0;
      v35 = (unsigned __int64)&v46[v44];
      v56 = 0;
      v57 = v46 + 8;
      LOBYTE(v40) = 0;
      if ( (unsigned __int8)((*v46 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v57 <= v35 )
        {
          v56 = v46[2];
          LOBYTE(v40) = v46[1] & 0xF;
          v55 = v46[3];
          goto LABEL_126;
        }
      }
      else if ( (unsigned __int64)v57 <= v35 )
      {
        v58 = v46 + 13;
        LOBYTE(v40) = v46[2] & 0xF;
        v59 = v44;
        if ( (unsigned int)(unsigned __int8)v46[7] + 8 <= v44 )
          v59 = (unsigned __int8)v46[7] + 8;
        v35 = (unsigned __int64)&v46[v59];
        if ( (unsigned __int64)v58 <= v35 )
          v56 = v46[12];
        if ( (unsigned __int64)(v46 + 14) > v35 )
          v55 = 0;
        else
          v55 = *v58;
LABEL_126:
        if ( v41 )
        {
LABEL_128:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v35,
            v40,
            (unsigned int)&v158,
            a2,
            *(_DWORD *)(a2 + 48),
            v54,
            v52,
            v40,
            v56,
            v55,
            a2);
          goto LABEL_132;
        }
LABEL_127:
        LOBYTE(v40) = 0;
        v56 = 0;
        v55 = 0;
        goto LABEL_128;
      }
      v41 = 0;
      goto LABEL_126;
    }
LABEL_132:
    IofCompleteRequest((PIRP)a2, 0);
    v32 = -1073741811;
LABEL_67:
    v33 = v154;
    goto LABEL_429;
  }
  v66 = *(_BYTE *)(v60 + 2);
  v67 = 24;
  if ( v66 != 40 )
    v67 = 12;
  if ( (*(_DWORD *)(v67 + v60) & 0x4000) == 0 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741811;
    if ( v31 )
      goto LABEL_132;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v36 = *(unsigned __int8 **)(a2 + 184);
    if ( *v36 == 14 )
      goto LABEL_129;
    v37 = *v36 - 15;
    if ( *v36 != 15 )
      goto LABEL_72;
    if ( byte_140177431 >= 0 )
      goto LABEL_132;
    v40 = *((_QWORD *)v36 + 1);
    v41 = 1;
    v42 = *(unsigned __int8 *)(v40 + 2);
    if ( (_BYTE)v42 == 40 )
    {
      if ( *(_DWORD *)(v40 + 20) )
        goto LABEL_132;
      v68 = *(_DWORD *)(v40 + 56);
      if ( !v68 )
        goto LABEL_132;
      v44 = 0;
      v150 = 0;
      v45 = 0;
      v46 = 0;
      v69 = 0;
      v70 = 0;
      while ( 1 )
      {
        v35 = *(unsigned int *)(v40 + 4LL * v69 + 120);
        if ( (unsigned int)v35 >= 0x80 )
        {
          v71 = *(unsigned int *)(v40 + 16);
          if ( (unsigned int)v35 < (unsigned int)v71 )
          {
            v50 = (unsigned int)v35;
            v72 = *(_DWORD *)(v40 + v35) - 64;
            if ( v72 )
            {
              LODWORD(v35) = v72 - 1;
              if ( (_DWORD)v35 )
              {
                if ( (_DWORD)v35 == 1 )
                {
                  LODWORD(v35) = v50 + 40;
                  if ( v50 + 40 <= v71 )
                  {
LABEL_92:
                    if ( *(_DWORD *)(v40 + v50 + 12) )
                      v45 = (char *)(v50 + v40 + 32);
                    v46 = *(_BYTE **)(v40 + v50 + 24);
                    goto LABEL_95;
                  }
                }
              }
              else
              {
                LODWORD(v35) = v50 + 56;
                if ( v50 + 56 <= v71 )
                {
                  v70 = 1;
                  if ( *(_BYTE *)(v40 + v50 + 10) )
                    v45 = (char *)(v50 + v40 + 24);
                  v46 = *(_BYTE **)(v40 + v50 + 16);
                  v44 = *(_BYTE *)(v40 + v50 + 9);
                  v150 = *(_BYTE *)(v40 + v50 + 8);
                }
              }
            }
            else
            {
              LODWORD(v35) = v50 + 40;
              if ( v50 + 40 <= v71 )
              {
LABEL_106:
                if ( *(_BYTE *)(v40 + v50 + 10) )
                  v45 = (char *)(v50 + v40 + 24);
                v46 = *(_BYTE **)(v40 + v50 + 16);
LABEL_95:
                v52 = *(_BYTE *)(v40 + v50 + 8);
                v44 = *(_BYTE *)(v40 + v50 + 9);
LABEL_104:
                if ( v45 )
                {
                  v53 = *v45;
                  goto LABEL_110;
                }
                goto LABEL_132;
              }
            }
            if ( v70 )
              goto LABEL_103;
          }
        }
        if ( ++v69 >= v68 )
          goto LABEL_103;
      }
    }
    goto LABEL_109;
  }
  v73 = (_DWORD *)*((_QWORD *)v2 + 3);
  if ( *v73 == 1314275652 )
  {
    v74 = (__int64)v73 + 282;
  }
  else if ( *v73 == 1094997074 )
  {
    v74 = (__int64)v73 + 466;
  }
  else
  {
    v74 = 98;
  }
  v41 = 1;
  if ( v66 == 40 )
  {
    if ( *(_BYTE *)v74 != 1 )
    {
      v31 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(v60 + 3) = 6;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = -1073741637;
      if ( v31 )
        goto LABEL_253;
      v158 = 0;
      IoGetActivityIdIrp(a2, &v158);
      v76 = *(_QWORD *)(a2 + 184);
      if ( *(_BYTE *)v76 == 14 )
      {
        if ( (byte_140177432 & 8) != 0 )
        {
          v78 = EventNonReadWriteRequestComplete;
          goto LABEL_252;
        }
LABEL_253:
        IofCompleteRequest((PIRP)a2, 0);
        v32 = -1073741637;
        goto LABEL_67;
      }
      if ( *(_BYTE *)v76 != 15 )
      {
        if ( *(_BYTE *)v76 == 27 )
        {
          if ( *(_BYTE *)(v76 + 1) == 7 && !*(_DWORD *)(v76 + 8) )
          {
            if ( (byte_140177432 & 0x40) != 0 )
            {
              v77 = *(int **)(a2 + 56);
              if ( v77 )
                v5 = *v77;
              McTemplateK0pqd_EtwWriteTransfer(v75, v76, (unsigned int)&v158, a2, v5, *(_DWORD *)(a2 + 48));
            }
            goto LABEL_253;
          }
          if ( (byte_140177432 & 0x20) != 0 )
          {
            v78 = EventPnpRequestComplete;
LABEL_252:
            McTemplateK0pd_EtwWriteTransfer(v75, v78, &v158, a2, *(_DWORD *)(a2 + 48));
            goto LABEL_253;
          }
        }
        goto LABEL_253;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_253;
      v79 = *(_QWORD *)(v76 + 8);
      if ( *(_BYTE *)(v79 + 2) == 40 )
      {
        if ( *(_DWORD *)(v79 + 20) )
          goto LABEL_253;
        v80 = *(_DWORD *)(v79 + 56);
        if ( !v80 )
          goto LABEL_253;
        v81 = 0;
        v151 = 0;
        v82 = 0;
        v83 = 0;
        v84 = 0;
        v85 = 0;
        do
        {
          v75 = *(unsigned int *)(v79 + 4LL * v84 + 120);
          if ( (unsigned int)v75 >= 0x80 )
          {
            v86 = *(unsigned int *)(v79 + 16);
            if ( (unsigned int)v75 < (unsigned int)v86 )
            {
              v87 = (unsigned int)v75;
              v88 = *(_DWORD *)(v79 + v75) - 64;
              if ( v88 )
              {
                LODWORD(v75) = v88 - 1;
                if ( (_DWORD)v75 )
                {
                  if ( (_DWORD)v75 == 1 )
                  {
                    LODWORD(v75) = v87 + 40;
                    if ( v87 + 40 <= v86 )
                    {
                      if ( *(_DWORD *)(v79 + v87 + 12) )
                        v82 = (char *)(v87 + v79 + 32);
                      v83 = *(_BYTE **)(v79 + v87 + 24);
LABEL_216:
                      v89 = *(_BYTE *)(v79 + v87 + 8);
                      v81 = *(_BYTE *)(v79 + v87 + 9);
                      goto LABEL_225;
                    }
                  }
                }
                else
                {
                  LODWORD(v75) = v87 + 56;
                  if ( v87 + 56 <= v86 )
                  {
                    v85 = 1;
                    if ( *(_BYTE *)(v79 + v87 + 10) )
                      v82 = (char *)(v87 + v79 + 24);
                    v83 = *(_BYTE **)(v79 + v87 + 16);
                    v81 = *(_BYTE *)(v79 + v87 + 9);
                    v151 = *(_BYTE *)(v79 + v87 + 8);
                  }
                }
              }
              else
              {
                LODWORD(v75) = v87 + 40;
                if ( v87 + 40 <= v86 )
                {
                  if ( *(_BYTE *)(v79 + v87 + 10) )
                    v82 = (char *)(v87 + v79 + 24);
                  v83 = *(_BYTE **)(v79 + v87 + 16);
                  goto LABEL_216;
                }
              }
              if ( v85 )
                break;
            }
          }
          ++v84;
        }
        while ( v84 < v80 );
        v89 = v151;
LABEL_225:
        if ( !v82 )
          goto LABEL_253;
        v90 = *v82;
      }
      else
      {
        v90 = *(_BYTE *)(v79 + 72);
        v83 = *(_BYTE **)(v79 + 32);
        v81 = *(_BYTE *)(v79 + 11);
        v89 = *(_BYTE *)(v79 + 4);
        if ( *(_BYTE *)(v79 + 2) )
          goto LABEL_253;
      }
      LOBYTE(v75) = v90 - 8;
      if ( (v75 & 0x5D) != 0 )
        goto LABEL_253;
      v91 = *(_BYTE *)(v79 + 3);
      if ( v91 == 1 || !v83 || !v81 )
        goto LABEL_248;
      LOBYTE(v79) = 0;
      v75 = (unsigned __int64)&v83[v81];
      v92 = 0;
      v93 = v83 + 8;
      v94 = 0;
      if ( (unsigned __int8)((*v83 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v93 <= v75 )
        {
          v92 = v83[2];
          LOBYTE(v79) = v83[1] & 0xF;
          v94 = v83[3];
          goto LABEL_247;
        }
      }
      else if ( (unsigned __int64)v93 <= v75 )
      {
        v95 = v83 + 13;
        LOBYTE(v79) = v83[2] & 0xF;
        v96 = v81;
        if ( (unsigned int)(unsigned __int8)v83[7] + 8 <= v81 )
          v96 = (unsigned __int8)v83[7] + 8;
        v75 = (unsigned __int64)&v83[v96];
        if ( (unsigned __int64)v95 <= v75 )
          v92 = v83[12];
        if ( (unsigned __int64)(v83 + 14) > v75 )
          v94 = 0;
        else
          v94 = *v95;
LABEL_247:
        if ( v41 )
        {
LABEL_249:
          McTemplateK0pduuuuup_EtwWriteTransfer(
            v75,
            v79,
            (unsigned int)&v158,
            a2,
            *(_DWORD *)(a2 + 48),
            v91,
            v89,
            v79,
            v92,
            v94,
            a2);
          goto LABEL_253;
        }
LABEL_248:
        LOBYTE(v79) = 0;
        v92 = 0;
        v94 = 0;
        goto LABEL_249;
      }
      v41 = 0;
      goto LABEL_247;
    }
    if ( *(_DWORD *)(v60 + 8) != 1397899864
      || *(_DWORD *)(v60 + 48)
      || (v97 = v60, v98 = *(_DWORD *)(v60 + 20), v156 = v98, v155 = *(_DWORD *)(v60 + 24), *(_QWORD *)(v60 + 72)) )
    {
      v31 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(v60 + 3) = 6;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = -1073741811;
      if ( v31 )
        goto LABEL_132;
      v158 = 0;
      IoGetActivityIdIrp(a2, &v158);
      v36 = *(unsigned __int8 **)(a2 + 184);
      if ( *v36 == 14 )
        goto LABEL_129;
      v37 = *v36 - 15;
      if ( *v36 != 15 )
        goto LABEL_72;
      if ( byte_140177431 >= 0 )
        goto LABEL_132;
      v40 = *((_QWORD *)v36 + 1);
      v42 = *(unsigned __int8 *)(v40 + 2);
      if ( (_BYTE)v42 == 40 )
      {
        if ( *(_DWORD *)(v40 + 20) )
          goto LABEL_132;
        v99 = *(_DWORD *)(v40 + 56);
        if ( !v99 )
          goto LABEL_132;
        v44 = 0;
        v150 = 0;
        v45 = 0;
        v46 = 0;
        v100 = 0;
        v101 = 0;
        while ( 1 )
        {
          v35 = *(unsigned int *)(v40 + 4LL * v100 + 120);
          if ( (unsigned int)v35 >= 0x80 )
          {
            v102 = *(unsigned int *)(v40 + 16);
            if ( (unsigned int)v35 < (unsigned int)v102 )
            {
              v103 = (unsigned int)v35;
              v104 = *(_DWORD *)(v35 + v40) - 64;
              if ( v104 )
              {
                LODWORD(v35) = v104 - 1;
                if ( (_DWORD)v35 )
                {
                  if ( (_DWORD)v35 == 1 )
                  {
                    LODWORD(v35) = v103 + 40;
                    if ( v103 + 40 <= v102 )
                    {
                      if ( *(_DWORD *)(v103 + v40 + 12) )
                        v45 = (char *)(v103 + v40 + 32);
                      v46 = *(_BYTE **)(v103 + v40 + 24);
LABEL_274:
                      v52 = *(_BYTE *)(v103 + v40 + 8);
                      v44 = *(_BYTE *)(v103 + v40 + 9);
                      goto LABEL_104;
                    }
                  }
                }
                else
                {
                  LODWORD(v35) = v103 + 56;
                  if ( v103 + 56 <= v102 )
                  {
                    v101 = 1;
                    if ( *(_BYTE *)(v103 + v40 + 10) )
                      v45 = (char *)(v103 + v40 + 24);
                    v46 = *(_BYTE **)(v103 + v40 + 16);
                    v44 = *(_BYTE *)(v103 + v40 + 9);
                    v150 = *(_BYTE *)(v103 + v40 + 8);
                  }
                }
              }
              else
              {
                LODWORD(v35) = v103 + 40;
                if ( v103 + 40 <= v102 )
                {
                  if ( *(_BYTE *)(v103 + v40 + 10) )
                    v45 = (char *)(v103 + v40 + 24);
                  v46 = *(_BYTE **)(v103 + v40 + 16);
                  goto LABEL_274;
                }
              }
              if ( v101 )
                goto LABEL_103;
            }
          }
          if ( ++v100 >= v99 )
          {
LABEL_103:
            v52 = v150;
            goto LABEL_104;
          }
        }
      }
      goto LABEL_109;
    }
  }
  else
  {
    v97 = 0;
    v155 = *(_DWORD *)(v60 + 12);
    v98 = *(unsigned __int8 *)(v60 + 2);
    v156 = v98;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids, v2, a2, v98);
    v2 = v154;
  }
  if ( (v155 & 0x100000) != 0 )
  {
    if ( (v105 = *((_QWORD *)v2 + 3), (v106 = *(_QWORD *)(v105 + 5024)) != 0) && (*(_DWORD *)(v106 + 20) & 1) == 0
      || (*(_BYTE *)(v105 + 107) & 4) != 0
      || *(_DWORD *)(v105 + 332) != 1 )
    {
      v31 = StorEtwLoggingEnabled == 0;
      *(_BYTE *)(v60 + 3) = 36;
      *(_QWORD *)(a2 + 56) = 0;
      *(_BYTE *)(a2 + 141) = -84;
      *(_DWORD *)(a2 + 48) = -1073741823;
      if ( v31 )
        goto LABEL_66;
      v158 = 0;
      IoGetActivityIdIrp(a2, &v158);
      v9 = *(unsigned __int8 **)(a2 + 184);
      if ( *v9 != 14 )
      {
        v10 = *v9 - 15;
        if ( *v9 != 15 )
          goto LABEL_5;
        if ( byte_140177431 >= 0 )
          goto LABEL_66;
        v107 = *((_QWORD *)v9 + 1);
        v108 = *(unsigned __int8 *)(v107 + 2);
        if ( (_BYTE)v108 == 40 )
        {
          if ( *(_DWORD *)(v107 + 20) )
            goto LABEL_66;
          v109 = *(_DWORD *)(v107 + 56);
          if ( !v109 )
            goto LABEL_66;
          v110 = 0;
          v152 = 0;
          v111 = 0;
          v112 = 0;
          v113 = 0;
          v114 = 0;
          while ( 1 )
          {
            v8 = *(unsigned int *)(v107 + 4LL * v113 + 120);
            if ( (unsigned int)v8 >= 0x80 )
            {
              v115 = *(unsigned int *)(v107 + 16);
              if ( (unsigned int)v8 < (unsigned int)v115 )
              {
                v116 = (unsigned int)v8;
                v117 = *(_DWORD *)(v8 + v107) - 64;
                if ( v117 )
                {
                  LODWORD(v8) = v117 - 1;
                  if ( (_DWORD)v8 )
                  {
                    if ( (_DWORD)v8 == 1 )
                    {
                      LODWORD(v8) = v116 + 40;
                      if ( v116 + 40 <= v115 )
                        goto LABEL_310;
                    }
                  }
                  else
                  {
                    LODWORD(v8) = v116 + 56;
                    if ( v116 + 56 <= v115 )
                    {
                      v114 = 1;
                      if ( *(_BYTE *)(v116 + v107 + 10) )
                        v111 = (char *)(v116 + v107 + 24);
                      v112 = *(_BYTE **)(v116 + v107 + 16);
                      v110 = *(_BYTE *)(v116 + v107 + 9);
                      v152 = *(_BYTE *)(v116 + v107 + 8);
                    }
                  }
                }
                else
                {
                  LODWORD(v8) = v116 + 40;
                  if ( v116 + 40 <= v115 )
                    goto LABEL_324;
                }
                if ( v114 )
                  goto LABEL_321;
              }
            }
            if ( ++v113 >= v109 )
              goto LABEL_321;
          }
        }
        goto LABEL_327;
      }
LABEL_62:
      v31 = (byte_140177432 & 8) == 0;
LABEL_63:
      if ( v31 )
        goto LABEL_66;
      v12 = EventNonReadWriteRequestComplete;
      goto LABEL_65;
    }
  }
  if ( v156 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(v60 + 3) = 6;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741823;
    if ( v31 )
      goto LABEL_66;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v9 = *(unsigned __int8 **)(a2 + 184);
    if ( *v9 != 14 )
    {
      v10 = *v9 - 15;
      if ( *v9 != 15 )
        goto LABEL_5;
      if ( byte_140177431 >= 0 )
        goto LABEL_66;
      v107 = *((_QWORD *)v9 + 1);
      v108 = *(unsigned __int8 *)(v107 + 2);
      if ( (_BYTE)v108 == 40 )
      {
        if ( *(_DWORD *)(v107 + 20) )
          goto LABEL_66;
        v126 = *(_DWORD *)(v107 + 56);
        if ( !v126 )
          goto LABEL_66;
        v110 = 0;
        v152 = 0;
        v111 = 0;
        v112 = 0;
        v127 = 0;
        v128 = 0;
        while ( 1 )
        {
          v8 = *(unsigned int *)(v107 + 4LL * v127 + 120);
          if ( (unsigned int)v8 >= 0x80 )
          {
            v129 = *(unsigned int *)(v107 + 16);
            if ( (unsigned int)v8 < (unsigned int)v129 )
            {
              v116 = (unsigned int)v8;
              v130 = *(_DWORD *)(v8 + v107) - 64;
              if ( v130 )
              {
                LODWORD(v8) = v130 - 1;
                if ( (_DWORD)v8 )
                {
                  if ( (_DWORD)v8 == 1 )
                  {
                    LODWORD(v8) = v116 + 40;
                    if ( v116 + 40 <= v129 )
                      goto LABEL_310;
                  }
                }
                else
                {
                  LODWORD(v8) = v116 + 56;
                  if ( v116 + 56 <= v129 )
                  {
                    v128 = 1;
                    if ( *(_BYTE *)(v116 + v107 + 10) )
                      v111 = (char *)(v116 + v107 + 24);
                    v112 = *(_BYTE **)(v116 + v107 + 16);
                    v110 = *(_BYTE *)(v116 + v107 + 9);
                    v152 = *(_BYTE *)(v116 + v107 + 8);
                  }
                }
              }
              else
              {
                LODWORD(v8) = v116 + 40;
                if ( v116 + 40 <= v129 )
                  goto LABEL_324;
              }
              if ( v128 )
                goto LABEL_321;
            }
          }
          if ( ++v127 >= v126 )
            goto LABEL_321;
        }
      }
      goto LABEL_327;
    }
    goto LABEL_62;
  }
  if ( *(_BYTE *)(v60 + 2) != 40 )
  {
    v131 = (_BYTE *)(v60 + 72);
    goto LABEL_395;
  }
  v131 = 0;
  if ( *(_BYTE *)(v97 + 2) == 40 && !*(_DWORD *)(v97 + 20) )
  {
    v132 = *(_DWORD *)(v97 + 56);
    if ( v132 )
    {
      v133 = 0;
      v153 = 0;
      do
      {
        v134 = *(unsigned int *)(v97 + 4LL * v133 + 120);
        if ( (unsigned int)v134 >= 0x80 )
        {
          v135 = *(unsigned int *)(v97 + 16);
          if ( (unsigned int)v134 < (unsigned int)v135 )
          {
            v136 = (unsigned int)v134;
            v137 = *(_DWORD *)(v134 + v97) - 64;
            if ( v137 )
            {
              v138 = v137 - 1;
              if ( v138 )
              {
                if ( v138 == 1 && v136 + 40 <= v135 )
                {
                  if ( !*(_DWORD *)(v136 + v97 + 12) )
                    break;
                  v139 = v97 + 32;
                  goto LABEL_393;
                }
              }
              else if ( v136 + 56 <= v135 )
              {
                if ( !*(_BYTE *)(v136 + v97 + 10) )
                  break;
                v153 = 1;
                v131 = (_BYTE *)(v136 + v97 + 24);
              }
            }
            else if ( v136 + 40 <= v135 )
            {
              if ( !*(_BYTE *)(v136 + v97 + 10) )
                break;
              v139 = v97 + 24;
LABEL_393:
              v131 = (_BYTE *)(v136 + v139);
              break;
            }
            if ( v153 )
              break;
          }
        }
        ++v133;
      }
      while ( v133 < v132 );
    }
  }
LABEL_395:
  v140 = (unsigned __int8)*v131;
  if ( ((*v131 - 8) & 0x5D) != 0 )
  {
    v31 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(v60 + 3) = 6;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = -1073741823;
    if ( v31 )
      goto LABEL_66;
    v158 = 0;
    IoGetActivityIdIrp(a2, &v158);
    v9 = *(unsigned __int8 **)(a2 + 184);
    if ( *v9 == 14 )
    {
      v31 = (byte_140177432 & 8) == 0;
      goto LABEL_63;
    }
    v10 = *v9 - 15;
    if ( *v9 != 15 )
      goto LABEL_5;
    if ( byte_140177431 >= 0 )
      goto LABEL_66;
    v107 = *((_QWORD *)v9 + 1);
    v108 = *(unsigned __int8 *)(v107 + 2);
    if ( (_BYTE)v108 == 40 )
    {
      if ( *(_DWORD *)(v107 + 20) )
        goto LABEL_66;
      v141 = *(_DWORD *)(v107 + 56);
      if ( !v141 )
        goto LABEL_66;
      v110 = 0;
      v152 = 0;
      v111 = 0;
      v112 = 0;
      v142 = 0;
      v143 = 0;
      while ( 1 )
      {
        v8 = *(unsigned int *)(v107 + 4LL * v142 + 120);
        if ( (unsigned int)v8 >= 0x80 )
        {
          v144 = *(unsigned int *)(v107 + 16);
          if ( (unsigned int)v8 < (unsigned int)v144 )
          {
            v116 = (unsigned int)v8;
            v145 = *(_DWORD *)(v8 + v107) - 64;
            if ( v145 )
            {
              LODWORD(v8) = v145 - 1;
              if ( (_DWORD)v8 )
              {
                if ( (_DWORD)v8 == 1 )
                {
                  LODWORD(v8) = v116 + 40;
                  if ( v116 + 40 <= v144 )
                  {
LABEL_310:
                    if ( *(_DWORD *)(v116 + v107 + 12) )
                      v111 = (char *)(v116 + v107 + 32);
                    v112 = *(_BYTE **)(v116 + v107 + 24);
                    goto LABEL_313;
                  }
                }
              }
              else
              {
                LODWORD(v8) = v116 + 56;
                if ( v116 + 56 <= v144 )
                {
                  v143 = 1;
                  if ( *(_BYTE *)(v116 + v107 + 10) )
                    v111 = (char *)(v116 + v107 + 24);
                  v112 = *(_BYTE **)(v116 + v107 + 16);
                  v110 = *(_BYTE *)(v116 + v107 + 9);
                  v152 = *(_BYTE *)(v116 + v107 + 8);
                }
              }
            }
            else
            {
              LODWORD(v8) = v116 + 40;
              if ( v116 + 40 <= v144 )
              {
LABEL_324:
                if ( *(_BYTE *)(v116 + v107 + 10) )
                  v111 = (char *)(v116 + v107 + 24);
                v112 = *(_BYTE **)(v116 + v107 + 16);
LABEL_313:
                v118 = *(_BYTE *)(v116 + v107 + 8);
                v110 = *(_BYTE *)(v116 + v107 + 9);
LABEL_322:
                if ( !v111 )
                  goto LABEL_66;
                v119 = *v111;
LABEL_328:
                LOBYTE(v8) = v119 - 8;
                if ( (v8 & 0x5D) != 0 )
                  goto LABEL_66;
                v120 = *(_BYTE *)(v107 + 3);
                if ( v120 == 1 || !v112 || !v110 )
                  goto LABEL_345;
                LOBYTE(v107) = 0;
                v8 = (unsigned __int64)&v112[v110];
                v121 = 0;
                v122 = v112 + 8;
                v123 = 0;
                if ( (unsigned __int8)((*v112 & 0x7F) - 114) <= 1u )
                {
                  if ( (unsigned __int64)v122 <= v8 )
                  {
                    v121 = v112[2];
                    LOBYTE(v107) = v112[1] & 0xF;
                    v123 = v112[3];
                    goto LABEL_344;
                  }
                }
                else if ( (unsigned __int64)v122 <= v8 )
                {
                  v124 = v112 + 13;
                  LOBYTE(v107) = v112[2] & 0xF;
                  v125 = v110;
                  if ( (unsigned int)(unsigned __int8)v112[7] + 8 <= v110 )
                    v125 = (unsigned __int8)v112[7] + 8;
                  v8 = (unsigned __int64)&v112[v125];
                  if ( (unsigned __int64)v124 <= v8 )
                    v121 = v112[12];
                  if ( (unsigned __int64)(v112 + 14) > v8 )
                    v123 = 0;
                  else
                    v123 = *v124;
LABEL_344:
                  if ( !v41 )
                  {
LABEL_345:
                    LOBYTE(v107) = 0;
                    v121 = 0;
                    v123 = 0;
                  }
                  McTemplateK0pduuuuup_EtwWriteTransfer(
                    v8,
                    v107,
                    (unsigned int)&v158,
                    a2,
                    *(_DWORD *)(a2 + 48),
                    v120,
                    v118,
                    v107,
                    v121,
                    v123,
                    a2);
                  goto LABEL_66;
                }
                v41 = 0;
                goto LABEL_344;
              }
            }
            if ( v143 )
              goto LABEL_321;
          }
        }
        if ( ++v142 >= v141 )
        {
LABEL_321:
          v118 = v152;
          goto LABEL_322;
        }
      }
    }
LABEL_327:
    v119 = *(_BYTE *)(v107 + 72);
    v112 = *(_BYTE **)(v107 + 32);
    v110 = *(_BYTE *)(v107 + 11);
    v118 = *(_BYTE *)(v107 + 4);
    if ( v108 )
      goto LABEL_66;
    goto LABEL_328;
  }
  if ( StorEtwLoggingEnabled && (byte_140177431 & 0x1E) != 0 )
  {
    if ( (_BYTE)v140 == 8
      || (unsigned __int8)v140 <= 0x2Au && (v146 = 0x50000000400LL, _bittest64(&v146, v140))
      || (LOBYTE(v140) = v140 + 120, (unsigned __int8)v140 <= 0x22u) && (v147 = 0x500000005LL, _bittest64(&v147, v140)) )
    {
      IoGetActivityIdIrp(a2, &v159);
      StorEtwIORequestDispatch(a2);
    }
  }
  v33 = v154;
  *(_BYTE *)(a2 + 141) = -88;
  v32 = RaidUnitSubmitRequest(v154, a2);
LABEL_429:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqD(
      WPP_GLOBAL_Control->AttachedDevice,
      76,
      WPP_79b784db0f1333d9a4638a6d2649ad59_Traceguids,
      a1,
      v33,
      a2,
      v32);
  }
  return v32;
}

```

## disassembly

```asm
0x14006d300  mov     [rsp-8+arg_10], rbx
0x14006d305  push    rbp
0x14006d306  push    rsi
0x14006d307  push    rdi
0x14006d308  push    r12
0x14006d30a  push    r13
0x14006d30c  push    r14
0x14006d30e  push    r15
0x14006d310  lea     rbp, [rsp-27h]
0x14006d315  sub     rsp, 0B0h
0x14006d31c  mov     rax, cs:__security_cookie
0x14006d323  xor     rax, rsp
0x14006d326  mov     [rbp+57h+var_40], rax
0x14006d32a  mov     r9, [rcx+40h]
0x14006d32e  lea     r10, WPP_GLOBAL_Control
0x14006d335  mov     rdi, rdx
0x14006d338  mov     [rbp+57h+var_68], rcx
0x14006d33c  mov     rdx, rcx
0x14006d33f  mov     [rbp+57h+var_78], r9
0x14006d343  xorps   xmm0, xmm0
0x14006d346  xor     ebx, ebx
0x14006d348  mov     ecx, [r9]
0x14006d34b  add     qword ptr [rdi+0B8h], 0FFFFFFFFFFFFFFB8h
0x14006d353  dec     byte ptr [rdi+43h]
0x14006d356  mov     rax, [rdi+0B8h]
0x14006d35d  movups  [rbp+57h+var_50], xmm0
0x14006d361  mov     [rax+28h], rdx
0x14006d365  cmp     ecx, 554E4954h
0x14006d36b  jz      loc_14006D665
0x14006d371  cmp     cs:StorEtwLoggingEnabled, bl
0x14006d377  mov     [rdi+38h], rbx
0x14006d37b  mov     byte ptr [rdi+8Dh], 0ACh
0x14006d382  mov     dword ptr [rdi+30h], 0C0000001h
0x14006d389  jz      loc_14006D646
0x14006d38f  lea     rdx, [rbp+57h+var_60]
0x14006d393  mov     rcx, rdi
0x14006d396  movups  [rbp+57h+var_60], xmm0
0x14006d39a  call    cs:__imp_IoGetActivityIdIrp
0x14006d3a1  nop     dword ptr [rax+rax+00h]
0x14006d3a6  mov     rdx, [rdi+0B8h]
0x14006d3ad  movzx   eax, byte ptr [rdx]
0x14006d3b0  sub     eax, 0Eh
0x14006d3b3  jz      loc_14006D623
0x14006d3b9  sub     eax, 1
0x14006d3bc  jz      short loc_14006D423
0x14006d3be  lea     r13d, [rbx+0Ch]
0x14006d3c2  cmp     eax, r13d
0x14006d3c5  jnz     loc_14006D646
0x14006d3cb  cmp     byte ptr [rdx+1], 7
0x14006d3cf  jnz     short loc_14006D40A
0x14006d3d1  cmp     [rdx+8], ebx
0x14006d3d4  jnz     short loc_14006D40A
0x14006d3d6  test    cs:byte_140177432, 40h
0x14006d3dd  jz      loc_14006D646
0x14006d3e3  mov     rax, [rdi+38h]
0x14006d3e7  test    rax, rax
0x14006d3ea  jz      short loc_14006D3EE
0x14006d3ec  mov     ebx, [rax]
0x14006d3ee  mov     eax, [rdi+30h]
0x14006d3f1  lea     r8, [rbp+57h+var_60]
0x14006d3f5  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14006d3f9  mov     r9, rdi
0x14006d3fc  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14006d400  call    McTemplateK0pqd_EtwWriteTransfer
0x14006d405  jmp     loc_14006D646
0x14006d40a  test    cs:byte_140177432, 20h
0x14006d411  jz      loc_14006D646
0x14006d417  lea     rdx, EventPnpRequestComplete
0x14006d41e  jmp     loc_14006D633
0x14006d423  cmp     cs:byte_140177431, bl
0x14006d429  jge     loc_14006D646
0x14006d42f  mov     rdx, [rdx+8]
0x14006d433  mov     r12b, 28h ; '('
0x14006d436  mov     esi, 1
0x14006d43b  movzx   eax, byte ptr [rdx+2]
0x14006d43f  cmp     al, r12b
0x14006d442  jnz     loc_14006D52C
0x14006d448  cmp     [rdx+14h], ebx
0x14006d44b  jnz     loc_14006D646
0x14006d451  mov     r12d, [rdx+38h]
0x14006d455  test    r12d, r12d
0x14006d458  jz      loc_14006D646
0x14006d45e  mov     r10b, bl
0x14006d461  mov     [rbp+57h+var_80], bl
0x14006d464  mov     r11, rbx
0x14006d467  mov     r13b, bl
0x14006d46a  mov     r9, rbx
0x14006d46d  mov     r15d, ebx
0x14006d470  mov     eax, r15d
0x14006d473  mov     ecx, [rdx+rax*4+78h]
0x14006d477  cmp     ecx, 80h
0x14006d47d  jb      short loc_14006D4F3
0x14006d47f  mov     r14d, [rdx+10h]
0x14006d483  cmp     ecx, r14d
0x14006d486  jnb     short loc_14006D4F3
0x14006d488  mov     r8d, ecx
0x14006d48b  mov     ecx, [rcx+rdx]
0x14006d48e  sub     ecx, 40h ; '@'
0x14006d491  jz      short loc_14006D4E5
0x14006d493  sub     ecx, esi
0x14006d495  jz      short loc_14006D4B9
0x14006d497  cmp     ecx, esi
0x14006d499  jnz     short loc_14006D4EE
0x14006d49b  lea     rcx, [r8+28h]
0x14006d49f  cmp     rcx, r14
0x14006d4a2  ja      short loc_14006D4EE
0x14006d4a4  cmp     [r8+rdx+0Ch], ebx
0x14006d4a9  jbe     short loc_14006D4B2
0x14006d4ab  lea     r11, [rdx+20h]
0x14006d4af  add     r11, r8
0x14006d4b2  mov     r9, [r8+rdx+18h]
0x14006d4b7  jmp     short loc_14006D514
0x14006d4b9  lea     rcx, [r8+38h]
0x14006d4bd  cmp     rcx, r14
0x14006d4c0  ja      short loc_14006D4EE
0x14006d4c2  mov     [rbp+57h+var_80], sil
0x14006d4c6  cmp     [r8+rdx+0Ah], bl
0x14006d4cb  jbe     short loc_14006D4D4
0x14006d4cd  lea     r11, [rdx+18h]
0x14006d4d1  add     r11, r8
0x14006d4d4  mov     r13b, [r8+rdx+8]
0x14006d4d9  mov     r9, [r8+rdx+10h]
0x14006d4de  mov     r10b, [r8+rdx+9]
0x14006d4e3  jmp     short loc_14006D4EE
0x14006d4e5  lea     rcx, [r8+28h]
0x14006d4e9  cmp     rcx, r14
0x14006d4ec  jbe     short loc_14006D501
0x14006d4ee  cmp     [rbp+57h+var_80], bl
0x14006d4f1  jnz     short loc_14006D51E
0x14006d4f3  add     r15d, esi
0x14006d4f6  cmp     r15d, r12d
0x14006d4f9  jb      loc_14006D470
0x14006d4ff  jmp     short loc_14006D51E
0x14006d501  cmp     [r8+rdx+0Ah], bl
0x14006d506  jbe     short loc_14006D50F
0x14006d508  lea     r11, [rdx+18h]
0x14006d50c  add     r11, r8
0x14006d50f  mov     r9, [r8+rdx+10h]
0x14006d514  mov     r10b, [r8+rdx+9]
0x14006d519  mov     r13b, [r8+rdx+8]
0x14006d51e  test    r11, r11
0x14006d521  jz      loc_14006D646
0x14006d527  mov     cl, [r11]
0x14006d52a  jmp     short loc_14006D543
0x14006d52c  mov     cl, [rdx+48h]
0x14006d52f  mov     r9, [rdx+20h]
0x14006d533  mov     r10b, [rdx+0Bh]
0x14006d537  mov     r13b, [rdx+4]
0x14006d53b  test    eax, eax
0x14006d53d  jnz     loc_14006D646
0x14006d543  sub     cl, 8
0x14006d546  test    cl, 5Dh
0x14006d549  jnz     loc_14006D646
0x14006d54f  mov     r14b, [rdx+3]
0x14006d553  cmp     r14b, sil
0x14006d556  jz      loc_14006D5E9
0x14006d55c  test    r9, r9
0x14006d55f  jz      loc_14006D5E9
0x14006d565  test    r10b, r10b
0x14006d568  jz      short loc_14006D5E9
0x14006d56a  mov     al, [r9]
0x14006d56d  mov     dl, bl
0x14006d56f  and     al, 7Fh
0x14006d571  movzx   ecx, r10b
0x14006d575  sub     al, 72h ; 'r'
0x14006d577  add     rcx, r9
0x14006d57a  cmp     al, sil
0x14006d57d  mov     r11b, bl
0x14006d580  lea     rax, [r9+8]
0x14006d584  mov     r8b, bl
0x14006d587  jbe     short loc_14006D5CB
0x14006d589  cmp     rax, rcx
0x14006d58c  ja      short loc_14006D5E1
0x14006d58e  movzx   ecx, byte ptr [r9+7]
0x14006d593  lea     r8, [r9+0Dh]
0x14006d597  mov     dl, [r9+2]
0x14006d59b  add     ecx, 8
0x14006d59e  and     dl, 0Fh
0x14006d5a1  movzx   eax, r10b
0x14006d5a5  cmp     ecx, eax
0x14006d5a7  cmovbe  eax, ecx
0x14006d5aa  mov     ecx, eax
0x14006d5ac  add     rcx, r9
0x14006d5af  cmp     r8, rcx
0x14006d5b2  ja      short loc_14006D5B8
0x14006d5b4  mov     r11b, [r9+0Ch]
0x14006d5b8  lea     rax, [r9+0Eh]
0x14006d5bc  cmp     rax, rcx
0x14006d5bf  ja      short loc_14006D5C6
0x14006d5c1  mov     r8b, [r8]
0x14006d5c4  jmp     short loc_14006D5E4
0x14006d5c6  mov     r8b, bl
0x14006d5c9  jmp     short loc_14006D5E4
0x14006d5cb  cmp     rax, rcx
0x14006d5ce  ja      short loc_14006D5E1
0x14006d5d0  mov     dl, [r9+1]
0x14006d5d4  mov     r11b, [r9+2]
0x14006d5d8  and     dl, 0Fh
0x14006d5db  mov     r8b, [r9+3]
0x14006d5df  jmp     short loc_14006D5E4
0x14006d5e1  mov     sil, bl
0x14006d5e4  test    sil, sil
0x14006d5e7  jnz     short loc_14006D5F1
0x14006d5e9  mov     dl, bl
0x14006d5eb  mov     r11b, bl
0x14006d5ee  mov     r8b, bl
0x14006d5f1  mov     [rsp+0E0h+var_90], rdi
0x14006d5f6  mov     [rsp+0E0h+var_98], r8b
0x14006d5fb  mov     [rsp+0E0h+var_A0], r11b
0x14006d600  mov     [rsp+0E0h+var_A8], dl
0x14006d604  mov     byte ptr [rsp+0E0h+var_B0], r13b
0x14006d609  mov     eax, [rdi+30h]
0x14006d60c  lea     r8, [rbp+57h+var_60]
0x14006d610  mov     byte ptr [rsp+0E0h+var_B8], r14b
0x14006d615  mov     r9, rdi
0x14006d618  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14006d61c  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14006d621  jmp     short loc_14006D646
0x14006d623  test    cs:byte_140177432, 8
0x14006d62a  jz      short loc_14006D646
0x14006d62c  lea     rdx, EventNonReadWriteRequestComplete
0x14006d633  mov     eax, [rdi+30h]
0x14006d636  lea     r8, [rbp+57h+var_60]
0x14006d63a  mov     r9, rdi
0x14006d63d  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14006d641  call    McTemplateK0pd_EtwWriteTransfer
0x14006d646  xor     edx, edx; PriorityBoost
0x14006d648  mov     rcx, rdi; Irp
0x14006d64b  call    cs:__imp_IofCompleteRequest
0x14006d652  nop     dword ptr [rax+rax+00h]
0x14006d657  mov     ebx, 0C0000001h
0x14006d65c  mov     rsi, [rbp+57h+var_78]
0x14006d660  jmp     loc_14006E72A
0x14006d665  mov     r14, [rdi+0B8h]
0x14006d66c  cmp     byte ptr [r14], 0Fh
0x14006d670  jz      loc_14006D972
0x14006d676  cmp     cs:StorEtwLoggingEnabled, bl
0x14006d67c  mov     [rdi+38h], rbx
0x14006d680  mov     byte ptr [rdi+8Dh], 0ACh
0x14006d687  mov     dword ptr [rdi+30h], 0C000000Dh
0x14006d68e  jz      loc_14006D957
0x14006d694  lea     rdx, [rbp+57h+var_60]
0x14006d698  mov     rcx, rdi
0x14006d69b  movups  [rbp+57h+var_60], xmm0
0x14006d69f  call    cs:__imp_IoGetActivityIdIrp
0x14006d6a6  nop     dword ptr [rax+rax+00h]
0x14006d6ab  mov     rdx, [rdi+0B8h]
0x14006d6b2  movzx   eax, byte ptr [rdx]
0x14006d6b5  sub     eax, 0Eh
0x14006d6b8  jz      loc_14006D934
0x14006d6be  sub     eax, 1
0x14006d6c1  jz      short loc_14006D72A
0x14006d6c3  mov     r13d, 0Ch
0x14006d6c9  cmp     eax, r13d
0x14006d6cc  jnz     loc_14006D957
0x14006d6d2  cmp     byte ptr [rdx+1], 7
0x14006d6d6  jnz     short loc_14006D711
0x14006d6d8  cmp     [rdx+8], ebx
0x14006d6db  jnz     short loc_14006D711
0x14006d6dd  test    cs:byte_140177432, 40h
0x14006d6e4  jz      loc_14006D957
0x14006d6ea  mov     rax, [rdi+38h]
0x14006d6ee  test    rax, rax
0x14006d6f1  jz      short loc_14006D6F5
0x14006d6f3  mov     ebx, [rax]
0x14006d6f5  mov     eax, [rdi+30h]
0x14006d6f8  lea     r8, [rbp+57h+var_60]
0x14006d6fc  mov     dword ptr [rsp+0E0h+var_B8], eax
0x14006d700  mov     r9, rdi
0x14006d703  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14006d707  call    McTemplateK0pqd_EtwWriteTransfer
0x14006d70c  jmp     loc_14006D957
0x14006d711  test    cs:byte_140177432, 20h
0x14006d718  jz      loc_14006D957
0x14006d71e  lea     rdx, EventPnpRequestComplete
0x14006d725  jmp     loc_14006D944
0x14006d72a  cmp     cs:byte_140177431, bl
0x14006d730  jge     loc_14006D957
0x14006d736  mov     rdx, [rdx+8]
0x14006d73a  mov     r12b, 28h ; '('
0x14006d73d  mov     esi, 1
0x14006d742  movzx   eax, byte ptr [rdx+2]
0x14006d746  cmp     al, r12b
0x14006d749  jnz     loc_14006D83D
0x14006d74f  cmp     [rdx+14h], ebx
0x14006d752  jnz     loc_14006D957
0x14006d758  mov     r12d, [rdx+38h]
0x14006d75c  test    r12d, r12d
0x14006d75f  jz      loc_14006D957
0x14006d765  mov     r11b, bl
0x14006d768  mov     [rbp+57h+var_80], bl
0x14006d76b  mov     r10, rbx
0x14006d76e  mov     r9, rbx
0x14006d771  mov     r15d, ebx
0x14006d774  mov     r13b, bl
0x14006d777  mov     eax, r15d
0x14006d77a  mov     ecx, [rdx+rax*4+78h]
0x14006d77e  cmp     ecx, 80h
0x14006d784  jb      loc_14006D80A
0x14006d78a  mov     r14d, [rdx+10h]
  ... truncated ...
```
