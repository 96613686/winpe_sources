# SchGetTrustedRoots(void * *,void *)

- ea: `0x180071068`
- end: `0x1800714dc`
- name: `?SchGetTrustedRoots@@YAKPEAPEAXPEAX@Z`
- size: `1140`
- prototype: `unsigned int(void **, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180072580`

## callees

- `0x180011054`
- `0x180021da8`
- `0x18003f740`
- `0x180048784`
- `0x1800597b0`
- `0x18005a160`
- `0x180071068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007110d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007110d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800712b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071448`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071497`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071497`
- `CRYPT32!CertOpenStore` at `0x1800710ff`
- `CRYPT32!CertOpenStore` at `0x18007114b`
- `CRYPT32!CertOpenStore` at `0x1800710ff`
- `CRYPT32!CertOpenStore` at `0x18007114b`
- `CRYPT32!CertCloseStore` at `0x18007148a`
- `CRYPT32!CertCloseStore` at `0x1800714ac`
- `CRYPT32!CertCloseStore` at `0x18007148a`
- `CRYPT32!CertCloseStore` at `0x1800714ac`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800711a3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180071473`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800711a3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180071473`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18007142c`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18007142c`
- `CRYPT32!CertGetCertificateChain` at `0x18007126a`
- `CRYPT32!CertGetCertificateChain` at `0x18007126a`
- `CRYPT32!CertFreeCertificateChain` at `0x180071411`
- `CRYPT32!CertFreeCertificateChain` at `0x180071419`
- `CRYPT32!CertFreeCertificateChain` at `0x180071411`
- `CRYPT32!CertFreeCertificateChain` at `0x180071419`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180071376`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180071376`

## pseudocode

```c
__int64 __fastcall SchGetTrustedRoots(void **a1, void *a2)
{
  HCERTSTORE v4; // r15
  DWORD LastError; // ebx
  HCERTSTORE v6; // rax
  void *v7; // r14
  DWORD v8; // eax
  PCCERT_CONTEXT i; // rsi
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  DWORD v15; // eax
  __int64 v16; // rdx
  char v17; // al
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  DWORD v21; // eax
  const CERT_CHAIN_CONTEXT *v22; // rcx
  int v24; // [rsp+40h] [rbp-158h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+48h] [rbp-150h] BYREF
  const char *v26; // [rsp+50h] [rbp-148h] BYREF
  int v27[4]; // [rsp+58h] [rbp-140h] BYREF
  __int64 v28; // [rsp+68h] [rbp-130h]
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+70h] [rbp-128h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+80h] [rbp-118h] BYREF
  struct _CERT_CHAIN_PARA pChainPara; // [rsp+A0h] [rbp-F8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+100h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+110h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+120h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+130h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+140h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+150h] [rbp-48h] BYREF

  v28 = 0;
  *(_OWORD *)v27 = 0;
  pPolicyPara = 0;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  memset_0(&pChainPara, 0, 0x60u);
  pChainContext = 0;
  v26 = 0;
  v24 = 0;
  v4 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  if ( !v4 )
  {
    LastError = GetLastError();
    goto LABEL_42;
  }
  LastError = SslImpersonateClient(a2, &v24);
  if ( !LastError )
  {
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x18001u, L"ROOT");
    v7 = v6;
    if ( !v6 )
    {
      v8 = GetLastError();
      LastError = v8;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v8);
      goto LABEL_40;
    }
    for ( i = CertEnumCertificatesInStore(v6, 0); i; i = CertEnumCertificatesInStore(v7, i) )
    {
      if ( (unsigned int)IsCertSelfSigned(i) )
      {
        v26 = "1.3.6.1.5.5.7.3.2";
        memset_0(&pChainPara, 0, 0x60u);
        pChainPara.cbSize = 96;
        pChainPara.RequestedUsage.dwType = 1;
        pChainPara.RequestedUsage.Usage.cUsageIdentifier = 1;
        pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier = (LPSTR *)&v26;
        if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(1, (int)&ChainBuildStart, v10, v11, &v32);
        if ( !CertGetCertificateChain(0, i, 0, 0, &pChainPara, 0, 0, &pChainContext) )
        {
          if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(v12, (int)&ChainBuildStop, v13, v14, &v33);
          if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            continue;
          }
          v15 = GetLastError();
          v16 = 15;
LABEL_37:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v15);
          continue;
        }
        v17 = Microsoft_Windows_Schannel_EventsEnableBits;
        if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
        {
          McGenEventWrite_EventWriteTransfer(v12, (int)&ChainBuildStop, v13, v14, &v34);
          v17 = Microsoft_Windows_Schannel_EventsEnableBits;
        }
        *(_QWORD *)&v27[2] = 0;
        v27[0] = 24;
        v27[1] = 1;
        pPolicyPara.pvExtraPolicyPara = v27;
        v28 = 0;
        pPolicyPara.cbSize = 16;
        pPolicyPara.dwFlags = 7;
        memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
        pPolicyStatus.cbSize = 24;
        if ( (v17 & 1) != 0 )
          McGenEventWrite_EventWriteTransfer((int)v27, (int)&ChainVerifyStart, v13, v14, &v35);
        if ( CertVerifyCertificateChainPolicy((LPCSTR)4, pChainContext, &pPolicyPara, &pPolicyStatus) )
        {
          if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(v18, (int)&ChainVerifyStop, v19, v20, &v37);
          v22 = pChainContext;
          if ( !pPolicyStatus.dwError )
          {
            CertFreeCertificateChain(pChainContext);
            if ( CertAddCertificateContextToStore(v4, i, 2u, 0)
              || WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              continue;
            }
            v15 = GetLastError();
            v16 = 17;
            goto LABEL_37;
          }
        }
        else
        {
          if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(v18, (int)&ChainVerifyStop, v19, v20, &v36);
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v21 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v21);
          }
          v22 = pChainContext;
        }
        CertFreeCertificateChain(v22);
      }
    }
    CertCloseStore(v7, 0);
  }
LABEL_40:
  if ( v24 )
    RevertToSelf();
LABEL_42:
  if ( LastError )
    CertCloseStore(v4, 0);
  else
    *a1 = v4;
  return LastError;
}

```

