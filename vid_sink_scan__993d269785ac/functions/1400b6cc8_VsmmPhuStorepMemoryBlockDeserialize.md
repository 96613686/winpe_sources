# VsmmPhuStorepMemoryBlockDeserialize

- ea: `0x1400b6cc8`
- end: `0x1400b73bf`
- name: `VsmmPhuStorepMemoryBlockDeserialize`
- size: `1783`
- prototype: `__int64 __fastcall(int, __int64 *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400b77dc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x14002f524`
- `0x1400b6cc8`
- `0x1400b73c8`
- `0x1400b7450`
- `0x1400b8c94`
- `0x1400e6334`
- `0x1400f2d14`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b729e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b729e`

## string_xrefs

- `0x1400b6d74`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b6dbe`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b6e08`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b6e3b`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b6eb1`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b6fd5`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b70fe`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b71be`: `VsmmPhuStorepMemoryBlockDeserialize`
- `0x1400b72f4`: `VsmmPhuStorepMemoryBlockDeserialize`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepMemoryBlockDeserialize(int a1, __int64 *a2, int a3, __int64 a4, __int64 a5)
{
  unsigned int Structure; // ebx
  __int16 v9; // r12d^2
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // r9d
  __int64 v13; // r11
  char v14; // r15
  char v15; // r13
  char v16; // bl
  __int128 v17; // xmm3
  __int128 v18; // xmm2
  __int128 v19; // xmm6
  __int64 v20; // r8
  __int64 v21; // r9
  __int128 v22; // xmm4
  __int128 v23; // xmm5
  __int64 v24; // rax
  __int64 *v25; // rdx
  int v26; // r8d
  int v27; // r8d
  int v28; // r9d
  __int128 v29; // xmm1
  __int64 v30; // r14
  __int64 v31; // rbx
  int v33; // [rsp+38h] [rbp-D0h] BYREF
  int v34; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v35; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v38[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+98h] [rbp-70h]
  __int128 v40; // [rsp+A8h] [rbp-60h]
  _OWORD v41[6]; // [rsp+B8h] [rbp-50h] BYREF
  int v42[4]; // [rsp+118h] [rbp+10h] BYREF
  int v43; // [rsp+128h] [rbp+20h] BYREF
  __int128 v44; // [rsp+130h] [rbp+28h] BYREF
  __int128 v45; // [rsp+140h] [rbp+38h]
  _BYTE v46[32]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v47[16]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v48[16]; // [rsp+188h] [rbp+80h] BYREF
  int *v49; // [rsp+198h] [rbp+90h]
  __int64 v50; // [rsp+1A0h] [rbp+98h]
  int *v51; // [rsp+1A8h] [rbp+A0h]
  __int64 v52; // [rsp+1B0h] [rbp+A8h]
  __int64 *v53; // [rsp+1B8h] [rbp+B0h]
  __int64 v54; // [rsp+1C0h] [rbp+B8h]
  __int64 *v55; // [rsp+1C8h] [rbp+C0h]
  __int64 v56; // [rsp+1D0h] [rbp+C8h]
  int *v57; // [rsp+1D8h] [rbp+D0h]
  __int64 v58; // [rsp+1E0h] [rbp+D8h]

  v35 = a4;
  v43 = 0;
  *(_OWORD *)v42 = 0;
  v44 = 0;
  v45 = 0;
  memset(v41, 0, sizeof(v41));
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, a3, (int)v42, 20, v42, 0);
  if ( (Structure & 0x80000000) != 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7933);
    return Structure;
  }
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v42[1], (int)&v42[2], 32, &v44, 0);
  if ( (Structure & 0x80000000) != 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7946);
    return Structure;
  }
  Structure = VsmmPhuStorepSerializationContextConsumeAndReadStructure(a1, v42[3], (int)&v43, 96, v41, 0);
  if ( (Structure & 0x80000000) != 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7964);
    return Structure;
  }
  v9 = WORD1(v41[0]);
  if ( !LOBYTE(v41[0]) )
  {
    Structure = -1073739509;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepMemoryBlockDeserialize",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      7971);
    return Structure;
  }
  v10 = *a2;
  v11 = *a2 & 1;
  if ( v11 && ((BYTE8(v45) & 1) == 0 && !*((_QWORD *)&v41[2] + 1) || (BYTE1(v41[0]) & 1) == 0) )
  {
    Structure = -1073741713;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v47, "VsmmPhuStorepMemoryBlockDeserialize");
      tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v34 = 8006;
      v49 = &v34;
      v50 = 4;
      v51 = (int *)&v35;
      LODWORD(v35) = v12;
      v36 = v13 & *((_QWORD *)&v45 + 1);
      v53 = &v36;
      v37 = *((_QWORD *)&v41[2] + 1);
      v55 = &v37;
      v52 = 4;
      LOBYTE(v33) = v13 & BYTE1(v41[0]);
      v57 = &v33;
      v54 = 8;
      v56 = 8;
      v58 = v13;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004F0A5, 0, 0, 9, v46);
    }
    return Structure;
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( ((*((_QWORD *)&v45 + 1) >> 4) & 1LL) != 0 || (BYTE1(v41[0]) & 2) == 0 )
  {
    if ( (v10 & 4) == 0 )
    {
      if ( !v11 )
        goto LABEL_31;
      if ( (v10 & 2) == 0 )
      {
        Structure = -1073741713;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorepMemoryBlockDeserialize",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          8063);
        return Structure;
      }
    }
    if ( (BYTE1(v41[0]) & 2) == 0 )
    {
      if ( v11 )
      {
        *((_QWORD *)&v41[1] + 1) = 0;
        *(_QWORD *)&v41[2] = 0;
      }
      else if ( *((_QWORD *)&v41[1] + 1) )
      {
        v14 = 1;
      }
    }
    v16 = v11;
    if ( ((*((_QWORD *)&v45 + 1) >> 4) & 1LL) != 0 )
    {
      if ( (BYTE1(v41[0]) & 1) != 0 )
        v16 = 1;
      else
        v15 = 1;
    }
  }
