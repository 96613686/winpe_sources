# xxxSendBSMtoDesktop(tagWND *,uint,unsigned __int64,__int64,tagBROADCASTSYSTEMMSGPARAMS *,int)

- ea: `0x140025c64`
- end: `0x140026430`
- name: `?xxxSendBSMtoDesktop@@YAHPEAUtagWND@@I_K_JPEAUtagBROADCASTSYSTEMMSGPARAMS@@H@Z`
- size: `1996`
- prototype: `int(struct tagWND *, unsigned int, unsigned __int64, __int64, struct tagBROADCASTSYSTEMMSGPARAMS *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401485a0`

## callees

- `0x140020370`
- `0x1400208b0`
- `0x140021d30`
- `0x140023ac0`
- `0x140025c64`
- `0x140027d44`
- `0x140028660`
- `0x1400bcaa0`
- `0x1400c138c`
- `0x1400c2a10`
- `0x1400c3a60`
- `0x1400eb130`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!ZwPowerInformation` at `0x140025f85`
- `ntoskrnl!ZwPowerInformation` at `0x14002603f`
- `ntoskrnl!ZwPowerInformation` at `0x140025f85`
- `ntoskrnl!ZwPowerInformation` at `0x14002603f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400261b8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400261b8`
- `ntoskrnl!PsGetThreadProcessId` at `0x140025f5c`
- `ntoskrnl!PsGetThreadProcessId` at `0x140026019`
- `ntoskrnl!PsGetThreadProcessId` at `0x140025f5c`
- `ntoskrnl!PsGetThreadProcessId` at `0x140026019`
- `ntoskrnl!KeBugCheckEx` at `0x1400262c5`
- `ntoskrnl!KeBugCheckEx` at `0x1400262c5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025d8b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400260e0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025d8b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400260e0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140026093`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140026093`
- `win32kbase!GetProcessLuid` at `0x140026229`
- `win32kbase!GetProcessLuid` at `0x140026266`
- `win32kbase!GetProcessLuid` at `0x140026337`
- `win32kbase!GetProcessLuid` at `0x140026229`
- `win32kbase!GetProcessLuid` at `0x140026266`
- `win32kbase!GetProcessLuid` at `0x140026337`
- `win32kbase!HMPkheFromPhe` at `0x140025dff`
- `win32kbase!HMPkheFromPhe` at `0x140025dff`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x1400263e3`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x1400263e3`
- `win32kbase!luidSystem` at `0x14002623d`
- `win32kbase!luidSystem` at `0x140026343`
- `win32kbase!HMLockObject` at `0x140025ede`
- `win32kbase!HMLockObject` at `0x140025ede`
- `win32kbase!HMUnlockObject` at `0x14002611a`
- `win32kbase!HMUnlockObject` at `0x14002611a`
- `WIN32K!W32GetUserSessionState` at `0x140025daf`
- `WIN32K!W32GetUserSessionState` at `0x140025dcc`
- `WIN32K!W32GetUserSessionState` at `0x140025ddb`
- `WIN32K!W32GetUserSessionState` at `0x140025e9a`
- `WIN32K!W32GetUserSessionState` at `0x14002639f`
- `WIN32K!W32GetUserSessionState` at `0x140025daf`
- `WIN32K!W32GetUserSessionState` at `0x140025dcc`
- `WIN32K!W32GetUserSessionState` at `0x140025ddb`
- `WIN32K!W32GetUserSessionState` at `0x140025e9a`
- `WIN32K!W32GetUserSessionState` at `0x14002639f`

## pseudocode

