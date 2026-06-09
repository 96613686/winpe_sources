# CallPerInstanceInitFunctions

- ea: `0x140006520`
- end: `0x1400069db`
- name: `CallPerInstanceInitFunctions`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001970`

## callees

- `0x140001bc0`
- `0x140002150`
- `0x140004f90`
- `0x140005ccc`
- `0x140005e48`
- `0x140006520`
- `0x1400069fc`
- `0x140008474`
- `0x140008b84`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006742`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006742`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140006597`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140006597`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400069a2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400069a2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400065be`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400065be`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400066a7`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400066fc`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400066a7`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400066fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400067f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400067f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400067cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400067cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000678f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000678f`
- `ntdll!TpAllocTimer` at `0x14000671a`
- `ntdll!TpAllocTimer` at `0x14000671a`
- `ntdll!NtSetInformationProcess` at `0x140006842`
- `ntdll!NtSetInformationProcess` at `0x140006842`
- `ntdll!RtlSetProcessIsCritical` at `0x14000667e`
- `ntdll!RtlSetProcessIsCritical` at `0x14000667e`
- `ntdll!RtlImageNtHeader` at `0x14000663d`
- `ntdll!RtlImageNtHeader` at `0x14000663d`
- `ntdll!NtQueryInformationProcess` at `0x1400065ec`
- `ntdll!NtQueryInformationProcess` at `0x1400065ec`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140006651`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140006651`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x140006663`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x140006663`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400068aa`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400068aa`

## string_xrefs

- `0x140006760`: `System\CurrentControlSet\Control\SCMConfig`

## pseudocode

```c
__int64 __fastcall CallPerInstanceInitFunctions(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // ecx
  unsigned int SizeOfStackCommit; // ecx
  PIMAGE_NT_HEADERS v5; // rax
  ULONGLONG TickCount64; // rax
  int v7; // esi
  int v8; // eax
  int v9; // edi
  _BYTE ProcessInformation[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  void *v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+7Ch] [rbp-84h]
  wchar_t *v22; // [rsp+80h] [rbp-80h]
  int v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+8Ch] [rbp-74h]
  BYTE *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  wchar_t pszDest[264]; // [rsp+A0h] [rbp-60h] BYREF

  ProcessInformation[0] = 0;
  ProviderId = (GUID)*((_OWORD *)off_14000F008 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_14000F028 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_14000F000, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_14000F008, *(unsigned __int16 *)off_14000F008);
  v2 = -1;
  if ( NtQueryInformationProcess(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         ProcessAffinityUpdateMode|ProcessUserModeIOPL,
         ProcessInformation,
         1u,
         0) < 0 )
    return 0;
  if ( ProcessInformation[0] )
    CustomServiceMainRoutinesAllowed = 0;
  if ( *(_DWORD *)(a1 + 40) && !(unsigned int)InitializeSecurity(a1) )
    return 0;
  v3 = *(_DWORD *)(a1 + 80);
  if ( v3 )
  {
    SizeOfStackCommit = v3 << 10;
  }
  else
  {
    v5 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
    if ( !v5 )
      goto LABEL_15;
    SizeOfStackCommit = v5->OptionalHeader.SizeOfStackCommit;
  }
  RpcMgmtSetServerStackSize(SizeOfStackCommit);
