# StartRpcServerListen(void)

- ea: `0x18002ba94`
- end: `0x18002be95`
- name: `?StartRpcServerListen@@YAJXZ`
- size: `1025`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b438`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002b5b0`
- `0x18002ba94`
- `0x18002de18`
- `0x18002def8`
- `0x18004f008`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002be6c`
- `KERNEL32!HeapFree` at `0x18002be6c`
- `KERNEL32!LocalFree` at `0x18002be4f`
- `KERNEL32!LocalFree` at `0x18002be4f`
- `KERNEL32!GetProcessHeap` at `0x18002be5d`
- `KERNEL32!GetProcessHeap` at `0x18002be5d`
- `KERNEL32!CreateEventW` at `0x18002bdd1`
- `KERNEL32!CreateEventW` at `0x18002bdd1`
- `KERNEL32!GetLastError` at `0x18002bd88`
- `KERNEL32!GetLastError` at `0x18002bdb2`
- `KERNEL32!GetLastError` at `0x18002bdf0`
- `KERNEL32!GetLastError` at `0x18002be1a`
- `KERNEL32!GetLastError` at `0x18002be3e`
- `KERNEL32!GetLastError` at `0x18002bd88`
- `KERNEL32!GetLastError` at `0x18002bdb2`
- `KERNEL32!GetLastError` at `0x18002bdf0`
- `KERNEL32!GetLastError` at `0x18002be1a`
- `KERNEL32!GetLastError` at `0x18002be3e`
- `RPCRT4!RpcServerListen` at `0x18002bd11`
- `RPCRT4!RpcServerListen` at `0x18002bd11`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002bb8a`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18002bb8a`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002bc23`
- `RPCRT4!RpcServerRegisterIf3` at `0x18002bc23`
- `RPCRT4!RpcStringFreeW` at `0x18002bccd`
- `RPCRT4!RpcStringFreeW` at `0x18002bccd`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18002bc72`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x18002bc72`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002bcba`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x18002bcba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002bde6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002bde6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002bb6d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002bb6d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002bb5a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002bb5a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002bd7e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002bd7e`

## string_xrefs

- `0x18002bb07`: `StartRpcServerListen: PrepareStiAcl() returned RpcStatus=0x%X`
- `0x18002bb2b`: `StartRpcServerListen: PrepareStiAcl() returned RpcStatus=0x%X`
- `0x18002bd90`: `StartRpcServerListen failed to produce event security descriptor (Error %d)`
- `0x18002bdb8`: `StartRpcServerListen failed to produce event security descriptor (Error %d)`
- `0x18002bdc1`: `Global\WiaServiceStarted`

## pseudocode

