# Initialize(void)

- ea: `0x180002694`
- end: `0x180002982`
- name: `?Initialize@@YAXXZ`
- size: `750`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x18000195c`
- `0x180002694`
- `0x1800032dc`
- `0x180003430`
- `0x180003840`

## import_xrefs

- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180002838`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180002838`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002798`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002798`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800028e7`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800028e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026b9`

## string_xrefs

- `0x18000271c`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x1800027ec`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x180002881`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`
- `0x180002930`: `admin\wmi\events\forwarding\collector\service\srvmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Initialize(void)
{
  DWORD LastError; // ebx
  CollectorService *v1; // rax
  CollectorService *v2; // rax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v10; // [rsp+38h] [rbp-38h]
  const char *v11; // [rsp+40h] [rbp-30h]
  __int64 v12; // [rsp+48h] [rbp-28h]
  __int64 v13; // [rsp+50h] [rbp-20h]
  DWORD v14; // [rsp+58h] [rbp-18h]
  int v15; // [rsp+5Ch] [rbp-14h]
  int v16; // [rsp+60h] [rbp-10h]

  byte_18002F808 = 0;
  g_svchostShutdownEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_svchostShutdownEvent )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, LastError);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v12 = 0;
    v13 = 0;
    v14 = LastError;
    v15 = -1;
    v16 = 157;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v1 = (CollectorService *)operator new(0x78u);
  if ( v1 )
    v2 = CollectorService::CollectorService(v1);
  else
    v2 = 0;
  g_service = v2;
  v3 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x14u, (RPC_WSTR)L"wecsvc", 0);
  v4 = v3;
  if ( v3 && v3 != 1740 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v3);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v12 = 0;
    v13 = 0;
    v14 = v4;
    v15 = -1;
    v16 = 167;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = RpcServerRegisterAuthInfoW(0, 0xAu, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v5);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v12 = 0;
    v13 = 0;
    v14 = v6;
    v15 = -1;
    v16 = 173;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v7 = RpcServerRegisterIfEx(qword_180025140, 0, 0, 1u, 0x64u, (RPC_IF_CALLBACK_FN *)RpcInterfaceSecurityCallback);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids, v7);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\service\\srvmain.cpp";
    v12 = 0;
    v13 = 0;
    v14 = v8;
    v15 = -1;
    v16 = 184;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180002694  mov     [rsp-8+arg_8], rbx
0x180002699  mov     [rsp-8+arg_10], rdi
0x18000269e  push    rbp
0x18000269f  mov     rbp, rsp
0x1800026a2  sub     rsp, 70h
0x1800026a6  xor     edi, edi
0x1800026a8  mov     cs:byte_18002F808, dil
0x1800026af  xor     r9d, r9d; lpName
0x1800026b2  xor     r8d, r8d; bInitialState
0x1800026b5  xor     edx, edx; bManualReset
0x1800026b7  xor     ecx, ecx; lpEventAttributes
0x1800026b9  call    cs:__imp_CreateEventW
0x1800026bf  mov     cs:?g_svchostShutdownEvent@@3PEAXEA, rax; void * g_svchostShutdownEvent
0x1800026c6  test    rax, rax
0x1800026c9  jnz     loc_18000275C
0x1800026cf  call    cs:__imp_GetLastError
0x1800026d5  mov     ebx, eax
0x1800026d7  mov     eax, 507h
0x1800026dc  test    ebx, ebx
0x1800026de  cmovz   ebx, eax
0x1800026e1  lea     rcx, WPP_GLOBAL_Control
0x1800026e8  mov     r10, cs:WPP_GLOBAL_Control
0x1800026ef  cmp     r10, rcx
0x1800026f2  jz      short loc_180002718
0x1800026f4  test    byte ptr [r10+1Ch], 10h
0x1800026f9  jz      short loc_180002718
0x1800026fb  cmp     byte ptr [r10+19h], 2
0x180002700  jb      short loc_180002718
0x180002702  lea     edx, [rdi+11h]
0x180002705  mov     r9d, ebx
0x180002708  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x18000270f  mov     rcx, [r10+10h]
0x180002713  call    WPP_SF_D
0x180002718  mov     [rbp+var_38], dil
0x18000271c  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002723  mov     [rbp+var_30], rax
0x180002727  mov     [rbp+var_28], rdi
0x18000272b  mov     [rbp+var_20], rdi
0x18000272f  mov     [rbp+var_18], ebx
0x180002732  mov     [rbp+var_14], 0FFFFFFFFh
0x180002739  mov     [rbp+var_10], 9Dh
0x180002740  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002747  mov     [rbp+pExceptionObject], rax
0x18000274b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002752  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002756  call    _CxxThrowException_0
0x18000275c  mov     ecx, 78h ; 'x'; dwBytes
0x180002761  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002766  mov     [rbp+arg_0], rax
0x18000276a  test    rax, rax
0x18000276d  jz      short loc_180002779
0x18000276f  mov     rcx, rax; this
0x180002772  call    ??0CollectorService@@QEAA@XZ; CollectorService::CollectorService(void)
0x180002777  jmp     short loc_18000277C
0x180002779  mov     rax, rdi
0x18000277c  mov     cs:?g_service@@3PEAVCollectorService@@EA, rax; CollectorService * g_service
0x180002783  xor     r9d, r9d; SecurityDescriptor
0x180002786  lea     r8, ServiceName; "wecsvc"
0x18000278d  lea     edx, [r9+14h]; MaxCalls
0x180002791  lea     rcx, Protseq; "ncalrpc"
0x180002798  call    cs:__imp_RpcServerUseProtseqEpW
0x18000279e  mov     ebx, eax
0x1800027a0  test    eax, eax
0x1800027a2  jz      loc_18000282C
0x1800027a8  cmp     eax, 6CCh
0x1800027ad  jz      short loc_18000282C
0x1800027af  lea     rcx, WPP_GLOBAL_Control
0x1800027b6  mov     r10, cs:WPP_GLOBAL_Control
0x1800027bd  cmp     r10, rcx
0x1800027c0  jz      short loc_1800027E8
0x1800027c2  test    byte ptr [r10+1Ch], 10h
0x1800027c7  jz      short loc_1800027E8
0x1800027c9  cmp     byte ptr [r10+19h], 2
0x1800027ce  jb      short loc_1800027E8
0x1800027d0  mov     edx, 12h
0x1800027d5  mov     r9d, eax
0x1800027d8  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x1800027df  mov     rcx, [r10+10h]
0x1800027e3  call    WPP_SF_D
0x1800027e8  mov     [rbp+var_38], dil
0x1800027ec  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x1800027f3  mov     [rbp+var_30], rax
0x1800027f7  mov     [rbp+var_28], rdi
0x1800027fb  mov     [rbp+var_20], rdi
0x1800027ff  mov     [rbp+var_18], ebx
0x180002802  mov     [rbp+var_14], 0FFFFFFFFh
0x180002809  mov     [rbp+var_10], 0A7h
0x180002810  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180002817  mov     [rbp+pExceptionObject], rax
0x18000281b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002822  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002826  call    _CxxThrowException_0
0x18000282c  xor     r9d, r9d; Arg
0x18000282f  xor     r8d, r8d; GetKeyFn
0x180002832  lea     edx, [r9+0Ah]; AuthnSvc
0x180002836  xor     ecx, ecx; ServerPrincName
0x180002838  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18000283e  mov     ebx, eax
0x180002840  test    eax, eax
0x180002842  jz      short loc_1800028C1
0x180002844  lea     rcx, WPP_GLOBAL_Control
0x18000284b  mov     r10, cs:WPP_GLOBAL_Control
0x180002852  cmp     r10, rcx
0x180002855  jz      short loc_18000287D
0x180002857  test    byte ptr [r10+1Ch], 10h
0x18000285c  jz      short loc_18000287D
0x18000285e  cmp     byte ptr [r10+19h], 2
0x180002863  jb      short loc_18000287D
0x180002865  mov     edx, 13h
0x18000286a  mov     r9d, eax
0x18000286d  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002874  mov     rcx, [r10+10h]
0x180002878  call    WPP_SF_D
0x18000287d  mov     [rbp+var_38], dil
0x180002881  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002888  mov     [rbp+var_30], rax
0x18000288c  mov     [rbp+var_28], rdi
0x180002890  mov     [rbp+var_20], rdi
0x180002894  mov     [rbp+var_18], ebx
0x180002897  mov     [rbp+var_14], 0FFFFFFFFh
0x18000289e  mov     [rbp+var_10], 0ADh
0x1800028a5  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800028ac  mov     [rbp+pExceptionObject], rax
0x1800028b0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800028b7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800028bb  call    _CxxThrowException_0
0x1800028c1  lea     rax, ?RpcInterfaceSecurityCallback@@YAJPEAX0@Z; RpcInterfaceSecurityCallback(void *,void *)
0x1800028c8  mov     [rsp+70h+IfCallback], rax; IfCallback
0x1800028cd  mov     [rsp+70h+MaxCalls], 64h ; 'd'; MaxCalls
0x1800028d5  mov     r9d, 1; Flags
0x1800028db  xor     r8d, r8d; MgrEpv
0x1800028de  xor     edx, edx; MgrTypeUuid
0x1800028e0  lea     rcx, qword_180025140; IfSpec
0x1800028e7  call    cs:__imp_RpcServerRegisterIfEx
0x1800028ed  mov     ebx, eax
0x1800028ef  test    eax, eax
0x1800028f1  jz      short loc_180002970
0x1800028f3  lea     rcx, WPP_GLOBAL_Control
0x1800028fa  mov     r10, cs:WPP_GLOBAL_Control
0x180002901  cmp     r10, rcx
0x180002904  jz      short loc_18000292C
0x180002906  test    byte ptr [r10+1Ch], 10h
0x18000290b  jz      short loc_18000292C
0x18000290d  cmp     byte ptr [r10+19h], 2
0x180002912  jb      short loc_18000292C
0x180002914  mov     edx, 14h
0x180002919  mov     r9d, eax
0x18000291c  lea     r8, WPP_ca6bc7c05c2a3d506e8ee1e48e049877_Traceguids
0x180002923  mov     rcx, [r10+10h]
0x180002927  call    WPP_SF_D
0x18000292c  mov     [rbp+var_38], dil
0x180002930  lea     rax, aAdminWmiEvents; "admin\\wmi\\events\\forwarding\\collect"...
0x180002937  mov     [rbp+var_30], rax
0x18000293b  mov     [rbp+var_28], rdi
0x18000293f  mov     [rbp+var_20], rdi
0x180002943  mov     [rbp+var_18], ebx
0x180002946  mov     [rbp+var_14], 0FFFFFFFFh
0x18000294d  mov     [rbp+var_10], 0B8h
0x180002954  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000295b  mov     [rbp+pExceptionObject], rax
0x18000295f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180002966  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000296a  call    _CxxThrowException_0
0x180002970  lea     r11, [rsp+70h+var_s0]
0x180002975  mov     rbx, [r11+18h]
0x180002979  mov     rdi, [r11+20h]
0x18000297d  mov     rsp, r11
0x180002980  pop     rbp
0x180002981  retn
```
