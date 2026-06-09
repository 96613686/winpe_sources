# NvmeAdapterFabricsAddControllerIoctl

- ea: `0x1401a152c`
- end: `0x1401a1ad3`
- name: `NvmeAdapterFabricsAddControllerIoctl`
- size: `1447`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400e7d6c`
- `0x1400f72a0`
- `0x1400f8d6c`
- `0x14014b400`
- `0x14014b800`
- `0x1401a152c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1713`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a1713`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a172c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a172c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a164e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a164e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a176b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a176b`
- `ntoskrnl!IofCompleteRequest` at `0x1401a1a9c`
- `ntoskrnl!IofCompleteRequest` at `0x1401a1a9c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a16c2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a1787`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a1808`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a16c2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a1787`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a1808`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a1777`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a1777`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsAddControllerIoctl(__int64 a1, __int64 a2)
{
  char v2; // r13
  char v5; // si
  __int64 v6; // rbp
  __int64 v7; // r12
  unsigned __int16 v8; // cx
  int AddNvmeController; // ebx
  __int64 SubsystemPort; // rax
  int v11; // r8d
  __int64 v12; // r14
  bool v13; // zf
  unsigned __int64 v14; // rcx
  __int64 v15; // rdx
  int *v16; // rax
  int v17; // ecx
  unsigned __int16 v18; // cx
  __int64 v19; // rbp
  _QWORD *v20; // rdx
  _DWORD *v21; // r14
  __int64 *v22; // rdx
  __int64 v23; // rdx
  unsigned int v24; // r12d
  unsigned __int8 v25; // r10
  char *v26; // r11
  char v27; // r14
  _BYTE *v28; // r9
  unsigned int v29; // r15d
  unsigned __int64 v30; // rbp
  __int64 v31; // r8
  int v32; // ecx
  char v33; // cl
  char v34; // bp
  char v35; // r11
  _BYTE *v36; // rax
  char v37; // r8
  char *v38; // r8
  unsigned int v39; // eax
  __int128 v41; // [rsp+60h] [rbp-58h] BYREF

  v2 = 0;
  *(_QWORD *)(a2 + 56) = 0;
  *(_QWORD *)&v41 = 0;
  v5 = 1;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v6 = *(_QWORD *)(a2 + 24);
    if ( v6
      && (v7 = *(_QWORD *)(a2 + 184), *(_DWORD *)(v7 + 16) >= 0x38u)
      && *(_WORD *)v6 == 1
      && *(_WORD *)(v6 + 2) >= 0x38u
      && *(_WORD *)(v6 + 16) <= 0xFFEFu
      && (v8 = *(_WORD *)(v6 + 18), (unsigned __int16)(v8 - 1) > 0x1Eu)
      && v8 < 0x1001u )
    {
      if ( *(_DWORD *)(v7 + 8) < 0x20u )
      {
        AddNvmeController = -1073741789;
        goto LABEL_14;
      }
      SubsystemPort = NvmeAdapterFindSubsystemPort(a1, *(_QWORD *)(v6 + 8) ^ a1, 0, 0);
      v12 = SubsystemPort;
      if ( !SubsystemPort )
      {
        AddNvmeController = -1073741275;
        goto LABEL_14;
      }
      if ( (*(_BYTE *)(SubsystemPort + 32) & 4) != 0 )
      {
        AddNvmeController = -1073741637;
LABEL_25:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v12 + 40));
        goto LABEL_14;
      }
      LOBYTE(v11) = 1;
      AddNvmeController = NvmeAdapterCreateAddNvmeController(
                            SubsystemPort,
                            *(unsigned __int16 *)(v6 + 16),
                            v11,
                            (int)v6 + 20,
                            (__int64)&v41);
      if ( AddNvmeController < 0 )
        goto LABEL_25;
      v18 = *(_WORD *)(v6 + 18);
      v19 = v41;
      if ( v18 )
      {
        if ( v18 >= *(_WORD *)(v41 + 6) )
          v18 = *(_WORD *)(v41 + 6);
        *(_WORD *)(v41 + 6) = v18;
      }
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v12 + 632), 1u);
      v20 = *(_QWORD **)(v12 + 616);
      if ( *v20 != v12 + 608 )
        __fastfail(3u);
      *(_QWORD *)(v19 + 64) = v12 + 608;
      *(_QWORD *)(v19 + 72) = v20;
      *v20 = v19 + 64;
      *(_QWORD *)(v12 + 616) = v19 + 64;
      ++*(_DWORD *)(v12 + 624);
      ExReleaseResourceLite((PERESOURCE)(v12 + 632));
      KeLeaveCriticalRegion();
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v12 + 40));
      v21 = *(_DWORD **)(a2 + 24);
      memset_0(v21, 0, *(unsigned int *)(v7 + 8));
      AddNvmeController = NvmeControllerAcquireRundown(v19);
      if ( AddNvmeController >= 0 )
      {
        *v21 = 2097153;
        if ( (*(_BYTE *)(v19 + 136) & 4) != 0 )
          v21[1] |= 8u;
        *((_QWORD *)v21 + 1) = v19 ^ a1;
        *((_WORD *)v21 + 8) = *(_WORD *)(v19 + 4);
        v21[5] = *(_DWORD *)(v19 + 572);
        if ( *(_DWORD *)(v19 + 572) == 1 )
        {
          *((_WORD *)v21 + 12) = *(_WORD *)(v19 + 20);
          *((_WORD *)v21 + 13) = *(_WORD *)(v19 + 8);
        }
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v19 + 552));
        *(_QWORD *)(a2 + 56) = *((unsigned __int16 *)v21 + 1);
      }
    }
    else
    {
      AddNvmeController = -1073741811;
    }
  }
  else
  {
    AddNvmeController = -1073741637;
  }
