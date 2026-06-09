# vSpComputeUnlockedRegion(_SPRITESTATE *)

- ea: `0x1401a3654`
- end: `0x1401a3a11`
- name: `?vSpComputeUnlockedRegion@@YAXPEAU_SPRITESTATE@@@Z`
- size: `957`
- prototype: `void __fastcall(struct _SPRITESTATE *)`
- caller_count: `6`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14006f758`
- `0x1401a3348`
- `0x1403080fc`
- `0x140309f6c`
- `0x14030a1fc`
- `0x14030c160`

## callees

- `0x1400943d4`
- `0x140097e80`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x14015e77c`
- `0x1401a3654`
- `0x1401a3ddc`
- `0x1401f30d4`
- `0x14028ba70`
- `0x140306564`
- `0x14030661c`
- `0x1403090a0`
- `0x1403384dc`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a368f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a38f8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a368f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401a38f8`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x1401a3811`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x1401a3811`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1401a37ec`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x1401a37ec`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3790`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a385e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a3790`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401a385e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3767`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3882`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3767`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1401a3882`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a38b1`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a3960`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a39e1`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a38b1`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a3960`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1401a39e1`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401a371f`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401a371f`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a3896`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a3945`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a39c6`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a3896`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a3945`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401a39c6`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1401a381d`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a38c5`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a3974`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a39f5`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a38c5`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a3974`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x1401a39f5`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x1401a383a`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x1401a383a`
- `WIN32K!W32GetSessionState` at `0x1401a36ae`
- `WIN32K!W32GetSessionState` at `0x1401a36ae`

## pseudocode

