# CIDCRLCertObject::AssociateCert(uchar const *,ulong)

- ea: `0x180010c08`
- end: `0x180010d92`
- name: `?AssociateCert@CIDCRLCertObject@@QEAAJPEBEK@Z`
- size: `394`
- prototype: `__int64 __fastcall(CIDCRLCertObject *this, const unsigned __int8 *, DWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010d98`
- `0x180011e50`

## callees

- `0x18000cc9c`
- `0x18000cdd8`
- `0x18000d194`
- `0x18000e870`
- `0x180010c08`
- `0x1800117c0`
- `0x180012c9c`
- `0x1800530e4`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ca0`
- `CRYPT32!CertCreateCertificateContext` at `0x180010c85`
- `CRYPT32!CertCreateCertificateContext` at `0x180010c85`

## string_xrefs

- `0x180010cb5`: `AssociateCert: failed to CertCreateCertificateContext, hr = 0x%x.`

## pseudocode

```c
__int64 __fastcall CIDCRLCertObject::AssociateCert(CIDCRLCertObject *this, const unsigned __int8 *a2, DWORD a3)
{
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  unsigned __int8 v10; // cl
  PCCERT_CONTEXT v11; // rdx
  unsigned int v12; // ebx
  const unsigned __int16 *v14; // [rsp+20h] [rbp-49h]
  __int64 v15; // [rsp+20h] [rbp-49h]
  __int64 v16; // [rsp+30h] [rbp-39h] BYREF
  void **v17; // [rsp+38h] [rbp-31h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-29h]
  _QWORD v19[4]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v20; // [rsp+68h] [rbp-1h]
  const WCHAR *v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+78h] [rbp+Fh]
  __int128 v23; // [rsp+80h] [rbp+17h]
  int v24; // [rsp+90h] [rbp+27h]
  int v25; // [rsp+94h] [rbp+2Bh]
  signed int v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v26 = 0;
  v19[2] = 0;
  v19[0] = "CIDCRLCertObject::AssociateCert";
  v19[3] = 0;
  v19[1] = &v26;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlcert.cpp",
    "CIDCRLCertObject::AssociateCert",
    (const char *)0x2B3,
    0,
    v14);
  v16 = 0;
  pCertContext = 0;
  v17 = &SmartPCCERT_CONTEXT::`vftable';
  CertificateContext = CertCreateCertificateContext(0x10001u, a2, a3);
  SmartPtr<void *>::Attach(&v17, CertificateContext);
  if ( pCertContext )
  {
    v20 = 0;
    v25 = 0;
    v23 = 0;
    if ( (*((_BYTE *)this + 88) & 1) != 0 )
      v20 = *((_QWORD *)this + 12);
    v22 = 1;
    v24 = 1;
    v21 = L"Microsoft Enhanced Cryptographic Provider v1.0";
    LastError = SetPrivateKey(pCertContext);
    v26 = LastError;
    if ( !LastError )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
      v11 = pCertContext;
      pCertContext = 0;
      SmartPtr<void *>::Attach((char *)this + 48, v11);
      goto LABEL_11;
    }
    v8 = L"SetPrivateKey - failed to set private key=  hr:%x";
    v9 = 735;
    v10 = 5;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v26 = LastError;
    v8 = L"AssociateCert: failed to CertCreateCertificateContext, hr = 0x%x.";
    v9 = 709;
    v10 = 2;
  }
  LODWORD(v15) = LastError;
  TracePrintW(v10, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrlcert.cpp", v9, v8, v15);
LABEL_11:
  v12 = v26;
  ATL::CAutoPtr<CIDCRLCertObject>::Free(&v16);
  SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT((SmartPCCERT_CONTEXT *)&v17);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return v12;
}

```

## disassembly

