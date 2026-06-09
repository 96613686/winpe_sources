# TpmApiPlatformHash(ushort *,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x1400329b0`
- end: `0x140032bd7`
- name: `?TpmApiPlatformHash@@YAJPEAGPEAEI1I1IPEAIK@Z`
- size: `551`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG, PUCHAR, ULONG cbOutput, unsigned int *, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400329b0`
- `0x140032c60`
- `0x140032c88`
- `0x140039b40`

## import_xrefs

- `cng!BCryptFinishHash` at `0x140032b75`
- `cng!BCryptFinishHash` at `0x140032b75`
- `cng!BCryptHashData` at `0x140032b54`
- `cng!BCryptHashData` at `0x140032b54`
- `cng!BCryptCloseAlgorithmProvider` at `0x140032bba`
- `cng!BCryptCloseAlgorithmProvider` at `0x140032bba`
- `cng!BCryptDestroyHash` at `0x140032b8c`
- `cng!BCryptDestroyHash` at `0x140032b8c`
- `cng!BCryptCreateHash` at `0x140032b35`
- `cng!BCryptCreateHash` at `0x140032b35`
- `cng!BCryptGetProperty` at `0x140032a70`
- `cng!BCryptGetProperty` at `0x140032ace`
- `cng!BCryptGetProperty` at `0x140032a70`
- `cng!BCryptGetProperty` at `0x140032ace`
- `cng!BCryptOpenAlgorithmProvider` at `0x140032a2f`
- `cng!BCryptOpenAlgorithmProvider` at `0x140032a2f`

## pseudocode

```c
__int64 __fastcall TpmApiPlatformHash(
        LPCWSTR pszAlgId,
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a6,
        ULONG cbOutput,
        unsigned int *a8,
        ULONG dwFlags)
{
  NTSTATUS Property; // ebx
  ULONG v13; // eax
  UCHAR v15[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  UCHAR pbOutput[8]; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-20h] BYREF
  PUCHAR pbHashObject[3]; // [rsp+60h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbHashObject[0] = 0;
  *(_DWORD *)v15 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( (!cbOutput || a6) && a8 )
  {
    *a8 = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, L"Microsoft Primitive Provider", dwFlags);
    if ( Property >= 0 )
    {
      pcbResult = 4;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        v13 = *(_DWORD *)pbOutput;
        *a8 = *(_DWORD *)pbOutput;
        if ( cbOutput )
        {
          if ( cbOutput >= v13 )
          {
            pcbResult = 4;
            Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", v15, 4u, &pcbResult, 0);
            if ( Property >= 0 )
            {
              if ( (unsigned int)TpmApiCallbackAlloc(-1, *(unsigned int *)v15, pbHashObject) )
              {
                Property = -1073741801;
              }
              else
              {
                memset(pbHashObject[0], 0, *(unsigned int *)v15);
                Property = BCryptCreateHash(phAlgorithm, &phHash, pbHashObject[0], *(ULONG *)v15, pbSecret, cbSecret, 0);
                if ( Property >= 0 )
                {
                  Property = BCryptHashData(phHash, pbInput, cbInput, 0);
                  if ( Property >= 0 )
                    Property = BCryptFinishHash(phHash, a6, cbOutput, 0);
                }
              }
            }
          }
          else
          {
            Property = -1073741789;
          }
        }
      }
    }
    if ( phHash )
      BCryptDestroyHash(phHash);
  }
  else
  {
    Property = -1073741811;
  }
  TpmApiCallbackFree(-1, *(unsigned int *)v15, pbHashObject[0]);
  *(_DWORD *)v15 = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400329b0  push    rbp
