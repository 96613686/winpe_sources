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
  __int64 left; // rdx
  struct tagWND *v9; // r14
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  bool v14; // zf
  int right; // r8d
  int bottom; // r8d
  int v17; // eax
  __int64 v18; // rdi
  __int64 v20; // r9
  int v21; // r10d
  LONG v22; // ecx
  LONG v23; // eax
  LONG top; // ecx
  LONG v25; // eax
  __int64 EmptyRgnPublic; // r15
  _BYTE *v27; // rcx
  unsigned int v28; // eax
  __int64 UserSessionState; // rax
  __int64 v30; // rdx
  struct tagWND *v31; // rcx
  struct tagWND *v32; // rdi
  HRGN v33; // r13
  __int64 v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  HRGN v38; // rdx
  int v39; // ebx
  int v40; // eax
  HRGN v41; // r13
  __int64 v42; // r8
  __int64 v43; // r9
  HRGN v44; // r13
  int v45; // ebx
  HRGN v46; // rcx
  __int64 v47; // rax
  int v48; // ecx
  _BYTE *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rdx
  struct tagWND *v53; // rcx
  __int64 v54; // rax
  unsigned int v55; // eax
  bool v56; // cf
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rax
  HRGN v62; // rdi
  int v63; // eax
  int v64; // esi
  __int64 v65; // rbx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rax
  unsigned int v69; // eax
  int v70; // eax
  __int64 v71; // rax
  __int64 Prop; // rax
  __int64 v73; // rcx
  __int64 v74; // rdi
  __int64 v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  unsigned int v82; // [rsp+30h] [rbp-51h]
  unsigned int v83; // [rsp+30h] [rbp-51h]
  struct tagRECT v84; // [rsp+38h] [rbp-49h] BYREF
  HRGN v85; // [rsp+48h] [rbp-39h] BYREF
  int v86; // [rsp+50h] [rbp-31h]
  HRGN v87; // [rsp+58h] [rbp-29h]
  HRGN v88; // [rsp+60h] [rbp-21h] BYREF
  int v89; // [rsp+68h] [rbp-19h]
  int v90; // [rsp+6Ch] [rbp-15h]
  HRGN v91; // [rsp+70h] [rbp-11h]
  struct tagRECT v92; // [rsp+78h] [rbp-9h] BYREF

  v5 = a5 | 0x8000;
  v87 = a3;
  v92 = 0;
  v7 = a3;
  left = *((_QWORD *)a1 + 5);
  v9 = a1;
  if ( !*(_QWORD *)(left + 168) )
    v5 = a5;
  v92 = *(struct tagRECT *)(left + 88);
  if ( (v5 & 1) == 0 )
    goto LABEL_29;
  if ( (((v5 & 0x10000) == 0) & (*(_BYTE *)(left + 26) >> 3)) != 0 && (*((_DWORD *)a1 + 95) & 0x4000) == 0 )
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
    if ( (*(_DWORD *)(left + 232) & 2) == 0 )
      return 1;
  }
  *((_DWORD *)v9 + 95) &= ~0x4000u;
  v13 = *(unsigned __int8 *)(left + 27);
  LOBYTE(v13) = ~(*(_BYTE *)(left + 26) >> 3) & ~((unsigned __int8)v13 >> 5);
  if ( (v13 & 1) != 0 )
  {
    v14 = *((_QWORD *)v9 + 13) == 0;
    v84 = *a4;
    if ( !v14 )
      PhysicalToLogicalInPlaceRect(v9, &v84);
    left = (unsigned int)v92.left;
    right = v92.right;
    if ( v92.left <= v84.left )
      left = (unsigned int)v84.left;
    v92.left = left;
    if ( v92.right >= v84.right )
      right = v84.right;
    v92.right = right;
    if ( (int)left < right )
    {
      left = (unsigned int)v92.top;
      bottom = v92.bottom;
      if ( v92.top <= v84.top )
        left = (unsigned int)v84.top;
      v92.top = left;
      if ( v92.bottom >= v84.bottom )
        bottom = v84.bottom;
      v92.bottom = bottom;
      if ( (int)left < bottom )
      {
        v17 = 0;
        goto LABEL_26;
      }
    }
    v92.bottom = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
    v92.top = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v92.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v92.left = 0;
  }
  else if ( v92.left < v92.right && v92.top < v92.bottom )
  {
    v17 = 0;
    goto LABEL_26;
  }
  v17 = 1;
