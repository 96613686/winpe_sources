# VidPartitionUninitialize

- ea: `0x140011d70`
- end: `0x140012254`
- name: `VidPartitionUninitialize`
- size: `1252`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `installer_update`

## callers

- `0x140007ac8`
- `0x1400094b8`
- `0x14000a040`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14000fdf8`
- `0x140011d70`
- `0x140014378`
- `0x140015f18`
- `0x140016a20`
- `0x140021c60`
- `0x140023a60`
- `0x1400858ec`
- `0x140087acc`
- `0x1400880e4`
- `0x14008a6d0`
- `0x14008b628`
- `0x140094c6c`
- `0x140097e3c`
- `0x140099634`
- `0x14009a308`
- `0x14009baac`
- `0x14009fec8`
- `0x1400a05b0`
- `0x1400a3c4c`
- `0x1400a4ffc`
- `0x1400a6bb4`
- `0x1400a8e38`
- `0x1400a8e74`
- `0x1400ef6d0`
- `0x1400ef7e8`
- `0x1401040c8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14001220f`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14001220f`
- `ntoskrnl!ZwClose` at `0x1400121e9`
- `ntoskrnl!ZwClose` at `0x1400121e9`
- `ntoskrnl!IoFreeWorkItem` at `0x1400121b2`
- `ntoskrnl!IoFreeWorkItem` at `0x1400121ca`
- `ntoskrnl!IoFreeWorkItem` at `0x1400121b2`
- `ntoskrnl!IoFreeWorkItem` at `0x1400121ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011df6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001216b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011df6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e46`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011e8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001216b`
- `winhvr!WinHvDeletePartition` at `0x14001205e`
- `winhvr!WinHvDeletePartition` at `0x14001205e`
- `winhvr!WinHvFinalizePartition` at `0x140011f02`
- `winhvr!WinHvFinalizePartition` at `0x140011f02`

## string_xrefs

- `0x140011f54`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140011ff6`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400120a3`: `onecore\vm\vid\sys\driver\vidcreateclose.c`

## pseudocode

```c
void __fastcall VidPartitionUninitialize(__int64 a1)
{
  unsigned int i; // ebx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  void *v12; // rcx
  struct _IO_WORKITEM *v13; // rcx
  struct _IO_WORKITEM *v14; // rcx
  void *v15; // rcx
  int v16; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v17[3]; // [rsp+34h] [rbp-45h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v19[16]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-9h] BYREF
  int *v21; // [rsp+80h] [rbp+7h]
  __int64 v22; // [rsp+88h] [rbp+Fh]
  int *v23; // [rsp+90h] [rbp+17h]
  __int64 v24; // [rsp+98h] [rbp+1Fh]

  VsmmPartitionUninitialize();
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) == 0 && *(_QWORD *)(a1 + 648) != -1 && *(_QWORD *)(a1 + 3208) )
  {
    for ( i = *(_DWORD *)(a1 + 3200); i; VidVpDeleteFromHypervisor(*(_QWORD *)(a1 + 3208) + 2512LL * i) )
      --i;
    ExFreePoolWithTag(*(PVOID *)(a1 + 3208), 0x72446456u);
    *(_QWORD *)(a1 + 3208) = 0;
    *(_DWORD *)(a1 + 3200) = 0;
  }
  VidMessagePoolFree(a1);
  VidHvStatsMappingSetTeardown(a1 + 1616);
  VidHvStateTeardown(a1);
  VidReaderCounterTeardown(a1 + 3928);
  v3 = *(void **)(a1 + 3392);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x72446456u);
    *(_QWORD *)(a1 + 3392) = 0;
  }
  v4 = *(void **)(a1 + 3408);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0x72446456u);
    *(_QWORD *)(a1 + 3408) = 0;
  }
  v5 = *(void **)(a1 + 3376);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x72446456u);
    *(_QWORD *)(a1 + 3376) = 0;
  }
  if ( *(_BYTE *)(a1 + 832) )
    VidDispatchInterfaceUninitialize(a1);
  VidSynicPortPartitionTeardown(a1);
  VidHandleTableUninitialize(a1 + 3232);
  VidHandleTableUninitialize(a1 + 3264);
  VsmmPhuHvPartitionTeardown(a1);
  VidTriggerPartitionTeardown(a1);
  if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 )
    VidExoVpTeardown(a1);
  if ( *(_QWORD *)(a1 + 648) != -1 )
  {
    v6 = WinHvFinalizePartition();
    v8 = (unsigned int)v6;
    if ( v6 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v17[0] = v9;
      v21 = &v16;
      v16 = 1223;
      v23 = v17;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &dword_1400463FC, 0, 0, 6, v18);
    }
    if ( (int)VidHvMemWithdrawAll(a1, v7, v8) < 0
      && (unsigned int)dword_140065110 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v16 = v10;
      v21 = v17;
      v17[0] = 1248;
      v23 = &v16;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_1400463B9, 0, 0, 6, v18);
    }
    if ( (int)WinHvDeletePartition(*(_QWORD *)(a1 + 648)) < 0
      && (unsigned int)dword_140065110 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v16 = v11;
      v21 = v17;
      v17[0] = 1255;
      v23 = &v16;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_140046376, 0, 0, 6, v18);
    }
    *(_QWORD *)(a1 + 648) = -1;
  }
  VidPdcNotifyPartitionTeardown(a1);
  VsmmMemTrackerPartitionCleanup(a1);
  VsmmFallbackMappingTeardown(a1 + 8432);
  VsmmFallbackMdlTeardown(a1 + 8408);
  VsmmPhuPartitionTeardown(a1);
  VsmmProcessTeardown(a1);
  VsmmMemPartTeardownPhysicalAllocationMemPart(a1);
  VsmmMemPartTeardownMemoryHostingJob(a1);
  VidResourcePartitionPartitionTeardown(a1);
  v12 = *(void **)(a1 + 112);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0x72446456u);
    *(_QWORD *)(a1 + 112) = 0;
    *(_DWORD *)(a1 + 104) = 0;
  }
  VidStatisticsDataUnMap((PFAST_MUTEX)(a1 + 1472));
  VidStatisticsDataTeardown((PFAST_MUTEX)(a1 + 1472));
  VidHypercallDoorbellFree(a1);
  v13 = *(struct _IO_WORKITEM **)(a1 + 12256);
  if ( v13 )
    IoFreeWorkItem(v13);
  v14 = *(struct _IO_WORKITEM **)(a1 + 12160);
  if ( v14 )
  {
    IoFreeWorkItem(v14);
    *(_QWORD *)(a1 + 12160) = 0;
  }
  v15 = *(void **)(a1 + 10248);
  if ( v15 )
  {
    ZwClose(v15);
    *(_QWORD *)(a1 + 10248) = 0;
  }
  if ( *(_BYTE *)(a1 + 8657) )
  {
    *(_BYTE *)(a1 + 8657) = 0;
  }
  else
  {
    ObfDereferenceObjectWithTag(*(PVOID *)(a1 + 10240), 0x72446456u);
    *(_QWORD *)(a1 + 10240) = 0;
  }
}

