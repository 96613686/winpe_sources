# UserHardErrorEx

- ea: `0x18000dda0`
- end: `0x18000e28a`
- name: `UserHardErrorEx`
- size: `1258`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dd90`
- `0x1800120c0`

## callees

- `0x18000beec`
- `0x18000bf38`
- `0x18000c050`
- `0x18000d738`
- `0x18000d870`
- `0x18000d924`
- `0x18000da7c`
- `0x18000dda0`
- `0x180012d74`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000de0e`
- `KERNELBASE!LocalAlloc` at `0x18000de0e`
- `ntdll!NtQueryInformationProcess` at `0x18000de98`
- `ntdll!NtQueryInformationProcess` at `0x18000de98`
- `ntdll!NtWaitForSingleObject` at `0x18000e226`
- `ntdll!NtWaitForSingleObject` at `0x18000e226`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1ba`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1f4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1ba`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e1f4`
- `ntdll!RtlEnterCriticalSection` at `0x18000e19c`
- `ntdll!RtlEnterCriticalSection` at `0x18000e19c`
- `ntdll!NtClose` at `0x18000e235`
- `ntdll!NtClose` at `0x18000e279`
- `ntdll!NtClose` at `0x18000e235`
- `ntdll!NtClose` at `0x18000e279`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000e0ef`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000e0ef`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e0b1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e0b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000df42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ded8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ded8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000de62`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000de62`
- `CSRSRV!CsrReplyToMessage` at `0x18000e06a`
- `CSRSRV!CsrReplyToMessage` at `0x18000e06a`
- `CSRSRV!CsrReferenceThread` at `0x18000e083`
- `CSRSRV!CsrReferenceThread` at `0x18000e083`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18000deab`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18000deab`

## pseudocode

```c
void __fastcall UserHardErrorEx(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r15d
  __int64 v5; // rdx
  int v8; // esi
  int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rbx
  int v12; // r12d
  DWORD v13; // r8d
  HANDLE v14; // rax
  void *v15; // r14
  __int64 v16; // r14
  HANDLE EventW; // rax
  void *v18; // r12
  signed __int64 v19; // rcx
  int HardErrorMode; // r15d
  unsigned int v21; // r14d
  __int64 *v22; // rcx
  __int64 *v23; // rdx
  int v24; // [rsp+30h] [rbp-20h]
  int ProcessInformation; // [rsp+34h] [rbp-1Ch] BYREF
  int v26; // [rsp+38h] [rbp-18h]
  ULONGLONG RegHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  int v28; // [rsp+98h] [rbp+48h]
  int v29; // [rsp+A8h] [rbp+58h]

  v3 = 0;
  v5 = *(unsigned int *)(a2 + 64);
  ProcessInformation = 0;
  v8 = 1;
  if ( (unsigned int)v5 > 5 )
    goto LABEL_19;
  v9 = *(_DWORD *)(a2 + 40);
  switch ( v9 )
  {
    case 1073741848:
      if ( (unsigned int)(v5 - 3) > 1 || *(_DWORD *)(a2 + 68) != 3 )
        goto LABEL_19;
      break;
    case -1073741283:
      if ( (_DWORD)v5 != 5 || *(_DWORD *)(a2 + 68) != 12 )
        goto LABEL_19;
      break;
    case -1073741500:
      if ( *(_DWORD *)(a2 + 68) )
      {
        MicrosoftTelemetryAssertTriggeredArgs(a1, v5, 1945);
        goto LABEL_19;
      }
      break;
    default:
      if ( v9 == -1073741103 && *(_DWORD *)(a2 + 68) != 1 )
      {
        MicrosoftTelemetryAssertTriggeredArgs(a1, v5, 1964);
        goto LABEL_19;
      }
      break;
  }
  if ( *(_DWORD *)(a2 + 56) >= 9u )
    goto LABEL_19;
  v10 = LocalAlloc(0x40u, 0xC8u);
  v11 = (__int64)v10;
  if ( !v10 )
    goto LABEL_19;
  v28 = 0;
  v24 = 0;
  v10[1] = a1;
  v10[24] = a3;
  if ( a1 && *(_QWORD *)(*(_QWORD *)(a1 + 56) + 56LL) )
    v3 = 1;
  v12 = *(_DWORD *)(a2 + 56);
  v13 = *(_DWORD *)(a2 + 8);
  v29 = v12;
  v26 = v3;
  v14 = OpenProcess(0x1000u, 0, v13);
  v15 = v14;
  if ( v14 )
  {
    RegHandle[0] = 0;
    NtQueryInformationProcess(v14, ProcessDefaultHardErrorMode, &ProcessInformation, 4u, 0);
    if ( !(unsigned int)GetProcessUIContextInformation(v15, RegHandle) || (v28 = 1, LODWORD(RegHandle[0]) != 1) )
      v28 = 0;
    v24 = IsProcessDWM(v15);
    CloseHandle(v15);
  }
  if ( v3 || v12 == 7 )
  {
    v16 = v11 + 24;
    v18 = 0;
    *(_OWORD *)(v11 + 24) = *(_OWORD *)a2;
    *(_OWORD *)(v11 + 40) = *(_OWORD *)(a2 + 16);
    *(_OWORD *)(v11 + 56) = *(_OWORD *)(a2 + 32);
    *(_OWORD *)(v11 + 72) = *(_OWORD *)(a2 + 48);
    *(_OWORD *)(v11 + 88) = *(_OWORD *)(a2 + 64);
    *(_OWORD *)(v11 + 104) = *(_OWORD *)(a2 + 80);
    *(_OWORD *)(v11 + 120) = *(_OWORD *)(a2 + 96);
    if ( v29 == 7 )
    {
      *(_DWORD *)(v11 + 136) |= 0x100u;
      *(_DWORD *)(v11 + 80) = 1;
      *(_QWORD *)(v11 + 8) = 0;
    }
    else
    {
      if ( a1 )
        *(_DWORD *)(v11 + 136) |= 0x10u;
      *(_DWORD *)(a2 + 60) = -1;
    }
  }
  else
  {
    v16 = v11 + 24;
    *(_OWORD *)(v11 + 24) = *(_OWORD *)a2;
    *(_OWORD *)(v11 + 40) = *(_OWORD *)(a2 + 16);
    *(_OWORD *)(v11 + 56) = *(_OWORD *)(a2 + 32);
    *(_OWORD *)(v11 + 72) = *(_OWORD *)(a2 + 48);
    *(_OWORD *)(v11 + 88) = *(_OWORD *)(a2 + 64);
    *(_OWORD *)(v11 + 104) = *(_OWORD *)(a2 + 80);
    *(_OWORD *)(v11 + 120) = *(_OWORD *)(a2 + 96);
    EventW = CreateEventW(0, 0, 0, 0);
    v18 = EventW;
    if ( !EventW )
    {
      FreePhi(v11);
LABEL_19:
      *(_DWORD *)(a2 + 60) = 1;
      return;
    }
    *(_QWORD *)(v11 + 16) = EventW;
  }
  GetHardErrorText(v11);
  if ( v29 == 7 )
  {
    *(_DWORD *)(v11 + 136) |= 8u;
    *(_DWORD *)(v11 + 84) = 6;
    if ( v3 )
    {
      CsrReplyToMessage(v16);
    }
    else
    {
      *(_DWORD *)(a2 + 60) = 6;
      if ( a1 )
        CsrReferenceThread(a1);
    }
  }
  if ( gEventSource )
    goto LABEL_51;
  RegHandle[0] = 0;
  if ( EventRegister(&PopupControlGuid, 0, 0, RegHandle) )
  {
    v19 = 0;
    RegHandle[0] = 0;
  }
  else
  {
    v19 = RegHandle[0];
  }
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&gEventSource, v19, 0) )
  {
    if ( RegHandle[0] )
      EventUnregister(RegHandle[0]);
    goto LABEL_51;
  }
  if ( RegHandle[0] )
  {
LABEL_51:
    HardErrorMode = GetHardErrorMode();
    LogErrorPopup(*(_QWORD *)(v11 + 168), *(_QWORD *)(v11 + 152));
    goto LABEL_52;
  }
  HardErrorMode = 0;
