# ProcessInboundTransportLayerClassify

- ea: `0x1401319c0`
- end: `0x1401327d3`
- name: `ProcessInboundTransportLayerClassify`
- size: `3603`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400974c0`

## callees

- `0x14004c7d0`
- `0x1400504b0`
- `0x1400fff20`
- `0x1401319c0`
- `0x14015058c`
- `0x1401506e4`
- `0x140193d04`
- `0x140194254`
- `0x140196d08`
- `0x1401bf390`
- `0x140260c08`
- `0x14026e7d8`
- `0x140276b0c`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1401323d5`
- `ntoskrnl!MmBadPointer` at `0x140132473`
- `ntoskrnl!ExFreePoolWithTag` at `0x140132749`
- `ntoskrnl!ExFreePoolWithTag` at `0x140132749`
- `NETIO!WfpNblInfoGet` at `0x1401323b9`
- `NETIO!WfpNblInfoGet` at `0x140132462`
- `NETIO!WfpNblInfoGet` at `0x1401323b9`
- `NETIO!WfpNblInfoGet` at `0x140132462`
- `NETIO!KfdReleaseCachedFilters` at `0x14013252d`
- `NETIO!KfdReleaseCachedFilters` at `0x1401325b2`
- `NETIO!KfdReleaseCachedFilters` at `0x14013252d`
- `NETIO!KfdReleaseCachedFilters` at `0x1401325b2`
- `NETIO!KfdClassify` at `0x1401323a5`
- `NETIO!KfdClassify` at `0x1401324c6`
- `NETIO!KfdClassify` at `0x1401323a5`
- `NETIO!KfdClassify` at `0x1401324c6`

## pseudocode

