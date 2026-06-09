# UntrapAppContainerRenderingWrap

- ea: `0x14011d730`
- end: `0x14011da2d`
- name: `UntrapAppContainerRenderingWrap`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14005db98`
- `0x140067320`
- `0x140099c84`
- `0x14009a40c`
- `0x14009b35c`
- `0x1400ac68c`
- `0x14011d730`
- `0x14011e794`
- `0x14011e9a0`
- `0x14011ea9c`
- `0x14011eb74`
- `0x14011ec90`

## import_xrefs

- `win32kbase!GreDereferenceObject` at `0x14011d8aa`
- `win32kbase!GreDereferenceObject` at `0x14011d8aa`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d7e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d819`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d854`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d87b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d8d2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d91c`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d7e8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d819`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d854`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d87b`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d8d2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14011d91c`
- `win32kbase!HmgShareLock` at `0x14011d806`
- `win32kbase!HmgShareLock` at `0x14011d831`
- `win32kbase!HmgShareLock` at `0x14011d806`
- `win32kbase!HmgShareLock` at `0x14011d831`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14011d867`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14011d88e`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14011d867`
- `win32kbase!DEC_SHARE_REF_CNT` at `0x14011d88e`
- `win32kbase!PushThreadGuardedObject` at `0x14011d7a3`
- `win32kbase!PushThreadGuardedObject` at `0x14011d7d1`
- `win32kbase!PushThreadGuardedObject` at `0x14011d7a3`
- `win32kbase!PushThreadGuardedObject` at `0x14011d7d1`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14011d975`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14011da02`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14011da1f`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14011da02`
- `win32kbase!?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z` at `0x14011da1f`
- `win32kbase!GreGetLockCount` at `0x14011d8f5`
- `win32kbase!GreGetLockCount` at `0x14011d8f5`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14011d944`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14011d9cd`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14011d944`
- `win32kbase!HmgShareUnlockRemoveObject` at `0x14011d9cd`

## pseudocode

