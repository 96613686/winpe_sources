# Ssl::FindAndLoadCertificate(void *,ulong,void *,_CERT_CONTEXT const * *,int,_SecHandle * *,_SecHandle * *)

- ea: `0x10044cff0`
- end: `0x10044d3d5`
- name: `?FindAndLoadCertificate@Ssl@@CAKPEAXK0PEAPEBU_CERT_CONTEXT@@HPEAPEAU_SecHandle@@2@Z`
- size: `997`
- prototype: `unsigned int __usercall@<eax>(HCERTSTORE hCertStore@<rcx>, DWORD dwFindType@<edx>, void *pvFindPara@<r8>, const struct _CERT_CONTEXT **@<r9>, int, struct _SecHandle **, struct _SecHandle **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x10044ce10`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10044b950`
- `0x10044bbf0`
- `0x10044cff0`
- `0x10044fd00`
- `0x10044fec0`
- `0x100450100`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10044d313`
- `KERNEL32!GetLastError` at `0x10044d313`
- `sqldk!?IsWindowsServer2022OrBeyond@SOS_OS@@SA_NXZ` at `0x10044d23d`
- `sqldk!?IsWindowsServer2022OrBeyond@SOS_OS@@SA_NXZ` at `0x10044d23d`
- `CRYPT32!CertVerifyTimeValidity` at `0x10044d148`
- `CRYPT32!CertVerifyTimeValidity` at `0x10044d148`
- `CRYPT32!CertFindCertificateInStore` at `0x10044d08d`
- `CRYPT32!CertFindCertificateInStore` at `0x10044d2a4`
- `CRYPT32!CertFindCertificateInStore` at `0x10044d08d`
- `CRYPT32!CertFindCertificateInStore` at `0x10044d2a4`

## string_xrefs

