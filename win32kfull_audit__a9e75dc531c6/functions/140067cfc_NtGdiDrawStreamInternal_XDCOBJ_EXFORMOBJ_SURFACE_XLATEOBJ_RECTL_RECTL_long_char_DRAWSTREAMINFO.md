# NtGdiDrawStreamInternal(XDCOBJ &,EXFORMOBJ &,SURFACE *,_XLATEOBJ *,_RECTL *,_RECTL *,long,char *,_DRAWSTREAMINFO *)

- ea: `0x140067cfc`
- end: `0x1400684f1`
- name: `?NtGdiDrawStreamInternal@@YAHAEAVXDCOBJ@@AEAVEXFORMOBJ@@PEAVSURFACE@@PEAU_XLATEOBJ@@PEAU_RECTL@@4JPEADPEAU_DRAWSTREAMINFO@@@Z`
- size: `2037`
- prototype: `_BOOL8 __fastcall(DC **this, struct EXFORMOBJ *, struct SURFACE *, struct _XLATEOBJ *, struct _RECTL *, struct _RECTL *, int, char *, struct _DRAWSTREAMINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400502c4`

## callees

- `0x14006743c`
- `0x140067498`
- `0x1400677c0`
- `0x140067cfc`
- `0x1400684f8`
- `0x1400697e4`
- `0x1400ab71c`
- `0x1400ab7ac`
- `0x1401ad190`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140067e48`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140067e48`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400681f7`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140067ed3`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400681f7`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400681e2`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1400681e2`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140067e64`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140067e64`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140068308`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140068331`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140068308`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140068331`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1400682f7`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140068320`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1400682f7`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140068320`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400683be`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400683e0`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400683be`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400683e0`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400683ad`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400683cf`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400683ad`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1400683cf`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140068354`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140068354`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140067fae`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140067fae`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140068372`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140068372`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14006838c`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x14006838c`
- `win32kbase!EngSetLastError` at `0x140067f58`
- `win32kbase!EngSetLastError` at `0x140067f58`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x1400681cb`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x1400681cb`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x140068157`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x140068157`

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
                  if ( *(int *)(v45 + 144) >= 0 && (!v49 || *(_WORD *)(v45 + 100) != 3) )
                    v46 = EngDrawStream;
                  v50 = v65;
                  v71.m128i_i64[0] = 0;
                  v51 = (unsigned __int64)v65 + 24;
                  SURFREFVIEW::bMap(
                    (SURFREFVIEW *)&v71,
                    (struct _SURFOBJ *)(((unsigned __int64)v65 + 24)
                                      & ((unsigned __int128)-(__int128)(unsigned __int64)v65 >> 64)));
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
        GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v63);
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
0x140067cfc  push    rbp
0x140067cfe  push    rbx
0x140067cff  push    rsi
0x140067d00  push    rdi
0x140067d01  push    r12
0x140067d03  push    r13
0x140067d05  push    r14
0x140067d07  push    r15
0x140067d09  lea     rbp, [rsp-7]
0x140067d0e  sub     rsp, 0F8h
0x140067d15  mov     rax, cs:__security_cookie
0x140067d1c  xor     rax, rsp
0x140067d1f  mov     [rbp+3Fh+var_50], rax
0x140067d23  mov     rax, [rbp+3Fh+arg_40]
0x140067d2a  mov     r12, rcx
0x140067d2d  mov     rcx, [rbp+3Fh+arg_20]
0x140067d31  xor     r13d, r13d
0x140067d34  movsxd  rdi, [rbp+3Fh+arg_30]
0x140067d38  mov     rsi, rdx
0x140067d3b  mov     r14, [rbp+3Fh+arg_38]
0x140067d42  mov     r15d, r13d
0x140067d45  mov     [rbp+3Fh+var_A0], rax
0x140067d49  mov     eax, [rcx]
0x140067d4b  mov     dword ptr [rbp+3Fh+var_80], eax
0x140067d4e  mov     eax, [rcx+4]
0x140067d51  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x140067d54  mov     eax, [rcx+8]
0x140067d57  mov     dword ptr [rbp+3Fh+var_80+8], eax
0x140067d5a  mov     eax, [rcx+0Ch]
0x140067d5d  mov     rcx, [r12]
0x140067d61  mov     dword ptr [rbp+3Fh+var_80+0Ch], eax
0x140067d64  mov     [rbp+3Fh+var_90], r9
0x140067d68  mov     r9, [rbp+3Fh+arg_28]
0x140067d6c  mov     [rsp+130h+var_D0], r13
0x140067d71  mov     [rbp+3Fh+var_A8], r8
0x140067d75  mov     [rsp+130h+var_C8], edi
0x140067d79  mov     eax, [r9]
0x140067d7c  mov     [rbp+3Fh+var_70], eax
0x140067d7f  mov     eax, [r9+4]
0x140067d83  mov     [rbp+3Fh+var_6C], eax
0x140067d86  mov     eax, [r9+8]
0x140067d8a  mov     [rbp+3Fh+var_68], eax
0x140067d8d  mov     eax, [r9+0Ch]
0x140067d91  mov     [rbp+3Fh+var_64], eax
0x140067d94  mov     rcx, [rcx+1F0h]; struct SURFACE *
0x140067d9b  mov     [rbp+3Fh+var_98], r14
0x140067d9f  call    ?DestSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; DestSurfaceAccessCheck(SURFACE *)
0x140067da4  test    eax, eax
0x140067da6  jz      loc_140067F53
0x140067dac  mov     rcx, [rsi]
0x140067daf  test    byte ptr [rcx+20h], 1
0x140067db3  jz      loc_140067EDF
0x140067db9  mov     eax, [rcx+20h]
0x140067dbc  test    al, 2
0x140067dbe  jz      loc_140067F03
0x140067dc4  and     eax, 43h
0x140067dc7  cmp     al, 43h ; 'C'
0x140067dc9  jz      short loc_140067DD9
0x140067dcb  lea     r8d, [r13+1]
0x140067dcf  lea     rdx, [rsp+130h+var_D0]
0x140067dd4  call    bCvtPts1
0x140067dd9  mov     rcx, [rsi]
0x140067ddc  mov     rbx, [r12]
0x140067de0  mov     eax, [rcx+20h]
0x140067de3  and     eax, 43h
0x140067de6  cmp     al, 43h ; 'C'
0x140067de8  jz      short loc_140067DFD
0x140067dea  mov     r8d, 2
0x140067df0  lea     rdx, [rbp+3Fh+var_70]
0x140067df4  call    bCvtPts1
0x140067df9  test    eax, eax
0x140067dfb  jz      short loc_140067E10
0x140067dfd  mov     rax, [rbx+3D0h]
0x140067e04  mov     ecx, [rax+6Ch]
0x140067e07  test    cl, 1
0x140067e0a  jnz     loc_140067F3E
0x140067e10  mov     eax, [rbp+3Fh+var_68]
0x140067e13  mov     ecx, [rbp+3Fh+var_70]
0x140067e16  cmp     ecx, eax
0x140067e18  jle     short loc_140067E20
0x140067e1a  mov     [rbp+3Fh+var_70], eax
0x140067e1d  mov     [rbp+3Fh+var_68], ecx
0x140067e20  mov     ecx, [rbp+3Fh+var_6C]
0x140067e23  mov     eax, [rbp+3Fh+var_64]
0x140067e26  cmp     ecx, eax
0x140067e28  jle     short loc_140067E30
0x140067e2a  mov     [rbp+3Fh+var_6C], eax
0x140067e2d  mov     [rbp+3Fh+var_64], ecx
0x140067e30  mov     eax, dword ptr [rbp+3Fh+var_80+8]
0x140067e33  cmp     dword ptr [rbp+3Fh+var_80], eax
0x140067e36  jz      loc_140067EDF
0x140067e3c  mov     eax, dword ptr [rbp+3Fh+var_80+0Ch]
0x140067e3f  cmp     dword ptr [rbp+3Fh+var_80+4], eax
0x140067e42  jz      loc_140067EDF
0x140067e48  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140067e4f  nop     dword ptr [rax+rax+00h]
0x140067e54  mov     rax, [rax]
0x140067e57  add     rax, 270h
0x140067e5d  mov     rcx, rax
0x140067e60  mov     [rbp+3Fh+var_B8], rax
0x140067e64  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140067e6b  nop     dword ptr [rax+rax+00h]
0x140067e70  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140067e75  mov     rdx, [r12]
0x140067e79  mov     esi, 80000000h
0x140067e7e  movsxd  r8, dword ptr [rbp+3Fh+var_80]
0x140067e82  mov     r13d, 0FFFFFFFFh
0x140067e88  mov     ecx, [rdx+28h]
0x140067e8b  mov     rax, [rdx+1F0h]
0x140067e92  and     ecx, 1
0x140067e95  mov     [rbp+3Fh+var_B0], rax
0x140067e99  mov     eax, [rdx+rcx*8+3F8h]
0x140067ea0  add     dword ptr [rsp+130h+var_D0], eax
0x140067ea4  mov     eax, [rdx+rcx*8+3FCh]
0x140067eab  add     dword ptr [rsp+130h+var_D0+4], eax
0x140067eaf  mov     r11d, [rdx+28h]
0x140067eb3  and     r11d, 1
0x140067eb7  movsxd  rdi, dword ptr [rdx+r11*8+3F8h]
0x140067ebf  lea     rax, [rdi+r8]
0x140067ec3  add     rax, rsi
0x140067ec6  cmp     rax, r13
0x140067ec9  jbe     loc_1400684A8
0x140067ecf  mov     rdx, [rbp+3Fh+var_B8]
0x140067ed3  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140067eda  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140067edf  mov     eax, r15d
0x140067ee2  mov     rcx, [rbp+3Fh+var_50]
0x140067ee6  xor     rcx, rsp; StackCookie
0x140067ee9  call    __security_check_cookie
0x140067eee  add     rsp, 0F8h
0x140067ef5  pop     r15
0x140067ef7  pop     r14
0x140067ef9  pop     r13
0x140067efb  pop     r12
0x140067efd  pop     rdi
0x140067efe  pop     rsi
0x140067eff  pop     rbx
0x140067f00  pop     rbp
0x140067f01  retn
0x140067f03  mov     rbx, r14
0x140067f06  add     rdi, r14
0x140067f09  cmp     rbx, rdi
0x140067f0c  jnb     loc_140067DD9
0x140067f12  cmp     dword ptr [rbx], 9
0x140067f15  jnz     short loc_140067EDF
0x140067f17  mov     rcx, [r12]; this
0x140067f1b  lea     r8, [rbx+4]; struct ERECTL *
0x140067f1f  mov     rdx, rsi; struct EXFORMOBJ *
0x140067f22  call    ?bXform@DC@@QEBA_NAEBVEXFORMOBJ@@AEAVERECTL@@@Z; DC::bXform(EXFORMOBJ const &,ERECTL &)
0x140067f27  mov     rcx, [r12]; this
0x140067f2b  call    ?bDpiScaledSurface@DC@@QEBAHXZ; DC::bDpiScaledSurface(void)
0x140067f30  test    eax, eax
0x140067f32  jz      short loc_140067F38
0x140067f34  and     dword ptr [rbx+24h], 0FFFFFFDFh
0x140067f38  add     rbx, 3Ch ; '<'
0x140067f3c  jmp     short loc_140067F09
0x140067f3e  mov     ecx, [rbp+3Fh+var_70]
0x140067f41  mov     eax, [rbp+3Fh+var_68]
0x140067f44  inc     ecx
0x140067f46  inc     eax
0x140067f48  mov     [rbp+3Fh+var_70], ecx
0x140067f4b  mov     [rbp+3Fh+var_68], eax
0x140067f4e  jmp     loc_140067E16
0x140067f53  mov     ecx, 5; iError
0x140067f58  call    cs:__imp_EngSetLastError
0x140067f5f  nop     dword ptr [rax+rax+00h]
0x140067f64  jmp     loc_140067EDF
0x140067f69  add     r14d, dword ptr [rsp+130h+var_E0]
0x140067f6e  mov     [rbp+3Fh+var_70], r14d
0x140067f72  add     ebx, [r11]
0x140067f75  mov     [rbp+3Fh+var_68], ebx
0x140067f78  add     esi, [r11+4]
0x140067f7c  mov     [rbp+3Fh+var_6C], esi
0x140067f7f  add     edi, [r11+4]
0x140067f83  mov     [rbp+3Fh+var_64], edi
0x140067f86  cmp     r9d, edi
0x140067f89  jge     loc_140068208
0x140067f8f  mov     r9d, 1
0x140067f95  mov     rcx, r12; this
0x140067f98  lea     r14, [rdx+6E8h]
0x140067f9f  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140067fa4  mov     rdx, rax
0x140067fa7  lea     r8, [rbp+3Fh+var_80]
0x140067fab  mov     rcx, r14
0x140067fae  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x140067fb5  nop     dword ptr [rax+rax+00h]
0x140067fba  movups  xmm1, xmmword ptr [r14+4]
0x140067fbf  movdqa  xmm0, xmm1
0x140067fc3  movaps  [rbp+3Fh+var_80], xmm1
0x140067fc7  psrldq  xmm0, 8
0x140067fcc  movd    ecx, xmm0
0x140067fd0  movd    r8d, xmm1
0x140067fd5  cmp     r8d, ecx
0x140067fd8  jz      loc_1400682B9
0x140067fde  movdqa  xmm0, xmm1
0x140067fe2  movq    rax, xmm1
0x140067fe7  psrldq  xmm0, 8
0x140067fec  movq    rcx, xmm0
0x140067ff1  shr     rax, 20h
0x140067ff5  shr     rcx, 20h
0x140067ff9  cmp     eax, ecx
0x140067ffb  jz      loc_1400682B9
0x140068001  mov     rcx, [r12]
0x140068005  mov     r10d, [rcx+24h]
0x140068009  test    r10b, 0E0h
0x14006800d  jz      loc_1400680DC
0x140068013  movdqa  [rbp+3Fh+var_60], xmm1
0x140068018  mov     eax, [rcx+28h]
0x14006801b  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x14006801e  and     eax, 1
0x140068021  mov     r9d, dword ptr [rbp+3Fh+var_60+4]
0x140068025  sub     r8d, [rcx+rax*8+3F8h]
0x14006802d  mov     dword ptr [rbp+3Fh+var_60], r8d
0x140068031  sub     edx, [rcx+rax*8+3F8h]
0x140068038  mov     dword ptr [rbp+3Fh+var_60+8], edx
0x14006803b  sub     r9d, [rcx+rax*8+3FCh]
0x140068043  mov     dword ptr [rbp+3Fh+var_60+4], r9d
0x140068047  mov     eax, [rcx+rax*8+3FCh]
0x14006804e  sub     dword ptr [rbp+3Fh+var_60+0Ch], eax
0x140068051  test    r10b, 40h
0x140068055  jz      loc_1400680DC
0x14006805b  mov     r11d, [rcx+438h]
0x140068062  mov     eax, [rcx+440h]
0x140068068  cmp     r11d, eax
0x14006806b  jz      loc_1400682C4
0x140068071  mov     r10d, [rcx+444h]
0x140068078  cmp     [rcx+43Ch], r10d
0x14006807f  jz      loc_1400682C4
0x140068085  cmp     r8d, r11d
0x140068088  jge     short loc_140068098
0x14006808a  mov     [rcx+438h], r8d
0x140068091  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x140068094  mov     r9d, dword ptr [rbp+3Fh+var_60+4]
0x140068098  cmp     r9d, [rcx+43Ch]
0x14006809f  jge     short loc_1400680AB
0x1400680a1  mov     [rcx+43Ch], r9d
0x1400680a8  mov     edx, dword ptr [rbp+3Fh+var_60+8]
0x1400680ab  cmp     edx, eax
0x1400680ad  jle     short loc_1400680B5
0x1400680af  mov     [rcx+440h], edx
0x1400680b5  mov     eax, dword ptr [rbp+3Fh+var_60+0Ch]
0x1400680b8  cmp     eax, r10d
0x1400680bb  jle     short loc_1400680C3
0x1400680bd  mov     [rcx+444h], eax
0x1400680c3  mov     rax, [r12]
0x1400680c7  mov     rcx, [rax+4A0h]
0x1400680ce  mov     [rsp+130h+var_C0], rcx
0x1400680d3  test    rcx, rcx
0x1400680d6  jnz     loc_1400682E6
0x1400680dc  mov     r15, [rbp+3Fh+var_B0]
0x1400680e0  lea     rbx, EngDrawStream
0x1400680e7  mov     rdx, [r15+30h]
0x1400680eb  lea     rsi, [r15+18h]
0x1400680ef  mov     eax, [rsi+44h]
0x1400680f2  inc     eax
0x1400680f4  mov     [r15+5Ch], eax
0x1400680f8  mov     rax, [rdx+0D48h]
0x1400680ff  test    rax, rax
0x140068102  cmovnz  rbx, rax
0x140068106  mov     rax, [r12]
0x14006810a  test    dword ptr [rax+24h], 200h
0x140068111  jz      short loc_14006811C
0x140068113  test    rdx, rdx
0x140068116  jnz     loc_14006824D
0x14006811c  xor     al, al
0x14006811e  cmp     dword ptr [r15+90h], 0
0x140068126  jl      short loc_140068137
0x140068128  test    al, al
0x14006812a  jnz     loc_1400682D5
0x140068130  lea     rbx, EngDrawStream
0x140068137  mov     r13, [rbp+3Fh+var_A8]
0x14006813b  lea     rcx, [rbp+3Fh+var_60]
0x14006813f  mov     rax, r13
0x140068142  mov     qword ptr [rbp+3Fh+var_60], 0
0x14006814a  neg     rax
0x14006814d  sbb     rdx, rdx
0x140068150  lea     rdi, [r13+18h]
0x140068154  and     rdx, rdi
0x140068157  call    cs:__imp_?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z; SURFREFVIEW::bMap(_SURFOBJ *)
0x14006815e  nop     dword ptr [rax+rax+00h]
0x140068163  cmp     qword ptr [rbp+3Fh+var_60], 0
0x140068168  jz      short loc_1400681C4
0x14006816a  mov     rax, [rbp+3Fh+var_A0]
0x14006816e  neg     r13
0x140068171  mov     r9, [rbp+3Fh+var_90]
0x140068175  mov     r8, r14
0x140068178  mov     [rsp+130h+var_F0], rax
0x14006817d  sbb     rdx, rdx
0x140068180  mov     rax, [rbp+3Fh+var_98]
0x140068184  and     rdx, rdi
0x140068187  mov     [rsp+130h+var_F8], rax
0x14006818c  neg     r15
0x14006818f  mov     eax, [rsp+130h+var_C8]
0x140068193  mov     [rsp+130h+var_100], eax
0x140068197  sbb     rcx, rcx
0x14006819a  lea     rax, [rsp+130h+var_D0]
0x14006819f  and     rcx, rsi
0x1400681a2  mov     [rsp+130h+var_108], rax
0x1400681a7  lea     rax, [rbp+3Fh+var_80]
0x1400681ab  mov     [rsp+130h+var_110], rax
  ... truncated ...
```