```

## disassembly

```asm
0x140011d70  mov     [rsp-8+arg_8], rbx
0x140011d75  mov     [rsp-8+arg_10], rsi
0x140011d7a  push    rbp
0x140011d7b  push    rdi
0x140011d7c  push    r12
0x140011d7e  push    r14
0x140011d80  push    r15
0x140011d82  lea     rbp, [rsp-37h]
0x140011d87  sub     rsp, 0B0h
0x140011d8e  mov     rax, cs:__security_cookie
0x140011d95  xor     rax, rsp
0x140011d98  mov     [rbp+57h+var_30], rax
0x140011d9c  mov     rdi, rcx
0x140011d9f  call    VsmmPartitionUninitialize
0x140011da4  mov     eax, [rdi+10h]
0x140011da7  xor     esi, esi
0x140011da9  bt      rax, 0Fh
0x140011dae  mov     r14d, 72446456h
0x140011db4  jb      short loc_140011E0F
0x140011db6  cmp     qword ptr [rdi+288h], 0FFFFFFFFFFFFFFFFh
0x140011dbe  jz      short loc_140011E0F
0x140011dc0  cmp     [rdi+0C88h], rsi
0x140011dc7  jz      short loc_140011E0F
0x140011dc9  mov     ebx, [rdi+0C80h]
0x140011dcf  jmp     short loc_140011DE8
0x140011dd1  dec     ebx
0x140011dd3  mov     eax, ebx
0x140011dd5  imul    rcx, rax, 9D0h
0x140011ddc  add     rcx, [rdi+0C88h]
0x140011de3  call    VidVpDeleteFromHypervisor
0x140011de8  test    ebx, ebx
0x140011dea  jnz     short loc_140011DD1
0x140011dec  mov     rcx, [rdi+0C88h]; P
0x140011df3  mov     edx, r14d; Tag
0x140011df6  call    cs:__imp_ExFreePoolWithTag
0x140011dfd  nop     dword ptr [rax+rax+00h]
0x140011e02  mov     [rdi+0C88h], rsi
0x140011e09  mov     [rdi+0C80h], esi
0x140011e0f  mov     rcx, rdi
0x140011e12  call    VidMessagePoolFree
0x140011e17  lea     rcx, [rdi+650h]
0x140011e1e  call    VidHvStatsMappingSetTeardown
0x140011e23  mov     rcx, rdi
0x140011e26  call    VidHvStateTeardown
0x140011e2b  lea     rcx, [rdi+0F58h]
0x140011e32  call    VidReaderCounterTeardown
0x140011e37  mov     rcx, [rdi+0D40h]; P
0x140011e3e  test    rcx, rcx
0x140011e41  jz      short loc_140011E59
0x140011e43  mov     edx, r14d; Tag
0x140011e46  call    cs:__imp_ExFreePoolWithTag
0x140011e4d  nop     dword ptr [rax+rax+00h]
0x140011e52  mov     [rdi+0D40h], rsi
0x140011e59  mov     rcx, [rdi+0D50h]; P
0x140011e60  test    rcx, rcx
0x140011e63  jz      short loc_140011E7B
0x140011e65  mov     edx, r14d; Tag
0x140011e68  call    cs:__imp_ExFreePoolWithTag
0x140011e6f  nop     dword ptr [rax+rax+00h]
0x140011e74  mov     [rdi+0D50h], rsi
0x140011e7b  mov     rcx, [rdi+0D30h]; P
0x140011e82  test    rcx, rcx
0x140011e85  jz      short loc_140011E9D
0x140011e87  mov     edx, r14d; Tag
0x140011e8a  call    cs:__imp_ExFreePoolWithTag
0x140011e91  nop     dword ptr [rax+rax+00h]
0x140011e96  mov     [rdi+0D30h], rsi
0x140011e9d  mov     al, [rdi+340h]
0x140011ea3  test    al, al
0x140011ea5  jz      short loc_140011EAF
0x140011ea7  mov     rcx, rdi
0x140011eaa  call    VidDispatchInterfaceUninitialize
0x140011eaf  mov     rcx, rdi
0x140011eb2  call    VidSynicPortPartitionTeardown
0x140011eb7  lea     rcx, [rdi+0CA0h]
0x140011ebe  call    VidHandleTableUninitialize
0x140011ec3  lea     rcx, [rdi+0CC0h]
0x140011eca  call    VidHandleTableUninitialize
0x140011ecf  mov     rcx, rdi
0x140011ed2  call    VsmmPhuHvPartitionTeardown
0x140011ed7  mov     rcx, rdi
0x140011eda  call    VidTriggerPartitionTeardown
0x140011edf  mov     eax, [rdi+10h]
0x140011ee2  bt      rax, 0Fh
0x140011ee7  jnb     short loc_140011EF1
0x140011ee9  mov     rcx, rdi
0x140011eec  call    VidExoVpTeardown
0x140011ef1  mov     rcx, [rdi+288h]
0x140011ef8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140011efc  jz      loc_14001210F
0x140011f02  call    cs:__imp_WinHvFinalizePartition
0x140011f09  nop     dword ptr [rax+rax+00h]
0x140011f0e  mov     r15d, 100h
0x140011f14  lea     rbx, dword_140065110
0x140011f1b  mov     r8d, eax
0x140011f1e  test    eax, eax
0x140011f20  jns     loc_140011FB5
0x140011f26  mov     ecx, cs:dword_140065110
0x140011f2c  cmp     ecx, 2
0x140011f2f  jbe     loc_140011FB5
0x140011f35  mov     edx, r15d
0x140011f38  mov     rcx, rbx
0x140011f3b  call    _tlgKeywordOn
0x140011f40  test    al, al
0x140011f42  jz      short loc_140011FB5
0x140011f44  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x140011f4b  lea     rcx, [rbp+57h+var_70]
0x140011f4f  call    _tlgCreate1Sz_char
0x140011f54  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140011f5b  lea     rcx, [rbp+57h+var_60]
0x140011f5f  call    _tlgCreate1Sz_char
0x140011f64  lea     rax, [rbp+57h+var_A0]
0x140011f68  mov     [rbp+57h+var_9C], r8d
0x140011f6c  mov     [rbp+57h+var_50], rax
0x140011f70  lea     rdx, dword_1400463FC
0x140011f77  lea     rax, [rbp+57h+var_9C]
0x140011f7b  mov     [rbp+57h+var_A0], 4C7h
0x140011f82  mov     [rbp+57h+var_40], rax
0x140011f86  xor     r9d, r9d
0x140011f89  lea     rax, [rbp+57h+var_90]
0x140011f8d  mov     [rbp+57h+var_48], 4
0x140011f95  mov     [rsp+0D0h+var_A8], rax
0x140011f9a  xor     r8d, r8d
0x140011f9d  mov     rcx, rbx
0x140011fa0  mov     [rsp+0D0h+var_B0], 6
0x140011fa8  mov     [rbp+57h+var_38], 4
0x140011fb0  call    _tlgWriteTransfer_EtwWriteTransfer
0x140011fb5  mov     rcx, rdi
0x140011fb8  call    VidHvMemWithdrawAll
0x140011fbd  mov     r8d, eax
0x140011fc0  test    eax, eax
0x140011fc2  jns     loc_140012057
0x140011fc8  mov     ecx, cs:dword_140065110
0x140011fce  cmp     ecx, 2
0x140011fd1  jbe     loc_140012057
0x140011fd7  mov     rdx, r15
0x140011fda  mov     rcx, rbx
0x140011fdd  call    _tlgKeywordOn
0x140011fe2  test    al, al
0x140011fe4  jz      short loc_140012057
0x140011fe6  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x140011fed  lea     rcx, [rbp+57h+var_70]
0x140011ff1  call    _tlgCreate1Sz_char
0x140011ff6  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140011ffd  lea     rcx, [rbp+57h+var_60]
0x140012001  call    _tlgCreate1Sz_char
0x140012006  lea     rax, [rbp+57h+var_9C]
0x14001200a  mov     [rbp+57h+var_A0], r8d
0x14001200e  mov     [rbp+57h+var_50], rax
0x140012012  lea     rdx, byte_1400463B9
0x140012019  lea     rax, [rbp+57h+var_A0]
0x14001201d  mov     [rbp+57h+var_9C], 4E0h
0x140012024  mov     [rbp+57h+var_40], rax
0x140012028  xor     r9d, r9d
0x14001202b  lea     rax, [rbp+57h+var_90]
0x14001202f  mov     [rbp+57h+var_48], 4
0x140012037  mov     [rsp+0D0h+var_A8], rax
0x14001203c  xor     r8d, r8d
0x14001203f  mov     rcx, rbx
0x140012042  mov     [rsp+0D0h+var_B0], 6
0x14001204a  mov     [rbp+57h+var_38], 4
0x140012052  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012057  mov     rcx, [rdi+288h]
0x14001205e  call    cs:__imp_WinHvDeletePartition
0x140012065  nop     dword ptr [rax+rax+00h]
0x14001206a  mov     r8d, eax
0x14001206d  test    eax, eax
0x14001206f  jns     loc_140012104
0x140012075  mov     ecx, cs:dword_140065110
0x14001207b  cmp     ecx, 2
0x14001207e  jbe     loc_140012104
0x140012084  mov     rdx, r15
0x140012087  mov     rcx, rbx
0x14001208a  call    _tlgKeywordOn
0x14001208f  test    al, al
0x140012091  jz      short loc_140012104
0x140012093  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x14001209a  lea     rcx, [rbp+57h+var_70]
0x14001209e  call    _tlgCreate1Sz_char
0x1400120a3  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400120aa  lea     rcx, [rbp+57h+var_60]
0x1400120ae  call    _tlgCreate1Sz_char
0x1400120b3  lea     rax, [rbp+57h+var_9C]
0x1400120b7  mov     [rbp+57h+var_A0], r8d
0x1400120bb  mov     [rbp+57h+var_50], rax
0x1400120bf  lea     rdx, word_140046376
0x1400120c6  lea     rax, [rbp+57h+var_A0]
0x1400120ca  mov     [rbp+57h+var_9C], 4E7h
0x1400120d1  mov     [rbp+57h+var_40], rax
0x1400120d5  xor     r9d, r9d
0x1400120d8  lea     rax, [rbp+57h+var_90]
0x1400120dc  mov     [rbp+57h+var_48], 4
0x1400120e4  mov     [rsp+0D0h+var_A8], rax
0x1400120e9  xor     r8d, r8d
0x1400120ec  mov     rcx, rbx
0x1400120ef  mov     [rsp+0D0h+var_B0], 6
0x1400120f7  mov     [rbp+57h+var_38], 4
0x1400120ff  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012104  mov     qword ptr [rdi+288h], 0FFFFFFFFFFFFFFFFh
0x14001210f  mov     rcx, rdi
0x140012112  call    VidPdcNotifyPartitionTeardown
0x140012117  mov     rcx, rdi
0x14001211a  call    VsmmMemTrackerPartitionCleanup
0x14001211f  lea     rcx, [rdi+20F0h]
0x140012126  call    VsmmFallbackMappingTeardown
0x14001212b  lea     rcx, [rdi+20D8h]
0x140012132  call    VsmmFallbackMdlTeardown
0x140012137  mov     rcx, rdi
0x14001213a  call    VsmmPhuPartitionTeardown
0x14001213f  mov     rcx, rdi
0x140012142  call    VsmmProcessTeardown
0x140012147  mov     rcx, rdi
0x14001214a  call    VsmmMemPartTeardownPhysicalAllocationMemPart
0x14001214f  mov     rcx, rdi
0x140012152  call    VsmmMemPartTeardownMemoryHostingJob
0x140012157  mov     rcx, rdi
0x14001215a  call    VidResourcePartitionPartitionTeardown
0x14001215f  mov     rcx, [rdi+70h]; P
0x140012163  test    rcx, rcx
0x140012166  jz      short loc_14001217E
0x140012168  mov     edx, r14d; Tag
0x14001216b  call    cs:__imp_ExFreePoolWithTag
0x140012172  nop     dword ptr [rax+rax+00h]
0x140012177  mov     [rdi+70h], rsi
0x14001217b  mov     [rdi+68h], esi
0x14001217e  lea     rbx, [rdi+5C0h]
0x140012185  xor     edx, edx
0x140012187  mov     rcx, rbx; FastMutex
0x14001218a  lea     r8, [rdi+608h]
0x140012191  call    VidStatisticsDataUnMap
0x140012196  mov     rcx, rbx; FastMutex
0x140012199  call    VidStatisticsDataTeardown
0x14001219e  mov     rcx, rdi
0x1400121a1  call    VidHypercallDoorbellFree
0x1400121a6  mov     rcx, [rdi+2FE0h]; IoWorkItem
0x1400121ad  test    rcx, rcx
0x1400121b0  jz      short loc_1400121BE
0x1400121b2  call    cs:__imp_IoFreeWorkItem
0x1400121b9  nop     dword ptr [rax+rax+00h]
0x1400121be  mov     rcx, [rdi+2F80h]; IoWorkItem
0x1400121c5  test    rcx, rcx
0x1400121c8  jz      short loc_1400121DD
0x1400121ca  call    cs:__imp_IoFreeWorkItem
0x1400121d1  nop     dword ptr [rax+rax+00h]
0x1400121d6  mov     [rdi+2F80h], rsi
0x1400121dd  mov     rcx, [rdi+2808h]; Handle
0x1400121e4  test    rcx, rcx
0x1400121e7  jz      short loc_1400121FC
0x1400121e9  call    cs:__imp_ZwClose
0x1400121f0  nop     dword ptr [rax+rax+00h]
0x1400121f5  mov     [rdi+2808h], rsi
0x1400121fc  cmp     [rdi+21D1h], sil
0x140012203  jnz     short loc_140012224
0x140012205  mov     rcx, [rdi+2800h]; Object
0x14001220c  mov     edx, r14d; Tag
0x14001220f  call    cs:__imp_ObfDereferenceObjectWithTag
0x140012216  nop     dword ptr [rax+rax+00h]
0x14001221b  mov     [rdi+2800h], rsi
0x140012222  jmp     short loc_14001222B
0x140012224  mov     [rdi+21D1h], sil
0x14001222b  mov     rcx, [rbp+57h+var_30]
0x14001222f  xor     rcx, rsp; StackCookie
0x140012232  call    __security_check_cookie
0x140012237  lea     r11, [rsp+0D0h+var_20]
0x14001223f  mov     rbx, [r11+38h]
0x140012243  mov     rsi, [r11+40h]
0x140012247  mov     rsp, r11
0x14001224a  pop     r15
0x14001224c  pop     r14
0x14001224e  pop     r12
0x140012250  pop     rdi
0x140012251  pop     rbp
0x140012252  retn
```