LABEL_31:
  if ( DWORD1(v41[0]) != 1 )
  {
    Structure = -1073741735;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      return Structure;
    tlgCreate1Sz_char(v47, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v35) = 8081;
    v49 = (int *)&v35;
    v25 = qword_14004F118;
    v34 = -1073741735;
    v51 = &v34;
    v33 = DWORD1(v41[0]);
    goto LABEL_67;
  }
  v17 = v41[3];
  v18 = v41[5];
  v19 = v41[2];
  v38[0] = v41[0];
  v38[3] = v41[3];
  v39 = v41[4];
  v40 = v41[5];
  v21 = (unsigned int)VsmmPhuStorepMemoryBlockDeterminePageOwnership(v35, *((_QWORD *)&v45 + 1));
  if ( !v9 )
  {
    *((_QWORD *)&v38[3] + 1) = *(_QWORD *)&v41[3];
    v17 = v38[3];
    *((_QWORD *)&v39 + 1) = *((_QWORD *)&v41[3] + 1);
    *(_QWORD *)&v39 = 0;
    v22 = v39;
    *(_QWORD *)&v40 = *(_QWORD *)&v41[4];
    goto LABEL_39;
  }
  if ( v9 == 1 )
  {
LABEL_39:
    v24 = 0;
    goto LABEL_40;
  }
  if ( v9 != 2 )
  {
    if ( v9 != 3 )
      goto LABEL_49;
    goto LABEL_43;
  }
  v24 = *((_QWORD *)&v40 + 1);
LABEL_40:
  if ( v24 )
    v24 = -1;
  *((_QWORD *)&v40 + 1) = v24;
  v18 = v40;
LABEL_43:
  if ( (BYTE1(v38[0]) & 4) != 0 )
  {
    Structure = -1073739509;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      return Structure;
    tlgCreate1Sz_char(v47, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v35) = 8181;
    v49 = (int *)&v35;
    v25 = (__int64 *)&byte_14004EFFF;
    v34 = v26;
    v51 = &v34;
    LOWORD(v33) = WORD1(v38[0]);
    v54 = 2;
LABEL_68:
    v53 = (__int64 *)&v33;
    v50 = 4;
    v52 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v25, 0, 0, 7, v46);
    return Structure;
  }
  if ( (_DWORD)v21 == 1 )
    BYTE1(v38[0]) |= 4u;
