# VidTdxIoctlPartitionCreateScanContext

- ea: `0x14007b274`
- end: `0x14007b71e`
- name: `VidTdxIoctlPartitionCreateScanContext`
- size: `1194`
- prototype: `__int64 __fastcall(__int64, unsigned __int8, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x1400246b0`
- `0x140024718`
- `0x140024c78`
- `0x140030790`
- `0x1400307d0`
- `0x14007a4ac`
- `0x14007b274`
- `0x1400ef710`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007b431`
- `ntoskrnl!ExAllocatePool2` at `0x14007b431`
- `winhvr!WinHvCreateTdScanContext` at `0x14007b491`
- `winhvr!WinHvCreateTdScanContext` at `0x14007b491`

## string_xrefs

- `0x14007b2e9`: `VidTdxIoctlPartitionCreateScanContext`

## pseudocode

```c
__int64 __fastcall VidTdxIoctlPartitionCreateScanContext(__int64 a1, unsigned __int8 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r13
  __int64 v6; // r12
  __int64 *v7; // r14
  int v8; // ecx
  __int64 v9; // rdx
  unsigned int v10; // edx
  __int64 *v11; // rcx
  __int64 v12; // r8
  int TdScanContext; // ebx
  char v14; // r12
  _QWORD *Pool2; // rax
  _QWORD *v16; // rdi
  int v17; // r8d
  bool v18; // zf
  unsigned int v19; // edx
  __int64 *v20; // rcx
  unsigned int v21; // edx
  __int64 *v22; // rcx
  char v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  GUID v28[5]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v29[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[32]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v32; // [rsp+100h] [rbp+0h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]
  __int64 *v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  __int64 *v36; // [rsp+120h] [rbp+20h]
  __int64 v37; // [rsp+128h] [rbp+28h] BYREF
  __int64 *v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h] BYREF
  __int64 *v40; // [rsp+140h] [rbp+40h]
  __int64 v41; // [rsp+148h] [rbp+48h]
  __int64 *v42; // [rsp+150h] [rbp+50h]
  __int64 v43; // [rsp+158h] [rbp+58h]

  v26 = a3;
  v3 = a3;
  v4 = a2;
  memset(v29, 0, 24);
  memset(v28, 0, sizeof(v28));
  v6 = -1;
  v25 = -1;
  VidTraceActivityInitialize(v28);
  v7 = (__int64 *)(a1 + 648);
  *(_QWORD *)v28[3].Data4 = *(_QWORD *)(a1 + 648);
  v8 = a1 + 656;
  v9 = a1 + 120;
  *(_QWORD *)&v28[0].Data1 = "VidTdxIoctlPartitionCreateScanContext";
  *(_QWORD *)&v28[3].Data1 = a1 + 656;
  *(_QWORD *)&v28[4].Data1 = a1 + 120;
  if ( (unsigned int)dword_140064110 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v31, *(_QWORD *)&v28[0].Data1);
      v32 = *(_QWORD *)&v28[3].Data1;
      v33 = 16;
      v10 = (unsigned __int16)**(_WORD **)&v28[4].Data1;
      v11 = *(__int64 **)(*(_QWORD *)&v28[4].Data1 + 8LL);
      v34 = &v37;
      v27 = *(_QWORD *)v28[3].Data4;
      v38 = &v27;
      v40 = (__int64 *)&v24;
      v36 = v11;
      v37 = v10;
      v39 = v12;
      v35 = 2;
      v24 = v4;
      v41 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_140045D80, &v28[2], &v28[1], v12, v30);
    }
    v9 = a1 + 120;
    v8 = a1 + 656;
  }
  v28[4].Data4[0] = 1;
  if ( (unsigned __int8)v4 >= *(_BYTE *)(a1 + 2040) )
  {
    TdScanContext = -1073741811;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateScanContext",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      438,
      v8,
      v9,
      *v7,
      -1073741811);
    goto LABEL_18;
  }
  v14 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 112, 1917084758);
  v16 = Pool2;
  if ( !Pool2 )
  {
    TdScanContext = -1073741670;
    v17 = 451;
    goto LABEL_13;
  }
  *Pool2 = 0;
  memset(Pool2 + 4, 0, 0x48u);
  v16[10] = v16 + 9;
  v16[9] = v16 + 9;
  v16[1] = -1;
  v16[13] = 0;
  TdScanContext = WinHvCreateTdScanContext(*v7, *(unsigned __int8 *)(v4 + a1 + 2041), v29);
  if ( TdScanContext < 0 )
  {
    v17 = 475;
    goto LABEL_13;
  }
  v6 = *(_QWORD *)&v29[0];
  v16[1] = *(_QWORD *)&v29[0];
  v25 = v6;
  *((_OWORD *)v16 + 1) = *(_OWORD *)((char *)v29 + 8);
  VidLockAcquireExclusive(a1 + 12800);
  TdScanContext = VidHandleTableAllocateEntry(a1 + 12768, v16, v26);
  if ( TdScanContext < 0 )
  {
    v14 = 1;
    v17 = 493;
LABEL_13:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateScanContext",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      v17,
      a1 + 656,
      a1 + 120,
      *v7,
      TdScanContext);
    if ( v16 )
      VidTdxScanContextTeardown(a1, v16);
    v18 = v14 == 0;
    v6 = v25;
    if ( v18 )
      goto LABEL_17;
  }
  VidLockRelease(a1 + 12800);
