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
        unsigned int a3,
        unsigned int a4,
        __m128i *a5,
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
  unsigned int ClipBox; // r14d
  __m128i *v16; // rcx
  __m128i v17; // xmm1
  int v18; // esi
  int v19; // r9d
  int v20; // r12d
  int v21; // r10d
  int v22; // eax
  int v23; // r11d
  int v24; // esi
  int v25; // ebx
  int v26; // r8d
  int v27; // ecx
  int v28; // edx
  int v29; // eax
  struct tagRECT v30; // xmm3
  int v31; // esi
  int v32; // r15d
  struct tagRECT v33; // xmm6
  int v34; // eax
  int v35; // r8d
  int v36; // esi
  int v37; // ebx
  int v38; // r15d
  int v39; // r12d
  int v40; // ecx
  HRGN v41; // r12
  __int64 v42; // rsi
  __int64 v43; // rbx
  unsigned __int64 v44; // r12
  int v45; // ebx
  __int64 v46; // rax
  HRGN v47; // r12
  __int64 v48; // rbx
  int v50; // eax
  int v51; // edx
  int v52; // ecx
  int v53; // eax
  int v54; // ecx
  int v55; // eax
  BOOL v56; // ecx
  BOOL v57; // eax
  struct tagRECT *v58; // r15
  __int64 v59; // rbx
  int v60; // esi
  __int64 v61; // rax
  int v62; // ecx
  __int32 v63; // ecx
  int v64; // ecx
  __int64 v65; // [rsp+68h] [rbp-A0h]
  __int64 v66; // [rsp+70h] [rbp-98h]
  __int64 v67; // [rsp+78h] [rbp-90h]
  int v68; // [rsp+80h] [rbp-88h]
  int v69; // [rsp+80h] [rbp-88h]
  HRGN EmptyRgn; // [rsp+88h] [rbp-80h]
  int v71; // [rsp+98h] [rbp-70h]
  int v72; // [rsp+98h] [rbp-70h]
  int v73; // [rsp+A8h] [rbp-60h]
  int v74; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v75; // [rsp+B0h] [rbp-58h]
  __int64 v76; // [rsp+C0h] [rbp-48h]
  int v77; // [rsp+C8h] [rbp-40h]
  int v78; // [rsp+CCh] [rbp-3Ch] BYREF
  HRGN v79; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v80; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v81; // [rsp+E0h] [rbp-28h]
  __int64 v82; // [rsp+E8h] [rbp-20h]
  __int64 v83; // [rsp+F0h] [rbp-18h]
  int v84; // [rsp+F8h] [rbp-10h]
  int v85; // [rsp+FCh] [rbp-Ch]
  __m128i Buf2; // [rsp+108h] [rbp+0h] BYREF
  __m128i Buf1; // [rsp+118h] [rbp+10h] BYREF
  __int128 v88; // [rsp+128h] [rbp+20h] BYREF
  __int128 v89; // [rsp+138h] [rbp+30h] BYREF
  struct tagRECT v90; // [rsp+148h] [rbp+40h] BYREF
  __int128 v91; // [rsp+158h] [rbp+50h] BYREF
  __int128 v92; // [rsp+168h] [rbp+60h] BYREF

  v10 = a9;
  v12 = a8;
  v79 = a7;
  v88 = 0;
  v78 = 0;
  Buf1 = 0;
  v75 = __PAIR64__(a3, a4);
  v92 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  UserSessionState = W32GetUserSessionState(a1);
  if ( !(unsigned int)GreLockVisRgnSharedOrExclusive(
                        *(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                        a2,
                        &v78) )
    return 0;
  EmptyRgn = 0;
  v66 = 0;
  v65 = 0;
  v14 = 0;
  v67 = 0;
  v82 = 0;
  v76 = 0;
  ClipBox = GreGetClipBox(a2, &v88, 1);
  if ( !ClipBox )
  {
    v41 = 0;
    goto LABEL_152;
  }
  v16 = (__m128i *)&v88;
  if ( a5 )
    v16 = a5;
  v17 = *v16;
  Buf1 = *v16;
  if ( a6 )
    v92 = (__int128)*a6;
  v18 = HIDWORD(v75);
  v81 = v75;
  if ( a10 )
  {
    v60 = 0;
    GreLPtoDP(a2);
    GreLPtoDP(a2);
    if ( (GreGetLayout(a2) & 1) != 0 )
    {
      v62 = v88;
      v60 = 1;
      LODWORD(v88) = DWORD2(v88);
      DWORD2(v88) = v62;
      v63 = Buf1.m128i_i32[0];
      Buf1.m128i_i32[0] = Buf1.m128i_i32[2];
      Buf1.m128i_i32[2] = v63;
    }
    if ( a6 )
    {
      GreLPtoDP(a2);
      if ( v60 )
      {
        v64 = v92;
        LODWORD(v92) = DWORD2(v92);
        DWORD2(v92) = v64;
      }
    }
    v84 = HIDWORD(v75);
    v85 = v75;
    v83 = 0;
    GreLPtoDP(a2);
    v18 = v84 - v83;
    v17 = Buf1;
    LODWORD(v75) = v85 - HIDWORD(v83);
    HIDWORD(v75) = v84 - v83;
  }
  if ( ClipBox == 1 )
  {
    v48 = 0;
    goto LABEL_173;
  }
  if ( ClipBox == 3 )
  {
    EmptyRgn = (HRGN)CreateEmptyRgn();
    v41 = EmptyRgn;
    if ( (unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
    {
      v17 = Buf1;
      LODWORD(v14) = 1;
      goto LABEL_10;
    }
LABEL_152:
    v48 = 0;
LABEL_153:
    v42 = 0;
    goto LABEL_53;
  }
LABEL_10:
  v71 = _mm_cvtsi128_si32(v17);
  v19 = v18 + v71;
  LODWORD(v89) = v18 + v71;
  v20 = _mm_cvtsi128_si32(_mm_srli_si128(v17, 4));
  v73 = _mm_cvtsi128_si32(_mm_srli_si128(v17, 8));
  v21 = v18 + v73;
  v22 = _mm_cvtsi128_si32(_mm_srli_si128(v17, 12));
  DWORD2(v89) = v18 + v73;
  v68 = v22;
  v23 = v75 + v20;
  DWORD1(v89) = v75 + v20;
  v24 = v75 + v22;
  HIDWORD(v89) = v75 + v22;
  if ( !a6 )
  {
    v25 = v22;
LABEL_12:
    if ( ClipBox != 2 )
      goto LABEL_40;
    v26 = HIDWORD(v88);
    v27 = DWORD2(v88);
    v28 = DWORD1(v88);
    v29 = v88;
LABEL_14:
    if ( (unsigned __int64)v79 <= 1 )
    {
      Buf2 = v17;
      if ( v19 <= v29 )
        v19 = v29;
      LODWORD(v89) = v19;
      if ( v21 >= v27 )
        v21 = v27;
      DWORD2(v89) = v21;
      if ( v19 >= v21 )
        goto LABEL_25;
      if ( v23 <= v28 )
        v23 = v28;
      DWORD1(v89) = v23;
      if ( v24 >= v26 )
        v24 = v26;
      v77 = v24;
      HIDWORD(v89) = v24;
      if ( v23 < v24 )
      {
        v30 = (struct tagRECT)v89;
      }
      else
      {
LABEL_25:
        v30 = 0;
        v77 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
        v23 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        v89 = 0;
        v21 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
        v19 = _mm_cvtsi128_si32((__m128i)0LL);
      }
      v31 = v71;
      v32 = v73;
      if ( v71 <= v29 )
        v31 = v29;
      v72 = v31;
      if ( v73 >= v27 )
        v32 = v27;
      Buf1.m128i_i32[0] = v31;
      v74 = v32;
      Buf1.m128i_i32[2] = v32;
      if ( v31 >= v32 )
        goto LABEL_36;
      if ( v20 <= v28 )
        v20 = v28;
      LODWORD(v80) = v20;
      if ( v25 >= v26 )
        v25 = v26;
      Buf1.m128i_i32[1] = v20;
      v69 = v25;
      Buf1.m128i_i32[3] = v25;
      if ( v20 < v25 )
      {
        v33 = (struct tagRECT)Buf1;
        v35 = 1;
        v34 = v25;
      }
      else
      {
LABEL_36:
        v33 = 0;
        v34 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
        v35 = 0;
        v20 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        v32 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
        v31 = _mm_cvtsi128_si32((__m128i)0LL);
        LODWORD(v80) = v20;
        Buf1 = 0;
        v69 = v34;
        v74 = v32;
        v72 = v31;
      }
      if ( v79 == (HRGN)1 )
      {
        v51 = v77;
      }
      else
      {
        v36 = HIDWORD(v75) + v31;
        LODWORD(v91) = v36;
        v37 = HIDWORD(v75) + v32;
        DWORD2(v91) = HIDWORD(v75) + v32;
        v38 = v75 + v20;
        v39 = v75 + v34;
        if ( v36 <= v19 )
        {
          v36 = v19;
          LODWORD(v91) = v19;
          v40 = v19;
        }
        else
        {
          v40 = v36;
        }
        if ( v37 < v21 )
        {
          v50 = v37;
        }
        else
        {
          v37 = v21;
          v50 = v21;
          DWORD2(v91) = v21;
        }
        v51 = v77;
        if ( v40 < v50 )
        {
          if ( v38 <= v23 )
            v38 = v23;
          DWORD1(v91) = v38;
          if ( v39 >= v77 )
            v39 = v77;
          HIDWORD(v91) = v39;
          if ( v38 < v39 )
            goto LABEL_77;
        }
      }
      v39 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      v38 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v91 = 0;
      v37 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v36 = _mm_cvtsi128_si32((__m128i)0LL);
LABEL_77:
      if ( !v35 )
      {
        v90 = v30;
        goto LABEL_110;
      }
      v52 = v19;
      v53 = v21;
      if ( v72 > v19 )
        v52 = v72;
      v90.left = v52;
      if ( v74 < v21 )
        v53 = v74;
      v90.right = v53;
      if ( v52 >= v53 )
        goto LABEL_88;
      v54 = v23;
      v55 = v51;
      if ( (int)v80 > v23 )
        v54 = v80;
      v90.top = v54;
      if ( v69 < v51 )
        v55 = v69;
      v90.bottom = v55;
      if ( v54 < v55 )
      {
        if ( !HIDWORD(v75) || !(_DWORD)v75 )
        {
          v56 = v72 >= v74 || (int)v80 >= v69;
          v57 = v19 >= v21 || v23 >= v51;
          if ( v56 )
          {
            if ( v57 )
              v90 = 0;
            else
              v90 = v30;
          }
          else if ( v57 )
          {
            v90 = v33;
          }
          else
          {
            if ( v72 < v19 )
              v19 = v72;
            v90.left = v19;
            if ( (int)v80 < v23 )
              v23 = v80;
            v90.top = v23;
            if ( v74 > v21 )
              v21 = v74;
            v90.right = v21;
            if ( v69 > v51 )
              v51 = v69;
            v90.bottom = v51;
          }
          SubtractRect(&v90, &v90, &v91);
          v30 = v90;
          goto LABEL_110;
        }
      }
      else
      {
LABEL_88:
        v90 = 0;
        if ( !memcmp(&Buf1, &Buf2, 0x10u) )
        {
          v30 = v33;
          v90 = v33;
LABEL_110:
          if ( a9 )
            *a9 = v30;
          if ( !a8 )
            goto LABEL_115;
          if ( (unsigned int)SetRectRgnIndirect(a8, &v90) )
          {
            v39 = HIDWORD(v91);
            v37 = DWORD2(v91);
            v38 = DWORD1(v91);
            v36 = v91;
LABEL_115:
            if ( v90.left >= v90.right || (ClipBox = 2, v90.top >= v90.bottom) )
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
          if ( v36 < v37 && v38 < v39 )
          {
            if ( a10 )
            {
              GreDPtoLP(a2);
              v39 = HIDWORD(v91);
              v37 = DWORD2(v91);
              v38 = DWORD1(v91);
              v36 = v91;
            }
            GreBitBltInternal(
              a2,
              (unsigned int)v36,
              (unsigned int)v38,
              (unsigned int)(v37 - v36),
              v39 - v38,
              a2,
              v36 - HIDWORD(v81),
              v38 - v81,
              13369376,
              0,
              0);
          }
          v47 = (HRGN)v65;
          v58 = a9;
          goto LABEL_119;
        }
        v61 = CreateEmptyRgn();
        v65 = v61;
        v14 = v61;
        if ( !v61 )
        {
LABEL_198:
          v39 = HIDWORD(v91);
          v37 = DWORD2(v91);
          v38 = DWORD1(v91);
          v36 = v91;
          goto LABEL_117;
        }
        v12 = (HRGN)v61;
      }
      v48 = v66;
      if ( !v66 )
      {
        v48 = CreateEmptyRgn();
        v66 = v48;
      }
      SetRectRgnIndirect(v48, &Buf1);
      SetRectRgnIndirect(v12, &v89);
      if ( (unsigned int)GreCombineRgn(v12, v12, v48, 2) )
      {
        SetRectRgnIndirect(v48, &v91);
        ClipBox = GreCombineRgn(v12, v12, v48, 4);
        if ( ClipBox )
        {
          if ( !a9 || (unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_198;
        }
      }
LABEL_52:
      v41 = EmptyRgn;
      v42 = v67;
LABEL_53:
      if ( v78 )
        GreUnlockVisRgnShared();
      else
        GreUnlockVisRgn();
      GreDeleteObject(v41);
      GreDeleteObject(v48);
      GreDeleteObject(v14);
      GreDeleteObject(v42);
      GreDeleteObject(v82);
      GreDeleteObject(v76);
      return 0;
    }
LABEL_40:
    if ( (_DWORD)v14 )
    {
      v41 = EmptyRgn;
    }
    else
    {
      EmptyRgn = (HRGN)CreateEmptyRgn();
      v41 = EmptyRgn;
      if ( !(unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
        goto LABEL_190;
    }
    v67 = CreateEmptyRgn();
    v42 = v67;
    SetRectRgnIndirect(v67, &Buf1);
    if ( !(unsigned int)GreCombineRgn(v42, v42, v41, 1)
      || (v82 = CreateEmptyRgn(),
          v43 = v82,
          SetRectRgnIndirect(v82, &v89),
          !(unsigned int)GreCombineRgn(v43, v43, v41, 1)) )
    {
      v14 = 0;
      v48 = v66;
      goto LABEL_53;
    }
    v44 = (unsigned __int64)v79;
    v45 = 1;
    if ( v79 != (HRGN)1 )
    {
      v76 = CreateEmptyRgn();
      if ( !(unsigned int)GreCombineRgn(v76, v67, 0, 5) )
      {
LABEL_150:
        v14 = v65;
        goto LABEL_51;
      }
      GreOffsetRgn(v76, HIDWORD(v75), (unsigned int)v75);
      v45 = GreCombineRgn(v76, v76, v82, 1);
      if ( v44 <= 1 )
      {
        v14 = 0;
      }
      else
      {
        v46 = CreateEmptyRgn();
        v65 = v46;
        v47 = (HRGN)v46;
        if ( !v45 )
        {
          v14 = v46;
          goto LABEL_51;
        }
        if ( v45 == 1 )
          goto LABEL_140;
        v80 = 0;
        GetDCOrgOnScreen(a2, &v80);
        GreCombineRgn(v47, v79, 0, 5);
        GreOffsetRgn(v47, (unsigned int)-(int)v80, (unsigned int)-HIDWORD(v80));
        v45 = GreCombineRgn(v76, v76, v47, 4);
        if ( !v45 )
        {
          v14 = (__int64)v47;
LABEL_51:
          v48 = v66;
          goto LABEL_52;
        }
        if ( v45 == 1 )
        {
LABEL_140:
          v58 = a9;
          if ( !a8 )
          {
            if ( !a9 )
              goto LABEL_145;
            if ( !v47 )
            {
              v65 = CreateEmptyRgn();
              v47 = (HRGN)v65;
              if ( !v65 )
                goto LABEL_145;
            }
            v12 = v47;
          }
          ClipBox = GreCombineRgn(v12, v82, v67, 2);
          if ( !ClipBox )
            goto LABEL_150;
          if ( v45 != 1 )
            ClipBox = GreCombineRgn(v12, v12, v76, 4);
          if ( a9 && !(unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_150;
LABEL_145:
          if ( v45 != 1 )
          {
            v79 = 0;
            GreGetDCOrg(a2, &v79);
            v59 = v76;
            GreOffsetRgn(v76, (unsigned int)v79, HIDWORD(v79));
            GreSelectVisRgnShared(a2, v76, 4);
            if ( a10 )
              GreDPtoLP(a2);
            GreBitBltInternal(
              a2,
              (unsigned int)v89,
              DWORD1(v89),
              (unsigned int)(DWORD2(v89) - v89),
              HIDWORD(v89) - DWORD1(v89),
              a2,
              v89 - HIDWORD(v81),
              DWORD1(v89) - v81,
              13369376,
              0,
              0);
            GreSelectVisRgnShared(a2, v76, 4);
            goto LABEL_120;
          }
LABEL_119:
          v59 = v76;
LABEL_120:
          if ( a10 && v58 )
            GreDPtoLP(a2);
          if ( v78 )
            GreUnlockVisRgnShared();
          else
            GreUnlockVisRgn();
          GreDeleteObject(EmptyRgn);
          GreDeleteObject(v66);
          GreDeleteObject(v47);
          GreDeleteObject(v67);
          GreDeleteObject(v82);
          GreDeleteObject(v59);
          return ClipBox;
        }
        v14 = (__int64)v47;
        GreOffsetRgn(v47, HIDWORD(v75), (unsigned int)v75);
        v45 = GreCombineRgn(v76, v76, v47, 4);
      }
      if ( !v45 )
        goto LABEL_51;
    }
    v47 = (HRGN)v65;
    goto LABEL_140;
  }
  if ( (unsigned __int64)v79 <= 1 && ClipBox == 2 )
  {
    v29 = v88;
    v27 = DWORD2(v88);
    if ( (int)v88 <= (int)v92 )
      v29 = v92;
    LODWORD(v88) = v29;
    if ( SDWORD2(v88) >= SDWORD2(v92) )
      v27 = DWORD2(v92);
    DWORD2(v88) = v27;
    if ( v29 < v27 )
    {
      v28 = DWORD1(v88);
      v26 = HIDWORD(v88);
      if ( SDWORD1(v88) <= SDWORD1(v92) )
        v28 = DWORD1(v92);
      DWORD1(v88) = v28;
      if ( SHIDWORD(v88) >= SHIDWORD(v92) )
        v26 = HIDWORD(v92);
      HIDWORD(v88) = v26;
      if ( v28 < v26 )
      {
        v25 = v68;
        goto LABEL_14;
      }
    }
    v10 = a9;
    v48 = 0;
    v88 = 0;
    goto LABEL_173;
  }
  if ( (_DWORD)v14 )
  {
    v41 = EmptyRgn;
    goto LABEL_62;
  }
  EmptyRgn = (HRGN)CreateEmptyRgn();
  v41 = EmptyRgn;
  if ( !(unsigned int)GetTrueClipRgn(a2, EmptyRgn) )
  {
    v14 = 0;
    goto LABEL_152;
  }
  LODWORD(v14) = 1;
LABEL_62:
  v66 = CreateEmptyRgn();
  v48 = v66;
  SetRectRgnIndirect(v66, &v92);
  ClipBox = GreCombineRgn(v41, v66, v41, 1);
  if ( !ClipBox )
    goto LABEL_219;
  if ( ClipBox != 1 )
  {
    if ( ClipBox != 2 )
    {
      v25 = Buf1.m128i_i32[3];
      v20 = Buf1.m128i_i32[1];
      v17 = Buf1;
      v24 = HIDWORD(v89);
      v21 = DWORD2(v89);
      v23 = DWORD1(v89);
      v19 = v89;
      v73 = Buf1.m128i_i32[2];
      v71 = Buf1.m128i_i32[0];
      goto LABEL_12;
    }
    if ( (unsigned int)GreGetRgnBox(v41, &v88) )
    {
      v26 = HIDWORD(v88);
      v27 = DWORD2(v88);
      v28 = DWORD1(v88);
      v29 = v88;
      v25 = Buf1.m128i_i32[3];
      v20 = Buf1.m128i_i32[1];
      v17 = Buf1;
      v24 = HIDWORD(v89);
      v21 = DWORD2(v89);
      v23 = DWORD1(v89);
      v73 = Buf1.m128i_i32[2];
      v71 = Buf1.m128i_i32[0];
      v19 = v89;
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
    v41 = EmptyRgn;
LABEL_190:
    v14 = 0;
    v48 = v66;
    goto LABEL_153;
  }
  if ( v10 )
    *v10 = 0;
  if ( v78 )
    GreUnlockVisRgnShared();
  else
    GreUnlockVisRgn();
  GreDeleteObject(EmptyRgn);
  GreDeleteObject(v48);
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
