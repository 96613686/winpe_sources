# Smb2ContinueReadRdmaTail

- ea: `0x14000a100`
- end: `0x14000a4db`
- name: `Smb2ContinueReadRdmaTail`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400041a0`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x14000a034`
- `0x14000a100`
- `0x14000a4e4`
- `0x140022958`
- `0x140029c50`
- `0x140038980`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a304`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a304`
- `srvnet!SmbCryptoGetCryptoKeyNonceSize` at `0x14000a15b`
- `srvnet!SmbCryptoGetCryptoKeyNonceSize` at `0x14000a15b`
- `srvnet!SmbCryptoGetCryptoKeyAuthTagSize` at `0x14000a1a3`
- `srvnet!SmbCryptoGetCryptoKeyAuthTagSize` at `0x14000a1a3`
- `srvnet!SmbCryptoEncryptRdmaPayload` at `0x14000a363`
- `srvnet!SmbCryptoEncryptRdmaPayload` at `0x14000a363`

## string_xrefs

- `0x14000a47d`: `Smb2ContinueReadRdmaTail`
- `0x14000a181`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
__int64 __fastcall Smb2ContinueReadRdmaTail(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdi
  int v3; // r15d
  __int64 v4; // r14
  __int64 v5; // rdx
  unsigned int CryptoKeyNonceSize; // eax
  unsigned __int16 v7; // r12
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int CryptoKeyAuthTagSize; // eax
  unsigned int v12; // r13d
  int ResponseBuffer; // eax
  unsigned int v14; // esi
  __int64 v15; // rbp
  __int64 v16; // rcx
  _WORD *v17; // rsi
  int v18; // ecx
  PVOID v19; // r10
  unsigned int v20; // r12d
  int v21; // eax
  int v22; // eax
  unsigned int v23; // r15d
  int v24; // ecx
  unsigned int v25; // edx
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  unsigned int v27; // [rsp+80h] [rbp+8h]
  __int16 v28; // [rsp+88h] [rbp+10h]

  v1 = a1;
  v2 = a1[70];
  v3 = *(_DWORD *)(v2 + 260);
  v4 = *(_QWORD *)(v2 + 200);
  v5 = 1;
  v27 = *(_DWORD *)(*(_QWORD *)(a1[39] + 24LL) + 72LL);
  if ( !v3 )
  {
    v20 = *(_DWORD *)(*(_QWORD *)(a1[39] + 24LL) + 72LL);
    goto LABEL_42;
  }
  if ( v3 == 1 )
  {
    CryptoKeyNonceSize = SmbCryptoGetCryptoKeyNonceSize(a1[26], 1);
    v7 = CryptoKeyNonceSize;
    if ( CryptoKeyNonceSize > 0xFFFF )
    {
      v8 = 2381;
LABEL_5:
      v9 = 3221225621LL;
LABEL_6:
      a1 = v1;
LABEL_7:
      Smb2SetError(a1, v9, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", v8);
      return Srv2CompleteWorkItem(v1, 0);
    }
    CryptoKeyAuthTagSize = SmbCryptoGetCryptoKeyAuthTagSize(v1[26]);
    if ( CryptoKeyAuthTagSize > 0xFFFF )
    {
      v8 = 2390;
      goto LABEL_5;
    }
  }
  else
  {
    CryptoKeyAuthTagSize = *(_DWORD *)(v2 + 124);
    if ( CryptoKeyAuthTagSize > 0xFFFF )
    {
      v8 = 2403;
      v9 = 3221225621LL;
      goto LABEL_7;
    }
    v7 = *(_WORD *)(v2 + 136);
  }
  v28 = CryptoKeyAuthTagSize;
  v12 = ((unsigned __int16)CryptoKeyAuthTagSize + 7 + v7) & 0xFFFFFFF8;
  ResponseBuffer = Srv2AllocateResponseBuffer(v1, (v12 + *(_DWORD *)(v1[39] + 36LL) + 31) & 0xFFFFFFF8, v1[39]);
  v14 = ResponseBuffer;
  if ( ResponseBuffer < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
          v1,
          ResponseBuffer);
    }
    v8 = 2430;
LABEL_18:
    v9 = v14;
    goto LABEL_6;
  }
  memset(
    (void *)(*(_QWORD *)(v1[39] + 24LL) + *(unsigned int *)(v1[39] + 36LL)),
    0,
    (unsigned int)(*(_DWORD *)(v1[39] + 32LL) - *(_DWORD *)(v1[39] + 36LL)));
  *((_DWORD *)v1 + 121) &= ~4u;
  v5 = 1;
  v15 = *(_QWORD *)(v1[39] + 24LL);
  v16 = *(unsigned __int8 *)(v15 + 66);
  *(_DWORD *)(v15 + 76) |= 1u;
  *(_QWORD *)(v16 + v15) = 0;
  v17 = (_WORD *)(v16 + v15);
  *(_WORD *)(v16 + v15 + 8) = 1;
  v17[9] = v28;
  v17[10] = v7;
  if ( v3 == 1 )
  {
    v17[8] = 1;
    v18 = v12 + 24 + *(unsigned __int8 *)(v15 + 66);
    *(_DWORD *)(v15 + 68) = v12 + 24;
    *(_DWORD *)(v1[39] + 36LL) = v18;
    if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
      v19 = *(PVOID *)(v4 + 24);
    else
      v19 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000010u);
    if ( (*(_BYTE *)(v2 + 264) & 0x30) == 0 )
      __int2c();
    if ( **(_QWORD **)(v2 + 200) )
      __int2c();
    v20 = v27;
    v21 = SmbCryptoEncryptRdmaPayload(
            v1[26],
            v17 + 12,
            (unsigned __int16)v17[9],
            (char *)v17 + (unsigned __int16)v17[9] + 24,
            (unsigned __int16)v17[10],
            v19,
            v27,
            v19);
    v14 = v21;
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, v1, v21);
      }
      v8 = 2499;
      goto LABEL_18;
    }
    goto LABEL_41;
  }
  v20 = v27;
  if ( v3 == 2 )
  {
    v17[8] = 2;
    v22 = Smb2ComputeOutgoingSignatureForRdmaBuffer(v1, v17 + 8, v4, v27);
    v23 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids, v1, v22);
      }
      v8 = 2521;
      v9 = v23;
      goto LABEL_6;
    }
    v24 = *(unsigned __int8 *)(v15 + 66);
    v25 = (((unsigned __int16)v17[10] + 7 + (unsigned __int16)v17[9]) & 0xFFFFFFF8) + 24;
    *(_DWORD *)(v15 + 68) = v25;
    *(_DWORD *)(v1[39] + 36LL) = v25 + v24;
