# DriverEntry

- ea: `0x140036078`
- end: `0x1400363cd`
- name: `DriverEntry`
- size: `853`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036010`

## callees

- `0x14000d7c8`
- `0x14000e0d0`
- `0x140010b24`
- `0x1400134dc`
- `0x140013b84`
- `0x140016198`
- `0x1400186e4`
- `0x140018ad0`
- `0x140018e4c`
- `0x14001f320`
- `0x14001f980`
- `0x14002f780`
- `0x14002fb8c`
- `0x14002fe80`
- `0x14002feb0`
- `0x140036078`
- `0x1400363d4`
- `0x140036580`
- `0x140036af8`
- `0x140036cac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400360d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400360d6`
- `ntoskrnl!RtlGetVersion` at `0x140036160`
- `ntoskrnl!RtlGetVersion` at `0x140036160`
- `ntoskrnl!IoCreateDevice` at `0x14003610b`
- `ntoskrnl!IoCreateDevice` at `0x14003610b`
- `NETIO!NmrRegisterProvider` at `0x1400362f7`
- `NETIO!NmrRegisterProvider` at `0x1400362f7`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v3; // ebx
  NTSTATUS PersistentSettings; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-148h] BYREF
  _BYTE VersionInformation[284]; // [rsp+50h] [rbp-138h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  WinNatDriverObject = DriverObject;
  DestinationString = 0;
  wil_InitializeFeatureStaging();
  FastWppInit();
  RtlInitUnicodeString(&DestinationString, L"\\Device\\WinNat");
  v3 = IoCreateDevice(DriverObject, 0, &DestinationString, 0x22u, 0x100u, 0, &deviceObject);
  if ( v3 >= 0 )
  {
    McGenEventRegister_EtwRegister();
    byte_140027B70 |= 0x20u;
    InitializeTelemetryAssertsKMByDriverObject(DriverObject);
    EnableXlat = 0;
    memset(&VersionInformation[4], 0, 0x118u);
    *(_DWORD *)VersionInformation = 284;
    if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && VersionInformation[282] == 1 )
      EnableXlat = 1;
    PersistentSettings = WinNatSetDeviceDacl(deviceObject);
    v3 = PersistentSettings;
    if ( PersistentSettings >= 0 )
    {
      PersistentSettings = WinNatInitializeGlobals(DriverObject);
      v3 = PersistentSettings;
      if ( PersistentSettings >= 0 )
      {
        LOBYTE(v8) = 1;
        qword_140027AE0 = (PVOID)WinNatLibInitializeState(v8, (unsigned int)dword_140027B60, qword_140027B68);
        if ( !qword_140027AE0 )
        {
          v3 = -1073741670;
          if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
            McTemplateK0qzqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v9,
              v10,
              2003,
              (__int64)L"DriverEntry",
              0,
              154);
          goto LABEL_45;
        }
        PersistentSettings = WinNatInitializeWFP();
        v3 = PersistentSettings;
        if ( PersistentSettings >= 0 )
        {
          PersistentSettings = SlbNatInitialize();
          v3 = PersistentSettings;
          if ( PersistentSettings >= 0 )
          {
            if ( EnableXlat )
            {
              v3 = IPxlatInitialize();
              if ( v3 < 0 )
                goto LABEL_45;
            }
            PersistentSettings = WinNatRegisterChangeNotification();
            v3 = PersistentSettings;
            if ( PersistentSettings >= 0 )
            {
              PersistentSettings = NmrRegisterProvider(&WinNatProviderCharacteristics, 0, &WinNatNsiRegistrationHandle);
              v3 = PersistentSettings;
              if ( PersistentSettings >= 0 )
              {
                PersistentSettings = WinNatInitializePcwCounterSets();
                v3 = PersistentSettings;
                if ( PersistentSettings >= 0 )
                {
                  PersistentSettings = SlbNatLoadPersistentSettings();
                  v3 = PersistentSettings;
                  if ( PersistentSettings >= 0 )
                  {
                    WinNatLoadPersistentSettings();
                    DriverObject->DriverUnload = (PDRIVER_UNLOAD)WinNatUnload;
                    return v3;
                  }
                  if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
                    goto LABEL_45;
                  v7 = 2009;
                }
                else
                {
                  if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
                    goto LABEL_45;
                  v7 = 2008;
                }
              }
              else
              {
                if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
                  goto LABEL_45;
                v7 = 2007;
              }
            }
            else
            {
              if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
                goto LABEL_45;
              v7 = 2006;
            }
          }
          else
          {
            if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
              goto LABEL_45;
            v7 = 2005;
          }
        }
        else
        {
          if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
            goto LABEL_45;
          v7 = 2004;
        }
      }
      else
      {
        if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
          goto LABEL_45;
        v7 = 2002;
      }
    }
    else
    {
      if ( dword_140027104 != 1 || (byte_140027BED & 0x10) == 0 )
        goto LABEL_45;
      v7 = 2001;
    }
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v5,
      v6,
      v7,
      (__int64)L"DriverEntry",
      0,
      PersistentSettings);
LABEL_45:
    WinNatUnload(DriverObject);
    return v3;
  }
  wil_UninitializeFeatureStaging();
  return v3;
}

```

