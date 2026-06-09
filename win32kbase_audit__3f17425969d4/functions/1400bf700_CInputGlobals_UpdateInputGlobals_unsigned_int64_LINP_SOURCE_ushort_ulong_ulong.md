# CInputGlobals::UpdateInputGlobals(unsigned __int64,_LINP_SOURCE,ushort,ulong,ulong)

- ea: `0x1400bf700`
- end: `0x1400bfcf9`
- name: `?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z`
- size: `1529`
- prototype: `char __fastcall(__int64, __int64, int, unsigned __int16, unsigned int, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006b708`
- `0x1400bc840`
- `0x1400bebf4`
- `0x1400ccf10`
- `0x1400ece90`

## callees

- `0x14000b9f0`
- `0x1400371c0`
- `0x1400bf700`
- `0x1400bfd00`
- `0x1400bfe7c`
- `0x1400c081c`
- `0x14010f9f0`
- `0x14018ba14`
- `0x1401aab9c`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bf79c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400bf79c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bf78b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bf78b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bf882`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bf882`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bf876`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400bf876`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400bfc51`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400bfc51`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400bfb24`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400bfb24`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400bf92a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400bf94f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400bf92a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400bf94f`
- `WIN32K!W32GetUserSessionState` at `0x1400bf7a8`
- `WIN32K!W32GetUserSessionState` at `0x1400bf7e6`
- `WIN32K!W32GetUserSessionState` at `0x1400bf819`
- `WIN32K!W32GetUserSessionState` at `0x1400bf88e`
- `WIN32K!W32GetUserSessionState` at `0x1400bf8b3`
- `WIN32K!W32GetUserSessionState` at `0x1400bfaab`
- `WIN32K!W32GetUserSessionState` at `0x1400bfac4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfae2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfb07`
- `WIN32K!W32GetUserSessionState` at `0x1400bf7a8`
- `WIN32K!W32GetUserSessionState` at `0x1400bf7e6`
- `WIN32K!W32GetUserSessionState` at `0x1400bf819`
- `WIN32K!W32GetUserSessionState` at `0x1400bf88e`
- `WIN32K!W32GetUserSessionState` at `0x1400bf8b3`
- `WIN32K!W32GetUserSessionState` at `0x1400bfaab`
- `WIN32K!W32GetUserSessionState` at `0x1400bfac4`
- `WIN32K!W32GetUserSessionState` at `0x1400bfae2`
- `WIN32K!W32GetUserSessionState` at `0x1400bfb07`

## pseudocode

```c
char __fastcall CInputGlobals::UpdateInputGlobals(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int16 a4,
        unsigned int a5,
        int a6)
{
  unsigned int v6; // ebp
  unsigned int v8; // r15d
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 UserSessionState; // rax
  LONGLONG TimeQuadPart; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int16 v27; // cx
  __int64 v28; // rcx
  int (*v29)(void); // rax
  __int64 v30; // rcx
  void (__fastcall *v31)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  int CurrentWin32kSessionId; // eax
  int v42; // edx
  int v43; // ecx
  int v44; // r8d
  __int64 v45; // rax
  LONGLONG v46; // [rsp+90h] [rbp+8h] BYREF

  v6 = a6;
  v8 = 0;
  if ( (a6 & 0x20) != 0 )
  {
    switch ( a3 )
    {
      case 1:
        v11 = 4;
        break;
      case 3:
        v11 = 2;
        break;
      case 11:
        v11 = 8;
        break;
      case 13:
        v11 = 16;
        break;
      case 17:
        v11 = 32;
        break;
      default:
        v11 = 0;
        break;
    }
    if ( (v11 & *(_DWORD *)(a1 + 148)) != 0 )
      v6 = a6 | 4;
    switch ( a3 )
    {
      case 1:
        v12 = 4;
        break;
      case 3:
        v12 = 2;
        break;
      case 11:
        v12 = 8;
        break;
      case 13:
        v12 = 16;
        break;
      case 17:
        v12 = 32;
        break;
      default:
        v12 = 0;
        break;
    }
    if ( (v12 & *(_DWORD *)(a1 + 144)) != 0 )
      v6 |= 2u;
  }
  InputTraceLogging::Power::UpdateInputGlobals((unsigned int)a3, a4, v6);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  v16 = *(volatile signed __int32 **)(W32GetUserSessionState(v14, v13) + 19704);
  if ( (*v16 & 0x2000) != 0 )
  {
    W32ReleasePushLockExclusiveEx((struct W32_PUSH_LOCK *)a1);
    return 1;
  }
  *(_DWORD *)(a1 + 136) = a3;
  *(_BYTE *)(a1 + 140) = (v6 & 8) != 0;
  if ( a3 != 1 )
  {
    v16 = *(volatile signed __int32 **)(W32GetUserSessionState(v16, v15) + 19704);
    _InterlockedAnd(v16, 0xFFFFFFBF);
  }
  if ( (v6 & 0x10) == 0 )
  {
    if ( (unsigned __int64)(a2 - *(_QWORD *)(a1 + 64)) > 0x1F4 )
    {
      LODWORD(v46) = W32GetCurrentWin32kSessionId((__int64)v16);
      if ( (int)ZwUpdateWnfStateData(&WNF_ISM_LAST_USER_ACTIVITY, 0, 0, 0, &v46, 0, 0) < 0 )
      {
        a6 = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 255);
      }
      *(_QWORD *)(a1 + 64) = a2;
      v45 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 128) = v45;
      *(_QWORD *)(a1 + 72) = v45 + 1;
    }
    if ( !*(_DWORD *)(W32GetUserSessionState(v16, v15) + 19152) || (v6 & 8) == 0 )
    {
      EtwTraceDisplayTimeoutReset(*(_QWORD *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = a2;
      if ( a3 <= 11 )
      {
        if ( a3 == 11 || a3 == 1 || a3 == 3 || a3 == 4 || a3 == 5 || a3 == 9 )
          goto LABEL_22;
      }
      else if ( a3 == 13 || a3 == 14 || (unsigned int)(a3 - 16) <= 1 )
      {
LABEL_22:
        v17 = *(_QWORD *)(a1 + 72);
        *(_QWORD *)(a1 + 80) = v17;
        *(_QWORD *)(a1 + 72) = v17 + 1;
        *(_QWORD *)(a1 + 16) = a2;
      }
    }
  }
  ExReleasePushLockExclusiveEx(a1);
  KeLeaveCriticalRegion();
  UserSessionState = W32GetUserSessionState(v19, v18);
  v46 = 0;
  TimeQuadPart = 0;
  v22 = *(_QWORD *)(UserSessionState + 19704);
  *(_DWORD *)(v22 + 4968) = a2;
  v24 = W32GetUserSessionState(v22, v23);
  v25 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  v26 = (unsigned int)(v25 - *(_DWORD *)(v24 + 69160));
  if ( (unsigned int)v26 >= 0xEA60 )
  {
    *(_DWORD *)(v24 + 69160) = v25;
    if ( *(_QWORD *)(W32GetUserSessionState(v26, v25) + 18984) )
    {
      v35 = *(_QWORD *)(W32GetUserSessionState(v34, v33) + 18984);
      v8 = *(_DWORD *)(*(_QWORD *)(v35 + 456) + 56LL);
      v37 = W32GetUserSessionState(v35, v36);
      v39 = 0;
      if ( **(_QWORD **)(*(_QWORD *)(v37 + 18984) + 456LL) )
      {
        v40 = W32GetUserSessionState(0, v38);
        TimeQuadPart = PsGetProcessCreateTimeQuadPart(**(PEPROCESS **)(*(_QWORD *)(v40 + 18984) + 456LL));
        v46 = TimeQuadPart;
        goto LABEL_68;
      }
    }
    else
    {
      v39 = 0;
    }
    v46 = 0;
LABEL_68:
    if ( (W32kEtwEnabledKeyword & 0x8000000000020000uLL) != 0
      && (unsigned __int8)(byte_140293DD8 - 1) > 2u
      && (qword_140293DC0 & 0x8000000000020000uLL) != 0
      && (qword_140293DC8 & 0x8000000000020000uLL) == qword_140293DC8
      && (Microsoft_Windows_Win32kEnableBits & 0x20) != 0 )
    {
      CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v39);
      McTemplateK0qqm_EtwWriteTransfer(v43, v42, v44, CurrentWin32kSessionId, v8, (__int64)&v46);
    }
    ApiSetTraceLoggingUserIsActive(v8, TimeQuadPart);
  }
  if ( (v6 & 0x10) == 0 )
  {
    switch ( a3 )
    {
      case 1:
        if ( (v6 & 0x40) != 0 )
        {
          v27 = 512;
        }
        else if ( (v6 & 8) != 0 )
        {
          v27 = 1024;
        }
        else
        {
          v27 = 1;
        }
        break;
      case 3:
        if ( (v6 & 8) != 0 )
          v27 = 2048;
        else
          v27 = 2;
        break;
      case 4:
        v27 = 16;
        break;
      case 5:
        v27 = 32;
        break;
      case 11:
        if ( (v6 & 8) != 0 )
          v27 = 4096;
        else
          v27 = 4;
        break;
      case 13:
        if ( (v6 & 8) != 0 )
        {
          v27 = 0x2000;
        }
        else if ( (v6 & 0x80u) == 0 )
        {
          v27 = 8;
        }
        else
        {
          v27 = 0x8000;
        }
        break;
      case 17:
        if ( (v6 & 8) != 0 )
          v27 = 0x4000;
        else
          v27 = 256;
        break;
      default:
        v27 = 0;
        break;
    }
    CitpLastInputUpdate(v27, a2);
    v29 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v28) + 48) + 3936LL);
    if ( v29 && v29() >= 0 )
    {
      v31 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v30) + 48)
                                                                  + 3944LL);
      if ( v31 )
        v31((unsigned int)a2, (unsigned int)a3, a5, v6);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400bf700  push    rbx
