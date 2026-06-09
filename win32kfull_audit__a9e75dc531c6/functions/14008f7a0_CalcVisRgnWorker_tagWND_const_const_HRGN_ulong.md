# CalcVisRgnWorker(tagWND const * const,HRGN__ * *,ulong)

- ea: `0x14008f7a0`
- end: `0x1400909db`
- name: `?CalcVisRgnWorker@@YAHQEBUtagWND@@PEAPEAUHRGN__@@K@Z`
- size: `4667`
- prototype: `__int64 __fastcall(struct tagWND *, HRGN *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140019be0`

## callees

- `0x140069bc8`
- `0x14008db30`
- `0x14008e458`
- `0x14008ee88`
- `0x14008eefc`
- `0x14008f0dc`
- `0x14008f7a0`
- `0x1400909e4`
- `0x140091448`
- `0x140091460`
- `0x140091ee8`
- `0x140091f38`
- `0x140091fbc`
- `0x140145a60`
- `0x1401dd4bc`
- `0x1401dd704`
- `0x1401dd800`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `win32kbase!PopThreadGuardedObject` at `0x140090586`
- `win32kbase!PopThreadGuardedObject` at `0x140090586`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140090884`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x140090884`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140090527`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140090527`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140090568`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140090568`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x14008fac6`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x14008ff33`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x14008fac6`
- `win32kbase!SetOrCreateRectRgnIndirectPublic` at `0x14008ff33`
- `win32kbase!SetRectRgnIndirect` at `0x140090660`
- `win32kbase!SetRectRgnIndirect` at `0x1400906ee`
- `win32kbase!SetRectRgnIndirect` at `0x140090660`
- `win32kbase!SetRectRgnIndirect` at `0x1400906ee`
- `win32kbase!CreateEmptyRgn` at `0x140090503`
- `win32kbase!CreateEmptyRgn` at `0x1400905a0`
- `win32kbase!CreateEmptyRgn` at `0x140090503`
- `win32kbase!CreateEmptyRgn` at `0x1400905a0`
- `win32kbase!GreCombineRgn` at `0x14008fb01`
- `win32kbase!GreCombineRgn` at `0x1400901de`
- `win32kbase!GreCombineRgn` at `0x140090335`
- `win32kbase!GreCombineRgn` at `0x140090684`
- `win32kbase!GreCombineRgn` at `0x1400906c1`
- `win32kbase!GreCombineRgn` at `0x1400908e3`
- `win32kbase!GreCombineRgn` at `0x14008fb01`
- `win32kbase!GreCombineRgn` at `0x1400901de`
- `win32kbase!GreCombineRgn` at `0x140090335`
- `win32kbase!GreCombineRgn` at `0x140090684`
- `win32kbase!GreCombineRgn` at `0x1400906c1`
- `win32kbase!GreCombineRgn` at `0x1400908e3`
- `win32kbase!IsWindowDesktopComposed` at `0x14009023c`
- `win32kbase!IsWindowDesktopComposed` at `0x14009023c`
- `win32kbase!ValidateHmonitorNoRip` at `0x14008fe4c`
- `win32kbase!ValidateHmonitorNoRip` at `0x14009094a`
- `win32kbase!ValidateHmonitorNoRip` at `0x14008fe4c`
- `win32kbase!ValidateHmonitorNoRip` at `0x14009094a`
- `win32kbase!GreDeleteObject` at `0x14008ff72`
- `win32kbase!GreDeleteObject` at `0x1400901f5`
- `win32kbase!GreDeleteObject` at `0x140090318`
- `win32kbase!GreDeleteObject` at `0x1400908f7`
- `win32kbase!GreDeleteObject` at `0x14009090b`
- `win32kbase!GreDeleteObject` at `0x14008ff72`
- `win32kbase!GreDeleteObject` at `0x1400901f5`
- `win32kbase!GreDeleteObject` at `0x140090318`
- `win32kbase!GreDeleteObject` at `0x1400908f7`
- `win32kbase!GreDeleteObject` at `0x14009090b`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14009082b`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x14009082b`
- `win32kbase!Win32FreePool` at `0x14008ff92`
- `win32kbase!Win32FreePool` at `0x1400905ce`
- `win32kbase!Win32FreePool` at `0x14008ff92`
- `win32kbase!Win32FreePool` at `0x1400905ce`

## pseudocode

```c
__int64 __fastcall CalcVisRgnWorker(struct tagWND *a1, HRGN *a2, unsigned int a3)
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
  __int64 v20; // r8
  struct tagWND *v21; // r15
  __int64 v22; // rdx
  int v23; // eax
  int v24; // r15d
  struct tagWND *v25; // r14
  char v26; // cl
  struct tagWND *v27; // r8
  int v28; // ecx
  unsigned int v29; // edi
  struct tagWND *v30; // r8
  __int64 v31; // rbx
  int v32; // esi
  __int64 v33; // rdi
  unsigned int v34; // eax
  bool v35; // zf
  LONG *v36; // r14
  LONG *v37; // rdx
  _DWORD *v38; // rcx
  _DWORD *v39; // rdi
  __int64 v40; // rax
  HRGN *v41; // r15
  __int64 v42; // r8
  struct tagWND *v43; // r8
  int v44; // r12d
  struct tagWND *v45; // rbx
  struct tagWND *v46; // rsi
  __int64 v47; // rcx
  struct tagWND *v48; // rbx
  int v49; // esi
  __int64 v50; // rdi
  unsigned int v51; // eax
  bool v52; // zf
  LONG *v53; // r15
  LONG *v54; // rdx
  _DWORD *v55; // rcx
  _DWORD *v56; // rdi
  __int64 v57; // rax
  __int64 v58; // rax
  char v59; // cl
  LONG right; // r8d
  LONG v61; // edx
  LONG top; // edx
  LONG v63; // eax
  LONG bottom; // ecx
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // r8
  char *v70; // rbx
  unsigned __int16 v71; // bx
  __int64 v72; // rax
  __int64 v73; // rbx
  __int64 v74; // r8
  __int64 v75; // rcx
  LONG v76; // edx
  LONG v77; // ecx
  LONG v78; // edx
  LONG v79; // ecx
  __int64 v81; // rdx
  struct tagWND *v82; // rax
  LONG v83; // edx
  LONG v84; // r8d
  LONG v85; // edx
  LONG v86; // ecx
  int v87; // ecx
  __int64 v88; // rdx
  __int64 v89; // rdx
  unsigned int v90; // eax
  int v91; // r14d
  struct tagWND *v92; // rdi
  int v93; // r15d
  int v94; // eax
  struct tagWND *v95; // rdi
  struct _RECTL *v96; // r14
  int v97; // edi
  int v98; // r12d
  int v99; // esi
  char *v100; // r15
  struct tagWND *v101; // r13
  __int64 v102; // r9
  __int64 v103; // r8
  const struct tagWND *v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // rbx
  int *p_left; // rbx
  const struct tagWND *v108; // r9
  unsigned int v109; // eax
  bool v110; // zf
  const struct tagWND *TopLevelOrDpiBoundaryWindow; // rax
  const struct tagWND *v112; // rax
  __int64 v113; // rax
  int v114; // edx
  int v115; // eax
  float *v116; // rdx
  float v117; // xmm5_4
  float v118; // xmm4_4
  float v119; // xmm5_4
  HRGN *v120; // rbx
  HRGN EmptyRgn; // rax
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rbx
  __int64 v127; // rax
  __int64 v128; // r15
  __int64 v129; // r9
  float *v130; // rax
  __int64 v131; // r11
  float *v132; // rdx
  __int64 v133; // r11
  int v134; // r9d
  float v135; // xmm0_4
  __int64 v136; // rax
  int v137; // ecx
  int v138; // edx
  __int64 v139; // rdi
  __int64 v140; // r15
  unsigned __int16 WindowCoordinateSpaceDpi; // bx
  __int64 v142; // rbx
  __int64 v143; // r8
  int v144; // [rsp+38h] [rbp-D0h]
  struct tagWND *v145; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v146; // [rsp+48h] [rbp-C0h]
  __int128 v147; // [rsp+50h] [rbp-B8h] BYREF
  struct _RECTL *v148; // [rsp+60h] [rbp-A8h]
  __int64 v149; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v150; // [rsp+70h] [rbp-98h] BYREF
  __int128 v151; // [rsp+80h] [rbp-88h]
  __int64 v152; // [rsp+90h] [rbp-78h]
  int v153; // [rsp+98h] [rbp-70h]
  HRGN *v154; // [rsp+A0h] [rbp-68h]
  struct tagWND *v155; // [rsp+A8h] [rbp-60h]
  char *v156; // [rsp+B0h] [rbp-58h]
  _DWORD v157[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v158; // [rsp+C8h] [rbp-40h] BYREF
  char v159[40]; // [rsp+D0h] [rbp-38h] BYREF
  int v160; // [rsp+F8h] [rbp-10h]
  struct _RECTL v161; // [rsp+100h] [rbp-8h] BYREF
  __int128 v162; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v163[240]; // [rsp+128h] [rbp+20h] BYREF
  struct _RECTL v164; // [rsp+218h] [rbp+110h] BYREF

  v3 = a1;
  v4 = a3;
  v146 = a3;
  v154 = a2;
  v145 = a1;
  v161 = 0;
  memset_0(v163, 0, sizeof(v163));
  v5 = *((_QWORD *)v3 + 13);
  v6 = 0;
  v152 = 0;
  v7 = 1;
  v150 = 0;
  v151 = 0;
  if ( !v5
    || (v8 = *((_QWORD *)v3 + 3)) != 0 && (v9 = *(_QWORD *)(v8 + 8)) != 0 && v5 == *(_QWORD *)(v9 + 24)
    || (v10 = *(_QWORD *)(v5 + 40),
        v11 = (char *)v3 + 40,
        v156 = (char *)v3 + 40,
        (((unsigned __int16)(*(_DWORD *)(*((_QWORD *)v3 + 5) + 288LL) >> 8)
        ^ (unsigned __int16)(*(_DWORD *)(v10 + 288) >> 8))
       & 0x1FF) == 0) )
  {
    v11 = (char *)v3 + 40;
    goto LABEL_7;
  }
  WindowCoordinateSpaceDpi = GetWindowCoordinateSpaceDpi(v3);
  if ( WindowCoordinateSpaceDpi == GetWindowCoordinateSpaceDpi(*((const struct tagWND **)v145 + 13)) )
  {
    v142 = ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)v11 + 256LL));
    if ( v142 )
    {
      v143 = *(_DWORD *)(*(_QWORD *)v11 + 288LL) >> 8;
      LOWORD(v143) = v143 & 0x1FF;
      GetMonitorRectForDpi(&v147, v142, v143);
      if ( *(_QWORD *)(*(_QWORD *)(v142 + 40) + 28LL) != (_QWORD)v147 )
      {
        v3 = v145;
        v12 = 1;
        v144 = 1;
        goto LABEL_8;
      }
    }
    v3 = v145;
