# WfpAleFastUdpInspection

- ea: `0x140097800`
- end: `0x140098368`
- name: `WfpAleFastUdpInspection`
- size: `2920`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int16, char, char, __int64, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x140095c00`
- `0x140097210`

## callees

- `0x14001b1a0`
- `0x140076b70`
- `0x1400773a8`
- `0x140077790`
- `0x14008b220`
- `0x140097800`
- `0x140099980`
- `0x1400999b0`
- `0x140099ab0`
- `0x140099fb0`
- `0x1400d2ca0`
- `0x1400d5ea0`
- `0x1400ee350`
- `0x140105298`
- `0x14010d46c`
- `0x1401316a0`
- `0x14016a2b0`
- `0x14016b0f4`
- `0x14016b168`
- `0x14016b1e0`
- `0x14016b2a8`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140097b83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14009825a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140097b83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14009825a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140097bd1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400982ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140097bd1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400982ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009830b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140097bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009830b`
- `ntoskrnl!ExAllocatePool2` at `0x140097a0e`
- `ntoskrnl!ExAllocatePool2` at `0x1400980b9`
- `ntoskrnl!ExAllocatePool2` at `0x140097a0e`
- `ntoskrnl!ExAllocatePool2` at `0x1400980b9`
- `NETIO!KfdIsLayerEmpty` at `0x140097d4c`
- `NETIO!KfdIsLayerEmpty` at `0x140097d8b`
- `NETIO!KfdIsLayerEmpty` at `0x140097d4c`
- `NETIO!KfdIsLayerEmpty` at `0x140097d8b`

## string_xrefs

- `0x140097abc`: `WfpAleGetRefedUdpCachedRemoteEndpoint`
- `0x14009817d`: `WfpAleSetUdpCachedRemoteEndpoint`
- `0x140097fc1`: `Continuing with the fast path`
- `0x14009802f`: `Continuing with the fast path`
- `0x140097fb3`: `Falling off of fast path.`
- `0x140098021`: `Falling off of fast path.`
- `0x140097b1d`: `StringCchCopyA`
- `0x1400981e8`: `StringCchCopyA`
- `0x140097b5f`: `WfpStringCchCopyA`
- `0x140098230`: `WfpStringCchCopyA`

## pseudocode

