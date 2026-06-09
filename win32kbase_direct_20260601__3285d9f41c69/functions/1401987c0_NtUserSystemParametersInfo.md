# NtUserSystemParametersInfo

- ea: `0x1401987c0`
- end: `0x14019a06c`
- name: `NtUserSystemParametersInfo`
- size: `6316`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033364`
- `0x140033d94`
- `0x14004c720`
- `0x1400687c0`
- `0x14006888c`
- `0x140076b80`
- `0x140078090`
- `0x140078120`
- `0x140081ed4`
- `0x14017287c`
- `0x1401984a0`
- `0x1401987c0`
- `0x14019a260`
- `0x1401a9f9c`
- `0x1401c6028`
- `0x1401c6dd8`
- `0x1401c7c38`
- `0x1401c7d40`
- `0x1402382c0`
- `0x140238800`
- `0x1402bb1a0`
- `0x1402bb358`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140199271`
- `ntoskrnl!ProbeForRead` at `0x140199a16`
- `ntoskrnl!ProbeForRead` at `0x140199b93`
- `ntoskrnl!ProbeForRead` at `0x140199d00`
- `ntoskrnl!ProbeForRead` at `0x140199271`
- `ntoskrnl!ProbeForRead` at `0x140199a16`
- `ntoskrnl!ProbeForRead` at `0x140199b93`
- `ntoskrnl!ProbeForRead` at `0x140199d00`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401992d2`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401992d2`
- `ntoskrnl!KeBugCheckEx` at `0x140198d84`
- `ntoskrnl!KeBugCheckEx` at `0x140198f51`
- `ntoskrnl!KeBugCheckEx` at `0x140198d84`
- `ntoskrnl!KeBugCheckEx` at `0x140198f51`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401988c7`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140198916`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a005`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401988c7`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140198916`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14019a005`
- `ntoskrnl!ExRaiseStatus` at `0x140198f0f`
- `ntoskrnl!ExRaiseStatus` at `0x140198f0f`
- `ntoskrnl!ProbeForWrite` at `0x1401991a2`
- `ntoskrnl!ProbeForWrite` at `0x1401991dc`
- `ntoskrnl!ProbeForWrite` at `0x1401993e0`
- `ntoskrnl!ProbeForWrite` at `0x1401995ed`
- `ntoskrnl!ProbeForWrite` at `0x140199db5`
- `ntoskrnl!ProbeForWrite` at `0x1401991a2`
- `ntoskrnl!ProbeForWrite` at `0x1401991dc`
- `ntoskrnl!ProbeForWrite` at `0x1401993e0`
- `ntoskrnl!ProbeForWrite` at `0x1401995ed`
- `ntoskrnl!ProbeForWrite` at `0x140199db5`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199182`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401995cc`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401999f7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199b74`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199d97`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199182`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401995cc`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401999f7`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199b74`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140199d97`
- `WIN32K!W32GetUserSessionState` at `0x140198800`
- `WIN32K!W32GetUserSessionState` at `0x140198800`

## pseudocode

```c
__int64 __fastcall NtUserSystemParametersInfo(__int64 a1, __int64 a2, ULONG_PTR a3, int a4)
{
  __int64 v4; // r15
  unsigned int v5; // esi
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
  ULONG_PTR v63; // rbx
  unsigned int ULongFromUser; // eax
  __int64 v65; // rax
  struct tagPROCESSINFO *v66; // rcx
  ULONG_PTR BugCheckParameter3; // [rsp+38h] [rbp-540h]
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
  v4 = (unsigned int)a2;
  v5 = a1;
  BugCheckParameter3 = a3;
  v80 = 0;
  v6 = 0;
  v69 = 0;
  UserSessionState = W32GetUserSessionState(a1, a2, a3);
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
  if ( v5 <= 0x6D )
  {
    if ( v5 == 109 )
      goto LABEL_402;
    if ( v5 > 0x37 )
    {
      if ( v5 <= 0x55 )
      {
        if ( v5 == 85 )
          goto LABEL_402;
        if ( v5 > 0x49 )
        {
          if ( v5 != 75 && v5 != 76 && v5 != 77 && v5 != 78 && v5 - 81 >= 2 )
            goto LABEL_127;
          goto LABEL_402;
        }
        if ( v5 - 57 <= 0x10 )
        {
          v15 = 87317;
          v18 = _bittest((const int *)&v15, v5 - 57);
LABEL_26:
          if ( !v18 )
            goto LABEL_127;
LABEL_402:
          v65 = PsGetCurrentProcessWin32Process();
          v66 = (struct tagPROCESSINFO *)v65;
          if ( v65 )
            v66 = (struct tagPROCESSINFO *)(((unsigned __int128)-(__int128)*(unsigned __int64 *)v65 >> 64) & v65);
          EtwTraceUIPISystemError(v66);
          v31 = 0;
          v32 = 5;
          goto LABEL_405;
        }
LABEL_127:
        v26 = 4;
        goto LABEL_128;
      }
      if ( v5 > 0x60 )
      {
        if ( v5 - 97 > 0xA || (((_BYTE)v5 - 97) & 1) != 0 )
          goto LABEL_127;
        goto LABEL_402;
      }
      if ( v5 == 96 || v5 == 86 || v5 == 87 || v5 == 88 || v5 == 90 )
        goto LABEL_402;
      v25 = v5 - 91;
      v24 = v5 == 91;
      goto LABEL_124;
    }
    if ( v5 == 55 )
      goto LABEL_402;
    if ( v5 <= 0x1D )
    {
      if ( v5 == 29 )
        goto LABEL_402;
      if ( v5 <= 0x13 )
      {
        v17 = 698452;
        v18 = _bittest(&v17, v5);
        goto LABEL_26;
      }
      if ( v5 == 20 || v5 == 21 || v5 == 23 )
        goto LABEL_402;
      v20 = v5 - 24;
      v19 = v5 == 24;
      goto LABEL_122;
    }
    if ( v5 <= 0x2A )
    {
      if ( v5 == 42 || v5 == 30 || v5 == 32 || v5 == 33 || v5 == 34 || v5 == 36 )
        goto LABEL_402;
      v21 = v5 == 37;
LABEL_126:
      if ( v21 )
        goto LABEL_402;
      goto LABEL_127;
    }
    if ( v5 == 44 || v5 == 46 )
      goto LABEL_402;
    v23 = v5 - 47;
    v22 = v5 == 47;
    goto LABEL_120;
  }
  if ( v5 <= 0x1017 )
  {
    if ( v5 == 4119 )
      goto LABEL_402;
    if ( v5 <= 0xAD )
    {
      if ( v5 == 173 )
        goto LABEL_402;
      if ( v5 > 0x99 )
      {
        if ( v5 == 155 || v5 == 161 || v5 == 163 || v5 == 166 )
          goto LABEL_402;
        v25 = v5 - 169;
        v24 = v5 == 169;
LABEL_124:
        if ( v24 )
          goto LABEL_402;
        v21 = v25 == 2;
        goto LABEL_126;
      }
      switch ( v5 )
      {
        case 0x99u:
          goto LABEL_402;
        case 0x6Fu:
          goto LABEL_402;
        case 0x71u:
          goto LABEL_402;
      }
      v26 = 4;
      if ( v5 == 117 || v5 == 119 || v5 == 147 )
        goto LABEL_402;
      v28 = v5 - 149;
      v27 = v5 == 149;
      goto LABEL_114;
    }
    if ( v5 <= 0x1007 )
    {
      if ( v5 == 4103 || v5 == 175 || v5 == 177 || v5 == 179 )
        goto LABEL_402;
      v20 = v5 - 4097;
      v19 = v5 == 4097;
LABEL_122:
      if ( v19 )
        goto LABEL_402;
      v25 = v20 - 2;
      v24 = v25 == 0;
      goto LABEL_124;
    }
    switch ( v5 )
    {
      case 0x1009u:
        goto LABEL_402;
      case 0x100Bu:
        goto LABEL_402;
      case 0x100Du:
        goto LABEL_402;
    }
    v29 = v5 - 4111;
    if ( v5 == 4111 )
      goto LABEL_402;
    v26 = 4;
LABEL_113:
    v28 = v29 - 4;
    v27 = v28 == 0;
    goto LABEL_114;
  }
  if ( v5 > 0x2003 )
  {
    if ( v5 > 0x2019 )
    {
      if ( v5 == 8219 || v5 == 8221 )
        goto LABEL_402;
      v23 = v5 - 8241;
      v22 = v5 == 8241;
LABEL_120:
      if ( v22 )
        goto LABEL_402;
      v20 = v23 - 2;
      v19 = v20 == 0;
      goto LABEL_122;
    }
    if ( v5 == 8217 )
      goto LABEL_402;
    if ( v5 == 8197 )
      goto LABEL_402;
    v26 = 4;
    if ( v5 == 8201 )
      goto LABEL_402;
    if ( v5 == 8207 )
      goto LABEL_402;
    v29 = v5 - 8209;
    if ( v5 == 8209 )
      goto LABEL_402;
    goto LABEL_113;
  }
  if ( v5 == 8195 )
    goto LABEL_402;
  if ( v5 > 0x1049 )
  {
    if ( v5 == 4171 || v5 == 4173 || v5 == 4175 || v5 == 4177 || v5 == 4179 )
      goto LABEL_402;
    v21 = v5 == 8193;
    goto LABEL_126;
  }
  if ( v5 == 4169 )
    goto LABEL_402;
  if ( v5 == 4121 )
    goto LABEL_402;
  v26 = 4;
  if ( v5 == 4125 || v5 == 4127 || v5 == 4135 )
    goto LABEL_402;
  v28 = v5 - 4161;
  v27 = v5 == 4161;
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
  if ( v5 > 0x1026 )
  {
    if ( v5 == 4135 )
      goto LABEL_398;
    if ( v5 == 8221 )
    {
      v31 = 0;
      if ( BugCheckParameter3 > 2 )
        goto LABEL_397;
      goto LABEL_398;
    }
    goto LABEL_380;
  }
  if ( v5 == 4134 )
    goto LABEL_395;
  if ( v5 <= 0x62 )
  {
    if ( v5 == 98 )
      goto LABEL_395;
    if ( v5 <= 0x32 )
    {
      if ( v5 == 50 )
      {
        v6 = 24;
        goto LABEL_377;
      }
      if ( v5 <= 0x19 )
      {
        if ( v5 == 25 )
          goto LABEL_395;
        if ( v5 > 0xE )
        {
          switch ( v5 )
          {
            case 0x10u:
            case 0x12u:
              goto LABEL_395;
            case 0x14u:
              if ( !BugCheckParameter3 )
                BugCheckParameter3 = -1;
              if ( BugCheckParameter3 == -2 || BugCheckParameter3 == -1 )
              {
                LODWORD(v4) = -1;
                v76 = -1;
                goto LABEL_398;
              }
              break;
            case 0x15u:
              if ( (_DWORD)v4 == -1 )
                goto LABEL_398;
              if ( !BugCheckParameter3 )
              {
                LODWORD(v4) = -1;
                v76 = -1;
                goto LABEL_398;
              }
              break;
            default:
              if ( v5 != 22 )
              {
                if ( v5 != 24 )
                  goto LABEL_380;
LABEL_158:
                if ( (BugCheckParameter3 & 0xFFFFFFFFFFFF0000uLL) == 0 )
                  goto LABEL_398;
              }
LABEL_395:
              v6 = 4;
              v63 = BugCheckParameter3;
              v69 = (volatile void *)BugCheckParameter3;
              BugCheckParameter3 = (ULONG_PTR)v30;
              ULongFromUser = RtlReadULongFromUser(v69);
              RtlWriteULongToUser(v63, ULongFromUser);
              goto LABEL_219;
          }
          v36 = DuplicateUnicodeStringFromUser<0>(BugCheckParameter3, v35, &v80);
          if ( v36 < 0 )
            ExRaiseStatus(v36);
          BugCheckParameter3 = *((_QWORD *)&v80 + 1);
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
        if ( v5 == 14 || v5 == 1 )
          goto LABEL_395;
        if ( v5 != 3 )
        {
          if ( v5 != 4 )
          {
            if ( v5 != 5 && v5 != 10 )
            {
              if ( v5 != 13 )
                goto LABEL_380;
              goto LABEL_158;
            }
            goto LABEL_395;
          }
          goto LABEL_149;
        }
        goto LABEL_151;
      }
      if ( v5 <= 0x2A )
      {
        switch ( v5 )
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
            v61 = (_DWORD *)BugCheckParameter3;
            v69 = (volatile void *)BugCheckParameter3;
            BugCheckParameter3 = (ULONG_PTR)v30;
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
        ProbeForRead((volatile void *)BugCheckParameter3, v6, 4u);
        memmove(v30, (const void *)BugCheckParameter3, v6);
        BugCheckParameter3 = (ULONG_PTR)v30;
        goto LABEL_398;
      }
      switch ( v5 )
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
      if ( v5 != 47 )
      {
        if ( v5 != 48 )
          goto LABEL_380;
        goto LABEL_194;
      }
      goto LABEL_322;
    }
    if ( v5 > 0x43 )
    {
      if ( v5 > 0x50 )
      {
        if ( v5 == 83 || v5 == 84 )
          goto LABEL_395;
        if ( v5 != 89 )
        {
          if ( v5 != 90 )
          {
            v40 = v5 - 94;
            if ( v5 == 94 )
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
        if ( v5 == 80 || v5 == 68 || v5 == 70 )
          goto LABEL_395;
        if ( v5 != 72 )
        {
          if ( v5 != 73 )
          {
            if ( v5 == 74 )
              goto LABEL_395;
            v45 = v5 == 79;
            goto LABEL_270;
          }
          goto LABEL_222;
        }
      }
LABEL_244:
      v6 = 8;
      goto LABEL_377;
    }
    if ( v5 != 67 )
    {
      if ( v5 <= 0x3A )
      {
        if ( v5 != 58 )
        {
          if ( v5 == 51 )
          {
            v6 = 24;
            goto LABEL_372;
          }
          if ( v5 != 52 )
          {
            if ( v5 != 53 )
            {
              if ( v5 != 54 )
              {
                v40 = v5 - 55;
                if ( v5 == 55 )
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
      if ( v5 == 59 )
        goto LABEL_222;
      if ( v5 != 60 )
      {
        if ( v5 != 61 )
        {
          switch ( v5 )
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
              ProbeForWrite((volatile void *)BugCheckParameter3, 0x10u, v41 != 0 ? 1 : 4);
              v69 = (volatile void *)BugCheckParameter3;
              *(_OWORD *)v30 = *(_OWORD *)BugCheckParameter3;
              BugCheckParameter3 = (ULONG_PTR)v30;
              ProbeForWrite(*((volatile void **)v30 + 1), 0x100u, 2u);
LABEL_219:
              v42 = 1;
              v75 = 1;
LABEL_399:
              v49 = (void *)v69;
              goto LABEL_400;
          }
LABEL_380:
          if ( v5 < 0xB6 )
            goto LABEL_398;
          if ( v5 - 4096 <= 0x55 || v5 - 0x2000 <= 0x37 )
          {
            v31 = 0;
            if ( (_DWORD)v4 && (*((_DWORD *)PtiCurrent() + 166) > 0x400u || v5 != 4159 || (_DWORD)v4 != 1) )
              goto LABEL_397;
            if ( (v5 & 1) != 0 )
            {
              if ( v5 != 8203 )
              {
                if ( v5 == 8211 )
                {
                  v77 = (_DWORD *)BugCheckParameter3;
                  if ( (BugCheckParameter3 & 0xFFFFFFFE) != 0 )
                    goto LABEL_397;
                }
                goto LABEL_398;
              }
              v78 = BugCheckParameter3;
              if ( (BugCheckParameter3 & 0xFFFFFFFC) != 0 )
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
    RtlCopyFromUser(&v80, (void *)BugCheckParameter3, 0x18u);
    v43 = v81;
    *(_OWORD *)v30 = v80;
    *((_QWORD *)v30 + 2) = v43;
    BugCheckParameter3 = (ULONG_PTR)v30;
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
  if ( v5 <= 0x94 )
  {
    if ( v5 == 148 )
    {
      v6 = 40;
      if ( (_DWORD)v4 != 40 )
        goto LABEL_315;
      goto LABEL_377;
    }
    if ( v5 > 0x7A )
    {
      if ( v5 > 0x88 )
      {
        if ( v5 == 138 || v5 == 140 || v5 == 142 || v5 == 144 )
          goto LABEL_395;
        if ( v5 == 146 )
        {
          if ( (_DWORD)v4 != 68 )
            goto LABEL_315;
          v6 = 68;
          goto LABEL_377;
        }
        if ( v5 != 147 )
          goto LABEL_380;
        if ( (_DWORD)v4 != 68 )
          goto LABEL_315;
        v6 = 68;
        goto LABEL_372;
      }
      if ( v5 == 136 || v5 == 124 || v5 == 126 || v5 == 128 || v5 == 130 )
        goto LABEL_395;
      v47 = v5 - 132;
      v46 = v5 == 132;
    }
    else
    {
      if ( v5 == 122 )
        goto LABEL_395;
      if ( v5 <= 0x70 )
      {
        if ( ((v5 - 100) & 0xFFFFFFF1) != 0 )
          goto LABEL_380;
        goto LABEL_395;
      }
      switch ( v5 )
      {
        case 'r':
          goto LABEL_395;
        case 's':
          v69 = (volatile void *)BugCheckParameter3;
          BugCheckParameter3 = (ULONG_PTR)v30;
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
      v47 = v5 - 118;
      v46 = v5 == 118;
    }
    if ( v46 )
      goto LABEL_395;
    v45 = v47 == 2;
    goto LABEL_270;
  }
  if ( v5 <= 0xA5 )
  {
    if ( v5 != 165 )
    {
      if ( v5 > 0x9B )
      {
        if ( v5 == 156 )
        {
          if ( (_DWORD)v4 != 16 )
            goto LABEL_315;
LABEL_194:
          v6 = 16;
          goto LABEL_377;
        }
        if ( v5 != 157 )
        {
          if ( v5 == 158 || v5 == 160 )
            goto LABEL_395;
          if ( v5 == 162 )
            goto LABEL_194;
          if ( v5 != 163 )
            goto LABEL_380;
        }
LABEL_322:
        v6 = 16;
        goto LABEL_372;
      }
      if ( v5 == 155 )
      {
        if ( (_DWORD)v4 == 548 )
        {
          v6 = 548;
          memset(v82, 0, 0x224u);
          RtlCopyFromUser(v82, (void *)BugCheckParameter3, 0x224u);
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
          BugCheckParameter3 = (ULONG_PTR)v56;
          if ( v56[6] <= 0x104u )
            goto LABEL_398;
        }
        goto LABEL_315;
      }
      if ( v5 == 149 )
      {
        v6 = 40;
        if ( (_DWORD)v4 != 40 )
          goto LABEL_315;
        goto LABEL_372;
      }
      if ( v5 != 150 )
      {
        if ( v5 != 151 )
        {
          if ( v5 == 152 )
          {
            if ( (_DWORD)v4 != 128 )
              goto LABEL_315;
            v6 = 128;
            goto LABEL_377;
          }
          if ( v5 != 153 )
          {
            if ( (_DWORD)v4 == 548 )
            {
              v6 = 548;
              v48 = PsGetCurrentProcessWow64Process();
              ProbeForWrite((volatile void *)BugCheckParameter3, 0x224u, v48 != 0 ? 1 : 4);
              v49 = (void *)BugCheckParameter3;
              v50 = (_OWORD *)BugCheckParameter3;
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
              BugCheckParameter3 = (ULONG_PTR)v51;
              v42 = 1;
              v75 = 1;
LABEL_400:
              v31 = xxxSystemParametersInfo(v5, v4);
              if ( v42 )
                memmove(v49, (const void *)BugCheckParameter3, v6);
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
  if ( v5 > 0xAF )
  {
    switch ( v5 )
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
  if ( v5 != 175 )
  {
    if ( v5 == 167 )
      goto LABEL_348;
    if ( v5 == 168 || v5 == 170 )
      goto LABEL_395;
    if ( v5 != 172 )
    {
      if ( v5 != 173 )
      {
        if ( v5 != 174 )
          goto LABEL_380;
        v59 = PsGetCurrentProcessWow64Process();
        ProbeForRead((volatile void *)BugCheckParameter3, 4u, v59 != 0 ? 1 : 4);
        if ( *(_DWORD *)BugCheckParameter3 )
        {
          switch ( *(_DWORD *)BugCheckParameter3 )
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
        *v77 = *(_DWORD *)BugCheckParameter3;
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
  ProbeForRead((volatile void *)BugCheckParameter3, 4u, v60 != 0 ? 1 : 4);
  if ( *(_DWORD *)BugCheckParameter3 )
  {
    switch ( *(_DWORD *)BugCheckParameter3 )
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
0x1401987c0  push    rbx
0x1401987c2  push    rsi
0x1401987c3  push    rdi
0x1401987c4  push    r12
0x1401987c6  push    r13
0x1401987c8  push    r14
0x1401987ca  push    r15
0x1401987cc  sub     rsp, 540h
0x1401987d3  mov     [rsp+578h+var_4F8], r9d
0x1401987db  mov     r15d, edx
0x1401987de  mov     esi, ecx
0x1401987e0  mov     [rsp+578h+BugCheckParameter3], r8
0x1401987e5  xorps   xmm0, xmm0
0x1401987e8  movups  [rsp+578h+var_4B0], xmm0
0x1401987f0  xor     r13d, r13d
0x1401987f3  mov     edi, r13d
0x1401987f6  mov     [rsp+578h+var_548], r13d
0x1401987fb  mov     [rsp+578h+var_530], r13
0x140198800  call    cs:__imp_W32GetUserSessionState
0x140198807  nop     dword ptr [rax+rax+00h]
0x14019880c  mov     rbx, rax
0x14019880f  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x140198816  xor     r8d, r8d
0x140198819  xor     edx, edx
0x14019881b  mov     rcx, rax
0x14019881e  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x140198823  mov     r14, rax
0x140198826  mov     [rbx+10h], rax
0x14019882a  test    rax, rax
0x14019882d  jz      short loc_140198853
0x14019882f  lea     rcx, [rbx+4C40h]
0x140198836  call    DestroySharedUserCritDeferredUnlockList
0x14019883b  lea     rcx, [rbx+4C78h]
0x140198842  call    DestroyDeferredUnlockObjectAssignmentList
0x140198847  lea     rcx, [rbx+4C68h]
0x14019884e  call    DestroyDeferredUnlockObjectAssignmentList
0x140198853  lea     rcx, [rsp+578h+BugCheckParameter2]
0x140198858  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x14019885d  lea     rcx, [rsp+578h+var_528]
0x140198862  call    ??0?$Win32RawLockedNtObject@UtagDESKTOP@@@@QEAA@XZ; Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(void)
0x140198867  call    Feature_UserJobImprovement__private_IsEnabledDeviceUsageNoInline
0x14019886c  test    eax, eax
0x14019886e  jz      short loc_140198885
0x140198870  mov     edx, 8; unsigned int
0x140198875  mov     rcx, [r14+1C8h]; this
0x14019887c  call    ?HasUILimit@tagPROCESSINFO@@QEBA_NK@Z; tagPROCESSINFO::HasUILimit(ulong)
0x140198881  mov     bl, al
0x140198883  jmp     short loc_1401988BE
0x140198885  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14019888a  mov     rdx, rax
0x14019888d  mov     ecx, r13d
0x140198890  xor     eax, eax
0x140198892  lock cmpxchg [rdx+208h], ecx
0x14019889a  bt      eax, 1Dh
0x14019889e  jnb     short loc_1401988B9
0x1401988a0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401988a5  mov     rcx, [rax+1C8h]
0x1401988ac  mov     rax, [rcx+2F0h]
0x1401988b3  mov     ecx, [rax+20h]
0x1401988b6  and     ecx, 8
0x1401988b9  test    ecx, ecx
0x1401988bb  setnz   bl
0x1401988be  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1401988c3  test    eax, eax
0x1401988c5  jz      short loc_1401988F7
0x1401988c7  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1401988ce  nop     dword ptr [rax+rax+00h]
0x1401988d3  test    rax, rax
0x1401988d6  jz      short loc_1401988E4
0x1401988d8  mov     rcx, [rax]
0x1401988db  neg     rcx
0x1401988de  sbb     rdx, rdx
0x1401988e1  and     rax, rdx
0x1401988e4  lea     rcx, [rax+360h]; this
0x1401988eb  mov     edx, 2000h; struct tagUIPI_INFO *
0x1401988f0  call    ?HasMinimumIntegrityLevel@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@K@Z; UIPrivilegeIsolation::HasMinimumIntegrityLevel(tagUIPI_INFO const &,ulong)
0x1401988f5  jmp     short loc_14019894A
0x1401988f7  mov     dword ptr [rsp+578h+var_4C0], 2000h
0x140198902  mov     dword ptr [rsp+578h+var_4C0+4], 0FFFFFFFFh
0x14019890d  xor     eax, eax
0x14019890f  mov     [rsp+578h+var_4B8], eax
0x140198916  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14019891d  nop     dword ptr [rax+rax+00h]
0x140198922  test    rax, rax
0x140198925  jz      short loc_140198933
0x140198927  mov     rcx, [rax]
0x14019892a  neg     rcx
0x14019892d  sbb     rdx, rdx
0x140198930  and     rax, rdx
0x140198933  lea     rcx, [rax+360h]
0x14019893a  xor     r8d, r8d
0x14019893d  lea     rdx, [rsp+578h+var_4C0]
0x140198945  call    ?CheckAccessEx@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0W4AppContainerMatch@1@@Z; UIPrivilegeIsolation::CheckAccessEx(tagUIPI_INFO const &,tagUIPI_INFO const &,UIPrivilegeIsolation::AppContainerMatch)
0x14019894a  test    bl, bl
0x14019894c  jnz     short loc_14019895C
0x14019894e  test    al, al
0x140198950  jz      short loc_14019895C
0x140198952  mov     ebx, 2
0x140198957  jmp     loc_140198D28
0x14019895c  cmp     esi, 6Dh ; 'm'
0x14019895f  ja      loc_140198AEC
0x140198965  jz      loc_140199FFF
0x14019896b  cmp     esi, 37h ; '7'
0x14019896e  ja      loc_140198A28
0x140198974  jz      loc_140199FFF
0x14019897a  cmp     esi, 1Dh
0x14019897d  ja      short loc_1401989C3
0x14019897f  jz      loc_140199FFF
0x140198985  cmp     esi, 13h
0x140198988  ja      short loc_14019899A
0x14019898a  mov     eax, 0AA854h
0x14019898f  bt      eax, esi
0x140198992  jb      loc_140199FFF
0x140198998  jmp     short loc_140198952
0x14019899a  mov     eax, esi
0x14019899c  sub     eax, 14h
0x14019899f  jz      loc_140199FFF
0x1401989a5  sub     eax, 1
0x1401989a8  jz      loc_140199FFF
0x1401989ae  mov     ebx, 2
0x1401989b3  sub     eax, ebx
0x1401989b5  jz      loc_140199FFF
0x1401989bb  sub     eax, 1
0x1401989be  jmp     loc_140198D12
0x1401989c3  cmp     esi, 2Ah ; '*'
0x1401989c6  ja      short loc_140198A08
0x1401989c8  jz      loc_140199FFF
0x1401989ce  mov     eax, esi
0x1401989d0  sub     eax, 1Eh
0x1401989d3  jz      loc_140199FFF
0x1401989d9  mov     ebx, 2
0x1401989de  sub     eax, ebx
0x1401989e0  jz      loc_140199FFF
0x1401989e6  sub     eax, 1
0x1401989e9  jz      loc_140199FFF
0x1401989ef  sub     eax, 1
0x1401989f2  jz      loc_140199FFF
0x1401989f8  sub     eax, ebx
0x1401989fa  jz      loc_140199FFF
0x140198a00  cmp     eax, 1
0x140198a03  jmp     loc_140198D22
0x140198a08  mov     eax, esi
0x140198a0a  sub     eax, 2Ch ; ','
0x140198a0d  jz      loc_140199FFF
0x140198a13  mov     ebx, 2
0x140198a18  sub     eax, ebx
0x140198a1a  jz      loc_140199FFF
0x140198a20  sub     eax, 1
0x140198a23  jmp     loc_140198D0A
0x140198a28  cmp     esi, 55h ; 'U'
0x140198a2b  ja      short loc_140198A8E
0x140198a2d  jz      loc_140199FFF
0x140198a33  cmp     esi, 49h ; 'I'
0x140198a36  ja      short loc_140198A51
0x140198a38  lea     eax, [rsi-39h]
0x140198a3b  cmp     eax, 10h
0x140198a3e  ja      loc_140198952
0x140198a44  mov     ecx, 15515h
0x140198a49  bt      ecx, eax
0x140198a4c  jmp     loc_140198992
0x140198a51  mov     eax, esi
0x140198a53  sub     eax, 4Bh ; 'K'
0x140198a56  jz      loc_140199FFF
0x140198a5c  sub     eax, 1
0x140198a5f  jz      loc_140199FFF
0x140198a65  sub     eax, 1
0x140198a68  jz      loc_140199FFF
0x140198a6e  sub     eax, 1
0x140198a71  jz      loc_140199FFF
0x140198a77  sub     eax, 3
0x140198a7a  jz      loc_140199FFF
0x140198a80  cmp     eax, 1
0x140198a83  jz      loc_140199FFF
0x140198a89  jmp     loc_140198952
0x140198a8e  cmp     esi, 60h ; '`'
0x140198a91  ja      short loc_140198ACB
0x140198a93  jz      loc_140199FFF
0x140198a99  mov     eax, esi
0x140198a9b  sub     eax, 56h ; 'V'
0x140198a9e  jz      loc_140199FFF
0x140198aa4  sub     eax, 1
0x140198aa7  jz      loc_140199FFF
0x140198aad  sub     eax, 1
0x140198ab0  jz      loc_140199FFF
0x140198ab6  mov     ebx, 2
0x140198abb  sub     eax, ebx
0x140198abd  jz      loc_140199FFF
0x140198ac3  sub     eax, 1
0x140198ac6  jmp     loc_140198D1A
0x140198acb  lea     eax, [rsi-61h]
0x140198ace  mov     r12d, 1
0x140198ad4  cmp     eax, 0Ah
0x140198ad7  ja      short loc_140198AE2
0x140198ad9  test    r12b, al
0x140198adc  jz      loc_14019A005
0x140198ae2  mov     ebx, 2
0x140198ae7  jmp     loc_140198D2E
0x140198aec  mov     eax, 1017h
0x140198af1  cmp     esi, eax
0x140198af3  ja      loc_140198C00
0x140198af9  jz      loc_140199FFF
0x140198aff  mov     eax, 0ADh
0x140198b04  cmp     esi, eax
0x140198b06  ja      loc_140198B92
0x140198b0c  jz      loc_140199FFF
0x140198b12  mov     eax, 99h
0x140198b17  cmp     esi, eax
0x140198b19  ja      short loc_140198B5E
0x140198b1b  jz      loc_140199FFF
0x140198b21  mov     eax, esi
0x140198b23  sub     eax, 6Fh ; 'o'
0x140198b26  jz      loc_140199FFF
0x140198b2c  mov     ebx, 2
0x140198b31  sub     eax, ebx
0x140198b33  jz      loc_140199FFF
0x140198b39  lea     r14d, [rbx+2]
0x140198b3d  sub     eax, r14d
0x140198b40  jz      loc_140199FFF
0x140198b46  sub     eax, ebx
0x140198b48  jz      loc_140199FFF
0x140198b4e  sub     eax, 1Ch
0x140198b51  jz      loc_140199FFF
0x140198b57  sub     eax, ebx
0x140198b59  jmp     loc_140198CD7
0x140198b5e  mov     eax, esi
0x140198b60  sub     eax, 9Bh
0x140198b65  jz      loc_140199FFF
0x140198b6b  sub     eax, 6
0x140198b6e  jz      loc_140199FFF
0x140198b74  mov     ebx, 2
0x140198b79  sub     eax, ebx
0x140198b7b  jz      loc_140199FFF
0x140198b81  sub     eax, 3
0x140198b84  jz      loc_140199FFF
0x140198b8a  sub     eax, 3
0x140198b8d  jmp     loc_140198D1A
0x140198b92  mov     eax, 1007h
0x140198b97  cmp     esi, eax
0x140198b99  ja      short loc_140198BCD
0x140198b9b  jz      loc_140199FFF
0x140198ba1  mov     eax, esi
0x140198ba3  sub     eax, 0AFh
0x140198ba8  jz      loc_140199FFF
0x140198bae  mov     ebx, 2
0x140198bb3  sub     eax, ebx
0x140198bb5  jz      loc_140199FFF
0x140198bbb  sub     eax, ebx
0x140198bbd  jz      loc_140199FFF
0x140198bc3  sub     eax, 0F4Eh
0x140198bc8  jmp     loc_140198D12
0x140198bcd  mov     eax, esi
0x140198bcf  sub     eax, 1009h
0x140198bd4  jz      loc_140199FFF
0x140198bda  mov     ebx, 2
0x140198bdf  sub     eax, ebx
0x140198be1  jz      loc_140199FFF
0x140198be7  sub     eax, ebx
0x140198be9  jz      loc_140199FFF
0x140198bef  sub     eax, ebx
0x140198bf1  jz      loc_140199FFF
0x140198bf7  lea     r14d, [rbx+2]
0x140198bfb  jmp     loc_140198CD4
0x140198c00  mov     eax, 2003h
0x140198c05  cmp     esi, eax
0x140198c07  ja      loc_140198C94
0x140198c0d  jz      loc_140199FFF
0x140198c13  mov     eax, 1049h
0x140198c18  cmp     esi, eax
0x140198c1a  ja      short loc_140198C58
0x140198c1c  jz      loc_140199FFF
0x140198c22  mov     eax, esi
0x140198c24  sub     eax, 1019h
0x140198c29  jz      loc_140199FFF
0x140198c2f  mov     r14d, 4
0x140198c35  sub     eax, r14d
0x140198c38  jz      loc_140199FFF
0x140198c3e  lea     ebx, [r14-2]
0x140198c42  sub     eax, ebx
0x140198c44  jz      loc_140199FFF
0x140198c4a  sub     eax, 8
0x140198c4d  jz      loc_140199FFF
0x140198c53  sub     eax, 1Ah
0x140198c56  jmp     short loc_140198CD7
0x140198c58  mov     eax, esi
0x140198c5a  sub     eax, 104Bh
0x140198c5f  jz      loc_140199FFF
0x140198c65  mov     ebx, 2
0x140198c6a  sub     eax, ebx
0x140198c6c  jz      loc_140199FFF
0x140198c72  sub     eax, ebx
0x140198c74  jz      loc_140199FFF
0x140198c7a  sub     eax, ebx
0x140198c7c  jz      loc_140199FFF
0x140198c82  sub     eax, ebx
0x140198c84  jz      loc_140199FFF
0x140198c8a  cmp     eax, 0FAEh
0x140198c8f  jmp     loc_140198D22
0x140198c94  mov     eax, 2019h
0x140198c99  cmp     esi, eax
0x140198c9b  ja      short loc_140198CED
  ... truncated ...
```
