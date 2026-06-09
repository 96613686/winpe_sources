# UmpoInternalPowerPolicyInit

- ea: `0x18000a030`
- end: `0x18000a56d`
- name: `UmpoInternalPowerPolicyInit`
- size: `1341`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ed10`

## callees

- `0x180005480`
- `0x18000a030`
- `0x18000a574`
- `0x18000a990`
- `0x18000f3dc`
- `0x180010070`
- `0x180010946`
- `0x180013414`
- `0x180013598`
- `0x180019010`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000a284`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000a284`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000a249`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000a249`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a3aa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a3b7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a3aa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000a3b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a517`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a534`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a517`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a534`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a371`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a396`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a371`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a396`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a3d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a232`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a2b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a232`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a2b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a32d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a32d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a107`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a14d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a18b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a0cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a107`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a14d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a18b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a1cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a443`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a485`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a1e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000a1e5`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a4f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000a4f7`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18000a408`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18000a408`

## string_xrefs

- `0x18000a214`: `System\CurrentControlSet\Control\Power\SecurityDescriptors`
- `0x18000a27d`: `PowerSettingsUserStatePath`

## pseudocode

```c
__int64 UmpoInternalPowerPolicyInit()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  unsigned int LastError; // ebx
  char IsStateSeparationEnabled; // di
  LSTATUS v4; // eax
  BYTE v5; // al
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  cbData = 0;
  *(_DWORD *)Data = 0;
  memset_0(SubKey, 0, 0x20Au);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( (_DWORD)UmpoOverlaySchemeSuspendMask )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned __int64)UmpoPowerControlKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Power", 0, 0x2001Fu, &UmpoPowerControlKey);
  UmpoInitializePowerSettingOverrides(v1, v0);
  if ( (unsigned __int64)UmpoSystemPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Control\\Power\\PowerSettings",
                0,
                0x2001Fu,
                &UmpoSystemPowerRootKey);
  if ( !LastError )
  {
    if ( (unsigned __int64)UmpoUserPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
                  0,
                  0x20019u,
                  &UmpoUserPowerRootKey);
    if ( LastError == 2 )
    {
      if ( !qword_1800246D0 )
        goto LABEL_38;
      qword_1800246D0();
      LastError = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
                    0,
                    0x20019u,
                    &UmpoUserPowerRootKey);
    }
    if ( !LastError )
    {
      if ( (unsigned __int64)UmpoPpmProfileEventsRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      LastError = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\Power\\Profile\\Events\\{54533251-82be-4824-96c1-47b60b740d00}",
                    0,
                    0x20019u,
                    &UmpoPpmProfileEventsRootKey);
      if ( (LastError & 0xFFFFFFFD) != 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        goto LABEL_38;
      }
      UmpoUserPowerTlsSlot = TlsAlloc();
      if ( UmpoUserPowerTlsSlot == -1 )
      {
        LastError = GetLastError();
        goto LABEL_38;
      }
      LastError = RegCreateKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\Power\\SecurityDescriptors",
                    0,
                    0,
                    0,
                    0x2001Fu,
                    0,
                    &UmpoPowerSecurityDescriptorRootKey,
                    0);
      if ( !LastError )
      {
        UmpoFullPowerPlanSupportDisabled = 0;
        IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
        if ( IsStateSeparationEnabled )
        {
          RtlGetPersistedStateLocation(
            L"PowerSettingsUserStatePath",
            0,
            L"System\\CurrentControlSet\\Control\\Power\\User\\PowerSchemes",
            0,
            SubKey,
            520,
            0);
          LastError = RegCreateKeyExW(
                        HKEY_LOCAL_MACHINE,
                        SubKey,
                        0,
                        0,
                        0,
                        0x2001Fu,
                        0,
                        &UmpoUserPowerStateSepRootKey,
                        0);
          if ( LastError )
            goto LABEL_38;
          LastError = UmpoInternalOpenGUIDSubKey(
                        UmpoUserPowerStateSepRootKey,
                        &GUID_TYPICAL_POWER_SAVINGS,
                        &hKey,
                        0x2001Fu,
                        0,
                        0);
          if ( LastError )
            goto LABEL_38;
          UmpoStateSeparationEnabled = 1;
          cbData = 4;
          v4 = RegQueryValueExW(UmpoPowerControlKey, L"FullPowerPlanSupportDisabled", 0, 0, Data, &cbData);
          LastError = v4;
          if ( v4 == 2 )
          {
            v5 = 0;
            *(_DWORD *)Data = 0;
          }
          else
          {
            if ( v4 )
              goto LABEL_38;
            v5 = Data[0];
          }
          UmpoFullPowerPlanSupportDisabled = v5;
        }
        memset_0(&UmpoPowerSubGroupCache, 0, 0x78u);
        InitializeCriticalSection(&CriticalSection);
        byte_180024DF0 = 1;
        memset_0(&UmpoPowerSettingCache, 0, 0x78u);
        InitializeCriticalSection(&stru_180024D08);
        byte_180024D30 = 1;
        InitializeSRWLock(&UmpoUserPowerLock);
        InitializeSRWLock(&UmpoDefaultSecurityDescriptorLock);
        if ( byte_180024FA8 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        EnterCriticalSection(&UmpoSchemeLock);
        LastError = UmpoCheckAndUpdateOverlayNotification(0);
        if ( byte_180024FA8 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        LeaveCriticalSection(&UmpoSchemeLock);
        if ( IsStateSeparationEnabled )
        {
          if ( IsApiSetImplemented("ext-ms-win-devmgmt-policy-l1-1-0") )
          {
            LastError = UmpoInternalInitializeSubscribeOnProvisioningComplete();
            if ( LastError || (LastError = UmpoInternalInitializeAdvancedPowerSettings()) != 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
      }
    }
  }
LABEL_38:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( LastError )
  {
    if ( (unsigned __int64)UmpoSystemPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(UmpoSystemPowerRootKey);
      UmpoSystemPowerRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( (unsigned __int64)UmpoUserPowerRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(UmpoUserPowerRootKey);
      UmpoUserPowerRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( (unsigned __int64)UmpoPowerSecurityDescriptorRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(UmpoPowerSecurityDescriptorRootKey);
      UmpoPowerSecurityDescriptorRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( (unsigned __int64)UmpoPowerControlKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(UmpoPowerControlKey);
      UmpoPowerControlKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( (unsigned __int64)UmpoUserPowerStateSepRootKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(UmpoUserPowerStateSepRootKey);
      UmpoUserPowerStateSepRootKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    if ( UmpoUserPowerTlsSlot != -1 )
    {
      TlsFree(UmpoUserPowerTlsSlot);
      UmpoUserPowerTlsSlot = -1;
    }
    if ( byte_180024DF0 )
    {
      DeleteCriticalSection(&CriticalSection);
      byte_180024DF0 = 0;
    }
    if ( byte_180024D30 )
    {
      DeleteCriticalSection(&stru_180024D08);
      byte_180024D30 = 0;
    }
  }
  else
  {
    UmpoPowerPolicyInitialized = 1;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000a030  push    rbp
0x18000a032  push    rbx
0x18000a033  push    rsi
0x18000a034  push    rdi
0x18000a035  push    r12
0x18000a037  push    r13
0x18000a039  push    r15
0x18000a03b  lea     rbp, [rsp-180h]
0x18000a043  sub     rsp, 280h
0x18000a04a  mov     rax, cs:__security_cookie
0x18000a051  xor     rax, rsp
0x18000a054  mov     [rbp+1B0h+var_40], rax
0x18000a05b  xor     esi, esi
0x18000a05d  lea     rcx, [rsp+2B0h+SubKey]; void *
0x18000a062  xor     edx, edx; Val
0x18000a064  mov     [rsp+2B0h+cbData], esi
0x18000a068  mov     r8d, 20Ah; Size
0x18000a06e  mov     dword ptr [rsp+2B0h+Data], esi
0x18000a072  call    memset_0
0x18000a077  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000a07b  cmp     cs:UmpoOverlaySchemeSuspendMask, esi
0x18000a081  mov     [rsp+2B0h+hKey], r15
0x18000a086  jz      short loc_18000A08D
0x18000a088  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a08d  mov     rax, cs:UmpoPowerControlKey
0x18000a094  dec     rax
0x18000a097  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a09b  ja      short loc_18000A0A2
0x18000a09d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a0a2  lea     rax, UmpoPowerControlKey
0x18000a0a9  mov     r13d, 2001Fh
0x18000a0af  mov     r12, 0FFFFFFFF80000002h
0x18000a0b6  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000a0bb  mov     r9d, r13d; samDesired
0x18000a0be  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a0c5  mov     rcx, r12; hKey
0x18000a0c8  xor     r8d, r8d; ulOptions
0x18000a0cb  call    cs:__imp_RegOpenKeyExW
0x18000a0d1  call    UmpoInitializePowerSettingOverrides
0x18000a0d6  mov     rax, cs:UmpoSystemPowerRootKey
0x18000a0dd  dec     rax
0x18000a0e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a0e4  ja      short loc_18000A0EB
0x18000a0e6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a0eb  lea     rax, UmpoSystemPowerRootKey
0x18000a0f2  mov     r9d, r13d; samDesired
0x18000a0f5  xor     r8d, r8d; ulOptions
0x18000a0f8  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000a0fd  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Pow"...
0x18000a104  mov     rcx, r12; hKey
0x18000a107  call    cs:__imp_RegOpenKeyExW
0x18000a10d  mov     ebx, eax
0x18000a10f  test    eax, eax
0x18000a111  jnz     loc_18000A434
0x18000a117  mov     rax, cs:UmpoUserPowerRootKey
0x18000a11e  dec     rax
0x18000a121  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a125  ja      short loc_18000A12C
0x18000a127  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a12c  lea     rax, UmpoUserPowerRootKey
0x18000a133  mov     edi, 20019h
0x18000a138  mov     r9d, edi; samDesired
0x18000a13b  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000a140  xor     r8d, r8d; ulOptions
0x18000a143  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a14a  mov     rcx, r12; hKey
0x18000a14d  call    cs:__imp_RegOpenKeyExW
0x18000a153  mov     ebx, eax
0x18000a155  cmp     eax, 2
0x18000a158  jnz     short loc_18000A193
0x18000a15a  mov     rax, cs:qword_1800246D0
0x18000a161  test    rax, rax
0x18000a164  jz      loc_18000A434
0x18000a16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a16f  lea     rax, UmpoUserPowerRootKey
0x18000a176  mov     r9d, edi; samDesired
0x18000a179  xor     r8d, r8d; ulOptions
0x18000a17c  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000a181  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a188  mov     rcx, r12; hKey
0x18000a18b  call    cs:__imp_RegOpenKeyExW
0x18000a191  mov     ebx, eax
0x18000a193  test    ebx, ebx
0x18000a195  jnz     loc_18000A434
0x18000a19b  mov     rax, cs:UmpoPpmProfileEventsRootKey
0x18000a1a2  dec     rax
0x18000a1a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a1a9  ja      short loc_18000A1B0
0x18000a1ab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a1b0  lea     rax, UmpoPpmProfileEventsRootKey
0x18000a1b7  mov     r9d, edi; samDesired
0x18000a1ba  xor     r8d, r8d; ulOptions
0x18000a1bd  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000a1c2  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a1c9  mov     rcx, r12; hKey
0x18000a1cc  call    cs:__imp_RegOpenKeyExW
0x18000a1d2  mov     ebx, eax
0x18000a1d4  test    eax, 0FFFFFFFDh
0x18000a1d9  jz      short loc_18000A1E5
0x18000a1db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a1e0  jmp     loc_18000A434
0x18000a1e5  call    cs:__imp_TlsAlloc
0x18000a1eb  mov     cs:UmpoUserPowerTlsSlot, eax
0x18000a1f1  cmp     eax, 0FFFFFFFFh
0x18000a1f4  jnz     short loc_18000A203
0x18000a1f6  call    cs:__imp_GetLastError
0x18000a1fc  mov     ebx, eax
0x18000a1fe  jmp     loc_18000A434
0x18000a203  mov     [rsp+2B0h+lpdwDisposition], rsi; lpdwDisposition
0x18000a208  lea     rax, UmpoPowerSecurityDescriptorRootKey
0x18000a20f  mov     [rsp+2B0h+var_278], rax; phkResult
0x18000a214  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a21b  mov     [rsp+2B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a220  xor     r9d, r9d; lpClass
0x18000a223  mov     [rsp+2B0h+samDesired], r13d; samDesired
0x18000a228  xor     r8d, r8d; Reserved
0x18000a22b  mov     rcx, r12; hKey
0x18000a22e  mov     dword ptr [rsp+2B0h+phkResult], esi; dwOptions
0x18000a232  call    cs:__imp_RegCreateKeyExW
0x18000a238  mov     ebx, eax
0x18000a23a  test    eax, eax
0x18000a23c  jnz     loc_18000A434
0x18000a242  mov     cs:UmpoFullPowerPlanSupportDisabled, sil
0x18000a249  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000a24f  mov     dil, al
0x18000a252  test    al, al
0x18000a254  jz      loc_18000A354
0x18000a25a  mov     [rsp+2B0h+lpSecurityAttributes], rsi
0x18000a25f  lea     rax, [rsp+2B0h+SubKey]
0x18000a264  mov     [rsp+2B0h+samDesired], 208h
0x18000a26c  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Pow"...
0x18000a273  xor     r9d, r9d
0x18000a276  mov     [rsp+2B0h+phkResult], rax
0x18000a27b  xor     edx, edx
0x18000a27d  lea     rcx, aPowersettingsu; "PowerSettingsUserStatePath"
0x18000a284  call    cs:__imp_RtlGetPersistedStateLocation
0x18000a28a  mov     [rsp+2B0h+lpdwDisposition], rsi; lpdwDisposition
0x18000a28f  lea     rax, UmpoUserPowerStateSepRootKey
0x18000a296  mov     [rsp+2B0h+var_278], rax; phkResult
0x18000a29b  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18000a2a0  mov     [rsp+2B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a2a5  xor     r9d, r9d; lpClass
0x18000a2a8  mov     [rsp+2B0h+samDesired], r13d; samDesired
0x18000a2ad  xor     r8d, r8d; Reserved
0x18000a2b0  mov     rcx, r12; hKey
0x18000a2b3  mov     dword ptr [rsp+2B0h+phkResult], esi; dwOptions
0x18000a2b7  call    cs:__imp_RegCreateKeyExW
0x18000a2bd  mov     ebx, eax
0x18000a2bf  test    eax, eax
0x18000a2c1  jnz     loc_18000A434
0x18000a2c7  mov     rcx, cs:UmpoUserPowerStateSepRootKey; hKey
0x18000a2ce  lea     r8, [rsp+2B0h+hKey]; phkResult
0x18000a2d3  mov     qword ptr [rsp+2B0h+samDesired], rsi; __int64
0x18000a2d8  lea     rdx, GUID_TYPICAL_POWER_SAVINGS; Uuid2
0x18000a2df  mov     r9d, r13d; samDesired
0x18000a2e2  mov     byte ptr [rsp+2B0h+phkResult], sil; char
0x18000a2e7  call    UmpoInternalOpenGUIDSubKey
0x18000a2ec  mov     ebx, eax
0x18000a2ee  test    eax, eax
0x18000a2f0  jnz     loc_18000A434
0x18000a2f6  mov     rcx, cs:UmpoPowerControlKey; hKey
0x18000a2fd  lea     rax, [rsp+2B0h+cbData]
0x18000a302  mov     qword ptr [rsp+2B0h+samDesired], rax; lpcbData
0x18000a307  lea     rdx, aFullpowerplans; "FullPowerPlanSupportDisabled"
0x18000a30e  lea     rax, [rsp+2B0h+Data]
0x18000a313  mov     cs:UmpoStateSeparationEnabled, 1
0x18000a31a  xor     r9d, r9d; lpType
0x18000a31d  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000a322  xor     r8d, r8d; lpReserved
0x18000a325  mov     [rsp+2B0h+cbData], 4
0x18000a32d  call    cs:__imp_RegQueryValueExW
0x18000a333  mov     ebx, eax
0x18000a335  cmp     eax, 2
0x18000a338  jnz     short loc_18000A342
0x18000a33a  mov     eax, esi
0x18000a33c  mov     dword ptr [rsp+2B0h+Data], eax
0x18000a340  jmp     short loc_18000A34E
0x18000a342  test    eax, eax
0x18000a344  jnz     loc_18000A434
0x18000a34a  mov     eax, dword ptr [rsp+2B0h+Data]
0x18000a34e  mov     cs:UmpoFullPowerPlanSupportDisabled, al
0x18000a354  mov     ebx, 78h ; 'x'
0x18000a359  lea     rcx, UmpoPowerSubGroupCache; void *
0x18000a360  mov     r8d, ebx; Size
0x18000a363  xor     edx, edx; Val
0x18000a365  call    memset_0
0x18000a36a  lea     rcx, CriticalSection; lpCriticalSection
0x18000a371  call    cs:__imp_InitializeCriticalSection
0x18000a377  mov     r8d, ebx; Size
0x18000a37a  mov     cs:byte_180024DF0, 1
0x18000a381  xor     edx, edx; Val
0x18000a383  lea     rcx, UmpoPowerSettingCache; void *
0x18000a38a  call    memset_0
0x18000a38f  lea     rcx, stru_180024D08; lpCriticalSection
0x18000a396  call    cs:__imp_InitializeCriticalSection
0x18000a39c  lea     rcx, UmpoUserPowerLock; SRWLock
0x18000a3a3  mov     cs:byte_180024D30, 1
0x18000a3aa  call    cs:__imp_InitializeSRWLock
0x18000a3b0  lea     rcx, UmpoDefaultSecurityDescriptorLock; SRWLock
0x18000a3b7  call    cs:__imp_InitializeSRWLock
0x18000a3bd  cmp     cs:byte_180024FA8, 1
0x18000a3c4  jz      short loc_18000A3CB
0x18000a3c6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a3cb  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000a3d2  call    cs:__imp_EnterCriticalSection
0x18000a3d8  xor     ecx, ecx
0x18000a3da  call    UmpoCheckAndUpdateOverlayNotification
0x18000a3df  cmp     cs:byte_180024FA8, 1
0x18000a3e6  mov     ebx, eax
0x18000a3e8  jz      short loc_18000A3EF
0x18000a3ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a3ef  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000a3f6  call    cs:__imp_LeaveCriticalSection
0x18000a3fc  test    dil, dil
0x18000a3ff  jz      short loc_18000A434
0x18000a401  lea     rcx, Contract; "ext-ms-win-devmgmt-policy-l1-1-0"
0x18000a408  call    cs:__imp_IsApiSetImplemented
0x18000a40e  test    eax, eax
0x18000a410  jz      short loc_18000A434
0x18000a412  call    UmpoInternalInitializeSubscribeOnProvisioningComplete
0x18000a417  mov     ebx, eax
0x18000a419  test    eax, eax
0x18000a41b  jz      short loc_18000A424
0x18000a41d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a422  jmp     short loc_18000A434
0x18000a424  call    UmpoInternalInitializeAdvancedPowerSettings
0x18000a429  mov     ebx, eax
0x18000a42b  test    eax, eax
0x18000a42d  jz      short loc_18000A434
0x18000a42f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a434  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000a439  lea     rax, [rcx-1]
0x18000a43d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a441  ja      short loc_18000A44E
0x18000a443  call    cs:__imp_RegCloseKey
0x18000a449  mov     [rsp+2B0h+hKey], r15
0x18000a44e  test    ebx, ebx
0x18000a450  jz      loc_18000A543
0x18000a456  mov     rcx, cs:UmpoSystemPowerRootKey; hKey
0x18000a45d  lea     rax, [rcx-1]
0x18000a461  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a465  ja      short loc_18000A474
0x18000a467  call    cs:__imp_RegCloseKey
0x18000a46d  mov     cs:UmpoSystemPowerRootKey, r15
0x18000a474  mov     rcx, cs:UmpoUserPowerRootKey; hKey
0x18000a47b  lea     rax, [rcx-1]
0x18000a47f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a483  ja      short loc_18000A492
0x18000a485  call    cs:__imp_RegCloseKey
0x18000a48b  mov     cs:UmpoUserPowerRootKey, r15
0x18000a492  mov     rcx, cs:UmpoPowerSecurityDescriptorRootKey; hKey
0x18000a499  lea     rax, [rcx-1]
0x18000a49d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a4a1  ja      short loc_18000A4B0
0x18000a4a3  call    cs:__imp_RegCloseKey
0x18000a4a9  mov     cs:UmpoPowerSecurityDescriptorRootKey, r15
0x18000a4b0  mov     rcx, cs:UmpoPowerControlKey; hKey
0x18000a4b7  lea     rax, [rcx-1]
0x18000a4bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a4bf  ja      short loc_18000A4CE
0x18000a4c1  call    cs:__imp_RegCloseKey
0x18000a4c7  mov     cs:UmpoPowerControlKey, r15
0x18000a4ce  mov     rcx, cs:UmpoUserPowerStateSepRootKey; hKey
0x18000a4d5  lea     rax, [rcx-1]
0x18000a4d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a4dd  ja      short loc_18000A4EC
0x18000a4df  call    cs:__imp_RegCloseKey
0x18000a4e5  mov     cs:UmpoUserPowerStateSepRootKey, r15
0x18000a4ec  mov     ecx, cs:UmpoUserPowerTlsSlot; dwTlsIndex
0x18000a4f2  cmp     ecx, 0FFFFFFFFh
0x18000a4f5  jz      short loc_18000A507
0x18000a4f7  call    cs:__imp_TlsFree
0x18000a4fd  mov     cs:UmpoUserPowerTlsSlot, 0FFFFFFFFh
0x18000a507  cmp     cs:byte_180024DF0, sil
0x18000a50e  jz      short loc_18000A524
0x18000a510  lea     rcx, CriticalSection; lpCriticalSection
0x18000a517  call    cs:__imp_DeleteCriticalSection
0x18000a51d  mov     cs:byte_180024DF0, sil
0x18000a524  cmp     cs:byte_180024D30, sil
0x18000a52b  jz      short loc_18000A54A
0x18000a52d  lea     rcx, stru_180024D08; lpCriticalSection
0x18000a534  call    cs:__imp_DeleteCriticalSection
0x18000a53a  mov     cs:byte_180024D30, sil
0x18000a541  jmp     short loc_18000A54A
0x18000a543  mov     cs:UmpoPowerPolicyInitialized, 1
0x18000a54a  mov     eax, ebx
0x18000a54c  mov     rcx, [rbp+1B0h+var_40]
0x18000a553  xor     rcx, rsp; StackCookie
0x18000a556  call    __security_check_cookie
0x18000a55b  add     rsp, 280h
0x18000a562  pop     r15
0x18000a564  pop     r13
0x18000a566  pop     r12
0x18000a568  pop     rdi
0x18000a569  pop     rsi
0x18000a56a  pop     rbx
0x18000a56b  pop     rbp
0x18000a56c  retn
```