```c
_BOOL8 __fastcall WfpAleFastUdpInspection(
        KSPIN_LOCK *SpinLock,
        unsigned __int16 a2,
        KSPIN_LOCK a3,
        __int64 a4,
        unsigned __int16 a5,
        __int16 a6,
        char a7,
        char a8,
        __int64 a9,
        char a10)
{
  KSPIN_LOCK v11; // rdi
  __int64 Pool2; // r15
  bool v13; // r12
  __int64 v14; // r13
  unsigned __int16 v15; // bx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  __int16 v22; // ax
  __int64 v23; // r14
  __int64 v24; // rbx
  __int64 v25; // rcx
  const char *v26; // rdx
  _BYTE *v27; // r8
  char v28; // di
  _BYTE *v29; // rax
  char v30; // al
  void *v31; // rbx
  char v32; // r8
  char v33; // r14
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned __int16 v36; // ax
  __int64 v37; // rbx
  unsigned __int16 v38; // ax
  __int64 v39; // r14
  __int64 v40; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  bool v42; // zf
  const char *v43; // r9
  const char *v44; // r9
  __int64 v45; // rbx
  __int64 v46; // r14
  __int64 v47; // rbx
  const char *v48; // rax
  _BYTE *v49; // rcx
  char v50; // r8
  _BYTE *v51; // rax
  KSPIN_LOCK v52; // rcx
  void *v53; // rbx
  __int64 v54; // rdx
  char v57; // [rsp+40h] [rbp-C0h]
  char v59[8]; // [rsp+50h] [rbp-B0h] BYREF
  KSPIN_LOCK v60; // [rsp+58h] [rbp-A8h]
  __int64 v61; // [rsp+60h] [rbp-A0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h]
  _QWORD v64[79]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v65[16]; // [rsp+300h] [rbp+200h] BYREF

  v60 = a3;
  v63 = a9;
  v11 = 0;
  memset(v64, 0, sizeof(v64));
  Pool2 = 0;
  v13 = 0;
  v61 = 0;
  v59[0] = 0;
  v14 = 2147483646;
  if ( a7 )
  {
    v15 = a2;
    if ( (unsigned int)CheckOutboundBypass(a2, 0) )
    {
      v13 = 1;
LABEL_7:
      v16 = a4;
      goto LABEL_8;
    }
  }
  else
  {
    if ( (unsigned int)CheckInboundBypass(a2, 17, a5, *(_DWORD *)(v60 + 24), a9) )
    {
      v13 = 1;
      goto LABEL_6;
    }
    v15 = a2;
    if ( (*(_DWORD *)(a9 + 136) & 0x400000) != 0 )
      goto LABEL_7;
  }
  if ( (SpinLock[6] & 0x4000) != 0 || (SpinLock[6] & 0x40000000) != 0 || (SpinLock[35] & 1) != 0 )
    goto LABEL_6;
  v64[62] = SpinLock;
  WORD2(v64[7]) = v15;
  LODWORD(v64[5]) = 17;
  v18 = **(_QWORD **)(v60 + 16);
  HIWORD(v64[7]) = a5;
  v19 = *(_QWORD *)(v60 + 8);
  v64[60] = v18;
  BYTE4(v64[61]) = 1;
  LOBYTE(v64[77]) = a7;
  v20 = *(_QWORD *)(v19 + 16);
  v21 = 16;
  v64[59] = v20;
  if ( v15 == 2 )
    v21 = 4;
  LODWORD(v64[61]) = v21;
  if ( (*((_DWORD *)SpinLock + 13) & 0x40000) != 0 )
  {
    memset(v65, 0, LODWORD(v64[61]));
    BYTE5(v64[61]) = 2;
    v64[4] = v65;
    v22 = 0;
  }
  else
  {
    v64[4] = a4;
    v22 = a6;
    BYTE5(v64[61]) = 0;
  }
  LOWORD(v64[8]) = v22;
  if ( a8 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( SpinLock[92] )
    {
      v23 = 0;
      if ( gAleDebugEnabled )
      {
        v24 = 38;
        Pool2 = ExAllocatePool2(64, 38, 1281715265);
        if ( Pool2 )
          goto LABEL_31;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"ExAllocatePool2",
            23);
        }
        v23 = -1073741801;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
        {
LABEL_31:
          if ( !v23 )
          {
            v25 = 2147483646;
            v26 = "WfpAleGetRefedUdpCachedRemoteEndpoint";
            v27 = (_BYTE *)Pool2;
            do
            {
              if ( !v25 )
                break;
              if ( !*v26 )
                break;
              *v27++ = *v26++;
              --v25;
              --v24;
            }
            while ( v24 );
            v28 = 122;
            if ( v24 )
              v28 = 0;
            v29 = v27 - 1;
            if ( v24 )
              v29 = v27;
            *v29 = 0;
            if ( !v24 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"StringCchCopyA",
                  v28);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"WfpStringCchCopyA",
                  v28);
              }
            }
          }
        }
        else
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpPoolAllocNonPaged",
            23);
        }
      }
      KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
      while ( *((_DWORD *)SpinLock + 2) )
        ;
      v30 = gAleDebugEnabled;
      if ( gAleDebugEnabled == 1 && !v23 )
        SpinLock[3] = Pool2;
      v11 = SpinLock[92];
      v31 = 0;
      SpinLock[2] = 0;
      if ( v30 == 1 )
      {
        v31 = (void *)SpinLock[3];
        SpinLock[3] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( gAleDebugEnabled == 1 && v31 )
        ExFreePoolWithTag(v31, 0);
      if ( v11 )
      {
        if ( (unsigned __int8)WfpAleReferenceEndpoint_0(v11, 18) )
        {
          if ( (unsigned __int8)WfpAlepIsSameEndpoint(v11, v64) )
          {
            Pool2 = v11;
            if ( (*(_DWORD *)(v11 + 48) & 0x40000000) != 0
              || (*(_DWORD *)(v11 + 280) & 1) != 0
              || (*(_DWORD *)(v11 + 200) & 4) != 0
              || (*(_DWORD *)(v11 + 48) & 0xC000) == 0xC000 )
            {
              v32 = 0;
            }
            else
            {
              v32 = 1;
              if ( (*(_DWORD *)(v11 + 48) & 0x8000) == 0 )
                _InterlockedExchange64((volatile __int64 *)(v11 + 544), MEMORY[0xFFFFF78000000008] / 0x2710uLL);
            }
            goto LABEL_73;
          }
          WfpAleDereferenceEndpoint(v11, 18);
        }
        v11 = 0;
      }
    }
  }
  Pool2 = WfpAleFastFindRemoteEndpoint((__int64)v64, v59);
  if ( !Pool2 )
    goto LABEL_6;
  v32 = v59[0];
LABEL_73:
  v33 = a7;
  if ( (*(_DWORD *)(Pool2 + 48) & 0x100000) == 0 && a7 )
    *(_BYTE *)(Pool2 + 494) = 1;
  if ( !v32 )
    goto LABEL_6;
  v15 = a2;
  if ( (*(_DWORD *)(Pool2 + 48) & 0x8000) != 0 )
    goto LABEL_7;
  WfpGetEpochContext((_DWORD)SpinLock, a2, 17, Pool2, (__int64)&v61);
  if ( a7 )
  {
    v36 = FamilyToLayerIdOutboundTransport(a2, v34, v35);
    v37 = v61;
    if ( (unsigned int)IsOutboundTransportClassifyNeeded(v36, v61) || !(unsigned int)KfdIsLayerEmpty(79) )
      goto LABEL_6;
  }
  else
  {
    v38 = FamilyToLayerIdInboundTransport(a2);
    v37 = v61;
    v39 = v63;
    if ( (unsigned int)IsInboundTransportClassifyNeeded(v38, v63, v61)
      || !(unsigned int)KfdIsLayerEmpty(78)
      || (*(_DWORD *)(v39 + 136) & 0x2000000) != 0 && (a10 & 8) != 0 )
    {
      goto LABEL_6;
    }
    v33 = a7;
  }
  if ( (unsigned __int8)IsALEReclassifyNeeded(v37, 0) )
  {
LABEL_6:
    v15 = a2;
    goto LABEL_7;
  }
  v40 = v37;
  v15 = a2;
  if ( (unsigned int)IsDatagramDataClassifyNeeded(a2, v40) )
    goto LABEL_7;
  if ( !v33 || !(unsigned int)TlShimGetRedirectRecordForNonTCPEndpoint(SpinLock, a6, 0) )
  {
    if ( (Feature_Netsec_BugFix_UDPCaching__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFix_UDPCaching__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFix_UDPCaching__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      v42 = v33 == 0;
      v16 = a4;
      if ( v42 )
        v13 = *(_BYTE *)(Pool2 + 320) == 1;
      else
        v13 = *(_BYTE *)(Pool2 + 321) == 1;
      goto LABEL_8;
    }
    v13 = 1;
    goto LABEL_7;
  }
  if ( a2 == 2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_7;
    v16 = a4;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      WPP_SF__IPV4_d_IPV4_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_21ae1c28cece38638c80b42a9020dd23_Traceguids,
        **(_QWORD **)(v60 + 16),
        a5,
        a4,
        a6);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_7;
    v16 = a4;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      WPP_SF__IPV6_d_IPV6_d(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)WPP_21ae1c28cece38638c80b42a9020dd23_Traceguids,
        **(_QWORD **)(v60 + 16),
        a5,
        a4);
  }
LABEL_8:
  if ( (Feature_Netsec_BugFix_UDPCaching__private_featureState & 0x10) != 0 )
    v17 = Feature_Netsec_BugFix_UDPCaching__private_featureState & 1;
  else
    v17 = Feature_Netsec_BugFix_UDPCaching__private_IsEnabledDeviceUsageNoInline();
  if ( v17 )
  {
    if ( v15 == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
      {
        v43 = "Continuing with the fast path";
        if ( !v13 )
          v43 = "Falling off of fast path.";
        WPP_SF_s_IPV4_d_IPV4_d(
          WPP_GLOBAL_Control->AttachedDevice,
          a5,
          *(_QWORD *)(v60 + 16),
          (_DWORD)v43,
          **(_QWORD **)(v60 + 16),
          a5,
          v16,
          a6);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      v44 = "Continuing with the fast path";
      if ( !v13 )
        v44 = "Falling off of fast path.";
      WPP_SF_s_IPV6_d_IPV6_d(
        WPP_GLOBAL_Control->AttachedDevice,
        a5,
        *(_QWORD *)(v60 + 16),
        (_DWORD)v44,
        **(_QWORD **)(v60 + 16),
        a5,
        v16,
        a6);
    }
  }
  if ( Pool2 )
  {
    if ( v13 )
    {
      if ( !v11 )
      {
        if ( a8 )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( gAleDebugEnabled )
          {
            v45 = 33;
            v46 = ExAllocatePool2(64, 33, 1281715265);
            if ( v46 )
              goto LABEL_137;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control->AttachedDevice,
                10,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"ExAllocatePool2",
                23);
            }
            v11 = -1073741801;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
            {
LABEL_137:
              v60 = v11;
              if ( !v11 )
              {
                v48 = "WfpAleSetUdpCachedRemoteEndpoint";
                v49 = (_BYTE *)v46;
                do
                {
                  if ( !v14 )
                    break;
                  if ( !*v48 )
                    break;
                  *v49++ = *v48++;
                  --v14;
                  --v45;
                }
                while ( v45 );
                v50 = 122;
                if ( v45 )
                  v50 = 0;
                v51 = v49 - 1;
                if ( v45 )
                  v51 = v49;
                v57 = v50;
                *v51 = 0;
                if ( !v45 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
                  {
                    WPP_SF_sd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      13,
                      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                      (unsigned int)"StringCchCopyA",
                      v50);
                    v50 = v57;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
                  {
                    WPP_SF_sd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                      (unsigned int)"WfpStringCchCopyA",
                      v50);
                  }
                }
              }
              v47 = v60;
            }
            else
            {
              v47 = -1073741801;
              WPP_SF_sd(
                WPP_GLOBAL_Control->AttachedDevice,
                15,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"WfpPoolAllocNonPaged",
                23);
            }
          }
          else
          {
            v47 = 0;
            v46 = 0;
          }
          KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
          while ( *((_DWORD *)SpinLock + 2) )
            ;
          v42 = gAleDebugEnabled == 1;
          SpinLock[2] = (KSPIN_LOCK)KeGetCurrentThread();
          if ( v42 && !v47 )
            SpinLock[3] = v46;
          v52 = SpinLock[92];
          if ( v52 )
            WfpAleDereferenceEndpoint(v52, 18);
          v42 = gAleDebugEnabled == 0;
          SpinLock[92] = Pool2;
          if ( !v42 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Pool2 + 152) + 72LL));
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(Pool2 + 152) + 16LL));
          }
          v53 = 0;
          SpinLock[2] = 0;
          if ( gAleDebugEnabled == 1 )
          {
            v53 = (void *)SpinLock[3];
            SpinLock[3] = 0;
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( gAleDebugEnabled == 1 && v53 )
            ExFreePoolWithTag(v53, 0);
          return v13;
        }
        goto LABEL_173;
      }
    }
    else if ( !a8 )
    {
LABEL_173:
      v54 = 4;
      goto LABEL_174;
    }
    v54 = 18;
LABEL_174:
    WfpAleDereferenceEndpoint(Pool2, v54);
  }
  return v13;
}

```

