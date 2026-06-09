# NtGdiLineTo

- ea: `0x14018b7b0`
- end: `0x14018bc5d`
- name: `NtGdiLineTo`
- size: `1197`
- prototype: `__int64 __fastcall(Gre::Base *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14005b820`
- `0x14005c5f0`
- `0x1400a4e80`
- `0x140154d18`
- `0x14018b7b0`
- `0x140319168`
- `0x140319190`
- `0x14031923c`
- `0x140336ed4`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b88a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b9f7`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b88a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14018b9f7`
- `win32kbase!UserReferenceDwmApiPort` at `0x14018bc06`
- `win32kbase!UserReferenceDwmApiPort` at `0x14018bc06`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14018b7f0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14018b7f0`
- `win32kbase!HmgPentryFromPobj` at `0x14018b8b2`
- `win32kbase!HmgPentryFromPobj` at `0x14018ba1f`
- `win32kbase!HmgPentryFromPobj` at `0x14018b8b2`
- `win32kbase!HmgPentryFromPobj` at `0x14018ba1f`
- `win32kbase!PopThreadGuardedObject` at `0x14018b9cb`
- `win32kbase!PopThreadGuardedObject` at `0x14018ba84`
- `win32kbase!PopThreadGuardedObject` at `0x14018b9cb`
- `win32kbase!PopThreadGuardedObject` at `0x14018ba84`
- `win32kbase!PushThreadGuardedObject` at `0x14018b82d`
- `win32kbase!PushThreadGuardedObject` at `0x14018b939`
- `win32kbase!PushThreadGuardedObject` at `0x14018b82d`
- `win32kbase!PushThreadGuardedObject` at `0x14018b939`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14018ba56`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14018ba56`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14018b8d0`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14018ba3d`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14018b8d0`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14018ba3d`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14018bb77`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14018bc45`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14018bb77`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14018bc45`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14018b8e9`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14018b8e9`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14018bb26`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14018bb26`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14018bb12`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14018bb12`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14018b84c`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14018b84c`
- `win32kbase!EngSetLastError` at `0x14018bac0`
- `win32kbase!EngSetLastError` at `0x14018bac0`
- `win32kbase!DwmSyncFlushAndWaitForBatch` at `0x14018bc15`
- `win32kbase!DwmSyncFlushAndWaitForBatch` at `0x14018bc15`

## pseudocode

```c
__int64 __fastcall NtGdiLineTo(Gre::Base *a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned int CurrentProcessId; // eax
  unsigned __int64 v10; // rdi
  unsigned int v11; // ebx
  char *v12; // rsi
  struct _DC_ATTR *UserAttr; // rax
  int v14; // ebx
  __int64 v15; // rcx
  unsigned int v16; // r14d
  unsigned __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned __int64 v19; // rbx
  unsigned int v20; // edi
  char *v21; // rsi
  struct _DC_ATTR *v22; // rax
  int v24; // eax
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // rax
  unsigned __int64 v29; // [rsp+20h] [rbp-A9h] BYREF
  int v30; // [rsp+28h] [rbp-A1h]
  struct Gre::Base::SESSION_GLOBALS *v31; // [rsp+30h] [rbp-99h]
  __int64 v32; // [rsp+38h] [rbp-91h]
  _OWORD v33[2]; // [rsp+40h] [rbp-89h] BYREF
  _OWORD v34[2]; // [rsp+60h] [rbp-69h] BYREF
  char v35; // [rsp+80h] [rbp-49h]
  _BYTE v36[24]; // [rsp+90h] [rbp-39h] BYREF
  unsigned __int64 *v37; // [rsp+A8h] [rbp-21h]

  v32 = 0;
  v31 = Gre::Base::Globals(a1);
  v29 = 0;
  v30 = 0;
  memset(v33, 0, sizeof(v33));
  PushThreadGuardedObject(
    v33,
    &v29,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v6) = 1;
  v7 = HmgLock(v31, a1, v6, 0);
  v29 = v7;
  v8 = v7;
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v7 + 12));
      v8 = 0;
      v29 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v8 = v29;
  }
  if ( v8 )
  {
    if ( (*(_DWORD *)(v8 + 44) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v10 = v29;
      v11 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v29 )
      {
        v12 = (char *)HmgPentryFromPobj(v31, v29);
      }
      else
      {
        v12 = (char *)(v29 + 2152);
        *(_OWORD *)(v29 + 2152) = 0;
        *(_QWORD *)(v10 + 2168) = 0;
        *(_DWORD *)(v10 + 2160) = -2147483630;
        *(_QWORD *)(v10 + 2168) = GreEncodeUserModePointer(0);
      }
      if ( v11 == (*((_DWORD *)v12 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v29);
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes((DC *)v29, UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)(v29 + 12));
            v29 = 0;
            goto LABEL_13;
          }
        }
      }
      *(_DWORD *)(v29 + 44) |= 2u;
      v8 = v29;
      v30 = 1;
    }
    if ( (*(_DWORD *)(v8 + 520) & 4) != 0 )
    {
      *(_DWORD *)(v8 + 520) &= ~4u;
      v24 = *(_DWORD *)(v8 + 520);
      v25 = *(_QWORD *)(v8 + 976);
      v26 = *(_DWORD *)(v25 + 340);
      if ( (v24 & 1) != 0 )
        v27 = v26 | 0x16090;
      else
        v27 = v26 | 0x6090;
      *(_DWORD *)(v25 + 340) = v27;
    }
  }
