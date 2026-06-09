# DafClass5GuidFromBlob(_GUID const &,void *,ulong,_GUID *)

- ea: `0x180014a84`
- end: `0x180014cd9`
- name: `?DafClass5GuidFromBlob@@YAJAEBU_GUID@@PEAXKPEAU1@@Z`
- size: `597`
- prototype: `int(const struct _GUID *, void *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014ce0`

## callees

- `0x180004f0c`
- `0x180004f18`
- `0x180005320`
- `0x180014a84`
- `0x18001503c`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180014c76`
- `bcrypt!BCryptDestroyHash` at `0x180014c76`
- `bcrypt!BCryptCreateHash` at `0x180014b6d`
- `bcrypt!BCryptCreateHash` at `0x180014b6d`
- `bcrypt!BCryptHashData` at `0x180014b95`
- `bcrypt!BCryptHashData` at `0x180014bae`
- `bcrypt!BCryptHashData` at `0x180014b95`
- `bcrypt!BCryptHashData` at `0x180014bae`
- `bcrypt!BCryptGetProperty` at `0x180014b2f`
- `bcrypt!BCryptGetProperty` at `0x180014bda`
- `bcrypt!BCryptGetProperty` at `0x180014b2f`
- `bcrypt!BCryptGetProperty` at `0x180014bda`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180014afb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180014afb`
- `bcrypt!BCryptFinishHash` at `0x180014c0f`
- `bcrypt!BCryptFinishHash` at `0x180014c0f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180014c87`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180014c87`

## pseudocode

```c
__int64 __fastcall DafClass5GuidFromBlob(const struct _GUID *a1, UCHAR *a2, ULONG a3, struct _GUID *a4)
{
  UCHAR *v4; // rsi
  UCHAR *v5; // rdi
  size_t v9; // r15
  unsigned __int64 v10; // rdx
  NTSTATUS Property; // ebx
  bool v12; // sf
  unsigned __int16 Data3; // ax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  UCHAR pbInput[4]; // [rsp+58h] [rbp-18h] BYREF
  int v21; // [rsp+5Ch] [rbp-14h]
  unsigned __int64 v22; // [rsp+60h] [rbp-10h]

  phAlgorithm = 0;
  phHash = 0;
  v4 = 0;
  *(_DWORD *)pbOutput = 0;
  v5 = 0;
  pcbResult = 0;
  *a4 = 0;
  *(_DWORD *)pbInput = 507857385;
  v21 = 1133792159;
  v22 = 0x973B90D6C14C80AAuLL;
  v9 = 16;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v4 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
      if ( !v4 )
      {
LABEL_10:
        Property = -1073741801;
        goto LABEL_17;
      }
      Property = BCryptCreateHash(phAlgorithm, &phHash, v4, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property >= 0 )
      {
        *(_DWORD *)pbInput = -381074146;
        v21 = -1807507637;
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( Property >= 0 )
          Property = BCryptHashData(phHash, a2, a3, 0);
      }
    }
  }
  v12 = Property < 0;
  if ( Property )
  {
LABEL_12:
    if ( v12 )
      goto LABEL_17;
    goto LABEL_13;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v12 = Property < 0;
    goto LABEL_12;
  }
  v5 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
  if ( !v5 )
    goto LABEL_10;
LABEL_13:
  Property = BCryptFinishHash(phHash, v5, *(ULONG *)pbOutput, 0);
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput < 0x10u )
      v9 = *(unsigned int *)pbOutput;
    memcpy_0(a4, v5, v9);
    a4->Data1 = _byteswap_ulong(a4->Data1);
    a4->Data2 = __ROR2__(a4->Data2, 8);
    Data3 = a4->Data3;
    a4->Data4[0] &= 0x3Fu;
    a4->Data4[0] |= 0x80u;
    a4->Data3 = __ROR2__(Data3, 8) & 0xFFF | 0x5000;
  }
LABEL_17:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v4 )
    operator delete(v4, v10);
  if ( v5 )
    operator delete(v5, v10);
  if ( Property < 0 )
    return (unsigned int)(Property | 0x10000000);
  else
    return 0;
}

