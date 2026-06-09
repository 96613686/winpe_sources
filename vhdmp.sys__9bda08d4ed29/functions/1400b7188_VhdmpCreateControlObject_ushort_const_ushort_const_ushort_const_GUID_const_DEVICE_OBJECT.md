# VhdmpCreateControlObject(ushort const *,ushort const *,ushort const *,_GUID const *,_DEVICE_OBJECT * *)

- ea: `0x1400b7188`
- end: `0x1400b7362`
- name: `?VhdmpCreateControlObject@@YAJPEBG00PEBU_GUID@@PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, struct _DEVICE_OBJECT **)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400b8400`

## callees

- `0x140026e20`
- `0x14004953c`
- `0x14005dc30`
- `0x14005e100`
- `0x1400afc1c`
- `0x1400b7188`
- `0x1400b7640`
- `0x1400cc9a0`
- `0x1400d39f8`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b72c6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400b72c6`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400b72da`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400b72da`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7201`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b71ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b7201`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b731f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b731f`

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
0x1400b7188  mov     rax, rsp
0x1400b718b  mov     [rax+8], rbx
0x1400b718f  mov     [rax+10h], rdi
0x1400b7193  mov     [rax+20h], r9
0x1400b7197  mov     [rax+18h], r8
0x1400b719b  push    rbp
0x1400b719c  mov     rbp, rsp
0x1400b719f  sub     rsp, 80h
0x1400b71a6  xorps   xmm0, xmm0
0x1400b71a9  mov     [rbp+DeviceObject], 0
0x1400b71b1  xorps   xmm1, xmm1
0x1400b71b4  mov     [rbp+P], 0
0x1400b71bc  lea     rdx, aDeviceVhdmp; "\\Device\\VHDMP"
0x1400b71c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400b71c7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400b71cb  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1400b71cf  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm0
0x1400b71d3  call    cs:__imp_RtlInitUnicodeString
0x1400b71da  nop     dword ptr [rax+rax+00h]
0x1400b71df  lea     rdx, aDosdevicesVhdm; "\\DosDevices\\VHDMP"
0x1400b71e6  lea     rcx, [rbp+SymbolicLinkName]; DestinationString
0x1400b71ea  call    cs:__imp_RtlInitUnicodeString
0x1400b71f1  nop     dword ptr [rax+rax+00h]
0x1400b71f6  lea     rdx, aDPAGaSyAGaBaAG; "D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;AU)"...
0x1400b71fd  lea     rcx, [rbp+var_10]; DestinationString
0x1400b7201  call    cs:__imp_RtlInitUnicodeString
0x1400b7208  nop     dword ptr [rax+rax+00h]
0x1400b720d  cmp     cs:WdmlibInitialized, 0
0x1400b7214  mov     rbx, cs:VhdmpDriverObject
0x1400b721b  jnz     short loc_1400B7222
0x1400b721d  call    WdmlibInit
0x1400b7222  mov     rax, cs:PfnIoCreateDeviceSecure
0x1400b7229  lea     rcx, [rbp+DeviceObject]
0x1400b722d  mov     [rsp+80h+var_40], rcx
0x1400b7232  lea     r8, [rbp+DestinationString]
0x1400b7236  lea     rcx, GUID_VHDMP_CONTROL_OBJECT
0x1400b723d  mov     r9d, 53h ; 'S'
0x1400b7243  mov     [rsp+80h+var_48], rcx
0x1400b7248  mov     edx, 198h
0x1400b724d  lea     rcx, [rbp+var_10]
0x1400b7251  mov     [rsp+80h+var_50], rcx
0x1400b7256  mov     rcx, rbx
0x1400b7259  mov     [rsp+80h+var_58], 0
0x1400b725e  mov     [rsp+80h+var_60], 100h
0x1400b7266  call    _guard_dispatch_icall
0x1400b726b  mov     ebx, eax
0x1400b726d  test    eax, eax
0x1400b726f  js      loc_1400B7314
0x1400b7275  lea     r8, [rbp+P]
0x1400b7279  call    VhdmpiCreateNonGenericSecurityDescriptorFromSddlString
0x1400b727e  mov     ebx, eax
0x1400b7280  test    eax, eax
0x1400b7282  js      loc_1400B7314
0x1400b7288  mov     rdx, [rbp+P]
0x1400b728c  mov     rcx, [rbp+DeviceObject]
0x1400b7290  call    VhdmpiSetDeviceSecurity
0x1400b7295  mov     ebx, eax
0x1400b7297  test    eax, eax
0x1400b7299  js      short loc_1400B7314
0x1400b729b  mov     rax, [rbp+DeviceObject]
0x1400b729f  xor     edx, edx; Val
0x1400b72a1  mov     r8d, 198h; Size
0x1400b72a7  or      dword ptr [rax+30h], 10h
0x1400b72ab  mov     rax, [rbp+DeviceObject]
0x1400b72af  mov     rdi, [rax+40h]
0x1400b72b3  mov     rcx, rdi; void *
0x1400b72b6  call    memset
0x1400b72bb  mov     rax, [rbp+DeviceObject]
0x1400b72bf  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400b72c3  mov     [rdi], rax
0x1400b72c6  call    cs:__imp_IoDeleteSymbolicLink
0x1400b72cd  nop     dword ptr [rax+rax+00h]
0x1400b72d2  lea     rdx, [rbp+DestinationString]; DeviceName
0x1400b72d6  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400b72da  call    cs:__imp_IoCreateSymbolicLink
0x1400b72e1  nop     dword ptr [rax+rax+00h]
0x1400b72e6  mov     ebx, eax
0x1400b72e8  test    eax, eax
0x1400b72ea  js      short loc_1400B7314
0x1400b72ec  mov     rcx, rdi
0x1400b72ef  call    VhdmpiInitializeIoctlQueue
0x1400b72f4  mov     ebx, eax
0x1400b72f6  test    eax, eax
0x1400b72f8  js      short loc_1400B7314
0x1400b72fa  lea     rax, [rdi+0B0h]
0x1400b7301  lea     rcx, [rdi+0C0h]
0x1400b7308  mov     [rax+8], rax
0x1400b730c  mov     [rax], rax
0x1400b730f  call    VhdmpiInitializePassiveLock
0x1400b7314  mov     rcx, [rbp+P]; P
0x1400b7318  test    rcx, rcx
0x1400b731b  jz      short loc_1400B732B
0x1400b731d  xor     edx, edx; Tag
0x1400b731f  call    cs:__imp_ExFreePoolWithTag
0x1400b7326  nop     dword ptr [rax+rax+00h]
0x1400b732b  test    ebx, ebx
0x1400b732d  jns     short loc_1400B733F
0x1400b732f  mov     rcx, [rbp+DeviceObject]; DeviceObject
0x1400b7333  test    rcx, rcx
0x1400b7336  jz      short loc_1400B734A
0x1400b7338  call    ?VhdmpiDeleteControlDevice@@YAXPEAU_DEVICE_OBJECT@@@Z; VhdmpiDeleteControlDevice(_DEVICE_OBJECT *)
0x1400b733d  jmp     short loc_1400B734A
0x1400b733f  mov     rcx, [rbp+arg_20]
0x1400b7343  mov     rax, [rbp+DeviceObject]
0x1400b7347  mov     [rcx], rax
0x1400b734a  lea     r11, [rsp+80h+var_s0]
0x1400b7352  mov     eax, ebx
0x1400b7354  mov     rbx, [r11+10h]
0x1400b7358  mov     rdi, [r11+18h]
0x1400b735c  mov     rsp, r11
0x1400b735f  pop     rbp
0x1400b7360  retn
```
