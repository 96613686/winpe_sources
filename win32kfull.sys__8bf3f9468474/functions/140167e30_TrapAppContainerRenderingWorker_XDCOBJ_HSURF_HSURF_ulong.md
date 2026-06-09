# TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)

- ea: `0x140167e30`
- end: `0x1401683af`
- name: `?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z`
- size: `1407`
- prototype: `bool __fastcall(struct XDCOBJ *, HSURF *, HSURF *, unsigned int *)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140068f04`
- `0x14006d614`
- `0x140167e10`

## callees

- `0x14005f380`
- `0x14005fb0c`
- `0x140062bf4`
- `0x14006cd1c`
- `0x140077d74`
- `0x14007f010`
- `0x1400846c8`
- `0x14008d990`
- `0x14008e730`
- `0x14008e84c`
- `0x140093684`
- `0x14009654c`
- `0x140096604`
- `0x140167e30`
- `0x1401683b8`
- `0x14016ab60`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140167ef4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140167ef4`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401682c8`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401682c8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140167e78`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140167e78`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140167e68`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x140167e68`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140167ecc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140167fe4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016806a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168095`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168110`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168159`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168231`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016825c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140167ecc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140167fe4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016806a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168095`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168110`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168159`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168231`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016825c`
- `win32kbase!HmgShareLock` at `0x140168085`
- `win32kbase!HmgShareLock` at `0x1401680b0`
- `win32kbase!HmgShareLock` at `0x14016824c`
- `win32kbase!HmgShareLock` at `0x140168277`
- `win32kbase!HmgShareLock` at `0x140168085`
- `win32kbase!HmgShareLock` at `0x1401680b0`
- `win32kbase!HmgShareLock` at `0x14016824c`
- `win32kbase!HmgShareLock` at `0x140168277`
- `win32kbase!PushThreadGuardedObject` at `0x140167f78`
- `win32kbase!PushThreadGuardedObject` at `0x140167fa6`
- `win32kbase!PushThreadGuardedObject` at `0x140167f78`
- `win32kbase!PushThreadGuardedObject` at `0x140167fa6`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140167f18`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401680df`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401681b8`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140168326`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14016834b`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140168123`
- `win32kbase!INC_SHARE_REF_CNT` at `0x14016816d`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140168123`
- `win32kbase!INC_SHARE_REF_CNT` at `0x14016816d`
- `win32kbase!GreGetLockCount` at `0x140167fd0`
- `win32kbase!GreGetLockCount` at `0x140167fd0`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140168000`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140168000`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140168022`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401681e9`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140168022`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401681e9`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401680c5`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016828c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016830c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016838b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x1401680c5`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016828c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016830c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x14016838b`

## pseudocode

```c
char __fastcall TrapAppContainerRenderingWorker(struct XDCOBJ *a1, HSURF *a2, HSURF *a3, unsigned int *a4)
{
  __int64 v8; // rcx
  Gre::Base **CurrentThreadWin32Thread; // rax
  Gre::Base *v10; // rcx
  struct Gre::Base::SESSION_GLOBALS *v12; // rax
  _DWORD *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r13
  Gre::Base *v21; // rcx
  struct Gre::Base::SESSION_GLOBALS *v22; // rax
  int v23; // esi
  int v24; // edi
  Gre::Base *v25; // rcx
  HBITMAP CompatibleBitmap; // rsi
  __int64 v27; // rdi
  struct Gre::Base::SESSION_GLOBALS *v28; // rax
  __int64 v29; // r8
  Gre::Base *v30; // rcx
  struct Gre::Base::SESSION_GLOBALS *v31; // rax
  __int64 v32; // r8
  struct SURFACE *v33; // rax
  HSURF v34; // rcx
  struct Gre::Base::SESSION_GLOBALS *v35; // rax
  Gre::Base *v36; // rcx
  struct Gre::Base::SESSION_GLOBALS *v37; // rax
  int v38; // esi
  int v39; // edi
  HBITMAP v40; // rsi
  Gre::Base *v41; // rcx
  __int64 v42; // rdi
  struct Gre::Base::SESSION_GLOBALS *v43; // rax
  __int64 v44; // r8
  Gre::Base *v45; // rcx
  struct Gre::Base::SESSION_GLOBALS *v46; // rax
  __int64 v47; // r8
  _QWORD *CurrentProcessWin32Process; // rax
  char v49; // [rsp+30h] [rbp-D0h]
  __int64 v50; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v51; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v52[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct SURFACE *v53; // [rsp+68h] [rbp-98h]
  _OWORD v54[2]; // [rsp+70h] [rbp-90h] BYREF
  SURFACE *v55; // [rsp+90h] [rbp-70h]
  _BYTE v56[112]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v57[96]; // [rsp+110h] [rbp+10h] BYREF

  *a2 = 0;
  if ( !(unsigned int)UserIsCurrentProcessImmersiveAppContainer() )
    return 1;
  CurrentThreadWin32Thread = (Gre::Base **)PsGetCurrentThreadWin32Thread(v8);
  if ( CurrentThreadWin32Thread )
  {
    v10 = *CurrentThreadWin32Thread;
    if ( *CurrentThreadWin32Thread )
    {
      if ( v10 != (Gre::Base *)-8LL && (*((_DWORD *)v10 + 86) & 4) != 0 )
        return 1;
    }
  }
  v12 = Gre::Base::Globals(v10);
  SEMOBJSHARED<1>::SEMOBJSHARED<1>(&v50, v12);
  v13 = *(_DWORD **)(*(_QWORD *)a1 + 496LL);
  if ( !v13 || v13[172] == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) && (int)v13[40] >= 0 )
    goto LABEL_10;
  v18 = *(_QWORD *)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 472LL) && *(_DWORD *)(v18 + 488) && !*(_DWORD *)(v18 + 492) )
  {
    CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process(v15, v14, v16, v17);
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
      CurrentProcessWin32Process = 0;
    if ( CurrentProcessWin32Process == *(_QWORD **)(*(_QWORD *)a1 + 480LL) )
    {
LABEL_10:
      GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
      return 1;
    }
  }
  memset(v54, 0, sizeof(v54));
  PushThreadGuardedObject(
    v54,
    v54,
    UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
  v55 = 0;
  memset(v52, 0, sizeof(v52));
  PushThreadGuardedObject(
    v52,
    v52,
    UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
  v19 = *(_QWORD *)a1;
  v20 = *((_QWORD *)a1 + 2);
  v53 = 0;
  if ( (*(_DWORD *)(v19 + 36) & 0x200) != 0 )
  {
    v49 = 0;
    if ( !(unsigned int)GreGetLockCount()
      && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v20) )
    {
      GreAcquireSemaphore<2,>(v20);
      v49 = 1;
    }
    v22 = Gre::Base::Globals(v21);
    SEMOBJSHARED<3>::SEMOBJSHARED<3>(&v51, v22);
    DC::vSetRendering(*(DC **)a1);
    v23 = v13[14];
    v24 = v13[15];
    OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v56, a1);
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
    CompatibleBitmap = GrepCreateCompatibleBitmap((struct OPTAPIDCOBJ *)v56, v23, v24, 0, 0, 0);
    if ( CompatibleBitmap )
    {
      v27 = **(_QWORD **)(*(_QWORD *)a1 + 496LL);
      v28 = Gre::Base::Globals(v25);
      LOBYTE(v29) = 5;
      v55 = (SURFACE *)HmgShareLock(v28, v27, v29, 1);
      v31 = Gre::Base::Globals(v30);
      LOBYTE(v32) = 5;
      v53 = (struct SURFACE *)HmgShareLock(v31, CompatibleBitmap, v32, 1);
      ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
      OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v56);
      GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
      if ( v49 )
        GreReleaseSemaphoreShared<2,>(v20);
      goto LABEL_19;
    }
    DC::vClearRendering(*(DC **)a1);
    if ( v49 )
      GreReleaseSemaphoreShared<2,>(v20);
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v56);
    GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
