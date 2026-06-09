# SP_CONTROL::Remove(void)

- ea: `0x1400a3d48`
- end: `0x1400a3ee0`
- name: `?Remove@SP_CONTROL@@QEAAXXZ`
- size: `408`
- prototype: `void __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x140033590`
- `0x1400a1bd8`

## callees

- `0x1400a2050`
- `0x1400a3d48`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3e69`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3e97`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3e69`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3e97`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3eaf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3eaf`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a3ec0`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a3ec0`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3e5a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3e88`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3e5a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3e88`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3e0d`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3e30`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3e0d`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3e30`
- `ntoskrnl!PcwUnregister` at `0x1400a3d69`
- `ntoskrnl!PcwUnregister` at `0x1400a3d8c`
- `ntoskrnl!PcwUnregister` at `0x1400a3daf`
- `ntoskrnl!PcwUnregister` at `0x1400a3dd2`
- `ntoskrnl!PcwUnregister` at `0x1400a3d69`
- `ntoskrnl!PcwUnregister` at `0x1400a3d8c`
- `ntoskrnl!PcwUnregister` at `0x1400a3daf`
- `ntoskrnl!PcwUnregister` at `0x1400a3dd2`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400a3df5`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400a3df5`

## pseudocode

```c
void __fastcall SP_CONTROL::Remove(SP_CONTROL *this)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( SpDrtCounterSet )
  {
    PcwUnregister(SpDrtCounterSet);
    SpDrtCounterSet = 0;
  }
  if ( SpCacheCounterSet )
  {
    PcwUnregister(SpCacheCounterSet);
    SpCacheCounterSet = 0;
  }
  if ( SpTierCounterSet )
  {
    PcwUnregister(SpTierCounterSet);
    SpTierCounterSet = 0;
  }
  if ( SpSpaceCounterSet )
  {
    PcwUnregister(SpSpaceCounterSet);
    SpSpaceCounterSet = 0;
  }
  if ( (*(_DWORD *)(*(_QWORD *)this + 48LL) & 0x800) != 0 )
    IoUnregisterShutdownNotification(*(PDEVICE_OBJECT *)this);
  v2 = (void *)*((_QWORD *)this + 363);
  if ( v2 )
  {
    IoUnregisterPlugPlayNotification(v2);
    *((_QWORD *)this + 363) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 362);
  if ( v3 )
  {
    IoUnregisterPlugPlayNotification(v3);
    *((_QWORD *)this + 362) = 0;
  }
  if ( *((_QWORD *)this + 361) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)this + 180, 0);
    RtlFreeUnicodeString((PUNICODE_STRING)this + 180);
  }
  if ( *((_QWORD *)this + 359) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)this + 179, 0);
    RtlFreeUnicodeString((PUNICODE_STRING)this + 179);
  }
  RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\Spaceport");
  IoDeleteSymbolicLink(&DestinationString);
  SP_CONTROL::DiscardBootData(this);
}

