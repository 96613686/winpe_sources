# VidPartitionUninitialize

- ea: `0x140011f20`
- end: `0x1400123fc`
- name: `VidPartitionUninitialize`
- size: `1244`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `29`
- tags: `installer_update`

## callers

- `0x1400086d4`
- `0x140009988`
- `0x14000a510`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14000ffa8`
- `0x140011f20`
- `0x140014528`
- `0x140016068`
- `0x140016b74`
- `0x140021650`
- `0x140023a60`
- `0x14008476c`
- `0x14008694c`
- `0x140086f64`
- `0x14008934c`
- `0x14008a284`
- `0x14009357c`
- `0x14009640c`
- `0x140097c00`
- `0x1400988d8`
- `0x14009a07c`
- `0x14009e498`
- `0x14009eb70`
- `0x1400a21fc`
- `0x1400a35a0`
- `0x1400a5058`
- `0x1400a70d0`
- `0x1400ec9f0`
- `0x1400ecb08`
- `0x1401010c8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400123b7`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400123b7`
- `ntoskrnl!ZwClose` at `0x140012391`
- `ntoskrnl!ZwClose` at `0x140012391`
- `ntoskrnl!IoFreeWorkItem` at `0x14001235a`
- `ntoskrnl!IoFreeWorkItem` at `0x140012372`
- `ntoskrnl!IoFreeWorkItem` at `0x14001235a`
- `ntoskrnl!IoFreeWorkItem` at `0x140012372`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001203a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012313`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001203a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012313`
- `winhvr!WinHvDeletePartition` at `0x14001220e`
- `winhvr!WinHvDeletePartition` at `0x14001220e`
- `winhvr!WinHvFinalizePartition` at `0x1400120b2`
- `winhvr!WinHvFinalizePartition` at `0x1400120b2`

## string_xrefs

