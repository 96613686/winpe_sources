# IsSmartCardCert_Helper(_CERT_CONTEXT const *,int &)

- ea: `0x180058630`
- end: `0x180058818`
- name: `?IsSmartCardCert_Helper@@YAJPEBU_CERT_CONTEXT@@AEAH@Z`
- size: `488`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180057f40`
- `0x180058428`

## callees

- `0x180005aa8`
- `0x18000a914`
- `0x18000ba8c`
- `0x18000cc9c`
- `0x18000e870`
- `0x18000fa70`
- `0x1800103d0`
- `0x1800530e4`
- `0x180058630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800586c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800587b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800586c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800587b1`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800586ba`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800586ba`
- `CRYPTSP!CryptGetUserKey` at `0x180058741`
- `CRYPTSP!CryptGetUserKey` at `0x180058741`
- `CRYPTSP!CryptGetKeyParam` at `0x1800587a7`
- `CRYPTSP!CryptGetKeyParam` at `0x1800587a7`

## string_xrefs

- `0x18005867e`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x1800586ea`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`
- `0x180058772`: `onecoreuap\ds\ext\live\identity\lib\utilities\certtoken.cpp`

## pseudocode

```c
__int64 __fastcall IsSmartCardCert_Helper(PCCERT_CONTEXT pCert, int *a2)
{
  signed int v4; // eax
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE v5; // rcx
  BOOL UserKey; // eax
  signed int LastError; // eax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  DWORD *pdwKeySpec; // [rsp+20h] [rbp-60h]
  DWORD *pdwKeySpeca; // [rsp+20h] [rbp-60h]
  DWORD pdwDataLen; // [rsp+30h] [rbp-50h] BYREF
  HCRYPTKEY v15; // [rsp+38h] [rbp-48h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE v17; // [rsp+48h] [rbp-38h] BYREF
  HCRYPTKEY phUserKey; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v20[4]; // [rsp+60h] [rbp-20h] BYREF
  signed int v21; // [rsp+A8h] [rbp+28h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+B0h] [rbp+30h] BYREF
  DWORD dwKeySpec; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  dwKeySpec = 0;
  pdwDataLen = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v19);
  phCryptProvOrNCryptKey = 0;
  v20[0] = "IsSmartCardCert_Helper";
  v20[1] = &v21;
  phUserKey = 0;
  v17 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  v20[2] = 0;
  v20[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
    "IsSmartCardCert_Helper",
    (const char *)0x3D,
    0,
    (const unsigned __int16 *)pdwKeySpec);
  *a2 = 0;
  if ( CryptAcquireCertificatePrivateKey(
         pCert,
         0x40u,
         0,
         &phCryptProvOrNCryptKey,
         &dwKeySpec,
         &pfCallerFreeProvOrNCryptKey) )
  {
    v5 = phCryptProvOrNCryptKey;
    v17 = phCryptProvOrNCryptKey;
    if ( phCryptProvOrNCryptKey && !pfCallerFreeProvOrNCryptKey )
    {
      ATL::CCryptProv::AddRef((ATL::CCryptProv *)&v17);
      v5 = phCryptProvOrNCryptKey;
    }
    UserKey = CryptGetUserKey(v5, dwKeySpec, &phUserKey);
    v15 = phUserKey;
    if ( UserKey )
    {
      if ( CryptGetKeyParam(phUserKey, 0x1Au, 0, &pdwDataLen, 0) )
      {
        ATL::CCryptKey::Destroy((ATL::CCryptKey *)&v15);
        *a2 = 1;
        goto LABEL_20;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = L"CryptGetKeyParam failed with hr=0x%x";
      v9 = 100;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = L"CryptGetUserKey failed with hr=0x%x";
      v9 = 92;
    }
    LODWORD(pdwKeySpeca) = LastError;
    v21 = LastError;
    TracePrintW(3u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp", v9, v8, pdwKeySpeca);
    v21 = 0;
    ATL::CCryptKey::Destroy((ATL::CCryptKey *)&v15);
  }
  else
  {
    v4 = GetLastError();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v21 = v4;
    LODWORD(pdwKeySpeca) = v4;
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilities\\certtoken.cpp",
      0x49u,
      L"CryptAcquireCertificatePrivateKey failed with hr=0x%x",
      pdwKeySpeca);
    if ( (v21 & 0x1FFF0000) == 0x100000 )
      *a2 = 1;
    v21 = 0;
  }
LABEL_20:
  v10 = v21;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v20);
  ATL::CCryptProv::Release((ATL::CCryptProv *)&v17);
  ATL::CStringData::Release((ATL::CStringData *)(v19 - 24));
  return v10;
}

