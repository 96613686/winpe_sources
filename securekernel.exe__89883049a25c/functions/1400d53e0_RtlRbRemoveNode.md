# RtlRbRemoveNode

- ea: `0x1400d53e0`
- end: `0x1400d5ec1`
- name: `RtlRbRemoveNode`
- size: `2785`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140035e8c`
- `0x140085bf8`
- `0x14009a8b0`
- `0x1400c96e8`
- `0x1400c9fe8`
- `0x1400cbae4`
- `0x1400d0abc`
- `0x1400d1958`
- `0x1400d2dc8`

## callees

- `0x1400d53e0`
- `0x1400d5ec8`

## pseudocode

```c
char __fastcall RtlRbRemoveNode(unsigned __int64 a1, __int64 *a2)
{
  char v2; // al
  __int64 v4; // rbx
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  char v10; // al
  bool v11; // zf
  unsigned __int64 v12; // rax
  unsigned __int64 *v13; // r12
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  char v23; // r13
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // r14
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  char v28; // dl
  __int64 v29; // rax
  __int64 *v30; // rcx
  __int64 v31; // rax
  unsigned __int64 *v32; // r12
  __int64 *v33; // rcx
  unsigned __int64 v34; // r14
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // r14
  __int64 v37; // rdx
  __int64 *v38; // rcx
  __int64 *v39; // rdx
  __int64 *v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rcx
  unsigned int v44; // ebp
  unsigned __int64 v45; // rcx
  char v46; // cl
  __int64 v47; // r13
  __int64 v48; // r9
  unsigned __int64 v49; // rbx
  unsigned __int64 *v50; // r12
  __int64 v51; // rax
  unsigned __int64 v52; // rax
  int v53; // r15d
  unsigned __int64 v54; // rcx
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // r14
  __int64 v57; // rcx
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // rax
  unsigned __int64 v60; // rax
  unsigned __int64 v61; // rcx
  unsigned __int64 v62; // rax
  unsigned __int64 *v63; // r14
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rbp
  __int64 v66; // rdx
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rax
  __int64 *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rax
  char v73; // r8
  char v74; // cl
  __int64 v75; // rax
  char v76; // al
  __int64 v77; // rdx
  unsigned __int64 v78; // rcx
  unsigned __int64 v79; // rdx
  char v80; // r8
  unsigned __int64 v81; // r14
  __int64 v82; // rbp
  unsigned __int64 v83; // rax
  int v84; // r15d
  unsigned __int64 v85; // rcx
  __int64 v86; // r13
  __int64 v87; // r12
  __int64 v88; // rcx
  unsigned __int64 v89; // rcx
  unsigned __int64 v90; // rcx
  unsigned __int64 v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rbp
  __int64 v94; // rdx
  unsigned __int64 v95; // rax
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rax
  unsigned __int64 v98; // rcx
  __int64 v99; // rax
  char v100; // r15
  unsigned __int64 v101; // rcx
  int v102; // r15d
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // r14
  __int64 v105; // rcx
  unsigned __int64 v106; // rax
  unsigned __int64 v107; // rax
  unsigned __int64 v108; // rax
  unsigned __int64 v109; // rcx
  unsigned __int64 v110; // rax
  unsigned __int64 *v111; // r14
  unsigned __int64 v112; // rbp
  __int64 v113; // rax
  unsigned __int64 v114; // rcx
  unsigned __int64 v115; // r9
  unsigned __int64 v116; // rcx
  unsigned int v118; // [rsp+70h] [rbp+8h]
  __int64 v119; // [rsp+78h] [rbp+10h] BYREF
  __int64 v120; // [rsp+80h] [rbp+18h]
  __int64 v121; // [rsp+88h] [rbp+20h]

  v2 = *(_BYTE *)(a1 + 8);
  v4 = *a2;
  v119 = 0;
  if ( (v2 & 1) != 0 && v4 )
    v4 ^= (unsigned __int64)a2;
  v6 = a2[1];
  if ( (v2 & 1) != 0 && v6 )
    v6 ^= (unsigned __int64)a2;
  if ( !v4 )
  {
    v4 = v6;
    goto LABEL_80;
  }
  if ( v6 )
  {
    v7 = v6;
    v118 = 1;
    v8 = v6;
    v9 = *(_QWORD *)v6;
    v10 = v2 & 1;
    while ( v9 )
    {
      v8 = v7;
      if ( v10 )
        v7 ^= v9;
      else
        v7 = v9;
      v118 = 0;
      v9 = *(_QWORD *)v7;
    }
    v11 = v10 == 0;
    v12 = v4;
    if ( !v11 )
      v12 = v7 ^ v4;
    *(_QWORD *)v7 = v12;
    v13 = (unsigned __int64 *)(v4 + 16);
    v14 = *(_QWORD *)(v4 + 16);
    v15 = v14 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v15 )
      v15 ^= v4;
    if ( (__int64 *)v15 != a2 )
      RtlpRbReportFatalError(v15, a2, v4);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      v16 = v7 ^ v4;
    else
      v16 = v7;
    *v13 = v16 | v14 & 3;
    v17 = *(_QWORD *)(v6 + 16);
    v18 = v17 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v18 )
      v18 ^= v6;
    if ( (__int64 *)v18 != a2 )
      RtlpRbReportFatalError(v18, a2, v6);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      v19 = v7 ^ v6;
    else
      v19 = v7;
    v20 = v7 ^ v6;
    *(_QWORD *)(v6 + 16) = v19 | v17 & 3;
    v4 = *(_QWORD *)(v7 + 8);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v4 )
    {
      v4 ^= v7;
    }
    else if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
    {
      v20 = v6;
    }
    *(_QWORD *)(v7 + 8) = v20;
    v21 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v21 )
      v21 ^= v7;
    if ( v21 != v8 && (v21 || v8 != v7) )
      RtlpRbReportFatalError(v21, v8, v7);
    v22 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    v23 = *(_BYTE *)(v7 + 16);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v22 )
    {
      v22 ^= (unsigned __int64)a2;
    }
    else if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
    {
LABEL_52:
      v24 = v22 | *(_DWORD *)(v7 + 16) & 3;
      *(_QWORD *)(v7 + 16) = v24;
      *(_BYTE *)(v7 + 16) = v24 ^ (*((_BYTE *)a2 + 16) ^ v24) & 1;
      v25 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v25 )
      {
        v28 = *(_BYTE *)(a1 + 8) & 1;
        if ( v28 )
          v25 ^= (unsigned __int64)a2;
        v29 = *(_QWORD *)(v25 + 8);
        if ( v28 && v29 )
          v30 = (__int64 *)(v29 ^ v25);
        else
          v30 = *(__int64 **)(v25 + 8);
        v31 = 0;
        if ( v30 == a2 )
          v31 = 8;
        v32 = (unsigned __int64 *)(v31 + v25);
        v27 = *(_QWORD *)(v31 + v25);
        if ( v28 && v27 )
          v33 = (__int64 *)(v27 ^ v25);
        else
          v33 = (__int64 *)v27;
        if ( v33 != a2 )
          RtlpRbReportFatalError(v33, a2, v25);
        if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
          v34 = v7 ^ v25;
        else
          v34 = v7;
        *v32 = v34;
      }
      else
      {
        v26 = *(_QWORD *)a1;
        if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v26 )
          v26 ^= a1;
        if ( (__int64 *)v26 != a2 )
          RtlpRbReportFatalError(v26, a2, a1);
        v27 = v7;
        if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
          v27 = a1 ^ v7;
        *(_QWORD *)a1 = v27;
      }
      goto LABEL_124;
    }
    if ( v22 )
      v22 ^= v7;
    goto LABEL_52;
  }
  v6 = v4;
