# RpcXdrDriverUnload

- ea: `0x140020640`
- end: `0x140020850`
- name: `RpcXdrDriverUnload`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting`

## callers

- `0x140024b80`

## callees

- `0x1400014d4`
- `0x1400020c0`
- `0x140003878`
- `0x14000a24c`
- `0x140010d50`
- `0x140011640`
- `0x140013044`
- `0x1400134d4`
- `0x1400201dc`
- `0x140020640`
- `0x140020858`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400206b4`
- `ntoskrnl!ZwClose` at `0x1400206b4`
- `ntoskrnl!KeSetEvent` at `0x14002067b`
- `ntoskrnl!KeSetEvent` at `0x14002067b`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002069a`
- `ntoskrnl!ZwWaitForSingleObject` at `0x14002069a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140020734`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140020734`
- `ntoskrnl!IoDeleteDevice` at `0x14002081b`
- `ntoskrnl!IoDeleteDevice` at `0x14002081b`
- `ntoskrnl!EtwUnregister` at `0x140020838`
- `ntoskrnl!EtwUnregister` at `0x140020838`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020708`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020708`
- `NETIO!WskDeregister` at `0x1400207bc`
- `NETIO!WskDeregister` at `0x1400207bc`

## pseudocode

```c
NTSTATUS __fastcall RpcXdrDriverUnload(__int64 a1)
{
  NTSTATUS v2; // eax
  _DWORD *v3; // rax
  void *v4; // rcx
  int v5; // eax
  NTSTATUS result; // eax

  if ( DeviceExtension )
  {
    if ( *((_QWORD *)DeviceExtension + 15) )
    {
      KeSetEvent((PRKEVENT)((char *)DeviceExtension + 160), 0, 0);
      ZwWaitForSingleObject(*((HANDLE *)DeviceExtension + 16), 0, 0);
      v2 = ZwClose(*((HANDLE *)DeviceExtension + 16));
      if ( v2 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
          (unsigned int)v2);
      }
    }
    v3 = DeviceExtension;
    v4 = (void *)*((_QWORD *)DeviceExtension + 27);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0x544C5444u);
      v3 = DeviceExtension;
      *((_QWORD *)DeviceExtension + 27) = 0;
    }
    if ( (v3[17] & 1) != 0 )
      IoDeleteSymbolicLink(&SymbolicLinkName);
    OncRpcDrcShutdown();
    if ( *((_QWORD *)DeviceExtension + 28) )
    {
      OncRpcConnMgrPnPShutdown();
      NfsResMgrResourceDeregister(1314407250);
      NfsResMgrResourceDeregister(1347177810);
      NfsResMgrResourceDeregister(1397313618);
      NfsResMgrResourceDeregister(1397116242);
      NfsResMgrResourceDeregister(1397771602);
      NfsResMgrResourceDeregister(1380864082);
    }
    OncRpcWiMgrShutdown(*((_QWORD *)DeviceExtension + 29));
    if ( (*((_DWORD *)DeviceExtension + 17) & 4) != 0 )
      WskDeregister((PWSK_REGISTRATION)DeviceExtension + 3);
    OncRpcSeShutdown();
    OncRpcMsgShutdown();
    OncRpcBufMgrShutdown();
    v5 = NfsResMgrShutdown((char *)DeviceExtension + 104);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids,
        (unsigned int)v5);
    }
    IoDeleteDevice(*(PDEVICE_OBJECT *)(a1 + 8));
  }
  result = WppCleanupKm();
  if ( RegHandle )
    return EtwUnregister(RegHandle);
  return result;
}

```

## disassembly

