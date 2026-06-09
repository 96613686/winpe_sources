# FilterDeviceIoControl

- ea: `0x140005bf0`
- end: `0x140006788`
- name: `FilterDeviceIoControl`
- size: `2968`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000443c`
- `0x140004568`
- `0x140005968`
- `0x140005bf0`
- `0x140006790`
- `0x14000ae10`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000db14`
- `0x14000e0e8`
- `0x14000e604`
- `0x14000f110`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140005d4a`
- `ntoskrnl!IofCompleteRequest` at `0x140005d4a`
- `NDIS!NdisGetDeviceReservedExtension` at `0x140005c55`
- `NDIS!NdisGetDeviceReservedExtension` at `0x140005c55`

## string_xrefs

- `0x140005fa4`: `FilterDeviceExtension->Signature == 'FTDR'`

## pseudocode

```c
__int64 __fastcall FilterDeviceIoControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v5; // r15d
  _DWORD *v6; // rsi
  char v7; // r12
  struct _IRP *MasterIrp; // rdi
  unsigned int Options; // ebp
  unsigned int Length; // r14d
  __int64 v11; // rax
  unsigned int Guid; // ebx
  int v13; // eax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  ULONG *p_Flags; // r14
  char *v27; // rcx
  __int64 v28; // rdx
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v34; // eax
  unsigned int v35; // ebp
  __int64 v36; // rax
  __int64 v37; // r8
  unsigned int v38; // ebp
  __int64 FilterModuleAndRef; // rax
  __int128 v40; // xmm0
  __int64 MatchingMpCtx; // rax
  int v42; // edx
  int v43; // r8d
  unsigned int v44; // [rsp+30h] [rbp-68h] BYREF
  __int128 v45; // [rsp+38h] [rbp-60h]
  __int128 v46; // [rsp+48h] [rbp-50h] BYREF

  v46 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( !CurrentStackLocation->FileObject )
    return 3221225473LL;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)NdisGetDeviceReservedExtension(DeviceObject) != 1179927634 )
    TraceAssert("FilterDeviceExtension->Signature == 'FTDR'", "onecoreuap\\net\\vwifi\\filter\\device.c", 587);
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  Irp->IoStatus.Information = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  switch ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
  {
    case 0x120004u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options < 0x14 || Length < 0x10 )
      {
        Guid = -1073741789;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 48;
        goto LABEL_157;
      }
      v38 = *(_DWORD *)&MasterIrp->Type;
      p_Flags = (ULONG *)(&MasterIrp->Size + 1);
      FilterModuleAndRef = filterFindFilterModuleAndRef(&MasterIrp->Size + 1);
      v6 = (_DWORD *)FilterModuleAndRef;
      if ( FilterModuleAndRef )
      {
        v7 = 1;
        if ( v38 )
        {
          MatchingMpCtx = FilterFindMatchingMpCtx(FilterModuleAndRef, v38);
          if ( !MatchingMpCtx || !*(_BYTE *)(MatchingMpCtx + 3) )
          {
            Guid = -1071448019;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_dq_guid_(
                WPP_GLOBAL_Control->AttachedDevice,
                v42,
                v43,
                v38,
                (_DWORD)v6,
                (__int64)(&MasterIrp->Size + 1));
            }
            goto LABEL_17;
          }
          v40 = *(_OWORD *)(MatchingMpCtx + 20);
        }
        else
        {
          v40 = *(_OWORD *)(FilterModuleAndRef + 2248);
        }
        Guid = 0;
        *(_OWORD *)&MasterIrp->Type = v40;
        v5 = 16;
        goto LABEL_17;
      }
      Guid = -1073741811;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v30 = 49;
