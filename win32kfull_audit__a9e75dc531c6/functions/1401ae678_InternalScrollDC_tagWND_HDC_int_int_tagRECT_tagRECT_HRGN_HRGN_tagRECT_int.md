# InternalScrollDC(tagWND *,HDC__ *,int,int,tagRECT *,tagRECT *,HRGN__ *,HRGN__ *,tagRECT *,int)

- ea: `0x1401ae678`
- end: `0x1401af647`
- name: `?InternalScrollDC@@YAHPEAUtagWND@@PEAUHDC__@@HHPEAUtagRECT@@2PEAUHRGN__@@32H@Z`
- size: `4047`
- prototype: `__int64 __fastcall(struct tagWND *, Gre::Base *, __int64, __int64, struct tagRECT *, struct tagRECT *, HRGN, HRGN, struct tagRECT *, int)`
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
        Gre::Base *a2,
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
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int ClipBox; // r14d
  __m128i *v20; // rcx
  __m128i v21; // xmm1
  int v22; // esi
  __int64 v23; // r9
  int v24; // r12d
  int v25; // r10d
  int v26; // eax
  int v27; // r11d
  int v28; // esi
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
  HRGN v41; // r12
  __int64 v42; // rsi
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rbx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned __int64 v50; // r12
  int v51; // ebx
  __int64 v52; // rax
  HRGN v53; // r12
  __int64 v54; // rbx
  int v56; // eax
  __int64 v57; // rdx
  int v58; // ecx
  int v59; // eax
  __int64 v60; // r8
  int v61; // eax
  BOOL v62; // ecx
  BOOL v63; // eax
  struct tagRECT *v64; // r15
  __int64 v65; // rbx
  int v66; // esi
  __int64 v67; // rax
  int v68; // ecx
  __int32 v69; // ecx
  int v70; // ecx
  __int64 v71; // [rsp+68h] [rbp-A0h]
  __int64 v72; // [rsp+70h] [rbp-98h]
  __int64 v73; // [rsp+78h] [rbp-90h]
  int v74; // [rsp+80h] [rbp-88h]
  int v75; // [rsp+80h] [rbp-88h]
  HRGN EmptyRgn; // [rsp+88h] [rbp-80h]
  int v77; // [rsp+98h] [rbp-70h]
  int v78; // [rsp+98h] [rbp-70h]
  int v79; // [rsp+A8h] [rbp-60h]
  int v80; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v81; // [rsp+B0h] [rbp-58h]
  __int64 v82; // [rsp+C0h] [rbp-48h]
  unsigned int v83; // [rsp+C8h] [rbp-40h]
  int v84; // [rsp+CCh] [rbp-3Ch] BYREF
  HRGN v85; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v86; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v87; // [rsp+E0h] [rbp-28h]
  __int64 v88; // [rsp+E8h] [rbp-20h]
  struct _POINTL v89; // [rsp+F0h] [rbp-18h] BYREF
  int v90; // [rsp+F8h] [rbp-10h]
  int v91; // [rsp+FCh] [rbp-Ch]
  __m128i Buf2; // [rsp+108h] [rbp+0h] BYREF
  __m128i Buf1; // [rsp+118h] [rbp+10h] BYREF
  __int128 v94; // [rsp+128h] [rbp+20h] BYREF
  __int128 v95; // [rsp+138h] [rbp+30h] BYREF
  struct tagRECT v96; // [rsp+148h] [rbp+40h] BYREF
  __int128 v97; // [rsp+158h] [rbp+50h] BYREF
  __int128 v98; // [rsp+168h] [rbp+60h] BYREF

  v10 = a9;
  v12 = a8;
  v85 = a7;
  v94 = 0;
  v84 = 0;
  Buf1 = 0;
  v81 = __PAIR64__(a3, a4);
  v98 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3, a4);
  if ( !(unsigned int)GreLockVisRgnSharedOrExclusive(
                        *(_QWORD *)(*(_QWORD *)(UserSessionState + 56744) + 40LL),
                        a2,
                        &v84) )
    return 0;
  EmptyRgn = 0;
  v72 = 0;
  v71 = 0;
  v14 = 0;
  v73 = 0;
  v88 = 0;
  v82 = 0;
  ClipBox = GreGetClipBox(a2, &v94, 1);
  if ( !ClipBox )
  {
    v41 = 0;
    goto LABEL_152;
  }
  v20 = (__m128i *)&v94;
  if ( a5 )
    v20 = (__m128i *)a5;
  v21 = *v20;
  Buf1 = *v20;
  if ( a6 )
    v98 = (__int128)*a6;
  v22 = HIDWORD(v81);
  v87 = v81;
  if ( a10 )
  {
    v66 = 0;
    GreLPtoDP((HDC)a2, (struct _POINTL *)&v94);
    GreLPtoDP((HDC)a2, (struct _POINTL *)&Buf1);
    if ( (GreGetLayout((HDC)a2) & 1) != 0 )
    {
      v68 = v94;
      v66 = 1;
      LODWORD(v94) = DWORD2(v94);
      DWORD2(v94) = v68;
      v69 = Buf1.m128i_i32[0];
      Buf1.m128i_i32[0] = Buf1.m128i_i32[2];
      Buf1.m128i_i32[2] = v69;
    }
    if ( a6 )
    {
      GreLPtoDP((HDC)a2, (struct _POINTL *)&v98);
      if ( v66 )
      {
        v70 = v98;
        LODWORD(v98) = DWORD2(v98);
        DWORD2(v98) = v70;
      }
    }
    v90 = HIDWORD(v81);
    v91 = v81;
    v89 = 0;
    GreLPtoDP((HDC)a2, &v89);
    v22 = v90 - v89.x;
    v21 = Buf1;
    LODWORD(v81) = v91 - v89.y;
    HIDWORD(v81) = v90 - v89.x;
  }
  v16 = ClipBox - 1;
  if ( ClipBox == 1 )
  {
    v54 = 0;
    goto LABEL_173;
  }
  if ( ClipBox == 3 )
  {
    EmptyRgn = (HRGN)CreateEmptyRgn(v16, v15, v17, v18);
    v41 = EmptyRgn;
    if ( (unsigned int)GetTrueClipRgn((HDC)a2, EmptyRgn) )
    {
      v21 = Buf1;
      LODWORD(v14) = 1;
      goto LABEL_10;
    }
LABEL_152:
    v54 = 0;
LABEL_153:
    v42 = 0;
    goto LABEL_53;
  }
