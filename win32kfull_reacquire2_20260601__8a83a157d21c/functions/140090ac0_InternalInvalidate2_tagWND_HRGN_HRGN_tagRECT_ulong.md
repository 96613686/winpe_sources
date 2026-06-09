# InternalInvalidate2(tagWND *,HRGN__ *,HRGN__ *,tagRECT *,ulong)

- ea: `0x140090ac0`
- end: `0x140091441`
- name: `?InternalInvalidate2@@YAHPEAUtagWND@@PEAUHRGN__@@1PEAUtagRECT@@K@Z`
- size: `2433`
- prototype: `__int64 __fastcall(struct tagWND *, HRGN, HRGN, struct tagRECT *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14008f430`
- `0x140090ac0`
- `0x1401d9670`

## callees

- `0x14008db30`
- `0x1400909e4`
- `0x140090ac0`
- `0x140091448`
- `0x1400916d4`
- `0x14009211c`
- `0x1400e52f0`
- `0x1401e9ea0`
- `0x140342fa0`

## import_xrefs

- `win32kbase!CreateEmptyRgnPublic` at `0x140090e7d`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400913ec`
- `win32kbase!CreateEmptyRgnPublic` at `0x140090e7d`
- `win32kbase!CreateEmptyRgnPublic` at `0x1400913ec`
- `win32kbase!SetRectRgnIndirect` at `0x140090dab`
- `win32kbase!SetRectRgnIndirect` at `0x140091100`
- `win32kbase!SetRectRgnIndirect` at `0x140091360`
- `win32kbase!SetRectRgnIndirect` at `0x140091420`
- `win32kbase!SetRectRgnIndirect` at `0x140090dab`
- `win32kbase!SetRectRgnIndirect` at `0x140091100`
- `win32kbase!SetRectRgnIndirect` at `0x140091360`
- `win32kbase!SetRectRgnIndirect` at `0x140091420`
- `win32kbase!GreCombineRgn` at `0x140090e12`
- `win32kbase!GreCombineRgn` at `0x140090ea9`
- `win32kbase!GreCombineRgn` at `0x140090f6b`
- `win32kbase!GreCombineRgn` at `0x140091135`
- `win32kbase!GreCombineRgn` at `0x1400911bd`
- `win32kbase!GreCombineRgn` at `0x140091262`
- `win32kbase!GreCombineRgn` at `0x1400912bf`
- `win32kbase!GreCombineRgn` at `0x140091391`
- `win32kbase!GreCombineRgn` at `0x1400913c0`
- `win32kbase!GreCombineRgn` at `0x140090e12`
- `win32kbase!GreCombineRgn` at `0x140090ea9`
- `win32kbase!GreCombineRgn` at `0x140090f6b`
- `win32kbase!GreCombineRgn` at `0x140091135`
- `win32kbase!GreCombineRgn` at `0x1400911bd`
- `win32kbase!GreCombineRgn` at `0x140091262`
- `win32kbase!GreCombineRgn` at `0x1400912bf`
- `win32kbase!GreCombineRgn` at `0x140091391`
- `win32kbase!GreCombineRgn` at `0x1400913c0`
- `win32kbase!IsWindowDesktopComposed` at `0x140090fbb`
- `win32kbase!IsWindowDesktopComposed` at `0x140090fbb`
- `win32kbase!GreDeleteObject` at `0x140090f18`
- `win32kbase!GreDeleteObject` at `0x140090f9b`
- `win32kbase!GreDeleteObject` at `0x140091095`
- `win32kbase!GreDeleteObject` at `0x1400911d6`
- `win32kbase!GreDeleteObject` at `0x140091275`
- `win32kbase!GreDeleteObject` at `0x1400912cf`
- `win32kbase!GreDeleteObject` at `0x1400912df`
- `win32kbase!GreDeleteObject` at `0x140090f18`
- `win32kbase!GreDeleteObject` at `0x140090f9b`
- `win32kbase!GreDeleteObject` at `0x140091095`
- `win32kbase!GreDeleteObject` at `0x1400911d6`
- `win32kbase!GreDeleteObject` at `0x140091275`
- `win32kbase!GreDeleteObject` at `0x1400912cf`
- `win32kbase!GreDeleteObject` at `0x1400912df`
- `WIN32K!W32GetUserSessionState` at `0x140090d94`
- `WIN32K!W32GetUserSessionState` at `0x140090de0`
- `WIN32K!W32GetUserSessionState` at `0x140090df3`
- `WIN32K!W32GetUserSessionState` at `0x1400910e9`
- `WIN32K!W32GetUserSessionState` at `0x140091116`
- `WIN32K!W32GetUserSessionState` at `0x14009118b`
- `WIN32K!W32GetUserSessionState` at `0x14009119e`
- `WIN32K!W32GetUserSessionState` at `0x140091230`
- `WIN32K!W32GetUserSessionState` at `0x140091243`
- `WIN32K!W32GetUserSessionState` at `0x14009130f`
- `WIN32K!W32GetUserSessionState` at `0x140091349`
- `WIN32K!W32GetUserSessionState` at `0x140091372`
- `WIN32K!W32GetUserSessionState` at `0x1400913a1`
- `WIN32K!W32GetUserSessionState` at `0x140091409`
- `WIN32K!W32GetUserSessionState` at `0x140090d94`
- `WIN32K!W32GetUserSessionState` at `0x140090de0`
- `WIN32K!W32GetUserSessionState` at `0x140090df3`
- `WIN32K!W32GetUserSessionState` at `0x1400910e9`
- `WIN32K!W32GetUserSessionState` at `0x140091116`
- `WIN32K!W32GetUserSessionState` at `0x14009118b`
- `WIN32K!W32GetUserSessionState` at `0x14009119e`
- `WIN32K!W32GetUserSessionState` at `0x140091230`
- `WIN32K!W32GetUserSessionState` at `0x140091243`
- `WIN32K!W32GetUserSessionState` at `0x14009130f`
- `WIN32K!W32GetUserSessionState` at `0x140091349`
- `WIN32K!W32GetUserSessionState` at `0x140091372`
- `WIN32K!W32GetUserSessionState` at `0x1400913a1`
- `WIN32K!W32GetUserSessionState` at `0x140091409`

## pseudocode

```c
_BOOL8 __fastcall InternalInvalidate2(struct tagWND *a1, HRGN a2, HRGN a3, struct tagRECT *a4, unsigned int a5)
{
  unsigned int v5; // esi
  HRGN v7; // r13
  __int64 v8; // rdx
  struct tagWND *v9; // r14
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  bool v14; // zf
  LONG left; // edx
  LONG right; // r8d
  LONG top; // edx
  LONG bottom; // r8d
  int v19; // eax
  __int64 v20; // rdi
  __int64 v22; // r9
  unsigned __int8 v23; // dl
  int v24; // r10d
  LONG v25; // ecx
  LONG v26; // eax
  LONG v27; // ecx
  LONG v28; // eax
  __int64 EmptyRgnPublic; // r15
  _BYTE *v30; // rcx
  unsigned int v31; // eax
  __int64 UserSessionState; // rax
  struct tagWND *v33; // rcx
  struct tagWND *v34; // rdi
  HRGN v35; // r13
  __int64 v36; // rbx
  __int64 v37; // rcx
  __int64 v38; // rax
  HRGN v39; // rdx
  int v40; // ebx
  int v41; // eax
  HRGN v42; // r13
  HRGN v43; // r13
  int v44; // ebx
  HRGN v45; // rcx
  __int64 v46; // rax
  int v47; // ecx
  int v48; // edx
  _BYTE *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  struct tagWND *v52; // rcx
  __int64 v53; // rax
  unsigned int v54; // eax
  bool v55; // cf
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rcx
  __int64 v59; // rax
  HRGN v60; // rdi
  int v61; // eax
  int v62; // esi
  __int64 v63; // rbx
  __int64 v64; // rcx
  __int64 v65; // rax
  unsigned int v66; // eax
  int v67; // eax
  __int64 v68; // rax
  __int64 Prop; // rax
  __int64 v70; // rcx
  __int64 v71; // rdi
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  unsigned int v78; // [rsp+30h] [rbp-51h]
  unsigned int v79; // [rsp+30h] [rbp-51h]
  struct tagRECT v80; // [rsp+38h] [rbp-49h] BYREF
  HRGN v81; // [rsp+48h] [rbp-39h] BYREF
  int v82; // [rsp+50h] [rbp-31h]
  HRGN v83; // [rsp+58h] [rbp-29h]
  HRGN v84; // [rsp+60h] [rbp-21h] BYREF
  int v85; // [rsp+68h] [rbp-19h]
  int v86; // [rsp+6Ch] [rbp-15h]
  HRGN v87; // [rsp+70h] [rbp-11h]
  struct tagRECT v88; // [rsp+78h] [rbp-9h] BYREF

  v5 = a5 | 0x8000;
  v83 = a3;
  v88 = 0;
  v7 = a3;
  v8 = *((_QWORD *)a1 + 5);
  v9 = a1;
  if ( !*(_QWORD *)(v8 + 168) )
    v5 = a5;
  v88 = *(struct tagRECT *)(v8 + 88);
  if ( (v5 & 1) == 0 )
    goto LABEL_29;
  if ( (((v5 & 0x10000) == 0) & (*(_BYTE *)(v8 + 26) >> 3)) != 0 && (*((_DWORD *)a1 + 95) & 0x4000) == 0 )
  {
    v10 = *((_QWORD *)a1 + 13);
    if ( v10 )
    {
      v11 = *((_QWORD *)a1 + 3);
      if ( v11 )
      {
        v12 = *(_QWORD *)(v11 + 8);
        if ( v12 )
        {
          if ( v10 == *(_QWORD *)(v12 + 24) )
            return 1;
        }
      }
    }
    if ( (*(_DWORD *)(v8 + 232) & 2) == 0 )
      return 1;
  }
  *((_DWORD *)v9 + 95) &= ~0x4000u;
  v13 = *(unsigned __int8 *)(v8 + 27);
  LOBYTE(v13) = ~(*(_BYTE *)(v8 + 26) >> 3) & ~((unsigned __int8)v13 >> 5);
  if ( (v13 & 1) != 0 )
  {
    v14 = *((_QWORD *)v9 + 13) == 0;
    v80 = *a4;
    if ( !v14 )
      PhysicalToLogicalInPlaceRect(v9, &v80);
    left = v88.left;
    right = v88.right;
    if ( v88.left <= v80.left )
      left = v80.left;
    v88.left = left;
    if ( v88.right >= v80.right )
      right = v80.right;
    v88.right = right;
    if ( left < right )
    {
      top = v88.top;
      bottom = v88.bottom;
      if ( v88.top <= v80.top )
        top = v80.top;
      v88.top = top;
      if ( v88.bottom >= v80.bottom )
        bottom = v80.bottom;
      v88.bottom = bottom;
      if ( top < bottom )
      {
        v19 = 0;
        goto LABEL_26;
      }
    }
    v88.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v88.top = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v88.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v88.left = 0;
  }
  else if ( v88.left < v88.right && v88.top < v88.bottom )
  {
    v19 = 0;
    goto LABEL_26;
  }
  v19 = 1;
LABEL_26:
  if ( v19 )
    return 1;
  if ( (unsigned __int64)a2 <= 1 )
    goto LABEL_28;
  v31 = SmartRectInRegion(a2, &v88);
  if ( v31 == 1 )
  {
    if ( (v5 & 0x8000) != 0 )
    {
      UserSessionState = W32GetUserSessionState(v13);
      SetRectRgnIndirect(*(_QWORD *)(UserSessionState + 63136), &v88);
      v33 = 0;
      v34 = v9;
      do
      {
        v35 = *(HRGN *)(*((_QWORD *)v34 + 5) + 168LL);
        v81 = v35;
        if ( v35 )
        {
          if ( v33 )
          {
            v66 = PhysicalToLogicalInPlaceRgn(v33, &v81);
            v35 = v81;
            v79 = v66;
          }
          else
          {
            v79 = 0;
          }
          v57 = *(_QWORD *)(W32GetUserSessionState(v33) + 63136);
          v59 = W32GetUserSessionState(v58);
          GreCombineRgn(*(_QWORD *)(v59 + 63136), v57, v35, 1);
          if ( v79 )
            GreDeleteObject(v35);
        }
        v33 = v34;
        v34 = (struct tagWND *)*((_QWORD *)v34 + 13);
      }
      while ( v34 );
      v36 = *(_QWORD *)(W32GetUserSessionState(v33) + 63136);
      v38 = W32GetUserSessionState(v37);
      if ( (unsigned int)GreCombineRgn(*(_QWORD *)(v38 + 63136), v36, a2, 1) == 1 )
        return 1;
      v7 = v83;
    }
    goto LABEL_28;
  }
  if ( !v31 )
    return 1;
  v54 = v31 - 2;
  if ( v54 )
  {
    if ( v54 == 1 )
      return 0;
  }
  else
  {
    v55 = (GetAppCompatFlags(*((_QWORD *)v9 + 2)) & 0x10000) != 0;
    v56 = 1;
    if ( v55 )
      v56 = (__int64)a2;
    a2 = (HRGN)v56;
  }
LABEL_28:
  if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 27LL) & 0x10) == 0
    || (v68 = W32GetUserSessionState(v13), Prop = GetProp(v9, *(unsigned __int16 *)(v68 + 41198), 1), (v71 = Prop) == 0) )
  {
LABEL_29:
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 31LL) & 2) == 0 )
      InternalInvalidate3(v9);
    v20 = *((_QWORD *)v9 + 14);
    if ( v20 )
    {
      v22 = *((_QWORD *)v9 + 5);
      v23 = *(_BYTE *)(v22 + 31);
      if ( (((v5 & 0x40) == 0) & (unsigned __int8)~(v23 >> 5)) != 0 && ((v5 & 0x80u) != 0 || (v23 & 2) == 0) )
      {
        v24 = v5 | 0x2000;
        v80 = 0;
        v25 = *(_DWORD *)(v22 + 104);
        if ( (v5 & 1) != 0 )
          v24 = v5 | 0x2404;
        v78 = v24;
        if ( v88.left > v25 )
          v25 = v88.left;
        v80.left = v25;
        v26 = *(_DWORD *)(v22 + 112);
        if ( v88.right < v26 )
          v26 = v88.right;
        v80.right = v26;
        if ( v25 < v26 )
        {
          v27 = *(_DWORD *)(v22 + 108);
          if ( v88.top > v27 )
            v27 = v88.top;
          v80.top = v27;
          v28 = *(_DWORD *)(v22 + 116);
          if ( v88.bottom < v28 )
            v28 = v88.bottom;
          v80.bottom = v28;
          if ( v27 < v28 )
          {
            EmptyRgnPublic = 0;
            while ( v20 )
            {
              v30 = *(_BYTE **)(v20 + 40);
              if ( (v30[31] & 0x10) != 0 )
              {
                if ( (v30[27] & 0x20) != 0 || (v30[26] & 8) != 0 )
                {
                  v82 = 1;
                  if ( EmptyRgnPublic || (EmptyRgnPublic = CreateEmptyRgnPublic()) != 0 )
                  {
                    v39 = v7;
                    if ( a2 != (HRGN)1 )
                      v39 = a2;
                    GreCombineRgn(EmptyRgnPublic, v39, 0, 5);
                  }
                }
                else
                {
                  v82 = 0;
                }
                v84 = a2;
                v81 = v7;
                v86 = PhysicalToLogicalInPlaceRect(v20, &v80);
                v40 = PhysicalToLogicalInPlaceRgn(v20, &v84);
                v41 = PhysicalToLogicalInPlaceRgn(v20, &v81);
                v42 = v84;
                v85 = v41;
                v87 = v81;
                LODWORD(v84) = InternalInvalidate2((struct tagWND *)v20, v84, v81, &v80, v78);
                if ( v40 )
                  GreDeleteObject(v42);
                if ( v85 )
                {
                  v67 = LogicalToPhysicalInPlaceRgnWorker(v20, &v81, 0);
                  v43 = v83;
                  if ( v67 )
                  {
                    GreCombineRgn(v83, v81, 0, 5);
                    GreDeleteObject(v81);
                  }
                  GreDeleteObject(v87);
                }
                else
                {
                  v43 = v83;
                }
                if ( v86
                  && (*(_DWORD *)(*(_QWORD *)(v20 + 40) + 232LL) & 2) != 0
                  && *(_QWORD *)(v20 + 216)
                  && (unsigned int)IsWindowDesktopComposed(v20) )
                {
                  v80.left = (int)(float)((float)v80.left * **(float **)(v20 + 216));
                  v80.top = (int)(float)((float)v80.top * *(float *)(*(_QWORD *)(v20 + 216) + 20LL));
                  v80.right = (int)(float)((float)v80.right * **(float **)(v20 + 216));
                  v80.bottom = (int)(float)((float)v80.bottom * *(float *)(*(_QWORD *)(v20 + 216) + 20LL));
                  v46 = *(_QWORD *)(v20 + 216);
                  v47 = (int)*(float *)(v46 + 48);
                  v48 = (int)*(float *)(v46 + 52);
                  v80.left += v47;
                  v80.right += v47;
                  v80.bottom += v48;
                  v80.top += v48;
                }
                v44 = v82;
                if ( v82 && EmptyRgnPublic )
                {
                  v45 = v43;
                  if ( a2 != (HRGN)1 )
                    v45 = a2;
                  GreCombineRgn(v45, EmptyRgnPublic, 0, 5);
                }
                if ( !(_DWORD)v84 && !v44 )
                {
                  if ( (v5 & 0x12) == 0 )
                  {
                    if ( EmptyRgnPublic )
                      GreDeleteObject(EmptyRgnPublic);
                    return 0;
                  }
                  v5 &= 0xFFFFF3D2;
                  v78 &= 0xFFFFD3D2;
                }
              }
              v20 = *(_QWORD *)(v20 + 88);
              v7 = v83;
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
    v49 = (_BYTE *)*((_QWORD *)v9 + 5);
    if ( (v49[24] & 0x20) != 0 )
      return 1;
    if ( (v49[26] & 8) != 0 )
      return 1;
    if ( (v49[31] & 4) == 0 )
      return 1;
    if ( (v5 & 8) == 0 )
    {
      v50 = *((_QWORD *)v9 + 13);
      if ( !v50
        || (*(_BYTE *)(*(_QWORD *)(v50 + 40) + 31LL) & 2) == 0 && (GetAppCompatFlags(*((_QWORD *)v9 + 2)) & 0x4000) == 0 )
      {
        return 1;
      }
    }
    v51 = W32GetUserSessionState(v49);
    SetRectRgnIndirect(*(_QWORD *)(v51 + 63136), &v88);
    if ( (v5 & 0x8000) != 0 )
    {
      v52 = 0;
      do
      {
        v60 = *(HRGN *)(*((_QWORD *)v9 + 5) + 168LL);
        v81 = v60;
        if ( v60 )
        {
          if ( v52 )
          {
            v61 = LogicalToPhysicalInPlaceRgnWorker(v52, &v81, 0);
            v60 = v81;
            v62 = v61;
          }
          else
          {
            v62 = 0;
          }
          v63 = *(_QWORD *)(W32GetUserSessionState(v52) + 63136);
          v65 = W32GetUserSessionState(v64);
          GreCombineRgn(*(_QWORD *)(v65 + 63136), v63, v60, 1);
          if ( v62 )
            GreDeleteObject(v60);
        }
        v52 = v9;
        v9 = (struct tagWND *)*((_QWORD *)v9 + 13);
      }
      while ( v9 );
    }
    v53 = W32GetUserSessionState(v52);
    return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v53 + 63136), 4) != 1;
  }
  v72 = *(_QWORD *)(Prop + 40);
  if ( v72 || (v72 = CreateEmptyRgnPublic()) != 0 )
  {
    v73 = W32GetUserSessionState(v70);
    SetRectRgnIndirect(*(_QWORD *)(v73 + 63136), &v88);
    if ( v72 != 1 )
    {
      v75 = W32GetUserSessionState(v74);
      GreCombineRgn(v72, v72, *(_QWORD *)(v75 + 63136), 2);
    }
  }
  else
  {
    v72 = 1;
    v77 = W32GetUserSessionState(v70);
    SetRectRgnIndirect(*(_QWORD *)(v77 + 63136), &v88);
  }
  *(_QWORD *)(v71 + 40) = v72;
  v76 = W32GetUserSessionState(v74);
  return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v76 + 63136), 4) != 1;
}

