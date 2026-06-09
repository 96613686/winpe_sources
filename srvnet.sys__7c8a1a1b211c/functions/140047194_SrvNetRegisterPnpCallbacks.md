# SrvNetRegisterPnpCallbacks

- ea: `0x140047194`
- end: `0x140047591`
- name: `SrvNetRegisterPnpCallbacks`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140053eb0`

## callees

- `0x14001389c`
- `0x140047194`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004744a`
- `ntoskrnl!ObfDereferenceObject` at `0x140047534`
- `ntoskrnl!ObfDereferenceObject` at `0x14004744a`
- `ntoskrnl!ObfDereferenceObject` at `0x140047534`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400473cc`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400474ba`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400473cc`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400474ba`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400473f3`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400474dd`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400473f3`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400474dd`
- `NETIO!NotifyUnicastIpAddressChange` at `0x14004724e`
- `NETIO!NotifyUnicastIpAddressChange` at `0x14004724e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400472d6`
- `NETIO!NsiRegisterChangeNotification` at `0x14004731e`
- `NETIO!NsiRegisterChangeNotification` at `0x1400472d6`
- `NETIO!NsiRegisterChangeNotification` at `0x14004731e`
- `NETIO!NotifyIpInterfaceChange` at `0x1400471cf`
- `NETIO!NotifyIpInterfaceChange` at `0x1400471cf`

## pseudocode

