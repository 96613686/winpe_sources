# DEVLOCKBLTOBJ::bLock(XDCOBJ &,XDCOBJ &)

- ea: `0x140065000`
- end: `0x14006597e`
- name: `?bLock@DEVLOCKBLTOBJ@@QEAAHAEAVXDCOBJ@@0@Z`
- size: `2430`
- prototype: `__int64 __fastcall(DEVLOCKBLTOBJ *__hidden this, struct XDCOBJ *, struct XDCOBJ *)`
- caller_count: `6`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140058784`
- `0x140060b1c`
- `0x140062340`
- `0x14008ad24`
- `0x14011178c`
- `0x1403113e8`

## callees

- `0x14005ec40`
- `0x14005fb58`
- `0x14005fd50`
- `0x140065000`
- `0x1400659b0`
- `0x140065f38`
- `0x140066ad4`
- `0x140066c94`
- `0x1400672ac`
- `0x140067320`
- `0x1400698fc`
- `0x1400994c8`
- `0x14009b28c`
- `0x14009b35c`
- `0x14009b430`
- `0x14009b5c8`
- `0x14009d1d0`
- `0x1400a5094`
- `0x1400a538c`
- `0x1400aa9e4`
- `0x1400ac68c`
- `0x1400acc04`
- `0x14011ec90`
- `0x140120b1c`
- `0x14014f2c8`
- `0x1401b331c`
- `0x1401cfb8c`
- `0x140304808`

## import_xrefs

- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140065859`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x1400658b6`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140065859`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x1400658b6`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14006537c`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14006535e`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14006535e`
- `win32kbase!GreGetLockCount` at `0x14006510f`
- `win32kbase!GreGetLockCount` at `0x140065408`
- `win32kbase!GreGetLockCount` at `0x1400654ad`
- `win32kbase!GreGetLockCount` at `0x1400656eb`
- `win32kbase!GreGetLockCount` at `0x14006510f`
- `win32kbase!GreGetLockCount` at `0x140065408`
- `win32kbase!GreGetLockCount` at `0x1400654ad`
- `win32kbase!GreGetLockCount` at `0x1400656eb`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400651ac`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400651d0`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400651ac`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400651d0`
- `win32kbase!GreIncLockCount` at `0x140065435`
- `win32kbase!GreIncLockCount` at `0x1400654c6`
- `win32kbase!GreIncLockCount` at `0x140065718`
- `win32kbase!GreIncLockCount` at `0x140065435`
- `win32kbase!GreIncLockCount` at `0x1400654c6`
- `win32kbase!GreIncLockCount` at `0x140065718`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400655c9`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x14006560f`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x1400655c9`
- `win32kbase!?bCompute@DC@@QEAAHXZ` at `0x14006560f`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065314`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065668`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065314`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065668`

## pseudocode

```c
__int64 __fastcall DEVLOCKBLTOBJ::bLock(DEVLOCKBLTOBJ *this, struct XDCOBJ *a2, struct XDCOBJ *a3)
{
  HSURF *v3; // rbx
  HSURF *v5; // rsi
  int v9; // ebx
  int v10; // ebp
  __int64 *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r10
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  struct SURFACE *v18; // rax
  unsigned int v19; // r8d
  __int64 v20; // rdx
  DC *v21; // rcx
  DC *v22; // rcx
  int v23; // r8d
  __int64 v24; // r9
  struct _GRETHREAD *v25; // rax
  struct _GRETHREAD *v26; // r13
  __int64 v27; // rbx
  DC *v28; // rcx
  unsigned __int64 v29; // rcx
  int v30; // eax
  struct _GRETHREAD *v31; // rax
  bool v32; // zf
  unsigned __int64 v33; // rax
  BOOL v34; // ebx
  int v35; // eax
  HDC v36; // rdx
  __int64 v37; // rdx
  int v38; // r9d
  struct _GRETHREAD *v39; // rax
  struct _GRETHREAD *CurrentThread; // rax
  __int64 v41; // r9
  int v42; // edx
  __int64 v43; // rdx
  signed __int32 v44[26]; // [rsp+0h] [rbp-68h] BYREF
  __int64 v45; // [rsp+70h] [rbp+8h] BYREF

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
    goto LABEL_2;
  }
  *((_QWORD *)this + 11) = 0;
  v9 = 1;
  *((_QWORD *)this + 24) = 0;
  v10 = 0;
  v11 = (__int64 *)*((_QWORD *)a2 + 2);
  if ( *(_QWORD *)a3 && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x200) != 0
    || *(_QWORD *)a2 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 )
  {
    v12 = *((_QWORD *)a2 + 2);
    *((_QWORD *)this + 2) = *v11 + 624;
    GreAcquireSemaphoreShared<1,>(v12);
    *((_DWORD *)this + 20) |= 8u;
    if ( !(unsigned int)GreGetLockCount()
      && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v11) )
    {
      GreAcquireSemaphoreShared<2,>(v11);
      v10 = 1;
    }
    v13 = *(_QWORD *)a3;
    if ( !*(_QWORD *)a3 )
      goto LABEL_18;
    v14 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
    {
      v15 = *(_DWORD *)(v14 + 36);
      v16 = *(_DWORD *)(v13 + 36);
      if ( ((v16 ^ v15) & 0x200) != 0 )
      {
        if ( (**(_BYTE **)(v13 + 976) & 1) != 0 && (v15 & 0x8000) != 0
          || (**(_DWORD **)(v14 + 976) & 1) != 0 && (v16 & 0x8000) != 0 )
        {
          v9 = 1;
          goto LABEL_17;
        }
      }
      else if ( (v16 & 0x200) != 0 )
      {
        v9 = 1;
        if ( (v15 & 0x8200) == 33280 && (*(_DWORD *)(v13 + 36) & 0x8000) != 0 )
          goto LABEL_17;
      }
      v9 = 0;
    }
