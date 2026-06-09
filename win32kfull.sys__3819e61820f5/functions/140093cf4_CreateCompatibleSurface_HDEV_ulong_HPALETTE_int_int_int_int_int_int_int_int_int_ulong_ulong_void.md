# CreateCompatibleSurface(HDEV__ *,ulong,HPALETTE__ *,int,int,int,int,int,int,int,int,int,ulong,ulong,void *)

- ea: `0x140093cf4`
- end: `0x1400943cc`
- name: `?CreateCompatibleSurface@@YA?AVSURFREF@@PEAUHDEV__@@KPEAUHPALETTE__@@HHHHHHHHHKKPEAX@Z`
- size: `1752`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140093684`
- `0x1401a4fd8`
- `0x1401a5234`

## callees

- `0x14005fb0c`
- `0x14006a090`
- `0x1400923b8`
- `0x140093534`
- `0x140093cf4`
- `0x140134fe0`
- `0x140296924`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140093da9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140093f0c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140094036`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400941b3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140093da9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140093f0c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140094036`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400941b3`
- `win32kbase!HmgShareLock` at `0x14009404e`
- `win32kbase!HmgShareLock` at `0x1400941cb`
- `win32kbase!HmgShareLock` at `0x14009404e`
- `win32kbase!HmgShareLock` at `0x1400941cb`
- `win32kbase!PopThreadGuardedObject` at `0x140094083`
- `win32kbase!PopThreadGuardedObject` at `0x140094083`
- `win32kbase!PushThreadGuardedObject` at `0x140093ef7`
- `win32kbase!PushThreadGuardedObject` at `0x14009402a`
- `win32kbase!PushThreadGuardedObject` at `0x140093ef7`
- `win32kbase!PushThreadGuardedObject` at `0x14009402a`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140093f2f`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140093f2f`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140093e6d`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140093e6d`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140093f1f`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140093f1f`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400940e9`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14009422b`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400940e9`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14009422b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140093fe7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140094179`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400942d7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140093fe7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140094179`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400942d7`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x140093ed0`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x140094208`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x140093ed0`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x140094208`
- `WIN32K!W32GetSessionState` at `0x140093dbe`
- `WIN32K!W32GetSessionState` at `0x140093dbe`

## pseudocode