LABEL_35:
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v54);
    GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
    return 0;
  }
  v38 = v13[14];
  v39 = v13[15];
  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v56, a1);
  ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
  v40 = GrepCreateCompatibleBitmap((struct OPTAPIDCOBJ *)v56, v38, v39, 0, 0, 0);
  if ( !v40 )
  {
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v56);
    goto LABEL_35;
  }
  v41 = *(Gre::Base **)(*(_QWORD *)a1 + 496LL);
  v42 = *(_QWORD *)v41;
  v43 = Gre::Base::Globals(v41);
  LOBYTE(v44) = 5;
  v55 = (SURFACE *)HmgShareLock(v43, v42, v44, 1);
  v46 = Gre::Base::Globals(v45);
  LOBYTE(v47) = 5;
  v53 = (struct SURFACE *)HmgShareLock(v46, v40, v47, 1);
  ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v57);
  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v56);
LABEL_19:
  v33 = v53;
  *a2 = *(HSURF *)v55;
  v34 = *(HSURF *)v33;
  *a3 = *(HSURF *)v33;
  v35 = Gre::Base::Globals((Gre::Base *)v34);
  INC_SHARE_REF_CNT(v35, v55);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x4000) != 0 && (unsigned int)SURFACE::bRedirectionBitmap(v55) )
    ++*((_DWORD *)v53 + 93);
  *(_QWORD *)(*(_QWORD *)a1 + 504LL) = *a2;
  DC::pSurface(*(DC **)a1, v53);
  v37 = Gre::Base::Globals(v36);
  INC_SHARE_REF_CNT(v37, v53);
  if ( a4 )
  {
    *a4 = *(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0xE0;
    *(_DWORD *)(*(_QWORD *)a1 + 36LL) &= 0xFFFFFF1F;
  }
  GreAcquireSemaphoreShared<1,>(v20);
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v52);
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v54);
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal);
  return 1;
}

