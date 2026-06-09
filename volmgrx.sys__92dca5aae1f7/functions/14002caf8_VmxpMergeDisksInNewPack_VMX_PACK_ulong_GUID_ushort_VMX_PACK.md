# VmxpMergeDisksInNewPack(VMX_PACK *,ulong,_GUID *,ushort *,VMX_PACK * *)

- ea: `0x14002caf8`
- end: `0x14002d3e6`
- name: `?VmxpMergeDisksInNewPack@@YAJPEAVVMX_PACK@@KPEAU_GUID@@PEAGPEAPEAV1@@Z`
- size: `2286`
- prototype: `__int64 __fastcall(struct VMX_PACK *, unsigned int, struct _GUID *, unsigned __int16 *, struct VMX_PACK **)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140038d44`

## callees

- `0x140005f80`
- `0x140008d00`
- `0x140008dc8`
- `0x140008eec`
- `0x140009670`
- `0x140009718`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14001be80`
- `0x14002b0c4`
- `0x14002caf8`
- `0x14002d3ec`
- `0x14002fe20`
- `0x14003d81c`
- `0x140041970`
- `0x140041d3c`
- `0x14004e3ac`
- `0x14004e950`
- `0x140051db4`
- `0x140051e54`
- `0x14005d40c`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002cd4d`
- `ntoskrnl!ExAllocatePool2` at `0x14002cd4d`
- `ntoskrnl!ExUuidCreate` at `0x14002cc25`
- `ntoskrnl!ExUuidCreate` at `0x14002cc25`

## pseudocode

