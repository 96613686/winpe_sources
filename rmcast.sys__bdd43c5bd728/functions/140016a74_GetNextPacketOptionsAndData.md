# GetNextPacketOptionsAndData

- ea: `0x140016a74`
- end: `0x1400172f7`
- name: `GetNextPacketOptionsAndData`
- size: `2179`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, KIRQL *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400185a4`

## callees

- `0x140005038`
- `0x140005068`
- `0x140005168`
- `0x140016a74`
- `0x140017300`
- `0x14001cdf0`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140016d63`
- `ntoskrnl!KeStackAttachProcess` at `0x140016d63`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140017125`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140017258`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140017125`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140017258`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016d1e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140016d1e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140016d37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140016d37`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001713c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001726f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001713c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001726f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017148`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001727b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017148`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001727b`
- `ntoskrnl!PsGetCurrentProcess` at `0x140016d43`
- `ntoskrnl!PsGetCurrentProcess` at `0x140016d43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016d12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016d12`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001715b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001728e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001715b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001728e`
- `TDI!TdiCopyMdlToBuffer` at `0x140016df2`
- `TDI!TdiCopyMdlToBuffer` at `0x140016df2`

## pseudocode

```c
__int64 __fastcall GetNextPacketOptionsAndData(__int64 a1, __int64 a2, _QWORD *a3, KIRQL *a4, __int64 a5)
{
  __int64 v5; // rsi
  KIRQL *v6; // r11
  _OWORD *v9; // r9
  void *v10; // r14
  ULONG v11; // ecx
  unsigned int v12; // r10d
  ULONG v13; // eax
  ULONG DestinationBufferSize; // r13d
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // ebx
  int v19; // r12d
  int v20; // edx
  __int16 v21; // cx
  __int16 v22; // r8
  char v23; // al
  unsigned __int16 v24; // dx
  _WORD *v25; // rcx
  int v26; // eax
  KIRQL v27; // dl
  int inited; // ebx
  __int64 v29; // rcx
  ULONG v30; // edx
  __int16 v31; // r14
  __int64 v32; // rbx
  unsigned int v33; // eax
  _OWORD *v34; // rdx
  __int64 v35; // rcx
  int v36; // r14d
  __int64 v37; // rcx
  _OWORD *v38; // rax
  __int128 v39; // xmm1
  __int64 v40; // rsi
  _OWORD *v41; // r13
  int v42; // ecx
  unsigned __int8 v43; // r12
  _OWORD *v44; // rbx
  unsigned int v45; // ecx
  unsigned int v46; // eax
  __int64 v47; // rbx
  unsigned int v48; // r9d
  __int64 v49; // r8
  __int64 v50; // r10
  unsigned int v51; // ecx
  __int64 v52; // rdx
  KIRQL v53; // al
  bool v54; // zf
  unsigned __int8 v55; // r8
  __int64 v56; // rax
  __int64 v57; // rdx
  unsigned __int64 v58; // rax
  KIRQL v60; // al
  int v61; // eax
  unsigned int v62; // eax
  unsigned __int8 v63; // [rsp+40h] [rbp-E8h]
  char v64; // [rsp+41h] [rbp-E7h]
  _WORD v65[2]; // [rsp+44h] [rbp-E4h] BYREF
  unsigned int v66; // [rsp+48h] [rbp-E0h]
  ULONG BytesCopied; // [rsp+4Ch] [rbp-DCh] BYREF
  __int64 v68; // [rsp+50h] [rbp-D8h]
  __int128 v69; // [rsp+58h] [rbp-D0h] BYREF
  __int128 v70; // [rsp+68h] [rbp-C0h]
  ULONG v71; // [rsp+78h] [rbp-B0h]
  ULONG v72; // [rsp+7Ch] [rbp-ACh]
  _OWORD *v73; // [rsp+80h] [rbp-A8h]
  _OWORD *v74; // [rsp+88h] [rbp-A0h]
  KIRQL *v75; // [rsp+90h] [rbp-98h]
  __int128 v76; // [rsp+98h] [rbp-90h]
  __int64 v77; // [rsp+A8h] [rbp-80h]
  _KAPC_STATE ApcState; // [rsp+B0h] [rbp-78h] BYREF

  v5 = *(_QWORD *)(a1 + 40);
  memset(&ApcState, 0, sizeof(ApcState));
  BytesCopied = 0;
  v6 = a4;
  v75 = a4;
  v9 = (_OWORD *)(*(_QWORD *)(a2 + 120) + *(_QWORD *)(v5 + 80));
  *(_QWORD *)&v76 = a5;
  v77 = v5;
  v63 = 0;
  v10 = v9 + 2;
  v74 = v9;
  *a3 = v9 + 2;
  v11 = *(_DWORD *)(v5 + 112);
  v12 = *(_DWORD *)(v5 + 152);
  LODWORD(v68) = *(_DWORD *)(v5 + 108);
  v13 = *(_DWORD *)(a2 + 104);
  v73 = v9 + 2;
  v66 = v12;
  v71 = v11;
  if ( v13 <= v11 )
  {
    DestinationBufferSize = *(unsigned __int16 *)(a2 + 104);
    v72 = DestinationBufferSize;
  }
  else
  {
    DestinationBufferSize = v11;
    v72 = v11;
  }
  v69 = 0;
  v70 = 0;
  if ( *(_BYTE *)(a2 + 152) && v13 == DestinationBufferSize )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
      v9 = v74;
      v12 = v66;
      v6 = v75;
    }
    v15 = *(_DWORD *)(a2 + 60);
    *(_BYTE *)(a2 + 152) = 0;
    if ( v15 )
    {
      v16 = *(_DWORD *)(a2 + 64);
    }
    else
    {
      *(_DWORD *)(a2 + 64) = 4;
      v16 = 4;
    }
    if ( (*(_DWORD *)(a1 + 32) & 0x4000) != 0 || !*(_QWORD *)(a1 + 96) )
      v17 = v15 | 0x80;
    else
      v17 = v15 | 0x40;
    *(_DWORD *)(a2 + 60) = v17;
    *(_DWORD *)(a2 + 64) = v16 + 4;
  }
  v18 = *(_DWORD *)(a2 + 60);
  v19 = *(_DWORD *)(a2 + 64);
  DWORD1(v69) = v18;
  if ( (v18 & 1) != 0 )
  {
    LODWORD(v70) = *(_DWORD *)(a2 + 96);
    DWORD1(v70) = *(_DWORD *)(a2 + 56) + *(_DWORD *)(a2 + 72);
    DWORD2(v70) = *(_DWORD *)(a2 + 68);
  }
  if ( (v18 & 8) != 0 )
  {
    v20 = *(_DWORD *)(v5 + 176);
    if ( (int)(v12 - *(_DWORD *)(v5 + 164) - v20) <= 0 )
      HIDWORD(v69) = *(_DWORD *)(v5 + 164);
    else
      HIDWORD(v69) = v12 - v20;
  }
  if ( *(_BYTE *)(a1 + 161) )
  {
    v21 = *(unsigned __int8 *)(a1 + 160);
    v22 = v12 & (unsigned __int8)(*(_BYTE *)(a1 + 160) - 1);
    v23 = HIBYTE(v70);
    v24 = v21 - v22;
    if ( v21 - v22 == v21 )
      v23 = v21;
    HIBYTE(v70) = v23;
    if ( *(_DWORD *)(v5 + 188) == 1 && v24 > 1u )
    {
      *(_DWORD *)(v5 + 180) = v12;
      if ( !v18 )
        v19 = 4;
      v18 |= 0x800u;
      BYTE13(v70) = v22 + 1;
      v19 += 8;
      DWORD1(v69) = v18;
      v25 = (_WORD *)(a1 + 158);
      v26 = *(unsigned __int16 *)(a1 + 158);
      v63 = v24 - 1;
    }
    else
    {
      v25 = (_WORD *)(a1 + 158);
      v26 = *(unsigned __int16 *)(a1 + 158);
      if ( !(_WORD)v26 || v24 != 1 )
      {
LABEL_34:
        if ( *v25 && *(unsigned __int8 *)(a1 + 160) == v24 )
          *(_QWORD *)(v5 + 272) = v9;
        goto LABEL_37;
      }
    }
    *(_DWORD *)(a2 + 140) = v26;
    goto LABEL_34;
  }
