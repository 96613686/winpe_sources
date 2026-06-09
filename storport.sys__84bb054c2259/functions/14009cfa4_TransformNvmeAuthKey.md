# TransformNvmeAuthKey

- ea: `0x14009cfa4`
- end: `0x14009d23c`
- name: `TransformNvmeAuthKey`
- size: `664`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, __int64, PUCHAR)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140099750`
- `0x14009ad8c`

## callees

- `0x14009cfa4`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009d205`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d205`
- `ntoskrnl!ExAllocatePool2` at `0x14009d0a5`
- `ntoskrnl!ExAllocatePool2` at `0x14009d0a5`
- `ksecdd!BCryptCreateHash` at `0x14009d154`
- `ksecdd!BCryptCreateHash` at `0x14009d154`
- `ksecdd!BCryptHashData` at `0x14009d17d`
- `ksecdd!BCryptHashData` at `0x14009d1a1`
- `ksecdd!BCryptHashData` at `0x14009d17d`
- `ksecdd!BCryptHashData` at `0x14009d1a1`
- `ksecdd!BCryptDestroyHash` at `0x14009d1ec`
- `ksecdd!BCryptDestroyHash` at `0x14009d1ec`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14009d21c`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14009d21c`
- `ksecdd!BCryptFinishHash` at `0x14009d1c2`
- `ksecdd!BCryptFinishHash` at `0x14009d1c2`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14009d045`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14009d045`
- `ksecdd!BCryptGetProperty` at `0x14009d081`
- `ksecdd!BCryptGetProperty` at `0x14009d0e9`
- `ksecdd!BCryptGetProperty` at `0x14009d081`
- `ksecdd!BCryptGetProperty` at `0x14009d0e9`

## pseudocode

```c
__int64 __fastcall TransformNvmeAuthKey(
        PUCHAR pbInput,
        unsigned __int16 a2,
        void *a3,
        unsigned __int16 a4,
        unsigned __int16 *a5,
        PUCHAR a6)
{
  unsigned __int16 *v6; // r15
  int v8; // edi
  ULONG v10; // r14d
  PUCHAR v11; // rcx
  NTSTATUS Property; // ebx
  UCHAR *Pool2; // rsi
  const WCHAR *v14; // rdx
  int v15; // edx
  __int64 v16; // r8
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-18h] BYREF
  ULONG v22; // [rsp+C8h] [rbp+60h] BYREF

  v6 = a5;
  v8 = a4;
  v10 = a2;
  phAlgorithm = 0;
  *a5 = 0;
  phHash = 0;
  v22 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( !a4 )
  {
    v11 = a6;
    *v6 = a2;
    Property = 0;
    memmove(v11, a3, a2);
    return (unsigned int)Property;
  }
  Pool2 = 0;
  switch ( a4 )
  {
    case 1u:
      v14 = L"SHA256";
LABEL_9:
      Property = BCryptOpenAlgorithmProvider(&phAlgorithm, v14, L"Microsoft Primitive Provider", 8u);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1095655762);
          if ( Pool2 )
          {
            Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&v22, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( v8 == 1 )
              {
                v15 = 32;
              }
              else if ( v8 == 2 )
              {
                v15 = 48;
              }
              else
              {
                v15 = 64;
              }
              if ( v22 == v15 )
              {
                Property = BCryptCreateHash(phAlgorithm, &phHash, Pool2, *(ULONG *)pbOutput, (PUCHAR)a3, v10, 0);
                if ( Property >= 0 )
                {
                  v16 = -1;
                  do
                    ++v16;
                  while ( pbInput[v16] );
                  Property = BCryptHashData(phHash, pbInput, v16, 0);
                  if ( Property >= 0 )
                  {
                    Property = BCryptHashData(phHash, (PUCHAR)"NVMe-over-Fabrics", 0x11u, 0);
                    if ( Property >= 0 )
                    {
                      Property = BCryptFinishHash(phHash, a6, v22, 0);
                      if ( Property >= 0 )
                        *v6 = v22;
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
      goto LABEL_29;
    case 2u:
      v14 = L"SHA384";
      goto LABEL_9;
    case 3u:
      v14 = L"SHA512";
      goto LABEL_9;
  }
  Property = -1073741811;
LABEL_29:
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
0x14009cfa4  push    rbp
0x14009cfa6  push    rbx
0x14009cfa7  push    rsi
0x14009cfa8  push    rdi
0x14009cfa9  push    r12
0x14009cfab  push    r13
0x14009cfad  push    r14
0x14009cfaf  push    r15
0x14009cfb1  mov     rbp, rsp
0x14009cfb4  sub     rsp, 68h
0x14009cfb8  mov     r15, [rbp+arg_20]
0x14009cfbc  mov     r12, r8
0x14009cfbf  movzx   edi, r9w
0x14009cfc3  mov     r13, rcx
0x14009cfc6  xor     r9d, r9d
0x14009cfc9  movzx   r14d, dx
0x14009cfcd  mov     [rbp+phAlgorithm], r9
0x14009cfd1  mov     [r15], r9w
0x14009cfd5  mov     [rbp+phHash], r9
0x14009cfd9  mov     [rbp+arg_18], r9d
0x14009cfdd  mov     dword ptr [rbp+pbOutput], r9d
0x14009cfe1  mov     [rbp+var_24], r9d
0x14009cfe5  test    di, di
0x14009cfe8  jnz     short loc_14009D005
0x14009cfea  mov     rcx, [rbp+arg_28]; void *
0x14009cfee  mov     r8d, r14d; Size
0x14009cff1  mov     rdx, r12; Src
0x14009cff4  mov     [r15], r14w
0x14009cff8  mov     ebx, r9d
0x14009cffb  call    memmove
0x14009d000  jmp     loc_14009D228
0x14009d005  mov     rsi, r9
0x14009d008  cmp     edi, 1
0x14009d00b  jnz     short loc_14009D016
0x14009d00d  lea     rdx, aSha256; "SHA256"
0x14009d014  jmp     short loc_14009D034
0x14009d016  cmp     edi, 2
0x14009d019  jnz     short loc_14009D024
0x14009d01b  lea     rdx, aSha384; "SHA384"
0x14009d022  jmp     short loc_14009D034
0x14009d024  cmp     edi, 3
0x14009d027  jnz     loc_14009D1DE
0x14009d02d  lea     rdx, pszAlgId; "SHA512"
0x14009d034  mov     r9d, 8; dwFlags
0x14009d03a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14009d041  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x14009d045  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14009d04c  nop     dword ptr [rax+rax+00h]
0x14009d051  xor     r9d, r9d
0x14009d054  mov     ebx, eax
0x14009d056  test    eax, eax
0x14009d058  js      loc_14009D1E3
0x14009d05e  mov     rcx, [rbp+phAlgorithm]; hObject
0x14009d062  lea     rax, [rbp+var_24]
0x14009d066  mov     [rsp+68h+dwFlags], r9d; dwFlags
0x14009d06b  lea     r8, [rbp+pbOutput]; pbOutput
0x14009d06f  mov     r9d, 4; cbOutput
0x14009d075  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14009d07a  lea     rdx, pszProperty; "ObjectLength"
0x14009d081  call    cs:__imp_BCryptGetProperty
0x14009d088  nop     dword ptr [rax+rax+00h]
0x14009d08d  mov     ebx, eax
0x14009d08f  test    eax, eax
0x14009d091  js      loc_14009D1E3
0x14009d097  mov     edx, dword ptr [rbp+pbOutput]
0x14009d09a  mov     ecx, 100h
0x14009d09f  mov     r8d, 414E6152h
0x14009d0a5  call    cs:__imp_ExAllocatePool2
0x14009d0ac  nop     dword ptr [rax+rax+00h]
0x14009d0b1  xor     r9d, r9d
0x14009d0b4  mov     rsi, rax
0x14009d0b7  test    rax, rax
0x14009d0ba  jnz     short loc_14009D0C6
0x14009d0bc  mov     ebx, 0C0000017h
0x14009d0c1  jmp     loc_14009D1E3
0x14009d0c6  mov     rcx, [rbp+phAlgorithm]; hObject
0x14009d0ca  lea     rax, [rbp+var_24]
0x14009d0ce  mov     [rsp+68h+dwFlags], r9d; dwFlags
0x14009d0d3  lea     r8, [rbp+arg_18]; pbOutput
0x14009d0d7  mov     r9d, 4; cbOutput
0x14009d0dd  mov     [rsp+68h+pcbResult], rax; pcbResult
0x14009d0e2  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14009d0e9  call    cs:__imp_BCryptGetProperty
0x14009d0f0  nop     dword ptr [rax+rax+00h]
0x14009d0f5  xor     r9d, r9d
0x14009d0f8  mov     ebx, eax
0x14009d0fa  test    eax, eax
0x14009d0fc  js      loc_14009D1E3
0x14009d102  mov     ecx, edi
0x14009d104  mov     edx, r9d
0x14009d107  sub     ecx, 1
0x14009d10a  jz      short loc_14009D122
0x14009d10c  sub     ecx, 1
0x14009d10f  jz      short loc_14009D11B
0x14009d111  cmp     ecx, 1
0x14009d114  jnz     short loc_14009D127
0x14009d116  lea     edx, [rcx+3Fh]
0x14009d119  jmp     short loc_14009D127
0x14009d11b  mov     edx, 30h ; '0'
0x14009d120  jmp     short loc_14009D127
0x14009d122  mov     edx, 20h ; ' '
0x14009d127  cmp     [rbp+arg_18], edx
0x14009d12a  jz      short loc_14009D136
0x14009d12c  mov     ebx, 0C0000004h
0x14009d131  jmp     loc_14009D1E3
0x14009d136  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14009d13a  lea     rdx, [rbp+phHash]; phHash
0x14009d13e  mov     [rsp+68h+var_38], r9d; dwFlags
0x14009d143  mov     r8, rsi; pbHashObject
0x14009d146  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x14009d14a  mov     [rsp+68h+dwFlags], r14d; cbSecret
0x14009d14f  mov     [rsp+68h+pcbResult], r12; pbSecret
0x14009d154  call    cs:__imp_BCryptCreateHash
0x14009d15b  nop     dword ptr [rax+rax+00h]
0x14009d160  xor     r9d, r9d; dwFlags
0x14009d163  mov     ebx, eax
0x14009d165  test    eax, eax
0x14009d167  js      short loc_14009D1E3
0x14009d169  or      r8, 0FFFFFFFFFFFFFFFFh
0x14009d16d  inc     r8; cbInput
0x14009d170  cmp     [r8+r13], r9b
0x14009d174  jnz     short loc_14009D16D
0x14009d176  mov     rcx, [rbp+phHash]; hHash
0x14009d17a  mov     rdx, r13; pbInput
0x14009d17d  call    cs:__imp_BCryptHashData
0x14009d184  nop     dword ptr [rax+rax+00h]
0x14009d189  xor     r9d, r9d; dwFlags
0x14009d18c  mov     ebx, eax
0x14009d18e  test    eax, eax
0x14009d190  js      short loc_14009D1E3
0x14009d192  mov     rcx, [rbp+phHash]; hHash
0x14009d196  lea     r8d, [r9+11h]; cbInput
0x14009d19a  lea     rdx, pbInput; "NVMe-over-Fabrics"
0x14009d1a1  call    cs:__imp_BCryptHashData
0x14009d1a8  nop     dword ptr [rax+rax+00h]
0x14009d1ad  xor     r9d, r9d; dwFlags
0x14009d1b0  mov     ebx, eax
0x14009d1b2  test    eax, eax
0x14009d1b4  js      short loc_14009D1E3
0x14009d1b6  mov     r8d, [rbp+arg_18]; cbOutput
0x14009d1ba  mov     rdx, [rbp+arg_28]; pbOutput
0x14009d1be  mov     rcx, [rbp+phHash]; hHash
0x14009d1c2  call    cs:__imp_BCryptFinishHash
0x14009d1c9  nop     dword ptr [rax+rax+00h]
0x14009d1ce  mov     ebx, eax
0x14009d1d0  test    eax, eax
0x14009d1d2  js      short loc_14009D1E3
0x14009d1d4  movzx   eax, word ptr [rbp+arg_18]
0x14009d1d8  mov     [r15], ax
0x14009d1dc  jmp     short loc_14009D1E3
0x14009d1de  mov     ebx, 0C000000Dh
0x14009d1e3  mov     rcx, [rbp+phHash]; hHash
0x14009d1e7  test    rcx, rcx
0x14009d1ea  jz      short loc_14009D1F8
0x14009d1ec  call    cs:__imp_BCryptDestroyHash
0x14009d1f3  nop     dword ptr [rax+rax+00h]
0x14009d1f8  test    rsi, rsi
0x14009d1fb  jz      short loc_14009D211
0x14009d1fd  mov     edx, 414E6152h; Tag
0x14009d202  mov     rcx, rsi; P
0x14009d205  call    cs:__imp_ExFreePoolWithTag
0x14009d20c  nop     dword ptr [rax+rax+00h]
0x14009d211  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14009d215  test    rcx, rcx
0x14009d218  jz      short loc_14009D228
0x14009d21a  xor     edx, edx; dwFlags
0x14009d21c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14009d223  nop     dword ptr [rax+rax+00h]
0x14009d228  mov     eax, ebx
0x14009d22a  add     rsp, 68h
0x14009d22e  pop     r15
0x14009d230  pop     r14
0x14009d232  pop     r13
0x14009d234  pop     r12
0x14009d236  pop     rdi
0x14009d237  pop     rsi
0x14009d238  pop     rbx
0x14009d239  pop     rbp
0x14009d23a  retn
```
