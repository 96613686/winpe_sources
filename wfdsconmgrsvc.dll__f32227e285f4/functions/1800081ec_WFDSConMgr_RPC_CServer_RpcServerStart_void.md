# WFDSConMgr::RPC::CServer::RpcServerStart(void)

- ea: `0x1800081ec`
- end: `0x18000857f`
- name: `?RpcServerStart@CServer@RPC@WFDSConMgr@@QEAAXXZ`
- size: `915`
- prototype: `void __fastcall(WFDSConMgr::RPC::CServer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005cb4`

## callees

- `0x180006740`
- `0x180006c60`
- `0x180006db8`
- `0x180006e04`
- `0x180006e24`
- `0x1800081ec`
- `0x180008a10`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000826e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000826e`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000835b`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18000835b`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800083d3`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800083d3`
- `RPCRT4!RpcServerInqBindings` at `0x18000844c`
- `RPCRT4!RpcServerInqBindings` at `0x18000844c`
- `RPCRT4!RpcEpRegisterW` at `0x1800084a2`
- `RPCRT4!RpcEpRegisterW` at `0x1800084a2`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000830e`
- `RPCRT4!RpcServerUseProtseqW` at `0x18000830e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008264`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008264`

## string_xrefs

- `0x180008285`: `ConvertStringSecurityDescriptorToSecurityDescriptorW failed`
- `0x1800082cd`: `Attempted to start RPC server multiple times`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CServer::RpcServerStart(WFDSConMgr::RPC::CServer *this)
{
  char LastError; // al
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  int v5; // eax
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  RPC_BINDING_VECTOR *v8; // [rsp+40h] [rbp-30h] BYREF
  WFDSConMgr::RPC::CServer *v9; // [rsp+48h] [rbp-28h] BYREF
  int v10; // [rsp+50h] [rbp-20h]
  _BYTE v11[24]; // [rsp+58h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp+28h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+A0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR v14; // [rsp+A8h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, this);
  }
  BindingVector = 0;
  v8 = 0;
  SecurityDescriptor = 0;
  v14 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      87,
      L"ConvertStringSecurityDescriptorToSecurityDescriptorW failed",
      this);
  }
  v14 = SecurityDescriptor;
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(v11, this);
  if ( *((_BYTE *)this + 26) )
    WFDSConMgr::CException::Throw(
      223,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      95,
      L"Attempted to start RPC server multiple times",
      this);
  v9 = this;
  LOBYTE(v10) = 1;
  v3 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
  if ( v3 )
    WFDSConMgr::CException::Throw(
      v3,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      110,
      L"RpcServerUseProtseqW failed",
      this);
  v4 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
  if ( v4 )
    WFDSConMgr::CException::Throw(
      v4,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      116,
      L"RpcServerRegisterAuthInfoW failed",
      this);
  v5 = RpcServerRegisterIf3(
         qword_180070080,
         0,
         0,
         41,
         1234,
         -1,
         WFDSConMgr::RPC::CServer::RpcSecurityCallback,
         SecurityDescriptor,
         v8,
         v9,
         v10);
  if ( v5 )
    WFDSConMgr::CException::Throw(
      v5,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      135,
      L"RpcServerRegisterIf3 failed",
      this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, this);
  }
  *((_BYTE *)this + 24) = 1;
  v6 = RpcServerInqBindings(&BindingVector);
  if ( v6 )
    WFDSConMgr::CException::Throw(
      v6,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      145,
      L"RpcServerInqBindings failed",
      this);
  v8 = BindingVector;
  v7 = RpcEpRegisterW(qword_180070080, BindingVector, 0, 0);
  if ( v7 )
    WFDSConMgr::CException::Throw(
      v7,
      "WFDSConMgr::RPC::CServer::RpcServerStart",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
      154,
      L"RpcEpRegisterW failed",
      this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, this);
  }
  *((_BYTE *)this + 25) = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, this);
  }
  *((_BYTE *)this + 26) = 1;
  LOBYTE(v10) = 0;
  WFDSConMgr::RPC::CRpcServerShutdownGuard::~CRpcServerShutdownGuard((WFDSConMgr::RPC::CRpcServerShutdownGuard *)&v9);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v11);
  std::unique_ptr<void,WFDSConMgr::RPC::LocalFreeDeleter>::~unique_ptr<void,WFDSConMgr::RPC::LocalFreeDeleter>(&v14);
  std::unique_ptr<_RPC_BINDING_VECTOR,WFDSConMgr::RPC::RPCBindingVectorFreeDeleter>::~unique_ptr<_RPC_BINDING_VECTOR,WFDSConMgr::RPC::RPCBindingVectorFreeDeleter>(&v8);
}

```

