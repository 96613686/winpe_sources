# CreateCompatibleSurface(HDEV__ *,ulong,HPALETTE__ *,int,int,int,int,int,int,int,int,int,ulong,ulong,void *)

- ea: `0x1400aa304`
- end: `0x1400aa9dc`
- name: `?CreateCompatibleSurface@@YA?AVSURFREF@@PEAUHDEV__@@KPEAUHPALETTE__@@HHHHHHHHHKKPEAX@Z`
- size: `1752`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, unsigned int, unsigned int, unsigned int, int, int, int, int, int, int, int, int, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a9c94`
- `0x140120928`
- `0x140120b84`

## callees

- `0x14006b59c`
- `0x14009a40c`
- `0x1400a9b38`
- `0x1400aa304`
- `0x140112588`
- `0x140120e28`
- `0x140298e04`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa3b9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa51c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa646`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa7c3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa3b9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa51c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa646`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400aa7c3`
- `win32kbase!HmgShareLock` at `0x1400aa65e`
- `win32kbase!HmgShareLock` at `0x1400aa7db`
- `win32kbase!HmgShareLock` at `0x1400aa65e`
- `win32kbase!HmgShareLock` at `0x1400aa7db`
- `win32kbase!PopThreadGuardedObject` at `0x1400aa693`
- `win32kbase!PopThreadGuardedObject` at `0x1400aa693`
- `win32kbase!PushThreadGuardedObject` at `0x1400aa507`
- `win32kbase!PushThreadGuardedObject` at `0x1400aa63a`
- `win32kbase!PushThreadGuardedObject` at `0x1400aa507`
- `win32kbase!PushThreadGuardedObject` at `0x1400aa63a`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400aa53f`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400aa53f`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400aa47d`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400aa47d`
- `win32kbase!INC_SHARE_REF_CNT` at `0x1400aa52f`
- `win32kbase!INC_SHARE_REF_CNT` at `0x1400aa52f`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa6f9`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa83b`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa6f9`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa83b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa5f7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa789`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa8e7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa5f7`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa789`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1400aa8e7`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x1400aa4e0`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x1400aa818`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x1400aa4e0`
- `win32kbase!EtwPhysicalSurfCreateEvent` at `0x1400aa818`
- `WIN32K!W32GetSessionState` at `0x1400aa3ce`
- `WIN32K!W32GetSessionState` at `0x1400aa3ce`

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
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 (__fastcall *v27)(_QWORD, unsigned __int64, _QWORD); // rax
  int v28; // eax
  __int64 v29; // rdi
  Gre::Base *v30; // rcx
  struct Gre::Base::SESSION_GLOBALS *v31; // rax
  __int64 v33; // rdi
  SURFACE *v34; // rax
  unsigned int v35; // ecx
  Gre::Base *v36; // rcx
  struct Gre::Base::SESSION_GLOBALS *v37; // rax
  __int64 v38; // r8
  SURFACE *v39; // rax
  Gre::Base *v40; // rcx
  int v41; // r12d
  unsigned int v42; // edi
  HSURF v43; // rax
  ThreadRestrictNewHandlesRegion *v44; // rcx
  __int64 v45; // rsi
  struct Gre::Base::SESSION_GLOBALS *v46; // rax
  __int64 v47; // r8
  __int64 v48; // rax
  unsigned int v49; // r12d
  HSURF v50; // rax
  int (*v51)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // rax
  _OWORD v52[2]; // [rsp+68h] [rbp-98h] BYREF
  SURFACE *v53; // [rsp+88h] [rbp-78h]
  unsigned __int64 v54; // [rsp+90h] [rbp-70h]
  unsigned int v55; // [rsp+98h] [rbp-68h]
  __int64 v56; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-58h] BYREF
  char v58; // [rsp+B0h] [rbp-50h]
  _DWORD v59[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h]
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v63; // [rsp+E8h] [rbp-18h]
  unsigned int v64; // [rsp+ECh] [rbp-14h]
  _BYTE v65[96]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v66[96]; // [rsp+150h] [rbp+50h] BYREF

  v17 = a5;
  v18 = 262145;
  v20 = a7;
  v56 = a16;
  v21 = 1;
  v61 = 1;
  v59[3] = 0;
  v59[1] = a5;
  v59[2] = a6;
  v60 = a4;
  v59[0] = a3;
  v22 = (*(_DWORD *)(a2 + 40) & 0x8000) == 0;
  v62 = a2;
  if ( !v22 )
    v21 = 262145;
  LODWORD(v61) = v21;
  if ( !a7 )
  {
    if ( !a9 )
      goto LABEL_11;
    v20 = bRemoteDriverNeedsDeviceBitmaps((struct PDEVOBJ *)&v62);
    if ( !v20 )
      goto LABEL_11;
  }
  if ( a9 )
  {
    v20 = 0;
    if ( *((_QWORD *)Gre::Base::Globals((Gre::Base *)v18) + 28) )
      v20 = *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v24, v23, v25, v26) + 96) + 88LL);
    if ( !v20 )
      goto LABEL_11;
  }
  v54 = __PAIR64__(a6, a5);
  if ( a9 )
  {
    v41 = 87;
    if ( a14 )
      v41 = a14;
    if ( *(_QWORD *)(a2 + 3432) )
    {
      v62 = 0;
      v42 = (a12 != 0 ? 5 : 1) | 8;
      if ( !a13 )
        v42 = a12 != 0 ? 5 : 1;
      v55 = v42;
      ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v65);
      v43 = (HSURF)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, _QWORD, _QWORD, _DWORD, int, __int64 *))(a2 + 3432))(
                     *(_QWORD *)(a2 + 1784),
                     v54,
                     v59[0],
                     v42,
                     0,
                     0,
                     a15,
                     &v62);
      v33 = (__int64)v43;
      if ( v43 )
      {
        SURFREF::SURFREF((SURFREF *)v52, v43);
        v34 = v53;
        if ( !v53 )
        {
          UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>((_OWORD *)a1);
          *(_QWORD *)(a1 + 32) = 0;
          SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
          v44 = (ThreadRestrictNewHandlesRegion *)v65;
LABEL_41:
          ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(v44);
          return a1;
        }
        if ( a13 )
        {
          *((_DWORD *)v53 + 37) |= 0x400u;
          v34 = v53;
        }
        *((_DWORD *)v34 + 37) |= 1u;
        *((_QWORD *)v53 + 75) = v62;
        v35 = v55;
        *((_DWORD *)v53 + 39) = v41;
        *((_DWORD *)v53 + 38) = v35;
        SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
      }
      ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v65);
      if ( v33 )
        goto LABEL_27;
    }
    if ( !a10 )
      goto LABEL_11;
