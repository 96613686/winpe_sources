# GreCreateSpriteInternal(HDEV__ *,HWND__ *,tagRECT *,tagMINIWINDOWINFO *,ulong,int,int,int,int,int,int,ushort const *)

- ea: `0x14011c8e4`
- end: `0x14011cdac`
- name: `?GreCreateSpriteInternal@@YAPEAXPEAUHDEV__@@PEAUHWND__@@PEAUtagRECT@@PEAUtagMINIWINDOWINFO@@KHHHHHHPEBG@Z`
- size: `1224`
- prototype: `void *__fastcall(HDEV, HWND, struct tagRECT *, struct tagMINIWINDOWINFO *, unsigned int, int, int, int, int, int, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14011ae80`
- `0x14011c80c`
- `0x14011da34`
- `0x140216594`

## callees

- `0x140014550`
- `0x140016de4`
- `0x1400197fc`
- `0x1400a9b80`
- `0x140112d58`
- `0x14011ab40`
- `0x14011c458`
- `0x14011c694`
- `0x14011c6c0`
- `0x14011c8e4`
- `0x14011cdb4`
- `0x14011d414`
- `0x14011dee4`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14011cc03`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14011cc03`
- `win32kbase!UserReferenceDwmApiPort` at `0x14011cb98`
- `win32kbase!UserReferenceDwmApiPort` at `0x14011cd07`
- `win32kbase!UserReferenceDwmApiPort` at `0x14011cb98`
- `win32kbase!UserReferenceDwmApiPort` at `0x14011cd07`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14011cc15`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14011cc15`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011c938`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011ca24`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cbda`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011ccdf`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011c938`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011ca24`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011cbda`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011ccdf`
- `win32kbase!PopThreadGuardedObject` at `0x14011cc47`
- `win32kbase!PopThreadGuardedObject` at `0x14011cd37`
- `win32kbase!PopThreadGuardedObject` at `0x14011cc47`
- `win32kbase!PopThreadGuardedObject` at `0x14011cd37`
- `win32kbase!PushThreadGuardedObject` at `0x14011c9f0`
- `win32kbase!PushThreadGuardedObject` at `0x14011cccf`
- `win32kbase!PushThreadGuardedObject` at `0x14011c9f0`
- `win32kbase!PushThreadGuardedObject` at `0x14011cccf`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14011cb50`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14011cb50`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14011c991`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14011c991`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011ca41`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011ccf7`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011ca41`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14011ccf7`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011ca04`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011ca04`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011ca55`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14011ca55`
- `WIN32K!W32GetUserSessionState` at `0x14011cc9d`
- `WIN32K!W32GetUserSessionState` at `0x14011cd6a`
- `WIN32K!W32GetUserSessionState` at `0x14011cc9d`
- `WIN32K!W32GetUserSessionState` at `0x14011cd6a`

## pseudocode

