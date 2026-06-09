# InternalInvalidate2(tagWND *,HRGN__ *,HRGN__ *,tagRECT *,ulong)

- ea: `0x140018940`
- end: `0x1400192c1`
- name: `?InternalInvalidate2@@YAHPEAUtagWND@@PEAUHRGN__@@1PEAUtagRECT@@K@Z`
- size: `2433`
- prototype: `__int64 __fastcall(struct tagWND *, HRGN, HRGN, struct tagRECT *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400172b0`
- `0x140018940`
- `0x1401dcb10`

## callees

- `0x1400159b0`
- `0x140018864`
- `0x140018940`
- `0x1400192c8`
- `0x140019554`
- `0x140019f9c`
- `0x1400bf0e0`
- `0x1401e9a60`
- `0x140341ff0`

## import_xrefs

- `win32kbase!CreateEmptyRgnPublic` at `0x140018cfd`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001926c`
- `win32kbase!CreateEmptyRgnPublic` at `0x140018cfd`
- `win32kbase!CreateEmptyRgnPublic` at `0x14001926c`
- `win32kbase!SetRectRgnIndirect` at `0x140018c2b`
- `win32kbase!SetRectRgnIndirect` at `0x140018f80`
- `win32kbase!SetRectRgnIndirect` at `0x1400191e0`
- `win32kbase!SetRectRgnIndirect` at `0x1400192a0`
- `win32kbase!SetRectRgnIndirect` at `0x140018c2b`
- `win32kbase!SetRectRgnIndirect` at `0x140018f80`
- `win32kbase!SetRectRgnIndirect` at `0x1400191e0`
- `win32kbase!SetRectRgnIndirect` at `0x1400192a0`
- `win32kbase!GreCombineRgn` at `0x140018c92`
- `win32kbase!GreCombineRgn` at `0x140018d29`
- `win32kbase!GreCombineRgn` at `0x140018deb`
- `win32kbase!GreCombineRgn` at `0x140018fb5`
- `win32kbase!GreCombineRgn` at `0x14001903d`
- `win32kbase!GreCombineRgn` at `0x1400190e2`
- `win32kbase!GreCombineRgn` at `0x14001913f`
- `win32kbase!GreCombineRgn` at `0x140019211`
- `win32kbase!GreCombineRgn` at `0x140019240`
- `win32kbase!GreCombineRgn` at `0x140018c92`
- `win32kbase!GreCombineRgn` at `0x140018d29`
- `win32kbase!GreCombineRgn` at `0x140018deb`
- `win32kbase!GreCombineRgn` at `0x140018fb5`
- `win32kbase!GreCombineRgn` at `0x14001903d`
- `win32kbase!GreCombineRgn` at `0x1400190e2`
- `win32kbase!GreCombineRgn` at `0x14001913f`
- `win32kbase!GreCombineRgn` at `0x140019211`
- `win32kbase!GreCombineRgn` at `0x140019240`
- `win32kbase!IsWindowDesktopComposed` at `0x140018e3b`
- `win32kbase!IsWindowDesktopComposed` at `0x140018e3b`
- `win32kbase!GreDeleteObject` at `0x140018d98`
- `win32kbase!GreDeleteObject` at `0x140018e1b`
- `win32kbase!GreDeleteObject` at `0x140018f15`
- `win32kbase!GreDeleteObject` at `0x140019056`
- `win32kbase!GreDeleteObject` at `0x1400190f5`
- `win32kbase!GreDeleteObject` at `0x14001914f`
- `win32kbase!GreDeleteObject` at `0x14001915f`
- `win32kbase!GreDeleteObject` at `0x140018d98`
- `win32kbase!GreDeleteObject` at `0x140018e1b`
- `win32kbase!GreDeleteObject` at `0x140018f15`
- `win32kbase!GreDeleteObject` at `0x140019056`
- `win32kbase!GreDeleteObject` at `0x1400190f5`
- `win32kbase!GreDeleteObject` at `0x14001914f`
- `win32kbase!GreDeleteObject` at `0x14001915f`
- `WIN32K!W32GetUserSessionState` at `0x140018c14`
- `WIN32K!W32GetUserSessionState` at `0x140018c60`
- `WIN32K!W32GetUserSessionState` at `0x140018c73`
- `WIN32K!W32GetUserSessionState` at `0x140018f69`
- `WIN32K!W32GetUserSessionState` at `0x140018f96`
- `WIN32K!W32GetUserSessionState` at `0x14001900b`
- `WIN32K!W32GetUserSessionState` at `0x14001901e`
- `WIN32K!W32GetUserSessionState` at `0x1400190b0`
- `WIN32K!W32GetUserSessionState` at `0x1400190c3`
- `WIN32K!W32GetUserSessionState` at `0x14001918f`
- `WIN32K!W32GetUserSessionState` at `0x1400191c9`
- `WIN32K!W32GetUserSessionState` at `0x1400191f2`
- `WIN32K!W32GetUserSessionState` at `0x140019221`
- `WIN32K!W32GetUserSessionState` at `0x140019289`
- `WIN32K!W32GetUserSessionState` at `0x140018c14`
- `WIN32K!W32GetUserSessionState` at `0x140018c60`
- `WIN32K!W32GetUserSessionState` at `0x140018c73`
- `WIN32K!W32GetUserSessionState` at `0x140018f69`
- `WIN32K!W32GetUserSessionState` at `0x140018f96`
- `WIN32K!W32GetUserSessionState` at `0x14001900b`
- `WIN32K!W32GetUserSessionState` at `0x14001901e`
- `WIN32K!W32GetUserSessionState` at `0x1400190b0`
- `WIN32K!W32GetUserSessionState` at `0x1400190c3`
- `WIN32K!W32GetUserSessionState` at `0x14001918f`
- `WIN32K!W32GetUserSessionState` at `0x1400191c9`
- `WIN32K!W32GetUserSessionState` at `0x1400191f2`
- `WIN32K!W32GetUserSessionState` at `0x140019221`
- `WIN32K!W32GetUserSessionState` at `0x140019289`

## pseudocode

```c
_BOOL8 __fastcall InternalInvalidate2(
        struct tagWND *a1,
        HRGN a2,
        unsigned __int64 right,
        struct tagRECT *a4,
        unsigned int a5)
{
  unsigned int v5; // esi
  HRGN v7; // r13
  __int64 left; // rdx
  struct tagWND *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  bool v13; // zf
  int v14; // eax
  __int64 v15; // rdi
  int v17; // r10d
  LONG v18; // ecx
  LONG v19; // eax
  LONG bottom; // ecx
  LONG top; // eax
  __int64 EmptyRgnPublic; // r15
  _BYTE *v23; // rcx
  unsigned int v24; // eax
  __int64 UserSessionState; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  struct tagWND *v29; // rcx
  struct tagWND *v30; // rdi
  HRGN v31; // r13
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  HRGN v38; // rdx
  int v39; // ebx
  int v40; // eax
  HRGN v41; // r13
  HRGN v42; // r13
  int v43; // ebx
  HRGN v44; // rcx
  __int64 v45; // rax
  int v46; // ecx
  _BYTE *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  struct tagWND *v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rax
  unsigned int v55; // eax
  bool v56; // cf
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rax
  HRGN v64; // rdi
  int v65; // eax
  int v66; // esi
  __int64 v67; // rbx
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // rax
  unsigned int v73; // eax
  int v74; // eax
  __int64 v75; // rax
  __int64 Prop; // rax
  __int64 v77; // rcx
  __int64 v78; // rdi
  __int64 v79; // rbx
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rax
  unsigned int v88; // [rsp+30h] [rbp-51h]
  unsigned int v89; // [rsp+30h] [rbp-51h]
  struct tagRECT v90; // [rsp+38h] [rbp-49h] BYREF
  HRGN v91; // [rsp+48h] [rbp-39h] BYREF
  int v92; // [rsp+50h] [rbp-31h]
  unsigned __int64 v93; // [rsp+58h] [rbp-29h]
  HRGN v94; // [rsp+60h] [rbp-21h] BYREF
  int v95; // [rsp+68h] [rbp-19h]
  int v96; // [rsp+6Ch] [rbp-15h]
  HRGN v97; // [rsp+70h] [rbp-11h]
  struct tagRECT v98; // [rsp+78h] [rbp-9h] BYREF

  v5 = a5 | 0x8000;
  v93 = right;
  v98 = 0;
  v7 = (HRGN)right;
  left = *((_QWORD *)a1 + 5);
  v9 = a1;
  if ( !*(_QWORD *)(left + 168) )
    v5 = a5;
  v98 = *(struct tagRECT *)(left + 88);
  if ( (v5 & 1) == 0 )
    goto LABEL_29;
  if ( (((v5 & 0x10000) == 0) & (*(_BYTE *)(left + 26) >> 3)) != 0 && (*((_DWORD *)a1 + 95) & 0x4000) == 0 )
  {
    right = *((_QWORD *)a1 + 13);
    if ( right )
    {
      v10 = *((_QWORD *)a1 + 3);
      if ( v10 )
      {
        v11 = *(_QWORD *)(v10 + 8);
        if ( v11 )
        {
          if ( right == *(_QWORD *)(v11 + 24) )
            return 1;
        }
      }
    }
    if ( (*(_DWORD *)(left + 232) & 2) == 0 )
      return 1;
  }
  *((_DWORD *)v9 + 95) &= ~0x4000u;
  v12 = *(unsigned __int8 *)(left + 27);
  LOBYTE(v12) = ~(*(_BYTE *)(left + 26) >> 3) & ~((unsigned __int8)v12 >> 5);
  if ( (v12 & 1) != 0 )
  {
    v13 = *((_QWORD *)v9 + 13) == 0;
    v90 = *a4;
    if ( !v13 )
      PhysicalToLogicalInPlaceRect(v9, &v90);
    left = (unsigned int)v98.left;
    right = (unsigned int)v98.right;
    if ( v98.left <= v90.left )
      left = (unsigned int)v90.left;
    v98.left = left;
    if ( v98.right >= v90.right )
      right = (unsigned int)v90.right;
    v98.right = right;
    if ( (int)left < (int)right )
    {
      left = (unsigned int)v98.top;
      right = (unsigned int)v98.bottom;
      if ( v98.top <= v90.top )
        left = (unsigned int)v90.top;
      v98.top = left;
      if ( v98.bottom >= v90.bottom )
        right = (unsigned int)v90.bottom;
      v98.bottom = right;
      if ( (int)left < (int)right )
      {
        v14 = 0;
        goto LABEL_26;
      }
    }
    v98.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v98.top = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v98.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v98.left = 0;
  }
  else if ( v98.left < v98.right && v98.top < v98.bottom )
  {
    v14 = 0;
    goto LABEL_26;
  }
  v14 = 1;
LABEL_26:
  if ( v14 )
    return 1;
  if ( (unsigned __int64)a2 <= 1 )
    goto LABEL_28;
  v24 = SmartRectInRegion(a2, &v98);
  if ( v24 == 1 )
  {
    if ( (v5 & 0x8000) != 0 )
    {
      UserSessionState = W32GetUserSessionState(v12, left, right, a4);
      SetRectRgnIndirect(*(_QWORD *)(UserSessionState + 63136), &v98);
      v29 = 0;
      v30 = v9;
      do
      {
        v31 = *(HRGN *)(*((_QWORD *)v30 + 5) + 168LL);
        v91 = v31;
        if ( v31 )
        {
          if ( v29 )
          {
            v73 = PhysicalToLogicalInPlaceRgn(v29, &v91);
            v31 = v91;
            v89 = v73;
          }
          else
          {
            v89 = 0;
          }
          v58 = *(_QWORD *)(W32GetUserSessionState(v29, v26, v27, v28) + 63136);
          v63 = W32GetUserSessionState(v60, v59, v61, v62);
          GreCombineRgn(*(_QWORD *)(v63 + 63136), v58, v31, 1);
          if ( v89 )
            GreDeleteObject(v31);
        }
        v29 = v30;
        v30 = (struct tagWND *)*((_QWORD *)v30 + 13);
      }
      while ( v30 );
      v32 = *(_QWORD *)(W32GetUserSessionState(v29, v26, v27, v28) + 63136);
      v37 = W32GetUserSessionState(v34, v33, v35, v36);
      if ( (unsigned int)GreCombineRgn(*(_QWORD *)(v37 + 63136), v32, a2, 1) == 1 )
        return 1;
      v7 = (HRGN)v93;
    }
    goto LABEL_28;
  }
  if ( !v24 )
    return 1;
  v55 = v24 - 2;
  if ( v55 )
  {
    if ( v55 == 1 )
      return 0;
  }
  else
  {
    v56 = (GetAppCompatFlags(*((_QWORD *)v9 + 2)) & 0x10000) != 0;
    v57 = 1;
    if ( v56 )
      v57 = (__int64)a2;
    a2 = (HRGN)v57;
  }
LABEL_28:
  if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 27LL) & 0x10) == 0
    || (v75 = W32GetUserSessionState(v12, left, right, a4),
        Prop = GetProp(v9, *(unsigned __int16 *)(v75 + 41198), 1),
        (v78 = Prop) == 0) )
  {
LABEL_29:
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 31LL) & 2) == 0 )
      InternalInvalidate3(v9);
    v15 = *((_QWORD *)v9 + 14);
    if ( v15 )
    {
      a4 = (struct tagRECT *)*((_QWORD *)v9 + 5);
      left = HIBYTE(a4[1].bottom);
      if ( (((v5 & 0x40) == 0) & (unsigned __int8)~((unsigned __int8)left >> 5)) != 0
        && ((v5 & 0x80u) != 0 || (left & 2) == 0) )
      {
        v17 = v5 | 0x2000;
        v90 = 0;
        v18 = a4[6].right;
        if ( (v5 & 1) != 0 )
          v17 = v5 | 0x2404;
        v88 = v17;
        if ( v98.left > v18 )
          v18 = v98.left;
        v90.left = v18;
        v19 = a4[7].left;
        if ( v98.right < v19 )
          v19 = v98.right;
        v90.right = v19;
        if ( v18 < v19 )
        {
          bottom = a4[6].bottom;
          if ( v98.top > bottom )
            bottom = v98.top;
          v90.top = bottom;
          top = a4[7].top;
          if ( v98.bottom < top )
            top = v98.bottom;
          v90.bottom = top;
          if ( bottom < top )
          {
            EmptyRgnPublic = 0;
            while ( v15 )
            {
              v23 = *(_BYTE **)(v15 + 40);
              if ( (v23[31] & 0x10) != 0 )
              {
                if ( (v23[27] & 0x20) != 0 || (v23[26] & 8) != 0 )
                {
                  v92 = 1;
                  if ( EmptyRgnPublic || (EmptyRgnPublic = CreateEmptyRgnPublic()) != 0 )
                  {
                    v38 = v7;
                    if ( a2 != (HRGN)1 )
                      v38 = a2;
                    GreCombineRgn(EmptyRgnPublic, v38, 0, 5);
                  }
                }
                else
                {
                  v92 = 0;
                }
                v94 = a2;
                v91 = v7;
                v96 = PhysicalToLogicalInPlaceRect(v15, &v90);
                v39 = PhysicalToLogicalInPlaceRgn(v15, &v94);
                v40 = PhysicalToLogicalInPlaceRgn(v15, &v91);
                v41 = v94;
                v95 = v40;
                v97 = v91;
                LODWORD(v94) = InternalInvalidate2((struct tagWND *)v15, v94, v91, &v90, v88);
                if ( v39 )
                  GreDeleteObject(v41);
                if ( v95 )
                {
                  v74 = LogicalToPhysicalInPlaceRgnWorker(v15, &v91, 0);
                  v42 = (HRGN)v93;
                  if ( v74 )
                  {
                    GreCombineRgn(v93, v91, 0, 5);
                    GreDeleteObject(v91);
                  }
                  GreDeleteObject(v97);
                }
                else
                {
                  v42 = (HRGN)v93;
                }
                if ( v96
                  && (*(_DWORD *)(*(_QWORD *)(v15 + 40) + 232LL) & 2) != 0
                  && *(_QWORD *)(v15 + 216)
                  && (unsigned int)IsWindowDesktopComposed(v15) )
                {
                  v90.left = (int)(float)((float)v90.left * **(float **)(v15 + 216));
                  v90.top = (int)(float)((float)v90.top * *(float *)(*(_QWORD *)(v15 + 216) + 20LL));
                  a4 = (struct tagRECT *)(unsigned int)(int)(float)((float)v90.right * **(float **)(v15 + 216));
                  v90.right = (int)a4;
                  right = (unsigned int)(int)(float)((float)v90.bottom * *(float *)(*(_QWORD *)(v15 + 216) + 20LL));
                  v90.bottom = right;
                  v45 = *(_QWORD *)(v15 + 216);
                  v46 = (int)*(float *)(v45 + 48);
                  left = (unsigned int)(int)*(float *)(v45 + 52);
                  v90.left += v46;
                  v90.right = v46 + (_DWORD)a4;
                  v90.bottom = left + right;
                  v90.top += left;
                }
                v43 = v92;
                if ( v92 && EmptyRgnPublic )
                {
                  v44 = v42;
                  if ( a2 != (HRGN)1 )
                    v44 = a2;
                  GreCombineRgn(v44, EmptyRgnPublic, 0, 5);
                }
                if ( !(_DWORD)v94 && !v43 )
                {
                  if ( (v5 & 0x12) == 0 )
                  {
                    if ( EmptyRgnPublic )
                      GreDeleteObject(EmptyRgnPublic);
                    return 0;
                  }
                  v5 &= 0xFFFFF3D2;
                  v88 &= 0xFFFFD3D2;
                }
              }
              v15 = *(_QWORD *)(v15 + 88);
              v7 = (HRGN)v93;
            }
            if ( EmptyRgnPublic )
              GreDeleteObject(EmptyRgnPublic);
          }
        }
      }
    }
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 31LL) & 2) != 0 )
      InternalInvalidate3(v9);
    if ( (v5 & 0x2000) == 0 )
      return 1;
    v47 = (_BYTE *)*((_QWORD *)v9 + 5);
    if ( (v47[24] & 0x20) != 0 )
      return 1;
    if ( (v47[26] & 8) != 0 )
      return 1;
    if ( (v47[31] & 4) == 0 )
      return 1;
    if ( (v5 & 8) == 0 )
    {
      v48 = *((_QWORD *)v9 + 13);
      if ( !v48
        || (*(_BYTE *)(*(_QWORD *)(v48 + 40) + 31LL) & 2) == 0 && (GetAppCompatFlags(*((_QWORD *)v9 + 2)) & 0x4000) == 0 )
      {
        return 1;
      }
    }
    v49 = W32GetUserSessionState(v47, left, right, a4);
    SetRectRgnIndirect(*(_QWORD *)(v49 + 63136), &v98);
    if ( (v5 & 0x8000) != 0 )
    {
      v51 = 0;
      do
      {
        v64 = *(HRGN *)(*((_QWORD *)v9 + 5) + 168LL);
        v91 = v64;
        if ( v64 )
        {
          if ( v51 )
          {
            v65 = LogicalToPhysicalInPlaceRgnWorker(v51, &v91, 0);
            v64 = v91;
            v66 = v65;
          }
          else
          {
            v66 = 0;
          }
          v67 = *(_QWORD *)(W32GetUserSessionState(v51, v50, v52, v53) + 63136);
          v72 = W32GetUserSessionState(v69, v68, v70, v71);
          GreCombineRgn(*(_QWORD *)(v72 + 63136), v67, v64, 1);
          if ( v66 )
            GreDeleteObject(v64);
        }
        v51 = v9;
        v9 = (struct tagWND *)*((_QWORD *)v9 + 13);
      }
      while ( v9 );
    }
    v54 = W32GetUserSessionState(v51, v50, v52, v53);
    return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v54 + 63136), 4) != 1;
  }
  v79 = *(_QWORD *)(Prop + 40);
  if ( v79 || (v79 = CreateEmptyRgnPublic()) != 0 )
  {
    v80 = W32GetUserSessionState(v77, left, right, a4);
    SetRectRgnIndirect(*(_QWORD *)(v80 + 63136), &v98);
    if ( v79 != 1 )
    {
      v85 = W32GetUserSessionState(v82, v81, v83, v84);
      GreCombineRgn(v79, v79, *(_QWORD *)(v85 + 63136), 2);
    }
  }
  else
  {
    v79 = 1;
    v87 = W32GetUserSessionState(v77, left, right, a4);
    SetRectRgnIndirect(*(_QWORD *)(v87 + 63136), &v98);
  }
  *(_QWORD *)(v78 + 40) = v79;
  v86 = W32GetUserSessionState(v82, v81, v83, v84);
  return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v86 + 63136), 4) != 1;
}

