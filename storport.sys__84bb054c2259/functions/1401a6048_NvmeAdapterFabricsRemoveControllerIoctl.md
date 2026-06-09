# NvmeAdapterFabricsRemoveControllerIoctl

- ea: `0x1401a6048`
- end: `0x1401a64fa`
- name: `NvmeAdapterFabricsRemoveControllerIoctl`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x14007706c`
- `0x1400848c4`
- `0x1400f8b90`
- `0x14014b400`
- `0x1401a6048`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6153`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a6153`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6170`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a6170`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a6210`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a6210`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a61a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a61a5`
- `ntoskrnl!IofCompleteRequest` at `0x1401a64c4`
- `ntoskrnl!IofCompleteRequest` at `0x1401a64c4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a611c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a61c1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a611c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1401a61c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a61b1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a61b1`

## pseudocode

```c
__int64 __fastcall NvmeAdapterFabricsRemoveControllerIoctl(__int64 a1, __int64 a2)
{
  char v2; // si
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 NvmeController; // rax
  __int64 v7; // rdi
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // r14
  struct _ERESOURCE *v11; // r15
  _QWORD *v12; // rdi
  __int64 v13; // rdx
  _QWORD *v14; // rax
  bool v15; // zf
  unsigned __int64 v16; // rcx
  __int64 v17; // rdx
  int *v18; // rax
  int v19; // ecx
  __int64 v20; // rdx
  unsigned int v21; // r12d
  _BYTE *v22; // r9
  unsigned __int8 v23; // r11
  char *v24; // r10
  char v25; // r13
  __int64 v26; // r15
  unsigned __int64 v27; // r14
  __int64 v28; // r8
  int v29; // ecx
  char v30; // cl
  char v31; // r14
  char v32; // r10
  char v33; // r8
  _BYTE *v34; // rax
  char *v35; // r8
  unsigned int v36; // eax
  char v38; // [rsp+60h] [rbp-9h]
  __int64 v39; // [rsp+68h] [rbp-1h] BYREF
  __int128 v40; // [rsp+70h] [rbp+7h] BYREF

  v2 = 1;
  *(_QWORD *)(a2 + 56) = 0;
  v39 = 0;
  if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    v4 = *(_QWORD *)(a2 + 24);
    if ( v4 && *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL) >= 0x10u && *(_WORD *)v4 == 1 && *(_WORD *)(v4 + 2) >= 0x10u )
    {
      v5 = *(_QWORD *)(v4 + 8) ^ a1;
      LOBYTE(v4) = 1;
      NvmeController = NvmeAdapterFindNvmeController(a1, v5, v4, &v39);
      *(_QWORD *)&v40 = NvmeController;
      v7 = NvmeController;
      if ( !NvmeController )
      {
        v8 = -1073741275;
        goto LABEL_22;
      }
      v9 = *(_QWORD *)(NvmeController + 136);
      if ( (v9 & 1) == 0 )
      {
        v8 = -1073741637;
LABEL_11:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v39 + 40));
        goto LABEL_22;
      }
      if ( *(_DWORD *)(v7 + 568) )
      {
        v8 = -1073741808;
        goto LABEL_11;
      }
      if ( (v9 & 8) != 0 )
      {
        v8 = -2147483631;
        goto LABEL_11;
      }
      *(_QWORD *)(v7 + 136) = v9 | 8;
      KeEnterCriticalRegion();
      v10 = v39;
      v11 = (struct _ERESOURCE *)(v39 + 632);
      ExAcquireResourceExclusiveLite((PERESOURCE)(v39 + 632), 1u);
      v12 = (_QWORD *)(v7 + 64);
      v13 = *v12;
      if ( *(_QWORD **)(*v12 + 8LL) != v12 || (v14 = (_QWORD *)v12[1], (_QWORD *)*v14 != v12) )
        __fastfail(3u);
      *v14 = v13;
      *(_QWORD *)(v13 + 8) = v14;
      v8 = 0;
      --*(_DWORD *)(v10 + 624);
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
      ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v10 + 40));
      NvmeAdapterDeleteNvmeController((PVOID *)&v40);
    }
    else
    {
      v8 = -1073741811;
    }
  }
  else
  {
    v8 = -1073741637;
  }
LABEL_22:
  v15 = StorEtwLoggingEnabled == 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v8;
  if ( v15 )
    goto LABEL_85;
  v40 = 0;
  IoGetActivityIdIrp(a2, &v40);
  v17 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v17 == 14 )
  {
    if ( (byte_140177432 & 8) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v16, EventNonReadWriteRequestComplete, &v40, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_85;
  }
  if ( *(_BYTE *)v17 != 15 )
  {
    if ( *(_BYTE *)v17 == 27 )
    {
      if ( *(_BYTE *)(v17 + 1) != 7 || *(_DWORD *)(v17 + 8) )
      {
        if ( (byte_140177432 & 0x20) != 0 )
          McTemplateK0pd_EtwWriteTransfer(v16, EventPnpRequestComplete, &v40, a2, *(_DWORD *)(a2 + 48));
      }
      else if ( (byte_140177432 & 0x40) != 0 )
      {
        v18 = *(int **)(a2 + 56);
        if ( v18 )
          v19 = *v18;
        else
          v19 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v19, v17, (unsigned int)&v40, a2, v19, *(_DWORD *)(a2 + 48));
      }
    }
    goto LABEL_85;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_85;
  v20 = *(_QWORD *)(v17 + 8);
  if ( *(_BYTE *)(v20 + 2) != 40 )
  {
    v30 = *(_BYTE *)(v20 + 72);
    v22 = *(_BYTE **)(v20 + 32);
    v23 = *(_BYTE *)(v20 + 11);
    v25 = *(_BYTE *)(v20 + 4);
    if ( *(_BYTE *)(v20 + 2) )
      goto LABEL_85;
LABEL_64:
    LOBYTE(v16) = v30 - 8;
    if ( (v16 & 0x5D) != 0 )
      goto LABEL_85;
    v31 = *(_BYTE *)(v20 + 3);
    if ( v31 == 1 || !v22 || !v23 )
      goto LABEL_81;
    LOBYTE(v20) = 0;
    v32 = 0;
    v33 = 0;
    v16 = (unsigned __int64)&v22[v23];
    v34 = v22 + 8;
    if ( (unsigned __int8)((*v22 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v34 <= v16 )
      {
        v32 = v22[2];
        LOBYTE(v20) = v22[1] & 0xF;
        v33 = v22[3];
        goto LABEL_80;
      }
    }
    else if ( (unsigned __int64)v34 <= v16 )
    {
      v35 = v22 + 13;
      LOBYTE(v20) = v22[2] & 0xF;
      v36 = v23;
      if ( (unsigned int)(unsigned __int8)v22[7] + 8 <= v23 )
        v36 = (unsigned __int8)v22[7] + 8;
      v16 = (unsigned __int64)&v22[v36];
      if ( (unsigned __int64)v35 <= v16 )
        v32 = v22[12];
      if ( (unsigned __int64)(v22 + 14) > v16 )
        v33 = 0;
      else
        v33 = *v35;
LABEL_80:
      if ( v2 )
      {
LABEL_82:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v16,
          v20,
          (unsigned int)&v40,
          a2,
          *(_DWORD *)(a2 + 48),
          v31,
          v25,
          v20,
          v32,
          v33,
          a2);
        goto LABEL_85;
      }
LABEL_81:
      LOBYTE(v20) = 0;
      v32 = 0;
      v33 = 0;
      goto LABEL_82;
    }
    v2 = 0;
    goto LABEL_80;
  }
  if ( *(_DWORD *)(v20 + 20) )
    goto LABEL_85;
  v21 = *(_DWORD *)(v20 + 56);
  if ( !v21 )
    goto LABEL_85;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v38 = 0;
  v25 = 0;
  v26 = 0;
  while ( 1 )
  {
    v16 = *(unsigned int *)(v20 + 4 * v26 + 120);
    if ( (unsigned int)v16 >= 0x80 )
    {
      v27 = *(unsigned int *)(v20 + 16);
      if ( (unsigned int)v16 < (unsigned int)v27 )
        break;
    }
LABEL_55:
    v26 = (unsigned int)(v26 + 1);
    if ( (unsigned int)v26 >= v21 )
      goto LABEL_61;
  }
  v28 = (unsigned int)v16;
  v29 = *(_DWORD *)(v16 + v20) - 64;
  if ( v29 )
  {
    LODWORD(v16) = v29 - 1;
    if ( (_DWORD)v16 )
    {
      if ( (_DWORD)v16 == 1 )
      {
        LODWORD(v16) = v28 + 40;
        if ( v28 + 40 <= v27 )
        {
          if ( *(_DWORD *)(v28 + v20 + 12) )
            v24 = (char *)(v28 + v20 + 32);
          v22 = *(_BYTE **)(v28 + v20 + 24);
          goto LABEL_60;
        }
      }
    }
    else
    {
      LODWORD(v16) = v28 + 56;
      if ( v28 + 56 <= v27 )
      {
        v38 = 1;
        if ( *(_BYTE *)(v28 + v20 + 10) )
          v24 = (char *)(v28 + v20 + 24);
        v25 = *(_BYTE *)(v28 + v20 + 8);
        v22 = *(_BYTE **)(v28 + v20 + 16);
        v23 = *(_BYTE *)(v28 + v20 + 9);
      }
    }
    goto LABEL_54;
  }
  LODWORD(v16) = v28 + 40;
  if ( v28 + 40 > v27 )
  {
LABEL_54:
    if ( v38 )
      goto LABEL_61;
    goto LABEL_55;
  }
  if ( *(_BYTE *)(v28 + v20 + 10) )
    v24 = (char *)(v28 + v20 + 24);
  v22 = *(_BYTE **)(v28 + v20 + 16);
LABEL_60:
  v23 = *(_BYTE *)(v28 + v20 + 9);
  v25 = *(_BYTE *)(v28 + v20 + 8);
LABEL_61:
  if ( v24 )
  {
    v30 = *v24;
    goto LABEL_64;
  }
LABEL_85:
  IofCompleteRequest((PIRP)a2, 0);
  return v8;
}

```

