# KEGenerateHMACWithSHA512

- ea: `0x1800174e0`
- end: `0x1800176a9`
- name: `KEGenerateHMACWithSHA512`
- size: `457`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b38`

## callees

- `0x1800174e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017688`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017688`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017578`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800175d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017578`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800175d7`
- `bcrypt!BCryptGetProperty` at `0x180017558`
- `bcrypt!BCryptGetProperty` at `0x1800175b5`
- `bcrypt!BCryptGetProperty` at `0x180017558`
- `bcrypt!BCryptGetProperty` at `0x1800175b5`
- `bcrypt!BCryptCreateHash` at `0x180017609`
- `bcrypt!BCryptCreateHash` at `0x180017609`
- `bcrypt!BCryptHashData` at `0x180017624`
- `bcrypt!BCryptHashData` at `0x180017624`
- `bcrypt!BCryptDestroyHash` at `0x18001767a`
- `bcrypt!BCryptDestroyHash` at `0x18001767a`
- `bcrypt!BCryptFinishHash` at `0x18001763e`
- `bcrypt!BCryptFinishHash` at `0x18001763e`

## pseudocode

```c
__int64 __fastcall KEGenerateHMACWithSHA512(
        BCRYPT_ALG_HANDLE hAlgorithm,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        PUCHAR *a6,
        _DWORD *a7)
{
  UCHAR *v9; // rsi
  NTSTATUS Property; // ebx
  UCHAR *v11; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  UCHAR v14[4]; // [rsp+44h] [rbp-1Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF

  phHash = 0;
  v9 = 0;
  *(_DWORD *)pbOutput = 0;
  *a6 = 0;
  *a7 = 0;
  *(_DWORD *)v14 = 0;
  pcbResult = 0;
  if ( cbInput && a3 )
  {
    Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
      goto LABEL_14;
    if ( pcbResult == 4 )
    {
      v9 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
      if ( !v9 )
      {
LABEL_6:
        Property = -1073741670;
        goto LABEL_17;
      }
      Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v14, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
LABEL_14:
        if ( !Property )
          goto LABEL_19;
        goto LABEL_17;
      }
      if ( pcbResult == 4 )
      {
        v11 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v14);
        *a6 = v11;
        if ( !v11 )
          goto LABEL_6;
        Property = BCryptCreateHash(hAlgorithm, &phHash, v9, *(ULONG *)pbOutput, a2, a3, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, a4, cbInput, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(phHash, *a6, *(ULONG *)v14, 0);
            if ( Property >= 0 )
              *a7 = *(_DWORD *)v14;
          }
        }
        goto LABEL_14;
      }
    }
  }
  Property = -1073741811;
LABEL_17:
  if ( *a6 )
  {
    LocalFree(*a6);
    *a6 = 0;
  }