```c
void __fastcall vSpComputeUnlockedRegion(HDEV *a1)
{
  HDEV v1; // rbx
  struct Gre::Base::SESSION_GLOBALS *v3; // rax
  HDEV v4; // rcx
  struct Gre::Base::SESSION_GLOBALS *v5; // r12
  __int64 v6; // r15
  int v7; // r14d
  void *i; // rdx
  __int64 v9; // rbx
  __int64 GlobalLockName; // rax
  struct _GRETHREAD *v11; // rax
  bool v12; // zf
  void *v13; // rsi
  Gre::Base *v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v15; // rax
  __int64 j; // rsi
  __int64 k; // rbx
  REGION *v18; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  HDEV v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _RECTL v23; // [rsp+50h] [rbp-30h] BYREF
  struct _RECTL v24; // [rsp+60h] [rbp-20h] BYREF

  v1 = *a1;
  v23 = 0;
  v22[0] = v1;
  v3 = Gre::Base::Globals((Gre::Base *)a1);
  v4 = a1[130];
  v5 = v3;
  if ( v4 )
  {
    v20 = a1[130];
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v20);
    a1[130] = 0;
  }
  v6 = *(_QWORD *)(W32GetSessionState(v4) + 96);
  if ( *(_QWORD *)(v6 + 4816) || a1[131] || *((_DWORD *)v1 + 658) )
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v18);
    if ( v18 )
    {
      *(_QWORD *)&v23.left = 0;
      *(_QWORD *)&v23.right = **(_QWORD **)&PDEVOBJ::sizl((PDEVOBJ *)v22);
      RGNOBJ::vSet((RGNOBJ *)&v18, &v23);
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v20);
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v19);
      if ( !v20 || !v19 )
        goto LABEL_9;
      v24 = 0;
      v7 = 0;
      GreAcquireSemaphore<8,PDEVOBJ>(v1);
      for ( i = 0; ; i = v13 )
      {
        v13 = DxDdEnumLockedSurfaceRect(v1, i, &v24);
        if ( !v13 )
          break;
        RGNOBJ::vSet((RGNOBJ *)&v20, &v24);
        RGNOBJ::bCopy((RGNOBJ *)&v19, (struct RGNOBJ *)&v18);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v18, (struct RGNOBJ *)&v19, (struct RGNOBJ *)&v20, 4u) )
          v7 = 1;
        else
          RGNOBJ::vSet((RGNOBJ *)&v18);
      }
      GreReleaseSemaphoreExclusive<8,PDEVOBJ>(v1);
      v15 = Gre::Base::Globals(v14);
      SEMOBJ<33>::SEMOBJ<33>(&v21, v15);
      for ( j = *(_QWORD *)(v6 + 4816); j; j = *(_QWORD *)(j + 8) )
      {
        for ( k = *(_QWORD *)(j + 24); k; k = *(_QWORD *)(k + 160) )
        {
          UNDODESKTOPCOORD::UNDODESKTOPCOORD((UNDODESKTOPCOORD *)v22, (struct EWNDOBJ *)k, (struct _SPRITESTATE *)a1);
          if ( (*(_DWORD *)(k + 184) & 0x1000000) != 0 )
          {
            RGNOBJ::bCopy((RGNOBJ *)&v19, (struct RGNOBJ *)&v18);
            if ( RGNOBJ::bMerge((RGNOBJ *)&v18, (struct RGNOBJ *)&v19, (struct RGNOBJ *)(k + 56), 4u) )
              v7 = 1;
            else
              RGNOBJ::vSet((RGNOBJ *)&v18);
          }
          UNDODESKTOPCOORD::~UNDODESKTOPCOORD((UNDODESKTOPCOORD *)v22);
        }
      }
      if ( a1[131] )
      {
        v22[0] = a1[131];
        RGNOBJ::bCopy((RGNOBJ *)&v19, (struct RGNOBJ *)&v18);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v18, (struct RGNOBJ *)&v19, (struct RGNOBJ *)v22, 8u) )
          v7 = 1;
        else
          RGNOBJ::vSet((RGNOBJ *)&v18);
      }
      v9 = v21;
      if ( v21 )
      {
        GlobalLockName = GrepGetGlobalLockName(33);
        EtwTraceGreLockReleaseSemaphore(GlobalLockName, v9);
        v11 = GreGetCurrentThreadCrossSessionCheck();
        if ( v11 )
        {
          v12 = (*(_QWORD *)v11 & 0xFFFFFFFDFFFFFFFFuLL) == 0;
          *(_QWORD *)v11 &= ~0x200000000uLL;
          if ( v12 )
            GrepOnAllLocksReleased();
        }
        ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v9);
      }
      if ( v7 == 1 )
      {
        REGION::vStamp(v18);
        a1[130] = (HDEV)v18;
      }
      else
      {
LABEL_9:
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v18);
      }
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v19);
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v20);
    }
  }
  *((_DWORD *)a1 + 29) = 0;
  vSpComputeSpriteRanges(a1);
  ++*((_DWORD *)v5 + 1088);
}

```

## disassembly

