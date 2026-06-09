# NvmeNamespaceCompleteNvmRequest

- ea: `0x14011ce10`
- end: `0x14011d428`
- name: `NvmeNamespaceCompleteNvmRequest`
- size: `1560`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14011b3c8`
- `0x14011bd30`
- `0x14011ce10`
- `0x1401265c0`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14011d13d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14011d13d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011cf18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011cf40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011cf18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011cf40`
- `ntoskrnl!IofCompleteRequest` at `0x14011d3f7`
- `ntoskrnl!IofCompleteRequest` at `0x14011d3f7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14011d100`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14011d100`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x14011cf2c`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x14011cf2c`

## pseudocode

```c
void __fastcall NvmeNamespaceCompleteNvmRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *P)
{
  unsigned __int8 v6; // r12
  unsigned int v7; // r10d
  char v11; // si
  unsigned int v12; // r8d
  __int64 i; // rcx
  __int64 v14; // rdx
  __int64 v15; // r15
  void *v16; // rcx
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  __int64 j; // rdx
  __int64 v20; // rcx
  char v21; // al
  unsigned __int16 v22; // r9
  const int *v23; // r11
  int v24; // r8d
  __int64 v25; // r9
  bool v26; // zf
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  int *v29; // rax
  int v30; // ecx
  __int64 *v31; // rdx
  __int64 v32; // rdx
  unsigned int v33; // r15d
  unsigned __int8 v34; // r10
  char *v35; // r11
  char v36; // di
  _BYTE *v37; // r9
  unsigned int v38; // r14d
  char v39; // r12
  unsigned __int64 v40; // rbp
  __int64 v41; // r8
  int v42; // ecx
  char v43; // cl
  char v44; // bp
  char v45; // r11
  _BYTE *v46; // rax
  char v47; // r8
  char *v48; // r8
  unsigned int v49; // eax
  __int128 v51; // [rsp+B8h] [rbp-60h] BYREF

  v6 = 4;
  v7 = a4;
  *(_QWORD *)&v51 = *(_QWORD *)(a1 + 128);
  v11 = 1;
  if ( *(_BYTE *)(a5 + 684) )
    v6 = *(_BYTE *)(a5 + 684);
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    v12 = *(_DWORD *)(a2 + 56);
    if ( v12 )
    {
      for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
      {
        v14 = *(unsigned int *)(a2 + 4 * i + 120);
        if ( (unsigned int)v14 >= 0x80 && (unsigned int)v14 < *(_DWORD *)(a2 + 16) )
        {
          v15 = a2 + v14;
          if ( *(_DWORD *)(a2 + v14) == 67 )
            goto LABEL_12;
        }
      }
    }
  }
  v15 = 0;