```

## disassembly

```asm
0x140167e30  push    rbp
0x140167e32  push    rbx
0x140167e33  push    rsi
0x140167e34  push    r12
0x140167e36  push    r14
0x140167e38  push    r15
0x140167e3a  lea     rbp, [rsp-98h]
0x140167e42  sub     rsp, 198h
0x140167e49  mov     rax, cs:__security_cookie
0x140167e50  xor     rax, rsp
0x140167e53  mov     [rbp+0C0h+var_50], rax
0x140167e57  xor     esi, esi
0x140167e59  mov     r15, r9
0x140167e5c  mov     [rdx], rsi
0x140167e5f  mov     r12, r8
0x140167e62  mov     rbx, rdx
0x140167e65  mov     r14, rcx
0x140167e68  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x140167e6f  nop     dword ptr [rax+rax+00h]
0x140167e74  test    eax, eax
0x140167e76  jz      short loc_140167EA4
0x140167e78  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140167e7f  nop     dword ptr [rax+rax+00h]
0x140167e84  test    rax, rax
0x140167e87  jz      short loc_140167EC4
0x140167e89  mov     rcx, [rax]
0x140167e8c  test    rcx, rcx
0x140167e8f  jz      short loc_140167EC4
0x140167e91  lea     rax, [rcx+8]
0x140167e95  test    rax, rax
0x140167e98  jz      short loc_140167EC4
0x140167e9a  mov     eax, [rax+150h]
0x140167ea0  test    al, 4
0x140167ea2  jz      short loc_140167EC4
0x140167ea4  mov     al, 1
0x140167ea6  mov     rcx, [rbp+0C0h+var_50]
0x140167eaa  xor     rcx, rsp; StackCookie
0x140167ead  call    __security_check_cookie
0x140167eb2  add     rsp, 198h
0x140167eb9  pop     r15
0x140167ebb  pop     r14
0x140167ebd  pop     r12
0x140167ebf  pop     rsi
0x140167ec0  pop     rbx
0x140167ec1  pop     rbp
0x140167ec2  retn
0x140167ec4  mov     [rsp+1C0h+var_30], rdi
0x140167ecc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140167ed3  nop     dword ptr [rax+rax+00h]
0x140167ed8  mov     rdx, rax
0x140167edb  lea     rcx, [rsp+1C0h+var_188]
0x140167ee0  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x140167ee5  mov     rax, [r14]
0x140167ee8  mov     rdi, [rax+1F0h]
0x140167eef  test    rdi, rdi
0x140167ef2  jz      short loc_140167F13
0x140167ef4  call    cs:__imp_PsGetCurrentProcessId
0x140167efb  nop     dword ptr [rax+rax+00h]
0x140167f00  and     eax, 0FFFFFFFCh
0x140167f03  cmp     [rdi+2B0h], eax
0x140167f09  jnz     short loc_140167F33
0x140167f0b  cmp     [rdi+0A0h], esi
0x140167f11  jl      short loc_140167F33
0x140167f13  mov     rdx, [rsp+1C0h+var_188]
0x140167f18  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140167f1f  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140167f24  mov     al, 1
0x140167f26  mov     rdi, [rsp+1C0h+var_30]
0x140167f2e  jmp     loc_140167EA6
0x140167f33  mov     rax, [r14]
0x140167f36  cmp     [rax+1D8h], rsi
0x140167f3d  jz      short loc_140167F53
0x140167f3f  cmp     [rax+1E8h], esi
0x140167f45  jz      short loc_140167F53
0x140167f47  cmp     [rax+1ECh], esi
0x140167f4d  jz      loc_1401682C8
0x140167f53  xorps   xmm0, xmm0
0x140167f56  mov     [rsp+1C0h+var_38], r13
0x140167f5e  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140167f65  lea     rdx, [rsp+1C0h+var_150]
0x140167f6a  lea     rcx, [rsp+1C0h+var_150]
0x140167f6f  movups  [rsp+1C0h+var_150], xmm0
0x140167f74  movups  [rbp+0C0h+var_140], xmm0
0x140167f78  call    cs:__imp_PushThreadGuardedObject
0x140167f7f  nop     dword ptr [rax+rax+00h]
0x140167f84  xorps   xmm0, xmm0
0x140167f87  mov     [rbp+0C0h+var_130], rsi
0x140167f8b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140167f92  lea     rdx, [rsp+1C0h+var_178]
0x140167f97  lea     rcx, [rsp+1C0h+var_178]
0x140167f9c  movups  [rsp+1C0h+var_178], xmm0
0x140167fa1  movups  [rsp+1C0h+var_168], xmm0
0x140167fa6  call    cs:__imp_PushThreadGuardedObject
0x140167fad  nop     dword ptr [rax+rax+00h]
0x140167fb2  mov     rax, [r14]
0x140167fb5  mov     r13, [r14+10h]
0x140167fb9  mov     [rsp+1C0h+var_158], rsi
0x140167fbe  test    dword ptr [rax+24h], 200h
0x140167fc5  jz      loc_1401681D3
0x140167fcb  mov     [rsp+1C0h+var_190], sil
0x140167fd0  call    cs:__imp_GreGetLockCount
0x140167fd7  nop     dword ptr [rax+rax+00h]
0x140167fdc  test    eax, eax
0x140167fde  jz      loc_1401682A6
0x140167fe4  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140167feb  nop     dword ptr [rax+rax+00h]
0x140167ff0  mov     rdx, rax
0x140167ff3  lea     rcx, [rsp+1C0h+var_180]
0x140167ff8  call    ??0?$SEMOBJSHARED@$02@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<3>::SEMOBJSHARED<3>(Gre::Base::SESSION_GLOBALS &)
0x140167ffd  mov     rcx, [r14]
0x140168000  call    cs:__imp_?vSetRendering@DC@@QEAAXXZ; DC::vSetRendering(void)
0x140168007  nop     dword ptr [rax+rax+00h]
0x14016800c  mov     esi, [rdi+38h]
0x14016800f  lea     rcx, [rbp+0C0h+var_120]; this
0x140168013  mov     edi, [rdi+3Ch]
0x140168016  mov     rdx, r14; struct XDCOBJ *
0x140168019  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x14016801e  lea     rcx, [rbp+0C0h+var_B0]
0x140168022  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x140168029  nop     dword ptr [rax+rax+00h]
0x14016802e  xor     r9d, r9d; unsigned int
0x140168031  mov     [rsp+1C0h+var_198], 0; unsigned __int16 *
0x14016803a  mov     r8d, edi; int
0x14016803d  mov     [rsp+1C0h+var_1A0], 0; struct _LUID *
0x140168046  mov     edx, esi; int
0x140168048  lea     rcx, [rbp+0C0h+var_120]; this
0x14016804c  call    ?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z; GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)
0x140168051  mov     rsi, rax
0x140168054  mov     rax, [r14]
0x140168057  test    rsi, rsi
0x14016805a  jz      loc_1401682F5
0x140168060  mov     rax, [rax+1F0h]
0x140168067  mov     rdi, [rax]
0x14016806a  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140168071  nop     dword ptr [rax+rax+00h]
0x140168076  mov     r9d, 1
0x14016807c  mov     r8b, 5
0x14016807f  mov     rcx, rax
0x140168082  mov     rdx, rdi
0x140168085  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14016808c  nop     dword ptr [rax+rax+00h]
0x140168091  mov     [rbp+0C0h+var_130], rax
0x140168095  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14016809c  nop     dword ptr [rax+rax+00h]
0x1401680a1  mov     r9d, 1
0x1401680a7  mov     r8b, 5
0x1401680aa  mov     rcx, rax
0x1401680ad  mov     rdx, rsi
0x1401680b0  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1401680b7  nop     dword ptr [rax+rax+00h]
0x1401680bc  lea     rcx, [rbp+0C0h+var_B0]
0x1401680c0  mov     [rsp+1C0h+var_158], rax
0x1401680c5  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x1401680cc  nop     dword ptr [rax+rax+00h]
0x1401680d1  lea     rcx, [rbp+0C0h+var_120]; this
0x1401680d5  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x1401680da  mov     rdx, [rsp+1C0h+var_180]
0x1401680df  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401680e6  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1401680eb  cmp     [rsp+1C0h+var_190], 0
0x1401680f0  jz      short loc_1401680FA
0x1401680f2  mov     rcx, r13
0x1401680f5  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x1401680fa  mov     rax, [rbp+0C0h+var_130]
0x1401680fe  mov     rcx, [rax]
0x140168101  mov     rax, [rsp+1C0h+var_158]
0x140168106  mov     [rbx], rcx
0x140168109  mov     rcx, [rax]
0x14016810c  mov     [r12], rcx
0x140168110  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140168117  nop     dword ptr [rax+rax+00h]
0x14016811c  mov     rdx, [rbp+0C0h+var_130]
0x140168120  mov     rcx, rax
0x140168123  call    cs:__imp_INC_SHARE_REF_CNT
0x14016812a  nop     dword ptr [rax+rax+00h]
0x14016812f  mov     rax, [r14]
0x140168132  test    dword ptr [rax+24h], 4000h
0x140168139  jnz     loc_140168366
0x14016813f  mov     rcx, [r14]
0x140168142  mov     rax, [rbx]
0x140168145  mov     [rcx+1F8h], rax
0x14016814c  mov     rdx, [rsp+1C0h+var_158]; struct SURFACE *
0x140168151  mov     rcx, [r14]; this
0x140168154  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x140168159  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140168160  nop     dword ptr [rax+rax+00h]
0x140168165  mov     rdx, [rsp+1C0h+var_158]
0x14016816a  mov     rcx, rax
0x14016816d  call    cs:__imp_INC_SHARE_REF_CNT
0x140168174  nop     dword ptr [rax+rax+00h]
0x140168179  test    r15, r15
0x14016817c  jz      short loc_140168197
0x14016817e  mov     rax, [r14]
0x140168181  mov     ecx, [rax+24h]
0x140168184  and     ecx, 0E0h
0x14016818a  mov     [r15], ecx
0x14016818d  mov     rax, [r14]
0x140168190  and     dword ptr [rax+24h], 0FFFFFF1Fh
0x140168197  mov     rcx, r13
0x14016819a  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x14016819f  lea     rcx, [rsp+1C0h+var_178]; this
0x1401681a4  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x1401681a9  lea     rcx, [rsp+1C0h+var_150]; this
0x1401681ae  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x1401681b3  mov     rdx, [rsp+1C0h+var_188]
0x1401681b8  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401681bf  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1401681c4  mov     r13, [rsp+1C0h+var_38]
0x1401681cc  mov     al, 1
0x1401681ce  jmp     loc_140167F26
0x1401681d3  mov     esi, [rdi+38h]
0x1401681d6  lea     rcx, [rbp+0C0h+var_120]; this
0x1401681da  mov     edi, [rdi+3Ch]
0x1401681dd  mov     rdx, r14; struct XDCOBJ *
0x1401681e0  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x1401681e5  lea     rcx, [rbp+0C0h+var_B0]
0x1401681e9  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x1401681f0  nop     dword ptr [rax+rax+00h]
0x1401681f5  xor     r9d, r9d; unsigned int
0x1401681f8  mov     [rsp+1C0h+var_198], 0; unsigned __int16 *
0x140168201  mov     r8d, edi; int
0x140168204  mov     [rsp+1C0h+var_1A0], 0; struct _LUID *
0x14016820d  mov     edx, esi; int
0x14016820f  lea     rcx, [rbp+0C0h+var_120]; this
0x140168213  call    ?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z; GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)
0x140168218  mov     rsi, rax
0x14016821b  test    rax, rax
0x14016821e  jz      loc_140168387
0x140168224  mov     rax, [r14]
0x140168227  mov     rcx, [rax+1F0h]
0x14016822e  mov     rdi, [rcx]
0x140168231  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140168238  nop     dword ptr [rax+rax+00h]
0x14016823d  mov     r9d, 1
0x140168243  mov     r8b, 5
0x140168246  mov     rcx, rax
0x140168249  mov     rdx, rdi
0x14016824c  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140168253  nop     dword ptr [rax+rax+00h]
0x140168258  mov     [rbp+0C0h+var_130], rax
0x14016825c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140168263  nop     dword ptr [rax+rax+00h]
0x140168268  mov     r9d, 1
0x14016826e  mov     r8b, 5
0x140168271  mov     rcx, rax
0x140168274  mov     rdx, rsi
0x140168277  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14016827e  nop     dword ptr [rax+rax+00h]
0x140168283  lea     rcx, [rbp+0C0h+var_B0]
0x140168287  mov     [rsp+1C0h+var_158], rax
0x14016828c  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140168293  nop     dword ptr [rax+rax+00h]
0x140168298  lea     rcx, [rbp+0C0h+var_120]; this
0x14016829c  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x1401682a1  jmp     loc_1401680FA
0x1401682a6  mov     rcx, r13
0x1401682a9  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x1401682ae  test    al, al
0x1401682b0  jnz     loc_140167FE4
0x1401682b6  mov     rcx, r13
0x1401682b9  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x1401682be  mov     [rsp+1C0h+var_190], 1
0x1401682c3  jmp     loc_140167FE4
0x1401682c8  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401682cf  nop     dword ptr [rax+rax+00h]
0x1401682d4  test    rax, rax
0x1401682d7  jz      short loc_1401682E0
0x1401682d9  cmp     [rax], rsi
0x1401682dc  cmovz   rax, rsi
0x1401682e0  mov     rcx, [r14]
0x1401682e3  cmp     rax, [rcx+1E0h]
0x1401682ea  jnz     loc_140167F53
0x1401682f0  jmp     loc_140167F13
0x1401682f5  mov     rcx, rax; this
0x1401682f8  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x1401682fd  cmp     [rsp+1C0h+var_190], 0
0x140168302  jnz     loc_1401683A2
0x140168308  lea     rcx, [rbp+0C0h+var_B0]
0x14016830c  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140168313  nop     dword ptr [rax+rax+00h]
0x140168318  lea     rcx, [rbp+0C0h+var_120]; this
0x14016831c  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140168321  mov     rdx, [rsp+1C0h+var_180]
0x140168326  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14016832d  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140168332  lea     rcx, [rsp+1C0h+var_178]; this
0x140168337  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14016833c  lea     rcx, [rsp+1C0h+var_150]; this
0x140168341  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140168346  mov     rdx, [rsp+1C0h+var_188]
0x14016834b  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140168352  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140168357  mov     r13, [rsp+1C0h+var_38]
0x14016835f  xor     al, al
0x140168361  jmp     loc_140167F26
0x140168366  mov     rcx, [rbp+0C0h+var_130]; this
0x14016836a  call    ?bRedirectionBitmap@SURFACE@@QEAAHXZ; SURFACE::bRedirectionBitmap(void)
0x14016836f  test    eax, eax
0x140168371  jz      loc_14016813F
0x140168377  mov     rax, [rsp+1C0h+var_158]
  ... truncated ...
```