- `0x10044d022`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d17b`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d19e`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d1f9`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d21c`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d2b2`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d2f9`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d348`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d383`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044d3a6`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Ssl::FindAndLoadCertificate(
        HCERTSTORE hCertStore,
        DWORD dwFindType,
        void *pvFindPara,
        const struct _CERT_CONTEXT **a4,
        int a5,
        struct _SecHandle **a6,
        struct _SecHandle **a7)
{
  PCCERT_CONTEXT CertificateInStore; // rdi
  const wchar_t *v12; // r9
  const char *v13; // rdx
  const char *v14; // rcx
  unsigned int IsCertKeyUsageExchange; // ebx
  unsigned int v16; // ebx
  unsigned int IsCertGoodKeyPair; // eax
  DWORD LastError; // eax
  void *pvFindParaa; // [rsp+20h] [rbp-98h]
  PCCERT_CONTEXT pPrevCertContext; // [rsp+28h] [rbp-90h]
  __int64 v22; // [rsp+30h] [rbp-88h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::FindAndLoadCertificate",
      1452,
      L"API|SNIhMyCertStore: %p{HCERTSTORE}, dwFindType: %d{DWORD}, pvFindPara: %p, ppCertContext: %p{PCCERT_CONTEXT*}\n",
      hCertStore,
      dwFindType,
      pvFindPara,
      a4,
      -2,
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::FindAndLoadCertificate",
      1452);
  CertificateInStore = CertFindCertificateInStore(hCertStore, 1u, 0, dwFindType, pvFindPara, 0);
  if ( !CertificateInStore )
  {
LABEL_41:
    LastError = GetLastError();
    v16 = LastError;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v22) = LastError;
      LODWORD(pPrevCertContext) = 0;
      LODWORD(pvFindParaa) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::FindAndLoadCertificate",
        1479,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        pvFindParaa,
        pPrevCertContext,
        v22);
    }
    SNISetLastError(6u, v16, 0xC3B4u);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(pvFindParaa) = v16;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::FindAndLoadCertificate",
        1481,
        L"RET|SNI%d{WINERR}\n",
        pvFindParaa);
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    v13 = "Ssl::IsCertTimeValid";
    v14 = "Ssl::IsCertUseable";
    if ( dwFindType != 0x10000 )
    {
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::IsCertUseable",
          3666,
          L"API|SNIpCertContext: %p{PCCERT_CONTEXT}\n",
          CertificateInStore);
      if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
        SNIXE_SNI_ENTER_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::IsCertTimeValid",
          3701,
          L"API|SNIpCertContext: %p{PCCERT_CONTEXT}\n",
          CertificateInStore);
      IsCertKeyUsageExchange = 0;
      if ( CertVerifyTimeValidity(0, CertificateInStore->pCertInfo) )
        IsCertKeyUsageExchange = -2146869243;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(pvFindParaa) = IsCertKeyUsageExchange;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::IsCertTimeValid",
          3710,
          L"RET|SNI%d{WINERR}\n",
          pvFindParaa);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::IsCertTimeValid", 3701, v12);
      if ( !IsCertKeyUsageExchange )
      {
        IsCertKeyUsageExchange = Ssl::IsCertKeyUsageExchange(CertificateInStore);
        if ( !IsCertKeyUsageExchange
          && (!a5 || (IsCertKeyUsageExchange = Ssl::IsCertServerAuth(CertificateInStore)) == 0) )
        {
          IsCertKeyUsageExchange = Ssl::IsCertGoodKeyPair(CertificateInStore);
        }
      }
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(pvFindParaa) = IsCertKeyUsageExchange;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
          "Ssl::IsCertUseable",
          3694,
          L"RET|SNI%d{WINERR}\n",
          pvFindParaa);
      }
      if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
        SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::IsCertUseable", 3666, v12);
      if ( IsCertKeyUsageExchange )
        goto LABEL_33;
    }
    if ( !a5 )
      goto LABEL_38;
    if ( !Ssl::s_fEnableTls13 || !(unsigned __int8)SOS_OS::IsWindowsServer2022OrBeyond(v14, v13) )
      break;
    byte_10052EAEC = 1;
    v16 = Ssl::AcquireCredentialsForServer_v2(CertificateInStore, a7);
    if ( !v16 )
      goto LABEL_31;
LABEL_32:
    if ( dwFindType == 0x10000 )
    {
      IsCertGoodKeyPair = Ssl::IsCertGoodKeyPair(CertificateInStore);
      if ( IsCertGoodKeyPair )
        v16 = IsCertGoodKeyPair;
      goto LABEL_45;
    }
LABEL_33:
    CertificateInStore = CertFindCertificateInStore(hCertStore, 1u, 0, dwFindType, pvFindPara, CertificateInStore);
    if ( !CertificateInStore )
      goto LABEL_41;
  }
  byte_10052EAEC = 0;
  *a7 = 0;
LABEL_31:
  v16 = Ssl::AcquireCredentialsForServer_v1(CertificateInStore, a6);
  if ( v16 )
    goto LABEL_32;
LABEL_38:
  *a4 = CertificateInStore;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(pvFindParaa) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::FindAndLoadCertificate",
      1503,
      L"RET|SNI%d{WINERR}\n",
      pvFindParaa);
  }
  v16 = 0;
LABEL_45:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::FindAndLoadCertificate", 1452, v12);
  return v16;
}

```

## disassembly