```asm
0x180010c08  push    rbp
0x180010c0a  push    rbx
0x180010c0b  push    rsi
0x180010c0c  push    rdi
0x180010c0d  lea     rbp, [rsp-3Fh]
0x180010c12  sub     rsp, 0A8h
0x180010c19  mov     rdi, rdx
0x180010c1c  mov     [rbp+57h+arg_18], 0
0x180010c23  lea     rdx, aCidcrlcertobje_1; "CIDCRLCertObject::AssociateCert"
0x180010c2a  mov     [rbp+57h+var_68], 0
0x180010c32  mov     ebx, r8d
0x180010c35  mov     [rbp+57h+var_78], rdx
0x180010c39  mov     rsi, rcx
0x180010c3c  mov     [rbp+57h+var_60], 0
0x180010c44  lea     rax, [rbp+57h+arg_18]
0x180010c48  xor     r9d, r9d; unsigned int
0x180010c4b  mov     r8d, 2B3h; char *
0x180010c51  mov     [rbp+57h+var_70], rax
0x180010c55  lea     rcx, aClientcoreDsEx_18; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180010c5c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180010c61  xor     eax, eax
0x180010c63  mov     [rbp+57h+var_90], 0
0x180010c6b  mov     [rbp+57h+pCertContext], rax
0x180010c6f  mov     r8d, ebx; cbCertEncoded
0x180010c72  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x180010c79  mov     rdx, rdi; pbCertEncoded
0x180010c7c  mov     ecx, 10001h; dwCertEncodingType
0x180010c81  mov     [rbp+57h+var_88], rax
0x180010c85  call    cs:__imp_CertCreateCertificateContext
0x180010c8b  mov     rdx, rax
0x180010c8e  lea     rcx, [rbp+57h+var_88]
0x180010c92  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x180010c97  mov     rcx, [rbp+57h+pCertContext]; pCertContext
0x180010c9b  test    rcx, rcx
0x180010c9e  jnz     short loc_180010CDC
0x180010ca0  call    cs:__imp_GetLastError
0x180010ca6  test    eax, eax
0x180010ca8  jle     short loc_180010CB2
0x180010caa  movzx   eax, ax
0x180010cad  or      eax, 80070000h
0x180010cb2  mov     [rbp+57h+arg_18], eax
0x180010cb5  lea     r9, aAssociatecertF_1; "AssociateCert: failed to CertCreateCert"...
0x180010cbc  mov     r8d, 2C5h; unsigned int
0x180010cc2  mov     ecx, 2; unsigned __int8
0x180010cc7  lea     rdx, aClientcoreDsEx_18; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180010cce  mov     [rsp+0C0h+var_A0], eax
0x180010cd2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010cd7  jmp     loc_180010D66
0x180010cdc  mov     edx, 1
0x180010ce1  mov     [rbp+57h+var_58], 0
0x180010ce9  xorps   xmm0, xmm0
0x180010cec  mov     [rbp+57h+var_2C], 0
0x180010cf3  movdqu  [rbp+57h+var_40], xmm0
0x180010cf8  test    [rsi+58h], dl
0x180010cfb  jz      short loc_180010D05
0x180010cfd  mov     rax, [rsi+60h]
0x180010d01  mov     [rbp+57h+var_58], rax
0x180010d05  mov     [rbp+57h+var_48], rdx
0x180010d09  lea     rax, szProvider; "Microsoft Enhanced Cryptographic Provid"...
0x180010d10  mov     [rbp+57h+var_30], edx
0x180010d13  lea     r8, [rbp+57h+var_58]
0x180010d17  mov     rdx, [rsi+28h]
0x180010d1b  mov     [rbp+57h+var_50], rax
0x180010d1f  call    SetPrivateKey
0x180010d24  mov     [rbp+57h+arg_18], eax
0x180010d27  test    eax, eax
0x180010d29  jz      short loc_180010D3F
0x180010d2b  lea     r9, aSetprivatekeyF; "SetPrivateKey - failed to set private k"...
0x180010d32  mov     r8d, 2DFh
0x180010d38  mov     ecx, 5
0x180010d3d  jmp     short loc_180010CC7
0x180010d3f  lea     rbx, [rsi+30h]
0x180010d43  mov     rax, [rbx]
0x180010d46  mov     rcx, rbx
0x180010d49  mov     rax, [rax+8]
0x180010d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d52  mov     rdx, [rbp+57h+pCertContext]
0x180010d56  mov     rcx, rbx
0x180010d59  mov     [rbp+57h+pCertContext], 0
0x180010d61  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x180010d66  mov     ebx, [rbp+57h+arg_18]
0x180010d69  lea     rcx, [rbp+57h+var_90]
0x180010d6d  call    ?Free@?$CAutoPtr@VCIDCRLCertObject@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CIDCRLCertObject>::Free(void)
0x180010d72  lea     rcx, [rbp+57h+var_88]; this
0x180010d76  call    ??1SmartPCCERT_CONTEXT@@UEAA@XZ; SmartPCCERT_CONTEXT::~SmartPCCERT_CONTEXT(void)
0x180010d7b  lea     rcx, [rbp+57h+var_78]
0x180010d7f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180010d84  mov     eax, ebx
0x180010d86  add     rsp, 0A8h
0x180010d8d  pop     rdi
0x180010d8e  pop     rsi
0x180010d8f  pop     rbx
0x180010d90  pop     rbp
0x180010d91  retn
```
