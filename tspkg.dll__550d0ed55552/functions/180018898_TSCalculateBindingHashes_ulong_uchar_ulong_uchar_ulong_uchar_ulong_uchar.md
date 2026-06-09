# TSCalculateBindingHashes(ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *)

- ea: `0x180018898`
- end: `0x180018b20`
- name: `?TSCalculateBindingHashes@@YAJKPEAEK0K0K0@Z`
- size: `648`
- prototype: `int(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001160`
- `0x180006650`

## callees

- `0x1800032c0`
- `0x180005ed0`
- `0x180018898`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018ae7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018ae7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800188f8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800188f8`
- `bcrypt!BCryptCreateHash` at `0x1800189b0`
- `bcrypt!BCryptCreateHash` at `0x180018a68`
- `bcrypt!BCryptCreateHash` at `0x1800189b0`
- `bcrypt!BCryptCreateHash` at `0x180018a68`
- `bcrypt!BCryptHashData` at `0x1800189d2`
- `bcrypt!BCryptHashData` at `0x1800189f0`
- `bcrypt!BCryptHashData` at `0x180018a0d`
- `bcrypt!BCryptHashData` at `0x180018a86`
- `bcrypt!BCryptHashData` at `0x180018aa0`
- `bcrypt!BCryptHashData` at `0x180018ab9`
- `bcrypt!BCryptHashData` at `0x1800189d2`
- `bcrypt!BCryptHashData` at `0x1800189f0`
- `bcrypt!BCryptHashData` at `0x180018a0d`
- `bcrypt!BCryptHashData` at `0x180018a86`
- `bcrypt!BCryptHashData` at `0x180018aa0`
- `bcrypt!BCryptHashData` at `0x180018ab9`
- `bcrypt!BCryptFinishHash` at `0x180018a2c`
- `bcrypt!BCryptFinishHash` at `0x180018ad4`
- `bcrypt!BCryptFinishHash` at `0x180018a2c`
- `bcrypt!BCryptFinishHash` at `0x180018ad4`
- `bcrypt!BCryptDestroyHash` at `0x180018a40`
- `bcrypt!BCryptDestroyHash` at `0x180018af6`
- `bcrypt!BCryptDestroyHash` at `0x180018a40`
- `bcrypt!BCryptDestroyHash` at `0x180018af6`
- `bcrypt!BCryptGetProperty` at `0x180018928`
- `bcrypt!BCryptGetProperty` at `0x180018958`
- `bcrypt!BCryptGetProperty` at `0x180018928`
- `bcrypt!BCryptGetProperty` at `0x180018958`

## pseudocode

```c
__int64 __fastcall TSCalculateBindingHashes(
        __int64 a1,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        ULONG pcbResult,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8)
{
  UCHAR *v11; // rdi
  NTSTATUS Property; // ebx
  UCHAR *v13; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-10h] BYREF
  ULONG pbOutput; // [rsp+90h] [rbp+38h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbOutput = 0;
  a7 = 0;
  pcbResult = 0;
  if ( a2 && a6 && a8 )
  {
    v11 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&a7, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          if ( a7 == 32 )
          {
            v13 = (UCHAR *)TSAllocate(pbOutput);
            v11 = v13;
            if ( v13 )
            {
              Property = BCryptCreateHash(phAlgorithm, &phHash, v13, pbOutput, 0, 0, 0);
              if ( Property >= 0 )
              {
                Property = BCryptHashData(phHash, (PUCHAR)"CredSSP Client-To-Server Binding Hash", 0x26u, 0);
                if ( Property >= 0 )
                {
                  Property = BCryptHashData(phHash, a2, 0x20u, 0);
                  if ( Property >= 0 )
                  {
                    Property = BCryptHashData(phHash, a4, a3, 0);
                    if ( Property >= 0 )
                    {
                      Property = BCryptFinishHash(phHash, a6, 0x20u, 0);
                      if ( Property >= 0 )
                      {
                        BCryptDestroyHash(phHash);
                        phHash = 0;
                        Property = BCryptCreateHash(phAlgorithm, &phHash, v11, pbOutput, 0, 0, 0);
                        if ( Property >= 0 )
                        {
                          Property = BCryptHashData(phHash, (PUCHAR)"CredSSP Server-To-Client Binding Hash", 0x26u, 0);
                          if ( Property >= 0 )
                          {
                            Property = BCryptHashData(phHash, a2, 0x20u, 0);
                            if ( Property >= 0 )
                            {
                              Property = BCryptHashData(phHash, a4, a3, 0);
                              if ( Property >= 0 )
                                Property = BCryptFinishHash(phHash, a8, 0x20u, 0);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            else
            {
              Property = -1073741670;
            }
          }
          else
          {
            Property = -1073741811;
          }
        }
      }
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( phHash )
      BCryptDestroyHash(phHash);
    if ( v11 )
      TSFree(v11);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180018898  mov     [rsp-30h+pbOutput], ecx
0x18001889c  push    rbp
0x18001889d  push    rbx
0x18001889e  push    rdi
0x18001889f  push    r12
0x1800188a1  push    r13
0x1800188a3  push    r14
0x1800188a5  mov     rbp, rsp
0x1800188a8  sub     rsp, 58h
0x1800188ac  xor     eax, eax
0x1800188ae  mov     r12, r9
0x1800188b1  mov     [rbp+phAlgorithm], rax
0x1800188b5  mov     r13d, r8d
0x1800188b8  mov     [rbp+phHash], rax
0x1800188bc  mov     r14, rdx
0x1800188bf  mov     [rbp+pbOutput], eax
0x1800188c2  mov     dword ptr [rbp+arg_30], eax
0x1800188c5  mov     [rbp+arg_20], eax
0x1800188c8  test    rdx, rdx
0x1800188cb  jz      loc_180018B0B
0x1800188d1  cmp     [rbp+arg_28], rax
0x1800188d5  jz      loc_180018B0B
0x1800188db  cmp     [rbp+arg_38], rax
0x1800188df  jz      loc_180018B0B
0x1800188e5  xor     r9d, r9d; dwFlags
0x1800188e8  lea     rdx, pszAlgId; "SHA256"
0x1800188ef  xor     r8d, r8d; pszImplementation
0x1800188f2  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800188f6  mov     edi, eax
0x1800188f8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800188fe  mov     ebx, eax
0x180018900  test    eax, eax
0x180018902  js      loc_180018ADC
0x180018908  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001890c  lea     rax, [rbp+arg_20]
0x180018910  mov     [rsp+58h+dwFlags], edi; dwFlags
0x180018914  lea     r9d, [rdi+4]; cbOutput
0x180018918  lea     r8, [rbp+pbOutput]; pbOutput
0x18001891c  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180018921  lea     rdx, pszProperty; "ObjectLength"
0x180018928  call    cs:__imp_BCryptGetProperty
0x18001892e  mov     ebx, eax
0x180018930  test    eax, eax
0x180018932  js      loc_180018ADC
0x180018938  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001893c  lea     rax, [rbp+arg_20]
0x180018940  mov     [rsp+58h+dwFlags], edi; dwFlags
0x180018944  lea     r9d, [rdi+4]; cbOutput
0x180018948  lea     r8, [rbp+arg_30]; pbOutput
0x18001894c  mov     [rsp+58h+pcbResult], rax; pcbResult
0x180018951  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180018958  call    cs:__imp_BCryptGetProperty
0x18001895e  mov     ebx, eax
0x180018960  test    eax, eax
0x180018962  js      loc_180018ADC
0x180018968  cmp     dword ptr [rbp+arg_30], 20h ; ' '
0x18001896c  jz      short loc_180018978
0x18001896e  mov     ebx, 0C000000Dh
0x180018973  jmp     loc_180018ADC
0x180018978  mov     ecx, [rbp+pbOutput]; Size
0x18001897b  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180018980  xor     ecx, ecx
0x180018982  mov     rdi, rax
0x180018985  test    rax, rax
0x180018988  jnz     short loc_180018994
0x18001898a  mov     ebx, 0C000009Ah
0x18001898f  jmp     loc_180018ADC
0x180018994  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180018998  lea     rdx, [rbp+phHash]; phHash
0x18001899c  mov     [rsp+58h+var_28], ecx; dwFlags
0x1800189a0  mov     r8, rdi; pbHashObject
0x1800189a3  mov     [rsp+58h+dwFlags], ecx; cbSecret
0x1800189a7  mov     [rsp+58h+pcbResult], rcx; pbSecret
0x1800189ac  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800189b0  call    cs:__imp_BCryptCreateHash
0x1800189b6  mov     ebx, eax
0x1800189b8  test    eax, eax
0x1800189ba  js      loc_180018ADC
0x1800189c0  mov     rcx, [rbp+phHash]; hHash
0x1800189c4  lea     rdx, pbInput; "CredSSP Client-To-Server Binding Hash"
0x1800189cb  xor     r9d, r9d; dwFlags
0x1800189ce  lea     r8d, [r9+26h]; cbInput
0x1800189d2  call    cs:__imp_BCryptHashData
0x1800189d8  mov     ebx, eax
0x1800189da  test    eax, eax
0x1800189dc  js      loc_180018ADC
0x1800189e2  mov     rcx, [rbp+phHash]; hHash
0x1800189e6  xor     r9d, r9d; dwFlags
0x1800189e9  mov     rdx, r14; pbInput
0x1800189ec  lea     r8d, [r9+20h]; cbInput
0x1800189f0  call    cs:__imp_BCryptHashData
0x1800189f6  mov     ebx, eax
0x1800189f8  test    eax, eax
0x1800189fa  js      loc_180018ADC
0x180018a00  mov     rcx, [rbp+phHash]; hHash
0x180018a04  xor     r9d, r9d; dwFlags
0x180018a07  mov     r8d, r13d; cbInput
0x180018a0a  mov     rdx, r12; pbInput
0x180018a0d  call    cs:__imp_BCryptHashData
0x180018a13  mov     ebx, eax
0x180018a15  test    eax, eax
0x180018a17  js      loc_180018ADC
0x180018a1d  mov     rdx, [rbp+arg_28]; pbOutput
0x180018a21  xor     r9d, r9d; dwFlags
0x180018a24  mov     rcx, [rbp+phHash]; hHash
0x180018a28  lea     r8d, [r9+20h]; cbOutput
0x180018a2c  call    cs:__imp_BCryptFinishHash
0x180018a32  mov     ebx, eax
0x180018a34  test    eax, eax
0x180018a36  js      loc_180018ADC
0x180018a3c  mov     rcx, [rbp+phHash]; hHash
0x180018a40  call    cs:__imp_BCryptDestroyHash
0x180018a46  mov     r9d, [rbp+pbOutput]; cbHashObject
0x180018a4a  lea     rdx, [rbp+phHash]; phHash
0x180018a4e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180018a52  xor     eax, eax
0x180018a54  mov     [rsp+58h+var_28], eax; dwFlags
0x180018a58  mov     r8, rdi; pbHashObject
0x180018a5b  mov     [rsp+58h+dwFlags], eax; cbSecret
0x180018a5f  mov     [rsp+58h+pcbResult], rax; pbSecret
0x180018a64  mov     [rbp+phHash], rax
0x180018a68  call    cs:__imp_BCryptCreateHash
0x180018a6e  mov     ebx, eax
0x180018a70  test    eax, eax
0x180018a72  js      short loc_180018ADC
0x180018a74  mov     rcx, [rbp+phHash]; hHash
0x180018a78  lea     rdx, aCredsspServerT; "CredSSP Server-To-Client Binding Hash"
0x180018a7f  xor     r9d, r9d; dwFlags
0x180018a82  lea     r8d, [r9+26h]; cbInput
0x180018a86  call    cs:__imp_BCryptHashData
0x180018a8c  mov     ebx, eax
0x180018a8e  test    eax, eax
0x180018a90  js      short loc_180018ADC
0x180018a92  mov     rcx, [rbp+phHash]; hHash
0x180018a96  xor     r9d, r9d; dwFlags
0x180018a99  mov     rdx, r14; pbInput
0x180018a9c  lea     r8d, [r9+20h]; cbInput
0x180018aa0  call    cs:__imp_BCryptHashData
0x180018aa6  mov     ebx, eax
0x180018aa8  test    eax, eax
0x180018aaa  js      short loc_180018ADC
0x180018aac  mov     rcx, [rbp+phHash]; hHash
0x180018ab0  xor     r9d, r9d; dwFlags
0x180018ab3  mov     r8d, r13d; cbInput
0x180018ab6  mov     rdx, r12; pbInput
0x180018ab9  call    cs:__imp_BCryptHashData
0x180018abf  mov     ebx, eax
0x180018ac1  test    eax, eax
0x180018ac3  js      short loc_180018ADC
0x180018ac5  mov     rdx, [rbp+arg_38]; pbOutput
0x180018ac9  xor     r9d, r9d; dwFlags
0x180018acc  mov     rcx, [rbp+phHash]; hHash
0x180018ad0  lea     r8d, [r9+20h]; cbOutput
0x180018ad4  call    cs:__imp_BCryptFinishHash
0x180018ada  mov     ebx, eax
0x180018adc  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180018ae0  test    rcx, rcx
0x180018ae3  jz      short loc_180018AED
0x180018ae5  xor     edx, edx; dwFlags
0x180018ae7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180018aed  mov     rcx, [rbp+phHash]; hHash
0x180018af1  test    rcx, rcx
0x180018af4  jz      short loc_180018AFC
0x180018af6  call    cs:__imp_BCryptDestroyHash
0x180018afc  test    rdi, rdi
0x180018aff  jz      short loc_180018B10
0x180018b01  mov     rcx, rdi; void *
0x180018b04  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180018b09  jmp     short loc_180018B10
0x180018b0b  mov     ebx, 0C000000Dh
0x180018b10  mov     eax, ebx
0x180018b12  add     rsp, 58h
0x180018b16  pop     r14
0x180018b18  pop     r13
0x180018b1a  pop     r12
0x180018b1c  pop     rdi
0x180018b1d  pop     rbx
0x180018b1e  pop     rbp
0x180018b1f  retn
```
