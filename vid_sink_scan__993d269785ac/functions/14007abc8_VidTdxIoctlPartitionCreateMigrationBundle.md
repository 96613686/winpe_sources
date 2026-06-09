# VidTdxIoctlPartitionCreateMigrationBundle

- ea: `0x14007abc8`
- end: `0x14007b26b`
- name: `VidTdxIoctlPartitionCreateMigrationBundle`
- size: `1699`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int8, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x1400246b0`
- `0x140024718`
- `0x140024c78`
- `0x140030790`
- `0x1400307d0`
- `0x14007a150`
- `0x14007abc8`
- `0x1400ef710`

## import_xrefs

- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14007ae85`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14007ae85`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007aef2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007aef2`
- `ntoskrnl!ExAllocatePool2` at `0x14007adde`
- `ntoskrnl!ExAllocatePool2` at `0x14007adde`
- `winhvr!WinHvCreateTdMigrationBundle` at `0x14007af27`
- `winhvr!WinHvCreateTdMigrationBundle` at `0x14007af27`

## string_xrefs

- `0x14007ac52`: `VidTdxIoctlPartitionCreateMigrationBundle`

## pseudocode

```c
__int64 __fastcall VidTdxIoctlPartitionCreateMigrationBundle(
        __int64 a1,
        unsigned int a2,
        unsigned __int8 a3,
        __int64 *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 *v9; // r14
  unsigned int v10; // edx
  __int64 *v11; // rcx
  int TdMigrationBundle; // edi
  _QWORD *Pool2; // rax
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdi
  struct _MDL *NodePagesForMdl; // rax
  int v19; // r8d
  PVOID v20; // rax
  int v21; // r8d
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  _OWORD *v24; // rax
  __int128 v25; // xmm1
  unsigned int v26; // edx
  __int64 *v27; // rcx
  unsigned int v28; // edx
  __int64 *v29; // rcx
  char v31; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v32; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v33; // [rsp+42h] [rbp-BEh]
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[10]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v40[34]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v42[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v43; // [rsp+200h] [rbp+100h] BYREF
  __int64 v44; // [rsp+208h] [rbp+108h]
  __int64 *v45; // [rsp+210h] [rbp+110h]
  __int64 v46; // [rsp+218h] [rbp+118h]
  __int64 *v47; // [rsp+220h] [rbp+120h]
  __int64 v48; // [rsp+228h] [rbp+128h] BYREF
  __int64 *v49; // [rsp+230h] [rbp+130h]
  __int64 v50; // [rsp+238h] [rbp+138h] BYREF
  __int64 *v51; // [rsp+240h] [rbp+140h]
  __int64 v52; // [rsp+248h] [rbp+148h]
  __int64 *v53; // [rsp+250h] [rbp+150h]
  __int64 v54; // [rsp+258h] [rbp+158h]

  v33 = a3;
  LODWORD(v34) = a2;
  v38 = a4;
  memset(v40, 0, sizeof(v40));
  memset(v39, 0, sizeof(v39));
  v31 = 0;
  v7 = -1;
  VidTraceActivityInitialize(v39);
  v8 = a1 + 120;
  v9 = (__int64 *)(a1 + 648);
  v35 = a1 + 120;
  v39[7] = *(_QWORD *)(a1 + 648);
  v39[0] = "VidTdxIoctlPartitionCreateMigrationBundle";
  v39[6] = a1 + 656;
  v39[8] = a1 + 120;
  if ( (unsigned int)dword_140064110 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v42, v39[0]);
      v43 = v39[6];
      v44 = 16;
      v10 = *(unsigned __int16 *)v39[8];
      v11 = *(__int64 **)(v39[8] + 8LL);
      v45 = &v48;
      v37 = v39[7];
      v49 = &v37;
      v51 = (__int64 *)&v36;
      v53 = (__int64 *)&v32;
      v47 = v11;
      v48 = v10;
      v46 = 2;
      v50 = 8;
      v36 = a2;
      v52 = 4;
      v32 = a3;
      v54 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140045EE1, &v39[4], &v39[2], 9, v41);
    }
    v8 = a1 + 120;
  }
  LOBYTE(v39[9]) = 1;
  if ( a2 > 1 )
  {
    v14 = 0;
    TdMigrationBundle = -1073741811;
    v21 = 256;
    goto LABEL_23;
  }
  if ( a3 < *(_BYTE *)(a1 + 2040) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 384, 1917084758);
    v14 = Pool2;
    if ( !Pool2 )
    {
      TdMigrationBundle = -1073741670;
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
        276,
        a1 + 656,
        v35,
        *v9,
        -1073741670);
      goto LABEL_28;
    }
    *Pool2 = 0;
    v15 = Pool2 + 35;
    memset(Pool2 + 35, 0, 0x48u);
    v15[6] = v15 + 5;
    v15[5] = v15 + 5;
    v16 = v33;
    v14[1] = -1;
    v17 = (unsigned int)v16;
    v14[46] = 0;
    *((_BYTE *)v14 + 376) = v16;
    NodePagesForMdl = (struct _MDL *)MmAllocateNodePagesForMdlEx(
                                       0,
                                       -1,
                                       0,
                                       4096,
                                       1,
                                       *(unsigned __int8 *)(v16 + a1 + 2041),
                                       20);
    v14[45] = NodePagesForMdl;
    if ( !NodePagesForMdl )
    {
      v19 = 313;
LABEL_13:
      TdMigrationBundle = -1073741670;
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
        v19,
        a1 + 656,
        a1 + 120,
        *v9,
        -1073741670);
      goto LABEL_25;
    }
    v20 = MmMapLockedPagesSpecifyCache(NodePagesForMdl, 0, MmCached, 0, 0, 0x40000010u);
    v14[44] = v20;
    if ( !v20 )
    {
      v19 = 328;
      goto LABEL_13;
    }
    TdMigrationBundle = WinHvCreateTdMigrationBundle(*v9, *(unsigned __int8 *)(v17 + a1 + 2041), (unsigned int)v34, v40);
    if ( TdMigrationBundle >= 0 )
    {
      v7 = v40[0];
      v22 = v14 + 2;
      v23 = 2;
      v14[1] = v40[0];
      v24 = &v40[1];
      do
      {
        *v22 = *v24;
        v22[1] = v24[1];
        v22[2] = v24[2];
        v22[3] = v24[3];
        v22[4] = v24[4];
        v22[5] = v24[5];
        v22[6] = v24[6];
        v25 = v24[7];
        v24 += 8;
        v22[7] = v25;
        v22 += 8;
        --v23;
      }
      while ( v23 );
      *(_QWORD *)v22 = *(_QWORD *)v24;
      VidLockAcquireExclusive(a1 + 12760);
      TdMigrationBundle = VidHandleTableAllocateEntry(a1 + 12728, v14, v38);
      if ( TdMigrationBundle >= 0 )
      {
LABEL_27:
        VidLockRelease(a1 + 12760);
        goto LABEL_28;
      }
      v31 = 1;
      v21 = 358;
    }
    else
    {
      v21 = 340;
    }
LABEL_23:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      v21,
      a1 + 656,
      a1 + 120,
      *v9,
      TdMigrationBundle);
    if ( !v14 )
    {
LABEL_26:
      if ( !v31 )
        goto LABEL_28;
      goto LABEL_27;
    }
LABEL_25:
    VidTdxMigrationBundleTeardown(a1, v14);
    goto LABEL_26;
  }
  TdMigrationBundle = -1073741811;
  VidTracePartitionErrorInternal0(
    (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
    (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
    263,
    a1 + 656,
    v8,
    *v9,
    -1073741811);
LABEL_28:
  if ( LOBYTE(v39[9]) )
  {
    if ( TdMigrationBundle < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        v42[0] = &v34;
        LODWORD(v34) = TdMigrationBundle;
        v42[1] = 4;
        tlgCreate1Sz_char(&v43, v39[0]);
        v45 = (__int64 *)v39[6];
        v46 = 16;
        v28 = *(unsigned __int16 *)v39[8];
        v29 = *(__int64 **)(v39[8] + 8LL);
        v47 = &v50;
        v35 = v39[7];
        v51 = &v35;
        v49 = v29;
        v50 = v28;
        v48 = 2;
        v52 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140045DF3, &v39[4], 0, 8, v41);
      }
    }
    else if ( (unsigned int)dword_140064110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v42, v39[0]);
      v43 = v39[6];
      v44 = 16;
      v26 = *(unsigned __int16 *)v39[8];
      v27 = *(__int64 **)(v39[8] + 8LL);
      v45 = &v48;
      v35 = v39[7];
      v49 = &v35;
      v48 = v26;
      v46 = 2;
      v47 = v27;
      v37 = *v38;
      v51 = &v37;
      v53 = &v34;
      v50 = 8;
      v52 = 8;
      v34 = v7;
      v54 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140045E5A, &v39[4], 0, 9, v41);
    }
    VidTraceActivityTeardown(v39);
  }
  return (unsigned int)TdMigrationBundle;
}

```

