# SrvNetCommonReceiveHandler

- ea: `0x140002a10`
- end: `0x1400035bb`
- name: `SrvNetCommonReceiveHandler`
- size: `2987`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002650`
- `0x1400027a0`
- `0x140018de0`
- `0x14001a4b0`

## callees

- `0x140001b18`
- `0x140001bcc`
- `0x140002a10`
- `0x140003628`
- `0x140014948`
- `0x140015790`
- `0x140016c84`
- `0x140016cc8`
- `0x140018728`
- `0x14001b560`
- `0x14001b5e0`
- `0x14002a3e0`
- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!EtwProviderEnabled` at `0x140002ad0`
- `ntoskrnl!EtwProviderEnabled` at `0x140002afe`
- `ntoskrnl!EtwProviderEnabled` at `0x140002ad0`
- `ntoskrnl!EtwProviderEnabled` at `0x140002afe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000305f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000342e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000305f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000342e`
- `ntoskrnl!EtwWriteTransfer` at `0x1400031ff`
- `ntoskrnl!EtwWriteTransfer` at `0x140003511`
- `ntoskrnl!EtwWriteTransfer` at `0x1400031ff`
- `ntoskrnl!EtwWriteTransfer` at `0x140003511`
- `ntoskrnl!IoGetActivityIdThread` at `0x140002b32`
- `ntoskrnl!IoGetActivityIdThread` at `0x140002b32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000301b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000301b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400033e9`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400033e9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e31`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002f2c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002fa3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003216`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002e31`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002f2c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002fa3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003216`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d1d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002e60`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d1d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002e60`

## pseudocode