```c
__int64 __fastcall CreateCompatibleSurface(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        __int64 a16)
{
  unsigned int v17; // r12d
  __int64 v18; // rcx
  unsigned int v20; // r14d
  int v21; // eax
  bool v22; // zf
  __int64 v23; // rcx
  __int64 (__fastcall *v24)(_QWORD, unsigned __int64, _QWORD); // rax
  int v25; // eax
  __int64 v26; // rdi
  Gre::Base *v27; // rcx
  struct Gre::Base::SESSION_GLOBALS *v28; // rax
  __int64 v30; // rdi
  SURFACE *v31; // rax
  unsigned int v32; // ecx
  Gre::Base *v33; // rcx
  struct Gre::Base::SESSION_GLOBALS *v34; // rax
  __int64 v35; // r8
  SURFACE *v36; // rax
  Gre::Base *v37; // rcx
  int v38; // r12d
  unsigned int v39; // edi
  HSURF v40; // rax
  ThreadRestrictNewHandlesRegion *v41; // rcx
  __int64 v42; // rsi
  struct Gre::Base::SESSION_GLOBALS *v43; // rax
  __int64 v44; // r8
  __int64 v45; // rax
  unsigned int v46; // r12d
  HSURF v47; // rax
  int (*v48)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  _OWORD v49[2]; // [rsp+68h] [rbp-98h] BYREF
  SURFACE *v50; // [rsp+88h] [rbp-78h]
  unsigned __int64 v51; // [rsp+90h] [rbp-70h]
  unsigned int v52; // [rsp+98h] [rbp-68h]
  __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  char v55; // [rsp+B0h] [rbp-50h]
  _DWORD v56[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  __int64 v59; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v60; // [rsp+E8h] [rbp-18h]
  unsigned int v61; // [rsp+ECh] [rbp-14h]
  _BYTE v62[96]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v63[96]; // [rsp+150h] [rbp+50h] BYREF

  v17 = a5;
  v18 = 262145;
  v20 = a7;
  v53 = a16;
  v21 = 1;
  v58 = 1;
  v56[3] = 0;
  v56[1] = a5;
  v56[2] = a6;
  v57 = a4;
  v56[0] = a3;
  v22 = (*(_DWORD *)(a2 + 40) & 0x8000) == 0;
  v59 = a2;
  if ( !v22 )
    v21 = 262145;
  LODWORD(v58) = v21;
  if ( !a7 )
  {
    if ( !a9 )
      goto LABEL_11;
    v20 = bRemoteDriverNeedsDeviceBitmaps((struct PDEVOBJ *)&v59);
    if ( !v20 )
      goto LABEL_11;
  }
  if ( a9 )
  {
    v20 = 0;
    if ( *((_QWORD *)Gre::Base::Globals((Gre::Base *)v18) + 28) )
      v20 = *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v23) + 96) + 88LL);
    if ( !v20 )
      goto LABEL_11;
  }
  v51 = __PAIR64__(a6, a5);
  if ( a9 )
  {
    v38 = 87;
    if ( a14 )
      v38 = a14;
    if ( *(_QWORD *)(a2 + 3432) )
    {
      v59 = 0;
      v39 = (a12 != 0 ? 5 : 1) | 8;
      if ( !a13 )
        v39 = a12 != 0 ? 5 : 1;
      v52 = v39;
      ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v62);
      v40 = (HSURF)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, _QWORD, _QWORD, _DWORD, int, __int64 *))(a2 + 3432))(
                     *(_QWORD *)(a2 + 1784),
                     v51,
                     v56[0],
                     v39,
                     0,
                     0,
                     a15,
                     &v59);
      v30 = (__int64)v40;
      if ( v40 )
      {
        SURFREF::SURFREF((SURFREF *)v49, v40);
        v31 = v50;
        if ( !v50 )
        {
          UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
          *(_QWORD *)(a1 + 32) = 0;
          SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v49);
          v41 = (ThreadRestrictNewHandlesRegion *)v62;
LABEL_41:
          ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(v41);
          return a1;
        }
        if ( a13 )
        {
          *((_DWORD *)v50 + 41) |= 0x400u;
          v31 = v50;
        }
        *((_DWORD *)v31 + 41) |= 1u;
        *((_QWORD *)v50 + 77) = v59;
        v32 = v52;
        *((_DWORD *)v50 + 43) = v38;
        *((_DWORD *)v50 + 42) = v32;
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v49);
      }
      ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v62);
      if ( v30 )
        goto LABEL_27;
    }
    if ( !a10 )
      goto LABEL_11;
LABEL_52:
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
    return a1;
  }
  if ( !a11 )
  {
    v24 = *(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(a2 + 2760);
    if ( !v24 )
      goto LABEL_11;
    v30 = v24(*(_QWORD *)(a2 + 1784), v51, v56[0]);
    if ( !v30 )
      goto LABEL_11;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)(a2 + 3432) )
    goto LABEL_52;
  ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v63);
  v46 = a12 != 0 ? 6 : 2;
  v47 = (HSURF)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, _QWORD, _QWORD, int, int, __int64 *))(a2 + 3432))(
                 *(_QWORD *)(a2 + 1784),
                 v51,
                 v56[0],
                 v46,
                 0,
                 a14,
                 a15,
                 &v53);
  v30 = (__int64)v47;
  if ( !v47 )
    goto LABEL_51;
  SURFREF::SURFREF((SURFREF *)v49, v47);
  if ( !v50 )
  {
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v49);
    v41 = (ThreadRestrictNewHandlesRegion *)v63;
    goto LABEL_41;
  }
  *((_DWORD *)v50 + 41) |= 8u;
  *((_QWORD *)v50 + 77) = v53;
  *((_DWORD *)v50 + 42) = v46;
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v49);
LABEL_51:
  ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v63);
  if ( !v30 )
    goto LABEL_52;
LABEL_27:
  v17 = a5;
LABEL_28:
  if ( (_DWORD)v30 != -1 )
  {
    memset(v49, 0, sizeof(v49));
    PushThreadGuardedObject(
      v49,
      v49,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v34 = Gre::Base::Globals(v33);
    LOBYTE(v35) = 5;
    v36 = (SURFACE *)HmgShareLock(v34, v30, v35, 0);
    v50 = v36;
    if ( v36 )
    {
      *((_DWORD *)v36 + 40) |= 0x800000u;
      *((_DWORD *)v50 + 40) |= 0x4000000u;
      *((_DWORD *)v50 + 40) |= 0x4000u;
      v42 = v57;
      if ( v57 )
      {
        v43 = Gre::Base::Globals(v37);
        LOBYTE(v44) = 8;
        v45 = HmgShareLock(v43, v42, v44, 0);
        if ( v45 )
          *((_QWORD *)v50 + 22) = v45;
      }
      if ( !a9 && (!a11 || !v53) )
      {
        v61 = a6;
        v59 = 0;
        v60 = v17;
        v48 = SURFACE::pfnBitBlt(v50);
        ((void (__fastcall *)(unsigned __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v48)(
          ((unsigned __int64)v50 + 24) & -(__int64)(v50 != 0),
          0,
          0,
          0,
          0,
          &v59,
          0,
          0,
          0,
          0,
          0);
      }
      EtwPhysicalSurfCreateEvent(v30, 1, *((_QWORD *)v50 + 77), 1);
    }
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = v50;
    v50 = 0;
    PopThreadGuardedObject(v49);
    return a1;
  }
LABEL_11:
  v25 = 1;
  if ( !a9 )
    v25 = a8;
  LODWORD(v58) = (v25 != 0 ? 0x800 : 0) | v58;
  SURFMEM::SURFMEM(&v54, 4);
  SURFMEM::bCreateDIB((SURFMEM *)&v54, (struct _DEVBITMAPINFO *)v56, 0, 0, 0, 0, 0, 0, 1, 0);
  if ( v54 )
  {
    v55 |= 1u;
    *(_DWORD *)(v54 + 160) |= 0x800000u;
    *(_DWORD *)(v54 + 160) |= 0x4000000u;
    *(_QWORD *)(v54 + 48) = a2;
    if ( *(_QWORD *)(v54 + 296) )
      *(_DWORD *)(v54 + 160) |= 0x4000u;
    else
      *(_DWORD *)(v54 + 160) |= 0x200u;
    EtwPhysicalSurfCreateEvent(*(_QWORD *)(v54 + 32), 0, 0, v20);
    v26 = v54;
    *(_OWORD *)a1 = 0;
    *(_OWORD *)(a1 + 16) = 0;
    PushThreadGuardedObject(
      a1,
      a1,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    if ( v26 )
    {
      *(_QWORD *)(a1 + 32) = v26;
      v28 = Gre::Base::Globals(v27);
      INC_SHARE_REF_CNT(v28, *(_QWORD *)(a1 + 32));
    }
  }
  else
  {
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
  }
  SURFMEM::~SURFMEM((SURFMEM *)&v54);
  return a1;
}

```