```c
HSPRITE __fastcall GreCreateSpriteInternal(
        Gre::Base *a1,
        HWND a2,
        struct tagRECT *a3,
        struct tagMINIWINDOWINFO *a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8,
        char a9,
        char a10,
        char a11,
        struct REGION *a12)
{
  HWND v14; // r13
  struct Gre::Base::SESSION_GLOBALS *v16; // rbx
  struct PDEVOBJ *v17; // rdx
  HSPRITE v18; // r15
  HSEMAPHORE v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 DwmSpriteObj; // rbx
  Gre::Base *v24; // rcx
  struct Gre::Base::SESSION_GLOBALS *v25; // rax
  __int64 v26; // r8
  DWMSPRITE *v27; // rdi
  SFMLOGICALSURFACE *v28; // r13
  struct tagRECT *v29; // rbx
  unsigned int v30; // ecx
  int v31; // edx
  int v32; // edx
  int v33; // eax
  struct REGION *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // ebx
  void *v38; // rax
  Gre::Base *v39; // rcx
  struct Gre::Base::SESSION_GLOBALS *v40; // rax
  HSPRITE v41; // rbx
  Gre::Base *v43; // rcx
  struct Gre::Base::SESSION_GLOBALS *v44; // rax
  __int64 v45; // r8
  void *v46; // rax
  struct DWMSPRITE *v47; // r8
  int v48; // [rsp+40h] [rbp-C0h]
  HSPRITE v49; // [rsp+48h] [rbp-B8h]
  struct REGION *v50; // [rsp+50h] [rbp-B0h] BYREF
  HWND v51; // [rsp+58h] [rbp-A8h]
  _OWORD v52[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWMSPRITE *v53; // [rsp+80h] [rbp-80h]
  HSPRITE NeighborSprite; // [rsp+88h] [rbp-78h]
  _OWORD v55[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  Gre::Base *v57; // [rsp+B8h] [rbp-48h] BYREF
  char v58[8]; // [rsp+C0h] [rbp-40h] BYREF
  HSEMAPHORE v59; // [rsp+C8h] [rbp-38h]
  char v60; // [rsp+D0h] [rbp-30h]
  _OWORD v61[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  __int64 v64; // [rsp+110h] [rbp+10h]
  _BYTE v65[96]; // [rsp+170h] [rbp+70h] BYREF

  v50 = a12;
  v14 = a2;
  v51 = a2;
  v16 = Gre::Base::Globals(a1);
  if ( !a6 || !(unsigned int)IsDwmActive() )
    return (HSPRITE)GdiCreateSprite((HDEV)a1, v14, a3);
  v48 = 1;
  v57 = a1;
  v18 = 0;
  DWMSPRITELOCK::DWMSPRITELOCK((DWMSPRITELOCK *)v58, v17, 0, 0);
  v19 = (HSEMAPHORE)(*(_QWORD *)v16 + 520LL);
  v60 = 0;
  v59 = v19;
  GreAcquireSemaphoreInternal(v19);
  GrepAcquireLockValidate<7>();
  if ( (unsigned int)IsDwmActive() )
  {
    memset_0(v61, 0, 0x88u);
    v48 = 0;
    if ( a4 )
      v22 = *((_QWORD *)a4 + 6);
    else
      v22 = *(_QWORD *)(W32GetUserSessionState(v21, v20) + 18760);
    memset(v52, 0, sizeof(v52));
    PushThreadGuardedObject(
      v52,
      v52,
      UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
    v53 = 0;
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v65);
    DwmSpriteObj = hspCreateDwmSpriteObj((Gre::Base *)v14, v22, (HDEV)a1, a8);
    v25 = Gre::Base::Globals(v24);
    if ( DwmSpriteObj )
    {
      LOBYTE(v26) = 15;
      v53 = (DWMSPRITE *)HmgLock(v25, DwmSpriteObj, v26);
    }
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v65);
    v27 = v53;
    if ( v53 )
    {
      v28 = (SFMLOGICALSURFACE *)*((_QWORD *)v53 + 18);
      v29 = (struct tagRECT *)((char *)v53 + 56);
      *((_DWORD *)v53 + 29) = 0;
      if ( a3 )
        *v29 = *a3;
      v30 = *((_DWORD *)v27 + 34) & 0xFFFFFFFE | (a7 != 0);
      *((_DWORD *)v27 + 34) = v30 ^ ((unsigned __int8)v30 ^ (unsigned __int8)(2 * a8)) & 2;
      v31 = *((_DWORD *)v28 + 63) ^ ((unsigned __int8)*((_DWORD *)v28 + 63) ^ (unsigned __int8)(16 * a8)) & 0x10;
      *((_DWORD *)v28 + 63) = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(4 * a9)) & 4;
      v32 = *((_DWORD *)v27 + 34) ^ ((unsigned __int8)*((_DWORD *)v27 + 34) ^ (unsigned __int8)(8 * a10)) & 8;
      v33 = v32 ^ ((unsigned __int8)v32 ^ (unsigned __int8)(a11 << 6)) & 0x40;
      v34 = v50;
      *((_DWORD *)v27 + 34) = v33;
      DWMSPRITE::vUpdateDpiScaling(v27, (const unsigned __int16 *)v34);
      v49 = *(HSPRITE *)v27;
      NeighborSprite = hspGetNeighborSprite(*(HSPRITE *)v27, 0, 1);
      if ( !v51 && !a4 )
      {
        if ( v27 != (DWMSPRITE *)-56LL )
        {
          v61[0] = *v29;
          v61[1] = v61[0];
        }
        v62 = 0;
        v63 = 0;
        a4 = (struct tagMINIWINDOWINFO *)v61;
        v64 = *(_QWORD *)(W32GetUserSessionState(v36, v35) + 18760);
      }
      if ( (*((_DWORD *)v28 + 63) & 4) != 0 )
      {
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v50);
        SFMLOGICALSURFACE::vDirtyRegionAccum(v28, v50);
      }
      v37 = *((_DWORD *)v28 + 63) & 0xC
          | *((_DWORD *)v27 + 34) & 1
          | (2 * (*((_DWORD *)v28 + 63) & 1 | *((_DWORD *)v27 + 34) & 0x40 | (4 * (*((_DWORD *)v27 + 34) & 0xE))));
      v38 = (void *)UserReferenceDwmApiPort();
      v14 = v51;
      if ( (int)DwmAsyncCreateSprite(v38, v37, (__int64)a4, a5) < 0 )
      {
        v47 = v53;
        if ( v53 )
          _InterlockedDecrement16((volatile signed __int16 *)v53 + 6);
        v53 = 0;
        vspDestroyDwmSpriteObjInternal((HDEV)a1, 0, v47);
      }
      else
      {
        v40 = Gre::Base::Globals(v39);
        v41 = NeighborSprite;
        if ( NeighborSprite && *(_QWORD *)(*((_QWORD *)v40 + 28) + 144LL) )
        {
          memset(v55, 0, sizeof(v55));
          PushThreadGuardedObject(
            v55,
            v55,
            UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
          v56 = 0;
          v44 = Gre::Base::Globals(v43);
          LOBYTE(v45) = 15;
          v56 = HmgLock(v44, v41, v45);
          v46 = (void *)UserReferenceDwmApiPort();
          DwmAsyncZorderSprite(v46);
          if ( v56 )
            _InterlockedDecrement16((volatile signed __int16 *)(v56 + 12));
          v56 = 0;
          PopThreadGuardedObject(v55);
        }
        *((_DWORD *)v27 + 28) = (unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC;
        v18 = v49;
        *((_BYTE *)v27 + 126) = (unsigned int)UserIsCurrentProcessImmersiveAppContainer() != 0;
      }
      if ( v53 )
        _InterlockedDecrement16((volatile signed __int16 *)v53 + 6);
    }
    v53 = 0;
    PopThreadGuardedObject(v52);
  }
  ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON((ENTER_DWM_CRIT_COMMON *)&v57);
  if ( v48 )
    return (HSPRITE)GdiCreateSprite((HDEV)a1, v14, a3);
  return v18;
}

```

