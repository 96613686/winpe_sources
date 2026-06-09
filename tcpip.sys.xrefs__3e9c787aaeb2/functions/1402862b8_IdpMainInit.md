# IdpMainInit

- ea: `0x1402862b8`
- end: `0x1402864a8`
- name: `IdpMainInit`
- size: `496`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140285c14`

## callees

- `0x140014a90`
- `0x1400c369c`
- `0x140158ab8`
- `0x140183274`
- `0x140259e00`
- `0x14027d924`
- `0x14027e204`
- `0x14027e9ac`
- `0x1402862b8`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x140286378`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140286378`
- `ntoskrnl!IoCreateDevice` at `0x14028631f`
- `ntoskrnl!IoCreateDevice` at `0x14028631f`
- `ntoskrnl!EtwRegister` at `0x1402863dc`
- `ntoskrnl!EtwRegister` at `0x1402863dc`
- `ntoskrnl!EtwUnregister` at `0x140286407`
- `ntoskrnl!EtwUnregister` at `0x140286407`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402862ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x140286362`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402862ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x140286362`
- `NETIO!FwpmEventProviderCreate0` at `0x1402863ad`
- `NETIO!FwpmEventProviderCreate0` at `0x1402863ad`

## string_xrefs

- `0x14028638b`: `IoCreateSymbolicLink`
- `0x1402863c0`: `FwpmEventProviderCreate0`

## pseudocode

```c
__int64 __fastcall IdpMainInit(PDRIVER_OBJECT DriverObject, _QWORD *a2, _QWORD *a3)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  const char *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  NTSTATUS v15; // ebx
  __int64 v16; // rax
  __int64 v18; // rax
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  DeviceName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DeviceName, L"\\Device\\IPSECDOSP");
  v6 = IoCreateDevice(DriverObject, 0, &DeviceName, 0x12u, 0x100u, 0, &gIdpDeviceObject);
  if ( v6 )
  {
    v8 = v6;
    v9 = "IoCeateDevice";
  }
  else
  {
    v12 = WfpAllowBfeGenericAll((__int64)gIdpDeviceObject);
    if ( v12 )
    {
LABEL_14:
      IdpMainShutdown(v11, v10);
      return (unsigned int)v12;
    }
    RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\IPSECDOSPDevice");
    v13 = IoCreateSymbolicLink(&DestinationString, &DeviceName);
    if ( v13 )
    {
      v8 = v13;
      v9 = "IoCreateSymbolicLink";
    }
    else
    {
      gIdpSymLinkCreated = 1;
      v14 = FwpmEventProviderCreate0(3, &gIdpDiagEventHandle);
      if ( v14 )
      {
        v8 = v14;
        v9 = "FwpmEventProviderCreate0";
      }
      else
      {
        v15 = EtwRegister(&MICROSOFT_WFP_PROVIDER, 0, 0, &gIdpOpEventHandle);
        if ( !v15 )
        {
          v15 = NetTrcRegisterCorrelationProviderEx(&MICROSOFT_WFP_PROVIDER);
          if ( v15 )
            EtwUnregister(gIdpOpEventHandle);
        }
        if ( v15 >= 0 )
        {
          v12 = WfpInitializeTimerManager(gIdpDeviceObject, (PNDIS_RW_LOCK_EX *)&gIdpTimerManager);
          if ( !v12 )
          {
            gIdpTimerManagerInit = 1;
            v12 = IdpStateInit();
            if ( !v12 )
            {
              v12 = IdpQosInit();
              if ( !v12 )
              {
                v18 = IdpCalloutInit();
                LODWORD(v12) = v18;
                if ( !v18 )
                {
                  *a2 = gIdpDeviceObject;
                  *a3 = &IdpDispatchIoctl;
                  return (unsigned int)v12;
                }
              }
            }
          }
          goto LABEL_14;
        }
        v8 = (unsigned int)v15;
        v9 = "NetTrcRegister";
      }
    }
  }
  v16 = WfpReportSysErrorAsNtStatus(v7, v9, v8);
  LODWORD(v12) = v16;
  if ( v16 )
    goto LABEL_14;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1402862b8  mov     rax, rsp
