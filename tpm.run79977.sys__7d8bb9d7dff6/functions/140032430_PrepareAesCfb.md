# PrepareAesCfb

- ea: `0x140032430`
- end: `0x14003257e`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_ALG_HANDLE *, BCRYPT_KEY_HANDLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140032590`
- `0x140032780`

## callees

- `0x140032430`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x1400324ac`
- `cng!BCryptGenerateSymmetricKey` at `0x1400324ac`
- `cng!BCryptDestroyKey` at `0x14003254b`
- `cng!BCryptDestroyKey` at `0x14003254b`
- `cng!BCryptCloseAlgorithmProvider` at `0x140032562`
- `cng!BCryptCloseAlgorithmProvider` at `0x140032562`
- `cng!BCryptOpenAlgorithmProvider` at `0x140032477`
- `cng!BCryptOpenAlgorithmProvider` at `0x140032477`
- `cng!BCryptSetProperty` at `0x1400324de`
- `cng!BCryptSetProperty` at `0x14003250d`
- `cng!BCryptSetProperty` at `0x1400324de`
- `cng!BCryptSetProperty` at `0x14003250d`

## pseudocode

```c
__int64 __fastcall PrepareAesCfb(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_ALG_HANDLE *a3, BCRYPT_KEY_HANDLE *a4)
{
  NTSTATUS v8; // ebx
  BCRYPT_ALG_HANDLE v9; // rcx
  BCRYPT_KEY_HANDLE v10; // rax
  UCHAR pbInput[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  *(_DWORD *)pbInput = 16;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0
    || (v8 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"MessageBlockLength", pbInput, 4u, 0), v8 < 0) )
  {
    v9 = phAlgorithm;
    v10 = phKey;
  }
  else
  {
    v9 = 0;
    *a3 = phAlgorithm;
    *a4 = phKey;
    v10 = 0;
    phKey = 0;
    phAlgorithm = 0;
  }
  if ( v10 )
  {
    BCryptDestroyKey(v10);
    v9 = phAlgorithm;
  }
  if ( v9 )
    BCryptCloseAlgorithmProvider(v9, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140032430  push    rbp
0x140032432  push    rbx
0x140032433  push    rsi
0x140032434  push    rdi
0x140032435  push    r14
0x140032437  push    r15
0x140032439  mov     rbp, rsp
0x14003243c  sub     rsp, 68h
0x140032440  mov     r14, r9
0x140032443  mov     [rbp+phAlgorithm], 0
0x14003244b  mov     r15, r8
0x14003244e  mov     [rbp+phKey], 0
0x140032456  mov     edi, edx
0x140032458  mov     dword ptr [rbp+pbInput], 10h
0x14003245f  mov     rsi, rcx
0x140032462  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140032469  xor     r9d, r9d; dwFlags
0x14003246c  lea     rdx, aAes; "AES"
0x140032473  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140032477  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14003247e  nop     dword ptr [rax+rax+00h]
0x140032483  mov     ebx, eax
0x140032485  test    eax, eax
0x140032487  js      loc_14003253B
0x14003248d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140032491  lea     rdx, [rbp+phKey]; phKey
0x140032495  mov     [rsp+68h+dwFlags], 0; dwFlags
0x14003249d  xor     r9d, r9d; cbKeyObject
0x1400324a0  mov     [rsp+68h+cbSecret], edi; cbSecret
0x1400324a4  xor     r8d, r8d; pbKeyObject
0x1400324a7  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x1400324ac  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400324b3  nop     dword ptr [rax+rax+00h]
0x1400324b8  mov     ebx, eax
0x1400324ba  test    eax, eax
0x1400324bc  js      short loc_14003253B
0x1400324be  mov     rcx, [rbp+phKey]; hObject
0x1400324c2  lea     r8, pbInput; "ChainingModeCFB"
0x1400324c9  mov     r9d, 20h ; ' '; cbInput
0x1400324cf  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1400324d7  lea     rdx, aChainingmode; "ChainingMode"
0x1400324de  call    cs:__imp_BCryptSetProperty
0x1400324e5  nop     dword ptr [rax+rax+00h]
0x1400324ea  mov     ebx, eax
0x1400324ec  test    eax, eax
0x1400324ee  js      short loc_14003253B
0x1400324f0  mov     rcx, [rbp+phKey]; hObject
0x1400324f4  lea     r8, [rbp+pbInput]; pbInput
0x1400324f8  mov     r9d, 4; cbInput
0x1400324fe  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x140032506  lea     rdx, aMessageblockle; "MessageBlockLength"
0x14003250d  call    cs:__imp_BCryptSetProperty
0x140032514  nop     dword ptr [rax+rax+00h]
0x140032519  mov     ebx, eax
0x14003251b  test    eax, eax
0x14003251d  js      short loc_14003253B
0x14003251f  mov     rax, [rbp+phAlgorithm]
0x140032523  xor     ecx, ecx
0x140032525  mov     [r15], rax
0x140032528  mov     rax, [rbp+phKey]
0x14003252c  mov     [r14], rax
0x14003252f  xor     eax, eax
0x140032531  mov     [rbp+phKey], rax
0x140032535  mov     [rbp+phAlgorithm], rcx
0x140032539  jmp     short loc_140032543
0x14003253b  mov     rcx, [rbp+phAlgorithm]
0x14003253f  mov     rax, [rbp+phKey]
0x140032543  test    rax, rax
0x140032546  jz      short loc_14003255B
0x140032548  mov     rcx, rax; hKey
0x14003254b  call    cs:__imp_BCryptDestroyKey
0x140032552  nop     dword ptr [rax+rax+00h]
0x140032557  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14003255b  test    rcx, rcx
0x14003255e  jz      short loc_14003256E
0x140032560  xor     edx, edx; dwFlags
0x140032562  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140032569  nop     dword ptr [rax+rax+00h]
0x14003256e  mov     eax, ebx
0x140032570  add     rsp, 68h
0x140032574  pop     r15
0x140032576  pop     r14
0x140032578  pop     rdi
0x140032579  pop     rsi
0x14003257a  pop     rbx
0x14003257b  pop     rbp
0x14003257c  retn
```