## disassembly

```asm
0x1800081ec  push    rbp
0x1800081ee  push    rbx
0x1800081ef  push    r15
0x1800081f1  mov     rbp, rsp
0x1800081f4  sub     rsp, 70h
0x1800081f8  mov     rbx, rcx
0x1800081fb  lea     r15, WPP_GLOBAL_Control
0x180008202  mov     rcx, cs:WPP_GLOBAL_Control
0x180008209  cmp     rcx, r15
0x18000820c  jz      short loc_180008232
0x18000820e  cmp     byte ptr [rcx+19h], 4
0x180008212  jb      short loc_180008232
0x180008214  test    byte ptr [rcx+1Ch], 1
0x180008218  jz      short loc_180008232
0x18000821a  mov     edx, 17h
0x18000821f  mov     r9, rbx
0x180008222  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x180008229  mov     rcx, [rcx+10h]
0x18000822d  call    WPP_SF_q
0x180008232  mov     [rbp+BindingVector], 0
0x18000823a  mov     [rbp+var_30], 0
0x180008242  mov     [rbp+SecurityDescriptor], 0
0x18000824a  mov     [rbp+arg_18], 0
0x180008252  xor     r9d, r9d; SecurityDescriptorSize
0x180008255  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180008259  lea     edx, [r9+1]; StringSDRevision
0x18000825d  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180008264  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000826a  test    eax, eax
0x18000826c  jnz     short loc_1800082AD
0x18000826e  call    cs:__imp_GetLastError
0x180008274  test    eax, eax
0x180008276  jle     short loc_180008280
0x180008278  movzx   eax, ax
0x18000827b  or      eax, 80070000h
0x180008280  mov     [rsp+70h+var_48], rbx; void *
0x180008285  lea     rcx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x18000828c  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x180008291  mov     r9d, 157h; char
0x180008297  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x18000829e  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x1800082a5  mov     ecx, eax; char
0x1800082a7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800082ad  mov     rax, [rbp+SecurityDescriptor]
0x1800082b1  mov     [rbp+arg_18], rax
0x1800082b5  mov     rdx, rbx
0x1800082b8  lea     rcx, [rbp+var_18]
0x1800082bc  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x1800082c1  nop
0x1800082c2  cmp     byte ptr [rbx+1Ah], 0
0x1800082c6  jz      short loc_1800082F8
0x1800082c8  mov     [rsp+70h+var_48], rbx; void *
0x1800082cd  lea     rax, aAttemptedToSta; "Attempted to start RPC server multiple "...
0x1800082d4  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x1800082d9  mov     r9d, 15Fh; char
0x1800082df  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x1800082e6  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x1800082ed  mov     ecx, 800704DFh; char
0x1800082f2  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800082f8  mov     [rbp+var_28], rbx
0x1800082fc  mov     byte ptr [rbp+var_20], 1
0x180008300  xor     r8d, r8d; SecurityDescriptor
0x180008303  lea     edx, [r8+0Ah]; MaxCalls
0x180008307  lea     rcx, Protseq; "ncalrpc"
0x18000830e  call    cs:__imp_RpcServerUseProtseqW
0x180008314  test    eax, eax
0x180008316  jz      short loc_18000834F
0x180008318  jle     short loc_180008322
0x18000831a  movzx   eax, ax
0x18000831d  or      eax, 80070000h
0x180008322  mov     [rsp+70h+var_48], rbx; void *
0x180008327  lea     rcx, aRpcserverusepr; "RpcServerUseProtseqW failed"
0x18000832e  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x180008333  mov     r9d, 16Eh; char
0x180008339  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180008340  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x180008347  mov     ecx, eax; char
0x180008349  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18000834f  xor     r9d, r9d; Arg
0x180008352  xor     r8d, r8d; GetKeyFn
0x180008355  lea     edx, [r9+9]; AuthnSvc
0x180008359  xor     ecx, ecx; ServerPrincName
0x18000835b  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180008361  test    eax, eax
0x180008363  jz      short loc_18000839C
0x180008365  jle     short loc_18000836F
0x180008367  movzx   eax, ax
0x18000836a  or      eax, 80070000h
0x18000836f  mov     [rsp+70h+var_48], rbx; void *
0x180008374  lea     rcx, aRpcserverregis; "RpcServerRegisterAuthInfoW failed"
0x18000837b  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x180008380  mov     r9d, 174h; char
0x180008386  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x18000838d  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x180008394  mov     ecx, eax; char
0x180008396  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18000839c  mov     rax, [rbp+SecurityDescriptor]
0x1800083a0  mov     [rsp+70h+var_38], rax
0x1800083a5  lea     rax, ?RpcSecurityCallback@CServer@RPC@WFDSConMgr@@CAJPEAX0@Z; WFDSConMgr::RPC::CServer::RpcSecurityCallback(void *,void *)
0x1800083ac  mov     [rsp+70h+var_40], rax
0x1800083b1  mov     dword ptr [rsp+70h+var_48], 0FFFFFFFFh
0x1800083b9  mov     dword ptr [rsp+70h+var_50], 4D2h
0x1800083c1  mov     r9d, 29h ; ')'
0x1800083c7  xor     r8d, r8d
0x1800083ca  xor     edx, edx
0x1800083cc  lea     rcx, qword_180070080
0x1800083d3  call    cs:__imp_RpcServerRegisterIf3
0x1800083d9  test    eax, eax
0x1800083db  jz      short loc_180008414
0x1800083dd  jle     short loc_1800083E7
0x1800083df  movzx   eax, ax
0x1800083e2  or      eax, 80070000h
0x1800083e7  mov     [rsp+70h+var_48], rbx; void *
0x1800083ec  lea     rcx, aRpcserverregis_0; "RpcServerRegisterIf3 failed"
0x1800083f3  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800083f8  mov     r9d, 187h; char
0x1800083fe  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180008405  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x18000840c  mov     ecx, eax; char
0x18000840e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180008414  mov     rcx, cs:WPP_GLOBAL_Control
0x18000841b  cmp     rcx, r15
0x18000841e  jz      short loc_180008444
0x180008420  cmp     byte ptr [rcx+19h], 4
0x180008424  jb      short loc_180008444
0x180008426  test    byte ptr [rcx+1Ch], 1
0x18000842a  jz      short loc_180008444
0x18000842c  mov     edx, 18h
0x180008431  mov     r9, rbx
0x180008434  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x18000843b  mov     rcx, [rcx+10h]
0x18000843f  call    WPP_SF_q
0x180008444  mov     byte ptr [rbx+18h], 1
0x180008448  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000844c  call    cs:__imp_RpcServerInqBindings
0x180008452  test    eax, eax
0x180008454  jz      short loc_18000848D
0x180008456  jle     short loc_180008460
0x180008458  movzx   eax, ax
0x18000845b  or      eax, 80070000h
0x180008460  mov     [rsp+70h+var_48], rbx; void *
0x180008465  lea     rcx, aRpcserverinqbi; "RpcServerInqBindings failed"
0x18000846c  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x180008471  mov     r9d, 191h; char
0x180008477  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x18000847e  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x180008485  mov     ecx, eax; char
0x180008487  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18000848d  mov     rdx, [rbp+BindingVector]; BindingVector
0x180008491  mov     [rbp+var_30], rdx
0x180008495  xor     r9d, r9d; Annotation
0x180008498  xor     r8d, r8d; UuidVector
0x18000849b  lea     rcx, qword_180070080; IfSpec
0x1800084a2  call    cs:__imp_RpcEpRegisterW
0x1800084a8  test    eax, eax
0x1800084aa  jz      short loc_1800084E3
0x1800084ac  jle     short loc_1800084B6
0x1800084ae  movzx   eax, ax
0x1800084b1  or      eax, 80070000h
0x1800084b6  mov     [rsp+70h+var_48], rbx; void *
0x1800084bb  lea     rcx, aRpcepregisterw; "RpcEpRegisterW failed"
0x1800084c2  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800084c7  mov     r9d, 19Ah; char
0x1800084cd  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x1800084d4  lea     rdx, aWfdsconmgrRpcC_4; "WFDSConMgr::RPC::CServer::RpcServerStar"...
0x1800084db  mov     ecx, eax; char
0x1800084dd  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800084e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ea  cmp     rcx, r15
0x1800084ed  jz      short loc_180008513
0x1800084ef  cmp     byte ptr [rcx+19h], 4
0x1800084f3  jb      short loc_180008513
0x1800084f5  test    byte ptr [rcx+1Ch], 1
0x1800084f9  jz      short loc_180008513
0x1800084fb  mov     edx, 19h
0x180008500  mov     r9, rbx
0x180008503  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x18000850a  mov     rcx, [rcx+10h]
0x18000850e  call    WPP_SF_q
0x180008513  mov     byte ptr [rbx+19h], 1
0x180008517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000851e  cmp     rcx, r15
0x180008521  jz      short loc_180008547
0x180008523  cmp     byte ptr [rcx+19h], 4
0x180008527  jb      short loc_180008547
0x180008529  test    byte ptr [rcx+1Ch], 1
0x18000852d  jz      short loc_180008547
0x18000852f  mov     edx, 1Ah
0x180008534  mov     r9, rbx
0x180008537  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x18000853e  mov     rcx, [rcx+10h]
0x180008542  call    WPP_SF_q
0x180008547  mov     byte ptr [rbx+1Ah], 1
0x18000854b  mov     byte ptr [rbp+var_20], 0
0x18000854f  lea     rcx, [rbp+var_28]; this
0x180008553  call    ??1CRpcServerShutdownGuard@RPC@WFDSConMgr@@QEAA@XZ; WFDSConMgr::RPC::CRpcServerShutdownGuard::~CRpcServerShutdownGuard(void)
0x180008558  nop
0x180008559  lea     rcx, [rbp+var_18]
0x18000855d  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x180008562  nop
0x180008563  lea     rcx, [rbp+arg_18]
0x180008567  call    ??1?$unique_ptr@XULocalFreeDeleter@RPC@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<void,WFDSConMgr::RPC::LocalFreeDeleter>::~unique_ptr<void,WFDSConMgr::RPC::LocalFreeDeleter>(void)
0x18000856c  nop
0x18000856d  lea     rcx, [rbp+var_30]
0x180008571  call    ??1?$unique_ptr@U_RPC_BINDING_VECTOR@@URPCBindingVectorFreeDeleter@RPC@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<_RPC_BINDING_VECTOR,WFDSConMgr::RPC::RPCBindingVectorFreeDeleter>::~unique_ptr<_RPC_BINDING_VECTOR,WFDSConMgr::RPC::RPCBindingVectorFreeDeleter>(void)
0x180008576  add     rsp, 70h
0x18000857a  pop     r15
0x18000857c  pop     rbx
0x18000857d  pop     rbp
0x18000857e  retn
```
