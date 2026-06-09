# VidVppSetup

- ea: `0x1400fa2e8`
- end: `0x1400faa0f`
- name: `VidVppSetup`
- size: `1831`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x140098628`

## callees

- `0x14000860c`
- `0x140008fd8`
- `0x14001362c`
- `0x140013658`
- `0x140021606`
- `0x140021650`
- `0x140021800`
- `0x140038630`
- `0x140074e58`
- `0x140098b5c`
- `0x140098ce4`
- `0x140099e84`
- `0x1400ed478`
- `0x1400f91bc`
- `0x1400fa2e8`

## import_xrefs

- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fa831`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fa935`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fa831`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fa935`
- `winhvr!WinHvGetVpRegisters` at `0x1400fa68b`
- `winhvr!WinHvGetVpRegisters` at `0x1400fa68b`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fa7d1`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fa8ef`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fa7d1`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fa8ef`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fa766`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fa8b7`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fa766`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fa8b7`
- `winhvr!WinHvCreateVp` at `0x1400fa437`
- `winhvr!WinHvCreateVp` at `0x1400fa437`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x1400fa548`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x1400fa548`
- `winhvr!WinHvSetVpRegisters` at `0x1400fa5e7`
- `winhvr!WinHvSetVpRegisters` at `0x1400fa5e7`

## pseudocode

```c
__int64 __fastcall VidVppSetup(__int64 *a1, __int64 a2)
{
  __int64 v4; // r8
  bool v5; // r14
  __int64 v6; // rsi
  char v7; // r12
  __int64 v8; // rax
  __int64 v9; // rdx
  __int128 v10; // xmm0
  __int64 v11; // r9
  __int64 v12; // rcx
  int VpRegisters; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  char v16; // dl
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
  _DWORD *v20; // r14
  int v21; // eax
  __int64 *v22; // r14
  __int64 v23; // rbx
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v33[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[510]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v36[2]; // [rsp+1060h] [rbp+F60h] BYREF
  _OWORD v37[2]; // [rsp+1080h] [rbp+F80h] BYREF

  v31 = 0;
  v32 = 0;
  memset(v36, 0, sizeof(v36));
  memset(v37, 0, sizeof(v37));
  v34 = 0;
  HviGetHypervisorFeatures(&v34);
  v5 = 0;
  if ( (v34 & 0x100000000LL) != 0 )
  {
    v34 = 0;
    HviGetHypervisorFeatures(&v34);
    if ( (v34 & 0x100000000000LL) == 0 )
      v5 = 1;
  }
  v6 = *a1;
  v7 = 0;
  v31 = 0;
  if ( *(_BYTE *)(v6 + 8761) && *(_DWORD *)(v6 + 8632) == 2 )
  {
    *((_DWORD *)a1 + 10) |= 4u;
    v7 = 1;
  }
  if ( (a1[5] & 4) != 0 )
    goto LABEL_27;
  v8 = *((unsigned __int8 *)a1 + 12);
  v34 = 0xFFFFFFFFFFFFFFFFuLL;
  v9 = *(unsigned __int8 *)(v8 + v6 + 2105) | 0x80000000;
  if ( *(char *)(v6 + 16) < 0 )
    v9 = *(unsigned __int8 *)(v8 + v6 + 2105);
  if ( v5 )
    v10 = v34;
  else
    v10 = *((_OWORD *)a1 + 1);
  v11 = *((unsigned int *)a1 + 2);
  v12 = *(_QWORD *)(v6 + 648);
  v34 = v10;
  VpRegisters = WinHvCreateVp(v12, v9, &v34, v11, 0);
  if ( VpRegisters >= 0 )
  {
    *((_DWORD *)a1 + 10) |= 4u;
    if ( (*(_BYTE *)(v6 + 696) & 4) != 0 && v5 && *(_BYTE *)(a2 + 51200) == 1 )
    {
      memset(v35, 0, 0xFE8u);
      v15 = *((unsigned int *)a1 + 2);
      v4 = *(unsigned int *)(a2 + 8 * v15 + 51204);
      if ( (unsigned int)v4 <= *(_DWORD *)(a2 + 8 * v15 + 51208) )
      {
        do
        {
          v16 = v4 & 0x3F;
          v17 = (unsigned __int64)(unsigned int)v4 >> 6;
          LODWORD(v4) = v4 + 1;
          v35[v17 + 2] |= 1LL << v16;
        }
        while ( (unsigned int)v4 <= *(_DWORD *)(a2 + 8 * v15 + 51208) );
        v35[0] = 0;
        v35[1] = *(_DWORD *)(a2 + 8 * v15 + 51208) >> 6 == 63
               ? -1LL
               : (1LL << ((unsigned __int8)(*(_DWORD *)(a2 + 8 * v15 + 51208) >> 6) + 1)) - 1;
        v18 = *(_QWORD *)(v6 + 648);
        *(_QWORD *)&v34 = (unsigned int)v15 | 0x100000000000000LL;
        VpRegisters = WinHvSetPartitionPropertyEx(v18, 268439552, v34, v35, 4072);
        if ( (int)(VpRegisters + 0x80000000) >= 0 && VpRegisters != -1070268386 )
        {
          VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 860);
          goto LABEL_69;
        }
      }
    }
LABEL_27:
    v19 = *((unsigned int *)a1 + 2);
    v33[0] = 524300;
    if ( *(_QWORD *)(a2 + 8 * v19 + 2048) > 0xFFFFFFFF )
    {
      LODWORD(v36[0]) = -1;
      VpRegisters = -1073741675;
      VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 890);
      goto LABEL_69;
    }
    LOBYTE(v4) = 0;
    LODWORD(v36[0]) = *(_QWORD *)(a2 + 8 * v19 + 2048);
    if ( v7 )
    {
      v20 = (_DWORD *)(v6 + 32);
      if ( (*(_DWORD *)(v6 + 32) & 0x1E0LL) == 0 )
      {
        VpRegisters = WinHvGetVpRegisters(*(_QWORD *)(v6 + 648), v19, v4, 1, v33, &v32, v37);
        if ( VpRegisters < 0 || *(_QWORD *)&v37[0] != *(_QWORD *)&v36[0] )
        {
          VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 966);
          goto LABEL_66;
        }
      }
    }
    else
    {
      VpRegisters = WinHvSetVpRegisters(*(_QWORD *)(v6 + 648), v19, v4, 1, v33, v36, &v32);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 935);
        goto LABEL_69;
      }
      v20 = (_DWORD *)(v6 + 32);
    }
    VpRegisters = VidMessageSlotSetup(a1 + 232);
    if ( VpRegisters < 0 )
    {
      VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 983);
      goto LABEL_69;
    }
    v21 = *((_DWORD *)a1 + 502) | 2;
    a1[252] = v6;
    *((_DWORD *)a1 + 502) = v21;
    *((_DWORD *)a1 + 503) = *((_DWORD *)a1 + 2);
    VpRegisters = VidMessagePoolRequiredCountInc(v6, 2);
    if ( VpRegisters < 0 )
      goto LABEL_69;
    *((_DWORD *)a1 + 10) |= 2u;
    VpRegisters = VidThreadPoolThreadAdd(v6 + 3488);
    if ( VpRegisters < 0 )
      goto LABEL_69;
    *((_DWORD *)a1 + 10) |= 1u;
    if ( (*(_BYTE *)(v6 + 16) & 4) != 0 )
    {
      VpRegisters = VidExtHypercallVpPagesAlloc(a1);
      if ( VpRegisters < 0 )
        goto LABEL_69;
    }
    if ( (*v20 & 0x1E0LL) == 0 )
    {
      v22 = a1 + 275;
      v23 = -1;
      a1[275] = 0;
      if ( (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
      {
        if ( (int)VidHvMemAllocatePagesForOverlay(v6, 1, a1 + 275) < 0 )
        {
          VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1037);
LABEL_46:
          VpRegisters = -1073741670;
          goto LABEL_69;
        }
        v23 = *(_QWORD *)(*v22 + 48);
      }
      LOBYTE(v24) = 15;
      VpRegisters = WinHvMapVpStatePage2(*(_QWORD *)(v6 + 648), *((unsigned int *)a1 + 2), 0, v24, v23, &v31);
      if ( VpRegisters < 0 )
      {
        if ( *v22 )
        {
          VidHvMemFreePagesForOverlay(v6);
          *v22 = 0;
        }
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1064);
        goto LABEL_69;
      }
      v25 = v31 << 12;
      *((_BYTE *)a1 + 2280) = 1;
      v26 = MmMapIoSpaceEx(v25, 4096, 4);
      a1[274] = v26;
      if ( !v26 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1073);
        goto LABEL_46;
      }
      VpRegisters = VidClientBufferPrepareFromOverlayPages((__int64)(a1 + 276), &v31, 1u);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1087);
        goto LABEL_69;
      }
    }
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
    {
      if ( (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
        __int2c();
      LOBYTE(v27) = 15;
      VpRegisters = WinHvMapVpStatePage2(*(_QWORD *)(v6 + 648), *((unsigned int *)a1 + 2), 1, v27, -1, &v31);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1109);
        goto LABEL_69;
      }
      v28 = v31 << 12;
      *((_BYTE *)a1 + 2368) = 1;
      v29 = MmMapIoSpaceEx(v28, 4096, 2);
      a1[286] = v29;
      if ( !v29 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1118);
        goto LABEL_46;
      }
      VpRegisters = VidClientBufferPrepareFromOverlayPages((__int64)(a1 + 287), &v31, 1u);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1130);
        goto LABEL_69;
      }
    }
    VpRegisters = VidVppInterceptThreadSetup(a1);
