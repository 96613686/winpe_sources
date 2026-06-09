# xxxProcessHidInput

- ea: `0x1400bf810`
- end: `0x1400c006b`
- name: `xxxProcessHidInput`
- size: `2139`
- prototype: `__int64 __fastcall(struct DEVICEINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400c0080`

## callees

- `0x140007b44`
- `0x140008690`
- `0x1400331d4`
- `0x140038a84`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400bf810`
- `0x1400eb064`
- `0x140143a88`
- `0x1401b0018`
- `0x1401d84d8`
- `0x1402587d8`
- `0x1403420d0`

## import_xrefs

- `win32kbase!?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z` at `0x1400c0028`
- `win32kbase!?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z` at `0x1400c0028`
- `win32kbase!RIMUnlockShared` at `0x1400bfe4e`
- `win32kbase!RIMUnlockShared` at `0x1400bfec8`
- `win32kbase!RIMUnlockShared` at `0x1400bfe4e`
- `win32kbase!RIMUnlockShared` at `0x1400bfec8`
- `win32kbase!RIMLockShared` at `0x1400bfe1f`
- `win32kbase!RIMLockShared` at `0x1400bfe1f`
- `win32kbase!IsInputThread` at `0x1400bfaf5`
- `win32kbase!IsInputThread` at `0x1400bfe6f`
- `win32kbase!IsInputThread` at `0x1400bfaf5`
- `win32kbase!IsInputThread` at `0x1400bfe6f`
- `win32kbase!UserSessionSwitchLeaveCritWithNonPaged` at `0x1400c003e`
- `win32kbase!UserSessionSwitchLeaveCritWithNonPaged` at `0x1400c003e`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400bfdfb`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400bfdfb`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfb2f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfd8a`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfeb3`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfb2f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfd8a`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400bfeb3`
- `WIN32K!W32GetUserSessionState` at `0x1400bf892`
- `WIN32K!W32GetUserSessionState` at `0x1400bf95c`
- `WIN32K!W32GetUserSessionState` at `0x1400bf9b5`
- `WIN32K!W32GetUserSessionState` at `0x1400bfa1a`
- `WIN32K!W32GetUserSessionState` at `0x1400bfa68`
- `WIN32K!W32GetUserSessionState` at `0x1400bfaa2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfbc4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfbf2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfc4a`
- `WIN32K!W32GetUserSessionState` at `0x1400bfc5d`
- `WIN32K!W32GetUserSessionState` at `0x1400bfcd8`
- `WIN32K!W32GetUserSessionState` at `0x1400bfd45`
- `WIN32K!W32GetUserSessionState` at `0x1400bfd5e`
- `WIN32K!W32GetUserSessionState` at `0x1400bfdaa`
- `WIN32K!W32GetUserSessionState` at `0x1400bfdcb`
- `WIN32K!W32GetUserSessionState` at `0x1400bfe0c`
- `WIN32K!W32GetUserSessionState` at `0x1400bff2f`
- `WIN32K!W32GetUserSessionState` at `0x1400bffb3`
- `WIN32K!W32GetUserSessionState` at `0x1400bffe2`
- `WIN32K!W32GetUserSessionState` at `0x1400bf892`
- `WIN32K!W32GetUserSessionState` at `0x1400bf95c`
- `WIN32K!W32GetUserSessionState` at `0x1400bf9b5`
- `WIN32K!W32GetUserSessionState` at `0x1400bfa1a`
- `WIN32K!W32GetUserSessionState` at `0x1400bfa68`
- `WIN32K!W32GetUserSessionState` at `0x1400bfaa2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfbc4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfbf2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfc4a`
- `WIN32K!W32GetUserSessionState` at `0x1400bfc5d`
- `WIN32K!W32GetUserSessionState` at `0x1400bfcd8`
- `WIN32K!W32GetUserSessionState` at `0x1400bfd45`
- `WIN32K!W32GetUserSessionState` at `0x1400bfd5e`
- `WIN32K!W32GetUserSessionState` at `0x1400bfdaa`
- `WIN32K!W32GetUserSessionState` at `0x1400bfdcb`
- `WIN32K!W32GetUserSessionState` at `0x1400bfe0c`
- `WIN32K!W32GetUserSessionState` at `0x1400bff2f`
- `WIN32K!W32GetUserSessionState` at `0x1400bffb3`
- `WIN32K!W32GetUserSessionState` at `0x1400bffe2`

## pseudocode

```c
__int64 __fastcall xxxProcessHidInput(struct DEVICEINFO *a1, void *a2, __int64 a3)
{
  unsigned int v3; // r15d
  __int64 v5; // r13
  char v6; // di
  char v7; // bl
  __int64 UserSessionState; // rax
  int v9; // r8d
  int v10; // edx
  __int64 result; // rax
  int v12; // r14d
  int v13; // r12d
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  struct MOVESIZEDATA *v17; // rcx
  char v18; // si
  char v19; // di
  __int16 v20; // bx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // edx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  char v28; // si
  struct MOVESIZEDATA *v29; // rcx
  char v30; // di
  char v31; // bl
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  __int64 v35; // rax
  __int64 v36; // rcx
  struct tagPROCESS_HID_REQUEST *v37; // rbx
  __int64 v38; // rax
  struct tagWND *v39; // rbx
  __int64 v40; // rdi
  const struct tagUIPI_INFO *v41; // r8
  UIPrivilegeIsolation *v42; // rcx
  char v43; // r15
  __int64 v44; // rax
  __int64 v45; // rsi
  __int64 v46; // rax
  __int16 v47; // bx
  __int16 v48; // di
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // rax
  int v54; // r8d
  int v55; // edx
  struct tagPROCESS_HID_TABLE *v56; // r15
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  struct tagPROCESS_HID_REQUEST *v66; // rax
  struct tagWND *v67; // rdi
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rdx
  bool v72; // zf
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rax
  const struct tagUIPI_INFO *v78; // r8
  __int64 v79; // rcx
  __int64 v80; // xmm6_8
  int v81; // ebx
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rbx
  __int64 v88; // rcx
  __int64 v89; // rsi
  const struct tagUIPI_INFO *v90; // r8
  UIPrivilegeIsolation *v91; // rcx
  bool v92; // al
  char v93; // r14
  __int64 v94; // rbx
  __int64 v95; // rax
  int v96; // r8d
  int v97; // edx
  __int64 v98; // rax
  int v99; // [rsp+20h] [rbp-A8h]
  int v100; // [rsp+60h] [rbp-68h]
  __int64 v101; // [rsp+70h] [rbp-58h] BYREF
  int v102; // [rsp+78h] [rbp-50h]
  unsigned int Size; // [rsp+E0h] [rbp+18h]
  char v105; // [rsp+E8h] [rbp+20h] BYREF

  Size = a3;
  v3 = a3;
  v5 = 0;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x13u)
    || (v6 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
  {
    v6 = 0;
  }
  if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
    || (v7 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
  {
    v7 = 0;
  }
  if ( v6 || v7 )
  {
    UserSessionState = W32GetUserSessionState(a1, a2, a3, WPP_GLOBAL_Control);
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v10,
      v9,
      *(_QWORD *)(UserSessionState + 69152),
      5,
      20,
      15,
      (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
      (char)a1);
  }
  result = IsDeviceInputAllowed(a1);
  if ( (_DWORD)result )
  {
    v12 = 1;
    v100 = 1;
    v13 = 0;
    ReEnterLeaveCrit::ReEnterLeaveCrit((ReEnterLeaveCrit *)&v105);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x13u)
      || (v18 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v18 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || (v19 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v19 = 0;
    }
    if ( v18 || v19 )
    {
      v20 = *(_WORD *)(*((_QWORD *)a1 + 55) + 44LL);
      v21 = W32GetUserSessionState(WPP_GLOBAL_Control, v14, v15, v16);
      LOBYTE(v22) = v19;
      LOBYTE(v23) = v18;
      WPP_RECORDER_AND_TRACE_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v23,
        v22,
        *(_QWORD *)(v21 + 69152),
        5,
        20,
        16,
        (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
        v20,
        v3);
    }
    v28 = 0;
    if ( !*(_QWORD *)(W32GetUserSessionState(v17, v14, v15, v16) + 18968) )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || (v30 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
      {
        v30 = 0;
      }
      if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
        || (v31 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
      {
        v31 = 0;
      }
      if ( v30 || v31 )
      {
        v32 = W32GetUserSessionState(WPP_GLOBAL_Control, v24, v26, v27);
        LOBYTE(v33) = v31;
        LOBYTE(v34) = v30;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v34,
          v33,
          *(_QWORD *)(v32 + 69152),
          5,
          20,
          17,
          (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids);
      }
      goto LABEL_57;
    }
    v35 = W32GetUserSessionState(v25, v24, v26, v27);
    v5 = *(_QWORD *)(PtiKbdFromQ(*(_QWORD *)(v35 + 18968)) + 456);
    v37 = HidIsRequestedByThisProcess(a1, *(struct tagPROCESS_HID_TABLE **)(v5 + 824));
    if ( !v37 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || (v43 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
      {
        v43 = 0;
      }
      if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
        || !*((_WORD *)WPP_GLOBAL_Control + 36) )
      {
        LOBYTE(v12) = 0;
      }
      if ( v43 || (_BYTE)v12 )
      {
        v44 = W32GetUserSessionState(WPP_GLOBAL_Control, v24, v26, v27);
        v45 = *(_QWORD *)(PtiKbdFromQ(*(_QWORD *)(v44 + 18968)) + 456);
        v46 = *((_QWORD *)a1 + 55);
        v47 = *(_WORD *)(v46 + 40);
        v48 = *(_WORD *)(v46 + 42);
        v53 = W32GetUserSessionState(v50, v49, v51, v52);
        LOBYTE(v54) = v12;
        LOBYTE(v55) = v43;
        WPP_RECORDER_AND_TRACE_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v55,
          v54,
          *(_QWORD *)(v53 + 69152),
          v99,
          20,
          18,
          (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
          v48,
          v47,
          v45);
        v28 = 0;
      }
      v12 = 1;
      goto LABEL_57;
    }
    v38 = W32GetUserSessionState(v36, v24, v26, v27);
    v39 = (struct tagWND *)*((_QWORD *)v37 + 4);
    if ( v39 )
    {
      if ( *(char *)(*((_QWORD *)v39 + 5) + 20LL) < 0 )
      {
LABEL_57:
        v56 = *(struct tagPROCESS_HID_TABLE **)(W32GetUserSessionState(v29, v24, v26, v27) + 216);
        v61 = W32GetUserSessionState(v58, v57, v59, v60);
        while ( 1 )
        {
          result = v61 + 216;
          if ( v56 == (struct tagPROCESS_HID_TABLE *)result )
          {
LABEL_104:
            if ( v13 )
            {
              result = *((unsigned int *)a1 + 46);
              if ( (result & 0x40) == 0 )
              {
                v98 = W32GetUserSessionState(v63, v62, v64, v65);
                result = CInputGlobals::UpdateInputGlobals(
                           *(_QWORD *)(v98 + 3008),
                           (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                          * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64,
                           4);
              }
            }
            if ( !v105 )
              return UserSessionSwitchLeaveCritWithNonPaged();
            return result;
          }
          if ( *((int *)v56 + 20) > 0 )
          {
            v66 = HidIsRequestedByThisProcess(a1, v56);
            if ( v66 )
            {
              v63 = *((unsigned int *)v66 + 5);
              if ( (v63 & 1) != 0 && ((v63 & 2) == 0 || v12) )
              {
                v62 = *((_QWORD *)v66 + 5);
                if ( v62 )
                {
                  (*((void (__fastcall **)(struct DEVICEINFO *))v66 + 5))(a1);
                  goto LABEL_102;
                }
                v67 = (struct tagWND *)*((_QWORD *)v66 + 4);
                if ( *(_QWORD *)(*((_QWORD *)v67 + 2) + 456LL) != v5 )
                {
                  v63 = *(_QWORD *)(W32GetUserSessionState(v63, 0, v64, v65) + 19216);
                  if ( *((_QWORD *)v67 + 3) == v63 )
                  {
                    v68 = *((_QWORD *)v67 + 5);
                    if ( *(char *)(v68 + 20) >= 0 && *(char *)(v68 + 19) >= 0 )
                      break;
                  }
                }
              }
            }
          }
LABEL_102:
          v56 = *(struct tagPROCESS_HID_TABLE **)v56;
          v61 = W32GetUserSessionState(v63, v62, v64, v65);
          v12 = v100;
        }
        v69 = *((_QWORD *)a1 + 56);
        v70 = *(unsigned __int16 *)(v69 + 16);
        v71 = *(unsigned __int16 *)(v69 + 18);
        if ( (_WORD)v70 == 12 )
        {
          v72 = (_WORD)v71 == 1;
        }
        else
        {
          if ( (_WORD)v70 != 1 )
          {
            if ( (unsigned __int16)v70 >= 0xFF00u )
              goto LABEL_90;
            goto LABEL_76;
          }
          v72 = (_WORD)v71 == 9;
        }
        if ( v72 )
        {
LABEL_90:
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
            || (v93 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
          {
            v93 = 0;
          }
          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && *((_WORD *)WPP_GLOBAL_Control + 36) )
          {
            v28 = 1;
          }
          if ( v93 || v28 )
          {
            v94 = *(_QWORD *)(*((_QWORD *)v67 + 2) + 464LL);
            v95 = W32GetUserSessionState(WPP_GLOBAL_Control, v71, v64, v65);
            LOBYTE(v96) = v28;
            LOBYTE(v97) = v93;
            WPP_RECORDER_AND_TRACE_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v97,
              v96,
              *(_QWORD *)(v95 + 69152),
              5,
              20,
              19,
              (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
              (char)v67,
              v94);
          }
          result = PostHidInput(a1, a2, Size, v67, 1u);
          v28 = 0;
          if ( !(_DWORD)result )
            goto LABEL_104;
          v13 = 1;
          goto LABEL_102;
        }
LABEL_76:
        if ( *(_QWORD *)(W32GetUserSessionState(v70, v71, v64, v65) + 18968) )
        {
          v77 = W32GetUserSessionState(v74, v73, v75, v76);
          if ( !UIPrivilegeIsolation::CheckAccess(
                  (UIPrivilegeIsolation *)(*(_QWORD *)(*((_QWORD *)v67 + 2) + 464LL) + 544LL),
                  (const struct tagUIPI_INFO *)(*(_QWORD *)(v77 + 18968) + 544LL),
                  v78) )
          {
            v74 = *(_QWORD *)(*((_QWORD *)v67 + 2) + 456LL);
            if ( *(int *)(v74 + 12) >= 0 )
            {
              v79 = *(_QWORD *)(W32GetUserSessionState(v74, v73, v75, v76) + 18968);
              v80 = *(_QWORD *)(v79 + 544);
              v81 = *(_DWORD *)(v79 + 552);
              v85 = W32GetUserSessionState(v79, v82, v83, v84);
              v86 = *((_QWORD *)v67 + 2);
              v101 = v80;
              v102 = v81;
              EtwTraceUIPIInputError(v86, 0, *(_QWORD *)(v85 + 18968), &v101, 5);
              goto LABEL_102;
            }
          }
        }
        v87 = W32GetUserSessionState(v74, v73, v75, v76) + 48;
        RIMLockShared(v87);
        if ( (*((_DWORD *)a1 + 42) & 0x1000) != 0 )
        {
          v88 = *(_QWORD *)(*((_QWORD *)a1 + 46) + 88LL);
          if ( !v88
            || *(int *)(v88 + 12) >= 0
            && ((v89 = *(_QWORD *)(*((_QWORD *)v67 + 2) + 464LL), !(unsigned __int8)IsInputThread())
             || (*((_DWORD *)a1 + 46) & 0x80u) == 0
              ? (v91 = (UIPrivilegeIsolation *)(*((_QWORD *)PtiCurrent() + 57) + 864LL))
              : (v91 = (UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 960LL)),
                v92 = UIPrivilegeIsolation::CheckAccess(v91, (const struct tagUIPI_INFO *)(v89 + 544), v90),
                v28 = 0,
                !v92) )
          {
            RIMUnlockShared(v87);
            goto LABEL_102;
          }
        }
        RIMUnlockShared(v87);
        goto LABEL_90;
      }
      v40 = *(_QWORD *)(*((_QWORD *)v39 + 2) + 464LL);
    }
    else
    {
      v40 = *(_QWORD *)(v38 + 18968);
    }
    if ( (*((_DWORD *)a1 + 42) & 0x20) == 0
      || (*(_DWORD *)(*((_QWORD *)a1 + 57) + 368LL) & 0x10) != 0
      || (!(unsigned __int8)IsInputThread()
        ? (v42 = (UIPrivilegeIsolation *)(*((_QWORD *)PtiCurrent() + 57) + 864LL))
        : (v42 = (UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 960LL)),
          UIPrivilegeIsolation::CheckAccess(v42, (const struct tagUIPI_INFO *)(v40 + 544), v41)) )
    {
      if ( (unsigned int)PostHidInput(a1, a2, v3, v39, 0) )
      {
        v13 = 1;
        v100 = 0;
        v12 = 0;
      }
    }
    goto LABEL_57;
  }
  return result;
}

```

## disassembly

```asm
0x1400bf810  mov     rax, rsp
0x1400bf813  mov     [rax+8], rbx
0x1400bf817  mov     [rax+18h], r8d
0x1400bf81b  mov     [rax+10h], rdx
0x1400bf81f  push    rbp
0x1400bf820  push    rsi
0x1400bf821  push    rdi
0x1400bf822  push    r12
0x1400bf824  push    r13
0x1400bf826  push    r14
0x1400bf828  push    r15
0x1400bf82a  sub     rsp, 90h
0x1400bf831  movaps  xmmword ptr [rax-48h], xmm6
0x1400bf835  mov     r15d, r8d
0x1400bf838  mov     rbp, rcx
0x1400bf83b  mov     r9, cs:WPP_GLOBAL_Control
0x1400bf842  lea     rax, WPP_GLOBAL_Control
0x1400bf849  xor     r13d, r13d
0x1400bf84c  cmp     r9, rax
0x1400bf84f  jz      short loc_1400BF863
0x1400bf851  bt      dword ptr [r9+2Ch], 13h
0x1400bf857  jnb     short loc_1400BF863
0x1400bf859  cmp     byte ptr [r9+29h], 5
0x1400bf85e  mov     dil, 1
0x1400bf861  jnb     short loc_1400BF866
0x1400bf863  mov     dil, r13b
0x1400bf866  lea     rax, WPP_RECORDER_INITIALIZED
0x1400bf86d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400bf874  jz      short loc_1400BF87F
0x1400bf876  mov     bl, 1
0x1400bf878  cmp     [r9+48h], r13w
0x1400bf87d  jnz     short loc_1400BF882
0x1400bf87f  mov     bl, r13b
0x1400bf882  lea     r14, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400bf889  test    dil, dil
0x1400bf88c  jnz     short loc_1400BF892
0x1400bf88e  test    bl, bl
0x1400bf890  jz      short loc_1400BF8D9
0x1400bf892  call    cs:__imp_W32GetUserSessionState
0x1400bf899  nop     dword ptr [rax+rax+00h]
0x1400bf89e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf8a5  mov     r8b, bl
0x1400bf8a8  mov     [rsp+0C8h+var_88], rbp
0x1400bf8ad  mov     dl, dil
0x1400bf8b0  mov     [rsp+0C8h+var_90], r14
0x1400bf8b5  mov     r9, [rax+10E20h]
0x1400bf8bc  mov     rcx, [rcx+18h]
0x1400bf8c0  mov     [rsp+0C8h+var_98], 0Fh
0x1400bf8c7  mov     [rsp+0C8h+var_A0], 14h
0x1400bf8cf  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400bf8d4  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400bf8d9  mov     rcx, rbp
0x1400bf8dc  call    IsDeviceInputAllowed
0x1400bf8e1  test    eax, eax
0x1400bf8e3  jz      loc_1400C004A
0x1400bf8e9  mov     r14d, 1
0x1400bf8ef  lea     rcx, [rsp+0C8h+arg_18]; this
0x1400bf8f7  mov     [rsp+0C8h+var_68], r14d
0x1400bf8fc  mov     r12d, r13d
0x1400bf8ff  call    ??0ReEnterLeaveCrit@@QEAA@XZ; ReEnterLeaveCrit::ReEnterLeaveCrit(void)
0x1400bf904  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf90b  lea     rax, WPP_GLOBAL_Control
0x1400bf912  cmp     rcx, rax
0x1400bf915  jz      short loc_1400BF927
0x1400bf917  bt      dword ptr [rcx+2Ch], 13h
0x1400bf91c  jnb     short loc_1400BF927
0x1400bf91e  cmp     byte ptr [rcx+29h], 5
0x1400bf922  mov     sil, r14b
0x1400bf925  jnb     short loc_1400BF92A
0x1400bf927  mov     sil, r13b
0x1400bf92a  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400bf931  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400bf938  jz      short loc_1400BF944
0x1400bf93a  mov     dil, r14b
0x1400bf93d  cmp     [rcx+48h], r13w
0x1400bf942  jnz     short loc_1400BF947
0x1400bf944  mov     dil, r13b
0x1400bf947  test    sil, sil
0x1400bf94a  jnz     short loc_1400BF951
0x1400bf94c  test    dil, dil
0x1400bf94f  jz      short loc_1400BF9B5
0x1400bf951  mov     rax, [rbp+1B8h]
0x1400bf958  movzx   ebx, word ptr [rax+2Ch]
0x1400bf95c  call    cs:__imp_W32GetUserSessionState
0x1400bf963  nop     dword ptr [rax+rax+00h]
0x1400bf968  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf96f  mov     r8b, dil
0x1400bf972  mov     dword ptr [rsp+0C8h+var_80], r15d
0x1400bf977  mov     dl, sil
0x1400bf97a  mov     dword ptr [rsp+0C8h+var_88], ebx
0x1400bf97e  mov     r9, [rax+10E20h]
0x1400bf985  lea     rax, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400bf98c  mov     rcx, [rcx+18h]
0x1400bf990  mov     [rsp+0C8h+var_90], rax
0x1400bf995  mov     [rsp+0C8h+var_98], 10h
0x1400bf99c  mov     [rsp+0C8h+var_A0], 14h
0x1400bf9a4  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400bf9a9  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1400bf9ae  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400bf9b5  call    cs:__imp_W32GetUserSessionState
0x1400bf9bc  nop     dword ptr [rax+rax+00h]
0x1400bf9c1  xor     esi, esi
0x1400bf9c3  cmp     [rax+4A18h], rsi
0x1400bf9ca  jnz     loc_1400BFA68
0x1400bf9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf9d7  lea     rax, WPP_GLOBAL_Control
0x1400bf9de  cmp     rcx, rax
0x1400bf9e1  jz      short loc_1400BF9F5
0x1400bf9e3  test    dword ptr [rcx+2Ch], 80000h
0x1400bf9ea  jz      short loc_1400BF9F5
0x1400bf9ec  cmp     byte ptr [rcx+29h], 5
0x1400bf9f0  mov     dil, r14b
0x1400bf9f3  jnb     short loc_1400BF9F8
0x1400bf9f5  mov     dil, sil
0x1400bf9f8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400bf9ff  jz      short loc_1400BFA0A
0x1400bfa01  mov     bl, r14b
0x1400bfa04  cmp     [rcx+48h], si
0x1400bfa08  jnz     short loc_1400BFA0D
0x1400bfa0a  mov     bl, sil
0x1400bfa0d  test    dil, dil
0x1400bfa10  jnz     short loc_1400BFA1A
0x1400bfa12  test    bl, bl
0x1400bfa14  jz      loc_1400BFC4A
0x1400bfa1a  call    cs:__imp_W32GetUserSessionState
0x1400bfa21  nop     dword ptr [rax+rax+00h]
0x1400bfa26  lea     rcx, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400bfa2d  mov     r8b, bl
0x1400bfa30  mov     [rsp+0C8h+var_90], rcx
0x1400bfa35  mov     dl, dil
0x1400bfa38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfa3f  mov     r9, [rax+10E20h]
0x1400bfa46  mov     [rsp+0C8h+var_98], 11h
0x1400bfa4d  mov     [rsp+0C8h+var_A0], 14h
0x1400bfa55  mov     rcx, [rcx+18h]
0x1400bfa59  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400bfa5e  call    WPP_RECORDER_AND_TRACE_SF_
0x1400bfa63  jmp     loc_1400BFC4A
0x1400bfa68  call    cs:__imp_W32GetUserSessionState
0x1400bfa6f  nop     dword ptr [rax+rax+00h]
0x1400bfa74  mov     rcx, [rax+4A18h]
0x1400bfa7b  call    PtiKbdFromQ
0x1400bfa80  mov     rcx, rbp; struct DEVICEINFO *
0x1400bfa83  mov     r13, [rax+1C8h]
0x1400bfa8a  mov     rdx, [r13+338h]; struct tagPROCESS_HID_TABLE *
0x1400bfa91  call    ?HidIsRequestedByThisProcess@@YAPEAUtagPROCESS_HID_REQUEST@@PEAUDEVICEINFO@@PEAUtagPROCESS_HID_TABLE@@@Z; HidIsRequestedByThisProcess(DEVICEINFO *,tagPROCESS_HID_TABLE *)
0x1400bfa96  mov     rbx, rax
0x1400bfa99  test    rax, rax
0x1400bfa9c  jz      loc_1400BFB75
0x1400bfaa2  call    cs:__imp_W32GetUserSessionState
0x1400bfaa9  nop     dword ptr [rax+rax+00h]
0x1400bfaae  mov     rbx, [rbx+20h]
0x1400bfab2  test    rbx, rbx
0x1400bfab5  jz      short loc_1400BFAD2
0x1400bfab7  mov     rax, [rbx+28h]
0x1400bfabb  cmp     [rax+14h], sil
0x1400bfabf  jl      loc_1400BFC4A
0x1400bfac5  mov     rax, [rbx+10h]
0x1400bfac9  mov     rdi, [rax+1D0h]
0x1400bfad0  jmp     short loc_1400BFAD9
0x1400bfad2  mov     rdi, [rax+4A18h]
0x1400bfad9  mov     eax, [rbp+0A8h]
0x1400bfadf  test    al, 20h
0x1400bfae1  jz      short loc_1400BFB43
0x1400bfae3  mov     rax, [rbp+1C8h]
0x1400bfaea  mov     ecx, [rax+170h]
0x1400bfaf0  test    cl, 10h
0x1400bfaf3  jnz     short loc_1400BFB43
0x1400bfaf5  call    cs:__imp_IsInputThread
0x1400bfafc  nop     dword ptr [rax+rax+00h]
0x1400bfb01  test    al, al
0x1400bfb03  jz      short loc_1400BFB15
0x1400bfb05  mov     rcx, [rbp+1C8h]
0x1400bfb0c  add     rcx, 3C0h
0x1400bfb13  jmp     short loc_1400BFB28
0x1400bfb15  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400bfb1a  mov     rcx, [rax+1C8h]
0x1400bfb21  add     rcx, 360h
0x1400bfb28  lea     rdx, [rdi+220h]
0x1400bfb2f  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400bfb36  nop     dword ptr [rax+rax+00h]
0x1400bfb3b  test    al, al
0x1400bfb3d  jz      loc_1400BFC4A
0x1400bfb43  mov     rdx, [rsp+0C8h+Src]; Src
0x1400bfb4b  mov     r9, rbx; struct tagWND *
0x1400bfb4e  mov     r8d, r15d; Size
0x1400bfb51  mov     [rsp+0C8h+var_A8], rsi; unsigned __int64
0x1400bfb56  mov     rcx, rbp; struct DEVICEINFO *
0x1400bfb59  call    ?PostHidInput@@YAHPEAUDEVICEINFO@@PEAXKPEAUtagWND@@_K@Z; PostHidInput(DEVICEINFO *,void *,ulong,tagWND *,unsigned __int64)
0x1400bfb5e  test    eax, eax
0x1400bfb60  jz      loc_1400BFC4A
0x1400bfb66  mov     r12d, r14d
0x1400bfb69  mov     [rsp+0C8h+var_68], esi
0x1400bfb6d  mov     r14d, esi
0x1400bfb70  jmp     loc_1400BFC4A
0x1400bfb75  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfb7c  lea     rax, WPP_GLOBAL_Control
0x1400bfb83  cmp     rcx, rax
0x1400bfb86  jz      short loc_1400BFB9A
0x1400bfb88  test    dword ptr [rcx+2Ch], 80000h
0x1400bfb8f  jz      short loc_1400BFB9A
0x1400bfb91  cmp     byte ptr [rcx+29h], 5
0x1400bfb95  mov     r15b, r14b
0x1400bfb98  jnb     short loc_1400BFB9D
0x1400bfb9a  mov     r15b, sil
0x1400bfb9d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400bfba4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400bfbab  jz      short loc_1400BFBB3
0x1400bfbad  cmp     [rcx+48h], si
0x1400bfbb1  jnz     short loc_1400BFBB6
0x1400bfbb3  mov     r14b, sil
0x1400bfbb6  test    r15b, r15b
0x1400bfbb9  jnz     short loc_1400BFBC4
0x1400bfbbb  test    r14b, r14b
0x1400bfbbe  jz      loc_1400BFC45
0x1400bfbc4  call    cs:__imp_W32GetUserSessionState
0x1400bfbcb  nop     dword ptr [rax+rax+00h]
0x1400bfbd0  mov     rcx, [rax+4A18h]
0x1400bfbd7  call    PtiKbdFromQ
0x1400bfbdc  mov     rsi, [rax+1C8h]
0x1400bfbe3  mov     rax, [rbp+1B8h]
0x1400bfbea  movzx   ebx, word ptr [rax+28h]
0x1400bfbee  movzx   edi, word ptr [rax+2Ah]
0x1400bfbf2  call    cs:__imp_W32GetUserSessionState
0x1400bfbf9  nop     dword ptr [rax+rax+00h]
0x1400bfbfe  mov     [rsp+0C8h+var_78], rsi
0x1400bfc03  lea     rcx, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400bfc0a  mov     dword ptr [rsp+0C8h+var_80], ebx
0x1400bfc0e  mov     r8b, r14b
0x1400bfc11  mov     dword ptr [rsp+0C8h+var_88], edi
0x1400bfc15  mov     dl, r15b
0x1400bfc18  mov     r9, [rax+10E20h]
0x1400bfc1f  mov     [rsp+0C8h+var_90], rcx
0x1400bfc24  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfc2b  mov     [rsp+0C8h+var_98], 12h
0x1400bfc32  mov     [rsp+0C8h+var_A0], 14h
0x1400bfc3a  mov     rcx, [rcx+18h]
0x1400bfc3e  call    WPP_RECORDER_AND_TRACE_SF_DDq
0x1400bfc43  xor     esi, esi
0x1400bfc45  mov     r14d, [rsp+0C8h+var_68]
0x1400bfc4a  call    cs:__imp_W32GetUserSessionState
0x1400bfc51  nop     dword ptr [rax+rax+00h]
0x1400bfc56  mov     r15, [rax+0D8h]
0x1400bfc5d  call    cs:__imp_W32GetUserSessionState
0x1400bfc64  nop     dword ptr [rax+rax+00h]
0x1400bfc69  jmp     loc_1400BFFC4
0x1400bfc6e  cmp     [r15+50h], esi
0x1400bfc72  jle     loc_1400BFFB0
0x1400bfc78  mov     rdx, r15; struct tagPROCESS_HID_TABLE *
0x1400bfc7b  mov     rcx, rbp; struct DEVICEINFO *
0x1400bfc7e  call    ?HidIsRequestedByThisProcess@@YAPEAUtagPROCESS_HID_REQUEST@@PEAUDEVICEINFO@@PEAUtagPROCESS_HID_TABLE@@@Z; HidIsRequestedByThisProcess(DEVICEINFO *,tagPROCESS_HID_TABLE *)
0x1400bfc83  test    rax, rax
0x1400bfc86  jz      loc_1400BFFB0
0x1400bfc8c  mov     ecx, [rax+14h]
0x1400bfc8f  mov     ebx, 1
0x1400bfc94  test    bl, cl
0x1400bfc96  jz      loc_1400BFFB0
0x1400bfc9c  test    cl, 2
0x1400bfc9f  jz      short loc_1400BFCAA
0x1400bfca1  test    r14d, r14d
0x1400bfca4  jz      loc_1400BFFB0
0x1400bfcaa  mov     rdx, [rax+28h]
0x1400bfcae  test    rdx, rdx
0x1400bfcb1  jz      short loc_1400BFCC3
0x1400bfcb3  mov     rcx, rbp
0x1400bfcb6  mov     rax, rdx
0x1400bfcb9  call    _guard_dispatch_icall
0x1400bfcbe  jmp     loc_1400BFFB0
0x1400bfcc3  mov     rdi, [rax+20h]
0x1400bfcc7  mov     rax, [rdi+10h]
0x1400bfccb  cmp     [rax+1C8h], r13
0x1400bfcd2  jz      loc_1400BFFB0
0x1400bfcd8  call    cs:__imp_W32GetUserSessionState
0x1400bfcdf  nop     dword ptr [rax+rax+00h]
0x1400bfce4  mov     rcx, [rax+4B10h]
0x1400bfceb  cmp     [rdi+18h], rcx
0x1400bfcef  jnz     loc_1400BFFB0
0x1400bfcf5  mov     rax, [rdi+28h]
0x1400bfcf9  cmp     [rax+14h], sil
0x1400bfcfd  jl      loc_1400BFFB0
0x1400bfd03  cmp     [rax+13h], sil
0x1400bfd07  jl      loc_1400BFFB0
0x1400bfd0d  mov     rax, [rbp+1C0h]
0x1400bfd14  movzx   ecx, word ptr [rax+10h]
0x1400bfd18  movzx   edx, word ptr [rax+12h]
0x1400bfd1c  cmp     cx, 0Ch
0x1400bfd20  jnz     short loc_1400BFD2C
0x1400bfd22  cmp     dx, bx
0x1400bfd25  jnz     short loc_1400BFD45
0x1400bfd27  jmp     loc_1400BFED9
0x1400bfd2c  cmp     cx, bx
0x1400bfd2f  jnz     short loc_1400BFD37
0x1400bfd31  cmp     dx, 9
0x1400bfd35  jmp     short loc_1400BFD25
0x1400bfd37  mov     eax, 0FF00h
0x1400bfd3c  cmp     cx, ax
0x1400bfd3f  jnb     loc_1400BFED9
0x1400bfd45  call    cs:__imp_W32GetUserSessionState
0x1400bfd4c  nop     dword ptr [rax+rax+00h]
0x1400bfd51  cmp     [rax+4A18h], rsi
  ... truncated ...
```