LABEL_7:
    v12 = 0;
    v144 = 0;
LABEL_8:
    v156 = v11;
    goto LABEL_9;
  }
  v3 = v145;
  v12 = 1;
  v144 = 1;
LABEL_9:
  v13 = *(_QWORD *)v11;
  if ( (v4 & 1) != 0 )
  {
    v15 = *(struct _RECTL *)(v13 + 88);
    v161 = v15;
    left = v15.left;
    v161.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v15, 12));
    v16 = (__m128i)v15;
  }
  else
  {
    v161 = *(struct _RECTL *)(v13 + 104);
    right = v161.right;
    v61 = _mm_cvtsi128_si32((__m128i)v161);
    if ( v61 <= *(_DWORD *)(v13 + 88) )
      v61 = *(_DWORD *)(v13 + 88);
    v161.left = v61;
    if ( v161.right >= *(_DWORD *)(v13 + 96) )
      right = *(_DWORD *)(v13 + 96);
    v161.right = right;
    if ( v61 < right )
    {
      top = v161.top;
      if ( v161.top <= *(_DWORD *)(v13 + 92) )
        top = *(_DWORD *)(v13 + 92);
      v161.top = top;
      v63 = *(_DWORD *)(v13 + 100);
      bottom = v161.bottom;
      if ( v161.bottom >= v63 )
        bottom = v63;
      v161.bottom = bottom;
      if ( top < bottom )
        goto LABEL_12;
    }
    left = 0;
    v15 = 0;
    v161 = 0;
    v161.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v16 = 0;
  }
  v161.top = _mm_cvtsi128_si32(_mm_srli_si128(v16, 4));
  v161.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v15, 8));
  v161.left = left;
