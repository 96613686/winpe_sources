# DEVLOCKBLTOBJ::bLock(XDCOBJ &,XDCOBJ &)

- ea: `0x140068f04`
- end: `0x14006987f`
- name: `?bLock@DEVLOCKBLTOBJ@@QEAAHAEAVXDCOBJ@@0@Z`
- size: `2427`
- prototype: `__int64 __fastcall(DEVLOCKBLTOBJ *__hidden this, struct XDCOBJ *, struct XDCOBJ *)`
- caller_count: `6`
- callee_count: `29`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140064ba0`
- `0x1400663c0`
- `0x14007be5c`
- `0x1401343b0`
- `0x140137c54`
- `0x14030f788`

## callees

- `0x14005e2e0`
- `0x140062148`
- `0x140068f04`
- `0x14006b960`
- `0x14006ca24`
- `0x14006cd1c`
- `0x1400704e0`
- `0x14008209c`
- `0x140082294`
- `0x140082fd0`
- `0x14008d7ec`
- `0x14008d8bc`
- `0x14008d990`
- `0x14008e84c`
- `0x1400943d4`
- `0x14009608c`
- `0x140096604`
- `0x140135050`
- `0x14015e77c`
- `0x140167e30`
- `0x14016ca44`
- `0x14016ca80`
- `0x140175230`
- `0x14017f918`
- `0x1401a51cc`
- `0x1401a9fc8`
- `0x1401b6a2c`
- `0x1401d373c`
- `0x140302998`

## import_xrefs

- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140069499`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140069532`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140069499`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140069532`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1400694f1`
- `win32kbase!GreGetLockCount` at `0x14006901c`
- `win32kbase!GreGetLockCount` at `0x14006916c`
- `win32kbase!GreGetLockCount` at `0x1400692d1`
- `win32kbase!GreGetLockCount` at `0x140069440`
- `win32kbase!GreGetLockCount` at `0x14006901c`
- `win32kbase!GreGetLockCount` at `0x14006916c`
- `win32kbase!GreGetLockCount` at `0x1400692d1`
- `win32kbase!GreGetLockCount` at `0x140069440`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400690b5`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400690da`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400690b5`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400690da`
- `win32kbase!GreIncLockCount` at `0x140069199`
- `win32kbase!GreIncLockCount` at `0x1400692fe`
- `win32kbase!GreIncLockCount` at `0x140069459`
- `win32kbase!GreIncLockCount` at `0x140069199`
- `win32kbase!GreIncLockCount` at `0x1400692fe`
- `win32kbase!GreIncLockCount` at `0x140069459`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400693ac`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400693f6`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400693ac`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400693f6`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x14006948b`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140069524`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x14006948b`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140069524`
- `win32kbase!IsDEVLOCKMappingEnabled` at `0x140069770`
- `win32kbase!IsDEVLOCKMappingEnabled` at `0x140069770`
- `win32kbase!?MapUserVAToKernel@SURFACE@@QEAAJW4_LOCK_OPERATION@@_N@Z` at `0x1400697cc`
- `win32kbase!?MapUserVAToKernel@SURFACE@@QEAAJW4_LOCK_OPERATION@@_N@Z` at `0x140069854`
- `win32kbase!?MapUserVAToKernel@SURFACE@@QEAAJW4_LOCK_OPERATION@@_N@Z` at `0x1400697cc`
- `win32kbase!?MapUserVAToKernel@SURFACE@@QEAAJW4_LOCK_OPERATION@@_N@Z` at `0x140069854`

## pseudocode

