# WfpAleFastUdpInspection

- ea: `0x14005d740`
- end: `0x14005e2a8`
- name: `WfpAleFastUdpInspection`
- size: `2920`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int16, char, char, __int64, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x140044e10`
- `0x14005d150`

## callees

- `0x140018ea0`
- `0x1400193a0`
- `0x14005d740`
- `0x14005f8c0`
- `0x14005f8f0`
- `0x14005fe20`
- `0x14005fe90`
- `0x140062d10`
- `0x140063548`
- `0x140063930`
- `0x1400ad6a0`
- `0x1400e3840`
- `0x1400f5da0`
- `0x1401100cc`
- `0x140116bd8`
- `0x140137040`
- `0x14016bdb0`
- `0x14016cbf4`
- `0x14016cc68`
- `0x14016cce0`
- `0x14016cda8`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005dac3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e19a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005dac3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e19a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db11`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e22c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005db11`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e22c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005db30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e24b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005db30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e24b`
- `ntoskrnl!ExAllocatePool2` at `0x14005d94e`
- `ntoskrnl!ExAllocatePool2` at `0x14005dff9`
- `ntoskrnl!ExAllocatePool2` at `0x14005d94e`
- `ntoskrnl!ExAllocatePool2` at `0x14005dff9`
- `NETIO!KfdIsLayerEmpty` at `0x14005dc8c`
- `NETIO!KfdIsLayerEmpty` at `0x14005dccb`
- `NETIO!KfdIsLayerEmpty` at `0x14005dc8c`
- `NETIO!KfdIsLayerEmpty` at `0x14005dccb`

## string_xrefs