```

## disassembly

```asm
0x140018940  push    rbp
0x140018942  push    rbx
0x140018943  push    rsi
0x140018944  push    rdi
0x140018945  push    r12
0x140018947  push    r13
0x140018949  push    r14
0x14001894b  push    r15
0x14001894d  lea     rbp, [rsp-17h]
0x140018952  sub     rsp, 98h
0x140018959  mov     rax, cs:__security_cookie
0x140018960  xor     rax, rsp
0x140018963  mov     [rbp+4Fh+var_48], rax
0x140018967  mov     esi, [rbp+4Fh+arg_20]
0x14001896a  xorps   xmm0, xmm0
0x14001896d  bts     esi, 0Fh
0x140018971  mov     [rbp+4Fh+var_78], r8
0x140018975  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm0
0x140018979  mov     r12, rdx
0x14001897c  mov     r13, r8
0x14001897f  mov     rdx, [rcx+28h]
0x140018983  mov     r14, rcx
0x140018986  cmp     qword ptr [rdx+0A8h], 0
0x14001898e  movups  xmm0, xmmword ptr [rdx+58h]
0x140018992  cmovz   esi, [rbp+4Fh+arg_20]
0x140018996  mov     r15d, esi
0x140018999  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm0
0x14001899d  and     r15d, 1
0x1400189a1  jz      loc_140018AD5
0x1400189a7  movzx   ecx, byte ptr [rdx+1Ah]
0x1400189ab  shr     cl, 3
0x1400189ae  bt      esi, 10h
0x1400189b2  setnb   al
0x1400189b5  and     cl, al
0x1400189b7  test    cl, 1
0x1400189ba  jz      short loc_1400189FC
0x1400189bc  test    dword ptr [r14+17Ch], 4000h
0x1400189c7  jnz     short loc_1400189FC
0x1400189c9  mov     r8, [r14+68h]
0x1400189cd  test    r8, r8
0x1400189d0  jz      short loc_1400189EE
0x1400189d2  mov     rax, [r14+18h]
0x1400189d6  test    rax, rax
0x1400189d9  jz      short loc_1400189EE
0x1400189db  mov     rcx, [rax+8]
0x1400189df  test    rcx, rcx
0x1400189e2  jz      short loc_1400189EE
0x1400189e4  cmp     r8, [rcx+18h]
0x1400189e8  jz      loc_140018B18
0x1400189ee  mov     eax, [rdx+0E8h]
0x1400189f4  test    al, 2
0x1400189f6  jz      loc_140018B18
0x1400189fc  and     dword ptr [r14+17Ch], 0FFFFBFFFh
0x140018a07  movzx   ecx, byte ptr [rdx+1Bh]
0x140018a0b  movzx   eax, byte ptr [rdx+1Ah]
0x140018a0f  shr     cl, 5
0x140018a12  shr     al, 3
0x140018a15  not     cl
0x140018a17  not     al
0x140018a19  and     cl, al
0x140018a1b  test    cl, 1
0x140018a1e  jz      loc_140018CC1
0x140018a24  cmp     qword ptr [r14+68h], 0
0x140018a29  movups  xmm0, xmmword ptr [r9]
0x140018a2d  movups  xmmword ptr [rbp+4Fh+var_98.left], xmm0
0x140018a31  jnz     loc_140018CB0
0x140018a37  mov     edx, [rbp+4Fh+var_58.left]
0x140018a3a  cmp     edx, [rbp+4Fh+var_98.left]
0x140018a3d  mov     r8d, [rbp+4Fh+var_58.right]
0x140018a41  cmovle  edx, [rbp+4Fh+var_98.left]
0x140018a45  cmp     r8d, [rbp+4Fh+var_98.right]
0x140018a49  mov     [rbp+4Fh+var_58.left], edx
0x140018a4c  cmovge  r8d, [rbp+4Fh+var_98.right]
0x140018a51  mov     [rbp+4Fh+var_58.right], r8d
0x140018a55  cmp     edx, r8d
0x140018a58  jge     short loc_140018A81
0x140018a5a  mov     edx, [rbp+4Fh+var_58.top]
0x140018a5d  cmp     edx, [rbp+4Fh+var_98.top]
0x140018a60  mov     r8d, [rbp+4Fh+var_58.bottom]
0x140018a64  cmovle  edx, [rbp+4Fh+var_98.top]
0x140018a68  cmp     r8d, [rbp+4Fh+var_98.bottom]
0x140018a6c  mov     [rbp+4Fh+var_58.top], edx
0x140018a6f  cmovge  r8d, [rbp+4Fh+var_98.bottom]
0x140018a74  mov     [rbp+4Fh+var_58.bottom], r8d
0x140018a78  cmp     edx, r8d
0x140018a7b  jl      loc_140018CE0
0x140018a81  xorps   xmm0, xmm0
0x140018a84  xorps   xmm2, xmm2
0x140018a87  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm2
0x140018a8b  psrldq  xmm0, 0Ch
0x140018a90  xorps   xmm1, xmm1
0x140018a93  movd    [rbp+4Fh+var_58.bottom], xmm0
0x140018a98  xorps   xmm0, xmm0
0x140018a9b  psrldq  xmm0, 4
0x140018aa0  psrldq  xmm1, 8
0x140018aa5  movd    [rbp+4Fh+var_58.top], xmm0
0x140018aaa  movd    [rbp+4Fh+var_58.right], xmm1
0x140018aaf  movss   [rbp+4Fh+var_58.left], xmm2
0x140018ab4  mov     eax, 1
0x140018ab9  test    eax, eax
0x140018abb  jnz     short loc_140018B18
0x140018abd  cmp     r12, 1
0x140018ac1  ja      loc_140018BF5
0x140018ac7  mov     rax, [r14+28h]
0x140018acb  test    byte ptr [rax+1Bh], 10h
0x140018acf  jnz     loc_14001918F
0x140018ad5  mov     rax, [r14+28h]
0x140018ad9  test    byte ptr [rax+1Fh], 2
0x140018add  jnz     short loc_140018AED
0x140018adf  mov     r8d, esi
0x140018ae2  mov     rdx, r12
0x140018ae5  mov     rcx, r14; struct tagWND *
0x140018ae8  call    InternalInvalidate3
0x140018aed  mov     rdi, [r14+70h]
0x140018af1  test    rdi, rdi
0x140018af4  jnz     short loc_140018B3E
0x140018af6  mov     rax, [r14+28h]
0x140018afa  test    byte ptr [rax+1Fh], 2
0x140018afe  jz      short loc_140018B0E
0x140018b00  mov     r8d, esi
0x140018b03  mov     rdx, r12
0x140018b06  mov     rcx, r14; struct tagWND *
0x140018b09  call    InternalInvalidate3
0x140018b0e  bt      esi, 0Dh
0x140018b12  jb      loc_140018F26
0x140018b18  mov     eax, 1
0x140018b1d  mov     rcx, [rbp+4Fh+var_48]
0x140018b21  xor     rcx, rsp; StackCookie
0x140018b24  call    __security_check_cookie
0x140018b29  add     rsp, 98h
0x140018b30  pop     r15
0x140018b32  pop     r14
0x140018b34  pop     r13
0x140018b36  pop     r12
0x140018b38  pop     rdi
0x140018b39  pop     rsi
0x140018b3a  pop     rbx
0x140018b3b  pop     rbp
0x140018b3c  retn
0x140018b3e  mov     r9, [r14+28h]
0x140018b42  movzx   edx, byte ptr [r9+1Fh]
0x140018b47  movzx   ecx, dl
0x140018b4a  shr     cl, 5
0x140018b4d  test    sil, 40h
0x140018b51  not     cl
0x140018b53  setz    al
0x140018b56  and     cl, al
0x140018b58  test    cl, 1
0x140018b5b  jz      short loc_140018AF6
0x140018b5d  test    sil, sil
0x140018b60  js      short loc_140018B67
0x140018b62  test    dl, 2
0x140018b65  jnz     short loc_140018AF6
0x140018b67  mov     r10d, esi
0x140018b6a  xorps   xmm0, xmm0
0x140018b6d  bts     r10d, 0Dh
0x140018b72  movups  xmmword ptr [rbp+4Fh+var_98.left], xmm0
0x140018b76  mov     ecx, [r9+68h]
0x140018b7a  mov     eax, r10d
0x140018b7d  or      eax, 404h
0x140018b82  test    r15d, r15d
0x140018b85  cmovnz  r10d, eax
0x140018b89  cmp     [rbp+4Fh+var_58.left], ecx
0x140018b8c  mov     [rbp+4Fh+var_A0], r10d
0x140018b90  cmovg   ecx, [rbp+4Fh+var_58.left]
0x140018b94  mov     [rbp+4Fh+var_98.left], ecx
0x140018b97  mov     eax, [r9+70h]
0x140018b9b  cmp     [rbp+4Fh+var_58.right], eax
0x140018b9e  cmovl   eax, [rbp+4Fh+var_58.right]
0x140018ba2  mov     [rbp+4Fh+var_98.right], eax
0x140018ba5  cmp     ecx, eax
0x140018ba7  jge     loc_140018AF6
0x140018bad  mov     ecx, [r9+6Ch]
0x140018bb1  cmp     [rbp+4Fh+var_58.top], ecx
0x140018bb4  cmovg   ecx, [rbp+4Fh+var_58.top]
0x140018bb8  mov     [rbp+4Fh+var_98.top], ecx
0x140018bbb  mov     eax, [r9+74h]
0x140018bbf  cmp     [rbp+4Fh+var_58.bottom], eax
0x140018bc2  cmovl   eax, [rbp+4Fh+var_58.bottom]
0x140018bc6  mov     [rbp+4Fh+var_98.bottom], eax
0x140018bc9  cmp     ecx, eax
0x140018bcb  jge     loc_140018AF6
0x140018bd1  xor     r15d, r15d
0x140018bd4  test    rdi, rdi
0x140018bd7  jz      loc_140018F09
0x140018bdd  mov     rcx, [rdi+28h]
0x140018be1  test    byte ptr [rcx+1Fh], 10h
0x140018be5  jnz     loc_140018CE7
0x140018beb  mov     rdi, [rdi+58h]
0x140018bef  mov     r13, [rbp+4Fh+var_78]
0x140018bf3  jmp     short loc_140018BD4
0x140018bf5  lea     rdx, [rbp+4Fh+var_58]; struct tagRECT *
0x140018bf9  mov     rcx, r12; HRGN
0x140018bfc  call    ?SmartRectInRegion@@YAIPEAUHRGN__@@PEAUtagRECT@@@Z; SmartRectInRegion(HRGN__ *,tagRECT *)
0x140018c01  cmp     eax, 1
0x140018c04  jnz     loc_140018FD0
0x140018c0a  bt      esi, 0Fh
0x140018c0e  jnb     loc_140018AC7
0x140018c14  call    cs:__imp_W32GetUserSessionState
0x140018c1b  nop     dword ptr [rax+rax+00h]
0x140018c20  lea     rdx, [rbp+4Fh+var_58]
0x140018c24  mov     rcx, [rax+0F6A0h]
0x140018c2b  call    cs:__imp_SetRectRgnIndirect
0x140018c32  nop     dword ptr [rax+rax+00h]
0x140018c37  xor     ecx, ecx
0x140018c39  mov     rdi, r14
0x140018c3c  mov     rax, [rdi+28h]
0x140018c40  mov     r13, [rax+0A8h]
0x140018c47  mov     [rbp+4Fh+var_88], r13
0x140018c4b  test    r13, r13
0x140018c4e  jnz     loc_140018FFF
0x140018c54  mov     rcx, rdi
0x140018c57  mov     rdi, [rdi+68h]
0x140018c5b  test    rdi, rdi
0x140018c5e  jnz     short loc_140018C3C
0x140018c60  call    cs:__imp_W32GetUserSessionState
0x140018c67  nop     dword ptr [rax+rax+00h]
0x140018c6c  mov     rbx, [rax+0F6A0h]
0x140018c73  call    cs:__imp_W32GetUserSessionState
0x140018c7a  nop     dword ptr [rax+rax+00h]
0x140018c7f  mov     r9d, 1
0x140018c85  mov     r8, r12
0x140018c88  mov     rdx, rbx
0x140018c8b  mov     rcx, [rax+0F6A0h]
0x140018c92  call    cs:__imp_GreCombineRgn
0x140018c99  nop     dword ptr [rax+rax+00h]
0x140018c9e  cmp     eax, 1
0x140018ca1  jz      loc_140018B18
0x140018ca7  mov     r13, [rbp+4Fh+var_78]
0x140018cab  jmp     loc_140018AC7
0x140018cb0  lea     rdx, [rbp+4Fh+var_98]
0x140018cb4  mov     rcx, r14
0x140018cb7  call    PhysicalToLogicalInPlaceRect
0x140018cbc  jmp     loc_140018A37
0x140018cc1  mov     eax, [rbp+4Fh+var_58.right]
0x140018cc4  cmp     [rbp+4Fh+var_58.left], eax
0x140018cc7  jge     loc_140018AB4
0x140018ccd  mov     eax, [rbp+4Fh+var_58.bottom]
0x140018cd0  cmp     [rbp+4Fh+var_58.top], eax
0x140018cd3  jge     loc_140018AB4
0x140018cd9  xor     eax, eax
0x140018cdb  jmp     loc_140018AB9
0x140018ce0  xor     eax, eax
0x140018ce2  jmp     loc_140018AB9
0x140018ce7  test    byte ptr [rcx+1Bh], 20h
0x140018ceb  jz      loc_140018EF3
0x140018cf1  mov     [rbp+4Fh+var_80], 1
0x140018cf8  test    r15, r15
0x140018cfb  jnz     short loc_140018D11
0x140018cfd  call    cs:__imp_CreateEmptyRgnPublic
0x140018d04  nop     dword ptr [rax+rax+00h]
0x140018d09  mov     r15, rax
0x140018d0c  test    rax, rax
0x140018d0f  jz      short loc_140018D35
0x140018d11  xor     r8d, r8d
0x140018d14  mov     r9d, 5
0x140018d1a  mov     rcx, r15
0x140018d1d  mov     rdx, r13
0x140018d20  cmp     r12, 1
0x140018d24  jz      short loc_140018D29
0x140018d26  mov     rdx, r12
0x140018d29  call    cs:__imp_GreCombineRgn
0x140018d30  nop     dword ptr [rax+rax+00h]
0x140018d35  lea     rdx, [rbp+4Fh+var_98]
0x140018d39  mov     [rbp+4Fh+var_70], r12
0x140018d3d  mov     rcx, rdi
0x140018d40  mov     [rbp+4Fh+var_88], r13
0x140018d44  call    PhysicalToLogicalInPlaceRect
0x140018d49  lea     rdx, [rbp+4Fh+var_70]
0x140018d4d  mov     [rbp+4Fh+var_64], eax
0x140018d50  mov     rcx, rdi
0x140018d53  call    PhysicalToLogicalInPlaceRgn
0x140018d58  lea     rdx, [rbp+4Fh+var_88]
0x140018d5c  mov     rcx, rdi
0x140018d5f  mov     ebx, eax
0x140018d61  call    PhysicalToLogicalInPlaceRgn
0x140018d66  mov     r13, [rbp+4Fh+var_70]
0x140018d6a  lea     r9, [rbp+4Fh+var_98]; struct tagRECT *
0x140018d6e  mov     [rbp+4Fh+var_68], eax
0x140018d71  mov     rdx, r13; HRGN
0x140018d74  mov     eax, [rbp+4Fh+var_A0]
0x140018d77  mov     rcx, rdi; struct tagWND *
0x140018d7a  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x140018d7e  mov     rax, [rbp+4Fh+var_88]
0x140018d82  mov     r8, rax; HRGN
0x140018d85  mov     [rbp+4Fh+var_60], rax
0x140018d89  call    ?InternalInvalidate2@@YAHPEAUtagWND@@PEAUHRGN__@@1PEAUtagRECT@@K@Z; InternalInvalidate2(tagWND *,HRGN__ *,HRGN__ *,tagRECT *,ulong)
0x140018d8e  mov     dword ptr [rbp+4Fh+var_70], eax
0x140018d91  test    ebx, ebx
0x140018d93  jz      short loc_140018DA4
0x140018d95  mov     rcx, r13
0x140018d98  call    cs:__imp_GreDeleteObject
0x140018d9f  nop     dword ptr [rax+rax+00h]
0x140018da4  cmp     [rbp+4Fh+var_68], 0
0x140018da8  jnz     loc_140019118
0x140018dae  mov     r13, [rbp+4Fh+var_78]
0x140018db2  cmp     [rbp+4Fh+var_64], 0
0x140018db6  jz      short loc_140018DC7
0x140018db8  mov     rax, [rdi+28h]
0x140018dbc  mov     ecx, [rax+0E8h]
  ... truncated ...
```