LABEL_80:
  v8 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
  LOBYTE(v27) = v2 & 1;
  if ( (_BYTE)v27 )
  {
    if ( !v8 )
    {
LABEL_84:
      if ( v4 )
        *(_QWORD *)(v4 + 16) = 0;
      v35 = *(_QWORD *)a1;
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v35 )
        v35 ^= a1;
      if ( (__int64 *)v35 != a2 )
        RtlpRbReportFatalError(v35, a2, a1);
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      {
        v36 = a1 ^ v4;
        v27 = -v4;
        *(_QWORD *)(a1 + 8) = (a1 ^ v4) & -(__int64)(v4 != 0);
        *(_BYTE *)(a1 + 8) |= 1u;
      }
      else
      {
        *(_QWORD *)(a1 + 8) = v4;
        v36 = a1 ^ v6;
      }
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
        v4 = v36 & -(__int64)(v4 != 0);
      *(_QWORD *)a1 = v4;
      return v27;
    }
    v8 ^= (unsigned __int64)a2;
  }
  if ( !v8 )
    goto LABEL_84;
  v37 = *(_QWORD *)(v8 + 8);
  v7 = (unsigned __int64)a2;
  if ( (_BYTE)v27 && v37 )
    v38 = (__int64 *)(v37 ^ v8);
  else
    v38 = *(__int64 **)(v8 + 8);
  if ( v38 != a2 )
  {
    v39 = *(__int64 **)v8;
    if ( (_BYTE)v27 && v39 )
      v40 = (__int64 *)((unsigned __int64)v39 ^ v8);
    else
      v40 = *(__int64 **)v8;
    if ( v40 != a2 )
      RtlpRbReportFatalError(v40, a2, v8);
    v118 = 0;
    v41 = *(_QWORD *)(a1 + 8);
    if ( (v41 & 1) != 0 )
    {
      if ( v41 == 1 )
        v27 = 0;
      else
        v27 = v41 ^ (a1 | 1);
    }
    else
    {
      v27 = *(_QWORD *)(a1 + 8);
    }
    if ( (__int64 *)v27 != a2 )
      goto LABEL_123;
    LOBYTE(v27) = *(_BYTE *)(a1 + 8) & 1;
    if ( v4 )
    {
      if ( !(_BYTE)v27 )
      {
        *(_QWORD *)(a1 + 8) = v4;
        goto LABEL_123;
      }
      v42 = v4;
    }
    else
    {
      if ( !(_BYTE)v27 )
      {
        *(_QWORD *)(a1 + 8) = v8;
        goto LABEL_123;
      }
      v42 = v8;
    }
    v27 = a1 ^ v42;
    *(_QWORD *)(a1 + 8) = v27;
    *(_BYTE *)(a1 + 8) |= 1u;
    goto LABEL_123;
  }
  v118 = 1;
