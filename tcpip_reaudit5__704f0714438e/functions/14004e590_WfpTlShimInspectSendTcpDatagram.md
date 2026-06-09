# WfpTlShimInspectSendTcpDatagram

- ea: `0x14004e590`
- end: `0x14004eee2`
- name: `WfpTlShimInspectSendTcpDatagram`
- size: `2386`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004eef0`

## callees

- `0x14001b340`
- `0x14003b8b0`
- `0x14004ca70`
- `0x14004d980`
- `0x14004de30`
- `0x14004de80`
- `0x14004e590`
- `0x140050870`
- `0x1400509e0`
- `0x140050a3c`
- `0x140051888`
- `0x140052630`
- `0x140052870`
- `0x140053af0`
- `0x140053bb0`
- `0x1400551a0`
- `0x140080790`
- `0x14008b220`
- `0x1400ec7f0`
- `0x1400fce30`
- `0x1400fff40`
- `0x1401054d4`
- `0x140134880`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x14004eea2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004e6b1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004e6b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004edde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004edde`
- `NETIO!KfdIsLayerEmpty` at `0x14004e650`
- `NETIO!KfdIsLayerEmpty` at `0x14004ead6`
- `NETIO!KfdIsLayerEmpty` at `0x14004e650`
- `NETIO!KfdIsLayerEmpty` at `0x14004ead6`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004e9cc`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004e9cc`
- `NETIO!KfdReleaseCachedFilters` at `0x14004e984`
- `NETIO!KfdReleaseCachedFilters` at `0x14004e984`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14004e82f`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14004e82f`
- `NETIO!KfdClassify` at `0x14004e8fc`
- `NETIO!KfdClassify` at `0x1401c4045`
- `NETIO!KfdClassify` at `0x14004e8fc`
- `NETIO!KfdClassify` at `0x1401c4045`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14004e80f`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14004e80f`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14004eb67`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14004eb67`

## string_xrefs