LABEL_52:
  if ( gSessionId == gServiceSessionId || v28 || v24 || (ProcessInformation & 0x4000) != 0 )
    goto LABEL_75;
  v21 = 0;
  if ( *(_DWORD *)(v11 + 64) == 1073741848 || !HardErrorMode )
    goto LABEL_63;
  if ( *(_DWORD *)(v11 + 64) != -1073741283 )
  {
    if ( HardErrorMode == 1 && (*(_BYTE *)(v11 + 136) & 0x40) == 0 )
      goto LABEL_63;
LABEL_75:
    v21 = *((_DWORD *)dwResponseDefault + *(unsigned int *)(v11 + 80));
LABEL_76:
    ReplyHardError(v11, v21);
    if ( v18 )
      NtClose(v18);
    return;
  }
  v21 = HardErrorMode != 1 ? 6 : 0;
  if ( HardErrorMode != 1 )
    goto LABEL_76;
LABEL_63:
  RtlEnterCriticalSection(&gcsUserSrv);
  if ( a1 && (*(_BYTE *)(*(_QWORD *)(a1 + 56) + 92LL) & 0x40) != 0 )
  {
    RtlLeaveCriticalSection(&gcsUserSrv);
    goto LABEL_76;
  }
  v22 = (__int64 *)gphiList;
  if ( gphiList )
  {
    do
    {
      v23 = v22;
      v22 = (__int64 *)*v22;
    }
    while ( v22 );
  }
  else
  {
    v23 = &gphiList;
  }
  *v23 = v11;
  RtlLeaveCriticalSection(&gcsUserSrv);
  if ( v29 != 7 || v26 )
    v8 = 0;
  ProcessHardErrorRequest(v8);
  if ( v18 )
  {
    NtWaitForSingleObject(v18, 0, 0);
    NtClose(v18);
    *(_DWORD *)(a2 + 60) = *(_DWORD *)(v11 + 84);
    FreePhi(v11);
  }
}

