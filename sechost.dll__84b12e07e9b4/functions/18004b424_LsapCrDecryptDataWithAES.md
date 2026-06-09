# LsapCrDecryptDataWithAES

- ea: `0x18004b424`
- end: `0x18004b68b`
- name: `LsapCrDecryptDataWithAES`
- size: `615`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, PUCHAR pbSecret, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004bb8c`

## callees

- `0x18004b424`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18004b493`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18004b493`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b5b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b5b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b633`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b633`
- `bcrypt!BCryptDestroyKey` at `0x18004b642`
- `bcrypt!BCryptDestroyKey` at `0x18004b642`
- `bcrypt!BCryptSetProperty` at `0x18004b51a`
- `bcrypt!BCryptSetProperty` at `0x18004b51a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004b54c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18004b54c`
- `bcrypt!BCryptGetProperty` at `0x18004b4e0`
- `bcrypt!BCryptGetProperty` at `0x18004b4e0`
- `bcrypt!BCryptDecrypt` at `0x18004b598`
- `bcrypt!BCryptDecrypt` at `0x18004b600`
- `bcrypt!BCryptDecrypt` at `0x18004b598`
- `bcrypt!BCryptDecrypt` at `0x18004b600`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004b4aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004b4aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004b653`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004b653`

## pseudocode

```c
__int64 __fastcall LsapCrDecryptDataWithAES(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbIV,
        __int64 a4,
        PUCHAR pbSecret,
        ULONG cbSecret,
        UCHAR **a7,
        ULONG *a8)
{
  NTSTATUS Property; // ebx
  UCHAR *v12; // rdi
  __int64 v13; // rcx
  UCHAR *v14; // rax
  ULONG cbOutput; // [rsp+50h] [rbp-39h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-35h] BYREF
  ULONG v18; // [rsp+58h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-21h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-19h] BYREF
  __int128 Destination; // [rsp+78h] [rbp-11h] BYREF

  phAlgorithm = 0;
  *a8 = 0;
  *(_DWORD *)pbOutput = 16;
  phKey = 0;
  pcbResult = 0;
  cbOutput = 0;
  Destination = 0;
  v18 = 0;
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
          Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIV, 0x10u, 0, 0, &cbOutput, 1u);
          if ( Property >= 0 )
          {
            v12 = (UCHAR *)LocalAlloc(0x40u, cbOutput);
            if ( !v12 )
            {
              Property = -1073741670;
              goto LABEL_15;
            }
            Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, (PUCHAR)&Destination, 0x10u, v12, cbOutput, &v18, 1u);
            if ( Property >= 0 )
            {
              if ( v18 <= cbOutput )
              {
                *a8 = v18;
                *a7 = v12;
                goto LABEL_15;
              }
              Property = -1073741811;
            }
            v13 = cbOutput;
            v14 = v12;
            if ( cbOutput )
            {
              do
              {
                *v14++ = 0;
                --v13;
              }
              while ( v13 );
            }
            LocalFree(v12);
          }
        }
      }
    }
  }