## disassembly

```asm
0x14011c8e4  push    rbp
0x14011c8e6  push    rbx
0x14011c8e7  push    rsi
0x14011c8e8  push    rdi
0x14011c8e9  push    r12
0x14011c8eb  push    r13
0x14011c8ed  push    r14
0x14011c8ef  push    r15
0x14011c8f1  lea     rbp, [rsp-0E8h]
0x14011c8f9  sub     rsp, 1E8h
0x14011c900  mov     rax, cs:__security_cookie
0x14011c907  xor     rax, rsp
0x14011c90a  mov     [rbp+120h+var_50], rax
0x14011c911  mov     rax, [rbp+120h+arg_58]
0x14011c918  mov     rsi, r9
0x14011c91b  mov     edi, [rbp+120h+arg_38]
0x14011c921  mov     r12, r8
0x14011c924  mov     [rsp+220h+var_1D0], rax
0x14011c929  mov     r13, rdx
0x14011c92c  mov     [rsp+220h+var_1C8], rdx
0x14011c931  mov     r14, rcx
0x14011c934  mov     dword ptr [rsp+220h+var_1D8], edi
0x14011c938  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011c93f  nop     dword ptr [rax+rax+00h]
0x14011c944  cmp     [rbp+120h+arg_28], 0
0x14011c94b  mov     rbx, rax
0x14011c94e  jz      loc_14011CC8A
0x14011c954  call    IsDwmActive
0x14011c959  test    eax, eax
0x14011c95b  jz      loc_14011CC8A
0x14011c961  xor     r9d, r9d; int
0x14011c964  mov     [rsp+220h+var_1E0], 1
0x14011c96c  xor     r8d, r8d; int
0x14011c96f  mov     [rbp+120h+var_168], r14
0x14011c973  lea     rcx, [rbp+120h+var_160]; this
0x14011c977  xor     r15d, r15d
0x14011c97a  call    ??0DWMSPRITELOCK@@QEAA@AEAVPDEVOBJ@@HH@Z; DWMSPRITELOCK::DWMSPRITELOCK(PDEVOBJ &,int,int)
0x14011c97f  mov     rcx, [rbx]
0x14011c982  add     rcx, 208h
0x14011c989  mov     [rbp+120h+var_150], r15b
0x14011c98d  mov     [rbp+120h+var_158], rcx
0x14011c991  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14011c998  nop     dword ptr [rax+rax+00h]
0x14011c99d  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x14011c9a2  call    IsDwmActive
0x14011c9a7  test    eax, eax
0x14011c9a9  jz      loc_14011CC53
0x14011c9af  xor     edx, edx; Val
0x14011c9b1  lea     rcx, [rbp+120h+var_140]; void *
0x14011c9b5  mov     r8d, 88h; Size
0x14011c9bb  call    memset_0
0x14011c9c0  mov     [rsp+220h+var_1E0], r15d
0x14011c9c5  test    rsi, rsi
0x14011c9c8  jz      loc_14011CC9D
0x14011c9ce  mov     rbx, [rsi+30h]
0x14011c9d2  xorps   xmm0, xmm0
0x14011c9d5  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14011c9dc  lea     rdx, [rsp+220h+var_1C0]
0x14011c9e1  lea     rcx, [rsp+220h+var_1C0]
0x14011c9e6  movups  [rsp+220h+var_1C0], xmm0
0x14011c9eb  movups  [rsp+220h+var_1B0], xmm0
0x14011c9f0  call    cs:__imp_PushThreadGuardedObject
0x14011c9f7  nop     dword ptr [rax+rax+00h]
0x14011c9fc  lea     rcx, [rbp+120h+var_B0]
0x14011ca00  mov     [rbp+120h+var_1A0], r15
0x14011ca04  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x14011ca0b  nop     dword ptr [rax+rax+00h]
0x14011ca10  mov     r9d, edi; int
0x14011ca13  mov     r8, r14; HDEV
0x14011ca16  mov     rdx, rbx; unsigned __int64
0x14011ca19  mov     rcx, r13; HWND
0x14011ca1c  call    ?hspCreateDwmSpriteObj@@YAPEAUHSPRITE__@@PEAUHWND__@@_KPEAUHDEV__@@H@Z; hspCreateDwmSpriteObj(HWND__ *,unsigned __int64,HDEV__ *,int)
0x14011ca21  mov     rbx, rax
0x14011ca24  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011ca2b  nop     dword ptr [rax+rax+00h]
0x14011ca30  test    rbx, rbx
0x14011ca33  jz      short loc_14011CA51
0x14011ca35  xor     r9d, r9d
0x14011ca38  mov     r8b, 0Fh
0x14011ca3b  mov     rdx, rbx
0x14011ca3e  mov     rcx, rax
0x14011ca41  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011ca48  nop     dword ptr [rax+rax+00h]
0x14011ca4d  mov     [rbp+120h+var_1A0], rax
0x14011ca51  lea     rcx, [rbp+120h+var_B0]
0x14011ca55  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14011ca5c  nop     dword ptr [rax+rax+00h]
0x14011ca61  mov     rdi, [rbp+120h+var_1A0]
0x14011ca65  test    rdi, rdi
0x14011ca68  jz      loc_14011CC3A
0x14011ca6e  mov     r13, [rdi+90h]
0x14011ca75  lea     rbx, [rdi+38h]
0x14011ca79  mov     [rdi+74h], r15d
0x14011ca7d  test    r12, r12
0x14011ca80  jz      short loc_14011CA8B
0x14011ca82  movups  xmm0, xmmword ptr [r12]
0x14011ca87  movdqu  xmmword ptr [rbx], xmm0
0x14011ca8b  mov     eax, [rdi+88h]
0x14011ca91  xor     ecx, ecx
0x14011ca93  cmp     [rbp+120h+arg_30], ecx
0x14011ca99  mov     edx, dword ptr [rsp+220h+var_1D8]
0x14011ca9d  setnz   cl
0x14011caa0  and     eax, 0FFFFFFFEh
0x14011caa3  or      ecx, eax
0x14011caa5  lea     eax, [rdx+rdx]
0x14011caa8  shl     edx, 4
0x14011caab  xor     eax, ecx
0x14011caad  and     eax, 2
0x14011cab0  xor     eax, ecx
0x14011cab2  mov     [rdi+88h], eax
0x14011cab8  mov     eax, [r13+0FCh]
0x14011cabf  xor     edx, eax
0x14011cac1  and     edx, 10h
0x14011cac4  xor     edx, eax
0x14011cac6  mov     eax, dword ptr [rbp+120h+arg_40]
0x14011cacc  shl     eax, 2
0x14011cacf  xor     eax, edx
0x14011cad1  and     eax, 4
0x14011cad4  xor     eax, edx
0x14011cad6  mov     [r13+0FCh], eax
0x14011cadd  mov     ecx, [rdi+88h]
0x14011cae3  mov     eax, dword ptr [rbp+120h+arg_48]
0x14011cae9  lea     edx, ds:0[rax*8]
0x14011caf0  mov     eax, dword ptr [rbp+120h+arg_50]
0x14011caf6  xor     edx, ecx
0x14011caf8  shl     eax, 6
0x14011cafb  and     edx, 8
0x14011cafe  xor     edx, ecx
0x14011cb00  mov     rcx, rdi; this
0x14011cb03  xor     eax, edx
0x14011cb05  and     eax, 40h
0x14011cb08  xor     eax, edx
0x14011cb0a  mov     rdx, [rsp+220h+var_1D0]; unsigned __int16 *
0x14011cb0f  mov     [rdi+88h], eax
0x14011cb15  call    ?vUpdateDpiScaling@DWMSPRITE@@QEAAXPEBG@Z; DWMSPRITE::vUpdateDpiScaling(ushort const *)
0x14011cb1a  mov     rax, [rdi]
0x14011cb1d  mov     r8b, 1; bool
0x14011cb20  mov     rcx, rax; HSPRITE
0x14011cb23  mov     [rsp+220h+var_1D8], rax
0x14011cb28  xor     edx, edx; bool
0x14011cb2a  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14011cb2f  mov     [rbp+120h+var_198], rax
0x14011cb33  xor     eax, eax
0x14011cb35  cmp     [rsp+220h+var_1C8], rax
0x14011cb3a  jz      loc_14011CD48
0x14011cb40  mov     eax, [r13+0FCh]
0x14011cb47  test    al, 4
0x14011cb49  jz      short loc_14011CB69
0x14011cb4b  lea     rcx, [rsp+220h+var_1D0]
0x14011cb50  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14011cb57  nop     dword ptr [rax+rax+00h]
0x14011cb5c  mov     rdx, [rsp+220h+var_1D0]; struct REGION *
0x14011cb61  mov     rcx, r13; this
0x14011cb64  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x14011cb69  mov     ecx, [rdi+88h]
0x14011cb6f  mov     ebx, ecx
0x14011cb71  mov     edx, [r13+0FCh]
0x14011cb78  and     ebx, 0Eh
0x14011cb7b  shl     ebx, 2
0x14011cb7e  mov     eax, ecx
0x14011cb80  and     eax, 40h
0x14011cb83  and     ecx, 1
0x14011cb86  or      ebx, eax
0x14011cb88  mov     eax, edx
0x14011cb8a  and     eax, 1
0x14011cb8d  and     edx, 0Ch
0x14011cb90  or      ebx, eax
0x14011cb92  add     ebx, ebx
0x14011cb94  or      ebx, ecx
0x14011cb96  or      ebx, edx
0x14011cb98  call    cs:__imp_UserReferenceDwmApiPort
0x14011cb9f  nop     dword ptr [rax+rax+00h]
0x14011cba4  mov     ecx, [rbp+120h+arg_20]
0x14011cbaa  mov     r9, r12
0x14011cbad  mov     r13, [rsp+220h+var_1C8]
0x14011cbb2  mov     [rsp+220h+var_1F0], ecx; int
0x14011cbb6  mov     r8, r13
0x14011cbb9  mov     [rsp+220h+var_1F8], rsi; __int64
0x14011cbbe  mov     rcx, rax; Object
0x14011cbc1  mov     rsi, [rsp+220h+var_1D8]
0x14011cbc6  mov     rdx, rsi
0x14011cbc9  mov     [rsp+220h+var_200], ebx; int
0x14011cbcd  call    DwmAsyncCreateSprite
0x14011cbd2  test    eax, eax
0x14011cbd4  js      loc_14011CD8A
0x14011cbda  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011cbe1  nop     dword ptr [rax+rax+00h]
0x14011cbe6  mov     rbx, [rbp+120h+var_198]
0x14011cbea  test    rbx, rbx
0x14011cbed  jz      short loc_14011CC03
0x14011cbef  mov     rax, [rax+0E0h]
0x14011cbf6  cmp     [rax+90h], r15
0x14011cbfd  jnz     loc_14011CCB5
0x14011cc03  call    cs:__imp_PsGetCurrentProcessId
0x14011cc0a  nop     dword ptr [rax+rax+00h]
0x14011cc0f  and     eax, 0FFFFFFFCh
0x14011cc12  mov     [rdi+70h], eax
0x14011cc15  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x14011cc1c  nop     dword ptr [rax+rax+00h]
0x14011cc21  test    eax, eax
0x14011cc23  mov     r15, rsi
0x14011cc26  setnz   al
0x14011cc29  mov     [rdi+7Eh], al
0x14011cc2c  mov     rax, [rbp+120h+var_1A0]
0x14011cc30  test    rax, rax
0x14011cc33  jz      short loc_14011CC3A
0x14011cc35  lock dec word ptr [rax+0Ch]
0x14011cc3a  lea     rcx, [rsp+220h+var_1C0]
0x14011cc3f  mov     [rbp+120h+var_1A0], 0
0x14011cc47  call    cs:__imp_PopThreadGuardedObject
0x14011cc4e  nop     dword ptr [rax+rax+00h]
0x14011cc53  lea     rcx, [rbp+120h+var_168]; this
0x14011cc57  call    ??1ENTER_DWM_CRIT_COMMON@@QEAA@XZ; ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON(void)
0x14011cc5c  cmp     [rsp+220h+var_1E0], 0
0x14011cc61  jnz     short loc_14011CC8A
0x14011cc63  mov     rax, r15
0x14011cc66  mov     rcx, [rbp+120h+var_50]
0x14011cc6d  xor     rcx, rsp; StackCookie
0x14011cc70  call    __security_check_cookie
0x14011cc75  add     rsp, 1E8h
0x14011cc7c  pop     r15
0x14011cc7e  pop     r14
0x14011cc80  pop     r13
0x14011cc82  pop     r12
0x14011cc84  pop     rdi
0x14011cc85  pop     rsi
0x14011cc86  pop     rbx
0x14011cc87  pop     rbp
0x14011cc88  retn
0x14011cc8a  mov     r8, r12; struct tagRECT *
0x14011cc8d  mov     rdx, r13; HWND
0x14011cc90  mov     rcx, r14; HDEV
0x14011cc93  call    ?GdiCreateSprite@@YAPEAXPEAUHDEV__@@PEAUHWND__@@PEAUtagRECT@@@Z; GdiCreateSprite(HDEV__ *,HWND__ *,tagRECT *)
0x14011cc98  mov     r15, rax
0x14011cc9b  jmp     short loc_14011CC63
0x14011cc9d  call    cs:__imp_W32GetUserSessionState
0x14011cca4  nop     dword ptr [rax+rax+00h]
0x14011cca9  mov     rbx, [rax+4948h]
0x14011ccb0  jmp     loc_14011C9D2
0x14011ccb5  xorps   xmm0, xmm0
0x14011ccb8  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14011ccbf  lea     rdx, [rbp+120h+var_190]
0x14011ccc3  lea     rcx, [rbp+120h+var_190]
0x14011ccc7  movups  [rbp+120h+var_190], xmm0
0x14011cccb  movups  [rbp+120h+var_180], xmm0
0x14011cccf  call    cs:__imp_PushThreadGuardedObject
0x14011ccd6  nop     dword ptr [rax+rax+00h]
0x14011ccdb  mov     [rbp+120h+var_170], r15
0x14011ccdf  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011cce6  nop     dword ptr [rax+rax+00h]
0x14011cceb  xor     r9d, r9d
0x14011ccee  mov     r8b, 0Fh
0x14011ccf1  mov     rcx, rax
0x14011ccf4  mov     rdx, rbx
0x14011ccf7  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011ccfe  nop     dword ptr [rax+rax+00h]
0x14011cd03  mov     [rbp+120h+var_170], rax
0x14011cd07  call    cs:__imp_UserReferenceDwmApiPort
0x14011cd0e  nop     dword ptr [rax+rax+00h]
0x14011cd13  mov     r8, rbx
0x14011cd16  mov     rdx, rsi
0x14011cd19  mov     rcx, rax; Object
0x14011cd1c  call    DwmAsyncZorderSprite
0x14011cd21  mov     rax, [rbp+120h+var_170]
0x14011cd25  test    rax, rax
0x14011cd28  jz      short loc_14011CD2F
0x14011cd2a  lock dec word ptr [rax+0Ch]
0x14011cd2f  lea     rcx, [rbp+120h+var_190]
0x14011cd33  mov     [rbp+120h+var_170], r15
0x14011cd37  call    cs:__imp_PopThreadGuardedObject
0x14011cd3e  nop     dword ptr [rax+rax+00h]
0x14011cd43  jmp     loc_14011CC03
0x14011cd48  test    rsi, rsi
0x14011cd4b  jnz     loc_14011CB40
0x14011cd51  test    rbx, rbx
0x14011cd54  jz      short loc_14011CD62
0x14011cd56  movups  xmm0, xmmword ptr [rbx]
0x14011cd59  movaps  [rbp+120h+var_140], xmm0
0x14011cd5d  movdqu  [rbp+120h+var_130], xmm0
0x14011cd62  mov     [rbp+120h+var_120], rax
0x14011cd66  mov     [rbp+120h+var_118], rax
0x14011cd6a  call    cs:__imp_W32GetUserSessionState
0x14011cd71  nop     dword ptr [rax+rax+00h]
0x14011cd76  lea     rsi, [rbp+120h+var_140]
0x14011cd7a  mov     rcx, [rax+4948h]
0x14011cd81  mov     [rbp+120h+var_110], rcx
0x14011cd85  jmp     loc_14011CB40
0x14011cd8a  mov     r8, [rbp+120h+var_1A0]; struct DWMSPRITE *
0x14011cd8e  test    r8, r8
0x14011cd91  jz      short loc_14011CD99
0x14011cd93  lock dec word ptr [r8+0Ch]
0x14011cd99  xor     edx, edx; bool
0x14011cd9b  mov     [rbp+120h+var_1A0], r15
0x14011cd9f  mov     rcx, r14; HDEV
0x14011cda2  call    ?vspDestroyDwmSpriteObjInternal@@YAXPEAUHDEV__@@_NPEAVDWMSPRITE@@@Z; vspDestroyDwmSpriteObjInternal(HDEV__ *,bool,DWMSPRITE *)
0x14011cda7  jmp     loc_14011CC2C
```
