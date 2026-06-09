# UmpoSmartPresenceInit

- ea: `0x18001735c`
- end: `0x18001760d`
- name: `UmpoSmartPresenceInit`
- size: `689`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x18000f3dc`
- `0x18001735c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800173f0`
- `ntdll!RtlAllocateHeap` at `0x1800173f0`
- `ntdll!RtlFreeHeap` at `0x180017536`
- `ntdll!RtlFreeHeap` at `0x180017536`
- `ntdll!DbgPrint` at `0x1800175f8`
- `ntdll!DbgPrint` at `0x1800175f8`
- `ntdll!RtlNtStatusToDosError` at `0x1800173c5`
- `ntdll!RtlNtStatusToDosError` at `0x1800173c5`
- `ntdll!NtPowerInformation` at `0x1800173b9`
- `ntdll!NtPowerInformation` at `0x1800173b9`
- `ntdll!NtCreateIRTimer` at `0x18001743f`
- `ntdll!NtCreateIRTimer` at `0x18001743f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017475`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017493`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017475`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017493`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800174c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800174f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800174c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800174f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017457`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017457`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001738b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001738b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017581`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017581`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017419`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017510`

## pseudocode

```c
__int64 __fastcall UmpoSmartPresenceInit(_DWORD *a1)
{
  int v2; // eax
  ULONG LastError; // eax
  unsigned int v4; // ebx
  LSTATUS ValueW; // eax
  unsigned int v6; // ecx
  char v7; // bl
  char v8; // al
  DWORD cbSid; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-Ch] BYREF
  __int64 InputBuffer; // [rsp+48h] [rbp-8h] BYREF
  char OutputBuffer; // [rsp+78h] [rbp+28h] BYREF
  int v14; // [rsp+80h] [rbp+30h] BYREF
  unsigned int pvData; // [rsp+88h] [rbp+38h] BYREF

  pvData = 0;
  v14 = 0;
  cbSid = 0;
  OutputBuffer = 0;
  pcbData = 0;
  InitializeCriticalSection(&UmpoSmartPresenceLock);
  byte_180024808 = 1;
  InputBuffer = 4;
  v2 = NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, &OutputBuffer, 1u);
  if ( v2 < 0 )
    goto LABEL_2;
  if ( !OutputBuffer )
    return 0;
  cbSid = 68;
  UmpoNullSid = RtlAllocateHeap(UmpoHeapHandle, 8u, 0x44u);
  if ( !UmpoNullSid )
  {
    v4 = 14;
LABEL_14:
    if ( UmpoTimeUpdateWork )
    {
      CloseThreadpoolWait(UmpoTimeUpdateWork);
      UmpoTimeUpdateWork = 0;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( UmpoTimerWork )
    {
      CloseThreadpoolWait(UmpoTimerWork);
      UmpoTimerWork = 0;
    }
    if ( h )
    {
      CloseHandle(h);
      h = 0;
    }
    if ( UmpoNullSid )
    {
      RtlFreeHeap(UmpoHeapHandle, 0, UmpoNullSid);
      UmpoNullSid = 0;
    }
    return v4;
  }
  if ( !CreateWellKnownSid(WinNullSid, 0, UmpoNullSid, &cbSid) )
    goto LABEL_12;
  v14 = 6;
  v2 = NtCreateIRTimer(&h, &v14, 2031619);
  if ( v2 < 0 )
  {
LABEL_2:
    LastError = RtlNtStatusToDosError(v2);
    goto LABEL_13;
  }
  hObject = CreateEventW(0, 0, 0, 0);
  if ( !hObject
    || (UmpoTimerWork = CreateThreadpoolWait(UmpoSmartPresenceTimerWaitCallback, 0, 0)) == 0
    || (UmpoTimeUpdateWork = CreateThreadpoolWait(UmpoSmartPresenceTimeUpdateWaitCallback, 0, 0)) == 0 )
  {
LABEL_12:
    LastError = GetLastError();
LABEL_13:
    v4 = LastError;
    if ( !LastError )
      return v4;
    goto LABEL_14;
  }
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\Power",
             L"SmartPresenceConfidence",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    UmpoSmartPresenceMinConfidence = 65;
  }
  else
  {
    v6 = pvData;
    v7 = 100;
    if ( pvData > 0x64 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v6 = pvData;
    }
    if ( v6 < 0x64 )
      v7 = v6;
    UmpoSmartPresenceMinConfidence = v7;
  }
  v8 = UmpoDebug;
  v4 = 0;
  UmpoSmartPresenceModeDisabled = 1;
  UmpoSmartPresenceSuspendCount = 1;
  *a1 = 512;
  UmpoSmartPresenceEnabled = 1;
  if ( (v8 & 2) != 0 )
    DbgPrint("%s: Enabled support\n", "UmpoSmartPresenceInit");
  return v4;
}

```

