# DwmMovePointer(_SURFOBJ *,long,long,_RECTL *,ulong)

- ea: `0x140092444`
- end: `0x140092c2d`
- name: `?DwmMovePointer@@YAXPEAU_SURFOBJ@@JJPEAU_RECTL@@K@Z`
- size: `2025`
- prototype: `void __fastcall(struct _SURFOBJ *, int, int, struct _RECTL *, char)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008a1c0`
- `0x140091a4c`
- `0x140092e24`
- `0x140094a30`

## callees

- `0x14007f010`
- `0x140086434`
- `0x1400875b8`
- `0x14008a670`
- `0x14008eb28`
- `0x140090004`
- `0x140091e34`
- `0x140092444`
- `0x14017e6e8`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092475`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400925ba`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009269d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400927d6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009284c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400928de`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092a57`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092bd4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092475`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400925ba`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009269d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400927d6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14009284c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400928de`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092a57`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140092bd4`
- `win32kbase!HmgShareLock` at `0x140092bf5`
- `win32kbase!HmgShareLock` at `0x140092bf5`
- `win32kbase!PopThreadGuardedObject` at `0x1400926fa`
- `win32kbase!PopThreadGuardedObject` at `0x140092976`
- `win32kbase!PopThreadGuardedObject` at `0x1400929ac`
- `win32kbase!PopThreadGuardedObject` at `0x1400929d2`
- `win32kbase!PopThreadGuardedObject` at `0x140092ac7`
- `win32kbase!PopThreadGuardedObject` at `0x1400926fa`
- `win32kbase!PopThreadGuardedObject` at `0x140092976`
- `win32kbase!PopThreadGuardedObject` at `0x1400929ac`
- `win32kbase!PopThreadGuardedObject` at `0x1400929d2`
- `win32kbase!PopThreadGuardedObject` at `0x140092ac7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400925cc`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400925cc`
- `win32kbase!PushThreadGuardedObject` at `0x14009268d`
- `win32kbase!PushThreadGuardedObject` at `0x1400927c2`
- `win32kbase!PushThreadGuardedObject` at `0x140092838`
- `win32kbase!PushThreadGuardedObject` at `0x1400928ca`
- `win32kbase!PushThreadGuardedObject` at `0x140092a43`
- `win32kbase!PushThreadGuardedObject` at `0x14009268d`
- `win32kbase!PushThreadGuardedObject` at `0x1400927c2`
- `win32kbase!PushThreadGuardedObject` at `0x140092838`
- `win32kbase!PushThreadGuardedObject` at `0x1400928ca`
- `win32kbase!PushThreadGuardedObject` at `0x140092a43`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400925ae`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400925ae`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14009258f`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14009258f`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400924b4`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400924b4`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1400925dd`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400926b5`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400927f3`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14009286d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400928ff`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140092a78`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400926b5`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400927f3`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14009286d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400928ff`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140092a78`
- `win32kbase!DrvPixelSpaceToUniformSpacePoint` at `0x140092b39`
- `win32kbase!DrvPixelSpaceToUniformSpacePoint` at `0x140092b39`

## pseudocode

```c
void __fastcall DwmMovePointer(struct _SURFOBJ *a1, int a2, int a3, struct _RECTL *a4, char a5)
{
  int v5; // edi
  struct Gre::Base::SESSION_GLOBALS *v8; // rbx
  __int64 v9; // rax
  HDEV hdev; // r13
  HSEMAPHORE v11; // r14
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 **v14; // rdx
  __int64 v15; // rax
  __int64 **v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // rsi
  Gre::Base *v19; // rcx
  struct Gre::Base::SESSION_GLOBALS *v20; // rax
  __int64 **v21; // rdx
  __int64 v22; // rax
  __int64 **v23; // rdx
  __int64 v24; // rbx
  HSPRITE v25; // rbx
  Gre::Base *v26; // rcx
  struct Gre::Base::SESSION_GLOBALS *v27; // rax
  __int64 v28; // r8
  struct DWMSPRITE *v29; // rax
  HDEV v30; // rdi
  __int64 v31; // rdi
  Gre::Base *v32; // rcx
  struct Gre::Base::SESSION_GLOBALS *v33; // rax
  __int64 v34; // r8
  HSPRITE NeighborSprite; // rdi
  Gre::Base *v36; // rcx
  struct Gre::Base::SESSION_GLOBALS *v37; // rax
  __int64 v38; // r8
  __int64 v39; // rcx
  HSPRITE v40; // rdi
  Gre::Base *v41; // rcx
  struct Gre::Base::SESSION_GLOBALS *v42; // rax
  __int64 v43; // r8
  struct DWMSPRITE *v44; // rax
  HSPRITE v45; // rdi
  Gre::Base *v46; // rcx
  struct Gre::Base::SESSION_GLOBALS *v47; // rax
  __int64 v48; // r8
  struct DWMSPRITE *v49; // rcx
  __int64 v50; // rdx
  void *v51; // rsi
  HDEV v52; // rbx
  Gre::Base *v53; // rcx
  struct Gre::Base::SESSION_GLOBALS *v54; // rax
  __int64 v55; // r8
  __int64 v56; // rbx
  __int128 v57; // [rsp+88h] [rbp-80h] BYREF
  __int128 v58; // [rsp+98h] [rbp-70h]
  struct DWMSPRITE *v59; // [rsp+A8h] [rbp-60h]
  __int128 v60; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v61; // [rsp+C0h] [rbp-48h]
  __int64 v62; // [rsp+D0h] [rbp-38h]
  _OWORD v63[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v64; // [rsp+F8h] [rbp-10h]
  _BYTE v65[112]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v66[160]; // [rsp+178h] [rbp+70h] BYREF
  struct tagPOINT v67; // [rsp+228h] [rbp+120h] BYREF
  int v68; // [rsp+238h] [rbp+130h]
  struct _RECTL *v69; // [rsp+240h] [rbp+138h] BYREF

  v69 = a4;
  v68 = a3;
  v5 = a3;
  v8 = Gre::Base::Globals((Gre::Base *)a1);
  v9 = *((_QWORD *)v8 + 28);
  if ( !*(_DWORD *)(v9 + 100) || !*(_QWORD *)(v9 + 136) )
    return;
  hdev = a1->hdev;
  v11 = (HSEMAPHORE)(*(_QWORD *)v8 + 520LL);
  GreAcquireSemaphoreInternal(v11);
  GrepAcquireLockValidate<7>();
  if ( *(_QWORD *)(*((_QWORD *)v8 + 28) + 144LL) != *(_QWORD *)(*((_QWORD *)v8 + 28) + 136LL) )
  {
    v17 = *((_QWORD *)v8 + 28);
    v18 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
    if ( (unsigned int)(v18 - *(_DWORD *)(v17 + 164)) >= *(_DWORD *)(v17 + 168) )
    {
      v31 = *(_QWORD *)(v17 + 136);
      v60 = 0;
      v61 = 0;
      PushThreadGuardedObject(
        &v60,
        &v60,
        UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
      v62 = 0;
      v33 = Gre::Base::Globals(v32);
      if ( v31 )
      {
        LOBYTE(v34) = 15;
        v62 = HmgLock(v33, v31, v34);
      }
      NeighborSprite = hspGetNeighborSprite(*(HSPRITE *)(*((_QWORD *)v8 + 28) + 136LL), 0, 0);
      memset(v63, 0, sizeof(v63));
      PushThreadGuardedObject(
        v63,
        v63,
        UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
      v64 = 0;
      v37 = Gre::Base::Globals(v36);
      if ( NeighborSprite )
      {
        LOBYTE(v38) = 15;
        v39 = HmgLock(v37, NeighborSprite, v38);
        v64 = v39;
      }
      else
      {
        v39 = v64;
      }
      if ( v62 )
      {
        if ( !v39 )
        {
LABEL_50:
          v64 = 0;
          PopThreadGuardedObject(v63);
          if ( v62 )
            _InterlockedAdd16((volatile signed __int16 *)(v62 + 12), 0xFFFFu);
          v62 = 0;
          PopThreadGuardedObject(&v60);
          v5 = v68;
          goto LABEL_4;
        }
        if ( *(_DWORD *)(v39 + 56) == *(_DWORD *)(v62 + 56) && *(_DWORD *)(v39 + 60) == *(_DWORD *)(v62 + 60) )
        {
          v45 = *(HSPRITE *)(*((_QWORD *)v8 + 28) + 144LL);
          while ( v45 != *(HSPRITE *)(*((_QWORD *)v8 + 28) + 136LL) )
          {
            v57 = 0;
            v58 = 0;
            PushThreadGuardedObject(
              &v57,
              &v57,
              UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
            v59 = 0;
            v47 = Gre::Base::Globals(v46);
            if ( v45 )
            {
              LOBYTE(v48) = 15;
              v49 = (struct DWMSPRITE *)HmgLock(v47, v45, v48);
              v59 = v49;
            }
            else
            {
              v49 = v59;
            }
            if ( v49 && (*((_DWORD *)v49 + 34) & 1) != 0 )
            {
              vSpDwmUpdateSpriteVisibility(v49, 0);
              goto LABEL_44;
            }
            v45 = hspGetNeighborSprite(v45, 1, 0);
            if ( v59 )
              _InterlockedAdd16((volatile signed __int16 *)v59 + 6, 0xFFFFu);
            v59 = 0;
            PopThreadGuardedObject(&v57);
          }
        }
        else
        {
          v40 = *(HSPRITE *)(*((_QWORD *)v8 + 28) + 144LL);
          v57 = 0;
          v58 = 0;
          PushThreadGuardedObject(
            &v57,
            &v57,
            UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
          v59 = 0;
          v42 = Gre::Base::Globals(v41);
          if ( v40 )
          {
            LOBYTE(v43) = 15;
            v44 = (struct DWMSPRITE *)HmgLock(v42, v40, v43);
            v59 = v44;
          }
          else
          {
            v44 = v59;
          }
          if ( v44 )
            vSpDwmUpdateSpriteVisibility(v44, 0);
          *(_QWORD *)(*((_QWORD *)v8 + 28) + 144LL) = hspGetNeighborSprite(v40, 1, 0);
          vSpDwmZorderSprite(v40, *(HSPRITE *)(*((_QWORD *)v8 + 28) + 136LL));
          *(_QWORD *)(*((_QWORD *)v8 + 28) + 136LL) = v40;
LABEL_44:
          if ( v59 )
            _InterlockedAdd16((volatile signed __int16 *)v59 + 6, 0xFFFFu);
          v59 = 0;
          PopThreadGuardedObject(&v57);
        }
        *(_DWORD *)(*((_QWORD *)v8 + 28) + 164LL) = v18;
        v39 = v64;
      }
      if ( v39 )
        _InterlockedAdd16((volatile signed __int16 *)(v39 + 12), 0xFFFFu);
      goto LABEL_50;
    }
  }
LABEL_4:
  v12 = (__int64 *)(hdev + 880);
  v13 = *((_QWORD *)hdev + 440);
  if ( a2 == -1 )
  {
    if ( *(__int64 **)(v13 + 8) != v12
      || (v21 = (__int64 **)*((_QWORD *)hdev + 441), *v21 != v12)
      || (*v21 = (__int64 *)v13,
          *(_QWORD *)(v13 + 8) = v21,
          v22 = *((_QWORD *)v8 + 28) + 104LL,
          v23 = *(__int64 ***)(*((_QWORD *)v8 + 28) + 112LL),
          *v23 != (__int64 *)v22) )
    {
LABEL_8:
      __fastfail(3u);
    }
    *v12 = v22;
    *((_QWORD *)hdev + 441) = v23;
    *v23 = v12;
    *(_QWORD *)(v22 + 8) = v12;
    v24 = *((_QWORD *)v8 + 28);
    if ( *(_QWORD *)(v24 + 120) == v24 + 120 )
    {
      v25 = *(HSPRITE *)(v24 + 144);
      while ( v25 )
      {
        v60 = 0;
        v61 = 0;
        PushThreadGuardedObject(
          &v60,
          &v60,
          UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
        v62 = 0;
        v27 = Gre::Base::Globals(v26);
        LOBYTE(v28) = 15;
        v29 = (struct DWMSPRITE *)HmgLock(v27, v25, v28);
        v62 = (__int64)v29;
        if ( v29 )
          vSpDwmUpdateSpriteVisibility(v29, 0);
        v25 = hspGetNeighborSprite(v25, 1, 0);
        if ( v62 )
          _InterlockedAdd16((volatile signed __int16 *)(v62 + 12), 0xFFFFu);
        v62 = 0;
        PopThreadGuardedObject(&v60);
      }
    }
  }
  else
  {
    v67 = 0;
    if ( *(__int64 **)(v13 + 8) != v12 )
      goto LABEL_8;
    v14 = (__int64 **)*((_QWORD *)hdev + 441);
    if ( *v14 != v12 )
      goto LABEL_8;
    *v14 = (__int64 *)v13;
    *(_QWORD *)(v13 + 8) = v14;
    v15 = *((_QWORD *)v8 + 28) + 120LL;
    v16 = *(__int64 ***)(*((_QWORD *)v8 + 28) + 128LL);
    if ( *v16 != (__int64 *)v15 )
      goto LABEL_8;
    *((_QWORD *)hdev + 441) = v16;
    *v12 = v15;
    *v16 = v12;
    *(_QWORD *)(v15 + 8) = v12;
    v50 = *((_QWORD *)v8 + 28);
    v67.x = a2 + *((_DWORD *)hdev + 644) - *(_DWORD *)(v50 + 152);
    v67.y = v5 + *((_DWORD *)hdev + 645) - *(_DWORD *)(v50 + 156);
    v51 = *(void **)(v50 + 136);
    DrvPixelSpaceToUniformSpacePoint(&v67, &v67.y);
    v52 = a1->hdev;
    OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v66, 0);
    OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v65, 0);
    GrepUpdateSprite(
      v52,
      0,
      v51,
      (struct OPTAPIDCOBJ *)v66,
      &v67,
      0,
      (struct OPTAPIDCOBJ *)v65,
      0,
      0,
      0,
      0x40200000u,
      0,
      0,
      1,
      0,
      0);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v65);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v66);
    v54 = Gre::Base::Globals(v53);
    if ( v51 )
    {
      LOBYTE(v55) = 15;
      v56 = HmgShareLock(v54, v51, v55, 0);
      if ( v56 )
      {
        if ( (a5 & 4) != 0 )
        {
          v30 = a1->hdev;
          LODWORD(v69) = 0x1000000;
          OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v65, 0);
          OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v66, 0);
          GrepUpdateSprite(
            v30,
            0,
            v51,
            (struct OPTAPIDCOBJ *)v65,
            0,
            0,
            (struct OPTAPIDCOBJ *)v66,
            0,
            0,
            (struct _BLENDFUNCTION *)&v69,
            0x21200002u,
            0,
            0,
            1,
            0,
            0);
          OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v66);
          OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v65);
        }
        if ( v56 != -88 )
          GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v56 + 88));
        vSpDwmUpdateSpriteVisibility((struct DWMSPRITE *)v56, 1);
        if ( v56 != -88 )
          GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v56 + 88));
        v20 = Gre::Base::Globals(v19);
        DEC_SHARE_REF_CNT(v20, v56);
      }
    }
  }
  if ( v11 )
    GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal, v11);
}