- `0x14004ed76`: `WfpAleCopySecurityRealmIdFromEndpoint`
- `0x14004ee23`: `WfpAleCopySecurityRealmIdFromEndpoint`

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
  __int64 v36; // rax
  __int64 v37; // rdx
  int v39; // r12d
  char *v40; // r13
  unsigned int v41; // r10d
  int v42; // eax
  __int64 v43; // rdi
  _DWORD *v44; // rcx
  int v45; // eax
  __int64 v46; // r12
  int v47; // edx
  __int64 v48; // rax
  __int64 v49; // rbx
  int v50; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+28h] [rbp-D8h]
  char v53; // [rsp+62h] [rbp-9Eh]
  unsigned __int8 v54; // [rsp+63h] [rbp-9Dh]
  int v55; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v56; // [rsp+68h] [rbp-98h]
  unsigned __int16 v57; // [rsp+6Ah] [rbp-96h]
  int v58; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  int *v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h]
  PVOID P[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v64[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-50h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v67[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v68[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+120h] [rbp+20h]

  v7 = 16;
  v56 = a4;
  v57 = a3;
  if ( a2 != 2 )
    LOWORD(v7) = 18;
  v9 = a2;
  v58 = v7;
  v10 = (SpinLock[13] & 0x20000) == 0;
  v11 = SpinLock[13] & 0x20000;
  v61 = 0;
  LODWORD(v62) = 0;
  v12 = !v10;
  WORD2(v62) = 0;
  v65 = 0;
  v60 = 0;
  LODWORD(v70) = 0;
  v55 = 0;
  *(_OWORD *)P = 0;
  memset(v67, 0, sizeof(v67));
  *(_OWORD *)v68 = 0;
  v69 = 0;
  *(_OWORD *)v64 = 0;
  if ( a2 != 2 )
  {
    if ( !(unsigned int)KfdIsLayerEmpty(18) )
      goto LABEL_5;
LABEL_64:
    v35 = 0;
    v39 = 1;
LABEL_51:
    if ( qword_140227E98 )
    {
      v41 = 0;
      if ( v9 != 2 )
        v41 = 41;
      LOWORD(v51) = v56;
      LOWORD(v50) = v57;
      v42 = qword_140227E98(v41, *(_QWORD *)a5, *(_QWORD *)(a5 + 8), 6, v50, v51, *(_QWORD *)(a5 + 48), v39, SpinLock);
      if ( v42 != 1 )
      {
        if ( v42 )
        {
          v45 = v42 - 2;
          if ( !v45 )
          {
            v35 = 3;
            goto LABEL_56;
          }
          if ( v45 == 1 )
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
      v48 = WfpBufferCopy(*((void **)SpinLock + 34), (unsigned int)SpinLock[66]);
      LODWORD(P[0]) = SpinLock[66];
      v49 = v48;
      AleReleaseEndpointLock(SpinLock, &LockHandle);
      if ( v49 )
      {
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
            v49);
        }
      }
    }
LABEL_9:
    if ( !*((_QWORD *)SpinLock + 43) )
      goto LABEL_10;
    v59 = TlShimLookupLayerCache((PKSPIN_LOCK)SpinLock);
    v43 = v59;
    if ( !v59 )
      goto LABEL_10;
    KfdGetLayerCacheEpoch((unsigned __int16)v58, SpinLock + 90);
    v44 = SpinLock;
    if ( SpinLock[90] != *(_DWORD *)(v59 + 44) )
    {
LABEL_71:
      TlShimPurgeLayerCache(v44, v43);
      TlShimReleaseLayerCache(&v59);
LABEL_10:
      if ( KeGetCurrentIrql() >= 2u )
      {
        v15 = 0;
        v54 = 0;
        v16 = 0;
      }
      else
      {
        v14 = WfpRaiseIrqlToDispatchLevel();
        v15 = v14;
        v54 = v14;
        v16 = 1;
      }
      LODWORD(v14) = HIDWORD(KeGetPcr()[1].LockArray);
      v53 = v16;
      if ( !*((_BYTE *)gPerProcessorContext + 72 * v14 + 32) )
      {
        v17 = *((_QWORD *)gPerProcessorContext + 9 * v14 + 3);
        v18 = (int *)*((_QWORD *)gPerProcessorContext + 9 * v14 + 2);
        *((_BYTE *)gPerProcessorContext + 72 * v14 + 32) = 1;
        goto LABEL_14;
      }
      if ( !WfpAllocateFromPerProcessorLookasideList(gIncomingValuesLookasideList, &v65) )
      {
        if ( !WfpAllocateFromPerProcessorLookasideList(gMetadataLookasideList, &v60) )
        {
          v17 = v65;
          v18 = v60;
LABEL_14:
          v59 = v17;
          memset((void *)v17, 0, 0x2A0u);
          memset(v18, 0, 0x2A8u);
          v19 = v56;
          v20 = v57;
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
          LOWORD(v61) = v58;
          HIDWORD(v61) = v21;
          v62 = v17;
          v60 = 0;
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
          if ( !KfdAleAcquireFlowHandleForFlow(SpinLock, 0, &v60) )
          {
            v26 = v60;
            *v18 |= 2u;
            *((_QWORD *)v18 + 4) = v26;
            KfdAleReleaseFlowHandleForFlow(SpinLock);
          }
          v27 = *(_QWORD *)(a5 + 56);
          if ( v27 )
          {
            v28 = *(_DWORD *)(v27 + 8);
            v55 = v28;
            if ( !v28 )
              goto LABEL_34;
            v29 = *(const UCHAR **)(a5 + 8);
            if ( a2 == 23 )
            {
              IN6_UNCANONICALIZE_SCOPE_ID(v29, &v55);
              v28 = v55;
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
            v17 = v59;
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
          *(_QWORD *)&v67[0] = SpinLock;
          *((_QWORD *)v18 + 1) = v67;
          PacketInfo = (_OWORD *)FwppGetPacketInfo(*(_QWORD *)(a5 + 48));
          if ( PacketInfo && PacketInfo != MmBadPointer )
            *((_OWORD *)v18 + 23) = PacketInfo[22];
          v33 = v58;
          v64[1] = (__int64)v64;
          v64[0] = (__int64)v64;
          v34 = (unsigned __int16)v58;
          *((_QWORD *)v18 + 64) = v64;
          v35 = KfdClassify(v34, &v61, v18, *(_QWORD *)(a5 + 48), 0, v68);
          HIDWORD(v36) = HIDWORD(qword_140227E90);
          if ( qword_140227E90
            && (v37 = *(_QWORD *)(a5 + 48),
                LOWORD(v58) = 0,
                v55 = 0,
                v36 = qword_140227E90(SpinLock, v37, &v58, &v55),
                (_DWORD)v36) )
          {
            *(_DWORD *)(v17 + 168) = v55;
            *(_WORD *)(v17 + 88) = __ROR2__(v58, 8);
            *((_QWORD *)v18 + 64) = 0;
            v36 = KfdClassify(v33, &v61, v18, *(_QWORD *)(a5 + 48), 0, v68);
            v35 = v36;
            if ( v18[134] )
              goto LABEL_42;
          }
          else if ( v18[134] )
          {
            v36 = TlShimCacheMatchedFilterList((PKSPIN_LOCK)SpinLock, (__int64)v64, v51);
            if ( (int)v36 < 0 )
LABEL_42:
              v36 = KfdReleaseCachedFilters(v64);
          }
          if ( v35 )
          {
            HIDWORD(v36) = 0;
            *(_OWORD *)v68 = 0;
            LODWORD(v68[0]) = 4097;
            v69 = 0;
            v70 = 0;
          }
          else if ( LODWORD(v68[0]) != 4097 )
          {
            v39 = 1;
LABEL_46:
            LODWORD(v36) = HIDWORD(KeGetPcr()[1].LockArray);
            v40 = (char *)gPerProcessorContext + 72 * v36;
            KfdReleaseTerminatingFilters(v18 + 156);
            if ( v59 == *((_QWORD *)v40 + 3) )
            {
              v40[32] = 0;
            }
            else
            {
              PplFreeToLookasideList(gMetadataLookasideList);
              PplFreeToLookasideList(gIncomingValuesLookasideList);
            }
            if ( v53 )
              WfpLowerIrqlFromDispatchLevel(v54);
            goto LABEL_50;
          }
          if ( (BYTE12(v69) & 1) != 0 )
          {
            v35 = 3;
            v39 = 2;
          }
          else
          {
            *((_QWORD *)v18 + 64) = 0;
            v39 = 0;
            v36 = WfpShimIndicateDiscardGeneral(
                    v33,
                    (unsigned int)&v61,
                    (_DWORD)v18,
                    *(_QWORD *)(a5 + 48),
                    0,
                    (__int64)v68);
            v35 = 1;
          }
          goto LABEL_46;
        }
        PplFreeToLookasideList(gIncomingValuesLookasideList);
      }
      if ( v16 )
        WfpLowerIrqlFromDispatchLevel(v15);
      v35 = 1;
      goto LABEL_59;
    }
    if ( !TlShimDirectClassify((KSPIN_LOCK *)SpinLock, a2, v59, 6, v57, v56, 0, a5, a6, 0, v12, &v55) )
    {
      v44 = SpinLock;
      goto LABEL_71;
    }
    v39 = v55;
    if ( v55 == 1 )
    {
      v35 = 0;
      TlShimReleaseLayerCache(&v59);
LABEL_50:
      v9 = a2;
      goto LABEL_51;
    }
    if ( v55 )
    {
      if ( v55 == 2 )
      {
        v35 = 3;
        TlShimReleaseLayerCache(&v59);
        goto LABEL_50;
      }
      if ( v55 == 3 )
      {
        v35 = 2;
        TlShimReleaseLayerCache(&v59);
        goto LABEL_50;
      }
    }
    v35 = 1;
    TlShimReleaseLayerCache(&v59);
    goto LABEL_50;
  }
  v46 = *(_QWORD *)(a5 + 32);
  if ( *(_DWORD *)(*(_QWORD *)(v46 + 48) + 12LL) != 131 )
  {
    ProfileIdFromInterface = *(_DWORD *)(v46 + 56);
    goto LABEL_9;
  }
  if ( (unsigned int)TlShimDiscoverPhysicalNexthopInterface(SpinLock, v9, 6, a5) != 259 )
  {
    ProfileIdFromInterface = WfpGetProfileIdFromInterface(
                               *(_QWORD *)(a5 + 32),
                               v47,
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
0x14004e590  push    rbp
0x14004e592  push    rbx
0x14004e593  push    rsi
0x14004e594  push    rdi
0x14004e595  push    r12
0x14004e597  push    r13
0x14004e599  push    r14
0x14004e59b  push    r15
0x14004e59d  lea     rbp, [rsp-38h]
0x14004e5a2  sub     rsp, 138h
0x14004e5a9  mov     rax, cs:__security_cookie
0x14004e5b0  xor     rax, rsp
0x14004e5b3  mov     [rbp+70h+var_48], rax
0x14004e5b7  mov     r14, [rbp+70h+arg_20]
0x14004e5be  xorps   xmm0, xmm0
0x14004e5c1  mov     rbx, [rbp+70h+arg_30]
0x14004e5c8  cmp     dx, 2
0x14004e5cc  mov     eax, 10h
0x14004e5d1  mov     [rsp+170h+var_108], r9w
0x14004e5d7  mov     rsi, rcx
0x14004e5da  mov     [rsp+170h+var_106], r8w
0x14004e5e0  mov     ecx, 12h
0x14004e5e5  mov     [rsp+170h+var_110], dx
0x14004e5ea  cmovnz  ax, cx
0x14004e5ee  movzx   edi, dx
0x14004e5f1  xor     r12d, r12d
0x14004e5f4  mov     [rsp+170h+var_104], eax
0x14004e5f8  mov     r13d, [rsi+34h]
0x14004e5fc  xor     eax, eax
0x14004e5fe  and     r13d, 20000h
0x14004e605  mov     [rbp+70h+var_F0], rax
0x14004e609  mov     dword ptr [rbp+70h+var_E8], eax
0x14004e60c  setnz   r15b
0x14004e610  mov     word ptr [rbp+70h+var_E8+4], ax
0x14004e614  mov     [rbp+70h+var_C0], r12
0x14004e618  mov     [rsp+170h+var_F8], r12
0x14004e61d  mov     dword ptr [rbp+70h+var_50], eax
0x14004e620  mov     [rsp+170h+var_10C], r12d
0x14004e625  movups  xmmword ptr [rbp+70h+P], xmm0
0x14004e629  movups  [rbp+70h+var_A0], xmm0
0x14004e62d  movups  [rbp+70h+var_90], xmm0
0x14004e631  movups  [rbp+70h+var_80], xmm0
0x14004e635  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x14004e639  movups  [rbp+70h+var_60], xmm0
0x14004e63d  movups  xmmword ptr [rbp+70h+var_D0], xmm0
0x14004e641  cmp     dx, 2
0x14004e645  jnz     loc_14004EAD6
0x14004e64b  mov     ecx, 10h
0x14004e650  call    cs:__imp_KfdIsLayerEmpty
0x14004e657  nop     dword ptr [rax+rax+00h]
0x14004e65c  test    eax, eax
0x14004e65e  jnz     loc_14004EAEA
0x14004e664  mov     eax, [rsi+30h]
0x14004e667  bt      eax, 1Eh
0x14004e66b  jb      loc_14004E96D
0x14004e671  mov     eax, [rsi+30h]
0x14004e674  bt      eax, 0Bh
0x14004e678  jb      loc_14004E96D
0x14004e67e  test    rbx, rbx
0x14004e681  jz      loc_14004ECC2
0x14004e687  mov     r12d, [rbx]
0x14004e68a  xor     edi, edi
0x14004e68c  test    dword ptr [rsi+0C8h], 4000h
0x14004e696  mov     [rbp+70h+P+8], rdi
0x14004e69a  mov     dword ptr [rbp+70h+P], edi
0x14004e69d  jnz     loc_14004ED73
0x14004e6a3  cmp     qword ptr [rsi+158h], 0
0x14004e6ab  jnz     loc_14004EB3A
0x14004e6b1  call    cs:__imp_KeGetCurrentIrql
0x14004e6b8  nop     dword ptr [rax+rax+00h]
0x14004e6bd  cmp     al, 2
0x14004e6bf  jnb     loc_14004ED01
0x14004e6c5  call    WfpRaiseIrqlToDispatchLevel
0x14004e6ca  movzx   edi, al
0x14004e6cd  mov     [rsp+170h+var_10D], al
0x14004e6d1  mov     bl, 1
0x14004e6d3  mov     eax, gs:1A4h
0x14004e6db  mov     [rsp+170h+var_10E], bl
0x14004e6df  lea     rdx, [rax+rax*8]
0x14004e6e3  mov     rax, cs:gPerProcessorContext
0x14004e6ea  cmp     byte ptr [rax+rdx*8+20h], 0
0x14004e6ef  jnz     loc_14004EC81
0x14004e6f5  mov     r15, [rax+rdx*8+18h]
0x14004e6fa  mov     rdi, [rax+rdx*8+10h]
0x14004e6ff  mov     byte ptr [rax+rdx*8+20h], 1
0x14004e704  xor     edx, edx; Val
0x14004e706  mov     [rsp+170h+var_100], r15
0x14004e70b  mov     r8d, 2A0h; Size
0x14004e711  mov     rcx, r15; void *
0x14004e714  call    memset
0x14004e719  xor     edx, edx; Val
0x14004e71b  mov     r8d, 2A8h; Size
0x14004e721  mov     rcx, rdi; void *
0x14004e724  call    memset
0x14004e729  movzx   r9d, [rsp+170h+var_108]
0x14004e72f  lea     rax, [rdi+270h]
0x14004e736  movzx   r8d, [rsp+170h+var_106]
0x14004e73c  lea     rcx, [rbp+70h+P]
0x14004e740  mov     [rax+8], rax
0x14004e744  mov     edx, 6
0x14004e749  mov     [rax], rax
0x14004e74c  xor     eax, eax
0x14004e74e  cmp     [r14+2Ch], al
0x14004e752  mov     [rsp+170h+var_130], r15
0x14004e757  mov     [rsp+170h+var_138], rcx
0x14004e75c  setnz   al
0x14004e75f  movzx   ecx, [rsp+170h+var_110]
0x14004e764  mov     dword ptr [rsp+170h+var_140], eax
0x14004e768  mov     dword ptr [rsp+170h+var_148], r12d
0x14004e76d  mov     [rsp+170h+var_150], r14
0x14004e772  call    TlShimMarshalOutTransportFields
0x14004e777  cmp     dword ptr [rsi+2A8h], 1
0x14004e77e  mov     ecx, [rsp+170h+var_104]
0x14004e782  mov     word ptr [rbp+70h+var_F0], cx
0x14004e786  mov     dword ptr [rbp+70h+var_F0+4], eax
0x14004e789  mov     [rbp+70h+var_E8], r15
0x14004e78d  mov     [rsp+170h+var_F8], 0
0x14004e796  jz      loc_14004EE96
0x14004e79c  mov     ecx, [rdi]
0x14004e79e  mov     eax, [rbp+70h+arg_28]
0x14004e7a4  bts     ecx, 0Ah
0x14004e7a8  mov     [rdi+2Ch], eax
0x14004e7ab  test    r13d, r13d
0x14004e7ae  jz      short loc_14004E7B4
0x14004e7b0  or      dword ptr [rdi+4], 8
0x14004e7b4  or      ecx, 880h
0x14004e7ba  mov     [rdi], ecx
0x14004e7bc  mov     rax, [r14]
0x14004e7bf  mov     rcx, [rax+8]
0x14004e7c3  mov     rax, [rcx]
0x14004e7c6  mov     ecx, [rax]
0x14004e7c8  mov     [rdi+50h], ecx
0x14004e7cb  mov     rcx, rsi
0x14004e7ce  call    WfpAleQueryOrInsertEndpointHandle
0x14004e7d3  test    rax, rax
0x14004e7d6  jz      short loc_14004E805
0x14004e7d8  or      dword ptr [rdi], 8000h
0x14004e7de  mov     [rdi+70h], rax
0x14004e7e2  mov     rcx, [rsi+220h]
0x14004e7e9  test    rcx, rcx
0x14004e7ec  jz      short loc_14004E805
0x14004e7ee  call    WfpAleQueryOrInsertEndpointHandle
0x14004e7f3  test    rax, rax
0x14004e7f6  jz      short loc_14004E805
0x14004e7f8  or      dword ptr [rdi], 4000000h
0x14004e7fe  mov     [rdi+0C0h], rax
0x14004e805  lea     r8, [rsp+170h+var_F8]
0x14004e80a  xor     edx, edx
0x14004e80c  mov     rcx, rsi
0x14004e80f  call    cs:__imp_KfdAleAcquireFlowHandleForFlow
0x14004e816  nop     dword ptr [rax+rax+00h]
0x14004e81b  test    rax, rax
0x14004e81e  jnz     short loc_14004E83B
0x14004e820  mov     rax, [rsp+170h+var_F8]
0x14004e825  mov     rcx, rsi
0x14004e828  or      dword ptr [rdi], 2
0x14004e82b  mov     [rdi+20h], rax
0x14004e82f  call    cs:__imp_KfdAleReleaseFlowHandleForFlow
0x14004e836  nop     dword ptr [rax+rax+00h]
0x14004e83b  mov     rbx, [r14+38h]
0x14004e83f  test    rbx, rbx
0x14004e842  jz      loc_14004EC02
0x14004e848  mov     ebx, [rbx+8]
0x14004e84b  mov     [rsp+170h+var_10C], ebx
0x14004e84f  test    ebx, ebx
0x14004e851  jz      short loc_14004E89D
0x14004e853  cmp     [rsp+170h+var_110], 17h
0x14004e859  mov     r15, [r14+8]
0x14004e85d  mov     rcx, r15; Address
0x14004e860  jz      loc_14004EAC3
0x14004e866  call    Ipv4AddressScope
0x14004e86b  mov     edx, eax
0x14004e86d  cmp     eax, 0Eh
0x14004e870  jnz     loc_14004EC0B
0x14004e876  xor     ebx, ebx
0x14004e878  xor     ecx, ecx
0x14004e87a  mov     eax, ecx
0x14004e87c  shr     eax, 1Ch
0x14004e87f  cmp     eax, edx
0x14004e881  jnz     short loc_14004E88B
0x14004e883  mov     ebx, ecx
0x14004e885  and     ebx, 0FFFFFFFh
0x14004e88b  mov     r15, [rsp+170h+var_100]
0x14004e890  test    ebx, ebx
0x14004e892  jz      short loc_14004E89D
0x14004e894  or      dword ptr [rdi], 20000h
0x14004e89a  mov     [rdi+78h], ebx
0x14004e89d  lea     rax, [rbp+70h+var_A0]
0x14004e8a1  mov     qword ptr [rbp+70h+var_A0], rsi
0x14004e8a5  mov     [rdi+8], rax
0x14004e8a9  mov     rcx, [r14+30h]
0x14004e8ad  call    FwppGetPacketInfo
0x14004e8b2  test    rax, rax
0x14004e8b5  jnz     loc_14004EEA2
0x14004e8bb  mov     r13d, [rsp+170h+var_104]
0x14004e8c0  lea     rax, [rbp+70h+var_D0]
0x14004e8c4  mov     [rbp+70h+var_D0+8], rax
0x14004e8c8  lea     rdx, [rbp+70h+var_F0]
0x14004e8cc  lea     rax, [rbp+70h+var_D0]
0x14004e8d0  mov     r8, rdi
0x14004e8d3  mov     [rbp+70h+var_D0], rax
0x14004e8d7  movzx   ecx, r13w
0x14004e8db  lea     rax, [rbp+70h+var_D0]
0x14004e8df  mov     [rdi+200h], rax
0x14004e8e6  lea     rax, [rbp+70h+var_70]
0x14004e8ea  mov     r9, [r14+30h]
0x14004e8ee  mov     [rsp+170h+var_148], rax; __int64
0x14004e8f3  mov     [rsp+170h+var_150], 0
0x14004e8fc  call    cs:__imp_KfdClassify
0x14004e903  nop     dword ptr [rax+rax+00h]
0x14004e908  mov     ebx, eax
0x14004e90a  mov     rax, cs:qword_140227E90
0x14004e911  test    rax, rax
0x14004e914  jz      short loc_14004E93F
0x14004e916  mov     rdx, [r14+30h]
0x14004e91a  lea     r9, [rsp+170h+var_10C]
0x14004e91f  xor     ecx, ecx
0x14004e921  lea     r8, [rsp+170h+var_104]
0x14004e926  mov     word ptr [rsp+170h+var_104], cx
0x14004e92b  mov     [rsp+170h+var_10C], ecx
0x14004e92f  mov     rcx, rsi
0x14004e932  call    _guard_dispatch_icall
0x14004e937  test    eax, eax
0x14004e939  jnz     loc_1401C4006
0x14004e93f  cmp     dword ptr [rdi+218h], 0
0x14004e946  jz      short loc_14004E990
0x14004e948  mov     r8d, [rdi+210h]
0x14004e94f  lea     rax, [rbp+70h+var_D0]
0x14004e953  mov     r9d, r12d
0x14004e956  mov     [rsp+170h+var_150], rax; __int64
0x14004e95b  movzx   edx, r13w
0x14004e95f  mov     rcx, rsi; SpinLock
0x14004e962  call    TlShimCacheMatchedFilterList
0x14004e967  test    eax, eax
0x14004e969  jns     short loc_14004E990
0x14004e96b  jmp     short loc_14004E980
0x14004e96d  mov     eax, 1
0x14004e972  jmp     loc_14004EA8B
0x14004e977  cmp     dword ptr [rdi+218h], 0
0x14004e97e  jz      short loc_14004E990
0x14004e980  lea     rcx, [rbp+70h+var_D0]
0x14004e984  call    cs:__imp_KfdReleaseCachedFilters
0x14004e98b  nop     dword ptr [rax+rax+00h]
0x14004e990  mov     r15d, 1
0x14004e996  test    ebx, ebx
0x14004e998  jnz     loc_14004EEC5
0x14004e99e  cmp     dword ptr [rbp+70h+var_70], 1001h
0x14004e9a5  jz      loc_14004EAFB
0x14004e9ab  mov     r12d, r15d
0x14004e9ae  mov     eax, gs:1A4h
0x14004e9b6  lea     rcx, [rdi+270h]
0x14004e9bd  lea     rdx, [rax+rax*8]
0x14004e9c1  mov     rax, cs:gPerProcessorContext
0x14004e9c8  lea     r13, [rax+rdx*8]
0x14004e9cc  call    cs:__imp_KfdReleaseTerminatingFilters
0x14004e9d3  nop     dword ptr [rax+rax+00h]
0x14004e9d8  mov     rax, [rsp+170h+var_100]
0x14004e9dd  cmp     rax, [r13+18h]
0x14004e9e1  jnz     loc_14004EC5C
0x14004e9e7  mov     byte ptr [r13+20h], 0
0x14004e9ec  cmp     [rsp+170h+var_10E], 0
0x14004e9f1  jz      short loc_14004E9FD
0x14004e9f3  movzx   ecx, [rsp+170h+var_10D]
0x14004e9f8  call    WfpLowerIrqlFromDispatchLevel
0x14004e9fd  movzx   edi, [rsp+170h+var_110]
0x14004ea02  mov     rax, cs:qword_140227E98
0x14004ea09  test    rax, rax
0x14004ea0c  jz      short loc_14004EA65
0x14004ea0e  mov     r8, [r14+8]
0x14004ea12  xor     r10d, r10d
0x14004ea15  mov     rdx, [r14]
0x14004ea18  mov     ecx, 29h ; ')'
0x14004ea1d  mov     [rsp+170h+var_130], rsi
0x14004ea22  cmp     di, 2
0x14004ea26  mov     dword ptr [rsp+170h+var_138], r12d
0x14004ea2b  mov     r9d, 6
0x14004ea31  cmovnz  r10d, ecx
0x14004ea35  mov     rcx, [r14+30h]
0x14004ea39  mov     [rsp+170h+var_140], rcx
0x14004ea3e  movzx   ecx, [rsp+170h+var_108]
0x14004ea43  mov     word ptr [rsp+170h+var_148], cx
0x14004ea48  movzx   ecx, [rsp+170h+var_106]
0x14004ea4d  mov     word ptr [rsp+170h+var_150], cx
0x14004ea52  mov     ecx, r10d
0x14004ea55  call    _guard_dispatch_icall
0x14004ea5a  cmp     eax, 1
0x14004ea5d  jnz     loc_14004EC41
0x14004ea63  xor     ebx, ebx
0x14004ea65  test    ebx, ebx
0x14004ea67  jnz     short loc_14004EA6F
0x14004ea69  cmp     [r14+2Ch], bl
0x14004ea6d  jnz     short loc_14004EAAC
0x14004ea6f  mov     rcx, [rbp+70h+P+8]; P
0x14004ea73  test    rcx, rcx
0x14004ea76  jz      short loc_14004EA89
0x14004ea78  mov     edx, 52537049h; Tag
0x14004ea7d  call    cs:__imp_ExFreePoolWithTag
0x14004ea84  nop     dword ptr [rax+rax+00h]
0x14004ea89  mov     eax, ebx
0x14004ea8b  mov     rcx, [rbp+70h+var_48]
  ... truncated ...
```
