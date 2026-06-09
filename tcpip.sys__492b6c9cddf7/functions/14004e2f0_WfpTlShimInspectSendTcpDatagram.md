# WfpTlShimInspectSendTcpDatagram

- ea: `0x14004e2f0`
- end: `0x14004ec42`
- name: `WfpTlShimInspectSendTcpDatagram`
- size: `2386`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004ec50`

## callees

- `0x14001b0a0`
- `0x14003b610`
- `0x14004c7d0`
- `0x14004d6e0`
- `0x14004db90`
- `0x14004dbe0`
- `0x14004e2f0`
- `0x1400505d0`
- `0x140050740`
- `0x14005079c`
- `0x1400515e8`
- `0x140052390`
- `0x1400525d0`
- `0x140053850`
- `0x140053910`
- `0x140054f00`
- `0x14007f8e0`
- `0x14008a370`
- `0x1400ec900`
- `0x1400fccf0`
- `0x1400fff20`
- `0x1401054b4`
- `0x140134740`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x14004ec02`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004e411`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004e411`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004eb3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004eb3e`
- `NETIO!KfdIsLayerEmpty` at `0x14004e3b0`
- `NETIO!KfdIsLayerEmpty` at `0x14004e836`
- `NETIO!KfdIsLayerEmpty` at `0x14004e3b0`
- `NETIO!KfdIsLayerEmpty` at `0x14004e836`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004e72c`
- `NETIO!KfdReleaseTerminatingFilters` at `0x14004e72c`
- `NETIO!KfdReleaseCachedFilters` at `0x14004e6e4`
- `NETIO!KfdReleaseCachedFilters` at `0x14004e6e4`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14004e58f`
- `NETIO!KfdAleReleaseFlowHandleForFlow` at `0x14004e58f`
- `NETIO!KfdClassify` at `0x14004e65c`
- `NETIO!KfdClassify` at `0x1401c3f05`
- `NETIO!KfdClassify` at `0x14004e65c`
- `NETIO!KfdClassify` at `0x1401c3f05`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14004e56f`
- `NETIO!KfdAleAcquireFlowHandleForFlow` at `0x14004e56f`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14004e8c7`
- `NETIO!KfdGetLayerCacheEpoch` at `0x14004e8c7`

## string_xrefs

- `0x14004ead6`: `WfpAleCopySecurityRealmIdFromEndpoint`
- `0x14004eb83`: `WfpAleCopySecurityRealmIdFromEndpoint`

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
    if ( qword_140227F18 )
    {
      v41 = 0;
      if ( v9 != 2 )
        v41 = 41;
      LOWORD(v51) = v56;
      LOWORD(v50) = v57;
      v42 = qword_140227F18(v41, *(_QWORD *)a5, *(_QWORD *)(a5 + 8), 6, v50, v51, *(_QWORD *)(a5 + 48), v39, SpinLock);
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
          HIDWORD(v36) = HIDWORD(qword_140227F10);
          if ( qword_140227F10
            && (v37 = *(_QWORD *)(a5 + 48),
                LOWORD(v58) = 0,
                v55 = 0,
                v36 = qword_140227F10(SpinLock, v37, &v58, &v55),
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
0x14004e2f0  push    rbp
0x14004e2f2  push    rbx
0x14004e2f3  push    rsi
0x14004e2f4  push    rdi
0x14004e2f5  push    r12
0x14004e2f7  push    r13
0x14004e2f9  push    r14
0x14004e2fb  push    r15
0x14004e2fd  lea     rbp, [rsp-38h]
0x14004e302  sub     rsp, 138h
0x14004e309  mov     rax, cs:__security_cookie
0x14004e310  xor     rax, rsp
0x14004e313  mov     [rbp+70h+var_48], rax
0x14004e317  mov     r14, [rbp+70h+arg_20]
0x14004e31e  xorps   xmm0, xmm0
0x14004e321  mov     rbx, [rbp+70h+arg_30]
0x14004e328  cmp     dx, 2
0x14004e32c  mov     eax, 10h
0x14004e331  mov     [rsp+170h+var_108], r9w
0x14004e337  mov     rsi, rcx
0x14004e33a  mov     [rsp+170h+var_106], r8w
0x14004e340  mov     ecx, 12h
0x14004e345  mov     [rsp+170h+var_110], dx
0x14004e34a  cmovnz  ax, cx
0x14004e34e  movzx   edi, dx
0x14004e351  xor     r12d, r12d
0x14004e354  mov     [rsp+170h+var_104], eax
0x14004e358  mov     r13d, [rsi+34h]
0x14004e35c  xor     eax, eax
0x14004e35e  and     r13d, 20000h
0x14004e365  mov     [rbp+70h+var_F0], rax
0x14004e369  mov     dword ptr [rbp+70h+var_E8], eax
0x14004e36c  setnz   r15b
0x14004e370  mov     word ptr [rbp+70h+var_E8+4], ax
0x14004e374  mov     [rbp+70h+var_C0], r12
0x14004e378  mov     [rsp+170h+var_F8], r12
0x14004e37d  mov     dword ptr [rbp+70h+var_50], eax
0x14004e380  mov     [rsp+170h+var_10C], r12d
0x14004e385  movups  xmmword ptr [rbp+70h+P], xmm0
0x14004e389  movups  [rbp+70h+var_A0], xmm0
0x14004e38d  movups  [rbp+70h+var_90], xmm0
0x14004e391  movups  [rbp+70h+var_80], xmm0
0x14004e395  movups  xmmword ptr [rbp+70h+var_70], xmm0
0x14004e399  movups  [rbp+70h+var_60], xmm0
0x14004e39d  movups  xmmword ptr [rbp+70h+var_D0], xmm0
0x14004e3a1  cmp     dx, 2
0x14004e3a5  jnz     loc_14004E836
0x14004e3ab  mov     ecx, 10h
0x14004e3b0  call    cs:__imp_KfdIsLayerEmpty
0x14004e3b7  nop     dword ptr [rax+rax+00h]
0x14004e3bc  test    eax, eax
0x14004e3be  jnz     loc_14004E84A
0x14004e3c4  mov     eax, [rsi+30h]
0x14004e3c7  bt      eax, 1Eh
0x14004e3cb  jb      loc_14004E6CD
0x14004e3d1  mov     eax, [rsi+30h]
0x14004e3d4  bt      eax, 0Bh
0x14004e3d8  jb      loc_14004E6CD
0x14004e3de  test    rbx, rbx
0x14004e3e1  jz      loc_14004EA22
0x14004e3e7  mov     r12d, [rbx]
0x14004e3ea  xor     edi, edi
0x14004e3ec  test    dword ptr [rsi+0C8h], 4000h
0x14004e3f6  mov     [rbp+70h+P+8], rdi
0x14004e3fa  mov     dword ptr [rbp+70h+P], edi
0x14004e3fd  jnz     loc_14004EAD3
0x14004e403  cmp     qword ptr [rsi+158h], 0
0x14004e40b  jnz     loc_14004E89A
0x14004e411  call    cs:__imp_KeGetCurrentIrql
0x14004e418  nop     dword ptr [rax+rax+00h]
0x14004e41d  cmp     al, 2
0x14004e41f  jnb     loc_14004EA61
0x14004e425  call    WfpRaiseIrqlToDispatchLevel
0x14004e42a  movzx   edi, al
0x14004e42d  mov     [rsp+170h+var_10D], al
0x14004e431  mov     bl, 1
0x14004e433  mov     eax, gs:1A4h
0x14004e43b  mov     [rsp+170h+var_10E], bl
0x14004e43f  lea     rdx, [rax+rax*8]
0x14004e443  mov     rax, cs:gPerProcessorContext
0x14004e44a  cmp     byte ptr [rax+rdx*8+20h], 0
0x14004e44f  jnz     loc_14004E9E1
0x14004e455  mov     r15, [rax+rdx*8+18h]
0x14004e45a  mov     rdi, [rax+rdx*8+10h]
0x14004e45f  mov     byte ptr [rax+rdx*8+20h], 1
0x14004e464  xor     edx, edx; Val
0x14004e466  mov     [rsp+170h+var_100], r15
0x14004e46b  mov     r8d, 2A0h; Size
0x14004e471  mov     rcx, r15; void *
0x14004e474  call    memset
0x14004e479  xor     edx, edx; Val
0x14004e47b  mov     r8d, 2A8h; Size
0x14004e481  mov     rcx, rdi; void *
0x14004e484  call    memset
0x14004e489  movzx   r9d, [rsp+170h+var_108]
0x14004e48f  lea     rax, [rdi+270h]
0x14004e496  movzx   r8d, [rsp+170h+var_106]
0x14004e49c  lea     rcx, [rbp+70h+P]
0x14004e4a0  mov     [rax+8], rax
0x14004e4a4  mov     edx, 6
0x14004e4a9  mov     [rax], rax
0x14004e4ac  xor     eax, eax
0x14004e4ae  cmp     [r14+2Ch], al
0x14004e4b2  mov     [rsp+170h+var_130], r15
0x14004e4b7  mov     [rsp+170h+var_138], rcx
0x14004e4bc  setnz   al
0x14004e4bf  movzx   ecx, [rsp+170h+var_110]
0x14004e4c4  mov     dword ptr [rsp+170h+var_140], eax
0x14004e4c8  mov     dword ptr [rsp+170h+var_148], r12d
0x14004e4cd  mov     [rsp+170h+var_150], r14
0x14004e4d2  call    TlShimMarshalOutTransportFields
0x14004e4d7  cmp     dword ptr [rsi+2A8h], 1
0x14004e4de  mov     ecx, [rsp+170h+var_104]
0x14004e4e2  mov     word ptr [rbp+70h+var_F0], cx
0x14004e4e6  mov     dword ptr [rbp+70h+var_F0+4], eax
0x14004e4e9  mov     [rbp+70h+var_E8], r15
0x14004e4ed  mov     [rsp+170h+var_F8], 0
0x14004e4f6  jz      loc_14004EBF6
0x14004e4fc  mov     ecx, [rdi]
0x14004e4fe  mov     eax, [rbp+70h+arg_28]
0x14004e504  bts     ecx, 0Ah
0x14004e508  mov     [rdi+2Ch], eax
0x14004e50b  test    r13d, r13d
0x14004e50e  jz      short loc_14004E514
0x14004e510  or      dword ptr [rdi+4], 8
0x14004e514  or      ecx, 880h
0x14004e51a  mov     [rdi], ecx
0x14004e51c  mov     rax, [r14]
0x14004e51f  mov     rcx, [rax+8]
0x14004e523  mov     rax, [rcx]
0x14004e526  mov     ecx, [rax]
0x14004e528  mov     [rdi+50h], ecx
0x14004e52b  mov     rcx, rsi
0x14004e52e  call    WfpAleQueryOrInsertEndpointHandle
0x14004e533  test    rax, rax
0x14004e536  jz      short loc_14004E565
0x14004e538  or      dword ptr [rdi], 8000h
0x14004e53e  mov     [rdi+70h], rax
0x14004e542  mov     rcx, [rsi+220h]
0x14004e549  test    rcx, rcx
0x14004e54c  jz      short loc_14004E565
0x14004e54e  call    WfpAleQueryOrInsertEndpointHandle
0x14004e553  test    rax, rax
0x14004e556  jz      short loc_14004E565
0x14004e558  or      dword ptr [rdi], 4000000h
0x14004e55e  mov     [rdi+0C0h], rax
0x14004e565  lea     r8, [rsp+170h+var_F8]
0x14004e56a  xor     edx, edx
0x14004e56c  mov     rcx, rsi
0x14004e56f  call    cs:__imp_KfdAleAcquireFlowHandleForFlow
0x14004e576  nop     dword ptr [rax+rax+00h]
0x14004e57b  test    rax, rax
0x14004e57e  jnz     short loc_14004E59B
0x14004e580  mov     rax, [rsp+170h+var_F8]
0x14004e585  mov     rcx, rsi
0x14004e588  or      dword ptr [rdi], 2
0x14004e58b  mov     [rdi+20h], rax
0x14004e58f  call    cs:__imp_KfdAleReleaseFlowHandleForFlow
0x14004e596  nop     dword ptr [rax+rax+00h]
0x14004e59b  mov     rbx, [r14+38h]
0x14004e59f  test    rbx, rbx
0x14004e5a2  jz      loc_14004E962
0x14004e5a8  mov     ebx, [rbx+8]
0x14004e5ab  mov     [rsp+170h+var_10C], ebx
0x14004e5af  test    ebx, ebx
0x14004e5b1  jz      short loc_14004E5FD
0x14004e5b3  cmp     [rsp+170h+var_110], 17h
0x14004e5b9  mov     r15, [r14+8]
0x14004e5bd  mov     rcx, r15; Address
0x14004e5c0  jz      loc_14004E823
0x14004e5c6  call    Ipv4AddressScope
0x14004e5cb  mov     edx, eax
0x14004e5cd  cmp     eax, 0Eh
0x14004e5d0  jnz     loc_14004E96B
0x14004e5d6  xor     ebx, ebx
0x14004e5d8  xor     ecx, ecx
0x14004e5da  mov     eax, ecx
0x14004e5dc  shr     eax, 1Ch
0x14004e5df  cmp     eax, edx
0x14004e5e1  jnz     short loc_14004E5EB
0x14004e5e3  mov     ebx, ecx
0x14004e5e5  and     ebx, 0FFFFFFFh
0x14004e5eb  mov     r15, [rsp+170h+var_100]
0x14004e5f0  test    ebx, ebx
0x14004e5f2  jz      short loc_14004E5FD
0x14004e5f4  or      dword ptr [rdi], 20000h
0x14004e5fa  mov     [rdi+78h], ebx
0x14004e5fd  lea     rax, [rbp+70h+var_A0]
0x14004e601  mov     qword ptr [rbp+70h+var_A0], rsi
0x14004e605  mov     [rdi+8], rax
0x14004e609  mov     rcx, [r14+30h]
0x14004e60d  call    FwppGetPacketInfo
0x14004e612  test    rax, rax
0x14004e615  jnz     loc_14004EC02
0x14004e61b  mov     r13d, [rsp+170h+var_104]
0x14004e620  lea     rax, [rbp+70h+var_D0]
0x14004e624  mov     [rbp+70h+var_D0+8], rax
0x14004e628  lea     rdx, [rbp+70h+var_F0]
0x14004e62c  lea     rax, [rbp+70h+var_D0]
0x14004e630  mov     r8, rdi
0x14004e633  mov     [rbp+70h+var_D0], rax
0x14004e637  movzx   ecx, r13w
0x14004e63b  lea     rax, [rbp+70h+var_D0]
0x14004e63f  mov     [rdi+200h], rax
0x14004e646  lea     rax, [rbp+70h+var_70]
0x14004e64a  mov     r9, [r14+30h]
0x14004e64e  mov     [rsp+170h+var_148], rax; __int64
0x14004e653  mov     [rsp+170h+var_150], 0
0x14004e65c  call    cs:__imp_KfdClassify
0x14004e663  nop     dword ptr [rax+rax+00h]
0x14004e668  mov     ebx, eax
0x14004e66a  mov     rax, cs:qword_140227F10
0x14004e671  test    rax, rax
0x14004e674  jz      short loc_14004E69F
0x14004e676  mov     rdx, [r14+30h]
0x14004e67a  lea     r9, [rsp+170h+var_10C]
0x14004e67f  xor     ecx, ecx
0x14004e681  lea     r8, [rsp+170h+var_104]
0x14004e686  mov     word ptr [rsp+170h+var_104], cx
0x14004e68b  mov     [rsp+170h+var_10C], ecx
0x14004e68f  mov     rcx, rsi
0x14004e692  call    _guard_dispatch_icall
0x14004e697  test    eax, eax
0x14004e699  jnz     loc_1401C3EC6
0x14004e69f  cmp     dword ptr [rdi+218h], 0
0x14004e6a6  jz      short loc_14004E6F0
0x14004e6a8  mov     r8d, [rdi+210h]
0x14004e6af  lea     rax, [rbp+70h+var_D0]
0x14004e6b3  mov     r9d, r12d
0x14004e6b6  mov     [rsp+170h+var_150], rax; __int64
0x14004e6bb  movzx   edx, r13w
0x14004e6bf  mov     rcx, rsi; SpinLock
0x14004e6c2  call    TlShimCacheMatchedFilterList
0x14004e6c7  test    eax, eax
0x14004e6c9  jns     short loc_14004E6F0
0x14004e6cb  jmp     short loc_14004E6E0
0x14004e6cd  mov     eax, 1
0x14004e6d2  jmp     loc_14004E7EB
0x14004e6d7  cmp     dword ptr [rdi+218h], 0
0x14004e6de  jz      short loc_14004E6F0
0x14004e6e0  lea     rcx, [rbp+70h+var_D0]
0x14004e6e4  call    cs:__imp_KfdReleaseCachedFilters
0x14004e6eb  nop     dword ptr [rax+rax+00h]
0x14004e6f0  mov     r15d, 1
0x14004e6f6  test    ebx, ebx
0x14004e6f8  jnz     loc_14004EC25
0x14004e6fe  cmp     dword ptr [rbp+70h+var_70], 1001h
0x14004e705  jz      loc_14004E85B
0x14004e70b  mov     r12d, r15d
0x14004e70e  mov     eax, gs:1A4h
0x14004e716  lea     rcx, [rdi+270h]
0x14004e71d  lea     rdx, [rax+rax*8]
0x14004e721  mov     rax, cs:gPerProcessorContext
0x14004e728  lea     r13, [rax+rdx*8]
0x14004e72c  call    cs:__imp_KfdReleaseTerminatingFilters
0x14004e733  nop     dword ptr [rax+rax+00h]
0x14004e738  mov     rax, [rsp+170h+var_100]
0x14004e73d  cmp     rax, [r13+18h]
0x14004e741  jnz     loc_14004E9BC
0x14004e747  mov     byte ptr [r13+20h], 0
0x14004e74c  cmp     [rsp+170h+var_10E], 0
0x14004e751  jz      short loc_14004E75D
0x14004e753  movzx   ecx, [rsp+170h+var_10D]
0x14004e758  call    WfpLowerIrqlFromDispatchLevel
0x14004e75d  movzx   edi, [rsp+170h+var_110]
0x14004e762  mov     rax, cs:qword_140227F18
0x14004e769  test    rax, rax
0x14004e76c  jz      short loc_14004E7C5
0x14004e76e  mov     r8, [r14+8]
0x14004e772  xor     r10d, r10d
0x14004e775  mov     rdx, [r14]
0x14004e778  mov     ecx, 29h ; ')'
0x14004e77d  mov     [rsp+170h+var_130], rsi
0x14004e782  cmp     di, 2
0x14004e786  mov     dword ptr [rsp+170h+var_138], r12d
0x14004e78b  mov     r9d, 6
0x14004e791  cmovnz  r10d, ecx
0x14004e795  mov     rcx, [r14+30h]
0x14004e799  mov     [rsp+170h+var_140], rcx
0x14004e79e  movzx   ecx, [rsp+170h+var_108]
0x14004e7a3  mov     word ptr [rsp+170h+var_148], cx
0x14004e7a8  movzx   ecx, [rsp+170h+var_106]
0x14004e7ad  mov     word ptr [rsp+170h+var_150], cx
0x14004e7b2  mov     ecx, r10d
0x14004e7b5  call    _guard_dispatch_icall
0x14004e7ba  cmp     eax, 1
0x14004e7bd  jnz     loc_14004E9A1
0x14004e7c3  xor     ebx, ebx
0x14004e7c5  test    ebx, ebx
0x14004e7c7  jnz     short loc_14004E7CF
0x14004e7c9  cmp     [r14+2Ch], bl
0x14004e7cd  jnz     short loc_14004E80C
0x14004e7cf  mov     rcx, [rbp+70h+P+8]; P
0x14004e7d3  test    rcx, rcx
0x14004e7d6  jz      short loc_14004E7E9
0x14004e7d8  mov     edx, 52537049h; Tag
0x14004e7dd  call    cs:__imp_ExFreePoolWithTag
0x14004e7e4  nop     dword ptr [rax+rax+00h]
0x14004e7e9  mov     eax, ebx
0x14004e7eb  mov     rcx, [rbp+70h+var_48]
  ... truncated ...
```
