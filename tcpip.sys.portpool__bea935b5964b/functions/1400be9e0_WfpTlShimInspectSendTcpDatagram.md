# WfpTlShimInspectSendTcpDatagram

- ea: `0x1400be9e0`
- end: `0x1400bf332`
- name: `WfpTlShimInspectSendTcpDatagram`
- size: `2386`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000f9c0`

## callees

- `0x140011340`
- `0x1400114b0`
- `0x14001150c`
- `0x14001215c`
- `0x140012f00`
- `0x140013140`
- `0x1400143c0`
- `0x140014480`
- `0x140015a70`
- `0x140047c20`
- `0x1400a1150`
- `0x1400ad6a0`
- `0x1400bd6a8`
- `0x1400be9e0`
- `0x1400bf340`
- `0x1400bf390`
- `0x1400bf840`
- `0x1400bfc9c`
- `0x1400bff50`
- `0x1400c0500`
- `0x1400c05e0`
- `0x1400c0ca4`
- `0x1400c0d78`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1400bf2f2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400beb01`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400beb01`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400beecd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf22e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400beecd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bf22e`
- `NETIO!KfdIsLayerEmpty` at `0x1400beaa0`
- `NETIO!KfdIsLayerEmpty` at `0x1400bef26`
- `NETIO!KfdIsLayerEmpty` at `0x1400beaa0`
- `NETIO!KfdIsLayerEmpty` at `0x1400bef26`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400bee1c`
- `NETIO!KfdReleaseTerminatingFilters` at `0x1400bee1c`
- `NETIO!KfdReleaseCachedFilters` at `0x1400bedd4`
- `NETIO!KfdReleaseCachedFilters` at `0x1400bedd4`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400bec7f`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x1400bec7f`
- `NETIO!KfdClassify` at `0x1400bed4c`
- `NETIO!KfdClassify` at `0x1401cfd43`
- `NETIO!KfdClassify` at `0x1400bed4c`
- `NETIO!KfdClassify` at `0x1401cfd43`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x1400bec5f`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x1400bec5f`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1400befb7`
- `NETIO!KfdGetLayerCacheEpoch` at `0x1400befb7`

## string_xrefs

- `0x1400bf1c6`: `WfpAleCopySecurityRealmIdFromEndpoint`
- `0x1400bf273`: `WfpAleCopySecurityRealmIdFromEndpoint`

## pseudocode