```c
__int64 __fastcall DEVLOCKBLTOBJ::bLock(DEVLOCKBLTOBJ *this, struct XDCOBJ *a2, struct XDCOBJ *a3)
{
  HSURF *v3; // rdi
  HSURF *v5; // r15
  int v8; // r15d
  int v9; // ebp
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // edx
  int v15; // r10d
  int v16; // eax
  __int64 v17; // rdx
  struct _GRETHREAD *CurrentThread; // rax
  struct SURFACE *v19; // rax
  unsigned int v20; // r8d
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // r9
  int v24; // edx
  struct _GRETHREAD *v25; // rax
  bool v26; // zf
  DC *v28; // rcx
  DC *v29; // rcx
  int v30; // r8d
  __int64 v31; // r9
  struct _GRETHREAD *v32; // rax
  struct _GRETHREAD *v33; // r15
  __int64 v34; // rdx
  DC *v35; // rcx
  struct _GRETHREAD *v36; // rax
  unsigned __int64 v37; // rcx
  __int64 v38; // rdx
  unsigned __int64 v39; // rax
  BOOL v40; // ebp
  int v41; // eax
  int v42; // r9d
  HDC v43; // rdx
  __int64 v44; // rcx
  SURFACE *v45; // rcx
  XDCOBJ *v46; // rcx
  SURFACE *v47; // rax
  signed __int32 v48[26]; // [rsp+0h] [rbp-68h] BYREF
  __int64 v49; // [rsp+70h] [rbp+8h] BYREF

  v3 = (HSURF *)((char *)this + 328);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v5 = (HSURF *)((char *)this + 336);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 20) = 1;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 40) = **(_QWORD **)a2;
  *((_QWORD *)this + 43) = **(_QWORD **)a3;
  if ( !TrapAppContainerRenderingWorker(a2, (HSURF *)this + 39, (HSURF *)this + 38, (unsigned int *)this + 21)
    || !TrapAppContainerRenderingWorker(a3, v5, v3, 0) )
  {
    goto LABEL_65;
  }
  DEVLOCKBLTOBJ::bPrepareTrgDco(this, 0, 0);
  *((_QWORD *)this + 24) = 0;
  v8 = 1;
  v9 = 0;
  v10 = *((_QWORD *)a2 + 2);
  if ( *(_QWORD *)a3 && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x200) != 0
    || *(_QWORD *)a2 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 )
  {
    v11 = *((_QWORD *)a2 + 2);
    *((_QWORD *)this + 2) = *(_QWORD *)v10 + 624LL;
    GreAcquireSemaphoreShared<1,>(v11);
    *((_DWORD *)this + 20) |= 8u;
    if ( !(unsigned int)GreGetLockCount()
      && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v10) )
    {
      GreAcquireSemaphoreShared<2,>(v10);
      v9 = 1;
    }
    v12 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 )
    {
      v13 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        v14 = *(_DWORD *)(v13 + 36);
        v15 = *(_DWORD *)(v12 + 36);
        if ( ((v15 ^ v14) & 0x200) != 0 )
        {
          if ( ((**(_DWORD **)(v12 + 976) & 1) == 0 || (v14 & 0x8000) == 0)
            && ((**(_DWORD **)(v13 + 976) & 1) == 0 || (v15 & 0x8000) == 0) )
          {
            v8 = 0;
          }
        }
        else
        {
          v8 = (v15 & v14 & 0x8200) == 33280;
        }
      }
      v49 = *(_QWORD *)(v12 + 48);
      v8 &= PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v49);
    }
    if ( *(_QWORD *)a2 )
    {
      v49 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
      v8 &= PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v49);
    }
  }
  v16 = *(_DWORD *)(*(_QWORD *)a3 + 36LL);
  if ( (v16 & 0x200) != 0 )
  {
    if ( (v16 & 0x8000) == 0 || !v8 )
    {
      v17 = *(_QWORD *)(*(_QWORD *)a3 + 64LL);
      *((_QWORD *)this + 1) = v17;
      *((_QWORD *)this + 4) = *(_QWORD *)(*(_QWORD *)a3 + 48LL);
      if ( v9 && v17 == *(_QWORD *)v10 + 1144LL )
      {
        GreReleaseSemaphoreShared<2,>(v10);
        v9 = 0;
      }
      if ( *((_QWORD *)this + 1) == *(_QWORD *)v10 + 1144LL )
      {
        *((_DWORD *)this + 20) |= 0x200000u;
        GreAcquireSemaphore<2,>(v10);
      }
      else
      {
        GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 4));
      }
    }
    if ( (!*(_QWORD *)a2 || (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) == 0) && !(unsigned int)GreGetLockCount() )
    {
      *((_DWORD *)this + 20) |= 0x1000u;
      CurrentThread = GreGetCurrentThread();
      if ( CurrentThread )
      {
        *((_QWORD *)CurrentThread + 38) = 0;
        *((_QWORD *)CurrentThread + 37) = 0;
      }
      GreIncLockCount();
      GreAcquireSemaphoreShared<3,>(v10);
    }
    if ( (unsigned int)DC::bInFullScreen(*(DC **)a3) )
    {
      if ( (*((_DWORD *)this + 20) & 0x1000) != 0 )
        GreReleaseSemaphoreShared<3,>(v10);
      *((_DWORD *)this + 20) &= ~1u;
      if ( v9 )
        GreReleaseSemaphoreShared<2,>(v10);
      return 0;
    }
  }
  v19 = XDCOBJ::pSurfaceEff(a3);
  *((_DWORD *)this + 20) ^= (*((_DWORD *)this + 20) ^ ((unsigned int)SrcSurfaceAccessCheck(v19) << 22)) & 0x400000;
  v20 = *((_DWORD *)this + 20) & 0xFF7FFFFF | ~(*((_DWORD *)XDCOBJ::pSurfaceEff(a3) + 40) >> 5) & 0x800000;
  *((_DWORD *)this + 20) = v20;
  v21 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    v22 = *(_DWORD *)(v21 + 36);
    if ( (v22 & 0x200) == 0 )
      goto LABEL_69;
    if ( (v22 & 0x8000) == 0 || !v8 )
    {
      v23 = *(_QWORD *)(v21 + 64);
      *(_QWORD *)this = v23;
      *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
      if ( v9 && v23 == *(_QWORD *)v10 + 1144LL )
      {
        GreReleaseSemaphoreShared<2,>(v10);
        v20 = *((_DWORD *)this + 20);
        v9 = 0;
      }
      if ( *(_QWORD *)this == *(_QWORD *)v10 + 1144LL )
      {
        *((_DWORD *)this + 20) = v20 | 0x100000;
        GreAcquireSemaphore<2,>(v10);
      }
      else
      {
        GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 3));
      }
      v24 = *((_DWORD *)this + 20);
      if ( (v24 & 0x200) == 0 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) != 0 )
        *((_DWORD *)this + 20) = v24 | 0x200;
    }
    if ( !(unsigned int)GreGetLockCount() )
    {
      *((_DWORD *)this + 20) |= 0x1000u;
      v25 = GreGetCurrentThread();
      if ( v25 )
      {
        *((_QWORD *)v25 + 38) = 0;
        *((_QWORD *)v25 + 37) = 0;
      }
      GreIncLockCount();
      GreAcquireSemaphoreShared<3,>(v10);
    }
    if ( (unsigned int)DC::bInFullScreen(*(DC **)a2) )
    {
      v26 = (*((_DWORD *)this + 20) & 0x1000) == 0;
LABEL_61:
      if ( !v26 )
        GreReleaseSemaphoreShared<3,>(v10);
      if ( v9 )
        GreReleaseSemaphoreShared<2,>(v10);
      goto LABEL_65;
    }
    if ( v21 )
    {
LABEL_69:
      if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && (*(_DWORD *)(v21 + 36) & 0x80000) != 0 )
      {
LABEL_70:
        v26 = *((_QWORD *)this + 2) == 0;
        goto LABEL_61;
      }
    }
  }
  else
  {
    v21 = 0;
  }
  if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x80000) != 0
    || v21
    && ((*((_DWORD *)this + 20) & 0x1000) != 0 || (*(_DWORD *)(v21 + 36) & 0x200) == 0)
    && (*(_DWORD *)(v21 + 36) & 0x10) != 0
    && !DC::bCompute((DC *)v21) )
  {
    goto LABEL_70;
  }
  if ( !DC::prgnRao(*(DC **)a2) && !DC::prgnVisSnap(v28) )
    goto LABEL_65;
  if ( ((*((_DWORD *)this + 20) & 0x1000) != 0 || (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x200) == 0)
    && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x10) != 0
    && !DC::bCompute(*(DC **)a3) )
  {
    goto LABEL_70;
  }
  if ( !DC::prgnRao(*(DC **)a3) && !DC::prgnVisSnap(v29) )
    goto LABEL_65;
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 || (*(_DWORD *)(v31 + 36) & 0x200) != 0 )
  {
    if ( (*((_DWORD *)this + 20) & 0x1000) == 0 )
      goto LABEL_109;
    if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 )
    {
      if ( *((_QWORD *)this + 38) )
        UserIsCurrentProcessImmersiveAppContainer();
      else
        DC::vSetRendering(*(DC **)a2);
      v32 = GreGetCurrentThread();
      v33 = v32;
      if ( v32 )
      {
        *((_QWORD *)v32 + 37) = *(_QWORD *)a2;
        if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) == 0 )
        {
          *((_DWORD *)v32 + 84) |= 1u;
          *(_QWORD *)(*(_QWORD *)a2 + 1976LL) = 0;
          SEMOBJSHARED<14>::SEMOBJSHARED<14>(&v49, v10);
          v34 = v49;
          *((_DWORD *)v33 + 87) = *(_DWORD *)(v10 + 4392);
          GreReleaseSemaphoreCommon<14,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v34);
        }
      }
    }
    v35 = *(DC **)a3;
    if ( **(_QWORD **)a3 != **(_QWORD **)a2 && (*((_DWORD *)v35 + 9) & 0x200) != 0 )
    {
      if ( *((_QWORD *)this + 41) )
        UserIsCurrentProcessImmersiveAppContainer();
      else
        DC::vSetRendering(v35);
      v36 = GreGetCurrentThread();
      if ( v36 )
        *((_QWORD *)v36 + 38) = *(_QWORD *)a3;
    }
  }
  else if ( !(unsigned int)GreGetLockCount() )
  {
    *((_DWORD *)this + 20) |= 0x80000u;
    GreIncLockCount();
  }
  if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && *((_QWORD *)this + 2) )
    GreReleaseSemaphoreShared<3,>(v10);
LABEL_109:
  if ( v9 )
    GreReleaseSemaphoreShared<2,>(v10);
  if ( (*((_DWORD *)this + 20) & 0x1000) == 0 )
    goto LABEL_146;
  if ( *(_QWORD *)a3 )
    v37 = *(_QWORD *)(*(_QWORD *)a3 + 496LL);
  else
    v37 = 0;
  v38 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
    v39 = *(_QWORD *)(v38 + 496);
  else
    v39 = 0;
  if ( v37 && v39 && v37 != v39 )
  {
    if ( v37 < v39 )
    {
      *((_DWORD *)this + 20) |= 0x8000u;
      v40 = DEVLOCKBLTOBJ::bPrepareSrcDco(this, a3, v30, 1) == 0;
      _InterlockedOr(v48, 0);
      v41 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1);
      goto LABEL_130;
    }
    v40 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1) == 0;
    _InterlockedOr(v48, 0);
    v42 = 1;
LABEL_129:
    v41 = DEVLOCKBLTOBJ::bPrepareSrcDco(this, a3, v30, v42);
LABEL_130:
    if ( !v41 )
      goto LABEL_65;
    goto LABEL_131;
  }
  v40 = 0;
  if ( v38 )
    v40 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1) == 0;
  if ( !*(_QWORD *)a2 || **(_QWORD **)a2 != **(_QWORD **)a3 )
  {
    v42 = 0;
    goto LABEL_129;
  }
LABEL_131:
  if ( v40
    || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 48LL) + 40LL) & 0x8000) != 0
    && *(_QWORD *)(*(_QWORD *)a2 + 496LL)
    && *(_QWORD *)this )
  {
    goto LABEL_65;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 48LL) + 40LL) & 0x8000) != 0
    && *(_QWORD *)(*(_QWORD *)a3 + 496LL)
    && *((_QWORD *)this + 1) )
  {
    *((_QWORD *)this + 9) = a3;
    *((_QWORD *)this + 8) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 496LL) + 32LL);
    if ( !bCopySurface(
            (DEVLOCKBLTOBJ *)((char *)this + 40),
            (struct _SURFOBJ *)(*(_QWORD *)(*(_QWORD *)a3 + 496LL) + 24LL))
      || !XDCOBJ::SetSurfaceEff(a3, *((struct SURFACE **)this + 5)) )
    {
      goto LABEL_65;
    }
    DEVLOCKBLTOBJ::bUnMapSrcSurfaceView(this);
    DEVLOCKBLTOBJ::bDisposeSrcDco(this);
    if ( (*((_DWORD *)this + 20) & 0x200000) != 0 )
    {
      GreReleaseSemaphoreExclusive<2>();
      *((_DWORD *)this + 20) &= ~0x200000u;
    }
    else if ( *((_QWORD *)this + 1) )
    {
      GreReleaseSemaphoreExclusive<8,PDEVOBJ>(*((_QWORD *)this + 4));
    }
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 4) = 0;
    if ( *((_QWORD *)this + 2) )
    {
      GreReleaseSemaphoreShared<1,>(v10);
      *((_QWORD *)this + 2) = 0;
    }
  }
LABEL_146:
  if ( (*((_DWORD *)this + 20) & 0x81000) != 0 )
  {
    DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKBLTOBJ *)((char *)this + 88), **(HDC **)a2);
    v43 = **(HDC **)a3;
    if ( v43 != **(HDC **)a2 )
      DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKBLTOBJ *)((char *)this + 192), v43);
  }
  if ( !(unsigned int)IsDEVLOCKMappingEnabled() )
    return 1;
  if ( DLODCOBJ::bValid((DEVLOCKBLTOBJ *)((char *)this + 88)) )
  {
    v45 = *(SURFACE **)(*(_QWORD *)v44 + 496LL);
  }
  else if ( *(_QWORD *)a2 )
  {
    v45 = *(SURFACE **)(*(_QWORD *)a2 + 496LL);
  }
  else
  {
    v45 = 0;
  }
  v26 = *((_DWORD *)this + 90) == 2;
  *((_QWORD *)this + 46) = v45;
  if ( v26 && v45 )
  {
    if ( (int)SURFACE::MapUserVAToKernel(v45, IoWriteAccess, 0) >= 0 )
    {
      *((_DWORD *)this + 90) = 0;
      goto LABEL_159;
    }
    *((_DWORD *)this + 90) = 1;
LABEL_65:
    *((_DWORD *)this + 20) &= ~1u;
    return 0;
  }
LABEL_159:
  if ( DLODCOBJ::bValid((DEVLOCKBLTOBJ *)((char *)this + 192)) && *(_QWORD *)(*((_QWORD *)this + 24) + 496LL) )
  {
    v46 = (DEVLOCKBLTOBJ *)((char *)this + 192);
  }
  else
  {
    if ( !*(_QWORD *)a3 || !*(_QWORD *)(*(_QWORD *)a3 + 496LL) )
    {
      v47 = 0;
      goto LABEL_168;
    }
    v46 = a3;
  }
  v47 = XDCOBJ::pSurfaceEff(v46);
LABEL_168:
  v26 = *((_DWORD *)this + 94) == 2;
  *((_QWORD *)this + 48) = v47;
  if ( !v26 || !v47 )
    return 1;
  if ( (int)SURFACE::MapUserVAToKernel(v47, IoWriteAccess, 0) < 0 )
  {
    *((_DWORD *)this + 94) = 1;
    goto LABEL_65;
  }
  *((_DWORD *)this + 94) = 0;
  return 1;
}

```

