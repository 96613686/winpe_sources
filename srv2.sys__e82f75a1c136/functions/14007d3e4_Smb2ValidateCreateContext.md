# Smb2ValidateCreateContext

- ea: `0x14007d3e4`
- end: `0x14007e26d`
- name: `Smb2ValidateCreateContext`
- size: `3721`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007d060`

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
- `0x14007d3e4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14007de32`
- `ntoskrnl!RtlCompareMemory` at `0x14007de32`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007e21d`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007e21d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007e202`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007e202`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007e069`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007e069`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007e151`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007e151`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14007d96d`
- `ntoskrnl!IoCheckEaBufferValidity` at `0x14007d96d`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007d670`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14007d670`

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
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
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
0x14007d3e4  mov     [rsp-38h+arg_10], rbx
0x14007d3e9  push    rbp
0x14007d3ea  push    rsi
0x14007d3eb  push    rdi
0x14007d3ec  push    r12
0x14007d3ee  push    r13
0x14007d3f0  push    r14
0x14007d3f2  push    r15
0x14007d3f4  mov     rbp, rsp
0x14007d3f7  sub     rsp, 60h
0x14007d3fb  mov     rax, cs:__security_cookie
0x14007d402  xor     rax, rsp
0x14007d405  mov     [rbp+var_10], rax
0x14007d409  mov     rax, [rcx+60h]
0x14007d40d  mov     r14, r9
0x14007d410  mov     rbx, [rcx+230h]
0x14007d417  mov     r13, rcx
0x14007d41a  mov     r12, [rax+1F0h]
0x14007d421  cmp     r8, 4
0x14007d425  jnz     loc_14007DE0D
0x14007d42b  mov     eax, [rdx]
0x14007d42d  mov     ecx, 516E4844h
0x14007d432  cmp     eax, ecx
0x14007d434  ja      loc_14007DA7E
0x14007d43a  jz      loc_14007D9D1
0x14007d440  cmp     eax, 41747845h
0x14007d445  jz      loc_14007D8B1
0x14007d44b  cmp     eax, 43324844h
0x14007d450  jz      loc_14007D77D
0x14007d456  cmp     eax, 436E4844h
0x14007d45b  jz      loc_14007D6C4
0x14007d461  cmp     eax, 44636553h
0x14007d466  jz      loc_14007D5D1
0x14007d46c  cmp     eax, 51324844h
0x14007d471  jnz     loc_14007DFAD
0x14007d477  cmp     [rbp+ullOperand], 20h ; ' '
0x14007d47c  jz      short loc_14007D4BE
0x14007d47e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d485  lea     rdi, WPP_GLOBAL_Control
0x14007d48c  cmp     rcx, rdi
0x14007d48f  jz      short loc_14007D4B4
0x14007d491  test    dword ptr [rcx+2Ch], 100000h
0x14007d498  jz      short loc_14007D4B4
0x14007d49a  cmp     byte ptr [rcx+29h], 1
0x14007d49e  jb      short loc_14007D4B4
0x14007d4a0  mov     rcx, [rcx+18h]
0x14007d4a4  lea     edx, [r8+17h]
0x14007d4a8  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d4af  call    WPP_SF_
0x14007d4b4  mov     edx, 0Fh
0x14007d4b9  jmp     loc_14007D8F6
0x14007d4be  xor     esi, esi
0x14007d4c0  cmp     [rbx+160h], sil
0x14007d4c7  jnz     loc_14007D590
0x14007d4cd  cmp     [rbx+168h], sil
0x14007d4d4  jnz     loc_14007D590
0x14007d4da  cmp     [rbx+17Ah], sil
0x14007d4e1  jnz     loc_14007D590
0x14007d4e7  mov     byte ptr [rbx+179h], 1
0x14007d4ee  test    byte ptr [r12+31h], 4
0x14007d4f4  jz      short loc_14007D54E
0x14007d4f6  test    byte ptr [r9+4], 2
0x14007d4fb  jz      short loc_14007D54E
0x14007d4fd  mov     rcx, [rbx+38h]
0x14007d501  test    dword ptr [rcx+50h], 4000h
0x14007d508  jz      short loc_14007D54E
0x14007d50a  cmp     [rcx+4Ch], esi
0x14007d50d  jnz     short loc_14007D54E
0x14007d50f  mov     byte ptr [rbx+17Bh], 1
0x14007d516  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d51d  lea     rdi, WPP_GLOBAL_Control
0x14007d524  cmp     rcx, rdi
0x14007d527  jz      short loc_14007D54E
0x14007d529  test    dword ptr [rcx+2Ch], 200000h
0x14007d530  jz      short loc_14007D54E
0x14007d532  cmp     byte ptr [rcx+29h], 2
0x14007d536  jb      short loc_14007D54E
0x14007d538  mov     rcx, [rcx+18h]
0x14007d53c  lea     edx, [rsi+1Dh]
0x14007d53f  mov     r9, r13
0x14007d542  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d549  call    WPP_SF_q
0x14007d54e  mov     eax, [r14]
0x14007d551  test    eax, eax
0x14007d553  jnz     short loc_14007D56E
0x14007d555  mov     rax, [rbx+38h]
0x14007d559  mov     rcx, [rax+60h]
0x14007d55d  mov     edx, [rcx+12Ch]
0x14007d563  test    edx, edx
0x14007d565  cmovz   edx, cs:Smb2DurableHandleV2TimeoutInMs
0x14007d56c  jmp     short loc_14007D578
0x14007d56e  mov     edx, 493E0h
0x14007d573  cmp     eax, edx
0x14007d575  cmovb   edx, eax
0x14007d578  mov     [rbx+164h], edx
0x14007d57e  movups  xmm0, xmmword ptr [r14+10h]
0x14007d583  movdqu  xmmword ptr [rbx+150h], xmm0
0x14007d58b  jmp     loc_14007DFAD
0x14007d590  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d597  lea     rdi, WPP_GLOBAL_Control
0x14007d59e  cmp     rcx, rdi
0x14007d5a1  jz      short loc_14007D5C7
0x14007d5a3  test    dword ptr [rcx+2Ch], 100000h
0x14007d5aa  jz      short loc_14007D5C7
0x14007d5ac  cmp     byte ptr [rcx+29h], 1
0x14007d5b0  jb      short loc_14007D5C7
0x14007d5b2  mov     rcx, [rcx+18h]
0x14007d5b6  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d5bd  mov     edx, 1Ch
0x14007d5c2  call    WPP_SF_
0x14007d5c7  mov     edx, 10h
0x14007d5cc  jmp     loc_14007D8F6
0x14007d5d1  xor     esi, esi
0x14007d5d3  mov     [rbp+pulResult], esi
0x14007d5d6  cmp     [rbx+0E0h], rsi
0x14007d5dd  jz      short loc_14007D61E
0x14007d5df  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d5e6  lea     rdi, WPP_GLOBAL_Control
0x14007d5ed  cmp     rcx, rdi
0x14007d5f0  jz      short loc_14007D614
0x14007d5f2  test    dword ptr [rcx+2Ch], 100000h
0x14007d5f9  jz      short loc_14007D614
0x14007d5fb  cmp     byte ptr [rcx+29h], 1
0x14007d5ff  jb      short loc_14007D614
0x14007d601  mov     rcx, [rcx+18h]
0x14007d605  lea     edx, [rsi+0Dh]
0x14007d608  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d60f  call    WPP_SF_
0x14007d614  mov     edx, 5
0x14007d619  jmp     loc_14007D8F6
0x14007d61e  mov     rcx, [rbp+ullOperand]; ullOperand
0x14007d622  lea     rdx, [rbp+pulResult]; pulResult
0x14007d626  call    RtlULongLongToULong
0x14007d62b  test    eax, eax
0x14007d62d  jns     short loc_14007D667
0x14007d62f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d636  lea     rdi, WPP_GLOBAL_Control
0x14007d63d  cmp     rcx, rdi
0x14007d640  jz      loc_14007D8FE
0x14007d646  test    dword ptr [rcx+2Ch], 100000h
0x14007d64d  jz      loc_14007D8FE
0x14007d653  cmp     byte ptr [rcx+29h], 1
0x14007d657  jb      loc_14007D8FE
0x14007d65d  mov     edx, 0Eh
0x14007d662  jmp     loc_14007D94F
0x14007d667  mov     edx, [rbp+pulResult]; SecurityDescriptorLength
0x14007d66a  xor     r8d, r8d; RequiredInformation
0x14007d66d  mov     rcx, r14; SecurityDescriptorInput
0x14007d670  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x14007d677  nop     dword ptr [rax+rax+00h]
0x14007d67c  test    al, al
0x14007d67e  jnz     short loc_14007D6B8
0x14007d680  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d687  lea     rdi, WPP_GLOBAL_Control
0x14007d68e  cmp     rcx, rdi
0x14007d691  jz      loc_14007D8FE
0x14007d697  test    dword ptr [rcx+2Ch], 100000h
0x14007d69e  jz      loc_14007D8FE
0x14007d6a4  cmp     byte ptr [rcx+29h], 1
0x14007d6a8  jb      loc_14007D8FE
0x14007d6ae  mov     edx, 0Fh
0x14007d6b3  jmp     loc_14007D94F
0x14007d6b8  mov     [rbx+0E0h], r14
0x14007d6bf  jmp     loc_14007DFAD
0x14007d6c4  mov     r15d, 10h
0x14007d6ca  cmp     [rbp+ullOperand], r15
0x14007d6ce  jz      short loc_14007D710
0x14007d6d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d6d7  lea     rdi, WPP_GLOBAL_Control
0x14007d6de  cmp     rcx, rdi
0x14007d6e1  jz      short loc_14007D706
0x14007d6e3  test    dword ptr [rcx+2Ch], 100000h
0x14007d6ea  jz      short loc_14007D706
0x14007d6ec  cmp     byte ptr [rcx+29h], 1
0x14007d6f0  jb      short loc_14007D706
0x14007d6f2  mov     rcx, [rcx+18h]
0x14007d6f6  lea     edx, [r15+3]
0x14007d6fa  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d701  call    WPP_SF_
0x14007d706  mov     edx, 9
0x14007d70b  jmp     loc_14007D8F6
0x14007d710  xor     esi, esi
0x14007d712  cmp     [rbx+179h], sil
0x14007d719  jnz     short loc_14007D73C
0x14007d71b  cmp     [rbx+17Ah], sil
0x14007d722  jnz     short loc_14007D73C
0x14007d724  mov     byte ptr [rbx+168h], 1
0x14007d72b  movups  xmm0, xmmword ptr [r9]
0x14007d72f  movdqu  xmmword ptr [rbx+169h], xmm0
0x14007d737  jmp     loc_14007DFAD
0x14007d73c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d743  lea     rdi, WPP_GLOBAL_Control
0x14007d74a  cmp     rcx, rdi
0x14007d74d  jz      short loc_14007D773
0x14007d74f  test    dword ptr [rcx+2Ch], 100000h
0x14007d756  jz      short loc_14007D773
0x14007d758  cmp     byte ptr [rcx+29h], 1
0x14007d75c  jb      short loc_14007D773
0x14007d75e  mov     rcx, [rcx+18h]
0x14007d762  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d769  mov     edx, 14h
0x14007d76e  call    WPP_SF_
0x14007d773  mov     edx, 0Ah
0x14007d778  jmp     loc_14007D8F6
0x14007d77d  cmp     [rbp+ullOperand], 24h ; '$'
0x14007d782  jz      short loc_14007D7C5
0x14007d784  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d78b  lea     rdi, WPP_GLOBAL_Control
0x14007d792  cmp     rcx, rdi
0x14007d795  jz      short loc_14007D7BB
0x14007d797  test    dword ptr [rcx+2Ch], 100000h
0x14007d79e  jz      short loc_14007D7BB
0x14007d7a0  cmp     byte ptr [rcx+29h], 1
0x14007d7a4  jb      short loc_14007D7BB
0x14007d7a6  mov     rcx, [rcx+18h]
0x14007d7aa  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d7b1  mov     edx, 1Eh
0x14007d7b6  call    WPP_SF_
0x14007d7bb  mov     edx, 11h
0x14007d7c0  jmp     loc_14007D8F6
0x14007d7c5  xor     esi, esi
0x14007d7c7  cmp     [rbx+160h], sil
0x14007d7ce  jnz     loc_14007D873
0x14007d7d4  cmp     [rbx+168h], sil
0x14007d7db  jnz     loc_14007D873
0x14007d7e1  cmp     [rbx+179h], sil
0x14007d7e8  jnz     loc_14007D873
0x14007d7ee  mov     byte ptr [rbx+17Ah], 1
0x14007d7f5  test    byte ptr [r12+31h], 4
0x14007d7fb  jz      short loc_14007D855
0x14007d7fd  test    byte ptr [r9+20h], 2
0x14007d802  jz      short loc_14007D855
0x14007d804  mov     rcx, [rbx+38h]
0x14007d808  test    dword ptr [rcx+50h], 4000h
0x14007d80f  jz      short loc_14007D855
0x14007d811  cmp     [rcx+4Ch], esi
0x14007d814  jnz     short loc_14007D855
0x14007d816  mov     byte ptr [rbx+17Bh], 1
0x14007d81d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d824  lea     rdi, WPP_GLOBAL_Control
0x14007d82b  cmp     rcx, rdi
0x14007d82e  jz      short loc_14007D855
0x14007d830  test    dword ptr [rcx+2Ch], 200000h
0x14007d837  jz      short loc_14007D855
0x14007d839  cmp     byte ptr [rcx+29h], 2
0x14007d83d  jb      short loc_14007D855
0x14007d83f  mov     rcx, [rcx+18h]
0x14007d843  lea     edx, [rsi+20h]
0x14007d846  mov     r9, r13
0x14007d849  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d850  call    WPP_SF_q
0x14007d855  movups  xmm0, xmmword ptr [r14+10h]
0x14007d85a  movdqu  xmmword ptr [rbx+150h], xmm0
0x14007d862  movups  xmm1, xmmword ptr [r14]
0x14007d866  movdqu  xmmword ptr [rbx+169h], xmm1
0x14007d86e  jmp     loc_14007DFAD
0x14007d873  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d87a  lea     rdi, WPP_GLOBAL_Control
0x14007d881  cmp     rcx, rdi
0x14007d884  jz      short loc_14007D8AA
0x14007d886  test    dword ptr [rcx+2Ch], 100000h
0x14007d88d  jz      short loc_14007D8AA
0x14007d88f  cmp     byte ptr [rcx+29h], 1
0x14007d893  jb      short loc_14007D8AA
0x14007d895  mov     rcx, [rcx+18h]
0x14007d899  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d8a0  mov     edx, 1Fh
0x14007d8a5  call    WPP_SF_
0x14007d8aa  mov     edx, 12h
0x14007d8af  jmp     short loc_14007D8F6
0x14007d8b1  xor     esi, esi
0x14007d8b3  cmp     [rbx+0D0h], rsi
0x14007d8ba  jz      short loc_14007D908
0x14007d8bc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007d8c3  lea     rdi, WPP_GLOBAL_Control
0x14007d8ca  cmp     rcx, rdi
0x14007d8cd  jz      short loc_14007D8F1
0x14007d8cf  test    dword ptr [rcx+2Ch], 100000h
0x14007d8d6  jz      short loc_14007D8F1
0x14007d8d8  cmp     byte ptr [rcx+29h], 1
0x14007d8dc  jb      short loc_14007D8F1
0x14007d8de  mov     rcx, [rcx+18h]
0x14007d8e2  lea     edx, [rsi+0Ah]
0x14007d8e5  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14007d8ec  call    WPP_SF_
0x14007d8f1  mov     edx, 4
0x14007d8f6  mov     rcx, rbx
0x14007d8f9  call    Smb2LkmdTelCollectParsingFailureCreateHelper
0x14007d8fe  mov     eax, 0C000000Dh
0x14007d903  jmp     loc_14007DFAF
0x14007d908  mov     rcx, [rbp+ullOperand]; ullOperand
0x14007d90c  test    rcx, rcx
0x14007d90f  jz      loc_14007DFAD
0x14007d915  lea     rdx, [rbp+pulResult]; pulResult
0x14007d919  mov     [rbp+pulResult], esi
0x14007d91c  mov     [rbp+ErrorOffset], esi
0x14007d91f  call    RtlULongLongToULong
0x14007d924  test    eax, eax
0x14007d926  jns     short loc_14007D961
0x14007d928  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