LABEL_37:
  v27 = *v6;
  v65[0] = *(_WORD *)(v5 + 112);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v27);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(a1 + 40) + 736LL), 1u);
  if ( (PRKPROCESS)PsGetCurrentProcess() == PgmStaticConfig )
  {
    v64 = 0;
  }
  else
  {
    KeStackAttachProcess(PgmStaticConfig, &ApcState);
    v64 = 1;
  }
  memset(v10, 0, 0x44u);
  inited = InitDataSpmHeader(a1, a2, (_DWORD)v10, (unsigned int)v65, v18, (__int64)&v69, 4);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        59,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)inited);
    goto LABEL_81;
  }
  v29 = *(_QWORD *)(a2 + 24);
  v30 = *(_DWORD *)(a2 + 56);
  BytesCopied = 0;
  v31 = v65[0];
  v32 = v65[0];
  v33 = TdiCopyMdlToBuffer(*(PMDL *)(v29 + 8), v30, (char *)v73 + v65[0], 0, DestinationBufferSize, &BytesCopied);
  if ( (int)(v33 + 0x80000000) >= 0 && v33 != -2147483643 || BytesCopied != DestinationBufferSize )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DDd(
        WPP_GLOBAL_Control->AttachedDevice,
        58,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        v33,
        BytesCopied,
        DestinationBufferSize);
    inited = -1073741823;