LABEL_123:
  v23 = *((_BYTE *)a2 + 16);
LABEL_124:
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v4 )
    v43 = v4 ^ v8;
  else
    v43 = v4;
  v44 = v118;
  *(_QWORD *)(v8 + 8LL * v118) = v43;
  if ( v4 )
  {
    v45 = *(_QWORD *)(v4 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v45 )
      v45 ^= v4;
    if ( v45 != v7 )
      RtlpRbReportFatalError(v45, v7, v4);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v8 )
      v8 ^= v4;
    *(_QWORD *)(v4 + 16) = v8;
    return v27;
  }
  if ( (v23 & 1) != 0 )
    return v27;
  while ( 1 )
  {
    v46 = *(_BYTE *)(a1 + 8);
    v47 = v44 ^ 1LL;
    v48 = v44;
    v120 = v44;
    v121 = v47;
    v49 = *(_QWORD *)(v8 + 8 * v47);
    if ( (v46 & 1) != 0 && v49 )
      v49 ^= v8;
    v50 = (unsigned __int64 *)(v49 + 16);
    if ( (*(_BYTE *)(v49 + 16) & 1) != 0 )
    {
      v51 = *(_QWORD *)a1;
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v51 )
        v51 ^= a1;
      v119 = v51;
      v52 = *v50 & 0xFFFFFFFFFFFFFFFCuLL;
      v53 = v46 & 1;
      if ( (v46 & 1) != 0 && v52 )
        v54 = v52 ^ v49;
      else
        v54 = *v50 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v54 != v8 )
        RtlpRbReportFatalError(v54, v8, v49);
      v55 = *(_QWORD *)(v8 + 8 * v47);
      if ( v53 && v55 )
        v55 ^= v8;
      if ( v55 != v49 )
        RtlpRbReportFatalError(v55, v49, v8);
      v56 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v53 )
      {
        if ( !v56 )
          goto LABEL_161;
        v56 ^= v8;
      }
      if ( v56 )
      {
        v57 = *(_QWORD *)(v56 + 8);
        if ( v53 && v57 )
          v58 = v57 ^ v56;
        else
          v58 = *(_QWORD *)(v56 + 8);
        if ( v58 == v8 )
        {
          if ( v53 )
            v59 = v49 ^ v56;
          else
            v59 = v49;
          *(_QWORD *)(v56 + 8) = v59;
        }
        else
        {
          v60 = *(_QWORD *)v56;
          if ( v53 && v60 )
            v61 = v60 ^ v56;
          else
            v61 = *(_QWORD *)v56;
          if ( v61 != v8 )
            RtlpRbReportFatalError(v61, v8, v56);
          if ( v53 )
            v62 = v49 ^ v56;
          else
            v62 = v49;
          *(_QWORD *)v56 = v62;
        }
        goto LABEL_183;
      }
LABEL_161:
      if ( v119 != v8 )
        RtlpRbReportFatalError(v119, v8, &v119);
      v119 = v49;
