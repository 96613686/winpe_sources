# VsmmPhuStorePartitionDeserialize

- ea: `0x1400b5f8c`
- end: `0x1400b66f7`
- name: `VsmmPhuStorePartitionDeserialize`
- size: `1899`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x1400a18c0`
- `0x1400a3a1c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x140078c40`
- `0x1400b5f8c`
- `0x1400b9ae8`
- `0x1400b9dac`
- `0x1400ba070`
- `0x1400ba0c4`
- `0x1400ba364`
- `0x1400ba6d8`
- `0x1400bab24`
- `0x1400bae54`
- `0x1400bae8c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b64c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400b64c9`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b6428`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b6479`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b6428`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b6479`

## string_xrefs

- `0x1400b602a`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b6061`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b60a5`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b6104`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b6155`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b61f7`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b62ef`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b6340`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b63eb`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b644a`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b649b`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b64f2`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b65b9`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b6628`: `VsmmPhuStorePartitionDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorePartitionDeserialize(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  unsigned __int64 v8; // rsi
  int v9; // eax
  int Structure; // eax
  int v11; // r8d
  char *v12; // rdx
  int v13; // r9d
  __int64 v14; // r14
  int v15; // eax
  int v16; // eax
  int v17; // r9d
  int v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  __int64 Pool2; // rax
  __int64 v22; // rbx
  _QWORD *v23; // rcx
  __int128 v24; // xmm3
  __int128 v25; // xmm2
  __int128 v26; // xmm1
  __int64 v27; // xmm0_8
  unsigned __int64 v28; // rdx
  int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v38; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+78h] [rbp-88h]
  __int128 v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  int v42[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-50h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int128 SystemInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v47; // [rsp+E8h] [rbp-18h]
  __int128 v48; // [rsp+100h] [rbp+0h] BYREF
  __int128 v49; // [rsp+110h] [rbp+10h]
  __int128 v50; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v51[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v52; // [rsp+140h] [rbp+40h]
  __int64 v53; // [rsp+148h] [rbp+48h]
  int *v54; // [rsp+150h] [rbp+50h]
  __int64 v55; // [rsp+158h] [rbp+58h]
  __int64 *v56; // [rsp+160h] [rbp+60h]
  __int64 v57; // [rsp+168h] [rbp+68h]
  __int64 *v58; // [rsp+170h] [rbp+70h]
  __int64 v59; // [rsp+178h] [rbp+78h]

  v36 = 0;
  v45 = 0;
  v41 = 0;
  LODWORD(v33) = 0;
  *(_OWORD *)v35 = 0;
  v34 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v4 = VsmmPhuStorepStableBootTimeQuery(&v34);
  v5 = v4;
  if ( v4 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1958,
      (unsigned int)v4);
LABEL_49:
    LOBYTE(v6) = 1;
    VsmmPhuStorepSerializationBufferTeardown(a1 + 48, v6, &v38);
    return v5;
  }
  v7 = VsmmPhuStorepSerializationBufferSetupRestore(a1 + 48, a2, &v38);
  v5 = v7;
  if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1972,
      (unsigned int)v7);
    goto LABEL_49;
  }
  VsmmPhuStorepSerializationContextInitializeFromBuffer(&v38, v35);
  v8 = v36;
  if ( v36 < 0x20 )
  {
    v5 = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1983,
      3221227787LL);
    goto LABEL_49;
  }
  v9 = VsmmPhuStorepSerializationContextEncodePointer(v35, *(_QWORD *)v35);
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure((int)v35, v9, (int)v42, 56, v42, (__int64)&v33);
  v5 = Structure;
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2003,
      (unsigned int)Structure);
    goto LABEL_49;
  }
  if ( (unsigned int)v33 < 0x20 )
  {
    v5 = -1073739509;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_49;
    tlgCreate1Sz_char(&v50, "VsmmPhuStorePartitionDeserialize");
    tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v33) = 2013;
    v54 = &v32;
    v52 = &v33;
    v56 = &v34;
    v12 = (char *)qword_1400503D0;
    LODWORD(v34) = v13;
    v57 = 4;
    goto LABEL_47;
  }
  v14 = v34;
  if ( (v42[1] & 1) != 0 )
  {
    if ( *((_QWORD *)&v43 + 1) != v34 )
    {
      v5 = -1073741713;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_49;
      tlgCreate1Sz_char(&v50, "VsmmPhuStorePartitionDeserialize");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(v34) = 2032;
      v54 = &v32;
      v52 = &v34;
      v12 = byte_140050423;
      v32 = -1073741713;
      v33 = v14;
      v56 = &v33;
      v37 = *((_QWORD *)&v43 + 1);
      v58 = &v37;
      v31 = 8;
      v57 = 8;
      v59 = 8;
      goto LABEL_48;
    }
    VsmmPhuStorepSerializationBufferOverlaySet(v43, *(_QWORD *)&v42[2], &v38);
    VsmmPhuStorepSerializationContextInitializeFromBuffer(&v38, v35);
    v8 = v36;
    v15 = VsmmPhuStorepSerializationContextEncodePointer(v35, *(_QWORD *)v35);
    v16 = VsmmPhuStorepSerializationContextConsumeAndReadStructure((int)v35, v15, (int)v42, 56, v42, (__int64)&v33);
    v5 = v16;
    if ( v16 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2060,
        (unsigned int)v16);
      goto LABEL_49;
    }
    if ( (unsigned int)v33 < 0x20 )
    {
      v5 = -1073739509;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_49;
      tlgCreate1Sz_char(&v50, "VsmmPhuStorePartitionDeserialize");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(v34) = 2070;
      v54 = &v32;
      v52 = &v34;
      v56 = &v33;
      v12 = (char *)word_140050322;
      LODWORD(v33) = v17;
      v57 = 4;
      goto LABEL_47;
    }
  }
  if ( *(_QWORD *)&v42[2] < (unsigned __int64)(unsigned int)v42[0] || *(_QWORD *)&v42[2] > v36 )
  {
    v5 = -1073739509;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_49;
    tlgCreate1Sz_char(&v50, "VsmmPhuStorePartitionDeserialize");
    tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v34) = 2086;
    v52 = &v34;
    v12 = byte_140050375;
    v37 = *(_QWORD *)&v42[2];
    v56 = &v37;
    v54 = &v32;
    v57 = 8;
LABEL_47:
    v32 = v11;
    v31 = 7;
LABEL_48:
    v53 = 4;
    v55 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v12, 0, 0, v31, &v48);
    goto LABEL_49;
  }
  v36 = *(_QWORD *)&v42[2];
  v18 = VsmmPhuStorepPartitionDeserialize((int)v35, a1);
  v5 = v18;
  if ( v18 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2104,
      (unsigned int)v18);
    goto LABEL_49;
  }
  if ( *(_QWORD *)(a1 + 1376) <= v8 )
  {
LABEL_38:
    v24 = v38;
    v25 = v39;
    v26 = v40;
    v27 = v41;
    goto LABEL_39;
  }
  LODWORD(v33) = 0;
  SystemInformation = 0;
  v47 = 0;
  v19 = ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  v5 = v19;
  if ( v19 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2135,
      (unsigned int)v19);
LABEL_42:
    VsmmPhuStorepPartitionDeserializeUndo(a1);
    goto LABEL_49;
  }
  if ( (BYTE8(v47) & 4) != 0 )
  {
    v20 = ZwQuerySystemInformation(SystemInterruptInformation|0x80, &v33, 4u, 0);
    v5 = v20;
    if ( v20 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2148,
        (unsigned int)v20);
      goto LABEL_42;
    }
    if ( (v33 & 1) == 0 )
    {
      Pool2 = ExAllocatePool2(256, *(_QWORD *)(a1 + 1376), 1833788502);
      v22 = Pool2;
      if ( !Pool2 )
      {
        v5 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorePartitionDeserialize",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          2175,
          3221225626LL);
        goto LABEL_42;
      }
      VsmmPhuStorepSerializationBufferOverlaySet(Pool2, *(_QWORD *)(a1 + 1376), &v38);
      v23 = (_QWORD *)v38;
      *(_DWORD *)(v38 + 4) |= 1u;
      v23[1] = *(_QWORD *)(a1 + 1376);
      v23[2] = v22;
      v23[3] = v14;
      goto LABEL_38;
    }
  }
  v28 = (unsigned __int64)(*(_QWORD *)(a1 + 1376) + 4095LL) >> 12;
  v51[0] = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v29 = VsmmPhuStorepSerializationBufferSetupNew(a1 + 48, v28, &v48);
  v5 = v29;
  if ( v29 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2208,
      (unsigned int)v29);
    goto LABEL_42;
  }
  VsmmPhuStorepSerializationBufferTeardown(a1 + 48, 0, &v38);
  v24 = v48;
  v25 = v49;
  v26 = v50;
  v27 = v51[0];
LABEL_39:
  *(_QWORD *)(a1 + 16) &= ~1uLL;
  v5 = 0;
  *(_OWORD *)(a1 + 1384) = v24;
  *(_OWORD *)(a1 + 1400) = v25;
  *(_OWORD *)(a1 + 1416) = v26;
  *(_QWORD *)(a1 + 1432) = v27;
  return v5;
}

```