LABEL_10:
  v16 = (unsigned int)v81;
  v77 = _mm_cvtsi128_si32(v21);
  v23 = (unsigned int)(v22 + v77);
  LODWORD(v95) = v22 + v77;
  v24 = _mm_cvtsi128_si32(_mm_srli_si128(v21, 4));
  v79 = _mm_cvtsi128_si32(_mm_srli_si128(v21, 8));
  v25 = v22 + v79;
  v26 = _mm_cvtsi128_si32(_mm_srli_si128(v21, 12));
  DWORD2(v95) = v22 + v79;
  v74 = v26;
  v27 = v81 + v24;
  DWORD1(v95) = v81 + v24;
  v28 = v81 + v26;
  HIDWORD(v95) = v81 + v26;
  if ( !a6 )
  {
    v29 = v26;
LABEL_12:
    if ( ClipBox != 2 )
      goto LABEL_40;
    v17 = HIDWORD(v94);
    v16 = DWORD2(v94);
    v15 = DWORD1(v94);
    v30 = v94;
LABEL_14:
    if ( (unsigned __int64)v85 <= 1 )
    {
      Buf2 = v21;
      if ( (int)v23 <= v30 )
        v23 = (unsigned int)v30;
      LODWORD(v95) = v23;
      if ( v25 >= (int)v16 )
        v25 = v16;
      DWORD2(v95) = v25;
      if ( (int)v23 >= v25 )
        goto LABEL_25;
      if ( v27 <= (int)v15 )
        v27 = v15;
      DWORD1(v95) = v27;
      if ( v28 >= (int)v17 )
        v28 = v17;
      v83 = v28;
      HIDWORD(v95) = v28;
      if ( v27 < v28 )
      {
        v31 = (struct tagRECT)v95;
      }
      else
      {
LABEL_25:
        v31 = 0;
        v83 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
        v27 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
        v95 = 0;
        v25 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
        v23 = (unsigned int)_mm_cvtsi128_si32((__m128i)0LL);
      }
      v32 = v77;
      v33 = v79;
      if ( v77 <= v30 )
        v32 = v30;
      v78 = v32;
      if ( v79 >= (int)v16 )
        v33 = v16;
      Buf1.m128i_i32[0] = v32;
      v80 = v33;
      Buf1.m128i_i32[2] = v33;
      if ( v32 >= v33 )
        goto LABEL_36;
      if ( v24 <= (int)v15 )
        v24 = v15;
      LODWORD(v86) = v24;
      if ( v29 >= (int)v17 )
        v29 = v17;
      Buf1.m128i_i32[1] = v24;
      v75 = v29;
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
        LODWORD(v86) = v24;
        Buf1 = 0;
        v75 = v35;
        v80 = v33;
        v78 = v32;
      }
      if ( v85 == (HRGN)1 )
      {
        v57 = v83;
      }
      else
      {
        v37 = HIDWORD(v81) + v32;
        LODWORD(v97) = v37;
        v38 = HIDWORD(v81) + v33;
        DWORD2(v97) = HIDWORD(v81) + v33;
        v39 = v81 + v24;
        v40 = v81 + v35;
        if ( v37 <= (int)v23 )
        {
          v37 = v23;
          LODWORD(v97) = v23;
          v16 = (unsigned int)v23;
        }
        else
        {
          v16 = (unsigned int)v37;
        }
        if ( v38 < v25 )
        {
          v56 = v38;
        }
        else
        {
          v38 = v25;
          v56 = v25;
          DWORD2(v97) = v25;
        }
        v57 = v83;
        if ( (int)v16 < v56 )
        {
          if ( v39 <= v27 )
            v39 = v27;
          DWORD1(v97) = v39;
          if ( v40 >= (int)v83 )
            v40 = v83;
          HIDWORD(v97) = v40;
          if ( v39 < v40 )
            goto LABEL_77;
        }
      }
      v40 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
      v39 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
      v97 = 0;
      v38 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
      v37 = _mm_cvtsi128_si32((__m128i)0LL);
LABEL_77:
      if ( !v36 )
      {
        v96 = v31;
        goto LABEL_110;
      }
      v58 = v23;
      v59 = v25;
      if ( v78 > (int)v23 )
        v58 = v78;
      v96.left = v58;
      if ( v80 < v25 )
        v59 = v80;
      v96.right = v59;
      if ( v58 >= v59 )
        goto LABEL_88;
      v60 = (unsigned int)v86;
      v16 = (unsigned int)v27;
      v61 = v57;
      if ( (int)v86 > v27 )
        v16 = (unsigned int)v86;
      v96.top = v16;
      if ( v75 < (int)v57 )
        v61 = v75;
      v96.bottom = v61;
      if ( (int)v16 < v61 )
      {
        if ( !HIDWORD(v81) || !(_DWORD)v81 )
        {
          v62 = v78 >= v80 || (int)v86 >= v75;
          v63 = (int)v23 >= v25 || v27 >= (int)v57;
          if ( v62 )
          {
            if ( v63 )
              v96 = 0;
            else
              v96 = v31;
          }
          else if ( v63 )
          {
            v96 = v34;
          }
          else
          {
            if ( v78 < (int)v23 )
              LODWORD(v23) = v78;
            v96.left = v23;
            if ( (int)v86 < v27 )
              v27 = v86;
            v96.top = v27;
            if ( v80 > v25 )
              v25 = v80;
            v96.right = v25;
            if ( v75 > (int)v57 )
              LODWORD(v57) = v75;
            v96.bottom = v57;
          }
          SubtractRect(&v96, &v96, &v97);
          v31 = v96;
          goto LABEL_110;
        }
      }
      else
      {
LABEL_88:
        v96 = 0;
        if ( !memcmp(&Buf1, &Buf2, 0x10u) )
        {
          v31 = v34;
          v96 = v34;
LABEL_110:
          if ( a9 )
            *a9 = v31;
          if ( !a8 )
            goto LABEL_115;
          if ( (unsigned int)SetRectRgnIndirect(a8, &v96) )
          {
            v40 = HIDWORD(v97);
            v38 = DWORD2(v97);
            v39 = DWORD1(v97);
            v37 = v97;
LABEL_115:
            if ( v96.left >= v96.right || (ClipBox = 2, v96.top >= v96.bottom) )
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
              GreDPtoLP((HDC)a2);
              v40 = HIDWORD(v97);
              v38 = DWORD2(v97);
              v39 = DWORD1(v97);
              v37 = v97;
            }
            GreBitBltInternal(
              a2,
              v37,
              v39,
              v38 - v37,
              v40 - v39,
              (__int64)a2,
              v37 - HIDWORD(v87),
              v39 - v87,
              0xCC0020u,
              0,
              0);
          }
          v53 = (HRGN)v71;
          v64 = a9;
          goto LABEL_119;
        }
        v67 = CreateEmptyRgn(v16, v57, v60, v23);
        v71 = v67;
        v14 = v67;
        if ( !v67 )
        {
LABEL_198:
          v40 = HIDWORD(v97);
          v38 = DWORD2(v97);
          v39 = DWORD1(v97);
          v37 = v97;
          goto LABEL_117;
        }
        v12 = (HRGN)v67;
      }
      v54 = v72;
      if ( !v72 )
      {
        v54 = CreateEmptyRgn(v16, v57, v60, v23);
        v72 = v54;
      }
      SetRectRgnIndirect(v54, &Buf1);
      SetRectRgnIndirect(v12, &v95);
      if ( (unsigned int)GreCombineRgn(v12, v12, v54, 2) )
      {
        SetRectRgnIndirect(v54, &v97);
        ClipBox = GreCombineRgn(v12, v12, v54, 4);
        if ( ClipBox )
        {
          if ( !a9 || (unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_198;
        }
      }
LABEL_52:
      v41 = EmptyRgn;
      v42 = v73;
LABEL_53:
      if ( v84 )
        GreUnlockVisRgnShared();
      else
        GreUnlockVisRgn(v16);
      GreDeleteObject(v41);
      GreDeleteObject(v54);
      GreDeleteObject(v14);
      GreDeleteObject(v42);
      GreDeleteObject(v88);
      GreDeleteObject(v82);
      return 0;
    }
LABEL_40:
    if ( (_DWORD)v14 )
    {
      v41 = EmptyRgn;
    }
    else
    {
      EmptyRgn = (HRGN)CreateEmptyRgn(v16, v15, v17, v23);
      v41 = EmptyRgn;
      if ( !(unsigned int)GetTrueClipRgn((HDC)a2, EmptyRgn) )
        goto LABEL_190;
    }
    v73 = CreateEmptyRgn(v16, v15, v17, v23);
    v42 = v73;
    SetRectRgnIndirect(v73, &Buf1);
    if ( !(unsigned int)GreCombineRgn(v42, v42, v41, 1)
      || (v88 = CreateEmptyRgn(v16, v43, v44, v45),
          v46 = v88,
          SetRectRgnIndirect(v88, &v95),
          !(unsigned int)GreCombineRgn(v46, v46, v41, 1)) )
    {
      v14 = 0;
      v54 = v72;
      goto LABEL_53;
    }
    v50 = (unsigned __int64)v85;
    v51 = 1;
    if ( v85 != (HRGN)1 )
    {
      v82 = CreateEmptyRgn(v16, v47, v48, v49);
      if ( !(unsigned int)GreCombineRgn(v82, v73, 0, 5) )
      {
LABEL_150:
        v14 = v71;
        goto LABEL_51;
      }
      GreOffsetRgn(v82, HIDWORD(v81), (unsigned int)v81);
      v51 = GreCombineRgn(v82, v82, v88, 1);
      if ( v50 <= 1 )
      {
        v14 = 0;
      }
      else
      {
        v52 = CreateEmptyRgn(v16, v47, v48, v49);
        v71 = v52;
        v53 = (HRGN)v52;
        if ( !v51 )
        {
          v14 = v52;
          goto LABEL_51;
        }
        if ( v51 == 1 )
          goto LABEL_140;
        v86 = 0;
        GetDCOrgOnScreen((__int64)a2, &v86);
        GreCombineRgn(v53, v85, 0, 5);
        GreOffsetRgn(v53, (unsigned int)-(int)v86, (unsigned int)-HIDWORD(v86));
        v51 = GreCombineRgn(v82, v82, v53, 4);
        if ( !v51 )
        {
          v14 = (__int64)v53;
LABEL_51:
          v54 = v72;
          goto LABEL_52;
        }
        if ( v51 == 1 )
        {
LABEL_140:
          v64 = a9;
          if ( !a8 )
          {
            if ( !a9 )
              goto LABEL_145;
            if ( !v53 )
            {
              v71 = CreateEmptyRgn(v16, v47, v48, v49);
              v53 = (HRGN)v71;
              if ( !v71 )
                goto LABEL_145;
            }
            v12 = v53;
          }
          ClipBox = GreCombineRgn(v12, v88, v73, 2);
          if ( !ClipBox )
            goto LABEL_150;
          if ( v51 != 1 )
            ClipBox = GreCombineRgn(v12, v12, v82, 4);
          if ( a9 && !(unsigned int)GreGetRgnBox(v12, a9) )
            goto LABEL_150;
LABEL_145:
          if ( v51 != 1 )
          {
            v85 = 0;
            GreGetDCOrg(a2, &v85);
            v65 = v82;
            GreOffsetRgn(v82, (unsigned int)v85, HIDWORD(v85));
            GreSelectVisRgnShared(a2, v82, 4);
            if ( a10 )
              GreDPtoLP((HDC)a2);
            GreBitBltInternal(
              a2,
              v95,
              SDWORD1(v95),
              DWORD2(v95) - v95,
              HIDWORD(v95) - DWORD1(v95),
              (__int64)a2,
              v95 - HIDWORD(v87),
              DWORD1(v95) - v87,
              0xCC0020u,
              0,
              0);
            GreSelectVisRgnShared(a2, v82, 4);
            goto LABEL_120;
          }
LABEL_119:
          v65 = v82;
LABEL_120:
          if ( a10 && v64 )
            GreDPtoLP((HDC)a2);
          if ( v84 )
            GreUnlockVisRgnShared();
          else
            GreUnlockVisRgn(v16);
          GreDeleteObject(EmptyRgn);
          GreDeleteObject(v72);
          GreDeleteObject(v53);
          GreDeleteObject(v73);
          GreDeleteObject(v88);
          GreDeleteObject(v65);
          return ClipBox;
        }
        v14 = (__int64)v53;
        GreOffsetRgn(v53, HIDWORD(v81), (unsigned int)v81);
        v51 = GreCombineRgn(v82, v82, v53, 4);
      }
      if ( !v51 )
        goto LABEL_51;
    }
    v53 = (HRGN)v71;
    goto LABEL_140;
  }
  if ( (unsigned __int64)v85 <= 1 && ClipBox == 2 )
  {
    v30 = v94;
    v16 = DWORD2(v94);
    if ( (int)v94 <= (int)v98 )
      v30 = v98;
    LODWORD(v94) = v30;
    if ( SDWORD2(v94) >= SDWORD2(v98) )
      v16 = DWORD2(v98);
    DWORD2(v94) = v16;
    if ( v30 < (int)v16 )
    {
      v15 = DWORD1(v94);
      v17 = HIDWORD(v94);
      if ( SDWORD1(v94) <= SDWORD1(v98) )
        v15 = DWORD1(v98);
      DWORD1(v94) = v15;
      if ( SHIDWORD(v94) >= SHIDWORD(v98) )
        v17 = HIDWORD(v98);
      HIDWORD(v94) = v17;
      if ( (int)v15 < (int)v17 )
      {
        v29 = v74;
        goto LABEL_14;
      }
    }
    v10 = a9;
    v54 = 0;
    v94 = 0;
    goto LABEL_173;
  }
  if ( (_DWORD)v14 )
  {
    v41 = EmptyRgn;
    goto LABEL_62;
  }
  EmptyRgn = (HRGN)CreateEmptyRgn((unsigned int)v81, v15, v17, v23);
  v41 = EmptyRgn;
  if ( !(unsigned int)GetTrueClipRgn((HDC)a2, EmptyRgn) )
  {
    v14 = 0;
    goto LABEL_152;
  }
  LODWORD(v14) = 1;
