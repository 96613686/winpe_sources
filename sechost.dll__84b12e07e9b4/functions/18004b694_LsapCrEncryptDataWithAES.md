# LsapCrEncryptDataWithAES

- ea: `0x18004b694`
- end: `0x18004b8d2`
- name: `LsapCrEncryptDataWithAES`
- size: `574`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004bf34`

## callees

- `0x18004b694`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18004b709`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18004b709`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b80c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b80c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b883`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b883`
- `bcrypt!BCryptDestroyKey` at `0x18004b892`
- `bcrypt!BCryptDestroyKey` at `0x18004b892`
- `bcrypt!BCryptSetProperty` at `0x18004b784`
- `bcrypt!BCryptSetProperty` at `0x18004b784`
- `bcrypt!BCryptEncrypt` at `0x18004b7fa`
- `bcrypt!BCryptEncrypt` at `0x18004b85c`
- `bcrypt!BCryptEncrypt` at `0x18004b7fa`
- `bcrypt!BCryptEncrypt` at `0x18004b85c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004b7b6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004b7b6`
- `bcrypt!BCryptGetProperty` at `0x18004b750`
- `bcrypt!BCryptGetProperty` at `0x18004b750`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004b720`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004b720`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004b8a3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004b8a3`

## pseudocode

```c
__int64 __fastcall LsapCrEncryptDataWithAES(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbIV,
        __int64 a4,
        UCHAR *a5,
        ULONG cbSecret,
        UCHAR **a7,
        ULONG *a8)
{
  UCHAR *v11; // rdi
  NTSTATUS Property; // ebx
  ULONG cbOutput; // [rsp+50h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-45h] BYREF
  ULONG v16; // [rsp+58h] [rbp-41h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-29h] BYREF
  PUCHAR pbSecret; // [rsp+78h] [rbp-21h]
  __int128 Destination; // [rsp+80h] [rbp-19h] BYREF

  pbSecret = a5;
  *a8 = 0;
  v11 = 0;
  phAlgorithm = 0;
  phKey = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 16;
  cbOutput = 0;
  v16 = 0;
  Destination = 0;
  *a7 = 0;
  memcpy_s(&Destination, 0x10u, pbIV, 0x10u);
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 && *(_DWORD *)pbOutput == 16 )
    {
      Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptEncrypt(phKey, pbInput, cbInput, 0, pbIV, 0x10u, 0, 0, &cbOutput, 1u);
          if ( Property >= 0 )
          {
            v11 = (UCHAR *)LocalAlloc(0x40u, cbOutput);
            if ( v11 )
            {
              Property = BCryptEncrypt(phKey, pbInput, cbInput, 0, (PUCHAR)&Destination, 0x10u, v11, cbOutput, &v16, 1u);
              if ( Property >= 0 )
              {
                if ( v16 <= cbOutput )
                {
                  *a8 = v16;
                  *a7 = v11;
                  v11 = 0;
                }
                else
                {
                  Property = -1073741823;
                }
              }
            }
            else
            {
              Property = -1073741670;
            }
          }
        }
      }
    }
  }
  LocalFree(v11);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18004b694  mov     [rsp-8+arg_18], rbx
0x18004b699  push    rbp
0x18004b69a  push    rsi
0x18004b69b  push    rdi
0x18004b69c  push    r12
0x18004b69e  push    r13
0x18004b6a0  push    r14
0x18004b6a2  push    r15
0x18004b6a4  lea     rbp, [rsp-7]
0x18004b6a9  sub     rsp, 0A0h
0x18004b6b0  mov     rax, cs:__security_cookie
0x18004b6b7  xor     rax, rsp
0x18004b6ba  mov     [rbp+37h+var_40], rax
0x18004b6be  mov     rax, [rbp+37h+arg_20]
0x18004b6c2  mov     rsi, rcx
0x18004b6c5  mov     r12, [rbp+37h+arg_38]
0x18004b6c9  mov     r14d, edx
0x18004b6cc  mov     r15, [rbp+37h+arg_30]
0x18004b6d0  xorps   xmm0, xmm0
0x18004b6d3  mov     [rbp+37h+pbSecret], rax
0x18004b6d7  mov     r13, r8
0x18004b6da  xor     eax, eax
0x18004b6dc  mov     [r12], eax
0x18004b6e0  mov     edi, eax
0x18004b6e2  mov     [rbp+37h+phAlgorithm], rax
0x18004b6e6  mov     [rbp+37h+phKey], rax
0x18004b6ea  lea     ecx, [rax+10h]
0x18004b6ed  mov     [rbp+37h+var_60], eax
0x18004b6f0  mov     dword ptr [rbp+37h+pbOutput], ecx
0x18004b6f3  mov     r9d, ecx; SourceSize
0x18004b6f6  mov     edx, ecx; DestinationSize
0x18004b6f8  mov     [rbp+37h+var_80], eax
0x18004b6fb  lea     rcx, [rbp+37h+Destination]; Destination
0x18004b6ff  mov     [rbp+37h+var_78], eax
0x18004b702  movups  [rbp+37h+Destination], xmm0
0x18004b706  mov     [r15], rax
0x18004b709  call    cs:__imp_memcpy_s
0x18004b70f  xor     r9d, r9d; dwFlags
0x18004b712  lea     rdx, pszAlgId; "AES"
0x18004b719  xor     r8d, r8d; pszImplementation
0x18004b71c  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x18004b720  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004b726  mov     ebx, eax
0x18004b728  test    eax, eax
0x18004b72a  js      loc_18004B880
0x18004b730  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18004b734  lea     rax, [rbp+37h+var_60]
0x18004b738  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x18004b73c  lea     r9d, [rdi+4]; cbOutput
0x18004b740  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x18004b744  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x18004b749  lea     rdx, pszProperty; "BlockLength"
0x18004b750  call    cs:__imp_BCryptGetProperty
0x18004b756  mov     ebx, eax
0x18004b758  test    eax, eax
0x18004b75a  js      loc_18004B880
0x18004b760  cmp     dword ptr [rbp+37h+pbOutput], 10h
0x18004b764  jnz     loc_18004B880
0x18004b76a  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18004b76e  lea     r9d, [rdi+20h]; cbInput
0x18004b772  lea     r8, pbInput; "ChainingModeCBC"
0x18004b779  mov     dword ptr [rsp+0D0h+pcbResult], edi; dwFlags
0x18004b77d  lea     rdx, aChainingmode; "ChainingMode"
0x18004b784  call    cs:__imp_BCryptSetProperty
0x18004b78a  mov     ebx, eax
0x18004b78c  test    eax, eax
0x18004b78e  js      loc_18004B880
0x18004b794  mov     eax, [rbp+37h+cbSecret]
0x18004b797  lea     rdx, [rbp+37h+phKey]; phKey
0x18004b79b  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18004b79f  xor     r9d, r9d; cbKeyObject
0x18004b7a2  mov     [rsp+0D0h+var_A0], edi; dwFlags
0x18004b7a6  xor     r8d, r8d; pbKeyObject
0x18004b7a9  mov     [rsp+0D0h+dwFlags], eax; cbSecret
0x18004b7ad  mov     rax, [rbp+37h+pbSecret]
0x18004b7b1  mov     [rsp+0D0h+pcbResult], rax; pbSecret
0x18004b7b6  call    cs:__imp_BCryptGenerateSymmetricKey
0x18004b7bc  mov     ebx, eax
0x18004b7be  test    eax, eax
0x18004b7c0  js      loc_18004B880
0x18004b7c6  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b7ca  lea     rax, [rbp+37h+var_80]
0x18004b7ce  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18004b7d6  xor     r9d, r9d; pPaddingInfo
0x18004b7d9  mov     [rsp+0D0h+var_90], rax; pcbResult
0x18004b7de  mov     r8d, r14d; cbInput
0x18004b7e1  mov     [rsp+0D0h+cbOutput], edi; cbOutput
0x18004b7e5  mov     rdx, rsi; pbInput
0x18004b7e8  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x18004b7ed  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x18004b7f5  mov     [rsp+0D0h+pcbResult], r13; pbIV
0x18004b7fa  call    cs:__imp_BCryptEncrypt
0x18004b800  mov     ebx, eax
0x18004b802  test    eax, eax
0x18004b804  js      short loc_18004B880
0x18004b806  mov     edx, [rbp+37h+var_80]; uBytes
0x18004b809  lea     ecx, [rdi+40h]; uFlags
0x18004b80c  call    cs:__imp_LocalAlloc
0x18004b812  mov     rdi, rax
0x18004b815  test    rax, rax
0x18004b818  jnz     short loc_18004B821
0x18004b81a  mov     ebx, 0C000009Ah
0x18004b81f  jmp     short loc_18004B880
0x18004b821  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b825  lea     rax, [rbp+37h+var_78]
0x18004b829  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18004b831  xor     r9d, r9d; pPaddingInfo
0x18004b834  mov     [rsp+0D0h+var_90], rax; pcbResult
0x18004b839  mov     r8d, r14d; cbInput
0x18004b83c  mov     eax, [rbp+37h+var_80]
0x18004b83f  mov     rdx, rsi; pbInput
0x18004b842  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x18004b846  lea     rax, [rbp+37h+Destination]
0x18004b84a  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x18004b84f  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x18004b857  mov     [rsp+0D0h+pcbResult], rax; pbIV
0x18004b85c  call    cs:__imp_BCryptEncrypt
0x18004b862  mov     ebx, eax
0x18004b864  test    eax, eax
0x18004b866  js      short loc_18004B880
0x18004b868  mov     eax, [rbp+37h+var_78]
0x18004b86b  cmp     eax, [rbp+37h+var_80]
0x18004b86e  jbe     short loc_18004B877
0x18004b870  mov     ebx, 0C0000001h
0x18004b875  jmp     short loc_18004B880
0x18004b877  mov     [r12], eax
0x18004b87b  mov     [r15], rdi
0x18004b87e  xor     edi, edi
0x18004b880  mov     rcx, rdi; hMem
0x18004b883  call    cs:__imp_LocalFree
0x18004b889  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b88d  test    rcx, rcx
0x18004b890  jz      short loc_18004B898
0x18004b892  call    cs:__imp_BCryptDestroyKey
0x18004b898  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18004b89c  test    rcx, rcx
0x18004b89f  jz      short loc_18004B8A9
0x18004b8a1  xor     edx, edx; dwFlags
0x18004b8a3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004b8a9  mov     eax, ebx
0x18004b8ab  mov     rcx, [rbp+37h+var_40]
0x18004b8af  xor     rcx, rsp; StackCookie
0x18004b8b2  call    __security_check_cookie
0x18004b8b7  mov     rbx, [rsp+0D0h+arg_18]
0x18004b8bf  add     rsp, 0A0h
0x18004b8c6  pop     r15
0x18004b8c8  pop     r14
0x18004b8ca  pop     r13
0x18004b8cc  pop     r12
0x18004b8ce  pop     rdi
0x18004b8cf  pop     rsi
0x18004b8d0  pop     rbp
0x18004b8d1  retn
```