```c
void __fastcall UntrapAppContainerRenderingWrap(HDC *a1, _QWORD *a2, __int64 *a3, _DWORD *a4)
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
    v8 = *a3;
    v34 = 0;
    v10 = Gre::Base::Globals(v9);
    LOBYTE(v11) = 5;
    v12 = HmgShareLock(v10, v8, v11, 1);
    v13 = *a2;
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
        SURFACE::bDeleteSurface(v28, v24, 0, 1);
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
        SURFACE::bDeleteSurface(v30, v24, 0, 1);
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
0x14011d730  mov     [rsp-8+arg_0], rbx
0x14011d735  mov     [rsp-8+arg_10], rsi
0x14011d73a  push    rbp
0x14011d73b  push    rdi
0x14011d73c  push    r13
0x14011d73e  push    r14
0x14011d740  push    r15
0x14011d742  lea     rbp, [rsp-37h]
0x14011d747  sub     rsp, 0C0h
0x14011d74e  cmp     qword ptr [rdx], 0
0x14011d752  mov     rsi, r9
0x14011d755  mov     r14, r8
0x14011d758  mov     rdi, rdx
0x14011d75b  mov     r15, rcx
0x14011d75e  jnz     short loc_14011D77D
0x14011d760  lea     r11, [rsp+0E0h+var_20]
0x14011d768  mov     rbx, [r11+30h]
0x14011d76c  mov     rsi, [r11+40h]
0x14011d770  mov     rsp, r11
0x14011d773  pop     r15
0x14011d775  pop     r14
0x14011d777  pop     r13
0x14011d779  pop     rdi
0x14011d77a  pop     rbp
0x14011d77b  retn
0x14011d77d  mov     rdx, [rcx]; HDC
0x14011d780  lea     rcx, [rbp+57h+var_60]; this
0x14011d784  call    ??0DCOBJ@@QEAA@PEAUHDC__@@@Z; DCOBJ::DCOBJ(HDC__ *)
0x14011d789  xorps   xmm0, xmm0
0x14011d78c  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14011d793  lea     rdx, [rbp+57h+var_B0]
0x14011d797  lea     rcx, [rbp+57h+var_B0]
0x14011d79b  movups  [rbp+57h+var_B0], xmm0
0x14011d79f  movups  [rbp+57h+var_A0], xmm0
0x14011d7a3  call    cs:__imp_PushThreadGuardedObject
0x14011d7aa  nop     dword ptr [rax+rax+00h]
0x14011d7af  xorps   xmm0, xmm0
0x14011d7b2  mov     [rbp+57h+var_90], 0
0x14011d7ba  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORTRANSFORMOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORTRANSFORMOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14011d7c1  lea     rdx, [rbp+57h+var_88]
0x14011d7c5  lea     rcx, [rbp+57h+var_88]
0x14011d7c9  movups  [rbp+57h+var_88], xmm0
0x14011d7cd  movups  [rbp+57h+var_78], xmm0
0x14011d7d1  call    cs:__imp_PushThreadGuardedObject
0x14011d7d8  nop     dword ptr [rax+rax+00h]
0x14011d7dd  mov     rbx, [r14]
0x14011d7e0  mov     [rbp+57h+var_68], 0
0x14011d7e8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d7ef  nop     dword ptr [rax+rax+00h]
0x14011d7f4  mov     r13d, 1
0x14011d7fa  mov     r8b, 5
0x14011d7fd  mov     r9d, r13d
0x14011d800  mov     rcx, rax
0x14011d803  mov     rdx, rbx
0x14011d806  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011d80d  nop     dword ptr [rax+rax+00h]
0x14011d812  mov     rbx, [rdi]
0x14011d815  mov     [rbp+57h+var_90], rax
0x14011d819  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d820  nop     dword ptr [rax+rax+00h]
0x14011d825  mov     r9d, r13d
0x14011d828  mov     r8b, 5
0x14011d82b  mov     rcx, rax
0x14011d82e  mov     rdx, rbx
0x14011d831  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14011d838  nop     dword ptr [rax+rax+00h]
0x14011d83d  mov     rcx, [rbp+57h+var_90]
0x14011d841  mov     rdx, rax; struct SURFACE *
0x14011d844  mov     [rbp+57h+var_68], rax
0x14011d848  mov     rbx, [rcx]
0x14011d84b  mov     rcx, [rbp+57h+var_60]; this
0x14011d84f  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x14011d854  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d85b  nop     dword ptr [rax+rax+00h]
0x14011d860  mov     rdx, [rbp+57h+var_90]
0x14011d864  mov     rcx, rax
0x14011d867  call    cs:__imp_DEC_SHARE_REF_CNT
0x14011d86e  nop     dword ptr [rax+rax+00h]
0x14011d873  mov     [rbp+57h+var_90], 0
0x14011d87b  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d882  nop     dword ptr [rax+rax+00h]
0x14011d887  mov     rdx, [rbp+57h+var_68]
0x14011d88b  mov     rcx, rax
0x14011d88e  call    cs:__imp_DEC_SHARE_REF_CNT
0x14011d895  nop     dword ptr [rax+rax+00h]
0x14011d89a  mov     r8d, r13d
0x14011d89d  mov     [rbp+57h+var_68], 0
0x14011d8a5  mov     dl, 5
0x14011d8a7  mov     rcx, rbx
0x14011d8aa  call    cs:__imp_GreDereferenceObject
0x14011d8b1  nop     dword ptr [rax+rax+00h]
0x14011d8b6  mov     qword ptr [r15], 0
0x14011d8bd  mov     qword ptr [r14], 0
0x14011d8c4  test    rsi, rsi
0x14011d8c7  jz      short loc_14011D8D2
0x14011d8c9  mov     rcx, [rbp+57h+var_60]
0x14011d8cd  mov     eax, [rsi]
0x14011d8cf  or      [rcx+24h], eax
0x14011d8d2  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d8d9  nop     dword ptr [rax+rax+00h]
0x14011d8de  mov     rcx, [rbp+57h+var_60]
0x14011d8e2  mov     rbx, rax
0x14011d8e5  test    dword ptr [rcx+24h], 200h
0x14011d8ec  jz      loc_14011D9BD
0x14011d8f2  xor     sil, sil
0x14011d8f5  call    cs:__imp_GreGetLockCount
0x14011d8fc  nop     dword ptr [rax+rax+00h]
0x14011d901  test    eax, eax
0x14011d903  jnz     short loc_14011D91C
0x14011d905  mov     rcx, rbx
0x14011d908  call    ??$GrepIsLockOwnedByCurrentThread@$01USESSION_GLOBALS@Base@Gre@@@@YA_NAEBUSESSION_GLOBALS@Base@Gre@@@Z; GrepIsLockOwnedByCurrentThread<2,Gre::Base::SESSION_GLOBALS>(Gre::Base::SESSION_GLOBALS const &)
0x14011d90d  test    al, al
0x14011d90f  jnz     short loc_14011D91C
0x14011d911  mov     rcx, rbx
0x14011d914  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14011d919  mov     sil, r13b
0x14011d91c  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14011d923  nop     dword ptr [rax+rax+00h]
0x14011d928  mov     rdx, rax
0x14011d92b  lea     rcx, [rbp+57h+arg_8]
0x14011d92f  call    ??0?$SEMOBJSHARED@$02@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@@Z; SEMOBJSHARED<3>::SEMOBJSHARED<3>(Gre::Base::SESSION_GLOBALS &)
0x14011d934  mov     rcx, [rdi]
0x14011d937  xor     r9d, r9d
0x14011d93a  xor     r8d, r8d
0x14011d93d  mov     [rsp+0E0h+var_C0], 5
0x14011d942  xor     edx, edx
0x14011d944  call    cs:__imp_HmgShareUnlockRemoveObject
0x14011d94b  nop     dword ptr [rax+rax+00h]
0x14011d950  test    rax, rax
0x14011d953  jnz     loc_14011D9F6
0x14011d959  mov     rax, [rbp+57h+var_60]
0x14011d95d  mov     qword ptr [rax+1F8h], 0
0x14011d968  mov     rcx, [rbp+57h+var_60]; this
0x14011d96c  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x14011d971  mov     rdx, [rbp+57h+arg_8]
0x14011d975  mov     rcx, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14011d97c  mov     qword ptr [rdi], 0
0x14011d983  call    ??$GreReleaseSemaphoreCommon@$02P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<3,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14011d988  test    sil, sil
0x14011d98b  jz      short loc_14011D995
0x14011d98d  mov     rcx, rbx
0x14011d990  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14011d995  mov     rcx, rbx
0x14011d998  call    ??$GreReleaseSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x14011d99d  lea     rcx, [rbp+57h+var_88]; this
0x14011d9a1  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14011d9a6  lea     rcx, [rbp+57h+var_B0]; this
0x14011d9aa  call    ??1SFMALTLOGICALSURFACEREF@@QEAA@XZ; SFMALTLOGICALSURFACEREF::~SFMALTLOGICALSURFACEREF(void)
0x14011d9af  lea     rcx, [rbp+57h+var_60]; this
0x14011d9b3  call    ??1DCOBJ@@QEAA@XZ; DCOBJ::~DCOBJ(void)
0x14011d9b8  jmp     loc_14011D760
0x14011d9bd  mov     rcx, [rdi]
0x14011d9c0  xor     r9d, r9d
0x14011d9c3  xor     r8d, r8d
0x14011d9c6  mov     [rsp+0E0h+var_C0], 5
0x14011d9cb  xor     edx, edx
0x14011d9cd  call    cs:__imp_HmgShareUnlockRemoveObject
0x14011d9d4  nop     dword ptr [rax+rax+00h]
0x14011d9d9  test    rax, rax
0x14011d9dc  jnz     short loc_14011DA13
0x14011d9de  mov     rax, [rbp+57h+var_60]
0x14011d9e2  mov     qword ptr [rax+1F8h], 0
0x14011d9ed  mov     qword ptr [rdi], 0
0x14011d9f4  jmp     short loc_14011D995
0x14011d9f6  mov     r9d, r13d
0x14011d9f9  xor     r8d, r8d
0x14011d9fc  mov     rdx, rbx
0x14011d9ff  mov     rcx, rax
0x14011da02  call    cs:__imp_?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z; SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)
0x14011da09  nop     dword ptr [rax+rax+00h]
0x14011da0e  jmp     loc_14011D959
0x14011da13  mov     r9d, r13d
0x14011da16  xor     r8d, r8d
0x14011da19  mov     rdx, rbx
0x14011da1c  mov     rcx, rax
0x14011da1f  call    cs:__imp_?bDeleteSurface@SURFACE@@QEAAHAEAUSESSION_GLOBALS@Base@Gre@@W4_CLEANUPTYPE@@H@Z; SURFACE::bDeleteSurface(Gre::Base::SESSION_GLOBALS &,_CLEANUPTYPE,int)
0x14011da26  nop     dword ptr [rax+rax+00h]
0x14011da2b  jmp     short loc_14011D9DE
```
