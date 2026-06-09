# UntrapAppContainerRendering(HDC__ * &,HSURF__ * &,HSURF__ * &,ulong *)

- ea: `0x14008c880`
- end: `0x14008cb7d`
- name: `?UntrapAppContainerRendering@@YAXAEAPEAUHDC__@@AEAPEAUHSURF__@@1PEAK@Z`
- size: `765`
- prototype: `void __fastcall(HDC *, HSURF *, HSURF *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007bc10`
- `0x140080590`

## callees

- `0x14005f380`
- `0x14005fb0c`
- `0x140077d74`
- `0x140078610`
- `0x1400846c8`
- `0x14008c880`
- `0x14008cde8`
- `0x14008d8bc`
- `0x14008d990`
- `0x14008e730`
- `0x14008e84c`
- `0x14009608c`

## import_xrefs

- `win32kbase!GreDereferenceObject` at `0x14008c9fa`
- `win32kbase!GreDereferenceObject` at `0x14008c9fa`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c938`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c969`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c9a4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c9cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ca22`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ca6c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c938`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c969`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c9a4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008c9cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ca22`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14008ca6c`
- `win32kbase!HmgShareLock` at `0x14008c956`
- `win32kbase!HmgShareLock` at `0x14008c981`
- `win32kbase!HmgShareLock` at `0x14008c956`
- `win32kbase!HmgShareLock` at `0x14008c981`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008c9b7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008c9de`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008c9b7`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14008c9de`
- `win32kbase!PushThreadGuardedObject` at `0x14008c8f3`
- `win32kbase!PushThreadGuardedObject` at `0x14008c921`
- `win32kbase!PushThreadGuardedObject` at `0x14008c8f3`
- `win32kbase!PushThreadGuardedObject` at `0x14008c921`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14008cac5`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14008cb52`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14008cb6f`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14008cb52`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14008cb6f`
- `win32kbase!GreGetLockCount` at `0x14008ca45`
- `win32kbase!GreGetLockCount` at `0x14008ca45`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14008ca94`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14008cb1d`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14008ca94`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14008cb1d`

## pseudocode

```c
void __fastcall UntrapAppContainerRendering(HDC *a1, HSURF *a2, HSURF *a3, unsigned int *a4)
{
  __int64 v8; // rbx
  Gre::Base *v9; // rcx
  struct Gre::Base::SESSION_GLOBALS *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  Gre::Base *v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v15; // rax
  __int64 v16; // r8
  __int64 v17; // rbx
  Gre::Base *v18; // rcx
  struct Gre::Base::SESSION_GLOBALS *v19; // rax
  Gre::Base *v20; // rcx
  struct Gre::Base::SESSION_GLOBALS *v21; // rax
  __int64 v22; // rdx
  Gre::Base *v23; // rcx
  struct Gre::Base::SESSION_GLOBALS *v24; // rbx
  char v25; // si
  Gre::Base *v26; // rcx
  struct Gre::Base::SESSION_GLOBALS *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  _OWORD v31[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v32; // [rsp+50h] [rbp-39h]
  _OWORD v33[2]; // [rsp+58h] [rbp-31h] BYREF
  struct SURFACE *v34; // [rsp+78h] [rbp-11h]
  DC *v35[8]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v36; // [rsp+F8h] [rbp+6Fh] BYREF

  if ( *a2 )
  {
    DCOBJ::DCOBJ((DCOBJ *)v35, *a1);
    memset(v31, 0, sizeof(v31));
    PushThreadGuardedObject(
      v31,
      v31,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v32 = 0;
    memset(v33, 0, sizeof(v33));
    PushThreadGuardedObject(
      v33,
      v33,
      UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic);
    v8 = (__int64)*a3;
    v34 = 0;
    v10 = Gre::Base::Globals(v9);
    LOBYTE(v11) = 5;
    v12 = HmgShareLock(v10, v8, v11, 1);
    v13 = (__int64)*a2;
    v32 = (__int64 *)v12;
    v15 = Gre::Base::Globals(v14);
    LOBYTE(v16) = 5;
    v34 = (struct SURFACE *)HmgShareLock(v15, v13, v16, 1);
    v17 = *v32;
    DC::pSurface(v35[0], v34);
    v19 = Gre::Base::Globals(v18);
    DEC_SHARE_REF_CNT(v19, v32);
    v32 = 0;
    v21 = Gre::Base::Globals(v20);
    DEC_SHARE_REF_CNT(v21, v34);
    v34 = 0;
    LOBYTE(v22) = 5;
    GreDereferenceObject(v17, v22, 1);
    *a1 = 0;
    *a3 = 0;
    if ( a4 )
    {
      v23 = v35[0];
      *((_DWORD *)v35[0] + 9) |= *a4;
    }
    v24 = Gre::Base::Globals(v23);
    if ( (*((_DWORD *)v35[0] + 9) & 0x200) != 0 )
    {
      v25 = 0;
      if ( !(unsigned int)GreGetLockCount()
        && !(unsigned __int8)GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(v24) )
      {
        GreAcquireSemaphoreShared<2,>(v24);
        v25 = 1;
      }
      v27 = Gre::Base::Globals(v26);
      SEMOBJSHARED<3>::SEMOBJSHARED<3>(&v36, v27);
      v28 = HmgShareUnlockRemoveObject(*a2, 0, 0, 0, 5);
      if ( v28 )
        SURFACE::bDeleteSurface(v28, v24, 0);
      *((_QWORD *)v35[0] + 63) = 0;
      DC::vClearRendering(v35[0]);
      v29 = v36;
      *a2 = 0;
      GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(GreReleaseSemaphoreSharedInternal, v29);
      if ( v25 )
        GreReleaseSemaphoreShared<2,>(v24);
    }
    else
    {
      v30 = HmgShareUnlockRemoveObject(*a2, 0, 0, 0, 5);
      if ( v30 )
        SURFACE::bDeleteSurface(v30, v24, 0);
      *((_QWORD *)v35[0] + 63) = 0;
      *a2 = 0;
    }
    GreReleaseSemaphoreShared<1,>(v24);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v33);
    SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF((SFMALTLOGICALSURFACEREF *)v31);
    DCOBJ::~DCOBJ((DCOBJ *)v35);
  }
}

```

## disassembly

```asm
0x14008c880  mov     [rsp-8+arg_0], rbx
0x14008c885  mov     [rsp-8+arg_10], rsi
0x14008c88a  push    rbp
0x14008c88b  push    rdi
0x14008c88c  push    r13
0x14008c88e  push    r14
0x14008c890  push    r15
0x14008c892  lea     rbp, [rsp-37h]
0x14008c897  sub     rsp, 0C0h
0x14008c89e  cmp     qword ptr [rdx], 0
0x14008c8a2  mov     rsi, r9
0x14008c8a5  mov     r14, r8
0x14008c8a8  mov     rdi, rdx
0x14008c8ab  mov     r15, rcx
0x14008c8ae  jnz     short loc_14008C8CD
0x14008c8b0  lea     r11, [rsp+0E0h+var_20]
0x14008c8b8  mov     rbx, [r11+30h]
0x14008c8bc  mov     rsi, [r11+40h]
0x14008c8c0  mov     rsp, r11
0x14008c8c3  pop     r15
0x14008c8c5  pop     r14
0x14008c8c7  pop     r13
0x14008c8c9  pop     rdi
0x14008c8ca  pop     rbp
0x14008c8cb  retn
0x14008c8cd  mov     rdx, [rcx]; HDC
0x14008c8d0  lea     rcx, [rbp+57h+var_60]; this
0x14008c8d4  call    ??0DCOBJ@@QEAA@PEAUHDC__@@@Z; DCOBJ::DCOBJ(HDC__ *)
0x14008c8d9  xorps   xmm0, xmm0
0x14008c8dc  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14008c8e3  lea     rdx, [rbp+57h+var_B0]
0x14008c8e7  lea     rcx, [rbp+57h+var_B0]
0x14008c8eb  movups  [rbp+57h+var_B0], xmm0
0x14008c8ef  movups  [rbp+57h+var_A0], xmm0
0x14008c8f3  call    cs:__imp_PushThreadGuardedObject
0x14008c8fa  nop     dword ptr [rax+rax+00h]
0x14008c8ff  xorps   xmm0, xmm0
0x14008c902  mov     [rbp+57h+var_90], 0
0x14008c90a  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14008c911  lea     rdx, [rbp+57h+var_88]
0x14008c915  lea     rcx, [rbp+57h+var_88]
0x14008c919  movups  [rbp+57h+var_88], xmm0
0x14008c91d  movups  [rbp+57h+var_78], xmm0
0x14008c921  call    cs:__imp_PushThreadGuardedObject
0x14008c928  nop     dword ptr [rax+rax+00h]
0x14008c92d  mov     rbx, [r14]
0x14008c930  mov     [rbp+57h+var_68], 0
0x14008c938  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c93f  nop     dword ptr [rax+rax+00h]
0x14008c944  mov     r13d, 1
0x14008c94a  mov     r8b, 5
0x14008c94d  mov     r9d, r13d
0x14008c950  mov     rcx, rax
0x14008c953  mov     rdx, rbx
0x14008c956  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008c95d  nop     dword ptr [rax+rax+00h]
0x14008c962  mov     rbx, [rdi]
0x14008c965  mov     [rbp+57h+var_90], rax
0x14008c969  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c970  nop     dword ptr [rax+rax+00h]
0x14008c975  mov     r9d, r13d
0x14008c978  mov     r8b, 5
0x14008c97b  mov     rcx, rax
0x14008c97e  mov     rdx, rbx
0x14008c981  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14008c988  nop     dword ptr [rax+rax+00h]
0x14008c98d  mov     rcx, [rbp+57h+var_90]
0x14008c991  mov     rdx, rax; struct SURFACE *
0x14008c994  mov     [rbp+57h+var_68], rax
0x14008c998  mov     rbx, [rcx]
0x14008c99b  mov     rcx, [rbp+57h+var_60]; this
0x14008c99f  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x14008c9a4  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c9ab  nop     dword ptr [rax+rax+00h]
0x14008c9b0  mov     rdx, [rbp+57h+var_90]
0x14008c9b4  mov     rcx, rax
0x14008c9b7  call    cs:__imp_DEC_SHARE_REF_CNT
0x14008c9be  nop     dword ptr [rax+rax+00h]
0x14008c9c3  mov     [rbp+57h+var_90], 0
0x14008c9cb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008c9d2  nop     dword ptr [rax+rax+00h]
0x14008c9d7  mov     rdx, [rbp+57h+var_68]
0x14008c9db  mov     rcx, rax
0x14008c9de  call    cs:__imp_DEC_SHARE_REF_CNT
0x14008c9e5  nop     dword ptr [rax+rax+00h]
0x14008c9ea  mov     r8d, r13d
0x14008c9ed  mov     [rbp+57h+var_68], 0
0x14008c9f5  mov     dl, 5
0x14008c9f7  mov     rcx, rbx
0x14008c9fa  call    cs:__imp_GreDereferenceObject
0x14008ca01  nop     dword ptr [rax+rax+00h]
0x14008ca06  mov     qword ptr [r15], 0
0x14008ca0d  mov     qword ptr [r14], 0
0x14008ca14  test    rsi, rsi
0x14008ca17  jz      short loc_14008CA22
0x14008ca19  mov     rcx, [rbp+57h+var_60]
0x14008ca1d  mov     eax, [rsi]
0x14008ca1f  or      [rcx+24h], eax
0x14008ca22  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008ca29  nop     dword ptr [rax+rax+00h]
0x14008ca2e  mov     rcx, [rbp+57h+var_60]
0x14008ca32  mov     rbx, rax
0x14008ca35  test    dword ptr [rcx+24h], 200h
0x14008ca3c  jz      loc_14008CB0D
0x14008ca42  xor     sil, sil
0x14008ca45  call    cs:__imp_GreGetLockCount
0x14008ca4c  nop     dword ptr [rax+rax+00h]
0x14008ca51  test    eax, eax
0x14008ca53  jnz     short loc_14008CA6C
0x14008ca55  mov     rcx, rbx
0x14008ca58  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x14008ca5d  test    al, al
0x14008ca5f  jnz     short loc_14008CA6C
0x14008ca61  mov     rcx, rbx
0x14008ca64  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14008ca69  mov     sil, r13b
0x14008ca6c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008ca73  nop     dword ptr [rax+rax+00h]
0x14008ca78  mov     rdx, rax
0x14008ca7b  lea     rcx, [rbp+57h+arg_8]
0x14008ca7f  call    ??0?$SEMOBJSHARED@$02@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<3>::SEMOBJSHARED<3>(Gre::Base::SESSION_GLOBALS &)
0x14008ca84  mov     rcx, [rdi]
0x14008ca87  xor     r9d, r9d
0x14008ca8a  xor     r8d, r8d
0x14008ca8d  mov     [rsp+0E0h+var_C0], 5
0x14008ca92  xor     edx, edx
0x14008ca94  call    cs:__imp_HmgShareUnlockRemoveObject
0x14008ca9b  nop     dword ptr [rax+rax+00h]
0x14008caa0  test    rax, rax
0x14008caa3  jnz     loc_14008CB46
0x14008caa9  mov     rax, [rbp+57h+var_60]
0x14008caad  mov     qword ptr [rax+1F8h], 0
0x14008cab8  mov     rcx, [rbp+57h+var_60]; this
0x14008cabc  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x14008cac1  mov     rdx, [rbp+57h+arg_8]
0x14008cac5  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14008cacc  mov     qword ptr [rdi], 0
0x14008cad3  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14008cad8  test    sil, sil
0x14008cadb  jz      short loc_14008CAE5
0x14008cadd  mov     rcx, rbx
0x14008cae0  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14008cae5  mov     rcx, rbx
0x14008cae8  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x14008caed  lea     rcx, [rbp+57h+var_88]; this
0x14008caf1  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14008caf6  lea     rcx, [rbp+57h+var_B0]; this
0x14008cafa  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14008caff  lea     rcx, [rbp+57h+var_60]; this
0x14008cb03  call    ??1DCOBJ@@QEAA@XZ; DCOBJ::~DCOBJ(void)
0x14008cb08  jmp     loc_14008C8B0
0x14008cb0d  mov     rcx, [rdi]
0x14008cb10  xor     r9d, r9d
0x14008cb13  xor     r8d, r8d
0x14008cb16  mov     [rsp+0E0h+var_C0], 5
0x14008cb1b  xor     edx, edx
0x14008cb1d  call    cs:__imp_HmgShareUnlockRemoveObject
0x14008cb24  nop     dword ptr [rax+rax+00h]
0x14008cb29  test    rax, rax
0x14008cb2c  jnz     short loc_14008CB63
0x14008cb2e  mov     rax, [rbp+57h+var_60]
0x14008cb32  mov     qword ptr [rax+1F8h], 0
0x14008cb3d  mov     qword ptr [rdi], 0
0x14008cb44  jmp     short loc_14008CAE5
0x14008cb46  mov     r9d, r13d
0x14008cb49  xor     r8d, r8d
0x14008cb4c  mov     rdx, rbx
0x14008cb4f  mov     rcx, rax
0x14008cb52  call    cs:__imp_?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z; SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)
0x14008cb59  nop     dword ptr [rax+rax+00h]
0x14008cb5e  jmp     loc_14008CAA9
0x14008cb63  mov     r9d, r13d
0x14008cb66  xor     r8d, r8d
0x14008cb69  mov     rdx, rbx
0x14008cb6c  mov     rcx, rax
0x14008cb6f  call    cs:__imp_?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z; SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)
0x14008cb76  nop     dword ptr [rax+rax+00h]
0x14008cb7b  jmp     short loc_14008CB2E
```
