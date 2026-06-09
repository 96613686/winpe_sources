# VsmmHostAccesspAcqRelProcessBatch

- ea: `0x1400ec5c4`
- end: `0x1400ec901`
- name: `VsmmHostAccesspAcqRelProcessBatch`
- size: `829`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140074030`
- `0x1400ec584`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021db0`
- `0x140028934`
- `0x1400768a0`
- `0x1400ec5c4`

## import_xrefs

- `winhvr!WinHvAcquireSparseSpaPageHostAccess` at `0x1400ec6e0`
- `winhvr!WinHvAcquireSparseSpaPageHostAccess` at `0x1400ec6e0`
- `winhvr!WinHvReleaseSparseSpaPageHostAccess` at `0x1400ec710`
- `winhvr!WinHvReleaseSparseSpaPageHostAccess` at `0x1400ec710`
- `winhvr!WinHvAcquireSparseGpaPageHostAccess` at `0x1400ec73d`
- `winhvr!WinHvAcquireSparseGpaPageHostAccess` at `0x1400ec73d`
- `winhvr!WinHvReleaseSparseGpaPageHostAccess` at `0x1400ec74b`
- `winhvr!WinHvReleaseSparseGpaPageHostAccess` at `0x1400ec74b`

## string_xrefs

- `0x1400ec78a`: `VsmmHostAccesspAcqRelProcessBatch`
- `0x1400ec79a`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`

## pseudocode

```c
__int64 __fastcall VsmmHostAccesspAcqRelProcessBatch(__int64 *a1)
{
  __int64 v1; // r8
  int v4; // ecx
  int v5; // ecx
  unsigned int v6; // edi
  __int64 v7; // r8
  int v8; // r9d
  int *v9; // r14
  __int64 *v10; // rsi
  unsigned int v11; // ecx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // ecx
  int v15; // edx
  int v16; // eax
  __int64 v17; // r10
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  unsigned int v21; // r15d
  __int64 v22; // rdx
  __int64 v23; // rdx
  void (__fastcall *v24)(__int64 *, __int64); // r8
  __int64 v25; // rdx
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v28; // [rsp+3Ch] [rbp-C4h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh] BYREF
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  char v36[32]; // [rsp+70h] [rbp-90h] BYREF
  char v37[16]; // [rsp+90h] [rbp-70h] BYREF
  char v38[16]; // [rsp+A0h] [rbp-60h] BYREF
  int *v39; // [rsp+B0h] [rbp-50h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  unsigned int *v41; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 *v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  int *v45; // [rsp+E0h] [rbp-20h]
  __int64 v46; // [rsp+E8h] [rbp-18h]
  int *v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  int *v49; // [rsp+100h] [rbp+0h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  int *v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]
  unsigned int *v53; // [rsp+120h] [rbp+20h]
  __int64 v54; // [rsp+128h] [rbp+28h]
  __int64 *v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]

  v1 = a1[13];
  v26 = 0;
  if ( !v1 )
    return 0;
  v4 = *((_DWORD *)a1 + 4);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 1 )
        v6 = 5;
      else
        v6 = 7;
    }
    else
    {
      v6 = 4;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( !(unsigned __int8)VsmmHostAccesspAcqRelBySpa(a1) )
  {
    v19 = *a1;
    v9 = (int *)a1 + 5;
    v10 = a1 + 12;
    v20 = a1[12];
    if ( *((_DWORD *)a1 + 5) )
      v13 = WinHvAcquireSparseGpaPageHostAccess(v19, v6, v7, v20, &v26);
    else
      v13 = WinHvReleaseSparseGpaPageHostAccess(v19, v6, v7, v20, &v26);
    goto LABEL_33;
  }
  v6 &= ~4u;
  v8 = a1[3] & 1;
  if ( !v8 || *((_DWORD *)a1 + 2) != 1 )
  {
    v14 = 0;
    if ( *((_DWORD *)a1 + 30) == 2 )
    {
      v14 = 4;
    }
    else if ( *((_DWORD *)a1 + 30) == 3 )
    {
      v14 = 8;
    }
    v9 = (int *)a1 + 5;
    v15 = *((_DWORD *)a1 + 5);
    if ( v15 )
    {
      v16 = v14 | 2;
      if ( !v8 )
        v16 = v14;
      v14 = v16;
    }
    else if ( v8 )
    {
      v17 = *a1;
      v14 |= 1u;
LABEL_25:
      v10 = a1 + 12;
      v18 = a1[12];
      if ( v15 )
        v13 = WinHvAcquireSparseSpaPageHostAccess(v6, v14, v7, v18, &v26);
      else
        v13 = WinHvReleaseSparseSpaPageHostAccess(v17, v6, v14, v7, v18, &v26);
      goto LABEL_33;
    }
    v17 = 0;
    goto LABEL_25;
  }
  v9 = (int *)a1 + 5;
  v10 = a1 + 12;
  v11 = (*((_DWORD *)a1 + 5) != 0) + 1;
  v12 = v11 | 4;
  if ( *((_DWORD *)a1 + 30) != 2 )
    v12 = v11;
  v13 = VsmmSvcpCallModifySpaPageOwnership(*a1, v12, a1[12], v7, &v26);
LABEL_33:
  v21 = v13;
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmHostAccesspAcqRelProcessBatch");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
      v22 = *v10;
      v39 = &v27;
      v27 = 1439;
      v41 = &v28;
      v34 = *a1;
      v43 = &v34;
      v29 = *v9;
      v45 = &v29;
      v30 = *((_DWORD *)a1 + 6);
      v47 = &v30;
      v31 = *((_DWORD *)a1 + 2);
      v49 = &v31;
      v32 = *((_DWORD *)a1 + 3);
      v51 = &v32;
      v53 = &v33;
      v40 = 4;
      v28 = v21;
      v42 = 4;
      v44 = 8;
      v46 = 4;
      v48 = 4;
      v50 = 4;
      v52 = 4;
      v33 = v6;
      v54 = 4;
      v23 = *(_QWORD *)(v22 + 8 * v26);
      v55 = &v35;
      v35 = v23;
      v56 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &byte_14005C3F7, 0, 0, 13, v36);
    }
    if ( (a1[3] & 1) != 0 )
      __int2c();
  }
  v24 = (void (__fastcall *)(__int64 *, __int64))a1[18];
  if ( !v24 )
    goto LABEL_46;
  v25 = v26;
  if ( *((_DWORD *)a1 + 30) == 2 )
  {
    v25 = v26 << 9;
    goto LABEL_44;
  }
  if ( *((_DWORD *)a1 + 30) == 3 )
  {
    v25 = v26 << 18;
LABEL_44:
    v26 = v25;
  }
  v24(a1, v25);
