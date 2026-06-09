# GreCreateSpriteInternal(HDEV__ *,HWND__ *,tagRECT *,tagMINIWINDOWINFO *,ulong,int,int,int,int,int,int,ushort const *)

- ea: `0x14008acd0`
- end: `0x14008b198`
- name: `?GreCreateSpriteInternal@@YAPEAXPEAUHDEV__@@PEAUHWND__@@PEAUtagRECT@@PEAUtagMINIWINDOWINFO@@KHHHHHHPEBG@Z`
- size: `1224`
- prototype: `void *(HDEV, HWND, struct tagRECT *, struct tagMINIWINDOWINFO *, unsigned int, int, int, int, int, int, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008a1c0`
- `0x14008abf8`
- `0x140197108`
- `0x14020e2b0`

## callees

- `0x1400875b8`
- `0x14008a670`
- `0x14008acd0`
- `0x14008b1a0`
- `0x14008b800`
- `0x14008b8d0`
- `0x14008be9c`
- `0x140090228`
- `0x140090290`
- `0x140093570`
- `0x14016a0a0`
- `0x1401a27c0`
- `0x1401e060c`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14008afef`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14008afef`
- `win32kbase!UserReferenceDwmApiPort` at `0x14008af84`
- `win32kbase!UserReferenceDwmApiPort` at `0x14008b0f3`
- `win32kbase!UserReferenceDwmApiPort` at `0x14008af84`
- `win32kbase!UserReferenceDwmApiPort` at `0x14008b0f3`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14008b001`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x14008b001`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ad24`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ae10`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008afc6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b0cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ad24`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ae10`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008afc6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008b0cb`
- `win32kbase!PopThreadGuardedObject` at `0x14008b033`
- `win32kbase!PopThreadGuardedObject` at `0x14008b123`
- `win32kbase!PopThreadGuardedObject` at `0x14008b033`
- `win32kbase!PopThreadGuardedObject` at `0x14008b123`
- `win32kbase!PushThreadGuardedObject` at `0x14008addc`
- `win32kbase!PushThreadGuardedObject` at `0x14008b0bb`
- `win32kbase!PushThreadGuardedObject` at `0x14008addc`
- `win32kbase!PushThreadGuardedObject` at `0x14008b0bb`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008af3c`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008af3c`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14008ad7d`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x14008ad7d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008ae2d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b0e3`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008ae2d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14008b0e3`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008adf0`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008adf0`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008ae41`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14008ae41`
- `WIN32K!W32GetUserSessionState` at `0x14008b089`
- `WIN32K!W32GetUserSessionState` at `0x14008b156`
- `WIN32K!W32GetUserSessionState` at `0x14008b089`
- `WIN32K!W32GetUserSessionState` at `0x14008b156`

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
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 DwmSpriteObj; // rbx
  Gre::Base *v23; // rcx
  struct Gre::Base::SESSION_GLOBALS *v24; // rax
  __int64 v25; // r8
  DWMSPRITE *v26; // rdi
  SFMLOGICALSURFACE *v27; // r13
  struct tagRECT *v28; // rbx
  unsigned int v29; // ecx
  int v30; // edx
  int v31; // edx
  int v32; // eax
  struct REGION *v33; // rdx
  __int64 v34; // rcx
  int v35; // ebx
  void *v36; // rax
  Gre::Base *v37; // rcx
  struct Gre::Base::SESSION_GLOBALS *v38; // rax
  HSPRITE v39; // rbx
  Gre::Base *v41; // rcx
  struct Gre::Base::SESSION_GLOBALS *v42; // rax
  __int64 v43; // r8
  void *v44; // rax
  struct DWMSPRITE *v45; // r8
  int v46; // [rsp+40h] [rbp-C0h]
  HSPRITE v47; // [rsp+48h] [rbp-B8h]
  struct REGION *v48; // [rsp+50h] [rbp-B0h] BYREF
  HWND v49; // [rsp+58h] [rbp-A8h]
  _OWORD v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWMSPRITE *v51; // [rsp+80h] [rbp-80h]
  HSPRITE NeighborSprite; // [rsp+88h] [rbp-78h]
  _OWORD v53[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h]
  Gre::Base *v55; // [rsp+B8h] [rbp-48h] BYREF
  char v56[8]; // [rsp+C0h] [rbp-40h] BYREF
  HSEMAPHORE v57; // [rsp+C8h] [rbp-38h]
  char v58; // [rsp+D0h] [rbp-30h]
  _OWORD v59[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  _BYTE v63[96]; // [rsp+170h] [rbp+70h] BYREF

  v48 = a12;
  v14 = a2;
  v49 = a2;
  v16 = Gre::Base::Globals(a1);
  if ( !a6 || !(unsigned int)IsDwmActive() )
    return (HSPRITE)GdiCreateSprite((HDEV)a1, v14, a3);
  v46 = 1;
  v55 = a1;
  v18 = 0;
  DWMSPRITELOCK::DWMSPRITELOCK((DWMSPRITELOCK *)v56, v17, 0, 0);
  v19 = (HSEMAPHORE)(*(_QWORD *)v16 + 520LL);
  v58 = 0;
  v57 = v19;
  GreAcquireSemaphoreInternal(v19);
  GrepAcquireLockValidate<7>();
  if ( (unsigned int)IsDwmActive() )
  {
    memset_0(v59, 0, 0x88u);
    v46 = 0;
    if ( a4 )
      v21 = *((_QWORD *)a4 + 6);
    else
      v21 = *(_QWORD *)(W32GetUserSessionState(v20) + 18760);
    memset(v50, 0, sizeof(v50));
    PushThreadGuardedObject(
      v50,
      v50,
      UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
    v51 = 0;
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v63);
    DwmSpriteObj = hspCreateDwmSpriteObj((Gre::Base *)v14, v21, (HDEV)a1, a8);
    v24 = Gre::Base::Globals(v23);
    if ( DwmSpriteObj )
    {
      LOBYTE(v25) = 15;
      v51 = (DWMSPRITE *)HmgLock(v24, DwmSpriteObj, v25);
    }
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v63);
    v26 = v51;
    if ( v51 )
    {
      v27 = (SFMLOGICALSURFACE *)*((_QWORD *)v51 + 18);
      v28 = (struct tagRECT *)((char *)v51 + 56);
      *((_DWORD *)v51 + 29) = 0;
      if ( a3 )
        *v28 = *a3;
      v29 = *((_DWORD *)v26 + 34) & 0xFFFFFFFE | (a7 != 0);
      *((_DWORD *)v26 + 34) = v29 ^ ((unsigned __int8)v29 ^ (unsigned __int8)(2 * a8)) & 2;
      v30 = *((_DWORD *)v27 + 63) ^ ((unsigned __int8)*((_DWORD *)v27 + 63) ^ (unsigned __int8)(16 * a8)) & 0x10;
      *((_DWORD *)v27 + 63) = v30 ^ ((unsigned __int8)v30 ^ (unsigned __int8)(4 * a9)) & 4;
      v31 = *((_DWORD *)v26 + 34) ^ ((unsigned __int8)*((_DWORD *)v26 + 34) ^ (unsigned __int8)(8 * a10)) & 8;
      v32 = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(a11 << 6)) & 0x40;
      v33 = v48;
      *((_DWORD *)v26 + 34) = v32;
      DWMSPRITE::vUpdateDpiScaling(v26, (const unsigned __int16 *)v33);
      v47 = *(HSPRITE *)v26;
      NeighborSprite = hspGetNeighborSprite(*(HSPRITE *)v26, 0, 1);
      if ( !v49 && !a4 )
      {
        if ( v26 != (DWMSPRITE *)-56LL )
        {
          v59[0] = *v28;
          v59[1] = v59[0];
        }
        v60 = 0;
        v61 = 0;
        a4 = (struct tagMINIWINDOWINFO *)v59;
        v62 = *(_QWORD *)(W32GetUserSessionState(v34) + 18760);
      }
      if ( (*((_DWORD *)v27 + 63) & 4) != 0 )
      {
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v48);
        SFMLOGICALSURFACE::vDirtyRegionAccum(v27, v48);
      }
      v35 = *((_DWORD *)v27 + 63) & 0xC
          | *((_DWORD *)v26 + 34) & 1
          | (2 * (*((_DWORD *)v27 + 63) & 1 | *((_DWORD *)v26 + 34) & 0x40 | (4 * (*((_DWORD *)v26 + 34) & 0xE))));
      v36 = (void *)UserReferenceDwmApiPort();
      v14 = v49;
      if ( (int)DwmAsyncCreateSprite(v36, v35, (__int64)a4, a5) < 0 )
      {
        v45 = v51;
        if ( v51 )
          _InterlockedDecrement16((volatile signed __int16 *)v51 + 6);
        v51 = 0;
        vspDestroyDwmSpriteObjInternal((HDEV)a1, 0, v45);
      }
      else
      {
        v38 = Gre::Base::Globals(v37);
        v39 = NeighborSprite;
        if ( NeighborSprite && *(_QWORD *)(*((_QWORD *)v38 + 28) + 144LL) )
        {
          memset(v53, 0, sizeof(v53));
          PushThreadGuardedObject(
            v53,
            v53,
            UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
          v54 = 0;
          v42 = Gre::Base::Globals(v41);
          LOBYTE(v43) = 15;
          v54 = HmgLock(v42, v39, v43);
          v44 = (void *)UserReferenceDwmApiPort();
          DwmAsyncZorderSprite(v44);
          if ( v54 )
            _InterlockedDecrement16((volatile signed __int16 *)(v54 + 12));
          v54 = 0;
          PopThreadGuardedObject(v53);
        }
        *((_DWORD *)v26 + 28) = (unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC;
        v18 = v47;
        *((_BYTE *)v26 + 126) = (unsigned int)UserIsCurrentProcessImmersiveAppContainer() != 0;
      }
      if ( v51 )
        _InterlockedDecrement16((volatile signed __int16 *)v51 + 6);
    }
    v51 = 0;
    PopThreadGuardedObject(v50);
  }
  ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON((ENTER_DWM_CRIT_COMMON *)&v55);
  if ( v46 )
    return (HSPRITE)GdiCreateSprite((HDEV)a1, v14, a3);
  return v18;
}