LABEL_62:
  v72 = CreateEmptyRgn(v16, v15, v17, v23);
  v54 = v72;
  SetRectRgnIndirect(v72, &v98);
  ClipBox = GreCombineRgn(v41, v72, v41, 1);
  if ( !ClipBox )
    goto LABEL_219;
  v15 = ClipBox - 1;
  if ( ClipBox != 1 )
  {
    if ( ClipBox != 2 )
    {
      v29 = Buf1.m128i_i32[3];
      v24 = Buf1.m128i_i32[1];
      v21 = Buf1;
      v28 = HIDWORD(v95);
      v25 = DWORD2(v95);
      v27 = DWORD1(v95);
      v23 = (unsigned int)v95;
      v79 = Buf1.m128i_i32[2];
      v77 = Buf1.m128i_i32[0];
      goto LABEL_12;
    }
    if ( (unsigned int)GreGetRgnBox(v41, &v94) )
    {
      v17 = HIDWORD(v94);
      v16 = DWORD2(v94);
      v15 = DWORD1(v94);
      v30 = v94;
      v29 = Buf1.m128i_i32[3];
      v24 = Buf1.m128i_i32[1];
      v21 = Buf1;
      v28 = HIDWORD(v95);
      v25 = DWORD2(v95);
      v27 = DWORD1(v95);
      v79 = Buf1.m128i_i32[2];
      v77 = Buf1.m128i_i32[0];
      v23 = (unsigned int)v95;
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
    v54 = v72;
    goto LABEL_153;
  }
  if ( v10 )
    *v10 = 0;
  if ( v84 )
    GreUnlockVisRgnShared();
  else
    GreUnlockVisRgn(v16);
  GreDeleteObject(EmptyRgn);
  GreDeleteObject(v54);
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
