# CTokenActivation::ThrowCertChooser(int)

- ea: `0x18003a474`
- end: `0x18003a7f1`
- name: `?ThrowCertChooser@CTokenActivation@@IEAAJH@Z`
- size: `893`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003a800`

## callees

- `0x180003520`
- `0x180004288`
- `0x180036fc4`
- `0x180037288`
- `0x1800398b4`
- `0x180039bf8`
- `0x18003a474`
- `0x18003ac1c`
- `0x18003c52a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a4cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a4e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a4e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a705`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5b3`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003a50c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003a50c`
- `CRYPT32!CertFreeCertificateContext` at `0x18003a7b0`
- `CRYPT32!CertFreeCertificateContext` at `0x18003a7b0`
- `CRYPT32!CertCloseStore` at `0x18003a59e`
- `CRYPT32!CertCloseStore` at `0x18003a7c7`
- `CRYPT32!CertCloseStore` at `0x18003a59e`
- `CRYPT32!CertCloseStore` at `0x18003a7c7`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003a60e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003a654`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003a60e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18003a654`
- `CRYPT32!CertOpenStore` at `0x18003a584`
- `CRYPT32!CertOpenStore` at `0x18003a584`
- `CRYPTUI!CryptUIDlgSelectCertificateW` at `0x18003a6e6`
- `CRYPTUI!CryptUIDlgSelectCertificateW` at `0x18003a6e6`

## pseudocode

```c
__int64 __fastcall CTokenActivation::ThrowCertChooser(CTokenActivation *this, int a2)
{
  const CERT_CONTEXT *v4; // rbx
  _QWORD *v5; // rsi
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rax
  ULONG_PTR v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rdi
  char v12; // al
  __int64 v13; // rcx
  int v14; // eax
  HCERTSTORE v15; // r15
  signed int LastError; // eax
  _DWORD *v17; // rcx
  int v18; // r15d
  _DWORD *v19; // rcx
  int v20; // r15d
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v25; // [rsp+30h] [rbp-59h] BYREF
  __int64 v26; // [rsp+38h] [rbp-51h]
  __int64 v27; // [rsp+48h] [rbp-41h]
  int v28; // [rsp+50h] [rbp-39h]
  __int64 v29; // [rsp+58h] [rbp-31h]
  __int64 v30; // [rsp+60h] [rbp-29h]
  __int64 v31; // [rsp+68h] [rbp-21h]
  __int64 v32; // [rsp+70h] [rbp-19h]
  int v33; // [rsp+78h] [rbp-11h]
  HCERTSTORE *p_hCertStore; // [rsp+80h] [rbp-9h]
  int v35; // [rsp+88h] [rbp-1h]
  __int64 v36; // [rsp+90h] [rbp+7h]
  int v37; // [rsp+98h] [rbp+Fh]
  __int128 v38; // [rsp+A0h] [rbp+17h]
  HCERTSTORE hCertStore; // [rsp+F0h] [rbp+67h] BYREF
  _QWORD *v40; // [rsp+100h] [rbp+77h] BYREF

  hCertStore = 0;
  v40 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  memset_0(&v25, 0, 0x80u);
  *((_DWORD *)this + 62) = 0;
  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 0, 0x58u);
    v11 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 0x58u);
      *(_DWORD *)v11 = 1;
      v11[8] = EncodePointer(0);
      v11[9] = 0;
      CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(v11);
      v12 = 0;
    }
    else
    {
      v12 = 1;
      v11 = 0;
    }
    v5 = 0;
    if ( !v12 )
      v5 = v11;
    v40 = v5;
    if ( !v5 )
    {
      v6 = -2147024882;
LABEL_9:
      v13 = v6;
      goto LABEL_48;
    }
    v5[10] = this;
    v14 = CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::BeginInvokeEx((char *)v5, v9, v10);
    v6 = v14;
    if ( v14 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_9;
  }
  v15 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( !v15 )
  {
    hCertStore = 0;
    goto LABEL_17;
  }
  v17 = (_DWORD *)*((_QWORD *)this + 28);
  hCertStore = v15;
  if ( v17 && *v17 )
  {
    v18 = 0;
    while ( CertAddCertificateContextToStore(hCertStore, *(PCCERT_CONTEXT *)&v17[2 * v18 + 2], 3u, 0) )
    {
      v17 = (_DWORD *)*((_QWORD *)this + 28);
      if ( (unsigned int)++v18 >= *v17 )
        goto LABEL_26;
    }
    goto LABEL_17;
  }