0x1400329b2  push    rbx
0x1400329b3  push    rsi
0x1400329b4  push    r12
0x1400329b6  push    r13
0x1400329b8  push    r15
0x1400329ba  mov     rbp, rsp
0x1400329bd  sub     rsp, 78h
0x1400329c1  cmp     [rbp+cbOutput], 0
0x1400329c5  mov     r13, r9
0x1400329c8  mov     r15d, r8d
0x1400329cb  mov     [rbp+phAlgorithm], 0
0x1400329d3  mov     r12, rdx
0x1400329d6  mov     [rbp+phHash], 0
0x1400329de  mov     [rbp+pbHashObject], 0
0x1400329e6  mov     dword ptr [rbp+var_38], 0
0x1400329ed  mov     dword ptr [rbp+pbOutput], 0
0x1400329f4  mov     [rbp+var_34], 0
0x1400329fb  jz      short loc_140032A04
0x1400329fd  cmp     [rbp+arg_28], 0
0x140032a02  jz      short loc_140032A0D
0x140032a04  mov     rsi, [rbp+arg_38]
0x140032a08  test    rsi, rsi
0x140032a0b  jnz     short loc_140032A17
0x140032a0d  mov     ebx, 0C000000Dh
0x140032a12  jmp     loc_140032B98
0x140032a17  mov     r9d, [rbp+dwFlags]; dwFlags
0x140032a1b  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140032a22  mov     rdx, rcx; pszAlgId
0x140032a25  mov     dword ptr [rsi], 0
0x140032a2b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140032a2f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140032a36  nop     dword ptr [rax+rax+00h]
0x140032a3b  mov     ebx, eax
0x140032a3d  test    eax, eax
0x140032a3f  js      loc_140032B83
0x140032a45  mov     ecx, 4
0x140032a4a  mov     [rsp+78h+cbSecret], 0; dwFlags
0x140032a52  mov     [rbp+var_34], ecx
0x140032a55  lea     rax, [rbp+var_34]
0x140032a59  mov     r9d, ecx; cbOutput
0x140032a5c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x140032a61  mov     rcx, [rbp+phAlgorithm]; hObject
0x140032a65  lea     r8, [rbp+pbOutput]; pbOutput
0x140032a69  lea     rdx, aHashdigestleng; "HashDigestLength"
0x140032a70  call    cs:__imp_BCryptGetProperty
0x140032a77  nop     dword ptr [rax+rax+00h]
0x140032a7c  mov     ebx, eax
0x140032a7e  test    eax, eax
0x140032a80  js      loc_140032B83
0x140032a86  cmp     [rbp+cbOutput], 0
0x140032a8a  mov     eax, dword ptr [rbp+pbOutput]
0x140032a8d  mov     [rsi], eax
0x140032a8f  jz      loc_140032B83
0x140032a95  cmp     [rbp+cbOutput], eax
0x140032a98  jnb     short loc_140032AA4
0x140032a9a  mov     ebx, 0C0000023h
0x140032a9f  jmp     loc_140032B83
0x140032aa4  mov     rcx, [rbp+phAlgorithm]; hObject
0x140032aa8  lea     rax, [rbp+var_34]
0x140032aac  mov     r9d, 4; cbOutput
0x140032ab2  mov     [rsp+78h+cbSecret], 0; dwFlags
0x140032aba  lea     r8, [rbp+var_38]; pbOutput
0x140032abe  mov     [rbp+var_34], r9d
0x140032ac2  lea     rdx, pszProperty; "ObjectLength"
0x140032ac9  mov     [rsp+78h+pcbResult], rax; pcbResult
0x140032ace  call    cs:__imp_BCryptGetProperty
0x140032ad5  nop     dword ptr [rax+rax+00h]
0x140032ada  mov     ebx, eax
0x140032adc  test    eax, eax
0x140032ade  js      loc_140032B83
0x140032ae4  mov     edx, dword ptr [rbp+var_38]
0x140032ae7  lea     r8, [rbp+pbHashObject]
0x140032aeb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140032aef  call    TpmApiCallbackAlloc
0x140032af4  test    eax, eax
0x140032af6  jz      short loc_140032B02
0x140032af8  mov     ebx, 0C0000017h
0x140032afd  jmp     loc_140032B83
0x140032b02  mov     r8d, dword ptr [rbp+var_38]; Size
0x140032b06  xor     edx, edx; Val
0x140032b08  mov     rcx, [rbp+pbHashObject]; void *
0x140032b0c  call    memset
0x140032b11  mov     eax, [rbp+arg_20]
0x140032b14  lea     rdx, [rbp+phHash]; phHash
0x140032b18  mov     r9d, dword ptr [rbp+var_38]; cbHashObject
0x140032b1c  mov     r8, [rbp+pbHashObject]; pbHashObject
0x140032b20  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140032b24  mov     [rsp+78h+var_48], 0; dwFlags
0x140032b2c  mov     [rsp+78h+cbSecret], eax; cbSecret
0x140032b30  mov     [rsp+78h+pcbResult], r13; pbSecret
0x140032b35  call    cs:__imp_BCryptCreateHash
0x140032b3c  nop     dword ptr [rax+rax+00h]
0x140032b41  mov     ebx, eax
0x140032b43  test    eax, eax
0x140032b45  js      short loc_140032B83
0x140032b47  mov     rcx, [rbp+phHash]; hHash
0x140032b4b  xor     r9d, r9d; dwFlags
0x140032b4e  mov     r8d, r15d; cbInput
0x140032b51  mov     rdx, r12; pbInput
0x140032b54  call    cs:__imp_BCryptHashData
0x140032b5b  nop     dword ptr [rax+rax+00h]
0x140032b60  mov     ebx, eax
0x140032b62  test    eax, eax
0x140032b64  js      short loc_140032B83
0x140032b66  mov     r8d, [rbp+cbOutput]; cbOutput
0x140032b6a  xor     r9d, r9d; dwFlags
0x140032b6d  mov     rdx, [rbp+arg_28]; pbOutput
0x140032b71  mov     rcx, [rbp+phHash]; hHash
0x140032b75  call    cs:__imp_BCryptFinishHash
0x140032b7c  nop     dword ptr [rax+rax+00h]
0x140032b81  mov     ebx, eax
0x140032b83  mov     rcx, [rbp+phHash]; hHash
0x140032b87  test    rcx, rcx
0x140032b8a  jz      short loc_140032B98
0x140032b8c  call    cs:__imp_BCryptDestroyHash
0x140032b93  nop     dword ptr [rax+rax+00h]
0x140032b98  mov     r8, [rbp+pbHashObject]
0x140032b9c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140032ba0  mov     edx, dword ptr [rbp+var_38]
0x140032ba3  call    TpmApiCallbackFree
0x140032ba8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140032bac  mov     dword ptr [rbp+var_38], 0
0x140032bb3  test    rcx, rcx
0x140032bb6  jz      short loc_140032BC6
0x140032bb8  xor     edx, edx; dwFlags
0x140032bba  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140032bc1  nop     dword ptr [rax+rax+00h]
0x140032bc6  mov     eax, ebx
0x140032bc8  add     rsp, 78h
0x140032bcc  pop     r15
0x140032bce  pop     r13
0x140032bd0  pop     r12
0x140032bd2  pop     rsi
0x140032bd3  pop     rbx
0x140032bd4  pop     rbp
0x140032bd5  retn
```