## disassembly

```asm
0x14007abc8  push    rbp
0x14007abca  push    rbx
0x14007abcb  push    rsi
0x14007abcc  push    rdi
0x14007abcd  push    r12
0x14007abcf  push    r13
0x14007abd1  push    r14
0x14007abd3  push    r15
0x14007abd5  lea     rbp, [rsp-178h]
0x14007abdd  sub     rsp, 278h
0x14007abe4  mov     rax, cs:__security_cookie
0x14007abeb  xor     rax, rsp
0x14007abee  mov     [rbp+1B0h+var_50], rax
0x14007abf5  mov     dil, r8b
0x14007abf8  mov     [rsp+2B0h+var_26E], r8b
0x14007abfd  mov     esi, edx
0x14007abff  mov     dword ptr [rsp+2B0h+var_268], edx
0x14007ac03  mov     r13, rcx
0x14007ac06  mov     [rsp+2B0h+var_248], r9
0x14007ac0b  xor     edx, edx; Val
0x14007ac0d  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x14007ac11  mov     r8d, 110h; Size
0x14007ac17  call    memset
0x14007ac1c  xor     edx, edx; Val
0x14007ac1e  lea     rcx, [rsp+2B0h+var_240]; void *
0x14007ac23  lea     r8d, [rdx+50h]; Size
0x14007ac27  call    memset
0x14007ac2c  lea     rcx, [rsp+2B0h+var_240]
0x14007ac31  mov     [rsp+2B0h+var_270], 0
0x14007ac36  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14007ac3a  call    VidTraceActivityInitialize
0x14007ac3f  lea     rcx, [r13+78h]
0x14007ac43  lea     r14, [r13+288h]
0x14007ac4a  mov     [rsp+2B0h+var_260], rcx
0x14007ac4f  mov     rax, [r14]
0x14007ac52  lea     r15, aVidtdxioctlpar_23
0x14007ac59  mov     [rbp+1B0h+var_208], rax
0x14007ac5d  lea     r12, [r13+290h]
0x14007ac64  mov     eax, cs:dword_140064110
0x14007ac6a  mov     [rsp+2B0h+var_240], r15
0x14007ac6f  mov     [rbp+1B0h+var_210], r12
0x14007ac73  mov     [rbp+1B0h+var_200], rcx
0x14007ac77  cmp     eax, 5
0x14007ac7a  jbe     loc_14007AD85
0x14007ac80  mov     edx, 100h
0x14007ac85  lea     rcx, dword_140064110
0x14007ac8c  call    _tlgKeywordOn
0x14007ac91  test    al, al
0x14007ac93  jz      loc_14007AD81
0x14007ac99  mov     rdx, [rsp+2B0h+var_240]
0x14007ac9e  lea     rcx, [rbp+1B0h+var_C0]
0x14007aca5  call    _tlgCreate1Sz_char
0x14007acaa  mov     rax, [rbp+1B0h+var_200]
0x14007acae  lea     r9, [rbp+1B0h+var_230]
0x14007acb2  mov     rcx, [rbp+1B0h+var_210]
0x14007acb6  lea     r8, [rbp+1B0h+var_220]
0x14007acba  mov     [rbp+1B0h+var_B0], rcx
0x14007acc1  mov     [rbp+1B0h+var_A8], 10h
0x14007accc  movzx   edx, word ptr [rax]
0x14007accf  mov     rcx, [rax+8]
0x14007acd3  lea     rax, [rbp+1B0h+var_88]
0x14007acda  mov     [rbp+1B0h+var_A0], rax
0x14007ace1  mov     rax, [rbp+1B0h+var_208]
0x14007ace5  mov     [rsp+2B0h+var_250], rax
0x14007acea  lea     rax, [rsp+2B0h+var_250]
0x14007acef  mov     [rbp+1B0h+var_80], rax
0x14007acf6  lea     rax, [rsp+2B0h+var_258]
0x14007acfb  mov     [rbp+1B0h+var_70], rax
0x14007ad02  lea     rax, [rsp+2B0h+var_26F]
0x14007ad07  mov     [rbp+1B0h+var_60], rax
0x14007ad0e  lea     rax, [rbp+1B0h+var_E0]
0x14007ad15  mov     [rbp+1B0h+var_90], rcx
0x14007ad1c  lea     rcx, dword_140064110
0x14007ad23  mov     dword ptr [rbp+1B0h+var_88], edx
0x14007ad29  lea     rdx, byte_140045EE1
0x14007ad30  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007ad35  mov     [rsp+2B0h+BugCheckOnFailure], 9
0x14007ad3d  mov     [rbp+1B0h+var_98], 2
0x14007ad48  mov     dword ptr [rbp+1B0h+var_88+4], 0
0x14007ad52  mov     [rbp+1B0h+var_78], 8
0x14007ad5d  mov     [rsp+2B0h+var_258], esi
0x14007ad61  mov     [rbp+1B0h+var_68], 4
0x14007ad6c  mov     [rsp+2B0h+var_26F], dil
0x14007ad71  mov     [rbp+1B0h+var_58], 1
0x14007ad7c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007ad81  lea     rcx, [r13+78h]
0x14007ad85  mov     [rbp+1B0h+var_1F8], 1
0x14007ad89  cmp     esi, 1
0x14007ad8c  ja      loc_14007AFE0
0x14007ad92  cmp     dil, [r13+7F8h]
0x14007ad99  jb      short loc_14007ADCE
0x14007ad9b  mov     edi, 0C000000Dh
0x14007ada0  mov     rax, [r14]
0x14007ada3  mov     r8d, 107h
0x14007ada9  mov     [rsp+2B0h+var_280], edi
0x14007adad  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007adb2  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rcx
0x14007adb7  mov     r9, r12
0x14007adba  lea     rdx, aOnecoreVmVidSy_21
0x14007adc1  mov     rcx, r15
0x14007adc4  call    VidTracePartitionErrorInternal0
0x14007adc9  jmp     loc_14007B03B
0x14007adce  mov     edx, 180h
0x14007add3  mov     ecx, 40h ; '@'
0x14007add8  mov     r8d, 72446456h
0x14007adde  call    cs:__imp_ExAllocatePool2
0x14007ade5  nop     dword ptr [rax+rax+00h]
0x14007adea  mov     rsi, rax
0x14007aded  test    rax, rax
0x14007adf0  jnz     short loc_14007AE17
0x14007adf2  mov     eax, 0C000009Ah
0x14007adf7  mov     edi, eax
0x14007adf9  mov     [rsp+2B0h+var_280], eax
0x14007adfd  mov     r8d, 114h
0x14007ae03  mov     rax, [r14]
0x14007ae06  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007ae0b  mov     rax, [rsp+2B0h+var_260]
0x14007ae10  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007ae15  jmp     short loc_14007ADB7
0x14007ae17  xor     edx, edx; Val
0x14007ae19  mov     qword ptr [rax], 0
0x14007ae20  lea     rdi, [rax+118h]
0x14007ae27  mov     rcx, rdi; void *
0x14007ae2a  lea     r8d, [rdx+48h]; Size
0x14007ae2e  call    memset
0x14007ae33  lea     rax, [rdi+28h]
0x14007ae37  mov     [rsp+2B0h+var_280], 14h
0x14007ae3f  mov     [rax+8], rax
0x14007ae43  xor     ecx, ecx
0x14007ae45  mov     [rax], rax
0x14007ae48  xor     r8d, r8d
0x14007ae4b  movzx   eax, [rsp+2B0h+var_26E]
0x14007ae50  mov     r9d, 1000h
0x14007ae56  mov     [rsi+8], rbx
0x14007ae5a  mov     edi, eax
0x14007ae5c  mov     qword ptr [rsi+170h], 0
0x14007ae67  mov     rdx, rbx
0x14007ae6a  mov     [rsi+178h], al
0x14007ae70  movzx   eax, byte ptr [rax+r13+7F9h]
0x14007ae79  mov     [rsp+2B0h+Priority], eax
0x14007ae7d  mov     [rsp+2B0h+BugCheckOnFailure], 1
0x14007ae85  call    cs:__imp_MmAllocateNodePagesForMdlEx
0x14007ae8c  nop     dword ptr [rax+rax+00h]
0x14007ae91  mov     [rsi+168h], rax
0x14007ae98  test    rax, rax
0x14007ae9b  jnz     short loc_14007AED6
0x14007ae9d  mov     r8d, 139h
0x14007aea3  mov     eax, 0C000009Ah
0x14007aea8  mov     edi, eax
0x14007aeaa  mov     [rsp+2B0h+var_280], eax
0x14007aeae  lea     rdx, aOnecoreVmVidSy_21
0x14007aeb5  mov     rax, [r14]
0x14007aeb8  mov     r9, r12
0x14007aebb  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007aec0  mov     rcx, r15
0x14007aec3  lea     rax, [r13+78h]
0x14007aec7  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007aecc  call    VidTracePartitionErrorInternal0
0x14007aed1  jmp     loc_14007B01D
0x14007aed6  xor     r9d, r9d; RequestedAddress
0x14007aed9  mov     [rsp+2B0h+Priority], 40000010h; Priority
0x14007aee1  xor     edx, edx; AccessMode
0x14007aee3  mov     [rsp+2B0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14007aeeb  mov     rcx, rax; MemoryDescriptorList
0x14007aeee  lea     r8d, [r9+1]; CacheType
0x14007aef2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007aef9  nop     dword ptr [rax+rax+00h]
0x14007aefe  mov     [rsi+160h], rax
0x14007af05  test    rax, rax
0x14007af08  jnz     short loc_14007AF12
0x14007af0a  mov     r8d, 148h
0x14007af10  jmp     short loc_14007AEA3
0x14007af12  movzx   edx, byte ptr [rdi+r13+7F9h]
0x14007af1b  lea     r9, [rbp+1B0h+var_1F0]
0x14007af1f  mov     r8d, dword ptr [rsp+2B0h+var_268]
0x14007af24  mov     rcx, [r14]
0x14007af27  call    cs:__imp_WinHvCreateTdMigrationBundle
0x14007af2e  nop     dword ptr [rax+rax+00h]
0x14007af33  mov     edi, eax
0x14007af35  test    eax, eax
0x14007af37  jns     short loc_14007AF44
0x14007af39  mov     r8d, 154h
0x14007af3f  jmp     loc_14007AFED
0x14007af44  mov     rbx, [rbp+1B0h+var_1F0]
0x14007af48  lea     rcx, [rsi+10h]
0x14007af4c  mov     edx, 2
0x14007af51  mov     [rsi+8], rbx
0x14007af55  lea     rax, [rbp+1B0h+var_1E8]
0x14007af59  lea     r8d, [rdx+7Eh]
0x14007af5d  movups  xmm0, xmmword ptr [rax]
0x14007af60  movups  xmmword ptr [rcx], xmm0
0x14007af63  movups  xmm1, xmmword ptr [rax+10h]
0x14007af67  movups  xmmword ptr [rcx+10h], xmm1
0x14007af6b  movups  xmm0, xmmword ptr [rax+20h]
0x14007af6f  movups  xmmword ptr [rcx+20h], xmm0
0x14007af73  movups  xmm1, xmmword ptr [rax+30h]
0x14007af77  movups  xmmword ptr [rcx+30h], xmm1
0x14007af7b  movups  xmm0, xmmword ptr [rax+40h]
0x14007af7f  movups  xmmword ptr [rcx+40h], xmm0
0x14007af83  movups  xmm1, xmmword ptr [rax+50h]
0x14007af87  movups  xmmword ptr [rcx+50h], xmm1
0x14007af8b  movups  xmm0, xmmword ptr [rax+60h]
0x14007af8f  movups  xmmword ptr [rcx+60h], xmm0
0x14007af93  movups  xmm1, xmmword ptr [rax+70h]
0x14007af97  add     rax, r8
0x14007af9a  movups  xmmword ptr [rcx+70h], xmm1
0x14007af9e  add     rcx, r8
0x14007afa1  sub     rdx, 1
0x14007afa5  jnz     short loc_14007AF5D
0x14007afa7  mov     rax, [rax]
0x14007afaa  mov     [rcx], rax
0x14007afad  lea     rcx, [r13+31D8h]
0x14007afb4  call    VidLockAcquireExclusive
0x14007afb9  mov     r8, [rsp+2B0h+var_248]
0x14007afbe  lea     rcx, [r13+31B8h]
0x14007afc5  mov     rdx, rsi
0x14007afc8  call    VidHandleTableAllocateEntry
0x14007afcd  mov     edi, eax
0x14007afcf  test    eax, eax
0x14007afd1  jns     short loc_14007B02F
0x14007afd3  mov     [rsp+2B0h+var_270], 1
0x14007afd8  mov     r8d, 166h
0x14007afde  jmp     short loc_14007AFED
0x14007afe0  xor     esi, esi
0x14007afe2  mov     edi, 0C000000Dh
0x14007afe7  mov     r8d, 100h
0x14007afed  lea     rdx, aOnecoreVmVidSy_21
0x14007aff4  mov     rax, [r14]
0x14007aff7  mov     r9, r12
0x14007affa  mov     [rsp+2B0h+var_280], edi
0x14007affe  mov     rcx, r15
0x14007b001  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007b006  lea     rax, [r13+78h]
0x14007b00a  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007b00f  call    VidTracePartitionErrorInternal0
0x14007b014  test    edi, edi
0x14007b016  jns     short loc_14007B028
0x14007b018  test    rsi, rsi
0x14007b01b  jz      short loc_14007B028
0x14007b01d  mov     rdx, rsi
0x14007b020  mov     rcx, r13
0x14007b023  call    VidTdxMigrationBundleTeardown
0x14007b028  cmp     [rsp+2B0h+var_270], 0
0x14007b02d  jz      short loc_14007B03B
0x14007b02f  lea     rcx, [r13+31D8h]
0x14007b036  call    VidLockRelease
0x14007b03b  xor     esi, esi
0x14007b03d  cmp     [rbp+1B0h+var_1F8], sil
0x14007b041  jz      loc_14007B245
0x14007b047  mov     eax, cs:dword_140064110
0x14007b04d  test    edi, edi
0x14007b04f  js      loc_14007B155
0x14007b055  cmp     eax, 5
0x14007b058  jbe     loc_14007B23B
0x14007b05e  mov     edx, 100h
0x14007b063  lea     rcx, dword_140064110
0x14007b06a  call    _tlgKeywordOn
0x14007b06f  test    al, al
0x14007b071  jz      loc_14007B23B
0x14007b077  mov     rdx, [rsp+2B0h+var_240]
0x14007b07c  lea     rcx, [rbp+1B0h+var_C0]
0x14007b083  call    _tlgCreate1Sz_char
0x14007b088  mov     rax, [rbp+1B0h+var_200]
0x14007b08c  mov     rcx, [rbp+1B0h+var_210]
0x14007b090  mov     [rbp+1B0h+var_B0], rcx
0x14007b097  mov     [rbp+1B0h+var_A8], 10h
0x14007b0a2  movzx   edx, word ptr [rax]
0x14007b0a5  mov     rcx, [rax+8]
0x14007b0a9  lea     rax, [rbp+1B0h+var_88]
0x14007b0b0  mov     [rbp+1B0h+var_A0], rax
0x14007b0b7  mov     rax, [rbp+1B0h+var_208]
0x14007b0bb  mov     [rsp+2B0h+var_260], rax
0x14007b0c0  lea     rax, [rsp+2B0h+var_260]
0x14007b0c5  mov     [rbp+1B0h+var_80], rax
0x14007b0cc  mov     rax, [rsp+2B0h+var_248]
0x14007b0d1  mov     dword ptr [rbp+1B0h+var_88], edx
0x14007b0d7  lea     rdx, word_140045E5A
0x14007b0de  mov     [rbp+1B0h+var_98], 2
0x14007b0e9  mov     [rbp+1B0h+var_90], rcx
0x14007b0f0  mov     rax, [rax]
0x14007b0f3  mov     [rsp+2B0h+var_250], rax
0x14007b0f8  lea     rax, [rsp+2B0h+var_250]
0x14007b0fd  mov     [rbp+1B0h+var_70], rax
0x14007b104  lea     rax, [rsp+2B0h+var_268]
0x14007b109  mov     [rbp+1B0h+var_60], rax
0x14007b110  lea     rax, [rbp+1B0h+var_E0]
0x14007b117  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007b11c  mov     [rsp+2B0h+BugCheckOnFailure], 9
0x14007b124  mov     dword ptr [rbp+1B0h+var_88+4], esi
0x14007b12a  mov     [rbp+1B0h+var_78], 8
0x14007b135  mov     [rbp+1B0h+var_68], 8
0x14007b140  mov     [rsp+2B0h+var_268], rbx
0x14007b145  mov     [rbp+1B0h+var_58], 8
0x14007b150  jmp     loc_14007B228
0x14007b155  cmp     eax, 2
0x14007b158  jbe     loc_14007B23B
0x14007b15e  mov     edx, 100h
0x14007b163  lea     rcx, dword_140064110
0x14007b16a  call    _tlgKeywordOn
0x14007b16f  test    al, al
  ... truncated ...
```