```c
__int64 __fastcall ProcessInboundTransportLayerClassify(
        unsigned __int16 a1,
        __int64 a2,
        int a3,
        __int16 a4,
        __int16 a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        _DWORD *a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        int a18)
{
  int v20; // ebx
  _DWORD *v22; // rdx
  unsigned __int16 v23; // r15
  __int64 v24; // rbx
  unsigned int v25; // esi
  __int64 v26; // rax
  int v27; // edi
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  _DWORD *v36; // rcx
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int16 v44; // ax
  __int64 v45; // rax
  int v46; // r12d
  _QWORD *v47; // rax
  __int64 v48; // rdx
  struct _DEVICE_OBJECT *v49; // r8
  __int64 NsConnEntryFromInboundContext; // rax
  char v51; // cl
  __int64 v52; // r13
  _DWORD *v53; // rax
  _QWORD *v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  __int16 RemoteWirePortFromNsConnEntry; // ax
  _DWORD *v58; // rcx
  int v59; // edi
  PVOID v60; // rcx
  __int64 v62; // [rsp+28h] [rbp-D8h]
  _WORD v66[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+64h] [rbp-9Ch]
  _DWORD *v68; // [rsp+68h] [rbp-98h]
  __int64 v69[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID P[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD *v71; // [rsp+90h] [rbp-70h]
  __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  __int128 v73; // [rsp+A0h] [rbp-60h]
  __int128 v74; // [rsp+B0h] [rbp-50h]
  __int64 v75; // [rsp+C0h] [rbp-40h]
  _OWORD v76[9]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v77; // [rsp+158h] [rbp+58h]
  __int64 v78[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v79; // [rsp+170h] [rbp+70h]
  __int64 v80; // [rsp+180h] [rbp+80h]

  v66[1] = 0;
  LODWORD(v80) = 0;
  v75 = 0;
  v20 = a1;
  v69[1] = (__int64)v69;
  v69[0] = (__int64)v69;
  *(_QWORD *)(a15 + 8) = &v72;
  v71 = a14;
  v66[0] = a1;
  v67 = 15;
  v68 = a14;
  v72 = a2;
  *(_OWORD *)v78 = 0;
  v79 = 0;
  v73 = 0;
  v74 = 0;
  *(_OWORD *)P = 0;
  if ( a17 )
    *(_QWORD *)(a15 + 384) = a17 + 16;
  if ( a2 && (*(_DWORD *)(a2 + 40) == 6 && (*(_DWORD *)(a2 + 48) & 0x10) == 0 || !*(_BYTE *)(a2 + 618)) )
    *(_QWORD *)(a15 + 512) = v69;
  WfpAleCopySecurityRealmIdFromEndpoint((PKSPIN_LOCK)a2);
  v22 = v68;
  v23 = 2;
  switch ( v20 )
  {
    case 0:
      v24 = a7;
      v25 = 1;
      v27 = a18;
      *((_BYTE *)v68 + 40) = *(_BYTE *)(a7 + 24);
      v22[8] = 1;
      v40 = *(_QWORD *)(a7 + 8);
      v22[12] = 4;
      *((_QWORD *)v22 + 7) = v40 + 16;
      v22[18] = a10;
      v22[22] = a11;
      v22[30] = a12;
      v22[34] = a13;
      v22[16] = 3;
      v22[20] = 3;
      v22[28] = 3;
      v22[32] = 3;
      v22[24] = 3;
      v22[26] = a18;
      v22[2] = _byteswap_ulong(***(_DWORD ***)(a7 + 16));
      *v22 = 3;
      v22[6] = _byteswap_ulong(*a8);
      v22[4] = 3;
      goto LABEL_16;
    case 2:
      v25 = 1;
      v24 = a7;
      v27 = a18;
      v68[18] = a10;
      v22[22] = a11;
      v22[30] = a12;
      v22[34] = a13;
      v22[16] = 3;
      v22[20] = 3;
      v22[28] = 3;
      v22[32] = 3;
      v22[24] = 3;
      v22[26] = a18;
      *((_BYTE *)v22 + 40) = *(_BYTE *)(a7 + 24);
      v22[8] = 1;
      v41 = *(_QWORD *)(a7 + 8);
      v22[12] = 4;
      *((_QWORD *)v22 + 7) = v41 + 16;
      v42 = **(_QWORD **)(a7 + 16);
      *((_QWORD *)v22 + 3) = a8;
      *v22 = 11;
      *((_QWORD *)v22 + 1) = v42;
      v22[4] = 11;
      goto LABEL_16;
    case 4:
      v24 = a7;
      v25 = 1;
      v27 = a18;
      *((_BYTE *)v68 + 24) = *(_BYTE *)(a7 + 24);
      v22[4] = 1;
      v31 = *(_QWORD *)(a7 + 8);
      v22[12] = 4;
      *((_QWORD *)v22 + 7) = v31 + 16;
      v22[18] = a10;
      v22[22] = a11;
      v22[30] = a12;
      v22[34] = a13;
      v22[16] = 3;
      v22[20] = 3;
      v22[28] = 3;
      v22[32] = 3;
      v22[24] = 3;
      v22[26] = a18;
      v22[2] = _byteswap_ulong(***(_DWORD ***)(a7 + 16));
      *v22 = 3;
      v22[10] = _byteswap_ulong(*a8);
      v22[8] = 3;
      goto LABEL_16;
    case 6:
      v24 = a7;
      v25 = 1;
      v27 = a18;
      *((_BYTE *)v68 + 24) = *(_BYTE *)(a7 + 24);
      v22[4] = 1;
      v33 = *(_QWORD *)(a7 + 8);
      v22[12] = 4;
      *((_QWORD *)v22 + 7) = v33 + 16;
      v22[18] = a10;
      v22[22] = a11;
      v22[30] = a12;
      v22[34] = a13;
      v22[16] = 3;
      v22[20] = 3;
      v22[28] = 3;
      v22[32] = 3;
      v22[24] = 3;
      v22[26] = a18;
      v34 = **(_QWORD **)(a7 + 16);
      *((_QWORD *)v22 + 5) = a8;
      *v22 = 11;
      *((_QWORD *)v22 + 1) = v34;
      v22[8] = 11;
LABEL_16:
      v32 = ***(_DWORD ***)(v24 + 8);
      v22[36] = 3;
      v22[38] = v32;
      goto LABEL_31;
    case 12:
      v24 = a7;
      v25 = 1;
      *((_WORD *)v68 + 36) = __ROR2__(a4, 8);
      *((_WORD *)v22 + 44) = __ROR2__(a5, 8);
      *v22 = 1;
      *((_BYTE *)v22 + 8) = a3;
      v22[16] = 2;
      v22[20] = 2;
      *((_BYTE *)v22 + 56) = *(_BYTE *)(a7 + 24);
      v22[12] = 1;
      v35 = *(_QWORD *)(a7 + 8) + 16LL;
      v22[24] = 4;
      *((_QWORD *)v22 + 13) = v35;
      v22[30] = a10;
      v22[34] = a11;
      v22[42] = a12;
      v22[46] = a13;
      v22[50] = a9;
      v22[28] = 3;
      v22[32] = 3;
      v22[40] = 3;
      v22[44] = 3;
      v22[48] = 3;
      v36 = v71;
      v71[6] = _byteswap_ulong(***(_DWORD ***)(a7 + 16));
      v36[4] = 3;
      LODWORD(v35) = *a8;
      v36[8] = 3;
      v36[10] = _byteswap_ulong(v35);
      if ( a3 != 1 && a3 != 58 )
        goto LABEL_22;
      v22[16] = 2;
      v22[20] = 2;
LABEL_21:
      *((_WORD *)v22 + 36) = *(unsigned __int8 *)(a6 + 4);
      *((_WORD *)v22 + 44) = *(unsigned __int8 *)(a6 + 5);
LABEL_22:
      v27 = a18;
      *((_QWORD *)v22 + 27) = P;
      v22[36] = 3;
      v22[38] = a18;
      v22[52] = 12;
      v37 = ***(_DWORD ***)(v24 + 8);
      v22[56] = 3;
      v22[58] = v37;
      goto LABEL_31;
    case 14:
      v24 = a7;
      v25 = 1;
      *((_WORD *)v68 + 36) = __ROR2__(a4, 8);
      *((_WORD *)v22 + 44) = __ROR2__(a5, 8);
      *v22 = 1;
      *((_BYTE *)v22 + 8) = a3;
      v22[16] = 2;
      v22[20] = 2;
      *((_BYTE *)v22 + 56) = *(_BYTE *)(a7 + 24);
      v22[12] = 1;
      v38 = *(_QWORD *)(a7 + 8) + 16LL;
      v22[24] = 4;
      *((_QWORD *)v22 + 13) = v38;
      v22[30] = a10;
      v22[34] = a11;
      v22[42] = a12;
      v22[46] = a13;
      v22[50] = a9;
      v22[28] = 3;
      v22[32] = 3;
      v22[40] = 3;
      v22[44] = 3;
      v22[48] = 3;
      v39 = **(_QWORD **)(a7 + 16);
      *((_QWORD *)v22 + 5) = a8;
      v22[4] = 11;
      *((_QWORD *)v22 + 3) = v39;
      v22[8] = 11;
      if ( a3 == 1 || a3 == 58 )
        goto LABEL_21;
      goto LABEL_22;
    case 16:
      v24 = a7;
      v25 = 1;
      *((_WORD *)v68 + 36) = __ROR2__(a4, 8);
      *((_WORD *)v22 + 44) = __ROR2__(a5, 8);
      *v22 = 1;
      *((_BYTE *)v22 + 8) = a3;
      v22[16] = 2;
      v22[20] = 2;
      *((_BYTE *)v22 + 40) = *(_BYTE *)(a7 + 24);
      v22[8] = 1;
      v26 = *(_QWORD *)(a7 + 8);
      v22[24] = 4;
      *((_QWORD *)v22 + 13) = v26 + 16;
      v22[30] = a10;
      v22[34] = a11;
      v22[46] = a12;
      v22[50] = a13;
      v22[54] = a9;
      v22[28] = 3;
      v22[32] = 3;
      v22[44] = 3;
      v22[48] = 3;
      v22[52] = 3;
      v22[36] = 1;
      *((_BYTE *)v22 + 152) = 0;
      v22[6] = _byteswap_ulong(***(_DWORD ***)(a7 + 16));
      v22[4] = 3;
      v22[14] = _byteswap_ulong(*a8);
      v22[12] = 3;
      goto LABEL_10;
    case 18:
      v24 = a7;
      v25 = 1;
      *((_WORD *)v68 + 36) = __ROR2__(a4, 8);
      *((_WORD *)v22 + 44) = __ROR2__(a5, 8);
      *v22 = 1;
      *((_BYTE *)v22 + 8) = a3;
      v22[16] = 2;
      v22[20] = 2;
      *((_BYTE *)v22 + 40) = *(_BYTE *)(a7 + 24);
      v22[8] = 1;
      v29 = *(_QWORD *)(a7 + 8);
      v22[24] = 4;
      *((_QWORD *)v22 + 13) = v29 + 16;
      v22[30] = a10;
      v22[34] = a11;
      v22[46] = a12;
      v22[50] = a13;
      v22[54] = a9;
      v22[28] = 3;
      v22[32] = 3;
      v22[44] = 3;
      v22[48] = 3;
      v22[52] = 3;
      v22[36] = 1;
      *((_BYTE *)v22 + 152) = 0;
      v30 = **(_QWORD **)(a7 + 16);
      *((_QWORD *)v22 + 7) = a8;
      v22[4] = 11;
      *((_QWORD *)v22 + 3) = v30;
      v22[12] = 11;
LABEL_10:
      if ( a3 == 1 || a3 == 58 )
      {
        *((_WORD *)v22 + 36) = *(unsigned __int8 *)(a6 + 4);
        *((_WORD *)v22 + 44) = *(unsigned __int8 *)(a6 + 5);
      }
      v27 = a18;
      *((_QWORD *)v22 + 29) = P;
      v22[40] = 3;
      v22[42] = a18;
      v22[56] = 12;
      v28 = ***(_DWORD ***)(v24 + 8);
      v22[60] = 3;
      v22[62] = v28;
      goto LABEL_31;
    case 70:
      v24 = a7;
      v68[2] = _byteswap_ulong(***(_DWORD ***)(a7 + 16));
      *v22 = 3;
      v22[6] = _byteswap_ulong(*a8);
      v22[4] = 3;
      goto LABEL_30;
    case 71:
      v24 = a7;
      v43 = **(_QWORD **)(a7 + 16);
      *((_QWORD *)v68 + 3) = a8;
      *v22 = 11;
      *((_QWORD *)v22 + 1) = v43;
      v22[4] = 11;
LABEL_30:
      v27 = a18;
      v44 = __ROR2__(a4, 8);
      v25 = 1;
      *((_WORD *)v22 + 20) = v44;
      *((_WORD *)v22 + 28) = __ROR2__(a5, 8);
      v22[12] = 2;
      v22[8] = 2;
      v45 = *(_QWORD *)(v24 + 8);
      v22[16] = 4;
      *((_QWORD *)v22 + 9) = v45 + 16;
      v22[22] = a10;
      v22[26] = a11;
      v22[38] = a12;
      v22[42] = a13;
      v22[20] = 3;
      v22[24] = 3;
      v22[28] = 3;
      v22[30] = 1;
      v22[32] = 3;
      v22[34] = a18;
      v22[36] = 3;
      v22[40] = 3;
      v22[46] = ***(_DWORD ***)(v24 + 8);
      v22[44] = 3;
LABEL_31:
      v46 = KfdClassify(a1, v66, a15, a16, 0, v78);
      v47 = (_QWORD *)WfpNblInfoGet(a16);
      v49 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
      if ( !v47
        || v47 == MmBadPointer
        || (v48 = v47[3]) == 0
        || (NsConnEntryFromInboundContext = IPSecGetNsConnEntryFromInboundContext(v47[3])) == 0
        || (v51 = *(_BYTE *)(NsConnEntryFromInboundContext + 64), v51 != 6) && v51 != 17
        || *(_WORD *)(NsConnEntryFromInboundContext + 66) == *(_WORD *)(NsConnEntryFromInboundContext + 68)
        || (unsigned int)IPSecCheckInboundContextVerified(v48) )
      {
        v59 = a3;
        if ( a3 == 1 || a3 == 58 || (unsigned int)(*(_DWORD *)(v24 + 24) - 3) <= 1 || (__int64 *)v69[0] == v69 )
        {
          if ( !*(_DWORD *)(a15 + 536) )
            goto LABEL_59;
        }
        else
        {
          if ( !*(_DWORD *)(a15 + 536) )
          {
LABEL_59:
            v52 = a16;
            goto LABEL_60;
          }
          if ( (int)TlShimCacheMatchedFilterList((PKSPIN_LOCK)a2, (__int64)v69, v62) >= 0 )
          {
LABEL_58:
            v49 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
            goto LABEL_59;
          }
        }
        KfdReleaseCachedFilters(v69);
        goto LABEL_58;
      }
      v52 = a16;
      IPsecGetNattWireRemotePortInbound(a16);
      v53 = v68;
      v68[36] = 3;
      v53[38] = v27 | 0x80;
      v54 = (_QWORD *)WfpNblInfoGet(a16);
      if ( !v54 || v54 == MmBadPointer )
        v55 = 0;
      else
        v55 = v54[3];
      v56 = IPSecGetNsConnEntryFromInboundContext(v55);
      RemoteWirePortFromNsConnEntry = IPSecGetRemoteWirePortFromNsConnEntry(v56);
      v58 = v68;
      *((_WORD *)v68 + 44) = __ROR2__(RemoteWirePortFromNsConnEntry, 8);
      v58[20] = 2;
      v46 = KfdClassify(a1, v66, a15, a16, 0, v78);
      if ( v46 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sDd(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          (_DWORD)WPP_GLOBAL_Control,
          (unsigned int)"ProcessIPsecNattTransportLayerReclassifyInbound",
          232,
          v46);
      }
      if ( *(_DWORD *)(a15 + 536) )
        KfdReleaseCachedFilters(v69);
      v59 = a3;
      v49 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
LABEL_60:
      if ( (v46 & 0xC0000000) == 0xC0000000 )
      {
        *(_OWORD *)v78 = 0;
        LODWORD(v78[0]) = 4097;
        v79 = 0;
        v80 = 0;
      }
      else if ( LODWORD(v78[0]) != 4097 )
      {
        goto LABEL_78;
      }
      if ( (BYTE12(v79) & 1) != 0 )
      {
        v25 = 2;
      }
      else
      {
        v25 = 0;
        if ( WPP_GLOBAL_Control != v49
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sDD(
            WPP_GLOBAL_Control->AttachedDevice,
            v48,
            (_DWORD)v49,
            (unsigned int)"ProcessInboundTransportLayerClassify",
            29,
            0);
        }
        if ( (*(_DWORD *)(v52 + 136) & 0x400000) != 0 )
        {
          memset(v76, 0, sizeof(v76));
          v77 = 0;
          if ( !IPsecPopulateAleDiscardState(v52, v76) && (unsigned int)(LODWORD(v76[0]) - 2) <= 1 )
          {
            if ( a1 != 12 )
              v23 = 23;
            WfpCacheIpsecStateOnDiscard(v23, v24, (int)a8, v59, a4, a5, v52, *(_DWORD *)(a15 + 44), v76);
          }
        }
        *(_QWORD *)(a15 + 512) = 0;
        WfpShimIndicateDiscardGeneral(a1, (unsigned int)v66, a15, v52, 0, (__int64)v78);
      }
LABEL_78:
      v60 = P[1];
      *(_QWORD *)(a15 + 8) = 0;
      if ( v60 )
        ExFreePoolWithTag(v60, 0x52537049u);
      P[1] = 0;
      LODWORD(P[0]) = 0;
      if ( v25 != 1
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v48,
          (_DWORD)v49,
          (unsigned int)"ProcessInboundTransportLayerClassify",
          93,
          v25);
      }
      return v25;
    default:
      __fastfail(5u);
  }
}

```

