# xxxRealSleepThread(uint,ulong,int,int,SLEEP_STATUS *)

- ea: `0x1400c31e0`
- end: `0x1400c3a57`
- name: `?xxxRealSleepThread@@YAHIKHHPEAW4SLEEP_STATUS@@@Z`
- size: `2167`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int, int, enum SLEEP_STATUS *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400354a0`
- `0x1400c1fc0`
- `0x1401bc3d8`

## callees

- `0x1400b6040`
- `0x1400c2a10`
- `0x1400c31e0`
- `0x1400c4270`
- `0x1400ecb50`
- `0x140107aa8`
- `0x1401084c0`
- `0x140108684`
- `0x140188ea0`
- `0x1401d8940`
- `0x1401f22fc`
- `0x140341ff0`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosError` at `0x140343f54`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140343f54`
- `ntoskrnl!KeClearEvent` at `0x1400c339e`
- `ntoskrnl!KeClearEvent` at `0x1400c3a0e`
- `ntoskrnl!KeClearEvent` at `0x1400c339e`
- `ntoskrnl!KeClearEvent` at `0x1400c3a0e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c373b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c373b`
- `ntoskrnl!KeSetEvent` at `0x1400c35f3`
- `ntoskrnl!KeSetEvent` at `0x1400c3978`
- `ntoskrnl!KeSetEvent` at `0x1400c35f3`
- `ntoskrnl!KeSetEvent` at `0x1400c3978`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400c3586`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400c3586`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3299`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3370`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3299`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c3370`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c3603`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c3603`
- `win32kbase!DCompHitTest` at `0x1400c38ff`
- `win32kbase!DCompHitTest` at `0x1400c38ff`
- `win32kbase!EtwTraceWakeInputIdle` at `0x1400c35d0`
- `win32kbase!EtwTraceWakeInputIdle` at `0x1400c35d0`
- `win32kbase!WakeMIT` at `0x1400c39eb`
- `win32kbase!WakeMIT` at `0x1400c39eb`
- `win32kbase!IsInputThread` at `0x1400c363c`
- `win32kbase!IsInputThread` at `0x1400c3823`
- `win32kbase!IsInputThread` at `0x1400c363c`
- `win32kbase!IsInputThread` at `0x1400c3823`
- `win32kbase!EnterCrit` at `0x1400c3751`
- `win32kbase!EnterCrit` at `0x1400c3751`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c36fb`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c36fb`
- `WIN32K!W32GetUserSessionState` at `0x1400c3479`
- `WIN32K!W32GetUserSessionState` at `0x1400c353e`
- `WIN32K!W32GetUserSessionState` at `0x1400c3655`
- `WIN32K!W32GetUserSessionState` at `0x1400c36a8`
- `WIN32K!W32GetUserSessionState` at `0x1400c37fe`
- `WIN32K!W32GetUserSessionState` at `0x1400c3814`
- `WIN32K!W32GetUserSessionState` at `0x1400c3948`
- `WIN32K!W32GetUserSessionState` at `0x1400c395d`
- `WIN32K!W32GetUserSessionState` at `0x1400c39bb`
- `WIN32K!W32GetUserSessionState` at `0x1400c39d1`
- `WIN32K!W32GetUserSessionState` at `0x1400c39fb`
- `WIN32K!W32GetUserSessionState` at `0x1400c3479`
- `WIN32K!W32GetUserSessionState` at `0x1400c353e`
- `WIN32K!W32GetUserSessionState` at `0x1400c3655`
- `WIN32K!W32GetUserSessionState` at `0x1400c36a8`
- `WIN32K!W32GetUserSessionState` at `0x1400c37fe`
- `WIN32K!W32GetUserSessionState` at `0x1400c3814`
- `WIN32K!W32GetUserSessionState` at `0x1400c3948`
- `WIN32K!W32GetUserSessionState` at `0x1400c395d`
- `WIN32K!W32GetUserSessionState` at `0x1400c39bb`
- `WIN32K!W32GetUserSessionState` at `0x1400c39d1`
- `WIN32K!W32GetUserSessionState` at `0x1400c39fb`

## pseudocode

```c
__int64 __fastcall xxxRealSleepThread(__int64 a1, int a2, int a3, int a4, enum SLEEP_STATUS *a5)
{
  __int64 v5; // rsi
  NTSTATUS v6; // r14d
  int v7; // ebx
  enum SLEEP_STATUS *v8; // r13
  unsigned int v9; // edi
  __int64 *v10; // r12
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v12; // r15
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // ebx
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  unsigned int v20; // r9d
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rax
  _QWORD *CurrentProcessWin32Process; // rax
  _QWORD *v34; // rbx
  __int64 v35; // rax
  struct _KEVENT *v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  char v42; // r12
  ULONG v43; // r13d
  void *v44; // rcx
  unsigned __int64 v45; // rcx
  __int64 v46; // rbx
  union _LARGE_INTEGER *v47; // rdx
  __int64 v48; // rcx
  unsigned __int64 v49; // r9
  BOOL v50; // edi
  int v51; // edx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rbx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r9
  __int64 v64; // rax
  int v65; // ebx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 UserSessionState; // rax
  int v75; // [rsp+44h] [rbp-1D4h]
  unsigned int v76; // [rsp+48h] [rbp-1D0h]
  __int32 v77; // [rsp+4Ch] [rbp-1CCh]
  union _LARGE_INTEGER *Timeout; // [rsp+50h] [rbp-1C8h]
  int v79; // [rsp+58h] [rbp-1C0h] BYREF
  int v80; // [rsp+5Ch] [rbp-1BCh]
  int v81; // [rsp+60h] [rbp-1B8h]
  __int32 v82; // [rsp+74h] [rbp-1A4h]
  int v83; // [rsp+78h] [rbp-1A0h]
  __int64 v84; // [rsp+80h] [rbp-198h] BYREF
  enum SLEEP_STATUS *v85; // [rsp+88h] [rbp-190h]
  PVOID Object[2]; // [rsp+90h] [rbp-188h] BYREF
  __int64 v87; // [rsp+A0h] [rbp-178h]
  int v88; // [rsp+B0h] [rbp-168h] BYREF
  __int64 v89; // [rsp+B4h] [rbp-164h]
  __int64 v90; // [rsp+BCh] [rbp-15Ch]
  __int64 v91; // [rsp+C4h] [rbp-154h]
  __int64 v92; // [rsp+CCh] [rbp-14Ch]
  __int64 v93; // [rsp+D4h] [rbp-144h]
  int v94; // [rsp+DCh] [rbp-13Ch]
  __int64 v95; // [rsp+E0h] [rbp-138h]
  __int64 v96; // [rsp+E8h] [rbp-130h]
  int v97; // [rsp+F0h] [rbp-128h]
  unsigned __int64 v98; // [rsp+F4h] [rbp-124h]
  int v99; // [rsp+FCh] [rbp-11Ch]
  _BYTE v100[112]; // [rsp+100h] [rbp-118h] BYREF
  _OWORD v101[7]; // [rsp+170h] [rbp-A8h] BYREF

  v80 = a4;
  v81 = a3;
  v5 = 0;
  v84 = 0;
  v6 = 0;
  v7 = a1 & 0x8000;
  v75 = v7;
  *(_OWORD *)Object = 0;
  v79 = 0;
  v8 = (enum SLEEP_STATUS *)&v79;
  if ( a5 )
    v8 = a5;
  v85 = v8;
  *(_DWORD *)v8 = 0;
  v9 = a1 & 0xFFFF7FFF;
  if ( (a1 & 0x8000) == 0 )
    v9 = a1;
  v76 = v9;
  if ( a2 )
  {
    a1 = -10000LL * a2;
    v84 = a1;
    v10 = &v84;
  }
  else
  {
    v10 = 0;
  }
  Timeout = (union _LARGE_INTEGER *)v10;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(a1);
  if ( CurrentThreadWin32Thread )
    v5 = *CurrentThreadWin32Thread;
  v12 = v5 + 480;
  v87 = v5 + 480;
  v77 = *(_DWORD *)(*(_QWORD *)(v5 + 480) + 16LL);
  v82 = v77;
LABEL_11:
  v13 = 0xFFFFF78000000004uLL;
  v14 = 0xFFFFF78000000320uLL;
  while ( (v9 & *(_DWORD *)(*(_QWORD *)v12 + 4LL)) == 0 && (!v80 || (v9 & *(_DWORD *)(*(_QWORD *)v12 + 8LL)) == 0) )
  {
    if ( *(_DWORD *)v8 == 2 )
      goto LABEL_27;
    if ( !v7 && (*(_DWORD *)(*(_QWORD *)v12 + 8LL) & 0x40) != 0 )
    {
      do
        xxxReceiveMessage((struct tagTHREADINFO *)v5);
      while ( (*(_DWORD *)(*(_QWORD *)v12 + 8LL) & 0x40) != 0 );
      v14 = *(_DWORD *)(*(_QWORD *)v12 + 8LL) & (unsigned int)*(unsigned __int16 *)(v5 + 912);
      _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v12 + 4LL), v14);
      *(_WORD *)(v5 + 912) = 0;
    }
    xxxDoSysExpungeIfNeeded(v5, v14, v13);
    v16 = 0;
    if ( !v75 )
      v16 = 64;
    v17 = (__int64 *)PsGetCurrentThreadWin32Thread(v15);
    if ( v17 )
      v18 = *v17;
    else
      v18 = 0;
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(v18 + 480) + 16LL), v16 | (unsigned __int16)v9);
    KeClearEvent(*(PRKEVENT *)(v18 + 760));
    if ( v6 == 258 )
    {
      UserSetLastError(1460);
      *(_DWORD *)v8 = 1;
LABEL_27:
      v20 = 0;
      goto LABEL_28;
    }
    if ( v6 == 192 )
    {
      ClientDeliverUserApc();
      goto LABEL_27;
    }
    v22 = *(unsigned int *)(*(_QWORD *)v12 + 16LL);
    v14 = 0xFFFFF78000000320uLL;
    v13 = 0xFFFFF78000000004uLL;
    v7 = v75;
    if ( (*(_DWORD *)(*(_QWORD *)v12 + 4LL) & (unsigned int)v22) == 0 )
    {
      if ( v5 != *(_QWORD *)(W32GetUserSessionState(v22, 0xFFFFF78000000320uLL, 0xFFFFF78000000004uLL, v19) + 68464)
        || (v9 & 0x200) == 0
        || v10 )
      {
        v26 = v81;
        if ( v81 )
        {
          v27 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v5 + 520), 0, 0) & 0x400) != 0
            && (int)CheckProcessForeground((struct tagTHREADINFO *)v5) < 0 )
          {
            goto LABEL_27;
          }
          *(_QWORD *)(*(_QWORD *)(v5 + 512) + 8LL) = 0;
          if ( v26 )
          {
            if ( v5 == *(_QWORD *)(W32GetUserSessionState(v27, v23, v24, v25) + 18984) )
            {
              v32 = *(__int64 **)(v5 + 496);
              v29 = *v32;
              v28 = (unsigned int)(*(_DWORD *)(v5 + 712) | *(_DWORD *)(*v32 + 16));
              if ( ((*(_WORD *)(v5 + 712) | *(_WORD *)(*v32 + 16)) & 0x1000) != 0 )
                xxxCallHook(0, 0, 0, 11);
            }
            CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process(v29, v28, v30, v31);
            v34 = CurrentProcessWin32Process;
            if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
              v34 = 0;
            v35 = *(_QWORD *)(v5 + 456);
            if ( !*(_QWORD *)(v35 + 336) )
              *(_QWORD *)(v35 + 336) = v5;
            if ( *(_QWORD *)(*(_QWORD *)(v5 + 456) + 336LL) == v5 )
            {
              EtwTraceWakeInputIdle(0, v5);
              v36 = (struct _KEVENT *)v34[2];
              if ( !v36 )
                goto LABEL_55;
              if ( v36 != (struct _KEVENT *)-1LL )
              {
                KeSetEvent(v36, 1, 0);
                ObfDereferenceObject((PVOID)v34[2]);
LABEL_55:
                v34[2] = -1;
              }
            }
            v37 = *((_DWORD *)v34 + 3);
            if ( (v37 & 4) != 0 )
            {
              *((_DWORD *)v34 + 3) = v37 & 0xFFFFFFFB;
              zzzCalcStartCursorHide(0, 0);
            }
          }
        }
        Object[0] = *(PVOID *)(v5 + 1608);
        if ( (unsigned __int8)IsInputThread() && (v9 & 0x200) != 0 )
        {
          v42 = 1;
          Object[1] = *(PVOID *)(W32GetUserSessionState(v39, v38, v40, v41) + 18864);
          v43 = 2;
        }
        else
        {
          v43 = 1;
          v42 = 0;
        }
        v44 = *(void **)(v5 + 1576);
        if ( v44 && (v9 & 0xFFFF7DFF) != 0 )
          Object[v43++] = v44;
        if ( v42 )
          *(_DWORD *)(W32GetUserSessionState(v44, v38, v40, v41) + 63960) = 1;
        v83 = 0;
        while ( 1 )
        {
          v45 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
          v46 = (v45 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          UserSessionSwitchLeaveCrit(v45, v46, v40);
          v6 = KeWaitForMultipleObjects(v43, Object, WaitAny, WrUserRequest, 1, 0, Timeout, 0);
          EnterCrit(1, 0);
          v50 = 0;
          if ( !v6 )
          {
            if ( (unsigned int)xxxRemoveQueueCompletion() )
            {
              v48 = v9 & *(_DWORD *)(*(_QWORD *)v12 + 8LL);
              if ( ((unsigned __int8)v9 & *(_BYTE *)(*(_QWORD *)v12 + 8LL) & 8) == 0 )
                v50 = 1;
            }
          }
          if ( v6 == 1 )
          {
            if ( v42 )
            {
              v49 = 0xFFFFF78000000004uLL;
              v40 = 0xFFFFF78000000320uLL;
              if ( (unsigned __int64)(((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                                      * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
                                    - v46) >= 0x10 )
                v51 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                      * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
                    - v46;
              else
                v51 = 16;
              v48 = -10000LL * v51;
              v47 = Timeout;
              if ( v48 <= Timeout->QuadPart )
              {
                v65 = 1;
                v6 = 258;
LABEL_90:
                if ( v42 )
                {
                  *(_DWORD *)(W32GetUserSessionState(v48, v47, v40, v49) + 63960) = 0;
                  if ( *(_DWORD *)(W32GetUserSessionState(v67, v66, v68, v69) + 63964) )
                  {
                    WakeMIT(2);
                    if ( !v65 )
                    {
                      UserSessionState = W32GetUserSessionState(v71, v70, v72, v73);
                      KeClearEvent(*(PRKEVENT *)(UserSessionState + 18864));
                    }
                  }
                }
                SleepInputIdle(v5);
                v9 = v76;
                v10 = (__int64 *)Timeout;
                v8 = v85;
                v7 = v75;
                goto LABEL_11;
              }
              Timeout->QuadPart -= v48;
              *(_DWORD *)(W32GetUserSessionState(v48, Timeout, 0xFFFFF78000000320uLL, 0xFFFFF78000000004uLL) + 63964) = 0;
              v56 = W32GetUserSessionState(v53, v52, v54, v55);
              if ( (unsigned __int8)IsInputThread() )
              {
                v89 = 0;
                v90 = 0;
                v92 = 0;
                v93 = 0;
                v94 = 0;
                v96 = 0;
                memset(v101, 0, sizeof(v101));
                v88 = *(_DWORD *)(v56 + 19052);
                v91 = *(_QWORD *)(v56 + 19044);
                v95 = 0;
                v97 = 0;
                v98 = 0xFFFFFFFE00000000uLL;
                v99 = 0;
                DCompHitTest(v100, &v88, v101);
              }
              if ( !*(_DWORD *)(v56 + 19056) )
              {
                *(_OWORD *)(v56 + 19040) = 0;
                *(_OWORD *)(v56 + 19056) = 0;
                *(_OWORD *)(v56 + 19072) = 0;
                *(_OWORD *)(v56 + 19088) = 0;
                *(_OWORD *)(v56 + 19104) = 0;
                *(_OWORD *)(v56 + 19120) = 0;
                *(_OWORD *)(v56 + 19136) = 0;
              }
              if ( *(_BYTE *)(W32GetUserSessionState(v58, v57, v59, v60) + 18892) )
              {
                v64 = W32GetUserSessionState(v62, v61, v40, v63);
                KeSetEvent(*(PRKEVENT *)(v64 + 18904), 1, 0);
              }
            }
            else
            {
              *(_DWORD *)v85 = 2;
              v84 = -100000;
            }
          }
          else if ( !v50 )
          {
            v65 = v83;
            goto LABEL_90;
          }
          v9 = v76;
        }
      }
      v6 = xxxDesktopThreadWaiter(0, v9);
      v14 = 0xFFFFF78000000320uLL;
      v13 = 0xFFFFF78000000004uLL;
      if ( v6 == -1073741790 )
        goto LABEL_27;
    }
  }
  v20 = 1;
