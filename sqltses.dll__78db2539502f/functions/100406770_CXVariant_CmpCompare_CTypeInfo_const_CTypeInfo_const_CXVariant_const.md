# CXVariant::CmpCompare(CTypeInfo const *,CTypeInfo const *,CXVariant const &)

- ea: `0x100406770`
- end: `0x100406935`
- name: `?CmpCompare@CXVariant@@QEBAKPEBVCTypeInfo@@0AEBV1@@Z`
- size: `453`
- prototype: `unsigned int __fastcall(CXVariant *__hidden this, const struct CTypeInfo *, const struct CTypeInfo *, const struct CXVariant *)`
- caller_count: `9`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x100409500`
- `0x10044c790`
- `0x10044d200`
- `0x100487350`
- `0x100488290`
- `0x1004c8bc0`
- `0x1007df7e0`
- `0x1007f7410`
- `0x1007f7570`

## callees

- `0x100401170`
- `0x100406770`
- `0x1004073c0`
- `0x1004078c0`
- `0x100408180`
- `0x100408980`
- `0x10040bca0`
- `0x10040d680`
- `0x1004185b0`
- `0x1004466b0`
- `0x10044d200`
- `0x1004648f0`
- `0x1004649e0`
- `0x100464a90`
- `0x100464b80`
- `0x100464c50`
- `0x100464cf0`
- `0x100464db0`
- `0x100464f00`
- `0x100465200`
- `0x100465400`
- `0x1004656c0`
- `0x100465870`
- `0x1004659f0`
- `0x100465aa0`
- `0x100465c30`
- `0x100465dc0`
- `0x100465fa0`
- `0x100466060`
- `0x1004664a0`
- `0x10047de00`
- `0x10048d660`
- `0x100836050`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100407a1b`
- `sqldk!SystemThread_TlsOffset` at `0x100407a24`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100407a3d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100407a3d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044f965`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044f965`

## pseudocode

