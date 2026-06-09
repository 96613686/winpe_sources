# NvmeFabricControllerQueueComputeHostResponse

- ea: `0x140117a0c`
- end: `0x140117e25`
- name: `NvmeFabricControllerQueueComputeHostResponse`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401184e8`

## callees

- `0x14005285c`
- `0x140117a0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140117de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140117de4`
- `ntoskrnl!ExAllocatePool2` at `0x140117af6`
- `ntoskrnl!ExAllocatePool2` at `0x140117af6`
- `ksecdd!BCryptCreateHash` at `0x140117b90`
- `ksecdd!BCryptCreateHash` at `0x140117b90`
- `ksecdd!BCryptHashData` at `0x140117bb4`
- `ksecdd!BCryptHashData` at `0x140117bdd`
- `ksecdd!BCryptHashData` at `0x140117c02`
- `ksecdd!BCryptHashData` at `0x140117c2b`
- `ksecdd!BCryptHashData` at `0x140117c53`
- `ksecdd!BCryptHashData` at `0x140117c8c`
- `ksecdd!BCryptHashData` at `0x140117cad`
- `ksecdd!BCryptHashData` at `0x140117cd7`
- `ksecdd!BCryptHashData` at `0x140117bb4`
- `ksecdd!BCryptHashData` at `0x140117bdd`
- `ksecdd!BCryptHashData` at `0x140117c02`
- `ksecdd!BCryptHashData` at `0x140117c2b`
- `ksecdd!BCryptHashData` at `0x140117c53`
- `ksecdd!BCryptHashData` at `0x140117c8c`
- `ksecdd!BCryptHashData` at `0x140117cad`
- `ksecdd!BCryptHashData` at `0x140117cd7`
- `ksecdd!BCryptDestroyHash` at `0x140117dcb`
- `ksecdd!BCryptDestroyHash` at `0x140117dcb`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140117dfb`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140117dfb`
- `ksecdd!BCryptFinishHash` at `0x140117cf8`
- `ksecdd!BCryptFinishHash` at `0x140117cf8`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140117a9a`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140117a9a`
- `ksecdd!BCryptGetProperty` at `0x140117ad2`
- `ksecdd!BCryptGetProperty` at `0x140117b3a`
- `ksecdd!BCryptGetProperty` at `0x140117ad2`
- `ksecdd!BCryptGetProperty` at `0x140117b3a`

## string_xrefs

- `0x140117d9a`: `Computing host response failed`

## pseudocode

```c
__int64 __fastcall NvmeFabricControllerQueueComputeHostResponse(__int64 a1, unsigned __int16 a2, UCHAR *a3, UCHAR *a4)
{
  __int64 v4; // r13
  UCHAR *Pool2; // rsi
  __int64 v8; // r12
  int v9; // edi
  char v10; // cl
  const WCHAR *v11; // rdx
  NTSTATUS Property; // ebx
  UCHAR *v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // r8
  UCHAR *v16; // rdx
  UCHAR v18[4]; // [rsp+A0h] [rbp+7h] BYREF
  UCHAR pbOutput[4]; // [rsp+A4h] [rbp+Bh] BYREF
  ULONG pcbResult; // [rsp+A8h] [rbp+Fh] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+B0h] [rbp+17h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+B8h] [rbp+1Fh] BYREF
  UCHAR pbInput; // [rsp+100h] [rbp+67h] BYREF
  PUCHAR v24; // [rsp+118h] [rbp+7Fh]

  v24 = a4;
  v4 = *(_QWORD *)(a1 + 88);
  phAlgorithm = 0;
  Pool2 = 0;
  phHash = 0;
  *(_DWORD *)v18 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  pbInput = 0;
  v8 = *(_QWORD *)(v4 + 96);
  v9 = a2;
  v10 = *(_BYTE *)(*(_QWORD *)(a1 + 96) + 3LL);
  switch ( v10 )
  {
    case 1:
      v11 = L"SHA256";
      break;
    case 2:
      v11 = L"SHA384";
      break;
    case 3:
      v11 = L"SHA512";
      break;
    default:
      Property = -1073741811;
      goto LABEL_30;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v11, L"Microsoft Primitive Provider", 8u);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1095655762);
  if ( !Pool2 )
  {
    Property = -1073741801;
LABEL_30:
    StorEtwNvmeControllerEvent(
      v4,
      1,
      2,
      (unsigned int)L"Computing host response failed",
      (__int64)L"Status",
      Property,
      (__int64)L"HashID",
      *(_BYTE *)(*(_QWORD *)(a1 + 96) + 3LL),
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0,
      (__int64)&word_140155F3C,
      0);
    goto LABEL_31;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v18, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_30;
  if ( *(_DWORD *)v18 != v9 )
  {
    Property = -1073741820;
    goto LABEL_30;
  }
  Property = BCryptCreateHash(
               phAlgorithm,
               &phHash,
               Pool2,
               *(ULONG *)pbOutput,
               (PUCHAR)(*(_QWORD *)(v4 + 1664) + 532LL),
               *(unsigned __int16 *)(*(_QWORD *)(v4 + 1664) + 14LL),
               0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, a3, *(ULONG *)v18, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)(*(_QWORD *)(a1 + 96) + 8LL), 4u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, *(PUCHAR *)(a1 + 96), 2u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)(*(_QWORD *)(a1 + 96) + 2LL), 1u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, (PUCHAR)"HostHost", 8u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  v13 = (UCHAR *)(*(_QWORD *)(v4 + 1664) + 20LL);
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( v13[v15] );
  Property = BCryptHashData(phHash, v13, v15, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptHashData(phHash, &pbInput, 1u, 0);
  if ( Property < 0 )
    goto LABEL_30;
  v16 = (UCHAR *)(v8 + 60);
  do
    ++v14;
  while ( v16[v14] );
  Property = BCryptHashData(phHash, v16, v14, 0);
  if ( Property < 0 )
    goto LABEL_30;
  Property = BCryptFinishHash(phHash, v24, *(ULONG *)v18, 0);
  if ( Property < 0 )
    goto LABEL_30;
LABEL_31:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x414E6152u);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x140117a0c  mov     [rsp-8+arg_8], rbx
0x140117a11  mov     [rsp-8+arg_18], r9
0x140117a16  push    rbp
0x140117a17  push    rsi
0x140117a18  push    rdi
0x140117a19  push    r12
0x140117a1b  push    r13
0x140117a1d  push    r14
0x140117a1f  push    r15
0x140117a21  lea     rbp, [rsp-27h]
0x140117a26  sub     rsp, 0C0h
0x140117a2d  mov     r13, [rcx+58h]
0x140117a31  xor     eax, eax
0x140117a33  mov     [rbp+57h+phAlgorithm], rax
0x140117a37  mov     esi, eax
0x140117a39  mov     [rbp+57h+phHash], rax
0x140117a3d  mov     r14, rcx
0x140117a40  mov     dword ptr [rbp+57h+var_50], eax
0x140117a43  mov     r15, r8
0x140117a46  mov     dword ptr [rbp+57h+pbOutput], eax
0x140117a49  mov     [rbp+57h+var_48], eax
0x140117a4c  mov     [rbp+57h+pbInput], al
0x140117a4f  mov     rax, [rcx+60h]
0x140117a53  mov     r12, [r13+60h]
0x140117a57  movzx   edi, dx
0x140117a5a  mov     cl, [rax+3]
0x140117a5d  cmp     cl, 1
0x140117a60  jnz     short loc_140117A6B
0x140117a62  lea     rdx, aSha256; "SHA256"
0x140117a69  jmp     short loc_140117A89
0x140117a6b  cmp     cl, 2
0x140117a6e  jnz     short loc_140117A79
0x140117a70  lea     rdx, aSha384; "SHA384"
0x140117a77  jmp     short loc_140117A89
0x140117a79  cmp     cl, 3
0x140117a7c  jnz     loc_140117D10
0x140117a82  lea     rdx, pszAlgId; "SHA512"
0x140117a89  mov     r9d, 8; dwFlags
0x140117a8f  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140117a96  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x140117a9a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140117aa1  nop     dword ptr [rax+rax+00h]
0x140117aa6  mov     ebx, eax
0x140117aa8  test    eax, eax
0x140117aaa  js      loc_140117D15
0x140117ab0  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x140117ab4  lea     rax, [rbp+57h+var_48]
0x140117ab8  mov     [rsp+0F0h+dwFlags], esi; dwFlags
0x140117abc  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x140117ac0  mov     r9d, 4; cbOutput
0x140117ac6  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x140117acb  lea     rdx, pszProperty; "ObjectLength"
0x140117ad2  call    cs:__imp_BCryptGetProperty
0x140117ad9  nop     dword ptr [rax+rax+00h]
0x140117ade  mov     ebx, eax
0x140117ae0  test    eax, eax
0x140117ae2  js      loc_140117D15
0x140117ae8  mov     edx, dword ptr [rbp+57h+pbOutput]
0x140117aeb  mov     ecx, 100h
0x140117af0  mov     r8d, 414E6152h
0x140117af6  call    cs:__imp_ExAllocatePool2
0x140117afd  nop     dword ptr [rax+rax+00h]
0x140117b02  mov     rsi, rax
0x140117b05  test    rax, rax
0x140117b08  jnz     short loc_140117B14
0x140117b0a  mov     ebx, 0C0000017h
0x140117b0f  jmp     loc_140117D15
0x140117b14  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x140117b18  lea     rax, [rbp+57h+var_48]
0x140117b1c  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x140117b24  lea     r8, [rbp+57h+var_50]; pbOutput
0x140117b28  mov     r9d, 4; cbOutput
0x140117b2e  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x140117b33  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140117b3a  call    cs:__imp_BCryptGetProperty
0x140117b41  nop     dword ptr [rax+rax+00h]
0x140117b46  mov     ebx, eax
0x140117b48  test    eax, eax
0x140117b4a  js      loc_140117D15
0x140117b50  cmp     dword ptr [rbp+57h+var_50], edi
0x140117b53  jz      short loc_140117B5F
0x140117b55  mov     ebx, 0C0000004h
0x140117b5a  jmp     loc_140117D15
0x140117b5f  mov     rax, [r13+680h]
0x140117b66  lea     rdx, [rbp+57h+phHash]; phHash
0x140117b6a  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x140117b6e  mov     r8, rsi; pbHashObject
0x140117b71  mov     [rsp+0F0h+var_C0], 0; dwFlags
0x140117b79  movzx   ecx, word ptr [rax+0Eh]
0x140117b7d  add     rax, 214h
0x140117b83  mov     [rsp+0F0h+dwFlags], ecx; cbSecret
0x140117b87  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x140117b8b  mov     [rsp+0F0h+pcbResult], rax; pbSecret
0x140117b90  call    cs:__imp_BCryptCreateHash
0x140117b97  nop     dword ptr [rax+rax+00h]
0x140117b9c  mov     ebx, eax
0x140117b9e  test    eax, eax
0x140117ba0  js      loc_140117D15
0x140117ba6  mov     r8d, dword ptr [rbp+57h+var_50]; cbInput
0x140117baa  xor     r9d, r9d; dwFlags
0x140117bad  mov     rcx, [rbp+57h+phHash]; hHash
0x140117bb1  mov     rdx, r15; pbInput
0x140117bb4  call    cs:__imp_BCryptHashData
0x140117bbb  nop     dword ptr [rax+rax+00h]
0x140117bc0  mov     ebx, eax
0x140117bc2  test    eax, eax
0x140117bc4  js      loc_140117D15
0x140117bca  mov     rdx, [r14+60h]
0x140117bce  xor     r9d, r9d; dwFlags
0x140117bd1  mov     rcx, [rbp+57h+phHash]; hHash
0x140117bd5  add     rdx, 8; pbInput
0x140117bd9  lea     r8d, [r9+4]; cbInput
0x140117bdd  call    cs:__imp_BCryptHashData
0x140117be4  nop     dword ptr [rax+rax+00h]
0x140117be9  mov     ebx, eax
0x140117beb  test    eax, eax
0x140117bed  js      loc_140117D15
0x140117bf3  mov     rdx, [r14+60h]; pbInput
0x140117bf7  xor     r9d, r9d; dwFlags
0x140117bfa  mov     rcx, [rbp+57h+phHash]; hHash
0x140117bfe  lea     r8d, [r9+2]; cbInput
0x140117c02  call    cs:__imp_BCryptHashData
0x140117c09  nop     dword ptr [rax+rax+00h]
0x140117c0e  mov     ebx, eax
0x140117c10  test    eax, eax
0x140117c12  js      loc_140117D15
0x140117c18  mov     rdx, [r14+60h]
0x140117c1c  xor     r9d, r9d; dwFlags
0x140117c1f  mov     rcx, [rbp+57h+phHash]; hHash
0x140117c23  add     rdx, 2; pbInput
0x140117c27  lea     r8d, [r9+1]; cbInput
0x140117c2b  call    cs:__imp_BCryptHashData
0x140117c32  nop     dword ptr [rax+rax+00h]
0x140117c37  mov     ebx, eax
0x140117c39  test    eax, eax
0x140117c3b  js      loc_140117D15
0x140117c41  mov     rcx, [rbp+57h+phHash]; hHash
0x140117c45  lea     rdx, aHosthost; "HostHost"
0x140117c4c  xor     r9d, r9d; dwFlags
0x140117c4f  lea     r8d, [r9+8]; cbInput
0x140117c53  call    cs:__imp_BCryptHashData
0x140117c5a  nop     dword ptr [rax+rax+00h]
0x140117c5f  mov     ebx, eax
0x140117c61  test    eax, eax
0x140117c63  js      loc_140117D15
0x140117c69  mov     rdx, [r13+680h]
0x140117c70  add     rdx, 14h; pbInput
0x140117c74  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140117c78  mov     r8, rdi
0x140117c7b  inc     r8; cbInput
0x140117c7e  cmp     byte ptr [rdx+r8], 0
0x140117c83  jnz     short loc_140117C7B
0x140117c85  mov     rcx, [rbp+57h+phHash]; hHash
0x140117c89  xor     r9d, r9d; dwFlags
0x140117c8c  call    cs:__imp_BCryptHashData
0x140117c93  nop     dword ptr [rax+rax+00h]
0x140117c98  mov     ebx, eax
0x140117c9a  test    eax, eax
0x140117c9c  js      short loc_140117D15
0x140117c9e  mov     rcx, [rbp+57h+phHash]; hHash
0x140117ca2  lea     rdx, [rbp+57h+pbInput]; pbInput
0x140117ca6  xor     r9d, r9d; dwFlags
0x140117ca9  lea     r8d, [r9+1]; cbInput
0x140117cad  call    cs:__imp_BCryptHashData
0x140117cb4  nop     dword ptr [rax+rax+00h]
0x140117cb9  mov     ebx, eax
0x140117cbb  test    eax, eax
0x140117cbd  js      short loc_140117D15
0x140117cbf  lea     rdx, [r12+3Ch]; pbInput
0x140117cc4  inc     rdi
0x140117cc7  cmp     byte ptr [rdx+rdi], 0
0x140117ccb  jnz     short loc_140117CC4
0x140117ccd  mov     rcx, [rbp+57h+phHash]; hHash
0x140117cd1  xor     r9d, r9d; dwFlags
0x140117cd4  mov     r8d, edi; cbInput
0x140117cd7  call    cs:__imp_BCryptHashData
0x140117cde  nop     dword ptr [rax+rax+00h]
0x140117ce3  mov     ebx, eax
0x140117ce5  test    eax, eax
0x140117ce7  js      short loc_140117D15
0x140117ce9  mov     r8d, dword ptr [rbp+57h+var_50]; cbOutput
0x140117ced  xor     r9d, r9d; dwFlags
0x140117cf0  mov     rdx, [rbp+57h+arg_18]; pbOutput
0x140117cf4  mov     rcx, [rbp+57h+phHash]; hHash
0x140117cf8  call    cs:__imp_BCryptFinishHash
0x140117cff  nop     dword ptr [rax+rax+00h]
0x140117d04  mov     ebx, eax
0x140117d06  test    eax, eax
0x140117d08  jns     loc_140117DC2
0x140117d0e  jmp     short loc_140117D15
0x140117d10  mov     ebx, 0C000000Dh
0x140117d15  mov     rax, [r14+60h]
0x140117d19  lea     rcx, word_140155F3C
0x140117d20  mov     [rsp+0F0h+var_58], 0
0x140117d2c  mov     edx, 1
0x140117d31  mov     [rsp+0F0h+var_60], rcx
0x140117d39  mov     [rsp+0F0h+var_68], 0
0x140117d45  movzx   r9d, byte ptr [rax+3]
0x140117d4a  mov     [rsp+0F0h+var_70], rcx
0x140117d52  lea     r8d, [rdx+1]
0x140117d56  mov     [rsp+0F0h+var_78], 0
0x140117d5f  mov     [rsp+0F0h+var_80], rcx
0x140117d64  mov     [rsp+0F0h+var_88], 0
0x140117d6d  mov     [rsp+0F0h+var_90], rcx
0x140117d72  mov     [rsp+0F0h+var_98], 0
0x140117d7b  mov     [rsp+0F0h+var_A0], rcx
0x140117d80  mov     [rsp+0F0h+var_A8], 0
0x140117d89  mov     [rsp+0F0h+var_B0], rcx
0x140117d8e  lea     rcx, aHashid; "HashID"
0x140117d95  mov     [rsp+0F0h+var_B8], r9
0x140117d9a  lea     r9, aComputingHostR; "Computing host response failed"
0x140117da1  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x140117da6  mov     rcx, r13
0x140117da9  movsxd  rax, ebx
0x140117dac  mov     qword ptr [rsp+0F0h+dwFlags], rax
0x140117db1  lea     rax, aStatus; "Status"
0x140117db8  mov     [rsp+0F0h+pcbResult], rax
0x140117dbd  call    StorEtwNvmeControllerEvent
0x140117dc2  mov     rcx, [rbp+57h+phHash]; hHash
0x140117dc6  test    rcx, rcx
0x140117dc9  jz      short loc_140117DD7
0x140117dcb  call    cs:__imp_BCryptDestroyHash
0x140117dd2  nop     dword ptr [rax+rax+00h]
0x140117dd7  test    rsi, rsi
0x140117dda  jz      short loc_140117DF0
0x140117ddc  mov     edx, 414E6152h; Tag
0x140117de1  mov     rcx, rsi; P
0x140117de4  call    cs:__imp_ExFreePoolWithTag
0x140117deb  nop     dword ptr [rax+rax+00h]
0x140117df0  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x140117df4  test    rcx, rcx
0x140117df7  jz      short loc_140117E07
0x140117df9  xor     edx, edx; dwFlags
0x140117dfb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140117e02  nop     dword ptr [rax+rax+00h]
0x140117e07  mov     eax, ebx
0x140117e09  mov     rbx, [rsp+0F0h+arg_8]
0x140117e11  add     rsp, 0C0h
0x140117e18  pop     r15
0x140117e1a  pop     r14
0x140117e1c  pop     r13
0x140117e1e  pop     r12
0x140117e20  pop     rdi
0x140117e21  pop     rsi
0x140117e22  pop     rbp
0x140117e23  retn
```
