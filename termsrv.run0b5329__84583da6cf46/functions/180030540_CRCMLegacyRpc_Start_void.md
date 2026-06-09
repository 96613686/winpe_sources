# CRCMLegacyRpc::Start(void)

- ea: `0x180030540`
- end: `0x18003081a`
- name: `?Start@CRCMLegacyRpc@@UEAAJXZ`
- size: `730`
- prototype: `__int64 __fastcall(CRCMLegacyRpc *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800279a8`
- `0x180027a04`
- `0x180027b44`
- `0x180030540`
- `0x1800321f0`
- `0x180060570`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030695`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180030749`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180030749`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180030725`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180030725`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800306de`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800306de`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800307a4`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800307a4`
- `RPCRT4!RpcServerListen` at `0x1800307c9`
- `RPCRT4!RpcServerListen` at `0x1800307c9`
- `RPCRT4!RpcStringFreeW` at `0x18003075e`
- `RPCRT4!RpcStringFreeW` at `0x18003075e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180030649`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180030649`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030683`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030683`

## string_xrefs

- `0x1800305b4`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180030668`: `ExpandEnvironmentStrings failed for winsta.dll`
- `0x1800306b2`: `LoadLibrary( %ws ) failed: 0x%x`
- `0x180030642`: `%SystemRoot%\System32\winsta.dll`
- `0x1800306cb`: `\pipe\Ctx_WinStation_API_service`

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
         qword_1800D1CA0,
         0,
         0,
         CRCMLegacyRpc::fEncryptRPCTraffic != 0 ? 9 : 17,
         0x4D2u,
         (RPC_IF_CALLBACK_FN *)CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback);
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
0x180030540  mov     [rsp-8+arg_8], rbx
0x180030545  mov     [rsp-8+arg_10], rsi
0x18003054a  push    rbp
0x18003054b  lea     rbp, [rsp-190h]
0x180030553  sub     rsp, 290h
0x18003055a  mov     rax, cs:__security_cookie
0x180030561  xor     rax, rsp
0x180030564  mov     [rbp+190h+var_10], rax
0x18003056b  mov     rsi, rcx
0x18003056e  mov     [rsp+290h+PrincName], 0
0x180030577  mov     ebx, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x18003057d  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180030584  mov     [rsp+290h+var_250], rax
0x180030589  mov     [rsp+290h+var_248], 0
0x180030592  mov     [rsp+290h+var_240], 0
0x18003059a  mov     [rsp+290h+var_238], 0
0x1800305a3  or      eax, 0FFFFFFFFh
0x1800305a6  mov     [rsp+290h+var_230], eax
0x1800305aa  mov     [rsp+290h+var_22C], eax
0x1800305ae  mov     r9d, 20019h; unsigned int
0x1800305b4  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x1800305bb  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800305c2  lea     rcx, [rsp+290h+var_250]; this
0x1800305c7  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800305cc  test    eax, eax
0x1800305ce  jnz     short loc_1800305F7
0x1800305d0  mov     [rsp+290h+var_260], eax
0x1800305d4  lea     r8, [rsp+290h+var_260]; unsigned int *
0x1800305d9  lea     rdx, aFencryptrpctra; "fEncryptRPCTraffic"
0x1800305e0  lea     rcx, [rsp+290h+var_250]; this
0x1800305e5  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x1800305ea  test    eax, eax
0x1800305ec  jnz     short loc_1800305F7
0x1800305ee  cmp     [rsp+290h+var_260], eax
0x1800305f2  setnz   al
0x1800305f5  jmp     short loc_1800305FC
0x1800305f7  mov     eax, 1
0x1800305fc  mov     cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA, eax; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180030602  lea     rcx, [rsp+290h+var_250]; this
0x180030607  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18003060c  cmp     ebx, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180030612  jz      short loc_18003061C
0x180030614  mov     rcx, rsi; this
0x180030617  call    ?Stop@CRCMLegacyRpc@@UEAAJXZ; CRCMLegacyRpc::Stop(void)
0x18003061c  cmp     dword ptr [rsi+638h], 0
0x180030623  jnz     loc_1800307F2
0x180030629  cmp     qword ptr [rsi+6B8h], 0
0x180030631  jnz     loc_1800306C8
0x180030637  mov     r8d, 104h; nSize
0x18003063d  lea     rdx, [rsp+290h+Dst]; lpDst
0x180030642  lea     rcx, Src; "%SystemRoot%\\System32\\winsta.dll"
0x180030649  call    cs:__imp_ExpandEnvironmentStringsW
0x18003064f  test    eax, eax
0x180030651  jnz     short loc_18003067E
0x180030653  call    cs:__imp_GetLastError
0x180030659  mov     ebx, eax
0x18003065b  test    eax, eax
0x18003065d  jle     short loc_180030668
0x18003065f  movzx   ebx, ax
0x180030662  or      ebx, 80070000h
0x180030668  lea     rdx, aExpandenvironm_0; "ExpandEnvironmentStrings failed for win"...
0x18003066f  mov     ecx, 8; int
0x180030674  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030679  jmp     loc_1800307F4
0x18003067e  lea     rcx, [rsp+290h+Dst]; lpLibFileName
0x180030683  call    cs:__imp_LoadLibraryW
0x180030689  mov     [rsi+6B8h], rax
0x180030690  test    rax, rax
0x180030693  jnz     short loc_1800306C8
0x180030695  call    cs:__imp_GetLastError
0x18003069b  mov     ebx, eax
0x18003069d  test    eax, eax
0x18003069f  jle     short loc_1800306AA
0x1800306a1  movzx   ebx, ax
0x1800306a4  or      ebx, 80070000h
0x1800306aa  mov     r9d, ebx
0x1800306ad  lea     r8, [rsp+290h+Dst]
0x1800306b2  lea     rdx, aLoadlibraryWsF; "LoadLibrary( %ws ) failed: 0x%x"
0x1800306b9  mov     ecx, 8; int
0x1800306be  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800306c3  jmp     loc_1800307F4
0x1800306c8  xor     r9d, r9d; SecurityDescriptor
0x1800306cb  lea     r8, aPipeCtxWinstat; "\\pipe\\Ctx_WinStation_API_service"
0x1800306d2  mov     edx, 80h; MaxCalls
0x1800306d7  lea     rcx, Protseq; "ncacn_np"
0x1800306de  call    cs:__imp_RpcServerUseProtseqEpW
0x1800306e4  mov     ebx, eax
0x1800306e6  test    eax, eax
0x1800306e8  jz      short loc_18003071B
0x1800306ea  cmp     eax, 6CCh
0x1800306ef  jz      short loc_18003071B
0x1800306f1  lea     rdx, aErrorDRpcusepr_0; "Error %d RpcUseProtseqEp on ncacn_np"
0x1800306f8  mov     r8d, ebx
0x1800306fb  mov     ecx, 8; int
0x180030700  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030705  test    ebx, ebx
0x180030707  jle     loc_1800307F4
0x18003070d  movzx   ebx, bx
0x180030710  or      ebx, 80070000h
0x180030716  jmp     loc_1800307F4
0x18003071b  lea     rdx, [rsp+290h+PrincName]; PrincName
0x180030720  mov     ecx, 9; AuthnSvc
0x180030725  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18003072b  mov     ebx, eax
0x18003072d  test    eax, eax
0x18003072f  jz      short loc_18003073A
0x180030731  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerInqDefaultPrincName"
0x180030738  jmp     short loc_1800306F8
0x18003073a  xor     r9d, r9d; Arg
0x18003073d  xor     r8d, r8d; GetKeyFn
0x180030740  lea     edx, [r9+9]; AuthnSvc
0x180030744  mov     rcx, [rsp+290h+PrincName]; ServerPrincName
0x180030749  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18003074f  mov     ebx, eax
0x180030751  cmp     [rsp+290h+PrincName], 0
0x180030757  jz      short loc_180030764
0x180030759  lea     rcx, [rsp+290h+PrincName]; String
0x18003075e  call    cs:__imp_RpcStringFreeW
0x180030764  test    ebx, ebx
0x180030766  jz      short loc_180030771
0x180030768  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterAuthInfo"
0x18003076f  jmp     short loc_1800306F8
0x180030771  mov     eax, cs:?fEncryptRPCTraffic@CRCMLegacyRpc@@0HA; int CRCMLegacyRpc::fEncryptRPCTraffic
0x180030777  neg     eax
0x180030779  sbb     r9d, r9d
0x18003077c  and     r9d, 0FFFFFFF8h
0x180030780  add     r9d, 11h; Flags
0x180030784  lea     rax, ?staticRCMLegacyRpcSecurityCallback@CRCMLegacyRpc@@CAJPEAX0@Z; CRCMLegacyRpc::staticRCMLegacyRpcSecurityCallback(void *,void *)
0x18003078b  mov     [rsp+290h+IfCallback], rax; IfCallback
0x180030790  mov     dword ptr [rsp+290h+MaxCalls], 4D2h; MaxCalls
0x180030798  xor     r8d, r8d; MgrEpv
0x18003079b  xor     edx, edx; MgrTypeUuid
0x18003079d  lea     rcx, qword_1800D1CA0; IfSpec
0x1800307a4  call    cs:__imp_RpcServerRegisterIfEx
0x1800307aa  mov     ebx, eax
0x1800307ac  test    eax, eax
0x1800307ae  jz      short loc_1800307BC
0x1800307b0  lea     rdx, aErrorDRpcserve_2; "Error %d RpcServerRegisterIf"
0x1800307b7  jmp     loc_1800306F8
0x1800307bc  mov     edx, 4D2h; MaxCalls
0x1800307c1  mov     ecx, 1; MinimumCallThreads
0x1800307c6  mov     r8d, ecx; DontWait
0x1800307c9  call    cs:__imp_RpcServerListen
0x1800307cf  mov     ebx, eax
0x1800307d1  test    eax, eax
0x1800307d3  jz      short loc_1800307E8
0x1800307d5  cmp     eax, 6B1h
0x1800307da  jz      short loc_1800307E8
0x1800307dc  lea     rdx, aErrorDRpcserve; "Error %d RpcServerListen"
0x1800307e3  jmp     loc_1800306F8
0x1800307e8  mov     dword ptr [rsi+638h], 1
0x1800307f2  xor     ebx, ebx
0x1800307f4  mov     eax, ebx
0x1800307f6  mov     rcx, [rbp+190h+var_10]
0x1800307fd  xor     rcx, rsp; StackCookie
0x180030800  call    __security_check_cookie
0x180030805  lea     r11, [rsp+290h+var_s0]
0x18003080d  mov     rbx, [r11+18h]
0x180030811  mov     rsi, [r11+20h]
0x180030815  mov     rsp, r11
0x180030818  pop     rbp
0x180030819  retn
```
