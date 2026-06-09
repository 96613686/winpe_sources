# Microsoft::Diagnostics::XmlFileSignatureVerifier::ExtractSigningDate(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_FILETIME *)

- ea: `0x18009a564`
- end: `0x18009a854`
- name: `?ExtractSigningDate@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAU_FILETIME@@@Z`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009a184`

## callees

- `0x180026ecc`
- `0x18009a564`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a79f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a79f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009a83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a5c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a5c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009a6a8`
- `CRYPT32!CryptStringToBinaryW` at `0x18009a5b0`
- `CRYPT32!CryptStringToBinaryW` at `0x18009a605`
- `CRYPT32!CryptStringToBinaryW` at `0x18009a5b0`
- `CRYPT32!CryptStringToBinaryW` at `0x18009a605`
- `CRYPT32!CryptMsgClose` at `0x18009a790`
- `CRYPT32!CryptMsgClose` at `0x18009a7c1`
- `CRYPT32!CryptMsgClose` at `0x18009a82b`
- `CRYPT32!CryptMsgClose` at `0x18009a790`
- `CRYPT32!CryptMsgClose` at `0x18009a7c1`
- `CRYPT32!CryptMsgClose` at `0x18009a82b`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18009a638`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18009a638`
- `CRYPT32!CryptMsgUpdate` at `0x18009a65d`
- `CRYPT32!CryptMsgUpdate` at `0x18009a65d`
- `CRYPT32!CryptMsgGetParam` at `0x18009a691`
- `CRYPT32!CryptMsgGetParam` at `0x18009a6d5`
- `CRYPT32!CryptMsgGetParam` at `0x18009a691`
- `CRYPT32!CryptMsgGetParam` at `0x18009a6d5`
- `CRYPT32!CryptDecodeObject` at `0x18009a766`
- `CRYPT32!CryptDecodeObject` at `0x18009a766`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18009a709`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x18009a709`

## string_xrefs

- `0x18009a7ea`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x18009a80f`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::XmlFileSignatureVerifier::ExtractSigningDate(__int64 a1, _QWORD *a2)
{
  DWORD v2; // ebx
  const WCHAR *v3; // rsi
  const WCHAR *v5; // rcx
  void *v6; // rdi
  HCRYPTMSG v7; // rax
  void *v8; // rsi
  _QWORD *v9; // rbx
  __int64 i; // r14
  __int64 v11; // r8
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int pcbBinary; // [rsp+20h] [rbp-30h]
  __int64 pvStructInfo; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  DWORD pcbStructInfo; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *(_DWORD *)(a1 + 8);
  v3 = *(const WCHAR **)a1;
  v5 = *(const WCHAR **)a1;
  cbData = 0;
  if ( CryptStringToBinaryW(v5, v2, 1u, 0, &cbData, 0, 0) )
  {
    v6 = CoTaskMemAlloc(cbData);
    if ( !v6 )
    {
      v13 = -2147024882;
      v14 = 84;
      goto LABEL_19;
    }
    if ( CryptStringToBinaryW(v3, v2, 1u, (BYTE *)v6, &cbData, 0, 0) )
    {
      v7 = CryptMsgOpenToDecode(0x10000u, 0, 0, 0, 0, 0);
      v8 = v7;
      if ( v7 )
      {
        if ( CryptMsgUpdate(v7, (const BYTE *)v6, cbData, 1) )
        {
          pcbData = 0;
          if ( CryptMsgGetParam(v8, 6u, 0, 0, &pcbData) )
          {
            v9 = CoTaskMemAlloc(pcbData);
            if ( !v9 )
            {
              v13 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x66,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                (const char *)0x8007000ELL,
                pcbBinary);
              CryptMsgClose(v8);
              CoTaskMemFree(v6);
              return v13;
            }
            if ( CryptMsgGetParam(v8, 6u, 0, v9, &pcbData) )
            {
              for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 26); i = (unsigned int)(i + 1) )
              {
                if ( !lstrcmpA("1.2.840.113549.1.9.5", *(LPCSTR *)(v9[14] + 24 * i)) )
                {
                  _mm_lfence();
                  pvStructInfo = 0;
                  pcbStructInfo = 8;
                  v11 = *(_QWORD *)(v9[14] + 24 * i + 16);
                  if ( !CryptDecodeObject(
                          0x10001u,
                          "1.2.840.113549.1.9.5",
                          *(const BYTE **)(v11 + 8),
                          *(_DWORD *)v11,
                          0,
                          &pvStructInfo,
                          &pcbStructInfo) )
                    break;
                  *a2 = pvStructInfo;
                  CoTaskMemFree(v9);
                  CryptMsgClose(v8);
                  CoTaskMemFree(v6);
                  return 0;
                }
              }
            }
            CoTaskMemFree(v9);
          }
        }
        CryptMsgClose(v8);
      }
    }
    CoTaskMemFree(v6);
  }
  v13 = -2147418113;
  v14 = 130;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
    (const char *)v13,
    pcbBinary);
  return v13;
}

```

