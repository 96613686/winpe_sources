# VhdmpiUnitPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b7bbc`
- end: `0x1400b83dd`
- name: `?VhdmpiUnitPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2081`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b86bc`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x14001df30`
- `0x140023560`
- `0x1400269cc`
- `0x1400339d8`
- `0x140033a80`
- `0x140033f40`
- `0x14003402c`
- `0x140034054`
- `0x140035a50`
- `0x140035e94`
- `0x14005d7c0`
- `0x14005d840`
- `0x14005da00`
- `0x1400a9f58`
- `0x1400b66f8`
- `0x1400b7464`
- `0x1400b76b0`
- `0x1400b7920`
- `0x1400b7bbc`
- `0x1400bbfc8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400b7eb2`
- `ntoskrnl!KeCancelTimer` at `0x1400b7eb2`
- `ntoskrnl!ZwOpenKey` at `0x1400b81df`
- `ntoskrnl!ZwOpenKey` at `0x1400b81df`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b8183`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b8183`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400b80da`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400b80da`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b8126`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b828f`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b8126`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b828f`
- `ntoskrnl!ZwDeleteKey` at `0x1400b81f6`
- `ntoskrnl!ZwDeleteKey` at `0x1400b81f6`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400b8323`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400b8323`
- `ntoskrnl!IofCompleteRequest` at `0x1400b83a3`
- `ntoskrnl!IofCompleteRequest` at `0x1400b83a3`
- `ntoskrnl!ZwClose` at `0x1400b8209`
- `ntoskrnl!ZwClose` at `0x1400b82ac`
- `ntoskrnl!ZwClose` at `0x1400b8209`
- `ntoskrnl!ZwClose` at `0x1400b82ac`
- `storport!StorPortGetLogicalUnit` at `0x1400b7d3d`
- `storport!StorPortGetLogicalUnit` at `0x1400b7d3d`

## string_xrefs

- `0x1400b8254`: `VhdmpPnp: START: failed to delete the %S registry key. (Status 0x%x.)`
- `0x1400b82d6`: `VhdmpPnp: Status of clearing registry keys is 0x%x.`
- `0x1400b8076`: `VhdmpPnp: unsurface the disk %p as the backing store is no longer accessible.`

## pseudocode

