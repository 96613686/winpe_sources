# GrepUpdateSpriteDevLockEnd(XDCOBJ &,int)

- ea: `0x14005e5d4`
- end: `0x14005ec3a`
- name: `?GrepUpdateSpriteDevLockEnd@@YAHAEAVXDCOBJ@@H@Z`
- size: `1638`
- prototype: `__int64 __fastcall(struct tagPOINT **, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140057a4c`
- `0x14005d6e0`

## callees

- `0x140016e74`
- `0x14005b938`
- `0x14005e498`
- `0x14005e544`
- `0x14005e5d4`
- `0x14005f52c`
- `0x140069870`
- `0x1400698b4`
- `0x140069bc8`
- `0x140075244`
- `0x1400a7100`
- `0x1400fc340`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `win32kbase!UserGetHDEV` at `0x14005e610`
- `win32kbase!UserGetHDEV` at `0x14005e610`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e676`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e7bb`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e676`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e7bb`
- `win32kbase!PushThreadGuardedObject` at `0x14005e7f1`
- `win32kbase!PushThreadGuardedObject` at `0x14005e817`
- `win32kbase!PushThreadGuardedObject` at `0x14005e85e`
- `win32kbase!PushThreadGuardedObject` at `0x14005e887`
- `win32kbase!PushThreadGuardedObject` at `0x14005e7f1`
- `win32kbase!PushThreadGuardedObject` at `0x14005e817`
- `win32kbase!PushThreadGuardedObject` at `0x14005e85e`
- `win32kbase!PushThreadGuardedObject` at `0x14005e887`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005e71c`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005e71c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005e704`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005e704`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005e665`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005e665`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreShared` at `0x14005e652`
- `win32kbase!EtwTraceGreLockAcquireSemaphoreShared` at `0x14005e652`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005e6c8`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14005e6c8`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005e9b4`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14005e9b4`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14005e62f`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14005e6e2`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14005e62f`
- `win32kbase!?bAllowShareAccess@PDEVOBJ@@QEBAHXZ` at `0x14005e6e2`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14005e971`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x14005e971`
- `win32kbase!EtwDevLockEndTightUpdate` at `0x14005eac9`
- `win32kbase!EtwDevLockEndTightUpdate` at `0x14005eac9`
- `win32kbase!EtwDevLockEndUpdate` at `0x14005e7ab`
- `win32kbase!EtwDevLockEndUpdate` at `0x14005e7ab`
- `win32kbase!GreGetBounds` at `0x14005e6a2`
- `win32kbase!GreGetBounds` at `0x14005e6a2`

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
0x14005e5d4  push    rbp
0x14005e5d6  push    rbx
0x14005e5d7  push    rsi
0x14005e5d8  push    rdi
0x14005e5d9  push    r12
0x14005e5db  push    r13
0x14005e5dd  push    r14
0x14005e5df  push    r15
0x14005e5e1  lea     rbp, [rsp-2B8h]
0x14005e5e9  sub     rsp, 3B8h
0x14005e5f0  mov     rax, cs:__security_cookie
0x14005e5f7  xor     rax, rsp
0x14005e5fa  mov     [rbp+2F0h+var_50], rax
0x14005e601  xor     r12d, r12d
0x14005e604  mov     [rbp+2F0h+var_358], edx
0x14005e607  mov     r14d, r12d
0x14005e60a  mov     r15d, edx
0x14005e60d  mov     rdi, rcx
0x14005e610  call    cs:__imp_UserGetHDEV
0x14005e617  nop     dword ptr [rax+rax+00h]
0x14005e61c  mov     r13, [rdi+10h]
0x14005e620  lea     rcx, [rbp+2F0h+var_340]
0x14005e624  mov     rsi, rax
0x14005e627  mov     [rbp+2F0h+var_340], rax
0x14005e62b  mov     qword ptr [rbp+2F0h+var_360.x], r13
0x14005e62f  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x14005e636  nop     dword ptr [rax+rax+00h]
0x14005e63b  test    eax, eax
0x14005e63d  jz      short loc_14005E676
0x14005e63f  mov     rdx, [r13+0]
0x14005e643  lea     rcx, aSprite; "Sprite"
0x14005e64a  mov     ebx, 410h
0x14005e64f  add     rdx, rbx
0x14005e652  call    cs:__imp_EtwTraceGreLockAcquireSemaphoreShared
0x14005e659  nop     dword ptr [rax+rax+00h]
0x14005e65e  mov     rcx, [r13+0]
0x14005e662  add     rcx, rbx
0x14005e665  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14005e66c  nop     dword ptr [rax+rax+00h]
0x14005e671  call    ??$GrepAcquireLockValidate@$05@@YAXXZ; GrepAcquireLockValidate<6>(void)
0x14005e676  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005e67d  nop     dword ptr [rax+rax+00h]
0x14005e682  cmp     [rax+0E0h], r12
0x14005e689  jz      loc_14005E74F
0x14005e68f  mov     rcx, [rdi]
0x14005e692  lea     rdx, [rbp+2F0h+var_250]
0x14005e699  mov     r8d, 4
0x14005e69f  mov     rcx, [rcx]
0x14005e6a2  call    cs:__imp_GreGetBounds
0x14005e6a9  nop     dword ptr [rax+rax+00h]
0x14005e6ae  test    eax, eax
0x14005e6b0  jnz     loc_14005E759
0x14005e6b6  mov     rcx, [rdi]
0x14005e6b9  mov     rdx, [rcx+4A0h]
0x14005e6c0  lea     rcx, [rbp+2F0h+var_360]
0x14005e6c4  mov     qword ptr [rbp+2F0h+var_360.x], rdx
0x14005e6c8  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14005e6cf  nop     dword ptr [rax+rax+00h]
0x14005e6d4  mov     rcx, [rdi]
0x14005e6d7  mov     [rcx+4A0h], r12
0x14005e6de  lea     rcx, [rbp+2F0h+var_340]
0x14005e6e2  call    cs:__imp_?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x14005e6e9  nop     dword ptr [rax+rax+00h]
0x14005e6ee  test    eax, eax
0x14005e6f0  jz      short loc_14005E728
0x14005e6f2  mov     rbx, [r13+0]
0x14005e6f6  lea     rcx, aSprite; "Sprite"
0x14005e6fd  lea     rdx, [rbx+410h]
0x14005e704  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14005e70b  nop     dword ptr [rax+rax+00h]
0x14005e710  call    ??$GrepReleaseLockValidate@$05@@YAXXZ; GrepReleaseLockValidate<6>(void)
0x14005e715  lea     rcx, [rbx+410h]
0x14005e71c  call    cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14005e723  nop     dword ptr [rax+rax+00h]
0x14005e728  mov     eax, r14d
0x14005e72b  mov     rcx, [rbp+2F0h+var_50]
0x14005e732  xor     rcx, rsp; StackCookie
0x14005e735  call    __security_check_cookie
0x14005e73a  add     rsp, 3B8h
0x14005e741  pop     r15
0x14005e743  pop     r14
0x14005e745  pop     r13
0x14005e747  pop     r12
0x14005e749  pop     rdi
0x14005e74a  pop     rsi
0x14005e74b  pop     rbx
0x14005e74c  pop     rbp
0x14005e74d  retn
0x14005e74f  mov     rcx, rdi; struct XDCOBJ *
0x14005e752  call    ?GdiUpdateSpriteDevLockEnd@@YAHAEAVXDCOBJ@@@Z; GdiUpdateSpriteDevLockEnd(XDCOBJ &)
0x14005e757  jmp     short loc_14005E6DE
0x14005e759  mov     rcx, [rdi]
0x14005e75c  mov     rdx, [rcx+200h]
0x14005e763  mov     qword ptr [rbp+2F0h+var_368.cx], rdx
0x14005e767  mov     rax, [rcx+4A0h]
0x14005e76e  mov     [rbp+2F0h+var_350], rax
0x14005e772  test    rax, rax
0x14005e775  jnz     loc_14005E943
0x14005e77b  mov     eax, [rbp+2F0h+var_250.bottom]
0x14005e781  mov     r9d, [rbp+2F0h+var_250.left]
0x14005e788  mov     r8d, [rbp+2F0h+var_368.cy]
0x14005e78c  mov     rcx, [rcx+1D8h]
0x14005e793  mov     dword ptr [rsp+3F0h+var_3C0], eax
0x14005e797  mov     eax, [rbp+2F0h+var_250.right]
0x14005e79d  mov     dword ptr [rsp+3F0h+var_3C8], eax
0x14005e7a1  mov     eax, [rbp+2F0h+var_250.top]
0x14005e7a7  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x14005e7ab  call    cs:__imp_EtwDevLockEndUpdate
0x14005e7b2  nop     dword ptr [rax+rax+00h]
0x14005e7b7  mov     qword ptr [rbp+2F0h+var_360.x], r12
0x14005e7bb  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005e7c2  nop     dword ptr [rax+rax+00h]
0x14005e7c7  xorps   xmm0, xmm0
0x14005e7ca  mov     [rbp+2F0h+var_318], r12
0x14005e7ce  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005e7d5  mov     [rbp+2F0h+var_320], rax
0x14005e7d9  lea     rdx, [rbp+2F0h+var_330]
0x14005e7dd  mov     [rbp+2F0h+var_330], r12
0x14005e7e1  lea     rcx, [rbp+2F0h+var_310]
0x14005e7e5  mov     [rbp+2F0h+var_328], r12d
0x14005e7e9  movups  [rbp+2F0h+var_310], xmm0
0x14005e7ed  movups  [rbp+2F0h+var_300], xmm0
0x14005e7f1  call    cs:__imp_PushThreadGuardedObject
0x14005e7f8  nop     dword ptr [rax+rax+00h]
0x14005e7fd  xorps   xmm0, xmm0
0x14005e800  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005e807  lea     rdx, [rbp+2F0h+var_330]
0x14005e80b  lea     rcx, [rbp+2F0h+var_2F0]
0x14005e80f  movups  [rbp+2F0h+var_2F0], xmm0
0x14005e813  movups  [rbp+2F0h+var_2E0], xmm0
0x14005e817  call    cs:__imp_PushThreadGuardedObject
0x14005e81e  nop     dword ptr [rax+rax+00h]
0x14005e823  mov     rax, [rdi+10h]
0x14005e827  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005e82e  xorps   xmm0, xmm0
0x14005e831  mov     [rbp+2F0h+var_2B0], rax
0x14005e835  mov     ebx, 1
0x14005e83a  mov     [rbp+2F0h+var_2D0], r12
0x14005e83e  lea     rdx, [rbp+2F0h+var_2C0]
0x14005e842  mov     [rbp+2F0h+var_2C8], bx
0x14005e846  lea     rcx, [rbp+2F0h+var_2A0]
0x14005e84a  mov     [rbp+2F0h+var_2A8], r12
0x14005e84e  movups  [rbp+2F0h+var_2A0], xmm0
0x14005e852  mov     [rbp+2F0h+var_2C0], r12
0x14005e856  movups  [rbp+2F0h+var_290], xmm0
0x14005e85a  mov     [rbp+2F0h+var_2B8], r12d
0x14005e85e  call    cs:__imp_PushThreadGuardedObject
0x14005e865  nop     dword ptr [rax+rax+00h]
0x14005e86a  xorps   xmm0, xmm0
0x14005e86d  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005e874  lea     rdx, [rbp+2F0h+var_2C0]
0x14005e878  lea     rcx, [rbp+2F0h+var_280]
0x14005e87c  movups  [rbp+2F0h+var_280], xmm0
0x14005e880  movups  [rbp+2F0h+var_270], xmm0
0x14005e887  call    cs:__imp_PushThreadGuardedObject
0x14005e88e  nop     dword ptr [rax+rax+00h]
0x14005e893  mov     rdx, [rdi]
0x14005e896  test    rdx, rdx
0x14005e899  jz      loc_14005E937
0x14005e89f  mov     rax, [rdx]
0x14005e8a2  mov     [rbp+2F0h+var_260], rax
0x14005e8a9  mov     [rsp+3F0h+var_378], r12d; unsigned int
0x14005e8ae  lea     rax, [rbp+2F0h+var_250]
0x14005e8b5  mov     [rsp+3F0h+var_380], r15d; int
0x14005e8ba  lea     r9, [rbp+2F0h+var_330]; struct OPTAPIDCOBJ *
0x14005e8be  mov     [rsp+3F0h+var_388], ebx; int
0x14005e8c2  xor     r8d, r8d; void *
0x14005e8c5  mov     [rsp+3F0h+var_390], r12; struct tagMINIWINDOWINFO *
0x14005e8ca  mov     rcx, rsi; HDEV
0x14005e8cd  mov     [rsp+3F0h+var_398], rax; struct tagRECT *
0x14005e8d2  lea     rax, [rbp+2F0h+var_360]
0x14005e8d6  mov     [rsp+3F0h+var_3A0], 40200000h; unsigned int
0x14005e8de  mov     [rsp+3F0h+var_3A8], r12; struct _BLENDFUNCTION *
0x14005e8e3  mov     [rsp+3F0h+var_3B0], r12d; unsigned int
0x14005e8e8  mov     [rsp+3F0h+var_3B8], rax; struct tagPOINT *
0x14005e8ed  lea     rax, [rbp+2F0h+var_2C0]
0x14005e8f1  mov     [rsp+3F0h+var_3C0], rax; struct OPTAPIDCOBJ *
0x14005e8f6  lea     rax, [rbp+2F0h+var_368]
0x14005e8fa  mov     [rbp+2F0h+var_258], 100h
0x14005e903  mov     [rbp+2F0h+var_2C0], rdx
0x14005e907  mov     rdx, [rdx+1D8h]; HWND
0x14005e90e  mov     [rsp+3F0h+var_3C8], rax; struct tagSIZE *
0x14005e913  mov     [rsp+3F0h+var_3D0], r12; struct tagPOINT *
0x14005e918  call    ?GrepUpdateSprite@@YAHPEAUHDEV__@@PEAUHWND__@@PEAXAEAVOPTAPIDCOBJ@@PEAUtagPOINT@@PEAUtagSIZE@@34KPEAU_BLENDFUNCTION@@KPEAUtagRECT@@PEAUtagMINIWINDOWINFO@@HHK@Z; GrepUpdateSprite(HDEV__ *,HWND__ *,void *,OPTAPIDCOBJ &,tagPOINT *,tagSIZE *,OPTAPIDCOBJ &,tagPOINT *,ulong,_BLENDFUNCTION *,ulong,tagRECT *,tagMINIWINDOWINFO *,int,int,ulong)
0x14005e91d  lea     rcx, [rbp+2F0h+var_2C0]; this
0x14005e921  mov     r14d, eax
0x14005e924  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14005e929  lea     rcx, [rbp+2F0h+var_330]; this
0x14005e92d  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x14005e932  jmp     loc_14005E6B6
0x14005e937  mov     [rbp+2F0h+var_260], r12
0x14005e93e  jmp     loc_14005E8A9
0x14005e943  lea     rcx, [rbp+2F0h+var_350]; this
0x14005e947  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x14005e94c  mov     ebx, 1
0x14005e951  cmp     eax, ebx
0x14005e953  jz      loc_14005E6B6
0x14005e959  mov     rcx, [rdi]
0x14005e95c  mov     eax, [rcx+28h]
0x14005e95f  add     rcx, 3F8h
0x14005e966  and     rax, rbx
0x14005e969  lea     rdx, [rcx+rax*8]
0x14005e96d  lea     rcx, [rbp+2F0h+var_350]
0x14005e971  call    cs:__imp_?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z; RGNOBJ::bOffset(_POINTL const *)
0x14005e978  nop     dword ptr [rax+rax+00h]
0x14005e97d  mov     rdx, [rbp+2F0h+var_350]
0x14005e981  lea     r8, [rbp+2F0h+var_250]
0x14005e988  mov     r9d, ebx
0x14005e98b  mov     [rbp+2F0h+var_1F0], r12
0x14005e992  lea     rcx, [rbp+2F0h+var_240]
0x14005e999  mov     [rbp+2F0h+var_1E8], r12d
0x14005e9a0  mov     [rbp+2F0h+var_1C0], ebx
0x14005e9a6  mov     [rbp+2F0h+var_1B0], r12
0x14005e9ad  mov     [rbp+2F0h+var_208], r12
0x14005e9b4  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14005e9bb  nop     dword ptr [rax+rax+00h]
0x14005e9c0  xor     edx, edx; Val
0x14005e9c2  lea     rcx, [rbp+2F0h+var_1A0]; void *
0x14005e9c9  mov     r8d, 144h; Size
0x14005e9cf  call    memset_0
0x14005e9d4  movzx   ecx, [rbp+2F0h+var_22C]
0x14005e9db  test    ecx, ecx
0x14005e9dd  jz      loc_14005EC08
0x14005e9e3  sub     ecx, ebx
0x14005e9e5  jnz     loc_14005EBD7
0x14005e9eb  movups  xmm0, [rbp+2F0h+var_23C]
0x14005e9f2  mov     r15d, r12d
0x14005e9f5  mov     [rbp+2F0h+var_1A0], ebx
0x14005e9fb  movdqu  [rbp+2F0h+var_19C], xmm0
0x14005ea03  mov     [rbp+2F0h+var_370], r12d
0x14005ea07  mov     r14d, ebx
0x14005ea0a  mov     r13, rsi
0x14005ea0d  test    r15d, r15d
0x14005ea10  jz      short loc_14005EA33
0x14005ea12  xor     r9d, r9d; unsigned int *
0x14005ea15  lea     r8, [rbp+2F0h+var_1A0]; void *
0x14005ea1c  mov     edx, 144h; unsigned int
0x14005ea21  lea     rcx, [rbp+2F0h+var_240]; this
0x14005ea28  call    ?bEnum@XCLIPOBJ@@QEAAHKPEAXPEAK@Z; XCLIPOBJ::bEnum(ulong,void *,ulong *)
0x14005ea2d  mov     r15d, eax
0x14005ea30  mov     [rbp+2F0h+var_370], eax
0x14005ea33  cmp     [rbp+2F0h+var_1A0], 0
0x14005ea3a  jbe     loc_14005EBB9
0x14005ea40  mov     r15d, [rbp+2F0h+var_358]
0x14005ea44  mov     r9d, [rbp+2F0h+var_250.left]
0x14005ea4b  lea     rsi, [rbp+2F0h+var_19C]
0x14005ea52  mov     eax, r12d
0x14005ea55  shl     rax, 4
0x14005ea59  add     rsi, rax
0x14005ea5c  mov     ecx, dword ptr [rbp+rax+2F0h+var_19C]
0x14005ea63  cmp     ecx, r9d
0x14005ea66  jl      loc_14005EC14
0x14005ea6c  mov     r9d, ecx
0x14005ea6f  mov     eax, [rsi+4]
0x14005ea72  mov     r8d, [rbp+2F0h+var_250.top]
0x14005ea79  cmp     eax, r8d
0x14005ea7c  jl      loc_14005EC21
0x14005ea82  mov     r8d, eax
0x14005ea85  mov     eax, [rsi+8]
0x14005ea88  mov     edx, [rbp+2F0h+var_250.right]
0x14005ea8e  cmp     eax, edx
0x14005ea90  jg      loc_14005EC2A
0x14005ea96  mov     edx, eax
0x14005ea98  mov     ecx, [rsi+0Ch]
0x14005ea9b  mov     eax, [rbp+2F0h+var_250.bottom]
0x14005eaa1  cmp     ecx, eax
0x14005eaa3  jg      loc_14005EC32
0x14005eaa9  mov     eax, ecx
0x14005eaab  mov     rcx, [rdi]
0x14005eaae  mov     dword ptr [rsp+3F0h+var_3C0], eax
0x14005eab2  mov     dword ptr [rsp+3F0h+var_3C8], edx
0x14005eab6  mov     edx, [rbp+2F0h+var_368.cx]
0x14005eab9  mov     rcx, [rcx+1D8h]
0x14005eac0  mov     dword ptr [rsp+3F0h+var_3D0], r8d
0x14005eac5  mov     r8d, [rbp+2F0h+var_368.cy]
0x14005eac9  call    cs:__imp_EtwDevLockEndTightUpdate
0x14005ead0  nop     dword ptr [rax+rax+00h]
0x14005ead5  xor     edx, edx; HDC
0x14005ead7  mov     qword ptr [rbp+2F0h+var_348.x], 0
0x14005eadf  lea     rcx, [rbp+2F0h+var_2C0]; this
0x14005eae3  call    ??0OPTAPIDCOBJ@@QEAA@PEAUHDC__@@@Z; OPTAPIDCOBJ::OPTAPIDCOBJ(HDC__ *)
0x14005eae8  mov     rax, [rdi+10h]
0x14005eaec  lea     rcx, [rbp+2F0h+var_310]
0x14005eaf0  mov     [rbp+2F0h+var_320], rax
0x14005eaf4  xor     eax, eax
0x14005eaf6  mov     [rbp+2F0h+var_318], rax
0x14005eafa  mov     [rbp+2F0h+var_330], rax
0x14005eafe  mov     [rbp+2F0h+var_328], eax
0x14005eb01  call    ??0?$UnexpectedThreadTerminationHandler@VDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<DCOBJ>::UnexpectedThreadTerminationHandler<DCOBJ>(void)
0x14005eb06  lea     rcx, [rbp+2F0h+var_2F0]
0x14005eb0a  call    ??0?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@QEAA@XZ; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>(void)
0x14005eb0f  mov     rdx, [rdi]
0x14005eb12  xor     ecx, ecx
0x14005eb14  test    rdx, rdx
0x14005eb17  jz      loc_14005EBCE
0x14005eb1d  mov     rax, [rdx]
0x14005eb20  mov     [rbp+2F0h+var_2D0], rax
0x14005eb24  mov     [rsp+3F0h+var_378], ecx; unsigned int
0x14005eb28  lea     rax, [rbp+2F0h+var_348]
0x14005eb2c  mov     [rsp+3F0h+var_380], r15d; int
  ... truncated ...
```
