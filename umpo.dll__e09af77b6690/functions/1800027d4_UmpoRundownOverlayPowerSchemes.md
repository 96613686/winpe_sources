# UmpoRundownOverlayPowerSchemes

- ea: `0x1800027d4`
- end: `0x180002bab`
- name: `UmpoRundownOverlayPowerSchemes`
- size: `983`
- prototype: `void()`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008c80`

## callees

- `0x1800027d4`
- `0x180002d8c`
- `0x180003270`
- `0x180003440`
- `0x180003560`
- `0x1800035c0`
- `0x1800061d0`
- `0x180007790`
- `0x18000f3dc`
- `0x180010070`
- `0x1800132cc`
- `0x18001337c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800029f2`
- `ntdll!EtwEventWrite` at `0x180002a2c`
- `ntdll!EtwEventWrite` at `0x180002a56`
- `ntdll!EtwEventWrite` at `0x1800029f2`
- `ntdll!EtwEventWrite` at `0x180002a2c`
- `ntdll!EtwEventWrite` at `0x180002a56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ad0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ad0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000282d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002aa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000282d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002aa8`

## pseudocode

```c
void UmpoRundownOverlayPowerSchemes()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  HKEY v2; // rsi
  int PowerModeSchema; // ebx
  int KeyValueGuid; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  HKEY v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // edi
  UUID *v11; // rax
  __int64 *v12; // rdx
  bool v13; // zf
  int v14; // eax
  unsigned int i; // ebx
  __int64 v16; // rdx
  int SuspensionPowerMode; // eax
  _BYTE v18[4]; // [rsp+40h] [rbp-49h] BYREF
  int v19; // [rsp+44h] [rbp-45h] BYREF
  int v20; // [rsp+48h] [rbp-41h] BYREF
  __int64 v21; // [rsp+50h] [rbp-39h] BYREF
  UUID Uuid; // [rsp+58h] [rbp-31h] BYREF
  UUID v23; // [rsp+68h] [rbp-21h] BYREF
  UUID v24; // [rsp+78h] [rbp-11h] BYREF
  __int64 v25[2]; // [rsp+88h] [rbp-1h] BYREF
  UUID *p_Uuid; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+A0h] [rbp+17h]
  int *v28; // [rsp+A8h] [rbp+1Fh]
  __int64 v29; // [rsp+B0h] [rbp+27h]

  v19 = 0;
  Uuid = 0;
  v20 = 0;
  v23 = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  AcquireUserPowerLockShared(v1, v0);
  v2 = UmpoUserPowerRootKey;
  PowerModeSchema = 87;
  if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v2 = 0;
    MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
    KeyValueGuid = 87;
  }
  else
  {
    KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoUserPowerRootKey, L"ActiveOverlayAcPowerScheme", &Uuid);
    if ( KeyValueGuid == 2 )
    {
      KeyValueGuid = UmpoInternalGetKeyValueGuid(v2, L"ActiveOverlayPowerScheme", &Uuid);
      if ( KeyValueGuid == 2 )
      {
        KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, L"DefaultOverlayAcPowerScheme", &Uuid);
        if ( KeyValueGuid == 2 )
        {
          KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, L"DefaultOverlayPowerScheme", &Uuid);
          if ( KeyValueGuid == 2 )
          {
            KeyValueGuid = 0;
            Uuid = GUID_POWER_MODE_NONE;
          }
        }
      }
    }
  }
  UmpoInternalCloseUserPowerKey(v2);
  if ( KeyValueGuid )
  {
    PowerModeSchema = KeyValueGuid;
    goto LABEL_18;
  }
  AcquireUserPowerLockShared(v6, v5);
  v7 = UmpoUserPowerRootKey;
  if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v7 = 0;
    MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
  }
  else
  {
    PowerModeSchema = UmpoInternalGetKeyValueGuid(UmpoUserPowerRootKey, L"ActiveOverlayDcPowerScheme", &v23);
    if ( PowerModeSchema == 2 )
    {
      PowerModeSchema = UmpoInternalGetKeyValueGuid(v7, L"ActiveOverlayPowerScheme", &v23);
      if ( PowerModeSchema == 2 )
      {
        PowerModeSchema = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, L"DefaultOverlayDcPowerScheme", &v23);
        if ( PowerModeSchema == 2 )
        {
          PowerModeSchema = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, L"DefaultOverlayPowerScheme", &v23);
          if ( PowerModeSchema == 2 )
          {
            PowerModeSchema = 0;
            v23 = GUID_POWER_MODE_NONE;
          }
        }
      }
    }
  }
  UmpoInternalCloseUserPowerKey(v7);
  if ( !PowerModeSchema )
  {
    v18[0] = 0;
    if ( (_DWORD)UmpoOverlaySchemeSuspendMask )
    {
      PowerModeSchema = UmpoInternalGetPowerModeSchema(v18, v8, v9);
      if ( PowerModeSchema )
        goto LABEL_18;
      LOBYTE(v16) = v18[0];
      SuspensionPowerMode = UmpoInternalGetSuspensionPowerMode((int)UmpoOverlaySchemeSuspendMask, v16, &v24);
    }
    else
    {
      LOBYTE(v8) = UmpoOnAcPower;
      SuspensionPowerMode = UmpoGetActualOverlayScheme(&v24, v8);
    }
    PowerModeSchema = SuspensionPowerMode;
  }