LABEL_12:
  v17 = *((_QWORD *)v3 + 13);
  if ( !v17 )
    goto LABEL_132;
  v18 = *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v3 + 3) + 8LL) + 24LL);
  v149 = (__int64)v18;
  v19 = (struct tagWND *)*((_QWORD *)v18 + 13);
  v155 = v19;
  if ( (struct tagWND *)v17 == v19 && (*(_WORD *)(*(_QWORD *)v11 + 42LL) & 0x2FFF) != 0x29D )
    goto LABEL_132;
  v20 = v146;
  v21 = v3;
  v153 = 0;
  v22 = v146 & 0x4000;
  LODWORD(v148) = v146 & 0x4000;
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
    if ( (_DWORD)v22 )
    {
      v87 = *(_DWORD *)(*((_QWORD *)v21 + 5) + 24LL);
      if ( ((v87 & 0x80000) != 0 || (v87 & 0x20000000) != 0) && ((v87 & 0x2000000) == 0 || (struct tagWND *)v17 == v18) )
      {
        v23 = v22;
        goto LABEL_16;
      }
    }
    if ( (v20 & 0x8000000) != 0 && (*(_WORD *)(*(_QWORD *)(v17 + 40) + 42LL) & 0x2FFF) == 0x29D )
    {
      v94 = IsWindowDesktopComposed(v17, v22, v20, v18);
      v12 = v144;
      if ( v94 )
        break;
    }
    v65 = v153;
    v66 = *(_QWORD *)(v17 + 40);
    if ( *(_QWORD *)(v66 + 168) )
      v65 = 1;
    v153 = v65;
    if ( !v12 )
    {
      v67 = *(_QWORD *)(v17 + 104);
      if ( !v67
        || (v68 = *(_QWORD *)(v17 + 24)) != 0 && (v69 = *(_QWORD *)(v68 + 8)) != 0 && v67 == *(_QWORD *)(v69 + 24)
        || (((unsigned __int16)(*(_DWORD *)(v66 + 288) >> 8)
           ^ (unsigned __int16)(*(_DWORD *)(*(_QWORD *)(v67 + 40) + 288LL) >> 8))
          & 0x1FF) == 0 )
      {
        v70 = (char *)v3 + 224;
        v147 = *(_OWORD *)(v66 + 104);
LABEL_120:
        PhysicalToLogicalInPlaceRect(v21, &v147);
        goto LABEL_121;
      }
      v71 = GetWindowCoordinateSpaceDpi((const struct tagWND *)v17);
      if ( v71 != GetWindowCoordinateSpaceDpi(*(const struct tagWND **)(v17 + 104))
        || (v72 = ValidateHmonitorNoRip(*(_QWORD *)(*(_QWORD *)(v17 + 40) + 256LL)), (v73 = v72) != 0)
        && ((v74 = *(_DWORD *)(*(_QWORD *)(v17 + 40) + 288LL) >> 8,
             LOWORD(v74) = v74 & 0x1FF,
             GetMonitorRectForDpi(v157, v72, v74),
             v75 = *(_QWORD *)(v73 + 40),
             *(_DWORD *)(v75 + 28) != v157[0])
         || *(_DWORD *)(v75 + 32) != v157[1]) )
      {
        v144 = 1;
        v82 = v145;
        v147 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 104LL);
        v70 = (char *)v145 + 224;
        goto LABEL_148;
      }
      v12 = v144;
      v3 = v145;
    }
    v70 = (char *)v3 + 224;
    v147 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 104LL);
    if ( !v12 )
      goto LABEL_120;
    v82 = v145;
LABEL_148:
    if ( (unsigned int)DpiRectContainsRectWithSubpixel(&v147, v17 + 224, v17, &v161, v70, v82) )
      goto LABEL_149;
    LogicalToPhysicalInPlaceRectWithSubpixel(v17, &v147, 0);
    PhysicalToLogicalInPlaceRectWithSubpixel(v145, &v147, 0);
LABEL_121:
    v76 = v161.left;
    v77 = v161.right;
    if ( v161.left <= (int)v147 )
      v76 = v147;
    v161.left = v76;
    if ( v161.right >= SDWORD2(v147) )
      v77 = DWORD2(v147);
    v161.right = v77;
    if ( v76 >= v77 )
      goto LABEL_131;
    v78 = v161.top;
    v79 = v161.bottom;
    if ( v161.top <= SDWORD1(v147) )
      v78 = DWORD1(v147);
    v161.top = v78;
    if ( v161.bottom >= SHIDWORD(v147) )
      v79 = HIDWORD(v147);
    v161.bottom = v79;
    if ( v78 >= v79 )
    {
LABEL_131:
      v161 = 0;
      goto LABEL_132;
    }
LABEL_149:
    v147 = *(_OWORD *)(*(_QWORD *)(v17 + 40) + 88LL);
    if ( v144 )
    {
      if ( (unsigned int)DpiRectContainsRectWithSubpixel(&v147, v17 + 224, v17, &v161, v70, v145) )
        goto LABEL_161;
      LogicalToPhysicalInPlaceRectWithSubpixel(v17, &v147, 0);
      PhysicalToLogicalInPlaceRectWithSubpixel(v145, &v147, 0);
    }
    else
    {
      PhysicalToLogicalInPlaceRect(v21, &v147);
    }
    v83 = v161.left;
    v84 = v161.right;
    if ( v161.left <= (int)v147 )
      v83 = v147;
    v161.left = v83;
    if ( v161.right >= SDWORD2(v147) )
      v84 = DWORD2(v147);
    v161.right = v84;
    if ( v83 >= v84 )
      goto LABEL_131;
    v85 = v161.top;
    v86 = v161.bottom;
    if ( v161.top <= SDWORD1(v147) )
      v85 = DWORD1(v147);
    v161.top = v85;
    if ( v161.bottom >= SHIDWORD(v147) )
      v86 = HIDWORD(v147);
    v161.bottom = v86;
    if ( v85 >= v86 )
      goto LABEL_131;
LABEL_161:
    v22 = (unsigned int)v148;
    v21 = (struct tagWND *)v17;
    v17 = *(_QWORD *)(v17 + 104);
    v18 = (struct tagWND *)v149;
    v3 = v145;
    v19 = v155;
    v12 = v144;
    v20 = v146;
  }
  LODWORD(v22) = (_DWORD)v148;
  v23 = (int)v148;
  v18 = (struct tagWND *)v149;
  v19 = v155;
  LOBYTE(v20) = v146;
