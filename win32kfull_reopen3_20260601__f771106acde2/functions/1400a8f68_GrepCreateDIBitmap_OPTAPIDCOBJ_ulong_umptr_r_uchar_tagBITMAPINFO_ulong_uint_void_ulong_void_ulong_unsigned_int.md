# GrepCreateDIBitmap(OPTAPIDCOBJ &,ulong,umptr_r<uchar> &,tagBITMAPINFO *,ulong,uint,void *,ulong,void *,ulong,unsigned __int64,void * *)

- ea: `0x1400a8f68`
- end: `0x1400a9976`
- name: `?GrepCreateDIBitmap@@YA?AVSURFREF@@AEAVOPTAPIDCOBJ@@KAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KIPEAXK3K_KPEAPEAX@Z`
- size: `2574`
- prototype: ``
- caller_count: `7`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140087cfc`
- `0x140099860`
- `0x1400a55dc`
- `0x1400a6cc0`
- `0x1400a8e1c`
- `0x14028be70`
- `0x140323a04`

## callees

- `0x14005b820`
- `0x140062138`
- `0x1400684f8`
- `0x140068674`
- `0x140069870`
- `0x1400698fc`
- `0x1400a8f68`
- `0x1400a9b38`
- `0x1400abaf4`
- `0x1400acb4c`
- `0x1400cd374`
- `0x140112314`
- `0x1401b255c`
- `0x1401cf360`
- `0x1401d737c`
- `0x140226ddc`
- `0x140298e04`
- `0x1402a1080`
- `0x140343200`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a92b6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a96e1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a92b6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a96e1`
- `win32kbase!PushThreadGuardedObject` at `0x1400a92a1`
- `win32kbase!PushThreadGuardedObject` at `0x1400a92a1`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a92ea`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1400a92ea`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400a9740`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400a98dd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a91ff`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1400a91ff`
- `win32kbase!INC_SHARE_REF_CNT` at `0x1400a92c9`
- `win32kbase!INC_SHARE_REF_CNT` at `0x1400a92c9`
- `win32kbase!EngSetLastError` at `0x1400a9547`
- `win32kbase!EngSetLastError` at `0x1400a95e0`
- `win32kbase!EngSetLastError` at `0x1400a9659`
- `win32kbase!EngSetLastError` at `0x1400a9834`
- `win32kbase!EngSetLastError` at `0x1400a9950`
- `win32kbase!EngSetLastError` at `0x1400a9547`
- `win32kbase!EngSetLastError` at `0x1400a95e0`
- `win32kbase!EngSetLastError` at `0x1400a9659`
- `win32kbase!EngSetLastError` at `0x1400a9834`
- `win32kbase!EngSetLastError` at `0x1400a9950`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x1400a92fb`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x1400a92fb`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a90e2`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x1400a90e2`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400a9476`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400a96b9`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400a9476`
- `win32kbase!AllocFreeTmpBuffer` at `0x1400a96b9`
- `win32kbase!FreeTmpBuffer` at `0x1400a9502`
- `win32kbase!FreeTmpBuffer` at `0x1400a972f`
- `win32kbase!FreeTmpBuffer` at `0x1400a9502`
- `win32kbase!FreeTmpBuffer` at `0x1400a972f`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x1400a94f3`
- `win32kbase!?vUpdateTime@XEPALOBJ@@QEAAXXZ` at `0x1400a94f3`

## pseudocode

```c
__int64 __fastcall GrepCreateDIBitmap(
        __int64 a1,
        OPTAPIDCOBJ *a2,
        int a3,
        char **a4,
        unsigned int *a5,
        int a6,
        unsigned int a7,
        char *a8,
        unsigned int a9,
        void *a10,
        unsigned __int8 a11,
        unsigned __int64 a12,
        _QWORD *a13)
{
  int v13; // r15d
  unsigned int v16; // r13d
  __int64 v17; // r9
  unsigned int v18; // r8d
  int v19; // edx
  int v20; // eax
  int v21; // edx
  unsigned int v22; // edi
  unsigned int v23; // r14d
  unsigned int v24; // esi
  unsigned int v25; // eax
  unsigned int v26; // edx
  unsigned int v27; // ecx
  __int64 v28; // r8
  char *v29; // r10
  char **v30; // r9
  char *v31; // rsi
  char *v32; // r14
  unsigned __int8 v33; // dl
  bool v34; // al
  DC *v35; // rax
  char *v36; // rcx
  char *v37; // rdx
  int v38; // eax
  int DIB; // eax
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rsi
  __int64 v44; // rdi
  Gre::Base *v45; // rcx
  struct Gre::Base::SESSION_GLOBALS *v46; // rax
  int v48; // eax
  unsigned int v49; // r13d
  __int64 v50; // rcx
  void *v51; // rax
  void *v52; // rsi
  _BYTE *v53; // rcx
  unsigned int v54; // r8d
  char *v55; // rdx
  char v56; // al
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned __int64 v59; // rsi
  unsigned int CachedDpiScaleValue; // eax
  unsigned __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  void *v64; // rax
  void *v65; // r14
  Gre::Base *v66; // rcx
  struct Gre::Base::SESSION_GLOBALS *v67; // rax
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  int v71; // esi
  __int64 v72; // rdi
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rcx
  float v77; // xmm0_4
  void *v78; // rax
  void *Src; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v80; // [rsp+68h] [rbp-A0h] BYREF
  int v81; // [rsp+70h] [rbp-98h]
  int v82; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v83; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v84; // [rsp+80h] [rbp-88h]
  _DWORD v85[3]; // [rsp+84h] [rbp-84h] BYREF
  int v86; // [rsp+90h] [rbp-78h]
  int v87; // [rsp+94h] [rbp-74h]
  __int64 v88; // [rsp+98h] [rbp-70h] BYREF
  char v89; // [rsp+A0h] [rbp-68h]
  unsigned int v90; // [rsp+B0h] [rbp-58h]
  int v91; // [rsp+B4h] [rbp-54h]
  unsigned int v92; // [rsp+B8h] [rbp-50h]
  DC *v93; // [rsp+C8h] [rbp-40h] BYREF
  int v94; // [rsp+D0h] [rbp-38h]
  __int64 v95; // [rsp+D8h] [rbp-30h]
  __int64 v96; // [rsp+E0h] [rbp-28h]
  char v97[32]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v98[96]; // [rsp+108h] [rbp+0h] BYREF
  int v99; // [rsp+188h] [rbp+80h] BYREF
  char **v100; // [rsp+190h] [rbp+88h]

  v100 = a4;
  v99 = a3;
  v13 = a6;
  memset(v85, 0, sizeof(v85));
  v87 = 0;
  if ( a6 != 1 )
  {
    if ( a6 == 3 )
    {
      if ( (a11 & 1) == 0 )
        goto LABEL_93;
    }
    else if ( a6 )
    {
      goto LABEL_93;
    }
  }
  if ( !a8 && (a11 & 8) != 0 )
    goto LABEL_93;
  if ( !a5 )
    goto LABEL_93;
  v16 = a7;
  if ( a7 < 0x28 )
    goto LABEL_93;
  v17 = *a5;
  v91 = v17;
  if ( (unsigned int)v17 < 0x28 )
    goto LABEL_93;
  if ( a7 < (unsigned int)v17 )
    goto LABEL_93;
  v18 = a5[4];
  v92 = v18;
  if ( v18 - 4 <= 1 )
    goto LABEL_93;
  v19 = a5[1];
  if ( v19 <= 0 )
    goto LABEL_93;
  v20 = a5[2];
  if ( !v20 )
    goto LABEL_93;
  v86 = 0;
  v83 = v19;
  if ( v20 < 0 )
  {
    v20 = -v20;
    v86 = 1;
  }
  v21 = *((unsigned __int16 *)a5 + 7);
  v84 = v20;
  v90 = a5[8];
  Src = (char *)a5 + v17;
  v82 = v21;
  v99 = 0;
  if ( v18 )
  {
    if ( v18 == 3 )
    {
      if ( a7 < 0x34 || a6 )
        goto LABEL_93;
      if ( (_WORD)v21 == 16 )
      {
        v82 = 4;
      }
      else
      {
        if ( v21 != 32 )
          goto LABEL_93;
        v82 = 6;
      }
      v22 = 0;
      v25 = a5[10];
      v23 = 2;
      v27 = a5[11];
      v24 = 512;
      Src = a5 + 10;
      v26 = a5[12];
      goto LABEL_20;
    }
    if ( v18 != 10 || !OPTAPIDCOBJ::bValid(a2) )
      goto LABEL_93;
    APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v93, a2);
    if ( !(unsigned int)DC::bIsCMYKColor(v93) )
      goto LABEL_127;
    switch ( v82 )
    {
      case 1:
        v82 = 1;
        v22 = 2;
        break;
      case 4:
        v82 = 2;
        v22 = 16;
        break;
      case 8:
        v82 = 3;
        v22 = 256;
        break;
      case 32:
        v22 = 0;
        v82 = 6;
        v23 = 16;
        v24 = 512;
LABEL_117:
        APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
        goto LABEL_19;
      default:
LABEL_127:
        EngSetLastError(0x57u);
        UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
        *(_QWORD *)(a1 + 32) = 0;
        APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
        return a1;
    }
    v23 = 1;
    v24 = 1024;
    goto LABEL_117;
  }
  switch ( v21 )
  {
    case 1:
      v82 = 1;
      v22 = 2;
LABEL_18:
      v23 = 1;
      v24 = 1024;
LABEL_19:
      v25 = v99;
      v26 = v99;
      v27 = v99;
      goto LABEL_20;
    case 4:
      v82 = 2;
      v22 = 16;
      goto LABEL_18;
    case 8:
      v82 = 3;
      v22 = 256;
      goto LABEL_18;
  }
  v48 = 0;
  v22 = 0;
  v24 = 512;
  if ( a6 != 1 )
    v48 = a6;
  v13 = v48;
  if ( v21 != 16 )
  {
    if ( (_WORD)v21 == 24 )
    {
      v82 = 5;
      goto LABEL_50;
    }
    if ( v21 == 32 )
    {
      v82 = 6;
LABEL_50:
      v23 = 8;
      v25 = 0;
      v27 = 0;
      v26 = 0;
      goto LABEL_20;
    }
LABEL_93:
    EngSetLastError(0x57u);
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
    return a1;
  }
  v82 = 4;
  v25 = 31744;
  v27 = 992;
  v26 = 31;
  v23 = 2;
