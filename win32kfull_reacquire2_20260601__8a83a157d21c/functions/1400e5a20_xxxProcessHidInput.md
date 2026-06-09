# xxxProcessHidInput

- ea: `0x1400e5a20`
- end: `0x1400e627b`
- name: `xxxProcessHidInput`
- size: `2139`
- prototype: `__int64 __fastcall(struct DEVICEINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400e6290`

## callees

- `0x14002eb54`
- `0x1400c636c`
- `0x1400ca844`
- `0x1400cb390`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x1400e5a20`
- `0x140139a48`
- `0x1401ab540`
- `0x1401b9e84`
- `0x1401d43d0`
- `0x140259f98`
- `0x140343080`

## import_xrefs

- `win32kbase!?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z` at `0x1400e6238`
- `win32kbase!?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z` at `0x1400e6238`
- `win32kbase!RIMUnlockShared` at `0x1400e605e`
- `win32kbase!RIMUnlockShared` at `0x1400e60d8`
- `win32kbase!RIMUnlockShared` at `0x1400e605e`
- `win32kbase!RIMUnlockShared` at `0x1400e60d8`
- `win32kbase!RIMLockShared` at `0x1400e602f`
- `win32kbase!RIMLockShared` at `0x1400e602f`
- `win32kbase!IsInputThread` at `0x1400e5d05`
- `win32kbase!IsInputThread` at `0x1400e607f`
- `win32kbase!IsInputThread` at `0x1400e5d05`
- `win32kbase!IsInputThread` at `0x1400e607f`
- `win32kbase!UserSessionSwitchLeaveCritWithNonPaged` at `0x1400e624e`
- `win32kbase!UserSessionSwitchLeaveCritWithNonPaged` at `0x1400e624e`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400e600b`
- `win32kbase!EtwTraceUIPIInputError` at `0x1400e600b`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e5d3f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e5f9a`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e60c3`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e5d3f`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e5f9a`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1400e60c3`
- `WIN32K!W32GetUserSessionState` at `0x1400e5aa2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5b6c`
- `WIN32K!W32GetUserSessionState` at `0x1400e5bc5`
- `WIN32K!W32GetUserSessionState` at `0x1400e5c2a`
- `WIN32K!W32GetUserSessionState` at `0x1400e5c78`
- `WIN32K!W32GetUserSessionState` at `0x1400e5cb2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5dd4`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e02`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e5a`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e6d`
- `WIN32K!W32GetUserSessionState` at `0x1400e5ee8`
- `WIN32K!W32GetUserSessionState` at `0x1400e5f55`
- `WIN32K!W32GetUserSessionState` at `0x1400e5f6e`
- `WIN32K!W32GetUserSessionState` at `0x1400e5fba`
- `WIN32K!W32GetUserSessionState` at `0x1400e5fdb`
- `WIN32K!W32GetUserSessionState` at `0x1400e601c`
- `WIN32K!W32GetUserSessionState` at `0x1400e613f`
- `WIN32K!W32GetUserSessionState` at `0x1400e61c3`
- `WIN32K!W32GetUserSessionState` at `0x1400e61f2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5aa2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5b6c`
- `WIN32K!W32GetUserSessionState` at `0x1400e5bc5`
- `WIN32K!W32GetUserSessionState` at `0x1400e5c2a`
- `WIN32K!W32GetUserSessionState` at `0x1400e5c78`
- `WIN32K!W32GetUserSessionState` at `0x1400e5cb2`
- `WIN32K!W32GetUserSessionState` at `0x1400e5dd4`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e02`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e5a`
- `WIN32K!W32GetUserSessionState` at `0x1400e5e6d`
- `WIN32K!W32GetUserSessionState` at `0x1400e5ee8`
- `WIN32K!W32GetUserSessionState` at `0x1400e5f55`
- `WIN32K!W32GetUserSessionState` at `0x1400e5f6e`
- `WIN32K!W32GetUserSessionState` at `0x1400e5fba`
- `WIN32K!W32GetUserSessionState` at `0x1400e5fdb`
- `WIN32K!W32GetUserSessionState` at `0x1400e601c`
- `WIN32K!W32GetUserSessionState` at `0x1400e613f`
- `WIN32K!W32GetUserSessionState` at `0x1400e61c3`
- `WIN32K!W32GetUserSessionState` at `0x1400e61f2`

## pseudocode

