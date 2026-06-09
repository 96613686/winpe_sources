# CalcVisRgnWorker(tagWND const * const,HRGN__ * *,ulong)

- ea: `0x140017620`
- end: `0x14001885b`
- name: `?CalcVisRgnWorker@@YAHQEBUtagWND@@PEAPEAUHRGN__@@K@Z`
- size: `4667`
- prototype: `__int64 __fastcall(const struct tagWND *const, HRGN *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140020fa0`

## callees

- `0x140015750`
- `0x14001584c`
- `0x1400159b0`
- `0x1400162d8`
- `0x140016d08`
- `0x140016d7c`
- `0x140016f5c`
- `0x140017620`
- `0x140018864`
- `0x1400192c8`
- `0x1400192e0`
- `0x140019d68`
- `0x140019db8`
- `0x140019e3c`
- `0x1400620a8`
- `0x14014faa0`
- `0x1401f6ef0`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `win32kbase!PopThreadGuardedObject` at `0x140018406`
- `win32kbase!PopThreadGuardedObject` at `0x140018406`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140018704`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140018704`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1400183a7`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1400183a7`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x1400183e8`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x1400183e8`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x140017946`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x140017db3`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x140017946`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x140017db3`
- `win32kbase!SetRectRgnIndirect` at `0x1400184e0`
- `win32kbase!SetRectRgnIndirect` at `0x14001856e`
- `win32kbase!SetRectRgnIndirect` at `0x1400184e0`
- `win32kbase!SetRectRgnIndirect` at `0x14001856e`
- `win32kbase!CreateEmptyRgn` at `0x140018383`
- `win32kbase!CreateEmptyRgn` at `0x140018420`
- `win32kbase!CreateEmptyRgn` at `0x140018383`
- `win32kbase!CreateEmptyRgn` at `0x140018420`
- `win32kbase!GreCombineRgn` at `0x140017981`
- `win32kbase!GreCombineRgn` at `0x14001805e`
- `win32kbase!GreCombineRgn` at `0x1400181b5`
- `win32kbase!GreCombineRgn` at `0x140018504`
- `win32kbase!GreCombineRgn` at `0x140018541`
- `win32kbase!GreCombineRgn` at `0x140018763`
- `win32kbase!GreCombineRgn` at `0x140017981`
- `win32kbase!GreCombineRgn` at `0x14001805e`
- `win32kbase!GreCombineRgn` at `0x1400181b5`
- `win32kbase!GreCombineRgn` at `0x140018504`
- `win32kbase!GreCombineRgn` at `0x140018541`
- `win32kbase!GreCombineRgn` at `0x140018763`
- `win32kbase!IsWindowDesktopComposed` at `0x1400180bc`
- `win32kbase!IsWindowDesktopComposed` at `0x1400180bc`
- `win32kbase!ValidateHmonitorNoRip` at `0x140017ccc`
- `win32kbase!ValidateHmonitorNoRip` at `0x1400187ca`
- `win32kbase!ValidateHmonitorNoRip` at `0x140017ccc`
- `win32kbase!ValidateHmonitorNoRip` at `0x1400187ca`
- `win32kbase!GreDeleteObject` at `0x140017df2`
- `win32kbase!GreDeleteObject` at `0x140018075`
- `win32kbase!GreDeleteObject` at `0x140018198`
- `win32kbase!GreDeleteObject` at `0x140018777`
- `win32kbase!GreDeleteObject` at `0x14001878b`
- `win32kbase!GreDeleteObject` at `0x140017df2`
- `win32kbase!GreDeleteObject` at `0x140018075`
- `win32kbase!GreDeleteObject` at `0x140018198`
- `win32kbase!GreDeleteObject` at `0x140018777`
- `win32kbase!GreDeleteObject` at `0x14001878b`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400186ab`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x1400186ab`
- `win32kbase!Win32FreePool` at `0x140017e12`
- `win32kbase!Win32FreePool` at `0x14001844e`
- `win32kbase!Win32FreePool` at `0x140017e12`
- `win32kbase!Win32FreePool` at `0x14001844e`

## pseudocode