```c
__int64 __fastcall SrvNetCommonReceiveHandler(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r12
  unsigned int v10; // esi
  unsigned int v11; // r15d
  __int64 v12; // rdi
  unsigned int v13; // r14d
  unsigned int v14; // ebx
  __int64 v15; // rdx
  EVENT_DESCRIPTOR *ActivityIdThread; // r15
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // r14
  __int64 v20; // rdx
  int v21; // ecx
  unsigned int v22; // esi
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // ebx
  int v26; // r12d
  __int64 v27; // r14
  unsigned __int16 v28; // si
  __int64 v29; // r15
  __int64 v30; // rbx
  int v31; // eax
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  bool v35; // zf
  __int64 v36; // rax
  __int64 v37; // r14
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r8
  KSPIN_LOCK *v42; // rcx
  char v43; // bl
  int v44; // eax
  __int64 *v45; // rcx
  __int64 *v46; // rax
  __int64 **v47; // rdx
  __int64 v48; // rax
  __int64 **v49; // rdx
  _BYTE *v50; // rax
  __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  KIRQL v53; // si
  __int64 v54; // rbx
  PDEVICE_OBJECT v55; // rcx
  _QWORD *v56; // rsi
  int v57; // ebx
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  unsigned int v61; // eax
  PDEVICE_OBJECT v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-C9h]
  __int64 v67; // [rsp+30h] [rbp-C1h]
  __int64 v68; // [rsp+38h] [rbp-B9h]
  unsigned int v69; // [rsp+50h] [rbp-A1h]
  __int128 v71; // [rsp+58h] [rbp-99h] BYREF
  __int64 v72; // [rsp+68h] [rbp-89h]
  int v73; // [rsp+70h] [rbp-81h] BYREF
  int v74; // [rsp+74h] [rbp-7Dh] BYREF
  __int64 v75; // [rsp+78h] [rbp-79h]
  __int64 v76; // [rsp+80h] [rbp-71h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-69h] BYREF
  PVOID v78; // [rsp+A0h] [rbp-51h] BYREF
  __m256i v79; // [rsp+A8h] [rbp-49h]
  __int64 v80; // [rsp+C8h] [rbp-29h]
  int *v81; // [rsp+D0h] [rbp-21h]
  __int64 v82; // [rsp+D8h] [rbp-19h]

  v7 = a6;
  v8 = a3;
  v9 = a7;
  v10 = a4;
  v11 = a2;
  v75 = a3;
  v12 = a1;
  v72 = a6;
  v76 = a7;
  v69 = a2;
  *(_QWORD *)&v71 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, a5);
  }
  EventDescriptor = 0;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x4000000) == 0 )
    goto LABEL_26;
  v13 = *(unsigned __int16 *)(v12 + 480);
  if ( !EtwProviderEnabled(PROV_SRV2_Context, 0, 0x200000000uLL) )
    goto LABEL_25;
  v14 = v11;
  if ( !EtwProviderEnabled(PROV_SRV2_Context, 0, 0x800000000000uLL) && v11 >= 0x40 && *(_DWORD *)a5 == 1112364030 )
  {
    v14 = *(_DWORD *)(a5 + 20) + 576;
    if ( v14 > v11 )
      v14 = v11;
  }
  ActivityIdThread = (EVENT_DESCRIPTOR *)IoGetActivityIdThread();
  if ( !ActivityIdThread )
  {
    EventDescriptor.Keyword = 0;
    ActivityIdThread = &EventDescriptor;
    *(_QWORD *)&EventDescriptor.Id = _InterlockedIncrement64(&Correlation);
  }
  if ( v14 < 0xF000 )
  {
    LODWORD(UserData) = 28;
    Template_qqbqb_ex(PROV_SRV2_Context, v15, 0x200000000LL, ActivityIdThread, v13, UserData, v12 + 128, v14, a5);
    goto LABEL_24;
  }
  v17 = *(_OWORD *)(v12 + 128);
  v78 = (PVOID)(v13 | 0x1C00000000LL);
  v18 = *(_OWORD *)(v12 + 140);
  *(_OWORD *)v79.m256i_i8 = v17;
  v19 = a5;
  v79.m256i_i32[7] = v14;
  *(_OWORD *)((char *)&v79.m256i_u64[1] + 4) = v18;
  v21 = Template_qqbjqb_ex(PROV_SRV2_Context, v15, 0x240000000LL, ActivityIdThread, 40, &v78);
  while ( v21 >= 0 )
  {
    if ( v14 < 0xF000 )
    {
      v22 = v14;
LABEL_21:
      v23 = 0x280000000LL;
      goto LABEL_22;
    }
    v23 = 0x200000000LL;
    v22 = 61440;
    if ( v14 == 61440 )
      goto LABEL_21;
LABEL_22:
    v21 = Template_qqbjqb_ex(PROV_SRV2_Context, v20, v23, ActivityIdThread, v22, v19);
    v19 += v22;
    v14 -= v22;
    if ( !v14 )
      break;
  }
  v12 = v71;
  v9 = v76;
LABEL_24:
  v10 = a4;
  v8 = v75;
  v11 = v69;
LABEL_25:
  v7 = v72;
LABEL_26:
  v24 = *(_DWORD *)(v12 + 484);
  if ( v24 == 3 )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)(v12 + 440) + 8LL))(
            *(_QWORD *)(v12 + 456),
            *(_QWORD *)(v12 + 464),
            v10,
            v11,
            v8,
            a5,
            v7,
            v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
        *(_QWORD *)(v12 + 464),
        v25);
    }
    return v25;
  }
  if ( v24 == 2 )
  {
    v26 = -1073741285;
    v27 = *(_QWORD *)(v12 + 448);
    *(_QWORD *)&v71 = v27;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
    v28 = 0;
    v29 = *(_QWORD *)(*(_QWORD *)(v12 + 448) + 368LL);
    while ( 1 )
    {
      v30 = *(&SrvNetDeviceExtension[4].OwnerEntry.OwnerThread + v28);
      if ( !v30 || !*(_BYTE *)(v30 + 237) )
        goto LABEL_53;
      if ( v29 )
      {
        if ( *(_BYTE *)(v30 + 225) > 5u )
          __int2c();
        v31 = *(_DWORD *)(v29 + 4);
        if ( !_bittest(&v31, *(unsigned __int8 *)(v30 + 225)) )
          goto LABEL_53;
      }
      v32 = *(_DWORD *)(v12 + 480);
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            if ( v34 != 2 )
              goto LABEL_53;
            v35 = (*(_BYTE *)(v30 + 224) & 8) == 0;
          }
          else
          {
            v35 = (*(_BYTE *)(v30 + 224) & 4) == 0;
          }
        }
        else
        {
          v35 = (*(_BYTE *)(v30 + 224) & 2) == 0;
        }
      }
      else
      {
        v35 = (*(_BYTE *)(v30 + 224) & 1) == 0;
      }
      if ( !v35 )
      {
        v36 = *(unsigned int *)(v30 + 232);
        if ( *(_BYTE *)(v36 + v27 + 432) )
        {
          v37 = *(_QWORD *)(v27 + 8 * v36 + 376);
          v38 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v30 + 176))(v37, v69, a5);
          v26 = v38;
          if ( v38 >= 0 )
          {
            *(_QWORD *)(v12 + 456) = v37;
            *(_QWORD *)(v12 + 440) = v30 + 184;
            *(_BYTE *)(v12 + 492) = *(_BYTE *)(v30 + 225);
            v55 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qdq(
                WPP_GLOBAL_Control->AttachedDevice,
                12,
                WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
                v30,
                *(_DWORD *)(v30 + 232),
                v12);
            }
            if ( (*(_BYTE *)(v30 + 224) & 4) == 0 && SrvNetAuditSmb1Access )
            {
              if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x10000000) != 0 )
                McTemplateK0s_EtwWriteTransfer(v55, SRVNET_EVENT_SMB1_ACCESS_AUDIT, v40, v12 + 4);
              if ( (unsigned int)dword_140036120 > 5
                && (qword_140036130 & 0x400000000000LL) != 0
                && (qword_140036138 & 0x400000000000LL) == qword_140036138 )
              {
                EventDescriptor.Keyword = 0x400000000000LL;
                v79.m256i_i64[3] = (__int64)&v73;
                v74 = *(_DWORD *)(v12 + 480);
                v73 = 1;
                v81 = &v74;
                *(_DWORD *)&EventDescriptor.Level = 5;
                v78 = EventInformation;
                v80 = 4;
                v82 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                v79.m256i_i64[0] = *(unsigned __int16 *)EventInformation | 0x200000000LL;
                v79.m256i_i64[1] = (__int64)&dword_140031A5C;
                v79.m256i_i64[2] = 0x10000003CLL;
                LODWORD(v71) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, (PEVENT_DATA_DESCRIPTOR)&v78);
              }
            }
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
            goto LABEL_55;
          }
          if ( v38 == -1073741637 && (*(_BYTE *)(v30 + 224) & 4) == 0 )
          {
            if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 0x20) != 0 )
            {
              McTemplateK0s_EtwWriteTransfer(v39, SRVNET_EVENT_SMB1_CONNECTION_REJECTED, v40, v12 + 4);
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
              goto LABEL_72;
            }
LABEL_54:
            KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
            if ( v26 < 0 )
            {
LABEL_72:
              if ( v69 >= 0x24 && *(_DWORD *)a5 == 1112364031 && *(_BYTE *)(a5 + 4) == 114 )
              {
                v52 = a5 + *(unsigned __int16 *)(a5 + 33) + 35LL;
                if ( v52 <= (unsigned __int64)v69 + a5 )
                {
                  if ( SrvNetAuditSmb1Access && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
                    McTemplateK0s_EtwWriteTransfer(v52, AUDIT_SMB1_ACCESS, v41, v12 + 4);
                  v53 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&SrvNetDeviceExtension[1]);
                  v54 = MEMORY[0xFFFFF78000000320];
                  if ( SrvNetSmb1DisabledOrUninstalledEventLastWrittenTickCount
                    && (MEMORY[0xFFFFF78000000320] < SrvNetSmb1DisabledOrUninstalledEventLastWrittenTickCount
                     || KeQueryTimeIncrement() * (v54 - SrvNetSmb1DisabledOrUninstalledEventLastWrittenTickCount) < 864000000000LL) )
                  {
                    KeReleaseSpinLock((PKSPIN_LOCK)&SrvNetDeviceExtension[1], v53);
                  }
                  else
                  {
                    SrvNetSmb1DisabledOrUninstalledEventLastWrittenTickCount = v54;
                    KeReleaseSpinLock((PKSPIN_LOCK)&SrvNetDeviceExtension[1], v53);
                    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
                      McTemplateK0_EtwWriteTransfer(v64, SRVNET_EVENT_SMB1_DISABLED_OR_NOT_INSTALLED, 0);
                    if ( (unsigned int)dword_140036120 > 5
                      && (qword_140036130 & 0x400000000000LL) != 0
                      && (qword_140036138 & 0x400000000000LL) == qword_140036138 )
                    {
                      *(_DWORD *)&EventDescriptor.Level = 5;
                      v78 = EventInformation;
                      EventDescriptor.Keyword = 0x400000000000LL;
                      *(_DWORD *)&EventDescriptor.Id = 184549376;
                      v79.m256i_i64[0] = *(unsigned __int16 *)EventInformation | 0x200000000LL;
                      v79.m256i_i64[1] = (__int64)&dword_140031AA4;
                      v79.m256i_i64[2] = 0x100000015LL;
                      LODWORD(v71) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)&v78);
                    }
                  }
                }
              }
              *(_BYTE *)(v12 + 613) = 1;
              v62 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                v63 = 18;
LABEL_121:
                WPP_SF_q(v62->AttachedDevice, v63, WPP_9a5897045a5730f713eba007d66b1edc_Traceguids, v12);
              }
            }
            else
            {
LABEL_55:
              v42 = (KSPIN_LOCK *)(*(_QWORD *)(v12 + 448) + 24LL);
              v71 = 0;
              KeAcquireSpinLockAtDpcLevel(v42);
              v43 = *(_BYTE *)(*(_QWORD *)(v12 + 448) + 145LL);
              if ( v29 )
              {
                v44 = *(_DWORD *)(v29 + 4);
                if ( !_bittest(&v44, *(unsigned __int8 *)(v12 + 492)) )
                {
                  v26 = -1073741285;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      13,
                      WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
                      *(_QWORD *)(v12 + 464),
                      -1073741285);
                  }
                }
              }
              v45 = (__int64 *)(v12 + 512);
              v46 = *(__int64 **)(v12 + 512);
              if ( v46[1] != v12 + 512
                || (v47 = *(__int64 ***)(v12 + 520), *v47 != v45)
                || (*v47 = v46,
                    v46[1] = (__int64)v47,
                    v48 = *(_QWORD *)(v12 + 448) + 224LL,
                    v49 = *(__int64 ***)(*(_QWORD *)(v12 + 448) + 232LL),
                    *v49 != (__int64 *)v48) )
              {
                __fastfail(3u);
              }
              *v45 = v48;
              *(_QWORD *)(v12 + 520) = v49;
              *v49 = v45;
              *(_QWORD *)(v48 + 8) = v45;
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(*(_QWORD *)(v12 + 448) + 24LL));
              v50 = (_BYTE *)(v12 + 4);
              *((_QWORD *)&v71 + 1) = v12 + 4;
              if ( v12 == -4 )
                goto LABEL_95;
              v51 = 65;
              do
              {
                if ( !*v50 )
                  break;
                ++v50;
                --v51;
              }
              while ( v51 );
              if ( !v51 )
LABEL_95:
                LOWORD(v71) = 0;
              else
                LOWORD(v71) = 65 - v51;
              if ( v26 >= 0 )
              {
                v56 = (_QWORD *)(v12 + 464);
                if ( v43 )
                  v57 = -1073741258;
                else
                  v57 = (**(__int64 (__fastcall ***)(_QWORD, __int64, __int128 *, __int64))(v12 + 440))(
                          *(_QWORD *)(v12 + 456),
                          v12,
                          &v71,
                          v12 + 464);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    14,
                    WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
                    *(_QWORD *)(v12 + 456),
                    v57);
                }
                if ( v57 >= 0 )
                {
                  v58 = *(_QWORD *)(v12 + 440);
                  v59 = *v56;
                  v68 = v76;
                  v67 = v72;
                  v60 = v75;
                  *(_DWORD *)(v12 + 484) = 3;
                  v61 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(v58 + 8))(
                          *(_QWORD *)(v12 + 456),
                          v59,
                          a4,
                          v69,
                          v60,
                          a5,
                          v67,
                          v68);
                  v25 = v61;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
                      *v56,
                      v61);
                  }
                  if ( (int)(v25 + 0x80000000) >= 0 && v25 != -1073741807 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_qD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        16,
                        WPP_9a5897045a5730f713eba007d66b1edc_Traceguids,
                        *v56,
                        v25);
                    }
                    if ( v25 != -1073741802 )
                      return (unsigned int)-1073741285;
                  }
                  return v25;
                }
              }
              *(_BYTE *)(v12 + 613) = 1;
              v62 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                v63 = 17;
                goto LABEL_121;
              }
            }
            SrvNetCloseConnectionWithLock(v12);
            return (unsigned int)-1073741285;
          }
          v27 = v71;
        }
      }
LABEL_53:
      if ( ++v28 >= 7u )
        goto LABEL_54;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_9a5897045a5730f713eba007d66b1edc_Traceguids);
  }
  return (unsigned int)-1073741285;
}

```

