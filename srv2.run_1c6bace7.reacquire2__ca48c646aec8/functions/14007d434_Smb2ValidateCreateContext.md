# Smb2ValidateCreateContext

- ea: `0x14007d434`
- end: `0x14007e2bd`
- name: `Smb2ValidateCreateContext`
- size: `3721`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007d0b0`

## callees

- `0x140014120`
- `0x14001a554`
- `0x14001d6e4`
- `0x14001ef80`
- `0x14002019c`
- `0x1400222ec`
- `0x140022690`
- `0x140022958`
- `0x140032a78`
- `0x140038490`
- `0x140038560`
- `0x140038680`
- `0x14007d434`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14007de82`
- `ntoskrnl!RtlCompareMemory` at `0x14007de82`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007e26d`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007e26d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007e252`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007e252`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007e0b9`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007e0b9`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007e1a1`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007e1a1`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14007d9bd`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14007d9bd`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007d6c0`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007d6c0`

## pseudocode

```c
__int64 __fastcall Smb2ValidateCreateContext(__int64 a1, GUID *a2, __int64 a3, __int64 a4, ULONGLONG ullOperand)
{
  _OWORD *v5; // r14
  __int64 v6; // rbx
  __int64 v8; // r12
  unsigned int Data1; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // edx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  ULONG v17; // edi
  NTSTATUS v18; // r15d
  __int64 v19; // rcx
  __int128 v20; // xmm1
  int Lease; // ebx
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  __int128 v25; // xmm0
  NTSTATUS ParameterList; // eax
  NTSTATUS v27; // r12d
  _DWORD *v28; // r14
  NTSTATUS Parameter; // r14d
  ULONG pulResult; // [rsp+30h] [rbp-30h] BYREF
  ULONG ErrorOffset[2]; // [rsp+38h] [rbp-28h] BYREF
  GUID Source1; // [rsp+40h] [rbp-20h] BYREF

  v5 = (_OWORD *)a4;
  v6 = *(_QWORD *)(a1 + 560);
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL);
  if ( a3 != 4 )
  {
    if ( a3 != 16 )
      return 0;
    Source1 = *a2;
    if ( RtlCompareMemory(&Source1, &Smb2RkfGuidEcpIn, 0x10u) == 16 && !*(_BYTE *)(*(_QWORD *)(v8 + 56) + 509LL) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
      }
      v10 = 19;
      goto LABEL_98;
    }
    if ( !Smb2IsKnownPassthroughEcp(&Source1, 1) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
      }
      return 0;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
    }
    if ( !memcmp(&Source1, &GUID_ECP_NETWORK_APP_INSTANCE, 0x10u) )
    {
      if ( ullOperand != 20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 20;
        goto LABEL_98;
      }
      v25 = *(_OWORD *)((char *)v5 + 4);
      *(_BYTE *)(v6 + 400) = 1;
      *(_OWORD *)(v6 + 384) = v25;
      goto LABEL_214;
    }
    if ( !memcmp(&Source1, &GUID_ECP_NETWORK_APP_INSTANCE_VERSION, 0x10u) )
    {
      if ( *(_WORD *)(v8 + 44) >= 0x311u )
      {
        if ( ullOperand != 24 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
          }
          v10 = 21;
          goto LABEL_98;
        }
        *(_QWORD *)(v6 + 408) = *((_QWORD *)v5 + 1);
        *(_QWORD *)(v6 + 416) = *((_QWORD *)v5 + 2);
      }
      goto LABEL_214;
    }
    *(_QWORD *)ErrorOffset = 0;
    if ( *(_QWORD *)(v6 + 320)
      || (ParameterList = FsRtlAllocateExtraCreateParameterList(0, (PECP_LIST *)(v6 + 320)),
          v27 = ParameterList,
          ParameterList >= 0) )
    {
      if ( !*(_BYTE *)(*(_QWORD *)(v6 + 32) + 285LL)
        && memcmp(&Source1, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0x10u)
        && memcmp(&Source1, &GUID_ECP_ENABLE_REDIRECTIONGUARD, 0x10u) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
        }
        return 3221225506LL;
      }
      v27 = FsRtlAllocateExtraCreateParameter(&Source1, ullOperand, 0, 0, 0x5324534Cu, (PVOID *)ErrorOffset);
      if ( v27 >= 0 )
      {
        memmove(*(void **)ErrorOffset, v5, ullOperand);
        v28 = *(_DWORD **)ErrorOffset;
        if ( (*(_DWORD *)(*(_QWORD *)(v6 + 56) + 84LL) & 0x1000000) != 0
          && !memcmp(&Source1, &Smb2RkfGuidEcpIn, 0x10u)
          && ullOperand >= 0x68
          && (unsigned int)(*v28 - 1) <= 2 )
        {
          *(_BYTE *)(v6 + 309) = 1;
        }
        Parameter = FsRtlInsertExtraCreateParameter(*(PECP_LIST *)(v6 + 320), v28);
        if ( Parameter < 0 )
        {
          FsRtlFreeExtraCreateParameter(*(PVOID *)ErrorOffset);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              41,
              WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
              a1,
              *(_QWORD *)ErrorOffset);
          }
          return (unsigned int)Parameter;
        }
