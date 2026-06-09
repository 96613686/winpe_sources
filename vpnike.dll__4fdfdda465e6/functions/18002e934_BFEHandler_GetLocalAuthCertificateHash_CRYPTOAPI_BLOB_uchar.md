# BFEHandler::GetLocalAuthCertificateHash(_CRYPTOAPI_BLOB *,uchar *)

- ea: `0x18002e934`
- end: `0x18002ed58`
- name: `?GetLocalAuthCertificateHash@BFEHandler@@KAKPEAU_CRYPTOAPI_BLOB@@PEAE@Z`
- size: `1060`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *pvFindPara, unsigned __int8 *pvData)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036250`
- `0x18003bdb4`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002e934`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ec6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eccb`
- `CRYPT32!CertOpenStore` at `0x18002ea3c`
- `CRYPT32!CertOpenStore` at `0x18002ea3c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002ebb1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002ebb1`
- `CRYPT32!CertFindCertificateInStore` at `0x18002eaf3`
- `CRYPT32!CertFindCertificateInStore` at `0x18002eaf3`
- `CRYPT32!CertFreeCertificateContext` at `0x18002ec49`
- `CRYPT32!CertFreeCertificateContext` at `0x18002ec49`
- `CRYPT32!CertCloseStore` at `0x18002ec54`
- `CRYPT32!CertCloseStore` at `0x18002ec54`

## string_xrefs

- `0x18002ea6c`: `Failed to open the certificate store: 0x%x.`

## pseudocode

```c
__int64 __fastcall BFEHandler::GetLocalAuthCertificateHash(struct _CRYPTOAPI_BLOB *pvFindPara, unsigned __int8 *pvData)
{
  HCERTSTORE v4; // rax
  void *v5; // r14
  DWORD v6; // eax
  DWORD v7; // eax
  PVOID *v8; // rcx
  __int64 v9; // rdx
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v11; // rdi
  DWORD v12; // eax
  DWORD LastError; // eax
  DWORD v14; // eax
  unsigned int v15; // ebx
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids);
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v17 = 0;
  pcbData = 20;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"BFEHandler::GetLocalAuthCertificateHash",
      &v17,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  v4 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x28000u, L"MY");
  v5 = v4;
  if ( v4 )
  {
    CertificateInStore = CertFindCertificateInStore(v4, 0x10001u, 0, 0x20007u, pvFindPara, 0);
    v11 = CertificateInStore;
    if ( CertificateInStore )
    {
      if ( !CertGetCertificateContextProperty(CertificateInStore, 3u, pvData, &pcbData) )
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"CertGetCertificateContextProperty Failed: 0x%x.", LastError);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
          LastError = v17;
        }
        if ( LastError
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, LastError);
        }
      }
      CertFreeCertificateContext(v11);
    }
    else
    {
      v12 = GetLastError();
      v17 = v12;
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, L"CertFindCertificateInStore Failed: 0x%x.", v12);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
        v12 = v17;
      }
      if ( v12
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v12);
      }
    }
    if ( CertCloseStore(v5, 0) )
      goto LABEL_47;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v25) = 0;
      v14 = GetLastError();
      FormatRRASErrorString(&v25, L"CertCloseStore failed and returned 0x%x", v14);
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
    }
    if ( !GetLastError() )
      goto LABEL_47;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_52;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_48;
    v7 = GetLastError();
    v9 = 92;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v6 = GetLastError();
  v17 = v6;
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"Failed to open the certificate store: 0x%x.", v6);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v25);
  }
  v7 = v17;
  if ( !v17 )
    goto LABEL_47;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_52;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 89;
LABEL_46:
    WPP_SF_d(v8[2], v9, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v7);
LABEL_47:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_48:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 93, &WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids, v17);
LABEL_52:
  v15 = v17;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v15;
}