```c
__int64 StartRpcServerListen(void)
{
  struct tagWiaTraceData_Type *v0; // rax
  char *v1; // rdx
  unsigned int v2; // r8d
  unsigned int v3; // edi
  char *v4; // rbx
  void *v5; // rdx
  void *v6; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rdx
  char *v10; // rbx
  void *v11; // rdx
  void *v12; // rax
  int v13; // edx
  int v14; // ecx
  char *v15; // rbx
  void *v16; // rdx
  char *v17; // rbx
  void *v18; // rdx
  char *v19; // rbx
  void *v20; // rdx
  __int64 v21; // rdx
  char *v22; // rbx
  void *v23; // rdx
  void *v24; // rax
  int v25; // edx
  int v26; // ecx
  char *v27; // rbx
  void *v28; // rdx
  DWORD v29; // eax
  void *v30; // rax
  int v31; // edx
  int v32; // ecx
  HANDLE v33; // rax
  char *v34; // rbx
  void *v35; // rdx
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax
  unsigned int lpMem; // [rsp+20h] [rbp-69h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+40h] [rbp-49h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v42; // [rsp+78h] [rbp-11h]
  _BYTE v43[80]; // [rsp+80h] [rbp-9h] BYREF
  RPC_WSTR PrincName; // [rsp+F0h] [rbp+67h] BYREF
  PACL pDacl; // [rsp+F8h] [rbp+6Fh] BYREF

  v0 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("StartRpcServerListen");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v43, v1, v2, "StartRpcServerListen", lpMem, v0);
  *(_QWORD *)&EventAttributes.nLength = 24;
  v42 = 0;
  EventAttributes.lpSecurityDescriptor = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  pDacl = 0;
  v3 = PrepareStiAcl(&pDacl);
  if ( !pDacl )
  {
    v4 = (char *)WiaTrace_TraceLog("StartRpcServerListen: PrepareStiAcl() returned RpcStatus=0x%X");
    WriteDbgTraceErrorWI("StartRpcServerListen", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    v6 = (void *)WiaTrace_Trace("StartRpcServerListen: PrepareStiAcl() returned RpcStatus=0x%X", v3);
    WiaTrace_ProcessTrace_Ex(v8, v7, (int)"StartRpcServerListen", 1, v6);
    goto LABEL_25;
  }
  InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0);
  v3 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x4D2u, (RPC_WSTR)L"STI_LRPC", pSecurityDescriptor);
  if ( v3 )
  {
    v10 = (char *)WiaTrace_TraceLog("StartRpcServerListen: RpcServerUseProtseqEp returned RpcStatus=0x%X");
    WriteDbgTraceErrorWI("StartRpcServerListen", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void *)WiaTrace_Trace("StartRpcServerListen: RpcServerUseProtseqEp returned RpcStatus=0x%X", v3);
  }
  else
  {
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
      v9);
    v3 = RpcServerRegisterIf3(
           qword_18007B370,
           0,
           0,
           8,
           1234,
           -1,
           StiRpcSecurityCallBack,
           pSecurityDescriptor,
           *(_QWORD *)&EventAttributes.nLength);
    if ( v3 )
    {
      v15 = (char *)WiaTrace_TraceLog("StartRpcServerListen: RpcServerRegisterIf returned RpcStatus=0x%X");
      WriteDbgTraceErrorWI("StartRpcServerListen", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v12 = (void *)WiaTrace_Trace("StartRpcServerListen: RpcServerRegisterIf returned RpcStatus=0x%X", v3);
    }
    else
    {
      PrincName = 0;
      v3 = RpcServerInqDefaultPrincNameW(0xAu, &PrincName);
      if ( v3 )
      {
        v17 = (char *)WiaTrace_TraceLog("RpcServerInqDefaultPrincName returned RpcStatus=0x%X");
        WriteDbgTraceErrorWI("StartRpcServerListen", v17);
        WiaTrcLib::Free((WiaTrcLib *)v17, v18);
        v12 = (void *)WiaTrace_Trace("RpcServerInqDefaultPrincName returned RpcStatus=0x%X", v3);
      }
      else
      {
        v3 = RpcServerRegisterAuthInfoW(PrincName, 0xAu, 0, 0);
        if ( PrincName )
          RpcStringFreeW(&PrincName);
        if ( !v3 )
        {
          v3 = RpcServerListen(1u, 0x4D2u, 1u);
          if ( v3 )
          {
            v22 = (char *)WiaTrace_TraceLog("StartRpcServerListen: RpcServerListen returned RpcStatus=0x%X");
            WriteDbgTraceErrorWI("StartRpcServerListen", v22);
            WiaTrcLib::Free((WiaTrcLib *)v22, v23);
            v24 = (void *)WiaTrace_Trace("StartRpcServerListen: RpcServerListen returned RpcStatus=0x%X", v3);
            WiaTrace_ProcessTrace_Ex(v26, v25, (int)"StartRpcServerListen", 1, v24);
          }
          LOBYTE(v21) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl'::`2'::impl,
            v21);
          if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                 L"D:(A;;0x1f0003;;;SY)(A;;0x1f0003;;;LS)(A;;0x1f0003;;;AU)(A;;0x1f0003;;;IU)(A;;0x1f0003;;;LA)(A;;0x1f000"
                  "3;;;S-1-15-3-65536-3835542226-3421776687-588827804-1234363463-3384265473-2476176233-4149357980-1501605488)",
                 1u,
                 &EventAttributes.lpSecurityDescriptor,
                 0)
            && (v33 = CreateEventW(&EventAttributes, 0, 0, L"Global\\WiaServiceStarted"),
                (g_hWiaServiceStarted = v33) != 0) )
          {
            if ( SetEvent(v33) )
              goto LABEL_22;
            GetLastError();
            v34 = (char *)WiaTrace_TraceLog("StartRpcServerListen failed to set event (Error %d)");
            WriteDbgTraceErrorWI("StartRpcServerListen", v34);
            WiaTrcLib::Free((WiaTrcLib *)v34, v35);
            LastError = GetLastError();
            v30 = (void *)WiaTrace_Trace("StartRpcServerListen failed to set event (Error %d)", LastError);
          }
          else
          {
            GetLastError();
            v27 = (char *)WiaTrace_TraceLog("StartRpcServerListen failed to produce event security descriptor (Error %d)");
            WriteDbgTraceErrorWI("StartRpcServerListen", v27);
            WiaTrcLib::Free((WiaTrcLib *)v27, v28);
            v29 = GetLastError();
            v30 = (void *)WiaTrace_Trace(
                            "StartRpcServerListen failed to produce event security descriptor (Error %d)",
                            v29);
          }
          WiaTrace_ProcessTrace_Ex(v32, v31, (int)"StartRpcServerListen", 1, v30);
          v3 = GetLastError();
          goto LABEL_22;
        }
        v19 = (char *)WiaTrace_TraceLog("RpcServerRegisterAuthInfo returned RpcStatus=0x%X");
        WriteDbgTraceErrorWI("StartRpcServerListen", v19);
        WiaTrcLib::Free((WiaTrcLib *)v19, v20);
        v12 = (void *)WiaTrace_Trace("RpcServerRegisterAuthInfo returned RpcStatus=0x%X", v3);
      }
    }
  }
  WiaTrace_ProcessTrace_Ex(v14, v13, (int)"StartRpcServerListen", 1, v12);
