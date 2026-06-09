# BFEHandler::IsValidLocalAuthCertificateHash(_CRYPTOAPI_BLOB *)

- ea: `0x18002f51c`
- end: `0x18002f844`
- name: `?IsValidLocalAuthCertificateHash@BFEHandler@@KAHPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *pvFindPara)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036250`
- `0x18003bdb4`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x18002f51c`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f769`
- `CRYPT32!CertOpenStore` at `0x18002f60d`
- `CRYPT32!CertOpenStore` at `0x18002f60d`
- `CRYPT32!CertFindCertificateInStore` at `0x18002f6ba`
- `CRYPT32!CertFindCertificateInStore` at `0x18002f6ba`
- `CRYPT32!CertFreeCertificateContext` at `0x18002f754`
- `CRYPT32!CertFreeCertificateContext` at `0x18002f754`
- `CRYPT32!CertCloseStore` at `0x18002f75f`
- `CRYPT32!CertCloseStore` at `0x18002f75f`

## string_xrefs

- `0x18002f63b`: `Failed to open the certificate store: 0x%x.`

## pseudocode

```c
__int64 __fastcall BFEHandler::IsValidLocalAuthCertificateHash(struct _CRYPTOAPI_BLOB *pvFindPara)
{
  unsigned int v2; // esi
  HCERTSTORE v3; // rax
  void *v4; // r14
  DWORD v5; // edi
  __int64 v6; // r9
  PVOID *v7; // rcx
  __int64 v8; // rdx
  const CERT_CONTEXT *CertificateInStore; // rax
  DWORD LastError; // edi
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+38h] [rbp-C8h]
  __int128 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+64h] [rbp-9Ch]
  int v18; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"BFEHandler::IsValidLocalAuthCertificateHash",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  v2 = 0;
  v3 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, L"MY");
  v4 = v3;
  if ( v3 )
  {
    CertificateInStore = CertFindCertificateInStore(v3, 0x10001u, 0, 0x10000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      v2 = 1;
      CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      LastError = GetLastError();
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"CertFindCertificateInStore Failed: 0x%x.", LastError);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v18);
      }
      if ( LastError
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, LastError);
      }
    }
    if ( CertCloseStore(v4, 0) )
      goto LABEL_36;
    v5 = GetLastError();
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"CertCloseStore failed and returned 0x%x", v5);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v18);
    }
    if ( !v5 )
      goto LABEL_36;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_37;
    v8 = 86;
    goto LABEL_35;
  }
  v5 = GetLastError();
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Failed to open the certificate store: 0x%x.", v5);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v18);
  }
  if ( !v5 )
    goto LABEL_36;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 84;
LABEL_35:
    WPP_SF_d(v7[2], v8, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v5);
LABEL_36:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
  {
    LOBYTE(v6) = v2;
    WPP_SF_c(v7[2], 87, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v6);
  }
LABEL_41:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v2;
}

```

## disassembly