```

## disassembly

```asm
0x140092444  mov     rax, rsp
0x140092447  mov     [rax+10h], rbx
0x14009244b  mov     [rax+20h], r9
0x14009244f  mov     [rax+18h], r8d
0x140092453  push    rbp
0x140092454  push    rsi
0x140092455  push    rdi
0x140092456  push    r12
0x140092458  push    r13
0x14009245a  push    r14
0x14009245c  push    r15
0x14009245e  lea     rbp, [rax-118h]
0x140092465  sub     rsp, 1E0h
0x14009246c  mov     edi, r8d
0x14009246f  mov     r12d, edx
0x140092472  mov     r15, rcx
0x140092475  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14009247c  nop     dword ptr [rax+rax+00h]
0x140092481  mov     rbx, rax
0x140092484  mov     rax, [rax+0E0h]
0x14009248b  cmp     dword ptr [rax+64h], 0
0x14009248f  jz      loc_1400925EC
0x140092495  cmp     qword ptr [rax+88h], 0
0x14009249d  jz      loc_1400925EC
0x1400924a3  mov     r14, [rbx]
0x1400924a6  mov     r13, [r15+18h]
0x1400924aa  add     r14, 208h
0x1400924b1  mov     rcx, r14
0x1400924b4  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400924bb  nop     dword ptr [rax+rax+00h]
0x1400924c0  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x1400924c5  mov     rcx, [rbx+0E0h]
0x1400924cc  or      esi, 0FFFFFFFFh
0x1400924cf  mov     rax, [rcx+88h]
0x1400924d6  cmp     [rcx+90h], rax
0x1400924dd  jnz     short loc_140092532
0x1400924df  lea     rcx, [r13+0DC0h]
0x1400924e6  mov     rax, [rcx]
0x1400924e9  cmp     r12d, esi
0x1400924ec  jz      loc_140092608
0x1400924f2  mov     qword ptr [rbp+110h+arg_0.x], 0
0x1400924fd  cmp     [rax+8], rcx
0x140092501  jnz     short loc_14009252B
0x140092503  mov     rdx, [rcx+8]
0x140092507  cmp     [rdx], rcx
0x14009250a  jnz     short loc_14009252B
0x14009250c  mov     [rdx], rax
0x14009250f  mov     [rax+8], rdx
0x140092513  mov     rax, [rbx+0E0h]
0x14009251a  add     rax, 78h ; 'x'
0x14009251e  mov     rdx, [rax+8]
0x140092522  cmp     [rdx], rax
0x140092525  jz      loc_140092AE4
0x14009252b  mov     ecx, 3
0x140092530  int     29h; Win8: RtlFailFast(ecx)
0x140092532  mov     rcx, 0FFFFF78000000004h
0x14009253c  mov     rax, 0FFFFF78000000320h
0x140092546  mov     rax, [rax]
0x140092549  mov     esi, [rcx]
0x14009254b  mov     rcx, [rbx+0E0h]
0x140092552  imul    rsi, rax
0x140092556  shr     rsi, 18h
0x14009255a  mov     eax, esi
0x14009255c  sub     eax, [rcx+0A4h]
0x140092562  cmp     eax, [rcx+0A8h]
0x140092568  jnb     loc_1400927A1
0x14009256e  or      esi, 0FFFFFFFFh
0x140092571  jmp     loc_1400924DF
0x140092576  test    [rbp+110h+arg_20], 4
0x14009257d  jnz     loc_14009270B
0x140092583  lea     rdi, [rbx+58h]
0x140092587  test    rdi, rdi
0x14009258a  jz      short loc_14009259B
0x14009258c  mov     rcx, rdi
0x14009258f  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140092596  nop     dword ptr [rax+rax+00h]
0x14009259b  mov     dl, r13b; bool
0x14009259e  mov     rcx, rbx; struct DWMSPRITE *
0x1400925a1  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x1400925a6  test    rdi, rdi
0x1400925a9  jz      short loc_1400925BA
0x1400925ab  mov     rcx, rdi
0x1400925ae  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1400925b5  nop     dword ptr [rax+rax+00h]
0x1400925ba  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400925c1  nop     dword ptr [rax+rax+00h]
0x1400925c6  mov     rcx, rax
0x1400925c9  mov     rdx, rbx
0x1400925cc  call    cs:__imp_DEC_SHARE_REF_CNT
0x1400925d3  nop     dword ptr [rax+rax+00h]
0x1400925d8  test    r14, r14
0x1400925db  jz      short loc_1400925EC
0x1400925dd  mov     rcx, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x1400925e4  mov     rdx, r14
0x1400925e7  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1400925ec  mov     rbx, [rsp+210h+arg_8]
0x1400925f4  add     rsp, 1E0h
0x1400925fb  pop     r15
0x1400925fd  pop     r14
0x1400925ff  pop     r13
0x140092601  pop     r12
0x140092603  pop     rdi
0x140092604  pop     rsi
0x140092605  pop     rbp
0x140092606  retn
0x140092608  cmp     [rax+8], rcx
0x14009260c  jnz     loc_14009252B
0x140092612  mov     rdx, [rcx+8]
0x140092616  cmp     [rdx], rcx
0x140092619  jnz     loc_14009252B
0x14009261f  mov     [rdx], rax
0x140092622  mov     [rax+8], rdx
0x140092626  mov     rax, [rbx+0E0h]
0x14009262d  add     rax, 68h ; 'h'
0x140092631  mov     rdx, [rax+8]
0x140092635  cmp     [rdx], rax
0x140092638  jnz     loc_14009252B
0x14009263e  mov     [rcx], rax
0x140092641  mov     [rcx+8], rdx
0x140092645  mov     [rdx], rcx
0x140092648  mov     [rax+8], rcx
0x14009264c  mov     rbx, [rbx+0E0h]
0x140092653  lea     rax, [rbx+78h]
0x140092657  cmp     [rax], rax
0x14009265a  jnz     loc_1400925D8
0x140092660  mov     rbx, [rbx+90h]
0x140092667  xor     r12d, r12d
0x14009266a  test    rbx, rbx
0x14009266d  jz      loc_1400925D8
0x140092673  xorps   xmm0, xmm0
0x140092676  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14009267d  lea     rdx, [rbp+110h+var_168]
0x140092681  lea     rcx, [rbp+110h+var_168]
0x140092685  movups  [rbp+110h+var_168], xmm0
0x140092689  movups  [rbp+110h+var_158], xmm0
0x14009268d  call    cs:__imp_PushThreadGuardedObject
0x140092694  nop     dword ptr [rax+rax+00h]
0x140092699  mov     [rbp+110h+var_148], r12
0x14009269d  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400926a4  nop     dword ptr [rax+rax+00h]
0x1400926a9  xor     r9d, r9d
0x1400926ac  mov     r8b, 0Fh
0x1400926af  mov     rcx, rax
0x1400926b2  mov     rdx, rbx
0x1400926b5  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400926bc  nop     dword ptr [rax+rax+00h]
0x1400926c1  mov     [rbp+110h+var_148], rax
0x1400926c5  test    rax, rax
0x1400926c8  jz      short loc_1400926D4
0x1400926ca  xor     edx, edx; bool
0x1400926cc  mov     rcx, rax; struct DWMSPRITE *
0x1400926cf  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x1400926d4  xor     r8d, r8d; bool
0x1400926d7  mov     dl, 1; bool
0x1400926d9  mov     rcx, rbx; HSPRITE
0x1400926dc  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x1400926e1  mov     rbx, rax
0x1400926e4  mov     rax, [rbp+110h+var_148]
0x1400926e8  test    rax, rax
0x1400926eb  jz      short loc_1400926F2
0x1400926ed  lock add [rax+0Ch], si
0x1400926f2  lea     rcx, [rbp+110h+var_168]
0x1400926f6  mov     [rbp+110h+var_148], r12
0x1400926fa  call    cs:__imp_PopThreadGuardedObject
0x140092701  nop     dword ptr [rax+rax+00h]
0x140092706  jmp     loc_14009266A
0x14009270b  mov     rdi, [r15+18h]
0x14009270f  lea     rcx, [rbp+110h+var_110]; this
0x140092713  xor     edx, edx; HDC
0x140092715  mov     dword ptr [rbp+110h+arg_18], 1000000h
0x14009271f  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x140092724  xor     edx, edx; HDC
0x140092726  lea     rcx, [rbp+110h+var_A0]; this
0x14009272a  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x14009272f  mov     [rsp+78h], r12d; unsigned int
0x140092734  lea     rax, [rbp+110h+arg_18]
0x14009273b  mov     [rsp+210h+var_1A0], r12d; int
0x140092740  lea     r9, [rbp+110h+var_110]; struct OPTAPIDCOBJ *
0x140092744  mov     [rsp+210h+var_1A8], r13d; int
0x140092749  mov     r8, rsi; void *
0x14009274c  mov     [rsp+210h+var_1B0], r12; struct tagMINIWINDOWINFO *
0x140092751  xor     edx, edx; HWND
0x140092753  mov     [rsp+210h+var_1B8], r12; struct tagRECT *
0x140092758  mov     rcx, rdi; HDEV
0x14009275b  mov     [rsp+210h+var_1C0], 21200002h; unsigned int
0x140092763  mov     [rsp+210h+var_1C8], rax; struct _BLENDFUNCTION *
0x140092768  lea     rax, [rbp+110h+var_A0]
0x14009276c  mov     [rsp+210h+var_1D0], r12d; unsigned int
0x140092771  mov     [rsp+210h+var_1D8], r12; struct tagPOINT *
0x140092776  mov     [rsp+210h+var_1E0], rax; struct OPTAPIDCOBJ *
0x14009277b  mov     [rsp+210h+var_1E8], r12; struct tagSIZE *
0x140092780  mov     [rsp+210h+var_1F0], r12; struct tagPOINT *
0x140092785  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x14009278a  lea     rcx, [rbp+110h+var_A0]; this
0x14009278e  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140092793  lea     rcx, [rbp+110h+var_110]; this
0x140092797  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14009279c  jmp     loc_140092583
0x1400927a1  mov     rdi, [rcx+88h]
0x1400927a8  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400927af  xorps   xmm0, xmm0
0x1400927b2  lea     rcx, [rbp+110h+var_168]
0x1400927b6  lea     rdx, [rbp+110h+var_168]
0x1400927ba  movups  [rbp+110h+var_168], xmm0
0x1400927be  movups  [rbp+110h+var_158], xmm0
0x1400927c2  call    cs:__imp_PushThreadGuardedObject
0x1400927c9  nop     dword ptr [rax+rax+00h]
0x1400927ce  mov     [rbp+110h+var_148], 0
0x1400927d6  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400927dd  nop     dword ptr [rax+rax+00h]
0x1400927e2  test    rdi, rdi
0x1400927e5  jz      short loc_140092803
0x1400927e7  xor     r9d, r9d
0x1400927ea  mov     r8b, 0Fh
0x1400927ed  mov     rdx, rdi
0x1400927f0  mov     rcx, rax
0x1400927f3  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400927fa  nop     dword ptr [rax+rax+00h]
0x1400927ff  mov     [rbp+110h+var_148], rax
0x140092803  mov     rcx, [rbx+0E0h]
0x14009280a  xor     r8d, r8d; bool
0x14009280d  xor     edx, edx; bool
0x14009280f  mov     rcx, [rcx+88h]; HSPRITE
0x140092816  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14009281b  xorps   xmm0, xmm0
0x14009281e  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x140092825  lea     rdx, [rbp+110h+var_140]
0x140092829  mov     rdi, rax
0x14009282c  lea     rcx, [rbp+110h+var_140]
0x140092830  movups  [rbp+110h+var_140], xmm0
0x140092834  movups  [rbp+110h+var_130], xmm0
0x140092838  call    cs:__imp_PushThreadGuardedObject
0x14009283f  nop     dword ptr [rax+rax+00h]
0x140092844  mov     [rbp+110h+var_120], 0
0x14009284c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140092853  nop     dword ptr [rax+rax+00h]
0x140092858  test    rdi, rdi
0x14009285b  jz      loc_140092C12
0x140092861  xor     r9d, r9d
0x140092864  mov     r8b, 0Fh
0x140092867  mov     rdx, rdi
0x14009286a  mov     rcx, rax
0x14009286d  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140092874  nop     dword ptr [rax+rax+00h]
0x140092879  mov     rcx, rax
0x14009287c  mov     [rbp+110h+var_120], rax
0x140092880  mov     rdx, [rbp+110h+var_148]
0x140092884  test    rdx, rdx
0x140092887  jz      loc_140092993
0x14009288d  test    rcx, rcx
0x140092890  jz      loc_1400929E9
0x140092896  mov     eax, [rdx+38h]
0x140092899  cmp     [rcx+38h], eax
0x14009289c  jz      loc_1400929FB
0x1400928a2  mov     rax, [rbx+0E0h]
0x1400928a9  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400928b0  xorps   xmm0, xmm0
0x1400928b3  lea     rdx, [rbp+110h+var_190]
0x1400928b7  lea     rcx, [rbp+110h+var_190]
0x1400928bb  mov     rdi, [rax+90h]
0x1400928c2  movups  [rbp+110h+var_190], xmm0
0x1400928c6  movups  [rbp+110h+var_180], xmm0
0x1400928ca  call    cs:__imp_PushThreadGuardedObject
0x1400928d1  nop     dword ptr [rax+rax+00h]
0x1400928d6  mov     [rbp+110h+var_170], 0
0x1400928de  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400928e5  nop     dword ptr [rax+rax+00h]
0x1400928ea  test    rdi, rdi
0x1400928ed  jz      loc_140092C24
0x1400928f3  xor     r9d, r9d
0x1400928f6  mov     r8b, 0Fh
0x1400928f9  mov     rdx, rdi
0x1400928fc  mov     rcx, rax
0x1400928ff  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140092906  nop     dword ptr [rax+rax+00h]
0x14009290b  mov     [rbp+110h+var_170], rax
0x14009290f  test    rax, rax
0x140092912  jz      short loc_14009291E
0x140092914  xor     edx, edx; bool
0x140092916  mov     rcx, rax; struct DWMSPRITE *
0x140092919  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x14009291e  xor     r8d, r8d; bool
0x140092921  mov     dl, 1; bool
0x140092923  mov     rcx, rdi; HSPRITE
0x140092926  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x14009292b  mov     rcx, [rbx+0E0h]
0x140092932  mov     [rcx+90h], rax
0x140092939  mov     rcx, rdi; HSPRITE
0x14009293c  mov     rdx, [rbx+0E0h]
0x140092943  mov     rdx, [rdx+88h]; HSPRITE
0x14009294a  call    ?vSpDwmZorderSprite@@YAXPEAUHSPRITE__@@0@Z; vSpDwmZorderSprite(HSPRITE__ *,HSPRITE__ *)
0x14009294f  mov     rax, [rbx+0E0h]
0x140092956  mov     [rax+88h], rdi
0x14009295d  mov     rax, [rbp+110h+var_170]
0x140092961  test    rax, rax
0x140092964  jnz     loc_1400929EE
0x14009296a  lea     rcx, [rbp+110h+var_190]
0x14009296e  mov     [rbp+110h+var_170], 0
0x140092976  call    cs:__imp_PopThreadGuardedObject
0x14009297d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