LABEL_214:
        if ( Smb2IsKnownPassthroughEcp(&Source1, 0) )
          *(_BYTE *)(v6 + 328) = 1;
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
        a1,
        ParameterList);
    }
    return (unsigned int)v27;
  }
  Data1 = a2->Data1;
  if ( a2->Data1 > 0x516E4844 )
  {
    switch ( Data1 )
    {
      case 0x6341784Du:
        *(_BYTE *)(v6 + 304) = 1;
        if ( ullOperand == 8 )
          *(_QWORD *)(v6 + 312) = *(_QWORD *)a4;
        else
          *(_QWORD *)(v6 + 312) = 0;
        return 0;
      case 0x64694651u:
        *(_BYTE *)(v6 + 305) = 1;
        return 0;
      case 0x69536C41u:
        if ( ullOperand != 8 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
          }
          v10 = 11;
          goto LABEL_98;
        }
        *(_QWORD *)(v6 + 240) = *(_QWORD *)a4;
        return 0;
      case 0x70725754u:
        if ( ullOperand != 8 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
          }
          v10 = 6;
          goto LABEL_98;
        }
        *(_QWORD *)(v6 + 232) = *(_QWORD *)a4;
        return 0;
    }
    if ( Data1 != 1934389586 )
      return 0;
    if ( *(_WORD *)(v8 + 44) < 0x210u )
      return 0;
    if ( !Smb2LeasingEnabled )
      return 0;
    v19 = *(_QWORD *)(v6 + 56);
    if ( (*(_DWORD *)(v19 + 80) & 0x20000) != 0 )
      return 0;
    if ( *(_BYTE *)(v6 + 306) == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      v10 = 12;
      goto LABEL_98;
    }
    if ( (*(_DWORD *)(v19 + 84) & 0x1000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      return 0;
    }
    if ( ullOperand == 32 )
    {
      *(_OWORD *)(v6 + 248) = *(_OWORD *)a4;
      v20 = *(_OWORD *)(a4 + 16);
      *(_WORD *)(v6 + 300) = 0;
      *(_WORD *)(v6 + 296) = 0;
      *(_OWORD *)(v6 + 264) = v20;
      if ( !*(_BYTE *)(v19 + 88) )
      {
LABEL_149:
        Smb2LeaseStateMapToOplock(*(unsigned int *)(v6 + 264), v6 + 302);
        return 0;
      }
      LOBYTE(a4) = 1;
      *(_BYTE *)(v6 + 306) = 1;
      LOBYTE(a3) = 1;
      Lease = Smb2FindOrCreateLease(a1, (int)v6 + 248, a3, a4, 0);
      if ( Lease >= 0 )
        return 0;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v23 = 24;
LABEL_155:
        WPP_SF_(v22->AttachedDevice, v23, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
    }
    else
    {
      if ( ullOperand != 52 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 14;
        goto LABEL_98;
      }
      *(_WORD *)(v6 + 300) = 1;
      *(_OWORD *)(v6 + 248) = *(_OWORD *)a4;
      *(_OWORD *)(v6 + 264) = *(_OWORD *)(a4 + 16);
      *(_OWORD *)(v6 + 280) = *(_OWORD *)(a4 + 32);
      *(_DWORD *)(v6 + 296) = *(_DWORD *)(a4 + 48);
      if ( !*(_BYTE *)(v19 + 88) )
        goto LABEL_149;
      v24 = *(_DWORD *)(v6 + 268);
      *(_BYTE *)(v6 + 306) = 1;
      if ( (v24 & 4) != 0 )
        *(_BYTE *)(v6 + 301) = 1;
      LOBYTE(a4) = 1;
      LOBYTE(a3) = 1;
      Lease = Smb2FindOrCreateLease(a1, (int)v6 + 248, a3, a4, v6 + 296);
      if ( Lease >= 0 )
        return 0;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v23 = 25;
        goto LABEL_155;
      }
    }
    return (unsigned int)Lease;
  }
  if ( Data1 == 1366181956 )
  {
    if ( ullOperand != 16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      v10 = 7;
      goto LABEL_98;
    }
    if ( *(_BYTE *)(v6 + 377) || *(_BYTE *)(v6 + 378) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
      }
      v10 = 8;
      goto LABEL_98;
    }
    *(_BYTE *)(v6 + 352) = 1;
    return 0;
  }
  if ( Data1 != 1098152005 )
  {
    if ( Data1 == 1127368772 )
    {
      if ( ullOperand != 36 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 17;
        goto LABEL_98;
      }
      if ( *(_BYTE *)(v6 + 352) || *(_BYTE *)(v6 + 360) || *(_BYTE *)(v6 + 377) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 18;
        goto LABEL_98;
      }
      *(_BYTE *)(v6 + 378) = 1;
      if ( (*(_BYTE *)(v8 + 49) & 4) != 0 && (*(_BYTE *)(a4 + 32) & 2) != 0 )
      {
        v15 = *(_QWORD *)(v6 + 56);
        if ( (*(_DWORD *)(v15 + 80) & 0x4000) != 0 && !*(_DWORD *)(v15 + 76) )
        {
          *(_BYTE *)(v6 + 379) = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
          }
        }
      }
      *(_OWORD *)(v6 + 336) = v5[1];
      *(_OWORD *)(v6 + 361) = *v5;
    }
    else if ( Data1 == 1131300932 )
    {
      if ( ullOperand != 16 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 9;
        goto LABEL_98;
      }
      if ( *(_BYTE *)(v6 + 377) || *(_BYTE *)(v6 + 378) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 10;
        goto LABEL_98;
      }
      *(_BYTE *)(v6 + 360) = 1;
      *(_OWORD *)(v6 + 361) = *(_OWORD *)a4;
    }
    else
    {
      if ( Data1 != 1147364691 )
      {
        if ( Data1 == 1362249796 )
        {
          if ( ullOperand != 32 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
            }
            v10 = 15;
LABEL_98:
            Smb2LkmdTelCollectParsingFailureCreateHelper(v6, v10);
            return 3221225485LL;
          }
          if ( *(_BYTE *)(v6 + 352) || *(_BYTE *)(v6 + 360) || *(_BYTE *)(v6 + 378) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
            }
            v10 = 16;
            goto LABEL_98;
          }
          *(_BYTE *)(v6 + 377) = 1;
          if ( (*(_BYTE *)(v8 + 49) & 4) != 0 && (*(_BYTE *)(a4 + 4) & 2) != 0 )
          {
            v11 = *(_QWORD *)(v6 + 56);
            if ( (*(_DWORD *)(v11 + 80) & 0x4000) != 0 && !*(_DWORD *)(v11 + 76) )
            {
              *(_BYTE *)(v6 + 379) = 1;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
              }
            }
          }
          if ( *(_DWORD *)v5 )
          {
            v12 = 300000;
            if ( *(_DWORD *)v5 < 0x493E0u )
              v12 = *(_DWORD *)v5;
          }
          else
          {
            v12 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 56) + 96LL) + 300LL);
            if ( !v12 )
              v12 = Smb2DurableHandleV2TimeoutInMs;
          }
          *(_DWORD *)(v6 + 356) = v12;
          *(_OWORD *)(v6 + 336) = v5[1];
        }
        return 0;
      }
      pulResult = 0;
      if ( *(_QWORD *)(v6 + 224) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v10 = 5;
        goto LABEL_98;
      }
      if ( RtlULongLongToULong(ullOperand, &pulResult) < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return 3221225485LL;
        }
        v14 = 14;
        goto LABEL_106;
      }
      if ( !RtlValidRelativeSecurityDescriptor(v5, pulResult, 0) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          return 3221225485LL;
        }
        v14 = 15;
        goto LABEL_106;
      }
      *(_QWORD *)(v6 + 224) = v5;
    }
    return 0;
  }
  if ( *(_QWORD *)(v6 + 208) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    v10 = 4;
    goto LABEL_98;
  }
  if ( !ullOperand )
    return 0;
  pulResult = 0;
  ErrorOffset[0] = 0;
  if ( RtlULongLongToULong(ullOperand, &pulResult) < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225485LL;
    }
    v14 = 11;