## disassembly

```asm
0x140097800  push    rbp
0x140097802  push    rbx
0x140097803  push    rsi
0x140097804  push    rdi
0x140097805  push    r12
0x140097807  push    r13
0x140097809  push    r14
0x14009780b  push    r15
0x14009780d  lea     rbp, [rsp-228h]
0x140097815  sub     rsp, 328h
0x14009781c  mov     rax, cs:__security_cookie
0x140097823  xor     rax, rsp
0x140097826  mov     [rbp+260h+var_50], rax
0x14009782d  mov     rbx, [rbp+260h+arg_40]
0x140097834  mov     rsi, rcx
0x140097837  mov     [rsp+360h+var_308], r8
0x14009783c  lea     rcx, [rbp+260h+var_2D8]; void *
0x140097840  mov     word ptr [rsp+360h+var_320], dx
0x140097845  mov     r8d, 278h; Size
0x14009784b  xor     edx, edx; Val
0x14009784d  mov     [rbp+260h+var_2E0], rbx
0x140097851  mov     [rsp+360h+var_318], r9
0x140097856  xor     edi, edi
0x140097858  call    memset
0x14009785d  movzx   r14d, [rbp+260h+arg_30]
0x140097865  xor     r15d, r15d
0x140097868  xor     r12b, r12b
0x14009786b  mov     [rsp+360h+var_300], rdi
0x140097870  mov     [rsp+360h+var_310], dil
0x140097875  mov     r13d, 7FFFFFFEh
0x14009787b  test    r14b, r14b
0x14009787e  jz      short loc_140097898
0x140097880  movzx   ebx, word ptr [rsp+360h+var_320]
0x140097885  xor     edx, edx
0x140097887  movzx   ecx, bx
0x14009788a  call    CheckOutboundBypass
0x14009788f  test    eax, eax
0x140097891  jz      short loc_1400978F5
0x140097893  mov     r12b, 1
0x140097896  jmp     short loc_1400978C9
0x140097898  mov     rax, [rsp+360h+var_308]
0x14009789d  mov     edx, 11h
0x1400978a2  movzx   r8d, [rbp+260h+arg_20]
0x1400978aa  movzx   ecx, word ptr [rsp+360h+var_320]
0x1400978af  mov     qword ptr [rsp+360h+var_340], rbx
0x1400978b4  mov     r9d, [rax+18h]
0x1400978b8  call    CheckInboundBypass
0x1400978bd  test    eax, eax
0x1400978bf  jz      short loc_1400978E4
0x1400978c1  mov     r12b, 1
0x1400978c4  movzx   ebx, word ptr [rsp+360h+var_320]
0x1400978c9  mov     r14, [rsp+360h+var_318]
0x1400978ce  mov     eax, cs:Feature_Netsec_BugFix_UDPCaching__private_featureState
0x1400978d4  test    al, 10h
0x1400978d6  jz      loc_140097F6B
0x1400978dc  and     eax, 1
0x1400978df  jmp     loc_140097F70
0x1400978e4  test    dword ptr [rbx+88h], 400000h
0x1400978ee  movzx   ebx, word ptr [rsp+360h+var_320]
0x1400978f3  jnz     short loc_1400978C9
0x1400978f5  mov     eax, [rsi+30h]
0x1400978f8  bt      eax, 0Eh
0x1400978fc  jb      short loc_1400978C4
0x1400978fe  mov     eax, [rsi+30h]
0x140097901  bt      eax, 1Eh
0x140097905  jb      short loc_1400978C4
0x140097907  mov     eax, [rsi+118h]
0x14009790d  test    al, 1
0x14009790f  jnz     short loc_1400978C4
0x140097911  mov     rdx, [rsp+360h+var_308]
0x140097916  cmp     bx, 2
0x14009791a  mov     [rbp+260h+var_E8], rsi
0x140097921  mov     [rbp+260h+var_29C], bx
0x140097925  mov     [rbp+260h+var_2B0], 11h
0x14009792c  mov     rax, [rdx+10h]
0x140097930  mov     rcx, [rax]
0x140097933  movzx   eax, [rbp+260h+arg_20]
0x14009793a  mov     [rbp+260h+var_29A], ax
0x14009793e  mov     rax, [rdx+8]
0x140097942  mov     [rbp+260h+var_F8], rcx
0x140097949  mov     byte ptr [rbp+260h+Size+4], 1
0x140097950  mov     [rbp+260h+var_70], r14b
0x140097957  mov     rcx, [rax+10h]
0x14009795b  mov     eax, 10h
0x140097960  mov     [rbp+260h+var_100], rcx
0x140097967  mov     ecx, 4
0x14009796c  cmovz   eax, ecx
0x14009796f  mov     dword ptr [rbp+260h+Size], eax
0x140097975  mov     eax, [rsi+34h]
0x140097978  bt      eax, 12h
0x14009797c  jnb     short loc_1400979A9
0x14009797e  mov     r8d, dword ptr [rbp+260h+Size]; Size
0x140097985  lea     rcx, [rbp+260h+var_60]; void *
0x14009798c  xor     edx, edx; Val
0x14009798e  call    memset
0x140097993  lea     rax, [rbp+260h+var_60]
0x14009799a  mov     byte ptr [rbp+260h+Size+5], 2
0x1400979a1  mov     [rbp+260h+var_2B8], rax
0x1400979a5  xor     eax, eax
0x1400979a7  jmp     short loc_1400979C0
0x1400979a9  mov     rax, [rsp+360h+var_318]
0x1400979ae  mov     [rbp+260h+var_2B8], rax
0x1400979b2  movzx   eax, [rbp+260h+arg_28]
0x1400979b9  mov     byte ptr [rbp+260h+Size+5], dil
0x1400979c0  mov     [rbp+260h+var_298], ax
0x1400979c4  cmp     [rbp+260h+arg_38], dil
0x1400979cb  jz      loc_140097CA9
0x1400979d1  xor     eax, eax
0x1400979d3  xorps   xmm0, xmm0
0x1400979d6  movups  xmmword ptr [rsp+360h+LockHandle.LockQueue.Next], xmm0
0x1400979db  mov     qword ptr [rsp+360h+LockHandle.OldIrql], rax
0x1400979e0  cmp     [rsi+2E0h], rax
0x1400979e7  jz      loc_140097CA9
0x1400979ed  xor     r14d, r14d
0x1400979f0  cmp     cs:gAleDebugEnabled, al
0x1400979f6  jz      loc_140097B7B
0x1400979fc  mov     ebx, 26h ; '&'
0x140097a01  mov     r8d, 4C656C41h
0x140097a07  mov     edx, ebx
0x140097a09  mov     ecx, 40h ; '@'
0x140097a0e  call    cs:__imp_ExAllocatePool2
0x140097a15  nop     dword ptr [rax+rax+00h]
0x140097a1a  mov     r15, rax
0x140097a1d  test    rax, rax
0x140097a20  jnz     loc_140097AA9
0x140097a26  mov     rcx, cs:WPP_GLOBAL_Control
0x140097a2d  lea     r9, WPP_GLOBAL_Control
0x140097a34  cmp     rcx, r9
0x140097a37  jz      short loc_140097A73
0x140097a39  cmp     byte ptr [rcx+29h], 2
0x140097a3d  jb      short loc_140097A73
0x140097a3f  test    dword ptr [rcx+2Ch], 1000h
0x140097a46  jz      short loc_140097A73
0x140097a48  mov     rcx, [rcx+18h]
0x140097a4c  lea     r9, aExallocatepool; "ExAllocatePool2"
0x140097a53  mov     edx, 0Ah
0x140097a58  mov     dword ptr [rsp+360h+var_340], 0C0000017h
0x140097a60  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140097a67  call    WPP_SF_sd
0x140097a6c  lea     r9, WPP_GLOBAL_Control
0x140097a73  mov     r8, 0FFFFFFFFC0000017h
0x140097a7a  mov     r14, r8
0x140097a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140097a84  cmp     rcx, r9
0x140097a87  jz      short loc_140097AB0
0x140097a89  cmp     byte ptr [rcx+29h], 2
0x140097a8d  jb      short loc_140097AB0
0x140097a8f  test    dword ptr [rcx+2Ch], 1000h
0x140097a96  jz      short loc_140097AB0
0x140097a98  mov     dword ptr [rsp+360h+var_340], r8d
0x140097a9d  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x140097aa4  jmp     loc_140097B66
0x140097aa9  lea     r9, WPP_GLOBAL_Control
0x140097ab0  test    r14, r14
0x140097ab3  jnz     loc_140097B7B
0x140097ab9  mov     rcx, r13
0x140097abc  lea     rdx, aWfpalegetrefed; "WfpAleGetRefedUdpCachedRemoteEndpoint"
0x140097ac3  mov     r8, r15
0x140097ac6  test    rcx, rcx
0x140097ac9  jz      short loc_140097AE4
0x140097acb  movzx   eax, byte ptr [rdx]
0x140097ace  test    al, al
0x140097ad0  jz      short loc_140097AE4
0x140097ad2  mov     [r8], al
0x140097ad5  inc     rdx
0x140097ad8  inc     r8
0x140097adb  dec     rcx
0x140097ade  sub     rbx, 1
0x140097ae2  jnz     short loc_140097AC6
0x140097ae4  xor     eax, eax
0x140097ae6  mov     edi, 8007007Ah
0x140097aeb  test    rbx, rbx
0x140097aee  cmovnz  edi, eax
0x140097af1  lea     rax, [r8-1]
0x140097af5  cmovnz  rax, r8
0x140097af9  mov     [rax], r12b
0x140097afc  jnz     short loc_140097B7B
0x140097afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140097b05  cmp     rcx, r9
0x140097b08  jz      short loc_140097B40
0x140097b0a  cmp     byte ptr [rcx+29h], 2
0x140097b0e  jb      short loc_140097B40
0x140097b10  test    dword ptr [rcx+2Ch], 1000h
0x140097b17  jz      short loc_140097B40
0x140097b19  mov     rcx, [rcx+18h]
0x140097b1d  lea     r9, aStringcchcopya; "StringCchCopyA"
0x140097b24  mov     edx, 0Dh
0x140097b29  mov     dword ptr [rsp+360h+var_340], edi
0x140097b2d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140097b34  call    WPP_SF_sd
0x140097b39  lea     r9, WPP_GLOBAL_Control
0x140097b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140097b47  cmp     rcx, r9
0x140097b4a  jz      short loc_140097B7B
0x140097b4c  cmp     byte ptr [rcx+29h], 2
0x140097b50  jb      short loc_140097B7B
0x140097b52  test    dword ptr [rcx+2Ch], 1000h
0x140097b59  jz      short loc_140097B7B
0x140097b5b  mov     dword ptr [rsp+360h+var_340], edi
0x140097b5f  lea     r9, aWfpstringcchco; "WfpStringCchCopyA"
0x140097b66  mov     rcx, [rcx+18h]
0x140097b6a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140097b71  mov     edx, 0Fh
0x140097b76  call    WPP_SF_sd
0x140097b7b  lea     rdx, [rsp+360h+LockHandle]; LockHandle
0x140097b80  mov     rcx, rsi; SpinLock
0x140097b83  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140097b8a  nop     dword ptr [rax+rax+00h]
0x140097b8f  nop
0x140097b90  mov     eax, [rsi+8]
0x140097b93  test    eax, eax
0x140097b95  jnz     short loc_140097B90
0x140097b97  movzx   eax, cs:gAleDebugEnabled
0x140097b9e  cmp     al, 1
0x140097ba0  jnz     short loc_140097BAB
0x140097ba2  test    r14, r14
0x140097ba5  jnz     short loc_140097BAB
0x140097ba7  mov     [rsi+18h], r15
0x140097bab  mov     rdi, [rsi+2E0h]
0x140097bb2  xor     ebx, ebx
0x140097bb4  mov     qword ptr [rsi+10h], 0
0x140097bbc  cmp     al, 1
0x140097bbe  jnz     short loc_140097BCC
0x140097bc0  mov     rbx, [rsi+18h]
0x140097bc4  mov     qword ptr [rsi+18h], 0
0x140097bcc  lea     rcx, [rsp+360h+LockHandle]; LockHandle
0x140097bd1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140097bd8  nop     dword ptr [rax+rax+00h]
0x140097bdd  cmp     cs:gAleDebugEnabled, 1
0x140097be4  jnz     short loc_140097BFC
0x140097be6  test    rbx, rbx
0x140097be9  jz      short loc_140097BFC
0x140097beb  xor     edx, edx; Tag
0x140097bed  mov     rcx, rbx; P
0x140097bf0  call    cs:__imp_ExFreePoolWithTag
0x140097bf7  nop     dword ptr [rax+rax+00h]
0x140097bfc  test    rdi, rdi
0x140097bff  jz      loc_140097CA9
0x140097c05  mov     edx, 12h
0x140097c0a  mov     rcx, rdi
0x140097c0d  call    WfpAleReferenceEndpoint_0
0x140097c12  test    al, al
0x140097c14  jz      loc_140097CA7
0x140097c1a  test    rdi, rdi
0x140097c1d  jz      loc_140097CA9
0x140097c23  lea     rdx, [rbp+260h+var_2D8]
0x140097c27  mov     rcx, rdi
0x140097c2a  call    WfpAlepIsSameEndpoint
0x140097c2f  test    al, al
0x140097c31  jz      short loc_140097C9A
0x140097c33  mov     eax, [rdi+30h]
0x140097c36  mov     r15, rdi
0x140097c39  bt      eax, 1Eh
0x140097c3d  jb      short loc_140097C95
0x140097c3f  mov     eax, [rdi+118h]
0x140097c45  test    al, 1
0x140097c47  jnz     short loc_140097C95
0x140097c49  mov     eax, [rdi+0C8h]
0x140097c4f  test    al, 4
0x140097c51  jnz     short loc_140097C95
0x140097c53  mov     eax, [rdi+30h]
0x140097c56  and     eax, 0C000h
0x140097c5b  cmp     eax, 0C000h
0x140097c60  jz      short loc_140097C95
0x140097c62  mov     eax, [rdi+30h]
0x140097c65  mov     r8b, 1
0x140097c68  bt      eax, 0Fh
0x140097c6c  jb      short loc_140097CC9
0x140097c6e  mov     rcx, 0FFFFF78000000008h
0x140097c78  mov     rax, 346DC5D63886594Bh
0x140097c82  mov     rcx, [rcx]
0x140097c85  mul     rcx
0x140097c88  shr     rdx, 0Bh
0x140097c8c  xchg    rdx, [rdi+220h]
0x140097c93  jmp     short loc_140097CC9
0x140097c95  xor     r8b, r8b
0x140097c98  jmp     short loc_140097CC9
0x140097c9a  mov     edx, 12h
0x140097c9f  mov     rcx, rdi
0x140097ca2  call    WfpAleDereferenceEndpoint
0x140097ca7  xor     edi, edi
0x140097ca9  lea     rdx, [rsp+360h+var_310]
0x140097cae  lea     rcx, [rbp+260h+var_2D8]
0x140097cb2  call    WfpAleFastFindRemoteEndpoint
0x140097cb7  mov     r15, rax
0x140097cba  test    rax, rax
0x140097cbd  jz      loc_1400978C4
0x140097cc3  movzx   r8d, [rsp+360h+var_310]
0x140097cc9  mov     ecx, [r15+30h]
0x140097ccd  movzx   r14d, [rbp+260h+arg_30]
0x140097cd5  bt      ecx, 14h
0x140097cd9  jb      short loc_140097CE8
0x140097cdb  test    r14b, r14b
0x140097cde  jz      short loc_140097CE8
0x140097ce0  mov     byte ptr [r15+1EEh], 1
0x140097ce8  test    r8b, r8b
0x140097ceb  jz      loc_1400978C4
0x140097cf1  mov     eax, [r15+30h]
0x140097cf5  movzx   ebx, word ptr [rsp+360h+var_320]
0x140097cfa  bt      eax, 0Fh
  ... truncated ...
```
