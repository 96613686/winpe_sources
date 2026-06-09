# VsmmPhuStorePartitionDeserialize

- ea: `0x1400b408c`
- end: `0x1400b47f7`
- name: `VsmmPhuStorePartitionDeserialize`
- size: `1899`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x14009fe78`
- `0x1400a1fcc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x140077d64`
- `0x1400b408c`
- `0x1400b7c54`
- `0x1400b7f18`
- `0x1400b81e0`
- `0x1400b8234`
- `0x1400b84d4`
- `0x1400b8848`
- `0x1400b8c94`
- `0x1400b8fc4`
- `0x1400b8ffc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400b45c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400b45c9`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b4528`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b4579`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b4528`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400b4579`

## string_xrefs

- `0x1400b412a`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b4161`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b41a5`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b4204`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b4255`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b42f7`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b43ef`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b4440`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b44eb`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b454a`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b459b`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b45f2`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b46b9`: `VsmmPhuStorePartitionDeserialize`
- `0x1400b4728`: `VsmmPhuStorePartitionDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorePartitionDeserialize(__int64 a1, __int64 a2)
{
  NTSTATUS Structure; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // rsi
  int v7; // eax
  int v8; // r8d
  __int64 *v9; // rdx
  int v10; // r9d
  __int64 v11; // r14
  int v12; // eax
  int v13; // r9d
  __int64 Pool2; // rax
  __int64 v15; // rbx
  _QWORD *v16; // rcx
  __int128 v17; // xmm3
  __int128 v18; // xmm2
  __int128 v19; // xmm1
  __int64 v20; // xmm0_8
  unsigned __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[4]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  int v34[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-50h]
  __int128 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  __int128 SystemInformation; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v39; // [rsp+E8h] [rbp-18h]
  __int128 v40; // [rsp+100h] [rbp+0h] BYREF
  __int128 v41; // [rsp+110h] [rbp+10h]
  __int128 v42; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v43[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]
  int *v46; // [rsp+150h] [rbp+50h]
  __int64 v47; // [rsp+158h] [rbp+58h]
  __int64 *v48; // [rsp+160h] [rbp+60h]
  __int64 v49; // [rsp+168h] [rbp+68h]
  __int64 *v50; // [rsp+170h] [rbp+70h]
  __int64 v51; // [rsp+178h] [rbp+78h]

  v28 = 0;
  v37 = 0;
  v33 = 0;
  LODWORD(v25) = 0;
  *(_OWORD *)v27 = 0;
  v26 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  Structure = VsmmPhuStorepStableBootTimeQuery(&v26);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1965);
LABEL_49:
    LOBYTE(v5) = 1;
    VsmmPhuStorepSerializationBufferTeardown(a1 + 48, v5, &v30);
    return (unsigned int)Structure;
  }
  Structure = VsmmPhuStorepSerializationBufferSetupRestore(a1 + 48, a2, &v30);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1979);
    goto LABEL_49;
  }
  VsmmPhuStorepSerializationContextInitializeFromBuffer(&v30, v27);
  v6 = v28;
  if ( v28 < 0x20 )
  {
    Structure = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      1990);
    goto LABEL_49;
  }
  v7 = VsmmPhuStorepSerializationContextEncodePointer(v27, *(_QWORD *)v27);
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure((int)v27, v7, (int)v34, 56, v34, (__int64)&v25);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2010);
    goto LABEL_49;
  }
  if ( (unsigned int)v25 < 0x20 )
  {
    Structure = -1073739509;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_49;
    tlgCreate1Sz_char(&v42, "VsmmPhuStorePartitionDeserialize");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v25) = 2020;
    v46 = &v24;
    v44 = &v25;
    v48 = &v26;
    v9 = (__int64 *)byte_14004FE95;
    LODWORD(v26) = v10;
    v49 = 4;
    goto LABEL_47;
  }
  v11 = v26;
  if ( (v34[1] & 1) != 0 )
  {
    if ( *((_QWORD *)&v35 + 1) != v26 )
    {
      Structure = -1073741713;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_49;
      tlgCreate1Sz_char(&v42, "VsmmPhuStorePartitionDeserialize");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(v26) = 2039;
      v46 = &v24;
      v44 = &v26;
      v9 = (__int64 *)&unk_14004FEE8;
      v24 = -1073741713;
      v25 = v11;
      v48 = &v25;
      v29 = *((_QWORD *)&v35 + 1);
      v50 = &v29;
      v23 = 8;
      v49 = 8;
      v51 = 8;
      goto LABEL_48;
    }
    VsmmPhuStorepSerializationBufferOverlaySet(v35, *(_QWORD *)&v34[2], &v30);
    VsmmPhuStorepSerializationContextInitializeFromBuffer(&v30, v27);
    v6 = v28;
    v12 = VsmmPhuStorepSerializationContextEncodePointer(v27, *(_QWORD *)v27);
    Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(
                  (int)v27,
                  v12,
                  (int)v34,
                  56,
                  v34,
                  (__int64)&v25);
    if ( Structure < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2067);
      goto LABEL_49;
    }
    if ( (unsigned int)v25 < 0x20 )
    {
      Structure = -1073739509;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_49;
      tlgCreate1Sz_char(&v42, "VsmmPhuStorePartitionDeserialize");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      LODWORD(v26) = 2077;
      v46 = &v24;
      v44 = &v26;
      v48 = &v25;
      v9 = qword_14004FF58;
      LODWORD(v25) = v13;
      v49 = 4;
      goto LABEL_47;
    }
  }
  if ( *(_QWORD *)&v34[2] < (unsigned __int64)(unsigned int)v34[0] || *(_QWORD *)&v34[2] > v28 )
  {
    Structure = -1073739509;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_49;
    tlgCreate1Sz_char(&v42, "VsmmPhuStorePartitionDeserialize");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v26) = 2093;
    v44 = &v26;
    v9 = qword_14004FDE0;
    v29 = *(_QWORD *)&v34[2];
    v48 = &v29;
    v46 = &v24;
    v49 = 8;
