# IdpMainInit

- ea: `0x1402822e8`
- end: `0x1402824d8`
- name: `IdpMainInit`
- size: `496`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140281c44`

## callees

- `0x1400541c0`
- `0x1400b9b6c`
- `0x140156cb8`
- `0x1401816c4`
- `0x140255e00`
- `0x140279924`
- `0x14027a204`
- `0x14027a9ac`
- `0x1402822e8`

## import_xrefs

- `ntoskrnl!IoCreateSymbolicLink` at `0x1402823a8`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1402823a8`
- `ntoskrnl!IoCreateDevice` at `0x14028234f`
- `ntoskrnl!IoCreateDevice` at `0x14028234f`
- `ntoskrnl!EtwRegister` at `0x14028240c`
- `ntoskrnl!EtwRegister` at `0x14028240c`
- `ntoskrnl!EtwUnregister` at `0x140282437`
- `ntoskrnl!EtwUnregister` at `0x140282437`
- `ntoskrnl!RtlInitUnicodeString` at `0x14028231a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140282392`
- `ntoskrnl!RtlInitUnicodeString` at `0x14028231a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140282392`
- `NETIO!FwpmEventProviderCreate0` at `0x1402823dd`
- `NETIO!FwpmEventProviderCreate0` at `0x1402823dd`

## string_xrefs

- `0x1402823bb`: `IoCreateSymbolicLink`
- `0x1402823f0`: `FwpmEventProviderCreate0`

## pseudocode

