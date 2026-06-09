# CLikePatternUtil::LikeRangeTransW(wchar_t *,CTypeInfo const *,CXVariant *,CXVariant const *,CLikePatternUtil::x_iGetCode,wchar_t *,int *)

- ea: `0x10048a5f0`
- end: `0x10048b19f`
- name: `?LikeRangeTransW@CLikePatternUtil@@SAXPEA_WPEBVCTypeInfo@@PEAVCXVariant@@PEBV3@W4x_iGetCode@1@0PEAH@Z`
- size: `2991`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100453ea0`
- `0x100453fb0`
- `0x1004540c0`
- `0x1007df590`
- `0x1007df610`
- `0x1007df690`

## callees

- `0x100401630`
- `0x100401cc0`
- `0x100402ec0`
- `0x10046bf60`
- `0x100475080`
- `0x10048a5f0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10048a717`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048a761`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048afff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b00a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b014`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b01e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b0b2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b173`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048a717`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048a761`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048afff`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b00a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b014`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b01e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b0b2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b173`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048b198`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a703`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a74d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a8ce`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048adb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ade9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ae2b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ae64`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a703`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a74d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048a8ce`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048adb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ade9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ae2b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048ae64`
- `sqldk!SystemThread_TlsIndex` at `0x10048a647`
- `sqldk!SystemThread_TlsOffset` at `0x10048a651`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10048a66c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10048a66c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CLikePatternUtil::LikeRangeTransW(
        wchar_t *a1,
        CTypeInfo *a2,
        wchar_t *a3,
        __int64 a4,
        int a5,
        bool a6,
        char a7)
{
  wchar_t *v8; // rsi
  wchar_t *v10; // r13
  char v11; // r8
  const wchar_t *v12; // r15
  const wchar_t *v13; // r14
  __int64 v14; // rbx
  __int64 v15; // rax
  void *v16; // rcx
  int v17; // edi
  unsigned int v18; // r15d
  wchar_t *v19; // r14
  unsigned int v20; // ebx
  wchar_t *v21; // rdx
  wchar_t *v22; // r13
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // rax
  wchar_t *v25; // rbx
  unsigned __int64 v26; // rax
  wchar_t *v27; // rbx
  const wchar_t *v28; // rbx
  wchar_t *v30; // rdi
  char v31; // al
  wchar_t *v32; // rbx
  int v33; // esi
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // rax
  wchar_t *v39; // rsi
  wchar_t *v40; // rbx
  char v42; // al
  char v43; // di
  wchar_t v44; // ax
  wchar_t *v45; // rdi
  unsigned __int64 v46; // rax
  bool v47; // zf
  char v48; // cl
  const wchar_t *v49; // rsi
  char v50; // dl
  int v51; // esi
  char *v52; // rdi
  char v53; // al
  _WORD *v54; // rdi
  char v55; // al
  int v56; // ecx
  int v57; // ecx
  wchar_t *v58; // rbx
  __int64 v59; // rsi
  unsigned __int64 v60; // r14
  unsigned __int64 v61; // rax
  struct IMemObj *v62; // rdi
  unsigned __int64 v63; // rax
  wchar_t *v64; // r13
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rax
  wchar_t *v67; // rdi
  int v68; // esi
  int v69; // r14d
  wchar_t *v70; // r15
  bool v71; // al
  bool v72; // bl
  void *v73; // rsi
  int v74; // edi
  size_t v75; // rdi
  int v76; // eax
  int v77; // edi
  int v78; // edi
  int v79; // edi
  int v80; // edi
  wchar_t v81; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v82; // [rsp+64h] [rbp-9Ch] BYREF
  bool v83; // [rsp+68h] [rbp-98h] BYREF
  bool v84; // [rsp+69h] [rbp-97h] BYREF
  bool v85; // [rsp+6Ah] [rbp-96h] BYREF
  bool v86; // [rsp+6Bh] [rbp-95h] BYREF
  char v87; // [rsp+6Ch] [rbp-94h]
  char *v88; // [rsp+70h] [rbp-90h]
  unsigned __int64 v89; // [rsp+78h] [rbp-88h]
  unsigned __int64 v90; // [rsp+80h] [rbp-80h]
  void *Src; // [rsp+88h] [rbp-78h]
  wchar_t *v92; // [rsp+90h] [rbp-70h]
  wchar_t *v93; // [rsp+98h] [rbp-68h]
  unsigned int v94; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v95; // [rsp+A4h] [rbp-5Ch] BYREF
  int v96; // [rsp+A8h] [rbp-58h] BYREF
  int v97; // [rsp+ACh] [rbp-54h] BYREF
  wchar_t *v98; // [rsp+B0h] [rbp-50h]
  wchar_t *v99; // [rsp+B8h] [rbp-48h]
  size_t Size; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v101; // [rsp+C8h] [rbp-38h]
  wchar_t *v102; // [rsp+D0h] [rbp-30h]
  int v103; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v104; // [rsp+E0h] [rbp-20h]
  void *v105; // [rsp+E8h] [rbp-18h]
  wchar_t *v106; // [rsp+F0h] [rbp-10h]
  wchar_t *v107; // [rsp+F8h] [rbp-8h]
  wchar_t *v108; // [rsp+100h] [rbp+0h]
  void *v109; // [rsp+110h] [rbp+10h]
  size_t v110; // [rsp+118h] [rbp+18h]
  size_t v111; // [rsp+138h] [rbp+38h]
  wchar_t *v114; // [rsp+1A8h] [rbp+A8h] BYREF

  v104 = -2;
  v8 = a3;
  v10 = a1;
  v11 = *(_BYTE *)a3;
  a7 = v11;
  v12 = 0;
  v13 = 0;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
    v11 = a7;
  }
  v16 = *(void **)(v15 + 1000);
  Src = v16;
  v102 = 0;
  v101 = 0;
  if ( ((*(_BYTE *)a4 + 1) & 0xFB) != 0 && *(_DWORD *)(a4 + 16) )
    v13 = *(const wchar_t **)(a4 + 8);
  if ( v11 == 3 )
  {
    v17 = 62;
    v18 = v110;
    v19 = (wchar_t *)v109;
    v20 = v111;
    v21 = a3;
  }
  else
  {
    v22 = (wchar_t *)*((_QWORD *)v8 + 1);
    v23 = *((_DWORD *)v8 + 4) >> 1;
    v89 = v23;
    v24 = 2 * v23;
    if ( !is_mul_ok(v23, 2u) )
      v24 = -1;
    v25 = (wchar_t *)operator new[](
                       v24,
                       (struct IMemObj *)v16,
                       "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp",
                       979,
                       6u);
    v93 = v25;
    if ( v25 )
      operator delete[](0);
    v102 = v25;
    v26 = 2 * v23;
    if ( !is_mul_ok(v23, 2u) )
      v26 = -1;
    v27 = (wchar_t *)operator new[](
                       v26,
                       (struct IMemObj *)Src,
                       "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp",
                       980,
                       6u);
    v99 = v27;
    if ( v27 )
      operator delete[](0);
    v101 = v27;
    v28 = 0;
    while ( 1 )
    {
      if ( !v22 )
        goto LABEL_25;
      if ( !v28++ )
        v28 = v22;
      v30 = &v22[v23];
      v92 = v30;
      if ( v30 <= v28 )
        goto LABEL_25;
      if ( !v13 || (_mm_lfence(), (unsigned int)CTypeInfo::ICompW(a2, v28, 2u, v13, 2u)) )
      {
        v31 = 0;
      }
      else
      {
        v31 = 1;
        if ( v30 <= ++v28 )
          goto LABEL_25;
      }
      if ( !v28 )
      {
LABEL_25:
        LODWORD(v88) = 62;
        v32 = v93;
        v33 = v89;
        while ( v22 )
        {
          if ( !v12++ )
            v12 = v22;
          v35 = (unsigned __int64)&v22[v33];
          if ( v35 <= (unsigned __int64)v12 )
            break;
          if ( v13 )
          {
            _mm_lfence();
            if ( !(unsigned int)CTypeInfo::ICompW(a2, v12, 2u, v13, 2u) && v35 <= (unsigned __int64)++v12 )
              break;
          }
          if ( !v12 )
            break;
          *v32++ = *v12;
        }
        v19 = v93;
        v18 = (_DWORD)v32 - (_DWORD)v93;
        v17 = (int)v88;
        v20 = 8000;
        goto LABEL_180;
      }
      if ( !v31 )
      {
        v36 = *v28;
        LOWORD(v36) = v36 - 37;
        if ( (unsigned __int16)v36 <= 0x3Au )
        {
          v37 = 0x440000000000001LL;
          if ( _bittest64(&v37, v36) )
            break;
        }
      }
      v23 = v89;
    }
    v38 = 2 * v89;
    if ( !is_mul_ok(v89, 2u) )
      v38 = -1;
    v39 = (wchar_t *)operator new[](
                       v38,
                       (struct IMemObj *)Src,
                       "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp",
                       1020,
                       6u);
    v90 = (unsigned __int64)v39;
    v98 = v39;
    v40 = 0;
    while ( 1 )
    {
      if ( !v40++ )
        v40 = v22;
      if ( v30 <= v40 )
      {
LABEL_49:
        v43 = 0;
        goto LABEL_50;
      }
      if ( !v13 || (_mm_lfence(), (unsigned int)CTypeInfo::ICompW(a2, v40, 2u, v13, 2u)) )
      {
        v42 = 0;
      }
      else
      {
        v42 = 1;
        if ( v30 <= ++v40 )
          goto LABEL_49;
      }
      if ( !v40 )
        break;
      if ( v42 )
        goto LABEL_81;
      v44 = *v40;
      if ( *v40 == 95 || v44 == 37 )
      {
        v50 = 0;
        goto LABEL_87;
      }
      if ( v44 != 91 )
      {
LABEL_81:
        v45 = v40;
      }
      else
      {
        v45 = v40 + 1;
        v46 = (unsigned __int64)&v22[(unsigned int)v89];
        v88 = (char *)v46;
        if ( v46 > (unsigned __int64)(v40 + 1) )
        {
          if ( v13 )
          {
            _mm_lfence();
            v47 = (unsigned int)CTypeInfo::ICompW(a2, v40 + 1, 2u, v13, 2u) == 0;
            v46 = (unsigned __int64)v88;
            if ( v47 )
            {
              v45 = v40 + 2;
              if ( v88 <= (char *)v40 + 4 )
                v45 = 0;
            }
          }
        }
        else
        {
          v45 = 0;
        }
        v48 = 0;
        v49 = v45 + 1;
        if ( !v45 )
          v49 = v22;
        if ( v46 > (unsigned __int64)v49 )
        {
          if ( !v13 || (_mm_lfence(), (unsigned int)CTypeInfo::ICompW(a2, v49, 2u, v13, 2u)) )
          {
            v48 = 0;
          }
          else
          {
            v48 = 1;
            if ( v88 <= (char *)++v49 )
              v49 = 0;
          }
        }
        else
        {
          v49 = 0;
        }
        if ( !v45 || !v49 || v48 || *v49 != 93 )
          break;
        if ( !(unsigned int)FRegularWChar(a2, *v45) )
        {
          v50 = 1;
          goto LABEL_87;
        }
        v40 = (wchar_t *)v49;
        v39 = (wchar_t *)v90;
      }
      *v39++ = *v45;
      v90 = (unsigned __int64)v39;
      v30 = v92;
    }
    v43 = 0;
    v50 = 0;
    if ( !v40 )
      goto LABEL_140;
LABEL_87:
    v43 = 0;
    if ( (unsigned int)v89 > v40 - v22 + 2 )
    {
      _mm_lfence();
      if ( *v40 == 91 && !v50 )
      {
        ++v40;
        v92 = (wchar_t *)(2LL * (unsigned int)v89);
        v88 = (char *)v22 + (_QWORD)v92;
        if ( (char *)v22 + (unsigned __int64)v92 > (char *)v40 )
        {
          if ( v13 )
          {
            _mm_lfence();
            if ( !(unsigned int)CTypeInfo::ICompW(a2, v40, 2u, v13, 2u)
              && (char *)v22 + (unsigned __int64)v92 <= (char *)++v40 )
            {
              v40 = 0;
            }
          }
        }
        else
        {
          v40 = 0;
        }
        v43 = 0;
        if ( *v40 != 94 )
        {
          if ( (unsigned int)FRegularWChar(a2, *v40) )
          {
            v87 = 1;
            v81 = *v40;
            v82 = v81;
            v51 = 1;
            while ( 2 )
            {
              v52 = v88;
LABEL_100:
              if ( v52 <= (char *)++v40 )
              {
LABEL_104:
                v40 = 0;
LABEL_105:
                v43 = 0;
                goto LABEL_140;
              }
              if ( !v13 || (_mm_lfence(), (unsigned int)CTypeInfo::ICompW(a2, v40, 2u, v13, 2u)) )
              {
                v53 = 0;
              }
              else
              {
                v53 = 1;
                if ( v52 <= (char *)++v40 )
                  goto LABEL_104;
              }
              if ( !v40 )
                goto LABEL_105;
              if ( v53 )
              {
                ++v51;
              }
              else
              {
                if ( *v40 == 93 )
                {
                  v43 = v87;
                  goto LABEL_140;
                }
                ++v51;
                if ( *v40 == 45 )
                {
                  v54 = v40 + 1;
                  if ( v40 + 1 < (wchar_t *)((char *)v92 + (_QWORD)v22) && v51 > 1 )
                  {
                    if ( !v13 || (_mm_lfence(), (unsigned int)CTypeInfo::ICompW(a2, v40 + 1, 2u, v13, 2u)) )
                    {
                      v55 = 0;
                    }
                    else
                    {
                      v55 = 1;
                      v54 = v40 + 2;
                      if ( (wchar_t *)((char *)v92 + (_QWORD)v22) <= v40 + 2 )
                        goto LABEL_118;
                    }
                    if ( v54 && (v55 || *v54 != 93) )
                    {
                      v51 = -1;
                      continue;
                    }
                  }
LABEL_118:
                  v52 = v88;
                }
              }
              break;
            }
            if ( !(unsigned int)FRegularWChar(a2, *v40) )
              goto LABEL_105;
            if ( v90 > (unsigned __int64)v98 && CTypeInfo::FBinarySort1(a2) )
            {
              v56 = *(unsigned __int8 *)v40 - (unsigned __int8)v81;
              if ( !v56 )
                v56 = *((unsigned __int8 *)v40 + 1) - HIBYTE(v81);
              if ( v56 < 0 )
                v81 = *v40;
              v57 = *(unsigned __int8 *)v40 - (unsigned __int8)v82;
              if ( !v57 )
                v57 = *((unsigned __int8 *)v40 + 1) - HIBYTE(v82);
              if ( v57 > 0 )
                v82 = *v40;
            }
            else
            {
              if ( (int)CTypeInfo::ICompW(a2, v40, 2u, &v81, 2u) < 0 )
                v81 = *v40;
              if ( (int)CTypeInfo::ICompW(a2, v40, 2u, &v82, 2u) > 0 )
                v82 = *v40;
            }
            goto LABEL_100;
          }
        }
      }
    }
LABEL_140:
    v39 = (wchar_t *)v90;
    if ( v40 == v22 )
      goto LABEL_51;
LABEL_50:
    if ( v39 != v98 )
      goto LABEL_142;
LABEL_51:
    if ( !v43 )
    {
      v17 = 1;
      v19 = v93;
      v20 = 8000;
      v18 = 8000;
      goto LABEL_178;
    }
LABEL_142:
    v58 = v98;
    v59 = v39 - v98;
    v90 = v59;
    a6 = 0;
    LOBYTE(v114) = 0;
    if ( v43 )
    {
      v60 = v89;
      v61 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v61 = -1;
      v62 = (struct IMemObj *)Src;
      Src = operator new[](v61, (struct IMemObj *)Src, "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp", 1231, 6u);
      v105 = Src;
      v63 = 2 * v60;
      if ( !is_mul_ok(v60, 2u) )
        v63 = -1;
      v64 = (wchar_t *)operator new[](v63, v62, "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp", 1232, 6u);
      v106 = v64;
      v83 = 0;
      v85 = 0;
      v65 = 2 * v60;
      if ( !is_mul_ok(v60, 2u) )
        v65 = -1;
      v92 = (wchar_t *)operator new[](v65, v62, "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp", 1237, 6u);
      v107 = v92;
      v66 = 2 * v60;
      if ( !is_mul_ok(v60, 2u) )
        v66 = -1;
      v114 = (wchar_t *)operator new[](v66, v62, "sql\\ntdbms\\msql\\typesystem\\LikePatternUtil.cpp", 1238, 6u);
      v108 = v114;
      v84 = 0;
      v86 = 0;
      v67 = &v58[(int)v59];
      *v67 = v81;
      v68 = 2 * v60;
      v69 = 2 * v90 + 2;
      CTypeInfo::GetUnicodeRange(a2, v58, v69, v68, (wchar_t *)Src, (int *)&Size, &v83, v64, (int *)&v95, &v85, 0);
      *v67 = v82;
      v70 = v114;
      CTypeInfo::GetUnicodeRange(a2, v58, v69, v68, v92, &v103, &v84, v114, (int *)&v94, &v86, 0);
      v71 = v83 && v84;
      a6 = v71;
      v72 = v85 && v86;
      LOBYTE(v114) = v72;
      v73 = Src;
      v19 = v93;
      if ( v71 )
      {
        v74 = Size;
        if ( v93 != Src )
          memmove(v93, Src, (unsigned int)Size);
        v97 = v74;
      }
      if ( v72 )
      {
        v20 = v94;
        v75 = v95;
        if ( (int)CTypeInfo::ICompW(a2, v64, v95, v70, v94) > 0 )
        {
          if ( v99 != v64 )
          {
            _mm_lfence();
            memmove(v99, v64, v75);
            LODWORD(v75) = v95;
          }
          v20 = v75;
        }
        else if ( v99 != v70 )
        {
          _mm_lfence();
          memmove(v99, v70, v20);
          v20 = v94;
        }
      }
      else
      {
        v20 = v96;
      }
      operator delete[](v70);
      operator delete[](v92);
      operator delete[](v64);
      operator delete[](v73);
    }
    else
    {
      v19 = v93;
      CTypeInfo::GetUnicodeRange(a2, v98, 2 * v59, 2 * v89, v93, &v97, &a6, v99, &v96, (bool *)&v114, 0);
      v20 = v96;
    }
    v18 = v97;
    if ( a6 )
    {
      v17 = 22;
      v76 = 30;
    }
    else
    {
      v17 = 1;
      v76 = 10;
    }
    if ( (_BYTE)v114 )
      v17 = v76;
LABEL_178:
    operator delete[](v98);
LABEL_180:
    v11 = a7;
    v21 = v99;
    v10 = a1;
    v8 = a3;
  }
  *(_BYTE *)v8 = 0;
  if ( a5 == 2 )
  {
    *((_DWORD *)v8 + 2) = v17;
    *((_BYTE *)v8 + 1) = 56;
    goto LABEL_200;
  }
  v77 = v17 - 1;
  if ( !v77 )
    goto LABEL_199;
  v78 = v77 - 9;
  if ( !v78 )
  {
    if ( !a5 )
      goto LABEL_199;
    goto LABEL_192;
  }
  v79 = v78 - 12;
  if ( !v79 )
  {
    if ( a5 )
    {
      if ( a5 != 1 )
        goto LABEL_200;
      goto LABEL_199;
    }
    goto LABEL_189;
  }
  v80 = v79 - 8;
  if ( v80 )
  {
    if ( v80 != 32 )
      goto LABEL_200;
    if ( v11 != 3 )
      goto LABEL_189;
LABEL_199:
    *(_BYTE *)v8 = 3;
    goto LABEL_200;
  }
  if ( !a5 )
  {
LABEL_189:
    *((_QWORD *)v8 + 1) = v10;
    *((_QWORD *)v8 + 2) = v18;
    if ( v10 != v19 )
      memmove(v10, v19, v18);
    goto LABEL_200;
  }
