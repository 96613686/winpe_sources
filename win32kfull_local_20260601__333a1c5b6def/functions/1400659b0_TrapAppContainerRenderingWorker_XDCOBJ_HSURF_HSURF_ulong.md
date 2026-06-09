# TrapAppContainerRenderingWorker(XDCOBJ &,HSURF__ * &,HSURF__ * &,ulong *)

- ea: `0x1400659b0`
- end: `0x140065f2f`
- name: `?TrapAppContainerRenderingWorker@@YA_NAEAVXDCOBJ@@AEAPEAUHSURF__@@1PEAK@Z`
- size: `1407`
- prototype: `bool __fastcall(struct XDCOBJ *, HSURF *, HSURF *, unsigned int *)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140065000`
- `0x140065990`
- `0x14009bf24`

## callees

- `0x14005b938`
- `0x14005db98`
- `0x1400659b0`
- `0x140067320`
- `0x1400684f8`
- `0x140099c84`
- `0x14009a40c`
- `0x1400a538c`
- `0x1400a9c94`
- `0x1400acb4c`
- `0x1400acc04`
- `0x140113818`
- `0x1401150d0`
- `0x14011ea9c`
- `0x14011eb74`
- `0x14011ec90`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140065a74`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140065a74`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140065e48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140065e48`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400659f8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400659f8`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x1400659e8`
- `win32kbase!UserIsCurrentProcessImmersiveAppContainer` at `0x1400659e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065a4c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065b64`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065bea`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065c15`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065c90`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065cd9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065db1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065ddc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065a4c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065b64`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065bea`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065c15`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065c90`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065cd9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065db1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140065ddc`
- `win32kbase!HmgShareLock` at `0x140065c05`
- `win32kbase!HmgShareLock` at `0x140065c30`
- `win32kbase!HmgShareLock` at `0x140065dcc`
- `win32kbase!HmgShareLock` at `0x140065df7`
- `win32kbase!HmgShareLock` at `0x140065c05`
- `win32kbase!HmgShareLock` at `0x140065c30`
- `win32kbase!HmgShareLock` at `0x140065dcc`
- `win32kbase!HmgShareLock` at `0x140065df7`
- `win32kbase!PushThreadGuardedObject` at `0x140065af8`
- `win32kbase!PushThreadGuardedObject` at `0x140065b26`
- `win32kbase!PushThreadGuardedObject` at `0x140065af8`
- `win32kbase!PushThreadGuardedObject` at `0x140065b26`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140065a98`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140065c5f`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140065d38`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140065ea6`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140065ecb`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140065ca3`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140065ced`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140065ca3`
- `win32kbase!INC_SHARE_REF_CNT` at `0x140065ced`
- `win32kbase!GreGetLockCount` at `0x140065b50`
- `win32kbase!GreGetLockCount` at `0x140065b50`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065b80`
- `win32kbase!?vSetRendering@DC@@QEAAXXZ` at `0x140065b80`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065ba2`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065d69`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065ba2`
- `win32kbase!??0ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065d69`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065c45`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065e0c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065e8c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065f0b`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065c45`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065e0c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065e8c`
- `win32kbase!??1ThreadRestrictNewHandlesRegion@@QEAA@XZ` at `0x140065f0b`

## pseudocode

```c
char __fastcall TrapAppContainerRenderingWorker(struct XDCOBJ *a1, HSURF *a2, HSURF *a3, unsigned int *a4)
{
  __int64 v8; // rcx
  Gre::Base **CurrentThreadWin32Thread; // rax
  Gre::Base *v10; // rcx
  struct Gre::Base::SESSION_GLOBALS *v12; // rax
  _DWORD *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r13
  Gre::Base *v17; // rcx
  struct Gre::Base::SESSION_GLOBALS *v18; // rax
  int v19; // esi
  int v20; // edi
  Gre::Base *v21; // rcx
  HBITMAP CompatibleBitmap; // rsi
  __int64 v23; // rdi
  struct Gre::Base::SESSION_GLOBALS *v24; // rax
  __int64 v25; // r8
  Gre::Base *v26; // rcx
  struct Gre::Base::SESSION_GLOBALS *v27; // rax
  __int64 v28; // r8
  struct SURFACE *v29; // rax
  HSURF v30; // rcx
  struct Gre::Base::SESSION_GLOBALS *v31; // rax
  Gre::Base *v32; // rcx
  struct Gre::Base::SESSION_GLOBALS *v33; // rax
  int v34; // esi
  int v35; // edi
  HBITMAP v36; // rsi
  Gre::Base *v37; // rcx
  __int64 v38; // rdi
  struct Gre::Base::SESSION_GLOBALS *v39; // rax
  __int64 v40; // r8
  Gre::Base *v41; // rcx
  struct Gre::Base::SESSION_GLOBALS *v42; // rax
  __int64 v43; // r8
  _QWORD *CurrentProcessWin32Process; // rax
  char v45; // [rsp+30h] [rbp-D0h]
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v48[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct SURFACE *v49; // [rsp+68h] [rbp-98h]
  _OWORD v50[2]; // [rsp+70h] [rbp-90h] BYREF
  SURFACE *v51; // [rsp+90h] [rbp-70h]
  _BYTE v52[112]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v53[96]; // [rsp+110h] [rbp+10h] BYREF

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
  SEMOBJSHARED<1>::SEMOBJSHARED<1>(&v46, v12);
  v13 = *(_DWORD **)(*(_QWORD *)a1 + 496LL);
  if ( !v13 || v13[168] == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) && (int)v13[36] >= 0 )
    goto LABEL_10;
  v14 = *(_QWORD *)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 472LL) && *(_DWORD *)(v14 + 488) && !*(_DWORD *)(v14 + 492) )
  {
    CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process();
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
      CurrentProcessWin32Process = 0;
    if ( CurrentProcessWin32Process == *(_QWORD **)(*(_QWORD *)a1 + 480LL) )
    {
LABEL_10:
      GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v46);
      return 1;
    }
  }
  memset(v50, 0, sizeof(v50));
  PushThreadGuardedObject(
    v50,
    v50,
    UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
  v51 = 0;
  memset(v48, 0, sizeof(v48));
  PushThreadGuardedObject(
    v48,
    v48,
    UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
  v15 = *(_QWORD *)a1;
  v16 = *((_QWORD *)a1 + 2);
  v49 = 0;
  if ( (*(_DWORD *)(v15 + 36) & 0x200) != 0 )
  {
    v45 = 0;
    if ( !(unsigned int)GreGetLockCount()
      && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v16) )
    {
      GreAcquireSemaphore<2,>(v16);
      v45 = 1;
    }
    v18 = Gre::Base::Globals(v17);
    SEMOBJSHARED<3>::SEMOBJSHARED<3>(&v47, v18);
    DC::vSetRendering(*(DC **)a1);
    v19 = v13[14];
    v20 = v13[15];
    OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v52, a1);
    ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
    CompatibleBitmap = GrepCreateCompatibleBitmap((struct OPTAPIDCOBJ *)v52, v19, v20, 0, 0, 0);
    if ( CompatibleBitmap )
    {
      v23 = **(_QWORD **)(*(_QWORD *)a1 + 496LL);
      v24 = Gre::Base::Globals(v21);
      LOBYTE(v25) = 5;
      v51 = (SURFACE *)HmgShareLock(v24, v23, v25, 1);
      v27 = Gre::Base::Globals(v26);
      LOBYTE(v28) = 5;
      v49 = (struct SURFACE *)HmgShareLock(v27, CompatibleBitmap, v28, 1);
      ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
      OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v52);
      GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v47);
      if ( v45 )
        GreReleaseSemaphoreShared<2,>(v16);
      goto LABEL_19;
    }
    DC::vClearRendering(*(DC **)a1);
    if ( v45 )
      GreReleaseSemaphoreShared<2,>(v16);
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v52);
    GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v47);
