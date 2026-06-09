# GreUpdateSpriteClipRgn

- ea: `0x1401213e0`
- end: `0x1401216d7`
- name: `GreUpdateSpriteClipRgn`
- size: `759`
- prototype: `void __fastcall(Gre::Base *, Gre::Base *, HRGN, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140028978`
- `0x140029014`

## callees

- `0x140014178`
- `0x140014550`
- `0x140016de4`
- `0x1400197fc`
- `0x1400a9b80`
- `0x14011f600`
- `0x1401213e0`
- `0x1401216e0`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140121401`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401214a5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140121401`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401214a5`
- `win32kbase!PopThreadGuardedObject` at `0x14012162e`
- `win32kbase!PopThreadGuardedObject` at `0x140121662`
- `win32kbase!PopThreadGuardedObject` at `0x14012162e`
- `win32kbase!PopThreadGuardedObject` at `0x140121662`
- `win32kbase!PushThreadGuardedObject` at `0x140121486`
- `win32kbase!PushThreadGuardedObject` at `0x140121486`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401215ba`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401215ba`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140121699`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x140121699`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401215dd`
- `win32kbase!GreReleasePushLockExclusive` at `0x140121608`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401215dd`
- `win32kbase!GreReleasePushLockExclusive` at `0x140121608`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401214eb`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14012150d`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401214eb`
- `win32kbase!GreAcquirePushLockExclusive` at `0x14012150d`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140121559`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140121559`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140121435`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140121435`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1401214c2`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1401214c2`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140121581`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140121581`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140121460`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140121460`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140121644`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140121644`
- `win32kbase!?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z` at `0x1401216c6`
- `win32kbase!?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z` at `0x1401216c6`

## pseudocode