LABEL_12:
  if ( P )
  {
    if ( (unsigned __int8)*(_DWORD *)(v15 + 16) == 9 && (*(_DWORD *)(v15 + 60) & 4) != 0 )
    {
      *(_QWORD *)(a2 + 64) = P[1];
      *(_DWORD *)(a2 + 60) = *((_DWORD *)P + 4);
      a3 = *P;
      v16 = (void *)P[3];
      v17 = 16 * *((_DWORD *)P + 5);
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + 408LL) + 184LL) & 0x2000) != 0 && v17 <= 0x1000 )
        ExFreePoolWithTag(v16, 0x52436152u);
      else
        MmFreeContiguousMemorySpecifyCache(v16, v17, MmCached);
    }
    ExFreePoolWithTag(P, 0x4D4E6152u);
    v7 = a4;
  }
  if ( *(_BYTE *)(a2 + 2) == 40 )
  {
    v18 = *(_DWORD *)(a2 + 56);
    if ( v18 )
    {
      for ( j = 0; (unsigned int)j < v18; j = (unsigned int)(j + 1) )
      {
        v20 = *(unsigned int *)(a2 + 4 * j + 120);
        if ( (unsigned int)v20 >= 0x80
          && (unsigned int)v20 < *(_DWORD *)(a2 + 16)
          && (unsigned int)(*(_DWORD *)(v20 + a2) - 64) <= 2 )
        {
          *(_DWORD *)(a2 + 20) = 0;
          break;
        }
      }
    }
  }
  v21 = *(_BYTE *)(a2 + 3);
  if ( v21 == 37 || v21 == 14 )
  {
    v25 = *(_QWORD *)(a3 + 184);
    *(_QWORD *)(v25 + 32) = (unsigned int)(*(_DWORD *)(v25 + 32) + 1);
    if ( *(_DWORD *)(v25 + 32) <= (unsigned int)v6 )
    {
      NvmeNamespaceQueueRequest(a5, a3, v7);
      return;
    }
    NvmeMapStatus(a2);
    _InterlockedAdd64((volatile signed __int64 *)(a5 + 192), 1u);
  }
  else
  {
    NvmeMapStatus(a2);
    if ( (*(_BYTE *)(a2 + 3) & 0x3F) != 1 )
    {
      _InterlockedAdd64((volatile signed __int64 *)(a5 + 192), 1u);
      if ( (byte_14017743A & 2) != 0 )
      {
        v22 = *(_WORD *)(v15 + 86);
        v23 = &dword_140157D94;
        v24 = v22;
        if ( *(_QWORD *)(a1 + 752) )
          v23 = *(const int **)(a1 + 752);
        LOWORD(v24) = v22 >> 1;
        McTemplateK0qjzshqusssuuuqqqqqq_EtwWriteTransfer(
          a1 + 841,
          a1 + 800,
          v24,
          *(_DWORD *)(v51 + 56),
          v51 + 1048,
          *(_QWORD *)(v51 + 1032),
          *(_QWORD *)(a1 + 792),
          *(_WORD *)(a1 + 4),
          *(_DWORD *)(a5 + 56),
          *(_BYTE *)(a1 + 744),
          (__int64)v23,
          a1 + 800,
          a1 + 841,
          *(_BYTE *)(v15 + 16),
          (v22 >> 9) & 7,
          v22 >> 1,
          *(_DWORD *)(v15 + 56),
          *(_DWORD *)(v15 + 60),
          *(_DWORD *)(v15 + 64),
          *(_DWORD *)(v15 + 68),
          *(_DWORD *)(v15 + 72),
          *(_DWORD *)(v15 + 76));
      }
    }
  }
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a5 + 120));
  *(_BYTE *)(a3 + 141) = -84;
  v26 = StorEtwLoggingEnabled == 0;
  *(_DWORD *)(a3 + 48) = 0;
  if ( v26 )
    goto LABEL_103;
  v51 = 0;
  IoGetActivityIdIrp(a3, &v51);
  v28 = *(_QWORD *)(a3 + 184);
  if ( *(_BYTE *)v28 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_103;
    v31 = EventNonReadWriteRequestComplete;
    goto LABEL_102;
  }
  if ( *(_BYTE *)v28 != 15 )
  {
    if ( *(_BYTE *)v28 != 27 )
      goto LABEL_103;
    if ( *(_BYTE *)(v28 + 1) == 7 && !*(_DWORD *)(v28 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v29 = *(int **)(a3 + 56);
        if ( v29 )
          v30 = *v29;
        else
          v30 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v30, v28, (unsigned int)&v51, a3, v30, *(_DWORD *)(a3 + 48));
      }
      goto LABEL_103;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_103;
    v31 = EventPnpRequestComplete;
LABEL_102:
    McTemplateK0pd_EtwWriteTransfer(v27, v31, &v51, a3, *(_DWORD *)(a3 + 48));
    goto LABEL_103;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_103;
  v32 = *(_QWORD *)(v28 + 8);
  if ( *(_BYTE *)(v32 + 2) == 40 )
  {
    if ( *(_DWORD *)(v32 + 20) )
      goto LABEL_103;
    v33 = *(_DWORD *)(v32 + 56);
    if ( !v33 )
      goto LABEL_103;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    while ( 1 )
    {
      v27 = *(unsigned int *)(v32 + 4LL * v38 + 120);
      if ( (unsigned int)v27 >= 0x80 )
      {
        v40 = *(unsigned int *)(v32 + 16);
        if ( (unsigned int)v27 < (unsigned int)v40 )
        {
          v41 = (unsigned int)v27;
          v42 = *(_DWORD *)(v27 + v32) - 64;
          if ( v42 )
          {
            LODWORD(v27) = v42 - 1;
            if ( (_DWORD)v27 )
            {
              if ( (_DWORD)v27 == 1 )
              {
                LODWORD(v27) = v41 + 40;
                if ( v41 + 40 <= v40 )
                {
                  if ( *(_DWORD *)(v41 + v32 + 12) )
                    v35 = (char *)(v41 + v32 + 32);
                  v37 = *(_BYTE **)(v41 + v32 + 24);
                  goto LABEL_77;
                }
              }
            }
            else
            {
              LODWORD(v27) = v41 + 56;
              if ( v41 + 56 <= v40 )
              {
                v39 = 1;
                if ( *(_BYTE *)(v41 + v32 + 10) )
                  v35 = (char *)(v41 + v32 + 24);
                v36 = *(_BYTE *)(v41 + v32 + 8);
                v37 = *(_BYTE **)(v41 + v32 + 16);
                v34 = *(_BYTE *)(v41 + v32 + 9);
              }
            }
          }
          else
          {
            LODWORD(v27) = v41 + 40;
            if ( v41 + 40 <= v40 )
            {
              if ( *(_BYTE *)(v41 + v32 + 10) )
                v35 = (char *)(v41 + v32 + 24);
              v37 = *(_BYTE **)(v41 + v32 + 16);
LABEL_77:
              v34 = *(_BYTE *)(v41 + v32 + 9);
              v36 = *(_BYTE *)(v41 + v32 + 8);
LABEL_78:
              if ( v35 )
              {
                v43 = *v35;
                goto LABEL_81;
              }
              goto LABEL_103;
            }
          }
          if ( v39 )
            goto LABEL_78;
        }
      }
      if ( ++v38 >= v33 )
        goto LABEL_78;
    }
  }
  v43 = *(_BYTE *)(v32 + 72);
  v37 = *(_BYTE **)(v32 + 32);
  v34 = *(_BYTE *)(v32 + 11);
  v36 = *(_BYTE *)(v32 + 4);
  if ( *(_BYTE *)(v32 + 2) )
    goto LABEL_103;
LABEL_81:
  LOBYTE(v27) = v43 - 8;
  if ( (v27 & 0x5D) == 0 )
  {
    v44 = *(_BYTE *)(v32 + 3);
    if ( v44 == 1 || !v37 || !v34 )
      goto LABEL_98;
    LOBYTE(v32) = 0;
    v27 = (unsigned __int64)&v37[v34];
    v45 = 0;
    v46 = v37 + 8;
    v47 = 0;
    if ( (unsigned __int8)((*v37 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v46 <= v27 )
      {
        v45 = v37[2];
        LOBYTE(v32) = v37[1] & 0xF;
        v47 = v37[3];
        goto LABEL_97;
      }
    }
    else if ( (unsigned __int64)v46 <= v27 )
    {
      v48 = v37 + 13;
      LOBYTE(v32) = v37[2] & 0xF;
      v49 = v34;
      if ( (unsigned int)(unsigned __int8)v37[7] + 8 <= v34 )
        v49 = (unsigned __int8)v37[7] + 8;
      v27 = (unsigned __int64)&v37[v49];
      if ( (unsigned __int64)v48 <= v27 )
        v45 = v37[12];
      if ( (unsigned __int64)(v37 + 14) > v27 )
        v47 = 0;
      else
        v47 = *v48;
LABEL_97:
      if ( v11 )
      {
LABEL_99:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v27,
          v32,
          (unsigned int)&v51,
          a3,
          *(_DWORD *)(a3 + 48),
          v44,
          v36,
          v32,
          v45,
          v47,
          a3);
        goto LABEL_103;
      }
LABEL_98:
      LOBYTE(v32) = 0;
      v45 = 0;
      v47 = 0;
      goto LABEL_99;
    }
    v11 = 0;
    goto LABEL_97;
  }
LABEL_103:
  IofCompleteRequest((PIRP)a3, 0);
}

