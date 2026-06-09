# WkstDecryptDataWithAES

- ea: `0x1800321b4`
- end: `0x180032427`
- name: `WkstDecryptDataWithAES`
- size: `627`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR pbIV@<r8>, __int64, ULONG cbSecret, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180032430`

## callees

- `0x18001fbd0`
- `0x1800321b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032342`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032342`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323c5`
- `bcrypt!BCryptDestroyKey` at `0x1800323da`
- `bcrypt!BCryptDestroyKey` at `0x1800323da`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800322dc`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800322dc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800323f1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800323f1`
- `bcrypt!BCryptGetProperty` at `0x18003226a`
- `bcrypt!BCryptGetProperty` at `0x18003226a`
- `bcrypt!BCryptDecrypt` at `0x180032326`
- `bcrypt!BCryptDecrypt` at `0x180032398`
- `bcrypt!BCryptDecrypt` at `0x180032326`
- `bcrypt!BCryptDecrypt` at `0x180032398`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180032234`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180032234`
- `bcrypt!BCryptSetProperty` at `0x1800322a4`
- `bcrypt!BCryptSetProperty` at `0x1800322a4`

## pseudocode

```c
__int64 __fastcall WkstDecryptDataWithAES(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbIV,
        __int64 a4,
        UCHAR *a5,
        ULONG cbSecret,
        UCHAR **a7,
        ULONG *a8)
{
  __int128 v11; // xmm0
  UCHAR *v12; // rdi
  NTSTATUS Property; // ebx
  ULONG cbOutput; // [rsp+50h] [rbp-49h] BYREF
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-45h] BYREF
  ULONG v17; // [rsp+58h] [rbp-41h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-29h] BYREF
  PUCHAR pbSecret; // [rsp+78h] [rbp-21h]
  UCHAR pbIVa[16]; // [rsp+80h] [rbp-19h] BYREF

  pbSecret = a5;
  *(_DWORD *)pbOutput = 16;
  *a8 = 0;
  *a7 = 0;
  v11 = *(_OWORD *)pbIV;
  phAlgorithm = 0;
  phKey = 0;
  v12 = 0;
  *(_OWORD *)pbIVa = v11;
  pcbResult = 0;
  cbOutput = 0;
  v17 = 0;
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
            if ( v12 )
            {
              Property = BCryptDecrypt(phKey, pbInput, cbInput, 0, pbIVa, 0x10u, v12, cbOutput, &v17, 1u);
              if ( Property >= 0 )
              {
                if ( v17 <= cbOutput )
                {
                  *a8 = v17;
                  *a7 = v12;
                  v12 = 0;
                }
                else
                {
                  Property = -1073741811;
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
  LocalFree(v12);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800321b4  mov     [rsp-8+arg_18], rbx
0x1800321b9  push    rbp
0x1800321ba  push    rsi
0x1800321bb  push    rdi
0x1800321bc  push    r12
0x1800321be  push    r13
0x1800321c0  push    r14
0x1800321c2  push    r15
0x1800321c4  lea     rbp, [rsp-7]
0x1800321c9  sub     rsp, 0A0h
0x1800321d0  mov     rax, cs:__security_cookie
0x1800321d7  xor     rax, rsp
0x1800321da  mov     [rbp+37h+var_40], rax
0x1800321de  mov     rax, [rbp+37h+arg_20]
0x1800321e2  mov     r13, r8
0x1800321e5  mov     r12, [rbp+37h+arg_38]
0x1800321e9  mov     r14d, edx
0x1800321ec  mov     r15, [rbp+37h+arg_30]
0x1800321f0  lea     rdx, pszAlgId; "AES"
0x1800321f7  mov     [rbp+37h+pbSecret], rax
0x1800321fb  mov     rsi, rcx
0x1800321fe  xor     eax, eax
0x180032200  mov     dword ptr [rbp+37h+pbOutput], 10h
0x180032207  mov     [r12], eax
0x18003220b  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x18003220f  mov     [r15], rax
0x180032212  xor     r9d, r9d; dwFlags
0x180032215  movups  xmm0, xmmword ptr [r8]
0x180032219  xor     r8d, r8d; pszImplementation
0x18003221c  mov     [rbp+37h+phAlgorithm], rax
0x180032220  mov     [rbp+37h+phKey], rax
0x180032224  mov     edi, eax
0x180032226  movdqu  xmmword ptr [rbp+37h+pbIV], xmm0
0x18003222b  mov     [rbp+37h+var_60], eax
0x18003222e  mov     [rbp+37h+var_80], eax
0x180032231  mov     [rbp+37h+var_78], eax
0x180032234  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003223b  nop     dword ptr [rax+rax+00h]
0x180032240  mov     ebx, eax
0x180032242  test    eax, eax
0x180032244  js      loc_1800323C2
0x18003224a  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18003224e  lea     rax, [rbp+37h+var_60]
0x180032252  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x180032256  lea     r9d, [rdi+4]; cbOutput
0x18003225a  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x18003225e  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180032263  lea     rdx, pszProperty; "BlockLength"
0x18003226a  call    cs:__imp_BCryptGetProperty
0x180032271  nop     dword ptr [rax+rax+00h]
0x180032276  mov     ebx, eax
0x180032278  test    eax, eax
0x18003227a  js      loc_1800323C2
0x180032280  cmp     dword ptr [rbp+37h+pbOutput], 10h
0x180032284  jnz     loc_1800323C2
0x18003228a  mov     rcx, [rbp+37h+phAlgorithm]; hObject
0x18003228e  lea     r9d, [rdi+20h]; cbInput
0x180032292  lea     r8, pbInput; "ChainingModeCBC"
0x180032299  mov     dword ptr [rsp+0D0h+pcbResult], edi; dwFlags
0x18003229d  lea     rdx, aChainingmode; "ChainingMode"
0x1800322a4  call    cs:__imp_BCryptSetProperty
0x1800322ab  nop     dword ptr [rax+rax+00h]
0x1800322b0  mov     ebx, eax
0x1800322b2  test    eax, eax
0x1800322b4  js      loc_1800323C2
0x1800322ba  mov     eax, [rbp+37h+cbSecret]
0x1800322bd  lea     rdx, [rbp+37h+phKey]; phKey
0x1800322c1  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x1800322c5  xor     r9d, r9d; cbKeyObject
0x1800322c8  mov     [rsp+0D0h+var_A0], edi; dwFlags
0x1800322cc  xor     r8d, r8d; pbKeyObject
0x1800322cf  mov     [rsp+0D0h+dwFlags], eax; cbSecret
0x1800322d3  mov     rax, [rbp+37h+pbSecret]
0x1800322d7  mov     [rsp+0D0h+pcbResult], rax; pbSecret
0x1800322dc  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800322e3  nop     dword ptr [rax+rax+00h]
0x1800322e8  mov     ebx, eax
0x1800322ea  test    eax, eax
0x1800322ec  js      loc_1800323C2
0x1800322f2  mov     rcx, [rbp+37h+phKey]; hKey
0x1800322f6  lea     rax, [rbp+37h+var_80]
0x1800322fa  mov     [rsp+0D0h+var_88], 1; dwFlags
0x180032302  xor     r9d, r9d; pPaddingInfo
0x180032305  mov     [rsp+0D0h+var_90], rax; pcbResult
0x18003230a  mov     r8d, r14d; cbInput
0x18003230d  mov     [rsp+0D0h+cbOutput], edi; cbOutput
0x180032311  mov     rdx, rsi; pbInput
0x180032314  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x180032319  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x180032321  mov     [rsp+0D0h+pcbResult], r13; pbIV
0x180032326  call    cs:__imp_BCryptDecrypt
0x18003232d  nop     dword ptr [rax+rax+00h]
0x180032332  mov     ebx, eax
0x180032334  test    eax, eax
0x180032336  js      loc_1800323C2
0x18003233c  mov     edx, [rbp+37h+var_80]; uBytes
0x18003233f  lea     ecx, [rdi+40h]; uFlags
0x180032342  call    cs:__imp_LocalAlloc
0x180032349  nop     dword ptr [rax+rax+00h]
0x18003234e  mov     rdi, rax
0x180032351  test    rax, rax
0x180032354  jnz     short loc_18003235D
0x180032356  mov     ebx, 0C000009Ah
0x18003235b  jmp     short loc_1800323C2
0x18003235d  mov     rcx, [rbp+37h+phKey]; hKey
0x180032361  lea     rax, [rbp+37h+var_78]
0x180032365  mov     [rsp+0D0h+var_88], 1; dwFlags
0x18003236d  xor     r9d, r9d; pPaddingInfo
0x180032370  mov     [rsp+0D0h+var_90], rax; pcbResult
0x180032375  mov     r8d, r14d; cbInput
0x180032378  mov     eax, [rbp+37h+var_80]
0x18003237b  mov     rdx, rsi; pbInput
0x18003237e  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x180032382  lea     rax, [rbp+37h+pbIV]
0x180032386  mov     qword ptr [rsp+0D0h+var_A0], rdi; pbOutput
0x18003238b  mov     [rsp+0D0h+dwFlags], 10h; cbIV
0x180032393  mov     [rsp+0D0h+pcbResult], rax; pbIV
0x180032398  call    cs:__imp_BCryptDecrypt
0x18003239f  nop     dword ptr [rax+rax+00h]
0x1800323a4  mov     ebx, eax
0x1800323a6  test    eax, eax
0x1800323a8  js      short loc_1800323C2
0x1800323aa  mov     eax, [rbp+37h+var_78]
0x1800323ad  cmp     eax, [rbp+37h+var_80]
0x1800323b0  jbe     short loc_1800323B9
0x1800323b2  mov     ebx, 0C000000Dh
0x1800323b7  jmp     short loc_1800323C2
0x1800323b9  mov     [r12], eax
0x1800323bd  mov     [r15], rdi
0x1800323c0  xor     edi, edi
0x1800323c2  mov     rcx, rdi; hMem
0x1800323c5  call    cs:__imp_LocalFree
0x1800323cc  nop     dword ptr [rax+rax+00h]
0x1800323d1  mov     rcx, [rbp+37h+phKey]; hKey
0x1800323d5  test    rcx, rcx
0x1800323d8  jz      short loc_1800323E6
0x1800323da  call    cs:__imp_BCryptDestroyKey
0x1800323e1  nop     dword ptr [rax+rax+00h]
0x1800323e6  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x1800323ea  test    rcx, rcx
0x1800323ed  jz      short loc_1800323FD
0x1800323ef  xor     edx, edx; dwFlags
0x1800323f1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800323f8  nop     dword ptr [rax+rax+00h]
0x1800323fd  mov     eax, ebx
0x1800323ff  mov     rcx, [rbp+37h+var_40]
0x180032403  xor     rcx, rsp; StackCookie
0x180032406  call    __security_check_cookie
0x18003240b  mov     rbx, [rsp+0D0h+arg_18]
0x180032413  add     rsp, 0A0h
0x18003241a  pop     r15
0x18003241c  pop     r14
0x18003241e  pop     r13
0x180032420  pop     r12
0x180032422  pop     rdi
0x180032423  pop     rsi
0x180032424  pop     rbp
0x180032425  retn
```