LABEL_20:
  v81 = 0;
  v80 = 0;
  if ( !PALMEMOBJ::bCreatePalette((PALMEMOBJ *)&v80, v23, v22, 0, v25, v27, v26, v24, 1) )
  {
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
    goto LABEL_40;
  }
  *(_QWORD *)&v85[1] = *(_QWORD *)v80;
  SURFMEM::SURFMEM(&v88, 2);
  v30 = v100;
  v31 = v100[1];
  v32 = v100[2];
  if ( (v33 & a11) != 0 )
  {
    *(_DWORD *)(v28 + 24) |= 0x8000u;
    v36 = *v30;
    if ( !*v30 )
      goto LABEL_38;
    v37 = v30[2];
    v30[2] = v29;
    *v30 = v29;
    v30[1] = v29;
    *((_WORD *)v30 + 12) = (_WORD)v29;
  }
  else
  {
    a8 = v29;
    if ( *((char **)a2 + 12) != v29 )
    {
      v34 = OPTAPIDCOBJ::bValid(a2);
      v29 = 0;
      if ( v34 )
      {
        v95 = *((_QWORD *)a2 + 2);
        v96 = 0;
        v93 = 0;
        v94 = 0;
        UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v97);
        UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(v98);
        v35 = *(DC **)a2;
        v98[32] = 0;
        v93 = v35;
        if ( (*(_DWORD *)(*((_QWORD *)v35 + 6) + 40LL) & 0x8000) != 0 )
          v86 |= 0x40000u;
        APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
        v29 = 0;
      }
    }
    v36 = v29;
    v37 = v29;
  }
  v99 = a11 & 8;
  v38 = (int)v29;
  LOBYTE(v38) = v99 != 0;
  DIB = SURFMEM::bCreateDIB(
          (SURFMEM *)&v88,
          (struct _DEVBITMAPINFO *)&v82,
          &v37[(_QWORD)v36],
          a8,
          a9,
          a10,
          a12,
          (_DWORD)v29,
          1,
          v38);
  v41 = 0;
  if ( !DIB )
    goto LABEL_38;
  v42 = v88;
  v43 = v31 - v32;
  if ( !*(_WORD *)(v88 + 100) && *(_QWORD *)(v88 + 224) && *(_DWORD *)(v88 + 64) != v43 )
    goto LABEL_38;
  if ( *v100 )
  {
    v61 = *(unsigned int *)(v88 + 64);
    if ( v61 > v43 )
      goto LABEL_78;
    umptr_r<unsigned char>::read<unsigned char>(v100, *(_QWORD *)(v88 + 72), v61, 0);
    v42 = v88;
  }
  if ( v90 && v90 < v22 )
  {
    v22 = v90;
  }
  else if ( !v22 )
  {
LABEL_34:
    if ( a13 )
    {
      if ( v99 )
        *a13 = 0;
      else
        *a13 = *(_QWORD *)(v42 + 72);
    }
    *(_DWORD *)(v42 + 144) |= 0x4000000u;
    v89 |= 1u;
    v81 = 1;
    if ( (a11 & 0x10) != 0 && OPTAPIDCOBJ::bValid(a2) )
    {
      APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v93, a2);
      CachedDpiScaleValue = DC::GetCachedDpiScaleValue(v93);
      ReturnValueTracer<unsigned long>::ReturnValueTracer<unsigned long>(&v99, CachedDpiScaleValue);
      if ( v99 > 1 )
      {
        LODWORD(Src) = v83 / v99;
        v76 = v88;
        v77 = (float)v99;
        HIDWORD(Src) = v84 / v99;
        v78 = Src;
        *(_DWORD *)(v88 + 148) |= 0x800u;
        *(_QWORD *)(v76 + 700) = v78;
        *(float *)(v76 + 692) = v77;
        *(float *)(v76 + 696) = v77;
      }
      APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
    }
    v44 = v88;
    *(_OWORD *)a1 = 0;
    *(_OWORD *)(a1 + 16) = 0;
    PushThreadGuardedObject(
      a1,
      a1,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    if ( v44 )
    {
      *(_QWORD *)(a1 + 32) = v44;
      v46 = Gre::Base::Globals(v45);
      INC_SHARE_REF_CNT(v46, *(_QWORD *)(a1 + 32));
    }
    goto LABEL_39;
  }
  v49 = v16 - v91;
  if ( !v13 )
  {
    if ( 4 * (unsigned __int64)v22 <= 0xFFFFFFFF )
    {
      v50 = 4 * v22;
      if ( v49 >= (unsigned int)v50 )
      {
        v51 = (void *)AllocFreeTmpBuffer(v50, v41, v40);
        v52 = v51;
        if ( v51 )
        {
          memmove(v51, Src, 4LL * v22);
          v53 = *(_BYTE **)(v80 + 112);
          if ( v92 - 10 <= 2 )
          {
            if ( v22 > *(_DWORD *)(v80 + 28) )
              v22 = *(_DWORD *)(v80 + 28);
            memmove(v53, v52, 4LL * v22);
          }
          else
          {
            v54 = *(_DWORD *)(v80 + 28);
            v55 = (char *)v52;
            if ( v22 <= v54 || (v22 = *(_DWORD *)(v80 + 28), v54) )
            {
              do
              {
                v53[3] = 0;
                v56 = *v55;
                v55 += 4;
                v53[2] = v56;
                *v53 = *(v55 - 2);
                v53 += 4;
                *(v53 - 3) = *(v55 - 3);
                --v22;
              }
              while ( v22 );
            }
          }
          XEPALOBJ::vUpdateTime((XEPALOBJ *)&v80);
          FreeTmpBuffer(v52, v57, v58);
          if ( (a11 & 4) != 0 && v82 == 3 )
          {
            if ( !OPTAPIDCOBJ::bValid(a2) )
              goto LABEL_38;
            v71 = 0;
            APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v93, a2);
            v72 = *((_QWORD *)v93 + 6);
            SEMOBJSHARED<1>::SEMOBJSHARED<1>(&Src, v73, v74, v75);
            if ( *(_DWORD *)(v72 + 2092) == 3
              && (*(_DWORD *)(v72 + 2156) & 0x100) != 0
              && (*(_DWORD *)(v72 + 40) & 1) != 0 )
            {
              v71 = 1;
              XEPALOBJ::apalColorSet((XEPALOBJ *)&v80, *(struct PALETTE **)(v72 + 1792));
            }
            GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, Src);
            APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
            if ( !v71 )
              goto LABEL_38;
          }
          goto LABEL_75;
        }
        EngSetLastError(0xEu);
        goto LABEL_38;
      }
    }