LABEL_183:
      if ( v53 && v56 )
        v56 ^= v49;
      v48 = v120;
      *v50 = v56 | *(_DWORD *)v50 & 3;
      v63 = (unsigned __int64 *)(v49 + 8 * v48);
      v64 = *v63;
      if ( v53 && v64 )
        v65 = v64 ^ v49;
      else
        v65 = *v63;
      if ( v65 )
      {
        v66 = *(_QWORD *)(v65 + 16);
        v67 = v66 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v53 && v67 )
          v68 = v67 ^ v65;
        else
          v68 = *(_QWORD *)(v65 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v68 != v49 )
          RtlpRbReportFatalError(v68, v49, v65);
        if ( v53 )
          v69 = v8 ^ v65;
        else
          v69 = v8;
        *(_QWORD *)(v65 + 16) = v69 | v66 & 3;
      }
      if ( v53 && v65 )
        v65 ^= v8;
      *(_QWORD *)(v8 + 8 * v47) = v65;
      if ( v53 )
      {
        v49 ^= v8;
        *v63 = v49;
      }
      else
      {
        *v63 = v8;
      }
      *(_QWORD *)(v8 + 16) = v49 | *(_DWORD *)(v8 + 16) & 3;
      v70 = (__int64 *)a1;
      v71 = v119;
      if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
      {
        v71 = (v119 ^ a1) & -(__int64)(v119 != 0);
        v70 = (__int64 *)a1;
      }
      *v70 = v71;
      *(_BYTE *)v50 &= ~1u;
      *(_BYTE *)(v8 + 16) |= 1u;
      v46 = *(_BYTE *)(a1 + 8);
      v49 = *(_QWORD *)(v8 + 8 * v47);
      if ( (v46 & 1) != 0 && v49 )
        v49 ^= v8;
      v44 = v118;
    }
    v72 = *(_QWORD *)v49;
    v73 = v46;
    v74 = v46 & 1;
    if ( *(_QWORD *)v49 )
    {
      if ( v74 )
        v72 ^= v49;
      if ( (*(_BYTE *)(v72 + 16) & 1) != 0 )
        break;
    }
    v75 = *(_QWORD *)(v49 + 8);
    if ( v75 )
    {
      if ( v74 )
        v75 ^= v49;
      if ( (*(_BYTE *)(v75 + 16) & 1) != 0 )
        break;
    }
    v76 = *(_BYTE *)(v8 + 16);
    if ( (v76 & 1) != 0 )
    {
      LOBYTE(v27) = v76 & 0xFE;
      *(_BYTE *)(v8 + 16) = v27;
      *(_BYTE *)(v49 + 16) |= 1u;
      return v27;
    }
    *(_BYTE *)(v49 + 16) |= 1u;
    v27 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
    {
      if ( !v27 )
        return v27;
      v27 ^= v8;
    }
    if ( !v27 )
      return v27;
    v77 = *(_QWORD *)(v27 + 8);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v77 )
      v78 = v77 ^ v27;
    else
      v78 = *(_QWORD *)(v27 + 8);
    v11 = v78 == v8;
    v8 = v27;
    v44 = v11;
    v118 = v11;
  }
  v79 = *(_QWORD *)(v49 + 8 * v47);
  v80 = v73 & 1;
  if ( v80 )
  {
    if ( v79 )
    {
      v79 ^= v49;
      goto LABEL_234;
    }
LABEL_236:
    v81 = *(_QWORD *)(v49 + 8 * v48);
    if ( v80 && v81 )
      v81 ^= v49;
    *(_BYTE *)(v81 + 16) &= ~1u;
    v82 = v44 ^ 1;
    v83 = *(_QWORD *)(v81 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    v84 = *(_BYTE *)(a1 + 8) & 1;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v83 )
      v85 = v83 ^ v81;
    else
      v85 = *(_QWORD *)(v81 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v85 != v49 )
      RtlpRbReportFatalError(v85, v49, v81);
    v86 = (unsigned int)v82 ^ 1LL;
    v87 = (unsigned int)v82;
    v88 = *(_QWORD *)(v49 + 8 * v86);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v88 )
      v88 ^= v49;
    if ( v88 != v81 )
      RtlpRbReportFatalError(v88, v81, v49);
    v89 = *(_QWORD *)(v8 + 8 * v82);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v89 )
      v89 ^= v8;
    if ( v89 != v49 )
      RtlpRbReportFatalError(v89, v49, v8);
    v90 = *(_QWORD *)(v49 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v90 )
      v90 ^= v49;
    if ( v90 != v8 )
      RtlpRbReportFatalError(v90, v8, v49);
    if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
    {
      v91 = v8 ^ v81;
      *(_QWORD *)(v8 + 8 * v82) = v8 ^ v81;
      if ( v8 )
        goto LABEL_265;
    }
    else
    {
      *(_QWORD *)(v8 + 8 * v82) = v81;
    }
    v91 = v8;
