# DriverEntry

- ea: `0x140035078`
- end: `0x1400353cd`
- name: `DriverEntry`
- size: `853`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140035010`

## callees

- `0x14000d7f8`
- `0x14000e100`
- `0x140010ac4`
- `0x140012b9c`
- `0x140013244`
- `0x140015818`
- `0x140018204`
- `0x1400185f0`
- `0x14001896c`
- `0x14001ede0`
- `0x14001f440`
- `0x14002e780`
- `0x14002eb8c`
- `0x14002ee80`
- `0x14002eeb0`
- `0x140035078`
- `0x1400353d4`
- `0x140035580`
- `0x140035af8`
- `0x140035cac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400350d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400350d6`
- `ntoskrnl!RtlGetVersion` at `0x140035160`
- `ntoskrnl!RtlGetVersion` at `0x140035160`
- `ntoskrnl!IoCreateDevice` at `0x14003510b`
- `ntoskrnl!IoCreateDevice` at `0x14003510b`
- `NETIO!NmrRegisterProvider` at `0x1400352f7`
- `NETIO!NmrRegisterProvider` at `0x1400352f7`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v3; // ebx
  int PersistentSettings; // eax
  __int64 v5; // rdx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rcx
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
    byte_140026B70 |= 0x20u;
    InitializeTelemetryAssertsKMByDriverObject(DriverObject);
    EnableXlat = 0;
    memset(&VersionInformation[4], 0, 0x118u);
    *(_DWORD *)VersionInformation = 284;
    if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0 && VersionInformation[282] == 1 )
      EnableXlat = 1;
    PersistentSettings = WinNatSetDeviceDacl((__int64)deviceObject);
    v3 = PersistentSettings;
    if ( PersistentSettings >= 0 )
    {
      PersistentSettings = WinNatInitializeGlobals(DriverObject);
      v3 = PersistentSettings;
      if ( PersistentSettings >= 0 )
      {
        LOBYTE(v8) = 1;
        qword_140026AE0 = (PVOID)WinNatLibInitializeState(v8, (unsigned int)dword_140026B60, qword_140026B68);
        if ( !qword_140026AE0 )
        {
          v3 = -1073741670;
          if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
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
              v3 = IPxlatInitialize(v11, v5);
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
                  if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
                    goto LABEL_45;
                  v7 = 2009;
                }
                else
                {
                  if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
                    goto LABEL_45;
                  v7 = 2008;
                }
              }
              else
              {
                if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
                  goto LABEL_45;
                v7 = 2007;
              }
            }
            else
            {
              if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
                goto LABEL_45;
              v7 = 2006;
            }
          }
          else
          {
            if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
              goto LABEL_45;
            v7 = 2005;
          }
        }
        else
        {
          if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
            goto LABEL_45;
          v7 = 2004;
        }
      }
      else
      {
        if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
          goto LABEL_45;
        v7 = 2002;
      }
    }
    else
    {
      if ( dword_140026104 != 1 || (byte_140026BED & 0x10) == 0 )
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
0x140035078  mov     [rsp+arg_8], rbx
0x14003507d  mov     [rsp+arg_10], rsi
0x140035082  push    rdi
0x140035083  sub     rsp, 180h
0x14003508a  mov     rax, cs:__security_cookie
0x140035091  xor     rax, rsp
0x140035094  mov     [rsp+188h+var_18], rax
0x14003509c  mov     rdi, rcx
0x14003509f  xor     edx, edx; Val
0x1400350a1  lea     rcx, [rsp+188h+VersionInformation]; void *
0x1400350a6  mov     r8d, 11Ch; Size
0x1400350ac  call    memset
0x1400350b1  xorps   xmm0, xmm0
0x1400350b4  mov     cs:WinNatDriverObject, rdi
0x1400350bb  movups  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x1400350c0  call    wil_InitializeFeatureStaging
0x1400350c5  call    FastWppInit
0x1400350ca  lea     rdx, aDeviceWinnat; "\\Device\\WinNat"
0x1400350d1  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x1400350d6  call    cs:__imp_RtlInitUnicodeString
0x1400350dd  nop     dword ptr [rax+rax+00h]
0x1400350e2  xor     esi, esi
0x1400350e4  lea     rax, deviceObject
0x1400350eb  mov     [rsp+188h+DeviceObject], rax; DeviceObject
0x1400350f0  lea     r8, [rsp+188h+DestinationString]; DeviceName
0x1400350f5  mov     [rsp+188h+Exclusive], sil; Exclusive
0x1400350fa  xor     edx, edx; DeviceExtensionSize
0x1400350fc  mov     rcx, rdi; DriverObject
0x1400350ff  mov     [rsp+188h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140035107  lea     r9d, [rsi+22h]; DeviceType
0x14003510b  call    cs:__imp_IoCreateDevice
0x140035112  nop     dword ptr [rax+rax+00h]
0x140035117  mov     ebx, eax
0x140035119  test    eax, eax
0x14003511b  jns     short loc_140035127
0x14003511d  call    wil_UninitializeFeatureStaging
0x140035122  jmp     loc_1400353A5
0x140035127  call    McGenEventRegister_EtwRegister
0x14003512c  or      cs:byte_140026B70, 20h
0x140035133  mov     rcx, rdi
0x140035136  call    InitializeTelemetryAssertsKMByDriverObject
0x14003513b  xor     edx, edx; Val
0x14003513d  mov     cs:EnableXlat, esi
0x140035143  mov     r8d, 118h; Size
0x140035149  lea     rcx, [rsp+188h+VersionInformation.dwMajorVersion]; void *
0x14003514e  call    memset
0x140035153  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x140035158  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140035160  call    cs:__imp_RtlGetVersion
0x140035167  nop     dword ptr [rax+rax+00h]
0x14003516c  test    eax, eax
0x14003516e  js      short loc_140035184
0x140035170  cmp     [rsp+188h+var_1E], 1
0x140035178  jnz     short loc_140035184
0x14003517a  mov     cs:EnableXlat, 1
0x140035184  mov     rcx, cs:deviceObject
0x14003518b  call    WinNatSetDeviceDacl
0x140035190  mov     ebx, eax
0x140035192  test    eax, eax
0x140035194  jns     short loc_1400351BB
0x140035196  cmp     cs:dword_140026104, 1
0x14003519d  jnz     loc_14003538B
0x1400351a3  test    cs:byte_140026BED, 10h
0x1400351aa  jz      loc_14003538B
0x1400351b0  mov     r9d, 7D1h
0x1400351b6  jmp     loc_14003536B
0x1400351bb  mov     rcx, rdi
0x1400351be  call    WinNatInitializeGlobals
0x1400351c3  mov     ebx, eax
0x1400351c5  test    eax, eax
0x1400351c7  jns     short loc_1400351EE
0x1400351c9  cmp     cs:dword_140026104, 1
0x1400351d0  jnz     loc_14003538B
0x1400351d6  test    cs:byte_140026BED, 10h
0x1400351dd  jz      loc_14003538B
0x1400351e3  mov     r9d, 7D2h
0x1400351e9  jmp     loc_14003536B
0x1400351ee  mov     r8, cs:qword_140026B68
0x1400351f5  mov     cl, 1
0x1400351f7  mov     edx, cs:dword_140026B60
0x1400351fd  call    WinNatLibInitializeState
0x140035202  mov     cs:qword_140026AE0, rax
0x140035209  test    rax, rax
0x14003520c  jnz     short loc_140035240
0x14003520e  cmp     cs:dword_140026104, 1
0x140035215  mov     ebx, 0C000009Ah
0x14003521a  jnz     loc_14003538B
0x140035220  test    cs:byte_140026BED, 10h
0x140035227  jz      loc_14003538B
0x14003522d  mov     dword ptr [rsp+188h+DeviceObject], 0C000009Ah
0x140035235  mov     r9d, 7D3h
0x14003523b  jmp     loc_14003536F
0x140035240  call    WinNatInitializeWFP
0x140035245  mov     ebx, eax
0x140035247  test    eax, eax
0x140035249  jns     short loc_140035270
0x14003524b  cmp     cs:dword_140026104, 1
0x140035252  jnz     loc_14003538B
0x140035258  test    cs:byte_140026BED, 10h
0x14003525f  jz      loc_14003538B
0x140035265  mov     r9d, 7D4h
0x14003526b  jmp     loc_14003536B
0x140035270  call    SlbNatInitialize
0x140035275  mov     ebx, eax
0x140035277  test    eax, eax
0x140035279  jns     short loc_1400352A0
0x14003527b  cmp     cs:dword_140026104, 1
0x140035282  jnz     loc_14003538B
0x140035288  test    cs:byte_140026BED, 10h
0x14003528f  jz      loc_14003538B
0x140035295  mov     r9d, 7D5h
0x14003529b  jmp     loc_14003536B
0x1400352a0  cmp     cs:EnableXlat, esi
0x1400352a6  jz      short loc_1400352B7
0x1400352a8  call    IPxlatInitialize
0x1400352ad  mov     ebx, eax
0x1400352af  test    eax, eax
0x1400352b1  js      loc_14003538B
0x1400352b7  call    WinNatRegisterChangeNotification
0x1400352bc  mov     ebx, eax
0x1400352be  test    eax, eax
0x1400352c0  jns     short loc_1400352E7
0x1400352c2  cmp     cs:dword_140026104, 1
0x1400352c9  jnz     loc_14003538B
0x1400352cf  test    cs:byte_140026BED, 10h
0x1400352d6  jz      loc_14003538B
0x1400352dc  mov     r9d, 7D6h
0x1400352e2  jmp     loc_14003536B
0x1400352e7  lea     r8, WinNatNsiRegistrationHandle; NmrProviderHandle
0x1400352ee  xor     edx, edx; ProviderContext
0x1400352f0  lea     rcx, WinNatProviderCharacteristics; ProviderCharacteristics
0x1400352f7  call    cs:__imp_NmrRegisterProvider
0x1400352fe  nop     dword ptr [rax+rax+00h]
0x140035303  mov     ebx, eax
0x140035305  test    eax, eax
0x140035307  jns     short loc_140035323
0x140035309  cmp     cs:dword_140026104, 1
0x140035310  jnz     short loc_14003538B
0x140035312  test    cs:byte_140026BED, 10h
0x140035319  jz      short loc_14003538B
0x14003531b  mov     r9d, 7D7h
0x140035321  jmp     short loc_14003536B
0x140035323  call    WinNatInitializePcwCounterSets
0x140035328  mov     ebx, eax
0x14003532a  test    eax, eax
0x14003532c  jns     short loc_140035348
0x14003532e  cmp     cs:dword_140026104, 1
0x140035335  jnz     short loc_14003538B
0x140035337  test    cs:byte_140026BED, 10h
0x14003533e  jz      short loc_14003538B
0x140035340  mov     r9d, 7D8h
0x140035346  jmp     short loc_14003536B
0x140035348  call    SlbNatLoadPersistentSettings
0x14003534d  mov     ebx, eax
0x14003534f  test    eax, eax
0x140035351  jns     short loc_140035395
0x140035353  cmp     cs:dword_140026104, 1
0x14003535a  jnz     short loc_14003538B
0x14003535c  test    cs:byte_140026BED, 10h
0x140035363  jz      short loc_14003538B
0x140035365  mov     r9d, 7D9h
0x14003536b  mov     dword ptr [rsp+188h+DeviceObject], eax
0x14003536f  lea     rax, aDriverentry; "DriverEntry"
0x140035376  mov     dword ptr [rsp+188h+Exclusive], esi
0x14003537a  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140035381  mov     qword ptr [rsp+188h+DeviceCharacteristics], rax
0x140035386  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003538b  mov     rcx, rdi
0x14003538e  call    WinNatUnload
0x140035393  jmp     short loc_1400353A5
0x140035395  call    WinNatLoadPersistentSettings
0x14003539a  lea     rax, WinNatUnload
0x1400353a1  mov     [rdi+68h], rax
0x1400353a5  mov     eax, ebx
0x1400353a7  mov     rcx, [rsp+188h+var_18]
0x1400353af  xor     rcx, rsp; StackCookie
0x1400353b2  call    __security_check_cookie
0x1400353b7  lea     r11, [rsp+188h+var_8]
0x1400353bf  mov     rbx, [r11+18h]
0x1400353c3  mov     rsi, [r11+20h]
0x1400353c7  mov     rsp, r11
0x1400353ca  pop     rdi
0x1400353cb  retn
```
