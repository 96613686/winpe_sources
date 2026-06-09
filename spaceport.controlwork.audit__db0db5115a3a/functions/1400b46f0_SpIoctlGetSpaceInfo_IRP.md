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
  __int64 v25; // r8
  SDB_RECORD *RecordByRecordId; // rax
  GUID v27; // xmm0
  __int64 v28; // r8
  SDB_RECORD *v29; // rax
  GUID v30; // xmm0
  __int64 v31; // r8
  SDB_RECORD *v32; // rax
  GUID v33; // xmm0
  wchar_t *v34; // r13
  int v35; // esi
  unsigned int v36; // r14d
  bool v37; // zf
  const wchar_t *v38; // r8
  __int64 v39; // r10
  int v40; // eax
  void *v41; // r12
  unsigned int v42; // ecx
  ULONG v43; // r14d
  ULONG v44; // eax
  __int64 v45; // rsi
  char v46; // di
  int v47; // ecx
  unsigned int v48; // r14d
  int v49; // r8d
  SP_SPACE *v50; // r10
  _OWORD *p_Data1; // r9
  unsigned int v52; // r8d
  SDB_RECORD *i; // rcx
  struct SDB_OBJECT *v54; // rax
  unsigned int v55; // edx
  unsigned int v56; // r13d
  ULONG DeviceType; // ecx
  const char *v58; // r9
  __int64 v60; // r13
  SDB_RECORD *Extent; // rdi
  struct SDB_OBJECT *v62; // rsi
  SDB_RECORD *Drive; // rax
  struct SDB_OBJECT *v64; // rax
  struct SDB_OBJECT *v65; // r12
  SDB_RECORD *Tier; // rax
  struct SDB_OBJECT *v67; // rax
  SP_SPACE *v68; // rcx
  struct SP_DEVICE *v69; // rax
  SP_SPACE *v70; // rcx
  unsigned int v71; // edx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // edx
  int v75; // r8d
  struct SP_POOL *v76; // rdx
  int MetadataDrives; // eax
  unsigned int v78; // edx
  unsigned int j; // ecx
  char v80; // [rsp+38h] [rbp-D0h]
  NTSTATUS Health; // [rsp+3Ch] [rbp-CCh]
  unsigned int v82; // [rsp+40h] [rbp-C8h] BYREF
  int v83; // [rsp+44h] [rbp-C4h]
  unsigned int v84[2]; // [rsp+48h] [rbp-C0h] BYREF
  SP_SPACE *v85; // [rsp+50h] [rbp-B8h]
  struct _GUID *v86; // [rsp+58h] [rbp-B0h] BYREF
  struct SP_DEVICE *v87; // [rsp+60h] [rbp-A8h]
  struct _GUID v88; // [rsp+68h] [rbp-A0h] BYREF
  void *v89; // [rsp+78h] [rbp-90h]
  unsigned __int64 v90; // [rsp+80h] [rbp-88h] BYREF
  SDB_SPACE *v91; // [rsp+88h] [rbp-80h]
  struct SDB_OBJECT *Object; // [rsp+90h] [rbp-78h]
  struct SP_POOL *v93; // [rsp+98h] [rbp-70h]
  struct _IRP *v94; // [rsp+A0h] [rbp-68h]
  int v95; // [rsp+A8h] [rbp-60h]
  struct _GUID v96; // [rsp+ACh] [rbp-5Ch] BYREF
  struct _GUID v97; // [rsp+BCh] [rbp-4Ch] BYREF
  int v98; // [rsp+CCh] [rbp-3Ch]
  __int128 v99; // [rsp+D8h] [rbp-30h] BYREF
  _DWORD v100[32]; // [rsp+E8h] [rbp-20h] BYREF

  Child = 0;
  v94 = a1;
  v90 = 0;
  v84[0] = 0;
  v99 = 0;
  memset(v100, 0, 0x74u);
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v89 = 0;
  v86 = 0;
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
    v58 = "Error";
    goto LABEL_58;
  }
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  Flink_high = HIDWORD(MasterIrp->ThreadListEntry.Flink);
  v95 = *(_DWORD *)&MasterIrp->Type;
  v83 = Flink_high;
  v98 = Flink_high;
  v6 = *(struct _GUID *)(&MasterIrp->Size + 1);
  v7 = *(struct _GUID *)(&MasterIrp->Flags + 1);
  v96 = v6;
  v97 = v7;
  if ( v95 != 40 )
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
  PoolById = SpFindPoolById(&v96);
  v93 = PoolById;
  v10 = PoolById;
  if ( !PoolById )
  {
    v21 = -1070071760;
    goto LABEL_86;
  }
  v11 = (SDB_RECORD **)*((_QWORD *)PoolById + 6);
  Object = SDB_RECORD::GetObject(v11[34]);
  SpaceById = SDB_POOL_CONFIG::FindSpaceById((SDB_POOL_CONFIG *)v11, &v97);
  if ( !SpaceById )
  {
    v21 = -1073741275;
    goto LABEL_86;
  }
  v85 = 0;
  v13 = SDB_RECORD::GetObject(SpaceById);
  v15 = v13;
  v91 = v13;
  if ( *((_DWORD *)v13 + 47) )
  {
    TopLevelSpace = SDB_POOL_CONFIG::FindTopLevelSpace((SDB_POOL_CONFIG *)v11, v14);
    v88 = (struct _GUID)*((_OWORD *)SDB_RECORD::GetObject(TopLevelSpace) + 2);
    v17 = SpAcquireReferenceExclusive(&v88);
    v87 = v17;
    v18 = v17;
    if ( v17 )
    {
      v70 = (SP_SPACE *)*((_QWORD *)v17 + 403);
      v88 = (struct _GUID)*((_OWORD *)v15 + 2);
      Child = SP_SPACE::GetChild(v70, &v88);
      v85 = Child;
    }
  }
  else
  {
    v88 = (struct _GUID)*((_OWORD *)v13 + 2);
    v69 = SpAcquireReferenceExclusive(&v88);
    v87 = v69;
    v18 = v69;
    if ( v69 )
    {
      Child = (SP_SPACE *)*((_QWORD *)v69 + 403);
      v85 = Child;
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
    v82 = 8;
    Health = SP_SPACE::GetHealth(
               Child,
               (struct _SIO_HEALTH_CONTEXT *)v100,
               (enum _SP_SPACE_STATE *)&MasterIrp[12].Tail,
               &v82);
    v21 = Health;
    if ( Health < 0 )
      goto LABEL_52;
    HIDWORD(MasterIrp[12].UserBuffer) = v100[0];
    HIDWORD(MasterIrp[12].CancelRoutine) = *((_DWORD *)v18 + 784);
    v22 = 1;
  }
  else
  {
    Health = 0;
    v37 = *((_DWORD *)v15 + 66) == 2;
    LODWORD(MasterIrp[12].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 1;
    HIDWORD(MasterIrp[12].CancelRoutine) = -1;
    HIDWORD(MasterIrp[12].UserBuffer) = !v37;
    v22 = *((_DWORD *)v15 + 66);
  }
  *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 11) = v22;
  v80 = 0;
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
  v25 = *((unsigned int *)v15 + 47);
  if ( (_DWORD)v25 )
  {
    LOBYTE(v23) = 3;
    RecordByRecordId = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23, v25);
    v27 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(RecordByRecordId) + 2);
  }
  else
  {
    v27 = GUID_NULL;
  }
  *(GUID *)&MasterIrp[13].CancelRoutine = v27;
  v28 = *((unsigned int *)v15 + 48);
  if ( (_DWORD)v28 )
  {
    LOBYTE(v23) = 3;
    v29 = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23, v28);
    v30 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(v29) + 2);
  }
  else
  {
    v30 = GUID_NULL;
  }
  MasterIrp[13].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = (LIST_ENTRY)v30;
  v31 = *((unsigned int *)v15 + 49);
  if ( (_DWORD)v31 )
  {
    LOBYTE(v23) = 3;
    v32 = (SDB_RECORD *)SDB_POOL_CONFIG::FindRecordByRecordId(*((_QWORD *)v10 + 6), v23, v31);
    v33 = (GUID)*((_OWORD *)SDB_RECORD::GetObject(v32) + 2);
  }
  else
  {
    v33 = GUID_NULL;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) += 2888;
  v34 = (wchar_t *)(&MasterIrp[13].Tail.CompletionKey + 8);
  v35 = *(_DWORD *)(&MasterIrp->Size + 1);
  v36 = Length - 2888;
  v37 = (v83 & 1) == 0;
  *((GUID *)&MasterIrp[13].Tail.CompletionKey + 1) = v33;
  *(_QWORD *)&v88.Data1 = (char *)MasterIrp + 2888;
  if ( v37 )
  {
    v60 = 0;
    v82 = 0;
    Extent = SDB_SPACE::GetExtent(v15, 0, &v90);
    if ( Extent )
    {
      do
      {
        v62 = SDB_RECORD::GetObject(Extent);
        Drive = SDB_EXTENT::GetDrive(v62);
        v64 = SDB_RECORD::GetObject(Drive);
        ++*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 10);
        v65 = v64;
        if ( v36 < 0x90 )
        {
          v36 = 0;
          v80 = 1;
        }
        else
        {
          if ( SDB_EXTENT::GetTier(v62) )
          {
            Tier = SDB_EXTENT::GetTier(v62);
            v67 = SDB_RECORD::GetObject(Tier);
            *(struct _GUID *)&(&MasterIrp[14].MdlAddress)[18 * v60] = v6;
            *((_OWORD *)&MasterIrp[14].AssociatedIrp.MasterIrp + 9 * v60) = *((_OWORD *)v67 + 2);
          }
          v68 = v85;
          *((struct _GUID *)&MasterIrp[13].Tail.CompletionKey + 9 * v60 + 4) = v6;
          *((struct _GUID *)&MasterIrp[13].Tail.CompletionKey + 9 * v60 + 5) = v7;
          (&MasterIrp[14].ThreadListEntry.Blink)[18 * v60] = (struct _LIST_ENTRY *)*((_QWORD *)v62 + 5);
          *(&MasterIrp[14].IoStatus.Status + 36 * v60) = *((_DWORD *)v62 + 16);
          *((_DWORD *)&MasterIrp[14].IoStatus.Pointer + 36 * v60 + 1) = *((_DWORD *)v62 + 17);
          *((_DWORD *)&MasterIrp[14].IoStatus.Information + 36 * v60) = *((_DWORD *)v62 + 18);
          *(struct _GUID *)((char *)&MasterIrp[14].IoStatus.Information + 144 * v60 + 4) = v6;
          *(_OWORD *)((char *)&(&MasterIrp[14].UserIosb)[18 * v60] + 4) = *((_OWORD *)v65 + 2);
          *((_QWORD *)&MasterIrp[14].Overlay.AsynchronousParameters.UserApcContext + 18 * v60) = *((_QWORD *)v62 + 6);
          *((_QWORD *)&MasterIrp[14].CancelRoutine + 18 * v60) = *((_QWORD *)v62 + 4);
          if ( v68 )
          {
            v99 = 0;
            *((_QWORD *)&v99 + 1) = *((_QWORD *)&MasterIrp[14].IoStatus.Pointer + 18 * v60);
            (*(void (__fastcall **)(_QWORD, __int64, struct _LIST_ENTRY *, _QWORD, __int128 *))(**((_QWORD **)v68 + 49)
                                                                                              + 96LL))(
              *((_QWORD *)v68 + 49),
              3,
              (&MasterIrp[14].ThreadListEntry.Blink)[18 * v60],
              0,
              &v99);
            *((_DWORD *)&MasterIrp[14].UserBuffer + 36 * v60) = v99;
            *((_WORD *)&MasterIrp[14].UserBuffer + 72 * v60 + 2) = WORD2(v99);
          }
          *(_QWORD *)&v88.Data1 += 144LL;
          v60 = v82 + 1;
          v15 = v91;
          v36 -= 144;
          ++v82;
        }
        v35 = *(_DWORD *)(&MasterIrp->Size + 1) + 144;
        *(_DWORD *)(&MasterIrp->Size + 1) = v35;
        Extent = SDB_SPACE::GetExtent(v15, Extent, &v90);
      }
      while ( Extent );
      v34 = *(wchar_t **)&v88.Data1;
      v18 = v87;
    }
    else
    {
      v34 = (wchar_t *)(&MasterIrp[13].Tail.CompletionKey + 8);
    }
  }
  if ( v18 )
  {
    v38 = (const wchar_t *)*((_QWORD *)v18 + 394);
    if ( v38 )
    {
      LODWORD(v39) = *((unsigned __int16 *)v18 + 1573);
      if ( v36 < (unsigned int)v39 )
      {
        v36 = 0;
        v80 = 1;
      }
      else
      {
        Health = RtlStringCbCopyW(v34, v36, v38);
        v21 = Health;
        if ( Health < 0 )
        {
          p_Data1 = v89;
          goto LABEL_50;
        }
        v40 = (int)v34;
        v34 = (wchar_t *)((char *)v34 + v39);
        LODWORD(MasterIrp[12].UserBuffer) = v40 - (_DWORD)MasterIrp;
        v36 -= v39;
      }
      *(_DWORD *)(&MasterIrp->Size + 1) += v39;
      v35 = *(_DWORD *)(&MasterIrp->Size + 1);
    }
  }
  v41 = (void *)*((_QWORD *)v15 + 22);
  if ( !v41 )
  {
    v41 = (void *)*((_QWORD *)Object + 29);
    if ( !v41 )
      v41 = (void *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 48);
  }
  v42 = (((_DWORD)v34 + 3) & 0xFFFFFFFC) - (_DWORD)v34;
  if ( v36 < v42 )
  {
    v43 = 0;
    v80 = 1;
  }
  else
  {
    v34 = (wchar_t *)((char *)v34 + v42);
    v43 = v36 - v42;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) = v42 + v35;
  v44 = RtlLengthSecurityDescriptor(v41);
  v45 = v44;
  if ( v43 < v44 )
  {
    v46 = 1;
    v48 = 0;
  }
  else
  {
    memmove(v34, v41, v44);
    v46 = v80;
    v47 = (_DWORD)v34 - (_DWORD)MasterIrp;
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 18) = v45;
    v34 = (wchar_t *)((char *)v34 + v45);
    *((_DWORD *)&MasterIrp[12].Tail.CompletionKey + 19) = v47;
    v48 = v43 - v45;
  }
  *(_DWORD *)(&MasterIrp->Size + 1) += v45;
  v49 = *(_DWORD *)(&MasterIrp->Size + 1);
  MasterIrp[13].AssociatedIrp.IrpCount = *((_DWORD *)v15 + 50);
  *(PVOID *)((char *)&MasterIrp[13].AssociatedIrp.SystemBuffer + 4) = 0;
  if ( *((_DWORD *)v15 + 51) )
  {
    v71 = (((_DWORD)v34 + 3) & 0xFFFFFFFC) - (_DWORD)v34;
    if ( v48 < v71 )
      v46 = 1;
    else
      v34 = (wchar_t *)((char *)v34 + v71);
    v73 = v48;
    v48 -= v71;
    if ( v73 < v71 )
      v48 = 0;
    v49 += v71;
    *(_DWORD *)(&MasterIrp->Size + 1) = v49;
    if ( *((_DWORD *)v15 + 51) )
    {
      v74 = 0;
      do
      {
        if ( v48 < 0x10 )
        {
          v48 = 0;
          v46 = 1;
        }
        else
        {
          *(_OWORD *)v34 = *(_OWORD *)(*((_QWORD *)v15 + 26) + 16LL * v74);
          if ( !LODWORD(MasterIrp[13].ThreadListEntry.Flink) )
            LODWORD(MasterIrp[13].ThreadListEntry.Flink) = (_DWORD)v34 - (_DWORD)MasterIrp;
          v34 += 8;
          v48 -= 16;
        }
        v75 = *(_DWORD *)(&MasterIrp->Size + 1);
        ++v74;
        ++HIDWORD(MasterIrp[13].AssociatedIrp.SystemBuffer);
        v49 = v75 + 16;
        *(_DWORD *)(&MasterIrp->Size + 1) = v49;
      }
      while ( v74 < *((_DWORD *)v15 + 51) );
    }
  }
  v50 = v85;
  *(struct _LIST_ENTRY **)((char *)&MasterIrp[13].ThreadListEntry.Flink + 4) = 0;
  if ( !v50 || (v83 & 2) != 0 )
  {
    p_Data1 = v89;
    v21 = Health;
LABEL_40:
    MasterIrp[13].Tail.Overlay.Thread = 0;
    if ( *((_QWORD *)v15 + 30) )
    {
      v52 = (((_DWORD)v34 + 3) & 0xFFFFFFFC) - (_DWORD)v34;
      if ( v48 < v52 )
        v46 = 1;
      else
        v34 = (wchar_t *)((char *)v34 + v52);
      *(_DWORD *)(&MasterIrp->Size + 1) += v52;
      for ( i = (SDB_RECORD *)*((_QWORD *)v15 + 30); i; i = (SDB_RECORD *)*((_QWORD *)v54 + 31) )
      {
        v54 = SDB_RECORD::GetObject(i);
        if ( v55 >= 0x10 )
        {
          *(_OWORD *)v34 = *((_OWORD *)v54 + 2);
          if ( !*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 9) )
            *((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 9) = (_DWORD)v34 - (_DWORD)MasterIrp;
          v34 += 8;
        }
        else
        {
          v46 = 1;
        }
        ++*((_DWORD *)&MasterIrp[13].Tail.CompletionKey + 8);
        *(_DWORD *)(&MasterIrp->Size + 1) += 16;
      }
    }
    v56 = (_DWORD)v34 - (_DWORD)MasterIrp;
    v18 = v87;
    if ( v46 )
      v21 = -2147483643;
    v94->IoStatus.Information = v56;
    goto LABEL_50;
  }
  v72 = (((_DWORD)v34 + 3) & 0xFFFFFFFC) - (_DWORD)v34;
  if ( v48 < v72 )
  {
    v48 = 0;
    v46 = 1;
  }
  else
  {
    v34 = (wchar_t *)((char *)v34 + v72);
    v48 -= v72;
  }
  v76 = v93;
  *(_DWORD *)(&MasterIrp->Size + 1) = v49 + v72;
  MetadataDrives = SDB_SPACE_CONFIG::GetMetadataDrives(
                     *((SDB_SPACE_CONFIG **)v50 + 41),
                     *((struct SDB_POOL_CONFIG **)v76 + 6),
                     v84,
                     &v86);
  p_Data1 = &v86->Data1;
  v21 = MetadataDrives;
  if ( MetadataDrives >= 0 )
  {
    v78 = v84[0];
    for ( j = 0; j < v78; *(_DWORD *)(&MasterIrp->Size + 1) += 16 )
    {
      if ( v48 < 0x10 )
      {
        v48 = 0;
        v46 = 1;
      }
      else
      {
        *(_OWORD *)v34 = p_Data1[j];
        if ( !LODWORD(MasterIrp[13].ThreadListEntry.Blink) )
          LODWORD(MasterIrp[13].ThreadListEntry.Blink) = (_DWORD)v34 - (_DWORD)MasterIrp;
        v34 += 8;
        v48 -= 16;
      }
      ++HIDWORD(MasterIrp[13].ThreadListEntry.Flink);
      ++j;
    }
    goto LABEL_40;
  }
  v18 = v87;
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
  v58 = "Exit ";
LABEL_58:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      85,
      (unsigned int)WPP_4418e0cc87393d873e5df6684ee1e024_Traceguids,
      (_DWORD)v58,
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
