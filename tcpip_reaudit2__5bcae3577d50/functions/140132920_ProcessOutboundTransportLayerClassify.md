# ProcessOutboundTransportLayerClassify

- ea: `0x140132920`
- end: `0x14013379d`
- name: `ProcessOutboundTransportLayerClassify`
- size: `3709`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, int, __int16, __int16, __int16, __int64, __int64, char, __int64, __int64, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140050c94`

## callees

- `0x14004ca70`
- `0x140050750`
- `0x1400851f0`
- `0x1400fff40`
- `0x140132920`
- `0x1401506cc`
- `0x140150824`
- `0x1401bf4d0`
- `0x140260c08`
- `0x14026e4e8`
- `0x14026e6b4`
- `0x14026e6d4`
- `0x14026fac4`
- `0x140274b90`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140132a28`
- `ntoskrnl!MmBadPointer` at `0x140132a3d`
- `ntoskrnl!MmBadPointer` at `0x14013340e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140133717`
- `ntoskrnl!ExFreePoolWithTag` at `0x140133717`
- `NETIO!WfpNblInfoGet` at `0x140132a14`
- `NETIO!WfpNblInfoGet` at `0x1401333fd`
- `NETIO!WfpNblInfoGet` at `0x140132a14`
- `NETIO!WfpNblInfoGet` at `0x1401333fd`
- `NETIO!KfdReleaseCachedFilters` at `0x140133540`
- `NETIO!KfdReleaseCachedFilters` at `0x1401335ca`
- `NETIO!KfdReleaseCachedFilters` at `0x1401335e6`
- `NETIO!KfdReleaseCachedFilters` at `0x140133540`
- `NETIO!KfdReleaseCachedFilters` at `0x1401335ca`
- `NETIO!KfdReleaseCachedFilters` at `0x1401335e6`
- `NETIO!KfdClassify` at `0x14013336f`
- `NETIO!KfdClassify` at `0x1401334db`
- `NETIO!KfdClassify` at `0x14013336f`
- `NETIO!KfdClassify` at `0x1401334db`

## pseudocode