LABEL_78:
    EngSetLastError(0x57u);
    UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
    *(_QWORD *)(a1 + 32) = 0;
    goto LABEL_39;
  }
  if ( v13 != 1 )
    goto LABEL_34;
  v59 = 2LL * v22;
  if ( v59 > 0xFFFFFFFF || v49 < v59 )
    goto LABEL_78;
  if ( OPTAPIDCOBJ::bValid(a2) )
  {
    APIDCOBJ::APIDCOBJ((APIDCOBJ *)&v93, a2);
    v64 = (void *)AllocFreeTmpBuffer(2 * v22, v62, v63);
    v65 = v64;
    if ( !v64 )
    {
      EngSetLastError(0xEu);
      UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
      *(_QWORD *)(a1 + 32) = 0;
      APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
      goto LABEL_39;
    }
    memmove(v64, Src, 2LL * v22);
    v67 = Gre::Base::Globals(v66);
    SEMOBJSHARED<1>::SEMOBJSHARED<1>(&Src, v67);
    v68 = *((_QWORD *)XDCOBJ::pSurfaceEff((XDCOBJ *)&v93) + 20);
    if ( !v68 )
      v68 = *(_QWORD *)(*((_QWORD *)v93 + 6) + 1792LL);
    XEPALOBJ::vGetEntriesFrom(&v80, *((_QWORD *)v93 + 11), v68, v65, v22);
    FreeTmpBuffer(v65, v69, v70);
    GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, Src);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v93);
