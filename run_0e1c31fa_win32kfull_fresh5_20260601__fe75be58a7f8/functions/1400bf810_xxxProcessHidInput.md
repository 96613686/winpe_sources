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
