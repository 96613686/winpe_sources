# UdfSeqCacheCloseSession

- ea: `0x14003aa44`
- end: `0x14003b600`
- name: `UdfSeqCacheCloseSession`
- size: `3004`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x1400361d8`
- `0x1400379c0`
- `0x140054830`

## callees

- `0x140007b90`
- `0x140009450`
- `0x14000b808`
- `0x14000ca10`
- `0x14000cad4`
- `0x14000cbcc`
- `0x140016fa8`
- `0x14001bc30`
- `0x14001c080`
- `0x14002c774`
- `0x14002fdbc`
- `0x14002fe08`
- `0x140031b04`
- `0x14003aa44`
- `0x14003b730`
- `0x14003cf04`
- `0x140049020`
- `0x140049bb0`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14003b597`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c37c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003b597`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c37c`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheCloseSession(__int64 a1, char a2)
{
  __int64 v3; // rbx
  unsigned int v4; // r12d
  int v5; // ecx
  bool v6; // al
  char v7; // si
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rcx
  int DiscInfo; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // r12d
  int v15; // edx
  __int64 v16; // rdx
  const char *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // r13d
  unsigned int v20; // esi
  __int64 v21; // rdi
  unsigned int v22; // r12d
  __int16 *v23; // r9
  __int16 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // edx
  int v28; // eax
  __int64 v29; // rdi
  __int64 v30; // r8
  char v31; // si
  __int64 v32; // rdx
  int v33; // eax
  char v34; // al
  char v37; // [rsp+41h] [rbp-E7h]
  unsigned int v38; // [rsp+44h] [rbp-E4h]
  int v39; // [rsp+44h] [rbp-E4h]
  unsigned int v40; // [rsp+48h] [rbp-E0h]
  unsigned int v41; // [rsp+48h] [rbp-E0h]
  unsigned int v42; // [rsp+4Ch] [rbp-DCh]
  unsigned int v43; // [rsp+50h] [rbp-D8h]
  int v44; // [rsp+50h] [rbp-D8h]
  unsigned int v45; // [rsp+54h] [rbp-D4h]
  int v46; // [rsp+54h] [rbp-D4h]
  __int64 v47; // [rsp+68h] [rbp-C0h]
  void *v48; // [rsp+68h] [rbp-C0h]
  __int64 v49; // [rsp+70h] [rbp-B8h]
  __int64 v51; // [rsp+80h] [rbp-A8h]
  __int64 v52; // [rsp+80h] [rbp-A8h]
  __int128 v53; // [rsp+98h] [rbp-90h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-80h]
  int v55; // [rsp+B8h] [rbp-70h]
  _BYTE v56[48]; // [rsp+C0h] [rbp-68h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  v49 = *(_QWORD *)(v3 + 104);
  v4 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  memset(v56, 0, 42);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 43, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  v5 = *(_DWORD *)(*(_QWORD *)(v3 + 104) + 4LL) & 0x10;
  if ( (*(_DWORD *)(v3 + 48) & 0x20000000) != 0 )
  {
    if ( v5 )
      return 3221226048LL;
    v6 = 0;
  }
  else
  {
    v6 = v5 != 0;
  }
  v7 = 0;
  if ( v6 )
    return 3221226048LL;
  UdfFlushVolume(a1, v3, 0, 1, 0, 0);
  UdfAcquireResource(a1, v3 + 2024, 0, 0);
  UdfMarkVolumeClean(a1);
  if ( (*(_DWORD *)(v3 + 2128) & 2) != 0 )
  {
    v10 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 44, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
    }
    DiscInfo = -1073741757;
    goto LABEL_120;
  }
  LOBYTE(v9) = 1;
  DiscInfo = UdfToggleMediaEjectDisable(v8, v3, v9, 0);
  if ( DiscInfo < 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) == 0 )
    {
      goto LABEL_120;
    }
    v12 = 45;
    v13 = *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL);
    goto LABEL_18;
  }
  DiscInfo = UdfReadDiscInfo(*(_QWORD *)(v3 + 24), v56, 42);
  if ( DiscInfo >= 0 )
  {
    if ( (v56[2] & 0xC) != 4 )
    {
      v10 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 47, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
      }
      DiscInfo = -1073741774;
      goto LABEL_120;
    }
    v4 = v56[6];
    v42 = v56[6];
    if ( v56[5] != v56[6] )
    {
      DiscInfo = UdfReadTrackInfo(*(_QWORD *)(v3 + 24), v56[5], &v53, 36);
      if ( DiscInfo < 0 )
        goto LABEL_120;
      LOBYTE(v40) = HIBYTE(v53);
      BYTE1(v40) = BYTE14(v53);
      BYTE2(v40) = BYTE13(v53);
      HIBYTE(v40) = BYTE12(v53);
      LOBYTE(v38) = BYTE11(v54);
      BYTE1(v38) = BYTE10(v54);
      BYTE2(v38) = BYTE9(v54);
      HIBYTE(v38) = BYTE8(v54);
      LOBYTE(v43) = BYTE11(v53);
      BYTE1(v43) = BYTE10(v53);
      BYTE2(v43) = BYTE9(v53);
      HIBYTE(v43) = BYTE8(v53);
      if ( SBYTE6(v53) < 0 && (BYTE7(v53) & 1) != 0 )
      {
        v14 = v38;
        v10 = v43;
        if ( v40 >= v43 + v38 )
        {
          v4 = v42;
        }
        else
        {
          if ( v40 != v43 )
            goto LABEL_38;
          if ( v38 < 0x101 )
            goto LABEL_38;
          v15 = *(_DWORD *)(v49 + 8);
          if ( v38 > 2 * v15 )
            goto LABEL_38;
          v47 = 5 * ((((unsigned __int8)*(_DWORD *)(v49 + 16) + 1) & 7) + 1LL);
          memset(
            *(void **)(v49 + 40 * ((((unsigned __int8)*(_DWORD *)(v49 + 16) + 1) & 7) + 1LL)),
            0,
            (unsigned int)(v15 << *(_DWORD *)(v3 + 72)));
          v39 = *(_DWORD *)(v3 + 72);
          v51 = *(_QWORD *)(v49 + 8 * v47);
          DiscInfo = UdfReadTrackInfo(*(_QWORD *)(v3 + 24), (unsigned int)v56[5] + 1, &v53, 36);
          if ( DiscInfo < 0 )
          {
LABEL_119:
            v4 = v42;
            goto LABEL_120;
          }
          v52 = v51 + (unsigned int)(256 << v39);
          LOBYTE(v45) = BYTE11(v53);
          BYTE1(v45) = BYTE10(v53);
          BYTE2(v45) = BYTE9(v53);
          HIBYTE(v45) = BYTE8(v53);
          v10 = v45;
          if ( v45 - v43 != 512 )
          {
LABEL_38:
            DiscInfo = -1073741774;
            goto LABEL_119;
          }
          UdfReadWriteSectors(
            a1,
            (unsigned __int64)v45 << *(_DWORD *)(v3 + 72),
            *(unsigned int *)(v3 + 68),
            0,
            v52,
            *(_QWORD *)(v3 + 24),
            0);
          UdfVerifyDescriptor(a1, v52, 2, 0x200u, v45, 0);
          *(_DWORD *)(v52 + 12) = v43 + 256;
          UdfUpdateChecksumAndCrc(v52, 512);
          v16 = *(_QWORD *)(v49 + 8 * v47);
          *(_BYTE *)(v16 + 0x8000) = 0;
          *(_BYTE *)(v16 + 32774) = 1;
          qmemcpy((void *)(v16 + 32769), "BEA01", 5);
          *(_BYTE *)(v16 + 34816) = 0;
          *(_BYTE *)(v16 + 34822) = 1;
          v17 = "NSR02";
          if ( *(_WORD *)(v3 + 2138) >= 0x200u )
            v17 = "NSR03";
          *(_DWORD *)(v16 + 34817) = *(_DWORD *)v17;
          *(_BYTE *)(v16 + 34821) = v17[4];
          *(_BYTE *)(v16 + 36864) = 0;
          *(_BYTE *)(v16 + 36870) = 1;
          qmemcpy((void *)(v16 + 36865), "TEA01", 5);
          *(_DWORD *)(v3 + 480) = v56[5];
          v7 = 1;
          DiscInfo = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, 257, 0, *(_QWORD *)(v49 + 8 * v47), 0);
          if ( DiscInfo < 0 )
            goto LABEL_119;
          if ( v14 > 0x101 )
          {
            DiscInfo = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, v14 - 257, 0, 0, 0);
            if ( DiscInfo < 0 )
              goto LABEL_119;
          }
          UdfSeqCacheFlush(a1, v3);
          DiscInfo = UdfSeqCacheSyncCache(v3);
          v4 = v42;
          if ( DiscInfo < 0 )
            goto LABEL_120;
          *(_DWORD *)(v3 + 480) = v42;
        }
      }
    }
    DiscInfo = UdfReadTrackInfo(*(_QWORD *)(v3 + 24), v4, &v53, 36);
    if ( DiscInfo < 0 )
    {
      v10 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 48, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
      }
      goto LABEL_51;
    }
    LOBYTE(v41) = HIBYTE(v53);
    BYTE1(v41) = BYTE14(v53);
    BYTE2(v41) = BYTE13(v53);
    HIBYTE(v41) = BYTE12(v53);
    LOBYTE(v44) = BYTE11(v53);
    BYTE1(v44) = BYTE10(v53);
    BYTE2(v44) = BYTE9(v53);
    HIBYTE(v44) = BYTE8(v53);
    v19 = v41;
    if ( (*(_DWORD *)(v3 + 84) & 0x80) != 0 && v41 - v44 < 0x12C
      || (v10 = *(_DWORD *)(v3 + 84) & 0x8000008, (_DWORD)v10 == 8) && v41 < 0xFEF0 && (BYTE7(v53) & 1) != 0 )
    {
      if ( (*(_DWORD *)(v3 + 84) & 0x80) != 0 )
        v20 = v44 - v41 + 300;
      else
        v20 = 65264 - v41;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          49,
          WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
      }
      v21 = v49;
      v48 = *(void **)(v49 + 40 * (*(unsigned int *)(v49 + 16) + 1LL));
      memset(v48, 0, (unsigned int)(*(_DWORD *)(v49 + 8) << *(_DWORD *)(v3 + 72)));
      do
      {
        v22 = *(_DWORD *)(v21 + 8);
        if ( v20 <= v22 )
          v22 = v20 - 1;
        v46 = v22;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            50,
            WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
        }
        if ( v22 )
        {
          v29 = (__int64)v48;
        }
        else
        {
          *(_DWORD *)(*(_QWORD *)(v3 + 464) + 12LL) = v19 - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
          v23 = *(__int16 **)(v3 + 464);
          v24 = *v23;
          v25 = 86;
          if ( *v23 != 261 )
            v25 = 106;
          v26 = 84;
          if ( v24 != 261 )
            v26 = 104;
          v27 = *(_DWORD *)&v23[v26] + *(_DWORD *)&v23[v25];
          v28 = 216;
          if ( v24 != 266 )
            v28 = 176;
          UdfUpdateChecksumAndCrc(*(_QWORD *)(v3 + 464), (unsigned int)(v28 + v27));
          v29 = *(_QWORD *)(v3 + 464);
          v48 = (void *)v29;
          v22 = 1;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              51,
              WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
          }
          v46 = 1;
        }
        DiscInfo = UdfSeqCacheWriteBlocksForFile(a1, -1, 0, v22, 0, v29, 0);
        if ( DiscInfo < 0 )
        {
          v7 = 0;
          goto LABEL_119;
        }
        v20 -= v22;
        v19 += v46;
        v21 = v49;
      }
      while ( v20 );
      UdfSeqCacheFlush(a1, v3);
      DiscInfo = UdfSeqCacheSyncCache(v3);
      v7 = 0;
      v4 = v42;
      if ( DiscInfo < 0 )
        goto LABEL_120;
    }
    v30 = *(unsigned int *)(v3 + 84);
    if ( (v30 & 0x8000000) != 0 )
    {
      v10 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 52, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
        v30 = *(unsigned int *)(v3 + 84);
      }
      v31 = 1;
    }
    else
    {
      v31 = a2;
    }
    LOBYTE(v18) = v31 == 0;
    if ( !(unsigned __int8)UdfPrepareDeviceForWrite(v10, *(_QWORD *)(v3 + 24), v30, v18) )
    {
      DiscInfo = -1073741435;
LABEL_51:
      v7 = 0;
      goto LABEL_120;
    }
    DiscInfo = UdfCloseTrackSession(*(_QWORD *)(v3 + 24), 1, (unsigned __int16)v4);
    if ( DiscInfo < 0 )
    {
LABEL_102:
      if ( DiscInfo >= 0 )
        DiscInfo = UdfReadDiscInfo(*(_QWORD *)(v3 + 24), v56, 42);
      LOBYTE(v10) = v56[2];
      if ( DiscInfo < 0 || (v34 = (v56[2] >> 2) & 3, v34 != 3) && v34 )
      {
        *(_DWORD *)(*(_QWORD *)(v3 + 24) + 48LL) |= 2u;
        v7 = 0;
        if ( DiscInfo >= 0 )
          DiscInfo = -1073741435;
        goto LABEL_120;
      }
      *(_DWORD *)(v3 + 480) = v56[6];
      LOBYTE(v10) = v10 & 3;
      v37 = v10;
      if ( (_BYTE)v10 != 2 )
      {
        DiscInfo = UdfQueryFreeBlocksAndNWA(v3, v3 + 668, v3 + 684);
        LOBYTE(v10) = v37;
      }
      if ( DiscInfo < 0 || (_BYTE)v10 == 2 || *(_DWORD *)(v3 + 668) <= *(_DWORD *)(v3 + 680) )
      {
        *(_DWORD *)(v3 + 48) |= 0x4010u;
        v10 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            53,
            WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
        }
      }
      else
      {
        *(_DWORD *)(v3 + 2128) |= 0x80u;
      }
      *(_DWORD *)(v3 + 2128) &= ~0x10u;
      goto LABEL_51;
    }
    v32 = 2;
    if ( v31 )
    {
      v33 = *(_DWORD *)(v3 + 84);
      switch ( v33 )
      {
        case 528:
          goto LABEL_100;
        case 67108888:
LABEL_99:
          v32 = 5;
          break;
        case 134218256:
LABEL_100:
          v32 = 6;
          break;
        case 201326616:
          goto LABEL_99;
      }
    }
    DiscInfo = UdfCloseTrackSession(*(_QWORD *)(v3 + 24), v32, 0);
    goto LABEL_102;
  }
  v10 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) == 0 )
  {
    goto LABEL_120;
  }
  v12 = 46;
  v13 = *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL);