## disassembly

```asm
0x140036078  mov     [rsp+arg_8], rbx
0x14003607d  mov     [rsp+arg_10], rsi
0x140036082  push    rdi
0x140036083  sub     rsp, 180h
0x14003608a  mov     rax, cs:__security_cookie
0x140036091  xor     rax, rsp
0x140036094  mov     [rsp+188h+var_18], rax
0x14003609c  mov     rdi, rcx
0x14003609f  xor     edx, edx; Val
0x1400360a1  lea     rcx, [rsp+188h+VersionInformation]; void *
0x1400360a6  mov     r8d, 11Ch; Size
0x1400360ac  call    memset
0x1400360b1  xorps   xmm0, xmm0
0x1400360b4  mov     cs:WinNatDriverObject, rdi
0x1400360bb  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x1400360c0  call    wil_InitializeFeatureStaging
0x1400360c5  call    FastWppInit
0x1400360ca  lea     rdx, aDeviceWinnat; "\\Device\\WinNat"
0x1400360d1  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x1400360d6  call    cs:__imp_RtlInitUnicodeString
0x1400360dd  nop     dword ptr [rax+rax+00h]
0x1400360e2  xor     esi, esi
0x1400360e4  lea     rax, deviceObject
0x1400360eb  mov     [rsp+188h+DeviceObject], rax; DeviceObject
0x1400360f0  lea     r8, [rsp+188h+DestinationString]; DeviceName
0x1400360f5  mov     [rsp+188h+Exclusive], sil; Exclusive
0x1400360fa  xor     edx, edx; DeviceExtensionSize
0x1400360fc  mov     rcx, rdi; DriverObject
0x1400360ff  mov     [rsp+188h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140036107  lea     r9d, [rsi+22h]; DeviceType
0x14003610b  call    cs:__imp_IoCreateDevice
0x140036112  nop     dword ptr [rax+rax+00h]
0x140036117  mov     ebx, eax
0x140036119  test    eax, eax
0x14003611b  jns     short loc_140036127
0x14003611d  call    wil_UninitializeFeatureStaging
0x140036122  jmp     loc_1400363A5
0x140036127  call    McGenEventRegister_EtwRegister
0x14003612c  or      cs:byte_140027B70, 20h
0x140036133  mov     rcx, rdi
0x140036136  call    InitializeTelemetryAssertsKMByDriverObject
0x14003613b  xor     edx, edx; Val
0x14003613d  mov     cs:EnableXlat, esi
0x140036143  mov     r8d, 118h; Size
0x140036149  lea     rcx, [rsp+188h+VersionInformation.dwMajorVersion]; void *
0x14003614e  call    memset
0x140036153  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x140036158  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140036160  call    cs:__imp_RtlGetVersion
0x140036167  nop     dword ptr [rax+rax+00h]
0x14003616c  test    eax, eax
0x14003616e  js      short loc_140036184
0x140036170  cmp     [rsp+188h+var_1E], 1
0x140036178  jnz     short loc_140036184
0x14003617a  mov     cs:EnableXlat, 1
0x140036184  mov     rcx, cs:deviceObject
0x14003618b  call    WinNatSetDeviceDacl
0x140036190  mov     ebx, eax
0x140036192  test    eax, eax
0x140036194  jns     short loc_1400361BB
0x140036196  cmp     cs:dword_140027104, 1
0x14003619d  jnz     loc_14003638B
0x1400361a3  test    cs:byte_140027BED, 10h
0x1400361aa  jz      loc_14003638B
0x1400361b0  mov     r9d, 7D1h
0x1400361b6  jmp     loc_14003636B
0x1400361bb  mov     rcx, rdi
0x1400361be  call    WinNatInitializeGlobals
0x1400361c3  mov     ebx, eax
0x1400361c5  test    eax, eax
0x1400361c7  jns     short loc_1400361EE
0x1400361c9  cmp     cs:dword_140027104, 1
0x1400361d0  jnz     loc_14003638B
0x1400361d6  test    cs:byte_140027BED, 10h
0x1400361dd  jz      loc_14003638B
0x1400361e3  mov     r9d, 7D2h
0x1400361e9  jmp     loc_14003636B
0x1400361ee  mov     r8, cs:qword_140027B68
0x1400361f5  mov     cl, 1
0x1400361f7  mov     edx, cs:dword_140027B60
0x1400361fd  call    WinNatLibInitializeState
0x140036202  mov     cs:qword_140027AE0, rax
0x140036209  test    rax, rax
0x14003620c  jnz     short loc_140036240
0x14003620e  cmp     cs:dword_140027104, 1
0x140036215  mov     ebx, 0C000009Ah
0x14003621a  jnz     loc_14003638B
0x140036220  test    cs:byte_140027BED, 10h
0x140036227  jz      loc_14003638B
0x14003622d  mov     dword ptr [rsp+188h+DeviceObject], 0C000009Ah
0x140036235  mov     r9d, 7D3h
0x14003623b  jmp     loc_14003636F
0x140036240  call    WinNatInitializeWFP
0x140036245  mov     ebx, eax
0x140036247  test    eax, eax
0x140036249  jns     short loc_140036270
0x14003624b  cmp     cs:dword_140027104, 1
0x140036252  jnz     loc_14003638B
0x140036258  test    cs:byte_140027BED, 10h
0x14003625f  jz      loc_14003638B
0x140036265  mov     r9d, 7D4h
0x14003626b  jmp     loc_14003636B
0x140036270  call    SlbNatInitialize
0x140036275  mov     ebx, eax
0x140036277  test    eax, eax
0x140036279  jns     short loc_1400362A0
0x14003627b  cmp     cs:dword_140027104, 1
0x140036282  jnz     loc_14003638B
0x140036288  test    cs:byte_140027BED, 10h
0x14003628f  jz      loc_14003638B
0x140036295  mov     r9d, 7D5h
0x14003629b  jmp     loc_14003636B
0x1400362a0  cmp     cs:EnableXlat, esi
0x1400362a6  jz      short loc_1400362B7
0x1400362a8  call    IPxlatInitialize
0x1400362ad  mov     ebx, eax
0x1400362af  test    eax, eax
0x1400362b1  js      loc_14003638B
0x1400362b7  call    WinNatRegisterChangeNotification
0x1400362bc  mov     ebx, eax
0x1400362be  test    eax, eax
0x1400362c0  jns     short loc_1400362E7
0x1400362c2  cmp     cs:dword_140027104, 1
0x1400362c9  jnz     loc_14003638B
0x1400362cf  test    cs:byte_140027BED, 10h
0x1400362d6  jz      loc_14003638B
0x1400362dc  mov     r9d, 7D6h
0x1400362e2  jmp     loc_14003636B
0x1400362e7  lea     r8, WinNatNsiRegistrationHandle; NmrProviderHandle
0x1400362ee  xor     edx, edx; ProviderContext
0x1400362f0  lea     rcx, WinNatProviderCharacteristics; ProviderCharacteristics
0x1400362f7  call    cs:__imp_NmrRegisterProvider
0x1400362fe  nop     dword ptr [rax+rax+00h]
0x140036303  mov     ebx, eax
0x140036305  test    eax, eax
0x140036307  jns     short loc_140036323
0x140036309  cmp     cs:dword_140027104, 1
0x140036310  jnz     short loc_14003638B
0x140036312  test    cs:byte_140027BED, 10h
0x140036319  jz      short loc_14003638B
0x14003631b  mov     r9d, 7D7h
0x140036321  jmp     short loc_14003636B
0x140036323  call    WinNatInitializePcwCounterSets
0x140036328  mov     ebx, eax
0x14003632a  test    eax, eax
0x14003632c  jns     short loc_140036348
0x14003632e  cmp     cs:dword_140027104, 1
0x140036335  jnz     short loc_14003638B
0x140036337  test    cs:byte_140027BED, 10h
0x14003633e  jz      short loc_14003638B
0x140036340  mov     r9d, 7D8h
0x140036346  jmp     short loc_14003636B
0x140036348  call    SlbNatLoadPersistentSettings
0x14003634d  mov     ebx, eax
0x14003634f  test    eax, eax
0x140036351  jns     short loc_140036395
0x140036353  cmp     cs:dword_140027104, 1
0x14003635a  jnz     short loc_14003638B
0x14003635c  test    cs:byte_140027BED, 10h
0x140036363  jz      short loc_14003638B
0x140036365  mov     r9d, 7D9h
0x14003636b  mov     dword ptr [rsp+188h+DeviceObject], eax
0x14003636f  lea     rax, aDriverentry; "DriverEntry"
0x140036376  mov     dword ptr [rsp+188h+Exclusive], esi
0x14003637a  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140036381  mov     qword ptr [rsp+188h+DeviceCharacteristics], rax
0x140036386  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003638b  mov     rcx, rdi
0x14003638e  call    WinNatUnload
0x140036393  jmp     short loc_1400363A5
0x140036395  call    WinNatLoadPersistentSettings
0x14003639a  lea     rax, WinNatUnload
0x1400363a1  mov     [rdi+68h], rax
0x1400363a5  mov     eax, ebx
0x1400363a7  mov     rcx, [rsp+188h+var_18]
0x1400363af  xor     rcx, rsp; StackCookie
0x1400363b2  call    __security_check_cookie
0x1400363b7  lea     r11, [rsp+188h+var_8]
0x1400363bf  mov     rbx, [r11+18h]
0x1400363c3  mov     rsi, [r11+20h]
0x1400363c7  mov     rsp, r11
0x1400363ca  pop     rdi
0x1400363cb  retn
```
