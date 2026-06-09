# GetCertContext(SmartHCERTSTORE &,uchar const *,ulong,char const *,int,int,_CERT_CONTEXT const * *,ulong &,unsigned __int64 *,int &,int &)

- ea: `0x180057f40`
- end: `0x18005820a`
- name: `?GetCertContext@@YAJAEAVSmartHCERTSTORE@@PEBEKPEBDHHPEAPEBU_CERT_CONTEXT@@AEAKPEA_KAEAH6@Z`
- size: `714`
- prototype: `int(struct SmartHCERTSTORE *, const unsigned __int8 *, unsigned int, const char *, int, int, const struct _CERT_CONTEXT **, unsigned int *, unsigned __int64 *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002ba10`

## callees

- `0x18000ba8c`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x1800530e4`
- `0x180053890`
- `0x180057110`
- `0x180057f40`
- `0x180058630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005803c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005803c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058186`
- `CRYPT32!CertFindCertificateInStore` at `0x18005802e`
- `CRYPT32!CertFindCertificateInStore` at `0x18005802e`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18005810c`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18005810c`
- `CRYPTSP!CryptSetProvParam` at `0x18005817c`
- `CRYPTSP!CryptSetProvParam` at `0x18005817c`

## string_xrefs

- `0x180057fa8`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x18005805f`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1800580b4`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x18005813c`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1800581dc`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCertContext(
        HCERTSTORE *a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        const BYTE *a4,
        int a5,
        int a6,
        const struct _CERT_CONTEXT **a7,
        unsigned int *pdwKeySpec,
        unsigned __int64 *phCryptProvOrNCryptKey,
        int *pfCallerFreeProvOrNCryptKey,
        int *a11)
{
  int *v14; // rdi
  const char *v15; // rax
  unsigned int v16; // r8d
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  signed int v18; // eax
  int v19; // eax
  DWORD v20; // edx
  signed int v21; // eax
  signed int LastError; // eax
  unsigned int v23; // ebx
  void *pvFindPara; // [rsp+20h] [rbp-61h]
  void *pvFindParaa; // [rsp+20h] [rbp-61h]
  int v27; // [rsp+40h] [rbp-41h] BYREF
  __int128 v28; // [rsp+48h] [rbp-39h] BYREF
  char *v29[13]; // [rsp+58h] [rbp-29h] BYREF

  v27 = 0;
  v28 = 0;
  v14 = a11;
  *a11 = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v29,
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
    0x8Eu,
    (char *)&v27,
    "GetCertContext",
    L"pbThumbprint=0x%p",
    a2);
  if ( !a7 || !phCryptProvOrNCryptKey )
  {
    v15 = "ppCertContext != nullptr && phCryptProv != nullptr";
    v16 = 145;
    goto LABEL_28;
  }
  if ( a5 && !a4 )
  {
    v15 = "!fSetPIN || szPIN != nullptr";
    v16 = 146;
LABEL_28:
    v27 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      "GetCertContext",
      v16,
      -2147024809,
      v15);
    goto LABEL_29;
  }
  *a7 = 0;
  *phCryptProvOrNCryptKey = 0;
  *((_QWORD *)&v28 + 1) = a2;
  LODWORD(v28) = a3;
  CertificateInStore = CertFindCertificateInStore(a1[1], 0x10001u, 0, 0x10000u, &v28, 0);
  *a7 = CertificateInStore;
  if ( CertificateInStore )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
      &a11,
      a2,
      a3);
    v19 = IsSmartCardCert_Helper(*a7, v14);
    v27 = v19;
    if ( v19 < 0 )
    {
      LODWORD(pvFindPara) = v19;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        0xADu,
        L"IsSmartCardCert_Helper failed with hr=0x%x",
        pvFindPara);
      v27 = 0;
    }
    ATL::CStringData::Release((ATL::CStringData *)(a11 - 6));
    if ( a6 || (v20 = 0, *v14) )
      v20 = 66;
    if ( CryptAcquireCertificatePrivateKey(*a7, v20, 0, phCryptProvOrNCryptKey, pdwKeySpec, pfCallerFreeProvOrNCryptKey) )
    {
      if ( a5 && *v14 && !CryptSetProvParam(*phCryptProvOrNCryptKey, 0x20u, a4, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v27 = LastError;
        if ( LastError < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
            "GetCertContext",
            0xCFu,
            LastError,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
      }
    }
    else
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v27 = v21;
      LODWORD(pvFindParaa) = v21;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
        0xBDu,
        L"CryptAcquireCertificatePrivateKey failed with hr=0x%x",
        pvFindParaa);
      if ( v27 == -2146893802 )
        v27 = -2146435028;
    }
  }
  else
  {
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    LODWORD(pvFindPara) = v18;
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      0xA3u,
      L"CertFindCertificateInStore failed with hr=0x%x",
      pvFindPara);
    v27 = -2147467263;
  }
LABEL_29:
  v23 = v27;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v29);
  return v23;
}

```

