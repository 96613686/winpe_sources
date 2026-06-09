# SIPolicyVerifySignedData

- ea: `0x18004d24c`
- end: `0x18004d458`
- name: `SIPolicyVerifySignedData`
- size: `524`
- prototype: `__int64 __fastcall(BYTE *pbSignedBlob, DWORD cbSignedBlob, __int64, __int64, PCCERT_CONTEXT pCertContext, _QWORD *, _DWORD *, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18004a7ec`

## callees

- `0x18002c104`
- `0x18004cac8`
- `0x18004cddc`
- `0x18004d24c`
- `0x18004d460`
- `0x18004d588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d2fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d2fd`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18004d2c9`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18004d2c9`
- `CRYPT32!CryptMsgUpdate` at `0x18004d35a`
- `CRYPT32!CryptMsgUpdate` at `0x18004d35a`
- `CRYPT32!CertFreeCertificateContext` at `0x18004d314`
- `CRYPT32!CertFreeCertificateContext` at `0x18004d314`
- `CRYPT32!CryptMsgClose` at `0x18004d322`
- `CRYPT32!CryptMsgClose` at `0x18004d322`

## pseudocode

```c
__int64 __fastcall SIPolicyVerifySignedData(
        BYTE *pbSignedBlob,
        DWORD cbSignedBlob,
        __int64 a3,
        __int64 a4,
        PCCERT_CONTEXT pCertContext,
        _QWORD *a6,
        _DWORD *a7,
        _OWORD *a8)
{
  _QWORD *v8; // r13
  const CERT_CONTEXT *v11; // rsi
  HCRYPTMSG v12; // rax
  void *v13; // rdi
  signed int LastError; // eax
  unsigned int v15; // ebx
  signed int CryptMessageParam; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int DecodedMessageBlob; // eax
  _DWORD *v21; // rcx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // [rsp+40h] [rbp-40h] BYREF
  __int128 v26; // [rsp+50h] [rbp-30h]
  __int128 v27; // [rsp+60h] [rbp-20h]
  __int64 v28; // [rsp+70h] [rbp-10h]
  int v29; // [rsp+D0h] [rbp+50h] BYREF
  int v30; // [rsp+D4h] [rbp+54h]
  int v31; // [rsp+D8h] [rbp+58h]

  v30 = HIDWORD(a3);
  v8 = a6;
  v28 = 0;
  v29 = 0;
  v31 = 0;
  *a7 = 0;
  pCertContext = 0;
  v11 = 0;
  *v8 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v12 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v13 = v12;
  if ( v12 && CryptMsgUpdate(v12, pbSignedBlob, cbSignedBlob, 1) )
  {
    CryptMessageParam = GetCryptMessageParam(v13, 1u, (__int64)&v29);
    if ( CryptMessageParam >= 0 )
    {
      if ( MEMORY[0] == 2 )
      {
        CryptMessageParam = ValidateOid(v19, v18, v13);
        if ( CryptMessageParam >= 0 )
        {
          DecodedMessageBlob = VerifySignatureGetDecodedMessageBlob(pbSignedBlob, cbSignedBlob, (__int64)&pCertContext);
          v11 = pCertContext;
          CryptMessageParam = DecodedMessageBlob;
          if ( DecodedMessageBlob >= 0 )
          {
            CryptMessageParam = ConvertCertCtxToChainInfo(v13, pCertContext);
            if ( CryptMessageParam >= 0 )
            {
              v21 = a7;
              *v8 = 0;
              *v21 = v31;
              v22 = a8;
              if ( a8 )
              {
                v23 = v26;
                *a8 = v25;
                v24 = v27;
                v22[1] = v23;
                *(_QWORD *)&v23 = v28;
                v22[2] = v24;
                *((_QWORD *)v22 + 6) = v23;
                v28 = 0;
                v25 = 0;
                v26 = 0;
                v27 = 0;
              }
            }
          }
        }
      }
      else
      {
        CryptMessageParam = -1073740760;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    CryptMessageParam = v15 & 0xAFFFFFFF | 0x40000000;
  }
  LocalFree(0);
  SIPolicyFreeSIChainInfo(&v25);
  if ( v11 )
    CertFreeCertificateContext(v11);
  if ( v13 )
    CryptMsgClose(v13);
  if ( CryptMessageParam < 0 )
    return (unsigned int)-1073740760;
  return (unsigned int)CryptMessageParam;
}

```