```c
__int64 __fastcall SrvNetRegisterPnpCallbacks(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS v4; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx

  v4 = 0;
  if ( !SrvNetUseTdiNotifications && !SrvNetIPInterfaceNotificationHandle )
  {
    v4 = NotifyIpInterfaceChange(0, SrvNetIPInterfaceNotificationHandler, 0, 1u, &SrvNetIPInterfaceNotificationHandle);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
          (unsigned int)v4);
      }
      return (unsigned int)v4;
    }
  }
  if ( !SrvNetUnicastIpAddressNotificationHandle )
  {
    v4 = NotifyUnicastIpAddressChange(
           0,
           SrvNetUnicastIPAddressNotificationHandler,
           0,
           1u,
           &SrvNetUnicastIpAddressNotificationHandle);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)v4;
      }
      v6 = 11;
      goto LABEL_53;
    }
  }
  if ( SrvNetIsSMBDirectSupported && !SrvNetRdmaNotificationHandle )
  {
    LOBYTE(a4) = 1;
    v4 = NsiRegisterChangeNotification(
           &NPI_MS_FLRDMA_MODULEID,
           0,
           SrvNetRdmaNotificationHandler,
           a4,
           0,
           &SrvNetRdmaNotificationHandle);
    if ( v4 == -1073741637 )
    {
      v4 = 0;
    }
    else if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)v4;
      }
      v6 = 12;
LABEL_53:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids, (unsigned int)v4);
      return (unsigned int)v4;
    }
  }
  if ( !SrvNetRssNotificationHandle )
  {
    LOBYTE(a4) = 1;
    v4 = NsiRegisterChangeNotification(
           NPI_MS_RSS_MODULEID,
           0,
           SrvNetRssNotificationHandler,
           a4,
           0,
           &SrvNetRssNotificationHandle);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return (unsigned int)v4;
      }
      v6 = 13;
      goto LABEL_53;
    }
  }
  if ( SrvNetWmiLinkStatusDataBlock )
    goto LABEL_41;
  v4 = IoWMIOpenBlock(&GUID_NDIS_STATUS_LINK_STATE, 4u, &SrvNetWmiLinkStatusDataBlock);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return (unsigned int)v4;
    }
    v6 = 15;
    goto LABEL_53;
  }
  v4 = IoWMISetNotificationCallback(
         SrvNetWmiLinkStatusDataBlock,
         (WMI_NOTIFICATION_CALLBACK)SrvNetWmiLinkStateNotificationHandler,
         0);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
        (unsigned int)v4);
    }
    ObfDereferenceObject(SrvNetWmiLinkStatusDataBlock);
    SrvNetWmiLinkStatusDataBlock = 0;
    return (unsigned int)v4;
  }
LABEL_41:
  if ( SrvNetWmiOperStatusDataBlock )
    return (unsigned int)v4;
  v4 = IoWMIOpenBlock(&GUID_NDIS_STATUS_OPER_STATUS, 4u, &SrvNetWmiOperStatusDataBlock);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return (unsigned int)v4;
    }
    v6 = 17;
    goto LABEL_53;
  }
  v4 = IoWMISetNotificationCallback(
         SrvNetWmiOperStatusDataBlock,
         (WMI_NOTIFICATION_CALLBACK)SrvNetWmiOperStateNotificationHandler,
         0);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
        (unsigned int)v4);
    }
    ObfDereferenceObject(SrvNetWmiOperStatusDataBlock);
    SrvNetWmiOperStatusDataBlock = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140047194  mov     [rsp+arg_0], rbx
0x140047199  push    rdi
0x14004719a  sub     rsp, 30h
0x14004719e  xor     edi, edi
0x1400471a0  cmp     cs:SrvNetUseTdiNotifications, dil
0x1400471a7  mov     ebx, edi
0x1400471a9  jnz     short loc_14004722A
0x1400471ab  cmp     cs:SrvNetIPInterfaceNotificationHandle, rdi
0x1400471b2  jnz     short loc_14004722A
0x1400471b4  lea     rax, SrvNetIPInterfaceNotificationHandle
0x1400471bb  xor     ecx, ecx; Family
0x1400471bd  mov     r9b, 1; InitialNotification
0x1400471c0  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x1400471c5  xor     r8d, r8d; CallerContext
0x1400471c8  lea     rdx, SrvNetIPInterfaceNotificationHandler; Callback
0x1400471cf  call    cs:__imp_NotifyIpInterfaceChange
0x1400471d6  nop     dword ptr [rax+rax+00h]
0x1400471db  mov     ebx, eax
0x1400471dd  test    eax, eax
0x1400471df  jns     short loc_14004722A
0x1400471e1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400471e8  lea     rax, WPP_GLOBAL_Control
0x1400471ef  cmp     rcx, rax
0x1400471f2  jz      loc_140047583
0x1400471f8  test    dword ptr [rcx+2Ch], 2000h
0x1400471ff  jz      loc_140047583
0x140047205  cmp     byte ptr [rcx+29h], 1
0x140047209  jb      loc_140047583
0x14004720f  mov     rcx, [rcx+18h]
0x140047213  lea     edx, [rdi+0Ah]
0x140047216  mov     r9d, ebx
0x140047219  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140047220  call    WPP_SF_d
0x140047225  jmp     loc_140047583
0x14004722a  cmp     cs:SrvNetUnicastIpAddressNotificationHandle, rdi
0x140047231  jnz     short loc_140047298
0x140047233  lea     rax, SrvNetUnicastIpAddressNotificationHandle
0x14004723a  xor     ecx, ecx; Family
0x14004723c  mov     r9b, 1; InitialNotification
0x14004723f  mov     [rsp+38h+NotificationHandle], rax; NotificationHandle
0x140047244  xor     r8d, r8d; CallerContext
0x140047247  lea     rdx, SrvNetUnicastIPAddressNotificationHandler; Callback
0x14004724e  call    cs:__imp_NotifyUnicastIpAddressChange
0x140047255  nop     dword ptr [rax+rax+00h]
0x14004725a  mov     ebx, eax
0x14004725c  test    eax, eax
0x14004725e  jns     short loc_1400472A0
0x140047260  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047267  lea     rax, WPP_GLOBAL_Control
0x14004726e  cmp     rcx, rax
0x140047271  jz      loc_140047583
0x140047277  test    dword ptr [rcx+2Ch], 80000h
0x14004727e  jz      loc_140047583
0x140047284  cmp     byte ptr [rcx+29h], 1
0x140047288  jb      loc_140047583
0x14004728e  mov     edx, 0Bh
0x140047293  jmp     loc_140047570
0x140047298  test    ebx, ebx
0x14004729a  js      loc_140047583
0x1400472a0  cmp     cs:SrvNetIsSMBDirectSupported, dil
0x1400472a7  jz      short loc_1400472ED
0x1400472a9  cmp     cs:SrvNetRdmaNotificationHandle, rdi
0x1400472b0  jnz     short loc_1400472ED
0x1400472b2  lea     rax, SrvNetRdmaNotificationHandle
0x1400472b9  mov     r9b, 1
0x1400472bc  mov     [rsp+38h+var_10], rax
0x1400472c1  lea     r8, SrvNetRdmaNotificationHandler
0x1400472c8  xor     edx, edx
0x1400472ca  mov     [rsp+38h+NotificationHandle], rdi
0x1400472cf  lea     rcx, NPI_MS_FLRDMA_MODULEID
0x1400472d6  call    cs:__imp_NsiRegisterChangeNotification
0x1400472dd  nop     dword ptr [rax+rax+00h]
0x1400472e2  mov     ebx, eax
0x1400472e4  cmp     eax, 0C00000BBh
0x1400472e9  jnz     short loc_140047368
0x1400472eb  mov     ebx, edi
0x1400472ed  cmp     cs:SrvNetRssNotificationHandle, rdi
0x1400472f4  jnz     loc_1400473A4
0x1400472fa  lea     rax, SrvNetRssNotificationHandle
0x140047301  mov     r9b, 1
0x140047304  mov     [rsp+38h+var_10], rax
0x140047309  lea     r8, SrvNetRssNotificationHandler
0x140047310  xor     edx, edx
0x140047312  mov     [rsp+38h+NotificationHandle], rdi
0x140047317  lea     rcx, NPI_MS_RSS_MODULEID
0x14004731e  call    cs:__imp_NsiRegisterChangeNotification
0x140047325  nop     dword ptr [rax+rax+00h]
0x14004732a  mov     ebx, eax
0x14004732c  test    eax, eax
0x14004732e  jns     short loc_1400473AC
0x140047330  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047337  lea     rax, WPP_GLOBAL_Control
0x14004733e  cmp     rcx, rax
0x140047341  jz      loc_140047583
0x140047347  test    dword ptr [rcx+2Ch], 2000h
0x14004734e  jz      loc_140047583
0x140047354  cmp     byte ptr [rcx+29h], 1
0x140047358  jb      loc_140047583
0x14004735e  mov     edx, 0Dh
0x140047363  jmp     loc_140047570
0x140047368  test    ebx, ebx
0x14004736a  jns     short loc_1400472ED
0x14004736c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047373  lea     rax, WPP_GLOBAL_Control
0x14004737a  cmp     rcx, rax
0x14004737d  jz      loc_140047583
0x140047383  test    dword ptr [rcx+2Ch], 80000h
0x14004738a  jz      loc_140047583
0x140047390  cmp     byte ptr [rcx+29h], 1
0x140047394  jb      loc_140047583
0x14004739a  mov     edx, 0Ch
0x14004739f  jmp     loc_140047570
0x1400473a4  test    ebx, ebx
0x1400473a6  js      loc_140047583
0x1400473ac  cmp     cs:SrvNetWmiLinkStatusDataBlock, rdi
0x1400473b3  jnz     loc_14004749A
0x1400473b9  lea     r8, SrvNetWmiLinkStatusDataBlock; DataBlockObject
0x1400473c0  mov     edx, 4; DesiredAccess
0x1400473c5  lea     rcx, GUID_NDIS_STATUS_LINK_STATE; Guid
0x1400473cc  call    cs:__imp_IoWMIOpenBlock
0x1400473d3  nop     dword ptr [rax+rax+00h]
0x1400473d8  mov     ebx, eax
0x1400473da  test    eax, eax
0x1400473dc  js      loc_140047462
0x1400473e2  mov     rcx, cs:SrvNetWmiLinkStatusDataBlock; Object
0x1400473e9  lea     rdx, SrvNetWmiLinkStateNotificationHandler; Callback
0x1400473f0  xor     r8d, r8d; Context
0x1400473f3  call    cs:__imp_IoWMISetNotificationCallback
0x1400473fa  nop     dword ptr [rax+rax+00h]
0x1400473ff  mov     ebx, eax
0x140047401  test    eax, eax
0x140047403  jns     loc_14004749A
0x140047409  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047410  lea     rax, WPP_GLOBAL_Control
0x140047417  cmp     rcx, rax
0x14004741a  jz      short loc_140047443
0x14004741c  test    dword ptr [rcx+2Ch], 2000h
0x140047423  jz      short loc_140047443
0x140047425  cmp     byte ptr [rcx+29h], 1
0x140047429  jb      short loc_140047443
0x14004742b  mov     rcx, [rcx+18h]
0x14004742f  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140047436  mov     edx, 0Eh
0x14004743b  mov     r9d, ebx
0x14004743e  call    WPP_SF_d
0x140047443  mov     rcx, cs:SrvNetWmiLinkStatusDataBlock; Object
0x14004744a  call    cs:__imp_ObfDereferenceObject
0x140047451  nop     dword ptr [rax+rax+00h]
0x140047456  mov     cs:SrvNetWmiLinkStatusDataBlock, rdi
0x14004745d  jmp     loc_140047583
0x140047462  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047469  lea     rax, WPP_GLOBAL_Control
0x140047470  cmp     rcx, rax
0x140047473  jz      loc_140047583
0x140047479  test    dword ptr [rcx+2Ch], 2000h
0x140047480  jz      loc_140047583
0x140047486  cmp     byte ptr [rcx+29h], 1
0x14004748a  jb      loc_140047583
0x140047490  mov     edx, 0Fh
0x140047495  jmp     loc_140047570
0x14004749a  cmp     cs:SrvNetWmiOperStatusDataBlock, rdi
0x1400474a1  jnz     loc_140047583
0x1400474a7  lea     r8, SrvNetWmiOperStatusDataBlock; DataBlockObject
0x1400474ae  mov     edx, 4; DesiredAccess
0x1400474b3  lea     rcx, GUID_NDIS_STATUS_OPER_STATUS; Guid
0x1400474ba  call    cs:__imp_IoWMIOpenBlock
0x1400474c1  nop     dword ptr [rax+rax+00h]
0x1400474c6  mov     ebx, eax
0x1400474c8  test    eax, eax
0x1400474ca  js      short loc_140047549
0x1400474cc  mov     rcx, cs:SrvNetWmiOperStatusDataBlock; Object
0x1400474d3  lea     rdx, SrvNetWmiOperStateNotificationHandler; Callback
0x1400474da  xor     r8d, r8d; Context
0x1400474dd  call    cs:__imp_IoWMISetNotificationCallback
0x1400474e4  nop     dword ptr [rax+rax+00h]
0x1400474e9  mov     ebx, eax
0x1400474eb  test    eax, eax
0x1400474ed  jns     loc_140047583
0x1400474f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400474fa  lea     rax, WPP_GLOBAL_Control
0x140047501  cmp     rcx, rax
0x140047504  jz      short loc_14004752D
0x140047506  test    dword ptr [rcx+2Ch], 2000h
0x14004750d  jz      short loc_14004752D
0x14004750f  cmp     byte ptr [rcx+29h], 1
0x140047513  jb      short loc_14004752D
0x140047515  mov     rcx, [rcx+18h]
0x140047519  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140047520  mov     edx, 10h
0x140047525  mov     r9d, ebx
0x140047528  call    WPP_SF_d
0x14004752d  mov     rcx, cs:SrvNetWmiOperStatusDataBlock; Object
0x140047534  call    cs:__imp_ObfDereferenceObject
0x14004753b  nop     dword ptr [rax+rax+00h]
0x140047540  mov     cs:SrvNetWmiOperStatusDataBlock, rdi
0x140047547  jmp     short loc_140047583
0x140047549  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047550  lea     rax, WPP_GLOBAL_Control
0x140047557  cmp     rcx, rax
0x14004755a  jz      short loc_140047583
0x14004755c  test    dword ptr [rcx+2Ch], 2000h
0x140047563  jz      short loc_140047583
0x140047565  cmp     byte ptr [rcx+29h], 1
0x140047569  jb      short loc_140047583
0x14004756b  mov     edx, 11h
0x140047570  mov     rcx, [rcx+18h]
0x140047574  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x14004757b  mov     r9d, ebx
0x14004757e  call    WPP_SF_d
0x140047583  mov     eax, ebx
0x140047585  mov     rbx, [rsp+38h+arg_0]
0x14004758a  add     rsp, 30h
0x14004758e  pop     rdi
0x14004758f  retn
```
