# NtGdiDrawStreamInternal(XDCOBJ &,EXFORMOBJ &,SURFACE *,_XLATEOBJ *,_RECTL *,_RECTL *,long,char *,_DRAWSTREAMINFO *)

- ea: `0x140062400`
- end: `0x140062bec`
- name: `?NtGdiDrawStreamInternal@@YAHAEAVXDCOBJ@@AEAVEXFORMOBJ@@PEAVSURFACE@@PEAU_XLATEOBJ@@PEAU_RECTL@@4JPEADPEAU_DRAWSTREAMINFO@@@Z`
- size: `2028`
- prototype: `__int64 __usercall@<rax>(struct XDCOBJ *this@<rcx>, struct EXFORMOBJ *@<rdx>, struct SURFACE *@<r8>, struct _XLATEOBJ *@<r9>, struct _RECTL *, struct _RECTL *, int, char *, struct _DRAWSTREAMINFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140079e6c`

## callees

- `0x1400615f4`
- `0x140062400`
- `0x140062bf4`
- `0x140063ee0`
- `0x14006ba00`
- `0x14006ba5c`
- `0x14009510c`
- `0x14009519c`
- `0x14016cabc`
- `0x14030f740`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006254c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006254c`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400628f2`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400625d7`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400628f2`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400628dd`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400628dd`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140062568`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140062568`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062a03`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062a2c`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062a03`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062a2c`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1400629f2`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140062a1b`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1400629f2`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140062a1b`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140062ab9`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140062adb`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140062ab9`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140062adb`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062aa8`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062aca`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062aa8`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140062aca`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140062a4f`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140062a4f`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400626b2`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400626b2`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140062a6d`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140062a6d`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140062a87`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140062a87`
- `win32kbase!EngSetLastError` at `0x14006265c`
- `win32kbase!EngSetLastError` at `0x14006265c`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x1400628c6`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x1400628c6`

## pseudocode

