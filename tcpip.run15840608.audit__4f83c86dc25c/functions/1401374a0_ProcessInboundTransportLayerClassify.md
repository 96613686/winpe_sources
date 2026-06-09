# ProcessInboundTransportLayerClassify

- ea: `0x1401374a0`
- end: `0x1401382b3`
- name: `ProcessInboundTransportLayerClassify`
- size: `3603`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14005e2b0`

## callees

- `0x140011220`
- `0x1400bf840`
- `0x1400c0d78`
- `0x1401374a0`
- `0x1401522cc`
- `0x140152424`
- `0x140195ae4`
- `0x140196034`
- `0x140198ad4`
- `0x1401c0fd0`
- `0x140264c08`
- `0x140272b78`
- `0x14027a92c`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140137eb5`
- `ntoskrnl!MmBadPointer` at `0x140137f53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138229`
- `ntoskrnl!ExFreePoolWithTag` at `0x140138229`
- `NETIO!WfpNblInfoGet` at `0x140137e99`
- `NETIO!WfpNblInfoGet` at `0x140137f42`
- `NETIO!WfpNblInfoGet` at `0x140137e99`
- `NETIO!WfpNblInfoGet` at `0x140137f42`
- `NETIO!KfdReleaseCachedFilters` at `0x14013800d`
- `NETIO!KfdReleaseCachedFilters` at `0x140138092`
- `NETIO!KfdReleaseCachedFilters` at `0x14013800d`
- `NETIO!KfdReleaseCachedFilters` at `0x140138092`
- `NETIO!KfdClassify` at `0x140137e85`
- `NETIO!KfdClassify` at `0x140137fa6`
- `NETIO!KfdClassify` at `0x140137e85`
- `NETIO!KfdClassify` at `0x140137fa6`

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
0x1401374a0  push    rbp
0x1401374a2  push    rbx
0x1401374a3  push    rsi
0x1401374a4  push    rdi
0x1401374a5  push    r12
0x1401374a7  push    r13
0x1401374a9  push    r14
0x1401374ab  lea     rbp, [rsp-90h]
0x1401374b3  sub     rsp, 190h
0x1401374ba  mov     rax, cs:__security_cookie
0x1401374c1  xor     rax, rsp
0x1401374c4  mov     [rbp+0C0h+var_38], rax
0x1401374cb  mov     r14, [rbp+0C0h+arg_70]
0x1401374d2  xor     eax, eax
0x1401374d4  mov     r12, [rbp+0C0h+arg_78]
0x1401374db  xorps   xmm0, xmm0
0x1401374de  mov     [rsp+1C0h+var_15E], ax
0x1401374e3  xorps   xmm1, xmm1
0x1401374e6  mov     dword ptr [rbp+0C0h+var_40], eax
0x1401374ec  movzx   esi, r9w
0x1401374f0  mov     [rbp+0C0h+var_100], rax
0x1401374f4  mov     edi, r8d
0x1401374f7  movzx   ebx, cx
0x1401374fa  lea     rax, [rsp+1C0h+var_150]
0x1401374ff  mov     rcx, [rbp+0C0h+arg_68]
0x140137506  mov     r13, rdx
0x140137509  mov     [rsp+1C0h+var_148], rax
0x14013750e  lea     rax, [rsp+1C0h+var_150]
0x140137513  mov     [rsp+1C0h+var_150], rax
0x140137518  lea     rax, [rbp+0C0h+var_128]
0x14013751c  mov     [r14+8], rax
0x140137520  mov     rax, [rbp+0C0h+arg_80]
0x140137527  mov     [rsp+1C0h+var_170], r9w
0x14013752d  mov     [rsp+1C0h+var_16C], r8d
0x140137532  mov     [rsp+1C0h+var_16E], bx
0x140137537  mov     [rbp+0C0h+var_130], rcx
0x14013753b  mov     [rsp+1C0h+var_168], r12
0x140137540  mov     [rsp+1C0h+var_160], bx
0x140137545  mov     [rsp+1C0h+var_15C], 0Fh
0x14013754d  mov     [rsp+1C0h+var_158], rcx
0x140137552  mov     [rbp+0C0h+var_128], rdx
0x140137556  movups  xmmword ptr [rbp+0C0h+var_60], xmm0
0x14013755a  movups  [rbp+0C0h+var_50], xmm0
0x14013755e  movdqu  [rbp+0C0h+var_120], xmm0
0x140137563  movdqu  [rbp+0C0h+var_110], xmm1
0x140137568  movups  xmmword ptr [rbp+0C0h+P], xmm0
0x14013756c  test    rax, rax
0x14013756f  jz      short loc_14013757C
0x140137571  add     rax, 10h
0x140137575  mov     [r14+180h], rax
0x14013757c  test    r13, r13
0x14013757f  jz      short loc_1401375A3
0x140137581  cmp     dword ptr [rdx+28h], 6
0x140137585  jnz     short loc_14013758E
0x140137587  mov     eax, [rdx+30h]
0x14013758a  test    al, 10h
0x14013758c  jz      short loc_140137597
0x14013758e  cmp     byte ptr [rdx+26Ah], 0
0x140137595  jnz     short loc_1401375A3
0x140137597  lea     rax, [rsp+1C0h+var_150]
0x14013759c  mov     [r14+200h], rax
0x1401375a3  lea     rdx, [rbp+0C0h+P]
0x1401375a7  mov     [rsp+1C0h+arg_10], r15
0x1401375af  mov     rcx, r13; SpinLock
0x1401375b2  call    WfpAleCopySecurityRealmIdFromEndpoint
0x1401375b7  cmp     ebx, 47h; switch 72 cases
0x1401375ba  ja      def_1401375E6; jumptable 00000001401375E6 default case, cases 1,3,5,7-11,13,15,17,19-69
0x1401375c0  mov     rdx, [rsp+1C0h+var_158]
0x1401375c5  lea     r8, cs:140000000h
0x1401375cc  movzx   eax, ds:(byte_1401F4193 - 140000000h)[r8+rbx]
0x1401375d5  mov     r15d, 2
0x1401375db  mov     ecx, ds:(jpt_1401375E6 - 140000000h)[r8+rax*4]
0x1401375e3  add     rcx, r8
0x1401375e6  jmp     rcx; switch jump
0x1401375ec  mov     rbx, [rbp+0C0h+arg_30]; jumptable 00000001401375E6 case 16
0x1401375f3  mov     esi, 1
0x1401375f8  movzx   eax, [rsp+1C0h+var_170]
0x1401375fd  ror     ax, 8
0x140137601  mov     [rdx+48h], ax
0x140137605  movzx   eax, [rbp+0C0h+arg_20]
0x14013760c  ror     ax, 8
0x140137610  mov     [rdx+58h], ax
0x140137614  mov     [rdx], esi
0x140137616  mov     [rdx+8], dil
0x14013761a  mov     [rdx+40h], r15d
0x14013761e  mov     [rdx+50h], r15d
0x140137622  movzx   eax, byte ptr [rbx+18h]
0x140137626  mov     [rdx+28h], al
0x140137629  mov     [rdx+20h], esi
0x14013762c  mov     rax, [rbx+8]
0x140137630  add     rax, 10h
0x140137634  mov     dword ptr [rdx+60h], 4
0x14013763b  mov     [rdx+68h], rax
0x14013763f  mov     eax, [rbp+0C0h+arg_48]
0x140137645  mov     [rdx+78h], eax
0x140137648  mov     eax, [rbp+0C0h+arg_50]
0x14013764e  mov     [rdx+88h], eax
0x140137654  mov     eax, [rbp+0C0h+arg_58]
0x14013765a  mov     [rdx+0B8h], eax
0x140137660  mov     eax, [rbp+0C0h+arg_60]
0x140137666  mov     [rdx+0C8h], eax
0x14013766c  mov     eax, [rbp+0C0h+arg_40]
0x140137672  mov     [rdx+0D8h], eax
0x140137678  mov     dword ptr [rdx+70h], 3
0x14013767f  mov     dword ptr [rdx+80h], 3
0x140137689  mov     dword ptr [rdx+0B0h], 3
0x140137693  mov     dword ptr [rdx+0C0h], 3
0x14013769d  mov     dword ptr [rdx+0D0h], 3
0x1401376a7  mov     [rdx+90h], esi
0x1401376ad  mov     byte ptr [rdx+98h], 0
0x1401376b4  mov     rax, [rbx+10h]
0x1401376b8  mov     rcx, [rax]
0x1401376bb  mov     eax, [rcx]
0x1401376bd  bswap   eax
0x1401376bf  mov     [rdx+18h], eax
0x1401376c2  mov     rax, [rbp+0C0h+arg_38]
0x1401376c9  mov     dword ptr [rdx+10h], 3
0x1401376d0  mov     eax, [rax]
0x1401376d2  bswap   eax
0x1401376d4  mov     [rdx+38h], eax
0x1401376d7  mov     dword ptr [rdx+30h], 3
0x1401376de  cmp     edi, esi
0x1401376e0  jz      short loc_1401376E7
0x1401376e2  cmp     edi, 3Ah ; ':'
0x1401376e5  jnz     short loc_1401376FE
0x1401376e7  mov     rcx, [rbp+0C0h+arg_28]
0x1401376ee  movzx   eax, byte ptr [rcx+4]
0x1401376f2  mov     [rdx+48h], ax
0x1401376f6  movzx   eax, byte ptr [rcx+5]
0x1401376fa  mov     [rdx+58h], ax
0x1401376fe  mov     edi, [rbp+0C0h+arg_88]
0x140137704  lea     rax, [rbp+0C0h+P]
0x140137708  mov     [rdx+0E8h], rax
0x14013770f  mov     dword ptr [rdx+0A0h], 3
0x140137719  mov     [rdx+0A8h], edi
0x14013771f  mov     dword ptr [rdx+0E0h], 0Ch
0x140137729  mov     rax, [rbx+8]
0x14013772d  mov     rcx, [rax]
0x140137730  mov     eax, [rcx]
0x140137732  mov     dword ptr [rdx+0F0h], 3
0x14013773c  mov     [rdx+0F8h], eax
0x140137742  jmp     loc_140137E63
0x140137747  mov     rbx, [rbp+0C0h+arg_30]; jumptable 00000001401375E6 case 18
0x14013774e  mov     esi, 1
0x140137753  movzx   eax, [rsp+1C0h+var_170]
0x140137758  ror     ax, 8
0x14013775c  mov     [rdx+48h], ax
0x140137760  movzx   eax, [rbp+0C0h+arg_20]
0x140137767  ror     ax, 8
0x14013776b  mov     [rdx+58h], ax
0x14013776f  mov     [rdx], esi
0x140137771  mov     [rdx+8], dil
0x140137775  mov     [rdx+40h], r15d
0x140137779  mov     [rdx+50h], r15d
0x14013777d  movzx   eax, byte ptr [rbx+18h]
0x140137781  mov     [rdx+28h], al
0x140137784  mov     [rdx+20h], esi
0x140137787  mov     rax, [rbx+8]
0x14013778b  add     rax, 10h
0x14013778f  mov     dword ptr [rdx+60h], 4
0x140137796  mov     [rdx+68h], rax
0x14013779a  mov     eax, [rbp+0C0h+arg_48]
0x1401377a0  mov     [rdx+78h], eax
0x1401377a3  mov     eax, [rbp+0C0h+arg_50]
0x1401377a9  mov     [rdx+88h], eax
0x1401377af  mov     eax, [rbp+0C0h+arg_58]
0x1401377b5  mov     [rdx+0B8h], eax
0x1401377bb  mov     eax, [rbp+0C0h+arg_60]
0x1401377c1  mov     [rdx+0C8h], eax
0x1401377c7  mov     eax, [rbp+0C0h+arg_40]
0x1401377cd  mov     [rdx+0D8h], eax
0x1401377d3  mov     dword ptr [rdx+70h], 3
0x1401377da  mov     dword ptr [rdx+80h], 3
0x1401377e4  mov     dword ptr [rdx+0B0h], 3
0x1401377ee  mov     dword ptr [rdx+0C0h], 3
0x1401377f8  mov     dword ptr [rdx+0D0h], 3
0x140137802  mov     [rdx+90h], esi
0x140137808  mov     byte ptr [rdx+98h], 0
0x14013780f  mov     rax, [rbx+10h]
0x140137813  mov     rcx, [rax]
0x140137816  mov     rax, [rbp+0C0h+arg_38]
0x14013781d  mov     [rdx+38h], rax
0x140137821  mov     dword ptr [rdx+10h], 0Bh
0x140137828  mov     [rdx+18h], rcx
0x14013782c  mov     dword ptr [rdx+30h], 0Bh
0x140137833  jmp     loc_1401376DE
0x140137838  mov     rbx, [rbp+0C0h+arg_30]; jumptable 00000001401375E6 case 4
0x14013783f  mov     esi, 1
0x140137844  mov     edi, [rbp+0C0h+arg_88]
0x14013784a  movzx   eax, byte ptr [rbx+18h]
0x14013784e  mov     [rdx+18h], al
0x140137851  mov     [rdx+10h], esi
0x140137854  mov     rax, [rbx+8]
0x140137858  add     rax, 10h
0x14013785c  mov     dword ptr [rdx+30h], 4
0x140137863  mov     [rdx+38h], rax
0x140137867  mov     eax, [rbp+0C0h+arg_48]
0x14013786d  mov     [rdx+48h], eax
0x140137870  mov     eax, [rbp+0C0h+arg_50]
0x140137876  mov     [rdx+58h], eax
0x140137879  mov     eax, [rbp+0C0h+arg_58]
0x14013787f  mov     [rdx+78h], eax
0x140137882  mov     eax, [rbp+0C0h+arg_60]
0x140137888  mov     [rdx+88h], eax
0x14013788e  mov     dword ptr [rdx+40h], 3
0x140137895  mov     dword ptr [rdx+50h], 3
0x14013789c  mov     dword ptr [rdx+70h], 3
0x1401378a3  mov     dword ptr [rdx+80h], 3
0x1401378ad  mov     dword ptr [rdx+60h], 3
0x1401378b4  mov     [rdx+68h], edi
0x1401378b7  mov     rax, [rbx+10h]
0x1401378bb  mov     rcx, [rax]
0x1401378be  mov     eax, [rcx]
0x1401378c0  bswap   eax
0x1401378c2  mov     [rdx+8], eax
0x1401378c5  mov     rax, [rbp+0C0h+arg_38]
0x1401378cc  mov     dword ptr [rdx], 3
0x1401378d2  mov     eax, [rax]
0x1401378d4  bswap   eax
0x1401378d6  mov     [rdx+28h], eax
0x1401378d9  mov     dword ptr [rdx+20h], 3
0x1401378e0  mov     rax, [rbx+8]
0x1401378e4  mov     rcx, [rax]
0x1401378e7  mov     eax, [rcx]
0x1401378e9  mov     dword ptr [rdx+90h], 3
0x1401378f3  mov     [rdx+98h], eax
0x1401378f9  jmp     loc_140137E63
0x1401378fe  mov     rbx, [rbp+0C0h+arg_30]; jumptable 00000001401375E6 case 6
0x140137905  mov     esi, 1
0x14013790a  mov     edi, [rbp+0C0h+arg_88]
0x140137910  movzx   eax, byte ptr [rbx+18h]
0x140137914  mov     [rdx+18h], al
0x140137917  mov     [rdx+10h], esi
0x14013791a  mov     rax, [rbx+8]
0x14013791e  add     rax, 10h
0x140137922  mov     dword ptr [rdx+30h], 4
0x140137929  mov     [rdx+38h], rax
0x14013792d  mov     eax, [rbp+0C0h+arg_48]
0x140137933  mov     [rdx+48h], eax
0x140137936  mov     eax, [rbp+0C0h+arg_50]
0x14013793c  mov     [rdx+58h], eax
0x14013793f  mov     eax, [rbp+0C0h+arg_58]
0x140137945  mov     [rdx+78h], eax
0x140137948  mov     eax, [rbp+0C0h+arg_60]
0x14013794e  mov     [rdx+88h], eax
0x140137954  mov     dword ptr [rdx+40h], 3
0x14013795b  mov     dword ptr [rdx+50h], 3
0x140137962  mov     dword ptr [rdx+70h], 3
0x140137969  mov     dword ptr [rdx+80h], 3
0x140137973  mov     dword ptr [rdx+60h], 3
0x14013797a  mov     [rdx+68h], edi
0x14013797d  mov     rax, [rbx+10h]
0x140137981  mov     rcx, [rax]
0x140137984  mov     rax, [rbp+0C0h+arg_38]
0x14013798b  mov     [rdx+28h], rax
0x14013798f  mov     dword ptr [rdx], 0Bh
0x140137995  mov     [rdx+8], rcx
0x140137999  mov     dword ptr [rdx+20h], 0Bh
0x1401379a0  jmp     loc_1401378E0
0x1401379a5  mov     rbx, [rbp+0C0h+arg_30]; jumptable 00000001401375E6 case 12
0x1401379ac  mov     esi, 1
0x1401379b1  movzx   eax, [rsp+1C0h+var_170]
0x1401379b6  ror     ax, 8
0x1401379ba  mov     [rdx+48h], ax
0x1401379be  movzx   eax, [rbp+0C0h+arg_20]
0x1401379c5  ror     ax, 8
0x1401379c9  mov     [rdx+58h], ax
0x1401379cd  mov     [rdx], esi
0x1401379cf  mov     [rdx+8], dil
0x1401379d3  mov     [rdx+40h], r15d
0x1401379d7  mov     [rdx+50h], r15d
0x1401379db  movzx   eax, byte ptr [rbx+18h]
0x1401379df  mov     [rdx+38h], al
0x1401379e2  mov     [rdx+30h], esi
0x1401379e5  mov     rax, [rbx+8]
0x1401379e9  add     rax, 10h
0x1401379ed  mov     dword ptr [rdx+60h], 4
0x1401379f4  mov     [rdx+68h], rax
0x1401379f8  mov     eax, [rbp+0C0h+arg_48]
0x1401379fe  mov     [rdx+78h], eax
0x140137a01  mov     eax, [rbp+0C0h+arg_50]
0x140137a07  mov     [rdx+88h], eax
0x140137a0d  mov     eax, [rbp+0C0h+arg_58]
0x140137a13  mov     [rdx+0A8h], eax
0x140137a19  mov     eax, [rbp+0C0h+arg_60]
0x140137a1f  mov     [rdx+0B8h], eax
0x140137a25  mov     eax, [rbp+0C0h+arg_40]
0x140137a2b  mov     [rdx+0C8h], eax
0x140137a31  mov     dword ptr [rdx+70h], 3
0x140137a38  mov     dword ptr [rdx+80h], 3
0x140137a42  mov     dword ptr [rdx+0A0h], 3
0x140137a4c  mov     dword ptr [rdx+0B0h], 3
0x140137a56  mov     dword ptr [rdx+0C0h], 3
0x140137a60  mov     rax, [rbx+10h]
0x140137a64  mov     rcx, [rax]
0x140137a67  mov     eax, [rcx]
0x140137a69  mov     rcx, [rbp+0C0h+var_130]
0x140137a6d  bswap   eax
0x140137a6f  mov     [rcx+18h], eax
0x140137a72  mov     rax, [rbp+0C0h+arg_38]
  ... truncated ...
```
