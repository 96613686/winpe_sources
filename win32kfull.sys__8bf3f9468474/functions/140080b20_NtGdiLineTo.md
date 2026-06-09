# NtGdiLineTo

- ea: `0x140080b20`
- end: `0x140080fcd`
- name: `NtGdiLineTo`
- size: `1197`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400781e8`
- `0x14007eef8`
- `0x14007fc10`
- `0x140080b20`
- `0x140164228`
- `0x14031761c`
- `0x140317644`
- `0x1403176f0`
- `0x140335abc`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140080bfa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140080d67`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140080bfa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140080d67`
- `win32kbase!UserReferenceDwmApiPort` at `0x140080f76`
- `win32kbase!UserReferenceDwmApiPort` at `0x140080f76`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140080b60`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140080b60`
- `win32kbase!HmgPentryFromPobj` at `0x140080c22`
- `win32kbase!HmgPentryFromPobj` at `0x140080d8f`
- `win32kbase!HmgPentryFromPobj` at `0x140080c22`
- `win32kbase!HmgPentryFromPobj` at `0x140080d8f`
- `win32kbase!PopThreadGuardedObject` at `0x140080d3b`
- `win32kbase!PopThreadGuardedObject` at `0x140080df4`
- `win32kbase!PopThreadGuardedObject` at `0x140080d3b`
- `win32kbase!PopThreadGuardedObject` at `0x140080df4`
- `win32kbase!PushThreadGuardedObject` at `0x140080b9d`
- `win32kbase!PushThreadGuardedObject` at `0x140080ca9`
- `win32kbase!PushThreadGuardedObject` at `0x140080b9d`
- `win32kbase!PushThreadGuardedObject` at `0x140080ca9`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140080dc6`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140080dc6`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140080c40`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140080dad`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140080c40`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140080dad`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140080ee7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140080fb5`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140080ee7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140080fb5`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140080c59`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140080c59`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140080e96`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140080e96`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140080e82`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140080e82`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140080bbc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140080bbc`
- `win32kbase!EngSetLastError` at `0x140080e30`
- `win32kbase!EngSetLastError` at `0x140080e30`
- `win32kbase!DwmSyncFlushAndWaitForBatch` at `0x140080f85`
- `win32kbase!DwmSyncFlushAndWaitForBatch` at `0x140080f85`

## pseudocode

