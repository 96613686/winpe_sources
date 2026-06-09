# DwmMovePointer(_SURFOBJ *,long,long,_RECTL *,ulong)

- ea: `0x1400a7ee8`
- end: `0x1400a86d1`
- name: `?DwmMovePointer@@YAXPEAU_SURFOBJ@@JJPEAU_RECTL@@K@Z`
- size: `2025`
- prototype: `void __fastcall(struct _SURFOBJ *, int, int, struct _RECTL *, char)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a88c8`
- `0x1400ab040`
- `0x14011da34`
- `0x1401e0bb4`

## callees

- `0x140014614`
- `0x140016de4`
- `0x140016e74`
- `0x14005b938`
- `0x1400a7100`
- `0x1400a7ee8`
- `0x14011c5ac`
- `0x14011dee4`
- `0x14011ee44`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a7f19`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a805e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8141`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a827a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a82f0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8382`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a84fb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8678`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a7f19`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a805e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8141`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a827a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a82f0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8382`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a84fb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400a8678`
- `win32kbase!HmgShareLock` at `0x1400a8699`
- `win32kbase!HmgShareLock` at `0x1400a8699`
- `win32kbase!PopThreadGuardedObject` at `0x1400a819e`
- `win32kbase!PopThreadGuardedObject` at `0x1400a841a`
- `win32kbase!PopThreadGuardedObject` at `0x1400a8450`
- `win32kbase!PopThreadGuardedObject` at `0x1400a8476`
- `win32kbase!PopThreadGuardedObject` at `0x1400a856b`
- `win32kbase!PopThreadGuardedObject` at `0x1400a819e`
- `win32kbase!PopThreadGuardedObject` at `0x1400a841a`
- `win32kbase!PopThreadGuardedObject` at `0x1400a8450`
- `win32kbase!PopThreadGuardedObject` at `0x1400a8476`
- `win32kbase!PopThreadGuardedObject` at `0x1400a856b`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400a8070`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1400a8070`
- `win32kbase!PushThreadGuardedObject` at `0x1400a8131`
- `win32kbase!PushThreadGuardedObject` at `0x1400a8266`
- `win32kbase!PushThreadGuardedObject` at `0x1400a82dc`
- `win32kbase!PushThreadGuardedObject` at `0x1400a836e`
- `win32kbase!PushThreadGuardedObject` at `0x1400a84e7`
- `win32kbase!PushThreadGuardedObject` at `0x1400a8131`
- `win32kbase!PushThreadGuardedObject` at `0x1400a8266`
- `win32kbase!PushThreadGuardedObject` at `0x1400a82dc`
- `win32kbase!PushThreadGuardedObject` at `0x1400a836e`
- `win32kbase!PushThreadGuardedObject` at `0x1400a84e7`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400a8052`
- `win32kbase!GreReleasePushLockExclusive` at `0x1400a8052`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400a8033`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1400a8033`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400a7f58`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400a7f58`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1400a8081`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8159`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8297`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8311`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a83a3`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a851c`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8159`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8297`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a8311`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a83a3`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400a851c`
- `win32kbase!DrvPixelSpaceToUniformSpacePoint` at `0x1400a85dd`
- `win32kbase!DrvPixelSpaceToUniformSpacePoint` at `0x1400a85dd`

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
        v62 = HmgLock(v33, v31, v34, 0);
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
        v39 = HmgLock(v37, NeighborSprite, v38, 0);
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
              v49 = (struct DWMSPRITE *)HmgLock(v47, v45, v48, 0);
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
            v44 = (struct DWMSPRITE *)HmgLock(v42, v40, v43, 0);
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
        v29 = (struct DWMSPRITE *)HmgLock(v27, v25, v28, 0);
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
    GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreExclusiveInternal);
}

