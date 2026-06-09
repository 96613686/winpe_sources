# GreAdjustSpriteDirtyAccum

- ea: `0x1401202a8`
- end: `0x140120546`
- name: `GreAdjustSpriteDirtyAccum`
- size: `670`
- prototype: `__int64 __fastcall(Gre::Base *, HWND, struct _RECTL *, __int64, struct _POINTL *, struct _POINTL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140110d58`

## callees

- `0x140016de4`
- `0x1400a9b80`
- `0x14011c694`
- `0x14011ee44`
- `0x1401202a8`
- `0x14012054c`
- `0x1403085bc`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401202ea`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401204ca`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401202ea`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401204ca`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1401204dc`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x1401204dc`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401204f4`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140120306`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140120306`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401203a8`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401203d1`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401203a8`
- `win32kbase!?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x1401203d1`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140120398`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401203c1`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x140120398`
- `win32kbase!?vInitialize@RGNMEMOBJ@@QEAAXK@Z` at `0x1401203c1`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140120476`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140120496`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140120476`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x140120496`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140120466`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140120486`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140120466`
- `win32kbase!?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ` at `0x140120486`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140120411`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x140120411`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14012042c`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x14012042c`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140120444`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140120444`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401204aa`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401204be`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401204aa`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401204be`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140120353`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14012036e`
- `win32kbase!GreAcquirePushLockExclusive` at `0x140120353`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14012036e`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401203f9`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401203f9`

## pseudocode

```c
__int64 __fastcall GreAdjustSpriteDirtyAccum(
        Gre::Base *a1,
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
  Gre::Base *v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // r14
  struct Gre::Base::SESSION_GLOBALS *v17; // rax
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  struct REGION *v20; // [rsp+38h] [rbp-18h] BYREF
  HSEMAPHORE v21; // [rsp+40h] [rbp-10h]
  __int64 v24; // [rsp+A8h] [rbp+58h] BYREF

  v24 = a4;
  v6 = a3;
  v8 = (HDEV)a1;
  if ( !IsDwmActive(a1) )
    return (unsigned int)GdiAdjustSpriteDirtyAccum(v8, a2, v6, v10, a5, a6);
  v11 = 0;
  v12 = 1;
  v21 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v9) + 520LL);
  GreAcquireSemaphoreSharedInternal(v21);
  GrepAcquireLockValidate<7>();
  if ( IsDwmActive(v13) )
  {
    v12 = 0;
    DWMALTSPRITEREF::DWMALTSPRITEREF((DWMALTSPRITEREF *)&v24, a2);
    v15 = v24;
    if ( v24 )
    {
      v16 = *(_QWORD *)(v24 + 144);
      if ( v24 != -88 )
        GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v24 + 88));
      if ( v16 != -256 )
        GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v16 + 256));
      if ( *(_QWORD *)(v16 + 80) )
      {
        v20 = *(struct REGION **)(v16 + 80);
        v19 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v19, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v19);
        v24 = 0;
        RGNMEMOBJ::vInitialize((RGNMEMOBJ *)&v24, 0x70u);
        RGNMEMOBJ::vPushThreadGuardedObject((RGNMEMOBJ *)&v24);
        if ( v20 )
        {
          if ( v19 )
          {
            if ( v24 )
            {
              if ( RGNOBJ::bOffset((RGNOBJ *)&v20, a5) )
              {
                RGNOBJ::vSet((RGNOBJ *)&v19, a3);
                if ( RGNOBJ::bMerge((RGNOBJ *)&v24, (struct RGNOBJ *)&v20, (struct RGNOBJ *)&v19, 8u) )
                {
                  RGNOBJ::vSwap((RGNOBJ *)&v24, (struct RGNOBJ *)&v20);
                  SFMLOGICALSURFACE::vDirtyRegionAccum((SFMLOGICALSURFACE *)v16, v20);
                  v11 = 1;
                }
              }
            }
          }
        }
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v24);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v24);
        RGNMEMOBJ::vPopThreadGuardedObject((RGNMEMOBJ *)&v19);
        RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v19);
      }
      if ( v16 != -256 )
        GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v16 + 256));
      if ( v15 != -88 )
        GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 88));
      v17 = Gre::Base::Globals(v14);
      DEC_SHARE_REF_CNT(v17, v15);
      v6 = a3;
      v8 = (HDEV)a1;
    }
  }
  GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(
    (__int64 (__fastcall *)(__int64))GreReleaseSemaphoreSharedInternal,
    (__int64)v21);
  if ( v12 )
    return (unsigned int)GdiAdjustSpriteDirtyAccum(v8, a2, v6, v10, a5, a6);
  return v11;
}