LABEL_18:
  v10 = (unsigned int)UmpoOverlaySchemeSuspendMask;
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
  if ( !PowerModeSchema )
  {
    p_Uuid = &Uuid;
    v19 = 1;
    v28 = &v19;
    v27 = 16;
    v29 = 4;
    EtwEventWrite(UmpoProviderHandle, "2", 2, &p_Uuid);
    p_Uuid = &v23;
    v19 = 0;
    v28 = &v19;
    v27 = 16;
    v29 = 4;
    EtwEventWrite(UmpoProviderHandle, "2", 2, &p_Uuid);
    v11 = &v24;
    v27 = 16;
    v12 = UMPO_EVT_RUNDOWN_EFFECTIVE_OVERLAY_POWER_SCHEME;
    while ( 1 )
    {
      p_Uuid = v11;
      EtwEventWrite(UmpoProviderHandle, v12, 1, &p_Uuid);
      v13 = !_BitScanForward((unsigned int *)&v14, v10);
      v20 = v14;
      if ( v13 )
        break;
      if ( v14 >= 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v27 = 4;
      v10 &= v10 - 1;
      v12 = UMPO_EVT_RUNDOWN_OVERLAY_SUSPEND_REASON;
      v11 = (UUID *)&v20;
    }
    for ( i = 0; ; ++i )
    {
      LODWORD(v21) = 16;
      if ( (unsigned int)UmpoEnumerate(0, 0, 26, i, (UUID *)v25, &v21, 1) )
        break;
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      EnterCriticalSection(&UmpoSchemeLock);
      UmpoEnumeratePowerSettings(
        0,
        (__int64 (__fastcall *)(UUID *, UUID *, __int64))UmpoRundownOverlaySettingCallback,
        (__int64)v25);
      if ( byte_180024FA8 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      LeaveCriticalSection(&UmpoSchemeLock);
    }
  }
}

```

## disassembly

```asm
0x1800027d4  push    rbp
0x1800027d6  push    rbx
0x1800027d7  push    rsi
0x1800027d8  push    rdi
0x1800027d9  push    r15
0x1800027db  lea     rbp, [rsp-37h]
0x1800027e0  sub     rsp, 0C0h
0x1800027e7  mov     rax, cs:__security_cookie
0x1800027ee  xor     rax, rsp
0x1800027f1  mov     [rbp+57h+var_28], rax
0x1800027f5  cmp     cs:byte_180024FA8, 1
0x1800027fc  xorps   xmm0, xmm0
0x1800027ff  xorps   xmm1, xmm1
0x180002802  mov     [rbp+57h+var_9C], 0
0x180002809  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18000280d  mov     [rbp+57h+var_98], 0
0x180002814  movups  xmmword ptr [rbp+57h+var_78.Data1], xmm1
0x180002818  movups  xmmword ptr [rbp+57h+var_68.Data1], xmm0
0x18000281c  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x180002820  jnz     loc_180002B0C
0x180002826  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x18000282d  call    cs:__imp_EnterCriticalSection
0x180002833  call    AcquireUserPowerLockShared
0x180002838  mov     rsi, cs:UmpoUserPowerRootKey
0x18000283f  mov     ebx, 57h ; 'W'
0x180002844  lea     rax, [rsi-1]
0x180002848  lea     r15d, [rbx-55h]
0x18000284c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002850  ja      loc_180002B16
0x180002856  lea     r8, [rbp+57h+Uuid]; Uuid
0x18000285a  mov     rcx, rsi; hKey
0x18000285d  lea     rdx, aActiveoverlaya; "ActiveOverlayAcPowerScheme"
0x180002864  call    UmpoInternalGetKeyValueGuid
0x180002869  mov     edi, eax
0x18000286b  cmp     eax, r15d
0x18000286e  jnz     short loc_1800028D4
0x180002870  lea     r8, [rbp+57h+Uuid]; Uuid
0x180002874  mov     rcx, rsi; hKey
0x180002877  lea     rdx, aActiveoverlayp; "ActiveOverlayPowerScheme"
0x18000287e  call    UmpoInternalGetKeyValueGuid
0x180002883  mov     edi, eax
0x180002885  cmp     eax, r15d
0x180002888  jnz     short loc_1800028D4
0x18000288a  mov     rcx, cs:UmpoPowerControlKey; hKey
0x180002891  lea     r8, [rbp+57h+Uuid]; Uuid
0x180002895  lea     rdx, aDefaultoverlay; "DefaultOverlayAcPowerScheme"
0x18000289c  call    UmpoInternalGetKeyValueGuid
0x1800028a1  mov     edi, eax
0x1800028a3  cmp     eax, r15d
0x1800028a6  jnz     short loc_1800028D4
0x1800028a8  mov     rcx, cs:UmpoPowerControlKey; hKey
0x1800028af  lea     r8, [rbp+57h+Uuid]; Uuid
0x1800028b3  lea     rdx, aDefaultoverlay_0; "DefaultOverlayPowerScheme"
0x1800028ba  call    UmpoInternalGetKeyValueGuid
0x1800028bf  mov     edi, eax
0x1800028c1  cmp     eax, r15d
0x1800028c4  jnz     short loc_1800028D4
0x1800028c6  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_NONE.Data1
0x1800028cd  xor     edi, edi
0x1800028cf  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800028d4  mov     rcx, rsi
0x1800028d7  call    UmpoInternalCloseUserPowerKey
0x1800028dc  test    edi, edi
0x1800028de  jz      short loc_1800028E7
0x1800028e0  mov     ebx, edi
0x1800028e2  jmp     loc_18000298F
0x1800028e7  call    AcquireUserPowerLockShared
0x1800028ec  mov     rdi, cs:UmpoUserPowerRootKey
0x1800028f3  lea     rax, [rdi-1]
0x1800028f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800028fb  ja      loc_180002B29
0x180002901  lea     r8, [rbp+57h+var_78]; Uuid
0x180002905  mov     rcx, rdi; hKey
0x180002908  lea     rdx, aActiveoverlayd; "ActiveOverlayDcPowerScheme"
0x18000290f  call    UmpoInternalGetKeyValueGuid
0x180002914  mov     ebx, eax
0x180002916  cmp     eax, r15d
0x180002919  jnz     short loc_18000297F
0x18000291b  lea     r8, [rbp+57h+var_78]; Uuid
0x18000291f  mov     rcx, rdi; hKey
0x180002922  lea     rdx, aActiveoverlayp; "ActiveOverlayPowerScheme"
0x180002929  call    UmpoInternalGetKeyValueGuid
0x18000292e  mov     ebx, eax
0x180002930  cmp     eax, r15d
0x180002933  jnz     short loc_18000297F
0x180002935  mov     rcx, cs:UmpoPowerControlKey; hKey
0x18000293c  lea     r8, [rbp+57h+var_78]; Uuid
0x180002940  lea     rdx, aDefaultoverlay_1; "DefaultOverlayDcPowerScheme"
0x180002947  call    UmpoInternalGetKeyValueGuid
0x18000294c  mov     ebx, eax
0x18000294e  cmp     eax, r15d
0x180002951  jnz     short loc_18000297F
0x180002953  mov     rcx, cs:UmpoPowerControlKey; hKey
0x18000295a  lea     r8, [rbp+57h+var_78]; Uuid
0x18000295e  lea     rdx, aDefaultoverlay_0; "DefaultOverlayPowerScheme"
0x180002965  call    UmpoInternalGetKeyValueGuid
0x18000296a  mov     ebx, eax
0x18000296c  cmp     eax, r15d
0x18000296f  jnz     short loc_18000297F
0x180002971  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_NONE.Data1
0x180002978  xor     ebx, ebx
0x18000297a  movdqu  xmmword ptr [rbp+57h+var_78.Data1], xmm0
0x18000297f  mov     rcx, rdi
0x180002982  call    UmpoInternalCloseUserPowerKey
0x180002987  test    ebx, ebx
0x180002989  jz      loc_180002B3A
0x18000298f  cmp     cs:byte_180024FA8, 1
0x180002996  mov     edi, cs:UmpoOverlaySchemeSuspendMask
0x18000299c  jnz     loc_180002AFB
0x1800029a2  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x1800029a9  call    cs:__imp_LeaveCriticalSection
0x1800029af  test    ebx, ebx
0x1800029b1  jnz     loc_180002ADA
0x1800029b7  mov     rcx, cs:UmpoProviderHandle
0x1800029be  lea     rax, [rbp+57h+Uuid]
0x1800029c2  mov     [rbp+57h+var_48], rax
0x1800029c6  lea     esi, [rbx+10h]
0x1800029c9  lea     rax, [rbp+57h+var_9C]
0x1800029cd  mov     [rbp+57h+var_9C], 1
0x1800029d4  lea     r9, [rbp+57h+var_48]
0x1800029d8  mov     [rbp+57h+var_38], rax
0x1800029dc  mov     r8d, r15d
0x1800029df  mov     [rbp+57h+var_40], rsi
0x1800029e3  lea     rdx, UMPO_EVT_RUNDOWN_ACTUAL_OVERLAY_POWER_SCHEME; "2"
0x1800029ea  mov     [rbp+57h+var_30], 4
0x1800029f2  call    cs:__imp_EtwEventWrite
0x1800029f8  mov     rcx, cs:UmpoProviderHandle
0x1800029ff  lea     rax, [rbp+57h+var_78]
0x180002a03  mov     [rbp+57h+var_48], rax
0x180002a07  lea     r9, [rbp+57h+var_48]
0x180002a0b  lea     rax, [rbp+57h+var_9C]
0x180002a0f  mov     [rbp+57h+var_9C], ebx
0x180002a12  mov     r8d, r15d
0x180002a15  mov     [rbp+57h+var_38], rax
0x180002a19  lea     rdx, UMPO_EVT_RUNDOWN_ACTUAL_OVERLAY_POWER_SCHEME; "2"
0x180002a20  mov     [rbp+57h+var_40], rsi
0x180002a24  mov     [rbp+57h+var_30], 4
0x180002a2c  call    cs:__imp_EtwEventWrite
0x180002a32  lea     rax, [rbp+57h+var_68]
0x180002a36  mov     [rbp+57h+var_40], rsi
0x180002a3a  lea     rdx, UMPO_EVT_RUNDOWN_EFFECTIVE_OVERLAY_POWER_SCHEME
0x180002a41  mov     rcx, cs:UmpoProviderHandle
0x180002a48  lea     r9, [rbp+57h+var_48]
0x180002a4c  mov     r8d, 1
0x180002a52  mov     [rbp+57h+var_48], rax
0x180002a56  call    cs:__imp_EtwEventWrite
0x180002a5c  bsf     eax, edi
0x180002a5f  mov     [rbp+57h+var_98], eax
0x180002a62  jnz     loc_180002B84
0x180002a68  xor     ebx, ebx
0x180002a6a  xor     edx, edx; UUID *
0x180002a6c  mov     [rsp+0E0h+var_B0], 1; char
0x180002a71  lea     rax, [rbp+57h+var_90]
0x180002a75  mov     dword ptr [rbp+57h+var_90], esi
0x180002a78  mov     [rsp+0E0h+var_B8], rax; __int64
0x180002a7d  mov     r9d, ebx
0x180002a80  lea     rax, [rbp+57h+var_58]
0x180002a84  xor     ecx, ecx; Uuid2
0x180002a86  lea     r8d, [rdx+1Ah]
0x180002a8a  mov     [rsp+0E0h+var_C0], rax; __int64
0x180002a8f  call    UmpoEnumerate
0x180002a94  test    eax, eax
0x180002a96  jnz     short loc_180002ADA
0x180002a98  cmp     cs:byte_180024FA8, 1
0x180002a9f  jnz     short loc_180002B05
0x180002aa1  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180002aa8  call    cs:__imp_EnterCriticalSection
0x180002aae  lea     r8, [rbp+57h+var_58]
0x180002ab2  xor     ecx, ecx
0x180002ab4  lea     rdx, UmpoRundownOverlaySettingCallback
0x180002abb  call    UmpoEnumeratePowerSettings
0x180002ac0  cmp     cs:byte_180024FA8, 1
0x180002ac7  jnz     short loc_180002AF4
0x180002ac9  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180002ad0  call    cs:__imp_LeaveCriticalSection
0x180002ad6  inc     ebx
0x180002ad8  jmp     short loc_180002A6A
0x180002ada  mov     rcx, [rbp+57h+var_28]
0x180002ade  xor     rcx, rsp; StackCookie
0x180002ae1  call    __security_check_cookie
0x180002ae6  add     rsp, 0C0h
0x180002aed  pop     r15
0x180002aef  pop     rdi
0x180002af0  pop     rsi
0x180002af1  pop     rbx
0x180002af2  pop     rbp
0x180002af3  retn
0x180002af4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002af9  jmp     short loc_180002AC9
0x180002afb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b00  jmp     loc_1800029A2
0x180002b05  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b0a  jmp     short loc_180002AA1
0x180002b0c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b11  jmp     loc_180002826
0x180002b16  xor     esi, esi
0x180002b18  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b1d  call    ReleaseUserPowerLock
0x180002b22  mov     edi, ebx
0x180002b24  jmp     loc_1800028D4
0x180002b29  xor     edi, edi
0x180002b2b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b30  call    ReleaseUserPowerLock
0x180002b35  jmp     loc_18000297F
0x180002b3a  cmp     cs:UmpoOverlaySchemeSuspendMask, 0
0x180002b41  mov     [rbp+57h+var_A0], 0
0x180002b45  jz      short loc_180002B6E
0x180002b47  lea     rcx, [rbp+57h+var_A0]
0x180002b4b  call    UmpoInternalGetPowerModeSchema
0x180002b50  mov     ebx, eax
0x180002b52  test    eax, eax
0x180002b54  jnz     loc_18000298F
0x180002b5a  mov     dl, [rbp+57h+var_A0]
0x180002b5d  lea     r8, [rbp+57h+var_68]
0x180002b61  mov     ecx, cs:UmpoOverlaySchemeSuspendMask
0x180002b67  call    UmpoInternalGetSuspensionPowerMode
0x180002b6c  jmp     short loc_180002B7D
0x180002b6e  mov     dl, cs:UmpoOnAcPower
0x180002b74  lea     rcx, [rbp+57h+var_68]; Uuid
0x180002b78  call    UmpoGetActualOverlayScheme
0x180002b7d  mov     ebx, eax
0x180002b7f  jmp     loc_18000298F
0x180002b84  cmp     eax, r15d
0x180002b87  jl      short loc_180002B8E
0x180002b89  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002b8e  lea     eax, [rdi-1]
0x180002b91  mov     [rbp+57h+var_40], 4
0x180002b99  and     edi, eax
0x180002b9b  lea     rdx, UMPO_EVT_RUNDOWN_OVERLAY_SUSPEND_REASON
0x180002ba2  lea     rax, [rbp+57h+var_98]
0x180002ba6  jmp     loc_180002A41
```
