# CStoredIdentity::RemoveFromCertStore(uchar *,ulong)

- ea: `0x1800c3ca8`
- end: `0x1800c3e5d`
- name: `?RemoveFromCertStore@CStoredIdentity@@AEAAJPEAEK@Z`
- size: `437`
- prototype: `__int64 __fastcall(CStoredIdentity *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b74c`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180034908`
- `0x18004ff98`
- `0x1800c3ca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3d5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3dfc`
- `CRYPT32!CertOpenStore` at `0x1800c3d3f`
- `CRYPT32!CertOpenStore` at `0x1800c3d3f`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c3db4`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c3db4`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800c3df2`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800c3df2`

## string_xrefs

- `0x1800c3cf4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c3e2a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\systemstore.cpp`
- `0x1800c3cbe`: `CStoredIdentity::RemoveFromCertStore`

## pseudocode

```c
__int64 __fastcall CStoredIdentity::RemoveFromCertStore(CStoredIdentity *this, unsigned __int8 *a2, int a3)
{
  HCERTSTORE v5; // rax
  HCERTSTORE v6; // rcx
  signed int LastError; // eax
  const CERT_CONTEXT *CertificateInStore; // rbx
  signed int v9; // eax
  signed int v10; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *pvPara; // [rsp+20h] [rbp-29h]
  __int128 pvFindPara; // [rsp+30h] [rbp-19h] BYREF
  void **v15; // [rsp+40h] [rbp-9h] BYREF
  HCERTSTORE hCertStore; // [rsp+48h] [rbp-1h]
  int v17; // [rsp+50h] [rbp+7h]
  _QWORD v18[9]; // [rsp+58h] [rbp+Fh] BYREF
  signed int v19; // [rsp+B0h] [rbp+67h] BYREF
  int v20; // [rsp+B4h] [rbp+6Bh]

  v20 = HIDWORD(this);
  v19 = 0;
  v18[0] = "CStoredIdentity::RemoveFromCertStore";
  v18[2] = 0;
  v18[3] = 0;
  v18[1] = &v19;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
    "CStoredIdentity::RemoveFromCertStore",
    (const char *)0x558,
    0,
    pvPara);
  v17 = 1;
  hCertStore = 0;
  v15 = &SmartHCERTSTORE::`vftable';
  pvFindPara = 0;
  v5 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x14400u, L"MY");
  SmartPtr<void *>::Attach(&v15, v5);
  v6 = hCertStore;
  if ( !hCertStore )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v19 = LastError;
    if ( LastError < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
        "CStoredIdentity::RemoveFromCertStore",
        0x564u,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
      goto LABEL_17;
    }
    v6 = hCertStore;
  }
  LODWORD(pvFindPara) = a3;
  *((_QWORD *)&pvFindPara + 1) = a2;
  CertificateInStore = CertFindCertificateInStore(v6, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
  if ( CertificateInStore )
    goto LABEL_20;
  v9 = GetLastError();
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  v19 = v9;
  if ( v9 >= 0 )
  {
LABEL_20:
    if ( !CertDeleteCertificateFromStore(CertificateInStore) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v19 = v10;
      if ( v10 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
          "CStoredIdentity::RemoveFromCertStore",
          0x571u,
          v10,
          "hr = HRESULT_FROM_WIN32(GetLastError())");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\systemstore.cpp",
      "CStoredIdentity::RemoveFromCertStore",
      0x56Fu,
      v9,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
LABEL_17:
  v11 = v19;
  SmartHCERTSTORE::~SmartHCERTSTORE((SmartHCERTSTORE *)&v15);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v18);
  return v11;
}

```

## disassembly

