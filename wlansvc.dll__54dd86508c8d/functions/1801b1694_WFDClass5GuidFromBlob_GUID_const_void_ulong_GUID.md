# WFDClass5GuidFromBlob(_GUID const *,void *,ulong,_GUID *)

- ea: `0x1801b1694`
- end: `0x1801b18f4`
- name: `?WFDClass5GuidFromBlob@@YAKPEBU_GUID@@PEAXKPEAU1@@Z`
- size: `608`
- prototype: `unsigned int(const struct _GUID *, void *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800f8028`

## callees

- `0x180106340`
- `0x180107318`
- `0x1801b1694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801b18b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801b18c7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801b18b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801b18c7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801b1746`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801b1810`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801b1746`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801b1810`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801b18ab`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801b18ab`
- `bcrypt!BCryptCreateHash` at `0x1801b1774`
- `bcrypt!BCryptCreateHash` at `0x1801b1774`
- `bcrypt!BCryptGetProperty` at `0x1801b1733`
- `bcrypt!BCryptGetProperty` at `0x1801b17fd`
- `bcrypt!BCryptGetProperty` at `0x1801b1733`
- `bcrypt!BCryptGetProperty` at `0x1801b17fd`
- `bcrypt!BCryptHashData` at `0x1801b17af`
- `bcrypt!BCryptHashData` at `0x1801b17cd`
- `bcrypt!BCryptHashData` at `0x1801b17af`
- `bcrypt!BCryptHashData` at `0x1801b17cd`
- `bcrypt!BCryptFinishHash` at `0x1801b1833`
- `bcrypt!BCryptFinishHash` at `0x1801b1833`
- `bcrypt!BCryptDestroyHash` at `0x1801b189a`
- `bcrypt!BCryptDestroyHash` at `0x1801b189a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801b1703`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801b1703`

## pseudocode

```c
__int64 __fastcall WFDClass5GuidFromBlob(const struct _GUID *a1, UCHAR *a2, __int64 a3, struct _GUID *a4)
{
  UCHAR *v6; // rsi
  UCHAR *v7; // rdi
  unsigned int Property; // ebx
  UCHAR *v9; // rax
  size_t v10; // r14
  UCHAR *v11; // rax
  unsigned __int16 Data3; // ax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  UCHAR pbInput[16]; // [rsp+58h] [rbp-18h] BYREF

  phAlgorithm = 0;
  *a4 = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)pbInput = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( !Property )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( !Property )
    {
      v9 = (UCHAR *)malloc(*(unsigned int *)pbOutput);
      v6 = v9;
      if ( !v9 )
      {
LABEL_9:
        Property = 8;
        goto LABEL_14;
      }
      Property = BCryptCreateHash(phAlgorithm, &phHash, v9, *(ULONG *)pbOutput, 0, 0, 0);
      if ( !Property )
      {
        v10 = 16;
        *(_QWORD *)&pbInput[8] = 0x22C2D206EF863CB9LL;
        *(_DWORD *)pbInput = -225926718;
        *(_DWORD *)&pbInput[4] = -1521860860;
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( !Property )
        {
          Property = BCryptHashData(phHash, a2, 0x2Cu, 0);
          if ( !Property )
          {
            Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
            if ( !Property )
            {
              v11 = (UCHAR *)malloc(*(unsigned int *)pbOutput);
              v7 = v11;
              if ( !v11 )
                goto LABEL_9;
              Property = BCryptFinishHash(phHash, v11, *(ULONG *)pbOutput, 0);
              if ( !Property )
              {
                if ( *(_DWORD *)pbOutput < 0x10u )
                  v10 = *(unsigned int *)pbOutput;
                memcpy_0(a4, v7, v10);
                a4->Data1 = _byteswap_ulong(a4->Data1);
                a4->Data2 = __ROR2__(a4->Data2, 8);
                Data3 = a4->Data3;
                a4->Data4[0] &= 0x3Fu;
                a4->Data4[0] |= 0x80u;
                a4->Data3 = __ROR2__(Data3, 8) & 0xFFF | 0x5000;
              }
            }
          }
        }
      }
    }
  }
LABEL_14:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v6 )
    free(v6);
  if ( v7 )
    free(v7);
  return Property;
}

```

## disassembly