LABEL_78:
      WPP_SF__guid_(v29->AttachedDevice, v30, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids, p_Flags);
      goto LABEL_17;
    case 0x120008u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options < 0x14 )
      {
        Guid = -1073741789;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 52;
        goto LABEL_157;
      }
      v36 = filterFindFilterModuleAndRef(MasterIrp);
      v6 = (_DWORD *)v36;
      if ( v36 )
      {
        LOBYTE(v37) = MasterIrp->Flags;
        v7 = 1;
        Guid = FilterSetVirtualAdapter(v36, 1, v37);
        if ( !Guid )
          goto LABEL_17;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v22 = 54;
        goto LABEL_168;
      }
      Guid = -1073741811;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v25 = 53;
      goto LABEL_162;
    case 0x12000Cu:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options < 0x14 )
      {
        Guid = -1073741789;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 61;
        goto LABEL_157;
      }
      v19 = filterFindFilterModuleAndRef(MasterIrp);
      v6 = (_DWORD *)v19;
      if ( v19 )
      {
        v7 = 1;
        if ( !*(_BYTE *)(v19 + 2659) )
        {
          Guid = -1073741637;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v16 = 63;
          goto LABEL_157;
        }
        if ( !LOBYTE(MasterIrp->Flags) )
        {
          v34 = *(_DWORD *)(v19 + 2684) - 1;
          if ( v34 > 3 )
          {
            v35 = v34;
            while ( 1 )
            {
              Guid = FilterSetVirtualAdapter(v6, v34, 0);
              if ( Guid )
                break;
              v34 = v35 - 1;
              v35 = v34;
              if ( v34 <= 3 )
                goto LABEL_50;
            }
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_17;
            }
            v22 = 64;
            goto LABEL_168;
          }
        }
LABEL_50:
        LOBYTE(v20) = MasterIrp->Flags;
        Guid = FilterSetVirtualAdapter(v6, 3, v20);
        if ( Guid )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v22 = 65;
          goto LABEL_168;
        }
        goto LABEL_44;
      }
      Guid = -1073741811;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v25 = 62;
LABEL_162:
      v33 = (__int64)MasterIrp;
      goto LABEL_163;
    case 0x120010u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options < 0x14 )
      {
        Guid = -1073741789;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 67;
        goto LABEL_157;
      }
      if ( !LOBYTE(MasterIrp->Flags) )
      {
        Guid = -1073741637;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 68;
        goto LABEL_157;
      }
      v17 = filterFindFilterModuleAndRef(MasterIrp);
      v6 = (_DWORD *)v17;
      if ( v17 )
      {
        v7 = 1;
        if ( !*(_BYTE *)(v17 + 2659) )
        {
          Guid = -1073741637;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v16 = 70;
          goto LABEL_157;
        }
        Guid = 0;
        LOBYTE(v18) = 1;
        FilterSetVirtualAdapter(v17, 0xFFFFFFFFLL, v18);
        goto LABEL_44;
      }
      Guid = -1073741811;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v25 = 69;
      goto LABEL_162;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1179668 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1179672 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options >= 0x10 && Length >= 0x18 )
      {
        v46 = *(_OWORD *)&MasterIrp->Type;
        Guid = filterFindGuid(&v46, MasterIrp);
        if ( Guid )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v25 = 74;
          v33 = (__int64)&v46;
          goto LABEL_163;
        }
        v5 = 24;
        goto LABEL_17;
      }
      Guid = -1073741789;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v16 = 73;
LABEL_157:
      WPP_SF_(v15->AttachedDevice, v16, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      goto LABEL_17;
    }
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1179676 )
    {
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1179680 )
      {
        Guid = -1073741811;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v22 = 84;
        goto LABEL_168;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      if ( Options < 0x24 )
      {
        Guid = -1073741789;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v16 = 56;
        goto LABEL_157;
      }
      v6 = (_DWORD *)filterFindFilterModuleAndRef(MasterIrp);
      if ( !v6 )
      {
        Guid = -1073741811;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v25 = 57;
        goto LABEL_162;
      }
      p_Flags = &MasterIrp->Flags;
      v27 = *(char **)&MasterIrp->Flags;
      v28 = 0xFFFFFFFFLL;
      v44 = -1;
      v7 = 1;
      v45 = 0;
      if ( !v27 )
        v27 = (char *)MasterIrp->AssociatedIrp.MasterIrp - *((_QWORD *)&v45 + 1);
      if ( v27 )
      {
        Guid = filterFindGuid2(v6, &MasterIrp->Flags, &v44);
        if ( Guid )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v30 = 58;
          goto LABEL_78;
        }
        v28 = v44;
      }
      LOBYTE(v23) = MasterIrp->ThreadListEntry.Flink;
      Guid = FilterSetVirtualAdapter(v6, v28, v23);
      if ( !Guid )
        goto LABEL_17;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v22 = 59;