LABEL_49:
  WORD1(v38[0]) = 4;
  if ( (BYTE1(v38[0]) & 4) != 0 && (_DWORD)v21 != 1 )
  {
    Structure = -1073739509;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      return Structure;
    tlgCreate1Sz_char(v47, "VsmmPhuStorepMemoryBlockDeserialize");
    tlgCreate1Sz_char(v48, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    LODWORD(v35) = 8220;
    v49 = (int *)&v35;
    v25 = (__int64 *)&dword_14004F054;
    v34 = v27;
    v51 = &v34;
    v33 = v28;
LABEL_67:
    v54 = 4;
    goto LABEL_68;
  }
  v29 = v45;
  *(_OWORD *)a5 = v44;
  *(_OWORD *)(a5 + 32) = v38[0];
  *(_OWORD *)(a5 + 48) = v23;
  *(_OWORD *)(a5 + 64) = v19;
  *(_OWORD *)(a5 + 80) = v17;
  *(_OWORD *)(a5 + 96) = v22;
  *(_OWORD *)(a5 + 112) = v18;
  *(_OWORD *)(a5 + 16) = v29;
  if ( v16 )
    *(_QWORD *)(a5 + 112) = 0;
  if ( v14 )
  {
    v30 = *(_QWORD *)(a5 + 64);
    v31 = *(_QWORD *)(a5 + 56);
    if ( v30 )
    {
      memset(v38, 0, sizeof(v38));
      VsmmPhysicalBufferAssign(0, 2, v31, v30, v38);
      VsmmPhysicalBufferTeardown(v38);
      *(_QWORD *)(a5 + 64) = 0;
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(a5 + 56), 0x6D4D6456u);
    }
    *(_QWORD *)(a5 + 56) = 0;
  }
  if ( v15 )
    VsmmPhuStorepMemoryBlockFree(v35, a5, v20, v21);
  return 0;
}

