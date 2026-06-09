# VsmmPhuIoctlCommit

- ea: `0x14009f2cc`
- end: `0x14009fb06`
- name: `VsmmPhuIoctlCommit`
- size: `2106`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140006ff4`
- `0x140007094`
- `0x14000a4e0`
- `0x140021650`
- `0x140024754`
- `0x140024c78`
- `0x1400307d0`
- `0x140033900`
- `0x140034554`
- `0x140034914`
- `0x14009f2cc`
- `0x1400b26a4`
- `0x1400f69c0`

## import_xrefs

- `winhvr!WinHvPersistPartitionReservedPages` at `0x14009f8fe`
- `winhvr!WinHvPersistPartitionReservedPages` at `0x14009f8fe`

## string_xrefs

- `0x14009f3c4`: `VsmmPhuIoctlCommit`
- `0x14009f542`: `VsmmPhuIoctlCommit`
- `0x14009f6cc`: `VsmmPhuIoctlCommit`
- `0x14009f7b3`: `VsmmPhuIoctlCommit`
- `0x14009f7f0`: `VsmmPhuIoctlCommit`
- `0x14009f976`: `VsmmPhuIoctlCommit`
- `0x14009fa22`: `VsmmPhuIoctlCommit`

## pseudocode

```c
__int64 __fastcall VsmmPhuIoctlCommit(__int64 a1, __int64 a2, __int64 a3)
{
  char *v4; // r15
  __int64 v5; // r12
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r15
  int v9; // edi
  char v10; // di
  bool v11; // r12
  __int64 v12; // rax
  __int16 *v13; // rdx
  __int64 v14; // r11
  __int64 Next; // rax
  __int64 i; // rax
  __int64 v18; // r11
  int v19; // eax
  int v20; // r8d
  int v21; // [rsp+20h] [rbp-E0h]
  _BYTE v22[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  char *v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  __int64 v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  __int64 v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+118h] [rbp+18h] BYREF
  int v45; // [rsp+11Ch] [rbp+1Ch]
  __int64 *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  __int64 *v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  __int64 *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  __int64 *v52; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h]
  __int64 *v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+168h] [rbp+68h]
  _BYTE *v56; // [rsp+170h] [rbp+70h]
  __int64 v57; // [rsp+178h] [rbp+78h]

  v4 = (char *)VidDeviceExtension + 1640;
  v25 = (char *)VidDeviceExtension + 1640;
  VidLockAcquireShared((char *)VidDeviceExtension + 1640, a2, a3);
  v5 = a1 + 3736;
  v26 = a1 + 3736;
  VidObjectLockAcquireExclusive(a1 + 3736);
  if ( (BYTE1(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink) & 4) != 0 )
    McTemplateK0j_EtwWriteTransfer(v6, VID_PARTITION_PERSIST_START, v7, a1 + 656);
  if ( *(_DWORD *)(a1 + 8632) != 1 || *(_BYTE *)(a1 + 8656) )
  {
    v7 = 3221266435LL;
    v9 = -1073700861;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v33, "VsmmPhuIoctlCommit");
      tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
      v23 = v20;
      v35 = &v24;
      LODWORD(v24) = 560;
      v37 = (__int64 *)&v23;
      v36 = 4;
      v41 = &v44;
      v43 = *(_QWORD *)(a1 + 128);
      v44 = *(unsigned __int16 *)(a1 + 120);
      v29 = *(_QWORD *)(a1 + 648);
      v46 = &v29;
      v22[0] = *(_BYTE *)(a1 + 8656);
      v48 = (__int64 *)v22;
      v38 = 4;
      v39 = a1 + 656;
      v40 = 16;
      v42 = 2;
      v45 = 0;
      v47 = 8;
      v49 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_14004B1DF, 0, 0, 11, v32);
    }
  }
  else
  {
    v8 = *(_QWORD *)(a1 + 8648);
    if ( *(_DWORD *)(a1 + 8636) != 2 || *(_QWORD *)(v8 + 1304) == *(_QWORD *)(v8 + 1296) )
    {
      v10 = 0;
      v24 = -1;
      v11 = 0;
      while ( 1 )
      {
        Next = VidHandleTableGetNext(a1 + 3232, &v24);
        if ( !Next )
          break;
        if ( (*(_DWORD *)(Next + 20) & 0x800) != 0 )
        {
          v12 = *(_QWORD *)(Next + 640);
          if ( v10 )
          {
            v6 = v12 != 0;
            if ( v11 != (_DWORD)v6 )
            {
              v9 = -1070137276;
              if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
              {
                tlgCreate1Sz_char(v33, "VsmmPhuIoctlCommit");
                tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
                LODWORD(v24) = 627;
                v35 = &v24;
                v13 = &word_14004B256;
                v36 = 4;
                v37 = (__int64 *)&v23;
                v41 = &v44;
                v43 = *(_QWORD *)(a1 + 128);
                v44 = *(unsigned __int16 *)(a1 + 120);
                v28 = *(_QWORD *)(a1 + 648);
                v46 = &v28;
                v27 = *(_QWORD *)(v14 + 24);
                v48 = &v27;
                v30 = *(_QWORD *)(v14 + 40);
                v50 = &v30;
                v31[0] = *(_QWORD *)(v14 + 48);
                v52 = v31;
                v29 = *(int *)(v14 + 20);
                v54 = &v29;
                v56 = v22;
                v21 = 15;
                v23 = -1070137276;
                v38 = 4;
                v39 = a1 + 656;
                v40 = 16;
                v42 = 2;
                v22[0] = v11;
                v57 = 1;
LABEL_17:
                v47 = 8;
                v45 = 0;
                v55 = 8;
                v53 = 8;
                v51 = 8;
                v49 = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v13, 0, 0, v21, v32);
              }
              goto LABEL_18;
            }
          }
          else
          {
            v10 = 1;
            v11 = v12 != 0;
          }
        }
      }
      v24 = -1;
      for ( i = VidHandleTableGetNext(a1 + 3264, &v24); ; i = VidHandleTableGetNext(a1 + 3264, &v24) )
      {
        if ( !i )
        {
          if ( *(_DWORD *)(a1 + 8660) == 1 )
          {
            v9 = -1073700861;
            VidTracePartitionErrorInternal0(
              (unsigned int)"VsmmPhuIoctlCommit",
              (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
              678,
              a1 + 656,
              a1 + 120,
              *(_QWORD *)(a1 + 648),
              -1073700861);
          }
          else if ( *(_DWORD *)(a1 + 8660) == 3
                 && (v19 = WinHvPersistPartitionReservedPages(*(_QWORD *)(a1 + 648)), v9 = v19, v19 < 0) )
          {
            VidTracePartitionErrorInternal0(
              (unsigned int)"VsmmPhuIoctlCommit",
              (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
              691,
              a1 + 656,
              a1 + 120,
              *(_QWORD *)(a1 + 648),
              v19);
          }
          else
          {
            if ( *(_DWORD *)(a1 + 8636) == 2 )
              VsmmPhuStoreItemReadyModifyAll(v8);
            *(_DWORD *)(a1 + 8632) = 2;
            *(_DWORD *)(a1 + 8640) = 0;
            if ( (unsigned int)dword_140064110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            {
              tlgCreate1Sz_char(v33, "VsmmPhuIoctlCommit");
              tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
              LODWORD(v24) = 718;
              v35 = &v24;
              v36 = 4;
              v37 = (__int64 *)(a1 + 656);
              v38 = 16;
              tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14004B10E, 0, 0, 6, v32);
            }
            v9 = 0;
          }
          goto LABEL_18;
        }
        if ( *(_QWORD *)(i + 296) )
        {
          v6 = *(_QWORD *)(i + 384);
          if ( !*(_QWORD *)(v6 + 640) )
            break;
        }
      }
      v9 = -1070137282;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v33, "VsmmPhuIoctlCommit");
        tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
        LODWORD(v24) = 665;
        v35 = &v24;
        v13 = (__int16 *)qword_14004B070;
        v36 = 4;
        v37 = (__int64 *)&v23;
        v41 = &v44;
        v43 = *(_QWORD *)(a1 + 128);
        v44 = *(unsigned __int16 *)(a1 + 120);
        v29 = *(_QWORD *)(a1 + 648);
        v46 = &v29;
        v31[0] = *(_QWORD *)(v18 + 248);
        v48 = v31;
        v30 = *(_QWORD *)(v18 + 256);
        v50 = &v30;
        v28 = *(_QWORD *)(v18 + 264);
        v52 = &v28;
        v27 = *(int *)(v18 + 292);
        v54 = &v27;
        v21 = 14;
        v23 = -1070137282;
        v38 = 4;
        v39 = a1 + 656;
        v40 = 16;
        v42 = 2;
        goto LABEL_17;
      }
LABEL_18:
      v5 = v26;
    }
    else
    {
      v9 = -1070137273;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v33, "VsmmPhuIoctlCommit");
        tlgCreate1Sz_char(v34, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c");
        v23 = 594;
        v35 = (__int64 *)&v23;
        v36 = 4;
        v37 = &v24;
        LODWORD(v24) = -1070137273;
        v41 = &v44;
        v43 = *(_QWORD *)(a1 + 128);
        v44 = *(unsigned __int16 *)(a1 + 120);
        v26 = *(_QWORD *)(a1 + 648);
        v46 = &v26;
        v27 = *(_QWORD *)(v8 + 1304);
        v48 = &v27;
        v28 = *(_QWORD *)(v8 + 1296);
        v50 = &v28;
        v38 = 4;
        v39 = a1 + 656;
        v40 = 16;
        v42 = 2;
        v45 = 0;
        v47 = 8;
        v49 = 8;
        v51 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004B151, 0, 0, 12, v32);
      }
    }
    v4 = v25;
  }
  if ( (BYTE1(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink) & 4) != 0 )
    McTemplateK0x_EtwWriteTransfer(v6, VID_PARTITION_PERSIST_STOP, v7, v9);
  VidObjectLockRelease(v5);
  VidLockRelease(v4);
  if ( v9 < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VsmmPhuIoctlCommit",
      (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c",
      733,
      v9,
      a1 + 656);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14009f2cc  push    rbp
0x14009f2ce  push    rbx
0x14009f2cf  push    rsi
0x14009f2d0  push    rdi
0x14009f2d1  push    r12
0x14009f2d3  push    r13
0x14009f2d5  push    r14
0x14009f2d7  push    r15
0x14009f2d9  lea     rbp, [rsp-98h]
0x14009f2e1  sub     rsp, 198h
0x14009f2e8  mov     rax, cs:__security_cookie
0x14009f2ef  xor     rax, rsp
0x14009f2f2  mov     [rbp+0D0h+var_50], rax
0x14009f2f9  mov     r15, cs:VidDeviceExtension
0x14009f300  mov     rbx, rcx
0x14009f303  add     r15, 668h
0x14009f30a  mov     rcx, r15
0x14009f30d  mov     [rsp+1D0h+var_180], r15
0x14009f312  call    VidLockAcquireShared
0x14009f317  lea     r12, [rbx+0E98h]
0x14009f31e  mov     rcx, r12
0x14009f321  mov     [rsp+1D0h+var_178], r12
0x14009f326  call    VidObjectLockAcquireExclusive
0x14009f32b  mov     r9d, 4
0x14009f331  lea     r14, [rbx+290h]
0x14009f338  test    byte ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink+1, r9b
0x14009f33f  jz      short loc_14009F350
0x14009f341  mov     r9, r14
0x14009f344  lea     rdx, VID_PARTITION_PERSIST_START
0x14009f34b  call    McTemplateK0j_EtwWriteTransfer
0x14009f350  xor     r13d, r13d
0x14009f353  cmp     dword ptr [rbx+21B8h], 1
0x14009f35a  jnz     loc_14009F9ED
0x14009f360  cmp     [rbx+21D0h], r13b
0x14009f367  jnz     loc_14009F9ED
0x14009f36d  mov     r15, [rbx+21C8h]
0x14009f374  lea     esi, [r13+2]
0x14009f378  cmp     [rbx+21BCh], esi
0x14009f37e  jnz     loc_14009F4C6
0x14009f384  mov     rax, [r15+510h]
0x14009f38b  cmp     [r15+518h], rax
0x14009f392  jz      loc_14009F4C6
0x14009f398  mov     eax, cs:dword_140064110
0x14009f39e  mov     edi, 0C0370047h
0x14009f3a3  cmp     eax, esi
0x14009f3a5  jbe     loc_14009F686
0x14009f3ab  mov     edx, 100h
0x14009f3b0  lea     rcx, dword_140064110
0x14009f3b7  call    _tlgKeywordOn
0x14009f3bc  test    al, al
0x14009f3be  jz      loc_14009F686
0x14009f3c4  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x14009f3cb  lea     rcx, [rbp+0D0h+var_120]
0x14009f3cf  call    _tlgCreate1Sz_char
0x14009f3d4  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x14009f3db  lea     rcx, [rbp+0D0h+var_110]
0x14009f3df  call    _tlgCreate1Sz_char
0x14009f3e4  lea     rax, [rsp+1D0h+var_18C]
0x14009f3e9  mov     [rsp+1D0h+var_18C], 252h
0x14009f3f1  mov     [rbp+0D0h+var_100], rax
0x14009f3f5  lea     rdx, byte_14004B151
0x14009f3fc  lea     rax, [rsp+1D0h+var_188]
0x14009f401  mov     [rbp+0D0h+var_F8], 4
0x14009f409  mov     [rbp+0D0h+var_F0], rax
0x14009f40d  lea     rcx, dword_140064110
0x14009f414  lea     rax, [rbp+0D0h+var_B8]
0x14009f418  mov     dword ptr [rsp+1D0h+var_188], edi
0x14009f41c  mov     [rbp+0D0h+var_D0], rax
0x14009f420  xor     r9d, r9d
0x14009f423  mov     rax, [rbx+80h]
0x14009f42a  xor     r8d, r8d
0x14009f42d  mov     [rbp+0D0h+var_C0], rax
0x14009f431  movzx   eax, word ptr [rbx+78h]
0x14009f435  mov     [rbp+0D0h+var_B8], eax
0x14009f438  mov     rax, [rbx+288h]
0x14009f43f  mov     [rsp+1D0h+var_178], rax
0x14009f444  lea     rax, [rsp+1D0h+var_178]
0x14009f449  mov     [rbp+0D0h+var_B0], rax
0x14009f44d  mov     rax, [r15+518h]
0x14009f454  mov     [rsp+1D0h+var_170], rax
0x14009f459  lea     rax, [rsp+1D0h+var_170]
0x14009f45e  mov     [rbp+0D0h+var_A0], rax
0x14009f462  mov     rax, [r15+510h]
0x14009f469  mov     [rsp+1D0h+var_168], rax
0x14009f46e  lea     rax, [rsp+1D0h+var_168]
0x14009f473  mov     [rbp+0D0h+var_90], rax
0x14009f477  lea     rax, [rbp+0D0h+var_140]
0x14009f47b  mov     [rsp+1D0h+var_1A8], rax
0x14009f480  mov     dword ptr [rsp+1D0h+var_1B0], 0Ch
0x14009f488  mov     [rbp+0D0h+var_E8], 4
0x14009f490  mov     [rbp+0D0h+var_E0], r14
0x14009f494  mov     [rbp+0D0h+var_D8], 10h
0x14009f49c  mov     [rbp+0D0h+var_C8], rsi
0x14009f4a0  mov     [rbp+0D0h+var_B4], r13d
0x14009f4a4  mov     [rbp+0D0h+var_A8], 8
0x14009f4ac  mov     [rbp+0D0h+var_98], 8
0x14009f4b4  mov     [rbp+0D0h+var_88], 8
0x14009f4bc  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009f4c1  jmp     loc_14009F686
0x14009f4c6  mov     dil, r13b
0x14009f4c9  mov     [rsp+1D0h+var_188], 0FFFFFFFFFFFFFFFFh
0x14009f4d2  mov     r12b, r13b
0x14009f4d5  lea     r13, [rbx+0CA0h]
0x14009f4dc  jmp     loc_14009F708
0x14009f4e1  test    dword ptr [r11+14h], 800h
0x14009f4e9  jz      loc_14009F708
0x14009f4ef  mov     rax, [r11+280h]
0x14009f4f6  test    dil, dil
0x14009f4f9  jz      loc_14009F6FE
0x14009f4ff  xor     ecx, ecx
0x14009f501  test    rax, rax
0x14009f504  movzx   eax, r12b
0x14009f508  setnz   cl
0x14009f50b  cmp     eax, ecx
0x14009f50d  jz      loc_14009F708
0x14009f513  mov     eax, cs:dword_140064110
0x14009f519  mov     edi, 0C0370044h
0x14009f51e  cmp     eax, esi
0x14009f520  jbe     loc_14009F681
0x14009f526  mov     edx, 100h
0x14009f52b  lea     rcx, dword_140064110
0x14009f532  call    _tlgKeywordOn
0x14009f537  xor     r13d, r13d
0x14009f53a  test    al, al
0x14009f53c  jz      loc_14009F681
0x14009f542  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x14009f549  lea     rcx, [rbp+0D0h+var_120]
0x14009f54d  call    _tlgCreate1Sz_char
0x14009f552  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x14009f559  lea     rcx, [rbp+0D0h+var_110]
0x14009f55d  call    _tlgCreate1Sz_char
0x14009f562  lea     rax, [rsp+1D0h+var_188]
0x14009f567  mov     dword ptr [rsp+1D0h+var_188], 273h
0x14009f56f  mov     [rbp+0D0h+var_100], rax
0x14009f573  lea     rdx, word_14004B256
0x14009f57a  lea     rax, [rsp+1D0h+var_18C]
0x14009f57f  mov     [rbp+0D0h+var_F8], 4
0x14009f587  mov     [rbp+0D0h+var_F0], rax
0x14009f58b  lea     rax, [rbp+0D0h+var_B8]
0x14009f58f  mov     [rbp+0D0h+var_D0], rax
0x14009f593  mov     rax, [rbx+80h]
0x14009f59a  mov     [rbp+0D0h+var_C0], rax
0x14009f59e  movzx   eax, word ptr [rbx+78h]
0x14009f5a2  mov     [rbp+0D0h+var_B8], eax
0x14009f5a5  mov     rax, [rbx+288h]
0x14009f5ac  mov     [rsp+1D0h+var_168], rax
0x14009f5b1  lea     rax, [rsp+1D0h+var_168]
0x14009f5b6  mov     [rbp+0D0h+var_B0], rax
0x14009f5ba  mov     rax, [r11+18h]
0x14009f5be  mov     [rsp+1D0h+var_170], rax
0x14009f5c3  lea     rax, [rsp+1D0h+var_170]
0x14009f5c8  mov     [rbp+0D0h+var_A0], rax
0x14009f5cc  mov     rax, [r11+28h]
0x14009f5d0  mov     [rsp+1D0h+var_158], rax
0x14009f5d5  lea     rax, [rsp+1D0h+var_158]
0x14009f5da  mov     [rbp+0D0h+var_90], rax
0x14009f5de  mov     rax, [r11+30h]
0x14009f5e2  mov     [rbp+0D0h+var_150], rax
0x14009f5e6  lea     rax, [rbp+0D0h+var_150]
0x14009f5ea  mov     [rbp+0D0h+var_80], rax
0x14009f5ee  movsxd  rax, dword ptr [r11+14h]
0x14009f5f2  mov     [rsp+1D0h+var_160], rax
0x14009f5f7  lea     rax, [rsp+1D0h+var_160]
0x14009f5fc  mov     [rbp+0D0h+var_70], rax
0x14009f600  lea     rax, [rsp+1D0h+var_190]
0x14009f605  mov     [rbp+0D0h+var_60], rax
0x14009f609  lea     rax, [rbp+0D0h+var_140]
0x14009f60d  mov     [rsp+1D0h+var_1A8], rax
0x14009f612  mov     dword ptr [rsp+1D0h+var_1B0], 0Fh
0x14009f61a  mov     [rsp+1D0h+var_18C], edi
0x14009f61e  mov     [rbp+0D0h+var_E8], 4
0x14009f626  mov     [rbp+0D0h+var_E0], r14
0x14009f62a  mov     [rbp+0D0h+var_D8], 10h
0x14009f632  mov     [rbp+0D0h+var_C8], rsi
0x14009f636  mov     [rsp+1D0h+var_190], r12b
0x14009f63b  mov     [rbp+0D0h+var_58], 1
0x14009f643  xor     r9d, r9d
0x14009f646  mov     [rbp+0D0h+var_A8], 8
0x14009f64e  xor     r8d, r8d
0x14009f651  mov     [rbp+0D0h+var_B4], r13d
0x14009f655  lea     rcx, dword_140064110
0x14009f65c  mov     [rbp+0D0h+var_68], 8
0x14009f664  mov     [rbp+0D0h+var_78], 8
0x14009f66c  mov     [rbp+0D0h+var_88], 8
0x14009f674  mov     [rbp+0D0h+var_98], 8
0x14009f67c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009f681  mov     r12, [rsp+1D0h+var_178]
0x14009f686  mov     r15, [rsp+1D0h+var_180]
0x14009f68b  test    byte ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink+1, 4
0x14009f692  jz      short loc_14009F6A3
0x14009f694  movsxd  r9, edi
0x14009f697  lea     rdx, VID_PARTITION_PERSIST_STOP
0x14009f69e  call    McTemplateK0x_EtwWriteTransfer
0x14009f6a3  mov     rcx, r12
0x14009f6a6  call    VidObjectLockRelease
0x14009f6ab  mov     rcx, r15
0x14009f6ae  call    VidLockRelease
0x14009f6b3  test    edi, edi
0x14009f6b5  jns     short loc_14009F6D8
0x14009f6b7  mov     r9d, edi
0x14009f6ba  mov     [rsp+1D0h+var_1B0], r14
0x14009f6bf  mov     r8d, 2DDh
0x14009f6c5  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x14009f6cc  lea     rcx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x14009f6d3  call    VidTraceErrorStatusPartitionInternal0
0x14009f6d8  mov     eax, edi
0x14009f6da  mov     rcx, [rbp+0D0h+var_50]
0x14009f6e1  xor     rcx, rsp; StackCookie
0x14009f6e4  call    __security_check_cookie
0x14009f6e9  add     rsp, 198h
0x14009f6f0  pop     r15
0x14009f6f2  pop     r14
0x14009f6f4  pop     r13
0x14009f6f6  pop     r12
0x14009f6f8  pop     rdi
0x14009f6f9  pop     rsi
0x14009f6fa  pop     rbx
0x14009f6fb  pop     rbp
0x14009f6fc  retn
0x14009f6fe  test    rax, rax
0x14009f701  mov     dil, 1
0x14009f704  setnz   r12b
0x14009f708  lea     rdx, [rsp+1D0h+var_188]
0x14009f70d  mov     rcx, r13
0x14009f710  call    VidHandleTableGetNext
0x14009f715  mov     r11, rax
0x14009f718  test    rax, rax
0x14009f71b  jnz     loc_14009F4E1
0x14009f721  lea     rdi, [rbx+0CC0h]
0x14009f728  mov     [rsp+1D0h+var_188], 0FFFFFFFFFFFFFFFFh
0x14009f731  mov     rcx, rdi
0x14009f734  lea     rdx, [rsp+1D0h+var_188]
0x14009f739  call    VidHandleTableGetNext
0x14009f73e  xor     r13d, r13d
0x14009f741  jmp     short loc_14009F769
0x14009f743  cmp     [r11+128h], r13
0x14009f74a  jz      short loc_14009F75C
0x14009f74c  mov     rcx, [r11+180h]
0x14009f753  cmp     [rcx+280h], r13
0x14009f75a  jz      short loc_14009F7C4
0x14009f75c  lea     rdx, [rsp+1D0h+var_188]
0x14009f761  mov     rcx, rdi
0x14009f764  call    VidHandleTableGetNext
0x14009f769  mov     r11, rax
0x14009f76c  test    rax, rax
0x14009f76f  jnz     short loc_14009F743
0x14009f771  mov     eax, [rbx+21D4h]
0x14009f777  cmp     eax, 1
0x14009f77a  jnz     loc_14009F8EC
0x14009f780  mov     r8d, 0C000A003h
0x14009f786  mov     edi, r8d
0x14009f789  mov     rax, [rbx+288h]
0x14009f790  lea     rcx, [rbx+78h]
0x14009f794  mov     [rsp+1D0h+var_1A0], r8d
0x14009f799  mov     r8d, 2A6h
0x14009f79f  mov     [rsp+1D0h+var_1A8], rax
0x14009f7a4  mov     [rsp+1D0h+var_1B0], rcx
0x14009f7a9  mov     r9, r14
0x14009f7ac  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x14009f7b3  lea     rcx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x14009f7ba  call    VidTracePartitionErrorInternal0
0x14009f7bf  jmp     loc_14009F681
0x14009f7c4  mov     eax, cs:dword_140064110
0x14009f7ca  mov     edi, 0C037003Eh
0x14009f7cf  cmp     eax, esi
0x14009f7d1  jbe     loc_14009F681
0x14009f7d7  mov     edx, 100h
0x14009f7dc  lea     rcx, dword_140064110
0x14009f7e3  call    _tlgKeywordOn
0x14009f7e8  test    al, al
0x14009f7ea  jz      loc_14009F681
0x14009f7f0  lea     rdx, aVsmmphuioctlco; "VsmmPhuIoctlCommit"
0x14009f7f7  lea     rcx, [rbp+0D0h+var_120]
0x14009f7fb  call    _tlgCreate1Sz_char
0x14009f800  lea     rdx, aOnecoreVmVidSy_9; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphu.c"
0x14009f807  lea     rcx, [rbp+0D0h+var_110]
0x14009f80b  call    _tlgCreate1Sz_char
0x14009f810  lea     rax, [rsp+1D0h+var_188]
0x14009f815  mov     dword ptr [rsp+1D0h+var_188], 299h
0x14009f81d  mov     [rbp+0D0h+var_100], rax
0x14009f821  lea     rdx, qword_14004B070
0x14009f828  lea     rax, [rsp+1D0h+var_18C]
0x14009f82d  mov     [rbp+0D0h+var_F8], 4
0x14009f835  mov     [rbp+0D0h+var_F0], rax
0x14009f839  lea     rax, [rbp+0D0h+var_B8]
0x14009f83d  mov     [rbp+0D0h+var_D0], rax
0x14009f841  mov     rax, [rbx+80h]
0x14009f848  mov     [rbp+0D0h+var_C0], rax
0x14009f84c  movzx   eax, word ptr [rbx+78h]
0x14009f850  mov     [rbp+0D0h+var_B8], eax
0x14009f853  mov     rax, [rbx+288h]
0x14009f85a  mov     [rsp+1D0h+var_160], rax
0x14009f85f  lea     rax, [rsp+1D0h+var_160]
0x14009f864  mov     [rbp+0D0h+var_B0], rax
0x14009f868  mov     rax, [r11+0F8h]
0x14009f86f  mov     [rbp+0D0h+var_150], rax
0x14009f873  lea     rax, [rbp+0D0h+var_150]
0x14009f877  mov     [rbp+0D0h+var_A0], rax
0x14009f87b  mov     rax, [r11+100h]
0x14009f882  mov     [rsp+1D0h+var_158], rax
  ... truncated ...
```