LABEL_35:
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v48);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v50);
    GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v46);
    return 0;
  }
  v34 = v13[14];
  v35 = v13[15];
  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)v52, a1);
  ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
  v36 = GrepCreateCompatibleBitmap((struct OPTAPIDCOBJ *)v52, v34, v35, 0, 0, 0);
  if ( !v36 )
  {
    ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v52);
    goto LABEL_35;
  }
  v37 = *(Gre::Base **)(*(_QWORD *)a1 + 496LL);
  v38 = *(_QWORD *)v37;
  v39 = Gre::Base::Globals(v37);
  LOBYTE(v40) = 5;
  v51 = (SURFACE *)HmgShareLock(v39, v38, v40, 1);
  v42 = Gre::Base::Globals(v41);
  LOBYTE(v43) = 5;
  v49 = (struct SURFACE *)HmgShareLock(v42, v36, v43, 1);
  ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion((ThreadRestrictNewHandlesRegion *)v53);
  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)v52);
LABEL_19:
  v29 = v49;
  *a2 = *(HSURF *)v51;
  v30 = *(HSURF *)v29;
  *a3 = *(HSURF *)v29;
  v31 = Gre::Base::Globals((Gre::Base *)v30);
  INC_SHARE_REF_CNT(v31, v51);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0x4000) != 0 && (unsigned int)SURFACE::bRedirectionBitmap(v51) )
    ++*((_DWORD *)v49 + 89);
  *(_QWORD *)(*(_QWORD *)a1 + 504LL) = *a2;
  DC::pSurface(*(DC **)a1, v49);
  v33 = Gre::Base::Globals(v32);
  INC_SHARE_REF_CNT(v33, v49);
  if ( a4 )
  {
    *a4 = *(_DWORD *)(*(_QWORD *)a1 + 36LL) & 0xE0;
    *(_DWORD *)(*(_QWORD *)a1 + 36LL) &= 0xFFFFFF1F;
  }
  GreAcquireSemaphoreShared<1,>(v16);
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v48);
  SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v50);
  GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v46);
  return 1;
}

