# VsmmHostAccesspAcqRelProcessBatch

- ea: `0x1400e98e4`
- end: `0x1400e9c21`
- name: `VsmmHostAccesspAcqRelProcessBatch`
- size: `829`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140073030`
- `0x1400e98a4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400217a0`
- `0x140028784`
- `0x1400759c4`
- `0x1400e98e4`

## import_xrefs

- `winhvr!WinHvAcquireSparseSpaPageHostAccess` at `0x1400e9a00`
- `winhvr!WinHvAcquireSparseSpaPageHostAccess` at `0x1400e9a00`
- `winhvr!WinHvReleaseSparseSpaPageHostAccess` at `0x1400e9a30`
- `winhvr!WinHvReleaseSparseSpaPageHostAccess` at `0x1400e9a30`
- `winhvr!WinHvAcquireSparseGpaPageHostAccess` at `0x1400e9a5d`
- `winhvr!WinHvAcquireSparseGpaPageHostAccess` at `0x1400e9a5d`
- `winhvr!WinHvReleaseSparseGpaPageHostAccess` at `0x1400e9a6b`
- `winhvr!WinHvReleaseSparseGpaPageHostAccess` at `0x1400e9a6b`

## string_xrefs

- `0x1400e9aba`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400e9aaa`: `VsmmHostAccesspAcqRelProcessBatch`

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
        v6 = 0;
      else
        v6 = 7;
    }
    else
    {
      v6 = 5;
    }
  }
  else
  {
    v6 = 4;
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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmHostAccesspAcqRelProcessBatch");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
      v22 = *v10;
      v39 = &v27;
      v27 = 1502;
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
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14005BE31, 0, 0, 13, v36);
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
0x1400e98e4  push    rbp
0x1400e98e6  push    rbx
0x1400e98e7  push    rsi
0x1400e98e8  push    rdi
0x1400e98e9  push    r12
0x1400e98eb  push    r13
0x1400e98ed  push    r14
0x1400e98ef  push    r15
0x1400e98f1  lea     rbp, [rsp-58h]
0x1400e98f6  sub     rsp, 158h
0x1400e98fd  mov     rax, cs:__security_cookie
0x1400e9904  xor     rax, rsp
0x1400e9907  mov     [rbp+90h+var_50], rax
0x1400e990b  mov     r8, [rcx+68h]
0x1400e990f  xor     r12d, r12d
0x1400e9912  mov     [rsp+190h+var_160], r12
0x1400e9917  mov     rbx, rcx
0x1400e991a  test    r8, r8
0x1400e991d  jnz     short loc_1400E9926
0x1400e991f  xor     eax, eax
0x1400e9921  jmp     loc_1400E9C00
0x1400e9926  mov     ecx, [rcx+10h]
0x1400e9929  mov     r13d, 4
0x1400e992f  test    ecx, ecx
0x1400e9931  jz      short loc_1400E994F
0x1400e9933  sub     ecx, 1
0x1400e9936  jz      short loc_1400E9948
0x1400e9938  cmp     ecx, 1
0x1400e993b  jz      short loc_1400E9943
0x1400e993d  lea     edi, [r13+3]
0x1400e9941  jmp     short loc_1400E9952
0x1400e9943  mov     edi, r12d
0x1400e9946  jmp     short loc_1400E9952
0x1400e9948  mov     edi, 5
0x1400e994d  jmp     short loc_1400E9952
0x1400e994f  mov     edi, r13d
0x1400e9952  mov     rcx, rbx
0x1400e9955  call    VsmmHostAccesspAcqRelBySpa
0x1400e995a  test    al, al
0x1400e995c  jz      loc_1400E9A3E
0x1400e9962  mov     r9d, [rbx+18h]
0x1400e9966  and     edi, 0FFFFFFFBh
0x1400e9969  and     r9d, 1
0x1400e996d  jz      short loc_1400E99B1
0x1400e996f  cmp     dword ptr [rbx+8], 1
0x1400e9973  jnz     short loc_1400E99B1
0x1400e9975  mov     r9, r8
0x1400e9978  lea     r14, [rbx+14h]
0x1400e997c  mov     eax, [r14]
0x1400e997f  lea     rsi, [rbx+60h]
0x1400e9983  mov     r8, [rsi]
0x1400e9986  neg     eax
0x1400e9988  lea     rax, [rsp+190h+var_160]
0x1400e998d  sbb     ecx, ecx
0x1400e998f  mov     [rsp+190h+var_170], rax
0x1400e9994  neg     ecx
0x1400e9996  inc     ecx
0x1400e9998  mov     edx, ecx
0x1400e999a  or      edx, r13d
0x1400e999d  cmp     dword ptr [rbx+78h], 2
0x1400e99a1  cmovnz  edx, ecx
0x1400e99a4  mov     rcx, [rbx]
0x1400e99a7  call    VsmmSvcpCallModifySpaPageOwnership
0x1400e99ac  jmp     loc_1400E9A77
0x1400e99b1  mov     edx, [rbx+78h]
0x1400e99b4  mov     ecx, r12d
0x1400e99b7  sub     edx, 2
0x1400e99ba  jz      short loc_1400E99C6
0x1400e99bc  cmp     edx, 1
0x1400e99bf  jnz     short loc_1400E99C9
0x1400e99c1  lea     ecx, [rdx+7]
0x1400e99c4  jmp     short loc_1400E99C9
0x1400e99c6  mov     ecx, r13d
0x1400e99c9  lea     r14, [rbx+14h]
0x1400e99cd  mov     edx, [r14]
0x1400e99d0  test    edx, edx
0x1400e99d2  jz      short loc_1400E9A0E
0x1400e99d4  mov     eax, ecx
0x1400e99d6  or      eax, 2
0x1400e99d9  test    r9d, r9d
0x1400e99dc  cmovz   eax, ecx
0x1400e99df  mov     ecx, eax
0x1400e99e1  mov     r10, r12
0x1400e99e4  lea     rsi, [rbx+60h]
0x1400e99e8  test    edx, edx
0x1400e99ea  mov     rax, [rsi]
0x1400e99ed  lea     rdx, [rsp+190h+var_160]
0x1400e99f2  jz      short loc_1400E9A1B
0x1400e99f4  mov     [rsp+190h+var_170], rdx
0x1400e99f9  mov     r9, rax
0x1400e99fc  mov     edx, ecx
0x1400e99fe  mov     ecx, edi
0x1400e9a00  call    cs:__imp_WinHvAcquireSparseSpaPageHostAccess
0x1400e9a07  nop     dword ptr [rax+rax+00h]
0x1400e9a0c  jmp     short loc_1400E9A77
0x1400e9a0e  test    r9d, r9d
0x1400e9a11  jz      short loc_1400E99E1
0x1400e9a13  mov     r10, [rbx]
0x1400e9a16  or      ecx, 1
0x1400e9a19  jmp     short loc_1400E99E4
0x1400e9a1b  mov     [rsp+190h+var_168], rdx
0x1400e9a20  mov     r9, r8
0x1400e9a23  mov     r8d, ecx
0x1400e9a26  mov     [rsp+190h+var_170], rax
0x1400e9a2b  mov     rcx, r10
0x1400e9a2e  mov     edx, edi
0x1400e9a30  call    cs:__imp_WinHvReleaseSparseSpaPageHostAccess
0x1400e9a37  nop     dword ptr [rax+rax+00h]
0x1400e9a3c  jmp     short loc_1400E9A77
0x1400e9a3e  mov     rcx, [rbx]
0x1400e9a41  lea     r14, [rbx+14h]
0x1400e9a45  lea     rsi, [rbx+60h]
0x1400e9a49  mov     edx, edi
0x1400e9a4b  lea     rax, [rsp+190h+var_160]
0x1400e9a50  mov     r9, [rsi]
0x1400e9a53  mov     [rsp+190h+var_170], rax
0x1400e9a58  cmp     [r14], r12d
0x1400e9a5b  jz      short loc_1400E9A6B
0x1400e9a5d  call    cs:__imp_WinHvAcquireSparseGpaPageHostAccess
0x1400e9a64  nop     dword ptr [rax+rax+00h]
0x1400e9a69  jmp     short loc_1400E9A77
0x1400e9a6b  call    cs:__imp_WinHvReleaseSparseGpaPageHostAccess
0x1400e9a72  nop     dword ptr [rax+rax+00h]
0x1400e9a77  mov     r15d, eax
0x1400e9a7a  test    eax, eax
0x1400e9a7c  jns     loc_1400E9BC1
0x1400e9a82  mov     eax, cs:dword_140064110
0x1400e9a88  cmp     eax, 2
0x1400e9a8b  jbe     loc_1400E9BB8
0x1400e9a91  mov     edx, 100h
0x1400e9a96  lea     rcx, dword_140064110
0x1400e9a9d  call    _tlgKeywordOn
0x1400e9aa2  test    al, al
0x1400e9aa4  jz      loc_1400E9BB8
0x1400e9aaa  lea     rdx, aVsmmhostaccess_1; "VsmmHostAccesspAcqRelProcessBatch"
0x1400e9ab1  lea     rcx, [rbp+90h+var_100]
0x1400e9ab5  call    _tlgCreate1Sz_char
0x1400e9aba  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400e9ac1  lea     rcx, [rbp+90h+var_F0]
0x1400e9ac5  call    _tlgCreate1Sz_char
0x1400e9aca  mov     rdx, [rsi]
0x1400e9acd  lea     rax, [rsp+190h+var_158]
0x1400e9ad2  mov     [rbp+90h+var_E0], rax
0x1400e9ad6  lea     rcx, dword_140064110
0x1400e9add  lea     rax, [rsp+190h+var_154]
0x1400e9ae2  mov     [rsp+190h+var_158], 5DEh
0x1400e9aea  mov     [rbp+90h+var_D0], rax
0x1400e9aee  xor     r9d, r9d
0x1400e9af1  mov     rax, [rbx]
0x1400e9af4  xor     r8d, r8d
0x1400e9af7  mov     [rsp+190h+var_138], rax
0x1400e9afc  lea     rax, [rsp+190h+var_138]
0x1400e9b01  mov     [rbp+90h+var_C0], rax
0x1400e9b05  mov     eax, [r14]
0x1400e9b08  mov     [rsp+190h+var_150], eax
0x1400e9b0c  lea     rax, [rsp+190h+var_150]
0x1400e9b11  mov     [rbp+90h+var_B0], rax
0x1400e9b15  mov     eax, [rbx+18h]
0x1400e9b18  mov     [rsp+190h+var_14C], eax
0x1400e9b1c  lea     rax, [rsp+190h+var_14C]
0x1400e9b21  mov     [rbp+90h+var_A0], rax
0x1400e9b25  mov     eax, [rbx+8]
0x1400e9b28  mov     [rsp+190h+var_148], eax
0x1400e9b2c  lea     rax, [rsp+190h+var_148]
0x1400e9b31  mov     [rbp+90h+var_90], rax
0x1400e9b35  mov     eax, [rbx+0Ch]
0x1400e9b38  mov     [rsp+190h+var_144], eax
0x1400e9b3c  lea     rax, [rsp+190h+var_144]
0x1400e9b41  mov     [rbp+90h+var_80], rax
0x1400e9b45  lea     rax, [rsp+190h+var_140]
0x1400e9b4a  mov     [rbp+90h+var_70], rax
0x1400e9b4e  mov     rax, [rsp+190h+var_160]
0x1400e9b53  mov     [rbp+90h+var_D8], r13
0x1400e9b57  mov     [rsp+190h+var_154], r15d
0x1400e9b5c  mov     [rbp+90h+var_C8], r13
0x1400e9b60  mov     [rbp+90h+var_B8], 8
0x1400e9b68  mov     [rbp+90h+var_A8], r13
0x1400e9b6c  mov     [rbp+90h+var_98], r13
0x1400e9b70  mov     [rbp+90h+var_88], r13
0x1400e9b74  mov     [rbp+90h+var_78], r13
0x1400e9b78  mov     [rsp+190h+var_140], edi
0x1400e9b7c  mov     [rbp+90h+var_68], r13
0x1400e9b80  mov     rdx, [rdx+rax*8]
0x1400e9b84  lea     rax, [rsp+190h+var_130]
0x1400e9b89  mov     [rbp+90h+var_60], rax
0x1400e9b8d  lea     rax, [rsp+190h+var_120]
0x1400e9b92  mov     [rsp+190h+var_130], rdx
0x1400e9b97  lea     rdx, byte_14005BE31
0x1400e9b9e  mov     [rsp+190h+var_168], rax
0x1400e9ba3  mov     dword ptr [rsp+190h+var_170], 0Dh
0x1400e9bab  mov     [rbp+90h+var_58], 8
0x1400e9bb3  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e9bb8  mov     eax, [rbx+18h]
0x1400e9bbb  test    al, 1
0x1400e9bbd  jz      short loc_1400E9BC1
0x1400e9bbf  int     2Ch; Windows NT - assertion failure
0x1400e9bc1  mov     r8, [rbx+90h]
0x1400e9bc8  test    r8, r8
0x1400e9bcb  jz      short loc_1400E9BF9
0x1400e9bcd  mov     ecx, [rbx+78h]
0x1400e9bd0  mov     rdx, [rsp+190h+var_160]
0x1400e9bd5  sub     ecx, 2
0x1400e9bd8  jz      short loc_1400E9BE5
0x1400e9bda  cmp     ecx, 1
0x1400e9bdd  jnz     short loc_1400E9BEE
0x1400e9bdf  shl     rdx, 12h
0x1400e9be3  jmp     short loc_1400E9BE9
0x1400e9be5  shl     rdx, 9
0x1400e9be9  mov     [rsp+190h+var_160], rdx
0x1400e9bee  mov     rcx, rbx
0x1400e9bf1  mov     rax, r8
0x1400e9bf4  call    _guard_dispatch_icall
0x1400e9bf9  mov     [rbx+68h], r12
0x1400e9bfd  mov     eax, r15d
0x1400e9c00  mov     rcx, [rbp+90h+var_50]
0x1400e9c04  xor     rcx, rsp; StackCookie
0x1400e9c07  call    __security_check_cookie
0x1400e9c0c  add     rsp, 158h
0x1400e9c13  pop     r15
0x1400e9c15  pop     r14
0x1400e9c17  pop     r13
0x1400e9c19  pop     r12
0x1400e9c1b  pop     rdi
0x1400e9c1c  pop     rsi
0x1400e9c1d  pop     rbx
0x1400e9c1e  pop     rbp
0x1400e9c1f  retn
```