```

## disassembly

```asm
0x1401202a8  mov     rax, rsp
0x1401202ab  mov     [rax+10h], rbx
0x1401202af  mov     [rax+20h], r9
0x1401202b3  mov     [rax+18h], r8
0x1401202b7  mov     [rax+8], rcx
0x1401202bb  push    rbp
0x1401202bc  push    rsi
0x1401202bd  push    rdi
0x1401202be  push    r12
0x1401202c0  push    r13
0x1401202c2  push    r14
0x1401202c4  push    r15
0x1401202c6  mov     rbp, rsp
0x1401202c9  sub     rsp, 50h
0x1401202cd  mov     rbx, r8
0x1401202d0  mov     r12, rdx
0x1401202d3  mov     rdi, rcx
0x1401202d6  call    IsDwmActive
0x1401202db  test    eax, eax
0x1401202dd  jz      loc_140120521
0x1401202e3  xor     r15d, r15d
0x1401202e6  lea     r13d, [r15+1]
0x1401202ea  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401202f1  nop     dword ptr [rax+rax+00h]
0x1401202f6  mov     rax, [rax]
0x1401202f9  add     rax, 208h
0x1401202ff  mov     rcx, rax
0x140120302  mov     [rbp+var_10], rax
0x140120306  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14012030d  nop     dword ptr [rax+rax+00h]
0x140120312  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x140120317  call    IsDwmActive
0x14012031c  test    eax, eax
0x14012031e  jz      loc_1401204F0
0x140120324  mov     rdx, r12; HWND
0x140120327  lea     rcx, [rbp+arg_18]; this
0x14012032b  xor     r13d, r13d
0x14012032e  call    ??0DWMALTSPRITEREF@@QEAA@PEAUHWND__@@@Z; DWMALTSPRITEREF::DWMALTSPRITEREF(HWND__ *)
0x140120333  mov     rsi, [rbp+arg_18]
0x140120337  test    rsi, rsi
0x14012033a  jz      loc_1401204F0
0x140120340  mov     r14, [rsi+90h]
0x140120347  lea     rdi, [rsi+58h]
0x14012034b  test    rdi, rdi
0x14012034e  jz      short loc_14012035F
0x140120350  mov     rcx, rdi
0x140120353  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x14012035a  nop     dword ptr [rax+rax+00h]
0x14012035f  lea     rbx, [r14+100h]
0x140120366  test    rbx, rbx
0x140120369  jz      short loc_14012037A
0x14012036b  mov     rcx, rbx
0x14012036e  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140120375  nop     dword ptr [rax+rax+00h]
0x14012037a  mov     rax, [r14+50h]
0x14012037e  test    rax, rax
0x140120381  jz      loc_1401204A2
0x140120387  mov     edx, 70h ; 'p'
0x14012038c  mov     [rbp+var_18], rax
0x140120390  lea     rcx, [rbp+var_20]
0x140120394  mov     [rbp+var_20], r13
0x140120398  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x14012039f  nop     dword ptr [rax+rax+00h]
0x1401203a4  lea     rcx, [rbp+var_20]
0x1401203a8  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401203af  nop     dword ptr [rax+rax+00h]
0x1401203b4  mov     edx, 70h ; 'p'
0x1401203b9  mov     [rbp+arg_18], r13
0x1401203bd  lea     rcx, [rbp+arg_18]
0x1401203c1  call    cs:__imp_?vInitialize@RGNMEMOBJ@@QEAAXK@Z; RGNMEMOBJ::vInitialize(ulong)
0x1401203c8  nop     dword ptr [rax+rax+00h]
0x1401203cd  lea     rcx, [rbp+arg_18]
0x1401203d1  call    cs:__imp_?vPushThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPushThreadGuardedObject(void)
0x1401203d8  nop     dword ptr [rax+rax+00h]
0x1401203dd  xor     eax, eax
0x1401203df  cmp     [rbp+var_18], rax
0x1401203e3  jz      short loc_140120462
0x1401203e5  cmp     [rbp+var_20], rax
0x1401203e9  jz      short loc_140120462
0x1401203eb  cmp     [rbp+arg_18], rax
0x1401203ef  jz      short loc_140120462
0x1401203f1  mov     rdx, [rbp+arg_20]
0x1401203f5  lea     rcx, [rbp+var_18]
0x1401203f9  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x140120400  nop     dword ptr [rax+rax+00h]
0x140120405  test    eax, eax
0x140120407  jz      short loc_140120462
0x140120409  mov     rdx, [rbp+arg_10]
0x14012040d  lea     rcx, [rbp+var_20]
0x140120411  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x140120418  nop     dword ptr [rax+rax+00h]
0x14012041d  mov     r9b, 8
0x140120420  lea     r8, [rbp+var_20]
0x140120424  lea     rdx, [rbp+var_18]
0x140120428  lea     rcx, [rbp+arg_18]
0x14012042c  call    cs:__imp_?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z; RGNOBJ::bMerge(RGNOBJ &,RGNOBJ &,uchar)
0x140120433  nop     dword ptr [rax+rax+00h]
0x140120438  test    eax, eax
0x14012043a  jz      short loc_140120462
0x14012043c  lea     rdx, [rbp+var_18]
0x140120440  lea     rcx, [rbp+arg_18]
0x140120444  call    cs:__imp_?vSwap@RGNOBJ@@QEAAXPEAV1@@Z; RGNOBJ::vSwap(RGNOBJ *)
0x14012044b  nop     dword ptr [rax+rax+00h]
0x140120450  mov     rdx, [rbp+var_18]; struct REGION *
0x140120454  mov     rcx, r14; this
0x140120457  call    ?vDirtyRegionAccum@SFMLOGICALSURFACE@@QEAAXPEAVREGION@@@Z; SFMLOGICALSURFACE::vDirtyRegionAccum(REGION *)
0x14012045c  mov     r15d, 1
0x140120462  lea     rcx, [rbp+arg_18]
0x140120466  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14012046d  nop     dword ptr [rax+rax+00h]
0x140120472  lea     rcx, [rbp+arg_18]
0x140120476  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14012047d  nop     dword ptr [rax+rax+00h]
0x140120482  lea     rcx, [rbp+var_20]
0x140120486  call    cs:__imp_?vPopThreadGuardedObject@RGNMEMOBJ@@QEAAXXZ; RGNMEMOBJ::vPopThreadGuardedObject(void)
0x14012048d  nop     dword ptr [rax+rax+00h]
0x140120492  lea     rcx, [rbp+var_20]
0x140120496  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14012049d  nop     dword ptr [rax+rax+00h]
0x1401204a2  test    rbx, rbx
0x1401204a5  jz      short loc_1401204B6
0x1401204a7  mov     rcx, rbx
0x1401204aa  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1401204b1  nop     dword ptr [rax+rax+00h]
0x1401204b6  test    rdi, rdi
0x1401204b9  jz      short loc_1401204CA
0x1401204bb  mov     rcx, rdi
0x1401204be  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1401204c5  nop     dword ptr [rax+rax+00h]
0x1401204ca  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401204d1  nop     dword ptr [rax+rax+00h]
0x1401204d6  mov     rcx, rax
0x1401204d9  mov     rdx, rsi
0x1401204dc  call    cs:__imp_DEC_SHARE_REF_CNT
0x1401204e3  nop     dword ptr [rax+rax+00h]
0x1401204e8  mov     rbx, [rbp+arg_10]
0x1401204ec  mov     rdi, [rbp+arg_0]
0x1401204f0  mov     rdx, [rbp+var_10]
0x1401204f4  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1401204fb  call    ??$GreReleaseSemaphoreCommon@$06P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<7,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140120500  test    r13d, r13d
0x140120503  jnz     short loc_140120521
0x140120505  mov     rbx, [rsp+50h+arg_8]
0x14012050d  mov     eax, r15d
0x140120510  add     rsp, 50h
0x140120514  pop     r15
0x140120516  pop     r14
0x140120518  pop     r13
0x14012051a  pop     r12
0x14012051c  pop     rdi
0x14012051d  pop     rsi
0x14012051e  pop     rbp
0x14012051f  retn
0x140120521  mov     rax, [rbp+arg_28]
0x140120525  mov     r8, rbx; struct _RECTL *
0x140120528  mov     [rsp+50h+var_28], rax; struct _POINTL *
0x14012052d  mov     rdx, r12; HWND
0x140120530  mov     rax, [rbp+arg_20]
0x140120534  mov     rcx, rdi; HDEV
0x140120537  mov     [rsp+50h+var_30], rax; struct _POINTL *
0x14012053c  call    ?GdiAdjustSpriteDirtyAccum@@YAHPEAUHDEV__@@PEAUHWND__@@PEAU_RECTL@@2PEAU_POINTL@@3@Z; GdiAdjustSpriteDirtyAccum(HDEV__ *,HWND__ *,_RECTL *,_RECTL *,_POINTL *,_POINTL *)
0x140120541  mov     r15d, eax
0x140120544  jmp     short loc_140120505
```