LABEL_17:
    v45 = *(_QWORD *)(v13 + 48);
    v9 &= PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v45);
LABEL_18:
    if ( *(_QWORD *)a2 )
    {
      v45 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
      v9 &= PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v45);
    }
  }
  v17 = *(_DWORD *)(*(_QWORD *)a3 + 36LL);
  if ( (v17 & 0x200) != 0 )
  {
    if ( (v17 & 0x8000) == 0 || !v9 )
    {
      v43 = *(_QWORD *)(*(_QWORD *)a3 + 64LL);
      *((_QWORD *)this + 1) = v43;
      *((_QWORD *)this + 4) = *(_QWORD *)(*(_QWORD *)a3 + 48LL);
      if ( v10 && v43 == *v11 + 1144 )
      {
        GreReleaseSemaphoreShared<2,>(v11);
        v10 = 0;
      }
      if ( *((_QWORD *)this + 1) == *v11 + 1144 )
      {
        *((_DWORD *)this + 20) |= 0x200000u;
        GreAcquireSemaphore<2,>(v11);
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
      GreAcquireSemaphoreShared<3,>(v11);
    }
    if ( (unsigned int)DC::bInFullScreen(*(DC **)a3) )
    {
      if ( (*((_DWORD *)this + 20) & 0x1000) != 0 )
        GreReleaseSemaphoreShared<3,>(v11);
      *((_DWORD *)this + 20) &= ~1u;
      if ( v10 )
        GreReleaseSemaphoreShared<2,>(v11);
      return 0;
    }
  }
  v18 = XDCOBJ::pSurfaceEff(a3);
  *((_DWORD *)this + 20) ^= (*((_DWORD *)this + 20) ^ ((unsigned int)SrcSurfaceAccessCheck(v18) << 22)) & 0x400000;
  v19 = *((_DWORD *)this + 20) & 0xFF7FFFFF | ~(*((_DWORD *)XDCOBJ::pSurfaceEff(a3) + 36) >> 5) & 0x800000;
  *((_DWORD *)this + 20) = v19;
  v20 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    v30 = *(_DWORD *)(v20 + 36);
    if ( (v30 & 0x200) == 0 )
      goto LABEL_64;
    if ( (v30 & 0x8000) == 0 || !v9 )
    {
      v41 = *(_QWORD *)(v20 + 64);
      *(_QWORD *)this = v41;
      *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
      if ( v10 && v41 == *v11 + 1144 )
      {
        GreReleaseSemaphoreShared<2,>(v11);
        v19 = *((_DWORD *)this + 20);
        v10 = 0;
      }
      if ( *(_QWORD *)this == *v11 + 1144 )
      {
        *((_DWORD *)this + 20) = v19 | 0x100000;
        GreAcquireSemaphore<2,>(v11);
      }
      else
      {
        GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 3));
      }
      v42 = *((_DWORD *)this + 20);
      if ( (v42 & 0x200) == 0 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) != 0 )
        *((_DWORD *)this + 20) = v42 | 0x200;
    }
    if ( !(unsigned int)GreGetLockCount() )
    {
      *((_DWORD *)this + 20) |= 0x1000u;
      v31 = GreGetCurrentThread();
      if ( v31 )
      {
        *((_QWORD *)v31 + 38) = 0;
        *((_QWORD *)v31 + 37) = 0;
      }
      GreIncLockCount();
      GreAcquireSemaphoreShared<3,>(v11);
    }
    if ( (unsigned int)DC::bInFullScreen(*(DC **)a2) )
    {
      v32 = (*((_DWORD *)this + 20) & 0x1000) == 0;
      goto LABEL_66;
    }
    if ( v20 )
    {
LABEL_64:
      if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && (*(_DWORD *)(v20 + 36) & 0x80000) != 0 )
      {
LABEL_65:
        v32 = *((_QWORD *)this + 2) == 0;
LABEL_66:
        if ( !v32 )
          GreReleaseSemaphoreShared<3,>(v11);
        if ( v10 )
          GreReleaseSemaphoreShared<2,>(v11);
        goto LABEL_2;
      }
    }
  }
  else
  {
    v20 = 0;
  }
  if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x80000) != 0
    || v20
    && ((*((_DWORD *)this + 20) & 0x1000) != 0 || (*(_DWORD *)(v20 + 36) & 0x200) == 0)
    && (*(_DWORD *)(v20 + 36) & 0x10) != 0
    && !DC::bCompute((DC *)v20) )
  {
    goto LABEL_65;
  }
  if ( !DC::prgnRao(*(DC **)a2) && !DC::prgnVisSnap(v21) )
    goto LABEL_2;
  if ( ((*((_DWORD *)this + 20) & 0x1000) != 0 || (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x200) == 0)
    && (*(_DWORD *)(*(_QWORD *)a3 + 36LL) & 0x10) != 0
    && !DC::bCompute(*(DC **)a3) )
  {
    goto LABEL_65;
  }
  if ( !DC::prgnRao(*(DC **)a3) && !DC::prgnVisSnap(v22) )
    goto LABEL_2;
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 || (*(_DWORD *)(v24 + 36) & 0x200) != 0 )
  {
    if ( (*((_DWORD *)this + 20) & 0x1000) == 0 )
      goto LABEL_49;
    if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) != 0 )
    {
      if ( *((_QWORD *)this + 38) )
        UserIsCurrentProcessImmersiveAppContainer();
      else
        DC::vSetRendering(*(DC **)a2);
      v25 = GreGetCurrentThread();
      v26 = v25;
      if ( v25 )
      {
        *((_QWORD *)v25 + 37) = *(_QWORD *)a2;
        if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) == 0 )
        {
          *((_DWORD *)v25 + 84) |= 1u;
          *(_QWORD *)(*(_QWORD *)a2 + 1976LL) = 0;
          v27 = *v11;
          GreAcquireSemaphoreSharedInternal((HSEMAPHORE)(*v11 + 832));
          GrepAcquireLockValidate<14>();
          *((_DWORD *)v26 + 87) = *((_DWORD *)v11 + 1098);
          GreReleaseSemaphoreCommon<14,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v27 + 832);
        }
      }
    }
    v28 = *(DC **)a3;
    if ( **(_QWORD **)a3 != **(_QWORD **)a2 && (*((_DWORD *)v28 + 9) & 0x200) != 0 )
    {
      if ( *((_QWORD *)this + 41) )
        UserIsCurrentProcessImmersiveAppContainer();
      else
        DC::vSetRendering(v28);
      v39 = GreGetCurrentThread();
      if ( v39 )
        *((_QWORD *)v39 + 38) = *(_QWORD *)a3;
    }
  }
  else if ( !(unsigned int)GreGetLockCount() )
  {
    *((_DWORD *)this + 20) |= 0x80000u;
    GreIncLockCount();
  }
  if ( (*((_DWORD *)this + 20) & 0x1000) != 0 && *((_QWORD *)this + 2) )
    GreReleaseSemaphoreShared<3,>(v11);
