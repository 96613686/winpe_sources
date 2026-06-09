# TLoad64BitDllsMgr::StartLdrRPCServer(ulong)

- ea: `0x14000805c`
- end: `0x1400082b8`
- name: `?StartLdrRPCServer@TLoad64BitDllsMgr@@IEAAKK@Z`
- size: `604`
- prototype: `unsigned int(TLoad64BitDllsMgr *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140007dac`

## callees

- `0x140001b90`
- `0x140001ee0`
- `0x140005f18`
- `0x14000805c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000f9cc`
- `0x14001293c`
- `0x140012a20`
- `0x140012a9c`
- `0x140012bf8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140008087`
- `KERNEL32!GetCurrentProcessId` at `0x140008087`
- `KERNEL32!LocalFree` at `0x140008255`
- `KERNEL32!LocalFree` at `0x140008255`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14000818c`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x14000818c`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1400081d6`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1400081d6`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1400081e9`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1400081e9`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x140008220`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x140008220`

## string_xrefs

- `0x1400081ef`: `TLoad64BitDllsMgr::StartLdrRPCServer`
- `0x140008246`: `TLoad64BitDllsMgr::StartLdrRPCServer`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::StartLdrRPCServer(TLoad64BitDllsMgr *this, unsigned int a2)
{
  int AuthenticationIdAndIntegrity; // ebx
  unsigned int v5; // edi
  unsigned int v6; // ecx
  HLOCAL v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  struct _LUID v13; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v16[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[64]; // [rsp+A0h] [rbp-60h] BYREF

  GetCurrentProcessId();
  v13 = 0;
  Block = &NCoreLibrary::TString::gszNullState;
  v12 = 0;
  NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v16);
  hMem = 0;
  AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
                                   (NSecurityLibrary::TSidUserContext *)v16,
                                   &v13,
                                   &v12);
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_18;
  AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetSidAsString(
                                   (NSecurityLibrary::TSidUserContext *)v16,
                                   (struct NCoreLibrary::TString *)&Block);
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_18;
  v5 = v12;
  v6 = v12;
  if ( a2 < v12 )
    v6 = a2;
  AuthenticationIdAndIntegrity = SplWOWCreateSecurityDescriptor(v6, (struct NCoreLibrary::TString *)&Block, 1, &hMem);
  if ( AuthenticationIdAndIntegrity < 0 )
  {
LABEL_18:
    if ( (AuthenticationIdAndIntegrity & 0x1FFF0000) == 0x70000 )
      AuthenticationIdAndIntegrity = (unsigned __int16)AuthenticationIdAndIntegrity;
  }
  else
  {
    if ( a2 < v5 )
      v5 = a2;
    if ( v5 < 0x2000 )
      v5 = 0x2000;
    StringCchPrintfW(v17, 0x3Cu, L"%s_%x_%x_%x_%x", L"splwow64", *((_DWORD *)this + 14), v13.LowPart, v13.HighPart, v5);
    v7 = hMem;
    qword_140021090 = (__int64)v17;
    qword_140021098 = (__int64)hMem;
    qword_140021148 = (__int64)hMem;
    v8 = RpcServerRegisterAuthInfoW(0, 0xAu, 0, 0);
    AuthenticationIdAndIntegrity = v8;
    if ( v8 )
    {
      SplWow64Telemetry::WriteDbgTraceError(
        "TLoad64BitDllsMgr::StartLdrRPCServer",
        L"Register AuthInfo failed.  Error %d",
        v8);
    }
    else
    {
      v9 = RpcServerInterfaceGroupCreateW(&TLoad64BitDllsMgr::m_rpcInterface, 1, &TLoad64BitDllsMgr::m_rpcEndpoint);
      AuthenticationIdAndIntegrity = v9;
      if ( v9 )
      {
        SplWow64Telemetry::WriteDbgTraceError(
          "TLoad64BitDllsMgr::StartLdrRPCServer",
          L"Creation of InterfaceGroup failed.  Error %d",
          v9);
      }
      else
      {
        v10 = RpcServerInterfaceGroupActivate(TLoad64BitDllsMgr::m_interfaceGroup);
        AuthenticationIdAndIntegrity = v10;
        if ( v10 )
        {
          SplWow64Telemetry::WriteDbgTraceError(
            "TLoad64BitDllsMgr::StartLdrRPCServer",
            L"Activation of InterfaceGroup failed.  Error %d",
            v10);
          RpcServerInterfaceGroupClose(TLoad64BitDllsMgr::m_interfaceGroup);
          TLoad64BitDllsMgr::m_interfaceGroup = 0;
        }
        else
        {
          SplWow64Telemetry::WriteDbgTraceInfo(
            "TLoad64BitDllsMgr::StartLdrRPCServer",
            L"Activation of InterfaceGroup succeeded.");
        }
      }
    }
    LocalFree(v7);
  }
  NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v16);
  if ( Block != &NCoreLibrary::TString::gszNullState && Block != word_14002174A )
    operator delete(Block);
  return (unsigned int)AuthenticationIdAndIntegrity;
}

