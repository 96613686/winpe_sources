# VhdmpCreateControlObject(ushort const *,ushort const *,ushort const *,_GUID const *,_DEVICE_OBJECT * *)

- ea: `0x1400b71a0`
- end: `0x1400b737a`
- name: `?VhdmpCreateControlObject@@YAJPEBG00PEBU_GUID@@PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400b8410`

## callees

- `0x140026a00`
- `0x14004914c`
- `0x14005d840`
- `0x14005dd00`
- `0x1400afc1c`
- `0x1400b71a0`
- `0x1400b7658`
- `0x1400cc9b0`
- `0x1400d3a68`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b72de`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b72de`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400b72f2`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400b72f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7202`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7219`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7202`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7219`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7337`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7337`

## pseudocode

```c
__int64 __fastcall VhdmpCreateControlObject(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        struct _DEVICE_OBJECT **a5)
{
  PDRIVER_OBJECT v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  _QWORD *DeviceExtension; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING v13; // [rsp+70h] [rbp-10h] BYREF
  PVOID P; // [rsp+A0h] [rbp+20h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+A8h] [rbp+28h] BYREF

  DeviceObject = 0;
  P = 0;
  DestinationString = 0;
  v13 = 0;
  SymbolicLinkName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\VHDMP");
  RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\VHDMP");
  RtlInitUnicodeString(
    &v13,
    L"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)(A;;GA;;;S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-1"
     "04643441-2915960892-1612460704)");
  v5 = VhdmpDriverObject;
  if ( !WdmlibInitialized )
    WdmlibInit();
  v8 = ((__int64 (__fastcall *)(PDRIVER_OBJECT, __int64, struct _UNICODE_STRING *, __int64, int, _BYTE, struct _UNICODE_STRING *, GUID *, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
         v5,
         408,
         &DestinationString,
         83,
         256,
         0,
         &v13,
         &GUID_VHDMP_CONTROL_OBJECT,
         &DeviceObject);
  if ( v8 >= 0 )
  {
    v8 = VhdmpiCreateNonGenericSecurityDescriptorFromSddlString(v7, v6, &P);
    if ( v8 >= 0 )
    {
      v8 = VhdmpiSetDeviceSecurity(DeviceObject, P);
      if ( v8 >= 0 )
      {
        DeviceObject->Flags |= 0x10u;
        DeviceExtension = DeviceObject->DeviceExtension;
        memset(DeviceExtension, 0, 0x198u);
        *DeviceExtension = DeviceObject;
        IoDeleteSymbolicLink(&SymbolicLinkName);
        v8 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
        if ( v8 >= 0 )
        {
          v8 = VhdmpiInitializeIoctlQueue(DeviceExtension);
          if ( v8 >= 0 )
          {
            DeviceExtension[23] = DeviceExtension + 22;
            DeviceExtension[22] = DeviceExtension + 22;
            VhdmpiInitializePassiveLock(DeviceExtension + 24);
          }
        }
      }
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v8 >= 0 )
  {
    *a5 = DeviceObject;
  }
  else if ( DeviceObject )
  {
    VhdmpiDeleteControlDevice(DeviceObject);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b71a0  mov     rax, rsp
0x1400b71a3  mov     [rax+8], rbx
0x1400b71a7  mov     [rax+10h], rdi
0x1400b71ab  mov     [rax+20h], r9
0x1400b71af  mov     [rax+18h], r8
0x1400b71b3  push    rbp
0x1400b71b4  mov     rbp, rsp
0x1400b71b7  sub     rsp, 80h
0x1400b71be  xorps   xmm0, xmm0
0x1400b71c1  mov     [rbp+DeviceObject], 0
0x1400b71c9  xorps   xmm1, xmm1
0x1400b71cc  mov     [rbp+P], 0
0x1400b71d4  lea     rdx, aDeviceVhdmp; "\\Device\\VHDMP"
0x1400b71db  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400b71df  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400b71e3  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1400b71e7  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm0
0x1400b71eb  call    cs:__imp_RtlInitUnicodeString
0x1400b71f2  nop     dword ptr [rax+rax+00h]
0x1400b71f7  lea     rdx, aDosdevicesVhdm; "\\DosDevices\\VHDMP"
0x1400b71fe  lea     rcx, [rbp+SymbolicLinkName]; DestinationString
0x1400b7202  call    cs:__imp_RtlInitUnicodeString
0x1400b7209  nop     dword ptr [rax+rax+00h]
0x1400b720e  lea     rdx, aDPAGaSyAGaBaAG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)"...
0x1400b7215  lea     rcx, [rbp+var_10]; DestinationString
0x1400b7219  call    cs:__imp_RtlInitUnicodeString
0x1400b7220  nop     dword ptr [rax+rax+00h]
0x1400b7225  cmp     cs:WdmlibInitialized, 0
0x1400b722c  mov     rbx, cs:VhdmpDriverObject
0x1400b7233  jnz     short loc_1400B723A
0x1400b7235  call    WdmlibInit
0x1400b723a  mov     rax, cs:PfnIoCreateDeviceSecure
0x1400b7241  lea     rcx, [rbp+DeviceObject]
0x1400b7245  mov     [rsp+80h+var_40], rcx
0x1400b724a  lea     r8, [rbp+DestinationString]
0x1400b724e  lea     rcx, GUID_VHDMP_CONTROL_OBJECT
0x1400b7255  mov     r9d, 53h ; 'S'
0x1400b725b  mov     [rsp+80h+var_48], rcx
0x1400b7260  mov     edx, 198h
0x1400b7265  lea     rcx, [rbp+var_10]
0x1400b7269  mov     [rsp+80h+var_50], rcx
0x1400b726e  mov     rcx, rbx
0x1400b7271  mov     [rsp+80h+var_58], 0
0x1400b7276  mov     [rsp+80h+var_60], 100h
0x1400b727e  call    _guard_dispatch_icall
0x1400b7283  mov     ebx, eax
0x1400b7285  test    eax, eax
0x1400b7287  js      loc_1400B732C
0x1400b728d  lea     r8, [rbp+P]
0x1400b7291  call    VhdmpiCreateNonGenericSecurityDescriptorFromSddlString
0x1400b7296  mov     ebx, eax
0x1400b7298  test    eax, eax
0x1400b729a  js      loc_1400B732C
0x1400b72a0  mov     rdx, [rbp+P]
0x1400b72a4  mov     rcx, [rbp+DeviceObject]
0x1400b72a8  call    VhdmpiSetDeviceSecurity
0x1400b72ad  mov     ebx, eax
0x1400b72af  test    eax, eax
0x1400b72b1  js      short loc_1400B732C
0x1400b72b3  mov     rax, [rbp+DeviceObject]
0x1400b72b7  xor     edx, edx; Val
0x1400b72b9  mov     r8d, 198h; Size
0x1400b72bf  or      dword ptr [rax+30h], 10h
0x1400b72c3  mov     rax, [rbp+DeviceObject]
0x1400b72c7  mov     rdi, [rax+40h]
0x1400b72cb  mov     rcx, rdi; void *
0x1400b72ce  call    memset
0x1400b72d3  mov     rax, [rbp+DeviceObject]
0x1400b72d7  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400b72db  mov     [rdi], rax
0x1400b72de  call    cs:__imp_IoDeleteSymbolicLink
0x1400b72e5  nop     dword ptr [rax+rax+00h]
0x1400b72ea  lea     rdx, [rbp+DestinationString]; DeviceName
0x1400b72ee  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400b72f2  call    cs:__imp_IoCreateSymbolicLink
0x1400b72f9  nop     dword ptr [rax+rax+00h]
0x1400b72fe  mov     ebx, eax
0x1400b7300  test    eax, eax
0x1400b7302  js      short loc_1400B732C
0x1400b7304  mov     rcx, rdi
0x1400b7307  call    VhdmpiInitializeIoctlQueue
0x1400b730c  mov     ebx, eax
0x1400b730e  test    eax, eax
0x1400b7310  js      short loc_1400B732C
0x1400b7312  lea     rax, [rdi+0B0h]
0x1400b7319  lea     rcx, [rdi+0C0h]
0x1400b7320  mov     [rax+8], rax
0x1400b7324  mov     [rax], rax
0x1400b7327  call    VhdmpiInitializePassiveLock
0x1400b732c  mov     rcx, [rbp+P]; P
0x1400b7330  test    rcx, rcx
0x1400b7333  jz      short loc_1400B7343
0x1400b7335  xor     edx, edx; Tag
0x1400b7337  call    cs:__imp_ExFreePoolWithTag
0x1400b733e  nop     dword ptr [rax+rax+00h]
0x1400b7343  test    ebx, ebx
0x1400b7345  jns     short loc_1400B7357
0x1400b7347  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400b734b  test    rcx, rcx
0x1400b734e  jz      short loc_1400B7362
0x1400b7350  call    ?VhdmpiDeleteControlDevice@@YAXPEAU_DEVICE_OBJECT@@@Z; VhdmpiDeleteControlDevice(_DEVICE_OBJECT *)
0x1400b7355  jmp     short loc_1400B7362
0x1400b7357  mov     rcx, [rbp+arg_20]
0x1400b735b  mov     rax, [rbp+DeviceObject]
0x1400b735f  mov     [rcx], rax
0x1400b7362  lea     r11, [rsp+80h+var_s0]
0x1400b736a  mov     eax, ebx
0x1400b736c  mov     rbx, [r11+10h]
0x1400b7370  mov     rdi, [r11+18h]
0x1400b7374  mov     rsp, r11
0x1400b7377  pop     rbp
0x1400b7378  retn
```