LABEL_49:
  if ( v10 )
    GreReleaseSemaphoreShared<2,>(v11);
  if ( (*((_DWORD *)this + 20) & 0x1000) == 0 )
    goto LABEL_83;
  if ( *(_QWORD *)a3 )
    v29 = *(_QWORD *)(*(_QWORD *)a3 + 496LL);
  else
    v29 = 0;
  v37 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
    v33 = *(_QWORD *)(v37 + 496);
  else
    v33 = 0;
  if ( v29 && v33 && v29 != v33 )
  {
    if ( v29 < v33 )
    {
      *((_DWORD *)this + 20) |= 0x8000u;
      v34 = DEVLOCKBLTOBJ::bPrepareSrcDco(this, a3, v23, 1) == 0;
      _InterlockedOr(v44, 0);
      v35 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1);
      goto LABEL_79;
    }
    v34 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1) == 0;
    _InterlockedOr(v44, 0);
    v38 = 1;
  }
  else
  {
    v34 = 0;
    if ( v37 )
      v34 = DEVLOCKBLTOBJ::bPrepareTrgDco(this, a2, 1) == 0;
    if ( *(_QWORD *)a2 && **(_QWORD **)a2 == **(_QWORD **)a3 )
      goto LABEL_80;
    v38 = 0;
  }
  v35 = DEVLOCKBLTOBJ::bPrepareSrcDco(this, a3, v23, v38);