```

## disassembly

```asm
0x1400a3d48  mov     [rsp+arg_0], rbx
0x1400a3d4d  push    rdi
0x1400a3d4e  sub     rsp, 30h
0x1400a3d52  mov     rbx, rcx
0x1400a3d55  xorps   xmm0, xmm0
0x1400a3d58  mov     rcx, cs:SpDrtCounterSet; Registration
0x1400a3d5f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400a3d64  test    rcx, rcx
0x1400a3d67  jz      short loc_1400A3D80
0x1400a3d69  call    cs:__imp_PcwUnregister
0x1400a3d70  nop     dword ptr [rax+rax+00h]
0x1400a3d75  mov     cs:SpDrtCounterSet, 0
0x1400a3d80  mov     rcx, cs:SpCacheCounterSet; Registration
0x1400a3d87  test    rcx, rcx
0x1400a3d8a  jz      short loc_1400A3DA3
0x1400a3d8c  call    cs:__imp_PcwUnregister
0x1400a3d93  nop     dword ptr [rax+rax+00h]
0x1400a3d98  mov     cs:SpCacheCounterSet, 0
0x1400a3da3  mov     rcx, cs:SpTierCounterSet; Registration
0x1400a3daa  test    rcx, rcx
0x1400a3dad  jz      short loc_1400A3DC6
0x1400a3daf  call    cs:__imp_PcwUnregister
0x1400a3db6  nop     dword ptr [rax+rax+00h]
0x1400a3dbb  mov     cs:SpTierCounterSet, 0
0x1400a3dc6  mov     rcx, cs:SpSpaceCounterSet; Registration
0x1400a3dcd  test    rcx, rcx
0x1400a3dd0  jz      short loc_1400A3DE9
0x1400a3dd2  call    cs:__imp_PcwUnregister
0x1400a3dd9  nop     dword ptr [rax+rax+00h]
0x1400a3dde  mov     cs:SpSpaceCounterSet, 0
0x1400a3de9  mov     rcx, [rbx]; DeviceObject
0x1400a3dec  test    dword ptr [rcx+30h], 800h
0x1400a3df3  jz      short loc_1400A3E01
0x1400a3df5  call    cs:__imp_IoUnregisterShutdownNotification
0x1400a3dfc  nop     dword ptr [rax+rax+00h]
0x1400a3e01  mov     rcx, [rbx+0B58h]; NotificationEntry
0x1400a3e08  test    rcx, rcx
0x1400a3e0b  jz      short loc_1400A3E24
0x1400a3e0d  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1400a3e14  nop     dword ptr [rax+rax+00h]
0x1400a3e19  mov     qword ptr [rbx+0B58h], 0
0x1400a3e24  mov     rcx, [rbx+0B50h]; NotificationEntry
0x1400a3e2b  test    rcx, rcx
0x1400a3e2e  jz      short loc_1400A3E47
0x1400a3e30  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1400a3e37  nop     dword ptr [rax+rax+00h]
0x1400a3e3c  mov     qword ptr [rbx+0B50h], 0
0x1400a3e47  lea     rdi, [rbx+0B40h]
0x1400a3e4e  cmp     qword ptr [rdi+8], 0
0x1400a3e53  jz      short loc_1400A3E75
0x1400a3e55  xor     edx, edx; Enable
0x1400a3e57  mov     rcx, rdi; SymbolicLinkName
0x1400a3e5a  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a3e61  nop     dword ptr [rax+rax+00h]
0x1400a3e66  mov     rcx, rdi; UnicodeString
0x1400a3e69  call    cs:__imp_RtlFreeUnicodeString
0x1400a3e70  nop     dword ptr [rax+rax+00h]
0x1400a3e75  lea     rdi, [rbx+0B30h]
0x1400a3e7c  cmp     qword ptr [rdi+8], 0
0x1400a3e81  jz      short loc_1400A3EA3
0x1400a3e83  xor     edx, edx; Enable
0x1400a3e85  mov     rcx, rdi; SymbolicLinkName
0x1400a3e88  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a3e8f  nop     dword ptr [rax+rax+00h]
0x1400a3e94  mov     rcx, rdi; UnicodeString
0x1400a3e97  call    cs:__imp_RtlFreeUnicodeString
0x1400a3e9e  nop     dword ptr [rax+rax+00h]
0x1400a3ea3  lea     rdx, aDosdevicesSpac; "\\DosDevices\\Spaceport"
0x1400a3eaa  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400a3eaf  call    cs:__imp_RtlInitUnicodeString
0x1400a3eb6  nop     dword ptr [rax+rax+00h]
0x1400a3ebb  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x1400a3ec0  call    cs:__imp_IoDeleteSymbolicLink
0x1400a3ec7  nop     dword ptr [rax+rax+00h]
0x1400a3ecc  mov     rcx, rbx; this
0x1400a3ecf  call    ?DiscardBootData@SP_CONTROL@@QEAAXXZ; SP_CONTROL::DiscardBootData(void)
0x1400a3ed4  mov     rbx, [rsp+38h+arg_0]
0x1400a3ed9  add     rsp, 30h
0x1400a3edd  pop     rdi
0x1400a3ede  retn
```
