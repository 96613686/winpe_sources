# GreUpdateSpriteClipRgn

- ea: `0x1401b2680`
- end: `0x1401b2977`
- name: `GreUpdateSpriteClipRgn`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002da38`
- `0x140059f84`

## callees

- `0x1400875b8`
- `0x14008bec8`
- `0x140090228`
- `0x140090290`
- `0x1400910f4`
- `0x140093570`
- `0x1401b2680`
- `0x1401b2980`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b26a1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b2745`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b26a1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401b2745`
- `win32kbase!PopThreadGuardedObject` at `0x1401b28ce`
- `win32kbase!PopThreadGuardedObject` at `0x1401b2902`
- `win32kbase!PopThreadGuardedObject` at `0x1401b28ce`
- `win32kbase!PopThreadGuardedObject` at `0x1401b2902`
- `win32kbase!PushThreadGuardedObject` at `0x1401b2726`
- `win32kbase!PushThreadGuardedObject` at `0x1401b2726`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401b285a`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1401b285a`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401b2939`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1401b2939`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401b287d`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401b28a8`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401b287d`
- `win32kbase!GreReleasePushLockExclusive` at `0x1401b28a8`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401b278b`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401b27ad`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401b278b`
- `win32kbase!GreAcquirePushLockExclusive` at `0x1401b27ad`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401b27f9`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x1401b27f9`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1401b26d5`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1401b26d5`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1401b2762`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1401b2762`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401b2821`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x1401b2821`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1401b2700`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x1401b2700`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x1401b28e4`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x1401b28e4`
- `win32kbase!?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z` at `0x1401b2966`
- `win32kbase!?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z` at `0x1401b2966`

## pseudocode

```c
void __fastcall GreUpdateSpriteClipRgn(Gre::Base *a1, HWND a2, HRGN a3, int a4)
{
  struct Gre::Base::SESSION_GLOBALS *v7; // rdi
  struct PDEVOBJ *v8; // rdx
  HSEMAPHORE v9; // rcx
  HSPRITE v10; // rbx
  Gre::Base *v11; // rcx
  struct Gre::Base::SESSION_GLOBALS *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rbx
  struct _POINTL v16; // [rsp+20h] [rbp-79h] BYREF
  _OWORD v17[2]; // [rsp+28h] [rbp-71h] BYREF
  __int64 v18; // [rsp+48h] [rbp-51h]
  _DWORD v19[4]; // [rsp+50h] [rbp-49h] BYREF
  Gre::Base *v20; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-31h] BYREF
  HSEMAPHORE v22; // [rsp+70h] [rbp-29h]
  char v23; // [rsp+78h] [rbp-21h]
  __int64 v24; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v25[40]; // [rsp+88h] [rbp-11h] BYREF
  int v26; // [rsp+B0h] [rbp+17h]
  __int64 v27; // [rsp+100h] [rbp+67h] BYREF

  v20 = a1;
  v7 = Gre::Base::Globals(a1);
  DWMSPRITELOCK::DWMSPRITELOCK((DWMSPRITELOCK *)v21, v8, 0, 0);
  v9 = (HSEMAPHORE)(*(_QWORD *)v7 + 520LL);
  v23 = 0;
  v22 = v9;
  GreAcquireSemaphoreInternal(v9);
  GrepAcquireLockValidate<7>();
  if ( !(unsigned int)IsDwmActive() )
    goto LABEL_35;
  RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v24, a3, 0, 0);
  memset(v17, 0, sizeof(v17));
  PushThreadGuardedObject(
    v17,
    v17,
    UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic);
  v18 = 0;
  v10 = DWMSPRITEREF::hspLookupWindow(a2);
  v12 = Gre::Base::Globals(v11);
  if ( v10 )
  {
    LOBYTE(v13) = 15;
    v18 = HmgLock(v12, v10, v13);
  }
  v14 = v18;
  if ( v18 )
  {
    if ( v18 != -88 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v18 + 88));
    v15 = *(_QWORD *)(v14 + 144);
    if ( v15 != -256 )
      GreAcquirePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 256));
    if ( v24 && (unsigned int)UserGetWindowRect(*(_QWORD *)(v14 + 40), v19) )
    {
      if ( !*(_QWORD *)(v15 + 88) )
      {
        RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v27);
        if ( v27 )
          *(_QWORD *)(v15 + 88) = v27;
      }
      if ( !*(_QWORD *)(v15 + 88) )
        goto LABEL_22;
      v27 = *(_QWORD *)(v15 + 88);
      if ( !RGNOBJ::bCopy((RGNOBJ *)&v27, (struct RGNOBJ *)&v24) )
        goto LABEL_22;
      v16.x = -v19[0];
      v16.y = -v19[1];
      if ( RGNOBJ::bOffset((RGNOBJ *)&v27, &v16) )
      {
        if ( (*(_DWORD *)(v14 + 136) & 0x20) != 0 )
          RGNOBJ::vScale(&v27, *(_QWORD *)(v14 + 128));
        *(_QWORD *)(v15 + 88) = v27;
        goto LABEL_21;
      }
    }
    else
    {
      if ( !*(_QWORD *)(v15 + 88) )
      {
LABEL_22:
        if ( v15 != -256 )
          GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v15 + 256));
        if ( (*(_DWORD *)(v15 + 252) & 1) == 0 || !a4 )
          vSpDwmFlushSpriteClipRgnChange((struct SFMLOGICALSURFACE *)v15);
        if ( v14 != -88 )
          GreReleasePushLockExclusive((struct W32_PUSH_LOCK *)(v14 + 88));
        if ( v18 )
          _InterlockedDecrement16((volatile signed __int16 *)(v18 + 12));
        goto LABEL_30;
      }
      v27 = *(_QWORD *)(v15 + 88);
    }
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v27);
    *(_QWORD *)(v15 + 88) = 0;