- `0x14005d9fc`: `WfpAleGetRefedUdpCachedRemoteEndpoint`
- `0x14005e0bd`: `WfpAleSetUdpCachedRemoteEndpoint`
- `0x14005def3`: `Falling off of fast path.`
- `0x14005df61`: `Falling off of fast path.`
- `0x14005df01`: `Continuing with the fast path`
- `0x14005df6f`: `Continuing with the fast path`
- `0x14005da5d`: `StringCchCopyA`
- `0x14005e128`: `StringCchCopyA`
- `0x14005da9f`: `WfpStringCchCopyA`
- `0x14005e170`: `WfpStringCchCopyA`

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
0x14005d740  push    rbp
0x14005d742  push    rbx
0x14005d743  push    rsi
0x14005d744  push    rdi
0x14005d745  push    r12
0x14005d747  push    r13
0x14005d749  push    r14
0x14005d74b  push    r15
0x14005d74d  lea     rbp, [rsp-228h]
0x14005d755  sub     rsp, 328h
0x14005d75c  mov     rax, cs:__security_cookie
0x14005d763  xor     rax, rsp
0x14005d766  mov     [rbp+260h+var_50], rax
0x14005d76d  mov     rbx, [rbp+260h+arg_40]
0x14005d774  mov     rsi, rcx
0x14005d777  mov     [rsp+360h+var_308], r8
0x14005d77c  lea     rcx, [rbp+260h+var_2D8]; void *
0x14005d780  mov     word ptr [rsp+360h+var_320], dx
0x14005d785  mov     r8d, 278h; Size
0x14005d78b  xor     edx, edx; Val
0x14005d78d  mov     [rbp+260h+var_2E0], rbx
0x14005d791  mov     [rsp+360h+var_318], r9
0x14005d796  xor     edi, edi
0x14005d798  call    memset
0x14005d79d  movzx   r14d, [rbp+260h+arg_30]
0x14005d7a5  xor     r15d, r15d
0x14005d7a8  xor     r12b, r12b
0x14005d7ab  mov     [rsp+360h+var_300], rdi
0x14005d7b0  mov     [rsp+360h+var_310], dil
0x14005d7b5  mov     r13d, 7FFFFFFEh
0x14005d7bb  test    r14b, r14b
0x14005d7be  jz      short loc_14005D7D8
0x14005d7c0  movzx   ebx, word ptr [rsp+360h+var_320]
0x14005d7c5  xor     edx, edx
0x14005d7c7  movzx   ecx, bx
0x14005d7ca  call    CheckOutboundBypass
0x14005d7cf  test    eax, eax
0x14005d7d1  jz      short loc_14005D835
0x14005d7d3  mov     r12b, 1
0x14005d7d6  jmp     short loc_14005D809
0x14005d7d8  mov     rax, [rsp+360h+var_308]
0x14005d7dd  mov     edx, 11h
0x14005d7e2  movzx   r8d, [rbp+260h+arg_20]
0x14005d7ea  movzx   ecx, word ptr [rsp+360h+var_320]
0x14005d7ef  mov     qword ptr [rsp+360h+var_340], rbx
0x14005d7f4  mov     r9d, [rax+18h]
0x14005d7f8  call    CheckInboundBypass
0x14005d7fd  test    eax, eax
0x14005d7ff  jz      short loc_14005D824
0x14005d801  mov     r12b, 1
0x14005d804  movzx   ebx, word ptr [rsp+360h+var_320]
0x14005d809  mov     r14, [rsp+360h+var_318]
0x14005d80e  mov     eax, cs:Feature_Netsec_BugFix_UDPCaching__private_featureState
0x14005d814  test    al, 10h
0x14005d816  jz      loc_14005DEAB
0x14005d81c  and     eax, 1
0x14005d81f  jmp     loc_14005DEB0
0x14005d824  test    dword ptr [rbx+88h], 400000h
0x14005d82e  movzx   ebx, word ptr [rsp+360h+var_320]
0x14005d833  jnz     short loc_14005D809
0x14005d835  mov     eax, [rsi+30h]
0x14005d838  bt      eax, 0Eh
0x14005d83c  jb      short loc_14005D804
0x14005d83e  mov     eax, [rsi+30h]
0x14005d841  bt      eax, 1Eh
0x14005d845  jb      short loc_14005D804
0x14005d847  mov     eax, [rsi+118h]
0x14005d84d  test    al, 1
0x14005d84f  jnz     short loc_14005D804
0x14005d851  mov     rdx, [rsp+360h+var_308]
0x14005d856  cmp     bx, 2
0x14005d85a  mov     [rbp+260h+var_E8], rsi
0x14005d861  mov     [rbp+260h+var_29C], bx
0x14005d865  mov     [rbp+260h+var_2B0], 11h
0x14005d86c  mov     rax, [rdx+10h]
0x14005d870  mov     rcx, [rax]
0x14005d873  movzx   eax, [rbp+260h+arg_20]
0x14005d87a  mov     [rbp+260h+var_29A], ax
0x14005d87e  mov     rax, [rdx+8]
0x14005d882  mov     [rbp+260h+var_F8], rcx
0x14005d889  mov     byte ptr [rbp+260h+Size+4], 1
0x14005d890  mov     [rbp+260h+var_70], r14b
0x14005d897  mov     rcx, [rax+10h]
0x14005d89b  mov     eax, 10h
0x14005d8a0  mov     [rbp+260h+var_100], rcx
0x14005d8a7  mov     ecx, 4
0x14005d8ac  cmovz   eax, ecx
0x14005d8af  mov     dword ptr [rbp+260h+Size], eax
0x14005d8b5  mov     eax, [rsi+34h]
0x14005d8b8  bt      eax, 12h
0x14005d8bc  jnb     short loc_14005D8E9
0x14005d8be  mov     r8d, dword ptr [rbp+260h+Size]; Size
0x14005d8c5  lea     rcx, [rbp+260h+var_60]; void *
0x14005d8cc  xor     edx, edx; Val
0x14005d8ce  call    memset
0x14005d8d3  lea     rax, [rbp+260h+var_60]
0x14005d8da  mov     byte ptr [rbp+260h+Size+5], 2
0x14005d8e1  mov     [rbp+260h+var_2B8], rax
0x14005d8e5  xor     eax, eax
0x14005d8e7  jmp     short loc_14005D900
0x14005d8e9  mov     rax, [rsp+360h+var_318]
0x14005d8ee  mov     [rbp+260h+var_2B8], rax
0x14005d8f2  movzx   eax, [rbp+260h+arg_28]
0x14005d8f9  mov     byte ptr [rbp+260h+Size+5], dil
0x14005d900  mov     [rbp+260h+var_298], ax
0x14005d904  cmp     [rbp+260h+arg_38], dil
0x14005d90b  jz      loc_14005DBE9
0x14005d911  xor     eax, eax
0x14005d913  xorps   xmm0, xmm0
0x14005d916  movups  xmmword ptr [rsp+360h+LockHandle.LockQueue.Next], xmm0
0x14005d91b  mov     qword ptr [rsp+360h+LockHandle.OldIrql], rax
0x14005d920  cmp     [rsi+2E0h], rax
0x14005d927  jz      loc_14005DBE9
0x14005d92d  xor     r14d, r14d
0x14005d930  cmp     cs:gAleDebugEnabled, al
0x14005d936  jz      loc_14005DABB
0x14005d93c  mov     ebx, 26h ; '&'
0x14005d941  mov     r8d, 4C656C41h
0x14005d947  mov     edx, ebx
0x14005d949  mov     ecx, 40h ; '@'
0x14005d94e  call    cs:__imp_ExAllocatePool2
0x14005d955  nop     dword ptr [rax+rax+00h]
0x14005d95a  mov     r15, rax
0x14005d95d  test    rax, rax
0x14005d960  jnz     loc_14005D9E9
0x14005d966  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d96d  lea     r9, WPP_GLOBAL_Control
0x14005d974  cmp     rcx, r9
0x14005d977  jz      short loc_14005D9B3
0x14005d979  cmp     byte ptr [rcx+29h], 2
0x14005d97d  jb      short loc_14005D9B3
0x14005d97f  test    dword ptr [rcx+2Ch], 1000h
0x14005d986  jz      short loc_14005D9B3
0x14005d988  mov     rcx, [rcx+18h]
0x14005d98c  lea     r9, aExallocatepool; "ExAllocatePool2"
0x14005d993  mov     edx, 0Ah
0x14005d998  mov     dword ptr [rsp+360h+var_340], 0C0000017h
0x14005d9a0  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14005d9a7  call    WPP_SF_sd
0x14005d9ac  lea     r9, WPP_GLOBAL_Control
0x14005d9b3  mov     r8, 0FFFFFFFFC0000017h
0x14005d9ba  mov     r14, r8
0x14005d9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d9c4  cmp     rcx, r9
0x14005d9c7  jz      short loc_14005D9F0
0x14005d9c9  cmp     byte ptr [rcx+29h], 2
0x14005d9cd  jb      short loc_14005D9F0
0x14005d9cf  test    dword ptr [rcx+2Ch], 1000h
0x14005d9d6  jz      short loc_14005D9F0
0x14005d9d8  mov     dword ptr [rsp+360h+var_340], r8d
0x14005d9dd  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x14005d9e4  jmp     loc_14005DAA6
0x14005d9e9  lea     r9, WPP_GLOBAL_Control
0x14005d9f0  test    r14, r14
0x14005d9f3  jnz     loc_14005DABB
0x14005d9f9  mov     rcx, r13
0x14005d9fc  lea     rdx, aWfpalegetrefed; "WfpAleGetRefedUdpCachedRemoteEndpoint"
0x14005da03  mov     r8, r15
0x14005da06  test    rcx, rcx
0x14005da09  jz      short loc_14005DA24
0x14005da0b  movzx   eax, byte ptr [rdx]
0x14005da0e  test    al, al
0x14005da10  jz      short loc_14005DA24
0x14005da12  mov     [r8], al
0x14005da15  inc     rdx
0x14005da18  inc     r8
0x14005da1b  dec     rcx
0x14005da1e  sub     rbx, 1
0x14005da22  jnz     short loc_14005DA06
0x14005da24  xor     eax, eax
0x14005da26  mov     edi, 8007007Ah
0x14005da2b  test    rbx, rbx
0x14005da2e  cmovnz  edi, eax
0x14005da31  lea     rax, [r8-1]
0x14005da35  cmovnz  rax, r8
0x14005da39  mov     [rax], r12b
0x14005da3c  jnz     short loc_14005DABB
0x14005da3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da45  cmp     rcx, r9
0x14005da48  jz      short loc_14005DA80
0x14005da4a  cmp     byte ptr [rcx+29h], 2
0x14005da4e  jb      short loc_14005DA80
0x14005da50  test    dword ptr [rcx+2Ch], 1000h
0x14005da57  jz      short loc_14005DA80
0x14005da59  mov     rcx, [rcx+18h]
0x14005da5d  lea     r9, aStringcchcopya; "StringCchCopyA"
0x14005da64  mov     edx, 0Dh
0x14005da69  mov     dword ptr [rsp+360h+var_340], edi
0x14005da6d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14005da74  call    WPP_SF_sd
0x14005da79  lea     r9, WPP_GLOBAL_Control
0x14005da80  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da87  cmp     rcx, r9
0x14005da8a  jz      short loc_14005DABB
0x14005da8c  cmp     byte ptr [rcx+29h], 2
0x14005da90  jb      short loc_14005DABB
0x14005da92  test    dword ptr [rcx+2Ch], 1000h
0x14005da99  jz      short loc_14005DABB
0x14005da9b  mov     dword ptr [rsp+360h+var_340], edi
0x14005da9f  lea     r9, aWfpstringcchco; "WfpStringCchCopyA"
0x14005daa6  mov     rcx, [rcx+18h]
0x14005daaa  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14005dab1  mov     edx, 0Fh
0x14005dab6  call    WPP_SF_sd
0x14005dabb  lea     rdx, [rsp+360h+LockHandle]; LockHandle
0x14005dac0  mov     rcx, rsi; SpinLock
0x14005dac3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005daca  nop     dword ptr [rax+rax+00h]
0x14005dacf  nop
0x14005dad0  mov     eax, [rsi+8]
0x14005dad3  test    eax, eax
0x14005dad5  jnz     short loc_14005DAD0
0x14005dad7  movzx   eax, cs:gAleDebugEnabled
0x14005dade  cmp     al, 1
0x14005dae0  jnz     short loc_14005DAEB
0x14005dae2  test    r14, r14
0x14005dae5  jnz     short loc_14005DAEB
0x14005dae7  mov     [rsi+18h], r15
0x14005daeb  mov     rdi, [rsi+2E0h]
0x14005daf2  xor     ebx, ebx
0x14005daf4  mov     qword ptr [rsi+10h], 0
0x14005dafc  cmp     al, 1
0x14005dafe  jnz     short loc_14005DB0C
0x14005db00  mov     rbx, [rsi+18h]
0x14005db04  mov     qword ptr [rsi+18h], 0
0x14005db0c  lea     rcx, [rsp+360h+LockHandle]; LockHandle
0x14005db11  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005db18  nop     dword ptr [rax+rax+00h]
0x14005db1d  cmp     cs:gAleDebugEnabled, 1
0x14005db24  jnz     short loc_14005DB3C
0x14005db26  test    rbx, rbx
0x14005db29  jz      short loc_14005DB3C
0x14005db2b  xor     edx, edx; Tag
0x14005db2d  mov     rcx, rbx; P
0x14005db30  call    cs:__imp_ExFreePoolWithTag
0x14005db37  nop     dword ptr [rax+rax+00h]
0x14005db3c  test    rdi, rdi
0x14005db3f  jz      loc_14005DBE9
0x14005db45  mov     edx, 12h
0x14005db4a  mov     rcx, rdi
0x14005db4d  call    WfpAleReferenceEndpoint_0
0x14005db52  test    al, al
0x14005db54  jz      loc_14005DBE7
0x14005db5a  test    rdi, rdi
0x14005db5d  jz      loc_14005DBE9
0x14005db63  lea     rdx, [rbp+260h+var_2D8]
0x14005db67  mov     rcx, rdi
0x14005db6a  call    WfpAlepIsSameEndpoint
0x14005db6f  test    al, al
0x14005db71  jz      short loc_14005DBDA
0x14005db73  mov     eax, [rdi+30h]
0x14005db76  mov     r15, rdi
0x14005db79  bt      eax, 1Eh
0x14005db7d  jb      short loc_14005DBD5
0x14005db7f  mov     eax, [rdi+118h]
0x14005db85  test    al, 1
0x14005db87  jnz     short loc_14005DBD5
0x14005db89  mov     eax, [rdi+0C8h]
0x14005db8f  test    al, 4
0x14005db91  jnz     short loc_14005DBD5
0x14005db93  mov     eax, [rdi+30h]
0x14005db96  and     eax, 0C000h
0x14005db9b  cmp     eax, 0C000h
0x14005dba0  jz      short loc_14005DBD5
0x14005dba2  mov     eax, [rdi+30h]
0x14005dba5  mov     r8b, 1
0x14005dba8  bt      eax, 0Fh
0x14005dbac  jb      short loc_14005DC09
0x14005dbae  mov     rcx, 0FFFFF78000000008h
0x14005dbb8  mov     rax, 346DC5D63886594Bh
0x14005dbc2  mov     rcx, [rcx]
0x14005dbc5  mul     rcx
0x14005dbc8  shr     rdx, 0Bh
0x14005dbcc  xchg    rdx, [rdi+220h]
0x14005dbd3  jmp     short loc_14005DC09
0x14005dbd5  xor     r8b, r8b
0x14005dbd8  jmp     short loc_14005DC09
0x14005dbda  mov     edx, 12h
0x14005dbdf  mov     rcx, rdi
0x14005dbe2  call    WfpAleDereferenceEndpoint
0x14005dbe7  xor     edi, edi
0x14005dbe9  lea     rdx, [rsp+360h+var_310]
0x14005dbee  lea     rcx, [rbp+260h+var_2D8]
0x14005dbf2  call    WfpAleFastFindRemoteEndpoint
0x14005dbf7  mov     r15, rax
0x14005dbfa  test    rax, rax
0x14005dbfd  jz      loc_14005D804
0x14005dc03  movzx   r8d, [rsp+360h+var_310]
0x14005dc09  mov     ecx, [r15+30h]
0x14005dc0d  movzx   r14d, [rbp+260h+arg_30]
0x14005dc15  bt      ecx, 14h
0x14005dc19  jb      short loc_14005DC28
0x14005dc1b  test    r14b, r14b
0x14005dc1e  jz      short loc_14005DC28
0x14005dc20  mov     byte ptr [r15+1EEh], 1
0x14005dc28  test    r8b, r8b
0x14005dc2b  jz      loc_14005D804
0x14005dc31  mov     eax, [r15+30h]
0x14005dc35  movzx   ebx, word ptr [rsp+360h+var_320]
0x14005dc3a  bt      eax, 0Fh
  ... truncated ...
```
