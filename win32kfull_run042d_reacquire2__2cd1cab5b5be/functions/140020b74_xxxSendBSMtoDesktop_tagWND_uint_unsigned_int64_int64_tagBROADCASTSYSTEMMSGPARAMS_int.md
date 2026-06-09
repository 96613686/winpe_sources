# xxxSendBSMtoDesktop(tagWND *,uint,unsigned __int64,__int64,tagBROADCASTSYSTEMMSGPARAMS *,int)

- ea: `0x140020b74`
- end: `0x140021340`
- name: `?xxxSendBSMtoDesktop@@YAHPEAUtagWND@@I_K_JPEAUtagBROADCASTSYSTEMMSGPARAMS@@H@Z`
- size: `1996`
- prototype: `int(struct tagWND *, unsigned int, unsigned __int64, __int64, struct tagBROADCASTSYSTEMMSGPARAMS *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14013e560`

## callees

- `0x14001a8b0`
- `0x14001adf0`
- `0x14001cb60`
- `0x14001e950`
- `0x140020b74`
- `0x140022c54`
- `0x140023570`
- `0x1400e2cb0`
- `0x1400e759c`
- `0x1400e8c20`
- `0x1400e9c10`
- `0x14017bc34`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!ZwPowerInformation` at `0x140020e95`
- `ntoskrnl!ZwPowerInformation` at `0x140020f4f`
- `ntoskrnl!ZwPowerInformation` at `0x140020e95`
- `ntoskrnl!ZwPowerInformation` at `0x140020f4f`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400210c8`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1400210c8`
- `ntoskrnl!PsGetThreadProcessId` at `0x140020e6c`
- `ntoskrnl!PsGetThreadProcessId` at `0x140020f29`
- `ntoskrnl!PsGetThreadProcessId` at `0x140020e6c`
- `ntoskrnl!PsGetThreadProcessId` at `0x140020f29`
- `ntoskrnl!KeBugCheckEx` at `0x1400211d5`
- `ntoskrnl!KeBugCheckEx` at `0x1400211d5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140020c9b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140020ff0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140020c9b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140020ff0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140020fa3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140020fa3`
- `win32kbase!GetProcessLuid` at `0x140021139`
- `win32kbase!GetProcessLuid` at `0x140021176`
- `win32kbase!GetProcessLuid` at `0x140021247`
- `win32kbase!GetProcessLuid` at `0x140021139`
- `win32kbase!GetProcessLuid` at `0x140021176`
- `win32kbase!GetProcessLuid` at `0x140021247`
- `win32kbase!HMPkheFromPhe` at `0x140020d0f`
- `win32kbase!HMPkheFromPhe` at `0x140020d0f`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x1400212f3`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x1400212f3`
- `win32kbase!luidSystem` at `0x14002114d`
- `win32kbase!luidSystem` at `0x140021253`
- `win32kbase!HMLockObject` at `0x140020dee`
- `win32kbase!HMLockObject` at `0x140020dee`
- `win32kbase!HMUnlockObject` at `0x14002102a`
- `win32kbase!HMUnlockObject` at `0x14002102a`
- `WIN32K!W32GetUserSessionState` at `0x140020cbf`
- `WIN32K!W32GetUserSessionState` at `0x140020cdc`
- `WIN32K!W32GetUserSessionState` at `0x140020ceb`
- `WIN32K!W32GetUserSessionState` at `0x140020daa`
- `WIN32K!W32GetUserSessionState` at `0x1400212af`
- `WIN32K!W32GetUserSessionState` at `0x140020cbf`
- `WIN32K!W32GetUserSessionState` at `0x140020cdc`
- `WIN32K!W32GetUserSessionState` at `0x140020ceb`
- `WIN32K!W32GetUserSessionState` at `0x140020daa`
- `WIN32K!W32GetUserSessionState` at `0x1400212af`

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
0x140020b74  push    rbp
0x140020b76  push    rbx
0x140020b77  push    rsi
0x140020b78  push    rdi
0x140020b79  push    r12
0x140020b7b  push    r13
0x140020b7d  push    r14
0x140020b7f  push    r15
0x140020b81  lea     rbp, [rsp-0Fh]
0x140020b86  sub     rsp, 0F8h
0x140020b8d  mov     rax, cs:__security_cookie
0x140020b94  xor     rax, rsp
0x140020b97  mov     [rbp+47h+var_48], rax
0x140020b9b  mov     r15, [rbp+47h+arg_20]
0x140020b9f  mov     r14, r9
0x140020ba2  mov     [rbp+47h+var_A8], r9
0x140020ba6  mov     esi, edx
0x140020ba8  mov     [rsp+130h+var_C8], r8
0x140020bad  mov     rbx, rcx
0x140020bb0  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x140020bb5  xor     r12d, r12d
0x140020bb8  mov     [rbp+47h+var_80], rax
0x140020bbc  mov     r13, rax
0x140020bbf  mov     ecx, r12d
0x140020bc2  lea     eax, [rsi-400h]
0x140020bc8  xorps   xmm0, xmm0
0x140020bcb  cmp     eax, 0BBFFh
0x140020bd0  movups  [rbp+47h+var_60], xmm0
0x140020bd4  setbe   cl
0x140020bd7  xor     eax, eax
0x140020bd9  mov     [rbp+47h+var_50], eax
0x140020bdc  test    rbx, rbx
0x140020bdf  jz      loc_140021106
0x140020be5  test    ecx, ecx
0x140020be7  jnz     loc_140021293
0x140020bed  lea     edi, [rax+1]
0x140020bf0  cmp     [rbp+47h+arg_28], r12d
0x140020bf4  jnz     short loc_140020C29
0x140020bf6  cmp     esi, 127h
0x140020bfc  jz      loc_1400212A7
0x140020c02  cmp     esi, 15h
0x140020c05  jz      loc_1400212A7
0x140020c0b  cmp     esi, 1Ah
0x140020c0e  jz      loc_1400212A7
0x140020c14  cmp     esi, 1Dh
0x140020c17  jz      loc_1400212A7
0x140020c1d  cmp     esi, 31Ah
0x140020c23  jz      loc_1400212A7
0x140020c29  mov     rcx, [rbx+70h]
0x140020c2d  xor     r8d, r8d
0x140020c30  mov     r9d, edi
0x140020c33  lea     edx, [r8+2]
0x140020c37  call    BuildHwndList
0x140020c3c  mov     [rbp+47h+var_78], rax
0x140020c40  test    rax, rax
0x140020c43  jz      loc_140021106
0x140020c49  mov     ecx, [r15+4]
0x140020c4d  and     cl, 90h
0x140020c50  mov     [rbp+47h+var_C0], r12d
0x140020c54  cmp     cl, 80h
0x140020c57  jz      loc_1400212AF
0x140020c5d  cmp     esi, 219h
0x140020c63  jnz     short loc_140020C7C
0x140020c65  mov     rax, [rsp+130h+var_C8]
0x140020c6a  add     rax, 0FFFFFFFFFFFF8000h
0x140020c70  test    rax, 0FFFFFFFFFFFFFFFBh
0x140020c76  jz      loc_1400211F4
0x140020c7c  mov     rax, [rbp+47h+var_78]
0x140020c80  mov     r12d, edi
0x140020c83  add     rax, 20h ; ' '
0x140020c87  mov     [rsp+130h+var_E0], edi
0x140020c8b  mov     r14, [rax]
0x140020c8e  mov     [rbp+47h+var_B8], rax
0x140020c92  cmp     r14, rdi
0x140020c95  jz      loc_140020FC0
0x140020c9b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140020ca2  nop     dword ptr [rax+rax+00h]
0x140020ca7  test    rax, rax
0x140020caa  jz      short loc_140020CBB
0x140020cac  mov     rax, [rax]
0x140020caf  test    rax, rax
0x140020cb2  jz      short loc_140020CBB
0x140020cb4  mov     rax, [rax+200h]
0x140020cbb  movzx   r13d, r14w
0x140020cbf  call    cs:__imp_W32GetUserSessionState
0x140020cc6  nop     dword ptr [rax+rax+00h]
0x140020ccb  mov     rcx, [rax+4CF8h]
0x140020cd2  cmp     r13, [rcx+8]
0x140020cd6  jnb     loc_140021036
0x140020cdc  call    cs:__imp_W32GetUserSessionState
0x140020ce3  nop     dword ptr [rax+rax+00h]
0x140020ce8  mov     rbx, rax
0x140020ceb  call    cs:__imp_W32GetUserSessionState
0x140020cf2  nop     dword ptr [rax+rax+00h]
0x140020cf7  mov     rbx, [rbx+4D08h]
0x140020cfe  imul    r13d, [rax+4D10h]
0x140020d06  mov     ecx, r13d
0x140020d09  add     rbx, rcx
0x140020d0c  mov     rcx, rbx
0x140020d0f  call    cs:__imp_HMPkheFromPhe
0x140020d16  nop     dword ptr [rax+rax+00h]
0x140020d1b  shr     r14, 10h
0x140020d1f  mov     r13, rax
0x140020d22  mov     eax, 7FFFh
0x140020d27  and     r14w, ax
0x140020d2b  cmp     r14w, [rbx+1Ah]
0x140020d30  jnz     loc_1400210B4
0x140020d36  test    [rbx+19h], dil
0x140020d3a  jnz     loc_140021036
0x140020d40  cmp     [rbx+18h], dil
0x140020d44  jnz     loc_140021036
0x140020d4a  mov     rbx, [r13+0]
0x140020d4e  xor     r13d, r13d
0x140020d51  test    rbx, rbx
0x140020d54  jz      loc_140021036
0x140020d5a  mov     edx, [r15+4]
0x140020d5e  lea     r8, [rbx+10h]
0x140020d62  mov     r14, [rbp+47h+var_80]
0x140020d66  mov     [rsp+130h+var_D0], r8
0x140020d6b  test    dl, 2
0x140020d6e  jnz     loc_1400210EA
0x140020d74  mov     [rsp+130h+var_D0], r8
0x140020d79  bt      edx, 0Ah
0x140020d7d  jb      loc_140021168
0x140020d83  mov     [rbp+47h+var_BC], r13d
0x140020d87  cmp     [rbp+47h+var_C0], edi
0x140020d8a  jz      loc_140021129
0x140020d90  mov     rax, [rbx+28h]
0x140020d94  movzx   ecx, word ptr [rax+2Ah]
0x140020d98  and     ecx, 0FFFF2FFFh
0x140020d9e  cmp     ecx, 29Ch
0x140020da4  jz      loc_140021036
0x140020daa  call    cs:__imp_W32GetUserSessionState
0x140020db1  nop     dword ptr [rax+rax+00h]
0x140020db6  movzx   edx, word ptr [rax+0A0D2h]
0x140020dbd  mov     rax, [rbx+88h]
0x140020dc4  mov     rcx, [rax+8]
0x140020dc8  cmp     dx, [rcx]
0x140020dcb  jz      loc_140021036
0x140020dd1  mov     rax, [r14+1C0h]
0x140020dd8  mov     rcx, rbx
0x140020ddb  mov     [rbp+47h+BugCheckParameter3], rax
0x140020ddf  lea     rax, [rbp+47h+BugCheckParameter3]
0x140020de3  mov     [r14+1C0h], rax
0x140020dea  mov     [rbp+47h+var_68], rbx
0x140020dee  call    cs:__imp_HMLockObject
0x140020df5  nop     dword ptr [rax+rax+00h]
0x140020dfa  mov     r12d, [r15+4]
0x140020dfe  test    r12b, 10h
0x140020e02  jnz     loc_140020FD1
0x140020e08  bt      r12d, 8
0x140020e0d  jb      loc_140021304
0x140020e13  bt      r12d, 1Dh
0x140020e18  jb      loc_140021043
0x140020e1e  mov     edx, r12d
0x140020e21  mov     [rbp+47h+var_98], r13
0x140020e25  and     edx, 8
0x140020e28  mov     [rsp+130h+InputBuffer], r13
0x140020e2d  mov     [rbp+47h+var_A0], edx
0x140020e30  cmp     esi, 218h
0x140020e36  jz      loc_1400211AE
0x140020e3c  xor     ecx, ecx
0x140020e3e  test    edx, edx
0x140020e40  jz      loc_1400210E2
0x140020e46  mov     eax, r13d
0x140020e49  neg     eax
0x140020e4b  sbb     r14d, r14d
0x140020e4e  and     r14d, 0FFFFF448h
0x140020e55  add     r14d, 1388h
0x140020e5c  test    r13d, r13d
0x140020e5f  jz      short loc_140020EA4
0x140020e61  mov     rcx, [rsp+130h+var_D0]
0x140020e66  mov     rcx, [rcx]
0x140020e69  mov     rcx, [rcx]; Thread
0x140020e6c  call    cs:__imp_PsGetThreadProcessId
0x140020e73  nop     dword ptr [rax+rax+00h]
0x140020e78  xor     r9d, r9d; OutputBuffer
0x140020e7b  mov     [rsp+130h+OutputBufferLength], 0; OutputBufferLength
0x140020e83  lea     rdx, [rsp+130h+InputBuffer]; InputBuffer
0x140020e88  mov     [rsp+130h+InputBuffer], rax
0x140020e8d  lea     r8d, [r9+8]; InputBufferLength
0x140020e91  lea     ecx, [r9+1Eh]; InformationLevel
0x140020e95  call    cs:__imp_ZwPowerInformation
0x140020e9c  nop     dword ptr [rax+rax+00h]
0x140020ea1  mov     edx, [rbp+47h+var_A0]
0x140020ea4  mov     ecx, [r15+4]
0x140020ea8  lea     r9, [rbp+47h+var_60]
0x140020eac  mov     r8, [rsp+130h+var_C8]
0x140020eb1  shr     ecx, 3
0x140020eb4  and     ecx, 8
0x140020eb7  mov     [rsp+130h+var_F0], edi; int
0x140020ebb  neg     edx
0x140020ebd  mov     edx, esi; unsigned int
0x140020ebf  sbb     eax, eax
0x140020ec1  and     eax, 2
0x140020ec4  or      ecx, eax
0x140020ec6  mov     eax, [rbp+47h+arg_28]
0x140020ec9  cmp     [rbp+47h+var_BC], 0
0x140020ecd  mov     [rsp+130h+var_F8], eax; int
0x140020ed1  lea     rax, [rbp+47h+var_98]
0x140020ed5  cmovz   r9, [rbp+47h+var_A8]
0x140020eda  mov     [rsp+130h+Handle], rax; __int64
0x140020edf  mov     dword ptr [rsp+130h+AccessMode], r14d; int
0x140020ee4  mov     [rsp+130h+OutputBufferLength], ecx; int
0x140020ee8  mov     rcx, rbx; struct tagWND *
0x140020eeb  call    xxxSendTransformableMessageTimeout
0x140020ef0  xor     ecx, ecx
0x140020ef2  test    rax, rax
0x140020ef5  jz      loc_1400210A6
0x140020efb  mov     eax, [r15+4]
0x140020eff  test    dil, al
0x140020f02  jnz     loc_14002127A
0x140020f08  mov     r12d, [rsp+130h+var_E0]
0x140020f0d  test    r13d, r13d
0x140020f10  jz      loc_140021330
0x140020f16  mov     rax, [rsp+130h+var_D0]
0x140020f1b  xor     r13d, r13d
0x140020f1e  mov     [rsp+130h+InputBuffer], r13
0x140020f23  mov     rcx, [rax]
0x140020f26  mov     rcx, [rcx]; Thread
0x140020f29  call    cs:__imp_PsGetThreadProcessId
0x140020f30  nop     dword ptr [rax+rax+00h]
0x140020f35  xor     r9d, r9d; OutputBuffer
0x140020f38  mov     [rsp+130h+OutputBufferLength], r13d; OutputBufferLength
0x140020f3d  lea     r8d, [r13+8]; InputBufferLength
0x140020f41  mov     [rsp+130h+InputBuffer], rax
0x140020f46  lea     rdx, [rsp+130h+InputBuffer]; InputBuffer
0x140020f4b  lea     ecx, [r13+1Fh]; InformationLevel
0x140020f4f  call    cs:__imp_ZwPowerInformation
0x140020f56  nop     dword ptr [rax+rax+00h]
0x140020f5b  test    r12d, r12d
0x140020f5e  jnz     loc_140020FF0
0x140020f64  test    dword ptr [r15+4], 200h
0x140020f6c  mov     rax, [rbx]
0x140020f6f  mov     [r15+18h], rax
0x140020f73  jz      short loc_140020FB7
0x140020f75  mov     rcx, [rbx+18h]; Object
0x140020f79  mov     rax, r13
0x140020f7c  mov     [rbp+47h+var_B8], rax
0x140020f80  test    rcx, rcx
0x140020f83  jz      short loc_140020FB3
0x140020f85  lea     rax, [rbp+47h+var_B8]
0x140020f89  mov     r9d, 1F0003h; DesiredAccess
0x140020f8f  mov     [rsp+130h+Handle], rax; Handle
0x140020f94  xor     r8d, r8d; PassedAccessState
0x140020f97  mov     [rsp+130h+AccessMode], dil; AccessMode
0x140020f9c  xor     edx, edx; HandleAttributes
0x140020f9e  mov     qword ptr [rsp+130h+OutputBufferLength], r13; ObjectType
0x140020fa3  call    cs:__imp_ObOpenObjectByPointer
0x140020faa  nop     dword ptr [rax+rax+00h]
0x140020faf  mov     rax, [rbp+47h+var_B8]
0x140020fb3  mov     [r15+10h], rax
0x140020fb7  lea     rcx, [rbp+47h+BugCheckParameter3]; BugCheckParameter3
0x140020fbb  call    ??1?$Win32HMThreadLockAlways@UtagWND@@@@QEAA@XZ; Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>(void)
0x140020fc0  mov     rcx, [rbp+47h+var_78]
0x140020fc4  call    FreeHwndList
0x140020fc9  mov     eax, r12d
0x140020fcc  jmp     loc_140021108
0x140020fd1  mov     eax, [rbp+47h+arg_28]
0x140020fd4  mov     edx, esi; unsigned int
0x140020fd6  mov     r9, [rbp+47h+var_A8]
0x140020fda  mov     rcx, rbx; struct tagWND *
0x140020fdd  mov     r8, [rsp+130h+var_C8]
0x140020fe2  mov     [rsp+130h+OutputBufferLength], eax; int
0x140020fe6  call    _PostTransformableMessageIL
0x140020feb  mov     r12d, [rsp+130h+var_E0]
0x140020ff0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140020ff7  nop     dword ptr [rax+rax+00h]
0x140020ffc  test    rax, rax
0x140020fff  jz      loc_140021338
0x140021005  mov     r8, [rax]; BugCheckParameter2
0x140021008  mov     rcx, [r8+1C0h]
0x14002100f  lea     rax, [rbp+47h+BugCheckParameter3]
0x140021013  cmp     rcx, rax
0x140021016  jnz     loc_1400211C2
0x14002101c  mov     rax, [rcx]
0x14002101f  mov     [r8+1C0h], rax
0x140021026  mov     rcx, [rcx+8]
0x14002102a  call    cs:__imp_HMUnlockObject
0x140021031  nop     dword ptr [rax+rax+00h]
0x140021036  mov     rax, [rbp+47h+var_B8]
0x14002103a  add     rax, 8
0x14002103e  jmp     loc_140020C8B
0x140021043  lea     rcx, [rbp+47h+var_90]; this
0x140021047  mov     [rbp+47h+var_90], r13b
0x14002104b  mov     [rbp+47h+var_88], r13
0x14002104f  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x140021054  cmp     [rbp+47h+arg_28], r13d
0x140021058  mov     eax, r13d
0x14002105b  mov     r9, [rbp+47h+var_A8]
0x14002105f  mov     edx, esi; unsigned int
0x140021061  mov     r8, [rsp+130h+var_C8]
0x140021066  setnz   al
0x140021069  mov     [rsp+130h+var_F0], edi; int
0x14002106d  mov     rcx, rbx; struct tagWND *
0x140021070  mov     [rsp+130h+var_F8], eax; int
0x140021074  mov     dword ptr [rsp+130h+Handle], r13d; int
0x140021079  mov     qword ptr [rsp+130h+AccessMode], rdi; __int64
0x14002107e  mov     qword ptr [rsp+130h+OutputBufferLength], r13; __int64
0x140021083  call    xxxSendMessageCallback
  ... truncated ...
```