LABEL_17:
  v3 = v26;
LABEL_18:
  if ( v28[4].Data4[0] )
  {
    if ( TdScanContext < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        v31[0] = &v25;
        LODWORD(v25) = TdScanContext;
        v31[1] = 4;
        tlgCreate1Sz_char(&v32, *(_QWORD *)&v28[0].Data1);
        v34 = *(__int64 **)&v28[3].Data1;
        v35 = 16;
        v21 = (unsigned __int16)**(_WORD **)&v28[4].Data1;
        v22 = *(__int64 **)(*(_QWORD *)&v28[4].Data1 + 8LL);
        v36 = &v39;
        v27 = *(_QWORD *)v28[3].Data4;
        v40 = &v27;
        v38 = v22;
        v39 = v21;
        v37 = 2;
        v41 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_140045C9A, &v28[2], 0, 8, v30);
      }
    }
    else if ( (unsigned int)dword_140064110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v31, *(_QWORD *)&v28[0].Data1);
      v32 = *(_QWORD *)&v28[3].Data1;
      v33 = 16;
      v19 = (unsigned __int16)**(_WORD **)&v28[4].Data1;
      v20 = *(__int64 **)(*(_QWORD *)&v28[4].Data1 + 8LL);
      v34 = &v37;
      v27 = *(_QWORD *)v28[3].Data4;
      v38 = &v27;
      v26 = (_QWORD *)*v3;
      v40 = (__int64 *)&v26;
      v42 = &v25;
      v37 = v19;
      v35 = 2;
      v36 = v20;
      v39 = 8;
      v41 = 8;
      v25 = v6;
      v43 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140045D01, &v28[2], 0, 9, v30);
    }
    VidTraceActivityTeardown(v28);
  }
  return (unsigned int)TdScanContext;
}