LABEL_41:
    v5 = 1;
  }
LABEL_42:
  LOBYTE(BugCheckOnFailure) = 1;
  LOBYTE(v5) = 6;
  SRV2_PERF_ENTER_EX(v1 + 73, v5, 2533, "Smb2ContinueReadRdmaTail", BugCheckOnFailure);
  return Srv2WriteDirectDataAndCompleteWorkItem((_DWORD)v1, *(_QWORD *)(v2 + 216), *(_DWORD *)(v2 + 232), v4, v20);
}

```

## disassembly

```asm
0x14000a100  mov     [rsp+arg_10], rbx
0x14000a105  push    rbp
0x14000a106  push    rsi
0x14000a107  push    rdi
0x14000a108  push    r12
0x14000a10a  push    r13
0x14000a10c  push    r14
0x14000a10e  push    r15
0x14000a110  sub     rsp, 40h
0x14000a114  mov     rax, [rcx+138h]
0x14000a11b  mov     rbx, rcx
0x14000a11e  mov     rdi, [rcx+230h]
0x14000a125  mov     rdx, [rax+18h]
0x14000a129  mov     r15d, [rdi+104h]
0x14000a130  mov     r14, [rdi+0C8h]
0x14000a137  mov     eax, [rdx+48h]
0x14000a13a  mov     edx, 1
0x14000a13f  mov     [rsp+78h+arg_0], eax
0x14000a146  test    r15d, r15d
0x14000a149  jz      loc_14000A4D6
0x14000a14f  cmp     r15d, edx
0x14000a152  jnz     short loc_14000A1BB
0x14000a154  mov     rcx, [rcx+0D0h]
0x14000a15b  call    cs:__imp_SmbCryptoGetCryptoKeyNonceSize
0x14000a162  nop     dword ptr [rax+rax+00h]
0x14000a167  mov     esi, 0FFFFh
0x14000a16c  mov     r12d, eax
0x14000a16f  cmp     eax, esi
0x14000a171  jbe     short loc_14000A19C
0x14000a173  mov     r9d, 94Dh
0x14000a179  mov     edx, 0C0000095h
0x14000a17e  mov     rcx, rbx
0x14000a181  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14000a188  call    _Smb2SetError
0x14000a18d  xor     edx, edx
0x14000a18f  mov     rcx, rbx
0x14000a192  call    Srv2CompleteWorkItem
0x14000a197  jmp     loc_14000A4AD
0x14000a19c  mov     rcx, [rbx+0D0h]
0x14000a1a3  call    cs:__imp_SmbCryptoGetCryptoKeyAuthTagSize
0x14000a1aa  nop     dword ptr [rax+rax+00h]
0x14000a1af  cmp     eax, esi
0x14000a1b1  jbe     short loc_14000A1D3
0x14000a1b3  mov     r9d, 956h
0x14000a1b9  jmp     short loc_14000A179
0x14000a1bb  mov     eax, [rdi+7Ch]
0x14000a1be  mov     esi, 0FFFFh
0x14000a1c3  cmp     eax, esi
0x14000a1c5  ja      loc_14000A4C6
0x14000a1cb  movzx   r12d, word ptr [rdi+88h]
0x14000a1d3  mov     r8, [rbx+138h]
0x14000a1da  movzx   ecx, ax
0x14000a1dd  mov     [rsp+78h+arg_8], ecx
0x14000a1e4  add     ecx, 7
0x14000a1e7  movzx   r13d, r12w
0x14000a1eb  mov     edx, [r8+24h]
0x14000a1ef  add     r13d, ecx
0x14000a1f2  mov     ecx, 0FFFFFFF8h
0x14000a1f7  add     edx, 1Fh
0x14000a1fa  and     r13d, ecx
0x14000a1fd  add     edx, r13d
0x14000a200  and     edx, ecx
0x14000a202  mov     rcx, rbx
0x14000a205  call    Srv2AllocateResponseBuffer
0x14000a20a  mov     esi, eax
0x14000a20c  test    eax, eax
0x14000a20e  jns     short loc_14000A25D
0x14000a210  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a217  lea     rcx, WPP_GLOBAL_Control
0x14000a21e  cmp     r10, rcx
0x14000a221  jz      short loc_14000A250
0x14000a223  test    dword ptr [r10+2Ch], 800000h
0x14000a22b  jz      short loc_14000A250
0x14000a22d  cmp     byte ptr [r10+29h], 1
0x14000a232  jb      short loc_14000A250
0x14000a234  mov     rcx, [r10+18h]
0x14000a238  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14000a23f  mov     edx, 27h ; '''
0x14000a244  mov     [rsp+78h+BugCheckOnFailure], eax
0x14000a248  mov     r9, rbx
0x14000a24b  call    WPP_SF_qD
0x14000a250  mov     r9d, 97Eh
0x14000a256  mov     edx, esi
0x14000a258  jmp     loc_14000A17E
0x14000a25d  mov     rdx, [rbx+138h]
0x14000a264  mov     ecx, [rdx+24h]
0x14000a267  mov     r8d, [rdx+20h]
0x14000a26b  sub     r8d, ecx; Size
0x14000a26e  add     rcx, [rdx+18h]; void *
0x14000a272  xor     edx, edx; Val
0x14000a274  call    memset
0x14000a279  and     dword ptr [rbx+1E4h], 0FFFFFFFBh
0x14000a280  mov     edx, 1
0x14000a285  mov     rax, [rbx+138h]
0x14000a28c  mov     rbp, [rax+18h]
0x14000a290  mov     eax, [rsp+78h+arg_8]
0x14000a297  movzx   ecx, byte ptr [rbp+42h]
0x14000a29b  or      [rbp+4Ch], edx
0x14000a29e  mov     qword ptr [rcx+rbp], 0
0x14000a2a6  lea     rsi, [rcx+rbp]
0x14000a2aa  mov     [rcx+rbp+8], dx
0x14000a2af  mov     [rsi+12h], ax
0x14000a2b3  mov     [rsi+14h], r12w
0x14000a2b8  cmp     r15d, edx
0x14000a2bb  jnz     loc_14000A3C4
0x14000a2c1  mov     [rsi+10h], dx
0x14000a2c5  lea     eax, [r13+18h]
0x14000a2c9  movzx   ecx, byte ptr [rbp+42h]
0x14000a2cd  add     ecx, eax
0x14000a2cf  mov     [rbp+44h], eax
0x14000a2d2  mov     rax, [rbx+138h]
0x14000a2d9  mov     [rax+24h], ecx
0x14000a2dc  test    byte ptr [r14+0Ah], 5
0x14000a2e1  jz      short loc_14000A2E9
0x14000a2e3  mov     r10, [r14+18h]
0x14000a2e7  jmp     short loc_14000A313
0x14000a2e9  mov     r8d, edx; CacheType
0x14000a2ec  mov     [rsp+78h+Priority], 40000010h; Priority
0x14000a2f4  xor     edx, edx; AccessMode
0x14000a2f6  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000a2fe  xor     r9d, r9d; RequestedAddress
0x14000a301  mov     rcx, r14; MemoryDescriptorList
0x14000a304  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a30b  nop     dword ptr [rax+rax+00h]
0x14000a310  mov     r10, rax
0x14000a313  test    byte ptr [rdi+108h], 30h
0x14000a31a  jnz     short loc_14000A31E
0x14000a31c  int     2Ch; Windows NT - assertion failure
0x14000a31e  mov     rcx, [rdi+0C8h]
0x14000a325  cmp     qword ptr [rcx], 0
0x14000a329  jz      short loc_14000A32D
0x14000a32b  int     2Ch; Windows NT - assertion failure
0x14000a32d  movzx   r8d, word ptr [rsi+12h]
0x14000a332  lea     r9, [rsi+18h]
0x14000a336  movzx   eax, word ptr [rsi+14h]
0x14000a33a  lea     rdx, [rsi+18h]
0x14000a33e  mov     r12d, [rsp+78h+arg_0]
0x14000a346  add     r9, r8
0x14000a349  mov     rcx, [rbx+0D0h]
0x14000a350  mov     [rsp+78h+var_40], r10
0x14000a355  mov     [rsp+78h+var_48], r12d
0x14000a35a  mov     qword ptr [rsp+78h+Priority], r10
0x14000a35f  mov     [rsp+78h+BugCheckOnFailure], eax
0x14000a363  call    cs:__imp_SmbCryptoEncryptRdmaPayload
0x14000a36a  nop     dword ptr [rax+rax+00h]
0x14000a36f  mov     esi, eax
0x14000a371  test    eax, eax
0x14000a373  jns     loc_14000A46B
0x14000a379  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a380  lea     rcx, WPP_GLOBAL_Control
0x14000a387  cmp     r10, rcx
0x14000a38a  jz      short loc_14000A3B9
0x14000a38c  test    dword ptr [r10+2Ch], 800000h
0x14000a394  jz      short loc_14000A3B9
0x14000a396  cmp     byte ptr [r10+29h], 1
0x14000a39b  jb      short loc_14000A3B9
0x14000a39d  mov     rcx, [r10+18h]
0x14000a3a1  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14000a3a8  mov     edx, 28h ; '('
0x14000a3ad  mov     [rsp+78h+BugCheckOnFailure], eax
0x14000a3b1  mov     r9, rbx
0x14000a3b4  call    WPP_SF_qD
0x14000a3b9  mov     r9d, 9C3h
0x14000a3bf  jmp     loc_14000A256
0x14000a3c4  mov     r12d, [rsp+78h+arg_0]
0x14000a3cc  mov     eax, 2
0x14000a3d1  cmp     r15d, eax
0x14000a3d4  jnz     loc_14000A470
0x14000a3da  mov     r9d, r12d
0x14000a3dd  mov     [rsi+10h], ax
0x14000a3e1  mov     r8, r14
0x14000a3e4  lea     rdx, [rsi+10h]
0x14000a3e8  mov     rcx, rbx
0x14000a3eb  call    Smb2ComputeOutgoingSignatureForRdmaBuffer
0x14000a3f0  mov     r15d, eax
0x14000a3f3  test    eax, eax
0x14000a3f5  jns     short loc_14000A445
0x14000a3f7  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a3fe  lea     rcx, WPP_GLOBAL_Control
0x14000a405  cmp     r10, rcx
0x14000a408  jz      short loc_14000A437
0x14000a40a  test    dword ptr [r10+2Ch], 800000h
0x14000a412  jz      short loc_14000A437
0x14000a414  cmp     byte ptr [r10+29h], 1
0x14000a419  jb      short loc_14000A437
0x14000a41b  mov     rcx, [r10+18h]
0x14000a41f  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14000a426  mov     edx, 29h ; ')'
0x14000a42b  mov     [rsp+78h+BugCheckOnFailure], eax
0x14000a42f  mov     r9, rbx
0x14000a432  call    WPP_SF_qD
0x14000a437  mov     r9d, 9D9h
0x14000a43d  mov     edx, r15d
0x14000a440  jmp     loc_14000A17E
0x14000a445  movzx   ecx, word ptr [rsi+14h]
0x14000a449  movzx   edx, word ptr [rsi+12h]
0x14000a44d  add     ecx, 7
0x14000a450  add     edx, ecx
0x14000a452  movzx   ecx, byte ptr [rbp+42h]
0x14000a456  and     edx, 0FFFFFFF8h
0x14000a459  add     edx, 18h
0x14000a45c  mov     [rbp+44h], edx
0x14000a45f  add     ecx, edx
0x14000a461  mov     rax, [rbx+138h]
0x14000a468  mov     [rax+24h], ecx
0x14000a46b  mov     edx, 1
0x14000a470  mov     byte ptr [rsp+78h+BugCheckOnFailure], dl
0x14000a474  lea     rcx, [rbx+248h]
0x14000a47b  mov     dl, 6
0x14000a47d  lea     r9, aSmb2continuere; "Smb2ContinueReadRdmaTail"
0x14000a484  mov     r8d, 9E5h
0x14000a48a  call    SRV2_PERF_ENTER_EX
0x14000a48f  mov     r8d, [rdi+0E8h]
0x14000a496  mov     r9, r14
0x14000a499  mov     rdx, [rdi+0D8h]
0x14000a4a0  mov     rcx, rbx
0x14000a4a3  mov     [rsp+78h+BugCheckOnFailure], r12d
0x14000a4a8  call    Srv2WriteDirectDataAndCompleteWorkItem
0x14000a4ad  mov     rbx, [rsp+78h+arg_10]
0x14000a4b5  add     rsp, 40h
0x14000a4b9  pop     r15
0x14000a4bb  pop     r14
0x14000a4bd  pop     r13
0x14000a4bf  pop     r12
0x14000a4c1  pop     rdi
0x14000a4c2  pop     rsi
0x14000a4c3  pop     rbp
0x14000a4c4  retn
0x14000a4c6  mov     r9d, 963h
0x14000a4cc  mov     edx, 0C0000095h
0x14000a4d1  jmp     loc_14000A181
0x14000a4d6  mov     r12d, eax
0x14000a4d9  jmp     short loc_14000A470
```
