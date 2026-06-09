# SP_CONTROL::Remove(void)

- ea: `0x1400a3e78`
- end: `0x1400a4010`
- name: `?Remove@SP_CONTROL@@QEAAXXZ`
- size: `408`
- prototype: `void __fastcall(SP_CONTROL *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x140033640`
- `0x1400a1d08`

## callees

- `0x1400a2180`
- `0x1400a3e78`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3f99`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3fc7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3f99`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a3fc7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3fdf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a3fdf`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a3ff0`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400a3ff0`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3f8a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3fb8`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3f8a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400a3fb8`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3f3d`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3f60`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3f3d`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1400a3f60`
- `ntoskrnl!PcwUnregister` at `0x1400a3e99`
- `ntoskrnl!PcwUnregister` at `0x1400a3ebc`
- `ntoskrnl!PcwUnregister` at `0x1400a3edf`
- `ntoskrnl!PcwUnregister` at `0x1400a3f02`
- `ntoskrnl!PcwUnregister` at `0x1400a3e99`
- `ntoskrnl!PcwUnregister` at `0x1400a3ebc`
- `ntoskrnl!PcwUnregister` at `0x1400a3edf`
- `ntoskrnl!PcwUnregister` at `0x1400a3f02`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400a3f25`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400a3f25`

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
0x1400a3e78  mov     [rsp+arg_0], rbx
0x1400a3e7d  push    rdi
0x1400a3e7e  sub     rsp, 30h
0x1400a3e82  mov     rbx, rcx
0x1400a3e85  xorps   xmm0, xmm0
0x1400a3e88  mov     rcx, cs:SpDrtCounterSet; Registration
0x1400a3e8f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400a3e94  test    rcx, rcx
0x1400a3e97  jz      short loc_1400A3EB0
0x1400a3e99  call    cs:__imp_PcwUnregister
0x1400a3ea0  nop     dword ptr [rax+rax+00h]
0x1400a3ea5  mov     cs:SpDrtCounterSet, 0
0x1400a3eb0  mov     rcx, cs:SpCacheCounterSet; Registration
0x1400a3eb7  test    rcx, rcx
0x1400a3eba  jz      short loc_1400A3ED3
0x1400a3ebc  call    cs:__imp_PcwUnregister
0x1400a3ec3  nop     dword ptr [rax+rax+00h]
0x1400a3ec8  mov     cs:SpCacheCounterSet, 0
0x1400a3ed3  mov     rcx, cs:SpTierCounterSet; Registration
0x1400a3eda  test    rcx, rcx
0x1400a3edd  jz      short loc_1400A3EF6
0x1400a3edf  call    cs:__imp_PcwUnregister
0x1400a3ee6  nop     dword ptr [rax+rax+00h]
0x1400a3eeb  mov     cs:SpTierCounterSet, 0
0x1400a3ef6  mov     rcx, cs:SpSpaceCounterSet; Registration
0x1400a3efd  test    rcx, rcx
0x1400a3f00  jz      short loc_1400A3F19
0x1400a3f02  call    cs:__imp_PcwUnregister
0x1400a3f09  nop     dword ptr [rax+rax+00h]
0x1400a3f0e  mov     cs:SpSpaceCounterSet, 0
0x1400a3f19  mov     rcx, [rbx]; DeviceObject
0x1400a3f1c  test    dword ptr [rcx+30h], 800h
0x1400a3f23  jz      short loc_1400A3F31
0x1400a3f25  call    cs:__imp_IoUnregisterShutdownNotification
0x1400a3f2c  nop     dword ptr [rax+rax+00h]
0x1400a3f31  mov     rcx, [rbx+0B58h]; NotificationEntry
0x1400a3f38  test    rcx, rcx
0x1400a3f3b  jz      short loc_1400A3F54
0x1400a3f3d  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1400a3f44  nop     dword ptr [rax+rax+00h]
0x1400a3f49  mov     qword ptr [rbx+0B58h], 0
0x1400a3f54  mov     rcx, [rbx+0B50h]; NotificationEntry
0x1400a3f5b  test    rcx, rcx
0x1400a3f5e  jz      short loc_1400A3F77
0x1400a3f60  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1400a3f67  nop     dword ptr [rax+rax+00h]
0x1400a3f6c  mov     qword ptr [rbx+0B50h], 0
0x1400a3f77  lea     rdi, [rbx+0B40h]
0x1400a3f7e  cmp     qword ptr [rdi+8], 0
0x1400a3f83  jz      short loc_1400A3FA5
0x1400a3f85  xor     edx, edx; Enable
0x1400a3f87  mov     rcx, rdi; SymbolicLinkName
0x1400a3f8a  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a3f91  nop     dword ptr [rax+rax+00h]
0x1400a3f96  mov     rcx, rdi; UnicodeString
0x1400a3f99  call    cs:__imp_RtlFreeUnicodeString
0x1400a3fa0  nop     dword ptr [rax+rax+00h]
0x1400a3fa5  lea     rdi, [rbx+0B30h]
0x1400a3fac  cmp     qword ptr [rdi+8], 0
0x1400a3fb1  jz      short loc_1400A3FD3
0x1400a3fb3  xor     edx, edx; Enable
0x1400a3fb5  mov     rcx, rdi; SymbolicLinkName
0x1400a3fb8  call    cs:__imp_IoSetDeviceInterfaceState
0x1400a3fbf  nop     dword ptr [rax+rax+00h]
0x1400a3fc4  mov     rcx, rdi; UnicodeString
0x1400a3fc7  call    cs:__imp_RtlFreeUnicodeString
0x1400a3fce  nop     dword ptr [rax+rax+00h]
0x1400a3fd3  lea     rdx, aDosdevicesSpac; "\\DosDevices\\Spaceport"
0x1400a3fda  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400a3fdf  call    cs:__imp_RtlInitUnicodeString
0x1400a3fe6  nop     dword ptr [rax+rax+00h]
0x1400a3feb  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x1400a3ff0  call    cs:__imp_IoDeleteSymbolicLink
0x1400a3ff7  nop     dword ptr [rax+rax+00h]
0x1400a3ffc  mov     rcx, rbx; this
0x1400a3fff  call    ?DiscardBootData@SP_CONTROL@@QEAAXXZ; SP_CONTROL::DiscardBootData(void)
0x1400a4004  mov     rbx, [rsp+38h+arg_0]
0x1400a4009  add     rsp, 30h
0x1400a400d  pop     rdi
0x1400a400e  retn
```
