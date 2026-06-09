# xxxBroadcastMessageEx

- ea: `0x140021348`
- end: `0x140021dcb`
- name: `xxxBroadcastMessageEx`
- size: `2691`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, struct _LARGE_STRING *volatile, unsigned int, __int64, int, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14013e398`
- `0x14020de80`
- `0x1402367b0`

## callees

- `0x14001a8b0`
- `0x14001adf0`
- `0x14001cb60`
- `0x14001e950`
- `0x140020840`
- `0x140021348`
- `0x140022c54`
- `0x140091fbc`
- `0x140093278`
- `0x1400e2cb0`
- `0x1400e8c20`
- `0x1400e9c10`
- `0x14013e398`
- `0x14013eb50`
- `0x140184ce8`
- `0x1401dc278`
- `0x14026c96c`
- `0x14027f6c0`
- `0x140296f64`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140021721`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140021721`
- `ntoskrnl!PsGetThreadId` at `0x140021b23`
- `ntoskrnl!PsGetThreadId` at `0x140021cbd`
- `ntoskrnl!PsGetThreadId` at `0x140021d44`
- `ntoskrnl!PsGetThreadId` at `0x140021b23`
- `ntoskrnl!PsGetThreadId` at `0x140021cbd`
- `ntoskrnl!PsGetThreadId` at `0x140021d44`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400213e4`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400213e4`
- `ntoskrnl!KeBugCheckEx` at `0x1400219c7`
- `ntoskrnl!KeBugCheckEx` at `0x1400219c7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002141d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400215e9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002141d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400215e9`
- `win32kbase!UserDeleteAtom` at `0x1400216fe`
- `win32kbase!UserDeleteAtom` at `0x1400216fe`
- `win32kbase!HMPkheFromPhe` at `0x140021491`
- `win32kbase!HMPkheFromPhe` at `0x140021491`
- `win32kbase!UserAddAtomEx` at `0x1400216a1`
- `win32kbase!UserAddAtomEx` at `0x1400216a1`
- `win32kbase!GetDispInfo` at `0x140021788`
- `win32kbase!GetDispInfo` at `0x140021788`
- `win32kbase!HMLockObject` at `0x14002156b`
- `win32kbase!HMLockObject` at `0x14002156b`
- `win32kbase!HMUnlockObject` at `0x140021623`
- `win32kbase!HMUnlockObject` at `0x140021623`
- `win32kbase!Win32FreePool` at `0x140021a30`
- `WIN32K!W32GetUserSessionState` at `0x140021441`
- `WIN32K!W32GetUserSessionState` at `0x14002145e`
- `WIN32K!W32GetUserSessionState` at `0x14002146d`
- `WIN32K!W32GetUserSessionState` at `0x1400214f2`
- `WIN32K!W32GetUserSessionState` at `0x140021b35`
- `WIN32K!W32GetUserSessionState` at `0x140021ccf`
- `WIN32K!W32GetUserSessionState` at `0x140021d56`
- `WIN32K!W32GetUserSessionState` at `0x140021441`
- `WIN32K!W32GetUserSessionState` at `0x14002145e`
- `WIN32K!W32GetUserSessionState` at `0x14002146d`
- `WIN32K!W32GetUserSessionState` at `0x1400214f2`
- `WIN32K!W32GetUserSessionState` at `0x140021b35`
- `WIN32K!W32GetUserSessionState` at `0x140021ccf`
- `WIN32K!W32GetUserSessionState` at `0x140021d56`

## pseudocode

```c
__int64 __fastcall xxxBroadcastMessageEx(
        struct tagWND **a1,
        unsigned int a2,
        unsigned __int64 a3,
        ULONG_PTR *a4,
        unsigned int a5,
        union tagBROADCASTMSG *a6,
        int a7,
        unsigned int a8)
{
  unsigned __int64 v9; // r12
  struct tagTHREADINFO *v12; // rcx
  int v13; // edi
  __int64 v14; // rcx
  __int64 CurrentProcessWin32Process; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 UserSessionState; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  ULONG_PTR *v27; // r14
  ULONG_PTR v28; // r14
  __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // ebx
  ULONG_PTR *CurrentThreadWin32Thread; // rax
  ULONG_PTR v33; // r8
  ULONG_PTR *v34; // rcx
  __int64 v35; // rbx
  _WORD *v36; // rcx
  unsigned __int16 v37; // ax
  unsigned int WindowCompositedDpiContext; // eax
  __int64 v39; // r9
  char v40; // al
  char v41; // r12
  char v42; // al
  char v43; // r12
  ULONG_PTR *v44; // r9
  __int64 v45; // rdx
  unsigned __int64 v46; // r8
  __int64 v48; // rax
  char v49; // al
  char v50; // r12
  unsigned __int8 v51; // al
  __int64 v52; // rdi
  char v53; // bl
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // edx
  const char *v58; // rcx
  int v59; // r8d
  __int64 v60; // rcx
  unsigned int v61; // ecx
  unsigned __int8 v62; // al
  __int64 v63; // rdi
  char v64; // bl
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  int v68; // edx
  int v69; // r8d
  unsigned __int8 ThreadId; // al
  __int64 v71; // rdi
  char v72; // bl
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // rax
  int v76; // edx
  int v77; // r8d
  int BugCheckParameter4; // [rsp+20h] [rbp-99h]
  int v79; // [rsp+28h] [rbp-91h]
  ULONG_PTR v80[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v81; // [rsp+70h] [rbp-49h]
  __int64 v82; // [rsp+78h] [rbp-41h]
  _QWORD *v83; // [rsp+80h] [rbp-39h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v85; // [rsp+98h] [rbp-21h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+A0h] [rbp-19h] BYREF
  struct tagTHREADINFO *v87; // [rsp+B0h] [rbp-9h]
  __int64 v88; // [rsp+B8h] [rbp-1h]
  char v89; // [rsp+108h] [rbp+4Fh]
  char v90; // [rsp+108h] [rbp+4Fh]
  char v91; // [rsp+108h] [rbp+4Fh]

  v9 = a3;
  v12 = PtiCurrent();
  v87 = v12;
  if ( a2 - 1024 > 0xBBFF )
  {
    v13 = a7;
    if ( !a7 && (a2 == 21 || a2 == 26 || a2 == 29 || a2 == 295 || a2 == 794 || a2 - 804 <= 1) )
    {
      v13 = 1;
      a7 = 1;
    }
    if ( a1 )
    {
LABEL_4:
      v88 = BuildHwndList(a1[14], 2u);
      if ( v88 )
      {
        TraceLoggingBroadcastMessage((const struct tagWND *)a1, a2, v9, a5);
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v14);
        v81 = CurrentProcessWin32Process;
        if ( CurrentProcessWin32Process )
        {
          v16 = -*(_QWORD *)CurrentProcessWin32Process;
          v81 = CurrentProcessWin32Process & -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
        }
        v83 = (_QWORD *)(v88 + 32);
        v17 = *(_QWORD *)(v88 + 32);
        if ( v17 != 1 )
        {
          while ( 1 )
          {
            PsGetCurrentThreadWin32Thread(v16);
            v16 = *(_QWORD *)(W32GetUserSessionState(v19, v18) + 19704);
            if ( (unsigned __int64)(unsigned __int16)v17 < *(_QWORD *)(v16 + 8) )
            {
              UserSessionState = W32GetUserSessionState(v16, v20);
              v24 = *(_DWORD *)(W32GetUserSessionState(v23, v22) + 19728) * (unsigned int)(unsigned __int16)v17
                  + *(_QWORD *)(UserSessionState + 19720);
              v27 = (ULONG_PTR *)HMPkheFromPhe(v24);
              LOWORD(v17) = WORD1(v17) & 0x7FFF;
              if ( ((WORD1(v17) & 0x7FFF) == *(_WORD *)(v24 + 26)
                 || (_WORD)v17 == 0x7FFF
                 || !(_WORD)v17 && PsGetCurrentProcessWow64Process(v16, v25, v26))
                && (*(_BYTE *)(v24 + 25) & 1) == 0
                && *(_BYTE *)(v24 + 24) == 1 )
              {
                v28 = *v27;
                if ( v28 )
                {
                  v16 = *(_WORD *)(*(_QWORD *)(v28 + 40) + 42LL) & 0x2FFF;
                  if ( (_DWORD)v16 != 668 )
                  {
                    v29 = W32GetUserSessionState(v16, v25);
                    v16 = *(_QWORD *)(*(_QWORD *)(v28 + 136) + 8LL);
                    if ( *(_WORD *)(v29 + 41170) != *(_WORD *)v16 )
                    {
                      if ( a2 - 784 > 1
                        || (*(_BYTE *)(*(_QWORD *)(v28 + 40) + 31LL) & 0x10) != 0
                        || (v16 = 0,
                            (_InterlockedCompareExchange(
                               (volatile signed __int32 *)(*(_QWORD *)(v28 + 16) + 520LL),
                               0,
                               0)
                           & 0x800) != 0) )
                      {
                        if ( a8 == 1 )
                        {
                          if ( *(_DWORD *)(*(_QWORD *)(v28 + 40) + 236LL) != 1 )
                            goto LABEL_31;
                        }
                        else if ( a8 == 2 )
                        {
                          v48 = *(_QWORD *)(v28 + 40);
                          if ( *(_DWORD *)(v48 + 236) == 1 && (*(_BYTE *)(v48 + 232) & 0x40) == 0 )
                            goto LABEL_31;
                        }
                        if ( (*(_DWORD *)(v28 + 380) & 0x10) == 0
                          || (a2 != 126 || a4 != (ULONG_PTR *)1) && (a2 != 26 || v9 != 47) )
                        {
                          BugCheckParameter3[1] = v28;
                          BugCheckParameter3[0] = *((_QWORD *)v87 + 56);
                          *((_QWORD *)v87 + 56) = BugCheckParameter3;
                          HMLockObject(v28);
                          switch ( a5 )
                          {
                            case 0u:
                              xxxSendTransformableMessageTimeout((struct tagWND *)v28, a2, 0, 0, 0, a7, 1);
                              goto LABEL_27;
                            case 1u:
                              v31 = a7;
                              break;
                            case 2u:
                              if ( !*(_QWORD *)(v28 + 120) )
                                PostTransformableMessageIL((struct tagWND *)v28, a2, a7);
                              goto LABEL_27;
                            case 3u:
                              xxxSendMessageCallback(
                                (struct tagWND *)v28,
                                a2,
                                *(_QWORD *)a6,
                                *((_QWORD *)a6 + 1),
                                *((_DWORD *)a6 + 4),
                                a7,
                                1);
                              goto LABEL_27;
                            case 4u:
LABEL_26:
                              v31 = a7;
                              if ( xxxSendTransformableMessageTimeout(
                                     (struct tagWND *)v28,
                                     a2,
                                     *(_DWORD *)a6,
                                     *((_DWORD *)a6 + 1),
                                     *((_QWORD *)a6 + 1),
                                     a7,
                                     1)
                                || a5 != 6 )
                              {
                                goto LABEL_27;
                              }
                              break;
                            case 5u:
                              v60 = *(_QWORD *)(v28 + 16);
                              if ( *(_QWORD *)(v60 + 456) == v81
                                && (_InterlockedCompareExchange((volatile signed __int32 *)(v60 + 520), 0, 0) & 8) == 0 )
                              {
                                xxxSendTransformableMessageTimeout((struct tagWND *)v28, a2, 0, 0, 0, 1, 1);
                                goto LABEL_27;
                              }
                              v31 = a7;
LABEL_127:
                              v44 = a4;
                              v46 = v9;
                              v45 = a2;
                              goto LABEL_74;
                            case 6u:
                              goto LABEL_26;
                            default:
LABEL_27:
                              CurrentThreadWin32Thread = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v30);
                              if ( CurrentThreadWin32Thread )
                                v33 = *CurrentThreadWin32Thread;
                              else
                                v33 = 0;
                              v34 = *(ULONG_PTR **)(v33 + 448);
                              if ( v34 != BugCheckParameter3 )
                                KeBugCheckEx(0x164u, 0x3Bu, v33, (ULONG_PTR)BugCheckParameter3, 0);
                              *(_QWORD *)(v33 + 448) = *v34;
                              HMUnlockObject(v34[1]);
                              goto LABEL_31;
                          }
                          if ( a2 == 26 || a2 == 27 )
                          {
                            v35 = 0;
                            if ( a4 )
                            {
                              v36 = (_WORD *)a4[1];
                              if ( *v36 )
                              {
                                v37 = UserAddAtomEx(v36, 0, 2);
                                v35 = v37;
                                if ( !v37 )
                                  goto LABEL_27;
                              }
                              else
                              {
                                v35 = -1;
                              }
                            }
                            if ( !(unsigned int)PostEventMessageEx(
                                                  *(struct tagTHREADINFO **)(v28 + 16),
                                                  *(struct tagQ **)(*(_QWORD *)(v28 + 16) + 464LL),
                                                  9u,
                                                  (struct tagWND *)v28,
                                                  a2,
                                                  v9,
                                                  v35,
                                                  0)
                              && (unsigned __int64)(v35 + 1) > 1 )
                            {
                              UserDeleteAtom((unsigned __int16)v35);
                            }
                            goto LABEL_27;
                          }
                          if ( a2 != 126 )
                            goto LABEL_127;
                          GetDispInfo(v30);
                          WindowCompositedDpiContext = GetWindowCompositedDpiContext((const struct tagWND *)v28);
                          GetMonitorRectForDpi(v80, *(_QWORD *)(v39 + 96), (WindowCompositedDpiContext >> 8) & 0x1FF);
                          v82 = ((unsigned __int16)(WORD2(v80[1]) - WORD2(v80[0])) << 16)
                              | (unsigned __int16)(LOWORD(v80[1]) - LOWORD(v80[0]));
                          if ( a4 )
                          {
                            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                              || (v40 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                            {
                              v40 = 0;
                            }
                            v89 = v40;
                            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                              || (v41 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                            {
                              v41 = 0;
                            }
                            if ( v40 || v41 )
                            {
                              ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v28 + 16));
                              v71 = *(_QWORD *)v28;
                              v72 = ThreadId;
                              v75 = W32GetUserSessionState(v74, v73);
                              LOBYTE(v76) = v89;
                              LOBYTE(v77) = v41;
                              WPP_RECORDER_AND_TRACE_SF_qD(
                                *((_QWORD *)WPP_GLOBAL_Control + 3),
                                v76,
                                v77,
                                *(_QWORD *)(v75 + 69152),
                                5,
                                7,
                                15,
                                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                                v71,
                                v72);
                            }
                            PostEventMessageEx(
                              *(struct tagTHREADINFO **)(v28 + 16),
                              *(struct tagQ **)(*(_QWORD *)(v28 + 16) + 464LL),
                              9u,
                              (struct tagWND *)v28,
                              0x7Eu,
                              a3,
                              v82,
                              0);
                            goto LABEL_27;
                          }
                          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                            || (v42 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                          {
                            v42 = 0;
                          }
                          v90 = v42;
                          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                            || (v43 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                          {
                            v43 = 0;
                          }
                          if ( v42 || v43 )
                          {
                            v62 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v28 + 16));
                            v63 = *(_QWORD *)v28;
                            v64 = v62;
                            v67 = W32GetUserSessionState(v66, v65);
                            LOBYTE(v68) = v90;
                            LOBYTE(v69) = v43;
                            WPP_RECORDER_AND_TRACE_SF_qD(
                              *((_QWORD *)WPP_GLOBAL_Control + 3),
                              v68,
                              v69,
                              *(_QWORD *)(v67 + 69152),
                              5,
                              7,
                              14,
                              (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                              v63,
                              v64);
                            v31 = a7;
                          }
                          v44 = (ULONG_PTR *)v82;
                          v45 = 126;
                          v46 = a3;
LABEL_74:
                          xxxSendNotifyMessage(v28, v45, v46, v44, v31);
                          goto LABEL_27;
                        }
                        v16 = (unsigned __int64)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                          || (v49 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                        {
                          v49 = 0;
                        }
                        v91 = v49;
                        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                          || (v50 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                        {
                          v50 = 0;
                        }
                        if ( v49 || v50 )
                        {
                          v51 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v28 + 16));
                          v52 = *(_QWORD *)v28;
                          v53 = v51;
                          v56 = W32GetUserSessionState(v55, v54);
                          LOBYTE(v57) = v91;
                          v58 = "WM_DISPLAYCHANGE";
                          LOBYTE(v59) = v50;
                          if ( a2 != 126 )
                            v58 = "WM_SETTINGCHANGE (for SPI_SETWORKAREA)";
                          WPP_RECORDER_AND_TRACE_SF_sqd(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            v57,
                            v59,
                            *(_QWORD *)(v56 + 69152),
                            BugCheckParameter4,
                            v79,
                            13,
                            (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                            (__int64)v58,
                            v52,
                            v53);
                        }
                      }
                    }
                  }
                }
              }
            }
LABEL_31:
            v17 = *++v83;
            if ( *v83 == 1 )
              break;
            v9 = a3;
          }
        }
        FreeHwndList(v88);
        return 1;
      }
      return 0;
    }
    *(_OWORD *)v80 = 0;
    if ( a2 == 26 || a2 == 27 )
    {
      v85 = -1;
      *(_OWORD *)BugCheckParameter2 = 0;
      if ( a4 )
      {
        if ( !(unsigned int)CaptureBroadcastString(
                              (struct _LARGE_UNICODE_STRING *)v80,
                              (struct _LARGE_STRING *volatile)a4) )
        {
          if ( v85 != -1 )
            PopAndFreeW32ThreadLock(BugCheckParameter2);
          return 0;
        }
        Win32RawLockedItemBase<unsigned short,&void Win32FreePool(void *),1,1,1>::ManualLock<void>(
          (ULONG_PTR)BugCheckParameter2,
          v80[1]);
        a4 = v80;
      }
      xxxSystemBroadcastMessage(a2, v9, (__int64)a4, a5, a6, v13, a8);
      if ( v85 != -1 )
        PopAndFreeW32ThreadLock(BugCheckParameter2);
    }
    else
    {
      if ( a2 == 30 )
      {
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)v12 + 130, 0, 0) & 4) == 0 )
          return 0;
        goto LABEL_85;
      }
      if ( a2 == 42 )
      {
        v61 = 42;
      }
      else
      {
        if ( a2 - 712 >= 2 )
        {
LABEL_85:
          a1 = *(struct tagWND ***)(*(_QWORD *)(*((_QWORD *)v12 + 61) + 8LL) + 24LL);
          if ( a1 )
            goto LABEL_4;
          UserSetLastError(5);
          return 0;
        }
        v61 = a2;
      }
      xxxSystemBroadcastMessage(v61, v9, (__int64)a4, a5, a6, v13, a8);
    }
    return 1;
  }
  UserSetLastError(87);
  return 1;
}

