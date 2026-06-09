# TdxInitializeModule

- ea: `0x140014184`
- end: `0x14001459a`
- name: `TdxInitializeModule`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x140017360`

## callees

- `0x14001154c`
- `0x140011c38`
- `0x140011f10`
- `0x140012620`
- `0x140012b34`
- `0x140012b5c`
- `0x140014184`
- `0x140015038`
- `0x140015658`
- `0x1400156d4`
- `0x140017494`
- `0x140018064`
- `0x140023008`
- `0x140024078`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140014232`
- `ntoskrnl!IoCreateDevice` at `0x140014232`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140014282`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400142c7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140014282`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400142c7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001453c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014552`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018f8b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018fa1`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001453c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140014552`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018f8b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018fa1`
- `ntoskrnl!IoDeleteDevice` at `0x14001456a`
- `ntoskrnl!IoDeleteDevice` at `0x140018fba`
- `ntoskrnl!IoDeleteDevice` at `0x14001456a`
- `ntoskrnl!IoDeleteDevice` at `0x140018fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400144d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f21`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400141fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001426c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400142b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001434e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400141fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001426c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400142b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001434e`
- `NETIO!NmrRegisterProvider` at `0x1400143cc`
- `NETIO!NmrRegisterProvider` at `0x1400143cc`
- `NETIO!NmrRegisterClient` at `0x140014399`
- `NETIO!NmrRegisterClient` at `0x140014439`
- `NETIO!NmrRegisterClient` at `0x140014399`
- `NETIO!NmrRegisterClient` at `0x140014439`
- `TDI!TdiRegisterProvider` at `0x140014366`
- `TDI!TdiRegisterProvider` at `0x140014366`
- `TDI!TdiProviderReady` at `0x140014470`
- `TDI!TdiProviderReady` at `0x140014470`
- `TDI!TdiDeregisterProvider` at `0x140014507`
- `TDI!TdiDeregisterProvider` at `0x140018f53`
- `TDI!TdiDeregisterProvider` at `0x140014507`
- `TDI!TdiDeregisterProvider` at `0x140018f53`

## pseudocode

```c
__int64 __fastcall TdxInitializeModule(struct _DRIVER_OBJECT *a1)
{
  __int16 v1; // bx
  NTSTATUS v2; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-50h] BYREF
  struct _UNICODE_STRING v5; // [rsp+58h] [rbp-40h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+68h] [rbp-30h] BYREF
  struct _UNICODE_STRING ProviderName; // [rsp+78h] [rbp-20h] BYREF
  char v8; // [rsp+A0h] [rbp+8h] BYREF

  v8 = 0;
  DestinationString = 0;
  ProviderName = 0;
  SymbolicLinkName = 0;
  v5 = 0;
  TdxDriverObject = a1;
  v1 = 0;
  v2 = wil_InitializeFeatureStaging();
  if ( v2 >= 0 )
  {
    v2 = TdxInitializeEntityArray();
    if ( v2 >= 0 )
    {
      v1 = 1;
      RtlInitUnicodeString(&DestinationString, L"\\Device\\Tdx");
      v2 = IoCreateDevice(TdxDriverObject, 0, &DestinationString, 0x21u, 0x100u, 0, &TdxDeviceObject);
      if ( v2 >= 0 )
      {
        v1 = 3;
        TdxDeviceObject->Flags |= 0x10u;
        RtlInitUnicodeString(&SymbolicLinkName, L"\\Device\\Ip");
        v2 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
        if ( v2 >= 0 )
        {
          v1 = 7;
          RtlInitUnicodeString(&v5, L"\\Device\\Ip6");
          v2 = IoCreateSymbolicLink(&v5, &DestinationString);
          if ( v2 >= 0 )
          {
            v1 = 15;
            v2 = TdxInitializeTransportModule();
            if ( v2 >= 0 )
            {
              v1 = 31;
              v2 = TdxInitializeTransportAddressModule();
              if ( v2 >= 0 )
              {
                v1 = 255;
                RtlInitUnicodeString(&ProviderName, L"\\Device\\Tdx");
                v2 = TdiRegisterProvider(&ProviderName, &TdxTdiProviderHandle);
                if ( v2 >= 0 )
                {
                  v1 = 511;
                  v2 = NmrRegisterClient(&TdxTlClientNotify, 0, &TdxTlClientHandle);
                  if ( v2 >= 0 )
                  {
                    v1 = 1023;
                    v2 = NmrRegisterProvider(&TdxNsiProviderNotify, 0, (PHANDLE)&WPP_MAIN_CB.Queue.ListEntry.Flink);
                    if ( v2 >= 0 )
                    {
                      v1 = 2047;
                      v2 = TdxInitializeNaClientModule(&v8);
                      if ( v2 >= 0 )
                      {
                        v1 = 4095;
                        WPP_MAIN_CB.DeviceExtension = 0;
                        *(_QWORD *)&WPP_MAIN_CB.DeviceType = 0;
                        v2 = NmrRegisterClient(&TdxPnpEventClientNotify, 0, &WPP_MAIN_CB.DeviceExtension);
                        if ( v2 >= 0 )
                        {
                          v1 = 0x1FFF;
                          if ( !v8 )
                          {
                            _InterlockedIncrement((volatile signed __int32 *)&qword_14001E508);
                            TdiProviderReady(TdxTdiProviderHandle);
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                10,
                                WPP_bc140b0f64a03b9eb3fa92c495441d9d_Traceguids);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v2 < 0 )
  {
    if ( (v1 & 0x1000) != 0 )
      TdxShutdownPnpEventClientModule();
    if ( (v1 & 1) != 0 )
      ExFreePoolWithTag(TdxEntityArray, 0x20786454u);
    if ( (v1 & 0x400) != 0 )
      TdxShutdownNsiProviderModule();
    if ( (v1 & 0x200) != 0 )
      TdxShutdownTlClientModule();
    if ( (v1 & 0x100) != 0 )
      TdiDeregisterProvider(TdxTdiProviderHandle);
    if ( (v1 & 0x20) != 0 )
      TdxShutdownTransportAddressModule();
    if ( (v1 & 0x10) != 0 )
      TdxShutdownTransportModule();
    if ( (v1 & 0x800) != 0 )
      TdxShutdownNaClientModule();
    if ( (v1 & 8) != 0 )
      IoDeleteSymbolicLink(&v5);
    if ( (v1 & 4) != 0 )
      IoDeleteSymbolicLink(&SymbolicLinkName);
    if ( (v1 & 2) != 0 )
    {
      IoDeleteDevice(TdxDeviceObject);
      TdxDeviceObject = 0;
    }
    wil_UninitializeFeatureStaging();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140014184  mov     rax, rsp
0x140014187  mov     [rax+10h], rbx
0x14001418b  push    rdi
0x14001418c  sub     rsp, 90h
0x140014193  mov     byte ptr [rax+8], 0
0x140014197  xorps   xmm0, xmm0
0x14001419a  movups  xmmword ptr [rax-50h], xmm0
0x14001419e  xorps   xmm1, xmm1
0x1400141a1  movups  xmmword ptr [rax-20h], xmm1
0x1400141a5  movups  xmmword ptr [rax-30h], xmm0
0x1400141a9  movups  xmmword ptr [rax-40h], xmm1
0x1400141ad  mov     dword ptr [rax-58h], 0C0000001h
0x1400141b4  mov     cs:TdxDriverObject, rcx
0x1400141bb  xor     ebx, ebx
0x1400141bd  mov     [rax-54h], ebx
0x1400141c0  call    wil_InitializeFeatureStaging
0x1400141c5  mov     edi, eax
0x1400141c7  mov     [rsp+98h+var_58], eax
0x1400141cb  test    eax, eax
0x1400141cd  js      loc_1400144B4
0x1400141d3  call    TdxInitializeEntityArray
0x1400141d8  mov     edi, eax
0x1400141da  mov     [rsp+98h+var_58], eax
0x1400141de  test    eax, eax
0x1400141e0  js      loc_1400144B4
0x1400141e6  mov     ebx, 1
0x1400141eb  mov     [rsp+98h+var_54], ebx
0x1400141ef  lea     rdx, TdxDeviceName; "\\Device\\Tdx"
0x1400141f6  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400141fb  call    cs:__imp_RtlInitUnicodeString
0x140014202  nop     dword ptr [rax+rax+00h]
0x140014207  lea     rax, TdxDeviceObject
0x14001420e  mov     [rsp+98h+DeviceObject], rax; DeviceObject
0x140014213  mov     [rsp+98h+Exclusive], 0; Exclusive
0x140014218  mov     [rsp+98h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140014220  lea     r9d, [rbx+20h]; DeviceType
0x140014224  lea     r8, [rsp+98h+DestinationString]; DeviceName
0x140014229  xor     edx, edx; DeviceExtensionSize
0x14001422b  mov     rcx, cs:TdxDriverObject; DriverObject
0x140014232  call    cs:__imp_IoCreateDevice
0x140014239  nop     dword ptr [rax+rax+00h]
0x14001423e  mov     edi, eax
0x140014240  mov     [rsp+98h+var_58], eax
0x140014244  test    eax, eax
0x140014246  js      loc_1400144B4
0x14001424c  mov     ebx, 3
0x140014251  mov     [rsp+98h+var_54], ebx
0x140014255  mov     rax, cs:TdxDeviceObject
0x14001425c  or      dword ptr [rax+30h], 10h
0x140014260  lea     rdx, TdxIpDeviceName; "\\Device\\Ip"
0x140014267  lea     rcx, [rsp+98h+SymbolicLinkName]; DestinationString
0x14001426c  call    cs:__imp_RtlInitUnicodeString
0x140014273  nop     dword ptr [rax+rax+00h]
0x140014278  lea     rdx, [rsp+98h+DestinationString]; DeviceName
0x14001427d  lea     rcx, [rsp+98h+SymbolicLinkName]; SymbolicLinkName
0x140014282  call    cs:__imp_IoCreateSymbolicLink
0x140014289  nop     dword ptr [rax+rax+00h]
0x14001428e  mov     edi, eax
0x140014290  mov     [rsp+98h+var_58], eax
0x140014294  test    eax, eax
0x140014296  js      loc_1400144B4
0x14001429c  mov     ebx, 7
0x1400142a1  mov     [rsp+98h+var_54], ebx
0x1400142a5  lea     rdx, TdxIpv6DeviceName; "\\Device\\Ip6"
0x1400142ac  lea     rcx, [rsp+98h+var_40]; DestinationString
0x1400142b1  call    cs:__imp_RtlInitUnicodeString
0x1400142b8  nop     dword ptr [rax+rax+00h]
0x1400142bd  lea     rdx, [rsp+98h+DestinationString]; DeviceName
0x1400142c2  lea     rcx, [rsp+98h+var_40]; SymbolicLinkName
0x1400142c7  call    cs:__imp_IoCreateSymbolicLink
0x1400142ce  nop     dword ptr [rax+rax+00h]
0x1400142d3  mov     edi, eax
0x1400142d5  mov     [rsp+98h+var_58], eax
0x1400142d9  test    eax, eax
0x1400142db  js      loc_1400144B4
0x1400142e1  mov     ebx, 0Fh
0x1400142e6  mov     [rsp+98h+var_54], ebx
0x1400142ea  call    TdxInitializeTransportModule
0x1400142ef  mov     edi, eax
0x1400142f1  mov     [rsp+98h+var_58], eax
0x1400142f5  test    eax, eax
0x1400142f7  js      loc_1400144B4
0x1400142fd  mov     ebx, 1Fh
0x140014302  mov     [rsp+98h+var_54], ebx
0x140014306  call    TdxInitializeTransportAddressModule
0x14001430b  mov     edi, eax
0x14001430d  mov     [rsp+98h+var_58], eax
0x140014311  test    eax, eax
0x140014313  js      loc_1400144B4
0x140014319  mov     [rsp+98h+var_54], 3Fh ; '?'
0x140014321  mov     [rsp+98h+var_58], 0
0x140014329  mov     [rsp+98h+var_54], 7Fh
0x140014331  mov     [rsp+98h+var_58], 0
0x140014339  mov     ebx, 0FFh
0x14001433e  mov     [rsp+98h+var_54], ebx
0x140014342  lea     rdx, TdxDeviceName; "\\Device\\Tdx"
0x140014349  lea     rcx, [rsp+98h+ProviderName]; DestinationString
0x14001434e  call    cs:__imp_RtlInitUnicodeString
0x140014355  nop     dword ptr [rax+rax+00h]
0x14001435a  lea     rdx, TdxTdiProviderHandle; ProviderHandle
0x140014361  lea     rcx, [rsp+98h+ProviderName]; ProviderName
0x140014366  call    cs:__imp_TdiRegisterProvider
0x14001436d  nop     dword ptr [rax+rax+00h]
0x140014372  mov     edi, eax
0x140014374  mov     [rsp+98h+var_58], eax
0x140014378  test    eax, eax
0x14001437a  js      loc_1400144B4
0x140014380  mov     ebx, 1FFh
0x140014385  mov     [rsp+98h+var_54], ebx
0x140014389  lea     r8, TdxTlClientHandle; NmrClientHandle
0x140014390  xor     edx, edx; ClientContext
0x140014392  lea     rcx, TdxTlClientNotify; ClientCharacteristics
0x140014399  call    cs:__imp_NmrRegisterClient
0x1400143a0  nop     dword ptr [rax+rax+00h]
0x1400143a5  mov     edi, eax
0x1400143a7  mov     [rsp+98h+var_58], eax
0x1400143ab  test    eax, eax
0x1400143ad  js      loc_1400144B4
0x1400143b3  mov     ebx, 3FFh
0x1400143b8  mov     [rsp+98h+var_54], ebx
0x1400143bc  lea     r8, WPP_MAIN_CB.Queue; NmrProviderHandle
0x1400143c3  xor     edx, edx; ProviderContext
0x1400143c5  lea     rcx, TdxNsiProviderNotify; ProviderCharacteristics
0x1400143cc  call    cs:__imp_NmrRegisterProvider
0x1400143d3  nop     dword ptr [rax+rax+00h]
0x1400143d8  mov     edi, eax
0x1400143da  mov     [rsp+98h+var_58], eax
0x1400143de  test    eax, eax
0x1400143e0  js      loc_1400144B4
0x1400143e6  mov     ebx, 7FFh
0x1400143eb  mov     [rsp+98h+var_54], ebx
0x1400143ef  lea     rcx, [rsp+98h+arg_0]
0x1400143f7  call    TdxInitializeNaClientModule
0x1400143fc  mov     edi, eax
0x1400143fe  mov     [rsp+98h+var_58], eax
0x140014402  test    eax, eax
0x140014404  js      loc_1400144B4
0x14001440a  mov     ebx, 0FFFh
0x14001440f  mov     [rsp+98h+var_54], ebx
0x140014413  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x14001441e  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, 0
0x140014429  lea     r8, WPP_MAIN_CB.DeviceExtension; NmrClientHandle
0x140014430  xor     edx, edx; ClientContext
0x140014432  lea     rcx, TdxPnpEventClientNotify; ClientCharacteristics
0x140014439  call    cs:__imp_NmrRegisterClient
0x140014440  nop     dword ptr [rax+rax+00h]
0x140014445  mov     edi, eax
0x140014447  mov     [rsp+98h+var_58], eax
0x14001444b  test    eax, eax
0x14001444d  js      short loc_1400144B4
0x14001444f  mov     ebx, 1FFFh
0x140014454  mov     [rsp+98h+var_54], ebx
0x140014458  cmp     [rsp+98h+arg_0], 0
0x140014460  jnz     short loc_1400144B4
0x140014462  lock inc dword ptr cs:qword_14001E508
0x140014469  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x140014470  call    cs:__imp_TdiProviderReady
0x140014477  nop     dword ptr [rax+rax+00h]
0x14001447c  lea     rax, WPP_GLOBAL_Control
0x140014483  mov     rcx, cs:WPP_GLOBAL_Control
0x14001448a  cmp     rcx, rax
0x14001448d  jz      short loc_1400144B4
0x14001448f  cmp     byte ptr [rcx+29h], 3
0x140014493  jb      short loc_1400144B4
0x140014495  mov     eax, [rcx+2Ch]
0x140014498  bt      eax, 9
0x14001449c  jnb     short loc_1400144B4
0x14001449e  mov     edx, 0Ah
0x1400144a3  lea     r8, WPP_bc140b0f64a03b9eb3fa92c495441d9d_Traceguids
0x1400144aa  mov     rcx, [rcx+18h]
0x1400144ae  call    WPP_SF_
0x1400144b3  nop
0x1400144b4  test    edi, edi
0x1400144b6  jns     loc_140014586
0x1400144bc  bt      ebx, 0Ch
0x1400144c0  jnb     short loc_1400144C7
0x1400144c2  call    TdxShutdownPnpEventClientModule
0x1400144c7  test    bl, 1
0x1400144ca  jz      short loc_1400144E4
0x1400144cc  mov     edx, 20786454h; Tag
0x1400144d1  mov     rcx, cs:TdxEntityArray; P
0x1400144d8  call    cs:__imp_ExFreePoolWithTag
0x1400144df  nop     dword ptr [rax+rax+00h]
0x1400144e4  bt      ebx, 0Ah
0x1400144e8  jnb     short loc_1400144EF
0x1400144ea  call    TdxShutdownNsiProviderModule
0x1400144ef  bt      ebx, 9
0x1400144f3  jnb     short loc_1400144FA
0x1400144f5  call    TdxShutdownTlClientModule
0x1400144fa  bt      ebx, 8
0x1400144fe  jnb     short loc_140014513
0x140014500  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x140014507  call    cs:__imp_TdiDeregisterProvider
0x14001450e  nop     dword ptr [rax+rax+00h]
0x140014513  test    bl, 20h
0x140014516  jz      short loc_14001451D
0x140014518  call    TdxShutdownTransportAddressModule
0x14001451d  test    bl, 10h
0x140014520  jz      short loc_140014527
0x140014522  call    TdxShutdownTransportModule
0x140014527  bt      ebx, 0Bh
0x14001452b  jnb     short loc_140014532
0x14001452d  call    TdxShutdownNaClientModule
0x140014532  test    bl, 8
0x140014535  jz      short loc_140014548
0x140014537  lea     rcx, [rsp+98h+var_40]; SymbolicLinkName
0x14001453c  call    cs:__imp_IoDeleteSymbolicLink
0x140014543  nop     dword ptr [rax+rax+00h]
0x140014548  test    bl, 4
0x14001454b  jz      short loc_14001455E
0x14001454d  lea     rcx, [rsp+98h+SymbolicLinkName]; SymbolicLinkName
0x140014552  call    cs:__imp_IoDeleteSymbolicLink
0x140014559  nop     dword ptr [rax+rax+00h]
0x14001455e  test    bl, 2
0x140014561  jz      short loc_140014581
0x140014563  mov     rcx, cs:TdxDeviceObject; DeviceObject
0x14001456a  call    cs:__imp_IoDeleteDevice
0x140014571  nop     dword ptr [rax+rax+00h]
0x140014576  mov     cs:TdxDeviceObject, 0
0x140014581  call    wil_UninitializeFeatureStaging
0x140014586  mov     eax, edi
0x140014588  mov     rbx, [rsp+98h+arg_8]
0x140014590  add     rsp, 90h
0x140014597  pop     rdi
0x140014598  retn
0x140018eed  push    rbx
0x140018eef  push    rbp
0x140018ef0  sub     rsp, 48h
0x140018ef4  mov     rbp, rdx
0x140018ef7  cmp     dword ptr [rbp+40h], 0
0x140018efb  jge     loc_140018FD7
0x140018f01  mov     ebx, [rbp+44h]
0x140018f04  bt      ebx, 0Ch
0x140018f08  jnb     short loc_140018F10
0x140018f0a  call    TdxShutdownPnpEventClientModule
0x140018f0f  nop
0x140018f10  test    bl, 1
0x140018f13  jz      short loc_140018F2E
0x140018f15  mov     edx, 20786454h; Tag
0x140018f1a  mov     rcx, cs:TdxEntityArray; P
0x140018f21  call    cs:__imp_ExFreePoolWithTag
0x140018f28  nop     dword ptr [rax+rax+00h]
0x140018f2d  nop
0x140018f2e  bt      ebx, 0Ah
0x140018f32  jnb     short loc_140018F3A
0x140018f34  call    TdxShutdownNsiProviderModule
0x140018f39  nop
0x140018f3a  bt      ebx, 9
0x140018f3e  jnb     short loc_140018F46
0x140018f40  call    TdxShutdownTlClientModule
0x140018f45  nop
0x140018f46  bt      ebx, 8
0x140018f4a  jnb     short loc_140018F60
0x140018f4c  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x140018f53  call    cs:__imp_TdiDeregisterProvider
0x140018f5a  nop     dword ptr [rax+rax+00h]
0x140018f5f  nop
0x140018f60  test    bl, 20h
0x140018f63  jz      short loc_140018F6B
0x140018f65  call    TdxShutdownTransportAddressModule
0x140018f6a  nop
0x140018f6b  test    bl, 10h
0x140018f6e  jz      short loc_140018F76
0x140018f70  call    TdxShutdownTransportModule
0x140018f75  nop
0x140018f76  bt      ebx, 0Bh
0x140018f7a  jnb     short loc_140018F82
0x140018f7c  call    TdxShutdownNaClientModule
0x140018f81  nop
0x140018f82  test    bl, 8
0x140018f85  jz      short loc_140018F98
0x140018f87  lea     rcx, [rbp+58h]; SymbolicLinkName
0x140018f8b  call    cs:__imp_IoDeleteSymbolicLink
0x140018f92  nop     dword ptr [rax+rax+00h]
0x140018f97  nop
0x140018f98  test    bl, 4
0x140018f9b  jz      short loc_140018FAE
0x140018f9d  lea     rcx, [rbp+68h]; SymbolicLinkName
0x140018fa1  call    cs:__imp_IoDeleteSymbolicLink
0x140018fa8  nop     dword ptr [rax+rax+00h]
0x140018fad  nop
0x140018fae  test    bl, 2
0x140018fb1  jz      short loc_140018FD1
0x140018fb3  mov     rcx, cs:TdxDeviceObject; DeviceObject
0x140018fba  call    cs:__imp_IoDeleteDevice
0x140018fc1  nop     dword ptr [rax+rax+00h]
0x140018fc6  mov     cs:TdxDeviceObject, 0
0x140018fd1  call    wil_UninitializeFeatureStaging
0x140018fd6  nop
0x140018fd7  add     rsp, 48h
0x140018fdb  pop     rbp
0x140018fdc  pop     rbx
0x140018fdd  retn
```