```c
_BOOL8 __fastcall NtGdiDrawStreamInternal(
        DC **this,
        struct EXFORMOBJ *a2,
        struct SURFACE *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *a5,
        struct _RECTL *a6,
        int a7,
        char *a8,
        struct _DRAWSTREAMINFO *a9)
{
  BOOL v11; // r15d
  DC *v12; // rcx
  struct SURFACE *v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  DC *v16; // rbx
  int right; // eax
  int left; // ecx
  Gre::Base *top; // rcx
  DC *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r11
  __int64 v23; // rdi
  char *i; // rbx
  int v26; // r14d
  LONG v27; // ebx
  LONG v28; // esi
  LONG v29; // edi
  char *v30; // r14
  struct REGION *v31; // rax
  int v32; // r9d
  __m128i v33; // xmm1
  __int32 v34; // ecx
  int v35; // r8d
  DC *v36; // rcx
  int v37; // r10d
  __int64 v38; // rax
  LONG v39; // r8d
  int v40; // edx
  int v41; // r9d
  LONG v42; // r11d
  int v43; // eax
  LONG v44; // r10d
  __int64 v45; // r15
  __int64 (__fastcall *v46)(int, int, int, int, int, __int64, __int64, __int64, __int64); // rbx
  __int64 v47; // rdx
  __int64 v48; // rsi
  bool v49; // al
  struct SURFACE *v50; // r13
  unsigned __int64 v51; // rdi
  int v52; // eax
  __int32 v53; // r10d
  __int32 v54; // r9d
  _DWORD *v55; // r11
  __int64 v56; // r13
  __int64 v57; // rbx
  __int64 v58; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v59; // [rsp+58h] [rbp-99h] BYREF
  __int64 v60; // [rsp+60h] [rbp-91h] BYREF
  int v61; // [rsp+68h] [rbp-89h]
  __int64 v62; // [rsp+70h] [rbp-81h] BYREF
  HSEMAPHORE v63; // [rsp+78h] [rbp-79h]
  __int64 v64; // [rsp+80h] [rbp-71h]
  struct SURFACE *v65; // [rsp+88h] [rbp-69h]
  struct _DRAWSTREAMINFO *v66; // [rsp+90h] [rbp-61h]
  char *v67; // [rsp+98h] [rbp-59h]
  struct _XLATEOBJ *v68; // [rsp+A0h] [rbp-51h]
  __m128i v69; // [rsp+B0h] [rbp-41h] BYREF
  struct _RECTL v70; // [rsp+C0h] [rbp-31h] BYREF
  __m128i v71; // [rsp+D0h] [rbp-21h] BYREF

  v11 = 0;
  v66 = a9;
  v69.m128i_i64[0] = *(_QWORD *)&a5->left;
  v69.m128i_i32[2] = a5->right;
  v12 = *this;
  v69.m128i_i32[3] = a5->bottom;
  v68 = a4;
  v60 = 0;
  v65 = a3;
  v61 = a7;
  v70 = *a6;
  v13 = (struct SURFACE *)*((_QWORD *)v12 + 62);
  v67 = a8;
  if ( (unsigned int)DestSurfaceAccessCheck(v13) )
  {
    v14 = *(_QWORD *)a2;
    if ( (*(_BYTE *)(*(_QWORD *)a2 + 32LL) & 1) != 0 )
    {
      v15 = *(_DWORD *)(v14 + 32);
      if ( (v15 & 2) != 0 )
      {
        if ( (v15 & 0x43) != 0x43 )
          bCvtPts1(v14, &v60, 1);
      }
      else
      {
        for ( i = a8; i < &a8[a7]; i += 60 )
        {
          if ( *(_DWORD *)i != 9 )
            return v11;
          DC::bXform(*this, a2, (struct ERECTL *)(i + 4));
          if ( (unsigned int)DC::bDpiScaledSurface(*this) )
            *((_DWORD *)i + 9) &= ~0x20u;
        }
      }
      v16 = *this;
      if ( ((*(_BYTE *)(*(_QWORD *)a2 + 32LL) & 0x43) == 0x43 || (unsigned int)bCvtPts1(*(_QWORD *)a2, &v70, 2))
        && (*(_DWORD *)(*((_QWORD *)v16 + 122) + 108LL) & 1) != 0 )
      {
        left = v70.left + 1;
        right = v70.right + 1;
        ++v70.left;
        ++v70.right;
      }
      else
      {
        right = v70.right;
        left = v70.left;
      }
      if ( left > right )
      {
        v70.left = right;
        v70.right = left;
      }
      top = (Gre::Base *)(unsigned int)v70.top;
      if ( v70.top > v70.bottom )
      {
        v70.top = v70.bottom;
        v70.bottom = (int)top;
      }
      if ( v69.m128i_i32[0] != v69.m128i_i32[2] && v69.m128i_i32[1] != v69.m128i_i32[3] )
      {
        v63 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(top) + 624LL);
        GreAcquireSemaphoreSharedInternal(v63);
        GrepAcquireLockValidate<1>();
        v20 = *this;
        v21 = *((_DWORD *)*this + 10) & 1;
        v64 = *((_QWORD *)*this + 62);
        LODWORD(v60) = *((_DWORD *)v20 + 2 * v21 + 254) + v60;
        HIDWORD(v60) += *((_DWORD *)v20 + 2 * v21 + 255);
        v22 = *((_DWORD *)v20 + 10) & 1;
        v23 = *((int *)v20 + 2 * v22 + 254);
        if ( (unsigned __int64)(v23 + v69.m128i_i32[0] + 0x80000000LL) <= 0xFFFFFFFF
          && (unsigned __int64)(v23 + v69.m128i_i32[2] + 0x80000000LL) <= 0xFFFFFFFF )
        {
          v57 = *((int *)v20 + 2 * v22 + 255);
          if ( (unsigned __int64)(v57 + v69.m128i_i32[1] + 0x80000000LL) <= 0xFFFFFFFF
            && (unsigned __int64)(v57 + v69.m128i_i32[3] + 0x80000000LL) <= 0xFFFFFFFF )
          {
            v35 = v23 + v69.m128i_i32[0];
            v69.m128i_i32[0] += v23;
            v34 = *((_DWORD *)v20 + 2 * v22 + 254) + v69.m128i_i32[2];
            v53 = *((_DWORD *)v20 + 2 * v22 + 255) + v69.m128i_i32[1];
            *(__int64 *)((char *)v69.m128i_i64 + 4) = __PAIR64__(v34, v53);
            v54 = *((_DWORD *)v20 + 2 * v22 + 255) + v69.m128i_i32[3];
            v55 = (_DWORD *)((char *)v20 + 1024);
            v69.m128i_i32[3] = v54;
            if ( (*((_DWORD *)v20 + 10) & 1) == 0 )
              v55 = (_DWORD *)((char *)v20 + 1016);
            LODWORD(v58) = *v55;
            if ( (unsigned __int64)(v70.left + (__int64)(int)v58 + 0x80000000LL) <= 0xFFFFFFFF
              && (unsigned __int64)((int)v58 + (__int64)v70.right + 0x80000000LL) <= 0xFFFFFFFF )
            {
              v56 = (int)v55[1];
              if ( (unsigned __int64)(v70.top + v56 + 0x80000000LL) <= 0xFFFFFFFF
                && (unsigned __int64)(v70.bottom + v56 + 0x80000000LL) <= 0xFFFFFFFF )
              {
                v26 = v58 + v70.left;
                v70.left += v58;
                v27 = *v55 + v70.right;
                v70.right = v27;
                v28 = v55[1] + v70.top;
                v70.top = v28;
                v29 = v55[1] + v70.bottom;
                v70.bottom = v29;
                if ( v54 >= v29
                  && v35 <= v26
                  && v53 <= v28
                  && v34 >= v27
                  && (v52 = *((_DWORD *)v20 + 250), v52 <= v26)
                  && *((_DWORD *)v20 + 252) >= v27
                  && *((_DWORD *)v20 + 251) <= v28
                  && *((_DWORD *)v20 + 253) >= v29 )
                {
                  if ( v52 > v35 )
                    v35 = *((_DWORD *)v20 + 250);
                  v69.m128i_i32[0] = v35;
                  if ( *((_DWORD *)v20 + 251) > v53 )
                    v53 = *((_DWORD *)v20 + 251);
                  v69.m128i_i32[1] = v53;
                  if ( *((_DWORD *)v20 + 252) < v34 )
                    v34 = *((_DWORD *)v20 + 252);
                  v69.m128i_i32[2] = v34;
                  if ( *((_DWORD *)v20 + 253) < v54 )
                    v54 = *((_DWORD *)v20 + 253);
                  v69.m128i_i32[3] = v54;
                  if ( v34 < v35 )
                  {
                    v69.m128i_i32[0] = v34;
                    goto LABEL_81;
                  }
                  v30 = 0;
                  if ( v54 < v53 )
                    v69.m128i_i32[1] = v54;
                  v33 = v69;
                }
                else
                {
                  v30 = (char *)v20 + 1768;
                  v31 = XDCOBJ::prgnEffRao((XDCOBJ *)this);
                  XCLIPOBJ::vSetup((XCLIPOBJ *)v30, v31, (const struct ERECTL *)&v69, v32);
                  v69 = *(__m128i *)(v30 + 4);
                  v33 = v69;
                  v34 = _mm_cvtsi128_si32(_mm_srli_si128(v69, 8));
                  v35 = _mm_cvtsi128_si32(v69);
                }
                if ( v35 != v34 && v33.m128i_i32[1] != _mm_srli_si128(v33, 8).m128i_i32[1] )
                {
                  v36 = *this;
                  v37 = *((_DWORD *)*this + 9);
                  if ( (v37 & 0xE0) != 0 )
                  {
                    v71 = v33;
                    v38 = *((_DWORD *)v36 + 10) & 1;
                    v39 = v35 - *((_DWORD *)v36 + 2 * v38 + 254);
                    v71.m128i_i32[0] = v39;
                    v40 = v33.m128i_i32[2] - *((_DWORD *)v36 + 2 * v38 + 254);
                    v71.m128i_i32[2] = v40;
                    v41 = v33.m128i_i32[1] - *((_DWORD *)v36 + 2 * v38 + 255);
                    v71.m128i_i32[1] = v41;
                    v71.m128i_i32[3] = v33.m128i_i32[3] - *((_DWORD *)v36 + 2 * v38 + 255);
                    if ( (v37 & 0x40) != 0 )
                    {
                      v42 = *((_DWORD *)v36 + 270);
                      v43 = *((_DWORD *)v36 + 272);
                      if ( v42 == v43 || (v44 = *((_DWORD *)v36 + 273), *((_DWORD *)v36 + 271) == v44) )
                      {
                        *(__m128i *)((char *)v36 + 1080) = v71;
                      }
                      else
                      {
                        if ( v39 < v42 )
                        {
                          *((_DWORD *)v36 + 270) = v39;
                          v40 = v71.m128i_i32[2];
                          v41 = v71.m128i_i32[1];
                        }
                        if ( v41 < *((_DWORD *)v36 + 271) )
                        {
                          *((_DWORD *)v36 + 271) = v41;
                          v40 = v71.m128i_i32[2];
                        }
                        if ( v40 > v43 )
                          *((_DWORD *)v36 + 272) = v40;
                        if ( v71.m128i_i32[3] > v44 )
                          *((_DWORD *)v36 + 273) = v71.m128i_i32[3];
                      }
                      v62 = *((_QWORD *)*this + 148);
                      if ( v62 )
                      {
                        v59 = 0;
                        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v59, 0x70u);
                        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v59);
                        v58 = 0;
                        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v58, 0x70u);
                        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v58);
                        if ( v59 )
                        {
                          if ( v58 )
                          {
                            RGNOBJ::vSet((RGNOBJ *)&v58, (const struct _RECTL *const)&v71);
                            if ( RGNOBJ::bMerge((RGNOBJ *)&v59, (struct RGNOBJ *)&v62, (struct RGNOBJ *)&v58, 0xEu) )
                            {
                              RGNOBJ::vSwap((RGNOBJ *)&v62, (struct RGNOBJ *)&v59);
                              *((_QWORD *)*this + 148) = v62;
                            }
                          }
                        }
                        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v58);
                        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v58);
                        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v59);
                        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v59);
                      }
                    }
                  }
                  v45 = v64;
                  v46 = EngDrawStream;
                  v47 = *(_QWORD *)(v64 + 48);
                  v48 = v64 + 24;
                  ++*(_DWORD *)(v64 + 92);
                  if ( *(_QWORD *)(v47 + 3400) )
                    v46 = *(__int64 (__fastcall **)(int, int, int, int, int, __int64, __int64, __int64, __int64))(v47 + 3400);
                  v49 = (*((_DWORD *)*this + 9) & 0x200) != 0 && v47 && (*(_DWORD *)(v47 + 40) & 0x20000) != 0;
                  if ( *(int *)(v45 + 160) >= 0 && (!v49 || *(_WORD *)(v45 + 100) != 3) )
                    v46 = EngDrawStream;
                  v50 = v65;
                  v51 = (unsigned __int64)v65 + 24;
                  SURFREFVIEW::SURFREFVIEW(
                    &v71,
                    ((unsigned __int64)v65 + 24) & ((unsigned __int128)-(__int128)(unsigned __int64)v65 >> 64),
                    4);
                  v11 = v71.m128i_i64[0]
                     && (unsigned int)v46(
                                        v48 & -(__int64)(v45 != 0),
                                        v51 & -(__int64)(v50 != 0),
                                        (int)v30,
                                        (int)v68,
                                        (int)&v69,
                                        (__int64)&v60,
                                        v61,
                                        (__int64)v67,
                                        (__int64)v66);
                  SURFREFVIEW::bUnMap((SURFREFVIEW *)&v71);
                  goto LABEL_57;
                }
LABEL_81:
                v11 = 1;
LABEL_57:
                EtwTraceGreLockReleaseSemaphore(L"DynamicModeChange", v63);
                GrepReleaseLockValidate<1>();
                GreReleaseSemaphoreSharedInternal(v63);
                return v11;
              }
            }
          }
        }
        GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
      }
    }
  }
  else
  {
    EngSetLastError(5u);
  }
  return v11;
}

```