LABEL_16:
  *((_QWORD *)&v151 + 1) = v163;
  v24 = 0;
  *(_QWORD *)((char *)&v150 + 4) = 0x1E00000000LL;
  *(_QWORD *)&v151 = v163;
  v25 = v3;
  v26 = v20;
  v27 = (struct tagWND *)*((_QWORD *)v3 + 13);
  v28 = v26 & 0x10;
  while ( 2 )
  {
    *(_QWORD *)&v147 = v27;
    if ( v27 != v19 )
    {
      if ( v23 )
      {
        v81 = *((_QWORD *)v25 + 5);
        if ( (*(_BYTE *)(v81 + 27) & 0x20) != 0 && ((*(_DWORD *)(v81 + 24) & 0x2000000) == 0 || v27 == v18) )
          break;
        LODWORD(v22) = (_DWORD)v148;
      }
      if ( !v28 || (v48 = (struct tagWND *)*((_QWORD *)v27 + 14), v48 == v25) )
      {
LABEL_87:
        v58 = *((_QWORD *)v27 + 5);
        v25 = v27;
        v27 = (struct tagWND *)*((_QWORD *)v27 + 13);
        v59 = *(_BYTE *)(v58 + 31);
        v23 = v22;
        v28 = v59 & 4;
        continue;
      }
      v49 = 0;
      while ( 1 )
      {
        if ( !v48 || v48 == v25 )
        {
          v27 = (struct tagWND *)v147;
          LODWORD(v22) = (_DWORD)v148;
          v18 = (struct tagWND *)v149;
          v19 = v155;
          if ( v49 )
          {
            v12 = 1;
            v144 = 1;
          }
          else
          {
            v12 = v144;
          }
          goto LABEL_87;
        }
        v50 = *((_QWORD *)v48 + 5);
        if ( !v49 )
        {
          v51 = *(_DWORD *)(*(_QWORD *)v11 + 288LL);
          if ( *(_QWORD *)(*(_QWORD *)v11 + 256LL) == *(_QWORD *)(v50 + 256) )
          {
            v52 = (((unsigned __int16)(v51 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v50 + 288) >> 8)) & 0x1FF) == 0;
          }
          else
          {
            if ( (v51 & 0xF) != 2 )
            {
LABEL_71:
              v49 = 1;
              goto LABEL_66;
            }
            v52 = (*(_DWORD *)(v50 + 288) & 0xF) == 2;
          }
          if ( !v52 )
            goto LABEL_71;
        }
LABEL_66:
        if ( (*(_BYTE *)(v50 + 31) & 0x10) == 0 || (*(_BYTE *)(v50 + 26) & 8) != 0 || (*(_BYTE *)(v50 + 24) & 0x20) != 0 )
          goto LABEL_67;
        v53 = (LONG *)(v50 + 88);
        if ( v49 )
        {
          if ( !(unsigned int)DpiRectIntersectsRectWithSubpixel(
                                v50 + 88,
                                (char *)v48 + 224,
                                v48,
                                &v161,
                                (char *)v145 + 224,
                                v145) )
            goto LABEL_89;
          v54 = (LONG *)(v50 + 96);
          v55 = (_DWORD *)(v50 + 100);
          v56 = (_DWORD *)(v50 + 92);
        }
        else
        {
          v54 = (LONG *)(v50 + 96);
          if ( v161.left >= *(_DWORD *)(v50 + 96)
            || *v53 >= v161.right
            || (v55 = (_DWORD *)(v50 + 100), v161.top >= *(_DWORD *)(v50 + 100))
            || (v56 = (_DWORD *)(v50 + 92), v53[1] >= v161.bottom) )
          {
LABEL_89:
            v24 = DWORD1(v150);
LABEL_67:
            v48 = (struct tagWND *)*((_QWORD *)v48 + 11);
            continue;
          }
        }
        if ( *v53 >= *v54 )
          goto LABEL_89;
        v24 = DWORD1(v150);
        if ( *v56 >= *v55 )
          goto LABEL_67;
        if ( DWORD1(v150) == DWORD2(v150) )
        {
          if ( !(unsigned int)ResizeVisExcludeMemory((struct _CalcVisRgnData *)&v150) )
            goto LABEL_187;
          v24 = DWORD1(v150);
        }
        v57 = v24++;
        DWORD1(v150) = v24;
        *(_QWORD *)(v151 + 8 * v57) = v48;
        v48 = (struct tagWND *)*((_QWORD *)v48 + 11);
      }
    }
    break;
  }
  v29 = v146;
  if ( (v146 & 8) != 0 )
  {
    v30 = v145;
    v31 = *((_QWORD *)v145 + 14);
    if ( v31 )
    {
      v32 = 0;
      while ( 1 )
      {
        if ( !v31 )
        {
          v29 = v146;
          if ( v32 )
          {
            v12 = 1;
            v144 = 1;
          }
          else
          {
            v12 = v144;
          }
          break;
        }
        v33 = *(_QWORD *)(v31 + 40);
        if ( !v32 )
        {
          v34 = *(_DWORD *)(*(_QWORD *)v11 + 288LL);
          if ( *(_QWORD *)(*(_QWORD *)v11 + 256LL) == *(_QWORD *)(v33 + 256) )
          {
            v35 = (((unsigned __int16)(v34 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v33 + 288) >> 8)) & 0x1FF) == 0;
          }
          else
          {
            if ( (v34 & 0xF) != 2 )
            {
LABEL_28:
              v32 = 1;
              goto LABEL_23;
            }
            v35 = (*(_DWORD *)(v33 + 288) & 0xF) == 2;
          }
          if ( !v35 )
            goto LABEL_28;
        }
LABEL_23:
        if ( (*(_BYTE *)(v33 + 31) & 0x10) != 0 && (*(_BYTE *)(v33 + 26) & 8) == 0 && (*(_BYTE *)(v33 + 24) & 0x20) == 0 )
        {
          v36 = (LONG *)(v33 + 88);
          if ( v32 )
          {
            if ( !(unsigned int)DpiRectIntersectsRectWithSubpixel(
                                  v33 + 88,
                                  v31 + 224,
                                  v31,
                                  &v161,
                                  (char *)v30 + 224,
                                  v30) )
              goto LABEL_24;
            v37 = (LONG *)(v33 + 96);
            v38 = (_DWORD *)(v33 + 100);
            v39 = (_DWORD *)(v33 + 92);
          }
          else
          {
            v37 = (LONG *)(v33 + 96);
            if ( v161.left >= *(_DWORD *)(v33 + 96) )
              goto LABEL_24;
            if ( *v36 >= v161.right )
              goto LABEL_24;
            v38 = (_DWORD *)(v33 + 100);
            if ( v161.top >= *(_DWORD *)(v33 + 100) )
              goto LABEL_24;
            v39 = (_DWORD *)(v33 + 92);
            if ( v36[1] >= v161.bottom )
              goto LABEL_24;
          }
          if ( *v36 < *v37 && *v39 < *v38 )
          {
            if ( v24 == DWORD2(v150) )
            {
              if ( !(unsigned int)ResizeVisExcludeMemory((struct _CalcVisRgnData *)&v150) )
                goto LABEL_187;
              v24 = DWORD1(v150);
            }
            v40 = v24++;
            DWORD1(v150) = v24;
            *(_QWORD *)(v151 + 8 * v40) = v31;
          }
        }
LABEL_24:
        v31 = *(_QWORD *)(v31 + 88);
        v30 = v145;
      }
    }
  }
  if ( v24 <= 0 )
  {
    if ( *(char *)(*(_QWORD *)v11 + 19LL) < 0 )
      v161 = 0;
    v41 = v154;
    if ( (unsigned int)SetOrCreateRectRgnIndirectPublic(v154, &v161) )
    {
      v6 = v152;
      *(_QWORD *)&v147 = v152;
      goto LABEL_51;
    }
    goto LABEL_187;
  }
  if ( v24 > 30 )
  {
    v148 = (struct _RECTL *)Win32AllocPoolWithQuotaZInit(16LL * v24, 1769370453);
    v96 = v148;
    if ( !v148 )
    {
LABEL_187:
      v6 = v152;
LABEL_132:
      v162 = 0;
      SetOrCreateRectRgnIndirectPublic(v154, &v162);
      v7 = 0;
      goto LABEL_133;
    }
    v12 = v144;
  }
  else
  {
    v96 = &v164;
    v148 = &v164;
  }
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v100 = v156;
  v101 = v145;
  v102 = v151;
  while ( 2 )
  {
    v103 = v99;
    v104 = *(const struct tagWND **)(v102 + 8LL * v99);
    v105 = *((_QWORD *)v104 + 5);
    if ( *(_QWORD *)(v105 + 168) )
    {
      v127 = v98++;
      *(_QWORD *)(v102 + 8 * v127) = v104;
    }
    else
    {
      v106 = v97++;
      p_left = &v96[v106].left;
      *(_OWORD *)p_left = *(_OWORD *)(v105 + 88);
      if ( v12 )
      {
        v105 = *(_QWORD *)v100;
        v108 = *(const struct tagWND **)(v102 + 8LL * v99);
        v104 = (const struct tagWND *)*((_QWORD *)v108 + 5);
        v109 = *(_DWORD *)(*(_QWORD *)v100 + 288LL);
        if ( *(_QWORD *)(*(_QWORD *)v100 + 256LL) == *((_QWORD *)v104 + 32) )
        {
          v104 = (const struct tagWND *)(*((_DWORD *)v104 + 72) >> 8);
          LOWORD(v104) = (v109 >> 8) ^ (unsigned __int16)v104;
          v110 = ((unsigned __int16)v104 & 0x1FF) == 0;
          goto LABEL_202;
        }
        if ( (v109 & 0xF) != 2 )
          goto LABEL_203;
        v110 = (*((_DWORD *)v104 + 72) & 0xF) == 2;
LABEL_202:
        if ( !v110 )
        {
LABEL_203:
          TopLevelOrDpiBoundaryWindow = GetTopLevelOrDpiBoundaryWindow(v108);
          if ( TopLevelOrDpiBoundaryWindow )
          {
            v130 = (float *)*((_QWORD *)TopLevelOrDpiBoundaryWindow + 27);
            if ( v130 )
            {
              ScaleValueWithSubpixel(p_left, 0, *v130);
              ScaleValueWithSubpixel(p_left + 1, v132, *(float *)(*(_QWORD *)(v131 + 216) + 20LL));
              v134 = (int)(float)((float)((float)((float)p_left[2] * **(float **)(v133 + 216)) + 0.0) + 0.5);
              p_left[2] = v134;
              v135 = (float)((float)((float)p_left[3] * *(float *)(*(_QWORD *)(v133 + 216) + 20LL)) + 0.0) + 0.5;
              p_left[3] = (int)v135;
              v136 = *(_QWORD *)(v133 + 216);
              v137 = (int)*(float *)(v136 + 48);
              v138 = (int)*(float *)(v136 + 52);
              *p_left += v137;
              p_left[2] = v134 + v137;
              p_left[1] += v138;
              p_left[3] = (int)v135 + v138;
            }
          }
          v112 = GetTopLevelOrDpiBoundaryWindow(v101);
          v104 = v112;
          if ( v112 )
          {
            v113 = *((_QWORD *)v112 + 27);
            if ( v113 )
            {
              v114 = (int)*(float *)(v113 + 52);
              v115 = (int)*(float *)(v113 + 48);
              p_left[3] -= v114;
              p_left[1] -= v114;
              *p_left -= v115;
              p_left[2] -= v115;
              ScaleValueWithSubpixel(p_left, 0, 1.0 / **((float **)v104 + 27));
              ScaleValueWithSubpixel(p_left + 1, v116, v117);
              p_left[2] = (int)(float)((float)((float)((float)p_left[2] * v118) + 0.0) + 0.5);
              p_left[3] = (int)(float)((float)((float)((float)p_left[3] * v119) + 0.0) + 0.5);
            }
          }
        }
        v102 = v151;
      }
    }
    v12 = v144;
    if ( ++v99 < SDWORD1(v150) )
      continue;
    break;
  }
  v7 = 1;
  v120 = v154;
  EmptyRgn = *v154;
  if ( !*v154 )
  {
    EmptyRgn = (HRGN)CreateEmptyRgn(v104, v105, v103, v102);
    *v120 = EmptyRgn;
  }
  if ( v97 )
  {
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v158, EmptyRgn, 0, 0);
    if ( v158 )
    {
      if ( RGNOBJAPI::bSubtract((RGNOBJAPI *)&v158, &v161, v96, v97) )
      {
        RGNOBJ::iComplexity((RGNOBJ *)&v158);
      }
      else if ( v158 )
      {
        RGNOBJ::vSet((RGNOBJ *)&v158);
      }
    }
    if ( !v160 )
      RGNOBJ::UpdateUserRgn((RGNOBJ *)&v158);
    if ( v158 )
      _InterlockedDecrement16((volatile signed __int16 *)(v158 + 12));
    PopThreadGuardedObject(v159);
  }
  else
  {
    SetRectRgnIndirect(EmptyRgn, &v161);
  }
  v6 = v152;
  *(_QWORD *)&v147 = v152;
  if ( !v152 )
  {
    v6 = CreateEmptyRgn(v123, v122, v124, v125);
    *(_QWORD *)&v147 = v6;
  }
  v126 = 0;
  if ( v98 > 0 )
  {
    v128 = v151;
    do
    {
      SetRectRgnIndirect(v6, *(_QWORD *)(*(_QWORD *)(v128 + 8 * v126) + 40LL) + 88LL);
      GreCombineRgn(v6, v6, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v128 + 8 * v126) + 40LL) + 168LL), 1);
      if ( v144 && IsDpiBoundaryBetweenWindows(v145, *(const struct tagWND **)(v128 + 8 * v126)) )
      {
        v149 = v6;
        v139 = 0;
        v140 = 0;
        if ( (unsigned int)LogicalToPhysicalInPlaceRgnWorker(v129, &v149, 1) )
          v139 = v149;
        if ( (unsigned int)PhysicalToLogicalInPlaceRgnWorker(v145) )
          v140 = v149;
        if ( v149 != v6 )
          GreCombineRgn(v6, v149, 0, 5);
        if ( v139 )
          GreDeleteObject(v139);
        if ( v140 )
          GreDeleteObject(v140);
        v128 = v151;
      }
      if ( (unsigned int)GreCombineRgn(*v154, *v154, v6, 4) == 1 )
        break;
      v126 = (unsigned int)(v126 + 1);
    }
    while ( (int)v126 < v98 );
    v96 = v148;
  }
  if ( v96 != &v164 )
    Win32FreePool(v96);
  v41 = v154;
  v29 = v146;
