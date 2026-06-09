# VidResourcePartitionStateKsrPersist

- ea: `0x1400935b8`
- end: `0x140093b33`
- name: `VidResourcePartitionStateKsrPersist`
- size: `1403`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400cf5d4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007234`
- `0x1400087b8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400935b8`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400936b4`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400936b4`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140093a05`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140093a05`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400939ec`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400939ec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400937b6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400937b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093a16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093a2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093a16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093a2f`
- `ntoskrnl!ExAllocatePool2` at `0x1400938fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400938fa`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400938d9`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x140093a6e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400938d9`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x140093a6e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemory` at `0x140093a8e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemory` at `0x140093a8e`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionStateKsrPersist(__int64 a1, _QWORD *a2)
{
  void *v2; // r12
  char *v3; // rbx
  char v4; // di
  char *v5; // rcx
  _QWORD *v6; // r14
  _QWORD *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  _QWORD *v12; // rcx
  __int64 v13; // r15
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  struct _MDL *PagesForMdl; // rax
  struct _MDL *v17; // rsi
  int v18; // ebx
  const GUID *v19; // r9
  __int64 *v20; // rcx
  int v21; // r8d
  unsigned __int8 *v22; // rdx
  __int64 *v23; // rax
  _QWORD *v24; // rax
  int v25; // r8d
  unsigned __int64 v26; // rax
  _QWORD *v27; // rbx
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  __int64 Pool2; // rax
  __int16 *v31; // rdx
  int v32; // r8d
  __int64 *v33; // rax
  unsigned int v35; // [rsp+34h] [rbp-A5h] BYREF
  int v36; // [rsp+38h] [rbp-A1h] BYREF
  int v37; // [rsp+3Ch] [rbp-9Dh] BYREF
  __int64 v38; // [rsp+40h] [rbp-99h] BYREF
  _QWORD *v39; // [rsp+48h] [rbp-91h] BYREF
  char *v40; // [rsp+50h] [rbp-89h]
  struct _EVENT_DATA_DESCRIPTOR v41[2]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v42[16]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE v43[16]; // [rsp+90h] [rbp-49h] BYREF
  int *v44; // [rsp+A0h] [rbp-39h]
  __int64 v45; // [rsp+A8h] [rbp-31h]
  int *v46; // [rsp+B0h] [rbp-29h]
  __int64 v47; // [rsp+B8h] [rbp-21h]
  __int64 *v48; // [rsp+C0h] [rbp-19h]
  __int64 v49; // [rsp+C8h] [rbp-11h]
  __int64 *v50; // [rsp+D0h] [rbp-9h]
  __int64 v51; // [rsp+D8h] [rbp-1h]

  v2 = 0;
  v3 = (char *)VidDeviceExtension + 2200;
  v39 = a2;
  v4 = 0;
  v35 = 0;
  v5 = (char *)VidDeviceExtension + 2200;
  v6 = 0;
  v40 = (char *)VidDeviceExtension + 2200;
  *a2 = 0;
  VidPushLockAcquireExclusive(v5);
  v10 = *((_QWORD *)v3 + 2);
  v11 = (unsigned __int64)(v3 + 8);
  if ( (v10 & 1) != 0 )
  {
    if ( v10 == 1 )
    {
LABEL_55:
      v17 = 0;
      v18 = -1073741275;
      goto LABEL_41;
    }
    v12 = (_QWORD *)(v10 ^ (v11 | 1));
  }
  else
  {
    v12 = (_QWORD *)v10;
  }
  v13 = 0;
  if ( !v12 )
    goto LABEL_55;
  do
  {
    v14 = (_QWORD *)v12[1];
    ++v13;
    if ( v14 )
    {
      v7 = (_QWORD *)*v14;
      if ( *v14 )
      {
        do
        {
          v12 = v7;
          v7 = (_QWORD *)*v7;
        }
        while ( v7 );
      }
      else
      {
        v12 = (_QWORD *)v12[1];
      }
    }
    else
    {
      do
      {
        v15 = v12;
        v12 = (_QWORD *)(v12[2] & 0xFFFFFFFFFFFFFFFCuLL);
      }
      while ( v12 && (_QWORD *)*v12 != v15 );
    }
  }
  while ( v12 );
  if ( !v13 )
    goto LABEL_55;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, 16 * v13 + 8, MmCached, 0x14u);
  v9 = 0;
  v17 = PagesForMdl;
  if ( !PagesForMdl )
  {
    v8 = 3221225626LL;
    v18 = -1073741670;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v42, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v36 = 2154;
      v44 = &v36;
      v20 = (__int64 *)&v39;
      v37 = v21;
      v46 = &v37;
      v22 = (unsigned __int8 *)word_140047E5A;
      v23 = &v38;
      v38 = 16 * v13 + 8;
      v39 = (_QWORD *)v13;
LABEL_19:
      v50 = v20;
      v48 = v23;
      v51 = 8;
      v49 = 8;
      v47 = 4;
      v45 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, v22, 0, v19, 8u, v41);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v24 = MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000010u);
  v6 = v24;
  if ( v24 )
  {
    *v24 = 0;
    v26 = *(_QWORD *)(v11 + 8);
    if ( (v26 & 1) == 0 )
      goto LABEL_27;
    if ( v26 != 1 )
    {
      v27 = (_QWORD *)(v26 ^ (v11 | 1));
      while ( v27 )
      {
        *(_OWORD *)&v6[2 * (*v6)++ + 1] = *(_OWORD *)(v27 - 3);
        v26 = v27[1];
        if ( v26 )
        {
          v28 = *(_QWORD **)v26;
          if ( *(_QWORD *)v26 )
          {
            do
            {
              v27 = v28;
              v28 = (_QWORD *)*v28;
            }
            while ( v28 );
          }
          else
          {
LABEL_27:
            v27 = (_QWORD *)v26;
          }
        }
        else
        {
          do
          {
            v29 = v27;
            v27 = (_QWORD *)(v27[2] & 0xFFFFFFFFFFFFFFFCuLL);
          }
          while ( v27 && (_QWORD *)*v27 != v29 );
        }
      }
    }
    KsrMdlToMemoryRuns(v17, 0, 0, &v35);
    Pool2 = ExAllocatePool2(256, 8LL * v35, 1917084758);
    v2 = (void *)Pool2;
    if ( Pool2 )
    {
      KsrMdlToMemoryRuns(v17, Pool2, v35, &v35);
      v18 = KsrPersistMemory(VSMM_KSR_GLOBAL_STATE_GUID, v2, v35, v39);
      if ( v18 >= 0 )
      {
        v4 = 1;
        v18 = 0;
        goto LABEL_41;
      }
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
LABEL_40:
        v4 = 0;
        goto LABEL_41;
      }
      tlgCreate1Sz_char(v42, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      LODWORD(v38) = 2235;
      v44 = (int *)&v38;
      v31 = word_140047E12;
      v37 = v18;
      v46 = &v37;
      v36 = v35;
      v33 = (__int64 *)&v36;
    }
    else
    {
      v8 = 3221225626LL;
      v18 = -1073741670;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_40;
      tlgCreate1Sz_char(v42, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v37 = 2215;
      v44 = &v37;
      v31 = word_140047DCA;
      v36 = v32;
      v46 = &v36;
      LODWORD(v38) = v35;
      v33 = &v38;
    }
    v48 = v33;
    v49 = 4;
    v47 = 4;
    v45 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)v31, 0, 0, 7u, v41);
    goto LABEL_40;
  }
  v8 = 3221225626LL;
  v18 = -1073741670;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v42, "VidResourcePartitionStateKsrPersist");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    v37 = 2172;
    v44 = &v37;
    v20 = &v38;
    v36 = v25;
    v46 = &v36;
    v22 = (unsigned __int8 *)&byte_140047EC7;
    v23 = (__int64 *)&v39;
    v39 = (_QWORD *)(16 * v13 + 8);
    v38 = v13;
    v19 = 0;
    goto LABEL_19;
  }