LABEL_26:
  if ( v17 )
    return 1;
  if ( (unsigned __int64)a2 <= 1 )
    goto LABEL_28;
  v28 = SmartRectInRegion(a2, &v92);
  if ( v28 == 1 )
  {
    if ( (v5 & 0x8000) != 0 )
    {
      UserSessionState = W32GetUserSessionState(v13, left);
      SetRectRgnIndirect(*(_QWORD *)(UserSessionState + 63136), &v92);
      v31 = 0;
      v32 = v9;
      do
      {
        v33 = *(HRGN *)(*((_QWORD *)v32 + 5) + 168LL);
        v85 = v33;
        if ( v33 )
        {
          if ( v31 )
          {
            v69 = PhysicalToLogicalInPlaceRgn(v31, &v85);
            v33 = v85;
            v83 = v69;
          }
          else
          {
            v83 = 0;
          }
          v58 = *(_QWORD *)(W32GetUserSessionState(v31, v30) + 63136);
          v61 = W32GetUserSessionState(v60, v59);
          GreCombineRgn(*(_QWORD *)(v61 + 63136), v58, v33, 1);
          if ( v83 )
            GreDeleteObject(v33);
        }
        v31 = v32;
        v32 = (struct tagWND *)*((_QWORD *)v32 + 13);
      }
      while ( v32 );
      v34 = *(_QWORD *)(W32GetUserSessionState(v31, v30) + 63136);
      v37 = W32GetUserSessionState(v36, v35);
      if ( (unsigned int)GreCombineRgn(*(_QWORD *)(v37 + 63136), v34, a2, 1) == 1 )
        return 1;
      v7 = v87;
    }
    goto LABEL_28;
  }
  if ( !v28 )
    return 1;
  v55 = v28 - 2;
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
    || (v71 = W32GetUserSessionState(v13, left),
        Prop = GetProp(v9, *(unsigned __int16 *)(v71 + 41198), 1),
        (v74 = Prop) == 0) )
  {
LABEL_29:
    if ( (*(_BYTE *)(*((_QWORD *)v9 + 5) + 31LL) & 2) == 0 )
      InternalInvalidate3(v9);
    v18 = *((_QWORD *)v9 + 14);
    if ( v18 )
    {
      v20 = *((_QWORD *)v9 + 5);
      left = *(unsigned __int8 *)(v20 + 31);
      if ( (((v5 & 0x40) == 0) & (unsigned __int8)~((unsigned __int8)left >> 5)) != 0
        && ((v5 & 0x80u) != 0 || (left & 2) == 0) )
      {
        v21 = v5 | 0x2000;
        v84 = 0;
        v22 = *(_DWORD *)(v20 + 104);
        if ( (v5 & 1) != 0 )
          v21 = v5 | 0x2404;
        v82 = v21;
        if ( v92.left > v22 )
          v22 = v92.left;
        v84.left = v22;
        v23 = *(_DWORD *)(v20 + 112);
        if ( v92.right < v23 )
          v23 = v92.right;
        v84.right = v23;
        if ( v22 < v23 )
        {
          top = *(_DWORD *)(v20 + 108);
          if ( v92.top > top )
            top = v92.top;
          v84.top = top;
          v25 = *(_DWORD *)(v20 + 116);
          if ( v92.bottom < v25 )
            v25 = v92.bottom;
          v84.bottom = v25;
          if ( top < v25 )
          {
            EmptyRgnPublic = 0;
            while ( v18 )
            {
              v27 = *(_BYTE **)(v18 + 40);
              if ( (v27[31] & 0x10) != 0 )
              {
                if ( (v27[27] & 0x20) != 0 || (v27[26] & 8) != 0 )
                {
                  v86 = 1;
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
                  v86 = 0;
                }
                v88 = a2;
                v85 = v7;
                v90 = PhysicalToLogicalInPlaceRect(v18, &v84);
                v39 = PhysicalToLogicalInPlaceRgn(v18, &v88);
                v40 = PhysicalToLogicalInPlaceRgn(v18, &v85);
                v41 = v88;
                v89 = v40;
                v91 = v85;
                LODWORD(v88) = InternalInvalidate2((struct tagWND *)v18, v88, v85, &v84, v82);
                if ( v39 )
                  GreDeleteObject(v41);
                if ( v89 )
                {
                  v70 = LogicalToPhysicalInPlaceRgnWorker(v18, &v85, 0);
                  v44 = v87;
                  if ( v70 )
                  {
                    GreCombineRgn(v87, v85, 0, 5);
                    GreDeleteObject(v85);
                  }
                  GreDeleteObject(v91);
                }
                else
                {
                  v44 = v87;
                }
                if ( v90
                  && (*(_DWORD *)(*(_QWORD *)(v18 + 40) + 232LL) & 2) != 0
                  && *(_QWORD *)(v18 + 216)
                  && (unsigned int)IsWindowDesktopComposed(v18, left, v42, v43) )
                {
                  v84.left = (int)(float)((float)v84.left * **(float **)(v18 + 216));
                  v84.top = (int)(float)((float)v84.top * *(float *)(*(_QWORD *)(v18 + 216) + 20LL));
                  v84.right = (int)(float)((float)v84.right * **(float **)(v18 + 216));
                  v84.bottom = (int)(float)((float)v84.bottom * *(float *)(*(_QWORD *)(v18 + 216) + 20LL));
                  v47 = *(_QWORD *)(v18 + 216);
                  v48 = (int)*(float *)(v47 + 48);
                  left = (unsigned int)(int)*(float *)(v47 + 52);
                  v84.left += v48;
                  v84.right += v48;
                  v84.bottom += left;
                  v84.top += left;
                }
                v45 = v86;
                if ( v86 && EmptyRgnPublic )
                {
                  v46 = v44;
                  if ( a2 != (HRGN)1 )
                    v46 = a2;
                  GreCombineRgn(v46, EmptyRgnPublic, 0, 5);
                }
                if ( !(_DWORD)v88 && !v45 )
                {
                  if ( (v5 & 0x12) == 0 )
                  {
                    if ( EmptyRgnPublic )
                      GreDeleteObject(EmptyRgnPublic);
                    return 0;
                  }
                  v5 &= 0xFFFFF3D2;
                  v82 &= 0xFFFFD3D2;
                }
              }
              v18 = *(_QWORD *)(v18 + 88);
              v7 = v87;
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
    v51 = W32GetUserSessionState(v49, left);
    SetRectRgnIndirect(*(_QWORD *)(v51 + 63136), &v92);
    if ( (v5 & 0x8000) != 0 )
    {
      v53 = 0;
      do
      {
        v62 = *(HRGN *)(*((_QWORD *)v9 + 5) + 168LL);
        v85 = v62;
        if ( v62 )
        {
          if ( v53 )
          {
            v63 = LogicalToPhysicalInPlaceRgnWorker(v53, &v85, 0);
            v62 = v85;
            v64 = v63;
          }
          else
          {
            v64 = 0;
          }
          v65 = *(_QWORD *)(W32GetUserSessionState(v53, v52) + 63136);
          v68 = W32GetUserSessionState(v67, v66);
          GreCombineRgn(*(_QWORD *)(v68 + 63136), v65, v62, 1);
          if ( v64 )
            GreDeleteObject(v62);
        }
        v53 = v9;
        v9 = (struct tagWND *)*((_QWORD *)v9 + 13);
      }
      while ( v9 );
    }
    v54 = W32GetUserSessionState(v53, v52);
    return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v54 + 63136), 4) != 1;
  }
  v75 = *(_QWORD *)(Prop + 40);
  if ( v75 || (v75 = CreateEmptyRgnPublic()) != 0 )
  {
    v76 = W32GetUserSessionState(v73, left);
    SetRectRgnIndirect(*(_QWORD *)(v76 + 63136), &v92);
    if ( v75 != 1 )
    {
      v79 = W32GetUserSessionState(v78, v77);
      GreCombineRgn(v75, v75, *(_QWORD *)(v79 + 63136), 2);
    }
  }
  else
  {
    v75 = 1;
    v81 = W32GetUserSessionState(v73, left);
    SetRectRgnIndirect(*(_QWORD *)(v81 + 63136), &v92);
  }
  *(_QWORD *)(v74 + 40) = v75;
  v80 = W32GetUserSessionState(v78, v77);
  return (unsigned int)GreCombineRgn(v7, v7, *(_QWORD *)(v80 + 63136), 4) != 1;
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
