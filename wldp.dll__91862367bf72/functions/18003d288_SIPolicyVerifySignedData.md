# SIPolicyVerifySignedData

- ea: `0x18003d288`
- end: `0x18003d494`
- name: `SIPolicyVerifySignedData`
- size: `524`
- prototype: `__int64 __usercall@<rax>(BYTE *pbSignedBlob@<rcx>, DWORD cbSignedBlob@<edx>, PCCERT_CONTEXT pCertContext, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18003a254`

## callees

- `0x180019050`
- `0x18003cb04`
- `0x18003ce18`
- `0x18003d288`
- `0x18003d49c`
- `0x18003d5c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d339`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d313`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d350`
- `CRYPT32!CertFreeCertificateContext` at `0x18003d350`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18003d305`
- `CRYPT32!CryptMsgOpenToDecode` at `0x18003d305`
- `CRYPT32!CryptMsgUpdate` at `0x18003d396`
- `CRYPT32!CryptMsgUpdate` at `0x18003d396`
- `CRYPT32!CryptMsgClose` at `0x18003d35e`
- `CRYPT32!CryptMsgClose` at `0x18003d35e`

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
0x18003d288  mov     [rsp-38h+arg_0], rbx
0x18003d28d  mov     [rsp-38h+arg_18], r9d
0x18003d292  mov     [rsp-38h+arg_10], r8
0x18003d297  push    rbp
0x18003d298  push    rsi
0x18003d299  push    rdi
0x18003d29a  push    r12
0x18003d29c  push    r13
0x18003d29e  push    r14
0x18003d2a0  push    r15
0x18003d2a2  mov     rbp, rsp
0x18003d2a5  sub     rsp, 80h
0x18003d2ac  mov     r13, [rbp+arg_28]
0x18003d2b0  xor     ebx, ebx
0x18003d2b2  xorps   xmm0, xmm0
0x18003d2b5  mov     [rsp+80h+pStreamInfo], rbx; pStreamInfo
0x18003d2ba  xor     eax, eax
0x18003d2bc  mov     [rbp+var_50], rbx
0x18003d2c0  mov     [rbp+var_10], rax
0x18003d2c4  mov     r15d, edx
0x18003d2c7  mov     rax, [rbp+arg_30]
0x18003d2cb  mov     r12, rcx
0x18003d2ce  xor     r9d, r9d; hCryptProv
0x18003d2d1  mov     [rbp+var_48], rbx
0x18003d2d5  xor     r8d, r8d; dwMsgType
0x18003d2d8  mov     dword ptr [rbp+arg_10], ebx
0x18003d2db  xor     edx, edx; dwFlags
0x18003d2dd  mov     [rbp+arg_18], ebx
0x18003d2e0  mov     ecx, 10001h; dwMsgEncodingType
0x18003d2e5  mov     [rax], ebx
0x18003d2e7  mov     r14d, ebx
0x18003d2ea  mov     [rbp+pCertContext], rbx
0x18003d2ee  mov     esi, ebx
0x18003d2f0  mov     [r13+0], rbx
0x18003d2f4  movups  [rbp+var_40], xmm0
0x18003d2f8  mov     [rsp+80h+pRecipientInfo], rbx; pRecipientInfo
0x18003d2fd  movups  [rbp+var_30], xmm0
0x18003d301  movups  [rbp+var_20], xmm0
0x18003d305  call    cs:__imp_CryptMsgOpenToDecode
0x18003d30b  mov     rdi, rax
0x18003d30e  test    rax, rax
0x18003d311  jnz     short loc_18003D387
0x18003d313  call    cs:__imp_GetLastError
0x18003d319  mov     ebx, eax
0x18003d31b  test    eax, eax
0x18003d31d  jle     short loc_18003D328
0x18003d31f  movzx   ebx, ax
0x18003d322  or      ebx, 80070000h
0x18003d328  btr     ebx, 1Ch
0x18003d32c  bts     ebx, 1Eh
0x18003d330  mov     r15d, 0C0000428h
0x18003d336  mov     rcx, r14; hMem
0x18003d339  call    cs:__imp_LocalFree
0x18003d33f  lea     rcx, [rbp+var_40]
0x18003d343  call    SIPolicyFreeSIChainInfo
0x18003d348  test    rsi, rsi
0x18003d34b  jz      short loc_18003D356
0x18003d34d  mov     rcx, rsi; pCertContext
0x18003d350  call    cs:__imp_CertFreeCertificateContext
0x18003d356  test    rdi, rdi
0x18003d359  jz      short loc_18003D364
0x18003d35b  mov     rcx, rdi; hCryptMsg
0x18003d35e  call    cs:__imp_CryptMsgClose
0x18003d364  test    ebx, ebx
0x18003d366  cmovs   ebx, r15d
0x18003d36a  mov     eax, ebx
0x18003d36c  mov     rbx, [rsp+80h+arg_0]
0x18003d374  add     rsp, 80h
0x18003d37b  pop     r15
0x18003d37d  pop     r14
0x18003d37f  pop     r13
0x18003d381  pop     r12
0x18003d383  pop     rdi
0x18003d384  pop     rsi
0x18003d385  pop     rbp
0x18003d386  retn
0x18003d387  mov     r9d, 1; fFinal
0x18003d38d  mov     r8d, r15d; cbData
0x18003d390  mov     rdx, r12; pbData
0x18003d393  mov     rcx, rdi; hCryptMsg
0x18003d396  call    cs:__imp_CryptMsgUpdate
0x18003d39c  test    eax, eax
0x18003d39e  jz      loc_18003D313
0x18003d3a4  lea     rax, [rbp+arg_10]
0x18003d3a8  mov     edx, 1; dwParamType
0x18003d3ad  lea     r9, [rbp+var_50]
0x18003d3b1  mov     [rsp+80h+pRecipientInfo], rax; __int64
0x18003d3b6  mov     rcx, rdi; hCryptMsg
0x18003d3b9  call    GetCryptMessageParam
0x18003d3be  mov     r14, [rbp+var_50]
0x18003d3c2  mov     ebx, eax
0x18003d3c4  test    eax, eax
0x18003d3c6  js      loc_18003D330
0x18003d3cc  cmp     byte ptr [r14], 2
0x18003d3d0  jz      short loc_18003D3E0
0x18003d3d2  mov     r15d, 0C0000428h
0x18003d3d8  mov     ebx, r15d
0x18003d3db  jmp     loc_18003D336
0x18003d3e0  mov     r8, rdi
0x18003d3e3  call    ValidateOid
0x18003d3e8  mov     ebx, eax
0x18003d3ea  test    eax, eax
0x18003d3ec  js      loc_18003D330
0x18003d3f2  lea     rax, [rbp+pCertContext]
0x18003d3f6  mov     edx, r15d; cbSignedBlob
0x18003d3f9  lea     r9, [rbp+arg_18]
0x18003d3fd  mov     [rsp+80h+pRecipientInfo], rax; __int64
0x18003d402  lea     r8, [rbp+var_48]
0x18003d406  mov     rcx, r12; pbSignedBlob
0x18003d409  call    VerifySignatureGetDecodedMessageBlob
0x18003d40e  mov     rsi, [rbp+pCertContext]
0x18003d412  mov     ebx, eax
0x18003d414  test    eax, eax
0x18003d416  js      loc_18003D330
0x18003d41c  lea     r9, [rbp+var_40]
0x18003d420  mov     rdx, rsi; pCertContext
0x18003d423  mov     rcx, rdi; pvPara
0x18003d426  call    ConvertCertCtxToChainInfo
0x18003d42b  mov     ebx, eax
0x18003d42d  test    eax, eax
0x18003d42f  js      loc_18003D330
0x18003d435  mov     rax, [rbp+var_48]
0x18003d439  mov     r15d, 0C0000428h
0x18003d43f  mov     rcx, [rbp+arg_30]
0x18003d443  mov     [r13+0], rax
0x18003d447  mov     eax, [rbp+arg_18]
0x18003d44a  mov     [rcx], eax
0x18003d44c  mov     rax, [rbp+arg_38]
0x18003d450  test    rax, rax
0x18003d453  jz      loc_18003D336
0x18003d459  movups  xmm0, [rbp+var_40]
0x18003d45d  movups  xmm1, [rbp+var_30]
0x18003d461  movups  xmmword ptr [rax], xmm0
0x18003d464  movups  xmm0, [rbp+var_20]
0x18003d468  movups  xmmword ptr [rax+10h], xmm1
0x18003d46c  movsd   xmm1, [rbp+var_10]
0x18003d471  movups  xmmword ptr [rax+20h], xmm0
0x18003d475  xorps   xmm0, xmm0
0x18003d478  movsd   qword ptr [rax+30h], xmm1
0x18003d47d  xor     eax, eax
0x18003d47f  mov     [rbp+var_10], rax
0x18003d483  movups  [rbp+var_40], xmm0
0x18003d487  movups  [rbp+var_30], xmm0
0x18003d48b  movups  [rbp+var_20], xmm0
0x18003d48f  jmp     loc_18003D336
```