LABEL_265:
    *(_QWORD *)(v81 + 16) = v91 | *(_DWORD *)(v81 + 16) & 3;
    v92 = *(_QWORD *)(v81 + 8 * v82);
    if ( v84 && v92 )
      v93 = v92 ^ v81;
    else
      v93 = *(_QWORD *)(v81 + 8 * v82);
    if ( v93 )
    {
      v94 = *(_QWORD *)(v93 + 16);
      v95 = v94 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v84 && v95 )
        v96 = v95 ^ v93;
      else
        v96 = *(_QWORD *)(v93 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v96 != v81 )
        RtlpRbReportFatalError(v96, v81, v93);
      if ( v84 )
        v97 = v49 ^ v93;
      else
        v97 = v49;
      *(_QWORD *)(v93 + 16) = v97 | v94 & 3;
    }
    if ( v84 && v93 )
      v93 ^= v49;
    *(_QWORD *)(v49 + 8 * v86) = v93;
    v98 = v81;
    if ( v84 )
    {
      v98 = v49 ^ v81;
      *(_QWORD *)(v81 + 8 * v87) = v49 ^ v81;
    }
    else
    {
      *(_QWORD *)(v81 + 8 * v87) = v49;
    }
    v79 = v49;
    v47 = v121;
    *(_QWORD *)(v49 + 16) = v98 | *(_DWORD *)(v49 + 16) & 3;
    v49 = v81;
  }
  else
  {
LABEL_234:
    if ( !v79 || (*(_BYTE *)(v79 + 16) & 1) == 0 )
      goto LABEL_236;
  }
  *(_BYTE *)(v49 + 16) ^= (*(_BYTE *)(v8 + 16) ^ *(_BYTE *)(v49 + 16)) & 1;
  *(_BYTE *)(v8 + 16) &= ~1u;
  *(_BYTE *)(v79 + 16) &= ~1u;
  v99 = *(_QWORD *)a1;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 && v99 )
    v99 ^= a1;
  v100 = *(_BYTE *)(a1 + 8);
  v119 = v99;
  v101 = *(_QWORD *)(v49 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  v102 = v100 & 1;
  if ( v102 && v101 )
    v101 ^= v49;
  if ( v101 != v8 )
    RtlpRbReportFatalError(v101, v8, v49);
  v103 = *(_QWORD *)(v8 + 8 * v47);
  if ( v102 && v103 )
    v103 ^= v8;
  if ( v103 != v49 )
    RtlpRbReportFatalError(v103, v49, v8);
  v104 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v102 )
  {
    if ( v104 )
    {
      v104 ^= v8;
      goto LABEL_303;
    }
LABEL_304:
    if ( v119 != v8 )
      RtlpRbReportFatalError(v119, v8, &v119);
    v119 = v49;
  }
  else
  {
LABEL_303:
    if ( !v104 )
      goto LABEL_304;
    v105 = *(_QWORD *)(v104 + 8);
    if ( v102 && v105 )
      v106 = v105 ^ v104;
    else
      v106 = *(_QWORD *)(v104 + 8);
    if ( v106 == v8 )
    {
      if ( v102 )
        v107 = v49 ^ v104;
      else
        v107 = v49;
      *(_QWORD *)(v104 + 8) = v107;
    }
    else
    {
      v108 = *(_QWORD *)v104;
      if ( v102 && v108 )
        v109 = v108 ^ v104;
      else
        v109 = *(_QWORD *)v104;
      if ( v109 != v8 )
        RtlpRbReportFatalError(v109, v8, v104);
      if ( v102 )
        v110 = v49 ^ v104;
      else
        v110 = v49;
      *(_QWORD *)v104 = v110;
    }
  }
  if ( v102 && v104 )
    v104 ^= v49;
  *(_QWORD *)(v49 + 16) = v104 | *(_DWORD *)(v49 + 16) & 3;
  v111 = (unsigned __int64 *)(v49 + 8 * v120);
  v112 = *v111;
  if ( v102 )
  {
    if ( v112 )
    {
      v112 ^= v49;
      goto LABEL_332;
    }
  }
  else
  {
LABEL_332:
    if ( v112 )
    {
      v113 = *(_QWORD *)(v112 + 16);
      v114 = v113 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v102 && v114 )
        v115 = v114 ^ v112;
      else
        v115 = *(_QWORD *)(v112 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v115 != v49 )
        RtlpRbReportFatalError(v115, v49, v112);
      if ( v102 )
        v116 = v8 ^ v112;
      else
        v116 = v8;
      *(_QWORD *)(v112 + 16) = v116 | v113 & 3;
    }
  }
  if ( v102 && v112 )
    v112 ^= v8;
  *(_QWORD *)(v8 + 8 * v47) = v112;
  if ( v102 )
  {
    v49 ^= v8;
    *v111 = v49;
  }
  else
  {
    *v111 = v8;
  }
  v27 = v49 | *(_DWORD *)(v8 + 16) & 3;
  *(_QWORD *)(v8 + 16) = v27;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
  {
    v27 = (v119 ^ a1) & -(__int64)(v119 != 0);
    *(_QWORD *)a1 = v27;
  }
  else
  {
    *(_QWORD *)a1 = v119;
  }
  return v27;
}

