# GreGetRandomRgn

- ea: `0x14006a4c0`
- end: `0x14006aa0f`
- name: `GreGetRandomRgn`
- size: `1359`
- prototype: `__int64 __fastcall(Gre::Base *, HRGN, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140037b08`
- `0x14006a450`
- `0x1401af650`
- `0x1401efb90`

## callees

- `0x140038760`
- `0x1400539b0`
- `0x14005b820`
- `0x14005d010`
- `0x140060284`
- `0x14006a4c0`
- `0x14006bd2c`
- `0x1400876f0`
- `0x1400a4e80`
- `0x140154d18`
- `0x1401d036c`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006a4f4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14006a4f4`
- `win32kbase!PopThreadGuardedObject` at `0x14006a6dc`
- `win32kbase!PopThreadGuardedObject` at `0x14006a6dc`
- `win32kbase!PushThreadGuardedObject` at `0x14006a52f`
- `win32kbase!PushThreadGuardedObject` at `0x14006a5bf`
- `win32kbase!PushThreadGuardedObject` at `0x14006a52f`
- `win32kbase!PushThreadGuardedObject` at `0x14006a5bf`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14006a950`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14006a950`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14006a93a`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14006a93a`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14006a54e`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14006a54e`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x14006a801`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x14006a8bb`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x14006a801`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x14006a8bb`
- `win32kbase!?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ` at `0x14006a7b9`
- `win32kbase!?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ` at `0x14006a86d`
- `win32kbase!?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ` at `0x14006a7b9`
- `win32kbase!?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ` at `0x14006a86d`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14006a8f1`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14006a8f1`
- `win32kbase!EngSetLastError` at `0x14006a71f`
- `win32kbase!EngSetLastError` at `0x14006a71f`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14006a61c`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14006a61c`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14006a63e`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x14006a63e`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a6ba`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a739`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a77a`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a819`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a90d`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a6ba`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a739`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a77a`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a819`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x14006a90d`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14006a9d5`
- `win32kbase!?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z` at `0x14006a9d5`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a694`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a7e9`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a89d`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a694`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a7e9`
- `win32kbase!?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z` at `0x14006a89d`

## pseudocode

```c
__int64 __fastcall GreGetRandomRgn(Gre::Base *a1, HRGN a2, int a3)
{
  int v6; // esi
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // edi
  struct _POINTL v15; // rcx
  int v16; // eax
  int v17; // edi
  int v19; // edi
  int v20; // edi
  GreInnermostPushLock *v21; // rsi
  GreInnermostPushLock *v22; // rcx
  GreInnermostPushLock *v23; // r14
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v28[40]; // [rsp+28h] [rbp-D8h] BYREF
  int v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  DC *v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  struct Gre::Base::SESSION_GLOBALS *v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  _OWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v36[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+D0h] [rbp-30h] BYREF
  HDC v39[20]; // [rsp+E0h] [rbp-20h] BYREF
  struct _POINTL v40; // [rsp+1C8h] [rbp+C8h] BYREF

  v34 = 0;
  v33 = Gre::Base::Globals(a1);
  v31 = 0;
  v32 = 0;
  memset(v35, 0, sizeof(v35));
  PushThreadGuardedObject(
    v35,
    &v31,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  v6 = 1;
  LOBYTE(v7) = 1;
  v8 = HmgLock(v33, a1, v7, 0);
  v10 = -1;
  v31 = (DC *)v8;
  if ( v8 )
  {
    if ( *(_DWORD *)(v8 + 2136) )
    {
      _InterlockedAdd16((volatile signed __int16 *)(v8 + 12), 0xFFFFu);
      v31 = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(v9) != 1 )
  {
    GrepAuditBehaviorRestrictionViolations(1);
  }
  if ( v31 )
  {
    if ( (unsigned int)DCOBJ::SaveAttributes((DCOBJ *)&v31) )
    {
      if ( (*((_DWORD *)v31 + 130) & 4) != 0 )
        DC::vMarkTransformDirty(v31);
    }
    else
    {
      _InterlockedAdd16((volatile signed __int16 *)v31 + 6, 0xFFFFu);
      v31 = 0;
    }
  }
  memset(v36, 0, sizeof(v36));
  PushThreadGuardedObject(v36, &v31, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v37 = 1;
  if ( !v31 )
    goto LABEL_29;
  if ( *((_WORD *)v31 + 6) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11);
  if ( *((_WORD *)v31 + 6) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v31);
  if ( !v31 )
  {
LABEL_29:
    EngSetLastError(6u);
    goto LABEL_28;
  }
  DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v39);
  if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v39, (struct XDCOBJ *)&v31, 1) )
  {
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v27, a2, 0, 0);
    v13 = v27;
    if ( !v27 )
    {
      if ( !v29 )
      {
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v27);
        if ( v27 )
          _InterlockedAdd16((volatile signed __int16 *)(v27 + 12), 0xFFFFu);
      }
      goto LABEL_26;
    }
    if ( a3 == 4 )
    {
      if ( (*((_DWORD *)v31 + 9) & 0x4000) != 0 )
      {
        v23 = (DC *)((char *)v31 + 1112);
        GreInnermostPushLock::AcquireLockShared((DC *)((char *)v31 + 1112));
        v30 = *((_QWORD *)v31 + 142);
        if ( v30 )
        {
          v24 = RGNOBJAPI::bCopy((RGNOBJAPI *)&v27, (struct RGNOBJ *)&v30);
          v17 = v24 != 0 ? 1 : -1;
          if ( v24 )
          {
            GreInnermostPushLock::ReleaseLock(v23);
            v40 = 0;
            if ( !(unsigned int)UserGetRedirectedWindowOrigin((__int64)a1, (__int64)&v40)
              || !RGNOBJ::bOffset((RGNOBJ *)&v27, &v40) )
            {
              v6 = -1;
            }
            if ( !v29 )
              RGNOBJ::UpdateUserRgn((RGNOBJ *)&v27);
            if ( v27 )
              _InterlockedAdd16((volatile signed __int16 *)(v27 + 12), 0xFFFFu);
            v10 = v6;
            goto LABEL_26;
          }
        }
        else
        {
          v17 = 0;
        }
        v22 = v23;
        goto LABEL_45;
      }
LABEL_42:
      v21 = (DC *)((char *)v31 + 1112);
      GreInnermostPushLock::AcquireLockShared((DC *)((char *)v31 + 1112));
      v40 = (struct _POINTL)*((_QWORD *)v31 + 142);
      if ( v40 )
        v17 = RGNOBJAPI::bCopy((RGNOBJAPI *)&v27, (struct RGNOBJ *)&v40) != 0 ? 1 : -1;
      else
        v17 = 0;
      v22 = v21;
LABEL_45:
      GreInnermostPushLock::ReleaseLock(v22);
      if ( !v29 )
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v27);
      if ( v27 )
        _InterlockedAdd16((volatile signed __int16 *)(v27 + 12), 0xFFFFu);
      goto LABEL_25;
    }
    v14 = a3 - 1;
    if ( !v14 )
    {
      v15 = (struct _POINTL)*((_QWORD *)v31 + 20);
LABEL_19:
      v40 = v15;
      if ( v15 )
      {
        v16 = RGNOBJAPI::bCopy((RGNOBJAPI *)&v27, (struct RGNOBJ *)&v40);
        v13 = v27;
        v17 = v16 != 0 ? 1 : -1;
      }
      else
      {
        v17 = 0;
      }
      if ( !v29 )
      {
        RGNOBJ::UpdateUserRgn((RGNOBJ *)&v27);
        v13 = v27;
      }
      if ( v13 )
        _InterlockedAdd16((volatile signed __int16 *)(v13 + 12), 0xFFFFu);
LABEL_25:
      v10 = v17;
LABEL_26:
      PopThreadGuardedObject(v28);
      goto LABEL_27;
    }
    v19 = v14 - 1;
    if ( !v19 )
    {
      v15 = (struct _POINTL)*((_QWORD *)v31 + 21);
      goto LABEL_19;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( (unsigned int)(v20 - 1) >= 2 )
      {
        if ( !v29 )
        {
          RGNOBJ::UpdateUserRgn((RGNOBJ *)&v27);
          v13 = v27;
        }
        if ( v13 )
          _InterlockedAdd16((volatile signed __int16 *)(v13 + 12), 0xFFFFu);
        v10 = 0;
        goto LABEL_26;
      }
      goto LABEL_42;
    }
    v25 = *((_QWORD *)v31 + 21);
    v26 = *((_QWORD *)v31 + 20);
    if ( v25 )
    {
      if ( v26 )
      {
        v38 = *((_QWORD *)v31 + 20);
        v30 = v25;
        v10 = RGNOBJAPI::iCombine((RGNOBJAPI *)&v27, (struct RGNOBJ *)&v38, (struct RGNOBJ *)&v30, 1) != 0 ? 1 : -1;
LABEL_73:
        RGNOBJAPI::~RGNOBJAPI((RGNOBJAPI *)&v27);
        goto LABEL_27;
      }
    }
    else if ( v26 )
    {
      v25 = *((_QWORD *)v31 + 20);
    }
    v10 = GreGetRandomRgn_::_2_::_lambda_1_::operator()(v26, &v27, v25);
    goto LABEL_73;
  }
