# VidVppSetup

- ea: `0x1400fcb5c`
- end: `0x1400fd283`
- name: `VidVppSetup`
- size: `1831`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x14009a058`

## callees

- `0x140007a00`
- `0x140008990`
- `0x14001346c`
- `0x140013498`
- `0x140021c16`
- `0x140021c60`
- `0x140021e00`
- `0x1400386a0`
- `0x140075d20`
- `0x14009a58c`
- `0x14009a714`
- `0x14009b8b4`
- `0x1400f0158`
- `0x1400fb990`
- `0x1400fcb5c`

## import_xrefs

- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fd0a5`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fd1a9`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fd0a5`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400fd1a9`
- `winhvr!WinHvGetVpRegisters` at `0x1400fceff`
- `winhvr!WinHvGetVpRegisters` at `0x1400fceff`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fd045`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fd163`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fd045`
- `winhvr!WinHvMapVpStatePage2` at `0x1400fd163`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fcfda`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fd12b`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fcfda`
- `winhvr!WinHvIsOverlayMapLocationRequired` at `0x1400fd12b`
- `winhvr!WinHvCreateVp` at `0x1400fccab`
- `winhvr!WinHvCreateVp` at `0x1400fccab`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x1400fcdbc`
- `winhvr!WinHvSetPartitionPropertyEx` at `0x1400fcdbc`
- `winhvr!WinHvSetVpRegisters` at `0x1400fce5b`
- `winhvr!WinHvSetVpRegisters` at `0x1400fce5b`

## pseudocode