## disassembly

```asm
0x180057f40  mov     [rsp-8+arg_0], rcx
0x180057f45  push    rbp
0x180057f46  push    rbx
0x180057f47  push    rsi
0x180057f48  push    rdi
0x180057f49  push    r12
0x180057f4b  push    r13
0x180057f4d  push    r14
0x180057f4f  push    r15
0x180057f51  lea     rbp, [rsp-7]
0x180057f56  sub     rsp, 88h
0x180057f5d  mov     r12, r9
0x180057f60  mov     r13d, r8d
0x180057f63  mov     r15, rdx
0x180057f66  mov     [rbp+3Fh+var_80], 0
0x180057f6d  xorps   xmm0, xmm0
0x180057f70  movups  [rbp+3Fh+var_78], xmm0
0x180057f74  mov     rdi, [rbp+3Fh+arg_50]
0x180057f7b  mov     dword ptr [rdi], 0
0x180057f81  mov     [rsp+0C0h+var_90], rdx
0x180057f86  lea     rax, aPbthumbprint0x; "pbThumbprint=0x%p"
0x180057f8d  mov     [rsp+0C0h+pPrevCertContext], rax
0x180057f92  lea     rsi, aGetcertcontext; "GetCertContext"
0x180057f99  mov     [rsp+0C0h+pvFindPara], rsi
0x180057f9e  lea     r9, [rbp+3Fh+var_80]
0x180057fa2  mov     r8d, 8Eh
0x180057fa8  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180057faf  lea     rcx, [rbp+3Fh+var_68]
0x180057fb3  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x180057fb8  nop
0x180057fb9  mov     r14, [rbp+3Fh+arg_30]
0x180057fbd  xor     eax, eax
0x180057fbf  test    r14, r14
0x180057fc2  jz      loc_1800581BD
0x180057fc8  mov     rbx, [rbp+3Fh+phCryptProvOrNCryptKey]
0x180057fcf  test    rbx, rbx
0x180057fd2  jz      loc_1800581BD
0x180057fd8  mov     esi, [rbp+3Fh+arg_20]
0x180057fdb  test    esi, esi
0x180057fdd  jz      short loc_180057FFD
0x180057fdf  test    r12, r12
0x180057fe2  jnz     short loc_180057FFD
0x180057fe4  lea     rax, aFsetpinSzpinNu; "!fSetPIN || szPIN != nullptr"
0x180057feb  mov     r8d, 92h
0x180057ff1  lea     rdx, aGetcertcontext; "GetCertContext"
0x180057ff8  jmp     loc_1800581CD
0x180057ffd  mov     [r14], rax
0x180058000  mov     [rbx], rax
0x180058003  mov     qword ptr [rbp+3Fh+var_78+8], r15
0x180058007  mov     dword ptr [rbp+3Fh+var_78], r13d
0x18005800b  mov     [rsp+0C0h+pPrevCertContext], rax; pPrevCertContext
0x180058010  lea     rax, [rbp+3Fh+var_78]
0x180058014  mov     [rsp+0C0h+pvFindPara], rax; pvFindPara
0x180058019  mov     r9d, 10000h; dwFindType
0x18005801f  xor     r8d, r8d; dwFindFlags
0x180058022  lea     edx, [r9+1]; dwCertEncodingType
0x180058026  mov     rcx, [rbp+3Fh+arg_0]
0x18005802a  mov     rcx, [rcx+8]; hCertStore
0x18005802e  call    cs:__imp_CertFindCertificateInStore
0x180058034  mov     [r14], rax
0x180058037  test    rax, rax
0x18005803a  jnz     short loc_18005807C
0x18005803c  call    cs:__imp_GetLastError
0x180058042  test    eax, eax
0x180058044  jle     short loc_18005804E
0x180058046  movzx   eax, ax
0x180058049  or      eax, 80070000h
0x18005804e  mov     dword ptr [rsp+0C0h+pvFindPara], eax
0x180058052  lea     r9, aCertfindcertif; "CertFindCertificateInStore failed with "...
0x180058059  mov     r8d, 0A3h; unsigned int
0x18005805f  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058066  mov     ecx, 3; unsigned __int8
0x18005806b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180058070  mov     [rbp+3Fh+var_80], 80004001h
0x180058077  jmp     loc_1800581E8
0x18005807c  mov     r8d, r13d
0x18005807f  mov     rdx, r15
0x180058082  lea     rcx, [rbp+3Fh+arg_50]
0x180058089  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBDH@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *,int)
0x18005808e  mov     rdx, rdi; int *
0x180058091  mov     rcx, [r14]; pCert
0x180058094  call    ?IsSmartCardCert_Helper@@YAJPEBU_CERT_CONTEXT@@AEAH@Z; IsSmartCardCert_Helper(_CERT_CONTEXT const *,int &)
0x180058099  mov     [rbp+3Fh+var_80], eax
0x18005809c  xor     r15d, r15d
0x18005809f  test    eax, eax
0x1800580a1  jns     short loc_1800580C8
0x1800580a3  mov     dword ptr [rsp+0C0h+pvFindPara], eax
0x1800580a7  lea     r9, aIssmartcardcer_0; "IsSmartCardCert_Helper failed with hr=0"...
0x1800580ae  mov     r8d, 0ADh; unsigned int
0x1800580b4  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800580bb  lea     ecx, [r15+3]; unsigned __int8
0x1800580bf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800580c4  mov     [rbp+3Fh+var_80], r15d
0x1800580c8  mov     rcx, [rbp+3Fh+arg_50]
0x1800580cf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800580d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800580d8  cmp     [rbp+3Fh+arg_28], r15d
0x1800580dc  jnz     short loc_1800580E6
0x1800580de  cmp     [rdi], r15d
0x1800580e1  mov     edx, r15d
0x1800580e4  jz      short loc_1800580EB
0x1800580e6  mov     edx, 42h ; 'B'; dwFlags
0x1800580eb  mov     rax, [rbp+3Fh+pfCallerFreeProvOrNCryptKey]
0x1800580f2  mov     [rsp+0C0h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x1800580f7  mov     rax, [rbp+3Fh+pdwKeySpec]
0x1800580fe  mov     [rsp+0C0h+pvFindPara], rax; pdwKeySpec
0x180058103  mov     r9, rbx; phCryptProvOrNCryptKey
0x180058106  xor     r8d, r8d; pvParameters
0x180058109  mov     rcx, [r14]; pCert
0x18005810c  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180058112  test    eax, eax
0x180058114  jnz     short loc_180058166
0x180058116  call    cs:__imp_GetLastError
0x18005811c  test    eax, eax
0x18005811e  jle     short loc_180058128
0x180058120  movzx   eax, ax
0x180058123  or      eax, 80070000h
0x180058128  mov     [rbp+3Fh+var_80], eax
0x18005812b  mov     dword ptr [rsp+0C0h+pvFindPara], eax
0x18005812f  lea     r9, aCryptacquirece; "CryptAcquireCertificatePrivateKey faile"...
0x180058136  mov     r8d, 0BDh; unsigned int
0x18005813c  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058143  mov     ecx, 3; unsigned __int8
0x180058148  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005814d  cmp     [rbp+3Fh+var_80], 80090016h
0x180058154  jnz     loc_1800581E8
0x18005815a  mov     [rbp+3Fh+var_80], 8010002Ch
0x180058161  jmp     loc_1800581E8
0x180058166  test    esi, esi
0x180058168  jz      short loc_1800581E8
0x18005816a  cmp     [rdi], r15d
0x18005816d  jz      short loc_1800581E8
0x18005816f  xor     r9d, r9d; dwFlags
0x180058172  mov     r8, r12; pbData
0x180058175  lea     edx, [r9+20h]; dwParam
0x180058179  mov     rcx, [rbx]; hProv
0x18005817c  call    cs:__imp_CryptSetProvParam
0x180058182  test    eax, eax
0x180058184  jnz     short loc_1800581E8
0x180058186  call    cs:__imp_GetLastError
0x18005818c  test    eax, eax
0x18005818e  jle     short loc_180058198
0x180058190  movzx   eax, ax
0x180058193  or      eax, 80070000h
0x180058198  mov     [rbp+3Fh+var_80], eax
0x18005819b  test    eax, eax
0x18005819d  jns     short loc_1800581E8
0x18005819f  lea     rcx, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800581a6  mov     [rsp+0C0h+pvFindPara], rcx
0x1800581ab  mov     r9d, eax
0x1800581ae  mov     r8d, 0CFh
0x1800581b4  lea     rdx, aGetcertcontext; "GetCertContext"
0x1800581bb  jmp     short loc_1800581DC
0x1800581bd  lea     rax, aPpcertcontextN; "ppCertContext != nullptr && phCryptProv"...
0x1800581c4  mov     r8d, 91h; unsigned int
0x1800581ca  mov     rdx, rsi; char *
0x1800581cd  mov     r9d, 80070057h; int
0x1800581d3  mov     [rsp+0C0h+pvFindPara], rax; char *
0x1800581d8  mov     [rbp+3Fh+var_80], r9d
0x1800581dc  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800581e3  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800581e8  mov     ebx, [rbp+3Fh+var_80]
0x1800581eb  lea     rcx, [rbp+3Fh+var_68]
0x1800581ef  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800581f4  mov     eax, ebx
0x1800581f6  add     rsp, 88h
0x1800581fd  pop     r15
0x1800581ff  pop     r14
0x180058201  pop     r13
0x180058203  pop     r12
0x180058205  pop     rdi
0x180058206  pop     rsi
0x180058207  pop     rbx
0x180058208  pop     rbp
0x180058209  retn
```