## disassembly

```asm
0x140093cf4  push    rbp
0x140093cf6  push    rbx
0x140093cf7  push    rsi
0x140093cf8  push    rdi
0x140093cf9  push    r12
0x140093cfb  push    r13
0x140093cfd  push    r14
0x140093cff  push    r15
0x140093d01  lea     rbp, [rsp-0C8h]
0x140093d09  sub     rsp, 1C8h
0x140093d10  mov     rax, cs:__security_cookie
0x140093d17  xor     rax, rsp
0x140093d1a  mov     [rbp+100h+var_50], rax
0x140093d21  mov     eax, [rbp+100h+arg_70]
0x140093d27  mov     rbx, rcx
0x140093d2a  mov     r12d, [rbp+100h+arg_20]
0x140093d31  mov     ecx, 40001h
0x140093d36  mov     r13d, [rbp+100h+arg_28]
0x140093d3d  mov     rsi, rdx
0x140093d40  mov     r14d, [rbp+100h+arg_30]
0x140093d47  mov     edi, [rbp+100h+arg_68]
0x140093d4d  mov     r15d, [rbp+100h+arg_40]
0x140093d54  mov     [rsp+200h+var_1A0], eax
0x140093d58  mov     rax, [rbp+100h+arg_78]
0x140093d5f  mov     [rbp+100h+var_160], rax
0x140093d63  mov     eax, 1
0x140093d68  mov     [rbp+100h+var_128], 1
0x140093d70  mov     [rbp+100h+var_134], 0
0x140093d77  mov     [rbp+100h+var_13C], r12d
0x140093d7b  mov     [rbp+100h+var_138], r13d
0x140093d7f  mov     [rbp+100h+var_130], r9
0x140093d83  mov     [rbp+100h+var_140], r8d
0x140093d87  test    dword ptr [rdx+28h], 8000h
0x140093d8e  mov     [rbp+100h+var_120], rdx
0x140093d92  cmovnz  eax, ecx
0x140093d95  mov     dword ptr [rbp+100h+var_128], eax
0x140093d98  test    r14d, r14d
0x140093d9b  jz      loc_1400943AA
0x140093da1  test    r15d, r15d
0x140093da4  jz      short loc_140093DD7
0x140093da6  xor     r14d, r14d
0x140093da9  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140093db0  nop     dword ptr [rax+rax+00h]
0x140093db5  cmp     [rax+0E0h], r14
0x140093dbc  jz      short loc_140093DD2
0x140093dbe  call    cs:__imp_W32GetSessionState
0x140093dc5  nop     dword ptr [rax+rax+00h]
0x140093dca  mov     rcx, [rax+60h]
0x140093dce  mov     r14d, [rcx+58h]
0x140093dd2  test    r14d, r14d
0x140093dd5  jz      short loc_140093E08
0x140093dd7  mov     dword ptr [rbp+100h+var_170+4], r13d
0x140093ddb  mov     r13d, [rbp+100h+arg_50]
0x140093de2  mov     dword ptr [rbp+100h+var_170], r12d
0x140093de6  test    r15d, r15d
0x140093de9  jnz     loc_140094094
0x140093def  test    r13d, r13d
0x140093df2  jnz     loc_140094219
0x140093df8  mov     rax, [rsi+0AC8h]
0x140093dff  test    rax, rax
0x140093e02  jnz     loc_140093F74
0x140093e08  mov     edi, 1
0x140093e0d  lea     rcx, [rbp+100h+var_158]
0x140093e11  test    r15d, r15d
0x140093e14  mov     eax, edi
0x140093e16  cmovz   eax, [rbp+100h+arg_38]
0x140093e1d  neg     eax
0x140093e1f  lea     edx, [rdi+3]
0x140093e22  sbb     eax, eax
0x140093e24  and     eax, 800h
0x140093e29  or      dword ptr [rbp+100h+var_128], eax
0x140093e2c  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x140093e31  mov     dword ptr [rsp+200h+var_1B8], 0
0x140093e39  lea     rdx, [rbp+100h+var_140]
0x140093e3d  mov     dword ptr [rsp+200h+var_1C0], edi
0x140093e41  lea     rcx, [rbp+100h+var_158]
0x140093e45  mov     dword ptr [rsp+200h+var_1C8], 0
0x140093e4d  xor     r9d, r9d
0x140093e50  mov     [rsp+200h+var_1D0], 0
0x140093e59  xor     r8d, r8d
0x140093e5c  mov     [rsp+200h+var_1D8], 0
0x140093e65  mov     dword ptr [rsp+200h+var_1E0], 0
0x140093e6d  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x140093e74  nop     dword ptr [rax+rax+00h]
0x140093e79  mov     rax, [rbp+100h+var_158]
0x140093e7d  test    rax, rax
0x140093e80  jz      loc_140093F62
0x140093e86  or      [rbp+100h+var_150], dil
0x140093e8a  bts     dword ptr [rax+0A0h], 17h
0x140093e92  mov     rax, [rbp+100h+var_158]
0x140093e96  bts     dword ptr [rax+0A0h], 1Ah
0x140093e9e  mov     rax, [rbp+100h+var_158]
0x140093ea2  mov     [rax+30h], rsi
0x140093ea6  mov     rax, [rbp+100h+var_158]
0x140093eaa  cmp     qword ptr [rax+128h], 0
0x140093eb2  jnz     loc_14009439D
0x140093eb8  bts     dword ptr [rax+0A0h], 9
0x140093ec0  mov     rcx, [rbp+100h+var_158]
0x140093ec4  mov     r9d, r14d
0x140093ec7  xor     r8d, r8d
0x140093eca  xor     edx, edx
0x140093ecc  mov     rcx, [rcx+20h]
0x140093ed0  call    cs:__imp_EtwPhysicalSurfCreateEvent
0x140093ed7  nop     dword ptr [rax+rax+00h]
0x140093edc  mov     rdi, [rbp+100h+var_158]
0x140093ee0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140093ee7  xorps   xmm0, xmm0
0x140093eea  mov     rdx, rbx
0x140093eed  movups  xmmword ptr [rbx], xmm0
0x140093ef0  mov     rcx, rbx
0x140093ef3  movups  xmmword ptr [rbx+10h], xmm0
0x140093ef7  call    cs:__imp_PushThreadGuardedObject
0x140093efe  nop     dword ptr [rax+rax+00h]
0x140093f03  test    rdi, rdi
0x140093f06  jz      short loc_140093F2B
0x140093f08  mov     [rbx+20h], rdi
0x140093f0c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140093f13  nop     dword ptr [rax+rax+00h]
0x140093f18  mov     rdx, [rbx+20h]
0x140093f1c  mov     rcx, rax
0x140093f1f  call    cs:__imp_INC_SHARE_REF_CNT
0x140093f26  nop     dword ptr [rax+rax+00h]
0x140093f2b  lea     rcx, [rbp+100h+var_158]
0x140093f2f  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x140093f36  nop     dword ptr [rax+rax+00h]
0x140093f3b  mov     rax, rbx
0x140093f3e  mov     rcx, [rbp+100h+var_50]
0x140093f45  xor     rcx, rsp; StackCookie
0x140093f48  call    __security_check_cookie
0x140093f4d  add     rsp, 1C8h
0x140093f54  pop     r15
0x140093f56  pop     r14
0x140093f58  pop     r13
0x140093f5a  pop     r12
0x140093f5c  pop     rdi
0x140093f5d  pop     rsi
0x140093f5e  pop     rbx
0x140093f5f  pop     rbp
0x140093f60  retn
0x140093f62  mov     rcx, rbx
0x140093f65  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x140093f6a  mov     qword ptr [rbx+20h], 0
0x140093f72  jmp     short loc_140093F2B
0x140093f74  mov     r8d, [rbp+100h+var_140]
0x140093f78  mov     rdx, [rbp+100h+var_170]
0x140093f7c  mov     rcx, [rsi+6F8h]
0x140093f83  call    _guard_dispatch_icall
0x140093f88  mov     rdi, rax
0x140093f8b  test    rax, rax
0x140093f8e  jz      loc_140093E08
0x140093f94  jmp     short loc_140094003
0x140093f96  cmp     [rbp+100h+arg_60], 0
0x140093f9d  jz      short loc_140093FAB
0x140093f9f  bts     dword ptr [rax+0A4h], 0Ah
0x140093fa7  mov     rax, [rbp+100h+var_178]
0x140093fab  or      dword ptr [rax+0A4h], 1
0x140093fb2  mov     rcx, [rbp+100h+var_120]
0x140093fb6  mov     rax, [rbp+100h+var_178]
0x140093fba  mov     [rax+268h], rcx
0x140093fc1  mov     rax, [rbp+100h+var_178]
0x140093fc5  mov     ecx, [rbp+100h+var_168]
0x140093fc8  mov     [rax+0ACh], r12d
0x140093fcf  mov     rax, [rbp+100h+var_178]
0x140093fd3  mov     [rax+0A8h], ecx
0x140093fd9  lea     rcx, [rsp+200h+var_198]; this
0x140093fde  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140093fe3  lea     rcx, [rbp+100h+var_110]
0x140093fe7  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140093fee  nop     dword ptr [rax+rax+00h]
0x140093ff3  test    rdi, rdi
0x140093ff6  jz      loc_1400940AA
0x140093ffc  mov     r12d, [rbp+100h+arg_20]
0x140094003  cmp     edi, 0FFFFFFFFh
0x140094006  jz      loc_140093E08
0x14009400c  xorps   xmm0, xmm0
0x14009400f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140094016  lea     rdx, [rsp+200h+var_198]
0x14009401b  lea     rcx, [rsp+200h+var_198]
0x140094020  movups  [rsp+200h+var_198], xmm0
0x140094025  movups  [rsp+200h+var_188], xmm0
0x14009402a  call    cs:__imp_PushThreadGuardedObject
0x140094031  nop     dword ptr [rax+rax+00h]
0x140094036  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14009403d  nop     dword ptr [rax+rax+00h]
0x140094042  xor     r9d, r9d
0x140094045  mov     r8b, 5
0x140094048  mov     rcx, rax
0x14009404b  mov     rdx, rdi
0x14009404e  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140094055  nop     dword ptr [rax+rax+00h]
0x14009405a  xor     r14d, r14d
0x14009405d  mov     [rbp+100h+var_178], rax
0x140094061  test    rax, rax
0x140094064  jnz     loc_14009418A
0x14009406a  mov     rcx, rbx
0x14009406d  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x140094072  mov     rax, [rbp+100h+var_178]
0x140094076  lea     rcx, [rsp+200h+var_198]
0x14009407b  mov     [rbx+20h], rax
0x14009407f  mov     [rbp+100h+var_178], r14
0x140094083  call    cs:__imp_PopThreadGuardedObject
0x14009408a  nop     dword ptr [rax+rax+00h]
0x14009408f  jmp     loc_140093F3B
0x140094094  test    edi, edi
0x140094096  mov     r12d, 57h ; 'W'
0x14009409c  cmovnz  r12d, edi
0x1400940a0  cmp     qword ptr [rsi+0D68h], 0
0x1400940a8  jnz     short loc_1400940BC
0x1400940aa  cmp     [rbp+100h+arg_48], 0
0x1400940b1  jz      loc_140093E08
0x1400940b7  jmp     loc_1400942EC
0x1400940bc  mov     eax, [rbp+100h+arg_58]
0x1400940c2  neg     eax
0x1400940c4  mov     [rbp+100h+var_120], 0
0x1400940cc  sbb     ecx, ecx
0x1400940ce  and     ecx, 4
0x1400940d1  inc     ecx
0x1400940d3  mov     edi, ecx
0x1400940d5  or      edi, 8
0x1400940d8  cmp     [rbp+100h+arg_60], 0
0x1400940df  cmovz   edi, ecx
0x1400940e2  lea     rcx, [rbp+100h+var_110]
0x1400940e6  mov     [rbp+100h+var_168], edi
0x1400940e9  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x1400940f0  nop     dword ptr [rax+rax+00h]
0x1400940f5  mov     rax, [rsi+0D68h]
0x1400940fc  lea     rcx, [rbp+100h+var_120]
0x140094100  mov     r8d, [rbp+100h+var_140]
0x140094104  mov     r9d, edi
0x140094107  mov     rdx, [rbp+100h+var_170]
0x14009410b  mov     [rsp+200h+var_1C8], rcx
0x140094110  mov     ecx, [rsp+200h+var_1A0]
0x140094114  mov     dword ptr [rsp+200h+var_1D0], ecx
0x140094118  mov     rcx, [rsi+6F8h]
0x14009411f  mov     dword ptr [rsp+200h+var_1D8], 0
0x140094127  mov     [rsp+200h+var_1E0], 0
0x140094130  call    _guard_dispatch_icall
0x140094135  mov     rdi, rax
0x140094138  test    rax, rax
0x14009413b  jz      loc_140093FE3
0x140094141  mov     rdx, rax; HSURF
0x140094144  lea     rcx, [rsp+200h+var_198]; this
0x140094149  call    ??0SURFREF@@QEAA@PEAUHSURF__@@@Z; SURFREF::SURFREF(HSURF__ *)
0x14009414e  mov     rax, [rbp+100h+var_178]
0x140094152  test    rax, rax
0x140094155  jnz     loc_140093F96
0x14009415b  mov     rcx, rbx
0x14009415e  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x140094163  lea     rcx, [rsp+200h+var_198]; this
0x140094168  mov     qword ptr [rbx+20h], 0
0x140094170  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140094175  lea     rcx, [rbp+100h+var_110]
0x140094179  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140094180  nop     dword ptr [rax+rax+00h]
0x140094185  jmp     loc_140093F3B
0x14009418a  bts     dword ptr [rax+0A0h], 17h
0x140094192  mov     rax, [rbp+100h+var_178]
0x140094196  bts     dword ptr [rax+0A0h], 1Ah
0x14009419e  mov     rax, [rbp+100h+var_178]
0x1400941a2  bts     dword ptr [rax+0A0h], 0Eh
0x1400941aa  mov     rsi, [rbp+100h+var_130]
0x1400941ae  test    rsi, rsi
0x1400941b1  jz      short loc_1400941E7
0x1400941b3  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400941ba  nop     dword ptr [rax+rax+00h]
0x1400941bf  xor     r9d, r9d
0x1400941c2  mov     r8b, 8
0x1400941c5  mov     rcx, rax
0x1400941c8  mov     rdx, rsi
0x1400941cb  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400941d2  nop     dword ptr [rax+rax+00h]
0x1400941d7  test    rax, rax
0x1400941da  jz      short loc_1400941E7
0x1400941dc  mov     rcx, [rbp+100h+var_178]
0x1400941e0  mov     [rcx+0B0h], rax
0x1400941e7  test    r15d, r15d
0x1400941ea  jz      loc_140094301
0x1400941f0  mov     r8, [rbp+100h+var_178]
0x1400941f4  mov     eax, 1
0x1400941f9  mov     r9d, eax
0x1400941fc  mov     edx, eax
0x1400941fe  mov     rcx, rdi
0x140094201  mov     r8, [r8+268h]
0x140094208  call    cs:__imp_EtwPhysicalSurfCreateEvent
0x14009420f  nop     dword ptr [rax+rax+00h]
0x140094214  jmp     loc_14009406A
0x140094219  cmp     qword ptr [rsi+0D68h], 0
0x140094221  jz      loc_1400942EC
0x140094227  lea     rcx, [rbp+100h+var_B0]
0x14009422b  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x140094232  nop     dword ptr [rax+rax+00h]
0x140094237  mov     eax, [rbp+100h+arg_58]
0x14009423d  lea     rcx, [rbp+100h+var_160]
0x140094241  mov     r8d, [rbp+100h+var_140]
0x140094245  neg     eax
0x140094247  mov     rax, [rsi+0D68h]
0x14009424e  mov     rdx, [rbp+100h+var_170]
0x140094252  sbb     r12d, r12d
0x140094255  mov     [rsp+200h+var_1C8], rcx
0x14009425a  and     r12d, 4
  ... truncated ...
```
