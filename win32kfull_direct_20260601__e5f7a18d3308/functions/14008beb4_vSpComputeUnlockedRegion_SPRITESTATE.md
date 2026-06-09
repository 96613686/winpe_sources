# vSpComputeUnlockedRegion(_SPRITESTATE *)

- ea: `0x14008beb4`
- end: `0x14008c271`
- name: `?vSpComputeUnlockedRegion@@YAXPEAU_SPRITESTATE@@@Z`
- size: `957`
- prototype: `void __fastcall(struct _SPRITESTATE *)`
- caller_count: `6`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14008c480`
- `0x14009c448`
- `0x140309de4`
- `0x14030bc48`
- `0x14030bed8`
- `0x14030ddf0`

## callees

- `0x140077348`
- `0x140079b44`
- `0x14008beb4`
- `0x1400aa9e4`
- `0x1400ae480`
- `0x140119d14`
- `0x14014f2c8`
- `0x1401f7a24`
- `0x14028df60`
- `0x140308254`
- `0x14030830c`
- `0x14030ad88`
- `0x1403398ec`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008beef`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c158`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008beef`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c158`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14008c071`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14008c071`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14008c04c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14008c04c`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008bff0`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c0be`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008bff0`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14008c0be`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008bfc7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c0e2`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008bfc7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14008c0e2`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c111`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c1c0`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c241`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c111`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c1c0`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14008c241`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008bf7f`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14008bf7f`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c0f6`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c1a5`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c226`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c0f6`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c1a5`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x14008c226`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14008c07d`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c125`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c1d4`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c255`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c125`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c1d4`
- `win32kbase!?vSet@RGNOBJ@@QEAAXXZ` at `0x14008c255`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008c09a`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14008c09a`
- `WIN32K!W32GetSessionState` at `0x14008bf0e`
- `WIN32K!W32GetSessionState` at `0x14008bf0e`

## pseudocode