0x1400bf702  push    rbp
0x1400bf703  push    rsi
0x1400bf704  push    rdi
0x1400bf705  push    r12
0x1400bf707  push    r13
0x1400bf709  push    r14
0x1400bf70b  push    r15
0x1400bf70d  sub     rsp, 48h
0x1400bf711  mov     ebp, [rsp+88h+arg_28]
0x1400bf718  mov     r13, rdx
0x1400bf71b  mov     edx, 2
0x1400bf720  xor     r15d, r15d
0x1400bf723  mov     edi, r8d
0x1400bf726  mov     rbx, rcx
0x1400bf729  lea     r10d, [rdx+1Eh]
0x1400bf72d  lea     r14d, [rdx+6]
0x1400bf731  lea     r8d, [rdx+2]
0x1400bf735  lea     r11d, [rdx+0Eh]
0x1400bf739  test    r10b, bpl
0x1400bf73c  jz      short loc_1400BF77D
0x1400bf73e  mov     ecx, edi
0x1400bf740  sub     ecx, 1
0x1400bf743  jz      loc_1400BF9F4
0x1400bf749  sub     ecx, edx
0x1400bf74b  jnz     loc_1400BFA79
0x1400bf751  mov     ecx, edx
0x1400bf753  test    [rbx+94h], ecx
0x1400bf759  jz      short loc_1400BF75E
0x1400bf75b  or      ebp, r8d
0x1400bf75e  mov     ecx, edi
0x1400bf760  sub     ecx, 1
0x1400bf763  jz      loc_1400BF9EC
0x1400bf769  sub     ecx, edx
0x1400bf76b  jnz     loc_1400BFA57
0x1400bf771  mov     ecx, edx
0x1400bf773  test    [rbx+90h], ecx
0x1400bf779  jz      short loc_1400BF77D
0x1400bf77b  or      ebp, edx
0x1400bf77d  mov     r8d, ebp
0x1400bf780  movzx   edx, r9w
0x1400bf784  mov     ecx, edi
0x1400bf786  call    ?UpdateInputGlobals@Power@InputTraceLogging@@SAXW4_LINP_SOURCE@@GK@Z; InputTraceLogging::Power::UpdateInputGlobals(_LINP_SOURCE,ushort,ulong)
0x1400bf78b  call    cs:__imp_KeEnterCriticalRegion
0x1400bf792  nop     dword ptr [rax+rax+00h]
0x1400bf797  xor     edx, edx
0x1400bf799  mov     rcx, rbx
0x1400bf79c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400bf7a3  nop     dword ptr [rax+rax+00h]
0x1400bf7a8  call    cs:__imp_W32GetUserSessionState
0x1400bf7af  nop     dword ptr [rax+rax+00h]
0x1400bf7b4  mov     rcx, [rax+4CF8h]
0x1400bf7bb  test    dword ptr [rcx], 2000h
0x1400bf7c1  jnz     loc_1400BF9FC
0x1400bf7c7  mov     esi, ebp
0x1400bf7c9  mov     [rbx+88h], edi
0x1400bf7cf  and     esi, r14d
0x1400bf7d2  mov     r14d, 1
0x1400bf7d8  setnz   al
0x1400bf7db  mov     [rbx+8Ch], al
0x1400bf7e1  cmp     edi, r14d
0x1400bf7e4  jz      short loc_1400BF7FD
0x1400bf7e6  call    cs:__imp_W32GetUserSessionState
0x1400bf7ed  nop     dword ptr [rax+rax+00h]
0x1400bf7f2  mov     rcx, [rax+4CF8h]
0x1400bf7f9  lock and dword ptr [rcx], 0FFFFFFBFh
0x1400bf7fd  mov     r12d, ebp
0x1400bf800  and     r12d, 10h
0x1400bf804  jnz     short loc_1400BF871
0x1400bf806  mov     rax, r13
0x1400bf809  sub     rax, [rbx+40h]
0x1400bf80d  cmp     rax, 1F4h
0x1400bf813  ja      loc_1400BFC1F
0x1400bf819  call    cs:__imp_W32GetUserSessionState
0x1400bf820  nop     dword ptr [rax+rax+00h]
0x1400bf825  cmp     [rax+4AD0h], r15d
0x1400bf82c  jnz     loc_1400BF9CB
0x1400bf832  mov     rcx, [rbx+8]
0x1400bf836  call    EtwTraceDisplayTimeoutReset
0x1400bf83b  mov     [rbx+8], r13
0x1400bf83f  cmp     edi, 0Bh
0x1400bf842  jle     loc_1400BFCA2
0x1400bf848  mov     ecx, edi
0x1400bf84a  sub     ecx, 0Dh
0x1400bf84d  jz      short loc_1400BF85E
0x1400bf84f  sub     ecx, r14d
0x1400bf852  jz      short loc_1400BF85E
0x1400bf854  sub     ecx, 2
0x1400bf857  jz      short loc_1400BF85E
0x1400bf859  cmp     ecx, r14d
0x1400bf85c  jnz     short loc_1400BF871
0x1400bf85e  mov     rax, [rbx+48h]
0x1400bf862  mov     [rbx+50h], rax
0x1400bf866  inc     rax
0x1400bf869  mov     [rbx+48h], rax
0x1400bf86d  mov     [rbx+10h], r13
0x1400bf871  xor     edx, edx
0x1400bf873  mov     rcx, rbx
0x1400bf876  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400bf87d  nop     dword ptr [rax+rax+00h]
0x1400bf882  call    cs:__imp_KeLeaveCriticalRegion
0x1400bf889  nop     dword ptr [rax+rax+00h]
0x1400bf88e  call    cs:__imp_W32GetUserSessionState
0x1400bf895  nop     dword ptr [rax+rax+00h]
0x1400bf89a  mov     [rsp+88h+arg_0], r15
0x1400bf8a2  mov     rbx, r15
0x1400bf8a5  mov     rcx, [rax+4CF8h]
0x1400bf8ac  mov     [rcx+1368h], r13d
0x1400bf8b3  call    cs:__imp_W32GetUserSessionState
0x1400bf8ba  nop     dword ptr [rax+rax+00h]
0x1400bf8bf  mov     rcx, 0FFFFF78000000320h
0x1400bf8c9  mov     rdx, 0FFFFF78000000004h
0x1400bf8d3  mov     rcx, [rcx]
0x1400bf8d6  mov     edx, [rdx]
0x1400bf8d8  imul    rdx, rcx
0x1400bf8dc  shr     rdx, 18h
0x1400bf8e0  mov     ecx, edx
0x1400bf8e2  sub     ecx, [rax+10E28h]
0x1400bf8e8  cmp     ecx, 0EA60h
0x1400bf8ee  jnb     loc_1400BFAA5
0x1400bf8f4  test    r12d, r12d
0x1400bf8f7  jnz     loc_1400BF980
0x1400bf8fd  mov     ecx, edi
0x1400bf8ff  sub     ecx, r14d
0x1400bf902  jz      loc_1400BFA0E
0x1400bf908  lea     eax, [r12+2]
0x1400bf90d  sub     ecx, eax
0x1400bf90f  jnz     loc_1400BF995
0x1400bf915  test    esi, esi
0x1400bf917  jz      loc_1400BFBBC
0x1400bf91d  mov     ecx, 800h; unsigned __int16
0x1400bf922  mov     edx, r13d; unsigned int
0x1400bf925  call    ?CitpLastInputUpdate@@YAXGI@Z; CitpLastInputUpdate(ushort,uint)
0x1400bf92a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400bf931  nop     dword ptr [rax+rax+00h]
0x1400bf936  mov     rcx, [rax+30h]
0x1400bf93a  mov     rax, [rcx+0F60h]
0x1400bf941  test    rax, rax
0x1400bf944  jz      short loc_1400BF980
0x1400bf946  call    _guard_dispatch_icall
0x1400bf94b  test    eax, eax
0x1400bf94d  js      short loc_1400BF980
0x1400bf94f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400bf956  nop     dword ptr [rax+rax+00h]
0x1400bf95b  mov     rcx, [rax+30h]
0x1400bf95f  mov     rax, [rcx+0F68h]
0x1400bf966  test    rax, rax
0x1400bf969  jz      short loc_1400BF980
0x1400bf96b  mov     r8d, [rsp+88h+arg_20]
0x1400bf973  mov     r9d, ebp
0x1400bf976  mov     edx, edi
0x1400bf978  mov     ecx, r13d
0x1400bf97b  call    _guard_dispatch_icall
0x1400bf980  mov     al, r14b
0x1400bf983  add     rsp, 48h
0x1400bf987  pop     r15
0x1400bf989  pop     r14
0x1400bf98b  pop     r13
0x1400bf98d  pop     r12
0x1400bf98f  pop     rdi
0x1400bf990  pop     rsi
0x1400bf991  pop     rbp
0x1400bf992  pop     rbx
0x1400bf993  retn
0x1400bf995  sub     ecx, r14d
0x1400bf998  jz      short loc_1400BF9D8
0x1400bf99a  sub     ecx, r14d
0x1400bf99d  jz      short loc_1400BF9E2
0x1400bf99f  sub     ecx, 6
0x1400bf9a2  jz      loc_1400BFA2A
0x1400bf9a8  sub     ecx, eax
0x1400bf9aa  jz      loc_1400BFA3C
0x1400bf9b0  cmp     ecx, 4
0x1400bf9b3  jnz     loc_1400BFC17
0x1400bf9b9  test    esi, esi
0x1400bf9bb  jz      loc_1400BFBC4
0x1400bf9c1  mov     ecx, 4000h
0x1400bf9c6  jmp     loc_1400BF922
0x1400bf9cb  test    esi, esi
0x1400bf9cd  jnz     loc_1400BF871
0x1400bf9d3  jmp     loc_1400BF832
0x1400bf9d8  mov     ecx, 10h
0x1400bf9dd  jmp     loc_1400BF922
0x1400bf9e2  mov     ecx, 20h ; ' '
0x1400bf9e7  jmp     loc_1400BF922
0x1400bf9ec  mov     ecx, r8d
0x1400bf9ef  jmp     loc_1400BF773
0x1400bf9f4  mov     ecx, r8d
0x1400bf9f7  jmp     loc_1400BF753
0x1400bf9fc  mov     rcx, rbx; struct W32_PUSH_LOCK *
0x1400bf9ff  call    ?W32ReleasePushLockExclusiveEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockExclusiveEx(W32_PUSH_LOCK *,ulong)
0x1400bfa04  mov     eax, 1
0x1400bfa09  jmp     loc_1400BF983
0x1400bfa0e  test    bpl, 40h
0x1400bfa12  jnz     loc_1400BFA9B
0x1400bfa18  test    esi, esi
0x1400bfa1a  jz      loc_1400BFCF0
0x1400bfa20  mov     ecx, 400h
0x1400bfa25  jmp     loc_1400BF922
0x1400bfa2a  test    esi, esi
0x1400bfa2c  jz      loc_1400BFCE6
0x1400bfa32  mov     ecx, 1000h
0x1400bfa37  jmp     loc_1400BF922
0x1400bfa3c  test    esi, esi
0x1400bfa3e  jnz     loc_1400BFBCE
0x1400bfa44  test    bpl, bpl
0x1400bfa47  jns     loc_1400BFCDC
0x1400bfa4d  mov     ecx, 8000h
0x1400bfa52  jmp     loc_1400BF922
0x1400bfa57  sub     ecx, r14d
0x1400bfa5a  jz      loc_1400BFBE8
0x1400bfa60  sub     ecx, edx
0x1400bfa62  jz      loc_1400BFBE0
0x1400bfa68  cmp     ecx, r8d
0x1400bfa6b  jnz     loc_1400BFBD8
0x1400bfa71  mov     ecx, r10d
0x1400bfa74  jmp     loc_1400BF773
0x1400bfa79  sub     ecx, r14d
0x1400bfa7c  jz      loc_1400BFC00
0x1400bfa82  sub     ecx, edx
0x1400bfa84  jz      loc_1400BFBF8
0x1400bfa8a  cmp     ecx, r8d
0x1400bfa8d  jnz     loc_1400BFBF0
0x1400bfa93  mov     ecx, r10d
0x1400bfa96  jmp     loc_1400BF753
0x1400bfa9b  mov     ecx, 200h
0x1400bfaa0  jmp     loc_1400BF922
0x1400bfaa5  mov     [rax+10E28h], edx
0x1400bfaab  call    cs:__imp_W32GetUserSessionState
0x1400bfab2  nop     dword ptr [rax+rax+00h]
0x1400bfab7  cmp     [rax+4A28h], r15
0x1400bfabe  jz      loc_1400BFC08
0x1400bfac4  call    cs:__imp_W32GetUserSessionState
0x1400bfacb  nop     dword ptr [rax+rax+00h]
0x1400bfad0  mov     rcx, [rax+4A28h]
0x1400bfad7  mov     rax, [rcx+1C8h]
0x1400bfade  mov     r15d, [rax+38h]
0x1400bfae2  call    cs:__imp_W32GetUserSessionState
0x1400bfae9  nop     dword ptr [rax+rax+00h]
0x1400bfaee  mov     rcx, [rax+4A28h]
0x1400bfaf5  mov     rax, [rcx+1C8h]
0x1400bfafc  xor     ecx, ecx
0x1400bfafe  cmp     [rax], rcx
0x1400bfb01  jz      loc_1400BFC0A
0x1400bfb07  call    cs:__imp_W32GetUserSessionState
0x1400bfb0e  nop     dword ptr [rax+rax+00h]
0x1400bfb13  mov     rcx, [rax+4A28h]
0x1400bfb1a  mov     rcx, [rcx+1C8h]
0x1400bfb21  mov     rcx, [rcx]; Process
0x1400bfb24  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400bfb2b  nop     dword ptr [rax+rax+00h]
0x1400bfb30  mov     rbx, rax
0x1400bfb33  mov     dword ptr [rsp+88h+arg_0], eax
0x1400bfb3a  shr     rax, 20h
0x1400bfb3e  mov     dword ptr [rsp+88h+arg_0+4], eax
0x1400bfb45  mov     rdx, 8000000000020000h
0x1400bfb4f  test    cs:W32kEtwEnabledKeyword, rdx
0x1400bfb56  jz      short loc_1400BFBA9
0x1400bfb58  mov     al, cs:byte_140293DD8
0x1400bfb5e  sub     al, r14b
0x1400bfb61  cmp     al, 2
0x1400bfb63  jbe     short loc_1400BFBA9
0x1400bfb65  test    cs:qword_140293DC0, rdx
0x1400bfb6c  jz      short loc_1400BFBA9
0x1400bfb6e  mov     rax, cs:qword_140293DC8
0x1400bfb75  and     rax, rdx
0x1400bfb78  cmp     rax, cs:qword_140293DC8
0x1400bfb7f  jnz     short loc_1400BFBA9
0x1400bfb81  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 20h
0x1400bfb88  jz      short loc_1400BFBA9
0x1400bfb8a  call    W32GetCurrentWin32kSessionId
0x1400bfb8f  mov     r9d, eax
0x1400bfb92  lea     rax, [rsp+88h+arg_0]
0x1400bfb9a  mov     [rsp+88h+var_60], rax
0x1400bfb9f  mov     dword ptr [rsp+88h+var_68], r15d
0x1400bfba4  call    McTemplateK0qqm_EtwWriteTransfer
0x1400bfba9  mov     rdx, rbx
0x1400bfbac  mov     ecx, r15d
0x1400bfbaf  call    ApiSetTraceLoggingUserIsActive
0x1400bfbb4  xor     r15d, r15d
0x1400bfbb7  jmp     loc_1400BF8F4
0x1400bfbbc  movzx   ecx, ax
0x1400bfbbf  jmp     loc_1400BF922
0x1400bfbc4  mov     ecx, 100h
0x1400bfbc9  jmp     loc_1400BF922
0x1400bfbce  mov     ecx, 2000h
0x1400bfbd3  jmp     loc_1400BF922
0x1400bfbd8  mov     ecx, r15d
0x1400bfbdb  jmp     loc_1400BF773
0x1400bfbe0  mov     ecx, r11d
0x1400bfbe3  jmp     loc_1400BF773
0x1400bfbe8  mov     ecx, r14d
0x1400bfbeb  jmp     loc_1400BF773
0x1400bfbf0  mov     ecx, r15d
0x1400bfbf3  jmp     loc_1400BF753
0x1400bfbf8  mov     ecx, r11d
0x1400bfbfb  jmp     loc_1400BF753
0x1400bfc00  mov     ecx, r14d
0x1400bfc03  jmp     loc_1400BF753
0x1400bfc08  xor     ecx, ecx
  ... truncated ...
```