LABEL_51:
  v42 = *(_QWORD *)(*((_QWORD *)v145 + 5) + 168LL);
  if ( v42 )
    GreCombineRgn(*v41, *v41, v42, 1);
  if ( v153 )
  {
    v43 = v145;
    v44 = 0;
    v45 = (struct tagWND *)*((_QWORD *)v145 + 13);
    if ( v45 != v155 )
    {
      v46 = v145;
      while ( 2 )
      {
        v47 = *((_QWORD *)v45 + 5);
        v145 = *(struct tagWND **)(v47 + 168);
        if ( !v145 )
          goto LABEL_57;
        v88 = *((_QWORD *)v43 + 5);
        if ( (*(_BYTE *)(v88 + 26) & 8) != 0 && (*(_DWORD *)(v88 + 232) & 2) == 0 )
        {
          v44 = 1;
          goto LABEL_232;
        }
        if ( (v29 & 0x1000000) != 0 )
        {
          v44 = 1;
          goto LABEL_232;
        }
        if ( v44 )
        {
LABEL_232:
          if ( (*(_WORD *)(v47 + 42) & 0x2FFF) == 0x29D )
          {
LABEL_58:
            v6 = v147;
            goto LABEL_133;
          }
        }
        v89 = *((_QWORD *)v46 + 5);
        v90 = *(_DWORD *)(v89 + 288);
        if ( *(_QWORD *)(v89 + 256) == *(_QWORD *)(v47 + 256) )
        {
          if ( (((unsigned __int16)(v90 >> 8) ^ (unsigned __int16)(*(_DWORD *)(v47 + 288) >> 8)) & 0x1FF) == 0 )
            goto LABEL_174;
LABEL_190:
          v95 = 0;
          if ( (unsigned int)LogicalToPhysicalInPlaceRgnWorker(v45, &v145, 1) )
            v95 = v145;
          v91 = PhysicalToLogicalInPlaceRgnWorker(v46);
          if ( v91 && v95 )
          {
            GreDeleteObject(v95);
            v92 = v145;
            v93 = GreCombineRgn(*v41, *v41, v145, 1);
LABEL_176:
            GreDeleteObject(v92);
LABEL_177:
            if ( v93 == 1 )
              goto LABEL_58;
LABEL_57:
            v29 = v146;
            v43 = v45;
            v45 = (struct tagWND *)*((_QWORD *)v45 + 13);
            v41 = v154;
            if ( v45 == v155 )
              goto LABEL_58;
            continue;
          }
        }
        else
        {
          if ( (v90 & 0xF) != 2 || (*(_DWORD *)(v47 + 288) & 0xF) != 2 )
            goto LABEL_190;
LABEL_174:
          v91 = PhysicalToLogicalInPlaceRgn(v43, &v145);
        }
        break;
      }
      v92 = v145;
      v93 = GreCombineRgn(*v41, *v41, v145, 1);
      if ( v91 )
        goto LABEL_176;
      goto LABEL_177;
    }
  }