```c
__int64 __fastcall NtGdiLineTo(Gre::Base *a1, int a2, int a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned int CurrentProcessId; // eax
  unsigned __int64 v10; // rdi
  unsigned int v11; // ebx
  char *v12; // rsi
  struct _DC_ATTR *UserAttr; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // ebx
  __int64 v17; // rcx
  unsigned int v18; // r14d
  unsigned __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned __int64 v21; // rbx
  unsigned int v22; // edi
  char *v23; // rsi
  struct _DC_ATTR *v24; // rax
  int v26; // eax
  __int64 v27; // rdx
  int v28; // ecx
  int v29; // ecx
  __int64 v30; // rax
  unsigned __int64 v31; // [rsp+20h] [rbp-A9h] BYREF
  int v32; // [rsp+28h] [rbp-A1h]
  struct Gre::Base::SESSION_GLOBALS *v33; // [rsp+30h] [rbp-99h]
  __int64 v34; // [rsp+38h] [rbp-91h]
  _OWORD v35[2]; // [rsp+40h] [rbp-89h] BYREF
  _OWORD v36[2]; // [rsp+60h] [rbp-69h] BYREF
  char v37; // [rsp+80h] [rbp-49h]
  _BYTE v38[24]; // [rsp+90h] [rbp-39h] BYREF
  unsigned __int64 *v39; // [rsp+A8h] [rbp-21h]

  v34 = 0;
  v33 = Gre::Base::Globals(a1);
  v31 = 0;
  v32 = 0;
  memset(v35, 0, sizeof(v35));
  PushThreadGuardedObject(
    v35,
    &v31,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v6) = 1;
  v7 = HmgLock(v33, a1, v6, 0);
  v31 = v7;
  v8 = v7;
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v7 + 12));
      v8 = 0;
      v31 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v8 = v31;
  }
  if ( v8 )
  {
    if ( (*(_DWORD *)(v8 + 44) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v10 = v31;
      v11 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v31 )
      {
        v12 = (char *)HmgPentryFromPobj(v33, v31);
      }
      else
      {
        v12 = (char *)(v31 + 2152);
        *(_OWORD *)(v31 + 2152) = 0;
        *(_QWORD *)(v10 + 2168) = 0;
        *(_DWORD *)(v10 + 2160) = -2147483630;
        *(_QWORD *)(v10 + 2168) = GreEncodeUserModePointer(0);
      }
      if ( v11 == (*((_DWORD *)v12 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v31);
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes((DC *)v31, UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)(v31 + 12));
            v31 = 0;
            goto LABEL_13;
          }
        }
      }
      *(_DWORD *)(v31 + 44) |= 2u;
      v8 = v31;
      v32 = 1;
    }
    if ( (*(_DWORD *)(v8 + 520) & 4) != 0 )
    {
      *(_DWORD *)(v8 + 520) &= ~4u;
      v26 = *(_DWORD *)(v8 + 520);
      v27 = *(_QWORD *)(v8 + 976);
      v28 = *(_DWORD *)(v27 + 340);
      if ( (v26 & 1) != 0 )
        v29 = v28 | 0x16090;
      else
        v29 = v28 | 0x6090;
      *(_DWORD *)(v27 + 340) = v29;
    }
  }
LABEL_13:
  memset(v36, 0, sizeof(v36));
  PushThreadGuardedObject(v36, &v31, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v37 = 1;
  if ( !v31 )
    goto LABEL_33;
  if ( *(_WORD *)(v31 + 12) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14);
  if ( *(_WORD *)(v31 + 12) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v31);
  if ( v31 )
  {
    v16 = 0;
    v39 = &v31;
    if ( *(_DWORD *)(v31 + 492)
      && (*(_DWORD *)(v31 + 36) & 0x4000) != 0
      && !(unsigned int)DWMSCREENREADMODIFYWRITEASSIST::bInPathBracket((DWMSCREENREADMODIFYWRITEASSIST *)v38) )
    {
      DWMSCREENREADMODIFYWRITEASSIST::vSaveAccumBoundsAndDisableSpriteUpdates((DWMSCREENREADMODIFYWRITEASSIST *)v38);
      if ( (unsigned int)GrepLineTo((struct XDCOBJ *)&v31, a2, a3) )
        v16 = DWMSCREENREADMODIFYWRITEASSIST::bReadFromAccumulatedBounds((DWMSCREENREADMODIFYWRITEASSIST *)v38);
      DWMSCREENREADMODIFYWRITEASSIST::vRestoreAccumBoundsAndEnableSpriteUpdates((DWMSCREENREADMODIFYWRITEASSIST *)v38);
    }
    v18 = GrepLineTo((struct XDCOBJ *)&v31, a2, a3);
    if ( v16 )
    {
      v30 = UserReferenceDwmApiPort(v17);
      DwmSyncFlushAndWaitForBatch(v30);
    }
    v31 &= -(__int64)(v37 != 0);
    PopThreadGuardedObject(v36);
    v19 = v31;
    if ( v31 )
    {
      if ( v32 && (*(_DWORD *)(v31 + 44) & 2) != 0 )
      {
        v20 = (unsigned int)PsGetCurrentProcessId();
        v21 = v31;
        v22 = v20 & 0xFFFFFFFC;
        if ( *(_QWORD *)v31 )
        {
          v23 = (char *)HmgPentryFromPobj(v33, v31);
        }
        else
        {
          v23 = (char *)(v31 + 2152);
          *(_OWORD *)(v31 + 2152) = 0;
          *(_QWORD *)(v21 + 2168) = 0;
          *(_DWORD *)(v21 + 2160) = -2147483630;
          *(_QWORD *)(v21 + 2168) = GreEncodeUserModePointer(0);
        }
        if ( v22 == (*((_DWORD *)v23 + 2) & 0xFFFFFFFE) )
        {
          v24 = DCOBJ::GetUserAttr((DCOBJ *)&v31);
          if ( v24 )
            DC::RestoreAttributes((DC *)v31, v24);
        }
        *(_DWORD *)(v31 + 44) &= ~2u;
        v19 = v31;
        v32 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)(v19 + 12));
      v31 = 0;
    }
    PopThreadGuardedObject(v35);
    return v18;
  }
  else
  {
LABEL_33:
    EngSetLastError(6u);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v31);
    return 0;
  }
}

```