## disassembly

```asm
0x18009a564  push    rbp
0x18009a566  push    rbx
0x18009a567  push    rsi
0x18009a568  push    rdi
0x18009a569  push    r12
0x18009a56b  push    r14
0x18009a56d  push    r15
0x18009a56f  mov     rbp, rsp
0x18009a572  sub     rsp, 50h
0x18009a576  mov     ebx, [rcx+8]
0x18009a579  lea     rax, [rbp+cbData]
0x18009a57d  mov     rsi, [rcx]
0x18009a580  xor     r9d, r9d; pbBinary
0x18009a583  mov     r12, rdx
0x18009a586  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x18009a58f  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x18009a598  mov     edx, ebx; cchString
0x18009a59a  mov     rcx, rsi; pszString
0x18009a59d  mov     [rbp+cbData], 0
0x18009a5a4  lea     r14d, [r9+1]
0x18009a5a8  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x18009a5ad  mov     r8d, r14d; dwFlags
0x18009a5b0  call    cs:__imp_CryptStringToBinaryW
0x18009a5b7  nop     dword ptr [rax+rax+00h]
0x18009a5bc  test    eax, eax
0x18009a5be  jz      loc_18009A7DC
0x18009a5c4  mov     ecx, [rbp+cbData]; cb
0x18009a5c7  call    cs:__imp_CoTaskMemAlloc
0x18009a5ce  nop     dword ptr [rax+rax+00h]
0x18009a5d3  mov     rdi, rax
0x18009a5d6  test    rax, rax
0x18009a5d9  jz      loc_18009A848
0x18009a5df  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x18009a5e8  lea     rax, [rbp+cbData]
0x18009a5ec  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x18009a5f5  mov     r9, rdi; pbBinary
0x18009a5f8  mov     r8d, r14d; dwFlags
0x18009a5fb  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x18009a600  mov     edx, ebx; cchString
0x18009a602  mov     rcx, rsi; pszString
0x18009a605  call    cs:__imp_CryptStringToBinaryW
0x18009a60c  nop     dword ptr [rax+rax+00h]
0x18009a611  test    eax, eax
0x18009a613  jz      loc_18009A7CD
0x18009a619  mov     [rsp+50h+pdwSkip], 0; pStreamInfo
0x18009a622  xor     r9d, r9d; hCryptProv
0x18009a625  xor     r8d, r8d; dwMsgType
0x18009a628  mov     [rsp+50h+pcbBinary], 0; pRecipientInfo
0x18009a631  xor     edx, edx; dwFlags
0x18009a633  mov     ecx, 10000h; dwMsgEncodingType
0x18009a638  call    cs:__imp_CryptMsgOpenToDecode
0x18009a63f  nop     dword ptr [rax+rax+00h]
0x18009a644  mov     rsi, rax
0x18009a647  test    rax, rax
0x18009a64a  jz      loc_18009A7CD
0x18009a650  mov     r8d, [rbp+cbData]; cbData
0x18009a654  mov     r9d, r14d; fFinal
0x18009a657  mov     rdx, rdi; pbData
0x18009a65a  mov     rcx, rax; hCryptMsg
0x18009a65d  call    cs:__imp_CryptMsgUpdate
0x18009a664  nop     dword ptr [rax+rax+00h]
0x18009a669  test    eax, eax
0x18009a66b  jz      loc_18009A7BE
0x18009a671  xor     r9d, r9d; pvData
0x18009a674  mov     [rbp+pcbData], 0
0x18009a67b  lea     rax, [rbp+pcbData]
0x18009a67f  xor     r8d, r8d; dwIndex
0x18009a682  mov     rcx, rsi; hCryptMsg
0x18009a685  mov     [rsp+50h+pcbBinary], rax; int
0x18009a68a  lea     r14d, [r9+6]
0x18009a68e  mov     edx, r14d; dwParamType
0x18009a691  call    cs:__imp_CryptMsgGetParam
0x18009a698  nop     dword ptr [rax+rax+00h]
0x18009a69d  test    eax, eax
0x18009a69f  jz      loc_18009A7BE
0x18009a6a5  mov     ecx, [rbp+pcbData]; cb
0x18009a6a8  call    cs:__imp_CoTaskMemAlloc
0x18009a6af  nop     dword ptr [rax+rax+00h]
0x18009a6b4  mov     rbx, rax
0x18009a6b7  test    rax, rax
0x18009a6ba  jz      loc_18009A80B
0x18009a6c0  lea     rax, [rbp+pcbData]
0x18009a6c4  mov     r9, rbx; pvData
0x18009a6c7  xor     r8d, r8d; dwIndex
0x18009a6ca  mov     [rsp+50h+pcbBinary], rax; int
0x18009a6cf  mov     edx, r14d; dwParamType
0x18009a6d2  mov     rcx, rsi; hCryptMsg
0x18009a6d5  call    cs:__imp_CryptMsgGetParam
0x18009a6dc  nop     dword ptr [rax+rax+00h]
0x18009a6e1  test    eax, eax
0x18009a6e3  jz      loc_18009A7AF
0x18009a6e9  xor     r14d, r14d
0x18009a6ec  cmp     r14d, [rbx+68h]
0x18009a6f0  jnb     loc_18009A7AF
0x18009a6f6  mov     rdx, [rbx+70h]
0x18009a6fa  lea     r15, [r14+r14*2]
0x18009a6fe  lea     rcx, szStructType; "1.2.840.113549.1.9.5"
0x18009a705  mov     rdx, [rdx+r15*8]; lpString2
0x18009a709  call    cs:__imp_lstrcmpA
0x18009a710  nop     dword ptr [rax+rax+00h]
0x18009a715  test    eax, eax
0x18009a717  jz      short loc_18009A71E
0x18009a719  inc     r14d
0x18009a71c  jmp     short loc_18009A6EC
0x18009a71e  lfence
0x18009a721  mov     [rbp+pvStructInfo], 0
0x18009a729  lea     rdx, szStructType; "1.2.840.113549.1.9.5"
0x18009a730  mov     [rbp+pcbStructInfo], 8
0x18009a737  mov     ecx, 10001h; dwCertEncodingType
0x18009a73c  mov     rax, [rbx+70h]
0x18009a740  mov     r8, [rax+r15*8+10h]
0x18009a745  lea     rax, [rbp+pcbStructInfo]
0x18009a749  mov     [rsp+50h+pdwFlags], rax; pcbStructInfo
0x18009a74e  lea     rax, [rbp+pvStructInfo]
0x18009a752  mov     [rsp+50h+pdwSkip], rax; pvStructInfo
0x18009a757  mov     dword ptr [rsp+50h+pcbBinary], 0; dwFlags
0x18009a75f  mov     r9d, [r8]; cbEncoded
0x18009a762  mov     r8, [r8+8]; pbEncoded
0x18009a766  call    cs:__imp_CryptDecodeObject
0x18009a76d  nop     dword ptr [rax+rax+00h]
0x18009a772  test    eax, eax
0x18009a774  jz      short loc_18009A7AF
0x18009a776  mov     rax, [rbp+pvStructInfo]
0x18009a77a  mov     rcx, rbx; pv
0x18009a77d  mov     [r12], rax
0x18009a781  call    cs:__imp_CoTaskMemFree
0x18009a788  nop     dword ptr [rax+rax+00h]
0x18009a78d  mov     rcx, rsi; hCryptMsg
0x18009a790  call    cs:__imp_CryptMsgClose
0x18009a797  nop     dword ptr [rax+rax+00h]
0x18009a79c  mov     rcx, rdi; pv
0x18009a79f  call    cs:__imp_CoTaskMemFree
0x18009a7a6  nop     dword ptr [rax+rax+00h]
0x18009a7ab  xor     eax, eax
0x18009a7ad  jmp     short loc_18009A7FB
0x18009a7af  mov     rcx, rbx; pv
0x18009a7b2  call    cs:__imp_CoTaskMemFree
0x18009a7b9  nop     dword ptr [rax+rax+00h]
0x18009a7be  mov     rcx, rsi; hCryptMsg
0x18009a7c1  call    cs:__imp_CryptMsgClose
0x18009a7c8  nop     dword ptr [rax+rax+00h]
0x18009a7cd  mov     rcx, rdi; pv
0x18009a7d0  call    cs:__imp_CoTaskMemFree
0x18009a7d7  nop     dword ptr [rax+rax+00h]
0x18009a7dc  mov     ebx, 8000FFFFh
0x18009a7e1  mov     edx, 82h; void *
0x18009a7e6  mov     rcx, [rbp+38h]; this
0x18009a7ea  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x18009a7f1  mov     r9d, ebx; char *
0x18009a7f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a7f9  mov     eax, ebx
0x18009a7fb  add     rsp, 50h
0x18009a7ff  pop     r15
0x18009a801  pop     r14
0x18009a803  pop     r12
0x18009a805  pop     rdi
0x18009a806  pop     rsi
0x18009a807  pop     rbx
0x18009a808  pop     rbp
0x18009a809  retn
0x18009a80b  mov     rcx, [rbp+38h]; this
0x18009a80f  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x18009a816  mov     ebx, 8007000Eh
0x18009a81b  mov     edx, 66h ; 'f'; void *
0x18009a820  mov     r9d, ebx; char *
0x18009a823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a828  mov     rcx, rsi; hCryptMsg
0x18009a82b  call    cs:__imp_CryptMsgClose
0x18009a832  nop     dword ptr [rax+rax+00h]
0x18009a837  mov     rcx, rdi; pv
0x18009a83a  call    cs:__imp_CoTaskMemFree
0x18009a841  nop     dword ptr [rax+rax+00h]
0x18009a846  jmp     short loc_18009A7F9
0x18009a848  mov     ebx, 8007000Eh
0x18009a84d  mov     edx, 54h ; 'T'
0x18009a852  jmp     short loc_18009A7E6
```