```c
void __fastcall GreUpdateSpriteClipRgn(Gre::Base *a1, Gre::Base *a2, HRGN a3, int a4)
{
  struct Gre::Base::SESSION_GLOBALS *v7; // rdi
  struct PDEVOBJ *v8; // rdx
  HSEMAPHORE v9; // rcx
  Gre::Base *v10; // rcx
  __int64 v11; // rbx
  Gre::Base *v12; // rcx
  struct Gre::Base::SESSION_GLOBALS *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdi
  __int64 v16; // rbx
  struct _POINTL v17; // [rsp+20h] [rbp-79h] BYREF
  _OWORD v18[2]; // [rsp+28h] [rbp-71h] BYREF
  __int64 v19; // [rsp+48h] [rbp-51h]
  _DWORD v20[4]; // [rsp+50h] [rbp-49h] BYREF
  Gre::Base *v21; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v22[8]; // [rsp+68h] [rbp-31h] BYREF
  HSEMAPHORE v23; // [rsp+70h] [rbp-29h]
  char v24; // [rsp+78h] [rbp-21h]
  __int64 v25; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v26[40]; // [rsp+88h] [rbp-11h] BYREF
  int v27; // [rsp+B0h] [rbp+17h]
  __int64 v28; // [rsp+100h] [rbp+67h] BYREF

  v21 = a1;
  v7 = Gre::Base::Globals(a1);
  DWMSPRITELOCK::DWMSPRITELOCK((DWMSPRITELOCK *)v22, v8, 0, 0);
  v9 = (HSEMAPHORE)(*(_QWORD *)v7 + 520LL);
  v24 = 0;
  v23 = v9;
  GreAcquireSemaphoreInternal(v9);
  GrepAcquireLockValidate<7>();
  if ( !IsDwmActive(v10) )
    goto LABEL_35;
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v25, a3, 0, 0);
  memset(v18, 0, sizeof(v18));
  PushThreadGuardedObject(
    v18,
    v18,
    UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
  v19 = 0;
  v11 = DWMSPRITEREF::hspLookupWindow(a2);
  v13 = Gre::Base::Globals(v12);
  if ( v11 )
  {
    LOBYTE(v14) = 15;
    v19 = HmgLock(v13, v11, v14, 0);
  }
  v15 = v19;
  if ( v19 )
  {
    if ( v19 != -88 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v19 + 88));
    v16 = *(_QWORD *)(v15 + 144);
    if ( v16 != -256 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v16 + 256));
    if ( v25 && (unsigned int)UserGetWindowRect(*(_QWORD *)(v15 + 40), v20) )
    {
      if ( !*(_QWORD *)(v16 + 88) )
      {
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v28);
        if ( v28 )
          *(_QWORD *)(v16 + 88) = v28;
      }
      if ( !*(_QWORD *)(v16 + 88) )
        goto LABEL_22;
      v28 = *(_QWORD *)(v16 + 88);
      if ( !RGNOBJ::bCopy((RGNOBJ *)&v28, (struct RGNOBJ *)&v25) )
        goto LABEL_22;
      v17.x = -v20[0];
      v17.y = -v20[1];
      if ( RGNOBJ::bOffset((RGNOBJ *)&v28, &v17) )
      {
        if ( (*(_DWORD *)(v15 + 136) & 0x20) != 0 )
          RGNOBJ::vScale(&v28, *(_QWORD *)(v15 + 128));
        *(_QWORD *)(v16 + 88) = v28;
        goto LABEL_21;
      }
    }
    else
    {
      if ( !*(_QWORD *)(v16 + 88) )
      {
LABEL_22:
        if ( v16 != -256 )
          GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v16 + 256));
        if ( (*(_DWORD *)(v16 + 252) & 1) == 0 || !a4 )
          vSpDwmFlushSpriteClipRgnChange((struct SFMLOGICALSURFACE *)v16);
        if ( v15 != -88 )
          GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 88));
        if ( v19 )
          _InterlockedDecrement16((volatile signed __int16 *)(v19 + 12));
        goto LABEL_30;
      }
      v28 = *(_QWORD *)(v16 + 88);
    }
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v28);
    *(_QWORD *)(v16 + 88) = 0;
LABEL_21:
    *(_DWORD *)(v16 + 252) |= 0x20u;
    goto LABEL_22;
  }
LABEL_30:
  v19 = 0;
  PopThreadGuardedObject(v18);
  if ( !v27 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v25);
  if ( v25 )
    _InterlockedDecrement16((volatile signed __int16 *)(v25 + 12));
  PopThreadGuardedObject(v26);
LABEL_35:
  ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON((ENTER_DWM_CRIT_COMMON *)&v21);
}

```

## disassembly