LABEL_133:
  if ( v6 )
    GreDeleteObject(v6);
  if ( (_DWORD)v150 )
    Win32FreePool((void *)v151);
  return v7;
}

```

## disassembly

```asm
0x14008f7a0  mov     r11, rsp
0x14008f7a3  push    rbp
0x14008f7a4  push    r13
0x14008f7a6  lea     rbp, [r11-358h]
0x14008f7ad  sub     rsp, 448h
0x14008f7b4  mov     rax, cs:__security_cookie
0x14008f7bb  xor     rax, rsp
0x14008f7be  mov     [rbp+350h+var_60], rax
0x14008f7c5  mov     [r11+18h], rbx
0x14008f7c9  xorps   xmm0, xmm0
0x14008f7cc  mov     [r11-18h], rsi
0x14008f7d0  mov     rbx, rcx
0x14008f7d3  mov     [r11-20h], rdi
0x14008f7d7  mov     edi, r8d
0x14008f7da  mov     dword ptr [rsp+450h+var_410], r8d
0x14008f7df  mov     r8d, 0F0h; Size
0x14008f7e5  mov     [rbp+350h+var_3B8], rdx
0x14008f7e9  xor     edx, edx; Val
0x14008f7eb  mov     [rsp+450h+var_418], rcx
0x14008f7f0  lea     rcx, [rbp+350h+var_330]; void *
0x14008f7f4  mov     [r11-28h], r12
0x14008f7f8  mov     [r11-30h], r14
0x14008f7fc  movups  xmmword ptr [rbp+350h+var_358.left], xmm0
0x14008f800  call    memset_0
0x14008f805  mov     rax, [rbx+68h]
0x14008f809  xor     esi, esi
0x14008f80b  mov     [rbp+350h+var_3C8], rsi
0x14008f80f  xorps   xmm0, xmm0
0x14008f812  mov     r13d, 1
0x14008f818  mov     r14d, 1FFh
0x14008f81e  movups  [rsp+450h+var_3F0+8], xmm0
0x14008f823  movups  [rsp+450h+var_3E0+8], xmm0
0x14008f828  test    rax, rax
0x14008f82b  jz      short loc_14008F874
0x14008f82d  mov     rcx, [rbx+18h]
0x14008f831  test    rcx, rcx
0x14008f834  jz      short loc_14008F845
0x14008f836  mov     rdx, [rcx+8]
0x14008f83a  test    rdx, rdx
0x14008f83d  jz      short loc_14008F845
0x14008f83f  cmp     rax, [rdx+18h]
0x14008f843  jz      short loc_14008F874
0x14008f845  mov     rax, [rax+28h]
0x14008f849  lea     r12, [rbx+28h]
0x14008f84d  mov     [rbp+350h+var_3A8], r12
0x14008f851  mov     edx, [rax+120h]
0x14008f857  mov     rax, [r12]
0x14008f85b  shr     edx, 8
0x14008f85e  mov     ecx, [rax+120h]
0x14008f864  shr     ecx, 8
0x14008f867  xor     dx, cx
0x14008f86a  test    r14w, dx
0x14008f86e  jnz     loc_140090921
0x14008f874  lea     r12, [rbx+28h]
0x14008f878  xor     r11d, r11d
0x14008f87b  mov     dword ptr [rsp+450h+var_420], r11d
0x14008f880  mov     [rbp+350h+var_3A8], r12
0x14008f884  mov     rcx, [r12]
0x14008f888  test    r13b, dil
0x14008f88b  jz      loc_14008FD12
0x14008f891  movups  xmm2, xmmword ptr [rcx+58h]
0x14008f895  movdqa  xmm0, xmm2
0x14008f899  movdqa  xmm1, xmm2
0x14008f89d  psrldq  xmm0, 0Ch
0x14008f8a2  movups  xmmword ptr [rbp+350h+var_358.left], xmm2
0x14008f8a6  movd    [rbp+350h+var_358.bottom], xmm0
0x14008f8ab  movdqa  xmm0, xmm2
0x14008f8af  psrldq  xmm0, 4
0x14008f8b4  psrldq  xmm1, 8
0x14008f8b9  movd    [rbp+350h+var_358.top], xmm0
0x14008f8be  movd    [rbp+350h+var_358.right], xmm1
0x14008f8c3  movss   [rbp+350h+var_358.left], xmm2
0x14008f8c8  mov     rdi, [rbx+68h]
0x14008f8cc  mov     [rsp+450h+var_30], r15
0x14008f8d4  test    rdi, rdi
0x14008f8d7  jz      loc_14008FF23
0x14008f8dd  mov     rax, [rbx+18h]
0x14008f8e1  mov     rcx, [rax+8]
0x14008f8e5  mov     r9, [rcx+18h]
0x14008f8e9  mov     qword ptr [rsp+450h+var_3F0], r9
0x14008f8ee  mov     r10, [r9+68h]
0x14008f8f2  mov     [rbp+350h+var_3B0], r10
0x14008f8f6  cmp     rdi, r10
0x14008f8f9  jz      loc_140090104
0x14008f8ff  mov     r8d, dword ptr [rsp+450h+var_410]
0x14008f904  mov     r15, rbx
0x14008f907  mov     edx, r8d
0x14008f90a  mov     [rbp+350h+var_3C0], esi
0x14008f90d  and     edx, 4000h
0x14008f913  mov     dword ptr [rsp+450h+var_3F8], edx
0x14008f917  mov     eax, edx
0x14008f919  cmp     rdi, r10
0x14008f91c  jnz     loc_14008FD83
0x14008f922  lea     rcx, [rbp+350h+var_330]
0x14008f926  mov     dword ptr [rsp+450h+var_3E0], 1Eh
0x14008f92e  mov     [rbp+350h+var_3D0], rcx
0x14008f932  xor     r15d, r15d
0x14008f935  lea     rcx, [rbp+350h+var_330]
0x14008f939  mov     dword ptr [rsp+450h+var_3F0+0Ch], r15d
0x14008f93e  mov     qword ptr [rsp+450h+var_3E0+8], rcx
0x14008f943  mov     r14, rbx
0x14008f946  mov     ecx, r8d
0x14008f949  mov     r8, [rbx+68h]
0x14008f94d  and     ecx, 10h
0x14008f950  mov     qword ptr [rsp+450h+var_410+8], r8
0x14008f955  cmp     r8, r10
0x14008f958  jnz     loc_14008FB68
0x14008f95e  mov     edi, dword ptr [rsp+450h+var_410]
0x14008f962  test    dil, 8
0x14008f966  jz      loc_14008FAA1
0x14008f96c  mov     r8, [rsp+450h+var_418]
0x14008f971  mov     rbx, [r8+70h]
0x14008f975  test    rbx, rbx
0x14008f978  jz      loc_14008FAA1
0x14008f97e  xor     esi, esi
0x14008f980  test    rbx, rbx
0x14008f983  jz      loc_14008FA90
0x14008f989  mov     rdi, [rbx+28h]
0x14008f98d  test    esi, esi
0x14008f98f  jz      short loc_14008F9A2
0x14008f991  test    byte ptr [rdi+1Fh], 10h
0x14008f995  jnz     short loc_14008F9DE
0x14008f997  mov     rbx, [rbx+58h]
0x14008f99b  mov     r8, [rsp+450h+var_418]
0x14008f9a0  jmp     short loc_14008F980
0x14008f9a2  mov     rdx, [r12]
0x14008f9a6  mov     rax, [rdi+100h]
0x14008f9ad  cmp     [rdx+100h], rax
0x14008f9b4  mov     eax, [rdx+120h]
0x14008f9ba  jnz     loc_14008FA77
0x14008f9c0  mov     ecx, [rdi+120h]
0x14008f9c6  shr     eax, 8
0x14008f9c9  shr     ecx, 8
0x14008f9cc  xor     cx, ax
0x14008f9cf  mov     eax, 1FFh
0x14008f9d4  test    ax, cx
0x14008f9d7  jz      short loc_14008F991
0x14008f9d9  mov     esi, r13d
0x14008f9dc  jmp     short loc_14008F991
0x14008f9de  test    byte ptr [rdi+1Ah], 8
0x14008f9e2  jnz     short loc_14008F997
0x14008f9e4  test    byte ptr [rdi+18h], 20h
0x14008f9e8  jnz     short loc_14008F997
0x14008f9ea  lea     r14, [rdi+58h]
0x14008f9ee  test    esi, esi
0x14008f9f0  jnz     loc_14009026E
0x14008f9f6  mov     eax, [r14+8]
0x14008f9fa  lea     rdx, [r14+8]
0x14008f9fe  cmp     [rbp+350h+var_358.left], eax
0x14008fa01  jge     short loc_14008F997
0x14008fa03  mov     eax, [rbp+350h+var_358.right]
0x14008fa06  cmp     [r14], eax
0x14008fa09  jge     short loc_14008F997
0x14008fa0b  mov     eax, [r14+0Ch]
0x14008fa0f  lea     rcx, [r14+0Ch]
0x14008fa13  cmp     [rbp+350h+var_358.top], eax
0x14008fa16  jge     loc_14008F997
0x14008fa1c  mov     eax, [rbp+350h+var_358.bottom]
0x14008fa1f  lea     rdi, [r14+4]
0x14008fa23  cmp     [rdi], eax
0x14008fa25  jge     loc_14008F997
0x14008fa2b  mov     eax, [rdx]
0x14008fa2d  cmp     [r14], eax
0x14008fa30  jge     loc_14008F997
0x14008fa36  mov     eax, [rcx]
0x14008fa38  cmp     [rdi], eax
0x14008fa3a  jge     loc_14008F997
0x14008fa40  cmp     r15d, dword ptr [rsp+450h+var_3E0]
0x14008fa45  jnz     short loc_14008FA5E
0x14008fa47  lea     rcx, [rsp+450h+var_3F0+8]; struct _CalcVisRgnData *
0x14008fa4c  call    ?ResizeVisExcludeMemory@@YAHPEAU_CalcVisRgnData@@@Z; ResizeVisExcludeMemory(_CalcVisRgnData *)
0x14008fa51  test    eax, eax
0x14008fa53  jz      loc_1400902B8
0x14008fa59  mov     r15d, dword ptr [rsp+450h+var_3F0+0Ch]
0x14008fa5e  mov     rcx, qword ptr [rsp+450h+var_3E0+8]
0x14008fa63  movsxd  rax, r15d
0x14008fa66  inc     r15d
0x14008fa69  mov     dword ptr [rsp+450h+var_3F0+0Ch], r15d
0x14008fa6e  mov     [rcx+rax*8], rbx
0x14008fa72  jmp     loc_14008F997
0x14008fa77  and     al, 0Fh
0x14008fa79  cmp     al, 2
0x14008fa7b  jnz     loc_14008F9D9
0x14008fa81  mov     eax, [rdi+120h]
0x14008fa87  and     al, 0Fh
0x14008fa89  cmp     al, 2
0x14008fa8b  jmp     loc_14008F9D7
0x14008fa90  mov     edi, dword ptr [rsp+450h+var_410]
0x14008fa94  test    esi, esi
0x14008fa96  jnz     loc_14008FFBC
0x14008fa9c  mov     r11d, dword ptr [rsp+450h+var_420]
0x14008faa1  test    r15d, r15d
0x14008faa4  jg      loc_140090349
0x14008faaa  mov     rax, [r12]
0x14008faae  cmp     byte ptr [rax+13h], 0
0x14008fab2  jge     short loc_14008FABB
0x14008fab4  xorps   xmm0, xmm0
0x14008fab7  movups  xmmword ptr [rbp+350h+var_358.left], xmm0
0x14008fabb  mov     r15, [rbp+350h+var_3B8]
0x14008fabf  lea     rdx, [rbp+350h+var_358]
0x14008fac3  mov     rcx, r15
0x14008fac6  call    cs:__imp_SetOrCreateRectRgnIndirectPublic
0x14008facd  nop     dword ptr [rax+rax+00h]
0x14008fad2  test    eax, eax
0x14008fad4  jz      loc_1400902B8
0x14008fada  mov     rsi, [rbp+350h+var_3C8]
0x14008fade  mov     qword ptr [rsp+450h+var_410+8], rsi
0x14008fae3  mov     rbx, [rsp+450h+var_418]
0x14008fae8  mov     rax, [rbx+28h]
0x14008faec  mov     r8, [rax+0A8h]
0x14008faf3  test    r8, r8
0x14008faf6  jz      short loc_14008FB0D
0x14008faf8  mov     rcx, [r15]
0x14008fafb  mov     r9d, r13d
0x14008fafe  mov     rdx, rcx
0x14008fb01  call    cs:__imp_GreCombineRgn
0x14008fb08  nop     dword ptr [rax+rax+00h]
0x14008fb0d  cmp     [rbp+350h+var_3C0], 0
0x14008fb11  jz      loc_14008FF42
0x14008fb17  mov     r8, rbx
0x14008fb1a  xor     r12d, r12d
0x14008fb1d  mov     rbx, [rbx+68h]
0x14008fb21  cmp     rbx, [rbp+350h+var_3B0]
0x14008fb25  jz      loc_14008FF42
0x14008fb2b  mov     rsi, r8
0x14008fb2e  xchg    ax, ax
0x14008fb30  mov     rcx, [rbx+28h]
0x14008fb34  mov     rax, [rcx+0A8h]
0x14008fb3b  mov     [rsp+450h+var_418], rax
0x14008fb40  test    rax, rax
0x14008fb43  jnz     loc_140090161
0x14008fb49  mov     edi, dword ptr [rsp+450h+var_410]
0x14008fb4d  mov     r8, rbx
0x14008fb50  mov     rbx, [rbx+68h]
0x14008fb54  mov     r15, [rbp+350h+var_3B8]
0x14008fb58  cmp     rbx, [rbp+350h+var_3B0]
0x14008fb5c  jnz     short loc_14008FB30
0x14008fb5e  mov     rsi, qword ptr [rsp+450h+var_410+8]
0x14008fb63  jmp     loc_14008FF42
0x14008fb68  test    eax, eax
0x14008fb6a  jnz     loc_14009000F
0x14008fb70  test    ecx, ecx
0x14008fb72  jz      loc_14008FCBB
0x14008fb78  mov     rbx, [r8+70h]
0x14008fb7c  cmp     rbx, r14
0x14008fb7f  jz      loc_14008FCBB
0x14008fb85  xor     esi, esi
0x14008fb87  test    rbx, rbx
0x14008fb8a  jz      loc_14008FC99
0x14008fb90  cmp     rbx, r14
0x14008fb93  jz      loc_14008FC99
0x14008fb99  mov     rdi, [rbx+28h]
0x14008fb9d  test    esi, esi
0x14008fb9f  jz      short loc_14008FBAD
0x14008fba1  test    byte ptr [rdi+1Fh], 10h
0x14008fba5  jnz     short loc_14008FBE9
0x14008fba7  mov     rbx, [rbx+58h]
0x14008fbab  jmp     short loc_14008FB87
0x14008fbad  mov     rdx, [r12]
0x14008fbb1  mov     rax, [rdi+100h]
0x14008fbb8  cmp     [rdx+100h], rax
0x14008fbbf  mov     eax, [rdx+120h]
0x14008fbc5  jnz     loc_14008FC80
0x14008fbcb  mov     ecx, [rdi+120h]
0x14008fbd1  shr     eax, 8
0x14008fbd4  shr     ecx, 8
0x14008fbd7  xor     cx, ax
0x14008fbda  mov     eax, 1FFh
0x14008fbdf  test    ax, cx
0x14008fbe2  jz      short loc_14008FBA1
0x14008fbe4  mov     esi, r13d
0x14008fbe7  jmp     short loc_14008FBA1
0x14008fbe9  test    byte ptr [rdi+1Ah], 8
0x14008fbed  jnz     short loc_14008FBA7
0x14008fbef  test    byte ptr [rdi+18h], 20h
0x14008fbf3  jnz     short loc_14008FBA7
0x14008fbf5  lea     r15, [rdi+58h]
0x14008fbf9  test    esi, esi
0x14008fbfb  jnz     loc_14008FCD4
0x14008fc01  mov     eax, [r15+8]
0x14008fc05  lea     rdx, [r15+8]
0x14008fc09  cmp     [rbp+350h+var_358.left], eax
0x14008fc0c  jge     loc_14008FD08
0x14008fc12  mov     eax, [rbp+350h+var_358.right]
0x14008fc15  cmp     [r15], eax
0x14008fc18  jge     loc_14008FD08
0x14008fc1e  mov     eax, [r15+0Ch]
0x14008fc22  lea     rcx, [r15+0Ch]
0x14008fc26  cmp     [rbp+350h+var_358.top], eax
0x14008fc29  jge     loc_14008FD08
0x14008fc2f  mov     eax, [rbp+350h+var_358.bottom]
0x14008fc32  lea     rdi, [r15+4]
0x14008fc36  cmp     [rdi], eax
0x14008fc38  jge     loc_14008FD08
0x14008fc3e  mov     eax, [rdx]
0x14008fc40  cmp     [r15], eax
0x14008fc43  jge     loc_14008FD08
0x14008fc49  mov     eax, [rcx]
0x14008fc4b  mov     r15d, dword ptr [rsp+450h+var_3F0+0Ch]
0x14008fc50  cmp     [rdi], eax
  ... truncated ...
```