LABEL_66:
    if ( VpRegisters >= 0 )
      return (unsigned int)VpRegisters;
    goto LABEL_69;
  }
  VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 809);
LABEL_69:
  LOBYTE(v14) = 1;
  VidVpTeardown(a1, v14);
  return (unsigned int)VpRegisters;
}

```

## disassembly

```asm
0x1400fa2e8  mov     [rsp-8+arg_10], rbx
0x1400fa2ed  mov     [rsp-8+arg_18], rsi
0x1400fa2f2  push    rbp
0x1400fa2f3  push    rdi
0x1400fa2f4  push    r12
0x1400fa2f6  push    r14
0x1400fa2f8  push    r15
0x1400fa2fa  lea     rbp, [rsp-0FB0h]
0x1400fa302  mov     eax, 10B0h
0x1400fa307  call    __chkstk_0
0x1400fa30c  sub     rsp, rax
0x1400fa30f  mov     rax, cs:__security_cookie
0x1400fa316  xor     rax, rsp
0x1400fa319  mov     [rbp+0FD0h+var_30], rax
0x1400fa320  xorps   xmm0, xmm0
0x1400fa323  mov     [rsp+10D0h+var_1090], 0
0x1400fa32c  mov     rdi, rcx
0x1400fa32f  mov     [rsp+10D0h+var_1088], 0
0x1400fa338  xorps   xmm1, xmm1
0x1400fa33b  lea     rcx, [rsp+10D0h+var_1070]
0x1400fa340  movups  [rbp+0FD0h+var_70], xmm0
0x1400fa347  mov     r15, rdx
0x1400fa34a  movups  [rbp+0FD0h+var_60], xmm0
0x1400fa351  movups  [rbp+0FD0h+var_50], xmm1
0x1400fa358  movups  [rbp+0FD0h+var_40], xmm1
0x1400fa35f  movups  [rsp+10D0h+var_1070], xmm0
0x1400fa364  call    HviGetHypervisorFeatures
0x1400fa369  mov     rax, 100000000h
0x1400fa373  test    qword ptr [rsp+10D0h+var_1070], rax
0x1400fa378  jz      short loc_1400FA3A2
0x1400fa37a  xorps   xmm0, xmm0
0x1400fa37d  lea     rcx, [rsp+10D0h+var_1070]
0x1400fa382  movups  [rsp+10D0h+var_1070], xmm0
0x1400fa387  call    HviGetHypervisorFeatures
0x1400fa38c  mov     rax, 100000000000h
0x1400fa396  test    qword ptr [rsp+10D0h+var_1070], rax
0x1400fa39b  jnz     short loc_1400FA3A2
0x1400fa39d  mov     r14b, 1
0x1400fa3a0  jmp     short loc_1400FA3A5
0x1400fa3a2  xor     r14b, r14b
0x1400fa3a5  mov     rsi, [rdi]
0x1400fa3a8  xor     r12b, r12b
0x1400fa3ab  mov     [rsp+10D0h+var_1090], 0
0x1400fa3b4  cmp     [rsi+2239h], r12b
0x1400fa3bb  jz      short loc_1400FA3CD
0x1400fa3bd  cmp     dword ptr [rsi+21B8h], 2
0x1400fa3c4  jnz     short loc_1400FA3CD
0x1400fa3c6  or      dword ptr [rdi+28h], 4
0x1400fa3ca  mov     r12b, 1
0x1400fa3cd  mov     eax, [rdi+28h]
0x1400fa3d0  test    al, 4
0x1400fa3d2  jnz     loc_1400FA587
0x1400fa3d8  movzx   eax, byte ptr [rdi+0Ch]
0x1400fa3dc  mov     r8d, 80000000h
0x1400fa3e2  mov     qword ptr [rsp+10D0h+var_1070+8], 0
0x1400fa3eb  mov     qword ptr [rsp+10D0h+var_1070], 0FFFFFFFFFFFFFFFFh
0x1400fa3f4  movzx   ecx, byte ptr [rax+rsi+839h]
0x1400fa3fc  mov     edx, ecx
0x1400fa3fe  or      edx, r8d
0x1400fa401  test    byte ptr [rsi+10h], 80h
0x1400fa405  cmovnz  edx, ecx
0x1400fa408  test    r14b, r14b
0x1400fa40b  jnz     short loc_1400FA413
0x1400fa40d  movups  xmm0, xmmword ptr [rdi+10h]
0x1400fa411  jmp     short loc_1400FA418
0x1400fa413  movaps  xmm0, [rsp+10D0h+var_1070]
0x1400fa418  mov     r9d, [rdi+8]
0x1400fa41c  lea     r8, [rsp+10D0h+var_1070]
0x1400fa421  mov     rcx, [rsi+288h]
0x1400fa428  movdqa  [rsp+10D0h+var_1070], xmm0
0x1400fa42e  mov     [rsp+10D0h+var_10B0], 0
0x1400fa437  call    cs:__imp_WinHvCreateVp
0x1400fa43e  nop     dword ptr [rax+rax+00h]
0x1400fa443  mov     ebx, eax
0x1400fa445  test    eax, eax
0x1400fa447  jns     short loc_1400FA467
0x1400fa449  mov     r8d, 329h
0x1400fa44f  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa456  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa45d  call    VidTraceErrorInternal0
0x1400fa462  jmp     loc_1400FA9D7
0x1400fa467  or      dword ptr [rdi+28h], 4
0x1400fa46b  test    byte ptr [rsi+2B8h], 4
0x1400fa472  jz      loc_1400FA587
0x1400fa478  test    r14b, r14b
0x1400fa47b  jz      loc_1400FA587
0x1400fa481  cmp     byte ptr [r15+0C800h], 1
0x1400fa489  jnz     loc_1400FA587
0x1400fa48f  mov     ebx, 0FE8h
0x1400fa494  lea     rcx, [rsp+10D0h+var_1060]; void *
0x1400fa499  mov     r8d, ebx; Size
0x1400fa49c  xor     edx, edx; Val
0x1400fa49e  call    memset
0x1400fa4a3  mov     r9d, [rdi+8]
0x1400fa4a7  mov     r8d, [r15+r9*8+0C804h]
0x1400fa4af  cmp     r8d, [r15+r9*8+0C808h]
0x1400fa4b7  ja      loc_1400FA587
0x1400fa4bd  mov     edx, r8d
0x1400fa4c0  mov     ecx, r8d
0x1400fa4c3  and     edx, 3Fh
0x1400fa4c6  shr     rcx, 6
0x1400fa4ca  inc     r8d
0x1400fa4cd  mov     rax, [rbp+rcx*8+0FD0h+var_1050]
0x1400fa4d2  bts     rax, rdx
0x1400fa4d6  mov     [rbp+rcx*8+0FD0h+var_1050], rax
0x1400fa4db  cmp     r8d, [r15+r9*8+0C808h]
0x1400fa4e3  jbe     short loc_1400FA4BD
0x1400fa4e5  mov     [rsp+10D0h+var_1060], 0
0x1400fa4ee  mov     ecx, [r15+r9*8+0C808h]
0x1400fa4f6  shr     ecx, 6
0x1400fa4f9  inc     ecx
0x1400fa4fb  cmp     ecx, 40h ; '@'
0x1400fa4fe  jz      short loc_1400FA512
0x1400fa500  mov     eax, 1
0x1400fa505  shl     rax, cl
0x1400fa508  dec     rax
0x1400fa50b  mov     [rsp+10D0h+var_1058], rax
0x1400fa510  jmp     short loc_1400FA51B
0x1400fa512  mov     [rsp+10D0h+var_1058], 0FFFFFFFFFFFFFFFFh
0x1400fa51b  mov     rcx, [rsi+288h]
0x1400fa522  mov     edx, 10001000h
0x1400fa527  mov     qword ptr [rsp+10D0h+var_1070], 0
0x1400fa530  mov     dword ptr [rsp+10D0h+var_1070], r9d
0x1400fa535  lea     r9, [rsp+10D0h+var_1060]
0x1400fa53a  mov     byte ptr [rsp+10D0h+var_1070+7], 1
0x1400fa53f  mov     r8, qword ptr [rsp+10D0h+var_1070]
0x1400fa544  mov     dword ptr [rsp+10D0h+var_10B0], ebx
0x1400fa548  call    cs:__imp_WinHvSetPartitionPropertyEx
0x1400fa54f  nop     dword ptr [rax+rax+00h]
0x1400fa554  mov     ecx, 80000000h
0x1400fa559  mov     ebx, eax
0x1400fa55b  add     eax, ecx
0x1400fa55d  test    ecx, eax
0x1400fa55f  jnz     short loc_1400FA587
0x1400fa561  cmp     ebx, 0C035001Eh
0x1400fa567  jz      short loc_1400FA587
0x1400fa569  mov     r8d, 35Ch
0x1400fa56f  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa576  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa57d  call    VidTraceErrorInternal0
0x1400fa582  jmp     loc_1400FA9D7
0x1400fa587  mov     edx, [rdi+8]
0x1400fa58a  mov     ecx, 0FFFFFFFFh
0x1400fa58f  mov     [rsp+10D0h+var_1080], 8000Ch
0x1400fa597  mov     rax, [r15+rdx*8+800h]
0x1400fa59f  cmp     rax, rcx
0x1400fa5a2  ja      loc_1400FA9B3
0x1400fa5a8  xor     r8b, r8b
0x1400fa5ab  mov     dword ptr [rbp+0FD0h+var_70], eax
0x1400fa5b1  test    r12b, r12b
0x1400fa5b4  jnz     loc_1400FA64F
0x1400fa5ba  mov     rcx, [rsi+288h]
0x1400fa5c1  lea     rax, [rsp+10D0h+var_1088]
0x1400fa5c6  mov     [rsp+10D0h+var_10A0], rax
0x1400fa5cb  mov     r9d, 1
0x1400fa5d1  lea     rax, [rbp+0FD0h+var_70]
0x1400fa5d8  mov     [rsp+10D0h+var_10A8], rax
0x1400fa5dd  lea     rax, [rsp+10D0h+var_1080]
0x1400fa5e2  mov     [rsp+10D0h+var_10B0], rax
0x1400fa5e7  call    cs:__imp_WinHvSetVpRegisters
0x1400fa5ee  nop     dword ptr [rax+rax+00h]
0x1400fa5f3  mov     ebx, eax
0x1400fa5f5  test    eax, eax
0x1400fa5f7  jns     short loc_1400FA617
0x1400fa5f9  mov     r8d, 3A7h
0x1400fa5ff  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa606  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa60d  call    VidTraceErrorInternal0
0x1400fa612  jmp     loc_1400FA9D7
0x1400fa617  lea     r14, [rsi+20h]
0x1400fa61b  lea     rcx, [rdi+740h]
0x1400fa622  call    VidMessageSlotSetup
0x1400fa627  mov     ebx, eax
0x1400fa629  test    eax, eax
0x1400fa62b  jns     loc_1400FA6CF
0x1400fa631  mov     r8d, 3D7h
0x1400fa637  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa63e  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa645  call    VidTraceErrorInternal0
0x1400fa64a  jmp     loc_1400FA9D7
0x1400fa64f  lea     r14, [rsi+20h]
0x1400fa653  mov     eax, [r14]
0x1400fa656  test    rax, 1E0h
0x1400fa65c  jnz     short loc_1400FA61B
0x1400fa65e  mov     rcx, [rsi+288h]
0x1400fa665  lea     rax, [rbp+0FD0h+var_50]
0x1400fa66c  mov     [rsp+10D0h+var_10A0], rax
0x1400fa671  mov     r9d, 1
0x1400fa677  lea     rax, [rsp+10D0h+var_1088]
0x1400fa67c  mov     [rsp+10D0h+var_10A8], rax
0x1400fa681  lea     rax, [rsp+10D0h+var_1080]
0x1400fa686  mov     [rsp+10D0h+var_10B0], rax
0x1400fa68b  call    cs:__imp_WinHvGetVpRegisters
0x1400fa692  nop     dword ptr [rax+rax+00h]
0x1400fa697  mov     ebx, eax
0x1400fa699  test    eax, eax
0x1400fa69b  js      short loc_1400FA6B1
0x1400fa69d  mov     rax, qword ptr [rbp+0FD0h+var_70]
0x1400fa6a4  cmp     qword ptr [rbp+0FD0h+var_50], rax
0x1400fa6ab  jz      loc_1400FA61B
0x1400fa6b1  mov     r8d, 3C6h
0x1400fa6b7  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa6be  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa6c5  call    VidTraceErrorInternal0
0x1400fa6ca  jmp     loc_1400FA9AD
0x1400fa6cf  mov     eax, [rdi+7D8h]
0x1400fa6d5  mov     r12d, 2
0x1400fa6db  or      eax, r12d
0x1400fa6de  mov     [rdi+7E0h], rsi
0x1400fa6e5  mov     [rdi+7D8h], eax
0x1400fa6eb  mov     edx, r12d
0x1400fa6ee  mov     eax, [rdi+8]
0x1400fa6f1  mov     rcx, rsi
0x1400fa6f4  mov     [rdi+7DCh], eax
0x1400fa6fa  call    VidMessagePoolRequiredCountInc
0x1400fa6ff  mov     ebx, eax
0x1400fa701  test    eax, eax
0x1400fa703  js      loc_1400FA9D7
0x1400fa709  or      [rdi+28h], r12d
0x1400fa70d  lea     rcx, [rsi+0DA0h]
0x1400fa714  call    VidThreadPoolThreadAdd
0x1400fa719  mov     ebx, eax
0x1400fa71b  test    eax, eax
0x1400fa71d  js      loc_1400FA9D7
0x1400fa723  or      dword ptr [rdi+28h], 1
0x1400fa727  test    byte ptr [rsi+10h], 4
0x1400fa72b  jz      short loc_1400FA73F
0x1400fa72d  mov     rcx, rdi
0x1400fa730  call    VidExtHypercallVpPagesAlloc
0x1400fa735  mov     ebx, eax
0x1400fa737  test    eax, eax
0x1400fa739  js      loc_1400FA9D7
0x1400fa73f  mov     eax, [r14]
0x1400fa742  mov     r15d, 1000h
0x1400fa748  test    rax, 1E0h
0x1400fa74e  jnz     loc_1400FA8A2
0x1400fa754  lea     r14, [rdi+898h]
0x1400fa75b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400fa75f  mov     qword ptr [r14], 0
0x1400fa766  call    cs:__imp_WinHvIsOverlayMapLocationRequired
0x1400fa76d  nop     dword ptr [rax+rax+00h]
0x1400fa772  test    al, al
0x1400fa774  jz      short loc_1400FA7B2
0x1400fa776  mov     r8, r14
0x1400fa779  lea     edx, [rbx+2]
0x1400fa77c  mov     rcx, rsi
0x1400fa77f  call    VidHvMemAllocatePagesForOverlay
0x1400fa784  test    eax, eax
0x1400fa786  jns     short loc_1400FA7AB
0x1400fa788  mov     r8d, 40Dh
0x1400fa78e  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa795  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa79c  call    VidTraceErrorInternal0
0x1400fa7a1  mov     ebx, 0C000009Ah
0x1400fa7a6  jmp     loc_1400FA9D7
0x1400fa7ab  mov     rax, [r14]
0x1400fa7ae  mov     rbx, [rax+30h]
0x1400fa7b2  mov     edx, [rdi+8]
0x1400fa7b5  lea     rax, [rsp+10D0h+var_1090]
0x1400fa7ba  mov     rcx, [rsi+288h]
0x1400fa7c1  mov     r9b, 0Fh
0x1400fa7c4  mov     [rsp+10D0h+var_10A8], rax
0x1400fa7c9  xor     r8d, r8d
0x1400fa7cc  mov     [rsp+10D0h+var_10B0], rbx
0x1400fa7d1  call    cs:__imp_WinHvMapVpStatePage2
0x1400fa7d8  nop     dword ptr [rax+rax+00h]
0x1400fa7dd  mov     ebx, eax
0x1400fa7df  test    eax, eax
0x1400fa7e1  jns     short loc_1400FA818
0x1400fa7e3  mov     rdx, [r14]
0x1400fa7e6  test    rdx, rdx
0x1400fa7e9  jz      short loc_1400FA7FA
0x1400fa7eb  mov     rcx, rsi
0x1400fa7ee  call    VidHvMemFreePagesForOverlay
0x1400fa7f3  mov     qword ptr [r14], 0
0x1400fa7fa  mov     r8d, 428h
0x1400fa800  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa807  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa80e  call    VidTraceErrorInternal0
0x1400fa813  jmp     loc_1400FA9D7
0x1400fa818  mov     rcx, [rsp+10D0h+var_1090]
0x1400fa81d  mov     r8d, 4
0x1400fa823  shl     rcx, 0Ch
0x1400fa827  mov     rdx, r15
0x1400fa82a  mov     byte ptr [rdi+8E8h], 1
0x1400fa831  call    cs:__imp_MmMapIoSpaceEx
0x1400fa838  nop     dword ptr [rax+rax+00h]
0x1400fa83d  mov     [rdi+890h], rax
0x1400fa844  test    rax, rax
0x1400fa847  jnz     short loc_1400FA867
0x1400fa849  mov     r8d, 431h
0x1400fa84f  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fa856  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fa85d  call    VidTraceErrorInternal0
0x1400fa862  jmp     loc_1400FA7A1
0x1400fa867  lea     rcx, [rdi+8A0h]
0x1400fa86e  mov     r8d, 1
0x1400fa874  lea     rdx, [rsp+10D0h+var_1090]
0x1400fa879  call    VidClientBufferPrepareFromOverlayPages
0x1400fa87e  mov     ebx, eax
  ... truncated ...
```