```

## disassembly

```asm
0x180014a84  mov     [rsp-38h+arg_0], rbx
0x180014a89  push    rbp
0x180014a8a  push    rsi
0x180014a8b  push    rdi
0x180014a8c  push    r12
0x180014a8e  push    r13
0x180014a90  push    r14
0x180014a92  push    r15
0x180014a94  mov     rbp, rsp
0x180014a97  sub     rsp, 70h
0x180014a9b  mov     rax, cs:__security_cookie
0x180014aa2  xor     rax, rsp
0x180014aa5  mov     [rbp+var_8], rax
0x180014aa9  mov     rax, cs:qword_18001AF50
0x180014ab0  xor     ecx, ecx
0x180014ab2  xorps   xmm0, xmm0
0x180014ab5  mov     [rbp+phAlgorithm], rcx
0x180014ab9  mov     [rbp+phHash], rcx
0x180014abd  mov     esi, ecx
0x180014abf  mov     dword ptr [rbp+pbOutput], ecx
0x180014ac2  mov     edi, ecx
0x180014ac4  mov     [rbp+var_2C], ecx
0x180014ac7  mov     r14, r9
0x180014aca  movups  xmmword ptr [r9], xmm0
0x180014ace  mov     r13d, r8d
0x180014ad1  mov     dword ptr [rbp+pbInput], 1E4549E9h
0x180014ad8  mov     r12, rdx
0x180014adb  mov     [rbp+var_14], 43944B9Fh
0x180014ae2  xor     r9d, r9d; dwFlags
0x180014ae5  mov     [rbp+var_10], rax
0x180014ae9  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180014aed  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180014af4  lea     rdx, pszAlgId; "SHA1"
0x180014afb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180014b01  lea     r15d, [rdi+10h]
0x180014b05  mov     ebx, eax
0x180014b07  test    eax, eax
0x180014b09  js      loc_180014BB6
0x180014b0f  mov     rcx, [rbp+phAlgorithm]; hObject
0x180014b13  lea     rax, [rbp+var_2C]
0x180014b17  mov     [rsp+70h+dwFlags], esi; dwFlags
0x180014b1b  lea     r9d, [rdi+4]; cbOutput
0x180014b1f  lea     r8, [rbp+pbOutput]; pbOutput
0x180014b23  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180014b28  lea     rdx, pszProperty; "ObjectLength"
0x180014b2f  call    cs:__imp_BCryptGetProperty
0x180014b35  mov     ebx, eax
0x180014b37  test    eax, eax
0x180014b39  js      short loc_180014BB6
0x180014b3b  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x180014b3e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014b43  mov     rsi, rax
0x180014b46  xor     eax, eax
0x180014b48  test    rsi, rsi
0x180014b4b  jz      loc_180014BF6
0x180014b51  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180014b55  lea     rdx, [rbp+phHash]; phHash
0x180014b59  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180014b5d  mov     r8, rsi; pbHashObject
0x180014b60  mov     [rsp+70h+var_40], eax; dwFlags
0x180014b64  mov     [rsp+70h+dwFlags], eax; cbSecret
0x180014b68  mov     [rsp+70h+pcbResult], rax; pbSecret
0x180014b6d  call    cs:__imp_BCryptCreateHash
0x180014b73  mov     ebx, eax
0x180014b75  test    eax, eax
0x180014b77  js      short loc_180014BB6
0x180014b79  mov     rcx, [rbp+phHash]; hHash
0x180014b7d  lea     rdx, [rbp+pbInput]; pbInput
0x180014b81  xor     r9d, r9d; dwFlags
0x180014b84  mov     dword ptr [rbp+pbInput], 0E949451Eh
0x180014b8b  mov     r8d, r15d; cbInput
0x180014b8e  mov     [rbp+var_14], 94439F4Bh
0x180014b95  call    cs:__imp_BCryptHashData
0x180014b9b  mov     ebx, eax
0x180014b9d  test    eax, eax
0x180014b9f  js      short loc_180014BB6
0x180014ba1  mov     rcx, [rbp+phHash]; hHash
0x180014ba5  xor     r9d, r9d; dwFlags
0x180014ba8  mov     r8d, r13d; cbInput
0x180014bab  mov     rdx, r12; pbInput
0x180014bae  call    cs:__imp_BCryptHashData
0x180014bb4  mov     ebx, eax
0x180014bb6  test    ebx, ebx
0x180014bb8  jnz     short loc_180014BFF
0x180014bba  mov     rcx, [rbp+phAlgorithm]; hObject
0x180014bbe  lea     rax, [rbp+var_2C]
0x180014bc2  mov     [rsp+70h+dwFlags], edi; dwFlags
0x180014bc6  lea     r9d, [rbx+4]; cbOutput
0x180014bca  lea     r8, [rbp+pbOutput]; pbOutput
0x180014bce  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180014bd3  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180014bda  call    cs:__imp_BCryptGetProperty
0x180014be0  mov     ebx, eax
0x180014be2  test    eax, eax
0x180014be4  jnz     short loc_180014BFD
0x180014be6  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x180014be9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014bee  mov     rdi, rax
0x180014bf1  test    rax, rax
0x180014bf4  jnz     short loc_180014C01
0x180014bf6  mov     ebx, 0C0000017h
0x180014bfb  jmp     short loc_180014C6D
0x180014bfd  test    ebx, ebx
0x180014bff  js      short loc_180014C6D
0x180014c01  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x180014c05  xor     r9d, r9d; dwFlags
0x180014c08  mov     rcx, [rbp+phHash]; hHash
0x180014c0c  mov     rdx, rdi; pbOutput
0x180014c0f  call    cs:__imp_BCryptFinishHash
0x180014c15  mov     ebx, eax
0x180014c17  test    eax, eax
0x180014c19  js      short loc_180014C6D
0x180014c1b  cmp     dword ptr [rbp+pbOutput], r15d
0x180014c1f  jnb     short loc_180014C25
0x180014c21  mov     r15d, dword ptr [rbp+pbOutput]
0x180014c25  mov     r8, r15; Size
0x180014c28  mov     rdx, rdi; Src
0x180014c2b  mov     rcx, r14; void *
0x180014c2e  call    memcpy_0
0x180014c33  mov     eax, [r14]
0x180014c36  mov     ecx, 0FFFh
0x180014c3b  bswap   eax
0x180014c3d  mov     [r14], eax
0x180014c40  movzx   eax, word ptr [r14+4]
0x180014c45  ror     ax, 8
0x180014c49  mov     [r14+4], ax
0x180014c4e  movzx   eax, word ptr [r14+6]
0x180014c53  and     byte ptr [r14+8], 3Fh
0x180014c58  ror     ax, 8
0x180014c5c  and     ax, cx
0x180014c5f  or      ax, 5000h
0x180014c63  or      byte ptr [r14+8], 80h
0x180014c68  mov     [r14+6], ax
0x180014c6d  mov     rcx, [rbp+phHash]; hHash
0x180014c71  test    rcx, rcx
0x180014c74  jz      short loc_180014C7C
0x180014c76  call    cs:__imp_BCryptDestroyHash
0x180014c7c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180014c80  test    rcx, rcx
0x180014c83  jz      short loc_180014C8D
0x180014c85  xor     edx, edx; dwFlags
0x180014c87  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180014c8d  test    rsi, rsi
0x180014c90  jz      short loc_180014C9A
0x180014c92  mov     rcx, rsi; void *
0x180014c95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014c9a  test    rdi, rdi
0x180014c9d  jz      short loc_180014CA7
0x180014c9f  mov     rcx, rdi; void *
0x180014ca2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014ca7  test    ebx, ebx
0x180014ca9  js      short loc_180014CAF
0x180014cab  xor     ebx, ebx
0x180014cad  jmp     short loc_180014CB3
0x180014caf  bts     ebx, 1Ch
0x180014cb3  mov     eax, ebx
0x180014cb5  mov     rcx, [rbp+var_8]
0x180014cb9  xor     rcx, rsp; StackCookie
0x180014cbc  call    __security_check_cookie
0x180014cc1  mov     rbx, [rsp+70h+arg_0]
0x180014cc9  add     rsp, 70h
0x180014ccd  pop     r15
0x180014ccf  pop     r14
0x180014cd1  pop     r13
0x180014cd3  pop     r12
0x180014cd5  pop     rdi
0x180014cd6  pop     rsi
0x180014cd7  pop     rbp
0x180014cd8  retn
```