## disassembly

```asm
0x140062400  push    rbp
0x140062402  push    rbx
0x140062403  push    rsi
0x140062404  push    rdi
0x140062405  push    r12
0x140062407  push    r13
0x140062409  push    r14
0x14006240b  push    r15
0x14006240d  lea     rbp, [rsp-7]
0x140062412  sub     rsp, 0F8h
0x140062419  mov     rax, cs:__security_cookie
0x140062420  xor     rax, rsp
0x140062423  mov     [rbp+3Fh+var_50], rax
0x140062427  mov     rax, [rbp+3Fh+arg_40]
0x14006242e  mov     r12, rcx
0x140062431  mov     rcx, [rbp+3Fh+arg_20]
0x140062435  xor     r13d, r13d
0x140062438  movsxd  rdi, [rbp+3Fh+arg_30]
0x14006243c  mov     rsi, rdx
0x14006243f  mov     r14, [rbp+3Fh+arg_38]
0x140062446  mov     r15d, r13d
0x140062449  mov     [rbp+3Fh+var_A0], rax
0x14006244d  mov     eax, [rcx]
0x14006244f  mov     dword ptr [rbp+3Fh+var_80], eax
0x140062452  mov     eax, [rcx+4]
0x140062455  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x140062458  mov     eax, [rcx+8]
0x14006245b  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x14006245e  mov     eax, [rcx+0Ch]
0x140062461  mov     rcx, [r12]
0x140062465  mov     dword ptr [rbp+3Fh+var_80+0Ch], eax
0x140062468  mov     [rbp+3Fh+var_90], r9
0x14006246c  mov     r9, [rbp+3Fh+arg_28]
0x140062470  mov     [rsp+130h+var_D0], r13
0x140062475  mov     [rbp+3Fh+var_A8], r8
0x140062479  mov     [rsp+130h+var_C8], edi
0x14006247d  mov     eax, [r9]
0x140062480  mov     [rbp+3Fh+var_70], eax
0x140062483  mov     eax, [r9+4]
0x140062487  mov     [rbp+3Fh+var_6C], eax
0x14006248a  mov     eax, [r9+8]
0x14006248e  mov     [rbp+3Fh+var_68], eax
0x140062491  mov     eax, [r9+0Ch]
0x140062495  mov     [rbp+3Fh+var_64], eax
0x140062498  mov     rcx, [rcx+1F0h]; struct SURFACE *
0x14006249f  mov     [rbp+3Fh+var_98], r14
0x1400624a3  call    ?DestSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; DestSurfaceAccessCheck(SURFACE *)
0x1400624a8  test    eax, eax
0x1400624aa  jz      loc_140062657
0x1400624b0  mov     rcx, [rsi]
0x1400624b3  test    byte ptr [rcx+20h], 1
0x1400624b7  jz      loc_1400625E3
0x1400624bd  mov     eax, [rcx+20h]
0x1400624c0  test    al, 2
0x1400624c2  jz      loc_140062607
0x1400624c8  and     eax, 43h
0x1400624cb  cmp     al, 43h ; 'C'
0x1400624cd  jz      short loc_1400624DD
0x1400624cf  lea     r8d, [r13+1]
0x1400624d3  lea     rdx, [rsp+130h+var_D0]
0x1400624d8  call    bCvtPts1
0x1400624dd  mov     rcx, [rsi]
0x1400624e0  mov     rbx, [r12]
0x1400624e4  mov     eax, [rcx+20h]
0x1400624e7  and     eax, 43h
0x1400624ea  cmp     al, 43h ; 'C'
0x1400624ec  jz      short loc_140062501
0x1400624ee  mov     r8d, 2
0x1400624f4  lea     rdx, [rbp+3Fh+var_70]
0x1400624f8  call    bCvtPts1
0x1400624fd  test    eax, eax
0x1400624ff  jz      short loc_140062514
0x140062501  mov     rax, [rbx+3D0h]
0x140062508  mov     ecx, [rax+6Ch]
0x14006250b  test    cl, 1
0x14006250e  jnz     loc_140062642
0x140062514  mov     eax, [rbp+3Fh+var_68]
0x140062517  mov     ecx, [rbp+3Fh+var_70]
0x14006251a  cmp     ecx, eax
0x14006251c  jle     short loc_140062524
0x14006251e  mov     [rbp+3Fh+var_70], eax
0x140062521  mov     [rbp+3Fh+var_68], ecx
0x140062524  mov     ecx, [rbp+3Fh+var_6C]
0x140062527  mov     eax, [rbp+3Fh+var_64]
0x14006252a  cmp     ecx, eax
0x14006252c  jle     short loc_140062534
0x14006252e  mov     [rbp+3Fh+var_6C], eax
0x140062531  mov     [rbp+3Fh+var_64], ecx
0x140062534  mov     eax, dword ptr [rbp+3Fh+var_80+8]
0x140062537  cmp     dword ptr [rbp+3Fh+var_80], eax
0x14006253a  jz      loc_1400625E3
0x140062540  mov     eax, dword ptr [rbp+3Fh+var_80+0Ch]
0x140062543  cmp     dword ptr [rbp+3Fh+var_80+4], eax
0x140062546  jz      loc_1400625E3
0x14006254c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140062553  nop     dword ptr [rax+rax+00h]
0x140062558  mov     rax, [rax]
0x14006255b  add     rax, 270h
0x140062561  mov     rcx, rax
0x140062564  mov     [rbp+3Fh+var_B8], rax
0x140062568  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14006256f  nop     dword ptr [rax+rax+00h]
0x140062574  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140062579  mov     rdx, [r12]
0x14006257d  mov     esi, 80000000h
0x140062582  movsxd  r8, dword ptr [rbp+3Fh+var_80]
0x140062586  mov     r13d, 0FFFFFFFFh
0x14006258c  mov     ecx, [rdx+28h]
0x14006258f  mov     rax, [rdx+1F0h]
0x140062596  and     ecx, 1
0x140062599  mov     [rbp+3Fh+var_B0], rax
0x14006259d  mov     eax, [rdx+rcx*8+3F8h]
0x1400625a4  add     dword ptr [rsp+130h+var_D0], eax
0x1400625a8  mov     eax, [rdx+rcx*8+3FCh]
0x1400625af  add     dword ptr [rsp+130h+var_D0+4], eax
0x1400625b3  mov     r11d, [rdx+28h]
0x1400625b7  and     r11d, 1
0x1400625bb  movsxd  rdi, dword ptr [rdx+r11*8+3F8h]
0x1400625c3  lea     rax, [rdi+r8]
0x1400625c7  add     rax, rsi
0x1400625ca  cmp     rax, r13
0x1400625cd  jbe     loc_140062BA3
0x1400625d3  mov     rdx, [rbp+3Fh+var_B8]
0x1400625d7  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400625de  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1400625e3  mov     eax, r15d
0x1400625e6  mov     rcx, [rbp+3Fh+var_50]
0x1400625ea  xor     rcx, rsp; StackCookie
0x1400625ed  call    __security_check_cookie
0x1400625f2  add     rsp, 0F8h
0x1400625f9  pop     r15
0x1400625fb  pop     r14
0x1400625fd  pop     r13
0x1400625ff  pop     r12
0x140062601  pop     rdi
0x140062602  pop     rsi
0x140062603  pop     rbx
0x140062604  pop     rbp
0x140062605  retn
0x140062607  mov     rbx, r14
0x14006260a  add     rdi, r14
0x14006260d  cmp     rbx, rdi
0x140062610  jnb     loc_1400624DD
0x140062616  cmp     dword ptr [rbx], 9
0x140062619  jnz     short loc_1400625E3
0x14006261b  mov     rcx, [r12]; this
0x14006261f  lea     r8, [rbx+4]; struct ERECTL *
0x140062623  mov     rdx, rsi; struct EXFORMOBJ *
0x140062626  call    ?bXform@DC@@QEBA_NAEBVEXFORMOBJ@@AEAVERECTL@@@Z; DC::bXform(EXFORMOBJ const &,ERECTL &)
0x14006262b  mov     rcx, [r12]; this
0x14006262f  call    ?bDpiScaledSurface@DC@@QEBAHXZ; DC::bDpiScaledSurface(void)
0x140062634  test    eax, eax
0x140062636  jz      short loc_14006263C
0x140062638  and     dword ptr [rbx+24h], 0FFFFFFDFh
0x14006263c  add     rbx, 3Ch ; '<'
0x140062640  jmp     short loc_14006260D
0x140062642  mov     ecx, [rbp+3Fh+var_70]
0x140062645  mov     eax, [rbp+3Fh+var_68]
0x140062648  inc     ecx
0x14006264a  inc     eax
0x14006264c  mov     [rbp+3Fh+var_70], ecx
0x14006264f  mov     [rbp+3Fh+var_68], eax
0x140062652  jmp     loc_14006251A
0x140062657  mov     ecx, 5; iError
0x14006265c  call    cs:__imp_EngSetLastError
0x140062663  nop     dword ptr [rax+rax+00h]
0x140062668  jmp     loc_1400625E3
0x14006266d  add     r14d, dword ptr [rsp+130h+var_E0]
0x140062672  mov     [rbp+3Fh+var_70], r14d
0x140062676  add     ebx, [r11]
0x140062679  mov     [rbp+3Fh+var_68], ebx
0x14006267c  add     esi, [r11+4]
0x140062680  mov     [rbp+3Fh+var_6C], esi
0x140062683  add     edi, [r11+4]
0x140062687  mov     [rbp+3Fh+var_64], edi
0x14006268a  cmp     r9d, edi
0x14006268d  jge     loc_140062903
0x140062693  mov     r9d, 1
0x140062699  mov     rcx, r12; this
0x14006269c  lea     r14, [rdx+6E8h]
0x1400626a3  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x1400626a8  mov     rdx, rax
0x1400626ab  lea     r8, [rbp+3Fh+var_80]
0x1400626af  mov     rcx, r14
0x1400626b2  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x1400626b9  nop     dword ptr [rax+rax+00h]
0x1400626be  movups  xmm1, xmmword ptr [r14+4]
0x1400626c3  movdqa  xmm0, xmm1
0x1400626c7  movaps  [rbp+3Fh+var_80], xmm1
0x1400626cb  psrldq  xmm0, 8
0x1400626d0  movd    ecx, xmm0
0x1400626d4  movd    r8d, xmm1
0x1400626d9  cmp     r8d, ecx
0x1400626dc  jz      loc_1400629B4
0x1400626e2  movdqa  xmm0, xmm1
0x1400626e6  movq    rax, xmm1
0x1400626eb  psrldq  xmm0, 8
0x1400626f0  movq    rcx, xmm0
0x1400626f5  shr     rax, 20h
0x1400626f9  shr     rcx, 20h
0x1400626fd  cmp     eax, ecx
0x1400626ff  jz      loc_1400629B4
0x140062705  mov     rcx, [r12]
0x140062709  mov     r10d, [rcx+24h]
0x14006270d  test    r10b, 0E0h
0x140062711  jz      loc_1400627E0
0x140062717  movdqa  [rbp+3Fh+var_60], xmm1
0x14006271c  mov     eax, [rcx+28h]
0x14006271f  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x140062722  and     eax, 1
0x140062725  mov     r9d, dword ptr [rbp+3Fh+var_60+4]
0x140062729  sub     r8d, [rcx+rax*8+3F8h]
0x140062731  mov     dword ptr [rbp+3Fh+var_60], r8d
0x140062735  sub     edx, [rcx+rax*8+3F8h]
0x14006273c  mov     dword ptr [rbp+3Fh+var_60+8], edx
0x14006273f  sub     r9d, [rcx+rax*8+3FCh]
0x140062747  mov     dword ptr [rbp+3Fh+var_60+4], r9d
0x14006274b  mov     eax, [rcx+rax*8+3FCh]
0x140062752  sub     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x140062755  test    r10b, 40h
0x140062759  jz      loc_1400627E0
0x14006275f  mov     r11d, [rcx+438h]
0x140062766  mov     eax, [rcx+440h]
0x14006276c  cmp     r11d, eax
0x14006276f  jz      loc_1400629BF
0x140062775  mov     r10d, [rcx+444h]
0x14006277c  cmp     [rcx+43Ch], r10d
0x140062783  jz      loc_1400629BF
0x140062789  cmp     r8d, r11d
0x14006278c  jge     short loc_14006279C
0x14006278e  mov     [rcx+438h], r8d
0x140062795  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x140062798  mov     r9d, dword ptr [rbp+3Fh+var_60+4]
0x14006279c  cmp     r9d, [rcx+43Ch]
0x1400627a3  jge     short loc_1400627AF
0x1400627a5  mov     [rcx+43Ch], r9d
0x1400627ac  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x1400627af  cmp     edx, eax
0x1400627b1  jle     short loc_1400627B9
0x1400627b3  mov     [rcx+440h], edx
0x1400627b9  mov     eax, dword ptr [rbp+3Fh+var_60+0Ch]
0x1400627bc  cmp     eax, r10d
0x1400627bf  jle     short loc_1400627C7
0x1400627c1  mov     [rcx+444h], eax
0x1400627c7  mov     rax, [r12]
0x1400627cb  mov     rcx, [rax+4A0h]
0x1400627d2  mov     [rsp+130h+var_C0], rcx
0x1400627d7  test    rcx, rcx
0x1400627da  jnz     loc_1400629E1
0x1400627e0  mov     r15, [rbp+3Fh+var_B0]
0x1400627e4  lea     rbx, EngDrawStream
0x1400627eb  mov     rdx, [r15+30h]
0x1400627ef  lea     rsi, [r15+18h]
0x1400627f3  mov     eax, [rsi+44h]
0x1400627f6  inc     eax
0x1400627f8  mov     [r15+5Ch], eax
0x1400627fc  mov     rax, [rdx+0D48h]
0x140062803  test    rax, rax
0x140062806  cmovnz  rbx, rax
0x14006280a  mov     rax, [r12]
0x14006280e  test    dword ptr [rax+24h], 200h
0x140062815  jz      short loc_140062820
0x140062817  test    rdx, rdx
0x14006281a  jnz     loc_140062948
0x140062820  xor     al, al
0x140062822  cmp     dword ptr [r15+0A0h], 0
0x14006282a  jl      short loc_14006283B
0x14006282c  test    al, al
0x14006282e  jnz     loc_1400629D0
0x140062834  lea     rbx, EngDrawStream
0x14006283b  mov     r13, [rbp+3Fh+var_A8]
0x14006283f  lea     rcx, [rbp+3Fh+var_60]
0x140062843  mov     rax, r13
0x140062846  mov     r8d, 4
0x14006284c  neg     rax
0x14006284f  sbb     rdx, rdx
0x140062852  lea     rdi, [r13+18h]
0x140062856  and     rdx, rdi
0x140062859  call    ??0SURFREFVIEW@@QEAA@PEAU_SURFOBJ@@W4U2KMMAPStatus@@@Z; SURFREFVIEW::SURFREFVIEW(_SURFOBJ *,U2KMMAPStatus)
0x14006285e  cmp     qword ptr [rbp+3Fh+var_60], 0
0x140062863  jz      short loc_1400628BF
0x140062865  mov     rax, [rbp+3Fh+var_A0]
0x140062869  neg     r13
0x14006286c  mov     r9, [rbp+3Fh+var_90]
0x140062870  mov     r8, r14
0x140062873  mov     [rsp+130h+var_F0], rax
0x140062878  sbb     rdx, rdx
0x14006287b  mov     rax, [rbp+3Fh+var_98]
0x14006287f  and     rdx, rdi
0x140062882  mov     [rsp+130h+var_F8], rax
0x140062887  neg     r15
0x14006288a  mov     eax, [rsp+130h+var_C8]
0x14006288e  mov     [rsp+130h+var_100], eax
0x140062892  sbb     rcx, rcx
0x140062895  lea     rax, [rsp+130h+var_D0]
0x14006289a  and     rcx, rsi
0x14006289d  mov     [rsp+130h+var_108], rax
0x1400628a2  lea     rax, [rbp+3Fh+var_80]
0x1400628a6  mov     [rsp+130h+var_110], rax
0x1400628ab  mov     rax, rbx
  ... truncated ...
```
