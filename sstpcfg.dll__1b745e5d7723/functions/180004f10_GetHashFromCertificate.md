# GetHashFromCertificate

- ea: `0x180004f10`
- end: `0x18000536a`
- name: `GetHashFromCertificate`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001d10`
- `0x180004300`
- `0x180005830`
- `0x180005ea0`
- `0x180006b6c`
- `0x180007450`
- `0x180008e70`

## callees

- `0x180004f10`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180004f85`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180004f85`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18000533c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18000533c`
- `CRYPT32!CryptHashCertificate` at `0x180005058`
- `CRYPT32!CryptHashCertificate` at `0x180005097`
- `CRYPT32!CryptHashCertificate` at `0x1800051d1`
- `CRYPT32!CryptHashCertificate` at `0x18000520e`
- `CRYPT32!CryptHashCertificate` at `0x180005058`
- `CRYPT32!CryptHashCertificate` at `0x180005097`
- `CRYPT32!CryptHashCertificate` at `0x1800051d1`
- `CRYPT32!CryptHashCertificate` at `0x18000520e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000521c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052b9`

## pseudocode

```c
__int64 __fastcall GetHashFromCertificate(__int64 a1, char a2, BYTE *a3, BYTE *a4)
{
  DWORD LastError; // ebx
  __int64 v9; // r8
  DWORD *v10; // rdi
  const BYTE *v11; // r9
  __int64 v12; // r8
  const wchar_t *v13; // rdx
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  __int64 v16; // r8
  const BYTE *v17; // r9
  __int64 v18; // r8
  __int64 v19; // r8
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-E0h]
  DWORD pcbComputedHash; // [rsp+40h] [rbp-C0h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[2044]; // [rsp+54h] [rbp-ACh] BYREF

  phProv = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
  {
    v10 = (DWORD *)(a1 + 16);
    if ( (a2 & 2) != 0 )
    {
      v11 = *(const BYTE **)(a1 + 8);
      dwFlags = *v10;
      pcbComputedHash = 0;
      if ( !CryptHashCertificate(phProv, 0x800Cu, 0, v11, dwFlags, 0, &pcbComputedHash) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x8Du, v16, LastError);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_54;
        v13 = L"Unable to retrieve the certificate hash(sha256 - length): %d";
LABEL_52:
        LOWORD(v25) = 0;
        FormatRRASErrorString((wchar_t *)&v25, v13, LastError);
        v14 = xmmword_1800146E0;
        v15 = (const wchar_t *)&v25;
LABEL_53:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v14, v15);
        goto LABEL_54;
      }
      if ( pcbComputedHash != 32 )
      {
        LastError = -2146889721;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 140);
        }
        v14 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_54;
        v15 = L"Unsupported hash length returned for SHA256 cert hash";
        goto LABEL_53;
      }
      if ( !CryptHashCertificate(phProv, 0x800Cu, 0, *(const BYTE **)(a1 + 8), *v10, a4, &pcbComputedHash) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x8Bu, v12, LastError);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_54;
        v13 = L"Unable to retrieve the certificate hash(sha256): %d";
        goto LABEL_52;
      }
    }
    LastError = 0;
    if ( (a2 & 1) == 0 )
    {
LABEL_54:
      CryptReleaseContext(phProv, 0);
      return LastError;
    }
    v17 = *(const BYTE **)(a1 + 8);
    dwFlagsa = *v10;
    pcbComputedHash = 0;
    if ( CryptHashCertificate(phProv, 0x8004u, 0, v17, dwFlagsa, 0, &pcbComputedHash) )
    {
      if ( pcbComputedHash != 20 )
      {
        LastError = -2146889721;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143);
        }
        v14 = xmmword_1800146E0;
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_54;
        v15 = L"Unsupported hash length returned for SHA1 cert hash";
        goto LABEL_53;
      }
      if ( CryptHashCertificate(phProv, 0x8004u, 0, *(const BYTE **)(a1 + 8), *v10, a3, &pcbComputedHash) )
        goto LABEL_54;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x8Eu, v18, LastError);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_54;
      v13 = L"Unable to retrieve the certificate hash(sha1): %d";
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x90u, v19, LastError);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_54;
      v13 = L"Unable to retrieve the certificate hash length (sha1): %d";
    }
    goto LABEL_52;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x8Au, v9, LastError);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString((wchar_t *)&v25, L"CryptAcquireContext for enhanced crypto provider fails with %d", LastError);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v25);
  }
  return LastError;
}

```

## disassembly

