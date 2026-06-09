# LsapCrGenerateHMACWithSHA512

- ea: `0x18004b8d8`
- end: `0x18004bac6`
- name: `LsapCrGenerateHMACWithSHA512`
- size: `494`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004bb8c`
- `0x18004bf34`

## callees

- `0x18004b8d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b971`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b9cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b971`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b9cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004baa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ba81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004baa6`
- `bcrypt!BCryptCreateHash` at `0x18004b9fe`
- `bcrypt!BCryptCreateHash` at `0x18004b9fe`
- `bcrypt!BCryptGetProperty` at `0x18004b951`
- `bcrypt!BCryptGetProperty` at `0x18004b9aa`
- `bcrypt!BCryptGetProperty` at `0x18004b951`
- `bcrypt!BCryptGetProperty` at `0x18004b9aa`
- `bcrypt!BCryptFinishHash` at `0x18004ba33`
- `bcrypt!BCryptFinishHash` at `0x18004ba33`
- `bcrypt!BCryptDestroyHash` at `0x18004ba5c`
- `bcrypt!BCryptDestroyHash` at `0x18004ba5c`
- `bcrypt!BCryptHashData` at `0x18004ba19`
- `bcrypt!BCryptHashData` at `0x18004ba19`

## pseudocode

```c
__int64 __fastcall LsapCrGenerateHMACWithSHA512(
        BCRYPT_ALG_HANDLE hAlgorithm,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        UCHAR **a6,
        _DWORD *a7)
{
  UCHAR *v7; // rsi
  UCHAR *v8; // rdi
  NTSTATUS Property; // ebx
  int v12; // eax
  __int64 v13; // rax
  UCHAR *v14; // rcx
  __int64 v15; // rax
  UCHAR *v16; // rcx
  UCHAR v18[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-1Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF

  v7 = 0;
  v8 = 0;
  phHash = 0;
  *a6 = 0;
  *a7 = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v18 = 0;
  pcbResult = 0;
  if ( !cbInput || !a3 )
    goto LABEL_14;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_15;
  if ( pcbResult != 4 )
    goto LABEL_14;
  v7 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
  if ( !v7 )
  {
LABEL_6:
    Property = -1073741670;
    goto LABEL_15;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v18, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    if ( pcbResult == 4 )
    {
      v8 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v18);
      if ( !v8 )
        goto LABEL_6;
      Property = BCryptCreateHash(hAlgorithm, &phHash, v7, *(ULONG *)pbOutput, a2, a3, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, a4, cbInput, 0);
        if ( Property >= 0 )
        {
          Property = BCryptFinishHash(phHash, v8, *(ULONG *)v18, 0);
          if ( Property >= 0 )
          {
            v12 = *(_DWORD *)v18;
            *a6 = v8;
            v8 = 0;
            *a7 = v12;
          }
        }
      }
      goto LABEL_15;
    }
LABEL_14:
    Property = -1073741811;
  }
