# WfpAleFastUdpInspection

- ea: `0x140096950`
- end: `0x1400974b8`
- name: `WfpAleFastUdpInspection`
- size: `2920`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int16, char, char, __int64, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x140094d50`
- `0x140096360`

## callees

- `0x14001af00`
- `0x1400768d0`
- `0x140077108`
- `0x1400774f0`
- `0x14008a370`
- `0x140096950`
- `0x140098ad0`
- `0x140098b00`
- `0x140098c00`
- `0x140099100`
- `0x1400d2ec0`
- `0x1400d60c0`
- `0x1400ee460`
- `0x140105278`
- `0x14010d32c`
- `0x140131560`
- `0x14016a170`
- `0x14016afb4`
- `0x14016b028`
- `0x14016b0a0`
- `0x14016b168`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140096cd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400973aa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140096cd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400973aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140096d21`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14009743c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140096d21`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14009743c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009745b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096d40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009745b`
- `ntoskrnl!ExAllocatePool2` at `0x140096b5e`
- `ntoskrnl!ExAllocatePool2` at `0x140097209`
- `ntoskrnl!ExAllocatePool2` at `0x140096b5e`
- `ntoskrnl!ExAllocatePool2` at `0x140097209`
- `NETIO!KfdIsLayerEmpty` at `0x140096e9c`
- `NETIO!KfdIsLayerEmpty` at `0x140096edb`
- `NETIO!KfdIsLayerEmpty` at `0x140096e9c`
- `NETIO!KfdIsLayerEmpty` at `0x140096edb`

## string_xrefs