LABEL_46:
  a1[13] = 0;
  return v21;
}

```

## disassembly

```asm
0x1400ec5c4  push    rbp
0x1400ec5c6  push    rbx
0x1400ec5c7  push    rsi
0x1400ec5c8  push    rdi
0x1400ec5c9  push    r12
0x1400ec5cb  push    r13
0x1400ec5cd  push    r14
0x1400ec5cf  push    r15
0x1400ec5d1  lea     rbp, [rsp-58h]
0x1400ec5d6  sub     rsp, 158h
0x1400ec5dd  mov     rax, cs:__security_cookie
0x1400ec5e4  xor     rax, rsp
0x1400ec5e7  mov     [rbp+90h+var_50], rax
0x1400ec5eb  mov     r8, [rcx+68h]
0x1400ec5ef  xor     r12d, r12d
0x1400ec5f2  mov     [rsp+190h+var_160], r12
0x1400ec5f7  mov     rbx, rcx
0x1400ec5fa  test    r8, r8
0x1400ec5fd  jnz     short loc_1400EC606
0x1400ec5ff  xor     eax, eax
0x1400ec601  jmp     loc_1400EC8E0
0x1400ec606  mov     ecx, [rcx+10h]
0x1400ec609  mov     r13d, 4
0x1400ec60f  test    ecx, ecx
0x1400ec611  jz      short loc_1400EC62F
0x1400ec613  sub     ecx, 1
0x1400ec616  jz      short loc_1400EC62A
0x1400ec618  cmp     ecx, 1
0x1400ec61b  jz      short loc_1400EC623
0x1400ec61d  lea     edi, [r13+3]
0x1400ec621  jmp     short loc_1400EC632
0x1400ec623  mov     edi, 5
0x1400ec628  jmp     short loc_1400EC632
0x1400ec62a  mov     edi, r13d
0x1400ec62d  jmp     short loc_1400EC632
0x1400ec62f  mov     edi, r12d
0x1400ec632  mov     rcx, rbx
0x1400ec635  call    VsmmHostAccesspAcqRelBySpa
0x1400ec63a  test    al, al
0x1400ec63c  jz      loc_1400EC71E
0x1400ec642  mov     r9d, [rbx+18h]
0x1400ec646  and     edi, 0FFFFFFFBh
0x1400ec649  and     r9d, 1
0x1400ec64d  jz      short loc_1400EC691
0x1400ec64f  cmp     dword ptr [rbx+8], 1
0x1400ec653  jnz     short loc_1400EC691
0x1400ec655  mov     r9, r8
0x1400ec658  lea     r14, [rbx+14h]
0x1400ec65c  mov     eax, [r14]
0x1400ec65f  lea     rsi, [rbx+60h]
0x1400ec663  mov     r8, [rsi]
0x1400ec666  neg     eax
0x1400ec668  lea     rax, [rsp+190h+var_160]
0x1400ec66d  sbb     ecx, ecx
0x1400ec66f  mov     [rsp+190h+var_170], rax
0x1400ec674  neg     ecx
0x1400ec676  inc     ecx
0x1400ec678  mov     edx, ecx
0x1400ec67a  or      edx, r13d
0x1400ec67d  cmp     dword ptr [rbx+78h], 2
0x1400ec681  cmovnz  edx, ecx
0x1400ec684  mov     rcx, [rbx]
0x1400ec687  call    VsmmSvcpCallModifySpaPageOwnership
0x1400ec68c  jmp     loc_1400EC757
0x1400ec691  mov     edx, [rbx+78h]
0x1400ec694  mov     ecx, r12d
0x1400ec697  sub     edx, 2
0x1400ec69a  jz      short loc_1400EC6A6
0x1400ec69c  cmp     edx, 1
0x1400ec69f  jnz     short loc_1400EC6A9
0x1400ec6a1  lea     ecx, [rdx+7]
0x1400ec6a4  jmp     short loc_1400EC6A9
0x1400ec6a6  mov     ecx, r13d
0x1400ec6a9  lea     r14, [rbx+14h]
0x1400ec6ad  mov     edx, [r14]
0x1400ec6b0  test    edx, edx
0x1400ec6b2  jz      short loc_1400EC6EE
0x1400ec6b4  mov     eax, ecx
0x1400ec6b6  or      eax, 2
0x1400ec6b9  test    r9d, r9d
0x1400ec6bc  cmovz   eax, ecx
0x1400ec6bf  mov     ecx, eax
0x1400ec6c1  mov     r10, r12
0x1400ec6c4  lea     rsi, [rbx+60h]
0x1400ec6c8  test    edx, edx
0x1400ec6ca  mov     rax, [rsi]
0x1400ec6cd  lea     rdx, [rsp+190h+var_160]
0x1400ec6d2  jz      short loc_1400EC6FB
0x1400ec6d4  mov     [rsp+190h+var_170], rdx
0x1400ec6d9  mov     r9, rax
0x1400ec6dc  mov     edx, ecx
0x1400ec6de  mov     ecx, edi
0x1400ec6e0  call    cs:__imp_WinHvAcquireSparseSpaPageHostAccess
0x1400ec6e7  nop     dword ptr [rax+rax+00h]
0x1400ec6ec  jmp     short loc_1400EC757
0x1400ec6ee  test    r9d, r9d
0x1400ec6f1  jz      short loc_1400EC6C1
0x1400ec6f3  mov     r10, [rbx]
0x1400ec6f6  or      ecx, 1
0x1400ec6f9  jmp     short loc_1400EC6C4
0x1400ec6fb  mov     [rsp+190h+var_168], rdx
0x1400ec700  mov     r9, r8
0x1400ec703  mov     r8d, ecx
0x1400ec706  mov     [rsp+190h+var_170], rax
0x1400ec70b  mov     rcx, r10
0x1400ec70e  mov     edx, edi
0x1400ec710  call    cs:__imp_WinHvReleaseSparseSpaPageHostAccess
0x1400ec717  nop     dword ptr [rax+rax+00h]
0x1400ec71c  jmp     short loc_1400EC757
0x1400ec71e  mov     rcx, [rbx]
0x1400ec721  lea     r14, [rbx+14h]
0x1400ec725  lea     rsi, [rbx+60h]
0x1400ec729  mov     edx, edi
0x1400ec72b  lea     rax, [rsp+190h+var_160]
0x1400ec730  mov     r9, [rsi]
0x1400ec733  mov     [rsp+190h+var_170], rax
0x1400ec738  cmp     [r14], r12d
0x1400ec73b  jz      short loc_1400EC74B
0x1400ec73d  call    cs:__imp_WinHvAcquireSparseGpaPageHostAccess
0x1400ec744  nop     dword ptr [rax+rax+00h]
0x1400ec749  jmp     short loc_1400EC757
0x1400ec74b  call    cs:__imp_WinHvReleaseSparseGpaPageHostAccess
0x1400ec752  nop     dword ptr [rax+rax+00h]
0x1400ec757  mov     r15d, eax
0x1400ec75a  test    eax, eax
0x1400ec75c  jns     loc_1400EC8A1
0x1400ec762  mov     eax, cs:dword_140065110
0x1400ec768  cmp     eax, 2
0x1400ec76b  jbe     loc_1400EC898
0x1400ec771  mov     edx, 100h
0x1400ec776  lea     rcx, dword_140065110
0x1400ec77d  call    _tlgKeywordOn
0x1400ec782  test    al, al
0x1400ec784  jz      loc_1400EC898
0x1400ec78a  lea     rdx, aVsmmhostaccess_1; "VsmmHostAccesspAcqRelProcessBatch"
0x1400ec791  lea     rcx, [rbp+90h+var_100]
0x1400ec795  call    _tlgCreate1Sz_char
0x1400ec79a  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400ec7a1  lea     rcx, [rbp+90h+var_F0]
0x1400ec7a5  call    _tlgCreate1Sz_char
0x1400ec7aa  mov     rdx, [rsi]
0x1400ec7ad  lea     rax, [rsp+190h+var_158]
0x1400ec7b2  mov     [rbp+90h+var_E0], rax
0x1400ec7b6  lea     rcx, dword_140065110
0x1400ec7bd  lea     rax, [rsp+190h+var_154]
0x1400ec7c2  mov     [rsp+190h+var_158], 59Fh
0x1400ec7ca  mov     [rbp+90h+var_D0], rax
0x1400ec7ce  xor     r9d, r9d
0x1400ec7d1  mov     rax, [rbx]
0x1400ec7d4  xor     r8d, r8d
0x1400ec7d7  mov     [rsp+190h+var_138], rax
0x1400ec7dc  lea     rax, [rsp+190h+var_138]
0x1400ec7e1  mov     [rbp+90h+var_C0], rax
0x1400ec7e5  mov     eax, [r14]
0x1400ec7e8  mov     [rsp+190h+var_150], eax
0x1400ec7ec  lea     rax, [rsp+190h+var_150]
0x1400ec7f1  mov     [rbp+90h+var_B0], rax
0x1400ec7f5  mov     eax, [rbx+18h]
0x1400ec7f8  mov     [rsp+190h+var_14C], eax
0x1400ec7fc  lea     rax, [rsp+190h+var_14C]
0x1400ec801  mov     [rbp+90h+var_A0], rax
0x1400ec805  mov     eax, [rbx+8]
0x1400ec808  mov     [rsp+190h+var_148], eax
0x1400ec80c  lea     rax, [rsp+190h+var_148]
0x1400ec811  mov     [rbp+90h+var_90], rax
0x1400ec815  mov     eax, [rbx+0Ch]
0x1400ec818  mov     [rsp+190h+var_144], eax
0x1400ec81c  lea     rax, [rsp+190h+var_144]
0x1400ec821  mov     [rbp+90h+var_80], rax
0x1400ec825  lea     rax, [rsp+190h+var_140]
0x1400ec82a  mov     [rbp+90h+var_70], rax
0x1400ec82e  mov     rax, [rsp+190h+var_160]
0x1400ec833  mov     [rbp+90h+var_D8], r13
0x1400ec837  mov     [rsp+190h+var_154], r15d
0x1400ec83c  mov     [rbp+90h+var_C8], r13
0x1400ec840  mov     [rbp+90h+var_B8], 8
0x1400ec848  mov     [rbp+90h+var_A8], r13
0x1400ec84c  mov     [rbp+90h+var_98], r13
0x1400ec850  mov     [rbp+90h+var_88], r13
0x1400ec854  mov     [rbp+90h+var_78], r13
0x1400ec858  mov     [rsp+190h+var_140], edi
0x1400ec85c  mov     [rbp+90h+var_68], r13
0x1400ec860  mov     rdx, [rdx+rax*8]
0x1400ec864  lea     rax, [rsp+190h+var_130]
0x1400ec869  mov     [rbp+90h+var_60], rax
0x1400ec86d  lea     rax, [rsp+190h+var_120]
0x1400ec872  mov     [rsp+190h+var_130], rdx
0x1400ec877  lea     rdx, byte_14005C3F7
0x1400ec87e  mov     [rsp+190h+var_168], rax
0x1400ec883  mov     dword ptr [rsp+190h+var_170], 0Dh
0x1400ec88b  mov     [rbp+90h+var_58], 8
0x1400ec893  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ec898  mov     eax, [rbx+18h]
0x1400ec89b  test    al, 1
0x1400ec89d  jz      short loc_1400EC8A1
0x1400ec89f  int     2Ch; Windows NT - assertion failure
0x1400ec8a1  mov     r8, [rbx+90h]
0x1400ec8a8  test    r8, r8
0x1400ec8ab  jz      short loc_1400EC8D9
0x1400ec8ad  mov     ecx, [rbx+78h]
0x1400ec8b0  mov     rdx, [rsp+190h+var_160]
0x1400ec8b5  sub     ecx, 2
0x1400ec8b8  jz      short loc_1400EC8C5
0x1400ec8ba  cmp     ecx, 1
0x1400ec8bd  jnz     short loc_1400EC8CE
0x1400ec8bf  shl     rdx, 12h
0x1400ec8c3  jmp     short loc_1400EC8C9
0x1400ec8c5  shl     rdx, 9
0x1400ec8c9  mov     [rsp+190h+var_160], rdx
0x1400ec8ce  mov     rcx, rbx
0x1400ec8d1  mov     rax, r8
0x1400ec8d4  call    _guard_dispatch_icall
0x1400ec8d9  mov     [rbx+68h], r12
0x1400ec8dd  mov     eax, r15d
0x1400ec8e0  mov     rcx, [rbp+90h+var_50]
0x1400ec8e4  xor     rcx, rsp; StackCookie
0x1400ec8e7  call    __security_check_cookie
0x1400ec8ec  add     rsp, 158h
0x1400ec8f3  pop     r15
0x1400ec8f5  pop     r14
0x1400ec8f7  pop     r13
0x1400ec8f9  pop     r12
0x1400ec8fb  pop     rdi
0x1400ec8fc  pop     rsi
0x1400ec8fd  pop     rbx
0x1400ec8fe  pop     rbp
0x1400ec8ff  retn
```