## disassembly

```asm
0x140080b20  mov     [rsp-8+arg_18], rbx
0x140080b25  push    rbp
0x140080b26  push    rsi
0x140080b27  push    rdi
0x140080b28  push    r12
0x140080b2a  push    r13
0x140080b2c  push    r14
0x140080b2e  push    r15
0x140080b30  lea     rbp, [rsp-27h]
0x140080b35  sub     rsp, 0F0h
0x140080b3c  mov     rax, cs:__security_cookie
0x140080b43  xor     rax, rsp
0x140080b46  mov     [rbp+57h+var_40], rax
0x140080b4a  xor     r12d, r12d
0x140080b4d  mov     r15d, r8d
0x140080b50  mov     [rsp+120h+var_100], r12
0x140080b55  mov     r14d, edx
0x140080b58  mov     [rsp+120h+var_F8], r12d
0x140080b5d  mov     rbx, rcx
0x140080b60  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140080b67  nop     dword ptr [rax+rax+00h]
0x140080b6c  xorps   xmm0, xmm0
0x140080b6f  mov     [rsp+120h+var_E8], r12
0x140080b74  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140080b7b  mov     [rsp+120h+var_F0], rax
0x140080b80  lea     rdx, [rsp+120h+var_100]
0x140080b85  mov     [rsp+120h+var_100], r12
0x140080b8a  lea     rcx, [rsp+120h+var_E0]
0x140080b8f  mov     [rsp+120h+var_F8], r12d
0x140080b94  movups  [rsp+120h+var_E0], xmm0
0x140080b99  movups  [rbp+57h+var_D0], xmm0
0x140080b9d  call    cs:__imp_PushThreadGuardedObject
0x140080ba4  nop     dword ptr [rax+rax+00h]
0x140080ba9  mov     rcx, [rsp+120h+var_F0]
0x140080bae  lea     r13d, [r12+1]
0x140080bb3  mov     r8b, r13b
0x140080bb6  xor     r9d, r9d
0x140080bb9  mov     rdx, rbx
0x140080bbc  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140080bc3  nop     dword ptr [rax+rax+00h]
0x140080bc8  mov     [rsp+120h+var_100], rax
0x140080bcd  mov     rcx, rax
0x140080bd0  test    rax, rax
0x140080bd3  jz      loc_140080E82
0x140080bd9  cmp     [rax+858h], r12d
0x140080be0  jnz     loc_140080EB6
0x140080be6  test    rcx, rcx
0x140080be9  jz      loc_140080C8E
0x140080bef  mov     eax, [rcx+2Ch]
0x140080bf2  test    al, 2
0x140080bf4  jnz     loc_140080C80
0x140080bfa  call    cs:__imp_PsGetCurrentProcessId
0x140080c01  nop     dword ptr [rax+rax+00h]
0x140080c06  mov     rdi, [rsp+120h+var_100]
0x140080c0b  mov     rbx, rax
0x140080c0e  and     ebx, 0FFFFFFFCh
0x140080c11  cmp     [rdi], r12
0x140080c14  jz      loc_140080EC8
0x140080c1a  mov     rcx, [rsp+120h+var_F0]
0x140080c1f  mov     rdx, rdi
0x140080c22  call    cs:__imp_HmgPentryFromPobj
0x140080c29  nop     dword ptr [rax+rax+00h]
0x140080c2e  mov     rsi, rax
0x140080c31  mov     eax, [rsi+8]
0x140080c34  and     eax, 0FFFFFFFEh
0x140080c37  cmp     ebx, eax
0x140080c39  jnz     short loc_140080C6D
0x140080c3b  lea     rcx, [rsp+120h+var_100]
0x140080c40  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140080c47  nop     dword ptr [rax+rax+00h]
0x140080c4c  test    rax, rax
0x140080c4f  jz      short loc_140080C6D
0x140080c51  mov     rcx, [rsp+120h+var_100]
0x140080c56  mov     rdx, rax
0x140080c59  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140080c60  nop     dword ptr [rax+rax+00h]
0x140080c65  test    eax, eax
0x140080c67  jz      loc_140080EFF
0x140080c6d  mov     rax, [rsp+120h+var_100]
0x140080c72  or      dword ptr [rax+2Ch], 2
0x140080c76  mov     rcx, [rsp+120h+var_100]
0x140080c7b  mov     [rsp+120h+var_F8], r13d
0x140080c80  mov     eax, [rcx+208h]
0x140080c86  test    al, 4
0x140080c88  jnz     loc_140080E4A
0x140080c8e  xorps   xmm0, xmm0
0x140080c91  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140080c98  lea     rdx, [rsp+120h+var_100]
0x140080c9d  lea     rcx, [rbp+57h+var_C0]
0x140080ca1  movups  [rbp+57h+var_C0], xmm0
0x140080ca5  movups  [rbp+57h+var_B0], xmm0
0x140080ca9  call    cs:__imp_PushThreadGuardedObject
0x140080cb0  nop     dword ptr [rax+rax+00h]
0x140080cb5  mov     rax, [rsp+120h+var_100]
0x140080cba  mov     [rbp+57h+var_A0], r13b
0x140080cbe  test    rax, rax
0x140080cc1  jz      loc_140080E2B
0x140080cc7  movzx   eax, word ptr [rax+0Ch]
0x140080ccb  cmp     ax, r13w
0x140080ccf  jnz     loc_140080EAC
0x140080cd5  mov     rax, [rsp+120h+var_100]
0x140080cda  movzx   ecx, word ptr [rax+0Ch]
0x140080cde  cmp     cx, r13w
0x140080ce2  jnz     loc_140080F13
0x140080ce8  mov     rax, [rsp+120h+var_100]
0x140080ced  test    rax, rax
0x140080cf0  jz      loc_140080E2B
0x140080cf6  lea     rcx, [rsp+120h+var_100]
0x140080cfb  mov     ebx, r12d
0x140080cfe  mov     [rbp+57h+var_78], rcx
0x140080d02  cmp     [rax+1ECh], r12d
0x140080d09  jnz     loc_140080F22
0x140080d0f  mov     r8d, r15d; int
0x140080d12  lea     rcx, [rsp+120h+var_100]; struct XDCOBJ *
0x140080d17  mov     edx, r14d; int
0x140080d1a  call    ?GrepLineTo@@YAHAEAVXDCOBJ@@HH@Z; GrepLineTo(XDCOBJ &,int,int)
0x140080d1f  mov     r14d, eax
0x140080d22  test    ebx, ebx
0x140080d24  jnz     loc_140080F76
0x140080d2a  mov     cl, [rbp+57h+var_A0]
0x140080d2d  neg     cl
0x140080d2f  lea     rcx, [rbp+57h+var_C0]
0x140080d33  sbb     rdx, rdx
0x140080d36  and     [rsp+120h+var_100], rdx
0x140080d3b  call    cs:__imp_PopThreadGuardedObject
0x140080d42  nop     dword ptr [rax+rax+00h]
0x140080d47  mov     rcx, [rsp+120h+var_100]
0x140080d4c  test    rcx, rcx
0x140080d4f  jz      loc_140080DEF
0x140080d55  cmp     [rsp+120h+var_F8], r12d
0x140080d5a  jz      loc_140080DE5
0x140080d60  mov     eax, [rcx+2Ch]
0x140080d63  test    al, 2
0x140080d65  jz      short loc_140080DE5
0x140080d67  call    cs:__imp_PsGetCurrentProcessId
0x140080d6e  nop     dword ptr [rax+rax+00h]
0x140080d73  mov     rbx, [rsp+120h+var_100]
0x140080d78  mov     rdi, rax
0x140080d7b  and     edi, 0FFFFFFFCh
0x140080d7e  cmp     [rbx], r12
0x140080d81  jz      loc_140080F96
0x140080d87  mov     rcx, [rsp+120h+var_F0]
0x140080d8c  mov     rdx, rbx
0x140080d8f  call    cs:__imp_HmgPentryFromPobj
0x140080d96  nop     dword ptr [rax+rax+00h]
0x140080d9b  mov     rsi, rax
0x140080d9e  mov     eax, [rsi+8]
0x140080da1  and     eax, 0FFFFFFFEh
0x140080da4  cmp     edi, eax
0x140080da6  jnz     short loc_140080DD2
0x140080da8  lea     rcx, [rsp+120h+var_100]
0x140080dad  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140080db4  nop     dword ptr [rax+rax+00h]
0x140080db9  test    rax, rax
0x140080dbc  jz      short loc_140080DD2
0x140080dbe  mov     rcx, [rsp+120h+var_100]
0x140080dc3  mov     rdx, rax
0x140080dc6  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x140080dcd  nop     dword ptr [rax+rax+00h]
0x140080dd2  mov     rax, [rsp+120h+var_100]
0x140080dd7  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x140080ddb  mov     rcx, [rsp+120h+var_100]
0x140080de0  mov     [rsp+120h+var_F8], r12d
0x140080de5  lock dec word ptr [rcx+0Ch]
0x140080dea  mov     [rsp+120h+var_100], r12
0x140080def  lea     rcx, [rsp+120h+var_E0]
0x140080df4  call    cs:__imp_PopThreadGuardedObject
0x140080dfb  nop     dword ptr [rax+rax+00h]
0x140080e00  mov     eax, r14d
0x140080e03  mov     rcx, [rbp+57h+var_40]
0x140080e07  xor     rcx, rsp; StackCookie
0x140080e0a  call    __security_check_cookie
0x140080e0f  mov     rbx, [rsp+120h+arg_18]
0x140080e17  add     rsp, 0F0h
0x140080e1e  pop     r15
0x140080e20  pop     r14
0x140080e22  pop     r13
0x140080e24  pop     r12
0x140080e26  pop     rdi
0x140080e27  pop     rsi
0x140080e28  pop     rbp
0x140080e29  retn
0x140080e2b  mov     ecx, 6; iError
0x140080e30  call    cs:__imp_EngSetLastError
0x140080e37  nop     dword ptr [rax+rax+00h]
0x140080e3c  lea     rcx, [rsp+120h+var_100]; this
0x140080e41  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140080e46  xor     eax, eax
0x140080e48  jmp     short loc_140080E03
0x140080e4a  and     dword ptr [rcx+208h], 0FFFFFFFBh
0x140080e51  mov     eax, [rcx+208h]
0x140080e57  mov     rdx, [rcx+3D0h]
0x140080e5e  mov     ecx, [rdx+154h]
0x140080e64  test    r13b, al
0x140080e67  jz      short loc_140080E7A
0x140080e69  or      ecx, 16090h
0x140080e6f  mov     [rdx+154h], ecx
0x140080e75  jmp     loc_140080C8E
0x140080e7a  or      ecx, 6090h
0x140080e80  jmp     short loc_140080E6F
0x140080e82  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140080e89  nop     dword ptr [rax+rax+00h]
0x140080e8e  cmp     eax, r13d
0x140080e91  jz      short loc_140080EA2
0x140080e93  mov     ecx, r13d
0x140080e96  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x140080e9d  nop     dword ptr [rax+rax+00h]
0x140080ea2  mov     rcx, [rsp+120h+var_100]
0x140080ea7  jmp     loc_140080BE6
0x140080eac  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140080eb1  jmp     loc_140080CD5
0x140080eb6  lock dec word ptr [rax+0Ch]
0x140080ebb  mov     rcx, r12
0x140080ebe  mov     [rsp+120h+var_100], rcx
0x140080ec3  jmp     loc_140080BE6
0x140080ec8  xorps   xmm0, xmm0
0x140080ecb  lea     rsi, [rdi+868h]
0x140080ed2  movups  xmmword ptr [rsi], xmm0
0x140080ed5  xor     eax, eax
0x140080ed7  xor     ecx, ecx
0x140080ed9  mov     [rsi+10h], rax
0x140080edd  mov     dword ptr [rdi+870h], 80000012h
0x140080ee7  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140080eee  nop     dword ptr [rax+rax+00h]
0x140080ef3  mov     [rdi+878h], rax
0x140080efa  jmp     loc_140080C31
0x140080eff  mov     rax, [rsp+120h+var_100]
0x140080f04  lock dec word ptr [rax+0Ch]
0x140080f09  mov     [rsp+120h+var_100], r12
0x140080f0e  jmp     loc_140080C8E
0x140080f13  lea     rcx, [rsp+120h+var_100]; this
0x140080f18  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x140080f1d  jmp     loc_140080CE8
0x140080f22  test    dword ptr [rax+24h], 4000h
0x140080f29  jz      loc_140080D0F
0x140080f2f  lea     rcx, [rbp+57h+var_90]; this
0x140080f33  call    ?bInPathBracket@DWMSCREENREADMODIFYWRITEASSIST@@QEBAHXZ; DWMSCREENREADMODIFYWRITEASSIST::bInPathBracket(void)
0x140080f38  test    eax, eax
0x140080f3a  jnz     loc_140080D0F
0x140080f40  lea     rcx, [rbp+57h+var_90]; this
0x140080f44  call    ?vSaveAccumBoundsAndDisableSpriteUpdates@DWMSCREENREADMODIFYWRITEASSIST@@QEAAXXZ; DWMSCREENREADMODIFYWRITEASSIST::vSaveAccumBoundsAndDisableSpriteUpdates(void)
0x140080f49  mov     r8d, r15d; int
0x140080f4c  lea     rcx, [rsp+120h+var_100]; struct XDCOBJ *
0x140080f51  mov     edx, r14d; int
0x140080f54  call    ?GrepLineTo@@YAHAEAVXDCOBJ@@HH@Z; GrepLineTo(XDCOBJ &,int,int)
0x140080f59  test    eax, eax
0x140080f5b  jz      short loc_140080F68
0x140080f5d  lea     rcx, [rbp+57h+var_90]; this
0x140080f61  call    ?bReadFromAccumulatedBounds@DWMSCREENREADMODIFYWRITEASSIST@@QEAAHXZ; DWMSCREENREADMODIFYWRITEASSIST::bReadFromAccumulatedBounds(void)
0x140080f66  mov     ebx, eax
0x140080f68  lea     rcx, [rbp+57h+var_90]; this
0x140080f6c  call    ?vRestoreAccumBoundsAndEnableSpriteUpdates@DWMSCREENREADMODIFYWRITEASSIST@@QEAAXXZ; DWMSCREENREADMODIFYWRITEASSIST::vRestoreAccumBoundsAndEnableSpriteUpdates(void)
0x140080f71  jmp     loc_140080D0F
0x140080f76  call    cs:__imp_UserReferenceDwmApiPort
0x140080f7d  nop     dword ptr [rax+rax+00h]
0x140080f82  mov     rcx, rax
0x140080f85  call    cs:__imp_DwmSyncFlushAndWaitForBatch
0x140080f8c  nop     dword ptr [rax+rax+00h]
0x140080f91  jmp     loc_140080D2A
0x140080f96  xorps   xmm0, xmm0
0x140080f99  lea     rsi, [rbx+868h]
0x140080fa0  movups  xmmword ptr [rsi], xmm0
0x140080fa3  xor     eax, eax
0x140080fa5  xor     ecx, ecx
0x140080fa7  mov     [rsi+10h], rax
0x140080fab  mov     dword ptr [rbx+870h], 80000012h
0x140080fb5  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140080fbc  nop     dword ptr [rax+rax+00h]
0x140080fc1  mov     [rbx+878h], rax
0x140080fc8  jmp     loc_140080D9E
```