```

## disassembly

```asm
0x140090ac0  push    rbp
0x140090ac2  push    rbx
0x140090ac3  push    rsi
0x140090ac4  push    rdi
0x140090ac5  push    r12
0x140090ac7  push    r13
0x140090ac9  push    r14
0x140090acb  push    r15
0x140090acd  lea     rbp, [rsp-17h]
0x140090ad2  sub     rsp, 98h
0x140090ad9  mov     rax, cs:__security_cookie
0x140090ae0  xor     rax, rsp
0x140090ae3  mov     [rbp+4Fh+var_48], rax
0x140090ae7  mov     esi, [rbp+4Fh+arg_20]
0x140090aea  xorps   xmm0, xmm0
0x140090aed  bts     esi, 0Fh
0x140090af1  mov     [rbp+4Fh+var_78], r8
0x140090af5  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm0
0x140090af9  mov     r12, rdx
0x140090afc  mov     r13, r8
0x140090aff  mov     rdx, [rcx+28h]
0x140090b03  mov     r14, rcx
0x140090b06  cmp     qword ptr [rdx+0A8h], 0
0x140090b0e  movups  xmm0, xmmword ptr [rdx+58h]
0x140090b12  cmovz   esi, [rbp+4Fh+arg_20]
0x140090b16  mov     r15d, esi
0x140090b19  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm0
0x140090b1d  and     r15d, 1
0x140090b21  jz      loc_140090C55
0x140090b27  movzx   ecx, byte ptr [rdx+1Ah]
0x140090b2b  shr     cl, 3
0x140090b2e  bt      esi, 10h
0x140090b32  setnb   al
0x140090b35  and     cl, al
0x140090b37  test    cl, 1
0x140090b3a  jz      short loc_140090B7C
0x140090b3c  test    dword ptr [r14+17Ch], 4000h
0x140090b47  jnz     short loc_140090B7C
0x140090b49  mov     r8, [r14+68h]
0x140090b4d  test    r8, r8
0x140090b50  jz      short loc_140090B6E
0x140090b52  mov     rax, [r14+18h]
0x140090b56  test    rax, rax
0x140090b59  jz      short loc_140090B6E
0x140090b5b  mov     rcx, [rax+8]
0x140090b5f  test    rcx, rcx
0x140090b62  jz      short loc_140090B6E
0x140090b64  cmp     r8, [rcx+18h]
0x140090b68  jz      loc_140090C98
0x140090b6e  mov     eax, [rdx+0E8h]
0x140090b74  test    al, 2
0x140090b76  jz      loc_140090C98
0x140090b7c  and     dword ptr [r14+17Ch], 0FFFFBFFFh
0x140090b87  movzx   ecx, byte ptr [rdx+1Bh]
0x140090b8b  movzx   eax, byte ptr [rdx+1Ah]
0x140090b8f  shr     cl, 5
0x140090b92  shr     al, 3
0x140090b95  not     cl
0x140090b97  not     al
0x140090b99  and     cl, al
0x140090b9b  test    cl, 1
0x140090b9e  jz      loc_140090E41
0x140090ba4  cmp     qword ptr [r14+68h], 0
0x140090ba9  movups  xmm0, xmmword ptr [r9]
0x140090bad  movups  xmmword ptr [rbp+4Fh+var_98.left], xmm0
0x140090bb1  jnz     loc_140090E30
0x140090bb7  mov     edx, [rbp+4Fh+var_58.left]
0x140090bba  cmp     edx, [rbp+4Fh+var_98.left]
0x140090bbd  mov     r8d, [rbp+4Fh+var_58.right]
0x140090bc1  cmovle  edx, [rbp+4Fh+var_98.left]
0x140090bc5  cmp     r8d, [rbp+4Fh+var_98.right]
0x140090bc9  mov     [rbp+4Fh+var_58.left], edx
0x140090bcc  cmovge  r8d, [rbp+4Fh+var_98.right]
0x140090bd1  mov     [rbp+4Fh+var_58.right], r8d
0x140090bd5  cmp     edx, r8d
0x140090bd8  jge     short loc_140090C01
0x140090bda  mov     edx, [rbp+4Fh+var_58.top]
0x140090bdd  cmp     edx, [rbp+4Fh+var_98.top]
0x140090be0  mov     r8d, [rbp+4Fh+var_58.bottom]
0x140090be4  cmovle  edx, [rbp+4Fh+var_98.top]
0x140090be8  cmp     r8d, [rbp+4Fh+var_98.bottom]
0x140090bec  mov     [rbp+4Fh+var_58.top], edx
0x140090bef  cmovge  r8d, [rbp+4Fh+var_98.bottom]
0x140090bf4  mov     [rbp+4Fh+var_58.bottom], r8d
0x140090bf8  cmp     edx, r8d
0x140090bfb  jl      loc_140090E60
0x140090c01  xorps   xmm0, xmm0
0x140090c04  xorps   xmm2, xmm2
0x140090c07  movups  xmmword ptr [rbp+4Fh+var_58.left], xmm2
0x140090c0b  psrldq  xmm0, 0Ch
0x140090c10  xorps   xmm1, xmm1
0x140090c13  movd    [rbp+4Fh+var_58.bottom], xmm0
0x140090c18  xorps   xmm0, xmm0
0x140090c1b  psrldq  xmm0, 4
0x140090c20  psrldq  xmm1, 8
0x140090c25  movd    [rbp+4Fh+var_58.top], xmm0
0x140090c2a  movd    [rbp+4Fh+var_58.right], xmm1
0x140090c2f  movss   [rbp+4Fh+var_58.left], xmm2
0x140090c34  mov     eax, 1
0x140090c39  test    eax, eax
0x140090c3b  jnz     short loc_140090C98
0x140090c3d  cmp     r12, 1
0x140090c41  ja      loc_140090D75
0x140090c47  mov     rax, [r14+28h]
0x140090c4b  test    byte ptr [rax+1Bh], 10h
0x140090c4f  jnz     loc_14009130F
0x140090c55  mov     rax, [r14+28h]
0x140090c59  test    byte ptr [rax+1Fh], 2
0x140090c5d  jnz     short loc_140090C6D
0x140090c5f  mov     r8d, esi
0x140090c62  mov     rdx, r12
0x140090c65  mov     rcx, r14; struct tagWND *
0x140090c68  call    InternalInvalidate3
0x140090c6d  mov     rdi, [r14+70h]
0x140090c71  test    rdi, rdi
0x140090c74  jnz     short loc_140090CBE
0x140090c76  mov     rax, [r14+28h]
0x140090c7a  test    byte ptr [rax+1Fh], 2
0x140090c7e  jz      short loc_140090C8E
0x140090c80  mov     r8d, esi
0x140090c83  mov     rdx, r12
0x140090c86  mov     rcx, r14; struct tagWND *
0x140090c89  call    InternalInvalidate3
0x140090c8e  bt      esi, 0Dh
0x140090c92  jb      loc_1400910A6
0x140090c98  mov     eax, 1
0x140090c9d  mov     rcx, [rbp+4Fh+var_48]
0x140090ca1  xor     rcx, rsp; StackCookie
0x140090ca4  call    __security_check_cookie
0x140090ca9  add     rsp, 98h
0x140090cb0  pop     r15
0x140090cb2  pop     r14
0x140090cb4  pop     r13
0x140090cb6  pop     r12
0x140090cb8  pop     rdi
0x140090cb9  pop     rsi
0x140090cba  pop     rbx
0x140090cbb  pop     rbp
0x140090cbc  retn
0x140090cbe  mov     r9, [r14+28h]
0x140090cc2  movzx   edx, byte ptr [r9+1Fh]
0x140090cc7  movzx   ecx, dl
0x140090cca  shr     cl, 5
0x140090ccd  test    sil, 40h
0x140090cd1  not     cl
0x140090cd3  setz    al
0x140090cd6  and     cl, al
0x140090cd8  test    cl, 1
0x140090cdb  jz      short loc_140090C76
0x140090cdd  test    sil, sil
0x140090ce0  js      short loc_140090CE7
0x140090ce2  test    dl, 2
0x140090ce5  jnz     short loc_140090C76
0x140090ce7  mov     r10d, esi
0x140090cea  xorps   xmm0, xmm0
0x140090ced  bts     r10d, 0Dh
0x140090cf2  movups  xmmword ptr [rbp+4Fh+var_98.left], xmm0
0x140090cf6  mov     ecx, [r9+68h]
0x140090cfa  mov     eax, r10d
0x140090cfd  or      eax, 404h
0x140090d02  test    r15d, r15d
0x140090d05  cmovnz  r10d, eax
0x140090d09  cmp     [rbp+4Fh+var_58.left], ecx
0x140090d0c  mov     [rbp+4Fh+var_A0], r10d
0x140090d10  cmovg   ecx, [rbp+4Fh+var_58.left]
0x140090d14  mov     [rbp+4Fh+var_98.left], ecx
0x140090d17  mov     eax, [r9+70h]
0x140090d1b  cmp     [rbp+4Fh+var_58.right], eax
0x140090d1e  cmovl   eax, [rbp+4Fh+var_58.right]
0x140090d22  mov     [rbp+4Fh+var_98.right], eax
0x140090d25  cmp     ecx, eax
0x140090d27  jge     loc_140090C76
0x140090d2d  mov     ecx, [r9+6Ch]
0x140090d31  cmp     [rbp+4Fh+var_58.top], ecx
0x140090d34  cmovg   ecx, [rbp+4Fh+var_58.top]
0x140090d38  mov     [rbp+4Fh+var_98.top], ecx
0x140090d3b  mov     eax, [r9+74h]
0x140090d3f  cmp     [rbp+4Fh+var_58.bottom], eax
0x140090d42  cmovl   eax, [rbp+4Fh+var_58.bottom]
0x140090d46  mov     [rbp+4Fh+var_98.bottom], eax
0x140090d49  cmp     ecx, eax
0x140090d4b  jge     loc_140090C76
0x140090d51  xor     r15d, r15d
0x140090d54  test    rdi, rdi
0x140090d57  jz      loc_140091089
0x140090d5d  mov     rcx, [rdi+28h]
0x140090d61  test    byte ptr [rcx+1Fh], 10h
0x140090d65  jnz     loc_140090E67
0x140090d6b  mov     rdi, [rdi+58h]
0x140090d6f  mov     r13, [rbp+4Fh+var_78]
0x140090d73  jmp     short loc_140090D54
0x140090d75  lea     rdx, [rbp+4Fh+var_58]; struct tagRECT *
0x140090d79  mov     rcx, r12; HRGN
0x140090d7c  call    ?SmartRectInRegion@@YAIPEAUHRGN__@@PEAUtagRECT@@@Z; SmartRectInRegion(HRGN__ *,tagRECT *)
0x140090d81  cmp     eax, 1
0x140090d84  jnz     loc_140091150
0x140090d8a  bt      esi, 0Fh
0x140090d8e  jnb     loc_140090C47
0x140090d94  call    cs:__imp_W32GetUserSessionState
0x140090d9b  nop     dword ptr [rax+rax+00h]
0x140090da0  lea     rdx, [rbp+4Fh+var_58]
0x140090da4  mov     rcx, [rax+0F6A0h]
0x140090dab  call    cs:__imp_SetRectRgnIndirect
0x140090db2  nop     dword ptr [rax+rax+00h]
0x140090db7  xor     ecx, ecx
0x140090db9  mov     rdi, r14
0x140090dbc  mov     rax, [rdi+28h]
0x140090dc0  mov     r13, [rax+0A8h]
0x140090dc7  mov     [rbp+4Fh+var_88], r13
0x140090dcb  test    r13, r13
0x140090dce  jnz     loc_14009117F
0x140090dd4  mov     rcx, rdi
0x140090dd7  mov     rdi, [rdi+68h]
0x140090ddb  test    rdi, rdi
0x140090dde  jnz     short loc_140090DBC
0x140090de0  call    cs:__imp_W32GetUserSessionState
0x140090de7  nop     dword ptr [rax+rax+00h]
0x140090dec  mov     rbx, [rax+0F6A0h]
0x140090df3  call    cs:__imp_W32GetUserSessionState
0x140090dfa  nop     dword ptr [rax+rax+00h]
0x140090dff  mov     r9d, 1
0x140090e05  mov     r8, r12
0x140090e08  mov     rdx, rbx
0x140090e0b  mov     rcx, [rax+0F6A0h]
0x140090e12  call    cs:__imp_GreCombineRgn
0x140090e19  nop     dword ptr [rax+rax+00h]
0x140090e1e  cmp     eax, 1
0x140090e21  jz      loc_140090C98
0x140090e27  mov     r13, [rbp+4Fh+var_78]
0x140090e2b  jmp     loc_140090C47
0x140090e30  lea     rdx, [rbp+4Fh+var_98]
0x140090e34  mov     rcx, r14
0x140090e37  call    PhysicalToLogicalInPlaceRect
0x140090e3c  jmp     loc_140090BB7
0x140090e41  mov     eax, [rbp+4Fh+var_58.right]
0x140090e44  cmp     [rbp+4Fh+var_58.left], eax
0x140090e47  jge     loc_140090C34
0x140090e4d  mov     eax, [rbp+4Fh+var_58.bottom]
0x140090e50  cmp     [rbp+4Fh+var_58.top], eax
0x140090e53  jge     loc_140090C34
0x140090e59  xor     eax, eax
0x140090e5b  jmp     loc_140090C39
0x140090e60  xor     eax, eax
0x140090e62  jmp     loc_140090C39
0x140090e67  test    byte ptr [rcx+1Bh], 20h
0x140090e6b  jz      loc_140091073
0x140090e71  mov     [rbp+4Fh+var_80], 1
0x140090e78  test    r15, r15
0x140090e7b  jnz     short loc_140090E91
0x140090e7d  call    cs:__imp_CreateEmptyRgnPublic
0x140090e84  nop     dword ptr [rax+rax+00h]
0x140090e89  mov     r15, rax
0x140090e8c  test    rax, rax
0x140090e8f  jz      short loc_140090EB5
0x140090e91  xor     r8d, r8d
0x140090e94  mov     r9d, 5
0x140090e9a  mov     rcx, r15
0x140090e9d  mov     rdx, r13
0x140090ea0  cmp     r12, 1
0x140090ea4  jz      short loc_140090EA9
0x140090ea6  mov     rdx, r12
0x140090ea9  call    cs:__imp_GreCombineRgn
0x140090eb0  nop     dword ptr [rax+rax+00h]
0x140090eb5  lea     rdx, [rbp+4Fh+var_98]
0x140090eb9  mov     [rbp+4Fh+var_70], r12
0x140090ebd  mov     rcx, rdi
0x140090ec0  mov     [rbp+4Fh+var_88], r13
0x140090ec4  call    PhysicalToLogicalInPlaceRect
0x140090ec9  lea     rdx, [rbp+4Fh+var_70]
0x140090ecd  mov     [rbp+4Fh+var_64], eax
0x140090ed0  mov     rcx, rdi
0x140090ed3  call    PhysicalToLogicalInPlaceRgn
0x140090ed8  lea     rdx, [rbp+4Fh+var_88]
0x140090edc  mov     rcx, rdi
0x140090edf  mov     ebx, eax
0x140090ee1  call    PhysicalToLogicalInPlaceRgn
0x140090ee6  mov     r13, [rbp+4Fh+var_70]
0x140090eea  lea     r9, [rbp+4Fh+var_98]; struct tagRECT *
0x140090eee  mov     [rbp+4Fh+var_68], eax
0x140090ef1  mov     rdx, r13; HRGN
0x140090ef4  mov     eax, [rbp+4Fh+var_A0]
0x140090ef7  mov     rcx, rdi; struct tagWND *
0x140090efa  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x140090efe  mov     rax, [rbp+4Fh+var_88]
0x140090f02  mov     r8, rax; HRGN
0x140090f05  mov     [rbp+4Fh+var_60], rax
0x140090f09  call    ?InternalInvalidate2@@YAHPEAUtagWND@@PEAUHRGN__@@1PEAUtagRECT@@K@Z; InternalInvalidate2(tagWND *,HRGN__ *,HRGN__ *,tagRECT *,ulong)
0x140090f0e  mov     dword ptr [rbp+4Fh+var_70], eax
0x140090f11  test    ebx, ebx
0x140090f13  jz      short loc_140090F24
0x140090f15  mov     rcx, r13
0x140090f18  call    cs:__imp_GreDeleteObject
0x140090f1f  nop     dword ptr [rax+rax+00h]
0x140090f24  cmp     [rbp+4Fh+var_68], 0
0x140090f28  jnz     loc_140091298
0x140090f2e  mov     r13, [rbp+4Fh+var_78]
0x140090f32  cmp     [rbp+4Fh+var_64], 0
0x140090f36  jz      short loc_140090F47
0x140090f38  mov     rax, [rdi+28h]
0x140090f3c  mov     ecx, [rax+0E8h]
  ... truncated ...
```