```

## disassembly

```asm
0x14000805c  mov     [rsp-8+arg_10], rbx
0x140008061  push    rbp
0x140008062  push    rsi
0x140008063  push    rdi
0x140008064  push    r13
0x140008066  push    r14
0x140008068  lea     rbp, [rsp-30h]
0x14000806d  sub     rsp, 130h
0x140008074  mov     rax, cs:__security_cookie
0x14000807b  xor     rax, rsp
0x14000807e  mov     [rbp+50h+var_30], rax
0x140008082  mov     esi, edx
0x140008084  mov     r14, rcx
0x140008087  call    cs:__imp_GetCurrentProcessId
0x14000808d  lea     r13, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x140008094  mov     qword ptr [rsp+150h+var_108.LowPart], 0
0x14000809d  lea     rcx, [rsp+150h+var_F0]; this
0x1400080a2  mov     [rsp+150h+Block], r13
0x1400080a7  mov     [rsp+150h+var_110], 0
0x1400080af  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x1400080b4  lea     r8, [rsp+150h+var_110]; unsigned int *
0x1400080b9  mov     [rsp+150h+hMem], 0
0x1400080c2  lea     rdx, [rsp+150h+var_108]; struct _LUID *
0x1400080c7  lea     rcx, [rsp+150h+var_F0]; this
0x1400080cc  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x1400080d1  mov     ebx, eax
0x1400080d3  test    eax, eax
0x1400080d5  js      loc_14000825D
0x1400080db  lea     rdx, [rsp+150h+Block]; struct NCoreLibrary::TString *
0x1400080e0  lea     rcx, [rsp+150h+var_F0]; this
0x1400080e5  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x1400080ea  mov     ebx, eax
0x1400080ec  test    eax, eax
0x1400080ee  js      loc_14000825D
0x1400080f4  mov     edi, [rsp+150h+var_110]
0x1400080f8  lea     r9, [rsp+150h+hMem]; void **
0x1400080fd  mov     ecx, edi
0x1400080ff  lea     rdx, [rsp+150h+Block]; struct NCoreLibrary::TString *
0x140008104  cmp     esi, edi
0x140008106  mov     r8b, 1; bool
0x140008109  cmovb   ecx, esi; unsigned int
0x14000810c  call    ?SplWOWCreateSecurityDescriptor@@YAJKAEAVTString@NCoreLibrary@@_NPEAPEAX@Z; SplWOWCreateSecurityDescriptor(ulong,NCoreLibrary::TString &,bool,void * *)
0x140008111  mov     ebx, eax
0x140008113  test    eax, eax
0x140008115  js      loc_14000825D
0x14000811b  mov     eax, 2000h
0x140008120  lea     r9, aSplwow64; "splwow64"
0x140008127  cmp     esi, edi
0x140008129  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x140008130  mov     edx, 3Ch ; '<'; unsigned __int64
0x140008135  lea     rcx, [rbp+50h+var_B0]; unsigned __int16 *
0x140008139  cmovb   edi, esi
0x14000813c  cmp     edi, eax
0x14000813e  cmovb   edi, eax
0x140008141  mov     eax, [rsp+150h+var_108.HighPart]
0x140008145  mov     dword ptr [rsp+150h+var_118], edi
0x140008149  mov     dword ptr [rsp+150h+var_120], eax
0x14000814d  mov     eax, [rsp+150h+var_108.LowPart]
0x140008151  mov     dword ptr [rsp+150h+var_128], eax
0x140008155  mov     eax, [r14+38h]
0x140008159  mov     [rsp+150h+var_130], eax
0x14000815d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008162  mov     rdi, [rsp+150h+hMem]
0x140008167  lea     rax, [rbp+50h+var_B0]
0x14000816b  xor     r9d, r9d; Arg
0x14000816e  mov     cs:qword_140021090, rax
0x140008175  xor     r8d, r8d; GetKeyFn
0x140008178  mov     cs:qword_140021098, rdi
0x14000817f  xor     ecx, ecx; ServerPrincName
0x140008181  mov     cs:qword_140021148, rdi
0x140008188  lea     edx, [r9+0Ah]; AuthnSvc
0x14000818c  call    cs:__imp_RpcServerRegisterAuthInfoW
0x140008192  mov     ebx, eax
0x140008194  test    eax, eax
0x140008196  jnz     loc_14000823C
0x14000819c  lea     rax, ?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA; void * TLoad64BitDllsMgr::m_interfaceGroup
0x1400081a3  mov     [rsp+150h+var_118], rax
0x1400081a8  lea     r9d, [rbx+1]
0x1400081ac  lea     rax, ?IdleCallback@IdleHandler@@SAXPEAX0K@Z; IdleHandler::IdleCallback(void *,void *,ulong)
0x1400081b3  mov     [rsp+150h+var_120], r14
0x1400081b8  mov     [rsp+150h+var_128], rax
0x1400081bd  lea     r8, ?m_rpcEndpoint@TLoad64BitDllsMgr@@0URPC_ENDPOINT_TEMPLATEW@@A; RPC_ENDPOINT_TEMPLATEW TLoad64BitDllsMgr::m_rpcEndpoint
0x1400081c4  mov     edx, r9d
0x1400081c7  mov     [rsp+150h+var_130], 78h ; 'x'
0x1400081cf  lea     rcx, ?m_rpcInterface@TLoad64BitDllsMgr@@0URPC_INTERFACE_TEMPLATEW@@A; RPC_INTERFACE_TEMPLATEW TLoad64BitDllsMgr::m_rpcInterface
0x1400081d6  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x1400081dc  mov     ebx, eax
0x1400081de  test    eax, eax
0x1400081e0  jnz     short loc_140008233
0x1400081e2  mov     rcx, cs:?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA; void * TLoad64BitDllsMgr::m_interfaceGroup
0x1400081e9  call    cs:__imp_RpcServerInterfaceGroupActivate
0x1400081ef  lea     rcx, aTload64bitdlls_5; "TLoad64BitDllsMgr::StartLdrRPCServer"
0x1400081f6  mov     ebx, eax
0x1400081f8  test    eax, eax
0x1400081fa  jnz     short loc_14000820A
0x1400081fc  lea     rdx, aActivationOfIn; "Activation of InterfaceGroup succeeded."
0x140008203  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140008208  jmp     short loc_140008252
0x14000820a  mov     r8d, eax
0x14000820d  lea     rdx, aActivationOfIn_0; "Activation of InterfaceGroup failed.  E"...
0x140008214  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140008219  mov     rcx, cs:?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA; void * TLoad64BitDllsMgr::m_interfaceGroup
0x140008220  call    cs:__imp_RpcServerInterfaceGroupClose
0x140008226  mov     cs:?m_interfaceGroup@TLoad64BitDllsMgr@@0PEAXEA, 0; void * TLoad64BitDllsMgr::m_interfaceGroup
0x140008231  jmp     short loc_140008252
0x140008233  lea     rdx, aCreationOfInte; "Creation of InterfaceGroup failed.  Err"...
0x14000823a  jmp     short loc_140008243
0x14000823c  lea     rdx, aRegisterAuthin; "Register AuthInfo failed.  Error %d"
0x140008243  mov     r8d, eax
0x140008246  lea     rcx, aTload64bitdlls_5; "TLoad64BitDllsMgr::StartLdrRPCServer"
0x14000824d  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140008252  mov     rcx, rdi; hMem
0x140008255  call    cs:__imp_LocalFree
0x14000825b  jmp     short loc_14000826E
0x14000825d  mov     eax, ebx
0x14000825f  and     eax, 1FFF0000h
0x140008264  cmp     eax, 70000h
0x140008269  jnz     short loc_14000826E
0x14000826b  movzx   ebx, bx
0x14000826e  lea     rcx, [rsp+150h+var_F0]; this
0x140008273  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140008278  mov     rcx, [rsp+150h+Block]; Block
0x14000827d  cmp     rcx, r13
0x140008280  jz      short loc_140008293
0x140008282  lea     rax, word_14002174A
0x140008289  cmp     rcx, rax
0x14000828c  jz      short loc_140008293
0x14000828e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008293  mov     eax, ebx
0x140008295  mov     rcx, [rbp+50h+var_30]
0x140008299  xor     rcx, rsp; StackCookie
0x14000829c  call    __security_check_cookie
0x1400082a1  mov     rbx, [rsp+150h+arg_10]
0x1400082a9  add     rsp, 130h
0x1400082b0  pop     r14
0x1400082b2  pop     r13
0x1400082b4  pop     rdi
0x1400082b5  pop     rsi
0x1400082b6  pop     rbp
0x1400082b7  retn
```
