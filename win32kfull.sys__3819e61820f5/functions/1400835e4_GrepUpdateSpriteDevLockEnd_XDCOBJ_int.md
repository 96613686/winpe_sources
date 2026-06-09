# GrepUpdateSpriteDevLockEnd(XDCOBJ &,int)

- ea: `0x1400835e4`
- end: `0x140083c4a`
- name: `?GrepUpdateSpriteDevLockEnd@@YAHAEAVXDCOBJ@@H@Z`
- size: `1638`
- prototype: `__int64 __fastcall(struct XDCOBJ *, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140084210`
- `0x140199df4`
- `0x1401b25b4`

## callees

- `0x1400620a8`
- `0x140062190`
- `0x140063f70`
- `0x14007f010`
- `0x140082a3c`
- `0x1400835e4`
- `0x140084a10`
- `0x140084abc`
- `0x140086434`
- `0x140091e34`
- `0x1400f6d54`
- `0x14012a770`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `win32kbase!UserGetHDEV` at `0x140083620`
- `win32kbase!UserGetHDEV` at `0x140083620`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083686`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400837cb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083686`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400837cb`
- `win32kbase!PushThreadGuardedObject` at `0x140083801`
- `win32kbase!PushThreadGuardedObject` at `0x140083827`
- `win32kbase!PushThreadGuardedObject` at `0x14008386e`
- `win32kbase!PushThreadGuardedObject` at `0x140083897`
- `win32kbase!PushThreadGuardedObject` at `0x140083801`
- `win32kbase!PushThreadGuardedObject` at `0x140083827`
- `win32kbase!PushThreadGuardedObject` at `0x14008386e`
- `win32kbase!PushThreadGuardedObject` at `0x140083897`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14008372c`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14008372c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083714`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083714`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083675`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083675`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreShared` at `0x140083662`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreShared` at `0x140083662`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400836d8`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x1400836d8`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400839c4`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1400839c4`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14008363f`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400836f2`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14008363f`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x1400836f2`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140083981`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140083981`
- `win32kbase!EtwDevLockEndTightUpdate` at `0x140083ad9`
- `win32kbase!EtwDevLockEndTightUpdate` at `0x140083ad9`
- `win32kbase!EtwDevLockEndUpdate` at `0x1400837bb`
- `win32kbase!EtwDevLockEndUpdate` at `0x1400837bb`
- `win32kbase!GreGetBounds` at `0x1400836b2`
- `win32kbase!GreGetBounds` at `0x1400836b2`

## pseudocode