## disassembly

```asm
0x18001735c  mov     [rsp-18h+arg_0], rbx
0x180017361  push    rbp
0x180017362  push    rsi
0x180017363  push    rdi
0x180017364  mov     rbp, rsp
0x180017367  sub     rsp, 50h
0x18001736b  xor     esi, esi
0x18001736d  mov     rdi, rcx
0x180017370  lea     rcx, UmpoSmartPresenceLock; lpCriticalSection
0x180017377  mov     [rbp+arg_18], esi
0x18001737a  mov     [rbp+arg_10], esi
0x18001737d  mov     [rbp+cbSid], esi
0x180017380  mov     [rbp+InputBuffer], rsi
0x180017384  mov     [rbp+OutputBuffer], sil
0x180017388  mov     [rbp+var_C], esi
0x18001738b  call    cs:__imp_InitializeCriticalSection
0x180017391  lea     ebx, [rsi+8]
0x180017394  mov     cs:byte_180024808, 1
0x18001739b  mov     r8d, ebx; InputBufferLength
0x18001739e  mov     [rbp+InputBuffer], 4
0x1800173a6  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x1800173aa  mov     [rsp+50h+OutputBufferLength], 1; OutputBufferLength
0x1800173b2  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x1800173b6  lea     ecx, [rsi+57h]; PowerInformationLevel
0x1800173b9  call    cs:__imp_NtPowerInformation
0x1800173bf  test    eax, eax
0x1800173c1  jns     short loc_1800173D0
0x1800173c3  mov     ecx, eax; Status
0x1800173c5  call    cs:__imp_RtlNtStatusToDosError
0x1800173cb  jmp     loc_1800174AF
0x1800173d0  cmp     [rbp+OutputBuffer], sil
0x1800173d4  jnz     short loc_1800173DD
0x1800173d6  mov     ebx, esi
0x1800173d8  jmp     loc_1800175FE
0x1800173dd  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800173e4  mov     r8d, 44h ; 'D'; Size
0x1800173ea  mov     edx, ebx; Flags
0x1800173ec  mov     [rbp+cbSid], r8d
0x1800173f0  call    cs:__imp_RtlAllocateHeap
0x1800173f6  mov     cs:UmpoNullSid, rax
0x1800173fd  test    rax, rax
0x180017400  jnz     short loc_18001740A
0x180017402  lea     ebx, [rax+0Eh]
0x180017405  jmp     loc_1800174B9
0x18001740a  mov     r8, cs:UmpoNullSid; pSid
0x180017411  lea     r9, [rbp+cbSid]; cbSid
0x180017415  xor     edx, edx; DomainSid
0x180017417  xor     ecx, ecx; WellKnownSidType
0x180017419  call    cs:__imp_CreateWellKnownSid
0x18001741f  test    eax, eax
0x180017421  jz      loc_1800174A9
0x180017427  mov     r8d, 1F0003h
0x18001742d  mov     [rbp+arg_10], 6
0x180017434  lea     rdx, [rbp+arg_10]
0x180017438  lea     rcx, h
0x18001743f  call    cs:__imp_NtCreateIRTimer
0x180017445  test    eax, eax
0x180017447  js      loc_1800173C3
0x18001744d  xor     r9d, r9d; lpName
0x180017450  xor     r8d, r8d; bInitialState
0x180017453  xor     edx, edx; bManualReset
0x180017455  xor     ecx, ecx; lpEventAttributes
0x180017457  call    cs:__imp_CreateEventW
0x18001745d  mov     cs:hObject, rax
0x180017464  test    rax, rax
0x180017467  jz      short loc_1800174A9
0x180017469  xor     r8d, r8d; pcbe
0x18001746c  lea     rcx, UmpoSmartPresenceTimerWaitCallback; pfnwa
0x180017473  xor     edx, edx; pv
0x180017475  call    cs:__imp_CreateThreadpoolWait
0x18001747b  mov     cs:UmpoTimerWork, rax
0x180017482  test    rax, rax
0x180017485  jz      short loc_1800174A9
0x180017487  xor     r8d, r8d; pcbe
0x18001748a  lea     rcx, UmpoSmartPresenceTimeUpdateWaitCallback; pfnwa
0x180017491  xor     edx, edx; pv
0x180017493  call    cs:__imp_CreateThreadpoolWait
0x180017499  mov     cs:UmpoTimeUpdateWork, rax
0x1800174a0  test    rax, rax
0x1800174a3  jnz     loc_180017548
0x1800174a9  call    cs:__imp_GetLastError
0x1800174af  mov     ebx, eax
0x1800174b1  test    eax, eax
0x1800174b3  jz      loc_1800175FE
0x1800174b9  mov     rcx, cs:UmpoTimeUpdateWork; pwa
0x1800174c0  test    rcx, rcx
0x1800174c3  jz      short loc_1800174D2
0x1800174c5  call    cs:__imp_CloseThreadpoolWait
0x1800174cb  mov     cs:UmpoTimeUpdateWork, rsi
0x1800174d2  mov     rcx, cs:hObject; hObject
0x1800174d9  test    rcx, rcx
0x1800174dc  jz      short loc_1800174EB
0x1800174de  call    cs:__imp_CloseHandle
0x1800174e4  mov     cs:hObject, rsi
0x1800174eb  mov     rcx, cs:UmpoTimerWork; pwa
0x1800174f2  test    rcx, rcx
0x1800174f5  jz      short loc_180017504
0x1800174f7  call    cs:__imp_CloseThreadpoolWait
0x1800174fd  mov     cs:UmpoTimerWork, rsi
0x180017504  mov     rcx, cs:h; hObject
0x18001750b  test    rcx, rcx
0x18001750e  jz      short loc_18001751D
0x180017510  call    cs:__imp_CloseHandle
0x180017516  mov     cs:h, rsi
0x18001751d  mov     r8, cs:UmpoNullSid; P
0x180017524  test    r8, r8
0x180017527  jz      loc_1800175FE
0x18001752d  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180017534  xor     edx, edx; Flags
0x180017536  call    cs:__imp_RtlFreeHeap
0x18001753c  mov     cs:UmpoNullSid, rsi
0x180017543  jmp     loc_1800175FE
0x180017548  lea     rax, [rbp+var_C]
0x18001754c  mov     [rbp+var_C], 4
0x180017553  mov     [rsp+50h+pcbData], rax; pcbData
0x180017558  lea     r8, aSmartpresencec; "SmartPresenceConfidence"
0x18001755f  lea     rax, [rbp+arg_18]
0x180017563  mov     r9d, 10h; dwFlags
0x180017569  mov     [rsp+50h+pvData], rax; pvData
0x18001756e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pow"...
0x180017575  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001757c  mov     qword ptr [rsp+50h+OutputBufferLength], rsi; pdwType
0x180017581  call    cs:__imp_RegGetValueW
0x180017587  test    eax, eax
0x180017589  jz      short loc_18001759E
0x18001758b  cmp     eax, 2
0x18001758e  jz      short loc_180017595
0x180017590  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180017595  mov     cs:UmpoSmartPresenceMinConfidence, 41h ; 'A'
0x18001759c  jmp     short loc_1800175C0
0x18001759e  mov     ecx, [rbp+arg_18]
0x1800175a1  mov     ebx, 64h ; 'd'
0x1800175a6  cmp     ecx, ebx
0x1800175a8  jbe     short loc_1800175B2
0x1800175aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800175af  mov     ecx, [rbp+arg_18]
0x1800175b2  cmp     ecx, ebx
0x1800175b4  movzx   eax, cl
0x1800175b7  cmovb   ebx, eax
0x1800175ba  mov     cs:UmpoSmartPresenceMinConfidence, bl
0x1800175c0  mov     eax, cs:UmpoDebug
0x1800175c6  mov     ebx, esi
0x1800175c8  mov     cs:UmpoSmartPresenceModeDisabled, 1
0x1800175cf  mov     cs:UmpoSmartPresenceSuspendCount, 1
0x1800175d9  mov     dword ptr [rdi], 200h
0x1800175df  mov     cs:UmpoSmartPresenceEnabled, 1
0x1800175e6  test    al, 2
0x1800175e8  jz      short loc_1800175FE
0x1800175ea  lea     rdx, aUmposmartprese_1; "UmpoSmartPresenceInit"
0x1800175f1  lea     rcx, aSEnabledSuppor; "%s: Enabled support\n"
0x1800175f8  call    cs:__imp_DbgPrint
0x1800175fe  mov     eax, ebx
0x180017600  mov     rbx, [rsp+50h+arg_0]
0x180017605  add     rsp, 50h
0x180017609  pop     rdi
0x18001760a  pop     rsi
0x18001760b  pop     rbp
0x18001760c  retn
```
