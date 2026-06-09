# xxxRealSleepThread(uint,ulong,int,int,SLEEP_STATUS *)

- ea: `0x1400e9390`
- end: `0x1400e9c07`
- name: `?xxxRealSleepThread@@YAHIKHHPEAW4SLEEP_STATUS@@@Z`
- size: `2167`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int, int, enum SLEEP_STATUS *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140030e20`
- `0x1400e81d0`
- `0x1401b41e8`

## callees

- `0x14007fc08`
- `0x140080620`
- `0x1400807e4`
- `0x1400dc2d0`
- `0x1400e8c20`
- `0x1400e9390`
- `0x1400ea480`
- `0x14017e680`
- `0x14018f810`
- `0x1401d5398`
- `0x1401f67dc`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosError` at `0x140345574`
- `ntoskrnl!RtlNtStatusToDosError` at `0x140345574`
- `ntoskrnl!KeClearEvent` at `0x1400e954e`
- `ntoskrnl!KeClearEvent` at `0x1400e9bbe`
- `ntoskrnl!KeClearEvent` at `0x1400e954e`
- `ntoskrnl!KeClearEvent` at `0x1400e9bbe`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400e98eb`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400e98eb`
- `ntoskrnl!KeSetEvent` at `0x1400e97a3`
- `ntoskrnl!KeSetEvent` at `0x1400e9b28`
- `ntoskrnl!KeSetEvent` at `0x1400e97a3`
- `ntoskrnl!KeSetEvent` at `0x1400e9b28`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400e9736`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400e9736`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e9449`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e9520`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e9449`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400e9520`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e97b3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e97b3`
- `win32kbase!DCompHitTest` at `0x1400e9aaf`
- `win32kbase!DCompHitTest` at `0x1400e9aaf`
- `win32kbase!EtwTraceWakeInputIdle` at `0x1400e9780`
- `win32kbase!EtwTraceWakeInputIdle` at `0x1400e9780`
- `win32kbase!WakeMIT` at `0x1400e9b9b`
- `win32kbase!WakeMIT` at `0x1400e9b9b`
- `win32kbase!IsInputThread` at `0x1400e97ec`
- `win32kbase!IsInputThread` at `0x1400e99d3`
- `win32kbase!IsInputThread` at `0x1400e97ec`
- `win32kbase!IsInputThread` at `0x1400e99d3`
- `win32kbase!EnterCrit` at `0x1400e9901`
- `win32kbase!EnterCrit` at `0x1400e9901`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e98ab`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400e98ab`
- `WIN32K!W32GetUserSessionState` at `0x1400e9629`
- `WIN32K!W32GetUserSessionState` at `0x1400e96ee`
- `WIN32K!W32GetUserSessionState` at `0x1400e9805`
- `WIN32K!W32GetUserSessionState` at `0x1400e9858`
- `WIN32K!W32GetUserSessionState` at `0x1400e99ae`
- `WIN32K!W32GetUserSessionState` at `0x1400e99c4`
- `WIN32K!W32GetUserSessionState` at `0x1400e9af8`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b0d`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b6b`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b81`
- `WIN32K!W32GetUserSessionState` at `0x1400e9bab`
- `WIN32K!W32GetUserSessionState` at `0x1400e9629`
- `WIN32K!W32GetUserSessionState` at `0x1400e96ee`
- `WIN32K!W32GetUserSessionState` at `0x1400e9805`
- `WIN32K!W32GetUserSessionState` at `0x1400e9858`
- `WIN32K!W32GetUserSessionState` at `0x1400e99ae`
- `WIN32K!W32GetUserSessionState` at `0x1400e99c4`
- `WIN32K!W32GetUserSessionState` at `0x1400e9af8`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b0d`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b6b`
- `WIN32K!W32GetUserSessionState` at `0x1400e9b81`
- `WIN32K!W32GetUserSessionState` at `0x1400e9bab`

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
  unsigned int v19; // r9d
  __int64 v21; // rcx
  int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 *v25; // rax
  _QWORD *CurrentProcessWin32Process; // rax
  _QWORD *v27; // rbx
  __int64 v28; // rax
  struct _KEVENT *v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  char v32; // r12
  ULONG v33; // r13d
  void *v34; // rcx
  unsigned __int64 v35; // rcx
  __int64 v36; // rbx
  __int64 v37; // rcx
  BOOL v38; // edi
  int v39; // edx
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // ebx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 UserSessionState; // rax
  int v49; // [rsp+44h] [rbp-1D4h]
  unsigned int v50; // [rsp+48h] [rbp-1D0h]
  __int32 v51; // [rsp+4Ch] [rbp-1CCh]
  union _LARGE_INTEGER *Timeout; // [rsp+50h] [rbp-1C8h]
  int v53; // [rsp+58h] [rbp-1C0h] BYREF
  int v54; // [rsp+5Ch] [rbp-1BCh]
  int v55; // [rsp+60h] [rbp-1B8h]
  __int32 v56; // [rsp+74h] [rbp-1A4h]
  int v57; // [rsp+78h] [rbp-1A0h]
  __int64 v58; // [rsp+80h] [rbp-198h] BYREF
  enum SLEEP_STATUS *v59; // [rsp+88h] [rbp-190h]
  PVOID Object[2]; // [rsp+90h] [rbp-188h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-178h]
  int v62; // [rsp+B0h] [rbp-168h] BYREF
  __int64 v63; // [rsp+B4h] [rbp-164h]
  __int64 v64; // [rsp+BCh] [rbp-15Ch]
  __int64 v65; // [rsp+C4h] [rbp-154h]
  __int64 v66; // [rsp+CCh] [rbp-14Ch]
  __int64 v67; // [rsp+D4h] [rbp-144h]
  int v68; // [rsp+DCh] [rbp-13Ch]
  __int64 v69; // [rsp+E0h] [rbp-138h]
  __int64 v70; // [rsp+E8h] [rbp-130h]
  int v71; // [rsp+F0h] [rbp-128h]
  unsigned __int64 v72; // [rsp+F4h] [rbp-124h]
  int v73; // [rsp+FCh] [rbp-11Ch]
  _BYTE v74[112]; // [rsp+100h] [rbp-118h] BYREF
  _OWORD v75[7]; // [rsp+170h] [rbp-A8h] BYREF

  v54 = a4;
  v55 = a3;
  v5 = 0;
  v58 = 0;
  v6 = 0;
  v7 = a1 & 0x8000;
  v49 = v7;
  *(_OWORD *)Object = 0;
  v53 = 0;
  v8 = (enum SLEEP_STATUS *)&v53;
  if ( a5 )
    v8 = a5;
  v59 = v8;
  *(_DWORD *)v8 = 0;
  v9 = a1 & 0xFFFF7FFF;
  if ( (a1 & 0x8000) == 0 )
    v9 = a1;
  v50 = v9;
  if ( a2 )
  {
    a1 = -10000LL * a2;
    v58 = a1;
    v10 = &v58;
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
  v61 = v5 + 480;
  v51 = *(_DWORD *)(*(_QWORD *)(v5 + 480) + 16LL);
  v56 = v51;
LABEL_11:
  v13 = 0xFFFFF78000000004uLL;
  v14 = 0xFFFFF78000000320uLL;
  while ( (v9 & *(_DWORD *)(*(_QWORD *)v12 + 4LL)) == 0 && (!v54 || (v9 & *(_DWORD *)(*(_QWORD *)v12 + 8LL)) == 0) )
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
    if ( !v49 )
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
      v19 = 0;
      goto LABEL_28;
    }
    if ( v6 == 192 )
    {
      ClientDeliverUserApc();
      goto LABEL_27;
    }
    v21 = *(unsigned int *)(*(_QWORD *)v12 + 16LL);
    v14 = 0xFFFFF78000000320uLL;
    v13 = 0xFFFFF78000000004uLL;
    v7 = v49;
    if ( (*(_DWORD *)(*(_QWORD *)v12 + 4LL) & (unsigned int)v21) == 0 )
    {
      if ( v5 != *(_QWORD *)(W32GetUserSessionState(v21) + 68464) || (v9 & 0x200) == 0 || v10 )
      {
        v22 = v55;
        if ( v55 )
        {
          v23 = 0;
          if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v5 + 520), 0, 0) & 0x400) != 0
            && (int)CheckProcessForeground((struct tagTHREADINFO *)v5) < 0 )
          {
            goto LABEL_27;
          }
          *(_QWORD *)(*(_QWORD *)(v5 + 512) + 8LL) = 0;
          if ( v22 )
          {
            if ( v5 == *(_QWORD *)(W32GetUserSessionState(v23) + 18984) )
            {
              v25 = *(__int64 **)(v5 + 496);
              v24 = *v25;
              if ( ((*(_DWORD *)(v5 + 712) | *(_DWORD *)(*v25 + 16)) & 0x1000) != 0 )
                xxxCallHook(0, 0, 0, 11);
            }
            CurrentProcessWin32Process = (_QWORD *)PsGetCurrentProcessWin32Process(v24);
            v27 = CurrentProcessWin32Process;
            if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process )
              v27 = 0;
            v28 = *(_QWORD *)(v5 + 456);
            if ( !*(_QWORD *)(v28 + 336) )
              *(_QWORD *)(v28 + 336) = v5;
            if ( *(_QWORD *)(*(_QWORD *)(v5 + 456) + 336LL) == v5 )
            {
              EtwTraceWakeInputIdle(0, v5);
              v29 = (struct _KEVENT *)v27[2];
              if ( !v29 )
                goto LABEL_55;
              if ( v29 != (struct _KEVENT *)-1LL )
              {
                KeSetEvent(v29, 1, 0);
                ObfDereferenceObject((PVOID)v27[2]);
LABEL_55:
                v27[2] = -1;
              }
            }
            v30 = *((_DWORD *)v27 + 3);
            if ( (v30 & 4) != 0 )
            {
              *((_DWORD *)v27 + 3) = v30 & 0xFFFFFFFB;
              zzzCalcStartCursorHide(0, 0);
            }
          }
        }
        Object[0] = *(PVOID *)(v5 + 1608);
        if ( (unsigned __int8)IsInputThread() && (v9 & 0x200) != 0 )
        {
          v32 = 1;
          Object[1] = *(PVOID *)(W32GetUserSessionState(v31) + 18864);
          v33 = 2;
        }
        else
        {
          v33 = 1;
          v32 = 0;
        }
        v34 = *(void **)(v5 + 1576);
        if ( v34 && (v9 & 0xFFFF7DFF) != 0 )
          Object[v33++] = v34;
        if ( v32 )
          *(_DWORD *)(W32GetUserSessionState(v34) + 63960) = 1;
        v57 = 0;
        while ( 1 )
        {
          v35 = (unsigned __int64)MEMORY[0xFFFFF78000000004] << 32;
          v36 = (v35 * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
          UserSessionSwitchLeaveCrit(v35, v36);
          v6 = KeWaitForMultipleObjects(v33, Object, WaitAny, WrUserRequest, 1, 0, Timeout, 0);
          EnterCrit(1, 0);
          v38 = 0;
          if ( !v6 )
          {
            if ( (unsigned int)xxxRemoveQueueCompletion() )
            {
              v37 = v9 & *(_DWORD *)(*(_QWORD *)v12 + 8LL);
              if ( ((unsigned __int8)v9 & *(_BYTE *)(*(_QWORD *)v12 + 8LL) & 8) == 0 )
                v38 = 1;
            }
          }
          if ( v6 == 1 )
          {
            if ( v32 )
            {
              if ( (unsigned __int64)(((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                                      * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
                                    - v36) >= 0x10 )
                v39 = ((((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                      * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64)
                    - v36;
              else
                v39 = 16;
              v37 = -10000LL * v39;
              if ( v37 <= Timeout->QuadPart )
              {
                v45 = 1;
                v6 = 258;
LABEL_90:
                if ( v32 )
                {
                  *(_DWORD *)(W32GetUserSessionState(v37) + 63960) = 0;
                  if ( *(_DWORD *)(W32GetUserSessionState(v46) + 63964) )
                  {
                    WakeMIT(2);
                    if ( !v45 )
                    {
                      UserSessionState = W32GetUserSessionState(v47);
                      KeClearEvent(*(PRKEVENT *)(UserSessionState + 18864));
                    }
                  }
                }
                SleepInputIdle(v5);
                v9 = v50;
                v10 = (__int64 *)Timeout;
                v8 = v59;
                v7 = v49;
                goto LABEL_11;
              }
              Timeout->QuadPart -= v37;
              *(_DWORD *)(W32GetUserSessionState(v37) + 63964) = 0;
              v41 = W32GetUserSessionState(v40);
              if ( (unsigned __int8)IsInputThread() )
              {
                v63 = 0;
                v64 = 0;
                v66 = 0;
                v67 = 0;
                v68 = 0;
                v70 = 0;
                memset(v75, 0, sizeof(v75));
                v62 = *(_DWORD *)(v41 + 19052);
                v65 = *(_QWORD *)(v41 + 19044);
                v69 = 0;
                v71 = 0;
                v72 = 0xFFFFFFFE00000000uLL;
                v73 = 0;
                DCompHitTest(v74, &v62, v75);
              }
              if ( !*(_DWORD *)(v41 + 19056) )
              {
                *(_OWORD *)(v41 + 19040) = 0;
                *(_OWORD *)(v41 + 19056) = 0;
                *(_OWORD *)(v41 + 19072) = 0;
                *(_OWORD *)(v41 + 19088) = 0;
                *(_OWORD *)(v41 + 19104) = 0;
                *(_OWORD *)(v41 + 19120) = 0;
                *(_OWORD *)(v41 + 19136) = 0;
              }
              if ( *(_BYTE *)(W32GetUserSessionState(v42) + 18892) )
              {
                v44 = W32GetUserSessionState(v43);
                KeSetEvent(*(PRKEVENT *)(v44 + 18904), 1, 0);
              }
            }
            else
            {
              *(_DWORD *)v59 = 2;
              v58 = -100000;
            }
          }
          else if ( !v38 )
          {
            v45 = v57;
            goto LABEL_90;
          }
          v9 = v50;
        }
      }
      v6 = xxxDesktopThreadWaiter(0, v9);
      v14 = 0xFFFFF78000000320uLL;
      v13 = 0xFFFFF78000000004uLL;
      if ( v6 == -1073741790 )
        goto LABEL_27;
    }
  }
  v19 = 1;
LABEL_28:
  _InterlockedExchange((volatile __int32 *)(*(_QWORD *)v12 + 16LL), v51);
  if ( v19 )
    _InterlockedExchange(
      (volatile __int32 *)(*(_QWORD *)v12 + 20LL),
      (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
  return v19;
}

```

## disassembly

```asm
0x1400e9390  mov     [rsp+arg_0], rbx
0x1400e9395  mov     [rsp+arg_10], rsi
0x1400e939a  push    rdi
0x1400e939b  push    r12
0x1400e939d  push    r13
0x1400e939f  push    r14
0x1400e93a1  push    r15
0x1400e93a3  sub     rsp, 1F0h
0x1400e93aa  mov     rax, cs:__security_cookie
0x1400e93b1  xor     rax, rsp
0x1400e93b4  mov     [rsp+218h+var_38], rax
0x1400e93bc  mov     [rsp+218h+var_1BC], r9d
0x1400e93c1  mov     [rsp+218h+var_1B8], r8d
0x1400e93c6  mov     rax, [rsp+218h+arg_20]
0x1400e93ce  xor     esi, esi
0x1400e93d0  mov     [rsp+218h+var_198], rsi
0x1400e93d8  mov     r14d, esi
0x1400e93db  mov     ebx, ecx
0x1400e93dd  and     ebx, 8000h
0x1400e93e3  mov     [rsp+218h+var_1D4], ebx
0x1400e93e7  mov     [rsp+218h+var_1D8], esi
0x1400e93eb  xorps   xmm0, xmm0
0x1400e93ee  movups  xmmword ptr [rsp+218h+Object], xmm0
0x1400e93f6  mov     [rsp+218h+var_1C0], esi
0x1400e93fa  lea     r13, [rsp+218h+var_1C0]
0x1400e93ff  test    rax, rax
0x1400e9402  cmovnz  r13, rax
0x1400e9406  mov     [rsp+218h+var_190], r13
0x1400e940e  mov     [r13+0], esi
0x1400e9412  mov     edi, ecx
0x1400e9414  btr     edi, 0Fh
0x1400e9418  test    ebx, ebx
0x1400e941a  cmovz   edi, ecx
0x1400e941d  mov     [rsp+218h+var_1D0], edi
0x1400e9421  test    edx, edx
0x1400e9423  jz      short loc_1400E9441
0x1400e9425  movsxd  rax, edx
0x1400e9428  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x1400e942f  mov     [rsp+218h+var_198], rcx
0x1400e9437  lea     r12, [rsp+218h+var_198]
0x1400e943f  jmp     short loc_1400E9444
0x1400e9441  mov     r12, rsi
0x1400e9444  mov     [rsp+218h+var_1C8], r12
0x1400e9449  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e9450  nop     dword ptr [rax+rax+00h]
0x1400e9455  test    rax, rax
0x1400e9458  jz      short loc_1400E945D
0x1400e945a  mov     rsi, [rax]
0x1400e945d  lea     r15, [rsi+1E0h]
0x1400e9464  mov     [rsp+218h+var_178], r15
0x1400e946c  mov     rax, [r15]
0x1400e946f  mov     ecx, [rax+10h]
0x1400e9472  mov     [rsp+218h+var_1CC], ecx
0x1400e9476  mov     [rsp+218h+var_1A4], ecx
0x1400e947a  mov     r8, 0FFFFF78000000004h
0x1400e9484  mov     rdx, 0FFFFF78000000320h
0x1400e948e  xchg    ax, ax
0x1400e9490  mov     rax, [r15]
0x1400e9493  mov     ecx, [rax+4]
0x1400e9496  test    ecx, edi
0x1400e9498  jnz     loc_1400E9BFC
0x1400e949e  cmp     [rsp+218h+var_1BC], 0
0x1400e94a3  jz      short loc_1400E94B3
0x1400e94a5  mov     rax, [r15]
0x1400e94a8  mov     ecx, [rax+8]
0x1400e94ab  test    ecx, edi
0x1400e94ad  jnz     loc_1400E9BFC
0x1400e94b3  cmp     dword ptr [r13+0], 2
0x1400e94b8  jz      loc_1400E9594
0x1400e94be  test    ebx, ebx
0x1400e94c0  jnz     short loc_1400E950A
0x1400e94c2  mov     rax, [r15]
0x1400e94c5  mov     ecx, [rax+8]
0x1400e94c8  test    cl, 40h
0x1400e94cb  jz      short loc_1400E950A
0x1400e94cd  mov     rax, [r15]
0x1400e94d0  mov     ecx, [rax+8]
0x1400e94d3  test    cl, 40h
0x1400e94d6  jz      short loc_1400E94EB
0x1400e94d8  mov     rcx, rsi; struct tagTHREADINFO *
0x1400e94db  call    ?xxxReceiveMessage@@YAXPEAUtagTHREADINFO@@@Z; xxxReceiveMessage(tagTHREADINFO *)
0x1400e94e0  mov     rax, [r15]
0x1400e94e3  mov     ecx, [rax+8]
0x1400e94e6  test    cl, 40h
0x1400e94e9  jnz     short loc_1400E94D8
0x1400e94eb  mov     rax, [r15]
0x1400e94ee  mov     ecx, [rax+8]
0x1400e94f1  movzx   edx, word ptr [rsi+390h]
0x1400e94f8  and     edx, ecx
0x1400e94fa  mov     rax, [r15]
0x1400e94fd  lock or [rax+4], edx
0x1400e9501  xor     eax, eax
0x1400e9503  mov     [rsi+390h], ax
0x1400e950a  mov     rcx, rsi
0x1400e950d  call    xxxDoSysExpungeIfNeeded
0x1400e9512  xor     ebx, ebx
0x1400e9514  cmp     [rsp+218h+var_1D4], ebx
0x1400e9518  mov     eax, 40h ; '@'
0x1400e951d  cmovz   ebx, eax
0x1400e9520  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400e9527  nop     dword ptr [rax+rax+00h]
0x1400e952c  test    rax, rax
0x1400e952f  jz      short loc_1400E9536
0x1400e9531  mov     rcx, [rax]
0x1400e9534  jmp     short loc_1400E9538
0x1400e9536  xor     ecx, ecx
0x1400e9538  movzx   edx, di
0x1400e953b  or      edx, ebx
0x1400e953d  mov     rax, [rcx+1E0h]
0x1400e9544  xchg    edx, [rax+10h]
0x1400e9547  mov     rcx, [rcx+2F8h]; Event
0x1400e954e  call    cs:__imp_KeClearEvent
0x1400e9555  nop     dword ptr [rax+rax+00h]
0x1400e955a  cmp     r14d, 102h
0x1400e9561  jnz     loc_1400E95ED
0x1400e9567  mov     ecx, 5B4h
0x1400e956c  call    UserSetLastError
0x1400e9571  mov     dword ptr [r13+0], 1
0x1400e9579  nop     dword ptr [rax+00000000h]
0x1400e9580  mov     rdx, 0FFFFF78000000320h
0x1400e958a  mov     r8, 0FFFFF78000000004h
0x1400e9594  mov     r9d, [rsp+218h+var_1D8]
0x1400e9599  mov     rax, [r15]
0x1400e959c  mov     ecx, [rsp+218h+var_1CC]
0x1400e95a0  xchg    ecx, [rax+10h]
0x1400e95a3  test    r9d, r9d
0x1400e95a6  jz      short loc_1400E95BC
0x1400e95a8  mov     rcx, [rdx]
0x1400e95ab  mov     edx, [r8]
0x1400e95ae  imul    rdx, rcx
0x1400e95b2  shr     rdx, 18h
0x1400e95b6  mov     rcx, [r15]
0x1400e95b9  xchg    edx, [rcx+14h]
0x1400e95bc  mov     eax, r9d
0x1400e95bf  mov     rcx, [rsp+218h+var_38]
0x1400e95c7  xor     rcx, rsp; StackCookie
0x1400e95ca  call    __security_check_cookie
0x1400e95cf  lea     r11, [rsp+218h+var_28]
0x1400e95d7  mov     rbx, [r11+30h]
0x1400e95db  mov     rsi, [r11+40h]
0x1400e95df  mov     rsp, r11
0x1400e95e2  pop     r15
0x1400e95e4  pop     r14
0x1400e95e6  pop     r13
0x1400e95e8  pop     r12
0x1400e95ea  pop     rdi
0x1400e95eb  retn
0x1400e95ed  cmp     r14d, 0C0h
0x1400e95f4  jnz     short loc_1400E95FD
0x1400e95f6  call    ClientDeliverUserApc
0x1400e95fb  jmp     short loc_1400E9580
0x1400e95fd  mov     rax, [r15]
0x1400e9600  mov     edx, [rax+4]
0x1400e9603  mov     rax, [r15]
0x1400e9606  mov     ecx, [rax+10h]
0x1400e9609  test    ecx, edx
0x1400e960b  mov     rdx, 0FFFFF78000000320h
0x1400e9615  mov     r8, 0FFFFF78000000004h
0x1400e961f  mov     ebx, [rsp+218h+var_1D4]
0x1400e9623  jnz     loc_1400E9490
0x1400e9629  call    cs:__imp_W32GetUserSessionState
0x1400e9630  nop     dword ptr [rax+rax+00h]
0x1400e9635  cmp     rsi, [rax+10B70h]
0x1400e963c  jnz     short loc_1400E9679
0x1400e963e  bt      edi, 9
0x1400e9642  jnb     short loc_1400E9679
0x1400e9644  test    r12, r12
0x1400e9647  jnz     short loc_1400E9679
0x1400e9649  mov     edx, edi
0x1400e964b  xor     ecx, ecx
0x1400e964d  call    xxxDesktopThreadWaiter
0x1400e9652  mov     r14d, eax
0x1400e9655  mov     rdx, 0FFFFF78000000320h
0x1400e965f  mov     r8, 0FFFFF78000000004h
0x1400e9669  cmp     eax, 0C0000022h
0x1400e966e  jz      loc_1400E9594
0x1400e9674  jmp     loc_1400E9490
0x1400e9679  mov     ebx, [rsp+218h+var_1B8]
0x1400e967d  test    ebx, ebx
0x1400e967f  jz      loc_1400E97DD
0x1400e9685  xor     ecx, ecx
0x1400e9687  xor     eax, eax
0x1400e9689  lock cmpxchg [rsi+208h], ecx
0x1400e9691  bt      eax, 0Ah
0x1400e9695  jnb     short loc_1400E96A7
0x1400e9697  mov     rcx, rsi; struct tagTHREADINFO *
0x1400e969a  call    ?CheckProcessForeground@@YAJPEAUtagTHREADINFO@@@Z; CheckProcessForeground(tagTHREADINFO *)
0x1400e969f  test    eax, eax
0x1400e96a1  js      loc_1400E9580
0x1400e96a7  mov     rax, [rsi+200h]
0x1400e96ae  mov     qword ptr [rax+8], 0
0x1400e96b6  jmp     short loc_1400E96E6
0x1400e96b8  mov     rdx, 0FFFFF78000000320h
0x1400e96c2  mov     r8, 0FFFFF78000000004h
0x1400e96cc  mov     eax, [rsp+218h+var_1A4]
0x1400e96d0  mov     [rsp+218h+var_1CC], eax
0x1400e96d4  mov     r15, [rsp+218h+var_178]
0x1400e96dc  mov     r9d, [rsp+218h+var_1D8]
0x1400e96e1  jmp     loc_1400E9599
0x1400e96e6  test    ebx, ebx
0x1400e96e8  jz      loc_1400E97DD
0x1400e96ee  call    cs:__imp_W32GetUserSessionState
0x1400e96f5  nop     dword ptr [rax+rax+00h]
0x1400e96fa  cmp     rsi, [rax+4A28h]
0x1400e9701  jnz     short loc_1400E972E
0x1400e9703  mov     rax, [rsi+1F0h]
0x1400e970a  mov     rcx, [rax]
0x1400e970d  mov     edx, [rcx+10h]
0x1400e9710  or      edx, [rsi+2C8h]
0x1400e9716  bt      edx, 0Ch
0x1400e971a  jnb     short loc_1400E972E
0x1400e971c  mov     r9d, 0Bh; int
0x1400e9722  xor     r8d, r8d; __int64
0x1400e9725  xor     edx, edx; unsigned __int64
0x1400e9727  xor     ecx, ecx; int
0x1400e9729  call    ?xxxCallHook@@YAHH_K_JH@Z; xxxCallHook(int,unsigned __int64,__int64,int)
0x1400e972e  test    ebx, ebx
0x1400e9730  jz      loc_1400E97DD
0x1400e9736  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400e973d  nop     dword ptr [rax+rax+00h]
0x1400e9742  mov     rbx, rax
0x1400e9745  test    rax, rax
0x1400e9748  jz      short loc_1400E9753
0x1400e974a  xor     ecx, ecx
0x1400e974c  cmp     [rax], rcx
0x1400e974f  cmovz   rbx, rcx
0x1400e9753  mov     rax, [rsi+1C8h]
0x1400e975a  cmp     qword ptr [rax+150h], 0
0x1400e9762  jnz     short loc_1400E976B
0x1400e9764  mov     [rax+150h], rsi
0x1400e976b  mov     rax, [rsi+1C8h]
0x1400e9772  cmp     [rax+150h], rsi
0x1400e9779  jnz     short loc_1400E97C7
0x1400e977b  mov     rdx, rsi
0x1400e977e  xor     ecx, ecx
0x1400e9780  call    cs:__imp_EtwTraceWakeInputIdle
0x1400e9787  nop     dword ptr [rax+rax+00h]
0x1400e978c  mov     rcx, [rbx+10h]; Event
0x1400e9790  test    rcx, rcx
0x1400e9793  jz      short loc_1400E97BF
0x1400e9795  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400e9799  jz      short loc_1400E97C7
0x1400e979b  xor     r8d, r8d; Wait
0x1400e979e  mov     edx, 1; Increment
0x1400e97a3  call    cs:__imp_KeSetEvent
0x1400e97aa  nop     dword ptr [rax+rax+00h]
0x1400e97af  mov     rcx, [rbx+10h]; Object
0x1400e97b3  call    cs:__imp_ObfDereferenceObject
0x1400e97ba  nop     dword ptr [rax+rax+00h]
0x1400e97bf  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1400e97c7  mov     eax, [rbx+0Ch]
0x1400e97ca  test    al, 4
0x1400e97cc  jz      short loc_1400E97DD
0x1400e97ce  and     eax, 0FFFFFFFBh
0x1400e97d1  mov     [rbx+0Ch], eax
0x1400e97d4  xor     edx, edx
0x1400e97d6  xor     ecx, ecx
0x1400e97d8  call    zzzCalcStartCursorHide
0x1400e97dd  mov     rax, [rsi+648h]
0x1400e97e4  mov     [rsp+218h+Object], rax
0x1400e97ec  call    cs:__imp_IsInputThread
0x1400e97f3  nop     dword ptr [rax+rax+00h]
0x1400e97f8  test    al, al
0x1400e97fa  jz      short loc_1400E9828
0x1400e97fc  bt      edi, 9
0x1400e9800  jnb     short loc_1400E9828
0x1400e9802  mov     r12b, 1
0x1400e9805  call    cs:__imp_W32GetUserSessionState
0x1400e980c  nop     dword ptr [rax+rax+00h]
0x1400e9811  mov     rcx, [rax+49B0h]
0x1400e9818  mov     [rsp+218h+Object+8], rcx
0x1400e9820  mov     r13d, 2
0x1400e9826  jmp     short loc_1400E9831
0x1400e9828  mov     r13d, 1
0x1400e982e  xor     r12b, r12b
0x1400e9831  mov     rcx, [rsi+628h]
0x1400e9838  test    rcx, rcx
0x1400e983b  jz      short loc_1400E9853
0x1400e983d  test    edi, 0FFFF7DFFh
0x1400e9843  jz      short loc_1400E9853
0x1400e9845  mov     eax, r13d
0x1400e9848  mov     [rsp+rax*8+218h+Object], rcx
0x1400e9850  inc     r13d
0x1400e9853  test    r12b, r12b
0x1400e9856  jz      short loc_1400E986E
0x1400e9858  call    cs:__imp_W32GetUserSessionState
0x1400e985f  nop     dword ptr [rax+rax+00h]
0x1400e9864  mov     dword ptr [rax+0F9D8h], 1
0x1400e986e  mov     [rsp+218h+var_1A0], 0
0x1400e9876  jmp     short loc_1400E9884
0x1400e9880  mov     edi, [rsp+218h+var_1D0]
0x1400e9884  mov     rax, 0FFFFF78000000004h
0x1400e988e  mov     ecx, [rax]
0x1400e9890  mov     rax, 0FFFFF78000000320h
0x1400e989a  mov     rax, [rax]
0x1400e989d  shl     rax, 8
0x1400e98a1  shl     rcx, 20h
0x1400e98a5  mul     rcx
0x1400e98a8  mov     rbx, rdx
0x1400e98ab  call    cs:__imp_UserSessionSwitchLeaveCrit
  ... truncated ...
```