LABEL_13:
  memset(v34, 0, sizeof(v34));
  PushThreadGuardedObject(v34, &v29, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v35 = 1;
  if ( !v29 )
    goto LABEL_33;
  if ( *(_WORD *)(v29 + 12) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( *(_WORD *)(v29 + 12) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v29);
  if ( v29 )
  {
    v14 = 0;
    v37 = &v29;
    if ( *(_DWORD *)(v29 + 492)
      && (*(_DWORD *)(v29 + 36) & 0x4000) != 0
      && !(unsigned int)DWMSCREENREADMODIFYWRITEASSIST::bInPathBracket((DWMSCREENREADMODIFYWRITEASSIST *)v36) )
    {
      DWMSCREENREADMODIFYWRITEASSIST::vSaveAccumBoundsAndDisableSpriteUpdates((DWMSCREENREADMODIFYWRITEASSIST *)v36);
      if ( (unsigned int)GrepLineTo((struct XDCOBJ *)&v29, a2, a3) )
        v14 = DWMSCREENREADMODIFYWRITEASSIST::bReadFromAccumulatedBounds((DWMSCREENREADMODIFYWRITEASSIST *)v36);
      DWMSCREENREADMODIFYWRITEASSIST::vRestoreAccumBoundsAndEnableSpriteUpdates((DWMSCREENREADMODIFYWRITEASSIST *)v36);
    }
    v16 = GrepLineTo((struct XDCOBJ *)&v29, a2, a3);
    if ( v14 )
    {
      v28 = UserReferenceDwmApiPort(v15);
      DwmSyncFlushAndWaitForBatch(v28);
    }
    v29 &= -(__int64)(v35 != 0);
    PopThreadGuardedObject(v34);
    v17 = v29;
    if ( v29 )
    {
      if ( v30 && (*(_DWORD *)(v29 + 44) & 2) != 0 )
      {
        v18 = (unsigned int)PsGetCurrentProcessId();
        v19 = v29;
        v20 = v18 & 0xFFFFFFFC;
        if ( *(_QWORD *)v29 )
        {
          v21 = (char *)HmgPentryFromPobj(v31, v29);
        }
        else
        {
          v21 = (char *)(v29 + 2152);
          *(_OWORD *)(v29 + 2152) = 0;
          *(_QWORD *)(v19 + 2168) = 0;
          *(_DWORD *)(v19 + 2160) = -2147483630;
          *(_QWORD *)(v19 + 2168) = GreEncodeUserModePointer(0);
        }
        if ( v20 == (*((_DWORD *)v21 + 2) & 0xFFFFFFFE) )
        {
          v22 = DCOBJ::GetUserAttr((DCOBJ *)&v29);
          if ( v22 )
            DC::RestoreAttributes((DC *)v29, v22);
        }
        *(_DWORD *)(v29 + 44) &= ~2u;
        v17 = v29;
        v30 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)(v17 + 12));
      v29 = 0;
    }
    PopThreadGuardedObject(v33);
    return v16;
  }
  else
  {
LABEL_33:
    EngSetLastError(6u);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v29);
    return 0;
  }
}

