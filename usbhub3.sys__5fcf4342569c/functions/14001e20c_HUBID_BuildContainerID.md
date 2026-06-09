# HUBID_BuildContainerID

- ea: `0x14001e20c`
- end: `0x14001e6c8`
- name: `HUBID_BuildContainerID`
- size: `1212`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14007ea48`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x14001e20c`
- `0x14001efa8`
- `0x140045530`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e63d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001e63d`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e5a3`
- `ntoskrnl!RtlStringFromGUID` at `0x14001e5a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e60f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e627`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e5f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e60f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e627`
- `ntoskrnl!ExAllocatePool2` at `0x14001e297`
- `ntoskrnl!ExAllocatePool2` at `0x14001e41c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e510`
- `ntoskrnl!ExAllocatePool2` at `0x14001e297`
- `ntoskrnl!ExAllocatePool2` at `0x14001e41c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e510`
- `ksecdd!BCryptDestroyHash` at `0x14001e5e1`
- `ksecdd!BCryptDestroyHash` at `0x14001e5e1`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001e654`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001e654`
- `ksecdd!BCryptFinishHash` at `0x14001e536`
- `ksecdd!BCryptFinishHash` at `0x14001e536`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001e3ad`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001e3ad`
- `ksecdd!BCryptHashData` at `0x14001e47a`
- `ksecdd!BCryptHashData` at `0x14001e4a0`
- `ksecdd!BCryptHashData` at `0x14001e47a`
- `ksecdd!BCryptHashData` at `0x14001e4a0`
- `ksecdd!BCryptCreateHash` at `0x14001e452`
- `ksecdd!BCryptCreateHash` at `0x14001e452`
- `ksecdd!BCryptGetProperty` at `0x14001e3eb`
- `ksecdd!BCryptGetProperty` at `0x14001e4d9`
- `ksecdd!BCryptGetProperty` at `0x14001e3eb`
- `ksecdd!BCryptGetProperty` at `0x14001e4d9`

## pseudocode

```c
void __fastcall HUBID_BuildContainerID(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v3; // r15
  NTSTATUS Property; // ebx
  UCHAR *v6; // r14
  UCHAR *v7; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r9
  unsigned __int16 v11; // cx
  char v12; // al
  NTSTATUS v13; // eax
  const wchar_t *v14; // rdx
  size_t v15; // r8
  UCHAR *Pool2; // rax
  UCHAR *v17; // rax
  const GUID *v18; // rcx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-25h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-21h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v25[8]; // [rsp+78h] [rbp+Fh] BYREF

  v2 = *(_DWORD *)(a1 + 1640);
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v3 = a2;
  phAlgorithm = 0;
  Property = 0;
  DestinationString = 0;
  GuidString = 0;
  if ( (v2 & 0x20) != 0 )
    goto LABEL_41;
  v6 = 0;
  v7 = 0;
  if ( (v2 & 0x78) != 0x40 )
  {
    v18 = (const GUID *)(a1 + 2072);
    goto LABEL_32;
  }
  v8 = *(_DWORD *)(a1 + 2156) + 28;
  DestinationString.Buffer = (wchar_t *)ExAllocatePool2(64, v8, 1681082453);
  if ( DestinationString.Buffer )
  {
    v9 = *(unsigned __int16 *)(a1 + 1998);
    v10 = *(unsigned __int16 *)(a1 + 2006);
    DestinationString.MaximumLength = v8;
    DestinationString.Length = 0;
    if ( (unsigned __int16)v9 > 0x200u )
    {
      v13 = RtlUnicodeStringPrintf(&DestinationString, L"%.4X%.4X.%4X", *(unsigned __int16 *)(a1 + 2004), v10, v9);
    }
    else
    {
      v11 = *(_WORD *)(a1 + 2008);
      v25[4] = 0;
      v25[0] = (v11 >> 12) + 48;
      v25[1] = (HIBYTE(v11) & 0xF) + 48;
      v12 = *(_BYTE *)(a1 + 2008) & 0xF;
      v25[2] = ((unsigned __int8)v11 >> 4) + 48;
      v25[3] = v12 + 48;
      v13 = RtlUnicodeStringPrintf(&DestinationString, L"%.4X%.4X%S", *(unsigned __int16 *)(a1 + 2004), v10, v25);
    }
    Property = v13;
    if ( v13 < 0 )
      goto LABEL_35;
    v14 = *(const wchar_t **)(a1 + 2160);
    if ( v14 )
    {
      if ( (*(_DWORD *)(a1 + 1644) & 0x800) != 0 )
        v14 += 6;
      v15 = *(unsigned int *)(a1 + 2156) - 14LL;
      if ( (*(_DWORD *)(a1 + 1644) & 0x800) == 0 )
        v15 = *(unsigned int *)(a1 + 2156);
      Property = RtlUnicodeStringCbCatStringN(&DestinationString, v14, v15);
      if ( Property < 0 )
        goto LABEL_35;
    }
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 1u);
    if ( Property < 0 )
    {
      phAlgorithm = 0;
      goto LABEL_35;
    }
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_35;
    if ( pcbResult != 4 )
    {
      Property = -1073741306;
      goto LABEL_35;
    }
    Pool2 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)pbOutput, 1681082453);
    v6 = Pool2;
    if ( Pool2 )
    {
      Property = BCryptCreateHash(phAlgorithm, &phHash, Pool2, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property < 0 )
        goto LABEL_35;
      Property = BCryptHashData(phHash, (PUCHAR)&pbInput, 0x10u, 0);
      if ( Property < 0 )
        goto LABEL_35;
      Property = BCryptHashData(phHash, (PUCHAR)DestinationString.Buffer, DestinationString.Length, 0);
      if ( Property < 0 )
        goto LABEL_35;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property < 0 )
        goto LABEL_35;
      if ( pcbResult != 4 || *(_DWORD *)pbOutput < 0x10u )
      {
        Property = -1073741811;
        goto LABEL_35;
      }
      v17 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)pbOutput, 1681082453);
      v7 = v17;
      if ( v17 )
      {
        Property = BCryptFinishHash(phHash, v17, *(ULONG *)pbOutput, 0);
        if ( Property < 0 )
          goto LABEL_35;
        v18 = (const GUID *)(a1 + 2072);
        LODWORD(a2) = 4095;
        *(_OWORD *)(a1 + 2072) = *(_OWORD *)v7;
        *(_WORD *)(a1 + 2078) = *(_WORD *)(a1 + 2078) & 0xFFF | 0x5000;
        *(_BYTE *)(a1 + 2080) = *(_BYTE *)(a1 + 2080) & 0x3F | 0x80;
        _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 8u);
