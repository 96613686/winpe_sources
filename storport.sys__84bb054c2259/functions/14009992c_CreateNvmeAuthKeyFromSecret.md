# CreateNvmeAuthKeyFromSecret

- ea: `0x14009992c`
- end: `0x140099bd3`
- name: `CreateNvmeAuthKeyFromSecret`
- size: `679`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, __int64, PUCHAR)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401a2b28`

## callees

- `0x14009992c`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140099b9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099b9c`
- `ntoskrnl!ExAllocatePool2` at `0x140099a3c`
- `ntoskrnl!ExAllocatePool2` at `0x140099a3c`
- `ksecdd!BCryptCreateHash` at `0x140099aeb`
- `ksecdd!BCryptCreateHash` at `0x140099aeb`
- `ksecdd!BCryptHashData` at `0x140099b14`
- `ksecdd!BCryptHashData` at `0x140099b38`
- `ksecdd!BCryptHashData` at `0x140099b14`
- `ksecdd!BCryptHashData` at `0x140099b38`
- `ksecdd!BCryptDestroyHash` at `0x140099b83`
- `ksecdd!BCryptDestroyHash` at `0x140099b83`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140099bb3`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140099bb3`
- `ksecdd!BCryptFinishHash` at `0x140099b59`
- `ksecdd!BCryptFinishHash` at `0x140099b59`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400999dc`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400999dc`
- `ksecdd!BCryptGetProperty` at `0x140099a18`
- `ksecdd!BCryptGetProperty` at `0x140099a80`
- `ksecdd!BCryptGetProperty` at `0x140099a18`
- `ksecdd!BCryptGetProperty` at `0x140099a80`

## pseudocode

