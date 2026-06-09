# NtGdiSelectBitmap

- ea: `0x14016ce50`
- end: `0x14016d2f1`
- name: `NtGdiSelectBitmap`
- size: `1185`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400781e8`
- `0x140164228`
- `0x14016ce50`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14016cf05`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14016d047`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14016d0d9`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14016cf05`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14016d047`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14016d0d9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016ce78`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14016ce78`
- `win32kbase!HmgPentryFromPobj` at `0x14016cf2b`
- `win32kbase!HmgPentryFromPobj` at `0x14016d06d`
- `win32kbase!HmgPentryFromPobj` at `0x14016d0ff`
- `win32kbase!HmgPentryFromPobj` at `0x14016cf2b`
- `win32kbase!HmgPentryFromPobj` at `0x14016d06d`
- `win32kbase!HmgPentryFromPobj` at `0x14016d0ff`
- `win32kbase!PopThreadGuardedObject` at `0x14016d021`
- `win32kbase!PopThreadGuardedObject` at `0x14016d160`
- `win32kbase!PopThreadGuardedObject` at `0x14016d197`
- `win32kbase!PopThreadGuardedObject` at `0x14016d021`
- `win32kbase!PopThreadGuardedObject` at `0x14016d160`
- `win32kbase!PopThreadGuardedObject` at `0x14016d197`
- `win32kbase!PushThreadGuardedObject` at `0x14016ceae`
- `win32kbase!PushThreadGuardedObject` at `0x14016cfac`
- `win32kbase!PushThreadGuardedObject` at `0x14016ceae`
- `win32kbase!PushThreadGuardedObject` at `0x14016cfac`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14016d0a2`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14016d134`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14016d0a2`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14016d134`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016cf49`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016d08a`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016d11c`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016cf49`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016d08a`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14016d11c`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d24b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d2a2`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d2d9`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d24b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d2a2`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14016d2d9`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14016cf61`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14016cf61`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14016d1fb`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14016d1fb`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14016d1e9`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14016d1e9`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14016cecc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14016cecc`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14016d002`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x14016d002`

## pseudocode

```c
__int64 __fastcall NtGdiSelectBitmap(Gre::Base *a1, __int64 a2)
{
  char v4; // di
  __int64 v5; // r8
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  unsigned int CurrentProcessId; // eax
  unsigned __int64 v9; // rsi
  unsigned int v10; // ebx
  char *v11; // r14
  struct _DC_ATTR *UserAttr; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned __int64 v17; // rbx
  unsigned int v18; // edi
  char *v19; // rsi
  struct _DC_ATTR *v20; // rax
  unsigned int v21; // eax
  unsigned __int64 v22; // rbx
  unsigned int v23; // edi
  char *v24; // rsi
  struct _DC_ATTR *v25; // rax
  unsigned __int64 v26; // rcx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // ecx
  int v31; // ecx
  _BYTE v32[16]; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int64 v33; // [rsp+30h] [rbp-49h] BYREF
  int v34; // [rsp+38h] [rbp-41h]
  struct Gre::Base::SESSION_GLOBALS *v35; // [rsp+40h] [rbp-39h]
  __int64 v36; // [rsp+48h] [rbp-31h]
  _OWORD v37[2]; // [rsp+50h] [rbp-29h] BYREF
  _OWORD v38[2]; // [rsp+70h] [rbp-9h] BYREF
  char v39; // [rsp+90h] [rbp+17h]

  v36 = 0;
  v35 = Gre::Base::Globals(a1);
  v33 = 0;
  v34 = 0;
  memset(v37, 0, sizeof(v37));
  PushThreadGuardedObject(
    v37,
    &v33,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  v4 = 1;
  LOBYTE(v5) = 1;
  v6 = HmgLock(v35, a1, v5);
  v33 = v6;
  v7 = v6;
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v6 + 12));
      v7 = 0;
      v33 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v7 = v33;
  }
  if ( v7 )
  {
    if ( (*(_DWORD *)(v7 + 44) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v9 = v33;
      v10 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v33 )
      {
        v11 = (char *)HmgPentryFromPobj(v35, v33);
      }
      else
      {
        v11 = (char *)(v33 + 2152);
        *(_OWORD *)(v33 + 2152) = 0;
        *(_QWORD *)(v9 + 2168) = 0;
        *(_DWORD *)(v9 + 2160) = -2147483630;
        *(_QWORD *)(v9 + 2168) = GreEncodeUserModePointer(0);
      }
      if ( v10 == (*((_DWORD *)v11 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v33);
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes((DC *)v33, UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)(v33 + 12));
            v33 = 0;
            goto LABEL_13;
          }
        }
      }
      *(_DWORD *)(v33 + 44) |= 2u;
      v7 = v33;
      v34 = 1;
    }
    if ( (*(_DWORD *)(v7 + 520) & 4) != 0 )
    {
      *(_DWORD *)(v7 + 520) &= ~4u;
      v28 = *(_DWORD *)(v7 + 520);
      v29 = *(_QWORD *)(v7 + 976);
      v30 = *(_DWORD *)(v29 + 340);
      if ( (v28 & 1) != 0 )
        v31 = v30 | 0x16090;
      else
        v31 = v30 | 0x6090;
      *(_DWORD *)(v29 + 340) = v31;
    }
  }