```c
__int64 __fastcall ProcessOutboundTransportLayerClassify(
        _DWORD *SpinLock,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        int a6,
        __int16 a7,
        __int16 a8,
        __int16 a9,
        __int64 a10,
        unsigned int *a11,
        char a12,
        __int64 a13,
        __int64 a14,
        int a15,
        int a16,
        int a17,
        int a18,
        int a19,
        int a20,
        int a21)
{
  int v24; // ebx
  _QWORD *v25; // rax
  PVOID v26; // rdx
  _OWORD *v27; // r8
  _OWORD *v28; // rax
  _DWORD *v29; // rdx
  int v30; // r12d
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rax
  unsigned int *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned int *v46; // rax
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // edx
  __int64 v53; // rcx
  int v54; // r8d
  int v55; // r13d
  KSPIN_LOCK v56; // r14
  __int64 v57; // rcx
  char v58; // al
  __int64 v59; // r13
  _QWORD *v60; // rax
  PVOID v61; // rcx
  _DWORD *v62; // rax
  unsigned __int16 v63; // r14
  KSPIN_LOCK v64; // rbx
  __int64 v65; // rcx
  __int16 RemoteWirePortFromNsConnEntry; // bx
  __int64 v67; // rcx
  _DWORD *v68; // rcx
  int v69; // ebx
  __int64 v70; // r13
  int v71; // ecx
  unsigned int v72; // eax
  int v73; // edx
  int v74; // r8d
  PVOID v75; // rcx
  unsigned int v76; // ebx
  __int64 v78; // [rsp+28h] [rbp-D1h]
  __int16 v79; // [rsp+50h] [rbp-A9h] BYREF
  char v80; // [rsp+52h] [rbp-A7h]
  unsigned int *v81; // [rsp+58h] [rbp-A1h]
  KSPIN_LOCK v82; // [rsp+60h] [rbp-99h] BYREF
  _WORD v83[2]; // [rsp+68h] [rbp-91h] BYREF
  int v84; // [rsp+6Ch] [rbp-8Dh]
  _DWORD *v85; // [rsp+70h] [rbp-89h]
  __int64 v86; // [rsp+78h] [rbp-81h]
  _QWORD v87[2]; // [rsp+80h] [rbp-79h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-69h] BYREF
  _DWORD *v89; // [rsp+A0h] [rbp-59h] BYREF
  __int128 v90; // [rsp+A8h] [rbp-51h]
  __int128 v91; // [rsp+B8h] [rbp-41h]
  __int64 v92; // [rsp+C8h] [rbp-31h]
  __int64 v93[2]; // [rsp+D0h] [rbp-29h] BYREF
  __int128 v94; // [rsp+E0h] [rbp-19h]
  __int64 v95; // [rsp+F0h] [rbp-9h]

  v81 = a11;
  v86 = a14;
  v83[1] = 0;
  LODWORD(v95) = 0;
  v92 = 0;
  v87[1] = v87;
  v87[0] = v87;
  *(_QWORD *)(a3 + 8) = &v89;
  v83[0] = a5;
  v85 = a2;
  v84 = 16;
  v89 = SpinLock;
  *(_OWORD *)v93 = 0;
  v94 = 0;
  v90 = 0;
  v91 = 0;
  *(_OWORD *)P = 0;
  if ( a4 )
    *(_QWORD *)(a3 + 384) = a4;
  if ( SpinLock && (SpinLock[10] == 6 && (SpinLock[12] & 0x10) == 0 || !*((_BYTE *)SpinLock + 618)) )
    *(_QWORD *)(a3 + 512) = v87;
  v24 = a21 | 1;
  if ( !a15 )
    v24 = a21;
  v25 = (_QWORD *)WfpNblInfoGet(a14);
  v26 = v25;
  if ( !v25 || (v27 = MmBadPointer, v25 == MmBadPointer) )
  {
    v28 = MmBadPointer;
    if ( v26 != MmBadPointer )
      goto LABEL_18;
    v27 = MmBadPointer;
  }
  else
  {
    v28 = (_OWORD *)v25[1];
  }
  if ( v28 && v28 != v27 )
    *(_OWORD *)(a3 + 368) = v28[22];
LABEL_18:
  WfpAleCopySecurityRealmIdFromEndpoint((PKSPIN_LOCK)SpinLock);
  if ( a5 > 0x47u )
    goto LABEL_103;
  v29 = v85;
  v30 = 2;
  switch ( a5 )
  {
    case 0u:
      *((_BYTE *)v85 + 40) = *(_BYTE *)(a10 + 24);
      v29[8] = 1;
      v45 = *(_QWORD *)(a10 + 8);
      v29[12] = 4;
      *((_QWORD *)v29 + 7) = v45 + 16;
      v29[18] = a17;
      v29[22] = a18;
      v29[30] = a19;
      v29[34] = a20;
      v29[16] = 3;
      v29[20] = 3;
      v29[28] = 3;
      v29[32] = 3;
      v29[24] = 3;
      v29[26] = v24;
      v29[2] = _byteswap_ulong(***(_DWORD ***)(a10 + 16));
      v46 = v81;
      *v29 = 3;
      v29[6] = _byteswap_ulong(*v46);
      v29[4] = 3;
      goto LABEL_28;
    case 2u:
      v85[18] = a17;
      v29[22] = a18;
      v29[30] = a19;
      v29[34] = a20;
      v29[16] = 3;
      v29[20] = 3;
      v29[28] = 3;
      v29[32] = 3;
      v29[24] = 3;
      v29[26] = v24;
      *((_BYTE *)v29 + 40) = *(_BYTE *)(a10 + 24);
      v29[8] = 1;
      v47 = *(_QWORD *)(a10 + 8);
      v29[12] = 4;
      *((_QWORD *)v29 + 7) = v47 + 16;
      v48 = **(_QWORD **)(a10 + 16);
      *((_QWORD *)v29 + 3) = v81;
      *v29 = 11;
      *((_QWORD *)v29 + 1) = v48;
      v29[4] = 11;
      goto LABEL_28;
    case 4u:
      *((_BYTE *)v85 + 24) = *(_BYTE *)(a10 + 24);
      v29[4] = 1;
      v36 = *(_QWORD *)(a10 + 8);
      v29[12] = 4;
      *((_QWORD *)v29 + 7) = v36 + 16;
      v29[18] = a17;
      v29[22] = a18;
      v29[30] = a19;
      v29[34] = a20;
      v29[16] = 3;
      v29[20] = 3;
      v29[28] = 3;
      v29[32] = 3;
      v29[24] = 3;
      v29[26] = v24;
      v29[2] = _byteswap_ulong(***(_DWORD ***)(a10 + 16));
      v37 = v81;
      *v29 = 3;
      v29[10] = _byteswap_ulong(*v37);
      v29[8] = 3;
      goto LABEL_28;
    case 6u:
      *((_BYTE *)v85 + 24) = *(_BYTE *)(a10 + 24);
      v29[4] = 1;
      v39 = *(_QWORD *)(a10 + 8);
      v29[12] = 4;
      *((_QWORD *)v29 + 7) = v39 + 16;
      v29[18] = a17;
      v29[22] = a18;
      v29[30] = a19;
      v29[34] = a20;
      v29[16] = 3;
      v29[20] = 3;
      v29[28] = 3;
      v29[32] = 3;
      v29[24] = 3;
      v29[26] = v24;
      v40 = **(_QWORD **)(a10 + 16);
      *((_QWORD *)v29 + 5) = v81;
      *v29 = 11;
      *((_QWORD *)v29 + 1) = v40;
      v29[8] = 11;
LABEL_28:
      v38 = ***(_DWORD ***)(a10 + 8);
      v29[36] = 3;
      v29[38] = v38;
      goto LABEL_43;
    case 0xCu:
      *((_WORD *)v85 + 36) = __ROR2__(a8, 8);
      *((_WORD *)v29 + 44) = __ROR2__(a9, 8);
      *v29 = 1;
      *((_BYTE *)v29 + 8) = a6;
      v29[16] = 2;
      v29[20] = 2;
      *((_BYTE *)v29 + 56) = *(_BYTE *)(a10 + 24);
      v29[12] = 1;
      v41 = *(_QWORD *)(a10 + 8) + 16LL;
      v29[24] = 4;
      *((_QWORD *)v29 + 13) = v41;
      v29[30] = a17;
      v29[34] = a18;
      v29[42] = a19;
      v29[46] = a20;
      v29[50] = a16;
      v29[28] = 3;
      v29[32] = 3;
      v29[40] = 3;
      v29[44] = 3;
      v29[48] = 3;
      LODWORD(v41) = ***(_DWORD ***)(a10 + 16);
      a2[4] = 3;
      a2[6] = _byteswap_ulong(v41);
      LODWORD(v41) = *v81;
      a2[8] = 3;
      a2[10] = _byteswap_ulong(v41);
      if ( a6 != 1 && a6 != 58 )
        goto LABEL_34;
      v29[16] = 2;
      v29[20] = 2;
LABEL_33:
      *((_WORD *)v29 + 36) = *(unsigned __int8 *)(a13 + 4);
      *((_WORD *)v29 + 44) = *(unsigned __int8 *)(a13 + 5);
LABEL_34:
      v29[36] = 3;
      *((_QWORD *)v29 + 27) = P;
      v29[38] = v24;
      v29[52] = 12;
      v42 = ***(_DWORD ***)(a10 + 8);
      v29[56] = 3;
      v29[58] = v42;
      goto LABEL_43;
    case 0xEu:
      *((_WORD *)v85 + 36) = __ROR2__(a8, 8);
      *((_WORD *)v29 + 44) = __ROR2__(a9, 8);
      *v29 = 1;
      *((_BYTE *)v29 + 8) = a6;
      v29[16] = 2;
      v29[20] = 2;
      *((_BYTE *)v29 + 56) = *(_BYTE *)(a10 + 24);
      v29[12] = 1;
      v43 = *(_QWORD *)(a10 + 8) + 16LL;
      v29[24] = 4;
      *((_QWORD *)v29 + 13) = v43;
      v29[30] = a17;
      v29[34] = a18;
      v29[42] = a19;
      v29[46] = a20;
      v29[50] = a16;
      v29[28] = 3;
      v29[32] = 3;
      v29[40] = 3;
      v29[44] = 3;
      v29[48] = 3;
      v44 = **(_QWORD **)(a10 + 16);
      *((_QWORD *)v29 + 5) = v81;
      v29[4] = 11;
      *((_QWORD *)v29 + 3) = v44;
      v29[8] = 11;
      if ( a6 == 1 || a6 == 58 )
        goto LABEL_33;
      goto LABEL_34;
    case 0x10u:
      *((_WORD *)v85 + 36) = __ROR2__(a8, 8);
      *((_WORD *)v29 + 44) = __ROR2__(a9, 8);
      *v29 = 1;
      *((_BYTE *)v29 + 8) = a6;
      v29[16] = 2;
      v29[20] = 2;
      *((_BYTE *)v29 + 40) = *(_BYTE *)(a10 + 24);
      v29[8] = 1;
      v31 = *(_QWORD *)(a10 + 8) + 16LL;
      v29[24] = 4;
      *((_QWORD *)v29 + 13) = v31;
      v29[30] = a17;
      v29[34] = a18;
      v29[46] = a19;
      v29[50] = a20;
      v29[54] = a16;
      *((_BYTE *)v29 + 152) = a12;
      v29[28] = 3;
      v29[32] = 3;
      v29[44] = 3;
      v29[48] = 3;
      v29[52] = 3;
      v29[36] = 1;
      LODWORD(v31) = ***(_DWORD ***)(a10 + 16);
      v29[4] = 3;
      v29[6] = _byteswap_ulong(v31);
      LODWORD(v31) = *v81;
      v29[12] = 3;
      v29[14] = _byteswap_ulong(v31);
      if ( a6 == 1 || a6 == 58 )
        goto LABEL_22;
      goto LABEL_23;
    case 0x12u:
      *((_WORD *)v85 + 36) = __ROR2__(a8, 8);
      *((_WORD *)v29 + 44) = __ROR2__(a9, 8);
      *v29 = 1;
      *((_BYTE *)v29 + 8) = a6;
      v29[16] = 2;
      v29[20] = 2;
      *((_BYTE *)v29 + 40) = *(_BYTE *)(a10 + 24);
      v29[8] = 1;
      v33 = *(_QWORD *)(a10 + 8) + 16LL;
      v29[24] = 4;
      *((_QWORD *)v29 + 13) = v33;
      v29[30] = a17;
      v29[34] = a18;
      v29[46] = a19;
      v29[50] = a20;
      v29[54] = a16;
      *((_BYTE *)v29 + 152) = a12;
      v29[28] = 3;
      v29[32] = 3;
      v29[44] = 3;
      v29[48] = 3;
      v29[52] = 3;
      v29[36] = 1;
      v34 = **(_QWORD **)(a10 + 16);
      *((_QWORD *)v29 + 7) = v81;
      v29[4] = 11;
      *((_QWORD *)v29 + 3) = v34;
      v29[12] = 11;
      if ( a6 == 1 )
      {
LABEL_22:
        *((_WORD *)v29 + 36) = *(unsigned __int8 *)(a13 + 4);
        *((_WORD *)v29 + 44) = *(unsigned __int8 *)(a13 + 5);
LABEL_23:
        v29[40] = 3;
        *((_QWORD *)v29 + 29) = P;
        v29[42] = v24;
        v29[56] = 12;
        v32 = ***(_DWORD ***)(a10 + 8);
        v29[60] = 3;
        v29[62] = v32;
        goto LABEL_43;
      }
      if ( a6 != 58 )
        goto LABEL_23;
      v29[40] = 3;
      v29[42] = v24;
      v29[56] = 12;
      *((_WORD *)v29 + 36) = *(unsigned __int8 *)(a13 + 4);
      *((_WORD *)v29 + 44) = *(unsigned __int8 *)(a13 + 5);
      *((_QWORD *)v29 + 29) = P;
      v35 = ***(_DWORD ***)(a10 + 8);
      v29[60] = 3;
      v29[62] = v35;
LABEL_43:
      v55 = KfdClassify(a5, v83, a3, v86, 0, v93);
      if ( SpinLock )
      {
        v56 = 0;
        v79 = 0;
        v80 = 0;
        if ( *((_QWORD *)SpinLock + 21) )
        {
          IPSecAcquireReadLockConnDb(&v79);
          v56 = *((_QWORD *)SpinLock + 21);
          if ( v56 )
            IPSecRefNsConnEntry(v57, *((_QWORD *)SpinLock + 21));
          IPSecReleaseReadLockConnDb(&v79);
        }
        v82 = v56;
        if ( v56 )
        {
          v58 = *(_BYTE *)(v56 + 64);
          if ( (v58 == 6 || v58 == 17) && *(_WORD *)(v56 + 66) != *(_WORD *)(v56 + 68) )
          {
            v59 = v86;
            v60 = (_QWORD *)WfpNblInfoGet(v86);
            if ( v60 )
            {
              v61 = MmBadPointer;
              if ( v60 != MmBadPointer )
              {
                if ( v60[3] )
                  IPSecCleanupOutboundPacketState(v59);
              }
            }
            IPSecDerefNsConnEntry(v61, &v82);
            v62 = v85;
            v63 = a5;
            v85[42] = v24 | 0x80;
            v64 = 0;
            v62[40] = 3;
            v79 = 0;
            v80 = 0;
            if ( *((_QWORD *)SpinLock + 21) )
            {
              IPSecAcquireReadLockConnDb(&v79);
              v64 = *((_QWORD *)SpinLock + 21);
              if ( v64 )
                IPSecRefNsConnEntry(v65, *((_QWORD *)SpinLock + 21));
              IPSecReleaseReadLockConnDb(&v79);
            }
            v82 = v64;
            RemoteWirePortFromNsConnEntry = IPSecGetRemoteWirePortFromNsConnEntry(v64);
            IPSecDerefNsConnEntry(v67, &v82);
            v68 = v85;
            *((_WORD *)v85 + 44) = __ROR2__(RemoteWirePortFromNsConnEntry, 8);
            v68[20] = 2;
            v55 = KfdClassify(a5, v83, a3, v59, 0, v93);
            if ( v55 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
            {
              WPP_SF_sDd(
                WPP_GLOBAL_Control->AttachedDevice,
                16,
                v54,
                (unsigned int)"ProcessIPsecNattTransportLayerReclassifyOutbound",
                177,
                v55);
            }
            if ( *(_DWORD *)(a3 + 536) )
              KfdReleaseCachedFilters(v87);
            v69 = a6;
            goto LABEL_80;
          }
          IPSecDerefNsConnEntry(v53, &v82);
        }
      }
      v69 = a6;
      if ( a6 == 1
        || a6 == 58
        || (unsigned __int8)(a12 - 3) <= 1u
        || (unsigned int)(*(_DWORD *)(a10 + 24) - 3) <= 1
        || (_QWORD *)v87[0] == v87 )
      {
        if ( *(_DWORD *)(a3 + 536) )
          KfdReleaseCachedFilters(v87);
        goto LABEL_79;
      }
      if ( !*(_DWORD *)(a3 + 536) )
      {
LABEL_79:
        v63 = a5;
        goto LABEL_80;
      }
      v63 = a5;
      if ( (int)TlShimCacheMatchedFilterList((PKSPIN_LOCK)SpinLock, *(_QWORD *)(a3 + 512), v78) < 0 )
        KfdReleaseCachedFilters(v87);
LABEL_80:
      if ( (v55 & 0xC0000000) == 0xC0000000 )
      {
        *(_OWORD *)v93 = 0;
        LODWORD(v93[0]) = 4097;
        v94 = 0;
        v95 = 0;
      }
      else if ( LODWORD(v93[0]) != 4097 )
      {
        v30 = 1;
        goto LABEL_90;
      }
      if ( (BYTE12(v94) & 1) != 0 )
      {
LABEL_90:
        v70 = v86;
        goto LABEL_91;
      }
      v30 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v52,
          v54,
          (unsigned int)"ProcessOutboundTransportLayerClassify",
          180,
          0);
      }
      *(_QWORD *)(a3 + 512) = 0;
      v70 = v86;
      WfpShimIndicateDiscardGeneral(v63, (unsigned int)v83, a3, v86, 0, (__int64)v93);
LABEL_91:
      if ( a7 != 2 )
      {
        if ( a7 == 23 )
        {
          v71 = 41;
          goto LABEL_95;
        }
LABEL_103:
        __fastfail(5u);
      }
      v71 = 0;
LABEL_95:
      v72 = IpSecTlPacketsOutProcessing(v71, a10, (_DWORD)v81, v69, a8, a9, v70, v30, (__int64)SpinLock);
      v75 = P[1];
      *(_QWORD *)(a3 + 8) = 0;
      v76 = v72;
      if ( v75 )
        ExFreePoolWithTag(v75, 0x52537049u);
      P[1] = 0;
      LODWORD(P[0]) = 0;
      if ( v76 != 1
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v73,
          v74,
          (unsigned int)"ProcessOutboundTransportLayerClassify",
          220,
          v76);
      }
      return v76;
    case 0x46u:
      v85[2] = _byteswap_ulong(***(_DWORD ***)(a10 + 16));
      v49 = v81;
      *v29 = 3;
      v29[6] = _byteswap_ulong(*v49);
      v29[4] = 3;
      goto LABEL_42;
    case 0x47u:
      v50 = **(_QWORD **)(a10 + 16);
      *((_QWORD *)v85 + 3) = v81;
      *v29 = 11;
      *((_QWORD *)v29 + 1) = v50;
      v29[4] = 11;
LABEL_42:
      *((_WORD *)v29 + 20) = __ROR2__(a8, 8);
      *((_WORD *)v29 + 28) = __ROR2__(a9, 8);
      v29[8] = 2;
      v29[12] = 2;
      v51 = *(_QWORD *)(a10 + 8);
      v29[16] = 4;
      *((_QWORD *)v29 + 9) = v51 + 16;
      v29[22] = a17;
      v29[26] = a18;
      v29[38] = a19;
      v29[42] = a20;
      v29[20] = 3;
      v29[24] = 3;
      v29[28] = 3;
      v29[30] = 0;
      v29[32] = 3;
      v29[34] = v24;
      v29[36] = 3;
      v29[40] = 3;
      v29[46] = ***(_DWORD ***)(a10 + 8);
      v29[44] = 3;
      goto LABEL_43;
    default:
      goto LABEL_103;
  }
}

```

