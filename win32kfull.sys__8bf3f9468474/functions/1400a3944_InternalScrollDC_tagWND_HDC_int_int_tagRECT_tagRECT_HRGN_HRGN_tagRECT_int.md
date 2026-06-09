# InternalScrollDC(tagWND *,HDC__ *,int,int,tagRECT *,tagRECT *,HRGN__ *,HRGN__ *,tagRECT *,int)

- ea: `0x1400a3944`
- end: `0x1400a4913`
- name: `?InternalScrollDC@@YAHPEAUtagWND@@PEAUHDC__@@HHPEAUtagRECT@@2PEAUHRGN__@@32H@Z`
- size: `4047`
- prototype: `int(struct tagWND *, HDC, int, int, struct tagRECT *, struct tagRECT *, HRGN, HRGN, struct tagRECT *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400a3848`
- `0x1400d9774`

## callees

- `0x1400646b4`
- `0x14009dfd0`
- `0x1400a3944`
- `0x1400a491c`
- `0x1400a4980`
- `0x1400a4a64`
- `0x1400a4ca0`
- `0x1400d94b0`
- `0x140341ff0`
- `0x140342120`

## import_xrefs

- `win32kbase!GreGetDCOrg` at `0x1400a43cf`
- `win32kbase!GreGetDCOrg` at `0x1400a43cf`
- `win32kbase!GreGetRgnBox` at `0x1400a3f3f`
- `win32kbase!GreGetRgnBox` at `0x1400a4489`
- `win32kbase!GreGetRgnBox` at `0x1400a4880`
- `win32kbase!GreGetRgnBox` at `0x1400a3f3f`
- `win32kbase!GreGetRgnBox` at `0x1400a4489`
- `win32kbase!GreGetRgnBox` at `0x1400a4880`
- `win32kbase!SetEmptyRgn` at `0x1400a45bc`
- `win32kbase!SetEmptyRgn` at `0x1400a45bc`
- `win32kbase!GreGetClipBox` at `0x1400a3a2c`
- `win32kbase!GreGetClipBox` at `0x1400a3a2c`
- `win32kbase!GreLockVisRgnSharedOrExclusive` at `0x1400a39ef`
- `win32kbase!GreLockVisRgnSharedOrExclusive` at `0x1400a39ef`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a3e22`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a4190`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a45e7`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a3e22`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a4190`
- `win32kbase!GreUnlockVisRgnShared` at `0x1400a45e7`
- `win32kbase!GreSelectVisRgnShared` at `0x1400a43fe`
- `win32kbase!GreSelectVisRgnShared` at `0x1400a4472`
- `win32kbase!GreSelectVisRgnShared` at `0x1400a43fe`
- `win32kbase!GreSelectVisRgnShared` at `0x1400a4472`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46a6`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46b7`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46ec`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46a6`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46b7`
- `win32kbase!GreUnlockVisRgn` at `0x1400a46ec`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3c74`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3cc0`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3ef2`
- `win32kbase!SetRectRgnIndirect` at `0x1400a4124`
- `win32kbase!SetRectRgnIndirect` at `0x1400a47f2`
- `win32kbase!SetRectRgnIndirect` at `0x1400a4805`
- `win32kbase!SetRectRgnIndirect` at `0x1400a483b`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3c74`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3cc0`
- `win32kbase!SetRectRgnIndirect` at `0x1400a3ef2`
- `win32kbase!SetRectRgnIndirect` at `0x1400a4124`
- `win32kbase!SetRectRgnIndirect` at `0x1400a47f2`
- `win32kbase!SetRectRgnIndirect` at `0x1400a4805`
- `win32kbase!SetRectRgnIndirect` at `0x1400a483b`
- `win32kbase!CreateEmptyRgn` at `0x1400a3c59`
- `win32kbase!CreateEmptyRgn` at `0x1400a3ca6`
- `win32kbase!CreateEmptyRgn` at `0x1400a3d00`
- `win32kbase!CreateEmptyRgn` at `0x1400a3d76`
- `win32kbase!CreateEmptyRgn` at `0x1400a3eab`
- `win32kbase!CreateEmptyRgn` at `0x1400a3ed7`
- `win32kbase!CreateEmptyRgn` at `0x1400a4233`
- `win32kbase!CreateEmptyRgn` at `0x1400a4671`
- `win32kbase!CreateEmptyRgn` at `0x1400a4719`
- `win32kbase!CreateEmptyRgn` at `0x1400a473b`
- `win32kbase!CreateEmptyRgn` at `0x1400a47d7`
- `win32kbase!CreateEmptyRgn` at `0x1400a3c59`
- `win32kbase!CreateEmptyRgn` at `0x1400a3ca6`
- `win32kbase!CreateEmptyRgn` at `0x1400a3d00`
- `win32kbase!CreateEmptyRgn` at `0x1400a3d76`
- `win32kbase!CreateEmptyRgn` at `0x1400a3eab`
- `win32kbase!CreateEmptyRgn` at `0x1400a3ed7`
- `win32kbase!CreateEmptyRgn` at `0x1400a4233`
- `win32kbase!CreateEmptyRgn` at `0x1400a4671`
- `win32kbase!CreateEmptyRgn` at `0x1400a4719`
- `win32kbase!CreateEmptyRgn` at `0x1400a473b`
- `win32kbase!CreateEmptyRgn` at `0x1400a47d7`
- `win32kbase!GreCombineRgn` at `0x1400a3c92`
- `win32kbase!GreCombineRgn` at `0x1400a3cd8`
- `win32kbase!GreCombineRgn` at `0x1400a3d22`
- `win32kbase!GreCombineRgn` at `0x1400a3d5e`
- `win32kbase!GreCombineRgn` at `0x1400a3dbd`
- `win32kbase!GreCombineRgn` at `0x1400a3df1`
- `win32kbase!GreCombineRgn` at `0x1400a3f0d`
- `win32kbase!GreCombineRgn` at `0x1400a433c`
- `win32kbase!GreCombineRgn` at `0x1400a4376`
- `win32kbase!GreCombineRgn` at `0x1400a439f`
- `win32kbase!GreCombineRgn` at `0x1400a4820`
- `win32kbase!GreCombineRgn` at `0x1400a4856`
- `win32kbase!GreCombineRgn` at `0x1400a3c92`
- `win32kbase!GreCombineRgn` at `0x1400a3cd8`
- `win32kbase!GreCombineRgn` at `0x1400a3d22`
- `win32kbase!GreCombineRgn` at `0x1400a3d5e`
- `win32kbase!GreCombineRgn` at `0x1400a3dbd`
- `win32kbase!GreCombineRgn` at `0x1400a3df1`
- `win32kbase!GreCombineRgn` at `0x1400a3f0d`
- `win32kbase!GreCombineRgn` at `0x1400a433c`
- `win32kbase!GreCombineRgn` at `0x1400a4376`
- `win32kbase!GreCombineRgn` at `0x1400a439f`
- `win32kbase!GreCombineRgn` at `0x1400a4820`
- `win32kbase!GreCombineRgn` at `0x1400a4856`
- `win32kbase!GreOffsetRgn` at `0x1400a3d44`
- `win32kbase!GreOffsetRgn` at `0x1400a3dd8`
- `win32kbase!GreOffsetRgn` at `0x1400a4323`
- `win32kbase!GreOffsetRgn` at `0x1400a43e9`
- `win32kbase!GreOffsetRgn` at `0x1400a3d44`
- `win32kbase!GreOffsetRgn` at `0x1400a3dd8`
- `win32kbase!GreOffsetRgn` at `0x1400a4323`
- `win32kbase!GreOffsetRgn` at `0x1400a43e9`
- `win32kbase!GreDeleteObject` at `0x1400a3e31`
- `win32kbase!GreDeleteObject` at `0x1400a3e40`
- `win32kbase!GreDeleteObject` at `0x1400a3e4f`
- `win32kbase!GreDeleteObject` at `0x1400a3e5e`
- `win32kbase!GreDeleteObject` at `0x1400a3e6e`
- `win32kbase!GreDeleteObject` at `0x1400a3e7e`
- `win32kbase!GreDeleteObject` at `0x1400a41a0`
- `win32kbase!GreDeleteObject` at `0x1400a41b1`
- `win32kbase!GreDeleteObject` at `0x1400a41c0`
- `win32kbase!GreDeleteObject` at `0x1400a41d1`
- `win32kbase!GreDeleteObject` at `0x1400a41e1`
- `win32kbase!GreDeleteObject` at `0x1400a41f0`
- `win32kbase!GreDeleteObject` at `0x1400a45f7`
- `win32kbase!GreDeleteObject` at `0x1400a4606`
- `win32kbase!GreDeleteObject` at `0x1400a4614`
- `win32kbase!GreDeleteObject` at `0x1400a4622`
- `win32kbase!GreDeleteObject` at `0x1400a4630`
- `win32kbase!GreDeleteObject` at `0x1400a463e`
- `win32kbase!GreDeleteObject` at `0x1400a3e31`
- `win32kbase!GreDeleteObject` at `0x1400a3e40`
- `win32kbase!GreDeleteObject` at `0x1400a3e4f`
- `win32kbase!GreDeleteObject` at `0x1400a3e5e`
- `win32kbase!GreDeleteObject` at `0x1400a3e6e`
- `win32kbase!GreDeleteObject` at `0x1400a3e7e`
- `win32kbase!GreDeleteObject` at `0x1400a41a0`
- `win32kbase!GreDeleteObject` at `0x1400a41b1`
- `win32kbase!GreDeleteObject` at `0x1400a41c0`
- `win32kbase!GreDeleteObject` at `0x1400a41d1`
- `win32kbase!GreDeleteObject` at `0x1400a41e1`
- `win32kbase!GreDeleteObject` at `0x1400a41f0`
- `win32kbase!GreDeleteObject` at `0x1400a45f7`
- `win32kbase!GreDeleteObject` at `0x1400a4606`
- `win32kbase!GreDeleteObject` at `0x1400a4614`
- `win32kbase!GreDeleteObject` at `0x1400a4622`
- `win32kbase!GreDeleteObject` at `0x1400a4630`
- `win32kbase!GreDeleteObject` at `0x1400a463e`
- `WIN32K!W32GetUserSessionState` at `0x1400a39d1`
- `WIN32K!W32GetUserSessionState` at `0x1400a39d1`

## pseudocode

```c
__int64 __fastcall InternalScrollDC(
        struct tagWND *a1,
        HDC a2,
        __int64 a3,
        __int64 a4,
        struct tagRECT *a5,
        struct tagRECT *a6,
        HRGN a7,
        HRGN a8,
        struct tagRECT *a9,
        int a10)
{
  struct tagRECT *v10; // r12
  HRGN v12; // rdi
  __int64 UserSessionState; // rax
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int ClipBox; // r14d
  __m128i *v19; // rcx
  __m128i v20; // xmm1
  int v21; // esi
  __int64 v22; // rcx
  __int64 left; // r9
  int v24; // r12d
  int right; // r10d
  int v26; // eax
  int top; // r11d
  int bottom; // esi
  int v29; // ebx
  int v30; // eax
  struct tagRECT v31; // xmm3
  int v32; // esi
  int v33; // r15d
  struct tagRECT v34; // xmm6
  int v35; // eax
  int v36; // r8d
  int v37; // esi
  int v38; // ebx
  int v39; // r15d
  int v40; // r12d
  int v41; // ecx
  HRGN v42; // r12
  __int64 v43; // rsi
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  unsigned __int64 v53; // r12
  int v54; // ebx
  __int64 v55; // rax
  HRGN v56; // r12
  __int64 v57; // rbx
  int v59; // eax
  __int64 v60; // rdx
  int v61; // ecx
  int v62; // eax
  __int64 v63; // r8
  __int64 v64; // rcx
  int v65; // eax
  BOOL v66; // ecx
  BOOL v67; // eax
  struct tagRECT *v68; // r15
  __int64 v69; // rbx
  int v70; // esi
  __int64 v71; // rax
  int v72; // ecx
  __int32 v73; // ecx
  int v74; // ecx
  __int64 v75; // [rsp+68h] [rbp-A0h]
  __int64 v76; // [rsp+70h] [rbp-98h]
  __int64 v77; // [rsp+78h] [rbp-90h]
  int v78; // [rsp+80h] [rbp-88h]
  int v79; // [rsp+80h] [rbp-88h]
  HRGN EmptyRgn; // [rsp+88h] [rbp-80h]
  int v81; // [rsp+98h] [rbp-70h]
  int v82; // [rsp+98h] [rbp-70h]
  int v83; // [rsp+A8h] [rbp-60h]
  int v84; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v85; // [rsp+B0h] [rbp-58h]
  __int64 v86; // [rsp+C0h] [rbp-48h]
  unsigned int v87; // [rsp+C8h] [rbp-40h]
  int v88; // [rsp+CCh] [rbp-3Ch] BYREF
  HRGN v89; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v90; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v91; // [rsp+E0h] [rbp-28h]
  __int64 v92; // [rsp+E8h] [rbp-20h]
  __int64 v93; // [rsp+F0h] [rbp-18h]
  int v94; // [rsp+F8h] [rbp-10h]
  int v95; // [rsp+FCh] [rbp-Ch]
  __m128i Buf2; // [rsp+108h] [rbp+0h] BYREF
  __m128i Buf1; // [rsp+118h] [rbp+10h] BYREF
  __int128 v98; // [rsp+128h] [rbp+20h] BYREF
  struct tagRECT v99; // [rsp+138h] [rbp+30h] BYREF
  struct tagRECT v100; // [rsp+148h] [rbp+40h] BYREF
  __int128 v101; // [rsp+158h] [rbp+50h] BYREF
  __int128 v102; // [rsp+168h] [rbp+60h] BYREF

  v10 = a9;
  v12 = a8;
  v89 = a7;
  v98 = 0;
  v88 = 0;
  Buf1 = 0;
  v85 = __PAIR64__(a3, a4);
  v102 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3, a4);
  if ( !(unsigned int)GreLockVisRgnSharedOrExclusive(
                        *(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                        a2,
                        &v88) )
    return 0;
  EmptyRgn = 0;
  v76 = 0;
  v75 = 0;
  v14 = 0;
  v77 = 0;
  v92 = 0;
  v86 = 0;
  ClipBox = GreGetClipBox(a2, &v98, 1);
  if ( !ClipBox )
  {
    v42 = 0;
    goto LABEL_152;
  }
  v19 = (__m128i *)&v98;
  if ( a5 )
    v19 = (__m128i *)a5;
  v20 = *v19;
  Buf1 = *v19;
  if ( a6 )
    v102 = (__int128)*a6;
  v21 = HIDWORD(v85);
  v91 = v85;
  if ( a10 )
  {
    v70 = 0;
    GreLPtoDP(a2);
    GreLPtoDP(a2);
    if ( (GreGetLayout(a2) & 1) != 0 )
    {
      v72 = v98;
      v70 = 1;
      LODWORD(v98) = DWORD2(v98);
      DWORD2(v98) = v72;
      v73 = Buf1.m128i_i32[0];
      Buf1.m128i_i32[0] = Buf1.m128i_i32[2];
      Buf1.m128i_i32[2] = v73;
    }
    if ( a6 )
    {
      GreLPtoDP(a2);
      if ( v70 )
      {
        v74 = v102;
        LODWORD(v102) = DWORD2(v102);
        DWORD2(v102) = v74;
      }
    }
    v94 = HIDWORD(v85);
    v95 = v85;
    v93 = 0;
    GreLPtoDP(a2);
    v21 = v94 - v93;
    v20 = Buf1;
    LODWORD(v85) = v95 - HIDWORD(v93);
    HIDWORD(v85) = v94 - v93;
  }
  if ( ClipBox == 1 )
  {
    v57 = 0;
    goto LABEL_173;
  }
  if ( ClipBox == 3 )
  {
    EmptyRgn = (HRGN)CreateEmptyRgn(2, v15, v16, v17);
    v42 = EmptyRgn;
    if ( (unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
    {
      v20 = Buf1;
      LODWORD(v14) = 1;
      goto LABEL_10;
    }
LABEL_152:
    v57 = 0;
LABEL_153:
    v43 = 0;
    goto LABEL_53;
  }
LABEL_10:
  v22 = (unsigned int)v85;
  v81 = _mm_cvtsi128_si32(v20);
  left = (unsigned int)(v21 + v81);
  v99.left = v21 + v81;
  v24 = _mm_cvtsi128_si32(_mm_srli_si128(v20, 4));
  v83 = _mm_cvtsi128_si32(_mm_srli_si128(v20, 8));
  right = v21 + v83;
  v26 = _mm_cvtsi128_si32(_mm_srli_si128(v20, 12));
  v99.right = v21 + v83;
  v78 = v26;
  top = v85 + v24;
  v99.top = v85 + v24;
  bottom = v85 + v26;
  v99.bottom = v85 + v26;
  if ( !a6 )
  {
    v29 = v26;
LABEL_12:
    if ( ClipBox != 2 )
      goto LABEL_40;
    v16 = HIDWORD(v98);
    v22 = DWORD2(v98);
    v15 = DWORD1(v98);
    v30 = v98;
LABEL_14:
    if ( (unsigned __int64)v89 <= 1 )
    {
      Buf2 = v20;
      if ( (int)left <= v30 )
        left = (unsigned int)v30;
      v99.left = left;
      if ( right >= (int)v22 )
        right = v22;
      v99.right = right;
      if ( (int)left >= right )
        goto LABEL_25;
      if ( top <= (int)v15 )
        top = v15;
      v99.top = top;
      if ( bottom >= (int)v16 )
        bottom = v16;
      v87 = bottom;
      v99.bottom = bottom;
      if ( top < bottom )
      {
        v31 = v99;
      }
      else
      {
LABEL_25:
        v31 = 0;
        v87 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
        top = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        v99 = 0;
        right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
        left = (unsigned int)_mm_cvtsi128_si32((__m128i)0LL);
      }
      v32 = v81;
      v33 = v83;
      if ( v81 <= v30 )
        v32 = v30;
      v82 = v32;
      if ( v83 >= (int)v22 )
        v33 = v22;
      Buf1.m128i_i32[0] = v32;
      v84 = v33;
      Buf1.m128i_i32[2] = v33;
      if ( v32 >= v33 )
        goto LABEL_36;
      if ( v24 <= (int)v15 )
        v24 = v15;
      LODWORD(v90) = v24;
      if ( v29 >= (int)v16 )
        v29 = v16;
      Buf1.m128i_i32[1] = v24;
      v79 = v29;
      Buf1.m128i_i32[3] = v29;
      if ( v24 < v29 )
      {
        v34 = (struct tagRECT)Buf1;
        v36 = 1;
        v35 = v29;
      }
      else
      {
LABEL_36:
        v34 = 0;
        v35 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
        v36 = 0;
        v24 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        v33 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
        v32 = _mm_cvtsi128_si32((__m128i)0LL);
        LODWORD(v90) = v24;
        Buf1 = 0;
        v79 = v35;
        v84 = v33;
        v82 = v32;
      }
      if ( v89 == (HRGN)1 )
      {
        v60 = v87;
      }
      else
      {
        v37 = HIDWORD(v85) + v32;
        LODWORD(v101) = v37;
        v38 = HIDWORD(v85) + v33;
        DWORD2(v101) = HIDWORD(v85) + v33;
        v39 = v85 + v24;
        v40 = v85 + v35;
        if ( v37 <= (int)left )
        {
          v37 = left;
          LODWORD(v101) = left;
          v41 = left;
        }
        else
        {
          v41 = v37;
        }
        if ( v38 < right )
        {
          v59 = v38;
        }
        else
        {
          v38 = right;
          v59 = right;
          DWORD2(v101) = right;
        }
        v60 = v87;
        if ( v41 < v59 )
        {
          if ( v39 <= top )
            v39 = top;
          DWORD1(v101) = v39;
          if ( v40 >= (int)v87 )
            v40 = v87;
          HIDWORD(v101) = v40;
          if ( v39 < v40 )
            goto LABEL_77;
        }
      }
      v40 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      v39 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v101 = 0;
      v38 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v37 = _mm_cvtsi128_si32((__m128i)0LL);
LABEL_77:
      if ( !v36 )
      {
        v100 = v31;
        goto LABEL_110;
      }
      v61 = left;
      v62 = right;
      if ( v82 > (int)left )
        v61 = v82;
      v100.left = v61;
      if ( v84 < right )
        v62 = v84;
      v100.right = v62;
      if ( v61 >= v62 )
        goto LABEL_88;
      v63 = (unsigned int)v90;
      v64 = (unsigned int)top;
      v65 = v60;
      if ( (int)v90 > top )
        v64 = (unsigned int)v90;
      v100.top = v64;
      if ( v79 < (int)v60 )
        v65 = v79;
      v100.bottom = v65;
      if ( (int)v64 < v65 )
      {
        if ( !HIDWORD(v85) || !(_DWORD)v85 )
        {
          v66 = v82 >= v84 || (int)v90 >= v79;
          v67 = (int)left >= right || top >= (int)v60;
          if ( v66 )
          {
            if ( v67 )
              v100 = 0;
            else
              v100 = v31;
          }
          else if ( v67 )
          {
            v100 = v34;
          }
          else
          {
            if ( v82 < (int)left )
              LODWORD(left) = v82;
            v100.left = left;
            if ( (int)v90 < top )
              top = v90;
            v100.top = top;
            if ( v84 > right )
              right = v84;
            v100.right = right;
            if ( v79 > (int)v60 )
              LODWORD(v60) = v79;
            v100.bottom = v60;
          }
          SubtractRect(&v100, &v100, &v101);
          v31 = v100;
          goto LABEL_110;
        }
      }
      else
      {
LABEL_88:
        v100 = 0;
        if ( !memcmp(&Buf1, &Buf2, 0x10u) )
        {
          v31 = v34;
          v100 = v34;
LABEL_110:
          if ( a9 )
            *a9 = v31;
          if ( !a8 )
            goto LABEL_115;
          if ( (unsigned int)SetRectRgnIndirect(a8, &v100) )
          {
            v40 = HIDWORD(v101);
            v38 = DWORD2(v101);
            v39 = DWORD1(v101);
            v37 = v101;
LABEL_115:
            if ( v100.left >= v100.right || (ClipBox = 2, v100.top >= v100.bottom) )
              ClipBox = 1;
            goto LABEL_117;
          }
          goto LABEL_189;
        }
      }
      if ( a8 )
      {
        v14 = 0;
      }
      else
      {
        if ( !a9 )
        {
LABEL_117:
          if ( v37 < v38 && v39 < v40 )
          {
            if ( a10 )
            {
              GreDPtoLP(a2);
              v40 = HIDWORD(v101);
              v38 = DWORD2(v101);
              v39 = DWORD1(v101);
              v37 = v101;
            }
            GreBitBltInternal(
              a2,
              (unsigned int)v37,
              (unsigned int)v39,
              (unsigned int)(v38 - v37),
              v40 - v39,
              a2,
              v37 - HIDWORD(v91),
              v39 - v91,
              13369376,
              0,
              0);
          }
          v56 = (HRGN)v75;
          v68 = a9;
          goto LABEL_119;
        }
        v71 = CreateEmptyRgn(v64, v60, v63, left);
        v75 = v71;
        v14 = v71;
        if ( !v71 )
        {
LABEL_198:
          v40 = HIDWORD(v101);
          v38 = DWORD2(v101);
          v39 = DWORD1(v101);
          v37 = v101;
          goto LABEL_117;
        }
        v12 = (HRGN)v71;
      }
      v57 = v76;
      if ( !v76 )
      {
        v57 = CreateEmptyRgn(v64, v60, v63, left);
        v76 = v57;
      }
      SetRectRgnIndirect(v57, &Buf1);
      SetRectRgnIndirect(v12, &v99);
      if ( (unsigned int)GreCombineRgn(v12, v12, v57, 2) )
      {
        SetRectRgnIndirect(v57, &v101);
        ClipBox = GreCombineRgn(v12, v12, v57, 4);
        if ( ClipBox )
        {
          if ( !a9 || (unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_198;
        }
      }
LABEL_52:
      v42 = EmptyRgn;
      v43 = v77;
LABEL_53:
      if ( v88 )
        GreUnlockVisRgnShared();
      else
        GreUnlockVisRgn();
      GreDeleteObject(v42);
      GreDeleteObject(v57);
      GreDeleteObject(v14);
      GreDeleteObject(v43);
      GreDeleteObject(v92);
      GreDeleteObject(v86);
      return 0;
    }
LABEL_40:
    if ( (_DWORD)v14 )
    {
      v42 = EmptyRgn;
    }
    else
    {
      EmptyRgn = (HRGN)CreateEmptyRgn(v22, v15, v16, left);
      v42 = EmptyRgn;
      if ( !(unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
        goto LABEL_190;
    }
    v77 = CreateEmptyRgn(v22, v15, v16, left);
    v43 = v77;
    SetRectRgnIndirect(v77, &Buf1);
    if ( !(unsigned int)GreCombineRgn(v43, v43, v42, 1)
      || (v92 = CreateEmptyRgn(v45, v44, v46, v47),
          v48 = v92,
          SetRectRgnIndirect(v92, &v99),
          !(unsigned int)GreCombineRgn(v48, v48, v42, 1)) )
    {
      v14 = 0;
      v57 = v76;
      goto LABEL_53;
    }
    v53 = (unsigned __int64)v89;
    v54 = 1;
    if ( v89 != (HRGN)1 )
    {
      v86 = CreateEmptyRgn(v50, v49, v51, v52);
      if ( !(unsigned int)GreCombineRgn(v86, v77, 0, 5) )
      {
LABEL_150:
        v14 = v75;
        goto LABEL_51;
      }
      GreOffsetRgn(v86, HIDWORD(v85), (unsigned int)v85);
      v54 = GreCombineRgn(v86, v86, v92, 1);
      if ( v53 <= 1 )
      {
        v14 = 0;
      }
      else
      {
        v55 = CreateEmptyRgn(v50, v49, v51, v52);
        v75 = v55;
        v56 = (HRGN)v55;
        if ( !v54 )
        {
          v14 = v55;
          goto LABEL_51;
        }
        if ( v54 == 1 )
          goto LABEL_140;
        v90 = 0;
        GetDCOrgOnScreen(a2, &v90);
        GreCombineRgn(v56, v89, 0, 5);
        GreOffsetRgn(v56, (unsigned int)-(int)v90, (unsigned int)-HIDWORD(v90));
        v54 = GreCombineRgn(v86, v86, v56, 4);
        if ( !v54 )
        {
          v14 = (__int64)v56;
LABEL_51:
          v57 = v76;
          goto LABEL_52;
        }
        if ( v54 == 1 )
        {
LABEL_140:
          v68 = a9;
          if ( !a8 )
          {
            if ( !a9 )
              goto LABEL_145;
            if ( !v56 )
            {
              v75 = CreateEmptyRgn(v50, v49, v51, v52);
              v56 = (HRGN)v75;
              if ( !v75 )
                goto LABEL_145;
            }
            v12 = v56;
          }
          ClipBox = GreCombineRgn(v12, v92, v77, 2);
          if ( !ClipBox )
            goto LABEL_150;
          if ( v54 != 1 )
            ClipBox = GreCombineRgn(v12, v12, v86, 4);
          if ( a9 && !(unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_150;
LABEL_145:
          if ( v54 != 1 )
          {
            v89 = 0;
            GreGetDCOrg(a2, &v89);
            v69 = v86;
            GreOffsetRgn(v86, (unsigned int)v89, HIDWORD(v89));
            GreSelectVisRgnShared(a2, v86, 4);
            if ( a10 )
              GreDPtoLP(a2);
            GreBitBltInternal(
              a2,
              (unsigned int)v99.left,
              (unsigned int)v99.top,
              (unsigned int)(v99.right - v99.left),
              v99.bottom - v99.top,
              a2,
              v99.left - HIDWORD(v91),
              v99.top - v91,
              13369376,
              0,
              0);
            GreSelectVisRgnShared(a2, v86, 4);
            goto LABEL_120;
          }
LABEL_119:
          v69 = v86;
LABEL_120:
          if ( a10 && v68 )
            GreDPtoLP(a2);
          if ( v88 )
            GreUnlockVisRgnShared();
          else
            GreUnlockVisRgn();
          GreDeleteObject(EmptyRgn);
          GreDeleteObject(v76);
          GreDeleteObject(v56);
          GreDeleteObject(v77);
          GreDeleteObject(v92);
          GreDeleteObject(v69);
          return ClipBox;
        }
        v14 = (__int64)v56;
        GreOffsetRgn(v56, HIDWORD(v85), (unsigned int)v85);
        v54 = GreCombineRgn(v86, v86, v56, 4);
      }
      if ( !v54 )
        goto LABEL_51;
    }
    v56 = (HRGN)v75;
    goto LABEL_140;
  }
  if ( (unsigned __int64)v89 <= 1 && ClipBox == 2 )
  {
    v30 = v98;
    v22 = DWORD2(v98);
    if ( (int)v98 <= (int)v102 )
      v30 = v102;
    LODWORD(v98) = v30;
    if ( SDWORD2(v98) >= SDWORD2(v102) )
      v22 = DWORD2(v102);
    DWORD2(v98) = v22;
    if ( v30 < (int)v22 )
    {
      v15 = DWORD1(v98);
      v16 = HIDWORD(v98);
      if ( SDWORD1(v98) <= SDWORD1(v102) )
        v15 = DWORD1(v102);
      DWORD1(v98) = v15;
      if ( SHIDWORD(v98) >= SHIDWORD(v102) )
        v16 = HIDWORD(v102);
      HIDWORD(v98) = v16;
      if ( (int)v15 < (int)v16 )
      {
        v29 = v78;
        goto LABEL_14;
      }
    }
    v10 = a9;
    v57 = 0;
    v98 = 0;
    goto LABEL_173;
  }
  if ( (_DWORD)v14 )
  {
    v42 = EmptyRgn;
    goto LABEL_62;
  }
  EmptyRgn = (HRGN)CreateEmptyRgn((unsigned int)v85, v15, v16, left);
  v42 = EmptyRgn;
  if ( !(unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
  {
    v14 = 0;
    goto LABEL_152;
  }
  LODWORD(v14) = 1;
LABEL_62:
  v76 = CreateEmptyRgn(v22, v15, v16, left);
  v57 = v76;
  SetRectRgnIndirect(v76, &v102);
  ClipBox = GreCombineRgn(v42, v76, v42, 1);
  if ( !ClipBox )
    goto LABEL_219;
  v15 = ClipBox - 1;
  if ( ClipBox != 1 )
  {
    if ( ClipBox != 2 )
    {
      v29 = Buf1.m128i_i32[3];
      v24 = Buf1.m128i_i32[1];
      v20 = Buf1;
      bottom = v99.bottom;
      right = v99.right;
      top = v99.top;
      left = (unsigned int)v99.left;
      v83 = Buf1.m128i_i32[2];
      v81 = Buf1.m128i_i32[0];
      goto LABEL_12;
    }
    if ( (unsigned int)GreGetRgnBox(v42, &v98) )
    {
      v16 = HIDWORD(v98);
      v22 = DWORD2(v98);
      v15 = DWORD1(v98);
      v30 = v98;
      v29 = Buf1.m128i_i32[3];
      v24 = Buf1.m128i_i32[1];
      v20 = Buf1;
      bottom = v99.bottom;
      right = v99.right;
      top = v99.top;
      v83 = Buf1.m128i_i32[2];
      v81 = Buf1.m128i_i32[0];
      left = (unsigned int)v99.left;
      goto LABEL_14;
    }
LABEL_219:
    v14 = 0;
    goto LABEL_153;
  }
  v10 = a9;
LABEL_173:
  if ( a8 && !(unsigned int)SetEmptyRgn(a8) )
  {
LABEL_189:
    v42 = EmptyRgn;
LABEL_190:
    v14 = 0;
    v57 = v76;
    goto LABEL_153;
  }
  if ( v10 )
    *v10 = 0;
  if ( v88 )
    GreUnlockVisRgnShared();
  else
    GreUnlockVisRgn();
  GreDeleteObject(EmptyRgn);
  GreDeleteObject(v57);
  GreDeleteObject(0);
  GreDeleteObject(0);
  GreDeleteObject(0);
  GreDeleteObject(0);
  return 1;
}

```

## disassembly

```asm
0x1400a3944  mov     rax, rsp
0x1400a3947  mov     [rax+8], rbx
0x1400a394b  push    rbp
0x1400a394c  push    rsi
0x1400a394d  push    rdi
0x1400a394e  push    r12
0x1400a3950  push    r13
0x1400a3952  push    r14
0x1400a3954  push    r15
0x1400a3956  lea     rbp, [rax-0C8h]
0x1400a395d  sub     rsp, 190h
0x1400a3964  movaps  xmmword ptr [rax-48h], xmm6
0x1400a3968  mov     rax, cs:__security_cookie
0x1400a396f  xor     rax, rsp
0x1400a3972  mov     [rbp+0C0h+var_50], rax
0x1400a3976  mov     rax, [rbp+0C0h+arg_30]
0x1400a397d  xorps   xmm0, xmm0
0x1400a3980  mov     r12, [rbp+0C0h+arg_40]
0x1400a3987  xorps   xmm1, xmm1
0x1400a398a  mov     rsi, [rbp+0C0h+arg_20]
0x1400a3991  xor     r14d, r14d
0x1400a3994  mov     rbx, [rbp+0C0h+arg_28]
0x1400a399b  mov     r13, rdx
0x1400a399e  mov     rdi, [rbp+0C0h+arg_38]
0x1400a39a5  mov     [rbp+0C0h+var_F8], rax
0x1400a39a9  mov     [rbp+0C0h+var_110], r12
0x1400a39ad  movups  [rbp+0C0h+var_A0], xmm0
0x1400a39b1  mov     [rbp+0C0h+var_FC], r14d
0x1400a39b5  movups  [rbp+0C0h+Buf1], xmm1
0x1400a39b9  mov     dword ptr [rbp+0C0h+var_118], r9d
0x1400a39bd  movups  [rbp+0C0h+var_60], xmm0
0x1400a39c1  mov     dword ptr [rbp+0C0h+var_118+4], r8d
0x1400a39c5  movups  [rbp+0C0h+var_90], xmm1
0x1400a39c9  movups  [rbp+0C0h+var_80], xmm0
0x1400a39cd  movups  [rbp+0C0h+var_70], xmm1
0x1400a39d1  call    cs:__imp_W32GetUserSessionState
0x1400a39d8  nop     dword ptr [rax+rax+00h]
0x1400a39dd  lea     r8, [rbp+0C0h+var_FC]
0x1400a39e1  mov     rdx, r13
0x1400a39e4  mov     rcx, [rax+0DDA8h]
0x1400a39eb  mov     rcx, [rcx+28h]
0x1400a39ef  call    cs:__imp_GreLockVisRgnSharedOrExclusive
0x1400a39f6  nop     dword ptr [rax+rax+00h]
0x1400a39fb  test    eax, eax
0x1400a39fd  jz      loc_1400A3E8A
0x1400a3a03  lea     r8d, [r14+1]
0x1400a3a07  mov     [rbp+0C0h+var_140], r14
0x1400a3a0b  lea     rdx, [rbp+0C0h+var_A0]
0x1400a3a0f  mov     [rsp+1C0h+var_158], r14
0x1400a3a14  mov     rcx, r13
0x1400a3a17  mov     [rsp+1C0h+var_160], r14
0x1400a3a1c  mov     r15d, r14d
0x1400a3a1f  mov     [rsp+1C0h+var_150], r14
0x1400a3a24  mov     [rbp+0C0h+var_E0], r14
0x1400a3a28  mov     [rbp+0C0h+var_108], r14
0x1400a3a2c  call    cs:__imp_GreGetClipBox
0x1400a3a33  nop     dword ptr [rax+rax+00h]
0x1400a3a38  mov     r14d, eax
0x1400a3a3b  test    eax, eax
0x1400a3a3d  jz      loc_1400A44A7
0x1400a3a43  test    rsi, rsi
0x1400a3a46  lea     rcx, [rbp+0C0h+var_A0]
0x1400a3a4a  cmovnz  rcx, rsi
0x1400a3a4e  movups  xmm1, xmmword ptr [rcx]
0x1400a3a51  movaps  [rbp+0C0h+Buf1], xmm1
0x1400a3a55  test    rbx, rbx
0x1400a3a58  jz      short loc_1400A3A62
0x1400a3a5a  movups  xmm0, xmmword ptr [rbx]
0x1400a3a5d  movdqu  [rbp+0C0h+var_60], xmm0
0x1400a3a62  mov     esi, dword ptr [rbp+0C0h+var_118+4]
0x1400a3a65  mov     eax, dword ptr [rbp+0C0h+var_118]
0x1400a3a68  mov     dword ptr [rbp+0C0h+var_E8+4], esi
0x1400a3a6b  mov     dword ptr [rbp+0C0h+var_E8], eax
0x1400a3a6e  cmp     [rbp+0C0h+arg_48], r15d
0x1400a3a75  jnz     loc_1400A44B5
0x1400a3a7b  mov     ecx, r14d
0x1400a3a7e  sub     ecx, 1
0x1400a3a81  jz      loc_1400A45B1
0x1400a3a87  cmp     ecx, 2
0x1400a3a8a  jz      loc_1400A4671
0x1400a3a90  mov     ecx, dword ptr [rbp+0C0h+var_118]
0x1400a3a93  movdqa  xmm0, xmm1
0x1400a3a97  psrldq  xmm0, 8
0x1400a3a9c  movd    eax, xmm1
0x1400a3aa0  mov     [rbp+0C0h+var_130], eax
0x1400a3aa3  lea     r9d, [rsi+rax]
0x1400a3aa7  movd    eax, xmm0
0x1400a3aab  mov     dword ptr [rbp+0C0h+var_90], r9d
0x1400a3aaf  movdqa  xmm0, xmm1
0x1400a3ab3  psrldq  xmm0, 4
0x1400a3ab8  movd    r12d, xmm0
0x1400a3abd  movdqa  xmm0, xmm1
0x1400a3ac1  psrldq  xmm0, 0Ch
0x1400a3ac6  mov     [rbp+0C0h+var_120], eax
0x1400a3ac9  lea     r10d, [rsi+rax]
0x1400a3acd  movd    eax, xmm0
0x1400a3ad1  mov     dword ptr [rbp+0C0h+var_90+8], r10d
0x1400a3ad5  mov     [rsp+1C0h+var_148], eax
0x1400a3ad9  lea     r11d, [rcx+r12]
0x1400a3add  mov     dword ptr [rbp+0C0h+var_90+4], r11d
0x1400a3ae1  lea     esi, [rcx+rax]
0x1400a3ae4  mov     dword ptr [rbp+0C0h+var_90+0Ch], esi
0x1400a3ae7  test    rbx, rbx
0x1400a3aea  jnz     loc_1400A3E91
0x1400a3af0  mov     ebx, eax
0x1400a3af2  cmp     r14d, 2
0x1400a3af6  jnz     loc_1400A3C4C
0x1400a3afc  mov     r8d, dword ptr [rbp+0C0h+var_A0+0Ch]
0x1400a3b00  mov     ecx, dword ptr [rbp+0C0h+var_A0+8]
0x1400a3b03  mov     edx, dword ptr [rbp+0C0h+var_A0+4]
0x1400a3b06  mov     eax, dword ptr [rbp+0C0h+var_A0]
0x1400a3b09  cmp     [rbp+0C0h+var_F8], 1
0x1400a3b0e  ja      loc_1400A3C4C
0x1400a3b14  cmp     r9d, eax
0x1400a3b17  movdqa  [rbp+0C0h+Buf2], xmm1
0x1400a3b1c  cmovle  r9d, eax
0x1400a3b20  cmp     r10d, ecx
0x1400a3b23  mov     dword ptr [rbp+0C0h+var_90], r9d
0x1400a3b27  cmovge  r10d, ecx
0x1400a3b2b  mov     dword ptr [rbp+0C0h+var_90+8], r10d
0x1400a3b2f  cmp     r9d, r10d
0x1400a3b32  jge     short loc_1400A3B55
0x1400a3b34  cmp     r11d, edx
0x1400a3b37  cmovle  r11d, edx
0x1400a3b3b  cmp     esi, r8d
0x1400a3b3e  mov     dword ptr [rbp+0C0h+var_90+4], r11d
0x1400a3b42  cmovge  esi, r8d
0x1400a3b46  mov     [rbp+0C0h+var_100], esi
0x1400a3b49  mov     dword ptr [rbp+0C0h+var_90+0Ch], esi
0x1400a3b4c  cmp     r11d, esi
0x1400a3b4f  jl      loc_1400A425E
0x1400a3b55  xorps   xmm0, xmm0
0x1400a3b58  xorps   xmm3, xmm3
0x1400a3b5b  psrldq  xmm0, 0Ch
0x1400a3b60  xorps   xmm1, xmm1
0x1400a3b63  movd    [rbp+0C0h+var_100], xmm0
0x1400a3b68  xorps   xmm0, xmm0
0x1400a3b6b  psrldq  xmm0, 4
0x1400a3b70  psrldq  xmm1, 8
0x1400a3b75  movd    r11d, xmm0
0x1400a3b7a  movaps  [rbp+0C0h+var_90], xmm3
0x1400a3b7e  movd    r10d, xmm1
0x1400a3b83  movd    r9d, xmm3
0x1400a3b88  mov     esi, [rbp+0C0h+var_130]
0x1400a3b8b  cmp     esi, eax
0x1400a3b8d  mov     r15d, [rbp+0C0h+var_120]
0x1400a3b91  cmovle  esi, eax
0x1400a3b94  cmp     r15d, ecx
0x1400a3b97  mov     [rbp+0C0h+var_130], esi
0x1400a3b9a  cmovge  r15d, ecx
0x1400a3b9e  mov     dword ptr [rbp+0C0h+Buf1], esi
0x1400a3ba1  mov     [rbp+0C0h+var_120], r15d
0x1400a3ba5  mov     dword ptr [rbp+0C0h+Buf1+8], r15d
0x1400a3ba9  cmp     esi, r15d
0x1400a3bac  jge     short loc_1400A3BD4
0x1400a3bae  cmp     r12d, edx
0x1400a3bb1  cmovle  r12d, edx
0x1400a3bb5  cmp     ebx, r8d
0x1400a3bb8  mov     dword ptr [rbp+0C0h+var_F0], r12d
0x1400a3bbc  cmovge  ebx, r8d
0x1400a3bc0  mov     dword ptr [rbp+0C0h+Buf1+4], r12d
0x1400a3bc4  mov     [rsp+1C0h+var_148], ebx
0x1400a3bc8  mov     dword ptr [rbp+0C0h+Buf1+0Ch], ebx
0x1400a3bcb  cmp     r12d, ebx
0x1400a3bce  jl      loc_1400A4267
0x1400a3bd4  xorps   xmm0, xmm0
0x1400a3bd7  xorps   xmm6, xmm6
0x1400a3bda  psrldq  xmm0, 0Ch
0x1400a3bdf  xorps   xmm1, xmm1
0x1400a3be2  movd    eax, xmm0
0x1400a3be6  xor     r8d, r8d
0x1400a3be9  xorps   xmm0, xmm0
0x1400a3bec  psrldq  xmm1, 8
0x1400a3bf1  psrldq  xmm0, 4
0x1400a3bf6  movd    r12d, xmm0
0x1400a3bfb  movd    r15d, xmm1
0x1400a3c00  movd    esi, xmm6
0x1400a3c04  mov     dword ptr [rbp+0C0h+var_F0], r12d
0x1400a3c08  movaps  [rbp+0C0h+Buf1], xmm6
0x1400a3c0c  mov     [rsp+1C0h+var_148], eax
0x1400a3c10  mov     [rbp+0C0h+var_120], r15d
0x1400a3c14  mov     [rbp+0C0h+var_130], esi
0x1400a3c17  cmp     [rbp+0C0h+var_F8], 1
0x1400a3c1c  jz      loc_1400A42FF
0x1400a3c22  mov     ecx, dword ptr [rbp+0C0h+var_118+4]
0x1400a3c25  add     esi, ecx
0x1400a3c27  mov     dword ptr [rbp+0C0h+var_70], esi
0x1400a3c2a  lea     ebx, [rcx+r15]
0x1400a3c2e  mov     ecx, dword ptr [rbp+0C0h+var_118]
0x1400a3c31  mov     dword ptr [rbp+0C0h+var_70+8], ebx
0x1400a3c34  lea     r15d, [rcx+r12]
0x1400a3c38  lea     r12d, [rcx+rax]
0x1400a3c3c  cmp     esi, r9d
0x1400a3c3f  jle     loc_1400A3F8F
0x1400a3c45  mov     ecx, esi
0x1400a3c47  jmp     loc_1400A3F99
0x1400a3c4c  test    r15d, r15d
0x1400a3c4f  jz      loc_1400A4233
0x1400a3c55  mov     r12, [rbp+0C0h+var_140]
0x1400a3c59  call    cs:__imp_CreateEmptyRgn
0x1400a3c60  nop     dword ptr [rax+rax+00h]
0x1400a3c65  mov     rcx, rax
0x1400a3c68  mov     [rsp+1C0h+var_150], rax
0x1400a3c6d  lea     rdx, [rbp+0C0h+Buf1]
0x1400a3c71  mov     rsi, rax
0x1400a3c74  call    cs:__imp_SetRectRgnIndirect
0x1400a3c7b  nop     dword ptr [rax+rax+00h]
0x1400a3c80  mov     r15d, 1
0x1400a3c86  mov     r8, r12
0x1400a3c89  mov     r9d, r15d
0x1400a3c8c  mov     rdx, rsi
0x1400a3c8f  mov     rcx, rsi
0x1400a3c92  call    cs:__imp_GreCombineRgn
0x1400a3c99  nop     dword ptr [rax+rax+00h]
0x1400a3c9e  test    eax, eax
0x1400a3ca0  jz      loc_1400A48FA
0x1400a3ca6  call    cs:__imp_CreateEmptyRgn
0x1400a3cad  nop     dword ptr [rax+rax+00h]
0x1400a3cb2  mov     rcx, rax
0x1400a3cb5  mov     [rbp+0C0h+var_E0], rax
0x1400a3cb9  lea     rdx, [rbp+0C0h+var_90]
0x1400a3cbd  mov     rbx, rax
0x1400a3cc0  call    cs:__imp_SetRectRgnIndirect
0x1400a3cc7  nop     dword ptr [rax+rax+00h]
0x1400a3ccc  mov     r9d, r15d
0x1400a3ccf  mov     r8, r12
0x1400a3cd2  mov     rdx, rbx
0x1400a3cd5  mov     rcx, rbx
0x1400a3cd8  call    cs:__imp_GreCombineRgn
0x1400a3cdf  nop     dword ptr [rax+rax+00h]
0x1400a3ce4  test    eax, eax
0x1400a3ce6  jz      loc_1400A48FA
0x1400a3cec  mov     r12, [rbp+0C0h+var_F8]
0x1400a3cf0  lea     esi, [r15+3]
0x1400a3cf4  mov     ebx, r15d
0x1400a3cf7  cmp     r12, r15
0x1400a3cfa  jz      loc_1400A4352
0x1400a3d00  call    cs:__imp_CreateEmptyRgn
0x1400a3d07  nop     dword ptr [rax+rax+00h]
0x1400a3d0c  mov     rdx, [rsp+1C0h+var_150]
0x1400a3d11  lea     r9d, [r15+4]
0x1400a3d15  mov     rcx, rax
0x1400a3d18  mov     [rbp+0C0h+var_108], rax
0x1400a3d1c  xor     r8d, r8d
0x1400a3d1f  mov     rbx, rax
0x1400a3d22  call    cs:__imp_GreCombineRgn
0x1400a3d29  nop     dword ptr [rax+rax+00h]
0x1400a3d2e  test    eax, eax
0x1400a3d30  jz      loc_1400A449D
0x1400a3d36  mov     r15d, dword ptr [rbp+0C0h+var_118+4]
0x1400a3d3a  mov     rcx, rbx
0x1400a3d3d  mov     r8d, dword ptr [rbp+0C0h+var_118]
0x1400a3d41  mov     edx, r15d
0x1400a3d44  call    cs:__imp_GreOffsetRgn
0x1400a3d4b  nop     dword ptr [rax+rax+00h]
0x1400a3d50  mov     r8, [rbp+0C0h+var_E0]
0x1400a3d54  lea     r9d, [rsi-3]
0x1400a3d58  mov     rdx, rbx
0x1400a3d5b  mov     rcx, rbx
0x1400a3d5e  call    cs:__imp_GreCombineRgn
0x1400a3d65  nop     dword ptr [rax+rax+00h]
0x1400a3d6a  mov     ebx, eax
0x1400a3d6c  cmp     r12, 1
0x1400a3d70  jbe     loc_1400A4899
0x1400a3d76  call    cs:__imp_CreateEmptyRgn
0x1400a3d7d  nop     dword ptr [rax+rax+00h]
0x1400a3d82  mov     [rsp+1C0h+var_160], rax
0x1400a3d87  mov     r12, rax
0x1400a3d8a  test    ebx, ebx
0x1400a3d8c  jz      loc_1400A46D1
0x1400a3d92  cmp     ebx, 1
0x1400a3d95  jz      loc_1400A4357
0x1400a3d9b  lea     rdx, [rbp+0C0h+var_F0]
0x1400a3d9f  mov     [rbp+0C0h+var_F0], 0
0x1400a3da7  mov     rcx, r13
0x1400a3daa  call    GetDCOrgOnScreen
0x1400a3daf  mov     rdx, [rbp+0C0h+var_F8]
0x1400a3db3  lea     r9d, [rsi+1]
0x1400a3db7  xor     r8d, r8d
0x1400a3dba  mov     rcx, r12
0x1400a3dbd  call    cs:__imp_GreCombineRgn
0x1400a3dc4  nop     dword ptr [rax+rax+00h]
0x1400a3dc9  mov     r8d, dword ptr [rbp+0C0h+var_F0+4]
0x1400a3dcd  mov     rcx, r12
0x1400a3dd0  mov     edx, dword ptr [rbp+0C0h+var_F0]
0x1400a3dd3  neg     r8d
0x1400a3dd6  neg     edx
0x1400a3dd8  call    cs:__imp_GreOffsetRgn
0x1400a3ddf  nop     dword ptr [rax+rax+00h]
0x1400a3de4  mov     rdx, [rbp+0C0h+var_108]
0x1400a3de8  mov     r9d, esi
0x1400a3deb  mov     rcx, rdx
0x1400a3dee  mov     r8, r12
0x1400a3df1  call    cs:__imp_GreCombineRgn
0x1400a3df8  nop     dword ptr [rax+rax+00h]
0x1400a3dfd  mov     ebx, eax
0x1400a3dff  test    eax, eax
0x1400a3e01  jnz     loc_1400A4311
0x1400a3e07  mov     r15, r12
0x1400a3e0a  mov     rbx, [rsp+1C0h+var_158]
  ... truncated ...
```