LABEL_21:
    *(_DWORD *)(v15 + 252) |= 0x20u;
    goto LABEL_22;
  }
LABEL_30:
  v18 = 0;
  PopThreadGuardedObject(v17);
  if ( !v26 )
    RGNOBJ::UpdateUserRgn((RGNOBJ *)&v24);
  if ( v24 )
    _InterlockedDecrement16((volatile signed __int16 *)(v24 + 12));
  PopThreadGuardedObject(v25);
LABEL_35:
  ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON((ENTER_DWM_CRIT_COMMON *)&v20);
}

```

## disassembly

```asm
0x1401b2680  push    rbp
0x1401b2682  push    rbx
0x1401b2683  push    rsi
0x1401b2684  push    rdi
0x1401b2685  push    r14
0x1401b2687  push    r15
0x1401b2689  lea     rbp, [rsp-2Fh]
0x1401b268e  sub     rsp, 0C8h
0x1401b2695  mov     r15d, r9d
0x1401b2698  mov     rsi, r8
0x1401b269b  mov     r14, rdx
0x1401b269e  mov     rbx, rcx
0x1401b26a1  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401b26a8  nop     dword ptr [rax+rax+00h]
0x1401b26ad  xor     r9d, r9d; int
0x1401b26b0  mov     [rbp+57h+var_90], rbx
0x1401b26b4  xor     r8d, r8d; int
0x1401b26b7  lea     rcx, [rbp+57h+var_88]; this
0x1401b26bb  mov     rdi, rax
0x1401b26be  call    ??0DWMSPRITELOCK@@QEAA@AEAVPDEVOBJ@@HH@Z; DWMSPRITELOCK::DWMSPRITELOCK(PDEVOBJ &,int,int)
0x1401b26c3  mov     rcx, [rdi]
0x1401b26c6  add     rcx, 208h
0x1401b26cd  mov     [rbp+57h+var_78], 0
0x1401b26d1  mov     [rbp+57h+var_80], rcx
0x1401b26d5  call    cs:__imp_?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1401b26dc  nop     dword ptr [rax+rax+00h]
0x1401b26e1  call    ??$GrepAcquireLockValidate@$06@@YAXXZ; GrepAcquireLockValidate<7>(void)
0x1401b26e6  call    IsDwmActive
0x1401b26eb  test    eax, eax
0x1401b26ed  jz      loc_1401B290E
0x1401b26f3  xor     r9d, r9d
0x1401b26f6  lea     rcx, [rbp+57h+var_70]
0x1401b26fa  xor     r8d, r8d
0x1401b26fd  mov     rdx, rsi
0x1401b2700  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x1401b2707  nop     dword ptr [rax+rax+00h]
0x1401b270c  xorps   xmm0, xmm0
0x1401b270f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDWMSPRITEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DWMSPRITEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x1401b2716  lea     rdx, [rbp+57h+var_C8]
0x1401b271a  lea     rcx, [rbp+57h+var_C8]
0x1401b271e  movups  [rbp+57h+var_C8], xmm0
0x1401b2722  movups  [rbp+57h+var_B8], xmm0
0x1401b2726  call    cs:__imp_PushThreadGuardedObject
0x1401b272d  nop     dword ptr [rax+rax+00h]
0x1401b2732  mov     rcx, r14; HWND
0x1401b2735  mov     [rbp+57h+var_A8], 0
0x1401b273d  call    ?hspLookupWindow@DWMSPRITEREF@@SAPEAUHSPRITE__@@PEAUHWND__@@@Z; DWMSPRITEREF::hspLookupWindow(HWND__ *)
0x1401b2742  mov     rbx, rax
0x1401b2745  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401b274c  nop     dword ptr [rax+rax+00h]
0x1401b2751  test    rbx, rbx
0x1401b2754  jz      short loc_1401B2772
0x1401b2756  xor     r9d, r9d
0x1401b2759  mov     r8b, 0Fh
0x1401b275c  mov     rdx, rbx
0x1401b275f  mov     rcx, rax
0x1401b2762  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1401b2769  nop     dword ptr [rax+rax+00h]
0x1401b276e  mov     [rbp+57h+var_A8], rax
0x1401b2772  mov     rdi, [rbp+57h+var_A8]
0x1401b2776  test    rdi, rdi
0x1401b2779  jz      loc_1401B28C2
0x1401b277f  lea     rsi, [rdi+58h]
0x1401b2783  test    rsi, rsi
0x1401b2786  jz      short loc_1401B2797
0x1401b2788  mov     rcx, rsi
0x1401b278b  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1401b2792  nop     dword ptr [rax+rax+00h]
0x1401b2797  mov     rbx, [rdi+90h]
0x1401b279e  lea     r14, [rbx+100h]
0x1401b27a5  test    r14, r14
0x1401b27a8  jz      short loc_1401B27B9
0x1401b27aa  mov     rcx, r14
0x1401b27ad  call    cs:__imp_?GreAcquirePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreAcquirePushLockExclusive(W32_PUSH_LOCK *)
0x1401b27b4  nop     dword ptr [rax+rax+00h]
0x1401b27b9  cmp     [rbp+57h+var_70], 0
0x1401b27be  jz      loc_1401B2849
0x1401b27c4  mov     rcx, [rdi+28h]
0x1401b27c8  lea     rdx, [rbp+57h+var_A0]
0x1401b27cc  call    UserGetWindowRect
0x1401b27d1  test    eax, eax
0x1401b27d3  jz      short loc_1401B2849
0x1401b27d5  cmp     qword ptr [rbx+58h], 0
0x1401b27da  jz      loc_1401B2935
0x1401b27e0  mov     rax, [rbx+58h]
0x1401b27e4  test    rax, rax
0x1401b27e7  jz      loc_1401B2875
0x1401b27ed  lea     rdx, [rbp+57h+var_70]
0x1401b27f1  mov     [rbp+57h+arg_0], rax
0x1401b27f5  lea     rcx, [rbp+57h+arg_0]
0x1401b27f9  call    cs:__imp_?bCopy@RGNOBJ@@QEAAHAEAV1@@Z; RGNOBJ::bCopy(RGNOBJ &)
0x1401b2800  nop     dword ptr [rax+rax+00h]
0x1401b2805  test    eax, eax
0x1401b2807  jz      short loc_1401B2875
0x1401b2809  mov     eax, [rbp+57h+var_A0]
0x1401b280c  lea     rdx, [rbp+57h+var_D0]
0x1401b2810  neg     eax
0x1401b2812  lea     rcx, [rbp+57h+arg_0]
0x1401b2816  mov     [rbp+57h+var_D0], eax
0x1401b2819  mov     eax, [rbp+57h+var_9C]
0x1401b281c  neg     eax
0x1401b281e  mov     [rbp+57h+var_CC], eax
0x1401b2821  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x1401b2828  nop     dword ptr [rax+rax+00h]
0x1401b282d  test    eax, eax
0x1401b282f  jz      short loc_1401B2856
0x1401b2831  mov     eax, [rdi+88h]
0x1401b2837  test    al, 20h
0x1401b2839  jnz     loc_1401B295B
0x1401b283f  mov     rax, [rbp+57h+arg_0]
0x1401b2843  mov     [rbx+58h], rax
0x1401b2847  jmp     short loc_1401B286E
0x1401b2849  mov     rax, [rbx+58h]
0x1401b284d  test    rax, rax
0x1401b2850  jz      short loc_1401B2875
0x1401b2852  mov     [rbp+57h+arg_0], rax
0x1401b2856  lea     rcx, [rbp+57h+arg_0]
0x1401b285a  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1401b2861  nop     dword ptr [rax+rax+00h]
0x1401b2866  mov     qword ptr [rbx+58h], 0
0x1401b286e  or      dword ptr [rbx+0FCh], 20h
0x1401b2875  test    r14, r14
0x1401b2878  jz      short loc_1401B2889
0x1401b287a  mov     rcx, r14
0x1401b287d  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1401b2884  nop     dword ptr [rax+rax+00h]
0x1401b2889  mov     eax, [rbx+0FCh]
0x1401b288f  test    al, 1
0x1401b2891  jz      loc_1401B2928
0x1401b2897  test    r15d, r15d
0x1401b289a  jz      loc_1401B2928
0x1401b28a0  test    rsi, rsi
0x1401b28a3  jz      short loc_1401B28B4
0x1401b28a5  mov     rcx, rsi
0x1401b28a8  call    cs:__imp_?GreReleasePushLockExclusive@@YAXPEAVW32_PUSH_LOCK@@@Z; GreReleasePushLockExclusive(W32_PUSH_LOCK *)
0x1401b28af  nop     dword ptr [rax+rax+00h]
0x1401b28b4  mov     rdi, [rbp+57h+var_A8]
0x1401b28b8  test    rdi, rdi
0x1401b28bb  jz      short loc_1401B28C2
0x1401b28bd  lock dec word ptr [rdi+0Ch]
0x1401b28c2  lea     rcx, [rbp+57h+var_C8]
0x1401b28c6  mov     [rbp+57h+var_A8], 0
0x1401b28ce  call    cs:__imp_PopThreadGuardedObject
0x1401b28d5  nop     dword ptr [rax+rax+00h]
0x1401b28da  cmp     [rbp+57h+var_40], 0
0x1401b28de  jnz     short loc_1401B28F0
0x1401b28e0  lea     rcx, [rbp+57h+var_70]
0x1401b28e4  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x1401b28eb  nop     dword ptr [rax+rax+00h]
0x1401b28f0  mov     rax, [rbp+57h+var_70]
0x1401b28f4  test    rax, rax
0x1401b28f7  jz      short loc_1401B28FE
0x1401b28f9  lock dec word ptr [rax+0Ch]
0x1401b28fe  lea     rcx, [rbp+57h+var_68]
0x1401b2902  call    cs:__imp_PopThreadGuardedObject
0x1401b2909  nop     dword ptr [rax+rax+00h]
0x1401b290e  lea     rcx, [rbp+57h+var_90]; this
0x1401b2912  call    ??1ENTER_DWM_CRIT_COMMON@@QEAA@XZ; ENTER_DWM_CRIT_COMMON::~ENTER_DWM_CRIT_COMMON(void)
0x1401b2917  add     rsp, 0C8h
0x1401b291e  pop     r15
0x1401b2920  pop     r14
0x1401b2922  pop     rdi
0x1401b2923  pop     rsi
0x1401b2924  pop     rbx
0x1401b2925  pop     rbp
0x1401b2926  retn
0x1401b2928  mov     rcx, rbx; struct SFMLOGICALSURFACE *
0x1401b292b  call    ?vSpDwmFlushSpriteClipRgnChange@@YAXPEAVSFMLOGICALSURFACE@@@Z; vSpDwmFlushSpriteClipRgnChange(SFMLOGICALSURFACE *)
0x1401b2930  jmp     loc_1401B28A0
0x1401b2935  lea     rcx, [rbp+57h+arg_0]
0x1401b2939  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1401b2940  nop     dword ptr [rax+rax+00h]
0x1401b2945  mov     rax, [rbp+57h+arg_0]
0x1401b2949  test    rax, rax
0x1401b294c  jz      loc_1401B27E0
0x1401b2952  mov     [rbx+58h], rax
0x1401b2956  jmp     loc_1401B27E0
0x1401b295b  mov     rdx, [rdi+80h]
0x1401b2962  lea     rcx, [rbp+57h+arg_0]
0x1401b2966  call    cs:__imp_?vScale@RGNOBJ@@QEAAXVPOINTFL@@@Z; RGNOBJ::vScale(POINTFL)
0x1401b296d  nop     dword ptr [rax+rax+00h]
0x1401b2972  jmp     loc_1401B283F
```
