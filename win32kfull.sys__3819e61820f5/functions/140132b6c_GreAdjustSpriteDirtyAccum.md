# GreAdjustSpriteDirtyAccum

- ea: `0x140132b6c`
- end: `0x140132e0a`
- name: `GreAdjustSpriteDirtyAccum`
- size: `670`
- prototype: `__int64 __usercall@<rax>(HDEV@<rcx>, HWND@<rdx>, struct _RECTL *@<r8>, struct _POINTL *, struct _POINTL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401339d8`

## callees

- `0x1400875b8`
- `0x14008be9c`
- `0x14008eb28`
- `0x140093570`
- `0x140132b6c`
- `0x140132e10`
- `0x1403068cc`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140132bae`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140132d8e`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140132bae`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140132d8e`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140132da0`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x140132da0`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140132db8`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140132bca`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140132bca`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132c6c`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132c95`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132c6c`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132c95`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140132c5c`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140132c85`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140132c5c`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140132c85`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140132d3a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140132d5a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140132d3a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140132d5a`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132d2a`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132d4a`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132d2a`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140132d4a`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140132cd5`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140132cd5`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140132cf0`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140132cf0`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140132d08`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140132d08`
- `win32kbase!GreReleasePushLockExclusive` at `0x140132d6e`
- `win32kbase!GreReleasePushLockExclusive` at `0x140132d82`
- `win32kbase!GreReleasePushLockExclusive` at `0x140132d6e`
- `win32kbase!GreReleasePushLockExclusive` at `0x140132d82`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140132c17`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140132c32`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140132c17`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140132c32`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140132cbd`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140132cbd`

## pseudocode

```c
__int64 __fastcall GreAdjustSpriteDirtyAccum(
        HDEV a1,
        HWND a2,
        struct _RECTL *a3,
        __int64 a4,
        struct _POINTL *a5,
        struct _POINTL *a6)
{
  struct _RECTL *v6; // rbx
  HDEV v8; // rdi
  Gre::Base *v9; // rcx
  struct _RECTL *v10; // r9
  unsigned int v11; // r15d
  int v12; // r13d
  Gre::Base *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // r14
  struct Gre::Base::SESSION_GLOBALS *v16; // rax
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  struct REGION *v19; // [rsp+38h] [rbp-18h] BYREF
  HSEMAPHORE v20; // [rsp+40h] [rbp-10h]
  __int64 v23; // [rsp+A8h] [rbp+58h] BYREF

  v23 = a4;
  v6 = a3;
  v8 = a1;
  if ( !(unsigned int)IsDwmActive() )
    return (unsigned int)GdiAdjustSpriteDirtyAccum(v8, a2, v6, v10, a5, a6);
  v11 = 0;
  v12 = 1;
  v20 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v9) + 520LL);
  GreAcquireSemaphoreSharedInternal(v20);
  GrepAcquireLockValidate<7>();
  if ( (unsigned int)IsDwmActive() )
  {
    v12 = 0;
    DWMALTSPRITEREF::DWMALTSPRITEREF((DWMALTSPRITEREF *)&v23, a2);
    v14 = v23;
    if ( v23 )
    {
      v15 = *(_QWORD *)(v23 + 144);
      if ( v23 != -88 )
        GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v23 + 88));
      if ( v15 != -256 )
        GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 256));
      if ( *(_QWORD *)(v15 + 80) )
      {
        v19 = *(struct REGION **)(v15 + 80);
        v18 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v18, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v18);
        v23 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v23, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v23);
        if ( v19 )
        {
          if ( v18 )
          {
            if ( v23 )
            {
              if ( RGNOBJ::bOffset((RGNOBJ *)&v19, a5) )
              {
                RGNOBJ::vSet((RGNOBJ *)&v18, a3);
                if ( RGNOBJ::bMerge((RGNOBJ *)&v23, (struct RGNOBJ *)&v19, (struct RGNOBJ *)&v18, 8u) )
                {
                  RGNOBJ::vSwap((RGNOBJ *)&v23, (struct RGNOBJ *)&v19);
                  SFMLOGICALSURFACE::vDirtyRegionAccum((SFMLOGICALSURFACE *)v15, v19);
                  v11 = 1;
                }
              }
            }
          }
        }
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v23);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v23);
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v18);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v18);
      }
      if ( v15 != -256 )
        GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 256));
      if ( v14 != -88 )
        GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v14 + 88));
      v16 = Gre::Base::Globals(v13);
      DEC_SHARE_REF_CNT(v16, v14);
      v6 = a3;
      v8 = a1;
    }
  }
  GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v20);
  if ( v12 )
    return (unsigned int)GdiAdjustSpriteDirtyAccum(v8, a2, v6, v10, a5, a6);
  return v11;
}

```