```

## disassembly

```asm
0x14018b7b0  mov     [rsp-8+arg_18], rbx
0x14018b7b5  push    rbp
0x14018b7b6  push    rsi
0x14018b7b7  push    rdi
0x14018b7b8  push    r12
0x14018b7ba  push    r13
0x14018b7bc  push    r14
0x14018b7be  push    r15
0x14018b7c0  lea     rbp, [rsp-27h]
0x14018b7c5  sub     rsp, 0F0h
0x14018b7cc  mov     rax, cs:__security_cookie
0x14018b7d3  xor     rax, rsp
0x14018b7d6  mov     [rbp+57h+var_40], rax
0x14018b7da  xor     r12d, r12d
0x14018b7dd  mov     r15d, r8d
0x14018b7e0  mov     [rsp+120h+var_100], r12
0x14018b7e5  mov     r14d, edx
0x14018b7e8  mov     [rsp+120h+var_F8], r12d
0x14018b7ed  mov     rbx, rcx
0x14018b7f0  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14018b7f7  nop     dword ptr [rax+rax+00h]
0x14018b7fc  xorps   xmm0, xmm0
0x14018b7ff  mov     [rsp+120h+var_E8], r12
0x14018b804  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14018b80b  mov     [rsp+120h+var_F0], rax
0x14018b810  lea     rdx, [rsp+120h+var_100]
0x14018b815  mov     [rsp+120h+var_100], r12
0x14018b81a  lea     rcx, [rsp+120h+var_E0]
0x14018b81f  mov     [rsp+120h+var_F8], r12d
0x14018b824  movups  [rsp+120h+var_E0], xmm0
0x14018b829  movups  [rbp+57h+var_D0], xmm0
0x14018b82d  call    cs:__imp_PushThreadGuardedObject
0x14018b834  nop     dword ptr [rax+rax+00h]
0x14018b839  mov     rcx, [rsp+120h+var_F0]
0x14018b83e  lea     r13d, [r12+1]
0x14018b843  mov     r8b, r13b
0x14018b846  xor     r9d, r9d
0x14018b849  mov     rdx, rbx
0x14018b84c  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14018b853  nop     dword ptr [rax+rax+00h]
0x14018b858  mov     [rsp+120h+var_100], rax
0x14018b85d  mov     rcx, rax
0x14018b860  test    rax, rax
0x14018b863  jz      loc_14018BB12
0x14018b869  cmp     [rax+858h], r12d
0x14018b870  jnz     loc_14018BB46
0x14018b876  test    rcx, rcx
0x14018b879  jz      loc_14018B91E
0x14018b87f  mov     eax, [rcx+2Ch]
0x14018b882  test    al, 2
0x14018b884  jnz     loc_14018B910
0x14018b88a  call    cs:__imp_PsGetCurrentProcessId
0x14018b891  nop     dword ptr [rax+rax+00h]
0x14018b896  mov     rdi, [rsp+120h+var_100]
0x14018b89b  mov     rbx, rax
0x14018b89e  and     ebx, 0FFFFFFFCh
0x14018b8a1  cmp     [rdi], r12
0x14018b8a4  jz      loc_14018BB58
0x14018b8aa  mov     rcx, [rsp+120h+var_F0]
0x14018b8af  mov     rdx, rdi
0x14018b8b2  call    cs:__imp_HmgPentryFromPobj
0x14018b8b9  nop     dword ptr [rax+rax+00h]
0x14018b8be  mov     rsi, rax
0x14018b8c1  mov     eax, [rsi+8]
0x14018b8c4  and     eax, 0FFFFFFFEh
0x14018b8c7  cmp     ebx, eax
0x14018b8c9  jnz     short loc_14018B8FD
0x14018b8cb  lea     rcx, [rsp+120h+var_100]
0x14018b8d0  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14018b8d7  nop     dword ptr [rax+rax+00h]
0x14018b8dc  test    rax, rax
0x14018b8df  jz      short loc_14018B8FD
0x14018b8e1  mov     rcx, [rsp+120h+var_100]
0x14018b8e6  mov     rdx, rax
0x14018b8e9  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14018b8f0  nop     dword ptr [rax+rax+00h]
0x14018b8f5  test    eax, eax
0x14018b8f7  jz      loc_14018BB8F
0x14018b8fd  mov     rax, [rsp+120h+var_100]
0x14018b902  or      dword ptr [rax+2Ch], 2
0x14018b906  mov     rcx, [rsp+120h+var_100]
0x14018b90b  mov     [rsp+120h+var_F8], r13d
0x14018b910  mov     eax, [rcx+208h]
0x14018b916  test    al, 4
0x14018b918  jnz     loc_14018BADA
0x14018b91e  xorps   xmm0, xmm0
0x14018b921  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14018b928  lea     rdx, [rsp+120h+var_100]
0x14018b92d  lea     rcx, [rbp+57h+var_C0]
0x14018b931  movups  [rbp+57h+var_C0], xmm0
0x14018b935  movups  [rbp+57h+var_B0], xmm0
0x14018b939  call    cs:__imp_PushThreadGuardedObject
0x14018b940  nop     dword ptr [rax+rax+00h]
0x14018b945  mov     rax, [rsp+120h+var_100]
0x14018b94a  mov     [rbp+57h+var_A0], r13b
0x14018b94e  test    rax, rax
0x14018b951  jz      loc_14018BABB
0x14018b957  movzx   eax, word ptr [rax+0Ch]
0x14018b95b  cmp     ax, r13w
0x14018b95f  jnz     loc_14018BB3C
0x14018b965  mov     rax, [rsp+120h+var_100]
0x14018b96a  movzx   ecx, word ptr [rax+0Ch]
0x14018b96e  cmp     cx, r13w
0x14018b972  jnz     loc_14018BBA3
0x14018b978  mov     rax, [rsp+120h+var_100]
0x14018b97d  test    rax, rax
0x14018b980  jz      loc_14018BABB
0x14018b986  lea     rcx, [rsp+120h+var_100]
0x14018b98b  mov     ebx, r12d
0x14018b98e  mov     [rbp+57h+var_78], rcx
0x14018b992  cmp     [rax+1ECh], r12d
0x14018b999  jnz     loc_14018BBB2
0x14018b99f  mov     r8d, r15d; int
0x14018b9a2  lea     rcx, [rsp+120h+var_100]; struct XDCOBJ *
0x14018b9a7  mov     edx, r14d; int
0x14018b9aa  call    ?GrepLineTo@@YAHAEAVXDCOBJ@@HH@Z; GrepLineTo(XDCOBJ &,int,int)
0x14018b9af  mov     r14d, eax
0x14018b9b2  test    ebx, ebx
0x14018b9b4  jnz     loc_14018BC06
0x14018b9ba  mov     cl, [rbp+57h+var_A0]
0x14018b9bd  neg     cl
0x14018b9bf  lea     rcx, [rbp+57h+var_C0]
0x14018b9c3  sbb     rdx, rdx
0x14018b9c6  and     [rsp+120h+var_100], rdx
0x14018b9cb  call    cs:__imp_PopThreadGuardedObject
0x14018b9d2  nop     dword ptr [rax+rax+00h]
0x14018b9d7  mov     rcx, [rsp+120h+var_100]
0x14018b9dc  test    rcx, rcx
0x14018b9df  jz      loc_14018BA7F
0x14018b9e5  cmp     [rsp+120h+var_F8], r12d
0x14018b9ea  jz      loc_14018BA75
0x14018b9f0  mov     eax, [rcx+2Ch]
0x14018b9f3  test    al, 2
0x14018b9f5  jz      short loc_14018BA75
0x14018b9f7  call    cs:__imp_PsGetCurrentProcessId
0x14018b9fe  nop     dword ptr [rax+rax+00h]
0x14018ba03  mov     rbx, [rsp+120h+var_100]
0x14018ba08  mov     rdi, rax
0x14018ba0b  and     edi, 0FFFFFFFCh
0x14018ba0e  cmp     [rbx], r12
0x14018ba11  jz      loc_14018BC26
0x14018ba17  mov     rcx, [rsp+120h+var_F0]
0x14018ba1c  mov     rdx, rbx
0x14018ba1f  call    cs:__imp_HmgPentryFromPobj
0x14018ba26  nop     dword ptr [rax+rax+00h]
0x14018ba2b  mov     rsi, rax
0x14018ba2e  mov     eax, [rsi+8]
0x14018ba31  and     eax, 0FFFFFFFEh
0x14018ba34  cmp     edi, eax
0x14018ba36  jnz     short loc_14018BA62
0x14018ba38  lea     rcx, [rsp+120h+var_100]
0x14018ba3d  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14018ba44  nop     dword ptr [rax+rax+00h]
0x14018ba49  test    rax, rax
0x14018ba4c  jz      short loc_14018BA62
0x14018ba4e  mov     rcx, [rsp+120h+var_100]
0x14018ba53  mov     rdx, rax
0x14018ba56  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14018ba5d  nop     dword ptr [rax+rax+00h]
0x14018ba62  mov     rax, [rsp+120h+var_100]
0x14018ba67  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14018ba6b  mov     rcx, [rsp+120h+var_100]
0x14018ba70  mov     [rsp+120h+var_F8], r12d
0x14018ba75  lock dec word ptr [rcx+0Ch]
0x14018ba7a  mov     [rsp+120h+var_100], r12
0x14018ba7f  lea     rcx, [rsp+120h+var_E0]
0x14018ba84  call    cs:__imp_PopThreadGuardedObject
0x14018ba8b  nop     dword ptr [rax+rax+00h]
0x14018ba90  mov     eax, r14d
0x14018ba93  mov     rcx, [rbp+57h+var_40]
0x14018ba97  xor     rcx, rsp; StackCookie
0x14018ba9a  call    __security_check_cookie
0x14018ba9f  mov     rbx, [rsp+120h+arg_18]
0x14018baa7  add     rsp, 0F0h
0x14018baae  pop     r15
0x14018bab0  pop     r14
0x14018bab2  pop     r13
0x14018bab4  pop     r12
0x14018bab6  pop     rdi
0x14018bab7  pop     rsi
0x14018bab8  pop     rbp
0x14018bab9  retn
0x14018babb  mov     ecx, 6; iError
0x14018bac0  call    cs:__imp_EngSetLastError
0x14018bac7  nop     dword ptr [rax+rax+00h]
0x14018bacc  lea     rcx, [rsp+120h+var_100]; this
0x14018bad1  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14018bad6  xor     eax, eax
0x14018bad8  jmp     short loc_14018BA93
0x14018bada  and     dword ptr [rcx+208h], 0FFFFFFFBh
0x14018bae1  mov     eax, [rcx+208h]
0x14018bae7  mov     rdx, [rcx+3D0h]
0x14018baee  mov     ecx, [rdx+154h]
0x14018baf4  test    r13b, al
0x14018baf7  jz      short loc_14018BB0A
0x14018baf9  or      ecx, 16090h
0x14018baff  mov     [rdx+154h], ecx
0x14018bb05  jmp     loc_14018B91E
0x14018bb0a  or      ecx, 6090h
0x14018bb10  jmp     short loc_14018BAFF
0x14018bb12  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14018bb19  nop     dword ptr [rax+rax+00h]
0x14018bb1e  cmp     eax, r13d
0x14018bb21  jz      short loc_14018BB32
0x14018bb23  mov     ecx, r13d
0x14018bb26  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14018bb2d  nop     dword ptr [rax+rax+00h]
0x14018bb32  mov     rcx, [rsp+120h+var_100]
0x14018bb37  jmp     loc_14018B876
0x14018bb3c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14018bb41  jmp     loc_14018B965
0x14018bb46  lock dec word ptr [rax+0Ch]
0x14018bb4b  mov     rcx, r12
0x14018bb4e  mov     [rsp+120h+var_100], rcx
0x14018bb53  jmp     loc_14018B876
0x14018bb58  xorps   xmm0, xmm0
0x14018bb5b  lea     rsi, [rdi+868h]
0x14018bb62  movups  xmmword ptr [rsi], xmm0
0x14018bb65  xor     eax, eax
0x14018bb67  xor     ecx, ecx
0x14018bb69  mov     [rsi+10h], rax
0x14018bb6d  mov     dword ptr [rdi+870h], 80000012h
0x14018bb77  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14018bb7e  nop     dword ptr [rax+rax+00h]
0x14018bb83  mov     [rdi+878h], rax
0x14018bb8a  jmp     loc_14018B8C1
0x14018bb8f  mov     rax, [rsp+120h+var_100]
0x14018bb94  lock dec word ptr [rax+0Ch]
0x14018bb99  mov     [rsp+120h+var_100], r12
0x14018bb9e  jmp     loc_14018B91E
0x14018bba3  lea     rcx, [rsp+120h+var_100]; this
0x14018bba8  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x14018bbad  jmp     loc_14018B978
0x14018bbb2  test    dword ptr [rax+24h], 4000h
0x14018bbb9  jz      loc_14018B99F
0x14018bbbf  lea     rcx, [rbp+57h+var_90]; this
0x14018bbc3  call    ?bInPathBracket@DWMSCREENREADMODIFYWRITEASSIST@@QEBAHXZ; DWMSCREENREADMODIFYWRITEASSIST::bInPathBracket(void)
0x14018bbc8  test    eax, eax
0x14018bbca  jnz     loc_14018B99F
0x14018bbd0  lea     rcx, [rbp+57h+var_90]; this
0x14018bbd4  call    ?vSaveAccumBoundsAndDisableSpriteUpdates@DWMSCREENREADMODIFYWRITEASSIST@@QEAAXXZ; DWMSCREENREADMODIFYWRITEASSIST::vSaveAccumBoundsAndDisableSpriteUpdates(void)
0x14018bbd9  mov     r8d, r15d; int
0x14018bbdc  lea     rcx, [rsp+120h+var_100]; struct XDCOBJ *
0x14018bbe1  mov     edx, r14d; int
0x14018bbe4  call    ?GrepLineTo@@YAHAEAVXDCOBJ@@HH@Z; GrepLineTo(XDCOBJ &,int,int)
0x14018bbe9  test    eax, eax
0x14018bbeb  jz      short loc_14018BBF8
0x14018bbed  lea     rcx, [rbp+57h+var_90]; this
0x14018bbf1  call    ?bReadFromAccumulatedBounds@DWMSCREENREADMODIFYWRITEASSIST@@QEAAHXZ; DWMSCREENREADMODIFYWRITEASSIST::bReadFromAccumulatedBounds(void)
0x14018bbf6  mov     ebx, eax
0x14018bbf8  lea     rcx, [rbp+57h+var_90]; this
0x14018bbfc  call    ?vRestoreAccumBoundsAndEnableSpriteUpdates@DWMSCREENREADMODIFYWRITEASSIST@@QEAAXXZ; DWMSCREENREADMODIFYWRITEASSIST::vRestoreAccumBoundsAndEnableSpriteUpdates(void)
0x14018bc01  jmp     loc_14018B99F
0x14018bc06  call    cs:__imp_UserReferenceDwmApiPort
0x14018bc0d  nop     dword ptr [rax+rax+00h]
0x14018bc12  mov     rcx, rax
0x14018bc15  call    cs:__imp_DwmSyncFlushAndWaitForBatch
0x14018bc1c  nop     dword ptr [rax+rax+00h]
0x14018bc21  jmp     loc_14018B9BA
0x14018bc26  xorps   xmm0, xmm0
0x14018bc29  lea     rsi, [rbx+868h]
0x14018bc30  movups  xmmword ptr [rsi], xmm0
0x14018bc33  xor     eax, eax
0x14018bc35  xor     ecx, ecx
0x14018bc37  mov     [rsi+10h], rax
0x14018bc3b  mov     dword ptr [rbx+870h], 80000012h
0x14018bc45  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14018bc4c  nop     dword ptr [rax+rax+00h]
0x14018bc51  mov     [rbx+878h], rax
0x14018bc58  jmp     loc_14018BA2E
```
