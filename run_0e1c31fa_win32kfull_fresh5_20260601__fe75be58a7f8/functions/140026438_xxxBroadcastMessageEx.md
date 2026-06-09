# xxxBroadcastMessageEx

- ea: `0x140026438`
- end: `0x140026ebb`
- name: `xxxBroadcastMessageEx`
- size: `2691`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, struct _LARGE_STRING *volatile, unsigned int, __int64, int, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1401483d8`
- `0x14020cae0`
- `0x140236140`

## callees

- `0x140019e3c`
- `0x14001b0f8`
- `0x140020370`
- `0x1400208b0`
- `0x140021d30`
- `0x140023ac0`
- `0x140025930`
- `0x140026438`
- `0x140027d44`
- `0x1400bcaa0`
- `0x1400c2a10`
- `0x1400c3a60`
- `0x1401483d8`
- `0x140148b90`
- `0x140177ee8`
- `0x1401def48`
- `0x14026960c`
- `0x14027d500`
- `0x140294a14`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140026811`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x140026811`
- `ntoskrnl!PsGetThreadId` at `0x140026c13`
- `ntoskrnl!PsGetThreadId` at `0x140026dad`
- `ntoskrnl!PsGetThreadId` at `0x140026e34`
- `ntoskrnl!PsGetThreadId` at `0x140026c13`
- `ntoskrnl!PsGetThreadId` at `0x140026dad`
- `ntoskrnl!PsGetThreadId` at `0x140026e34`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400264d4`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400264d4`
- `ntoskrnl!KeBugCheckEx` at `0x140026ab7`
- `ntoskrnl!KeBugCheckEx` at `0x140026ab7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002650d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400266d9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002650d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400266d9`
- `win32kbase!UserDeleteAtom` at `0x1400267ee`
- `win32kbase!UserDeleteAtom` at `0x1400267ee`
- `win32kbase!HMPkheFromPhe` at `0x140026581`
- `win32kbase!HMPkheFromPhe` at `0x140026581`
- `win32kbase!UserAddAtomEx` at `0x140026791`
- `win32kbase!UserAddAtomEx` at `0x140026791`
- `win32kbase!GetDispInfo` at `0x140026878`
- `win32kbase!GetDispInfo` at `0x140026878`
- `win32kbase!HMLockObject` at `0x14002665b`
- `win32kbase!HMLockObject` at `0x14002665b`
- `win32kbase!HMUnlockObject` at `0x140026713`
- `win32kbase!HMUnlockObject` at `0x140026713`
- `win32kbase!Win32FreePool` at `0x140026b20`
- `WIN32K!W32GetUserSessionState` at `0x140026531`
- `WIN32K!W32GetUserSessionState` at `0x14002654e`
- `WIN32K!W32GetUserSessionState` at `0x14002655d`
- `WIN32K!W32GetUserSessionState` at `0x1400265e2`
- `WIN32K!W32GetUserSessionState` at `0x140026c25`
- `WIN32K!W32GetUserSessionState` at `0x140026dbf`
- `WIN32K!W32GetUserSessionState` at `0x140026e46`
- `WIN32K!W32GetUserSessionState` at `0x140026531`
- `WIN32K!W32GetUserSessionState` at `0x14002654e`
- `WIN32K!W32GetUserSessionState` at `0x14002655d`
- `WIN32K!W32GetUserSessionState` at `0x1400265e2`
- `WIN32K!W32GetUserSessionState` at `0x140026c25`
- `WIN32K!W32GetUserSessionState` at `0x140026dbf`
- `WIN32K!W32GetUserSessionState` at `0x140026e46`

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
  __int64 v18; // rcx
  __int64 UserSessionState; // rbx
  __int64 v20; // rcx
  __int64 v21; // rbx
  ULONG_PTR *v22; // r14
  ULONG_PTR v23; // r14
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // ebx
  ULONG_PTR *CurrentThreadWin32Thread; // rax
  ULONG_PTR v28; // r8
  ULONG_PTR *v29; // rcx
  __int64 v30; // rbx
  _WORD *v31; // rcx
  unsigned __int16 v32; // ax
  unsigned int WindowCompositedDpiContext; // eax
  __int64 v34; // r9
  char v35; // al
  char v36; // r12
  char v37; // al
  char v38; // r12
  ULONG_PTR *v39; // r9
  __int64 v40; // rdx
  unsigned __int64 v41; // r8
  __int64 v43; // rax
  char v44; // al
  char v45; // r12
  unsigned __int8 v46; // al
  __int64 v47; // rdi
  char v48; // bl
  __int64 v49; // rcx
  __int64 v50; // rax
  int v51; // edx
  const char *v52; // rcx
  int v53; // r8d
  __int64 v54; // rcx
  unsigned int v55; // ecx
  unsigned __int8 v56; // al
  __int64 v57; // rdi
  char v58; // bl
  __int64 v59; // rcx
  __int64 v60; // rax
  int v61; // edx
  int v62; // r8d
  unsigned __int8 ThreadId; // al
  __int64 v64; // rdi
  char v65; // bl
  __int64 v66; // rcx
  __int64 v67; // rax
  int v68; // edx
  int v69; // r8d
  int BugCheckParameter4; // [rsp+20h] [rbp-99h]
  int v71; // [rsp+28h] [rbp-91h]
  ULONG_PTR v72[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v73; // [rsp+70h] [rbp-49h]
  __int64 v74; // [rsp+78h] [rbp-41h]
  _QWORD *v75; // [rsp+80h] [rbp-39h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v77; // [rsp+98h] [rbp-21h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+A0h] [rbp-19h] BYREF
  struct tagTHREADINFO *v79; // [rsp+B0h] [rbp-9h]
  __int64 v80; // [rsp+B8h] [rbp-1h]
  char v81; // [rsp+108h] [rbp+4Fh]
  char v82; // [rsp+108h] [rbp+4Fh]
  char v83; // [rsp+108h] [rbp+4Fh]

  v9 = a3;
  v12 = PtiCurrent();
  v79 = v12;
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
      v80 = BuildHwndList(a1[14], 2u);
      if ( v80 )
      {
        TraceLoggingBroadcastMessage((const struct tagWND *)a1, a2, v9, a5);
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v14);
        v73 = CurrentProcessWin32Process;
        if ( CurrentProcessWin32Process )
        {
          v16 = -*(_QWORD *)CurrentProcessWin32Process;
          v73 = CurrentProcessWin32Process & -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
        }
        v75 = (_QWORD *)(v80 + 32);
        v17 = *(_QWORD *)(v80 + 32);
        if ( v17 != 1 )
        {
          while ( 1 )
          {
            PsGetCurrentThreadWin32Thread(v16);
            v16 = *(_QWORD *)(W32GetUserSessionState(v18) + 19704);
            if ( (unsigned __int64)(unsigned __int16)v17 < *(_QWORD *)(v16 + 8) )
            {
              UserSessionState = W32GetUserSessionState(v16);
              v21 = *(_DWORD *)(W32GetUserSessionState(v20) + 19728) * (unsigned int)(unsigned __int16)v17
                  + *(_QWORD *)(UserSessionState + 19720);
              v22 = (ULONG_PTR *)HMPkheFromPhe(v21);
              LOWORD(v17) = WORD1(v17) & 0x7FFF;
              if ( ((WORD1(v17) & 0x7FFF) == *(_WORD *)(v21 + 26)
                 || (_WORD)v17 == 0x7FFF
                 || !(_WORD)v17 && PsGetCurrentProcessWow64Process())
                && (*(_BYTE *)(v21 + 25) & 1) == 0
                && *(_BYTE *)(v21 + 24) == 1 )
              {
                v23 = *v22;
                if ( v23 )
                {
                  v16 = *(_WORD *)(*(_QWORD *)(v23 + 40) + 42LL) & 0x2FFF;
                  if ( (_DWORD)v16 != 668 )
                  {
                    v24 = W32GetUserSessionState(v16);
                    v16 = *(_QWORD *)(*(_QWORD *)(v23 + 136) + 8LL);
                    if ( *(_WORD *)(v24 + 41170) != *(_WORD *)v16 )
                    {
                      if ( a2 - 784 > 1
                        || (*(_BYTE *)(*(_QWORD *)(v23 + 40) + 31LL) & 0x10) != 0
                        || (v16 = 0,
                            (_InterlockedCompareExchange(
                               (volatile signed __int32 *)(*(_QWORD *)(v23 + 16) + 520LL),
                               0,
                               0)
                           & 0x800) != 0) )
                      {
                        if ( a8 == 1 )
                        {
                          if ( *(_DWORD *)(*(_QWORD *)(v23 + 40) + 236LL) != 1 )
                            goto LABEL_31;
                        }
                        else if ( a8 == 2 )
                        {
                          v43 = *(_QWORD *)(v23 + 40);
                          if ( *(_DWORD *)(v43 + 236) == 1 && (*(_BYTE *)(v43 + 232) & 0x40) == 0 )
                            goto LABEL_31;
                        }
                        if ( (*(_DWORD *)(v23 + 380) & 0x10) == 0
                          || (a2 != 126 || a4 != (ULONG_PTR *)1) && (a2 != 26 || v9 != 47) )
                        {
                          BugCheckParameter3[1] = v23;
                          BugCheckParameter3[0] = *((_QWORD *)v79 + 56);
                          *((_QWORD *)v79 + 56) = BugCheckParameter3;
                          HMLockObject(v23);
                          switch ( a5 )
                          {
                            case 0u:
                              xxxSendTransformableMessageTimeout((struct tagWND *)v23, a2, 0, 0, 0, a7, 1);
                              goto LABEL_27;
                            case 1u:
                              v26 = a7;
                              break;
                            case 2u:
                              if ( !*(_QWORD *)(v23 + 120) )
                                PostTransformableMessageIL((struct tagWND *)v23, a2, a7);
                              goto LABEL_27;
                            case 3u:
                              xxxSendMessageCallback(
                                (struct tagWND *)v23,
                                a2,
                                *(_QWORD *)a6,
                                *((_QWORD *)a6 + 1),
                                *((_DWORD *)a6 + 4),
                                a7,
                                1);
                              goto LABEL_27;
                            case 4u:
LABEL_26:
                              v26 = a7;
                              if ( xxxSendTransformableMessageTimeout(
                                     (struct tagWND *)v23,
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
                              v54 = *(_QWORD *)(v23 + 16);
                              if ( *(_QWORD *)(v54 + 456) == v73
                                && (_InterlockedCompareExchange((volatile signed __int32 *)(v54 + 520), 0, 0) & 8) == 0 )
                              {
                                xxxSendTransformableMessageTimeout((struct tagWND *)v23, a2, 0, 0, 0, 1, 1);
                                goto LABEL_27;
                              }
                              v26 = a7;
LABEL_127:
                              v39 = a4;
                              v41 = v9;
                              v40 = a2;
                              goto LABEL_74;
                            case 6u:
                              goto LABEL_26;
                            default:
LABEL_27:
                              CurrentThreadWin32Thread = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v25);
                              if ( CurrentThreadWin32Thread )
                                v28 = *CurrentThreadWin32Thread;
                              else
                                v28 = 0;
                              v29 = *(ULONG_PTR **)(v28 + 448);
                              if ( v29 != BugCheckParameter3 )
                                KeBugCheckEx(0x164u, 0x3Bu, v28, (ULONG_PTR)BugCheckParameter3, 0);
                              *(_QWORD *)(v28 + 448) = *v29;
                              HMUnlockObject(v29[1]);
                              goto LABEL_31;
                          }
                          if ( a2 == 26 || a2 == 27 )
                          {
                            v30 = 0;
                            if ( a4 )
                            {
                              v31 = (_WORD *)a4[1];
                              if ( *v31 )
                              {
                                v32 = UserAddAtomEx(v31, 0, 2);
                                v30 = v32;
                                if ( !v32 )
                                  goto LABEL_27;
                              }
                              else
                              {
                                v30 = -1;
                              }
                            }
                            if ( !(unsigned int)PostEventMessageEx(
                                                  *(struct tagTHREADINFO **)(v23 + 16),
                                                  *(struct tagQ **)(*(_QWORD *)(v23 + 16) + 464LL),
                                                  9u,
                                                  (struct tagWND *)v23,
                                                  a2,
                                                  v9,
                                                  v30,
                                                  0)
                              && (unsigned __int64)(v30 + 1) > 1 )
                            {
                              UserDeleteAtom((unsigned __int16)v30);
                            }
                            goto LABEL_27;
                          }
                          if ( a2 != 126 )
                            goto LABEL_127;
                          GetDispInfo(v25);
                          WindowCompositedDpiContext = GetWindowCompositedDpiContext((const struct tagWND *)v23);
                          GetMonitorRectForDpi(v72, *(_QWORD *)(v34 + 96), (WindowCompositedDpiContext >> 8) & 0x1FF);
                          v74 = ((unsigned __int16)(WORD2(v72[1]) - WORD2(v72[0])) << 16)
                              | (unsigned __int16)(LOWORD(v72[1]) - LOWORD(v72[0]));
                          if ( a4 )
                          {
                            if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                              || (v35 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                            {
                              v35 = 0;
                            }
                            v81 = v35;
                            if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                              || (v36 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                            {
                              v36 = 0;
                            }
                            if ( v35 || v36 )
                            {
                              ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v23 + 16));
                              v64 = *(_QWORD *)v23;
                              v65 = ThreadId;
                              v67 = W32GetUserSessionState(v66);
                              LOBYTE(v68) = v81;
                              LOBYTE(v69) = v36;
                              WPP_RECORDER_AND_TRACE_SF_qD(
                                *((_QWORD *)WPP_GLOBAL_Control + 3),
                                v68,
                                v69,
                                *(_QWORD *)(v67 + 69152),
                                5,
                                7,
                                15,
                                (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                                v64,
                                v65);
                            }
                            PostEventMessageEx(
                              *(struct tagTHREADINFO **)(v23 + 16),
                              *(struct tagQ **)(*(_QWORD *)(v23 + 16) + 464LL),
                              9u,
                              (struct tagWND *)v23,
                              0x7Eu,
                              a3,
                              v74,
                              0);
                            goto LABEL_27;
                          }
                          if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                            || (v37 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                          {
                            v37 = 0;
                          }
                          v82 = v37;
                          if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                            || (v38 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                          {
                            v38 = 0;
                          }
                          if ( v37 || v38 )
                          {
                            v56 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v23 + 16));
                            v57 = *(_QWORD *)v23;
                            v58 = v56;
                            v60 = W32GetUserSessionState(v59);
                            LOBYTE(v61) = v82;
                            LOBYTE(v62) = v38;
                            WPP_RECORDER_AND_TRACE_SF_qD(
                              *((_QWORD *)WPP_GLOBAL_Control + 3),
                              v61,
                              v62,
                              *(_QWORD *)(v60 + 69152),
                              5,
                              7,
                              14,
                              (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                              v57,
                              v58);
                            v26 = a7;
                          }
                          v39 = (ULONG_PTR *)v74;
                          v40 = 126;
                          v41 = a3;
LABEL_74:
                          xxxSendNotifyMessage(v23, v40, v41, v39, v26);
                          goto LABEL_27;
                        }
                        v16 = (unsigned __int64)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) == 0
                          || (v44 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
                        {
                          v44 = 0;
                        }
                        v83 = v44;
                        if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
                          || (v45 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
                        {
                          v45 = 0;
                        }
                        if ( v44 || v45 )
                        {
                          v46 = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v23 + 16));
                          v47 = *(_QWORD *)v23;
                          v48 = v46;
                          v50 = W32GetUserSessionState(v49);
                          LOBYTE(v51) = v83;
                          v52 = "WM_DISPLAYCHANGE";
                          LOBYTE(v53) = v45;
                          if ( a2 != 126 )
                            v52 = "WM_SETTINGCHANGE (for SPI_SETWORKAREA)";
                          WPP_RECORDER_AND_TRACE_SF_sqd(
                            *((_QWORD *)WPP_GLOBAL_Control + 3),
                            v51,
                            v53,
                            *(_QWORD *)(v50 + 69152),
                            BugCheckParameter4,
                            v71,
                            13,
                            (__int64)WPP_d89d491cd7523c23c97566722a0a71eb_Traceguids,
                            (__int64)v52,
                            v47,
                            v48);
                        }
                      }
                    }
                  }
                }
              }
            }
LABEL_31:
            v17 = *++v75;
            if ( *v75 == 1 )
              break;
            v9 = a3;
          }
        }
        FreeHwndList(v80);
        return 1;
      }
      return 0;
    }
    *(_OWORD *)v72 = 0;
    if ( a2 == 26 || a2 == 27 )
    {
      v77 = -1;
      *(_OWORD *)BugCheckParameter2 = 0;
      if ( a4 )
      {
        if ( !(unsigned int)CaptureBroadcastString(
                              (struct _LARGE_UNICODE_STRING *)v72,
                              (struct _LARGE_STRING *volatile)a4) )
        {
          if ( v77 != -1 )
            PopAndFreeW32ThreadLock(BugCheckParameter2);
          return 0;
        }
        Win32RawLockedItemBase<unsigned short,&void Win32FreePool(void *),1,1,1>::ManualLock<void>(
          (ULONG_PTR)BugCheckParameter2,
          v72[1]);
        a4 = v72;
      }
      xxxSystemBroadcastMessage(a2, v9, (__int64)a4, a5, a6, v13, a8);
      if ( v77 != -1 )
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
        v55 = 42;
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
        v55 = a2;
      }
      xxxSystemBroadcastMessage(v55, v9, (__int64)a4, a5, a6, v13, a8);
    }
    return 1;
  }
  UserSetLastError(87);
  return 1;
}

```