```

## disassembly

```asm
0x18002e934  mov     [rsp-8+arg_10], rbx
0x18002e939  push    rbp
0x18002e93a  push    rsi
0x18002e93b  push    rdi
0x18002e93c  push    r13
0x18002e93e  push    r14
0x18002e940  lea     rbp, [rsp-780h]
0x18002e948  sub     rsp, 880h
0x18002e94f  mov     rax, cs:__security_cookie
0x18002e956  xor     rax, rsp
0x18002e959  mov     [rbp+7A0h+var_30], rax
0x18002e960  mov     rsi, rdx
0x18002e963  mov     rbx, rcx
0x18002e966  lea     r13, WPP_GLOBAL_Control
0x18002e96d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e974  cmp     rcx, r13
0x18002e977  jz      short loc_18002E99A
0x18002e979  test    byte ptr [rcx+1Ch], 1
0x18002e97d  jz      short loc_18002E99A
0x18002e97f  cmp     byte ptr [rcx+19h], 6
0x18002e983  jb      short loc_18002E99A
0x18002e985  mov     edx, 58h ; 'X'
0x18002e98a  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002e991  mov     rcx, [rcx+10h]
0x18002e995  call    WPP_SF_
0x18002e99a  xor     eax, eax
0x18002e99c  mov     [rsp+8A0h+var_830], eax
0x18002e9a0  xor     edx, edx; Val
0x18002e9a2  mov     r8d, 7FCh; Size
0x18002e9a8  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18002e9ad  call    memset_0
0x18002e9b2  mov     [rsp+8A0h+var_870], 0
0x18002e9ba  mov     [rsp+8A0h+pcbData], 14h
0x18002e9c2  xorps   xmm0, xmm0
0x18002e9c5  movdqu  [rsp+8A0h+var_860], xmm0
0x18002e9cb  mov     [rsp+8A0h+var_868], 0
0x18002e9d4  xorps   xmm1, xmm1
0x18002e9d7  movdqu  [rsp+8A0h+var_850], xmm1
0x18002e9dd  mov     [rsp+8A0h+var_840], 0
0x18002e9e6  mov     [rsp+8A0h+var_838], 0FFFFFFFFh
0x18002e9ee  mov     [rsp+8A0h+var_834], 0
0x18002e9f6  test    cs:byte_1800AA941, 8
0x18002e9fd  jz      short loc_18002EA1C
0x18002e9ff  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18002ea06  lea     r8, [rsp+8A0h+var_870]; unsigned int *
0x18002ea0b  lea     rdx, aBfehandlerGetl; "BFEHandler::GetLocalAuthCertificateHash"
0x18002ea12  lea     rcx, [rsp+8A0h+var_868]; this
0x18002ea17  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18002ea1c  lea     rax, aMy; "MY"
0x18002ea23  mov     [rsp+8A0h+pvPara], rax; pvPara
0x18002ea28  mov     r9d, 28000h; dwFlags
0x18002ea2e  xor     r8d, r8d; hCryptProv
0x18002ea31  mov     edi, 10001h
0x18002ea36  mov     edx, edi; dwEncodingType
0x18002ea38  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x18002ea3c  call    cs:__imp_CertOpenStore
0x18002ea42  mov     r14, rax
0x18002ea45  test    rax, rax
0x18002ea48  jnz     loc_18002EAD7
0x18002ea4e  call    cs:__imp_GetLastError
0x18002ea54  mov     [rsp+8A0h+var_870], eax
0x18002ea58  mov     bl, 4
0x18002ea5a  test    cs:byte_1800AA941, bl
0x18002ea60  jz      short loc_18002EA9D
0x18002ea62  xor     ecx, ecx
0x18002ea64  mov     word ptr [rsp+8A0h+var_830], cx
0x18002ea69  mov     r8d, eax
0x18002ea6c  lea     rdx, aFailedToOpenTh; "Failed to open the certificate store: 0"...
0x18002ea73  lea     rcx, [rsp+8A0h+var_830]
0x18002ea78  call    FormatRRASErrorString
0x18002ea7d  test    cs:byte_1800AA941, bl
0x18002ea83  jz      short loc_18002EA9D
0x18002ea85  lea     r8, [rsp+8A0h+var_830]
0x18002ea8a  lea     rdx, RasVpnIkeTraceError
0x18002ea91  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ea98  call    McTemplateU0z_EventWriteTransfer
0x18002ea9d  mov     eax, [rsp+8A0h+var_870]
0x18002eaa1  test    eax, eax
0x18002eaa3  jz      loc_18002ECF0
0x18002eaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eab0  cmp     rcx, r13
0x18002eab3  jz      loc_18002ED22
0x18002eab9  test    byte ptr [rcx+1Ch], 1
0x18002eabd  jz      loc_18002ECF7
0x18002eac3  cmp     byte ptr [rcx+19h], 2
0x18002eac7  jb      loc_18002ECF7
0x18002eacd  mov     edx, 59h ; 'Y'
0x18002ead2  jmp     loc_18002ECDD
0x18002ead7  mov     [rsp+8A0h+pPrevCertContext], 0; pPrevCertContext
0x18002eae0  mov     [rsp+8A0h+pvPara], rbx; pvFindPara
0x18002eae5  mov     r9d, 20007h; dwFindType
0x18002eaeb  xor     r8d, r8d; dwFindFlags
0x18002eaee  mov     edx, edi; dwCertEncodingType
0x18002eaf0  mov     rcx, r14; hCertStore
0x18002eaf3  call    cs:__imp_CertFindCertificateInStore
0x18002eaf9  mov     rdi, rax
0x18002eafc  test    rax, rax
0x18002eaff  jnz     loc_18002EBA1
0x18002eb05  call    cs:__imp_GetLastError
0x18002eb0b  mov     [rsp+8A0h+var_870], eax
0x18002eb0f  mov     bl, 4
0x18002eb11  test    cs:byte_1800AA941, bl
0x18002eb17  jz      short loc_18002EB58
0x18002eb19  xor     ecx, ecx
0x18002eb1b  mov     word ptr [rsp+8A0h+var_830], cx
0x18002eb20  mov     r8d, eax
0x18002eb23  lea     rdx, aCertfindcertif_0; "CertFindCertificateInStore Failed: 0x%x"...
0x18002eb2a  lea     rcx, [rsp+8A0h+var_830]
0x18002eb2f  call    FormatRRASErrorString
0x18002eb34  test    cs:byte_1800AA941, bl
0x18002eb3a  jz      short loc_18002EB54
0x18002eb3c  lea     r8, [rsp+8A0h+var_830]
0x18002eb41  lea     rdx, RasVpnIkeTraceError
0x18002eb48  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002eb4f  call    McTemplateU0z_EventWriteTransfer
0x18002eb54  mov     eax, [rsp+8A0h+var_870]
0x18002eb58  test    eax, eax
0x18002eb5a  jz      loc_18002EC4F
0x18002eb60  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb67  cmp     rcx, r13
0x18002eb6a  jz      loc_18002EC4F
0x18002eb70  test    byte ptr [rcx+1Ch], 1
0x18002eb74  jz      loc_18002EC4F
0x18002eb7a  cmp     byte ptr [rcx+19h], 2
0x18002eb7e  jb      loc_18002EC4F
0x18002eb84  mov     edx, 5Ah ; 'Z'
0x18002eb89  mov     r9d, eax
0x18002eb8c  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002eb93  mov     rcx, [rcx+10h]
0x18002eb97  call    WPP_SF_d
0x18002eb9c  jmp     loc_18002EC4F
0x18002eba1  lea     r9, [rsp+8A0h+pcbData]; pcbData
0x18002eba6  mov     r8, rsi; pvData
0x18002eba9  mov     edx, 3; dwPropId
0x18002ebae  mov     rcx, rdi; pCertContext
0x18002ebb1  call    cs:__imp_CertGetCertificateContextProperty
0x18002ebb7  mov     bl, 4
0x18002ebb9  test    eax, eax
0x18002ebbb  jnz     loc_18002EC46
0x18002ebc1  call    cs:__imp_GetLastError
0x18002ebc7  mov     [rsp+8A0h+var_870], eax
0x18002ebcb  test    cs:byte_1800AA941, bl
0x18002ebd1  jz      short loc_18002EC12
0x18002ebd3  xor     ecx, ecx
0x18002ebd5  mov     word ptr [rsp+8A0h+var_830], cx
0x18002ebda  mov     r8d, eax
0x18002ebdd  lea     rdx, aCertgetcertifi_0; "CertGetCertificateContextProperty Faile"...
0x18002ebe4  lea     rcx, [rsp+8A0h+var_830]
0x18002ebe9  call    FormatRRASErrorString
0x18002ebee  test    cs:byte_1800AA941, bl
0x18002ebf4  jz      short loc_18002EC0E
0x18002ebf6  lea     r8, [rsp+8A0h+var_830]
0x18002ebfb  lea     rdx, RasVpnIkeTraceError
0x18002ec02  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002ec09  call    McTemplateU0z_EventWriteTransfer
0x18002ec0e  mov     eax, [rsp+8A0h+var_870]
0x18002ec12  test    eax, eax
0x18002ec14  jz      short loc_18002EC46
0x18002ec16  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec1d  cmp     rcx, r13
0x18002ec20  jz      short loc_18002EC46
0x18002ec22  test    byte ptr [rcx+1Ch], 1
0x18002ec26  jz      short loc_18002EC46
0x18002ec28  cmp     byte ptr [rcx+19h], 2
0x18002ec2c  jb      short loc_18002EC46
0x18002ec2e  mov     edx, 5Bh ; '['
0x18002ec33  mov     r9d, eax
0x18002ec36  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002ec3d  mov     rcx, [rcx+10h]
0x18002ec41  call    WPP_SF_d
0x18002ec46  mov     rcx, rdi; pCertContext
0x18002ec49  call    cs:__imp_CertFreeCertificateContext
0x18002ec4f  xor     edx, edx; dwFlags
0x18002ec51  mov     rcx, r14; hCertStore
0x18002ec54  call    cs:__imp_CertCloseStore
0x18002ec5a  test    eax, eax
0x18002ec5c  jnz     loc_18002ECF0
0x18002ec62  test    cs:byte_1800AA941, bl
0x18002ec68  jz      short loc_18002ECA9
0x18002ec6a  mov     word ptr [rsp+8A0h+var_830], ax
0x18002ec6f  call    cs:__imp_GetLastError
0x18002ec75  mov     r8d, eax
0x18002ec78  lea     rdx, aCertclosestore_0; "CertCloseStore failed and returned 0x%x"
0x18002ec7f  lea     rcx, [rsp+8A0h+var_830]
0x18002ec84  call    FormatRRASErrorString
0x18002ec89  test    cs:byte_1800AA941, bl
0x18002ec8f  jz      short loc_18002ECA9
0x18002ec91  lea     r8, [rsp+8A0h+var_830]
0x18002ec96  lea     rdx, RasVpnIkeTraceError
0x18002ec9d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002eca4  call    McTemplateU0z_EventWriteTransfer
0x18002eca9  call    cs:__imp_GetLastError
0x18002ecaf  test    eax, eax
0x18002ecb1  jz      short loc_18002ECF0
0x18002ecb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecba  cmp     rcx, r13
0x18002ecbd  jz      short loc_18002ED22
0x18002ecbf  test    byte ptr [rcx+1Ch], 1
0x18002ecc3  jz      short loc_18002ECF7
0x18002ecc5  cmp     byte ptr [rcx+19h], 2
0x18002ecc9  jb      short loc_18002ECF7
0x18002eccb  call    cs:__imp_GetLastError
0x18002ecd1  mov     edx, 5Ch ; '\'
0x18002ecd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecdd  mov     r9d, eax
0x18002ece0  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002ece7  mov     rcx, [rcx+10h]
0x18002eceb  call    WPP_SF_d
0x18002ecf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecf7  cmp     rcx, r13
0x18002ecfa  jz      short loc_18002ED22
0x18002ecfc  test    byte ptr [rcx+1Ch], 1
0x18002ed00  jz      short loc_18002ED22
0x18002ed02  cmp     byte ptr [rcx+19h], 6
0x18002ed06  jb      short loc_18002ED22
0x18002ed08  mov     edx, 5Dh ; ']'
0x18002ed0d  mov     r9d, [rsp+8A0h+var_870]
0x18002ed12  lea     r8, WPP_f6cfb02c6df931f19b5ad4ca33ae7bb3_Traceguids
0x18002ed19  mov     rcx, [rcx+10h]
0x18002ed1d  call    WPP_SF_d
0x18002ed22  mov     ebx, [rsp+8A0h+var_870]
0x18002ed26  lea     rcx, [rsp+8A0h+var_868]; this
0x18002ed2b  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18002ed30  mov     eax, ebx
0x18002ed32  mov     rcx, [rbp+7A0h+var_30]
0x18002ed39  xor     rcx, rsp; StackCookie
0x18002ed3c  call    __security_check_cookie
0x18002ed41  mov     rbx, [rsp+8A0h+arg_10]
0x18002ed49  add     rsp, 880h
0x18002ed50  pop     r14
0x18002ed52  pop     r13
0x18002ed54  pop     rdi
0x18002ed55  pop     rsi
0x18002ed56  pop     rbp
0x18002ed57  retn
```