LABEL_19:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800174e0  mov     rax, rsp
0x1800174e3  mov     [rax+8], rbx
0x1800174e7  mov     [rax+18h], rsi
0x1800174eb  mov     [rax+20h], r9
0x1800174ef  mov     [rax+10h], rdx
0x1800174f3  push    rbp
0x1800174f4  push    rdi
0x1800174f5  push    r12
0x1800174f7  push    r14
0x1800174f9  push    r15
0x1800174fb  mov     rbp, rsp
0x1800174fe  sub     rsp, 60h
0x180017502  mov     rdi, [rbp+arg_28]
0x180017506  mov     r15, rcx
0x180017509  mov     r12, [rbp+arg_30]
0x18001750d  xor     ecx, ecx
0x18001750f  mov     r14d, r8d
0x180017512  mov     [rbp+phHash], rcx
0x180017516  mov     esi, ecx
0x180017518  mov     dword ptr [rbp+pbOutput], ecx
0x18001751b  mov     [rdi], rcx
0x18001751e  mov     [r12], ecx
0x180017522  mov     dword ptr [rbp+var_1C], ecx
0x180017525  mov     [rbp+var_20], ecx
0x180017528  cmp     [rbp+cbInput], ecx
0x18001752b  jz      loc_180017657
0x180017531  test    r8d, r8d
0x180017534  jz      loc_180017657
0x18001753a  mov     [rax-60h], ecx
0x18001753d  lea     r9d, [rcx+4]; cbOutput
0x180017541  lea     rax, [rbp+var_20]
0x180017545  mov     rcx, r15; hObject
0x180017548  lea     r8, [rbp+pbOutput]; pbOutput
0x18001754c  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180017551  lea     rdx, aObjectlength; "ObjectLength"
0x180017558  call    cs:__imp_BCryptGetProperty
0x18001755e  mov     ebx, eax
0x180017560  test    eax, eax
0x180017562  js      loc_180017651
0x180017568  cmp     [rbp+var_20], 4
0x18001756c  jnz     loc_180017657
0x180017572  mov     edx, dword ptr [rbp+pbOutput]; uBytes
0x180017575  lea     ecx, [rsi+40h]; uFlags
0x180017578  call    cs:__imp_LocalAlloc
0x18001757e  mov     rsi, rax
0x180017581  test    rax, rax
0x180017584  jnz     short loc_180017590
0x180017586  mov     ebx, 0C000009Ah
0x18001758b  jmp     loc_18001765C
0x180017590  lea     rax, [rbp+var_20]
0x180017594  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001759c  mov     r9d, 4; cbOutput
0x1800175a2  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800175a7  lea     r8, [rbp+var_1C]; pbOutput
0x1800175ab  mov     rcx, r15; hObject
0x1800175ae  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800175b5  call    cs:__imp_BCryptGetProperty
0x1800175bb  mov     ebx, eax
0x1800175bd  test    eax, eax
0x1800175bf  js      loc_180017651
0x1800175c5  cmp     [rbp+var_20], 4
0x1800175c9  jnz     loc_180017657
0x1800175cf  mov     edx, dword ptr [rbp+var_1C]; uBytes
0x1800175d2  mov     ecx, 40h ; '@'; uFlags
0x1800175d7  call    cs:__imp_LocalAlloc
0x1800175dd  mov     [rdi], rax
0x1800175e0  test    rax, rax
0x1800175e3  jz      short loc_180017586
0x1800175e5  mov     rax, [rbp+pbSecret]
0x1800175e9  lea     rdx, [rbp+phHash]; phHash
0x1800175ed  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x1800175f1  mov     r8, rsi; pbHashObject
0x1800175f4  mov     [rsp+60h+var_30], 0; dwFlags
0x1800175fc  mov     rcx, r15; hAlgorithm
0x1800175ff  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180017604  mov     [rsp+60h+pcbResult], rax; pbSecret
0x180017609  call    cs:__imp_BCryptCreateHash
0x18001760f  mov     ebx, eax
0x180017611  test    eax, eax
0x180017613  js      short loc_180017651
0x180017615  mov     r8d, [rbp+cbInput]; cbInput
0x180017619  xor     r9d, r9d; dwFlags
0x18001761c  mov     rdx, [rbp+pbInput]; pbInput
0x180017620  mov     rcx, [rbp+phHash]; hHash
0x180017624  call    cs:__imp_BCryptHashData
0x18001762a  mov     ebx, eax
0x18001762c  test    eax, eax
0x18001762e  js      short loc_180017651
0x180017630  mov     r8d, dword ptr [rbp+var_1C]; cbOutput
0x180017634  xor     r9d, r9d; dwFlags
0x180017637  mov     rdx, [rdi]; pbOutput
0x18001763a  mov     rcx, [rbp+phHash]; hHash
0x18001763e  call    cs:__imp_BCryptFinishHash
0x180017644  mov     ebx, eax
0x180017646  test    eax, eax
0x180017648  js      short loc_180017651
0x18001764a  mov     eax, dword ptr [rbp+var_1C]
0x18001764d  mov     [r12], eax
0x180017651  test    ebx, ebx
0x180017653  jnz     short loc_18001765C
0x180017655  jmp     short loc_180017671
0x180017657  mov     ebx, 0C000000Dh
0x18001765c  mov     rcx, [rdi]; hMem
0x18001765f  test    rcx, rcx
0x180017662  jz      short loc_180017671
0x180017664  call    cs:__imp_LocalFree
0x18001766a  mov     qword ptr [rdi], 0
0x180017671  mov     rcx, [rbp+phHash]; hHash
0x180017675  test    rcx, rcx
0x180017678  jz      short loc_180017680
0x18001767a  call    cs:__imp_BCryptDestroyHash
0x180017680  test    rsi, rsi
0x180017683  jz      short loc_18001768E
0x180017685  mov     rcx, rsi; hMem
0x180017688  call    cs:__imp_LocalFree
0x18001768e  lea     r11, [rsp+60h+var_s0]
0x180017693  mov     eax, ebx
0x180017695  mov     rbx, [r11+30h]
0x180017699  mov     rsi, [r11+40h]
0x18001769d  mov     rsp, r11
0x1800176a0  pop     r15
0x1800176a2  pop     r14
0x1800176a4  pop     r12
0x1800176a6  pop     rdi
0x1800176a7  pop     rbp
0x1800176a8  retn
```