LABEL_27:
  DEVLOCKOBJ::~DEVLOCKOBJ(v39);
LABEL_28:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v31);
  return v10;
}

```

## disassembly

```asm
0x14006a4c0  mov     [rsp-8+arg_0], rbx
0x14006a4c5  mov     [rsp-8+arg_8], rsi
0x14006a4ca  push    rbp
0x14006a4cb  push    rdi
0x14006a4cc  push    r12
0x14006a4ce  push    r14
0x14006a4d0  push    r15
0x14006a4d2  lea     rbp, [rsp-80h]
0x14006a4d7  sub     rsp, 180h
0x14006a4de  xor     r12d, r12d
0x14006a4e1  mov     edi, r8d
0x14006a4e4  mov     [rsp+1A0h+var_140], r12
0x14006a4e9  mov     r14, rdx
0x14006a4ec  mov     [rsp+1A0h+var_138], r12d
0x14006a4f1  mov     r15, rcx
0x14006a4f4  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14006a4fb  nop     dword ptr [rax+rax+00h]
0x14006a500  xorps   xmm0, xmm0
0x14006a503  mov     [rsp+1A0h+var_128], r12
0x14006a508  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14006a50f  mov     [rsp+1A0h+var_130], rax
0x14006a514  lea     rdx, [rsp+1A0h+var_140]
0x14006a519  mov     [rsp+1A0h+var_140], r12
0x14006a51e  lea     rcx, [rbp+0A0h+var_120]
0x14006a522  mov     [rsp+1A0h+var_138], r12d
0x14006a527  movups  [rbp+0A0h+var_120], xmm0
0x14006a52b  movups  [rbp+0A0h+var_110], xmm0
0x14006a52f  call    cs:__imp_PushThreadGuardedObject
0x14006a536  nop     dword ptr [rax+rax+00h]
0x14006a53b  mov     rcx, [rsp+1A0h+var_130]
0x14006a540  lea     esi, [r12+1]
0x14006a545  mov     r8b, sil
0x14006a548  xor     r9d, r9d
0x14006a54b  mov     rdx, r15
0x14006a54e  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14006a555  nop     dword ptr [rax+rax+00h]
0x14006a55a  or      ebx, 0FFFFFFFFh
0x14006a55d  mov     [rsp+1A0h+var_140], rax
0x14006a562  test    rax, rax
0x14006a565  jz      loc_14006A93A
0x14006a56b  cmp     [rax+858h], r12d
0x14006a572  jnz     loc_14006A980
0x14006a578  cmp     [rsp+1A0h+var_140], r12
0x14006a57d  jz      short loc_14006A5A4
0x14006a57f  lea     rcx, [rsp+1A0h+var_140]; this
0x14006a584  call    ?SaveAttributes@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributes(void)
0x14006a589  test    eax, eax
0x14006a58b  jz      loc_14006A83D
0x14006a591  mov     rcx, [rsp+1A0h+var_140]; this
0x14006a596  mov     eax, [rcx+208h]
0x14006a59c  test    al, 4
0x14006a59e  jnz     loc_14006A7A5
0x14006a5a4  xorps   xmm0, xmm0
0x14006a5a7  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14006a5ae  lea     rdx, [rsp+1A0h+var_140]
0x14006a5b3  lea     rcx, [rbp+0A0h+var_100]
0x14006a5b7  movups  [rbp+0A0h+var_100], xmm0
0x14006a5bb  movups  [rbp+0A0h+var_F0], xmm0
0x14006a5bf  call    cs:__imp_PushThreadGuardedObject
0x14006a5c6  nop     dword ptr [rax+rax+00h]
0x14006a5cb  mov     rax, [rsp+1A0h+var_140]
0x14006a5d0  mov     [rbp+0A0h+var_E0], sil
0x14006a5d4  test    rax, rax
0x14006a5d7  jz      loc_14006A71A
0x14006a5dd  movzx   eax, word ptr [rax+0Ch]
0x14006a5e1  cmp     ax, si
0x14006a5e4  jnz     loc_14006A976
0x14006a5ea  mov     rax, [rsp+1A0h+var_140]
0x14006a5ef  movzx   ecx, word ptr [rax+0Ch]
0x14006a5f3  cmp     cx, si
0x14006a5f6  jnz     loc_14006A98F
0x14006a5fc  cmp     [rsp+1A0h+var_140], r12
0x14006a601  jz      loc_14006A71A
0x14006a607  lea     rcx, [rbp+0A0h+var_C0]; this
0x14006a60b  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x14006a610  mov     r8d, esi
0x14006a613  lea     rdx, [rsp+1A0h+var_140]
0x14006a618  lea     rcx, [rbp+0A0h+var_C0]
0x14006a61c  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x14006a623  nop     dword ptr [rax+rax+00h]
0x14006a628  test    eax, eax
0x14006a62a  jz      loc_14006A6E8
0x14006a630  xor     r9d, r9d
0x14006a633  lea     rcx, [rsp+1A0h+var_180]
0x14006a638  xor     r8d, r8d
0x14006a63b  mov     rdx, r14
0x14006a63e  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x14006a645  nop     dword ptr [rax+rax+00h]
0x14006a64a  mov     rdx, [rsp+1A0h+var_180]
0x14006a64f  test    rdx, rdx
0x14006a652  jz      loc_14006A72D
0x14006a658  mov     rcx, [rsp+1A0h+var_140]
0x14006a65d  cmp     edi, 4
0x14006a660  jz      loc_14006A856
0x14006a666  sub     edi, esi
0x14006a668  jnz     loc_14006A756
0x14006a66e  mov     rax, rcx
0x14006a671  mov     rcx, [rcx+0A0h]
0x14006a678  mov     [rbp+0A0h+arg_18], rcx
0x14006a67f  test    rcx, rcx
0x14006a682  jz      loc_14006A79D
0x14006a688  lea     rdx, [rbp+0A0h+arg_18]
0x14006a68f  lea     rcx, [rsp+1A0h+var_180]
0x14006a694  call    cs:__imp_?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z; RGNOBJAPI::bCopy(RGNOBJ &)
0x14006a69b  nop     dword ptr [rax+rax+00h]
0x14006a6a0  mov     rdx, [rsp+1A0h+var_180]
0x14006a6a5  neg     eax
0x14006a6a7  sbb     edi, edi
0x14006a6a9  and     edi, 2
0x14006a6ac  add     edi, ebx
0x14006a6ae  cmp     [rsp+1A0h+var_150], r12d
0x14006a6b3  jnz     short loc_14006A6CB
0x14006a6b5  lea     rcx, [rsp+1A0h+var_180]
0x14006a6ba  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006a6c1  nop     dword ptr [rax+rax+00h]
0x14006a6c6  mov     rdx, [rsp+1A0h+var_180]
0x14006a6cb  test    rdx, rdx
0x14006a6ce  jz      short loc_14006A6D5
0x14006a6d0  lock add [rdx+0Ch], bx
0x14006a6d5  mov     ebx, edi
0x14006a6d7  lea     rcx, [rsp+1A0h+var_178]
0x14006a6dc  call    cs:__imp_PopThreadGuardedObject
0x14006a6e3  nop     dword ptr [rax+rax+00h]
0x14006a6e8  lea     rcx, [rbp+0A0h+var_C0]; this
0x14006a6ec  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14006a6f1  lea     rcx, [rsp+1A0h+var_140]; this
0x14006a6f6  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14006a6fb  lea     r11, [rsp+1A0h+var_20]
0x14006a703  mov     eax, ebx
0x14006a705  mov     rbx, [r11+30h]
0x14006a709  mov     rsi, [r11+38h]
0x14006a70d  mov     rsp, r11
0x14006a710  pop     r15
0x14006a712  pop     r14
0x14006a714  pop     r12
0x14006a716  pop     rdi
0x14006a717  pop     rbp
0x14006a718  retn
0x14006a71a  mov     ecx, 6; iError
0x14006a71f  call    cs:__imp_EngSetLastError
0x14006a726  nop     dword ptr [rax+rax+00h]
0x14006a72b  jmp     short loc_14006A6F1
0x14006a72d  cmp     [rsp+1A0h+var_150], r12d
0x14006a732  jnz     short loc_14006A6D7
0x14006a734  lea     rcx, [rsp+1A0h+var_180]
0x14006a739  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006a740  nop     dword ptr [rax+rax+00h]
0x14006a745  mov     rax, [rsp+1A0h+var_180]
0x14006a74a  test    rax, rax
0x14006a74d  jz      short loc_14006A6D7
0x14006a74f  lock add [rax+0Ch], bx
0x14006a754  jmp     short loc_14006A6D7
0x14006a756  sub     edi, esi
0x14006a758  jz      loc_14006A961
0x14006a75e  sub     edi, esi
0x14006a760  jz      loc_14006A99E
0x14006a766  sub     edi, esi
0x14006a768  jz      short loc_14006A7AF
0x14006a76a  cmp     edi, esi
0x14006a76c  jz      short loc_14006A7AF
0x14006a76e  cmp     [rsp+1A0h+var_150], r12d
0x14006a773  jnz     short loc_14006A78B
0x14006a775  lea     rcx, [rsp+1A0h+var_180]
0x14006a77a  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006a781  nop     dword ptr [rax+rax+00h]
0x14006a786  mov     rdx, [rsp+1A0h+var_180]
0x14006a78b  test    rdx, rdx
0x14006a78e  jz      short loc_14006A795
0x14006a790  lock add [rdx+0Ch], bx
0x14006a795  mov     ebx, r12d
0x14006a798  jmp     loc_14006A6D7
0x14006a79d  mov     edi, r12d
0x14006a7a0  jmp     loc_14006A6AE
0x14006a7a5  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x14006a7aa  jmp     loc_14006A5A4
0x14006a7af  lea     rsi, [rcx+458h]
0x14006a7b6  mov     rcx, rsi
0x14006a7b9  call    cs:__imp_?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ; GreInnermostPushLock::AcquireLockShared(void)
0x14006a7c0  nop     dword ptr [rax+rax+00h]
0x14006a7c5  mov     rax, [rsp+1A0h+var_140]
0x14006a7ca  mov     rcx, [rax+470h]
0x14006a7d1  mov     [rbp+0A0h+arg_18], rcx
0x14006a7d8  test    rcx, rcx
0x14006a7db  jz      short loc_14006A851
0x14006a7dd  lea     rdx, [rbp+0A0h+arg_18]
0x14006a7e4  lea     rcx, [rsp+1A0h+var_180]
0x14006a7e9  call    cs:__imp_?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z; RGNOBJAPI::bCopy(RGNOBJ &)
0x14006a7f0  nop     dword ptr [rax+rax+00h]
0x14006a7f5  neg     eax
0x14006a7f7  sbb     edi, edi
0x14006a7f9  and     edi, 2
0x14006a7fc  add     edi, ebx
0x14006a7fe  mov     rcx, rsi
0x14006a801  call    cs:__imp_?ReleaseLock@GreInnermostPushLock@@QEBAXXZ; GreInnermostPushLock::ReleaseLock(void)
0x14006a808  nop     dword ptr [rax+rax+00h]
0x14006a80d  cmp     [rsp+1A0h+var_150], r12d
0x14006a812  jnz     short loc_14006A825
0x14006a814  lea     rcx, [rsp+1A0h+var_180]
0x14006a819  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006a820  nop     dword ptr [rax+rax+00h]
0x14006a825  mov     rax, [rsp+1A0h+var_180]
0x14006a82a  test    rax, rax
0x14006a82d  jz      loc_14006A6D5
0x14006a833  lock add [rax+0Ch], bx
0x14006a838  jmp     loc_14006A6D5
0x14006a83d  mov     rax, [rsp+1A0h+var_140]
0x14006a842  lock add [rax+0Ch], bx
0x14006a847  mov     [rsp+1A0h+var_140], r12
0x14006a84c  jmp     loc_14006A5A4
0x14006a851  mov     edi, r12d
0x14006a854  jmp     short loc_14006A7FE
0x14006a856  test    dword ptr [rcx+24h], 4000h
0x14006a85d  jz      loc_14006A7AF
0x14006a863  lea     r14, [rcx+458h]
0x14006a86a  mov     rcx, r14
0x14006a86d  call    cs:__imp_?AcquireLockShared@GreInnermostPushLock@@QEBAXXZ; GreInnermostPushLock::AcquireLockShared(void)
0x14006a874  nop     dword ptr [rax+rax+00h]
0x14006a879  mov     rax, [rsp+1A0h+var_140]
0x14006a87e  mov     rcx, [rax+470h]
0x14006a885  mov     [rsp+1A0h+var_148], rcx
0x14006a88a  test    rcx, rcx
0x14006a88d  jz      loc_14006A92F
0x14006a893  lea     rdx, [rsp+1A0h+var_148]
0x14006a898  lea     rcx, [rsp+1A0h+var_180]
0x14006a89d  call    cs:__imp_?bCopy@RGNOBJAPI@@QEAAHAEAVRGNOBJ@@@Z; RGNOBJAPI::bCopy(RGNOBJ &)
0x14006a8a4  nop     dword ptr [rax+rax+00h]
0x14006a8a9  mov     ecx, eax
0x14006a8ab  neg     ecx
0x14006a8ad  sbb     edi, edi
0x14006a8af  and     edi, 2
0x14006a8b2  add     edi, ebx
0x14006a8b4  test    eax, eax
0x14006a8b6  jz      short loc_14006A932
0x14006a8b8  mov     rcx, r14
0x14006a8bb  call    cs:__imp_?ReleaseLock@GreInnermostPushLock@@QEBAXXZ; GreInnermostPushLock::ReleaseLock(void)
0x14006a8c2  nop     dword ptr [rax+rax+00h]
0x14006a8c7  lea     rdx, [rbp+0A0h+arg_18]
0x14006a8ce  mov     [rbp+0A0h+arg_18], r12
0x14006a8d5  mov     rcx, r15
0x14006a8d8  call    UserGetRedirectedWindowOrigin
0x14006a8dd  test    eax, eax
0x14006a8df  jz      loc_14006A972
0x14006a8e5  lea     rdx, [rbp+0A0h+arg_18]
0x14006a8ec  lea     rcx, [rsp+1A0h+var_180]
0x14006a8f1  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14006a8f8  nop     dword ptr [rax+rax+00h]
0x14006a8fd  test    eax, eax
0x14006a8ff  jz      short loc_14006A972
0x14006a901  cmp     [rsp+1A0h+var_150], r12d
0x14006a906  jnz     short loc_14006A919
0x14006a908  lea     rcx, [rsp+1A0h+var_180]
0x14006a90d  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x14006a914  nop     dword ptr [rax+rax+00h]
0x14006a919  mov     rax, [rsp+1A0h+var_180]
0x14006a91e  test    rax, rax
0x14006a921  jz      short loc_14006A928
0x14006a923  lock add [rax+0Ch], bx
0x14006a928  mov     ebx, esi
0x14006a92a  jmp     loc_14006A6D7
0x14006a92f  mov     edi, r12d
0x14006a932  mov     rcx, r14
0x14006a935  jmp     loc_14006A801
0x14006a93a  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14006a941  nop     dword ptr [rax+rax+00h]
0x14006a946  cmp     eax, esi
0x14006a948  jz      loc_14006A578
0x14006a94e  mov     ecx, esi
0x14006a950  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14006a957  nop     dword ptr [rax+rax+00h]
0x14006a95c  jmp     loc_14006A578
0x14006a961  mov     rax, [rsp+1A0h+var_140]
0x14006a966  mov     rcx, [rax+0A8h]
0x14006a96d  jmp     loc_14006A678
0x14006a972  mov     esi, ebx
0x14006a974  jmp     short loc_14006A901
0x14006a976  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14006a97b  jmp     loc_14006A5EA
0x14006a980  lock add [rax+0Ch], bx
0x14006a985  mov     [rsp+1A0h+var_140], r12
0x14006a98a  jmp     loc_14006A578
0x14006a98f  lea     rcx, [rsp+1A0h+var_140]; this
0x14006a994  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x14006a999  jmp     loc_14006A5FC
0x14006a99e  mov     rax, [rsp+1A0h+var_140]
0x14006a9a3  mov     r8, [rax+0A8h]
0x14006a9aa  mov     rcx, [rax+0A0h]
0x14006a9b1  test    r8, r8
0x14006a9b4  jz      short loc_14006A9EC
0x14006a9b6  test    rcx, rcx
0x14006a9b9  jz      short loc_14006A9F4
0x14006a9bb  mov     [rbp+0A0h+var_D0], rcx
0x14006a9bf  lea     rdx, [rbp+0A0h+var_D0]
0x14006a9c3  mov     [rsp+1A0h+var_148], r8
0x14006a9c8  lea     rcx, [rsp+1A0h+var_180]
0x14006a9cd  lea     r8, [rsp+1A0h+var_148]
0x14006a9d2  mov     r9d, esi
0x14006a9d5  call    cs:__imp_?iCombine@RGNOBJAPI@@QEAAJAEAVRGNOBJ@@0J@Z; RGNOBJAPI::iCombine(RGNOBJ &,RGNOBJ &,long)
0x14006a9dc  nop     dword ptr [rax+rax+00h]
0x14006a9e1  neg     eax
0x14006a9e3  sbb     ecx, ecx
  ... truncated ...
```