LABEL_52:
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>((_OWORD *)a1);
    *(_QWORD *)(a1 + 32) = 0;
    return a1;
  }
  if ( !a11 )
  {
    v27 = *(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(a2 + 2760);
    if ( !v27 )
      goto LABEL_11;
    v33 = v27(*(_QWORD *)(a2 + 1784), v54, v59[0]);
    if ( !v33 )
      goto LABEL_11;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)(a2 + 3432) )
    goto LABEL_52;
  ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v66);
  v49 = a12 != 0 ? 6 : 2;
  v50 = (HSURF)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, _QWORD, _QWORD, int, int, __int64 *))(a2 + 3432))(
                 *(_QWORD *)(a2 + 1784),
                 v54,
                 v59[0],
                 v49,
                 0,
                 a14,
                 a15,
                 &v56);
  v33 = (__int64)v50;
  if ( !v50 )
    goto LABEL_51;
  SURFREF::SURFREF((SURFREF *)v52, v50);
  if ( !v53 )
  {
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>((_OWORD *)a1);
    *(_QWORD *)(a1 + 32) = 0;
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
    v44 = (ThreadRestrictNewHandlesRegion *)v66;
    goto LABEL_41;
  }
  *((_DWORD *)v53 + 37) |= 8u;
  *((_QWORD *)v53 + 75) = v56;
  *((_DWORD *)v53 + 38) = v49;
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
LABEL_51:
  ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v66);
  if ( !v33 )
    goto LABEL_52;
LABEL_27:
  v17 = a5;