```c
__int64 __fastcall WfpTlShimInspectSendTcpDatagram(
        _DWORD *SpinLock,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        __int64 a5,
        int a6,
        int *a7)
{
  int v7; // eax
  unsigned __int16 v9; // di
  bool v10; // zf
  int v11; // r13d
  char v12; // r15
  int ProfileIdFromInterface; // r12d
  __int64 v14; // rax
  unsigned __int8 v15; // di
  char v16; // bl
  __int64 v17; // r15
  int *v18; // rdi
  int v19; // r9d
  int v20; // r8d
  int v21; // eax
  int v22; // ecx
  __int64 inserted; // rax
  KSPIN_LOCK v24; // rcx
  __int64 v25; // rax
  int *v26; // rax
  __int64 v27; // rbx
  int v28; // ebx
  const UCHAR *v29; // r15
  SCOPE_LEVEL v30; // edx
  unsigned int v31; // ecx
  _OWORD *PacketInfo; // rax
  unsigned __int16 v33; // r13
  __int64 v34; // rcx
  unsigned int v35; // ebx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  int v40; // r12d
  char *v41; // r13
  unsigned int v42; // r10d
  int v43; // eax
  __int64 v44; // rdi
  _DWORD *v45; // rcx
  int v46; // eax
  __int64 v47; // r12
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rbx
  int v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+28h] [rbp-D8h]
  char v54; // [rsp+62h] [rbp-9Eh]
  unsigned __int8 v55; // [rsp+63h] [rbp-9Dh]
  int v56; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v57; // [rsp+68h] [rbp-98h]
  unsigned __int16 v58; // [rsp+6Ah] [rbp-96h]
  int v59; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h] BYREF
  int *v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h]
  PVOID P[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v68[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v69[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v70; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+120h] [rbp+20h]

  v7 = 16;
  v57 = a4;
  v58 = a3;
  if ( a2 != 2 )
    LOWORD(v7) = 18;
  v9 = a2;
  v59 = v7;
  v10 = (SpinLock[13] & 0x20000) == 0;
  v11 = SpinLock[13] & 0x20000;
  v62 = 0;
  LODWORD(v63) = 0;
  v12 = !v10;
  WORD2(v63) = 0;
  v66 = 0;
  v61 = 0;
  LODWORD(v71) = 0;
  v56 = 0;
  *(_OWORD *)P = 0;
  memset(v68, 0, sizeof(v68));
  *(_OWORD *)v69 = 0;
  v70 = 0;
  *(_OWORD *)v65 = 0;
  if ( a2 != 2 )
  {
    if ( !(unsigned int)KfdIsLayerEmpty(18) )
      goto LABEL_5;
LABEL_64:
    v35 = 0;
    v40 = 1;
LABEL_51:
    if ( qword_14022BF38 )
    {
      v42 = 0;
      if ( v9 != 2 )
        v42 = 41;
      LOWORD(v52) = v57;
      LOWORD(v51) = v58;
      v43 = qword_14022BF38(v42, *(_QWORD *)a5, *(_QWORD *)(a5 + 8), 6, v51, v52, *(_QWORD *)(a5 + 48), v40, SpinLock);
      if ( v43 != 1 )
      {
        if ( v43 )
        {
          v46 = v43 - 2;
          if ( !v46 )
          {
            v35 = 3;
            goto LABEL_56;
          }
          if ( v46 == 1 )
          {
            v35 = 2;
            goto LABEL_56;
          }
        }
        v35 = 1;
        goto LABEL_56;
      }
      v35 = 0;
    }
LABEL_56:
    if ( !v35 && *(_BYTE *)(a5 + 44) )
      v35 = WfpTlShimInspectFastLoopbackSendDatagram(SpinLock, v9, *(_QWORD *)(a5 + 48)) != 0;
    goto LABEL_59;
  }
  if ( (unsigned int)KfdIsLayerEmpty(16) )
    goto LABEL_64;
LABEL_5:
  if ( (SpinLock[12] & 0x40000000) != 0 || (SpinLock[12] & 0x800) != 0 )
    return 1;
  if ( a7 )
  {
    ProfileIdFromInterface = *a7;
    v10 = (SpinLock[50] & 0x4000) == 0;
    P[1] = 0;
    LODWORD(P[0]) = 0;
    if ( !v10 )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      AleAcquireEndpointLockEx((PKSPIN_LOCK)SpinLock, &LockHandle);
      v49 = WfpBufferCopy(*((void **)SpinLock + 34), (unsigned int)SpinLock[66], 0x52537049u, &P[1]);
      LODWORD(P[0]) = SpinLock[66];
      v50 = v49;
      AleReleaseEndpointLock(SpinLock, &LockHandle);
      if ( v50 )
      {
        if ( P[1] )
          ExFreePoolWithTag(P[1], 0x52537049u);
        P[1] = 0;
        LODWORD(P[0]) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpAleCopySecurityRealmIdFromEndpoint",
            v50);
        }
      }
    }
LABEL_9:
    if ( !*((_QWORD *)SpinLock + 43) )
      goto LABEL_10;
    v60 = TlShimLookupLayerCache((PKSPIN_LOCK)SpinLock);
    v44 = v60;
    if ( !v60 )
      goto LABEL_10;
    KfdGetLayerCacheEpoch((unsigned __int16)v59, SpinLock + 90);
    v45 = SpinLock;
    if ( SpinLock[90] != *(_DWORD *)(v60 + 44) )
    {
LABEL_71:
      TlShimPurgeLayerCache(v45, v44);
      TlShimReleaseLayerCache(&v60);
LABEL_10:
      if ( KeGetCurrentIrql() >= 2u )
      {
        v15 = 0;
        v55 = 0;
        v16 = 0;
      }
      else
      {
        v14 = WfpRaiseIrqlToDispatchLevel();
        v15 = v14;
        v55 = v14;
        v16 = 1;
      }
      LODWORD(v14) = HIDWORD(KeGetPcr()[1].LockArray);
      v54 = v16;
      if ( !*((_BYTE *)gPerProcessorContext + 72 * v14 + 32) )
      {
        v17 = *((_QWORD *)gPerProcessorContext + 9 * v14 + 3);
        v18 = (int *)*((_QWORD *)gPerProcessorContext + 9 * v14 + 2);
        *((_BYTE *)gPerProcessorContext + 72 * v14 + 32) = 1;
        goto LABEL_14;
      }
      if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &v66) )
      {
        if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v61) )
        {
          v17 = v66;
          v18 = v61;
LABEL_14:
          v60 = v17;
          memset((void *)v17, 0, 0x2A0u);
          memset(v18, 0, 0x2A8u);
          v19 = v57;
          v20 = v58;
          *((_QWORD *)v18 + 79) = v18 + 156;
          *((_QWORD *)v18 + 78) = v18 + 156;
          v21 = TlShimMarshalOutTransportFields(
                  a2,
                  6,
                  v20,
                  v19,
                  a5,
                  ProfileIdFromInterface,
                  *(_BYTE *)(a5 + 44) != 0,
                  (__int64)P,
                  v17);
          v10 = SpinLock[170] == 1;
          LOWORD(v62) = v59;
          HIDWORD(v62) = v21;
          v63 = v17;
          v61 = 0;
          if ( v10 )
            v18[1] |= 0x80000u;
          v22 = *v18 | 0x400;
          v18[11] = a6;
          if ( v11 )
            v18[1] |= 8u;
          *v18 = v22 | 0x880;
          v18[20] = ***(_DWORD ***)(*(_QWORD *)a5 + 8LL);
          inserted = WfpAleQueryOrInsertEndpointHandle(SpinLock);
          if ( inserted )
          {
            *v18 |= 0x8000u;
            *((_QWORD *)v18 + 14) = inserted;
            v24 = *((_QWORD *)SpinLock + 68);
            if ( v24 )
            {
              v25 = WfpAleQueryOrInsertEndpointHandle(v24);
              if ( v25 )
              {
                *v18 |= 0x4000000u;
                *((_QWORD *)v18 + 24) = v25;
              }
            }
          }
          if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, 0, &v61) )
          {
            v26 = v61;
            *v18 |= 2u;
            *((_QWORD *)v18 + 4) = v26;
            KfdAleReleaseFlowHandleForFlow(SpinLock);
          }
          v27 = *(_QWORD *)(a5 + 56);
          if ( v27 )
          {
            v28 = *(_DWORD *)(v27 + 8);
            v56 = v28;
            if ( !v28 )
              goto LABEL_34;
            v29 = *(const UCHAR **)(a5 + 8);
            if ( a2 == 23 )
            {
              IN6_UNCANONICALIZE_SCOPE_ID(v29, &v56);
              v28 = v56;
            }
            else
            {
              v30 = Ipv4AddressScope(v29);
              if ( v30 == ScopeLevelGlobal || *v29 == 127 )
              {
                v28 = 0;
                v31 = 0;
              }
              else
              {
                v31 = v28;
              }
              if ( v31 >> 28 == v30 )
                v28 = v31 & 0xFFFFFFF;
            }
            v17 = v60;
          }
          else
          {
            v28 = *(_DWORD *)(a5 + 64);
          }
          if ( v28 )
          {
            *v18 |= 0x20000u;
            v18[30] = v28;
          }
LABEL_34:
          *(_QWORD *)&v68[0] = SpinLock;
          *((_QWORD *)v18 + 1) = v68;
          PacketInfo = (_OWORD *)FwppGetPacketInfo(*(_QWORD *)(a5 + 48));
          if ( PacketInfo && PacketInfo != MmBadPointer )
            *((_OWORD *)v18 + 23) = PacketInfo[22];
          v33 = v59;
          v65[1] = (__int64)v65;
          v65[0] = (__int64)v65;
          v34 = (unsigned __int16)v59;
          *((_QWORD *)v18 + 64) = v65;
          v35 = KfdClassify(v34, &v62, v18, *(_QWORD *)(a5 + 48), 0, v69);
          HIDWORD(v37) = HIDWORD(qword_14022BF30);
          if ( qword_14022BF30
            && (v38 = *(_QWORD *)(a5 + 48),
                LOWORD(v59) = 0,
                v56 = 0,
                v37 = qword_14022BF30(SpinLock, v38, &v59, &v56),
                (_DWORD)v37) )
          {
            *(_DWORD *)(v17 + 168) = v56;
            *(_WORD *)(v17 + 88) = __ROR2__(v59, 8);
            *((_QWORD *)v18 + 64) = 0;
            v37 = KfdClassify(v33, &v62, v18, *(_QWORD *)(a5 + 48), 0, v69);
            v35 = v37;
            if ( v18[134] )
              goto LABEL_42;
          }
          else if ( v18[134] )
          {
            v37 = TlShimCacheMatchedFilterList((PKSPIN_LOCK)SpinLock, (__int64)v65, v52);
            if ( (int)v37 < 0 )
LABEL_42:
              v37 = KfdReleaseCachedFilters(v65);
          }
          if ( v35 )
          {
            HIDWORD(v37) = 0;
            *(_OWORD *)v69 = 0;
            LODWORD(v69[0]) = 4097;
            v70 = 0;
            v71 = 0;
          }
          else if ( LODWORD(v69[0]) != 4097 )
          {
            v40 = 1;
LABEL_46:
            LODWORD(v37) = HIDWORD(KeGetPcr()[1].LockArray);
            v41 = (char *)gPerProcessorContext + 72 * v37;
            KfdReleaseTerminatingFilters(v18 + 156, 9 * v37, v36);
            if ( v60 == *((_QWORD *)v41 + 3) )
            {
              v41[32] = 0;
            }
            else
            {
              PplFreeToLookasideList(gMetadataLookasideList, v18);
              PplFreeToLookasideList(gIncomingValuesLookasideList, v60);
            }
            if ( v54 )
              WfpLowerIrqlFromDispatchLevel(v55);
            goto LABEL_50;
          }
          if ( (BYTE12(v70) & 1) != 0 )
          {
            v35 = 3;
            v40 = 2;
          }
          else
          {
            *((_QWORD *)v18 + 64) = 0;
            v40 = 0;
            v37 = WfpShimIndicateDiscardGeneral(
                    v33,
                    (unsigned int)&v62,
                    (_DWORD)v18,
                    *(_QWORD *)(a5 + 48),
                    0,
                    (__int64)v69);
            v35 = 1;
          }
          goto LABEL_46;
        }
        PplFreeToLookasideList(gIncomingValuesLookasideList, v66);
      }
      if ( v16 )
        WfpLowerIrqlFromDispatchLevel(v15);
      v35 = 1;
      goto LABEL_59;
    }
    if ( !TlShimDirectClassify((KSPIN_LOCK *)SpinLock, a2, v60, 6, v58, v57, 0, a5, a6, 0, v12, &v56) )
    {
      v45 = SpinLock;
      goto LABEL_71;
    }
    v40 = v56;
    if ( v56 == 1 )
    {
      v35 = 0;
      TlShimReleaseLayerCache(&v60);
LABEL_50:
      v9 = a2;
      goto LABEL_51;
    }
    if ( v56 )
    {
      if ( v56 == 2 )
      {
        v35 = 3;
        TlShimReleaseLayerCache(&v60);
        goto LABEL_50;
      }
      if ( v56 == 3 )
      {
        v35 = 2;
        TlShimReleaseLayerCache(&v60);
        goto LABEL_50;
      }
    }
    v35 = 1;
    TlShimReleaseLayerCache(&v60);
    goto LABEL_50;
  }
  v47 = *(_QWORD *)(a5 + 32);
  if ( *(_DWORD *)(*(_QWORD *)(v47 + 48) + 12LL) != 131 )
  {
    ProfileIdFromInterface = *(_DWORD *)(v47 + 56);
    goto LABEL_9;
  }
  if ( (unsigned int)TlShimDiscoverPhysicalNexthopInterface(SpinLock, v9, 6, a5) != 259 )
  {
    ProfileIdFromInterface = WfpGetProfileIdFromInterface(
                               *(_QWORD *)(a5 + 32),
                               v48,
                               *(_QWORD *)a5,
                               *(_QWORD *)(a5 + 24),
                               0);
    goto LABEL_9;
  }
  v35 = 3;
LABEL_59:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x52537049u);
  return v35;
}

```