LABEL_47:
    v24 = v8;
    v23 = 7;
LABEL_48:
    v45 = 4;
    v47 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v9, 0, 0, v23, &v40);
    goto LABEL_49;
  }
  v28 = *(_QWORD *)&v34[2];
  Structure = VsmmPhuStorepPartitionDeserialize((int)v27, a1);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2111);
    goto LABEL_49;
  }
  if ( *(_QWORD *)(a1 + 1376) <= v6 )
  {
LABEL_38:
    v17 = v30;
    v18 = v31;
    v19 = v32;
    v20 = v33;
    goto LABEL_39;
  }
  LODWORD(v25) = 0;
  SystemInformation = 0;
  v39 = 0;
  Structure = ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2142);
LABEL_42:
    VsmmPhuStorepPartitionDeserializeUndo(a1);
    goto LABEL_49;
  }
  if ( (BYTE8(v39) & 4) != 0 )
  {
    Structure = ZwQuerySystemInformation(SystemInterruptInformation|0x80, &v25, 4u, 0);
    if ( Structure < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePartitionDeserialize",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2155);
      goto LABEL_42;
    }
    if ( (v25 & 1) == 0 )
    {
      Pool2 = ExAllocatePool2(256, *(_QWORD *)(a1 + 1376), 1833788502);
      v15 = Pool2;
      if ( !Pool2 )
      {
        Structure = -1073741670;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorePartitionDeserialize",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          2182);
        goto LABEL_42;
      }
      VsmmPhuStorepSerializationBufferOverlaySet(Pool2, *(_QWORD *)(a1 + 1376), &v30);
      v16 = (_QWORD *)v30;
      *(_DWORD *)(v30 + 4) |= 1u;
      v16[1] = *(_QWORD *)(a1 + 1376);
      v16[2] = v15;
      v16[3] = v11;
      goto LABEL_38;
    }
  }
  v21 = (unsigned __int64)(*(_QWORD *)(a1 + 1376) + 4095LL) >> 12;
  v43[0] = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  Structure = VsmmPhuStorepSerializationBufferSetupNew(a1 + 48, v21, &v40);
  if ( Structure < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorePartitionDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      2215);
    goto LABEL_42;
  }
  VsmmPhuStorepSerializationBufferTeardown(a1 + 48, 0, &v30);
  v17 = v40;
  v18 = v41;
  v19 = v42;
  v20 = v43[0];
LABEL_39:
  *(_QWORD *)(a1 + 16) &= ~1uLL;
  Structure = 0;
  *(_OWORD *)(a1 + 1384) = v17;
  *(_OWORD *)(a1 + 1400) = v18;
  *(_OWORD *)(a1 + 1416) = v19;
  *(_QWORD *)(a1 + 1432) = v20;
  return (unsigned int)Structure;
}