```c
__int64 __fastcall xxxSendBSMtoDesktop(
        struct tagWND **a1,
        unsigned int a2,
        __int64 a3,
        __int128 *a4,
        struct tagBROADCASTSYSTEMMSGPARAMS *a5,
        int a6)
{
  int v9; // r12d
  __int64 v10; // rcx
  unsigned int v11; // r12d
  __int64 *v12; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 UserSessionState; // rbx
  __int64 v16; // rcx
  __int64 v17; // rbx
  PETHREAD ***v18; // r13
  PETHREAD **v19; // rbx
  int v20; // r13d
  int v21; // edx
  __int64 *v22; // r8
  struct tagTHREADINFO *v23; // r14
  __int64 v24; // rax
  int v25; // r12d
  int v26; // edx
  int v27; // r14d
  __int64 v28; // rax
  __int64 v29; // rcx
  PETHREAD *v30; // rcx
  void *v31; // rax
  ULONG_PTR *CurrentThreadWin32Thread; // rax
  ULONG_PTR v34; // r8
  ULONG_PTR *v35; // rcx
  __int64 v36; // rax
  _QWORD *v37; // rcx
  _QWORD *v38; // rcx
  __int128 v39; // xmm0
  int v40; // eax
  bool v41; // zf
  int v42; // [rsp+50h] [rbp-99h]
  HANDLE InputBuffer; // [rsp+58h] [rbp-91h] BYREF
  PETHREAD **v44; // [rsp+60h] [rbp-89h] BYREF
  __int64 v45; // [rsp+68h] [rbp-81h]
  int v46; // [rsp+70h] [rbp-79h]
  int v47; // [rsp+74h] [rbp-75h]
  void *Handle; // [rsp+78h] [rbp-71h] BYREF
  __int64 v49; // [rsp+80h] [rbp-69h] BYREF
  __int128 *v50; // [rsp+88h] [rbp-61h]
  int v51; // [rsp+90h] [rbp-59h]
  __int64 v52; // [rsp+98h] [rbp-51h] BYREF
  char v53[8]; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-41h]
  struct tagTHREADINFO *v55; // [rsp+B0h] [rbp-39h]
  __int64 v56; // [rsp+B8h] [rbp-31h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+C0h] [rbp-29h] BYREF
  __int128 v58; // [rsp+D0h] [rbp-19h]
  int v59; // [rsp+E0h] [rbp-9h]

  v50 = a4;
  v45 = a3;
  v9 = 0;
  v55 = PtiCurrent();
  v58 = 0;
  v59 = 0;
  if ( !a1 )
    return 0;
  if ( a2 - 1024 > 0xBBFF )
  {
    if ( !a6 && (a2 == 295 || a2 == 21 || a2 == 26 || a2 == 29 || a2 == 794) )
      a6 = 1;
    v56 = BuildHwndList(a1[14], 2u);
    if ( v56 )
    {
      v10 = *((unsigned int *)a5 + 1);
      LOBYTE(v10) = v10 & 0x90;
      v46 = 0;
      if ( (_BYTE)v10 == 0x80 )
      {
        v10 = *(_QWORD *)(W32GetUserSessionState(v10) + 19216);
        if ( a1[3] == (struct tagWND *)v10 )
        {
          v10 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)v55 + 130, 0, 0) & 8) != 0
            || CanForceForeground(*((const struct tagPROCESSINFO **)v55 + 57)) )
          {
            LastWokenThread::Clear((LastWokenThread *)v10);
          }
        }
      }
      if ( a2 != 537 || ((v45 - 0x8000) & 0xFFFFFFFFFFFFFFFBuLL) != 0 || *((_DWORD *)a4 + 1) != 2 )
        goto LABEL_13;
      v10 = 0x40000000;
      if ( (*((_DWORD *)a4 + 3) & 0x40000000) == 0 )
      {
        v39 = *a4;
        v59 = *((_DWORD *)a4 + 4);
        v40 = HIDWORD(*((_QWORD *)a4 + 1)) | 0x40000000;
        v41 = (*((_DWORD *)a5 + 1) & 0x400) == 0;
        v58 = v39;
        HIDWORD(v58) = v40;
        if ( v41 )
        {
          v44 = 0;
          GetProcessLuid(0, &v44);
          v10 = luidSystem[0];
          if ( (_DWORD)v44 == luidSystem[0] )
          {
            v10 = luidSystem[1];
            if ( HIDWORD(v44) == (_DWORD)v10 )
              v9 = 1;
            v46 = v9;
          }
        }
LABEL_13:
        v11 = 1;
        v12 = (__int64 *)(v56 + 32);
        v42 = 1;
        while ( 1 )
        {
          v13 = *v12;
          Handle = v12;
          if ( v13 == 1 )
          {
LABEL_45:
            FreeHwndList(v56);
            return v11;
          }
          PsGetCurrentThreadWin32Thread(v10);
          v10 = *(_QWORD *)(W32GetUserSessionState(v14) + 19704);
          if ( (unsigned __int64)(unsigned __int16)v13 < *(_QWORD *)(v10 + 8) )
          {
            UserSessionState = W32GetUserSessionState(v10);
            v17 = *(_DWORD *)(W32GetUserSessionState(v16) + 19728) * (unsigned int)(unsigned __int16)v13
                + *(_QWORD *)(UserSessionState + 19720);
            v18 = (PETHREAD ***)HMPkheFromPhe(v17);
            LOWORD(v13) = WORD1(v13) & 0x7FFF;
            if ( ((WORD1(v13) & 0x7FFF) == *(_WORD *)(v17 + 26)
               || (_WORD)v13 == 0x7FFF
               || !(_WORD)v13 && PsGetCurrentProcessWow64Process())
              && (*(_BYTE *)(v17 + 25) & 1) == 0
              && *(_BYTE *)(v17 + 24) == 1 )
            {
              v19 = *v18;
              v20 = 0;
              if ( v19 )
              {
                v21 = *((_DWORD *)a5 + 1);
                v22 = (__int64 *)(v19 + 2);
                v23 = v55;
                v44 = v19 + 2;
                if ( (v21 & 2) != 0 )
                {
                  v10 = *v22;
                  if ( *(_QWORD *)(*v22 + 464) == *((_QWORD *)v55 + 58) )
                    goto LABEL_52;
                }
                else
                {
                  v44 = v19 + 2;
                }
                if ( (v21 & 0x400) != 0 )
                {
                  v38 = (_QWORD *)*v22;
                  v49 = 0;
                  if ( (int)GetProcessLuid(*v38, &v49) < 0 || *((_QWORD *)a5 + 4) != v49 )
                    goto LABEL_52;
                  v22 = (__int64 *)v44;
                }
                v47 = 0;
                if ( v46 == 1 )
                {
                  v37 = (_QWORD *)*v22;
                  InputBuffer = 0;
                  if ( (int)GetProcessLuid(*v37, &InputBuffer) < 0 )
                    goto LABEL_52;
                  if ( (HANDLE)__PAIR64__(luidSystem[1], luidSystem[0]) != InputBuffer )
                    v47 = 1;
                }
                v10 = *((_WORD *)v19[5] + 21) & 0x2FFF;
                if ( (_DWORD)v10 != 668 )
                {
                  v24 = W32GetUserSessionState(v10);
                  v10 = (__int64)v19[17][1];
                  if ( *(_WORD *)(v24 + 41170) != *(_WORD *)v10 )
                    break;
                }
              }
            }
          }
LABEL_52:
          v12 = (__int64 *)((char *)Handle + 8);
        }
        BugCheckParameter3[0] = *((_QWORD *)v23 + 56);
        *((_QWORD *)v23 + 56) = BugCheckParameter3;
        BugCheckParameter3[1] = (ULONG_PTR)v19;
        HMLockObject(v19);
        v25 = *((_DWORD *)a5 + 1);
        if ( (v25 & 0x10) != 0 )
        {
          PostTransformableMessageIL((struct tagWND *)v19, a2, a6);
        }
        else if ( (v25 & 0x100) != 0 )
        {
          xxxSendNotifyMessage(v19, a2, v45, v50, a6);
        }
        else
        {
          if ( (v25 & 0x20000000) == 0 )
          {
            v52 = 0;
            v26 = v25 & 8;
            InputBuffer = 0;
            v51 = v26;
            if ( a2 == 536 && v45 == 4 )
              v20 = 1;
            if ( (v25 & 8) != 0 )
              v27 = v20 != 0 ? 2000 : 5000;
            else
              v27 = 0;
            if ( v20 )
            {
              InputBuffer = PsGetThreadProcessId(**v44);
              ZwPowerInformation(TraceApplicationPowerMessage, &InputBuffer, 8u, 0, 0);
              v26 = v51;
            }
            v28 = xxxSendTransformableMessageTimeout(
                    (struct tagWND *)v19,
                    a2,
                    (v26 != 0 ? 2 : 0) | (*((_DWORD *)a5 + 1) >> 3) & 8u,
                    v27,
                    (__int64)&v52,
                    a6,
                    1);
            v29 = 0;
            if ( v28 )
            {
              if ( (*((_DWORD *)a5 + 1) & 1) == 0 )
              {
                v11 = v42;
                goto LABEL_37;
              }
              v11 = 0;
              if ( a2 == 17 )
                v41 = v52 == 0;
              else
                v41 = v52 == 1112363332;
              LOBYTE(v11) = !v41;
            }
            else
            {
              v11 = v25 & 0x20;
            }
            v42 = v11;
LABEL_37:
            if ( v20 )
            {
              InputBuffer = 0;
              InputBuffer = PsGetThreadProcessId(**v44);
              ZwPowerInformation(TraceApplicationPowerMessageEnd, &InputBuffer, 8u, 0, 0);
            }
            if ( !v11 )
            {
              v41 = (*((_DWORD *)a5 + 1) & 0x200) == 0;
              *((_QWORD *)a5 + 3) = *v19;
              if ( !v41 )
              {
                v30 = v19[3];
                v31 = 0;
                Handle = 0;
                if ( v30 )
                {
                  ObOpenObjectByPointer(v30, 0, 0, 0x1F0003u, 0, 1, &Handle);
                  v31 = Handle;
                }
                *((_QWORD *)a5 + 2) = v31;
              }
              Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)BugCheckParameter3);
              goto LABEL_45;
            }
            goto LABEL_48;
          }
          v53[0] = 0;
          v54 = 0;
          AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v53);
          xxxSendMessageCallback((struct tagWND *)v19, a2, 0, 1, 0, a6 != 0, 1);
          if ( v53[0] )
          {
            v36 = v54;
            v54 = 0;
            v53[0] = 0;
            --*(_DWORD *)(v36 + 28);
          }
        }
        v11 = v42;
LABEL_48:
        CurrentThreadWin32Thread = (ULONG_PTR *)PsGetCurrentThreadWin32Thread(v29);
        if ( CurrentThreadWin32Thread )
          v34 = *CurrentThreadWin32Thread;
        else
          v34 = 0;
        v35 = *(ULONG_PTR **)(v34 + 448);
        if ( v35 != BugCheckParameter3 )
          KeBugCheckEx(0x164u, 0x3Bu, v34, (ULONG_PTR)BugCheckParameter3, 0);
        *(_QWORD *)(v34 + 448) = *v35;
        HMUnlockObject(v35[1]);
        goto LABEL_52;
      }
    }
    return 0;
  }
  UserSetLastError(87);
  return 1;
}

```

