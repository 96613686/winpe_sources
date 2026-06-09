# Duplicate802_11AttachAttributesCommon

- ea: `0x140001474`
- end: `0x140002007`
- name: `Duplicate802_11AttachAttributesCommon`
- size: `2963`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, char, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000317c`
- `0x14000d3a0`

## callees

- `0x140001474`
- `0x140002010`
- `0x14000c9e8`
- `0x14000cca8`
- `0x14000f200`
- `0x14000f500`

## pseudocode

```c
__int64 __fastcall Duplicate802_11AttachAttributesCommon(
        __int16 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6,
        char a7,
        size_t Size,
        void **a9)
{
  char v10; // al
  unsigned int v11; // r11d
  __int64 v12; // rcx
  unsigned int v13; // ebx
  unsigned int v14; // edi
  unsigned int v15; // r10d
  __int64 v16; // rsi
  __int64 v17; // rcx
  int v18; // r10d
  unsigned int v19; // r10d
  __int64 v20; // rcx
  unsigned int v21; // r10d
  __int64 v22; // rcx
  unsigned int v23; // r10d
  __int64 v24; // rcx
  unsigned int v25; // r10d
  __int64 v26; // rcx
  unsigned int v27; // r10d
  __int64 v28; // rcx
  unsigned int v29; // r10d
  unsigned int v30; // eax
  __int64 v31; // r13
  int v32; // eax
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // r10d
  unsigned int v39; // r10d
  unsigned int v40; // eax
  size_t v41; // rcx
  unsigned int v42; // eax
  unsigned int v43; // eax
  size_t v44; // rcx
  unsigned int v45; // eax
  unsigned int v46; // eax
  __int64 v47; // r15
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  unsigned int v51; // r12d
  __int64 v52; // rcx
  unsigned int v53; // eax
  _DWORD *v54; // r12
  unsigned int v55; // ecx
  __int64 v56; // rbx
  _OWORD *v57; // rax
  unsigned int v58; // ecx
  _QWORD *v59; // r14
  char *v60; // rax
  __int64 v61; // rbx
  char *v62; // rax
  unsigned int v63; // ecx
  __int64 v64; // rbx
  char *v65; // rax
  unsigned int v66; // ecx
  __int64 v67; // rbx
  char *v68; // rax
  unsigned int v69; // ecx
  __int64 v70; // rbx
  char *v71; // rax
  unsigned int v72; // ecx
  __int64 v73; // rbx
  unsigned int v74; // ecx
  __int64 v75; // rbx
  __int64 v76; // rdx
  _QWORD *v77; // rcx
  char v78; // al
  size_t v79; // rsi
  _BYTE *v80; // r14
  _BYTE *v81; // rbx
  unsigned int v82; // r12d
  __int64 v83; // r15
  _OWORD *v84; // rax
  unsigned int v85; // ecx
  _QWORD *v86; // rsi
  char *v87; // rax
  __int64 v88; // rbx
  char *v89; // rax
  unsigned int v90; // ecx
  __int64 v91; // rbx
  char *v92; // rax
  unsigned int v93; // ecx
  __int64 v94; // rbx
  _OWORD *v95; // rax
  unsigned int v96; // ecx
  _QWORD *v97; // rsi
  char *v98; // rax
  __int64 v99; // rbx
  char *v100; // rax
  unsigned int v101; // ecx
  void *v103; // [rsp+28h] [rbp-71h] BYREF
  unsigned int v104; // [rsp+30h] [rbp-69h] BYREF
  size_t v105; // [rsp+34h] [rbp-65h] BYREF
  size_t v106; // [rsp+3Ch] [rbp-5Dh] BYREF
  unsigned int v107; // [rsp+44h] [rbp-55h] BYREF
  unsigned int v108; // [rsp+48h] [rbp-51h]
  size_t v109; // [rsp+4Ch] [rbp-4Dh] BYREF
  size_t v110; // [rsp+54h] [rbp-45h] BYREF
  __int64 v111; // [rsp+60h] [rbp-39h] BYREF
  __int64 v112; // [rsp+68h] [rbp-31h]
  __int64 v113; // [rsp+70h] [rbp-29h]
  size_t v114; // [rsp+78h] [rbp-21h]
  size_t v115; // [rsp+80h] [rbp-19h]
  _DWORD *v116; // [rsp+88h] [rbp-11h]
  int v117; // [rsp+E8h] [rbp+4Fh] BYREF
  int v118; // [rsp+F0h] [rbp+57h]
  int v119; // [rsp+F8h] [rbp+5Fh]
  int v120; // [rsp+FCh] [rbp+63h]
  int v121; // [rsp+100h] [rbp+67h]

  v120 = HIDWORD(a3);
  LOWORD(v117) = a1;
  LODWORD(Size) = 0;
  v121 = 0;
  v105 = 0;
  v106 = 0;
  v109 = 0;
  v107 = 0;
  v119 = 0;
  v104 = 0;
  LODWORD(v111) = 0;
  v118 = 0;
  v110 = 0;
  v103 = 0;
  if ( !a2 || !a9 || *(_BYTE *)a2 != 0xA1 )
    return (unsigned int)-1073741811;
  *a9 = 0;
  v10 = *(_BYTE *)(a2 + 1);
  if ( v10 == 1 )
  {
    if ( *(_WORD *)(a2 + 2) < 0x28u )
      return (unsigned int)-1073741811;
    v11 = 1;
  }
  else if ( v10 == 2 )
  {
    if ( *(_WORD *)(a2 + 2) < 0x38u )
      return (unsigned int)-1073741811;
    v11 = 2;
  }
  else
  {
    if ( v10 != 3 || *(_WORD *)(a2 + 2) < 0x40u )
      return (unsigned int)-1073741811;
    v11 = 3;
  }
  v12 = *(unsigned int *)(a2 + 20);
  v13 = 64;
  v117 = 64;
  v108 = v11;
  if ( (_DWORD)v12 && *(_QWORD *)(a2 + 24) )
  {
    v14 = PrivateULongMult(v12, 1092, &Size);
    if ( v14 )
      return v14;
    v14 = PrivateULongAdd(v15, (unsigned int)Size, &v117);
    if ( v14 )
      return v14;
    v13 = v117;
  }
  v16 = a6;
  if ( !a5 )
    v16 = *(_QWORD *)(a2 + 32);
  if ( v16 )
  {
    v17 = *(unsigned int *)(v16 + 48);
    v18 = 160;
    v121 = 160;
    v117 = 160;
    if ( (_DWORD)v17 && *(_QWORD *)(v16 + 56) )
    {
      v14 = PrivateULongMult(v17, 3, &v105);
      if ( v14 )
        return v14;
      v14 = PrivateULongAdd(v19, (unsigned int)v105, &v117);
      if ( v14 )
        return v14;
      v18 = v117;
      v121 = v117;
    }
    v20 = *(unsigned int *)(v16 + 64);
    if ( (_DWORD)v20 && *(_QWORD *)(v16 + 72) )
    {
      v14 = PrivateULongMult(v20, 8, (char *)&v105 + 4);
      if ( v14 )
        return v14;
      v14 = PrivateULongAdd(v21, HIDWORD(v105), &v117);
      if ( v14 )
        return v14;
      v18 = v117;
      v121 = v117;
    }
    v22 = *(unsigned int *)(v16 + 80);
    if ( (_DWORD)v22 && *(_QWORD *)(v16 + 88) )
    {
      v14 = PrivateULongMult(v22, 8, &v106);
      if ( v14 )
        return v14;
      v14 = PrivateULongAdd(v23, (unsigned int)v106, &v117);
      if ( v14 )
        return v14;
      v18 = v117;
      v121 = v117;
    }
    v24 = *(unsigned int *)(v16 + 96);
    if ( (_DWORD)v24 && *(_QWORD *)(v16 + 104) )
    {
      v14 = PrivateULongMult(v24, 8, (char *)&v106 + 4);
      if ( v14 )
        return v14;
      v14 = PrivateULongAdd(v25, HIDWORD(v106), &v117);
      if ( v14 )
        return v14;
      v18 = v117;
      v121 = v117;
    }
    v26 = *(unsigned int *)(v16 + 112);
    if ( (_DWORD)v26 && *(_QWORD *)(v16 + 120) )
    {
      v14 = PrivateULongMult(v26, 8, &v107);
      if ( v14 )
        return v14;
      v14 = PrivateULongAdd(v27, v107, &v117);
      if ( v14 )
        return v14;
      v18 = v117;
      v121 = v117;
    }
    if ( v11 >= 3 )
    {
      v28 = *(unsigned int *)(v16 + 140);
      if ( (_DWORD)v28 )
      {
        if ( *(_QWORD *)(v16 + 144) && *(_BYTE *)(v16 + 1) >= 3u )
        {
          v14 = PrivateULongMult(v28, 8, &v109);
          if ( v14 )
            return v14;
          v14 = PrivateULongAdd(v29, (unsigned int)v109, &v117);
          if ( v14 )
            return v14;
          v18 = v117;
          v121 = v117;
        }
      }
    }
    v30 = v13;
    v13 += v18;
    if ( v13 < v30 )
      return (unsigned int)-1073676267;
    v117 = v13;
  }
  if ( v11 < 2 )
  {
    v112 = 0;
    v31 = 0;
    v113 = 0;
    goto LABEL_72;
  }
  if ( a7 )
  {
    v31 = 0;
    v113 = 0;
  }
  else
  {
    v32 = *(_DWORD *)(a2 + 4);
    v31 = *(_QWORD *)(a2 + 48);
    v113 = v31;
    v33 = v32 & 0x28;
    if ( v33 && !v31 || v31 && !v33 )
      return (unsigned int)-1073741811;
  }
  v34 = *(_QWORD *)(a2 + 40);
  v112 = v34;
  if ( !v34 )
  {
LABEL_72:
    LODWORD(v114) = 0;
    LODWORD(v115) = 0;
    if ( v31 )
    {
      v37 = *(unsigned int *)(v31 + 32);
      v38 = 80;
      v119 = 80;
      v117 = 80;
      if ( (_DWORD)v37 && *(_QWORD *)(v31 + 40) )
      {
        v14 = PrivateULongMult(v37, 3, (char *)&v109 + 4);
        if ( v14 )
          return v14;
        v14 = PrivateULongAdd(v39, HIDWORD(v109), &v117);
        if ( v14 )
          return v14;
        v38 = v117;
        v119 = v117;
      }
      v40 = *(_DWORD *)(v31 + 48);
      if ( v40 )
      {
        if ( *(_QWORD *)(v31 + 56) )
        {
          v41 = 8LL * v40;
          v114 = v41;
          if ( v41 > 0xFFFFFFFF )
            return (unsigned int)-1073676267;
          v42 = v38;
          v38 += v41;
          v119 = v38;
          if ( v38 < v42 )
            return (unsigned int)-1073676267;
        }
      }
      v43 = *(_DWORD *)(v31 + 64);
      if ( v43 )
      {
        if ( *(_QWORD *)(v31 + 72) )
        {
          v44 = 8LL * v43;
          v115 = v44;
          if ( v44 > 0xFFFFFFFF )
            return (unsigned int)-1073676267;
          v45 = v38;
          v38 += v44;
          v119 = v38;
          if ( v38 < v45 )
            return (unsigned int)-1073676267;
        }
      }
      v46 = v13;
      v13 += v38;
      if ( v13 < v46 )
        return (unsigned int)-1073676267;
    }
    v111 = 0;
    v47 = 0;
    if ( v11 < 3 )
      goto LABEL_103;
    v48 = *(_DWORD *)(a2 + 4);
    v47 = *(_QWORD *)(a2 + 56);
    v111 = v47;
    v49 = v48 & 0x70;
    if ( v49 && !v47 )
      return (unsigned int)-1073741811;
    if ( !v47 )
    {
LABEL_103:
      v14 = AllocationFunction(&v103, v13, 1179014998);
      if ( !v14 )
      {
        memset(v103, 0, v13);
        v54 = v103;
        v55 = Size;
        v116 = v103;
        *a9 = v103;
        *(_OWORD *)v54 = *(_OWORD *)a2;
        v54[4] = *(_DWORD *)(a2 + 16);
        v103 = (char *)v103 + 64;
        *v54 = 4195233;
        if ( v55 && *(_DWORD *)(a2 + 20) )
        {
          v56 = v55;
          *((_QWORD *)v54 + 3) = v103;
          v54[5] = *(_DWORD *)(a2 + 20);
          memmove(v103, *(const void **)(a2 + 24), v55);
          v103 = (char *)v103 + v56;
        }
        else
        {
          *((_QWORD *)v54 + 3) = 0;
          v54[5] = 0;
        }
        if ( v121 && v16 )
        {
          v57 = v103;
          v58 = v105;
          *((_QWORD *)v54 + 4) = v103;
          v59 = v103;
          *v57 = *(_OWORD *)v16;
          v57[1] = *(_OWORD *)(v16 + 16);
          v57[2] = *(_OWORD *)(v16 + 32);
          v60 = (char *)v103 + 160;
          v103 = (char *)v103 + 160;
          if ( !v58 )
            goto LABEL_113;
          if ( *(_DWORD *)(v16 + 48) )
          {
            v59[7] = v60;
            v61 = v58;
            *((_DWORD *)v59 + 12) = *(_DWORD *)(v16 + 48);
            memmove(v103, *(const void **)(v16 + 56), v58);
            v62 = (char *)v103 + v61;
            v103 = (char *)v103 + v61;
          }
          else
          {
LABEL_113:
            v59[7] = 0;
            *((_DWORD *)v59 + 12) = 0;
            v62 = (char *)v103;
          }
          v63 = HIDWORD(v105);
          if ( HIDWORD(v105) && *(_DWORD *)(v16 + 64) )
          {
            v59[9] = v62;
            v64 = v63;
            *((_DWORD *)v59 + 16) = *(_DWORD *)(v16 + 64);
            memmove(v103, *(const void **)(v16 + 72), v63);
            v65 = (char *)v103 + v64;
            v103 = (char *)v103 + v64;
          }
          else
          {
            v59[9] = 0;
            *((_DWORD *)v59 + 16) = 0;
            v65 = (char *)v103;
          }
          v66 = v106;
          if ( (_DWORD)v106 && *(_DWORD *)(v16 + 80) )
          {
            v59[11] = v65;
            v67 = v66;
            *((_DWORD *)v59 + 20) = *(_DWORD *)(v16 + 80);
            memmove(v103, *(const void **)(v16 + 88), v66);
            v68 = (char *)v103 + v67;
            v103 = (char *)v103 + v67;
          }
          else
          {
            v59[11] = 0;
            *((_DWORD *)v59 + 20) = 0;
            v68 = (char *)v103;
          }
          v69 = HIDWORD(v106);
          if ( HIDWORD(v106) && *(_DWORD *)(v16 + 96) )
          {
            v59[13] = v68;
            v70 = v69;
            *((_DWORD *)v59 + 24) = *(_DWORD *)(v16 + 96);
            memmove(v103, *(const void **)(v16 + 104), v69);
            v71 = (char *)v103 + v70;
            v103 = (char *)v103 + v70;
          }
          else
          {
            v59[13] = 0;
            *((_DWORD *)v59 + 24) = 0;
            v71 = (char *)v103;
          }
          v72 = v107;
          if ( v107 && *(_DWORD *)(v16 + 112) )
          {
            v59[15] = v71;
            v73 = v72;
            *((_DWORD *)v59 + 28) = *(_DWORD *)(v16 + 112);
            memmove(v103, *(const void **)(v16 + 120), v72);
            v103 = (char *)v103 + v73;
          }
          else
          {
            v59[15] = 0;
            *((_DWORD *)v59 + 28) = 0;
          }
          if ( v108 >= 3 )
          {
            *(_BYTE *)(*((_QWORD *)v54 + 4) + 128LL) = *(_BYTE *)(v16 + 128);
            *(_DWORD *)(*((_QWORD *)v54 + 4) + 132LL) = *(_DWORD *)(v16 + 132);
            *(_BYTE *)(*((_QWORD *)v54 + 4) + 136LL) = *(_BYTE *)(v16 + 136);
            if ( *(_DWORD *)(v16 + 140) && *(_QWORD *)(v16 + 144) && *(_BYTE *)(v16 + 1) >= 3u )
            {
              v74 = v109;
              if ( (_DWORD)v109 )
              {
                v75 = (unsigned int)v109;
                v59[18] = v103;
                *((_DWORD *)v59 + 35) = *(_DWORD *)(v16 + 140);
                memmove(v103, *(const void **)(v16 + 144), v74);
                v103 = (char *)v103 + v75;
              }
              else
              {
                v59[18] = 0;
                *((_DWORD *)v59 + 35) = 0;
              }
            }
            if ( *(_BYTE *)(v16 + 1) >= 4u )
            {
              *(_BYTE *)(*((_QWORD *)v54 + 4) + 152LL) = *(_BYTE *)(v16 + 152);
              *(_BYTE *)(*((_QWORD *)v54 + 4) + 153LL) = *(_BYTE *)(v16 + 153);
              *(_BYTE *)(*((_QWORD *)v54 + 4) + 154LL) = *(_BYTE *)(v16 + 154);
              *(_BYTE *)(*((_QWORD *)v54 + 4) + 155LL) = *(_BYTE *)(v16 + 155);
              *(_BYTE *)(*((_QWORD *)v54 + 4) + 156LL) = *(_BYTE *)(v16 + 156);
            }
          }
        }
        if ( v104 )
        {
          v76 = v112;
          if ( v112 )
          {
            v77 = v103;
            *((_QWORD *)v54 + 5) = v103;
            *v77 = *(_QWORD *)v76;
            if ( *(_DWORD *)(v76 + 4) )
            {
              v78 = *(_BYTE *)(v76 + 9);
              if ( v78 == 3 )
              {
                v79 = 24;
              }
              else if ( v78 == 2 )
              {
                v79 = 20;
              }
              else
              {
                v79 = 0;
                if ( v78 == 1 )
                  v79 = 16;
              }
              v80 = (_BYTE *)(v76 + 8);
              v81 = (_BYTE *)(*((_QWORD *)v54 + 5) + 8LL);
              v82 = 0;
              v83 = v76;
              do
              {
                memmove(v81, v80, v79);
                ++v82;
                *v81 = *v80;
                v80 += v79;
                v81[1] = 3;
                *((_WORD *)v81 + 1) = 24;
                v81 += 24;
              }
              while ( v82 < *(_DWORD *)(v83 + 4) );
              v47 = v111;
              v31 = v113;
              v54 = v116;
            }
            v103 = (char *)v103 + v104;
          }
        }
        if ( v119 && v31 )
        {
          v84 = v103;
          v85 = HIDWORD(v109);
          *((_QWORD *)v54 + 6) = v103;
          v86 = v103;
          *v84 = *(_OWORD *)v31;
          v84[1] = *(_OWORD *)(v31 + 16);
          v87 = (char *)v103 + 80;
          v103 = (char *)v103 + 80;
          if ( v85 && *(_DWORD *)(v31 + 32) )
          {
            v86[5] = v87;
            v88 = v85;
            *((_DWORD *)v86 + 8) = *(_DWORD *)(v31 + 32);
            memmove(v103, *(const void **)(v31 + 40), v85);
            v89 = (char *)v103 + v88;
            v103 = (char *)v103 + v88;
          }
          else
          {
            v86[5] = 0;
            *((_DWORD *)v86 + 8) = 0;
            v89 = (char *)v103;
          }
          v90 = v114;
          if ( (_DWORD)v114 && *(_DWORD *)(v31 + 48) )
          {
            v86[7] = v89;
            *((_DWORD *)v86 + 12) = *(_DWORD *)(v31 + 48);
            v91 = v90;
            memmove(v103, *(const void **)(v31 + 56), v90);
            v92 = (char *)v103 + v91;
            v103 = (char *)v103 + v91;
          }
          else
          {
            v86[7] = 0;
            *((_DWORD *)v86 + 12) = 0;
            v92 = (char *)v103;
          }
          v93 = v115;
          if ( (_DWORD)v115 && *(_DWORD *)(v31 + 64) )
          {
            v86[9] = v92;
            *((_DWORD *)v86 + 16) = *(_DWORD *)(v31 + 64);
            v94 = v93;
            memmove(v103, *(const void **)(v31 + 72), v93);
            v103 = (char *)v103 + v94;
          }
          else
          {
            v86[9] = 0;
            *((_DWORD *)v86 + 16) = 0;
          }
        }
        if ( v118 && v47 )
        {
          v95 = v103;
          v96 = v110;
          *((_QWORD *)v54 + 7) = v103;
          v97 = v103;
          *v95 = *(_OWORD *)v47;
          v95[1] = *(_OWORD *)(v47 + 16);
          v95[2] = *(_OWORD *)(v47 + 32);
          v95[3] = *(_OWORD *)(v47 + 48);
          *((_QWORD *)v95 + 8) = *(_QWORD *)(v47 + 64);
          v98 = (char *)v103 + 72;
          v103 = (char *)v103 + 72;
          if ( v96 && *(_DWORD *)(v47 + 48) )
          {
            v97[7] = v98;
            v99 = v96;
            *((_DWORD *)v97 + 12) = *(_DWORD *)(v47 + 48);
            memmove(v103, *(const void **)(v47 + 56), v96);
            v100 = (char *)v103 + v99;
            v103 = (char *)v103 + v99;
          }
          else
          {
            v97[7] = 0;
            *((_DWORD *)v97 + 12) = 0;
            v100 = (char *)v103;
          }
          v101 = HIDWORD(v110);
          if ( HIDWORD(v110) && *(_DWORD *)(v47 + 32) )
          {
            v97[5] = v100;
            *((_DWORD *)v97 + 8) = *(_DWORD *)(v47 + 32);
            memmove(v103, *(const void **)(v47 + 40), v101);
          }
          else
          {
            v97[5] = 0;
            *((_DWORD *)v97 + 8) = 0;
          }
        }
      }
      return v14;
    }
    if ( v49 )
    {
      v50 = *(unsigned int *)(v47 + 48);
      v51 = 72;
      v118 = 72;
      v117 = 72;
      if ( (_DWORD)v50 && *(_QWORD *)(v47 + 56) )
      {
        v14 = PrivateULongMult(v50, 3, &v110);
        if ( v14 )
          return v14;
        v14 = PrivateULongAdd(72, (unsigned int)v110, &v117);
        if ( v14 )
          return v14;
        v51 = v117;
        v118 = v117;
      }
      v52 = *(unsigned int *)(v47 + 32);
      if ( (_DWORD)v52 && *(_QWORD *)(v47 + 40) )
      {
        v14 = PrivateULongMult(v52, 6, (char *)&v110 + 4);
        if ( v14 )
          return v14;
        v14 = PrivateULongAdd(v51, HIDWORD(v110), &v117);
        if ( v14 )
          return v14;
        v51 = v117;
        v118 = v117;
      }
      v53 = v13;
      v13 += v51;
      if ( v13 >= v53 )
        goto LABEL_103;
      return (unsigned int)-1073676267;
    }
    return (unsigned int)-1073741811;
  }
  v35 = *(unsigned int *)(v34 + 4);
  v104 = 8;
  if ( (_DWORD)v35 )
  {
    v14 = PrivateULongMult(v35, 24, &v111);
    if ( v14 )
      return v14;
    v36 = (unsigned int)v111;
  }
  else
  {
    v36 = 16;
  }
  v14 = PrivateULongAdd(8, v36, &v104);
  if ( !v14 )
  {
    v14 = PrivateULongAdd(v13, v104, &v117);
    if ( !v14 )
    {
      v13 = v117;
      goto LABEL_72;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x140001474  mov     rax, rsp
0x140001477  mov     [rax+20h], r9d
0x14000147b  mov     [rax+18h], r8
0x14000147f  mov     [rax+8], cx
0x140001483  push    rbp
0x140001484  push    rbx
0x140001485  push    rsi
0x140001486  push    rdi
0x140001487  push    r12
0x140001489  push    r13
0x14000148b  push    r14
0x14000148d  push    r15
0x14000148f  lea     rbp, [rax-47h]
0x140001493  sub     rsp, 98h
0x14000149a  xor     r12d, r12d
0x14000149d  mov     r14, rdx
0x1400014a0  mov     dword ptr [rbp+3Fh+Size], r12d
0x1400014a7  mov     [rbp+3Fh+arg_18], r12d
0x1400014ab  mov     dword ptr [rbp+3Fh+var_A4], r12d
0x1400014af  mov     dword ptr [rbp+3Fh+var_A4+4], r12d
0x1400014b3  mov     dword ptr [rbp+3Fh+var_9C], r12d
0x1400014b7  mov     dword ptr [rbp+3Fh+var_8C], r12d
0x1400014bb  mov     dword ptr [rbp+3Fh+var_9C+4], r12d
0x1400014bf  mov     dword ptr [rbp+3Fh+var_94], r12d
0x1400014c3  mov     [rbp+3Fh+arg_10], r12d
0x1400014c7  mov     dword ptr [rbp+3Fh+var_8C+4], r12d
0x1400014cb  mov     [rbp+3Fh+var_A8], r12d
0x1400014cf  mov     dword ptr [rbp+3Fh+var_78], r12d
0x1400014d3  mov     [rbp+3Fh+arg_8], r12d
0x1400014d7  mov     dword ptr [rbp+3Fh+var_84], r12d
0x1400014db  mov     dword ptr [rbp+3Fh+var_84+4], r12d
0x1400014df  mov     [rbp+3Fh+var_B0], r12
0x1400014e3  test    rdx, rdx
0x1400014e6  jz      loc_140001FEB
0x1400014ec  mov     rax, [rbp+3Fh+arg_40]
0x1400014f3  test    rax, rax
0x1400014f6  jz      loc_140001FEB
0x1400014fc  cmp     byte ptr [rdx], 0A1h
0x1400014ff  jnz     loc_140001FEB
0x140001505  mov     [rax], r12
0x140001508  lea     r15d, [r12+28h]
0x14000150d  mov     al, [rdx+1]
0x140001510  lea     r13d, [r12+3]
0x140001515  lea     r10d, [r12+40h]
0x14000151a  cmp     al, 1
0x14000151c  jnz     short loc_140001530
0x14000151e  cmp     [rdx+2], r15w
0x140001523  jb      loc_140001FEB
0x140001529  lea     r11d, [r12+1]
0x14000152e  jmp     short loc_14000155E
0x140001530  cmp     al, 2
0x140001532  jnz     short loc_140001547
0x140001534  cmp     word ptr [rdx+2], 38h ; '8'
0x140001539  jb      loc_140001FEB
0x14000153f  mov     r11d, 2
0x140001545  jmp     short loc_14000155E
0x140001547  cmp     al, r13b
0x14000154a  jnz     loc_140001FEB
0x140001550  cmp     [rdx+2], r10w
0x140001555  jb      loc_140001FEB
0x14000155b  mov     r11d, r13d
0x14000155e  mov     ecx, [rdx+14h]
0x140001561  mov     ebx, r10d
0x140001564  mov     [rbp+3Fh+arg_0], ebx
0x140001567  mov     dword ptr [rbp+3Fh+var_94+4], r11d
0x14000156b  test    ecx, ecx
0x14000156d  jz      short loc_1400015AF
0x14000156f  cmp     [rdx+18h], r12
0x140001573  jz      short loc_1400015AF
0x140001575  lea     r8, [rbp+3Fh+Size]
0x14000157c  mov     edx, 444h
0x140001581  call    PrivateULongMult
0x140001586  mov     edi, eax
0x140001588  test    eax, eax
0x14000158a  jnz     loc_140001FF0
0x140001590  mov     edx, dword ptr [rbp+3Fh+Size]
0x140001596  lea     r8, [rbp+3Fh+arg_0]
0x14000159a  mov     ecx, r10d
0x14000159d  call    PrivateULongAdd
0x1400015a2  mov     edi, eax
0x1400015a4  test    eax, eax
0x1400015a6  jnz     loc_140001FF0
0x1400015ac  mov     ebx, [rbp+3Fh+arg_0]
0x1400015af  mov     rsi, [rbp+3Fh+arg_28]
0x1400015b3  cmp     [rbp+3Fh+arg_20], r12b
0x1400015b7  jnz     short loc_1400015BD
0x1400015b9  mov     rsi, [r14+20h]
0x1400015bd  test    rsi, rsi
0x1400015c0  jz      loc_140001793
0x1400015c6  mov     ecx, [rsi+30h]
0x1400015c9  mov     r10d, 0A0h
0x1400015cf  mov     [rbp+3Fh+arg_18], r10d
0x1400015d3  mov     [rbp+3Fh+arg_0], r10d
0x1400015d7  test    ecx, ecx
0x1400015d9  jz      short loc_140001618
0x1400015db  cmp     [rsi+38h], r12
0x1400015df  jz      short loc_140001618
0x1400015e1  lea     r8, [rbp+3Fh+var_A4]
0x1400015e5  mov     edx, r13d
0x1400015e8  call    PrivateULongMult
0x1400015ed  mov     edi, eax
0x1400015ef  test    eax, eax
0x1400015f1  jnz     loc_140001FF0
0x1400015f7  mov     edx, dword ptr [rbp+3Fh+var_A4]
0x1400015fa  lea     r8, [rbp+3Fh+arg_0]
0x1400015fe  mov     ecx, r10d
0x140001601  call    PrivateULongAdd
0x140001606  mov     edi, eax
0x140001608  test    eax, eax
0x14000160a  jnz     loc_140001FF0
0x140001610  mov     r10d, [rbp+3Fh+arg_0]
0x140001614  mov     [rbp+3Fh+arg_18], r10d
0x140001618  mov     ecx, [rsi+40h]
0x14000161b  test    ecx, ecx
0x14000161d  jz      short loc_14000165E
0x14000161f  cmp     [rsi+48h], r12
0x140001623  jz      short loc_14000165E
0x140001625  lea     r8, [rbp+3Fh+var_A4+4]
0x140001629  mov     edx, 8
0x14000162e  call    PrivateULongMult
0x140001633  mov     edi, eax
0x140001635  test    eax, eax
0x140001637  jnz     loc_140001FF0
0x14000163d  mov     edx, dword ptr [rbp+3Fh+var_A4+4]
0x140001640  lea     r8, [rbp+3Fh+arg_0]
0x140001644  mov     ecx, r10d
0x140001647  call    PrivateULongAdd
0x14000164c  mov     edi, eax
0x14000164e  test    eax, eax
0x140001650  jnz     loc_140001FF0
0x140001656  mov     r10d, [rbp+3Fh+arg_0]
0x14000165a  mov     [rbp+3Fh+arg_18], r10d
0x14000165e  mov     ecx, [rsi+50h]
0x140001661  test    ecx, ecx
0x140001663  jz      short loc_1400016A4
0x140001665  cmp     [rsi+58h], r12
0x140001669  jz      short loc_1400016A4
0x14000166b  lea     r8, [rbp+3Fh+var_9C]
0x14000166f  mov     edx, 8
0x140001674  call    PrivateULongMult
0x140001679  mov     edi, eax
0x14000167b  test    eax, eax
0x14000167d  jnz     loc_140001FF0
0x140001683  mov     edx, dword ptr [rbp+3Fh+var_9C]
0x140001686  lea     r8, [rbp+3Fh+arg_0]
0x14000168a  mov     ecx, r10d
0x14000168d  call    PrivateULongAdd
0x140001692  mov     edi, eax
0x140001694  test    eax, eax
0x140001696  jnz     loc_140001FF0
0x14000169c  mov     r10d, [rbp+3Fh+arg_0]
0x1400016a0  mov     [rbp+3Fh+arg_18], r10d
0x1400016a4  mov     ecx, [rsi+60h]
0x1400016a7  test    ecx, ecx
0x1400016a9  jz      short loc_1400016EA
0x1400016ab  cmp     [rsi+68h], r12
0x1400016af  jz      short loc_1400016EA
0x1400016b1  lea     r8, [rbp+3Fh+var_9C+4]
0x1400016b5  mov     edx, 8
0x1400016ba  call    PrivateULongMult
0x1400016bf  mov     edi, eax
0x1400016c1  test    eax, eax
0x1400016c3  jnz     loc_140001FF0
0x1400016c9  mov     edx, dword ptr [rbp+3Fh+var_9C+4]
0x1400016cc  lea     r8, [rbp+3Fh+arg_0]
0x1400016d0  mov     ecx, r10d
0x1400016d3  call    PrivateULongAdd
0x1400016d8  mov     edi, eax
0x1400016da  test    eax, eax
0x1400016dc  jnz     loc_140001FF0
0x1400016e2  mov     r10d, [rbp+3Fh+arg_0]
0x1400016e6  mov     [rbp+3Fh+arg_18], r10d
0x1400016ea  mov     ecx, [rsi+70h]
0x1400016ed  test    ecx, ecx
0x1400016ef  jz      short loc_140001730
0x1400016f1  cmp     [rsi+78h], r12
0x1400016f5  jz      short loc_140001730
0x1400016f7  lea     r8, [rbp+3Fh+var_94]
0x1400016fb  mov     edx, 8
0x140001700  call    PrivateULongMult
0x140001705  mov     edi, eax
0x140001707  test    eax, eax
0x140001709  jnz     loc_140001FF0
0x14000170f  mov     edx, dword ptr [rbp+3Fh+var_94]
0x140001712  lea     r8, [rbp+3Fh+arg_0]
0x140001716  mov     ecx, r10d
0x140001719  call    PrivateULongAdd
0x14000171e  mov     edi, eax
0x140001720  test    eax, eax
0x140001722  jnz     loc_140001FF0
0x140001728  mov     r10d, [rbp+3Fh+arg_0]
0x14000172c  mov     [rbp+3Fh+arg_18], r10d
0x140001730  cmp     r11d, r13d
0x140001733  jb      short loc_140001787
0x140001735  mov     ecx, [rsi+8Ch]
0x14000173b  test    ecx, ecx
0x14000173d  jz      short loc_140001787
0x14000173f  cmp     [rsi+90h], r12
0x140001746  jz      short loc_140001787
0x140001748  cmp     [rsi+1], r13b
0x14000174c  jb      short loc_140001787
0x14000174e  lea     r8, [rbp+3Fh+var_8C]
0x140001752  mov     edx, 8
0x140001757  call    PrivateULongMult
0x14000175c  mov     edi, eax
0x14000175e  test    eax, eax
0x140001760  jnz     loc_140001FF0
0x140001766  mov     edx, dword ptr [rbp+3Fh+var_8C]
0x140001769  lea     r8, [rbp+3Fh+arg_0]
0x14000176d  mov     ecx, r10d
0x140001770  call    PrivateULongAdd
0x140001775  mov     edi, eax
0x140001777  test    eax, eax
0x140001779  jnz     loc_140001FF0
0x14000177f  mov     r10d, [rbp+3Fh+arg_0]
0x140001783  mov     [rbp+3Fh+arg_18], r10d
0x140001787  mov     eax, ebx
0x140001789  add     ebx, r10d
0x14000178c  cmp     ebx, eax
0x14000178e  jb      short loc_1400017AC
0x140001790  mov     [rbp+3Fh+arg_0], ebx
0x140001793  cmp     r11d, 2
0x140001797  jb      loc_140001857
0x14000179d  cmp     [rbp+3Fh+arg_30], r12b
0x1400017a1  jz      short loc_1400017B6
0x1400017a3  mov     r13, r12
0x1400017a6  mov     [rbp+3Fh+var_68], r12
0x1400017aa  jmp     short loc_1400017DD
0x1400017ac  mov     edi, 0C0010015h
0x1400017b1  jmp     loc_140001FF0
0x1400017b6  mov     eax, [r14+4]
0x1400017ba  mov     r13, [r14+30h]
0x1400017be  mov     [rbp+3Fh+var_68], r13
0x1400017c2  and     eax, r15d
0x1400017c5  jz      short loc_1400017D0
0x1400017c7  test    r13, r13
0x1400017ca  jz      loc_140001FEB
0x1400017d0  test    r13, r13
0x1400017d3  jz      short loc_1400017DD
0x1400017d5  test    eax, eax
0x1400017d7  jz      loc_140001FEB
0x1400017dd  mov     rax, [r14+28h]
0x1400017e1  mov     [rbp+3Fh+var_70], rax
0x1400017e5  test    rax, rax
0x1400017e8  jz      short loc_140001862
0x1400017ea  mov     ecx, [rax+4]
0x1400017ed  mov     [rbp+3Fh+var_A8], 8
0x1400017f4  test    ecx, ecx
0x1400017f6  jz      short loc_140001815
0x1400017f8  lea     r8, [rbp+3Fh+var_78]
0x1400017fc  mov     edx, 18h
0x140001801  call    PrivateULongMult
0x140001806  mov     edi, eax
0x140001808  test    eax, eax
0x14000180a  jnz     loc_140001FF0
0x140001810  mov     edx, dword ptr [rbp+3Fh+var_78]
0x140001813  jmp     short loc_14000181A
0x140001815  mov     edx, 10h
0x14000181a  lea     r8, [rbp+3Fh+var_A8]
0x14000181e  mov     ecx, 8
0x140001823  call    PrivateULongAdd
0x140001828  mov     edi, eax
0x14000182a  test    eax, eax
0x14000182c  jnz     loc_140001FF0
0x140001832  mov     r10d, [rbp+3Fh+var_A8]
0x140001836  lea     r8, [rbp+3Fh+arg_0]
0x14000183a  mov     edx, r10d
0x14000183d  mov     [rbp+3Fh+var_A8], r10d
0x140001841  mov     ecx, ebx
0x140001843  call    PrivateULongAdd
0x140001848  mov     edi, eax
0x14000184a  test    eax, eax
0x14000184c  jnz     loc_140001FF0
0x140001852  mov     ebx, [rbp+3Fh+arg_0]
0x140001855  jmp     short loc_140001862
0x140001857  mov     [rbp+3Fh+var_70], r12
0x14000185b  mov     r13, r12
0x14000185e  mov     [rbp+3Fh+var_68], r12
0x140001862  mov     dword ptr [rbp+3Fh+var_60], r12d
0x140001866  mov     dword ptr [rbp+3Fh+var_58], r12d
0x14000186a  test    r13, r13
0x14000186d  jz      loc_140001941
0x140001873  mov     ecx, [r13+20h]
0x140001877  mov     r10d, 50h ; 'P'
0x14000187d  mov     [rbp+3Fh+arg_10], r10d
0x140001881  mov     [rbp+3Fh+arg_0], r10d
0x140001885  test    ecx, ecx
0x140001887  jz      short loc_1400018C7
0x140001889  cmp     [r13+28h], r12
0x14000188d  jz      short loc_1400018C7
0x14000188f  lea     r8, [rbp+3Fh+var_8C+4]
0x140001893  lea     edx, [r10-4Dh]
0x140001897  call    PrivateULongMult
0x14000189c  mov     edi, eax
0x14000189e  test    eax, eax
0x1400018a0  jnz     loc_140001FF0
0x1400018a6  mov     edx, dword ptr [rbp+3Fh+var_8C+4]
0x1400018a9  lea     r8, [rbp+3Fh+arg_0]
0x1400018ad  mov     ecx, r10d
0x1400018b0  call    PrivateULongAdd
  ... truncated ...
```
