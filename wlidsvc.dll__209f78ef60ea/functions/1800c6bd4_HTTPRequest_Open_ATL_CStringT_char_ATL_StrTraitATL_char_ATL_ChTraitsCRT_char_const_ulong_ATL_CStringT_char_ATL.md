# HTTPRequest::Open(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ulong,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ulong,ulong,ulong,ulong)

- ea: `0x1800c6bd4`
- end: `0x1800c6e7e`
- name: `?Open@HTTPRequest@@QEAAJAEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@K00KKKK@Z`
- size: `682`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c4f64`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18002b33c`
- `0x1800a3b60`
- `0x1800c6bd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6cb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6cd1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6ceb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6cb7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6cd1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6e18`
- `WINHTTP!WinHttpSetOption` at `0x1800c6e0e`
- `WINHTTP!WinHttpSetOption` at `0x1800c6e0e`
- `WINHTTP!WinHttpOpen` at `0x1800c6ca1`
- `WINHTTP!WinHttpOpen` at `0x1800c6ca1`

## string_xrefs

- `0x1800c6c4a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c6d2c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c6de9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c6e34`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c6c33`: `HTTPRequest::Open`
- `0x1800c6d25`: `HTTPRequest::Open`
- `0x1800c6c27`: `strUserAgent: %hs, dwAccessType 0x%x`
- `0x1800c6ddc`: `Configured %ls timeout is %d ms.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HTTPRequest::Open(
        HINTERNET *a1,
        _QWORD *a2,
        DWORD a3,
        _QWORD *a4,
        _QWORD *a5,
        char a6,
        char a7,
        char a8,
        char a9)
{
  const WCHAR *v13; // rdi
  const WCHAR *v14; // rbx
  LPCWSTR *v15; // rax
  HINTERNET v16; // rbx
  signed int LastError; // eax
  unsigned int i; // ebx
  _DWORD *v19; // rsi
  const wchar_t *v20; // r14
  unsigned int v21; // ebx
  __int64 v23; // [rsp+28h] [rbp-D8h]
  signed int v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwOption[2]; // [rsp+50h] [rbp-B0h]
  LPVOID lpBuffer; // [rsp+58h] [rbp-A8h]
  const wchar_t *v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  char *v29; // [rsp+70h] [rbp-90h]
  const wchar_t *v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+80h] [rbp-80h]
  char *v32; // [rsp+88h] [rbp-78h]
  const wchar_t *v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  char *v35; // [rsp+A0h] [rbp-60h]
  const wchar_t *v36; // [rsp+A8h] [rbp-58h]
  const char *v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  void *Block; // [rsp+D0h] [rbp-30h] BYREF
  char v39; // [rsp+D8h] [rbp-28h] BYREF
  void *v40; // [rsp+1E0h] [rbp+E0h] BYREF
  char v41; // [rsp+1E8h] [rbp+E8h] BYREF
  void *v42; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v43; // [rsp+2F8h] [rbp+1F8h] BYREF

  v24[0] = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v37,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    2712,
    (const char *)v24,
    "HTTPRequest::Open",
    L"strUserAgent: %hs, dwAccessType 0x%x",
    *a2,
    a3);
  v13 = *(const WCHAR **)ATL::CA2WEX<128>::CA2WEX<128>(&v42, *a5);
  v14 = *(const WCHAR **)ATL::CA2WEX<128>::CA2WEX<128>(&v40, *a4);
  v15 = (LPCWSTR *)ATL::CA2WEX<128>::CA2WEX<128>(&Block, *a2);
  v16 = WinHttpOpen(*v15, a3, v14, v13, 0);
  if ( Block != &v39 )
    free(Block);
  if ( v40 != &v41 )
    free(v40);
  if ( v42 != &v43 )
    free(v42);
  if ( v16 )
    goto LABEL_12;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v24[0] = LastError;
  if ( LastError >= 0 )
  {
LABEL_12:
    *a1 = v16;
    dwOption[0] = 3;
    lpBuffer = &a7;
    v27 = L"connect";
    v28 = 6;
    v29 = &a8;
    v30 = L"receive";
    v31 = 5;
    v32 = &a9;
    v33 = L"send";
    v34 = 2;
    v35 = &a6;
    v36 = L"resolve";
    for ( i = 0; i < 4; ++i )
    {
      v19 = *(&lpBuffer + 3 * (int)i);
      v20 = (&v27)[3 * (int)i];
      LODWORD(v23) = *v19;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        0xAB6u,
        L"Configured %ls timeout is %d ms.",
        v20,
        v23);
      if ( *v19 && !WinHttpSetOption(*a1, dwOption[6 * i], v19, 4u) )
      {
        LODWORD(v23) = GetLastError();
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          0xAC0u,
          L"Unable to set %ls timeout - InternetSetOption failed (0x%x).",
          v20,
          v23);
      }
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "HTTPRequest::Open",
      0xAA1u,
      LastError,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
  v21 = v24[0];
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v37);
  return v21;
}