```c
void __fastcall vSpComputeUnlockedRegion(HDEV *a1)
{
  HDEV v1; // rbx
  struct Gre::Base::SESSION_GLOBALS *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  HDEV v7; // rcx
  struct Gre::Base::SESSION_GLOBALS *v8; // r12
  __int64 v9; // r15
  int v10; // r14d
  void *i; // rdx
  __int64 v12; // rbx
  __int64 GlobalLockName; // rax
  struct _GRETHREAD *v14; // rax
  bool v15; // zf
  void *v16; // rsi
  Gre::Base *v17; // rcx
  struct Gre::Base::SESSION_GLOBALS *v18; // rax
  __int64 j; // rsi
  __int64 k; // rbx
  REGION *v21; // [rsp+20h] [rbp-60h] BYREF
  __int64 v22; // [rsp+28h] [rbp-58h] BYREF
  HDEV v23; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _RECTL v26; // [rsp+50h] [rbp-30h] BYREF
  struct _RECTL v27; // [rsp+60h] [rbp-20h] BYREF

  v1 = *a1;
  v26 = 0;
  v25[0] = v1;
  v3 = Gre::Base::Globals((Gre::Base *)a1);
  v7 = a1[130];
  v8 = v3;
  if ( v7 )
  {
    v23 = a1[130];
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v23);
    a1[130] = 0;
  }
  v9 = *(_QWORD *)(W32GetSessionState(v7, v4, v5, v6) + 96);
  if ( *(_QWORD *)(v9 + 4816) || a1[131] || *((_DWORD *)v1 + 658) )
  {
    RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v21);
    if ( v21 )
    {
      *(_QWORD *)&v26.left = 0;
      *(_QWORD *)&v26.right = **(_QWORD **)&PDEVOBJ::sizl((PDEVOBJ *)v25);
      RGNOBJ::vSet((RGNOBJ *)&v21, &v26);
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v23);
      RGNMEMOBJTMP::RGNMEMOBJTMP((RGNMEMOBJTMP *)&v22);
      if ( !v23 || !v22 )
        goto LABEL_9;
      v27 = 0;
      v10 = 0;
      GreAcquireSemaphore<8,PDEVOBJ>(v1);
      for ( i = 0; ; i = v16 )
      {
        v16 = DxDdEnumLockedSurfaceRect(v1, i, &v27);
        if ( !v16 )
          break;
        RGNOBJ::vSet((RGNOBJ *)&v23, &v27);
        RGNOBJ::bCopy((RGNOBJ *)&v22, (struct RGNOBJ *)&v21);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v21, (struct RGNOBJ *)&v22, (struct RGNOBJ *)&v23, 4u) )
          v10 = 1;
        else
          RGNOBJ::vSet((RGNOBJ *)&v21);
      }
      GreReleaseSemaphoreExclusive<8,PDEVOBJ>(v1);
      v18 = Gre::Base::Globals(v17);
      SEMOBJ<33>::SEMOBJ<33>(&v24, v18);
      for ( j = *(_QWORD *)(v9 + 4816); j; j = *(_QWORD *)(j + 8) )
      {
        for ( k = *(_QWORD *)(j + 24); k; k = *(_QWORD *)(k + 160) )
        {
          UNDODESKTOPCOORD::UNDODESKTOPCOORD((UNDODESKTOPCOORD *)v25, (struct EWNDOBJ *)k, (struct _SPRITESTATE *)a1);
          if ( (*(_DWORD *)(k + 184) & 0x1000000) != 0 )
          {
            RGNOBJ::bCopy((RGNOBJ *)&v22, (struct RGNOBJ *)&v21);
            if ( RGNOBJ::bMerge((RGNOBJ *)&v21, (struct RGNOBJ *)&v22, (struct RGNOBJ *)(k + 56), 4u) )
              v10 = 1;
            else
              RGNOBJ::vSet((RGNOBJ *)&v21);
          }
          UNDODESKTOPCOORD::~UNDODESKTOPCOORD((UNDODESKTOPCOORD *)v25);
        }
      }
      if ( a1[131] )
      {
        v25[0] = a1[131];
        RGNOBJ::bCopy((RGNOBJ *)&v22, (struct RGNOBJ *)&v21);
        if ( RGNOBJ::bMerge((RGNOBJ *)&v21, (struct RGNOBJ *)&v22, (struct RGNOBJ *)v25, 8u) )
          v10 = 1;
        else
          RGNOBJ::vSet((RGNOBJ *)&v21);
      }
      v12 = v24;
      if ( v24 )
      {
        GlobalLockName = GrepGetGlobalLockName(33);
        EtwTraceGreLockReleaseSemaphore(GlobalLockName, v12);
        v14 = GreGetCurrentThreadCrossSessionCheck();
        if ( v14 )
        {
          v15 = (*(_QWORD *)v14 & 0xFFFFFFFDFFFFFFFFuLL) == 0;
          *(_QWORD *)v14 &= ~0x200000000uLL;
          if ( v15 )
            GrepOnAllLocksReleased();
        }
        ((void (__fastcall *)(__int64))GreReleaseSemaphoreExclusiveInternal)(v12);
      }
      if ( v10 == 1 )
      {
        REGION::vStamp(v21);
        a1[130] = (HDEV)v21;
      }
      else
      {
LABEL_9:
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v21);
      }
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v22);
      RGNMEMOBJTMP::~RGNMEMOBJTMP((RGNMEMOBJTMP *)&v23);
    }
  }
  *((_DWORD *)a1 + 29) = 0;
  vSpComputeSpriteRanges(a1);
  ++*((_DWORD *)v8 + 1088);
}

```

## disassembly