## disassembly

```asm
0x140026438  mov     [rsp-8+arg_0], rbx
0x14002643d  mov     [rsp-8+arg_10], r8
0x140026442  push    rbp
0x140026443  push    rsi
0x140026444  push    rdi
0x140026445  push    r12
0x140026447  push    r13
0x140026449  push    r14
0x14002644b  push    r15
0x14002644d  lea     rbp, [rsp-7]
0x140026452  sub     rsp, 0C0h
0x140026459  mov     r13, r9
0x14002645c  mov     r12, r8
0x14002645f  mov     r15d, edx
0x140026462  mov     rbx, rcx
0x140026465  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14002646a  mov     rcx, rax
0x14002646d  mov     [rbp+37h+var_40], rax
0x140026471  lea     eax, [r15-400h]
0x140026478  cmp     eax, 0BBFFh
0x14002647d  jbe     loc_140026EA7
0x140026483  mov     edi, [rbp+37h+arg_30]
0x140026486  xor     r14d, r14d
0x140026489  mov     esi, 1
0x14002648e  test    edi, edi
0x140026490  jz      loc_140026AC4
0x140026496  test    rbx, rbx
0x140026499  jz      loc_140026A3D
0x14002649f  mov     rcx, [rbx+70h]
0x1400264a3  xor     r8d, r8d
0x1400264a6  mov     r9d, esi
0x1400264a9  lea     edx, [r8+2]
0x1400264ad  call    BuildHwndList
0x1400264b2  mov     [rbp+37h+var_38], rax
0x1400264b6  mov     rdi, rax
0x1400264b9  test    rax, rax
0x1400264bc  jz      loc_140026A9D
0x1400264c2  mov     r9d, [rbp+37h+arg_20]; unsigned int
0x1400264c6  mov     r8, r12; unsigned __int64
0x1400264c9  mov     edx, r15d; unsigned int
0x1400264cc  mov     rcx, rbx; struct tagWND *
0x1400264cf  call    ?TraceLoggingBroadcastMessage@@YAXPEBUtagWND@@I_KI@Z; TraceLoggingBroadcastMessage(tagWND const *,uint,unsigned __int64,uint)
0x1400264d4  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400264db  nop     dword ptr [rax+rax+00h]
0x1400264e0  mov     [rbp+37h+var_80], rax
0x1400264e4  test    rax, rax
0x1400264e7  jz      short loc_1400264F9
0x1400264e9  mov     rcx, [rax]
0x1400264ec  neg     rcx
0x1400264ef  sbb     rdx, rdx
0x1400264f2  and     rdx, rax
0x1400264f5  mov     [rbp+37h+var_80], rdx
0x1400264f9  add     rdi, 20h ; ' '
0x1400264fd  mov     [rbp+37h+var_70], rdi
0x140026501  mov     rdi, [rdi]
0x140026504  cmp     rdi, rsi
0x140026507  jz      loc_1400269E8
0x14002650d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140026514  nop     dword ptr [rax+rax+00h]
0x140026519  test    rax, rax
0x14002651c  jz      short loc_14002652D
0x14002651e  mov     rax, [rax]
0x140026521  test    rax, rax
0x140026524  jz      short loc_14002652D
0x140026526  mov     rax, [rax+200h]
0x14002652d  movzx   r14d, di
0x140026531  call    cs:__imp_W32GetUserSessionState
0x140026538  nop     dword ptr [rax+rax+00h]
0x14002653d  mov     rcx, [rax+4CF8h]
0x140026544  cmp     r14, [rcx+8]
0x140026548  jnb     loc_14002671F
0x14002654e  call    cs:__imp_W32GetUserSessionState
0x140026555  nop     dword ptr [rax+rax+00h]
0x14002655a  mov     rbx, rax
0x14002655d  call    cs:__imp_W32GetUserSessionState
0x140026564  nop     dword ptr [rax+rax+00h]
0x140026569  mov     rbx, [rbx+4D08h]
0x140026570  imul    r14d, [rax+4D10h]
0x140026578  mov     ecx, r14d
0x14002657b  add     rbx, rcx
0x14002657e  mov     rcx, rbx
0x140026581  call    cs:__imp_HMPkheFromPhe
0x140026588  nop     dword ptr [rax+rax+00h]
0x14002658d  shr     rdi, 10h
0x140026591  mov     r14, rax
0x140026594  mov     eax, 7FFFh
0x140026599  and     di, ax
0x14002659c  cmp     di, [rbx+1Ah]
0x1400265a0  jnz     loc_1400267FF
0x1400265a6  xor     edi, edi
0x1400265a8  test    [rbx+19h], sil
0x1400265ac  jnz     loc_14002671F
0x1400265b2  cmp     [rbx+18h], sil
0x1400265b6  jnz     loc_14002671F
0x1400265bc  mov     r14, [r14]
0x1400265bf  test    r14, r14
0x1400265c2  jz      loc_14002671F
0x1400265c8  mov     rax, [r14+28h]
0x1400265cc  movzx   ecx, word ptr [rax+2Ah]
0x1400265d0  and     ecx, 0FFFF2FFFh
0x1400265d6  cmp     ecx, 29Ch
0x1400265dc  jz      loc_14002671F
0x1400265e2  call    cs:__imp_W32GetUserSessionState
0x1400265e9  nop     dword ptr [rax+rax+00h]
0x1400265ee  movzx   edx, word ptr [rax+0A0D2h]
0x1400265f5  mov     rax, [r14+88h]
0x1400265fc  mov     rcx, [rax+8]
0x140026600  cmp     dx, [rcx]
0x140026603  jz      loc_14002671F
0x140026609  lea     eax, [r15-310h]
0x140026610  cmp     eax, esi
0x140026612  jbe     loc_14002682D
0x140026618  cmp     [rbp+37h+arg_38], esi
0x14002661b  jz      loc_14002685A
0x140026621  cmp     [rbp+37h+arg_38], 2
0x140026625  jz      loc_140026B77
0x14002662b  mov     eax, [r14+17Ch]
0x140026632  test    al, 10h
0x140026634  jnz     loc_140026B99
0x14002663a  mov     rcx, [rbp+37h+var_40]
0x14002663e  mov     [rbp+37h+var_48], r14
0x140026642  mov     rax, [rcx+1C0h]
0x140026649  mov     [rbp+37h+BugCheckParameter3], rax
0x14002664d  lea     rax, [rbp+37h+BugCheckParameter3]
0x140026651  mov     [rcx+1C0h], rax
0x140026658  mov     rcx, r14
0x14002665b  call    cs:__imp_HMLockObject
0x140026662  nop     dword ptr [rax+rax+00h]
0x140026667  mov     eax, [rbp+37h+arg_20]
0x14002666a  test    eax, eax
0x14002666c  jz      loc_140026A0F
0x140026672  sub     eax, esi
0x140026674  jz      loc_140026763
0x14002667a  sub     eax, esi
0x14002667c  jz      loc_140026740
0x140026682  sub     eax, esi
0x140026684  jz      loc_140026D0B
0x14002668a  sub     eax, esi
0x14002668c  jz      short loc_14002669A
0x14002668e  sub     eax, esi
0x140026690  jz      loc_140026C8A
0x140026696  cmp     eax, esi
0x140026698  jnz     short loc_1400266D9
0x14002669a  mov     rcx, [rbp+37h+arg_28]
0x14002669e  mov     r9, r13
0x1400266a1  mov     ebx, [rbp+37h+arg_30]
0x1400266a4  mov     r8, r12
0x1400266a7  mov     [rsp+0F0h+var_B0], esi; int
0x1400266ab  mov     edx, r15d; unsigned int
0x1400266ae  mov     dword ptr [rsp+0F0h+var_B8], ebx; int
0x1400266b2  mov     rax, [rcx+8]
0x1400266b6  mov     qword ptr [rsp+0F0h+var_C0], rax; __int64
0x1400266bb  mov     eax, [rcx+4]
0x1400266be  mov     dword ptr [rsp+0F0h+var_C8], eax; int
0x1400266c2  mov     eax, [rcx]
0x1400266c4  mov     rcx, r14; struct tagWND *
0x1400266c7  mov     dword ptr [rsp+0F0h+BugCheckParameter4], eax; int
0x1400266cb  call    xxxSendTransformableMessageTimeout
0x1400266d0  test    rax, rax
0x1400266d3  jz      loc_1400269D9
0x1400266d9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400266e0  nop     dword ptr [rax+rax+00h]
0x1400266e5  test    rax, rax
0x1400266e8  jz      loc_140026E9F
0x1400266ee  mov     r8, [rax]; BugCheckParameter2
0x1400266f1  mov     rcx, [r8+1C0h]
0x1400266f8  lea     rax, [rbp+37h+BugCheckParameter3]
0x1400266fc  cmp     rcx, rax
0x1400266ff  jnz     loc_140026AA4
0x140026705  mov     rax, [rcx]
0x140026708  mov     [r8+1C0h], rax
0x14002670f  mov     rcx, [rcx+8]
0x140026713  call    cs:__imp_HMUnlockObject
0x14002671a  nop     dword ptr [rax+rax+00h]
0x14002671f  mov     r14, [rbp+37h+var_70]
0x140026723  add     r14, 8
0x140026727  mov     [rbp+37h+var_70], r14
0x14002672b  mov     rdi, [r14]
0x14002672e  cmp     rdi, rsi
0x140026731  jz      loc_1400269E8
0x140026737  mov     r12, [rbp+37h+arg_10]
0x14002673b  jmp     loc_14002650D
0x140026740  cmp     [r14+78h], rdi
0x140026744  jnz     short loc_1400266D9
0x140026746  mov     eax, [rbp+37h+arg_30]
0x140026749  mov     r9, r13
0x14002674c  mov     r8, r12
0x14002674f  mov     dword ptr [rsp+0F0h+BugCheckParameter4], eax; int
0x140026753  mov     edx, r15d; unsigned int
0x140026756  mov     rcx, r14; struct tagWND *
0x140026759  call    _PostTransformableMessageIL
0x14002675e  jmp     loc_1400266D9
0x140026763  mov     ebx, [rbp+37h+arg_30]
0x140026766  mov     eax, r15d
0x140026769  sub     eax, 1Ah
0x14002676c  jz      short loc_140026776
0x14002676e  sub     eax, esi
0x140026770  jnz     loc_14002686F
0x140026776  mov     rbx, rdi
0x140026779  test    r13, r13
0x14002677c  jz      short loc_1400267A9
0x14002677e  mov     rcx, [r13+8]
0x140026782  cmp     [rcx], di
0x140026785  jz      loc_140026961
0x14002678b  xor     edx, edx
0x14002678d  lea     r8d, [rdx+2]
0x140026791  call    cs:__imp_UserAddAtomEx
0x140026798  nop     dword ptr [rax+rax+00h]
0x14002679d  movzx   ebx, ax
0x1400267a0  test    rbx, rbx
0x1400267a3  jz      loc_1400266D9
0x1400267a9  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x1400267ad  mov     r9, r14; struct tagWND *
0x1400267b0  mov     [rsp+0F0h+var_B8], rdi; struct tagINPUT_MESSAGE_SOURCE *
0x1400267b5  mov     r8d, 9; unsigned int
0x1400267bb  mov     qword ptr [rsp+0F0h+var_C0], rbx; __int64
0x1400267c0  mov     [rsp+0F0h+var_C8], r12; unsigned __int64
0x1400267c5  mov     rdx, [rcx+1D0h]; struct tagQ *
0x1400267cc  mov     dword ptr [rsp+0F0h+BugCheckParameter4], r15d; unsigned int
0x1400267d1  call    ?PostEventMessageEx@@YAHPEAUtagTHREADINFO@@PEAUtagQ@@KPEAUtagWND@@I_K_JPEAUtagINPUT_MESSAGE_SOURCE@@@Z; PostEventMessageEx(tagTHREADINFO *,tagQ *,ulong,tagWND *,uint,unsigned __int64,__int64,tagINPUT_MESSAGE_SOURCE *)
0x1400267d6  test    eax, eax
0x1400267d8  jnz     loc_1400266D9
0x1400267de  lea     rax, [rbx+1]
0x1400267e2  cmp     rax, rsi
0x1400267e5  jbe     loc_1400266D9
0x1400267eb  movzx   ecx, bx
0x1400267ee  call    cs:__imp_UserDeleteAtom
0x1400267f5  nop     dword ptr [rax+rax+00h]
0x1400267fa  jmp     loc_1400266D9
0x1400267ff  cmp     di, ax
0x140026802  jz      loc_1400265A6
0x140026808  test    di, di
0x14002680b  jnz     loc_14002671F
0x140026811  call    cs:__imp_PsGetCurrentProcessWow64Process
0x140026818  nop     dword ptr [rax+rax+00h]
0x14002681d  xor     edi, edi
0x14002681f  test    rax, rax
0x140026822  jz      loc_14002671F
0x140026828  jmp     loc_1400265A8
0x14002682d  mov     rax, [r14+28h]
0x140026831  test    byte ptr [rax+1Fh], 10h
0x140026835  jnz     loc_140026618
0x14002683b  mov     rdx, [r14+10h]
0x14002683f  mov     ecx, edi
0x140026841  xor     eax, eax
0x140026843  lock cmpxchg [rdx+208h], ecx
0x14002684b  bt      eax, 0Bh
0x14002684f  jnb     loc_14002671F
0x140026855  jmp     loc_140026618
0x14002685a  mov     rax, [r14+28h]
0x14002685e  cmp     [rax+0ECh], esi
0x140026864  jnz     loc_14002671F
0x14002686a  jmp     loc_14002662B
0x14002686f  cmp     eax, 63h ; 'c'
0x140026872  jnz     loc_140026CFD
0x140026878  call    cs:__imp_GetDispInfo
0x14002687f  nop     dword ptr [rax+rax+00h]
0x140026884  mov     rcx, r14; struct tagWND *
0x140026887  mov     r9, rax
0x14002688a  call    ?GetWindowCompositedDpiContext@@YAKPEBUtagWND@@@Z; GetWindowCompositedDpiContext(tagWND const *)
0x14002688f  mov     rdx, [r9+60h]
0x140026893  lea     rcx, [rbp+37h+var_90]
0x140026897  shr     eax, 8
0x14002689a  mov     r8d, 1FFh
0x1400268a0  and     r8w, ax
0x1400268a4  call    GetMonitorRectForDpi
0x1400268a9  movzx   eax, word ptr [rbp+37h+var_90+0Ch]
0x1400268ad  sub     ax, word ptr [rbp+37h+var_90+4]
0x1400268b1  movzx   edx, ax
0x1400268b4  movzx   eax, word ptr [rbp+37h+var_90+8]
0x1400268b8  sub     ax, word ptr [rbp+37h+var_90]
0x1400268bc  movzx   eax, ax
0x1400268bf  shl     edx, 10h
0x1400268c2  or      eax, edx
0x1400268c4  cdqe
0x1400268c6  mov     [rbp+37h+var_78], rax
0x1400268ca  test    r13, r13
0x1400268cd  jz      loc_14002696A
0x1400268d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268da  lea     rax, WPP_GLOBAL_Control
0x1400268e1  cmp     rcx, rax
0x1400268e4  jz      short loc_1400268F1
0x1400268e6  mov     eax, [rcx+2Ch]
0x1400268e9  test    al, 40h
0x1400268eb  jnz     loc_140026E1B
0x1400268f1  mov     al, dil
0x1400268f4  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400268fb  mov     [rbp+37h+arg_8], al
0x1400268fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140026905  jz      short loc_140026910
0x140026907  mov     r12b, sil
0x14002690a  cmp     [rcx+48h], di
0x14002690e  jnz     short loc_140026913
0x140026910  mov     r12b, dil
0x140026913  test    al, al
0x140026915  jnz     loc_140026E2D
0x14002691b  test    r12b, r12b
0x14002691e  jnz     loc_140026E2D
0x140026924  mov     rcx, [r14+10h]; struct tagTHREADINFO *
0x140026928  mov     r9, r14; struct tagWND *
  ... truncated ...
```