## disassembly

```asm
0x18004d24c  mov     [rsp-38h+arg_0], rbx
0x18004d251  mov     [rsp-38h+arg_18], r9d
0x18004d256  mov     [rsp-38h+arg_10], r8
0x18004d25b  push    rbp
0x18004d25c  push    rsi
0x18004d25d  push    rdi
0x18004d25e  push    r12
0x18004d260  push    r13
0x18004d262  push    r14
0x18004d264  push    r15
0x18004d266  mov     rbp, rsp
0x18004d269  sub     rsp, 80h
0x18004d270  mov     r13, [rbp+arg_28]
0x18004d274  xor     ebx, ebx
0x18004d276  xorps   xmm0, xmm0
0x18004d279  mov     [rsp+80h+pStreamInfo], rbx; pStreamInfo
0x18004d27e  xor     eax, eax
0x18004d280  mov     [rbp+var_50], rbx
0x18004d284  mov     [rbp+var_10], rax
0x18004d288  mov     r15d, edx
0x18004d28b  mov     rax, [rbp+arg_30]
0x18004d28f  mov     r12, rcx
0x18004d292  xor     r9d, r9d; hCryptProv
0x18004d295  mov     [rbp+var_48], rbx
0x18004d299  xor     r8d, r8d; dwMsgType
0x18004d29c  mov     dword ptr [rbp+arg_10], ebx
0x18004d29f  xor     edx, edx; dwFlags
0x18004d2a1  mov     [rbp+arg_18], ebx
0x18004d2a4  mov     ecx, 10001h; dwMsgEncodingType
0x18004d2a9  mov     [rax], ebx
0x18004d2ab  mov     r14d, ebx
0x18004d2ae  mov     [rbp+pCertContext], rbx
0x18004d2b2  mov     esi, ebx
0x18004d2b4  mov     [r13+0], rbx
0x18004d2b8  movups  [rbp+var_40], xmm0
0x18004d2bc  mov     [rsp+80h+pRecipientInfo], rbx; pRecipientInfo
0x18004d2c1  movups  [rbp+var_30], xmm0
0x18004d2c5  movups  [rbp+var_20], xmm0
0x18004d2c9  call    cs:__imp_CryptMsgOpenToDecode
0x18004d2cf  mov     rdi, rax
0x18004d2d2  test    rax, rax
0x18004d2d5  jnz     short loc_18004D34B
0x18004d2d7  call    cs:__imp_GetLastError
0x18004d2dd  mov     ebx, eax
0x18004d2df  test    eax, eax
0x18004d2e1  jle     short loc_18004D2EC
0x18004d2e3  movzx   ebx, ax
0x18004d2e6  or      ebx, 80070000h
0x18004d2ec  btr     ebx, 1Ch
0x18004d2f0  bts     ebx, 1Eh
0x18004d2f4  mov     r15d, 0C0000428h
0x18004d2fa  mov     rcx, r14; hMem
0x18004d2fd  call    cs:__imp_LocalFree
0x18004d303  lea     rcx, [rbp+var_40]
0x18004d307  call    SIPolicyFreeSIChainInfo
0x18004d30c  test    rsi, rsi
0x18004d30f  jz      short loc_18004D31A
0x18004d311  mov     rcx, rsi; pCertContext
0x18004d314  call    cs:__imp_CertFreeCertificateContext
0x18004d31a  test    rdi, rdi
0x18004d31d  jz      short loc_18004D328
0x18004d31f  mov     rcx, rdi; hCryptMsg
0x18004d322  call    cs:__imp_CryptMsgClose
0x18004d328  test    ebx, ebx
0x18004d32a  cmovs   ebx, r15d
0x18004d32e  mov     eax, ebx
0x18004d330  mov     rbx, [rsp+80h+arg_0]
0x18004d338  add     rsp, 80h
0x18004d33f  pop     r15
0x18004d341  pop     r14
0x18004d343  pop     r13
0x18004d345  pop     r12
0x18004d347  pop     rdi
0x18004d348  pop     rsi
0x18004d349  pop     rbp
0x18004d34a  retn
0x18004d34b  mov     r9d, 1; fFinal
0x18004d351  mov     r8d, r15d; cbData
0x18004d354  mov     rdx, r12; pbData
0x18004d357  mov     rcx, rdi; hCryptMsg
0x18004d35a  call    cs:__imp_CryptMsgUpdate
0x18004d360  test    eax, eax
0x18004d362  jz      loc_18004D2D7
0x18004d368  lea     rax, [rbp+arg_10]
0x18004d36c  mov     edx, 1; dwParamType
0x18004d371  lea     r9, [rbp+var_50]
0x18004d375  mov     [rsp+80h+pRecipientInfo], rax; __int64
0x18004d37a  mov     rcx, rdi; hCryptMsg
0x18004d37d  call    GetCryptMessageParam
0x18004d382  mov     r14, [rbp+var_50]
0x18004d386  mov     ebx, eax
0x18004d388  test    eax, eax
0x18004d38a  js      loc_18004D2F4
0x18004d390  cmp     byte ptr [r14], 2
0x18004d394  jz      short loc_18004D3A4
0x18004d396  mov     r15d, 0C0000428h
0x18004d39c  mov     ebx, r15d
0x18004d39f  jmp     loc_18004D2FA
0x18004d3a4  mov     r8, rdi
0x18004d3a7  call    ValidateOid
0x18004d3ac  mov     ebx, eax
0x18004d3ae  test    eax, eax
0x18004d3b0  js      loc_18004D2F4
0x18004d3b6  lea     rax, [rbp+pCertContext]
0x18004d3ba  mov     edx, r15d; cbSignedBlob
0x18004d3bd  lea     r9, [rbp+arg_18]
0x18004d3c1  mov     [rsp+80h+pRecipientInfo], rax; __int64
0x18004d3c6  lea     r8, [rbp+var_48]
0x18004d3ca  mov     rcx, r12; pbSignedBlob
0x18004d3cd  call    VerifySignatureGetDecodedMessageBlob
0x18004d3d2  mov     rsi, [rbp+pCertContext]
0x18004d3d6  mov     ebx, eax
0x18004d3d8  test    eax, eax
0x18004d3da  js      loc_18004D2F4
0x18004d3e0  lea     r9, [rbp+var_40]
0x18004d3e4  mov     rdx, rsi; pCertContext
0x18004d3e7  mov     rcx, rdi; pvPara
0x18004d3ea  call    ConvertCertCtxToChainInfo
0x18004d3ef  mov     ebx, eax
0x18004d3f1  test    eax, eax
0x18004d3f3  js      loc_18004D2F4
0x18004d3f9  mov     rax, [rbp+var_48]
0x18004d3fd  mov     r15d, 0C0000428h
0x18004d403  mov     rcx, [rbp+arg_30]
0x18004d407  mov     [r13+0], rax
0x18004d40b  mov     eax, [rbp+arg_18]
0x18004d40e  mov     [rcx], eax
0x18004d410  mov     rax, [rbp+arg_38]
0x18004d414  test    rax, rax
0x18004d417  jz      loc_18004D2FA
0x18004d41d  movups  xmm0, [rbp+var_40]
0x18004d421  movups  xmm1, [rbp+var_30]
0x18004d425  movups  xmmword ptr [rax], xmm0
0x18004d428  movups  xmm0, [rbp+var_20]
0x18004d42c  movups  xmmword ptr [rax+10h], xmm1
0x18004d430  movsd   xmm1, [rbp+var_10]
0x18004d435  movups  xmmword ptr [rax+20h], xmm0
0x18004d439  xorps   xmm0, xmm0
0x18004d43c  movsd   qword ptr [rax+30h], xmm1
0x18004d441  xor     eax, eax
0x18004d443  mov     [rbp+var_10], rax
0x18004d447  movups  [rbp+var_40], xmm0
0x18004d44b  movups  [rbp+var_30], xmm0
0x18004d44f  movups  [rbp+var_20], xmm0
0x18004d453  jmp     loc_18004D2FA
```