```c
// Hidden C++ exception states: #wind=41
unsigned int __fastcall CXVariant::CmpCompare(
        CXVariant *this,
        const struct CTypeInfo *a2,
        const struct CTypeInfo *a3,
        const struct CXVariant *a4)
{
  char *v4; // rbp
  CXVariant *v5; // rdi
  __int64 v9; // r8
  char v10; // dl
  __int64 v11; // r13
  __int64 v12; // rsi
  __int64 v13; // rbx
  int v14; // eax
  int v15; // r10d
  unsigned int result; // eax
  unsigned int v17; // ebx
  int v18; // eax
  const struct CTypeInfo *v19; // rdx
  CXVariant *v20; // rsi
  char v21; // cl
  int v22; // ecx
  bool v23; // zf
  __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  struct CCompareObject *v27; // rsi
  int v28; // ecx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r11
  float v32; // xmm0_4
  float v33; // xmm1_4
  double v34; // xmm0_8
  double v35; // xmm1_8
  bool v36; // zf
  int v37; // r10d
  int v38; // eax
  int v39; // r10d
  int v40; // eax
  bool v41; // zf
  int v42; // r10d
  char *v43; // rdi
  int v44; // edx
  _BYTE *v45; // rcx
  int v46; // r8d
  unsigned __int8 v47; // al
  __int64 v48; // rax
  unsigned __int16 v49; // ax
  __int64 v50; // r9
  const struct CTypeInfo *v51; // rbx
  unsigned int v52; // edi
  int v53; // eax
  int v54; // r10d
  unsigned int v55; // eax
  int v56; // eax
  CXVariant *v57; // rdi
  int v58; // r9d
  char *v59; // r14
  unsigned __int8 v60; // al
  int v61; // ecx
  int v62; // eax
  int v63; // ecx
  int v64; // eax
  int v65; // ecx
  int v66; // eax
  int v67; // eax
  int v68; // eax
  signed __int64 v69; // rdx
  int v70; // eax
  int v71; // eax
  int v72; // r8d
  __int128 v73; // xmm1
  int v74; // eax
  int v75; // ecx
  int v76; // eax
  int v77; // eax
  __int16 v78; // cx
  __int64 v79; // rcx
  int v80; // eax
  __int64 v81; // rax
  int v82; // edx
  int v83; // eax
  float v84; // xmm0_4
  bool v85; // zf
  double v86; // xmm1_8
  double v87; // xmm0_8
  int v88; // ecx
  __int64 v89; // rcx
  int v90; // eax
  __int64 v91; // rax
  __int64 v92; // rcx
  __int64 v93; // r10
  int v94; // ecx
  int v95; // r10d
  __int64 v96; // rax
  __int64 v97; // r9
  __int128 v98; // rax
  __int64 v99; // r8
  bool v100; // zf
  int v101; // eax
  int v102; // r10d
  int v103; // eax
  signed __int64 v104; // r8
  int v105; // eax
  int v106; // eax
  __int64 v107; // rax
  int v108; // eax
  char v109; // al
  unsigned int v110; // edx
  int v111; // eax
  int v112; // [rsp+20h] [rbp-70h]
  char v113; // [rsp+90h] [rbp+0h] BYREF
  __int64 v114; // [rsp+190h] [rbp+100h]

  v114 = -2;
  v4 = (char *)((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL);
  v5 = a4;
  v9 = *(unsigned __int8 *)a4;
  v10 = *(_BYTE *)this;
  if ( (unsigned __int8)v9 | *(_BYTE *)this
    && (!*((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary
         + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a2))
     || *((_WORD *)a2 + 8) != 0xFFFF)
    && (!*((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWStringOrBinary
         + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)a3))
     || *((_WORD *)a3 + 8) != 0xFFFF) )
  {
    if ( (_BYTE)v9 == v10 )
      return 88;
    result = 40;
    if ( v10 != 3 )
      return 48;
    return result;
  }
  v11 = *(unsigned __int8 *)a2;
  v12 = *(unsigned __int8 *)a3;
  *v4 = v12;
  v13 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + v11);
  if ( *((_BYTE *)&xsm_rgfIsDeepType + v13) && FNeedCompareObj(a2, a3) )
  {
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v26 = 0;
    v27 = GenCompareObj(*(struct IMemObj **)(v25 + 1000), a2, a3, 0, 0);
    *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v27;
    if ( *(_BYTE *)v5 == 3 )
    {
      v28 = 0;
      v29 = 0;
    }
    else
    {
      v28 = *((_DWORD *)v5 + 4);
      v29 = *((_QWORD *)v5 + 1);
    }
    v30 = *(unsigned __int8 *)this;
    if ( (_BYTE)v30 == 3 )
    {
      v31 = 0;
    }
    else
    {
      v26 = *((_DWORD *)this + 4);
      v31 = *((_QWORD *)this + 1);
    }
    LOBYTE(v30) = (_BYTE)v30 == 3;
    LOBYTE(v112) = *(_BYTE *)v5 == 3;
    v17 = (*(__int64 (__fastcall **)(struct CCompareObject *, __int64, __int64, _QWORD, int, __int64, int))(*(_QWORD *)v27 + 48LL))(
            v27,
            v30,
            v31,
            v26,
            v112,
            v29,
            v28);
    (*(void (__fastcall **)(struct CCompareObject *, __int64))(*(_QWORD *)v27 + 40LL))(v27, 1);
    return v17;
  }
  if ( *((_BYTE *)&CXVariant::xsm_rgxvtEquivalent + v13) != *((_BYTE *)&CXVariant::xsm_rgxvtEquivalent
                                                            + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v12)) )
  {
    v17 = 0;
    v18 = comp_setop_types(a2, a3);
    *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v18;
    v19 = a2;
    if ( v18 <= 0 )
      v19 = a3;
    v20 = this;
    if ( v18 <= 0 )
    {
      v20 = v5;
      a3 = a2;
      v5 = this;
    }
    v21 = *v4;
    if ( v18 <= 0 )
      v21 = v11;
    switch ( v21 )
    {
      case 40:
        switch ( *(_BYTE *)v19 )
        {
          case '*':
            v68 = *((unsigned __int8 *)v19 + 19);
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v68;
            v17 = CXVariantPerformCompare<40,42>::Compare(v5, v20, v4 + 224);
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
            break;
          case '+':
            v67 = *((unsigned __int8 *)v19 + 19);
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
            *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v67;
            v17 = CXVariantPerformCompare<40,43>::Compare(v5, v20, v4 + 224);
            *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
            break;
          case ':':
            v17 = CXVariantPerformCompare<40,58>::Compare(v5, v20, &CTypeInfo::tiBit);
            break;
          case '=':
            v17 = CXVariantPerformCompare<40,61>::Compare(v5, v20, &CTypeInfo::tiBit);
            break;
        }
        goto LABEL_22;
      case 42:
        v75 = *((unsigned __int8 *)v19 + 19);
        v76 = *((unsigned __int8 *)a3 + 19);
        *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
        *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
        *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = v76;
        *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v75;
        v17 = CXVariantPerformCompare<42,43>::Compare(v5, v20, v4 + 224);
        *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
        goto LABEL_22;
      case 48:
      case 104:
        switch ( *(_BYTE *)v19 )
        {
          case '4':
            v78 = *((unsigned __int8 *)v5 + 8);
            v23 = v78 == *((_WORD *)v20 + 4);
            if ( v78 >= *((__int16 *)v20 + 4) )
              goto LABEL_20;
            v17 = 1;
            break;
          case '8':
            v22 = *((unsigned __int8 *)v5 + 8);
            v23 = v22 == *((_DWORD *)v20 + 2);
            if ( v22 >= *((_DWORD *)v20 + 2) )
              goto LABEL_20;
            v17 = 1;
            break;
          case ';':
            v83 = *((unsigned __int8 *)v5 + 8);
            goto LABEL_151;
          case '<':
            v81 = 10000LL * *((unsigned __int8 *)v5 + 8);
            v23 = v81 == *((_QWORD *)v20 + 1);
            if ( v81 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            break;
          case '>':
            v86 = (double)*((unsigned __int8 *)v5 + 8);
            goto LABEL_157;
          case 'j':
          case 'l':
            v82 = *((unsigned __int8 *)v5 + 8);
            goto LABEL_148;
          case 'z':
            v80 = 10000 * *((unsigned __int8 *)v5 + 8);
            v23 = v80 == *((_DWORD *)v20 + 2);
            if ( v80 >= *((_DWORD *)v20 + 2) )
              goto LABEL_20;
            v17 = 1;
            break;
          case '\x7F':
            v79 = *((unsigned __int8 *)v5 + 8);
            v23 = v79 == *((_QWORD *)v20 + 1);
            if ( v79 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            break;
          default:
            goto LABEL_22;
        }
        goto LABEL_22;
      case 52:
        switch ( *(_BYTE *)v19 )
        {
          case '8':
            v88 = *((__int16 *)v5 + 4);
            v23 = v88 == *((_DWORD *)v20 + 2);
            if ( v88 >= *((_DWORD *)v20 + 2) )
              goto LABEL_20;
            v17 = 1;
            goto LABEL_22;
          case ';':
            v83 = *((__int16 *)v5 + 4);
LABEL_151:
            v84 = *((float *)v20 + 2);
            if ( v84 > (float)v83 )
            {
              v17 = 1;
              goto LABEL_22;
            }
            v85 = (float)v83 == v84;
            break;
          case '<':
            v91 = 10000 * *((__int16 *)v5 + 4);
            v23 = v91 == *((_QWORD *)v20 + 1);
            if ( v91 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            goto LABEL_22;
          case '>':
            v86 = (double)*((__int16 *)v5 + 4);
            goto LABEL_157;
          case 'j':
          case 'l':
            v82 = *((__int16 *)v5 + 4);
LABEL_148:
            CSsNumeric::ConvertFromI4((CSsNumeric *)(v4 + 224), v82, 0x26u, 0);
            goto LABEL_149;
          case 'z':
            v90 = 10000 * *((__int16 *)v5 + 4);
            v23 = v90 == *((_DWORD *)v20 + 2);
            if ( v90 >= *((_DWORD *)v20 + 2) )
              goto LABEL_20;
            v17 = 1;
            goto LABEL_22;
          case '\x7F':
            v89 = *((__int16 *)v5 + 4);
            v23 = v89 == *((_QWORD *)v20 + 1);
            if ( v89 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            goto LABEL_22;
          default:
            goto LABEL_22;
        }
        goto LABEL_154;
      case 56:
        switch ( *(_BYTE *)v19 )
        {
          case ';':
            v87 = *((float *)v20 + 2);
            v86 = (double)*((int *)v5 + 2);
            goto LABEL_158;
          case '<':
            v96 = 10000LL * *((int *)v5 + 2);
            v23 = v96 == *((_QWORD *)v20 + 1);
            if ( v96 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            break;
          case '>':
            v86 = (double)*((int *)v5 + 2);
            goto LABEL_157;
          case 'j':
          case 'l':
            v17 = CXVariantPerformCompare<56,108>::Compare(v5, v20, &CTypeInfo::tiBit);
            break;
          case 'z':
            v93 = *((int *)v5 + 2);
            v94 = 10000 * v93;
            if ( ((((10000 * v93) & 0xFFFFFFFF80000000uLL) + 0x80000000) & 0xFFFFFFFF7FFFFFFFuLL) != 0 )
            {
              v17 = (((int)v93 >> 31) & 0xFFFFFFFD) + 4;
            }
            else if ( v94 >= *((_DWORD *)v20 + 2) )
            {
              v95 = 4;
              if ( v94 == *((_DWORD *)v20 + 2) )
                v95 = 2;
              v17 = v95;
            }
            else
            {
              v17 = 1;
            }
            break;
          case '\x7F':
            v92 = *((int *)v5 + 2);
            v23 = v92 == *((_QWORD *)v20 + 1);
            if ( v92 >= *((_QWORD *)v20 + 1) )
              goto LABEL_20;
            v17 = 1;
            break;
          default:
            goto LABEL_22;
        }
        goto LABEL_22;
      case 58:
        if ( *(_BYTE *)v19 == 42 )
        {
          v71 = *((unsigned __int8 *)v19 + 19);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v71;
          v17 = CXVariantPerformCompare<58,42>::Compare(v5, v20, v4 + 224);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          goto LABEL_22;
        }
        if ( *(_BYTE *)v19 == 43 )
        {
          v70 = *((unsigned __int8 *)v19 + 19);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v70;
          v17 = CXVariantPerformCompare<58,43>::Compare(v5, v20, v4 + 224);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          goto LABEL_22;
        }
        if ( *(_BYTE *)v19 != 61 )
          goto LABEL_22;
        v69 = (18000LL * *((unsigned __int16 *)v5 + 4)) | ((unsigned __int64)*((unsigned __int16 *)v5 + 5) << 32);
        v23 = v69 == *((_QWORD *)v20 + 1);
        if ( v69 < *((_QWORD *)v20 + 1) )
        {
          v17 = 1;
          goto LABEL_22;
        }
        goto LABEL_20;
      case 59:
        if ( *(_BYTE *)v19 == 62 )
        {
          v86 = *((float *)v5 + 2);
LABEL_157:
          v87 = *((double *)v20 + 1);
LABEL_158:
          if ( v87 <= v86 )
          {
            v85 = v86 == v87;
LABEL_154:
            v17 = 2;
            if ( !v85 )
              v17 = 4;
          }
          else
          {
            v17 = 1;
          }
        }
        goto LABEL_22;
      case 60:
        v109 = *(_BYTE *)v19;
        if ( *(_BYTE *)v19 == 59 )
        {
          v108 = CSsNumeric::ConvertFromI8((CSsNumeric *)(v4 + 224), *((_QWORD *)v5 + 1), 0x26u, 0);
          goto LABEL_228;
        }
        if ( v109 == 62 )
        {
          v17 = CXVariantPerformCompare<60,62>::Compare(v5, v20, &CTypeInfo::tiBit);
          goto LABEL_22;
        }
        if ( ((v109 - 106) & 0xFD) != 0 )
          goto LABEL_22;
        if ( !(unsigned int)CSsNumeric::ConvertFromI8((CSsNumeric *)(v4 + 224), *((_QWORD *)v5 + 1), 0x26u, 0) )
          goto LABEL_223;
        goto LABEL_149;
      case 61:
        if ( *(_BYTE *)v19 == 42 )
        {
          v74 = *((unsigned __int8 *)v19 + 19);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v74;
          v17 = CXVariantPerformCompare<61,42>::Compare(v5, v20, v4 + 224);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
        }
        else if ( *(_BYTE *)v19 == 43 )
        {
          v72 = *((unsigned __int8 *)v19 + 19);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareVarTimeInfo::`vftable';
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 7;
          *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xEC) = v72;
          v73 = *(_OWORD *)v20;
          *(_OWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = *(_OWORD *)v20;
          *(_OWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = *((_OWORD *)v20 + 1);
          *(_WORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC2) = WORD1(v73) & 0xFFFE;
          CXVariantPerformConvertVarTime<43,42>::Convert((struct CXVariant *)(v4 + 192));
          v17 = CXVariantPerformCompare<61,42>::Compare(v5, v4 + 192, v4 + 224);
          *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = &CCompareHashInfo::`vftable';
        }
        goto LABEL_22;
      case 106:
      case 108:
        if ( *(_BYTE *)v19 == 59 )
        {
          v17 = CmpCompareNmR4((CXVariant *)((char *)v5 + 8), *((float *)v20 + 2));
        }
        else if ( *(_BYTE *)v19 == 62 )
        {
          v17 = CmpCompareNmR8((CXVariant *)((char *)v5 + 8), *((double *)v20 + 1));
        }
        goto LABEL_22;
      case 122:
        switch ( *(_BYTE *)v19 )
        {
          case ';':
            v108 = CSsNumeric::ConvertFromI4((CSsNumeric *)(v4 + 224), *((_DWORD *)v5 + 2), 0x26u, 0);
LABEL_228:
            if ( !v108 )
            {
              *(_BYTE *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE2) = 4;
              CSsNumeric::ConvertToNm((CSsNumeric *)(v4 + 224), 0x26u, 4u, 0);
            }
            v17 = CmpCompareNmR4((const struct CSsNumeric *)(v4 + 224), *((float *)v20 + 2));
            break;
          case '<':
            v107 = *((int *)v5 + 2);
            v23 = v107 == *((_QWORD *)v20 + 1);
            if ( v107 >= *((_QWORD *)v20 + 1) )
            {
LABEL_20:
              v17 = 4;
              if ( v23 )
                v17 = 2;
            }
            else
            {
              v17 = 1;
            }
            break;
          case '>':
            v17 = CXVariantPerformCompare<122,62>::Compare(v5, v20, &CTypeInfo::tiBit);
            break;
          case 'j':
          case 'l':
            if ( (unsigned int)CSsNumeric::ConvertFromI4((CSsNumeric *)(v4 + 224), *((_DWORD *)v5 + 2), 0x26u, 0) )
            {
LABEL_149:
              v17 = CSsNumeric::CmpCompareNm((CSsNumeric *)(v4 + 224), (CXVariant *)((char *)v20 + 8));
            }
            else
            {
LABEL_223:
              *(_BYTE *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xE2) = 4;
              CSsNumeric::ConvertToNm((CSsNumeric *)(v4 + 224), 0x26u, 4u, 0);
              v17 = CSsNumeric::CmpCompareNm((CSsNumeric *)(v4 + 224), (CXVariant *)((char *)v20 + 8));
            }
            break;
        }
        goto LABEL_22;
      case 127:
        switch ( *(_BYTE *)v19 )
        {
          case ';':
            v17 = CmpCompareI8R8(*((_QWORD *)v5 + 1), *((float *)v20 + 2));
            goto LABEL_22;
          case '<':
            v104 = *((_QWORD *)v5 + 1);
            if ( 10000 * v104 >= 0 )
            {
              if ( is_mul_ok(v104, 0x2710u) )
              {
LABEL_205:
                if ( 10000 * v104 >= *((_QWORD *)v20 + 1) )
                {
                  v106 = 4;
                  if ( 10000 * v104 == *((_QWORD *)v20 + 1) )
                    v106 = 2;
                  v17 = v106;
                }
                else
                {
                  v17 = 1;
                }
                goto LABEL_22;
              }
            }
            else if ( (unsigned __int128)(v104 * (__int128)10000LL) >> 64 == -1 )
            {
              goto LABEL_205;
            }
            v105 = 4;
            if ( v104 < 0 )
              v105 = 1;
            v17 = v105;
LABEL_22:
            if ( *(int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) > 0 )
            {
              if ( (v17 & 0x78) != 0 )
              {
                v110 = v17 & 0xFFFFFFE7 | 0x10;
                if ( (v17 & 8) == 0 )
                  v110 = v17 & 0xFFFFFFE7;
                v111 = v110 | 8;
                if ( (v17 & 0x10) == 0 )
                  v111 = v110;
                v17 = v111;
              }
              else if ( (v17 & 5) != 5 && (v17 & 5) != 0 )
              {
                if ( (v17 & 1) != 0 )
                {
                  v17 = v17 & 0xFFFFFFFA | 4;
                }
                else if ( (v17 & 4) != 0 )
                {
                  v17 = v17 & 0xFFFFFFFA | 1;
                }
              }
            }
            break;
          case '>':
            v17 = CmpCompareI8R8(*((_QWORD *)v5 + 1), *((double *)v20 + 1));
            goto LABEL_22;
          case 'j':
          case 'l':
            CSsNumeric::ConvertFromI8((CSsNumeric *)(v4 + 224), *((_QWORD *)v5 + 1), 0x26u, 0);
            v17 = CSsNumeric::CmpCompareNm((CSsNumeric *)(v4 + 224), (CXVariant *)((char *)v20 + 8));
            goto LABEL_22;
          case 'z':
            v97 = *((_QWORD *)v5 + 1);
            v98 = v97 * (__int128)10000LL;
            v99 = 10000 * v97;
            if ( 10000 * v97 >= 0 )
              v100 = *((_QWORD *)&v98 + 1) == 0;
            else
              v100 = *((_QWORD *)&v98 + 1) == -1;
            if ( !v100 )
              goto LABEL_200;
            v101 = *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
            if ( (int)v99 == v99 )
              v101 = 10000 * v97;
            LOBYTE(v17) = (int)v99 != v99;
            if ( v17 )
            {
LABEL_200:
              v103 = 4;
              if ( v97 < 0 )
                v103 = 1;
              v17 = v103;
            }
            else if ( v101 >= *((_DWORD *)v20 + 2) )
            {
              v102 = 4;
              if ( v101 == *((_DWORD *)v20 + 2) )
                v102 = 2;
              v17 = v102;
            }
            else
            {
              v17 = 1;
            }
            goto LABEL_22;
          default:
            goto LABEL_22;
        }
        break;
      case -91:
      case -83:
        v77 = BYTES_HILO(*((const unsigned __int8 **)v5 + 1), *((_DWORD *)v5 + 4), (const unsigned __int8 *)v20 + 8, 8u);
        if ( v77 >= 0 )
        {
          v17 = 4;
          if ( !v77 )
            v17 = 2;
        }
        else
        {
          v17 = 1;
        }
        goto LABEL_22;
      default:
        goto LABEL_22;
    }
    return v17;
  }
  switch ( (int)v11 )
  {
    case 36:
      return CXVariantPerformCompare<36,36>::Compare(this, v5, v9, &CTypeInfo::tiBit);
    case 40:
      v43 = (char *)v5 + 8;
      v44 = 2;
      v45 = v43 + 2;
      while ( v45[(CXVariant *)((char *)this + 8) - (CXVariant *)v43] == *v45 )
      {
        --v44;
        if ( --v45 - v43 < 0 )
          return 2;
      }
      v46 = 4;
      if ( *((_BYTE *)this + v44 + 8) < (unsigned __int8)v43[v44] )
        return 1;
      return v46;
    case 41:
      v61 = *((unsigned __int8 *)a3 + 19);
      v62 = *((unsigned __int8 *)a2 + 19);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareVarTimeInfo::`vftable';
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v62;
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v61;
      result = CXVariantPerformCompare<41,41>::Compare(this, v5, v4 + 8, &CTypeInfo::tiBit);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      return result;
    case 42:
      v63 = *((unsigned __int8 *)a3 + 19);
      v64 = *((unsigned __int8 *)a2 + 19);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareVarTimeInfo::`vftable';
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v64;
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v63;
      result = CXVariantPerformCompare<42,42>::Compare(this, v5, v4 + 8, &CTypeInfo::tiBit);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      return result;
    case 43:
      v65 = *((unsigned __int8 *)a3 + 19);
      v66 = *((unsigned __int8 *)a2 + 19);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareVarTimeInfo::`vftable';
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v66;
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v65;
      result = CXVariantPerformCompare<43,43>::Compare(this, v5, v4 + 8, &CTypeInfo::tiBit);
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = &CCompareHashInfo::`vftable';
      return result;
    case 48:
    case 104:
      v47 = *((_BYTE *)v5 + 8);
      v41 = *((_BYTE *)this + 8) == v47;
      if ( *((_BYTE *)this + 8) >= v47 )
        goto LABEL_57;
      return 1;
    case 52:
      v49 = *((_WORD *)v5 + 4);
      v41 = *((_WORD *)this + 4) == v49;
      if ( *((_WORD *)this + 4) >= v49 )
        goto LABEL_57;
      return 1;
    case 56:
      v40 = *((_DWORD *)v5 + 2);
      v41 = *((_DWORD *)this + 2) == v40;
      if ( *((_DWORD *)this + 2) >= v40 )
        goto LABEL_57;
      return 1;
    case 58:
      v55 = *((_DWORD *)this + 2);
      v41 = v55 == *((_DWORD *)v5 + 2);
      if ( v55 >= *((_DWORD *)v5 + 2) )
        goto LABEL_57;
      return 1;
    case 59:
      v32 = *((float *)v5 + 2);
      v33 = *((float *)this + 2);
      if ( v32 > v33 )
        return 1;
      v36 = v33 == v32;
      goto LABEL_48;
    case 60:
    case 61:
    case 127:
      v48 = *((_QWORD *)v5 + 1);
      v41 = *((_QWORD *)this + 1) == v48;
      if ( *((_QWORD *)this + 1) >= v48 )
        goto LABEL_57;
      return 1;
    case 62:
      v34 = *((double *)v5 + 1);
      v35 = *((double *)this + 1);
      if ( v34 > v35 )
        return 1;
      v36 = v35 == v34;
LABEL_48:
      v37 = 2;
      if ( !v36 )
        return 4;
      return v37;
    case 98:
      return CXVariant::SsVarCmpCompare(this, v5);
    case 106:
    case 108:
      return CSsNumeric::CmpCompareNm((CXVariant *)((char *)this + 8), (CXVariant *)((char *)v5 + 8));
    case 122:
      v56 = *((_DWORD *)this + 2);
      v41 = v56 == *((_DWORD *)v5 + 2);
      if ( v56 < *((_DWORD *)v5 + 2) )
        return 1;
LABEL_57:
      v42 = 4;
      if ( v41 )
        return 2;
      return v42;
    case 165:
    case 173:
    case 240:
      if ( (*((_BYTE *)a2 + 1) & 0x10) != 0
        && (_BYTE)v11 != 0xF0
        && *((char *)a2 + 26) < 0
        && ((*((_BYTE *)a2 + 26) >> 4) & 7) == 2 )
      {
        v51 = a2;
        if ( (unsigned int)CtCheckCastEncrypted(a2, a3, 0, &CTypeInfo::tiBit) == 2 )
          v51 = a3;
        if ( (unsigned int)CtCheckCastEncrypted(a3, a2, 0, v50) == 2 )
          v51 = a2;
        v52 = CTrustedMachineHost::Compare(v51, this, v5);
        if ( !v52 )
          utassert_fail(1u, "cmpResult != x_cmpEmpty", "retypes.cpp", 5769, 0);
        return v52;
      }
      else
      {
        v53 = BYTES_HILO(
                *((const unsigned __int8 **)this + 1),
                *((_DWORD *)this + 4),
                *((const unsigned __int8 **)v5 + 1),
                *((_DWORD *)v5 + 4));
        if ( v53 < 0 )
          return 1;
        v54 = 4;
        if ( !v53 )
          return 2;
        return v54;
      }
    case 167:
    case 175:
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareHashInfo::`vftable';
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CSQLCollation::`vftable';
      *(_OWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = 0;
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = 0;
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
      *(_BYTE *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x9D) = 0;
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareString::`vftable';
      CTypeInfo::FillCS(a2, (struct CCompareString *)(v4 + 64));
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD, _DWORD, _QWORD, _DWORD))(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0))(
              *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80),
              *(unsigned int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x94),
              *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
              *(unsigned int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90),
              v4 + 64,
              *((_QWORD *)this + 1),
              *((_DWORD *)this + 4),
              *((_QWORD *)v5 + 1),
              *((_DWORD *)v5 + 4));
      if ( v14 < 0 )
      {
        v15 = 1;
      }
      else
      {
        v15 = 4;
        if ( !v14 )
          v15 = 2;
      }
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareHashInfo::`vftable';
      return v15;
    case 189:
      v57 = (CXVariant *)((char *)v5 + 8);
      v58 = 8;
      v59 = (char *)(this - v57);
      break;
    case 231:
    case 239:
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareHashInfo::`vftable';
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CSQLCollation::`vftable';
      *(_OWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = 0;
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = 0;
      *(_DWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 0;
      *(_BYTE *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x9D) = 0;
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareString::`vftable';
      CTypeInfo::FillCS(a2, (struct CCompareString *)(v4 + 64));
      v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD, _DWORD, _QWORD, _DWORD))(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0))(
              *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80),
              *(unsigned int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x94),
              *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
              *(unsigned int *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x90),
              v4 + 64,
              *((_QWORD *)this + 1),
              *((_DWORD *)this + 4),
              *((_QWORD *)v5 + 1),
              *((_DWORD *)v5 + 4));
      if ( v38 < 0 )
      {
        v39 = 1;
      }
      else
      {
        v39 = 4;
        if ( !v38 )
          v39 = 2;
      }
      *(_QWORD *)(((unsigned __int64)&v113 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = &CCompareHashInfo::`vftable';
      return v39;
    default:
      return 0;
  }
  while ( 1 )
  {
    v60 = v59[(_QWORD)v57 + 8];
    if ( v60 != *(_BYTE *)v57 )
      break;
    v57 = (CXVariant *)((char *)v57 + 1);
    if ( !--v58 )
      return 2;
  }
  if ( v60 < *(_BYTE *)v57 )
    return 1;
  else
    return 4;
}

```

## disassembly

```asm
0x100406770  push    rbp
0x100406772  push    rbx
0x100406773  push    rsi
0x100406774  push    rdi
0x100406775  push    r12
0x100406777  push    r13
0x100406779  push    r14
0x10040677b  push    r15
0x10040677d  sub     rsp, 1A8h
0x100406784  mov     [rsp+1E0h+var_50], 0FFFFFFFFFFFFFFFEh
0x100406790  lea     rbp, [rsp+90h]
0x100406798  and     rbp, 0FFFFFFFFFFFFFFC0h
0x10040679c  mov     rax, cs:__security_cookie
0x1004067a3  xor     rax, rsp
0x1004067a6  mov     [rbp+150h+var_58], rax
0x1004067ad  mov     rdi, r9
0x1004067b0  mov     r15, r8
0x1004067b3  mov     r12, rdx
0x1004067b6  mov     r14, rcx
0x1004067b9  movzx   r8d, byte ptr [r9]
0x1004067bd  movzx   edx, byte ptr [rcx]
0x1004067c0  movzx   eax, dl
0x1004067c3  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004067ca  or      al, r8b
0x1004067cd  jnz     loc_100421643
0x1004067d3  movzx   r13d, byte ptr [r12]
0x1004067d8  movzx   esi, byte ptr [r15]
0x1004067dc  mov     [rbp+150h+var_150], sil
0x1004067e0  movzx   ebx, byte ptr [r13+r9+45AE60h]
0x1004067e9  cmp     byte ptr [rbx+r9+45BE00h], 0
0x1004067f2  jz      short loc_10040680E
0x1004067f4  mov     rdx, r15; struct CTypeInfo *
0x1004067f7  mov     rcx, r12; struct CTypeInfo *
0x1004067fa  call    ?FNeedCompareObj@@YA_NPEBVCTypeInfo@@0@Z; FNeedCompareObj(CTypeInfo const *,CTypeInfo const *)
0x1004067ff  test    al, al
0x100406801  jnz     loc_100407A12
0x100406807  lea     r9, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10040680e  movzx   edx, byte ptr [rbx+r9+464268h]
0x100406817  movzx   ecx, byte ptr [rsi+r9+45AE60h]
0x100406820  cmp     dl, [rcx+r9+464268h]
0x100406828  jnz     loc_100407934
0x10040682e  lea     eax, [r13-22h]; switch 207 cases
0x100406832  cmp     eax, 0CEh
0x100406837  ja      def_100406853; jumptable 0000000100406853 default case, cases 34,35,37-39,44-47,49-51,53-55,57,63-97,99-103,105,107,109-121,123-126,128-164,166,168-172,174,176-188,190-230,232-238
0x10040683d  cdqe
0x10040683f  movzx   eax, ds:(byte_100406994 - 100400000h)[r9+rax]
0x100406848  mov     ecx, ds:(jpt_100406853 - 100400000h)[r9+rax*4]
0x100406850  add     rcx, r9
0x100406853  jmp     rcx; switch jump
0x100406856  lea     r15, ??_7CCompareHashInfo@@6B@; jumptable 0000000100406853 cases 167,175
0x10040685d  mov     [rbp+150h+var_110], r15
0x100406861  lea     rax, ??_7CSQLCollation@@6B@; const CSQLCollation::`vftable'
0x100406868  mov     [rbp+150h+var_110], rax
0x10040686c  xorps   xmm0, xmm0
0x10040686f  movdqa  [rbp+150h+var_D0], xmm0
0x100406877  xor     ebx, ebx
0x100406879  mov     [rbp+150h+var_C0], rbx
0x100406880  mov     [rbp+150h+var_B8], ebx
0x100406886  mov     [rbp+150h+var_B3], bl
0x10040688c  lea     rax, ??_7CCompareString@@6B@; const CCompareString::`vftable'
0x100406893  mov     [rbp+150h+var_110], rax
0x100406897  lea     rdx, [rbp+150h+var_110]; struct CCompareString *
0x10040689b  mov     rcx, r12; this
0x10040689e  call    ?FillCS@CTypeInfo@@QEBAXPEAVCCompareString@@@Z; CTypeInfo::FillCS(CCompareString *)
0x1004068a3  mov     eax, [rdi+10h]
0x1004068a6  mov     rcx, [rdi+8]
0x1004068aa  mov     edx, [r14+10h]
0x1004068ae  mov     r8, [r14+8]
0x1004068b2  mov     [rsp+1E0h+var_1A0], eax
0x1004068b6  mov     [rsp+1E0h+var_1A8], rcx
0x1004068bb  mov     [rsp+1E0h+var_1B0], edx
0x1004068bf  mov     [rsp+1E0h+var_1B8], r8
0x1004068c4  lea     rax, [rbp+150h+var_110]
0x1004068c8  mov     [rsp+1E0h+var_1C0], rax
0x1004068cd  mov     r9d, dword ptr [rbp+150h+var_C0]
0x1004068d4  mov     r8, qword ptr [rbp+150h+var_D0+8]
0x1004068db  mov     edx, dword ptr [rbp+150h+var_C0+4]
0x1004068e1  mov     rcx, qword ptr [rbp+150h+var_D0]
0x1004068e8  call    [rbp+150h+var_B0]
0x1004068ee  test    eax, eax
0x1004068f0  js      loc_10040D6E2
0x1004068f6  mov     r10d, 4
0x1004068fc  mov     r8d, 2
0x100406902  test    eax, eax
0x100406904  cmovz   r10d, r8d
0x100406908  mov     [rbp+150h+var_110], r15
0x10040690c  mov     eax, r10d
0x10040690f  jmp     short loc_100406912
0x100406912  mov     rcx, [rbp+150h+var_58]
0x100406919  xor     rcx, rsp; StackCookie
0x10040691c  call    __security_check_cookie
0x100406921  add     rsp, 1A8h
0x100406928  pop     r15
0x10040692a  pop     r14
0x10040692c  pop     r13
0x10040692e  pop     r12
0x100406930  pop     rdi
0x100406931  pop     rsi
0x100406932  pop     rbx
0x100406933  pop     rbp
0x100406934  retn
0x100407934  xor     ebx, ebx
0x100407936  mov     rdx, r15; struct CTypeInfo *
0x100407939  mov     rcx, r12; struct CTypeInfo *
0x10040793c  call    ?comp_setop_types@@YAHAEBVCTypeInfo@@0@Z; comp_setop_types(CTypeInfo const &,CTypeInfo const &)
0x100407941  mov     dword ptr [rbp+150h+var_148], eax
0x100407944  mov     rdx, r12
0x100407947  test    eax, eax
0x100407949  cmovle  rdx, r15
0x10040794d  mov     rsi, r14
0x100407950  cmovle  rsi, rdi
0x100407954  cmovle  r15, r12
0x100407958  cmovle  rdi, r14
0x10040795c  movzx   ecx, [rbp+150h+var_150]
0x100407960  cmovle  ecx, r13d
0x100407964  movzx   eax, cl
0x100407967  add     eax, 0FFFFFFD8h; switch 134 cases
0x10040796a  cmp     eax, 85h
0x10040796f  ja      short def_10040798E; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x100407971  cdqe
0x100407973  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10040797a  movzx   eax, ds:(byte_100406A9C - 100400000h)[r8+rax]
0x100407983  mov     ecx, ds:(jpt_10040798E - 100400000h)[r8+rax*4]
0x10040798b  add     rcx, r8
0x10040798e  jmp     rcx; switch jump
0x100407991  movzx   eax, byte ptr [rdx]; jumptable 000000010040798E cases 48,104
0x100407994  add     eax, 0FFFFFFCCh; switch 76 cases
0x100407997  cmp     eax, 4Bh
0x10040799a  ja      short def_10040798E; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x10040799c  cdqe
0x10040799e  movzx   eax, ds:(byte_100406B48 - 100400000h)[r8+rax]
0x1004079a7  mov     ecx, ds:(jpt_1004079B2 - 100400000h)[r8+rax*4]
0x1004079af  add     rcx, r8
0x1004079b2  jmp     rcx; switch jump
0x1004079b5  movzx   ecx, byte ptr [rdi+8]; jumptable 00000001004079B2 case 56
0x1004079b9  cmp     ecx, [rsi+8]
0x1004079bc  jl      loc_10044FE50
0x1004079c2  mov     ebx, 4
0x1004079c7  mov     r8d, 2
0x1004079cd  cmovz   ebx, r8d
0x1004079d1  jmp     short def_10040798E; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x1004079d4  cmp     dword ptr [rbp+150h+var_148], 0; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x1004079d8  jle     loc_100407ACF
0x1004079de  mov     eax, ebx
0x1004079e0  test    bl, 78h
0x1004079e3  jnz     loc_100450428
0x1004079e9  and     eax, 5
0x1004079ec  cmp     eax, 5
0x1004079ef  jz      loc_100407ACF
0x1004079f5  test    eax, eax
0x1004079f7  jz      loc_100407ACF
0x1004079fd  test    bl, 1
0x100407a00  jz      loc_10045044A
0x100407a06  and     ebx, 0FFFFFFFEh
0x100407a09  or      ebx, 4
0x100407a0c  jmp     loc_100407ACF
0x100407a12  mov     rdx, gs:58h
0x100407a1b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100407a22  mov     ecx, [rax]
0x100407a24  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100407a2b  mov     ebx, [rax]
0x100407a2d  add     rbx, [rdx+rcx*8]
0x100407a31  mov     rcx, [rbx+100h]
0x100407a38  test    rcx, rcx
0x100407a3b  jnz     short loc_100407A4A
0x100407a3d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100407a43  mov     rcx, [rbx+100h]
0x100407a4a  xor     ebx, ebx
0x100407a4c  mov     [rsp+1E0h+var_1C0], rbx; struct CEnvCollection *
0x100407a51  xor     r9d, r9d; int
0x100407a54  mov     r8, r15; struct CTypeInfo *
0x100407a57  mov     rdx, r12; struct CTypeInfo *
0x100407a5a  mov     rcx, [rcx+3E8h]; struct IMemObj *
0x100407a61  call    ?GenCompareObj@@YAPEAVCCompareObject@@PEAVIMemObj@@PEBVCTypeInfo@@1HPEAVCEnvCollection@@@Z; GenCompareObj(IMemObj *,CTypeInfo const *,CTypeInfo const *,int,CEnvCollection *)
0x100407a66  mov     rsi, rax
0x100407a69  mov     [rbp+150h+var_148], rax
0x100407a6d  movzx   eax, byte ptr [rdi]
0x100407a70  cmp     al, 3
0x100407a72  jnz     loc_10044F8A3
0x100407a78  mov     ecx, ebx
0x100407a7a  mov     r8d, ebx
0x100407a7d  jmp     short loc_100407A80
0x100407a80  movzx   edx, byte ptr [r14]
0x100407a84  cmp     dl, 3
0x100407a87  jnz     loc_10044F8B0
0x100407a8d  mov     r11, rbx
0x100407a90  jmp     short loc_100407A93
0x100407a93  cmp     al, 3
0x100407a95  setz    al
0x100407a98  cmp     dl, 3
0x100407a9b  setz    dl
0x100407a9e  mov     r10, [rsi]
0x100407aa1  mov     [rsp+1E0h+var_1B0], ecx
0x100407aa5  mov     [rsp+1E0h+var_1B8], r8
0x100407aaa  mov     byte ptr [rsp+1E0h+var_1C0], al
0x100407aae  mov     r9d, ebx
0x100407ab1  mov     r8, r11
0x100407ab4  mov     rcx, rsi
0x100407ab7  call    qword ptr [r10+30h]
0x100407abb  mov     ebx, eax
0x100407abd  mov     r8, [rsi]
0x100407ac0  mov     edx, 1
0x100407ac5  mov     rcx, rsi
0x100407ac8  call    qword ptr [r8+28h]
0x100407acc  jmp     short loc_100407ACF
0x100407acf  mov     eax, ebx
0x100407ad1  jmp     loc_100406912
0x10040d6e2  lea     r10d, [rbx+1]
0x10040d6e6  jmp     loc_100406908
0x100411fbe  lea     rdx, [rdi+8]; jumptable 0000000100406853 cases 106,108
0x100411fc2  lea     rcx, [r14+8]; this
0x100411fc6  call    ?CmpCompareNm@CSsNumeric@@QEBAKPEBV1@@Z; CSsNumeric::CmpCompareNm(CSsNumeric const *)
0x100411fcb  jmp     loc_100406912
0x100412320  movzx   ecx, byte ptr [rdx]; jumptable 000000010040798E case 40
0x100412323  sub     ecx, 2Ah ; '*'
0x100412326  jz      loc_10044FB7A
0x10041232c  sub     ecx, 1
0x10041232f  jz      loc_10044FB2A
0x100412335  sub     ecx, 0Fh
0x100412338  jz      loc_10044FB18
0x10041233e  cmp     ecx, 3
0x100412341  jnz     def_10040798E; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x100412347  mov     rdx, rsi
0x10041234a  mov     rcx, rdi
0x10041234d  call    ?Compare@?$CXVariantPerformCompare@$0CI@$0DN@@@SAKPEBVCXVariant@@0PEBVCCompareHashInfo@@@Z; CXVariantPerformCompare<40,61>::Compare(CXVariant const *,CXVariant const *,CCompareHashInfo const *)
0x100412352  mov     ebx, eax
0x100412354  jmp     def_10040798E; jumptable 000000010040798E default case, cases 41,43-47,49-51,53-55,57,62-103,105,107,109-121,123-126,128-164,166-172
0x1004124e6  movss   xmm0, dword ptr [rdi+8]; jumptable 0000000100406853 case 59
0x1004124eb  movss   xmm1, dword ptr [r14+8]
0x1004124f1  comiss  xmm0, xmm1
0x1004124f4  jbe     short loc_10041251D
0x1004124f6  mov     r10d, 1
0x1004124fc  mov     eax, r10d
0x1004124ff  jmp     loc_100406912
0x100412505  movsd   xmm0, qword ptr [rdi+8]; jumptable 0000000100406853 case 62
0x10041250a  movsd   xmm1, qword ptr [r14+8]
0x100412510  comisd  xmm0, xmm1
0x100412514  ja      short loc_1004124F6
0x100412516  ucomisd xmm1, xmm0
0x10041251a  jmp     short loc_100412520
0x10041251d  ucomiss xmm1, xmm0
0x100412520  jp      short loc_10041252A
0x100412522  mov     r10d, 2
0x100412528  jz      short loc_100412530
0x10041252a  mov     r10d, 4
0x100412530  mov     eax, r10d
0x100412533  jmp     loc_100406912
0x100414be9  lea     r15, ??_7CCompareHashInfo@@6B@; jumptable 0000000100406853 cases 231,239
0x100414bf0  mov     [rbp+150h+var_110], r15
0x100414bf4  lea     rax, ??_7CSQLCollation@@6B@; const CSQLCollation::`vftable'
0x100414bfb  mov     [rbp+150h+var_110], rax
0x100414bff  xorps   xmm0, xmm0
0x100414c02  movdqa  [rbp+150h+var_D0], xmm0
0x100414c0a  xor     ebx, ebx
0x100414c0c  mov     [rbp+150h+var_C0], rbx
0x100414c13  mov     [rbp+150h+var_B8], ebx
0x100414c19  mov     [rbp+150h+var_B3], bl
0x100414c1f  lea     rax, ??_7CCompareString@@6B@; const CCompareString::`vftable'
0x100414c26  mov     [rbp+150h+var_110], rax
0x100414c2a  lea     rdx, [rbp+150h+var_110]; struct CCompareString *
0x100414c2e  mov     rcx, r12; this
0x100414c31  call    ?FillCS@CTypeInfo@@QEBAXPEAVCCompareString@@@Z; CTypeInfo::FillCS(CCompareString *)
0x100414c36  mov     eax, [rdi+10h]
0x100414c39  mov     rcx, [rdi+8]
0x100414c3d  mov     edx, [r14+10h]
0x100414c41  mov     r8, [r14+8]
0x100414c45  mov     [rsp+1E0h+var_1A0], eax
0x100414c49  mov     [rsp+1E0h+var_1A8], rcx
0x100414c4e  mov     [rsp+1E0h+var_1B0], edx
0x100414c52  mov     [rsp+1E0h+var_1B8], r8
0x100414c57  lea     rax, [rbp+150h+var_110]
0x100414c5b  mov     [rsp+1E0h+var_1C0], rax
0x100414c60  mov     r9d, dword ptr [rbp+150h+var_C0]
0x100414c67  mov     r8, qword ptr [rbp+150h+var_D0+8]
0x100414c6e  mov     edx, dword ptr [rbp+150h+var_C0+4]
0x100414c74  mov     rcx, qword ptr [rbp+150h+var_D0]
0x100414c7b  call    [rbp+150h+var_B0]
0x100414c81  test    eax, eax
0x100414c83  js      short loc_100414CE5
0x100414c85  mov     r10d, 4
0x100414c8b  mov     r8d, 2
0x100414c91  test    eax, eax
0x100414c93  cmovz   r10d, r8d
0x100414c97  mov     [rbp+150h+var_110], r15
0x100414c9b  mov     eax, r10d
0x100414c9e  jmp     loc_100406912
0x100414ce5  lea     r10d, [rbx+1]
0x100414ce9  jmp     short loc_100414C97
0x1004193c2  mov     eax, [rdi+8]; jumptable 0000000100406853 case 56
0x1004193c5  cmp     [r14+8], eax
0x1004193c9  jl      short loc_1004193E4
0x1004193cb  mov     r10d, 4
0x1004193d1  mov     r8d, 2
0x1004193d7  cmovz   r10d, r8d
0x1004193db  mov     eax, r10d
0x1004193de  jmp     loc_100406912
0x1004193e4  mov     r10d, 1
0x1004193ea  mov     eax, r10d
0x1004193ed  jmp     loc_100406912
0x1004193f3  add     rdi, 8; jumptable 0000000100406853 case 40
  ... truncated ...
```