```asm
0x1800c3ca8  mov     [rsp-8+arg_0], rcx
0x1800c3cad  push    rbp
0x1800c3cae  push    rbx
0x1800c3caf  push    rdi
0x1800c3cb0  push    r14
0x1800c3cb2  lea     rbp, [rsp-3Fh]
0x1800c3cb7  sub     rsp, 88h
0x1800c3cbe  lea     r14, aCstoredidentit_5; "CStoredIdentity::RemoveFromCertStore"
0x1800c3cc5  mov     dword ptr [rbp+57h+arg_0], 0
0x1800c3ccc  mov     ebx, r8d
0x1800c3ccf  mov     [rbp+57h+var_48], r14
0x1800c3cd3  mov     rdi, rdx
0x1800c3cd6  mov     [rbp+57h+var_38], 0
0x1800c3cde  lea     rax, [rbp+57h+arg_0]
0x1800c3ce2  mov     [rbp+57h+var_30], 0
0x1800c3cea  mov     rdx, r14; char *
0x1800c3ced  mov     [rbp+57h+var_40], rax
0x1800c3cf1  xor     r9d, r9d; unsigned int
0x1800c3cf4  lea     rcx, aOnecoreuapDsEx_40; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c3cfb  mov     r8d, 558h; char *
0x1800c3d01  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800c3d06  xor     eax, eax
0x1800c3d08  mov     [rbp+57h+var_50], 1
0x1800c3d0f  mov     [rbp+57h+hCertStore], rax
0x1800c3d13  xor     edx, edx; dwEncodingType
0x1800c3d15  lea     rax, ??_7SmartHCERTSTORE@@6B@; const SmartHCERTSTORE::`vftable'
0x1800c3d1c  xorps   xmm0, xmm0
0x1800c3d1f  mov     [rbp+57h+var_60], rax
0x1800c3d23  mov     r9d, 14400h; dwFlags
0x1800c3d29  lea     rax, aMy; "MY"
0x1800c3d30  xor     r8d, r8d; hCryptProv
0x1800c3d33  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800c3d36  mov     [rsp+0A0h+pvPara], rax; pvPara
0x1800c3d3b  movups  [rbp+57h+pvFindPara], xmm0
0x1800c3d3f  call    cs:__imp_CertOpenStore
0x1800c3d45  mov     rdx, rax
0x1800c3d48  lea     rcx, [rbp+57h+var_60]
0x1800c3d4c  call    ?Attach@?$SmartPtr@PEAX@@QEAAXPEAX@Z; SmartPtr<void *>::Attach(void *)
0x1800c3d51  mov     rcx, [rbp+57h+hCertStore]
0x1800c3d55  test    rcx, rcx
0x1800c3d58  jnz     short loc_1800C3D8E
0x1800c3d5a  call    cs:__imp_GetLastError
0x1800c3d60  test    eax, eax
0x1800c3d62  jle     short loc_1800C3D6C
0x1800c3d64  movzx   eax, ax
0x1800c3d67  or      eax, 80070000h
0x1800c3d6c  mov     dword ptr [rbp+57h+arg_0], eax
0x1800c3d6f  test    eax, eax
0x1800c3d71  jns     short loc_1800C3D8A
0x1800c3d73  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c3d7a  mov     [rsp+0A0h+pvPara], r8
0x1800c3d7f  mov     r8d, 564h
0x1800c3d85  jmp     loc_1800C3E27
0x1800c3d8a  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x1800c3d8e  mov     r9d, 10000h; dwFindType
0x1800c3d94  mov     [rsp+0A0h+pPrevCertContext], 0; pPrevCertContext
0x1800c3d9d  lea     rax, [rbp+57h+pvFindPara]
0x1800c3da1  mov     dword ptr [rbp+57h+pvFindPara], ebx
0x1800c3da4  xor     r8d, r8d; dwFindFlags
0x1800c3da7  mov     qword ptr [rbp+57h+pvFindPara+8], rdi
0x1800c3dab  mov     [rsp+0A0h+pvPara], rax; pvFindPara
0x1800c3db0  lea     edx, [r9+1]; dwCertEncodingType
0x1800c3db4  call    cs:__imp_CertFindCertificateInStore
0x1800c3dba  mov     rbx, rax
0x1800c3dbd  test    rax, rax
0x1800c3dc0  jnz     short loc_1800C3DEF
0x1800c3dc2  call    cs:__imp_GetLastError
0x1800c3dc8  test    eax, eax
0x1800c3dca  jle     short loc_1800C3DD4
0x1800c3dcc  movzx   eax, ax
0x1800c3dcf  or      eax, 80070000h
0x1800c3dd4  mov     dword ptr [rbp+57h+arg_0], eax
0x1800c3dd7  test    eax, eax
0x1800c3dd9  jns     short loc_1800C3DEF
0x1800c3ddb  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c3de2  mov     [rsp+0A0h+pvPara], r8
0x1800c3de7  mov     r8d, 56Fh
0x1800c3ded  jmp     short loc_1800C3E27
0x1800c3def  mov     rcx, rbx; pCertContext
0x1800c3df2  call    cs:__imp_CertDeleteCertificateFromStore
0x1800c3df8  test    eax, eax
0x1800c3dfa  jnz     short loc_1800C3E39
0x1800c3dfc  call    cs:__imp_GetLastError
0x1800c3e02  test    eax, eax
0x1800c3e04  jle     short loc_1800C3E0E
0x1800c3e06  movzx   eax, ax
0x1800c3e09  or      eax, 80070000h
0x1800c3e0e  mov     dword ptr [rbp+57h+arg_0], eax
0x1800c3e11  test    eax, eax
0x1800c3e13  jns     short loc_1800C3E39
0x1800c3e15  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c3e1c  mov     [rsp+0A0h+pvPara], r8; char *
0x1800c3e21  mov     r8d, 571h; unsigned int
0x1800c3e27  mov     r9d, eax; int
0x1800c3e2a  lea     rcx, aOnecoreuapDsEx_40; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c3e31  mov     rdx, r14; char *
0x1800c3e34  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c3e39  mov     ebx, dword ptr [rbp+57h+arg_0]
0x1800c3e3c  lea     rcx, [rbp+57h+var_60]; this
0x1800c3e40  call    ??1SmartHCERTSTORE@@UEAA@XZ; SmartHCERTSTORE::~SmartHCERTSTORE(void)
0x1800c3e45  lea     rcx, [rbp+57h+var_48]
0x1800c3e49  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c3e4e  mov     eax, ebx
0x1800c3e50  add     rsp, 88h
0x1800c3e57  pop     r14
0x1800c3e59  pop     rdi
0x1800c3e5a  pop     rbx
0x1800c3e5b  pop     rbp
0x1800c3e5c  retn
```