```c
__int64 __fastcall VmxpMergeDisksInNewPack(
        struct VMX_PACK *a1,
        unsigned int a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        struct VMX_PACK **a5)
{
  unsigned int v6; // r15d
  struct _GUID *v7; // rcx
  __int64 v8; // r12
  struct _GUID *v10; // r13
  __int64 v11; // rax
  VMX_NOTIFICATION_QUEUE *v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  struct VMX_PACK *v16; // rbp
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned int v20; // edx
  unsigned int i; // ecx
  __int64 Pool2; // rax
  VMX_NOTIFICATION_QUEUE *v23; // rcx
  __int64 v24; // rdx
  struct _GUID *v25; // rdx
  unsigned int v26; // r9d
  __int64 v27; // rcx
  struct VMX_RECORD *DiskById; // rax
  __int64 v29; // r14
  __int64 v30; // r13
  __int64 v31; // rbx
  int v32; // ebp
  __int64 v33; // rax
  __int64 v34; // rcx
  __int128 v35; // xmm1
  VMX_NOTIFICATION_QUEUE *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r14
  VMX_CONFIG **v39; // rax
  VMX_CONFIG **v40; // rbx
  unsigned int v41; // edx
  unsigned int v42; // edx
  VMX_CONFIG *v43; // rax
  VMX_GLOBAL_DATA **v44; // rcx
  VMX_CONFIG *v45; // rax
  __int64 v46; // rcx
  VMX_CONFIG *v47; // rax
  VMX_CONFIG *v48; // rax
  void **v49; // rcx
  unsigned int v50; // edx
  struct VMX_PACK *v51; // rax
  struct VMX_PACK **v52; // rcx
  unsigned int v53; // edx
  unsigned int v54; // edx
  VMX_CONFIG *v55; // rcx
  void **v56; // rax
  struct VMX_PACK *v57; // [rsp+20h] [rbp-48h] BYREF

  v6 = 0;
  v7 = (struct _GUID *)((char *)Global + 216);
  v8 = a2;
  v10 = a3;
  *a5 = 0;
  v11 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v11 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v11 && VmxpFindPackById(v7) )
  {
    v12 = WPP_GLOBAL_Control;
    v13 = -1070071719;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 274;
      goto LABEL_9;
    }
    return v13;
  }
  v16 = (struct VMX_PACK *)*((_QWORD *)a1 + 2);
  v57 = v16;
  v17 = *((_QWORD *)v16 + 1);
  v18 = VMX_ALLOCATED_OBJECT::operator new(184, 258, 2018798934);
  v19 = v18;
  if ( !v18 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v24 = 275;
    goto LABEL_126;
  }
  *(_OWORD *)v18 = 0;
  *(_OWORD *)(v18 + 16) = 0;
  *(_OWORD *)(v18 + 32) = 0;
  *(_QWORD *)(v18 + 48) = 0;
  *(_WORD *)(v18 + 48) = 1;
  *(_DWORD *)(v18 + 160) = 0;
  *(_QWORD *)(v18 + 168) = 0;
  *(_WORD *)(v18 + 176) = 0;
  *(_QWORD *)(v18 + 56) = a1;
  *(_OWORD *)(v18 + 64) = *(_OWORD *)(v17 + 8);
  RtlStringCbCopyA((NTSTRSAFE_PSTR)(v18 + 80), 0x20u, (NTSTRSAFE_PCSTR)(v17 + 24));
  v13 = ExUuidCreate((UUID *)(v19 + 112));
  if ( (v13 & 0x80000000) != 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 276;
      goto LABEL_9;
    }
    return v13;
  }
  for ( i = 0; i < 0x20; ++i )
  {
    v20 = (__int16)a4[i];
    if ( (char)a4[i] != a4[i] )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v12 = WPP_GLOBAL_Control;
      v13 = -1070071758;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v14 = 277;
        goto LABEL_9;
      }
      return v13;
    }
    *(_BYTE *)(v19 + i + 128) = v20;
    if ( !(_BYTE)v20 )
      break;
  }
  v13 = VMX_RECORD_INFO::SanityCheckMandatoryName((char *)(v19 + 128), v20);
  if ( (v13 & 0x80000000) != 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v14 = 278;
      goto LABEL_9;
    }
    return v13;
  }
  *(_DWORD *)(v19 + 160) = v8;
  Pool2 = ExAllocatePool2(258, 48 * v8, 538996054);
  *(_QWORD *)(v19 + 168) = Pool2;
  if ( !Pool2 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v24 = 279;
LABEL_126:
    WPP_SF_d(*((_QWORD *)v23 + 3), v24, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225626LL);
    return 3221225626LL;
  }
  while ( 1 )
  {
    if ( v6 >= (unsigned int)v8 )
    {
      v38 = 64;
      v39 = (VMX_CONFIG **)VMX_ALLOCATED_OBJECT::operator new(64, 258, 1632660822);
      v40 = v39;
      if ( !v39 )
      {
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3221225626LL;
        }
        v24 = 286;
        goto LABEL_126;
      }
      memset(v39, 0, 0x40u);
      v57 = (struct VMX_PACK *)v40;
      v32 = VMX_PACK::CopyPack((VMX_PACK *)v40, a1);
      if ( v32 < 0 )
      {
        VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v40, v41);
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v32;
        }
        v37 = 287;
        goto LABEL_60;
      }
      v32 = VmxpWritePendingPrimaryPackId((struct _GUID *)(v19 + 112));
      if ( v32 < 0 )
      {
        VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v40, v42);
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v32;
        }
        v37 = 288;
        goto LABEL_60;
      }
      v43 = (VMX_GLOBAL_DATA *)((char *)Global + 200);
      v44 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 26);
      if ( *v44 != (VMX_GLOBAL_DATA *)((char *)Global + 200) )
        goto LABEL_117;
      *v40 = v43;
      v40[1] = (VMX_CONFIG *)v44;
      *v44 = (VMX_GLOBAL_DATA *)v40;
      *((_QWORD *)v43 + 1) = v40;
      v45 = v40[2];
      v40[6] = (VMX_CONFIG *)v19;
      v46 = *((_QWORD *)v45 + 1);
      if ( *(_WORD *)(v46 + 72) != 3 )
        v38 = 56;
      *(_QWORD *)v19 = *(_QWORD *)(v38 + v46) + 1LL;
      v47 = v40[6];
      *(_OWORD *)((char *)v47 + 8) = *(_OWORD *)(v46 + 144);
      *(_OWORD *)((char *)v47 + 20) = *(_OWORD *)(v46 + 156);
      v32 = VMX_PACK::MergeDisksInNewPackTargetTransaction((VMX_PACK *)v40);
      if ( v32 < 0 )
      {
        VMX_CONFIG::AbortRecords(v40[2]);
        v40[6] = 0;
      }
      else
      {
        v32 = VMX_PACK::CommitChangeIdentityTransaction((VMX_PACK *)v40);
        if ( v32 >= 0 )
        {
          if ( (int)VmxpWritePrimaryPackId((struct _GUID *)((char *)Global + 232)) >= 0 )
            VmxpDeletePendingPrimaryPackId();
          if ( !*((_DWORD *)v40 + 9) )
          {
            v48 = *v40;
            if ( *((VMX_CONFIG ***)*v40 + 1) != v40 )
              goto LABEL_117;
            v49 = (void **)v40[1];
            if ( *v49 != v40 )
              goto LABEL_117;
            *v49 = v48;
            *((_QWORD *)v48 + 1) = v49;
            VmxpSendPackDepartNotifications((struct VMX_PACK *)v40);
            VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v40, v50);
            v40 = 0;
            v57 = 0;
          }
          VMX_PACK::MergeDisksInNewPackSourceCleanup(a1, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
          if ( *((_DWORD *)a1 + 9) )
          {
LABEL_104:
            VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
            if ( v40 )
            {
              *((_BYTE *)Global + 277) = 1;
              VmxpOnlinePack((struct VMX_PACK *)v40, &v57);
              *((_BYTE *)Global + 277) = 0;
              *a5 = v57;
              return 0;
            }
            v12 = WPP_GLOBAL_Control;
            v13 = -1070071767;
            if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
            {
              return v13;
            }
            v14 = 290;
LABEL_9:
            WPP_SF_d(*((_QWORD *)v12 + 3), v14, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v13);
            return v13;
          }
          v51 = *(struct VMX_PACK **)a1;
          if ( *(struct VMX_PACK **)(*(_QWORD *)a1 + 8LL) == a1 )
          {
            v52 = (struct VMX_PACK **)*((_QWORD *)a1 + 1);
            if ( *v52 == a1 )
            {
              *v52 = v51;
              *((_QWORD *)v51 + 1) = v52;
              VmxpSendPackDepartNotifications(a1);
              VMX_PACK::`scalar deleting destructor'(a1, v53);
              goto LABEL_104;
            }
          }