```

## disassembly

```asm
0x14011ce10  push    rbx
0x14011ce12  push    rbp
0x14011ce13  push    rsi
0x14011ce14  push    rdi
0x14011ce15  push    r12
0x14011ce17  push    r13
0x14011ce19  push    r14
0x14011ce1b  push    r15
0x14011ce1d  sub     rsp, 0D8h
0x14011ce24  mov     rax, cs:__security_cookie
0x14011ce2b  xor     rax, rsp
0x14011ce2e  mov     [rsp+118h+var_50], rax
0x14011ce36  mov     rax, [rcx+80h]
0x14011ce3d  mov     r12d, 4
0x14011ce43  mov     rbp, [rsp+118h+arg_20]
0x14011ce4b  mov     r10d, r9d
0x14011ce4e  mov     r14, [rsp+118h+P]
0x14011ce56  mov     rbx, r8
0x14011ce59  mov     qword ptr [rsp+118h+var_60], rax
0x14011ce61  mov     rdi, rdx
0x14011ce64  mov     [rsp+118h+var_68], r9d
0x14011ce6c  mov     r13, rcx
0x14011ce6f  movzx   eax, byte ptr [rbp+2ACh]
0x14011ce76  mov     esi, 1
0x14011ce7b  test    al, al
0x14011ce7d  cmovnz  r12d, eax
0x14011ce81  cmp     byte ptr [rdx+2], 28h ; '('
0x14011ce85  jnz     short loc_14011CEB6
0x14011ce87  mov     r8d, [rdx+38h]
0x14011ce8b  test    r8d, r8d
0x14011ce8e  jz      short loc_14011CEB6
0x14011ce90  xor     ecx, ecx
0x14011ce92  cmp     ecx, r8d
0x14011ce95  jnb     short loc_14011CEB6
0x14011ce97  mov     edx, [rdi+rcx*4+78h]
0x14011ce9b  cmp     edx, 80h
0x14011cea1  jb      short loc_14011CEB2
0x14011cea3  cmp     edx, [rdi+10h]
0x14011cea6  jnb     short loc_14011CEB2
0x14011cea8  lea     r15, [rdi+rdx]
0x14011ceac  cmp     dword ptr [r15], 43h ; 'C'
0x14011ceb0  jz      short loc_14011CEB9
0x14011ceb2  add     ecx, esi
0x14011ceb4  jmp     short loc_14011CE92
0x14011ceb6  xor     r15d, r15d
0x14011ceb9  test    r14, r14
0x14011cebc  jz      loc_14011CF54
0x14011cec2  mov     eax, [r15+10h]
0x14011cec6  cmp     al, 9
0x14011cec8  jnz     short loc_14011CF38
0x14011ceca  mov     eax, [r15+3Ch]
0x14011cece  test    al, 4
0x14011ced0  jz      short loc_14011CF38
0x14011ced2  mov     rax, [r14+8]
0x14011ced6  mov     [rdi+40h], rax
0x14011ceda  mov     eax, [r14+10h]
0x14011cede  mov     [rdi+3Ch], eax
0x14011cee1  mov     rax, [r13+80h]
0x14011cee8  mov     r8d, [r14+14h]
0x14011ceec  mov     rbx, [r14]
0x14011ceef  mov     rcx, [r14+18h]; BaseAddress
0x14011cef3  mov     rdx, [rax+198h]
0x14011cefa  shl     r8d, 4
0x14011cefe  test    dword ptr [rdx+0B8h], 2000h
0x14011cf08  jz      short loc_14011CF26
0x14011cf0a  cmp     r8d, 1000h
0x14011cf11  ja      short loc_14011CF26
0x14011cf13  mov     edx, 52436152h; Tag
0x14011cf18  call    cs:__imp_ExFreePoolWithTag
0x14011cf1f  nop     dword ptr [rax+rax+00h]
0x14011cf24  jmp     short loc_14011CF38
0x14011cf26  mov     edx, r8d; NumberOfBytes
0x14011cf29  mov     r8d, esi; CacheType
0x14011cf2c  call    cs:__imp_MmFreeContiguousMemorySpecifyCache
0x14011cf33  nop     dword ptr [rax+rax+00h]
0x14011cf38  mov     edx, 4D4E6152h; Tag
0x14011cf3d  mov     rcx, r14; P
0x14011cf40  call    cs:__imp_ExFreePoolWithTag
0x14011cf47  nop     dword ptr [rax+rax+00h]
0x14011cf4c  mov     r10d, [rsp+118h+var_68]
0x14011cf54  cmp     byte ptr [rdi+2], 28h ; '('
0x14011cf58  jnz     short loc_14011CF91
0x14011cf5a  mov     r8d, [rdi+38h]
0x14011cf5e  test    r8d, r8d
0x14011cf61  jz      short loc_14011CF91
0x14011cf63  xor     edx, edx
0x14011cf65  cmp     edx, r8d
0x14011cf68  jnb     short loc_14011CF91
0x14011cf6a  mov     ecx, [rdi+rdx*4+78h]
0x14011cf6e  cmp     ecx, 80h
0x14011cf74  jb      short loc_14011CF86
0x14011cf76  cmp     ecx, [rdi+10h]
0x14011cf79  jnb     short loc_14011CF86
0x14011cf7b  mov     ecx, [rcx+rdi]
0x14011cf7e  sub     ecx, 40h ; '@'
0x14011cf81  cmp     ecx, 2
0x14011cf84  jbe     short loc_14011CF8A
0x14011cf86  add     edx, esi
0x14011cf88  jmp     short loc_14011CF65
0x14011cf8a  mov     dword ptr [rdi+14h], 0
0x14011cf91  mov     al, [rdi+3]
0x14011cf94  cmp     al, 25h ; '%'
0x14011cf96  jz      loc_14011D0BE
0x14011cf9c  cmp     al, 0Eh
0x14011cf9e  jz      loc_14011D0BE
0x14011cfa4  mov     rcx, rdi
0x14011cfa7  call    NvmeMapStatus
0x14011cfac  mov     al, [rdi+3]
0x14011cfaf  and     al, 3Fh
0x14011cfb1  cmp     al, sil
0x14011cfb4  jz      loc_14011D0FC
0x14011cfba  lock add [rbp+0C0h], rsi
0x14011cfc2  test    cs:byte_14017743A, 2
0x14011cfc9  jz      loc_14011D0FC
0x14011cfcf  mov     rax, [r13+2F0h]
0x14011cfd6  lea     rcx, [r13+349h]
0x14011cfdd  movzx   r9d, word ptr [r15+56h]
0x14011cfe2  lea     rdx, [r13+320h]
0x14011cfe9  mov     rdi, qword ptr [rsp+118h+var_60]
0x14011cff1  lea     r11, dword_140157D94
0x14011cff8  test    rax, rax
0x14011cffb  movzx   r8d, r9w
0x14011cfff  cmovnz  r11, rax
0x14011d003  shr     r8w, 1
0x14011d007  mov     eax, [r15+4Ch]
0x14011d00b  lea     r10, [rdi+418h]
0x14011d012  mov     [rsp+118h+var_70], eax
0x14011d019  mov     eax, [r15+48h]
0x14011d01d  mov     [rsp+118h+var_78], eax
0x14011d024  mov     eax, [r15+44h]
0x14011d028  mov     [rsp+118h+var_80], eax
0x14011d02f  mov     eax, [r15+40h]
0x14011d033  mov     [rsp+118h+var_88], eax
0x14011d03a  mov     eax, [r15+3Ch]
0x14011d03e  mov     [rsp+118h+var_90], eax
0x14011d045  mov     eax, [r15+38h]
0x14011d049  mov     [rsp+118h+var_98], eax
0x14011d050  mov     al, [r15+10h]
0x14011d054  mov     [rsp+118h+var_A0], r8b
0x14011d059  shr     r9w, 9
0x14011d05e  and     r9b, 7
0x14011d062  mov     [rsp+118h+var_A8], r9b
0x14011d067  mov     r9d, [rdi+38h]
0x14011d06b  mov     [rsp+118h+var_B0], al
0x14011d06f  mov     al, [r13+2E8h]
0x14011d076  mov     [rsp+118h+var_B8], rcx
0x14011d07b  mov     [rsp+118h+var_C0], rdx
0x14011d080  mov     [rsp+118h+var_C8], r11
0x14011d085  mov     [rsp+118h+var_D0], al
0x14011d089  mov     eax, [rbp+38h]
0x14011d08c  mov     [rsp+118h+var_D8], eax
0x14011d090  movzx   eax, word ptr [r13+4]
0x14011d095  mov     [rsp+118h+var_E0], ax
0x14011d09a  mov     rax, [r13+318h]
0x14011d0a1  mov     [rsp+118h+var_E8], rax
0x14011d0a6  mov     rax, [rdi+408h]
0x14011d0ad  mov     [rsp+118h+var_F0], rax
0x14011d0b2  mov     [rsp+118h+var_F8], r10
0x14011d0b7  call    McTemplateK0qjzshqusssuuuqqqqqq_EtwWriteTransfer
0x14011d0bc  jmp     short loc_14011D0FC
0x14011d0be  mov     r9, [rbx+0B8h]
0x14011d0c5  mov     eax, [r9+20h]
0x14011d0c9  add     eax, esi
0x14011d0cb  mov     [r9+20h], rax
0x14011d0cf  movzx   eax, r12b
0x14011d0d3  cmp     [r9+20h], eax
0x14011d0d7  ja      short loc_14011D0EC
0x14011d0d9  mov     r8d, r10d
0x14011d0dc  mov     rdx, rbx
0x14011d0df  mov     rcx, rbp
0x14011d0e2  call    NvmeNamespaceQueueRequest
0x14011d0e7  jmp     loc_14011D403
0x14011d0ec  mov     rcx, rdi
0x14011d0ef  call    NvmeMapStatus
0x14011d0f4  lock add [rbp+0C0h], rsi
0x14011d0fc  mov     rcx, [rbp+78h]; RunRefCacheAware
0x14011d100  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14011d107  nop     dword ptr [rax+rax+00h]
0x14011d10c  xor     r13d, r13d
0x14011d10f  mov     byte ptr [rbx+8Dh], 0ACh
0x14011d116  cmp     cs:StorEtwLoggingEnabled, r13b
0x14011d11d  mov     [rbx+30h], r13d
0x14011d121  jz      loc_14011D3F2
0x14011d127  xorps   xmm0, xmm0
0x14011d12a  lea     rdx, [rsp+118h+var_60]
0x14011d132  mov     rcx, rbx
0x14011d135  movups  [rsp+118h+var_60], xmm0
0x14011d13d  call    cs:__imp_IoGetActivityIdIrp
0x14011d144  nop     dword ptr [rax+rax+00h]
0x14011d149  mov     rdx, [rbx+0B8h]
0x14011d150  movzx   eax, byte ptr [rdx]
0x14011d153  sub     eax, 0Eh
0x14011d156  jz      loc_14011D3CB
0x14011d15c  sub     eax, esi
0x14011d15e  jz      short loc_14011D1CB
0x14011d160  cmp     eax, 0Ch
0x14011d163  jnz     loc_14011D3F2
0x14011d169  cmp     byte ptr [rdx+1], 7
0x14011d16d  jnz     short loc_14011D1B2
0x14011d16f  cmp     [rdx+8], r13d
0x14011d173  jnz     short loc_14011D1B2
0x14011d175  test    cs:byte_140177432, 40h
0x14011d17c  jz      loc_14011D3F2
0x14011d182  mov     rax, [rbx+38h]
0x14011d186  test    rax, rax
0x14011d189  jz      short loc_14011D18F
0x14011d18b  mov     ecx, [rax]
0x14011d18d  jmp     short loc_14011D192
0x14011d18f  mov     ecx, r13d
0x14011d192  mov     eax, [rbx+30h]
0x14011d195  lea     r8, [rsp+118h+var_60]
0x14011d19d  mov     dword ptr [rsp+118h+var_F0], eax
0x14011d1a1  mov     r9, rbx
0x14011d1a4  mov     dword ptr [rsp+118h+var_F8], ecx
0x14011d1a8  call    McTemplateK0pqd_EtwWriteTransfer
0x14011d1ad  jmp     loc_14011D3F2
0x14011d1b2  test    cs:byte_140177432, 20h
0x14011d1b9  jz      loc_14011D3F2
0x14011d1bf  lea     rdx, EventPnpRequestComplete
0x14011d1c6  jmp     loc_14011D3DB
0x14011d1cb  cmp     cs:byte_140177431, r13b
0x14011d1d2  jge     loc_14011D3F2
0x14011d1d8  mov     rdx, [rdx+8]
0x14011d1dc  movzx   eax, byte ptr [rdx+2]
0x14011d1e0  cmp     al, 28h ; '('
0x14011d1e2  jnz     loc_14011D2CA
0x14011d1e8  cmp     [rdx+14h], r13d
0x14011d1ec  jnz     loc_14011D3F2
0x14011d1f2  mov     r15d, [rdx+38h]
0x14011d1f6  test    r15d, r15d
0x14011d1f9  jz      loc_14011D3F2
0x14011d1ff  mov     r10b, r13b
0x14011d202  mov     r11, r13
0x14011d205  mov     dil, r13b
0x14011d208  mov     r9, r13
0x14011d20b  mov     r14d, r13d
0x14011d20e  mov     r12b, r13b
0x14011d211  mov     eax, r14d
0x14011d214  mov     ecx, [rdx+rax*4+78h]
0x14011d218  cmp     ecx, 80h
0x14011d21e  jb      short loc_14011D291
0x14011d220  mov     ebp, [rdx+10h]
0x14011d223  cmp     ecx, ebp
0x14011d225  jnb     short loc_14011D291
0x14011d227  mov     r8d, ecx
0x14011d22a  mov     ecx, [rcx+rdx]
0x14011d22d  sub     ecx, 40h ; '@'
0x14011d230  jz      short loc_14011D283
0x14011d232  sub     ecx, esi
0x14011d234  jz      short loc_14011D258
0x14011d236  cmp     ecx, esi
0x14011d238  jnz     short loc_14011D28C
0x14011d23a  lea     rcx, [r8+28h]
0x14011d23e  cmp     rcx, rbp
0x14011d241  ja      short loc_14011D28C
0x14011d243  cmp     [r8+rdx+0Ch], r13d
0x14011d248  jbe     short loc_14011D251
0x14011d24a  lea     r11, [rdx+20h]
0x14011d24e  add     r11, r8
0x14011d251  mov     r9, [r8+rdx+18h]
0x14011d256  jmp     short loc_14011D2B2
0x14011d258  lea     rcx, [r8+38h]
0x14011d25c  cmp     rcx, rbp
0x14011d25f  ja      short loc_14011D28C
0x14011d261  mov     r12b, sil
0x14011d264  cmp     [r8+rdx+0Ah], r13b
0x14011d269  jbe     short loc_14011D272
0x14011d26b  lea     r11, [rdx+18h]
0x14011d26f  add     r11, r8
0x14011d272  mov     dil, [r8+rdx+8]
0x14011d277  mov     r9, [r8+rdx+10h]
0x14011d27c  mov     r10b, [r8+rdx+9]
0x14011d281  jmp     short loc_14011D28C
0x14011d283  lea     rcx, [r8+28h]
0x14011d287  cmp     rcx, rbp
0x14011d28a  jbe     short loc_14011D29F
0x14011d28c  test    r12b, r12b
0x14011d28f  jnz     short loc_14011D2BC
0x14011d291  add     r14d, esi
0x14011d294  cmp     r14d, r15d
0x14011d297  jb      loc_14011D211
0x14011d29d  jmp     short loc_14011D2BC
0x14011d29f  cmp     [r8+rdx+0Ah], r13b
0x14011d2a4  jbe     short loc_14011D2AD
0x14011d2a6  lea     r11, [rdx+18h]
0x14011d2aa  add     r11, r8
0x14011d2ad  mov     r9, [r8+rdx+10h]
0x14011d2b2  mov     r10b, [r8+rdx+9]
0x14011d2b7  mov     dil, [r8+rdx+8]
0x14011d2bc  test    r11, r11
0x14011d2bf  jz      loc_14011D3F2
0x14011d2c5  mov     cl, [r11]
0x14011d2c8  jmp     short loc_14011D2E1
0x14011d2ca  mov     cl, [rdx+48h]
0x14011d2cd  mov     r9, [rdx+20h]
0x14011d2d1  mov     r10b, [rdx+0Bh]
0x14011d2d5  mov     dil, [rdx+4]
0x14011d2d9  test    eax, eax
0x14011d2db  jnz     loc_14011D3F2
0x14011d2e1  sub     cl, 8
  ... truncated ...
```
