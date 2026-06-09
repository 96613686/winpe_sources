# OncRpcSepProcessIncomingReplyGssInit

- ea: `0x14000bf88`
- end: `0x14000c46a`
- name: `OncRpcSepProcessIncomingReplyGssInit`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140009dc4`

## callees

- `0x1400020c0`
- `0x1400059f8`
- `0x14000a1ec`
- `0x14000bf88`
- `0x14000cb78`
- `0x14000d104`
- `0x14000d154`
- `0x140012838`
- `0x140015640`
- `0x140015720`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c08a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c08a`
- `ksecdd!QueryContextAttributesW` at `0x14000c35a`
- `ksecdd!QueryContextAttributesW` at `0x14000c35a`
- `ksecdd!InitializeSecurityContextW` at `0x14000c272`
- `ksecdd!InitializeSecurityContextW` at `0x14000c272`
- `ksecdd!MapSecurityError` at `0x14000c297`
- `ksecdd!MapSecurityError` at `0x14000c36f`
- `ksecdd!MapSecurityError` at `0x14000c297`
- `ksecdd!MapSecurityError` at `0x14000c36f`

## pseudocode

```c
__int64 __fastcall OncRpcSepProcessIncomingReplyGssInit(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  NTSTATUS v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  void *v9; // r14
  int v10; // eax
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // r9
  int v15; // r14d
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // r12d
  __int64 v22; // rbx
  bool v23; // zf
  __int64 v24; // rcx
  unsigned int v25; // r9d
  unsigned int v26; // eax
  int v27; // eax
  SECURITY_STATUS v28; // ecx
  _DWORD *v29; // rbx
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  struct _SecHandle *v32; // rcx
  unsigned int v33; // eax
  SECURITY_STATUS v34; // ecx
  void *Buf1; // [rsp+60h] [rbp-29h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+68h] [rbp-21h] BYREF
  struct _SecBufferDesc pInput; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v39[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v40; // [rsp+90h] [rbp+7h]
  __int128 pBuffer; // [rsp+98h] [rbp+Fh] BYREF

  v2 = *(_QWORD *)(a1 + 1008);
  *(_QWORD *)&pBuffer = a2;
  if ( *(_DWORD *)(v2 + 64) != 1 )
    goto LABEL_2;
  v5 = ((__int64 (*)(void))XdrDecodeInt_0)();
  v4 = *(_DWORD *)(a1 + 264);
  v6 = v5;
  if ( v4 < 0 )
    goto LABEL_3;
  if ( v5 - 1 > 0x18F )
    goto LABEL_2;
  v7 = *(_QWORD *)(a1 + 1008);
  if ( !*(_QWORD *)(v7 + 24) )
  {
    *(_DWORD *)(v7 + 32) = v6;
    v12 = *(_QWORD *)(a1 + 1008);
    v13 = *(unsigned int *)(v12 + 32);
    v14 = (_QWORD *)(v12 + 24);
    if ( (unsigned int)v13 > 4 )
    {
      v4 = NfsMemMgrBufferAllocate(512, 1131366226, v13, v14);
      if ( v4 < 0 )
        goto LABEL_3;
    }
    else
    {
      *v14 = v12 + 36;
    }
    XdrDecodeOpaque(a1, *(unsigned int *)(*(_QWORD *)(a1 + 1008) + 32LL), *(_QWORD *)(*(_QWORD *)(a1 + 1008) + 24LL));
    v4 = *(_DWORD *)(a1 + 264);
    goto LABEL_19;
  }
  if ( v6 != *(_DWORD *)(v7 + 32) )
  {
LABEL_2:
    v4 = -1073741811;
    goto LABEL_3;
  }
  Buf1 = 0;
  v8 = NfsMemMgrBufferAllocate(512, 1131366226, v6, &Buf1);
  v9 = Buf1;
  v4 = v8;
  if ( v8 >= 0 )
  {
    XdrDecodeOpaque(a1, v6, Buf1);
    v4 = *(_DWORD *)(a1 + 264);
    if ( v4 >= 0 )
    {
      v10 = memcmp(v9, *(const void **)(*(_QWORD *)(a1 + 1008) + 24LL), v6);
      v11 = v4;
      if ( v10 )
        v11 = -1073741811;
      v4 = v11;
    }
  }
  if ( v9 )
    ExFreePoolWithTag(v9, 0x436F4752u);
LABEL_19:
  if ( v4 >= 0 )
  {
    v15 = XdrDecodeInt_0(a1);
    XdrDecodeInt_0(a1);
    v16 = *(_QWORD *)(a1 + 72);
    if ( v16 )
      v17 = *(_QWORD *)(v16 + 64);
    else
      LODWORD(v17) = 0;
    v18 = *(_QWORD *)(a1 + 1008);
    *(_DWORD *)(v18 + 72) = XdrDecodeInt_0(a1);
    v19 = XdrDecodeInt_0(a1);
    v20 = *(_QWORD *)(a1 + 72);
    v21 = v19;
    if ( v20 )
      v22 = *(_QWORD *)(v20 + 64);
    else
      v22 = 0;
    if ( *(int *)(a1 + 264) < 0 || v19 > (unsigned int)XdrBytesLeft(a1) )
    {
      v4 = -2147483643;
    }
    else
    {
      if ( v15 )
        v23 = v15 == 1;
      else
        v23 = *(_DWORD *)(a1 + 288) == 6;
      if ( v23 )
      {
        v24 = *(_QWORD *)(a1 + 1008);
        if ( *(_BYTE *)(v24 + 56) )
        {
          LODWORD(Buf1) = 0;
          pOutput = 0;
          v25 = 1073807618;
          pInput = 0;
          if ( *(_DWORD *)(v24 + 120) != 3 )
            v25 = 65794;
          if ( byte_14001AA22 )
            v25 |= 0x400u;
          pInput.ulVersion = 0;
          pInput.pBuffers = (PSecBuffer)v39;
          pOutput.pBuffers = (PSecBuffer)(v24 + 40);
          pOutput.ulVersion = 0;
          v39[1] = 2;
          v39[0] = v21;
          pInput.cBuffers = 1;
          pOutput.cBuffers = 1;
          v40 = v22;
          *(_DWORD *)(v24 + 44) = 2;
          *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 40LL) = 0;
          *(_QWORD *)(*(_QWORD *)(a1 + 1008) + 48LL) = 0;
          v26 = InitializeSecurityContextW(
                  (PCredHandle)(*(_QWORD *)(a1 + 1008) + 80LL),
                  (PCtxtHandle)(*(_QWORD *)(a1 + 1008) + 96LL),
                  (PSECURITY_STRING)(*(_QWORD *)(a1 + 1008) + 192LL),
                  v25,
                  0,
                  0x10u,
                  &pInput,
                  0,
                  (PCtxtHandle)(*(_QWORD *)(a1 + 1008) + 96LL),
                  &pOutput,
                  (unsigned int *)&Buf1,
                  (PTimeStamp)(*(_QWORD *)(a1 + 1008) + 112LL));
          v27 = OncRpcSeSecStatusToGssMajor(v26);
          v29 = (_DWORD *)pBuffer;
          *(_DWORD *)pBuffer = v27;
          if ( v28 == 590610 || !v28 )
          {
            *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 60LL) |= 2u;
            if ( !v28 )
              *(_BYTE *)(*(_QWORD *)(a1 + 1008) + 56LL) = 0;
          }
          else
          {
            v4 = MapSecurityError(v28);
            if ( v4 < 0 )
              goto LABEL_3;
          }
        }
        else
        {
          v29 = (_DWORD *)pBuffer;
        }
        if ( v15 )
          goto LABEL_57;
        v4 = OncRpcSepVerifyMessage(
               (unsigned int)*(_QWORD *)(a1 + 1008) + 96,
               (_DWORD)v29,
               0,
               v17,
               4,
               a1 + 32,
               *(_QWORD *)(a1 + 360),
               *(_DWORD *)(a1 + 352));
        if ( v4 >= 0 )
        {
          v32 = (struct _SecHandle *)(*(_QWORD *)(a1 + 1008) + 96LL);
          pBuffer = 0;
          v33 = QueryContextAttributesW(v32, 0, &pBuffer);
          *v29 = OncRpcSeSecStatusToGssMajor(v33);
          v4 = MapSecurityError(v34);
          if ( v4 >= 0 )
          {
            *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 208LL) = HIDWORD(pBuffer);
            *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 212LL) = DWORD2(pBuffer);
            *(_QWORD *)(*(_QWORD *)(a1 + 1008) + 216LL) = pBuffer;
            *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 64LL) = 2;
            goto LABEL_57;
          }
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
          {
            goto LABEL_3;
          }
          v31 = 54;
        }
        else
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
          {
            goto LABEL_3;
          }
          v31 = 53;
        }
        WPP_SF_d(v30->AttachedDevice, v31, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v4);
      }
      else
      {
        v4 = -1073741790;
      }
    }
  }
LABEL_3:
  *(_DWORD *)(*(_QWORD *)(a1 + 1008) + 64LL) = 3;
LABEL_57:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000bf88  mov     [rsp-8+arg_10], rbx
0x14000bf8d  push    rbp
0x14000bf8e  push    rsi
0x14000bf8f  push    rdi
0x14000bf90  push    r12
0x14000bf92  push    r13
0x14000bf94  push    r14
0x14000bf96  push    r15
0x14000bf98  lea     rbp, [rsp-27h]
0x14000bf9d  sub     rsp, 0B0h
0x14000bfa4  mov     rax, cs:__security_cookie
0x14000bfab  xor     rax, rsp
0x14000bfae  mov     [rbp+57h+var_38], rax
0x14000bfb2  mov     rax, [rcx+3F0h]
0x14000bfb9  mov     rsi, rcx
0x14000bfbc  mov     qword ptr [rbp+57h+pBuffer], rdx
0x14000bfc0  cmp     dword ptr [rax+40h], 1
0x14000bfc4  jz      short loc_14000BFE5
0x14000bfc6  mov     edi, 0C000000Dh
0x14000bfcb  lea     rbx, WPP_GLOBAL_Control
0x14000bfd2  mov     rax, [rsi+3F0h]
0x14000bfd9  mov     dword ptr [rax+40h], 3
0x14000bfe0  jmp     loc_14000C415
0x14000bfe5  call    XdrDecodeInt_0
0x14000bfea  mov     edi, [rsi+108h]
0x14000bff0  mov     ebx, eax
0x14000bff2  test    edi, edi
0x14000bff4  js      short loc_14000BFCB
0x14000bff6  lea     eax, [rbx-1]
0x14000bff9  cmp     eax, 18Fh
0x14000bffe  ja      short loc_14000BFC6
0x14000c000  mov     rax, [rsi+3F0h]
0x14000c007  cmp     qword ptr [rax+18h], 0
0x14000c00c  jz      loc_14000C098
0x14000c012  cmp     ebx, [rax+20h]
0x14000c015  jnz     short loc_14000BFC6
0x14000c017  lea     r9, [rbp+57h+Buf1]
0x14000c01b  mov     [rbp+57h+Buf1], 0
0x14000c023  mov     r8d, ebx
0x14000c026  mov     edx, 436F4752h
0x14000c02b  mov     ecx, 200h
0x14000c030  call    NfsMemMgrBufferAllocate
0x14000c035  mov     r14, [rbp+57h+Buf1]
0x14000c039  mov     edi, eax
0x14000c03b  test    eax, eax
0x14000c03d  js      short loc_14000C07D
0x14000c03f  mov     r8, r14
0x14000c042  mov     edx, ebx
0x14000c044  mov     rcx, rsi
0x14000c047  call    XdrDecodeOpaque
0x14000c04c  mov     edi, [rsi+108h]
0x14000c052  test    edi, edi
0x14000c054  js      short loc_14000C07D
0x14000c056  mov     rdx, [rsi+3F0h]
0x14000c05d  mov     r8d, ebx; Size
0x14000c060  mov     rcx, r14; Buf1
0x14000c063  mov     rdx, [rdx+18h]; Buf2
0x14000c067  call    memcmp
0x14000c06c  mov     r8d, edi
0x14000c06f  test    eax, eax
0x14000c071  mov     edi, 0C000000Dh
0x14000c076  cmovnz  r8d, edi
0x14000c07a  mov     edi, r8d
0x14000c07d  test    r14, r14
0x14000c080  jz      short loc_14000C0EE
0x14000c082  mov     edx, 436F4752h; Tag
0x14000c087  mov     rcx, r14; P
0x14000c08a  call    cs:__imp_ExFreePoolWithTag
0x14000c091  nop     dword ptr [rax+rax+00h]
0x14000c096  jmp     short loc_14000C0EE
0x14000c098  mov     [rax+20h], ebx
0x14000c09b  mov     rax, [rsi+3F0h]
0x14000c0a2  mov     r8d, [rax+20h]
0x14000c0a6  lea     r9, [rax+18h]
0x14000c0aa  cmp     r8d, 4
0x14000c0ae  ja      short loc_14000C0B9
0x14000c0b0  add     rax, 24h ; '$'
0x14000c0b4  mov     [r9], rax
0x14000c0b7  jmp     short loc_14000C0D2
0x14000c0b9  mov     edx, 436F4752h
0x14000c0be  mov     ecx, 200h
0x14000c0c3  call    NfsMemMgrBufferAllocate
0x14000c0c8  mov     edi, eax
0x14000c0ca  test    eax, eax
0x14000c0cc  js      loc_14000BFCB
0x14000c0d2  mov     rdx, [rsi+3F0h]
0x14000c0d9  mov     rcx, rsi
0x14000c0dc  mov     r8, [rdx+18h]
0x14000c0e0  mov     edx, [rdx+20h]
0x14000c0e3  call    XdrDecodeOpaque
0x14000c0e8  mov     edi, [rsi+108h]
0x14000c0ee  test    edi, edi
0x14000c0f0  js      loc_14000BFCB
0x14000c0f6  mov     rcx, rsi
0x14000c0f9  call    XdrDecodeInt_0
0x14000c0fe  mov     rcx, rsi
0x14000c101  mov     r14d, eax
0x14000c104  call    XdrDecodeInt_0
0x14000c109  lea     r13, [rsi+20h]
0x14000c10d  mov     rcx, [r13+28h]
0x14000c111  test    rcx, rcx
0x14000c114  jnz     short loc_14000C11B
0x14000c116  xor     r15d, r15d
0x14000c119  jmp     short loc_14000C11F
0x14000c11b  mov     r15, [rcx+40h]
0x14000c11f  mov     rbx, [rsi+3F0h]
0x14000c126  mov     rcx, rsi
0x14000c129  call    XdrDecodeInt_0
0x14000c12e  mov     rcx, rsi
0x14000c131  mov     [rbx+48h], eax
0x14000c134  call    XdrDecodeInt_0
0x14000c139  mov     rcx, [rsi+48h]
0x14000c13d  mov     r12d, eax
0x14000c140  test    rcx, rcx
0x14000c143  jnz     short loc_14000C149
0x14000c145  xor     ebx, ebx
0x14000c147  jmp     short loc_14000C14D
0x14000c149  mov     rbx, [rcx+40h]
0x14000c14d  cmp     dword ptr [rsi+108h], 0
0x14000c154  jge     short loc_14000C160
0x14000c156  mov     edi, 80000005h
0x14000c15b  jmp     loc_14000BFCB
0x14000c160  mov     rcx, rsi
0x14000c163  call    XdrBytesLeft
0x14000c168  cmp     r12d, eax
0x14000c16b  ja      short loc_14000C156
0x14000c16d  xor     edx, edx
0x14000c16f  test    r14d, r14d
0x14000c172  jz      short loc_14000C184
0x14000c174  cmp     r14d, 1
0x14000c178  jz      short loc_14000C18D
0x14000c17a  mov     edi, 0C0000022h
0x14000c17f  jmp     loc_14000BFCB
0x14000c184  cmp     dword ptr [rsi+120h], 6
0x14000c18b  jmp     short loc_14000C178
0x14000c18d  mov     rcx, [rsi+3F0h]
0x14000c194  mov     r8d, 2
0x14000c19a  cmp     [rcx+38h], dl
0x14000c19d  jz      loc_14000C2CB
0x14000c1a3  xorps   xmm0, xmm0
0x14000c1a6  mov     dword ptr [rbp+57h+Buf1], edx
0x14000c1a9  xorps   xmm1, xmm1
0x14000c1ac  mov     eax, 10102h
0x14000c1b1  movups  xmmword ptr [rbp+57h+var_78.ulVersion], xmm0
0x14000c1b5  mov     r9d, 40010102h
0x14000c1bb  movups  xmmword ptr [rbp+57h+var_68.ulVersion], xmm1
0x14000c1bf  cmp     dword ptr [rcx+78h], 3
0x14000c1c3  cmovnz  r9d, eax
0x14000c1c7  cmp     cs:byte_14001AA22, dl
0x14000c1cd  jz      short loc_14000C1D4
0x14000c1cf  bts     r9d, 0Ah; fContextReq
0x14000c1d4  mov     [rbp+57h+var_68.ulVersion], edx
0x14000c1d7  lea     rax, [rbp+57h+var_58]
0x14000c1db  mov     [rbp+57h+var_68.pBuffers], rax
0x14000c1df  lea     rax, [rcx+28h]
0x14000c1e3  mov     [rbp+57h+var_78.pBuffers], rax
0x14000c1e7  mov     [rbp+57h+var_78.ulVersion], edx
0x14000c1ea  mov     [rbp+57h+var_54], r8d
0x14000c1ee  mov     [rbp+57h+var_58], r12d
0x14000c1f2  xor     r12d, r12d
0x14000c1f5  mov     [rbp+57h+var_68.cBuffers], 1
0x14000c1fc  mov     [rbp+57h+var_78.cBuffers], 1
0x14000c203  mov     [rbp+57h+var_50], rbx
0x14000c207  mov     [rcx+2Ch], r8d
0x14000c20b  mov     rax, [rsi+3F0h]
0x14000c212  mov     [rax+28h], r12d
0x14000c216  mov     rax, [rsi+3F0h]
0x14000c21d  mov     [rax+30h], r12
0x14000c221  mov     rcx, [rsi+3F0h]
0x14000c228  lea     rax, [rcx+70h]
0x14000c22c  mov     [rsp+0E0h+ptsExpiry], rax; ptsExpiry
0x14000c231  lea     rdx, [rcx+60h]; phContext
0x14000c235  lea     rax, [rbp+57h+Buf1]
0x14000c239  mov     [rsp+0E0h+pfContextAttr], rax; pfContextAttr
0x14000c23e  lea     r8, [rcx+0C0h]; pTargetName
0x14000c245  lea     rax, [rbp+57h+var_78]
0x14000c249  add     rcx, 50h ; 'P'; phCredential
0x14000c24d  mov     [rsp+0E0h+pOutput], rax; pOutput
0x14000c252  lea     rax, [rbp+57h+var_68]
0x14000c256  mov     [rsp+0E0h+phNewContext], rdx; phNewContext
0x14000c25b  mov     [rsp+0E0h+Reserved2], r12d; Reserved2
0x14000c260  mov     [rsp+0E0h+pInput], rax; pInput
0x14000c265  mov     [rsp+0E0h+TargetDataRep], 10h; TargetDataRep
0x14000c26d  mov     [rsp+0E0h+Reserved1], r12d; Reserved1
0x14000c272  call    cs:__imp_InitializeSecurityContextW
0x14000c279  nop     dword ptr [rax+rax+00h]
0x14000c27e  mov     ecx, eax
0x14000c280  call    OncRpcSeSecStatusToGssMajor
0x14000c285  mov     rbx, qword ptr [rbp+57h+pBuffer]
0x14000c289  mov     [rbx], eax
0x14000c28b  cmp     ecx, 90312h
0x14000c291  jz      short loc_14000C2AF
0x14000c293  test    ecx, ecx
0x14000c295  jz      short loc_14000C2AF
0x14000c297  call    cs:__imp_MapSecurityError
0x14000c29e  nop     dword ptr [rax+rax+00h]
0x14000c2a3  mov     edi, eax
0x14000c2a5  test    eax, eax
0x14000c2a7  js      loc_14000BFCB
0x14000c2ad  jmp     short loc_14000C2CF
0x14000c2af  mov     rax, [rsi+3F0h]
0x14000c2b6  or      dword ptr [rax+3Ch], 2
0x14000c2ba  test    ecx, ecx
0x14000c2bc  jnz     short loc_14000C2CF
0x14000c2be  mov     rax, [rsi+3F0h]
0x14000c2c5  mov     [rax+38h], r12b
0x14000c2c9  jmp     short loc_14000C2CF
0x14000c2cb  mov     rbx, qword ptr [rbp+57h+pBuffer]
0x14000c2cf  test    r14d, r14d
0x14000c2d2  jnz     loc_14000C40E
0x14000c2d8  mov     eax, [rsi+160h]
0x14000c2de  mov     r9, r15
0x14000c2e1  mov     rcx, [rsi+3F0h]
0x14000c2e8  xor     r8d, r8d
0x14000c2eb  mov     [rsp+0E0h+Reserved2], eax
0x14000c2ef  add     rcx, 60h ; '`'
0x14000c2f3  mov     rax, [rsi+168h]
0x14000c2fa  mov     rdx, rbx
0x14000c2fd  mov     [rsp+0E0h+pInput], rax
0x14000c302  mov     qword ptr [rsp+0E0h+TargetDataRep], r13
0x14000c307  mov     [rsp+0E0h+Reserved1], 4
0x14000c30f  call    OncRpcSepVerifyMessage
0x14000c314  mov     edi, eax
0x14000c316  test    eax, eax
0x14000c318  jns     short loc_14000C342
0x14000c31a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c321  lea     rbx, WPP_GLOBAL_Control
0x14000c328  cmp     rcx, rbx
0x14000c32b  jz      loc_14000BFD2
0x14000c331  mov     eax, [rcx+2Ch]
0x14000c334  test    al, 40h
0x14000c336  jz      loc_14000BFD2
0x14000c33c  lea     edx, [r14+35h]
0x14000c340  jmp     short loc_14000C3A8
0x14000c342  mov     rcx, [rsi+3F0h]
0x14000c349  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x14000c34d  xorps   xmm0, xmm0
0x14000c350  add     rcx, 60h ; '`'; phContext
0x14000c354  xor     edx, edx; ulAttribute
0x14000c356  movups  [rbp+57h+pBuffer], xmm0
0x14000c35a  call    cs:__imp_QueryContextAttributesW
0x14000c361  nop     dword ptr [rax+rax+00h]
0x14000c366  mov     ecx, eax
0x14000c368  call    OncRpcSeSecStatusToGssMajor
0x14000c36d  mov     [rbx], eax
0x14000c36f  call    cs:__imp_MapSecurityError
0x14000c376  nop     dword ptr [rax+rax+00h]
0x14000c37b  mov     edi, eax
0x14000c37d  test    eax, eax
0x14000c37f  jns     short loc_14000C3C0
0x14000c381  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c388  lea     rbx, WPP_GLOBAL_Control
0x14000c38f  cmp     rcx, rbx
0x14000c392  jz      loc_14000BFD2
0x14000c398  mov     eax, [rcx+2Ch]
0x14000c39b  test    al, 40h
0x14000c39d  jz      loc_14000BFD2
0x14000c3a3  mov     edx, 36h ; '6'
0x14000c3a8  mov     rcx, [rcx+18h]
0x14000c3ac  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c3b3  mov     r9d, edi
0x14000c3b6  call    WPP_SF_d
0x14000c3bb  jmp     loc_14000BFD2
0x14000c3c0  mov     rcx, [rsi+3F0h]
0x14000c3c7  mov     eax, dword ptr [rbp+57h+pBuffer+0Ch]
0x14000c3ca  mov     [rcx+0D0h], eax
0x14000c3d0  mov     rcx, [rsi+3F0h]
0x14000c3d7  mov     eax, dword ptr [rbp+57h+pBuffer+8]
0x14000c3da  mov     [rcx+0D4h], eax
0x14000c3e0  mov     rcx, [rsi+3F0h]
0x14000c3e7  mov     eax, dword ptr [rbp+57h+pBuffer]
0x14000c3ea  mov     [rcx+0D8h], eax
0x14000c3f0  mov     rcx, [rsi+3F0h]
0x14000c3f7  mov     eax, dword ptr [rbp+57h+pBuffer+4]
0x14000c3fa  mov     [rcx+0DCh], eax
0x14000c400  mov     rax, [rsi+3F0h]
0x14000c407  mov     dword ptr [rax+40h], 2
0x14000c40e  lea     rbx, WPP_GLOBAL_Control
0x14000c415  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c41c  cmp     rcx, rbx
0x14000c41f  jz      short loc_14000C440
0x14000c421  mov     eax, [rcx+2Ch]
0x14000c424  test    al, 1
0x14000c426  jz      short loc_14000C440
0x14000c428  mov     rcx, [rcx+18h]
0x14000c42c  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c433  mov     edx, 37h ; '7'
0x14000c438  mov     r9d, edi
0x14000c43b  call    WPP_SF_d
0x14000c440  mov     eax, edi
0x14000c442  mov     rcx, [rbp+57h+var_38]
0x14000c446  xor     rcx, rsp; StackCookie
0x14000c449  call    __security_check_cookie
0x14000c44e  mov     rbx, [rsp+0E0h+arg_10]
0x14000c456  add     rsp, 0B0h
0x14000c45d  pop     r15
0x14000c45f  pop     r14
0x14000c461  pop     r13
0x14000c463  pop     r12
0x14000c465  pop     rdi
  ... truncated ...
```