## disassembly

```asm
0x140132b6c  mov     rax, rsp
0x140132b6f  mov     [rax+10h], rbx
0x140132b73  mov     [rax+20h], r9
0x140132b77  mov     [rax+18h], r8
0x140132b7b  mov     [rax+8], rcx
0x140132b7f  push    rbp
0x140132b80  push    rsi
0x140132b81  push    rdi
0x140132b82  push    r12
0x140132b84  push    r13
0x140132b86  push    r14
0x140132b88  push    r15
0x140132b8a  mov     rbp, rsp
0x140132b8d  sub     rsp, 50h
0x140132b91  mov     rbx, r8
0x140132b94  mov     r12, rdx
0x140132b97  mov     rdi, rcx
0x140132b9a  call    IsDwmActive
0x140132b9f  test    eax, eax
0x140132ba1  jz      loc_140132DE5
0x140132ba7  xor     r15d, r15d
0x140132baa  lea     r13d, [r15+1]
0x140132bae  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140132bb5  nop     dword ptr [rax+rax+00h]
0x140132bba  mov     rax, [rax]
0x140132bbd  add     rax, 208h
0x140132bc3  mov     rcx, rax
0x140132bc6  mov     [rbp+var_10], rax
0x140132bca  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140132bd1  nop     dword ptr [rax+rax+00h]
0x140132bd6  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x140132bdb  call    IsDwmActive
0x140132be0  test    eax, eax
0x140132be2  jz      loc_140132DB4
0x140132be8  mov     rdx, r12; HWND
0x140132beb  lea     rcx, [rbp+arg_18]; this
0x140132bef  xor     r13d, r13d
0x140132bf2  call    ??0DWMALTSPRITEREF@@QEAA@PEAUHWND__@@@Z; DWMALTSPRITEREF::DWMALTSPRITEREF(HWND__ *)
0x140132bf7  mov     rsi, [rbp+arg_18]
0x140132bfb  test    rsi, rsi
0x140132bfe  jz      loc_140132DB4
0x140132c04  mov     r14, [rsi+90h]
0x140132c0b  lea     rdi, [rsi+58h]
0x140132c0f  test    rdi, rdi
0x140132c12  jz      short loc_140132C23
0x140132c14  mov     rcx, rdi
0x140132c17  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140132c1e  nop     dword ptr [rax+rax+00h]
0x140132c23  lea     rbx, [r14+100h]
0x140132c2a  test    rbx, rbx
0x140132c2d  jz      short loc_140132C3E
0x140132c2f  mov     rcx, rbx
0x140132c32  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140132c39  nop     dword ptr [rax+rax+00h]
0x140132c3e  mov     rax, [r14+50h]
0x140132c42  test    rax, rax
0x140132c45  jz      loc_140132D66
0x140132c4b  mov     edx, 70h ; 'p'
0x140132c50  mov     [rbp+var_18], rax
0x140132c54  lea     rcx, [rbp+var_20]
0x140132c58  mov     [rbp+var_20], r13
0x140132c5c  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x140132c63  nop     dword ptr [rax+rax+00h]
0x140132c68  lea     rcx, [rbp+var_20]
0x140132c6c  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x140132c73  nop     dword ptr [rax+rax+00h]
0x140132c78  mov     edx, 70h ; 'p'
0x140132c7d  mov     [rbp+arg_18], r13
0x140132c81  lea     rcx, [rbp+arg_18]
0x140132c85  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x140132c8c  nop     dword ptr [rax+rax+00h]
0x140132c91  lea     rcx, [rbp+arg_18]
0x140132c95  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x140132c9c  nop     dword ptr [rax+rax+00h]
0x140132ca1  xor     eax, eax
0x140132ca3  cmp     [rbp+var_18], rax
0x140132ca7  jz      short loc_140132D26
0x140132ca9  cmp     [rbp+var_20], rax
0x140132cad  jz      short loc_140132D26
0x140132caf  cmp     [rbp+arg_18], rax
0x140132cb3  jz      short loc_140132D26
0x140132cb5  mov     rdx, [rbp+arg_20]
0x140132cb9  lea     rcx, [rbp+var_18]
0x140132cbd  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x140132cc4  nop     dword ptr [rax+rax+00h]
0x140132cc9  test    eax, eax
0x140132ccb  jz      short loc_140132D26
0x140132ccd  mov     rdx, [rbp+arg_10]
0x140132cd1  lea     rcx, [rbp+var_20]
0x140132cd5  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140132cdc  nop     dword ptr [rax+rax+00h]
0x140132ce1  mov     r9b, 8
0x140132ce4  lea     r8, [rbp+var_20]
0x140132ce8  lea     rdx, [rbp+var_18]
0x140132cec  lea     rcx, [rbp+arg_18]
0x140132cf0  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140132cf7  nop     dword ptr [rax+rax+00h]
0x140132cfc  test    eax, eax
0x140132cfe  jz      short loc_140132D26
0x140132d00  lea     rdx, [rbp+var_18]
0x140132d04  lea     rcx, [rbp+arg_18]
0x140132d08  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x140132d0f  nop     dword ptr [rax+rax+00h]
0x140132d14  mov     rdx, [rbp+var_18]; struct REGION *
0x140132d18  mov     rcx, r14; this
0x140132d1b  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x140132d20  mov     r15d, 1
0x140132d26  lea     rcx, [rbp+arg_18]
0x140132d2a  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x140132d31  nop     dword ptr [rax+rax+00h]
0x140132d36  lea     rcx, [rbp+arg_18]
0x140132d3a  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140132d41  nop     dword ptr [rax+rax+00h]
0x140132d46  lea     rcx, [rbp+var_20]
0x140132d4a  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x140132d51  nop     dword ptr [rax+rax+00h]
0x140132d56  lea     rcx, [rbp+var_20]
0x140132d5a  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140132d61  nop     dword ptr [rax+rax+00h]
0x140132d66  test    rbx, rbx
0x140132d69  jz      short loc_140132D7A
0x140132d6b  mov     rcx, rbx
0x140132d6e  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140132d75  nop     dword ptr [rax+rax+00h]
0x140132d7a  test    rdi, rdi
0x140132d7d  jz      short loc_140132D8E
0x140132d7f  mov     rcx, rdi
0x140132d82  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x140132d89  nop     dword ptr [rax+rax+00h]
0x140132d8e  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140132d95  nop     dword ptr [rax+rax+00h]
0x140132d9a  mov     rcx, rax
0x140132d9d  mov     rdx, rsi
0x140132da0  call    cs:__imp_DEC_SHARE_REF_CNT
0x140132da7  nop     dword ptr [rax+rax+00h]
0x140132dac  mov     rbx, [rbp+arg_10]
0x140132db0  mov     rdi, [rbp+arg_0]
0x140132db4  mov     rdx, [rbp+var_10]
0x140132db8  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140132dbf  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140132dc4  test    r13d, r13d
0x140132dc7  jnz     short loc_140132DE5
0x140132dc9  mov     rbx, [rsp+50h+arg_8]
0x140132dd1  mov     eax, r15d
0x140132dd4  add     rsp, 50h
0x140132dd8  pop     r15
0x140132dda  pop     r14
0x140132ddc  pop     r13
0x140132dde  pop     r12
0x140132de0  pop     rdi
0x140132de1  pop     rsi
0x140132de2  pop     rbp
0x140132de3  retn
0x140132de5  mov     rax, [rbp+arg_28]
0x140132de9  mov     r8, rbx; struct _RECTL *
0x140132dec  mov     [rsp+50h+var_28], rax; struct _POINTL *
0x140132df1  mov     rdx, r12; HWND
0x140132df4  mov     rax, [rbp+arg_20]
0x140132df8  mov     rcx, rdi; HDEV
0x140132dfb  mov     [rsp+50h+var_30], rax; struct _POINTL *
0x140132e00  call    ?GdiAdjustSpriteDirtyAccum@@YAHPEAUHDEV__@@PEAUHWND__@@PEAU_RECTL@@2PEAU_POINTL@@3@Z; GdiAdjustSpriteDirtyAccum(HDEV__ *,HWND__ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *)
0x140132e05  mov     r15d, eax
0x140132e08  jmp     short loc_140132DC9
```