LABEL_22:
  if ( EventAttributes.lpSecurityDescriptor )
  {
    LocalFree(EventAttributes.lpSecurityDescriptor);
    EventAttributes.lpSecurityDescriptor = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, pDacl);
LABEL_25:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v43);
  return v3;
}

```

## disassembly

```asm
0x18002ba94  mov     [rsp-8+arg_10], rbx
0x18002ba99  mov     [rsp-8+arg_18], rsi
0x18002ba9e  push    rbp
0x18002ba9f  push    rdi
0x18002baa0  push    r12
0x18002baa2  lea     rbp, [rsp-47h]
0x18002baa7  sub     rsp, 0D0h
0x18002baae  lea     r12, aStartrpcserver_5; "StartRpcServerListen"
0x18002bab5  mov     rcx, r12
0x18002bab8  call    WiaTrace_Trace
0x18002babd  mov     r9, r12; char *
0x18002bac0  mov     [rsp+0E0h+var_B8], rax; struct tagWiaTraceData_Type *
0x18002bac5  lea     rcx, [rbp+57h+var_60]; this
0x18002bac9  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002bace  xor     eax, eax
0x18002bad0  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x18002bad8  xorps   xmm0, xmm0
0x18002badb  mov     [rbp+57h+var_68], rax
0x18002badf  lea     rcx, [rbp+57h+pDacl]; struct _ACL **
0x18002bae3  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x18002bae7  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18002baeb  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x18002baef  movups  [rbp+57h+var_78], xmm0
0x18002baf3  mov     [rbp+57h+pDacl], rax
0x18002baf7  call    ?PrepareStiAcl@@YAJPEAPEAU_ACL@@@Z; PrepareStiAcl(_ACL * *)
0x18002bafc  cmp     [rbp+57h+pDacl], 0
0x18002bb01  mov     edi, eax
0x18002bb03  jnz     short loc_18002BB4F
0x18002bb05  mov     edx, eax
0x18002bb07  lea     rcx, aStartrpcserver_0; "StartRpcServerListen: PrepareStiAcl() r"...
0x18002bb0e  call    WiaTrace_TraceLog
0x18002bb13  mov     rdx, rax; char *
0x18002bb16  mov     rcx, r12; char *
0x18002bb19  mov     rbx, rax
0x18002bb1c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bb21  mov     rcx, rbx; this
0x18002bb24  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bb29  mov     edx, edi
0x18002bb2b  lea     rcx, aStartrpcserver_0; "StartRpcServerListen: PrepareStiAcl() r"...
0x18002bb32  call    WiaTrace_Trace
0x18002bb37  mov     r9d, 1; int
0x18002bb3d  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18002bb42  mov     r8, r12; int
0x18002bb45  call    WiaTrace_ProcessTrace_Ex
0x18002bb4a  jmp     loc_18002BE72
0x18002bb4f  mov     esi, 1
0x18002bb54  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002bb58  mov     edx, esi; dwRevision
0x18002bb5a  call    cs:__imp_InitializeSecurityDescriptor
0x18002bb60  mov     r8, [rbp+57h+pDacl]; pDacl
0x18002bb64  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002bb68  xor     r9d, r9d; bDaclDefaulted
0x18002bb6b  mov     edx, esi; bDaclPresent
0x18002bb6d  call    cs:__imp_SetSecurityDescriptorDacl
0x18002bb73  lea     r9, [rbp+57h+pSecurityDescriptor]; SecurityDescriptor
0x18002bb77  mov     edx, 4D2h; MaxCalls
0x18002bb7c  lea     r8, Endpoint; "STI_LRPC"
0x18002bb83  lea     rcx, Protseq; "ncalrpc"
0x18002bb8a  call    cs:__imp_RpcServerUseProtseqEpW
0x18002bb90  mov     edi, eax
0x18002bb92  test    eax, eax
0x18002bb94  jz      short loc_18002BBDD
0x18002bb96  mov     edx, eax
0x18002bb98  lea     rcx, aStartrpcserver_2; "StartRpcServerListen: RpcServerUseProts"...
0x18002bb9f  call    WiaTrace_TraceLog
0x18002bba4  mov     rdx, rax; char *
0x18002bba7  mov     rcx, r12; char *
0x18002bbaa  mov     rbx, rax
0x18002bbad  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bbb2  mov     rcx, rbx; this
0x18002bbb5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bbba  lea     rcx, aStartrpcserver_2; "StartRpcServerListen: RpcServerUseProts"...
0x18002bbc1  mov     edx, edi
0x18002bbc3  call    WiaTrace_Trace
0x18002bbc8  mov     r9d, esi; int
0x18002bbcb  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18002bbd0  mov     r8, r12; int
0x18002bbd3  call    WiaTrace_ProcessTrace_Ex
0x18002bbd8  jmp     loc_18002BE46
0x18002bbdd  mov     dl, sil
0x18002bbe0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x18002bbe7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002bbec  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18002bbf0  mov     r9d, 8
0x18002bbf6  mov     [rsp+0E0h+var_A8], rax
0x18002bbfb  lea     rcx, qword_18007B370
0x18002bc02  lea     rax, ?StiRpcSecurityCallBack@@YAJPEAX0@Z; StiRpcSecurityCallBack(void *,void *)
0x18002bc09  xor     r8d, r8d
0x18002bc0c  mov     [rsp+0E0h+var_B0], rax
0x18002bc11  xor     edx, edx
0x18002bc13  mov     dword ptr [rsp+0E0h+var_B8], 0FFFFFFFFh
0x18002bc1b  mov     dword ptr [rsp+0E0h+lpMem], 4D2h
0x18002bc23  call    cs:__imp_RpcServerRegisterIf3
0x18002bc29  mov     edi, eax
0x18002bc2b  test    eax, eax
0x18002bc2d  jz      short loc_18002BC5F
0x18002bc2f  mov     edx, eax
0x18002bc31  lea     rcx, aStartrpcserver; "StartRpcServerListen: RpcServerRegister"...
0x18002bc38  call    WiaTrace_TraceLog
0x18002bc3d  mov     rdx, rax; char *
0x18002bc40  mov     rcx, r12; char *
0x18002bc43  mov     rbx, rax
0x18002bc46  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bc4b  mov     rcx, rbx; this
0x18002bc4e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bc53  lea     rcx, aStartrpcserver; "StartRpcServerListen: RpcServerRegister"...
0x18002bc5a  jmp     loc_18002BBC1
0x18002bc5f  mov     ebx, 0Ah
0x18002bc64  mov     [rbp+57h+PrincName], 0
0x18002bc6c  mov     ecx, ebx; AuthnSvc
0x18002bc6e  lea     rdx, [rbp+57h+PrincName]; PrincName
0x18002bc72  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18002bc78  mov     edi, eax
0x18002bc7a  test    eax, eax
0x18002bc7c  jz      short loc_18002BCAE
0x18002bc7e  mov     edx, eax
0x18002bc80  lea     rcx, aRpcserverinqde; "RpcServerInqDefaultPrincName returned R"...
0x18002bc87  call    WiaTrace_TraceLog
0x18002bc8c  mov     rdx, rax; char *
0x18002bc8f  mov     rcx, r12; char *
0x18002bc92  mov     rbx, rax
0x18002bc95  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bc9a  mov     rcx, rbx; this
0x18002bc9d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bca2  lea     rcx, aRpcserverinqde; "RpcServerInqDefaultPrincName returned R"...
0x18002bca9  jmp     loc_18002BBC1
0x18002bcae  mov     rcx, [rbp+57h+PrincName]; ServerPrincName
0x18002bcb2  xor     r9d, r9d; Arg
0x18002bcb5  xor     r8d, r8d; GetKeyFn
0x18002bcb8  mov     edx, ebx; AuthnSvc
0x18002bcba  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18002bcc0  cmp     [rbp+57h+PrincName], 0
0x18002bcc5  mov     edi, eax
0x18002bcc7  jz      short loc_18002BCD3
0x18002bcc9  lea     rcx, [rbp+57h+PrincName]; String
0x18002bccd  call    cs:__imp_RpcStringFreeW
0x18002bcd3  test    edi, edi
0x18002bcd5  jz      short loc_18002BD07
0x18002bcd7  mov     edx, edi
0x18002bcd9  lea     rcx, aRpcserverregis; "RpcServerRegisterAuthInfo returned RpcS"...
0x18002bce0  call    WiaTrace_TraceLog
0x18002bce5  mov     rdx, rax; char *
0x18002bce8  mov     rcx, r12; char *
0x18002bceb  mov     rbx, rax
0x18002bcee  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bcf3  mov     rcx, rbx; this
0x18002bcf6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bcfb  lea     rcx, aRpcserverregis; "RpcServerRegisterAuthInfo returned RpcS"...
0x18002bd02  jmp     loc_18002BBC1
0x18002bd07  mov     r8d, esi; DontWait
0x18002bd0a  mov     edx, 4D2h; MaxCalls
0x18002bd0f  mov     ecx, esi; MinimumCallThreads
0x18002bd11  call    cs:__imp_RpcServerListen
0x18002bd17  mov     edi, eax
0x18002bd19  test    eax, eax
0x18002bd1b  jz      short loc_18002BD5F
0x18002bd1d  mov     edx, eax
0x18002bd1f  lea     rcx, aStartrpcserver_4; "StartRpcServerListen: RpcServerListen r"...
0x18002bd26  call    WiaTrace_TraceLog
0x18002bd2b  mov     rdx, rax; char *
0x18002bd2e  mov     rcx, r12; char *
0x18002bd31  mov     rbx, rax
0x18002bd34  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bd39  mov     rcx, rbx; this
0x18002bd3c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bd41  mov     edx, edi
0x18002bd43  lea     rcx, aStartrpcserver_4; "StartRpcServerListen: RpcServerListen r"...
0x18002bd4a  call    WiaTrace_Trace
0x18002bd4f  mov     r9d, esi; int
0x18002bd52  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18002bd57  mov     r8, r12; int
0x18002bd5a  call    WiaTrace_ProcessTrace_Ex
0x18002bd5f  mov     dl, sil
0x18002bd62  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloScanner@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner> `wil::Feature<__WilFeatureTraits_Feature_AppSiloScanner>::GetImpl(void)'::`2'::impl
0x18002bd69  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloScanner@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloScanner>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002bd6e  xor     r9d, r9d; SecurityDescriptorSize
0x18002bd71  lea     r8, [rbp+57h+EventAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x18002bd75  mov     edx, esi; StringSDRevision
0x18002bd77  lea     rcx, aDA0x1f0003SyA0; "D:(A;;0x1f0003;;;SY)(A;;0x1f0003;;;LS)("...
0x18002bd7e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002bd84  test    eax, eax
0x18002bd86  jnz     short loc_18002BDC1
0x18002bd88  call    cs:__imp_GetLastError
0x18002bd8e  mov     edx, eax
0x18002bd90  lea     rcx, aStartrpcserver_1; "StartRpcServerListen failed to produce "...
0x18002bd97  call    WiaTrace_TraceLog
0x18002bd9c  mov     rdx, rax; char *
0x18002bd9f  mov     rcx, r12; char *
0x18002bda2  mov     rbx, rax
0x18002bda5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002bdaa  mov     rcx, rbx; this
0x18002bdad  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002bdb2  call    cs:__imp_GetLastError
0x18002bdb8  lea     rcx, aStartrpcserver_1; "StartRpcServerListen failed to produce "...
0x18002bdbf  jmp     short loc_18002BE27
0x18002bdc1  lea     r9, Name; "Global\\WiaServiceStarted"
0x18002bdc8  xor     r8d, r8d; bInitialState
0x18002bdcb  xor     edx, edx; bManualReset
0x18002bdcd  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18002bdd1  call    cs:__imp_CreateEventW
0x18002bdd7  mov     cs:?g_hWiaServiceStarted@@3PEAXEA, rax; void * g_hWiaServiceStarted
0x18002bdde  test    rax, rax
0x18002bde1  jz      short loc_18002BD88
0x18002bde3  mov     rcx, rax; hEvent
0x18002bde6  call    cs:__imp_SetEvent
0x18002bdec  test    eax, eax
0x18002bdee  jnz     short loc_18002BE46
0x18002bdf0  call    cs:__imp_GetLastError
0x18002bdf6  mov     edx, eax
0x18002bdf8  lea     rcx, aStartrpcserver_3; "StartRpcServerListen failed to set even"...
0x18002bdff  call    WiaTrace_TraceLog
0x18002be04  mov     rdx, rax; char *
0x18002be07  mov     rcx, r12; char *
0x18002be0a  mov     rbx, rax
0x18002be0d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002be12  mov     rcx, rbx; this
0x18002be15  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002be1a  call    cs:__imp_GetLastError
0x18002be20  lea     rcx, aStartrpcserver_3; "StartRpcServerListen failed to set even"...
0x18002be27  mov     edx, eax
0x18002be29  call    WiaTrace_Trace
0x18002be2e  mov     r9d, esi; int
0x18002be31  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18002be36  mov     r8, r12; int
0x18002be39  call    WiaTrace_ProcessTrace_Ex
0x18002be3e  call    cs:__imp_GetLastError
0x18002be44  mov     edi, eax
0x18002be46  mov     rcx, [rbp+57h+EventAttributes.lpSecurityDescriptor]; hMem
0x18002be4a  test    rcx, rcx
0x18002be4d  jz      short loc_18002BE5D
0x18002be4f  call    cs:__imp_LocalFree
0x18002be55  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], 0
0x18002be5d  call    cs:__imp_GetProcessHeap
0x18002be63  mov     r8, [rbp+57h+pDacl]; lpMem
0x18002be67  xor     edx, edx; dwFlags
0x18002be69  mov     rcx, rax; hHeap
0x18002be6c  call    cs:__imp_HeapFree
0x18002be72  lea     rcx, [rbp+57h+var_60]; this
0x18002be76  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002be7b  lea     r11, [rsp+0E0h+var_10]
0x18002be83  mov     eax, edi
0x18002be85  mov     rbx, [r11+30h]
0x18002be89  mov     rsi, [r11+38h]
0x18002be8d  mov     rsp, r11
0x18002be90  pop     r12
0x18002be92  pop     rdi
0x18002be93  pop     rbp
0x18002be94  retn
```