## disassembly

```asm
0x1400b5f8c  mov     [rsp-8+arg_18], rbx
0x1400b5f91  push    rbp
0x1400b5f92  push    rsi
0x1400b5f93  push    rdi
0x1400b5f94  push    r12
0x1400b5f96  push    r13
0x1400b5f98  push    r14
0x1400b5f9a  push    r15
0x1400b5f9c  lea     rbp, [rsp-90h]
0x1400b5fa4  sub     rsp, 190h
0x1400b5fab  mov     rax, cs:__security_cookie
0x1400b5fb2  xor     rax, rsp
0x1400b5fb5  mov     [rbp+0C0h+var_40], rax
0x1400b5fbc  xorps   xmm0, xmm0
0x1400b5fbf  xor     eax, eax
0x1400b5fc1  xorps   xmm1, xmm1
0x1400b5fc4  mov     [rsp+1C0h+var_168], rax
0x1400b5fc9  mov     rdi, rcx
0x1400b5fcc  mov     [rbp+0C0h+var_F0], rax
0x1400b5fd0  xor     r13d, r13d
0x1400b5fd3  mov     [rbp+0C0h+var_128], rax
0x1400b5fd7  lea     rcx, [rsp+1C0h+var_180]
0x1400b5fdc  mov     dword ptr [rsp+1C0h+var_188], r13d
0x1400b5fe1  movups  xmmword ptr [rsp+1C0h+var_178], xmm0
0x1400b5fe6  mov     [rsp+1C0h+var_180], r13
0x1400b5feb  mov     r12b, r8b
0x1400b5fee  movups  xmmword ptr [rbp+0C0h+var_120], xmm1
0x1400b5ff2  mov     rsi, rdx
0x1400b5ff5  movups  [rbp+0C0h+var_110], xmm1
0x1400b5ff9  movups  [rbp+0C0h+var_100], xmm1
0x1400b5ffd  movups  [rsp+1C0h+var_158], xmm0
0x1400b6002  movups  [rsp+1C0h+var_148], xmm0
0x1400b6007  movups  [rbp+0C0h+var_138], xmm0
0x1400b600b  call    VsmmPhuStorepStableBootTimeQuery
0x1400b6010  lea     r15, [rdi+30h]
0x1400b6014  mov     ebx, eax
0x1400b6016  test    eax, eax
0x1400b6018  jns     short loc_1400B603B
0x1400b601a  mov     r9d, eax
0x1400b601d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6024  mov     r8d, 7A6h
0x1400b602a  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b6031  call    VidTraceErrorStatusInternal0
0x1400b6036  jmp     loc_1400B66BB
0x1400b603b  lea     r8, [rsp+1C0h+var_158]
0x1400b6040  mov     rdx, rsi
0x1400b6043  mov     rcx, r15
0x1400b6046  call    VsmmPhuStorepSerializationBufferSetupRestore
0x1400b604b  mov     ebx, eax
0x1400b604d  test    eax, eax
0x1400b604f  jns     short loc_1400B6072
0x1400b6051  mov     r9d, eax
0x1400b6054  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b605b  mov     r8d, 7B4h
0x1400b6061  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b6068  call    VidTraceErrorStatusInternal0
0x1400b606d  jmp     loc_1400B66BB
0x1400b6072  lea     rdx, [rsp+1C0h+var_178]
0x1400b6077  lea     rcx, [rsp+1C0h+var_158]
0x1400b607c  call    VsmmPhuStorepSerializationContextInitializeFromBuffer
0x1400b6081  mov     rsi, [rsp+1C0h+var_168]
0x1400b6086  cmp     rsi, 20h ; ' '
0x1400b608a  jnb     short loc_1400B60B6
0x1400b608c  mov     r8d, 0C000090Bh
0x1400b6092  mov     ebx, r8d
0x1400b6095  mov     r9d, r8d
0x1400b6098  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b609f  mov     r8d, 7BFh
0x1400b60a5  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b60ac  call    VidTraceErrorStatusInternal0
0x1400b60b1  jmp     loc_1400B66BB
0x1400b60b6  mov     rdx, qword ptr [rsp+1C0h+var_178]
0x1400b60bb  lea     rcx, [rsp+1C0h+var_178]
0x1400b60c0  call    VsmmPhuStorepSerializationContextEncodePointer
0x1400b60c5  mov     edx, eax; int
0x1400b60c7  lea     r8, [rbp+0C0h+var_120]; int
0x1400b60cb  lea     rax, [rsp+1C0h+var_188]
0x1400b60d0  mov     r9d, 38h ; '8'; int
0x1400b60d6  mov     [rsp+1C0h+var_198], rax; __int64
0x1400b60db  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b60e0  lea     rax, [rbp+0C0h+var_120]
0x1400b60e4  mov     [rsp+1C0h+var_1A0], rax; void *
0x1400b60e9  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b60ee  mov     ebx, eax
0x1400b60f0  test    eax, eax
0x1400b60f2  jns     short loc_1400B6115
0x1400b60f4  mov     r9d, eax
0x1400b60f7  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b60fe  mov     r8d, 7D3h
0x1400b6104  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b610b  call    VidTraceErrorStatusInternal0
0x1400b6110  jmp     loc_1400B66BB
0x1400b6115  mov     r9d, dword ptr [rsp+1C0h+var_188]
0x1400b611a  cmp     r9d, 20h ; ' '
0x1400b611e  jnb     loc_1400B61B1
0x1400b6124  mov     eax, cs:dword_140065110
0x1400b612a  mov     r8d, 0C000090Bh
0x1400b6130  mov     ebx, r8d
0x1400b6133  cmp     eax, 2
0x1400b6136  jbe     loc_1400B66BB
0x1400b613c  mov     edx, 100h
0x1400b6141  lea     rcx, dword_140065110
0x1400b6148  call    _tlgKeywordOn
0x1400b614d  test    al, al
0x1400b614f  jz      loc_1400B66BB
0x1400b6155  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b615c  lea     rcx, [rbp+0C0h+var_A0]
0x1400b6160  call    _tlgCreate1Sz_char
0x1400b6165  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b616c  lea     rcx, [rbp+0C0h+var_90]
0x1400b6170  call    _tlgCreate1Sz_char
0x1400b6175  lea     rcx, [rsp+1C0h+var_190]
0x1400b617a  mov     dword ptr [rsp+1C0h+var_188], 7DDh
0x1400b6182  mov     [rbp+0C0h+var_70], rcx
0x1400b6186  lea     rax, [rsp+1C0h+var_188]
0x1400b618b  lea     rcx, [rsp+1C0h+var_180]
0x1400b6190  mov     [rbp+0C0h+var_80], rax
0x1400b6194  mov     [rbp+0C0h+var_60], rcx
0x1400b6198  lea     rdx, qword_1400503D0
0x1400b619f  mov     dword ptr [rsp+1C0h+var_180], r9d
0x1400b61a4  mov     [rbp+0C0h+var_58], 4
0x1400b61ac  jmp     loc_1400B6683
0x1400b61b1  test    byte ptr [rbp+0C0h+var_120+4], 1
0x1400b61b5  mov     r14, [rsp+1C0h+var_180]
0x1400b61ba  jz      loc_1400B639C
0x1400b61c0  cmp     qword ptr [rbp+0C0h+var_110+8], r14
0x1400b61c4  jz      loc_1400B627B
0x1400b61ca  mov     eax, cs:dword_140065110
0x1400b61d0  mov     ebx, 0C000006Fh
0x1400b61d5  cmp     eax, 2
0x1400b61d8  jbe     loc_1400B66BB
0x1400b61de  mov     edx, 100h
0x1400b61e3  lea     rcx, dword_140065110
0x1400b61ea  call    _tlgKeywordOn
0x1400b61ef  test    al, al
0x1400b61f1  jz      loc_1400B66BB
0x1400b61f7  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b61fe  lea     rcx, [rbp+0C0h+var_A0]
0x1400b6202  call    _tlgCreate1Sz_char
0x1400b6207  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b620e  lea     rcx, [rbp+0C0h+var_90]
0x1400b6212  call    _tlgCreate1Sz_char
0x1400b6217  lea     rcx, [rsp+1C0h+var_190]
0x1400b621c  mov     dword ptr [rsp+1C0h+var_180], 7F0h
0x1400b6224  lea     rax, [rsp+1C0h+var_180]
0x1400b6229  mov     [rbp+0C0h+var_70], rcx
0x1400b622d  mov     [rbp+0C0h+var_80], rax
0x1400b6231  lea     rdx, byte_140050423
0x1400b6238  mov     ecx, 8
0x1400b623d  mov     [rsp+1C0h+var_190], ebx
0x1400b6241  lea     rax, [rsp+1C0h+var_188]
0x1400b6246  mov     [rsp+1C0h+var_188], r14
0x1400b624b  mov     [rbp+0C0h+var_60], rax
0x1400b624f  mov     rax, qword ptr [rbp+0C0h+var_110+8]
0x1400b6253  mov     [rsp+1C0h+var_160], rax
0x1400b6258  lea     rax, [rsp+1C0h+var_160]
0x1400b625d  mov     [rbp+0C0h+var_50], rax
0x1400b6261  lea     rax, [rbp+0C0h+var_C0]
0x1400b6265  mov     [rsp+1C0h+var_198], rax
0x1400b626a  mov     dword ptr [rsp+1C0h+var_1A0], ecx
0x1400b626e  mov     [rbp+0C0h+var_58], rcx
0x1400b6272  mov     [rbp+0C0h+var_48], rcx
0x1400b6276  jmp     loc_1400B6699
0x1400b627b  mov     rdx, qword ptr [rbp+0C0h+var_120+8]
0x1400b627f  lea     r8, [rsp+1C0h+var_158]
0x1400b6284  mov     rcx, qword ptr [rbp+0C0h+var_110]
0x1400b6288  call    VsmmPhuStorepSerializationBufferOverlaySet
0x1400b628d  lea     rdx, [rsp+1C0h+var_178]
0x1400b6292  lea     rcx, [rsp+1C0h+var_158]
0x1400b6297  call    VsmmPhuStorepSerializationContextInitializeFromBuffer
0x1400b629c  mov     rdx, qword ptr [rsp+1C0h+var_178]
0x1400b62a1  lea     rcx, [rsp+1C0h+var_178]
0x1400b62a6  mov     rsi, [rsp+1C0h+var_168]
0x1400b62ab  call    VsmmPhuStorepSerializationContextEncodePointer
0x1400b62b0  mov     edx, eax; int
0x1400b62b2  lea     r8, [rbp+0C0h+var_120]; int
0x1400b62b6  lea     rax, [rsp+1C0h+var_188]
0x1400b62bb  mov     r9d, 38h ; '8'; int
0x1400b62c1  mov     [rsp+1C0h+var_198], rax; __int64
0x1400b62c6  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b62cb  lea     rax, [rbp+0C0h+var_120]
0x1400b62cf  mov     [rsp+1C0h+var_1A0], rax; void *
0x1400b62d4  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b62d9  mov     ebx, eax
0x1400b62db  test    eax, eax
0x1400b62dd  jns     short loc_1400B6300
0x1400b62df  mov     r9d, eax
0x1400b62e2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b62e9  mov     r8d, 80Ch
0x1400b62ef  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b62f6  call    VidTraceErrorStatusInternal0
0x1400b62fb  jmp     loc_1400B66BB
0x1400b6300  mov     r9d, dword ptr [rsp+1C0h+var_188]
0x1400b6305  cmp     r9d, 20h ; ' '
0x1400b6309  jnb     loc_1400B639C
0x1400b630f  mov     eax, cs:dword_140065110
0x1400b6315  mov     r8d, 0C000090Bh
0x1400b631b  mov     ebx, r8d
0x1400b631e  cmp     eax, 2
0x1400b6321  jbe     loc_1400B66BB
0x1400b6327  mov     edx, 100h
0x1400b632c  lea     rcx, dword_140065110
0x1400b6333  call    _tlgKeywordOn
0x1400b6338  test    al, al
0x1400b633a  jz      loc_1400B66BB
0x1400b6340  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b6347  lea     rcx, [rbp+0C0h+var_A0]
0x1400b634b  call    _tlgCreate1Sz_char
0x1400b6350  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6357  lea     rcx, [rbp+0C0h+var_90]
0x1400b635b  call    _tlgCreate1Sz_char
0x1400b6360  lea     rcx, [rsp+1C0h+var_190]
0x1400b6365  mov     dword ptr [rsp+1C0h+var_180], 816h
0x1400b636d  mov     [rbp+0C0h+var_70], rcx
0x1400b6371  lea     rax, [rsp+1C0h+var_180]
0x1400b6376  lea     rcx, [rsp+1C0h+var_188]
0x1400b637b  mov     [rbp+0C0h+var_80], rax
0x1400b637f  mov     [rbp+0C0h+var_60], rcx
0x1400b6383  lea     rdx, word_140050322
0x1400b638a  mov     dword ptr [rsp+1C0h+var_188], r9d
0x1400b638f  mov     [rbp+0C0h+var_58], 4
0x1400b6397  jmp     loc_1400B6683
0x1400b639c  mov     eax, [rbp+0C0h+var_120]
0x1400b639f  mov     rcx, qword ptr [rbp+0C0h+var_120+8]
0x1400b63a3  cmp     rcx, rax
0x1400b63a6  jb      loc_1400B65F7
0x1400b63ac  cmp     rcx, [rsp+1C0h+var_168]
0x1400b63b1  ja      loc_1400B65F7
0x1400b63b7  mov     [rsp+1C0h+var_168], rcx
0x1400b63bc  lea     rdx, [rbp+0C0h+var_120]
0x1400b63c0  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b63c5  mov     [rsp+1C0h+var_1A0], rdi; __int64
0x1400b63ca  mov     r9b, r12b
0x1400b63cd  mov     r8, r14
0x1400b63d0  call    VsmmPhuStorepPartitionDeserialize
0x1400b63d5  mov     ebx, eax
0x1400b63d7  test    eax, eax
0x1400b63d9  jns     short loc_1400B63FC
0x1400b63db  mov     r9d, eax
0x1400b63de  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b63e5  mov     r8d, 838h
0x1400b63eb  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b63f2  call    VidTraceErrorStatusInternal0
0x1400b63f7  jmp     loc_1400B66BB
0x1400b63fc  cmp     [rdi+560h], rsi
0x1400b6403  jbe     loc_1400B6533
0x1400b6409  xor     r9d, r9d; ReturnLength
0x1400b640c  mov     dword ptr [rsp+1C0h+var_188], r13d
0x1400b6411  xorps   xmm0, xmm0
0x1400b6414  lea     rdx, [rbp+0C0h+SystemInformation]; SystemInformation
0x1400b6418  movups  [rbp+0C0h+SystemInformation], xmm0
0x1400b641c  lea     r8d, [r9+20h]; SystemInformationLength
0x1400b6420  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1400b6424  movups  [rbp+0C0h+var_D8], xmm0
0x1400b6428  call    cs:__imp_ZwQuerySystemInformation
0x1400b642f  nop     dword ptr [rax+rax+00h]
0x1400b6434  mov     ebx, eax
0x1400b6436  test    eax, eax
0x1400b6438  jns     short loc_1400B645B
0x1400b643a  mov     r9d, eax
0x1400b643d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6444  mov     r8d, 857h
0x1400b644a  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b6451  call    VidTraceErrorStatusInternal0
0x1400b6456  jmp     loc_1400B65C5
0x1400b645b  mov     eax, 4
0x1400b6460  test    byte ptr [rbp+0C0h+var_D8+8], al
0x1400b6463  jz      loc_1400B6570
0x1400b6469  xor     r9d, r9d; ReturnLength
0x1400b646c  lea     rdx, [rsp+1C0h+var_188]; SystemInformation
0x1400b6471  mov     r8d, eax; SystemInformationLength
0x1400b6474  mov     ecx, 97h; SystemInformationClass
0x1400b6479  call    cs:__imp_ZwQuerySystemInformation
0x1400b6480  nop     dword ptr [rax+rax+00h]
0x1400b6485  mov     ebx, eax
0x1400b6487  test    eax, eax
0x1400b6489  jns     short loc_1400B64AC
0x1400b648b  mov     r9d, eax
0x1400b648e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6495  mov     r8d, 864h
0x1400b649b  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b64a2  call    VidTraceErrorStatusInternal0
0x1400b64a7  jmp     loc_1400B65C5
0x1400b64ac  test    byte ptr [rsp+1C0h+var_188], 1
0x1400b64b1  jnz     loc_1400B6570
0x1400b64b7  mov     rdx, [rdi+560h]
0x1400b64be  mov     ecx, 100h
0x1400b64c3  mov     r8d, 6D4D6456h
0x1400b64c9  call    cs:__imp_ExAllocatePool2
0x1400b64d0  nop     dword ptr [rax+rax+00h]
0x1400b64d5  mov     rbx, rax
0x1400b64d8  test    rax, rax
0x1400b64db  jnz     short loc_1400B6503
0x1400b64dd  mov     ebx, 0C000009Ah
0x1400b64e2  mov     r9d, ebx
0x1400b64e5  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b64ec  mov     r8d, 87Fh
0x1400b64f2  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b64f9  call    VidTraceErrorStatusInternal0
0x1400b64fe  jmp     loc_1400B65C5
  ... truncated ...
```
