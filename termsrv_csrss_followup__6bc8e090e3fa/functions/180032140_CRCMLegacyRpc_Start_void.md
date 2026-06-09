# CRCMLegacyRpc::Start(void)

- ea: `0x180032140`
- end: `0x18003245a`
- name: `?Start@CRCMLegacyRpc@@UEAAJXZ`
- size: `794`
- prototype: `__int64 __fastcall(CRCMLegacyRpc *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009940`
- `0x180028dd8`
- `0x180028e44`
- `0x180028f88`
- `0x180032140`
- `0x180033f60`
- `0x1800635d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a7`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18003236d`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18003236d`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180032343`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180032343`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800322f6`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800322f6`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800323d7`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800323d7`
- `RPCRT4!RpcServerListen` at `0x180032402`
- `RPCRT4!RpcServerListen` at `0x180032402`
- `RPCRT4!RpcStringFreeW` at `0x180032388`
- `RPCRT4!RpcStringFreeW` at `0x180032388`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032249`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032249`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003228f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003228f`

## string_xrefs

- `0x1800321b4`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180032274`: `ExpandEnvironmentStrings failed for winsta.dll`
- `0x1800322ca`: `LoadLibrary( %ws ) failed: 0x%x`
- `0x180032242`: `%SystemRoot%\System32\winsta.dll`
- `0x1800322e3`: `\pipe\Ctx_WinStation_API_service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRCMLegacyRpc::Start(CRCMLegacyRpc *this)
{
  int v2; // ebx
  BOOL v3; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  HMODULE LibraryW; // rax
  signed int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const unsigned __int16 *MaxCalls; // [rsp+20h] [rbp-E0h]
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  RPC_WSTR PrincName; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+64h] [rbp-9Ch]
  WCHAR Dst[264]; // [rsp+70h] [rbp-90h] BYREF

  PrincName = 0;
  v2 = CRCMLegacyRpc::fEncryptRPCTraffic;
  v14[0] = &CRegistry::`vftable';
  v14[1] = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = -1;
  v3 = CRegistry::OpenKey(
         (CRegistry *)v14,
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0x20019u,
         MaxCalls)
    || (v12 = 0, CRegistry::ReadRegDWord((CRegistry *)v14, L"fEncryptRPCTraffic", &v12))
    || v12 != 0;
  CRCMLegacyRpc::fEncryptRPCTraffic = v3;
  CRegistry::~CRegistry((CRegistry *)v14);
  if ( v2 != CRCMLegacyRpc::fEncryptRPCTraffic )
    CRCMLegacyRpc::Stop(this);
  if ( *((_DWORD *)this + 398) )
    return 0;
  if ( !*((_QWORD *)this + 215) )
  {
    if ( !ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\winsta.dll", Dst, 0x104u) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      _DbgPrintMessage(8, "ExpandEnvironmentStrings failed for winsta.dll");
      return v5;
    }
    LibraryW = LoadLibraryW(Dst);
    *((_QWORD *)this + 215) = LibraryW;
    if ( !LibraryW )
    {
      v7 = GetLastError();
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      _DbgPrintMessage(8, "LoadLibrary( %ws ) failed: 0x%x", Dst, v5);
      return v5;
    }
  }
  v8 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0x80u, (RPC_WSTR)L"\\pipe\\Ctx_WinStation_API_service", 0);
  v5 = v8;
  if ( v8 && v8 != 1740 )
  {
    _DbgPrintMessage(8, "Error %d RpcUseProtseqEp on ncacn_np", v8);
    goto LABEL_20;
  }
  v5 = RpcServerInqDefaultPrincNameW(9u, &PrincName);
  if ( v5 )
  {
    _DbgPrintMessage(8, "Error %d RpcServerInqDefaultPrincName", v5);
    goto LABEL_20;
  }
  v5 = RpcServerRegisterAuthInfoW(PrincName, 9u, 0, 0);
  if ( PrincName )
    RpcStringFreeW(&PrincName);
  if ( v5 )
  {
    _DbgPrintMessage(8, "Error %d RpcServerRegisterAuthInfo", v5);
    goto LABEL_20;
  }
  v5 = RpcServerRegisterIfEx(
         qword_1800D7D80,
         0,
         0,
         CRCMLegacyRpc::fEncryptRPCTraffic != 0 ? 9 : 17,
         0x4D2u,
         CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback);
  if ( v5 )
  {
    _DbgPrintMessage(8, "Error %d RpcServerRegisterIf", v5);
    goto LABEL_20;
  }
  v9 = RpcServerListen(1u, 0x4D2u, 1u);
  v5 = v9;
  if ( !v9 || v9 == 1713 )
  {
    *((_DWORD *)this + 398) = 1;
    return 0;
  }
  _DbgPrintMessage(8, "Error %d RpcServerListen", v9);