LABEL_192:
  if ( a5 == 1 )
  {
    *((_QWORD *)v8 + 1) = v10;
    *((_QWORD *)v8 + 2) = v20;
    if ( v10 != v21 )
      memmove(v10, v21, v20);
  }
LABEL_200:
  operator delete[](v101);
  operator delete[](v102);
}

```

## disassembly

```asm
0x10048a5f0  mov     [rsp-8+arg_10], r8
0x10048a5f5  mov     [rsp-8+arg_0], rcx
0x10048a5fa  push    rbp
0x10048a5fb  push    rsi
0x10048a5fc  push    rdi
0x10048a5fd  push    r12
0x10048a5ff  push    r13
0x10048a601  push    r14
0x10048a603  push    r15
0x10048a605  lea     rbp, [rsp-50h]
0x10048a60a  sub     rsp, 150h
0x10048a611  mov     [rbp+80h+var_A0], 0FFFFFFFFFFFFFFFEh
0x10048a619  mov     [rsp+180h+arg_8], rbx
0x10048a621  mov     rdi, r9
0x10048a624  mov     rsi, r8
0x10048a627  mov     r12, rdx
0x10048a62a  mov     r13, rcx
0x10048a62d  movzx   r8d, byte ptr [r8]
0x10048a631  mov     [rbp+80h+arg_30], r8b
0x10048a638  xor     r15d, r15d
0x10048a63b  mov     r14d, r15d
0x10048a63e  mov     r11, gs:58h
0x10048a647  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10048a64e  mov     r10d, [rax]
0x10048a651  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10048a658  mov     ebx, [rax]
0x10048a65a  add     rbx, [r11+r10*8]
0x10048a65e  mov     rax, [rbx+100h]
0x10048a665  test    rax, rax
0x10048a668  jnz     short loc_10048A681
0x10048a66a  xor     ecx, ecx
0x10048a66c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10048a672  mov     rax, [rbx+100h]
0x10048a679  movzx   r8d, [rbp+80h+arg_30]
0x10048a681  mov     rcx, [rax+3E8h]
0x10048a688  mov     [rbp+80h+Src], rcx
0x10048a68c  mov     [rbp+80h+var_B0], r15
0x10048a690  mov     [rbp+80h+var_B8], r15
0x10048a694  movzx   eax, byte ptr [rdi]
0x10048a697  inc     al
0x10048a699  test    al, 0FBh
0x10048a69b  jz      short loc_10048A6A7
0x10048a69d  cmp     dword ptr [rdi+10h], 0
0x10048a6a1  jz      short loc_10048A6A7
0x10048a6a3  mov     r14, [rdi+8]
0x10048a6a7  cmp     r8b, 3
0x10048a6ab  jnz     short loc_10048A6CA
0x10048a6ad  mov     edi, 3Eh ; '>'
0x10048a6b2  mov     r15, [rbp+80h+var_68]
0x10048a6b6  mov     r14, [rbp+80h+var_70]
0x10048a6ba  mov     rbx, [rbp+80h+var_48]
0x10048a6be  mov     rdx, [rbp+80h+arg_10]
0x10048a6c5  jmp     loc_10048B0E7
0x10048a6ca  mov     r13, [rsi+8]
0x10048a6ce  mov     edi, [rsi+10h]
0x10048a6d1  shr     edi, 1
0x10048a6d3  mov     [rsp+180h+var_108], rdi
0x10048a6d8  mov     eax, 2
0x10048a6dd  mul     rdi
0x10048a6e0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x10048a6e7  cmovo   rax, rdx
0x10048a6eb  mov     byte ptr [rsp+180h+var_160], 6
0x10048a6f0  mov     r9d, 3D3h
0x10048a6f6  lea     r8, aSqlNtdbmsMsqlT_0; "sql\\ntdbms\\msql\\typesystem\\LikePatt"...
0x10048a6fd  mov     rdx, rcx
0x10048a700  mov     rcx, rax
0x10048a703  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10048a709  mov     rbx, rax
0x10048a70c  mov     [rbp+80h+var_E8], rax
0x10048a710  test    rax, rax
0x10048a713  jz      short loc_10048A71D
0x10048a715  xor     ecx, ecx
0x10048a717  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10048a71d  mov     [rbp+80h+var_B0], rbx
0x10048a721  mov     eax, 2
0x10048a726  mul     rdi
0x10048a729  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10048a730  cmovo   rax, rcx
0x10048a734  mov     byte ptr [rsp+180h+var_160], 6
0x10048a739  mov     r9d, 3D4h
0x10048a73f  lea     r8, aSqlNtdbmsMsqlT_0; "sql\\ntdbms\\msql\\typesystem\\LikePatt"...
0x10048a746  mov     rdx, [rbp+80h+Src]
0x10048a74a  mov     rcx, rax
0x10048a74d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10048a753  mov     rbx, rax
0x10048a756  mov     [rbp+80h+var_C8], rax
0x10048a75a  test    rax, rax
0x10048a75d  jz      short loc_10048A767
0x10048a75f  xor     ecx, ecx
0x10048a761  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10048a767  mov     [rbp+80h+var_B8], rbx
0x10048a76b  mov     rbx, r15
0x10048a76e  jmp     short loc_10048A775
0x10048a770  mov     rdi, [rsp+180h+var_108]
0x10048a775  test    r13, r13
0x10048a778  jz      short loc_10048A7DB
0x10048a77a  mov     rax, rbx
0x10048a77d  add     rbx, 2
0x10048a781  test    rax, rax
0x10048a784  cmovz   rbx, r13
0x10048a788  lea     rdi, ds:0[rdi*2]
0x10048a790  add     rdi, r13
0x10048a793  mov     [rbp+80h+var_F0], rdi
0x10048a797  cmp     rdi, rbx
0x10048a79a  jbe     short loc_10048A7DB
0x10048a79c  test    r14, r14
0x10048a79f  jz      loc_10048A868
0x10048a7a5  lfence
0x10048a7a8  mov     dword ptr [rsp+180h+var_160], 2; unsigned int
0x10048a7b0  mov     r9, r14; wchar_t *
0x10048a7b3  mov     r8d, 2; unsigned int
0x10048a7b9  mov     rdx, rbx; wchar_t *
0x10048a7bc  mov     rcx, r12; this
0x10048a7bf  call    ?ICompW@CTypeInfo@@QEBAHPEFB_WK0K@Z; CTypeInfo::ICompW(wchar_t const *,ulong,wchar_t const *,ulong)
0x10048a7c4  test    eax, eax
0x10048a7c6  jnz     loc_10048A868
0x10048a7cc  mov     al, 1
0x10048a7ce  add     rbx, 2
0x10048a7d2  cmp     rdi, rbx
0x10048a7d5  ja      loc_10048A86A
0x10048a7db  mov     dword ptr [rsp+180h+var_110], 3Eh ; '>'
0x10048a7e3  mov     rbx, [rbp+80h+var_E8]
0x10048a7e7  mov     rsi, [rsp+180h+var_108]
0x10048a7ec  nop     dword ptr [rax+00h]
0x10048a7f0  test    r13, r13
0x10048a7f3  jz      loc_10048B0BA
0x10048a7f9  mov     rax, r15
0x10048a7fc  add     r15, 2
0x10048a800  test    rax, rax
0x10048a803  cmovz   r15, r13
0x10048a807  mov     eax, esi
0x10048a809  lea     rdi, ds:0[rax*2]
0x10048a811  add     rdi, r13
0x10048a814  cmp     rdi, r15
0x10048a817  jbe     loc_10048B0BA
0x10048a81d  test    r14, r14
0x10048a820  jz      short loc_10048A852
0x10048a822  lfence
0x10048a825  mov     dword ptr [rsp+180h+var_160], 2; unsigned int
0x10048a82d  mov     r9, r14; wchar_t *
0x10048a830  mov     r8d, 2; unsigned int
0x10048a836  mov     rdx, r15; wchar_t *
0x10048a839  mov     rcx, r12; this
0x10048a83c  call    ?ICompW@CTypeInfo@@QEBAHPEFB_WK0K@Z; CTypeInfo::ICompW(wchar_t const *,ulong,wchar_t const *,ulong)
0x10048a841  test    eax, eax
0x10048a843  jnz     short loc_10048A852
0x10048a845  add     r15, 2
0x10048a849  cmp     rdi, r15
0x10048a84c  jbe     loc_10048B0BA
0x10048a852  test    r15, r15
0x10048a855  jz      loc_10048B0BA
0x10048a85b  movzx   eax, word ptr [r15]
0x10048a85f  mov     [rbx], ax
0x10048a862  add     rbx, 2
0x10048a866  jmp     short loc_10048A7F0
0x10048a868  xor     al, al
0x10048a86a  test    rbx, rbx
0x10048a86d  jz      loc_10048A7DB
0x10048a873  test    al, al
0x10048a875  jnz     loc_10048A770
0x10048a87b  movzx   eax, word ptr [rbx]
0x10048a87e  sub     ax, 25h ; '%'
0x10048a882  cmp     ax, 3Ah ; ':'
0x10048a886  ja      loc_10048A770
0x10048a88c  mov     rcx, 440000000000001h
0x10048a896  bt      rcx, rax
0x10048a89a  jnb     loc_10048A770
0x10048a8a0  mov     eax, 2
0x10048a8a5  mul     [rsp+180h+var_108]
0x10048a8aa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10048a8b1  cmovo   rax, rcx
0x10048a8b5  mov     byte ptr [rsp+180h+var_160], 6
0x10048a8ba  mov     r9d, 3FCh
0x10048a8c0  lea     r8, aSqlNtdbmsMsqlT_0; "sql\\ntdbms\\msql\\typesystem\\LikePatt"...
0x10048a8c7  mov     rdx, [rbp+80h+Src]
0x10048a8cb  mov     rcx, rax
0x10048a8ce  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10048a8d4  mov     rsi, rax
0x10048a8d7  mov     [rbp+80h+var_100], rax
0x10048a8db  mov     [rbp+80h+var_D0], rax
0x10048a8df  mov     rbx, r15
0x10048a8e2  mov     rax, rbx
0x10048a8e5  add     rbx, 2
0x10048a8e9  test    rax, rax
0x10048a8ec  cmovz   rbx, r13
0x10048a8f0  cmp     rdi, rbx
0x10048a8f3  jbe     short loc_10048A928
0x10048a8f5  test    r14, r14
0x10048a8f8  jz      short loc_10048A954
0x10048a8fa  lfence
0x10048a8fd  mov     dword ptr [rsp+180h+var_160], 2; unsigned int
0x10048a905  mov     r9, r14; wchar_t *
0x10048a908  mov     r8d, 2; unsigned int
0x10048a90e  mov     rdx, rbx; wchar_t *
0x10048a911  mov     rcx, r12; this
0x10048a914  call    ?ICompW@CTypeInfo@@QEBAHPEFB_WK0K@Z; CTypeInfo::ICompW(wchar_t const *,ulong,wchar_t const *,ulong)
0x10048a919  test    eax, eax
0x10048a91b  jnz     short loc_10048A954
0x10048a91d  mov     al, 1
0x10048a91f  add     rbx, 2
0x10048a923  cmp     rdi, rbx
0x10048a926  ja      short loc_10048A956
0x10048a928  xor     dil, dil
0x10048a92b  cmp     rsi, [rbp+80h+var_D0]
0x10048a92f  jnz     loc_10048AD5E
0x10048a935  test    dil, dil
0x10048a938  jnz     loc_10048AD5E
0x10048a93e  mov     edi, 1
0x10048a943  mov     r14, [rbp+80h+var_E8]
0x10048a947  mov     ebx, 1F40h
0x10048a94c  mov     r15d, ebx
0x10048a94f  jmp     loc_10048B0AE
0x10048a954  xor     al, al
0x10048a956  test    rbx, rbx
0x10048a959  jz      loc_10048AA91
0x10048a95f  test    al, al
0x10048a961  jnz     loc_10048AA70
0x10048a967  movzx   eax, word ptr [rbx]
0x10048a96a  mov     ecx, 5Fh ; '_'
0x10048a96f  cmp     cx, ax
0x10048a972  jz      loc_10048AAA1
0x10048a978  mov     ecx, 25h ; '%'
0x10048a97d  cmp     cx, ax
0x10048a980  jz      loc_10048AAA1
0x10048a986  mov     ecx, 5Bh ; '['
0x10048a98b  cmp     cx, ax
0x10048a98e  jnz     loc_10048AA70
0x10048a994  lea     rdi, [rbx+2]
0x10048a998  mov     eax, dword ptr [rsp+180h+var_108]
0x10048a99c  lea     rax, ds:0[rax*2]
0x10048a9a4  add     rax, r13
0x10048a9a7  mov     [rsp+180h+var_110], rax
0x10048a9ac  cmp     rax, rdi
0x10048a9af  ja      short loc_10048A9B6
0x10048a9b1  mov     rdi, r15
0x10048a9b4  jmp     short loc_10048A9EE
0x10048a9b6  test    r14, r14
0x10048a9b9  jz      short loc_10048A9EE
0x10048a9bb  lfence
0x10048a9be  mov     dword ptr [rsp+180h+var_160], 2; unsigned int
0x10048a9c6  mov     r9, r14; wchar_t *
0x10048a9c9  mov     r8d, 2; unsigned int
0x10048a9cf  mov     rdx, rdi; wchar_t *
0x10048a9d2  mov     rcx, r12; this
0x10048a9d5  call    ?ICompW@CTypeInfo@@QEBAHPEFB_WK0K@Z; CTypeInfo::ICompW(wchar_t const *,ulong,wchar_t const *,ulong)
0x10048a9da  test    eax, eax
0x10048a9dc  mov     rax, [rsp+180h+var_110]
0x10048a9e1  jnz     short loc_10048A9EE
0x10048a9e3  add     rdi, 2
0x10048a9e7  cmp     rax, rdi
0x10048a9ea  cmovbe  rdi, r15
0x10048a9ee  xor     cl, cl
0x10048a9f0  lea     rsi, [rdi+2]
0x10048a9f4  test    rdi, rdi
0x10048a9f7  cmovz   rsi, r13
0x10048a9fb  cmp     rax, rsi
0x10048a9fe  ja      short loc_10048AA05
0x10048aa00  mov     rsi, r15
0x10048aa03  jmp     short loc_10048AA40
0x10048aa05  test    r14, r14
0x10048aa08  jz      short loc_10048AA3E
0x10048aa0a  lfence
0x10048aa0d  mov     dword ptr [rsp+180h+var_160], 2; unsigned int
0x10048aa15  mov     r9, r14; wchar_t *
0x10048aa18  mov     r8d, 2; unsigned int
0x10048aa1e  mov     rdx, rsi; wchar_t *
0x10048aa21  mov     rcx, r12; this
0x10048aa24  call    ?ICompW@CTypeInfo@@QEBAHPEFB_WK0K@Z; CTypeInfo::ICompW(wchar_t const *,ulong,wchar_t const *,ulong)
0x10048aa29  test    eax, eax
0x10048aa2b  jnz     short loc_10048AA3E
0x10048aa2d  mov     cl, 1
0x10048aa2f  add     rsi, 2
0x10048aa33  cmp     [rsp+180h+var_110], rsi
0x10048aa38  cmovbe  rsi, r15
0x10048aa3c  jmp     short loc_10048AA40
0x10048aa3e  xor     cl, cl
0x10048aa40  test    rdi, rdi
0x10048aa43  jz      short loc_10048AA91
0x10048aa45  test    rsi, rsi
0x10048aa48  jz      short loc_10048AA91
0x10048aa4a  test    cl, cl
0x10048aa4c  jnz     short loc_10048AA91
0x10048aa4e  mov     eax, 5Dh ; ']'
0x10048aa53  cmp     ax, [rsi]
0x10048aa56  jnz     short loc_10048AA91
0x10048aa58  movzx   edx, word ptr [rdi]; wchar_t
0x10048aa5b  mov     rcx, r12; struct CTypeInfo *
0x10048aa5e  call    ?FRegularWChar@@YAHPEBVCTypeInfo@@_W@Z; FRegularWChar(CTypeInfo const *,wchar_t)
0x10048aa63  test    eax, eax
0x10048aa65  jz      short loc_10048AA8D
0x10048aa67  mov     rbx, rsi
0x10048aa6a  mov     rsi, [rbp+80h+var_100]
0x10048aa6e  jmp     short loc_10048AA73
0x10048aa70  mov     rdi, rbx
0x10048aa73  movzx   ecx, word ptr [rdi]
0x10048aa76  lea     rax, [rsi+2]
0x10048aa7a  mov     [rsi], cx
0x10048aa7d  mov     rsi, rax
0x10048aa80  mov     [rbp+80h+var_100], rax
0x10048aa84  mov     rdi, [rbp+80h+var_F0]
  ... truncated ...
```