LABEL_14:
  v13 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = AddNvmeController;
  if ( v13 )
    goto LABEL_95;
  v41 = 0;
  IoGetActivityIdIrp(a2, &v41);
  v15 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v15 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_95;
    v22 = EventNonReadWriteRequestComplete;
    goto LABEL_94;
  }
  if ( *(_BYTE *)v15 != 15 )
  {
    if ( *(_BYTE *)v15 != 27 )
      goto LABEL_95;
    if ( *(_BYTE *)(v15 + 1) == 7 && !*(_DWORD *)(v15 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v16 = *(int **)(a2 + 56);
        if ( v16 )
          v17 = *v16;
        else
          v17 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v17, v15, (unsigned int)&v41, a2, v17, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_95;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_95;
    v22 = EventPnpRequestComplete;
LABEL_94:
    McTemplateK0pd_EtwWriteTransfer(v14, v22, &v41, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_95;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_95;
  v23 = *(_QWORD *)(v15 + 8);
  if ( *(_BYTE *)(v23 + 2) != 40 )
  {
    v33 = *(_BYTE *)(v23 + 72);
    v28 = *(_BYTE **)(v23 + 32);
    v25 = *(_BYTE *)(v23 + 11);
    v27 = *(_BYTE *)(v23 + 4);
    if ( *(_BYTE *)(v23 + 2) )
      goto LABEL_95;
LABEL_73:
    LOBYTE(v14) = v33 - 8;
    if ( (v14 & 0x5D) != 0 )
      goto LABEL_95;
    v34 = *(_BYTE *)(v23 + 3);
    if ( v34 == 1 || !v28 || !v25 )
      goto LABEL_90;
    LOBYTE(v23) = 0;
    v14 = (unsigned __int64)&v28[v25];
    v35 = 0;
    v36 = v28 + 8;
    v37 = 0;
    if ( (unsigned __int8)((*v28 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v36 <= v14 )
      {
        v35 = v28[2];
        LOBYTE(v23) = v28[1] & 0xF;
        v37 = v28[3];
        goto LABEL_89;
      }
    }
    else if ( (unsigned __int64)v36 <= v14 )
    {
      v38 = v28 + 13;
      LOBYTE(v23) = v28[2] & 0xF;
      v39 = v25;
      if ( (unsigned int)(unsigned __int8)v28[7] + 8 <= v25 )
        v39 = (unsigned __int8)v28[7] + 8;
      v14 = (unsigned __int64)&v28[v39];
      if ( (unsigned __int64)v38 <= v14 )
        v35 = v28[12];
      if ( (unsigned __int64)(v28 + 14) > v14 )
        v37 = 0;
      else
        v37 = *v38;
LABEL_89:
      if ( v5 )
      {
LABEL_91:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v14,
          v23,
          (unsigned int)&v41,
          a2,
          *(_DWORD *)(a2 + 48),
          v34,
          v27,
          v23,
          v35,
          v37,
          a2);
        goto LABEL_95;
      }
LABEL_90:
      LOBYTE(v23) = 0;
      v35 = 0;
      v37 = 0;
      goto LABEL_91;
    }
    v5 = 0;
    goto LABEL_89;
  }
  if ( *(_DWORD *)(v23 + 20) )
    goto LABEL_95;
  v24 = *(_DWORD *)(v23 + 56);
  if ( !v24 )
    goto LABEL_95;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  while ( 1 )
  {
    v14 = *(unsigned int *)(v23 + 4LL * v29 + 120);
    if ( (unsigned int)v14 >= 0x80 )
    {
      v30 = *(unsigned int *)(v23 + 16);
      if ( (unsigned int)v14 < (unsigned int)v30 )
        break;
    }
LABEL_66:
    if ( ++v29 >= v24 )
      goto LABEL_67;
  }
  v31 = (unsigned int)v14;
  v32 = *(_DWORD *)(v14 + v23) - 64;
  if ( v32 )
  {
    LODWORD(v14) = v32 - 1;
    if ( (_DWORD)v14 )
    {
      if ( (_DWORD)v14 == 1 )
      {
        LODWORD(v14) = v31 + 40;
        if ( v31 + 40 <= v30 )
        {
          if ( *(_DWORD *)(v31 + v23 + 12) )
            v26 = (char *)(v31 + v23 + 32);
          v28 = *(_BYTE **)(v31 + v23 + 24);
          goto LABEL_59;
        }
      }
    }
    else
    {
      LODWORD(v14) = v31 + 56;
      if ( v31 + 56 <= v30 )
      {
        v2 = 1;
        if ( *(_BYTE *)(v31 + v23 + 10) )
          v26 = (char *)(v31 + v23 + 24);
        v27 = *(_BYTE *)(v31 + v23 + 8);
        v28 = *(_BYTE **)(v31 + v23 + 16);
        v25 = *(_BYTE *)(v31 + v23 + 9);
      }
    }
    goto LABEL_65;
  }
  LODWORD(v14) = v31 + 40;
  if ( v31 + 40 > v30 )
  {
LABEL_65:
    if ( v2 )
      goto LABEL_67;
    goto LABEL_66;
  }
  if ( *(_BYTE *)(v31 + v23 + 10) )
    v26 = (char *)(v31 + v23 + 24);
  v28 = *(_BYTE **)(v31 + v23 + 16);
LABEL_59:
  v27 = *(_BYTE *)(v31 + v23 + 8);
  v25 = *(_BYTE *)(v31 + v23 + 9);
LABEL_67:
  if ( v26 )
  {
    v33 = *v26;
    goto LABEL_73;
  }
LABEL_95:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)AddNvmeController;
}

```

## disassembly

```asm
0x1401a152c  mov     [rsp+arg_10], rbx
0x1401a1531  push    rbp
0x1401a1532  push    rsi
0x1401a1533  push    rdi
0x1401a1534  push    r12
0x1401a1536  push    r13
0x1401a1538  push    r14
0x1401a153a  push    r15
0x1401a153c  sub     rsp, 80h
0x1401a1543  mov     rax, cs:__security_cookie
0x1401a154a  xor     rax, rsp
0x1401a154d  mov     [rsp+0B8h+var_48], rax
0x1401a1552  xor     r13d, r13d
0x1401a1555  mov     rdi, rdx
0x1401a1558  mov     [rdx+38h], r13
0x1401a155c  mov     r15, rcx
0x1401a155f  mov     qword ptr [rsp+0B8h+var_58], r13
0x1401a1564  lea     esi, [r13+1]
0x1401a1568  lea     r14d, [r13+20h]
0x1401a156c  test    [rcx+98h], sil
0x1401a1573  jz      loc_1401A182C
0x1401a1579  cmp     [rcx+268h], r13
0x1401a1580  jz      loc_1401A182C
0x1401a1586  mov     rbp, [rdx+18h]
0x1401a158a  test    rbp, rbp
0x1401a158d  jz      loc_1401A1822
0x1401a1593  mov     r12, [rdx+0B8h]
0x1401a159a  lea     eax, [rsi+37h]
0x1401a159d  cmp     [r12+10h], eax
0x1401a15a2  jb      loc_1401A1822
0x1401a15a8  cmp     [rbp+0], si
0x1401a15ac  jnz     loc_1401A1822
0x1401a15b2  cmp     [rbp+2], ax
0x1401a15b6  jb      loc_1401A1822
0x1401a15bc  mov     eax, 0FFEFh
0x1401a15c1  cmp     [rbp+10h], ax
0x1401a15c5  ja      loc_1401A1822
0x1401a15cb  movzx   ecx, word ptr [rbp+12h]
0x1401a15cf  movzx   eax, cx
0x1401a15d2  sub     ax, si
0x1401a15d5  cmp     ax, 1Eh
0x1401a15d9  jbe     loc_1401A1822
0x1401a15df  mov     eax, 1001h
0x1401a15e4  cmp     cx, ax
0x1401a15e7  jnb     loc_1401A1822
0x1401a15ed  cmp     [r12+8], r14d
0x1401a15f2  jnb     short loc_1401A15FB
0x1401a15f4  mov     ebx, 0C0000023h
0x1401a15f9  jmp     short loc_1401A1627
0x1401a15fb  mov     rdx, r15
0x1401a15fe  xor     r9d, r9d
0x1401a1601  xor     rdx, [rbp+8]
0x1401a1605  xor     r8d, r8d
0x1401a1608  mov     rcx, r15
0x1401a160b  call    NvmeAdapterFindSubsystemPort
0x1401a1610  mov     r14, rax
0x1401a1613  test    rax, rax
0x1401a1616  jnz     loc_1401A16B3
0x1401a161c  mov     ebx, 0C0000225h
0x1401a1621  mov     r14d, 20h ; ' '
0x1401a1627  cmp     cs:StorEtwLoggingEnabled, r13b
0x1401a162e  mov     byte ptr [rdi+8Dh], 0ACh
0x1401a1635  mov     [rdi+30h], ebx
0x1401a1638  jz      loc_1401A1A97
0x1401a163e  xorps   xmm0, xmm0
0x1401a1641  lea     rdx, [rsp+0B8h+var_58]
0x1401a1646  mov     rcx, rdi
0x1401a1649  movups  [rsp+0B8h+var_58], xmm0
0x1401a164e  call    cs:__imp_IoGetActivityIdIrp
0x1401a1655  nop     dword ptr [rax+rax+00h]
0x1401a165a  mov     rdx, [rdi+0B8h]
0x1401a1661  movzx   eax, byte ptr [rdx]
0x1401a1664  sub     eax, 0Eh
0x1401a1667  jz      loc_1401A1A73
0x1401a166d  sub     eax, esi
0x1401a166f  jz      loc_1401A186F
0x1401a1675  cmp     eax, 0Ch
0x1401a1678  jnz     loc_1401A1A97
0x1401a167e  cmp     byte ptr [rdx+1], 7
0x1401a1682  jnz     loc_1401A1856
0x1401a1688  cmp     [rdx+8], r13d
0x1401a168c  jnz     loc_1401A1856
0x1401a1692  test    cs:byte_140177432, 40h
0x1401a1699  jz      loc_1401A1A97
0x1401a169f  mov     rax, [rdi+38h]
0x1401a16a3  test    rax, rax
0x1401a16a6  jz      loc_1401A1836
0x1401a16ac  mov     ecx, [rax]
0x1401a16ae  jmp     loc_1401A1839
0x1401a16b3  test    byte ptr [rax+20h], 4
0x1401a16b7  jz      short loc_1401A16D3
0x1401a16b9  mov     ebx, 0C00000BBh
0x1401a16be  mov     rcx, [r14+28h]; RunRefCacheAware
0x1401a16c2  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a16c9  nop     dword ptr [rax+rax+00h]
0x1401a16ce  jmp     loc_1401A1621
0x1401a16d3  movzx   edx, word ptr [rbp+10h]
0x1401a16d7  lea     rax, [rsp+0B8h+var_58]
0x1401a16dc  lea     r9, [rbp+14h]
0x1401a16e0  mov     [rsp+0B8h+var_98], rax
0x1401a16e5  mov     r8b, sil
0x1401a16e8  mov     rcx, r14
0x1401a16eb  call    NvmeAdapterCreateAddNvmeController
0x1401a16f0  mov     ebx, eax
0x1401a16f2  test    eax, eax
0x1401a16f4  js      short loc_1401A16BE
0x1401a16f6  movzx   ecx, word ptr [rbp+12h]
0x1401a16fa  mov     rbp, qword ptr [rsp+0B8h+var_58]
0x1401a16ff  test    cx, cx
0x1401a1702  jz      short loc_1401A1713
0x1401a1704  movzx   eax, word ptr [rbp+6]
0x1401a1708  cmp     cx, ax
0x1401a170b  cmovnb  cx, ax
0x1401a170f  mov     [rbp+6], cx
0x1401a1713  call    cs:__imp_KeEnterCriticalRegion
0x1401a171a  nop     dword ptr [rax+rax+00h]
0x1401a171f  lea     rbx, [r14+278h]
0x1401a1726  mov     dl, sil; Wait
0x1401a1729  mov     rcx, rbx; Resource
0x1401a172c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a1733  nop     dword ptr [rax+rax+00h]
0x1401a1738  lea     rcx, [r14+260h]
0x1401a173f  mov     rdx, [rcx+8]
0x1401a1743  cmp     [rdx], rcx
0x1401a1746  jz      short loc_1401A174F
0x1401a1748  mov     ecx, 3
0x1401a174d  int     29h; Win8: RtlFailFast(ecx)
0x1401a174f  lea     rax, [rbp+40h]
0x1401a1753  mov     [rax], rcx
0x1401a1756  mov     [rax+8], rdx
0x1401a175a  mov     [rdx], rax
0x1401a175d  mov     [rcx+8], rax
0x1401a1761  mov     rcx, rbx; Resource
0x1401a1764  add     [r14+270h], esi
0x1401a176b  call    cs:__imp_ExReleaseResourceLite
0x1401a1772  nop     dword ptr [rax+rax+00h]
0x1401a1777  call    cs:__imp_KeLeaveCriticalRegion
0x1401a177e  nop     dword ptr [rax+rax+00h]
0x1401a1783  mov     rcx, [r14+28h]; RunRefCacheAware
0x1401a1787  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a178e  nop     dword ptr [rax+rax+00h]
0x1401a1793  mov     r14, [rdi+18h]
0x1401a1797  xor     edx, edx; Val
0x1401a1799  mov     r8d, [r12+8]; Size
0x1401a179e  mov     rcx, r14; void *
0x1401a17a1  call    memset_0
0x1401a17a6  mov     rcx, rbp
0x1401a17a9  call    NvmeControllerAcquireRundown
0x1401a17ae  mov     ebx, eax
0x1401a17b0  test    eax, eax
0x1401a17b2  js      loc_1401A1621
0x1401a17b8  mov     dword ptr [r14], 200001h
0x1401a17bf  test    byte ptr [rbp+88h], 4
0x1401a17c6  jz      short loc_1401A17CD
0x1401a17c8  or      dword ptr [r14+4], 8
0x1401a17cd  xor     r15, rbp
0x1401a17d0  mov     [r14+8], r15
0x1401a17d4  movzx   eax, word ptr [rbp+4]
0x1401a17d8  mov     [r14+10h], ax
0x1401a17dd  mov     eax, [rbp+23Ch]
0x1401a17e3  mov     [r14+14h], eax
0x1401a17e7  cmp     [rbp+23Ch], esi
0x1401a17ed  jnz     short loc_1401A1801
0x1401a17ef  movzx   eax, word ptr [rbp+14h]
0x1401a17f3  mov     [r14+18h], ax
0x1401a17f8  movzx   eax, word ptr [rbp+8]
0x1401a17fc  mov     [r14+1Ah], ax
0x1401a1801  mov     rcx, [rbp+228h]; RunRefCacheAware
0x1401a1808  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a180f  nop     dword ptr [rax+rax+00h]
0x1401a1814  movzx   eax, word ptr [r14+2]
0x1401a1819  mov     [rdi+38h], rax
0x1401a181d  jmp     loc_1401A1621
0x1401a1822  mov     ebx, 0C000000Dh
0x1401a1827  jmp     loc_1401A1627
0x1401a182c  mov     ebx, 0C00000BBh
0x1401a1831  jmp     loc_1401A1627
0x1401a1836  mov     ecx, r13d
0x1401a1839  mov     eax, [rdi+30h]
0x1401a183c  lea     r8, [rsp+0B8h+var_58]
0x1401a1841  mov     [rsp+0B8h+var_90], eax
0x1401a1845  mov     r9, rdi
0x1401a1848  mov     dword ptr [rsp+0B8h+var_98], ecx
0x1401a184c  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a1851  jmp     loc_1401A1A97
0x1401a1856  test    cs:byte_140177432, r14b
0x1401a185d  jz      loc_1401A1A97
0x1401a1863  lea     rdx, EventPnpRequestComplete
0x1401a186a  jmp     loc_1401A1A83
0x1401a186f  cmp     cs:byte_140177431, r13b
0x1401a1876  jge     loc_1401A1A97
0x1401a187c  mov     rdx, [rdx+8]
0x1401a1880  movzx   eax, byte ptr [rdx+2]
0x1401a1884  cmp     al, 28h ; '('
0x1401a1886  jnz     loc_1401A1975
0x1401a188c  cmp     [rdx+14h], r13d
0x1401a1890  jnz     loc_1401A1A97
0x1401a1896  mov     r12d, [rdx+38h]
0x1401a189a  test    r12d, r12d
0x1401a189d  jz      loc_1401A1A97
0x1401a18a3  mov     r10b, r13b
0x1401a18a6  mov     r11, r13
0x1401a18a9  mov     r14b, r13b
0x1401a18ac  mov     r9, r13
0x1401a18af  mov     r15d, r13d
0x1401a18b2  mov     eax, r15d
0x1401a18b5  mov     ecx, [rdx+rax*4+78h]
0x1401a18b9  cmp     ecx, 80h
0x1401a18bf  jb      short loc_1401A1940
0x1401a18c1  mov     ebp, [rdx+10h]
0x1401a18c4  cmp     ecx, ebp
0x1401a18c6  jnb     short loc_1401A1940
0x1401a18c8  mov     r8d, ecx
0x1401a18cb  mov     ecx, [rcx+rdx]
0x1401a18ce  sub     ecx, 40h ; '@'
0x1401a18d1  jz      short loc_1401A1932
0x1401a18d3  sub     ecx, esi
0x1401a18d5  jz      short loc_1401A1906
0x1401a18d7  cmp     ecx, esi
0x1401a18d9  jnz     short loc_1401A193B
0x1401a18db  lea     rcx, [r8+28h]
0x1401a18df  cmp     rcx, rbp
0x1401a18e2  ja      short loc_1401A193B
0x1401a18e4  xor     r13d, r13d
0x1401a18e7  cmp     [r8+rdx+0Ch], r13d
0x1401a18ec  jbe     short loc_1401A18F5
0x1401a18ee  lea     r11, [rdx+20h]
0x1401a18f2  add     r11, r8
0x1401a18f5  mov     r9, [r8+rdx+18h]
0x1401a18fa  mov     r14b, [r8+rdx+8]
0x1401a18ff  mov     r10b, [r8+rdx+9]
0x1401a1904  jmp     short loc_1401A194F
0x1401a1906  lea     rcx, [r8+38h]
0x1401a190a  cmp     rcx, rbp
0x1401a190d  ja      short loc_1401A193B
0x1401a190f  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a1915  mov     r13b, sil
0x1401a1918  jbe     short loc_1401A1921
0x1401a191a  lea     r11, [rdx+18h]
0x1401a191e  add     r11, r8
0x1401a1921  mov     r14b, [r8+rdx+8]
0x1401a1926  mov     r9, [r8+rdx+10h]
0x1401a192b  mov     r10b, [r8+rdx+9]
0x1401a1930  jmp     short loc_1401A193B
0x1401a1932  lea     rcx, [r8+28h]
0x1401a1936  cmp     rcx, rbp
0x1401a1939  jbe     short loc_1401A195D
0x1401a193b  test    r13b, r13b
0x1401a193e  jnz     short loc_1401A194C
0x1401a1940  add     r15d, esi
0x1401a1943  cmp     r15d, r12d
0x1401a1946  jb      loc_1401A18B2
0x1401a194c  xor     r13d, r13d
0x1401a194f  test    r11, r11
0x1401a1952  jz      loc_1401A1A97
0x1401a1958  mov     cl, [r11]
0x1401a195b  jmp     short loc_1401A198C
0x1401a195d  xor     r13d, r13d
0x1401a1960  cmp     [r8+rdx+0Ah], r13b
0x1401a1965  jbe     short loc_1401A196E
0x1401a1967  lea     r11, [rdx+18h]
0x1401a196b  add     r11, r8
0x1401a196e  mov     r9, [r8+rdx+10h]
0x1401a1973  jmp     short loc_1401A18FA
0x1401a1975  mov     cl, [rdx+48h]
0x1401a1978  mov     r9, [rdx+20h]
0x1401a197c  mov     r10b, [rdx+0Bh]
0x1401a1980  mov     r14b, [rdx+4]
0x1401a1984  test    eax, eax
0x1401a1986  jnz     loc_1401A1A97
0x1401a198c  sub     cl, 8
0x1401a198f  test    cl, 5Dh
0x1401a1992  jnz     loc_1401A1A97
0x1401a1998  mov     bpl, [rdx+3]
0x1401a199c  cmp     bpl, sil
0x1401a199f  jz      loc_1401A1A37
0x1401a19a5  test    r9, r9
0x1401a19a8  jz      loc_1401A1A37
0x1401a19ae  test    r10b, r10b
0x1401a19b1  jz      loc_1401A1A37
0x1401a19b7  mov     al, [r9]
0x1401a19ba  mov     dl, r13b
0x1401a19bd  and     al, 7Fh
0x1401a19bf  movzx   ecx, r10b
0x1401a19c3  sub     al, 72h ; 'r'
0x1401a19c5  add     rcx, r9
0x1401a19c8  cmp     al, sil
0x1401a19cb  mov     r11b, r13b
0x1401a19ce  lea     rax, [r9+8]
0x1401a19d2  mov     r8b, r13b
0x1401a19d5  jbe     short loc_1401A1A19
0x1401a19d7  cmp     rax, rcx
0x1401a19da  ja      short loc_1401A1A2F
0x1401a19dc  movzx   ecx, byte ptr [r9+7]
0x1401a19e1  lea     r8, [r9+0Dh]
0x1401a19e5  mov     dl, [r9+2]
0x1401a19e9  add     ecx, 8
0x1401a19ec  and     dl, 0Fh
0x1401a19ef  movzx   eax, r10b
0x1401a19f3  cmp     ecx, eax
  ... truncated ...
```