LABEL_20:
  if ( (int)v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x180032140  mov     [rsp-8+arg_8], rbx
0x180032145  mov     [rsp-8+arg_10], rsi
0x18003214a  push    rbp
0x18003214b  lea     rbp, [rsp-190h]
0x180032153  sub     rsp, 290h
0x18003215a  mov     rax, cs:__security_cookie
0x180032161  xor     rax, rsp
0x180032164  mov     [rbp+190h+var_10], rax
0x18003216b  mov     rsi, rcx
0x18003216e  mov     [rsp+290h+PrincName], 0
0x180032177  mov     ebx, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x18003217d  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180032184  mov     [rsp+290h+var_250], rax
0x180032189  mov     [rsp+290h+var_248], 0
0x180032192  mov     [rsp+290h+var_240], 0
0x18003219a  mov     [rsp+290h+var_238], 0
0x1800321a3  or      eax, 0FFFFFFFFh
0x1800321a6  mov     [rsp+290h+var_230], eax
0x1800321aa  mov     [rsp+290h+var_22C], eax
0x1800321ae  mov     r9d, 20019h; unsigned int
0x1800321b4  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800321bb  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800321c2  lea     rcx, [rsp+290h+var_250]; this
0x1800321c7  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800321cc  test    eax, eax
0x1800321ce  jnz     short loc_1800321F7
0x1800321d0  mov     [rsp+290h+var_260], eax
0x1800321d4  lea     r8, [rsp+290h+var_260]; unsigned int *
0x1800321d9  lea     rdx, aFencryptrpctra; "fEncryptRPCTraffic"
0x1800321e0  lea     rcx, [rsp+290h+var_250]; this
0x1800321e5  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x1800321ea  test    eax, eax
0x1800321ec  jnz     short loc_1800321F7
0x1800321ee  cmp     [rsp+290h+var_260], eax
0x1800321f2  setnz   al
0x1800321f5  jmp     short loc_1800321FC
0x1800321f7  mov     eax, 1
0x1800321fc  mov     cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA, eax; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180032202  lea     rcx, [rsp+290h+var_250]; this
0x180032207  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18003220c  cmp     ebx, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180032212  jz      short loc_18003221C
0x180032214  mov     rcx, rsi; this
0x180032217  call    ?Stop@CRCMLegacyRpc@@UEAAJXZ; CRCMLegacyRpc::Stop(void)
0x18003221c  cmp     dword ptr [rsi+638h], 0
0x180032223  jnz     loc_180032431
0x180032229  cmp     qword ptr [rsi+6B8h], 0
0x180032231  jnz     loc_1800322E0
0x180032237  mov     r8d, 104h; nSize
0x18003223d  lea     rdx, [rsp+290h+Dst]; lpDst
0x180032242  lea     rcx, Src; "%SystemRoot%\\System32\\winsta.dll"
0x180032249  call    cs:__imp_ExpandEnvironmentStringsW
0x180032250  nop     dword ptr [rax+rax+00h]
0x180032255  test    eax, eax
0x180032257  jnz     short loc_18003228A
0x180032259  call    cs:__imp_GetLastError
0x180032260  nop     dword ptr [rax+rax+00h]
0x180032265  mov     ebx, eax
0x180032267  test    eax, eax
0x180032269  jle     short loc_180032274
0x18003226b  movzx   ebx, ax
0x18003226e  or      ebx, 80070000h
0x180032274  lea     rdx, aExpandenvironm_0; "ExpandEnvironmentStrings failed for win"...
0x18003227b  mov     ecx, 8; int
0x180032280  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032285  jmp     loc_180032433
0x18003228a  lea     rcx, [rsp+290h+Dst]; lpLibFileName
0x18003228f  call    cs:__imp_LoadLibraryW
0x180032296  nop     dword ptr [rax+rax+00h]
0x18003229b  mov     [rsi+6B8h], rax
0x1800322a2  test    rax, rax
0x1800322a5  jnz     short loc_1800322E0
0x1800322a7  call    cs:__imp_GetLastError
0x1800322ae  nop     dword ptr [rax+rax+00h]
0x1800322b3  mov     ebx, eax
0x1800322b5  test    eax, eax
0x1800322b7  jle     short loc_1800322C2
0x1800322b9  movzx   ebx, ax
0x1800322bc  or      ebx, 80070000h
0x1800322c2  mov     r9d, ebx
0x1800322c5  lea     r8, [rsp+290h+Dst]
0x1800322ca  lea     rdx, aLoadlibraryWsF; "LoadLibrary( %ws ) failed: 0x%x"
0x1800322d1  mov     ecx, 8; int
0x1800322d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800322db  jmp     loc_180032433
0x1800322e0  xor     r9d, r9d; SecurityDescriptor
0x1800322e3  lea     r8, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x1800322ea  mov     edx, 80h; MaxCalls
0x1800322ef  lea     rcx, Protseq; "ncacn_np"
0x1800322f6  call    cs:__imp_RpcServerUseProtseqEpW
0x1800322fd  nop     dword ptr [rax+rax+00h]
0x180032302  mov     ebx, eax
0x180032304  test    eax, eax
0x180032306  jz      short loc_180032339
0x180032308  cmp     eax, 6CCh
0x18003230d  jz      short loc_180032339
0x18003230f  lea     rdx, aErrorDRpcusepr_0; "Error %d RpcUseProtseqEp on ncacn_np"
0x180032316  mov     r8d, ebx
0x180032319  mov     ecx, 8; int
0x18003231e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180032323  test    ebx, ebx
0x180032325  jle     loc_180032433
0x18003232b  movzx   ebx, bx
0x18003232e  or      ebx, 80070000h
0x180032334  jmp     loc_180032433
0x180032339  lea     rdx, [rsp+290h+PrincName]; PrincName
0x18003233e  mov     ecx, 9; AuthnSvc
0x180032343  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18003234a  nop     dword ptr [rax+rax+00h]
0x18003234f  mov     ebx, eax
0x180032351  test    eax, eax
0x180032353  jz      short loc_18003235E
0x180032355  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerInqDefaultPrincName"
0x18003235c  jmp     short loc_180032316
0x18003235e  xor     r9d, r9d; Arg
0x180032361  xor     r8d, r8d; GetKeyFn
0x180032364  lea     edx, [r9+9]; AuthnSvc
0x180032368  mov     rcx, [rsp+290h+PrincName]; ServerPrincName
0x18003236d  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180032374  nop     dword ptr [rax+rax+00h]
0x180032379  mov     ebx, eax
0x18003237b  cmp     [rsp+290h+PrincName], 0
0x180032381  jz      short loc_180032394
0x180032383  lea     rcx, [rsp+290h+PrincName]; String
0x180032388  call    cs:__imp_RpcStringFreeW
0x18003238f  nop     dword ptr [rax+rax+00h]
0x180032394  test    ebx, ebx
0x180032396  jz      short loc_1800323A4
0x180032398  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterAuthInfo"
0x18003239f  jmp     loc_180032316
0x1800323a4  mov     eax, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x1800323aa  neg     eax
0x1800323ac  sbb     r9d, r9d
0x1800323af  and     r9d, 0FFFFFFF8h
0x1800323b3  add     r9d, 11h; Flags
0x1800323b7  lea     rax, ?staticRCMLegacyRpcSecurityCallback@CRCMLegacyRpc@@CAJPEAX0@Z; CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback(void *,void *)
0x1800323be  mov     [rsp+290h+IfCallback], rax; IfCallback
0x1800323c3  mov     dword ptr [rsp+290h+MaxCalls], 4D2h; MaxCalls
0x1800323cb  xor     r8d, r8d; MgrEpv
0x1800323ce  xor     edx, edx; MgrTypeUuid
0x1800323d0  lea     rcx, qword_1800D7D80; IfSpec
0x1800323d7  call    cs:__imp_RpcServerRegisterIfEx
0x1800323de  nop     dword ptr [rax+rax+00h]
0x1800323e3  mov     ebx, eax
0x1800323e5  test    eax, eax
0x1800323e7  jz      short loc_1800323F5
0x1800323e9  lea     rdx, aErrorDRpcserve_2; "Error %d RpcServerRegisterIf"
0x1800323f0  jmp     loc_180032316
0x1800323f5  mov     edx, 4D2h; MaxCalls
0x1800323fa  mov     ecx, 1; MinimumCallThreads
0x1800323ff  mov     r8d, ecx; DontWait
0x180032402  call    cs:__imp_RpcServerListen
0x180032409  nop     dword ptr [rax+rax+00h]
0x18003240e  mov     ebx, eax
0x180032410  test    eax, eax
0x180032412  jz      short loc_180032427
0x180032414  cmp     eax, 6B1h
0x180032419  jz      short loc_180032427
0x18003241b  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x180032422  jmp     loc_180032316
0x180032427  mov     dword ptr [rsi+638h], 1
0x180032431  xor     ebx, ebx
0x180032433  mov     eax, ebx
0x180032435  mov     rcx, [rbp+190h+var_10]
0x18003243c  xor     rcx, rsp; StackCookie
0x18003243f  call    __security_check_cookie
0x180032444  lea     r11, [rsp+290h+var_s0]
0x18003244c  mov     rbx, [r11+18h]
0x180032450  mov     rsi, [r11+20h]
0x180032454  mov     rsp, r11
0x180032457  pop     rbp
0x180032458  retn
```