0x1402862bb  mov     [rax+8], rbx
0x1402862bf  mov     [rax+10h], rsi
0x1402862c3  push    rdi
0x1402862c4  sub     rsp, 60h
0x1402862c8  mov     rsi, rdx
0x1402862cb  mov     rbx, rcx
0x1402862ce  xorps   xmm0, xmm0
0x1402862d1  lea     rdx, aDeviceIpsecdos; "\\Device\\IPSECDOSP"
0x1402862d8  xorps   xmm1, xmm1
0x1402862db  lea     rcx, [rax-28h]; DestinationString
0x1402862df  movups  xmmword ptr [rax-28h], xmm0
0x1402862e3  mov     rdi, r8
0x1402862e6  movups  xmmword ptr [rax-18h], xmm1
0x1402862ea  call    cs:__imp_RtlInitUnicodeString
0x1402862f1  nop     dword ptr [rax+rax+00h]
0x1402862f6  lea     rax, gIdpDeviceObject
0x1402862fd  mov     r9d, 12h; DeviceType
0x140286303  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x140286308  lea     r8, [rsp+68h+DeviceName]; DeviceName
0x14028630d  mov     [rsp+68h+Exclusive], 0; Exclusive
0x140286312  xor     edx, edx; DeviceExtensionSize
0x140286314  mov     rcx, rbx; DriverObject
0x140286317  mov     [rsp+68h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14028631f  call    cs:__imp_IoCreateDevice
0x140286326  nop     dword ptr [rax+rax+00h]
0x14028632b  test    eax, eax
0x14028632d  jz      short loc_14028633E
0x14028632f  mov     r8d, eax
0x140286332  lea     rdx, aIoceatedevice; "IoCeateDevice"
0x140286339  jmp     loc_140286421
0x14028633e  mov     rcx, cs:gIdpDeviceObject
0x140286345  call    WfpAllowBfeGenericAll
0x14028634a  mov     rbx, rax
0x14028634d  test    rax, rax
0x140286350  jnz     loc_14028642E
0x140286356  lea     rdx, aDosdevicesIpse; "\\DosDevices\\IPSECDOSPDevice"
0x14028635d  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140286362  call    cs:__imp_RtlInitUnicodeString
0x140286369  nop     dword ptr [rax+rax+00h]
0x14028636e  lea     rdx, [rsp+68h+DeviceName]; DeviceName
0x140286373  lea     rcx, [rsp+68h+DestinationString]; SymbolicLinkName
0x140286378  call    cs:__imp_IoCreateSymbolicLink
0x14028637f  nop     dword ptr [rax+rax+00h]
0x140286384  test    eax, eax
0x140286386  jz      short loc_140286397
0x140286388  mov     r8d, eax
0x14028638b  lea     rdx, aIocreatesymbol; "IoCreateSymbolicLink"
0x140286392  jmp     loc_140286421
0x140286397  lea     rdx, gIdpDiagEventHandle
0x14028639e  mov     cs:gIdpSymLinkCreated, 1
0x1402863a8  mov     ecx, 3
0x1402863ad  call    cs:__imp_FwpmEventProviderCreate0
0x1402863b4  nop     dword ptr [rax+rax+00h]
0x1402863b9  test    eax, eax
0x1402863bb  jz      short loc_1402863C9
0x1402863bd  mov     r8d, eax
0x1402863c0  lea     rdx, aFwpmeventprovi; "FwpmEventProviderCreate0"
0x1402863c7  jmp     short loc_140286421
0x1402863c9  lea     r9, gIdpOpEventHandle; RegHandle
0x1402863d0  xor     r8d, r8d; CallbackContext
0x1402863d3  xor     edx, edx; EnableCallback
0x1402863d5  lea     rcx, MICROSOFT_WFP_PROVIDER; ProviderId
0x1402863dc  call    cs:__imp_EtwRegister
0x1402863e3  nop     dword ptr [rax+rax+00h]
0x1402863e8  mov     ebx, eax
0x1402863ea  test    eax, eax
0x1402863ec  jnz     short loc_140286413
0x1402863ee  lea     rcx, MICROSOFT_WFP_PROVIDER
0x1402863f5  call    NetTrcRegisterCorrelationProviderEx
0x1402863fa  mov     ebx, eax
0x1402863fc  test    eax, eax
0x1402863fe  jz      short loc_140286413
0x140286400  mov     rcx, cs:gIdpOpEventHandle; RegHandle
0x140286407  call    cs:__imp_EtwUnregister
0x14028640e  nop     dword ptr [rax+rax+00h]
0x140286413  test    ebx, ebx
0x140286415  jns     short loc_140286446
0x140286417  mov     r8d, ebx
0x14028641a  lea     rdx, aNettrcregister; "NetTrcRegister"
0x140286421  call    WfpReportSysErrorAsNtStatus
0x140286426  mov     rbx, rax
0x140286429  test    rax, rax
0x14028642c  jz      short loc_140286433
0x14028642e  call    IdpMainShutdown
0x140286433  mov     rsi, [rsp+68h+arg_8]
0x140286438  mov     eax, ebx
0x14028643a  mov     rbx, [rsp+68h+arg_0]
0x14028643f  add     rsp, 60h
0x140286443  pop     rdi
0x140286444  retn
0x140286446  mov     rcx, cs:gIdpDeviceObject; Object
0x14028644d  lea     rdx, gIdpTimerManager; void *
0x140286454  call    WfpInitializeTimerManager
0x140286459  mov     rbx, rax
0x14028645c  test    rax, rax
0x14028645f  jnz     short loc_14028642E
0x140286461  mov     cs:gIdpTimerManagerInit, 1
0x14028646b  call    IdpStateInit
0x140286470  mov     rbx, rax
0x140286473  test    rax, rax
0x140286476  jnz     short loc_14028642E
0x140286478  call    IdpQosInit
0x14028647d  mov     rbx, rax
0x140286480  test    rax, rax
0x140286483  jnz     short loc_14028642E
0x140286485  call    IdpCalloutInit
0x14028648a  mov     rbx, rax
0x14028648d  test    rax, rax
0x140286490  jnz     short loc_14028642E
0x140286492  mov     rax, cs:gIdpDeviceObject
0x140286499  mov     [rsi], rax
0x14028649c  lea     rax, IdpDispatchIoctl
0x1402864a3  mov     [rdi], rax
0x1402864a6  jmp     short loc_140286433
```