- `0x140096c0c`: `WfpAleGetRefedUdpCachedRemoteEndpoint`
- `0x1400972cd`: `WfpAleSetUdpCachedRemoteEndpoint`
- `0x140097103`: `Falling off of fast path.`
- `0x140097171`: `Falling off of fast path.`
- `0x140097111`: `Continuing with the fast path`
- `0x14009717f`: `Continuing with the fast path`
- `0x140096caf`: `WfpStringCchCopyA`
- `0x140097380`: `WfpStringCchCopyA`
- `0x140096c6d`: `StringCchCopyA`
- `0x140097338`: `StringCchCopyA`

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
0x140096950  push    rbp
0x140096952  push    rbx
0x140096953  push    rsi
0x140096954  push    rdi
0x140096955  push    r12
0x140096957  push    r13
0x140096959  push    r14
0x14009695b  push    r15
0x14009695d  lea     rbp, [rsp-228h]
0x140096965  sub     rsp, 328h
0x14009696c  mov     rax, cs:__security_cookie
0x140096973  xor     rax, rsp
0x140096976  mov     [rbp+260h+var_50], rax
0x14009697d  mov     rbx, [rbp+260h+arg_40]
0x140096984  mov     rsi, rcx
0x140096987  mov     [rsp+360h+var_308], r8
0x14009698c  lea     rcx, [rbp+260h+var_2D8]; void *
0x140096990  mov     word ptr [rsp+360h+var_320], dx
0x140096995  mov     r8d, 278h; Size
0x14009699b  xor     edx, edx; Val
0x14009699d  mov     [rbp+260h+var_2E0], rbx
0x1400969a1  mov     [rsp+360h+var_318], r9
0x1400969a6  xor     edi, edi
0x1400969a8  call    memset
0x1400969ad  movzx   r14d, [rbp+260h+arg_30]
0x1400969b5  xor     r15d, r15d
0x1400969b8  xor     r12b, r12b
0x1400969bb  mov     [rsp+360h+var_300], rdi
0x1400969c0  mov     [rsp+360h+var_310], dil
0x1400969c5  mov     r13d, 7FFFFFFEh
0x1400969cb  test    r14b, r14b
0x1400969ce  jz      short loc_1400969E8
0x1400969d0  movzx   ebx, word ptr [rsp+360h+var_320]
0x1400969d5  xor     edx, edx
0x1400969d7  movzx   ecx, bx
0x1400969da  call    CheckOutboundBypass
0x1400969df  test    eax, eax
0x1400969e1  jz      short loc_140096A45
0x1400969e3  mov     r12b, 1
0x1400969e6  jmp     short loc_140096A19
0x1400969e8  mov     rax, [rsp+360h+var_308]
0x1400969ed  mov     edx, 11h
0x1400969f2  movzx   r8d, [rbp+260h+arg_20]
0x1400969fa  movzx   ecx, word ptr [rsp+360h+var_320]
0x1400969ff  mov     qword ptr [rsp+360h+var_340], rbx
0x140096a04  mov     r9d, [rax+18h]
0x140096a08  call    CheckInboundBypass
0x140096a0d  test    eax, eax
0x140096a0f  jz      short loc_140096A34
0x140096a11  mov     r12b, 1
0x140096a14  movzx   ebx, word ptr [rsp+360h+var_320]
0x140096a19  mov     r14, [rsp+360h+var_318]
0x140096a1e  mov     eax, cs:Feature_Netsec_BugFix_UDPCaching__private_featureState
0x140096a24  test    al, 10h
0x140096a26  jz      loc_1400970BB
0x140096a2c  and     eax, 1
0x140096a2f  jmp     loc_1400970C0
0x140096a34  test    dword ptr [rbx+88h], 400000h
0x140096a3e  movzx   ebx, word ptr [rsp+360h+var_320]
0x140096a43  jnz     short loc_140096A19
0x140096a45  mov     eax, [rsi+30h]
0x140096a48  bt      eax, 0Eh
0x140096a4c  jb      short loc_140096A14
0x140096a4e  mov     eax, [rsi+30h]
0x140096a51  bt      eax, 1Eh
0x140096a55  jb      short loc_140096A14
0x140096a57  mov     eax, [rsi+118h]
0x140096a5d  test    al, 1
0x140096a5f  jnz     short loc_140096A14
0x140096a61  mov     rdx, [rsp+360h+var_308]
0x140096a66  cmp     bx, 2
0x140096a6a  mov     [rbp+260h+var_E8], rsi
0x140096a71  mov     [rbp+260h+var_29C], bx
0x140096a75  mov     [rbp+260h+var_2B0], 11h
0x140096a7c  mov     rax, [rdx+10h]
0x140096a80  mov     rcx, [rax]
0x140096a83  movzx   eax, [rbp+260h+arg_20]
0x140096a8a  mov     [rbp+260h+var_29A], ax
0x140096a8e  mov     rax, [rdx+8]
0x140096a92  mov     [rbp+260h+var_F8], rcx
0x140096a99  mov     byte ptr [rbp+260h+Size+4], 1
0x140096aa0  mov     [rbp+260h+var_70], r14b
0x140096aa7  mov     rcx, [rax+10h]
0x140096aab  mov     eax, 10h
0x140096ab0  mov     [rbp+260h+var_100], rcx
0x140096ab7  mov     ecx, 4
0x140096abc  cmovz   eax, ecx
0x140096abf  mov     dword ptr [rbp+260h+Size], eax
0x140096ac5  mov     eax, [rsi+34h]
0x140096ac8  bt      eax, 12h
0x140096acc  jnb     short loc_140096AF9
0x140096ace  mov     r8d, dword ptr [rbp+260h+Size]; Size
0x140096ad5  lea     rcx, [rbp+260h+var_60]; void *
0x140096adc  xor     edx, edx; Val
0x140096ade  call    memset
0x140096ae3  lea     rax, [rbp+260h+var_60]
0x140096aea  mov     byte ptr [rbp+260h+Size+5], 2
0x140096af1  mov     [rbp+260h+var_2B8], rax
0x140096af5  xor     eax, eax
0x140096af7  jmp     short loc_140096B10
0x140096af9  mov     rax, [rsp+360h+var_318]
0x140096afe  mov     [rbp+260h+var_2B8], rax
0x140096b02  movzx   eax, [rbp+260h+arg_28]
0x140096b09  mov     byte ptr [rbp+260h+Size+5], dil
0x140096b10  mov     [rbp+260h+var_298], ax
0x140096b14  cmp     [rbp+260h+arg_38], dil
0x140096b1b  jz      loc_140096DF9
0x140096b21  xor     eax, eax
0x140096b23  xorps   xmm0, xmm0
0x140096b26  movups  xmmword ptr [rsp+360h+LockHandle.LockQueue.Next], xmm0
0x140096b2b  mov     qword ptr [rsp+360h+LockHandle.OldIrql], rax
0x140096b30  cmp     [rsi+2E0h], rax
0x140096b37  jz      loc_140096DF9
0x140096b3d  xor     r14d, r14d
0x140096b40  cmp     cs:gAleDebugEnabled, al
0x140096b46  jz      loc_140096CCB
0x140096b4c  mov     ebx, 26h ; '&'
0x140096b51  mov     r8d, 4C656C41h
0x140096b57  mov     edx, ebx
0x140096b59  mov     ecx, 40h ; '@'
0x140096b5e  call    cs:__imp_ExAllocatePool2
0x140096b65  nop     dword ptr [rax+rax+00h]
0x140096b6a  mov     r15, rax
0x140096b6d  test    rax, rax
0x140096b70  jnz     loc_140096BF9
0x140096b76  mov     rcx, cs:WPP_GLOBAL_Control
0x140096b7d  lea     r9, WPP_GLOBAL_Control
0x140096b84  cmp     rcx, r9
0x140096b87  jz      short loc_140096BC3
0x140096b89  cmp     byte ptr [rcx+29h], 2
0x140096b8d  jb      short loc_140096BC3
0x140096b8f  test    dword ptr [rcx+2Ch], 1000h
0x140096b96  jz      short loc_140096BC3
0x140096b98  mov     rcx, [rcx+18h]
0x140096b9c  lea     r9, aExallocatepool; "ExAllocatePool2"
0x140096ba3  mov     edx, 0Ah
0x140096ba8  mov     dword ptr [rsp+360h+var_340], 0C0000017h
0x140096bb0  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140096bb7  call    WPP_SF_sd
0x140096bbc  lea     r9, WPP_GLOBAL_Control
0x140096bc3  mov     r8, 0FFFFFFFFC0000017h
0x140096bca  mov     r14, r8
0x140096bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140096bd4  cmp     rcx, r9
0x140096bd7  jz      short loc_140096C00
0x140096bd9  cmp     byte ptr [rcx+29h], 2
0x140096bdd  jb      short loc_140096C00
0x140096bdf  test    dword ptr [rcx+2Ch], 1000h
0x140096be6  jz      short loc_140096C00
0x140096be8  mov     dword ptr [rsp+360h+var_340], r8d
0x140096bed  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x140096bf4  jmp     loc_140096CB6
0x140096bf9  lea     r9, WPP_GLOBAL_Control
0x140096c00  test    r14, r14
0x140096c03  jnz     loc_140096CCB
0x140096c09  mov     rcx, r13
0x140096c0c  lea     rdx, aWfpalegetrefed; "WfpAleGetRefedUdpCachedRemoteEndpoint"
0x140096c13  mov     r8, r15
0x140096c16  test    rcx, rcx
0x140096c19  jz      short loc_140096C34
0x140096c1b  movzx   eax, byte ptr [rdx]
0x140096c1e  test    al, al
0x140096c20  jz      short loc_140096C34
0x140096c22  mov     [r8], al
0x140096c25  inc     rdx
0x140096c28  inc     r8
0x140096c2b  dec     rcx
0x140096c2e  sub     rbx, 1
0x140096c32  jnz     short loc_140096C16
0x140096c34  xor     eax, eax
0x140096c36  mov     edi, 8007007Ah
0x140096c3b  test    rbx, rbx
0x140096c3e  cmovnz  edi, eax
0x140096c41  lea     rax, [r8-1]
0x140096c45  cmovnz  rax, r8
0x140096c49  mov     [rax], r12b
0x140096c4c  jnz     short loc_140096CCB
0x140096c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140096c55  cmp     rcx, r9
0x140096c58  jz      short loc_140096C90
0x140096c5a  cmp     byte ptr [rcx+29h], 2
0x140096c5e  jb      short loc_140096C90
0x140096c60  test    dword ptr [rcx+2Ch], 1000h
0x140096c67  jz      short loc_140096C90
0x140096c69  mov     rcx, [rcx+18h]
0x140096c6d  lea     r9, aStringcchcopya; "StringCchCopyA"
0x140096c74  mov     edx, 0Dh
0x140096c79  mov     dword ptr [rsp+360h+var_340], edi
0x140096c7d  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140096c84  call    WPP_SF_sd
0x140096c89  lea     r9, WPP_GLOBAL_Control
0x140096c90  mov     rcx, cs:WPP_GLOBAL_Control
0x140096c97  cmp     rcx, r9
0x140096c9a  jz      short loc_140096CCB
0x140096c9c  cmp     byte ptr [rcx+29h], 2
0x140096ca0  jb      short loc_140096CCB
0x140096ca2  test    dword ptr [rcx+2Ch], 1000h
0x140096ca9  jz      short loc_140096CCB
0x140096cab  mov     dword ptr [rsp+360h+var_340], edi
0x140096caf  lea     r9, aWfpstringcchco; "WfpStringCchCopyA"
0x140096cb6  mov     rcx, [rcx+18h]
0x140096cba  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140096cc1  mov     edx, 0Fh
0x140096cc6  call    WPP_SF_sd
0x140096ccb  lea     rdx, [rsp+360h+LockHandle]; LockHandle
0x140096cd0  mov     rcx, rsi; SpinLock
0x140096cd3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140096cda  nop     dword ptr [rax+rax+00h]
0x140096cdf  nop
0x140096ce0  mov     eax, [rsi+8]
0x140096ce3  test    eax, eax
0x140096ce5  jnz     short loc_140096CE0
0x140096ce7  movzx   eax, cs:gAleDebugEnabled
0x140096cee  cmp     al, 1
0x140096cf0  jnz     short loc_140096CFB
0x140096cf2  test    r14, r14
0x140096cf5  jnz     short loc_140096CFB
0x140096cf7  mov     [rsi+18h], r15
0x140096cfb  mov     rdi, [rsi+2E0h]
0x140096d02  xor     ebx, ebx
0x140096d04  mov     qword ptr [rsi+10h], 0
0x140096d0c  cmp     al, 1
0x140096d0e  jnz     short loc_140096D1C
0x140096d10  mov     rbx, [rsi+18h]
0x140096d14  mov     qword ptr [rsi+18h], 0
0x140096d1c  lea     rcx, [rsp+360h+LockHandle]; LockHandle
0x140096d21  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140096d28  nop     dword ptr [rax+rax+00h]
0x140096d2d  cmp     cs:gAleDebugEnabled, 1
0x140096d34  jnz     short loc_140096D4C
0x140096d36  test    rbx, rbx
0x140096d39  jz      short loc_140096D4C
0x140096d3b  xor     edx, edx; Tag
0x140096d3d  mov     rcx, rbx; P
0x140096d40  call    cs:__imp_ExFreePoolWithTag
0x140096d47  nop     dword ptr [rax+rax+00h]
0x140096d4c  test    rdi, rdi
0x140096d4f  jz      loc_140096DF9
0x140096d55  mov     edx, 12h
0x140096d5a  mov     rcx, rdi
0x140096d5d  call    WfpAleReferenceEndpoint_0
0x140096d62  test    al, al
0x140096d64  jz      loc_140096DF7
0x140096d6a  test    rdi, rdi
0x140096d6d  jz      loc_140096DF9
0x140096d73  lea     rdx, [rbp+260h+var_2D8]
0x140096d77  mov     rcx, rdi
0x140096d7a  call    WfpAlepIsSameEndpoint
0x140096d7f  test    al, al
0x140096d81  jz      short loc_140096DEA
0x140096d83  mov     eax, [rdi+30h]
0x140096d86  mov     r15, rdi
0x140096d89  bt      eax, 1Eh
0x140096d8d  jb      short loc_140096DE5
0x140096d8f  mov     eax, [rdi+118h]
0x140096d95  test    al, 1
0x140096d97  jnz     short loc_140096DE5
0x140096d99  mov     eax, [rdi+0C8h]
0x140096d9f  test    al, 4
0x140096da1  jnz     short loc_140096DE5
0x140096da3  mov     eax, [rdi+30h]
0x140096da6  and     eax, 0C000h
0x140096dab  cmp     eax, 0C000h
0x140096db0  jz      short loc_140096DE5
0x140096db2  mov     eax, [rdi+30h]
0x140096db5  mov     r8b, 1
0x140096db8  bt      eax, 0Fh
0x140096dbc  jb      short loc_140096E19
0x140096dbe  mov     rcx, 0FFFFF78000000008h
0x140096dc8  mov     rax, 346DC5D63886594Bh
0x140096dd2  mov     rcx, [rcx]
0x140096dd5  mul     rcx
0x140096dd8  shr     rdx, 0Bh
0x140096ddc  xchg    rdx, [rdi+220h]
0x140096de3  jmp     short loc_140096E19
0x140096de5  xor     r8b, r8b
0x140096de8  jmp     short loc_140096E19
0x140096dea  mov     edx, 12h
0x140096def  mov     rcx, rdi
0x140096df2  call    WfpAleDereferenceEndpoint
0x140096df7  xor     edi, edi
0x140096df9  lea     rdx, [rsp+360h+var_310]
0x140096dfe  lea     rcx, [rbp+260h+var_2D8]
0x140096e02  call    WfpAleFastFindRemoteEndpoint
0x140096e07  mov     r15, rax
0x140096e0a  test    rax, rax
0x140096e0d  jz      loc_140096A14
0x140096e13  movzx   r8d, [rsp+360h+var_310]
0x140096e19  mov     ecx, [r15+30h]
0x140096e1d  movzx   r14d, [rbp+260h+arg_30]
0x140096e25  bt      ecx, 14h
0x140096e29  jb      short loc_140096E38
0x140096e2b  test    r14b, r14b
0x140096e2e  jz      short loc_140096E38
0x140096e30  mov     byte ptr [r15+1EEh], 1
0x140096e38  test    r8b, r8b
0x140096e3b  jz      loc_140096A14
0x140096e41  mov     eax, [r15+30h]
0x140096e45  movzx   ebx, word ptr [rsp+360h+var_320]
0x140096e4a  bt      eax, 0Fh
  ... truncated ...
```