LABEL_26:
  v19 = (_DWORD *)*((_QWORD *)this + 27);
  if ( v19 && *v19 )
  {
    v20 = 0;
    while ( CertAddCertificateContextToStore(hCertStore, *(PCCERT_CONTEXT *)&v19[2 * v20 + 2], 3u, 0) )
    {
      v19 = (_DWORD *)*((_QWORD *)this + 27);
      if ( (unsigned int)++v20 >= *v19 )
        goto LABEL_31;
    }
    goto LABEL_17;
  }
LABEL_31:
  v26 = *((_QWORD *)this + 20);
  v27 = *((_QWORD *)this + 32);
  v25 = 128;
  v28 = 20;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 1;
  v35 = 0;
  v29 = *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 272);
  p_hCertStore = &hCertStore;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v4 = (const CERT_CONTEXT *)CryptUIDlgSelectCertificateW(&v25);
  if ( a2 )
  {
    if ( !SetEvent(*(HANDLE *)(*((_QWORD *)this + 19) + 8LL)) )
    {
LABEL_17:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      goto LABEL_9;
    }
    if ( v5[1] )
    {
      v21 = CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(v5);
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = (unsigned int)v21;
LABEL_41:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
        goto LABEL_42;
      }
      if ( *((_DWORD *)v5 + 5) )
      {
LABEL_42:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( (v6 & 0x80000000) != 0 )
          goto LABEL_9;
        goto LABEL_43;
      }
      v6 = -2147023436;
    }
    else
    {
      v6 = -2147418113;
    }
    v22 = v6;
    goto LABEL_41;
  }
LABEL_43:
  if ( *((_DWORD *)this + 62) )
    goto LABEL_49;
  if ( !v4 )
  {
    v6 = -2146434962;
    goto LABEL_9;
  }
  v23 = CTokenActivation::SetSelectedCert(this, v4);
  v6 = v23;
  if ( v23 >= 0 )
    goto LABEL_49;
  v13 = (unsigned int)v23;
LABEL_48:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_49:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>::~SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>(&v40);
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  return v6;
}