LABEL_15:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18004b424  mov     [rsp-8+arg_18], rbx
0x18004b429  push    rbp
0x18004b42a  push    rsi
0x18004b42b  push    rdi
0x18004b42c  push    r12
0x18004b42e  push    r13
0x18004b430  push    r14
0x18004b432  push    r15
0x18004b434  lea     rbp, [rsp-7]
0x18004b439  sub     rsp, 90h
0x18004b440  mov     rax, cs:__security_cookie
0x18004b447  xor     rax, rsp
0x18004b44a  mov     [rbp+37h+var_38], rax
0x18004b44e  mov     r12, [rbp+37h+arg_38]
0x18004b452  xor     eax, eax
0x18004b454  mov     r15, [rbp+37h+arg_30]
0x18004b458  mov     rsi, rcx
0x18004b45b  mov     r13, [rbp+37h+pbSecret]
0x18004b45f  mov     r14d, edx
0x18004b462  xorps   xmm0, xmm0
0x18004b465  mov     [rbp+37h+phAlgorithm], rax
0x18004b469  lea     ecx, [rax+10h]
0x18004b46c  mov     [r12], eax
0x18004b470  mov     dword ptr [rbp+37h+pbOutput], ecx
0x18004b473  mov     r9d, ecx; SourceSize
0x18004b476  mov     edx, ecx; DestinationSize
0x18004b478  mov     [rbp+37h+phKey], rax
0x18004b47c  lea     rcx, [rbp+37h+Destination]; Destination
0x18004b480  mov     [rbp+37h+var_50], eax
0x18004b483  mov     rdi, r8
0x18004b486  mov     [rbp+37h+var_70], eax
0x18004b489  movups  [rbp+37h+Destination], xmm0
0x18004b48d  mov     [rbp+37h+var_68], eax
0x18004b490  mov     [r15], rax
0x18004b493  call    cs:__imp_memcpy_s
0x18004b499  xor     r9d, r9d; dwFlags
0x18004b49c  lea     rdx, pszAlgId; "AES"
0x18004b4a3  xor     r8d, r8d; pszImplementation
0x18004b4a6  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x18004b4aa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004b4b0  mov     ebx, eax
0x18004b4b2  test    eax, eax
0x18004b4b4  js      loc_18004B639
0x18004b4ba  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18004b4be  lea     rax, [rbp+37h+var_50]
0x18004b4c2  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18004b4ca  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x18004b4ce  mov     r9d, 4; cbOutput
0x18004b4d4  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18004b4d9  lea     rdx, pszProperty; "BlockLength"
0x18004b4e0  call    cs:__imp_BCryptGetProperty
0x18004b4e6  mov     ebx, eax
0x18004b4e8  test    eax, eax
0x18004b4ea  js      loc_18004B639
0x18004b4f0  cmp     dword ptr [rbp+37h+pbOutput], 10h
0x18004b4f4  jnz     loc_18004B639
0x18004b4fa  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18004b4fe  lea     r8, pbInput; "ChainingModeCBC"
0x18004b505  mov     r9d, 20h ; ' '; cbInput
0x18004b50b  mov     dword ptr [rsp+0C0h+pcbResult], 0; dwFlags
0x18004b513  lea     rdx, aChainingmode; "ChainingMode"
0x18004b51a  call    cs:__imp_BCryptSetProperty
0x18004b520  mov     ebx, eax
0x18004b522  test    eax, eax
0x18004b524  js      loc_18004B639
0x18004b52a  mov     eax, [rbp+37h+cbSecret]
0x18004b52d  lea     rdx, [rbp+37h+phKey]; phKey
0x18004b531  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18004b535  xor     r9d, r9d; cbKeyObject
0x18004b538  mov     [rsp+0C0h+var_90], 0; dwFlags
0x18004b540  xor     r8d, r8d; pbKeyObject
0x18004b543  mov     [rsp+0C0h+dwFlags], eax; cbSecret
0x18004b547  mov     [rsp+0C0h+pcbResult], r13; pbSecret
0x18004b54c  call    cs:__imp_BCryptGenerateSymmetricKey
0x18004b552  mov     ebx, eax
0x18004b554  test    eax, eax
0x18004b556  js      loc_18004B639
0x18004b55c  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b560  lea     rax, [rbp+37h+var_70]
0x18004b564  mov     [rsp+0C0h+var_78], 1; dwFlags
0x18004b56c  xor     r9d, r9d; pPaddingInfo
0x18004b56f  mov     [rsp+0C0h+var_80], rax; pcbResult
0x18004b574  mov     r8d, r14d; cbInput
0x18004b577  mov     [rsp+0C0h+cbOutput], 0; cbOutput
0x18004b57f  mov     rdx, rsi; pbInput
0x18004b582  mov     qword ptr [rsp+0C0h+var_90], 0; pbOutput
0x18004b58b  mov     [rsp+0C0h+dwFlags], 10h; cbIV
0x18004b593  mov     [rsp+0C0h+pcbResult], rdi; pbIV
0x18004b598  call    cs:__imp_BCryptDecrypt
0x18004b59e  mov     ebx, eax
0x18004b5a0  test    eax, eax
0x18004b5a2  js      loc_18004B639
0x18004b5a8  mov     edx, [rbp+37h+var_70]; uBytes
0x18004b5ab  mov     ecx, 40h ; '@'; uFlags
0x18004b5b0  call    cs:__imp_LocalAlloc
0x18004b5b6  mov     rdi, rax
0x18004b5b9  test    rax, rax
0x18004b5bc  jnz     short loc_18004B5C5
0x18004b5be  mov     ebx, 0C000009Ah
0x18004b5c3  jmp     short loc_18004B639
0x18004b5c5  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b5c9  lea     rax, [rbp+37h+var_68]
0x18004b5cd  mov     [rsp+0C0h+var_78], 1; dwFlags
0x18004b5d5  xor     r9d, r9d; pPaddingInfo
0x18004b5d8  mov     [rsp+0C0h+var_80], rax; pcbResult
0x18004b5dd  mov     r8d, r14d; cbInput
0x18004b5e0  mov     eax, [rbp+37h+var_70]
0x18004b5e3  mov     rdx, rsi; pbInput
0x18004b5e6  mov     [rsp+0C0h+cbOutput], eax; cbOutput
0x18004b5ea  lea     rax, [rbp+37h+Destination]
0x18004b5ee  mov     qword ptr [rsp+0C0h+var_90], rdi; pbOutput
0x18004b5f3  mov     [rsp+0C0h+dwFlags], 10h; cbIV
0x18004b5fb  mov     [rsp+0C0h+pcbResult], rax; pbIV
0x18004b600  call    cs:__imp_BCryptDecrypt
0x18004b606  mov     ebx, eax
0x18004b608  test    eax, eax
0x18004b60a  js      short loc_18004B619
0x18004b60c  mov     eax, [rbp+37h+var_68]
0x18004b60f  cmp     eax, [rbp+37h+var_70]
0x18004b612  jbe     short loc_18004B682
0x18004b614  mov     ebx, 0C000000Dh
0x18004b619  mov     ecx, [rbp+37h+var_70]
0x18004b61c  mov     rax, rdi
0x18004b61f  test    rcx, rcx
0x18004b622  jz      short loc_18004B630
0x18004b624  mov     byte ptr [rax], 0
0x18004b627  inc     rax
0x18004b62a  sub     rcx, 1
0x18004b62e  jnz     short loc_18004B624
0x18004b630  mov     rcx, rdi; hMem
0x18004b633  call    cs:__imp_LocalFree
0x18004b639  mov     rcx, [rbp+37h+phKey]; hKey
0x18004b63d  test    rcx, rcx
0x18004b640  jz      short loc_18004B648
0x18004b642  call    cs:__imp_BCryptDestroyKey
0x18004b648  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x18004b64c  test    rcx, rcx
0x18004b64f  jz      short loc_18004B659
0x18004b651  xor     edx, edx; dwFlags
0x18004b653  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004b659  mov     eax, ebx
0x18004b65b  mov     rcx, [rbp+37h+var_38]
0x18004b65f  xor     rcx, rsp; StackCookie
0x18004b662  call    __security_check_cookie
0x18004b667  mov     rbx, [rsp+0C0h+arg_18]
0x18004b66f  add     rsp, 90h
0x18004b676  pop     r15
0x18004b678  pop     r14
0x18004b67a  pop     r13
0x18004b67c  pop     r12
0x18004b67e  pop     rdi
0x18004b67f  pop     rsi
0x18004b680  pop     rbp
0x18004b681  retn
0x18004b682  mov     [r12], eax
0x18004b686  mov     [r15], rdi
0x18004b689  jmp     short loc_18004B639
```