```

## disassembly

```asm
0x140021348  mov     [rsp-8+arg_0], rbx
0x14002134d  mov     [rsp-8+arg_10], r8
0x140021352  push    rbp
0x140021353  push    rsi
0x140021354  push    rdi
0x140021355  push    r12
0x140021357  push    r13
0x140021359  push    r14
0x14002135b  push    r15
0x14002135d  lea     rbp, [rsp-7]
0x140021362  sub     rsp, 0C0h
0x140021369  mov     r13, r9
0x14002136c  mov     r12, r8
0x14002136f  mov     r15d, edx
0x140021372  mov     rbx, rcx
0x140021375  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002137a  mov     rcx, rax
0x14002137d  mov     [rbp+37h+var_40], rax
0x140021381  lea     eax, [r15-400h]
0x140021388  cmp     eax, 0BBFFh
0x14002138d  jbe     loc_140021DB7
0x140021393  mov     edi, [rbp+37h+arg_30]
0x140021396  xor     r14d, r14d
0x140021399  mov     esi, 1
0x14002139e  test    edi, edi
0x1400213a0  jz      loc_1400219D4
0x1400213a6  test    rbx, rbx
0x1400213a9  jz      loc_14002194D
0x1400213af  mov     rcx, [rbx+70h]
0x1400213b3  xor     r8d, r8d
0x1400213b6  mov     r9d, esi
0x1400213b9  lea     edx, [r8+2]
0x1400213bd  call    BuildHwndList
0x1400213c2  mov     [rbp+37h+var_38], rax
0x1400213c6  mov     rdi, rax
0x1400213c9  test    rax, rax
0x1400213cc  jz      loc_1400219AD
0x1400213d2  mov     r9d, [rbp+37h+arg_20]; unsigned int
0x1400213d6  mov     r8, r12; unsigned __int64
0x1400213d9  mov     edx, r15d; unsigned int
0x1400213dc  mov     rcx, rbx; struct tagWND *
0x1400213df  call    ?TraceLoggingBroadcastMessage@@YAXPEBUtagWND@@I_KI@Z; TraceLoggingBroadcastMessage(tagWND const *,uint,unsigned __int64,uint)
0x1400213e4  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400213eb  nop     dword ptr [rax+rax+00h]
0x1400213f0  mov     [rbp+37h+var_80], rax
0x1400213f4  test    rax, rax
0x1400213f7  jz      short loc_140021409
0x1400213f9  mov     rcx, [rax]
0x1400213fc  neg     rcx
0x1400213ff  sbb     rdx, rdx
0x140021402  and     rdx, rax
0x140021405  mov     [rbp+37h+var_80], rdx
0x140021409  add     rdi, 20h ; ' '
0x14002140d  mov     [rbp+37h+var_70], rdi
0x140021411  mov     rdi, [rdi]
0x140021414  cmp     rdi, rsi
0x140021417  jz      loc_1400218F8
0x14002141d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140021424  nop     dword ptr [rax+rax+00h]
0x140021429  test    rax, rax
0x14002142c  jz      short loc_14002143D
0x14002142e  mov     rax, [rax]
0x140021431  test    rax, rax
0x140021434  jz      short loc_14002143D
0x140021436  mov     rax, [rax+200h]
0x14002143d  movzx   r14d, di
0x140021441  call    cs:__imp_W32GetUserSessionState
0x140021448  nop     dword ptr [rax+rax+00h]
0x14002144d  mov     rcx, [rax+4CF8h]
0x140021454  cmp     r14, [rcx+8]
0x140021458  jnb     loc_14002162F
0x14002145e  call    cs:__imp_W32GetUserSessionState
0x140021465  nop     dword ptr [rax+rax+00h]
0x14002146a  mov     rbx, rax
0x14002146d  call    cs:__imp_W32GetUserSessionState
0x140021474  nop     dword ptr [rax+rax+00h]
0x140021479  mov     rbx, [rbx+4D08h]
0x140021480  imul    r14d, [rax+4D10h]
0x140021488  mov     ecx, r14d
0x14002148b  add     rbx, rcx
0x14002148e  mov     rcx, rbx
0x140021491  call    cs:__imp_HMPkheFromPhe
0x140021498  nop     dword ptr [rax+rax+00h]
0x14002149d  shr     rdi, 10h
0x1400214a1  mov     r14, rax
0x1400214a4  mov     eax, 7FFFh
0x1400214a9  and     di, ax
0x1400214ac  cmp     di, [rbx+1Ah]
0x1400214b0  jnz     loc_14002170F
0x1400214b6  xor     edi, edi
0x1400214b8  test    [rbx+19h], sil
0x1400214bc  jnz     loc_14002162F
0x1400214c2  cmp     [rbx+18h], sil
0x1400214c6  jnz     loc_14002162F
0x1400214cc  mov     r14, [r14]
0x1400214cf  test    r14, r14
0x1400214d2  jz      loc_14002162F
0x1400214d8  mov     rax, [r14+28h]
0x1400214dc  movzx   ecx, word ptr [rax+2Ah]
0x1400214e0  and     ecx, 0FFFF2FFFh
0x1400214e6  cmp     ecx, 29Ch
0x1400214ec  jz      loc_14002162F
0x1400214f2  call    cs:__imp_W32GetUserSessionState
0x1400214f9  nop     dword ptr [rax+rax+00h]
0x1400214fe  movzx   edx, word ptr [rax+0A0D2h]
0x140021505  mov     rax, [r14+88h]
0x14002150c  mov     rcx, [rax+8]
0x140021510  cmp     dx, [rcx]
0x140021513  jz      loc_14002162F
0x140021519  lea     eax, [r15-310h]
0x140021520  cmp     eax, esi
0x140021522  jbe     loc_14002173D
0x140021528  cmp     [rbp+37h+arg_38], esi
0x14002152b  jz      loc_14002176A
0x140021531  cmp     [rbp+37h+arg_38], 2
0x140021535  jz      loc_140021A87
0x14002153b  mov     eax, [r14+17Ch]
0x140021542  test    al, 10h
0x140021544  jnz     loc_140021AA9
0x14002154a  mov     rcx, [rbp+37h+var_40]
0x14002154e  mov     [rbp+37h+var_48], r14
0x140021552  mov     rax, [rcx+1C0h]
0x140021559  mov     [rbp+37h+BugCheckParameter3], rax
0x14002155d  lea     rax, [rbp+37h+BugCheckParameter3]
0x140021561  mov     [rcx+1C0h], rax
0x140021568  mov     rcx, r14
0x14002156b  call    cs:__imp_HMLockObject
0x140021572  nop     dword ptr [rax+rax+00h]
0x140021577  mov     eax, [rbp+37h+arg_20]
0x14002157a  test    eax, eax
0x14002157c  jz      loc_14002191F
0x140021582  sub     eax, esi
0x140021584  jz      loc_140021673
0x14002158a  sub     eax, esi
0x14002158c  jz      loc_140021650
0x140021592  sub     eax, esi
0x140021594  jz      loc_140021C1B
0x14002159a  sub     eax, esi
0x14002159c  jz      short loc_1400215AA
0x14002159e  sub     eax, esi
0x1400215a0  jz      loc_140021B9A
0x1400215a6  cmp     eax, esi
0x1400215a8  jnz     short loc_1400215E9
0x1400215aa  mov     rcx, [rbp+37h+arg_28]
0x1400215ae  mov     r9, r13
0x1400215b1  mov     ebx, [rbp+37h+arg_30]
0x1400215b4  mov     r8, r12
0x1400215b7  mov     [rsp+0F0h+var_B0], esi; int
0x1400215bb  mov     edx, r15d; unsigned int
0x1400215be  mov     dword ptr [rsp+0F0h+var_B8], ebx; int
0x1400215c2  mov     rax, [rcx+8]
0x1400215c6  mov     qword ptr [rsp+0F0h+var_C0], rax; __int64
0x1400215cb  mov     eax, [rcx+4]
0x1400215ce  mov     dword ptr [rsp+0F0h+var_C8], eax; int
0x1400215d2  mov     eax, [rcx]
0x1400215d4  mov     rcx, r14; struct tagWND *
0x1400215d7  mov     dword ptr [rsp+0F0h+BugCheckParameter4], eax; int
0x1400215db  call    xxxSendTransformableMessageTimeout
0x1400215e0  test    rax, rax
0x1400215e3  jz      loc_1400218E9
0x1400215e9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400215f0  nop     dword ptr [rax+rax+00h]
0x1400215f5  test    rax, rax
0x1400215f8  jz      loc_140021DAF
0x1400215fe  mov     r8, [rax]; BugCheckParameter2
0x140021601  mov     rcx, [r8+1C0h]
0x140021608  lea     rax, [rbp+37h+BugCheckParameter3]
0x14002160c  cmp     rcx, rax
0x14002160f  jnz     loc_1400219B4
0x140021615  mov     rax, [rcx]
0x140021618  mov     [r8+1C0h], rax
0x14002161f  mov     rcx, [rcx+8]
0x140021623  call    cs:__imp_HMUnlockObject
0x14002162a  nop     dword ptr [rax+rax+00h]
0x14002162f  mov     r14, [rbp+37h+var_70]
0x140021633  add     r14, 8
0x140021637  mov     [rbp+37h+var_70], r14
0x14002163b  mov     rdi, [r14]
0x14002163e  cmp     rdi, rsi
0x140021641  jz      loc_1400218F8
0x140021647  mov     r12, [rbp+37h+arg_10]
0x14002164b  jmp     loc_14002141D
0x140021650  cmp     [r14+78h], rdi
0x140021654  jnz     short loc_1400215E9
0x140021656  mov     eax, [rbp+37h+arg_30]
0x140021659  mov     r9, r13
0x14002165c  mov     r8, r12
0x14002165f  mov     dword ptr [rsp+0F0h+BugCheckParameter4], eax; int
0x140021663  mov     edx, r15d; unsigned int
0x140021666  mov     rcx, r14; struct tagWND *
0x140021669  call    _PostTransformableMessageIL
0x14002166e  jmp     loc_1400215E9
0x140021673  mov     ebx, [rbp+37h+arg_30]
0x140021676  mov     eax, r15d
0x140021679  sub     eax, 1Ah
0x14002167c  jz      short loc_140021686
0x14002167e  sub     eax, esi
0x140021680  jnz     loc_14002177F
0x140021686  mov     rbx, rdi
0x140021689  test    r13, r13
0x14002168c  jz      short loc_1400216B9
0x14002168e  mov     rcx, [r13+8]
0x140021692  cmp     [rcx], di
0x140021695  jz      loc_140021871
0x14002169b  xor     edx, edx
0x14002169d  lea     r8d, [rdx+2]
0x1400216a1  call    cs:__imp_UserAddAtomEx
0x1400216a8  nop     dword ptr [rax+rax+00h]
0x1400216ad  movzx   ebx, ax
0x1400216b0  test    rbx, rbx
0x1400216b3  jz      loc_1400215E9
0x1400216b9  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x1400216bd  mov     r9, r14; struct tagWND *
0x1400216c0  mov     [rsp+0F0h+var_B8], rdi; struct tagINPUT_MESSAGE_SOURCE *
0x1400216c5  mov     r8d, 9; unsigned int
0x1400216cb  mov     qword ptr [rsp+0F0h+var_C0], rbx; __int64
0x1400216d0  mov     [rsp+0F0h+var_C8], r12; unsigned __int64
0x1400216d5  mov     rdx, [rcx+1D0h]; struct tagQ *
0x1400216dc  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r15d; unsigned int
0x1400216e1  call    ?PostEventMessageEx@@YAHPEAUtagTHREADINFO@@PEAUtagQ@@KPEAUtagWND@@I_K_JPEAUtagINPUT_MESSAGE_SOURCE@@@Z; PostEventMessageEx(tagTHREADINFO *,tagQ *,ulong,tagWND *,uint,unsigned __int64,__int64,tagINPUT_MESSAGE_SOURCE *)
0x1400216e6  test    eax, eax
0x1400216e8  jnz     loc_1400215E9
0x1400216ee  lea     rax, [rbx+1]
0x1400216f2  cmp     rax, rsi
0x1400216f5  jbe     loc_1400215E9
0x1400216fb  movzx   ecx, bx
0x1400216fe  call    cs:__imp_UserDeleteAtom
0x140021705  nop     dword ptr [rax+rax+00h]
0x14002170a  jmp     loc_1400215E9
0x14002170f  cmp     di, ax
0x140021712  jz      loc_1400214B6
0x140021718  test    di, di
0x14002171b  jnz     loc_14002162F
0x140021721  call    cs:__imp_PsGetCurrentProcessWow64Process
0x140021728  nop     dword ptr [rax+rax+00h]
0x14002172d  xor     edi, edi
0x14002172f  test    rax, rax
0x140021732  jz      loc_14002162F
0x140021738  jmp     loc_1400214B8
0x14002173d  mov     rax, [r14+28h]
0x140021741  test    byte ptr [rax+1Fh], 10h
0x140021745  jnz     loc_140021528
0x14002174b  mov     rdx, [r14+10h]
0x14002174f  mov     ecx, edi
0x140021751  xor     eax, eax
0x140021753  lock cmpxchg [rdx+208h], ecx
0x14002175b  bt      eax, 0Bh
0x14002175f  jnb     loc_14002162F
0x140021765  jmp     loc_140021528
0x14002176a  mov     rax, [r14+28h]
0x14002176e  cmp     [rax+0ECh], esi
0x140021774  jnz     loc_14002162F
0x14002177a  jmp     loc_14002153B
0x14002177f  cmp     eax, 63h ; 'c'
0x140021782  jnz     loc_140021C0D
0x140021788  call    cs:__imp_GetDispInfo
0x14002178f  nop     dword ptr [rax+rax+00h]
0x140021794  mov     rcx, r14; struct tagWND *
0x140021797  mov     r9, rax
0x14002179a  call    ?GetWindowCompositedDpiContext@@YAKPEBUtagWND@@@Z; GetWindowCompositedDpiContext(tagWND const *)
0x14002179f  mov     rdx, [r9+60h]
0x1400217a3  lea     rcx, [rbp+37h+var_90]
0x1400217a7  shr     eax, 8
0x1400217aa  mov     r8d, 1FFh
0x1400217b0  and     r8w, ax
0x1400217b4  call    GetMonitorRectForDpi
0x1400217b9  movzx   eax, word ptr [rbp+37h+var_90+0Ch]
0x1400217bd  sub     ax, word ptr [rbp+37h+var_90+4]
0x1400217c1  movzx   edx, ax
0x1400217c4  movzx   eax, word ptr [rbp+37h+var_90+8]
0x1400217c8  sub     ax, word ptr [rbp+37h+var_90]
0x1400217cc  movzx   eax, ax
0x1400217cf  shl     edx, 10h
0x1400217d2  or      eax, edx
0x1400217d4  cdqe
0x1400217d6  mov     [rbp+37h+var_78], rax
0x1400217da  test    r13, r13
0x1400217dd  jz      loc_14002187A
0x1400217e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217ea  lea     rax, WPP_GLOBAL_Control
0x1400217f1  cmp     rcx, rax
0x1400217f4  jz      short loc_140021801
0x1400217f6  mov     eax, [rcx+2Ch]
0x1400217f9  test    al, 40h
0x1400217fb  jnz     loc_140021D2B
0x140021801  mov     al, dil
0x140021804  lea     rdx, WPP_RECORDER_INITIALIZED
0x14002180b  mov     [rbp+37h+arg_8], al
0x14002180e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140021815  jz      short loc_140021820
0x140021817  mov     r12b, sil
0x14002181a  cmp     [rcx+48h], di
0x14002181e  jnz     short loc_140021823
0x140021820  mov     r12b, dil
0x140021823  test    al, al
0x140021825  jnz     loc_140021D3D
0x14002182b  test    r12b, r12b
0x14002182e  jnz     loc_140021D3D
0x140021834  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x140021838  mov     r9, r14; struct tagWND *
  ... truncated ...
```