LABEL_75:
    v42 = v88;
    goto LABEL_34;
  }
LABEL_38:
  UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(a1);
  *(_QWORD *)(a1 + 32) = 0;
LABEL_39:
  SURFMEM::~SURFMEM((SURFMEM *)&v88);
LABEL_40:
  PALMEMOBJ::~PALMEMOBJ((PALMEMOBJ *)&v80);
  return a1;
}

```

## disassembly

```asm
0x1400a8f68  mov     rax, rsp
0x1400a8f6b  mov     [rax+8], rbx
0x1400a8f6f  mov     [rax+20h], r9
0x1400a8f73  mov     [rax+18h], r8d
0x1400a8f77  push    rbp
0x1400a8f78  push    rsi
0x1400a8f79  push    rdi
0x1400a8f7a  push    r12
0x1400a8f7c  push    r13
0x1400a8f7e  push    r14
0x1400a8f80  push    r15
0x1400a8f82  lea     rbp, [rax-68h]
0x1400a8f86  sub     rsp, 130h
0x1400a8f8d  mov     r15d, [rbp+60h+arg_28]
0x1400a8f94  xor     r14d, r14d
0x1400a8f97  mov     r12, rdx
0x1400a8f9a  mov     [rsp+7Ch], r14
0x1400a8f9f  mov     rbx, rcx
0x1400a8fa2  mov     [rbp+60h+var_DC], r14d
0x1400a8fa6  mov     [rbp+60h+var_D4], r14d
0x1400a8faa  lea     edi, [r14+3]
0x1400a8fae  lea     esi, [rdi-2]
0x1400a8fb1  cmp     r15d, esi
0x1400a8fb4  jz      short loc_1400A8FC8
0x1400a8fb6  cmp     r15d, edi
0x1400a8fb9  jz      loc_1400A975A
0x1400a8fbf  test    r15d, r15d
0x1400a8fc2  jnz     loc_1400A9654
0x1400a8fc8  mov     r10d, 8
0x1400a8fce  cmp     [rbp+60h+arg_38], r14
0x1400a8fd5  jnz     short loc_1400A8FE4
0x1400a8fd7  test    [rbp+60h+arg_50], r10b
0x1400a8fde  jnz     loc_1400A9654
0x1400a8fe4  mov     rcx, [rbp+60h+arg_20]
0x1400a8feb  test    rcx, rcx
0x1400a8fee  jz      loc_1400A9654
0x1400a8ff4  mov     r13d, [rbp+60h+arg_30]
0x1400a8ffb  cmp     r13d, 28h ; '('
0x1400a8fff  jb      loc_1400A9654
0x1400a9005  mov     r9d, [rcx]
0x1400a9008  mov     [rbp+60h+var_B4], r9d
0x1400a900c  cmp     r9d, 28h ; '('
0x1400a9010  jb      loc_1400A9654
0x1400a9016  cmp     r13d, r9d
0x1400a9019  jb      loc_1400A9654
0x1400a901f  mov     r8d, [rcx+10h]
0x1400a9023  mov     [rbp+60h+var_B0], r8d
0x1400a9027  lea     eax, [r8-4]
0x1400a902b  cmp     eax, esi
0x1400a902d  jbe     loc_1400A9654
0x1400a9033  mov     edx, [rcx+4]
0x1400a9036  test    edx, edx
0x1400a9038  jle     loc_1400A9654
0x1400a903e  mov     eax, [rcx+8]
0x1400a9041  test    eax, eax
0x1400a9043  jz      loc_1400A9654
0x1400a9049  mov     [rbp+60h+var_D8], r14d
0x1400a904d  mov     dword ptr [rsp+160h+var_EC], edx
0x1400a9051  js      loc_1400A9326
0x1400a9057  movzx   edx, word ptr [rcx+0Eh]
0x1400a905b  mov     r11d, 10h
0x1400a9061  mov     dword ptr [rsp+160h+var_EC+4], eax
0x1400a9065  mov     eax, [rcx+20h]
0x1400a9068  mov     [rbp+60h+var_B8], eax
0x1400a906b  lea     rax, [rcx+r9]
0x1400a906f  mov     [rsp+160h+Src], rax
0x1400a9074  lea     r9d, [r11-0Eh]
0x1400a9078  mov     [rsp+160h+var_F0], edx
0x1400a907c  mov     [rbp+60h+arg_10], r14d
0x1400a9083  test    r8d, r8d
0x1400a9086  jnz     loc_1400A93B7
0x1400a908c  mov     eax, edx
0x1400a908e  sub     eax, esi
0x1400a9090  jnz     loc_1400A9330
0x1400a9096  mov     [rsp+160h+var_F0], esi
0x1400a909a  mov     edi, r9d
0x1400a909d  mov     r14d, esi
0x1400a90a0  mov     esi, 400h
0x1400a90a5  mov     eax, [rbp+60h+arg_10]
0x1400a90ab  mov     edx, eax
0x1400a90ad  mov     ecx, eax
0x1400a90af  mov     [rsp+160h+var_120], 1
0x1400a90b7  xor     r8d, r8d
0x1400a90ba  mov     [rsp+160h+var_128], esi
0x1400a90be  xor     r9d, r9d
0x1400a90c1  mov     [rsp+160h+var_130], edx
0x1400a90c5  mov     edx, r14d
0x1400a90c8  mov     dword ptr [rsp+160h+var_138], ecx
0x1400a90cc  lea     rcx, [rsp+160h+var_100]
0x1400a90d1  mov     [rsp+160h+var_F8], r8d
0x1400a90d6  mov     [rsp+160h+var_100], r8
0x1400a90db  mov     r8d, edi
0x1400a90de  mov     dword ptr [rsp+160h+var_140], eax
0x1400a90e2  call    cs:__imp_?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z; PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)
0x1400a90e9  nop     dword ptr [rax+rax+00h]
0x1400a90ee  xor     r10d, r10d
0x1400a90f1  test    eax, eax
0x1400a90f3  jz      loc_1400A9640
0x1400a90f9  mov     r8, [rsp+160h+var_100]
0x1400a90fe  lea     edx, [r10+2]
0x1400a9102  lea     rcx, [rbp+60h+var_D0]
0x1400a9106  mov     rax, [r8]
0x1400a9109  mov     [rbp-80h], rax
0x1400a910d  call    ??0SURFMEM@@QEAA@W4U2KMMAPStatus@@@Z; SURFMEM::SURFMEM(U2KMMAPStatus)
0x1400a9112  mov     r9, [rbp+60h+arg_18]
0x1400a9119  mov     rsi, [r9+8]
0x1400a911d  mov     r14, [r9+10h]
0x1400a9121  test    [rbp+60h+arg_50], dl
0x1400a9127  jnz     loc_1400A938C
0x1400a912d  mov     [rbp+60h+arg_38], r10
0x1400a9134  cmp     [r12+60h], r10
0x1400a9139  jz      short loc_1400A919D
0x1400a913b  mov     rcx, r12; this
0x1400a913e  call    ?bValid@OPTAPIDCOBJ@@QEAA_NXZ; OPTAPIDCOBJ::bValid(void)
0x1400a9143  xor     r10d, r10d
0x1400a9146  test    al, al
0x1400a9148  jz      short loc_1400A919D
0x1400a914a  mov     rax, [r12+10h]
0x1400a914f  lea     rcx, [rbp+60h+var_80]
0x1400a9153  mov     [rbp+60h+var_90], rax
0x1400a9157  mov     [rbp+60h+var_88], r10
0x1400a915b  mov     [rbp+60h+var_A0], r10
0x1400a915f  mov     [rbp+60h+var_98], r10d
0x1400a9163  call    ??0?$UnexpectedThreadTerminationHandler@VDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(void)
0x1400a9168  lea     rcx, [rbp+60h+var_60]
0x1400a916c  call    ??0?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<APIDCOBJ>::UnexpectedThreadTerminationHandler<APIDCOBJ>(void)
0x1400a9171  mov     rax, [r12]
0x1400a9175  xor     r8d, r8d
0x1400a9178  mov     [rbp+60h+var_40], r8b
0x1400a917c  mov     [rbp+60h+var_A0], rax
0x1400a9180  mov     rax, [rax+30h]
0x1400a9184  test    dword ptr [rax+28h], 8000h
0x1400a918b  jnz     loc_1400A9567
0x1400a9191  lea     rcx, [rbp+60h+var_A0]; this
0x1400a9195  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400a919a  xor     r10d, r10d
0x1400a919d  mov     rcx, r10
0x1400a91a0  mov     rdx, r10
0x1400a91a3  mov     eax, dword ptr [rbp+60h+arg_50]
0x1400a91a9  lea     r8, [rcx+rdx]
0x1400a91ad  mov     r9, [rbp+60h+arg_38]
0x1400a91b4  lea     rdx, [rsp+160h+var_F0]
0x1400a91b9  and     eax, 8
0x1400a91bc  lea     rcx, [rbp+60h+var_D0]
0x1400a91c0  mov     [rbp+60h+arg_10], eax
0x1400a91c6  mov     eax, r10d
0x1400a91c9  setnz   al
0x1400a91cc  mov     [rsp+48h], eax
0x1400a91d0  mov     rax, [rbp+60h+arg_58]
0x1400a91d7  mov     [rsp+160h+var_120], 1
0x1400a91df  mov     [rsp+160h+var_128], r10d
0x1400a91e4  mov     qword ptr [rsp+160h+var_130], rax
0x1400a91e9  mov     rax, [rbp+60h+arg_48]
0x1400a91f0  mov     [rsp+160h+var_138], rax
0x1400a91f5  mov     eax, [rbp+60h+arg_40]
0x1400a91fb  mov     dword ptr [rsp+160h+var_140], eax
0x1400a91ff  call    cs:__imp_?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z; SURFMEM::bCreateDIB(_DEVBITMAPINFO *,void *,void *,ulong,void *,unsigned __int64,int,int,int)
0x1400a9206  nop     dword ptr [rax+rax+00h]
0x1400a920b  xor     edx, edx
0x1400a920d  test    eax, eax
0x1400a920f  jz      loc_1400A92D7
0x1400a9215  mov     rcx, [rbp+60h+var_D0]
0x1400a9219  sub     rsi, r14
0x1400a921c  cmp     [rcx+64h], dx
0x1400a9220  jnz     short loc_1400A922F
0x1400a9222  cmp     [rcx+0E0h], rdx
0x1400a9229  jnz     loc_1400A940F
0x1400a922f  mov     rax, [rbp+60h+arg_18]
0x1400a9236  cmp     [rax], rdx
0x1400a9239  jnz     loc_1400A95FF
0x1400a923f  mov     eax, [rbp+60h+var_B8]
0x1400a9242  test    eax, eax
0x1400a9244  jnz     loc_1400A9439
0x1400a924a  test    edi, edi
0x1400a924c  jnz     loc_1400A9443
0x1400a9252  xor     r13d, r13d
0x1400a9255  mov     rdx, [rbp+60h+arg_60]
0x1400a925c  test    rdx, rdx
0x1400a925f  jnz     loc_1400A9420
0x1400a9265  bts     dword ptr [rcx+90h], 1Ah
0x1400a926d  or      [rbp+60h+var_C8], 1
0x1400a9271  test    [rbp+60h+arg_50], 10h
0x1400a9278  mov     [rsp+160h+var_F8], 1
0x1400a9280  jnz     loc_1400A957E
0x1400a9286  mov     rdi, [rbp+60h+var_D0]
0x1400a928a  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a9291  xorps   xmm0, xmm0
0x1400a9294  mov     rdx, rbx
0x1400a9297  movups  xmmword ptr [rbx], xmm0
0x1400a929a  mov     rcx, rbx
0x1400a929d  movups  xmmword ptr [rbx+10h], xmm0
0x1400a92a1  call    cs:__imp_PushThreadGuardedObject
0x1400a92a8  nop     dword ptr [rax+rax+00h]
0x1400a92ad  test    rdi, rdi
0x1400a92b0  jz      short loc_1400A92E6
0x1400a92b2  mov     [rbx+20h], rdi
0x1400a92b6  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a92bd  nop     dword ptr [rax+rax+00h]
0x1400a92c2  mov     rdx, [rbx+20h]
0x1400a92c6  mov     rcx, rax
0x1400a92c9  call    cs:__imp_INC_SHARE_REF_CNT
0x1400a92d0  nop     dword ptr [rax+rax+00h]
0x1400a92d5  jmp     short loc_1400A92E6
0x1400a92d7  xor     r13d, r13d
0x1400a92da  mov     rcx, rbx
0x1400a92dd  call    ??0?$UnexpectedThreadTerminationHandler@VSURFREF@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<SURFREF>::UnexpectedThreadTerminationHandler<SURFREF>(void)
0x1400a92e2  mov     [rbx+20h], r13
0x1400a92e6  lea     rcx, [rbp+60h+var_D0]
0x1400a92ea  call    cs:__imp_??1SURFMEM@@QEAA@XZ; SURFMEM::~SURFMEM(void)
0x1400a92f1  nop     dword ptr [rax+rax+00h]
0x1400a92f6  lea     rcx, [rsp+160h+var_100]
0x1400a92fb  call    cs:__imp_??1PALMEMOBJ@@QEAA@XZ; PALMEMOBJ::~PALMEMOBJ(void)
0x1400a9302  nop     dword ptr [rax+rax+00h]
0x1400a9307  mov     rax, rbx
0x1400a930a  mov     rbx, [rsp+160h+arg_0]
0x1400a9312  add     rsp, 130h
0x1400a9319  pop     r15
0x1400a931b  pop     r14
0x1400a931d  pop     r13
0x1400a931f  pop     r12
0x1400a9321  pop     rdi
0x1400a9322  pop     rsi
0x1400a9323  pop     rbp
0x1400a9324  retn
0x1400a9326  neg     eax
0x1400a9328  mov     [rbp+60h+var_D8], esi
0x1400a932b  jmp     loc_1400A9057
0x1400a9330  sub     eax, edi
0x1400a9332  jz      loc_1400A967E
0x1400a9338  cmp     eax, 4
0x1400a933b  jz      loc_1400A95F1
0x1400a9341  cmp     r15d, esi
0x1400a9344  mov     eax, r14d
0x1400a9347  mov     edi, r14d
0x1400a934a  mov     esi, 200h
0x1400a934f  cmovnz  eax, r15d
0x1400a9353  mov     r15d, eax
0x1400a9356  cmp     edx, r11d
0x1400a9359  jz      loc_1400A976C
0x1400a935f  mov     ecx, 18h
0x1400a9364  cmp     dx, cx
0x1400a9367  jz      loc_1400A95CE
0x1400a936d  cmp     edx, 20h ; ' '
0x1400a9370  jnz     loc_1400A9654
0x1400a9376  mov     [rsp+160h+var_F0], 6
0x1400a937e  mov     r14d, r10d
0x1400a9381  mov     eax, edi
0x1400a9383  mov     ecx, edi
0x1400a9385  mov     edx, edi
0x1400a9387  jmp     loc_1400A90AF
0x1400a938c  bts     dword ptr [r8+18h], 0Fh
0x1400a9392  mov     rcx, [r9]
0x1400a9395  test    rcx, rcx
0x1400a9398  jz      loc_1400A92D7
0x1400a939e  mov     rdx, [r9+10h]
0x1400a93a2  mov     [r9+10h], r10
0x1400a93a6  mov     [r9], r10
0x1400a93a9  mov     [r9+8], r10
0x1400a93ad  mov     [r9+18h], r10w
0x1400a93b2  jmp     loc_1400A91A3
0x1400a93b7  cmp     r8d, edi
0x1400a93ba  jnz     loc_1400A978B
0x1400a93c0  cmp     r13d, 34h ; '4'
0x1400a93c4  jb      loc_1400A9654
0x1400a93ca  test    r15d, r15d
0x1400a93cd  jnz     loc_1400A9654
0x1400a93d3  cmp     dx, r11w
0x1400a93d7  jz      loc_1400A9571
0x1400a93dd  cmp     edx, 20h ; ' '
0x1400a93e0  jnz     loc_1400A9654
0x1400a93e6  mov     [rsp+160h+var_F0], 6
0x1400a93ee  lea     rdx, [rcx+28h]
0x1400a93f2  mov     edi, r14d
0x1400a93f5  mov     eax, [rdx]
0x1400a93f7  mov     r14d, r9d
0x1400a93fa  mov     ecx, [rdx+4]
0x1400a93fd  mov     esi, 200h
0x1400a9402  mov     [rsp+160h+Src], rdx
0x1400a9407  mov     edx, [rdx+8]
0x1400a940a  jmp     loc_1400A90AF
0x1400a940f  mov     eax, [rcx+40h]
0x1400a9412  cmp     rax, rsi
0x1400a9415  jz      loc_1400A922F
0x1400a941b  jmp     loc_1400A92D7
0x1400a9420  cmp     [rbp+60h+arg_10], r13d
0x1400a9427  jnz     loc_1400A9676
0x1400a942d  mov     rax, [rcx+48h]
0x1400a9431  mov     [rdx], rax
0x1400a9434  jmp     loc_1400A9265
0x1400a9439  cmp     eax, edi
0x1400a943b  jnb     loc_1400A924A
0x1400a9441  mov     edi, eax
0x1400a9443  sub     r13d, [rbp+60h+var_B4]
0x1400a9447  test    r15d, r15d
0x1400a944a  jnz     loc_1400A9524
0x1400a9450  mov     r15d, edi
0x1400a9453  mov     r14d, 0FFFFFFFFh
0x1400a9459  shl     r15, 2
0x1400a945d  cmp     r15, r14
0x1400a9460  ja      loc_1400A9542
  ... truncated ...
```