LABEL_106:
    WPP_SF_(v13->AttachedDevice, v14, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    return 3221225485LL;
  }
  v17 = pulResult;
  v18 = IoCheckEaBufferValidity((PFILE_FULL_EA_INFORMATION)v5, pulResult, ErrorOffset);
  if ( v18 >= 0 )
  {
    *(_QWORD *)(v6 + 208) = v5;
    *(_DWORD *)(v6 + 216) = v17;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14007d434  mov     [rsp-38h+arg_10], rbx
0x14007d439  push    rbp
0x14007d43a  push    rsi
0x14007d43b  push    rdi
0x14007d43c  push    r12
0x14007d43e  push    r13
0x14007d440  push    r14
0x14007d442  push    r15
0x14007d444  mov     rbp, rsp
0x14007d447  sub     rsp, 60h
0x14007d44b  mov     rax, cs:__security_cookie
0x14007d452  xor     rax, rsp
0x14007d455  mov     [rbp+var_10], rax
0x14007d459  mov     rax, [rcx+60h]
0x14007d45d  mov     r14, r9
0x14007d460  mov     rbx, [rcx+230h]
0x14007d467  mov     r13, rcx
0x14007d46a  mov     r12, [rax+1F0h]
0x14007d471  cmp     r8, 4
0x14007d475  jnz     loc_14007DE5D
0x14007d47b  mov     eax, [rdx]
0x14007d47d  mov     ecx, 516E4844h
0x14007d482  cmp     eax, ecx
0x14007d484  ja      loc_14007DACE
0x14007d48a  jz      loc_14007DA21
0x14007d490  cmp     eax, 41747845h
0x14007d495  jz      loc_14007D901
0x14007d49b  cmp     eax, 43324844h
0x14007d4a0  jz      loc_14007D7CD
0x14007d4a6  cmp     eax, 436E4844h
0x14007d4ab  jz      loc_14007D714
0x14007d4b1  cmp     eax, 44636553h
0x14007d4b6  jz      loc_14007D621
0x14007d4bc  cmp     eax, 51324844h
0x14007d4c1  jnz     loc_14007DFFD
0x14007d4c7  cmp     [rbp+ullOperand], 20h ; ' '
0x14007d4cc  jz      short loc_14007D50E
0x14007d4ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d4d5  lea     rdi, WPP_GLOBAL_Control
0x14007d4dc  cmp     rcx, rdi
0x14007d4df  jz      short loc_14007D504
0x14007d4e1  test    dword ptr [rcx+2Ch], 100000h
0x14007d4e8  jz      short loc_14007D504
0x14007d4ea  cmp     byte ptr [rcx+29h], 1
0x14007d4ee  jb      short loc_14007D504
0x14007d4f0  mov     rcx, [rcx+18h]
0x14007d4f4  lea     edx, [r8+17h]
0x14007d4f8  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d4ff  call    WPP_SF_
0x14007d504  mov     edx, 0Fh
0x14007d509  jmp     loc_14007D946
0x14007d50e  xor     esi, esi
0x14007d510  cmp     [rbx+160h], sil
0x14007d517  jnz     loc_14007D5E0
0x14007d51d  cmp     [rbx+168h], sil
0x14007d524  jnz     loc_14007D5E0
0x14007d52a  cmp     [rbx+17Ah], sil
0x14007d531  jnz     loc_14007D5E0
0x14007d537  mov     byte ptr [rbx+179h], 1
0x14007d53e  test    byte ptr [r12+31h], 4
0x14007d544  jz      short loc_14007D59E
0x14007d546  test    byte ptr [r9+4], 2
0x14007d54b  jz      short loc_14007D59E
0x14007d54d  mov     rcx, [rbx+38h]
0x14007d551  test    dword ptr [rcx+50h], 4000h
0x14007d558  jz      short loc_14007D59E
0x14007d55a  cmp     [rcx+4Ch], esi
0x14007d55d  jnz     short loc_14007D59E
0x14007d55f  mov     byte ptr [rbx+17Bh], 1
0x14007d566  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d56d  lea     rdi, WPP_GLOBAL_Control
0x14007d574  cmp     rcx, rdi
0x14007d577  jz      short loc_14007D59E
0x14007d579  test    dword ptr [rcx+2Ch], 200000h
0x14007d580  jz      short loc_14007D59E
0x14007d582  cmp     byte ptr [rcx+29h], 2
0x14007d586  jb      short loc_14007D59E
0x14007d588  mov     rcx, [rcx+18h]
0x14007d58c  lea     edx, [rsi+1Dh]
0x14007d58f  mov     r9, r13
0x14007d592  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d599  call    WPP_SF_q
0x14007d59e  mov     eax, [r14]
0x14007d5a1  test    eax, eax
0x14007d5a3  jnz     short loc_14007D5BE
0x14007d5a5  mov     rax, [rbx+38h]
0x14007d5a9  mov     rcx, [rax+60h]
0x14007d5ad  mov     edx, [rcx+12Ch]
0x14007d5b3  test    edx, edx
0x14007d5b5  cmovz   edx, cs:Smb2DurableHandleV2TimeoutInMs
0x14007d5bc  jmp     short loc_14007D5C8
0x14007d5be  mov     edx, 493E0h
0x14007d5c3  cmp     eax, edx
0x14007d5c5  cmovb   edx, eax
0x14007d5c8  mov     [rbx+164h], edx
0x14007d5ce  movups  xmm0, xmmword ptr [r14+10h]
0x14007d5d3  movdqu  xmmword ptr [rbx+150h], xmm0
0x14007d5db  jmp     loc_14007DFFD
0x14007d5e0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d5e7  lea     rdi, WPP_GLOBAL_Control
0x14007d5ee  cmp     rcx, rdi
0x14007d5f1  jz      short loc_14007D617
0x14007d5f3  test    dword ptr [rcx+2Ch], 100000h
0x14007d5fa  jz      short loc_14007D617
0x14007d5fc  cmp     byte ptr [rcx+29h], 1
0x14007d600  jb      short loc_14007D617
0x14007d602  mov     rcx, [rcx+18h]
0x14007d606  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d60d  mov     edx, 1Ch
0x14007d612  call    WPP_SF_
0x14007d617  mov     edx, 10h
0x14007d61c  jmp     loc_14007D946
0x14007d621  xor     esi, esi
0x14007d623  mov     [rbp+pulResult], esi
0x14007d626  cmp     [rbx+0E0h], rsi
0x14007d62d  jz      short loc_14007D66E
0x14007d62f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d636  lea     rdi, WPP_GLOBAL_Control
0x14007d63d  cmp     rcx, rdi
0x14007d640  jz      short loc_14007D664
0x14007d642  test    dword ptr [rcx+2Ch], 100000h
0x14007d649  jz      short loc_14007D664
0x14007d64b  cmp     byte ptr [rcx+29h], 1
0x14007d64f  jb      short loc_14007D664
0x14007d651  mov     rcx, [rcx+18h]
0x14007d655  lea     edx, [rsi+0Dh]
0x14007d658  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d65f  call    WPP_SF_
0x14007d664  mov     edx, 5
0x14007d669  jmp     loc_14007D946
0x14007d66e  mov     rcx, [rbp+ullOperand]; ullOperand
0x14007d672  lea     rdx, [rbp+pulResult]; pulResult
0x14007d676  call    RtlULongLongToULong
0x14007d67b  test    eax, eax
0x14007d67d  jns     short loc_14007D6B7
0x14007d67f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d686  lea     rdi, WPP_GLOBAL_Control
0x14007d68d  cmp     rcx, rdi
0x14007d690  jz      loc_14007D94E
0x14007d696  test    dword ptr [rcx+2Ch], 100000h
0x14007d69d  jz      loc_14007D94E
0x14007d6a3  cmp     byte ptr [rcx+29h], 1
0x14007d6a7  jb      loc_14007D94E
0x14007d6ad  mov     edx, 0Eh
0x14007d6b2  jmp     loc_14007D99F
0x14007d6b7  mov     edx, [rbp+pulResult]; SecurityDescriptorLength
0x14007d6ba  xor     r8d, r8d; RequiredInformation
0x14007d6bd  mov     rcx, r14; SecurityDescriptorInput
0x14007d6c0  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14007d6c7  nop     dword ptr [rax+rax+00h]
0x14007d6cc  test    al, al
0x14007d6ce  jnz     short loc_14007D708
0x14007d6d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d6d7  lea     rdi, WPP_GLOBAL_Control
0x14007d6de  cmp     rcx, rdi
0x14007d6e1  jz      loc_14007D94E
0x14007d6e7  test    dword ptr [rcx+2Ch], 100000h
0x14007d6ee  jz      loc_14007D94E
0x14007d6f4  cmp     byte ptr [rcx+29h], 1
0x14007d6f8  jb      loc_14007D94E
0x14007d6fe  mov     edx, 0Fh
0x14007d703  jmp     loc_14007D99F
0x14007d708  mov     [rbx+0E0h], r14
0x14007d70f  jmp     loc_14007DFFD
0x14007d714  mov     r15d, 10h
0x14007d71a  cmp     [rbp+ullOperand], r15
0x14007d71e  jz      short loc_14007D760
0x14007d720  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d727  lea     rdi, WPP_GLOBAL_Control
0x14007d72e  cmp     rcx, rdi
0x14007d731  jz      short loc_14007D756
0x14007d733  test    dword ptr [rcx+2Ch], 100000h
0x14007d73a  jz      short loc_14007D756
0x14007d73c  cmp     byte ptr [rcx+29h], 1
0x14007d740  jb      short loc_14007D756
0x14007d742  mov     rcx, [rcx+18h]
0x14007d746  lea     edx, [r15+3]
0x14007d74a  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d751  call    WPP_SF_
0x14007d756  mov     edx, 9
0x14007d75b  jmp     loc_14007D946
0x14007d760  xor     esi, esi
0x14007d762  cmp     [rbx+179h], sil
0x14007d769  jnz     short loc_14007D78C
0x14007d76b  cmp     [rbx+17Ah], sil
0x14007d772  jnz     short loc_14007D78C
0x14007d774  mov     byte ptr [rbx+168h], 1
0x14007d77b  movups  xmm0, xmmword ptr [r9]
0x14007d77f  movdqu  xmmword ptr [rbx+169h], xmm0
0x14007d787  jmp     loc_14007DFFD
0x14007d78c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d793  lea     rdi, WPP_GLOBAL_Control
0x14007d79a  cmp     rcx, rdi
0x14007d79d  jz      short loc_14007D7C3
0x14007d79f  test    dword ptr [rcx+2Ch], 100000h
0x14007d7a6  jz      short loc_14007D7C3
0x14007d7a8  cmp     byte ptr [rcx+29h], 1
0x14007d7ac  jb      short loc_14007D7C3
0x14007d7ae  mov     rcx, [rcx+18h]
0x14007d7b2  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d7b9  mov     edx, 14h
0x14007d7be  call    WPP_SF_
0x14007d7c3  mov     edx, 0Ah
0x14007d7c8  jmp     loc_14007D946
0x14007d7cd  cmp     [rbp+ullOperand], 24h ; '$'
0x14007d7d2  jz      short loc_14007D815
0x14007d7d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d7db  lea     rdi, WPP_GLOBAL_Control
0x14007d7e2  cmp     rcx, rdi
0x14007d7e5  jz      short loc_14007D80B
0x14007d7e7  test    dword ptr [rcx+2Ch], 100000h
0x14007d7ee  jz      short loc_14007D80B
0x14007d7f0  cmp     byte ptr [rcx+29h], 1
0x14007d7f4  jb      short loc_14007D80B
0x14007d7f6  mov     rcx, [rcx+18h]
0x14007d7fa  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d801  mov     edx, 1Eh
0x14007d806  call    WPP_SF_
0x14007d80b  mov     edx, 11h
0x14007d810  jmp     loc_14007D946
0x14007d815  xor     esi, esi
0x14007d817  cmp     [rbx+160h], sil
0x14007d81e  jnz     loc_14007D8C3
0x14007d824  cmp     [rbx+168h], sil
0x14007d82b  jnz     loc_14007D8C3
0x14007d831  cmp     [rbx+179h], sil
0x14007d838  jnz     loc_14007D8C3
0x14007d83e  mov     byte ptr [rbx+17Ah], 1
0x14007d845  test    byte ptr [r12+31h], 4
0x14007d84b  jz      short loc_14007D8A5
0x14007d84d  test    byte ptr [r9+20h], 2
0x14007d852  jz      short loc_14007D8A5
0x14007d854  mov     rcx, [rbx+38h]
0x14007d858  test    dword ptr [rcx+50h], 4000h
0x14007d85f  jz      short loc_14007D8A5
0x14007d861  cmp     [rcx+4Ch], esi
0x14007d864  jnz     short loc_14007D8A5
0x14007d866  mov     byte ptr [rbx+17Bh], 1
0x14007d86d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d874  lea     rdi, WPP_GLOBAL_Control
0x14007d87b  cmp     rcx, rdi
0x14007d87e  jz      short loc_14007D8A5
0x14007d880  test    dword ptr [rcx+2Ch], 200000h
0x14007d887  jz      short loc_14007D8A5
0x14007d889  cmp     byte ptr [rcx+29h], 2
0x14007d88d  jb      short loc_14007D8A5
0x14007d88f  mov     rcx, [rcx+18h]
0x14007d893  lea     edx, [rsi+20h]
0x14007d896  mov     r9, r13
0x14007d899  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d8a0  call    WPP_SF_q
0x14007d8a5  movups  xmm0, xmmword ptr [r14+10h]
0x14007d8aa  movdqu  xmmword ptr [rbx+150h], xmm0
0x14007d8b2  movups  xmm1, xmmword ptr [r14]
0x14007d8b6  movdqu  xmmword ptr [rbx+169h], xmm1
0x14007d8be  jmp     loc_14007DFFD
0x14007d8c3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d8ca  lea     rdi, WPP_GLOBAL_Control
0x14007d8d1  cmp     rcx, rdi
0x14007d8d4  jz      short loc_14007D8FA
0x14007d8d6  test    dword ptr [rcx+2Ch], 100000h
0x14007d8dd  jz      short loc_14007D8FA
0x14007d8df  cmp     byte ptr [rcx+29h], 1
0x14007d8e3  jb      short loc_14007D8FA
0x14007d8e5  mov     rcx, [rcx+18h]
0x14007d8e9  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d8f0  mov     edx, 1Fh
0x14007d8f5  call    WPP_SF_
0x14007d8fa  mov     edx, 12h
0x14007d8ff  jmp     short loc_14007D946
0x14007d901  xor     esi, esi
0x14007d903  cmp     [rbx+0D0h], rsi
0x14007d90a  jz      short loc_14007D958
0x14007d90c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d913  lea     rdi, WPP_GLOBAL_Control
0x14007d91a  cmp     rcx, rdi
0x14007d91d  jz      short loc_14007D941
0x14007d91f  test    dword ptr [rcx+2Ch], 100000h
0x14007d926  jz      short loc_14007D941
0x14007d928  cmp     byte ptr [rcx+29h], 1
0x14007d92c  jb      short loc_14007D941
0x14007d92e  mov     rcx, [rcx+18h]
0x14007d932  lea     edx, [rsi+0Ah]
0x14007d935  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d93c  call    WPP_SF_
0x14007d941  mov     edx, 4
0x14007d946  mov     rcx, rbx
0x14007d949  call    Smb2LkmdTelCollectParsingFailureCreateHelper
0x14007d94e  mov     eax, 0C000000Dh
0x14007d953  jmp     loc_14007DFFF
0x14007d958  mov     rcx, [rbp+ullOperand]; ullOperand
0x14007d95c  test    rcx, rcx
0x14007d95f  jz      loc_14007DFFD
0x14007d965  lea     rdx, [rbp+pulResult]; pulResult
0x14007d969  mov     [rbp+pulResult], esi
0x14007d96c  mov     [rbp+ErrorOffset], esi
0x14007d96f  call    RtlULongLongToULong
0x14007d974  test    eax, eax
0x14007d976  jns     short loc_14007D9B1
0x14007d978  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
