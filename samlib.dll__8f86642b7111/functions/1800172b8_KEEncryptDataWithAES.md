# KEEncryptDataWithAES

- ea: `0x1800172b8`
- end: `0x1800174da`
- name: `KEEncryptDataWithAES`
- size: `546`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, PUCHAR pbSecret, ULONG cbSecret, __int64, ULONG *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009b38`

## callees

- `0x180006620`
- `0x1800172b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017484`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001741c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001741c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800174aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800174aa`
- `bcrypt!BCryptSetProperty` at `0x180017395`
- `bcrypt!BCryptSetProperty` at `0x180017395`
- `bcrypt!BCryptGetProperty` at `0x180017365`
- `bcrypt!BCryptGetProperty` at `0x180017365`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017329`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017329`
- `bcrypt!BCryptEncrypt` at `0x180017408`
- `bcrypt!BCryptEncrypt` at `0x180017464`
- `bcrypt!BCryptEncrypt` at `0x180017408`
- `bcrypt!BCryptEncrypt` at `0x180017464`
- `bcrypt!BCryptDestroyKey` at `0x180017499`
- `bcrypt!BCryptDestroyKey` at `0x180017499`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800173be`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800173be`

## pseudocode

```c
__int64 __fastcall KEEncryptDataWithAES(
        PUCHAR pbInput,
        __int64 a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR pbSecret,
        ULONG cbSecret,
        HLOCAL *a7,
        ULONG *a8)
{
  __int128 v10; // xmm0
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  UCHAR *v13; // rax
  ULONG cbOutput; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-21h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-19h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-11h] BYREF
  UCHAR pbIV[16]; // [rsp+70h] [rbp-9h] BYREF

  phAlgorithm = 0;
  *a8 = 0;
  *a7 = 0;
  v10 = *(_OWORD *)a3;
  phKey = 0;
  pcbResult = 0;
  *(_OWORD *)pbIV = v10;
  cbOutput = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0) < 0
    || BCryptGetProperty(phAlgorithm, L"BlockLength", &KE_AESBlockSize, 4u, &pcbResult, 0) < 0
    || *(_DWORD *)&KE_AESBlockSize != 16
    || BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0) < 0 )
  {
    v11 = 1;
LABEL_3:
    v12 = 1;
    goto LABEL_12;
  }
  v11 = 1;
  if ( BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0) < 0 )
    goto LABEL_3;
  if ( BCryptEncrypt(phKey, pbInput, 0x202u, 0, a3, 0x10u, 0, 0, &cbOutput, 1u) < 0 )
    goto LABEL_3;
  v13 = (UCHAR *)LocalAlloc(0x40u, cbOutput);
  *a7 = v13;
  if ( !v13 )
    goto LABEL_3;
  v12 = BCryptEncrypt(phKey, pbInput, 0x202u, 0, pbIV, 0x10u, v13, cbOutput, a8, 1u);
  if ( v12 < 0 )
    v12 = 1;
LABEL_12:
  if ( *a8 > cbOutput || (v11 = v12) != 0 )
  {
    if ( *a7 )
    {
      LocalFree(*a7);
      *a7 = 0;
    }
    *a8 = 0;
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v11;
}

```

## disassembly