```

## disassembly

```asm
0x1400d53e0  push    rbx
0x1400d53e2  push    rbp
0x1400d53e3  push    rsi
0x1400d53e4  push    rdi
0x1400d53e5  push    r12
0x1400d53e7  push    r13
0x1400d53e9  push    r14
0x1400d53eb  push    r15
0x1400d53ed  sub     rsp, 28h
0x1400d53f1  movzx   eax, byte ptr [rcx+8]
0x1400d53f5  mov     rsi, rcx
0x1400d53f8  mov     rbx, [rdx]
0x1400d53fb  mov     ecx, eax
0x1400d53fd  mov     [rsp+68h+arg_8], 0
0x1400d5406  mov     rbp, rdx
0x1400d5409  and     ecx, 1
0x1400d540c  jz      short loc_1400D5416
0x1400d540e  test    rbx, rbx
0x1400d5411  jz      short loc_1400D5416
0x1400d5413  xor     rbx, rdx
0x1400d5416  mov     r14, [rdx+8]
0x1400d541a  test    ecx, ecx
0x1400d541c  jz      short loc_1400D5426
0x1400d541e  test    r14, r14
0x1400d5421  jz      short loc_1400D5426
0x1400d5423  xor     r14, rbp
0x1400d5426  test    rbx, rbx
0x1400d5429  jnz     short loc_1400D5433
0x1400d542b  mov     rbx, r14
0x1400d542e  jmp     loc_1400D5665
0x1400d5433  test    r14, r14
0x1400d5436  jz      loc_1400D5662
0x1400d543c  mov     ecx, 1
0x1400d5441  mov     r15, r14
0x1400d5444  mov     [rsp+68h+arg_0], ecx
0x1400d5448  mov     rdi, r14
0x1400d544b  mov     rcx, [r14]
0x1400d544e  and     al, 1
0x1400d5450  test    rcx, rcx
0x1400d5453  jz      short loc_1400D5474
0x1400d5455  mov     rdi, r15
0x1400d5458  test    al, al
0x1400d545a  jz      short loc_1400D5466
0x1400d545c  test    rcx, rcx
0x1400d545f  jz      short loc_1400D5466
0x1400d5461  xor     r15, rcx
0x1400d5464  jmp     short loc_1400D5469
0x1400d5466  mov     r15, rcx
0x1400d5469  xor     ecx, ecx
0x1400d546b  mov     [rsp+68h+arg_0], ecx
0x1400d546f  mov     rcx, [r15]
0x1400d5472  jmp     short loc_1400D5450
0x1400d5474  test    al, al
0x1400d5476  mov     rax, rbx
0x1400d5479  jz      short loc_1400D547E
0x1400d547b  xor     rax, r15
0x1400d547e  mov     [r15], rax
0x1400d5481  lea     r12, [rbx+10h]
0x1400d5485  mov     rdx, [r12]
0x1400d5489  mov     rcx, rdx
0x1400d548c  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400d5490  test    byte ptr [rsi+8], 1
0x1400d5494  jz      short loc_1400D549E
0x1400d5496  test    rcx, rcx
0x1400d5499  jz      short loc_1400D549E
0x1400d549b  xor     rcx, rbx
0x1400d549e  cmp     rcx, rbp
0x1400d54a1  jz      short loc_1400D54B2
0x1400d54a3  mov     r8, rbx
0x1400d54a6  mov     rdx, rbp
0x1400d54a9  call    RtlpRbReportFatalError
0x1400d54ae  mov     rdx, [r12]
0x1400d54b2  test    byte ptr [rsi+8], 1
0x1400d54b6  jz      short loc_1400D54BD
0x1400d54b8  xor     rbx, r15
0x1400d54bb  jmp     short loc_1400D54C0
0x1400d54bd  mov     rbx, r15
0x1400d54c0  and     edx, 3
0x1400d54c3  or      rdx, rbx
0x1400d54c6  mov     [r12], rdx
0x1400d54ca  mov     rdx, [r14+10h]
0x1400d54ce  mov     rcx, rdx
0x1400d54d1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400d54d5  test    byte ptr [rsi+8], 1
0x1400d54d9  jz      short loc_1400D54E3
0x1400d54db  test    rcx, rcx
0x1400d54de  jz      short loc_1400D54E3
0x1400d54e0  xor     rcx, r14
0x1400d54e3  cmp     rcx, rbp
0x1400d54e6  jz      short loc_1400D54F7
0x1400d54e8  mov     r8, r14
0x1400d54eb  mov     rdx, rbp
0x1400d54ee  call    RtlpRbReportFatalError
0x1400d54f3  mov     rdx, [r14+10h]
0x1400d54f7  test    byte ptr [rsi+8], 1
0x1400d54fb  jz      short loc_1400D5508
0x1400d54fd  mov     rax, r14
0x1400d5500  xor     rax, r15
0x1400d5503  mov     rcx, rax
0x1400d5506  jmp     short loc_1400D5511
0x1400d5508  mov     rcx, r14
0x1400d550b  mov     rax, r15
0x1400d550e  xor     rcx, r15
0x1400d5511  and     edx, 3
0x1400d5514  or      rdx, rax
0x1400d5517  mov     [r14+10h], rdx
0x1400d551b  mov     al, [rsi+8]
0x1400d551e  mov     rbx, [r15+8]
0x1400d5522  and     al, 1
0x1400d5524  jz      short loc_1400D5530
0x1400d5526  test    rbx, rbx
0x1400d5529  jz      short loc_1400D5530
0x1400d552b  xor     rbx, r15
0x1400d552e  jmp     short loc_1400D5537
0x1400d5530  test    al, al
0x1400d5532  jnz     short loc_1400D5537
0x1400d5534  mov     rcx, r14
0x1400d5537  mov     [r15+8], rcx
0x1400d553b  mov     rcx, [r15+10h]
0x1400d553f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400d5543  test    byte ptr [rsi+8], 1
0x1400d5547  jz      short loc_1400D5551
0x1400d5549  test    rcx, rcx
0x1400d554c  jz      short loc_1400D5551
0x1400d554e  xor     rcx, r15
0x1400d5551  cmp     rcx, rdi
0x1400d5554  jz      short loc_1400D556B
0x1400d5556  test    rcx, rcx
0x1400d5559  jnz     short loc_1400D5560
0x1400d555b  cmp     rdi, r15
0x1400d555e  jz      short loc_1400D556B
0x1400d5560  mov     r8, r15
0x1400d5563  mov     rdx, rdi
0x1400d5566  call    RtlpRbReportFatalError
0x1400d556b  mov     rcx, [rbp+10h]
0x1400d556f  mov     al, [rsi+8]
0x1400d5572  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400d5576  mov     r13b, [r15+10h]
0x1400d557a  and     al, 1
0x1400d557c  jz      short loc_1400D5588
0x1400d557e  test    rcx, rcx
0x1400d5581  jz      short loc_1400D5588
0x1400d5583  xor     rcx, rbp
0x1400d5586  jmp     short loc_1400D558C
0x1400d5588  test    al, al
0x1400d558a  jz      short loc_1400D5594
0x1400d558c  test    rcx, rcx
0x1400d558f  jz      short loc_1400D5594
0x1400d5591  xor     rcx, r15
0x1400d5594  mov     eax, [r15+10h]
0x1400d5598  and     eax, 3
0x1400d559b  or      rax, rcx
0x1400d559e  mov     [r15+10h], rax
0x1400d55a2  mov     cl, al
0x1400d55a4  xor     cl, [rbp+10h]
0x1400d55a7  and     cl, 1
0x1400d55aa  xor     cl, al
0x1400d55ac  mov     [r15+10h], cl
0x1400d55b0  mov     r14, [rbp+10h]
0x1400d55b4  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400d55b8  jnz     short loc_1400D55EF
0x1400d55ba  test    byte ptr [rsi+8], 1
0x1400d55be  mov     rcx, [rsi]
0x1400d55c1  jz      short loc_1400D55CB
0x1400d55c3  test    rcx, rcx
0x1400d55c6  jz      short loc_1400D55CB
0x1400d55c8  xor     rcx, rsi
0x1400d55cb  cmp     rcx, rbp
0x1400d55ce  jz      short loc_1400D55DB
0x1400d55d0  mov     r8, rsi
0x1400d55d3  mov     rdx, rbp
0x1400d55d6  call    RtlpRbReportFatalError
0x1400d55db  test    byte ptr [rsi+8], 1
0x1400d55df  mov     rax, r15
0x1400d55e2  jz      short loc_1400D55E7
0x1400d55e4  xor     rax, rsi
0x1400d55e7  mov     [rsi], rax
0x1400d55ea  jmp     loc_1400D57A0
0x1400d55ef  mov     dl, [rsi+8]
0x1400d55f2  and     dl, 1
0x1400d55f5  jz      short loc_1400D55FA
0x1400d55f7  xor     r14, rbp
0x1400d55fa  mov     rax, [r14+8]
0x1400d55fe  test    dl, dl
0x1400d5600  jz      short loc_1400D560F
0x1400d5602  test    rax, rax
0x1400d5605  jz      short loc_1400D560F
0x1400d5607  mov     rcx, r14
0x1400d560a  xor     rcx, rax
0x1400d560d  jmp     short loc_1400D5612
0x1400d560f  mov     rcx, rax
0x1400d5612  xor     eax, eax
0x1400d5614  cmp     rcx, rbp
0x1400d5617  lea     r8d, [rax+8]
0x1400d561b  cmovz   eax, r8d
0x1400d561f  lea     r12, [rax+r14]
0x1400d5623  mov     rax, [r12]
0x1400d5627  test    dl, dl
0x1400d5629  jz      short loc_1400D5638
0x1400d562b  test    rax, rax
0x1400d562e  jz      short loc_1400D5638
0x1400d5630  mov     rcx, r14
0x1400d5633  xor     rcx, rax
0x1400d5636  jmp     short loc_1400D563B
0x1400d5638  mov     rcx, rax
0x1400d563b  cmp     rcx, rbp
0x1400d563e  jz      short loc_1400D564B
0x1400d5640  mov     r8, r14
0x1400d5643  mov     rdx, rbp
0x1400d5646  call    RtlpRbReportFatalError
0x1400d564b  test    byte ptr [rsi+8], 1
0x1400d564f  jz      short loc_1400D5656
0x1400d5651  xor     r14, r15
0x1400d5654  jmp     short loc_1400D5659
0x1400d5656  mov     r14, r15
0x1400d5659  mov     [r12], r14
0x1400d565d  jmp     loc_1400D57A0
0x1400d5662  mov     r14, rbx
0x1400d5665  mov     rdi, [rdx+10h]
0x1400d5669  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400d566d  and     al, 1
0x1400d566f  jz      short loc_1400D5679
0x1400d5671  test    rdi, rdi
0x1400d5674  jz      short loc_1400D567E
0x1400d5676  xor     rdi, rbp
0x1400d5679  test    rdi, rdi
0x1400d567c  jnz     short loc_1400D56E9
0x1400d567e  test    rbx, rbx
0x1400d5681  jz      short loc_1400D568B
0x1400d5683  mov     qword ptr [rbx+10h], 0
0x1400d568b  test    byte ptr [rsi+8], 1
0x1400d568f  mov     rcx, [rsi]
0x1400d5692  jz      short loc_1400D569C
0x1400d5694  test    rcx, rcx
0x1400d5697  jz      short loc_1400D569C
0x1400d5699  xor     rcx, rsi
0x1400d569c  cmp     rcx, rbp
0x1400d569f  jz      short loc_1400D56A9
0x1400d56a1  mov     r8, rsi
0x1400d56a4  call    RtlpRbReportFatalError
0x1400d56a9  test    byte ptr [rsi+8], 1
0x1400d56ad  jz      short loc_1400D56CB
0x1400d56af  mov     r14, rbx
0x1400d56b2  mov     rax, rbx
0x1400d56b5  xor     r14, rsi
0x1400d56b8  neg     rax
0x1400d56bb  sbb     rcx, rcx
0x1400d56be  and     rcx, r14
0x1400d56c1  mov     [rsi+8], rcx
0x1400d56c5  or      byte ptr [rsi+8], 1
0x1400d56c9  jmp     short loc_1400D56D2
0x1400d56cb  mov     [rsi+8], rbx
0x1400d56cf  xor     r14, rsi
0x1400d56d2  test    byte ptr [rsi+8], 1
0x1400d56d6  jz      short loc_1400D56E1
0x1400d56d8  neg     rbx
0x1400d56db  sbb     rbx, rbx
0x1400d56de  and     rbx, r14
0x1400d56e1  mov     [rsi], rbx
0x1400d56e4  jmp     loc_1400D5EAF
0x1400d56e9  mov     rdx, [rdi+8]
0x1400d56ed  mov     r15, rbp
0x1400d56f0  test    al, al
0x1400d56f2  jz      short loc_1400D5701
0x1400d56f4  test    rdx, rdx
0x1400d56f7  jz      short loc_1400D5701
0x1400d56f9  mov     rcx, rdi
0x1400d56fc  xor     rcx, rdx
0x1400d56ff  jmp     short loc_1400D5704
0x1400d5701  mov     rcx, rdx
0x1400d5704  cmp     rcx, rbp
0x1400d5707  jnz     short loc_1400D5717
0x1400d5709  mov     ecx, 1
0x1400d570e  mov     [rsp+68h+arg_0], ecx
0x1400d5712  jmp     loc_1400D579C
0x1400d5717  mov     rdx, [rdi]
0x1400d571a  test    al, al
0x1400d571c  jz      short loc_1400D572B
0x1400d571e  test    rdx, rdx
0x1400d5721  jz      short loc_1400D572B
0x1400d5723  mov     rcx, rdi
0x1400d5726  xor     rcx, rdx
0x1400d5729  jmp     short loc_1400D572E
0x1400d572b  mov     rcx, rdx
0x1400d572e  cmp     rcx, rbp
0x1400d5731  jz      short loc_1400D573E
0x1400d5733  mov     r8, rdi
0x1400d5736  mov     rdx, rbp
0x1400d5739  call    RtlpRbReportFatalError
0x1400d573e  xor     ecx, ecx
0x1400d5740  mov     [rsp+68h+arg_0], ecx
0x1400d5744  mov     rcx, [rsi+8]
0x1400d5748  test    cl, 1
0x1400d574b  jz      short loc_1400D5763
0x1400d574d  cmp     rcx, 1
0x1400d5751  jnz     short loc_1400D5757
0x1400d5753  xor     eax, eax
0x1400d5755  jmp     short loc_1400D5766
0x1400d5757  mov     rax, rsi
0x1400d575a  or      rax, 1
  ... truncated ...
```
