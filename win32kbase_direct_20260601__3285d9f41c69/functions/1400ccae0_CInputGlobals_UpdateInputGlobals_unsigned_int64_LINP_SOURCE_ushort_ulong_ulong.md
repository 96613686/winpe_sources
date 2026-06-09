# CInputGlobals::UpdateInputGlobals(unsigned __int64,_LINP_SOURCE,ushort,ulong,ulong)

- ea: `0x1400ccae0`
- end: `0x1400cd0d9`
- name: `?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z`
- size: `1529`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400985c8`
- `0x1400a1c90`
- `0x1400c9a10`
- `0x1400cbdf4`
- `0x140126590`

## callees

- `0x14000bed0`
- `0x140031bf4`
- `0x1400ccae0`
- `0x1400cd0e0`
- `0x1400cd25c`
- `0x1400cdbfc`
- `0x14010e390`
- `0x14018a0d4`
- `0x1401a9f9c`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ccb7c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400ccb7c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ccb6b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ccb6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ccc62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ccc62`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ccc56`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400ccc56`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400cd031`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400cd031`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400ccf04`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400ccf04`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400ccd0a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400ccd2f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400ccd0a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400ccd2f`
- `WIN32K!W32GetUserSessionState` at `0x1400ccb88`
- `WIN32K!W32GetUserSessionState` at `0x1400ccbc6`
- `WIN32K!W32GetUserSessionState` at `0x1400ccbf9`
- `WIN32K!W32GetUserSessionState` at `0x1400ccc6e`
- `WIN32K!W32GetUserSessionState` at `0x1400ccc93`
- `WIN32K!W32GetUserSessionState` at `0x1400cce8b`
- `WIN32K!W32GetUserSessionState` at `0x1400ccea4`
- `WIN32K!W32GetUserSessionState` at `0x1400ccec2`
- `WIN32K!W32GetUserSessionState` at `0x1400ccee7`
- `WIN32K!W32GetUserSessionState` at `0x1400ccb88`
- `WIN32K!W32GetUserSessionState` at `0x1400ccbc6`
- `WIN32K!W32GetUserSessionState` at `0x1400ccbf9`
- `WIN32K!W32GetUserSessionState` at `0x1400ccc6e`
- `WIN32K!W32GetUserSessionState` at `0x1400ccc93`
- `WIN32K!W32GetUserSessionState` at `0x1400cce8b`
- `WIN32K!W32GetUserSessionState` at `0x1400ccea4`
- `WIN32K!W32GetUserSessionState` at `0x1400ccec2`
- `WIN32K!W32GetUserSessionState` at `0x1400ccee7`

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
  __int64 v15; // r8
  __int64 v16; // rdx
  volatile signed __int32 *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 UserSessionState; // rax
  LONGLONG TimeQuadPart; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // r8
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  int (__fastcall *v39)(__int64, __int64, __int64); // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  void (__fastcall *v42)(_QWORD, _QWORD, _QWORD, _QWORD, LONGLONG *, int, int); // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  int CurrentWin32kSessionId; // eax
  int v55; // edx
  int v56; // ecx
  int v57; // r8d
  __int64 v58; // rax
  LONGLONG *v59; // [rsp+20h] [rbp-68h]
  int v60; // [rsp+28h] [rbp-60h]
  int v61; // [rsp+30h] [rbp-58h]
  LONGLONG v62; // [rsp+90h] [rbp+8h] BYREF

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
  v17 = *(volatile signed __int32 **)(W32GetUserSessionState(v14, v13, v15) + 19704);
  if ( (*v17 & 0x2000) != 0 )
  {
    W32ReleasePushLockExclusiveEx((struct W32_PUSH_LOCK *)a1, v16);
    return 1;
  }
  *(_DWORD *)(a1 + 136) = a3;
  *(_BYTE *)(a1 + 140) = (v6 & 8) != 0;
  if ( a3 != 1 )
  {
    v17 = *(volatile signed __int32 **)(W32GetUserSessionState(v17, v16, v18) + 19704);
    _InterlockedAnd(v17, 0xFFFFFFBF);
  }
  if ( (v6 & 0x10) == 0 )
  {
    if ( (unsigned __int64)(a2 - *(_QWORD *)(a1 + 64)) > 0x1F4 )
    {
      LODWORD(v62) = ((__int64 (*)(void))W32GetCurrentWin32kSessionId)();
      v61 = 0;
      v60 = 0;
      v59 = &v62;
      if ( (int)ZwUpdateWnfStateData(&WNF_ISM_LAST_USER_ACTIVITY, 0, 0) < 0 )
      {
        a6 = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 255);
      }
      *(_QWORD *)(a1 + 64) = a2;
      v58 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 128) = v58;
      *(_QWORD *)(a1 + 72) = v58 + 1;
    }
    if ( !*(_DWORD *)(W32GetUserSessionState(v17, v16, v18) + 19152) || (v6 & 8) == 0 )
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
        v20 = *(_QWORD *)(a1 + 72);
        *(_QWORD *)(a1 + 80) = v20;
        *(_QWORD *)(a1 + 72) = v20 + 1;
        *(_QWORD *)(a1 + 16) = a2;
      }
    }
  }
  ExReleasePushLockExclusiveEx(a1, 0, v18, v19);
  KeLeaveCriticalRegion();
  UserSessionState = W32GetUserSessionState(v22, v21, v23);
  v62 = 0;
  TimeQuadPart = 0;
  v26 = *(_QWORD *)(UserSessionState + 19704);
  *(_DWORD *)(v26 + 4968) = a2;
  v29 = W32GetUserSessionState(v26, v27, v28);
  v31 = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
  v32 = (unsigned int)(v31 - *(_DWORD *)(v29 + 69160));
  if ( (unsigned int)v32 >= 0xEA60 )
  {
    *(_DWORD *)(v29 + 69160) = v31;
    if ( *(_QWORD *)(W32GetUserSessionState(v32, v31, v30) + 18984) )
    {
      v47 = *(_QWORD *)(W32GetUserSessionState(v45, v44, v46) + 18984);
      v8 = *(_DWORD *)(*(_QWORD *)(v47 + 456) + 56LL);
      v50 = W32GetUserSessionState(v47, v48, v49);
      v52 = 0;
      if ( **(_QWORD **)(*(_QWORD *)(v50 + 18984) + 456LL) )
      {
        v53 = W32GetUserSessionState(0, v51, v46);
        TimeQuadPart = PsGetProcessCreateTimeQuadPart(**(PEPROCESS **)(*(_QWORD *)(v53 + 18984) + 456LL));
        v62 = TimeQuadPart;
        goto LABEL_68;
      }
    }
    else
    {
      v52 = 0;
    }
    v62 = 0;
LABEL_68:
    if ( (W32kEtwEnabledKeyword & 0x8000000000020000uLL) != 0
      && (unsigned __int8)(byte_140292DD8 - 1) > 2u
      && (qword_140292DC0 & 0x8000000000020000uLL) != 0
      && (qword_140292DC8 & 0x8000000000020000uLL) == qword_140292DC8
      && (Microsoft_Windows_Win32kEnableBits & 0x20) != 0 )
    {
      CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v52, 0x8000000000020000uLL, v46);
      McTemplateK0qqm_EtwWriteTransfer(v56, v55, v57, CurrentWin32kSessionId, v8, (__int64)&v62);
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
          v33 = 512;
        }
        else if ( (v6 & 8) != 0 )
        {
          v33 = 1024;
        }
        else
        {
          v33 = 1;
        }
        break;
      case 3:
        if ( (v6 & 8) != 0 )
          v33 = 2048;
        else
          v33 = 2;
        break;
      case 4:
        v33 = 16;
        break;
      case 5:
        v33 = 32;
        break;
      case 11:
        if ( (v6 & 8) != 0 )
          v33 = 4096;
        else
          v33 = 4;
        break;
      case 13:
        if ( (v6 & 8) != 0 )
        {
          v33 = 0x2000;
        }
        else if ( (v6 & 0x80u) == 0 )
        {
          v33 = 8;
        }
        else
        {
          v33 = 0x8000;
        }
        break;
      case 17:
        if ( (v6 & 8) != 0 )
          v33 = 0x4000;
        else
          v33 = 256;
        break;
      default:
        v33 = 0;
        break;
    }
    CitpLastInputUpdate(v33, (unsigned int)a2, v30);
    v37 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v35, v34) + 48);
    v39 = *(int (__fastcall **)(__int64, __int64, __int64))(v37 + 3936);
    if ( v39 && v39(v37, v36, v38) >= 0 )
    {
      v42 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, LONGLONG *, int, int))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v41, v40) + 48)
                                                                                        + 3944LL);
      if ( v42 )
        v42((unsigned int)a2, (unsigned int)a3, a5, v6, v59, v60, v61);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400ccae0  push    rbx
0x1400ccae2  push    rbp
0x1400ccae3  push    rsi
0x1400ccae4  push    rdi
0x1400ccae5  push    r12
0x1400ccae7  push    r13
0x1400ccae9  push    r14
0x1400ccaeb  push    r15
0x1400ccaed  sub     rsp, 48h
0x1400ccaf1  mov     ebp, [rsp+88h+arg_28]
0x1400ccaf8  mov     r13, rdx
0x1400ccafb  mov     edx, 2
0x1400ccb00  xor     r15d, r15d
0x1400ccb03  mov     edi, r8d
0x1400ccb06  mov     rbx, rcx
0x1400ccb09  lea     r10d, [rdx+1Eh]
0x1400ccb0d  lea     r14d, [rdx+6]
0x1400ccb11  lea     r8d, [rdx+2]
0x1400ccb15  lea     r11d, [rdx+0Eh]
0x1400ccb19  test    r10b, bpl
0x1400ccb1c  jz      short loc_1400CCB5D
0x1400ccb1e  mov     ecx, edi
0x1400ccb20  sub     ecx, 1
0x1400ccb23  jz      loc_1400CCDD4
0x1400ccb29  sub     ecx, edx
0x1400ccb2b  jnz     loc_1400CCE59
0x1400ccb31  mov     ecx, edx
0x1400ccb33  test    [rbx+94h], ecx
0x1400ccb39  jz      short loc_1400CCB3E
0x1400ccb3b  or      ebp, r8d
0x1400ccb3e  mov     ecx, edi
0x1400ccb40  sub     ecx, 1
0x1400ccb43  jz      loc_1400CCDCC
0x1400ccb49  sub     ecx, edx
0x1400ccb4b  jnz     loc_1400CCE37
0x1400ccb51  mov     ecx, edx
0x1400ccb53  test    [rbx+90h], ecx
0x1400ccb59  jz      short loc_1400CCB5D
0x1400ccb5b  or      ebp, edx
0x1400ccb5d  mov     r8d, ebp
0x1400ccb60  movzx   edx, r9w
0x1400ccb64  mov     ecx, edi
0x1400ccb66  call    ?UpdateInputGlobals@Power@InputTraceLogging@@SAXW4_LINP_SOURCE@@GK@Z; InputTraceLogging::Power::UpdateInputGlobals(_LINP_SOURCE,ushort,ulong)
0x1400ccb6b  call    cs:__imp_KeEnterCriticalRegion
0x1400ccb72  nop     dword ptr [rax+rax+00h]
0x1400ccb77  xor     edx, edx
0x1400ccb79  mov     rcx, rbx
0x1400ccb7c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400ccb83  nop     dword ptr [rax+rax+00h]
0x1400ccb88  call    cs:__imp_W32GetUserSessionState
0x1400ccb8f  nop     dword ptr [rax+rax+00h]
0x1400ccb94  mov     rcx, [rax+4CF8h]
0x1400ccb9b  test    dword ptr [rcx], 2000h
0x1400ccba1  jnz     loc_1400CCDDC
0x1400ccba7  mov     esi, ebp
0x1400ccba9  mov     [rbx+88h], edi
0x1400ccbaf  and     esi, r14d
0x1400ccbb2  mov     r14d, 1
0x1400ccbb8  setnz   al
0x1400ccbbb  mov     [rbx+8Ch], al
0x1400ccbc1  cmp     edi, r14d
0x1400ccbc4  jz      short loc_1400CCBDD
0x1400ccbc6  call    cs:__imp_W32GetUserSessionState
0x1400ccbcd  nop     dword ptr [rax+rax+00h]
0x1400ccbd2  mov     rcx, [rax+4CF8h]
0x1400ccbd9  lock and dword ptr [rcx], 0FFFFFFBFh
0x1400ccbdd  mov     r12d, ebp
0x1400ccbe0  and     r12d, 10h
0x1400ccbe4  jnz     short loc_1400CCC51
0x1400ccbe6  mov     rax, r13
0x1400ccbe9  sub     rax, [rbx+40h]
0x1400ccbed  cmp     rax, 1F4h
0x1400ccbf3  ja      loc_1400CCFFF
0x1400ccbf9  call    cs:__imp_W32GetUserSessionState
0x1400ccc00  nop     dword ptr [rax+rax+00h]
0x1400ccc05  cmp     [rax+4AD0h], r15d
0x1400ccc0c  jnz     loc_1400CCDAB
0x1400ccc12  mov     rcx, [rbx+8]
0x1400ccc16  call    EtwTraceDisplayTimeoutReset
0x1400ccc1b  mov     [rbx+8], r13
0x1400ccc1f  cmp     edi, 0Bh
0x1400ccc22  jle     loc_1400CD082
0x1400ccc28  mov     ecx, edi
0x1400ccc2a  sub     ecx, 0Dh
0x1400ccc2d  jz      short loc_1400CCC3E
0x1400ccc2f  sub     ecx, r14d
0x1400ccc32  jz      short loc_1400CCC3E
0x1400ccc34  sub     ecx, 2
0x1400ccc37  jz      short loc_1400CCC3E
0x1400ccc39  cmp     ecx, r14d
0x1400ccc3c  jnz     short loc_1400CCC51
0x1400ccc3e  mov     rax, [rbx+48h]
0x1400ccc42  mov     [rbx+50h], rax
0x1400ccc46  inc     rax
0x1400ccc49  mov     [rbx+48h], rax
0x1400ccc4d  mov     [rbx+10h], r13
0x1400ccc51  xor     edx, edx
0x1400ccc53  mov     rcx, rbx
0x1400ccc56  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400ccc5d  nop     dword ptr [rax+rax+00h]
0x1400ccc62  call    cs:__imp_KeLeaveCriticalRegion
0x1400ccc69  nop     dword ptr [rax+rax+00h]
0x1400ccc6e  call    cs:__imp_W32GetUserSessionState
0x1400ccc75  nop     dword ptr [rax+rax+00h]
0x1400ccc7a  mov     [rsp+88h+arg_0], r15
0x1400ccc82  mov     rbx, r15
0x1400ccc85  mov     rcx, [rax+4CF8h]
0x1400ccc8c  mov     [rcx+1368h], r13d
0x1400ccc93  call    cs:__imp_W32GetUserSessionState
0x1400ccc9a  nop     dword ptr [rax+rax+00h]
0x1400ccc9f  mov     rcx, 0FFFFF78000000320h
0x1400ccca9  mov     rdx, 0FFFFF78000000004h
0x1400cccb3  mov     rcx, [rcx]
0x1400cccb6  mov     edx, [rdx]
0x1400cccb8  imul    rdx, rcx
0x1400cccbc  shr     rdx, 18h
0x1400cccc0  mov     ecx, edx
0x1400cccc2  sub     ecx, [rax+10E28h]
0x1400cccc8  cmp     ecx, 0EA60h
0x1400cccce  jnb     loc_1400CCE85
0x1400cccd4  test    r12d, r12d
0x1400cccd7  jnz     loc_1400CCD60
0x1400cccdd  mov     ecx, edi
0x1400cccdf  sub     ecx, r14d
0x1400ccce2  jz      loc_1400CCDEE
0x1400ccce8  lea     eax, [r12+2]
0x1400ccced  sub     ecx, eax
0x1400cccef  jnz     loc_1400CCD75
0x1400cccf5  test    esi, esi
0x1400cccf7  jz      loc_1400CCF9C
0x1400cccfd  mov     ecx, 800h; unsigned __int16
0x1400ccd02  mov     edx, r13d; unsigned int
0x1400ccd05  call    ?CitpLastInputUpdate@@YAXGI@Z; CitpLastInputUpdate(ushort,uint)
0x1400ccd0a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400ccd11  nop     dword ptr [rax+rax+00h]
0x1400ccd16  mov     rcx, [rax+30h]
0x1400ccd1a  mov     rax, [rcx+0F60h]
0x1400ccd21  test    rax, rax
0x1400ccd24  jz      short loc_1400CCD60
0x1400ccd26  call    _guard_dispatch_icall
0x1400ccd2b  test    eax, eax
0x1400ccd2d  js      short loc_1400CCD60
0x1400ccd2f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400ccd36  nop     dword ptr [rax+rax+00h]
0x1400ccd3b  mov     rcx, [rax+30h]
0x1400ccd3f  mov     rax, [rcx+0F68h]
0x1400ccd46  test    rax, rax
0x1400ccd49  jz      short loc_1400CCD60
0x1400ccd4b  mov     r8d, [rsp+88h+arg_20]
0x1400ccd53  mov     r9d, ebp
0x1400ccd56  mov     edx, edi
0x1400ccd58  mov     ecx, r13d
0x1400ccd5b  call    _guard_dispatch_icall
0x1400ccd60  mov     al, r14b
0x1400ccd63  add     rsp, 48h
0x1400ccd67  pop     r15
0x1400ccd69  pop     r14
0x1400ccd6b  pop     r13
0x1400ccd6d  pop     r12
0x1400ccd6f  pop     rdi
0x1400ccd70  pop     rsi
0x1400ccd71  pop     rbp
0x1400ccd72  pop     rbx
0x1400ccd73  retn
0x1400ccd75  sub     ecx, r14d
0x1400ccd78  jz      short loc_1400CCDB8
0x1400ccd7a  sub     ecx, r14d
0x1400ccd7d  jz      short loc_1400CCDC2
0x1400ccd7f  sub     ecx, 6
0x1400ccd82  jz      loc_1400CCE0A
0x1400ccd88  sub     ecx, eax
0x1400ccd8a  jz      loc_1400CCE1C
0x1400ccd90  cmp     ecx, 4
0x1400ccd93  jnz     loc_1400CCFF7
0x1400ccd99  test    esi, esi
0x1400ccd9b  jz      loc_1400CCFA4
0x1400ccda1  mov     ecx, 4000h
0x1400ccda6  jmp     loc_1400CCD02
0x1400ccdab  test    esi, esi
0x1400ccdad  jnz     loc_1400CCC51
0x1400ccdb3  jmp     loc_1400CCC12
0x1400ccdb8  mov     ecx, 10h
0x1400ccdbd  jmp     loc_1400CCD02
0x1400ccdc2  mov     ecx, 20h ; ' '
0x1400ccdc7  jmp     loc_1400CCD02
0x1400ccdcc  mov     ecx, r8d
0x1400ccdcf  jmp     loc_1400CCB53
0x1400ccdd4  mov     ecx, r8d
0x1400ccdd7  jmp     loc_1400CCB33
0x1400ccddc  mov     rcx, rbx; struct W32_PUSH_LOCK *
0x1400ccddf  call    ?W32ReleasePushLockExclusiveEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockExclusiveEx(W32_PUSH_LOCK *,ulong)
0x1400ccde4  mov     eax, 1
0x1400ccde9  jmp     loc_1400CCD63
0x1400ccdee  test    bpl, 40h
0x1400ccdf2  jnz     loc_1400CCE7B
0x1400ccdf8  test    esi, esi
0x1400ccdfa  jz      loc_1400CD0D0
0x1400cce00  mov     ecx, 400h
0x1400cce05  jmp     loc_1400CCD02
0x1400cce0a  test    esi, esi
0x1400cce0c  jz      loc_1400CD0C6
0x1400cce12  mov     ecx, 1000h
0x1400cce17  jmp     loc_1400CCD02
0x1400cce1c  test    esi, esi
0x1400cce1e  jnz     loc_1400CCFAE
0x1400cce24  test    bpl, bpl
0x1400cce27  jns     loc_1400CD0BC
0x1400cce2d  mov     ecx, 8000h
0x1400cce32  jmp     loc_1400CCD02
0x1400cce37  sub     ecx, r14d
0x1400cce3a  jz      loc_1400CCFC8
0x1400cce40  sub     ecx, edx
0x1400cce42  jz      loc_1400CCFC0
0x1400cce48  cmp     ecx, r8d
0x1400cce4b  jnz     loc_1400CCFB8
0x1400cce51  mov     ecx, r10d
0x1400cce54  jmp     loc_1400CCB53
0x1400cce59  sub     ecx, r14d
0x1400cce5c  jz      loc_1400CCFE0
0x1400cce62  sub     ecx, edx
0x1400cce64  jz      loc_1400CCFD8
0x1400cce6a  cmp     ecx, r8d
0x1400cce6d  jnz     loc_1400CCFD0
0x1400cce73  mov     ecx, r10d
0x1400cce76  jmp     loc_1400CCB33
0x1400cce7b  mov     ecx, 200h
0x1400cce80  jmp     loc_1400CCD02
0x1400cce85  mov     [rax+10E28h], edx
0x1400cce8b  call    cs:__imp_W32GetUserSessionState
0x1400cce92  nop     dword ptr [rax+rax+00h]
0x1400cce97  cmp     [rax+4A28h], r15
0x1400cce9e  jz      loc_1400CCFE8
0x1400ccea4  call    cs:__imp_W32GetUserSessionState
0x1400cceab  nop     dword ptr [rax+rax+00h]
0x1400cceb0  mov     rcx, [rax+4A28h]
0x1400cceb7  mov     rax, [rcx+1C8h]
0x1400ccebe  mov     r15d, [rax+38h]
0x1400ccec2  call    cs:__imp_W32GetUserSessionState
0x1400ccec9  nop     dword ptr [rax+rax+00h]
0x1400ccece  mov     rcx, [rax+4A28h]
0x1400cced5  mov     rax, [rcx+1C8h]
0x1400ccedc  xor     ecx, ecx
0x1400ccede  cmp     [rax], rcx
0x1400ccee1  jz      loc_1400CCFEA
0x1400ccee7  call    cs:__imp_W32GetUserSessionState
0x1400cceee  nop     dword ptr [rax+rax+00h]
0x1400ccef3  mov     rcx, [rax+4A28h]
0x1400ccefa  mov     rcx, [rcx+1C8h]
0x1400ccf01  mov     rcx, [rcx]; Process
0x1400ccf04  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400ccf0b  nop     dword ptr [rax+rax+00h]
0x1400ccf10  mov     rbx, rax
0x1400ccf13  mov     dword ptr [rsp+88h+arg_0], eax
0x1400ccf1a  shr     rax, 20h
0x1400ccf1e  mov     dword ptr [rsp+88h+arg_0+4], eax
0x1400ccf25  mov     rdx, 8000000000020000h
0x1400ccf2f  test    cs:W32kEtwEnabledKeyword, rdx
0x1400ccf36  jz      short loc_1400CCF89
0x1400ccf38  mov     al, cs:byte_140292DD8
0x1400ccf3e  sub     al, r14b
0x1400ccf41  cmp     al, 2
0x1400ccf43  jbe     short loc_1400CCF89
0x1400ccf45  test    cs:qword_140292DC0, rdx
0x1400ccf4c  jz      short loc_1400CCF89
0x1400ccf4e  mov     rax, cs:qword_140292DC8
0x1400ccf55  and     rax, rdx
0x1400ccf58  cmp     rax, cs:qword_140292DC8
0x1400ccf5f  jnz     short loc_1400CCF89
0x1400ccf61  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 20h
0x1400ccf68  jz      short loc_1400CCF89
0x1400ccf6a  call    W32GetCurrentWin32kSessionId
0x1400ccf6f  mov     r9d, eax
0x1400ccf72  lea     rax, [rsp+88h+arg_0]
0x1400ccf7a  mov     [rsp+88h+var_60], rax
0x1400ccf7f  mov     dword ptr [rsp+88h+var_68], r15d
0x1400ccf84  call    McTemplateK0qqm_EtwWriteTransfer
0x1400ccf89  mov     rdx, rbx
0x1400ccf8c  mov     ecx, r15d
0x1400ccf8f  call    ApiSetTraceLoggingUserIsActive
0x1400ccf94  xor     r15d, r15d
0x1400ccf97  jmp     loc_1400CCCD4
0x1400ccf9c  movzx   ecx, ax
0x1400ccf9f  jmp     loc_1400CCD02
0x1400ccfa4  mov     ecx, 100h
0x1400ccfa9  jmp     loc_1400CCD02
0x1400ccfae  mov     ecx, 2000h
0x1400ccfb3  jmp     loc_1400CCD02
0x1400ccfb8  mov     ecx, r15d
0x1400ccfbb  jmp     loc_1400CCB53
0x1400ccfc0  mov     ecx, r11d
0x1400ccfc3  jmp     loc_1400CCB53
0x1400ccfc8  mov     ecx, r14d
0x1400ccfcb  jmp     loc_1400CCB53
0x1400ccfd0  mov     ecx, r15d
0x1400ccfd3  jmp     loc_1400CCB33
0x1400ccfd8  mov     ecx, r11d
0x1400ccfdb  jmp     loc_1400CCB33
0x1400ccfe0  mov     ecx, r14d
0x1400ccfe3  jmp     loc_1400CCB33
0x1400ccfe8  xor     ecx, ecx
  ... truncated ...
```