## disassembly

```asm
0x1401319c0  push    rbp
0x1401319c2  push    rbx
0x1401319c3  push    rsi
0x1401319c4  push    rdi
0x1401319c5  push    r12
0x1401319c7  push    r13
0x1401319c9  push    r14
0x1401319cb  lea     rbp, [rsp-90h]
0x1401319d3  sub     rsp, 190h
0x1401319da  mov     rax, cs:__security_cookie
0x1401319e1  xor     rax, rsp
0x1401319e4  mov     [rbp+0C0h+var_38], rax
0x1401319eb  mov     r14, [rbp+0C0h+arg_70]
0x1401319f2  xor     eax, eax
0x1401319f4  mov     r12, [rbp+0C0h+arg_78]
0x1401319fb  xorps   xmm0, xmm0
0x1401319fe  mov     [rsp+1C0h+var_15E], ax
0x140131a03  xorps   xmm1, xmm1
0x140131a06  mov     dword ptr [rbp+0C0h+var_40], eax
0x140131a0c  movzx   esi, r9w
0x140131a10  mov     [rbp+0C0h+var_100], rax
0x140131a14  mov     edi, r8d
0x140131a17  movzx   ebx, cx
0x140131a1a  lea     rax, [rsp+1C0h+var_150]
0x140131a1f  mov     rcx, [rbp+0C0h+arg_68]
0x140131a26  mov     r13, rdx
0x140131a29  mov     [rsp+1C0h+var_148], rax
0x140131a2e  lea     rax, [rsp+1C0h+var_150]
0x140131a33  mov     [rsp+1C0h+var_150], rax
0x140131a38  lea     rax, [rbp+0C0h+var_128]
0x140131a3c  mov     [r14+8], rax
0x140131a40  mov     rax, [rbp+0C0h+arg_80]
0x140131a47  mov     [rsp+1C0h+var_170], r9w
0x140131a4d  mov     [rsp+1C0h+var_16C], r8d
0x140131a52  mov     [rsp+1C0h+var_16E], bx
0x140131a57  mov     [rbp+0C0h+var_130], rcx
0x140131a5b  mov     [rsp+1C0h+var_168], r12
0x140131a60  mov     [rsp+1C0h+var_160], bx
0x140131a65  mov     [rsp+1C0h+var_15C], 0Fh
0x140131a6d  mov     [rsp+1C0h+var_158], rcx
0x140131a72  mov     [rbp+0C0h+var_128], rdx
0x140131a76  movups  xmmword ptr [rbp+0C0h+var_60], xmm0
0x140131a7a  movups  [rbp+0C0h+var_50], xmm0
0x140131a7e  movdqu  [rbp+0C0h+var_120], xmm0
0x140131a83  movdqu  [rbp+0C0h+var_110], xmm1
0x140131a88  movups  xmmword ptr [rbp+0C0h+P], xmm0
0x140131a8c  test    rax, rax
0x140131a8f  jz      short loc_140131A9C
0x140131a91  add     rax, 10h
0x140131a95  mov     [r14+180h], rax
0x140131a9c  test    r13, r13
0x140131a9f  jz      short loc_140131AC3
0x140131aa1  cmp     dword ptr [rdx+28h], 6
0x140131aa5  jnz     short loc_140131AAE
0x140131aa7  mov     eax, [rdx+30h]
0x140131aaa  test    al, 10h
0x140131aac  jz      short loc_140131AB7
0x140131aae  cmp     byte ptr [rdx+26Ah], 0
0x140131ab5  jnz     short loc_140131AC3
0x140131ab7  lea     rax, [rsp+1C0h+var_150]
0x140131abc  mov     [r14+200h], rax
0x140131ac3  lea     rdx, [rbp+0C0h+P]
0x140131ac7  mov     [rsp+1C0h+arg_10], r15
0x140131acf  mov     rcx, r13; SpinLock
0x140131ad2  call    WfpAleCopySecurityRealmIdFromEndpoint
0x140131ad7  cmp     ebx, 47h; switch 72 cases
0x140131ada  ja      def_140131B06; jumptable 0000000140131B06 default case, cases 1,3,5,7-11,13,15,17,19-69
0x140131ae0  mov     rdx, [rsp+1C0h+var_158]
0x140131ae5  lea     r8, cs:140000000h
0x140131aec  movzx   eax, ds:(byte_1401F04E3 - 140000000h)[r8+rbx]
0x140131af5  mov     r15d, 2
0x140131afb  mov     ecx, ds:(jpt_140131B06 - 140000000h)[r8+rax*4]
0x140131b03  add     rcx, r8
0x140131b06  jmp     rcx; switch jump
0x140131b0c  mov     rbx, [rbp+0C0h+arg_30]; jumptable 0000000140131B06 case 16
0x140131b13  mov     esi, 1
0x140131b18  movzx   eax, [rsp+1C0h+var_170]
0x140131b1d  ror     ax, 8
0x140131b21  mov     [rdx+48h], ax
0x140131b25  movzx   eax, [rbp+0C0h+arg_20]
0x140131b2c  ror     ax, 8
0x140131b30  mov     [rdx+58h], ax
0x140131b34  mov     [rdx], esi
0x140131b36  mov     [rdx+8], dil
0x140131b3a  mov     [rdx+40h], r15d
0x140131b3e  mov     [rdx+50h], r15d
0x140131b42  movzx   eax, byte ptr [rbx+18h]
0x140131b46  mov     [rdx+28h], al
0x140131b49  mov     [rdx+20h], esi
0x140131b4c  mov     rax, [rbx+8]
0x140131b50  add     rax, 10h
0x140131b54  mov     dword ptr [rdx+60h], 4
0x140131b5b  mov     [rdx+68h], rax
0x140131b5f  mov     eax, [rbp+0C0h+arg_48]
0x140131b65  mov     [rdx+78h], eax
0x140131b68  mov     eax, [rbp+0C0h+arg_50]
0x140131b6e  mov     [rdx+88h], eax
0x140131b74  mov     eax, [rbp+0C0h+arg_58]
0x140131b7a  mov     [rdx+0B8h], eax
0x140131b80  mov     eax, [rbp+0C0h+arg_60]
0x140131b86  mov     [rdx+0C8h], eax
0x140131b8c  mov     eax, [rbp+0C0h+arg_40]
0x140131b92  mov     [rdx+0D8h], eax
0x140131b98  mov     dword ptr [rdx+70h], 3
0x140131b9f  mov     dword ptr [rdx+80h], 3
0x140131ba9  mov     dword ptr [rdx+0B0h], 3
0x140131bb3  mov     dword ptr [rdx+0C0h], 3
0x140131bbd  mov     dword ptr [rdx+0D0h], 3
0x140131bc7  mov     [rdx+90h], esi
0x140131bcd  mov     byte ptr [rdx+98h], 0
0x140131bd4  mov     rax, [rbx+10h]
0x140131bd8  mov     rcx, [rax]
0x140131bdb  mov     eax, [rcx]
0x140131bdd  bswap   eax
0x140131bdf  mov     [rdx+18h], eax
0x140131be2  mov     rax, [rbp+0C0h+arg_38]
0x140131be9  mov     dword ptr [rdx+10h], 3
0x140131bf0  mov     eax, [rax]
0x140131bf2  bswap   eax
0x140131bf4  mov     [rdx+38h], eax
0x140131bf7  mov     dword ptr [rdx+30h], 3
0x140131bfe  cmp     edi, esi
0x140131c00  jz      short loc_140131C07
0x140131c02  cmp     edi, 3Ah ; ':'
0x140131c05  jnz     short loc_140131C1E
0x140131c07  mov     rcx, [rbp+0C0h+arg_28]
0x140131c0e  movzx   eax, byte ptr [rcx+4]
0x140131c12  mov     [rdx+48h], ax
0x140131c16  movzx   eax, byte ptr [rcx+5]
0x140131c1a  mov     [rdx+58h], ax
0x140131c1e  mov     edi, [rbp+0C0h+arg_88]
0x140131c24  lea     rax, [rbp+0C0h+P]
0x140131c28  mov     [rdx+0E8h], rax
0x140131c2f  mov     dword ptr [rdx+0A0h], 3
0x140131c39  mov     [rdx+0A8h], edi
0x140131c3f  mov     dword ptr [rdx+0E0h], 0Ch
0x140131c49  mov     rax, [rbx+8]
0x140131c4d  mov     rcx, [rax]
0x140131c50  mov     eax, [rcx]
0x140131c52  mov     dword ptr [rdx+0F0h], 3
0x140131c5c  mov     [rdx+0F8h], eax
0x140131c62  jmp     loc_140132383
0x140131c67  mov     rbx, [rbp+0C0h+arg_30]; jumptable 0000000140131B06 case 18
0x140131c6e  mov     esi, 1
0x140131c73  movzx   eax, [rsp+1C0h+var_170]
0x140131c78  ror     ax, 8
0x140131c7c  mov     [rdx+48h], ax
0x140131c80  movzx   eax, [rbp+0C0h+arg_20]
0x140131c87  ror     ax, 8
0x140131c8b  mov     [rdx+58h], ax
0x140131c8f  mov     [rdx], esi
0x140131c91  mov     [rdx+8], dil
0x140131c95  mov     [rdx+40h], r15d
0x140131c99  mov     [rdx+50h], r15d
0x140131c9d  movzx   eax, byte ptr [rbx+18h]
0x140131ca1  mov     [rdx+28h], al
0x140131ca4  mov     [rdx+20h], esi
0x140131ca7  mov     rax, [rbx+8]
0x140131cab  add     rax, 10h
0x140131caf  mov     dword ptr [rdx+60h], 4
0x140131cb6  mov     [rdx+68h], rax
0x140131cba  mov     eax, [rbp+0C0h+arg_48]
0x140131cc0  mov     [rdx+78h], eax
0x140131cc3  mov     eax, [rbp+0C0h+arg_50]
0x140131cc9  mov     [rdx+88h], eax
0x140131ccf  mov     eax, [rbp+0C0h+arg_58]
0x140131cd5  mov     [rdx+0B8h], eax
0x140131cdb  mov     eax, [rbp+0C0h+arg_60]
0x140131ce1  mov     [rdx+0C8h], eax
0x140131ce7  mov     eax, [rbp+0C0h+arg_40]
0x140131ced  mov     [rdx+0D8h], eax
0x140131cf3  mov     dword ptr [rdx+70h], 3
0x140131cfa  mov     dword ptr [rdx+80h], 3
0x140131d04  mov     dword ptr [rdx+0B0h], 3
0x140131d0e  mov     dword ptr [rdx+0C0h], 3
0x140131d18  mov     dword ptr [rdx+0D0h], 3
0x140131d22  mov     [rdx+90h], esi
0x140131d28  mov     byte ptr [rdx+98h], 0
0x140131d2f  mov     rax, [rbx+10h]
0x140131d33  mov     rcx, [rax]
0x140131d36  mov     rax, [rbp+0C0h+arg_38]
0x140131d3d  mov     [rdx+38h], rax
0x140131d41  mov     dword ptr [rdx+10h], 0Bh
0x140131d48  mov     [rdx+18h], rcx
0x140131d4c  mov     dword ptr [rdx+30h], 0Bh
0x140131d53  jmp     loc_140131BFE
0x140131d58  mov     rbx, [rbp+0C0h+arg_30]; jumptable 0000000140131B06 case 4
0x140131d5f  mov     esi, 1
0x140131d64  mov     edi, [rbp+0C0h+arg_88]
0x140131d6a  movzx   eax, byte ptr [rbx+18h]
0x140131d6e  mov     [rdx+18h], al
0x140131d71  mov     [rdx+10h], esi
0x140131d74  mov     rax, [rbx+8]
0x140131d78  add     rax, 10h
0x140131d7c  mov     dword ptr [rdx+30h], 4
0x140131d83  mov     [rdx+38h], rax
0x140131d87  mov     eax, [rbp+0C0h+arg_48]
0x140131d8d  mov     [rdx+48h], eax
0x140131d90  mov     eax, [rbp+0C0h+arg_50]
0x140131d96  mov     [rdx+58h], eax
0x140131d99  mov     eax, [rbp+0C0h+arg_58]
0x140131d9f  mov     [rdx+78h], eax
0x140131da2  mov     eax, [rbp+0C0h+arg_60]
0x140131da8  mov     [rdx+88h], eax
0x140131dae  mov     dword ptr [rdx+40h], 3
0x140131db5  mov     dword ptr [rdx+50h], 3
0x140131dbc  mov     dword ptr [rdx+70h], 3
0x140131dc3  mov     dword ptr [rdx+80h], 3
0x140131dcd  mov     dword ptr [rdx+60h], 3
0x140131dd4  mov     [rdx+68h], edi
0x140131dd7  mov     rax, [rbx+10h]
0x140131ddb  mov     rcx, [rax]
0x140131dde  mov     eax, [rcx]
0x140131de0  bswap   eax
0x140131de2  mov     [rdx+8], eax
0x140131de5  mov     rax, [rbp+0C0h+arg_38]
0x140131dec  mov     dword ptr [rdx], 3
0x140131df2  mov     eax, [rax]
0x140131df4  bswap   eax
0x140131df6  mov     [rdx+28h], eax
0x140131df9  mov     dword ptr [rdx+20h], 3
0x140131e00  mov     rax, [rbx+8]
0x140131e04  mov     rcx, [rax]
0x140131e07  mov     eax, [rcx]
0x140131e09  mov     dword ptr [rdx+90h], 3
0x140131e13  mov     [rdx+98h], eax
0x140131e19  jmp     loc_140132383
0x140131e1e  mov     rbx, [rbp+0C0h+arg_30]; jumptable 0000000140131B06 case 6
0x140131e25  mov     esi, 1
0x140131e2a  mov     edi, [rbp+0C0h+arg_88]
0x140131e30  movzx   eax, byte ptr [rbx+18h]
0x140131e34  mov     [rdx+18h], al
0x140131e37  mov     [rdx+10h], esi
0x140131e3a  mov     rax, [rbx+8]
0x140131e3e  add     rax, 10h
0x140131e42  mov     dword ptr [rdx+30h], 4
0x140131e49  mov     [rdx+38h], rax
0x140131e4d  mov     eax, [rbp+0C0h+arg_48]
0x140131e53  mov     [rdx+48h], eax
0x140131e56  mov     eax, [rbp+0C0h+arg_50]
0x140131e5c  mov     [rdx+58h], eax
0x140131e5f  mov     eax, [rbp+0C0h+arg_58]
0x140131e65  mov     [rdx+78h], eax
0x140131e68  mov     eax, [rbp+0C0h+arg_60]
0x140131e6e  mov     [rdx+88h], eax
0x140131e74  mov     dword ptr [rdx+40h], 3
0x140131e7b  mov     dword ptr [rdx+50h], 3
0x140131e82  mov     dword ptr [rdx+70h], 3
0x140131e89  mov     dword ptr [rdx+80h], 3
0x140131e93  mov     dword ptr [rdx+60h], 3
0x140131e9a  mov     [rdx+68h], edi
0x140131e9d  mov     rax, [rbx+10h]
0x140131ea1  mov     rcx, [rax]
0x140131ea4  mov     rax, [rbp+0C0h+arg_38]
0x140131eab  mov     [rdx+28h], rax
0x140131eaf  mov     dword ptr [rdx], 0Bh
0x140131eb5  mov     [rdx+8], rcx
0x140131eb9  mov     dword ptr [rdx+20h], 0Bh
0x140131ec0  jmp     loc_140131E00
0x140131ec5  mov     rbx, [rbp+0C0h+arg_30]; jumptable 0000000140131B06 case 12
0x140131ecc  mov     esi, 1
0x140131ed1  movzx   eax, [rsp+1C0h+var_170]
0x140131ed6  ror     ax, 8
0x140131eda  mov     [rdx+48h], ax
0x140131ede  movzx   eax, [rbp+0C0h+arg_20]
0x140131ee5  ror     ax, 8
0x140131ee9  mov     [rdx+58h], ax
0x140131eed  mov     [rdx], esi
0x140131eef  mov     [rdx+8], dil
0x140131ef3  mov     [rdx+40h], r15d
0x140131ef7  mov     [rdx+50h], r15d
0x140131efb  movzx   eax, byte ptr [rbx+18h]
0x140131eff  mov     [rdx+38h], al
0x140131f02  mov     [rdx+30h], esi
0x140131f05  mov     rax, [rbx+8]
0x140131f09  add     rax, 10h
0x140131f0d  mov     dword ptr [rdx+60h], 4
0x140131f14  mov     [rdx+68h], rax
0x140131f18  mov     eax, [rbp+0C0h+arg_48]
0x140131f1e  mov     [rdx+78h], eax
0x140131f21  mov     eax, [rbp+0C0h+arg_50]
0x140131f27  mov     [rdx+88h], eax
0x140131f2d  mov     eax, [rbp+0C0h+arg_58]
0x140131f33  mov     [rdx+0A8h], eax
0x140131f39  mov     eax, [rbp+0C0h+arg_60]
0x140131f3f  mov     [rdx+0B8h], eax
0x140131f45  mov     eax, [rbp+0C0h+arg_40]
0x140131f4b  mov     [rdx+0C8h], eax
0x140131f51  mov     dword ptr [rdx+70h], 3
0x140131f58  mov     dword ptr [rdx+80h], 3
0x140131f62  mov     dword ptr [rdx+0A0h], 3
0x140131f6c  mov     dword ptr [rdx+0B0h], 3
0x140131f76  mov     dword ptr [rdx+0C0h], 3
0x140131f80  mov     rax, [rbx+10h]
0x140131f84  mov     rcx, [rax]
0x140131f87  mov     eax, [rcx]
0x140131f89  mov     rcx, [rbp+0C0h+var_130]
0x140131f8d  bswap   eax
0x140131f8f  mov     [rcx+18h], eax
0x140131f92  mov     rax, [rbp+0C0h+arg_38]
  ... truncated ...
```