LABEL_41:
  VidPushLockRelease(v40, v7, v8, v9);
  if ( v6 )
    MmUnmapLockedPages(v6, v17);
  if ( v17 )
  {
    if ( !v4 )
      MmFreePagesFromMdl(v17);
    ExFreePoolWithTag(v17, 0);
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0x72446456u);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400935b8  push    rbp
0x1400935ba  push    rbx
0x1400935bb  push    rsi
0x1400935bc  push    rdi
0x1400935bd  push    r12
0x1400935bf  push    r13
0x1400935c1  push    r14
0x1400935c3  push    r15
0x1400935c5  lea     rbp, [rsp-1Fh]
0x1400935ca  sub     rsp, 0F8h
0x1400935d1  mov     rax, cs:__security_cookie
0x1400935d8  xor     rax, rsp
0x1400935db  mov     [rbp+57h+var_50], rax
0x1400935df  mov     rbx, cs:VidDeviceExtension
0x1400935e6  xor     r12d, r12d
0x1400935e9  add     rbx, 898h
0x1400935f0  mov     [rsp+130h+var_E8], rdx
0x1400935f5  xor     dil, dil
0x1400935f8  mov     [rsp+130h+var_FC], r12d
0x1400935fd  mov     rcx, rbx
0x140093600  mov     [rsp+130h+var_100], dil
0x140093605  xor     r14d, r14d
0x140093608  mov     [rsp+130h+var_E0], rbx
0x14009360d  mov     [rdx], r12
0x140093610  call    VidPushLockAcquireExclusive
0x140093615  mov     rax, [rbx+10h]
0x140093619  add     rbx, 8
0x14009361d  test    al, 1
0x14009361f  jz      short loc_140093637
0x140093621  cmp     rax, 1
0x140093625  jz      loc_140093B27
0x14009362b  mov     rcx, rbx
0x14009362e  or      rcx, 1
0x140093632  xor     rcx, rax
0x140093635  jmp     short loc_14009363A
0x140093637  mov     rcx, rax
0x14009363a  xor     r15d, r15d
0x14009363d  test    rcx, rcx
0x140093640  jz      loc_140093B27
0x140093646  mov     rax, [rcx+8]
0x14009364a  inc     r15
0x14009364d  test    rax, rax
0x140093650  jz      short loc_140093674
0x140093652  mov     rdx, [rax]
0x140093655  test    rdx, rdx
0x140093658  jz      short loc_14009366A
0x14009365a  mov     rax, [rdx]
0x14009365d  mov     rcx, rdx
0x140093660  mov     rdx, rax
0x140093663  test    rax, rax
0x140093666  jnz     short loc_14009365A
0x140093668  jmp     short loc_140093681
0x14009366a  mov     rcx, rax
0x14009366d  jmp     short loc_140093681
0x14009366f  cmp     [rcx], rax
0x140093672  jz      short loc_140093681
0x140093674  mov     rax, rcx
0x140093677  mov     rcx, [rcx+10h]
0x14009367b  and     rcx, 0FFFFFFFFFFFFFFFCh; LowAddress
0x14009367f  jnz     short loc_14009366F
0x140093681  test    rcx, rcx
0x140093684  jnz     short loc_140093646
0x140093686  test    r15, r15
0x140093689  jz      loc_140093B27
0x14009368f  mov     r13, r15
0x140093692  mov     [rsp+130h+Flags], 14h; Flags
0x14009369a  shl     r13, 4
0x14009369e  xor     r8d, r8d; SkipBytes
0x1400936a1  add     r13, 8
0x1400936a5  mov     [rsp+130h+CacheType], 1; CacheType
0x1400936ad  mov     r9, r13; TotalBytes
0x1400936b0  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x1400936b4  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400936bb  nop     dword ptr [rax+rax+00h]
0x1400936c0  xor     r9d, r9d; RequestedAddress
0x1400936c3  mov     rsi, rax
0x1400936c6  test    rax, rax
0x1400936c9  jnz     loc_1400937A0
0x1400936cf  mov     eax, cs:dword_140064110
0x1400936d5  mov     r8d, 0C000009Ah
0x1400936db  mov     ebx, r8d
0x1400936de  cmp     eax, 2
0x1400936e1  jbe     loc_1400939D7
0x1400936e7  mov     edx, 100h
0x1400936ec  lea     rcx, dword_140064110
0x1400936f3  call    _tlgKeywordOn
0x1400936f8  test    al, al
0x1400936fa  jz      loc_1400939D7
0x140093700  lea     rdx, aVidresourcepar_2; "VidResourcePartitionStateKsrPersist"
0x140093707  lea     rcx, [rbp+57h+var_B0]
0x14009370b  call    _tlgCreate1Sz_char
0x140093710  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093717  lea     rcx, [rbp+57h+var_A0]
0x14009371b  call    _tlgCreate1Sz_char
0x140093720  lea     rax, [rsp+130h+var_F8]
0x140093725  mov     [rsp+130h+var_F8], 86Ah
0x14009372d  mov     [rbp+57h+var_90], rax
0x140093731  lea     rcx, [rsp+130h+var_E8]
0x140093736  lea     rax, [rsp+130h+var_F4]
0x14009373b  mov     [rsp+130h+var_F4], r8d
0x140093740  mov     [rbp+57h+var_80], rax
0x140093744  lea     rdx, word_140047E5A
0x14009374b  lea     rax, [rsp+130h+var_F0]
0x140093750  mov     [rsp+130h+var_F0], r13
0x140093755  mov     [rsp+130h+var_E8], r15
0x14009375a  mov     [rbp+57h+var_60], rcx
0x14009375e  xor     r8d, r8d
0x140093761  lea     rcx, [rbp+57h+var_D0]
0x140093765  mov     [rbp+57h+var_70], rax
0x140093769  mov     eax, 8
0x14009376e  mov     qword ptr [rsp+130h+Flags], rcx
0x140093773  lea     rcx, dword_140064110
0x14009377a  mov     [rsp+130h+CacheType], eax
0x14009377e  mov     [rbp+57h+var_58], rax
0x140093782  mov     [rbp+57h+var_68], rax
0x140093786  mov     [rbp+57h+var_78], 4
0x14009378e  mov     [rbp+57h+var_88], 4
0x140093796  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009379b  jmp     loc_1400939D7
0x1400937a0  xor     edx, edx; AccessMode
0x1400937a2  mov     [rsp+130h+Flags], 40000010h; Priority
0x1400937aa  mov     rcx, rsi; MemoryDescriptorList
0x1400937ad  mov     [rsp+130h+CacheType], r9d; BugCheckOnFailure
0x1400937b2  lea     r8d, [rdx+1]; CacheType
0x1400937b6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400937bd  nop     dword ptr [rax+rax+00h]
0x1400937c2  mov     r14, rax
0x1400937c5  test    rax, rax
0x1400937c8  jnz     loc_140093861
0x1400937ce  mov     eax, cs:dword_140064110
0x1400937d4  mov     r8d, 0C000009Ah
0x1400937da  mov     ebx, r8d
0x1400937dd  cmp     eax, 2
0x1400937e0  jbe     loc_1400939D7
0x1400937e6  mov     edx, 100h
0x1400937eb  lea     rcx, dword_140064110
0x1400937f2  call    _tlgKeywordOn
0x1400937f7  test    al, al
0x1400937f9  jz      loc_1400939D7
0x1400937ff  lea     rdx, aVidresourcepar_2; "VidResourcePartitionStateKsrPersist"
0x140093806  lea     rcx, [rbp+57h+var_B0]
0x14009380a  call    _tlgCreate1Sz_char
0x14009380f  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093816  lea     rcx, [rbp+57h+var_A0]
0x14009381a  call    _tlgCreate1Sz_char
0x14009381f  lea     rax, [rsp+130h+var_F4]
0x140093824  mov     [rsp+130h+var_F4], 87Ch
0x14009382c  mov     [rbp+57h+var_90], rax
0x140093830  lea     rcx, [rsp+130h+var_F0]
0x140093835  lea     rax, [rsp+130h+var_F8]
0x14009383a  mov     [rsp+130h+var_F8], r8d
0x14009383f  mov     [rbp+57h+var_80], rax
0x140093843  lea     rdx, byte_140047EC7
0x14009384a  lea     rax, [rsp+130h+var_E8]
0x14009384f  mov     [rsp+130h+var_E8], r13
0x140093854  mov     [rsp+130h+var_F0], r15
0x140093859  xor     r9d, r9d
0x14009385c  jmp     loc_14009375A
0x140093861  mov     [rax], r12
0x140093864  mov     rax, [rbx+8]
0x140093868  test    al, 1
0x14009386a  jz      short loc_14009387B
0x14009386c  cmp     rax, 1
0x140093870  jz      short loc_1400938CC
0x140093872  or      rbx, 1
0x140093876  xor     rbx, rax
0x140093879  jmp     short loc_1400938C7
0x14009387b  mov     rbx, rax
0x14009387e  jmp     short loc_1400938C7
0x140093880  mov     rax, [r14]
0x140093883  movups  xmm0, xmmword ptr [rbx-18h]
0x140093887  add     rax, rax
0x14009388a  movdqu  xmmword ptr [r14+rax*8+8], xmm0
0x140093891  inc     qword ptr [r14]
0x140093894  mov     rax, [rbx+8]
0x140093898  test    rax, rax
0x14009389b  jz      short loc_1400938BA
0x14009389d  mov     rcx, [rax]
0x1400938a0  test    rcx, rcx
0x1400938a3  jz      short loc_14009387B
0x1400938a5  mov     rax, [rcx]
0x1400938a8  mov     rbx, rcx
0x1400938ab  mov     rcx, rax
0x1400938ae  test    rax, rax
0x1400938b1  jnz     short loc_1400938A5
0x1400938b3  jmp     short loc_1400938C7
0x1400938b5  cmp     [rbx], rax
0x1400938b8  jz      short loc_1400938C7
0x1400938ba  mov     rax, rbx
0x1400938bd  mov     rbx, [rbx+10h]
0x1400938c1  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400938c5  jnz     short loc_1400938B5
0x1400938c7  test    rbx, rbx
0x1400938ca  jnz     short loc_140093880
0x1400938cc  lea     r9, [rsp+130h+var_FC]
0x1400938d1  xor     r8d, r8d
0x1400938d4  xor     edx, edx
0x1400938d6  mov     rcx, rsi
0x1400938d9  call    cs:__imp_KsrMdlToMemoryRuns
0x1400938e0  nop     dword ptr [rax+rax+00h]
0x1400938e5  mov     edx, [rsp+130h+var_FC]
0x1400938e9  mov     edi, 100h
0x1400938ee  shl     rdx, 3
0x1400938f2  mov     r8d, 72446456h
0x1400938f8  mov     ecx, edi
0x1400938fa  call    cs:__imp_ExAllocatePool2
0x140093901  nop     dword ptr [rax+rax+00h]
0x140093906  mov     r12, rax
0x140093909  test    rax, rax
0x14009390c  jnz     loc_140093A5E
0x140093912  mov     ecx, cs:dword_140064110
0x140093918  mov     r8d, 0C000009Ah
0x14009391e  mov     ebx, r8d
0x140093921  cmp     ecx, 2
0x140093924  jbe     loc_1400939D2
0x14009392a  mov     edx, edi
0x14009392c  lea     rcx, dword_140064110
0x140093933  call    _tlgKeywordOn
0x140093938  test    al, al
0x14009393a  jz      loc_1400939D2
0x140093940  lea     rdx, aVidresourcepar_2; "VidResourcePartitionStateKsrPersist"
0x140093947  lea     rcx, [rbp+57h+var_B0]
0x14009394b  call    _tlgCreate1Sz_char
0x140093950  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093957  lea     rcx, [rbp+57h+var_A0]
0x14009395b  call    _tlgCreate1Sz_char
0x140093960  lea     rax, [rsp+130h+var_F4]
0x140093965  mov     [rsp+130h+var_F4], 8A7h
0x14009396d  mov     [rbp+57h+var_90], rax
0x140093971  lea     rdx, word_140047DCA
0x140093978  lea     rax, [rsp+130h+var_F8]
0x14009397d  mov     [rsp+130h+var_F8], r8d
0x140093982  mov     [rbp+57h+var_80], rax
0x140093986  mov     eax, [rsp+130h+var_FC]
0x14009398a  mov     dword ptr [rsp+130h+var_F0], eax
0x14009398e  lea     rax, [rsp+130h+var_F0]
0x140093993  mov     [rbp+57h+var_70], rax
0x140093997  lea     rcx, dword_140064110
0x14009399e  lea     rax, [rbp+57h+var_D0]
0x1400939a2  mov     [rbp+57h+var_68], 4
0x1400939aa  mov     qword ptr [rsp+130h+Flags], rax
0x1400939af  xor     r9d, r9d
0x1400939b2  xor     r8d, r8d
0x1400939b5  mov     [rsp+130h+CacheType], 7
0x1400939bd  mov     [rbp+57h+var_78], 4
0x1400939c5  mov     [rbp+57h+var_88], 4
0x1400939cd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400939d2  mov     dil, [rsp+130h+var_100]
0x1400939d7  mov     rcx, [rsp+130h+var_E0]
0x1400939dc  call    VidPushLockRelease
0x1400939e1  test    r14, r14
0x1400939e4  jz      short loc_1400939F8
0x1400939e6  mov     rdx, rsi; MemoryDescriptorList
0x1400939e9  mov     rcx, r14; BaseAddress
0x1400939ec  call    cs:__imp_MmUnmapLockedPages
0x1400939f3  nop     dword ptr [rax+rax+00h]
0x1400939f8  test    rsi, rsi
0x1400939fb  jz      short loc_140093A22
0x1400939fd  test    dil, dil
0x140093a00  jnz     short loc_140093A11
0x140093a02  mov     rcx, rsi; MemoryDescriptorList
0x140093a05  call    cs:__imp_MmFreePagesFromMdl
0x140093a0c  nop     dword ptr [rax+rax+00h]
0x140093a11  xor     edx, edx; Tag
0x140093a13  mov     rcx, rsi; P
0x140093a16  call    cs:__imp_ExFreePoolWithTag
0x140093a1d  nop     dword ptr [rax+rax+00h]
0x140093a22  test    r12, r12
0x140093a25  jz      short loc_140093A3B
0x140093a27  mov     edx, 72446456h; Tag
0x140093a2c  mov     rcx, r12; P
0x140093a2f  call    cs:__imp_ExFreePoolWithTag
0x140093a36  nop     dword ptr [rax+rax+00h]
0x140093a3b  mov     eax, ebx
0x140093a3d  mov     rcx, [rbp+57h+var_50]
0x140093a41  xor     rcx, rsp; StackCookie
0x140093a44  call    __security_check_cookie
0x140093a49  add     rsp, 0F8h
0x140093a50  pop     r15
0x140093a52  pop     r14
0x140093a54  pop     r13
0x140093a56  pop     r12
0x140093a58  pop     rdi
0x140093a59  pop     rsi
0x140093a5a  pop     rbx
0x140093a5b  pop     rbp
0x140093a5c  retn
0x140093a5e  mov     r8d, [rsp+130h+var_FC]
0x140093a63  lea     r9, [rsp+130h+var_FC]
0x140093a68  mov     rdx, r12
0x140093a6b  mov     rcx, rsi
0x140093a6e  call    cs:__imp_KsrMdlToMemoryRuns
0x140093a75  nop     dword ptr [rax+rax+00h]
0x140093a7a  mov     r9, [rsp+130h+var_E8]
0x140093a7f  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x140093a86  mov     r8d, [rsp+130h+var_FC]
0x140093a8b  mov     rdx, r12
0x140093a8e  call    cs:__imp_KsrPersistMemory
0x140093a95  nop     dword ptr [rax+rax+00h]
0x140093a9a  mov     ebx, eax
  ... truncated ...
```
