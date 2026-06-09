# NtUserSystemParametersInfo

- ea: `0x14019a180`
- end: `0x14019ba2c`
- name: `NtUserSystemParametersInfo`
- size: `6316`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int64, int)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140022c58`
- `0x140022ca0`
- `0x140029710`
- `0x14004dfb0`
- `0x14004f4c0`
- `0x14004f550`
- `0x140059304`
- `0x14006f3a4`
- `0x1400700d8`
- `0x1400701d4`
- `0x140070518`
- `0x14007df80`
- `0x1401741d4`
- `0x140193100`
- `0x14019a180`
- `0x14019bc20`
- `0x1401aab9c`
- `0x1401c7158`
- `0x1401c7d70`
- `0x1401c8bd8`
- `0x1401c8cd0`
- `0x140238a40`
- `0x140238f80`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14019ac31`
- `ntoskrnl!ProbeForRead` at `0x14019b3d6`
- `ntoskrnl!ProbeForRead` at `0x14019b553`
- `ntoskrnl!ProbeForRead` at `0x14019b6c0`
- `ntoskrnl!ProbeForRead` at `0x14019ac31`
- `ntoskrnl!ProbeForRead` at `0x14019b3d6`
- `ntoskrnl!ProbeForRead` at `0x14019b553`
- `ntoskrnl!ProbeForRead` at `0x14019b6c0`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14019ac92`
- `ntoskrnl!ExRaiseAccessViolation` at `0x14019ac92`
- `ntoskrnl!KeBugCheckEx` at `0x14019a744`
- `ntoskrnl!KeBugCheckEx` at `0x14019a911`
- `ntoskrnl!KeBugCheckEx` at `0x14019a744`
- `ntoskrnl!KeBugCheckEx` at `0x14019a911`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a287`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a2d6`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019b9c5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a287`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a2d6`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019b9c5`
- `ntoskrnl!ExRaiseStatus` at `0x14019a8cf`
- `ntoskrnl!ExRaiseStatus` at `0x14019a8cf`
- `ntoskrnl!ProbeForWrite` at `0x14019ab62`
- `ntoskrnl!ProbeForWrite` at `0x14019ab9c`
- `ntoskrnl!ProbeForWrite` at `0x14019ada0`
- `ntoskrnl!ProbeForWrite` at `0x14019afad`
- `ntoskrnl!ProbeForWrite` at `0x14019b775`
- `ntoskrnl!ProbeForWrite` at `0x14019ab62`
- `ntoskrnl!ProbeForWrite` at `0x14019ab9c`
- `ntoskrnl!ProbeForWrite` at `0x14019ada0`
- `ntoskrnl!ProbeForWrite` at `0x14019afad`
- `ntoskrnl!ProbeForWrite` at `0x14019b775`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019ab42`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019af8c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b3b7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b534`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b757`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019ab42`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019af8c`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b3b7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b534`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x14019b757`
- `WIN32K!W32GetUserSessionState` at `0x14019a1c0`
- `WIN32K!W32GetUserSessionState` at `0x14019a1c0`

## pseudocode

```c
__int64 __fastcall NtUserSystemParametersInfo(unsigned int a1, unsigned int a2, unsigned __int64 a3, int a4)
{
  __int64 v4; // r15
  unsigned int v6; // edi
  __int64 UserSessionState; // rbx
  __int64 v8; // r14
  bool HasUILimit; // bl
  struct tagTHREADINFO *v10; // rdx
  int v11; // ecx
  __int64 CurrentProcessWin32Process; // rax
  unsigned int v13; // r8d
  char HasMinimumIntegrityLevel; // al
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  unsigned __int8 v18; // cf
  bool v19; // zf
  unsigned int v20; // eax
  bool v21; // zf
  bool v22; // zf
  unsigned int v23; // eax
  bool v24; // zf
  unsigned int v25; // eax
  __int64 v26; // r14
  bool v27; // zf
  unsigned int v28; // eax
  unsigned int v29; // eax
  _DWORD *v30; // r13
  int v31; // ebx
  __int64 v32; // rcx
  struct tagTHREADINFO *BugCheckParameter4; // rax
  struct tagTHREADINFO *v34; // rax
  __int64 v35; // rdx
  NTSTATUS v36; // eax
  ULONG_PTR v37; // rbx
  struct tagTHREADINFO *v38; // rax
  struct tagTHREADINFO *v39; // rax
  unsigned int v40; // eax
  __int64 v41; // rax
  int v42; // r14d
  __int64 v43; // xmm0_8
  unsigned __int16 v44; // cx
  bool v45; // zf
  bool v46; // zf
  unsigned int v47; // eax
  __int64 v48; // rax
  void *v49; // r13
  _OWORD *v50; // rax
  _DWORD *v51; // r8
  _OWORD *v52; // rdx
  _OWORD *v53; // rdx
  _OWORD *v54; // rax
  __int64 v55; // r8
  _DWORD *v56; // r8
  _OWORD *v57; // rdx
  _OWORD *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  _DWORD *v61; // rbx
  __int64 CurrentProcessWow64Process; // rax
  unsigned __int64 v63; // rbx
  unsigned int ULongFromUser; // eax
  __int64 v65; // rax
  __int64 v66; // rcx
  volatile void *v69; // [rsp+48h] [rbp-530h]
  ULONG_PTR v70[2]; // [rsp+50h] [rbp-528h] BYREF
  __int64 (__fastcall *v71)(PVOID); // [rsp+60h] [rbp-518h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+68h] [rbp-510h] BYREF
  __int64 (__fastcall *v73)(PVOID); // [rsp+78h] [rbp-500h]
  int v74; // [rsp+80h] [rbp-4F8h]
  int v75; // [rsp+84h] [rbp-4F4h]
  int v76; // [rsp+88h] [rbp-4F0h]
  _DWORD *v77; // [rsp+90h] [rbp-4E8h]
  unsigned __int64 v78; // [rsp+B8h] [rbp-4C0h] BYREF
  int v79; // [rsp+C0h] [rbp-4B8h]
  __int128 v80; // [rsp+C8h] [rbp-4B0h] BYREF
  __int64 v81; // [rsp+D8h] [rbp-4A0h]
  _BYTE v82[560]; // [rsp+E0h] [rbp-498h] BYREF
  _BYTE v83[616]; // [rsp+310h] [rbp-268h] BYREF

  v74 = a4;
  v4 = a2;
  v80 = 0;
  v6 = 0;
  v69 = 0;
  UserSessionState = W32GetUserSessionState();
  v8 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
         UserSessionState,
         0,
         0,
         _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
  *(_QWORD *)(UserSessionState + 16) = v8;
  if ( v8 )
  {
    DestroySharedUserCritDeferredUnlockList(UserSessionState + 19520);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
    DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
  }
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(BugCheckParameter2);
  Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v70);
  if ( (unsigned int)Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline() )
  {
    HasUILimit = tagPROCESSINFO::HasUILimit(*(tagPROCESSINFO **)(v8 + 456), 8u);
  }
  else
  {
    v10 = PtiCurrent();
    v11 = 0;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)v10 + 130, 0, 0) & 0x20000000) != 0 )
      v11 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)PtiCurrent() + 57) + 752LL) + 32LL) & 8;
    HasUILimit = v11 != 0;
  }
  if ( (unsigned int)Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline() )
  {
    CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
    if ( CurrentProcessWin32Process )
      CurrentProcessWin32Process &= -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::HasMinimumIntegrityLevel(
                                 (UIPrivilegeIsolation *)(CurrentProcessWin32Process + 864),
                                 (const struct tagUIPI_INFO *)0x2000,
                                 v13);
  }
  else
  {
    v78 = 0xFFFFFFFF00002000uLL;
    v79 = 0;
    v16 = PsGetCurrentProcessWin32Process();
    if ( v16 )
      v16 &= -(__int64)(*(_QWORD *)v16 != 0);
    HasMinimumIntegrityLevel = UIPrivilegeIsolation::CheckAccessEx(v16 + 864, &v78, 0);
  }
  if ( !HasUILimit && HasMinimumIntegrityLevel )
    goto LABEL_127;
  if ( a1 <= 0x6D )
  {
    if ( a1 == 109 )
      goto LABEL_402;
    if ( a1 > 0x37 )
    {
      if ( a1 <= 0x55 )
      {
        if ( a1 == 85 )
          goto LABEL_402;
        if ( a1 > 0x49 )
        {
          if ( a1 != 75 && a1 != 76 && a1 != 77 && a1 != 78 && a1 - 81 >= 2 )
            goto LABEL_127;
          goto LABEL_402;
        }
        if ( a1 - 57 <= 0x10 )
        {
          v15 = 87317;
          v18 = _bittest((const int *)&v15, a1 - 57);
LABEL_26:
          if ( !v18 )
            goto LABEL_127;
LABEL_402:
          v65 = PsGetCurrentProcessWin32Process();
          v66 = v65;
          if ( v65 )
            v66 = ((unsigned __int128)-(__int128)*(unsigned __int64 *)v65 >> 64) & v65;
          EtwTraceUIPISystemError(v66, 0, 1);
          v31 = 0;
          v32 = 5;
          goto LABEL_405;
        }
LABEL_127:
        v26 = 4;
        goto LABEL_128;
      }
      if ( a1 > 0x60 )
      {
        if ( a1 - 97 > 0xA || (((_BYTE)a1 - 97) & 1) != 0 )
          goto LABEL_127;
        goto LABEL_402;
      }
      if ( a1 == 96 || a1 == 86 || a1 == 87 || a1 == 88 || a1 == 90 )
        goto LABEL_402;
      v25 = a1 - 91;
      v24 = a1 == 91;
      goto LABEL_124;
    }
    if ( a1 == 55 )
      goto LABEL_402;
    if ( a1 <= 0x1D )
    {
      if ( a1 == 29 )
        goto LABEL_402;
      if ( a1 <= 0x13 )
      {
        v17 = 698452;
        v18 = _bittest(&v17, a1);
        goto LABEL_26;
      }
      if ( a1 == 20 || a1 == 21 || a1 == 23 )
        goto LABEL_402;
      v20 = a1 - 24;
      v19 = a1 == 24;
      goto LABEL_122;
    }
    if ( a1 <= 0x2A )
    {
      if ( a1 == 42 || a1 == 30 || a1 == 32 || a1 == 33 || a1 == 34 || a1 == 36 )
        goto LABEL_402;
      v21 = a1 == 37;
LABEL_126:
      if ( v21 )
        goto LABEL_402;
      goto LABEL_127;
    }
    if ( a1 == 44 || a1 == 46 )
      goto LABEL_402;
    v23 = a1 - 47;
    v22 = a1 == 47;
    goto LABEL_120;
  }
  if ( a1 <= 0x1017 )
  {
    if ( a1 == 4119 )
      goto LABEL_402;
    if ( a1 <= 0xAD )
    {
      if ( a1 == 173 )
        goto LABEL_402;
      if ( a1 > 0x99 )
      {
        if ( a1 == 155 || a1 == 161 || a1 == 163 || a1 == 166 )
          goto LABEL_402;
        v25 = a1 - 169;
        v24 = a1 == 169;
LABEL_124:
        if ( v24 )
          goto LABEL_402;
        v21 = v25 == 2;
        goto LABEL_126;
      }
      switch ( a1 )
      {
        case 0x99u:
          goto LABEL_402;
        case 0x6Fu:
          goto LABEL_402;
        case 0x71u:
          goto LABEL_402;
      }
      v26 = 4;
      if ( a1 == 117 || a1 == 119 || a1 == 147 )
        goto LABEL_402;
      v28 = a1 - 149;
      v27 = a1 == 149;
      goto LABEL_114;
    }
    if ( a1 <= 0x1007 )
    {
      if ( a1 == 4103 || a1 == 175 || a1 == 177 || a1 == 179 )
        goto LABEL_402;
      v20 = a1 - 4097;
      v19 = a1 == 4097;
LABEL_122:
      if ( v19 )
        goto LABEL_402;
      v25 = v20 - 2;
      v24 = v25 == 0;
      goto LABEL_124;
    }
    switch ( a1 )
    {
      case 0x1009u:
        goto LABEL_402;
      case 0x100Bu:
        goto LABEL_402;
      case 0x100Du:
        goto LABEL_402;
    }
    v29 = a1 - 4111;
    if ( a1 == 4111 )
      goto LABEL_402;
    v26 = 4;
LABEL_113:
    v28 = v29 - 4;
    v27 = v28 == 0;
    goto LABEL_114;
  }
  if ( a1 > 0x2003 )
  {
    if ( a1 > 0x2019 )
    {
      if ( a1 == 8219 || a1 == 8221 )
        goto LABEL_402;
      v23 = a1 - 8241;
      v22 = a1 == 8241;
LABEL_120:
      if ( v22 )
        goto LABEL_402;
      v20 = v23 - 2;
      v19 = v20 == 0;
      goto LABEL_122;
    }
    if ( a1 == 8217 )
      goto LABEL_402;
    if ( a1 == 8197 )
      goto LABEL_402;
    v26 = 4;
    if ( a1 == 8201 )
      goto LABEL_402;
    if ( a1 == 8207 )
      goto LABEL_402;
    v29 = a1 - 8209;
    if ( a1 == 8209 )
      goto LABEL_402;
    goto LABEL_113;
  }
  if ( a1 == 8195 )
    goto LABEL_402;
  if ( a1 > 0x1049 )
  {
    if ( a1 == 4171 || a1 == 4173 || a1 == 4175 || a1 == 4177 || a1 == 4179 )
      goto LABEL_402;
    v21 = a1 == 8193;
    goto LABEL_126;
  }
  if ( a1 == 4169 )
    goto LABEL_402;
  if ( a1 == 4121 )
    goto LABEL_402;
  v26 = 4;
  if ( a1 == 4125 || a1 == 4127 || a1 == 4135 )
    goto LABEL_402;
  v28 = a1 - 4161;
  v27 = a1 == 4161;
