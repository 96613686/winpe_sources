# VmsUninitializeDriver

- ea: `0x1400a41e8`
- end: `0x1400a42f7`
- name: `VmsUninitializeDriver`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007b6a0`

## callees

- `0x140046e5c`
- `0x1400883bc`
- `0x14008846c`
- `0x1400a37d8`
- `0x1400a41e8`
- `0x1400a4300`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400a42c2`
- `ntoskrnl!IoDeleteDevice` at `0x1400a42c2`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a423b`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a425e`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a423b`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a425e`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400a4281`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400a4281`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400a42a4`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400a42a4`

## pseudocode

```c
__int64 VmsUninitializeDriver()
{
  PVOID v0; // rcx

  WPP_RECORDER_SF_(VmsIfrLog, 4, 18, 39, (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids);
  VmsIsUnloadForServicing = 1;
  VmsVmNicDestroyControlDevice();
  VmsProxyUnregister();
  if ( VmsPDSwitchCount )
    VmsUninitializePD();
  if ( VmsProtocolHandle )
  {
    NdisDeregisterProtocolDriver(VmsProtocolHandle);
    VmsProtocolHandle = 0;
  }
  if ( VmsVswitchProtocolHandle )
  {
    NdisDeregisterProtocolDriver(VmsVswitchProtocolHandle);
    VmsVswitchProtocolHandle = 0;
  }
  if ( VmsVswitchFilterHandle )
  {
    NdisFDeregisterFilterDriver(VmsVswitchFilterHandle);
    VmsVswitchFilterHandle = 0;
  }
  if ( VmsVswitchMiniportHandle )
  {
    NdisMDeregisterMiniportDriver(VmsVswitchMiniportHandle);
    VmsVswitchMiniportHandle = 0;
  }
  IoDeleteDevice(VmsCdCtlDeviceObjectInternal);
  v0 = VmsDriverObject;
  VmsCdCtlDeviceObjectInternal = 0;
  *(_QWORD *)(*((_QWORD *)VmsDriverObject + 6) + 8LL) = 0;
  return VmsDriverUnload((__int64)v0);
}

```

## disassembly

```asm
0x1400a41e8  sub     rsp, 38h
0x1400a41ec  mov     rcx, cs:VmsIfrLog
0x1400a41f3  lea     rax, WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids
0x1400a41fa  mov     r9d, 27h ; '''
0x1400a4200  mov     [rsp+38h+var_18], rax
0x1400a4205  mov     dl, 4
0x1400a4207  lea     r8d, [r9-15h]
0x1400a420b  call    WPP_RECORDER_SF_
0x1400a4210  mov     cs:VmsIsUnloadForServicing, 1
0x1400a4217  call    VmsVmNicDestroyControlDevice
0x1400a421c  call    VmsProxyUnregister
0x1400a4221  cmp     cs:VmsPDSwitchCount, 0
0x1400a4228  jz      short loc_1400A422F
0x1400a422a  call    VmsUninitializePD
0x1400a422f  mov     rcx, cs:VmsProtocolHandle; NdisProtocolHandle
0x1400a4236  test    rcx, rcx
0x1400a4239  jz      short loc_1400A4252
0x1400a423b  call    cs:__imp_NdisDeregisterProtocolDriver
0x1400a4242  nop     dword ptr [rax+rax+00h]
0x1400a4247  mov     cs:VmsProtocolHandle, 0
0x1400a4252  mov     rcx, cs:VmsVswitchProtocolHandle; NdisProtocolHandle
0x1400a4259  test    rcx, rcx
0x1400a425c  jz      short loc_1400A4275
0x1400a425e  call    cs:__imp_NdisDeregisterProtocolDriver
0x1400a4265  nop     dword ptr [rax+rax+00h]
0x1400a426a  mov     cs:VmsVswitchProtocolHandle, 0
0x1400a4275  mov     rcx, cs:VmsVswitchFilterHandle; NdisFilterDriverHandle
0x1400a427c  test    rcx, rcx
0x1400a427f  jz      short loc_1400A4298
0x1400a4281  call    cs:__imp_NdisFDeregisterFilterDriver
0x1400a4288  nop     dword ptr [rax+rax+00h]
0x1400a428d  mov     cs:VmsVswitchFilterHandle, 0
0x1400a4298  mov     rcx, cs:VmsVswitchMiniportHandle; NdisMiniportDriverHandle
0x1400a429f  test    rcx, rcx
0x1400a42a2  jz      short loc_1400A42BB
0x1400a42a4  call    cs:__imp_NdisMDeregisterMiniportDriver
0x1400a42ab  nop     dword ptr [rax+rax+00h]
0x1400a42b0  mov     cs:VmsVswitchMiniportHandle, 0
0x1400a42bb  mov     rcx, cs:VmsCdCtlDeviceObjectInternal; DeviceObject
0x1400a42c2  call    cs:__imp_IoDeleteDevice
0x1400a42c9  nop     dword ptr [rax+rax+00h]
0x1400a42ce  mov     rcx, cs:VmsDriverObject
0x1400a42d5  mov     cs:VmsCdCtlDeviceObjectInternal, 0
0x1400a42e0  mov     rax, [rcx+30h]
0x1400a42e4  mov     qword ptr [rax+8], 0
0x1400a42ec  call    VmsDriverUnload
0x1400a42f1  add     rsp, 38h
0x1400a42f5  retn
```