```c
__int64 __fastcall xxxProcessHidInput(struct DEVICEINFO *a1, void *a2, unsigned int a3)
{
  __int64 v5; // r13
  char v6; // di
  char v7; // bl
  __int64 UserSessionState; // rax
  int v9; // r8d
  int v10; // edx
  __int64 result; // rax
  int v12; // r14d
  int v13; // r12d
  struct MOVESIZEDATA *v14; // rcx
  char v15; // si
  char v16; // di
  __int16 v17; // bx
  __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  __int64 v21; // rcx
  char v22; // si
  struct MOVESIZEDATA *v23; // rcx
  char v24; // di
  char v25; // bl
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rcx
  struct tagPROCESS_HID_REQUEST *v31; // rbx
  __int64 v32; // rax
  struct tagWND *v33; // rbx
  __int64 v34; // rdi
  const struct tagUIPI_INFO *v35; // r8
  UIPrivilegeIsolation *v36; // rcx
  char v37; // r15
  __int64 v38; // rax
  __int64 v39; // rsi
  __int64 v40; // rax
  __int16 v41; // bx
  __int16 v42; // di
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r8d
  int v46; // edx
  struct tagPROCESS_HID_TABLE *v47; // r15
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  struct tagPROCESS_HID_REQUEST *v51; // rax
  struct tagWND *v52; // rdi
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  __int16 v56; // dx
  bool v57; // zf
  __int64 v58; // rcx
  __int64 v59; // rax
  const struct tagUIPI_INFO *v60; // r8
  __int64 v61; // rcx
  __int64 v62; // xmm6_8
  int v63; // ebx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rbx
  __int64 v67; // rcx
  __int64 v68; // rsi
  const struct tagUIPI_INFO *v69; // r8
  UIPrivilegeIsolation *v70; // rcx
  bool v71; // al
  char v72; // r14
  __int64 v73; // rbx
  __int64 v74; // rax
  int v75; // r8d
  int v76; // edx
  __int64 v77; // rax
  int v78; // [rsp+20h] [rbp-A8h]
  int v79; // [rsp+60h] [rbp-68h]
  __int64 v80; // [rsp+70h] [rbp-58h] BYREF
  int v81; // [rsp+78h] [rbp-50h]
  char v84; // [rsp+E8h] [rbp+20h] BYREF

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
    UserSessionState = W32GetUserSessionState(a1);
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
    v79 = 1;
    v13 = 0;
    ReEnterLeaveCrit::ReEnterLeaveCrit((ReEnterLeaveCrit *)&v84);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x13u)
      || (v15 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      v15 = 0;
    }
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || (v16 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v16 = 0;
    }
    if ( v15 || v16 )
    {
      v17 = *(_WORD *)(*((_QWORD *)a1 + 55) + 44LL);
      v18 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v19) = v16;
      LOBYTE(v20) = v15;
      WPP_RECORDER_AND_TRACE_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v20,
        v19,
        *(_QWORD *)(v18 + 69152),
        5,
        20,
        16,
        (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
        v17,
        a3);
    }
    v22 = 0;
    if ( !*(_QWORD *)(W32GetUserSessionState(v14) + 18968) )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
      {
        v24 = 0;
      }
      if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
        || (v25 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
      {
        v25 = 0;
      }
      if ( v24 || v25 )
      {
        v26 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v27) = v25;
        LOBYTE(v28) = v24;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v28,
          v27,
          *(_QWORD *)(v26 + 69152),
          5,
          20,
          17,
          (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids);
      }
      goto LABEL_57;
    }
    v29 = W32GetUserSessionState(v21);
    v5 = *(_QWORD *)(PtiKbdFromQ(*(_QWORD *)(v29 + 18968)) + 456);
    v31 = HidIsRequestedByThisProcess(a1, *(struct tagPROCESS_HID_TABLE **)(v5 + 824));
    if ( !v31 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
        || (v37 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
      {
        v37 = 0;
      }
      if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
        || !*((_WORD *)WPP_GLOBAL_Control + 36) )
      {
        LOBYTE(v12) = 0;
      }
      if ( v37 || (_BYTE)v12 )
      {
        v38 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v39 = *(_QWORD *)(PtiKbdFromQ(*(_QWORD *)(v38 + 18968)) + 456);
        v40 = *((_QWORD *)a1 + 55);
        v41 = *(_WORD *)(v40 + 40);
        v42 = *(_WORD *)(v40 + 42);
        v44 = W32GetUserSessionState(v43);
        LOBYTE(v45) = v12;
        LOBYTE(v46) = v37;
        WPP_RECORDER_AND_TRACE_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v46,
          v45,
          *(_QWORD *)(v44 + 69152),
          v78,
          20,
          18,
          (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
          v42,
          v41,
          v39);
        v22 = 0;
      }
      v12 = 1;
      goto LABEL_57;
    }
    v32 = W32GetUserSessionState(v30);
    v33 = (struct tagWND *)*((_QWORD *)v31 + 4);
    if ( v33 )
    {
      if ( *(char *)(*((_QWORD *)v33 + 5) + 20LL) < 0 )
      {
LABEL_57:
        v47 = *(struct tagPROCESS_HID_TABLE **)(W32GetUserSessionState(v23) + 216);
        v49 = W32GetUserSessionState(v48);
        while ( 1 )
        {
          result = v49 + 216;
          if ( v47 == (struct tagPROCESS_HID_TABLE *)result )
          {
LABEL_104:
            if ( v13 )
            {
              result = *((unsigned int *)a1 + 46);
              if ( (result & 0x40) == 0 )
              {
                v77 = W32GetUserSessionState(v50);
                result = CInputGlobals::UpdateInputGlobals(
                           *(_QWORD *)(v77 + 3008),
                           (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                          * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64,
                           4);
              }
            }
            if ( !v84 )
              return UserSessionSwitchLeaveCritWithNonPaged();
            return result;
          }
          if ( *((int *)v47 + 20) > 0 )
          {
            v51 = HidIsRequestedByThisProcess(a1, v47);
            if ( v51 )
            {
              v50 = *((unsigned int *)v51 + 5);
              if ( (v50 & 1) != 0 && ((v50 & 2) == 0 || v12) )
              {
                if ( *((_QWORD *)v51 + 5) )
                {
                  (*((void (__fastcall **)(struct DEVICEINFO *))v51 + 5))(a1);
                  goto LABEL_102;
                }
                v52 = (struct tagWND *)*((_QWORD *)v51 + 4);
                if ( *(_QWORD *)(*((_QWORD *)v52 + 2) + 456LL) != v5 )
                {
                  v50 = *(_QWORD *)(W32GetUserSessionState(v50) + 19216);
                  if ( *((_QWORD *)v52 + 3) == v50 )
                  {
                    v53 = *((_QWORD *)v52 + 5);
                    if ( *(char *)(v53 + 20) >= 0 && *(char *)(v53 + 19) >= 0 )
                      break;
                  }
                }
              }
            }
          }
LABEL_102:
          v47 = *(struct tagPROCESS_HID_TABLE **)v47;
          v49 = W32GetUserSessionState(v50);
          v12 = v79;
        }
        v54 = *((_QWORD *)a1 + 56);
        v55 = *(unsigned __int16 *)(v54 + 16);
        v56 = *(_WORD *)(v54 + 18);
        if ( (_WORD)v55 == 12 )
        {
          v57 = v56 == 1;
        }
        else
        {
          if ( (_WORD)v55 != 1 )
          {
            if ( (unsigned __int16)v55 >= 0xFF00u )
              goto LABEL_90;
            goto LABEL_76;
          }
          v57 = v56 == 9;
        }
        if ( v57 )
        {
LABEL_90:
          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80000) == 0
            || (v72 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
          {
            v72 = 0;
          }
          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && *((_WORD *)WPP_GLOBAL_Control + 36) )
          {
            v22 = 1;
          }
          if ( v72 || v22 )
          {
            v73 = *(_QWORD *)(*((_QWORD *)v52 + 2) + 464LL);
            v74 = W32GetUserSessionState(WPP_GLOBAL_Control);
            LOBYTE(v75) = v22;
            LOBYTE(v76) = v72;
            WPP_RECORDER_AND_TRACE_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v76,
              v75,
              *(_QWORD *)(v74 + 69152),
              5,
              20,
              19,
              (__int64)WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids,
              (char)v52,
              v73);
          }
          result = PostHidInput(a1, a2, a3, v52, 1u);
          v22 = 0;
          if ( !(_DWORD)result )
            goto LABEL_104;
          v13 = 1;
          goto LABEL_102;
        }
LABEL_76:
        if ( *(_QWORD *)(W32GetUserSessionState(v55) + 18968) )
        {
          v59 = W32GetUserSessionState(v58);
          if ( !UIPrivilegeIsolation::CheckAccess(
                  (UIPrivilegeIsolation *)(*(_QWORD *)(*((_QWORD *)v52 + 2) + 464LL) + 544LL),
                  (const struct tagUIPI_INFO *)(*(_QWORD *)(v59 + 18968) + 544LL),
                  v60) )
          {
            v58 = *(_QWORD *)(*((_QWORD *)v52 + 2) + 456LL);
            if ( *(int *)(v58 + 12) >= 0 )
            {
              v61 = *(_QWORD *)(W32GetUserSessionState(v58) + 18968);
              v62 = *(_QWORD *)(v61 + 544);
              v63 = *(_DWORD *)(v61 + 552);
              v64 = W32GetUserSessionState(v61);
              v65 = *((_QWORD *)v52 + 2);
              v80 = v62;
              v81 = v63;
              EtwTraceUIPIInputError(v65, 0, *(_QWORD *)(v64 + 18968), &v80, 5);
              goto LABEL_102;
            }
          }
        }
        v66 = W32GetUserSessionState(v58) + 48;
        RIMLockShared(v66);
        if ( (*((_DWORD *)a1 + 42) & 0x1000) != 0 )
        {
          v67 = *(_QWORD *)(*((_QWORD *)a1 + 46) + 88LL);
          if ( !v67
            || *(int *)(v67 + 12) >= 0
            && ((v68 = *(_QWORD *)(*((_QWORD *)v52 + 2) + 464LL), !(unsigned __int8)IsInputThread())
             || (*((_DWORD *)a1 + 46) & 0x80u) == 0
              ? (v70 = (UIPrivilegeIsolation *)(*((_QWORD *)PtiCurrent() + 57) + 864LL))
              : (v70 = (UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 960LL)),
                v71 = UIPrivilegeIsolation::CheckAccess(v70, (const struct tagUIPI_INFO *)(v68 + 544), v69),
                v22 = 0,
                !v71) )
          {
            RIMUnlockShared(v66);
            goto LABEL_102;
          }
        }
        RIMUnlockShared(v66);
        goto LABEL_90;
      }
      v34 = *(_QWORD *)(*((_QWORD *)v33 + 2) + 464LL);
    }
    else
    {
      v34 = *(_QWORD *)(v32 + 18968);
    }
    if ( (*((_DWORD *)a1 + 42) & 0x20) == 0
      || (*(_DWORD *)(*((_QWORD *)a1 + 57) + 368LL) & 0x10) != 0
      || (!(unsigned __int8)IsInputThread()
        ? (v36 = (UIPrivilegeIsolation *)(*((_QWORD *)PtiCurrent() + 57) + 864LL))
        : (v36 = (UIPrivilegeIsolation *)(*((_QWORD *)a1 + 57) + 960LL)),
          UIPrivilegeIsolation::CheckAccess(v36, (const struct tagUIPI_INFO *)(v34 + 544), v35)) )
    {
      if ( (unsigned int)PostHidInput(a1, a2, a3, v33, 0) )
      {
        v13 = 1;
        v79 = 0;
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
0x1400e5a20  mov     rax, rsp
0x1400e5a23  mov     [rax+8], rbx
0x1400e5a27  mov     [rax+18h], r8d
0x1400e5a2b  mov     [rax+10h], rdx
0x1400e5a2f  push    rbp
0x1400e5a30  push    rsi
0x1400e5a31  push    rdi
0x1400e5a32  push    r12
0x1400e5a34  push    r13
0x1400e5a36  push    r14
0x1400e5a38  push    r15
0x1400e5a3a  sub     rsp, 90h
0x1400e5a41  movaps  xmmword ptr [rax-48h], xmm6
0x1400e5a45  mov     r15d, r8d
0x1400e5a48  mov     rbp, rcx
0x1400e5a4b  mov     r9, cs:WPP_GLOBAL_Control
0x1400e5a52  lea     rax, WPP_GLOBAL_Control
0x1400e5a59  xor     r13d, r13d
0x1400e5a5c  cmp     r9, rax
0x1400e5a5f  jz      short loc_1400E5A73
0x1400e5a61  bt      dword ptr [r9+2Ch], 13h
0x1400e5a67  jnb     short loc_1400E5A73
0x1400e5a69  cmp     byte ptr [r9+29h], 5
0x1400e5a6e  mov     dil, 1
0x1400e5a71  jnb     short loc_1400E5A76
0x1400e5a73  mov     dil, r13b
0x1400e5a76  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e5a7d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e5a84  jz      short loc_1400E5A8F
0x1400e5a86  mov     bl, 1
0x1400e5a88  cmp     [r9+48h], r13w
0x1400e5a8d  jnz     short loc_1400E5A92
0x1400e5a8f  mov     bl, r13b
0x1400e5a92  lea     r14, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400e5a99  test    dil, dil
0x1400e5a9c  jnz     short loc_1400E5AA2
0x1400e5a9e  test    bl, bl
0x1400e5aa0  jz      short loc_1400E5AE9
0x1400e5aa2  call    cs:__imp_W32GetUserSessionState
0x1400e5aa9  nop     dword ptr [rax+rax+00h]
0x1400e5aae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5ab5  mov     r8b, bl
0x1400e5ab8  mov     [rsp+0C8h+var_88], rbp
0x1400e5abd  mov     dl, dil
0x1400e5ac0  mov     [rsp+0C8h+var_90], r14
0x1400e5ac5  mov     r9, [rax+10E20h]
0x1400e5acc  mov     rcx, [rcx+18h]
0x1400e5ad0  mov     [rsp+0C8h+var_98], 0Fh
0x1400e5ad7  mov     [rsp+0C8h+var_A0], 14h
0x1400e5adf  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400e5ae4  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400e5ae9  mov     rcx, rbp
0x1400e5aec  call    IsDeviceInputAllowed
0x1400e5af1  test    eax, eax
0x1400e5af3  jz      loc_1400E625A
0x1400e5af9  mov     r14d, 1
0x1400e5aff  lea     rcx, [rsp+0C8h+arg_18]; this
0x1400e5b07  mov     [rsp+0C8h+var_68], r14d
0x1400e5b0c  mov     r12d, r13d
0x1400e5b0f  call    ??0ReEnterLeaveCrit@@QEAA@XZ; ReEnterLeaveCrit::ReEnterLeaveCrit(void)
0x1400e5b14  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5b1b  lea     rax, WPP_GLOBAL_Control
0x1400e5b22  cmp     rcx, rax
0x1400e5b25  jz      short loc_1400E5B37
0x1400e5b27  bt      dword ptr [rcx+2Ch], 13h
0x1400e5b2c  jnb     short loc_1400E5B37
0x1400e5b2e  cmp     byte ptr [rcx+29h], 5
0x1400e5b32  mov     sil, r14b
0x1400e5b35  jnb     short loc_1400E5B3A
0x1400e5b37  mov     sil, r13b
0x1400e5b3a  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400e5b41  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400e5b48  jz      short loc_1400E5B54
0x1400e5b4a  mov     dil, r14b
0x1400e5b4d  cmp     [rcx+48h], r13w
0x1400e5b52  jnz     short loc_1400E5B57
0x1400e5b54  mov     dil, r13b
0x1400e5b57  test    sil, sil
0x1400e5b5a  jnz     short loc_1400E5B61
0x1400e5b5c  test    dil, dil
0x1400e5b5f  jz      short loc_1400E5BC5
0x1400e5b61  mov     rax, [rbp+1B8h]
0x1400e5b68  movzx   ebx, word ptr [rax+2Ch]
0x1400e5b6c  call    cs:__imp_W32GetUserSessionState
0x1400e5b73  nop     dword ptr [rax+rax+00h]
0x1400e5b78  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5b7f  mov     r8b, dil
0x1400e5b82  mov     dword ptr [rsp+0C8h+var_80], r15d
0x1400e5b87  mov     dl, sil
0x1400e5b8a  mov     dword ptr [rsp+0C8h+var_88], ebx
0x1400e5b8e  mov     r9, [rax+10E20h]
0x1400e5b95  lea     rax, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400e5b9c  mov     rcx, [rcx+18h]
0x1400e5ba0  mov     [rsp+0C8h+var_90], rax
0x1400e5ba5  mov     [rsp+0C8h+var_98], 10h
0x1400e5bac  mov     [rsp+0C8h+var_A0], 14h
0x1400e5bb4  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400e5bb9  call    WPP_RECORDER_AND_TRACE_SF_DD
0x1400e5bbe  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400e5bc5  call    cs:__imp_W32GetUserSessionState
0x1400e5bcc  nop     dword ptr [rax+rax+00h]
0x1400e5bd1  xor     esi, esi
0x1400e5bd3  cmp     [rax+4A18h], rsi
0x1400e5bda  jnz     loc_1400E5C78
0x1400e5be0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5be7  lea     rax, WPP_GLOBAL_Control
0x1400e5bee  cmp     rcx, rax
0x1400e5bf1  jz      short loc_1400E5C05
0x1400e5bf3  test    dword ptr [rcx+2Ch], 80000h
0x1400e5bfa  jz      short loc_1400E5C05
0x1400e5bfc  cmp     byte ptr [rcx+29h], 5
0x1400e5c00  mov     dil, r14b
0x1400e5c03  jnb     short loc_1400E5C08
0x1400e5c05  mov     dil, sil
0x1400e5c08  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400e5c0f  jz      short loc_1400E5C1A
0x1400e5c11  mov     bl, r14b
0x1400e5c14  cmp     [rcx+48h], si
0x1400e5c18  jnz     short loc_1400E5C1D
0x1400e5c1a  mov     bl, sil
0x1400e5c1d  test    dil, dil
0x1400e5c20  jnz     short loc_1400E5C2A
0x1400e5c22  test    bl, bl
0x1400e5c24  jz      loc_1400E5E5A
0x1400e5c2a  call    cs:__imp_W32GetUserSessionState
0x1400e5c31  nop     dword ptr [rax+rax+00h]
0x1400e5c36  lea     rcx, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400e5c3d  mov     r8b, bl
0x1400e5c40  mov     [rsp+0C8h+var_90], rcx
0x1400e5c45  mov     dl, dil
0x1400e5c48  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5c4f  mov     r9, [rax+10E20h]
0x1400e5c56  mov     [rsp+0C8h+var_98], 11h
0x1400e5c5d  mov     [rsp+0C8h+var_A0], 14h
0x1400e5c65  mov     rcx, [rcx+18h]
0x1400e5c69  mov     byte ptr [rsp+0C8h+var_A8], 5
0x1400e5c6e  call    WPP_RECORDER_AND_TRACE_SF_
0x1400e5c73  jmp     loc_1400E5E5A
0x1400e5c78  call    cs:__imp_W32GetUserSessionState
0x1400e5c7f  nop     dword ptr [rax+rax+00h]
0x1400e5c84  mov     rcx, [rax+4A18h]
0x1400e5c8b  call    PtiKbdFromQ
0x1400e5c90  mov     rcx, rbp; struct DEVICEINFO *
0x1400e5c93  mov     r13, [rax+1C8h]
0x1400e5c9a  mov     rdx, [r13+338h]; struct tagPROCESS_HID_TABLE *
0x1400e5ca1  call    ?HidIsRequestedByThisProcess@@YAPEAUtagPROCESS_HID_REQUEST@@PEAUDEVICEINFO@@PEAUtagPROCESS_HID_TABLE@@@Z; HidIsRequestedByThisProcess(DEVICEINFO *,tagPROCESS_HID_TABLE *)
0x1400e5ca6  mov     rbx, rax
0x1400e5ca9  test    rax, rax
0x1400e5cac  jz      loc_1400E5D85
0x1400e5cb2  call    cs:__imp_W32GetUserSessionState
0x1400e5cb9  nop     dword ptr [rax+rax+00h]
0x1400e5cbe  mov     rbx, [rbx+20h]
0x1400e5cc2  test    rbx, rbx
0x1400e5cc5  jz      short loc_1400E5CE2
0x1400e5cc7  mov     rax, [rbx+28h]
0x1400e5ccb  cmp     [rax+14h], sil
0x1400e5ccf  jl      loc_1400E5E5A
0x1400e5cd5  mov     rax, [rbx+10h]
0x1400e5cd9  mov     rdi, [rax+1D0h]
0x1400e5ce0  jmp     short loc_1400E5CE9
0x1400e5ce2  mov     rdi, [rax+4A18h]
0x1400e5ce9  mov     eax, [rbp+0A8h]
0x1400e5cef  test    al, 20h
0x1400e5cf1  jz      short loc_1400E5D53
0x1400e5cf3  mov     rax, [rbp+1C8h]
0x1400e5cfa  mov     ecx, [rax+170h]
0x1400e5d00  test    cl, 10h
0x1400e5d03  jnz     short loc_1400E5D53
0x1400e5d05  call    cs:__imp_IsInputThread
0x1400e5d0c  nop     dword ptr [rax+rax+00h]
0x1400e5d11  test    al, al
0x1400e5d13  jz      short loc_1400E5D25
0x1400e5d15  mov     rcx, [rbp+1C8h]
0x1400e5d1c  add     rcx, 3C0h
0x1400e5d23  jmp     short loc_1400E5D38
0x1400e5d25  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400e5d2a  mov     rcx, [rax+1C8h]
0x1400e5d31  add     rcx, 360h
0x1400e5d38  lea     rdx, [rdi+220h]
0x1400e5d3f  call    cs:__imp_?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z; UIPrivilegeIsolation::CheckAccess(tagUIPI_INFO const &,tagUIPI_INFO const &)
0x1400e5d46  nop     dword ptr [rax+rax+00h]
0x1400e5d4b  test    al, al
0x1400e5d4d  jz      loc_1400E5E5A
0x1400e5d53  mov     rdx, [rsp+0C8h+Src]; Src
0x1400e5d5b  mov     r9, rbx; struct tagWND *
0x1400e5d5e  mov     r8d, r15d; Size
0x1400e5d61  mov     [rsp+0C8h+var_A8], rsi; unsigned __int64
0x1400e5d66  mov     rcx, rbp; struct DEVICEINFO *
0x1400e5d69  call    ?PostHidInput@@YAHPEAUDEVICEINFO@@PEAXKPEAUtagWND@@_K@Z; PostHidInput(DEVICEINFO *,void *,ulong,tagWND *,unsigned __int64)
0x1400e5d6e  test    eax, eax
0x1400e5d70  jz      loc_1400E5E5A
0x1400e5d76  mov     r12d, r14d
0x1400e5d79  mov     [rsp+0C8h+var_68], esi
0x1400e5d7d  mov     r14d, esi
0x1400e5d80  jmp     loc_1400E5E5A
0x1400e5d85  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5d8c  lea     rax, WPP_GLOBAL_Control
0x1400e5d93  cmp     rcx, rax
0x1400e5d96  jz      short loc_1400E5DAA
0x1400e5d98  test    dword ptr [rcx+2Ch], 80000h
0x1400e5d9f  jz      short loc_1400E5DAA
0x1400e5da1  cmp     byte ptr [rcx+29h], 5
0x1400e5da5  mov     r15b, r14b
0x1400e5da8  jnb     short loc_1400E5DAD
0x1400e5daa  mov     r15b, sil
0x1400e5dad  lea     rax, WPP_RECORDER_INITIALIZED
0x1400e5db4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400e5dbb  jz      short loc_1400E5DC3
0x1400e5dbd  cmp     [rcx+48h], si
0x1400e5dc1  jnz     short loc_1400E5DC6
0x1400e5dc3  mov     r14b, sil
0x1400e5dc6  test    r15b, r15b
0x1400e5dc9  jnz     short loc_1400E5DD4
0x1400e5dcb  test    r14b, r14b
0x1400e5dce  jz      loc_1400E5E55
0x1400e5dd4  call    cs:__imp_W32GetUserSessionState
0x1400e5ddb  nop     dword ptr [rax+rax+00h]
0x1400e5de0  mov     rcx, [rax+4A18h]
0x1400e5de7  call    PtiKbdFromQ
0x1400e5dec  mov     rsi, [rax+1C8h]
0x1400e5df3  mov     rax, [rbp+1B8h]
0x1400e5dfa  movzx   ebx, word ptr [rax+28h]
0x1400e5dfe  movzx   edi, word ptr [rax+2Ah]
0x1400e5e02  call    cs:__imp_W32GetUserSessionState
0x1400e5e09  nop     dword ptr [rax+rax+00h]
0x1400e5e0e  mov     [rsp+0C8h+var_78], rsi
0x1400e5e13  lea     rcx, WPP_614fa82acbf839f5b7aff598284aa4ff_Traceguids
0x1400e5e1a  mov     dword ptr [rsp+0C8h+var_80], ebx
0x1400e5e1e  mov     r8b, r14b
0x1400e5e21  mov     dword ptr [rsp+0C8h+var_88], edi
0x1400e5e25  mov     dl, r15b
0x1400e5e28  mov     r9, [rax+10E20h]
0x1400e5e2f  mov     [rsp+0C8h+var_90], rcx
0x1400e5e34  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e5e3b  mov     [rsp+0C8h+var_98], 12h
0x1400e5e42  mov     [rsp+0C8h+var_A0], 14h
0x1400e5e4a  mov     rcx, [rcx+18h]
0x1400e5e4e  call    WPP_RECORDER_AND_TRACE_SF_DDq
0x1400e5e53  xor     esi, esi
0x1400e5e55  mov     r14d, [rsp+0C8h+var_68]
0x1400e5e5a  call    cs:__imp_W32GetUserSessionState
0x1400e5e61  nop     dword ptr [rax+rax+00h]
0x1400e5e66  mov     r15, [rax+0D8h]
0x1400e5e6d  call    cs:__imp_W32GetUserSessionState
0x1400e5e74  nop     dword ptr [rax+rax+00h]
0x1400e5e79  jmp     loc_1400E61D4
0x1400e5e7e  cmp     [r15+50h], esi
0x1400e5e82  jle     loc_1400E61C0
0x1400e5e88  mov     rdx, r15; struct tagPROCESS_HID_TABLE *
0x1400e5e8b  mov     rcx, rbp; struct DEVICEINFO *
0x1400e5e8e  call    ?HidIsRequestedByThisProcess@@YAPEAUtagPROCESS_HID_REQUEST@@PEAUDEVICEINFO@@PEAUtagPROCESS_HID_TABLE@@@Z; HidIsRequestedByThisProcess(DEVICEINFO *,tagPROCESS_HID_TABLE *)
0x1400e5e93  test    rax, rax
0x1400e5e96  jz      loc_1400E61C0
0x1400e5e9c  mov     ecx, [rax+14h]
0x1400e5e9f  mov     ebx, 1
0x1400e5ea4  test    bl, cl
0x1400e5ea6  jz      loc_1400E61C0
0x1400e5eac  test    cl, 2
0x1400e5eaf  jz      short loc_1400E5EBA
0x1400e5eb1  test    r14d, r14d
0x1400e5eb4  jz      loc_1400E61C0
0x1400e5eba  mov     rdx, [rax+28h]
0x1400e5ebe  test    rdx, rdx
0x1400e5ec1  jz      short loc_1400E5ED3
0x1400e5ec3  mov     rcx, rbp
0x1400e5ec6  mov     rax, rdx
0x1400e5ec9  call    _guard_dispatch_icall
0x1400e5ece  jmp     loc_1400E61C0
0x1400e5ed3  mov     rdi, [rax+20h]
0x1400e5ed7  mov     rax, [rdi+10h]
0x1400e5edb  cmp     [rax+1C8h], r13
0x1400e5ee2  jz      loc_1400E61C0
0x1400e5ee8  call    cs:__imp_W32GetUserSessionState
0x1400e5eef  nop     dword ptr [rax+rax+00h]
0x1400e5ef4  mov     rcx, [rax+4B10h]
0x1400e5efb  cmp     [rdi+18h], rcx
0x1400e5eff  jnz     loc_1400E61C0
0x1400e5f05  mov     rax, [rdi+28h]
0x1400e5f09  cmp     [rax+14h], sil
0x1400e5f0d  jl      loc_1400E61C0
0x1400e5f13  cmp     [rax+13h], sil
0x1400e5f17  jl      loc_1400E61C0
0x1400e5f1d  mov     rax, [rbp+1C0h]
0x1400e5f24  movzx   ecx, word ptr [rax+10h]
0x1400e5f28  movzx   edx, word ptr [rax+12h]
0x1400e5f2c  cmp     cx, 0Ch
0x1400e5f30  jnz     short loc_1400E5F3C
0x1400e5f32  cmp     dx, bx
0x1400e5f35  jnz     short loc_1400E5F55
0x1400e5f37  jmp     loc_1400E60E9
0x1400e5f3c  cmp     cx, bx
0x1400e5f3f  jnz     short loc_1400E5F47
0x1400e5f41  cmp     dx, 9
0x1400e5f45  jmp     short loc_1400E5F35
0x1400e5f47  mov     eax, 0FF00h
0x1400e5f4c  cmp     cx, ax
0x1400e5f4f  jnb     loc_1400E60E9
0x1400e5f55  call    cs:__imp_W32GetUserSessionState
0x1400e5f5c  nop     dword ptr [rax+rax+00h]
0x1400e5f61  cmp     [rax+4A18h], rsi
  ... truncated ...
```
