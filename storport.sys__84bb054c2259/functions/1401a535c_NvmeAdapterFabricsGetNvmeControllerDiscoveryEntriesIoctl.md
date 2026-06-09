# NvmeAdapterFabricsGetNvmeControllerDiscoveryEntriesIoctl

- ea: `0x1401a535c`
- end: `0x1401a5a1a`
- name: `NvmeAdapterFabricsGetNvmeControllerDiscoveryEntriesIoctl`
- size: `1726`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400e7d6c`
- `0x1400f8b90`
- `0x14014b400`
- `0x14014b800`
- `0x1401a535c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5453`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a5453`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a573a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a573a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a56da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a56da`
- `ntoskrnl!IofCompleteRequest` at `0x1401a59e3`
- `ntoskrnl!IofCompleteRequest` at `0x1401a59e3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a56f9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a56f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a56e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a56e6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a5469`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a5469`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsGetNvmeControllerDiscoveryEntriesIoctl(__int64 a1, __int64 a2)
{
  char v3; // bp
  __int64 v4; // r14
  __int64 v5; // r12
  int v6; // esi
  struct _ERESOURCE *NvmeController; // rax
  struct _ERESOURCE *v8; // r15
  __int64 v9; // rax
  char v10; // bl
  unsigned __int64 v11; // r13
  _WORD *v12; // r14
  size_t v13; // r8
  _LIST_ENTRY *Blink; // rax
  unsigned __int64 v15; // rax
  int v16; // r10d
  _OWNER_ENTRY **p_OwnerTable; // rax
  unsigned __int64 v18; // r9
  _OWNER_ENTRY *OwnerTable; // r8
  _WORD *v20; // rdx
  unsigned int v21; // r11d
  _OWNER_ENTRY *v22; // rcx
  __int64 v23; // rbx
  _OWNER_ENTRY *v24; // rax
  _OWNER_ENTRY v25; // xmm0
  _OWNER_ENTRY *v26; // rax
  __int64 v27; // rbx
  _OWNER_ENTRY *v28; // rcx
  _OWNER_ENTRY v29; // xmm0
  bool v30; // zf
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  int *v33; // rax
  int v34; // ecx
  __int64 *v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // r12d
  unsigned __int8 v38; // r10
  char *v39; // r11
  char v40; // bl
  _BYTE *v41; // r9
  __int64 v42; // r15
  char v43; // r13
  unsigned __int64 v44; // r14
  __int64 v45; // r8
  int v46; // ecx
  char v47; // cl
  char v48; // r14
  char v49; // r11
  char v50; // r8
  _BYTE *v51; // rax
  char *v52; // r8
  unsigned int v53; // eax
  __int128 v55; // [rsp+60h] [rbp-58h] BYREF

  *(_QWORD *)(a2 + 56) = 0;
  v3 = 1;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v4 = *(_QWORD *)(a2 + 24);
    if ( v4
      && (v5 = *(_QWORD *)(a2 + 184), *(_DWORD *)(v5 + 16) >= 0x20u)
      && *(_WORD *)v4 == 1
      && *(_WORD *)(v4 + 2) >= 0x20u )
    {
      if ( *(_DWORD *)(v5 + 8) < 0x20u )
      {
        v6 = -1073741789;
        goto LABEL_45;
      }
      NvmeController = (struct _ERESOURCE *)NvmeAdapterFindNvmeController(
                                              a1,
                                              (_QWORD *)(*(_QWORD *)(v4 + 24) ^ a1),
                                              0,
                                              0);
      v8 = NvmeController;
      if ( !NvmeController )
      {
        v6 = -1073741275;
        goto LABEL_45;
      }
      v6 = NvmeControllerAcquireRundown(NvmeController);
      if ( v6 >= 0 )
      {
        if ( ((__int64)v8[1].SharedWaiters & 8) != 0 )
        {
          v6 = -2147483631;
LABEL_42:
          ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v8[5].SharedWaiters);
          goto LABEL_45;
        }
        if ( HIDWORD(v8[5].OwnerEntry.OwnerThread) != 2 )
        {
          v6 = -1073741637;
          goto LABEL_42;
        }
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite(v8 + 14, 1u);
        v9 = *(_QWORD *)(v4 + 8);
        v10 = *(_BYTE *)(v4 + 4);
        v11 = *(_QWORD *)(v4 + 16);
        v12 = *(_WORD **)(a2 + 24);
        v13 = *(unsigned int *)(v5 + 8);
        *(_QWORD *)&v55 = v9;
        memset_0(v12, 0, v13);
        if ( (v10 & 1) == 0 || (_LIST_ENTRY *)v55 == v8[15].SystemResourcesList.Flink )
        {
          *v12 = 1;
          *((_QWORD *)v12 + 2) = v8[15].SystemResourcesList.Flink;
          Blink = v8[15].SystemResourcesList.Blink;
          if ( v11 < (unsigned __int64)Blink )
          {
            v15 = (unsigned __int64)Blink - v11;
            *((_QWORD *)v12 + 3) = v15;
            if ( *(_DWORD *)(v5 + 8) >= 0x258u )
            {
              p_OwnerTable = &v8[15].OwnerTable;
              v18 = 0;
              OwnerTable = v8[15].OwnerTable;
              v20 = v12 + 16;
              v21 = 32;
              if ( OwnerTable != (_OWNER_ENTRY *)&v8[15].OwnerTable )
              {
                do
                {
                  if ( v18 >= v11 )
                  {
                    if ( *(unsigned int *)(v5 + 8) < (unsigned __int64)v21 + 568 || v18 - v11 > 0x400 )
                      break;
                    *(_DWORD *)v20 = 37224449;
                    if ( HIWORD(OwnerTable[1].OwnerThread) == 0xFFFF )
                      *((_DWORD *)v20 + 1) |= 1u;
                    if ( BYTE2(OwnerTable[1].OwnerThread) == 2 )
                      *((_DWORD *)v20 + 1) |= 2u;
                    v22 = OwnerTable + 17;
                    *((_DWORD *)v20 + 2) = LOBYTE(OwnerTable[1].OwnerThread);
                    v23 = 2;
                    *((_DWORD *)v20 + 3) = BYTE1(OwnerTable[1].OwnerThread);
                    v20[8] = WORD2(OwnerTable[1].OwnerThread);
                    v20[9] = HIWORD(OwnerTable[1].OwnerThread);
                    v20[10] = OwnerTable[1].EntryCounts.Value;
                    *((_BYTE *)v20 + 22) = BYTE3(OwnerTable[1].OwnerThread);
                    v24 = (_OWNER_ENTRY *)(v20 + 12);
                    do
                    {
                      v25 = *v22;
                      v22 += 8;
                      *v24 = v25;
                      v24 += 8;
                      v24[-7] = v22[-7];
                      v24[-6] = v22[-6];
                      v24[-5] = v22[-5];
                      v24[-4] = v22[-4];
                      v24[-3] = v22[-3];
                      v24[-2] = v22[-2];
                      v24[-1] = v22[-1];
                      --v23;
                    }
                    while ( v23 );
                    v26 = (_OWNER_ENTRY *)(v20 + 140);
                    v27 = 2;
                    v28 = OwnerTable + 33;
                    do
                    {
                      v29 = *v28;
                      v28 += 8;
                      *v26 = v29;
                      v26 += 8;
                      v26[-7] = v28[-7];
                      v26[-6] = v28[-6];
                      v26[-5] = v28[-5];
                      v26[-4] = v28[-4];
                      v26[-3] = v28[-3];
                      v26[-2] = v28[-2];
                      v26[-1] = v28[-1];
                      --v27;
                    }
                    while ( v27 );
                    p_OwnerTable = &v8[15].OwnerTable;
                    *(_OWNER_ENTRY *)(v20 + 268) = OwnerTable[3];
                    *(_OWNER_ENTRY *)(v20 + 276) = OwnerTable[4];
                    v20 += 284;
                    v21 += 568;
                  }
                  OwnerTable = (_OWNER_ENTRY *)OwnerTable->OwnerThread;
                  ++v18;
                }
                while ( OwnerTable != (_OWNER_ENTRY *)p_OwnerTable );
              }
              v12[1] = v18 - v11;
              *((_DWORD *)v12 + 1) = v21;
              *(_QWORD *)(a2 + 56) = v21;
              goto LABEL_41;
            }
            v16 = 1024;
            if ( v15 < 0x400 )
              v16 = v15;
            *((_DWORD *)v12 + 1) = 568 * v16;
          }
          else
          {
            *((_DWORD *)v12 + 1) = 32;
          }
          *(_QWORD *)(a2 + 56) = 32;
          v6 = 0;
        }
        else
        {
          v6 = -1073741536;
        }
LABEL_41:
        ExReleaseResourceLite(v8 + 14);
        KeLeaveCriticalRegion();
        goto LABEL_42;
      }
    }
    else
    {
      v6 = -1073741811;
    }
  }
  else
  {
    v6 = -1073741637;
  }