## disassembly

```asm
0x1401a6048  mov     [rsp-8+arg_10], rbx
0x1401a604d  push    rbp
0x1401a604e  push    rsi
0x1401a604f  push    rdi
0x1401a6050  push    r12
0x1401a6052  push    r13
0x1401a6054  push    r14
0x1401a6056  push    r15
0x1401a6058  lea     rbp, [rsp-27h]
0x1401a605d  sub     rsp, 90h
0x1401a6064  mov     rax, cs:__security_cookie
0x1401a606b  xor     rax, rsp
0x1401a606e  mov     [rbp+57h+var_40], rax
0x1401a6072  mov     esi, 1
0x1401a6077  mov     qword ptr [rdx+38h], 0
0x1401a607f  mov     rbx, rdx
0x1401a6082  mov     [rbp+57h+var_58], 0
0x1401a608a  test    [rcx+98h], sil
0x1401a6091  jz      loc_1401A61E6
0x1401a6097  cmp     qword ptr [rcx+268h], 0
0x1401a609f  jz      loc_1401A61E6
0x1401a60a5  mov     r8, [rdx+18h]
0x1401a60a9  test    r8, r8
0x1401a60ac  jz      loc_1401A61DF
0x1401a60b2  mov     rax, [rdx+0B8h]
0x1401a60b9  lea     edx, [rsi+0Fh]
0x1401a60bc  cmp     [rax+10h], edx
0x1401a60bf  jb      loc_1401A61DF
0x1401a60c5  cmp     [r8], si
0x1401a60c9  jnz     loc_1401A61DF
0x1401a60cf  cmp     [r8+2], dx
0x1401a60d4  jb      loc_1401A61DF
0x1401a60da  mov     rdx, rcx
0x1401a60dd  lea     r9, [rbp+57h+var_58]
0x1401a60e1  xor     rdx, [r8+8]
0x1401a60e5  mov     r8b, sil
0x1401a60e8  call    NvmeAdapterFindNvmeController
0x1401a60ed  mov     qword ptr [rbp+57h+var_50], rax
0x1401a60f1  mov     rdi, rax
0x1401a60f4  test    rax, rax
0x1401a60f7  jnz     short loc_1401A6103
0x1401a60f9  mov     edi, 0C0000225h
0x1401a60fe  jmp     loc_1401A61EB
0x1401a6103  mov     rax, [rax+88h]
0x1401a610a  test    sil, al
0x1401a610d  jnz     short loc_1401A612D
0x1401a610f  mov     edi, 0C00000BBh
0x1401a6114  mov     rcx, [rbp+57h+var_58]
0x1401a6118  mov     rcx, [rcx+28h]; RunRefCacheAware
0x1401a611c  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a6123  nop     dword ptr [rax+rax+00h]
0x1401a6128  jmp     loc_1401A61EB
0x1401a612d  cmp     dword ptr [rdi+238h], 0
0x1401a6134  jz      short loc_1401A613D
0x1401a6136  mov     edi, 0C0000010h
0x1401a613b  jmp     short loc_1401A6114
0x1401a613d  test    al, 8
0x1401a613f  jz      short loc_1401A6148
0x1401a6141  mov     edi, 80000011h
0x1401a6146  jmp     short loc_1401A6114
0x1401a6148  or      rax, 8
0x1401a614c  mov     [rdi+88h], rax
0x1401a6153  call    cs:__imp_KeEnterCriticalRegion
0x1401a615a  nop     dword ptr [rax+rax+00h]
0x1401a615f  mov     r14, [rbp+57h+var_58]
0x1401a6163  mov     dl, sil; Wait
0x1401a6166  lea     r15, [r14+278h]
0x1401a616d  mov     rcx, r15; Resource
0x1401a6170  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401a6177  nop     dword ptr [rax+rax+00h]
0x1401a617c  add     rdi, 40h ; '@'
0x1401a6180  mov     rdx, [rdi]
0x1401a6183  cmp     [rdx+8], rdi
0x1401a6187  jnz     short loc_1401A61D8
0x1401a6189  mov     rax, [rdi+8]
0x1401a618d  cmp     [rax], rdi
0x1401a6190  jnz     short loc_1401A61D8
0x1401a6192  mov     [rax], rdx
0x1401a6195  mov     rcx, r15; Resource
0x1401a6198  mov     [rdx+8], rax
0x1401a619c  xor     edi, edi
0x1401a619e  dec     dword ptr [r14+270h]
0x1401a61a5  call    cs:__imp_ExReleaseResourceLite
0x1401a61ac  nop     dword ptr [rax+rax+00h]
0x1401a61b1  call    cs:__imp_KeLeaveCriticalRegion
0x1401a61b8  nop     dword ptr [rax+rax+00h]
0x1401a61bd  mov     rcx, [r14+28h]; RunRefCacheAware
0x1401a61c1  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1401a61c8  nop     dword ptr [rax+rax+00h]
0x1401a61cd  lea     rcx, [rbp+57h+var_50]
0x1401a61d1  call    NvmeAdapterDeleteNvmeController
0x1401a61d6  jmp     short loc_1401A61EB
0x1401a61d8  mov     ecx, 3
0x1401a61dd  int     29h; Win8: RtlFailFast(ecx)
0x1401a61df  mov     edi, 0C000000Dh
0x1401a61e4  jmp     short loc_1401A61EB
0x1401a61e6  mov     edi, 0C00000BBh
0x1401a61eb  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a61f2  mov     byte ptr [rbx+8Dh], 0ACh
0x1401a61f9  mov     [rbx+30h], edi
0x1401a61fc  jz      loc_1401A64BF
0x1401a6202  xorps   xmm0, xmm0
0x1401a6205  lea     rdx, [rbp+57h+var_50]
0x1401a6209  mov     rcx, rbx
0x1401a620c  movups  [rbp+57h+var_50], xmm0
0x1401a6210  call    cs:__imp_IoGetActivityIdIrp
0x1401a6217  nop     dword ptr [rax+rax+00h]
0x1401a621c  mov     rdx, [rbx+0B8h]
0x1401a6223  movzx   eax, byte ptr [rdx]
0x1401a6226  sub     eax, 0Eh
0x1401a6229  jz      loc_1401A649C
0x1401a622f  sub     eax, esi
0x1401a6231  jz      short loc_1401A62A0
0x1401a6233  cmp     eax, 0Ch
0x1401a6236  jnz     loc_1401A64BF
0x1401a623c  cmp     byte ptr [rdx+1], 7
0x1401a6240  jnz     short loc_1401A6280
0x1401a6242  cmp     dword ptr [rdx+8], 0
0x1401a6246  jnz     short loc_1401A6280
0x1401a6248  test    cs:byte_140177432, 40h
0x1401a624f  jz      loc_1401A64BF
0x1401a6255  mov     rax, [rbx+38h]
0x1401a6259  test    rax, rax
0x1401a625c  jz      short loc_1401A6262
0x1401a625e  mov     ecx, [rax]
0x1401a6260  jmp     short loc_1401A6264
0x1401a6262  xor     ecx, ecx
0x1401a6264  mov     eax, [rbx+30h]
0x1401a6267  lea     r8, [rbp+57h+var_50]
0x1401a626b  mov     [rsp+0C0h+var_98], eax
0x1401a626f  mov     r9, rbx
0x1401a6272  mov     [rsp+0C0h+var_A0], ecx
0x1401a6276  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a627b  jmp     loc_1401A64BF
0x1401a6280  test    cs:byte_140177432, 20h
0x1401a6287  jz      loc_1401A64BF
0x1401a628d  mov     eax, [rbx+30h]
0x1401a6290  lea     rdx, EventPnpRequestComplete
0x1401a6297  mov     [rsp+0C0h+var_A0], eax
0x1401a629b  jmp     loc_1401A64B3
0x1401a62a0  cmp     cs:byte_140177431, 0
0x1401a62a7  jge     loc_1401A64BF
0x1401a62ad  mov     rdx, [rdx+8]
0x1401a62b1  movzx   eax, byte ptr [rdx+2]
0x1401a62b5  cmp     al, 28h ; '('
0x1401a62b7  jnz     loc_1401A63A5
0x1401a62bd  cmp     dword ptr [rdx+14h], 0
0x1401a62c1  jnz     loc_1401A64BF
0x1401a62c7  mov     r12d, [rdx+38h]
0x1401a62cb  test    r12d, r12d
0x1401a62ce  jz      loc_1401A64BF
0x1401a62d4  xor     r9d, r9d
0x1401a62d7  xor     r11b, r11b
0x1401a62da  xor     r10d, r10d
0x1401a62dd  mov     [rbp+57h+var_60], r9b
0x1401a62e1  xor     r13b, r13b
0x1401a62e4  xor     r15d, r15d
0x1401a62e7  mov     ecx, [rdx+r15*4+78h]
0x1401a62ec  cmp     ecx, 80h
0x1401a62f2  jb      short loc_1401A636B
0x1401a62f4  mov     r14d, [rdx+10h]
0x1401a62f8  cmp     ecx, r14d
0x1401a62fb  jnb     short loc_1401A636B
0x1401a62fd  mov     r8d, ecx
0x1401a6300  mov     ecx, [rcx+rdx]
0x1401a6303  sub     ecx, 40h ; '@'
0x1401a6306  jz      short loc_1401A635C
0x1401a6308  sub     ecx, esi
0x1401a630a  jz      short loc_1401A632F
0x1401a630c  cmp     ecx, esi
0x1401a630e  jnz     short loc_1401A6365
0x1401a6310  lea     rcx, [r8+28h]
0x1401a6314  cmp     rcx, r14
0x1401a6317  ja      short loc_1401A6365
0x1401a6319  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401a631f  jbe     short loc_1401A6328
0x1401a6321  lea     r10, [rdx+20h]
0x1401a6325  add     r10, r8
0x1401a6328  mov     r9, [r8+rdx+18h]
0x1401a632d  jmp     short loc_1401A638D
0x1401a632f  lea     rcx, [r8+38h]
0x1401a6333  cmp     rcx, r14
0x1401a6336  ja      short loc_1401A6365
0x1401a6338  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a633e  mov     [rbp+57h+var_60], sil
0x1401a6342  jbe     short loc_1401A634B
0x1401a6344  lea     r10, [rdx+18h]
0x1401a6348  add     r10, r8
0x1401a634b  mov     r13b, [r8+rdx+8]
0x1401a6350  mov     r9, [r8+rdx+10h]
0x1401a6355  mov     r11b, [r8+rdx+9]
0x1401a635a  jmp     short loc_1401A6365
0x1401a635c  lea     rcx, [r8+28h]
0x1401a6360  cmp     rcx, r14
0x1401a6363  jbe     short loc_1401A6379
0x1401a6365  cmp     [rbp+57h+var_60], 0
0x1401a6369  jnz     short loc_1401A6397
0x1401a636b  add     r15d, esi
0x1401a636e  cmp     r15d, r12d
0x1401a6371  jb      loc_1401A62E7
0x1401a6377  jmp     short loc_1401A6397
0x1401a6379  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401a637f  jbe     short loc_1401A6388
0x1401a6381  lea     r10, [rdx+18h]
0x1401a6385  add     r10, r8
0x1401a6388  mov     r9, [r8+rdx+10h]
0x1401a638d  mov     r11b, [r8+rdx+9]
0x1401a6392  mov     r13b, [r8+rdx+8]
0x1401a6397  test    r10, r10
0x1401a639a  jz      loc_1401A64BF
0x1401a63a0  mov     cl, [r10]
0x1401a63a3  jmp     short loc_1401A63BC
0x1401a63a5  mov     cl, [rdx+48h]
0x1401a63a8  mov     r9, [rdx+20h]
0x1401a63ac  mov     r11b, [rdx+0Bh]
0x1401a63b0  mov     r13b, [rdx+4]
0x1401a63b4  test    eax, eax
0x1401a63b6  jnz     loc_1401A64BF
0x1401a63bc  sub     cl, 8
0x1401a63bf  test    cl, 5Dh
0x1401a63c2  jnz     loc_1401A64BF
0x1401a63c8  mov     r14b, [rdx+3]
0x1401a63cc  cmp     r14b, sil
0x1401a63cf  jz      loc_1401A6462
0x1401a63d5  test    r9, r9
0x1401a63d8  jz      loc_1401A6462
0x1401a63de  test    r11b, r11b
0x1401a63e1  jz      short loc_1401A6462
0x1401a63e3  mov     al, [r9]
0x1401a63e6  xor     dl, dl
0x1401a63e8  and     al, 7Fh
0x1401a63ea  movzx   ecx, r11b
0x1401a63ee  sub     al, 72h ; 'r'
0x1401a63f0  xor     r10b, r10b
0x1401a63f3  xor     r8b, r8b
0x1401a63f6  add     rcx, r9
0x1401a63f9  cmp     al, sil
0x1401a63fc  lea     rax, [r9+8]
0x1401a6400  jbe     short loc_1401A6444
0x1401a6402  cmp     rax, rcx
0x1401a6405  ja      short loc_1401A645A
0x1401a6407  movzx   ecx, byte ptr [r9+7]
0x1401a640c  lea     r8, [r9+0Dh]
0x1401a6410  mov     dl, [r9+2]
0x1401a6414  add     ecx, 8
0x1401a6417  and     dl, 0Fh
0x1401a641a  movzx   eax, r11b
0x1401a641e  cmp     ecx, eax
0x1401a6420  cmovbe  eax, ecx
0x1401a6423  mov     ecx, eax
0x1401a6425  add     rcx, r9
0x1401a6428  cmp     r8, rcx
0x1401a642b  ja      short loc_1401A6431
0x1401a642d  mov     r10b, [r9+0Ch]
0x1401a6431  lea     rax, [r9+0Eh]
0x1401a6435  cmp     rax, rcx
0x1401a6438  ja      short loc_1401A643F
0x1401a643a  mov     r8b, [r8]
0x1401a643d  jmp     short loc_1401A645D
0x1401a643f  xor     r8b, r8b
0x1401a6442  jmp     short loc_1401A645D
0x1401a6444  cmp     rax, rcx
0x1401a6447  ja      short loc_1401A645A
0x1401a6449  mov     dl, [r9+1]
0x1401a644d  mov     r10b, [r9+2]
0x1401a6451  and     dl, 0Fh
0x1401a6454  mov     r8b, [r9+3]
0x1401a6458  jmp     short loc_1401A645D
0x1401a645a  xor     sil, sil
0x1401a645d  test    sil, sil
0x1401a6460  jnz     short loc_1401A646A
0x1401a6462  xor     dl, dl
0x1401a6464  xor     r10b, r10b
0x1401a6467  xor     r8b, r8b
0x1401a646a  mov     eax, [rbx+30h]
0x1401a646d  mov     r9, rbx
0x1401a6470  mov     [rsp+0C0h+var_70], rbx
0x1401a6475  mov     [rsp+0C0h+var_78], r8b
0x1401a647a  lea     r8, [rbp+57h+var_50]
0x1401a647e  mov     [rsp+0C0h+var_80], r10b
0x1401a6483  mov     [rsp+0C0h+var_88], dl
0x1401a6487  mov     [rsp+0C0h+var_90], r13b
0x1401a648c  mov     byte ptr [rsp+0C0h+var_98], r14b
0x1401a6491  mov     [rsp+0C0h+var_A0], eax
0x1401a6495  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401a649a  jmp     short loc_1401A64BF
0x1401a649c  test    cs:byte_140177432, 8
0x1401a64a3  jz      short loc_1401A64BF
0x1401a64a5  mov     edx, [rbx+30h]
0x1401a64a8  mov     [rsp+0C0h+var_A0], edx
0x1401a64ac  lea     rdx, EventNonReadWriteRequestComplete
0x1401a64b3  mov     r9, rbx
0x1401a64b6  lea     r8, [rbp+57h+var_50]
0x1401a64ba  call    McTemplateK0pd_EtwWriteTransfer
0x1401a64bf  xor     edx, edx; PriorityBoost
0x1401a64c1  mov     rcx, rbx; Irp
0x1401a64c4  call    cs:__imp_IofCompleteRequest
0x1401a64cb  nop     dword ptr [rax+rax+00h]
0x1401a64d0  mov     eax, edi
0x1401a64d2  mov     rcx, [rbp+57h+var_40]
  ... truncated ...
```
