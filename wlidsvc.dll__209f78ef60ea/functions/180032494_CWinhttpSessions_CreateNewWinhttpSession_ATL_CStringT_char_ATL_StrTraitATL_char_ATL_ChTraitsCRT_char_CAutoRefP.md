# CWinhttpSessions::CreateNewWinhttpSession(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CAutoRefPtr<CWinhttpSession> &)

- ea: `0x180032494`
- end: `0x18003263a`
- name: `?CreateNewWinhttpSession@CWinhttpSessions@@AEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAV?$CAutoRefPtr@VCWinhttpSession@@@@@Z`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800320a8`
- `0x1800888e8`

## callees

- `0x18000c050`
- `0x18000edd0`
- `0x1800124c4`
- `0x180015fdc`
- `0x180019690`
- `0x18002b33c`
- `0x180032494`
- `0x180035b8c`
- `0x1800859c4`
- `0x18008b65c`
- `0x1800a3b60`
- `0x1800a716c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032506`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032511`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800325d9`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800325d9`
- `WINHTTP!WinHttpOpen` at `0x1800324e8`
- `WINHTTP!WinHttpOpen` at `0x1800324e8`

## string_xrefs

- `0x180032546`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x1800325f9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\transport.cpp`
- `0x18003253f`: `CWinhttpSessions::CreateNewWinhttpSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinhttpSessions::CreateNewWinhttpSession(__int64 a1, _QWORD *a2, __int64 a3)
{
  signed int v5; // edi
  LPCWSTR *v6; // rax
  HINTERNET v7; // rbp
  signed int LastError; // eax
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  CClientConfigDataCacheManager *v11; // rax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-358h]
  _BYTE v14[112]; // [rsp+40h] [rbp-338h] BYREF
  int nResolveTimeout; // [rsp+B0h] [rbp-2C8h]
  int nConnectTimeout; // [rsp+B4h] [rbp-2C4h]
  int nSendTimeout; // [rsp+B8h] [rbp-2C0h]
  int nReceiveTimeout; // [rsp+BCh] [rbp-2BCh]
  void *Block; // [rsp+240h] [rbp-138h] BYREF
  char v20; // [rsp+248h] [rbp-130h] BYREF

  v5 = 0;
  CONFIGDATA::CONFIGDATA((CONFIGDATA *)v14);
  v6 = (LPCWSTR *)ATL::CA2WEX<128>::CA2WEX<128>(&Block, *a2);
  v7 = WinHttpOpen(*v6, 4u, 0, 0, 0);
  if ( Block != &v20 )
    free(Block);
  if ( v7 )
    goto LABEL_8;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_8:
    v9 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v10 = v9;
    if ( v9 )
    {
      v9[2] = 1;
      *(_QWORD *)v9 = &CWinhttpSession::`vftable';
      *((_QWORD *)v9 + 2) = v7;
    }
    else
    {
      v10 = 0;
    }
    CAutoRefPtr<IStoredIdentity>::Deinit(a3);
    *(_QWORD *)a3 = v10;
    if ( v10 )
    {
      v11 = CClientConfigDataCacheManager::theConfigDataManager();
      CClientConfigDataCacheManager::CopyConfigDataForTransport(v11, (struct CONFIGDATA *)v14);
      if ( !WinHttpSetTimeouts(
              *(HINTERNET *)(*(_QWORD *)a3 + 16LL),
              nResolveTimeout,
              nConnectTimeout,
              nSendTimeout,
              nReceiveTimeout) )
      {
        dwFlags[0] = ATL::AtlHresultFromLastError();
        TracePrintW(
          3u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
          0x5C2u,
          L"WinHttpSetTimeouts failed (0x%x).",
          *(_QWORD *)dwFlags);
      }
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\transport.cpp",
      "CWinhttpSessions::CreateNewWinhttpSession",
      0x5B1u,
      v5,
      "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
  CONFIGDATA::~CONFIGDATA((CONFIGDATA *)v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032494  mov     [rsp+arg_0], rbx
0x180032499  push    rbp
0x18003249a  push    rsi
0x18003249b  push    rdi
0x18003249c  sub     rsp, 360h
0x1800324a3  mov     rax, cs:__security_cookie
0x1800324aa  xor     rax, rsp
0x1800324ad  mov     [rsp+378h+var_28], rax
0x1800324b5  mov     rsi, r8
0x1800324b8  mov     rbx, rdx
0x1800324bb  xor     edi, edi
0x1800324bd  lea     rcx, [rsp+378h+var_338]; this
0x1800324c2  call    ??0CONFIGDATA@@QEAA@XZ; CONFIGDATA::CONFIGDATA(void)
0x1800324c7  nop
0x1800324c8  mov     rdx, [rbx]
0x1800324cb  lea     rcx, [rsp+378h+Block]
0x1800324d3  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x1800324d8  mov     [rsp+378h+dwFlags], edi; dwFlags
0x1800324dc  xor     r9d, r9d; pszProxyBypassW
0x1800324df  xor     r8d, r8d; pszProxyW
0x1800324e2  lea     edx, [rdi+4]; dwAccessType
0x1800324e5  mov     rcx, [rax]; pszAgentW
0x1800324e8  call    cs:__imp_WinHttpOpen
0x1800324ee  mov     rbp, rax
0x1800324f1  mov     rcx, [rsp+378h+Block]; Block
0x1800324f9  lea     rax, [rsp+378h+var_130]
0x180032501  cmp     rcx, rax
0x180032504  jz      short loc_18003250C
0x180032506  call    cs:__imp_free
0x18003250c  test    rbp, rbp
0x18003250f  jnz     short loc_180032557
0x180032511  call    cs:__imp_GetLastError
0x180032517  mov     edi, eax
0x180032519  test    eax, eax
0x18003251b  jle     short loc_180032526
0x18003251d  movzx   edi, ax
0x180032520  or      edi, 80070000h
0x180032526  test    edi, edi
0x180032528  jns     short loc_180032557
0x18003252a  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180032531  mov     qword ptr [rsp+378h+dwFlags], rax; char *
0x180032536  mov     r9d, edi; int
0x180032539  mov     r8d, 5B1h; unsigned int
0x18003253f  lea     rdx, aCwinhttpsessio_0; "CWinhttpSessions::CreateNewWinhttpSessi"...
0x180032546  lea     rcx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18003254d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180032552  jmp     loc_18003260B
0x180032557  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003255e  mov     ecx, 18h; unsigned __int64
0x180032563  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180032568  mov     rbx, rax
0x18003256b  mov     [rsp+378h+var_348], rax
0x180032570  test    rax, rax
0x180032573  jz      short loc_18003258C
0x180032575  mov     dword ptr [rax+8], 1
0x18003257c  lea     rax, ??_7CWinhttpSession@@6B@; const CWinhttpSession::`vftable'
0x180032583  mov     [rbx], rax
0x180032586  mov     [rbx+10h], rbp
0x18003258a  jmp     short loc_18003258E
0x18003258c  xor     ebx, ebx
0x18003258e  mov     rcx, rsi
0x180032591  call    ?Deinit@?$CAutoRefPtr@VIStoredIdentity@@@@IEAAXXZ; CAutoRefPtr<IStoredIdentity>::Deinit(void)
0x180032596  mov     [rsi], rbx
0x180032599  test    rbx, rbx
0x18003259c  jz      short loc_18003260B
0x18003259e  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x1800325a3  lea     rdx, [rsp+378h+var_338]; struct CONFIGDATA *
0x1800325a8  mov     rcx, rax; this
0x1800325ab  call    ?CopyConfigDataForTransport@CClientConfigDataCacheManager@@QEAAXAEAUCONFIGDATA@@@Z; CClientConfigDataCacheManager::CopyConfigDataForTransport(CONFIGDATA &)
0x1800325b0  mov     rcx, [rsi]
0x1800325b3  mov     eax, [rsp+378h+nReceiveTimeout]
0x1800325ba  mov     [rsp+378h+dwFlags], eax; nReceiveTimeout
0x1800325be  mov     r9d, [rsp+378h+nSendTimeout]; nSendTimeout
0x1800325c6  mov     r8d, [rsp+378h+nConnectTimeout]; nConnectTimeout
0x1800325ce  mov     edx, [rsp+378h+nResolveTimeout]; nResolveTimeout
0x1800325d5  mov     rcx, [rcx+10h]; hInternet
0x1800325d9  call    cs:__imp_WinHttpSetTimeouts
0x1800325df  test    eax, eax
0x1800325e1  jnz     short loc_18003260B
0x1800325e3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800325e8  mov     [rsp+378h+dwFlags], eax
0x1800325ec  lea     r9, aWinhttpsettime_0; "WinHttpSetTimeouts failed (0x%x)."
0x1800325f3  mov     r8d, 5C2h; unsigned int
0x1800325f9  lea     rdx, aOnecoreuapDsEx_35; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180032600  mov     ecx, 3; unsigned __int8
0x180032605  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003260a  nop
0x18003260b  lea     rcx, [rsp+378h+var_338]; this
0x180032610  call    ??1CONFIGDATA@@QEAA@XZ; CONFIGDATA::~CONFIGDATA(void)
0x180032615  mov     eax, edi
0x180032617  mov     rcx, [rsp+378h+var_28]
0x18003261f  xor     rcx, rsp; StackCookie
0x180032622  call    __security_check_cookie
0x180032627  mov     rbx, [rsp+378h+arg_0]
0x18003262f  add     rsp, 360h
0x180032636  pop     rdi
0x180032637  pop     rsi
0x180032638  pop     rbp
0x180032639  retn
```