LABEL_81:
    if ( v64 )
      KeUnstackDetachProcess(&ApcState);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 40) + 736LL));
    KeLeaveCriticalRegion();
    v60 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
    *v75 = v60;
    v61 = *(_DWORD *)(a2 + 60);
    if ( (v61 & 0x40) != 0 && *(_DWORD *)(a2 + 104) == DestinationBufferSize )
    {
      v62 = v61 & 0xFFFFFFBF;
      *(_BYTE *)(a2 + 152) = 1;
      *(_DWORD *)(a2 + 60) = v62;
      if ( v62 )
        *(_DWORD *)(a2 + 64) -= 4;
      else
        *(_DWORD *)(a2 + 64) = 0;
    }
    *(_DWORD *)(a2 + 140) = 0;
    return (unsigned int)inited;
  }
  v34 = v73;
  v65[0] = __ROR2__(DestinationBufferSize, 8);
  *((_WORD *)v73 + 7) = v65[0];
  *((_DWORD *)v34 + 4) = _byteswap_ulong(v66);
  WORD1(v69) = v31 - 24;
  v35 = (unsigned __int16)(v31 + DestinationBufferSize);
  LOWORD(v69) = v35;
  *(_WORD *)v76 = v35;
  v68 = (unsigned int)v68;
  memset((char *)v34 + v35, 0, (unsigned int)v68 - v35 - 32);
  v36 = DWORD1(v69);
  if ( *(_BYTE *)(a1 + 161) )
  {
    v37 = (__int64)v73 + v71;
    LODWORD(v76) = v65[0];
    *(_QWORD *)((char *)&v76 + 4) = _byteswap_uint64(__PAIR64__(v70, DWORD1(v70)));
    HIDWORD(v76) = _byteswap_ulong(DWORD2(v70));
    *(_OWORD *)(v37 + v32) = v76;
    if ( (v36 & 1) == 0 )
      *(_BYTE *)(v37 + v32 + 2) = 0x80;
  }
  v38 = v74;
  v39 = v70;
  *v74 = v69;
  v38[1] = v39;
  if ( v63 )
  {
    ++v66;
    if ( (v36 & 1) != 0 )
    {
      v36 &= ~1u;
      DWORD1(v69) = v36;
      v19 -= 16;
    }
    if ( (v36 & 0x800) != 0 )
    {
      v36 &= ~0x800u;
      DWORD1(v69) = v36;
      v19 -= 8;
    }
    v40 = v68;
    v41 = v74;
    v42 = v36 != 0 ? v19 : 0;
    v43 = v63;
    WORD1(v69) = v42;
    while ( 1 )
    {
      v44 = v41;
      v41 = (_OWORD *)((char *)v41 + v40);
      *v41 = v69;
      v41[1] = v39;
      memset((char *)v44 + v40 + 32, 0, v40 - 32);
      v65[0] = v71;
      InitDataSpmHeader(a1, a2, (_DWORD)v44 + v40 + 32, (unsigned int)v65, v36, (__int64)&v69, 4);
      v45 = v66;
      v46 = v66;
      *((_WORD *)v41 + 23) = 0;
      *((_DWORD *)v41 + 12) = _byteswap_ulong(v46);
      LOWORD(v46) = v65[0];
      *(_WORD *)v41 = v65[0];
      v66 = v45 + 1;
      *((_WORD *)v41 + 1) = v46 - 24;
      if ( !--v43 )
        break;
      v39 = v70;
      v36 = DWORD1(v69);
    }
    v5 = v77;
    DestinationBufferSize = v72;
  }
  v47 = v68;
  if ( *(_DWORD *)(a2 + 140) )
  {
    v48 = 0;
    v49 = *(_QWORD *)(v5 + 272);
    v50 = v49;
    *(_DWORD *)(*(_QWORD *)(v5 + 424) + 4LL) = 0;
    *(_BYTE *)(*(_QWORD *)(v5 + 424) + 1LL) = 0;
    LOBYTE(v51) = *(_BYTE *)(a1 + 160);
    if ( (_BYTE)v51 )
    {
      do
      {
        *(_QWORD *)(*(_QWORD *)(v5 + 424) + 8LL * v48 + 8) = v49 + *(unsigned __int16 *)(v49 + 2) + 56LL;
        *(_DWORD *)(*(_QWORD *)(v5 + 424) + 4LL) |= *(_DWORD *)(v49 + 4) & 0x861;
        if ( (*(_DWORD *)(v49 + 4) & 0x800) != 0 )
          *(_BYTE *)(*(_QWORD *)(v5 + 424) + 1LL) = *(_BYTE *)(v49 + 29);
        v51 = *(unsigned __int8 *)(a1 + 160);
        v50 += v47;
        ++v48;
        v49 = v50;
      }
      while ( v48 < v51 );
    }
    v52 = *(_QWORD *)(v5 + 424);
    if ( (*(_DWORD *)(v52 + 4) & 0x800) == 0 )
      *(_BYTE *)(v52 + 1) = v51;
  }
  if ( v64 )
    KeUnstackDetachProcess(&ApcState);
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 40) + 736LL));
  KeLeaveCriticalRegion();
  v53 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  *v75 = v53;
  ++*(_DWORD *)(a2 + 108);
  *(_QWORD *)(a2 + 120) += v47;
  *(_DWORD *)(a2 + 56) += DestinationBufferSize;
  v54 = *(_DWORD *)(a2 + 104) == DestinationBufferSize;
  *(_DWORD *)(a2 + 104) -= DestinationBufferSize;
  *(_DWORD *)(a2 + 112) = DestinationBufferSize;
  if ( v54 )
    *(_DWORD *)(a2 + 92) = *(_DWORD *)(v5 + 152);
  v55 = v63;
  --*(_DWORD *)(v5 + 188);
  --*(_DWORD *)(v5 + 116);
  v56 = *(unsigned int *)(v5 + 108);
  *(_QWORD *)(v5 + 120) -= v56;
  *(_QWORD *)(v5 + 128) += v56;
  ++*(_DWORD *)(v5 + 156);
  ++*(_DWORD *)(v5 + 152);
  *(_DWORD *)(v5 + 184) = v63;
  if ( v63 )
  {
    do
    {
      v57 = *(unsigned int *)(v5 + 108);
      ++*(_DWORD *)(v5 + 152);
      --*(_DWORD *)(v5 + 116);
      *(_QWORD *)(v5 + 120) -= v57;
      *(_QWORD *)(v5 + 128) += v57;
      *(_QWORD *)(a2 + 120) += v57;
      --v55;
    }
    while ( v55 );
  }
  v58 = *(_QWORD *)(v5 + 88);
  if ( *(_QWORD *)(v5 + 128) >= v58 )
    *(_QWORD *)(v5 + 128) = 0;
  if ( *(_QWORD *)(a2 + 120) >= v58 )
    *(_QWORD *)(a2 + 120) = 0;
  return 0;
}

