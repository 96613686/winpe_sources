# NtGdiSelectBitmap

- ea: `0x1401592a0`
- end: `0x140159741`
- name: `NtGdiSelectBitmap`
- size: `1185`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400a4e80`
- `0x140154d18`
- `0x1401592a0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140159355`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140159497`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140159529`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140159355`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140159497`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140159529`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401592c8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401592c8`
- `win32kbase!HmgPentryFromPobj` at `0x14015937b`
- `win32kbase!HmgPentryFromPobj` at `0x1401594bd`
- `win32kbase!HmgPentryFromPobj` at `0x14015954f`
- `win32kbase!HmgPentryFromPobj` at `0x14015937b`
- `win32kbase!HmgPentryFromPobj` at `0x1401594bd`
- `win32kbase!HmgPentryFromPobj` at `0x14015954f`
- `win32kbase!PopThreadGuardedObject` at `0x140159471`
- `win32kbase!PopThreadGuardedObject` at `0x1401595b0`
- `win32kbase!PopThreadGuardedObject` at `0x1401595e7`
- `win32kbase!PopThreadGuardedObject` at `0x140159471`
- `win32kbase!PopThreadGuardedObject` at `0x1401595b0`
- `win32kbase!PopThreadGuardedObject` at `0x1401595e7`
- `win32kbase!PushThreadGuardedObject` at `0x1401592fe`
- `win32kbase!PushThreadGuardedObject` at `0x1401593fc`
- `win32kbase!PushThreadGuardedObject` at `0x1401592fe`
- `win32kbase!PushThreadGuardedObject` at `0x1401593fc`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1401594f2`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140159584`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1401594f2`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140159584`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140159399`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1401594da`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14015956c`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140159399`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1401594da`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14015956c`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14015969b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1401596f2`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140159729`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14015969b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1401596f2`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140159729`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1401593b1`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1401593b1`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14015964b`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14015964b`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140159639`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140159639`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14015931c`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14015931c`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x140159452`
- `win32kbase!?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z` at `0x140159452`

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
0x1401592a0  push    rbp
0x1401592a2  push    rbx
0x1401592a3  push    rsi
0x1401592a4  push    rdi
0x1401592a5  push    r12
0x1401592a7  push    r14
0x1401592a9  push    r15
0x1401592ab  lea     rbp, [rsp-27h]
0x1401592b0  sub     rsp, 0A0h
0x1401592b7  xor     r12d, r12d
0x1401592ba  mov     r15, rdx
0x1401592bd  mov     [rbp+57h+var_A0], r12
0x1401592c1  mov     rbx, rcx
0x1401592c4  mov     [rbp+57h+var_98], r12d
0x1401592c8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1401592cf  nop     dword ptr [rax+rax+00h]
0x1401592d4  xorps   xmm0, xmm0
0x1401592d7  mov     [rbp+57h+var_88], r12
0x1401592db  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1401592e2  mov     [rbp+57h+var_90], rax
0x1401592e6  lea     rdx, [rbp+57h+var_A0]
0x1401592ea  mov     [rbp+57h+var_A0], r12
0x1401592ee  lea     rcx, [rbp+57h+var_80]
0x1401592f2  mov     [rbp+57h+var_98], r12d
0x1401592f6  movups  [rbp+57h+var_80], xmm0
0x1401592fa  movups  [rbp+57h+var_70], xmm0
0x1401592fe  call    cs:__imp_PushThreadGuardedObject
0x140159305  nop     dword ptr [rax+rax+00h]
0x14015930a  mov     rcx, [rbp+57h+var_90]
0x14015930e  lea     edi, [r12+1]
0x140159313  mov     r8b, dil
0x140159316  xor     r9d, r9d
0x140159319  mov     rdx, rbx
0x14015931c  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140159323  nop     dword ptr [rax+rax+00h]
0x140159328  mov     [rbp+57h+var_A0], rax
0x14015932c  mov     rcx, rax
0x14015932f  test    rax, rax
0x140159332  jz      loc_140159639
0x140159338  cmp     [rax+858h], r12d
0x14015933f  jnz     loc_14015966A
0x140159345  test    rcx, rcx
0x140159348  jz      loc_1401593E2
0x14015934e  mov     eax, [rcx+2Ch]
0x140159351  test    al, 2
0x140159353  jnz     short loc_1401593D4
0x140159355  call    cs:__imp_PsGetCurrentProcessId
0x14015935c  nop     dword ptr [rax+rax+00h]
0x140159361  mov     rsi, [rbp+57h+var_A0]
0x140159365  mov     rbx, rax
0x140159368  and     ebx, 0FFFFFFFCh
0x14015936b  cmp     [rsi], r12
0x14015936e  jz      loc_14015967B
0x140159374  mov     rcx, [rbp+57h+var_90]
0x140159378  mov     rdx, rsi
0x14015937b  call    cs:__imp_HmgPentryFromPobj
0x140159382  nop     dword ptr [rax+rax+00h]
0x140159387  mov     r14, rax
0x14015938a  mov     eax, [r14+8]
0x14015938e  and     eax, 0FFFFFFFEh
0x140159391  cmp     ebx, eax
0x140159393  jnz     short loc_1401593C5
0x140159395  lea     rcx, [rbp+57h+var_A0]
0x140159399  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x1401593a0  nop     dword ptr [rax+rax+00h]
0x1401593a5  test    rax, rax
0x1401593a8  jz      short loc_1401593C5
0x1401593aa  mov     rcx, [rbp+57h+var_A0]
0x1401593ae  mov     rdx, rax
0x1401593b1  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x1401593b8  nop     dword ptr [rax+rax+00h]
0x1401593bd  test    eax, eax
0x1401593bf  jz      loc_1401596B3
0x1401593c5  mov     rax, [rbp+57h+var_A0]
0x1401593c9  or      dword ptr [rax+2Ch], 2
0x1401593cd  mov     rcx, [rbp+57h+var_A0]
0x1401593d1  mov     [rbp+57h+var_98], edi
0x1401593d4  mov     eax, [rcx+208h]
0x1401593da  test    al, 4
0x1401593dc  jnz     loc_140159601
0x1401593e2  xorps   xmm0, xmm0
0x1401593e5  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1401593ec  lea     rdx, [rbp+57h+var_A0]
0x1401593f0  lea     rcx, [rbp+57h+var_60]
0x1401593f4  movups  [rbp+57h+var_60], xmm0
0x1401593f8  movups  [rbp+57h+var_50], xmm0
0x1401593fc  call    cs:__imp_PushThreadGuardedObject
0x140159403  nop     dword ptr [rax+rax+00h]
0x140159408  mov     rcx, [rbp+57h+var_A0]
0x14015940c  mov     [rbp+57h+var_40], dil
0x140159410  test    rcx, rcx
0x140159413  jz      loc_1401595D6
0x140159419  movzx   eax, word ptr [rcx+0Ch]
0x14015941d  cmp     ax, di
0x140159420  jnz     loc_140159660
0x140159426  mov     rax, [rbp+57h+var_A0]
0x14015942a  movzx   ecx, word ptr [rax+0Ch]
0x14015942e  cmp     cx, di
0x140159431  jnz     loc_1401596C5
0x140159437  mov     rcx, [rbp+57h+var_A0]
0x14015943b  test    rcx, rcx
0x14015943e  jz      loc_1401595D2
0x140159444  xor     r9d, r9d
0x140159447  lea     rdx, [rbp+57h+var_A0]
0x14015944b  mov     r8, r15
0x14015944e  lea     rcx, [rbp+57h+var_B0]
0x140159452  call    cs:__imp_?GrepSelectBitmap@@YA?AVGSBResult@@AEAVXDCOBJ@@PEAUHBITMAP__@@W4GSBOptions@@@Z; GrepSelectBitmap(XDCOBJ &,HBITMAP__ *,GSBOptions)
0x140159459  nop     dword ptr [rax+rax+00h]
0x14015945e  mov     r14, [rax]
0x140159461  mov     al, [rbp+57h+var_40]
0x140159464  neg     al
0x140159466  sbb     rcx, rcx
0x140159469  and     [rbp+57h+var_A0], rcx
0x14015946d  lea     rcx, [rbp+57h+var_60]
0x140159471  call    cs:__imp_PopThreadGuardedObject
0x140159478  nop     dword ptr [rax+rax+00h]
0x14015947d  mov     rcx, [rbp+57h+var_A0]
0x140159481  test    rcx, rcx
0x140159484  jz      loc_1401595AC
0x14015948a  cmp     [rbp+57h+var_98], r12d
0x14015948e  jz      short loc_14015950E
0x140159490  mov     eax, [rcx+2Ch]
0x140159493  test    al, 2
0x140159495  jz      short loc_14015950E
0x140159497  call    cs:__imp_PsGetCurrentProcessId
0x14015949e  nop     dword ptr [rax+rax+00h]
0x1401594a3  mov     rbx, [rbp+57h+var_A0]
0x1401594a7  mov     rdi, rax
0x1401594aa  and     edi, 0FFFFFFFCh
0x1401594ad  cmp     [rbx], r12
0x1401594b0  jz      loc_1401596D3
0x1401594b6  mov     rcx, [rbp+57h+var_90]
0x1401594ba  mov     rdx, rbx
0x1401594bd  call    cs:__imp_HmgPentryFromPobj
0x1401594c4  nop     dword ptr [rax+rax+00h]
0x1401594c9  mov     rsi, rax
0x1401594cc  mov     eax, [rsi+8]
0x1401594cf  and     eax, 0FFFFFFFEh
0x1401594d2  cmp     edi, eax
0x1401594d4  jnz     short loc_1401594FE
0x1401594d6  lea     rcx, [rbp+57h+var_A0]
0x1401594da  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x1401594e1  nop     dword ptr [rax+rax+00h]
0x1401594e6  test    rax, rax
0x1401594e9  jz      short loc_1401594FE
0x1401594eb  mov     rcx, [rbp+57h+var_A0]
0x1401594ef  mov     rdx, rax
0x1401594f2  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x1401594f9  nop     dword ptr [rax+rax+00h]
0x1401594fe  mov     rax, [rbp+57h+var_A0]
0x140159502  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x140159506  mov     rcx, [rbp+57h+var_A0]
0x14015950a  mov     [rbp+57h+var_98], r12d
0x14015950e  lock dec word ptr [rcx+0Ch]
0x140159513  mov     [rbp+57h+var_A0], r12
0x140159517  jmp     loc_1401595AC
0x14015951c  cmp     [rbp+57h+var_98], r12d
0x140159520  jz      short loc_1401595A0
0x140159522  mov     eax, [rcx+2Ch]
0x140159525  test    al, 2
0x140159527  jz      short loc_1401595A0
0x140159529  call    cs:__imp_PsGetCurrentProcessId
0x140159530  nop     dword ptr [rax+rax+00h]
0x140159535  mov     rbx, [rbp+57h+var_A0]
0x140159539  mov     rdi, rax
0x14015953c  and     edi, 0FFFFFFFCh
0x14015953f  cmp     [rbx], r12
0x140159542  jz      loc_14015970A
0x140159548  mov     rcx, [rbp+57h+var_90]
0x14015954c  mov     rdx, rbx
0x14015954f  call    cs:__imp_HmgPentryFromPobj
0x140159556  nop     dword ptr [rax+rax+00h]
0x14015955b  mov     rsi, rax
0x14015955e  mov     eax, [rsi+8]
0x140159561  and     eax, 0FFFFFFFEh
0x140159564  cmp     edi, eax
0x140159566  jnz     short loc_140159590
0x140159568  lea     rcx, [rbp+57h+var_A0]
0x14015956c  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140159573  nop     dword ptr [rax+rax+00h]
0x140159578  test    rax, rax
0x14015957b  jz      short loc_140159590
0x14015957d  mov     rcx, [rbp+57h+var_A0]
0x140159581  mov     rdx, rax
0x140159584  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14015958b  nop     dword ptr [rax+rax+00h]
0x140159590  mov     rax, [rbp+57h+var_A0]
0x140159594  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x140159598  mov     rcx, [rbp+57h+var_A0]
0x14015959c  mov     [rbp+57h+var_98], r12d
0x1401595a0  lock dec word ptr [rcx+0Ch]
0x1401595a5  mov     [rbp+57h+var_A0], r12
0x1401595a9  mov     r14, r12
0x1401595ac  lea     rcx, [rbp+57h+var_80]
0x1401595b0  call    cs:__imp_PopThreadGuardedObject
0x1401595b7  nop     dword ptr [rax+rax+00h]
0x1401595bc  mov     rax, r14
0x1401595bf  add     rsp, 0A0h
0x1401595c6  pop     r15
0x1401595c8  pop     r14
0x1401595ca  pop     r12
0x1401595cc  pop     rdi
0x1401595cd  pop     rsi
0x1401595ce  pop     rbx
0x1401595cf  pop     rbp
0x1401595d0  retn
0x1401595d2  mov     dil, [rbp+57h+var_40]
0x1401595d6  neg     dil
0x1401595d9  sbb     rax, rax
0x1401595dc  and     rax, rcx
0x1401595df  lea     rcx, [rbp+57h+var_60]
0x1401595e3  mov     [rbp+57h+var_A0], rax
0x1401595e7  call    cs:__imp_PopThreadGuardedObject
0x1401595ee  nop     dword ptr [rax+rax+00h]
0x1401595f3  mov     rcx, [rbp+57h+var_A0]
0x1401595f7  test    rcx, rcx
0x1401595fa  jz      short loc_1401595A9
0x1401595fc  jmp     loc_14015951C
0x140159601  and     dword ptr [rcx+208h], 0FFFFFFFBh
0x140159608  mov     eax, [rcx+208h]
0x14015960e  mov     rdx, [rcx+3D0h]
0x140159615  mov     ecx, [rdx+154h]
0x14015961b  test    dil, al
0x14015961e  jz      short loc_140159631
0x140159620  or      ecx, 16090h
0x140159626  mov     [rdx+154h], ecx
0x14015962c  jmp     loc_1401593E2
0x140159631  or      ecx, 6090h
0x140159637  jmp     short loc_140159626
0x140159639  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140159640  nop     dword ptr [rax+rax+00h]
0x140159645  cmp     eax, edi
0x140159647  jz      short loc_140159657
0x140159649  mov     ecx, edi
0x14015964b  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x140159652  nop     dword ptr [rax+rax+00h]
0x140159657  mov     rcx, [rbp+57h+var_A0]
0x14015965b  jmp     loc_140159345
0x140159660  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140159665  jmp     loc_140159426
0x14015966a  lock dec word ptr [rax+0Ch]
0x14015966f  mov     rcx, r12
0x140159672  mov     [rbp+57h+var_A0], rcx
0x140159676  jmp     loc_140159345
0x14015967b  xorps   xmm0, xmm0
0x14015967e  lea     r14, [rsi+868h]
0x140159685  movups  xmmword ptr [r14], xmm0
0x140159689  xor     eax, eax
0x14015968b  xor     ecx, ecx
0x14015968d  mov     [r14+10h], rax
0x140159691  mov     dword ptr [rsi+870h], 80000012h
0x14015969b  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x1401596a2  nop     dword ptr [rax+rax+00h]
0x1401596a7  mov     [rsi+878h], rax
0x1401596ae  jmp     loc_14015938A
0x1401596b3  mov     rax, [rbp+57h+var_A0]
0x1401596b7  lock dec word ptr [rax+0Ch]
0x1401596bc  mov     [rbp+57h+var_A0], r12
0x1401596c0  jmp     loc_1401593E2
0x1401596c5  lea     rcx, [rbp+57h+var_A0]; this
0x1401596c9  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x1401596ce  jmp     loc_140159437
0x1401596d3  xorps   xmm0, xmm0
0x1401596d6  lea     rsi, [rbx+868h]
0x1401596dd  movups  xmmword ptr [rsi], xmm0
0x1401596e0  xor     eax, eax
0x1401596e2  xor     ecx, ecx
0x1401596e4  mov     [rsi+10h], rax
0x1401596e8  mov     dword ptr [rbx+870h], 80000012h
0x1401596f2  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x1401596f9  nop     dword ptr [rax+rax+00h]
0x1401596fe  mov     [rbx+878h], rax
0x140159705  jmp     loc_1401594CC
0x14015970a  xorps   xmm0, xmm0
0x14015970d  lea     rsi, [rbx+868h]
0x140159714  movups  xmmword ptr [rsi], xmm0
0x140159717  xor     eax, eax
0x140159719  xor     ecx, ecx
0x14015971b  mov     [rsi+10h], rax
0x14015971f  mov     dword ptr [rbx+870h], 80000012h
0x140159729  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140159730  nop     dword ptr [rax+rax+00h]
0x140159735  mov     [rbx+878h], rax
0x14015973c  jmp     loc_14015955E
```