LABEL_15:
  if ( *(_DWORD *)(a1 + 84) == 1 )
    I_RpcServerDisableExceptionFilter();
  if ( *(_DWORD *)(a1 + 88) )
    RtlSetProcessIsCritical(1u, 0, 1u);
  if ( (unsigned int)ApplyProcessMitigationPolicies(a1) )
    return 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  if ( (*(_BYTE *)(a1 + 148) & 4) != 0 )
    LODWORD(NtCurrentPeb()[1].ImageBaseAddress) = LODWORD(NtCurrentPeb()[1].ImageBaseAddress) | 1;
  *(_QWORD *)&ProviderId.Data1 = 0;
  if ( ServiceCount )
  {
    HeapSetInformation(0, (HEAP_INFORMATION_CLASS)4, 0, 0);
    if ( (int)TpAllocTimer(&ProviderId, SvchostTelemetryTimerCallback, 0, 0) >= 0 )
    {
      g_TelemetryTimer = *(_QWORD *)&ProviderId.Data1;
      TickCount64 = GetTickCount64();
      *(_DWORD *)Data = 0;
      g_LastQueryHeapInfoTime = TickCount64;
      Type = 0;
      cbData = 0;
      phkResult = 0;
      v7 = 102400;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SCMConfig", 0, 0x20019u, &phkResult) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"SvchostHeapReportingThresholdInKB", 0, &Type, Data, &cbData)
          && Type == 4
          && cbData == 4 )
        {
          v7 = *(_DWORD *)Data;
        }
        RegCloseKey(phkResult);
      }
      g_HeapReportingThresholdKb = v7;
      ArmTheServiceMemoryTracingTimer();
    }
  }
  if ( (*(_BYTE *)(a1 + 148) & 8) != 0 )
  {
    *(_DWORD *)&Data[4] = 1;
    *(_DWORD *)Data = 4;
    if ( NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessCookie|ProcessUserModeIOPL, Data, 8u) < 0 )
      return 0;
  }
  if ( (unsigned int)Feature_ResourceManagerLimits__private_IsEnabledDeviceUsageNoInline()
    && *(_QWORD *)(a1 + 32)
    && (unsigned __int8)IsRmEnableLimitsPresent()
    && !ProcessInformation[0]
    && StringCchPrintfW(pszDest, 0x104u, L"svchost_%ws", *(_QWORD *)(a1 + 32)) >= 0 )
  {
    v8 = RmEnableLimits(pszDest);
    v9 = v8;
    if ( v8 == -1073740528 || v8 == -1073739509 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_14000F000 > 5 )
    {
      while ( pszDest[++v2] != 0 )
        ;
      v24 = 0;
      v22 = pszDest;
      *(_DWORD *)Data = v9;
      v23 = 2 * v2 + 2;
      v26 = 4;
      v25 = Data;
      *(_DWORD *)&ProviderId.Data2 = 5;
      UserData.Ptr = (ULONGLONG)off_14000F008;
      ProviderId.Data1 = 184549376;
      *(_QWORD *)ProviderId.Data4 = 0;
      UserData.Size = *(unsigned __int16 *)off_14000F008;
      v19 = &unk_14000B9F8;
      UserData.Reserved = 2;
      v20 = 41;
      v21 = 1;
      Type = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 4u, &UserData);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140006520  mov     [rsp-8+arg_10], rbx
0x140006525  push    rbp
0x140006526  push    rdi
0x140006527  push    r14
0x140006529  lea     rbp, [rsp-1C0h]
0x140006531  sub     rsp, 2C0h
0x140006538  mov     rax, cs:__security_cookie
0x14000653f  xor     rax, rsp
0x140006542  mov     [rbp+1D0h+var_20], rax
0x140006549  cmp     cs:RegHandle, 0
0x140006551  mov     rdi, rcx
0x140006554  mov     rax, cs:off_14000F008
0x14000655b  mov     [rsp+2D0h+ProcessInformation], 0
0x140006560  movups  xmm0, xmmword ptr [rax-10h]
0x140006564  movups  xmmword ptr [rsp+2D0h+ProviderId.Data1], xmm0
0x140006569  jz      short loc_140006572
0x14000656b  mov     ecx, 5
0x140006570  int     29h; Win8: RtlFailFast(ecx)
0x140006572  xorps   xmm0, xmm0
0x140006575  lea     r9, RegHandle; RegHandle
0x14000657c  lea     r8, dword_14000F000; CallbackContext
0x140006583  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000658a  lea     rcx, [rsp+2D0h+ProviderId]; ProviderId
0x14000658f  movdqu  cs:xmmword_14000F028, xmm0
0x140006597  call    cs:__imp_EventRegister
0x14000659e  nop     dword ptr [rax+rax+00h]
0x1400065a3  test    eax, eax
0x1400065a5  jnz     short loc_1400065CA
0x1400065a7  mov     r8, cs:off_14000F008
0x1400065ae  mov     edx, 2
0x1400065b3  mov     rcx, cs:RegHandle
0x1400065ba  movzx   r9d, word ptr [r8]
0x1400065be  call    cs:__imp_EventSetInformation
0x1400065c5  nop     dword ptr [rax+rax+00h]
0x1400065ca  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400065d1  lea     r8, [rsp+2D0h+ProcessInformation]; ProcessInformation
0x1400065d6  xor     r14d, r14d
0x1400065d9  mov     rcx, rbx; ProcessHandle
0x1400065dc  mov     r9d, 1; ProcessInformationLength
0x1400065e2  mov     [rsp+2D0h+ReturnLength], r14; ReturnLength
0x1400065e7  mov     edx, 3Dh ; '='; ProcessInformationClass
0x1400065ec  call    cs:__imp_NtQueryInformationProcess
0x1400065f3  nop     dword ptr [rax+rax+00h]
0x1400065f8  test    eax, eax
0x1400065fa  js      loc_1400069B5
0x140006600  cmp     [rsp+2D0h+ProcessInformation], r14b
0x140006605  jz      short loc_14000660E
0x140006607  mov     cs:CustomServiceMainRoutinesAllowed, r14d
0x14000660e  cmp     [rdi+28h], r14d
0x140006612  jz      short loc_140006624
0x140006614  mov     rcx, rdi
0x140006617  call    InitializeSecurity
0x14000661c  test    eax, eax
0x14000661e  jz      loc_1400069B5
0x140006624  mov     ecx, [rdi+50h]
0x140006627  test    ecx, ecx
0x140006629  jz      short loc_140006630
0x14000662b  shl     ecx, 0Ah
0x14000662e  jmp     short loc_140006651
0x140006630  mov     rcx, gs:60h
0x140006639  mov     rcx, [rcx+10h]; BaseAddress
0x14000663d  call    cs:__imp_RtlImageNtHeader
0x140006644  nop     dword ptr [rax+rax+00h]
0x140006649  test    rax, rax
0x14000664c  jz      short loc_14000665D
0x14000664e  mov     ecx, [rax+68h]; ThreadStackSize
0x140006651  call    cs:__imp_RpcMgmtSetServerStackSize
0x140006658  nop     dword ptr [rax+rax+00h]
0x14000665d  cmp     dword ptr [rdi+54h], 1
0x140006661  jnz     short loc_14000666F
0x140006663  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x14000666a  nop     dword ptr [rax+rax+00h]
0x14000666f  cmp     [rdi+58h], r14d
0x140006673  jz      short loc_14000668A
0x140006675  mov     r8b, 1; NeedBreaks
0x140006678  xor     edx, edx; OldValue
0x14000667a  movzx   ecx, r8b; NewValue
0x14000667e  call    cs:__imp_RtlSetProcessIsCritical
0x140006685  nop     dword ptr [rax+rax+00h]
0x14000668a  mov     rcx, rdi
0x14000668d  call    ApplyProcessMitigationPolicies
0x140006692  test    eax, eax
0x140006694  jnz     loc_1400069B5
0x14000669a  xor     r9d, r9d; HeapInformationLength
0x14000669d  xor     r8d, r8d; HeapInformation
0x1400066a0  mov     edx, 1; HeapInformationClass
0x1400066a5  xor     ecx, ecx; HeapHandle
0x1400066a7  call    cs:__imp_HeapSetInformation
0x1400066ae  nop     dword ptr [rax+rax+00h]
0x1400066b3  test    byte ptr [rdi+94h], 4
0x1400066ba  jz      short loc_1400066DD
0x1400066bc  mov     rax, gs:60h
0x1400066c5  mov     ecx, [rax+378h]
0x1400066cb  mov     rax, gs:60h
0x1400066d4  or      ecx, 1
0x1400066d7  mov     [rax+378h], ecx
0x1400066dd  cmp     cs:ServiceCount, r14d
0x1400066e4  mov     qword ptr [rsp+2D0h+ProviderId.Data1], r14
0x1400066e9  jbe     loc_140006814
0x1400066ef  xor     r9d, r9d; HeapInformationLength
0x1400066f2  xor     r8d, r8d; HeapInformation
0x1400066f5  mov     edx, 4; HeapInformationClass
0x1400066fa  xor     ecx, ecx; HeapHandle
0x1400066fc  call    cs:__imp_HeapSetInformation
0x140006703  nop     dword ptr [rax+rax+00h]
0x140006708  xor     r9d, r9d
0x14000670b  lea     rdx, SvchostTelemetryTimerCallback
0x140006712  xor     r8d, r8d
0x140006715  lea     rcx, [rsp+2D0h+ProviderId]
0x14000671a  call    cs:__imp_TpAllocTimer
0x140006721  nop     dword ptr [rax+rax+00h]
0x140006726  test    eax, eax
0x140006728  js      loc_140006814
0x14000672e  mov     rax, qword ptr [rsp+2D0h+ProviderId.Data1]
0x140006733  mov     cs:g_TelemetryTimer, rax
0x14000673a  mov     [rsp+2D0h+arg_8], rsi
0x140006742  call    cs:__imp_GetTickCount64
0x140006749  nop     dword ptr [rax+rax+00h]
0x14000674e  mov     r9d, 20019h; samDesired
0x140006754  mov     dword ptr [rsp+2D0h+Data], r14d
0x140006759  mov     cs:g_LastQueryHeapInfoTime, rax
0x140006760  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SCM"...
0x140006767  lea     rax, [rsp+2D0h+phkResult]
0x14000676c  mov     [rsp+2D0h+Type], r14d
0x140006771  xor     r8d, r8d; ulOptions
0x140006774  mov     [rsp+2D0h+ReturnLength], rax; phkResult
0x140006779  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006780  mov     [rsp+2D0h+cbData], r14d
0x140006785  mov     [rsp+2D0h+phkResult], r14
0x14000678a  mov     esi, 19000h
0x14000678f  call    cs:__imp_RegOpenKeyExW
0x140006796  nop     dword ptr [rax+rax+00h]
0x14000679b  test    eax, eax
0x14000679d  jnz     short loc_140006801
0x14000679f  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1400067a4  lea     rax, [rsp+2D0h+cbData]
0x1400067a9  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1400067ae  lea     r9, [rsp+2D0h+Type]; lpType
0x1400067b3  lea     rax, [rsp+2D0h+Data]
0x1400067b8  mov     [rsp+2D0h+cbData], 4
0x1400067c0  xor     r8d, r8d; lpReserved
0x1400067c3  mov     [rsp+2D0h+ReturnLength], rax; lpData
0x1400067c8  lea     rdx, aSvchostheaprep; "SvchostHeapReportingThresholdInKB"
0x1400067cf  call    cs:__imp_RegQueryValueExW
0x1400067d6  nop     dword ptr [rax+rax+00h]
0x1400067db  test    eax, eax
0x1400067dd  jnz     short loc_1400067F0
0x1400067df  cmp     [rsp+2D0h+Type], 4
0x1400067e4  jnz     short loc_1400067F0
0x1400067e6  cmp     [rsp+2D0h+cbData], 4
0x1400067eb  cmovz   esi, dword ptr [rsp+2D0h+Data]
0x1400067f0  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1400067f5  call    cs:__imp_RegCloseKey
0x1400067fc  nop     dword ptr [rax+rax+00h]
0x140006801  mov     cs:g_HeapReportingThresholdKb, esi
0x140006807  call    ArmTheServiceMemoryTracingTimer
0x14000680c  mov     rsi, [rsp+2D0h+arg_8]
0x140006814  test    byte ptr [rdi+94h], 8
0x14000681b  jz      short loc_140006856
0x14000681d  mov     qword ptr [rsp+2D0h+Data], r14
0x140006822  lea     r8, [rsp+2D0h+Data]; ProcessInformation
0x140006827  or      dword ptr [rsp+2D0h+Data+4], 1
0x14000682c  mov     r9d, 8; ProcessInformationLength
0x140006832  mov     edx, 34h ; '4'; ProcessInformationClass
0x140006837  mov     dword ptr [rsp+2D0h+Data], 4
0x14000683f  mov     rcx, rbx; ProcessHandle
0x140006842  call    cs:__imp_NtSetInformationProcess
0x140006849  nop     dword ptr [rax+rax+00h]
0x14000684e  test    eax, eax
0x140006850  js      loc_1400069B5
0x140006856  call    Feature_ResourceManagerLimits__private_IsEnabledDeviceUsageNoInline
0x14000685b  test    eax, eax
0x14000685d  jz      loc_1400069AE
0x140006863  cmp     [rdi+20h], r14
0x140006867  jz      loc_1400069AE
0x14000686d  call    IsRmEnableLimitsPresent
0x140006872  test    al, al
0x140006874  jz      loc_1400069AE
0x14000687a  cmp     [rsp+2D0h+ProcessInformation], r14b
0x14000687f  jnz     loc_1400069AE
0x140006885  mov     r9, [rdi+20h]
0x140006889  lea     r8, aSvchostWs; "svchost_%ws"
0x140006890  mov     edx, 104h; cchDest
0x140006895  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x140006899  call    StringCchPrintfW
0x14000689e  test    eax, eax
0x1400068a0  js      loc_1400069AE
0x1400068a6  lea     rcx, [rbp+1D0h+pszDest]
0x1400068aa  call    cs:__imp_RmEnableLimits
0x1400068b1  nop     dword ptr [rax+rax+00h]
0x1400068b6  mov     edi, eax
0x1400068b8  cmp     eax, 0C0000510h
0x1400068bd  jz      short loc_1400068C6
0x1400068bf  cmp     eax, 0C000090Bh
0x1400068c4  jnz     short loc_1400068CB
0x1400068c6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400068cb  mov     ecx, cs:dword_14000F000
0x1400068d1  cmp     ecx, 5
0x1400068d4  jbe     loc_1400069AE
0x1400068da  lea     rax, [rbp+1D0h+pszDest]
0x1400068de  xchg    ax, ax
0x1400068e0  cmp     [rax+rbx*2+2], r14w
0x1400068e6  lea     rbx, [rbx+1]
0x1400068ea  jnz     short loc_1400068E0
0x1400068ec  lea     rax, [rbp+1D0h+pszDest]
0x1400068f0  mov     [rbp+1D0h+var_244], r14d
0x1400068f4  mov     [rbp+1D0h+var_250], rax
0x1400068f8  lea     rcx, _TraceLoggingMetadata
0x1400068ff  mov     dword ptr [rsp+2D0h+Data], edi
0x140006903  lea     eax, ds:2[rbx*2]
0x14000690a  mov     [rbp+1D0h+var_248], eax
0x14000690d  lea     rdx, [rsp+2D0h+ProviderId]; EventDescriptor
0x140006912  lea     rax, [rsp+2D0h+Data]
0x140006917  mov     [rbp+1D0h+var_238], 4
0x14000691f  mov     [rbp+1D0h+var_240], rax
0x140006923  xor     r9d, r9d; RelatedActivityId
0x140006926  movzx   eax, cs:word_14000B9EE
0x14000692d  xor     r8d, r8d; ActivityId
0x140006930  mov     dword ptr [rsp+2D0h+ProviderId.Data2], eax
0x140006934  mov     rax, cs:off_14000F008
0x14000693b  mov     [rsp+2D0h+UserData.Ptr], rax
0x140006940  mov     [rsp+2D0h+ProviderId.Data1], 0B000000h
0x140006948  mov     qword ptr [rsp+2D0h+ProviderId.Data4], r14
0x14000694d  movzx   eax, word ptr [rax]
0x140006950  mov     [rsp+2D0h+UserData.Size], eax
0x140006954  lea     rax, unk_14000B9F8
0x14000695b  mov     [rsp+2D0h+var_260], rax
0x140006960  lea     rax, _TraceLoggingMetadataEnd
0x140006967  sub     eax, ecx
0x140006969  mov     dword ptr [rsp+2D0h+UserData.0Ch], 2
0x140006971  mov     [rsp+2D0h+var_258], 29h ; ')'
0x140006979  mov     [rsp+2D0h+var_254], 1
0x140006981  mov     [rsp+2D0h+Type], eax
0x140006985  mov     ecx, [rsp+2D0h+Type]
0x140006989  lea     rcx, [rsp+2D0h+UserData]
0x14000698e  mov     [rsp+2D0h+lpcbData], rcx; UserData
0x140006993  mov     rcx, cs:RegHandle; RegHandle
0x14000699a  mov     dword ptr [rsp+2D0h+ReturnLength], 4; UserDataCount
0x1400069a2  call    cs:__imp_EventWriteTransfer
0x1400069a9  nop     dword ptr [rax+rax+00h]
0x1400069ae  mov     eax, 1
0x1400069b3  jmp     short loc_1400069B7
0x1400069b5  xor     eax, eax
0x1400069b7  mov     rcx, [rbp+1D0h+var_20]
0x1400069be  xor     rcx, rsp; StackCookie
0x1400069c1  call    __security_check_cookie
0x1400069c6  mov     rbx, [rsp+2D0h+arg_10]
0x1400069ce  add     rsp, 2C0h
0x1400069d5  pop     r14
0x1400069d7  pop     rdi
0x1400069d8  pop     rbp
0x1400069d9  retn
```