- `0x140012104`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400121a6`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140012253`: `onecore\vm\vid\sys\driver\vidcreateclose.c`

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

  VsmmPartitionUninitialize(a1);
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
    VidDispatchInterfaceUninitialize((_QWORD *)a1);
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
    if ( v6 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v17[0] = v9;
      v21 = &v16;
      v16 = 1223;
      v23 = v17;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_140046254, 0, 0, 6, v18);
    }
    if ( (int)VidHvMemWithdrawAll(a1, v7, v8) < 0
      && (unsigned int)dword_140064110 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v16 = v10;
      v21 = v17;
      v17[0] = 1248;
      v23 = &v16;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140046211, 0, 0, 6, v18);
    }
    if ( (int)WinHvDeletePartition(*(_QWORD *)(a1 + 648)) < 0
      && (unsigned int)dword_140064110 > 2
      && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v19, "VidPartitionUninitialize");
      tlgCreate1Sz_char(v20, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
      v16 = v11;
      v21 = v17;
      v17[0] = 1255;
      v23 = &v16;
      v22 = 4;
      v24 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_1400461CE, 0, 0, 6, v18);
    }
    *(_QWORD *)(a1 + 648) = -1;
  }
  VidPdcNotifyPartitionTeardown(a1);
  VsmmMemTrackerPartitionCleanup(a1);
  VsmmFallbackMappingTeardown(a1 + 8432);
  VsmmFallbackMdlTeardown(a1 + 8408);
  VsmmPhuPartitionTeardown(a1);
  VsmmProcessTeardown(a1);
  VsmmMemPartTeardownPartition(a1);
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
0x140011f20  mov     [rsp-8+arg_8], rbx
0x140011f25  mov     [rsp-8+arg_10], rsi
0x140011f2a  push    rbp
0x140011f2b  push    rdi
0x140011f2c  push    r12
0x140011f2e  push    r14
0x140011f30  push    r15
0x140011f32  lea     rbp, [rsp-37h]
0x140011f37  sub     rsp, 0B0h
0x140011f3e  mov     rax, cs:__security_cookie
0x140011f45  xor     rax, rsp
0x140011f48  mov     [rbp+57h+var_30], rax
0x140011f4c  mov     rdi, rcx
0x140011f4f  call    VsmmPartitionUninitialize
0x140011f54  mov     eax, [rdi+10h]
0x140011f57  xor     esi, esi
0x140011f59  bt      rax, 0Fh
0x140011f5e  mov     r14d, 72446456h
0x140011f64  jb      short loc_140011FBF
0x140011f66  cmp     qword ptr [rdi+288h], 0FFFFFFFFFFFFFFFFh
0x140011f6e  jz      short loc_140011FBF
0x140011f70  cmp     [rdi+0C88h], rsi
0x140011f77  jz      short loc_140011FBF
0x140011f79  mov     ebx, [rdi+0C80h]
0x140011f7f  jmp     short loc_140011F98
0x140011f81  dec     ebx
0x140011f83  mov     eax, ebx
0x140011f85  imul    rcx, rax, 9D0h
0x140011f8c  add     rcx, [rdi+0C88h]
0x140011f93  call    VidVpDeleteFromHypervisor
0x140011f98  test    ebx, ebx
0x140011f9a  jnz     short loc_140011F81
0x140011f9c  mov     rcx, [rdi+0C88h]; P
0x140011fa3  mov     edx, r14d; Tag
0x140011fa6  call    cs:__imp_ExFreePoolWithTag
0x140011fad  nop     dword ptr [rax+rax+00h]
0x140011fb2  mov     [rdi+0C88h], rsi
0x140011fb9  mov     [rdi+0C80h], esi
0x140011fbf  mov     rcx, rdi
0x140011fc2  call    VidMessagePoolFree
0x140011fc7  lea     rcx, [rdi+650h]
0x140011fce  call    VidHvStatsMappingSetTeardown
0x140011fd3  mov     rcx, rdi
0x140011fd6  call    VidHvStateTeardown
0x140011fdb  lea     rcx, [rdi+0F58h]
0x140011fe2  call    VidReaderCounterTeardown
0x140011fe7  mov     rcx, [rdi+0D40h]; P
0x140011fee  test    rcx, rcx
0x140011ff1  jz      short loc_140012009
0x140011ff3  mov     edx, r14d; Tag
0x140011ff6  call    cs:__imp_ExFreePoolWithTag
0x140011ffd  nop     dword ptr [rax+rax+00h]
0x140012002  mov     [rdi+0D40h], rsi
0x140012009  mov     rcx, [rdi+0D50h]; P
0x140012010  test    rcx, rcx
0x140012013  jz      short loc_14001202B
0x140012015  mov     edx, r14d; Tag
0x140012018  call    cs:__imp_ExFreePoolWithTag
0x14001201f  nop     dword ptr [rax+rax+00h]
0x140012024  mov     [rdi+0D50h], rsi
0x14001202b  mov     rcx, [rdi+0D30h]; P
0x140012032  test    rcx, rcx
0x140012035  jz      short loc_14001204D
0x140012037  mov     edx, r14d; Tag
0x14001203a  call    cs:__imp_ExFreePoolWithTag
0x140012041  nop     dword ptr [rax+rax+00h]
0x140012046  mov     [rdi+0D30h], rsi
0x14001204d  mov     al, [rdi+340h]
0x140012053  test    al, al
0x140012055  jz      short loc_14001205F
0x140012057  mov     rcx, rdi
0x14001205a  call    VidDispatchInterfaceUninitialize
0x14001205f  mov     rcx, rdi
0x140012062  call    VidSynicPortPartitionTeardown
0x140012067  lea     rcx, [rdi+0CA0h]
0x14001206e  call    VidHandleTableUninitialize
0x140012073  lea     rcx, [rdi+0CC0h]
0x14001207a  call    VidHandleTableUninitialize
0x14001207f  mov     rcx, rdi
0x140012082  call    VsmmPhuHvPartitionTeardown
0x140012087  mov     rcx, rdi
0x14001208a  call    VidTriggerPartitionTeardown
0x14001208f  mov     eax, [rdi+10h]
0x140012092  bt      rax, 0Fh
0x140012097  jnb     short loc_1400120A1
0x140012099  mov     rcx, rdi
0x14001209c  call    VidExoVpTeardown
0x1400120a1  mov     rcx, [rdi+288h]
0x1400120a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400120ac  jz      loc_1400122BF
0x1400120b2  call    cs:__imp_WinHvFinalizePartition
0x1400120b9  nop     dword ptr [rax+rax+00h]
0x1400120be  mov     r15d, 100h
0x1400120c4  lea     rbx, dword_140064110
0x1400120cb  mov     r8d, eax
0x1400120ce  test    eax, eax
0x1400120d0  jns     loc_140012165
0x1400120d6  mov     ecx, cs:dword_140064110
0x1400120dc  cmp     ecx, 2
0x1400120df  jbe     loc_140012165
0x1400120e5  mov     edx, r15d
0x1400120e8  mov     rcx, rbx
0x1400120eb  call    _tlgKeywordOn
0x1400120f0  test    al, al
0x1400120f2  jz      short loc_140012165
0x1400120f4  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x1400120fb  lea     rcx, [rbp+57h+var_70]
0x1400120ff  call    _tlgCreate1Sz_char
0x140012104  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x14001210b  lea     rcx, [rbp+57h+var_60]
0x14001210f  call    _tlgCreate1Sz_char
0x140012114  lea     rax, [rbp+57h+var_A0]
0x140012118  mov     [rbp+57h+var_9C], r8d
0x14001211c  mov     [rbp+57h+var_50], rax
0x140012120  lea     rdx, dword_140046254
0x140012127  lea     rax, [rbp+57h+var_9C]
0x14001212b  mov     [rbp+57h+var_A0], 4C7h
0x140012132  mov     [rbp+57h+var_40], rax
0x140012136  xor     r9d, r9d
0x140012139  lea     rax, [rbp+57h+var_90]
0x14001213d  mov     [rbp+57h+var_48], 4
0x140012145  mov     [rsp+0D0h+var_A8], rax
0x14001214a  xor     r8d, r8d
0x14001214d  mov     rcx, rbx
0x140012150  mov     [rsp+0D0h+var_B0], 6
0x140012158  mov     [rbp+57h+var_38], 4
0x140012160  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012165  mov     rcx, rdi
0x140012168  call    VidHvMemWithdrawAll
0x14001216d  mov     r8d, eax
0x140012170  test    eax, eax
0x140012172  jns     loc_140012207
0x140012178  mov     ecx, cs:dword_140064110
0x14001217e  cmp     ecx, 2
0x140012181  jbe     loc_140012207
0x140012187  mov     rdx, r15
0x14001218a  mov     rcx, rbx
0x14001218d  call    _tlgKeywordOn
0x140012192  test    al, al
0x140012194  jz      short loc_140012207
0x140012196  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x14001219d  lea     rcx, [rbp+57h+var_70]
0x1400121a1  call    _tlgCreate1Sz_char
0x1400121a6  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400121ad  lea     rcx, [rbp+57h+var_60]
0x1400121b1  call    _tlgCreate1Sz_char
0x1400121b6  lea     rax, [rbp+57h+var_9C]
0x1400121ba  mov     [rbp+57h+var_A0], r8d
0x1400121be  mov     [rbp+57h+var_50], rax
0x1400121c2  lea     rdx, byte_140046211
0x1400121c9  lea     rax, [rbp+57h+var_A0]
0x1400121cd  mov     [rbp+57h+var_9C], 4E0h
0x1400121d4  mov     [rbp+57h+var_40], rax
0x1400121d8  xor     r9d, r9d
0x1400121db  lea     rax, [rbp+57h+var_90]
0x1400121df  mov     [rbp+57h+var_48], 4
0x1400121e7  mov     [rsp+0D0h+var_A8], rax
0x1400121ec  xor     r8d, r8d
0x1400121ef  mov     rcx, rbx
0x1400121f2  mov     [rsp+0D0h+var_B0], 6
0x1400121fa  mov     [rbp+57h+var_38], 4
0x140012202  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012207  mov     rcx, [rdi+288h]
0x14001220e  call    cs:__imp_WinHvDeletePartition
0x140012215  nop     dword ptr [rax+rax+00h]
0x14001221a  mov     r8d, eax
0x14001221d  test    eax, eax
0x14001221f  jns     loc_1400122B4
0x140012225  mov     ecx, cs:dword_140064110
0x14001222b  cmp     ecx, 2
0x14001222e  jbe     loc_1400122B4
0x140012234  mov     rdx, r15
0x140012237  mov     rcx, rbx
0x14001223a  call    _tlgKeywordOn
0x14001223f  test    al, al
0x140012241  jz      short loc_1400122B4
0x140012243  lea     rdx, aVidpartitionun; "VidPartitionUninitialize"
0x14001224a  lea     rcx, [rbp+57h+var_70]
0x14001224e  call    _tlgCreate1Sz_char
0x140012253  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x14001225a  lea     rcx, [rbp+57h+var_60]
0x14001225e  call    _tlgCreate1Sz_char
0x140012263  lea     rax, [rbp+57h+var_9C]
0x140012267  mov     [rbp+57h+var_A0], r8d
0x14001226b  mov     [rbp+57h+var_50], rax
0x14001226f  lea     rdx, word_1400461CE
0x140012276  lea     rax, [rbp+57h+var_A0]
0x14001227a  mov     [rbp+57h+var_9C], 4E7h
0x140012281  mov     [rbp+57h+var_40], rax
0x140012285  xor     r9d, r9d
0x140012288  lea     rax, [rbp+57h+var_90]
0x14001228c  mov     [rbp+57h+var_48], 4
0x140012294  mov     [rsp+0D0h+var_A8], rax
0x140012299  xor     r8d, r8d
0x14001229c  mov     rcx, rbx
0x14001229f  mov     [rsp+0D0h+var_B0], 6
0x1400122a7  mov     [rbp+57h+var_38], 4
0x1400122af  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400122b4  mov     qword ptr [rdi+288h], 0FFFFFFFFFFFFFFFFh
0x1400122bf  mov     rcx, rdi
0x1400122c2  call    VidPdcNotifyPartitionTeardown
0x1400122c7  mov     rcx, rdi
0x1400122ca  call    VsmmMemTrackerPartitionCleanup
0x1400122cf  lea     rcx, [rdi+20F0h]
0x1400122d6  call    VsmmFallbackMappingTeardown
0x1400122db  lea     rcx, [rdi+20D8h]
0x1400122e2  call    VsmmFallbackMdlTeardown
0x1400122e7  mov     rcx, rdi
0x1400122ea  call    VsmmPhuPartitionTeardown
0x1400122ef  mov     rcx, rdi
0x1400122f2  call    VsmmProcessTeardown
0x1400122f7  mov     rcx, rdi
0x1400122fa  call    VsmmMemPartTeardownPartition
0x1400122ff  mov     rcx, rdi
0x140012302  call    VidResourcePartitionPartitionTeardown
0x140012307  mov     rcx, [rdi+70h]; P
0x14001230b  test    rcx, rcx
0x14001230e  jz      short loc_140012326
0x140012310  mov     edx, r14d; Tag
0x140012313  call    cs:__imp_ExFreePoolWithTag
0x14001231a  nop     dword ptr [rax+rax+00h]
0x14001231f  mov     [rdi+70h], rsi
0x140012323  mov     [rdi+68h], esi
0x140012326  lea     rbx, [rdi+5C0h]
0x14001232d  xor     edx, edx
0x14001232f  mov     rcx, rbx; FastMutex
0x140012332  lea     r8, [rdi+608h]
0x140012339  call    VidStatisticsDataUnMap
0x14001233e  mov     rcx, rbx; FastMutex
0x140012341  call    VidStatisticsDataTeardown
0x140012346  mov     rcx, rdi
0x140012349  call    VidHypercallDoorbellFree
0x14001234e  mov     rcx, [rdi+2FE0h]; IoWorkItem
0x140012355  test    rcx, rcx
0x140012358  jz      short loc_140012366
0x14001235a  call    cs:__imp_IoFreeWorkItem
0x140012361  nop     dword ptr [rax+rax+00h]
0x140012366  mov     rcx, [rdi+2F80h]; IoWorkItem
0x14001236d  test    rcx, rcx
0x140012370  jz      short loc_140012385
0x140012372  call    cs:__imp_IoFreeWorkItem
0x140012379  nop     dword ptr [rax+rax+00h]
0x14001237e  mov     [rdi+2F80h], rsi
0x140012385  mov     rcx, [rdi+2808h]; Handle
0x14001238c  test    rcx, rcx
0x14001238f  jz      short loc_1400123A4
0x140012391  call    cs:__imp_ZwClose
0x140012398  nop     dword ptr [rax+rax+00h]
0x14001239d  mov     [rdi+2808h], rsi
0x1400123a4  cmp     [rdi+21D1h], sil
0x1400123ab  jnz     short loc_1400123CC
0x1400123ad  mov     rcx, [rdi+2800h]; Object
0x1400123b4  mov     edx, r14d; Tag
0x1400123b7  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400123be  nop     dword ptr [rax+rax+00h]
0x1400123c3  mov     [rdi+2800h], rsi
0x1400123ca  jmp     short loc_1400123D3
0x1400123cc  mov     [rdi+21D1h], sil
0x1400123d3  mov     rcx, [rbp+57h+var_30]
0x1400123d7  xor     rcx, rsp; StackCookie
0x1400123da  call    __security_check_cookie
0x1400123df  lea     r11, [rsp+0D0h+var_20]
0x1400123e7  mov     rbx, [r11+38h]
0x1400123eb  mov     rsi, [r11+40h]
0x1400123ef  mov     rsp, r11
0x1400123f2  pop     r15
0x1400123f4  pop     r14
0x1400123f6  pop     r12
0x1400123f8  pop     rdi
0x1400123f9  pop     rbp
0x1400123fa  retn
```