```asm
0x18002f51c  push    rbp
0x18002f51e  push    rbx
0x18002f51f  push    rsi
0x18002f520  push    rdi
0x18002f521  push    r13
0x18002f523  push    r14
0x18002f525  lea     rbp, [rsp-788h]
0x18002f52d  sub     rsp, 888h
0x18002f534  mov     rax, cs:__security_cookie
0x18002f53b  xor     rax, rsp
0x18002f53e  mov     [rbp+7B0h+var_40], rax
0x18002f545  mov     rbx, rcx
0x18002f548  lea     r13, WPP_GLOBAL_Control
0x18002f54f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f556  cmp     rcx, r13
0x18002f559  jz      short loc_18002F57C
0x18002f55b  test    byte ptr [rcx+1Ch], 1
0x18002f55f  jz      short loc_18002F57C
0x18002f561  cmp     byte ptr [rcx+19h], 6
0x18002f565  jb      short loc_18002F57C
0x18002f567  mov     edx, 53h ; 'S'
0x18002f56c  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002f573  mov     rcx, [rcx+10h]
0x18002f577  call    WPP_SF_
0x18002f57c  xor     eax, eax
0x18002f57e  mov     [rsp+8B0h+var_840], eax
0x18002f582  xor     edx, edx; Val
0x18002f584  mov     r8d, 7FCh; Size
0x18002f58a  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18002f58f  call    memset_0
0x18002f594  xorps   xmm0, xmm0
0x18002f597  movdqu  [rsp+8B0h+var_878], xmm0
0x18002f59d  mov     [rsp+8B0h+var_880], 0
0x18002f5a6  xorps   xmm1, xmm1
0x18002f5a9  movdqu  [rsp+8B0h+var_868], xmm1
0x18002f5af  mov     [rsp+8B0h+var_858], 0
0x18002f5b8  mov     [rsp+8B0h+var_850], 0FFFFFFFFh
0x18002f5c0  mov     [rsp+8B0h+var_84C], 0
0x18002f5c8  test    cs:byte_1800AA941, 8
0x18002f5cf  jz      short loc_18002F5EC
0x18002f5d1  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002f5d8  xor     r8d, r8d; unsigned int *
0x18002f5db  lea     rdx, aBfehandlerIsva; "BFEHandler::IsValidLocalAuthCertificate"...
0x18002f5e2  lea     rcx, [rsp+8B0h+var_880]; this
0x18002f5e7  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18002f5ec  xor     esi, esi
0x18002f5ee  lea     rax, aMy; "MY"
0x18002f5f5  mov     [rsp+8B0h+pvPara], rax; pvPara
0x18002f5fa  mov     r9d, 28000h; dwFlags
0x18002f600  xor     r8d, r8d; hCryptProv
0x18002f603  mov     edi, 10001h
0x18002f608  mov     edx, edi; dwEncodingType
0x18002f60a  lea     ecx, [rsi+0Ah]; lpszStoreProvider
0x18002f60d  call    cs:__imp_CertOpenStore
0x18002f613  mov     r14, rax
0x18002f616  test    rax, rax
0x18002f619  jnz     loc_18002F6A2
0x18002f61f  call    cs:__imp_GetLastError
0x18002f625  mov     edi, eax
0x18002f627  mov     bl, 4
0x18002f629  test    cs:byte_1800AA941, bl
0x18002f62f  jz      short loc_18002F66C
0x18002f631  xor     eax, eax
0x18002f633  mov     word ptr [rsp+8B0h+var_840], ax
0x18002f638  mov     r8d, edi
0x18002f63b  lea     rdx, aFailedToOpenTh; "Failed to open the certificate store: 0"...
0x18002f642  lea     rcx, [rsp+8B0h+var_840]
0x18002f647  call    FormatRRASErrorString
0x18002f64c  test    cs:byte_1800AA941, bl
0x18002f652  jz      short loc_18002F66C
0x18002f654  lea     r8, [rsp+8B0h+var_840]
0x18002f659  lea     rdx, RasVpnIkeTraceError
0x18002f660  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f667  call    McTemplateU0z_EventWriteTransfer
0x18002f66c  test    edi, edi
0x18002f66e  jz      loc_18002F7E8
0x18002f674  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f67b  cmp     rcx, r13
0x18002f67e  jz      loc_18002F819
0x18002f684  test    byte ptr [rcx+1Ch], 1
0x18002f688  jz      loc_18002F7EF
0x18002f68e  cmp     byte ptr [rcx+19h], 2
0x18002f692  jb      loc_18002F7EF
0x18002f698  mov     edx, 54h ; 'T'
0x18002f69d  jmp     loc_18002F7D5
0x18002f6a2  mov     [rsp+8B0h+pPrevCertContext], rsi; pPrevCertContext
0x18002f6a7  mov     [rsp+8B0h+pvPara], rbx; pvFindPara
0x18002f6ac  mov     r9d, 10000h; dwFindType
0x18002f6b2  xor     r8d, r8d; dwFindFlags
0x18002f6b5  mov     edx, edi; dwCertEncodingType
0x18002f6b7  mov     rcx, r14; hCertStore
0x18002f6ba  call    cs:__imp_CertFindCertificateInStore
0x18002f6c0  mov     bl, 4
0x18002f6c2  test    rax, rax
0x18002f6c5  jnz     loc_18002F74C
0x18002f6cb  call    cs:__imp_GetLastError
0x18002f6d1  mov     edi, eax
0x18002f6d3  test    cs:byte_1800AA941, bl
0x18002f6d9  jz      short loc_18002F716
0x18002f6db  xor     eax, eax
0x18002f6dd  mov     word ptr [rsp+8B0h+var_840], ax
0x18002f6e2  mov     r8d, edi
0x18002f6e5  lea     rdx, aCertfindcertif_0; "CertFindCertificateInStore Failed: 0x%x"...
0x18002f6ec  lea     rcx, [rsp+8B0h+var_840]
0x18002f6f1  call    FormatRRASErrorString
0x18002f6f6  test    cs:byte_1800AA941, bl
0x18002f6fc  jz      short loc_18002F716
0x18002f6fe  lea     r8, [rsp+8B0h+var_840]
0x18002f703  lea     rdx, RasVpnIkeTraceError
0x18002f70a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f711  call    McTemplateU0z_EventWriteTransfer
0x18002f716  test    edi, edi
0x18002f718  jz      short loc_18002F75A
0x18002f71a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f721  cmp     rcx, r13
0x18002f724  jz      short loc_18002F75A
0x18002f726  test    byte ptr [rcx+1Ch], 1
0x18002f72a  jz      short loc_18002F75A
0x18002f72c  cmp     byte ptr [rcx+19h], 2
0x18002f730  jb      short loc_18002F75A
0x18002f732  mov     edx, 55h ; 'U'
0x18002f737  mov     r9d, edi
0x18002f73a  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002f741  mov     rcx, [rcx+10h]
0x18002f745  call    WPP_SF_d
0x18002f74a  jmp     short loc_18002F75A
0x18002f74c  mov     esi, 1
0x18002f751  mov     rcx, rax; pCertContext
0x18002f754  call    cs:__imp_CertFreeCertificateContext
0x18002f75a  xor     edx, edx; dwFlags
0x18002f75c  mov     rcx, r14; hCertStore
0x18002f75f  call    cs:__imp_CertCloseStore
0x18002f765  test    eax, eax
0x18002f767  jnz     short loc_18002F7E8
0x18002f769  call    cs:__imp_GetLastError
0x18002f76f  mov     edi, eax
0x18002f771  test    cs:byte_1800AA941, bl
0x18002f777  jz      short loc_18002F7B4
0x18002f779  xor     eax, eax
0x18002f77b  mov     word ptr [rsp+8B0h+var_840], ax
0x18002f780  mov     r8d, edi
0x18002f783  lea     rdx, aCertclosestore_0; "CertCloseStore failed and returned 0x%x"
0x18002f78a  lea     rcx, [rsp+8B0h+var_840]
0x18002f78f  call    FormatRRASErrorString
0x18002f794  test    cs:byte_1800AA941, bl
0x18002f79a  jz      short loc_18002F7B4
0x18002f79c  lea     r8, [rsp+8B0h+var_840]
0x18002f7a1  lea     rdx, RasVpnIkeTraceError
0x18002f7a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f7af  call    McTemplateU0z_EventWriteTransfer
0x18002f7b4  test    edi, edi
0x18002f7b6  jz      short loc_18002F7E8
0x18002f7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7bf  cmp     rcx, r13
0x18002f7c2  jz      short loc_18002F819
0x18002f7c4  test    byte ptr [rcx+1Ch], 1
0x18002f7c8  jz      short loc_18002F7EF
0x18002f7ca  cmp     byte ptr [rcx+19h], 2
0x18002f7ce  jb      short loc_18002F7EF
0x18002f7d0  mov     edx, 56h ; 'V'
0x18002f7d5  mov     r9d, edi
0x18002f7d8  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002f7df  mov     rcx, [rcx+10h]
0x18002f7e3  call    WPP_SF_d
0x18002f7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7ef  cmp     rcx, r13
0x18002f7f2  jz      short loc_18002F819
0x18002f7f4  test    byte ptr [rcx+1Ch], 1
0x18002f7f8  jz      short loc_18002F819
0x18002f7fa  cmp     byte ptr [rcx+19h], 6
0x18002f7fe  jb      short loc_18002F819
0x18002f800  mov     r9b, sil
0x18002f803  mov     edx, 57h ; 'W'
0x18002f808  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002f80f  mov     rcx, [rcx+10h]
0x18002f813  call    WPP_SF_c
0x18002f818  nop
0x18002f819  lea     rcx, [rsp+8B0h+var_880]; this
0x18002f81e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18002f823  mov     eax, esi
0x18002f825  mov     rcx, [rbp+7B0h+var_40]
0x18002f82c  xor     rcx, rsp; StackCookie
0x18002f82f  call    __security_check_cookie
0x18002f834  add     rsp, 888h
0x18002f83b  pop     r14
0x18002f83d  pop     r13
0x18002f83f  pop     rdi
0x18002f840  pop     rsi
0x18002f841  pop     rbx
0x18002f842  pop     rbp
0x18002f843  retn
```