```asm
0x1801b1694  mov     [rsp-28h+arg_0], rbx
0x1801b1699  mov     [rsp-28h+arg_10], rsi
0x1801b169e  push    rbp
0x1801b169f  push    rdi
0x1801b16a0  push    r12
0x1801b16a2  push    r14
0x1801b16a4  push    r15
0x1801b16a6  mov     rbp, rsp
0x1801b16a9  sub     rsp, 70h
0x1801b16ad  mov     rax, cs:__security_cookie
0x1801b16b4  xor     rax, rsp
0x1801b16b7  mov     [rbp+var_8], rax
0x1801b16bb  xorps   xmm0, xmm0
0x1801b16be  mov     [rbp+phAlgorithm], 0
0x1801b16c6  movups  xmmword ptr [r9], xmm0
0x1801b16ca  mov     r15, r9
0x1801b16cd  mov     [rbp+phHash], 0
0x1801b16d5  mov     r12, rdx
0x1801b16d8  mov     dword ptr [rbp+pbOutput], 0
0x1801b16df  xor     r9d, r9d; dwFlags
0x1801b16e2  mov     [rbp+var_2C], 0
0x1801b16e9  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1801b16f0  xor     esi, esi
0x1801b16f2  lea     rdx, aSha1; "SHA1"
0x1801b16f9  xor     edi, edi
0x1801b16fb  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1801b16ff  movups  xmmword ptr [rbp+pbInput], xmm0
0x1801b1703  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801b1709  mov     ebx, eax
0x1801b170b  test    eax, eax
0x1801b170d  jnz     loc_1801B1891
0x1801b1713  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801b1717  lea     rax, [rbp+var_2C]
0x1801b171b  mov     [rsp+70h+dwFlags], esi; dwFlags
0x1801b171f  lea     r9d, [rsi+4]; cbOutput
0x1801b1723  lea     r8, [rbp+pbOutput]; pbOutput
0x1801b1727  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1801b172c  lea     rdx, pszProperty; "ObjectLength"
0x1801b1733  call    cs:__imp_BCryptGetProperty
0x1801b1739  mov     ebx, eax
0x1801b173b  test    eax, eax
0x1801b173d  jnz     loc_1801B1891
0x1801b1743  mov     ecx, dword ptr [rbp+pbOutput]; Size
0x1801b1746  call    cs:__imp_malloc
0x1801b174c  mov     rsi, rax
0x1801b174f  test    rax, rax
0x1801b1752  jz      loc_1801B181E
0x1801b1758  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x1801b175c  lea     rdx, [rbp+phHash]; phHash
0x1801b1760  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801b1764  mov     r8, rax; pbHashObject
0x1801b1767  mov     [rsp+70h+var_40], edi; dwFlags
0x1801b176b  mov     [rsp+70h+dwFlags], edi; cbSecret
0x1801b176f  mov     [rsp+70h+pcbResult], rdi; pbSecret
0x1801b1774  call    cs:__imp_BCryptCreateHash
0x1801b177a  mov     ebx, eax
0x1801b177c  test    eax, eax
0x1801b177e  jnz     loc_1801B1891
0x1801b1784  mov     rax, cs:qword_18025ABB8
0x1801b178b  lea     r14d, [rdi+10h]
0x1801b178f  mov     rcx, [rbp+phHash]; hHash
0x1801b1793  lea     rdx, [rbp+pbInput]; pbInput
0x1801b1797  mov     r8d, r14d; cbInput
0x1801b179a  mov     qword ptr [rbp+pbInput+8], rax
0x1801b179e  xor     r9d, r9d; dwFlags
0x1801b17a1  mov     dword ptr [rbp+pbInput], 0F288A1C2h
0x1801b17a8  mov     dword ptr [rbp+pbInput+4], 0A54A3F04h
0x1801b17af  call    cs:__imp_BCryptHashData
0x1801b17b5  mov     ebx, eax
0x1801b17b7  test    eax, eax
0x1801b17b9  jnz     loc_1801B1891
0x1801b17bf  mov     rcx, [rbp+phHash]; hHash
0x1801b17c3  lea     r8d, [rdi+2Ch]; cbInput
0x1801b17c7  xor     r9d, r9d; dwFlags
0x1801b17ca  mov     rdx, r12; pbInput
0x1801b17cd  call    cs:__imp_BCryptHashData
0x1801b17d3  mov     ebx, eax
0x1801b17d5  test    eax, eax
0x1801b17d7  jnz     loc_1801B1891
0x1801b17dd  mov     rcx, [rbp+phAlgorithm]; hObject
0x1801b17e1  lea     rax, [rbp+var_2C]
0x1801b17e5  mov     [rsp+70h+dwFlags], edi; dwFlags
0x1801b17e9  lea     r9d, [rdi+4]; cbOutput
0x1801b17ed  lea     r8, [rbp+pbOutput]; pbOutput
0x1801b17f1  mov     [rsp+70h+pcbResult], rax; pcbResult
0x1801b17f6  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1801b17fd  call    cs:__imp_BCryptGetProperty
0x1801b1803  mov     ebx, eax
0x1801b1805  test    eax, eax
0x1801b1807  jnz     loc_1801B1891
0x1801b180d  mov     ecx, dword ptr [rbp+pbOutput]; Size
0x1801b1810  call    cs:__imp_malloc
0x1801b1816  mov     rdi, rax
0x1801b1819  test    rax, rax
0x1801b181c  jnz     short loc_1801B1825
0x1801b181e  mov     ebx, 8
0x1801b1823  jmp     short loc_1801B1891
0x1801b1825  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x1801b1829  xor     r9d, r9d; dwFlags
0x1801b182c  mov     rcx, [rbp+phHash]; hHash
0x1801b1830  mov     rdx, rdi; pbOutput
0x1801b1833  call    cs:__imp_BCryptFinishHash
0x1801b1839  mov     ebx, eax
0x1801b183b  test    eax, eax
0x1801b183d  jnz     short loc_1801B1891
0x1801b183f  cmp     dword ptr [rbp+pbOutput], r14d
0x1801b1843  jnb     short loc_1801B1849
0x1801b1845  mov     r14d, dword ptr [rbp+pbOutput]
0x1801b1849  mov     r8, r14; Size
0x1801b184c  mov     rdx, rdi; Src
0x1801b184f  mov     rcx, r15; void *
0x1801b1852  call    memcpy_0
0x1801b1857  mov     eax, [r15]
0x1801b185a  mov     ecx, 0FFFh
0x1801b185f  bswap   eax
0x1801b1861  mov     [r15], eax
0x1801b1864  movzx   eax, word ptr [r15+4]
0x1801b1869  ror     ax, 8
0x1801b186d  mov     [r15+4], ax
0x1801b1872  movzx   eax, word ptr [r15+6]
0x1801b1877  and     byte ptr [r15+8], 3Fh
0x1801b187c  ror     ax, 8
0x1801b1880  and     ax, cx
0x1801b1883  or      ax, 5000h
0x1801b1887  or      byte ptr [r15+8], 80h
0x1801b188c  mov     [r15+6], ax
0x1801b1891  mov     rcx, [rbp+phHash]; hHash
0x1801b1895  test    rcx, rcx
0x1801b1898  jz      short loc_1801B18A0
0x1801b189a  call    cs:__imp_BCryptDestroyHash
0x1801b18a0  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801b18a4  test    rcx, rcx
0x1801b18a7  jz      short loc_1801B18B1
0x1801b18a9  xor     edx, edx; dwFlags
0x1801b18ab  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801b18b1  test    rsi, rsi
0x1801b18b4  jz      short loc_1801B18BF
0x1801b18b6  mov     rcx, rsi; Block
0x1801b18b9  call    cs:__imp_free
0x1801b18bf  test    rdi, rdi
0x1801b18c2  jz      short loc_1801B18CD
0x1801b18c4  mov     rcx, rdi; Block
0x1801b18c7  call    cs:__imp_free
0x1801b18cd  mov     eax, ebx
0x1801b18cf  mov     rcx, [rbp+var_8]
0x1801b18d3  xor     rcx, rsp; StackCookie
0x1801b18d6  call    __security_check_cookie
0x1801b18db  lea     r11, [rsp+70h+var_s0]
0x1801b18e0  mov     rbx, [r11+30h]
0x1801b18e4  mov     rsi, [r11+40h]
0x1801b18e8  mov     rsp, r11
0x1801b18eb  pop     r15
0x1801b18ed  pop     r14
0x1801b18ef  pop     r12
0x1801b18f1  pop     rdi
0x1801b18f2  pop     rbp
0x1801b18f3  retn
```