## disassembly

```asm
0x140132920  push    rbp
0x140132922  push    rbx
0x140132923  push    rsi
0x140132924  push    rdi
0x140132925  push    r13
0x140132927  push    r14
0x140132929  push    r15
0x14013292b  lea     rbp, [rsp-7]
0x140132930  sub     rsp, 100h
0x140132937  mov     rax, cs:__security_cookie
0x14013293e  xor     rax, rsp
0x140132941  mov     [rbp+37h+var_38], rax
0x140132945  mov     rax, [rbp+37h+arg_50]
0x14013294c  xorps   xmm0, xmm0
0x14013294f  movzx   r14d, [rbp+37h+arg_20]
0x140132954  mov     rsi, rcx
0x140132957  mov     rcx, [rbp+37h+arg_68]
0x14013295e  xorps   xmm1, xmm1
0x140132961  mov     rdi, [rbp+37h+arg_48]
0x140132968  mov     r15, r8
0x14013296b  mov     [rsp+130h+var_D8], rax
0x140132970  mov     r13, rdx
0x140132973  xor     eax, eax
0x140132975  mov     [rsp+130h+var_B8], rcx
0x14013297a  mov     [rsp+130h+var_C6], ax
0x14013297f  mov     dword ptr [rbp+37h+var_40], eax
0x140132982  mov     [rbp+37h+var_68], rax
0x140132986  lea     rax, [rbp+37h+var_B0]
0x14013298a  mov     [rbp+37h+var_A8], rax
0x14013298e  lea     rax, [rbp+37h+var_B0]
0x140132992  mov     [rbp+37h+var_B0], rax
0x140132996  lea     rax, [rbp+37h+var_90]
0x14013299a  mov     [r8+8], rax
0x14013299e  mov     [rsp+130h+var_C8], r14w
0x1401329a4  mov     [rsp+130h+var_C0], rdx
0x1401329a9  mov     [rsp+130h+var_C4], 10h
0x1401329b1  mov     [rbp+37h+var_90], rsi
0x1401329b5  movups  xmmword ptr [rbp+37h+var_60], xmm0
0x1401329b9  movups  [rbp+37h+var_50], xmm0
0x1401329bd  movdqu  [rbp+37h+var_88], xmm0
0x1401329c2  movdqu  [rbp+37h+var_78], xmm1
0x1401329c7  movups  xmmword ptr [rbp+37h+P], xmm0
0x1401329cb  test    r9, r9
0x1401329ce  jz      short loc_1401329D7
0x1401329d0  mov     [r8+180h], r9
0x1401329d7  test    rsi, rsi
0x1401329da  jz      short loc_1401329FD
0x1401329dc  cmp     dword ptr [rsi+28h], 6
0x1401329e0  jnz     short loc_1401329E9
0x1401329e2  mov     eax, [rsi+30h]
0x1401329e5  test    al, 10h
0x1401329e7  jz      short loc_1401329F2
0x1401329e9  cmp     byte ptr [rsi+26Ah], 0
0x1401329f0  jnz     short loc_1401329FD
0x1401329f2  lea     rax, [rbp+37h+var_B0]
0x1401329f6  mov     [r8+200h], rax
0x1401329fd  mov     ebx, [rbp+37h+arg_A0]
0x140132a03  or      ebx, 1
0x140132a06  cmp     [rbp+37h+arg_70], 0
0x140132a0d  cmovz   ebx, [rbp+37h+arg_A0]
0x140132a14  call    cs:__imp_WfpNblInfoGet
0x140132a1b  nop     dword ptr [rax+rax+00h]
0x140132a20  mov     rdx, rax
0x140132a23  test    rax, rax
0x140132a26  jz      short loc_140132A3D
0x140132a28  mov     rcx, cs:MmBadPointer
0x140132a2f  mov     r8, [rcx]
0x140132a32  cmp     rax, r8
0x140132a35  jz      short loc_140132A3D
0x140132a37  mov     rax, [rax+8]
0x140132a3b  jmp     short loc_140132A4F
0x140132a3d  mov     rax, cs:MmBadPointer
0x140132a44  mov     rax, [rax]
0x140132a47  cmp     rdx, rax
0x140132a4a  jnz     short loc_140132A68
0x140132a4c  mov     r8, rax
0x140132a4f  test    rax, rax
0x140132a52  jz      short loc_140132A68
0x140132a54  cmp     rax, r8
0x140132a57  jz      short loc_140132A68
0x140132a59  movups  xmm0, xmmword ptr [rax+160h]
0x140132a60  movups  xmmword ptr [r15+170h], xmm0
0x140132a68  lea     rdx, [rbp+37h+P]
0x140132a6c  mov     [rsp+130h+arg_18], r12
0x140132a74  mov     rcx, rsi; SpinLock
0x140132a77  call    WfpAleCopySecurityRealmIdFromEndpoint
0x140132a7c  mov     r10, r14
0x140132a7f  cmp     r14d, 47h ; 'G'
0x140132a83  ja      def_140132AB9; jumptable 0000000140132AB9 default case, cases 1,3,5,7-11,13,15,17,19-69
0x140132a89  mov     rdx, [rsp+130h+var_C0]
0x140132a8e  cmp     r10d, 47h; switch 72 cases
0x140132a92  ja      def_140132AB9; jumptable 0000000140132AB9 default case, cases 1,3,5,7-11,13,15,17,19-69
0x140132a98  lea     r8, cs:140000000h
0x140132a9f  mov     r12d, 2
0x140132aa5  movzx   eax, ds:(byte_1401F0547 - 140000000h)[r8+r14]
0x140132aae  mov     ecx, ds:(jpt_140132AB9 - 140000000h)[r8+rax*4]
0x140132ab6  add     rcx, r8
0x140132ab9  jmp     rcx; switch jump
0x140132abf  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140132AB9 case 16
0x140132ac3  mov     r14d, [rbp+37h+arg_28]
0x140132ac7  ror     ax, 8
0x140132acb  mov     [rdx+48h], ax
0x140132acf  movzx   eax, [rbp+37h+arg_40]
0x140132ad6  ror     ax, 8
0x140132ada  mov     [rdx+58h], ax
0x140132ade  mov     dword ptr [rdx], 1
0x140132ae4  mov     [rdx+8], r14b
0x140132ae8  mov     [rdx+40h], r12d
0x140132aec  mov     [rdx+50h], r12d
0x140132af0  movzx   eax, byte ptr [rdi+18h]
0x140132af4  mov     [rdx+28h], al
0x140132af7  mov     dword ptr [rdx+20h], 1
0x140132afe  mov     rax, [rdi+8]
0x140132b02  add     rax, 10h
0x140132b06  mov     dword ptr [rdx+60h], 4
0x140132b0d  mov     [rdx+68h], rax
0x140132b11  mov     eax, [rbp+37h+arg_80]
0x140132b17  mov     [rdx+78h], eax
0x140132b1a  mov     eax, [rbp+37h+arg_88]
0x140132b20  mov     [rdx+88h], eax
0x140132b26  mov     eax, [rbp+37h+arg_90]
0x140132b2c  mov     [rdx+0B8h], eax
0x140132b32  mov     eax, [rbp+37h+arg_98]
0x140132b38  mov     [rdx+0C8h], eax
0x140132b3e  mov     eax, [rbp+37h+arg_78]
0x140132b44  mov     [rdx+0D8h], eax
0x140132b4a  movzx   eax, [rbp+37h+arg_58]
0x140132b51  mov     [rdx+98h], al
0x140132b57  mov     dword ptr [rdx+70h], 3
0x140132b5e  mov     dword ptr [rdx+80h], 3
0x140132b68  mov     dword ptr [rdx+0B0h], 3
0x140132b72  mov     dword ptr [rdx+0C0h], 3
0x140132b7c  mov     dword ptr [rdx+0D0h], 3
0x140132b86  mov     dword ptr [rdx+90h], 1
0x140132b90  mov     rax, [rdi+10h]
0x140132b94  mov     rcx, [rax]
0x140132b97  mov     eax, [rcx]
0x140132b99  mov     dword ptr [rdx+10h], 3
0x140132ba0  bswap   eax
0x140132ba2  mov     [rdx+18h], eax
0x140132ba5  mov     rax, [rsp+130h+var_D8]
0x140132baa  mov     eax, [rax]
0x140132bac  mov     dword ptr [rdx+30h], 3
0x140132bb3  bswap   eax
0x140132bb5  mov     [rdx+38h], eax
0x140132bb8  cmp     r14d, 1
0x140132bbc  jz      short loc_140132BC4
0x140132bbe  cmp     r14d, 3Ah ; ':'
0x140132bc2  jnz     short loc_140132BDB
0x140132bc4  mov     rcx, [rbp+37h+arg_60]
0x140132bcb  movzx   eax, byte ptr [rcx+4]
0x140132bcf  mov     [rdx+48h], ax
0x140132bd3  movzx   eax, byte ptr [rcx+5]
0x140132bd7  mov     [rdx+58h], ax
0x140132bdb  mov     dword ptr [rdx+0A0h], 3
0x140132be5  lea     rax, [rbp+37h+P]
0x140132be9  mov     [rdx+0E8h], rax
0x140132bf0  mov     [rdx+0A8h], ebx
0x140132bf6  mov     dword ptr [rdx+0E0h], 0Ch
0x140132c00  mov     rax, [rdi+8]
0x140132c04  mov     rcx, [rax]
0x140132c07  mov     eax, [rcx]
0x140132c09  mov     dword ptr [rdx+0F0h], 3
0x140132c13  mov     [rdx+0F8h], eax
0x140132c19  jmp     loc_14013334C
0x140132c1e  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140132AB9 case 18
0x140132c22  mov     r14d, [rbp+37h+arg_28]
0x140132c26  ror     ax, 8
0x140132c2a  mov     [rdx+48h], ax
0x140132c2e  movzx   eax, [rbp+37h+arg_40]
0x140132c35  ror     ax, 8
0x140132c39  mov     [rdx+58h], ax
0x140132c3d  mov     dword ptr [rdx], 1
0x140132c43  mov     [rdx+8], r14b
0x140132c47  mov     [rdx+40h], r12d
0x140132c4b  mov     [rdx+50h], r12d
0x140132c4f  movzx   eax, byte ptr [rdi+18h]
0x140132c53  mov     [rdx+28h], al
0x140132c56  mov     dword ptr [rdx+20h], 1
0x140132c5d  mov     rax, [rdi+8]
0x140132c61  add     rax, 10h
0x140132c65  mov     dword ptr [rdx+60h], 4
0x140132c6c  mov     [rdx+68h], rax
0x140132c70  mov     eax, [rbp+37h+arg_80]
0x140132c76  mov     [rdx+78h], eax
0x140132c79  mov     eax, [rbp+37h+arg_88]
0x140132c7f  mov     [rdx+88h], eax
0x140132c85  mov     eax, [rbp+37h+arg_90]
0x140132c8b  mov     [rdx+0B8h], eax
0x140132c91  mov     eax, [rbp+37h+arg_98]
0x140132c97  mov     [rdx+0C8h], eax
0x140132c9d  mov     eax, [rbp+37h+arg_78]
0x140132ca3  mov     [rdx+0D8h], eax
0x140132ca9  movzx   eax, [rbp+37h+arg_58]
0x140132cb0  mov     [rdx+98h], al
0x140132cb6  mov     dword ptr [rdx+70h], 3
0x140132cbd  mov     dword ptr [rdx+80h], 3
0x140132cc7  mov     dword ptr [rdx+0B0h], 3
0x140132cd1  mov     dword ptr [rdx+0C0h], 3
0x140132cdb  mov     dword ptr [rdx+0D0h], 3
0x140132ce5  mov     dword ptr [rdx+90h], 1
0x140132cef  mov     rax, [rdi+10h]
0x140132cf3  mov     rcx, [rax]
0x140132cf6  mov     rax, [rsp+130h+var_D8]
0x140132cfb  mov     [rdx+38h], rax
0x140132cff  mov     dword ptr [rdx+10h], 0Bh
0x140132d06  mov     [rdx+18h], rcx
0x140132d0a  mov     dword ptr [rdx+30h], 0Bh
0x140132d11  cmp     r14d, 1
0x140132d15  jz      loc_140132BC4
0x140132d1b  cmp     r14d, 3Ah ; ':'
0x140132d1f  jnz     loc_140132BDB
0x140132d25  mov     rcx, [rbp+37h+arg_60]
0x140132d2c  mov     dword ptr [rdx+0A0h], 3
0x140132d36  mov     [rdx+0A8h], ebx
0x140132d3c  mov     dword ptr [rdx+0E0h], 0Ch
0x140132d46  movzx   eax, byte ptr [rcx+4]
0x140132d4a  mov     [rdx+48h], ax
0x140132d4e  movzx   eax, byte ptr [rcx+5]
0x140132d52  mov     [rdx+58h], ax
0x140132d56  lea     rax, [rbp+37h+P]
0x140132d5a  mov     [rdx+0E8h], rax
0x140132d61  mov     rax, [rdi+8]
0x140132d65  mov     rcx, [rax]
0x140132d68  mov     eax, [rcx]
0x140132d6a  mov     dword ptr [rdx+0F0h], 3
0x140132d74  mov     [rdx+0F8h], eax
0x140132d7a  jmp     loc_14013334C
0x140132d7f  movzx   eax, byte ptr [rdi+18h]; jumptable 0000000140132AB9 case 4
0x140132d83  mov     [rdx+18h], al
0x140132d86  mov     dword ptr [rdx+10h], 1
0x140132d8d  mov     rax, [rdi+8]
0x140132d91  add     rax, 10h
0x140132d95  mov     dword ptr [rdx+30h], 4
0x140132d9c  mov     [rdx+38h], rax
0x140132da0  mov     eax, [rbp+37h+arg_80]
0x140132da6  mov     [rdx+48h], eax
0x140132da9  mov     eax, [rbp+37h+arg_88]
0x140132daf  mov     [rdx+58h], eax
0x140132db2  mov     eax, [rbp+37h+arg_90]
0x140132db8  mov     [rdx+78h], eax
0x140132dbb  mov     eax, [rbp+37h+arg_98]
0x140132dc1  mov     [rdx+88h], eax
0x140132dc7  mov     dword ptr [rdx+40h], 3
0x140132dce  mov     dword ptr [rdx+50h], 3
0x140132dd5  mov     dword ptr [rdx+70h], 3
0x140132ddc  mov     dword ptr [rdx+80h], 3
0x140132de6  mov     dword ptr [rdx+60h], 3
0x140132ded  mov     [rdx+68h], ebx
0x140132df0  mov     rax, [rdi+10h]
0x140132df4  mov     rcx, [rax]
0x140132df7  mov     eax, [rcx]
0x140132df9  bswap   eax
0x140132dfb  mov     [rdx+8], eax
0x140132dfe  mov     rax, [rsp+130h+var_D8]
0x140132e03  mov     dword ptr [rdx], 3
0x140132e09  mov     eax, [rax]
0x140132e0b  bswap   eax
0x140132e0d  mov     [rdx+28h], eax
0x140132e10  mov     dword ptr [rdx+20h], 3
0x140132e17  mov     rax, [rdi+8]
0x140132e1b  mov     rcx, [rax]
0x140132e1e  mov     eax, [rcx]
0x140132e20  mov     dword ptr [rdx+90h], 3
0x140132e2a  mov     [rdx+98h], eax
0x140132e30  jmp     loc_14013334C
0x140132e35  movzx   eax, byte ptr [rdi+18h]; jumptable 0000000140132AB9 case 6
0x140132e39  mov     [rdx+18h], al
0x140132e3c  mov     dword ptr [rdx+10h], 1
0x140132e43  mov     rax, [rdi+8]
0x140132e47  add     rax, 10h
0x140132e4b  mov     dword ptr [rdx+30h], 4
0x140132e52  mov     [rdx+38h], rax
0x140132e56  mov     eax, [rbp+37h+arg_80]
0x140132e5c  mov     [rdx+48h], eax
0x140132e5f  mov     eax, [rbp+37h+arg_88]
0x140132e65  mov     [rdx+58h], eax
0x140132e68  mov     eax, [rbp+37h+arg_90]
0x140132e6e  mov     [rdx+78h], eax
0x140132e71  mov     eax, [rbp+37h+arg_98]
0x140132e77  mov     [rdx+88h], eax
0x140132e7d  mov     dword ptr [rdx+40h], 3
0x140132e84  mov     dword ptr [rdx+50h], 3
0x140132e8b  mov     dword ptr [rdx+70h], 3
0x140132e92  mov     dword ptr [rdx+80h], 3
0x140132e9c  mov     dword ptr [rdx+60h], 3
0x140132ea3  mov     [rdx+68h], ebx
0x140132ea6  mov     rax, [rdi+10h]
0x140132eaa  mov     rcx, [rax]
0x140132ead  mov     rax, [rsp+130h+var_D8]
0x140132eb2  mov     [rdx+28h], rax
0x140132eb6  mov     dword ptr [rdx], 0Bh
0x140132ebc  mov     [rdx+8], rcx
0x140132ec0  mov     dword ptr [rdx+20h], 0Bh
0x140132ec7  jmp     loc_140132E17
0x140132ecc  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140132AB9 case 12
0x140132ed0  mov     r14d, [rbp+37h+arg_28]
0x140132ed4  ror     ax, 8
0x140132ed8  mov     [rdx+48h], ax
0x140132edc  movzx   eax, [rbp+37h+arg_40]
  ... truncated ...
```