```

## disassembly

```asm
0x1400b408c  mov     [rsp-8+arg_18], rbx
0x1400b4091  push    rbp
0x1400b4092  push    rsi
0x1400b4093  push    rdi
0x1400b4094  push    r12
0x1400b4096  push    r13
0x1400b4098  push    r14
0x1400b409a  push    r15
0x1400b409c  lea     rbp, [rsp-90h]
0x1400b40a4  sub     rsp, 190h
0x1400b40ab  mov     rax, cs:__security_cookie
0x1400b40b2  xor     rax, rsp
0x1400b40b5  mov     [rbp+0C0h+var_40], rax
0x1400b40bc  xorps   xmm0, xmm0
0x1400b40bf  xor     eax, eax
0x1400b40c1  xorps   xmm1, xmm1
0x1400b40c4  mov     [rsp+1C0h+var_168], rax
0x1400b40c9  mov     rdi, rcx
0x1400b40cc  mov     [rbp+0C0h+var_F0], rax
0x1400b40d0  xor     r13d, r13d
0x1400b40d3  mov     [rbp+0C0h+var_128], rax
0x1400b40d7  lea     rcx, [rsp+1C0h+var_180]
0x1400b40dc  mov     dword ptr [rsp+1C0h+var_188], r13d
0x1400b40e1  movups  xmmword ptr [rsp+1C0h+var_178], xmm0
0x1400b40e6  mov     [rsp+1C0h+var_180], r13
0x1400b40eb  mov     r12b, r8b
0x1400b40ee  movups  xmmword ptr [rbp+0C0h+var_120], xmm1
0x1400b40f2  mov     rsi, rdx
0x1400b40f5  movups  [rbp+0C0h+var_110], xmm1
0x1400b40f9  movups  [rbp+0C0h+var_100], xmm1
0x1400b40fd  movups  [rsp+1C0h+var_158], xmm0
0x1400b4102  movups  [rsp+1C0h+var_148], xmm0
0x1400b4107  movups  [rbp+0C0h+var_138], xmm0
0x1400b410b  call    VsmmPhuStorepStableBootTimeQuery
0x1400b4110  lea     r15, [rdi+30h]
0x1400b4114  mov     ebx, eax
0x1400b4116  test    eax, eax
0x1400b4118  jns     short loc_1400B413B
0x1400b411a  mov     r9d, eax
0x1400b411d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4124  mov     r8d, 7ADh
0x1400b412a  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b4131  call    VidTraceErrorStatusInternal0
0x1400b4136  jmp     loc_1400B47BB
0x1400b413b  lea     r8, [rsp+1C0h+var_158]
0x1400b4140  mov     rdx, rsi
0x1400b4143  mov     rcx, r15
0x1400b4146  call    VsmmPhuStorepSerializationBufferSetupRestore
0x1400b414b  mov     ebx, eax
0x1400b414d  test    eax, eax
0x1400b414f  jns     short loc_1400B4172
0x1400b4151  mov     r9d, eax
0x1400b4154  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b415b  mov     r8d, 7BBh
0x1400b4161  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b4168  call    VidTraceErrorStatusInternal0
0x1400b416d  jmp     loc_1400B47BB
0x1400b4172  lea     rdx, [rsp+1C0h+var_178]
0x1400b4177  lea     rcx, [rsp+1C0h+var_158]
0x1400b417c  call    VsmmPhuStorepSerializationContextInitializeFromBuffer
0x1400b4181  mov     rsi, [rsp+1C0h+var_168]
0x1400b4186  cmp     rsi, 20h ; ' '
0x1400b418a  jnb     short loc_1400B41B6
0x1400b418c  mov     r8d, 0C000090Bh
0x1400b4192  mov     ebx, r8d
0x1400b4195  mov     r9d, r8d
0x1400b4198  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b419f  mov     r8d, 7C6h
0x1400b41a5  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b41ac  call    VidTraceErrorStatusInternal0
0x1400b41b1  jmp     loc_1400B47BB
0x1400b41b6  mov     rdx, qword ptr [rsp+1C0h+var_178]
0x1400b41bb  lea     rcx, [rsp+1C0h+var_178]
0x1400b41c0  call    VsmmPhuStorepSerializationContextEncodePointer
0x1400b41c5  mov     edx, eax; int
0x1400b41c7  lea     r8, [rbp+0C0h+var_120]; int
0x1400b41cb  lea     rax, [rsp+1C0h+var_188]
0x1400b41d0  mov     r9d, 38h ; '8'; int
0x1400b41d6  mov     [rsp+1C0h+var_198], rax; __int64
0x1400b41db  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b41e0  lea     rax, [rbp+0C0h+var_120]
0x1400b41e4  mov     [rsp+1C0h+var_1A0], rax; void *
0x1400b41e9  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b41ee  mov     ebx, eax
0x1400b41f0  test    eax, eax
0x1400b41f2  jns     short loc_1400B4215
0x1400b41f4  mov     r9d, eax
0x1400b41f7  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b41fe  mov     r8d, 7DAh
0x1400b4204  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b420b  call    VidTraceErrorStatusInternal0
0x1400b4210  jmp     loc_1400B47BB
0x1400b4215  mov     r9d, dword ptr [rsp+1C0h+var_188]
0x1400b421a  cmp     r9d, 20h ; ' '
0x1400b421e  jnb     loc_1400B42B1
0x1400b4224  mov     eax, cs:dword_140064110
0x1400b422a  mov     r8d, 0C000090Bh
0x1400b4230  mov     ebx, r8d
0x1400b4233  cmp     eax, 2
0x1400b4236  jbe     loc_1400B47BB
0x1400b423c  mov     edx, 100h
0x1400b4241  lea     rcx, dword_140064110
0x1400b4248  call    _tlgKeywordOn
0x1400b424d  test    al, al
0x1400b424f  jz      loc_1400B47BB
0x1400b4255  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b425c  lea     rcx, [rbp+0C0h+var_A0]
0x1400b4260  call    _tlgCreate1Sz_char
0x1400b4265  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b426c  lea     rcx, [rbp+0C0h+var_90]
0x1400b4270  call    _tlgCreate1Sz_char
0x1400b4275  lea     rcx, [rsp+1C0h+var_190]
0x1400b427a  mov     dword ptr [rsp+1C0h+var_188], 7E4h
0x1400b4282  mov     [rbp+0C0h+var_70], rcx
0x1400b4286  lea     rax, [rsp+1C0h+var_188]
0x1400b428b  lea     rcx, [rsp+1C0h+var_180]
0x1400b4290  mov     [rbp+0C0h+var_80], rax
0x1400b4294  mov     [rbp+0C0h+var_60], rcx
0x1400b4298  lea     rdx, byte_14004FE95
0x1400b429f  mov     dword ptr [rsp+1C0h+var_180], r9d
0x1400b42a4  mov     [rbp+0C0h+var_58], 4
0x1400b42ac  jmp     loc_1400B4783
0x1400b42b1  test    byte ptr [rbp+0C0h+var_120+4], 1
0x1400b42b5  mov     r14, [rsp+1C0h+var_180]
0x1400b42ba  jz      loc_1400B449C
0x1400b42c0  cmp     qword ptr [rbp+0C0h+var_110+8], r14
0x1400b42c4  jz      loc_1400B437B
0x1400b42ca  mov     eax, cs:dword_140064110
0x1400b42d0  mov     ebx, 0C000006Fh
0x1400b42d5  cmp     eax, 2
0x1400b42d8  jbe     loc_1400B47BB
0x1400b42de  mov     edx, 100h
0x1400b42e3  lea     rcx, dword_140064110
0x1400b42ea  call    _tlgKeywordOn
0x1400b42ef  test    al, al
0x1400b42f1  jz      loc_1400B47BB
0x1400b42f7  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b42fe  lea     rcx, [rbp+0C0h+var_A0]
0x1400b4302  call    _tlgCreate1Sz_char
0x1400b4307  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b430e  lea     rcx, [rbp+0C0h+var_90]
0x1400b4312  call    _tlgCreate1Sz_char
0x1400b4317  lea     rcx, [rsp+1C0h+var_190]
0x1400b431c  mov     dword ptr [rsp+1C0h+var_180], 7F7h
0x1400b4324  lea     rax, [rsp+1C0h+var_180]
0x1400b4329  mov     [rbp+0C0h+var_70], rcx
0x1400b432d  mov     [rbp+0C0h+var_80], rax
0x1400b4331  lea     rdx, unk_14004FEE8
0x1400b4338  mov     ecx, 8
0x1400b433d  mov     [rsp+1C0h+var_190], ebx
0x1400b4341  lea     rax, [rsp+1C0h+var_188]
0x1400b4346  mov     [rsp+1C0h+var_188], r14
0x1400b434b  mov     [rbp+0C0h+var_60], rax
0x1400b434f  mov     rax, qword ptr [rbp+0C0h+var_110+8]
0x1400b4353  mov     [rsp+1C0h+var_160], rax
0x1400b4358  lea     rax, [rsp+1C0h+var_160]
0x1400b435d  mov     [rbp+0C0h+var_50], rax
0x1400b4361  lea     rax, [rbp+0C0h+var_C0]
0x1400b4365  mov     [rsp+1C0h+var_198], rax
0x1400b436a  mov     dword ptr [rsp+1C0h+var_1A0], ecx
0x1400b436e  mov     [rbp+0C0h+var_58], rcx
0x1400b4372  mov     [rbp+0C0h+var_48], rcx
0x1400b4376  jmp     loc_1400B4799
0x1400b437b  mov     rdx, qword ptr [rbp+0C0h+var_120+8]
0x1400b437f  lea     r8, [rsp+1C0h+var_158]
0x1400b4384  mov     rcx, qword ptr [rbp+0C0h+var_110]
0x1400b4388  call    VsmmPhuStorepSerializationBufferOverlaySet
0x1400b438d  lea     rdx, [rsp+1C0h+var_178]
0x1400b4392  lea     rcx, [rsp+1C0h+var_158]
0x1400b4397  call    VsmmPhuStorepSerializationContextInitializeFromBuffer
0x1400b439c  mov     rdx, qword ptr [rsp+1C0h+var_178]
0x1400b43a1  lea     rcx, [rsp+1C0h+var_178]
0x1400b43a6  mov     rsi, [rsp+1C0h+var_168]
0x1400b43ab  call    VsmmPhuStorepSerializationContextEncodePointer
0x1400b43b0  mov     edx, eax; int
0x1400b43b2  lea     r8, [rbp+0C0h+var_120]; int
0x1400b43b6  lea     rax, [rsp+1C0h+var_188]
0x1400b43bb  mov     r9d, 38h ; '8'; int
0x1400b43c1  mov     [rsp+1C0h+var_198], rax; __int64
0x1400b43c6  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b43cb  lea     rax, [rbp+0C0h+var_120]
0x1400b43cf  mov     [rsp+1C0h+var_1A0], rax; void *
0x1400b43d4  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b43d9  mov     ebx, eax
0x1400b43db  test    eax, eax
0x1400b43dd  jns     short loc_1400B4400
0x1400b43df  mov     r9d, eax
0x1400b43e2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b43e9  mov     r8d, 813h
0x1400b43ef  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b43f6  call    VidTraceErrorStatusInternal0
0x1400b43fb  jmp     loc_1400B47BB
0x1400b4400  mov     r9d, dword ptr [rsp+1C0h+var_188]
0x1400b4405  cmp     r9d, 20h ; ' '
0x1400b4409  jnb     loc_1400B449C
0x1400b440f  mov     eax, cs:dword_140064110
0x1400b4415  mov     r8d, 0C000090Bh
0x1400b441b  mov     ebx, r8d
0x1400b441e  cmp     eax, 2
0x1400b4421  jbe     loc_1400B47BB
0x1400b4427  mov     edx, 100h
0x1400b442c  lea     rcx, dword_140064110
0x1400b4433  call    _tlgKeywordOn
0x1400b4438  test    al, al
0x1400b443a  jz      loc_1400B47BB
0x1400b4440  lea     rdx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b4447  lea     rcx, [rbp+0C0h+var_A0]
0x1400b444b  call    _tlgCreate1Sz_char
0x1400b4450  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4457  lea     rcx, [rbp+0C0h+var_90]
0x1400b445b  call    _tlgCreate1Sz_char
0x1400b4460  lea     rcx, [rsp+1C0h+var_190]
0x1400b4465  mov     dword ptr [rsp+1C0h+var_180], 81Dh
0x1400b446d  mov     [rbp+0C0h+var_70], rcx
0x1400b4471  lea     rax, [rsp+1C0h+var_180]
0x1400b4476  lea     rcx, [rsp+1C0h+var_188]
0x1400b447b  mov     [rbp+0C0h+var_80], rax
0x1400b447f  mov     [rbp+0C0h+var_60], rcx
0x1400b4483  lea     rdx, qword_14004FF58
0x1400b448a  mov     dword ptr [rsp+1C0h+var_188], r9d
0x1400b448f  mov     [rbp+0C0h+var_58], 4
0x1400b4497  jmp     loc_1400B4783
0x1400b449c  mov     eax, [rbp+0C0h+var_120]
0x1400b449f  mov     rcx, qword ptr [rbp+0C0h+var_120+8]
0x1400b44a3  cmp     rcx, rax
0x1400b44a6  jb      loc_1400B46F7
0x1400b44ac  cmp     rcx, [rsp+1C0h+var_168]
0x1400b44b1  ja      loc_1400B46F7
0x1400b44b7  mov     [rsp+1C0h+var_168], rcx
0x1400b44bc  lea     rdx, [rbp+0C0h+var_120]
0x1400b44c0  lea     rcx, [rsp+1C0h+var_178]; int
0x1400b44c5  mov     [rsp+1C0h+var_1A0], rdi; __int64
0x1400b44ca  mov     r9b, r12b
0x1400b44cd  mov     r8, r14
0x1400b44d0  call    VsmmPhuStorepPartitionDeserialize
0x1400b44d5  mov     ebx, eax
0x1400b44d7  test    eax, eax
0x1400b44d9  jns     short loc_1400B44FC
0x1400b44db  mov     r9d, eax
0x1400b44de  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b44e5  mov     r8d, 83Fh
0x1400b44eb  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b44f2  call    VidTraceErrorStatusInternal0
0x1400b44f7  jmp     loc_1400B47BB
0x1400b44fc  cmp     [rdi+560h], rsi
0x1400b4503  jbe     loc_1400B4633
0x1400b4509  xor     r9d, r9d; ReturnLength
0x1400b450c  mov     dword ptr [rsp+1C0h+var_188], r13d
0x1400b4511  xorps   xmm0, xmm0
0x1400b4514  lea     rdx, [rbp+0C0h+SystemInformation]; SystemInformation
0x1400b4518  movups  [rbp+0C0h+SystemInformation], xmm0
0x1400b451c  lea     r8d, [r9+20h]; SystemInformationLength
0x1400b4520  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1400b4524  movups  [rbp+0C0h+var_D8], xmm0
0x1400b4528  call    cs:__imp_ZwQuerySystemInformation
0x1400b452f  nop     dword ptr [rax+rax+00h]
0x1400b4534  mov     ebx, eax
0x1400b4536  test    eax, eax
0x1400b4538  jns     short loc_1400B455B
0x1400b453a  mov     r9d, eax
0x1400b453d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4544  mov     r8d, 85Eh
0x1400b454a  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b4551  call    VidTraceErrorStatusInternal0
0x1400b4556  jmp     loc_1400B46C5
0x1400b455b  mov     eax, 4
0x1400b4560  test    byte ptr [rbp+0C0h+var_D8+8], al
0x1400b4563  jz      loc_1400B4670
0x1400b4569  xor     r9d, r9d; ReturnLength
0x1400b456c  lea     rdx, [rsp+1C0h+var_188]; SystemInformation
0x1400b4571  mov     r8d, eax; SystemInformationLength
0x1400b4574  mov     ecx, 97h; SystemInformationClass
0x1400b4579  call    cs:__imp_ZwQuerySystemInformation
0x1400b4580  nop     dword ptr [rax+rax+00h]
0x1400b4585  mov     ebx, eax
0x1400b4587  test    eax, eax
0x1400b4589  jns     short loc_1400B45AC
0x1400b458b  mov     r9d, eax
0x1400b458e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4595  mov     r8d, 86Bh
0x1400b459b  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b45a2  call    VidTraceErrorStatusInternal0
0x1400b45a7  jmp     loc_1400B46C5
0x1400b45ac  test    byte ptr [rsp+1C0h+var_188], 1
0x1400b45b1  jnz     loc_1400B4670
0x1400b45b7  mov     rdx, [rdi+560h]
0x1400b45be  mov     ecx, 100h
0x1400b45c3  mov     r8d, 6D4D6456h
0x1400b45c9  call    cs:__imp_ExAllocatePool2
0x1400b45d0  nop     dword ptr [rax+rax+00h]
0x1400b45d5  mov     rbx, rax
0x1400b45d8  test    rax, rax
0x1400b45db  jnz     short loc_1400B4603
0x1400b45dd  mov     ebx, 0C000009Ah
0x1400b45e2  mov     r9d, ebx
0x1400b45e5  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b45ec  mov     r8d, 886h
0x1400b45f2  lea     rcx, aVsmmphustorepa; "VsmmPhuStorePartitionDeserialize"
0x1400b45f9  call    VidTraceErrorStatusInternal0
0x1400b45fe  jmp     loc_1400B46C5
  ... truncated ...
```