LABEL_168:
      WPP_SF_d(v21->AttachedDevice, v22, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
    if ( Options < 0x14 )
    {
      Guid = -1073741789;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v16 = 76;
      goto LABEL_157;
    }
    v31 = filterFindFilterModuleAndRef(MasterIrp);
    v6 = (_DWORD *)v31;
    if ( !v31 )
    {
      Guid = -1073741811;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v25 = 77;
      goto LABEL_162;
    }
    v7 = 1;
    if ( !*(_BYTE *)(v31 + 2658) )
    {
      Guid = -1073741637;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v16 = 78;
      goto LABEL_157;
    }
    LOBYTE(v32) = MasterIrp->Flags;
    Guid = FilterSetVirtualAdapter(v31, 2, v32);
    if ( Guid )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_17;
      v22 = 79;
      goto LABEL_168;
    }
LABEL_44:
    v5 = 20;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  if ( Options < 0x10 )
  {
    Guid = -1073741789;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v16 = 81;
    goto LABEL_157;
  }
  if ( Length < 4 )
  {
    Guid = -1073741789;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v16 = 82;
    goto LABEL_157;
  }
  v11 = filterFindFilterModuleAndRef(MasterIrp);
  v6 = (_DWORD *)v11;
  if ( v11 )
  {
    Guid = 0;
    v7 = 1;
    v13 = *(_DWORD *)(v11
                    + 4
                    * ((*(_BYTE *)(*(_QWORD *)(v11 + 3120) + 144LL) != 0)
                     | (unsigned __int64)(*(_BYTE *)(*(_QWORD *)(v11 + 3120) + 288LL) != 0 ? 2 : 0))
                    + 2660);
    *(_DWORD *)&MasterIrp->Type = v13;
    if ( !v13 )
      *(_DWORD *)&MasterIrp->Type = v6[669];
    v5 = 4;
    goto LABEL_17;
  }
  Guid = -1073741811;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v25 = 83;
    v33 = 4;
LABEL_163:
    WPP_SF__guid_(v24->AttachedDevice, v25, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids, v33);
  }
LABEL_17:
  Irp->IoStatus.Information = v5;
  Irp->IoStatus.Status = Guid;
  IofCompleteRequest(Irp, 0);
  if ( v7 )
  {
    if ( !v6 )
      TraceAssert("pFilter", "onecoreuap\\net\\vwifi\\filter\\device.c", 891);
    FilterDeRef(v6);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids);
  return Guid;
}

