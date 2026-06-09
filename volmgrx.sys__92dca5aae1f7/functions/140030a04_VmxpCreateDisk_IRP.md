# VmxpCreateDisk(_IRP *)

- ea: `0x140030a04`
- end: `0x14003117a`
- name: `?VmxpCreateDisk@@YAJPEAU_IRP@@@Z`
- size: `1910`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x14005c9a0`

## callees

- `0x140005f80`
- `0x14000774c`
- `0x140008d50`
- `0x140008df0`
- `0x14000982c`
- `0x1400099d8`
- `0x14001b960`
- `0x14001be80`
- `0x14002e230`
- `0x14002fbf4`
- `0x140030a04`
- `0x1400314e8`
- `0x140033750`
- `0x140033b44`
- `0x1400358f4`
- `0x14003763c`
- `0x140046fd4`
- `0x14005abb4`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140030c1d`
- `ntoskrnl!ObfDereferenceObject` at `0x140030c32`
- `ntoskrnl!ObfDereferenceObject` at `0x140030c8e`
- `ntoskrnl!ObfDereferenceObject` at `0x140030d17`
- `ntoskrnl!ObfDereferenceObject` at `0x140031105`
- `ntoskrnl!ObfDereferenceObject` at `0x140030c1d`
- `ntoskrnl!ObfDereferenceObject` at `0x140030c32`
- `ntoskrnl!ObfDereferenceObject` at `0x140030c8e`
- `ntoskrnl!ObfDereferenceObject` at `0x140030d17`
- `ntoskrnl!ObfDereferenceObject` at `0x140031105`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030b81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030b81`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140030ba1`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140030ba1`
- `ntoskrnl!ExUuidCreate` at `0x140030f01`
- `ntoskrnl!ExUuidCreate` at `0x140030f01`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140030bf3`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140030bf3`

## pseudocode

```c
__int64 __fastcall VmxpCreateDisk(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _IRP *MasterIrp; // r14
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  NTSTATUS DeviceObjectPointer; // edi
  __int64 v6; // rdx
  struct _DEVICE_OBJECT *v7; // rsi
  struct VMX_DISK_DEVICE *DiskDeviceByPdo; // rbx
  struct VMX_DISK_DEVICE *v9; // rax
  char *v10; // rax
  VMX_GLOBAL_DATA **v11; // rcx
  unsigned int v12; // edx
  struct VMX_DISK_DEVICE *v13; // rax
  struct VMX_DISK_DEVICE **v14; // rcx
  unsigned int v15; // edx
  struct VMX_DISK_DEVICE *v16; // rax
  struct VMX_DISK_DEVICE **v17; // rcx
  char *v18; // rax
  unsigned int v19; // edx
  char *v20; // rsi
  unsigned int v21; // edx
  unsigned int v22; // edx
  struct VMX_DISK_DEVICE *v23; // rcx
  struct VMX_DISK_DEVICE **v24; // rax
  VMX_GLOBAL_DATA *v25; // rcx
  VMX_GLOBAL_DATA **v26; // rdx
  int v27; // eax
  _QWORD *v28; // rax
  void **v29; // rcx
  unsigned int v30; // edx
  __int64 v31; // rax
  struct VMX_DISK_DEVICE *v33; // rax
  struct VMX_DISK_DEVICE **v34; // rcx
  VMX_NOTIFICATION_QUEUE *v35; // rcx
  __int64 v36; // rdx
  char v37; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v38[7]; // [rsp+41h] [rbp-BFh] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-B8h] BYREF
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-B0h] BYREF
  struct VMX_PACK *v41; // [rsp+58h] [rbp-A8h] BYREF
  struct VMX_RECORD *v42; // [rsp+60h] [rbp-A0h] BYREF
  struct _DEVICE_OBJECT *v43; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  __int128 v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h]
  wchar_t pszDest[56]; // [rsp+B0h] [rbp-50h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  v47 = 0;
  v37 = 0;
  FileObject = 0;
  DeviceObject = 0;
  DestinationString = 0;
  v43 = 0;
  v45 = 0;
  v41 = 0;
  v46 = 0;
  v42 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)v38, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v4 = WPP_GLOBAL_Control;
    DeviceObjectPointer = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 117;
    goto LABEL_16;
  }
  DeviceObjectPointer = -1073741811;
  if ( CurrentStackLocation->Parameters.Create.Options < 0x58 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 118;
    goto LABEL_16;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 119;
    goto LABEL_16;
  }
  RtlStringCbPrintfW(pszDest, 0x64u, L"\\Device\\Harddisk%lu\\Partition0", *(unsigned int *)&MasterIrp->Type);
  RtlInitUnicodeString(&DestinationString, pszDest);
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x80u, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 120;
    goto LABEL_16;
  }
  DeviceObject = IoGetAttachedDeviceReference(FileObject->DeviceObject);
  DeviceObjectPointer = VmxpGetTargetDevice(DeviceObject, FileObject, (PVOID *)&v43);
  ObfDereferenceObject(FileObject);
  if ( DeviceObjectPointer < 0 )
  {
    ObfDereferenceObject(DeviceObject);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 121;
    goto LABEL_16;
  }
  v7 = v43;
  DiskDeviceByPdo = VmxpFindDiskDeviceByPdo(v43);
  if ( DiskDeviceByPdo )
  {
    ObfDereferenceObject(DeviceObject);
    if ( VmxpFindPhysicalDiskByDevice(DiskDeviceByPdo) )
    {
      v4 = WPP_GLOBAL_Control;
      DeviceObjectPointer = -1070071801;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_95;
      }
      v6 = 124;
      goto LABEL_16;
    }
  }
  else
  {
    DeviceObjectPointer = VmxpSendDeviceControl(DeviceObject, 0x70000u, 0, 0, &v46, 0x18u, 0);
    if ( DeviceObjectPointer < 0 )
    {
      ObfDereferenceObject(DeviceObject);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_95;
      }
      v6 = 122;
      goto LABEL_16;
    }
    v9 = (struct VMX_DISK_DEVICE *)VMX_ALLOCATED_OBJECT::operator new(64, 66, 1682206038);
    DiskDeviceByPdo = v9;
    if ( !v9 )
    {
      ObfDereferenceObject(DeviceObject);
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        goto LABEL_94;
      }
      v36 = 123;
      goto LABEL_93;
    }
    memset(v9, 0, 0x40u);
    *((_DWORD *)DiskDeviceByPdo + 12) = 1;
    *((_QWORD *)DiskDeviceByPdo + 2) = v7;
    *((_QWORD *)DiskDeviceByPdo + 3) = DeviceObject;
    *((_DWORD *)DiskDeviceByPdo + 8) = *(_DWORD *)&MasterIrp->Type;
    *((_DWORD *)DiskDeviceByPdo + 9) = HIDWORD(v47);
    v10 = (char *)Global + 168;
    v11 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 22);
    if ( *v11 != (VMX_GLOBAL_DATA *)((char *)Global + 168) )
      goto LABEL_88;
    *(_QWORD *)DiskDeviceByPdo = v10;
    *((_QWORD *)DiskDeviceByPdo + 1) = v11;
    *v11 = DiskDeviceByPdo;
    *((_QWORD *)v10 + 1) = DiskDeviceByPdo;
  }
  DeviceObjectPointer = VMX_DISK_DEVICE::IsDiskClustered(DiskDeviceByPdo, &v37);
  if ( DeviceObjectPointer < 0 )
  {
LABEL_44:
    v13 = *(struct VMX_DISK_DEVICE **)DiskDeviceByPdo;
    if ( *(struct VMX_DISK_DEVICE **)(*(_QWORD *)DiskDeviceByPdo + 8LL) == DiskDeviceByPdo )
    {
      v14 = (struct VMX_DISK_DEVICE **)*((_QWORD *)DiskDeviceByPdo + 1);
      if ( *v14 == DiskDeviceByPdo )
      {
        *v14 = v13;
        *((_QWORD *)v13 + 1) = v14;
        VMX_DISK_DEVICE::`scalar deleting destructor'(DiskDeviceByPdo, v12);
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          goto LABEL_95;
        }
        v6 = 125;
        goto LABEL_16;
      }
    }
LABEL_88:
    __fastfail(3u);
  }
  if ( v37 )
  {
    DeviceObjectPointer = -1070071783;
    goto LABEL_44;
  }
  DeviceObjectPointer = VMX_DISK_DEVICE::GetDiskAttributes(DiskDeviceByPdo, &v45);
  if ( DeviceObjectPointer < 0 )
    goto LABEL_53;
  if ( (BYTE8(v45) & 1) != 0 )
  {
    DeviceObjectPointer = -2147483632;
LABEL_53:
    v16 = *(struct VMX_DISK_DEVICE **)DiskDeviceByPdo;
    if ( *(struct VMX_DISK_DEVICE **)(*(_QWORD *)DiskDeviceByPdo + 8LL) != DiskDeviceByPdo )
      goto LABEL_88;
    v17 = (struct VMX_DISK_DEVICE **)*((_QWORD *)DiskDeviceByPdo + 1);
    if ( *v17 != DiskDeviceByPdo )
      goto LABEL_88;
    *v17 = v16;
    *((_QWORD *)v16 + 1) = v17;
    VMX_DISK_DEVICE::`scalar deleting destructor'(DiskDeviceByPdo, v15);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 126;
    goto LABEL_16;
  }
  *((_BYTE *)DiskDeviceByPdo + 54) = 1;
  v18 = (char *)VMX_ALLOCATED_OBJECT::operator new(128, 258, 1682992470);
  v20 = v18;
  if ( !v18 )
  {
    v33 = *(struct VMX_DISK_DEVICE **)DiskDeviceByPdo;
    if ( *(struct VMX_DISK_DEVICE **)(*(_QWORD *)DiskDeviceByPdo + 8LL) != DiskDeviceByPdo )
      goto LABEL_88;
    v34 = (struct VMX_DISK_DEVICE **)*((_QWORD *)DiskDeviceByPdo + 1);
    if ( *v34 != DiskDeviceByPdo )
      goto LABEL_88;
    *v34 = v33;
    *((_QWORD *)v33 + 1) = v34;
    VMX_DISK_DEVICE::`scalar deleting destructor'(DiskDeviceByPdo, v19);
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
LABEL_94:
      DeviceObjectPointer = -1073741670;
      goto LABEL_95;
    }
    v36 = 127;
LABEL_93:
    WPP_SF_d(*((_QWORD *)v35 + 3), v36, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225626LL);
    goto LABEL_94;
  }
  memset(v18, 0, 0x80u);
  DeviceObjectPointer = ExUuidCreate((UUID *)(v20 + 44));
  if ( DeviceObjectPointer < 0 )
  {
    VMX_PHYSICAL_DISK::`scalar deleting destructor'((VMX_PHYSICAL_DISK *)v20, v21);
    v23 = *(struct VMX_DISK_DEVICE **)DiskDeviceByPdo;
    if ( *(struct VMX_DISK_DEVICE **)(*(_QWORD *)DiskDeviceByPdo + 8LL) != DiskDeviceByPdo )
      goto LABEL_88;
    v24 = (struct VMX_DISK_DEVICE **)*((_QWORD *)DiskDeviceByPdo + 1);
    if ( *v24 != DiskDeviceByPdo )
      goto LABEL_88;
    *v24 = v23;
    *((_QWORD *)v23 + 1) = v24;
    VMX_DISK_DEVICE::`scalar deleting destructor'(DiskDeviceByPdo, v22);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 128;
    goto LABEL_16;
  }
  v25 = Global;
  *((_QWORD *)v20 + 2) = DiskDeviceByPdo;
  v26 = (VMX_GLOBAL_DATA **)*((_QWORD *)v25 + 24);
  if ( *v26 != (VMX_GLOBAL_DATA *)((char *)v25 + 184) )
    goto LABEL_88;
  *((_QWORD *)v20 + 1) = v26;
  *(_QWORD *)v20 = (char *)v25 + 184;
  *v26 = (VMX_GLOBAL_DATA *)v20;
  *((_QWORD *)v25 + 24) = v20;
  VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)v25 + 36), 1, v20);
  if ( *((_BYTE *)&MasterIrp->Size + 2) )
    v27 = VmxpCreateDiskInNewPack(
            (struct VMX_PHYSICAL_DISK *)v20,
            (unsigned __int16 *)&MasterIrp->AssociatedIrp,
            &v41,
            &v42);
  else
    v27 = VmxpCreateDiskInPack((struct VMX_PHYSICAL_DISK *)v20, (struct _GUID *)&MasterIrp->MdlAddress, &v41, &v42);
  DeviceObjectPointer = v27;
  if ( v27 < 0 )
  {
    v28 = *(_QWORD **)v20;
    if ( *(char **)(*(_QWORD *)v20 + 8LL) != v20 )
      goto LABEL_88;
    v29 = (void **)*((_QWORD *)v20 + 1);
    if ( *v29 != v20 )
      goto LABEL_88;
    *v29 = v28;
    v28[1] = v29;
    VMX_NOTIFICATION_QUEUE::AddInvalidDiskNotification(*((_QWORD *)Global + 36), 2, v20);
    VMX_PHYSICAL_DISK::`scalar deleting destructor'((VMX_PHYSICAL_DISK *)v20, v30);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_95;
    }
    v6 = 129;
LABEL_16:
    WPP_SF_d(
      *((_QWORD *)v4 + 3),
      v6,
      WPP_2f8af752156e3401cd435973c831895d_Traceguids,
      (unsigned int)DeviceObjectPointer);
LABEL_95:
    VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)v38);
    return (unsigned int)DeviceObjectPointer;
  }
  *(_OWORD *)&MasterIrp->Type = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v41 + 2) + 8LL) + 8LL);
  if ( (*((_BYTE *)v42 + 64) & 1) != 0 )
    v31 = *((_QWORD *)v42 + 6);
  else
    v31 = *((_QWORD *)v42 + 5);
  *(_OWORD *)&MasterIrp->Flags = *(_OWORD *)(v31 + 72);
  a1->IoStatus.Information = 32;
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)v38);
  return 0;
}