LABEL_114:
  if ( v27 || v28 == 2 )
    goto LABEL_402;
LABEL_128:
  v30 = Win32AllocPoolWithQuotaZInitImpl(v15, 0x228u, 0x79747355u);
  v77 = v30;
  if ( !v30 )
  {
    v31 = 0;
    v32 = 8;
LABEL_405:
    UserSetLastError(v32);
LABEL_406:
    Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(v70);
    Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(BugCheckParameter2);
    goto LABEL_407;
  }
  if ( v73 != (__int64 (__fastcall *)(PVOID))-1LL )
  {
    BugCheckParameter4 = PtiCurrent();
    KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)v30, (ULONG_PTR)BugCheckParameter4);
  }
  v74 &= 3u;
  v34 = PtiCurrent();
  BugCheckParameter2[0] = *((_QWORD *)v34 + 47);
  *((_QWORD *)v34 + 47) = BugCheckParameter2;
  BugCheckParameter2[1] = (ULONG_PTR)v30;
  v73 = GreDeleteFastMutex;
  if ( a1 > 0x1026 )
  {
    if ( a1 == 4135 )
      goto LABEL_398;
    if ( a1 == 8221 )
    {
      v31 = 0;
      if ( a3 > 2 )
        goto LABEL_397;
      goto LABEL_398;
    }
    goto LABEL_380;
  }
  if ( a1 == 4134 )
    goto LABEL_395;
  if ( a1 <= 0x62 )
  {
    if ( a1 == 98 )
      goto LABEL_395;
    if ( a1 <= 0x32 )
    {
      if ( a1 == 50 )
      {
        v6 = 24;
        goto LABEL_377;
      }
      if ( a1 <= 0x19 )
      {
        if ( a1 == 25 )
          goto LABEL_395;
        if ( a1 > 0xE )
        {
          switch ( a1 )
          {
            case 0x10u:
            case 0x12u:
              goto LABEL_395;
            case 0x14u:
              if ( !a3 )
                a3 = -1;
              if ( a3 == -2 || a3 == -1 )
              {
                LODWORD(v4) = -1;
                v76 = -1;
                goto LABEL_398;
              }
              break;
            case 0x15u:
              if ( (_DWORD)v4 == -1 )
                goto LABEL_398;
              if ( !a3 )
              {
                LODWORD(v4) = -1;
                v76 = -1;
                goto LABEL_398;
              }
              break;
            default:
              if ( a1 != 22 )
              {
                if ( a1 != 24 )
                  goto LABEL_380;
LABEL_158:
                if ( (a3 & 0xFFFFFFFFFFFF0000uLL) == 0 )
                  goto LABEL_398;
              }
LABEL_395:
              v6 = 4;
              v63 = a3;
              v69 = (volatile void *)a3;
              a3 = (unsigned __int64)v30;
              ULongFromUser = RtlReadULongFromUser(v69);
              RtlWriteULongToUser(v63, ULongFromUser);
              goto LABEL_219;
          }
          v36 = DuplicateUnicodeStringFromUser<0>(a3, v35, &v80);
          if ( v36 < 0 )
            ExRaiseStatus(v36);
          a3 = *((_QWORD *)&v80 + 1);
          v37 = *((_QWORD *)&v80 + 1);
          if ( v71 != (__int64 (__fastcall *)(PVOID))-1LL )
          {
            v38 = PtiCurrent();
            KeBugCheckEx(0x164u, 0x12u, (ULONG_PTR)v70, v37, (ULONG_PTR)v38);
          }
          v39 = PtiCurrent();
          v70[0] = *((_QWORD *)v39 + 47);
          *((_QWORD *)v39 + 47) = v70;
          v70[1] = v37;
          v71 = GreDeleteFastMutex;
          goto LABEL_398;
        }
        if ( a1 == 14 || a1 == 1 )
          goto LABEL_395;
        if ( a1 != 3 )
        {
          if ( a1 != 4 )
          {
            if ( a1 != 5 && a1 != 10 )
            {
              if ( a1 != 13 )
                goto LABEL_380;
              goto LABEL_158;
            }
            goto LABEL_395;
          }
          goto LABEL_149;
        }
        goto LABEL_151;
      }
      if ( a1 <= 0x2A )
      {
        switch ( a1 )
        {
          case 0x2Au:
            if ( (((_DWORD)v4 - 500) & 0xFFFFFFFB) != 0 )
              goto LABEL_315;
            v6 = v4;
            break;
          case 0x1Bu:
            goto LABEL_395;
          case 0x1Fu:
            v6 = 92;
            goto LABEL_377;
          case 0x22u:
            v6 = 92;
            break;
          case 0x23u:
          case 0x26u:
            goto LABEL_395;
          case 0x29u:
            if ( (((_DWORD)v4 - 500) & 0xFFFFFFFB) != 0 )
              goto LABEL_315;
            v6 = v4;
LABEL_377:
            v61 = (_DWORD *)a3;
            v69 = (volatile void *)a3;
            a3 = (unsigned __int64)v30;
            CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
            ProbeForWrite(v61, v6, CurrentProcessWow64Process != 0 ? 1 : 4);
            v42 = 1;
            v75 = 1;
            *v30 = *v61;
            goto LABEL_399;
          default:
            goto LABEL_380;
        }
LABEL_372:
        ProbeForRead((volatile void *)a3, v6, 4u);
        memmove(v30, (const void *)a3, v6);
        a3 = (unsigned __int64)v30;
        goto LABEL_398;
      }
      switch ( a1 )
      {
        case '+':
          v6 = 20;
          goto LABEL_377;
        case ',':
          v6 = 20;
          goto LABEL_372;
        case '-':
          v6 = 108;
          goto LABEL_377;
        case '.':
          v6 = 108;
          goto LABEL_372;
      }
      if ( a1 != 47 )
      {
        if ( a1 != 48 )
          goto LABEL_380;
        goto LABEL_194;
      }
      goto LABEL_322;
    }
    if ( a1 > 0x43 )
    {
      if ( a1 > 0x50 )
      {
        if ( a1 == 83 || a1 == 84 )
          goto LABEL_395;
        if ( a1 != 89 )
        {
          if ( a1 != 90 )
          {
            v40 = a1 - 94;
            if ( a1 == 94 )
              goto LABEL_395;
LABEL_243:
            v45 = v40 == 1;
LABEL_270:
            if ( v45 )
              goto LABEL_395;
            goto LABEL_380;
          }
          goto LABEL_222;
        }
      }
      else
      {
        if ( a1 == 80 || a1 == 68 || a1 == 70 )
          goto LABEL_395;
        if ( a1 != 72 )
        {
          if ( a1 != 73 )
          {
            if ( a1 == 74 )
              goto LABEL_395;
            v45 = a1 == 79;
            goto LABEL_270;
          }
          goto LABEL_222;
        }
      }
LABEL_244:
      v6 = 8;
      goto LABEL_377;
    }
    if ( a1 != 67 )
    {
      if ( a1 <= 0x3A )
      {
        if ( a1 != 58 )
        {
          if ( a1 == 51 )
          {
            v6 = 24;
            goto LABEL_372;
          }
          if ( a1 != 52 )
          {
            if ( a1 != 53 )
            {
              if ( a1 != 54 )
              {
                v40 = a1 - 55;
                if ( a1 == 55 )
                  goto LABEL_209;
                goto LABEL_243;
              }
LABEL_210:
              v6 = 28;
              goto LABEL_377;
            }
LABEL_222:
            v6 = 8;
            goto LABEL_372;
          }
        }
        goto LABEL_244;
      }
      if ( a1 == 59 )
        goto LABEL_222;
      if ( a1 != 60 )
      {
        if ( a1 != 61 )
        {
          switch ( a1 )
          {
            case '@':
              v6 = 56;
              goto LABEL_377;
            case 'A':
              v6 = 56;
              goto LABEL_372;
            case 'B':
              v6 = 16;
              v41 = PsGetCurrentProcessWow64Process();
              ProbeForWrite((volatile void *)a3, 0x10u, v41 != 0 ? 1 : 4);
              v69 = (volatile void *)a3;
              *(_OWORD *)v30 = *(_OWORD *)a3;
              a3 = (unsigned __int64)v30;
              ProbeForWrite(*((volatile void **)v30 + 1), 0x100u, 2u);
LABEL_219:
              v42 = 1;
              v75 = 1;
LABEL_399:
              v49 = (void *)v69;
              goto LABEL_400;
          }
LABEL_380:
          if ( a1 < 0xB6 )
            goto LABEL_398;
          if ( a1 - 4096 <= 0x55 || a1 - 0x2000 <= 0x37 )
          {
            v31 = 0;
            if ( (_DWORD)v4 && (*((_DWORD *)PtiCurrent() + 166) > 0x400u || a1 != 4159 || (_DWORD)v4 != 1) )
              goto LABEL_397;
            if ( (a1 & 1) != 0 )
            {
              if ( a1 != 8203 )
              {
                if ( a1 == 8211 )
                {
                  v77 = (_DWORD *)a3;
                  if ( (a3 & 0xFFFFFFFE) != 0 )
                    goto LABEL_397;
                }
                goto LABEL_398;
              }
              v78 = a3;
              if ( (a3 & 0xFFFFFFFC) != 0 )
              {
LABEL_397:
                UserSetLastError(87);
                Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(v70);
                Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(BugCheckParameter2);
                goto LABEL_407;
              }
LABEL_398:
              v42 = 0;
              goto LABEL_399;
            }
            goto LABEL_395;
          }
          goto LABEL_315;
        }
LABEL_149:
        v6 = 12;
        goto LABEL_372;
      }
LABEL_151:
      v6 = 12;
      goto LABEL_377;
    }
    v80 = 0;
    v81 = 0;
    RtlCopyFromUser(&v80, (void *)a3, 0x18u);
    v43 = v81;
    *(_OWORD *)v30 = v80;
    *((_QWORD *)v30 + 2) = v43;
    a3 = (unsigned __int64)v30;
    ProbeForRead(*((volatile void **)v30 + 2), *((unsigned __int16 *)v30 + 4) + 2LL, 2u);
    v44 = *((_WORD *)v30 + 4);
    if ( v44 > *((_WORD *)v30 + 5) )
    {
      if ( (v44 & 1) == 0 )
        goto LABEL_229;
    }
    else if ( (v44 & 1) == 0 )
    {
      if ( !v44 )
        *((_QWORD *)v30 + 2) = 0;
      goto LABEL_398;
    }
    v74 = 0x20000;
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 483);
LABEL_229:
    ExRaiseAccessViolation();
  }
  if ( a1 <= 0x94 )
  {
    if ( a1 == 148 )
    {
      v6 = 40;
      if ( (_DWORD)v4 != 40 )
        goto LABEL_315;
      goto LABEL_377;
    }
    if ( a1 > 0x7A )
    {
      if ( a1 > 0x88 )
      {
        if ( a1 == 138 || a1 == 140 || a1 == 142 || a1 == 144 )
          goto LABEL_395;
        if ( a1 == 146 )
        {
          if ( (_DWORD)v4 != 68 )
            goto LABEL_315;
          v6 = 68;
          goto LABEL_377;
        }
        if ( a1 != 147 )
          goto LABEL_380;
        if ( (_DWORD)v4 != 68 )
          goto LABEL_315;
        v6 = 68;
        goto LABEL_372;
      }
      if ( a1 == 136 || a1 == 124 || a1 == 126 || a1 == 128 || a1 == 130 )
        goto LABEL_395;
      v47 = a1 - 132;
      v46 = a1 == 132;
    }
    else
    {
      if ( a1 == 122 )
        goto LABEL_395;
      if ( a1 <= 0x70 )
      {
        if ( ((a1 - 100) & 0xFFFFFFF1) != 0 )
          goto LABEL_380;
        goto LABEL_395;
      }
      switch ( a1 )
      {
        case 'r':
          goto LABEL_395;
        case 's':
          v69 = (volatile void *)a3;
          a3 = (unsigned __int64)v30;
          ProbeForWrite(v69, 2 * v4, 2u);
          if ( (unsigned int)v4 >= 0x104 )
            LODWORD(v4) = 260;
          v76 = v4;
          v6 = 2 * v4;
          goto LABEL_219;
        case 't':
          goto LABEL_151;
        case 'u':
          goto LABEL_149;
      }
      v47 = a1 - 118;
      v46 = a1 == 118;
    }
    if ( v46 )
      goto LABEL_395;
    v45 = v47 == 2;
    goto LABEL_270;
  }
  if ( a1 <= 0xA5 )
  {
    if ( a1 != 165 )
    {
      if ( a1 > 0x9B )
      {
        if ( a1 == 156 )
        {
          if ( (_DWORD)v4 != 16 )
            goto LABEL_315;
LABEL_194:
          v6 = 16;
          goto LABEL_377;
        }
        if ( a1 != 157 )
        {
          if ( a1 == 158 || a1 == 160 )
            goto LABEL_395;
          if ( a1 == 162 )
            goto LABEL_194;
          if ( a1 != 163 )
            goto LABEL_380;
        }
LABEL_322:
        v6 = 16;
        goto LABEL_372;
      }
      if ( a1 == 155 )
      {
        if ( (_DWORD)v4 == 548 )
        {
          v6 = 548;
          memset(v82, 0, 0x224u);
          RtlCopyFromUser(v82, (void *)a3, 0x224u);
          v53 = v83;
          v54 = v82;
          v55 = 4;
          do
          {
            *v53 = *v54;
            v53[1] = v54[1];
            v53[2] = v54[2];
            v53[3] = v54[3];
            v53[4] = v54[4];
            v53[5] = v54[5];
            v53[6] = v54[6];
            v53[7] = v54[7];
            v53 += 8;
            v54 += 8;
            --v55;
          }
          while ( v55 );
          *v53 = *v54;
          v53[1] = v54[1];
          *((_DWORD *)v53 + 8) = *((_DWORD *)v54 + 8);
          v56 = v77;
          v57 = v77;
          v58 = v83;
          do
          {
            *v57 = *v58;
            v57[1] = v58[1];
            v57[2] = v58[2];
            v57[3] = v58[3];
            v57[4] = v58[4];
            v57[5] = v58[5];
            v57[6] = v58[6];
            v57[7] = v58[7];
            v57 += 8;
            v58 += 8;
            --v26;
          }
          while ( v26 );
          *v57 = *v58;
          v57[1] = v58[1];
          *((_DWORD *)v57 + 8) = *((_DWORD *)v58 + 8);
          a3 = (unsigned __int64)v56;
          if ( v56[6] <= 0x104u )
            goto LABEL_398;
        }
        goto LABEL_315;
      }
      if ( a1 == 149 )
      {
        v6 = 40;
        if ( (_DWORD)v4 != 40 )
          goto LABEL_315;
        goto LABEL_372;
      }
      if ( a1 != 150 )
      {
        if ( a1 != 151 )
        {
          if ( a1 == 152 )
          {
            if ( (_DWORD)v4 != 128 )
              goto LABEL_315;
            v6 = 128;
            goto LABEL_377;
          }
          if ( a1 != 153 )
          {
            if ( (_DWORD)v4 == 548 )
            {
              v6 = 548;
              v48 = PsGetCurrentProcessWow64Process();
              ProbeForWrite((volatile void *)a3, 0x224u, v48 != 0 ? 1 : 4);
              v49 = (void *)a3;
              v50 = (_OWORD *)a3;
              v51 = v77;
              v52 = v77;
              do
              {
                *v52 = *v50;
                v52[1] = v50[1];
                v52[2] = v50[2];
                v52[3] = v50[3];
                v52[4] = v50[4];
                v52[5] = v50[5];
                v52[6] = v50[6];
                v52[7] = v50[7];
                v52 += 8;
                v50 += 8;
                --v26;
              }
              while ( v26 );
              *v52 = *v50;
              v52[1] = v50[1];
              *((_DWORD *)v52 + 8) = *((_DWORD *)v50 + 8);
              a3 = (unsigned __int64)v51;
              v42 = 1;
              v75 = 1;
LABEL_400:
              v31 = xxxSystemParametersInfo(a1, v4);
              if ( v42 )
                memmove(v49, (const void *)a3, v6);
              goto LABEL_406;
            }
            goto LABEL_315;
          }
          if ( (_DWORD)v4 != 128 )
            goto LABEL_315;
          v6 = 128;
          goto LABEL_372;
        }
        if ( (_DWORD)v4 != 28 )
          goto LABEL_315;
LABEL_209:
        v6 = 28;
        goto LABEL_372;
      }
      if ( (_DWORD)v4 != 28 )
        goto LABEL_315;
      goto LABEL_210;
    }
LABEL_348:
    v6 = 12;
    if ( (_DWORD)v4 != 12 )
      goto LABEL_315;
    goto LABEL_377;
  }
  if ( a1 > 0xAF )
  {
    switch ( a1 )
    {
      case 0xB0u:
        v31 = 0;
        if ( (_DWORD)v4 )
          goto LABEL_397;
        break;
      case 0xB2u:
        if ( (_DWORD)v4 != 4 )
          goto LABEL_315;
        break;
      case 0xB3u:
        if ( (_DWORD)v4 != 4 )
          goto LABEL_315;
LABEL_371:
        v6 = 4;
        goto LABEL_372;
      case 0xB4u:
        v6 = 56;
        if ( (_DWORD)v4 != 56 )
          goto LABEL_315;
        goto LABEL_377;
      case 0xB5u:
        v6 = 56;
        if ( (_DWORD)v4 != 56 )
          goto LABEL_315;
        goto LABEL_372;
      default:
        goto LABEL_380;
    }
LABEL_376:
    v6 = 4;
    goto LABEL_377;
  }
  if ( a1 != 175 )
  {
    if ( a1 == 167 )
      goto LABEL_348;
    if ( a1 == 168 || a1 == 170 )
      goto LABEL_395;
    if ( a1 != 172 )
    {
      if ( a1 != 173 )
      {
        if ( a1 != 174 )
          goto LABEL_380;
        v59 = PsGetCurrentProcessWow64Process();
        ProbeForRead((volatile void *)a3, 4u, v59 != 0 ? 1 : 4);
        if ( *(_DWORD *)a3 )
        {
          switch ( *(_DWORD *)a3 )
          {
            case 1:
              v6 = 44;
              break;
            case 2:
              v6 = 48;
              break;
            case 0xFFFFFFFF:
              v6 = 64;
              break;
            default:
              goto LABEL_315;
          }
        }
        else
        {
          v6 = 24;
        }
        if ( (_DWORD)v4 != v6 )
          goto LABEL_315;
        v30 = v77;
        *v77 = *(_DWORD *)a3;
        goto LABEL_377;
      }
      if ( (_DWORD)v4 != 4 )
        goto LABEL_315;
      goto LABEL_371;
    }
    if ( (_DWORD)v4 != 4 )
      goto LABEL_315;
    goto LABEL_376;
  }
  v60 = PsGetCurrentProcessWow64Process();
  ProbeForRead((volatile void *)a3, 4u, v60 != 0 ? 1 : 4);
  if ( *(_DWORD *)a3 )
  {
    switch ( *(_DWORD *)a3 )
    {
      case 1:
        v6 = 44;
        break;
      case 2:
        v6 = 48;
        break;
      case 0xFFFFFFFF:
        v6 = 64;
        break;
      default:
        goto LABEL_315;
    }
  }
  else
  {
    v6 = 24;
  }
  if ( (_DWORD)v4 == v6 )
    goto LABEL_372;