```c
__int64 __fastcall CreateNvmeAuthKeyFromSecret(
        PUCHAR pbInput,
        unsigned __int16 a2,
        void *a3,
        unsigned __int16 a4,
        _WORD *a5,
        PUCHAR a6)
{
  _WORD *v6; // r15
  int v8; // edi
  ULONG v10; // r14d
  unsigned __int16 v11; // cx
  NTSTATUS Property; // ebx
  size_t v13; // r8
  PUCHAR v14; // rcx
  UCHAR *Pool2; // rsi
  const WCHAR *v16; // rdx
  int v17; // edx
  __int64 v18; // r8
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  ULONG v24; // [rsp+C8h] [rbp+60h] BYREF

  v6 = a5;
  v8 = a4;
  v10 = a2;
  phAlgorithm = 0;
  *a5 = 0;
  phHash = 0;
  v24 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( !a4 )
  {
    v11 = 256;
    Property = 0;
    if ( a2 < 0x100u )
      v11 = a2;
    v13 = v11;
    v14 = a6;
    *v6 = v13;
    memmove(v14, a3, v13);
    return (unsigned int)Property;
  }
  Pool2 = 0;
  switch ( a4 )
  {
    case 1u:
      v16 = L"SHA256";
LABEL_11:
      Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v16, L"Microsoft Primitive Provider", 8u);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1095655762);
          if ( Pool2 )
          {
            Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&v24, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( v8 == 1 )
              {
                v17 = 32;
              }
              else if ( v8 == 2 )
              {
                v17 = 48;
              }
              else
              {
                v17 = 64;
              }
              if ( v24 == v17 )
              {
                Property = BCryptCreateHash(phAlgorithm, &phHash, Pool2, *(ULONG *)pbOutput, (PUCHAR)a3, v10, 0);
                if ( Property >= 0 )
                {
                  v18 = -1;
                  do
                    ++v18;
                  while ( pbInput[v18] );
                  Property = BCryptHashData(phHash, pbInput, v18, 0);
                  if ( Property >= 0 )
                  {
                    Property = BCryptHashData(phHash, (PUCHAR)"NVMe-over-Fabrics", 0x11u, 0);
                    if ( Property >= 0 )
                    {
                      Property = BCryptFinishHash(phHash, a6, v24, 0);
                      if ( Property >= 0 )
                        *v6 = v24;
                    }
                  }
                }
              }
              else
              {
                Property = -1073741820;
              }
            }
          }
          else
          {
            Property = -1073741801;
          }
        }
      }
      goto LABEL_31;
    case 2u:
      v16 = L"SHA384";
      goto LABEL_11;
    case 3u:
      v16 = L"SHA512";
      goto LABEL_11;
  }
  Property = -1073741811;
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
0x14009992c  push    rbp
0x14009992e  push    rbx
0x14009992f  push    rsi
0x140099930  push    rdi
0x140099931  push    r12
0x140099933  push    r13
0x140099935  push    r14
0x140099937  push    r15
0x140099939  mov     rbp, rsp
0x14009993c  sub     rsp, 68h
0x140099940  mov     r15, [rbp+arg_20]
0x140099944  mov     r12, r8
0x140099947  movzx   edi, r9w
0x14009994b  mov     r13, rcx
0x14009994e  xor     r9d, r9d
0x140099951  movzx   r14d, dx
0x140099955  mov     [rbp+phAlgorithm], r9
0x140099959  mov     [r15], r9w
0x14009995d  mov     [rbp+phHash], r9
0x140099961  mov     [rbp+arg_18], r9d
0x140099965  mov     dword ptr [rbp+pbOutput], r9d
0x140099969  mov     [rbp+var_24], r9d
0x14009996d  test    di, di
0x140099970  jnz     short loc_14009999C
0x140099972  mov     ecx, 100h
0x140099977  mov     ebx, r9d
0x14009997a  cmp     r14w, cx
0x14009997e  jnb     short loc_140099983
0x140099980  mov     ecx, r14d
0x140099983  movzx   r8d, cx; Size
0x140099987  mov     rdx, r12; Src
0x14009998a  mov     rcx, [rbp+arg_28]; void *
0x14009998e  mov     [r15], r8w
0x140099992  call    memmove
0x140099997  jmp     loc_140099BBF
0x14009999c  mov     rsi, r9
0x14009999f  cmp     edi, 1
0x1400999a2  jnz     short loc_1400999AD
0x1400999a4  lea     rdx, aSha256; "SHA256"
0x1400999ab  jmp     short loc_1400999CB
0x1400999ad  cmp     edi, 2
0x1400999b0  jnz     short loc_1400999BB
0x1400999b2  lea     rdx, aSha384; "SHA384"
0x1400999b9  jmp     short loc_1400999CB
0x1400999bb  cmp     edi, 3
0x1400999be  jnz     loc_140099B75
0x1400999c4  lea     rdx, pszAlgId; "SHA512"
0x1400999cb  mov     r9d, 8; dwFlags
0x1400999d1  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1400999d8  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1400999dc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400999e3  nop     dword ptr [rax+rax+00h]
0x1400999e8  xor     r9d, r9d
0x1400999eb  mov     ebx, eax
0x1400999ed  test    eax, eax
0x1400999ef  js      loc_140099B7A
0x1400999f5  mov     rcx, [rbp+phAlgorithm]; hObject
0x1400999f9  lea     rax, [rbp+var_24]
0x1400999fd  mov     [rsp+68h+dwFlags], r9d; dwFlags
0x140099a02  lea     r8, [rbp+pbOutput]; pbOutput
0x140099a06  mov     r9d, 4; cbOutput
0x140099a0c  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140099a11  lea     rdx, pszProperty; "ObjectLength"
0x140099a18  call    cs:__imp_BCryptGetProperty
0x140099a1f  nop     dword ptr [rax+rax+00h]
0x140099a24  mov     ebx, eax
0x140099a26  test    eax, eax
0x140099a28  js      loc_140099B7A
0x140099a2e  mov     edx, dword ptr [rbp+pbOutput]
0x140099a31  mov     ecx, 100h
0x140099a36  mov     r8d, 414E6152h
0x140099a3c  call    cs:__imp_ExAllocatePool2
0x140099a43  nop     dword ptr [rax+rax+00h]
0x140099a48  xor     r9d, r9d
0x140099a4b  mov     rsi, rax
0x140099a4e  test    rax, rax
0x140099a51  jnz     short loc_140099A5D
0x140099a53  mov     ebx, 0C0000017h
0x140099a58  jmp     loc_140099B7A
0x140099a5d  mov     rcx, [rbp+phAlgorithm]; hObject
0x140099a61  lea     rax, [rbp+var_24]
0x140099a65  mov     [rsp+68h+dwFlags], r9d; dwFlags
0x140099a6a  lea     r8, [rbp+arg_18]; pbOutput
0x140099a6e  mov     r9d, 4; cbOutput
0x140099a74  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140099a79  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140099a80  call    cs:__imp_BCryptGetProperty
0x140099a87  nop     dword ptr [rax+rax+00h]
0x140099a8c  xor     r9d, r9d
0x140099a8f  mov     ebx, eax
0x140099a91  test    eax, eax
0x140099a93  js      loc_140099B7A
0x140099a99  mov     ecx, edi
0x140099a9b  mov     edx, r9d
0x140099a9e  sub     ecx, 1
0x140099aa1  jz      short loc_140099AB9
0x140099aa3  sub     ecx, 1
0x140099aa6  jz      short loc_140099AB2
0x140099aa8  cmp     ecx, 1
0x140099aab  jnz     short loc_140099ABE
0x140099aad  lea     edx, [rcx+3Fh]
0x140099ab0  jmp     short loc_140099ABE
0x140099ab2  mov     edx, 30h ; '0'
0x140099ab7  jmp     short loc_140099ABE
0x140099ab9  mov     edx, 20h ; ' '
0x140099abe  cmp     [rbp+arg_18], edx
0x140099ac1  jz      short loc_140099ACD
0x140099ac3  mov     ebx, 0C0000004h
0x140099ac8  jmp     loc_140099B7A
0x140099acd  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140099ad1  lea     rdx, [rbp+phHash]; phHash
0x140099ad5  mov     [rsp+68h+var_38], r9d; dwFlags
0x140099ada  mov     r8, rsi; pbHashObject
0x140099add  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x140099ae1  mov     [rsp+68h+dwFlags], r14d; cbSecret
0x140099ae6  mov     [rsp+68h+pcbResult], r12; pbSecret
0x140099aeb  call    cs:__imp_BCryptCreateHash
0x140099af2  nop     dword ptr [rax+rax+00h]
0x140099af7  xor     r9d, r9d; dwFlags
0x140099afa  mov     ebx, eax
0x140099afc  test    eax, eax
0x140099afe  js      short loc_140099B7A
0x140099b00  or      r8, 0FFFFFFFFFFFFFFFFh
0x140099b04  inc     r8; cbInput
0x140099b07  cmp     [r8+r13], r9b
0x140099b0b  jnz     short loc_140099B04
0x140099b0d  mov     rcx, [rbp+phHash]; hHash
0x140099b11  mov     rdx, r13; pbInput
0x140099b14  call    cs:__imp_BCryptHashData
0x140099b1b  nop     dword ptr [rax+rax+00h]
0x140099b20  xor     r9d, r9d; dwFlags
0x140099b23  mov     ebx, eax
0x140099b25  test    eax, eax
0x140099b27  js      short loc_140099B7A
0x140099b29  mov     rcx, [rbp+phHash]; hHash
0x140099b2d  lea     r8d, [r9+11h]; cbInput
0x140099b31  lea     rdx, pbInput; "NVMe-over-Fabrics"
0x140099b38  call    cs:__imp_BCryptHashData
0x140099b3f  nop     dword ptr [rax+rax+00h]
0x140099b44  xor     r9d, r9d; dwFlags
0x140099b47  mov     ebx, eax
0x140099b49  test    eax, eax
0x140099b4b  js      short loc_140099B7A
0x140099b4d  mov     r8d, [rbp+arg_18]; cbOutput
0x140099b51  mov     rdx, [rbp+arg_28]; pbOutput
0x140099b55  mov     rcx, [rbp+phHash]; hHash
0x140099b59  call    cs:__imp_BCryptFinishHash
0x140099b60  nop     dword ptr [rax+rax+00h]
0x140099b65  mov     ebx, eax
0x140099b67  test    eax, eax
0x140099b69  js      short loc_140099B7A
0x140099b6b  movzx   eax, word ptr [rbp+arg_18]
0x140099b6f  mov     [r15], ax
0x140099b73  jmp     short loc_140099B7A
0x140099b75  mov     ebx, 0C000000Dh
0x140099b7a  mov     rcx, [rbp+phHash]; hHash
0x140099b7e  test    rcx, rcx
0x140099b81  jz      short loc_140099B8F
0x140099b83  call    cs:__imp_BCryptDestroyHash
0x140099b8a  nop     dword ptr [rax+rax+00h]
0x140099b8f  test    rsi, rsi
0x140099b92  jz      short loc_140099BA8
0x140099b94  mov     edx, 414E6152h; Tag
0x140099b99  mov     rcx, rsi; P
0x140099b9c  call    cs:__imp_ExFreePoolWithTag
0x140099ba3  nop     dword ptr [rax+rax+00h]
0x140099ba8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140099bac  test    rcx, rcx
0x140099baf  jz      short loc_140099BBF
0x140099bb1  xor     edx, edx; dwFlags
0x140099bb3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140099bba  nop     dword ptr [rax+rax+00h]
0x140099bbf  mov     eax, ebx
0x140099bc1  add     rsp, 68h
0x140099bc5  pop     r15
0x140099bc7  pop     r14
0x140099bc9  pop     r13
0x140099bcb  pop     r12
0x140099bcd  pop     rdi
0x140099bce  pop     rsi
0x140099bcf  pop     rbx
0x140099bd0  pop     rbp
0x140099bd1  retn
```