```

## disassembly

```asm
0x140030a04  push    rbp
0x140030a06  push    rbx
0x140030a07  push    rsi
0x140030a08  push    rdi
0x140030a09  push    r14
0x140030a0b  push    r15
0x140030a0d  lea     rbp, [rsp-38h]
0x140030a12  sub     rsp, 138h
0x140030a19  mov     rax, cs:__security_cookie
0x140030a20  xor     rax, rsp
0x140030a23  mov     [rbp+60h+var_40], rax
0x140030a27  mov     rbx, [rcx+0B8h]
0x140030a2e  xorps   xmm0, xmm0
0x140030a31  mov     r14, [rcx+18h]
0x140030a35  xor     eax, eax
0x140030a37  mov     r15, rcx
0x140030a3a  mov     [rbp+60h+var_C0], rax
0x140030a3e  xorps   xmm1, xmm1
0x140030a41  mov     [rsp+160h+var_120], al
0x140030a45  lea     rcx, [rsp+160h+var_11F]; this
0x140030a4a  mov     [rsp+160h+FileObject], 0
0x140030a53  xor     edx, edx; unsigned __int8
0x140030a55  mov     [rsp+160h+DeviceObject], 0
0x140030a5e  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x140030a63  mov     [rsp+160h+var_F8], 0
0x140030a6c  movups  [rbp+60h+var_E0], xmm0
0x140030a70  mov     [rsp+160h+var_108], 0
0x140030a79  movups  [rbp+60h+var_D0], xmm1
0x140030a7d  mov     [rsp+160h+var_100], 0
0x140030a86  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x140030a8b  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140030a92  cmp     byte ptr [rax+111h], 0
0x140030a99  jnz     short loc_140030AD3
0x140030a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030aa2  lea     rax, WPP_GLOBAL_Control
0x140030aa9  mov     edi, 0C0380019h
0x140030aae  cmp     rcx, rax
0x140030ab1  jz      loc_140031151
0x140030ab7  mov     eax, [rcx+2Ch]
0x140030aba  test    al, 2
0x140030abc  jz      loc_140031151
0x140030ac2  cmp     byte ptr [rcx+29h], 2
0x140030ac6  jb      loc_140031151
0x140030acc  mov     edx, 75h ; 'u'
0x140030ad1  jmp     short loc_140030B48
0x140030ad3  cmp     dword ptr [rbx+10h], 58h ; 'X'
0x140030ad7  mov     edi, 0C000000Dh
0x140030adc  jnb     short loc_140030B11
0x140030ade  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ae5  lea     rax, WPP_GLOBAL_Control
0x140030aec  cmp     rcx, rax
0x140030aef  jz      loc_140031151
0x140030af5  mov     eax, [rcx+2Ch]
0x140030af8  test    al, 2
0x140030afa  jz      loc_140031151
0x140030b00  cmp     byte ptr [rcx+29h], 2
0x140030b04  jb      loc_140031151
0x140030b0a  mov     edx, 76h ; 'v'
0x140030b0f  jmp     short loc_140030B48
0x140030b11  cmp     dword ptr [rbx+8], 20h ; ' '
0x140030b15  jnb     short loc_140030B60
0x140030b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b1e  lea     rax, WPP_GLOBAL_Control
0x140030b25  cmp     rcx, rax
0x140030b28  jz      loc_140031151
0x140030b2e  mov     eax, [rcx+2Ch]
0x140030b31  test    al, 2
0x140030b33  jz      loc_140031151
0x140030b39  cmp     byte ptr [rcx+29h], 2
0x140030b3d  jb      loc_140031151
0x140030b43  mov     edx, 77h ; 'w'
0x140030b48  mov     rcx, [rcx+18h]
0x140030b4c  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x140030b53  mov     r9d, edi
0x140030b56  call    WPP_SF_d
0x140030b5b  jmp     loc_140031151
0x140030b60  mov     r9d, [r14]
0x140030b63  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%lu\\Partition0"
0x140030b6a  mov     edx, 64h ; 'd'; cbDest
0x140030b6f  lea     rcx, [rbp+60h+pszDest]; pszDest
0x140030b73  call    RtlStringCbPrintfW
0x140030b78  lea     rdx, [rbp+60h+pszDest]; SourceString
0x140030b7c  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x140030b81  call    cs:__imp_RtlInitUnicodeString
0x140030b88  nop     dword ptr [rax+rax+00h]
0x140030b8d  lea     r9, [rsp+160h+DeviceObject]; DeviceObject
0x140030b92  mov     edx, 80h; DesiredAccess
0x140030b97  lea     r8, [rsp+160h+FileObject]; FileObject
0x140030b9c  lea     rcx, [rsp+160h+DestinationString]; ObjectName
0x140030ba1  call    cs:__imp_IoGetDeviceObjectPointer
0x140030ba8  nop     dword ptr [rax+rax+00h]
0x140030bad  mov     edi, eax
0x140030baf  test    eax, eax
0x140030bb1  jns     short loc_140030BEA
0x140030bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140030bba  lea     rax, WPP_GLOBAL_Control
0x140030bc1  cmp     rcx, rax
0x140030bc4  jz      loc_140031151
0x140030bca  mov     edx, [rcx+2Ch]
0x140030bcd  test    dl, 2
0x140030bd0  jz      loc_140031151
0x140030bd6  cmp     byte ptr [rcx+29h], 2
0x140030bda  jb      loc_140031151
0x140030be0  mov     edx, 78h ; 'x'
0x140030be5  jmp     loc_140030B48
0x140030bea  mov     rcx, [rsp+160h+FileObject]
0x140030bef  mov     rcx, [rcx+8]; DeviceObject
0x140030bf3  call    cs:__imp_IoGetAttachedDeviceReference
0x140030bfa  nop     dword ptr [rax+rax+00h]
0x140030bff  mov     rdx, [rsp+160h+FileObject]; struct _FILE_OBJECT *
0x140030c04  lea     r8, [rsp+160h+var_F8]; struct _DEVICE_OBJECT **
0x140030c09  mov     rcx, rax; DeviceObject
0x140030c0c  mov     [rsp+160h+DeviceObject], rax
0x140030c11  call    ?VmxpGetTargetDevice@@YAJPEAU_DEVICE_OBJECT@@PEAU_FILE_OBJECT@@PEAPEAU1@@Z; VmxpGetTargetDevice(_DEVICE_OBJECT *,_FILE_OBJECT *,_DEVICE_OBJECT * *)
0x140030c16  mov     rcx, [rsp+160h+FileObject]; Object
0x140030c1b  mov     edi, eax
0x140030c1d  call    cs:__imp_ObfDereferenceObject
0x140030c24  nop     dword ptr [rax+rax+00h]
0x140030c29  test    edi, edi
0x140030c2b  jns     short loc_140030C74
0x140030c2d  mov     rcx, [rsp+160h+DeviceObject]; Object
0x140030c32  call    cs:__imp_ObfDereferenceObject
0x140030c39  nop     dword ptr [rax+rax+00h]
0x140030c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c45  lea     rax, WPP_GLOBAL_Control
0x140030c4c  cmp     rcx, rax
0x140030c4f  jz      loc_140031151
0x140030c55  mov     eax, [rcx+2Ch]
0x140030c58  test    al, 2
0x140030c5a  jz      loc_140031151
0x140030c60  cmp     byte ptr [rcx+29h], 2
0x140030c64  jb      loc_140031151
0x140030c6a  mov     edx, 79h ; 'y'
0x140030c6f  jmp     loc_140030B48
0x140030c74  mov     rsi, [rsp+160h+var_F8]
0x140030c79  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x140030c7c  call    ?VmxpFindDiskDeviceByPdo@@YAPEAVVMX_DISK_DEVICE@@PEAU_DEVICE_OBJECT@@@Z; VmxpFindDiskDeviceByPdo(_DEVICE_OBJECT *)
0x140030c81  mov     rcx, [rsp+160h+DeviceObject]; DeviceObject
0x140030c86  mov     rbx, rax
0x140030c89  test    rax, rax
0x140030c8c  jz      short loc_140030CE6
0x140030c8e  call    cs:__imp_ObfDereferenceObject
0x140030c95  nop     dword ptr [rax+rax+00h]
0x140030c9a  mov     rcx, rbx; struct VMX_DISK_DEVICE *
0x140030c9d  call    ?VmxpFindPhysicalDiskByDevice@@YAPEAVVMX_PHYSICAL_DISK@@PEAVVMX_DISK_DEVICE@@@Z; VmxpFindPhysicalDiskByDevice(VMX_DISK_DEVICE *)
0x140030ca2  test    rax, rax
0x140030ca5  jz      loc_140030DCF
0x140030cab  mov     rcx, cs:WPP_GLOBAL_Control
0x140030cb2  lea     rax, WPP_GLOBAL_Control
0x140030cb9  mov     edi, 0C0380007h
0x140030cbe  cmp     rcx, rax
0x140030cc1  jz      loc_140031151
0x140030cc7  mov     eax, [rcx+2Ch]
0x140030cca  test    al, 2
0x140030ccc  jz      loc_140031151
0x140030cd2  cmp     byte ptr [rcx+29h], 2
0x140030cd6  jb      loc_140031151
0x140030cdc  mov     edx, 7Ch ; '|'
0x140030ce1  jmp     loc_140030B48
0x140030ce6  mov     [rsp+160h+var_130], 0; BOOLEAN
0x140030ceb  lea     rax, [rbp+60h+var_D0]
0x140030cef  mov     [rsp+160h+var_138], 18h; ULONG
0x140030cf7  xor     r9d, r9d; InputBufferLength
0x140030cfa  xor     r8d, r8d; InputBuffer
0x140030cfd  mov     [rsp+160h+var_140], rax; PVOID
0x140030d02  mov     edx, 70000h; IoControlCode
0x140030d07  call    ?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140030d0c  mov     edi, eax
0x140030d0e  test    eax, eax
0x140030d10  jns     short loc_140030D59
0x140030d12  mov     rcx, [rsp+160h+DeviceObject]; Object
0x140030d17  call    cs:__imp_ObfDereferenceObject
0x140030d1e  nop     dword ptr [rax+rax+00h]
0x140030d23  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d2a  lea     rax, WPP_GLOBAL_Control
0x140030d31  cmp     rcx, rax
0x140030d34  jz      loc_140031151
0x140030d3a  mov     eax, [rcx+2Ch]
0x140030d3d  test    al, 2
0x140030d3f  jz      loc_140031151
0x140030d45  cmp     byte ptr [rcx+29h], 2
0x140030d49  jb      loc_140031151
0x140030d4f  mov     edx, 7Ah ; 'z'
0x140030d54  jmp     loc_140030B48
0x140030d59  mov     edx, 42h ; 'B'; unsigned __int64
0x140030d5e  mov     r8d, 64446D56h; unsigned int
0x140030d64  lea     edi, [rdx-2]
0x140030d67  mov     ecx, edi; unsigned __int64
0x140030d69  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140030d6e  mov     rbx, rax
0x140030d71  test    rax, rax
0x140030d74  jz      loc_140031100
0x140030d7a  mov     r8d, edi; Size
0x140030d7d  xor     edx, edx; Val
0x140030d7f  mov     rcx, rax; void *
0x140030d82  call    memset
0x140030d87  mov     dword ptr [rbx+30h], 1
0x140030d8e  mov     [rbx+10h], rsi
0x140030d92  mov     rax, [rsp+160h+DeviceObject]
0x140030d97  mov     [rbx+18h], rax
0x140030d9b  mov     eax, [r14]
0x140030d9e  mov     [rbx+20h], eax
0x140030da1  mov     eax, dword ptr [rbp+60h+var_C0+4]
0x140030da4  mov     [rbx+24h], eax
0x140030da7  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140030dae  add     rax, 0A8h
0x140030db4  mov     rcx, [rax+8]
0x140030db8  cmp     [rcx], rax
0x140030dbb  jnz     loc_1400310F9
0x140030dc1  mov     [rbx], rax
0x140030dc4  mov     [rbx+8], rcx
0x140030dc8  mov     [rcx], rbx
0x140030dcb  mov     [rax+8], rbx
0x140030dcf  lea     rdx, [rsp+160h+var_120]; PVOID
0x140030dd4  mov     rcx, rbx; this
0x140030dd7  call    ?IsDiskClustered@VMX_DISK_DEVICE@@QEAAJPEAE@Z; VMX_DISK_DEVICE::IsDiskClustered(uchar *)
0x140030ddc  mov     edi, eax
0x140030dde  test    eax, eax
0x140030de0  js      short loc_140030DEE
0x140030de2  cmp     [rsp+160h+var_120], 0
0x140030de7  jz      short loc_140030E4D
0x140030de9  mov     edi, 0C0380019h
0x140030dee  mov     rax, [rbx]
0x140030df1  cmp     [rax+8], rbx
0x140030df5  jnz     loc_1400310F9
0x140030dfb  mov     rcx, [rbx+8]
0x140030dff  cmp     [rcx], rbx
0x140030e02  jnz     loc_1400310F9
0x140030e08  mov     [rcx], rax
0x140030e0b  mov     [rax+8], rcx
0x140030e0f  mov     rcx, rbx; this
0x140030e12  call    ??_GVMX_DISK_DEVICE@@QEAAPEAXI@Z; VMX_DISK_DEVICE::`scalar deleting destructor'(uint)
0x140030e17  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e1e  lea     rax, WPP_GLOBAL_Control
0x140030e25  cmp     rcx, rax
0x140030e28  jz      loc_140031151
0x140030e2e  mov     eax, [rcx+2Ch]
0x140030e31  test    al, 2
0x140030e33  jz      loc_140031151
0x140030e39  cmp     byte ptr [rcx+29h], 2
0x140030e3d  jb      loc_140031151
0x140030e43  mov     edx, 7Dh ; '}'
0x140030e48  jmp     loc_140030B48
0x140030e4d  lea     rdx, [rbp+60h+var_E0]; PVOID
0x140030e51  mov     rcx, rbx; this
0x140030e54  call    ?GetDiskAttributes@VMX_DISK_DEVICE@@QEAAJPEAU_GET_DISK_ATTRIBUTES@@@Z; VMX_DISK_DEVICE::GetDiskAttributes(_GET_DISK_ATTRIBUTES *)
0x140030e59  mov     edi, eax
0x140030e5b  test    eax, eax
0x140030e5d  js      short loc_140030E6A
0x140030e5f  test    byte ptr [rbp+60h+var_E0+8], 1
0x140030e63  jz      short loc_140030EC9
0x140030e65  mov     edi, 80000010h
0x140030e6a  mov     rax, [rbx]
0x140030e6d  cmp     [rax+8], rbx
0x140030e71  jnz     loc_1400310F9
0x140030e77  mov     rcx, [rbx+8]
0x140030e7b  cmp     [rcx], rbx
0x140030e7e  jnz     loc_1400310F9
0x140030e84  mov     [rcx], rax
0x140030e87  mov     [rax+8], rcx
0x140030e8b  mov     rcx, rbx; this
0x140030e8e  call    ??_GVMX_DISK_DEVICE@@QEAAPEAXI@Z; VMX_DISK_DEVICE::`scalar deleting destructor'(uint)
0x140030e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e9a  lea     rax, WPP_GLOBAL_Control
0x140030ea1  cmp     rcx, rax
0x140030ea4  jz      loc_140031151
0x140030eaa  mov     eax, [rcx+2Ch]
0x140030ead  test    al, 2
0x140030eaf  jz      loc_140031151
0x140030eb5  cmp     byte ptr [rcx+29h], 2
0x140030eb9  jb      loc_140031151
0x140030ebf  mov     edx, 7Eh ; '~'
0x140030ec4  jmp     loc_140030B48
0x140030ec9  mov     edi, 80h
0x140030ece  mov     byte ptr [rbx+36h], 1
0x140030ed2  mov     ecx, edi; unsigned __int64
0x140030ed4  mov     edx, 102h; unsigned __int64
0x140030ed9  mov     r8d, 64506D56h; unsigned int
0x140030edf  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140030ee4  mov     rsi, rax
0x140030ee7  test    rax, rax
0x140030eea  jz      loc_1400310B1
0x140030ef0  mov     r8d, edi; Size
0x140030ef3  xor     edx, edx; Val
0x140030ef5  mov     rcx, rax; void *
0x140030ef8  call    memset
0x140030efd  lea     rcx, [rsi+2Ch]; Uuid
0x140030f01  call    cs:__imp_ExUuidCreate
0x140030f08  nop     dword ptr [rax+rax+00h]
0x140030f0d  mov     edi, eax
0x140030f0f  test    eax, eax
0x140030f11  jns     short loc_140030F7A
0x140030f13  mov     rcx, rsi; this
0x140030f16  call    ??_GVMX_PHYSICAL_DISK@@QEAAPEAXI@Z; VMX_PHYSICAL_DISK::`scalar deleting destructor'(uint)
0x140030f1b  mov     rcx, [rbx]
0x140030f1e  cmp     [rcx+8], rbx
0x140030f22  jnz     loc_1400310F9
0x140030f28  mov     rax, [rbx+8]
0x140030f2c  cmp     [rax], rbx
0x140030f2f  jnz     loc_1400310F9
  ... truncated ...
```