LABEL_13:
  memset(v38, 0, sizeof(v38));
  PushThreadGuardedObject(v38, &v33, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v13 = v33;
  v39 = 1;
  if ( v33 )
  {
    if ( *(_WORD *)(v33 + 12) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( *(_WORD *)(v33 + 12) != 1 )
      DCOBJ::vUnlock((DCOBJ *)&v33);
    v13 = v33;
    if ( v33 )
    {
      v14 = *(_QWORD *)GrepSelectBitmap(v32, &v33, a2, 0);
      v33 &= -(__int64)(v39 != 0);
      PopThreadGuardedObject(v38);
      v15 = v33;
      if ( v33 )
      {
        if ( v34 && (*(_DWORD *)(v33 + 44) & 2) != 0 )
        {
          v16 = (unsigned int)PsGetCurrentProcessId();
          v17 = v33;
          v18 = v16 & 0xFFFFFFFC;
          if ( *(_QWORD *)v33 )
          {
            v19 = (char *)HmgPentryFromPobj(v35, v33);
          }
          else
          {
            v19 = (char *)(v33 + 2152);
            *(_OWORD *)(v33 + 2152) = 0;
            *(_QWORD *)(v17 + 2168) = 0;
            *(_DWORD *)(v17 + 2160) = -2147483630;
            *(_QWORD *)(v17 + 2168) = GreEncodeUserModePointer(0);
          }
          if ( v18 == (*((_DWORD *)v19 + 2) & 0xFFFFFFFE) )
          {
            v20 = DCOBJ::GetUserAttr((DCOBJ *)&v33);
            if ( v20 )
              DC::RestoreAttributes((DC *)v33, v20);
          }
          *(_DWORD *)(v33 + 44) &= ~2u;
          v15 = v33;
          v34 = 0;
        }
        _InterlockedDecrement16((volatile signed __int16 *)(v15 + 12));
        v33 = 0;
      }
      goto LABEL_39;
    }
    v4 = v39;
  }
  v33 = v13 & -(__int64)(v4 != 0);
  PopThreadGuardedObject(v38);
  v26 = v33;
  if ( v33 )
  {
    if ( v34 && (*(_DWORD *)(v33 + 44) & 2) != 0 )
    {
      v21 = (unsigned int)PsGetCurrentProcessId();
      v22 = v33;
      v23 = v21 & 0xFFFFFFFC;
      if ( *(_QWORD *)v33 )
      {
        v24 = (char *)HmgPentryFromPobj(v35, v33);
      }
      else
      {
        v24 = (char *)(v33 + 2152);
        *(_OWORD *)(v33 + 2152) = 0;
        *(_QWORD *)(v22 + 2168) = 0;
        *(_DWORD *)(v22 + 2160) = -2147483630;
        *(_QWORD *)(v22 + 2168) = GreEncodeUserModePointer(0);
      }
      if ( v23 == (*((_DWORD *)v24 + 2) & 0xFFFFFFFE) )
      {
        v25 = DCOBJ::GetUserAttr((DCOBJ *)&v33);
        if ( v25 )
          DC::RestoreAttributes((DC *)v33, v25);
      }
      *(_DWORD *)(v33 + 44) &= ~2u;
      v26 = v33;
      v34 = 0;
    }
    _InterlockedDecrement16((volatile signed __int16 *)(v26 + 12));
    v33 = 0;
  }
  v14 = 0;
LABEL_39:
  PopThreadGuardedObject(v37);
  return v14;
}

```

## disassembly

```asm
0x14016ce50  push    rbp
0x14016ce52  push    rbx
0x14016ce53  push    rsi
0x14016ce54  push    rdi
0x14016ce55  push    r12
0x14016ce57  push    r14
0x14016ce59  push    r15
0x14016ce5b  lea     rbp, [rsp-27h]
0x14016ce60  sub     rsp, 0A0h
0x14016ce67  xor     r12d, r12d
0x14016ce6a  mov     r15, rdx
0x14016ce6d  mov     [rbp+57h+var_A0], r12
0x14016ce71  mov     rbx, rcx
0x14016ce74  mov     [rbp+57h+var_98], r12d
0x14016ce78  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14016ce7f  nop     dword ptr [rax+rax+00h]
0x14016ce84  xorps   xmm0, xmm0
0x14016ce87  mov     [rbp+57h+var_88], r12
0x14016ce8b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14016ce92  mov     [rbp+57h+var_90], rax
0x14016ce96  lea     rdx, [rbp+57h+var_A0]
0x14016ce9a  mov     [rbp+57h+var_A0], r12
0x14016ce9e  lea     rcx, [rbp+57h+var_80]
0x14016cea2  mov     [rbp+57h+var_98], r12d
0x14016cea6  movups  [rbp+57h+var_80], xmm0
0x14016ceaa  movups  [rbp+57h+var_70], xmm0
0x14016ceae  call    cs:__imp_PushThreadGuardedObject
0x14016ceb5  nop     dword ptr [rax+rax+00h]
0x14016ceba  mov     rcx, [rbp+57h+var_90]
0x14016cebe  lea     edi, [r12+1]
0x14016cec3  mov     r8b, dil
0x14016cec6  xor     r9d, r9d
0x14016cec9  mov     rdx, rbx
0x14016cecc  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14016ced3  nop     dword ptr [rax+rax+00h]
0x14016ced8  mov     [rbp+57h+var_A0], rax
0x14016cedc  mov     rcx, rax
0x14016cedf  test    rax, rax
0x14016cee2  jz      loc_14016D1E9
0x14016cee8  cmp     [rax+858h], r12d
0x14016ceef  jnz     loc_14016D21A
0x14016cef5  test    rcx, rcx
0x14016cef8  jz      loc_14016CF92
0x14016cefe  mov     eax, [rcx+2Ch]
0x14016cf01  test    al, 2
0x14016cf03  jnz     short loc_14016CF84
0x14016cf05  call    cs:__imp_PsGetCurrentProcessId
0x14016cf0c  nop     dword ptr [rax+rax+00h]
0x14016cf11  mov     rsi, [rbp+57h+var_A0]
0x14016cf15  mov     rbx, rax
0x14016cf18  and     ebx, 0FFFFFFFCh
0x14016cf1b  cmp     [rsi], r12
0x14016cf1e  jz      loc_14016D22B
0x14016cf24  mov     rcx, [rbp+57h+var_90]
0x14016cf28  mov     rdx, rsi
0x14016cf2b  call    cs:__imp_HmgPentryFromPobj
0x14016cf32  nop     dword ptr [rax+rax+00h]
0x14016cf37  mov     r14, rax
0x14016cf3a  mov     eax, [r14+8]
0x14016cf3e  and     eax, 0FFFFFFFEh
0x14016cf41  cmp     ebx, eax
0x14016cf43  jnz     short loc_14016CF75
0x14016cf45  lea     rcx, [rbp+57h+var_A0]
0x14016cf49  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14016cf50  nop     dword ptr [rax+rax+00h]
0x14016cf55  test    rax, rax
0x14016cf58  jz      short loc_14016CF75
0x14016cf5a  mov     rcx, [rbp+57h+var_A0]
0x14016cf5e  mov     rdx, rax
0x14016cf61  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14016cf68  nop     dword ptr [rax+rax+00h]
0x14016cf6d  test    eax, eax
0x14016cf6f  jz      loc_14016D263
0x14016cf75  mov     rax, [rbp+57h+var_A0]
0x14016cf79  or      dword ptr [rax+2Ch], 2
0x14016cf7d  mov     rcx, [rbp+57h+var_A0]
0x14016cf81  mov     [rbp+57h+var_98], edi
0x14016cf84  mov     eax, [rcx+208h]
0x14016cf8a  test    al, 4
0x14016cf8c  jnz     loc_14016D1B1
0x14016cf92  xorps   xmm0, xmm0
0x14016cf95  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14016cf9c  lea     rdx, [rbp+57h+var_A0]
0x14016cfa0  lea     rcx, [rbp+57h+var_60]
0x14016cfa4  movups  [rbp+57h+var_60], xmm0
0x14016cfa8  movups  [rbp+57h+var_50], xmm0
0x14016cfac  call    cs:__imp_PushThreadGuardedObject
0x14016cfb3  nop     dword ptr [rax+rax+00h]
0x14016cfb8  mov     rcx, [rbp+57h+var_A0]
0x14016cfbc  mov     [rbp+57h+var_40], dil
0x14016cfc0  test    rcx, rcx
0x14016cfc3  jz      loc_14016D186
0x14016cfc9  movzx   eax, word ptr [rcx+0Ch]
0x14016cfcd  cmp     ax, di
0x14016cfd0  jnz     loc_14016D210
0x14016cfd6  mov     rax, [rbp+57h+var_A0]
0x14016cfda  movzx   ecx, word ptr [rax+0Ch]
0x14016cfde  cmp     cx, di
0x14016cfe1  jnz     loc_14016D275
0x14016cfe7  mov     rcx, [rbp+57h+var_A0]
0x14016cfeb  test    rcx, rcx
0x14016cfee  jz      loc_14016D182
0x14016cff4  xor     r9d, r9d
0x14016cff7  lea     rdx, [rbp+57h+var_A0]
0x14016cffb  mov     r8, r15
0x14016cffe  lea     rcx, [rbp+57h+var_B0]
0x14016d002  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x14016d009  nop     dword ptr [rax+rax+00h]
0x14016d00e  mov     r14, [rax]
0x14016d011  mov     al, [rbp+57h+var_40]
0x14016d014  neg     al
0x14016d016  sbb     rcx, rcx
0x14016d019  and     [rbp+57h+var_A0], rcx
0x14016d01d  lea     rcx, [rbp+57h+var_60]
0x14016d021  call    cs:__imp_PopThreadGuardedObject
0x14016d028  nop     dword ptr [rax+rax+00h]
0x14016d02d  mov     rcx, [rbp+57h+var_A0]
0x14016d031  test    rcx, rcx
0x14016d034  jz      loc_14016D15C
0x14016d03a  cmp     [rbp+57h+var_98], r12d
0x14016d03e  jz      short loc_14016D0BE
0x14016d040  mov     eax, [rcx+2Ch]
0x14016d043  test    al, 2
0x14016d045  jz      short loc_14016D0BE
0x14016d047  call    cs:__imp_PsGetCurrentProcessId
0x14016d04e  nop     dword ptr [rax+rax+00h]
0x14016d053  mov     rbx, [rbp+57h+var_A0]
0x14016d057  mov     rdi, rax
0x14016d05a  and     edi, 0FFFFFFFCh
0x14016d05d  cmp     [rbx], r12
0x14016d060  jz      loc_14016D283
0x14016d066  mov     rcx, [rbp+57h+var_90]
0x14016d06a  mov     rdx, rbx
0x14016d06d  call    cs:__imp_HmgPentryFromPobj
0x14016d074  nop     dword ptr [rax+rax+00h]
0x14016d079  mov     rsi, rax
0x14016d07c  mov     eax, [rsi+8]
0x14016d07f  and     eax, 0FFFFFFFEh
0x14016d082  cmp     edi, eax
0x14016d084  jnz     short loc_14016D0AE
0x14016d086  lea     rcx, [rbp+57h+var_A0]
0x14016d08a  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14016d091  nop     dword ptr [rax+rax+00h]
0x14016d096  test    rax, rax
0x14016d099  jz      short loc_14016D0AE
0x14016d09b  mov     rcx, [rbp+57h+var_A0]
0x14016d09f  mov     rdx, rax
0x14016d0a2  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14016d0a9  nop     dword ptr [rax+rax+00h]
0x14016d0ae  mov     rax, [rbp+57h+var_A0]
0x14016d0b2  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14016d0b6  mov     rcx, [rbp+57h+var_A0]
0x14016d0ba  mov     [rbp+57h+var_98], r12d
0x14016d0be  lock dec word ptr [rcx+0Ch]
0x14016d0c3  mov     [rbp+57h+var_A0], r12
0x14016d0c7  jmp     loc_14016D15C
0x14016d0cc  cmp     [rbp+57h+var_98], r12d
0x14016d0d0  jz      short loc_14016D150
0x14016d0d2  mov     eax, [rcx+2Ch]
0x14016d0d5  test    al, 2
0x14016d0d7  jz      short loc_14016D150
0x14016d0d9  call    cs:__imp_PsGetCurrentProcessId
0x14016d0e0  nop     dword ptr [rax+rax+00h]
0x14016d0e5  mov     rbx, [rbp+57h+var_A0]
0x14016d0e9  mov     rdi, rax
0x14016d0ec  and     edi, 0FFFFFFFCh
0x14016d0ef  cmp     [rbx], r12
0x14016d0f2  jz      loc_14016D2BA
0x14016d0f8  mov     rcx, [rbp+57h+var_90]
0x14016d0fc  mov     rdx, rbx
0x14016d0ff  call    cs:__imp_HmgPentryFromPobj
0x14016d106  nop     dword ptr [rax+rax+00h]
0x14016d10b  mov     rsi, rax
0x14016d10e  mov     eax, [rsi+8]
0x14016d111  and     eax, 0FFFFFFFEh
0x14016d114  cmp     edi, eax
0x14016d116  jnz     short loc_14016D140
0x14016d118  lea     rcx, [rbp+57h+var_A0]
0x14016d11c  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14016d123  nop     dword ptr [rax+rax+00h]
0x14016d128  test    rax, rax
0x14016d12b  jz      short loc_14016D140
0x14016d12d  mov     rcx, [rbp+57h+var_A0]
0x14016d131  mov     rdx, rax
0x14016d134  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14016d13b  nop     dword ptr [rax+rax+00h]
0x14016d140  mov     rax, [rbp+57h+var_A0]
0x14016d144  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14016d148  mov     rcx, [rbp+57h+var_A0]
0x14016d14c  mov     [rbp+57h+var_98], r12d
0x14016d150  lock dec word ptr [rcx+0Ch]
0x14016d155  mov     [rbp+57h+var_A0], r12
0x14016d159  mov     r14, r12
0x14016d15c  lea     rcx, [rbp+57h+var_80]
0x14016d160  call    cs:__imp_PopThreadGuardedObject
0x14016d167  nop     dword ptr [rax+rax+00h]
0x14016d16c  mov     rax, r14
0x14016d16f  add     rsp, 0A0h
0x14016d176  pop     r15
0x14016d178  pop     r14
0x14016d17a  pop     r12
0x14016d17c  pop     rdi
0x14016d17d  pop     rsi
0x14016d17e  pop     rbx
0x14016d17f  pop     rbp
0x14016d180  retn
0x14016d182  mov     dil, [rbp+57h+var_40]
0x14016d186  neg     dil
0x14016d189  sbb     rax, rax
0x14016d18c  and     rax, rcx
0x14016d18f  lea     rcx, [rbp+57h+var_60]
0x14016d193  mov     [rbp+57h+var_A0], rax
0x14016d197  call    cs:__imp_PopThreadGuardedObject
0x14016d19e  nop     dword ptr [rax+rax+00h]
0x14016d1a3  mov     rcx, [rbp+57h+var_A0]
0x14016d1a7  test    rcx, rcx
0x14016d1aa  jz      short loc_14016D159
0x14016d1ac  jmp     loc_14016D0CC
0x14016d1b1  and     dword ptr [rcx+208h], 0FFFFFFFBh
0x14016d1b8  mov     eax, [rcx+208h]
0x14016d1be  mov     rdx, [rcx+3D0h]
0x14016d1c5  mov     ecx, [rdx+154h]
0x14016d1cb  test    dil, al
0x14016d1ce  jz      short loc_14016D1E1
0x14016d1d0  or      ecx, 16090h
0x14016d1d6  mov     [rdx+154h], ecx
0x14016d1dc  jmp     loc_14016CF92
0x14016d1e1  or      ecx, 6090h
0x14016d1e7  jmp     short loc_14016D1D6
0x14016d1e9  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14016d1f0  nop     dword ptr [rax+rax+00h]
0x14016d1f5  cmp     eax, edi
0x14016d1f7  jz      short loc_14016D207
0x14016d1f9  mov     ecx, edi
0x14016d1fb  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14016d202  nop     dword ptr [rax+rax+00h]
0x14016d207  mov     rcx, [rbp+57h+var_A0]
0x14016d20b  jmp     loc_14016CEF5
0x14016d210  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14016d215  jmp     loc_14016CFD6
0x14016d21a  lock dec word ptr [rax+0Ch]
0x14016d21f  mov     rcx, r12
0x14016d222  mov     [rbp+57h+var_A0], rcx
0x14016d226  jmp     loc_14016CEF5
0x14016d22b  xorps   xmm0, xmm0
0x14016d22e  lea     r14, [rsi+868h]
0x14016d235  movups  xmmword ptr [r14], xmm0
0x14016d239  xor     eax, eax
0x14016d23b  xor     ecx, ecx
0x14016d23d  mov     [r14+10h], rax
0x14016d241  mov     dword ptr [rsi+870h], 80000012h
0x14016d24b  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14016d252  nop     dword ptr [rax+rax+00h]
0x14016d257  mov     [rsi+878h], rax
0x14016d25e  jmp     loc_14016CF3A
0x14016d263  mov     rax, [rbp+57h+var_A0]
0x14016d267  lock dec word ptr [rax+0Ch]
0x14016d26c  mov     [rbp+57h+var_A0], r12
0x14016d270  jmp     loc_14016CF92
0x14016d275  lea     rcx, [rbp+57h+var_A0]; this
0x14016d279  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x14016d27e  jmp     loc_14016CFE7
0x14016d283  xorps   xmm0, xmm0
0x14016d286  lea     rsi, [rbx+868h]
0x14016d28d  movups  xmmword ptr [rsi], xmm0
0x14016d290  xor     eax, eax
0x14016d292  xor     ecx, ecx
0x14016d294  mov     [rsi+10h], rax
0x14016d298  mov     dword ptr [rbx+870h], 80000012h
0x14016d2a2  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14016d2a9  nop     dword ptr [rax+rax+00h]
0x14016d2ae  mov     [rbx+878h], rax
0x14016d2b5  jmp     loc_14016D07C
0x14016d2ba  xorps   xmm0, xmm0
0x14016d2bd  lea     rsi, [rbx+868h]
0x14016d2c4  movups  xmmword ptr [rsi], xmm0
0x14016d2c7  xor     eax, eax
0x14016d2c9  xor     ecx, ecx
0x14016d2cb  mov     [rsi+10h], rax
0x14016d2cf  mov     dword ptr [rbx+870h], 80000012h
0x14016d2d9  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14016d2e0  nop     dword ptr [rax+rax+00h]
0x14016d2e5  mov     [rbx+878h], rax
0x14016d2ec  jmp     loc_14016D10E
```
