# SrvNetDeregisterPnpCallbacks

- ea: `0x14001acb4`
- end: `0x14001adb5`
- name: `SrvNetDeregisterPnpCallbacks`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140053eb0`
- `0x140056be0`

## callees

- `0x14001acb4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001ad62`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ad85`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ad62`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ad85`
- `NETIO!NsiDeregisterChangeNotification` at `0x14001accd`
- `NETIO!NsiDeregisterChangeNotification` at `0x14001ad1c`
- `NETIO!NsiDeregisterChangeNotification` at `0x14001accd`
- `NETIO!NsiDeregisterChangeNotification` at `0x14001ad1c`
- `NETIO!CancelMibChangeNotify2` at `0x14001acf0`
- `NETIO!CancelMibChangeNotify2` at `0x14001ad3f`
- `NETIO!CancelMibChangeNotify2` at `0x14001acf0`
- `NETIO!CancelMibChangeNotify2` at `0x14001ad3f`

## pseudocode

```c
PERESOURCE SrvNetDeregisterPnpCallbacks()
{
  PERESOURCE result; // rax

  if ( SrvNetRdmaNotificationHandle )
  {
    NsiDeregisterChangeNotification(&NPI_MS_FLRDMA_MODULEID, 0);
    SrvNetRdmaNotificationHandle = 0;
  }
  if ( SrvNetUnicastIpAddressNotificationHandle )
  {
    CancelMibChangeNotify2(SrvNetUnicastIpAddressNotificationHandle);
    SrvNetUnicastIpAddressNotificationHandle = 0;
  }
  if ( SrvNetRssNotificationHandle )
  {
    NsiDeregisterChangeNotification(NPI_MS_RSS_MODULEID, 0);
    SrvNetRssNotificationHandle = 0;
  }
  if ( SrvNetIPInterfaceNotificationHandle )
  {
    CancelMibChangeNotify2(SrvNetIPInterfaceNotificationHandle);
    SrvNetIPInterfaceNotificationHandle = 0;
  }
  if ( SrvNetWmiLinkStatusDataBlock )
  {
    ObfDereferenceObject(SrvNetWmiLinkStatusDataBlock);
    SrvNetWmiLinkStatusDataBlock = 0;
  }
  if ( SrvNetWmiOperStatusDataBlock )
  {
    ObfDereferenceObject(SrvNetWmiOperStatusDataBlock);
    SrvNetWmiOperStatusDataBlock = 0;
  }
  result = SrvNetDeviceExtension;
  if ( SrvNetDeviceExtension )
    BYTE1(SrvNetDeviceExtension[8].SystemResourcesList.Flink) = 0;
  return result;
}

```

## disassembly

```asm
0x14001acb4  sub     rsp, 28h
0x14001acb8  mov     r8, cs:SrvNetRdmaNotificationHandle
0x14001acbf  test    r8, r8
0x14001acc2  jz      short loc_14001ACE4
0x14001acc4  xor     edx, edx
0x14001acc6  lea     rcx, NPI_MS_FLRDMA_MODULEID
0x14001accd  call    cs:__imp_NsiDeregisterChangeNotification
0x14001acd4  nop     dword ptr [rax+rax+00h]
0x14001acd9  mov     cs:SrvNetRdmaNotificationHandle, 0
0x14001ace4  mov     rcx, cs:SrvNetUnicastIpAddressNotificationHandle; NotificationHandle
0x14001aceb  test    rcx, rcx
0x14001acee  jz      short loc_14001AD07
0x14001acf0  call    cs:__imp_CancelMibChangeNotify2
0x14001acf7  nop     dword ptr [rax+rax+00h]
0x14001acfc  mov     cs:SrvNetUnicastIpAddressNotificationHandle, 0
0x14001ad07  mov     r8, cs:SrvNetRssNotificationHandle
0x14001ad0e  test    r8, r8
0x14001ad11  jz      short loc_14001AD33
0x14001ad13  xor     edx, edx
0x14001ad15  lea     rcx, NPI_MS_RSS_MODULEID
0x14001ad1c  call    cs:__imp_NsiDeregisterChangeNotification
0x14001ad23  nop     dword ptr [rax+rax+00h]
0x14001ad28  mov     cs:SrvNetRssNotificationHandle, 0
0x14001ad33  mov     rcx, cs:SrvNetIPInterfaceNotificationHandle; NotificationHandle
0x14001ad3a  test    rcx, rcx
0x14001ad3d  jz      short loc_14001AD56
0x14001ad3f  call    cs:__imp_CancelMibChangeNotify2
0x14001ad46  nop     dword ptr [rax+rax+00h]
0x14001ad4b  mov     cs:SrvNetIPInterfaceNotificationHandle, 0
0x14001ad56  mov     rcx, cs:SrvNetWmiLinkStatusDataBlock; Object
0x14001ad5d  test    rcx, rcx
0x14001ad60  jz      short loc_14001AD79
0x14001ad62  call    cs:__imp_ObfDereferenceObject
0x14001ad69  nop     dword ptr [rax+rax+00h]
0x14001ad6e  mov     cs:SrvNetWmiLinkStatusDataBlock, 0
0x14001ad79  mov     rcx, cs:SrvNetWmiOperStatusDataBlock; Object
0x14001ad80  test    rcx, rcx
0x14001ad83  jz      short loc_14001AD9C
0x14001ad85  call    cs:__imp_ObfDereferenceObject
0x14001ad8c  nop     dword ptr [rax+rax+00h]
0x14001ad91  mov     cs:SrvNetWmiOperStatusDataBlock, 0
0x14001ad9c  mov     rax, cs:SrvNetDeviceExtension
0x14001ada3  test    rax, rax
0x14001ada6  jz      short loc_14001ADAF
0x14001ada8  mov     byte ptr [rax+341h], 0
0x14001adaf  add     rsp, 28h
0x14001adb3  retn
```