```

## disassembly

```asm
0x1400659b0  push    rbp
0x1400659b2  push    rbx
0x1400659b3  push    rsi
0x1400659b4  push    r12
0x1400659b6  push    r14
0x1400659b8  push    r15
0x1400659ba  lea     rbp, [rsp-98h]
0x1400659c2  sub     rsp, 198h
0x1400659c9  mov     rax, cs:__security_cookie
0x1400659d0  xor     rax, rsp
0x1400659d3  mov     [rbp+0C0h+var_50], rax
0x1400659d7  xor     esi, esi
0x1400659d9  mov     r15, r9
0x1400659dc  mov     [rdx], rsi
0x1400659df  mov     r12, r8
0x1400659e2  mov     rbx, rdx
0x1400659e5  mov     r14, rcx
0x1400659e8  call    cs:__imp_UserIsCurrentProcessImmersiveAppContainer
0x1400659ef  nop     dword ptr [rax+rax+00h]
0x1400659f4  test    eax, eax
0x1400659f6  jz      short loc_140065A24
0x1400659f8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400659ff  nop     dword ptr [rax+rax+00h]
0x140065a04  test    rax, rax
0x140065a07  jz      short loc_140065A44
0x140065a09  mov     rcx, [rax]
0x140065a0c  test    rcx, rcx
0x140065a0f  jz      short loc_140065A44
0x140065a11  lea     rax, [rcx+8]
0x140065a15  test    rax, rax
0x140065a18  jz      short loc_140065A44
0x140065a1a  mov     eax, [rax+150h]
0x140065a20  test    al, 4
0x140065a22  jz      short loc_140065A44
0x140065a24  mov     al, 1
0x140065a26  mov     rcx, [rbp+0C0h+var_50]
0x140065a2a  xor     rcx, rsp; StackCookie
0x140065a2d  call    __security_check_cookie
0x140065a32  add     rsp, 198h
0x140065a39  pop     r15
0x140065a3b  pop     r14
0x140065a3d  pop     r12
0x140065a3f  pop     rsi
0x140065a40  pop     rbx
0x140065a41  pop     rbp
0x140065a42  retn
0x140065a44  mov     [rsp+1C0h+var_30], rdi
0x140065a4c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065a53  nop     dword ptr [rax+rax+00h]
0x140065a58  mov     rdx, rax
0x140065a5b  lea     rcx, [rsp+1C0h+var_188]
0x140065a60  call    ??0?$SEMOBJSHARED@$00@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<1>::SEMOBJSHARED<1>(Gre::Base::SESSION_GLOBALS &)
0x140065a65  mov     rax, [r14]
0x140065a68  mov     rdi, [rax+1F0h]
0x140065a6f  test    rdi, rdi
0x140065a72  jz      short loc_140065A93
0x140065a74  call    cs:__imp_PsGetCurrentProcessId
0x140065a7b  nop     dword ptr [rax+rax+00h]
0x140065a80  and     eax, 0FFFFFFFCh
0x140065a83  cmp     [rdi+2A0h], eax
0x140065a89  jnz     short loc_140065AB3
0x140065a8b  cmp     [rdi+90h], esi
0x140065a91  jl      short loc_140065AB3
0x140065a93  mov     rdx, [rsp+1C0h+var_188]
0x140065a98  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065a9f  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140065aa4  mov     al, 1
0x140065aa6  mov     rdi, [rsp+1C0h+var_30]
0x140065aae  jmp     loc_140065A26
0x140065ab3  mov     rax, [r14]
0x140065ab6  cmp     [rax+1D8h], rsi
0x140065abd  jz      short loc_140065AD3
0x140065abf  cmp     [rax+1E8h], esi
0x140065ac5  jz      short loc_140065AD3
0x140065ac7  cmp     [rax+1ECh], esi
0x140065acd  jz      loc_140065E48
0x140065ad3  xorps   xmm0, xmm0
0x140065ad6  mov     [rsp+1C0h+var_38], r13
0x140065ade  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140065ae5  lea     rdx, [rsp+1C0h+var_150]
0x140065aea  lea     rcx, [rsp+1C0h+var_150]
0x140065aef  movups  [rsp+1C0h+var_150], xmm0
0x140065af4  movups  [rbp+0C0h+var_140], xmm0
0x140065af8  call    cs:__imp_PushThreadGuardedObject
0x140065aff  nop     dword ptr [rax+rax+00h]
0x140065b04  xorps   xmm0, xmm0
0x140065b07  mov     [rbp+0C0h+var_130], rsi
0x140065b0b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140065b12  lea     rdx, [rsp+1C0h+var_178]
0x140065b17  lea     rcx, [rsp+1C0h+var_178]
0x140065b1c  movups  [rsp+1C0h+var_178], xmm0
0x140065b21  movups  [rsp+1C0h+var_168], xmm0
0x140065b26  call    cs:__imp_PushThreadGuardedObject
0x140065b2d  nop     dword ptr [rax+rax+00h]
0x140065b32  mov     rax, [r14]
0x140065b35  mov     r13, [r14+10h]
0x140065b39  mov     [rsp+1C0h+var_158], rsi
0x140065b3e  test    dword ptr [rax+24h], 200h
0x140065b45  jz      loc_140065D53
0x140065b4b  mov     [rsp+1C0h+var_190], sil
0x140065b50  call    cs:__imp_GreGetLockCount
0x140065b57  nop     dword ptr [rax+rax+00h]
0x140065b5c  test    eax, eax
0x140065b5e  jz      loc_140065E26
0x140065b64  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065b6b  nop     dword ptr [rax+rax+00h]
0x140065b70  mov     rdx, rax
0x140065b73  lea     rcx, [rsp+1C0h+var_180]
0x140065b78  call    ??0?$SEMOBJSHARED@$02@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<3>::SEMOBJSHARED<3>(Gre::Base::SESSION_GLOBALS &)
0x140065b7d  mov     rcx, [r14]
0x140065b80  call    cs:__imp_?vSetRendering@DC@@QEAAXXZ; DC::vSetRendering(void)
0x140065b87  nop     dword ptr [rax+rax+00h]
0x140065b8c  mov     esi, [rdi+38h]
0x140065b8f  lea     rcx, [rbp+0C0h+var_120]; this
0x140065b93  mov     edi, [rdi+3Ch]
0x140065b96  mov     rdx, r14; struct XDCOBJ *
0x140065b99  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x140065b9e  lea     rcx, [rbp+0C0h+var_B0]
0x140065ba2  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x140065ba9  nop     dword ptr [rax+rax+00h]
0x140065bae  xor     r9d, r9d; unsigned int
0x140065bb1  mov     [rsp+1C0h+var_198], 0; unsigned __int16 *
0x140065bba  mov     r8d, edi; int
0x140065bbd  mov     [rsp+1C0h+var_1A0], 0; struct _LUID *
0x140065bc6  mov     edx, esi; int
0x140065bc8  lea     rcx, [rbp+0C0h+var_120]; this
0x140065bcc  call    ?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z; GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)
0x140065bd1  mov     rsi, rax
0x140065bd4  mov     rax, [r14]
0x140065bd7  test    rsi, rsi
0x140065bda  jz      loc_140065E75
0x140065be0  mov     rax, [rax+1F0h]
0x140065be7  mov     rdi, [rax]
0x140065bea  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065bf1  nop     dword ptr [rax+rax+00h]
0x140065bf6  mov     r9d, 1
0x140065bfc  mov     r8b, 5
0x140065bff  mov     rcx, rax
0x140065c02  mov     rdx, rdi
0x140065c05  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140065c0c  nop     dword ptr [rax+rax+00h]
0x140065c11  mov     [rbp+0C0h+var_130], rax
0x140065c15  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065c1c  nop     dword ptr [rax+rax+00h]
0x140065c21  mov     r9d, 1
0x140065c27  mov     r8b, 5
0x140065c2a  mov     rcx, rax
0x140065c2d  mov     rdx, rsi
0x140065c30  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140065c37  nop     dword ptr [rax+rax+00h]
0x140065c3c  lea     rcx, [rbp+0C0h+var_B0]
0x140065c40  mov     [rsp+1C0h+var_158], rax
0x140065c45  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140065c4c  nop     dword ptr [rax+rax+00h]
0x140065c51  lea     rcx, [rbp+0C0h+var_120]; this
0x140065c55  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140065c5a  mov     rdx, [rsp+1C0h+var_180]
0x140065c5f  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065c66  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140065c6b  cmp     [rsp+1C0h+var_190], 0
0x140065c70  jz      short loc_140065C7A
0x140065c72  mov     rcx, r13
0x140065c75  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140065c7a  mov     rax, [rbp+0C0h+var_130]
0x140065c7e  mov     rcx, [rax]
0x140065c81  mov     rax, [rsp+1C0h+var_158]
0x140065c86  mov     [rbx], rcx
0x140065c89  mov     rcx, [rax]
0x140065c8c  mov     [r12], rcx
0x140065c90  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065c97  nop     dword ptr [rax+rax+00h]
0x140065c9c  mov     rdx, [rbp+0C0h+var_130]
0x140065ca0  mov     rcx, rax
0x140065ca3  call    cs:__imp_INC_SHARE_REF_CNT
0x140065caa  nop     dword ptr [rax+rax+00h]
0x140065caf  mov     rax, [r14]
0x140065cb2  test    dword ptr [rax+24h], 4000h
0x140065cb9  jnz     loc_140065EE6
0x140065cbf  mov     rcx, [r14]
0x140065cc2  mov     rax, [rbx]
0x140065cc5  mov     [rcx+1F8h], rax
0x140065ccc  mov     rdx, [rsp+1C0h+var_158]; struct SURFACE *
0x140065cd1  mov     rcx, [r14]; this
0x140065cd4  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x140065cd9  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065ce0  nop     dword ptr [rax+rax+00h]
0x140065ce5  mov     rdx, [rsp+1C0h+var_158]
0x140065cea  mov     rcx, rax
0x140065ced  call    cs:__imp_INC_SHARE_REF_CNT
0x140065cf4  nop     dword ptr [rax+rax+00h]
0x140065cf9  test    r15, r15
0x140065cfc  jz      short loc_140065D17
0x140065cfe  mov     rax, [r14]
0x140065d01  mov     ecx, [rax+24h]
0x140065d04  and     ecx, 0E0h
0x140065d0a  mov     [r15], ecx
0x140065d0d  mov     rax, [r14]
0x140065d10  and     dword ptr [rax+24h], 0FFFFFF1Fh
0x140065d17  mov     rcx, r13
0x140065d1a  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140065d1f  lea     rcx, [rsp+1C0h+var_178]; this
0x140065d24  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140065d29  lea     rcx, [rsp+1C0h+var_150]; this
0x140065d2e  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140065d33  mov     rdx, [rsp+1C0h+var_188]
0x140065d38  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065d3f  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140065d44  mov     r13, [rsp+1C0h+var_38]
0x140065d4c  mov     al, 1
0x140065d4e  jmp     loc_140065AA6
0x140065d53  mov     esi, [rdi+38h]
0x140065d56  lea     rcx, [rbp+0C0h+var_120]; this
0x140065d5a  mov     edi, [rdi+3Ch]
0x140065d5d  mov     rdx, r14; struct XDCOBJ *
0x140065d60  call    ??0OPTAPIDCOBJ@@QEAA@AEAVXDCOBJ@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(XDCOBJ &)
0x140065d65  lea     rcx, [rbp+0C0h+var_B0]
0x140065d69  call    cs:__imp_??0ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::ThreadRestrictNewHandlesRegion(void)
0x140065d70  nop     dword ptr [rax+rax+00h]
0x140065d75  xor     r9d, r9d; unsigned int
0x140065d78  mov     [rsp+1C0h+var_198], 0; unsigned __int16 *
0x140065d81  mov     r8d, edi; int
0x140065d84  mov     [rsp+1C0h+var_1A0], 0; struct _LUID *
0x140065d8d  mov     edx, esi; int
0x140065d8f  lea     rcx, [rbp+0C0h+var_120]; this
0x140065d93  call    ?GrepCreateCompatibleBitmap@@YAPEAUHBITMAP__@@AEAVOPTAPIDCOBJ@@HHKPEAU_LUID@@PEAG@Z; GrepCreateCompatibleBitmap(OPTAPIDCOBJ &,int,int,ulong,_LUID *,ushort *)
0x140065d98  mov     rsi, rax
0x140065d9b  test    rax, rax
0x140065d9e  jz      loc_140065F07
0x140065da4  mov     rax, [r14]
0x140065da7  mov     rcx, [rax+1F0h]
0x140065dae  mov     rdi, [rcx]
0x140065db1  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065db8  nop     dword ptr [rax+rax+00h]
0x140065dbd  mov     r9d, 1
0x140065dc3  mov     r8b, 5
0x140065dc6  mov     rcx, rax
0x140065dc9  mov     rdx, rdi
0x140065dcc  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140065dd3  nop     dword ptr [rax+rax+00h]
0x140065dd8  mov     [rbp+0C0h+var_130], rax
0x140065ddc  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140065de3  nop     dword ptr [rax+rax+00h]
0x140065de8  mov     r9d, 1
0x140065dee  mov     r8b, 5
0x140065df1  mov     rcx, rax
0x140065df4  mov     rdx, rsi
0x140065df7  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140065dfe  nop     dword ptr [rax+rax+00h]
0x140065e03  lea     rcx, [rbp+0C0h+var_B0]
0x140065e07  mov     [rsp+1C0h+var_158], rax
0x140065e0c  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140065e13  nop     dword ptr [rax+rax+00h]
0x140065e18  lea     rcx, [rbp+0C0h+var_120]; this
0x140065e1c  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140065e21  jmp     loc_140065C7A
0x140065e26  mov     rcx, r13
0x140065e29  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x140065e2e  test    al, al
0x140065e30  jnz     loc_140065B64
0x140065e36  mov     rcx, r13
0x140065e39  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x140065e3e  mov     [rsp+1C0h+var_190], 1
0x140065e43  jmp     loc_140065B64
0x140065e48  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140065e4f  nop     dword ptr [rax+rax+00h]
0x140065e54  test    rax, rax
0x140065e57  jz      short loc_140065E60
0x140065e59  cmp     [rax], rsi
0x140065e5c  cmovz   rax, rsi
0x140065e60  mov     rcx, [r14]
0x140065e63  cmp     rax, [rcx+1E0h]
0x140065e6a  jnz     loc_140065AD3
0x140065e70  jmp     loc_140065A93
0x140065e75  mov     rcx, rax; this
0x140065e78  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x140065e7d  cmp     [rsp+1C0h+var_190], 0
0x140065e82  jnz     loc_140065F22
0x140065e88  lea     rcx, [rbp+0C0h+var_B0]
0x140065e8c  call    cs:__imp_??1ThreadRestrictNewHandlesRegion@@QEAA@XZ; ThreadRestrictNewHandlesRegion::~ThreadRestrictNewHandlesRegion(void)
0x140065e93  nop     dword ptr [rax+rax+00h]
0x140065e98  lea     rcx, [rbp+0C0h+var_120]; this
0x140065e9c  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140065ea1  mov     rdx, [rsp+1C0h+var_180]
0x140065ea6  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065ead  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140065eb2  lea     rcx, [rsp+1C0h+var_178]; this
0x140065eb7  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140065ebc  lea     rcx, [rsp+1C0h+var_150]; this
0x140065ec1  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x140065ec6  mov     rdx, [rsp+1C0h+var_188]
0x140065ecb  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140065ed2  call    ??$GreReleaseSemaphoreCommon@$00P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<1,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140065ed7  mov     r13, [rsp+1C0h+var_38]
0x140065edf  xor     al, al
0x140065ee1  jmp     loc_140065AA6
0x140065ee6  mov     rcx, [rbp+0C0h+var_130]; this
0x140065eea  call    ?bRedirectionBitmap@SURFACE@@QEAAHXZ; SURFACE::bRedirectionBitmap(void)
0x140065eef  test    eax, eax
0x140065ef1  jz      loc_140065CBF
0x140065ef7  mov     rax, [rsp+1C0h+var_158]
  ... truncated ...
```