LABEL_117:
          __fastfail(3u);
        }
      }
      VMX_PACK::UpdateCounters(a1);
      VmxpDeletePendingPrimaryPackId();
      v55 = *v40;
      if ( *((VMX_CONFIG ***)*v40 + 1) == v40 )
      {
        v56 = (void **)v40[1];
        if ( *v56 == v40 )
        {
          *v56 = v55;
          *((_QWORD *)v55 + 1) = v56;
          VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v40, v54);
          VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            return (unsigned int)v32;
          }
          v37 = 289;
LABEL_60:
          WPP_SF_d(*((_QWORD *)v36 + 3), v37, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v32);
          return (unsigned int)v32;
        }
      }
      goto LABEL_117;
    }
    v25 = &v10[v6];
    v26 = 0;
LABEL_38:
    if ( v26 < v6 )
      break;
    DiskById = VMX_CONFIG::FindDiskById(v16, v25);
    if ( !DiskById )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v12 = WPP_GLOBAL_Control;
      v13 = -1070071800;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v13;
      }
      v14 = 281;
      goto LABEL_9;
    }
    v29 = *((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5);
    v30 = *(_QWORD *)(v29 + 128);
    if ( !v30 )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v12 = WPP_GLOBAL_Control;
      v13 = -1070071791;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v13;
      }
      v14 = 282;
      goto LABEL_9;
    }
    v31 = *(_QWORD *)(v30 + 104);
    if ( !v31 || *(_BYTE *)(v31 + 17) )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v12 = WPP_GLOBAL_Control;
      v13 = -1070071806;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v13;
      }
      v14 = 283;
      goto LABEL_9;
    }
    if ( *(_BYTE *)(v31 + 19) )
      goto LABEL_50;
    v32 = VMX_CONFIG::SynchronizeConfigCopy(v16, *(struct VMX_CONFIG_COPY **)(v30 + 104));
    VMX_PACK::UpdateCounters(a1);
    if ( !*(_BYTE *)(v31 + 19) )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v37 = 284;
        goto LABEL_60;
      }
      return (unsigned int)v32;
    }
    v16 = v57;