LABEL_28:
  _InterlockedExchange((volatile __int32 *)(*(_QWORD *)v12 + 16LL), v77);
  if ( v20 )
    _InterlockedExchange(
      (volatile __int32 *)(*(_QWORD *)v12 + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  return v20;
}

```

## disassembly

```asm
0x1400c31e0  mov     [rsp+arg_0], rbx
0x1400c31e5  mov     [rsp+arg_10], rsi
0x1400c31ea  push    rdi
0x1400c31eb  push    r12
0x1400c31ed  push    r13
0x1400c31ef  push    r14
0x1400c31f1  push    r15
0x1400c31f3  sub     rsp, 1F0h
0x1400c31fa  mov     rax, cs:__security_cookie
0x1400c3201  xor     rax, rsp
0x1400c3204  mov     [rsp+218h+var_38], rax
0x1400c320c  mov     [rsp+218h+var_1BC], r9d
0x1400c3211  mov     [rsp+218h+var_1B8], r8d
0x1400c3216  mov     rax, [rsp+218h+arg_20]
0x1400c321e  xor     esi, esi
0x1400c3220  mov     [rsp+218h+var_198], rsi
0x1400c3228  mov     r14d, esi
0x1400c322b  mov     ebx, ecx
0x1400c322d  and     ebx, 8000h
0x1400c3233  mov     [rsp+218h+var_1D4], ebx
0x1400c3237  mov     [rsp+218h+var_1D8], esi
0x1400c323b  xorps   xmm0, xmm0
0x1400c323e  movups  xmmword ptr [rsp+218h+Object], xmm0
0x1400c3246  mov     [rsp+218h+var_1C0], esi
0x1400c324a  lea     r13, [rsp+218h+var_1C0]
0x1400c324f  test    rax, rax
0x1400c3252  cmovnz  r13, rax
0x1400c3256  mov     [rsp+218h+var_190], r13
0x1400c325e  mov     [r13+0], esi
0x1400c3262  mov     edi, ecx
0x1400c3264  btr     edi, 0Fh
0x1400c3268  test    ebx, ebx
0x1400c326a  cmovz   edi, ecx
0x1400c326d  mov     [rsp+218h+var_1D0], edi
0x1400c3271  test    edx, edx
0x1400c3273  jz      short loc_1400C3291
0x1400c3275  movsxd  rax, edx
0x1400c3278  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1400c327f  mov     [rsp+218h+var_198], rcx
0x1400c3287  lea     r12, [rsp+218h+var_198]
0x1400c328f  jmp     short loc_1400C3294
0x1400c3291  mov     r12, rsi
0x1400c3294  mov     [rsp+218h+var_1C8], r12
0x1400c3299  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c32a0  nop     dword ptr [rax+rax+00h]
0x1400c32a5  test    rax, rax
0x1400c32a8  jz      short loc_1400C32AD
0x1400c32aa  mov     rsi, [rax]
0x1400c32ad  lea     r15, [rsi+1E0h]
0x1400c32b4  mov     [rsp+218h+var_178], r15
0x1400c32bc  mov     rax, [r15]
0x1400c32bf  mov     ecx, [rax+10h]
0x1400c32c2  mov     [rsp+218h+var_1CC], ecx
0x1400c32c6  mov     [rsp+218h+var_1A4], ecx
0x1400c32ca  mov     r8, 0FFFFF78000000004h
0x1400c32d4  mov     rdx, 0FFFFF78000000320h
0x1400c32de  xchg    ax, ax
0x1400c32e0  mov     rax, [r15]
0x1400c32e3  mov     ecx, [rax+4]
0x1400c32e6  test    ecx, edi
0x1400c32e8  jnz     loc_1400C3A4C
0x1400c32ee  cmp     [rsp+218h+var_1BC], 0
0x1400c32f3  jz      short loc_1400C3303
0x1400c32f5  mov     rax, [r15]
0x1400c32f8  mov     ecx, [rax+8]
0x1400c32fb  test    ecx, edi
0x1400c32fd  jnz     loc_1400C3A4C
0x1400c3303  cmp     dword ptr [r13+0], 2
0x1400c3308  jz      loc_1400C33E4
0x1400c330e  test    ebx, ebx
0x1400c3310  jnz     short loc_1400C335A
0x1400c3312  mov     rax, [r15]
0x1400c3315  mov     ecx, [rax+8]
0x1400c3318  test    cl, 40h
0x1400c331b  jz      short loc_1400C335A
0x1400c331d  mov     rax, [r15]
0x1400c3320  mov     ecx, [rax+8]
0x1400c3323  test    cl, 40h
0x1400c3326  jz      short loc_1400C333B
0x1400c3328  mov     rcx, rsi; struct tagTHREADINFO *
0x1400c332b  call    ?xxxReceiveMessage@@YAXPEAUtagTHREADINFO@@@Z; xxxReceiveMessage(tagTHREADINFO *)
0x1400c3330  mov     rax, [r15]
0x1400c3333  mov     ecx, [rax+8]
0x1400c3336  test    cl, 40h
0x1400c3339  jnz     short loc_1400C3328
0x1400c333b  mov     rax, [r15]
0x1400c333e  mov     ecx, [rax+8]
0x1400c3341  movzx   edx, word ptr [rsi+390h]
0x1400c3348  and     edx, ecx
0x1400c334a  mov     rax, [r15]
0x1400c334d  lock or [rax+4], edx
0x1400c3351  xor     eax, eax
0x1400c3353  mov     [rsi+390h], ax
0x1400c335a  mov     rcx, rsi
0x1400c335d  call    xxxDoSysExpungeIfNeeded
0x1400c3362  xor     ebx, ebx
0x1400c3364  cmp     [rsp+218h+var_1D4], ebx
0x1400c3368  mov     eax, 40h ; '@'
0x1400c336d  cmovz   ebx, eax
0x1400c3370  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c3377  nop     dword ptr [rax+rax+00h]
0x1400c337c  test    rax, rax
0x1400c337f  jz      short loc_1400C3386
0x1400c3381  mov     rcx, [rax]
0x1400c3384  jmp     short loc_1400C3388
0x1400c3386  xor     ecx, ecx
0x1400c3388  movzx   edx, di
0x1400c338b  or      edx, ebx
0x1400c338d  mov     rax, [rcx+1E0h]
0x1400c3394  xchg    edx, [rax+10h]
0x1400c3397  mov     rcx, [rcx+2F8h]; Event
0x1400c339e  call    cs:__imp_KeClearEvent
0x1400c33a5  nop     dword ptr [rax+rax+00h]
0x1400c33aa  cmp     r14d, 102h
0x1400c33b1  jnz     loc_1400C343D
0x1400c33b7  mov     ecx, 5B4h
0x1400c33bc  call    UserSetLastError
0x1400c33c1  mov     dword ptr [r13+0], 1
0x1400c33c9  nop     dword ptr [rax+00000000h]
0x1400c33d0  mov     rdx, 0FFFFF78000000320h
0x1400c33da  mov     r8, 0FFFFF78000000004h
0x1400c33e4  mov     r9d, [rsp+218h+var_1D8]
0x1400c33e9  mov     rax, [r15]
0x1400c33ec  mov     ecx, [rsp+218h+var_1CC]
0x1400c33f0  xchg    ecx, [rax+10h]
0x1400c33f3  test    r9d, r9d
0x1400c33f6  jz      short loc_1400C340C
0x1400c33f8  mov     rcx, [rdx]
0x1400c33fb  mov     edx, [r8]
0x1400c33fe  imul    rdx, rcx
0x1400c3402  shr     rdx, 18h
0x1400c3406  mov     rcx, [r15]
0x1400c3409  xchg    edx, [rcx+14h]
0x1400c340c  mov     eax, r9d
0x1400c340f  mov     rcx, [rsp+218h+var_38]
0x1400c3417  xor     rcx, rsp; StackCookie
0x1400c341a  call    __security_check_cookie
0x1400c341f  lea     r11, [rsp+218h+var_28]
0x1400c3427  mov     rbx, [r11+30h]
0x1400c342b  mov     rsi, [r11+40h]
0x1400c342f  mov     rsp, r11
0x1400c3432  pop     r15
0x1400c3434  pop     r14
0x1400c3436  pop     r13
0x1400c3438  pop     r12
0x1400c343a  pop     rdi
0x1400c343b  retn
0x1400c343d  cmp     r14d, 0C0h
0x1400c3444  jnz     short loc_1400C344D
0x1400c3446  call    ClientDeliverUserApc
0x1400c344b  jmp     short loc_1400C33D0
0x1400c344d  mov     rax, [r15]
0x1400c3450  mov     edx, [rax+4]
0x1400c3453  mov     rax, [r15]
0x1400c3456  mov     ecx, [rax+10h]
0x1400c3459  test    ecx, edx
0x1400c345b  mov     rdx, 0FFFFF78000000320h
0x1400c3465  mov     r8, 0FFFFF78000000004h
0x1400c346f  mov     ebx, [rsp+218h+var_1D4]
0x1400c3473  jnz     loc_1400C32E0
0x1400c3479  call    cs:__imp_W32GetUserSessionState
0x1400c3480  nop     dword ptr [rax+rax+00h]
0x1400c3485  cmp     rsi, [rax+10B70h]
0x1400c348c  jnz     short loc_1400C34C9
0x1400c348e  bt      edi, 9
0x1400c3492  jnb     short loc_1400C34C9
0x1400c3494  test    r12, r12
0x1400c3497  jnz     short loc_1400C34C9
0x1400c3499  mov     edx, edi
0x1400c349b  xor     ecx, ecx
0x1400c349d  call    xxxDesktopThreadWaiter
0x1400c34a2  mov     r14d, eax
0x1400c34a5  mov     rdx, 0FFFFF78000000320h
0x1400c34af  mov     r8, 0FFFFF78000000004h
0x1400c34b9  cmp     eax, 0C0000022h
0x1400c34be  jz      loc_1400C33E4
0x1400c34c4  jmp     loc_1400C32E0
0x1400c34c9  mov     ebx, [rsp+218h+var_1B8]
0x1400c34cd  test    ebx, ebx
0x1400c34cf  jz      loc_1400C362D
0x1400c34d5  xor     ecx, ecx
0x1400c34d7  xor     eax, eax
0x1400c34d9  lock cmpxchg [rsi+208h], ecx
0x1400c34e1  bt      eax, 0Ah
0x1400c34e5  jnb     short loc_1400C34F7
0x1400c34e7  mov     rcx, rsi; struct tagTHREADINFO *
0x1400c34ea  call    ?CheckProcessForeground@@YAJPEAUtagTHREADINFO@@@Z; CheckProcessForeground(tagTHREADINFO *)
0x1400c34ef  test    eax, eax
0x1400c34f1  js      loc_1400C33D0
0x1400c34f7  mov     rax, [rsi+200h]
0x1400c34fe  mov     qword ptr [rax+8], 0
0x1400c3506  jmp     short loc_1400C3536
0x1400c3508  mov     rdx, 0FFFFF78000000320h
0x1400c3512  mov     r8, 0FFFFF78000000004h
0x1400c351c  mov     eax, [rsp+218h+var_1A4]
0x1400c3520  mov     [rsp+218h+var_1CC], eax
0x1400c3524  mov     r15, [rsp+218h+var_178]
0x1400c352c  mov     r9d, [rsp+218h+var_1D8]
0x1400c3531  jmp     loc_1400C33E9
0x1400c3536  test    ebx, ebx
0x1400c3538  jz      loc_1400C362D
0x1400c353e  call    cs:__imp_W32GetUserSessionState
0x1400c3545  nop     dword ptr [rax+rax+00h]
0x1400c354a  cmp     rsi, [rax+4A28h]
0x1400c3551  jnz     short loc_1400C357E
0x1400c3553  mov     rax, [rsi+1F0h]
0x1400c355a  mov     rcx, [rax]
0x1400c355d  mov     edx, [rcx+10h]
0x1400c3560  or      edx, [rsi+2C8h]
0x1400c3566  bt      edx, 0Ch
0x1400c356a  jnb     short loc_1400C357E
0x1400c356c  mov     r9d, 0Bh; int
0x1400c3572  xor     r8d, r8d; __int64
0x1400c3575  xor     edx, edx; unsigned __int64
0x1400c3577  xor     ecx, ecx; int
0x1400c3579  call    ?xxxCallHook@@YAHH_K_JH@Z; xxxCallHook(int,unsigned __int64,__int64,int)
0x1400c357e  test    ebx, ebx
0x1400c3580  jz      loc_1400C362D
0x1400c3586  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400c358d  nop     dword ptr [rax+rax+00h]
0x1400c3592  mov     rbx, rax
0x1400c3595  test    rax, rax
0x1400c3598  jz      short loc_1400C35A3
0x1400c359a  xor     ecx, ecx
0x1400c359c  cmp     [rax], rcx
0x1400c359f  cmovz   rbx, rcx
0x1400c35a3  mov     rax, [rsi+1C8h]
0x1400c35aa  cmp     qword ptr [rax+150h], 0
0x1400c35b2  jnz     short loc_1400C35BB
0x1400c35b4  mov     [rax+150h], rsi
0x1400c35bb  mov     rax, [rsi+1C8h]
0x1400c35c2  cmp     [rax+150h], rsi
0x1400c35c9  jnz     short loc_1400C3617
0x1400c35cb  mov     rdx, rsi
0x1400c35ce  xor     ecx, ecx
0x1400c35d0  call    cs:__imp_EtwTraceWakeInputIdle
0x1400c35d7  nop     dword ptr [rax+rax+00h]
0x1400c35dc  mov     rcx, [rbx+10h]; Event
0x1400c35e0  test    rcx, rcx
0x1400c35e3  jz      short loc_1400C360F
0x1400c35e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400c35e9  jz      short loc_1400C3617
0x1400c35eb  xor     r8d, r8d; Wait
0x1400c35ee  mov     edx, 1; Increment
0x1400c35f3  call    cs:__imp_KeSetEvent
0x1400c35fa  nop     dword ptr [rax+rax+00h]
0x1400c35ff  mov     rcx, [rbx+10h]; Object
0x1400c3603  call    cs:__imp_ObfDereferenceObject
0x1400c360a  nop     dword ptr [rax+rax+00h]
0x1400c360f  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1400c3617  mov     eax, [rbx+0Ch]
0x1400c361a  test    al, 4
0x1400c361c  jz      short loc_1400C362D
0x1400c361e  and     eax, 0FFFFFFFBh
0x1400c3621  mov     [rbx+0Ch], eax
0x1400c3624  xor     edx, edx
0x1400c3626  xor     ecx, ecx
0x1400c3628  call    zzzCalcStartCursorHide
0x1400c362d  mov     rax, [rsi+648h]
0x1400c3634  mov     [rsp+218h+Object], rax
0x1400c363c  call    cs:__imp_IsInputThread
0x1400c3643  nop     dword ptr [rax+rax+00h]
0x1400c3648  test    al, al
0x1400c364a  jz      short loc_1400C3678
0x1400c364c  bt      edi, 9
0x1400c3650  jnb     short loc_1400C3678
0x1400c3652  mov     r12b, 1
0x1400c3655  call    cs:__imp_W32GetUserSessionState
0x1400c365c  nop     dword ptr [rax+rax+00h]
0x1400c3661  mov     rcx, [rax+49B0h]
0x1400c3668  mov     [rsp+218h+Object+8], rcx
0x1400c3670  mov     r13d, 2
0x1400c3676  jmp     short loc_1400C3681
0x1400c3678  mov     r13d, 1
0x1400c367e  xor     r12b, r12b
0x1400c3681  mov     rcx, [rsi+628h]
0x1400c3688  test    rcx, rcx
0x1400c368b  jz      short loc_1400C36A3
0x1400c368d  test    edi, 0FFFF7DFFh
0x1400c3693  jz      short loc_1400C36A3
0x1400c3695  mov     eax, r13d
0x1400c3698  mov     [rsp+rax*8+218h+Object], rcx
0x1400c36a0  inc     r13d
0x1400c36a3  test    r12b, r12b
0x1400c36a6  jz      short loc_1400C36BE
0x1400c36a8  call    cs:__imp_W32GetUserSessionState
0x1400c36af  nop     dword ptr [rax+rax+00h]
0x1400c36b4  mov     dword ptr [rax+0F9D8h], 1
0x1400c36be  mov     [rsp+218h+var_1A0], 0
0x1400c36c6  jmp     short loc_1400C36D4
0x1400c36d0  mov     edi, [rsp+218h+var_1D0]
0x1400c36d4  mov     rax, 0FFFFF78000000004h
0x1400c36de  mov     ecx, [rax]
0x1400c36e0  mov     rax, 0FFFFF78000000320h
0x1400c36ea  mov     rax, [rax]
0x1400c36ed  shl     rax, 8
0x1400c36f1  shl     rcx, 20h
0x1400c36f5  mul     rcx
0x1400c36f8  mov     rbx, rdx
0x1400c36fb  call    cs:__imp_UserSessionSwitchLeaveCrit
  ... truncated ...
```
