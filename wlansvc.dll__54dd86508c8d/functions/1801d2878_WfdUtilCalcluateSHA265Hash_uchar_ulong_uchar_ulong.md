# WfdUtilCalcluateSHA265Hash(uchar *,ulong,uchar *,ulong *)

- ea: `0x1801d2878`
- end: `0x1801d2a60`
- name: `?WfdUtilCalcluateSHA265Hash@@YAJPEAEK0PEAK@Z`
- size: `488`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801d2f70`

## callees

- `0x180107294`
- `0x1801072b8`
- `0x1801d2878`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801d2a32`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801d2a32`
- `bcrypt!BCryptCreateHash` at `0x1801d29c9`
- `bcrypt!BCryptCreateHash` at `0x1801d29c9`
- `bcrypt!BCryptGetProperty` at `0x1801d291e`
- `bcrypt!BCryptGetProperty` at `0x1801d2973`
- `bcrypt!BCryptGetProperty` at `0x1801d291e`
- `bcrypt!BCryptGetProperty` at `0x1801d2973`
- `bcrypt!BCryptHashData` at `0x1801d29e9`
- `bcrypt!BCryptHashData` at `0x1801d29e9`
- `bcrypt!BCryptFinishHash` at `0x1801d2a09`
- `bcrypt!BCryptFinishHash` at `0x1801d2a09`
- `bcrypt!BCryptDestroyHash` at `0x1801d2a21`
- `bcrypt!BCryptDestroyHash` at `0x1801d2a21`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801d28e7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801d28e7`

## pseudocode

```c
__int64 __fastcall WfdUtilCalcluateSHA265Hash(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput, unsigned int *a4)
{
  UCHAR *v4; // rdi
  unsigned int Property; // ebx
  UCHAR *v10; // rax
  UCHAR pbOutputa[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-1Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG v16; // [rsp+90h] [rbp+30h] BYREF

  v4 = 0;
  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutputa = 0;
  v16 = 0;
  if ( !pbInput || !a4 )
    goto LABEL_14;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_15;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutputa, 4u, &pcbResult, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_15;
  if ( *a4 != *(_DWORD *)pbOutputa )
  {
    Property = -1073741789;
    *a4 = *(_DWORD *)pbOutputa;
    goto LABEL_15;
  }
  if ( !pbOutput )
  {
LABEL_14:
    Property = -1073741811;
    goto LABEL_15;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&v16, 4u, &pcbResult, 0);
  if ( (Property & 0xC0000000) != 0xC0000000 )
  {
    v10 = (UCHAR *)o_malloc_0(v16);
    v4 = v10;
    if ( v10 )
    {
      Property = BCryptCreateHash(phAlgorithm, &phHash, v10, v16, 0, 0, 0);
      if ( (Property & 0xC0000000) != 0xC0000000 )
      {
        Property = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( (Property & 0xC0000000) != 0xC0000000 )
          Property = BCryptFinishHash(phHash, pbOutput, *a4, 0);
      }
    }
    else
    {
      Property = -1073741801;
    }
  }
LABEL_15:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v4 )
    free(v4);
  return Property;
}

```

## disassembly