```c
__int64 __fastcall CalcVisRgnWorker(struct tagWND *a1, HRGN *a2, int a3)
{
  struct tagWND *v3; // rbx
  char v4; // di
  __int64 v5; // rax
  __int64 v6; // rsi
  unsigned int v7; // r13d
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  char *v11; // r12
  int v12; // r11d
  __int64 v13; // rcx
  LONG left; // xmm2_4
  struct _RECTL v15; // xmm1
  __m128i v16; // xmm0
  __int64 v17; // rdi
  struct tagWND *v18; // r9
  struct tagWND *v19; // r10
  int v20; // r8d
  struct tagWND *v21; // r15
  int v22; // edx
  int v23; // eax
  int v24; // r15d
  struct tagWND *v25; // r14
  char v26; // cl
  struct tagWND *v27; // r8
  int v28; // ecx
  int v29; // edi
  __int64 v30; // rbx
  int v31; // esi
  __int64 v32; // rdi
  unsigned int v33; // eax
  bool v34; // zf
  LONG *v35; // r14
  LONG *v36; // rdx
  _DWORD *v37; // rcx
  _DWORD *v38; // rdi
  __int64 v39; // rax
  HRGN *v40; // r15
  __int64 v41; // r8
  struct tagWND *v42; // r8
  int v43; // r12d
  struct tagWND *v44; // rbx
  struct tagWND *v45; // rsi
  __int64 v46; // rcx
  struct tagWND *v47; // rbx
  int v48; // esi
  __int64 v49; // rdi
  unsigned int v50; // eax
  bool v51; // zf
  LONG *v52; // r15
  LONG *v53; // rdx
  _DWORD *v54; // rcx
  _DWORD *v55; // rdi
  __int64 v56; // rax
  __int64 v57; // rax
  char v58; // cl
  LONG right; // r8d
  LONG v60; // edx
  LONG top; // edx
  LONG v62; // eax
  LONG bottom; // ecx
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // r8
  char *v69; // rbx
  unsigned __int16 v70; // bx
  __int64 v71; // rax
  __int64 v72; // rbx
  __int64 v73; // r8
  __int64 v74; // rcx
  LONG v75; // edx
  LONG v76; // ecx
  LONG v77; // edx
  LONG v78; // ecx
  __int64 v80; // rdx
  struct tagWND *v81; // rax
  LONG v82; // edx
  LONG v83; // r8d
  LONG v84; // edx
  LONG v85; // ecx
  int v86; // ecx
  __int64 v87; // rdx
  __int64 v88; // rdx
  unsigned int v89; // eax
  int v90; // r14d
  struct tagWND *v91; // rdi
  int v92; // r15d
  int v93; // eax
  struct tagWND *v94; // rdi
  struct _RECTL *v95; // r14
  int v96; // edi
  int v97; // r12d
  int v98; // esi
  char *v99; // r15
  struct tagWND *v100; // r13
  __int64 v101; // r9
  __int64 v102; // r8
  const struct tagWND *v103; // rcx
  __int64 v104; // rdx
  __int64 v105; // rbx
  int *p_left; // rbx
  const struct tagWND *v107; // r9
  unsigned int v108; // eax
  bool v109; // zf
  const struct tagWND *TopLevelOrDpiBoundaryWindow; // rax
  const struct tagWND *v111; // rax
  __int64 v112; // rax
  int v113; // edx
  int v114; // eax
  float *v115; // rdx
  float v116; // xmm5_4
  float v117; // xmm4_4
  float v118; // xmm5_4
  HRGN *v119; // rbx
  HRGN EmptyRgn; // rax
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // r8
  __int64 v124; // r9
  __int64 v125; // rbx
  __int64 v126; // rax
  __int64 v127; // r15
  __int64 v128; // r9
  float *v129; // rax
  __int64 v130; // r11
  float *v131; // rdx
  __int64 v132; // r11
  int v133; // r9d
  float v134; // xmm0_4
  __int64 v135; // rax
  int v136; // ecx
  int v137; // edx
  __int64 v138; // rdi
  __int64 v139; // r15
  unsigned __int16 WindowCoordinateSpaceDpi; // bx
  __int64 v141; // rbx
  __int64 v142; // r8
  int v143; // [rsp+38h] [rbp-D0h]
  struct tagWND *v144; // [rsp+40h] [rbp-C8h] BYREF
  int v145; // [rsp+48h] [rbp-C0h]
  __int128 v146; // [rsp+50h] [rbp-B8h] BYREF
  struct _RECTL *v147; // [rsp+60h] [rbp-A8h]
  __int64 v148; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v149; // [rsp+70h] [rbp-98h] BYREF
  __int128 v150; // [rsp+80h] [rbp-88h]
  __int64 v151; // [rsp+90h] [rbp-78h]
  int v152; // [rsp+98h] [rbp-70h]
  HRGN *v153; // [rsp+A0h] [rbp-68h]
  struct tagWND *v154; // [rsp+A8h] [rbp-60h]
  char *v155; // [rsp+B0h] [rbp-58h]
  _DWORD v156[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v157; // [rsp+C8h] [rbp-40h] BYREF
  char v158[40]; // [rsp+D0h] [rbp-38h] BYREF
  int v159; // [rsp+F8h] [rbp-10h]
  struct _RECTL v160; // [rsp+100h] [rbp-8h] BYREF
  __int128 v161; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v162[240]; // [rsp+128h] [rbp+20h] BYREF
  struct _RECTL v163; // [rsp+218h] [rbp+110h] BYREF

  v3 = a1;
  v4 = a3;
  v145 = a3;
  v153 = a2;
  v144 = a1;
  v160 = 0;
  memset_0(v162, 0, sizeof(v162));
  v5 = *((_QWORD *)v3 + 13);
  v6 = 0;
  v151 = 0;
  v7 = 1;
  v149 = 0;
  v150 = 0;
  if ( !v5
    || (v8 = *((_QWORD *)v3 + 3)) != 0 && (v9 = *(_QWORD *)(v8 + 8)) != 0 && v5 == *(_QWORD *)(v9 + 24)
    || (v10 = *(_QWORD *)(v5 + 40),
        v11 = (char *)v3 + 40,
        v155 = (char *)v3 + 40,
        (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v3 + 5) + 288LL) >> 8)
        ^ (unsigned __int16)(*(_DWORD *)(v10 + 288) >> 8))
       & 0x1FF) == 0) )
  {
    v11 = (char *)v3 + 40;
    goto LABEL_7;
  }
  WindowCoordinateSpaceDpi = GetWindowCoordinateSpaceDpi(v3);
  if ( WindowCoordinateSpaceDpi == GetWindowCoordinateSpaceDpi(*((const struct tagWND **)v144 + 13)) )
  {
    v141 = ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)v11 + 256LL));
    if ( v141 )
    {
      v142 = *(_DWORD *)(*(_QWORD *)v11 + 288LL) >> 8;
      LOWORD(v142) = v142 & 0x1FF;
      GetMonitorRectForDpi(&v146, v141, v142);
      if ( *(_QWORD *)(*(_QWORD *)(v141 + 40) + 28LL) != (_QWORD)v146 )
      {
        v3 = v144;
        v12 = 1;
        v143 = 1;
        goto LABEL_8;
      }
    }
    v3 = v144;
LABEL_7:
    v12 = 0;
    v143 = 0;
LABEL_8:
    v155 = v11;
    goto LABEL_9;
  }
  v3 = v144;
  v12 = 1;
  v143 = 1;
LABEL_9:
  v13 = *(_QWORD *)v11;
  if ( (v4 & 1) != 0 )
  {
    v15 = *(struct _RECTL *)(v13 + 88);
    v160 = v15;
    left = v15.left;
    v160.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v15, 12));
    v16 = (__m128i)v15;
  }
  else
  {
    v160 = *(struct _RECTL *)(v13 + 104);
    right = v160.right;
    v60 = _mm_cvtsi128_si32((__m128i)v160);
    if ( v60 <= *(_DWORD *)(v13 + 88) )
      v60 = *(_DWORD *)(v13 + 88);
    v160.left = v60;
    if ( v160.right >= *(_DWORD *)(v13 + 96) )
      right = *(_DWORD *)(v13 + 96);
    v160.right = right;
    if ( v60 < right )
    {
      top = v160.top;
      if ( v160.top <= *(_DWORD *)(v13 + 92) )
        top = *(_DWORD *)(v13 + 92);
      v160.top = top;
      v62 = *(_DWORD *)(v13 + 100);
      bottom = v160.bottom;
      if ( v160.bottom >= v62 )
        bottom = v62;
      v160.bottom = bottom;
      if ( top < bottom )
        goto LABEL_12;
    }
    left = 0;
    v15 = 0;
    v160 = 0;
    v160.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v16 = 0;
  }
  v160.top = _mm_cvtsi128_si32(_mm_srli_si128(v16, 4));
  v160.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v15, 8));
  v160.left = left;
LABEL_12:
  v17 = *((_QWORD *)v3 + 13);
  if ( !v17 )
    goto LABEL_132;
  v18 = *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v3 + 3) + 8LL) + 24LL);
  v148 = (__int64)v18;
  v19 = (struct tagWND *)*((_QWORD *)v18 + 13);
  v154 = v19;
  if ( (struct tagWND *)v17 == v19 && (*(_WORD *)(*(_QWORD *)v11 + 42LL) & 0x2FFF) != 0x29D )
    goto LABEL_132;
  v20 = v145;
  v21 = v3;
  v152 = 0;
  v22 = v145 & 0x4000;
  LODWORD(v147) = v22;
  while ( 1 )
  {
    v23 = v22;
    if ( (struct tagWND *)v17 == v19 )
      goto LABEL_16;
    if ( *(struct tagWND **)(v17 + 104) == v19 && (*(_WORD *)(*(_QWORD *)(v17 + 40) + 42LL) & 0x2FFF) != 0x29D )
      goto LABEL_132;
    if ( (v20 & 0x1004000) != 0 && (*(_WORD *)(*(_QWORD *)(v17 + 40) + 42LL) & 0x2FFF) == 0x29D )
    {
      v23 = v20 & 0x4000;
      goto LABEL_16;
    }
    if ( v22 )
    {
      v86 = *(_DWORD *)(*((_QWORD *)v21 + 5) + 24LL);
      if ( ((v86 & 0x80000) != 0 || (v86 & 0x20000000) != 0) && ((v86 & 0x2000000) == 0 || (struct tagWND *)v17 == v18) )
      {
        v23 = v22;
        goto LABEL_16;
      }
    }
    if ( (v20 & 0x8000000) != 0 && (*(_WORD *)(*(_QWORD *)(v17 + 40) + 42LL) & 0x2FFF) == 0x29D )
    {
      v93 = IsWindowDesktopComposed(v17);
      v12 = v143;
      if ( v93 )
        break;
    }
    v64 = v152;
    v65 = *(_QWORD *)(v17 + 40);
    if ( *(_QWORD *)(v65 + 168) )
      v64 = 1;
    v152 = v64;
    if ( !v12 )
    {
      v66 = *(_QWORD *)(v17 + 104);
      if ( !v66
        || (v67 = *(_QWORD *)(v17 + 24)) != 0 && (v68 = *(_QWORD *)(v67 + 8)) != 0 && v66 == *(_QWORD *)(v68 + 24)
        || (((unsigned __int16)(*(_DWORD *)(v65 + 288) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v66 + 40) + 288LL) >> 8))
          & 0x1FF) == 0 )
      {
        v69 = (char *)v3 + 224;
        v146 = *(_OWORD *)(v65 + 104);
LABEL_120:
        PhysicalToLogicalInPlaceRect(v21, &v146);
        goto LABEL_121;
      }
      v70 = GetWindowCoordinateSpaceDpi((const struct tagWND *)v17);
      if ( v70 != GetWindowCoordinateSpaceDpi(*(const struct tagWND **)(v17 + 104))
        || (v71 = ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v17 + 40) + 256LL)), (v72 = v71) != 0)
        && ((v73 = *(_DWORD *)(*(_QWORD *)(v17 + 40) + 288LL) >> 8,
             LOWORD(v73) = v73 & 0x1FF,
             GetMonitorRectForDpi(v156, v71, v73),
             v74 = *(_QWORD *)(v72 + 40),
             *(_DWORD *)(v74 + 28) != v156[0])
         || *(_DWORD *)(v74 + 32) != v156[1]) )
      {
        v143 = 1;
        v81 = v144;
        v146 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 104LL);
        v69 = (char *)v144 + 224;
        goto LABEL_148;
      }
      v12 = v143;
      v3 = v144;
    }
    v69 = (char *)v3 + 224;
    v146 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 104LL);
    if ( !v12 )
      goto LABEL_120;
    v81 = v144;
LABEL_148:
    if ( (unsigned int)DpiRectContainsRectWithSubpixel(&v146, v17 + 224, v17, &v160, v69, v81) )
      goto LABEL_149;
    LogicalToPhysicalInPlaceRectWithSubpixel(v17, &v146, 0);
    PhysicalToLogicalInPlaceRectWithSubpixel(v144, &v146, 0);
LABEL_121:
    v75 = v160.left;
    v76 = v160.right;
    if ( v160.left <= (int)v146 )
      v75 = v146;
    v160.left = v75;
    if ( v160.right >= SDWORD2(v146) )
      v76 = DWORD2(v146);
    v160.right = v76;
    if ( v75 >= v76 )
      goto LABEL_131;
    v77 = v160.top;
    v78 = v160.bottom;
    if ( v160.top <= SDWORD1(v146) )
      v77 = DWORD1(v146);
    v160.top = v77;
    if ( v160.bottom >= SHIDWORD(v146) )
      v78 = HIDWORD(v146);
    v160.bottom = v78;
    if ( v77 >= v78 )
    {
LABEL_131:
      v160 = 0;
      goto LABEL_132;
    }
LABEL_149:
    v146 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 88LL);
    if ( v143 )
    {
      if ( (unsigned int)DpiRectContainsRectWithSubpixel(&v146, v17 + 224, v17, &v160, v69, v144) )
        goto LABEL_161;
      LogicalToPhysicalInPlaceRectWithSubpixel(v17, &v146, 0);
      PhysicalToLogicalInPlaceRectWithSubpixel(v144, &v146, 0);
    }
    else
    {
      PhysicalToLogicalInPlaceRect(v21, &v146);
    }
    v82 = v160.left;
    v83 = v160.right;
    if ( v160.left <= (int)v146 )
      v82 = v146;
    v160.left = v82;
    if ( v160.right >= SDWORD2(v146) )
      v83 = DWORD2(v146);
    v160.right = v83;
    if ( v82 >= v83 )
      goto LABEL_131;
    v84 = v160.top;
    v85 = v160.bottom;
    if ( v160.top <= SDWORD1(v146) )
      v84 = DWORD1(v146);
    v160.top = v84;
    if ( v160.bottom >= SHIDWORD(v146) )
      v85 = HIDWORD(v146);
    v160.bottom = v85;
    if ( v84 >= v85 )
      goto LABEL_131;
LABEL_161:
    v22 = (int)v147;
    v21 = (struct tagWND *)v17;
    v17 = *(_QWORD *)(v17 + 104);
    v18 = (struct tagWND *)v148;
    v3 = v144;
    v19 = v154;
    v12 = v143;
    v20 = v145;
  }
  v22 = (int)v147;
  v23 = (int)v147;
  v18 = (struct tagWND *)v148;
  v19 = v154;
  LOBYTE(v20) = v145;
LABEL_16:
  *((_QWORD *)&v150 + 1) = v162;
  v24 = 0;
  *(_QWORD *)((char *)&v149 + 4) = 0x1E00000000LL;
  *(_QWORD *)&v150 = v162;
  v25 = v3;
  v26 = v20;
  v27 = (struct tagWND *)*((_QWORD *)v3 + 13);
  v28 = v26 & 0x10;
  while ( 2 )
  {
    *(_QWORD *)&v146 = v27;
    if ( v27 != v19 )
    {
      if ( v23 )
      {
        v80 = *((_QWORD *)v25 + 5);
        if ( (*(_BYTE *)(v80 + 27) & 0x20) != 0 && ((*(_DWORD *)(v80 + 24) & 0x2000000) == 0 || v27 == v18) )
          break;
        v22 = (int)v147;
      }
      if ( !v28 || (v47 = (struct tagWND *)*((_QWORD *)v27 + 14), v47 == v25) )
      {
LABEL_87:
        v57 = *((_QWORD *)v27 + 5);
        v25 = v27;
        v27 = (struct tagWND *)*((_QWORD *)v27 + 13);
        v58 = *(_BYTE *)(v57 + 31);
        v23 = v22;
        v28 = v58 & 4;
        continue;
      }
      v48 = 0;
      while ( 1 )
      {
        if ( !v47 || v47 == v25 )
        {
          v27 = (struct tagWND *)v146;
          v22 = (int)v147;
          v18 = (struct tagWND *)v148;
          v19 = v154;
          if ( v48 )
          {
            v12 = 1;
            v143 = 1;
          }
          else
          {
            v12 = v143;
          }
          goto LABEL_87;
        }
        v49 = *((_QWORD *)v47 + 5);
        if ( !v48 )
        {
          v50 = *(_DWORD *)(*(_QWORD *)v11 + 288LL);
          if ( *(_QWORD *)(*(_QWORD *)v11 + 256LL) == *(_QWORD *)(v49 + 256) )
          {
            v51 = (((unsigned __int16)(v50 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v49 + 288) >> 8)) & 0x1FF) == 0;
          }
          else
          {
            if ( (v50 & 0xF) != 2 )
            {
LABEL_71:
              v48 = 1;
              goto LABEL_66;
            }
            v51 = (*(_DWORD *)(v49 + 288) & 0xF) == 2;
          }
          if ( !v51 )
            goto LABEL_71;
        }
LABEL_66:
        if ( (*(_BYTE *)(v49 + 31) & 0x10) == 0 || (*(_BYTE *)(v49 + 26) & 8) != 0 || (*(_BYTE *)(v49 + 24) & 0x20) != 0 )
          goto LABEL_67;
        v52 = (LONG *)(v49 + 88);
        if ( v48 )
        {
          if ( !(unsigned int)DpiRectIntersectsRectWithSubpixel(
                                v49 + 88,
                                (char *)v47 + 224,
                                v47,
                                &v160,
                                (char *)v144 + 224,
                                v144) )
            goto LABEL_89;
          v53 = (LONG *)(v49 + 96);
          v54 = (_DWORD *)(v49 + 100);
          v55 = (_DWORD *)(v49 + 92);
        }
        else
        {
          v53 = (LONG *)(v49 + 96);
          if ( v160.left >= *(_DWORD *)(v49 + 96)
            || *v52 >= v160.right
            || (v54 = (_DWORD *)(v49 + 100), v160.top >= *(_DWORD *)(v49 + 100))
            || (v55 = (_DWORD *)(v49 + 92), v52[1] >= v160.bottom) )
          {
LABEL_89:
            v24 = DWORD1(v149);
LABEL_67:
            v47 = (struct tagWND *)*((_QWORD *)v47 + 11);
            continue;
          }
        }
        if ( *v52 >= *v53 )
          goto LABEL_89;
        v24 = DWORD1(v149);
        if ( *v55 >= *v54 )
          goto LABEL_67;
        if ( DWORD1(v149) == DWORD2(v149) )
        {
          if ( !(unsigned int)ResizeVisExcludeMemory((struct _CalcVisRgnData *)&v149) )
            goto LABEL_187;
          v24 = DWORD1(v149);
        }
        v56 = v24++;
        DWORD1(v149) = v24;
        *(_QWORD *)(v150 + 8 * v56) = v47;
        v47 = (struct tagWND *)*((_QWORD *)v47 + 11);
      }
    }
    break;
  }
  v29 = v145;
  if ( (v145 & 8) != 0 )
  {
    v27 = v144;
    v30 = *((_QWORD *)v144 + 14);
    if ( v30 )
    {
      v31 = 0;
      while ( 1 )
      {
        if ( !v30 )
        {
          v29 = v145;
          if ( v31 )
          {
            v12 = 1;
            v143 = 1;
          }
          else
          {
            v12 = v143;
          }
          break;
        }
        v32 = *(_QWORD *)(v30 + 40);
        if ( !v31 )
        {
          v33 = *(_DWORD *)(*(_QWORD *)v11 + 288LL);
          if ( *(_QWORD *)(*(_QWORD *)v11 + 256LL) == *(_QWORD *)(v32 + 256) )
          {
            v34 = (((unsigned __int16)(v33 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v32 + 288) >> 8)) & 0x1FF) == 0;
          }
          else
          {
            if ( (v33 & 0xF) != 2 )
            {
LABEL_28:
              v31 = 1;
              goto LABEL_23;
            }
            v34 = (*(_DWORD *)(v32 + 288) & 0xF) == 2;
          }
          if ( !v34 )
            goto LABEL_28;
        }
LABEL_23:
        if ( (*(_BYTE *)(v32 + 31) & 0x10) != 0 && (*(_BYTE *)(v32 + 26) & 8) == 0 && (*(_BYTE *)(v32 + 24) & 0x20) == 0 )
        {
          v35 = (LONG *)(v32 + 88);
          if ( v31 )
          {
            if ( !(unsigned int)DpiRectIntersectsRectWithSubpixel(
                                  v32 + 88,
                                  v30 + 224,
                                  v30,
                                  &v160,
                                  (char *)v27 + 224,
                                  v27) )
              goto LABEL_24;
            v36 = (LONG *)(v32 + 96);
            v37 = (_DWORD *)(v32 + 100);
            v38 = (_DWORD *)(v32 + 92);
          }
          else
          {
            v36 = (LONG *)(v32 + 96);
            if ( v160.left >= *(_DWORD *)(v32 + 96) )
              goto LABEL_24;
            if ( *v35 >= v160.right )
              goto LABEL_24;
            v37 = (_DWORD *)(v32 + 100);
            if ( v160.top >= *(_DWORD *)(v32 + 100) )
              goto LABEL_24;
            v38 = (_DWORD *)(v32 + 92);
            if ( v35[1] >= v160.bottom )
              goto LABEL_24;
          }
          if ( *v35 < *v36 && *v38 < *v37 )
          {
            if ( v24 == DWORD2(v149) )
            {
              if ( !(unsigned int)ResizeVisExcludeMemory((struct _CalcVisRgnData *)&v149) )
                goto LABEL_187;
              v24 = DWORD1(v149);
            }
            v39 = v24++;
            DWORD1(v149) = v24;
            *(_QWORD *)(v150 + 8 * v39) = v30;
          }
        }
LABEL_24:
        v30 = *(_QWORD *)(v30 + 88);
        v27 = v144;
      }
    }
  }
  if ( v24 <= 0 )
  {
    if ( *(char *)(*(_QWORD *)v11 + 19LL) < 0 )
      v160 = 0;
    v40 = v153;
    if ( (unsigned int)SetOrCreateRectRgnIndirectPublic(v153, &v160) )
    {
      v6 = v151;
      *(_QWORD *)&v146 = v151;
      goto LABEL_51;
    }
    goto LABEL_187;
  }
  if ( v24 > 30 )
  {
    v147 = (struct _RECTL *)Win32AllocPoolWithQuotaZInit(16LL * v24, 1769370453, v27, v18);
    v95 = v147;
    if ( !v147 )
    {
LABEL_187:
      v6 = v151;
LABEL_132:
      v161 = 0;
      SetOrCreateRectRgnIndirectPublic(v153, &v161);
      v7 = 0;
      goto LABEL_133;
    }
    v12 = v143;
  }
  else
  {
    v95 = &v163;
    v147 = &v163;
  }
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = v155;
  v100 = v144;
  v101 = v150;
  while ( 2 )
  {
    v102 = v98;
    v103 = *(const struct tagWND **)(v101 + 8LL * v98);
    v104 = *((_QWORD *)v103 + 5);
    if ( *(_QWORD *)(v104 + 168) )
    {
      v126 = v97++;
      *(_QWORD *)(v101 + 8 * v126) = v103;
    }
    else
    {
      v105 = v96++;
      p_left = &v95[v105].left;
      *(_OWORD *)p_left = *(_OWORD *)(v104 + 88);
      if ( v12 )
      {
        v104 = *(_QWORD *)v99;
        v107 = *(const struct tagWND **)(v101 + 8LL * v98);
        v103 = (const struct tagWND *)*((_QWORD *)v107 + 5);
        v108 = *(_DWORD *)(*(_QWORD *)v99 + 288LL);
        if ( *(_QWORD *)(*(_QWORD *)v99 + 256LL) == *((_QWORD *)v103 + 32) )
        {
          v103 = (const struct tagWND *)(*((_DWORD *)v103 + 72) >> 8);
          LOWORD(v103) = (v108 >> 8) ^ (unsigned __int16)v103;
          v109 = ((unsigned __int16)v103 & 0x1FF) == 0;
          goto LABEL_202;
        }
        if ( (v108 & 0xF) != 2 )
          goto LABEL_203;
        v109 = (*((_DWORD *)v103 + 72) & 0xF) == 2;
LABEL_202:
        if ( !v109 )
        {
LABEL_203:
          TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(v107);
          if ( TopLevelOrDpiBoundaryWindow )
          {
            v129 = (float *)*((_QWORD *)TopLevelOrDpiBoundaryWindow + 27);
            if ( v129 )
            {
              ScaleValueWithSubpixel(p_left, 0, *v129);
              ScaleValueWithSubpixel(p_left + 1, v131, *(float *)(*(_QWORD *)(v130 + 216) + 20LL));
              v133 = (int)(float)((float)((float)((float)p_left[2] * **(float **)(v132 + 216)) + 0.0) + 0.5);
              p_left[2] = v133;
              v134 = (float)((float)((float)p_left[3] * *(float *)(*(_QWORD *)(v132 + 216) + 20LL)) + 0.0) + 0.5;
              p_left[3] = (int)v134;
              v135 = *(_QWORD *)(v132 + 216);
              v136 = (int)*(float *)(v135 + 48);
              v137 = (int)*(float *)(v135 + 52);
              *p_left += v136;
              p_left[2] = v133 + v136;
              p_left[1] += v137;
              p_left[3] = (int)v134 + v137;
            }
          }
          v111 = GetTopLevelOrDpiBoundaryWindow(v100);
          v103 = v111;
          if ( v111 )
          {
            v112 = *((_QWORD *)v111 + 27);
            if ( v112 )
            {
              v113 = (int)*(float *)(v112 + 52);
              v114 = (int)*(float *)(v112 + 48);
              p_left[3] -= v113;
              p_left[1] -= v113;
              *p_left -= v114;
              p_left[2] -= v114;
              ScaleValueWithSubpixel(p_left, 0, 1.0 / **((float **)v103 + 27));
              ScaleValueWithSubpixel(p_left + 1, v115, v116);
              p_left[2] = (int)(float)((float)((float)((float)p_left[2] * v117) + 0.0) + 0.5);
              p_left[3] = (int)(float)((float)((float)((float)p_left[3] * v118) + 0.0) + 0.5);
            }
          }
        }
        v101 = v150;
      }
    }
    v12 = v143;
    if ( ++v98 < SDWORD1(v149) )
      continue;
    break;
  }
  v7 = 1;
  v119 = v153;
  EmptyRgn = *v153;
  if ( !*v153 )
  {
    EmptyRgn = (HRGN)CreateEmptyRgn(v103, v104, v102, v101);
    *v119 = EmptyRgn;
  }
  if ( v96 )
  {
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v157, EmptyRgn, 0, 0);
    if ( v157 )
    {
      if ( RGNOBJAPI::bSubtract((RGNOBJAPI *)&v157, &v160, v95, v96) )
      {
        RGNOBJ::iComplexity((RGNOBJ *)&v157);
      }
      else if ( v157 )
      {
        RGNOBJ::vSet((RGNOBJ *)&v157);
      }
    }
    if ( !v159 )
      RGNOBJ::UpdateUserRgn((RGNOBJ *)&v157);
    if ( v157 )
      _InterlockedDecrement16((volatile signed __int16 *)(v157 + 12));
    PopThreadGuardedObject(v158);
  }
  else
  {
    SetRectRgnIndirect(EmptyRgn, &v160);
  }
  v6 = v151;
  *(_QWORD *)&v146 = v151;
  if ( !v151 )
  {
    v6 = CreateEmptyRgn(v122, v121, v123, v124);
    *(_QWORD *)&v146 = v6;
  }
  v125 = 0;
  if ( v97 > 0 )
  {
    v127 = v150;
    do
    {
      SetRectRgnIndirect(v6, *(_QWORD *)(*(_QWORD *)(v127 + 8 * v125) + 40LL) + 88LL);
      GreCombineRgn(v6, v6, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 8 * v125) + 40LL) + 168LL), 1);
      if ( v143 && IsDpiBoundaryBetweenWindows(v144, *(const struct tagWND **)(v127 + 8 * v125)) )
      {
        v148 = v6;
        v138 = 0;
        v139 = 0;
        if ( (unsigned int)LogicalToPhysicalInPlaceRgnWorker(v128, &v148, 1) )
          v138 = v148;
        if ( (unsigned int)PhysicalToLogicalInPlaceRgnWorker(v144) )
          v139 = v148;
        if ( v148 != v6 )
          GreCombineRgn(v6, v148, 0, 5);
        if ( v138 )
          GreDeleteObject(v138);
        if ( v139 )
          GreDeleteObject(v139);
        v127 = v150;
      }
      if ( (unsigned int)GreCombineRgn(*v153, *v153, v6, 4) == 1 )
        break;
      v125 = (unsigned int)(v125 + 1);
    }
    while ( (int)v125 < v97 );
    v95 = v147;
  }
  if ( v95 != &v163 )
    Win32FreePool(v95);
  v40 = v153;
  v29 = v145;
LABEL_51:
  v41 = *(_QWORD *)(*((_QWORD *)v144 + 5) + 168LL);
  if ( v41 )
    GreCombineRgn(*v40, *v40, v41, 1);
  if ( v152 )
  {
    v42 = v144;
    v43 = 0;
    v44 = (struct tagWND *)*((_QWORD *)v144 + 13);
    if ( v44 != v154 )
    {
      v45 = v144;
      while ( 2 )
      {
        v46 = *((_QWORD *)v44 + 5);
        v144 = *(struct tagWND **)(v46 + 168);
        if ( !v144 )
          goto LABEL_57;
        v87 = *((_QWORD *)v42 + 5);
        if ( (*(_BYTE *)(v87 + 26) & 8) != 0 && (*(_DWORD *)(v87 + 232) & 2) == 0 )
        {
          v43 = 1;
          goto LABEL_232;
        }
        if ( (v29 & 0x1000000) != 0 )
        {
          v43 = 1;
          goto LABEL_232;
        }
        if ( v43 )
        {
LABEL_232:
          if ( (*(_WORD *)(v46 + 42) & 0x2FFF) == 0x29D )
          {
LABEL_58:
            v6 = v146;
            goto LABEL_133;
          }
        }
        v88 = *((_QWORD *)v45 + 5);
        v89 = *(_DWORD *)(v88 + 288);
        if ( *(_QWORD *)(v88 + 256) == *(_QWORD *)(v46 + 256) )
        {
          if ( (((unsigned __int16)(v89 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v46 + 288) >> 8)) & 0x1FF) == 0 )
            goto LABEL_174;
LABEL_190:
          v94 = 0;
          if ( (unsigned int)LogicalToPhysicalInPlaceRgnWorker(v44, &v144, 1) )
            v94 = v144;
          v90 = PhysicalToLogicalInPlaceRgnWorker(v45);
          if ( v90 && v94 )
          {
            GreDeleteObject(v94);
            v91 = v144;
            v92 = GreCombineRgn(*v40, *v40, v144, 1);
LABEL_176:
            GreDeleteObject(v91);
LABEL_177:
            if ( v92 == 1 )
              goto LABEL_58;
LABEL_57:
            v29 = v145;
            v42 = v44;
            v44 = (struct tagWND *)*((_QWORD *)v44 + 13);
            v40 = v153;
            if ( v44 == v154 )
              goto LABEL_58;
            continue;
          }
        }
        else
        {
          if ( (v89 & 0xF) != 2 || (*(_DWORD *)(v46 + 288) & 0xF) != 2 )
            goto LABEL_190;
LABEL_174:
          v90 = PhysicalToLogicalInPlaceRgn(v42, &v144);
        }
        break;
      }
      v91 = v144;
      v92 = GreCombineRgn(*v40, *v40, v144, 1);
      if ( v90 )
        goto LABEL_176;
      goto LABEL_177;
    }
  }
LABEL_133:
  if ( v6 )
    GreDeleteObject(v6);
  if ( (_DWORD)v149 )
    Win32FreePool((void *)v150);
  return v7;
}

```