## disassembly

```asm
0x140068f04  push    rbx
0x140068f06  push    rbp
0x140068f07  push    rsi
0x140068f08  push    rdi
0x140068f09  push    r12
0x140068f0b  push    r13
0x140068f0d  push    r14
0x140068f0f  push    r15
0x140068f11  sub     rsp, 28h
0x140068f15  xor     r12d, r12d
0x140068f18  lea     rdi, [rcx+148h]
0x140068f1f  mov     rbx, rcx
0x140068f22  mov     [rcx], r12
0x140068f25  mov     [rcx+8], r12
0x140068f29  lea     r15, [rcx+150h]
0x140068f30  mov     [rcx+10h], r12
0x140068f34  mov     r14, rdx
0x140068f37  mov     [rcx+18h], r12
0x140068f3b  lea     rdx, [rcx+138h]; HSURF *
0x140068f42  mov     [rcx+20h], r12
0x140068f46  lea     r13d, [r12+1]
0x140068f4b  mov     [rcx+50h], r13d
0x140068f4f  lea     r9, [rbx+54h]; unsigned int *
0x140068f53  mov     [rcx+40h], r12
0x140068f57  mov     rsi, r8
0x140068f5a  mov     [rcx+48h], r12
0x140068f5e  lea     r8, [rcx+130h]; HSURF *
0x140068f65  mov     [rcx+128h], r12
0x140068f6c  mov     [r8], r12
0x140068f6f  mov     [rdx], r12
0x140068f72  mov     [rdi], r12
0x140068f75  mov     [r15], r12
0x140068f78  mov     rax, [r14]
0x140068f7b  mov     rcx, [rax]
0x140068f7e  mov     [rbx+140h], rcx
0x140068f85  mov     rax, [rsi]
0x140068f88  mov     rcx, [rax]
0x140068f8b  mov     [rbx+158h], rcx
0x140068f92  mov     rcx, r14; struct XDCOBJ *
0x140068f95  call    ?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z; TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)
0x140068f9a  test    al, al
0x140068f9c  jz      loc_14006933E
0x140068fa2  xor     r9d, r9d; unsigned int *
0x140068fa5  mov     r8, rdi; HSURF *
0x140068fa8  mov     rdx, r15; HSURF *
0x140068fab  mov     rcx, rsi; struct XDCOBJ *
0x140068fae  call    ?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z; TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)
0x140068fb3  test    al, al
0x140068fb5  jz      loc_14006933E
0x140068fbb  xor     r8d, r8d; int
0x140068fbe  xor     edx, edx; struct XDCOBJ *
0x140068fc0  mov     rcx, rbx; this
0x140068fc3  call    ?bPrepareTrgDco@DEVLOCKBLTOBJ@@QEAAHPEAVXDCOBJ@@H@Z; DEVLOCKBLTOBJ::bPrepareTrgDco(XDCOBJ *,int)
0x140068fc8  mov     [rbx+0C0h], r12
0x140068fcf  mov     r15d, r13d
0x140068fd2  mov     rax, [rsi]
0x140068fd5  mov     ebp, r12d
0x140068fd8  mov     rdi, [r14+10h]
0x140068fdc  test    rax, rax
0x140068fdf  jz      short loc_140068FEA
0x140068fe1  test    dword ptr [rax+24h], 200h
0x140068fe8  jnz     short loc_140069003
0x140068fea  mov     rax, [r14]
0x140068fed  test    rax, rax
0x140068ff0  jz      loc_1400690E9
0x140068ff6  test    dword ptr [rax+24h], 200h
0x140068ffd  jz      loc_1400690E9
0x140069003  mov     rax, [rdi]
0x140069006  mov     rcx, rdi
0x140069009  add     rax, 270h
0x14006900f  mov     [rbx+10h], rax
0x140069013  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140069018  or      dword ptr [rbx+50h], 8
0x14006901c  call    cs:__imp_GreGetLockCount
0x140069023  nop     dword ptr [rax+rax+00h]
0x140069028  test    eax, eax
0x14006902a  jnz     short loc_140069043
0x14006902c  mov     rcx, rdi
0x14006902f  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x140069034  test    al, al
0x140069036  jnz     short loc_140069043
0x140069038  mov     rcx, rdi
0x14006903b  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140069040  mov     ebp, r13d
0x140069043  mov     r8, [rsi]
0x140069046  test    r8, r8
0x140069049  jz      short loc_1400690C4
0x14006904b  mov     r9, [r14]
0x14006904e  test    r9, r9
0x140069051  jz      short loc_1400690A7
0x140069053  mov     edx, [r9+24h]
0x140069057  mov     eax, edx
0x140069059  mov     r10d, [r8+24h]
0x14006905d  xor     eax, r10d
0x140069060  bt      eax, 9
0x140069064  jnb     short loc_140069094
0x140069066  mov     rax, [r8+3D0h]
0x14006906d  mov     ecx, [rax]
0x14006906f  test    r13b, cl
0x140069072  jz      short loc_14006907A
0x140069074  bt      edx, 0Fh
0x140069078  jb      short loc_1400690A7
0x14006907a  mov     rax, [r9+3D0h]
0x140069081  mov     ecx, [rax]
0x140069083  test    r13b, cl
0x140069086  jz      short loc_14006908F
0x140069088  bt      r10d, 0Fh
0x14006908d  jb      short loc_1400690A7
0x14006908f  mov     r15d, r12d
0x140069092  jmp     short loc_1400690A7
0x140069094  and     edx, r10d
0x140069097  mov     eax, 8200h
0x14006909c  and     edx, eax
0x14006909e  mov     r15d, r12d
0x1400690a1  cmp     edx, eax
0x1400690a3  setz    r15b
0x1400690a7  mov     rax, [r8+30h]
0x1400690ab  lea     rcx, [rsp+68h+arg_0]
0x1400690b0  mov     [rsp+68h+arg_0], rax
0x1400690b5  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x1400690bc  nop     dword ptr [rax+rax+00h]
0x1400690c1  and     r15d, eax
0x1400690c4  mov     rax, [r14]
0x1400690c7  test    rax, rax
0x1400690ca  jz      short loc_1400690E9
0x1400690cc  mov     rax, [rax+30h]
0x1400690d0  lea     rcx, [rsp+68h+arg_0]
0x1400690d5  mov     [rsp+68h+arg_0], rax
0x1400690da  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x1400690e1  nop     dword ptr [rax+rax+00h]
0x1400690e6  and     r15d, eax
0x1400690e9  mov     rdx, [rsi]
0x1400690ec  mov     eax, [rdx+24h]
0x1400690ef  bt      eax, 9
0x1400690f3  jnb     loc_1400691E3
0x1400690f9  bt      eax, 0Fh
0x1400690fd  jnb     short loc_140069104
0x1400690ff  test    r15d, r15d
0x140069102  jnz     short loc_14006915B
0x140069104  mov     rdx, [rdx+40h]
0x140069108  mov     [rbx+8], rdx
0x14006910c  mov     rax, [rsi]
0x14006910f  mov     rcx, [rax+30h]
0x140069113  mov     [rbx+20h], rcx
0x140069117  test    ebp, ebp
0x140069119  jz      short loc_140069134
0x14006911b  mov     rax, [rdi]
0x14006911e  add     rax, 478h
0x140069124  cmp     rdx, rax
0x140069127  jnz     short loc_140069134
0x140069129  mov     rcx, rdi
0x14006912c  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140069131  mov     ebp, r12d
0x140069134  mov     rax, [rdi]
0x140069137  add     rax, 478h
0x14006913d  cmp     [rbx+8], rax
0x140069141  jnz     short loc_140069152
0x140069143  bts     dword ptr [rbx+50h], 15h
0x140069148  mov     rcx, rdi
0x14006914b  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x140069150  jmp     short loc_14006915B
0x140069152  mov     rcx, [rbx+20h]
0x140069156  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x14006915b  mov     rax, [r14]
0x14006915e  test    rax, rax
0x140069161  jz      short loc_14006916C
0x140069163  test    dword ptr [rax+24h], 200h
0x14006916a  jnz     short loc_1400691AD
0x14006916c  call    cs:__imp_GreGetLockCount
0x140069173  nop     dword ptr [rax+rax+00h]
0x140069178  test    eax, eax
0x14006917a  jnz     short loc_1400691AD
0x14006917c  bts     dword ptr [rbx+50h], 0Ch
0x140069181  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140069186  test    rax, rax
0x140069189  jz      short loc_140069199
0x14006918b  mov     [rax+130h], r12
0x140069192  mov     [rax+128h], r12
0x140069199  call    cs:__imp_GreIncLockCount
0x1400691a0  nop     dword ptr [rax+rax+00h]
0x1400691a5  mov     rcx, rdi
0x1400691a8  call    ??$GreAcquireSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400691ad  mov     rcx, [rsi]; this
0x1400691b0  call    ?bInFullScreen@DC@@QEBAHXZ; DC::bInFullScreen(void)
0x1400691b5  test    eax, eax
0x1400691b7  jz      short loc_1400691E3
0x1400691b9  test    dword ptr [rbx+50h], 1000h
0x1400691c0  jz      short loc_1400691CA
0x1400691c2  mov     rcx, rdi
0x1400691c5  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400691ca  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x1400691ce  test    ebp, ebp
0x1400691d0  jz      loc_140069342
0x1400691d6  mov     rcx, rdi
0x1400691d9  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x1400691de  jmp     loc_140069342
0x1400691e3  mov     rcx, rsi; this
0x1400691e6  call    ?pSurfaceEff@XDCOBJ@@QEBAPEAVSURFACE@@XZ; XDCOBJ::pSurfaceEff(void)
0x1400691eb  mov     rcx, rax; struct SURFACE *
0x1400691ee  call    ?SrcSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; SrcSurfaceAccessCheck(SURFACE *)
0x1400691f3  mov     ecx, [rbx+50h]
0x1400691f6  shl     eax, 16h
0x1400691f9  xor     eax, ecx
0x1400691fb  and     eax, 400000h
0x140069200  xor     eax, ecx
0x140069202  mov     rcx, rsi; this
0x140069205  mov     [rbx+50h], eax
0x140069208  call    ?pSurfaceEff@XDCOBJ@@QEBAPEAVSURFACE@@XZ; XDCOBJ::pSurfaceEff(void)
0x14006920d  mov     r8d, [rax+0A0h]
0x140069214  mov     eax, [rbx+50h]
0x140069217  shr     r8d, 5
0x14006921b  btr     eax, 17h
0x14006921f  not     r8d
0x140069222  and     r8d, 800000h
0x140069229  or      r8d, eax
0x14006922c  mov     [rbx+50h], r8d
0x140069230  mov     rdx, [r14]
0x140069233  test    rdx, rdx
0x140069236  jz      loc_140069373
0x14006923c  mov     eax, [rdx+24h]
0x14006923f  bt      eax, 9
0x140069243  jnb     loc_14006935B
0x140069249  bt      eax, 0Fh
0x14006924d  jnb     short loc_140069254
0x14006924f  test    r15d, r15d
0x140069252  jnz     short loc_1400692D1
0x140069254  mov     r9, [rdx+40h]
0x140069258  mov     [rbx], r9
0x14006925b  mov     rax, [r14]
0x14006925e  mov     rcx, [rax+30h]
0x140069262  mov     [rbx+18h], rcx
0x140069266  test    ebp, ebp
0x140069268  jz      short loc_140069287
0x14006926a  mov     rax, [rdi]
0x14006926d  add     rax, 478h
0x140069273  cmp     r9, rax
0x140069276  jnz     short loc_140069287
0x140069278  mov     rcx, rdi
0x14006927b  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140069280  mov     r8d, [rbx+50h]
0x140069284  mov     ebp, r12d
0x140069287  mov     rax, [rdi]
0x14006928a  add     rax, 478h
0x140069290  cmp     [rbx], rax
0x140069293  jnz     short loc_1400692A8
0x140069295  bts     r8d, 14h
0x14006929a  mov     rcx, rdi
0x14006929d  mov     [rbx+50h], r8d
0x1400692a1  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x1400692a6  jmp     short loc_1400692B1
0x1400692a8  mov     rcx, [rbx+18h]
0x1400692ac  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x1400692b1  mov     edx, [rbx+50h]
0x1400692b4  mov     r8d, 200h
0x1400692ba  test    r8d, edx
0x1400692bd  jnz     short loc_1400692D1
0x1400692bf  mov     rax, [r14]
0x1400692c2  test    dword ptr [rax+24h], 4000h
0x1400692c9  jz      short loc_1400692D1
0x1400692cb  or      edx, r8d
0x1400692ce  mov     [rbx+50h], edx
0x1400692d1  call    cs:__imp_GreGetLockCount
0x1400692d8  nop     dword ptr [rax+rax+00h]
0x1400692dd  test    eax, eax
0x1400692df  jnz     short loc_140069312
0x1400692e1  bts     dword ptr [rbx+50h], 0Ch
0x1400692e6  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x1400692eb  test    rax, rax
0x1400692ee  jz      short loc_1400692FE
0x1400692f0  mov     [rax+130h], r12
0x1400692f7  mov     [rax+128h], r12
0x1400692fe  call    cs:__imp_GreIncLockCount
0x140069305  nop     dword ptr [rax+rax+00h]
0x14006930a  mov     rcx, rdi
0x14006930d  call    ??$GreAcquireSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x140069312  mov     rdx, [r14]
0x140069315  mov     rcx, rdx; this
0x140069318  call    ?bInFullScreen@DC@@QEBAHXZ; DC::bInFullScreen(void)
0x14006931d  test    eax, eax
0x14006931f  jz      short loc_140069356
0x140069321  test    dword ptr [rbx+50h], 1000h
0x140069328  jz      short loc_140069332
0x14006932a  mov     rcx, rdi
0x14006932d  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x140069332  test    ebp, ebp
0x140069334  jz      short loc_14006933E
0x140069336  mov     rcx, rdi
0x140069339  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14006933e  and     dword ptr [rbx+50h], 0FFFFFFFEh
0x140069342  xor     eax, eax
0x140069344  add     rsp, 28h
0x140069348  pop     r15
0x14006934a  pop     r14
0x14006934c  pop     r13
0x14006934e  pop     r12
0x140069350  pop     rdi
0x140069351  pop     rsi
0x140069352  pop     rbp
0x140069353  pop     rbx
0x140069354  retn
  ... truncated ...
```
