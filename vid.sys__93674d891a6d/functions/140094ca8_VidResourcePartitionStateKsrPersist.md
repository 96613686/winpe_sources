# VidResourcePartitionStateKsrPersist

- ea: `0x140094ca8`
- end: `0x140095223`
- name: `VidResourcePartitionStateKsrPersist`
- size: `1403`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400d1ed4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x1400071a4`
- `0x140007dbc`
- `0x14000a010`
- `0x140021c60`
- `0x140094ca8`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140094da4`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x140094da4`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400950f5`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400950f5`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400950dc`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400950dc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140094ea6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140094ea6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095106`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009511f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140095106`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009511f`
- `ntoskrnl!ExAllocatePool2` at `0x140094fea`
- `ntoskrnl!ExAllocatePool2` at `0x140094fea`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x140094fc9`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x14009515e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x140094fc9`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x14009515e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemory` at `0x14009517e`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemory` at `0x14009517e`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionStateKsrPersist(__int64 a1, _QWORD *a2)
{
  void *v2; // r12
  char *v3; // rbx
  char v4; // di
  char *v5; // rcx
  _QWORD *v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // r15
  _QWORD **v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rax
  struct _MDL *PagesForMdl; // rax
  struct _MDL *v15; // rsi
  int v16; // ebx
  const GUID *v17; // r9
  __int64 *v18; // rcx
  int v19; // r8d
  unsigned __int8 *v20; // rdx
  __int64 *v21; // rax
  _QWORD *v22; // rax
  int v23; // r8d
  unsigned __int64 v24; // rax
  _QWORD *v25; // rbx
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  __int64 Pool2; // rax
  unsigned __int8 *v29; // rdx
  int v30; // r8d
  __int64 *v31; // rax
  unsigned int v33; // [rsp+34h] [rbp-A5h] BYREF
  int v34; // [rsp+38h] [rbp-A1h] BYREF
  int v35; // [rsp+3Ch] [rbp-9Dh] BYREF
  __int64 v36; // [rsp+40h] [rbp-99h] BYREF
  __int64 v37; // [rsp+48h] [rbp-91h] BYREF
  char *v38; // [rsp+50h] [rbp-89h]
  struct _EVENT_DATA_DESCRIPTOR v39[2]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v40[16]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE v41[16]; // [rsp+90h] [rbp-49h] BYREF
  int *v42; // [rsp+A0h] [rbp-39h]
  __int64 v43; // [rsp+A8h] [rbp-31h]
  int *v44; // [rsp+B0h] [rbp-29h]
  __int64 v45; // [rsp+B8h] [rbp-21h]
  __int64 *v46; // [rsp+C0h] [rbp-19h]
  __int64 v47; // [rsp+C8h] [rbp-11h]
  __int64 *v48; // [rsp+D0h] [rbp-9h]
  __int64 v49; // [rsp+D8h] [rbp-1h]

  v2 = 0;
  v3 = (char *)VidDeviceExtension + 2200;
  v37 = (__int64)a2;
  v4 = 0;
  v33 = 0;
  v5 = (char *)VidDeviceExtension + 2200;
  v6 = 0;
  v38 = (char *)VidDeviceExtension + 2200;
  *a2 = 0;
  VidPushLockAcquireExclusive(v5);
  v7 = *((_QWORD *)v3 + 2);
  v8 = (unsigned __int64)(v3 + 8);
  if ( (v7 & 1) != 0 )
  {
    if ( v7 == 1 )
    {
LABEL_55:
      v15 = 0;
      v16 = -1073741275;
      goto LABEL_41;
    }
    v9 = (_QWORD *)(v7 ^ (v8 | 1));
  }
  else
  {
    v9 = (_QWORD *)v7;
  }
  v10 = 0;
  if ( !v9 )
    goto LABEL_55;
  do
  {
    v11 = (_QWORD **)v9[1];
    ++v10;
    if ( v11 )
    {
      v12 = *v11;
      if ( *v11 )
      {
        do
        {
          v9 = v12;
          v12 = (_QWORD *)*v12;
        }
        while ( v12 );
      }
      else
      {
        v9 = (_QWORD *)v9[1];
      }
    }
    else
    {
      do
      {
        v13 = v9;
        v9 = (_QWORD *)(v9[2] & 0xFFFFFFFFFFFFFFFCuLL);
      }
      while ( v9 && (_QWORD *)*v9 != v13 );
    }
  }
  while ( v9 );
  if ( !v10 )
    goto LABEL_55;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, 16 * v10 + 8, MmCached, 0x14u);
  v15 = PagesForMdl;
  if ( !PagesForMdl )
  {
    v16 = -1073741670;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v40, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v34 = 2250;
      v42 = &v34;
      v18 = &v37;
      v35 = v19;
      v44 = &v35;
      v20 = (unsigned __int8 *)&dword_140048354;
      v21 = &v36;
      v36 = 16 * v10 + 8;
      v37 = v10;
LABEL_19:
      v48 = v18;
      v46 = v21;
      v49 = 8;
      v47 = 8;
      v45 = 4;
      v43 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, v20, 0, v17, 8u, v39);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v22 = MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000010u);
  v6 = v22;
  if ( v22 )
  {
    *v22 = 0;
    v24 = *(_QWORD *)(v8 + 8);
    if ( (v24 & 1) == 0 )
      goto LABEL_27;
    if ( v24 != 1 )
    {
      v25 = (_QWORD *)(v24 ^ (v8 | 1));
      while ( v25 )
      {
        *(_OWORD *)&v6[2 * (*v6)++ + 1] = *(_OWORD *)(v25 - 3);
        v24 = v25[1];
        if ( v24 )
        {
          v26 = *(_QWORD **)v24;
          if ( *(_QWORD *)v24 )
          {
            do
            {
              v25 = v26;
              v26 = (_QWORD *)*v26;
            }
            while ( v26 );
          }
          else
          {
LABEL_27:
            v25 = (_QWORD *)v24;
          }
        }
        else
        {
          do
          {
            v27 = v25;
            v25 = (_QWORD *)(v25[2] & 0xFFFFFFFFFFFFFFFCuLL);
          }
          while ( v25 && (_QWORD *)*v25 != v27 );
        }
      }
    }
    KsrMdlToMemoryRuns(v15, 0, 0, &v33);
    Pool2 = ExAllocatePool2(256, 8LL * v33, 1917084758);
    v2 = (void *)Pool2;
    if ( Pool2 )
    {
      KsrMdlToMemoryRuns(v15, Pool2, v33, &v33);
      v16 = KsrPersistMemory(VSMM_KSR_GLOBAL_STATE_GUID, v2, v33, v37);
      if ( v16 >= 0 )
      {
        v4 = 1;
        v16 = 0;
        goto LABEL_41;
      }
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
LABEL_40:
        v4 = 0;
        goto LABEL_41;
      }
      tlgCreate1Sz_char(v40, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      LODWORD(v36) = 2331;
      v42 = (int *)&v36;
      v29 = (unsigned __int8 *)&byte_140048257;
      v35 = v16;
      v44 = &v35;
      v34 = v33;
      v31 = (__int64 *)&v34;
    }
    else
    {
      v16 = -1073741670;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_40;
      tlgCreate1Sz_char(v40, "VidResourcePartitionStateKsrPersist");
      tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v35 = 2311;
      v42 = &v35;
      v29 = (unsigned __int8 *)&dword_14004830C;
      v34 = v30;
      v44 = &v34;
      LODWORD(v36) = v33;
      v31 = &v36;
    }
    v46 = v31;
    v47 = 4;
    v45 = 4;
    v43 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, v29, 0, 0, 7u, v39);
    goto LABEL_40;
  }
  v16 = -1073741670;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v40, "VidResourcePartitionStateKsrPersist");
    tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    v35 = 2268;
    v42 = &v35;
    v18 = &v36;
    v34 = v23;
    v44 = &v34;
    v20 = (unsigned __int8 *)&byte_14004829F;
    v21 = &v37;
    v37 = 16 * v10 + 8;
    v36 = v10;
    v17 = 0;
    goto LABEL_19;
  }
LABEL_41:
  VidPushLockRelease(v38);
  if ( v6 )
    MmUnmapLockedPages(v6, v15);
  if ( v15 )
  {
    if ( !v4 )
      MmFreePagesFromMdl(v15);
    ExFreePoolWithTag(v15, 0);
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0x72446456u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140094ca8  push    rbp
0x140094caa  push    rbx
0x140094cab  push    rsi
0x140094cac  push    rdi
0x140094cad  push    r12
0x140094caf  push    r13
0x140094cb1  push    r14
0x140094cb3  push    r15
0x140094cb5  lea     rbp, [rsp-1Fh]
0x140094cba  sub     rsp, 0F8h
0x140094cc1  mov     rax, cs:__security_cookie
0x140094cc8  xor     rax, rsp
0x140094ccb  mov     [rbp+57h+var_50], rax
0x140094ccf  mov     rbx, cs:VidDeviceExtension
0x140094cd6  xor     r12d, r12d
0x140094cd9  add     rbx, 898h
0x140094ce0  mov     [rsp+130h+var_E8], rdx
0x140094ce5  xor     dil, dil
0x140094ce8  mov     [rsp+130h+var_FC], r12d
0x140094ced  mov     rcx, rbx
0x140094cf0  mov     [rsp+130h+var_100], dil
0x140094cf5  xor     r14d, r14d
0x140094cf8  mov     [rsp+130h+var_E0], rbx
0x140094cfd  mov     [rdx], r12
0x140094d00  call    VidPushLockAcquireExclusive
0x140094d05  mov     rax, [rbx+10h]
0x140094d09  add     rbx, 8
0x140094d0d  test    al, 1
0x140094d0f  jz      short loc_140094D27
0x140094d11  cmp     rax, 1
0x140094d15  jz      loc_140095217
0x140094d1b  mov     rcx, rbx
0x140094d1e  or      rcx, 1
0x140094d22  xor     rcx, rax
0x140094d25  jmp     short loc_140094D2A
0x140094d27  mov     rcx, rax
0x140094d2a  xor     r15d, r15d
0x140094d2d  test    rcx, rcx
0x140094d30  jz      loc_140095217
0x140094d36  mov     rax, [rcx+8]
0x140094d3a  inc     r15
0x140094d3d  test    rax, rax
0x140094d40  jz      short loc_140094D64
0x140094d42  mov     rdx, [rax]
0x140094d45  test    rdx, rdx
0x140094d48  jz      short loc_140094D5A
0x140094d4a  mov     rax, [rdx]
0x140094d4d  mov     rcx, rdx
0x140094d50  mov     rdx, rax
0x140094d53  test    rax, rax
0x140094d56  jnz     short loc_140094D4A
0x140094d58  jmp     short loc_140094D71
0x140094d5a  mov     rcx, rax
0x140094d5d  jmp     short loc_140094D71
0x140094d5f  cmp     [rcx], rax
0x140094d62  jz      short loc_140094D71
0x140094d64  mov     rax, rcx
0x140094d67  mov     rcx, [rcx+10h]
0x140094d6b  and     rcx, 0FFFFFFFFFFFFFFFCh; LowAddress
0x140094d6f  jnz     short loc_140094D5F
0x140094d71  test    rcx, rcx
0x140094d74  jnz     short loc_140094D36
0x140094d76  test    r15, r15
0x140094d79  jz      loc_140095217
0x140094d7f  mov     r13, r15
0x140094d82  mov     [rsp+130h+Flags], 14h; Flags
0x140094d8a  shl     r13, 4
0x140094d8e  xor     r8d, r8d; SkipBytes
0x140094d91  add     r13, 8
0x140094d95  mov     [rsp+130h+CacheType], 1; CacheType
0x140094d9d  mov     r9, r13; TotalBytes
0x140094da0  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x140094da4  call    cs:__imp_MmAllocatePagesForMdlEx
0x140094dab  nop     dword ptr [rax+rax+00h]
0x140094db0  xor     r9d, r9d; RequestedAddress
0x140094db3  mov     rsi, rax
0x140094db6  test    rax, rax
0x140094db9  jnz     loc_140094E90
0x140094dbf  mov     eax, cs:dword_140065110
0x140094dc5  mov     r8d, 0C000009Ah
0x140094dcb  mov     ebx, r8d
0x140094dce  cmp     eax, 2
0x140094dd1  jbe     loc_1400950C7
0x140094dd7  mov     edx, 100h
0x140094ddc  lea     rcx, dword_140065110
0x140094de3  call    _tlgKeywordOn
0x140094de8  test    al, al
0x140094dea  jz      loc_1400950C7
0x140094df0  lea     rdx, aVidresourcepar_3; "VidResourcePartitionStateKsrPersist"
0x140094df7  lea     rcx, [rbp+57h+var_B0]
0x140094dfb  call    _tlgCreate1Sz_char
0x140094e00  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140094e07  lea     rcx, [rbp+57h+var_A0]
0x140094e0b  call    _tlgCreate1Sz_char
0x140094e10  lea     rax, [rsp+130h+var_F8]
0x140094e15  mov     [rsp+130h+var_F8], 8CAh
0x140094e1d  mov     [rbp+57h+var_90], rax
0x140094e21  lea     rcx, [rsp+130h+var_E8]
0x140094e26  lea     rax, [rsp+130h+var_F4]
0x140094e2b  mov     [rsp+130h+var_F4], r8d
0x140094e30  mov     [rbp+57h+var_80], rax
0x140094e34  lea     rdx, dword_140048354
0x140094e3b  lea     rax, [rsp+130h+var_F0]
0x140094e40  mov     [rsp+130h+var_F0], r13
0x140094e45  mov     [rsp+130h+var_E8], r15
0x140094e4a  mov     [rbp+57h+var_60], rcx
0x140094e4e  xor     r8d, r8d
0x140094e51  lea     rcx, [rbp+57h+var_D0]
0x140094e55  mov     [rbp+57h+var_70], rax
0x140094e59  mov     eax, 8
0x140094e5e  mov     qword ptr [rsp+130h+Flags], rcx
0x140094e63  lea     rcx, dword_140065110
0x140094e6a  mov     [rsp+130h+CacheType], eax
0x140094e6e  mov     [rbp+57h+var_58], rax
0x140094e72  mov     [rbp+57h+var_68], rax
0x140094e76  mov     [rbp+57h+var_78], 4
0x140094e7e  mov     [rbp+57h+var_88], 4
0x140094e86  call    _tlgWriteTransfer_EtwWriteTransfer
0x140094e8b  jmp     loc_1400950C7
0x140094e90  xor     edx, edx; AccessMode
0x140094e92  mov     [rsp+130h+Flags], 40000010h; Priority
0x140094e9a  mov     rcx, rsi; MemoryDescriptorList
0x140094e9d  mov     [rsp+130h+CacheType], r9d; BugCheckOnFailure
0x140094ea2  lea     r8d, [rdx+1]; CacheType
0x140094ea6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140094ead  nop     dword ptr [rax+rax+00h]
0x140094eb2  mov     r14, rax
0x140094eb5  test    rax, rax
0x140094eb8  jnz     loc_140094F51
0x140094ebe  mov     eax, cs:dword_140065110
0x140094ec4  mov     r8d, 0C000009Ah
0x140094eca  mov     ebx, r8d
0x140094ecd  cmp     eax, 2
0x140094ed0  jbe     loc_1400950C7
0x140094ed6  mov     edx, 100h
0x140094edb  lea     rcx, dword_140065110
0x140094ee2  call    _tlgKeywordOn
0x140094ee7  test    al, al
0x140094ee9  jz      loc_1400950C7
0x140094eef  lea     rdx, aVidresourcepar_3; "VidResourcePartitionStateKsrPersist"
0x140094ef6  lea     rcx, [rbp+57h+var_B0]
0x140094efa  call    _tlgCreate1Sz_char
0x140094eff  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140094f06  lea     rcx, [rbp+57h+var_A0]
0x140094f0a  call    _tlgCreate1Sz_char
0x140094f0f  lea     rax, [rsp+130h+var_F4]
0x140094f14  mov     [rsp+130h+var_F4], 8DCh
0x140094f1c  mov     [rbp+57h+var_90], rax
0x140094f20  lea     rcx, [rsp+130h+var_F0]
0x140094f25  lea     rax, [rsp+130h+var_F8]
0x140094f2a  mov     [rsp+130h+var_F8], r8d
0x140094f2f  mov     [rbp+57h+var_80], rax
0x140094f33  lea     rdx, byte_14004829F
0x140094f3a  lea     rax, [rsp+130h+var_E8]
0x140094f3f  mov     [rsp+130h+var_E8], r13
0x140094f44  mov     [rsp+130h+var_F0], r15
0x140094f49  xor     r9d, r9d
0x140094f4c  jmp     loc_140094E4A
0x140094f51  mov     [rax], r12
0x140094f54  mov     rax, [rbx+8]
0x140094f58  test    al, 1
0x140094f5a  jz      short loc_140094F6B
0x140094f5c  cmp     rax, 1
0x140094f60  jz      short loc_140094FBC
0x140094f62  or      rbx, 1
0x140094f66  xor     rbx, rax
0x140094f69  jmp     short loc_140094FB7
0x140094f6b  mov     rbx, rax
0x140094f6e  jmp     short loc_140094FB7
0x140094f70  mov     rax, [r14]
0x140094f73  movups  xmm0, xmmword ptr [rbx-18h]
0x140094f77  add     rax, rax
0x140094f7a  movdqu  xmmword ptr [r14+rax*8+8], xmm0
0x140094f81  inc     qword ptr [r14]
0x140094f84  mov     rax, [rbx+8]
0x140094f88  test    rax, rax
0x140094f8b  jz      short loc_140094FAA
0x140094f8d  mov     rcx, [rax]
0x140094f90  test    rcx, rcx
0x140094f93  jz      short loc_140094F6B
0x140094f95  mov     rax, [rcx]
0x140094f98  mov     rbx, rcx
0x140094f9b  mov     rcx, rax
0x140094f9e  test    rax, rax
0x140094fa1  jnz     short loc_140094F95
0x140094fa3  jmp     short loc_140094FB7
0x140094fa5  cmp     [rbx], rax
0x140094fa8  jz      short loc_140094FB7
0x140094faa  mov     rax, rbx
0x140094fad  mov     rbx, [rbx+10h]
0x140094fb1  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140094fb5  jnz     short loc_140094FA5
0x140094fb7  test    rbx, rbx
0x140094fba  jnz     short loc_140094F70
0x140094fbc  lea     r9, [rsp+130h+var_FC]
0x140094fc1  xor     r8d, r8d
0x140094fc4  xor     edx, edx
0x140094fc6  mov     rcx, rsi
0x140094fc9  call    cs:__imp_KsrMdlToMemoryRuns
0x140094fd0  nop     dword ptr [rax+rax+00h]
0x140094fd5  mov     edx, [rsp+130h+var_FC]
0x140094fd9  mov     edi, 100h
0x140094fde  shl     rdx, 3
0x140094fe2  mov     r8d, 72446456h
0x140094fe8  mov     ecx, edi
0x140094fea  call    cs:__imp_ExAllocatePool2
0x140094ff1  nop     dword ptr [rax+rax+00h]
0x140094ff6  mov     r12, rax
0x140094ff9  test    rax, rax
0x140094ffc  jnz     loc_14009514E
0x140095002  mov     ecx, cs:dword_140065110
0x140095008  mov     r8d, 0C000009Ah
0x14009500e  mov     ebx, r8d
0x140095011  cmp     ecx, 2
0x140095014  jbe     loc_1400950C2
0x14009501a  mov     edx, edi
0x14009501c  lea     rcx, dword_140065110
0x140095023  call    _tlgKeywordOn
0x140095028  test    al, al
0x14009502a  jz      loc_1400950C2
0x140095030  lea     rdx, aVidresourcepar_3; "VidResourcePartitionStateKsrPersist"
0x140095037  lea     rcx, [rbp+57h+var_B0]
0x14009503b  call    _tlgCreate1Sz_char
0x140095040  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140095047  lea     rcx, [rbp+57h+var_A0]
0x14009504b  call    _tlgCreate1Sz_char
0x140095050  lea     rax, [rsp+130h+var_F4]
0x140095055  mov     [rsp+130h+var_F4], 907h
0x14009505d  mov     [rbp+57h+var_90], rax
0x140095061  lea     rdx, dword_14004830C
0x140095068  lea     rax, [rsp+130h+var_F8]
0x14009506d  mov     [rsp+130h+var_F8], r8d
0x140095072  mov     [rbp+57h+var_80], rax
0x140095076  mov     eax, [rsp+130h+var_FC]
0x14009507a  mov     dword ptr [rsp+130h+var_F0], eax
0x14009507e  lea     rax, [rsp+130h+var_F0]
0x140095083  mov     [rbp+57h+var_70], rax
0x140095087  lea     rcx, dword_140065110
0x14009508e  lea     rax, [rbp+57h+var_D0]
0x140095092  mov     [rbp+57h+var_68], 4
0x14009509a  mov     qword ptr [rsp+130h+Flags], rax
0x14009509f  xor     r9d, r9d
0x1400950a2  xor     r8d, r8d
0x1400950a5  mov     [rsp+130h+CacheType], 7
0x1400950ad  mov     [rbp+57h+var_78], 4
0x1400950b5  mov     [rbp+57h+var_88], 4
0x1400950bd  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400950c2  mov     dil, [rsp+130h+var_100]
0x1400950c7  mov     rcx, [rsp+130h+var_E0]
0x1400950cc  call    VidPushLockRelease
0x1400950d1  test    r14, r14
0x1400950d4  jz      short loc_1400950E8
0x1400950d6  mov     rdx, rsi; MemoryDescriptorList
0x1400950d9  mov     rcx, r14; BaseAddress
0x1400950dc  call    cs:__imp_MmUnmapLockedPages
0x1400950e3  nop     dword ptr [rax+rax+00h]
0x1400950e8  test    rsi, rsi
0x1400950eb  jz      short loc_140095112
0x1400950ed  test    dil, dil
0x1400950f0  jnz     short loc_140095101
0x1400950f2  mov     rcx, rsi; MemoryDescriptorList
0x1400950f5  call    cs:__imp_MmFreePagesFromMdl
0x1400950fc  nop     dword ptr [rax+rax+00h]
0x140095101  xor     edx, edx; Tag
0x140095103  mov     rcx, rsi; P
0x140095106  call    cs:__imp_ExFreePoolWithTag
0x14009510d  nop     dword ptr [rax+rax+00h]
0x140095112  test    r12, r12
0x140095115  jz      short loc_14009512B
0x140095117  mov     edx, 72446456h; Tag
0x14009511c  mov     rcx, r12; P
0x14009511f  call    cs:__imp_ExFreePoolWithTag
0x140095126  nop     dword ptr [rax+rax+00h]
0x14009512b  mov     eax, ebx
0x14009512d  mov     rcx, [rbp+57h+var_50]
0x140095131  xor     rcx, rsp; StackCookie
0x140095134  call    __security_check_cookie
0x140095139  add     rsp, 0F8h
0x140095140  pop     r15
0x140095142  pop     r14
0x140095144  pop     r13
0x140095146  pop     r12
0x140095148  pop     rdi
0x140095149  pop     rsi
0x14009514a  pop     rbx
0x14009514b  pop     rbp
0x14009514c  retn
0x14009514e  mov     r8d, [rsp+130h+var_FC]
0x140095153  lea     r9, [rsp+130h+var_FC]
0x140095158  mov     rdx, r12
0x14009515b  mov     rcx, rsi
0x14009515e  call    cs:__imp_KsrMdlToMemoryRuns
0x140095165  nop     dword ptr [rax+rax+00h]
0x14009516a  mov     r9, [rsp+130h+var_E8]
0x14009516f  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x140095176  mov     r8d, [rsp+130h+var_FC]
0x14009517b  mov     rdx, r12
0x14009517e  call    cs:__imp_KsrPersistMemory
0x140095185  nop     dword ptr [rax+rax+00h]
0x14009518a  mov     ebx, eax
  ... truncated ...
```