```asm
0x1801d2878  mov     [rsp-28h+arg_8], rbx
0x1801d287d  mov     [rsp-28h+arg_10], rsi
0x1801d2882  push    rbp
0x1801d2883  push    rdi
0x1801d2884  push    r12
0x1801d2886  push    r14
0x1801d2888  push    r15
0x1801d288a  mov     rbp, rsp
0x1801d288d  sub     rsp, 60h
0x1801d2891  xor     edi, edi
0x1801d2893  mov     [rbp+phAlgorithm], 0
0x1801d289b  mov     [rbp+phHash], 0
0x1801d28a3  mov     rsi, r9
0x1801d28a6  mov     [rbp+var_1C], 0
0x1801d28ad  mov     r14, r8
0x1801d28b0  mov     dword ptr [rbp+pbOutput], 0
0x1801d28b7  mov     r12d, edx
0x1801d28ba  mov     [rbp+arg_0], 0
0x1801d28c1  mov     r15, rcx
0x1801d28c4  test    rcx, rcx
0x1801d28c7  jz      loc_1801D2A13
0x1801d28cd  test    r9, r9
0x1801d28d0  jz      loc_1801D2A13
0x1801d28d6  xor     r9d, r9d; dwFlags
0x1801d28d9  lea     rdx, aSha256; "SHA256"
0x1801d28e0  xor     r8d, r8d; pszImplementation
0x1801d28e3  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1801d28e7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801d28ed  mov     ecx, 0C0000000h
0x1801d28f2  mov     ebx, eax
0x1801d28f4  and     eax, ecx
0x1801d28f6  cmp     eax, ecx
0x1801d28f8  jz      loc_1801D2A18
0x1801d28fe  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801d2902  lea     rax, [rbp+var_1C]
0x1801d2906  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1801d290a  lea     r9d, [rdi+4]; cbOutput
0x1801d290e  lea     r8, [rbp+pbOutput]; pbOutput
0x1801d2912  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1801d2917  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1801d291e  call    cs:__imp_BCryptGetProperty
0x1801d2924  mov     ecx, 0C0000000h
0x1801d2929  mov     ebx, eax
0x1801d292b  and     eax, ecx
0x1801d292d  cmp     eax, ecx
0x1801d292f  jz      loc_1801D2A18
0x1801d2935  mov     eax, dword ptr [rbp+pbOutput]
0x1801d2938  cmp     [rsi], eax
0x1801d293a  jz      short loc_1801D2948
0x1801d293c  mov     ebx, 0C0000023h
0x1801d2941  mov     [rsi], eax
0x1801d2943  jmp     loc_1801D2A18
0x1801d2948  test    r14, r14
0x1801d294b  jz      loc_1801D2A13
0x1801d2951  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801d2955  lea     rax, [rbp+var_1C]
0x1801d2959  mov     [rsp+60h+dwFlags], edi; dwFlags
0x1801d295d  lea     r8, [rbp+arg_0]; pbOutput
0x1801d2961  mov     r9d, 4; cbOutput
0x1801d2967  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1801d296c  lea     rdx, pszProperty; "ObjectLength"
0x1801d2973  call    cs:__imp_BCryptGetProperty
0x1801d2979  mov     ecx, 0C0000000h
0x1801d297e  mov     ebx, eax
0x1801d2980  and     eax, ecx
0x1801d2982  cmp     eax, ecx
0x1801d2984  jz      loc_1801D2A18
0x1801d298a  mov     ecx, [rbp+arg_0]; Size
0x1801d298d  call    _o_malloc_0
0x1801d2992  mov     rdi, rax
0x1801d2995  test    rax, rax
0x1801d2998  jnz     short loc_1801D29A1
0x1801d299a  mov     ebx, 0C0000017h
0x1801d299f  jmp     short loc_1801D2A18
0x1801d29a1  mov     r9d, [rbp+arg_0]; cbHashObject
0x1801d29a5  lea     rdx, [rbp+phHash]; phHash
0x1801d29a9  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801d29ad  mov     r8, rax; pbHashObject
0x1801d29b0  mov     [rsp+60h+var_30], 0; dwFlags
0x1801d29b8  mov     [rsp+60h+dwFlags], 0; cbSecret
0x1801d29c0  mov     [rsp+60h+pcbResult], 0; pbSecret
0x1801d29c9  call    cs:__imp_BCryptCreateHash
0x1801d29cf  mov     ecx, 0C0000000h
0x1801d29d4  mov     ebx, eax
0x1801d29d6  and     eax, ecx
0x1801d29d8  cmp     eax, ecx
0x1801d29da  jz      short loc_1801D2A18
0x1801d29dc  mov     rcx, [rbp+phHash]; hHash
0x1801d29e0  xor     r9d, r9d; dwFlags
0x1801d29e3  mov     r8d, r12d; cbInput
0x1801d29e6  mov     rdx, r15; pbInput
0x1801d29e9  call    cs:__imp_BCryptHashData
0x1801d29ef  mov     ecx, 0C0000000h
0x1801d29f4  mov     ebx, eax
0x1801d29f6  and     eax, ecx
0x1801d29f8  cmp     eax, ecx
0x1801d29fa  jz      short loc_1801D2A18
0x1801d29fc  mov     r8d, [rsi]; cbOutput
0x1801d29ff  xor     r9d, r9d; dwFlags
0x1801d2a02  mov     rcx, [rbp+phHash]; hHash
0x1801d2a06  mov     rdx, r14; pbOutput
0x1801d2a09  call    cs:__imp_BCryptFinishHash
0x1801d2a0f  mov     ebx, eax
0x1801d2a11  jmp     short loc_1801D2A18
0x1801d2a13  mov     ebx, 0C000000Dh
0x1801d2a18  mov     rcx, [rbp+phHash]; hHash
0x1801d2a1c  test    rcx, rcx
0x1801d2a1f  jz      short loc_1801D2A27
0x1801d2a21  call    cs:__imp_BCryptDestroyHash
0x1801d2a27  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801d2a2b  test    rcx, rcx
0x1801d2a2e  jz      short loc_1801D2A38
0x1801d2a30  xor     edx, edx; dwFlags
0x1801d2a32  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801d2a38  test    rdi, rdi
0x1801d2a3b  jz      short loc_1801D2A45
0x1801d2a3d  mov     rcx, rdi; Block
0x1801d2a40  call    free
0x1801d2a45  lea     r11, [rsp+60h+var_s0]
0x1801d2a4a  mov     eax, ebx
0x1801d2a4c  mov     rbx, [r11+38h]
0x1801d2a50  mov     rsi, [r11+40h]
0x1801d2a54  mov     rsp, r11
0x1801d2a57  pop     r15
0x1801d2a59  pop     r14
0x1801d2a5b  pop     r12
0x1801d2a5d  pop     rdi
0x1801d2a5e  pop     rbp
0x1801d2a5f  retn
```