```asm
0x14008beb4  mov     [rsp-28h+arg_8], rbx
0x14008beb9  mov     [rsp-28h+arg_10], rsi
0x14008bebe  push    rbp
0x14008bebf  push    rdi
0x14008bec0  push    r12
0x14008bec2  push    r14
0x14008bec4  push    r15
0x14008bec6  mov     rbp, rsp
0x14008bec9  sub     rsp, 80h
0x14008bed0  mov     rax, cs:__security_cookie
0x14008bed7  xor     rax, rsp
0x14008beda  mov     [rbp+var_10], rax
0x14008bede  mov     rbx, [rcx]
0x14008bee1  xorps   xmm0, xmm0
0x14008bee4  movups  [rbp+var_30], xmm0
0x14008bee8  mov     [rbp+var_40], rbx
0x14008beec  mov     rdi, rcx
0x14008beef  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008bef6  nop     dword ptr [rax+rax+00h]
0x14008befb  mov     rcx, [rdi+410h]
0x14008bf02  mov     r12, rax
0x14008bf05  test    rcx, rcx
0x14008bf08  jnz     loc_14008C0B6
0x14008bf0e  call    cs:__imp_W32GetSessionState
0x14008bf15  nop     dword ptr [rax+rax+00h]
0x14008bf1a  mov     r15, [rax+60h]
0x14008bf1e  cmp     qword ptr [r15+12D0h], 0
0x14008bf26  jnz     short loc_14008BF7B
0x14008bf28  cmp     qword ptr [rdi+418h], 0
0x14008bf30  jnz     short loc_14008BF7B
0x14008bf32  cmp     dword ptr [rbx+0A48h], 0
0x14008bf39  jnz     short loc_14008BF7B
0x14008bf3b  mov     rcx, rdi
0x14008bf3e  mov     dword ptr [rdi+74h], 0
0x14008bf45  call    ?vSpComputeSpriteRanges@@YAXPEAU_SPRITESTATE@@W4vSpComputeSpriteRangesOptions@@@Z; vSpComputeSpriteRanges(_SPRITESTATE *,vSpComputeSpriteRangesOptions)
0x14008bf4a  inc     dword ptr [r12+1100h]
0x14008bf52  mov     rcx, [rbp+var_10]
0x14008bf56  xor     rcx, rsp; StackCookie
0x14008bf59  call    __security_check_cookie
0x14008bf5e  lea     r11, [rsp+80h+var_s0]
0x14008bf66  mov     rbx, [r11+38h]
0x14008bf6a  mov     rsi, [r11+40h]
0x14008bf6e  mov     rsp, r11
0x14008bf71  pop     r15
0x14008bf73  pop     r14
0x14008bf75  pop     r12
0x14008bf77  pop     rdi
0x14008bf78  pop     rbp
0x14008bf79  retn
0x14008bf7b  lea     rcx, [rbp+var_60]
0x14008bf7f  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14008bf86  nop     dword ptr [rax+rax+00h]
0x14008bf8b  cmp     [rbp+var_60], 0
0x14008bf90  jz      short loc_14008BF3B
0x14008bf92  lea     rdx, [rbp+var_48]
0x14008bf96  mov     qword ptr [rbp+var_30], 0
0x14008bf9e  lea     rcx, [rbp+var_40]; this
0x14008bfa2  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x14008bfa7  lea     rdx, [rbp+var_48]
0x14008bfab  mov     ecx, [rax]
0x14008bfad  mov     dword ptr [rbp+var_30+8], ecx
0x14008bfb0  lea     rcx, [rbp+var_40]; this
0x14008bfb4  call    ?sizl@PDEVOBJ@@QEAA?AUtagSIZE@@XZ; PDEVOBJ::sizl(void)
0x14008bfb9  lea     rdx, [rbp+var_30]
0x14008bfbd  mov     ecx, [rax+4]
0x14008bfc0  mov     dword ptr [rbp+var_30+0Ch], ecx
0x14008bfc3  lea     rcx, [rbp+var_60]
0x14008bfc7  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14008bfce  nop     dword ptr [rax+rax+00h]
0x14008bfd3  lea     rcx, [rbp+var_50]; this
0x14008bfd7  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14008bfdc  lea     rcx, [rbp+var_58]; this
0x14008bfe0  call    ??0RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::RGNMEMOBJTMP(void)
0x14008bfe5  cmp     [rbp+var_50], 0
0x14008bfea  jnz     short loc_14008C013
0x14008bfec  lea     rcx, [rbp+var_60]
0x14008bff0  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008bff7  nop     dword ptr [rax+rax+00h]
0x14008bffc  lea     rcx, [rbp+var_58]; this
0x14008c000  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14008c005  lea     rcx, [rbp+var_50]; this
0x14008c009  call    ??1RGNMEMOBJTMP@@QEAA@XZ; RGNMEMOBJTMP::~RGNMEMOBJTMP(void)
0x14008c00e  jmp     loc_14008BF3B
0x14008c013  cmp     [rbp+var_58], 0
0x14008c018  jz      short loc_14008BFEC
0x14008c01a  xorps   xmm0, xmm0
0x14008c01d  mov     rcx, rbx
0x14008c020  movups  xmmword ptr [rbp+var_20.left], xmm0
0x14008c024  xor     r14d, r14d
0x14008c027  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x14008c02c  xor     edx, edx
0x14008c02e  jmp     loc_14008C13C
0x14008c033  mov     rbx, [rbp+var_48]
0x14008c037  test    rbx, rbx
0x14008c03a  jz      short loc_14008C08C
0x14008c03c  mov     ecx, 21h ; '!'
0x14008c041  call    ?GrepGetGlobalLockName@@YAPEBGW4GreLockClass@@@Z; GrepGetGlobalLockName(GreLockClass)
0x14008c046  mov     rcx, rax
0x14008c049  mov     rdx, rbx
0x14008c04c  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14008c053  nop     dword ptr [rax+rax+00h]
0x14008c058  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14008c05d  test    rax, rax
0x14008c060  jz      short loc_14008C07D
0x14008c062  mov     rcx, 0FFFFFFFDFFFFFFFFh
0x14008c06c  and     [rax], rcx
0x14008c06f  jnz     short loc_14008C07D
0x14008c071  call    cs:__imp_?GrepOnAllLocksReleased@@YAXXZ; GrepOnAllLocksReleased(void)
0x14008c078  nop     dword ptr [rax+rax+00h]
0x14008c07d  mov     rax, cs:__imp_?GreReleaseSemaphoreExclusiveInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreExclusiveInternal(HSEMAPHORE__ *)
0x14008c084  mov     rcx, rbx
0x14008c087  call    _guard_dispatch_icall
0x14008c08c  cmp     r14d, 1
0x14008c090  jnz     loc_14008BFEC
0x14008c096  mov     rcx, [rbp+var_60]
0x14008c09a  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14008c0a1  nop     dword ptr [rax+rax+00h]
0x14008c0a6  mov     rax, [rbp+var_60]
0x14008c0aa  mov     [rdi+410h], rax
0x14008c0b1  jmp     loc_14008BFFC
0x14008c0b6  mov     [rbp+var_50], rcx
0x14008c0ba  lea     rcx, [rbp+var_50]
0x14008c0be  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14008c0c5  nop     dword ptr [rax+rax+00h]
0x14008c0ca  mov     qword ptr [rdi+410h], 0
0x14008c0d5  jmp     loc_14008BF0E
0x14008c0da  lea     rdx, [rbp+var_20]
0x14008c0de  lea     rcx, [rbp+var_50]
0x14008c0e2  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14008c0e9  nop     dword ptr [rax+rax+00h]
0x14008c0ee  lea     rdx, [rbp+var_60]
0x14008c0f2  lea     rcx, [rbp+var_58]
0x14008c0f6  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14008c0fd  nop     dword ptr [rax+rax+00h]
0x14008c102  mov     r9b, 4
0x14008c105  lea     r8, [rbp+var_50]
0x14008c109  lea     rdx, [rbp+var_58]
0x14008c10d  lea     rcx, [rbp+var_60]
0x14008c111  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14008c118  nop     dword ptr [rax+rax+00h]
0x14008c11d  test    eax, eax
0x14008c11f  jnz     short loc_14008C133
0x14008c121  lea     rcx, [rbp+var_60]
0x14008c125  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x14008c12c  nop     dword ptr [rax+rax+00h]
0x14008c131  jmp     short loc_14008C139
0x14008c133  mov     r14d, 1
0x14008c139  mov     rdx, rsi; void *
0x14008c13c  lea     r8, [rbp+var_20]; struct _RECTL *
0x14008c140  mov     rcx, rbx; HDEV
0x14008c143  call    ?DxDdEnumLockedSurfaceRect@@YAPEAXPEAUHDEV__@@PEAXPEAU_RECTL@@@Z; DxDdEnumLockedSurfaceRect(HDEV__ *,void *,_RECTL *)
0x14008c148  mov     rsi, rax
0x14008c14b  test    rax, rax
0x14008c14e  jnz     short loc_14008C0DA
0x14008c150  mov     rcx, rbx
0x14008c153  call    ??$GreReleaseSemaphoreExclusive@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreReleaseSemaphoreExclusive<8,PDEVOBJ>(PDEVOBJ)
0x14008c158  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c15f  nop     dword ptr [rax+rax+00h]
0x14008c164  mov     rdx, rax
0x14008c167  lea     rcx, [rbp+var_48]
0x14008c16b  call    ??0?$SEMOBJ@$0CB@@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJ<33>::SEMOBJ<33>(Gre::Base::SESSION_GLOBALS &)
0x14008c170  mov     rsi, [r15+12D0h]
0x14008c177  jmp     loc_14008C201
0x14008c17c  mov     rbx, [rsi+18h]
0x14008c180  jmp     short loc_14008C1F8
0x14008c182  mov     r8, rdi; struct _SPRITESTATE *
0x14008c185  lea     rcx, [rbp+var_40]; this
0x14008c189  mov     rdx, rbx; struct EWNDOBJ *
0x14008c18c  call    ??0UNDODESKTOPCOORD@@QEAA@PEAVEWNDOBJ@@PEAU_SPRITESTATE@@@Z; UNDODESKTOPCOORD::UNDODESKTOPCOORD(EWNDOBJ *,_SPRITESTATE *)
0x14008c191  test    dword ptr [rbx+0B8h], 1000000h
0x14008c19b  jz      short loc_14008C1E8
0x14008c19d  lea     rdx, [rbp+var_60]
0x14008c1a1  lea     rcx, [rbp+var_58]
0x14008c1a5  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14008c1ac  nop     dword ptr [rax+rax+00h]
0x14008c1b1  lea     r8, [rbx+38h]
0x14008c1b5  mov     r9b, 4
0x14008c1b8  lea     rdx, [rbp+var_58]
0x14008c1bc  lea     rcx, [rbp+var_60]
0x14008c1c0  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14008c1c7  nop     dword ptr [rax+rax+00h]
0x14008c1cc  test    eax, eax
0x14008c1ce  jnz     short loc_14008C1E2
0x14008c1d0  lea     rcx, [rbp+var_60]
0x14008c1d4  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x14008c1db  nop     dword ptr [rax+rax+00h]
0x14008c1e0  jmp     short loc_14008C1E8
0x14008c1e2  mov     r14d, 1
0x14008c1e8  lea     rcx, [rbp+var_40]; this
0x14008c1ec  call    ??1UNDODESKTOPCOORD@@QEAA@XZ; UNDODESKTOPCOORD::~UNDODESKTOPCOORD(void)
0x14008c1f1  mov     rbx, [rbx+0A0h]
0x14008c1f8  test    rbx, rbx
0x14008c1fb  jnz     short loc_14008C182
0x14008c1fd  mov     rsi, [rsi+8]
0x14008c201  test    rsi, rsi
0x14008c204  jnz     loc_14008C17C
0x14008c20a  mov     rax, [rdi+418h]
0x14008c211  test    rax, rax
0x14008c214  jz      loc_14008C033
0x14008c21a  lea     rdx, [rbp+var_60]
0x14008c21e  mov     [rbp+var_40], rax
0x14008c222  lea     rcx, [rbp+var_58]
0x14008c226  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x14008c22d  nop     dword ptr [rax+rax+00h]
0x14008c232  mov     r9b, 8
0x14008c235  lea     r8, [rbp+var_40]
0x14008c239  lea     rdx, [rbp+var_58]
0x14008c23d  lea     rcx, [rbp+var_60]
0x14008c241  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x14008c248  nop     dword ptr [rax+rax+00h]
0x14008c24d  test    eax, eax
0x14008c24f  jnz     short loc_14008C266
0x14008c251  lea     rcx, [rbp+var_60]
0x14008c255  call    cs:__imp_?vSet@RGNOBJ@@QEAAXXZ; RGNOBJ::vSet(void)
0x14008c25c  nop     dword ptr [rax+rax+00h]
0x14008c261  jmp     loc_14008C033
0x14008c266  mov     r14d, 1
0x14008c26c  jmp     loc_14008C033
```