## disassembly

```asm
0x140017620  mov     r11, rsp
0x140017623  push    rbp
0x140017624  push    r13
0x140017626  lea     rbp, [r11-358h]
0x14001762d  sub     rsp, 448h
0x140017634  mov     rax, cs:__security_cookie
0x14001763b  xor     rax, rsp
0x14001763e  mov     [rbp+350h+var_60], rax
0x140017645  mov     [r11+18h], rbx
0x140017649  xorps   xmm0, xmm0
0x14001764c  mov     [r11-18h], rsi
0x140017650  mov     rbx, rcx
0x140017653  mov     [r11-20h], rdi
0x140017657  mov     edi, r8d
0x14001765a  mov     dword ptr [rsp+450h+var_410], r8d
0x14001765f  mov     r8d, 0F0h; Size
0x140017665  mov     [rbp+350h+var_3B8], rdx
0x140017669  xor     edx, edx; Val
0x14001766b  mov     [rsp+450h+var_418], rcx
0x140017670  lea     rcx, [rbp+350h+var_330]; void *
0x140017674  mov     [r11-28h], r12
0x140017678  mov     [r11-30h], r14
0x14001767c  movups  xmmword ptr [rbp+350h+var_358.left], xmm0
0x140017680  call    memset_0
0x140017685  mov     rax, [rbx+68h]
0x140017689  xor     esi, esi
0x14001768b  mov     [rbp+350h+var_3C8], rsi
0x14001768f  xorps   xmm0, xmm0
0x140017692  mov     r13d, 1
0x140017698  mov     r14d, 1FFh
0x14001769e  movups  [rsp+450h+var_3F0+8], xmm0
0x1400176a3  movups  [rsp+450h+var_3E0+8], xmm0
0x1400176a8  test    rax, rax
0x1400176ab  jz      short loc_1400176F4
0x1400176ad  mov     rcx, [rbx+18h]
0x1400176b1  test    rcx, rcx
0x1400176b4  jz      short loc_1400176C5
0x1400176b6  mov     rdx, [rcx+8]
0x1400176ba  test    rdx, rdx
0x1400176bd  jz      short loc_1400176C5
0x1400176bf  cmp     rax, [rdx+18h]
0x1400176c3  jz      short loc_1400176F4
0x1400176c5  mov     rax, [rax+28h]
0x1400176c9  lea     r12, [rbx+28h]
0x1400176cd  mov     [rbp+350h+var_3A8], r12
0x1400176d1  mov     edx, [rax+120h]
0x1400176d7  mov     rax, [r12]
0x1400176db  shr     edx, 8
0x1400176de  mov     ecx, [rax+120h]
0x1400176e4  shr     ecx, 8
0x1400176e7  xor     dx, cx
0x1400176ea  test    r14w, dx
0x1400176ee  jnz     loc_1400187A1
0x1400176f4  lea     r12, [rbx+28h]
0x1400176f8  xor     r11d, r11d
0x1400176fb  mov     dword ptr [rsp+450h+var_420], r11d
0x140017700  mov     [rbp+350h+var_3A8], r12
0x140017704  mov     rcx, [r12]
0x140017708  test    r13b, dil
0x14001770b  jz      loc_140017B92
0x140017711  movups  xmm2, xmmword ptr [rcx+58h]
0x140017715  movdqa  xmm0, xmm2
0x140017719  movdqa  xmm1, xmm2
0x14001771d  psrldq  xmm0, 0Ch
0x140017722  movups  xmmword ptr [rbp+350h+var_358.left], xmm2
0x140017726  movd    [rbp+350h+var_358.bottom], xmm0
0x14001772b  movdqa  xmm0, xmm2
0x14001772f  psrldq  xmm0, 4
0x140017734  psrldq  xmm1, 8
0x140017739  movd    [rbp+350h+var_358.top], xmm0
0x14001773e  movd    [rbp+350h+var_358.right], xmm1
0x140017743  movss   [rbp+350h+var_358.left], xmm2
0x140017748  mov     rdi, [rbx+68h]
0x14001774c  mov     [rsp+450h+var_30], r15
0x140017754  test    rdi, rdi
0x140017757  jz      loc_140017DA3
0x14001775d  mov     rax, [rbx+18h]
0x140017761  mov     rcx, [rax+8]
0x140017765  mov     r9, [rcx+18h]
0x140017769  mov     qword ptr [rsp+450h+var_3F0], r9
0x14001776e  mov     r10, [r9+68h]
0x140017772  mov     [rbp+350h+var_3B0], r10
0x140017776  cmp     rdi, r10
0x140017779  jz      loc_140017F84
0x14001777f  mov     r8d, dword ptr [rsp+450h+var_410]
0x140017784  mov     r15, rbx
0x140017787  mov     edx, r8d
0x14001778a  mov     [rbp+350h+var_3C0], esi
0x14001778d  and     edx, 4000h
0x140017793  mov     dword ptr [rsp+450h+var_3F8], edx
0x140017797  mov     eax, edx
0x140017799  cmp     rdi, r10
0x14001779c  jnz     loc_140017C03
0x1400177a2  lea     rcx, [rbp+350h+var_330]
0x1400177a6  mov     dword ptr [rsp+450h+var_3E0], 1Eh
0x1400177ae  mov     [rbp+350h+var_3D0], rcx
0x1400177b2  xor     r15d, r15d
0x1400177b5  lea     rcx, [rbp+350h+var_330]
0x1400177b9  mov     dword ptr [rsp+450h+var_3F0+0Ch], r15d
0x1400177be  mov     qword ptr [rsp+450h+var_3E0+8], rcx
0x1400177c3  mov     r14, rbx
0x1400177c6  mov     ecx, r8d
0x1400177c9  mov     r8, [rbx+68h]
0x1400177cd  and     ecx, 10h
0x1400177d0  mov     qword ptr [rsp+450h+var_410+8], r8
0x1400177d5  cmp     r8, r10
0x1400177d8  jnz     loc_1400179E8
0x1400177de  mov     edi, dword ptr [rsp+450h+var_410]
0x1400177e2  test    dil, 8
0x1400177e6  jz      loc_140017921
0x1400177ec  mov     r8, [rsp+450h+var_418]
0x1400177f1  mov     rbx, [r8+70h]
0x1400177f5  test    rbx, rbx
0x1400177f8  jz      loc_140017921
0x1400177fe  xor     esi, esi
0x140017800  test    rbx, rbx
0x140017803  jz      loc_140017910
0x140017809  mov     rdi, [rbx+28h]
0x14001780d  test    esi, esi
0x14001780f  jz      short loc_140017822
0x140017811  test    byte ptr [rdi+1Fh], 10h
0x140017815  jnz     short loc_14001785E
0x140017817  mov     rbx, [rbx+58h]
0x14001781b  mov     r8, [rsp+450h+var_418]
0x140017820  jmp     short loc_140017800
0x140017822  mov     rdx, [r12]
0x140017826  mov     rax, [rdi+100h]
0x14001782d  cmp     [rdx+100h], rax
0x140017834  mov     eax, [rdx+120h]
0x14001783a  jnz     loc_1400178F7
0x140017840  mov     ecx, [rdi+120h]
0x140017846  shr     eax, 8
0x140017849  shr     ecx, 8
0x14001784c  xor     cx, ax
0x14001784f  mov     eax, 1FFh
0x140017854  test    ax, cx
0x140017857  jz      short loc_140017811
0x140017859  mov     esi, r13d
0x14001785c  jmp     short loc_140017811
0x14001785e  test    byte ptr [rdi+1Ah], 8
0x140017862  jnz     short loc_140017817
0x140017864  test    byte ptr [rdi+18h], 20h
0x140017868  jnz     short loc_140017817
0x14001786a  lea     r14, [rdi+58h]
0x14001786e  test    esi, esi
0x140017870  jnz     loc_1400180EE
0x140017876  mov     eax, [r14+8]
0x14001787a  lea     rdx, [r14+8]
0x14001787e  cmp     [rbp+350h+var_358.left], eax
0x140017881  jge     short loc_140017817
0x140017883  mov     eax, [rbp+350h+var_358.right]
0x140017886  cmp     [r14], eax
0x140017889  jge     short loc_140017817
0x14001788b  mov     eax, [r14+0Ch]
0x14001788f  lea     rcx, [r14+0Ch]
0x140017893  cmp     [rbp+350h+var_358.top], eax
0x140017896  jge     loc_140017817
0x14001789c  mov     eax, [rbp+350h+var_358.bottom]
0x14001789f  lea     rdi, [r14+4]
0x1400178a3  cmp     [rdi], eax
0x1400178a5  jge     loc_140017817
0x1400178ab  mov     eax, [rdx]
0x1400178ad  cmp     [r14], eax
0x1400178b0  jge     loc_140017817
0x1400178b6  mov     eax, [rcx]
0x1400178b8  cmp     [rdi], eax
0x1400178ba  jge     loc_140017817
0x1400178c0  cmp     r15d, dword ptr [rsp+450h+var_3E0]
0x1400178c5  jnz     short loc_1400178DE
0x1400178c7  lea     rcx, [rsp+450h+var_3F0+8]; struct _CalcVisRgnData *
0x1400178cc  call    ?ResizeVisExcludeMemory@@YAHPEAU_CalcVisRgnData@@@Z; ResizeVisExcludeMemory(_CalcVisRgnData *)
0x1400178d1  test    eax, eax
0x1400178d3  jz      loc_140018138
0x1400178d9  mov     r15d, dword ptr [rsp+450h+var_3F0+0Ch]
0x1400178de  mov     rcx, qword ptr [rsp+450h+var_3E0+8]
0x1400178e3  movsxd  rax, r15d
0x1400178e6  inc     r15d
0x1400178e9  mov     dword ptr [rsp+450h+var_3F0+0Ch], r15d
0x1400178ee  mov     [rcx+rax*8], rbx
0x1400178f2  jmp     loc_140017817
0x1400178f7  and     al, 0Fh
0x1400178f9  cmp     al, 2
0x1400178fb  jnz     loc_140017859
0x140017901  mov     eax, [rdi+120h]
0x140017907  and     al, 0Fh
0x140017909  cmp     al, 2
0x14001790b  jmp     loc_140017857
0x140017910  mov     edi, dword ptr [rsp+450h+var_410]
0x140017914  test    esi, esi
0x140017916  jnz     loc_140017E3C
0x14001791c  mov     r11d, dword ptr [rsp+450h+var_420]
0x140017921  test    r15d, r15d
0x140017924  jg      loc_1400181C9
0x14001792a  mov     rax, [r12]
0x14001792e  cmp     byte ptr [rax+13h], 0
0x140017932  jge     short loc_14001793B
0x140017934  xorps   xmm0, xmm0
0x140017937  movups  xmmword ptr [rbp+350h+var_358.left], xmm0
0x14001793b  mov     r15, [rbp+350h+var_3B8]
0x14001793f  lea     rdx, [rbp+350h+var_358]
0x140017943  mov     rcx, r15
0x140017946  call    cs:__imp_SetOrCreateRectRgnIndirectPublic
0x14001794d  nop     dword ptr [rax+rax+00h]
0x140017952  test    eax, eax
0x140017954  jz      loc_140018138
0x14001795a  mov     rsi, [rbp+350h+var_3C8]
0x14001795e  mov     qword ptr [rsp+450h+var_410+8], rsi
0x140017963  mov     rbx, [rsp+450h+var_418]
0x140017968  mov     rax, [rbx+28h]
0x14001796c  mov     r8, [rax+0A8h]
0x140017973  test    r8, r8
0x140017976  jz      short loc_14001798D
0x140017978  mov     rcx, [r15]
0x14001797b  mov     r9d, r13d
0x14001797e  mov     rdx, rcx
0x140017981  call    cs:__imp_GreCombineRgn
0x140017988  nop     dword ptr [rax+rax+00h]
0x14001798d  cmp     [rbp+350h+var_3C0], 0
0x140017991  jz      loc_140017DC2
0x140017997  mov     r8, rbx
0x14001799a  xor     r12d, r12d
0x14001799d  mov     rbx, [rbx+68h]
0x1400179a1  cmp     rbx, [rbp+350h+var_3B0]
0x1400179a5  jz      loc_140017DC2
0x1400179ab  mov     rsi, r8
0x1400179ae  xchg    ax, ax
0x1400179b0  mov     rcx, [rbx+28h]
0x1400179b4  mov     rax, [rcx+0A8h]
0x1400179bb  mov     [rsp+450h+var_418], rax
0x1400179c0  test    rax, rax
0x1400179c3  jnz     loc_140017FE1
0x1400179c9  mov     edi, dword ptr [rsp+450h+var_410]
0x1400179cd  mov     r8, rbx
0x1400179d0  mov     rbx, [rbx+68h]
0x1400179d4  mov     r15, [rbp+350h+var_3B8]
0x1400179d8  cmp     rbx, [rbp+350h+var_3B0]
0x1400179dc  jnz     short loc_1400179B0
0x1400179de  mov     rsi, qword ptr [rsp+450h+var_410+8]
0x1400179e3  jmp     loc_140017DC2
0x1400179e8  test    eax, eax
0x1400179ea  jnz     loc_140017E8F
0x1400179f0  test    ecx, ecx
0x1400179f2  jz      loc_140017B3B
0x1400179f8  mov     rbx, [r8+70h]
0x1400179fc  cmp     rbx, r14
0x1400179ff  jz      loc_140017B3B
0x140017a05  xor     esi, esi
0x140017a07  test    rbx, rbx
0x140017a0a  jz      loc_140017B19
0x140017a10  cmp     rbx, r14
0x140017a13  jz      loc_140017B19
0x140017a19  mov     rdi, [rbx+28h]
0x140017a1d  test    esi, esi
0x140017a1f  jz      short loc_140017A2D
0x140017a21  test    byte ptr [rdi+1Fh], 10h
0x140017a25  jnz     short loc_140017A69
0x140017a27  mov     rbx, [rbx+58h]
0x140017a2b  jmp     short loc_140017A07
0x140017a2d  mov     rdx, [r12]
0x140017a31  mov     rax, [rdi+100h]
0x140017a38  cmp     [rdx+100h], rax
0x140017a3f  mov     eax, [rdx+120h]
0x140017a45  jnz     loc_140017B00
0x140017a4b  mov     ecx, [rdi+120h]
0x140017a51  shr     eax, 8
0x140017a54  shr     ecx, 8
0x140017a57  xor     cx, ax
0x140017a5a  mov     eax, 1FFh
0x140017a5f  test    ax, cx
0x140017a62  jz      short loc_140017A21
0x140017a64  mov     esi, r13d
0x140017a67  jmp     short loc_140017A21
0x140017a69  test    byte ptr [rdi+1Ah], 8
0x140017a6d  jnz     short loc_140017A27
0x140017a6f  test    byte ptr [rdi+18h], 20h
0x140017a73  jnz     short loc_140017A27
0x140017a75  lea     r15, [rdi+58h]
0x140017a79  test    esi, esi
0x140017a7b  jnz     loc_140017B54
0x140017a81  mov     eax, [r15+8]
0x140017a85  lea     rdx, [r15+8]
0x140017a89  cmp     [rbp+350h+var_358.left], eax
0x140017a8c  jge     loc_140017B88
0x140017a92  mov     eax, [rbp+350h+var_358.right]
0x140017a95  cmp     [r15], eax
0x140017a98  jge     loc_140017B88
0x140017a9e  mov     eax, [r15+0Ch]
0x140017aa2  lea     rcx, [r15+0Ch]
0x140017aa6  cmp     [rbp+350h+var_358.top], eax
0x140017aa9  jge     loc_140017B88
0x140017aaf  mov     eax, [rbp+350h+var_358.bottom]
0x140017ab2  lea     rdi, [r15+4]
0x140017ab6  cmp     [rdi], eax
0x140017ab8  jge     loc_140017B88
0x140017abe  mov     eax, [rdx]
0x140017ac0  cmp     [r15], eax
0x140017ac3  jge     loc_140017B88
0x140017ac9  mov     eax, [rcx]
0x140017acb  mov     r15d, dword ptr [rsp+450h+var_3F0+0Ch]
0x140017ad0  cmp     [rdi], eax
  ... truncated ...
```