## disassembly

```asm
0x180071068  mov     [rsp+arg_10], rbx
0x18007106d  push    rsi
0x18007106e  push    rdi
0x18007106f  push    r12
0x180071071  push    r14
0x180071073  push    r15
0x180071075  sub     rsp, 170h
0x18007107c  mov     rax, cs:__security_cookie
0x180071083  xor     rax, rsp
0x180071086  mov     [rsp+198h+var_38], rax
0x18007108e  xor     eax, eax
0x180071090  xorps   xmm0, xmm0
0x180071093  mov     rbx, rdx
0x180071096  mov     [rsp+198h+var_130], rax
0x18007109b  mov     r12, rcx
0x18007109e  mov     [rsp+198h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800710a6  xorps   xmm1, xmm1
0x1800710a9  lea     rcx, [rsp+198h+pChainPara]; void *
0x1800710b1  lea     r8d, [rax+60h]; Size
0x1800710b5  xor     edx, edx; Val
0x1800710b7  movups  xmmword ptr [rsp+198h+var_140], xmm0
0x1800710bc  movups  xmmword ptr [rsp+198h+pPolicyPara.cbSize], xmm0
0x1800710c1  movups  xmmword ptr [rsp+198h+pPolicyStatus.cbSize], xmm1
0x1800710c9  call    memset_0
0x1800710ce  xor     edx, edx; dwEncodingType
0x1800710d0  mov     [rsp+198h+pChainContext], 0
0x1800710d9  mov     r9d, 4; dwFlags
0x1800710df  mov     [rsp+198h+var_148], 0
0x1800710e8  xor     r8d, r8d; hCryptProv
0x1800710eb  mov     [rsp+198h+var_158], 0
0x1800710f3  mov     [rsp+198h+pvPara], 0; pvPara
0x1800710fc  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800710ff  call    cs:__imp_CertOpenStore
0x180071105  mov     r15, rax
0x180071108  test    rax, rax
0x18007110b  jnz     short loc_18007111A
0x18007110d  call    cs:__imp_GetLastError
0x180071113  mov     ebx, eax
0x180071115  jmp     loc_18007149D
0x18007111a  lea     rdx, [rsp+198h+var_158]; int *
0x18007111f  mov     rcx, rbx; void *
0x180071122  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x180071127  mov     ebx, eax
0x180071129  test    eax, eax
0x18007112b  jnz     loc_180071490
0x180071131  lea     rax, aRoot; "ROOT"
0x180071138  mov     r9d, 18001h; dwFlags
0x18007113e  xor     r8d, r8d; hCryptProv
0x180071141  mov     [rsp+198h+pvPara], rax; pvPara
0x180071146  xor     edx, edx; dwEncodingType
0x180071148  lea     ecx, [rbx+0Ah]; lpszStoreProvider
0x18007114b  call    cs:__imp_CertOpenStore
0x180071151  mov     r14, rax
0x180071154  test    rax, rax
0x180071157  jnz     short loc_18007119E
0x180071159  call    cs:__imp_GetLastError
0x18007115f  mov     ebx, eax
0x180071161  mov     rcx, cs:WPP_GLOBAL_Control
0x180071168  lea     rdi, WPP_GLOBAL_Control
0x18007116f  cmp     rcx, rdi
0x180071172  jz      loc_180071490
0x180071178  test    byte ptr [rcx+1Ch], 2
0x18007117c  jz      loc_180071490
0x180071182  mov     rcx, [rcx+10h]
0x180071186  lea     edx, [r14+0Eh]
0x18007118a  mov     r9d, eax
0x18007118d  lea     r8, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids
0x180071194  call    WPP_SF_d
0x180071199  jmp     loc_180071490
0x18007119e  xor     edx, edx; pPrevCertContext
0x1800711a0  mov     rcx, r14; hCertStore
0x1800711a3  call    cs:__imp_CertEnumCertificatesInStore
0x1800711a9  mov     rsi, rax
0x1800711ac  test    rax, rax
0x1800711af  jz      loc_180071485
0x1800711b5  lea     rdi, WPP_GLOBAL_Control
0x1800711bc  mov     rcx, rsi; struct _CERT_CONTEXT *
0x1800711bf  call    ?IsCertSelfSigned@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertSelfSigned(_CERT_CONTEXT const *)
0x1800711c4  test    eax, eax
0x1800711c6  jz      loc_18007146D
0x1800711cc  xor     edx, edx; Val
0x1800711ce  lea     rax, Str1; "1.3.6.1.5.5.7.3.2"
0x1800711d5  lea     rcx, [rsp+198h+pChainPara]; void *
0x1800711dd  mov     [rsp+198h+var_148], rax
0x1800711e2  lea     r8d, [rdx+60h]; Size
0x1800711e6  call    memset_0
0x1800711eb  mov     ecx, 1; int
0x1800711f0  mov     [rsp+198h+pChainPara.cbSize], 60h ; '`'
0x1800711fb  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, cl
0x180071201  lea     rax, [rsp+198h+var_148]
0x180071206  mov     [rsp+198h+pChainPara.RequestedUsage.dwType], ecx
0x18007120d  mov     [rsp+198h+pChainPara.RequestedUsage.Usage.cUsageIdentifier], ecx
0x180071214  mov     [rsp+198h+pChainPara.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x18007121c  jz      short loc_180071237
0x18007121e  lea     rax, [rsp+198h+var_98]
0x180071226  lea     rdx, ChainBuildStart; int
0x18007122d  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x180071232  call    McGenEventWrite_EventWriteTransfer
0x180071237  lea     rax, [rsp+198h+pChainContext]
0x18007123c  xor     r9d, r9d; hAdditionalStore
0x18007123f  mov     [rsp+198h+ppChainContext], rax; ppChainContext
0x180071244  xor     r8d, r8d; pTime
0x180071247  mov     [rsp+198h+pvReserved], 0; pvReserved
0x180071250  lea     rax, [rsp+198h+pChainPara]
0x180071258  mov     [rsp+198h+dwFlags], 0; dwFlags
0x180071260  mov     rdx, rsi; pCertContext
0x180071263  xor     ecx, ecx; hChainEngine
0x180071265  mov     [rsp+198h+pvPara], rax; pChainPara
0x18007126a  call    cs:__imp_CertGetCertificateChain
0x180071270  test    eax, eax
0x180071272  jnz     short loc_1800712C0
0x180071274  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18007127b  jz      short loc_180071296
0x18007127d  lea     rax, [rsp+198h+var_88]
0x180071285  lea     rdx, ChainBuildStop; int
0x18007128c  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x180071291  call    McGenEventWrite_EventWriteTransfer
0x180071296  mov     rax, cs:WPP_GLOBAL_Control
0x18007129d  cmp     rax, rdi
0x1800712a0  jz      loc_18007146D
0x1800712a6  test    byte ptr [rax+1Ch], 1
0x1800712aa  jz      loc_18007146D
0x1800712b0  call    cs:__imp_GetLastError
0x1800712b6  mov     edx, 0Fh
0x1800712bb  jmp     loc_180071453
0x1800712c0  mov     eax, cs:Microsoft_Windows_Schannel_EventsEnableBits
0x1800712c6  test    al, 1
0x1800712c8  jz      short loc_1800712E9
0x1800712ca  lea     rax, [rsp+198h+var_78]
0x1800712d2  lea     rdx, ChainBuildStop; int
0x1800712d9  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x1800712de  call    McGenEventWrite_EventWriteTransfer
0x1800712e3  mov     eax, cs:Microsoft_Windows_Schannel_EventsEnableBits
0x1800712e9  xor     ecx, ecx
0x1800712eb  mov     qword ptr [rsp+198h+var_140+8], 0
0x1800712f4  mov     [rsp+198h+pPolicyStatus.pvExtraPolicyStatus], rcx
0x1800712fc  mov     edx, 18h
0x180071301  mov     [rsp+198h+var_140], edx
0x180071305  xorps   xmm0, xmm0
0x180071308  mov     [rsp+198h+var_140+4], 1
0x180071310  lea     rcx, [rsp+198h+var_140]; int
0x180071315  mov     [rsp+198h+pPolicyPara.pvExtraPolicyPara], rcx
0x18007131a  mov     [rsp+198h+var_130], 0
0x180071323  mov     [rsp+198h+pPolicyPara.cbSize], 10h
0x18007132b  mov     [rsp+198h+pPolicyPara.dwFlags], 7
0x180071333  movups  xmmword ptr [rsp+198h+pPolicyStatus.cbSize], xmm0
0x18007133b  mov     [rsp+198h+pPolicyStatus.cbSize], edx
0x180071342  test    al, 1
0x180071344  jz      short loc_18007135F
0x180071346  lea     rax, [rsp+198h+var_68]
0x18007134e  lea     rdx, ChainVerifyStart; int
0x180071355  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x18007135a  call    McGenEventWrite_EventWriteTransfer
0x18007135f  mov     rdx, [rsp+198h+pChainContext]; pChainContext
0x180071364  lea     r9, [rsp+198h+pPolicyStatus]; pPolicyStatus
0x18007136c  lea     r8, [rsp+198h+pPolicyPara]; pPolicyPara
0x180071371  mov     ecx, 4; pszPolicyOID
0x180071376  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18007137c  test    eax, eax
0x18007137e  jnz     short loc_1800713E0
0x180071380  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x180071387  jz      short loc_1800713A2
0x180071389  lea     rax, [rsp+198h+var_58]
0x180071391  lea     rdx, ChainVerifyStop; int
0x180071398  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x18007139d  call    McGenEventWrite_EventWriteTransfer
0x1800713a2  mov     rax, cs:WPP_GLOBAL_Control
0x1800713a9  cmp     rax, rdi
0x1800713ac  jz      short loc_1800713D9
0x1800713ae  test    byte ptr [rax+1Ch], 1
0x1800713b2  jz      short loc_1800713D9
0x1800713b4  call    cs:__imp_GetLastError
0x1800713ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713c1  lea     r8, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids
0x1800713c8  mov     edx, 10h
0x1800713cd  mov     r9d, eax
0x1800713d0  mov     rcx, [rcx+10h]
0x1800713d4  call    WPP_SF_d
0x1800713d9  mov     rcx, [rsp+198h+pChainContext]
0x1800713de  jmp     short loc_180071411
0x1800713e0  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x1800713e7  jz      short loc_180071402
0x1800713e9  lea     rax, [rsp+198h+var_48]
0x1800713f1  lea     rdx, ChainVerifyStop; int
0x1800713f8  mov     [rsp+198h+pvPara], rax; PEVENT_DATA_DESCRIPTOR
0x1800713fd  call    McGenEventWrite_EventWriteTransfer
0x180071402  cmp     [rsp+198h+pPolicyStatus.dwError], 0
0x18007140a  mov     rcx, [rsp+198h+pChainContext]; pChainContext
0x18007140f  jz      short loc_180071419
0x180071411  call    cs:__imp_CertFreeCertificateChain
0x180071417  jmp     short loc_18007146D
0x180071419  call    cs:__imp_CertFreeCertificateChain
0x18007141f  xor     r9d, r9d; ppStoreContext
0x180071422  mov     rdx, rsi; pCertContext
0x180071425  mov     rcx, r15; hCertStore
0x180071428  lea     r8d, [r9+2]; dwAddDisposition
0x18007142c  call    cs:__imp_CertAddCertificateContextToStore
0x180071432  test    eax, eax
0x180071434  jnz     short loc_18007146D
0x180071436  mov     rax, cs:WPP_GLOBAL_Control
0x18007143d  cmp     rax, rdi
0x180071440  jz      short loc_18007146D
0x180071442  test    byte ptr [rax+1Ch], 1
0x180071446  jz      short loc_18007146D
0x180071448  call    cs:__imp_GetLastError
0x18007144e  mov     edx, 11h
0x180071453  mov     rcx, cs:WPP_GLOBAL_Control
0x18007145a  lea     r8, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids
0x180071461  mov     r9d, eax
0x180071464  mov     rcx, [rcx+10h]
0x180071468  call    WPP_SF_d
0x18007146d  mov     rdx, rsi; pPrevCertContext
0x180071470  mov     rcx, r14; hCertStore
0x180071473  call    cs:__imp_CertEnumCertificatesInStore
0x180071479  mov     rsi, rax
0x18007147c  test    rax, rax
0x18007147f  jnz     loc_1800711BC
0x180071485  xor     edx, edx; dwFlags
0x180071487  mov     rcx, r14; hCertStore
0x18007148a  call    cs:__imp_CertCloseStore
0x180071490  cmp     [rsp+198h+var_158], 0
0x180071495  jz      short loc_18007149D
0x180071497  call    cs:__imp_RevertToSelf
0x18007149d  test    ebx, ebx
0x18007149f  jnz     short loc_1800714A7
0x1800714a1  mov     [r12], r15
0x1800714a5  jmp     short loc_1800714B2
0x1800714a7  xor     edx, edx; dwFlags
0x1800714a9  mov     rcx, r15; hCertStore
0x1800714ac  call    cs:__imp_CertCloseStore
0x1800714b2  mov     eax, ebx
0x1800714b4  mov     rcx, [rsp+198h+var_38]
0x1800714bc  xor     rcx, rsp; StackCookie
0x1800714bf  call    __security_check_cookie
0x1800714c4  mov     rbx, [rsp+198h+arg_10]
0x1800714cc  add     rsp, 170h
0x1800714d3  pop     r15
0x1800714d5  pop     r14
0x1800714d7  pop     r12
0x1800714d9  pop     rdi
0x1800714da  pop     rsi
0x1800714db  retn
```