```

## disassembly

```asm
0x14008acd0  push    rbp
0x14008acd2  push    rbx
0x14008acd3  push    rsi
0x14008acd4  push    rdi
0x14008acd5  push    r12
0x14008acd7  push    r13
0x14008acd9  push    r14
0x14008acdb  push    r15
0x14008acdd  lea     rbp, [rsp-0E8h]
0x14008ace5  sub     rsp, 1E8h
0x14008acec  mov     rax, cs:__security_cookie
0x14008acf3  xor     rax, rsp
0x14008acf6  mov     [rbp+120h+var_50], rax
0x14008acfd  mov     rax, [rbp+120h+arg_58]
0x14008ad04  mov     rsi, r9
0x14008ad07  mov     edi, [rbp+120h+arg_38]
0x14008ad0d  mov     r12, r8
0x14008ad10  mov     [rsp+220h+var_1D0], rax
0x14008ad15  mov     r13, rdx
0x14008ad18  mov     [rsp+220h+var_1C8], rdx
0x14008ad1d  mov     r14, rcx
0x14008ad20  mov     dword ptr [rsp+220h+var_1D8], edi
0x14008ad24  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008ad2b  nop     dword ptr [rax+rax+00h]
0x14008ad30  cmp     [rbp+120h+arg_28], 0
0x14008ad37  mov     rbx, rax
0x14008ad3a  jz      loc_14008B076
0x14008ad40  call    IsDwmActive
0x14008ad45  test    eax, eax
0x14008ad47  jz      loc_14008B076
0x14008ad4d  xor     r9d, r9d; int
0x14008ad50  mov     [rsp+220h+var_1E0], 1
0x14008ad58  xor     r8d, r8d; int
0x14008ad5b  mov     [rbp+120h+var_168], r14
0x14008ad5f  lea     rcx, [rbp+120h+var_160]; this
0x14008ad63  xor     r15d, r15d
0x14008ad66  call    ??0DWMSPRITELOCK@@QEAA@AEAVPDEVOBJ@@HH@Z; DWMSPRITELOCK::DWMSPRITELOCK(PDEVOBJ &,int,int)
0x14008ad6b  mov     rcx, [rbx]
0x14008ad6e  add     rcx, 208h
0x14008ad75  mov     [rbp+120h+var_150], r15b
0x14008ad79  mov     [rbp+120h+var_158], rcx
0x14008ad7d  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14008ad84  nop     dword ptr [rax+rax+00h]
0x14008ad89  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x14008ad8e  call    IsDwmActive
0x14008ad93  test    eax, eax
0x14008ad95  jz      loc_14008B03F
0x14008ad9b  xor     edx, edx; Val
0x14008ad9d  lea     rcx, [rbp+120h+var_140]; void *
0x14008ada1  mov     r8d, 88h; Size
0x14008ada7  call    memset_0
0x14008adac  mov     [rsp+220h+var_1E0], r15d
0x14008adb1  test    rsi, rsi
0x14008adb4  jz      loc_14008B089
0x14008adba  mov     rbx, [rsi+30h]
0x14008adbe  xorps   xmm0, xmm0
0x14008adc1  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14008adc8  lea     rdx, [rsp+220h+var_1C0]
0x14008adcd  lea     rcx, [rsp+220h+var_1C0]
0x14008add2  movups  [rsp+220h+var_1C0], xmm0
0x14008add7  movups  [rsp+220h+var_1B0], xmm0
0x14008addc  call    cs:__imp_PushThreadGuardedObject
0x14008ade3  nop     dword ptr [rax+rax+00h]
0x14008ade8  lea     rcx, [rbp+120h+var_B0]
0x14008adec  mov     [rbp+120h+var_1A0], r15
0x14008adf0  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x14008adf7  nop     dword ptr [rax+rax+00h]
0x14008adfc  mov     r9d, edi; int
0x14008adff  mov     r8, r14; HDEV
0x14008ae02  mov     rdx, rbx; unsigned __int64
0x14008ae05  mov     rcx, r13; HWND
0x14008ae08  call    ?hspCreateDwmSpriteObj@@YAPEAUHSPRITE__@@PEAUHWND__@@_KPEAUHDEV__@@H@Z; hspCreateDwmSpriteObj(HWND__ *,unsigned __int64,HDEV__ *,int)
0x14008ae0d  mov     rbx, rax
0x14008ae10  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008ae17  nop     dword ptr [rax+rax+00h]
0x14008ae1c  test    rbx, rbx
0x14008ae1f  jz      short loc_14008AE3D
0x14008ae21  xor     r9d, r9d
0x14008ae24  mov     r8b, 0Fh
0x14008ae27  mov     rdx, rbx
0x14008ae2a  mov     rcx, rax
0x14008ae2d  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008ae34  nop     dword ptr [rax+rax+00h]
0x14008ae39  mov     [rbp+120h+var_1A0], rax
0x14008ae3d  lea     rcx, [rbp+120h+var_B0]
0x14008ae41  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x14008ae48  nop     dword ptr [rax+rax+00h]
0x14008ae4d  mov     rdi, [rbp+120h+var_1A0]
0x14008ae51  test    rdi, rdi
0x14008ae54  jz      loc_14008B026
0x14008ae5a  mov     r13, [rdi+90h]
0x14008ae61  lea     rbx, [rdi+38h]
0x14008ae65  mov     [rdi+74h], r15d
0x14008ae69  test    r12, r12
0x14008ae6c  jz      short loc_14008AE77
0x14008ae6e  movups  xmm0, xmmword ptr [r12]
0x14008ae73  movdqu  xmmword ptr [rbx], xmm0
0x14008ae77  mov     eax, [rdi+88h]
0x14008ae7d  xor     ecx, ecx
0x14008ae7f  cmp     [rbp+120h+arg_30], ecx
0x14008ae85  mov     edx, dword ptr [rsp+220h+var_1D8]
0x14008ae89  setnz   cl
0x14008ae8c  and     eax, 0FFFFFFFEh
0x14008ae8f  or      ecx, eax
0x14008ae91  lea     eax, [rdx+rdx]
0x14008ae94  shl     edx, 4
0x14008ae97  xor     eax, ecx
0x14008ae99  and     eax, 2
0x14008ae9c  xor     eax, ecx
0x14008ae9e  mov     [rdi+88h], eax
0x14008aea4  mov     eax, [r13+0FCh]
0x14008aeab  xor     edx, eax
0x14008aead  and     edx, 10h
0x14008aeb0  xor     edx, eax
0x14008aeb2  mov     eax, dword ptr [rbp+120h+arg_40]
0x14008aeb8  shl     eax, 2
0x14008aebb  xor     eax, edx
0x14008aebd  and     eax, 4
0x14008aec0  xor     eax, edx
0x14008aec2  mov     [r13+0FCh], eax
0x14008aec9  mov     ecx, [rdi+88h]
0x14008aecf  mov     eax, dword ptr [rbp+120h+arg_48]
0x14008aed5  lea     edx, ds:0[rax*8]
0x14008aedc  mov     eax, dword ptr [rbp+120h+arg_50]
0x14008aee2  xor     edx, ecx
0x14008aee4  shl     eax, 6
0x14008aee7  and     edx, 8
0x14008aeea  xor     edx, ecx
0x14008aeec  mov     rcx, rdi; this
0x14008aeef  xor     eax, edx
0x14008aef1  and     eax, 40h
0x14008aef4  xor     eax, edx
0x14008aef6  mov     rdx, [rsp+220h+var_1D0]; unsigned __int16 *
0x14008aefb  mov     [rdi+88h], eax
0x14008af01  call    ?vUpdateDpiScaling@DWMSPRITE@@QEAAXPEBG@Z; DWMSPRITE::vUpdateDpiScaling(ushort const *)
0x14008af06  mov     rax, [rdi]
0x14008af09  mov     r8b, 1; bool
0x14008af0c  mov     rcx, rax; HSPRITE
0x14008af0f  mov     [rsp+220h+var_1D8], rax
0x14008af14  xor     edx, edx; bool
0x14008af16  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14008af1b  mov     [rbp+120h+var_198], rax
0x14008af1f  xor     eax, eax
0x14008af21  cmp     [rsp+220h+var_1C8], rax
0x14008af26  jz      loc_14008B134
0x14008af2c  mov     eax, [r13+0FCh]
0x14008af33  test    al, 4
0x14008af35  jz      short loc_14008AF55
0x14008af37  lea     rcx, [rsp+220h+var_1D0]
0x14008af3c  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14008af43  nop     dword ptr [rax+rax+00h]
0x14008af48  mov     rdx, [rsp+220h+var_1D0]; struct REGION *
0x14008af4d  mov     rcx, r13; this
0x14008af50  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x14008af55  mov     ecx, [rdi+88h]
0x14008af5b  mov     ebx, ecx
0x14008af5d  mov     edx, [r13+0FCh]
0x14008af64  and     ebx, 0Eh
0x14008af67  shl     ebx, 2
0x14008af6a  mov     eax, ecx
0x14008af6c  and     eax, 40h
0x14008af6f  and     ecx, 1
0x14008af72  or      ebx, eax
0x14008af74  mov     eax, edx
0x14008af76  and     eax, 1
0x14008af79  and     edx, 0Ch
0x14008af7c  or      ebx, eax
0x14008af7e  add     ebx, ebx
0x14008af80  or      ebx, ecx
0x14008af82  or      ebx, edx
0x14008af84  call    cs:__imp_UserReferenceDwmApiPort
0x14008af8b  nop     dword ptr [rax+rax+00h]
0x14008af90  mov     ecx, [rbp+120h+arg_20]
0x14008af96  mov     r9, r12
0x14008af99  mov     r13, [rsp+220h+var_1C8]
0x14008af9e  mov     [rsp+220h+var_1F0], ecx; int
0x14008afa2  mov     r8, r13
0x14008afa5  mov     [rsp+220h+var_1F8], rsi; __int64
0x14008afaa  mov     rcx, rax; Object
0x14008afad  mov     rsi, [rsp+220h+var_1D8]
0x14008afb2  mov     rdx, rsi
0x14008afb5  mov     [rsp+220h+var_200], ebx; int
0x14008afb9  call    DwmAsyncCreateSprite
0x14008afbe  test    eax, eax
0x14008afc0  js      loc_14008B176
0x14008afc6  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008afcd  nop     dword ptr [rax+rax+00h]
0x14008afd2  mov     rbx, [rbp+120h+var_198]
0x14008afd6  test    rbx, rbx
0x14008afd9  jz      short loc_14008AFEF
0x14008afdb  mov     rax, [rax+0E0h]
0x14008afe2  cmp     [rax+90h], r15
0x14008afe9  jnz     loc_14008B0A1
0x14008afef  call    cs:__imp_PsGetCurrentProcessId
0x14008aff6  nop     dword ptr [rax+rax+00h]
0x14008affb  and     eax, 0FFFFFFFCh
0x14008affe  mov     [rdi+70h], eax
0x14008b001  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x14008b008  nop     dword ptr [rax+rax+00h]
0x14008b00d  test    eax, eax
0x14008b00f  mov     r15, rsi
0x14008b012  setnz   al
0x14008b015  mov     [rdi+7Eh], al
0x14008b018  mov     rax, [rbp+120h+var_1A0]
0x14008b01c  test    rax, rax
0x14008b01f  jz      short loc_14008B026
0x14008b021  lock dec word ptr [rax+0Ch]
0x14008b026  lea     rcx, [rsp+220h+var_1C0]
0x14008b02b  mov     [rbp+120h+var_1A0], 0
0x14008b033  call    cs:__imp_PopThreadGuardedObject
0x14008b03a  nop     dword ptr [rax+rax+00h]
0x14008b03f  lea     rcx, [rbp+120h+var_168]; this
0x14008b043  call    ??1ENTER_DWM_CRIT_COMMON@@QEAA@XZ; ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON(void)
0x14008b048  cmp     [rsp+220h+var_1E0], 0
0x14008b04d  jnz     short loc_14008B076
0x14008b04f  mov     rax, r15
0x14008b052  mov     rcx, [rbp+120h+var_50]
0x14008b059  xor     rcx, rsp; StackCookie
0x14008b05c  call    __security_check_cookie
0x14008b061  add     rsp, 1E8h
0x14008b068  pop     r15
0x14008b06a  pop     r14
0x14008b06c  pop     r13
0x14008b06e  pop     r12
0x14008b070  pop     rdi
0x14008b071  pop     rsi
0x14008b072  pop     rbx
0x14008b073  pop     rbp
0x14008b074  retn
0x14008b076  mov     r8, r12; struct tagRECT *
0x14008b079  mov     rdx, r13; HWND
0x14008b07c  mov     rcx, r14; HDEV
0x14008b07f  call    ?GdiCreateSprite@@YAPEAXPEAUHDEV__@@PEAUHWND__@@PEAUtagRECT@@@Z; GdiCreateSprite(HDEV__ *,HWND__ *,tagRECT *)
0x14008b084  mov     r15, rax
0x14008b087  jmp     short loc_14008B04F
0x14008b089  call    cs:__imp_W32GetUserSessionState
0x14008b090  nop     dword ptr [rax+rax+00h]
0x14008b095  mov     rbx, [rax+4948h]
0x14008b09c  jmp     loc_14008ADBE
0x14008b0a1  xorps   xmm0, xmm0
0x14008b0a4  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14008b0ab  lea     rdx, [rbp+120h+var_190]
0x14008b0af  lea     rcx, [rbp+120h+var_190]
0x14008b0b3  movups  [rbp+120h+var_190], xmm0
0x14008b0b7  movups  [rbp+120h+var_180], xmm0
0x14008b0bb  call    cs:__imp_PushThreadGuardedObject
0x14008b0c2  nop     dword ptr [rax+rax+00h]
0x14008b0c7  mov     [rbp+120h+var_170], r15
0x14008b0cb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008b0d2  nop     dword ptr [rax+rax+00h]
0x14008b0d7  xor     r9d, r9d
0x14008b0da  mov     r8b, 0Fh
0x14008b0dd  mov     rcx, rax
0x14008b0e0  mov     rdx, rbx
0x14008b0e3  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008b0ea  nop     dword ptr [rax+rax+00h]
0x14008b0ef  mov     [rbp+120h+var_170], rax
0x14008b0f3  call    cs:__imp_UserReferenceDwmApiPort
0x14008b0fa  nop     dword ptr [rax+rax+00h]
0x14008b0ff  mov     r8, rbx
0x14008b102  mov     rdx, rsi
0x14008b105  mov     rcx, rax; Object
0x14008b108  call    DwmAsyncZorderSprite
0x14008b10d  mov     rax, [rbp+120h+var_170]
0x14008b111  test    rax, rax
0x14008b114  jz      short loc_14008B11B
0x14008b116  lock dec word ptr [rax+0Ch]
0x14008b11b  lea     rcx, [rbp+120h+var_190]
0x14008b11f  mov     [rbp+120h+var_170], r15
0x14008b123  call    cs:__imp_PopThreadGuardedObject
0x14008b12a  nop     dword ptr [rax+rax+00h]
0x14008b12f  jmp     loc_14008AFEF
0x14008b134  test    rsi, rsi
0x14008b137  jnz     loc_14008AF2C
0x14008b13d  test    rbx, rbx
0x14008b140  jz      short loc_14008B14E
0x14008b142  movups  xmm0, xmmword ptr [rbx]
0x14008b145  movaps  [rbp+120h+var_140], xmm0
0x14008b149  movdqu  [rbp+120h+var_130], xmm0
0x14008b14e  mov     [rbp+120h+var_120], rax
0x14008b152  mov     [rbp+120h+var_118], rax
0x14008b156  call    cs:__imp_W32GetUserSessionState
0x14008b15d  nop     dword ptr [rax+rax+00h]
0x14008b162  lea     rsi, [rbp+120h+var_140]
0x14008b166  mov     rcx, [rax+4948h]
0x14008b16d  mov     [rbp+120h+var_110], rcx
0x14008b171  jmp     loc_14008AF2C
0x14008b176  mov     r8, [rbp+120h+var_1A0]; struct DWMSPRITE *
0x14008b17a  test    r8, r8
0x14008b17d  jz      short loc_14008B185
0x14008b17f  lock dec word ptr [r8+0Ch]
0x14008b185  xor     edx, edx; bool
0x14008b187  mov     [rbp+120h+var_1A0], r15
0x14008b18b  mov     rcx, r14; HDEV
0x14008b18e  call    ?vspDestroyDwmSpriteObjInternal@@YAXPEAUHDEV__@@_NPEAVDWMSPRITE@@@Z; vspDestroyDwmSpriteObjInternal(HDEV__ *,bool,DWMSPRITE *)
0x14008b193  jmp     loc_14008B018
```