```

## disassembly

```asm
0x1400b6cc8  mov     rax, rsp
0x1400b6ccb  mov     [rax+10h], rbx
0x1400b6ccf  push    rbp
0x1400b6cd0  push    rsi
0x1400b6cd1  push    rdi
0x1400b6cd2  push    r12
0x1400b6cd4  push    r13
0x1400b6cd6  push    r14
0x1400b6cd8  push    r15
0x1400b6cda  lea     rbp, [rax-138h]
0x1400b6ce1  sub     rsp, 200h
0x1400b6ce8  movaps  xmmword ptr [rax-48h], xmm6
0x1400b6cec  mov     rax, cs:__security_cookie
0x1400b6cf3  xor     rax, rsp
0x1400b6cf6  mov     [rbp+130h+var_50], rax
0x1400b6cfd  mov     rsi, [rbp+130h+arg_20]
0x1400b6d04  xor     eax, eax
0x1400b6d06  xorps   xmm1, xmm1
0x1400b6d09  mov     [rsp+230h+var_1F8], r9
0x1400b6d0e  mov     ebx, r8d
0x1400b6d11  mov     [rbp+130h+var_110], eax
0x1400b6d14  mov     r14, rdx
0x1400b6d17  mov     rdi, rcx
0x1400b6d1a  lea     r15d, [rax+60h]
0x1400b6d1e  xorps   xmm0, xmm0
0x1400b6d21  mov     r8d, r15d; Size
0x1400b6d24  lea     rcx, [rbp+130h+var_180]; void *
0x1400b6d28  xor     edx, edx; Val
0x1400b6d2a  movups  xmmword ptr [rbp+130h+var_120], xmm0
0x1400b6d2e  movups  [rbp+130h+var_108], xmm1
0x1400b6d32  movups  [rbp+130h+var_F8], xmm1
0x1400b6d36  call    memset
0x1400b6d3b  lea     rax, [rbp+130h+var_120]
0x1400b6d3f  xor     r12d, r12d
0x1400b6d42  mov     [rsp+230h+var_208], r12; __int64
0x1400b6d47  lea     r9d, [r15-4Ch]; int
0x1400b6d4b  lea     r8, [rbp+130h+var_120]; int
0x1400b6d4f  mov     [rsp+230h+var_210], rax; void *
0x1400b6d54  mov     edx, ebx; int
0x1400b6d56  mov     rcx, rdi; int
0x1400b6d59  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b6d5e  mov     ebx, eax
0x1400b6d60  test    eax, eax
0x1400b6d62  jns     short loc_1400B6D85
0x1400b6d64  mov     r9d, eax
0x1400b6d67  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6d6e  mov     r8d, 1EFDh
0x1400b6d74  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6d7b  call    VidTraceErrorStatusInternal0
0x1400b6d80  jmp     loc_1400B738D
0x1400b6d85  mov     edx, [rbp+130h+var_120+4]; int
0x1400b6d88  lea     rax, [rbp+130h+var_108]
0x1400b6d8c  mov     [rsp+230h+var_208], r12; __int64
0x1400b6d91  lea     r8, [rbp+130h+var_120+8]; int
0x1400b6d95  mov     r9d, 20h ; ' '; int
0x1400b6d9b  mov     [rsp+230h+var_210], rax; void *
0x1400b6da0  mov     rcx, rdi; int
0x1400b6da3  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b6da8  mov     ebx, eax
0x1400b6daa  test    eax, eax
0x1400b6dac  jns     short loc_1400B6DCF
0x1400b6dae  mov     r9d, eax
0x1400b6db1  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6db8  mov     r8d, 1F0Ah
0x1400b6dbe  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6dc5  call    VidTraceErrorStatusInternal0
0x1400b6dca  jmp     loc_1400B738D
0x1400b6dcf  mov     edx, [rbp+130h+var_120+0Ch]; int
0x1400b6dd2  lea     rax, [rbp+130h+var_180]
0x1400b6dd6  mov     [rsp+230h+var_208], r12; __int64
0x1400b6ddb  lea     r8, [rbp+130h+var_110]; int
0x1400b6ddf  mov     r9d, r15d; int
0x1400b6de2  mov     [rsp+230h+var_210], rax; void *
0x1400b6de7  mov     rcx, rdi; int
0x1400b6dea  call    VsmmPhuStorepSerializationContextConsumeAndReadStructure
0x1400b6def  xor     r10d, r10d
0x1400b6df2  mov     ebx, eax
0x1400b6df4  test    eax, eax
0x1400b6df6  jns     short loc_1400B6E19
0x1400b6df8  mov     r9d, eax
0x1400b6dfb  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6e02  mov     r8d, 1F1Ch
0x1400b6e08  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6e0f  call    VidTraceErrorStatusInternal0
0x1400b6e14  jmp     loc_1400B738D
0x1400b6e19  mov     r12, qword ptr [rbp+130h+var_180]
0x1400b6e1d  test    r12b, r12b
0x1400b6e20  jnz     short loc_1400B6E4C
0x1400b6e22  mov     r8d, 0C000090Bh
0x1400b6e28  mov     ebx, r8d
0x1400b6e2b  mov     r9d, r8d
0x1400b6e2e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6e35  mov     r8d, 1F23h
0x1400b6e3b  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6e42  call    VidTraceErrorStatusInternal0
0x1400b6e47  jmp     loc_1400B738D
0x1400b6e4c  mov     r8, [r14]
0x1400b6e4f  mov     r11d, 1
0x1400b6e55  mov     r9, qword ptr [rbp+130h+var_F8+8]
0x1400b6e59  mov     rax, r8
0x1400b6e5c  mov     dl, byte ptr [rbp+130h+var_180+1]
0x1400b6e5f  and     rax, r11
0x1400b6e62  jz      loc_1400B6F8C
0x1400b6e68  test    r11b, r9b
0x1400b6e6b  jnz     short loc_1400B6E73
0x1400b6e6d  cmp     qword ptr [rbp+130h+var_160+8], r10
0x1400b6e71  jz      short loc_1400B6E7C
0x1400b6e73  test    r11b, dl
0x1400b6e76  jnz     loc_1400B6F8C
0x1400b6e7c  mov     eax, cs:dword_140064110
0x1400b6e82  mov     edi, 2
0x1400b6e87  mov     r9d, 0C000006Fh
0x1400b6e8d  mov     ebx, r9d
0x1400b6e90  cmp     eax, edi
0x1400b6e92  jbe     loc_1400B738D
0x1400b6e98  mov     edx, 100h
0x1400b6e9d  lea     rcx, dword_140064110
0x1400b6ea4  call    _tlgKeywordOn
0x1400b6ea9  test    al, al
0x1400b6eab  jz      loc_1400B738D
0x1400b6eb1  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6eb8  lea     rcx, [rbp+130h+var_C0]
0x1400b6ebc  call    _tlgCreate1Sz_char
0x1400b6ec1  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6ec8  lea     rcx, [rbp+130h+var_B0]
0x1400b6ecf  call    _tlgCreate1Sz_char
0x1400b6ed4  lea     rax, [rsp+230h+var_200+4]
0x1400b6ed9  mov     dword ptr [rsp+230h+var_200+4], 1F46h
0x1400b6ee1  mov     [rbp+130h+var_A0], rax
0x1400b6ee8  lea     rdx, byte_14004F0A5
0x1400b6eef  lea     rax, [rsp+230h+var_1F8]
0x1400b6ef4  mov     [rbp+130h+var_98], 4
0x1400b6eff  mov     [rbp+130h+var_90], rax
0x1400b6f06  mov     rax, qword ptr [rbp+130h+var_F8+8]
0x1400b6f0a  and     rax, r11
0x1400b6f0d  mov     dword ptr [rsp+230h+var_1F8], r9d
0x1400b6f12  mov     [rsp+230h+var_1F0], rax
0x1400b6f17  lea     rax, [rsp+230h+var_1F0]
0x1400b6f1c  mov     [rbp+130h+var_80], rax
0x1400b6f23  mov     rax, qword ptr [rbp+130h+var_160+8]
0x1400b6f27  mov     qword ptr [rsp+230h+var_1E8], rax
0x1400b6f2c  lea     rax, [rsp+230h+var_1E8]
0x1400b6f31  mov     [rbp+130h+var_70], rax
0x1400b6f38  mov     al, byte ptr [rbp+130h+var_180+1]
0x1400b6f3b  and     al, r11b
0x1400b6f3e  mov     [rbp+130h+var_88], 4
0x1400b6f49  mov     byte ptr [rsp+230h+var_200], al
0x1400b6f4d  lea     rax, [rsp+230h+var_200]
0x1400b6f52  mov     [rbp+130h+var_60], rax
0x1400b6f59  lea     rax, [rbp+130h+var_E0]
0x1400b6f5d  mov     [rsp+230h+var_208], rax
0x1400b6f62  mov     dword ptr [rsp+230h+var_210], 9
0x1400b6f6a  mov     [rbp+130h+var_78], 8
0x1400b6f75  mov     [rbp+130h+var_68], 8
0x1400b6f80  mov     [rbp+130h+var_58], r11
0x1400b6f87  jmp     loc_1400B737B
0x1400b6f8c  mov     rcx, r9
0x1400b6f8f  movzx   r15d, r10b
0x1400b6f93  mov     edi, 2
0x1400b6f98  shr     rcx, 4
0x1400b6f9c  mov     r13b, r10b
0x1400b6f9f  mov     bl, r10b
0x1400b6fa2  lea     r14d, [rdi+2]
0x1400b6fa6  and     rcx, r11
0x1400b6fa9  jnz     short loc_1400B6FB0
0x1400b6fab  test    dil, dl
0x1400b6fae  jnz     short loc_1400B7016
0x1400b6fb0  test    r14b, r8b
0x1400b6fb3  jnz     short loc_1400B6FE6
0x1400b6fb5  test    rax, rax
0x1400b6fb8  jz      short loc_1400B7016
0x1400b6fba  test    dil, r8b
0x1400b6fbd  jnz     short loc_1400B6FE6
0x1400b6fbf  mov     r9d, 0C000006Fh
0x1400b6fc5  mov     ebx, r9d
0x1400b6fc8  mov     r8d, 1F7Fh
0x1400b6fce  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6fd5  lea     rcx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b6fdc  call    VidTraceErrorStatusInternal0
0x1400b6fe1  jmp     loc_1400B738D
0x1400b6fe6  test    dil, dl
0x1400b6fe9  jnz     short loc_1400B7002
0x1400b6feb  test    rax, rax
0x1400b6fee  jz      short loc_1400B6FFA
0x1400b6ff0  mov     [rbp+130h+var_168], r10
0x1400b6ff4  mov     qword ptr [rbp+130h+var_160], r10
0x1400b6ff8  jmp     short loc_1400B7002
0x1400b6ffa  cmp     [rbp+130h+var_168], r10
0x1400b6ffe  cmovnz  r15d, r11d
0x1400b7002  mov     bl, al
0x1400b7004  test    rcx, rcx
0x1400b7007  jz      short loc_1400B7016
0x1400b7009  test    r11b, dl
0x1400b700c  jz      short loc_1400B7013
0x1400b700e  mov     bl, r11b
0x1400b7011  jmp     short loc_1400B7016
0x1400b7013  mov     r13b, r11b
0x1400b7016  cmp     dword ptr [rbp+130h+var_180+4], r11d
0x1400b701a  jnz     loc_1400B72C8
0x1400b7020  movaps  xmm0, [rbp+130h+var_180]
0x1400b7024  mov     rdx, r9
0x1400b7027  movaps  xmm3, [rbp+130h+var_150]
0x1400b702b  movaps  xmm4, [rbp+130h+var_140]
0x1400b702f  movaps  xmm2, [rbp+130h+var_130]
0x1400b7033  mov     rcx, [rsp+230h+var_1F8]
0x1400b7038  movaps  xmm5, xmmword ptr [rbp-40h]
0x1400b703c  movaps  xmm6, [rbp+130h+var_160]
0x1400b7040  movaps  [rsp+230h+var_1E8+8], xmm0
0x1400b7045  movaps  [rbp+130h+var_1B0], xmm3
0x1400b7049  movaps  [rbp+130h+var_1A0], xmm4
0x1400b704d  movaps  [rbp+130h+var_190], xmm2
0x1400b7051  call    VsmmPhuStorepMemoryBlockDeterminePageOwnership
0x1400b7056  shr     r12, 10h
0x1400b705a  mov     r9d, eax
0x1400b705d  movzx   edx, r12w
0x1400b7061  xor     r12d, r12d
0x1400b7064  test    edx, edx
0x1400b7066  jz      short loc_1400B7082
0x1400b7068  sub     edx, 1
0x1400b706b  jz      short loc_1400B70A6
0x1400b706d  sub     edx, 1
0x1400b7070  jz      short loc_1400B707C
0x1400b7072  cmp     edx, 1
0x1400b7075  jz      short loc_1400B70BC
0x1400b7077  jmp     loc_1400B7173
0x1400b707c  mov     rax, qword ptr [rbp+130h+var_190+8]
0x1400b7080  jmp     short loc_1400B70A9
0x1400b7082  mov     rax, qword ptr [rbp+130h+var_150]
0x1400b7086  mov     qword ptr [rbp+130h+var_1B0+8], rax
0x1400b708a  mov     rax, qword ptr [rbp+130h+var_150+8]
0x1400b708e  movaps  xmm3, [rbp+130h+var_1B0]
0x1400b7092  mov     qword ptr [rbp+130h+var_1A0+8], rax
0x1400b7096  mov     rax, qword ptr [rbp+130h+var_140]
0x1400b709a  mov     qword ptr [rbp+130h+var_1A0], r12
0x1400b709e  movaps  xmm4, [rbp+130h+var_1A0]
0x1400b70a2  mov     qword ptr [rbp+130h+var_190], rax
0x1400b70a6  mov     rax, r12
0x1400b70a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b70ad  test    rax, rax
0x1400b70b0  cmovnz  rax, rcx
0x1400b70b4  mov     qword ptr [rbp+130h+var_190+8], rax
0x1400b70b8  movaps  xmm2, [rbp+130h+var_190]
0x1400b70bc  mov     rax, qword ptr [rsp+230h+var_1E8+8]
0x1400b70c1  shr     rax, 8
0x1400b70c5  test    r14b, al
0x1400b70c8  jz      loc_1400B7168
0x1400b70ce  mov     eax, cs:dword_140064110
0x1400b70d4  mov     r8d, 0C000090Bh
0x1400b70da  mov     ebx, r8d
0x1400b70dd  cmp     eax, edi
0x1400b70df  jbe     loc_1400B738D
0x1400b70e5  mov     edx, 100h
0x1400b70ea  lea     rcx, dword_140064110
0x1400b70f1  call    _tlgKeywordOn
0x1400b70f6  test    al, al
0x1400b70f8  jz      loc_1400B738D
0x1400b70fe  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b7105  lea     rcx, [rbp+130h+var_C0]
0x1400b7109  call    _tlgCreate1Sz_char
0x1400b710e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b7115  lea     rcx, [rbp+130h+var_B0]
0x1400b711c  call    _tlgCreate1Sz_char
0x1400b7121  lea     rax, [rsp+230h+var_1F8]
0x1400b7126  mov     dword ptr [rsp+230h+var_1F8], 1FF5h
0x1400b712e  mov     [rbp+130h+var_A0], rax
0x1400b7135  lea     rdx, byte_14004EFFF
0x1400b713c  lea     rax, [rsp+230h+var_200+4]
0x1400b7141  mov     dword ptr [rsp+230h+var_200+4], r8d
0x1400b7146  mov     [rbp+130h+var_90], rax
0x1400b714d  movzx   eax, word ptr [rsp+230h+var_1E8+0Ah]
0x1400b7152  mov     word ptr [rsp+230h+var_200], ax
0x1400b7157  lea     rax, [rsp+230h+var_200]
0x1400b715c  mov     [rbp+130h+var_78], rdi
0x1400b7163  jmp     loc_1400B7355
0x1400b7168  cmp     r9d, 1
0x1400b716c  jnz     short loc_1400B7173
0x1400b716e  or      byte ptr [rsp+230h+var_1E8+9], r14b
0x1400b7173  mov     word ptr [rsp+230h+var_1E8+0Ah], r14w
0x1400b7179  test    byte ptr [rsp+230h+var_1E8+9], r14b
0x1400b717e  jz      loc_1400B7217
0x1400b7184  cmp     r9d, 1
0x1400b7188  jz      loc_1400B7217
0x1400b718e  mov     eax, cs:dword_140064110
0x1400b7194  mov     r8d, 0C000090Bh
0x1400b719a  mov     ebx, r8d
0x1400b719d  cmp     eax, edi
0x1400b719f  jbe     loc_1400B738D
0x1400b71a5  mov     edx, 100h
0x1400b71aa  lea     rcx, dword_140064110
0x1400b71b1  call    _tlgKeywordOn
0x1400b71b6  test    al, al
0x1400b71b8  jz      loc_1400B738D
0x1400b71be  lea     rdx, aVsmmphustorepm; "VsmmPhuStorepMemoryBlockDeserialize"
0x1400b71c5  lea     rcx, [rbp+130h+var_C0]
0x1400b71c9  call    _tlgCreate1Sz_char
0x1400b71ce  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b71d5  lea     rcx, [rbp+130h+var_B0]
0x1400b71dc  call    _tlgCreate1Sz_char
0x1400b71e1  lea     rax, [rsp+230h+var_1F8]
0x1400b71e6  mov     dword ptr [rsp+230h+var_1F8], 201Ch
  ... truncated ...
```