LABEL_15:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v7 )
  {
    v13 = *(unsigned int *)pbOutput;
    v14 = v7;
    if ( *(_DWORD *)pbOutput )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    LocalFree(v7);
  }
  if ( v8 )
  {
    v15 = *(unsigned int *)v18;
    v16 = v8;
    if ( *(_DWORD *)v18 )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    LocalFree(v8);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18004b8d8  mov     rax, rsp
0x18004b8db  mov     [rax+8], rbx
0x18004b8df  mov     [rax+20h], r9
0x18004b8e3  mov     [rax+10h], rdx
0x18004b8e7  push    rbp
0x18004b8e8  push    rsi
0x18004b8e9  push    rdi
0x18004b8ea  push    r12
0x18004b8ec  push    r13
0x18004b8ee  push    r14
0x18004b8f0  push    r15
0x18004b8f2  mov     rbp, rsp
0x18004b8f5  sub     rsp, 60h
0x18004b8f9  mov     r12, [rbp+arg_28]
0x18004b8fd  xor     esi, esi
0x18004b8ff  mov     r13, [rbp+arg_30]
0x18004b903  xor     edi, edi
0x18004b905  mov     r14d, r8d
0x18004b908  mov     r15, rcx
0x18004b90b  mov     [rbp+phHash], 0
0x18004b913  mov     [r12], rsi
0x18004b917  mov     [r13+0], esi
0x18004b91b  mov     dword ptr [rbp+pbOutput], esi
0x18004b91e  mov     dword ptr [rbp+var_20], esi
0x18004b921  mov     [rbp+var_1C], esi
0x18004b924  cmp     [rbp+cbInput], esi
0x18004b927  jz      loc_18004BA4E
0x18004b92d  test    r8d, r8d
0x18004b930  jz      loc_18004BA4E
0x18004b936  mov     [rax-70h], esi
0x18004b939  lea     r9d, [rsi+4]; cbOutput
0x18004b93d  lea     rax, [rbp+var_1C]
0x18004b941  lea     r8, [rbp+pbOutput]; pbOutput
0x18004b945  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18004b94a  lea     rdx, aObjectlength; "ObjectLength"
0x18004b951  call    cs:__imp_BCryptGetProperty
0x18004b957  mov     ebx, eax
0x18004b959  test    eax, eax
0x18004b95b  js      loc_18004BA53
0x18004b961  cmp     [rbp+var_1C], 4
0x18004b965  jnz     loc_18004BA4E
0x18004b96b  mov     edx, dword ptr [rbp+pbOutput]; uBytes
0x18004b96e  lea     ecx, [rsi+40h]; uFlags
0x18004b971  call    cs:__imp_LocalAlloc
0x18004b977  mov     rsi, rax
0x18004b97a  test    rax, rax
0x18004b97d  jnz     short loc_18004B989
0x18004b97f  mov     ebx, 0C000009Ah
0x18004b984  jmp     loc_18004BA53
0x18004b989  lea     rax, [rbp+var_1C]
0x18004b98d  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18004b991  mov     r9d, 4; cbOutput
0x18004b997  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18004b99c  lea     r8, [rbp+var_20]; pbOutput
0x18004b9a0  mov     rcx, r15; hObject
0x18004b9a3  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18004b9aa  call    cs:__imp_BCryptGetProperty
0x18004b9b0  mov     ebx, eax
0x18004b9b2  test    eax, eax
0x18004b9b4  js      loc_18004BA53
0x18004b9ba  cmp     [rbp+var_1C], 4
0x18004b9be  jnz     loc_18004BA4E
0x18004b9c4  mov     edx, dword ptr [rbp+var_20]; uBytes
0x18004b9c7  mov     ecx, 40h ; '@'; uFlags
0x18004b9cc  call    cs:__imp_LocalAlloc
0x18004b9d2  mov     rdi, rax
0x18004b9d5  test    rax, rax
0x18004b9d8  jz      short loc_18004B97F
0x18004b9da  mov     rax, [rbp+pbSecret]
0x18004b9de  lea     rdx, [rbp+phHash]; phHash
0x18004b9e2  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18004b9e6  mov     r8, rsi; pbHashObject
0x18004b9e9  mov     [rsp+60h+var_30], 0; dwFlags
0x18004b9f1  mov     rcx, r15; hAlgorithm
0x18004b9f4  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x18004b9f9  mov     [rsp+60h+pcbResult], rax; pbSecret
0x18004b9fe  call    cs:__imp_BCryptCreateHash
0x18004ba04  mov     ebx, eax
0x18004ba06  test    eax, eax
0x18004ba08  js      short loc_18004BA53
0x18004ba0a  mov     r8d, [rbp+cbInput]; cbInput
0x18004ba0e  xor     r9d, r9d; dwFlags
0x18004ba11  mov     rdx, [rbp+pbInput]; pbInput
0x18004ba15  mov     rcx, [rbp+phHash]; hHash
0x18004ba19  call    cs:__imp_BCryptHashData
0x18004ba1f  mov     ebx, eax
0x18004ba21  test    eax, eax
0x18004ba23  js      short loc_18004BA53
0x18004ba25  mov     r8d, dword ptr [rbp+var_20]; cbOutput
0x18004ba29  xor     r9d, r9d; dwFlags
0x18004ba2c  mov     rcx, [rbp+phHash]; hHash
0x18004ba30  mov     rdx, rdi; pbOutput
0x18004ba33  call    cs:__imp_BCryptFinishHash
0x18004ba39  mov     ebx, eax
0x18004ba3b  test    eax, eax
0x18004ba3d  js      short loc_18004BA53
0x18004ba3f  mov     eax, dword ptr [rbp+var_20]
0x18004ba42  mov     [r12], rdi
0x18004ba46  xor     edi, edi
0x18004ba48  mov     [r13+0], eax
0x18004ba4c  jmp     short loc_18004BA53
0x18004ba4e  mov     ebx, 0C000000Dh
0x18004ba53  mov     rcx, [rbp+phHash]; hHash
0x18004ba57  test    rcx, rcx
0x18004ba5a  jz      short loc_18004BA62
0x18004ba5c  call    cs:__imp_BCryptDestroyHash
0x18004ba62  test    rsi, rsi
0x18004ba65  jz      short loc_18004BA87
0x18004ba67  mov     eax, dword ptr [rbp+pbOutput]
0x18004ba6a  mov     rcx, rsi
0x18004ba6d  test    rax, rax
0x18004ba70  jz      short loc_18004BA7E
0x18004ba72  mov     byte ptr [rcx], 0
0x18004ba75  inc     rcx
0x18004ba78  sub     rax, 1
0x18004ba7c  jnz     short loc_18004BA72
0x18004ba7e  mov     rcx, rsi; hMem
0x18004ba81  call    cs:__imp_LocalFree
0x18004ba87  test    rdi, rdi
0x18004ba8a  jz      short loc_18004BAAC
0x18004ba8c  mov     eax, dword ptr [rbp+var_20]
0x18004ba8f  mov     rcx, rdi
0x18004ba92  test    rax, rax
0x18004ba95  jz      short loc_18004BAA3
0x18004ba97  mov     byte ptr [rcx], 0
0x18004ba9a  inc     rcx
0x18004ba9d  sub     rax, 1
0x18004baa1  jnz     short loc_18004BA97
0x18004baa3  mov     rcx, rdi; hMem
0x18004baa6  call    cs:__imp_LocalFree
0x18004baac  mov     eax, ebx
0x18004baae  mov     rbx, [rsp+60h+arg_0]
0x18004bab6  add     rsp, 60h
0x18004baba  pop     r15
0x18004babc  pop     r14
0x18004babe  pop     r13
0x18004bac0  pop     r12
0x18004bac2  pop     rdi
0x18004bac3  pop     rsi
0x18004bac4  pop     rbp
0x18004bac5  retn
```