```c
__int64 __fastcall VhdmpiUnitPnp(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _BYTE *v3; // rbx
  PIRP v4; // r13
  char v5; // di
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rsi
  PIRP v10; // rdx
  signed int v11; // ebx
  signed int PowerRelations; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 LogicalUnit; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  struct _VHD_LUN_EXTENSION *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  char v24; // al
  struct _DEVICE_OBJECT *v25; // rcx
  __int64 v26; // rax
  struct _VHD_SURFACE *v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  NTSTATUS v31; // ebx
  void *v32; // rcx
  ULONG v33; // r13d
  char v35[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Index; // [rsp+44h] [rbp-BCh] BYREF
  void *DeviceRegKey; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp-98h] BYREF
  char v42[8]; // [rsp+78h] [rbp-88h]
  struct _IO_STACK_LOCATION *v43; // [rsp+80h] [rbp-80h]
  PIRP v44; // [rsp+88h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyInformation[12]; // [rsp+C0h] [rbp-40h] BYREF
  USHORT v47; // [rsp+CCh] [rbp-34h]
  char Src[240]; // [rsp+D0h] [rbp-30h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  v44 = Irp;
  v4 = Irp;
  v39 = 0;
  v35[0] = 0;
  KeyHandle = 0;
  v5 = 1;
  ResultLength = 0;
  DeviceRegKey = 0;
  String1 = 0;
  *(_QWORD *)v42 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v43 = CurrentStackLocation;
  v7 = VhdmpiAddRundownRefSurfaceByPdo(a1);
  v9 = v7;
  if ( v7 )
  {
    v3 = *(_BYTE **)(v7 + 16);
    *(_QWORD *)v42 = v3;
  }
  if ( v43->MinorFunction )
  {
    switch ( v43->MinorFunction )
    {
      case 2u:
        v35[0] = 0;
        VhdmpiSendSyncDeviceIoControlToDevice(0x2D190Cu, a1, 0, v35, 1u);
        v26 = VhdmpiAddRefSurfaceByPdo(a1);
        v27 = (struct _VHD_SURFACE *)v26;
        if ( v26 )
        {
          if ( KeCancelTimer((PKTIMER)(v26 + 352)) )
            VhdmpiCancelSurfaceDiskRequestAndRelease(v27, 3221225760LL, v29, v30);
          if ( v35[0] )
          {
            VhdmpiAcquirePassiveLock((char *)v27 + 304, v28, v29);
            VhdmpiHwDeleteLun(v27);
            VhdmpiReleasePassiveLock((char *)v27 + 304);
          }
          VhdmpiReleaseSurface(v27);
        }
        break;
      case 7u:
        v10 = v4;
        v25 = a1;
        if ( v43->Parameters.Read.Length == 2 )
        {
          PowerRelations = VhdmpiQueryPowerRelations(a1, v4);
LABEL_44:
          v5 = 0;
          goto LABEL_45;
        }
LABEL_43:
        PowerRelations = ((__int64 (__fastcall *)(struct _DEVICE_OBJECT *, PIRP))qword_14008D058)(v25, v10);
        goto LABEL_44;
      case 9u:
        if ( v7 )
        {
          SecurityContext = v43->Parameters.Create.SecurityContext;
          v24 = v3[80];
          HIDWORD(SecurityContext->SecurityQos) &= ~0x10u;
          if ( !v24 )
            HIDWORD(SecurityContext->SecurityQos) |= 0x208u;
        }
        break;
      case 0x11u:
        if ( v7 )
        {
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v7 + 72)) <= 1 )
            __fastfail(0xEu);
          VhdmpiReleaseRundownRefVirtualDiskSurface(v7, 0);
          if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
            TraceEvents(
              "VhdmpiUnitPnp",
              0x74Au,
              4u,
              0x10u,
              "VhdmpPnp: unsurface the disk %p as the user is requesting that the disk be un-enumerated.",
              v3);
          VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)v9);
          VhdmpiReleaseSurface(v9);
        }
        v11 = 0;
        goto LABEL_92;
      case 0x13u:
        if ( !v43->Parameters.Read.Length && (int)VhdmpiSendSyncDeviceIoControlToDevice(0x41018u, a1, 0, &v39, 8u) >= 0 )
        {
          LOBYTE(v15) = HIBYTE(v39);
          LOBYTE(v14) = BYTE6(v39);
          LOBYTE(v13) = BYTE5(v39);
          LogicalUnit = StorPortGetLogicalUnit(VhdmpAdapterExtension, v13, v14, v15);
          v20 = (struct _VHD_LUN_EXTENSION *)LogicalUnit;
          if ( LogicalUnit )
          {
            if ( !*(_BYTE *)LogicalUnit )
            {
              *(_BYTE *)LogicalUnit = 1;
              *(_QWORD *)(LogicalUnit + 16) = a1;
              v21 = VhdmpiAddRundownRefSurfaceByAddress(&v39, v17, v18, v19);
              v22 = v21;
              if ( v21 )
              {
                if ( (*(_DWORD *)(v21 + 56) & 0x200) == 0 )
                  VhdmpiHwCreateLun(a1, v20, (struct _VHD_SURFACE *)v21);
                VhdmpiReleaseRundownRefVirtualDiskSurface(v22, 0);
              }
            }
          }
        }
        break;
      case 0x14u:
        v4->IoStatus.Information |= 0x20uLL;
        break;
      default:
        v10 = v4;
        if ( v43->MinorFunction == 22 )
        {
          v11 = VhdmpiNotifyDeviceUsage((struct _VHD_SURFACE *)v7, v4);
          if ( v11 < 0 )
            goto LABEL_46;
          v5 = 0;
          PowerRelations = ((__int64 (__fastcall *)(struct _DEVICE_OBJECT *, PIRP))qword_14008D058)(a1, v4);
LABEL_45:
          v11 = PowerRelations;
LABEL_46:
          if ( v9 )
            goto LABEL_90;
          goto LABEL_91;
        }
        goto LABEL_42;
    }
    v10 = v4;
LABEL_42:
    v25 = a1;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x610u, 4u, 0x10u, "VhdmpPnp: START... DO: %p", a1);
  if ( !v9 )
  {
    v11 = -1073741810;
    goto LABEL_92;
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x61Au, 4u, 0x10u, "VhdmpPnp: START... Surface: %p", (const void *)v9);
  Index = 0;
  v11 = VhdmpiRegisterDiskWithDependencyDriver(v9, a1, v8, &Index);
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x634u,
        2u,
        0x10u,
        "VhdmpPnp: START: failed to register w/ depends driver. (0x%x)",
        v11);
    goto LABEL_90;
  }
  v11 = Index;
  if ( (Index & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x645u,
        4u,
        0x10u,
        "VhdmpPnp: unsurface the disk %p as the backing store is no longer accessible.",
        *(const void **)v42);
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v9 + 72)) <= 1 )
      __fastfail(0xEu);
    VhdmpiReleaseRundownRefVirtualDiskSurface(v9, 0);
    VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)v9);
    VhdmpiReleaseSurface(v9);
    goto LABEL_92;
  }
  v31 = IoOpenDeviceRegistryKey(a1, 1u, 0x20019u, &DeviceRegKey);
  if ( v31 >= 0 )
  {
    v32 = DeviceRegKey;
  }
  else
  {
    v32 = 0;
    DeviceRegKey = 0;
  }
  if ( !v32 )
    goto LABEL_85;
  Index = 0;
  if ( ZwEnumerateKey(v32, 0, KeyBasicInformation, KeyInformation, 0x100u, &ResultLength) < 0 )
    goto LABEL_84;
  v33 = Index;
  do
  {
    String1.Length = v47;
    String1.MaximumLength = v47;
    if ( v47 >= 0xF0u )
      continue;
    memmove(KeyInformation, Src, v47);
    String1.Buffer = (PWSTR)KeyInformation;
    if ( !RtlCompareUnicodeString(&String1, &stru_1400607C0, 1u) )
    {
      v31 = VhdmpiCleanupPartMgrKey(DeviceRegKey, &String1);
LABEL_81:
      ++v33;
      continue;
    }
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &String1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v31 = ZwOpenKey(&KeyHandle, 0x10000u, &ObjectAttributes);
    if ( v31 >= 0 )
    {
      v31 = ZwDeleteKey(KeyHandle);
      ZwClose(KeyHandle);
      if ( v31 >= 0 )
        continue;
    }
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x69Fu,
        2u,
        0x10u,
        "VhdmpPnp: START: failed to delete the %S registry key. (Status 0x%x.)",
        String1.Buffer,
        v31);
    goto LABEL_81;
  }
  while ( ZwEnumerateKey(DeviceRegKey, v33, KeyBasicInformation, KeyInformation, 0x100u, &ResultLength) >= 0 );
  v4 = v44;
LABEL_84:
  ZwClose(DeviceRegKey);
LABEL_85:
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x6B1u, 4u, 0x10u, "VhdmpPnp: Status of clearing registry keys is 0x%x.", v31);
  v5 = 0;
  v11 = ((__int64 (__fastcall *)(struct _DEVICE_OBJECT *, PIRP))qword_14008D058)(a1, v4);
  if ( v11 >= 0 )
    IoInvalidateDeviceRelations(a1, PowerRelations);
LABEL_90:
  VhdmpiReleaseRundownRefVirtualDiskSurface(v9, 0);
LABEL_91:
  if ( v5 )
  {
LABEL_92:
    if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x786u,
        4u,
        0x10u,
        "VhdmpPnp: failed MinorFunction 0x%x (Status 0x%x)",
        v43->MinorFunction,
        v11);
    v4->IoStatus.Information = 0;
    v4->IoStatus.Status = v11;
    IofCompleteRequest(v4, 0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400b7bbc  mov     [rsp-8+arg_10], rbx
0x1400b7bc1  mov     [rsp-8+arg_18], rsi
0x1400b7bc6  push    rbp
0x1400b7bc7  push    rdi
0x1400b7bc8  push    r12
0x1400b7bca  push    r13
0x1400b7bcc  push    r15
0x1400b7bce  lea     rbp, [rsp-0D0h]
0x1400b7bd6  sub     rsp, 1D0h
0x1400b7bdd  mov     rax, cs:__security_cookie
0x1400b7be4  xor     rax, rsp
0x1400b7be7  mov     [rbp+0F0h+var_30], rax
0x1400b7bee  mov     rax, [rdx+0B8h]
0x1400b7bf5  xorps   xmm1, xmm1
0x1400b7bf8  xor     ebx, ebx
0x1400b7bfa  mov     [rbp+0F0h+var_168], rdx
0x1400b7bfe  mov     r13, rdx
0x1400b7c01  mov     [rsp+1F0h+var_198], 0
0x1400b7c0a  xorps   xmm0, xmm0
0x1400b7c0d  mov     [rsp+1F0h+var_1B0], 0
0x1400b7c12  xor     edx, edx
0x1400b7c14  mov     [rsp+1F0h+KeyHandle], 0
0x1400b7c1d  lea     edi, [rbx+1]
0x1400b7c20  mov     [rsp+1F0h+var_1A0], 0
0x1400b7c28  mov     r15, rcx
0x1400b7c2b  mov     [rsp+1F0h+DeviceRegKey], 0
0x1400b7c34  movups  xmmword ptr [rsp+1F0h+String1.Length], xmm0
0x1400b7c39  mov     qword ptr [rsp+1F0h+var_178], rbx
0x1400b7c3e  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm1
0x1400b7c42  mov     [rbp+0F0h+var_170], rax
0x1400b7c46  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm1
0x1400b7c4a  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400b7c4e  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400b7c53  mov     rsi, rax
0x1400b7c56  test    rax, rax
0x1400b7c59  jz      short loc_1400B7C64
0x1400b7c5b  mov     rbx, [rax+10h]
0x1400b7c5f  mov     qword ptr [rsp+1F0h+var_178], rbx
0x1400b7c64  mov     rax, [rbp+0F0h+var_170]
0x1400b7c68  mov     r12d, 10h
0x1400b7c6e  movzx   edx, byte ptr [rax+1]
0x1400b7c72  test    edx, edx
0x1400b7c74  jz      loc_1400B7F22
0x1400b7c7a  sub     edx, 2
0x1400b7c7d  jz      loc_1400B7E6D
0x1400b7c83  sub     edx, 5
0x1400b7c86  jz      loc_1400B7E53
0x1400b7c8c  sub     edx, 2
0x1400b7c8f  jz      loc_1400B7E2B
0x1400b7c95  sub     edx, 8
0x1400b7c98  jz      loc_1400B7DA1
0x1400b7c9e  sub     edx, 2
0x1400b7ca1  jz      short loc_1400B7CE9
0x1400b7ca3  sub     edx, edi
0x1400b7ca5  jz      short loc_1400B7CDF
0x1400b7ca7  cmp     edx, 2
0x1400b7caa  mov     rdx, r13; struct _IRP *
0x1400b7cad  jnz     loc_1400B7F00
0x1400b7cb3  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b7cb6  call    ?VhdmpiNotifyDeviceUsage@@YAJPEAU_VHD_SURFACE@@PEAU_IRP@@@Z; VhdmpiNotifyDeviceUsage(_VHD_SURFACE *,_IRP *)
0x1400b7cbb  mov     ebx, eax
0x1400b7cbd  test    eax, eax
0x1400b7cbf  js      loc_1400B7F14
0x1400b7cc5  mov     rax, cs:qword_14008D058
0x1400b7ccc  xor     dil, dil
0x1400b7ccf  mov     rdx, r13
0x1400b7cd2  mov     rcx, r15
0x1400b7cd5  call    _guard_dispatch_icall
0x1400b7cda  jmp     loc_1400B7F12
0x1400b7cdf  or      qword ptr [r13+38h], 20h
0x1400b7ce4  jmp     loc_1400B7EFD
0x1400b7ce9  cmp     dword ptr [rax+8], 0
0x1400b7ced  jnz     loc_1400B7EFD
0x1400b7cf3  lea     rax, [rsp+1F0h+var_198]
0x1400b7cf8  mov     [rsp+1F0h+var_1C0], 8; ULONG
0x1400b7d00  mov     [rsp+1F0h+ResultLength], rax; PVOID
0x1400b7d05  xor     r9d, r9d
0x1400b7d08  mov     r8b, dil
0x1400b7d0b  mov     [rsp+1F0h+Length], 0; InputBufferLength
0x1400b7d13  mov     rdx, r15; DeviceObject
0x1400b7d16  mov     ecx, 41018h; IoControlCode
0x1400b7d1b  call    VhdmpiSendSyncDeviceIoControlToDevice
0x1400b7d20  test    eax, eax
0x1400b7d22  js      loc_1400B7EFD
0x1400b7d28  mov     r9b, byte ptr [rsp+1F0h+var_198+7]
0x1400b7d2d  mov     r8b, byte ptr [rsp+1F0h+var_198+6]
0x1400b7d32  mov     dl, byte ptr [rsp+1F0h+var_198+5]
0x1400b7d36  mov     rcx, cs:VhdmpAdapterExtension
0x1400b7d3d  call    cs:__imp_StorPortGetLogicalUnit
0x1400b7d44  nop     dword ptr [rax+rax+00h]
0x1400b7d49  mov     rbx, rax
0x1400b7d4c  test    rax, rax
0x1400b7d4f  jz      loc_1400B7EFD
0x1400b7d55  cmp     byte ptr [rax], 0
0x1400b7d58  jnz     loc_1400B7EFD
0x1400b7d5e  lea     rcx, [rsp+1F0h+var_198]
0x1400b7d63  mov     [rax], dil
0x1400b7d66  mov     [rax+10h], r15
0x1400b7d6a  call    VhdmpiAddRundownRefSurfaceByAddress
0x1400b7d6f  mov     rdi, rax
0x1400b7d72  test    rax, rax
0x1400b7d75  jz      loc_1400B7EFD
0x1400b7d7b  test    dword ptr [rax+38h], 200h
0x1400b7d82  jnz     short loc_1400B7D92
0x1400b7d84  mov     r8, rax; struct _VHD_SURFACE *
0x1400b7d87  mov     rdx, rbx; struct _VHD_LUN_EXTENSION *
0x1400b7d8a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7d8d  call    ?VhdmpiHwCreateLun@@YAEPEAU_DEVICE_OBJECT@@PEAU_VHD_LUN_EXTENSION@@PEAU_VHD_SURFACE@@@Z; VhdmpiHwCreateLun(_DEVICE_OBJECT *,_VHD_LUN_EXTENSION *,_VHD_SURFACE *)
0x1400b7d92  xor     edx, edx
0x1400b7d94  mov     rcx, rdi
0x1400b7d97  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7d9c  jmp     loc_1400B7EFD
0x1400b7da1  test    rsi, rsi
0x1400b7da4  jz      short loc_1400B7E24
0x1400b7da6  mov     rax, rdi
0x1400b7da9  lock xadd [rsi+48h], rax
0x1400b7daf  add     rax, rdi
0x1400b7db2  cmp     rax, rdi
0x1400b7db5  jg      short loc_1400B7DBE
0x1400b7db7  mov     ecx, 0Eh
0x1400b7dbc  int     29h; Win8: RtlFailFast(ecx)
0x1400b7dbe  xor     edx, edx
0x1400b7dc0  mov     rcx, rsi
0x1400b7dc3  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7dc8  mov     eax, cs:dword_140087708
0x1400b7dce  cmp     eax, 4
0x1400b7dd1  jbe     short loc_1400B7E11
0x1400b7dd3  mov     rdx, r12
0x1400b7dd6  lea     rcx, dword_140087708
0x1400b7ddd  call    _tlgKeywordOn
0x1400b7de2  test    al, al
0x1400b7de4  jz      short loc_1400B7E11
0x1400b7de6  lea     rax, aVhdmppnpUnsurf_0; "VhdmpPnp: unsurface the disk %p as the "...
0x1400b7ded  mov     [rsp+1F0h+ResultLength], rbx; char
0x1400b7df2  mov     edx, 74Ah; int
0x1400b7df7  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7dfc  mov     r9d, r12d; int
0x1400b7dff  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7e06  mov     r8d, 4; int
0x1400b7e0c  call    TraceEvents
0x1400b7e11  mov     dl, dil
0x1400b7e14  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b7e17  call    VhdmpiHaltSurfaceOrWait
0x1400b7e1c  mov     rcx, rsi
0x1400b7e1f  call    VhdmpiReleaseSurface
0x1400b7e24  xor     ebx, ebx
0x1400b7e26  jmp     loc_1400B833E
0x1400b7e2b  test    rsi, rsi
0x1400b7e2e  jz      loc_1400B7EFD
0x1400b7e34  mov     rcx, [rax+8]
0x1400b7e38  mov     al, [rbx+50h]
0x1400b7e3b  and     dword ptr [rcx+4], 0FFFFFFEFh
0x1400b7e3f  test    al, al
0x1400b7e41  jnz     loc_1400B7EFD
0x1400b7e47  or      dword ptr [rcx+4], 208h
0x1400b7e4e  jmp     loc_1400B7EFD
0x1400b7e53  cmp     dword ptr [rax+8], 2
0x1400b7e57  mov     rdx, r13; Irp
0x1400b7e5a  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7e5d  jnz     loc_1400B7F03
0x1400b7e63  call    ?VhdmpiQueryPowerRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VhdmpiQueryPowerRelations(_DEVICE_OBJECT *,_IRP *)
0x1400b7e68  jmp     loc_1400B7F0F
0x1400b7e6d  lea     rax, [rsp+1F0h+var_1B0]
0x1400b7e72  mov     [rsp+1F0h+var_1C0], edi; ULONG
0x1400b7e76  mov     [rsp+1F0h+ResultLength], rax; PVOID
0x1400b7e7b  xor     r9d, r9d
0x1400b7e7e  xor     r8d, r8d
0x1400b7e81  mov     [rsp+1F0h+Length], 0; InputBufferLength
0x1400b7e89  mov     rdx, r15; DeviceObject
0x1400b7e8c  mov     [rsp+1F0h+var_1B0], 0
0x1400b7e91  mov     ecx, 2D190Ch; IoControlCode
0x1400b7e96  call    VhdmpiSendSyncDeviceIoControlToDevice
0x1400b7e9b  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7e9e  call    VhdmpiAddRefSurfaceByPdo
0x1400b7ea3  mov     rdi, rax
0x1400b7ea6  test    rax, rax
0x1400b7ea9  jz      short loc_1400B7EFD
0x1400b7eab  lea     rcx, [rax+160h]; PKTIMER
0x1400b7eb2  call    cs:__imp_KeCancelTimer
0x1400b7eb9  nop     dword ptr [rax+rax+00h]
0x1400b7ebe  test    al, al
0x1400b7ec0  jz      short loc_1400B7ECF
0x1400b7ec2  mov     edx, 0C0000120h
0x1400b7ec7  mov     rcx, rdi
0x1400b7eca  call    VhdmpiCancelSurfaceDiskRequestAndRelease
0x1400b7ecf  cmp     [rsp+1F0h+var_1B0], 0
0x1400b7ed4  jz      short loc_1400B7EF5
0x1400b7ed6  lea     rbx, [rdi+130h]
0x1400b7edd  mov     rcx, rbx
0x1400b7ee0  call    VhdmpiAcquirePassiveLock
0x1400b7ee5  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400b7ee8  call    ?VhdmpiHwDeleteLun@@YAXPEAU_VHD_SURFACE@@@Z; VhdmpiHwDeleteLun(_VHD_SURFACE *)
0x1400b7eed  mov     rcx, rbx
0x1400b7ef0  call    VhdmpiReleasePassiveLock
0x1400b7ef5  mov     rcx, rdi
0x1400b7ef8  call    VhdmpiReleaseSurface
0x1400b7efd  mov     rdx, r13
0x1400b7f00  mov     rcx, r15
0x1400b7f03  mov     rax, cs:qword_14008D058
0x1400b7f0a  call    _guard_dispatch_icall
0x1400b7f0f  xor     dil, dil
0x1400b7f12  mov     ebx, eax
0x1400b7f14  test    rsi, rsi
0x1400b7f17  jz      loc_1400B8339
0x1400b7f1d  jmp     loc_1400B832F
0x1400b7f22  mov     eax, cs:dword_140087708
0x1400b7f28  cmp     eax, 4
0x1400b7f2b  jbe     short loc_1400B7F6B
0x1400b7f2d  mov     rdx, r12
0x1400b7f30  lea     rcx, dword_140087708
0x1400b7f37  call    _tlgKeywordOn
0x1400b7f3c  test    al, al
0x1400b7f3e  jz      short loc_1400B7F6B
0x1400b7f40  lea     rax, aVhdmppnpStartD; "VhdmpPnp: START... DO: %p"
0x1400b7f47  mov     [rsp+1F0h+ResultLength], r15; char
0x1400b7f4c  mov     edx, 610h; int
0x1400b7f51  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7f56  mov     r9d, r12d; int
0x1400b7f59  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7f60  mov     r8d, 4; int
0x1400b7f66  call    TraceEvents
0x1400b7f6b  test    rsi, rsi
0x1400b7f6e  jnz     short loc_1400B7F7A
0x1400b7f70  mov     ebx, 0C000000Eh
0x1400b7f75  jmp     loc_1400B833E
0x1400b7f7a  mov     eax, cs:dword_140087708
0x1400b7f80  cmp     eax, 4
0x1400b7f83  jbe     short loc_1400B7FC3
0x1400b7f85  mov     rdx, r12
0x1400b7f88  lea     rcx, dword_140087708
0x1400b7f8f  call    _tlgKeywordOn
0x1400b7f94  test    al, al
0x1400b7f96  jz      short loc_1400B7FC3
0x1400b7f98  lea     rax, aVhdmppnpStartS; "VhdmpPnp: START... Surface: %p"
0x1400b7f9f  mov     [rsp+1F0h+ResultLength], rsi; char
0x1400b7fa4  mov     edx, 61Ah; int
0x1400b7fa9  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7fae  mov     r9d, r12d; int
0x1400b7fb1  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7fb8  mov     r8d, 4; int
0x1400b7fbe  call    TraceEvents
0x1400b7fc3  lea     r9, [rsp+1F0h+Index]
0x1400b7fc8  mov     [rsp+1F0h+Index], 0
0x1400b7fd0  mov     rdx, r15
0x1400b7fd3  mov     rcx, rsi
0x1400b7fd6  call    VhdmpiRegisterDiskWithDependencyDriver
0x1400b7fdb  mov     ebx, eax
0x1400b7fdd  test    eax, eax
0x1400b7fdf  jns     short loc_1400B8036
0x1400b7fe1  mov     eax, cs:dword_140087708
0x1400b7fe7  cmp     eax, 2
0x1400b7fea  jbe     loc_1400B832F
0x1400b7ff0  mov     rdx, r12
0x1400b7ff3  lea     rcx, dword_140087708
0x1400b7ffa  call    _tlgKeywordOn
0x1400b7fff  test    al, al
0x1400b8001  jz      loc_1400B832F
0x1400b8007  lea     rax, aVhdmppnpStartF_0; "VhdmpPnp: START: failed to register w/ "...
0x1400b800e  mov     dword ptr [rsp+1F0h+ResultLength], ebx; char
0x1400b8012  mov     edx, 634h; int
0x1400b8017  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b801c  mov     r9d, r12d; int
0x1400b801f  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b8026  mov     r8d, 2; int
0x1400b802c  call    TraceEvents
0x1400b8031  jmp     loc_1400B832F
0x1400b8036  mov     ebx, [rsp+1F0h+Index]
0x1400b803a  test    ebx, ebx
0x1400b803c  jns     loc_1400B80CA
0x1400b8042  mov     eax, cs:dword_140087708
0x1400b8048  cmp     eax, 4
0x1400b804b  jbe     short loc_1400B8090
0x1400b804d  mov     rdx, r12
0x1400b8050  lea     rcx, dword_140087708
0x1400b8057  call    _tlgKeywordOn
0x1400b805c  test    al, al
0x1400b805e  jz      short loc_1400B8090
0x1400b8060  mov     rax, qword ptr [rsp+1F0h+var_178]
0x1400b8065  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b806c  mov     [rsp+1F0h+ResultLength], rax; char
0x1400b8071  mov     edx, 645h; int
0x1400b8076  lea     rax, aVhdmppnpUnsurf; "VhdmpPnp: unsurface the disk %p as the "...
0x1400b807d  mov     r9d, r12d; int
0x1400b8080  mov     r8d, 4; int
0x1400b8086  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b808b  call    TraceEvents
0x1400b8090  mov     rax, rdi
0x1400b8093  lock xadd [rsi+48h], rax
0x1400b8099  add     rax, rdi
0x1400b809c  cmp     rax, rdi
0x1400b809f  jg      short loc_1400B80A8
0x1400b80a1  mov     ecx, 0Eh
0x1400b80a6  int     29h; Win8: RtlFailFast(ecx)
0x1400b80a8  xor     edx, edx
0x1400b80aa  mov     rcx, rsi
0x1400b80ad  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b80b2  mov     dl, dil
0x1400b80b5  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b80b8  call    VhdmpiHaltSurfaceOrWait
0x1400b80bd  mov     rcx, rsi
  ... truncated ...
```