```asm
0x180004f10  mov     [rsp-8+arg_8], rbx
0x180004f15  push    rbp
0x180004f16  push    rsi
0x180004f17  push    rdi
0x180004f18  push    r14
0x180004f1a  push    r15
0x180004f1c  lea     rbp, [rsp-760h]
0x180004f24  sub     rsp, 860h
0x180004f2b  mov     rax, cs:__security_cookie
0x180004f32  xor     rax, rsp
0x180004f35  mov     [rbp+780h+var_30], rax
0x180004f3c  mov     r15, r8
0x180004f3f  mov     [rsp+880h+phProv], 0
0x180004f48  mov     r14b, dl
0x180004f4b  mov     rsi, rcx
0x180004f4e  xor     eax, eax
0x180004f50  lea     rcx, [rsp+880h+var_82C]; void *
0x180004f55  xor     edx, edx; Val
0x180004f57  mov     [rsp+880h+var_830], eax
0x180004f5b  mov     r8d, 7FCh; Size
0x180004f61  mov     rbx, r9
0x180004f64  call    memset_0
0x180004f69  mov     r9d, 18h; dwProvType
0x180004f6f  mov     [rsp+880h+dwFlags], 0F0000000h; dwFlags
0x180004f77  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180004f7e  xor     edx, edx; szContainer
0x180004f80  lea     rcx, [rsp+880h+phProv]; phProv
0x180004f85  call    cs:__imp_CryptAcquireContextW
0x180004f8b  test    eax, eax
0x180004f8d  jnz     loc_180005018
0x180004f93  call    cs:__imp_GetLastError
0x180004f99  mov     ebx, eax
0x180004f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fa2  lea     rax, WPP_GLOBAL_Control
0x180004fa9  cmp     rcx, rax
0x180004fac  jz      short loc_180004FCB
0x180004fae  test    byte ptr [rcx+1Ch], 40h
0x180004fb2  jz      short loc_180004FCB
0x180004fb4  cmp     byte ptr [rcx+19h], 1
0x180004fb8  jb      short loc_180004FCB
0x180004fba  mov     rcx, [rcx+10h]
0x180004fbe  mov     edx, 8Ah
0x180004fc3  mov     r9d, ebx
0x180004fc6  call    WPP_SF_d
0x180004fcb  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180004fd3  jz      loc_180005342
0x180004fd9  xor     eax, eax
0x180004fdb  lea     rdx, aCryptacquireco; "CryptAcquireContext for enhanced crypto"...
0x180004fe2  mov     r8d, ebx
0x180004fe5  mov     word ptr [rsp+880h+var_830], ax
0x180004fea  lea     rcx, [rsp+880h+var_830]
0x180004fef  call    FormatRRASErrorString
0x180004ff4  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180004ffb  lea     r8, [rsp+880h+var_830]
0x180005000  mov     rcx, cs:gSstpCfgEtwContext
0x180005007  mov     rax, cs:gSstpCfgTemplateFunc
0x18000500e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005013  jmp     loc_180005342
0x180005018  lea     rdi, [rsi+10h]
0x18000501c  test    r14b, 2
0x180005020  jz      loc_180005197
0x180005026  mov     r9, [rsi+8]; pbEncoded
0x18000502a  lea     rax, [rsp+880h+var_840]
0x18000502f  mov     rcx, [rsp+880h+phProv]; hCryptProv
0x180005034  xor     r8d, r8d; dwFlags
0x180005037  mov     [rsp+880h+pcbComputedHash], rax; pcbComputedHash
0x18000503c  mov     edx, 800Ch; Algid
0x180005041  mov     eax, [rdi]
0x180005043  mov     [rsp+880h+pbComputedHash], 0; pbComputedHash
0x18000504c  mov     [rsp+880h+dwFlags], eax; cbEncoded
0x180005050  mov     [rsp+880h+var_840], 0
0x180005058  call    cs:__imp_CryptHashCertificate
0x18000505e  test    eax, eax
0x180005060  jz      loc_180005145
0x180005066  cmp     [rsp+880h+var_840], 20h ; ' '
0x18000506b  jnz     loc_1800050F7
0x180005071  mov     r9, [rsi+8]; pbEncoded
0x180005075  lea     rax, [rsp+880h+var_840]
0x18000507a  mov     rcx, [rsp+880h+phProv]; hCryptProv
0x18000507f  xor     r8d, r8d; dwFlags
0x180005082  mov     [rsp+880h+pcbComputedHash], rax; pcbComputedHash
0x180005087  mov     edx, 800Ch; Algid
0x18000508c  mov     eax, [rdi]
0x18000508e  mov     [rsp+880h+pbComputedHash], rbx; pbComputedHash
0x180005093  mov     [rsp+880h+dwFlags], eax; cbEncoded
0x180005097  call    cs:__imp_CryptHashCertificate
0x18000509d  test    eax, eax
0x18000509f  jnz     loc_180005197
0x1800050a5  call    cs:__imp_GetLastError
0x1800050ab  mov     ebx, eax
0x1800050ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050b4  lea     rax, WPP_GLOBAL_Control
0x1800050bb  cmp     rcx, rax
0x1800050be  jz      short loc_1800050DD
0x1800050c0  test    byte ptr [rcx+1Ch], 40h
0x1800050c4  jz      short loc_1800050DD
0x1800050c6  cmp     byte ptr [rcx+19h], 1
0x1800050ca  jb      short loc_1800050DD
0x1800050cc  mov     rcx, [rcx+10h]
0x1800050d0  mov     edx, 8Bh
0x1800050d5  mov     r9d, ebx
0x1800050d8  call    WPP_SF_d
0x1800050dd  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800050e5  jz      loc_180005335
0x1800050eb  lea     rdx, aUnableToRetrie_0; "Unable to retrieve the certificate hash"...
0x1800050f2  jmp     loc_180005302
0x1800050f7  mov     ebx, 80091007h
0x1800050fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005103  lea     rax, WPP_GLOBAL_Control
0x18000510a  cmp     rcx, rax
0x18000510d  jz      short loc_180005129
0x18000510f  test    byte ptr [rcx+1Ch], 40h
0x180005113  jz      short loc_180005129
0x180005115  cmp     byte ptr [rcx+19h], 1
0x180005119  jb      short loc_180005129
0x18000511b  mov     rcx, [rcx+10h]
0x18000511f  mov     edx, 8Ch
0x180005124  call    WPP_SF_
0x180005129  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180005130  test    rdx, rdx
0x180005133  jz      loc_180005335
0x180005139  lea     r8, aUnsupportedHas; "Unsupported hash length returned for SH"...
0x180005140  jmp     loc_180005322
0x180005145  call    cs:__imp_GetLastError
0x18000514b  mov     ebx, eax
0x18000514d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005154  lea     rax, WPP_GLOBAL_Control
0x18000515b  cmp     rcx, rax
0x18000515e  jz      short loc_18000517D
0x180005160  test    byte ptr [rcx+1Ch], 40h
0x180005164  jz      short loc_18000517D
0x180005166  cmp     byte ptr [rcx+19h], 1
0x18000516a  jb      short loc_18000517D
0x18000516c  mov     rcx, [rcx+10h]
0x180005170  mov     edx, 8Dh
0x180005175  mov     r9d, ebx
0x180005178  call    WPP_SF_d
0x18000517d  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180005185  jz      loc_180005335
0x18000518b  lea     rdx, aUnableToRetrie_1; "Unable to retrieve the certificate hash"...
0x180005192  jmp     loc_180005302
0x180005197  xor     ebx, ebx
0x180005199  test    r14b, 1
0x18000519d  jz      loc_180005335
0x1800051a3  mov     r9, [rsi+8]; pbEncoded
0x1800051a7  lea     rax, [rsp+880h+var_840]
0x1800051ac  mov     rcx, [rsp+880h+phProv]; hCryptProv
0x1800051b1  mov     r14d, 8004h
0x1800051b7  mov     [rsp+880h+pcbComputedHash], rax; pcbComputedHash
0x1800051bc  xor     r8d, r8d; dwFlags
0x1800051bf  mov     eax, [rdi]
0x1800051c1  mov     edx, r14d; Algid
0x1800051c4  mov     [rsp+880h+pbComputedHash], rbx; pbComputedHash
0x1800051c9  mov     [rsp+880h+dwFlags], eax; cbEncoded
0x1800051cd  mov     [rsp+880h+var_840], ebx
0x1800051d1  call    cs:__imp_CryptHashCertificate
0x1800051d7  test    eax, eax
0x1800051d9  jz      loc_1800052B9
0x1800051df  cmp     [rsp+880h+var_840], 14h
0x1800051e4  jnz     loc_18000526E
0x1800051ea  mov     r9, [rsi+8]; pbEncoded
0x1800051ee  lea     rax, [rsp+880h+var_840]
0x1800051f3  mov     rcx, [rsp+880h+phProv]; hCryptProv
0x1800051f8  xor     r8d, r8d; dwFlags
0x1800051fb  mov     [rsp+880h+pcbComputedHash], rax; pcbComputedHash
0x180005200  mov     edx, r14d; Algid
0x180005203  mov     eax, [rdi]
0x180005205  mov     [rsp+880h+pbComputedHash], r15; pbComputedHash
0x18000520a  mov     [rsp+880h+dwFlags], eax; cbEncoded
0x18000520e  call    cs:__imp_CryptHashCertificate
0x180005214  test    eax, eax
0x180005216  jnz     loc_180005335
0x18000521c  call    cs:__imp_GetLastError
0x180005222  mov     ebx, eax
0x180005224  mov     rcx, cs:WPP_GLOBAL_Control
0x18000522b  lea     rax, WPP_GLOBAL_Control
0x180005232  cmp     rcx, rax
0x180005235  jz      short loc_180005254
0x180005237  test    byte ptr [rcx+1Ch], 40h
0x18000523b  jz      short loc_180005254
0x18000523d  cmp     byte ptr [rcx+19h], 1
0x180005241  jb      short loc_180005254
0x180005243  mov     rcx, [rcx+10h]
0x180005247  mov     edx, 8Eh
0x18000524c  mov     r9d, ebx
0x18000524f  call    WPP_SF_d
0x180005254  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000525c  jz      loc_180005335
0x180005262  lea     rdx, aUnableToRetrie; "Unable to retrieve the certificate hash"...
0x180005269  jmp     loc_180005302
0x18000526e  mov     ebx, 80091007h
0x180005273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000527a  lea     rax, WPP_GLOBAL_Control
0x180005281  cmp     rcx, rax
0x180005284  jz      short loc_1800052A0
0x180005286  test    byte ptr [rcx+1Ch], 40h
0x18000528a  jz      short loc_1800052A0
0x18000528c  cmp     byte ptr [rcx+19h], 1
0x180005290  jb      short loc_1800052A0
0x180005292  mov     rcx, [rcx+10h]
0x180005296  mov     edx, 8Fh
0x18000529b  call    WPP_SF_
0x1800052a0  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800052a7  test    rdx, rdx
0x1800052aa  jz      loc_180005335
0x1800052b0  lea     r8, aUnsupportedHas_0; "Unsupported hash length returned for SH"...
0x1800052b7  jmp     short loc_180005322
0x1800052b9  call    cs:__imp_GetLastError
0x1800052bf  mov     ebx, eax
0x1800052c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052c8  lea     rax, WPP_GLOBAL_Control
0x1800052cf  cmp     rcx, rax
0x1800052d2  jz      short loc_1800052F1
0x1800052d4  test    byte ptr [rcx+1Ch], 40h
0x1800052d8  jz      short loc_1800052F1
0x1800052da  cmp     byte ptr [rcx+19h], 1
0x1800052de  jb      short loc_1800052F1
0x1800052e0  mov     rcx, [rcx+10h]
0x1800052e4  mov     edx, 90h
0x1800052e9  mov     r9d, ebx
0x1800052ec  call    WPP_SF_d
0x1800052f1  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800052f9  jz      short loc_180005335
0x1800052fb  lea     rdx, aUnableToRetrie_2; "Unable to retrieve the certificate hash"...
0x180005302  xor     eax, eax
0x180005304  lea     rcx, [rsp+880h+var_830]
0x180005309  mov     r8d, ebx
0x18000530c  mov     word ptr [rsp+880h+var_830], ax
0x180005311  call    FormatRRASErrorString
0x180005316  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000531d  lea     r8, [rsp+880h+var_830]
0x180005322  mov     rcx, cs:gSstpCfgEtwContext
0x180005329  mov     rax, cs:gSstpCfgTemplateFunc
0x180005330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005335  mov     rcx, [rsp+880h+phProv]; hProv
0x18000533a  xor     edx, edx; dwFlags
0x18000533c  call    cs:__imp_CryptReleaseContext
0x180005342  mov     eax, ebx
0x180005344  mov     rcx, [rbp+780h+var_30]
0x18000534b  xor     rcx, rsp; StackCookie
0x18000534e  call    __security_check_cookie
0x180005353  mov     rbx, [rsp+880h+arg_8]
0x18000535b  add     rsp, 860h
0x180005362  pop     r15
0x180005364  pop     r14
0x180005366  pop     rdi
0x180005367  pop     rsi
0x180005368  pop     rbp
0x180005369  retn
```