LABEL_28:
  if ( (_DWORD)v33 != -1 )
  {
    memset(v52, 0, sizeof(v52));
    PushThreadGuardedObject(
      v52,
      v52,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v37 = Gre::Base::Globals(v36);
    LOBYTE(v38) = 5;
    v39 = (SURFACE *)HmgShareLock(v37, v33, v38, 0);
    v53 = v39;
    if ( v39 )
    {
      *((_DWORD *)v39 + 36) |= 0x800000u;
      *((_DWORD *)v53 + 36) |= 0x4000000u;
      *((_DWORD *)v53 + 36) |= 0x4000u;
      v45 = v60;
      if ( v60 )
      {
        v46 = Gre::Base::Globals(v40);
        LOBYTE(v47) = 8;
        v48 = HmgShareLock(v46, v45, v47, 0);
        if ( v48 )
          *((_QWORD *)v53 + 20) = v48;
      }
      if ( !a9 && (!a11 || !v56) )
      {
        v64 = a6;
        v62 = 0;
        v63 = v17;
        v51 = SURFACE::pfnBitBlt(v53);
        ((void (__fastcall *)(unsigned __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v51)(
          ((unsigned __int64)v53 + 24) & -(__int64)(v53 != 0),
          0,
          0,
          0,
          0,
          &v62,
          0,
          0,
          0,
          0,
          0);
      }
      EtwPhysicalSurfCreateEvent(v33, 1, *((_QWORD *)v53 + 75), 1);
    }
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>((_OWORD *)a1);
    *(_QWORD *)(a1 + 32) = v53;
    v53 = 0;
    PopThreadGuardedObject(v52);
    return a1;
  }
LABEL_11:
  v28 = 1;
  if ( !a9 )
    v28 = a8;
  LODWORD(v61) = (v28 != 0 ? 0x800 : 0) | v61;
  SURFMEM::SURFMEM(&v57, 3);
  SURFMEM::bCreateDIB((SURFMEM *)&v57, (struct _DEVBITMAPINFO *)v59, 0, 0, 0, 0, 0, 0, 1, 0);
  if ( v57 )
  {
    v58 |= 1u;
    *(_DWORD *)(v57 + 144) |= 0x800000u;
    *(_DWORD *)(v57 + 144) |= 0x4000000u;
    *(_QWORD *)(v57 + 48) = a2;
    if ( *(_QWORD *)(v57 + 280) )
      *(_DWORD *)(v57 + 144) |= 0x4000u;
    else
      *(_DWORD *)(v57 + 144) |= 0x200u;
    EtwPhysicalSurfCreateEvent(*(_QWORD *)(v57 + 32), 0, 0, v20);
    v29 = v57;
    *(_OWORD *)a1 = 0;
    *(_OWORD *)(a1 + 16) = 0;
    PushThreadGuardedObject(
      a1,
      a1,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    if ( v29 )
    {
      *(_QWORD *)(a1 + 32) = v29;
      v31 = Gre::Base::Globals(v30);
      INC_SHARE_REF_CNT(v31, *(_QWORD *)(a1 + 32));
    }
  }
  else
  {
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>((_OWORD *)a1);
    *(_QWORD *)(a1 + 32) = 0;
  }
  SURFMEM::~SURFMEM((SURFMEM *)&v57);
  return a1;
}

```

## disassembly

```asm
0x1400aa304  push    rbp
0x1400aa306  push    rbx
0x1400aa307  push    rsi
0x1400aa308  push    rdi
0x1400aa309  push    r12
0x1400aa30b  push    r13
0x1400aa30d  push    r14
0x1400aa30f  push    r15
0x1400aa311  lea     rbp, [rsp-0C8h]
0x1400aa319  sub     rsp, 1C8h
0x1400aa320  mov     rax, cs:__security_cookie
0x1400aa327  xor     rax, rsp
0x1400aa32a  mov     [rbp+100h+var_50], rax
0x1400aa331  mov     eax, [rbp+100h+arg_70]
0x1400aa337  mov     rbx, rcx
0x1400aa33a  mov     r12d, [rbp+100h+arg_20]
0x1400aa341  mov     ecx, 40001h
0x1400aa346  mov     r13d, [rbp+100h+arg_28]
0x1400aa34d  mov     rsi, rdx
0x1400aa350  mov     r14d, [rbp+100h+arg_30]
0x1400aa357  mov     edi, [rbp+100h+arg_68]
0x1400aa35d  mov     r15d, [rbp+100h+arg_40]
0x1400aa364  mov     [rsp+200h+var_1A0], eax
0x1400aa368  mov     rax, [rbp+100h+arg_78]
0x1400aa36f  mov     [rbp+100h+var_160], rax
0x1400aa373  mov     eax, 1
0x1400aa378  mov     [rbp+100h+var_128], 1
0x1400aa380  mov     [rbp+100h+var_134], 0
0x1400aa387  mov     [rbp+100h+var_13C], r12d
0x1400aa38b  mov     [rbp+100h+var_138], r13d
0x1400aa38f  mov     [rbp+100h+var_130], r9
0x1400aa393  mov     [rbp+100h+var_140], r8d
0x1400aa397  test    dword ptr [rdx+28h], 8000h
0x1400aa39e  mov     [rbp+100h+var_120], rdx
0x1400aa3a2  cmovnz  eax, ecx
0x1400aa3a5  mov     dword ptr [rbp+100h+var_128], eax
0x1400aa3a8  test    r14d, r14d
0x1400aa3ab  jz      loc_1400AA9BA
0x1400aa3b1  test    r15d, r15d
0x1400aa3b4  jz      short loc_1400AA3E7
0x1400aa3b6  xor     r14d, r14d
0x1400aa3b9  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400aa3c0  nop     dword ptr [rax+rax+00h]
0x1400aa3c5  cmp     [rax+0E0h], r14
0x1400aa3cc  jz      short loc_1400AA3E2
0x1400aa3ce  call    cs:__imp_W32GetSessionState
0x1400aa3d5  nop     dword ptr [rax+rax+00h]
0x1400aa3da  mov     rcx, [rax+60h]
0x1400aa3de  mov     r14d, [rcx+58h]
0x1400aa3e2  test    r14d, r14d
0x1400aa3e5  jz      short loc_1400AA418
0x1400aa3e7  mov     dword ptr [rbp+100h+var_170+4], r13d
0x1400aa3eb  mov     r13d, [rbp+100h+arg_50]
0x1400aa3f2  mov     dword ptr [rbp+100h+var_170], r12d
0x1400aa3f6  test    r15d, r15d
0x1400aa3f9  jnz     loc_1400AA6A4
0x1400aa3ff  test    r13d, r13d
0x1400aa402  jnz     loc_1400AA829
0x1400aa408  mov     rax, [rsi+0AC8h]
0x1400aa40f  test    rax, rax
0x1400aa412  jnz     loc_1400AA584
0x1400aa418  mov     edi, 1
0x1400aa41d  lea     rcx, [rbp+100h+var_158]
0x1400aa421  test    r15d, r15d
0x1400aa424  mov     eax, edi
0x1400aa426  cmovz   eax, [rbp+100h+arg_38]
0x1400aa42d  neg     eax
0x1400aa42f  lea     edx, [rdi+2]
0x1400aa432  sbb     eax, eax
0x1400aa434  and     eax, 800h
0x1400aa439  or      dword ptr [rbp+100h+var_128], eax
0x1400aa43c  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400aa441  mov     dword ptr [rsp+200h+var_1B8], 0
0x1400aa449  lea     rdx, [rbp+100h+var_140]
0x1400aa44d  mov     dword ptr [rsp+200h+var_1C0], edi
0x1400aa451  lea     rcx, [rbp+100h+var_158]
0x1400aa455  mov     dword ptr [rsp+200h+var_1C8], 0
0x1400aa45d  xor     r9d, r9d
0x1400aa460  mov     [rsp+200h+var_1D0], 0
0x1400aa469  xor     r8d, r8d
0x1400aa46c  mov     [rsp+200h+var_1D8], 0
0x1400aa475  mov     dword ptr [rsp+200h+var_1E0], 0
0x1400aa47d  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x1400aa484  nop     dword ptr [rax+rax+00h]
0x1400aa489  mov     rax, [rbp+100h+var_158]
0x1400aa48d  test    rax, rax
0x1400aa490  jz      loc_1400AA572
0x1400aa496  or      [rbp+100h+var_150], dil
0x1400aa49a  bts     dword ptr [rax+90h], 17h
0x1400aa4a2  mov     rax, [rbp+100h+var_158]
0x1400aa4a6  bts     dword ptr [rax+90h], 1Ah
0x1400aa4ae  mov     rax, [rbp+100h+var_158]
0x1400aa4b2  mov     [rax+30h], rsi
0x1400aa4b6  mov     rax, [rbp+100h+var_158]
0x1400aa4ba  cmp     qword ptr [rax+118h], 0
0x1400aa4c2  jnz     loc_1400AA9AD
0x1400aa4c8  bts     dword ptr [rax+90h], 9
0x1400aa4d0  mov     rcx, [rbp+100h+var_158]
0x1400aa4d4  mov     r9d, r14d
0x1400aa4d7  xor     r8d, r8d
0x1400aa4da  xor     edx, edx
0x1400aa4dc  mov     rcx, [rcx+20h]
0x1400aa4e0  call    cs:__imp_EtwPhysicalSurfCreateEvent
0x1400aa4e7  nop     dword ptr [rax+rax+00h]
0x1400aa4ec  mov     rdi, [rbp+100h+var_158]
0x1400aa4f0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400aa4f7  xorps   xmm0, xmm0
0x1400aa4fa  mov     rdx, rbx
0x1400aa4fd  movups  xmmword ptr [rbx], xmm0
0x1400aa500  mov     rcx, rbx
0x1400aa503  movups  xmmword ptr [rbx+10h], xmm0
0x1400aa507  call    cs:__imp_PushThreadGuardedObject
0x1400aa50e  nop     dword ptr [rax+rax+00h]
0x1400aa513  test    rdi, rdi
0x1400aa516  jz      short loc_1400AA53B
0x1400aa518  mov     [rbx+20h], rdi
0x1400aa51c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400aa523  nop     dword ptr [rax+rax+00h]
0x1400aa528  mov     rdx, [rbx+20h]
0x1400aa52c  mov     rcx, rax
0x1400aa52f  call    cs:__imp_INC_SHARE_REF_CNT
0x1400aa536  nop     dword ptr [rax+rax+00h]
0x1400aa53b  lea     rcx, [rbp+100h+var_158]
0x1400aa53f  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x1400aa546  nop     dword ptr [rax+rax+00h]
0x1400aa54b  mov     rax, rbx
0x1400aa54e  mov     rcx, [rbp+100h+var_50]
0x1400aa555  xor     rcx, rsp; StackCookie
0x1400aa558  call    __security_check_cookie
0x1400aa55d  add     rsp, 1C8h
0x1400aa564  pop     r15
0x1400aa566  pop     r14
0x1400aa568  pop     r13
0x1400aa56a  pop     r12
0x1400aa56c  pop     rdi
0x1400aa56d  pop     rsi
0x1400aa56e  pop     rbx
0x1400aa56f  pop     rbp
0x1400aa570  retn
0x1400aa572  mov     rcx, rbx
0x1400aa575  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x1400aa57a  mov     qword ptr [rbx+20h], 0
0x1400aa582  jmp     short loc_1400AA53B
0x1400aa584  mov     r8d, [rbp+100h+var_140]
0x1400aa588  mov     rdx, [rbp+100h+var_170]
0x1400aa58c  mov     rcx, [rsi+6F8h]
0x1400aa593  call    _guard_dispatch_icall
0x1400aa598  mov     rdi, rax
0x1400aa59b  test    rax, rax
0x1400aa59e  jz      loc_1400AA418
0x1400aa5a4  jmp     short loc_1400AA613
0x1400aa5a6  cmp     [rbp+100h+arg_60], 0
0x1400aa5ad  jz      short loc_1400AA5BB
0x1400aa5af  bts     dword ptr [rax+94h], 0Ah
0x1400aa5b7  mov     rax, [rbp+100h+var_178]
0x1400aa5bb  or      dword ptr [rax+94h], 1
0x1400aa5c2  mov     rcx, [rbp+100h+var_120]
0x1400aa5c6  mov     rax, [rbp+100h+var_178]
0x1400aa5ca  mov     [rax+258h], rcx
0x1400aa5d1  mov     rax, [rbp+100h+var_178]
0x1400aa5d5  mov     ecx, [rbp+100h+var_168]
0x1400aa5d8  mov     [rax+9Ch], r12d
0x1400aa5df  mov     rax, [rbp+100h+var_178]
0x1400aa5e3  mov     [rax+98h], ecx
0x1400aa5e9  lea     rcx, [rsp+200h+var_198]; this
0x1400aa5ee  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x1400aa5f3  lea     rcx, [rbp+100h+var_110]
0x1400aa5f7  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1400aa5fe  nop     dword ptr [rax+rax+00h]
0x1400aa603  test    rdi, rdi
0x1400aa606  jz      loc_1400AA6BA
0x1400aa60c  mov     r12d, [rbp+100h+arg_20]
0x1400aa613  cmp     edi, 0FFFFFFFFh
0x1400aa616  jz      loc_1400AA418
0x1400aa61c  xorps   xmm0, xmm0
0x1400aa61f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400aa626  lea     rdx, [rsp+200h+var_198]
0x1400aa62b  lea     rcx, [rsp+200h+var_198]
0x1400aa630  movups  [rsp+200h+var_198], xmm0
0x1400aa635  movups  [rsp+200h+var_188], xmm0
0x1400aa63a  call    cs:__imp_PushThreadGuardedObject
0x1400aa641  nop     dword ptr [rax+rax+00h]
0x1400aa646  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400aa64d  nop     dword ptr [rax+rax+00h]
0x1400aa652  xor     r9d, r9d
0x1400aa655  mov     r8b, 5
0x1400aa658  mov     rcx, rax
0x1400aa65b  mov     rdx, rdi
0x1400aa65e  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400aa665  nop     dword ptr [rax+rax+00h]
0x1400aa66a  xor     r14d, r14d
0x1400aa66d  mov     [rbp+100h+var_178], rax
0x1400aa671  test    rax, rax
0x1400aa674  jnz     loc_1400AA79A
0x1400aa67a  mov     rcx, rbx
0x1400aa67d  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x1400aa682  mov     rax, [rbp+100h+var_178]
0x1400aa686  lea     rcx, [rsp+200h+var_198]
0x1400aa68b  mov     [rbx+20h], rax
0x1400aa68f  mov     [rbp+100h+var_178], r14
0x1400aa693  call    cs:__imp_PopThreadGuardedObject
0x1400aa69a  nop     dword ptr [rax+rax+00h]
0x1400aa69f  jmp     loc_1400AA54B
0x1400aa6a4  test    edi, edi
0x1400aa6a6  mov     r12d, 57h ; 'W'
0x1400aa6ac  cmovnz  r12d, edi
0x1400aa6b0  cmp     qword ptr [rsi+0D68h], 0
0x1400aa6b8  jnz     short loc_1400AA6CC
0x1400aa6ba  cmp     [rbp+100h+arg_48], 0
0x1400aa6c1  jz      loc_1400AA418
0x1400aa6c7  jmp     loc_1400AA8FC
0x1400aa6cc  mov     eax, [rbp+100h+arg_58]
0x1400aa6d2  neg     eax
0x1400aa6d4  mov     [rbp+100h+var_120], 0
0x1400aa6dc  sbb     ecx, ecx
0x1400aa6de  and     ecx, 4
0x1400aa6e1  inc     ecx
0x1400aa6e3  mov     edi, ecx
0x1400aa6e5  or      edi, 8
0x1400aa6e8  cmp     [rbp+100h+arg_60], 0
0x1400aa6ef  cmovz   edi, ecx
0x1400aa6f2  lea     rcx, [rbp+100h+var_110]
0x1400aa6f6  mov     [rbp+100h+var_168], edi
0x1400aa6f9  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x1400aa700  nop     dword ptr [rax+rax+00h]
0x1400aa705  mov     rax, [rsi+0D68h]
0x1400aa70c  lea     rcx, [rbp+100h+var_120]
0x1400aa710  mov     r8d, [rbp+100h+var_140]
0x1400aa714  mov     r9d, edi
0x1400aa717  mov     rdx, [rbp+100h+var_170]
0x1400aa71b  mov     [rsp+200h+var_1C8], rcx
0x1400aa720  mov     ecx, [rsp+200h+var_1A0]
0x1400aa724  mov     dword ptr [rsp+200h+var_1D0], ecx
0x1400aa728  mov     rcx, [rsi+6F8h]
0x1400aa72f  mov     dword ptr [rsp+200h+var_1D8], 0
0x1400aa737  mov     [rsp+200h+var_1E0], 0
0x1400aa740  call    _guard_dispatch_icall
0x1400aa745  mov     rdi, rax
0x1400aa748  test    rax, rax
0x1400aa74b  jz      loc_1400AA5F3
0x1400aa751  mov     rdx, rax; HSURF
0x1400aa754  lea     rcx, [rsp+200h+var_198]; this
0x1400aa759  call    ??0SURFREF@@QEAA@PEAUHSURF__@@@Z; SURFREF::SURFREF(HSURF__ *)
0x1400aa75e  mov     rax, [rbp+100h+var_178]
0x1400aa762  test    rax, rax
0x1400aa765  jnz     loc_1400AA5A6
0x1400aa76b  mov     rcx, rbx
0x1400aa76e  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x1400aa773  lea     rcx, [rsp+200h+var_198]; this
0x1400aa778  mov     qword ptr [rbx+20h], 0
0x1400aa780  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x1400aa785  lea     rcx, [rbp+100h+var_110]
0x1400aa789  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1400aa790  nop     dword ptr [rax+rax+00h]
0x1400aa795  jmp     loc_1400AA54B
0x1400aa79a  bts     dword ptr [rax+90h], 17h
0x1400aa7a2  mov     rax, [rbp+100h+var_178]
0x1400aa7a6  bts     dword ptr [rax+90h], 1Ah
0x1400aa7ae  mov     rax, [rbp+100h+var_178]
0x1400aa7b2  bts     dword ptr [rax+90h], 0Eh
0x1400aa7ba  mov     rsi, [rbp+100h+var_130]
0x1400aa7be  test    rsi, rsi
0x1400aa7c1  jz      short loc_1400AA7F7
0x1400aa7c3  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400aa7ca  nop     dword ptr [rax+rax+00h]
0x1400aa7cf  xor     r9d, r9d
0x1400aa7d2  mov     r8b, 8
0x1400aa7d5  mov     rcx, rax
0x1400aa7d8  mov     rdx, rsi
0x1400aa7db  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400aa7e2  nop     dword ptr [rax+rax+00h]
0x1400aa7e7  test    rax, rax
0x1400aa7ea  jz      short loc_1400AA7F7
0x1400aa7ec  mov     rcx, [rbp+100h+var_178]
0x1400aa7f0  mov     [rcx+0A0h], rax
0x1400aa7f7  test    r15d, r15d
0x1400aa7fa  jz      loc_1400AA911
0x1400aa800  mov     r8, [rbp+100h+var_178]
0x1400aa804  mov     eax, 1
0x1400aa809  mov     r9d, eax
0x1400aa80c  mov     edx, eax
0x1400aa80e  mov     rcx, rdi
0x1400aa811  mov     r8, [r8+258h]
0x1400aa818  call    cs:__imp_EtwPhysicalSurfCreateEvent
0x1400aa81f  nop     dword ptr [rax+rax+00h]
0x1400aa824  jmp     loc_1400AA67A
0x1400aa829  cmp     qword ptr [rsi+0D68h], 0
0x1400aa831  jz      loc_1400AA8FC
0x1400aa837  lea     rcx, [rbp+100h+var_B0]
0x1400aa83b  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x1400aa842  nop     dword ptr [rax+rax+00h]
0x1400aa847  mov     eax, [rbp+100h+arg_58]
0x1400aa84d  lea     rcx, [rbp+100h+var_160]
0x1400aa851  mov     r8d, [rbp+100h+var_140]
0x1400aa855  neg     eax
0x1400aa857  mov     rax, [rsi+0D68h]
0x1400aa85e  mov     rdx, [rbp+100h+var_170]
0x1400aa862  sbb     r12d, r12d
0x1400aa865  mov     [rsp+200h+var_1C8], rcx
0x1400aa86a  and     r12d, 4
  ... truncated ...
```