```c
__int64 __fastcall IdpMainInit(PDRIVER_OBJECT DriverObject, _QWORD *a2, _QWORD *a3)
{
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  const char *v9; // rdx
  __int64 v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // eax
  NTSTATUS v13; // ebx
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
    v10 = WfpAllowBfeGenericAll((__int64)gIdpDeviceObject);
    if ( v10 )
    {
LABEL_14:
      IdpMainShutdown();
      return (unsigned int)v10;
    }
    RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\IPSECDOSPDevice");
    v11 = IoCreateSymbolicLink(&DestinationString, &DeviceName);
    if ( v11 )
    {
      v8 = v11;
      v9 = "IoCreateSymbolicLink";
    }
    else
    {
      gIdpSymLinkCreated = 1;
      v12 = FwpmEventProviderCreate0(3, &gIdpDiagEventHandle);
      if ( v12 )
      {
        v8 = v12;
        v9 = "FwpmEventProviderCreate0";
      }
      else
      {
        v13 = EtwRegister(&MICROSOFT_WFP_PROVIDER, 0, 0, &gIdpOpEventHandle);
        if ( !v13 )
        {
          v13 = NetTrcRegisterCorrelationProviderEx(&MICROSOFT_WFP_PROVIDER);
          if ( v13 )
            EtwUnregister(gIdpOpEventHandle);
        }
        if ( v13 >= 0 )
        {
          v10 = WfpInitializeTimerManager(gIdpDeviceObject, &gIdpTimerManager);
          if ( !v10 )
          {
            gIdpTimerManagerInit = 1;
            v10 = IdpStateInit();
            if ( !v10 )
            {
              v10 = IdpQosInit();
              if ( !v10 )
              {
                v10 = IdpCalloutInit();
                if ( !v10 )
                {
                  *a2 = gIdpDeviceObject;
                  *a3 = &IdpDispatchIoctl;
                  return (unsigned int)v10;
                }
              }
            }
          }
          goto LABEL_14;
        }
        v8 = (unsigned int)v13;
        v9 = "NetTrcRegister";
      }
    }
  }
  v10 = WfpReportSysErrorAsNtStatus(v7, v9, v8);
  if ( v10 )
    goto LABEL_14;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1402822e8  mov     rax, rsp
0x1402822eb  mov     [rax+8], rbx
0x1402822ef  mov     [rax+10h], rsi
0x1402822f3  push    rdi
0x1402822f4  sub     rsp, 60h
0x1402822f8  mov     rsi, rdx
0x1402822fb  mov     rbx, rcx
0x1402822fe  xorps   xmm0, xmm0
0x140282301  lea     rdx, aDeviceIpsecdos; "\\Device\\IPSECDOSP"
0x140282308  xorps   xmm1, xmm1
0x14028230b  lea     rcx, [rax-28h]; DestinationString
0x14028230f  movups  xmmword ptr [rax-28h], xmm0
0x140282313  mov     rdi, r8
0x140282316  movups  xmmword ptr [rax-18h], xmm1
0x14028231a  call    cs:__imp_RtlInitUnicodeString
0x140282321  nop     dword ptr [rax+rax+00h]
0x140282326  lea     rax, gIdpDeviceObject
0x14028232d  mov     r9d, 12h; DeviceType
0x140282333  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x140282338  lea     r8, [rsp+68h+DeviceName]; DeviceName
0x14028233d  mov     [rsp+68h+Exclusive], 0; Exclusive
0x140282342  xor     edx, edx; DeviceExtensionSize
0x140282344  mov     rcx, rbx; DriverObject
0x140282347  mov     [rsp+68h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14028234f  call    cs:__imp_IoCreateDevice
0x140282356  nop     dword ptr [rax+rax+00h]
0x14028235b  test    eax, eax
0x14028235d  jz      short loc_14028236E
0x14028235f  mov     r8d, eax
0x140282362  lea     rdx, aIoceatedevice; "IoCeateDevice"
0x140282369  jmp     loc_140282451
0x14028236e  mov     rcx, cs:gIdpDeviceObject
0x140282375  call    WfpAllowBfeGenericAll
0x14028237a  mov     rbx, rax
0x14028237d  test    rax, rax
0x140282380  jnz     loc_14028245E
0x140282386  lea     rdx, aDosdevicesIpse; "\\DosDevices\\IPSECDOSPDevice"
0x14028238d  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140282392  call    cs:__imp_RtlInitUnicodeString
0x140282399  nop     dword ptr [rax+rax+00h]
0x14028239e  lea     rdx, [rsp+68h+DeviceName]; DeviceName
0x1402823a3  lea     rcx, [rsp+68h+DestinationString]; SymbolicLinkName
0x1402823a8  call    cs:__imp_IoCreateSymbolicLink
0x1402823af  nop     dword ptr [rax+rax+00h]
0x1402823b4  test    eax, eax
0x1402823b6  jz      short loc_1402823C7
0x1402823b8  mov     r8d, eax
0x1402823bb  lea     rdx, aIocreatesymbol; "IoCreateSymbolicLink"
0x1402823c2  jmp     loc_140282451
0x1402823c7  lea     rdx, gIdpDiagEventHandle
0x1402823ce  mov     cs:gIdpSymLinkCreated, 1
0x1402823d8  mov     ecx, 3
0x1402823dd  call    cs:__imp_FwpmEventProviderCreate0
0x1402823e4  nop     dword ptr [rax+rax+00h]
0x1402823e9  test    eax, eax
0x1402823eb  jz      short loc_1402823F9
0x1402823ed  mov     r8d, eax
0x1402823f0  lea     rdx, aFwpmeventprovi; "FwpmEventProviderCreate0"
0x1402823f7  jmp     short loc_140282451
0x1402823f9  lea     r9, gIdpOpEventHandle; RegHandle
0x140282400  xor     r8d, r8d; CallbackContext
0x140282403  xor     edx, edx; EnableCallback
0x140282405  lea     rcx, MICROSOFT_WFP_PROVIDER; ProviderId
0x14028240c  call    cs:__imp_EtwRegister
0x140282413  nop     dword ptr [rax+rax+00h]
0x140282418  mov     ebx, eax
0x14028241a  test    eax, eax
0x14028241c  jnz     short loc_140282443
0x14028241e  lea     rcx, MICROSOFT_WFP_PROVIDER
0x140282425  call    NetTrcRegisterCorrelationProviderEx
0x14028242a  mov     ebx, eax
0x14028242c  test    eax, eax
0x14028242e  jz      short loc_140282443
0x140282430  mov     rcx, cs:gIdpOpEventHandle; RegHandle
0x140282437  call    cs:__imp_EtwUnregister
0x14028243e  nop     dword ptr [rax+rax+00h]
0x140282443  test    ebx, ebx
0x140282445  jns     short loc_140282476
0x140282447  mov     r8d, ebx
0x14028244a  lea     rdx, aNettrcregister; "NetTrcRegister"
0x140282451  call    WfpReportSysErrorAsNtStatus
0x140282456  mov     rbx, rax
0x140282459  test    rax, rax
0x14028245c  jz      short loc_140282463
0x14028245e  call    IdpMainShutdown
0x140282463  mov     rsi, [rsp+68h+arg_8]
0x140282468  mov     eax, ebx
0x14028246a  mov     rbx, [rsp+68h+arg_0]
0x14028246f  add     rsp, 60h
0x140282473  pop     rdi
0x140282474  retn
0x140282476  mov     rcx, cs:gIdpDeviceObject; Object
0x14028247d  lea     rdx, gIdpTimerManager; void *
0x140282484  call    WfpInitializeTimerManager
0x140282489  mov     rbx, rax
0x14028248c  test    rax, rax
0x14028248f  jnz     short loc_14028245E
0x140282491  mov     cs:gIdpTimerManagerInit, 1
0x14028249b  call    IdpStateInit
0x1402824a0  mov     rbx, rax
0x1402824a3  test    rax, rax
0x1402824a6  jnz     short loc_14028245E
0x1402824a8  call    IdpQosInit
0x1402824ad  mov     rbx, rax
0x1402824b0  test    rax, rax
0x1402824b3  jnz     short loc_14028245E
0x1402824b5  call    IdpCalloutInit
0x1402824ba  mov     rbx, rax
0x1402824bd  test    rax, rax
0x1402824c0  jnz     short loc_14028245E
0x1402824c2  mov     rax, cs:gIdpDeviceObject
0x1402824c9  mov     [rsi], rax
0x1402824cc  lea     rax, IdpDispatchIoctl
0x1402824d3  mov     [rdi], rax
0x1402824d6  jmp     short loc_140282463
```