LABEL_79:
  if ( !v35 )
    goto LABEL_2;
LABEL_80:
  if ( v34
    || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 48LL) + 40LL) & 0x8000) != 0
    && *(_QWORD *)(*(_QWORD *)a2 + 496LL)
    && *(_QWORD *)this )
  {
    goto LABEL_2;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 48LL) + 40LL) & 0x8000) != 0
    && *(_QWORD *)(*(_QWORD *)a3 + 496LL)
    && *((_QWORD *)this + 1) )
  {
    *((_QWORD *)this + 9) = a3;
    *((_QWORD *)this + 8) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 496LL) + 32LL);
    if ( bCopySurface(
           (DEVLOCKBLTOBJ *)((char *)this + 40),
           (struct _SURFOBJ *)(*(_QWORD *)(*(_QWORD *)a3 + 496LL) + 24LL))
      && XDCOBJ::SetSurfaceEff(a3, *((struct SURFACE **)this + 5)) )
    {
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
        GreReleaseSemaphoreShared<1,>(v11);
        *((_QWORD *)this + 2) = 0;
      }
      goto LABEL_83;
    }
LABEL_2:
    *((_DWORD *)this + 20) &= ~1u;
    return 0;
  }
LABEL_83:
  if ( (*((_DWORD *)this + 20) & 0x81000) != 0 )
  {
    DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKBLTOBJ *)((char *)this + 88), **(HDC **)a2);
    v36 = **(HDC **)a3;
    if ( v36 != **(HDC **)a2 )
      DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKBLTOBJ *)((char *)this + 192), v36);
  }
  return 1;
}