```

## disassembly

```asm
0x140016a74  push    rbx
0x140016a76  push    rsi
0x140016a77  push    rdi
0x140016a78  push    r12
0x140016a7a  push    r13
0x140016a7c  push    r14
0x140016a7e  push    r15
0x140016a80  sub     rsp, 0F0h
0x140016a87  mov     rax, cs:__security_cookie
0x140016a8e  xor     rax, rsp
0x140016a91  mov     [rsp+128h+var_48], rax
0x140016a99  mov     rsi, [rcx+28h]
0x140016a9d  xorps   xmm0, xmm0
0x140016aa0  mov     rax, [rsp+128h+arg_20]
0x140016aa8  xor     ebx, ebx
0x140016aaa  movups  xmmword ptr [rsp+128h+ApcState.ApcListHead.Flink], xmm0
0x140016ab2  mov     [rsp+128h+var_DC], ebx
0x140016ab6  mov     r11, r9
0x140016ab9  movups  xmmword ptr [rsp+128h+ApcState.ApcListHead.Flink+10h], xmm0
0x140016ac1  mov     [rsp+128h+var_98], r9
0x140016ac9  mov     r15, rcx
0x140016acc  movups  xmmword ptr [rsp+128h+ApcState.Process], xmm0
0x140016ad4  mov     r9, [rsi+50h]
0x140016ad8  mov     rdi, rdx
0x140016adb  add     r9, [rdx+78h]
0x140016adf  mov     qword ptr [rsp+128h+var_90], rax
0x140016ae7  mov     [rsp+128h+var_80], rsi
0x140016aef  mov     [rsp+128h+var_E8], bl
0x140016af3  lea     r14, [r9+20h]
0x140016af7  mov     [rsp+128h+var_A0], r9
0x140016aff  mov     [r8], r14
0x140016b02  mov     eax, [rsi+6Ch]
0x140016b05  mov     ecx, [rsi+70h]
0x140016b08  mov     r10d, [rsi+98h]
0x140016b0f  mov     dword ptr [rsp+128h+var_D8], eax
0x140016b13  mov     eax, [rdx+68h]
0x140016b16  mov     [rsp+128h+var_A8], r14
0x140016b1e  mov     [rsp+128h+var_E0], r10d
0x140016b23  mov     [rsp+128h+var_B0], ecx
0x140016b27  cmp     eax, ecx
0x140016b29  jbe     short loc_140016B34
0x140016b2b  mov     r13d, ecx
0x140016b2e  mov     [rsp+128h+var_AC], ecx
0x140016b32  jmp     short loc_140016B3E
0x140016b34  movzx   r13d, word ptr [rdx+68h]
0x140016b39  mov     [rsp+128h+var_AC], r13d
0x140016b3e  lea     rdx, WPP_GLOBAL_Control
0x140016b45  mov     r8d, 4
0x140016b4b  movups  [rsp+128h+var_D0], xmm0
0x140016b50  movups  [rsp+128h+var_C0], xmm0
0x140016b55  cmp     [rdi+98h], bl
0x140016b5b  jz      loc_140016BE3
0x140016b61  cmp     eax, r13d
0x140016b64  jnz     short loc_140016BE3
0x140016b66  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b6d  cmp     rcx, rdx
0x140016b70  jz      short loc_140016BA8
0x140016b72  mov     eax, [rcx+2Ch]
0x140016b75  test    al, 20h
0x140016b77  jz      short loc_140016BA8
0x140016b79  mov     rcx, [rcx+18h]
0x140016b7d  lea     edx, [r8+35h]
0x140016b81  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140016b88  call    WPP_SF_
0x140016b8d  mov     r9, [rsp+128h+var_A0]
0x140016b95  mov     r8d, 4
0x140016b9b  mov     r10d, [rsp+128h+var_E0]
0x140016ba0  mov     r11, [rsp+128h+var_98]
0x140016ba8  mov     ecx, [rdi+3Ch]
0x140016bab  mov     [rdi+98h], bl
0x140016bb1  test    ecx, ecx
0x140016bb3  jnz     short loc_140016BBE
0x140016bb5  mov     [rdi+40h], r8d
0x140016bb9  mov     edx, r8d
0x140016bbc  jmp     short loc_140016BC1
0x140016bbe  mov     edx, [rdi+40h]
0x140016bc1  test    dword ptr [r15+20h], 4000h
0x140016bc9  jnz     short loc_140016BD6
0x140016bcb  cmp     [r15+60h], rbx
0x140016bcf  jz      short loc_140016BD6
0x140016bd1  or      ecx, 40h
0x140016bd4  jmp     short loc_140016BDA
0x140016bd6  bts     ecx, 7
0x140016bda  lea     eax, [rdx+4]
0x140016bdd  mov     [rdi+3Ch], ecx
0x140016be0  mov     [rdi+40h], eax
0x140016be3  mov     ebx, [rdi+3Ch]
0x140016be6  mov     edx, 1
0x140016beb  mov     r12d, [rdi+40h]
0x140016bef  mov     dword ptr [rsp+128h+var_D0+4], ebx
0x140016bf3  test    dl, bl
0x140016bf5  jz      short loc_140016C0F
0x140016bf7  mov     eax, [rdi+60h]
0x140016bfa  mov     dword ptr [rsp+128h+var_C0], eax
0x140016bfe  mov     eax, [rdi+48h]
0x140016c01  add     eax, [rdi+38h]
0x140016c04  mov     dword ptr [rsp+128h+var_C0+4], eax
0x140016c08  mov     eax, [rdi+44h]
0x140016c0b  mov     dword ptr [rsp+128h+var_C0+8], eax
0x140016c0f  test    bl, 8
0x140016c12  jz      short loc_140016C3F
0x140016c14  mov     ecx, [rsi+0A4h]
0x140016c1a  mov     eax, r10d
0x140016c1d  mov     edx, [rsi+0B0h]
0x140016c23  sub     eax, ecx
0x140016c25  sub     eax, edx
0x140016c27  test    eax, eax
0x140016c29  jle     short loc_140016C36
0x140016c2b  mov     eax, r10d
0x140016c2e  sub     eax, edx
0x140016c30  mov     dword ptr [rsp+128h+var_D0+0Ch], eax
0x140016c34  jmp     short loc_140016C3A
0x140016c36  mov     dword ptr [rsp+128h+var_D0+0Ch], ecx
0x140016c3a  mov     edx, 1
0x140016c3f  cmp     byte ptr [r15+0A1h], 0
0x140016c47  jz      loc_140016CFF
0x140016c4d  movzx   ecx, byte ptr [r15+0A0h]
0x140016c55  mov     al, cl
0x140016c57  sub     al, dl
0x140016c59  movzx   edx, cx
0x140016c5c  and     al, r10b
0x140016c5f  movzx   r8d, al
0x140016c63  movzx   eax, byte ptr [rsp+128h+var_C0+0Fh]
0x140016c68  sub     dx, r8w
0x140016c6c  cmp     dx, cx
0x140016c6f  cmovz   eax, ecx
0x140016c72  mov     byte ptr [rsp+128h+var_C0+0Fh], al
0x140016c76  mov     eax, 1
0x140016c7b  cmp     [rsi+0BCh], eax
0x140016c81  jnz     short loc_140016CC3
0x140016c83  cmp     dx, ax
0x140016c86  jbe     short loc_140016CC3
0x140016c88  test    ebx, ebx
0x140016c8a  mov     [rsi+0B4h], r10d
0x140016c91  lea     ecx, [rax+3]
0x140016c94  mov     r10b, dl
0x140016c97  cmovz   r12d, ecx
0x140016c9b  add     r8b, al
0x140016c9e  bts     ebx, 0Bh
0x140016ca2  mov     byte ptr [rsp+128h+var_C0+0Dh], r8b
0x140016ca7  add     r12d, 8
0x140016cab  mov     dword ptr [rsp+128h+var_D0+4], ebx
0x140016caf  sub     r10b, al
0x140016cb2  lea     rcx, [r15+9Eh]
0x140016cb9  movzx   eax, word ptr [rcx]
0x140016cbc  mov     [rsp+128h+var_E8], r10b
0x140016cc1  jmp     short loc_140016CDE
0x140016cc3  lea     rcx, [r15+9Eh]
0x140016cca  movzx   eax, word ptr [rcx]
0x140016ccd  test    ax, ax
0x140016cd0  jz      short loc_140016CE4
0x140016cd2  mov     r8d, 1
0x140016cd8  cmp     r8w, dx
0x140016cdc  jnz     short loc_140016CE4
0x140016cde  mov     [rdi+8Ch], eax
0x140016ce4  xor     eax, eax
0x140016ce6  cmp     [rcx], ax
0x140016ce9  jz      short loc_140016CFF
0x140016ceb  movzx   eax, byte ptr [r15+0A0h]
0x140016cf3  cmp     ax, dx
0x140016cf6  jnz     short loc_140016CFF
0x140016cf8  mov     [rsi+110h], r9
0x140016cff  movzx   eax, word ptr [rsi+70h]
0x140016d03  lea     rcx, [r15+168h]; SpinLock
0x140016d0a  mov     dl, [r11]; NewIrql
0x140016d0d  mov     [rsp+128h+var_E4], ax
0x140016d12  call    cs:__imp_KeReleaseSpinLock
0x140016d19  nop     dword ptr [rax+rax+00h]
0x140016d1e  call    cs:__imp_KeEnterCriticalRegion
0x140016d25  nop     dword ptr [rax+rax+00h]
0x140016d2a  mov     rcx, [r15+28h]
0x140016d2e  mov     dl, 1; Wait
0x140016d30  add     rcx, 2E0h; Resource
0x140016d37  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140016d3e  nop     dword ptr [rax+rax+00h]
0x140016d43  call    cs:__imp_PsGetCurrentProcess
0x140016d4a  nop     dword ptr [rax+rax+00h]
0x140016d4f  mov     rcx, cs:PgmStaticConfig; PROCESS
0x140016d56  cmp     rax, rcx
0x140016d59  jz      short loc_140016D76
0x140016d5b  lea     rdx, [rsp+128h+ApcState]; ApcState
0x140016d63  call    cs:__imp_KeStackAttachProcess
0x140016d6a  nop     dword ptr [rax+rax+00h]
0x140016d6f  mov     [rsp+128h+var_E7], 1
0x140016d74  jmp     short loc_140016D7B
0x140016d76  mov     [rsp+128h+var_E7], 0
0x140016d7b  xor     edx, edx; Val
0x140016d7d  mov     rcx, r14; void *
0x140016d80  lea     r8d, [rdx+44h]; Size
0x140016d84  call    memset
0x140016d89  lea     rax, [rsp+128h+var_D0]
0x140016d8e  mov     [rsp+128h+var_F8], 4
0x140016d93  mov     [rsp+128h+BytesCopied], rax
0x140016d98  lea     r9, [rsp+128h+var_E4]
0x140016d9d  mov     r8, r14
0x140016da0  mov     [rsp+128h+DestinationBufferSize], ebx
0x140016da4  mov     rdx, rdi
0x140016da7  mov     rcx, r15
0x140016daa  call    InitDataSpmHeader
0x140016daf  xor     r14d, r14d
0x140016db2  mov     ebx, eax
0x140016db4  test    eax, eax
0x140016db6  js      loc_140017217
0x140016dbc  mov     rcx, [rdi+18h]
0x140016dc0  lea     rax, [rsp+128h+var_DC]
0x140016dc5  mov     r8, [rsp+128h+var_A8]
0x140016dcd  xor     r9d, r9d; DestinationOffset
0x140016dd0  mov     edx, [rdi+38h]; SourceOffset
0x140016dd3  mov     [rsp+128h+var_DC], r14d
0x140016dd8  movzx   r14d, [rsp+128h+var_E4]
0x140016dde  mov     rcx, [rcx+8]; SourceMdlChain
0x140016de2  add     r8, r14; DestinationBuffer
0x140016de5  mov     [rsp+128h+BytesCopied], rax; BytesCopied
0x140016dea  mov     ebx, r14d
0x140016ded  mov     [rsp+128h+DestinationBufferSize], r13d; DestinationBufferSize
0x140016df2  call    cs:__imp_TdiCopyMdlToBuffer
0x140016df9  nop     dword ptr [rax+rax+00h]
0x140016dfe  mov     r10d, [rsp+128h+var_DC]
0x140016e03  mov     r9d, eax
0x140016e06  mov     eax, 80000000h
0x140016e0b  lea     ecx, [r9+rax]
0x140016e0f  test    eax, ecx
0x140016e11  jnz     short loc_140016E1C
0x140016e13  cmp     r9d, 80000005h
0x140016e1a  jnz     short loc_140016E21
0x140016e1c  cmp     r10d, r13d
0x140016e1f  jz      short loc_140016E67
0x140016e21  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e28  lea     rax, WPP_GLOBAL_Control
0x140016e2f  cmp     rcx, rax
0x140016e32  jz      short loc_140016E5A
0x140016e34  mov     eax, [rcx+2Ch]
0x140016e37  test    al, 2
0x140016e39  jz      short loc_140016E5A
0x140016e3b  mov     rcx, [rcx+18h]
0x140016e3f  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140016e46  mov     edx, 3Ah ; ':'
0x140016e4b  mov     dword ptr [rsp+128h+BytesCopied], r13d
0x140016e50  mov     [rsp+128h+DestinationBufferSize], r10d
0x140016e55  call    WPP_SF_DDd
0x140016e5a  mov     ebx, 0C0000001h
0x140016e5f  xor     r14d, r14d
0x140016e62  jmp     loc_140017249
0x140016e67  mov     rdx, [rsp+128h+var_A8]
0x140016e6f  movzx   eax, r13w
0x140016e73  ror     ax, 8
0x140016e77  mov     [rsp+128h+var_E4], ax
0x140016e7c  mov     [rdx+0Eh], ax
0x140016e80  mov     eax, [rsp+128h+var_E0]
0x140016e84  bswap   eax
0x140016e86  mov     [rdx+10h], eax
0x140016e89  lea     eax, [r14-18h]
0x140016e8d  mov     word ptr [rsp+128h+var_D0+2], ax
0x140016e92  lea     eax, [r14+r13]
0x140016e96  movzx   ecx, ax
0x140016e99  mov     rax, qword ptr [rsp+128h+var_90]
0x140016ea1  mov     word ptr [rsp+128h+var_D0], cx
0x140016ea6  mov     [rax], cx
0x140016ea9  mov     eax, dword ptr [rsp+128h+var_D8]
0x140016ead  mov     r8d, eax
0x140016eb0  mov     [rsp+128h+var_D8], rax
0x140016eb5  sub     r8, rcx
0x140016eb8  add     rcx, rdx; void *
0x140016ebb  sub     r8, 20h ; ' '; Size
0x140016ebf  xor     edx, edx; Val
0x140016ec1  call    memset
0x140016ec6  mov     r14d, dword ptr [rsp+128h+var_D0+4]
0x140016ecb  xor     r8d, r8d
0x140016ece  lea     r11d, [r8+1]
0x140016ed2  cmp     [r15+0A1h], r8b
0x140016ed9  jz      short loc_140016F3B
0x140016edb  movzx   eax, [rsp+128h+var_E4]
0x140016ee0  mov     ecx, [rsp+128h+var_B0]
0x140016ee4  add     rcx, [rsp+128h+var_A8]
0x140016eec  mov     word ptr [rsp+128h+var_90], ax
0x140016ef4  mov     eax, dword ptr [rsp+128h+var_C0]
0x140016ef8  mov     word ptr [rsp+128h+var_90+2], r8w
0x140016f01  bswap   eax
0x140016f03  mov     dword ptr [rsp+128h+var_90+4], eax
0x140016f0a  mov     eax, dword ptr [rsp+128h+var_C0+4]
0x140016f0e  bswap   eax
0x140016f10  mov     dword ptr [rsp+128h+var_90+8], eax
0x140016f17  mov     eax, dword ptr [rsp+128h+var_C0+8]
0x140016f1b  bswap   eax
0x140016f1d  mov     dword ptr [rsp+128h+var_90+0Ch], eax
0x140016f24  movups  xmm0, [rsp+128h+var_90]
0x140016f2c  movdqu  xmmword ptr [rcx+rbx], xmm0
0x140016f31  test    r11b, r14b
0x140016f34  jnz     short loc_140016F3B
0x140016f36  mov     byte ptr [rcx+rbx+2], 80h
0x140016f3b  mov     rax, [rsp+128h+var_A0]
0x140016f43  movups  xmm0, [rsp+128h+var_D0]
0x140016f48  mov     dl, [rsp+128h+var_E8]
0x140016f4c  movups  xmm1, [rsp+128h+var_C0]
0x140016f51  movups  xmmword ptr [rax], xmm0
0x140016f54  movups  xmmword ptr [rax+10h], xmm1
0x140016f58  test    dl, dl
0x140016f5a  jz      loc_140017064
0x140016f60  mov     eax, [rsp+128h+var_E0]
0x140016f64  inc     eax
  ... truncated ...
```