```

## disassembly

```asm
0x14007b274  mov     [rsp-8+arg_18], rbx
0x14007b279  push    rbp
0x14007b27a  push    rsi
0x14007b27b  push    rdi
0x14007b27c  push    r12
0x14007b27e  push    r13
0x14007b280  push    r14
0x14007b282  push    r15
0x14007b284  lea     rbp, [rsp-70h]
0x14007b289  sub     rsp, 170h
0x14007b290  mov     rax, cs:__security_cookie
0x14007b297  xor     rax, rsp
0x14007b29a  mov     [rbp+0A0h+var_40], rax
0x14007b29e  xor     eax, eax
0x14007b2a0  mov     [rsp+1A0h+var_150], r8
0x14007b2a5  mov     rdi, r8
0x14007b2a8  movzx   r13d, dl
0x14007b2ac  mov     rsi, rcx
0x14007b2af  mov     [rbp+0A0h+var_E0], rax
0x14007b2b3  xorps   xmm0, xmm0
0x14007b2b6  lea     rcx, [rsp+1A0h+var_140]; void *
0x14007b2bb  lea     r8d, [rax+50h]; Size
0x14007b2bf  xor     edx, edx; Val
0x14007b2c1  movups  [rbp+0A0h+var_F0], xmm0
0x14007b2c5  call    memset
0x14007b2ca  or      r12, 0FFFFFFFFFFFFFFFFh
0x14007b2ce  lea     rcx, [rsp+1A0h+var_140]
0x14007b2d3  mov     [rsp+1A0h+var_158], r12
0x14007b2d8  call    VidTraceActivityInitialize
0x14007b2dd  lea     r14, [rsi+288h]
0x14007b2e4  xor     ebx, ebx
0x14007b2e6  mov     rax, [r14]
0x14007b2e9  lea     r15, aVidtdxioctlpar_19; "VidTdxIoctlPartitionCreateScanContext"
0x14007b2f0  mov     [rbp+0A0h+var_108], rax
0x14007b2f4  lea     rcx, [rsi+290h]
0x14007b2fb  mov     eax, cs:dword_140064110
0x14007b301  lea     rdx, [rsi+78h]
0x14007b305  mov     [rsp+1A0h+var_140], r15
0x14007b30a  lea     r8d, [r12+9]
0x14007b30f  mov     [rbp+0A0h+var_110], rcx
0x14007b313  mov     [rbp+0A0h+var_100], rdx
0x14007b317  cmp     eax, 5
0x14007b31a  jbe     loc_14007B3DD
0x14007b320  mov     edx, 100h
0x14007b325  lea     rcx, dword_140064110
0x14007b32c  call    _tlgKeywordOn
0x14007b331  test    al, al
0x14007b333  jz      loc_14007B3D2
0x14007b339  mov     rdx, [rsp+1A0h+var_140]
0x14007b33e  lea     rcx, [rbp+0A0h+var_B0]
0x14007b342  call    _tlgCreate1Sz_char
0x14007b347  mov     rax, [rbp+0A0h+var_100]
0x14007b34b  lea     r9, [rsp+1A0h+var_130]
0x14007b350  mov     rcx, [rbp+0A0h+var_110]
0x14007b354  mov     [rbp+0A0h+var_A0], rcx
0x14007b358  mov     [rbp+0A0h+var_98], 10h
0x14007b360  movzx   edx, word ptr [rax]
0x14007b363  mov     rcx, [rax+8]
0x14007b367  lea     rax, [rbp+0A0h+var_78]
0x14007b36b  mov     [rbp+0A0h+var_90], rax
0x14007b36f  mov     rax, [rbp+0A0h+var_108]
0x14007b373  mov     [rsp+1A0h+var_148], rax
0x14007b378  lea     rax, [rsp+1A0h+var_148]
0x14007b37d  mov     [rbp+0A0h+var_70], rax
0x14007b381  lea     rax, [rsp+1A0h+var_160]
0x14007b386  mov     [rbp+0A0h+var_60], rax
0x14007b38a  lea     rax, [rbp+0A0h+var_D0]
0x14007b38e  mov     [rsp+1A0h+var_178], rax
0x14007b393  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14007b398  mov     [rbp+0A0h+var_80], rcx
0x14007b39c  lea     rcx, dword_140064110
0x14007b3a3  mov     dword ptr [rbp+0A0h+var_78], edx
0x14007b3a6  lea     rdx, qword_140045D80
0x14007b3ad  mov     [rbp+0A0h+var_68], r8
0x14007b3b1  lea     r8, [rbp+0A0h+var_120]
0x14007b3b5  mov     [rbp+0A0h+var_88], 2
0x14007b3bd  mov     dword ptr [rbp+0A0h+var_78+4], ebx
0x14007b3c0  mov     [rsp+1A0h+var_160], r13b
0x14007b3c5  mov     [rbp+0A0h+var_58], 1
0x14007b3cd  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007b3d2  lea     rdx, [rsi+78h]
0x14007b3d6  lea     rcx, [rsi+290h]
0x14007b3dd  mov     [rbp+0A0h+var_F8], 1
0x14007b3e1  cmp     r13b, [rsi+7F8h]
0x14007b3e8  jb      short loc_14007B420
0x14007b3ea  mov     ebx, 0C000000Dh
0x14007b3ef  mov     rax, [r14]
0x14007b3f2  mov     r9, rcx
0x14007b3f5  mov     [rsp+1A0h+var_170], ebx
0x14007b3f9  mov     r8d, 1B6h
0x14007b3ff  mov     [rsp+1A0h+var_178], rax
0x14007b404  mov     rcx, r15
0x14007b407  mov     [rsp+1A0h+var_180], rdx
0x14007b40c  lea     rdx, aOnecoreVmVidSy_21; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007b413  call    VidTracePartitionErrorInternal0
0x14007b418  xor     r13d, r13d
0x14007b41b  jmp     loc_14007B549
0x14007b420  mov     edx, 70h ; 'p'
0x14007b425  mov     r8d, 72446456h
0x14007b42b  mov     r12b, bl
0x14007b42e  lea     ecx, [rdx-30h]
0x14007b431  call    cs:__imp_ExAllocatePool2
0x14007b438  nop     dword ptr [rax+rax+00h]
0x14007b43d  mov     rdi, rax
0x14007b440  test    rax, rax
0x14007b443  jnz     short loc_14007B458
0x14007b445  mov     ebx, 0C000009Ah
0x14007b44a  mov     r8d, 1C3h
0x14007b450  xor     r13d, r13d
0x14007b453  jmp     loc_14007B4F3
0x14007b458  xor     edx, edx; Val
0x14007b45a  mov     [rax], rbx
0x14007b45d  lea     rcx, [rax+20h]; void *
0x14007b461  lea     r8d, [rdx+48h]; Size
0x14007b465  call    memset
0x14007b46a  lea     rax, [rdi+48h]
0x14007b46e  mov     [rax+8], rax
0x14007b472  lea     r8, [rbp+0A0h+var_F0]
0x14007b476  mov     [rax], rax
0x14007b479  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14007b481  mov     [rdi+68h], rbx
0x14007b485  movzx   edx, byte ptr [r13+rsi+7F9h]
0x14007b48e  mov     rcx, [r14]
0x14007b491  call    cs:__imp_WinHvCreateTdScanContext
0x14007b498  nop     dword ptr [rax+rax+00h]
0x14007b49d  xor     r13d, r13d
0x14007b4a0  mov     ebx, eax
0x14007b4a2  test    eax, eax
0x14007b4a4  jns     short loc_14007B4AE
0x14007b4a6  mov     r8d, 1DBh
0x14007b4ac  jmp     short loc_14007B4F3
0x14007b4ae  mov     r12, qword ptr [rbp+0A0h+var_F0]
0x14007b4b2  lea     rcx, [rsi+3200h]
0x14007b4b9  mov     [rdi+8], r12
0x14007b4bd  movups  xmm0, [rbp+0A0h+var_F0+8]
0x14007b4c1  mov     [rsp+1A0h+var_158], r12
0x14007b4c6  movdqu  xmmword ptr [rdi+10h], xmm0
0x14007b4cb  call    VidLockAcquireExclusive
0x14007b4d0  mov     r8, [rsp+1A0h+var_150]
0x14007b4d5  lea     rcx, [rsi+31E0h]
0x14007b4dc  mov     rdx, rdi
0x14007b4df  call    VidHandleTableAllocateEntry
0x14007b4e4  mov     ebx, eax
0x14007b4e6  test    eax, eax
0x14007b4e8  jns     short loc_14007B538
0x14007b4ea  mov     r12b, 1
0x14007b4ed  mov     r8d, 1EDh
0x14007b4f3  lea     rdx, aOnecoreVmVidSy_21; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007b4fa  mov     rax, [r14]
0x14007b4fd  lea     r9, [rsi+290h]
0x14007b504  mov     [rsp+1A0h+var_170], ebx
0x14007b508  mov     rcx, r15
0x14007b50b  mov     [rsp+1A0h+var_178], rax
0x14007b510  lea     rax, [rsi+78h]
0x14007b514  mov     [rsp+1A0h+var_180], rax
0x14007b519  call    VidTracePartitionErrorInternal0
0x14007b51e  test    rdi, rdi
0x14007b521  jz      short loc_14007B52E
0x14007b523  mov     rdx, rdi
0x14007b526  mov     rcx, rsi
0x14007b529  call    VidTdxScanContextTeardown
0x14007b52e  test    r12b, r12b
0x14007b531  mov     r12, [rsp+1A0h+var_158]
0x14007b536  jz      short loc_14007B544
0x14007b538  lea     rcx, [rsi+3200h]
0x14007b53f  call    VidLockRelease
0x14007b544  mov     rdi, [rsp+1A0h+var_150]
0x14007b549  cmp     [rbp+0A0h+var_F8], r13b
0x14007b54d  jz      loc_14007B6F4
0x14007b553  mov     eax, cs:dword_140064110
0x14007b559  test    ebx, ebx
0x14007b55b  js      loc_14007B62D
0x14007b561  cmp     eax, 5
0x14007b564  jbe     loc_14007B6EA
0x14007b56a  mov     edx, 100h
0x14007b56f  lea     rcx, dword_140064110
0x14007b576  call    _tlgKeywordOn
0x14007b57b  test    al, al
0x14007b57d  jz      loc_14007B6EA
0x14007b583  mov     rdx, [rsp+1A0h+var_140]
0x14007b588  lea     rcx, [rbp+0A0h+var_B0]
0x14007b58c  call    _tlgCreate1Sz_char
0x14007b591  mov     rax, [rbp+0A0h+var_100]
0x14007b595  mov     rcx, [rbp+0A0h+var_110]
0x14007b599  mov     [rbp+0A0h+var_A0], rcx
0x14007b59d  mov     [rbp+0A0h+var_98], 10h
0x14007b5a5  movzx   edx, word ptr [rax]
0x14007b5a8  mov     rcx, [rax+8]
0x14007b5ac  lea     rax, [rbp+0A0h+var_78]
0x14007b5b0  mov     [rbp+0A0h+var_90], rax
0x14007b5b4  mov     rax, [rbp+0A0h+var_108]
0x14007b5b8  mov     [rsp+1A0h+var_148], rax
0x14007b5bd  lea     rax, [rsp+1A0h+var_148]
0x14007b5c2  mov     [rbp+0A0h+var_70], rax
0x14007b5c6  mov     rax, [rdi]
0x14007b5c9  mov     [rsp+1A0h+var_150], rax
0x14007b5ce  lea     rax, [rsp+1A0h+var_150]
0x14007b5d3  mov     [rbp+0A0h+var_60], rax
0x14007b5d7  lea     rax, [rsp+1A0h+var_158]
0x14007b5dc  mov     [rbp+0A0h+var_50], rax
0x14007b5e0  lea     rax, [rbp+0A0h+var_D0]
0x14007b5e4  mov     [rsp+1A0h+var_178], rax
0x14007b5e9  mov     dword ptr [rbp+0A0h+var_78], edx
0x14007b5ec  lea     rdx, byte_140045D01
0x14007b5f3  mov     dword ptr [rsp+1A0h+var_180], 9
0x14007b5fb  mov     [rbp+0A0h+var_88], 2
0x14007b603  mov     [rbp+0A0h+var_80], rcx
0x14007b607  mov     dword ptr [rbp+0A0h+var_78+4], r13d
0x14007b60b  mov     [rbp+0A0h+var_68], 8
0x14007b613  mov     [rbp+0A0h+var_58], 8
0x14007b61b  mov     [rsp+1A0h+var_158], r12
0x14007b620  mov     [rbp+0A0h+var_48], 8
0x14007b628  jmp     loc_14007B6D7
0x14007b62d  cmp     eax, 2
0x14007b630  jbe     loc_14007B6EA
0x14007b636  mov     edx, 100h
0x14007b63b  lea     rcx, dword_140064110
0x14007b642  call    _tlgKeywordOn
0x14007b647  test    al, al
0x14007b649  jz      loc_14007B6EA
0x14007b64f  mov     rdx, [rsp+1A0h+var_140]
0x14007b654  lea     rax, [rsp+1A0h+var_158]
0x14007b659  lea     rcx, [rbp+0A0h+var_A0]
0x14007b65d  mov     [rbp+0A0h+var_B0], rax
0x14007b661  mov     dword ptr [rsp+1A0h+var_158], ebx
0x14007b665  mov     [rbp+0A0h+var_A8], 4
0x14007b66d  call    _tlgCreate1Sz_char
0x14007b672  mov     rax, [rbp+0A0h+var_100]
0x14007b676  mov     rcx, [rbp+0A0h+var_110]
0x14007b67a  mov     [rbp+0A0h+var_90], rcx
0x14007b67e  mov     [rbp+0A0h+var_88], 10h
0x14007b686  movzx   edx, word ptr [rax]
0x14007b689  mov     rcx, [rax+8]
0x14007b68d  lea     rax, [rbp+0A0h+var_68]
0x14007b691  mov     [rbp+0A0h+var_80], rax
0x14007b695  mov     rax, [rbp+0A0h+var_108]
0x14007b699  mov     [rsp+1A0h+var_148], rax
0x14007b69e  lea     rax, [rsp+1A0h+var_148]
0x14007b6a3  mov     [rbp+0A0h+var_60], rax
0x14007b6a7  lea     rax, [rbp+0A0h+var_D0]
0x14007b6ab  mov     [rbp+0A0h+var_70], rcx
0x14007b6af  mov     ecx, 8
0x14007b6b4  mov     [rsp+1A0h+var_178], rax
0x14007b6b9  mov     dword ptr [rbp+0A0h+var_68], edx
0x14007b6bc  lea     rdx, word_140045C9A
0x14007b6c3  mov     dword ptr [rsp+1A0h+var_180], ecx
0x14007b6c7  mov     [rbp+0A0h+var_78], 2
0x14007b6cf  mov     dword ptr [rbp+0A0h+var_68+4], r13d
0x14007b6d3  mov     [rbp+0A0h+var_58], rcx
0x14007b6d7  xor     r9d, r9d
0x14007b6da  lea     r8, [rbp+0A0h+var_120]
0x14007b6de  lea     rcx, dword_140064110
0x14007b6e5  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007b6ea  lea     rcx, [rsp+1A0h+var_140]
0x14007b6ef  call    VidTraceActivityTeardown
0x14007b6f4  mov     eax, ebx
0x14007b6f6  mov     rcx, [rbp+0A0h+var_40]
0x14007b6fa  xor     rcx, rsp; StackCookie
0x14007b6fd  call    __security_check_cookie
0x14007b702  mov     rbx, [rsp+1A0h+arg_18]
0x14007b70a  add     rsp, 170h
0x14007b711  pop     r15
0x14007b713  pop     r14
0x14007b715  pop     r13
0x14007b717  pop     r12
0x14007b719  pop     rdi
0x14007b71a  pop     rsi
0x14007b71b  pop     rbp
0x14007b71c  retn
```