```c
__int64 __fastcall GrepUpdateSpriteDevLockEnd(struct tagPOINT **a1, int a2)
{
  unsigned int v2; // r12d
  unsigned int updated; // r14d
  __int64 HDEV; // rax
  struct tagPOINT *v7; // r13
  HDEV v8; // rsi
  Gre::Base *v9; // rcx
  struct tagPOINT v10; // rbx
  struct tagPOINT *v12; // rcx
  struct tagSIZE v13; // rdx
  Gre::Base *v14; // rcx
  struct Gre::Base::SESSION_GLOBALS *v15; // rax
  struct tagPOINT *v16; // rdx
  struct tagRECT v17; // xmm0
  int v18; // r15d
  HDEV v19; // r13
  int v20; // r15d
  __int64 left; // r9
  struct tagRECT *v22; // rsi
  LONG top; // r8d
  LONG right; // edx
  LONG bottom; // eax
  struct tagPOINT *v26; // rdx
  int v27; // [rsp+80h] [rbp-80h]
  struct tagSIZE v28; // [rsp+88h] [rbp-78h] BYREF
  struct tagPOINT v29; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+98h] [rbp-68h]
  struct REGION *v31; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPOINT v32; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct tagPOINT *v34; // [rsp+C0h] [rbp-40h] BYREF
  int v35; // [rsp+C8h] [rbp-38h]
  struct Gre::Base::SESSION_GLOBALS *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  _OWORD v38[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v39[2]; // [rsp+100h] [rbp+0h] BYREF
  struct tagPOINT v40; // [rsp+120h] [rbp+20h]
  __int16 v41; // [rsp+128h] [rbp+28h]
  struct tagPOINT *v42; // [rsp+130h] [rbp+30h] BYREF
  int v43; // [rsp+138h] [rbp+38h]
  struct tagPOINT *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  _OWORD v46[2]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v47[2]; // [rsp+170h] [rbp+70h] BYREF
  struct tagPOINT v48; // [rsp+190h] [rbp+90h]
  __int16 v49; // [rsp+198h] [rbp+98h]
  struct tagRECT v50; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v51[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  struct tagRECT v52; // [rsp+1B4h] [rbp+B4h]
  char v53; // [rsp+1C4h] [rbp+C4h]
  __int64 v54; // [rsp+1E8h] [rbp+E8h]
  __int64 v55; // [rsp+200h] [rbp+100h]
  int v56; // [rsp+208h] [rbp+108h]
  int v57; // [rsp+230h] [rbp+130h]
  __int64 v58; // [rsp+240h] [rbp+140h]
  unsigned int v59; // [rsp+250h] [rbp+150h] BYREF
  _OWORD v60[20]; // [rsp+254h] [rbp+154h] BYREF

  v2 = 0;
  v30 = a2;
  updated = 0;
  HDEV = UserGetHDEV();
  v7 = a1[2];
  v8 = (HDEV)HDEV;
  v33[0] = HDEV;
  v29 = (struct tagPOINT)v7;
  if ( PDEVOBJ::bAllowShareAccess((PDEVOBJ *)v33) )
  {
    EtwTraceGreLockAcquireSemaphoreShared(L"Sprite", *(_QWORD *)v7 + 1040LL);
    GreAcquireSemaphoreSharedInternal((HSEMAPHORE)(*(_QWORD *)v7 + 1040LL));
    GrepAcquireLockValidate<6>();
  }
  if ( *((_QWORD *)Gre::Base::Globals(v9) + 28) )
  {
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GreGetBounds)(**a1, &v50, 4) )
    {
      v12 = *a1;
      v13 = (struct tagSIZE)(*a1)[64];
      v28 = v13;
      v31 = (struct REGION *)v12[148];
      if ( !v31 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))EtwDevLockEndUpdate)(
          *(_QWORD *)&v12[59],
          v13,
          (unsigned int)v28.cy,
          (unsigned int)v50.left,
          v50.top,
          v50.right,
          v50.bottom);
        v29 = 0;
        v15 = Gre::Base::Globals(v14);
        v37 = 0;
        v36 = v15;
        v34 = 0;
        v35 = 0;
        memset(v38, 0, sizeof(v38));
        PushThreadGuardedObject(
          v38,
          &v34,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v39, 0, sizeof(v39));
        PushThreadGuardedObject(
          v39,
          &v34,
          UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic);
        v44 = a1[2];
        v40 = 0;
        v41 = 1;
        v45 = 0;
        memset(v46, 0, sizeof(v46));
        v42 = 0;
        v43 = 0;
        PushThreadGuardedObject(
          v46,
          &v42,
          UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
        memset(v47, 0, sizeof(v47));
        PushThreadGuardedObject(
          v47,
          &v42,
          UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic);
        v16 = *a1;
        if ( *a1 )
          v48 = *v16;
        else
          v48 = 0;
        v49 = 256;
        v42 = v16;
        updated = GrepUpdateSprite(
                    v8,
                    *(HWND *)&v16[59],
                    0,
                    (struct OPTAPIDCOBJ *)&v34,
                    0,
                    &v28,
                    (struct OPTAPIDCOBJ *)&v42,
                    &v29,
                    0,
                    0,
                    0x40200000u,
                    &v50,
                    0,
                    1,
                    a2,
                    0);
        OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v42);
        OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v34);
        goto LABEL_5;
      }
      if ( (unsigned int)RGNOBJ::iComplexity((RGNOBJ *)&v31) != 1 )
      {
        RGNOBJ::bOffset((RGNOBJ *)&v31, (const struct _POINTL *)&(*a1)[((*a1)[5].x & 1LL) + 127]);
        v55 = 0;
        v56 = 0;
        v57 = 1;
        v58 = 0;
        v54 = 0;
        XCLIPOBJ::vSetup((XCLIPOBJ *)v51, v31, (const struct ERECTL *)&v50, 1);
        memset_0(&v59, 0, 0x144u);
        switch ( v53 )
        {
          case 0:
            v17 = v50;
            goto LABEL_19;
          case 1:
            v17 = v52;
LABEL_19:
            v18 = 0;
            v59 = 1;
            v60[0] = v17;
            v27 = 0;
LABEL_20:
            updated = 1;
            v19 = v8;
            if ( !v18 )
              goto LABEL_22;
            do
            {
              v18 = XCLIPOBJ::bEnum((XCLIPOBJ *)v51, 0x144u, &v59, 0);
              v27 = v18;
LABEL_22:
              if ( v59 )
              {
                v20 = v30;
                do
                {
                  left = (unsigned int)v50.left;
                  v22 = (struct tagRECT *)&v60[v2];
                  if ( v22->left < v50.left )
                    LODWORD(v60[v2]) = v50.left;
                  else
                    left = (unsigned int)v22->left;
                  top = v50.top;
                  if ( v22->top < v50.top )
                    v22->top = v50.top;
                  else
                    top = v22->top;
                  right = v50.right;
                  if ( v22->right > v50.right )
                    v22->right = v50.right;
                  else
                    right = v22->right;
                  bottom = v50.bottom;
                  if ( v22->bottom > v50.bottom )
                    v22->bottom = v50.bottom;
                  else
                    bottom = v22->bottom;
                  EtwDevLockEndTightUpdate(
                    *(_QWORD *)&(*a1)[59],
                    (unsigned int)v28.cx,
                    (unsigned int)v28.cy,
                    left,
                    top,
                    right,
                    bottom);
                  v32 = 0;
                  OPTAPIDCOBJ::OPTAPIDCOBJ((OPTAPIDCOBJ *)&v42, 0);
                  v36 = (struct Gre::Base::SESSION_GLOBALS *)a1[2];
                  v37 = 0;
                  v34 = 0;
                  v35 = 0;
                  UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(v38);
                  UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>(v39);
                  v26 = *a1;
                  if ( *a1 )
                    v40 = *v26;
                  else
                    v40 = 0;
                  v41 = 256;
                  v34 = v26;
                  updated &= -((unsigned int)GrepUpdateSprite(
                                               v19,
                                               *(HWND *)&v26[59],
                                               0,
                                               (struct OPTAPIDCOBJ *)&v42,
                                               0,
                                               &v28,
                                               (struct OPTAPIDCOBJ *)&v34,
                                               &v32,
                                               0,
                                               0,
                                               0x40200000u,
                                               v22,
                                               0,
                                               1,
                                               v20,
                                               0) != 0);
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v34);
                  OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v42);
                  ++v2;
                }
                while ( v2 < v59 );
                v18 = v27;
              }
              v2 = 0;
            }
            while ( v18 );
            v7 = (struct tagPOINT *)v29;
            break;
          case 3:
            v27 = 1;
            v18 = 1;
            XCLIPOBJ::cEnumStart((XCLIPOBJ *)v51, 0, 0, 4u, 0x14u);
            goto LABEL_20;
        }
      }
    }
LABEL_5:
    v29 = (*a1)[148];
    RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v29);
    (*a1)[148] = 0;
    goto LABEL_6;
  }
  GdiUpdateSpriteDevLockEnd((struct XDCOBJ *)a1);
LABEL_6:
  if ( PDEVOBJ::bAllowShareAccess((PDEVOBJ *)v33) )
  {
    v10 = *v7;
    EtwTraceGreLockReleaseSemaphore(L"Sprite", *(_QWORD *)v7 + 1040LL);
    GrepReleaseLockValidate<6>();
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(*(_QWORD *)&v10 + 1040LL));
  }
  return updated;
}

```