## disassembly

```asm
0x140002a10  push    rbp
0x140002a12  push    rbx
0x140002a13  push    rsi
0x140002a14  push    rdi
0x140002a15  push    r12
0x140002a17  push    r13
0x140002a19  push    r14
0x140002a1b  push    r15
0x140002a1d  lea     rbp, [rsp-7]
0x140002a22  sub     rsp, 0F8h
0x140002a29  mov     rax, cs:__security_cookie
0x140002a30  xor     rax, rsp
0x140002a33  mov     [rbp+3Fh+var_50], rax
0x140002a37  mov     r14, [rbp+3Fh+arg_28]
0x140002a3b  mov     rbx, r8
0x140002a3e  mov     r12, [rbp+3Fh+arg_30]
0x140002a42  mov     esi, r9d
0x140002a45  mov     r13, [rbp+3Fh+arg_20]
0x140002a49  mov     r15d, edx
0x140002a4c  mov     [rbp+3Fh+var_B8], rbx
0x140002a50  mov     rdi, rcx
0x140002a53  mov     [rsp+130h+var_C8], r14
0x140002a58  mov     [rbp+3Fh+var_B0], r12
0x140002a5c  mov     [rsp+130h+var_DC], r9d
0x140002a61  mov     [rsp+130h+var_E0], edx
0x140002a65  mov     qword ptr [rsp+130h+var_D8], rcx
0x140002a6a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002a71  lea     rax, WPP_GLOBAL_Control
0x140002a78  cmp     rcx, rax
0x140002a7b  jz      short loc_140002AA1
0x140002a7d  test    dword ptr [rcx+2Ch], 200h
0x140002a84  jz      short loc_140002AA1
0x140002a86  cmp     byte ptr [rcx+29h], 2
0x140002a8a  jb      short loc_140002AA1
0x140002a8c  mov     rcx, [rcx+18h]
0x140002a90  mov     r9, rdi
0x140002a93  mov     [rsp+130h+UserData], r13
0x140002a98  mov     [rsp+130h+UserDataCount], edx
0x140002a9c  call    WPP_SF_qDq
0x140002aa1  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 4
0x140002aa8  xorps   xmm0, xmm0
0x140002aab  movups  xmmword ptr [rbp+3Fh+EventDescriptor.Id], xmm0
0x140002aaf  jz      loc_140002C5B
0x140002ab5  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140002abc  xor     edx, edx; Level
0x140002abe  movzx   r14d, word ptr [rdi+1E0h]
0x140002ac6  mov     r8, 200000000h; Keyword
0x140002ad0  call    cs:__imp_EtwProviderEnabled
0x140002ad7  nop     dword ptr [rax+rax+00h]
0x140002adc  test    al, al
0x140002ade  jz      loc_140002C56
0x140002ae4  mov     rcx, cs:PROV_SRV2_Context; RegHandle
0x140002aeb  lea     rsi, [rdi+80h]
0x140002af2  xor     edx, edx; Level
0x140002af4  mov     r8, 800000000000h; Keyword
0x140002afe  call    cs:__imp_EtwProviderEnabled
0x140002b05  nop     dword ptr [rax+rax+00h]
0x140002b0a  mov     ebx, r15d
0x140002b0d  test    al, al
0x140002b0f  jnz     short loc_140002B32
0x140002b11  cmp     r15d, 40h ; '@'
0x140002b15  jb      short loc_140002B32
0x140002b17  cmp     dword ptr [r13+0], 424D53FEh
0x140002b1f  jnz     short loc_140002B32
0x140002b21  mov     ebx, [r13+14h]
0x140002b25  add     ebx, 240h
0x140002b2b  cmp     ebx, r15d
0x140002b2e  cmova   ebx, r15d
0x140002b32  call    cs:__imp_IoGetActivityIdThread
0x140002b39  nop     dword ptr [rax+rax+00h]
0x140002b3e  mov     r15, rax
0x140002b41  test    rax, rax
0x140002b44  jnz     short loc_140002B66
0x140002b46  xorps   xmm0, xmm0
0x140002b49  mov     eax, 1
0x140002b4e  movups  xmmword ptr [rbp+3Fh+EventDescriptor.Id], xmm0
0x140002b52  lock xadd cs:Correlation, rax
0x140002b5b  inc     rax
0x140002b5e  lea     r15, [rbp+3Fh+EventDescriptor]
0x140002b62  mov     qword ptr [rbp+3Fh+EventDescriptor.Id], rax
0x140002b66  mov     rcx, cs:PROV_SRV2_Context
0x140002b6d  mov     eax, r14d
0x140002b70  mov     r9, r15
0x140002b73  cmp     ebx, 0F000h
0x140002b79  jnb     short loc_140002BA9
0x140002b7b  mov     [rsp+130h+var_F0], r13
0x140002b80  mov     r8, 200000000h
0x140002b8a  mov     dword ptr [rsp+130h+var_F8], ebx
0x140002b8e  mov     [rsp+130h+var_100], rsi
0x140002b93  mov     dword ptr [rsp+130h+UserData], 1Ch
0x140002b9b  mov     [rsp+130h+UserDataCount], eax
0x140002b9f  call    Template_qqbqb_ex
0x140002ba4  jmp     loc_140002C49
0x140002ba9  movups  xmm0, xmmword ptr [rsi]
0x140002bac  mov     dword ptr [rbp+3Fh+var_90.Ptr], eax
0x140002baf  lea     rax, [rbp+3Fh+var_90]
0x140002bb3  movups  xmm1, xmmword ptr [rsi+0Ch]
0x140002bb7  mov     [rsp+130h+UserData], rax
0x140002bbc  mov     r8, 240000000h
0x140002bc6  movups  xmmword ptr [rbp+3Fh+var_90.Size], xmm0
0x140002bca  mov     r14, r13
0x140002bcd  mov     [rbp+3Fh+var_6C], ebx
0x140002bd0  movups  xmmword ptr [rbp-3Dh], xmm1
0x140002bd4  mov     dword ptr [rbp+3Fh+var_90.Ptr+4], 1Ch
0x140002bdb  mov     [rsp+130h+UserDataCount], 28h ; '('
0x140002be3  call    Template_qqbjqb_ex
0x140002be8  mov     ecx, eax
0x140002bea  mov     rdi, 280000000h
0x140002bf4  mov     r12, 200000000h
0x140002bfe  xchg    ax, ax
0x140002c00  test    ecx, ecx
0x140002c02  js      short loc_140002C40
0x140002c04  cmp     ebx, 0F000h
0x140002c0a  jnb     short loc_140002C10
0x140002c0c  mov     esi, ebx
0x140002c0e  jmp     short loc_140002C1A
0x140002c10  mov     r8, r12
0x140002c13  mov     esi, 0F000h
0x140002c18  jnz     short loc_140002C1D
0x140002c1a  mov     r8, rdi
0x140002c1d  mov     rcx, cs:PROV_SRV2_Context
0x140002c24  mov     r9, r15
0x140002c27  mov     [rsp+130h+UserData], r14
0x140002c2c  mov     [rsp+130h+UserDataCount], esi
0x140002c30  call    Template_qqbjqb_ex
0x140002c35  mov     ecx, eax
0x140002c37  mov     eax, esi
0x140002c39  add     r14, rax
0x140002c3c  sub     ebx, esi
0x140002c3e  jnz     short loc_140002C00
0x140002c40  mov     rdi, qword ptr [rsp+130h+var_D8]
0x140002c45  mov     r12, [rbp+3Fh+var_B0]
0x140002c49  mov     esi, [rsp+130h+var_DC]
0x140002c4d  mov     rbx, [rbp+3Fh+var_B8]
0x140002c51  mov     r15d, [rsp+130h+var_E0]
0x140002c56  mov     r14, [rsp+130h+var_C8]
0x140002c5b  mov     eax, [rdi+1E4h]
0x140002c61  cmp     eax, 3
0x140002c64  jnz     loc_140002CF7
0x140002c6a  mov     rax, [rdi+1B8h]
0x140002c71  mov     r9d, r15d
0x140002c74  mov     rdx, [rdi+1D0h]
0x140002c7b  mov     r8d, esi
0x140002c7e  mov     rcx, [rdi+1C8h]
0x140002c85  mov     [rsp+130h+var_F8], r12
0x140002c8a  mov     rax, [rax+8]
0x140002c8e  mov     [rsp+130h+var_100], r14
0x140002c93  mov     [rsp+130h+UserData], r13
0x140002c98  mov     qword ptr [rsp+130h+UserDataCount], rbx
0x140002c9d  call    _guard_dispatch_icall
0x140002ca2  mov     ebx, eax
0x140002ca4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002cab  lea     rax, WPP_GLOBAL_Control
0x140002cb2  cmp     rcx, rax
0x140002cb5  jz      loc_140003598
0x140002cbb  test    dword ptr [rcx+2Ch], 200h
0x140002cc2  jz      loc_140003598
0x140002cc8  cmp     byte ptr [rcx+29h], 2
0x140002ccc  jb      loc_140003598
0x140002cd2  mov     r9, [rdi+1D0h]
0x140002cd9  lea     r8, WPP_9a5897045a5730f713eba007d66b1edc_Traceguids
0x140002ce0  mov     rcx, [rcx+18h]
0x140002ce4  mov     edx, 0Bh
0x140002ce9  mov     [rsp+130h+UserDataCount], ebx
0x140002ced  call    WPP_SF_qD
0x140002cf2  jmp     loc_140003598
0x140002cf7  cmp     eax, 2
0x140002cfa  jnz     loc_14000355C
0x140002d00  mov     rcx, cs:SrvNetDeviceExtension
0x140002d07  mov     r12d, 0C000021Bh
0x140002d0d  mov     r14, [rdi+1C0h]
0x140002d14  add     rcx, 68h ; 'h'; SpinLock
0x140002d18  mov     qword ptr [rsp+130h+var_D8], r14
0x140002d1d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002d24  nop     dword ptr [rax+rax+00h]
0x140002d29  mov     rax, [rdi+1C0h]
0x140002d30  xor     esi, esi
0x140002d32  mov     r15, [rax+170h]
0x140002d39  nop     dword ptr [rax+00000000h]
0x140002d40  mov     rax, cs:SrvNetDeviceExtension
0x140002d47  movzx   ecx, si
0x140002d4a  mov     rbx, [rax+rcx*8+1D0h]
0x140002d52  test    rbx, rbx
0x140002d55  jz      loc_140002E19
0x140002d5b  cmp     byte ptr [rbx+0EDh], 0
0x140002d62  jz      loc_140002E19
0x140002d68  test    r15, r15
0x140002d6b  jz      short loc_140002D89
0x140002d6d  movzx   eax, byte ptr [rbx+0E1h]
0x140002d74  cmp     al, 5
0x140002d76  jbe     short loc_140002D7A
0x140002d78  int     2Ch; Windows NT - assertion failure
0x140002d7a  mov     ecx, eax
0x140002d7c  mov     eax, [r15+4]
0x140002d80  bt      eax, ecx
0x140002d83  jnb     loc_140002E19
0x140002d89  mov     ecx, [rdi+1E0h]
0x140002d8f  test    ecx, ecx
0x140002d91  jz      short loc_140002DBD
0x140002d93  sub     ecx, 1
0x140002d96  jz      short loc_140002DB4
0x140002d98  sub     ecx, 1
0x140002d9b  jz      short loc_140002DAB
0x140002d9d  cmp     ecx, 2
0x140002da0  jnz     short loc_140002E19
0x140002da2  test    byte ptr [rbx+0E0h], 8
0x140002da9  jmp     short loc_140002DC4
0x140002dab  test    byte ptr [rbx+0E0h], 4
0x140002db2  jmp     short loc_140002DC4
0x140002db4  test    byte ptr [rbx+0E0h], 2
0x140002dbb  jmp     short loc_140002DC4
0x140002dbd  test    byte ptr [rbx+0E0h], 1
0x140002dc4  jz      short loc_140002E19
0x140002dc6  mov     eax, [rbx+0E8h]
0x140002dcc  cmp     byte ptr [rax+r14+1B0h], 0
0x140002dd5  jz      short loc_140002E19
0x140002dd7  mov     r14, [r14+rax*8+178h]
0x140002ddf  mov     r8, r13
0x140002de2  mov     rax, [rbx+0B0h]
0x140002de9  mov     rcx, r14
0x140002dec  mov     edx, [rsp+130h+var_E0]
0x140002df0  call    _guard_dispatch_icall
0x140002df5  mov     r12d, eax
0x140002df8  test    eax, eax
0x140002dfa  jns     loc_140003070
0x140002e00  cmp     eax, 0C00000BBh
0x140002e05  jnz     short loc_140002E14
0x140002e07  test    byte ptr [rbx+0E0h], 4
0x140002e0e  jz      loc_140002F7B
0x140002e14  mov     r14, qword ptr [rsp+130h+var_D8]
0x140002e19  inc     si
0x140002e1c  cmp     si, 7
0x140002e20  jb      loc_140002D40
0x140002e26  mov     rcx, cs:SrvNetDeviceExtension
0x140002e2d  add     rcx, 68h ; 'h'; SpinLock
0x140002e31  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002e38  nop     dword ptr [rax+rax+00h]
0x140002e3d  test    r12d, r12d
0x140002e40  js      loc_140002FAF
0x140002e46  lea     r14, WPP_GLOBAL_Control
0x140002e4d  mov     rcx, [rdi+1C0h]
0x140002e54  xorps   xmm0, xmm0
0x140002e57  add     rcx, 18h; SpinLock
0x140002e5b  movups  [rsp+130h+var_D8], xmm0
0x140002e60  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002e67  nop     dword ptr [rax+rax+00h]
0x140002e6c  mov     rax, [rdi+1C0h]
0x140002e73  movzx   ebx, byte ptr [rax+91h]
0x140002e7a  test    r15, r15
0x140002e7d  jz      short loc_140002ED1
0x140002e7f  movzx   ecx, byte ptr [rdi+1ECh]
0x140002e86  mov     eax, [r15+4]
0x140002e8a  bt      eax, ecx
0x140002e8d  jb      short loc_140002ED1
0x140002e8f  mov     r12d, 0C000021Bh
0x140002e95  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140002e9c  cmp     rcx, r14
0x140002e9f  jz      short loc_140002ED1
0x140002ea1  test    dword ptr [rcx+2Ch], 200h
0x140002ea8  jz      short loc_140002ED1
0x140002eaa  cmp     byte ptr [rcx+29h], 2
0x140002eae  jb      short loc_140002ED1
0x140002eb0  mov     r9, [rdi+1D0h]
0x140002eb7  lea     r8, WPP_9a5897045a5730f713eba007d66b1edc_Traceguids
0x140002ebe  mov     rcx, [rcx+18h]
0x140002ec2  mov     edx, 0Dh
0x140002ec7  mov     [rsp+130h+UserDataCount], r12d
0x140002ecc  call    WPP_SF_qD
0x140002ed1  lea     rcx, [rdi+200h]
0x140002ed8  mov     rax, [rcx]
0x140002edb  cmp     [rax+8], rcx
0x140002edf  jnz     loc_1400033E2
0x140002ee5  mov     rdx, [rcx+8]
0x140002ee9  cmp     [rdx], rcx
0x140002eec  jnz     loc_1400033E2
0x140002ef2  mov     [rdx], rax
0x140002ef5  mov     [rax+8], rdx
0x140002ef9  mov     rax, [rdi+1C0h]
0x140002f00  add     rax, 0E0h
0x140002f06  mov     rdx, [rax+8]
0x140002f0a  cmp     [rdx], rax
0x140002f0d  jnz     loc_1400033E2
0x140002f13  mov     [rcx], rax
0x140002f16  mov     [rcx+8], rdx
0x140002f1a  mov     [rdx], rcx
0x140002f1d  mov     [rax+8], rcx
0x140002f21  mov     rcx, [rdi+1C0h]
0x140002f28  add     rcx, 18h; SpinLock
0x140002f2c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002f33  nop     dword ptr [rax+rax+00h]
0x140002f38  lea     rax, [rdi+4]
0x140002f3c  mov     qword ptr [rsp+130h+var_D8+8], rax
0x140002f41  test    rax, rax
0x140002f44  jz      loc_140003227
0x140002f4a  mov     edx, 41h ; 'A'
0x140002f4f  mov     ecx, edx
0x140002f51  cmp     byte ptr [rax], 0
0x140002f54  jz      short loc_140002F5F
0x140002f56  inc     rax
0x140002f59  sub     rcx, 1
  ... truncated ...
```