```asm
0x1800172b8  mov     [rsp-8+arg_8], rbx
0x1800172bd  mov     [rsp-8+arg_18], rsi
0x1800172c2  push    rbp
0x1800172c3  push    rdi
0x1800172c4  push    r12
0x1800172c6  push    r14
0x1800172c8  push    r15
0x1800172ca  lea     rbp, [rsp-17h]
0x1800172cf  sub     rsp, 90h
0x1800172d6  mov     rax, cs:__security_cookie
0x1800172dd  xor     rax, rsp
0x1800172e0  mov     [rbp+37h+var_30], rax
0x1800172e4  mov     rsi, [rbp+37h+arg_38]
0x1800172e8  lea     rdx, aAes; "AES"
0x1800172ef  mov     rdi, [rbp+37h+arg_30]
0x1800172f3  xor     r12d, r12d
0x1800172f6  mov     rbx, [rbp+37h+pbSecret]
0x1800172fa  mov     r14, r8
0x1800172fd  mov     r15, rcx
0x180017300  mov     [rbp+37h+phAlgorithm], r12
0x180017304  mov     [rsi], r12d
0x180017307  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x18001730b  mov     [rdi], r12
0x18001730e  xor     r9d, r9d; dwFlags
0x180017311  movups  xmm0, xmmword ptr [r8]
0x180017315  xor     r8d, r8d; pszImplementation
0x180017318  mov     [rbp+37h+phKey], r12
0x18001731c  mov     [rbp+37h+var_48], r12d
0x180017320  movdqu  xmmword ptr [rbp+37h+pbIV], xmm0
0x180017325  mov     [rbp+37h+var_60], r12d
0x180017329  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001732f  test    eax, eax
0x180017331  jns     short loc_18001733F
0x180017333  mov     ebx, 1
0x180017338  mov     eax, ebx
0x18001733a  jmp     loc_18001746F
0x18001733f  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x180017343  lea     rax, [rbp+37h+var_48]
0x180017347  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x18001734c  lea     r8, ?KE_AESBlockSize@@3KA; pbOutput
0x180017353  mov     r9d, 4; cbOutput
0x180017359  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18001735e  lea     rdx, pszProperty; "BlockLength"
0x180017365  call    cs:__imp_BCryptGetProperty
0x18001736b  test    eax, eax
0x18001736d  js      short loc_180017333
0x18001736f  cmp     cs:?KE_AESBlockSize@@3KA, 10h; ulong KE_AESBlockSize
0x180017376  jnz     short loc_180017333
0x180017378  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18001737c  lea     r8, pbInput; "ChainingModeCBC"
0x180017383  mov     r9d, 20h ; ' '; cbInput
0x180017389  mov     dword ptr [rsp+0B0h+pcbResult], r12d; dwFlags
0x18001738e  lea     rdx, aChainingmode; "ChainingMode"
0x180017395  call    cs:__imp_BCryptSetProperty
0x18001739b  test    eax, eax
0x18001739d  js      short loc_180017333
0x18001739f  mov     eax, [rbp+37h+cbSecret]
0x1800173a2  lea     rdx, [rbp+37h+phKey]; phKey
0x1800173a6  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x1800173aa  xor     r9d, r9d; cbKeyObject
0x1800173ad  mov     [rsp+0B0h+var_80], r12d; dwFlags
0x1800173b2  xor     r8d, r8d; pbKeyObject
0x1800173b5  mov     [rsp+0B0h+dwFlags], eax; cbSecret
0x1800173b9  mov     [rsp+0B0h+pcbResult], rbx; pbSecret
0x1800173be  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800173c4  mov     ebx, 1
0x1800173c9  test    eax, eax
0x1800173cb  js      loc_180017338
0x1800173d1  mov     rcx, [rbp+37h+phKey]; hKey
0x1800173d5  lea     rax, [rbp+37h+var_60]
0x1800173d9  mov     [rsp+0B0h+var_68], ebx; dwFlags
0x1800173dd  xor     r9d, r9d; pPaddingInfo
0x1800173e0  mov     [rsp+0B0h+var_70], rax; pcbResult
0x1800173e5  mov     rdx, r15; pbInput
0x1800173e8  mov     [rsp+0B0h+cbOutput], r12d; cbOutput
0x1800173ed  mov     qword ptr [rsp+0B0h+var_80], r12; pbOutput
0x1800173f2  mov     [rsp+0B0h+dwFlags], 10h; cbIV
0x1800173fa  mov     [rsp+0B0h+pcbResult], r14; pbIV
0x1800173ff  mov     r14d, 202h
0x180017405  mov     r8d, r14d; cbInput
0x180017408  call    cs:__imp_BCryptEncrypt
0x18001740e  test    eax, eax
0x180017410  js      loc_180017338
0x180017416  mov     edx, [rbp+37h+var_60]; uBytes
0x180017419  lea     ecx, [rbx+3Fh]; uFlags
0x18001741c  call    cs:__imp_LocalAlloc
0x180017422  mov     [rdi], rax
0x180017425  mov     rcx, rax
0x180017428  test    rax, rax
0x18001742b  jz      loc_180017338
0x180017431  mov     eax, [rbp+37h+var_60]
0x180017434  xor     r9d, r9d; pPaddingInfo
0x180017437  mov     [rsp+0B0h+var_68], ebx; dwFlags
0x18001743b  mov     r8d, r14d; cbInput
0x18001743e  mov     [rsp+0B0h+var_70], rsi; pcbResult
0x180017443  mov     rdx, r15; pbInput
0x180017446  mov     [rsp+0B0h+cbOutput], eax; cbOutput
0x18001744a  lea     rax, [rbp+37h+pbIV]
0x18001744e  mov     qword ptr [rsp+0B0h+var_80], rcx; pbOutput
0x180017453  mov     rcx, [rbp+37h+phKey]; hKey
0x180017457  mov     [rsp+0B0h+dwFlags], 10h; cbIV
0x18001745f  mov     [rsp+0B0h+pcbResult], rax; pbIV
0x180017464  call    cs:__imp_BCryptEncrypt
0x18001746a  test    eax, eax
0x18001746c  cmovs   eax, ebx
0x18001746f  mov     ecx, [rbp+37h+var_60]
0x180017472  cmp     [rsi], ecx
0x180017474  ja      short loc_18001747C
0x180017476  mov     ebx, eax
0x180017478  test    eax, eax
0x18001747a  jz      short loc_180017490
0x18001747c  mov     rcx, [rdi]; hMem
0x18001747f  test    rcx, rcx
0x180017482  jz      short loc_18001748D
0x180017484  call    cs:__imp_LocalFree
0x18001748a  mov     [rdi], r12
0x18001748d  mov     [rsi], r12d
0x180017490  mov     rcx, [rbp+37h+phKey]; hKey
0x180017494  test    rcx, rcx
0x180017497  jz      short loc_18001749F
0x180017499  call    cs:__imp_BCryptDestroyKey
0x18001749f  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x1800174a3  test    rcx, rcx
0x1800174a6  jz      short loc_1800174B0
0x1800174a8  xor     edx, edx; dwFlags
0x1800174aa  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800174b0  mov     eax, ebx
0x1800174b2  mov     rcx, [rbp+37h+var_30]
0x1800174b6  xor     rcx, rsp; StackCookie
0x1800174b9  call    __security_check_cookie
0x1800174be  lea     r11, [rsp+0B0h+var_20]
0x1800174c6  mov     rbx, [r11+38h]
0x1800174ca  mov     rsi, [r11+48h]
0x1800174ce  mov     rsp, r11
0x1800174d1  pop     r15
0x1800174d3  pop     r14
0x1800174d5  pop     r12
0x1800174d7  pop     rdi
0x1800174d8  pop     rbp
0x1800174d9  retn
```
