# InternalScrollDC(tagWND *,HDC__ *,int,int,tagRECT *,tagRECT *,HRGN__ *,HRGN__ *,tagRECT *,int)

- ea: `0x1401ae678`
- end: `0x1401af647`
- name: `?InternalScrollDC@@YAHPEAUtagWND@@PEAUHDC__@@HHPEAUtagRECT@@2PEAUHRGN__@@32H@Z`
- size: `4047`
- prototype: `int(struct tagWND *, HDC, int, int, struct tagRECT *, struct tagRECT *, HRGN, HRGN, struct tagRECT *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140034bf8`
- `0x1401ae57c`

## callees

- `0x140037a10`
- `0x1400386f0`
- `0x140041870`
- `0x140060630`
- `0x1401ae678`
- `0x1401af650`
- `0x1401af734`
- `0x1401afbcc`
- `0x140342fa0`
- `0x1403430e0`

## import_xrefs

- `win32kbase!GreGetDCOrg` at `0x1401af103`
- `win32kbase!GreGetDCOrg` at `0x1401af103`
- `win32kbase!GreGetRgnBox` at `0x1401aec73`
- `win32kbase!GreGetRgnBox` at `0x1401af1bd`
- `win32kbase!GreGetRgnBox` at `0x1401af5b4`
- `win32kbase!GreGetRgnBox` at `0x1401aec73`
- `win32kbase!GreGetRgnBox` at `0x1401af1bd`
- `win32kbase!GreGetRgnBox` at `0x1401af5b4`
- `win32kbase!SetEmptyRgn` at `0x1401af2f0`
- `win32kbase!SetEmptyRgn` at `0x1401af2f0`
- `win32kbase!GreGetClipBox` at `0x1401ae760`
- `win32kbase!GreGetClipBox` at `0x1401ae760`
- `win32kbase!GreLockVisRgnSharedOrExclusive` at `0x1401ae723`
- `win32kbase!GreLockVisRgnSharedOrExclusive` at `0x1401ae723`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401aeb56`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401aeec4`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401af31b`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401aeb56`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401aeec4`
- `win32kbase!GreUnlockVisRgnShared` at `0x1401af31b`
- `win32kbase!GreSelectVisRgnShared` at `0x1401af132`
- `win32kbase!GreSelectVisRgnShared` at `0x1401af1a6`
- `win32kbase!GreSelectVisRgnShared` at `0x1401af132`
- `win32kbase!GreSelectVisRgnShared` at `0x1401af1a6`
- `win32kbase!GreUnlockVisRgn` at `0x1401af3da`
- `win32kbase!GreUnlockVisRgn` at `0x1401af3eb`
- `win32kbase!GreUnlockVisRgn` at `0x1401af420`
- `win32kbase!GreUnlockVisRgn` at `0x1401af3da`
- `win32kbase!GreUnlockVisRgn` at `0x1401af3eb`
- `win32kbase!GreUnlockVisRgn` at `0x1401af420`
- `win32kbase!SetRectRgnIndirect` at `0x1401ae9a8`
- `win32kbase!SetRectRgnIndirect` at `0x1401ae9f4`
- `win32kbase!SetRectRgnIndirect` at `0x1401aec26`
- `win32kbase!SetRectRgnIndirect` at `0x1401aee58`
- `win32kbase!SetRectRgnIndirect` at `0x1401af526`
- `win32kbase!SetRectRgnIndirect` at `0x1401af539`
- `win32kbase!SetRectRgnIndirect` at `0x1401af56f`
- `win32kbase!SetRectRgnIndirect` at `0x1401ae9a8`
- `win32kbase!SetRectRgnIndirect` at `0x1401ae9f4`
- `win32kbase!SetRectRgnIndirect` at `0x1401aec26`
- `win32kbase!SetRectRgnIndirect` at `0x1401aee58`
- `win32kbase!SetRectRgnIndirect` at `0x1401af526`
- `win32kbase!SetRectRgnIndirect` at `0x1401af539`
- `win32kbase!SetRectRgnIndirect` at `0x1401af56f`
- `win32kbase!CreateEmptyRgn` at `0x1401ae98d`
- `win32kbase!CreateEmptyRgn` at `0x1401ae9da`
- `win32kbase!CreateEmptyRgn` at `0x1401aea34`
- `win32kbase!CreateEmptyRgn` at `0x1401aeaaa`
- `win32kbase!CreateEmptyRgn` at `0x1401aebdf`
- `win32kbase!CreateEmptyRgn` at `0x1401aec0b`
- `win32kbase!CreateEmptyRgn` at `0x1401aef67`
- `win32kbase!CreateEmptyRgn` at `0x1401af3a5`
- `win32kbase!CreateEmptyRgn` at `0x1401af44d`
- `win32kbase!CreateEmptyRgn` at `0x1401af46f`
- `win32kbase!CreateEmptyRgn` at `0x1401af50b`
- `win32kbase!CreateEmptyRgn` at `0x1401ae98d`
- `win32kbase!CreateEmptyRgn` at `0x1401ae9da`
- `win32kbase!CreateEmptyRgn` at `0x1401aea34`
- `win32kbase!CreateEmptyRgn` at `0x1401aeaaa`
- `win32kbase!CreateEmptyRgn` at `0x1401aebdf`
- `win32kbase!CreateEmptyRgn` at `0x1401aec0b`
- `win32kbase!CreateEmptyRgn` at `0x1401aef67`
- `win32kbase!CreateEmptyRgn` at `0x1401af3a5`
- `win32kbase!CreateEmptyRgn` at `0x1401af44d`
- `win32kbase!CreateEmptyRgn` at `0x1401af46f`
- `win32kbase!CreateEmptyRgn` at `0x1401af50b`
- `win32kbase!GreCombineRgn` at `0x1401ae9c6`
- `win32kbase!GreCombineRgn` at `0x1401aea0c`
- `win32kbase!GreCombineRgn` at `0x1401aea56`
- `win32kbase!GreCombineRgn` at `0x1401aea92`
- `win32kbase!GreCombineRgn` at `0x1401aeaf1`
- `win32kbase!GreCombineRgn` at `0x1401aeb25`
- `win32kbase!GreCombineRgn` at `0x1401aec41`
- `win32kbase!GreCombineRgn` at `0x1401af070`
- `win32kbase!GreCombineRgn` at `0x1401af0aa`
- `win32kbase!GreCombineRgn` at `0x1401af0d3`
- `win32kbase!GreCombineRgn` at `0x1401af554`
- `win32kbase!GreCombineRgn` at `0x1401af58a`
- `win32kbase!GreCombineRgn` at `0x1401ae9c6`
- `win32kbase!GreCombineRgn` at `0x1401aea0c`
- `win32kbase!GreCombineRgn` at `0x1401aea56`
- `win32kbase!GreCombineRgn` at `0x1401aea92`
- `win32kbase!GreCombineRgn` at `0x1401aeaf1`
- `win32kbase!GreCombineRgn` at `0x1401aeb25`
- `win32kbase!GreCombineRgn` at `0x1401aec41`
- `win32kbase!GreCombineRgn` at `0x1401af070`
- `win32kbase!GreCombineRgn` at `0x1401af0aa`
- `win32kbase!GreCombineRgn` at `0x1401af0d3`
- `win32kbase!GreCombineRgn` at `0x1401af554`
- `win32kbase!GreCombineRgn` at `0x1401af58a`
- `win32kbase!GreOffsetRgn` at `0x1401aea78`
- `win32kbase!GreOffsetRgn` at `0x1401aeb0c`
- `win32kbase!GreOffsetRgn` at `0x1401af057`
- `win32kbase!GreOffsetRgn` at `0x1401af11d`
- `win32kbase!GreOffsetRgn` at `0x1401aea78`
- `win32kbase!GreOffsetRgn` at `0x1401aeb0c`
- `win32kbase!GreOffsetRgn` at `0x1401af057`
- `win32kbase!GreOffsetRgn` at `0x1401af11d`
- `win32kbase!GreDeleteObject` at `0x1401aeb65`
- `win32kbase!GreDeleteObject` at `0x1401aeb74`
- `win32kbase!GreDeleteObject` at `0x1401aeb83`
- `win32kbase!GreDeleteObject` at `0x1401aeb92`
- `win32kbase!GreDeleteObject` at `0x1401aeba2`
- `win32kbase!GreDeleteObject` at `0x1401aebb2`
- `win32kbase!GreDeleteObject` at `0x1401aeed4`
- `win32kbase!GreDeleteObject` at `0x1401aeee5`
- `win32kbase!GreDeleteObject` at `0x1401aeef4`
- `win32kbase!GreDeleteObject` at `0x1401aef05`
- `win32kbase!GreDeleteObject` at `0x1401aef15`
- `win32kbase!GreDeleteObject` at `0x1401aef24`
- `win32kbase!GreDeleteObject` at `0x1401af32b`
- `win32kbase!GreDeleteObject` at `0x1401af33a`
- `win32kbase!GreDeleteObject` at `0x1401af348`
- `win32kbase!GreDeleteObject` at `0x1401af356`
- `win32kbase!GreDeleteObject` at `0x1401af364`
- `win32kbase!GreDeleteObject` at `0x1401af372`
- `win32kbase!GreDeleteObject` at `0x1401aeb65`
- `win32kbase!GreDeleteObject` at `0x1401aeb74`
- `win32kbase!GreDeleteObject` at `0x1401aeb83`
- `win32kbase!GreDeleteObject` at `0x1401aeb92`
- `win32kbase!GreDeleteObject` at `0x1401aeba2`
- `win32kbase!GreDeleteObject` at `0x1401aebb2`
- `win32kbase!GreDeleteObject` at `0x1401aeed4`
- `win32kbase!GreDeleteObject` at `0x1401aeee5`
- `win32kbase!GreDeleteObject` at `0x1401aeef4`
- `win32kbase!GreDeleteObject` at `0x1401aef05`
- `win32kbase!GreDeleteObject` at `0x1401aef15`
- `win32kbase!GreDeleteObject` at `0x1401aef24`
- `win32kbase!GreDeleteObject` at `0x1401af32b`
- `win32kbase!GreDeleteObject` at `0x1401af33a`
- `win32kbase!GreDeleteObject` at `0x1401af348`
- `win32kbase!GreDeleteObject` at `0x1401af356`
- `win32kbase!GreDeleteObject` at `0x1401af364`
- `win32kbase!GreDeleteObject` at `0x1401af372`
- `WIN32K!W32GetUserSessionState` at `0x1401ae705`
- `WIN32K!W32GetUserSessionState` at `0x1401ae705`

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
0x1401ae678  mov     rax, rsp
0x1401ae67b  mov     [rax+8], rbx
0x1401ae67f  push    rbp
0x1401ae680  push    rsi
0x1401ae681  push    rdi
0x1401ae682  push    r12
0x1401ae684  push    r13
0x1401ae686  push    r14
0x1401ae688  push    r15
0x1401ae68a  lea     rbp, [rax-0C8h]
0x1401ae691  sub     rsp, 190h
0x1401ae698  movaps  xmmword ptr [rax-48h], xmm6
0x1401ae69c  mov     rax, cs:__security_cookie
0x1401ae6a3  xor     rax, rsp
0x1401ae6a6  mov     [rbp+0C0h+var_50], rax
0x1401ae6aa  mov     rax, [rbp+0C0h+arg_30]
0x1401ae6b1  xorps   xmm0, xmm0
0x1401ae6b4  mov     r12, [rbp+0C0h+arg_40]
0x1401ae6bb  xorps   xmm1, xmm1
0x1401ae6be  mov     rsi, [rbp+0C0h+arg_20]
0x1401ae6c5  xor     r14d, r14d
0x1401ae6c8  mov     rbx, [rbp+0C0h+arg_28]
0x1401ae6cf  mov     r13, rdx
0x1401ae6d2  mov     rdi, [rbp+0C0h+arg_38]
0x1401ae6d9  mov     [rbp+0C0h+var_F8], rax
0x1401ae6dd  mov     [rbp+0C0h+var_110], r12
0x1401ae6e1  movups  [rbp+0C0h+var_A0], xmm0
0x1401ae6e5  mov     [rbp+0C0h+var_FC], r14d
0x1401ae6e9  movups  [rbp+0C0h+Buf1], xmm1
0x1401ae6ed  mov     dword ptr [rbp+0C0h+var_118], r9d
0x1401ae6f1  movups  [rbp+0C0h+var_60], xmm0
0x1401ae6f5  mov     dword ptr [rbp+0C0h+var_118+4], r8d
0x1401ae6f9  movups  [rbp+0C0h+var_90], xmm1
0x1401ae6fd  movups  [rbp+0C0h+var_80], xmm0
0x1401ae701  movups  [rbp+0C0h+var_70], xmm1
0x1401ae705  call    cs:__imp_W32GetUserSessionState
0x1401ae70c  nop     dword ptr [rax+rax+00h]
0x1401ae711  lea     r8, [rbp+0C0h+var_FC]
0x1401ae715  mov     rdx, r13
0x1401ae718  mov     rcx, [rax+0DDA8h]
0x1401ae71f  mov     rcx, [rcx+28h]
0x1401ae723  call    cs:__imp_GreLockVisRgnSharedOrExclusive
0x1401ae72a  nop     dword ptr [rax+rax+00h]
0x1401ae72f  test    eax, eax
0x1401ae731  jz      loc_1401AEBBE
0x1401ae737  lea     r8d, [r14+1]
0x1401ae73b  mov     [rbp+0C0h+var_140], r14
0x1401ae73f  lea     rdx, [rbp+0C0h+var_A0]
0x1401ae743  mov     [rsp+1C0h+var_158], r14
0x1401ae748  mov     rcx, r13
0x1401ae74b  mov     [rsp+1C0h+var_160], r14
0x1401ae750  mov     r15d, r14d
0x1401ae753  mov     [rsp+1C0h+var_150], r14
0x1401ae758  mov     [rbp+0C0h+var_E0], r14
0x1401ae75c  mov     [rbp+0C0h+var_108], r14
0x1401ae760  call    cs:__imp_GreGetClipBox
0x1401ae767  nop     dword ptr [rax+rax+00h]
0x1401ae76c  mov     r14d, eax
0x1401ae76f  test    eax, eax
0x1401ae771  jz      loc_1401AF1DB
0x1401ae777  test    rsi, rsi
0x1401ae77a  lea     rcx, [rbp+0C0h+var_A0]
0x1401ae77e  cmovnz  rcx, rsi
0x1401ae782  movups  xmm1, xmmword ptr [rcx]
0x1401ae785  movaps  [rbp+0C0h+Buf1], xmm1
0x1401ae789  test    rbx, rbx
0x1401ae78c  jz      short loc_1401AE796
0x1401ae78e  movups  xmm0, xmmword ptr [rbx]
0x1401ae791  movdqu  [rbp+0C0h+var_60], xmm0
0x1401ae796  mov     esi, dword ptr [rbp+0C0h+var_118+4]
0x1401ae799  mov     eax, dword ptr [rbp+0C0h+var_118]
0x1401ae79c  mov     dword ptr [rbp+0C0h+var_E8+4], esi
0x1401ae79f  mov     dword ptr [rbp+0C0h+var_E8], eax
0x1401ae7a2  cmp     [rbp+0C0h+arg_48], r15d
0x1401ae7a9  jnz     loc_1401AF1E9
0x1401ae7af  mov     ecx, r14d
0x1401ae7b2  sub     ecx, 1
0x1401ae7b5  jz      loc_1401AF2E5
0x1401ae7bb  cmp     ecx, 2
0x1401ae7be  jz      loc_1401AF3A5
0x1401ae7c4  mov     ecx, dword ptr [rbp+0C0h+var_118]
0x1401ae7c7  movdqa  xmm0, xmm1
0x1401ae7cb  psrldq  xmm0, 8
0x1401ae7d0  movd    eax, xmm1
0x1401ae7d4  mov     [rbp+0C0h+var_130], eax
0x1401ae7d7  lea     r9d, [rsi+rax]
0x1401ae7db  movd    eax, xmm0
0x1401ae7df  mov     dword ptr [rbp+0C0h+var_90], r9d
0x1401ae7e3  movdqa  xmm0, xmm1
0x1401ae7e7  psrldq  xmm0, 4
0x1401ae7ec  movd    r12d, xmm0
0x1401ae7f1  movdqa  xmm0, xmm1
0x1401ae7f5  psrldq  xmm0, 0Ch
0x1401ae7fa  mov     [rbp+0C0h+var_120], eax
0x1401ae7fd  lea     r10d, [rsi+rax]
0x1401ae801  movd    eax, xmm0
0x1401ae805  mov     dword ptr [rbp+0C0h+var_90+8], r10d
0x1401ae809  mov     [rsp+1C0h+var_148], eax
0x1401ae80d  lea     r11d, [rcx+r12]
0x1401ae811  mov     dword ptr [rbp+0C0h+var_90+4], r11d
0x1401ae815  lea     esi, [rcx+rax]
0x1401ae818  mov     dword ptr [rbp+0C0h+var_90+0Ch], esi
0x1401ae81b  test    rbx, rbx
0x1401ae81e  jnz     loc_1401AEBC5
0x1401ae824  mov     ebx, eax
0x1401ae826  cmp     r14d, 2
0x1401ae82a  jnz     loc_1401AE980
0x1401ae830  mov     r8d, dword ptr [rbp+0C0h+var_A0+0Ch]
0x1401ae834  mov     ecx, dword ptr [rbp+0C0h+var_A0+8]
0x1401ae837  mov     edx, dword ptr [rbp+0C0h+var_A0+4]
0x1401ae83a  mov     eax, dword ptr [rbp+0C0h+var_A0]
0x1401ae83d  cmp     [rbp+0C0h+var_F8], 1
0x1401ae842  ja      loc_1401AE980
0x1401ae848  cmp     r9d, eax
0x1401ae84b  movdqa  [rbp+0C0h+Buf2], xmm1
0x1401ae850  cmovle  r9d, eax
0x1401ae854  cmp     r10d, ecx
0x1401ae857  mov     dword ptr [rbp+0C0h+var_90], r9d
0x1401ae85b  cmovge  r10d, ecx
0x1401ae85f  mov     dword ptr [rbp+0C0h+var_90+8], r10d
0x1401ae863  cmp     r9d, r10d
0x1401ae866  jge     short loc_1401AE889
0x1401ae868  cmp     r11d, edx
0x1401ae86b  cmovle  r11d, edx
0x1401ae86f  cmp     esi, r8d
0x1401ae872  mov     dword ptr [rbp+0C0h+var_90+4], r11d
0x1401ae876  cmovge  esi, r8d
0x1401ae87a  mov     [rbp+0C0h+var_100], esi
0x1401ae87d  mov     dword ptr [rbp+0C0h+var_90+0Ch], esi
0x1401ae880  cmp     r11d, esi
0x1401ae883  jl      loc_1401AEF92
0x1401ae889  xorps   xmm0, xmm0
0x1401ae88c  xorps   xmm3, xmm3
0x1401ae88f  psrldq  xmm0, 0Ch
0x1401ae894  xorps   xmm1, xmm1
0x1401ae897  movd    [rbp+0C0h+var_100], xmm0
0x1401ae89c  xorps   xmm0, xmm0
0x1401ae89f  psrldq  xmm0, 4
0x1401ae8a4  psrldq  xmm1, 8
0x1401ae8a9  movd    r11d, xmm0
0x1401ae8ae  movaps  [rbp+0C0h+var_90], xmm3
0x1401ae8b2  movd    r10d, xmm1
0x1401ae8b7  movd    r9d, xmm3
0x1401ae8bc  mov     esi, [rbp+0C0h+var_130]
0x1401ae8bf  cmp     esi, eax
0x1401ae8c1  mov     r15d, [rbp+0C0h+var_120]
0x1401ae8c5  cmovle  esi, eax
0x1401ae8c8  cmp     r15d, ecx
0x1401ae8cb  mov     [rbp+0C0h+var_130], esi
0x1401ae8ce  cmovge  r15d, ecx
0x1401ae8d2  mov     dword ptr [rbp+0C0h+Buf1], esi
0x1401ae8d5  mov     [rbp+0C0h+var_120], r15d
0x1401ae8d9  mov     dword ptr [rbp+0C0h+Buf1+8], r15d
0x1401ae8dd  cmp     esi, r15d
0x1401ae8e0  jge     short loc_1401AE908
0x1401ae8e2  cmp     r12d, edx
0x1401ae8e5  cmovle  r12d, edx
0x1401ae8e9  cmp     ebx, r8d
0x1401ae8ec  mov     dword ptr [rbp+0C0h+var_F0], r12d
0x1401ae8f0  cmovge  ebx, r8d
0x1401ae8f4  mov     dword ptr [rbp+0C0h+Buf1+4], r12d
0x1401ae8f8  mov     [rsp+1C0h+var_148], ebx
0x1401ae8fc  mov     dword ptr [rbp+0C0h+Buf1+0Ch], ebx
0x1401ae8ff  cmp     r12d, ebx
0x1401ae902  jl      loc_1401AEF9B
0x1401ae908  xorps   xmm0, xmm0
0x1401ae90b  xorps   xmm6, xmm6
0x1401ae90e  psrldq  xmm0, 0Ch
0x1401ae913  xorps   xmm1, xmm1
0x1401ae916  movd    eax, xmm0
0x1401ae91a  xor     r8d, r8d
0x1401ae91d  xorps   xmm0, xmm0
0x1401ae920  psrldq  xmm1, 8
0x1401ae925  psrldq  xmm0, 4
0x1401ae92a  movd    r12d, xmm0
0x1401ae92f  movd    r15d, xmm1
0x1401ae934  movd    esi, xmm6
0x1401ae938  mov     dword ptr [rbp+0C0h+var_F0], r12d
0x1401ae93c  movaps  [rbp+0C0h+Buf1], xmm6
0x1401ae940  mov     [rsp+1C0h+var_148], eax
0x1401ae944  mov     [rbp+0C0h+var_120], r15d
0x1401ae948  mov     [rbp+0C0h+var_130], esi
0x1401ae94b  cmp     [rbp+0C0h+var_F8], 1
0x1401ae950  jz      loc_1401AF033
0x1401ae956  mov     ecx, dword ptr [rbp+0C0h+var_118+4]
0x1401ae959  add     esi, ecx
0x1401ae95b  mov     dword ptr [rbp+0C0h+var_70], esi
0x1401ae95e  lea     ebx, [rcx+r15]
0x1401ae962  mov     ecx, dword ptr [rbp+0C0h+var_118]
0x1401ae965  mov     dword ptr [rbp+0C0h+var_70+8], ebx
0x1401ae968  lea     r15d, [rcx+r12]
0x1401ae96c  lea     r12d, [rcx+rax]
0x1401ae970  cmp     esi, r9d
0x1401ae973  jle     loc_1401AECC3
0x1401ae979  mov     ecx, esi
0x1401ae97b  jmp     loc_1401AECCD
0x1401ae980  test    r15d, r15d
0x1401ae983  jz      loc_1401AEF67
0x1401ae989  mov     r12, [rbp+0C0h+var_140]
0x1401ae98d  call    cs:__imp_CreateEmptyRgn
0x1401ae994  nop     dword ptr [rax+rax+00h]
0x1401ae999  mov     rcx, rax
0x1401ae99c  mov     [rsp+1C0h+var_150], rax
0x1401ae9a1  lea     rdx, [rbp+0C0h+Buf1]
0x1401ae9a5  mov     rsi, rax
0x1401ae9a8  call    cs:__imp_SetRectRgnIndirect
0x1401ae9af  nop     dword ptr [rax+rax+00h]
0x1401ae9b4  mov     r15d, 1
0x1401ae9ba  mov     r8, r12
0x1401ae9bd  mov     r9d, r15d
0x1401ae9c0  mov     rdx, rsi
0x1401ae9c3  mov     rcx, rsi
0x1401ae9c6  call    cs:__imp_GreCombineRgn
0x1401ae9cd  nop     dword ptr [rax+rax+00h]
0x1401ae9d2  test    eax, eax
0x1401ae9d4  jz      loc_1401AF62E
0x1401ae9da  call    cs:__imp_CreateEmptyRgn
0x1401ae9e1  nop     dword ptr [rax+rax+00h]
0x1401ae9e6  mov     rcx, rax
0x1401ae9e9  mov     [rbp+0C0h+var_E0], rax
0x1401ae9ed  lea     rdx, [rbp+0C0h+var_90]
0x1401ae9f1  mov     rbx, rax
0x1401ae9f4  call    cs:__imp_SetRectRgnIndirect
0x1401ae9fb  nop     dword ptr [rax+rax+00h]
0x1401aea00  mov     r9d, r15d
0x1401aea03  mov     r8, r12
0x1401aea06  mov     rdx, rbx
0x1401aea09  mov     rcx, rbx
0x1401aea0c  call    cs:__imp_GreCombineRgn
0x1401aea13  nop     dword ptr [rax+rax+00h]
0x1401aea18  test    eax, eax
0x1401aea1a  jz      loc_1401AF62E
0x1401aea20  mov     r12, [rbp+0C0h+var_F8]
0x1401aea24  lea     esi, [r15+3]
0x1401aea28  mov     ebx, r15d
0x1401aea2b  cmp     r12, r15
0x1401aea2e  jz      loc_1401AF086
0x1401aea34  call    cs:__imp_CreateEmptyRgn
0x1401aea3b  nop     dword ptr [rax+rax+00h]
0x1401aea40  mov     rdx, [rsp+1C0h+var_150]
0x1401aea45  lea     r9d, [r15+4]
0x1401aea49  mov     rcx, rax
0x1401aea4c  mov     [rbp+0C0h+var_108], rax
0x1401aea50  xor     r8d, r8d
0x1401aea53  mov     rbx, rax
0x1401aea56  call    cs:__imp_GreCombineRgn
0x1401aea5d  nop     dword ptr [rax+rax+00h]
0x1401aea62  test    eax, eax
0x1401aea64  jz      loc_1401AF1D1
0x1401aea6a  mov     r15d, dword ptr [rbp+0C0h+var_118+4]
0x1401aea6e  mov     rcx, rbx
0x1401aea71  mov     r8d, dword ptr [rbp+0C0h+var_118]
0x1401aea75  mov     edx, r15d
0x1401aea78  call    cs:__imp_GreOffsetRgn
0x1401aea7f  nop     dword ptr [rax+rax+00h]
0x1401aea84  mov     r8, [rbp+0C0h+var_E0]
0x1401aea88  lea     r9d, [rsi-3]
0x1401aea8c  mov     rdx, rbx
0x1401aea8f  mov     rcx, rbx
0x1401aea92  call    cs:__imp_GreCombineRgn
0x1401aea99  nop     dword ptr [rax+rax+00h]
0x1401aea9e  mov     ebx, eax
0x1401aeaa0  cmp     r12, 1
0x1401aeaa4  jbe     loc_1401AF5CD
0x1401aeaaa  call    cs:__imp_CreateEmptyRgn
0x1401aeab1  nop     dword ptr [rax+rax+00h]
0x1401aeab6  mov     [rsp+1C0h+var_160], rax
0x1401aeabb  mov     r12, rax
0x1401aeabe  test    ebx, ebx
0x1401aeac0  jz      loc_1401AF405
0x1401aeac6  cmp     ebx, 1
0x1401aeac9  jz      loc_1401AF08B
0x1401aeacf  lea     rdx, [rbp+0C0h+var_F0]
0x1401aead3  mov     [rbp+0C0h+var_F0], 0
0x1401aeadb  mov     rcx, r13
0x1401aeade  call    GetDCOrgOnScreen
0x1401aeae3  mov     rdx, [rbp+0C0h+var_F8]
0x1401aeae7  lea     r9d, [rsi+1]
0x1401aeaeb  xor     r8d, r8d
0x1401aeaee  mov     rcx, r12
0x1401aeaf1  call    cs:__imp_GreCombineRgn
0x1401aeaf8  nop     dword ptr [rax+rax+00h]
0x1401aeafd  mov     r8d, dword ptr [rbp+0C0h+var_F0+4]
0x1401aeb01  mov     rcx, r12
0x1401aeb04  mov     edx, dword ptr [rbp+0C0h+var_F0]
0x1401aeb07  neg     r8d
0x1401aeb0a  neg     edx
0x1401aeb0c  call    cs:__imp_GreOffsetRgn
0x1401aeb13  nop     dword ptr [rax+rax+00h]
0x1401aeb18  mov     rdx, [rbp+0C0h+var_108]
0x1401aeb1c  mov     r9d, esi
0x1401aeb1f  mov     rcx, rdx
0x1401aeb22  mov     r8, r12
0x1401aeb25  call    cs:__imp_GreCombineRgn
0x1401aeb2c  nop     dword ptr [rax+rax+00h]
0x1401aeb31  mov     ebx, eax
0x1401aeb33  test    eax, eax
0x1401aeb35  jnz     loc_1401AF045
0x1401aeb3b  mov     r15, r12
0x1401aeb3e  mov     rbx, [rsp+1C0h+var_158]
  ... truncated ...
```
