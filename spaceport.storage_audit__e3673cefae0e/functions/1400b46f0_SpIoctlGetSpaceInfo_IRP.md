# SpIoctlGetSpaceInfo(_IRP *)

- ea: `0x1400b46f0`
- end: `0x1400b520d`
- name: `?SpIoctlGetSpaceInfo@@YAJPEAU_IRP@@@Z`
- size: `2845`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b57b0`

## callees

- `0x14000b3e0`
- `0x14000c630`
- `0x14000cc80`
- `0x1400187f0`
- `0x140018810`
- `0x140018f10`
- `0x140019060`
- `0x14001d3f0`
- `0x14001e4a0`
- `0x14001eac0`
- `0x140021a90`
- `0x140026860`
- `0x140026f10`
- `0x140027060`
- `0x140027110`
- `0x140027120`
- `0x14002ce90`
- `0x14002e43c`
- `0x14002f060`
- `0x140061f50`
- `0x140067fc0`
- `0x140068000`
- `0x1400681c0`
- `0x1400684c0`
- `0x14008c2f0`
- `0x1400b46f0`
- `0x1400b55b0`
- `0x1400b5610`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400b519b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b519b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b4b66`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b4b66`

## pseudocode

```c
__int64 __fastcall SpIoctlGetSpaceInfo(struct _IRP *a1)
{
  SP_SPACE *Child; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IRP *MasterIrp; // rbx
  int Flink_high; // ecx
  struct _GUID v6; // xmm6
  struct _GUID v7; // xmm7
  unsigned int Length; // r14d
  struct SP_POOL *PoolById; // rax
  struct SP_POOL *v10; // r13
  SDB_RECORD **v11; // rdi
  SDB_RECORD *SpaceById; // rcx
  struct SDB_OBJECT *v13; // rax
  struct SDB_RECORD *v14; // rcx
  SDB_SPACE *v15; // r15
  SDB_RECORD *TopLevelSpace; // rax
  struct SP_DEVICE *v17; // rax
  struct SP_DEVICE *v18; // r12
  const wchar_t *v19; // r8
  const wchar_t *v20; // r8
  int v21; // esi
  int v22; // ecx
  __int64 v23; // rdx
  unsigned __int64 MaximumByteRate; // rax
  SDB_RECORD *RecordByRecordId; // rax
  GUID v26; // xmm0
  SDB_RECORD *v27; // rax
  GUID v28; // xmm0
  SDB_RECORD *v29; // rax
  GUID v30; // xmm0
  wchar_t *v31; // r13
  int v32; // esi
  unsigned int v33; // r14d
  bool v34; // zf
  const wchar_t *v35; // r8
  __int64 v36; // r10
  int v37; // eax
  void *v38; // r12
  unsigned int v39; // ecx
  ULONG v40; // r14d
  ULONG v41; // eax
  __int64 v42; // rsi
  char v43; // di
  int v44; // ecx
  unsigned int v45; // r14d
  int v46; // r8d
  SP_SPACE *v47; // r10
  _OWORD *p_Data1; // r9
  unsigned int v49; // r8d
  SDB_RECORD *i; // rcx
  struct SDB_OBJECT *v51; // rax
  unsigned int v52; // edx
  unsigned int v53; // r13d
  ULONG DeviceType; // ecx
  const char *v55; // r9
  __int64 v57; // r13
  SDB_RECORD *Extent; // rdi
  struct SDB_OBJECT *v59; // rsi
  SDB_RECORD *Drive; // rax
  struct SDB_OBJECT *v61; // rax
  struct SDB_OBJECT *v62; // r12
  SDB_RECORD *Tier; // rax
  struct SDB_OBJECT *v64; // rax
  SP_SPACE *v65; // rcx
  struct SP_DEVICE *v66; // rax
  SP_SPACE *v67; // rcx
  unsigned int v68; // edx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // edx
  int v72; // r8d
  struct SP_POOL *v73; // rdx
  int MetadataDrives; // eax
  unsigned int v75; // edx
  unsigned int j; // ecx
  char v77; // [rsp+38h] [rbp-D0h]
  NTSTATUS Health; // [rsp+3Ch] [rbp-CCh]
  unsigned int v79; // [rsp+40h] [rbp-C8h] BYREF
  int v80; // [rsp+44h] [rbp-C4h]
  unsigned int v81[2]; // [rsp+48h] [rbp-C0h] BYREF
  SP_SPACE *v82; // [rsp+50h] [rbp-B8h]
  struct _GUID *v83; // [rsp+58h] [rbp-B0h] BYREF
  struct SP_DEVICE *v84; // [rsp+60h] [rbp-A8h]
  struct _GUID v85; // [rsp+68h] [rbp-A0h] BYREF
  void *v86; // [rsp+78h] [rbp-90h]
  unsigned __int64 v87; // [rsp+80h] [rbp-88h] BYREF
  SDB_SPACE *v88; // [rsp+88h] [rbp-80h]
  struct SDB_OBJECT *Object; // [rsp+90h] [rbp-78h]
  struct SP_POOL *v90; // [rsp+98h] [rbp-70h]
  struct _IRP *v91; // [rsp+A0h] [rbp-68h]
  int v92; // [rsp+A8h] [rbp-60h]
  struct _GUID v93; // [rsp+ACh] [rbp-5Ch] BYREF
  struct _GUID v94; // [rsp+BCh] [rbp-4Ch] BYREF
  int v95; // [rsp+CCh] [rbp-3Ch]
  __int128 v96; // [rsp+D8h] [rbp-30h] BYREF
  _DWORD v97[32]; // [rsp+E8h] [rbp-20h] BYREF

  Child = 0;
  v91 = a1;
  v87 = 0;
  v81[0] = 0;
  v96 = 0;
  memset(v97, 0, 0x74u);
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v86 = 0;
  v83 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids);
  }
  SpAcquireResourceShared((PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96), 0);
  if ( CurrentStackLocation->Parameters.Create.Options < 0x28 )
  {
    v21 = -1073741820;
LABEL_86:
    SpReleaseResourceShared((struct _ERESOURCE *)((char *)WPP_MAIN_CB.DeviceExtension + 96));
LABEL_131:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v55 = "Error";
    goto LABEL_58;
  }
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  Flink_high = HIDWORD(MasterIrp->ThreadListEntry.Flink);
  v92 = *(_DWORD *)&MasterIrp->Type;
  v80 = Flink_high;
  v95 = Flink_high;
  v6 = *(struct _GUID *)(&MasterIrp->Size + 1);
  v7 = *(struct _GUID *)(&MasterIrp->Flags + 1);
  v93 = v6;
  v94 = v7;
  if ( v92 != 40 )
  {
    v21 = -1073741811;
    goto LABEL_86;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 0xB48 )
  {
    v21 = -1073741789;
    SpReleaseResourceShared((struct _ERESOURCE *)((char *)WPP_MAIN_CB.DeviceExtension + 96));
    goto LABEL_55;
  }
  memset(MasterIrp, 0, Length);
  *(_DWORD *)&MasterIrp->Type = 3032;
  PoolById = SpFindPoolById(&v93);
  v90 = PoolById;
  v10 = PoolById;
  if ( !PoolById )
  {
    v21 = -1070071760;
    goto LABEL_86;
  }
  v11 = (SDB_RECORD **)*((_QWORD *)PoolById + 6);
  Object = SDB_RECORD::GetObject(v11[34]);
  SpaceById = SDB_POOL_CONFIG::FindSpaceById((SDB_POOL_CONFIG *)v11, &v94);
  if ( !SpaceById )
  {
    v21 = -1073741275;
    goto LABEL_86;
  }
  v82 = 0;
  v13 = SDB_RECORD::GetObject(SpaceById);
  v15 = v13;
  v88 = v13;
  if ( *((_DWORD *)v13 + 47) )
  {
    TopLevelSpace = SDB_POOL_CONFIG::FindTopLevelSpace((SDB_POOL_CONFIG *)v11, v14);
    v85 = (struct _GUID)*((_OWORD *)SDB_RECORD::GetObject(TopLevelSpace) + 2);
    v17 = SpAcquireReferenceExclusive(&v85);
    v84 = v17;
    v18 = v17;
    if ( v17 )
    {
      v67 = (SP_SPACE *)*((_QWORD *)v17 + 403);
      v85 = (struct _GUID)*((_OWORD *)v15 + 2);
      Child = SP_SPACE::GetChild(v67, &v85);
      v82 = Child;
    }
  }
  else
  {
    v85 = (struct _GUID)*((_OWORD *)v13 + 2);
    v66 = SpAcquireReferenceExclusive(&v85);
    v84 = v66;
    v18 = v66;
    if ( v66 )
    {
      Child = (SP_SPACE *)*((_QWORD *)v66 + 403);
      v82 = Child;
    }
  }
  *(struct _GUID *)&MasterIrp->MdlAddress = v6;
  *(struct _GUID *)&MasterIrp->AssociatedIrp.MasterIrp = v7;
  v19 = (const wchar_t *)*((_QWORD *)v15 + 6);
  if ( v19 )
    RtlStringCbCopyW((NTSTRSAFE_PWSTR)&MasterIrp->ThreadListEntry.Blink, 0x200u, v19);
  v20 = (const wchar_t *)*((_QWORD *)v15 + 7);
  if ( v20 )
    RtlStringCbCopyW((NTSTRSAFE_PWSTR)&MasterIrp[2].Tail.CompletionKey + 8, 0x800u, v20);
  LOBYTE(MasterIrp[12].CancelRoutine) = *((_BYTE *)v15 + 66);
  MasterIrp[12].Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)*((_QWORD *)v15 + 9);
  MasterIrp[12].Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)SDB_SPACE::GetAllocatedCapacity(v15);
  MasterIrp[12].Tail.Overlay.CurrentStackLocation = (struct _IO_STACK_LOCATION *)*((_QWORD *)v15 + 35);
  if ( Child )
  {
    v79 = 8;
    Health = SP_SPACE::GetHealth(
               Child,
               (struct _SIO_HEALTH_CONTEXT *)v97,
               (enum _SP_SPACE_STATE *)&MasterIrp[12].Tail,
               &v79);
    v21 = Health;
    if ( Health < 0 )
      goto LABEL_52;
    HIDWORD(MasterIrp[12].UserBuffer) = v97[0];
    HIDWORD(MasterIrp[12].CancelRoutine) = *((_DWORD *)v18 + 784);
    v22 = 1;
  }
  else
  {
    Health = 0;
    v34 = *((_DWORD *)v15 + 66) == 2;
    LODWORD(MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 1;
    HIDWORD(MasterIrp[12].CancelRoutine) = -1;
    HIDWORD(MasterIrp[12].UserBuffer) = !v34;
    v22 = *((_DWORD *)v15 + 66);
  }
  *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 11) = v22;
  v77 = 0;
  *((_OWORD *)&MasterIrp[12].Tail.CompletionKey + 5) = *((_OWORD *)v15 + 6);
  *(_OWORD *)&MasterIrp[13].MdlAddress = *((_OWORD *)v15 + 7);
  *(_OWORD *)((char *)&MasterIrp[13].ThreadListEntry.Blink + 4) = *((_OWORD *)v15 + 8);
  *(ULONG_PTR *)((char *)&MasterIrp[13].IoStatus.Information + 4) = *((_QWORD *)v15 + 18);
  *(_OWORD *)&MasterIrp[13].UserIosb = *(_OWORD *)((char *)v15 + 152);
  MasterIrp[13].Overlay.AllocationSize.QuadPart = *((_QWORD *)v15 + 21);
  *((_DWORD *)&MasterIrp[13].Overlay.AllocationSize + 2) = *((_DWORD *)v15 + 46);
  MasterIrp[12].Tail.Overlay.Thread = (PETHREAD)*((_QWORD *)v15 + 39);
  *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 10) = *((_DWORD *)v15 + 80);
  *((_BYTE *)&MasterIrp[13].Overlay.AllocationSize + 12) = SDB_SPACE::NumberOfTiers(v15) != 0;
  *((_WORD *)&MasterIrp[13].Tail.CompletionKey + 22) = *((_WORD *)v15 + 32) & 0x3E;
  if ( v18 )
  {
    MasterIrp[13].Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)SpLimiterGetMaximumIoRate(*((void **)v18 + 411));
    MaximumByteRate = SpLimiterGetMaximumByteRate(*((void **)v18 + 411));
  }
  else
  {
    MasterIrp[13].Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)*((_QWORD *)v15 + 27);
    MaximumByteRate = *((_QWORD *)v15 + 28);
  }
  MasterIrp[13].Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)MaximumByteRate;
  if ( *((_DWORD *)v15 + 47) )
  {
    LOBYTE(v23) = 3;
    RecordByRecordId = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23);
    v26 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(RecordByRecordId) + 2);
  }
  else
  {
    v26 = GUID_NULL;
  }
  *(GUID *)&MasterIrp[13].CancelRoutine = v26;
  if ( *((_DWORD *)v15 + 48) )
  {
    LOBYTE(v23) = 3;
    v27 = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23);
    v28 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(v27) + 2);
  }
  else
  {
    v28 = GUID_NULL;
  }
  MasterIrp[13].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = (LIST_ENTRY)v28;
  if ( *((_DWORD *)v15 + 49) )
  {
    LOBYTE(v23) = 3;
    v29 = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23);
    v30 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(v29) + 2);
  }
  else
  {
    v30 = GUID_NULL;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) += 2888;
  v31 = (wchar_t *)(&MasterIrp[13].Tail.CompletionKey + 8);
  v32 = *(_DWORD *)(&MasterIrp->Size + 1);
  v33 = Length - 2888;
  v34 = (v80 & 1) == 0;
  *((GUID *)&MasterIrp[13].Tail.CompletionKey + 1) = v30;
  *(_QWORD *)&v85.Data1 = (char *)MasterIrp + 2888;
  if ( v34 )
  {
    v57 = 0;
    v79 = 0;
    Extent = SDB_SPACE::GetExtent(v15, 0, &v87);
    if ( Extent )
    {
      do
      {
        v59 = SDB_RECORD::GetObject(Extent);
        Drive = SDB_EXTENT::GetDrive(v59);
        v61 = SDB_RECORD::GetObject(Drive);
        ++*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 10);
        v62 = v61;
        if ( v33 < 0x90 )
        {
          v33 = 0;
          v77 = 1;
        }
        else
        {
          if ( SDB_EXTENT::GetTier(v59) )
          {
            Tier = SDB_EXTENT::GetTier(v59);
            v64 = SDB_RECORD::GetObject(Tier);
            *(struct _GUID *)&(&MasterIrp[14].MdlAddress)[18 * v57] = v6;
            *((_OWORD *)&MasterIrp[14].AssociatedIrp.MasterIrp + 9 * v57) = *((_OWORD *)v64 + 2);
          }
          v65 = v82;
          *((struct _GUID *)&MasterIrp[13].Tail.CompletionKey + 9 * v57 + 4) = v6;
          *((struct _GUID *)&MasterIrp[13].Tail.CompletionKey + 9 * v57 + 5) = v7;
          (&MasterIrp[14].ThreadListEntry.Blink)[18 * v57] = (struct _LIST_ENTRY *)*((_QWORD *)v59 + 5);
          *(&MasterIrp[14].IoStatus.Status + 36 * v57) = *((_DWORD *)v59 + 16);
          *((_DWORD *)&MasterIrp[14].IoStatus.Pointer + 36 * v57 + 1) = *((_DWORD *)v59 + 17);
          *((_DWORD *)&MasterIrp[14].IoStatus.Information + 36 * v57) = *((_DWORD *)v59 + 18);
          *(struct _GUID *)((char *)&MasterIrp[14].IoStatus.Information + 144 * v57 + 4) = v6;
          *(_OWORD *)((char *)&(&MasterIrp[14].UserIosb)[18 * v57] + 4) = *((_OWORD *)v62 + 2);
          *((_QWORD *)&MasterIrp[14].Overlay.AsynchronousParameters.UserApcContext + 18 * v57) = *((_QWORD *)v59 + 6);
          *((_QWORD *)&MasterIrp[14].CancelRoutine + 18 * v57) = *((_QWORD *)v59 + 4);
          if ( v65 )
          {
            v96 = 0;
            *((_QWORD *)&v96 + 1) = *((_QWORD *)&MasterIrp[14].IoStatus.Pointer + 18 * v57);
            (*(void (__fastcall **)(_QWORD, __int64, struct _LIST_ENTRY *, _QWORD, __int128 *))(**((_QWORD **)v65 + 49)
                                                                                              + 96LL))(
              *((_QWORD *)v65 + 49),
              3,
              (&MasterIrp[14].ThreadListEntry.Blink)[18 * v57],
              0,
              &v96);
            *((_DWORD *)&MasterIrp[14].UserBuffer + 36 * v57) = v96;
            *((_WORD *)&MasterIrp[14].UserBuffer + 72 * v57 + 2) = WORD2(v96);
          }
          *(_QWORD *)&v85.Data1 += 144LL;
          v57 = v79 + 1;
          v15 = v88;
          v33 -= 144;
          ++v79;
        }
        v32 = *(_DWORD *)(&MasterIrp->Size + 1) + 144;
        *(_DWORD *)(&MasterIrp->Size + 1) = v32;
        Extent = SDB_SPACE::GetExtent(v15, Extent, &v87);
      }
      while ( Extent );
      v31 = *(wchar_t **)&v85.Data1;
      v18 = v84;
    }
    else
    {
      v31 = (wchar_t *)(&MasterIrp[13].Tail.CompletionKey + 8);
    }
  }
  if ( v18 )
  {
    v35 = (const wchar_t *)*((_QWORD *)v18 + 394);
    if ( v35 )
    {
      LODWORD(v36) = *((unsigned __int16 *)v18 + 1573);
      if ( v33 < (unsigned int)v36 )
      {
        v33 = 0;
        v77 = 1;
      }
      else
      {
        Health = RtlStringCbCopyW(v31, v33, v35);
        v21 = Health;
        if ( Health < 0 )
        {
          p_Data1 = v86;
          goto LABEL_50;
        }
        v37 = (int)v31;
        v31 = (wchar_t *)((char *)v31 + v36);
        LODWORD(MasterIrp[12].UserBuffer) = v37 - (_DWORD)MasterIrp;
        v33 -= v36;
      }
      *(_DWORD *)(&MasterIrp->Size + 1) += v36;
      v32 = *(_DWORD *)(&MasterIrp->Size + 1);
    }
  }
  v38 = (void *)*((_QWORD *)v15 + 22);
  if ( !v38 )
  {
    v38 = (void *)*((_QWORD *)Object + 29);
    if ( !v38 )
      v38 = (void *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 48);
  }
  v39 = (((_DWORD)v31 + 3) & 0xFFFFFFFC) - (_DWORD)v31;
  if ( v33 < v39 )
  {
    v40 = 0;
    v77 = 1;
  }
  else
  {
    v31 = (wchar_t *)((char *)v31 + v39);
    v40 = v33 - v39;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) = v39 + v32;
  v41 = RtlLengthSecurityDescriptor(v38);
  v42 = v41;
  if ( v40 < v41 )
  {
    v43 = 1;
    v45 = 0;
  }
  else
  {
    memmove(v31, v38, v41);
    v43 = v77;
    v44 = (_DWORD)v31 - (_DWORD)MasterIrp;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 18) = v42;
    v31 = (wchar_t *)((char *)v31 + v42);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 19) = v44;
    v45 = v40 - v42;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) += v42;
  v46 = *(_DWORD *)(&MasterIrp->Size + 1);
  MasterIrp[13].AssociatedIrp.IrpCount = *((_DWORD *)v15 + 50);
  *(PVOID *)((char *)&MasterIrp[13].AssociatedIrp.SystemBuffer + 4) = 0;
  if ( *((_DWORD *)v15 + 51) )
  {
    v68 = (((_DWORD)v31 + 3) & 0xFFFFFFFC) - (_DWORD)v31;
    if ( v45 < v68 )
      v43 = 1;
    else
      v31 = (wchar_t *)((char *)v31 + v68);
    v70 = v45;
    v45 -= v68;
    if ( v70 < v68 )
      v45 = 0;
    v46 += v68;
    *(_DWORD *)(&MasterIrp->Size + 1) = v46;
    if ( *((_DWORD *)v15 + 51) )
    {
      v71 = 0;
      do
      {
        if ( v45 < 0x10 )
        {
          v45 = 0;
          v43 = 1;
        }
        else
        {
          *(_OWORD *)v31 = *(_OWORD *)(*((_QWORD *)v15 + 26) + 16LL * v71);
          if ( !LODWORD(MasterIrp[13].ThreadListEntry.Flink) )
            LODWORD(MasterIrp[13].ThreadListEntry.Flink) = (_DWORD)v31 - (_DWORD)MasterIrp;
          v31 += 8;
          v45 -= 16;
        }
        v72 = *(_DWORD *)(&MasterIrp->Size + 1);
        ++v71;
        ++HIDWORD(MasterIrp[13].AssociatedIrp.SystemBuffer);
        v46 = v72 + 16;
        *(_DWORD *)(&MasterIrp->Size + 1) = v46;
      }
      while ( v71 < *((_DWORD *)v15 + 51) );
    }
  }
  v47 = v82;
  *(struct _LIST_ENTRY **)((char *)&MasterIrp[13].ThreadListEntry.Flink + 4) = 0;
  if ( !v47 || (v80 & 2) != 0 )
  {
    p_Data1 = v86;
    v21 = Health;
LABEL_40:
    MasterIrp[13].Tail.Overlay.Thread = 0;
    if ( *((_QWORD *)v15 + 30) )
    {
      v49 = (((_DWORD)v31 + 3) & 0xFFFFFFFC) - (_DWORD)v31;
      if ( v45 < v49 )
        v43 = 1;
      else
        v31 = (wchar_t *)((char *)v31 + v49);
      *(_DWORD *)(&MasterIrp->Size + 1) += v49;
      for ( i = (SDB_RECORD *)*((_QWORD *)v15 + 30); i; i = (SDB_RECORD *)*((_QWORD *)v51 + 31) )
      {
        v51 = SDB_RECORD::GetObject(i);
        if ( v52 >= 0x10 )
        {
          *(_OWORD *)v31 = *((_OWORD *)v51 + 2);
          if ( !*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 9) )
            *((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 9) = (_DWORD)v31 - (_DWORD)MasterIrp;
          v31 += 8;
        }
        else
        {
          v43 = 1;
        }
        ++*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 8);
        *(_DWORD *)(&MasterIrp->Size + 1) += 16;
      }
    }
    v53 = (_DWORD)v31 - (_DWORD)MasterIrp;
    v18 = v84;
    if ( v43 )
      v21 = -2147483643;
    v91->IoStatus.Information = v53;
    goto LABEL_50;
  }
  v69 = (((_DWORD)v31 + 3) & 0xFFFFFFFC) - (_DWORD)v31;
  if ( v45 < v69 )
  {
    v45 = 0;
    v43 = 1;
  }
  else
  {
    v31 = (wchar_t *)((char *)v31 + v69);
    v45 -= v69;
  }
  v73 = v90;
  *(_DWORD *)(&MasterIrp->Size + 1) = v46 + v69;
  MetadataDrives = SDB_SPACE_CONFIG::GetMetadataDrives(
                     *((SDB_SPACE_CONFIG **)v47 + 41),
                     *((struct SDB_POOL_CONFIG **)v73 + 6),
                     v81,
                     &v83);
  p_Data1 = &v83->Data1;
  v21 = MetadataDrives;
  if ( MetadataDrives >= 0 )
  {
    v75 = v81[0];
    for ( j = 0; j < v75; *(_DWORD *)(&MasterIrp->Size + 1) += 16 )
    {
      if ( v45 < 0x10 )
      {
        v45 = 0;
        v43 = 1;
      }
      else
      {
        *(_OWORD *)v31 = p_Data1[j];
        if ( !LODWORD(MasterIrp[13].ThreadListEntry.Blink) )
          LODWORD(MasterIrp[13].ThreadListEntry.Blink) = (_DWORD)v31 - (_DWORD)MasterIrp;
        v31 += 8;
        v45 -= 16;
      }
      ++HIDWORD(MasterIrp[13].ThreadListEntry.Flink);
      ++j;
    }
    goto LABEL_40;
  }
  v18 = v84;
