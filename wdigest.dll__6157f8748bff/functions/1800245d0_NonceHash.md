# NonceHash

- ea: `0x1800245d0`
- end: `0x180024944`
- name: `NonceHash`
- size: `884`
- prototype: `__int64 __usercall@<rax>(BYTE *pbData@<rcx>, DWORD dwDataLen@<edx>, BYTE *@<r8>, BYTE *, int, int, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024328`
- `0x180024b10`

## callees

- `0x18000c6f0`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x1800245d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002467e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002471a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002475e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002486a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002467e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002471a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002475e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002486a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248b6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800246c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800246ff`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002473b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002477d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800247c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024803`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024847`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800246c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800246ff`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002473b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18002477d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800247c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024803`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180024847`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180024660`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180024660`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800248e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800248e9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180024893`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180024893`

## pseudocode

```c
__int64 __fastcall NonceHash(
        BYTE *pbData,
        DWORD dwDataLen,
        BYTE *a3,
        __int64 a4,
        BYTE *pbDataa,
        int a6,
        int a7,
        int a8,
        __int64 a9)
{
  PVOID *v12; // rcx
  DWORD LastError; // eax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  HCRYPTHASH hHash; // [rsp+30h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-28h] BYREF
  BYTE v19[16]; // [rsp+40h] [rbp-20h] BYREF

  hHash = 0;
  pdwDataLen = 16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
  if ( !CryptCreateHash(g_hCryptProv, 0x8003u, 0, 0, &hHash) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 34;
LABEL_8:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids, LastError);
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
    v15 = -1073741595;
    goto LABEL_44;
  }
  if ( dwDataLen )
  {
    if ( !CryptHashData(hHash, pbData, dwDataLen, 0) )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      LastError = GetLastError();
      v14 = 35;
      goto LABEL_8;
    }
    if ( !CryptHashData(hHash, ":", 1u, 0) )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      LastError = GetLastError();
      v14 = 36;
      goto LABEL_8;
    }
  }
  if ( !CryptHashData(hHash, a3, 0x10u, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 37;
    goto LABEL_8;
  }
  if ( !CryptHashData(hHash, ":", 1u, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 38;
    goto LABEL_8;
  }
  if ( !CryptHashData(hHash, pbDataa, 0x20u, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 39;
    goto LABEL_8;
  }
  if ( !CryptHashData(hHash, ":", 1u, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 40;
    goto LABEL_8;
  }
  if ( !CryptHashData(hHash, &g_cNoncePrivateKey, 0x20u, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 41;
    goto LABEL_8;
  }
  if ( !CryptGetHashParam(hHash, 2u, v19, &pdwDataLen, 0) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    LastError = GetLastError();
    v14 = 42;
    goto LABEL_8;
  }
  v15 = 0;
  BinToHex(v19, 16, a9);
  v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_44:
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    hHash = 0;
  }
  if ( v12 != &WPP_GLOBAL_Control && *((char *)v12 + 28) < 0 )
    WPP_SF_(v12[2], 43, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x1800245d0  mov     [rsp-38h+arg_18], rbx
0x1800245d5  push    rbp
0x1800245d6  push    rsi
0x1800245d7  push    rdi
0x1800245d8  push    r12
0x1800245da  push    r13
0x1800245dc  push    r14
0x1800245de  push    r15
0x1800245e0  mov     rbp, rsp
0x1800245e3  sub     rsp, 60h
0x1800245e7  mov     rax, cs:__security_cookie
0x1800245ee  xor     rax, rsp
0x1800245f1  mov     [rbp+var_10], rax
0x1800245f5  mov     r15, [rbp+pbData]
0x1800245f9  mov     r14, r8
0x1800245fc  mov     r12, [rbp+arg_40]
0x180024603  mov     edi, edx
0x180024605  mov     rsi, rcx
0x180024608  mov     [rbp+hHash], 0
0x180024610  mov     [rbp+pdwDataLen], 10h
0x180024617  mov     rcx, cs:WPP_GLOBAL_Control
0x18002461e  lea     r13, WPP_GLOBAL_Control
0x180024625  cmp     rcx, r13
0x180024628  jz      short loc_180024645
0x18002462a  test    byte ptr [rcx+1Ch], 80h
0x18002462e  jz      short loc_180024645
0x180024630  mov     rcx, [rcx+10h]
0x180024634  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x18002463b  mov     edx, 21h ; '!'
0x180024640  call    WPP_SF_
0x180024645  mov     rcx, cs:g_hCryptProv; hProv
0x18002464c  lea     rax, [rbp+hHash]
0x180024650  xor     r9d, r9d; dwFlags
0x180024653  mov     [rsp+60h+phHash], rax; phHash
0x180024658  xor     r8d, r8d; hKey
0x18002465b  mov     edx, 8003h; Algid
0x180024660  call    cs:__imp_CryptCreateHash
0x180024666  test    eax, eax
0x180024668  jnz     short loc_1800246B2
0x18002466a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024671  cmp     rcx, r13
0x180024674  jz      short loc_1800246A8
0x180024676  lea     ebx, [rax+1]
0x180024679  test    [rcx+1Ch], bl
0x18002467c  jz      short loc_1800246A8
0x18002467e  call    cs:__imp_GetLastError
0x180024684  lea     edx, [rbx+21h]
0x180024687  mov     rcx, cs:WPP_GLOBAL_Control
0x18002468e  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x180024695  mov     r9d, eax
0x180024698  mov     rcx, [rcx+10h]
0x18002469c  call    WPP_SF_d
0x1800246a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246a8  mov     ebx, 0C00000E5h
0x1800246ad  jmp     loc_1800248DD
0x1800246b2  mov     ebx, 1
0x1800246b7  test    edi, edi
0x1800246b9  jz      short loc_18002472A
0x1800246bb  mov     rcx, [rbp+hHash]; hHash
0x1800246bf  xor     r9d, r9d; dwFlags
0x1800246c2  mov     r8d, edi; dwDataLen
0x1800246c5  mov     rdx, rsi; pbData
0x1800246c8  call    cs:__imp_CryptHashData
0x1800246ce  test    eax, eax
0x1800246d0  jnz     short loc_1800246EE
0x1800246d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246d9  cmp     rcx, r13
0x1800246dc  jz      short loc_1800246A8
0x1800246de  test    [rcx+1Ch], bl
0x1800246e1  jz      short loc_1800246A8
0x1800246e3  call    cs:__imp_GetLastError
0x1800246e9  lea     edx, [rbx+22h]
0x1800246ec  jmp     short loc_180024687
0x1800246ee  mov     rcx, [rbp+hHash]; hHash
0x1800246f2  lea     rdx, pbData; ":"
0x1800246f9  xor     r9d, r9d; dwFlags
0x1800246fc  mov     r8d, ebx; dwDataLen
0x1800246ff  call    cs:__imp_CryptHashData
0x180024705  test    eax, eax
0x180024707  jnz     short loc_18002472A
0x180024709  mov     rcx, cs:WPP_GLOBAL_Control
0x180024710  cmp     rcx, r13
0x180024713  jz      short loc_1800246A8
0x180024715  test    [rcx+1Ch], bl
0x180024718  jz      short loc_1800246A8
0x18002471a  call    cs:__imp_GetLastError
0x180024720  mov     edx, 24h ; '$'
0x180024725  jmp     loc_180024687
0x18002472a  mov     rcx, [rbp+hHash]; hHash
0x18002472e  xor     r9d, r9d; dwFlags
0x180024731  mov     rdx, r14; pbData
0x180024734  lea     esi, [r9+10h]
0x180024738  mov     r8d, esi; dwDataLen
0x18002473b  call    cs:__imp_CryptHashData
0x180024741  test    eax, eax
0x180024743  jnz     short loc_18002476C
0x180024745  mov     rcx, cs:WPP_GLOBAL_Control
0x18002474c  cmp     rcx, r13
0x18002474f  jz      loc_1800246A8
0x180024755  test    [rcx+1Ch], bl
0x180024758  jz      loc_1800246A8
0x18002475e  call    cs:__imp_GetLastError
0x180024764  lea     edx, [rsi+15h]
0x180024767  jmp     loc_180024687
0x18002476c  mov     rcx, [rbp+hHash]; hHash
0x180024770  lea     rdx, pbData; ":"
0x180024777  xor     r9d, r9d; dwFlags
0x18002477a  mov     r8d, ebx; dwDataLen
0x18002477d  call    cs:__imp_CryptHashData
0x180024783  test    eax, eax
0x180024785  jnz     short loc_1800247B0
0x180024787  mov     rcx, cs:WPP_GLOBAL_Control
0x18002478e  cmp     rcx, r13
0x180024791  jz      loc_1800246A8
0x180024797  test    [rcx+1Ch], bl
0x18002479a  jz      loc_1800246A8
0x1800247a0  call    cs:__imp_GetLastError
0x1800247a6  mov     edx, 26h ; '&'
0x1800247ab  jmp     loc_180024687
0x1800247b0  mov     rcx, [rbp+hHash]; hHash
0x1800247b4  xor     r9d, r9d; dwFlags
0x1800247b7  mov     rdx, r15; pbData
0x1800247ba  lea     edi, [r9+20h]
0x1800247be  mov     r8d, edi; dwDataLen
0x1800247c1  call    cs:__imp_CryptHashData
0x1800247c7  test    eax, eax
0x1800247c9  jnz     short loc_1800247F2
0x1800247cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247d2  cmp     rcx, r13
0x1800247d5  jz      loc_1800246A8
0x1800247db  test    [rcx+1Ch], bl
0x1800247de  jz      loc_1800246A8
0x1800247e4  call    cs:__imp_GetLastError
0x1800247ea  lea     edx, [rdi+7]
0x1800247ed  jmp     loc_180024687
0x1800247f2  mov     rcx, [rbp+hHash]; hHash
0x1800247f6  lea     rdx, pbData; ":"
0x1800247fd  xor     r9d, r9d; dwFlags
0x180024800  mov     r8d, ebx; dwDataLen
0x180024803  call    cs:__imp_CryptHashData
0x180024809  test    eax, eax
0x18002480b  jnz     short loc_180024836
0x18002480d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024814  cmp     rcx, r13
0x180024817  jz      loc_1800246A8
0x18002481d  test    [rcx+1Ch], bl
0x180024820  jz      loc_1800246A8
0x180024826  call    cs:__imp_GetLastError
0x18002482c  mov     edx, 28h ; '('
0x180024831  jmp     loc_180024687
0x180024836  mov     rcx, [rbp+hHash]; hHash
0x18002483a  lea     rdx, ?g_cNoncePrivateKey@@3PADA; pbData
0x180024841  xor     r9d, r9d; dwFlags
0x180024844  mov     r8d, edi; dwDataLen
0x180024847  call    cs:__imp_CryptHashData
0x18002484d  test    eax, eax
0x18002484f  jnz     short loc_18002487A
0x180024851  mov     rcx, cs:WPP_GLOBAL_Control
0x180024858  cmp     rcx, r13
0x18002485b  jz      loc_1800246A8
0x180024861  test    [rcx+1Ch], bl
0x180024864  jz      loc_1800246A8
0x18002486a  call    cs:__imp_GetLastError
0x180024870  mov     edx, 29h ; ')'
0x180024875  jmp     loc_180024687
0x18002487a  mov     rcx, [rbp+hHash]; hHash
0x18002487e  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180024882  lea     r8, [rbp+var_20]; pbData
0x180024886  mov     dword ptr [rsp+60h+phHash], 0; dwFlags
0x18002488e  mov     edx, 2; dwParam
0x180024893  call    cs:__imp_CryptGetHashParam
0x180024899  test    eax, eax
0x18002489b  jnz     short loc_1800248C6
0x18002489d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248a4  cmp     rcx, r13
0x1800248a7  jz      loc_1800246A8
0x1800248ad  test    [rcx+1Ch], bl
0x1800248b0  jz      loc_1800246A8
0x1800248b6  call    cs:__imp_GetLastError
0x1800248bc  mov     edx, 2Ah ; '*'
0x1800248c1  jmp     loc_180024687
0x1800248c6  xor     ebx, ebx
0x1800248c8  lea     rcx, [rbp+var_20]
0x1800248cc  mov     r8, r12
0x1800248cf  mov     edx, esi
0x1800248d1  call    BinToHex
0x1800248d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248dd  mov     rax, [rbp+hHash]
0x1800248e1  test    rax, rax
0x1800248e4  jz      short loc_1800248FE
0x1800248e6  mov     rcx, rax; hHash
0x1800248e9  call    cs:__imp_CryptDestroyHash
0x1800248ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248f6  mov     [rbp+hHash], 0
0x1800248fe  cmp     rcx, r13
0x180024901  jz      short loc_18002491E
0x180024903  test    byte ptr [rcx+1Ch], 80h
0x180024907  jz      short loc_18002491E
0x180024909  mov     rcx, [rcx+10h]
0x18002490d  lea     r8, WPP_44f4a821d5a93d79ff0a58e212c9bb48_Traceguids
0x180024914  mov     edx, 2Bh ; '+'
0x180024919  call    WPP_SF_
0x18002491e  mov     eax, ebx
0x180024920  mov     rcx, [rbp+var_10]
0x180024924  xor     rcx, rsp; StackCookie
0x180024927  call    __security_check_cookie
0x18002492c  mov     rbx, [rsp+60h+arg_18]
0x180024934  add     rsp, 60h
0x180024938  pop     r15
0x18002493a  pop     r14
0x18002493c  pop     r13
0x18002493e  pop     r12
0x180024940  pop     rdi
0x180024941  pop     rsi
0x180024942  pop     rbp
0x180024943  retn
```