```

## disassembly

```asm
0x18003a474  mov     [rsp-8+arg_8], rbx
0x18003a479  push    rbp
0x18003a47a  push    rsi
0x18003a47b  push    rdi
0x18003a47c  push    r12
0x18003a47e  push    r13
0x18003a480  push    r14
0x18003a482  push    r15
0x18003a484  lea     rbp, [rsp-27h]
0x18003a489  sub     rsp, 0B0h
0x18003a490  xor     r13d, r13d
0x18003a493  mov     r12d, edx
0x18003a496  mov     r14, rcx
0x18003a499  mov     [rbp+57h+hCertStore], r13
0x18003a49d  xor     edx, edx; Val
0x18003a49f  mov     [rbp+57h+arg_10], r13
0x18003a4a3  lea     rcx, [rbp+57h+var_B0]; void *
0x18003a4a7  mov     r8d, 80h; Size
0x18003a4ad  mov     ebx, r13d
0x18003a4b0  mov     esi, r13d
0x18003a4b3  mov     edi, r13d
0x18003a4b6  call    memset_0
0x18003a4bb  mov     [r14+0F8h], r13d
0x18003a4c2  test    r12d, r12d
0x18003a4c5  jz      loc_18003A574
0x18003a4cb  call    cs:__imp_GetProcessHeap
0x18003a4d2  nop     dword ptr [rax+rax+00h]
0x18003a4d7  lea     esi, [r13+58h]
0x18003a4db  xor     edx, edx; dwFlags
0x18003a4dd  mov     rcx, rax; hHeap
0x18003a4e0  mov     r8d, esi; dwBytes
0x18003a4e3  call    cs:__imp_HeapAlloc
0x18003a4ea  nop     dword ptr [rax+rax+00h]
0x18003a4ef  mov     rdi, rax
0x18003a4f2  test    rax, rax
0x18003a4f5  jz      short loc_18003A52D
0x18003a4f7  mov     r8d, esi; Size
0x18003a4fa  xor     edx, edx; Val
0x18003a4fc  mov     rcx, rax; void *
0x18003a4ff  call    memset_0
0x18003a504  xor     ecx, ecx; Ptr
0x18003a506  mov     dword ptr [rdi], 1
0x18003a50c  call    cs:__imp_EncodePointer
0x18003a513  nop     dword ptr [rax+rax+00h]
0x18003a518  mov     [rdi+40h], rax
0x18003a51c  mov     rcx, rdi
0x18003a51f  mov     [rdi+48h], r13
0x18003a523  call    ?Reset@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJXZ; CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(void)
0x18003a528  mov     al, r13b
0x18003a52b  jmp     short loc_18003A532
0x18003a52d  mov     al, 1
0x18003a52f  mov     rdi, r13
0x18003a532  test    al, al
0x18003a534  mov     rsi, r13
0x18003a537  cmovz   rsi, rdi
0x18003a53b  mov     [rbp+57h+arg_10], rsi
0x18003a53f  test    rsi, rsi
0x18003a542  jnz     short loc_18003A550
0x18003a544  mov     edi, 8007000Eh
0x18003a549  mov     ecx, edi
0x18003a54b  jmp     loc_18003A793
0x18003a550  mov     rcx, rsi; void *
0x18003a553  mov     [rsi+50h], r14
0x18003a557  call    ?BeginInvokeEx@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@QEAAJP6AJPEAVCSmartCardDetector@CTokenActivation@@@ZPEAV?$CRefCountWrapper@VDH_HANDLE@@@@I@Z; CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::BeginInvokeEx(long (*)(CTokenActivation::CSmartCardDetector *),CRefCountWrapper<DH_HANDLE> *,uint)
0x18003a55c  mov     edi, eax
0x18003a55e  test    eax, eax
0x18003a560  jns     short loc_18003A569
0x18003a562  mov     ecx, eax
0x18003a564  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a569  mov     ecx, edi
0x18003a56b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a570  test    edi, edi
0x18003a572  js      short loc_18003A549
0x18003a574  xor     edx, edx; dwEncodingType
0x18003a576  mov     [rsp+0E0h+pvPara], r13; pvPara
0x18003a57b  xor     r9d, r9d; dwFlags
0x18003a57e  xor     r8d, r8d; hCryptProv
0x18003a581  lea     ecx, [rdx+2]; lpszStoreProvider
0x18003a584  call    cs:__imp_CertOpenStore
0x18003a58b  nop     dword ptr [rax+rax+00h]
0x18003a590  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18003a594  mov     r15, rax
0x18003a597  test    rcx, rcx
0x18003a59a  jz      short loc_18003A5AA
0x18003a59c  xor     edx, edx; dwFlags
0x18003a59e  call    cs:__imp_CertCloseStore
0x18003a5a5  nop     dword ptr [rax+rax+00h]
0x18003a5aa  test    r15, r15
0x18003a5ad  jnz     short loc_18003A5E3
0x18003a5af  mov     [rbp+57h+hCertStore], r13
0x18003a5b3  call    cs:__imp_GetLastError
0x18003a5ba  nop     dword ptr [rax+rax+00h]
0x18003a5bf  mov     edi, eax
0x18003a5c1  test    eax, eax
0x18003a5c3  jnz     short loc_18003A5CF
0x18003a5c5  mov     edi, 80004005h
0x18003a5ca  jmp     loc_18003A549
0x18003a5cf  jle     loc_18003A549
0x18003a5d5  movzx   edi, ax
0x18003a5d8  or      edi, 80070000h
0x18003a5de  jmp     loc_18003A549
0x18003a5e3  mov     rcx, [r14+0E0h]
0x18003a5ea  mov     [rbp+57h+hCertStore], r15
0x18003a5ee  test    rcx, rcx
0x18003a5f1  jz      short loc_18003A62D
0x18003a5f3  cmp     [rcx], r13d
0x18003a5f6  jbe     short loc_18003A62D
0x18003a5f8  mov     r15d, r13d
0x18003a5fb  mov     eax, r15d
0x18003a5fe  xor     r9d, r9d; ppStoreContext
0x18003a601  mov     rdx, [rcx+rax*8+8]; pCertContext
0x18003a606  lea     r8d, [r9+3]; dwAddDisposition
0x18003a60a  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18003a60e  call    cs:__imp_CertAddCertificateContextToStore
0x18003a615  nop     dword ptr [rax+rax+00h]
0x18003a61a  test    eax, eax
0x18003a61c  jz      short loc_18003A5B3
0x18003a61e  mov     rcx, [r14+0E0h]
0x18003a625  inc     r15d
0x18003a628  cmp     r15d, [rcx]
0x18003a62b  jb      short loc_18003A5FB
0x18003a62d  mov     rcx, [r14+0D8h]
0x18003a634  test    rcx, rcx
0x18003a637  jz      short loc_18003A677
0x18003a639  cmp     [rcx], r13d
0x18003a63c  jbe     short loc_18003A677
0x18003a63e  mov     r15d, r13d
0x18003a641  mov     eax, r15d
0x18003a644  xor     r9d, r9d; ppStoreContext
0x18003a647  mov     rdx, [rcx+rax*8+8]; pCertContext
0x18003a64c  lea     r8d, [r9+3]; dwAddDisposition
0x18003a650  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18003a654  call    cs:__imp_CertAddCertificateContextToStore
0x18003a65b  nop     dword ptr [rax+rax+00h]
0x18003a660  test    eax, eax
0x18003a662  jz      loc_18003A5B3
0x18003a668  mov     rcx, [r14+0D8h]
0x18003a66f  inc     r15d
0x18003a672  cmp     r15d, [rcx]
0x18003a675  jb      short loc_18003A641
0x18003a677  mov     rax, [r14+0A0h]
0x18003a67e  lea     rcx, [rbp+57h+var_B0]
0x18003a682  mov     [rbp+57h+var_A8], rax
0x18003a686  xorps   xmm0, xmm0
0x18003a689  mov     rax, [r14+100h]
0x18003a690  mov     [rbp+57h+var_98], rax
0x18003a694  mov     eax, r12d
0x18003a697  neg     eax
0x18003a699  mov     [rbp+57h+var_B0], 80h
0x18003a6a0  mov     [rbp+57h+var_90], 14h
0x18003a6a7  sbb     rax, rax
0x18003a6aa  mov     [rbp+57h+var_80], r13
0x18003a6ae  and     rax, 0FFFFFFFFFFFFFFF8h
0x18003a6b2  mov     [rbp+57h+var_78], r13
0x18003a6b6  mov     [rbp+57h+var_70], r13
0x18003a6ba  mov     [rbp+57h+var_68], 1
0x18003a6c1  mov     [rbp+57h+var_58], r13d
0x18003a6c5  mov     rax, [rax+r14+110h]
0x18003a6cd  mov     [rbp+57h+var_88], rax
0x18003a6d1  lea     rax, [rbp+57h+hCertStore]
0x18003a6d5  mov     [rbp+57h+var_60], rax
0x18003a6d9  mov     [rbp+57h+var_50], r13
0x18003a6dd  mov     [rbp+57h+var_48], r13d
0x18003a6e1  movdqa  [rbp+57h+var_40], xmm0
0x18003a6e6  call    cs:__imp_CryptUIDlgSelectCertificateW
0x18003a6ed  nop     dword ptr [rax+rax+00h]
0x18003a6f2  mov     rbx, rax
0x18003a6f5  test    r12d, r12d
0x18003a6f8  jz      short loc_18003A766
0x18003a6fa  mov     rax, [r14+98h]
0x18003a701  mov     rcx, [rax+8]; hEvent
0x18003a705  call    cs:__imp_SetEvent
0x18003a70c  nop     dword ptr [rax+rax+00h]
0x18003a711  test    eax, eax
0x18003a713  jz      loc_18003A5B3
0x18003a719  cmp     [rsi+8], r13
0x18003a71d  jz      short loc_18003A74B
0x18003a71f  mov     rcx, rsi
0x18003a722  call    ?Wait@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJK@Z; CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(ulong)
0x18003a727  mov     edi, eax
0x18003a729  test    eax, eax
0x18003a72b  jns     short loc_18003A731
0x18003a72d  mov     ecx, eax
0x18003a72f  jmp     short loc_18003A752
0x18003a731  mov     eax, [rsi+14h]
0x18003a734  test    eax, eax
0x18003a736  jnz     short loc_18003A73F
0x18003a738  mov     edi, 800705B4h
0x18003a73d  jmp     short loc_18003A750
0x18003a73f  mov     eax, [rsi+18h]
0x18003a742  test    eax, eax
0x18003a744  jnz     short loc_18003A757
0x18003a746  mov     eax, [rsi+10h]
0x18003a749  jmp     short loc_18003A757
0x18003a74b  mov     edi, 8000FFFFh
0x18003a750  mov     ecx, edi
0x18003a752  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a757  mov     ecx, edi
0x18003a759  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a75e  test    edi, edi
0x18003a760  js      loc_18003A549
0x18003a766  mov     eax, [r14+0F8h]
0x18003a76d  test    eax, eax
0x18003a76f  jnz     short loc_18003A798
0x18003a771  test    rbx, rbx
0x18003a774  jnz     short loc_18003A780
0x18003a776  mov     edi, 8010006Eh
0x18003a77b  jmp     loc_18003A549
0x18003a780  mov     rdx, rbx; struct _CERT_CONTEXT *
0x18003a783  mov     rcx, r14; this
0x18003a786  call    ?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z; CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)
0x18003a78b  mov     edi, eax
0x18003a78d  test    eax, eax
0x18003a78f  jns     short loc_18003A798
0x18003a791  mov     ecx, eax
0x18003a793  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a798  mov     ecx, edi
0x18003a79a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a79f  lea     rcx, [rbp+57h+arg_10]
0x18003a7a3  call    ??1?$SP@VCSmartCardDetector@CTokenActivation@@V?$SP_COM@VCSmartCardDetector@CTokenActivation@@@@@@QEAA@XZ; SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>::~SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>(void)
0x18003a7a8  test    rbx, rbx
0x18003a7ab  jz      short loc_18003A7BC
0x18003a7ad  mov     rcx, rbx; pCertContext
0x18003a7b0  call    cs:__imp_CertFreeCertificateContext
0x18003a7b7  nop     dword ptr [rax+rax+00h]
0x18003a7bc  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18003a7c0  test    rcx, rcx
0x18003a7c3  jz      short loc_18003A7D3
0x18003a7c5  xor     edx, edx; dwFlags
0x18003a7c7  call    cs:__imp_CertCloseStore
0x18003a7ce  nop     dword ptr [rax+rax+00h]
0x18003a7d3  mov     rbx, [rsp+0E0h+arg_8]
0x18003a7db  mov     eax, edi
0x18003a7dd  add     rsp, 0B0h
0x18003a7e4  pop     r15
0x18003a7e6  pop     r14
0x18003a7e8  pop     r13
0x18003a7ea  pop     r12
0x18003a7ec  pop     rdi
0x18003a7ed  pop     rsi
0x18003a7ee  pop     rbp
0x18003a7ef  retn
```
