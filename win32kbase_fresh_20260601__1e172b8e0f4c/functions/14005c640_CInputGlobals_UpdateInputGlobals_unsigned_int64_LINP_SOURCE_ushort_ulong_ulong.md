# CInputGlobals::UpdateInputGlobals(unsigned __int64,_LINP_SOURCE,ushort,ulong,ulong)

- ea: `0x14005c640`
- end: `0x14005cc39`
- name: `?UpdateInputGlobals@CInputGlobals@@QEAA_N_KW4_LINP_SOURCE@@GKK@Z`
- size: `1529`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140059500`
- `0x14005b8e4`
- `0x1400a17c8`
- `0x1400aae90`
- `0x140126530`

## callees

- `0x140028974`
- `0x14005c610`
- `0x14005c640`
- `0x14005cc40`
- `0x14005cdbc`
- `0x14005d75c`
- `0x14010d120`
- `0x140188f74`
- `0x1401aa4fc`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005c6dc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005c6dc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c6cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c6cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c7c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005c7c2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005c7b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005c7b6`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14005cb91`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14005cb91`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14005ca64`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14005ca64`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14005c86a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14005c88f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14005c86a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14005c88f`
- `WIN32K!W32GetUserSessionState` at `0x14005c6e8`
- `WIN32K!W32GetUserSessionState` at `0x14005c726`
- `WIN32K!W32GetUserSessionState` at `0x14005c759`
- `WIN32K!W32GetUserSessionState` at `0x14005c7ce`
- `WIN32K!W32GetUserSessionState` at `0x14005c7f3`
- `WIN32K!W32GetUserSessionState` at `0x14005c9eb`
- `WIN32K!W32GetUserSessionState` at `0x14005ca04`
- `WIN32K!W32GetUserSessionState` at `0x14005ca22`
- `WIN32K!W32GetUserSessionState` at `0x14005ca47`
- `WIN32K!W32GetUserSessionState` at `0x14005c6e8`
- `WIN32K!W32GetUserSessionState` at `0x14005c726`
- `WIN32K!W32GetUserSessionState` at `0x14005c759`
- `WIN32K!W32GetUserSessionState` at `0x14005c7ce`
- `WIN32K!W32GetUserSessionState` at `0x14005c7f3`
- `WIN32K!W32GetUserSessionState` at `0x14005c9eb`
- `WIN32K!W32GetUserSessionState` at `0x14005ca04`
- `WIN32K!W32GetUserSessionState` at `0x14005ca22`
- `WIN32K!W32GetUserSessionState` at `0x14005ca47`

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
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  int (__fastcall *v38)(__int64, __int64, __int64); // rax
  __int64 v39; // rcx
  void (__fastcall *v40)(_QWORD, _QWORD, _QWORD, _QWORD, LONGLONG *, int, int); // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  int CurrentWin32kSessionId; // eax
  int v53; // edx
  int v54; // ecx
  int v55; // r8d
  __int64 v56; // rax
  LONGLONG *v57; // [rsp+20h] [rbp-68h]
  int v58; // [rsp+28h] [rbp-60h]
  int v59; // [rsp+30h] [rbp-58h]
  LONGLONG v60; // [rsp+90h] [rbp+8h] BYREF

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
      LODWORD(v60) = ((__int64 (*)(void))W32GetCurrentWin32kSessionId)();
      v59 = 0;
      v58 = 0;
      v57 = &v60;
      if ( (int)ZwUpdateWnfStateData(&WNF_ISM_LAST_USER_ACTIVITY, 0, 0) < 0 )
      {
        a6 = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 255);
      }
      *(_QWORD *)(a1 + 64) = a2;
      v56 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 128) = v56;
      *(_QWORD *)(a1 + 72) = v56 + 1;
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
  v60 = 0;
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
      v45 = *(_QWORD *)(W32GetUserSessionState(v43, v42, v44) + 18984);
      v8 = *(_DWORD *)(*(_QWORD *)(v45 + 456) + 56LL);
      v48 = W32GetUserSessionState(v45, v46, v47);
      v50 = 0;
      if ( **(_QWORD **)(*(_QWORD *)(v48 + 18984) + 456LL) )
      {
        v51 = W32GetUserSessionState(0, v49, v44);
        TimeQuadPart = PsGetProcessCreateTimeQuadPart(**(PEPROCESS **)(*(_QWORD *)(v51 + 18984) + 456LL));
        v60 = TimeQuadPart;
        goto LABEL_68;
      }
    }
    else
    {
      v50 = 0;
    }
    v60 = 0;
LABEL_68:
    if ( (W32kEtwEnabledKeyword & 0x8000000000020000uLL) != 0
      && (unsigned __int8)(byte_140294DD8 - 1) > 2u
      && (qword_140294DC0 & 0x8000000000020000uLL) != 0
      && (qword_140294DC8 & 0x8000000000020000uLL) == qword_140294DC8
      && (Microsoft_Windows_Win32kEnableBits & 0x20) != 0 )
    {
      CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v50, 0x8000000000020000uLL, v44);
      McTemplateK0qqm_EtwWriteTransfer(v54, v53, v55, CurrentWin32kSessionId, v8, (__int64)&v60);
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
    v36 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v34) + 48);
    v38 = *(int (__fastcall **)(__int64, __int64, __int64))(v36 + 3936);
    if ( v38 && v38(v36, v35, v37) >= 0 )
    {
      v40 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, LONGLONG *, int, int))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v39) + 48)
                                                                                        + 3944LL);
      if ( v40 )
        v40((unsigned int)a2, (unsigned int)a3, a5, v6, v57, v58, v59);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14005c640  push    rbx
0x14005c642  push    rbp
0x14005c643  push    rsi
0x14005c644  push    rdi
0x14005c645  push    r12
0x14005c647  push    r13
0x14005c649  push    r14
0x14005c64b  push    r15
0x14005c64d  sub     rsp, 48h
0x14005c651  mov     ebp, [rsp+88h+arg_28]
0x14005c658  mov     r13, rdx
0x14005c65b  mov     edx, 2
0x14005c660  xor     r15d, r15d
0x14005c663  mov     edi, r8d
0x14005c666  mov     rbx, rcx
0x14005c669  lea     r10d, [rdx+1Eh]
0x14005c66d  lea     r14d, [rdx+6]
0x14005c671  lea     r8d, [rdx+2]
0x14005c675  lea     r11d, [rdx+0Eh]
0x14005c679  test    r10b, bpl
0x14005c67c  jz      short loc_14005C6BD
0x14005c67e  mov     ecx, edi
0x14005c680  sub     ecx, 1
0x14005c683  jz      loc_14005C934
0x14005c689  sub     ecx, edx
0x14005c68b  jnz     loc_14005C9B9
0x14005c691  mov     ecx, edx
0x14005c693  test    [rbx+94h], ecx
0x14005c699  jz      short loc_14005C69E
0x14005c69b  or      ebp, r8d
0x14005c69e  mov     ecx, edi
0x14005c6a0  sub     ecx, 1
0x14005c6a3  jz      loc_14005C92C
0x14005c6a9  sub     ecx, edx
0x14005c6ab  jnz     loc_14005C997
0x14005c6b1  mov     ecx, edx
0x14005c6b3  test    [rbx+90h], ecx
0x14005c6b9  jz      short loc_14005C6BD
0x14005c6bb  or      ebp, edx
0x14005c6bd  mov     r8d, ebp
0x14005c6c0  movzx   edx, r9w
0x14005c6c4  mov     ecx, edi
0x14005c6c6  call    ?UpdateInputGlobals@Power@InputTraceLogging@@SAXW4_LINP_SOURCE@@GK@Z; InputTraceLogging::Power::UpdateInputGlobals(_LINP_SOURCE,ushort,ulong)
0x14005c6cb  call    cs:__imp_KeEnterCriticalRegion
0x14005c6d2  nop     dword ptr [rax+rax+00h]
0x14005c6d7  xor     edx, edx
0x14005c6d9  mov     rcx, rbx
0x14005c6dc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14005c6e3  nop     dword ptr [rax+rax+00h]
0x14005c6e8  call    cs:__imp_W32GetUserSessionState
0x14005c6ef  nop     dword ptr [rax+rax+00h]
0x14005c6f4  mov     rcx, [rax+4CF8h]
0x14005c6fb  test    dword ptr [rcx], 2000h
0x14005c701  jnz     loc_14005C93C
0x14005c707  mov     esi, ebp
0x14005c709  mov     [rbx+88h], edi
0x14005c70f  and     esi, r14d
0x14005c712  mov     r14d, 1
0x14005c718  setnz   al
0x14005c71b  mov     [rbx+8Ch], al
0x14005c721  cmp     edi, r14d
0x14005c724  jz      short loc_14005C73D
0x14005c726  call    cs:__imp_W32GetUserSessionState
0x14005c72d  nop     dword ptr [rax+rax+00h]
0x14005c732  mov     rcx, [rax+4CF8h]
0x14005c739  lock and dword ptr [rcx], 0FFFFFFBFh
0x14005c73d  mov     r12d, ebp
0x14005c740  and     r12d, 10h
0x14005c744  jnz     short loc_14005C7B1
0x14005c746  mov     rax, r13
0x14005c749  sub     rax, [rbx+40h]
0x14005c74d  cmp     rax, 1F4h
0x14005c753  ja      loc_14005CB5F
0x14005c759  call    cs:__imp_W32GetUserSessionState
0x14005c760  nop     dword ptr [rax+rax+00h]
0x14005c765  cmp     [rax+4AD0h], r15d
0x14005c76c  jnz     loc_14005C90B
0x14005c772  mov     rcx, [rbx+8]
0x14005c776  call    EtwTraceDisplayTimeoutReset
0x14005c77b  mov     [rbx+8], r13
0x14005c77f  cmp     edi, 0Bh
0x14005c782  jle     loc_14005CBE2
0x14005c788  mov     ecx, edi
0x14005c78a  sub     ecx, 0Dh
0x14005c78d  jz      short loc_14005C79E
0x14005c78f  sub     ecx, r14d
0x14005c792  jz      short loc_14005C79E
0x14005c794  sub     ecx, 2
0x14005c797  jz      short loc_14005C79E
0x14005c799  cmp     ecx, r14d
0x14005c79c  jnz     short loc_14005C7B1
0x14005c79e  mov     rax, [rbx+48h]
0x14005c7a2  mov     [rbx+50h], rax
0x14005c7a6  inc     rax
0x14005c7a9  mov     [rbx+48h], rax
0x14005c7ad  mov     [rbx+10h], r13
0x14005c7b1  xor     edx, edx
0x14005c7b3  mov     rcx, rbx
0x14005c7b6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005c7bd  nop     dword ptr [rax+rax+00h]
0x14005c7c2  call    cs:__imp_KeLeaveCriticalRegion
0x14005c7c9  nop     dword ptr [rax+rax+00h]
0x14005c7ce  call    cs:__imp_W32GetUserSessionState
0x14005c7d5  nop     dword ptr [rax+rax+00h]
0x14005c7da  mov     [rsp+88h+arg_0], r15
0x14005c7e2  mov     rbx, r15
0x14005c7e5  mov     rcx, [rax+4CF8h]
0x14005c7ec  mov     [rcx+1368h], r13d
0x14005c7f3  call    cs:__imp_W32GetUserSessionState
0x14005c7fa  nop     dword ptr [rax+rax+00h]
0x14005c7ff  mov     rcx, 0FFFFF78000000320h
0x14005c809  mov     rdx, 0FFFFF78000000004h
0x14005c813  mov     rcx, [rcx]
0x14005c816  mov     edx, [rdx]
0x14005c818  imul    rdx, rcx
0x14005c81c  shr     rdx, 18h
0x14005c820  mov     ecx, edx
0x14005c822  sub     ecx, [rax+10E28h]
0x14005c828  cmp     ecx, 0EA60h
0x14005c82e  jnb     loc_14005C9E5
0x14005c834  test    r12d, r12d
0x14005c837  jnz     loc_14005C8C0
0x14005c83d  mov     ecx, edi
0x14005c83f  sub     ecx, r14d
0x14005c842  jz      loc_14005C94E
0x14005c848  lea     eax, [r12+2]
0x14005c84d  sub     ecx, eax
0x14005c84f  jnz     loc_14005C8D5
0x14005c855  test    esi, esi
0x14005c857  jz      loc_14005CAFC
0x14005c85d  mov     ecx, 800h; unsigned __int16
0x14005c862  mov     edx, r13d; unsigned int
0x14005c865  call    ?CitpLastInputUpdate@@YAXGI@Z; CitpLastInputUpdate(ushort,uint)
0x14005c86a  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14005c871  nop     dword ptr [rax+rax+00h]
0x14005c876  mov     rcx, [rax+30h]
0x14005c87a  mov     rax, [rcx+0F60h]
0x14005c881  test    rax, rax
0x14005c884  jz      short loc_14005C8C0
0x14005c886  call    _guard_dispatch_icall
0x14005c88b  test    eax, eax
0x14005c88d  js      short loc_14005C8C0
0x14005c88f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14005c896  nop     dword ptr [rax+rax+00h]
0x14005c89b  mov     rcx, [rax+30h]
0x14005c89f  mov     rax, [rcx+0F68h]
0x14005c8a6  test    rax, rax
0x14005c8a9  jz      short loc_14005C8C0
0x14005c8ab  mov     r8d, [rsp+88h+arg_20]
0x14005c8b3  mov     r9d, ebp
0x14005c8b6  mov     edx, edi
0x14005c8b8  mov     ecx, r13d
0x14005c8bb  call    _guard_dispatch_icall
0x14005c8c0  mov     al, r14b
0x14005c8c3  add     rsp, 48h
0x14005c8c7  pop     r15
0x14005c8c9  pop     r14
0x14005c8cb  pop     r13
0x14005c8cd  pop     r12
0x14005c8cf  pop     rdi
0x14005c8d0  pop     rsi
0x14005c8d1  pop     rbp
0x14005c8d2  pop     rbx
0x14005c8d3  retn
0x14005c8d5  sub     ecx, r14d
0x14005c8d8  jz      short loc_14005C918
0x14005c8da  sub     ecx, r14d
0x14005c8dd  jz      short loc_14005C922
0x14005c8df  sub     ecx, 6
0x14005c8e2  jz      loc_14005C96A
0x14005c8e8  sub     ecx, eax
0x14005c8ea  jz      loc_14005C97C
0x14005c8f0  cmp     ecx, 4
0x14005c8f3  jnz     loc_14005CB57
0x14005c8f9  test    esi, esi
0x14005c8fb  jz      loc_14005CB04
0x14005c901  mov     ecx, 4000h
0x14005c906  jmp     loc_14005C862
0x14005c90b  test    esi, esi
0x14005c90d  jnz     loc_14005C7B1
0x14005c913  jmp     loc_14005C772
0x14005c918  mov     ecx, 10h
0x14005c91d  jmp     loc_14005C862
0x14005c922  mov     ecx, 20h ; ' '
0x14005c927  jmp     loc_14005C862
0x14005c92c  mov     ecx, r8d
0x14005c92f  jmp     loc_14005C6B3
0x14005c934  mov     ecx, r8d
0x14005c937  jmp     loc_14005C693
0x14005c93c  mov     rcx, rbx; struct W32_PUSH_LOCK *
0x14005c93f  call    ?W32ReleasePushLockExclusiveEx@@YAXPEAVW32_PUSH_LOCK@@K@Z; W32ReleasePushLockExclusiveEx(W32_PUSH_LOCK *,ulong)
0x14005c944  mov     eax, 1
0x14005c949  jmp     loc_14005C8C3
0x14005c94e  test    bpl, 40h
0x14005c952  jnz     loc_14005C9DB
0x14005c958  test    esi, esi
0x14005c95a  jz      loc_14005CC30
0x14005c960  mov     ecx, 400h
0x14005c965  jmp     loc_14005C862
0x14005c96a  test    esi, esi
0x14005c96c  jz      loc_14005CC26
0x14005c972  mov     ecx, 1000h
0x14005c977  jmp     loc_14005C862
0x14005c97c  test    esi, esi
0x14005c97e  jnz     loc_14005CB0E
0x14005c984  test    bpl, bpl
0x14005c987  jns     loc_14005CC1C
0x14005c98d  mov     ecx, 8000h
0x14005c992  jmp     loc_14005C862
0x14005c997  sub     ecx, r14d
0x14005c99a  jz      loc_14005CB28
0x14005c9a0  sub     ecx, edx
0x14005c9a2  jz      loc_14005CB20
0x14005c9a8  cmp     ecx, r8d
0x14005c9ab  jnz     loc_14005CB18
0x14005c9b1  mov     ecx, r10d
0x14005c9b4  jmp     loc_14005C6B3
0x14005c9b9  sub     ecx, r14d
0x14005c9bc  jz      loc_14005CB40
0x14005c9c2  sub     ecx, edx
0x14005c9c4  jz      loc_14005CB38
0x14005c9ca  cmp     ecx, r8d
0x14005c9cd  jnz     loc_14005CB30
0x14005c9d3  mov     ecx, r10d
0x14005c9d6  jmp     loc_14005C693
0x14005c9db  mov     ecx, 200h
0x14005c9e0  jmp     loc_14005C862
0x14005c9e5  mov     [rax+10E28h], edx
0x14005c9eb  call    cs:__imp_W32GetUserSessionState
0x14005c9f2  nop     dword ptr [rax+rax+00h]
0x14005c9f7  cmp     [rax+4A28h], r15
0x14005c9fe  jz      loc_14005CB48
0x14005ca04  call    cs:__imp_W32GetUserSessionState
0x14005ca0b  nop     dword ptr [rax+rax+00h]
0x14005ca10  mov     rcx, [rax+4A28h]
0x14005ca17  mov     rax, [rcx+1C8h]
0x14005ca1e  mov     r15d, [rax+38h]
0x14005ca22  call    cs:__imp_W32GetUserSessionState
0x14005ca29  nop     dword ptr [rax+rax+00h]
0x14005ca2e  mov     rcx, [rax+4A28h]
0x14005ca35  mov     rax, [rcx+1C8h]
0x14005ca3c  xor     ecx, ecx
0x14005ca3e  cmp     [rax], rcx
0x14005ca41  jz      loc_14005CB4A
0x14005ca47  call    cs:__imp_W32GetUserSessionState
0x14005ca4e  nop     dword ptr [rax+rax+00h]
0x14005ca53  mov     rcx, [rax+4A28h]
0x14005ca5a  mov     rcx, [rcx+1C8h]
0x14005ca61  mov     rcx, [rcx]; Process
0x14005ca64  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14005ca6b  nop     dword ptr [rax+rax+00h]
0x14005ca70  mov     rbx, rax
0x14005ca73  mov     dword ptr [rsp+88h+arg_0], eax
0x14005ca7a  shr     rax, 20h
0x14005ca7e  mov     dword ptr [rsp+88h+arg_0+4], eax
0x14005ca85  mov     rdx, 8000000000020000h
0x14005ca8f  test    cs:W32kEtwEnabledKeyword, rdx
0x14005ca96  jz      short loc_14005CAE9
0x14005ca98  mov     al, cs:byte_140294DD8
0x14005ca9e  sub     al, r14b
0x14005caa1  cmp     al, 2
0x14005caa3  jbe     short loc_14005CAE9
0x14005caa5  test    cs:qword_140294DC0, rdx
0x14005caac  jz      short loc_14005CAE9
0x14005caae  mov     rax, cs:qword_140294DC8
0x14005cab5  and     rax, rdx
0x14005cab8  cmp     rax, cs:qword_140294DC8
0x14005cabf  jnz     short loc_14005CAE9
0x14005cac1  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 20h
0x14005cac8  jz      short loc_14005CAE9
0x14005caca  call    W32GetCurrentWin32kSessionId
0x14005cacf  mov     r9d, eax
0x14005cad2  lea     rax, [rsp+88h+arg_0]
0x14005cada  mov     [rsp+88h+var_60], rax
0x14005cadf  mov     dword ptr [rsp+88h+var_68], r15d
0x14005cae4  call    McTemplateK0qqm_EtwWriteTransfer
0x14005cae9  mov     rdx, rbx
0x14005caec  mov     ecx, r15d
0x14005caef  call    ApiSetTraceLoggingUserIsActive
0x14005caf4  xor     r15d, r15d
0x14005caf7  jmp     loc_14005C834
0x14005cafc  movzx   ecx, ax
0x14005caff  jmp     loc_14005C862
0x14005cb04  mov     ecx, 100h
0x14005cb09  jmp     loc_14005C862
0x14005cb0e  mov     ecx, 2000h
0x14005cb13  jmp     loc_14005C862
0x14005cb18  mov     ecx, r15d
0x14005cb1b  jmp     loc_14005C6B3
0x14005cb20  mov     ecx, r11d
0x14005cb23  jmp     loc_14005C6B3
0x14005cb28  mov     ecx, r14d
0x14005cb2b  jmp     loc_14005C6B3
0x14005cb30  mov     ecx, r15d
0x14005cb33  jmp     loc_14005C693
0x14005cb38  mov     ecx, r11d
0x14005cb3b  jmp     loc_14005C693
0x14005cb40  mov     ecx, r14d
0x14005cb43  jmp     loc_14005C693
0x14005cb48  xor     ecx, ecx
  ... truncated ...
```
