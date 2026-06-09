# VhdmpiUnitPnp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b7ba4`
- end: `0x1400b83c5`
- name: `?VhdmpiUnitPnp@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2081`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b86ac`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x14001e350`
- `0x140023980`
- `0x140026dec`
- `0x140033e98`
- `0x140033f40`
- `0x140034400`
- `0x1400344ec`
- `0x140034514`
- `0x140035e40`
- `0x140036284`
- `0x14005dbb0`
- `0x14005dc30`
- `0x14005de00`
- `0x1400a9f58`
- `0x1400b66f8`
- `0x1400b744c`
- `0x1400b7698`
- `0x1400b7908`
- `0x1400b7ba4`
- `0x1400bbfb8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400b7e9a`
- `ntoskrnl!KeCancelTimer` at `0x1400b7e9a`
- `ntoskrnl!ZwOpenKey` at `0x1400b81c7`
- `ntoskrnl!ZwOpenKey` at `0x1400b81c7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b816b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400b816b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400b80c2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400b80c2`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b810e`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b8277`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b810e`
- `ntoskrnl!ZwEnumerateKey` at `0x1400b8277`
- `ntoskrnl!ZwDeleteKey` at `0x1400b81de`
- `ntoskrnl!ZwDeleteKey` at `0x1400b81de`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400b830b`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400b830b`
- `ntoskrnl!IofCompleteRequest` at `0x1400b838b`
- `ntoskrnl!IofCompleteRequest` at `0x1400b838b`
- `ntoskrnl!ZwClose` at `0x1400b81f1`
- `ntoskrnl!ZwClose` at `0x1400b8294`
- `ntoskrnl!ZwClose` at `0x1400b81f1`
- `ntoskrnl!ZwClose` at `0x1400b8294`
- `storport!StorPortGetLogicalUnit` at `0x1400b7d25`
- `storport!StorPortGetLogicalUnit` at `0x1400b7d25`

## string_xrefs

- `0x1400b82be`: `VhdmpPnp: Status of clearing registry keys is 0x%x.`
- `0x1400b805e`: `VhdmpPnp: unsurface the disk %p as the backing store is no longer accessible.`
- `0x1400b823c`: `VhdmpPnp: START: failed to delete the %S registry key. (Status 0x%x.)`

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
  struct _VHD_LUN_EXTENSION *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  char v21; // al
  struct _DEVICE_OBJECT *v22; // rcx
  __int64 v23; // rax
  struct _VHD_SURFACE *v24; // rdi
  NTSTATUS v25; // ebx
  void *v26; // rcx
  ULONG v27; // r13d
  char v29[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Index; // [rsp+44h] [rbp-BCh] BYREF
  void *DeviceRegKey; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp-98h] BYREF
  char v36[8]; // [rsp+78h] [rbp-88h]
  struct _IO_STACK_LOCATION *v37; // [rsp+80h] [rbp-80h]
  PIRP v38; // [rsp+88h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyInformation[12]; // [rsp+C0h] [rbp-40h] BYREF
  USHORT v41; // [rsp+CCh] [rbp-34h]
  char Src[240]; // [rsp+D0h] [rbp-30h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  v38 = Irp;
  v4 = Irp;
  v33 = 0;
  v29[0] = 0;
  KeyHandle = 0;
  v5 = 1;
  ResultLength = 0;
  DeviceRegKey = 0;
  String1 = 0;
  *(_QWORD *)v36 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v37 = CurrentStackLocation;
  v7 = VhdmpiAddRundownRefSurfaceByPdo(a1);
  v9 = v7;
  if ( v7 )
  {
    v3 = *(_BYTE **)(v7 + 16);
    *(_QWORD *)v36 = v3;
  }
  if ( v37->MinorFunction )
  {
    switch ( v37->MinorFunction )
    {
      case 2u:
        v29[0] = 0;
        VhdmpiSendSyncDeviceIoControlToDevice(0x2D190Cu, a1, 0, v29, 1u);
        v23 = VhdmpiAddRefSurfaceByPdo(a1);
        v24 = (struct _VHD_SURFACE *)v23;
        if ( v23 )
        {
          if ( KeCancelTimer((PKTIMER)(v23 + 352)) )
            VhdmpiCancelSurfaceDiskRequestAndRelease(v24, 3221225760LL);
          if ( v29[0] )
          {
            VhdmpiAcquirePassiveLock((char *)v24 + 304);
            VhdmpiHwDeleteLun(v24);
            VhdmpiReleasePassiveLock((char *)v24 + 304);
          }
          VhdmpiReleaseSurface(v24);
        }
        break;
      case 7u:
        v10 = v4;
        v22 = a1;
        if ( v37->Parameters.Read.Length == 2 )
        {
          PowerRelations = VhdmpiQueryPowerRelations(a1, v4);
LABEL_44:
          v5 = 0;
          goto LABEL_45;
        }
LABEL_43:
        PowerRelations = ((__int64 (__fastcall *)(struct _DEVICE_OBJECT *, PIRP))qword_14008D058)(v22, v10);
        goto LABEL_44;
      case 9u:
        if ( v7 )
        {
          SecurityContext = v37->Parameters.Create.SecurityContext;
          v21 = v3[80];
          HIDWORD(SecurityContext->SecurityQos) &= ~0x10u;
          if ( !v21 )
            HIDWORD(SecurityContext->SecurityQos) |= 0x208u;
        }
        break;
      case 0x11u:
        if ( v7 )
        {
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v7 + 72)) <= 1 )
            __fastfail(0xEu);
          VhdmpiReleaseRundownRefVirtualDiskSurface(v7, 0);
          if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
        if ( !v37->Parameters.Read.Length && (int)VhdmpiSendSyncDeviceIoControlToDevice(0x41018u, a1, 0, &v33, 8u) >= 0 )
        {
          LOBYTE(v15) = HIBYTE(v33);
          LOBYTE(v14) = BYTE6(v33);
          LOBYTE(v13) = BYTE5(v33);
          LogicalUnit = StorPortGetLogicalUnit(VhdmpAdapterExtension, v13, v14, v15);
          v17 = (struct _VHD_LUN_EXTENSION *)LogicalUnit;
          if ( LogicalUnit )
          {
            if ( !*(_BYTE *)LogicalUnit )
            {
              *(_BYTE *)LogicalUnit = 1;
              *(_QWORD *)(LogicalUnit + 16) = a1;
              v18 = VhdmpiAddRundownRefSurfaceByAddress(&v33);
              v19 = v18;
              if ( v18 )
              {
                if ( (*(_DWORD *)(v18 + 56) & 0x200) == 0 )
                  VhdmpiHwCreateLun(a1, v17, (struct _VHD_SURFACE *)v18);
                VhdmpiReleaseRundownRefVirtualDiskSurface(v19, 0);
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
        if ( v37->MinorFunction == 22 )
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
    v22 = a1;
    goto LABEL_43;
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x610u, 4u, 0x10u, "VhdmpPnp: START... DO: %p", a1);
  if ( !v9 )
  {
    v11 = -1073741810;
    goto LABEL_92;
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x61Au, 4u, 0x10u, "VhdmpPnp: START... Surface: %p", (const void *)v9);
  Index = 0;
  v11 = VhdmpiRegisterDiskWithDependencyDriver(v9, a1, v8, &Index);
  if ( v11 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
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
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x645u,
        4u,
        0x10u,
        "VhdmpPnp: unsurface the disk %p as the backing store is no longer accessible.",
        *(const void **)v36);
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v9 + 72)) <= 1 )
      __fastfail(0xEu);
    VhdmpiReleaseRundownRefVirtualDiskSurface(v9, 0);
    VhdmpiHaltSurfaceOrWait((struct _VHD_SURFACE *)v9);
    VhdmpiReleaseSurface(v9);
    goto LABEL_92;
  }
  v25 = IoOpenDeviceRegistryKey(a1, 1u, 0x20019u, &DeviceRegKey);
  if ( v25 >= 0 )
  {
    v26 = DeviceRegKey;
  }
  else
  {
    v26 = 0;
    DeviceRegKey = 0;
  }
  if ( !v26 )
    goto LABEL_85;
  Index = 0;
  if ( ZwEnumerateKey(v26, 0, KeyBasicInformation, KeyInformation, 0x100u, &ResultLength) < 0 )
    goto LABEL_84;
  v27 = Index;
  do
  {
    String1.Length = v41;
    String1.MaximumLength = v41;
    if ( v41 >= 0xF0u )
      continue;
    memmove(KeyInformation, Src, v41);
    String1.Buffer = (PWSTR)KeyInformation;
    if ( !RtlCompareUnicodeString(&String1, &stru_1400607C0, 1u) )
    {
      v25 = VhdmpiCleanupPartMgrKey(DeviceRegKey, &String1);
LABEL_81:
      ++v27;
      continue;
    }
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &String1;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v25 = ZwOpenKey(&KeyHandle, 0x10000u, &ObjectAttributes);
    if ( v25 >= 0 )
    {
      v25 = ZwDeleteKey(KeyHandle);
      ZwClose(KeyHandle);
      if ( v25 >= 0 )
        continue;
    }
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x69Fu,
        2u,
        0x10u,
        "VhdmpPnp: START: failed to delete the %S registry key. (Status 0x%x.)",
        String1.Buffer,
        v25);
    goto LABEL_81;
  }
  while ( ZwEnumerateKey(DeviceRegKey, v27, KeyBasicInformation, KeyInformation, 0x100u, &ResultLength) >= 0 );
  v4 = v38;
LABEL_84:
  ZwClose(DeviceRegKey);
LABEL_85:
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents("VhdmpiUnitPnp", 0x6B1u, 4u, 0x10u, "VhdmpPnp: Status of clearing registry keys is 0x%x.", v25);
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
    if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiUnitPnp",
        0x786u,
        4u,
        0x10u,
        "VhdmpPnp: failed MinorFunction 0x%x (Status 0x%x)",
        v37->MinorFunction,
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
0x1400b7ba4  mov     [rsp-8+arg_10], rbx
0x1400b7ba9  mov     [rsp-8+arg_18], rsi
0x1400b7bae  push    rbp
0x1400b7baf  push    rdi
0x1400b7bb0  push    r12
0x1400b7bb2  push    r13
0x1400b7bb4  push    r15
0x1400b7bb6  lea     rbp, [rsp-0D0h]
0x1400b7bbe  sub     rsp, 1D0h
0x1400b7bc5  mov     rax, cs:__security_cookie
0x1400b7bcc  xor     rax, rsp
0x1400b7bcf  mov     [rbp+0F0h+var_30], rax
0x1400b7bd6  mov     rax, [rdx+0B8h]
0x1400b7bdd  xorps   xmm1, xmm1
0x1400b7be0  xor     ebx, ebx
0x1400b7be2  mov     [rbp+0F0h+var_168], rdx
0x1400b7be6  mov     r13, rdx
0x1400b7be9  mov     [rsp+1F0h+var_198], 0
0x1400b7bf2  xorps   xmm0, xmm0
0x1400b7bf5  mov     [rsp+1F0h+var_1B0], 0
0x1400b7bfa  xor     edx, edx
0x1400b7bfc  mov     [rsp+1F0h+KeyHandle], 0
0x1400b7c05  lea     edi, [rbx+1]
0x1400b7c08  mov     [rsp+1F0h+var_1A0], 0
0x1400b7c10  mov     r15, rcx
0x1400b7c13  mov     [rsp+1F0h+DeviceRegKey], 0
0x1400b7c1c  movups  xmmword ptr [rsp+1F0h+String1.Length], xmm0
0x1400b7c21  mov     qword ptr [rsp+1F0h+var_178], rbx
0x1400b7c26  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.Length], xmm1
0x1400b7c2a  mov     [rbp+0F0h+var_170], rax
0x1400b7c2e  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.ObjectName], xmm1
0x1400b7c32  movups  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400b7c36  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400b7c3b  mov     rsi, rax
0x1400b7c3e  test    rax, rax
0x1400b7c41  jz      short loc_1400B7C4C
0x1400b7c43  mov     rbx, [rax+10h]
0x1400b7c47  mov     qword ptr [rsp+1F0h+var_178], rbx
0x1400b7c4c  mov     rax, [rbp+0F0h+var_170]
0x1400b7c50  mov     r12d, 10h
0x1400b7c56  movzx   edx, byte ptr [rax+1]
0x1400b7c5a  test    edx, edx
0x1400b7c5c  jz      loc_1400B7F0A
0x1400b7c62  sub     edx, 2
0x1400b7c65  jz      loc_1400B7E55
0x1400b7c6b  sub     edx, 5
0x1400b7c6e  jz      loc_1400B7E3B
0x1400b7c74  sub     edx, 2
0x1400b7c77  jz      loc_1400B7E13
0x1400b7c7d  sub     edx, 8
0x1400b7c80  jz      loc_1400B7D89
0x1400b7c86  sub     edx, 2
0x1400b7c89  jz      short loc_1400B7CD1
0x1400b7c8b  sub     edx, edi
0x1400b7c8d  jz      short loc_1400B7CC7
0x1400b7c8f  cmp     edx, 2
0x1400b7c92  mov     rdx, r13; struct _IRP *
0x1400b7c95  jnz     loc_1400B7EE8
0x1400b7c9b  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b7c9e  call    ?VhdmpiNotifyDeviceUsage@@YAJPEAU_VHD_SURFACE@@PEAU_IRP@@@Z; VhdmpiNotifyDeviceUsage(_VHD_SURFACE *,_IRP *)
0x1400b7ca3  mov     ebx, eax
0x1400b7ca5  test    eax, eax
0x1400b7ca7  js      loc_1400B7EFC
0x1400b7cad  mov     rax, cs:qword_14008D058
0x1400b7cb4  xor     dil, dil
0x1400b7cb7  mov     rdx, r13
0x1400b7cba  mov     rcx, r15
0x1400b7cbd  call    _guard_dispatch_icall
0x1400b7cc2  jmp     loc_1400B7EFA
0x1400b7cc7  or      qword ptr [r13+38h], 20h
0x1400b7ccc  jmp     loc_1400B7EE5
0x1400b7cd1  cmp     dword ptr [rax+8], 0
0x1400b7cd5  jnz     loc_1400B7EE5
0x1400b7cdb  lea     rax, [rsp+1F0h+var_198]
0x1400b7ce0  mov     [rsp+1F0h+var_1C0], 8; ULONG
0x1400b7ce8  mov     [rsp+1F0h+ResultLength], rax; PVOID
0x1400b7ced  xor     r9d, r9d
0x1400b7cf0  mov     r8b, dil
0x1400b7cf3  mov     [rsp+1F0h+Length], 0; InputBufferLength
0x1400b7cfb  mov     rdx, r15; DeviceObject
0x1400b7cfe  mov     ecx, 41018h; IoControlCode
0x1400b7d03  call    VhdmpiSendSyncDeviceIoControlToDevice
0x1400b7d08  test    eax, eax
0x1400b7d0a  js      loc_1400B7EE5
0x1400b7d10  mov     r9b, byte ptr [rsp+1F0h+var_198+7]
0x1400b7d15  mov     r8b, byte ptr [rsp+1F0h+var_198+6]
0x1400b7d1a  mov     dl, byte ptr [rsp+1F0h+var_198+5]
0x1400b7d1e  mov     rcx, cs:VhdmpAdapterExtension
0x1400b7d25  call    cs:__imp_StorPortGetLogicalUnit
0x1400b7d2c  nop     dword ptr [rax+rax+00h]
0x1400b7d31  mov     rbx, rax
0x1400b7d34  test    rax, rax
0x1400b7d37  jz      loc_1400B7EE5
0x1400b7d3d  cmp     byte ptr [rax], 0
0x1400b7d40  jnz     loc_1400B7EE5
0x1400b7d46  lea     rcx, [rsp+1F0h+var_198]
0x1400b7d4b  mov     [rax], dil
0x1400b7d4e  mov     [rax+10h], r15
0x1400b7d52  call    VhdmpiAddRundownRefSurfaceByAddress
0x1400b7d57  mov     rdi, rax
0x1400b7d5a  test    rax, rax
0x1400b7d5d  jz      loc_1400B7EE5
0x1400b7d63  test    dword ptr [rax+38h], 200h
0x1400b7d6a  jnz     short loc_1400B7D7A
0x1400b7d6c  mov     r8, rax; struct _VHD_SURFACE *
0x1400b7d6f  mov     rdx, rbx; struct _VHD_LUN_EXTENSION *
0x1400b7d72  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7d75  call    ?VhdmpiHwCreateLun@@YAEPEAU_DEVICE_OBJECT@@PEAU_VHD_LUN_EXTENSION@@PEAU_VHD_SURFACE@@@Z; VhdmpiHwCreateLun(_DEVICE_OBJECT *,_VHD_LUN_EXTENSION *,_VHD_SURFACE *)
0x1400b7d7a  xor     edx, edx
0x1400b7d7c  mov     rcx, rdi
0x1400b7d7f  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7d84  jmp     loc_1400B7EE5
0x1400b7d89  test    rsi, rsi
0x1400b7d8c  jz      short loc_1400B7E0C
0x1400b7d8e  mov     rax, rdi
0x1400b7d91  lock xadd [rsi+48h], rax
0x1400b7d97  add     rax, rdi
0x1400b7d9a  cmp     rax, rdi
0x1400b7d9d  jg      short loc_1400B7DA6
0x1400b7d9f  mov     ecx, 0Eh
0x1400b7da4  int     29h; Win8: RtlFailFast(ecx)
0x1400b7da6  xor     edx, edx
0x1400b7da8  mov     rcx, rsi
0x1400b7dab  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7db0  mov     eax, cs:dword_1400876D0
0x1400b7db6  cmp     eax, 4
0x1400b7db9  jbe     short loc_1400B7DF9
0x1400b7dbb  mov     rdx, r12
0x1400b7dbe  lea     rcx, dword_1400876D0
0x1400b7dc5  call    _tlgKeywordOn
0x1400b7dca  test    al, al
0x1400b7dcc  jz      short loc_1400B7DF9
0x1400b7dce  lea     rax, aVhdmppnpUnsurf_0; "VhdmpPnp: unsurface the disk %p as the "...
0x1400b7dd5  mov     [rsp+1F0h+ResultLength], rbx; char
0x1400b7dda  mov     edx, 74Ah; int
0x1400b7ddf  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7de4  mov     r9d, r12d; int
0x1400b7de7  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7dee  mov     r8d, 4; int
0x1400b7df4  call    TraceEvents
0x1400b7df9  mov     dl, dil
0x1400b7dfc  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b7dff  call    VhdmpiHaltSurfaceOrWait
0x1400b7e04  mov     rcx, rsi
0x1400b7e07  call    VhdmpiReleaseSurface
0x1400b7e0c  xor     ebx, ebx
0x1400b7e0e  jmp     loc_1400B8326
0x1400b7e13  test    rsi, rsi
0x1400b7e16  jz      loc_1400B7EE5
0x1400b7e1c  mov     rcx, [rax+8]
0x1400b7e20  mov     al, [rbx+50h]
0x1400b7e23  and     dword ptr [rcx+4], 0FFFFFFEFh
0x1400b7e27  test    al, al
0x1400b7e29  jnz     loc_1400B7EE5
0x1400b7e2f  or      dword ptr [rcx+4], 208h
0x1400b7e36  jmp     loc_1400B7EE5
0x1400b7e3b  cmp     dword ptr [rax+8], 2
0x1400b7e3f  mov     rdx, r13; Irp
0x1400b7e42  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7e45  jnz     loc_1400B7EEB
0x1400b7e4b  call    ?VhdmpiQueryPowerRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; VhdmpiQueryPowerRelations(_DEVICE_OBJECT *,_IRP *)
0x1400b7e50  jmp     loc_1400B7EF7
0x1400b7e55  lea     rax, [rsp+1F0h+var_1B0]
0x1400b7e5a  mov     [rsp+1F0h+var_1C0], edi; ULONG
0x1400b7e5e  mov     [rsp+1F0h+ResultLength], rax; PVOID
0x1400b7e63  xor     r9d, r9d
0x1400b7e66  xor     r8d, r8d
0x1400b7e69  mov     [rsp+1F0h+Length], 0; InputBufferLength
0x1400b7e71  mov     rdx, r15; DeviceObject
0x1400b7e74  mov     [rsp+1F0h+var_1B0], 0
0x1400b7e79  mov     ecx, 2D190Ch; IoControlCode
0x1400b7e7e  call    VhdmpiSendSyncDeviceIoControlToDevice
0x1400b7e83  mov     rcx, r15; struct _DEVICE_OBJECT *
0x1400b7e86  call    VhdmpiAddRefSurfaceByPdo
0x1400b7e8b  mov     rdi, rax
0x1400b7e8e  test    rax, rax
0x1400b7e91  jz      short loc_1400B7EE5
0x1400b7e93  lea     rcx, [rax+160h]; PKTIMER
0x1400b7e9a  call    cs:__imp_KeCancelTimer
0x1400b7ea1  nop     dword ptr [rax+rax+00h]
0x1400b7ea6  test    al, al
0x1400b7ea8  jz      short loc_1400B7EB7
0x1400b7eaa  mov     edx, 0C0000120h
0x1400b7eaf  mov     rcx, rdi
0x1400b7eb2  call    VhdmpiCancelSurfaceDiskRequestAndRelease
0x1400b7eb7  cmp     [rsp+1F0h+var_1B0], 0
0x1400b7ebc  jz      short loc_1400B7EDD
0x1400b7ebe  lea     rbx, [rdi+130h]
0x1400b7ec5  mov     rcx, rbx
0x1400b7ec8  call    VhdmpiAcquirePassiveLock
0x1400b7ecd  mov     rcx, rdi; struct _VHD_SURFACE *
0x1400b7ed0  call    ?VhdmpiHwDeleteLun@@YAXPEAU_VHD_SURFACE@@@Z; VhdmpiHwDeleteLun(_VHD_SURFACE *)
0x1400b7ed5  mov     rcx, rbx
0x1400b7ed8  call    VhdmpiReleasePassiveLock
0x1400b7edd  mov     rcx, rdi
0x1400b7ee0  call    VhdmpiReleaseSurface
0x1400b7ee5  mov     rdx, r13
0x1400b7ee8  mov     rcx, r15
0x1400b7eeb  mov     rax, cs:qword_14008D058
0x1400b7ef2  call    _guard_dispatch_icall
0x1400b7ef7  xor     dil, dil
0x1400b7efa  mov     ebx, eax
0x1400b7efc  test    rsi, rsi
0x1400b7eff  jz      loc_1400B8321
0x1400b7f05  jmp     loc_1400B8317
0x1400b7f0a  mov     eax, cs:dword_1400876D0
0x1400b7f10  cmp     eax, 4
0x1400b7f13  jbe     short loc_1400B7F53
0x1400b7f15  mov     rdx, r12
0x1400b7f18  lea     rcx, dword_1400876D0
0x1400b7f1f  call    _tlgKeywordOn
0x1400b7f24  test    al, al
0x1400b7f26  jz      short loc_1400B7F53
0x1400b7f28  lea     rax, aVhdmppnpStartD; "VhdmpPnp: START... DO: %p"
0x1400b7f2f  mov     [rsp+1F0h+ResultLength], r15; char
0x1400b7f34  mov     edx, 610h; int
0x1400b7f39  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7f3e  mov     r9d, r12d; int
0x1400b7f41  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7f48  mov     r8d, 4; int
0x1400b7f4e  call    TraceEvents
0x1400b7f53  test    rsi, rsi
0x1400b7f56  jnz     short loc_1400B7F62
0x1400b7f58  mov     ebx, 0C000000Eh
0x1400b7f5d  jmp     loc_1400B8326
0x1400b7f62  mov     eax, cs:dword_1400876D0
0x1400b7f68  cmp     eax, 4
0x1400b7f6b  jbe     short loc_1400B7FAB
0x1400b7f6d  mov     rdx, r12
0x1400b7f70  lea     rcx, dword_1400876D0
0x1400b7f77  call    _tlgKeywordOn
0x1400b7f7c  test    al, al
0x1400b7f7e  jz      short loc_1400B7FAB
0x1400b7f80  lea     rax, aVhdmppnpStartS; "VhdmpPnp: START... Surface: %p"
0x1400b7f87  mov     [rsp+1F0h+ResultLength], rsi; char
0x1400b7f8c  mov     edx, 61Ah; int
0x1400b7f91  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b7f96  mov     r9d, r12d; int
0x1400b7f99  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b7fa0  mov     r8d, 4; int
0x1400b7fa6  call    TraceEvents
0x1400b7fab  lea     r9, [rsp+1F0h+Index]
0x1400b7fb0  mov     [rsp+1F0h+Index], 0
0x1400b7fb8  mov     rdx, r15
0x1400b7fbb  mov     rcx, rsi
0x1400b7fbe  call    VhdmpiRegisterDiskWithDependencyDriver
0x1400b7fc3  mov     ebx, eax
0x1400b7fc5  test    eax, eax
0x1400b7fc7  jns     short loc_1400B801E
0x1400b7fc9  mov     eax, cs:dword_1400876D0
0x1400b7fcf  cmp     eax, 2
0x1400b7fd2  jbe     loc_1400B8317
0x1400b7fd8  mov     rdx, r12
0x1400b7fdb  lea     rcx, dword_1400876D0
0x1400b7fe2  call    _tlgKeywordOn
0x1400b7fe7  test    al, al
0x1400b7fe9  jz      loc_1400B8317
0x1400b7fef  lea     rax, aVhdmppnpStartF_0; "VhdmpPnp: START: failed to register w/ "...
0x1400b7ff6  mov     dword ptr [rsp+1F0h+ResultLength], ebx; char
0x1400b7ffa  mov     edx, 634h; int
0x1400b7fff  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b8004  mov     r9d, r12d; int
0x1400b8007  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b800e  mov     r8d, 2; int
0x1400b8014  call    TraceEvents
0x1400b8019  jmp     loc_1400B8317
0x1400b801e  mov     ebx, [rsp+1F0h+Index]
0x1400b8022  test    ebx, ebx
0x1400b8024  jns     loc_1400B80B2
0x1400b802a  mov     eax, cs:dword_1400876D0
0x1400b8030  cmp     eax, 4
0x1400b8033  jbe     short loc_1400B8078
0x1400b8035  mov     rdx, r12
0x1400b8038  lea     rcx, dword_1400876D0
0x1400b803f  call    _tlgKeywordOn
0x1400b8044  test    al, al
0x1400b8046  jz      short loc_1400B8078
0x1400b8048  mov     rax, qword ptr [rsp+1F0h+var_178]
0x1400b804d  lea     rcx, aVhdmpiunitpnp; "VhdmpiUnitPnp"
0x1400b8054  mov     [rsp+1F0h+ResultLength], rax; char
0x1400b8059  mov     edx, 645h; int
0x1400b805e  lea     rax, aVhdmppnpUnsurf; "VhdmpPnp: unsurface the disk %p as the "...
0x1400b8065  mov     r9d, r12d; int
0x1400b8068  mov     r8d, 4; int
0x1400b806e  mov     qword ptr [rsp+1F0h+Length], rax; char *
0x1400b8073  call    TraceEvents
0x1400b8078  mov     rax, rdi
0x1400b807b  lock xadd [rsi+48h], rax
0x1400b8081  add     rax, rdi
0x1400b8084  cmp     rax, rdi
0x1400b8087  jg      short loc_1400B8090
0x1400b8089  mov     ecx, 0Eh
0x1400b808e  int     29h; Win8: RtlFailFast(ecx)
0x1400b8090  xor     edx, edx
0x1400b8092  mov     rcx, rsi
0x1400b8095  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b809a  mov     dl, dil
0x1400b809d  mov     rcx, rsi; struct _VHD_SURFACE *
0x1400b80a0  call    VhdmpiHaltSurfaceOrWait
0x1400b80a5  mov     rcx, rsi
  ... truncated ...
```