LABEL_32:
        if ( (*(_DWORD *)(a1 + 1640) & 0x18) != 0 )
        {
          Property = RtlStringFromGUID(v18, &GuidString);
          if ( Property >= 0 )
            Property = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 3128))(
                         WdfDriverGlobals,
                         v3,
                         &GuidString);
        }
        goto LABEL_35;
      }
    }
  }
  Property = -1073741670;
LABEL_35:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x64334855u);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x64334855u);
LABEL_41:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x64334855u);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( Property < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      a2,
      5,
      12,
      (__int64)WPP_bdf3ab4397113be5813bb2cc4e6ee38f_Traceguids,
      Property);
  }
}

```

## disassembly

```asm
0x14001e20c  mov     [rsp-8+arg_10], rbx
0x14001e211  push    rbp
0x14001e212  push    rsi
0x14001e213  push    rdi
0x14001e214  push    r12
0x14001e216  push    r13
0x14001e218  push    r14
0x14001e21a  push    r15
0x14001e21c  lea     rbp, [rsp-27h]
0x14001e221  sub     rsp, 90h
0x14001e228  mov     rax, cs:__security_cookie
0x14001e22f  xor     rax, rsp
0x14001e232  mov     [rbp+57h+var_40], rax
0x14001e236  mov     eax, [rcx+668h]
0x14001e23c  xor     r12d, r12d
0x14001e23f  mov     [rbp+57h+phHash], r12
0x14001e243  xorps   xmm0, xmm0
0x14001e246  mov     dword ptr [rbp+57h+pbOutput], r12d
0x14001e24a  xorps   xmm1, xmm1
0x14001e24d  mov     [rbp+57h+var_7C], r12d
0x14001e251  mov     r15, rdx
0x14001e254  mov     [rbp+57h+phAlgorithm], r12
0x14001e258  mov     rdi, rcx
0x14001e25b  mov     ebx, r12d
0x14001e25e  mov     r13d, 64334855h
0x14001e264  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001e268  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x14001e26c  test    al, 20h
0x14001e26e  jnz     loc_14001E61B
0x14001e274  and     al, 78h
0x14001e276  mov     r14d, r12d
0x14001e279  mov     esi, r12d
0x14001e27c  cmp     al, 40h ; '@'
0x14001e27e  jnz     loc_14001E58E
0x14001e284  mov     ebx, [rcx+86Ch]
0x14001e28a  mov     r8d, r13d
0x14001e28d  add     ebx, 1Ch
0x14001e290  lea     ecx, [r12+40h]
0x14001e295  mov     edx, ebx
0x14001e297  call    cs:__imp_ExAllocatePool2
0x14001e29e  nop     dword ptr [rax+rax+00h]
0x14001e2a3  mov     [rbp+57h+DestinationString.Buffer], rax
0x14001e2a7  test    rax, rax
0x14001e2aa  jnz     short loc_14001E2B6
0x14001e2ac  mov     ebx, 0C000009Ah
0x14001e2b1  jmp     loc_14001E5D8
0x14001e2b6  movzx   eax, word ptr [rdi+7CEh]
0x14001e2bd  mov     ecx, 200h
0x14001e2c2  movzx   r9d, word ptr [rdi+7D6h]
0x14001e2ca  mov     [rbp+57h+DestinationString.MaximumLength], bx
0x14001e2ce  mov     [rbp+57h+DestinationString.Length], r12w
0x14001e2d3  cmp     ax, cx
0x14001e2d6  ja      short loc_14001E32F
0x14001e2d8  movzx   ecx, word ptr [rdi+7D8h]
0x14001e2df  mov     r8b, 30h ; '0'
0x14001e2e2  movzx   eax, cx
0x14001e2e5  mov     [rbp+57h+var_44], r12b
0x14001e2e9  shr     ax, 0Ch
0x14001e2ed  mov     dl, 0Fh
0x14001e2ef  add     al, r8b
0x14001e2f2  mov     [rbp+57h+var_48], al
0x14001e2f5  movzx   eax, cx
0x14001e2f8  shr     ax, 8
0x14001e2fc  and     al, dl
0x14001e2fe  shr     cl, 4
0x14001e301  add     al, r8b
0x14001e304  and     cl, dl
0x14001e306  mov     [rbp+57h+var_47], al
0x14001e309  add     cl, r8b
0x14001e30c  mov     al, [rdi+7D8h]
0x14001e312  and     al, dl
0x14001e314  mov     [rbp+57h+var_46], cl
0x14001e317  add     al, r8b
0x14001e31a  lea     rdx, a4x4xS; "%.4X%.4X%S"
0x14001e321  mov     [rbp+57h+var_45], al
0x14001e324  lea     rax, [rbp+57h+var_48]
0x14001e328  mov     [rsp+0C0h+pcbResult], rax
0x14001e32d  jmp     short loc_14001E33A
0x14001e32f  mov     dword ptr [rsp+0C0h+pcbResult], eax
0x14001e333  lea     rdx, a4x4x4x; "%.4X%.4X.%4X"
0x14001e33a  movzx   r8d, word ptr [rdi+7D4h]
0x14001e342  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e346  call    RtlUnicodeStringPrintf
0x14001e34b  mov     ebx, eax
0x14001e34d  test    eax, eax
0x14001e34f  js      loc_14001E5D8
0x14001e355  mov     rdx, [rdi+870h]
0x14001e35c  test    rdx, rdx
0x14001e35f  jz      short loc_14001E395
0x14001e361  mov     eax, [rdi+66Ch]
0x14001e367  mov     ecx, [rdi+86Ch]
0x14001e36d  and     eax, 800h
0x14001e372  jz      short loc_14001E378
0x14001e374  add     rdx, 0Ch; pszSrc
0x14001e378  lea     r8, [rcx-0Eh]
0x14001e37c  test    eax, eax
0x14001e37e  cmovz   r8, rcx; cbToAppend
0x14001e382  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001e386  call    RtlUnicodeStringCbCatStringN
0x14001e38b  mov     ebx, eax
0x14001e38d  test    eax, eax
0x14001e38f  js      loc_14001E5D8
0x14001e395  mov     r9d, 1; dwFlags
0x14001e39b  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14001e3a2  lea     rdx, pszAlgId; "SHA1"
0x14001e3a9  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x14001e3ad  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001e3b4  nop     dword ptr [rax+rax+00h]
0x14001e3b9  mov     ebx, eax
0x14001e3bb  test    eax, eax
0x14001e3bd  jns     short loc_14001E3C8
0x14001e3bf  mov     [rbp+57h+phAlgorithm], r12
0x14001e3c3  jmp     loc_14001E5D8
0x14001e3c8  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14001e3cc  lea     rax, [rbp+57h+var_7C]
0x14001e3d0  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x14001e3d5  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14001e3d9  mov     r9d, 4; cbOutput
0x14001e3df  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x14001e3e4  lea     rdx, pszProperty; "ObjectLength"
0x14001e3eb  call    cs:__imp_BCryptGetProperty
0x14001e3f2  nop     dword ptr [rax+rax+00h]
0x14001e3f7  mov     ebx, eax
0x14001e3f9  test    eax, eax
0x14001e3fb  js      loc_14001E5D8
0x14001e401  cmp     [rbp+57h+var_7C], 4
0x14001e405  jz      short loc_14001E411
0x14001e407  mov     ebx, 0C0000206h
0x14001e40c  jmp     loc_14001E5D8
0x14001e411  mov     edx, dword ptr [rbp+57h+pbOutput]
0x14001e414  mov     r8d, r13d
0x14001e417  mov     ecx, 40h ; '@'
0x14001e41c  call    cs:__imp_ExAllocatePool2
0x14001e423  nop     dword ptr [rax+rax+00h]
0x14001e428  mov     r14, rax
0x14001e42b  test    rax, rax
0x14001e42e  jz      loc_14001E2AC
0x14001e434  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x14001e438  lea     rdx, [rbp+57h+phHash]; phHash
0x14001e43c  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14001e440  mov     r8, rax; pbHashObject
0x14001e443  mov     [rsp+0C0h+var_90], r12d; dwFlags
0x14001e448  mov     [rsp+0C0h+dwFlags], r12d; cbSecret
0x14001e44d  mov     [rsp+0C0h+pcbResult], r12; pbSecret
0x14001e452  call    cs:__imp_BCryptCreateHash
0x14001e459  nop     dword ptr [rax+rax+00h]
0x14001e45e  mov     ebx, eax
0x14001e460  test    eax, eax
0x14001e462  js      loc_14001E5D8
0x14001e468  mov     rcx, [rbp+57h+phHash]; hHash
0x14001e46c  lea     rdx, pbInput; pbInput
0x14001e473  xor     r9d, r9d; dwFlags
0x14001e476  lea     r8d, [r9+10h]; cbInput
0x14001e47a  call    cs:__imp_BCryptHashData
0x14001e481  nop     dword ptr [rax+rax+00h]
0x14001e486  mov     ebx, eax
0x14001e488  test    eax, eax
0x14001e48a  js      loc_14001E5D8
0x14001e490  movzx   r8d, [rbp+57h+DestinationString.Length]; cbInput
0x14001e495  xor     r9d, r9d; dwFlags
0x14001e498  mov     rdx, [rbp+57h+DestinationString.Buffer]; pbInput
0x14001e49c  mov     rcx, [rbp+57h+phHash]; hHash
0x14001e4a0  call    cs:__imp_BCryptHashData
0x14001e4a7  nop     dword ptr [rax+rax+00h]
0x14001e4ac  mov     ebx, eax
0x14001e4ae  test    eax, eax
0x14001e4b0  js      loc_14001E5D8
0x14001e4b6  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x14001e4ba  lea     rax, [rbp+57h+var_7C]
0x14001e4be  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x14001e4c3  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14001e4c7  mov     r9d, 4; cbOutput
0x14001e4cd  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x14001e4d2  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14001e4d9  call    cs:__imp_BCryptGetProperty
0x14001e4e0  nop     dword ptr [rax+rax+00h]
0x14001e4e5  mov     ebx, eax
0x14001e4e7  test    eax, eax
0x14001e4e9  js      loc_14001E5D8
0x14001e4ef  cmp     [rbp+57h+var_7C], 4
0x14001e4f3  jz      short loc_14001E4FF
0x14001e4f5  mov     ebx, 0C000000Dh
0x14001e4fa  jmp     loc_14001E5D8
0x14001e4ff  cmp     dword ptr [rbp+57h+pbOutput], 10h
0x14001e503  jb      short loc_14001E4F5
0x14001e505  mov     edx, dword ptr [rbp+57h+pbOutput]
0x14001e508  mov     r8d, r13d
0x14001e50b  mov     ecx, 40h ; '@'
0x14001e510  call    cs:__imp_ExAllocatePool2
0x14001e517  nop     dword ptr [rax+rax+00h]
0x14001e51c  mov     rsi, rax
0x14001e51f  test    rax, rax
0x14001e522  jz      loc_14001E2AC
0x14001e528  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x14001e52c  xor     r9d, r9d; dwFlags
0x14001e52f  mov     rcx, [rbp+57h+phHash]; hHash
0x14001e533  mov     rdx, rax; pbOutput
0x14001e536  call    cs:__imp_BCryptFinishHash
0x14001e53d  nop     dword ptr [rax+rax+00h]
0x14001e542  mov     ebx, eax
0x14001e544  test    eax, eax
0x14001e546  js      loc_14001E5D8
0x14001e54c  movups  xmm0, xmmword ptr [rsi]
0x14001e54f  lea     rcx, [rdi+818h]
0x14001e556  mov     edx, 0FFFh
0x14001e55b  movdqu  xmmword ptr [rcx], xmm0
0x14001e55f  movzx   eax, word ptr [rdi+81Eh]
0x14001e566  and     ax, dx
0x14001e569  or      ax, 5000h
0x14001e56d  mov     [rdi+81Eh], ax
0x14001e574  mov     al, [rdi+820h]
0x14001e57a  and     al, 3Fh
0x14001e57c  or      al, 80h
0x14001e57e  mov     [rdi+820h], al
0x14001e584  lock or dword ptr [rdi+668h], 8
0x14001e58c  jmp     short loc_14001E595
0x14001e58e  add     rcx, 818h; Guid
0x14001e595  mov     eax, [rdi+668h]
0x14001e59b  test    al, 18h
0x14001e59d  jz      short loc_14001E5D8
0x14001e59f  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14001e5a3  call    cs:__imp_RtlStringFromGUID
0x14001e5aa  nop     dword ptr [rax+rax+00h]
0x14001e5af  mov     ebx, eax
0x14001e5b1  test    eax, eax
0x14001e5b3  js      short loc_14001E5D8
0x14001e5b5  mov     rax, cs:WdfFunctions_01015
0x14001e5bc  lea     r8, [rbp+57h+GuidString]
0x14001e5c0  mov     rcx, cs:WdfDriverGlobals
0x14001e5c7  mov     rdx, r15
0x14001e5ca  mov     rax, [rax+0C38h]
0x14001e5d1  call    _guard_dispatch_icall
0x14001e5d6  mov     ebx, eax
0x14001e5d8  mov     rcx, [rbp+57h+phHash]; hHash
0x14001e5dc  test    rcx, rcx
0x14001e5df  jz      short loc_14001E5ED
0x14001e5e1  call    cs:__imp_BCryptDestroyHash
0x14001e5e8  nop     dword ptr [rax+rax+00h]
0x14001e5ed  test    rsi, rsi
0x14001e5f0  jz      short loc_14001E604
0x14001e5f2  mov     edx, r13d; Tag
0x14001e5f5  mov     rcx, rsi; P
0x14001e5f8  call    cs:__imp_ExFreePoolWithTag
0x14001e5ff  nop     dword ptr [rax+rax+00h]
0x14001e604  test    r14, r14
0x14001e607  jz      short loc_14001E61B
0x14001e609  mov     edx, r13d; Tag
0x14001e60c  mov     rcx, r14; P
0x14001e60f  call    cs:__imp_ExFreePoolWithTag
0x14001e616  nop     dword ptr [rax+rax+00h]
0x14001e61b  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14001e61f  test    rcx, rcx
0x14001e622  jz      short loc_14001E633
0x14001e624  mov     edx, r13d; Tag
0x14001e627  call    cs:__imp_ExFreePoolWithTag
0x14001e62e  nop     dword ptr [rax+rax+00h]
0x14001e633  cmp     [rbp+57h+GuidString.Buffer], r12
0x14001e637  jz      short loc_14001E649
0x14001e639  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14001e63d  call    cs:__imp_RtlFreeUnicodeString
0x14001e644  nop     dword ptr [rax+rax+00h]
0x14001e649  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x14001e64d  test    rcx, rcx
0x14001e650  jz      short loc_14001E660
0x14001e652  xor     edx, edx; dwFlags
0x14001e654  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14001e65b  nop     dword ptr [rax+rax+00h]
0x14001e660  test    ebx, ebx
0x14001e662  jns     short loc_14001E6A0
0x14001e664  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001e66b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e672  jz      short loc_14001E6A0
0x14001e674  mov     rcx, [rdi+8]
0x14001e678  lea     rax, WPP_bdf3ab4397113be5813bb2cc4e6ee38f_Traceguids
0x14001e67f  mov     r9d, 0Ch
0x14001e685  mov     [rsp+0C0h+dwFlags], ebx
0x14001e689  mov     dl, 2
0x14001e68b  mov     [rsp+0C0h+pcbResult], rax
0x14001e690  mov     rcx, [rcx+598h]
0x14001e697  lea     r8d, [r9-7]
0x14001e69b  call    WPP_RECORDER_SF_d
0x14001e6a0  mov     rcx, [rbp+57h+var_40]
0x14001e6a4  xor     rcx, rsp; StackCookie
0x14001e6a7  call    __security_check_cookie
0x14001e6ac  mov     rbx, [rsp+0C0h+arg_10]
0x14001e6b4  add     rsp, 90h
0x14001e6bb  pop     r15
0x14001e6bd  pop     r14
0x14001e6bf  pop     r13
0x14001e6c1  pop     r12
0x14001e6c3  pop     rdi
0x14001e6c4  pop     rsi
0x14001e6c5  pop     rbp
0x14001e6c6  retn
```