## disassembly

```asm
0x1400835e4  push    rbp
0x1400835e6  push    rbx
0x1400835e7  push    rsi
0x1400835e8  push    rdi
0x1400835e9  push    r12
0x1400835eb  push    r13
0x1400835ed  push    r14
0x1400835ef  push    r15
0x1400835f1  lea     rbp, [rsp-2B8h]
0x1400835f9  sub     rsp, 3B8h
0x140083600  mov     rax, cs:__security_cookie
0x140083607  xor     rax, rsp
0x14008360a  mov     [rbp+2F0h+var_50], rax
0x140083611  xor     r12d, r12d
0x140083614  mov     [rbp+2F0h+var_358], edx
0x140083617  mov     r14d, r12d
0x14008361a  mov     r15d, edx
0x14008361d  mov     rdi, rcx
0x140083620  call    cs:__imp_UserGetHDEV
0x140083627  nop     dword ptr [rax+rax+00h]
0x14008362c  mov     r13, [rdi+10h]
0x140083630  lea     rcx, [rbp+2F0h+var_340]
0x140083634  mov     rsi, rax
0x140083637  mov     [rbp+2F0h+var_340], rax
0x14008363b  mov     qword ptr [rbp+2F0h+var_360.x], r13
0x14008363f  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x140083646  nop     dword ptr [rax+rax+00h]
0x14008364b  test    eax, eax
0x14008364d  jz      short loc_140083686
0x14008364f  mov     rdx, [r13+0]
0x140083653  lea     rcx, aSprite; "Sprite"
0x14008365a  mov     ebx, 410h
0x14008365f  add     rdx, rbx
0x140083662  call    cs:__imp_EtwTraceGreLockAcquireSemaphoreShared
0x140083669  nop     dword ptr [rax+rax+00h]
0x14008366e  mov     rcx, [r13+0]
0x140083672  add     rcx, rbx
0x140083675  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14008367c  nop     dword ptr [rax+rax+00h]
0x140083681  call    ??$GrepAcquireLockValidate@$05@@YAXXZ; GrepAcquireLockValidate<6>(void)
0x140083686  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14008368d  nop     dword ptr [rax+rax+00h]
0x140083692  cmp     [rax+0E0h], r12
0x140083699  jz      loc_14008375F
0x14008369f  mov     rcx, [rdi]
0x1400836a2  lea     rdx, [rbp+2F0h+var_250]
0x1400836a9  mov     r8d, 4
0x1400836af  mov     rcx, [rcx]
0x1400836b2  call    cs:__imp_GreGetBounds
0x1400836b9  nop     dword ptr [rax+rax+00h]
0x1400836be  test    eax, eax
0x1400836c0  jnz     loc_140083769
0x1400836c6  mov     rcx, [rdi]
0x1400836c9  mov     rdx, [rcx+4A0h]
0x1400836d0  lea     rcx, [rbp+2F0h+var_360]
0x1400836d4  mov     qword ptr [rbp+2F0h+var_360.x], rdx
0x1400836d8  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x1400836df  nop     dword ptr [rax+rax+00h]
0x1400836e4  mov     rcx, [rdi]
0x1400836e7  mov     [rcx+4A0h], r12
0x1400836ee  lea     rcx, [rbp+2F0h+var_340]
0x1400836f2  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x1400836f9  nop     dword ptr [rax+rax+00h]
0x1400836fe  test    eax, eax
0x140083700  jz      short loc_140083738
0x140083702  mov     rbx, [r13+0]
0x140083706  lea     rcx, aSprite; "Sprite"
0x14008370d  lea     rdx, [rbx+410h]
0x140083714  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14008371b  nop     dword ptr [rax+rax+00h]
0x140083720  call    ??$GrepReleaseLockValidate@$05@@YAXXZ; GrepReleaseLockValidate<6>(void)
0x140083725  lea     rcx, [rbx+410h]
0x14008372c  call    cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140083733  nop     dword ptr [rax+rax+00h]
0x140083738  mov     eax, r14d
0x14008373b  mov     rcx, [rbp+2F0h+var_50]
0x140083742  xor     rcx, rsp; StackCookie
0x140083745  call    __security_check_cookie
0x14008374a  add     rsp, 3B8h
0x140083751  pop     r15
0x140083753  pop     r14
0x140083755  pop     r13
0x140083757  pop     r12
0x140083759  pop     rdi
0x14008375a  pop     rsi
0x14008375b  pop     rbx
0x14008375c  pop     rbp
0x14008375d  retn
0x14008375f  mov     rcx, rdi; struct XDCOBJ *
0x140083762  call    ?GdiUpdateSpriteDevLockEnd@@YAHAEAVXDCOBJ@@@Z; GdiUpdateSpriteDevLockEnd(XDCOBJ &)
0x140083767  jmp     short loc_1400836EE
0x140083769  mov     rcx, [rdi]
0x14008376c  mov     rdx, [rcx+200h]
0x140083773  mov     qword ptr [rbp+2F0h+var_368.cx], rdx
0x140083777  mov     rax, [rcx+4A0h]
0x14008377e  mov     [rbp+2F0h+var_350], rax
0x140083782  test    rax, rax
0x140083785  jnz     loc_140083953
0x14008378b  mov     eax, [rbp+2F0h+var_250.bottom]
0x140083791  mov     r9d, [rbp+2F0h+var_250.left]
0x140083798  mov     r8d, [rbp+2F0h+var_368.cy]
0x14008379c  mov     rcx, [rcx+1D8h]
0x1400837a3  mov     dword ptr [rsp+3F0h+var_3C0], eax
0x1400837a7  mov     eax, [rbp+2F0h+var_250.right]
0x1400837ad  mov     dword ptr [rsp+3F0h+var_3C8], eax
0x1400837b1  mov     eax, [rbp+2F0h+var_250.top]
0x1400837b7  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x1400837bb  call    cs:__imp_EtwDevLockEndUpdate
0x1400837c2  nop     dword ptr [rax+rax+00h]
0x1400837c7  mov     qword ptr [rbp+2F0h+var_360.x], r12
0x1400837cb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400837d2  nop     dword ptr [rax+rax+00h]
0x1400837d7  xorps   xmm0, xmm0
0x1400837da  mov     [rbp+2F0h+var_318], r12
0x1400837de  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400837e5  mov     [rbp+2F0h+var_320], rax
0x1400837e9  lea     rdx, [rbp+2F0h+var_330]
0x1400837ed  mov     [rbp+2F0h+var_330], r12
0x1400837f1  lea     rcx, [rbp+2F0h+var_310]
0x1400837f5  mov     [rbp+2F0h+var_328], r12d
0x1400837f9  movups  [rbp+2F0h+var_310], xmm0
0x1400837fd  movups  [rbp+2F0h+var_300], xmm0
0x140083801  call    cs:__imp_PushThreadGuardedObject
0x140083808  nop     dword ptr [rax+rax+00h]
0x14008380d  xorps   xmm0, xmm0
0x140083810  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140083817  lea     rdx, [rbp+2F0h+var_330]
0x14008381b  lea     rcx, [rbp+2F0h+var_2F0]
0x14008381f  movups  [rbp+2F0h+var_2F0], xmm0
0x140083823  movups  [rbp+2F0h+var_2E0], xmm0
0x140083827  call    cs:__imp_PushThreadGuardedObject
0x14008382e  nop     dword ptr [rax+rax+00h]
0x140083833  mov     rax, [rdi+10h]
0x140083837  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14008383e  xorps   xmm0, xmm0
0x140083841  mov     [rbp+2F0h+var_2B0], rax
0x140083845  mov     ebx, 1
0x14008384a  mov     [rbp+2F0h+var_2D0], r12
0x14008384e  lea     rdx, [rbp+2F0h+var_2C0]
0x140083852  mov     [rbp+2F0h+var_2C8], bx
0x140083856  lea     rcx, [rbp+2F0h+var_2A0]
0x14008385a  mov     [rbp+2F0h+var_2A8], r12
0x14008385e  movups  [rbp+2F0h+var_2A0], xmm0
0x140083862  mov     [rbp+2F0h+var_2C0], r12
0x140083866  movups  [rbp+2F0h+var_290], xmm0
0x14008386a  mov     [rbp+2F0h+var_2B8], r12d
0x14008386e  call    cs:__imp_PushThreadGuardedObject
0x140083875  nop     dword ptr [rax+rax+00h]
0x14008387a  xorps   xmm0, xmm0
0x14008387d  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140083884  lea     rdx, [rbp+2F0h+var_2C0]
0x140083888  lea     rcx, [rbp+2F0h+var_280]
0x14008388c  movups  [rbp+2F0h+var_280], xmm0
0x140083890  movups  [rbp+2F0h+var_270], xmm0
0x140083897  call    cs:__imp_PushThreadGuardedObject
0x14008389e  nop     dword ptr [rax+rax+00h]
0x1400838a3  mov     rdx, [rdi]
0x1400838a6  test    rdx, rdx
0x1400838a9  jz      loc_140083947
0x1400838af  mov     rax, [rdx]
0x1400838b2  mov     [rbp+2F0h+var_260], rax
0x1400838b9  mov     [rsp+3F0h+var_378], r12d; unsigned int
0x1400838be  lea     rax, [rbp+2F0h+var_250]
0x1400838c5  mov     [rsp+3F0h+var_380], r15d; int
0x1400838ca  lea     r9, [rbp+2F0h+var_330]; struct OPTAPIDCOBJ *
0x1400838ce  mov     [rsp+3F0h+var_388], ebx; int
0x1400838d2  xor     r8d, r8d; void *
0x1400838d5  mov     [rsp+3F0h+var_390], r12; struct tagMINIWINDOWINFO *
0x1400838da  mov     rcx, rsi; HDEV
0x1400838dd  mov     [rsp+3F0h+var_398], rax; struct tagRECT *
0x1400838e2  lea     rax, [rbp+2F0h+var_360]
0x1400838e6  mov     [rsp+3F0h+var_3A0], 40200000h; unsigned int
0x1400838ee  mov     [rsp+3F0h+var_3A8], r12; struct _BLENDFUNCTION *
0x1400838f3  mov     [rsp+3F0h+var_3B0], r12d; unsigned int
0x1400838f8  mov     [rsp+3F0h+var_3B8], rax; struct tagPOINT *
0x1400838fd  lea     rax, [rbp+2F0h+var_2C0]
0x140083901  mov     [rsp+3F0h+var_3C0], rax; struct OPTAPIDCOBJ *
0x140083906  lea     rax, [rbp+2F0h+var_368]
0x14008390a  mov     [rbp+2F0h+var_258], 100h
0x140083913  mov     [rbp+2F0h+var_2C0], rdx
0x140083917  mov     rdx, [rdx+1D8h]; HWND
0x14008391e  mov     [rsp+3F0h+var_3C8], rax; struct tagSIZE *
0x140083923  mov     [rsp+3F0h+var_3D0], r12; struct tagPOINT *
0x140083928  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x14008392d  lea     rcx, [rbp+2F0h+var_2C0]; this
0x140083931  mov     r14d, eax
0x140083934  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140083939  lea     rcx, [rbp+2F0h+var_330]; this
0x14008393d  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140083942  jmp     loc_1400836C6
0x140083947  mov     [rbp+2F0h+var_260], r12
0x14008394e  jmp     loc_1400838B9
0x140083953  lea     rcx, [rbp+2F0h+var_350]; this
0x140083957  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14008395c  mov     ebx, 1
0x140083961  cmp     eax, ebx
0x140083963  jz      loc_1400836C6
0x140083969  mov     rcx, [rdi]
0x14008396c  mov     eax, [rcx+28h]
0x14008396f  add     rcx, 3F8h
0x140083976  and     rax, rbx
0x140083979  lea     rdx, [rcx+rax*8]
0x14008397d  lea     rcx, [rbp+2F0h+var_350]
0x140083981  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x140083988  nop     dword ptr [rax+rax+00h]
0x14008398d  mov     rdx, [rbp+2F0h+var_350]
0x140083991  lea     r8, [rbp+2F0h+var_250]
0x140083998  mov     r9d, ebx
0x14008399b  mov     [rbp+2F0h+var_1F0], r12
0x1400839a2  lea     rcx, [rbp+2F0h+var_240]
0x1400839a9  mov     [rbp+2F0h+var_1E8], r12d
0x1400839b0  mov     [rbp+2F0h+var_1C0], ebx
0x1400839b6  mov     [rbp+2F0h+var_1B0], r12
0x1400839bd  mov     [rbp+2F0h+var_208], r12
0x1400839c4  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x1400839cb  nop     dword ptr [rax+rax+00h]
0x1400839d0  xor     edx, edx; Val
0x1400839d2  lea     rcx, [rbp+2F0h+var_1A0]; void *
0x1400839d9  mov     r8d, 144h; Size
0x1400839df  call    memset_0
0x1400839e4  movzx   ecx, [rbp+2F0h+var_22C]
0x1400839eb  test    ecx, ecx
0x1400839ed  jz      loc_140083C18
0x1400839f3  sub     ecx, ebx
0x1400839f5  jnz     loc_140083BE7
0x1400839fb  movups  xmm0, [rbp+2F0h+var_23C]
0x140083a02  mov     r15d, r12d
0x140083a05  mov     [rbp+2F0h+var_1A0], ebx
0x140083a0b  movdqu  [rbp+2F0h+var_19C], xmm0
0x140083a13  mov     [rbp+2F0h+var_370], r12d
0x140083a17  mov     r14d, ebx
0x140083a1a  mov     r13, rsi
0x140083a1d  test    r15d, r15d
0x140083a20  jz      short loc_140083A43
0x140083a22  xor     r9d, r9d; unsigned int *
0x140083a25  lea     r8, [rbp+2F0h+var_1A0]; void *
0x140083a2c  mov     edx, 144h; unsigned int
0x140083a31  lea     rcx, [rbp+2F0h+var_240]; this
0x140083a38  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x140083a3d  mov     r15d, eax
0x140083a40  mov     [rbp+2F0h+var_370], eax
0x140083a43  cmp     [rbp+2F0h+var_1A0], 0
0x140083a4a  jbe     loc_140083BC9
0x140083a50  mov     r15d, [rbp+2F0h+var_358]
0x140083a54  mov     r9d, [rbp+2F0h+var_250.left]
0x140083a5b  lea     rsi, [rbp+2F0h+var_19C]
0x140083a62  mov     eax, r12d
0x140083a65  shl     rax, 4
0x140083a69  add     rsi, rax
0x140083a6c  mov     ecx, dword ptr [rbp+rax+2F0h+var_19C]
0x140083a73  cmp     ecx, r9d
0x140083a76  jl      loc_140083C24
0x140083a7c  mov     r9d, ecx
0x140083a7f  mov     eax, [rsi+4]
0x140083a82  mov     r8d, [rbp+2F0h+var_250.top]
0x140083a89  cmp     eax, r8d
0x140083a8c  jl      loc_140083C31
0x140083a92  mov     r8d, eax
0x140083a95  mov     eax, [rsi+8]
0x140083a98  mov     edx, [rbp+2F0h+var_250.right]
0x140083a9e  cmp     eax, edx
0x140083aa0  jg      loc_140083C3A
0x140083aa6  mov     edx, eax
0x140083aa8  mov     ecx, [rsi+0Ch]
0x140083aab  mov     eax, [rbp+2F0h+var_250.bottom]
0x140083ab1  cmp     ecx, eax
0x140083ab3  jg      loc_140083C42
0x140083ab9  mov     eax, ecx
0x140083abb  mov     rcx, [rdi]
0x140083abe  mov     dword ptr [rsp+3F0h+var_3C0], eax
0x140083ac2  mov     dword ptr [rsp+3F0h+var_3C8], edx
0x140083ac6  mov     edx, [rbp+2F0h+var_368.cx]
0x140083ac9  mov     rcx, [rcx+1D8h]
0x140083ad0  mov     dword ptr [rsp+3F0h+var_3D0], r8d
0x140083ad5  mov     r8d, [rbp+2F0h+var_368.cy]
0x140083ad9  call    cs:__imp_EtwDevLockEndTightUpdate
0x140083ae0  nop     dword ptr [rax+rax+00h]
0x140083ae5  xor     edx, edx; HDC
0x140083ae7  mov     qword ptr [rbp+2F0h+var_348.x], 0
0x140083aef  lea     rcx, [rbp+2F0h+var_2C0]; this
0x140083af3  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x140083af8  mov     rax, [rdi+10h]
0x140083afc  lea     rcx, [rbp+2F0h+var_310]
0x140083b00  mov     [rbp+2F0h+var_320], rax
0x140083b04  xor     eax, eax
0x140083b06  mov     [rbp+2F0h+var_318], rax
0x140083b0a  mov     [rbp+2F0h+var_330], rax
0x140083b0e  mov     [rbp+2F0h+var_328], eax
0x140083b11  call    ??0?$UnexpectedThreadTerminationHandler@VDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(void)
0x140083b16  lea     rcx, [rbp+2F0h+var_2F0]
0x140083b1a  call    ??0?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>(void)
0x140083b1f  mov     rdx, [rdi]
0x140083b22  xor     ecx, ecx
0x140083b24  test    rdx, rdx
0x140083b27  jz      loc_140083BDE
0x140083b2d  mov     rax, [rdx]
0x140083b30  mov     [rbp+2F0h+var_2D0], rax
0x140083b34  mov     [rsp+3F0h+var_378], ecx; unsigned int
0x140083b38  lea     rax, [rbp+2F0h+var_348]
0x140083b3c  mov     [rsp+3F0h+var_380], r15d; int
  ... truncated ...
```
