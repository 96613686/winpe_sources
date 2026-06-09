# ClientDeviceIdHelpers::GenerateDeviceTokenHelper(SmartPCCERT_CONTEXT &,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18001ba88`
- end: `0x18001bc29`
- name: `?GenerateDeviceTokenHelper@ClientDeviceIdHelpers@@SAJAEAVSmartPCCERT_CONTEXT@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c0c0`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x18000fa70`
- `0x1800103d0`
- `0x18001ba88`
- `0x1800530e4`
- `0x180053890`
- `0x18005733c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb33`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001bb29`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18001bb29`

## string_xrefs

- `0x18001bbbe`: `<ps:AssertionFormat xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL">DEVICEID</ps:AssertionFormat>`
- `0x18001bad0`: `ClientDeviceIdHelpers::GenerateDeviceTokenHelper`
- `0x18001bbd5`: `hr = BuildCertToken(NULL, k_wstrAssertionFormatDeviceId, wszAudience, cryptProv, pCertContext, dwKeySpec, FALSE, FALSE, wstrToken)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClientDeviceIdHelpers::GenerateDeviceTokenHelper(__int64 a1, __int64 a2, __int64 a3)
{
  signed int LastError; // eax
  int v7; // ebx
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-29h]
  DWORD *pdwKeySpeca; // [rsp+20h] [rbp-29h]
  DWORD v11; // [rsp+50h] [rbp+7h] BYREF
  int v12[2]; // [rsp+58h] [rbp+Fh] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+60h] [rbp+17h] BYREF
  _QWORD v14[5]; // [rsp+68h] [rbp+1Fh] BYREF
  int v15; // [rsp+B0h] [rbp+67h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+C8h] [rbp+7Fh] BYREF

  v15 = 0;
  *(_QWORD *)v12 = 0;
  phCryptProvOrNCryptKey = 0;
  v11 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  v14[0] = "ClientDeviceIdHelpers::GenerateDeviceTokenHelper";
  v14[1] = &v15;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
    "ClientDeviceIdHelpers::GenerateDeviceTokenHelper",
    (const char *)0x2C,
    0,
    (const unsigned __int16 *)pdwKeySpec);
  if ( CryptAcquireCertificatePrivateKey(
         *(PCCERT_CONTEXT *)(a1 + 8),
         0,
         0,
         &phCryptProvOrNCryptKey,
         &v11,
         &pfCallerFreeProvOrNCryptKey) )
  {
    *(_QWORD *)v12 = phCryptProvOrNCryptKey;
    if ( phCryptProvOrNCryptKey && !pfCallerFreeProvOrNCryptKey )
      ATL::CCryptProv::AddRef((ATL::CCryptProv *)v12);
    v7 = BuildCertToken(
           0,
           (__int64)L"<ps:AssertionFormat xmlns:ps=\"http://schemas.microsoft.com/Passport/SoapServices/PPCRL\">DEVICEID</"
                     "ps:AssertionFormat>",
           a2,
           (__int64 *)v12,
           *(PCCERT_CONTEXT *)(a1 + 8),
           v11,
           0,
           0,
           a3);
    v15 = v7;
    if ( v7 < 0 )
    {
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
        "ClientDeviceIdHelpers::GenerateDeviceTokenHelper",
        0x49u,
        v7,
        "hr = BuildCertToken(NULL, k_wstrAssertionFormatDeviceId, wszAudience, cryptProv, pCertContext, dwKeySpec, FALSE,"
        " FALSE, wstrToken)");
      v7 = v15;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = LastError;
    LODWORD(pdwKeySpeca) = LastError;
    TracePrintW(
      3u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\idcrldevicehelpers.cpp",
      0x38u,
      L"CryptAcquireCertificatePrivateKey failed with hr=0x%x",
      pdwKeySpeca);
    v7 = -2147188659;
    v15 = -2147188659;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14);
  ATL::CCryptProv::Release((ATL::CCryptProv *)v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ba88  mov     [rsp-8+arg_8], rbx
0x18001ba8d  mov     [rsp-8+arg_10], rsi
0x18001ba92  push    rbp
0x18001ba93  push    rdi
0x18001ba94  push    r12
0x18001ba96  lea     rbp, [rsp-47h]
0x18001ba9b  sub     rsp, 90h
0x18001baa2  mov     rdi, r8
0x18001baa5  mov     rsi, rdx
0x18001baa8  mov     rbx, rcx
0x18001baab  mov     [rbp+57h+arg_0], 0
0x18001bab2  mov     qword ptr [rbp+57h+var_48], 0
0x18001baba  mov     [rbp+57h+phCryptProvOrNCryptKey], 0
0x18001bac2  mov     [rbp+57h+var_50], 0
0x18001bac9  mov     [rbp+57h+arg_18], 0
0x18001bad0  lea     r12, aClientdeviceid_2; "ClientDeviceIdHelpers::GenerateDeviceTo"...
0x18001bad7  mov     [rbp+57h+var_38], r12
0x18001badb  lea     rax, [rbp+57h+arg_0]
0x18001badf  mov     [rbp+57h+var_30], rax
0x18001bae3  mov     [rbp+57h+var_28], 0
0x18001baeb  mov     [rbp+57h+var_20], 0
0x18001baf3  xor     r9d, r9d; unsigned int
0x18001baf6  lea     r8d, [r9+2Ch]; char *
0x18001bafa  mov     rdx, r12; char *
0x18001bafd  lea     rcx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bb04  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001bb09  nop
0x18001bb0a  lea     rax, [rbp+57h+arg_18]
0x18001bb0e  mov     [rsp+0A0h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x18001bb13  lea     rax, [rbp+57h+var_50]
0x18001bb17  mov     [rsp+0A0h+pdwKeySpec], rax; pdwKeySpec
0x18001bb1c  lea     r9, [rbp+57h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18001bb20  xor     r8d, r8d; pvParameters
0x18001bb23  xor     edx, edx; dwFlags
0x18001bb25  mov     rcx, [rbx+8]; pCert
0x18001bb29  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18001bb2f  test    eax, eax
0x18001bb31  jnz     short loc_18001BB76
0x18001bb33  call    cs:__imp_GetLastError
0x18001bb39  test    eax, eax
0x18001bb3b  jle     short loc_18001BB45
0x18001bb3d  movzx   eax, ax
0x18001bb40  or      eax, 80070000h
0x18001bb45  mov     [rbp+57h+arg_0], eax
0x18001bb48  mov     dword ptr [rsp+0A0h+pdwKeySpec], eax
0x18001bb4c  lea     r9, aCryptacquirece; "CryptAcquireCertificatePrivateKey faile"...
0x18001bb53  mov     r8d, 38h ; '8'; unsigned int
0x18001bb59  lea     rdx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bb60  lea     ecx, [r8-35h]; unsigned __int8
0x18001bb64  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001bb69  mov     ebx, 8004804Dh
0x18001bb6e  mov     [rbp+57h+arg_0], ebx
0x18001bb71  jmp     loc_18001BBFC
0x18001bb76  mov     rax, [rbp+57h+phCryptProvOrNCryptKey]
0x18001bb7a  mov     qword ptr [rbp+57h+var_48], rax
0x18001bb7e  test    rax, rax
0x18001bb81  jz      short loc_18001BB92
0x18001bb83  cmp     [rbp+57h+arg_18], 0
0x18001bb87  jnz     short loc_18001BB92
0x18001bb89  lea     rcx, [rbp+57h+var_48]; this
0x18001bb8d  call    ?AddRef@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::AddRef(void)
0x18001bb92  mov     [rsp+0A0h+var_60], rdi; __int64
0x18001bb97  mov     [rsp+0A0h+var_68], 0; int
0x18001bb9f  mov     [rsp+0A0h+var_70], 0; int
0x18001bba7  mov     eax, [rbp+57h+var_50]
0x18001bbaa  mov     dword ptr [rsp+0A0h+pfCallerFreeProvOrNCryptKey], eax; int
0x18001bbae  mov     rax, [rbx+8]
0x18001bbb2  mov     [rsp+0A0h+pdwKeySpec], rax; pCertContext
0x18001bbb7  lea     r9, [rbp+57h+var_48]; int
0x18001bbbb  mov     r8, rsi; int
0x18001bbbe  lea     rdx, aPsAssertionfor_0; "<ps:AssertionFormat xmlns:ps=\"http://s"...
0x18001bbc5  xor     ecx, ecx; int
0x18001bbc7  call    ?BuildCertToken@@YAJPEBG00AEAVCCryptProv@ATL@@PEBU_CERT_CONTEXT@@KHHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; BuildCertToken(ushort const *,ushort const *,ushort const *,ATL::CCryptProv &,_CERT_CONTEXT const *,ulong,int,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001bbcc  mov     ebx, eax
0x18001bbce  mov     [rbp+57h+arg_0], eax
0x18001bbd1  test    eax, eax
0x18001bbd3  jns     short loc_18001BBFC
0x18001bbd5  lea     rax, aHrBuildcerttok; "hr = BuildCertToken(NULL, k_wstrAsserti"...
0x18001bbdc  mov     [rsp+0A0h+pdwKeySpec], rax; char *
0x18001bbe1  mov     r9d, ebx; int
0x18001bbe4  mov     r8d, 49h ; 'I'; unsigned int
0x18001bbea  mov     rdx, r12; char *
0x18001bbed  lea     rcx, aClientcoreDsEx_9; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18001bbf4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18001bbf9  mov     ebx, [rbp+57h+arg_0]
0x18001bbfc  lea     rcx, [rbp+57h+var_38]
0x18001bc00  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001bc05  nop
0x18001bc06  lea     rcx, [rbp+57h+var_48]; this
0x18001bc0a  call    ?Release@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::Release(void)
0x18001bc0f  mov     eax, ebx
0x18001bc11  lea     r11, [rsp+0A0h+var_10]
0x18001bc19  mov     rbx, [r11+28h]
0x18001bc1d  mov     rsi, [r11+30h]
0x18001bc21  mov     rsp, r11
0x18001bc24  pop     r12
0x18001bc26  pop     rdi
0x18001bc27  pop     rbp
0x18001bc28  retn
```