## disassembly

```asm
0x140025c64  push    rbp
0x140025c66  push    rbx
0x140025c67  push    rsi
0x140025c68  push    rdi
0x140025c69  push    r12
0x140025c6b  push    r13
0x140025c6d  push    r14
0x140025c6f  push    r15
0x140025c71  lea     rbp, [rsp-0Fh]
0x140025c76  sub     rsp, 0F8h
0x140025c7d  mov     rax, cs:__security_cookie
0x140025c84  xor     rax, rsp
0x140025c87  mov     [rbp+47h+var_48], rax
0x140025c8b  mov     r15, [rbp+47h+arg_20]
0x140025c8f  mov     r14, r9
0x140025c92  mov     [rbp+47h+var_A8], r9
0x140025c96  mov     esi, edx
0x140025c98  mov     [rsp+130h+var_C8], r8
0x140025c9d  mov     rbx, rcx
0x140025ca0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140025ca5  xor     r12d, r12d
0x140025ca8  mov     [rbp+47h+var_80], rax
0x140025cac  mov     r13, rax
0x140025caf  mov     ecx, r12d
0x140025cb2  lea     eax, [rsi-400h]
0x140025cb8  xorps   xmm0, xmm0
0x140025cbb  cmp     eax, 0BBFFh
0x140025cc0  movups  [rbp+47h+var_60], xmm0
0x140025cc4  setbe   cl
0x140025cc7  xor     eax, eax
0x140025cc9  mov     [rbp+47h+var_50], eax
0x140025ccc  test    rbx, rbx
0x140025ccf  jz      loc_1400261F6
0x140025cd5  test    ecx, ecx
0x140025cd7  jnz     loc_140026383
0x140025cdd  lea     edi, [rax+1]
0x140025ce0  cmp     [rbp+47h+arg_28], r12d
0x140025ce4  jnz     short loc_140025D19
0x140025ce6  cmp     esi, 127h
0x140025cec  jz      loc_140026397
0x140025cf2  cmp     esi, 15h
0x140025cf5  jz      loc_140026397
0x140025cfb  cmp     esi, 1Ah
0x140025cfe  jz      loc_140026397
0x140025d04  cmp     esi, 1Dh
0x140025d07  jz      loc_140026397
0x140025d0d  cmp     esi, 31Ah
0x140025d13  jz      loc_140026397
0x140025d19  mov     rcx, [rbx+70h]
0x140025d1d  xor     r8d, r8d
0x140025d20  mov     r9d, edi
0x140025d23  lea     edx, [r8+2]
0x140025d27  call    BuildHwndList
0x140025d2c  mov     [rbp+47h+var_78], rax
0x140025d30  test    rax, rax
0x140025d33  jz      loc_1400261F6
0x140025d39  mov     ecx, [r15+4]
0x140025d3d  and     cl, 90h
0x140025d40  mov     [rbp+47h+var_C0], r12d
0x140025d44  cmp     cl, 80h
0x140025d47  jz      loc_14002639F
0x140025d4d  cmp     esi, 219h
0x140025d53  jnz     short loc_140025D6C
0x140025d55  mov     rax, [rsp+130h+var_C8]
0x140025d5a  add     rax, 0FFFFFFFFFFFF8000h
0x140025d60  test    rax, 0FFFFFFFFFFFFFFFBh
0x140025d66  jz      loc_1400262E4
0x140025d6c  mov     rax, [rbp+47h+var_78]
0x140025d70  mov     r12d, edi
0x140025d73  add     rax, 20h ; ' '
0x140025d77  mov     [rsp+130h+var_E0], edi
0x140025d7b  mov     r14, [rax]
0x140025d7e  mov     [rbp+47h+var_B8], rax
0x140025d82  cmp     r14, rdi
0x140025d85  jz      loc_1400260B0
0x140025d8b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140025d92  nop     dword ptr [rax+rax+00h]
0x140025d97  test    rax, rax
0x140025d9a  jz      short loc_140025DAB
0x140025d9c  mov     rax, [rax]
0x140025d9f  test    rax, rax
0x140025da2  jz      short loc_140025DAB
0x140025da4  mov     rax, [rax+200h]
0x140025dab  movzx   r13d, r14w
0x140025daf  call    cs:__imp_W32GetUserSessionState
0x140025db6  nop     dword ptr [rax+rax+00h]
0x140025dbb  mov     rcx, [rax+4CF8h]
0x140025dc2  cmp     r13, [rcx+8]
0x140025dc6  jnb     loc_140026126
0x140025dcc  call    cs:__imp_W32GetUserSessionState
0x140025dd3  nop     dword ptr [rax+rax+00h]
0x140025dd8  mov     rbx, rax
0x140025ddb  call    cs:__imp_W32GetUserSessionState
0x140025de2  nop     dword ptr [rax+rax+00h]
0x140025de7  mov     rbx, [rbx+4D08h]
0x140025dee  imul    r13d, [rax+4D10h]
0x140025df6  mov     ecx, r13d
0x140025df9  add     rbx, rcx
0x140025dfc  mov     rcx, rbx
0x140025dff  call    cs:__imp_HMPkheFromPhe
0x140025e06  nop     dword ptr [rax+rax+00h]
0x140025e0b  shr     r14, 10h
0x140025e0f  mov     r13, rax
0x140025e12  mov     eax, 7FFFh
0x140025e17  and     r14w, ax
0x140025e1b  cmp     r14w, [rbx+1Ah]
0x140025e20  jnz     loc_1400261A4
0x140025e26  test    [rbx+19h], dil
0x140025e2a  jnz     loc_140026126
0x140025e30  cmp     [rbx+18h], dil
0x140025e34  jnz     loc_140026126
0x140025e3a  mov     rbx, [r13+0]
0x140025e3e  xor     r13d, r13d
0x140025e41  test    rbx, rbx
0x140025e44  jz      loc_140026126
0x140025e4a  mov     edx, [r15+4]
0x140025e4e  lea     r8, [rbx+10h]
0x140025e52  mov     r14, [rbp+47h+var_80]
0x140025e56  mov     [rsp+130h+var_D0], r8
0x140025e5b  test    dl, 2
0x140025e5e  jnz     loc_1400261DA
0x140025e64  mov     [rsp+130h+var_D0], r8
0x140025e69  bt      edx, 0Ah
0x140025e6d  jb      loc_140026258
0x140025e73  mov     [rbp+47h+var_BC], r13d
0x140025e77  cmp     [rbp+47h+var_C0], edi
0x140025e7a  jz      loc_140026219
0x140025e80  mov     rax, [rbx+28h]
0x140025e84  movzx   ecx, word ptr [rax+2Ah]
0x140025e88  and     ecx, 0FFFF2FFFh
0x140025e8e  cmp     ecx, 29Ch
0x140025e94  jz      loc_140026126
0x140025e9a  call    cs:__imp_W32GetUserSessionState
0x140025ea1  nop     dword ptr [rax+rax+00h]
0x140025ea6  movzx   edx, word ptr [rax+0A0D2h]
0x140025ead  mov     rax, [rbx+88h]
0x140025eb4  mov     rcx, [rax+8]
0x140025eb8  cmp     dx, [rcx]
0x140025ebb  jz      loc_140026126
0x140025ec1  mov     rax, [r14+1C0h]
0x140025ec8  mov     rcx, rbx
0x140025ecb  mov     [rbp+47h+BugCheckParameter3], rax
0x140025ecf  lea     rax, [rbp+47h+BugCheckParameter3]
0x140025ed3  mov     [r14+1C0h], rax
0x140025eda  mov     [rbp+47h+var_68], rbx
0x140025ede  call    cs:__imp_HMLockObject
0x140025ee5  nop     dword ptr [rax+rax+00h]
0x140025eea  mov     r12d, [r15+4]
0x140025eee  test    r12b, 10h
0x140025ef2  jnz     loc_1400260C1
0x140025ef8  bt      r12d, 8
0x140025efd  jb      loc_1400263F4
0x140025f03  bt      r12d, 1Dh
0x140025f08  jb      loc_140026133
0x140025f0e  mov     edx, r12d
0x140025f11  mov     [rbp+47h+var_98], r13
0x140025f15  and     edx, 8
0x140025f18  mov     [rsp+130h+InputBuffer], r13
0x140025f1d  mov     [rbp+47h+var_A0], edx
0x140025f20  cmp     esi, 218h
0x140025f26  jz      loc_14002629E
0x140025f2c  xor     ecx, ecx
0x140025f2e  test    edx, edx
0x140025f30  jz      loc_1400261D2
0x140025f36  mov     eax, r13d
0x140025f39  neg     eax
0x140025f3b  sbb     r14d, r14d
0x140025f3e  and     r14d, 0FFFFF448h
0x140025f45  add     r14d, 1388h
0x140025f4c  test    r13d, r13d
0x140025f4f  jz      short loc_140025F94
0x140025f51  mov     rcx, [rsp+130h+var_D0]
0x140025f56  mov     rcx, [rcx]
0x140025f59  mov     rcx, [rcx]; Thread
0x140025f5c  call    cs:__imp_PsGetThreadProcessId
0x140025f63  nop     dword ptr [rax+rax+00h]
0x140025f68  xor     r9d, r9d; OutputBuffer
0x140025f6b  mov     [rsp+130h+OutputBufferLength], 0; OutputBufferLength
0x140025f73  lea     rdx, [rsp+130h+InputBuffer]; InputBuffer
0x140025f78  mov     [rsp+130h+InputBuffer], rax
0x140025f7d  lea     r8d, [r9+8]; InputBufferLength
0x140025f81  lea     ecx, [r9+1Eh]; InformationLevel
0x140025f85  call    cs:__imp_ZwPowerInformation
0x140025f8c  nop     dword ptr [rax+rax+00h]
0x140025f91  mov     edx, [rbp+47h+var_A0]
0x140025f94  mov     ecx, [r15+4]
0x140025f98  lea     r9, [rbp+47h+var_60]
0x140025f9c  mov     r8, [rsp+130h+var_C8]
0x140025fa1  shr     ecx, 3
0x140025fa4  and     ecx, 8
0x140025fa7  mov     [rsp+130h+var_F0], edi; int
0x140025fab  neg     edx
0x140025fad  mov     edx, esi; unsigned int
0x140025faf  sbb     eax, eax
0x140025fb1  and     eax, 2
0x140025fb4  or      ecx, eax
0x140025fb6  mov     eax, [rbp+47h+arg_28]
0x140025fb9  cmp     [rbp+47h+var_BC], 0
0x140025fbd  mov     [rsp+130h+var_F8], eax; int
0x140025fc1  lea     rax, [rbp+47h+var_98]
0x140025fc5  cmovz   r9, [rbp+47h+var_A8]
0x140025fca  mov     [rsp+130h+Handle], rax; __int64
0x140025fcf  mov     dword ptr [rsp+130h+AccessMode], r14d; int
0x140025fd4  mov     [rsp+130h+OutputBufferLength], ecx; int
0x140025fd8  mov     rcx, rbx; struct tagWND *
0x140025fdb  call    xxxSendTransformableMessageTimeout
0x140025fe0  xor     ecx, ecx
0x140025fe2  test    rax, rax
0x140025fe5  jz      loc_140026196
0x140025feb  mov     eax, [r15+4]
0x140025fef  test    dil, al
0x140025ff2  jnz     loc_14002636A
0x140025ff8  mov     r12d, [rsp+130h+var_E0]
0x140025ffd  test    r13d, r13d
0x140026000  jz      loc_140026420
0x140026006  mov     rax, [rsp+130h+var_D0]
0x14002600b  xor     r13d, r13d
0x14002600e  mov     [rsp+130h+InputBuffer], r13
0x140026013  mov     rcx, [rax]
0x140026016  mov     rcx, [rcx]; Thread
0x140026019  call    cs:__imp_PsGetThreadProcessId
0x140026020  nop     dword ptr [rax+rax+00h]
0x140026025  xor     r9d, r9d; OutputBuffer
0x140026028  mov     [rsp+130h+OutputBufferLength], r13d; OutputBufferLength
0x14002602d  lea     r8d, [r13+8]; InputBufferLength
0x140026031  mov     [rsp+130h+InputBuffer], rax
0x140026036  lea     rdx, [rsp+130h+InputBuffer]; InputBuffer
0x14002603b  lea     ecx, [r13+1Fh]; InformationLevel
0x14002603f  call    cs:__imp_ZwPowerInformation
0x140026046  nop     dword ptr [rax+rax+00h]
0x14002604b  test    r12d, r12d
0x14002604e  jnz     loc_1400260E0
0x140026054  test    dword ptr [r15+4], 200h
0x14002605c  mov     rax, [rbx]
0x14002605f  mov     [r15+18h], rax
0x140026063  jz      short loc_1400260A7
0x140026065  mov     rcx, [rbx+18h]; Object
0x140026069  mov     rax, r13
0x14002606c  mov     [rbp+47h+var_B8], rax
0x140026070  test    rcx, rcx
0x140026073  jz      short loc_1400260A3
0x140026075  lea     rax, [rbp+47h+var_B8]
0x140026079  mov     r9d, 1F0003h; DesiredAccess
0x14002607f  mov     [rsp+130h+Handle], rax; Handle
0x140026084  xor     r8d, r8d; PassedAccessState
0x140026087  mov     [rsp+130h+AccessMode], dil; AccessMode
0x14002608c  xor     edx, edx; HandleAttributes
0x14002608e  mov     qword ptr [rsp+130h+OutputBufferLength], r13; ObjectType
0x140026093  call    cs:__imp_ObOpenObjectByPointer
0x14002609a  nop     dword ptr [rax+rax+00h]
0x14002609f  mov     rax, [rbp+47h+var_B8]
0x1400260a3  mov     [r15+10h], rax
0x1400260a7  lea     rcx, [rbp+47h+BugCheckParameter3]; BugCheckParameter3
0x1400260ab  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ; Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>(void)
0x1400260b0  mov     rcx, [rbp+47h+var_78]
0x1400260b4  call    FreeHwndList
0x1400260b9  mov     eax, r12d
0x1400260bc  jmp     loc_1400261F8
0x1400260c1  mov     eax, [rbp+47h+arg_28]
0x1400260c4  mov     edx, esi; unsigned int
0x1400260c6  mov     r9, [rbp+47h+var_A8]
0x1400260ca  mov     rcx, rbx; struct tagWND *
0x1400260cd  mov     r8, [rsp+130h+var_C8]
0x1400260d2  mov     [rsp+130h+OutputBufferLength], eax; int
0x1400260d6  call    _PostTransformableMessageIL
0x1400260db  mov     r12d, [rsp+130h+var_E0]
0x1400260e0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400260e7  nop     dword ptr [rax+rax+00h]
0x1400260ec  test    rax, rax
0x1400260ef  jz      loc_140026428
0x1400260f5  mov     r8, [rax]; BugCheckParameter2
0x1400260f8  mov     rcx, [r8+1C0h]
0x1400260ff  lea     rax, [rbp+47h+BugCheckParameter3]
0x140026103  cmp     rcx, rax
0x140026106  jnz     loc_1400262B2
0x14002610c  mov     rax, [rcx]
0x14002610f  mov     [r8+1C0h], rax
0x140026116  mov     rcx, [rcx+8]
0x14002611a  call    cs:__imp_HMUnlockObject
0x140026121  nop     dword ptr [rax+rax+00h]
0x140026126  mov     rax, [rbp+47h+var_B8]
0x14002612a  add     rax, 8
0x14002612e  jmp     loc_140025D7B
0x140026133  lea     rcx, [rbp+47h+var_90]; this
0x140026137  mov     [rbp+47h+var_90], r13b
0x14002613b  mov     [rbp+47h+var_88], r13
0x14002613f  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x140026144  cmp     [rbp+47h+arg_28], r13d
0x140026148  mov     eax, r13d
0x14002614b  mov     r9, [rbp+47h+var_A8]
0x14002614f  mov     edx, esi; unsigned int
0x140026151  mov     r8, [rsp+130h+var_C8]
0x140026156  setnz   al
0x140026159  mov     [rsp+130h+var_F0], edi; int
0x14002615d  mov     rcx, rbx; struct tagWND *
0x140026160  mov     [rsp+130h+var_F8], eax; int
0x140026164  mov     dword ptr [rsp+130h+Handle], r13d; int
0x140026169  mov     qword ptr [rsp+130h+AccessMode], rdi; __int64
0x14002616e  mov     qword ptr [rsp+130h+OutputBufferLength], r13; __int64
0x140026173  call    xxxSendMessageCallback
  ... truncated ...
```
