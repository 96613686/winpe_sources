# DigestHashN

- ea: `0x180018298`
- end: `0x1800185af`
- name: `DigestHashN`
- size: `791`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ff20`
- `0x18002ba20`

## callees

- `0x18000c6f0`
- `0x18000c850`
- `0x180011fec`
- `0x180012880`
- `0x180018298`
- `0x1800185b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184fb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180018426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180018446`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180018426`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180018446`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800183b3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800183b3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001848f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001850f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001848f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001850f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800184df`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800184df`

## pseudocode

```c
__int64 __fastcall DigestHashN(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  PVOID *v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  DWORD v10; // eax
  unsigned int i; // esi
  DWORD LastError; // eax
  __int64 v13; // rdx
  DWORD v14; // eax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-28h] BYREF
  BYTE pbData[16]; // [rsp+40h] [rbp-20h] BYREF

  hHash = 0;
  pdwDataLen = 16;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a4 + 8) )
  {
    if ( *(_WORD *)(a4 + 2) < 0x21u )
    {
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
      {
        WPP_SF_(v7[2], 109, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v8 = -1073741789;
      goto LABEL_46;
    }
    v8 = 0;
  }
  else
  {
    v8 = StringAllocate(a4, 32);
    if ( v8 < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 108;
LABEL_9:
        WPP_SF_(v7[2], v9, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_10:
      v8 = -2146893056;
      goto LABEL_46;
    }
  }
  if ( CryptCreateHash(g_hCryptProv, 0x8003u, 0, 0, &hHash) )
  {
    for ( i = 0; i < a2; ++i )
    {
      if ( i && !CryptHashData(hHash, ":", 1u, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v13 = 111;
          goto LABEL_31;
        }
LABEL_32:
        CryptDestroyHash(hHash);
        hHash = 0;
        v8 = -1073741174;
LABEL_45:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_46;
      }
      if ( !CryptHashData(hHash, *(const BYTE **)(a1 + 16LL * i + 8), *(unsigned __int16 *)(a1 + 16LL * i), 0) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        LastError = GetLastError();
        v13 = 112;
        goto LABEL_31;
      }
    }
    if ( !CryptGetHashParam(hHash, 2u, pbData, &pdwDataLen, 0) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_32;
      LastError = GetLastError();
      v13 = 113;
LABEL_31:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, LastError);
      goto LABEL_32;
    }
    CryptDestroyHash(hHash);
    v14 = *(unsigned __int16 *)(a4 + 2);
    hHash = 0;
    if ( v14 >= pdwDataLen )
    {
      BinToHex(pbData, pdwDataLen, *(_QWORD *)(a4 + 8));
      *(_WORD *)a4 = 32;
      goto LABEL_45;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 114;
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, v10);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = -1073741174;
LABEL_46:
  if ( v7 != &WPP_GLOBAL_Control && *((char *)v7 + 28) < 0 )
    WPP_SF_d(v7[2], 115, &WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018298  mov     [rsp-28h+arg_8], rbx
0x18001829d  mov     [rsp-28h+arg_10], rsi
0x1800182a2  push    rbp
0x1800182a3  push    rdi
0x1800182a4  push    r13
0x1800182a6  push    r14
0x1800182a8  push    r15
0x1800182aa  mov     rbp, rsp
0x1800182ad  sub     rsp, 60h
0x1800182b1  mov     rax, cs:__security_cookie
0x1800182b8  xor     rax, rsp
0x1800182bb  mov     [rbp+var_10], rax
0x1800182bf  mov     rdi, r9
0x1800182c2  mov     [rbp+hHash], 0
0x1800182ca  mov     r14d, edx
0x1800182cd  mov     [rbp+pdwDataLen], 10h
0x1800182d4  mov     r15, rcx
0x1800182d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182de  lea     r13, WPP_GLOBAL_Control
0x1800182e5  cmp     rcx, r13
0x1800182e8  jz      short loc_18001830C
0x1800182ea  test    byte ptr [rcx+1Ch], 80h
0x1800182ee  jz      short loc_18001830C
0x1800182f0  mov     rcx, [rcx+10h]
0x1800182f4  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x1800182fb  mov     edx, 6Bh ; 'k'
0x180018300  call    WPP_SF_
0x180018305  mov     rcx, cs:WPP_GLOBAL_Control
0x18001830c  cmp     qword ptr [rdi+8], 0
0x180018311  jnz     short loc_18001835E
0x180018313  mov     edx, 20h ; ' '
0x180018318  mov     rcx, rdi
0x18001831b  call    StringAllocate
0x180018320  mov     ebx, eax
0x180018322  test    eax, eax
0x180018324  jns     short loc_180018398
0x180018326  mov     rcx, cs:WPP_GLOBAL_Control
0x18001832d  cmp     rcx, r13
0x180018330  jz      short loc_180018354
0x180018332  test    byte ptr [rcx+1Ch], 1
0x180018336  jz      short loc_180018354
0x180018338  mov     edx, 6Ch ; 'l'
0x18001833d  mov     rcx, [rcx+10h]
0x180018341  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x180018348  call    WPP_SF_
0x18001834d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018354  mov     ebx, 80090300h
0x180018359  jmp     loc_180018565
0x18001835e  cmp     word ptr [rdi+2], 21h ; '!'
0x180018363  jnb     short loc_180018396
0x180018365  cmp     rcx, r13
0x180018368  jz      short loc_18001838C
0x18001836a  test    byte ptr [rcx+1Ch], 1
0x18001836e  jz      short loc_18001838C
0x180018370  mov     rcx, [rcx+10h]
0x180018374  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x18001837b  mov     edx, 6Dh ; 'm'
0x180018380  call    WPP_SF_
0x180018385  mov     rcx, cs:WPP_GLOBAL_Control
0x18001838c  mov     ebx, 0C0000023h
0x180018391  jmp     loc_180018565
0x180018396  xor     ebx, ebx
0x180018398  mov     rcx, cs:g_hCryptProv; hProv
0x18001839f  lea     rax, [rbp+hHash]
0x1800183a3  xor     r9d, r9d; dwFlags
0x1800183a6  mov     [rsp+60h+phHash], rax; phHash
0x1800183ab  xor     r8d, r8d; hKey
0x1800183ae  mov     edx, 8003h; Algid
0x1800183b3  call    cs:__imp_CryptCreateHash
0x1800183b9  test    eax, eax
0x1800183bb  jnz     short loc_180018405
0x1800183bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183c4  cmp     rcx, r13
0x1800183c7  jz      short loc_1800183FB
0x1800183c9  test    byte ptr [rcx+1Ch], 1
0x1800183cd  jz      short loc_1800183FB
0x1800183cf  call    cs:__imp_GetLastError
0x1800183d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183dc  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x1800183e3  mov     edx, 6Eh ; 'n'
0x1800183e8  mov     r9d, eax
0x1800183eb  mov     rcx, [rcx+10h]
0x1800183ef  call    WPP_SF_d
0x1800183f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183fb  mov     ebx, 0C000028Ah
0x180018400  jmp     loc_180018565
0x180018405  xor     esi, esi
0x180018407  cmp     esi, r14d
0x18001840a  jnb     loc_1800184C6
0x180018410  test    esi, esi
0x180018412  jz      short loc_180018430
0x180018414  mov     rcx, [rbp+hHash]; hHash
0x180018418  lea     rdx, pbData; ":"
0x18001841f  xor     r9d, r9d; dwFlags
0x180018422  lea     r8d, [r9+1]; dwDataLen
0x180018426  call    cs:__imp_CryptHashData
0x18001842c  test    eax, eax
0x18001842e  jz      short loc_180018454
0x180018430  mov     rcx, [rbp+hHash]; hHash
0x180018434  xor     r9d, r9d; dwFlags
0x180018437  mov     edx, esi
0x180018439  add     rdx, rdx
0x18001843c  movzx   r8d, word ptr [r15+rdx*8]; dwDataLen
0x180018441  mov     rdx, [r15+rdx*8+8]; pbData
0x180018446  call    cs:__imp_CryptHashData
0x18001844c  test    eax, eax
0x18001844e  jz      short loc_1800184A7
0x180018450  inc     esi
0x180018452  jmp     short loc_180018407
0x180018454  mov     rax, cs:WPP_GLOBAL_Control
0x18001845b  cmp     rax, r13
0x18001845e  jz      short loc_18001848B
0x180018460  test    byte ptr [rax+1Ch], 1
0x180018464  jz      short loc_18001848B
0x180018466  call    cs:__imp_GetLastError
0x18001846c  mov     edx, 6Fh ; 'o'
0x180018471  mov     rcx, cs:WPP_GLOBAL_Control
0x180018478  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x18001847f  mov     r9d, eax
0x180018482  mov     rcx, [rcx+10h]
0x180018486  call    WPP_SF_d
0x18001848b  mov     rcx, [rbp+hHash]; hHash
0x18001848f  call    cs:__imp_CryptDestroyHash
0x180018495  mov     [rbp+hHash], 0
0x18001849d  mov     ebx, 0C000028Ah
0x1800184a2  jmp     loc_18001855E
0x1800184a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800184ae  cmp     rax, r13
0x1800184b1  jz      short loc_18001848B
0x1800184b3  test    byte ptr [rax+1Ch], 1
0x1800184b7  jz      short loc_18001848B
0x1800184b9  call    cs:__imp_GetLastError
0x1800184bf  mov     edx, 70h ; 'p'
0x1800184c4  jmp     short loc_180018471
0x1800184c6  mov     rcx, [rbp+hHash]; hHash
0x1800184ca  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800184ce  lea     r8, [rbp+pbData]; pbData
0x1800184d2  mov     dword ptr [rsp+60h+phHash], 0; dwFlags
0x1800184da  mov     edx, 2; dwParam
0x1800184df  call    cs:__imp_CryptGetHashParam
0x1800184e5  test    eax, eax
0x1800184e7  jnz     short loc_18001850B
0x1800184e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800184f0  cmp     rax, r13
0x1800184f3  jz      short loc_18001848B
0x1800184f5  test    byte ptr [rax+1Ch], 1
0x1800184f9  jz      short loc_18001848B
0x1800184fb  call    cs:__imp_GetLastError
0x180018501  mov     edx, 71h ; 'q'
0x180018506  jmp     loc_180018471
0x18001850b  mov     rcx, [rbp+hHash]; hHash
0x18001850f  call    cs:__imp_CryptDestroyHash
0x180018515  movzx   eax, word ptr [rdi+2]
0x180018519  mov     edx, [rbp+pdwDataLen]
0x18001851c  mov     [rbp+hHash], 0
0x180018524  cmp     eax, edx
0x180018526  jnb     short loc_18001854C
0x180018528  mov     rcx, cs:WPP_GLOBAL_Control
0x18001852f  cmp     rcx, r13
0x180018532  jz      loc_180018354
0x180018538  test    byte ptr [rcx+1Ch], 1
0x18001853c  jz      loc_180018354
0x180018542  mov     edx, 72h ; 'r'
0x180018547  jmp     loc_18001833D
0x18001854c  mov     r8, [rdi+8]
0x180018550  lea     rcx, [rbp+pbData]
0x180018554  call    BinToHex
0x180018559  mov     word ptr [rdi], 20h ; ' '
0x18001855e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018565  cmp     rcx, r13
0x180018568  jz      short loc_180018588
0x18001856a  test    byte ptr [rcx+1Ch], 80h
0x18001856e  jz      short loc_180018588
0x180018570  mov     rcx, [rcx+10h]
0x180018574  lea     r8, WPP_8d7f25adb31537a06d09ecffe0b618d2_Traceguids
0x18001857b  mov     edx, 73h ; 's'
0x180018580  mov     r9d, ebx
0x180018583  call    WPP_SF_d
0x180018588  mov     eax, ebx
0x18001858a  mov     rcx, [rbp+var_10]
0x18001858e  xor     rcx, rsp; StackCookie
0x180018591  call    __security_check_cookie
0x180018596  lea     r11, [rsp+60h+var_s0]
0x18001859b  mov     rbx, [r11+38h]
0x18001859f  mov     rsi, [r11+40h]
0x1800185a3  mov     rsp, r11
0x1800185a6  pop     r15
0x1800185a8  pop     r14
0x1800185aa  pop     r13
0x1800185ac  pop     rdi
0x1800185ad  pop     rbp
0x1800185ae  retn
```