```

## disassembly

```asm
0x1400a7ee8  mov     rax, rsp
0x1400a7eeb  mov     [rax+10h], rbx
0x1400a7eef  mov     [rax+20h], r9
0x1400a7ef3  mov     [rax+18h], r8d
0x1400a7ef7  push    rbp
0x1400a7ef8  push    rsi
0x1400a7ef9  push    rdi
0x1400a7efa  push    r12
0x1400a7efc  push    r13
0x1400a7efe  push    r14
0x1400a7f00  push    r15
0x1400a7f02  lea     rbp, [rax-118h]
0x1400a7f09  sub     rsp, 1E0h
0x1400a7f10  mov     edi, r8d
0x1400a7f13  mov     r12d, edx
0x1400a7f16  mov     r15, rcx
0x1400a7f19  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a7f20  nop     dword ptr [rax+rax+00h]
0x1400a7f25  mov     rbx, rax
0x1400a7f28  mov     rax, [rax+0E0h]
0x1400a7f2f  cmp     dword ptr [rax+64h], 0
0x1400a7f33  jz      loc_1400A8090
0x1400a7f39  cmp     qword ptr [rax+88h], 0
0x1400a7f41  jz      loc_1400A8090
0x1400a7f47  mov     r14, [rbx]
0x1400a7f4a  mov     r13, [r15+18h]
0x1400a7f4e  add     r14, 208h
0x1400a7f55  mov     rcx, r14
0x1400a7f58  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400a7f5f  nop     dword ptr [rax+rax+00h]
0x1400a7f64  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x1400a7f69  mov     rcx, [rbx+0E0h]
0x1400a7f70  or      esi, 0FFFFFFFFh
0x1400a7f73  mov     rax, [rcx+88h]
0x1400a7f7a  cmp     [rcx+90h], rax
0x1400a7f81  jnz     short loc_1400A7FD6
0x1400a7f83  lea     rcx, [r13+0DC0h]
0x1400a7f8a  mov     rax, [rcx]
0x1400a7f8d  cmp     r12d, esi
0x1400a7f90  jz      loc_1400A80AC
0x1400a7f96  mov     qword ptr [rbp+110h+arg_0.x], 0
0x1400a7fa1  cmp     [rax+8], rcx
0x1400a7fa5  jnz     short loc_1400A7FCF
0x1400a7fa7  mov     rdx, [rcx+8]
0x1400a7fab  cmp     [rdx], rcx
0x1400a7fae  jnz     short loc_1400A7FCF
0x1400a7fb0  mov     [rdx], rax
0x1400a7fb3  mov     [rax+8], rdx
0x1400a7fb7  mov     rax, [rbx+0E0h]
0x1400a7fbe  add     rax, 78h ; 'x'
0x1400a7fc2  mov     rdx, [rax+8]
0x1400a7fc6  cmp     [rdx], rax
0x1400a7fc9  jz      loc_1400A8588
0x1400a7fcf  mov     ecx, 3
0x1400a7fd4  int     29h; Win8: RtlFailFast(ecx)
0x1400a7fd6  mov     rcx, 0FFFFF78000000004h
0x1400a7fe0  mov     rax, 0FFFFF78000000320h
0x1400a7fea  mov     rax, [rax]
0x1400a7fed  mov     esi, [rcx]
0x1400a7fef  mov     rcx, [rbx+0E0h]
0x1400a7ff6  imul    rsi, rax
0x1400a7ffa  shr     rsi, 18h
0x1400a7ffe  mov     eax, esi
0x1400a8000  sub     eax, [rcx+0A4h]
0x1400a8006  cmp     eax, [rcx+0A8h]
0x1400a800c  jnb     loc_1400A8245
0x1400a8012  or      esi, 0FFFFFFFFh
0x1400a8015  jmp     loc_1400A7F83
0x1400a801a  test    [rbp+110h+arg_20], 4
0x1400a8021  jnz     loc_1400A81AF
0x1400a8027  lea     rdi, [rbx+58h]
0x1400a802b  test    rdi, rdi
0x1400a802e  jz      short loc_1400A803F
0x1400a8030  mov     rcx, rdi
0x1400a8033  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1400a803a  nop     dword ptr [rax+rax+00h]
0x1400a803f  mov     dl, r13b; bool
0x1400a8042  mov     rcx, rbx; struct DWMSPRITE *
0x1400a8045  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x1400a804a  test    rdi, rdi
0x1400a804d  jz      short loc_1400A805E
0x1400a804f  mov     rcx, rdi
0x1400a8052  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1400a8059  nop     dword ptr [rax+rax+00h]
0x1400a805e  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a8065  nop     dword ptr [rax+rax+00h]
0x1400a806a  mov     rcx, rax
0x1400a806d  mov     rdx, rbx
0x1400a8070  call    cs:__imp_DEC_SHARE_REF_CNT
0x1400a8077  nop     dword ptr [rax+rax+00h]
0x1400a807c  test    r14, r14
0x1400a807f  jz      short loc_1400A8090
0x1400a8081  mov     rcx, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x1400a8088  mov     rdx, r14
0x1400a808b  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1400a8090  mov     rbx, [rsp+210h+arg_8]
0x1400a8098  add     rsp, 1E0h
0x1400a809f  pop     r15
0x1400a80a1  pop     r14
0x1400a80a3  pop     r13
0x1400a80a5  pop     r12
0x1400a80a7  pop     rdi
0x1400a80a8  pop     rsi
0x1400a80a9  pop     rbp
0x1400a80aa  retn
0x1400a80ac  cmp     [rax+8], rcx
0x1400a80b0  jnz     loc_1400A7FCF
0x1400a80b6  mov     rdx, [rcx+8]
0x1400a80ba  cmp     [rdx], rcx
0x1400a80bd  jnz     loc_1400A7FCF
0x1400a80c3  mov     [rdx], rax
0x1400a80c6  mov     [rax+8], rdx
0x1400a80ca  mov     rax, [rbx+0E0h]
0x1400a80d1  add     rax, 68h ; 'h'
0x1400a80d5  mov     rdx, [rax+8]
0x1400a80d9  cmp     [rdx], rax
0x1400a80dc  jnz     loc_1400A7FCF
0x1400a80e2  mov     [rcx], rax
0x1400a80e5  mov     [rcx+8], rdx
0x1400a80e9  mov     [rdx], rcx
0x1400a80ec  mov     [rax+8], rcx
0x1400a80f0  mov     rbx, [rbx+0E0h]
0x1400a80f7  lea     rax, [rbx+78h]
0x1400a80fb  cmp     [rax], rax
0x1400a80fe  jnz     loc_1400A807C
0x1400a8104  mov     rbx, [rbx+90h]
0x1400a810b  xor     r12d, r12d
0x1400a810e  test    rbx, rbx
0x1400a8111  jz      loc_1400A807C
0x1400a8117  xorps   xmm0, xmm0
0x1400a811a  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a8121  lea     rdx, [rbp+110h+var_168]
0x1400a8125  lea     rcx, [rbp+110h+var_168]
0x1400a8129  movups  [rbp+110h+var_168], xmm0
0x1400a812d  movups  [rbp+110h+var_158], xmm0
0x1400a8131  call    cs:__imp_PushThreadGuardedObject
0x1400a8138  nop     dword ptr [rax+rax+00h]
0x1400a813d  mov     [rbp+110h+var_148], r12
0x1400a8141  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a8148  nop     dword ptr [rax+rax+00h]
0x1400a814d  xor     r9d, r9d
0x1400a8150  mov     r8b, 0Fh
0x1400a8153  mov     rcx, rax
0x1400a8156  mov     rdx, rbx
0x1400a8159  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400a8160  nop     dword ptr [rax+rax+00h]
0x1400a8165  mov     [rbp+110h+var_148], rax
0x1400a8169  test    rax, rax
0x1400a816c  jz      short loc_1400A8178
0x1400a816e  xor     edx, edx; bool
0x1400a8170  mov     rcx, rax; struct DWMSPRITE *
0x1400a8173  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x1400a8178  xor     r8d, r8d; bool
0x1400a817b  mov     dl, 1; bool
0x1400a817d  mov     rcx, rbx; HSPRITE
0x1400a8180  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x1400a8185  mov     rbx, rax
0x1400a8188  mov     rax, [rbp+110h+var_148]
0x1400a818c  test    rax, rax
0x1400a818f  jz      short loc_1400A8196
0x1400a8191  lock add [rax+0Ch], si
0x1400a8196  lea     rcx, [rbp+110h+var_168]
0x1400a819a  mov     [rbp+110h+var_148], r12
0x1400a819e  call    cs:__imp_PopThreadGuardedObject
0x1400a81a5  nop     dword ptr [rax+rax+00h]
0x1400a81aa  jmp     loc_1400A810E
0x1400a81af  mov     rdi, [r15+18h]
0x1400a81b3  lea     rcx, [rbp+110h+var_110]; this
0x1400a81b7  xor     edx, edx; HDC
0x1400a81b9  mov     dword ptr [rbp+110h+arg_18], 1000000h
0x1400a81c3  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x1400a81c8  xor     edx, edx; HDC
0x1400a81ca  lea     rcx, [rbp+110h+var_A0]; this
0x1400a81ce  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x1400a81d3  mov     [rsp+78h], r12d; unsigned int
0x1400a81d8  lea     rax, [rbp+110h+arg_18]
0x1400a81df  mov     [rsp+210h+var_1A0], r12d; int
0x1400a81e4  lea     r9, [rbp+110h+var_110]; struct OPTAPIDCOBJ *
0x1400a81e8  mov     [rsp+210h+var_1A8], r13d; int
0x1400a81ed  mov     r8, rsi; void *
0x1400a81f0  mov     [rsp+210h+var_1B0], r12; struct tagMINIWINDOWINFO *
0x1400a81f5  xor     edx, edx; HWND
0x1400a81f7  mov     [rsp+210h+var_1B8], r12; struct tagRECT *
0x1400a81fc  mov     rcx, rdi; HDEV
0x1400a81ff  mov     [rsp+210h+var_1C0], 21200002h; unsigned int
0x1400a8207  mov     [rsp+210h+var_1C8], rax; struct _BLENDFUNCTION *
0x1400a820c  lea     rax, [rbp+110h+var_A0]
0x1400a8210  mov     [rsp+210h+var_1D0], r12d; unsigned int
0x1400a8215  mov     [rsp+210h+var_1D8], r12; struct tagPOINT *
0x1400a821a  mov     [rsp+210h+var_1E0], rax; struct OPTAPIDCOBJ *
0x1400a821f  mov     [rsp+210h+var_1E8], r12; struct tagSIZE *
0x1400a8224  mov     [rsp+210h+var_1F0], r12; struct tagPOINT *
0x1400a8229  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x1400a822e  lea     rcx, [rbp+110h+var_A0]; this
0x1400a8232  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x1400a8237  lea     rcx, [rbp+110h+var_110]; this
0x1400a823b  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x1400a8240  jmp     loc_1400A8027
0x1400a8245  mov     rdi, [rcx+88h]
0x1400a824c  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a8253  xorps   xmm0, xmm0
0x1400a8256  lea     rcx, [rbp+110h+var_168]
0x1400a825a  lea     rdx, [rbp+110h+var_168]
0x1400a825e  movups  [rbp+110h+var_168], xmm0
0x1400a8262  movups  [rbp+110h+var_158], xmm0
0x1400a8266  call    cs:__imp_PushThreadGuardedObject
0x1400a826d  nop     dword ptr [rax+rax+00h]
0x1400a8272  mov     [rbp+110h+var_148], 0
0x1400a827a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a8281  nop     dword ptr [rax+rax+00h]
0x1400a8286  test    rdi, rdi
0x1400a8289  jz      short loc_1400A82A7
0x1400a828b  xor     r9d, r9d
0x1400a828e  mov     r8b, 0Fh
0x1400a8291  mov     rdx, rdi
0x1400a8294  mov     rcx, rax
0x1400a8297  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400a829e  nop     dword ptr [rax+rax+00h]
0x1400a82a3  mov     [rbp+110h+var_148], rax
0x1400a82a7  mov     rcx, [rbx+0E0h]
0x1400a82ae  xor     r8d, r8d; bool
0x1400a82b1  xor     edx, edx; bool
0x1400a82b3  mov     rcx, [rcx+88h]; HSPRITE
0x1400a82ba  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x1400a82bf  xorps   xmm0, xmm0
0x1400a82c2  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a82c9  lea     rdx, [rbp+110h+var_140]
0x1400a82cd  mov     rdi, rax
0x1400a82d0  lea     rcx, [rbp+110h+var_140]
0x1400a82d4  movups  [rbp+110h+var_140], xmm0
0x1400a82d8  movups  [rbp+110h+var_130], xmm0
0x1400a82dc  call    cs:__imp_PushThreadGuardedObject
0x1400a82e3  nop     dword ptr [rax+rax+00h]
0x1400a82e8  mov     [rbp+110h+var_120], 0
0x1400a82f0  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a82f7  nop     dword ptr [rax+rax+00h]
0x1400a82fc  test    rdi, rdi
0x1400a82ff  jz      loc_1400A86B6
0x1400a8305  xor     r9d, r9d
0x1400a8308  mov     r8b, 0Fh
0x1400a830b  mov     rdx, rdi
0x1400a830e  mov     rcx, rax
0x1400a8311  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400a8318  nop     dword ptr [rax+rax+00h]
0x1400a831d  mov     rcx, rax
0x1400a8320  mov     [rbp+110h+var_120], rax
0x1400a8324  mov     rdx, [rbp+110h+var_148]
0x1400a8328  test    rdx, rdx
0x1400a832b  jz      loc_1400A8437
0x1400a8331  test    rcx, rcx
0x1400a8334  jz      loc_1400A848D
0x1400a833a  mov     eax, [rdx+38h]
0x1400a833d  cmp     [rcx+38h], eax
0x1400a8340  jz      loc_1400A849F
0x1400a8346  mov     rax, [rbx+0E0h]
0x1400a834d  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1400a8354  xorps   xmm0, xmm0
0x1400a8357  lea     rdx, [rbp+110h+var_190]
0x1400a835b  lea     rcx, [rbp+110h+var_190]
0x1400a835f  mov     rdi, [rax+90h]
0x1400a8366  movups  [rbp+110h+var_190], xmm0
0x1400a836a  movups  [rbp+110h+var_180], xmm0
0x1400a836e  call    cs:__imp_PushThreadGuardedObject
0x1400a8375  nop     dword ptr [rax+rax+00h]
0x1400a837a  mov     [rbp+110h+var_170], 0
0x1400a8382  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400a8389  nop     dword ptr [rax+rax+00h]
0x1400a838e  test    rdi, rdi
0x1400a8391  jz      loc_1400A86C8
0x1400a8397  xor     r9d, r9d
0x1400a839a  mov     r8b, 0Fh
0x1400a839d  mov     rdx, rdi
0x1400a83a0  mov     rcx, rax
0x1400a83a3  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400a83aa  nop     dword ptr [rax+rax+00h]
0x1400a83af  mov     [rbp+110h+var_170], rax
0x1400a83b3  test    rax, rax
0x1400a83b6  jz      short loc_1400A83C2
0x1400a83b8  xor     edx, edx; bool
0x1400a83ba  mov     rcx, rax; struct DWMSPRITE *
0x1400a83bd  call    ?vSpDwmUpdateSpriteVisibility@@YAXPEAVDWMSPRITE@@_N@Z; vSpDwmUpdateSpriteVisibility(DWMSPRITE *,bool)
0x1400a83c2  xor     r8d, r8d; bool
0x1400a83c5  mov     dl, 1; bool
0x1400a83c7  mov     rcx, rdi; HSPRITE
0x1400a83ca  call    ?hspGetNeighborSprite@@YAPEAUHSPRITE__@@PEAU1@_N1@Z; hspGetNeighborSprite(HSPRITE__ *,bool,bool)
0x1400a83cf  mov     rcx, [rbx+0E0h]
0x1400a83d6  mov     [rcx+90h], rax
0x1400a83dd  mov     rcx, rdi; HSPRITE
0x1400a83e0  mov     rdx, [rbx+0E0h]
0x1400a83e7  mov     rdx, [rdx+88h]; HSPRITE
0x1400a83ee  call    ?vSpDwmZorderSprite@@YAXPEAUHSPRITE__@@0@Z; vSpDwmZorderSprite(HSPRITE__ *,HSPRITE__ *)
0x1400a83f3  mov     rax, [rbx+0E0h]
0x1400a83fa  mov     [rax+88h], rdi
0x1400a8401  mov     rax, [rbp+110h+var_170]
0x1400a8405  test    rax, rax
0x1400a8408  jnz     loc_1400A8492
0x1400a840e  lea     rcx, [rbp+110h+var_190]
0x1400a8412  mov     [rbp+110h+var_170], 0
0x1400a841a  call    cs:__imp_PopThreadGuardedObject
0x1400a8421  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