LABEL_50:
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 88LL))(v29);
    if ( (v13 & 0x80000000) != 0 )
    {
      VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v13;
      }
      v14 = 285;
      goto LABEL_9;
    }
    v33 = *(_QWORD *)(v19 + 168);
    LODWORD(v8) = a2;
    v34 = 6LL * v6++;
    *(_OWORD *)(v33 + 8 * v34) = *(_OWORD *)(v29 + 72);
    v35 = *(_OWORD *)(v29 + 72);
    *(_QWORD *)(v33 + 8 * v34 + 32) = v30;
    v10 = a3;
    *(_OWORD *)(v33 + 8 * v34 + 16) = v35;
    *(_BYTE *)(v33 + 8 * v34 + 40) = 0;
  }
  v27 = *(_QWORD *)&v10[v26].Data1 - *(_QWORD *)&v25->Data1;
  if ( !v27 )
    v27 = *(_QWORD *)v10[v26].Data4 - *(_QWORD *)v25->Data4;
  if ( v27 )
  {
    ++v26;
    goto LABEL_38;
  }
  VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v19);
  v12 = WPP_GLOBAL_Control;
  v13 = -1070071802;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v14 = 280;
    goto LABEL_9;
  }
  return v13;
}

```

## disassembly

```asm
0x14002caf8  mov     [rsp+arg_0], rbx
0x14002cafd  mov     [rsp+arg_10], r8
0x14002cb02  mov     [rsp+arg_8], edx
0x14002cb06  push    rbp
0x14002cb07  push    rsi
0x14002cb08  push    rdi
0x14002cb09  push    r12
0x14002cb0b  push    r13
0x14002cb0d  push    r14
0x14002cb0f  push    r15
0x14002cb11  sub     rsp, 30h
0x14002cb15  mov     rax, [rsp+68h+arg_20]
0x14002cb1d  mov     rsi, rcx
0x14002cb20  mov     rcx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002cb27  xor     r15d, r15d
0x14002cb2a  add     rcx, 0D8h; struct _GUID *
0x14002cb31  mov     r12d, edx
0x14002cb34  mov     r14, r9
0x14002cb37  mov     r13, r8
0x14002cb3a  mov     [rax], r15
0x14002cb3d  mov     rax, [rcx]
0x14002cb40  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14002cb47  jnz     short loc_14002CB54
0x14002cb49  mov     rax, [rcx+8]
0x14002cb4d  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x14002cb54  test    rax, rax
0x14002cb57  jz      short loc_14002CBA8
0x14002cb59  call    ?VmxpFindPackById@@YAPEAVVMX_PACK@@PEAU_GUID@@@Z; VmxpFindPackById(_GUID *)
0x14002cb5e  test    rax, rax
0x14002cb61  jz      short loc_14002CBA8
0x14002cb63  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cb6a  lea     rax, WPP_GLOBAL_Control
0x14002cb71  mov     ebx, 0C0380059h
0x14002cb76  cmp     rcx, rax
0x14002cb79  jz      short loc_14002CBA1
0x14002cb7b  mov     edx, [rcx+2Ch]
0x14002cb7e  test    dl, 2
0x14002cb81  jz      short loc_14002CBA1
0x14002cb83  cmp     byte ptr [rcx+29h], 2
0x14002cb87  jb      short loc_14002CBA1
0x14002cb89  mov     edx, 112h
0x14002cb8e  mov     rcx, [rcx+18h]
0x14002cb92  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002cb99  mov     r9d, ebx
0x14002cb9c  call    WPP_SF_d
0x14002cba1  mov     eax, ebx
0x14002cba3  jmp     loc_14002D3D0
0x14002cba8  mov     rbp, [rsi+10h]
0x14002cbac  mov     edx, 102h; unsigned __int64
0x14002cbb1  mov     r8d, 78546D56h; unsigned int
0x14002cbb7  mov     [rsp+68h+var_48], rbp
0x14002cbbc  mov     rbx, [rbp+8]
0x14002cbc0  lea     ecx, [rdx-4Ah]; unsigned __int64
0x14002cbc3  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002cbc8  mov     rdi, rax
0x14002cbcb  test    rax, rax
0x14002cbce  jz      loc_14002D38F
0x14002cbd4  xorps   xmm0, xmm0
0x14002cbd7  lea     r8, [rbx+18h]; pszSrc
0x14002cbdb  movups  xmmword ptr [rdi], xmm0
0x14002cbde  xor     eax, eax
0x14002cbe0  lea     rcx, [rdi+50h]; pszDest
0x14002cbe4  movups  xmmword ptr [rdi+10h], xmm0
0x14002cbe8  movups  xmmword ptr [rdi+20h], xmm0
0x14002cbec  mov     [rdi+30h], rax
0x14002cbf0  lea     edx, [rax+20h]; cbDest
0x14002cbf3  mov     word ptr [rdi+30h], 1
0x14002cbf9  mov     [rdi+0A0h], r15d
0x14002cc00  mov     [rdi+0A8h], r15
0x14002cc07  mov     [rdi+0B0h], r15w
0x14002cc0f  mov     [rdi+38h], rsi
0x14002cc13  movups  xmm0, xmmword ptr [rbx+8]
0x14002cc17  movdqu  xmmword ptr [rdi+40h], xmm0
0x14002cc1c  call    RtlStringCbCopyA
0x14002cc21  lea     rcx, [rdi+70h]; Uuid
0x14002cc25  call    cs:__imp_ExUuidCreate
0x14002cc2c  nop     dword ptr [rax+rax+00h]
0x14002cc31  mov     ebx, eax
0x14002cc33  test    eax, eax
0x14002cc35  jns     short loc_14002CC76
0x14002cc37  mov     rcx, rdi; this
0x14002cc3a  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cc46  lea     rax, WPP_GLOBAL_Control
0x14002cc4d  cmp     rcx, rax
0x14002cc50  jz      loc_14002CBA1
0x14002cc56  mov     edx, [rcx+2Ch]
0x14002cc59  test    dl, 2
0x14002cc5c  jz      loc_14002CBA1
0x14002cc62  cmp     byte ptr [rcx+29h], 2
0x14002cc66  jb      loc_14002CBA1
0x14002cc6c  mov     edx, 114h
0x14002cc71  jmp     loc_14002CB8E
0x14002cc76  mov     ecx, r15d
0x14002cc79  cmp     ecx, 20h ; ' '
0x14002cc7c  jnb     short loc_14002CCE2
0x14002cc7e  mov     r8d, ecx
0x14002cc81  movsx   edx, word ptr [r14+r8*2]; unsigned int
0x14002cc86  movsx   eax, dl
0x14002cc89  cmp     ax, dx
0x14002cc8c  jnz     short loc_14002CC9E
0x14002cc8e  mov     [rdi+r8+80h], dl
0x14002cc96  test    dl, dl
0x14002cc98  jz      short loc_14002CCE2
0x14002cc9a  inc     ecx
0x14002cc9c  jmp     short loc_14002CC79
0x14002cc9e  mov     rcx, rdi; this
0x14002cca1  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cca6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ccad  lea     rax, WPP_GLOBAL_Control
0x14002ccb4  mov     ebx, 0C0380032h
0x14002ccb9  cmp     rcx, rax
0x14002ccbc  jz      loc_14002CBA1
0x14002ccc2  mov     edx, [rcx+2Ch]
0x14002ccc5  test    dl, 2
0x14002ccc8  jz      loc_14002CBA1
0x14002ccce  cmp     byte ptr [rcx+29h], 2
0x14002ccd2  jb      loc_14002CBA1
0x14002ccd8  mov     edx, 115h
0x14002ccdd  jmp     loc_14002CB8E
0x14002cce2  lea     rcx, [rdi+80h]; char *
0x14002cce9  call    ?SanityCheckMandatoryName@VMX_RECORD_INFO@@SAJPEADK@Z; VMX_RECORD_INFO::SanityCheckMandatoryName(char *,ulong)
0x14002ccee  mov     ebx, eax
0x14002ccf0  test    eax, eax
0x14002ccf2  jns     short loc_14002CD33
0x14002ccf4  mov     rcx, rdi; this
0x14002ccf7  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002ccfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cd03  lea     rax, WPP_GLOBAL_Control
0x14002cd0a  cmp     rcx, rax
0x14002cd0d  jz      loc_14002CBA1
0x14002cd13  mov     edx, [rcx+2Ch]
0x14002cd16  test    dl, 2
0x14002cd19  jz      loc_14002CBA1
0x14002cd1f  cmp     byte ptr [rcx+29h], 2
0x14002cd23  jb      loc_14002CBA1
0x14002cd29  mov     edx, 116h
0x14002cd2e  jmp     loc_14002CB8E
0x14002cd33  lea     rdx, [r12+r12*2]
0x14002cd37  mov     [rdi+0A0h], r12d
0x14002cd3e  shl     rdx, 4
0x14002cd42  mov     ecx, 102h
0x14002cd47  mov     r8d, 20206D56h
0x14002cd4d  call    cs:__imp_ExAllocatePool2
0x14002cd54  nop     dword ptr [rax+rax+00h]
0x14002cd59  mov     [rdi+0A8h], rax
0x14002cd60  test    rax, rax
0x14002cd63  jnz     short loc_14002CDA3
0x14002cd65  mov     rcx, rdi; this
0x14002cd68  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cd74  lea     rax, WPP_GLOBAL_Control
0x14002cd7b  cmp     rcx, rax
0x14002cd7e  jz      loc_14002D3CB
0x14002cd84  mov     eax, [rcx+2Ch]
0x14002cd87  test    al, 2
0x14002cd89  jz      loc_14002D3CB
0x14002cd8f  cmp     byte ptr [rcx+29h], 2
0x14002cd93  jb      loc_14002D3CB
0x14002cd99  mov     edx, 117h
0x14002cd9e  jmp     loc_14002D3B5
0x14002cda3  cmp     r15d, r12d
0x14002cda6  jnb     loc_14002D046
0x14002cdac  mov     edx, r15d
0x14002cdaf  shl     rdx, 4
0x14002cdb3  add     rdx, r13; unsigned int
0x14002cdb6  mov     r12d, r15d
0x14002cdb9  xor     r9d, r9d
0x14002cdbc  cmp     r9d, r15d
0x14002cdbf  jnb     short loc_14002CDE8
0x14002cdc1  mov     r8d, r9d
0x14002cdc4  add     r8, r8
0x14002cdc7  mov     rcx, [r13+r8*8+0]
0x14002cdcc  sub     rcx, [rdx]
0x14002cdcf  jnz     short loc_14002CDDA
0x14002cdd1  mov     rcx, [r13+r8*8+8]
0x14002cdd6  sub     rcx, [rdx+8]
0x14002cdda  test    rcx, rcx
0x14002cddd  jz      loc_14002CEB1
0x14002cde3  inc     r9d
0x14002cde6  jmp     short loc_14002CDBC
0x14002cde8  mov     rcx, rbp; this
0x14002cdeb  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14002cdf0  test    rax, rax
0x14002cdf3  jz      loc_14002D002
0x14002cdf9  movzx   ecx, word ptr [rax+40h]
0x14002cdfd  and     ecx, 1
0x14002ce00  mov     r14, [rax+rcx*8+28h]
0x14002ce05  mov     r13, [r14+80h]
0x14002ce0c  test    r13, r13
0x14002ce0f  jz      loc_14002CFBE
0x14002ce15  mov     rbx, [r13+68h]
0x14002ce19  test    rbx, rbx
0x14002ce1c  jz      loc_14002CF7A
0x14002ce22  cmp     byte ptr [rbx+11h], 0
0x14002ce26  jnz     loc_14002CF7A
0x14002ce2c  cmp     byte ptr [rbx+13h], 0
0x14002ce30  jnz     short loc_14002CE56
0x14002ce32  mov     rdx, rbx; struct VMX_CONFIG_COPY *
0x14002ce35  mov     rcx, rbp; this
0x14002ce38  call    ?SynchronizeConfigCopy@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::SynchronizeConfigCopy(VMX_CONFIG_COPY *)
0x14002ce3d  mov     rcx, rsi; this
0x14002ce40  mov     ebp, eax
0x14002ce42  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14002ce47  cmp     byte ptr [rbx+13h], 0
0x14002ce4b  jz      loc_14002CEF5
0x14002ce51  mov     rbp, [rsp+68h+var_48]
0x14002ce56  mov     rax, [r14]
0x14002ce59  mov     rcx, r14
0x14002ce5c  mov     rax, [rax+58h]
0x14002ce60  call    _guard_dispatch_icall
0x14002ce65  mov     ebx, eax
0x14002ce67  test    eax, eax
0x14002ce69  js      loc_14002CF3C
0x14002ce6f  mov     rax, [rdi+0A8h]
0x14002ce76  lea     rcx, [r12+r12*2]
0x14002ce7a  movups  xmm0, xmmword ptr [r14+48h]
0x14002ce7f  mov     r12d, [rsp+68h+arg_8]
0x14002ce84  add     rcx, rcx
0x14002ce87  inc     r15d
0x14002ce8a  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x14002ce8f  movups  xmm1, xmmword ptr [r14+48h]
0x14002ce94  mov     [rax+rcx*8+20h], r13
0x14002ce99  mov     r13, [rsp+68h+arg_10]
0x14002cea1  movdqu  xmmword ptr [rax+rcx*8+10h], xmm1
0x14002cea7  mov     byte ptr [rax+rcx*8+28h], 0
0x14002ceac  jmp     loc_14002CDA3
0x14002ceb1  mov     rcx, rdi; this
0x14002ceb4  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002ceb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cec0  lea     rax, WPP_GLOBAL_Control
0x14002cec7  mov     ebx, 0C0380006h
0x14002cecc  cmp     rcx, rax
0x14002cecf  jz      loc_14002CBA1
0x14002ced5  mov     edx, [rcx+2Ch]
0x14002ced8  test    dl, 2
0x14002cedb  jz      loc_14002CBA1
0x14002cee1  cmp     byte ptr [rcx+29h], 2
0x14002cee5  jb      loc_14002CBA1
0x14002ceeb  mov     edx, 118h
0x14002cef0  jmp     loc_14002CB8E
0x14002cef5  mov     rcx, rdi; this
0x14002cef8  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cefd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf04  lea     rax, WPP_GLOBAL_Control
0x14002cf0b  cmp     rcx, rax
0x14002cf0e  jz      short loc_14002CF35
0x14002cf10  mov     eax, [rcx+2Ch]
0x14002cf13  test    al, 2
0x14002cf15  jz      short loc_14002CF35
0x14002cf17  cmp     byte ptr [rcx+29h], 2
0x14002cf1b  jb      short loc_14002CF35
0x14002cf1d  mov     edx, 11Ch
0x14002cf22  mov     rcx, [rcx+18h]
0x14002cf26  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002cf2d  mov     r9d, ebp
0x14002cf30  call    WPP_SF_d
0x14002cf35  mov     eax, ebp
0x14002cf37  jmp     loc_14002D3D0
0x14002cf3c  mov     rcx, rdi; this
0x14002cf3f  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf4b  lea     rax, WPP_GLOBAL_Control
0x14002cf52  cmp     rcx, rax
0x14002cf55  jz      loc_14002CBA1
0x14002cf5b  mov     eax, [rcx+2Ch]
0x14002cf5e  test    al, 2
0x14002cf60  jz      loc_14002CBA1
0x14002cf66  cmp     byte ptr [rcx+29h], 2
0x14002cf6a  jb      loc_14002CBA1
0x14002cf70  mov     edx, 11Dh
0x14002cf75  jmp     loc_14002CB8E
0x14002cf7a  mov     rcx, rdi; this
0x14002cf7d  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cf82  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf89  lea     rax, WPP_GLOBAL_Control
0x14002cf90  mov     ebx, 0C0380002h
0x14002cf95  cmp     rcx, rax
0x14002cf98  jz      loc_14002CBA1
0x14002cf9e  mov     edx, [rcx+2Ch]
0x14002cfa1  test    dl, 2
0x14002cfa4  jz      loc_14002CBA1
0x14002cfaa  cmp     byte ptr [rcx+29h], 2
0x14002cfae  jb      loc_14002CBA1
0x14002cfb4  mov     edx, 11Bh
0x14002cfb9  jmp     loc_14002CB8E
0x14002cfbe  mov     rcx, rdi; this
0x14002cfc1  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002cfc6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cfcd  lea     rax, WPP_GLOBAL_Control
0x14002cfd4  mov     ebx, 0C0380011h
0x14002cfd9  cmp     rcx, rax
0x14002cfdc  jz      loc_14002CBA1
0x14002cfe2  mov     edx, [rcx+2Ch]
0x14002cfe5  test    dl, 2
0x14002cfe8  jz      loc_14002CBA1
0x14002cfee  cmp     byte ptr [rcx+29h], 2
0x14002cff2  jb      loc_14002CBA1
0x14002cff8  mov     edx, 11Ah
0x14002cffd  jmp     loc_14002CB8E
  ... truncated ...
```
