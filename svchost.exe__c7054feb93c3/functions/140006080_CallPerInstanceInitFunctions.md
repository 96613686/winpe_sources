# CallPerInstanceInitFunctions

- ea: `0x140006080`
- end: `0x140006514`
- name: `CallPerInstanceInitFunctions`
- size: `1172`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400018d0`

## callees

- `0x140001ac0`
- `0x140004bd0`
- `0x1400058ec`
- `0x140005a68`
- `0x140006080`
- `0x14000652c`
- `0x140007ebc`
- `0x140008544`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006266`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006318`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006266`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140006318`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1400060f7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1400060f7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400064e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400064e2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140006118`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140006118`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400061dd`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14000622c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400061dd`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x14000622c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006307`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006307`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400062e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400062e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062ad`
- `ntdll!TpSetTimer` at `0x140006352`
- `ntdll!TpSetTimer` at `0x140006352`
- `ntdll!TpAllocTimer` at `0x140006244`
- `ntdll!TpAllocTimer` at `0x140006244`
- `ntdll!NtSetInformationProcess` at `0x14000638e`
- `ntdll!NtSetInformationProcess` at `0x14000638e`
- `ntdll!RtlSetProcessIsCritical` at `0x1400061ba`
- `ntdll!RtlSetProcessIsCritical` at `0x1400061ba`
- `ntdll!RtlImageNtHeader` at `0x14000618b`
- `ntdll!RtlImageNtHeader` at `0x14000618b`
- `ntdll!NtQueryInformationProcess` at `0x140006140`
- `ntdll!NtQueryInformationProcess` at `0x140006140`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140006199`
- `RPCRT4!RpcMgmtSetServerStackSize` at `0x140006199`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x1400061a5`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x1400061a5`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400063f0`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400063f0`

## string_xrefs

- `0x14000627e`: `System\CurrentControlSet\Control\SCMConfig`

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
  __int64 *v19; // [rsp+70h] [rbp-90h]
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
    EventSetInformation(RegHandle, 2, off_14000F008, (unsigned __int16)*off_14000F008);
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
      phkResult = 0;
      g_LastTelemetryUploadTime = GetTickCount64() - 21600000;
      phkResult = (HKEY)-6000000000LL;
      TpSetTimer(g_TelemetryTimer, &phkResult, 600000, 30000);
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
      UserData.Size = (unsigned __int16)*off_14000F008;
      v19 = qword_14000B9F8;
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
0x140006080  mov     [rsp-8+arg_10], rbx
0x140006085  push    rbp
0x140006086  push    rdi
0x140006087  push    r14
0x140006089  lea     rbp, [rsp-1C0h]
0x140006091  sub     rsp, 2C0h
0x140006098  mov     rax, cs:__security_cookie
0x14000609f  xor     rax, rsp
0x1400060a2  mov     [rbp+1D0h+var_20], rax
0x1400060a9  cmp     cs:RegHandle, 0
0x1400060b1  mov     rdi, rcx
0x1400060b4  mov     rax, cs:off_14000F008
0x1400060bb  mov     [rsp+2D0h+ProcessInformation], 0
0x1400060c0  movups  xmm0, xmmword ptr [rax-10h]
0x1400060c4  movups  xmmword ptr [rsp+2D0h+ProviderId.Data1], xmm0
0x1400060c9  jz      short loc_1400060D2
0x1400060cb  mov     ecx, 5
0x1400060d0  int     29h; Win8: RtlFailFast(ecx)
0x1400060d2  xorps   xmm0, xmm0
0x1400060d5  lea     r9, RegHandle; RegHandle
0x1400060dc  lea     r8, dword_14000F000; CallbackContext
0x1400060e3  lea     rdx, _tlgEnableCallback; EnableCallback
0x1400060ea  lea     rcx, [rsp+2D0h+ProviderId]; ProviderId
0x1400060ef  movdqu  cs:xmmword_14000F028, xmm0
0x1400060f7  call    cs:__imp_EventRegister
0x1400060fd  test    eax, eax
0x1400060ff  jnz     short loc_14000611E
0x140006101  mov     r8, cs:off_14000F008
0x140006108  mov     edx, 2
0x14000610d  mov     rcx, cs:RegHandle
0x140006114  movzx   r9d, word ptr [r8]
0x140006118  call    cs:__imp_EventSetInformation
0x14000611e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140006125  lea     r8, [rsp+2D0h+ProcessInformation]; ProcessInformation
0x14000612a  xor     r14d, r14d
0x14000612d  mov     rcx, rbx; ProcessHandle
0x140006130  mov     r9d, 1; ProcessInformationLength
0x140006136  mov     [rsp+2D0h+ReturnLength], r14; ReturnLength
0x14000613b  mov     edx, 3Dh ; '='; ProcessInformationClass
0x140006140  call    cs:__imp_NtQueryInformationProcess
0x140006146  test    eax, eax
0x140006148  js      loc_1400064EF
0x14000614e  cmp     [rsp+2D0h+ProcessInformation], r14b
0x140006153  jz      short loc_14000615C
0x140006155  mov     cs:CustomServiceMainRoutinesAllowed, r14d
0x14000615c  cmp     [rdi+28h], r14d
0x140006160  jz      short loc_140006172
0x140006162  mov     rcx, rdi
0x140006165  call    InitializeSecurity
0x14000616a  test    eax, eax
0x14000616c  jz      loc_1400064EF
0x140006172  mov     ecx, [rdi+50h]
0x140006175  test    ecx, ecx
0x140006177  jz      short loc_14000617E
0x140006179  shl     ecx, 0Ah
0x14000617c  jmp     short loc_140006199
0x14000617e  mov     rcx, gs:60h
0x140006187  mov     rcx, [rcx+10h]; BaseAddress
0x14000618b  call    cs:__imp_RtlImageNtHeader
0x140006191  test    rax, rax
0x140006194  jz      short loc_14000619F
0x140006196  mov     ecx, [rax+68h]; ThreadStackSize
0x140006199  call    cs:__imp_RpcMgmtSetServerStackSize
0x14000619f  cmp     dword ptr [rdi+54h], 1
0x1400061a3  jnz     short loc_1400061AB
0x1400061a5  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x1400061ab  cmp     [rdi+58h], r14d
0x1400061af  jz      short loc_1400061C0
0x1400061b1  mov     r8b, 1; NeedBreaks
0x1400061b4  xor     edx, edx; OldValue
0x1400061b6  movzx   ecx, r8b; NewValue
0x1400061ba  call    cs:__imp_RtlSetProcessIsCritical
0x1400061c0  mov     rcx, rdi
0x1400061c3  call    ApplyProcessMitigationPolicies
0x1400061c8  test    eax, eax
0x1400061ca  jnz     loc_1400064EF
0x1400061d0  xor     r9d, r9d; HeapInformationLength
0x1400061d3  xor     r8d, r8d; HeapInformation
0x1400061d6  mov     edx, 1; HeapInformationClass
0x1400061db  xor     ecx, ecx; HeapHandle
0x1400061dd  call    cs:__imp_HeapSetInformation
0x1400061e3  test    byte ptr [rdi+94h], 4
0x1400061ea  jz      short loc_14000620D
0x1400061ec  mov     rax, gs:60h
0x1400061f5  mov     ecx, [rax+378h]
0x1400061fb  mov     rax, gs:60h
0x140006204  or      ecx, 1
0x140006207  mov     [rax+378h], ecx
0x14000620d  cmp     cs:ServiceCount, r14d
0x140006214  mov     qword ptr [rsp+2D0h+ProviderId.Data1], r14
0x140006219  jbe     loc_140006360
0x14000621f  xor     r9d, r9d; HeapInformationLength
0x140006222  xor     r8d, r8d; HeapInformation
0x140006225  mov     edx, 4; HeapInformationClass
0x14000622a  xor     ecx, ecx; HeapHandle
0x14000622c  call    cs:__imp_HeapSetInformation
0x140006232  xor     r9d, r9d
0x140006235  lea     rdx, SvchostTelemetryTimerCallback
0x14000623c  xor     r8d, r8d
0x14000623f  lea     rcx, [rsp+2D0h+ProviderId]
0x140006244  call    cs:__imp_TpAllocTimer
0x14000624a  test    eax, eax
0x14000624c  js      loc_140006360
0x140006252  mov     rax, qword ptr [rsp+2D0h+ProviderId.Data1]
0x140006257  mov     cs:g_TelemetryTimer, rax
0x14000625e  mov     [rsp+2D0h+arg_8], rsi
0x140006266  call    cs:__imp_GetTickCount64
0x14000626c  mov     r9d, 20019h; samDesired
0x140006272  mov     dword ptr [rsp+2D0h+Data], r14d
0x140006277  mov     cs:g_LastQueryHeapInfoTime, rax
0x14000627e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SCM"...
0x140006285  lea     rax, [rsp+2D0h+phkResult]
0x14000628a  mov     [rsp+2D0h+Type], r14d
0x14000628f  xor     r8d, r8d; ulOptions
0x140006292  mov     [rsp+2D0h+ReturnLength], rax; phkResult
0x140006297  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000629e  mov     [rsp+2D0h+cbData], r14d
0x1400062a3  mov     [rsp+2D0h+phkResult], r14
0x1400062a8  mov     esi, 19000h
0x1400062ad  call    cs:__imp_RegOpenKeyExW
0x1400062b3  test    eax, eax
0x1400062b5  jnz     short loc_14000630D
0x1400062b7  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x1400062bc  lea     rax, [rsp+2D0h+cbData]
0x1400062c1  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1400062c6  lea     r9, [rsp+2D0h+Type]; lpType
0x1400062cb  lea     rax, [rsp+2D0h+Data]
0x1400062d0  mov     [rsp+2D0h+cbData], 4
0x1400062d8  xor     r8d, r8d; lpReserved
0x1400062db  mov     [rsp+2D0h+ReturnLength], rax; lpData
0x1400062e0  lea     rdx, aSvchostheaprep; "SvchostHeapReportingThresholdInKB"
0x1400062e7  call    cs:__imp_RegQueryValueExW
0x1400062ed  test    eax, eax
0x1400062ef  jnz     short loc_140006302
0x1400062f1  cmp     [rsp+2D0h+Type], 4
0x1400062f6  jnz     short loc_140006302
0x1400062f8  cmp     [rsp+2D0h+cbData], 4
0x1400062fd  cmovz   esi, dword ptr [rsp+2D0h+Data]
0x140006302  mov     rcx, [rsp+2D0h+phkResult]; hKey
0x140006307  call    cs:__imp_RegCloseKey
0x14000630d  mov     cs:g_HeapReportingThresholdKb, esi
0x140006313  mov     [rsp+2D0h+phkResult], r14
0x140006318  call    cs:__imp_GetTickCount64
0x14000631e  mov     rcx, cs:g_TelemetryTimer
0x140006325  lea     rdx, [rsp+2D0h+phkResult]
0x14000632a  sub     rax, 1499700h
0x140006330  mov     r9d, 7530h
0x140006336  mov     cs:g_LastTelemetryUploadTime, rax
0x14000633d  mov     r8d, 927C0h
0x140006343  mov     rax, 0FFFFFFFE9A5F4400h
0x14000634d  mov     [rsp+2D0h+phkResult], rax
0x140006352  call    cs:__imp_TpSetTimer
0x140006358  mov     rsi, [rsp+2D0h+arg_8]
0x140006360  test    byte ptr [rdi+94h], 8
0x140006367  jz      short loc_14000639C
0x140006369  mov     qword ptr [rsp+2D0h+Data], r14
0x14000636e  lea     r8, [rsp+2D0h+Data]; ProcessInformation
0x140006373  or      dword ptr [rsp+2D0h+Data+4], 1
0x140006378  mov     r9d, 8; ProcessInformationLength
0x14000637e  mov     edx, 34h ; '4'; ProcessInformationClass
0x140006383  mov     dword ptr [rsp+2D0h+Data], 4
0x14000638b  mov     rcx, rbx; ProcessHandle
0x14000638e  call    cs:__imp_NtSetInformationProcess
0x140006394  test    eax, eax
0x140006396  js      loc_1400064EF
0x14000639c  call    Feature_ResourceManagerLimits__private_IsEnabledDeviceUsageNoInline
0x1400063a1  test    eax, eax
0x1400063a3  jz      loc_1400064E8
0x1400063a9  cmp     [rdi+20h], r14
0x1400063ad  jz      loc_1400064E8
0x1400063b3  call    IsRmEnableLimitsPresent
0x1400063b8  test    al, al
0x1400063ba  jz      loc_1400064E8
0x1400063c0  cmp     [rsp+2D0h+ProcessInformation], r14b
0x1400063c5  jnz     loc_1400064E8
0x1400063cb  mov     r9, [rdi+20h]
0x1400063cf  lea     r8, aSvchostWs; "svchost_%ws"
0x1400063d6  mov     edx, 104h; cchDest
0x1400063db  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x1400063df  call    StringCchPrintfW
0x1400063e4  test    eax, eax
0x1400063e6  js      loc_1400064E8
0x1400063ec  lea     rcx, [rbp+1D0h+pszDest]
0x1400063f0  call    cs:__imp_RmEnableLimits
0x1400063f6  mov     edi, eax
0x1400063f8  cmp     eax, 0C0000510h
0x1400063fd  jz      short loc_140006406
0x1400063ff  cmp     eax, 0C000090Bh
0x140006404  jnz     short loc_14000640B
0x140006406  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000640b  mov     ecx, cs:dword_14000F000
0x140006411  cmp     ecx, 5
0x140006414  jbe     loc_1400064E8
0x14000641a  lea     rax, [rbp+1D0h+pszDest]
0x14000641e  xchg    ax, ax
0x140006420  cmp     [rax+rbx*2+2], r14w
0x140006426  lea     rbx, [rbx+1]
0x14000642a  jnz     short loc_140006420
0x14000642c  lea     rax, [rbp+1D0h+pszDest]
0x140006430  mov     [rbp+1D0h+var_244], r14d
0x140006434  mov     [rbp+1D0h+var_250], rax
0x140006438  lea     rcx, _TraceLoggingMetadata
0x14000643f  mov     dword ptr [rsp+2D0h+Data], edi
0x140006443  lea     eax, ds:2[rbx*2]
0x14000644a  mov     [rbp+1D0h+var_248], eax
0x14000644d  lea     rdx, [rsp+2D0h+ProviderId]; EventDescriptor
0x140006452  lea     rax, [rsp+2D0h+Data]
0x140006457  mov     [rbp+1D0h+var_238], 4
0x14000645f  mov     [rbp+1D0h+var_240], rax
0x140006463  xor     r9d, r9d; RelatedActivityId
0x140006466  movzx   eax, cs:word_14000B9EE
0x14000646d  xor     r8d, r8d; ActivityId
0x140006470  mov     dword ptr [rsp+2D0h+ProviderId.Data2], eax
0x140006474  mov     rax, cs:off_14000F008
0x14000647b  mov     [rsp+2D0h+UserData.Ptr], rax
0x140006480  mov     [rsp+2D0h+ProviderId.Data1], 0B000000h
0x140006488  mov     qword ptr [rsp+2D0h+ProviderId.Data4], r14
0x14000648d  movzx   eax, word ptr [rax]
0x140006490  mov     [rsp+2D0h+UserData.Size], eax
0x140006494  lea     rax, qword_14000B9F8
0x14000649b  mov     [rsp+2D0h+var_260], rax
0x1400064a0  lea     rax, _TraceLoggingMetadataEnd
0x1400064a7  sub     eax, ecx
0x1400064a9  mov     dword ptr [rsp+2D0h+UserData.0Ch], 2
0x1400064b1  mov     [rsp+2D0h+var_258], 29h ; ')'
0x1400064b9  mov     [rsp+2D0h+var_254], 1
0x1400064c1  mov     [rsp+2D0h+Type], eax
0x1400064c5  mov     ecx, [rsp+2D0h+Type]
0x1400064c9  lea     rcx, [rsp+2D0h+UserData]
0x1400064ce  mov     [rsp+2D0h+lpcbData], rcx; UserData
0x1400064d3  mov     rcx, cs:RegHandle; RegHandle
0x1400064da  mov     dword ptr [rsp+2D0h+ReturnLength], 4; UserDataCount
0x1400064e2  call    cs:__imp_EventWriteTransfer
0x1400064e8  mov     eax, 1
0x1400064ed  jmp     short loc_1400064F1
0x1400064ef  xor     eax, eax
0x1400064f1  mov     rcx, [rbp+1D0h+var_20]
0x1400064f8  xor     rcx, rsp; StackCookie
0x1400064fb  call    __security_check_cookie
0x140006500  mov     rbx, [rsp+2D0h+arg_10]
0x140006508  add     rsp, 2C0h
0x14000650f  pop     r14
0x140006511  pop     rdi
0x140006512  pop     rbp
0x140006513  retn
```