## disassembly

```asm
0x1400be9e0  push    rbp
0x1400be9e2  push    rbx
0x1400be9e3  push    rsi
0x1400be9e4  push    rdi
0x1400be9e5  push    r12
0x1400be9e7  push    r13
0x1400be9e9  push    r14
0x1400be9eb  push    r15
0x1400be9ed  lea     rbp, [rsp-38h]
0x1400be9f2  sub     rsp, 138h
0x1400be9f9  mov     rax, cs:__security_cookie
0x1400bea00  xor     rax, rsp
0x1400bea03  mov     [rbp+70h+var_48], rax
0x1400bea07  mov     r14, [rbp+70h+arg_20]
0x1400bea0e  xorps   xmm0, xmm0
0x1400bea11  mov     rbx, [rbp+70h+arg_30]
0x1400bea18  cmp     dx, 2
0x1400bea1c  mov     eax, 10h
0x1400bea21  mov     [rsp+170h+var_108], r9w
0x1400bea27  mov     rsi, rcx
0x1400bea2a  mov     [rsp+170h+var_106], r8w
0x1400bea30  mov     ecx, 12h
0x1400bea35  mov     [rsp+170h+var_110], dx
0x1400bea3a  cmovnz  ax, cx
0x1400bea3e  movzx   edi, dx
0x1400bea41  xor     r12d, r12d
0x1400bea44  mov     [rsp+170h+var_104], eax
0x1400bea48  mov     r13d, [rsi+34h]
0x1400bea4c  xor     eax, eax
0x1400bea4e  and     r13d, 20000h
0x1400bea55  mov     [rbp+70h+var_F0], rax
0x1400bea59  mov     dword ptr [rbp+70h+var_E8], eax
0x1400bea5c  setnz   r15b
0x1400bea60  mov     word ptr [rbp+70h+var_E8+4], ax
0x1400bea64  mov     [rbp+70h+var_C0], r12
0x1400bea68  mov     [rsp+170h+var_F8], r12
0x1400bea6d  mov     dword ptr [rbp+70h+var_50], eax
0x1400bea70  mov     [rsp+170h+var_10C], r12d
0x1400bea75  movups  xmmword ptr [rbp+70h+P], xmm0
0x1400bea79  movups  [rbp+70h+var_A0], xmm0
0x1400bea7d  movups  [rbp+70h+var_90], xmm0
0x1400bea81  movups  [rbp+70h+var_80], xmm0
0x1400bea85  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x1400bea89  movups  [rbp+70h+var_60], xmm0
0x1400bea8d  movups  xmmword ptr [rbp+70h+var_D0], xmm0
0x1400bea91  cmp     dx, 2
0x1400bea95  jnz     loc_1400BEF26
0x1400bea9b  mov     ecx, 10h
0x1400beaa0  call    cs:__imp_KfdIsLayerEmpty
0x1400beaa7  nop     dword ptr [rax+rax+00h]
0x1400beaac  test    eax, eax
0x1400beaae  jnz     loc_1400BEF3A
0x1400beab4  mov     eax, [rsi+30h]
0x1400beab7  bt      eax, 1Eh
0x1400beabb  jb      loc_1400BEDBD
0x1400beac1  mov     eax, [rsi+30h]
0x1400beac4  bt      eax, 0Bh
0x1400beac8  jb      loc_1400BEDBD
0x1400beace  test    rbx, rbx
0x1400bead1  jz      loc_1400BF112
0x1400bead7  mov     r12d, [rbx]
0x1400beada  xor     edi, edi
0x1400beadc  test    dword ptr [rsi+0C8h], 4000h
0x1400beae6  mov     [rbp+70h+P+8], rdi
0x1400beaea  mov     dword ptr [rbp+70h+P], edi
0x1400beaed  jnz     loc_1400BF1C3
0x1400beaf3  cmp     qword ptr [rsi+158h], 0
0x1400beafb  jnz     loc_1400BEF8A
0x1400beb01  call    cs:__imp_KeGetCurrentIrql
0x1400beb08  nop     dword ptr [rax+rax+00h]
0x1400beb0d  cmp     al, 2
0x1400beb0f  jnb     loc_1400BF151
0x1400beb15  call    WfpRaiseIrqlToDispatchLevel
0x1400beb1a  movzx   edi, al
0x1400beb1d  mov     [rsp+170h+var_10D], al
0x1400beb21  mov     bl, 1
0x1400beb23  mov     eax, gs:1A4h
0x1400beb2b  mov     [rsp+170h+var_10E], bl
0x1400beb2f  lea     rdx, [rax+rax*8]
0x1400beb33  mov     rax, cs:gPerProcessorContext
0x1400beb3a  cmp     byte ptr [rax+rdx*8+20h], 0
0x1400beb3f  jnz     loc_1400BF0D1
0x1400beb45  mov     r15, [rax+rdx*8+18h]
0x1400beb4a  mov     rdi, [rax+rdx*8+10h]
0x1400beb4f  mov     byte ptr [rax+rdx*8+20h], 1
0x1400beb54  xor     edx, edx; Val
0x1400beb56  mov     [rsp+170h+var_100], r15
0x1400beb5b  mov     r8d, 2A0h; Size
0x1400beb61  mov     rcx, r15; void *
0x1400beb64  call    memset
0x1400beb69  xor     edx, edx; Val
0x1400beb6b  mov     r8d, 2A8h; Size
0x1400beb71  mov     rcx, rdi; void *
0x1400beb74  call    memset
0x1400beb79  movzx   r9d, [rsp+170h+var_108]
0x1400beb7f  lea     rax, [rdi+270h]
0x1400beb86  movzx   r8d, [rsp+170h+var_106]
0x1400beb8c  lea     rcx, [rbp+70h+P]
0x1400beb90  mov     [rax+8], rax
0x1400beb94  mov     edx, 6
0x1400beb99  mov     [rax], rax
0x1400beb9c  xor     eax, eax
0x1400beb9e  cmp     [r14+2Ch], al
0x1400beba2  mov     [rsp+170h+var_130], r15
0x1400beba7  mov     [rsp+170h+var_138], rcx
0x1400bebac  setnz   al
0x1400bebaf  movzx   ecx, [rsp+170h+var_110]
0x1400bebb4  mov     dword ptr [rsp+170h+var_140], eax
0x1400bebb8  mov     dword ptr [rsp+170h+var_148], r12d
0x1400bebbd  mov     [rsp+170h+var_150], r14
0x1400bebc2  call    TlShimMarshalOutTransportFields
0x1400bebc7  cmp     dword ptr [rsi+2A8h], 1
0x1400bebce  mov     ecx, [rsp+170h+var_104]
0x1400bebd2  mov     word ptr [rbp+70h+var_F0], cx
0x1400bebd6  mov     dword ptr [rbp+70h+var_F0+4], eax
0x1400bebd9  mov     [rbp+70h+var_E8], r15
0x1400bebdd  mov     [rsp+170h+var_F8], 0
0x1400bebe6  jz      loc_1400BF2E6
0x1400bebec  mov     ecx, [rdi]
0x1400bebee  mov     eax, [rbp+70h+arg_28]
0x1400bebf4  bts     ecx, 0Ah
0x1400bebf8  mov     [rdi+2Ch], eax
0x1400bebfb  test    r13d, r13d
0x1400bebfe  jz      short loc_1400BEC04
0x1400bec00  or      dword ptr [rdi+4], 8
0x1400bec04  or      ecx, 880h
0x1400bec0a  mov     [rdi], ecx
0x1400bec0c  mov     rax, [r14]
0x1400bec0f  mov     rcx, [rax+8]
0x1400bec13  mov     rax, [rcx]
0x1400bec16  mov     ecx, [rax]
0x1400bec18  mov     [rdi+50h], ecx
0x1400bec1b  mov     rcx, rsi
0x1400bec1e  call    WfpAleQueryOrInsertEndpointHandle
0x1400bec23  test    rax, rax
0x1400bec26  jz      short loc_1400BEC55
0x1400bec28  or      dword ptr [rdi], 8000h
0x1400bec2e  mov     [rdi+70h], rax
0x1400bec32  mov     rcx, [rsi+220h]
0x1400bec39  test    rcx, rcx
0x1400bec3c  jz      short loc_1400BEC55
0x1400bec3e  call    WfpAleQueryOrInsertEndpointHandle
0x1400bec43  test    rax, rax
0x1400bec46  jz      short loc_1400BEC55
0x1400bec48  or      dword ptr [rdi], 4000000h
0x1400bec4e  mov     [rdi+0C0h], rax
0x1400bec55  lea     r8, [rsp+170h+var_F8]
0x1400bec5a  xor     edx, edx
0x1400bec5c  mov     rcx, rsi
0x1400bec5f  call    cs:__imp_KfdAleAcquireFlowHandleForFlow
0x1400bec66  nop     dword ptr [rax+rax+00h]
0x1400bec6b  test    rax, rax
0x1400bec6e  jnz     short loc_1400BEC8B
0x1400bec70  mov     rax, [rsp+170h+var_F8]
0x1400bec75  mov     rcx, rsi
0x1400bec78  or      dword ptr [rdi], 2
0x1400bec7b  mov     [rdi+20h], rax
0x1400bec7f  call    cs:__imp_KfdAleReleaseFlowHandleForFlow
0x1400bec86  nop     dword ptr [rax+rax+00h]
0x1400bec8b  mov     rbx, [r14+38h]
0x1400bec8f  test    rbx, rbx
0x1400bec92  jz      loc_1400BF052
0x1400bec98  mov     ebx, [rbx+8]
0x1400bec9b  mov     [rsp+170h+var_10C], ebx
0x1400bec9f  test    ebx, ebx
0x1400beca1  jz      short loc_1400BECED
0x1400beca3  cmp     [rsp+170h+var_110], 17h
0x1400beca9  mov     r15, [r14+8]
0x1400becad  mov     rcx, r15; Address
0x1400becb0  jz      loc_1400BEF13
0x1400becb6  call    Ipv4AddressScope
0x1400becbb  mov     edx, eax
0x1400becbd  cmp     eax, 0Eh
0x1400becc0  jnz     loc_1400BF05B
0x1400becc6  xor     ebx, ebx
0x1400becc8  xor     ecx, ecx
0x1400becca  mov     eax, ecx
0x1400beccc  shr     eax, 1Ch
0x1400beccf  cmp     eax, edx
0x1400becd1  jnz     short loc_1400BECDB
0x1400becd3  mov     ebx, ecx
0x1400becd5  and     ebx, 0FFFFFFFh
0x1400becdb  mov     r15, [rsp+170h+var_100]
0x1400bece0  test    ebx, ebx
0x1400bece2  jz      short loc_1400BECED
0x1400bece4  or      dword ptr [rdi], 20000h
0x1400becea  mov     [rdi+78h], ebx
0x1400beced  lea     rax, [rbp+70h+var_A0]
0x1400becf1  mov     qword ptr [rbp+70h+var_A0], rsi
0x1400becf5  mov     [rdi+8], rax
0x1400becf9  mov     rcx, [r14+30h]
0x1400becfd  call    FwppGetPacketInfo
0x1400bed02  test    rax, rax
0x1400bed05  jnz     loc_1400BF2F2
0x1400bed0b  mov     r13d, [rsp+170h+var_104]
0x1400bed10  lea     rax, [rbp+70h+var_D0]
0x1400bed14  mov     [rbp+70h+var_D0+8], rax
0x1400bed18  lea     rdx, [rbp+70h+var_F0]
0x1400bed1c  lea     rax, [rbp+70h+var_D0]
0x1400bed20  mov     r8, rdi
0x1400bed23  mov     [rbp+70h+var_D0], rax
0x1400bed27  movzx   ecx, r13w
0x1400bed2b  lea     rax, [rbp+70h+var_D0]
0x1400bed2f  mov     [rdi+200h], rax
0x1400bed36  lea     rax, [rbp+70h+var_70]
0x1400bed3a  mov     r9, [r14+30h]
0x1400bed3e  mov     [rsp+170h+var_148], rax; __int64
0x1400bed43  mov     [rsp+170h+var_150], 0
0x1400bed4c  call    cs:__imp_KfdClassify
0x1400bed53  nop     dword ptr [rax+rax+00h]
0x1400bed58  mov     ebx, eax
0x1400bed5a  mov     rax, cs:qword_14022BF30
0x1400bed61  test    rax, rax
0x1400bed64  jz      short loc_1400BED8F
0x1400bed66  mov     rdx, [r14+30h]
0x1400bed6a  lea     r9, [rsp+170h+var_10C]
0x1400bed6f  xor     ecx, ecx
0x1400bed71  lea     r8, [rsp+170h+var_104]
0x1400bed76  mov     word ptr [rsp+170h+var_104], cx
0x1400bed7b  mov     [rsp+170h+var_10C], ecx
0x1400bed7f  mov     rcx, rsi
0x1400bed82  call    _guard_dispatch_icall
0x1400bed87  test    eax, eax
0x1400bed89  jnz     loc_1401CFD04
0x1400bed8f  cmp     dword ptr [rdi+218h], 0
0x1400bed96  jz      short loc_1400BEDE0
0x1400bed98  mov     r8d, [rdi+210h]
0x1400bed9f  lea     rax, [rbp+70h+var_D0]
0x1400beda3  mov     r9d, r12d
0x1400beda6  mov     [rsp+170h+var_150], rax; __int64
0x1400bedab  movzx   edx, r13w
0x1400bedaf  mov     rcx, rsi; SpinLock
0x1400bedb2  call    TlShimCacheMatchedFilterList
0x1400bedb7  test    eax, eax
0x1400bedb9  jns     short loc_1400BEDE0
0x1400bedbb  jmp     short loc_1400BEDD0
0x1400bedbd  mov     eax, 1
0x1400bedc2  jmp     loc_1400BEEDB
0x1400bedc7  cmp     dword ptr [rdi+218h], 0
0x1400bedce  jz      short loc_1400BEDE0
0x1400bedd0  lea     rcx, [rbp+70h+var_D0]
0x1400bedd4  call    cs:__imp_KfdReleaseCachedFilters
0x1400beddb  nop     dword ptr [rax+rax+00h]
0x1400bede0  mov     r15d, 1
0x1400bede6  test    ebx, ebx
0x1400bede8  jnz     loc_1400BF315
0x1400bedee  cmp     dword ptr [rbp+70h+var_70], 1001h
0x1400bedf5  jz      loc_1400BEF4B
0x1400bedfb  mov     r12d, r15d
0x1400bedfe  mov     eax, gs:1A4h
0x1400bee06  lea     rcx, [rdi+270h]
0x1400bee0d  lea     rdx, [rax+rax*8]
0x1400bee11  mov     rax, cs:gPerProcessorContext
0x1400bee18  lea     r13, [rax+rdx*8]
0x1400bee1c  call    cs:__imp_KfdReleaseTerminatingFilters
0x1400bee23  nop     dword ptr [rax+rax+00h]
0x1400bee28  mov     rax, [rsp+170h+var_100]
0x1400bee2d  cmp     rax, [r13+18h]
0x1400bee31  jnz     loc_1400BF0AC
0x1400bee37  mov     byte ptr [r13+20h], 0
0x1400bee3c  cmp     [rsp+170h+var_10E], 0
0x1400bee41  jz      short loc_1400BEE4D
0x1400bee43  movzx   ecx, [rsp+170h+var_10D]
0x1400bee48  call    WfpLowerIrqlFromDispatchLevel
0x1400bee4d  movzx   edi, [rsp+170h+var_110]
0x1400bee52  mov     rax, cs:qword_14022BF38
0x1400bee59  test    rax, rax
0x1400bee5c  jz      short loc_1400BEEB5
0x1400bee5e  mov     r8, [r14+8]
0x1400bee62  xor     r10d, r10d
0x1400bee65  mov     rdx, [r14]
0x1400bee68  mov     ecx, 29h ; ')'
0x1400bee6d  mov     [rsp+170h+var_130], rsi
0x1400bee72  cmp     di, 2
0x1400bee76  mov     dword ptr [rsp+170h+var_138], r12d
0x1400bee7b  mov     r9d, 6
0x1400bee81  cmovnz  r10d, ecx
0x1400bee85  mov     rcx, [r14+30h]
0x1400bee89  mov     [rsp+170h+var_140], rcx
0x1400bee8e  movzx   ecx, [rsp+170h+var_108]
0x1400bee93  mov     word ptr [rsp+170h+var_148], cx
0x1400bee98  movzx   ecx, [rsp+170h+var_106]
0x1400bee9d  mov     word ptr [rsp+170h+var_150], cx
0x1400beea2  mov     ecx, r10d
0x1400beea5  call    _guard_dispatch_icall
0x1400beeaa  cmp     eax, 1
0x1400beead  jnz     loc_1400BF091
0x1400beeb3  xor     ebx, ebx
0x1400beeb5  test    ebx, ebx
0x1400beeb7  jnz     short loc_1400BEEBF
0x1400beeb9  cmp     [r14+2Ch], bl
0x1400beebd  jnz     short loc_1400BEEFC
0x1400beebf  mov     rcx, [rbp+70h+P+8]; P
0x1400beec3  test    rcx, rcx
0x1400beec6  jz      short loc_1400BEED9
0x1400beec8  mov     edx, 52537049h; Tag
0x1400beecd  call    cs:__imp_ExFreePoolWithTag
0x1400beed4  nop     dword ptr [rax+rax+00h]
0x1400beed9  mov     eax, ebx
0x1400beedb  mov     rcx, [rbp+70h+var_48]
  ... truncated ...
```
