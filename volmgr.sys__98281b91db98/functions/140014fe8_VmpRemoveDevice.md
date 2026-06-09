# VmpRemoveDevice

- ea: `0x140014fe8`
- end: `0x140015150`
- name: `VmpRemoveDevice`
- size: `360`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x140016aa0`
- `0x140018078`
- `0x140018298`

## callees

- `0x140014fe8`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400150df`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1400150df`
- `ntoskrnl!IoDetachDevice` at `0x14001511a`
- `ntoskrnl!IoDetachDevice` at `0x14001511a`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001500e`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x14001500e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140015091`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400150f9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140015091`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400150f9`
- `ntoskrnl!IoDeleteDevice` at `0x140015138`
- `ntoskrnl!IoDeleteDevice` at `0x140015138`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400150bc`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400150bc`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400150a9`
- `ntoskrnl!IoUnregisterShutdownNotification` at `0x1400150a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001503d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001506c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001503d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001506c`

## pseudocode

```c
void __fastcall VmpRemoveDevice(PDEVICE_OBJECT DeviceObject, char a2)
{
  struct _UNICODE_STRING *v4; // rcx
  struct _DEVICE_OBJECT *v5; // rcx

  v4 = (struct _UNICODE_STRING *)VmRootExtension;
  if ( *((_QWORD *)VmRootExtension + 47) )
  {
    IoUnregisterPlugPlayNotification(*((PVOID *)VmRootExtension + 47));
    v4 = (struct _UNICODE_STRING *)VmRootExtension;
    *((_QWORD *)VmRootExtension + 47) = 0;
  }
  if ( v4[22].Buffer )
  {
    ExFreePoolWithTag(v4[22].Buffer, 0);
    v4 = (struct _UNICODE_STRING *)VmRootExtension;
    *((_QWORD *)VmRootExtension + 45) = 0;
  }
  if ( v4[21].Buffer )
  {
    ExFreePoolWithTag(v4[21].Buffer, 0);
    v4 = (struct _UNICODE_STRING *)VmRootExtension;
    *((_QWORD *)VmRootExtension + 43) = 0;
  }
  RtlFreeUnicodeString(v4 + 18);
  if ( (DeviceObject->Flags & 0x800) != 0 )
    IoUnregisterShutdownNotification(DeviceObject);
  IoDeleteSymbolicLink((PUNICODE_STRING)&stru_140007020);
  if ( *((_QWORD *)VmRootExtension + 22) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)VmRootExtension + 168), 0);
    RtlFreeUnicodeString((PUNICODE_STRING)((char *)VmRootExtension + 168));
  }
  if ( a2 )
  {
    v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)VmRootExtension + 5);
    if ( v5 )
    {
      IoDetachDevice(v5);
      *((_QWORD *)VmRootExtension + 5) = 0;
    }
    IoDeleteDevice(DeviceObject);
  }
}

```

## disassembly

```asm
0x140014fe8  mov     [rsp+arg_0], rbx
0x140014fed  push    rdi
0x140014fee  sub     rsp, 20h
0x140014ff2  mov     rbx, rcx
0x140014ff5  mov     dil, dl
0x140014ff8  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140014fff  mov     rax, [rcx+178h]
0x140015006  test    rax, rax
0x140015009  jz      short loc_14001502C
0x14001500b  mov     rcx, rax; NotificationEntry
0x14001500e  call    cs:__imp_IoUnregisterPlugPlayNotification
0x140015015  nop     dword ptr [rax+rax+00h]
0x14001501a  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140015021  mov     qword ptr [rcx+178h], 0
0x14001502c  mov     rax, [rcx+168h]
0x140015033  test    rax, rax
0x140015036  jz      short loc_14001505B
0x140015038  xor     edx, edx; Tag
0x14001503a  mov     rcx, rax; P
0x14001503d  call    cs:__imp_ExFreePoolWithTag
0x140015044  nop     dword ptr [rax+rax+00h]
0x140015049  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140015050  mov     qword ptr [rcx+168h], 0
0x14001505b  mov     rax, [rcx+158h]
0x140015062  test    rax, rax
0x140015065  jz      short loc_14001508A
0x140015067  xor     edx, edx; Tag
0x140015069  mov     rcx, rax; P
0x14001506c  call    cs:__imp_ExFreePoolWithTag
0x140015073  nop     dword ptr [rax+rax+00h]
0x140015078  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001507f  mov     qword ptr [rcx+158h], 0
0x14001508a  add     rcx, 120h; UnicodeString
0x140015091  call    cs:__imp_RtlFreeUnicodeString
0x140015098  nop     dword ptr [rax+rax+00h]
0x14001509d  mov     eax, [rbx+30h]
0x1400150a0  bt      eax, 0Bh
0x1400150a4  jnb     short loc_1400150B5
0x1400150a6  mov     rcx, rbx; DeviceObject
0x1400150a9  call    cs:__imp_IoUnregisterShutdownNotification
0x1400150b0  nop     dword ptr [rax+rax+00h]
0x1400150b5  lea     rcx, stru_140007020; SymbolicLinkName
0x1400150bc  call    cs:__imp_IoDeleteSymbolicLink
0x1400150c3  nop     dword ptr [rax+rax+00h]
0x1400150c8  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400150cf  add     rcx, 0A8h; SymbolicLinkName
0x1400150d6  cmp     qword ptr [rcx+8], 0
0x1400150db  jz      short loc_140015105
0x1400150dd  xor     edx, edx; Enable
0x1400150df  call    cs:__imp_IoSetDeviceInterfaceState
0x1400150e6  nop     dword ptr [rax+rax+00h]
0x1400150eb  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400150f2  add     rcx, 0A8h; UnicodeString
0x1400150f9  call    cs:__imp_RtlFreeUnicodeString
0x140015100  nop     dword ptr [rax+rax+00h]
0x140015105  test    dil, dil
0x140015108  jz      short loc_140015144
0x14001510a  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140015111  mov     rcx, [rax+28h]; TargetDevice
0x140015115  test    rcx, rcx
0x140015118  jz      short loc_140015135
0x14001511a  call    cs:__imp_IoDetachDevice
0x140015121  nop     dword ptr [rax+rax+00h]
0x140015126  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001512d  mov     qword ptr [rax+28h], 0
0x140015135  mov     rcx, rbx; DeviceObject
0x140015138  call    cs:__imp_IoDeleteDevice
0x14001513f  nop     dword ptr [rax+rax+00h]
0x140015144  mov     rbx, [rsp+28h+arg_0]
0x140015149  add     rsp, 20h
0x14001514d  pop     rdi
0x14001514e  retn
```