```asm
0x140020640  mov     [rsp+arg_0], rbx
0x140020645  push    rbp
0x140020646  sub     rsp, 20h
0x14002064a  mov     rbx, rcx
0x14002064d  mov     rcx, cs:DeviceExtension
0x140020654  test    rcx, rcx
0x140020657  jz      loc_140020827
0x14002065d  cmp     qword ptr [rcx+78h], 0
0x140020662  lea     rbp, WPP_GLOBAL_Control
0x140020669  jz      loc_1400206F0
0x14002066f  add     rcx, 0A0h; Event
0x140020676  xor     r8d, r8d; Wait
0x140020679  xor     edx, edx; Increment
0x14002067b  call    cs:__imp_KeSetEvent
0x140020682  nop     dword ptr [rax+rax+00h]
0x140020687  mov     rcx, cs:DeviceExtension
0x14002068e  xor     r8d, r8d; Timeout
0x140020691  xor     edx, edx; Alertable
0x140020693  mov     rcx, [rcx+80h]; Handle
0x14002069a  call    cs:__imp_ZwWaitForSingleObject
0x1400206a1  nop     dword ptr [rax+rax+00h]
0x1400206a6  mov     rcx, cs:DeviceExtension
0x1400206ad  mov     rcx, [rcx+80h]; Handle
0x1400206b4  call    cs:__imp_ZwClose
0x1400206bb  nop     dword ptr [rax+rax+00h]
0x1400206c0  test    eax, eax
0x1400206c2  jns     short loc_1400206F0
0x1400206c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206cb  cmp     rcx, rbp
0x1400206ce  jz      short loc_1400206F0
0x1400206d0  mov     edx, [rcx+2Ch]
0x1400206d3  test    dl, 1
0x1400206d6  jz      short loc_1400206F0
0x1400206d8  mov     rcx, [rcx+18h]
0x1400206dc  lea     r8, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids
0x1400206e3  mov     edx, 17h
0x1400206e8  mov     r9d, eax
0x1400206eb  call    WPP_SF_d
0x1400206f0  mov     rax, cs:DeviceExtension
0x1400206f7  mov     rcx, [rax+0D8h]; P
0x1400206fe  test    rcx, rcx
0x140020701  jz      short loc_140020726
0x140020703  mov     edx, 544C5444h; Tag
0x140020708  call    cs:__imp_ExFreePoolWithTag
0x14002070f  nop     dword ptr [rax+rax+00h]
0x140020714  mov     rax, cs:DeviceExtension
0x14002071b  mov     qword ptr [rax+0D8h], 0
0x140020726  mov     eax, [rax+44h]
0x140020729  test    al, 1
0x14002072b  jz      short loc_140020740
0x14002072d  lea     rcx, SymbolicLinkName; SymbolicLinkName
0x140020734  call    cs:__imp_IoDeleteSymbolicLink
0x14002073b  nop     dword ptr [rax+rax+00h]
0x140020740  call    OncRpcDrcShutdown
0x140020745  mov     rax, cs:DeviceExtension
0x14002074c  cmp     qword ptr [rax+0E0h], 0
0x140020754  jz      short loc_140020797
0x140020756  call    OncRpcConnMgrPnPShutdown
0x14002075b  mov     ecx, 4E584352h
0x140020760  call    NfsResMgrResourceDeregister
0x140020765  mov     ecx, 504C4D52h
0x14002076a  call    NfsResMgrResourceDeregister
0x14002076f  mov     ecx, 53495052h
0x140020774  call    NfsResMgrResourceDeregister
0x140020779  mov     ecx, 53464D52h
0x14002077e  call    NfsResMgrResourceDeregister
0x140020783  mov     ecx, 53504D52h
0x140020788  call    NfsResMgrResourceDeregister
0x14002078d  mov     ecx, 524E5052h
0x140020792  call    NfsResMgrResourceDeregister
0x140020797  mov     rcx, cs:DeviceExtension
0x14002079e  mov     rcx, [rcx+0E8h]
0x1400207a5  call    OncRpcWiMgrShutdown
0x1400207aa  mov     rcx, cs:DeviceExtension
0x1400207b1  mov     eax, [rcx+44h]
0x1400207b4  test    al, 4
0x1400207b6  jz      short loc_1400207C8
0x1400207b8  add     rcx, 48h ; 'H'; WskRegistration
0x1400207bc  call    cs:__imp_WskDeregister
0x1400207c3  nop     dword ptr [rax+rax+00h]
0x1400207c8  call    OncRpcSeShutdown
0x1400207cd  call    OncRpcMsgShutdown
0x1400207d2  call    OncRpcBufMgrShutdown
0x1400207d7  mov     rcx, cs:DeviceExtension
0x1400207de  add     rcx, 68h ; 'h'
0x1400207e2  call    NfsResMgrShutdown
0x1400207e7  test    eax, eax
0x1400207e9  jns     short loc_140020817
0x1400207eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207f2  cmp     rcx, rbp
0x1400207f5  jz      short loc_140020817
0x1400207f7  mov     edx, [rcx+2Ch]
0x1400207fa  test    dl, 1
0x1400207fd  jz      short loc_140020817
0x1400207ff  mov     rcx, [rcx+18h]
0x140020803  lea     r8, WPP_f76409a1276738e2972a6fdf7ba00470_Traceguids
0x14002080a  mov     edx, 18h
0x14002080f  mov     r9d, eax
0x140020812  call    WPP_SF_d
0x140020817  mov     rcx, [rbx+8]; DeviceObject
0x14002081b  call    cs:__imp_IoDeleteDevice
0x140020822  nop     dword ptr [rax+rax+00h]
0x140020827  call    WppCleanupKm
0x14002082c  mov     rcx, cs:RegHandle; RegHandle
0x140020833  test    rcx, rcx
0x140020836  jz      short loc_140020844
0x140020838  call    cs:__imp_EtwUnregister
0x14002083f  nop     dword ptr [rax+rax+00h]
0x140020844  mov     rbx, [rsp+28h+arg_0]
0x140020849  add     rsp, 20h
0x14002084d  pop     rbp
0x14002084e  retn
```