```

## disassembly

```asm
0x180058630  mov     [rsp-18h+arg_0], rbx
0x180058635  push    rbp
0x180058636  push    rsi
0x180058637  push    rdi
0x180058638  mov     rbp, rsp
0x18005863b  sub     rsp, 80h
0x180058642  xor     esi, esi
0x180058644  mov     rbx, rcx
0x180058647  lea     rcx, [rbp+var_28]
0x18005864b  mov     [rbp+arg_8], esi
0x18005864e  mov     [rbp+dwKeySpec], esi
0x180058651  mov     rdi, rdx
0x180058654  mov     [rbp+pdwDataLen], esi
0x180058657  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005865c  lea     rdx, aIssmartcardcer; "IsSmartCardCert_Helper"
0x180058663  mov     [rbp+phCryptProvOrNCryptKey], rsi
0x180058667  lea     rax, [rbp+arg_8]
0x18005866b  mov     [rbp+var_20], rdx
0x18005866f  xor     r9d, r9d; unsigned int
0x180058672  mov     [rbp+var_18], rax
0x180058676  lea     r8d, [rsi+3Dh]; char *
0x18005867a  mov     [rbp+phUserKey], rsi
0x18005867e  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058685  mov     [rbp+var_38], rsi
0x180058689  mov     [rbp+arg_10], esi
0x18005868c  mov     [rbp+var_10], rsi
0x180058690  mov     [rbp+var_8], rsi
0x180058694  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180058699  lea     rax, [rbp+arg_10]
0x18005869d  mov     [rdi], esi
0x18005869f  mov     [rsp+80h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x1800586a4  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800586a8  lea     rax, [rbp+dwKeySpec]
0x1800586ac  xor     r8d, r8d; pvParameters
0x1800586af  lea     edx, [rsi+40h]; dwFlags
0x1800586b2  mov     [rsp+80h+pdwKeySpec], rax; pdwKeySpec
0x1800586b7  mov     rcx, rbx; pCert
0x1800586ba  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800586c0  test    eax, eax
0x1800586c2  jnz     short loc_180058717
0x1800586c4  call    cs:__imp_GetLastError
0x1800586ca  test    eax, eax
0x1800586cc  jle     short loc_1800586D6
0x1800586ce  movzx   eax, ax
0x1800586d1  or      eax, 80070000h
0x1800586d6  mov     r8d, 49h ; 'I'; unsigned int
0x1800586dc  mov     [rbp+arg_8], eax
0x1800586df  lea     r9, aCryptacquirece; "CryptAcquireCertificatePrivateKey faile"...
0x1800586e6  mov     dword ptr [rsp+80h+pdwKeySpec], eax
0x1800586ea  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800586f1  lea     ecx, [r8-46h]; unsigned __int8
0x1800586f5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800586fa  mov     eax, [rbp+arg_8]
0x1800586fd  and     eax, 1FFF0000h
0x180058702  cmp     eax, 100000h
0x180058707  jnz     short loc_18005870F
0x180058709  mov     dword ptr [rdi], 1
0x18005870f  mov     [rbp+arg_8], esi
0x180058712  jmp     loc_1800587E1
0x180058717  mov     rcx, [rbp+phCryptProvOrNCryptKey]
0x18005871b  mov     [rbp+var_38], rcx
0x18005871f  test    rcx, rcx
0x180058722  jz      short loc_180058736
0x180058724  cmp     [rbp+arg_10], esi
0x180058727  jnz     short loc_180058736
0x180058729  lea     rcx, [rbp+var_38]; this
0x18005872d  call    ?AddRef@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::AddRef(void)
0x180058732  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x180058736  mov     edx, [rbp+dwKeySpec]; dwKeySpec
0x180058739  lea     r8, [rbp+phUserKey]; phUserKey
0x18005873d  mov     [rbp+var_48], rsi
0x180058741  call    cs:__imp_CryptGetUserKey
0x180058747  mov     rcx, [rbp+phUserKey]; hKey
0x18005874b  mov     [rbp+var_48], rcx
0x18005874f  test    eax, eax
0x180058751  jnz     short loc_180058798
0x180058753  call    cs:__imp_GetLastError
0x180058759  test    eax, eax
0x18005875b  jle     short loc_180058765
0x18005875d  movzx   eax, ax
0x180058760  or      eax, 80070000h
0x180058765  lea     r9, aCryptgetuserke; "CryptGetUserKey failed with hr=0x%x"
0x18005876c  mov     r8d, 5Ch ; '\'; unsigned int
0x180058772  lea     rdx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180058779  mov     dword ptr [rsp+80h+pdwKeySpec], eax
0x18005877d  mov     ecx, 3; unsigned __int8
0x180058782  mov     [rbp+arg_8], eax
0x180058785  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005878a  lea     rcx, [rbp+var_48]; this
0x18005878e  mov     [rbp+arg_8], esi
0x180058791  call    ?Destroy@CCryptKey@ATL@@QEAAXXZ; ATL::CCryptKey::Destroy(void)
0x180058796  jmp     short loc_1800587E1
0x180058798  xor     r8d, r8d; pbData
0x18005879b  mov     dword ptr [rsp+80h+pdwKeySpec], esi; dwFlags
0x18005879f  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1800587a3  lea     edx, [r8+1Ah]; dwParam
0x1800587a7  call    cs:__imp_CryptGetKeyParam
0x1800587ad  test    eax, eax
0x1800587af  jnz     short loc_1800587D2
0x1800587b1  call    cs:__imp_GetLastError
0x1800587b7  test    eax, eax
0x1800587b9  jle     short loc_1800587C3
0x1800587bb  movzx   eax, ax
0x1800587be  or      eax, 80070000h
0x1800587c3  lea     r9, aCryptgetkeypar; "CryptGetKeyParam failed with hr=0x%x"
0x1800587ca  mov     r8d, 64h ; 'd'
0x1800587d0  jmp     short loc_180058772
0x1800587d2  lea     rcx, [rbp+var_48]; this
0x1800587d6  call    ?Destroy@CCryptKey@ATL@@QEAAXXZ; ATL::CCryptKey::Destroy(void)
0x1800587db  mov     dword ptr [rdi], 1
0x1800587e1  mov     ebx, [rbp+arg_8]
0x1800587e4  lea     rcx, [rbp+var_20]
0x1800587e8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800587ed  lea     rcx, [rbp+var_38]; this
0x1800587f1  call    ?Release@CCryptProv@ATL@@QEAAJXZ; ATL::CCryptProv::Release(void)
0x1800587f6  mov     rcx, [rbp+var_28]
0x1800587fa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800587fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180058803  mov     eax, ebx
0x180058805  mov     rbx, [rsp+80h+arg_0]
0x18005880d  add     rsp, 80h
0x180058814  pop     rdi
0x180058815  pop     rsi
0x180058816  pop     rbp
0x180058817  retn
```