LABEL_18:
  WPP_SF_(v13, v12, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
LABEL_120:
  if ( v7 )
    *(_DWORD *)(v3 + 480) = v4;
  UdfToggleMediaEjectDisable(v10, v3, 0, 0);
  ExReleaseResourceLite((PERESOURCE)(v3 + 2024));
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 54, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  return (unsigned int)DiscInfo;
}

```

## disassembly

```asm
0x14003aa44  mov     r11, rsp
0x14003aa47  mov     [r11+10h], rbx
0x14003aa4b  mov     [r11+18h], rsi
0x14003aa4f  push    rdi
0x14003aa50  push    r12
0x14003aa52  push    r13
0x14003aa54  push    r14
0x14003aa56  push    r15
0x14003aa58  sub     rsp, 100h
0x14003aa5f  mov     rax, cs:__security_cookie
0x14003aa66  xor     rax, rsp
0x14003aa69  mov     [rsp+128h+var_38], rax
0x14003aa71  mov     [rsp+128h+var_E7], dl
0x14003aa75  mov     r13, rcx
0x14003aa78  mov     [rsp+128h+var_B0], rcx
0x14003aa7d  mov     rbx, [rcx+10h]
0x14003aa81  mov     [rsp+128h+var_A0], rbx
0x14003aa89  mov     r8, [rbx+68h]
0x14003aa8d  mov     [rsp+128h+var_B8], r8
0x14003aa92  xor     edx, edx
0x14003aa94  mov     r12d, edx
0x14003aa97  mov     [rsp+128h+var_DC], edx
0x14003aa9b  mov     [rsp+128h+var_E0], edx
0x14003aa9f  mov     [rsp+128h+var_E4], edx
0x14003aaa3  mov     [rsp+128h+var_D8], edx
0x14003aaa7  mov     [rsp+128h+var_D4], edx
0x14003aaab  xorps   xmm0, xmm0
0x14003aaae  xor     eax, eax
0x14003aab0  movups  [rsp+128h+var_90], xmm0
0x14003aab8  movups  xmmword ptr [r11-80h], xmm0
0x14003aabd  mov     [r11-70h], eax
0x14003aac1  xorps   xmm1, xmm1
0x14003aac4  movups  xmmword ptr [r11-68h], xmm1
0x14003aac9  movups  xmmword ptr [r11-58h], xmm1
0x14003aace  movups  xmmword ptr [r11-4Eh], xmm1
0x14003aad3  lea     rdi, WPP_GLOBAL_Control
0x14003aada  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aae1  mov     r14d, 20000000h
0x14003aae7  lea     r15, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14003aaee  cmp     rcx, rdi
0x14003aaf1  jz      short loc_14003AB0A
0x14003aaf3  test    [rcx+2Ch], r14d
0x14003aaf7  jz      short loc_14003AB0A
0x14003aaf9  lea     edx, [rax+2Bh]
0x14003aafc  mov     r8, r15
0x14003aaff  mov     rcx, [rcx+18h]
0x14003ab03  call    WPP_SF_
0x14003ab08  xor     edx, edx
0x14003ab0a  mov     rax, [rbx+68h]
0x14003ab0e  mov     ecx, [rax+4]
0x14003ab11  and     ecx, 10h
0x14003ab14  mov     eax, [rbx+30h]
0x14003ab17  test    r14d, eax
0x14003ab1a  jnz     short loc_14003AB23
0x14003ab1c  test    ecx, ecx
0x14003ab1e  setnz   al
0x14003ab21  jmp     short loc_14003AB2D
0x14003ab23  test    ecx, ecx
0x14003ab25  jnz     loc_14003B5CD
0x14003ab2b  mov     al, dl
0x14003ab2d  mov     [rsp+128h+var_D0], dl
0x14003ab31  mov     sil, dl
0x14003ab34  mov     [rsp+128h+var_E8], dl
0x14003ab38  test    al, al
0x14003ab3a  jnz     loc_14003B5CD
0x14003ab40  mov     [rsp+128h+var_100], dl; char
0x14003ab44  mov     [rsp+128h+var_108], dl; char
0x14003ab48  mov     r9b, 1
0x14003ab4b  xor     r8d, r8d
0x14003ab4e  mov     rdx, rbx
0x14003ab51  mov     rcx, r13; int
0x14003ab54  call    UdfFlushVolume
0x14003ab59  lea     rdx, [rbx+7E8h]
0x14003ab60  xor     r9d, r9d
0x14003ab63  xor     r8d, r8d
0x14003ab66  mov     rcx, r13
0x14003ab69  call    UdfAcquireResource
0x14003ab6e  mov     [rsp+128h+var_D0], 1
0x14003ab73  xor     r9d, r9d
0x14003ab76  mov     r8b, 1
0x14003ab79  mov     rdx, rbx
0x14003ab7c  mov     rcx, r13
0x14003ab7f  call    UdfMarkVolumeClean
0x14003ab84  mov     eax, [rbx+850h]
0x14003ab8a  test    al, 2
0x14003ab8c  jz      short loc_14003ABBD
0x14003ab8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab95  cmp     rcx, rdi
0x14003ab98  jz      short loc_14003ABB3
0x14003ab9a  mov     eax, [rcx+2Ch]
0x14003ab9d  test    r14d, eax
0x14003aba0  jz      short loc_14003ABB3
0x14003aba2  mov     edx, 2Ch ; ','
0x14003aba7  mov     r8, r15
0x14003abaa  mov     rcx, [rcx+18h]
0x14003abae  call    WPP_SF_
0x14003abb3  mov     edi, 0C0000043h
0x14003abb8  jmp     loc_14003B56F
0x14003abbd  xor     r9d, r9d
0x14003abc0  mov     r8b, 1
0x14003abc3  mov     rdx, rbx
0x14003abc6  call    UdfToggleMediaEjectDisable
0x14003abcb  mov     edi, eax
0x14003abcd  test    eax, eax
0x14003abcf  jns     short loc_14003AC08
0x14003abd1  mov     rax, cs:WPP_GLOBAL_Control
0x14003abd8  lea     r13, WPP_GLOBAL_Control
0x14003abdf  cmp     rax, r13
0x14003abe2  jz      loc_14003B576
0x14003abe8  test    [rax+2Ch], r14d
0x14003abec  jz      loc_14003B576
0x14003abf2  mov     edx, 2Dh ; '-'
0x14003abf7  mov     rcx, [rax+18h]
0x14003abfb  mov     r8, r15
0x14003abfe  call    WPP_SF_
0x14003ac03  jmp     loc_14003B576
0x14003ac08  mov     r8d, 2Ah ; '*'
0x14003ac0e  lea     rdx, [rsp+128h+var_68]
0x14003ac16  mov     rcx, [rbx+18h]
0x14003ac1a  call    UdfReadDiscInfo
0x14003ac1f  mov     edi, eax
0x14003ac21  test    eax, eax
0x14003ac23  jns     short loc_14003AC53
0x14003ac25  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac2c  lea     r13, WPP_GLOBAL_Control
0x14003ac33  cmp     rcx, r13
0x14003ac36  jz      loc_14003B576
0x14003ac3c  mov     eax, [rcx+2Ch]
0x14003ac3f  test    r14d, eax
0x14003ac42  jz      loc_14003B576
0x14003ac48  mov     edx, 2Eh ; '.'
0x14003ac4d  mov     rcx, [rcx+18h]
0x14003ac51  jmp     short loc_14003ABFB
0x14003ac53  mov     al, [rsp+128h+var_66]
0x14003ac5a  and     al, 0Ch
0x14003ac5c  cmp     al, 4
0x14003ac5e  jz      short loc_14003AC96
0x14003ac60  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac67  lea     r13, WPP_GLOBAL_Control
0x14003ac6e  cmp     rcx, r13
0x14003ac71  jz      short loc_14003AC8C
0x14003ac73  mov     eax, [rcx+2Ch]
0x14003ac76  test    r14d, eax
0x14003ac79  jz      short loc_14003AC8C
0x14003ac7b  mov     edx, 2Fh ; '/'
0x14003ac80  mov     r8, r15
0x14003ac83  mov     rcx, [rcx+18h]
0x14003ac87  call    WPP_SF_
0x14003ac8c  mov     edi, 0C0000032h
0x14003ac91  jmp     loc_14003B576
0x14003ac96  movzx   eax, [rsp+128h+var_63]
0x14003ac9e  movzx   r12d, [rsp+128h+var_62]
0x14003aca7  mov     [rsp+128h+var_DC], r12d
0x14003acac  cmp     eax, r12d
0x14003acaf  jz      loc_14003B047
0x14003acb5  mov     r9d, 24h ; '$'
0x14003acbb  lea     r8, [rsp+128h+var_90]
0x14003acc3  mov     edx, eax
0x14003acc5  mov     rcx, [rbx+18h]
0x14003acc9  call    UdfReadTrackInfo
0x14003acce  mov     edi, eax
0x14003acd0  test    eax, eax
0x14003acd2  js      loc_14003B56F
0x14003acd8  mov     al, byte ptr [rsp+128h+var_90+0Fh]
0x14003acdf  mov     byte ptr [rsp+128h+var_E0], al
0x14003ace3  mov     al, byte ptr [rsp+128h+var_90+0Eh]
0x14003acea  mov     byte ptr [rsp+128h+var_E0+1], al
0x14003acee  mov     al, byte ptr [rsp+128h+var_90+0Dh]
0x14003acf5  mov     byte ptr [rsp+128h+var_E0+2], al
0x14003acf9  mov     al, byte ptr [rsp+128h+var_90+0Ch]
0x14003ad00  mov     byte ptr [rsp+128h+var_E0+3], al
0x14003ad04  mov     al, [rsp+128h+var_75]
0x14003ad0b  mov     byte ptr [rsp+128h+var_E4], al
0x14003ad0f  mov     al, [rsp+128h+var_76]
0x14003ad16  mov     byte ptr [rsp+128h+var_E4+1], al
0x14003ad1a  mov     al, [rsp+128h+var_77]
0x14003ad21  mov     byte ptr [rsp+128h+var_E4+2], al
0x14003ad25  mov     al, [rsp+128h+var_78]
0x14003ad2c  mov     byte ptr [rsp+128h+var_E4+3], al
0x14003ad30  mov     al, byte ptr [rsp+128h+var_90+0Bh]
0x14003ad37  mov     byte ptr [rsp+128h+var_D8], al
0x14003ad3b  mov     al, byte ptr [rsp+128h+var_90+0Ah]
0x14003ad42  mov     byte ptr [rsp+128h+var_D8+1], al
0x14003ad46  mov     al, byte ptr [rsp+128h+var_90+9]
0x14003ad4d  mov     byte ptr [rsp+128h+var_D8+2], al
0x14003ad51  mov     al, byte ptr [rsp+128h+var_90+8]
0x14003ad58  mov     byte ptr [rsp+128h+var_D8+3], al
0x14003ad5c  test    byte ptr [rsp+128h+var_90+6], 80h
0x14003ad64  jz      loc_14003B047
0x14003ad6a  test    byte ptr [rsp+128h+var_90+7], 1
0x14003ad72  jz      loc_14003B047
0x14003ad78  mov     r12d, [rsp+128h+var_E4]
0x14003ad7d  mov     ecx, [rsp+128h+var_D8]
0x14003ad81  lea     eax, [rcx+r12]
0x14003ad85  cmp     [rsp+128h+var_E0], eax
0x14003ad89  jnb     loc_14003B042
0x14003ad8f  cmp     [rsp+128h+var_E0], ecx
0x14003ad93  jnz     loc_14003AE7E
0x14003ad99  cmp     r12d, 101h
0x14003ada0  jb      loc_14003AE7E
0x14003ada6  mov     rdi, [rsp+128h+var_B8]
0x14003adab  mov     edx, [rdi+8]
0x14003adae  lea     eax, [rdx+rdx]
0x14003adb1  cmp     r12d, eax
0x14003adb4  ja      loc_14003AE7E
0x14003adba  mov     eax, [rdi+10h]
0x14003adbd  inc     eax
0x14003adbf  and     eax, 7
0x14003adc2  inc     rax
0x14003adc5  lea     rax, [rax+rax*4]
0x14003adc9  mov     [rsp+128h+var_C0], rax
0x14003adce  mov     ecx, [rbx+48h]
0x14003add1  shl     edx, cl
0x14003add3  mov     r8d, edx; Size
0x14003add6  xor     edx, edx; Val
0x14003add8  mov     rcx, [rdi+rax*8]; void *
0x14003addc  call    memset
0x14003ade1  mov     eax, [rbx+48h]
0x14003ade4  mov     [rsp+128h+var_E4], eax
0x14003ade8  mov     rax, [rsp+128h+var_C0]
0x14003aded  mov     rax, [rdi+rax*8]
0x14003adf1  mov     [rsp+128h+var_A8], rax
0x14003adf9  movzx   edx, [rsp+128h+var_63]
0x14003ae01  inc     edx
0x14003ae03  mov     r9d, 24h ; '$'
0x14003ae09  lea     r8, [rsp+128h+var_90]
0x14003ae11  mov     rcx, [rbx+18h]
0x14003ae15  call    UdfReadTrackInfo
0x14003ae1a  mov     edi, eax
0x14003ae1c  test    eax, eax
0x14003ae1e  js      loc_14003B56A
0x14003ae24  mov     ecx, [rsp+128h+var_E4]
0x14003ae28  mov     edx, 100h
0x14003ae2d  shl     edx, cl
0x14003ae2f  add     rdx, [rsp+128h+var_A8]
0x14003ae37  mov     [rsp+128h+var_A8], rdx
0x14003ae3f  mov     al, byte ptr [rsp+128h+var_90+0Bh]
0x14003ae46  mov     byte ptr [rsp+128h+var_D4], al
0x14003ae4a  mov     al, byte ptr [rsp+128h+var_90+0Ah]
0x14003ae51  mov     byte ptr [rsp+128h+var_D4+1], al
0x14003ae55  mov     al, byte ptr [rsp+128h+var_90+9]
0x14003ae5c  mov     byte ptr [rsp+128h+var_D4+2], al
0x14003ae60  mov     al, byte ptr [rsp+128h+var_90+8]
0x14003ae67  mov     byte ptr [rsp+128h+var_D4+3], al
0x14003ae6b  mov     ecx, [rsp+128h+var_D4]
0x14003ae6f  mov     eax, ecx
0x14003ae71  mov     edi, [rsp+128h+var_D8]
0x14003ae75  sub     eax, edi
0x14003ae77  cmp     eax, 200h
0x14003ae7c  jz      short loc_14003AE88
0x14003ae7e  mov     edi, 0C0000032h
0x14003ae83  jmp     loc_14003B56A
0x14003ae88  mov     rdx, rcx
0x14003ae8b  mov     ecx, [rbx+48h]
0x14003ae8e  shl     rdx, cl
0x14003ae91  mov     byte ptr [rsp+128h+var_F8], 0
0x14003ae96  mov     rax, [rbx+18h]
0x14003ae9a  mov     qword ptr [rsp+128h+var_100], rax
0x14003ae9f  mov     rsi, [rsp+128h+var_A8]
0x14003aea7  mov     qword ptr [rsp+128h+var_108], rsi
0x14003aeac  xor     r9d, r9d
0x14003aeaf  mov     r8d, [rbx+44h]
0x14003aeb3  mov     rcx, r13
0x14003aeb6  call    UdfReadWriteSectors
0x14003aebb  mov     r8d, 2
0x14003aec1  mov     dword ptr [rsp+128h+var_100], 0
0x14003aec9  mov     eax, [rsp+128h+var_D4]
0x14003aecd  mov     dword ptr [rsp+128h+var_108], eax
0x14003aed1  mov     r9d, 200h
0x14003aed7  mov     rdx, rsi
0x14003aeda  mov     rcx, r13
0x14003aedd  call    UdfVerifyDescriptor
0x14003aee2  lea     eax, [rdi+100h]
0x14003aee8  mov     [rsi+0Ch], eax
0x14003aeeb  mov     edi, 200h
0x14003aef0  mov     edx, edi
0x14003aef2  mov     rcx, rsi
0x14003aef5  call    UdfUpdateChecksumAndCrc
0x14003aefa  mov     r8, [rsp+128h+var_B8]
0x14003aeff  mov     r9, [rsp+128h+var_C0]
0x14003af04  mov     rdx, [r8+r9*8]
0x14003af08  xor     r11d, r11d
0x14003af0b  mov     [rdx+8000h], r11b
0x14003af12  mov     byte ptr [rdx+8006h], 1
0x14003af19  mov     eax, dword ptr cs:aBea01; "BEA01"
0x14003af1f  mov     [rdx+8001h], eax
0x14003af25  mov     al, byte ptr cs:aBea01+4; "1"
0x14003af2b  mov     [rdx+8005h], al
0x14003af31  mov     [rdx+8800h], r11b
0x14003af38  mov     byte ptr [rdx+8806h], 1
0x14003af3f  lea     r10, aNsr03; "NSR03"
0x14003af46  lea     rcx, aNsr02; "NSR02"
0x14003af4d  cmp     [rbx+85Ah], di
0x14003af54  cmovnb  rcx, r10
0x14003af58  mov     eax, [rcx]
0x14003af5a  mov     [rdx+8801h], eax
0x14003af60  mov     al, [rcx+4]
0x14003af63  mov     [rdx+8805h], al
0x14003af69  mov     [rdx+9000h], r11b
0x14003af70  mov     byte ptr [rdx+9006h], 1
  ... truncated ...
```