```

## disassembly

```asm
0x140005bf0  mov     [rsp+arg_10], rbx
0x140005bf5  push    rbp
0x140005bf6  push    rsi
0x140005bf7  push    rdi
0x140005bf8  push    r12
0x140005bfa  push    r13
0x140005bfc  push    r14
0x140005bfe  push    r15
0x140005c00  sub     rsp, 60h
0x140005c04  mov     rax, cs:__security_cookie
0x140005c0b  xor     rax, rsp
0x140005c0e  mov     [rsp+98h+var_40], rax
0x140005c13  xorps   xmm0, xmm0
0x140005c16  mov     r13, rdx
0x140005c19  movups  [rsp+98h+var_50], xmm0
0x140005c1e  mov     rdi, rcx
0x140005c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c28  lea     rax, WPP_GLOBAL_Control
0x140005c2f  cmp     rcx, rax
0x140005c32  jnz     loc_140005D97
0x140005c38  mov     rbx, [r13+0B8h]
0x140005c3f  cmp     qword ptr [rbx+30h], 0
0x140005c44  jz      loc_140005F8D
0x140005c4a  mov     rcx, rdi; DeviceObject
0x140005c4d  xor     r15d, r15d
0x140005c50  xor     esi, esi
0x140005c52  xor     r12b, r12b
0x140005c55  call    cs:__imp_NdisGetDeviceReservedExtension
0x140005c5c  nop     dword ptr [rax+rax+00h]
0x140005c61  cmp     dword ptr [rax], 46544452h
0x140005c67  jnz     loc_140005F97
0x140005c6d  mov     rdi, [r13+18h]
0x140005c71  mov     [r13+38h], rsi
0x140005c75  mov     r9d, [rbx+18h]
0x140005c79  mov     eax, r9d
0x140005c7c  mov     ebp, [rbx+10h]
0x140005c7f  mov     r14d, [rbx+8]
0x140005c83  sub     eax, 120004h
0x140005c88  jz      loc_14000663F
0x140005c8e  sub     eax, 4
0x140005c91  jz      loc_140006528
0x140005c97  sub     eax, 4
0x140005c9a  jz      loc_140005F02
0x140005ca0  sub     eax, 4
0x140005ca3  jz      loc_140005E99
0x140005ca9  sub     eax, 4
0x140005cac  jnz     loc_140005DBC
0x140005cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cb9  lea     rax, WPP_GLOBAL_Control
0x140005cc0  cmp     rcx, rax
0x140005cc3  jnz     loc_14000629F
0x140005cc9  cmp     ebp, 10h
0x140005ccc  jb      loc_1400062C4
0x140005cd2  cmp     r14d, 4
0x140005cd6  jb      loc_1400062F5
0x140005cdc  mov     rcx, rdi
0x140005cdf  call    filterFindFilterModuleAndRef
0x140005ce4  mov     rsi, rax
0x140005ce7  test    rax, rax
0x140005cea  jz      loc_140006326
0x140005cf0  mov     rcx, [rax+0C30h]
0x140005cf7  xor     ebx, ebx
0x140005cf9  mov     r12b, 1
0x140005cfc  mov     al, [rcx+120h]
0x140005d02  neg     al
0x140005d04  sbb     rdx, rdx
0x140005d07  xor     eax, eax
0x140005d09  and     edx, 2
0x140005d0c  cmp     [rcx+90h], al
0x140005d12  setnz   al
0x140005d15  or      rdx, rax
0x140005d18  mov     eax, [rsi+rdx*4+0A64h]
0x140005d1f  mov     [rdi], eax
0x140005d21  test    eax, eax
0x140005d23  jnz     short loc_140005D2D
0x140005d25  mov     eax, [rsi+0A74h]
0x140005d2b  mov     [rdi], eax
0x140005d2d  mov     r15d, 4
0x140005d33  lea     r14, WPP_GLOBAL_Control
0x140005d3a  mov     eax, r15d
0x140005d3d  xor     edx, edx; PriorityBoost
0x140005d3f  mov     rcx, r13; Irp
0x140005d42  mov     [r13+38h], rax
0x140005d46  mov     [r13+30h], ebx
0x140005d4a  call    cs:__imp_IofCompleteRequest
0x140005d51  nop     dword ptr [rax+rax+00h]
0x140005d56  test    r12b, r12b
0x140005d59  jnz     loc_140005E83
0x140005d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d66  cmp     rcx, r14
0x140005d69  jnz     loc_140005E0C
0x140005d6f  mov     eax, ebx
0x140005d71  mov     rcx, [rsp+98h+var_40]
0x140005d76  xor     rcx, rsp; StackCookie
0x140005d79  call    __security_check_cookie
0x140005d7e  mov     rbx, [rsp+98h+arg_10]
0x140005d86  add     rsp, 60h
0x140005d8a  pop     r15
0x140005d8c  pop     r14
0x140005d8e  pop     r13
0x140005d90  pop     r12
0x140005d92  pop     rdi
0x140005d93  pop     rsi
0x140005d94  pop     rbp
0x140005d95  retn
0x140005d97  mov     eax, [rcx+2Ch]
0x140005d9a  test    al, 20h
0x140005d9c  jz      loc_140005C38
0x140005da2  mov     rcx, [rcx+18h]
0x140005da6  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140005dad  mov     edx, 2Eh ; '.'
0x140005db2  call    WPP_SF_
0x140005db7  jmp     loc_140005C38
0x140005dbc  sub     eax, 4
0x140005dbf  jnz     loc_140005FB5
0x140005dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005dcc  lea     rax, WPP_GLOBAL_Control
0x140005dd3  cmp     rcx, rax
0x140005dd6  jnz     short loc_140005E34
0x140005dd8  cmp     ebp, 10h
0x140005ddb  jb      short loc_140005E52
0x140005ddd  cmp     r14d, 18h
0x140005de1  jb      short loc_140005E52
0x140005de3  movups  xmm0, xmmword ptr [rdi]
0x140005de6  mov     rdx, rdi
0x140005de9  lea     rcx, [rsp+98h+var_50]
0x140005dee  movdqu  [rsp+98h+var_50], xmm0
0x140005df4  call    filterFindGuid
0x140005df9  mov     ebx, eax
0x140005dfb  test    eax, eax
0x140005dfd  jnz     loc_14000626E
0x140005e03  lea     r15d, [rax+18h]
0x140005e07  jmp     loc_140005D33
0x140005e0c  mov     eax, [rcx+2Ch]
0x140005e0f  test    al, 20h
0x140005e11  jz      loc_140005D6F
0x140005e17  mov     rcx, [rcx+18h]
0x140005e1b  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140005e22  mov     edx, 55h ; 'U'
0x140005e27  mov     r9d, ebx
0x140005e2a  call    WPP_SF_d
0x140005e2f  jmp     loc_140005D6F
0x140005e34  mov     eax, [rcx+2Ch]
0x140005e37  test    al, 20h
0x140005e39  jz      short loc_140005DD8
0x140005e3b  mov     rcx, [rcx+18h]
0x140005e3f  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140005e46  mov     edx, 48h ; 'H'
0x140005e4b  call    WPP_SF_
0x140005e50  jmp     short loc_140005DD8
0x140005e52  mov     ebx, 0C0000023h
0x140005e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e5e  lea     r14, WPP_GLOBAL_Control
0x140005e65  cmp     rcx, r14
0x140005e68  jz      loc_140005D3A
0x140005e6e  mov     eax, [rcx+2Ch]
0x140005e71  test    al, 1
0x140005e73  jz      loc_140005D3A
0x140005e79  mov     edx, 49h ; 'I'
0x140005e7e  jmp     loc_140006588
0x140005e83  test    rsi, rsi
0x140005e86  jz      loc_14000676A
0x140005e8c  mov     rcx, rsi; VirtualAddress
0x140005e8f  call    FilterDeRef
0x140005e94  jmp     loc_140005D5F
0x140005e99  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ea0  lea     r14, WPP_GLOBAL_Control
0x140005ea7  cmp     rcx, r14
0x140005eaa  jnz     loc_14000635B
0x140005eb0  cmp     ebp, 14h
0x140005eb3  jb      loc_140006380
0x140005eb9  cmp     [rdi+10h], sil
0x140005ebd  jz      loc_1400063AA
0x140005ec3  mov     rcx, rdi
0x140005ec6  call    filterFindFilterModuleAndRef
0x140005ecb  mov     rsi, rax
0x140005ece  test    rax, rax
0x140005ed1  jz      loc_1400063D4
0x140005ed7  mov     r12b, 1
0x140005eda  cmp     [rax+0A63h], r15b
0x140005ee1  jz      loc_1400063FE
0x140005ee7  xor     ebx, ebx
0x140005ee9  mov     r8b, r12b
0x140005eec  or      edx, 0FFFFFFFFh
0x140005eef  mov     rcx, rax
0x140005ef2  call    FilterSetVirtualAdapter
0x140005ef7  mov     r15d, 14h
0x140005efd  jmp     loc_140005D3A
0x140005f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f09  lea     r14, WPP_GLOBAL_Control
0x140005f10  cmp     rcx, r14
0x140005f13  jnz     loc_140006429
0x140005f19  cmp     ebp, 14h
0x140005f1c  jb      loc_14000644E
0x140005f22  mov     rcx, rdi
0x140005f25  call    filterFindFilterModuleAndRef
0x140005f2a  mov     rsi, rax
0x140005f2d  test    rax, rax
0x140005f30  jz      loc_140006478
0x140005f36  mov     r12b, 1
0x140005f39  cmp     [rax+0A63h], r15b
0x140005f40  jz      loc_1400064A2
0x140005f46  cmp     [rdi+10h], r15b
0x140005f4a  jz      loc_1400064CD
0x140005f50  mov     r8b, [rdi+10h]
0x140005f54  mov     edx, 3
0x140005f59  mov     rcx, rsi
0x140005f5c  call    FilterSetVirtualAdapter
0x140005f61  mov     ebx, eax
0x140005f63  test    eax, eax
0x140005f65  jz      short loc_140005EF7
0x140005f67  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f6e  cmp     rcx, r14
0x140005f71  jz      loc_140005D3A
0x140005f77  mov     eax, [rcx+2Ch]
0x140005f7a  test    r12b, al
0x140005f7d  jz      loc_140005D3A
0x140005f83  mov     edx, 41h ; 'A'
0x140005f88  jmp     loc_140006627
0x140005f8d  mov     eax, 0C0000001h
0x140005f92  jmp     loc_140005D71
0x140005f97  mov     r8d, 24Bh
0x140005f9d  lea     rdx, aOnecoreuapNetV_0; "onecoreuap\\net\\vwifi\\filter\\device."...
0x140005fa4  lea     rcx, aFilterdeviceex; "FilterDeviceExtension->Signature == 'FT"...
0x140005fab  call    TraceAssert
0x140005fb0  jmp     loc_140005C6D
0x140005fb5  sub     eax, 4
0x140005fb8  jz      loc_140006160
0x140005fbe  cmp     eax, 4
0x140005fc1  jz      short loc_140005FF4
0x140005fc3  mov     ebx, 0C000000Dh
0x140005fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fcf  lea     r14, WPP_GLOBAL_Control
0x140005fd6  cmp     rcx, r14
0x140005fd9  jz      loc_140005D3A
0x140005fdf  mov     eax, [rcx+2Ch]
0x140005fe2  test    al, 1
0x140005fe4  jz      loc_140005D3A
0x140005fea  mov     edx, 54h ; 'T'
0x140005fef  jmp     loc_14000662A
0x140005ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ffb  lea     r14, WPP_GLOBAL_Control
0x140006002  cmp     rcx, r14
0x140006005  jz      short loc_140006023
0x140006007  mov     eax, [rcx+2Ch]
0x14000600a  test    al, 20h
0x14000600c  jz      short loc_140006023
0x14000600e  mov     rcx, [rcx+18h]
0x140006012  lea     r8, WPP_d5e31b45fa4f31b576e451b1be9986c5_Traceguids
0x140006019  mov     edx, 37h ; '7'
0x14000601e  call    WPP_SF_
0x140006023  cmp     ebp, 24h ; '$'
0x140006026  jnb     short loc_140006052
0x140006028  mov     ebx, 0C0000023h
0x14000602d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006034  cmp     rcx, r14
0x140006037  jz      loc_140005D3A
0x14000603d  mov     eax, [rcx+2Ch]
0x140006040  test    al, 1
0x140006042  jz      loc_140005D3A
0x140006048  mov     edx, 38h ; '8'
0x14000604d  jmp     loc_140006588
0x140006052  mov     rcx, rdi
0x140006055  call    filterFindFilterModuleAndRef
0x14000605a  mov     rsi, rax
0x14000605d  test    rax, rax
0x140006060  jnz     short loc_14000608B
0x140006062  mov     ebx, 0C000000Dh
0x140006067  mov     rcx, cs:WPP_GLOBAL_Control
0x14000606e  cmp     rcx, r14
0x140006071  jz      loc_140005D3A
0x140006077  mov     edx, [rcx+2Ch]
0x14000607a  test    dl, 1
0x14000607d  jz      loc_140005D3A
0x140006083  lea     edx, [rax+39h]
0x140006086  jmp     loc_1400065D0
0x14000608b  xorps   xmm0, xmm0
0x14000608e  lea     r14, [rdi+10h]
0x140006092  mov     rcx, [r14]
0x140006095  or      edx, 0FFFFFFFFh
0x140006098  movq    rax, xmm0
0x14000609d  mov     [rsp+98h+var_68], edx
0x1400060a1  mov     r12b, 1
0x1400060a4  movups  [rsp+98h+var_60], xmm0
0x1400060a9  sub     rcx, rax
0x1400060ac  jnz     short loc_1400060B7
0x1400060ae  mov     rcx, [r14+8]
0x1400060b2  sub     rcx, qword ptr [rsp+98h+var_60+8]
0x1400060b7  test    rcx, rcx
0x1400060ba  jz      short loc_14000611D
0x1400060bc  lea     r8, [rsp+98h+var_68]
0x1400060c1  mov     rdx, r14
0x1400060c4  mov     rcx, rsi
0x1400060c7  call    filterFindGuid2
0x1400060cc  mov     ebx, eax
0x1400060ce  test    eax, eax
0x1400060d0  jz      short loc_140006119
0x1400060d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060d9  lea     rax, WPP_GLOBAL_Control
0x1400060e0  cmp     rcx, rax
  ... truncated ...
```