```c
__int64 __fastcall VidVppSetup(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  bool v5; // r14
  PKTHREAD v6; // rsi
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
  __int64 v22; // r14
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
  v6 = *(PKTHREAD *)a1;
  v7 = 0;
  v31 = 0;
  if ( *((_BYTE *)v6 + 8761) && *((_DWORD *)v6 + 2158) == 2 )
  {
    *(_DWORD *)(a1 + 40) |= 4u;
    v7 = 1;
  }
  if ( (*(_DWORD *)(a1 + 40) & 4) != 0 )
    goto LABEL_27;
  v8 = *(unsigned __int8 *)(a1 + 12);
  v34 = 0xFFFFFFFFFFFFFFFFuLL;
  v9 = *((unsigned __int8 *)v6 + v8 + 2105) | 0x80000000;
  if ( *((char *)v6 + 16) < 0 )
    v9 = *((unsigned __int8 *)v6 + v8 + 2105);
  if ( v5 )
    v10 = v34;
  else
    v10 = *(_OWORD *)(a1 + 16);
  v11 = *(unsigned int *)(a1 + 8);
  v12 = *((_QWORD *)v6 + 81);
  v34 = v10;
  VpRegisters = WinHvCreateVp(v12, v9, &v34, v11, 0);
  if ( VpRegisters >= 0 )
  {
    *(_DWORD *)(a1 + 40) |= 4u;
    if ( (*((_BYTE *)v6 + 696) & 4) != 0 && v5 && *(_BYTE *)(a2 + 51200) == 1 )
    {
      memset(v35, 0, 0xFE8u);
      v15 = *(unsigned int *)(a1 + 8);
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
        v18 = *((_QWORD *)v6 + 81);
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
    v19 = *(unsigned int *)(a1 + 8);
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
      v20 = (_DWORD *)((char *)v6 + 32);
      if ( (*((_DWORD *)v6 + 8) & 0x1E0LL) == 0 )
      {
        VpRegisters = WinHvGetVpRegisters(*((_QWORD *)v6 + 81), v19, v4, 1, v33, &v32, v37);
        if ( VpRegisters < 0 || *(_QWORD *)&v37[0] != *(_QWORD *)&v36[0] )
        {
          VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 966);
          goto LABEL_66;
        }
      }
    }
    else
    {
      VpRegisters = WinHvSetVpRegisters(*((_QWORD *)v6 + 81), v19, v4, 1, v33, v36, &v32);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 935);
        goto LABEL_69;
      }
      v20 = (_DWORD *)((char *)v6 + 32);
    }
    VpRegisters = VidMessageSlotSetup(a1 + 1856);
    if ( VpRegisters < 0 )
    {
      VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 983);
      goto LABEL_69;
    }
    v21 = *(_DWORD *)(a1 + 2008) | 2;
    *(_QWORD *)(a1 + 2016) = v6;
    *(_DWORD *)(a1 + 2008) = v21;
    *(_DWORD *)(a1 + 2012) = *(_DWORD *)(a1 + 8);
    VpRegisters = VidMessagePoolRequiredCountInc(v6, 2);
    if ( VpRegisters < 0 )
      goto LABEL_69;
    *(_DWORD *)(a1 + 40) |= 2u;
    VpRegisters = VidThreadPoolThreadAdd((char *)v6 + 3488);
    if ( VpRegisters < 0 )
      goto LABEL_69;
    *(_DWORD *)(a1 + 40) |= 1u;
    if ( (*((_BYTE *)v6 + 16) & 4) != 0 )
    {
      VpRegisters = VidExtHypercallVpPagesAlloc(a1);
      if ( VpRegisters < 0 )
        goto LABEL_69;
    }
    if ( (*v20 & 0x1E0LL) == 0 )
    {
      v22 = a1 + 2200;
      v23 = -1;
      *(_QWORD *)(a1 + 2200) = 0;
      if ( (unsigned __int8)WinHvIsOverlayMapLocationRequired() )
      {
        if ( (int)VidHvMemAllocatePagesForOverlay(v6, 1, a1 + 2200) < 0 )
        {
          VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1037);
LABEL_46:
          VpRegisters = -1073741670;
          goto LABEL_69;
        }
        v23 = *(_QWORD *)(*(_QWORD *)v22 + 48LL);
      }
      LOBYTE(v24) = 15;
      VpRegisters = WinHvMapVpStatePage2(*((_QWORD *)v6 + 81), *(unsigned int *)(a1 + 8), 0, v24, v23, &v31);
      if ( VpRegisters < 0 )
      {
        if ( *(_QWORD *)v22 )
        {
          VidHvMemFreePagesForOverlay(v6);
          *(_QWORD *)v22 = 0;
        }
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1064);
        goto LABEL_69;
      }
      v25 = v31 << 12;
      *(_BYTE *)(a1 + 2280) = 1;
      v26 = MmMapIoSpaceEx(v25, 4096, 4);
      *(_QWORD *)(a1 + 2192) = v26;
      if ( !v26 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1073);
        goto LABEL_46;
      }
      VpRegisters = VidClientBufferPrepareFromOverlayPages(a1 + 2208, &v31, 1);
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
      VpRegisters = WinHvMapVpStatePage2(*((_QWORD *)v6 + 81), *(unsigned int *)(a1 + 8), 1, v27, -1, &v31);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1109);
        goto LABEL_69;
      }
      v28 = v31 << 12;
      *(_BYTE *)(a1 + 2368) = 1;
      v29 = MmMapIoSpaceEx(v28, 4096, 2);
      *(_QWORD *)(a1 + 2288) = v29;
      if ( !v29 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1118);
        goto LABEL_46;
      }
      VpRegisters = VidClientBufferPrepareFromOverlayPages(a1 + 2296, &v31, 1);
      if ( VpRegisters < 0 )
      {
        VidTraceErrorInternal0("VidVppSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", 1130);
        goto LABEL_69;
      }
    }
    VpRegisters = VidVppInterceptThreadSetup((PKTHREAD *)a1);
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
0x1400fcb5c  mov     [rsp-8+arg_10], rbx
0x1400fcb61  mov     [rsp-8+arg_18], rsi
0x1400fcb66  push    rbp
0x1400fcb67  push    rdi
0x1400fcb68  push    r12
0x1400fcb6a  push    r14
0x1400fcb6c  push    r15
0x1400fcb6e  lea     rbp, [rsp-0FB0h]
0x1400fcb76  mov     eax, 10B0h
0x1400fcb7b  call    __chkstk_0
0x1400fcb80  sub     rsp, rax
0x1400fcb83  mov     rax, cs:__security_cookie
0x1400fcb8a  xor     rax, rsp
0x1400fcb8d  mov     [rbp+0FD0h+var_30], rax
0x1400fcb94  xorps   xmm0, xmm0
0x1400fcb97  mov     [rsp+10D0h+var_1090], 0
0x1400fcba0  mov     rdi, rcx
0x1400fcba3  mov     [rsp+10D0h+var_1088], 0
0x1400fcbac  xorps   xmm1, xmm1
0x1400fcbaf  lea     rcx, [rsp+10D0h+var_1070]
0x1400fcbb4  movups  [rbp+0FD0h+var_70], xmm0
0x1400fcbbb  mov     r15, rdx
0x1400fcbbe  movups  [rbp+0FD0h+var_60], xmm0
0x1400fcbc5  movups  [rbp+0FD0h+var_50], xmm1
0x1400fcbcc  movups  [rbp+0FD0h+var_40], xmm1
0x1400fcbd3  movups  [rsp+10D0h+var_1070], xmm0
0x1400fcbd8  call    HviGetHypervisorFeatures
0x1400fcbdd  mov     rax, 100000000h
0x1400fcbe7  test    qword ptr [rsp+10D0h+var_1070], rax
0x1400fcbec  jz      short loc_1400FCC16
0x1400fcbee  xorps   xmm0, xmm0
0x1400fcbf1  lea     rcx, [rsp+10D0h+var_1070]
0x1400fcbf6  movups  [rsp+10D0h+var_1070], xmm0
0x1400fcbfb  call    HviGetHypervisorFeatures
0x1400fcc00  mov     rax, 100000000000h
0x1400fcc0a  test    qword ptr [rsp+10D0h+var_1070], rax
0x1400fcc0f  jnz     short loc_1400FCC16
0x1400fcc11  mov     r14b, 1
0x1400fcc14  jmp     short loc_1400FCC19
0x1400fcc16  xor     r14b, r14b
0x1400fcc19  mov     rsi, [rdi]
0x1400fcc1c  xor     r12b, r12b
0x1400fcc1f  mov     [rsp+10D0h+var_1090], 0
0x1400fcc28  cmp     [rsi+2239h], r12b
0x1400fcc2f  jz      short loc_1400FCC41
0x1400fcc31  cmp     dword ptr [rsi+21B8h], 2
0x1400fcc38  jnz     short loc_1400FCC41
0x1400fcc3a  or      dword ptr [rdi+28h], 4
0x1400fcc3e  mov     r12b, 1
0x1400fcc41  mov     eax, [rdi+28h]
0x1400fcc44  test    al, 4
0x1400fcc46  jnz     loc_1400FCDFB
0x1400fcc4c  movzx   eax, byte ptr [rdi+0Ch]
0x1400fcc50  mov     r8d, 80000000h
0x1400fcc56  mov     qword ptr [rsp+10D0h+var_1070+8], 0
0x1400fcc5f  mov     qword ptr [rsp+10D0h+var_1070], 0FFFFFFFFFFFFFFFFh
0x1400fcc68  movzx   ecx, byte ptr [rax+rsi+839h]
0x1400fcc70  mov     edx, ecx
0x1400fcc72  or      edx, r8d
0x1400fcc75  test    byte ptr [rsi+10h], 80h
0x1400fcc79  cmovnz  edx, ecx
0x1400fcc7c  test    r14b, r14b
0x1400fcc7f  jnz     short loc_1400FCC87
0x1400fcc81  movups  xmm0, xmmword ptr [rdi+10h]
0x1400fcc85  jmp     short loc_1400FCC8C
0x1400fcc87  movaps  xmm0, [rsp+10D0h+var_1070]
0x1400fcc8c  mov     r9d, [rdi+8]
0x1400fcc90  lea     r8, [rsp+10D0h+var_1070]
0x1400fcc95  mov     rcx, [rsi+288h]
0x1400fcc9c  movdqa  [rsp+10D0h+var_1070], xmm0
0x1400fcca2  mov     [rsp+10D0h+var_10B0], 0
0x1400fccab  call    cs:__imp_WinHvCreateVp
0x1400fccb2  nop     dword ptr [rax+rax+00h]
0x1400fccb7  mov     ebx, eax
0x1400fccb9  test    eax, eax
0x1400fccbb  jns     short loc_1400FCCDB
0x1400fccbd  mov     r8d, 329h
0x1400fccc3  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fccca  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fccd1  call    VidTraceErrorInternal0
0x1400fccd6  jmp     loc_1400FD24B
0x1400fccdb  or      dword ptr [rdi+28h], 4
0x1400fccdf  test    byte ptr [rsi+2B8h], 4
0x1400fcce6  jz      loc_1400FCDFB
0x1400fccec  test    r14b, r14b
0x1400fccef  jz      loc_1400FCDFB
0x1400fccf5  cmp     byte ptr [r15+0C800h], 1
0x1400fccfd  jnz     loc_1400FCDFB
0x1400fcd03  mov     ebx, 0FE8h
0x1400fcd08  lea     rcx, [rsp+10D0h+var_1060]; void *
0x1400fcd0d  mov     r8d, ebx; Size
0x1400fcd10  xor     edx, edx; Val
0x1400fcd12  call    memset
0x1400fcd17  mov     r9d, [rdi+8]
0x1400fcd1b  mov     r8d, [r15+r9*8+0C804h]
0x1400fcd23  cmp     r8d, [r15+r9*8+0C808h]
0x1400fcd2b  ja      loc_1400FCDFB
0x1400fcd31  mov     edx, r8d
0x1400fcd34  mov     ecx, r8d
0x1400fcd37  and     edx, 3Fh
0x1400fcd3a  shr     rcx, 6
0x1400fcd3e  inc     r8d
0x1400fcd41  mov     rax, [rbp+rcx*8+0FD0h+var_1050]
0x1400fcd46  bts     rax, rdx
0x1400fcd4a  mov     [rbp+rcx*8+0FD0h+var_1050], rax
0x1400fcd4f  cmp     r8d, [r15+r9*8+0C808h]
0x1400fcd57  jbe     short loc_1400FCD31
0x1400fcd59  mov     [rsp+10D0h+var_1060], 0
0x1400fcd62  mov     ecx, [r15+r9*8+0C808h]
0x1400fcd6a  shr     ecx, 6
0x1400fcd6d  inc     ecx
0x1400fcd6f  cmp     ecx, 40h ; '@'
0x1400fcd72  jz      short loc_1400FCD86
0x1400fcd74  mov     eax, 1
0x1400fcd79  shl     rax, cl
0x1400fcd7c  dec     rax
0x1400fcd7f  mov     [rsp+10D0h+var_1058], rax
0x1400fcd84  jmp     short loc_1400FCD8F
0x1400fcd86  mov     [rsp+10D0h+var_1058], 0FFFFFFFFFFFFFFFFh
0x1400fcd8f  mov     rcx, [rsi+288h]
0x1400fcd96  mov     edx, 10001000h
0x1400fcd9b  mov     qword ptr [rsp+10D0h+var_1070], 0
0x1400fcda4  mov     dword ptr [rsp+10D0h+var_1070], r9d
0x1400fcda9  lea     r9, [rsp+10D0h+var_1060]
0x1400fcdae  mov     byte ptr [rsp+10D0h+var_1070+7], 1
0x1400fcdb3  mov     r8, qword ptr [rsp+10D0h+var_1070]
0x1400fcdb8  mov     dword ptr [rsp+10D0h+var_10B0], ebx
0x1400fcdbc  call    cs:__imp_WinHvSetPartitionPropertyEx
0x1400fcdc3  nop     dword ptr [rax+rax+00h]
0x1400fcdc8  mov     ecx, 80000000h
0x1400fcdcd  mov     ebx, eax
0x1400fcdcf  add     eax, ecx
0x1400fcdd1  test    ecx, eax
0x1400fcdd3  jnz     short loc_1400FCDFB
0x1400fcdd5  cmp     ebx, 0C035001Eh
0x1400fcddb  jz      short loc_1400FCDFB
0x1400fcddd  mov     r8d, 35Ch
0x1400fcde3  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fcdea  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fcdf1  call    VidTraceErrorInternal0
0x1400fcdf6  jmp     loc_1400FD24B
0x1400fcdfb  mov     edx, [rdi+8]
0x1400fcdfe  mov     ecx, 0FFFFFFFFh
0x1400fce03  mov     [rsp+10D0h+var_1080], 8000Ch
0x1400fce0b  mov     rax, [r15+rdx*8+800h]
0x1400fce13  cmp     rax, rcx
0x1400fce16  ja      loc_1400FD227
0x1400fce1c  xor     r8b, r8b
0x1400fce1f  mov     dword ptr [rbp+0FD0h+var_70], eax
0x1400fce25  test    r12b, r12b
0x1400fce28  jnz     loc_1400FCEC3
0x1400fce2e  mov     rcx, [rsi+288h]
0x1400fce35  lea     rax, [rsp+10D0h+var_1088]
0x1400fce3a  mov     [rsp+10D0h+var_10A0], rax
0x1400fce3f  mov     r9d, 1
0x1400fce45  lea     rax, [rbp+0FD0h+var_70]
0x1400fce4c  mov     [rsp+10D0h+var_10A8], rax
0x1400fce51  lea     rax, [rsp+10D0h+var_1080]
0x1400fce56  mov     [rsp+10D0h+var_10B0], rax
0x1400fce5b  call    cs:__imp_WinHvSetVpRegisters
0x1400fce62  nop     dword ptr [rax+rax+00h]
0x1400fce67  mov     ebx, eax
0x1400fce69  test    eax, eax
0x1400fce6b  jns     short loc_1400FCE8B
0x1400fce6d  mov     r8d, 3A7h
0x1400fce73  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fce7a  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fce81  call    VidTraceErrorInternal0
0x1400fce86  jmp     loc_1400FD24B
0x1400fce8b  lea     r14, [rsi+20h]
0x1400fce8f  lea     rcx, [rdi+740h]
0x1400fce96  call    VidMessageSlotSetup
0x1400fce9b  mov     ebx, eax
0x1400fce9d  test    eax, eax
0x1400fce9f  jns     loc_1400FCF43
0x1400fcea5  mov     r8d, 3D7h
0x1400fceab  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fceb2  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fceb9  call    VidTraceErrorInternal0
0x1400fcebe  jmp     loc_1400FD24B
0x1400fcec3  lea     r14, [rsi+20h]
0x1400fcec7  mov     eax, [r14]
0x1400fceca  test    rax, 1E0h
0x1400fced0  jnz     short loc_1400FCE8F
0x1400fced2  mov     rcx, [rsi+288h]
0x1400fced9  lea     rax, [rbp+0FD0h+var_50]
0x1400fcee0  mov     [rsp+10D0h+var_10A0], rax
0x1400fcee5  mov     r9d, 1
0x1400fceeb  lea     rax, [rsp+10D0h+var_1088]
0x1400fcef0  mov     [rsp+10D0h+var_10A8], rax
0x1400fcef5  lea     rax, [rsp+10D0h+var_1080]
0x1400fcefa  mov     [rsp+10D0h+var_10B0], rax
0x1400fceff  call    cs:__imp_WinHvGetVpRegisters
0x1400fcf06  nop     dword ptr [rax+rax+00h]
0x1400fcf0b  mov     ebx, eax
0x1400fcf0d  test    eax, eax
0x1400fcf0f  js      short loc_1400FCF25
0x1400fcf11  mov     rax, qword ptr [rbp+0FD0h+var_70]
0x1400fcf18  cmp     qword ptr [rbp+0FD0h+var_50], rax
0x1400fcf1f  jz      loc_1400FCE8F
0x1400fcf25  mov     r8d, 3C6h
0x1400fcf2b  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fcf32  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fcf39  call    VidTraceErrorInternal0
0x1400fcf3e  jmp     loc_1400FD221
0x1400fcf43  mov     eax, [rdi+7D8h]
0x1400fcf49  mov     r12d, 2
0x1400fcf4f  or      eax, r12d
0x1400fcf52  mov     [rdi+7E0h], rsi
0x1400fcf59  mov     [rdi+7D8h], eax
0x1400fcf5f  mov     edx, r12d
0x1400fcf62  mov     eax, [rdi+8]
0x1400fcf65  mov     rcx, rsi
0x1400fcf68  mov     [rdi+7DCh], eax
0x1400fcf6e  call    VidMessagePoolRequiredCountInc
0x1400fcf73  mov     ebx, eax
0x1400fcf75  test    eax, eax
0x1400fcf77  js      loc_1400FD24B
0x1400fcf7d  or      [rdi+28h], r12d
0x1400fcf81  lea     rcx, [rsi+0DA0h]
0x1400fcf88  call    VidThreadPoolThreadAdd
0x1400fcf8d  mov     ebx, eax
0x1400fcf8f  test    eax, eax
0x1400fcf91  js      loc_1400FD24B
0x1400fcf97  or      dword ptr [rdi+28h], 1
0x1400fcf9b  test    byte ptr [rsi+10h], 4
0x1400fcf9f  jz      short loc_1400FCFB3
0x1400fcfa1  mov     rcx, rdi
0x1400fcfa4  call    VidExtHypercallVpPagesAlloc
0x1400fcfa9  mov     ebx, eax
0x1400fcfab  test    eax, eax
0x1400fcfad  js      loc_1400FD24B
0x1400fcfb3  mov     eax, [r14]
0x1400fcfb6  mov     r15d, 1000h
0x1400fcfbc  test    rax, 1E0h
0x1400fcfc2  jnz     loc_1400FD116
0x1400fcfc8  lea     r14, [rdi+898h]
0x1400fcfcf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400fcfd3  mov     qword ptr [r14], 0
0x1400fcfda  call    cs:__imp_WinHvIsOverlayMapLocationRequired
0x1400fcfe1  nop     dword ptr [rax+rax+00h]
0x1400fcfe6  test    al, al
0x1400fcfe8  jz      short loc_1400FD026
0x1400fcfea  mov     r8, r14
0x1400fcfed  lea     edx, [rbx+2]
0x1400fcff0  mov     rcx, rsi
0x1400fcff3  call    VidHvMemAllocatePagesForOverlay
0x1400fcff8  test    eax, eax
0x1400fcffa  jns     short loc_1400FD01F
0x1400fcffc  mov     r8d, 40Dh
0x1400fd002  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fd009  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fd010  call    VidTraceErrorInternal0
0x1400fd015  mov     ebx, 0C000009Ah
0x1400fd01a  jmp     loc_1400FD24B
0x1400fd01f  mov     rax, [r14]
0x1400fd022  mov     rbx, [rax+30h]
0x1400fd026  mov     edx, [rdi+8]
0x1400fd029  lea     rax, [rsp+10D0h+var_1090]
0x1400fd02e  mov     rcx, [rsi+288h]
0x1400fd035  mov     r9b, 0Fh
0x1400fd038  mov     [rsp+10D0h+var_10A8], rax
0x1400fd03d  xor     r8d, r8d
0x1400fd040  mov     [rsp+10D0h+var_10B0], rbx
0x1400fd045  call    cs:__imp_WinHvMapVpStatePage2
0x1400fd04c  nop     dword ptr [rax+rax+00h]
0x1400fd051  mov     ebx, eax
0x1400fd053  test    eax, eax
0x1400fd055  jns     short loc_1400FD08C
0x1400fd057  mov     rdx, [r14]
0x1400fd05a  test    rdx, rdx
0x1400fd05d  jz      short loc_1400FD06E
0x1400fd05f  mov     rcx, rsi
0x1400fd062  call    VidHvMemFreePagesForOverlay
0x1400fd067  mov     qword ptr [r14], 0
0x1400fd06e  mov     r8d, 428h
0x1400fd074  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fd07b  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fd082  call    VidTraceErrorInternal0
0x1400fd087  jmp     loc_1400FD24B
0x1400fd08c  mov     rcx, [rsp+10D0h+var_1090]
0x1400fd091  mov     r8d, 4
0x1400fd097  shl     rcx, 0Ch
0x1400fd09b  mov     rdx, r15
0x1400fd09e  mov     byte ptr [rdi+8E8h], 1
0x1400fd0a5  call    cs:__imp_MmMapIoSpaceEx
0x1400fd0ac  nop     dword ptr [rax+rax+00h]
0x1400fd0b1  mov     [rdi+890h], rax
0x1400fd0b8  test    rax, rax
0x1400fd0bb  jnz     short loc_1400FD0DB
0x1400fd0bd  mov     r8d, 431h
0x1400fd0c3  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x1400fd0ca  lea     rcx, aVidvppsetup; "VidVppSetup"
0x1400fd0d1  call    VidTraceErrorInternal0
0x1400fd0d6  jmp     loc_1400FD015
0x1400fd0db  lea     rcx, [rdi+8A0h]
0x1400fd0e2  mov     r8d, 1
0x1400fd0e8  lea     rdx, [rsp+10D0h+var_1090]
0x1400fd0ed  call    VidClientBufferPrepareFromOverlayPages
0x1400fd0f2  mov     ebx, eax
  ... truncated ...
```