LABEL_315:
  UserSetLastError(87);
  v31 = 0;
  Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(v70);
  Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>::~Win32RawOptionalLockedItemAlways<void,&void Win32FreePool(void *)>(BugCheckParameter2);
LABEL_407:
  UserSessionSwitchLeaveCritWithNonPaged();
  return v31;
}

```

## disassembly

```asm
0x14019a180  push    rbx
0x14019a182  push    rsi
0x14019a183  push    rdi
0x14019a184  push    r12
0x14019a186  push    r13
0x14019a188  push    r14
0x14019a18a  push    r15
0x14019a18c  sub     rsp, 540h
0x14019a193  mov     [rsp+578h+var_4F8], r9d
0x14019a19b  mov     r15d, edx
0x14019a19e  mov     esi, ecx
0x14019a1a0  mov     [rsp+578h+BugCheckParameter3], r8
0x14019a1a5  xorps   xmm0, xmm0
0x14019a1a8  movups  [rsp+578h+var_4B0], xmm0
0x14019a1b0  xor     r13d, r13d
0x14019a1b3  mov     edi, r13d
0x14019a1b6  mov     [rsp+578h+var_548], r13d
0x14019a1bb  mov     [rsp+578h+var_530], r13
0x14019a1c0  call    cs:__imp_W32GetUserSessionState
0x14019a1c7  nop     dword ptr [rax+rax+00h]
0x14019a1cc  mov     rbx, rax
0x14019a1cf  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x14019a1d6  xor     r8d, r8d
0x14019a1d9  xor     edx, edx
0x14019a1db  mov     rcx, rax
0x14019a1de  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x14019a1e3  mov     r14, rax
0x14019a1e6  mov     [rbx+10h], rax
0x14019a1ea  test    rax, rax
0x14019a1ed  jz      short loc_14019A213
0x14019a1ef  lea     rcx, [rbx+4C40h]
0x14019a1f6  call    DestroySharedUserCritDeferredUnlockList
0x14019a1fb  lea     rcx, [rbx+4C78h]
0x14019a202  call    DestroyDeferredUnlockObjectAssignmentList
0x14019a207  lea     rcx, [rbx+4C68h]
0x14019a20e  call    DestroyDeferredUnlockObjectAssignmentList
0x14019a213  lea     rcx, [rsp+578h+BugCheckParameter2]
0x14019a218  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14019a21d  lea     rcx, [rsp+578h+var_528]
0x14019a222  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14019a227  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x14019a22c  test    eax, eax
0x14019a22e  jz      short loc_14019A245
0x14019a230  mov     edx, 8; unsigned int
0x14019a235  mov     rcx, [r14+1C8h]; this
0x14019a23c  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x14019a241  mov     bl, al
0x14019a243  jmp     short loc_14019A27E
0x14019a245  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14019a24a  mov     rdx, rax
0x14019a24d  mov     ecx, r13d
0x14019a250  xor     eax, eax
0x14019a252  lock cmpxchg [rdx+208h], ecx
0x14019a25a  bt      eax, 1Dh
0x14019a25e  jnb     short loc_14019A279
0x14019a260  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14019a265  mov     rcx, [rax+1C8h]
0x14019a26c  mov     rax, [rcx+2F0h]
0x14019a273  mov     ecx, [rax+20h]
0x14019a276  and     ecx, 8
0x14019a279  test    ecx, ecx
0x14019a27b  setnz   bl
0x14019a27e  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x14019a283  test    eax, eax
0x14019a285  jz      short loc_14019A2B7
0x14019a287  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14019a28e  nop     dword ptr [rax+rax+00h]
0x14019a293  test    rax, rax
0x14019a296  jz      short loc_14019A2A4
0x14019a298  mov     rcx, [rax]
0x14019a29b  neg     rcx
0x14019a29e  sbb     rdx, rdx
0x14019a2a1  and     rax, rdx
0x14019a2a4  lea     rcx, [rax+360h]; this
0x14019a2ab  mov     edx, 2000h; struct tagUIPI_INFO *
0x14019a2b0  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x14019a2b5  jmp     short loc_14019A30A
0x14019a2b7  mov     dword ptr [rsp+578h+var_4C0], 2000h
0x14019a2c2  mov     dword ptr [rsp+578h+var_4C0+4], 0FFFFFFFFh
0x14019a2cd  xor     eax, eax
0x14019a2cf  mov     [rsp+578h+var_4B8], eax
0x14019a2d6  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14019a2dd  nop     dword ptr [rax+rax+00h]
0x14019a2e2  test    rax, rax
0x14019a2e5  jz      short loc_14019A2F3
0x14019a2e7  mov     rcx, [rax]
0x14019a2ea  neg     rcx
0x14019a2ed  sbb     rdx, rdx
0x14019a2f0  and     rax, rdx
0x14019a2f3  lea     rcx, [rax+360h]
0x14019a2fa  xor     r8d, r8d
0x14019a2fd  lea     rdx, [rsp+578h+var_4C0]
0x14019a305  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x14019a30a  test    bl, bl
0x14019a30c  jnz     short loc_14019A31C
0x14019a30e  test    al, al
0x14019a310  jz      short loc_14019A31C
0x14019a312  mov     ebx, 2
0x14019a317  jmp     loc_14019A6E8
0x14019a31c  cmp     esi, 6Dh ; 'm'
0x14019a31f  ja      loc_14019A4AC
0x14019a325  jz      loc_14019B9BF
0x14019a32b  cmp     esi, 37h ; '7'
0x14019a32e  ja      loc_14019A3E8
0x14019a334  jz      loc_14019B9BF
0x14019a33a  cmp     esi, 1Dh
0x14019a33d  ja      short loc_14019A383
0x14019a33f  jz      loc_14019B9BF
0x14019a345  cmp     esi, 13h
0x14019a348  ja      short loc_14019A35A
0x14019a34a  mov     eax, 0AA854h
0x14019a34f  bt      eax, esi
0x14019a352  jb      loc_14019B9BF
0x14019a358  jmp     short loc_14019A312
0x14019a35a  mov     eax, esi
0x14019a35c  sub     eax, 14h
0x14019a35f  jz      loc_14019B9BF
0x14019a365  sub     eax, 1
0x14019a368  jz      loc_14019B9BF
0x14019a36e  mov     ebx, 2
0x14019a373  sub     eax, ebx
0x14019a375  jz      loc_14019B9BF
0x14019a37b  sub     eax, 1
0x14019a37e  jmp     loc_14019A6D2
0x14019a383  cmp     esi, 2Ah ; '*'
0x14019a386  ja      short loc_14019A3C8
0x14019a388  jz      loc_14019B9BF
0x14019a38e  mov     eax, esi
0x14019a390  sub     eax, 1Eh
0x14019a393  jz      loc_14019B9BF
0x14019a399  mov     ebx, 2
0x14019a39e  sub     eax, ebx
0x14019a3a0  jz      loc_14019B9BF
0x14019a3a6  sub     eax, 1
0x14019a3a9  jz      loc_14019B9BF
0x14019a3af  sub     eax, 1
0x14019a3b2  jz      loc_14019B9BF
0x14019a3b8  sub     eax, ebx
0x14019a3ba  jz      loc_14019B9BF
0x14019a3c0  cmp     eax, 1
0x14019a3c3  jmp     loc_14019A6E2
0x14019a3c8  mov     eax, esi
0x14019a3ca  sub     eax, 2Ch ; ','
0x14019a3cd  jz      loc_14019B9BF
0x14019a3d3  mov     ebx, 2
0x14019a3d8  sub     eax, ebx
0x14019a3da  jz      loc_14019B9BF
0x14019a3e0  sub     eax, 1
0x14019a3e3  jmp     loc_14019A6CA
0x14019a3e8  cmp     esi, 55h ; 'U'
0x14019a3eb  ja      short loc_14019A44E
0x14019a3ed  jz      loc_14019B9BF
0x14019a3f3  cmp     esi, 49h ; 'I'
0x14019a3f6  ja      short loc_14019A411
0x14019a3f8  lea     eax, [rsi-39h]
0x14019a3fb  cmp     eax, 10h
0x14019a3fe  ja      loc_14019A312
0x14019a404  mov     ecx, 15515h
0x14019a409  bt      ecx, eax
0x14019a40c  jmp     loc_14019A352
0x14019a411  mov     eax, esi
0x14019a413  sub     eax, 4Bh ; 'K'
0x14019a416  jz      loc_14019B9BF
0x14019a41c  sub     eax, 1
0x14019a41f  jz      loc_14019B9BF
0x14019a425  sub     eax, 1
0x14019a428  jz      loc_14019B9BF
0x14019a42e  sub     eax, 1
0x14019a431  jz      loc_14019B9BF
0x14019a437  sub     eax, 3
0x14019a43a  jz      loc_14019B9BF
0x14019a440  cmp     eax, 1
0x14019a443  jz      loc_14019B9BF
0x14019a449  jmp     loc_14019A312
0x14019a44e  cmp     esi, 60h ; '`'
0x14019a451  ja      short loc_14019A48B
0x14019a453  jz      loc_14019B9BF
0x14019a459  mov     eax, esi
0x14019a45b  sub     eax, 56h ; 'V'
0x14019a45e  jz      loc_14019B9BF
0x14019a464  sub     eax, 1
0x14019a467  jz      loc_14019B9BF
0x14019a46d  sub     eax, 1
0x14019a470  jz      loc_14019B9BF
0x14019a476  mov     ebx, 2
0x14019a47b  sub     eax, ebx
0x14019a47d  jz      loc_14019B9BF
0x14019a483  sub     eax, 1
0x14019a486  jmp     loc_14019A6DA
0x14019a48b  lea     eax, [rsi-61h]
0x14019a48e  mov     r12d, 1
0x14019a494  cmp     eax, 0Ah
0x14019a497  ja      short loc_14019A4A2
0x14019a499  test    r12b, al
0x14019a49c  jz      loc_14019B9C5
0x14019a4a2  mov     ebx, 2
0x14019a4a7  jmp     loc_14019A6EE
0x14019a4ac  mov     eax, 1017h
0x14019a4b1  cmp     esi, eax
0x14019a4b3  ja      loc_14019A5C0
0x14019a4b9  jz      loc_14019B9BF
0x14019a4bf  mov     eax, 0ADh
0x14019a4c4  cmp     esi, eax
0x14019a4c6  ja      loc_14019A552
0x14019a4cc  jz      loc_14019B9BF
0x14019a4d2  mov     eax, 99h
0x14019a4d7  cmp     esi, eax
0x14019a4d9  ja      short loc_14019A51E
0x14019a4db  jz      loc_14019B9BF
0x14019a4e1  mov     eax, esi
0x14019a4e3  sub     eax, 6Fh ; 'o'
0x14019a4e6  jz      loc_14019B9BF
0x14019a4ec  mov     ebx, 2
0x14019a4f1  sub     eax, ebx
0x14019a4f3  jz      loc_14019B9BF
0x14019a4f9  lea     r14d, [rbx+2]
0x14019a4fd  sub     eax, r14d
0x14019a500  jz      loc_14019B9BF
0x14019a506  sub     eax, ebx
0x14019a508  jz      loc_14019B9BF
0x14019a50e  sub     eax, 1Ch
0x14019a511  jz      loc_14019B9BF
0x14019a517  sub     eax, ebx
0x14019a519  jmp     loc_14019A697
0x14019a51e  mov     eax, esi
0x14019a520  sub     eax, 9Bh
0x14019a525  jz      loc_14019B9BF
0x14019a52b  sub     eax, 6
0x14019a52e  jz      loc_14019B9BF
0x14019a534  mov     ebx, 2
0x14019a539  sub     eax, ebx
0x14019a53b  jz      loc_14019B9BF
0x14019a541  sub     eax, 3
0x14019a544  jz      loc_14019B9BF
0x14019a54a  sub     eax, 3
0x14019a54d  jmp     loc_14019A6DA
0x14019a552  mov     eax, 1007h
0x14019a557  cmp     esi, eax
0x14019a559  ja      short loc_14019A58D
0x14019a55b  jz      loc_14019B9BF
0x14019a561  mov     eax, esi
0x14019a563  sub     eax, 0AFh
0x14019a568  jz      loc_14019B9BF
0x14019a56e  mov     ebx, 2
0x14019a573  sub     eax, ebx
0x14019a575  jz      loc_14019B9BF
0x14019a57b  sub     eax, ebx
0x14019a57d  jz      loc_14019B9BF
0x14019a583  sub     eax, 0F4Eh
0x14019a588  jmp     loc_14019A6D2
0x14019a58d  mov     eax, esi
0x14019a58f  sub     eax, 1009h
0x14019a594  jz      loc_14019B9BF
0x14019a59a  mov     ebx, 2
0x14019a59f  sub     eax, ebx
0x14019a5a1  jz      loc_14019B9BF
0x14019a5a7  sub     eax, ebx
0x14019a5a9  jz      loc_14019B9BF
0x14019a5af  sub     eax, ebx
0x14019a5b1  jz      loc_14019B9BF
0x14019a5b7  lea     r14d, [rbx+2]
0x14019a5bb  jmp     loc_14019A694
0x14019a5c0  mov     eax, 2003h
0x14019a5c5  cmp     esi, eax
0x14019a5c7  ja      loc_14019A654
0x14019a5cd  jz      loc_14019B9BF
0x14019a5d3  mov     eax, 1049h
0x14019a5d8  cmp     esi, eax
0x14019a5da  ja      short loc_14019A618
0x14019a5dc  jz      loc_14019B9BF
0x14019a5e2  mov     eax, esi
0x14019a5e4  sub     eax, 1019h
0x14019a5e9  jz      loc_14019B9BF
0x14019a5ef  mov     r14d, 4
0x14019a5f5  sub     eax, r14d
0x14019a5f8  jz      loc_14019B9BF
0x14019a5fe  lea     ebx, [r14-2]
0x14019a602  sub     eax, ebx
0x14019a604  jz      loc_14019B9BF
0x14019a60a  sub     eax, 8
0x14019a60d  jz      loc_14019B9BF
0x14019a613  sub     eax, 1Ah
0x14019a616  jmp     short loc_14019A697
0x14019a618  mov     eax, esi
0x14019a61a  sub     eax, 104Bh
0x14019a61f  jz      loc_14019B9BF
0x14019a625  mov     ebx, 2
0x14019a62a  sub     eax, ebx
0x14019a62c  jz      loc_14019B9BF
0x14019a632  sub     eax, ebx
0x14019a634  jz      loc_14019B9BF
0x14019a63a  sub     eax, ebx
0x14019a63c  jz      loc_14019B9BF
0x14019a642  sub     eax, ebx
0x14019a644  jz      loc_14019B9BF
0x14019a64a  cmp     eax, 0FAEh
0x14019a64f  jmp     loc_14019A6E2
0x14019a654  mov     eax, 2019h
0x14019a659  cmp     esi, eax
0x14019a65b  ja      short loc_14019A6AD
  ... truncated ...
```