```

## disassembly

```asm
0x140065000  push    rbx
0x140065002  push    rbp
0x140065003  push    rsi
0x140065004  push    rdi
0x140065005  push    r12
0x140065007  push    r13
0x140065009  push    r14
0x14006500b  push    r15
0x14006500d  sub     rsp, 28h
0x140065011  xor     r12d, r12d
0x140065014  lea     rbx, [rcx+148h]
0x14006501b  mov     rdi, rcx
0x14006501e  mov     [rcx], r12
0x140065021  mov     [rcx+8], r12
0x140065025  lea     rsi, [rcx+150h]
0x14006502c  mov     [rcx+10h], r12
0x140065030  mov     r14, rdx
0x140065033  mov     [rcx+18h], r12
0x140065037  lea     rdx, [rcx+138h]; HSURF *
0x14006503e  mov     [rcx+20h], r12
0x140065042  lea     ebp, [r12+1]
0x140065047  mov     [rcx+50h], ebp
0x14006504a  lea     r9, [rdi+54h]; unsigned int *
0x14006504e  mov     [rcx+40h], r12
0x140065052  mov     r15, r8
0x140065055  mov     [rcx+48h], r12
0x140065059  lea     r8, [rcx+130h]; HSURF *
0x140065060  mov     [rcx+128h], r12
0x140065067  mov     [r8], r12
0x14006506a  mov     [rdx], r12
0x14006506d  mov     [rbx], r12
0x140065070  mov     [rsi], r12
0x140065073  mov     rax, [r14]
0x140065076  mov     rcx, [rax]
0x140065079  mov     [rdi+140h], rcx
0x140065080  mov     rax, [r15]
0x140065083  mov     rcx, [rax]
0x140065086  mov     [rdi+158h], rcx
0x14006508d  mov     rcx, r14; struct XDCOBJ *
0x140065090  call    ?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z; TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)
0x140065095  test    al, al
0x140065097  jnz     short loc_1400650B1
0x140065099  and     dword ptr [rdi+50h], 0FFFFFFFEh
0x14006509d  xor     eax, eax
0x14006509f  add     rsp, 28h
0x1400650a3  pop     r15
0x1400650a5  pop     r14
0x1400650a7  pop     r13
0x1400650a9  pop     r12
0x1400650ab  pop     rdi
0x1400650ac  pop     rsi
0x1400650ad  pop     rbp
0x1400650ae  pop     rbx
0x1400650af  retn
0x1400650b1  xor     r9d, r9d; unsigned int *
0x1400650b4  mov     r8, rbx; HSURF *
0x1400650b7  mov     rdx, rsi; HSURF *
0x1400650ba  mov     rcx, r15; struct XDCOBJ *
0x1400650bd  call    ?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z; TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)
0x1400650c2  test    al, al
0x1400650c4  jz      short loc_140065099
0x1400650c6  mov     [rdi+58h], r12
0x1400650ca  mov     ebx, ebp
0x1400650cc  mov     [rdi+0C0h], r12
0x1400650d3  mov     ebp, r12d
0x1400650d6  mov     rax, [r15]
0x1400650d9  mov     r13d, 200h
0x1400650df  mov     rsi, [r14+10h]
0x1400650e3  test    rax, rax
0x1400650e6  jz      loc_1400651E0
0x1400650ec  test    [rax+24h], r13d
0x1400650f0  jz      loc_1400651E0
0x1400650f6  mov     rax, [rsi]
0x1400650f9  mov     rcx, rsi
0x1400650fc  add     rax, 270h
0x140065102  mov     [rdi+10h], rax
0x140065106  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x14006510b  or      dword ptr [rdi+50h], 8
0x14006510f  call    cs:__imp_GreGetLockCount
0x140065116  nop     dword ptr [rax+rax+00h]
0x14006511b  test    eax, eax
0x14006511d  jnz     loc_140065628
0x140065123  mov     rcx, rsi
0x140065126  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x14006512b  test    al, al
0x14006512d  jnz     loc_140065628
0x140065133  mov     rcx, rsi
0x140065136  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14006513b  mov     r11d, ebx
0x14006513e  mov     ebp, ebx
0x140065140  mov     r9, [r15]
0x140065143  test    r9, r9
0x140065146  jz      short loc_1400651BA
0x140065148  mov     r10, [r14]
0x14006514b  test    r10, r10
0x14006514e  jz      short loc_14006519E
0x140065150  mov     edx, [r10+24h]
0x140065154  mov     eax, edx
0x140065156  mov     r8d, [r9+24h]
0x14006515a  xor     eax, r8d
0x14006515d  test    r13d, eax
0x140065160  jz      loc_1400655B8
0x140065166  mov     rax, [r9+3D0h]
0x14006516d  test    [rax], r11b
0x140065170  setnz   cl
0x140065173  bt      edx, 0Fh
0x140065177  setb    al
0x14006517a  test    al, cl
0x14006517c  jnz     short loc_14006519B
0x14006517e  mov     rax, [r10+3D0h]
0x140065185  mov     ecx, [rax]
0x140065187  test    r11b, cl
0x14006518a  jz      loc_1400655C1
0x140065190  bt      r8d, 0Fh
0x140065195  jnb     loc_1400655C1
0x14006519b  mov     ebx, r11d
0x14006519e  mov     rax, [r9+30h]
0x1400651a2  lea     rcx, [rsp+68h+arg_0]
0x1400651a7  mov     [rsp+68h+arg_0], rax
0x1400651ac  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x1400651b3  nop     dword ptr [rax+rax+00h]
0x1400651b8  and     ebx, eax
0x1400651ba  mov     rax, [r14]
0x1400651bd  test    rax, rax
0x1400651c0  jz      short loc_1400651F2
0x1400651c2  mov     rax, [rax+30h]
0x1400651c6  lea     rcx, [rsp+68h+arg_0]
0x1400651cb  mov     [rsp+68h+arg_0], rax
0x1400651d0  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x1400651d7  nop     dword ptr [rax+rax+00h]
0x1400651dc  and     ebx, eax
0x1400651de  jmp     short loc_1400651F2
0x1400651e0  mov     rax, [r14]
0x1400651e3  test    rax, rax
0x1400651e6  jz      short loc_1400651F2
0x1400651e8  test    [rax+24h], r13d
0x1400651ec  jnz     loc_1400650F6
0x1400651f2  mov     rdx, [r15]
0x1400651f5  mov     eax, [rdx+24h]
0x1400651f8  test    r13d, eax
0x1400651fb  jnz     loc_140065691
0x140065201  mov     rcx, r15; this
0x140065204  call    ?pSurfaceEff@XDCOBJ@@QEBAPEAVSURFACE@@XZ; XDCOBJ::pSurfaceEff(void)
0x140065209  mov     rcx, rax; struct SURFACE *
0x14006520c  call    ?SrcSurfaceAccessCheck@@YAHPEAVSURFACE@@@Z; SrcSurfaceAccessCheck(SURFACE *)
0x140065211  mov     ecx, [rdi+50h]
0x140065214  shl     eax, 16h
0x140065217  xor     eax, ecx
0x140065219  and     eax, 400000h
0x14006521e  xor     eax, ecx
0x140065220  mov     rcx, r15; this
0x140065223  mov     [rdi+50h], eax
0x140065226  call    ?pSurfaceEff@XDCOBJ@@QEBAPEAVSURFACE@@XZ; XDCOBJ::pSurfaceEff(void)
0x14006522b  mov     r8d, [rax+90h]
0x140065232  mov     eax, [rdi+50h]
0x140065235  shr     r8d, 5
0x140065239  btr     eax, 17h
0x14006523d  not     r8d
0x140065240  and     r8d, 800000h
0x140065247  or      r8d, eax
0x14006524a  mov     [rdi+50h], r8d
0x14006524e  mov     rdx, [r14]
0x140065251  test    rdx, rdx
0x140065254  jnz     loc_1400653EE
0x14006525a  mov     rdx, r12
0x14006525d  mov     ebx, 1000h
0x140065262  mov     r8d, [rdi+50h]
0x140065266  and     r8d, ebx
0x140065269  jz      short loc_14006527B
0x14006526b  mov     rax, [r15]
0x14006526e  test    dword ptr [rax+24h], 80000h
0x140065275  jnz     loc_140065480
0x14006527b  test    rdx, rdx
0x14006527e  jz      short loc_140065294
0x140065280  test    r8d, r8d
0x140065283  jz      loc_1400655FD
0x140065289  mov     eax, [rdx+24h]
0x14006528c  test    al, 10h
0x14006528e  jnz     loc_14006560C
0x140065294  mov     rcx, [r14]; this
0x140065297  call    ?prgnRao@DC@@QEBAPEAVREGION@@XZ; DC::prgnRao(void)
0x14006529c  test    rax, rax
0x14006529f  jnz     short loc_1400652AF
0x1400652a1  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x1400652a6  test    rax, rax
0x1400652a9  jz      loc_140065099
0x1400652af  test    [rdi+50h], ebx
0x1400652b2  jz      loc_1400655A6
0x1400652b8  mov     rcx, [r15]
0x1400652bb  mov     eax, [rcx+24h]
0x1400652be  test    al, 10h
0x1400652c0  jnz     loc_1400655C9
0x1400652c6  mov     r9, [r15]
0x1400652c9  mov     rcx, r9; this
0x1400652cc  call    ?prgnRao@DC@@QEBAPEAVREGION@@XZ; DC::prgnRao(void)
0x1400652d1  test    rax, rax
0x1400652d4  jnz     short loc_1400652E4
0x1400652d6  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x1400652db  test    rax, rax
0x1400652de  jz      loc_140065099
0x1400652e4  mov     rdx, [r14]
0x1400652e7  mov     ecx, [rdx+24h]
0x1400652ea  and     ecx, r13d
0x1400652ed  jz      loc_1400654A3
0x1400652f3  test    [rdi+50h], ebx
0x1400652f6  jz      loc_1400653C5
0x1400652fc  test    ecx, ecx
0x1400652fe  jz      loc_14006539A
0x140065304  cmp     [rdi+130h], r12
0x14006530b  jnz     loc_140065859
0x140065311  mov     rcx, rdx
0x140065314  call    cs:__imp_?vSetRendering@DC@@QEAAXXZ; DC::vSetRendering(void)
0x14006531b  nop     dword ptr [rax+rax+00h]
0x140065320  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140065325  mov     r13, rax
0x140065328  test    rax, rax
0x14006532b  jz      short loc_140065394
0x14006532d  mov     rcx, [r14]
0x140065330  mov     [rax+128h], rcx
0x140065337  mov     rcx, [r14]
0x14006533a  test    dword ptr [rcx+24h], 4000h
0x140065341  jnz     short loc_140065394
0x140065343  or      dword ptr [rax+150h], 1
0x14006534a  mov     rcx, [r14]
0x14006534d  mov     [rcx+7B8h], r12
0x140065354  mov     rbx, [rsi]
0x140065357  lea     rcx, [rbx+340h]
0x14006535e  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065365  nop     dword ptr [rax+rax+00h]
0x14006536a  call    ??$GrepAcquireLockValidate@$0O@@@YAXXZ; GrepAcquireLockValidate<14>(void)
0x14006536f  mov     eax, [rsi+1128h]
0x140065375  lea     rdx, [rbx+340h]
0x14006537c  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065383  mov     [r13+15Ch], eax
0x14006538a  call    ??$GreReleaseSemaphoreCommon@$0O@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<14,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14006538f  mov     ebx, 1000h
0x140065394  mov     r13d, 200h
0x14006539a  mov     rax, [r14]
0x14006539d  mov     rcx, [r15]
0x1400653a0  mov     rdx, [rax]
0x1400653a3  cmp     [rcx], rdx
0x1400653a6  jz      short loc_1400653B2
0x1400653a8  test    [rcx+24h], r13d
0x1400653ac  jnz     loc_14006565B
0x1400653b2  test    [rdi+50h], ebx
0x1400653b5  jz      short loc_1400653C5
0x1400653b7  cmp     [rdi+10h], r12
0x1400653bb  jz      short loc_1400653C5
0x1400653bd  mov     rcx, rsi
0x1400653c0  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400653c5  test    ebp, ebp
0x1400653c7  jz      short loc_1400653D1
0x1400653c9  mov     rcx, rsi
0x1400653cc  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x1400653d1  test    [rdi+50h], ebx
0x1400653d4  jz      loc_14006556A
0x1400653da  mov     rcx, [r15]
0x1400653dd  test    rcx, rcx
0x1400653e0  jnz     loc_1400655E2
0x1400653e6  mov     rcx, r12
0x1400653e9  jmp     loc_1400655E9
0x1400653ee  mov     eax, [rdx+24h]
0x1400653f1  test    r13d, eax
0x1400653f4  jz      short loc_140065465
0x1400653f6  bt      eax, 0Fh
0x1400653fa  jnb     loc_14006572E
0x140065400  test    ebx, ebx
0x140065402  jz      loc_14006572E
0x140065408  call    cs:__imp_GreGetLockCount
0x14006540f  nop     dword ptr [rax+rax+00h]
0x140065414  test    eax, eax
0x140065416  jnz     short loc_140065449
0x140065418  bts     dword ptr [rdi+50h], 0Ch
0x14006541d  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140065422  test    rax, rax
0x140065425  jz      short loc_140065435
0x140065427  mov     [rax+130h], r12
0x14006542e  mov     [rax+128h], r12
0x140065435  call    cs:__imp_GreIncLockCount
0x14006543c  nop     dword ptr [rax+rax+00h]
0x140065441  mov     rcx, rsi
0x140065444  call    ??$GreAcquireSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x140065449  mov     rdx, [r14]
0x14006544c  mov     rcx, rdx; this
0x14006544f  call    ?bInFullScreen@DC@@QEBAHXZ; DC::bInFullScreen(void)
0x140065454  test    eax, eax
0x140065456  jnz     loc_1400658AA
0x14006545c  test    rdx, rdx
0x14006545f  jz      loc_14006525D
0x140065465  mov     ebx, 1000h
0x14006546a  test    [rdi+50h], ebx
0x14006546d  jz      loc_140065262
0x140065473  test    dword ptr [rdx+24h], 80000h
0x14006547a  jz      loc_140065262
0x140065480  cmp     [rdi+10h], r12
0x140065484  jz      short loc_14006548E
0x140065486  mov     rcx, rsi
0x140065489  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x14006548e  test    ebp, ebp
0x140065490  jz      loc_140065099
  ... truncated ...
```
