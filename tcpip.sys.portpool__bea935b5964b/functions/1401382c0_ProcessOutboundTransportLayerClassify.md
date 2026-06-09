# ProcessOutboundTransportLayerClassify

- ea: `0x1401382c0`
- end: `0x14013913d`
- name: `ProcessOutboundTransportLayerClassify`
- size: `3709`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, int, __int16, __int16, __int16, __int64, __int64, char, __int64, __int64, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140011568`

## callees

- `0x140011220`
- `0x1400bbc40`
- `0x1400bf840`
- `0x1400c0d78`
- `0x1401382c0`
- `0x1401522cc`
- `0x140152424`
- `0x1401c0fd0`
- `0x140264c08`
- `0x140272888`
- `0x140272a54`
- `0x140272a74`
- `0x140273e64`
- `0x140278f00`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1401383c8`
- `ntoskrnl!MmBadPointer` at `0x1401383dd`
- `ntoskrnl!MmBadPointer` at `0x140138dae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401390b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401390b7`
- `NETIO!WfpNblInfoGet` at `0x1401383b4`
- `NETIO!WfpNblInfoGet` at `0x140138d9d`
- `NETIO!WfpNblInfoGet` at `0x1401383b4`
- `NETIO!WfpNblInfoGet` at `0x140138d9d`
- `NETIO!KfdReleaseCachedFilters` at `0x140138ee0`
- `NETIO!KfdReleaseCachedFilters` at `0x140138f6a`
- `NETIO!KfdReleaseCachedFilters` at `0x140138f86`
- `NETIO!KfdReleaseCachedFilters` at `0x140138ee0`
- `NETIO!KfdReleaseCachedFilters` at `0x140138f6a`
- `NETIO!KfdReleaseCachedFilters` at `0x140138f86`
- `NETIO!KfdClassify` at `0x140138d0f`
- `NETIO!KfdClassify` at `0x140138e7b`
- `NETIO!KfdClassify` at `0x140138d0f`
- `NETIO!KfdClassify` at `0x140138e7b`

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
0x1401382c0  push    rbp
0x1401382c2  push    rbx
0x1401382c3  push    rsi
0x1401382c4  push    rdi
0x1401382c5  push    r13
0x1401382c7  push    r14
0x1401382c9  push    r15
0x1401382cb  lea     rbp, [rsp-7]
0x1401382d0  sub     rsp, 100h
0x1401382d7  mov     rax, cs:__security_cookie
0x1401382de  xor     rax, rsp
0x1401382e1  mov     [rbp+37h+var_38], rax
0x1401382e5  mov     rax, [rbp+37h+arg_50]
0x1401382ec  xorps   xmm0, xmm0
0x1401382ef  movzx   r14d, [rbp+37h+arg_20]
0x1401382f4  mov     rsi, rcx
0x1401382f7  mov     rcx, [rbp+37h+arg_68]
0x1401382fe  xorps   xmm1, xmm1
0x140138301  mov     rdi, [rbp+37h+arg_48]
0x140138308  mov     r15, r8
0x14013830b  mov     [rsp+130h+var_D8], rax
0x140138310  mov     r13, rdx
0x140138313  xor     eax, eax
0x140138315  mov     [rsp+130h+var_B8], rcx
0x14013831a  mov     [rsp+130h+var_C6], ax
0x14013831f  mov     dword ptr [rbp+37h+var_40], eax
0x140138322  mov     [rbp+37h+var_68], rax
0x140138326  lea     rax, [rbp+37h+var_B0]
0x14013832a  mov     [rbp+37h+var_A8], rax
0x14013832e  lea     rax, [rbp+37h+var_B0]
0x140138332  mov     [rbp+37h+var_B0], rax
0x140138336  lea     rax, [rbp+37h+var_90]
0x14013833a  mov     [r8+8], rax
0x14013833e  mov     [rsp+130h+var_C8], r14w
0x140138344  mov     [rsp+130h+var_C0], rdx
0x140138349  mov     [rsp+130h+var_C4], 10h
0x140138351  mov     [rbp+37h+var_90], rsi
0x140138355  movups  xmmword ptr [rbp+37h+var_60], xmm0
0x140138359  movups  [rbp+37h+var_50], xmm0
0x14013835d  movdqu  [rbp+37h+var_88], xmm0
0x140138362  movdqu  [rbp+37h+var_78], xmm1
0x140138367  movups  xmmword ptr [rbp+37h+P], xmm0
0x14013836b  test    r9, r9
0x14013836e  jz      short loc_140138377
0x140138370  mov     [r8+180h], r9
0x140138377  test    rsi, rsi
0x14013837a  jz      short loc_14013839D
0x14013837c  cmp     dword ptr [rsi+28h], 6
0x140138380  jnz     short loc_140138389
0x140138382  mov     eax, [rsi+30h]
0x140138385  test    al, 10h
0x140138387  jz      short loc_140138392
0x140138389  cmp     byte ptr [rsi+26Ah], 0
0x140138390  jnz     short loc_14013839D
0x140138392  lea     rax, [rbp+37h+var_B0]
0x140138396  mov     [r8+200h], rax
0x14013839d  mov     ebx, [rbp+37h+arg_A0]
0x1401383a3  or      ebx, 1
0x1401383a6  cmp     [rbp+37h+arg_70], 0
0x1401383ad  cmovz   ebx, [rbp+37h+arg_A0]
0x1401383b4  call    cs:__imp_WfpNblInfoGet
0x1401383bb  nop     dword ptr [rax+rax+00h]
0x1401383c0  mov     rdx, rax
0x1401383c3  test    rax, rax
0x1401383c6  jz      short loc_1401383DD
0x1401383c8  mov     rcx, cs:MmBadPointer
0x1401383cf  mov     r8, [rcx]
0x1401383d2  cmp     rax, r8
0x1401383d5  jz      short loc_1401383DD
0x1401383d7  mov     rax, [rax+8]
0x1401383db  jmp     short loc_1401383EF
0x1401383dd  mov     rax, cs:MmBadPointer
0x1401383e4  mov     rax, [rax]
0x1401383e7  cmp     rdx, rax
0x1401383ea  jnz     short loc_140138408
0x1401383ec  mov     r8, rax
0x1401383ef  test    rax, rax
0x1401383f2  jz      short loc_140138408
0x1401383f4  cmp     rax, r8
0x1401383f7  jz      short loc_140138408
0x1401383f9  movups  xmm0, xmmword ptr [rax+160h]
0x140138400  movups  xmmword ptr [r15+170h], xmm0
0x140138408  lea     rdx, [rbp+37h+P]
0x14013840c  mov     [rsp+130h+arg_18], r12
0x140138414  mov     rcx, rsi; SpinLock
0x140138417  call    WfpAleCopySecurityRealmIdFromEndpoint
0x14013841c  mov     r10, r14
0x14013841f  cmp     r14d, 47h ; 'G'
0x140138423  ja      def_140138459; jumptable 0000000140138459 default case, cases 1,3,5,7-11,13,15,17,19-69
0x140138429  mov     rdx, [rsp+130h+var_C0]
0x14013842e  cmp     r10d, 47h; switch 72 cases
0x140138432  ja      def_140138459; jumptable 0000000140138459 default case, cases 1,3,5,7-11,13,15,17,19-69
0x140138438  lea     r8, cs:140000000h
0x14013843f  mov     r12d, 2
0x140138445  movzx   eax, ds:(byte_1401F4207 - 140000000h)[r8+r14]
0x14013844e  mov     ecx, ds:(jpt_140138459 - 140000000h)[r8+rax*4]
0x140138456  add     rcx, r8
0x140138459  jmp     rcx; switch jump
0x14013845f  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140138459 case 16
0x140138463  mov     r14d, [rbp+37h+arg_28]
0x140138467  ror     ax, 8
0x14013846b  mov     [rdx+48h], ax
0x14013846f  movzx   eax, [rbp+37h+arg_40]
0x140138476  ror     ax, 8
0x14013847a  mov     [rdx+58h], ax
0x14013847e  mov     dword ptr [rdx], 1
0x140138484  mov     [rdx+8], r14b
0x140138488  mov     [rdx+40h], r12d
0x14013848c  mov     [rdx+50h], r12d
0x140138490  movzx   eax, byte ptr [rdi+18h]
0x140138494  mov     [rdx+28h], al
0x140138497  mov     dword ptr [rdx+20h], 1
0x14013849e  mov     rax, [rdi+8]
0x1401384a2  add     rax, 10h
0x1401384a6  mov     dword ptr [rdx+60h], 4
0x1401384ad  mov     [rdx+68h], rax
0x1401384b1  mov     eax, [rbp+37h+arg_80]
0x1401384b7  mov     [rdx+78h], eax
0x1401384ba  mov     eax, [rbp+37h+arg_88]
0x1401384c0  mov     [rdx+88h], eax
0x1401384c6  mov     eax, [rbp+37h+arg_90]
0x1401384cc  mov     [rdx+0B8h], eax
0x1401384d2  mov     eax, [rbp+37h+arg_98]
0x1401384d8  mov     [rdx+0C8h], eax
0x1401384de  mov     eax, [rbp+37h+arg_78]
0x1401384e4  mov     [rdx+0D8h], eax
0x1401384ea  movzx   eax, [rbp+37h+arg_58]
0x1401384f1  mov     [rdx+98h], al
0x1401384f7  mov     dword ptr [rdx+70h], 3
0x1401384fe  mov     dword ptr [rdx+80h], 3
0x140138508  mov     dword ptr [rdx+0B0h], 3
0x140138512  mov     dword ptr [rdx+0C0h], 3
0x14013851c  mov     dword ptr [rdx+0D0h], 3
0x140138526  mov     dword ptr [rdx+90h], 1
0x140138530  mov     rax, [rdi+10h]
0x140138534  mov     rcx, [rax]
0x140138537  mov     eax, [rcx]
0x140138539  mov     dword ptr [rdx+10h], 3
0x140138540  bswap   eax
0x140138542  mov     [rdx+18h], eax
0x140138545  mov     rax, [rsp+130h+var_D8]
0x14013854a  mov     eax, [rax]
0x14013854c  mov     dword ptr [rdx+30h], 3
0x140138553  bswap   eax
0x140138555  mov     [rdx+38h], eax
0x140138558  cmp     r14d, 1
0x14013855c  jz      short loc_140138564
0x14013855e  cmp     r14d, 3Ah ; ':'
0x140138562  jnz     short loc_14013857B
0x140138564  mov     rcx, [rbp+37h+arg_60]
0x14013856b  movzx   eax, byte ptr [rcx+4]
0x14013856f  mov     [rdx+48h], ax
0x140138573  movzx   eax, byte ptr [rcx+5]
0x140138577  mov     [rdx+58h], ax
0x14013857b  mov     dword ptr [rdx+0A0h], 3
0x140138585  lea     rax, [rbp+37h+P]
0x140138589  mov     [rdx+0E8h], rax
0x140138590  mov     [rdx+0A8h], ebx
0x140138596  mov     dword ptr [rdx+0E0h], 0Ch
0x1401385a0  mov     rax, [rdi+8]
0x1401385a4  mov     rcx, [rax]
0x1401385a7  mov     eax, [rcx]
0x1401385a9  mov     dword ptr [rdx+0F0h], 3
0x1401385b3  mov     [rdx+0F8h], eax
0x1401385b9  jmp     loc_140138CEC
0x1401385be  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140138459 case 18
0x1401385c2  mov     r14d, [rbp+37h+arg_28]
0x1401385c6  ror     ax, 8
0x1401385ca  mov     [rdx+48h], ax
0x1401385ce  movzx   eax, [rbp+37h+arg_40]
0x1401385d5  ror     ax, 8
0x1401385d9  mov     [rdx+58h], ax
0x1401385dd  mov     dword ptr [rdx], 1
0x1401385e3  mov     [rdx+8], r14b
0x1401385e7  mov     [rdx+40h], r12d
0x1401385eb  mov     [rdx+50h], r12d
0x1401385ef  movzx   eax, byte ptr [rdi+18h]
0x1401385f3  mov     [rdx+28h], al
0x1401385f6  mov     dword ptr [rdx+20h], 1
0x1401385fd  mov     rax, [rdi+8]
0x140138601  add     rax, 10h
0x140138605  mov     dword ptr [rdx+60h], 4
0x14013860c  mov     [rdx+68h], rax
0x140138610  mov     eax, [rbp+37h+arg_80]
0x140138616  mov     [rdx+78h], eax
0x140138619  mov     eax, [rbp+37h+arg_88]
0x14013861f  mov     [rdx+88h], eax
0x140138625  mov     eax, [rbp+37h+arg_90]
0x14013862b  mov     [rdx+0B8h], eax
0x140138631  mov     eax, [rbp+37h+arg_98]
0x140138637  mov     [rdx+0C8h], eax
0x14013863d  mov     eax, [rbp+37h+arg_78]
0x140138643  mov     [rdx+0D8h], eax
0x140138649  movzx   eax, [rbp+37h+arg_58]
0x140138650  mov     [rdx+98h], al
0x140138656  mov     dword ptr [rdx+70h], 3
0x14013865d  mov     dword ptr [rdx+80h], 3
0x140138667  mov     dword ptr [rdx+0B0h], 3
0x140138671  mov     dword ptr [rdx+0C0h], 3
0x14013867b  mov     dword ptr [rdx+0D0h], 3
0x140138685  mov     dword ptr [rdx+90h], 1
0x14013868f  mov     rax, [rdi+10h]
0x140138693  mov     rcx, [rax]
0x140138696  mov     rax, [rsp+130h+var_D8]
0x14013869b  mov     [rdx+38h], rax
0x14013869f  mov     dword ptr [rdx+10h], 0Bh
0x1401386a6  mov     [rdx+18h], rcx
0x1401386aa  mov     dword ptr [rdx+30h], 0Bh
0x1401386b1  cmp     r14d, 1
0x1401386b5  jz      loc_140138564
0x1401386bb  cmp     r14d, 3Ah ; ':'
0x1401386bf  jnz     loc_14013857B
0x1401386c5  mov     rcx, [rbp+37h+arg_60]
0x1401386cc  mov     dword ptr [rdx+0A0h], 3
0x1401386d6  mov     [rdx+0A8h], ebx
0x1401386dc  mov     dword ptr [rdx+0E0h], 0Ch
0x1401386e6  movzx   eax, byte ptr [rcx+4]
0x1401386ea  mov     [rdx+48h], ax
0x1401386ee  movzx   eax, byte ptr [rcx+5]
0x1401386f2  mov     [rdx+58h], ax
0x1401386f6  lea     rax, [rbp+37h+P]
0x1401386fa  mov     [rdx+0E8h], rax
0x140138701  mov     rax, [rdi+8]
0x140138705  mov     rcx, [rax]
0x140138708  mov     eax, [rcx]
0x14013870a  mov     dword ptr [rdx+0F0h], 3
0x140138714  mov     [rdx+0F8h], eax
0x14013871a  jmp     loc_140138CEC
0x14013871f  movzx   eax, byte ptr [rdi+18h]; jumptable 0000000140138459 case 4
0x140138723  mov     [rdx+18h], al
0x140138726  mov     dword ptr [rdx+10h], 1
0x14013872d  mov     rax, [rdi+8]
0x140138731  add     rax, 10h
0x140138735  mov     dword ptr [rdx+30h], 4
0x14013873c  mov     [rdx+38h], rax
0x140138740  mov     eax, [rbp+37h+arg_80]
0x140138746  mov     [rdx+48h], eax
0x140138749  mov     eax, [rbp+37h+arg_88]
0x14013874f  mov     [rdx+58h], eax
0x140138752  mov     eax, [rbp+37h+arg_90]
0x140138758  mov     [rdx+78h], eax
0x14013875b  mov     eax, [rbp+37h+arg_98]
0x140138761  mov     [rdx+88h], eax
0x140138767  mov     dword ptr [rdx+40h], 3
0x14013876e  mov     dword ptr [rdx+50h], 3
0x140138775  mov     dword ptr [rdx+70h], 3
0x14013877c  mov     dword ptr [rdx+80h], 3
0x140138786  mov     dword ptr [rdx+60h], 3
0x14013878d  mov     [rdx+68h], ebx
0x140138790  mov     rax, [rdi+10h]
0x140138794  mov     rcx, [rax]
0x140138797  mov     eax, [rcx]
0x140138799  bswap   eax
0x14013879b  mov     [rdx+8], eax
0x14013879e  mov     rax, [rsp+130h+var_D8]
0x1401387a3  mov     dword ptr [rdx], 3
0x1401387a9  mov     eax, [rax]
0x1401387ab  bswap   eax
0x1401387ad  mov     [rdx+28h], eax
0x1401387b0  mov     dword ptr [rdx+20h], 3
0x1401387b7  mov     rax, [rdi+8]
0x1401387bb  mov     rcx, [rax]
0x1401387be  mov     eax, [rcx]
0x1401387c0  mov     dword ptr [rdx+90h], 3
0x1401387ca  mov     [rdx+98h], eax
0x1401387d0  jmp     loc_140138CEC
0x1401387d5  movzx   eax, byte ptr [rdi+18h]; jumptable 0000000140138459 case 6
0x1401387d9  mov     [rdx+18h], al
0x1401387dc  mov     dword ptr [rdx+10h], 1
0x1401387e3  mov     rax, [rdi+8]
0x1401387e7  add     rax, 10h
0x1401387eb  mov     dword ptr [rdx+30h], 4
0x1401387f2  mov     [rdx+38h], rax
0x1401387f6  mov     eax, [rbp+37h+arg_80]
0x1401387fc  mov     [rdx+48h], eax
0x1401387ff  mov     eax, [rbp+37h+arg_88]
0x140138805  mov     [rdx+58h], eax
0x140138808  mov     eax, [rbp+37h+arg_90]
0x14013880e  mov     [rdx+78h], eax
0x140138811  mov     eax, [rbp+37h+arg_98]
0x140138817  mov     [rdx+88h], eax
0x14013881d  mov     dword ptr [rdx+40h], 3
0x140138824  mov     dword ptr [rdx+50h], 3
0x14013882b  mov     dword ptr [rdx+70h], 3
0x140138832  mov     dword ptr [rdx+80h], 3
0x14013883c  mov     dword ptr [rdx+60h], 3
0x140138843  mov     [rdx+68h], ebx
0x140138846  mov     rax, [rdi+10h]
0x14013884a  mov     rcx, [rax]
0x14013884d  mov     rax, [rsp+130h+var_D8]
0x140138852  mov     [rdx+28h], rax
0x140138856  mov     dword ptr [rdx], 0Bh
0x14013885c  mov     [rdx+8], rcx
0x140138860  mov     dword ptr [rdx+20h], 0Bh
0x140138867  jmp     loc_1401387B7
0x14013886c  movzx   eax, [rbp+37h+arg_38]; jumptable 0000000140138459 case 12
0x140138870  mov     r14d, [rbp+37h+arg_28]
0x140138874  ror     ax, 8
0x140138878  mov     [rdx+48h], ax
0x14013887c  movzx   eax, [rbp+37h+arg_40]
  ... truncated ...
```