LABEL_45:
  v30 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v6;
  if ( v30 )
    goto LABEL_109;
  v55 = 0;
  IoGetActivityIdIrp(a2, &v55);
  v32 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v32 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_109;
    v35 = EventNonReadWriteRequestComplete;
    goto LABEL_108;
  }
  if ( *(_BYTE *)v32 != 15 )
  {
    if ( *(_BYTE *)v32 != 27 )
      goto LABEL_109;
    if ( *(_BYTE *)(v32 + 1) == 7 && !*(_DWORD *)(v32 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v33 = *(int **)(a2 + 56);
        if ( v33 )
          v34 = *v33;
        else
          v34 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v34, v32, (unsigned int)&v55, a2, v34, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_109;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_109;
    v35 = EventPnpRequestComplete;
LABEL_108:
    McTemplateK0pd_EtwWriteTransfer(v31, v35, &v55, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_109;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_109;
  v36 = *(_QWORD *)(v32 + 8);
  if ( *(_BYTE *)(v36 + 2) != 40 )
  {
    v47 = *(_BYTE *)(v36 + 72);
    v41 = *(_BYTE **)(v36 + 32);
    v38 = *(_BYTE *)(v36 + 11);
    v40 = *(_BYTE *)(v36 + 4);
    if ( *(_BYTE *)(v36 + 2) )
      goto LABEL_109;
LABEL_87:
    LOBYTE(v31) = v47 - 8;
    if ( (v31 & 0x5D) != 0 )
      goto LABEL_109;
    v48 = *(_BYTE *)(v36 + 3);
    if ( v48 == 1 || !v41 || !v38 )
      goto LABEL_104;
    LOBYTE(v36) = 0;
    v49 = 0;
    v50 = 0;
    v31 = (unsigned __int64)&v41[v38];
    v51 = v41 + 8;
    if ( (unsigned __int8)((*v41 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v51 <= v31 )
      {
        v49 = v41[2];
        LOBYTE(v36) = v41[1] & 0xF;
        v50 = v41[3];
        goto LABEL_103;
      }
    }
    else if ( (unsigned __int64)v51 <= v31 )
    {
      v52 = v41 + 13;
      LOBYTE(v36) = v41[2] & 0xF;
      v53 = v38;
      if ( (unsigned int)(unsigned __int8)v41[7] + 8 <= v38 )
        v53 = (unsigned __int8)v41[7] + 8;
      v31 = (unsigned __int64)&v41[v53];
      if ( (unsigned __int64)v52 <= v31 )
        v49 = v41[12];
      if ( (unsigned __int64)(v41 + 14) > v31 )
        v50 = 0;
      else
        v50 = *v52;
LABEL_103:
      if ( v3 )
      {
LABEL_105:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v31,
          v36,
          (unsigned int)&v55,
          a2,
          *(_DWORD *)(a2 + 48),
          v48,
          v40,
          v36,
          v49,
          v50,
          a2);
        goto LABEL_109;
      }
LABEL_104:
      LOBYTE(v36) = 0;
      v49 = 0;
      v50 = 0;
      goto LABEL_105;
    }
    v3 = 0;
    goto LABEL_103;
  }
  if ( *(_DWORD *)(v36 + 20) )
    goto LABEL_109;
  v37 = *(_DWORD *)(v36 + 56);
  if ( !v37 )
    goto LABEL_109;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  while ( 1 )
  {
    v31 = *(unsigned int *)(v36 + 4 * v42 + 120);
    if ( (unsigned int)v31 >= 0x80 )
    {
      v44 = *(unsigned int *)(v36 + 16);
      if ( (unsigned int)v31 < (unsigned int)v44 )
        break;
    }
LABEL_78:
    v42 = (unsigned int)(v42 + 1);
    if ( (unsigned int)v42 >= v37 )
      goto LABEL_84;
  }
  v45 = (unsigned int)v31;
  v46 = *(_DWORD *)(v31 + v36) - 64;
  if ( v46 )
  {
    LODWORD(v31) = v46 - 1;
    if ( (_DWORD)v31 )
    {
      if ( (_DWORD)v31 == 1 )
      {
        LODWORD(v31) = v45 + 40;
        if ( v45 + 40 <= v44 )
        {
          if ( *(_DWORD *)(v45 + v36 + 12) )
            v39 = (char *)(v45 + v36 + 32);
          v41 = *(_BYTE **)(v45 + v36 + 24);
          goto LABEL_83;
        }
      }
    }
    else
    {
      LODWORD(v31) = v45 + 56;
      if ( v45 + 56 <= v44 )
      {
        v43 = 1;
        if ( *(_BYTE *)(v45 + v36 + 10) )
          v39 = (char *)(v45 + v36 + 24);
        v40 = *(_BYTE *)(v45 + v36 + 8);
        v41 = *(_BYTE **)(v45 + v36 + 16);
        v38 = *(_BYTE *)(v45 + v36 + 9);
      }
    }
    goto LABEL_77;
  }
  LODWORD(v31) = v45 + 40;
  if ( v45 + 40 > v44 )
  {
LABEL_77:
    if ( v43 )
      goto LABEL_84;
    goto LABEL_78;
  }
  if ( *(_BYTE *)(v45 + v36 + 10) )
    v39 = (char *)(v45 + v36 + 24);
  v41 = *(_BYTE **)(v45 + v36 + 16);
LABEL_83:
  v38 = *(_BYTE *)(v45 + v36 + 9);
  v40 = *(_BYTE *)(v45 + v36 + 8);
LABEL_84:
  if ( v39 )
  {
    v47 = *v39;
    goto LABEL_87;
  }
LABEL_109:
  IofCompleteRequest((PIRP)a2, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1401a535c  mov     [rsp+arg_10], rbx
0x1401a5361  push    rbp
0x1401a5362  push    rsi
0x1401a5363  push    rdi
0x1401a5364  push    r12
0x1401a5366  push    r13
0x1401a5368  push    r14
0x1401a536a  push    r15
0x1401a536c  sub     rsp, 80h
0x1401a5373  mov     rax, cs:__security_cookie
0x1401a537a  xor     rax, rsp
0x1401a537d  mov     [rsp+0B8h+var_48], rax
0x1401a5382  mov     ebx, 20h ; ' '
0x1401a5387  mov     qword ptr [rdx+38h], 0
0x1401a538f  mov     rdi, rdx
0x1401a5392  lea     ebp, [rbx-1Fh]
0x1401a5395  test    [rcx+98h], bpl
0x1401a539c  jz      loc_1401A570E
0x1401a53a2  cmp     qword ptr [rcx+268h], 0
0x1401a53aa  jz      loc_1401A570E
0x1401a53b0  mov     r14, [rdx+18h]
0x1401a53b4  test    r14, r14
0x1401a53b7  jz      loc_1401A5707
0x1401a53bd  mov     r12, [rdx+0B8h]
0x1401a53c4  cmp     [r12+10h], ebx
0x1401a53c9  jb      loc_1401A5707
0x1401a53cf  cmp     [r14], bp
0x1401a53d3  jnz     loc_1401A5707
0x1401a53d9  cmp     [r14+2], bx
0x1401a53de  jb      loc_1401A5707
0x1401a53e4  cmp     [r12+8], ebx
0x1401a53e9  jnb     short loc_1401A53F5
0x1401a53eb  mov     esi, 0C0000023h
0x1401a53f0  jmp     loc_1401A5713
0x1401a53f5  mov     rdx, rcx
0x1401a53f8  xor     r9d, r9d
0x1401a53fb  xor     rdx, [r14+18h]
0x1401a53ff  xor     r8d, r8d
0x1401a5402  call    NvmeAdapterFindNvmeController
0x1401a5407  mov     r15, rax
0x1401a540a  test    rax, rax
0x1401a540d  jnz     short loc_1401A5419
0x1401a540f  mov     esi, 0C0000225h
0x1401a5414  jmp     loc_1401A5713
0x1401a5419  mov     rcx, r15
0x1401a541c  call    NvmeControllerAcquireRundown
0x1401a5421  mov     esi, eax
0x1401a5423  test    eax, eax
0x1401a5425  js      loc_1401A5713
0x1401a542b  test    byte ptr [r15+88h], 8
0x1401a5433  jz      short loc_1401A543F
0x1401a5435  mov     esi, 80000011h
0x1401a543a  jmp     loc_1401A56F2
0x1401a543f  cmp     dword ptr [r15+23Ch], 2
0x1401a5447  jz      short loc_1401A5453
0x1401a5449  mov     esi, 0C00000BBh
0x1401a544e  jmp     loc_1401A56F2
0x1401a5453  call    cs:__imp_KeEnterCriticalRegion
0x1401a545a  nop     dword ptr [rax+rax+00h]
0x1401a545f  lea     rcx, [r15+5B0h]; Resource
0x1401a5466  mov     dl, bpl; Wait
0x1401a5469  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a5470  nop     dword ptr [rax+rax+00h]
0x1401a5475  mov     rax, [r14+8]
0x1401a5479  xor     edx, edx; Val
0x1401a547b  mov     bl, [r14+4]
0x1401a547f  mov     r13, [r14+10h]
0x1401a5483  mov     r14, [rdi+18h]
0x1401a5487  mov     r8d, [r12+8]; Size
0x1401a548c  mov     rcx, r14; void *
0x1401a548f  mov     qword ptr [rsp+0B8h+var_58], rax
0x1401a5494  call    memset_0
0x1401a5499  test    bpl, bl
0x1401a549c  jz      short loc_1401A54BB
0x1401a549e  mov     rax, qword ptr [rsp+0B8h+var_58]
0x1401a54a3  cmp     rax, [r15+618h]
0x1401a54aa  jz      short loc_1401A54BB
0x1401a54ac  mov     esi, 0C0000120h
0x1401a54b1  mov     ebx, 20h ; ' '
0x1401a54b6  jmp     loc_1401A56D3
0x1401a54bb  mov     [r14], bp
0x1401a54bf  mov     ebx, 20h ; ' '
0x1401a54c4  mov     rax, [r15+618h]
0x1401a54cb  mov     [r14+10h], rax
0x1401a54cf  mov     rax, [r15+620h]
0x1401a54d6  cmp     r13, rax
0x1401a54d9  jb      short loc_1401A54EA
0x1401a54db  mov     [r14+4], ebx
0x1401a54df  mov     [rdi+38h], rbx
0x1401a54e3  xor     esi, esi
0x1401a54e5  jmp     loc_1401A56D3
0x1401a54ea  sub     rax, r13
0x1401a54ed  mov     [r14+18h], rax
0x1401a54f1  cmp     dword ptr [r12+8], 258h
0x1401a54fa  jnb     short loc_1401A5516
0x1401a54fc  mov     r10d, 400h
0x1401a5502  cmp     rax, r10
0x1401a5505  cmovb   r10, rax
0x1401a5509  imul    eax, r10d, 238h
0x1401a5510  mov     [r14+4], eax
0x1401a5514  jmp     short loc_1401A54DF
0x1401a5516  lea     rax, [r15+628h]
0x1401a551d  xor     r9d, r9d
0x1401a5520  mov     r8, [rax]
0x1401a5523  lea     rdx, [r14+20h]
0x1401a5527  mov     r11d, ebx
0x1401a552a  cmp     r8, rax
0x1401a552d  jz      loc_1401A56BF
0x1401a5533  mov     ebx, 238h
0x1401a5538  mov     r10d, 400h
0x1401a553e  cmp     r9, r13
0x1401a5541  jb      loc_1401A56AB
0x1401a5547  mov     eax, [r12+8]
0x1401a554c  mov     ecx, r11d
0x1401a554f  add     rcx, rbx
0x1401a5552  cmp     rax, rcx
0x1401a5555  jb      loc_1401A56BA
0x1401a555b  mov     rax, r9
0x1401a555e  sub     rax, r13
0x1401a5561  cmp     rax, r10
0x1401a5564  ja      loc_1401A56BA
0x1401a556a  mov     eax, 0FFFFh
0x1401a556f  mov     dword ptr [rdx], 2380001h
0x1401a5575  cmp     [r8+16h], ax
0x1401a557a  jnz     short loc_1401A557F
0x1401a557c  or      [rdx+4], ebp
0x1401a557f  cmp     byte ptr [r8+12h], 2
0x1401a5584  jnz     short loc_1401A558A
0x1401a5586  or      dword ptr [rdx+4], 2
0x1401a558a  movzx   eax, byte ptr [r8+10h]
0x1401a558f  lea     rcx, [r8+110h]
0x1401a5596  mov     [rdx+8], eax
0x1401a5599  mov     ebx, 2
0x1401a559e  movzx   eax, byte ptr [r8+11h]
0x1401a55a3  mov     [rdx+0Ch], eax
0x1401a55a6  movzx   eax, word ptr [r8+14h]
0x1401a55ab  mov     [rdx+10h], ax
0x1401a55af  movzx   eax, word ptr [r8+16h]
0x1401a55b4  mov     [rdx+12h], ax
0x1401a55b8  movzx   eax, word ptr [r8+18h]
0x1401a55bd  mov     [rdx+14h], ax
0x1401a55c1  mov     al, [r8+13h]
0x1401a55c5  mov     [rdx+16h], al
0x1401a55c8  lea     rax, [rdx+18h]
0x1401a55cc  movups  xmm0, xmmword ptr [rcx]
0x1401a55cf  lea     rcx, [rcx+80h]
0x1401a55d6  movups  xmmword ptr [rax], xmm0
0x1401a55d9  lea     rax, [rax+80h]
0x1401a55e0  movups  xmm1, xmmword ptr [rcx-70h]
0x1401a55e4  movups  xmmword ptr [rax-70h], xmm1
0x1401a55e8  movups  xmm0, xmmword ptr [rcx-60h]
0x1401a55ec  movups  xmmword ptr [rax-60h], xmm0
0x1401a55f0  movups  xmm1, xmmword ptr [rcx-50h]
0x1401a55f4  movups  xmmword ptr [rax-50h], xmm1
0x1401a55f8  movups  xmm0, xmmword ptr [rcx-40h]
0x1401a55fc  movups  xmmword ptr [rax-40h], xmm0
0x1401a5600  movups  xmm1, xmmword ptr [rcx-30h]
0x1401a5604  movups  xmmword ptr [rax-30h], xmm1
0x1401a5608  movups  xmm0, xmmword ptr [rcx-20h]
0x1401a560c  movups  xmmword ptr [rax-20h], xmm0
0x1401a5610  movups  xmm1, xmmword ptr [rcx-10h]
0x1401a5614  movups  xmmword ptr [rax-10h], xmm1
0x1401a5618  sub     rbx, rbp
0x1401a561b  jnz     short loc_1401A55CC
0x1401a561d  lea     rax, [rdx+118h]
0x1401a5624  mov     ebx, 2
0x1401a5629  lea     rcx, [r8+210h]
0x1401a5630  movups  xmm0, xmmword ptr [rcx]
0x1401a5633  lea     rcx, [rcx+80h]
0x1401a563a  movups  xmmword ptr [rax], xmm0
0x1401a563d  lea     rax, [rax+80h]
0x1401a5644  movups  xmm1, xmmword ptr [rcx-70h]
0x1401a5648  movups  xmmword ptr [rax-70h], xmm1
0x1401a564c  movups  xmm0, xmmword ptr [rcx-60h]
0x1401a5650  movups  xmmword ptr [rax-60h], xmm0
0x1401a5654  movups  xmm1, xmmword ptr [rcx-50h]
0x1401a5658  movups  xmmword ptr [rax-50h], xmm1
0x1401a565c  movups  xmm0, xmmword ptr [rcx-40h]
0x1401a5660  movups  xmmword ptr [rax-40h], xmm0
0x1401a5664  movups  xmm1, xmmword ptr [rcx-30h]
0x1401a5668  movups  xmmword ptr [rax-30h], xmm1
0x1401a566c  movups  xmm0, xmmword ptr [rcx-20h]
0x1401a5670  movups  xmmword ptr [rax-20h], xmm0
0x1401a5674  movups  xmm1, xmmword ptr [rcx-10h]
0x1401a5678  movups  xmmword ptr [rax-10h], xmm1
0x1401a567c  sub     rbx, rbp
0x1401a567f  jnz     short loc_1401A5630
0x1401a5681  movups  xmm0, xmmword ptr [r8+30h]
0x1401a5686  mov     ebx, 238h
0x1401a568b  lea     rax, [r15+628h]
0x1401a5692  movups  xmmword ptr [rdx+218h], xmm0
0x1401a5699  movups  xmm1, xmmword ptr [r8+40h]
0x1401a569e  movups  xmmword ptr [rdx+228h], xmm1
0x1401a56a5  add     rdx, rbx
0x1401a56a8  add     r11d, ebx
0x1401a56ab  mov     r8, [r8]
0x1401a56ae  add     r9, rbp
0x1401a56b1  cmp     r8, rax
0x1401a56b4  jnz     loc_1401A553E
0x1401a56ba  mov     ebx, 20h ; ' '
0x1401a56bf  sub     r9w, r13w
0x1401a56c3  mov     eax, r11d
0x1401a56c6  mov     [r14+2], r9w
0x1401a56cb  mov     [r14+4], r11d
0x1401a56cf  mov     [rdi+38h], rax
0x1401a56d3  lea     rcx, [r15+5B0h]; Resource
0x1401a56da  call    cs:__imp_ExReleaseResourceLite
0x1401a56e1  nop     dword ptr [rax+rax+00h]
0x1401a56e6  call    cs:__imp_KeLeaveCriticalRegion
0x1401a56ed  nop     dword ptr [rax+rax+00h]
0x1401a56f2  mov     rcx, [r15+228h]; RunRefCacheAware
0x1401a56f9  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a5700  nop     dword ptr [rax+rax+00h]
0x1401a5705  jmp     short loc_1401A5713
0x1401a5707  mov     esi, 0C000000Dh
0x1401a570c  jmp     short loc_1401A5713
0x1401a570e  mov     esi, 0C00000BBh
0x1401a5713  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a571a  mov     byte ptr [rdi+8Dh], 0ACh
0x1401a5721  mov     [rdi+30h], esi
0x1401a5724  jz      loc_1401A59DE
0x1401a572a  xorps   xmm0, xmm0
0x1401a572d  lea     rdx, [rsp+0B8h+var_58]
0x1401a5732  mov     rcx, rdi
0x1401a5735  movups  [rsp+0B8h+var_58], xmm0
0x1401a573a  call    cs:__imp_IoGetActivityIdIrp
0x1401a5741  nop     dword ptr [rax+rax+00h]
0x1401a5746  mov     rdx, [rdi+0B8h]
0x1401a574d  movzx   eax, byte ptr [rdx]
0x1401a5750  sub     eax, 0Eh
0x1401a5753  jz      loc_1401A59BA
0x1401a5759  sub     eax, ebp
0x1401a575b  jz      short loc_1401A57C3
0x1401a575d  cmp     eax, 0Ch
0x1401a5760  jnz     loc_1401A59DE
0x1401a5766  cmp     byte ptr [rdx+1], 7
0x1401a576a  jnz     short loc_1401A57AB
0x1401a576c  cmp     dword ptr [rdx+8], 0
0x1401a5770  jnz     short loc_1401A57AB
0x1401a5772  test    cs:byte_140177432, 40h
0x1401a5779  jz      loc_1401A59DE
0x1401a577f  mov     rax, [rdi+38h]
0x1401a5783  test    rax, rax
0x1401a5786  jz      short loc_1401A578C
0x1401a5788  mov     ecx, [rax]
0x1401a578a  jmp     short loc_1401A578E
0x1401a578c  xor     ecx, ecx
0x1401a578e  mov     eax, [rdi+30h]
0x1401a5791  lea     r8, [rsp+0B8h+var_58]
0x1401a5796  mov     [rsp+0B8h+var_90], eax
0x1401a579a  mov     r9, rdi
0x1401a579d  mov     [rsp+0B8h+var_98], ecx
0x1401a57a1  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a57a6  jmp     loc_1401A59DE
0x1401a57ab  test    cs:byte_140177432, bl
0x1401a57b1  jz      loc_1401A59DE
0x1401a57b7  lea     rdx, EventPnpRequestComplete
0x1401a57be  jmp     loc_1401A59CA
0x1401a57c3  cmp     cs:byte_140177431, 0
0x1401a57ca  jge     loc_1401A59DE
0x1401a57d0  mov     rdx, [rdx+8]
0x1401a57d4  movzx   eax, byte ptr [rdx+2]
0x1401a57d8  cmp     al, 28h ; '('
0x1401a57da  jnz     loc_1401A58C4
0x1401a57e0  cmp     dword ptr [rdx+14h], 0
0x1401a57e4  jnz     loc_1401A59DE
0x1401a57ea  mov     r12d, [rdx+38h]
0x1401a57ee  test    r12d, r12d
0x1401a57f1  jz      loc_1401A59DE
0x1401a57f7  xor     r10b, r10b
0x1401a57fa  xor     r11d, r11d
0x1401a57fd  xor     bl, bl
0x1401a57ff  xor     r9d, r9d
0x1401a5802  xor     r15d, r15d
0x1401a5805  xor     r13b, r13b
0x1401a5808  mov     ecx, [rdx+r15*4+78h]
0x1401a580d  cmp     ecx, 80h
0x1401a5813  jb      short loc_1401A588A
0x1401a5815  mov     r14d, [rdx+10h]
0x1401a5819  cmp     ecx, r14d
0x1401a581c  jnb     short loc_1401A588A
0x1401a581e  mov     r8d, ecx
0x1401a5821  mov     ecx, [rcx+rdx]
0x1401a5824  sub     ecx, 40h ; '@'
0x1401a5827  jz      short loc_1401A587C
0x1401a5829  sub     ecx, ebp
0x1401a582b  jz      short loc_1401A5850
0x1401a582d  cmp     ecx, ebp
0x1401a582f  jnz     short loc_1401A5885
0x1401a5831  lea     rcx, [r8+28h]
0x1401a5835  cmp     rcx, r14
0x1401a5838  ja      short loc_1401A5885
0x1401a583a  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a5840  jbe     short loc_1401A5849
0x1401a5842  lea     r11, [rdx+20h]
0x1401a5846  add     r11, r8
0x1401a5849  mov     r9, [r8+rdx+18h]
0x1401a584e  jmp     short loc_1401A58AC
0x1401a5850  lea     rcx, [r8+38h]
0x1401a5854  cmp     rcx, r14
  ... truncated ...
```