```asm
0x10044cff0  mov     rax, rsp
0x10044cff3  push    rdi
0x10044cff4  push    r12
0x10044cff6  push    r13
0x10044cff8  push    r14
0x10044cffa  push    r15
0x10044cffc  sub     rsp, 90h
0x10044d003  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x10044d00b  mov     [rax+8], rbx
0x10044d00f  mov     [rax+10h], rbp
0x10044d013  mov     [rax+18h], rsi
0x10044d017  mov     r13, r9
0x10044d01a  mov     r15, r8
0x10044d01d  mov     esi, edx
0x10044d01f  mov     r12, rcx
0x10044d022  lea     rbx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d029  mov     [rax-70h], rbx
0x10044d02d  lea     rbp, aSslFindandload; "Ssl::FindAndLoadCertificate"
0x10044d034  mov     [rax-68h], rbp
0x10044d038  mov     dword ptr [rax-60h], 5ACh
0x10044d03f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d046  jz      short loc_10044D072
0x10044d048  mov     [rax-80h], r9
0x10044d04c  mov     [rsp+0B8h+var_88], r8
0x10044d051  mov     dword ptr [rsp+0B8h+pPrevCertContext], edx
0x10044d055  mov     [rsp+0B8h+pvFindPara], rcx
0x10044d05a  lea     r9, aApiSnihmycerts; "API|SNIhMyCertStore: %p{HCERTSTORE}, dw"...
0x10044d061  mov     r8d, 5ACh; int
0x10044d067  mov     rdx, rbp; char *
0x10044d06a  mov     rcx, rbx; char *
0x10044d06d  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d072  mov     [rsp+0B8h+pPrevCertContext], 0; pPrevCertContext
0x10044d07b  mov     [rsp+0B8h+pvFindPara], r15; pvFindPara
0x10044d080  mov     r9d, esi; dwFindType
0x10044d083  xor     r8d, r8d; dwFindFlags
0x10044d086  lea     edx, [r8+1]; dwCertEncodingType
0x10044d08a  mov     rcx, r12; hCertStore
0x10044d08d  call    cs:__imp_CertFindCertificateInStore
0x10044d093  mov     rdi, rax
0x10044d096  test    rax, rax
0x10044d099  jz      loc_10044D313
0x10044d09f  mov     r14, [rsp+0B8h+arg_30]
0x10044d0a7  mov     ebp, [rsp+0B8h+arg_20]
0x10044d0ae  lea     rdx, aSslIscerttimev; "Ssl::IsCertTimeValid"
0x10044d0b5  lea     rcx, aSslIscertuseab; "Ssl::IsCertUseable"
0x10044d0bc  cmp     esi, 10000h
0x10044d0c2  jz      loc_10044D22C
0x10044d0c8  mov     [rsp+0B8h+var_58], rbx
0x10044d0cd  mov     [rsp+0B8h+var_50], rcx
0x10044d0d2  mov     [rsp+0B8h+var_48], 0E52h
0x10044d0da  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d0e1  jz      short loc_10044D107
0x10044d0e3  mov     [rsp+0B8h+pvFindPara], rdi
0x10044d0e8  lea     r9, aApiSnipcertcon; "API|SNIpCertContext: %p{PCCERT_CONTEXT}"...
0x10044d0ef  mov     r8d, 0E52h; int
0x10044d0f5  mov     rdx, rcx; char *
0x10044d0f8  mov     rcx, rbx; char *
0x10044d0fb  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d100  lea     rdx, aSslIscerttimev; "Ssl::IsCertTimeValid"
0x10044d107  mov     [rsp+0B8h+var_40], rbx
0x10044d10c  mov     [rsp+0B8h+var_38], rdx
0x10044d114  mov     [rsp+0B8h+var_30], 0E75h
0x10044d11f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d126  jz      short loc_10044D142
0x10044d128  mov     [rsp+0B8h+pvFindPara], rdi
0x10044d12d  lea     r9, aApiSnipcertcon; "API|SNIpCertContext: %p{PCCERT_CONTEXT}"...
0x10044d134  mov     r8d, 0E75h; int
0x10044d13a  mov     rcx, rbx; char *
0x10044d13d  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d142  mov     rdx, [rdi+18h]; pCertInfo
0x10044d146  xor     ecx, ecx; pTimeToVerify
0x10044d148  call    cs:__imp_CertVerifyTimeValidity
0x10044d14e  xor     ebx, ebx
0x10044d150  test    eax, eax
0x10044d152  mov     eax, 80096005h
0x10044d157  cmovnz  ebx, eax
0x10044d15a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d161  jz      short loc_10044D188
0x10044d163  mov     dword ptr [rsp+0B8h+pvFindPara], ebx
0x10044d167  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044d16e  mov     r8d, 0E7Eh; int
0x10044d174  lea     rdx, aSslIscerttimev; "Ssl::IsCertTimeValid"
0x10044d17b  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d182  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d187  nop
0x10044d188  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d18f  jz      short loc_10044D1AA
0x10044d191  mov     r8d, 0E75h; int
0x10044d197  lea     rdx, aSslIscerttimev; "Ssl::IsCertTimeValid"
0x10044d19e  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d1a5  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044d1aa  test    ebx, ebx
0x10044d1ac  jnz     short loc_10044D1D8
0x10044d1ae  mov     rcx, rdi; pCertContext
0x10044d1b1  call    ?IsCertKeyUsageExchange@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z; Ssl::IsCertKeyUsageExchange(_CERT_CONTEXT const *)
0x10044d1b6  mov     ebx, eax
0x10044d1b8  test    eax, eax
0x10044d1ba  jnz     short loc_10044D1D8
0x10044d1bc  test    ebp, ebp
0x10044d1be  jz      short loc_10044D1CE
0x10044d1c0  mov     rcx, rdi; pCertContext
0x10044d1c3  call    ?IsCertServerAuth@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z; Ssl::IsCertServerAuth(_CERT_CONTEXT const *)
0x10044d1c8  mov     ebx, eax
0x10044d1ca  test    eax, eax
0x10044d1cc  jnz     short loc_10044D1D8
0x10044d1ce  mov     rcx, rdi; pCert
0x10044d1d1  call    ?IsCertGoodKeyPair@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z; Ssl::IsCertGoodKeyPair(_CERT_CONTEXT const *)
0x10044d1d6  mov     ebx, eax
0x10044d1d8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d1df  jz      short loc_10044D206
0x10044d1e1  mov     dword ptr [rsp+0B8h+pvFindPara], ebx
0x10044d1e5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044d1ec  mov     r8d, 0E6Eh; int
0x10044d1f2  lea     rdx, aSslIscertuseab; "Ssl::IsCertUseable"
0x10044d1f9  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d200  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d205  nop
0x10044d206  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d20d  jz      short loc_10044D228
0x10044d20f  mov     r8d, 0E52h; int
0x10044d215  lea     rdx, aSslIscertuseab; "Ssl::IsCertUseable"
0x10044d21c  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d223  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044d228  test    ebx, ebx
0x10044d22a  jnz     short loc_10044D28D
0x10044d22c  test    ebp, ebp
0x10044d22e  jz      loc_10044D2D0
0x10044d234  cmp     cs:?s_fEnableTls13@Ssl@@0_NA, 0; bool Ssl::s_fEnableTls13
0x10044d23b  jz      short loc_10044D261
0x10044d23d  call    cs:__imp_?IsWindowsServer2022OrBeyond@SOS_OS@@SA_NXZ; SOS_OS::IsWindowsServer2022OrBeyond(void)
0x10044d243  test    al, al
0x10044d245  jz      short loc_10044D261
0x10044d247  mov     cs:byte_10052EAEC, 1
0x10044d24e  mov     rdx, r14; struct _SecHandle **
0x10044d251  mov     rcx, rdi; struct _CERT_CONTEXT *
0x10044d254  call    ?AcquireCredentialsForServer_v2@Ssl@@SAKPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::AcquireCredentialsForServer_v2(_CERT_CONTEXT const *,_SecHandle * *)
0x10044d259  mov     ebx, eax
0x10044d25b  test    eax, eax
0x10044d25d  jz      short loc_10044D26F
0x10044d25f  jmp     short loc_10044D285
0x10044d261  mov     cs:byte_10052EAEC, 0
0x10044d268  mov     qword ptr [r14], 0
0x10044d26f  mov     rdx, [rsp+0B8h+arg_28]; struct _SecHandle **
0x10044d277  mov     rcx, rdi; struct _CERT_CONTEXT *
0x10044d27a  call    ?AcquireCredentialsForServer_v1@Ssl@@SAKPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z; Ssl::AcquireCredentialsForServer_v1(_CERT_CONTEXT const *,_SecHandle * *)
0x10044d27f  mov     ebx, eax
0x10044d281  test    eax, eax
0x10044d283  jz      short loc_10044D2D0
0x10044d285  cmp     esi, 10000h
0x10044d28b  jz      short loc_10044D2BE
0x10044d28d  mov     [rsp+0B8h+pPrevCertContext], rdi; pPrevCertContext
0x10044d292  mov     [rsp+0B8h+pvFindPara], r15; pvFindPara
0x10044d297  mov     r9d, esi; dwFindType
0x10044d29a  xor     r8d, r8d; dwFindFlags
0x10044d29d  lea     edx, [r8+1]; dwCertEncodingType
0x10044d2a1  mov     rcx, r12; hCertStore
0x10044d2a4  call    cs:__imp_CertFindCertificateInStore
0x10044d2aa  mov     rdi, rax
0x10044d2ad  test    rax, rax
0x10044d2b0  jz      short loc_10044D30C
0x10044d2b2  lea     rbx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d2b9  jmp     loc_10044D0AE
0x10044d2be  mov     rcx, rdi; pCert
0x10044d2c1  call    ?IsCertGoodKeyPair@Ssl@@CAKPEBU_CERT_CONTEXT@@@Z; Ssl::IsCertGoodKeyPair(_CERT_CONTEXT const *)
0x10044d2c6  test    eax, eax
0x10044d2c8  cmovnz  ebx, eax
0x10044d2cb  jmp     loc_10044D390
0x10044d2d0  mov     [r13+0], rdi
0x10044d2d4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d2db  jz      short loc_10044D305
0x10044d2dd  mov     dword ptr [rsp+0B8h+pvFindPara], 0
0x10044d2e5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044d2ec  mov     r8d, 5DFh; int
0x10044d2f2  lea     rdx, aSslFindandload; "Ssl::FindAndLoadCertificate"
0x10044d2f9  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d300  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d305  xor     ebx, ebx
0x10044d307  jmp     loc_10044D390
0x10044d30c  lea     rbp, aSslFindandload; "Ssl::FindAndLoadCertificate"
0x10044d313  call    cs:__imp_GetLastError
0x10044d319  mov     ebx, eax
0x10044d31b  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d322  jz      short loc_10044D354
0x10044d324  mov     dword ptr [rsp+0B8h+var_88], eax
0x10044d328  mov     dword ptr [rsp+0B8h+pPrevCertContext], 0
0x10044d330  mov     dword ptr [rsp+0B8h+pvFindPara], 6
0x10044d338  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044d33f  mov     r8d, 5C7h; int
0x10044d345  mov     rdx, rbp; char *
0x10044d348  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d34f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d354  mov     r8d, 0C3B4h
0x10044d35a  mov     edx, ebx
0x10044d35c  mov     ecx, 6
0x10044d361  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044d366  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d36d  jz      short loc_10044D390
0x10044d36f  mov     dword ptr [rsp+0B8h+pvFindPara], ebx
0x10044d373  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044d37a  mov     r8d, 5C9h; int
0x10044d380  mov     rdx, rbp; char *
0x10044d383  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d38a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044d38f  nop
0x10044d390  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044d397  jz      short loc_10044D3B2
0x10044d399  mov     r8d, 5ACh; int
0x10044d39f  lea     rdx, aSslFindandload; "Ssl::FindAndLoadCertificate"
0x10044d3a6  lea     rcx, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044d3ad  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044d3b2  mov     eax, ebx
0x10044d3b4  lea     r11, [rsp+0B8h+var_28]
0x10044d3bc  mov     rbx, [r11+30h]
0x10044d3c0  mov     rbp, [r11+38h]
0x10044d3c4  mov     rsi, [r11+40h]
0x10044d3c8  mov     rsp, r11
0x10044d3cb  pop     r15
0x10044d3cd  pop     r14
0x10044d3cf  pop     r13
0x10044d3d1  pop     r12
0x10044d3d3  pop     rdi
0x10044d3d4  retn
```