LABEL_50:
  if ( p_Data1 )
    SC_ENV_ALLOCATOR::operator delete[](p_Data1);
LABEL_52:
  if ( v18 )
  {
    SP_DEVICE::ReleaseMutex(v18);
    ObfDereferenceObject(*((PVOID *)v18 + 20));
  }
  SpReleaseResourceShared((struct _ERESOURCE *)((char *)WPP_MAIN_CB.DeviceExtension + 96));
  if ( v21 < 0 && v21 != -2147483643 && v21 != -1073741789 )
    goto LABEL_131;
LABEL_55:
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v55 = "Exit ";
LABEL_58:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      85,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v55,
      v21);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1400b46f0  mov     r11, rsp
0x1400b46f3  push    rbp
0x1400b46f4  push    rsi
0x1400b46f5  lea     rbp, [r11-0B8h]
0x1400b46fc  sub     rsp, 1A8h
0x1400b4703  mov     rax, cs:__security_cookie
0x1400b470a  xor     rax, rsp
0x1400b470d  mov     [rbp+0B0h+var_50], rax
0x1400b4711  mov     [r11+10h], rbx
0x1400b4715  xor     esi, esi
0x1400b4717  mov     rbx, rcx
0x1400b471a  mov     [rbp+0B0h+var_118], rcx
0x1400b471e  xorps   xmm0, xmm0
0x1400b4721  mov     [r11+18h], rdi
0x1400b4725  lea     rcx, [rbp+0B0h+var_D0]; void *
0x1400b4729  mov     [r11-28h], r15
0x1400b472d  xor     edx, edx; Val
0x1400b472f  mov     [rsp+1B0h+var_138], rsi
0x1400b4734  mov     r8d, 74h ; 't'; Size
0x1400b473a  mov     [rsp+1B0h+var_170], esi
0x1400b473e  movups  [rbp+0B0h+var_E0], xmm0
0x1400b4742  call    memset
0x1400b4747  mov     rdi, [rbx+0B8h]
0x1400b474e  mov     eax, esi
0x1400b4750  mov     [rsp+1B0h+var_140], rax
0x1400b4755  mov     [rsp+1B0h+var_160], rax
0x1400b475a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4761  lea     r15, WPP_GLOBAL_Control
0x1400b4768  cmp     rcx, r15
0x1400b476b  jnz     loc_1400B5005
0x1400b4771  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400b4778  xor     edx, edx; unsigned __int8
0x1400b477a  mov     [rsp+1A0h], r13
0x1400b4782  add     rcx, 60h ; '`'; Resource
0x1400b4786  mov     [rsp+1B0h+var_18], r14
0x1400b478e  movaps  [rsp+1B0h+var_38+8], xmm6
0x1400b4796  movaps  [rsp+1B0h+var_48+8], xmm7
0x1400b479e  call    ?SpAcquireResourceShared@@YAXPEAU_ERESOURCE@@E@Z; SpAcquireResourceShared(_ERESOURCE *,uchar)
0x1400b47a3  cmp     dword ptr [rdi+10h], 28h ; '('
0x1400b47a7  jb      loc_1400B5034
0x1400b47ad  mov     rbx, [rbx+18h]
0x1400b47b1  mov     eax, [rbx]
0x1400b47b3  mov     ecx, [rbx+24h]
0x1400b47b6  mov     [rbp+0B0h+var_110], eax
0x1400b47b9  mov     [rsp+1B0h+var_174], ecx
0x1400b47bd  mov     [rbp+0B0h+var_EC], ecx
0x1400b47c0  movups  xmm6, xmmword ptr [rbx+4]
0x1400b47c4  movups  xmm7, xmmword ptr [rbx+14h]
0x1400b47c8  movups  xmmword ptr [rbp+0B0h+var_10C.Data1], xmm6
0x1400b47cc  movups  xmmword ptr [rbp+0B0h+var_FC.Data1], xmm7
0x1400b47d0  cmp     eax, 28h ; '('
0x1400b47d3  jnz     loc_1400B5056
0x1400b47d9  mov     r14d, [rdi+8]
0x1400b47dd  cmp     r14d, 0B48h
0x1400b47e4  jb      loc_1400B505D
0x1400b47ea  mov     r8d, r14d; Size
0x1400b47ed  xor     edx, edx; Val
0x1400b47ef  mov     rcx, rbx; void *
0x1400b47f2  call    memset
0x1400b47f7  lea     rcx, [rbp+0B0h+var_10C]; struct _GUID *
0x1400b47fb  mov     dword ptr [rbx], 0BD8h
0x1400b4801  call    ?SpFindPoolById@@YAPEAVSP_POOL@@PEAU_GUID@@@Z; SpFindPoolById(_GUID *)
0x1400b4806  mov     [rbp+0B0h+var_120], rax
0x1400b480a  mov     r13, rax
0x1400b480d  test    rax, rax
0x1400b4810  jz      loc_1400B5077
0x1400b4816  mov     rdi, [rax+30h]
0x1400b481a  mov     rcx, [rdi+110h]; this
0x1400b4821  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4826  lea     rdx, [rbp+0B0h+var_FC]; struct _GUID *
0x1400b482a  mov     [rbp+0B0h+var_128], rax
0x1400b482e  mov     rcx, rdi; this
0x1400b4831  call    ?FindSpaceById@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAU_GUID@@@Z; SDB_POOL_CONFIG::FindSpaceById(_GUID *)
0x1400b4836  mov     rcx, rax; this
0x1400b4839  test    rax, rax
0x1400b483c  jz      loc_1400B503B
0x1400b4842  mov     [rsp+1B0h+arg_18], r12
0x1400b484a  mov     [rsp+1B0h+var_168], rsi
0x1400b484f  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4854  mov     r15, rax
0x1400b4857  mov     [rbp+0B0h+var_130], rax
0x1400b485b  cmp     [rax+0BCh], esi
0x1400b4861  jz      loc_1400B4F25
0x1400b4867  mov     rdx, rcx; struct SDB_RECORD *
0x1400b486a  mov     rcx, rdi; this
0x1400b486d  call    ?FindTopLevelSpace@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::FindTopLevelSpace(SDB_RECORD *)
0x1400b4872  mov     rcx, rax; this
0x1400b4875  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b487a  lea     rcx, [rsp+1B0h+var_158.Data4]; struct _GUID
0x1400b487f  movups  xmm0, xmmword ptr [rax+20h]
0x1400b4883  movaps  xmmword ptr [rsp+1B0h+var_158.Data4], xmm0
0x1400b4888  call    ?SpAcquireReferenceExclusive@@YAPEAVSP_DEVICE@@U_GUID@@@Z; SpAcquireReferenceExclusive(_GUID)
0x1400b488d  mov     qword ptr [rsp+1B0h+var_158.Data1], rax
0x1400b4892  mov     r12, rax
0x1400b4895  test    rax, rax
0x1400b4898  jnz     loc_1400B507E
0x1400b489e  movups  xmmword ptr [rbx+8], xmm6
0x1400b48a2  movups  xmmword ptr [rbx+18h], xmm7
0x1400b48a6  mov     r8, [r15+30h]; pszSrc
0x1400b48aa  test    r8, r8
0x1400b48ad  jnz     loc_1400B50A6
0x1400b48b3  mov     r8, [r15+38h]; pszSrc
0x1400b48b7  test    r8, r8
0x1400b48ba  jnz     loc_1400B50B9
0x1400b48c0  movzx   eax, byte ptr [r15+42h]
0x1400b48c5  mov     rcx, r15; this
0x1400b48c8  mov     [rbx+0A28h], al
0x1400b48ce  mov     rax, [r15+48h]
0x1400b48d2  mov     [rbx+0A68h], rax
0x1400b48d9  call    ?GetAllocatedCapacity@SDB_SPACE@@QEAA_KXZ; SDB_SPACE::GetAllocatedCapacity(void)
0x1400b48de  mov     [rbx+0A70h], rax
0x1400b48e5  mov     edi, 80000005h
0x1400b48ea  mov     rax, [r15+118h]
0x1400b48f1  mov     [rbx+0A78h], rax
0x1400b48f8  test    rsi, rsi
0x1400b48fb  jz      loc_1400B4F5A
0x1400b4901  lea     r8, [rbx+0A38h]; enum _SP_SPACE_STATE *
0x1400b4908  mov     [rsp+1B0h+var_178], 8
0x1400b4910  lea     r9, [rsp+1B0h+var_178]; unsigned int *
0x1400b4915  mov     rcx, rsi; this
0x1400b4918  lea     rdx, [rbp+0B0h+var_D0]; struct _SIO_HEALTH_CONTEXT *
0x1400b491c  call    ?GetHealth@SP_SPACE@@QEAAJPEAU_SIO_HEALTH_CONTEXT@@PEAW4_SP_SPACE_STATE@@PEAK@Z; SP_SPACE::GetHealth(_SIO_HEALTH_CONTEXT *,_SP_SPACE_STATE *,ulong *)
0x1400b4921  mov     [rsp+1B0h+var_17C], eax
0x1400b4925  mov     esi, eax
0x1400b4927  test    eax, eax
0x1400b4929  js      loc_1400B4C96
0x1400b492f  mov     ecx, [rbp+0B0h+var_D0]
0x1400b4932  mov     [rbx+0A34h], ecx
0x1400b4938  mov     ecx, [r12+0C40h]
0x1400b4940  mov     [rbx+0A2Ch], ecx
0x1400b4946  mov     ecx, 1
0x1400b494b  mov     [rbx+0A64h], ecx
0x1400b4951  xor     al, al
0x1400b4953  movups  xmm0, xmmword ptr [r15+60h]
0x1400b4958  mov     byte ptr [rsp+1B0h+var_180], al
0x1400b495c  mov     rcx, r15; this
0x1400b495f  movups  xmmword ptr [rbx+0A88h], xmm0
0x1400b4966  movups  xmm1, xmmword ptr [r15+70h]
0x1400b496b  movups  xmmword ptr [rbx+0A98h], xmm1
0x1400b4972  movups  xmm0, xmmword ptr [r15+80h]
0x1400b497a  movups  xmmword ptr [rbx+0ABCh], xmm0
0x1400b4981  movsd   xmm1, qword ptr [r15+90h]
0x1400b498a  movsd   qword ptr [rbx+0ACCh], xmm1
0x1400b4992  movups  xmm0, xmmword ptr [r15+98h]
0x1400b499a  movups  xmmword ptr [rbx+0AD8h], xmm0
0x1400b49a1  movsd   xmm1, qword ptr [r15+0A8h]
0x1400b49aa  movsd   qword ptr [rbx+0AE8h], xmm1
0x1400b49b2  mov     eax, [r15+0B8h]
0x1400b49b9  mov     [rbx+0AF0h], eax
0x1400b49bf  mov     rax, [r15+138h]
0x1400b49c6  mov     [rbx+0A58h], rax
0x1400b49cd  mov     eax, [r15+140h]
0x1400b49d4  mov     [rbx+0A60h], eax
0x1400b49da  call    ?NumberOfTiers@SDB_SPACE@@QEAAKXZ; SDB_SPACE::NumberOfTiers(void)
0x1400b49df  test    eax, eax
0x1400b49e1  setnz   al
0x1400b49e4  mov     [rbx+0AF4h], al
0x1400b49ea  movzx   eax, word ptr [r15+40h]
0x1400b49ef  and     ax, 3Eh
0x1400b49f3  mov     [rbx+0B34h], ax
0x1400b49fa  test    r12, r12
0x1400b49fd  jz      loc_1400B4F9A
0x1400b4a03  mov     rcx, [r12+0CD8h]; void *
0x1400b4a0b  call    ?SpLimiterGetMaximumIoRate@@YA_KPEAX@Z; SpLimiterGetMaximumIoRate(void *)
0x1400b4a10  mov     [rbx+0B38h], rax
0x1400b4a17  mov     rcx, [r12+0CD8h]; void *
0x1400b4a1f  call    ?SpLimiterGetMaximumByteRate@@YA_KPEAX@Z; SpLimiterGetMaximumByteRate(void *)
0x1400b4a24  mov     [rbx+0B40h], rax
0x1400b4a2b  mov     r8d, [r15+0BCh]
0x1400b4a32  test    r8d, r8d
0x1400b4a35  jz      loc_1400B4FB4
0x1400b4a3b  mov     rcx, [r13+30h]
0x1400b4a3f  mov     dl, 3
0x1400b4a41  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x1400b4a46  mov     rcx, rax; this
0x1400b4a49  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4a4e  movups  xmm0, xmmword ptr [rax+20h]
0x1400b4a52  movups  xmmword ptr [rbx+0AF8h], xmm0
0x1400b4a59  mov     r8d, [r15+0C0h]
0x1400b4a60  test    r8d, r8d
0x1400b4a63  jz      loc_1400B4FC0
0x1400b4a69  mov     rcx, [r13+30h]
0x1400b4a6d  mov     dl, 3
0x1400b4a6f  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x1400b4a74  mov     rcx, rax; this
0x1400b4a77  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4a7c  movups  xmm0, xmmword ptr [rax+20h]
0x1400b4a80  movups  xmmword ptr [rbx+0B08h], xmm0
0x1400b4a87  mov     r8d, [r15+0C4h]
0x1400b4a8e  test    r8d, r8d
0x1400b4a91  jz      loc_1400B4FCC
0x1400b4a97  mov     rcx, [r13+30h]
0x1400b4a9b  mov     dl, 3
0x1400b4a9d  call    ?FindRecordByRecordId@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@K@Z; SDB_POOL_CONFIG::FindRecordByRecordId(_SDB_RECORD_TYPE,ulong)
0x1400b4aa2  mov     rcx, rax; this
0x1400b4aa5  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4aaa  movups  xmm0, xmmword ptr [rax+20h]
0x1400b4aae  add     dword ptr [rbx+4], 0B48h
0x1400b4ab5  lea     r13, [rbx+0B48h]
0x1400b4abc  mov     esi, [rbx+4]
0x1400b4abf  add     r14d, 0FFFFF4B8h
0x1400b4ac6  test    byte ptr [rsp+1B0h+var_174], 1
0x1400b4acb  movups  xmmword ptr [rbx+0B18h], xmm0
0x1400b4ad2  mov     qword ptr [rsp+1B0h+var_158.Data4], r13
0x1400b4ad7  jz      loc_1400B4D3D
0x1400b4add  test    r12, r12
0x1400b4ae0  jz      short loc_1400B4B32
0x1400b4ae2  mov     r8, [r12+0C50h]; pszSrc
0x1400b4aea  test    r8, r8
0x1400b4aed  jz      short loc_1400B4B32
0x1400b4aef  movzx   r10d, word ptr [r12+0C4Ah]
0x1400b4af8  cmp     r14d, r10d
0x1400b4afb  jb      loc_1400B50DB
0x1400b4b01  mov     edx, r14d; cbDest
0x1400b4b04  mov     rcx, r13; pszDest
0x1400b4b07  call    RtlStringCbCopyW
0x1400b4b0c  mov     [rsp+1B0h+var_17C], eax
0x1400b4b10  mov     esi, eax
0x1400b4b12  test    eax, eax
0x1400b4b14  js      loc_1400B4FFB
0x1400b4b1a  mov     eax, r13d
0x1400b4b1d  add     r13, r10
0x1400b4b20  sub     eax, ebx
0x1400b4b22  mov     [rbx+0A30h], eax
0x1400b4b28  sub     r14d, r10d
0x1400b4b2b  add     [rbx+4], r10d
0x1400b4b2f  mov     esi, [rbx+4]
0x1400b4b32  mov     r12, [r15+0B0h]
0x1400b4b39  test    r12, r12
0x1400b4b3c  jz      loc_1400B50E8
0x1400b4b42  lea     rcx, [r13+3]
0x1400b4b46  and     ecx, 0FFFFFFFCh
0x1400b4b49  sub     ecx, r13d
0x1400b4b4c  cmp     r14d, ecx
0x1400b4b4f  jb      loc_1400B4FD8
0x1400b4b55  mov     eax, ecx
0x1400b4b57  add     r13, rax
0x1400b4b5a  sub     r14d, ecx
0x1400b4b5d  lea     eax, [rcx+rsi]
0x1400b4b60  mov     rcx, r12; SecurityDescriptor
0x1400b4b63  mov     [rbx+4], eax
0x1400b4b66  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400b4b6d  nop     dword ptr [rax+rax+00h]
0x1400b4b72  mov     esi, eax
0x1400b4b74  cmp     r14d, eax
0x1400b4b77  jb      loc_1400B4FE5
0x1400b4b7d  mov     r8d, esi; Size
0x1400b4b80  mov     rdx, r12; Src
0x1400b4b83  mov     rcx, r13; void *
0x1400b4b86  call    memmove
0x1400b4b8b  movzx   edi, byte ptr [rsp+1B0h+var_180]
0x1400b4b90  mov     ecx, r13d
0x1400b4b93  sub     ecx, ebx
0x1400b4b95  mov     [rbx+0A80h], esi
0x1400b4b9b  add     r13, rsi
0x1400b4b9e  mov     [rbx+0A84h], ecx
0x1400b4ba4  sub     r14d, esi
0x1400b4ba7  xor     r12d, r12d
0x1400b4baa  add     [rbx+4], esi
0x1400b4bad  mov     eax, [r15+0C8h]
0x1400b4bb4  mov     r8d, [rbx+4]
0x1400b4bb8  mov     [rbx+0AA8h], eax
0x1400b4bbe  mov     qword ptr [rbx+0AACh], 0
0x1400b4bc9  cmp     dword ptr [r15+0CCh], 0
0x1400b4bd1  ja      loc_1400B5110
0x1400b4bd7  mov     r10, [rsp+1B0h+var_168]
0x1400b4bdc  mov     qword ptr [rbx+0AB4h], 0
0x1400b4be7  test    r10, r10
0x1400b4bea  jnz     loc_1400B512D
0x1400b4bf0  mov     r9, [rsp+1B0h+var_140]
0x1400b4bf5  mov     esi, [rsp+1B0h+var_17C]
0x1400b4bf9  mov     qword ptr [rbx+0B28h], 0
0x1400b4c04  cmp     qword ptr [r15+0F0h], 0
0x1400b4c0c  jz      short loc_1400B4C6F
0x1400b4c0e  lea     r8, [r13+3]
0x1400b4c12  and     r8d, 0FFFFFFFCh
0x1400b4c16  sub     r8d, r13d
0x1400b4c19  cmp     r14d, r8d
0x1400b4c1c  jb      loc_1400B4FF3
0x1400b4c22  mov     eax, r8d
0x1400b4c25  add     r13, rax
0x1400b4c28  add     [rbx+4], r8d
0x1400b4c2c  mov     rcx, [r15+0F0h]; this
0x1400b4c33  test    rcx, rcx
0x1400b4c36  jz      short loc_1400B4C6F
0x1400b4c38  mov     edx, r14d
0x1400b4c3b  sub     edx, r8d
0x1400b4c3e  cmp     r14d, r8d
0x1400b4c41  cmovb   edx, r12d
0x1400b4c45  call    ?GetObject@SDB_RECORD@@QEAAPEAVSDB_OBJECT@@XZ; SDB_RECORD::GetObject(void)
0x1400b4c4a  cmp     edx, 10h
0x1400b4c4d  jnb     loc_1400B5158
0x1400b4c53  mov     edx, r12d
0x1400b4c56  mov     dil, 1
0x1400b4c59  inc     dword ptr [rbx+0B28h]
0x1400b4c5f  add     dword ptr [rbx+4], 10h
0x1400b4c63  mov     rcx, [rax+0F8h]
0x1400b4c6a  test    rcx, rcx
0x1400b4c6d  jnz     short loc_1400B4C45
0x1400b4c6f  mov     rcx, [rbp+0B0h+var_118]
  ... truncated ...
```