```asm
0x1401213e0  push    rbp
0x1401213e2  push    rbx
0x1401213e3  push    rsi
0x1401213e4  push    rdi
0x1401213e5  push    r14
0x1401213e7  push    r15
0x1401213e9  lea     rbp, [rsp-2Fh]
0x1401213ee  sub     rsp, 0C8h
0x1401213f5  mov     r15d, r9d
0x1401213f8  mov     rsi, r8
0x1401213fb  mov     r14, rdx
0x1401213fe  mov     rbx, rcx
0x140121401  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140121408  nop     dword ptr [rax+rax+00h]
0x14012140d  xor     r9d, r9d; int
0x140121410  mov     [rbp+57h+var_90], rbx
0x140121414  xor     r8d, r8d; int
0x140121417  lea     rcx, [rbp+57h+var_88]; this
0x14012141b  mov     rdi, rax
0x14012141e  call    ??0DWMSPRITELOCK@@QEAA@AEAVPDEVOBJ@@HH@Z; DWMSPRITELOCK::DWMSPRITELOCK(PDEVOBJ &,int,int)
0x140121423  mov     rcx, [rdi]
0x140121426  add     rcx, 208h
0x14012142d  mov     [rbp+57h+var_78], 0
0x140121431  mov     [rbp+57h+var_80], rcx
0x140121435  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14012143c  nop     dword ptr [rax+rax+00h]
0x140121441  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x140121446  call    IsDwmActive
0x14012144b  test    eax, eax
0x14012144d  jz      loc_14012166E
0x140121453  xor     r9d, r9d
0x140121456  lea     rcx, [rbp+57h+var_70]
0x14012145a  xor     r8d, r8d
0x14012145d  mov     rdx, rsi
0x140121460  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140121467  nop     dword ptr [rax+rax+00h]
0x14012146c  xorps   xmm0, xmm0
0x14012146f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x140121476  lea     rdx, [rbp+57h+var_C8]
0x14012147a  lea     rcx, [rbp+57h+var_C8]
0x14012147e  movups  [rbp+57h+var_C8], xmm0
0x140121482  movups  [rbp+57h+var_B8], xmm0
0x140121486  call    cs:__imp_PushThreadGuardedObject
0x14012148d  nop     dword ptr [rax+rax+00h]
0x140121492  mov     rcx, r14; HWND
0x140121495  mov     [rbp+57h+var_A8], 0
0x14012149d  call    ?hspLookupWindow@DWMSPRITEREF@@SAPEAUHSPRITE__@@PEAUHWND__@@@Z; DWMSPRITEREF::hspLookupWindow(HWND__ *)
0x1401214a2  mov     rbx, rax
0x1401214a5  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401214ac  nop     dword ptr [rax+rax+00h]
0x1401214b1  test    rbx, rbx
0x1401214b4  jz      short loc_1401214D2
0x1401214b6  xor     r9d, r9d
0x1401214b9  mov     r8b, 0Fh
0x1401214bc  mov     rdx, rbx
0x1401214bf  mov     rcx, rax
0x1401214c2  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1401214c9  nop     dword ptr [rax+rax+00h]
0x1401214ce  mov     [rbp+57h+var_A8], rax
0x1401214d2  mov     rdi, [rbp+57h+var_A8]
0x1401214d6  test    rdi, rdi
0x1401214d9  jz      loc_140121622
0x1401214df  lea     rsi, [rdi+58h]
0x1401214e3  test    rsi, rsi
0x1401214e6  jz      short loc_1401214F7
0x1401214e8  mov     rcx, rsi
0x1401214eb  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1401214f2  nop     dword ptr [rax+rax+00h]
0x1401214f7  mov     rbx, [rdi+90h]
0x1401214fe  lea     r14, [rbx+100h]
0x140121505  test    r14, r14
0x140121508  jz      short loc_140121519
0x14012150a  mov     rcx, r14
0x14012150d  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x140121514  nop     dword ptr [rax+rax+00h]
0x140121519  cmp     [rbp+57h+var_70], 0
0x14012151e  jz      loc_1401215A9
0x140121524  mov     rcx, [rdi+28h]
0x140121528  lea     rdx, [rbp+57h+var_A0]
0x14012152c  call    UserGetWindowRect
0x140121531  test    eax, eax
0x140121533  jz      short loc_1401215A9
0x140121535  cmp     qword ptr [rbx+58h], 0
0x14012153a  jz      loc_140121695
0x140121540  mov     rax, [rbx+58h]
0x140121544  test    rax, rax
0x140121547  jz      loc_1401215D5
0x14012154d  lea     rdx, [rbp+57h+var_70]
0x140121551  mov     [rbp+57h+arg_0], rax
0x140121555  lea     rcx, [rbp+57h+arg_0]
0x140121559  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x140121560  nop     dword ptr [rax+rax+00h]
0x140121565  test    eax, eax
0x140121567  jz      short loc_1401215D5
0x140121569  mov     eax, [rbp+57h+var_A0]
0x14012156c  lea     rdx, [rbp+57h+var_D0]
0x140121570  neg     eax
0x140121572  lea     rcx, [rbp+57h+arg_0]
0x140121576  mov     [rbp+57h+var_D0], eax
0x140121579  mov     eax, [rbp+57h+var_9C]
0x14012157c  neg     eax
0x14012157e  mov     [rbp+57h+var_CC], eax
0x140121581  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x140121588  nop     dword ptr [rax+rax+00h]
0x14012158d  test    eax, eax
0x14012158f  jz      short loc_1401215B6
0x140121591  mov     eax, [rdi+88h]
0x140121597  test    al, 20h
0x140121599  jnz     loc_1401216BB
0x14012159f  mov     rax, [rbp+57h+arg_0]
0x1401215a3  mov     [rbx+58h], rax
0x1401215a7  jmp     short loc_1401215CE
0x1401215a9  mov     rax, [rbx+58h]
0x1401215ad  test    rax, rax
0x1401215b0  jz      short loc_1401215D5
0x1401215b2  mov     [rbp+57h+arg_0], rax
0x1401215b6  lea     rcx, [rbp+57h+arg_0]
0x1401215ba  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401215c1  nop     dword ptr [rax+rax+00h]
0x1401215c6  mov     qword ptr [rbx+58h], 0
0x1401215ce  or      dword ptr [rbx+0FCh], 20h
0x1401215d5  test    r14, r14
0x1401215d8  jz      short loc_1401215E9
0x1401215da  mov     rcx, r14
0x1401215dd  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1401215e4  nop     dword ptr [rax+rax+00h]
0x1401215e9  mov     eax, [rbx+0FCh]
0x1401215ef  test    al, 1
0x1401215f1  jz      loc_140121688
0x1401215f7  test    r15d, r15d
0x1401215fa  jz      loc_140121688
0x140121600  test    rsi, rsi
0x140121603  jz      short loc_140121614
0x140121605  mov     rcx, rsi
0x140121608  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x14012160f  nop     dword ptr [rax+rax+00h]
0x140121614  mov     rdi, [rbp+57h+var_A8]
0x140121618  test    rdi, rdi
0x14012161b  jz      short loc_140121622
0x14012161d  lock dec word ptr [rdi+0Ch]
0x140121622  lea     rcx, [rbp+57h+var_C8]
0x140121626  mov     [rbp+57h+var_A8], 0
0x14012162e  call    cs:__imp_PopThreadGuardedObject
0x140121635  nop     dword ptr [rax+rax+00h]
0x14012163a  cmp     [rbp+57h+var_40], 0
0x14012163e  jnz     short loc_140121650
0x140121640  lea     rcx, [rbp+57h+var_70]
0x140121644  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14012164b  nop     dword ptr [rax+rax+00h]
0x140121650  mov     rax, [rbp+57h+var_70]
0x140121654  test    rax, rax
0x140121657  jz      short loc_14012165E
0x140121659  lock dec word ptr [rax+0Ch]
0x14012165e  lea     rcx, [rbp+57h+var_68]
0x140121662  call    cs:__imp_PopThreadGuardedObject
0x140121669  nop     dword ptr [rax+rax+00h]
0x14012166e  lea     rcx, [rbp+57h+var_90]; this
0x140121672  call    ??1ENTER_DWM_CRIT_COMMON@@QEAA@XZ; ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON(void)
0x140121677  add     rsp, 0C8h
0x14012167e  pop     r15
0x140121680  pop     r14
0x140121682  pop     rdi
0x140121683  pop     rsi
0x140121684  pop     rbx
0x140121685  pop     rbp
0x140121686  retn
0x140121688  mov     rcx, rbx; struct SFMLOGICALSURFACE *
0x14012168b  call    ?vSpDwmFlushSpriteClipRgnChange@@YAXPEAVSFMLOGICALSURFACE@@@Z; vSpDwmFlushSpriteClipRgnChange(SFMLOGICALSURFACE *)
0x140121690  jmp     loc_140121600
0x140121695  lea     rcx, [rbp+57h+arg_0]
0x140121699  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1401216a0  nop     dword ptr [rax+rax+00h]
0x1401216a5  mov     rax, [rbp+57h+arg_0]
0x1401216a9  test    rax, rax
0x1401216ac  jz      loc_140121540
0x1401216b2  mov     [rbx+58h], rax
0x1401216b6  jmp     loc_140121540
0x1401216bb  mov     rdx, [rdi+80h]
0x1401216c2  lea     rcx, [rbp+57h+arg_0]
0x1401216c6  call    cs:__imp_?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z; RGNOBJ::vScale(POINTFL)
0x1401216cd  nop     dword ptr [rax+rax+00h]
0x1401216d2  jmp     loc_14012159F
```