```asm
0x1401a3654  mov     [rsp-28h+arg_8], rbx
0x1401a3659  mov     [rsp-28h+arg_10], rsi
0x1401a365e  push    rbp
0x1401a365f  push    rdi
0x1401a3660  push    r12
0x1401a3662  push    r14
0x1401a3664  push    r15
0x1401a3666  mov     rbp, rsp
0x1401a3669  sub     rsp, 80h
0x1401a3670  mov     rax, cs:__security_cookie
0x1401a3677  xor     rax, rsp
0x1401a367a  mov     [rbp+var_10], rax
0x1401a367e  mov     rbx, [rcx]
0x1401a3681  xorps   xmm0, xmm0
0x1401a3684  movups  [rbp+var_30], xmm0
0x1401a3688  mov     [rbp+var_40], rbx
0x1401a368c  mov     rdi, rcx
0x1401a368f  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401a3696  nop     dword ptr [rax+rax+00h]
0x1401a369b  mov     rcx, [rdi+410h]
0x1401a36a2  mov     r12, rax
0x1401a36a5  test    rcx, rcx
0x1401a36a8  jnz     loc_1401A3856
0x1401a36ae  call    cs:__imp_W32GetSessionState
0x1401a36b5  nop     dword ptr [rax+rax+00h]
0x1401a36ba  mov     r15, [rax+60h]
0x1401a36be  cmp     qword ptr [r15+12D0h], 0
0x1401a36c6  jnz     short loc_1401A371B
0x1401a36c8  cmp     qword ptr [rdi+418h], 0
0x1401a36d0  jnz     short loc_1401A371B
0x1401a36d2  cmp     dword ptr [rbx+0A48h], 0
0x1401a36d9  jnz     short loc_1401A371B
0x1401a36db  mov     rcx, rdi
0x1401a36de  mov     dword ptr [rdi+74h], 0
0x1401a36e5  call    ?vSpComputeSpriteRanges@@YAXPEAU_SPRITESTATE@@W4vSpComputeSpriteRangesOptions@@@Z; vSpComputeSpriteRanges(_SPRITESTATE *,vSpComputeSpriteRangesOptions)
0x1401a36ea  inc     dword ptr [r12+1100h]
0x1401a36f2  mov     rcx, [rbp+var_10]
0x1401a36f6  xor     rcx, rsp; StackCookie
0x1401a36f9  call    __security_check_cookie
0x1401a36fe  lea     r11, [rsp+80h+var_s0]
0x1401a3706  mov     rbx, [r11+38h]
0x1401a370a  mov     rsi, [r11+40h]
0x1401a370e  mov     rsp, r11
0x1401a3711  pop     r15
0x1401a3713  pop     r14
0x1401a3715  pop     r12
0x1401a3717  pop     rdi
0x1401a3718  pop     rbp
0x1401a3719  retn
0x1401a371b  lea     rcx, [rbp+var_60]
0x1401a371f  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1401a3726  nop     dword ptr [rax+rax+00h]
0x1401a372b  cmp     [rbp+var_60], 0
0x1401a3730  jz      short loc_1401A36DB
0x1401a3732  lea     rdx, [rbp+var_48]
0x1401a3736  mov     qword ptr [rbp+var_30], 0
0x1401a373e  lea     rcx, [rbp+var_40]; this
0x1401a3742  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x1401a3747  lea     rdx, [rbp+var_48]
0x1401a374b  mov     ecx, [rax]
0x1401a374d  mov     dword ptr [rbp+var_30+8], ecx
0x1401a3750  lea     rcx, [rbp+var_40]; this
0x1401a3754  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x1401a3759  lea     rdx, [rbp+var_30]
0x1401a375d  mov     ecx, [rax+4]
0x1401a3760  mov     dword ptr [rbp+var_30+0Ch], ecx
0x1401a3763  lea     rcx, [rbp+var_60]
0x1401a3767  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1401a376e  nop     dword ptr [rax+rax+00h]
0x1401a3773  lea     rcx, [rbp+var_50]; this
0x1401a3777  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1401a377c  lea     rcx, [rbp+var_58]; this
0x1401a3780  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x1401a3785  cmp     [rbp+var_50], 0
0x1401a378a  jnz     short loc_1401A37B3
0x1401a378c  lea     rcx, [rbp+var_60]
0x1401a3790  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401a3797  nop     dword ptr [rax+rax+00h]
0x1401a379c  lea     rcx, [rbp+var_58]; this
0x1401a37a0  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x1401a37a5  lea     rcx, [rbp+var_50]; this
0x1401a37a9  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x1401a37ae  jmp     loc_1401A36DB
0x1401a37b3  cmp     [rbp+var_58], 0
0x1401a37b8  jz      short loc_1401A378C
0x1401a37ba  xorps   xmm0, xmm0
0x1401a37bd  mov     rcx, rbx
0x1401a37c0  movups  xmmword ptr [rbp+var_20.left], xmm0
0x1401a37c4  xor     r14d, r14d
0x1401a37c7  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x1401a37cc  xor     edx, edx
0x1401a37ce  jmp     loc_1401A38DC
0x1401a37d3  mov     rbx, [rbp+var_48]
0x1401a37d7  test    rbx, rbx
0x1401a37da  jz      short loc_1401A382C
0x1401a37dc  mov     ecx, 21h ; '!'
0x1401a37e1  call    ?GrepGetGlobalLockName@@YAPEBGW4GreLockClass@@@Z; GrepGetGlobalLockName(GreLockClass)
0x1401a37e6  mov     rcx, rax
0x1401a37e9  mov     rdx, rbx
0x1401a37ec  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x1401a37f3  nop     dword ptr [rax+rax+00h]
0x1401a37f8  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1401a37fd  test    rax, rax
0x1401a3800  jz      short loc_1401A381D
0x1401a3802  mov     rcx, 0FFFFFFFDFFFFFFFFh
0x1401a380c  and     [rax], rcx
0x1401a380f  jnz     short loc_1401A381D
0x1401a3811  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x1401a3818  nop     dword ptr [rax+rax+00h]
0x1401a381d  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x1401a3824  mov     rcx, rbx
0x1401a3827  call    _guard_dispatch_icall
0x1401a382c  cmp     r14d, 1
0x1401a3830  jnz     loc_1401A378C
0x1401a3836  mov     rcx, [rbp+var_60]
0x1401a383a  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x1401a3841  nop     dword ptr [rax+rax+00h]
0x1401a3846  mov     rax, [rbp+var_60]
0x1401a384a  mov     [rdi+410h], rax
0x1401a3851  jmp     loc_1401A379C
0x1401a3856  mov     [rbp+var_50], rcx
0x1401a385a  lea     rcx, [rbp+var_50]
0x1401a385e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401a3865  nop     dword ptr [rax+rax+00h]
0x1401a386a  mov     qword ptr [rdi+410h], 0
0x1401a3875  jmp     loc_1401A36AE
0x1401a387a  lea     rdx, [rbp+var_20]
0x1401a387e  lea     rcx, [rbp+var_50]
0x1401a3882  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1401a3889  nop     dword ptr [rax+rax+00h]
0x1401a388e  lea     rdx, [rbp+var_60]
0x1401a3892  lea     rcx, [rbp+var_58]
0x1401a3896  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x1401a389d  nop     dword ptr [rax+rax+00h]
0x1401a38a2  mov     r9b, 4
0x1401a38a5  lea     r8, [rbp+var_50]
0x1401a38a9  lea     rdx, [rbp+var_58]
0x1401a38ad  lea     rcx, [rbp+var_60]
0x1401a38b1  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401a38b8  nop     dword ptr [rax+rax+00h]
0x1401a38bd  test    eax, eax
0x1401a38bf  jnz     short loc_1401A38D3
0x1401a38c1  lea     rcx, [rbp+var_60]
0x1401a38c5  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1401a38cc  nop     dword ptr [rax+rax+00h]
0x1401a38d1  jmp     short loc_1401A38D9
0x1401a38d3  mov     r14d, 1
0x1401a38d9  mov     rdx, rsi; void *
0x1401a38dc  lea     r8, [rbp+var_20]; struct _RECTL *
0x1401a38e0  mov     rcx, rbx; HDEV
0x1401a38e3  call    ?DxDdEnumLockedSurfaceRect@@YAPEAXPEAUHDEV__@@PEAXPEAU_RECTL@@@Z; DxDdEnumLockedSurfaceRect(HDEV__ *,void *,_RECTL *)
0x1401a38e8  mov     rsi, rax
0x1401a38eb  test    rax, rax
0x1401a38ee  jnz     short loc_1401A387A
0x1401a38f0  mov     rcx, rbx
0x1401a38f3  call    ??$GreReleaseSemaphoreExclusive@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreReleaseSemaphoreExclusive<8,PDEVOBJ>(PDEVOBJ)
0x1401a38f8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401a38ff  nop     dword ptr [rax+rax+00h]
0x1401a3904  mov     rdx, rax
0x1401a3907  lea     rcx, [rbp+var_48]
0x1401a390b  call    ??0?$SEMOBJ@$0CB@@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJ<33>::SEMOBJ<33>(Gre::Base::SESSION_GLOBALS &)
0x1401a3910  mov     rsi, [r15+12D0h]
0x1401a3917  jmp     loc_1401A39A1
0x1401a391c  mov     rbx, [rsi+18h]
0x1401a3920  jmp     short loc_1401A3998
0x1401a3922  mov     r8, rdi; struct _SPRITESTATE *
0x1401a3925  lea     rcx, [rbp+var_40]; this
0x1401a3929  mov     rdx, rbx; struct EWNDOBJ *
0x1401a392c  call    ??0UNDODESKTOPCOORD@@QEAA@PEAVEWNDOBJ@@PEAU_SPRITESTATE@@@Z; UNDODESKTOPCOORD::UNDODESKTOPCOORD(EWNDOBJ *,_SPRITESTATE *)
0x1401a3931  test    dword ptr [rbx+0B8h], 1000000h
0x1401a393b  jz      short loc_1401A3988
0x1401a393d  lea     rdx, [rbp+var_60]
0x1401a3941  lea     rcx, [rbp+var_58]
0x1401a3945  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x1401a394c  nop     dword ptr [rax+rax+00h]
0x1401a3951  lea     r8, [rbx+38h]
0x1401a3955  mov     r9b, 4
0x1401a3958  lea     rdx, [rbp+var_58]
0x1401a395c  lea     rcx, [rbp+var_60]
0x1401a3960  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401a3967  nop     dword ptr [rax+rax+00h]
0x1401a396c  test    eax, eax
0x1401a396e  jnz     short loc_1401A3982
0x1401a3970  lea     rcx, [rbp+var_60]
0x1401a3974  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1401a397b  nop     dword ptr [rax+rax+00h]
0x1401a3980  jmp     short loc_1401A3988
0x1401a3982  mov     r14d, 1
0x1401a3988  lea     rcx, [rbp+var_40]; this
0x1401a398c  call    ??1UNDODESKTOPCOORD@@QEAA@XZ; UNDODESKTOPCOORD::~UNDODESKTOPCOORD(void)
0x1401a3991  mov     rbx, [rbx+0A0h]
0x1401a3998  test    rbx, rbx
0x1401a399b  jnz     short loc_1401A3922
0x1401a399d  mov     rsi, [rsi+8]
0x1401a39a1  test    rsi, rsi
0x1401a39a4  jnz     loc_1401A391C
0x1401a39aa  mov     rax, [rdi+418h]
0x1401a39b1  test    rax, rax
0x1401a39b4  jz      loc_1401A37D3
0x1401a39ba  lea     rdx, [rbp+var_60]
0x1401a39be  mov     [rbp+var_40], rax
0x1401a39c2  lea     rcx, [rbp+var_58]
0x1401a39c6  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x1401a39cd  nop     dword ptr [rax+rax+00h]
0x1401a39d2  mov     r9b, 8
0x1401a39d5  lea     r8, [rbp+var_40]
0x1401a39d9  lea     rdx, [rbp+var_58]
0x1401a39dd  lea     rcx, [rbp+var_60]
0x1401a39e1  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x1401a39e8  nop     dword ptr [rax+rax+00h]
0x1401a39ed  test    eax, eax
0x1401a39ef  jnz     short loc_1401A3A06
0x1401a39f1  lea     rcx, [rbp+var_60]
0x1401a39f5  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x1401a39fc  nop     dword ptr [rax+rax+00h]
0x1401a3a01  jmp     loc_1401A37D3
0x1401a3a06  mov     r14d, 1
0x1401a3a0c  jmp     loc_1401A37D3
```