```

## disassembly

```asm
0x18000dda0  mov     [rsp-38h+arg_0], rbx
0x18000dda5  push    rbp
0x18000dda6  push    rsi
0x18000dda7  push    rdi
0x18000dda8  push    r12
0x18000ddaa  push    r13
0x18000ddac  push    r14
0x18000ddae  push    r15
0x18000ddb0  mov     rbp, rsp
0x18000ddb3  sub     rsp, 50h
0x18000ddb7  xor     r15d, r15d
0x18000ddba  mov     rdi, rdx
0x18000ddbd  mov     edx, [rdx+40h]
0x18000ddc0  mov     r14, r8
0x18000ddc3  mov     [rbp+ProcessInformation], r15d
0x18000ddc7  mov     r13, rcx
0x18000ddca  lea     esi, [r15+1]
0x18000ddce  cmp     edx, 5
0x18000ddd1  ja      loc_18000DF5E
0x18000ddd7  mov     eax, [rdi+28h]
0x18000ddda  cmp     eax, 40000018h
0x18000dddf  jnz     loc_18000DF7A
0x18000dde5  lea     eax, [rdx-3]
0x18000dde8  cmp     eax, esi
0x18000ddea  ja      loc_18000DF5E
0x18000ddf0  cmp     dword ptr [rdi+44h], 3
0x18000ddf4  jnz     loc_18000DF5E
0x18000ddfa  cmp     dword ptr [rdi+38h], 9
0x18000ddfe  jnb     loc_18000DF5E
0x18000de04  mov     edx, 0C8h; uBytes
0x18000de09  mov     ecx, 40h ; '@'; uFlags
0x18000de0e  call    cs:__imp_LocalAlloc
0x18000de15  nop     dword ptr [rax+rax+00h]
0x18000de1a  mov     rbx, rax
0x18000de1d  test    rax, rax
0x18000de20  jz      loc_18000DF5E
0x18000de26  mov     [rbp+arg_8], r15d
0x18000de2a  mov     [rbp+var_20], r15d
0x18000de2e  mov     [rax+8], r13
0x18000de32  mov     [rax+0C0h], r14
0x18000de39  test    r13, r13
0x18000de3c  jz      short loc_18000DE4B
0x18000de3e  mov     rax, [r13+38h]
0x18000de42  cmp     [rax+38h], r15
0x18000de46  jz      short loc_18000DE4B
0x18000de48  mov     r15d, esi
0x18000de4b  mov     r12d, [rdi+38h]
0x18000de4f  xor     edx, edx; bInheritHandle
0x18000de51  mov     r8d, [rdi+8]; dwProcessId
0x18000de55  mov     ecx, 1000h; dwDesiredAccess
0x18000de5a  mov     [rbp+arg_18], r12d
0x18000de5e  mov     [rbp+var_18], r15d
0x18000de62  call    cs:__imp_OpenProcess
0x18000de69  nop     dword ptr [rax+rax+00h]
0x18000de6e  mov     r14, rax
0x18000de71  test    rax, rax
0x18000de74  jz      short loc_18000DEE4
0x18000de76  mov     r9d, 4; ProcessInformationLength
0x18000de7c  mov     [rbp+RegHandle], 0
0x18000de84  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x18000de88  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x18000de91  mov     rcx, rax; ProcessHandle
0x18000de94  lea     edx, [r9+8]; ProcessInformationClass
0x18000de98  call    cs:__imp_NtQueryInformationProcess
0x18000de9f  nop     dword ptr [rax+rax+00h]
0x18000dea4  lea     rdx, [rbp+RegHandle]
0x18000dea8  mov     rcx, r14
0x18000deab  call    cs:__imp_GetProcessUIContextInformation
0x18000deb2  nop     dword ptr [rax+rax+00h]
0x18000deb7  test    eax, eax
0x18000deb9  jz      short loc_18000DEC3
0x18000debb  mov     [rbp+arg_8], esi
0x18000debe  cmp     dword ptr [rbp+RegHandle], esi
0x18000dec1  jz      short loc_18000DECA
0x18000dec3  mov     [rbp+arg_8], 0
0x18000deca  mov     rcx, r14
0x18000decd  call    IsProcessDWM
0x18000ded2  mov     rcx, r14; hObject
0x18000ded5  mov     [rbp+var_20], eax
0x18000ded8  call    cs:__imp_CloseHandle
0x18000dedf  nop     dword ptr [rax+rax+00h]
0x18000dee4  test    r15d, r15d
0x18000dee7  jnz     loc_18000DFD7
0x18000deed  cmp     r12d, 7
0x18000def1  jz      loc_18000DFD7
0x18000def7  movups  xmm0, xmmword ptr [rdi]
0x18000defa  lea     r14, [rbx+18h]
0x18000defe  xor     r9d, r9d; lpName
0x18000df01  xor     r8d, r8d; bInitialState
0x18000df04  xor     edx, edx; bManualReset
0x18000df06  movups  xmmword ptr [r14], xmm0
0x18000df0a  xor     ecx, ecx; lpEventAttributes
0x18000df0c  movups  xmm1, xmmword ptr [rdi+10h]
0x18000df10  movups  xmmword ptr [r14+10h], xmm1
0x18000df15  movups  xmm0, xmmword ptr [rdi+20h]
0x18000df19  movups  xmmword ptr [r14+20h], xmm0
0x18000df1e  movups  xmm1, xmmword ptr [rdi+30h]
0x18000df22  movups  xmmword ptr [r14+30h], xmm1
0x18000df27  movups  xmm0, xmmword ptr [rdi+40h]
0x18000df2b  movups  xmmword ptr [r14+40h], xmm0
0x18000df30  movups  xmm1, xmmword ptr [rdi+50h]
0x18000df34  movups  xmmword ptr [r14+50h], xmm1
0x18000df39  movups  xmm0, xmmword ptr [rdi+60h]
0x18000df3d  movups  xmmword ptr [r14+60h], xmm0
0x18000df42  call    cs:__imp_CreateEventW
0x18000df49  nop     dword ptr [rax+rax+00h]
0x18000df4e  mov     r12, rax
0x18000df51  test    rax, rax
0x18000df54  jnz     short loc_18000DFD1
0x18000df56  mov     rcx, rbx
0x18000df59  call    FreePhi
0x18000df5e  mov     [rdi+3Ch], esi
0x18000df61  mov     rbx, [rsp+50h+arg_0]
0x18000df69  add     rsp, 50h
0x18000df6d  pop     r15
0x18000df6f  pop     r14
0x18000df71  pop     r13
0x18000df73  pop     r12
0x18000df75  pop     rdi
0x18000df76  pop     rsi
0x18000df77  pop     rbp
0x18000df78  retn
0x18000df7a  cmp     eax, 0C000021Dh
0x18000df7f  jnz     short loc_18000DF92
0x18000df81  cmp     edx, 5
0x18000df84  jnz     short loc_18000DF5E
0x18000df86  cmp     dword ptr [rdi+44h], 0Ch
0x18000df8a  jz      loc_18000DDFA
0x18000df90  jmp     short loc_18000DF5E
0x18000df92  cmp     eax, 0C0000144h
0x18000df97  jnz     short loc_18000DFB0
0x18000df99  cmp     [rdi+44h], r15d
0x18000df9d  jz      loc_18000DDFA
0x18000dfa3  mov     r8d, 799h
0x18000dfa9  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000dfae  jmp     short loc_18000DF5E
0x18000dfb0  cmp     eax, 0C00002D1h
0x18000dfb5  jnz     loc_18000DDFA
0x18000dfbb  cmp     [rdi+44h], esi
0x18000dfbe  jz      loc_18000DDFA
0x18000dfc4  mov     r8d, 7ACh
0x18000dfca  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000dfcf  jmp     short loc_18000DF5E
0x18000dfd1  mov     [rbx+10h], rax
0x18000dfd5  jmp     short loc_18000E045
0x18000dfd7  movups  xmm0, xmmword ptr [rdi]
0x18000dfda  lea     r14, [rbx+18h]
0x18000dfde  xor     r12d, r12d
0x18000dfe1  cmp     [rbp+arg_18], 7
0x18000dfe5  movups  xmmword ptr [r14], xmm0
0x18000dfe9  movups  xmm1, xmmword ptr [rdi+10h]
0x18000dfed  movups  xmmword ptr [r14+10h], xmm1
0x18000dff2  movups  xmm0, xmmword ptr [rdi+20h]
0x18000dff6  movups  xmmword ptr [r14+20h], xmm0
0x18000dffb  movups  xmm1, xmmword ptr [rdi+30h]
0x18000dfff  movups  xmmword ptr [r14+30h], xmm1
0x18000e004  movups  xmm0, xmmword ptr [rdi+40h]
0x18000e008  movups  xmmword ptr [r14+40h], xmm0
0x18000e00d  movups  xmm1, xmmword ptr [rdi+50h]
0x18000e011  movups  xmmword ptr [r14+50h], xmm1
0x18000e016  movups  xmm0, xmmword ptr [rdi+60h]
0x18000e01a  movups  xmmword ptr [r14+60h], xmm0
0x18000e01f  jnz     short loc_18000E032
0x18000e021  bts     dword ptr [rbx+88h], 8
0x18000e029  mov     [rbx+50h], esi
0x18000e02c  mov     [rbx+8], r12
0x18000e030  jmp     short loc_18000E045
0x18000e032  test    r13, r13
0x18000e035  jz      short loc_18000E03E
0x18000e037  or      dword ptr [rbx+88h], 10h
0x18000e03e  mov     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x18000e045  mov     rcx, rbx
0x18000e048  call    GetHardErrorText
0x18000e04d  cmp     [rbp+arg_18], 7
0x18000e051  mov     eax, 6
0x18000e056  jnz     short loc_18000E08F
0x18000e058  or      dword ptr [rbx+88h], 8
0x18000e05f  mov     [rbx+54h], eax
0x18000e062  test    r15d, r15d
0x18000e065  jz      short loc_18000E078
0x18000e067  mov     rcx, r14
0x18000e06a  call    cs:__imp_CsrReplyToMessage
0x18000e071  nop     dword ptr [rax+rax+00h]
0x18000e076  jmp     short loc_18000E08F
0x18000e078  mov     [rdi+3Ch], eax
0x18000e07b  test    r13, r13
0x18000e07e  jz      short loc_18000E08F
0x18000e080  mov     rcx, r13
0x18000e083  call    cs:__imp_CsrReferenceThread
0x18000e08a  nop     dword ptr [rax+rax+00h]
0x18000e08f  cmp     cs:gEventSource, 0
0x18000e097  jnz     short loc_18000E0FB
0x18000e099  lea     r9, [rbp+RegHandle]; RegHandle
0x18000e09d  mov     [rbp+RegHandle], 0
0x18000e0a5  xor     r8d, r8d; CallbackContext
0x18000e0a8  lea     rcx, PopupControlGuid; ProviderId
0x18000e0af  xor     edx, edx; EnableCallback
0x18000e0b1  call    cs:__imp_EventRegister
0x18000e0b8  nop     dword ptr [rax+rax+00h]
0x18000e0bd  test    eax, eax
0x18000e0bf  jz      short loc_18000E0C9
0x18000e0c1  xor     ecx, ecx
0x18000e0c3  mov     [rbp+RegHandle], rcx
0x18000e0c7  jmp     short loc_18000E0CD
0x18000e0c9  mov     rcx, [rbp+RegHandle]
0x18000e0cd  xor     eax, eax
0x18000e0cf  lock cmpxchg cs:gEventSource, rcx
0x18000e0d8  jnz     short loc_18000E0E6
0x18000e0da  cmp     [rbp+RegHandle], 0
0x18000e0df  jnz     short loc_18000E0FB
0x18000e0e1  xor     r15d, r15d
0x18000e0e4  jmp     short loc_18000E116
0x18000e0e6  mov     rcx, [rbp+RegHandle]; RegHandle
0x18000e0ea  test    rcx, rcx
0x18000e0ed  jz      short loc_18000E0FB
0x18000e0ef  call    cs:__imp_EventUnregister
0x18000e0f6  nop     dword ptr [rax+rax+00h]
0x18000e0fb  call    GetHardErrorMode
0x18000e100  mov     rdx, [rbx+98h]
0x18000e107  mov     r15d, eax
0x18000e10a  mov     rcx, [rbx+0A8h]
0x18000e111  call    LogErrorPopup
0x18000e116  mov     ecx, cs:gServiceSessionId
0x18000e11c  cmp     cs:gSessionId, ecx
0x18000e122  jz      loc_18000E254
0x18000e128  cmp     [rbp+arg_8], 0
0x18000e12c  jnz     loc_18000E254
0x18000e132  cmp     [rbp+var_20], 0
0x18000e136  jnz     loc_18000E254
0x18000e13c  test    [rbp+ProcessInformation], 4000h
0x18000e143  jnz     loc_18000E254
0x18000e149  xor     r14d, r14d
0x18000e14c  cmp     dword ptr [rbx+40h], 40000018h
0x18000e153  jz      short loc_18000E192
0x18000e155  test    r15d, r15d
0x18000e158  jz      short loc_18000E192
0x18000e15a  cmp     dword ptr [rbx+40h], 0C000021Dh
0x18000e161  jnz     short loc_18000E17C
0x18000e163  mov     eax, r15d
0x18000e166  sub     eax, esi
0x18000e168  neg     eax
0x18000e16a  sbb     r14d, r14d
0x18000e16d  and     r14d, 6
0x18000e171  cmp     r15d, esi
0x18000e174  jnz     loc_18000E262
0x18000e17a  jmp     short loc_18000E192
0x18000e17c  cmp     r15d, esi
0x18000e17f  jnz     loc_18000E254
0x18000e185  test    byte ptr [rbx+88h], 40h
0x18000e18c  jnz     loc_18000E254
0x18000e192  lea     r15, gcsUserSrv
0x18000e199  mov     rcx, r15; CriticalSection
0x18000e19c  call    cs:__imp_RtlEnterCriticalSection
0x18000e1a3  nop     dword ptr [rax+rax+00h]
0x18000e1a8  test    r13, r13
0x18000e1ab  jz      short loc_18000E1CB
0x18000e1ad  mov     rax, [r13+38h]
0x18000e1b1  test    byte ptr [rax+5Ch], 40h
0x18000e1b5  jz      short loc_18000E1CB
0x18000e1b7  mov     rcx, r15; CriticalSection
0x18000e1ba  call    cs:__imp_RtlLeaveCriticalSection
0x18000e1c1  nop     dword ptr [rax+rax+00h]
0x18000e1c6  jmp     loc_18000E262
0x18000e1cb  mov     rcx, cs:gphiList
0x18000e1d2  test    rcx, rcx
0x18000e1d5  jz      short loc_18000E1E7
0x18000e1d7  mov     rax, [rcx]
0x18000e1da  mov     rdx, rcx
0x18000e1dd  mov     rcx, rax
0x18000e1e0  test    rax, rax
0x18000e1e3  jnz     short loc_18000E1D7
0x18000e1e5  jmp     short loc_18000E1EE
0x18000e1e7  lea     rdx, gphiList
0x18000e1ee  mov     rcx, r15; CriticalSection
0x18000e1f1  mov     [rdx], rbx
0x18000e1f4  call    cs:__imp_RtlLeaveCriticalSection
0x18000e1fb  nop     dword ptr [rax+rax+00h]
0x18000e200  cmp     [rbp+arg_18], 7
0x18000e204  jnz     short loc_18000E20C
0x18000e206  cmp     [rbp+var_18], 0
0x18000e20a  jz      short loc_18000E20E
0x18000e20c  xor     esi, esi
0x18000e20e  mov     ecx, esi
0x18000e210  call    ProcessHardErrorRequest
0x18000e215  test    r12, r12
0x18000e218  jz      loc_18000DF61
0x18000e21e  xor     r8d, r8d; Timeout
0x18000e221  xor     edx, edx; Alertable
0x18000e223  mov     rcx, r12; Handle
0x18000e226  call    cs:__imp_NtWaitForSingleObject
0x18000e22d  nop     dword ptr [rax+rax+00h]
0x18000e232  mov     rcx, r12; Handle
0x18000e235  call    cs:__imp_NtClose
0x18000e23c  nop     dword ptr [rax+rax+00h]
0x18000e241  mov     eax, [rbx+54h]
0x18000e244  mov     rcx, rbx
0x18000e247  mov     [rdi+3Ch], eax
0x18000e24a  call    FreePhi
0x18000e24f  jmp     loc_18000DF61
0x18000e254  mov     eax, [rbx+50h]
  ... truncated ...
```
