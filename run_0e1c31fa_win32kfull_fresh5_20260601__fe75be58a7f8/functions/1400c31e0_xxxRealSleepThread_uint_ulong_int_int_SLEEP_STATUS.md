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