```

## disassembly

```asm
0x1800c6bd4  push    rbp
0x1800c6bd6  push    rbx
0x1800c6bd7  push    rsi
0x1800c6bd8  push    rdi
0x1800c6bd9  push    r12
0x1800c6bdb  push    r14
0x1800c6bdd  push    r15
0x1800c6bdf  lea     rbp, [rsp-310h]
0x1800c6be7  sub     rsp, 410h
0x1800c6bee  mov     rax, cs:__security_cookie
0x1800c6bf5  xor     rax, rsp
0x1800c6bf8  mov     [rbp+340h+var_40], rax
0x1800c6bff  mov     rsi, r9
0x1800c6c02  mov     r15d, r8d
0x1800c6c05  mov     r14, rdx
0x1800c6c08  mov     r12, rcx
0x1800c6c0b  mov     rbx, [rbp+340h+arg_20]
0x1800c6c12  mov     [rsp+440h+var_400], 0
0x1800c6c1a  mov     [rsp+440h+var_408], r8d
0x1800c6c1f  mov     rax, [rdx]
0x1800c6c22  mov     [rsp+440h+var_410], rax
0x1800c6c27  lea     rax, aStruseragentHs; "strUserAgent: %hs, dwAccessType 0x%x"
0x1800c6c2e  mov     [rsp+440h+var_418], rax
0x1800c6c33  lea     rax, aHttprequestOpe; "HTTPRequest::Open"
0x1800c6c3a  mov     qword ptr [rsp+440h+dwFlags], rax
0x1800c6c3f  lea     r9, [rsp+440h+var_400]
0x1800c6c44  mov     r8d, 0A98h
0x1800c6c4a  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6c51  lea     rcx, [rbp+340h+var_390]
0x1800c6c55  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800c6c5a  nop
0x1800c6c5b  mov     rdx, [rbx]
0x1800c6c5e  lea     rcx, [rbp+340h+var_150]
0x1800c6c65  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x1800c6c6a  nop
0x1800c6c6b  mov     rdi, [rax]
0x1800c6c6e  mov     rdx, [rsi]
0x1800c6c71  lea     rcx, [rbp+340h+var_260]
0x1800c6c78  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x1800c6c7d  nop
0x1800c6c7e  mov     rbx, [rax]
0x1800c6c81  mov     rdx, [r14]
0x1800c6c84  lea     rcx, [rbp+340h+Block]
0x1800c6c88  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x1800c6c8d  mov     [rsp+440h+dwFlags], 0; dwFlags
0x1800c6c95  mov     r9, rdi; pszProxyBypassW
0x1800c6c98  mov     r8, rbx; pszProxyW
0x1800c6c9b  mov     edx, r15d; dwAccessType
0x1800c6c9e  mov     rcx, [rax]; pszAgentW
0x1800c6ca1  call    cs:__imp_WinHttpOpen
0x1800c6ca7  mov     rbx, rax
0x1800c6caa  mov     rcx, [rbp+340h+Block]; Block
0x1800c6cae  lea     rax, [rbp+340h+var_368]
0x1800c6cb2  cmp     rcx, rax
0x1800c6cb5  jz      short loc_1800C6CBE
0x1800c6cb7  call    cs:__imp_free
0x1800c6cbd  nop
0x1800c6cbe  mov     rcx, [rbp+340h+var_260]; Block
0x1800c6cc5  lea     rax, [rbp+340h+var_258]
0x1800c6ccc  cmp     rcx, rax
0x1800c6ccf  jz      short loc_1800C6CD8
0x1800c6cd1  call    cs:__imp_free
0x1800c6cd7  nop
0x1800c6cd8  mov     rcx, [rbp+340h+var_150]; Block
0x1800c6cdf  lea     rax, [rbp+340h+var_148]
0x1800c6ce6  cmp     rcx, rax
0x1800c6ce9  jz      short loc_1800C6CF1
0x1800c6ceb  call    cs:__imp_free
0x1800c6cf1  test    rbx, rbx
0x1800c6cf4  jnz     short loc_1800C6D3D
0x1800c6cf6  call    cs:__imp_GetLastError
0x1800c6cfc  test    eax, eax
0x1800c6cfe  jle     short loc_1800C6D08
0x1800c6d00  movzx   eax, ax
0x1800c6d03  or      eax, 80070000h
0x1800c6d08  mov     [rsp+440h+var_400], eax
0x1800c6d0c  test    eax, eax
0x1800c6d0e  jns     short loc_1800C6D3D
0x1800c6d10  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800c6d17  mov     qword ptr [rsp+440h+dwFlags], r8; char *
0x1800c6d1c  mov     r9d, eax; int
0x1800c6d1f  mov     r8d, 0AA1h; unsigned int
0x1800c6d25  lea     rdx, aHttprequestOpe; "HTTPRequest::Open"
0x1800c6d2c  lea     rcx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6d33  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c6d38  jmp     loc_1800C6E4E
0x1800c6d3d  mov     [r12], rbx
0x1800c6d41  mov     [rsp+440h+dwOption], 3
0x1800c6d49  lea     rax, [rbp+340h+arg_30]
0x1800c6d50  mov     [rsp+440h+lpBuffer], rax
0x1800c6d55  lea     rax, aConnect; "connect"
0x1800c6d5c  mov     [rsp+440h+var_3E0], rax
0x1800c6d61  mov     [rsp+440h+var_3D8], 6
0x1800c6d69  lea     rax, [rbp+340h+arg_38]
0x1800c6d70  mov     [rsp+440h+var_3D0], rax
0x1800c6d75  lea     rax, aReceive; "receive"
0x1800c6d7c  mov     [rsp+440h+var_3C8], rax
0x1800c6d81  mov     r15d, 5
0x1800c6d87  mov     [rbp+340h+var_3C0], r15d
0x1800c6d8b  lea     rax, [rbp+340h+arg_40]
0x1800c6d92  mov     [rbp+340h+var_3B8], rax
0x1800c6d96  lea     rax, aSend; "send"
0x1800c6d9d  mov     [rbp+340h+var_3B0], rax
0x1800c6da1  mov     [rbp+340h+var_3A8], 2
0x1800c6da8  lea     rax, [rbp+340h+arg_28]
0x1800c6daf  mov     [rbp+340h+var_3A0], rax
0x1800c6db3  lea     rax, aResolve; "resolve"
0x1800c6dba  mov     [rbp+340h+var_398], rax
0x1800c6dbe  xor     ebx, ebx
0x1800c6dc0  movsxd  rax, ebx
0x1800c6dc3  lea     rdi, [rax+rax*2]
0x1800c6dc7  mov     rsi, [rsp+rdi*8+440h+lpBuffer]
0x1800c6dcc  mov     r14, [rsp+rdi*8+440h+var_3E0]
0x1800c6dd1  mov     eax, [rsi]
0x1800c6dd3  mov     dword ptr [rsp+440h+var_418], eax
0x1800c6dd7  mov     qword ptr [rsp+440h+dwFlags], r14
0x1800c6ddc  lea     r9, aConfiguredLsTi; "Configured %ls timeout is %d ms."
0x1800c6de3  mov     r8d, 0AB6h; unsigned int
0x1800c6de9  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6df0  mov     ecx, r15d; unsigned __int8
0x1800c6df3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c6df8  cmp     dword ptr [rsi], 0
0x1800c6dfb  jz      short loc_1800C6E43
0x1800c6dfd  mov     r9d, 4; dwBufferLength
0x1800c6e03  mov     r8, rsi; lpBuffer
0x1800c6e06  mov     edx, [rsp+rdi*8+440h+dwOption]; dwOption
0x1800c6e0a  mov     rcx, [r12]; hInternet
0x1800c6e0e  call    cs:__imp_WinHttpSetOption
0x1800c6e14  test    eax, eax
0x1800c6e16  jnz     short loc_1800C6E43
0x1800c6e18  call    cs:__imp_GetLastError
0x1800c6e1e  mov     dword ptr [rsp+440h+var_418], eax
0x1800c6e22  mov     qword ptr [rsp+440h+dwFlags], r14
0x1800c6e27  lea     r9, aUnableToSetLsT; "Unable to set %ls timeout - InternetSet"...
0x1800c6e2e  mov     r8d, 0AC0h; unsigned int
0x1800c6e34  lea     rdx, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c6e3b  mov     ecx, r15d; unsigned __int8
0x1800c6e3e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c6e43  inc     ebx
0x1800c6e45  cmp     ebx, 4
0x1800c6e48  jb      loc_1800C6DC0
0x1800c6e4e  mov     ebx, [rsp+440h+var_400]
0x1800c6e52  lea     rcx, [rbp+340h+var_390]
0x1800c6e56  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c6e5b  mov     eax, ebx
0x1800c6e5d  mov     rcx, [rbp+340h+var_40]
0x1800c6e64  xor     rcx, rsp; StackCookie
0x1800c6e67  call    __security_check_cookie
0x1800c6e6c  add     rsp, 410h
0x1800c6e73  pop     r15
0x1800c6e75  pop     r14
0x1800c6e77  pop     r12
0x1800c6e79  pop     rdi
0x1800c6e7a  pop     rsi
0x1800c6e7b  pop     rbx
0x1800c6e7c  pop     rbp
0x1800c6e7d  retn
```
