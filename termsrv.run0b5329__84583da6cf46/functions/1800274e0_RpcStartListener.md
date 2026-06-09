# RpcStartListener

- ea: `0x1800274e0`
- end: `0x180027806`
- name: `RpcStartListener`
- size: `806`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x180013150`
- `0x1800241f0`
- `0x1800274e0`
- `0x1800279a8`
- `0x180027a04`
- `0x180027b44`
- `0x1800321f0`
- `0x180047040`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180027614`
- `RPCRT4!RpcRevertToSelf` at `0x180027614`
- `RPCRT4!RpcImpersonateClient` at `0x1800275c1`
- `RPCRT4!RpcImpersonateClient` at `0x1800275c1`

## string_xrefs

- `0x1800275dd`: `RpcImpersonateClient failed: 0x%x in %s`
- `0x180027681`: `OpenKey failed: 0x%x in %s`
- `0x18002764a`: `AccessCheck( RESET ) failed: 0x%x in %s`
- `0x18002770a`: `OpenKey( ListenerName ) failed: 0x%x in %s`
- `0x180027744`: `ReadRegDWord( WIN_ENABLEWINSTATION ) failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcStartListener(__int64 a1)
{
  signed int v2; // edi
  RPC_STATUS v3; // eax
  const char *v4; // rdx
  __int64 v5; // rbx
  int v6; // eax
  bool v7; // sf
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const unsigned __int16 *v14; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+64h] [rbp-9Ch]
  _QWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+78h] [rbp-88h]
  HKEY v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+8Ch] [rbp-74h]
  _BYTE v28[592]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[32]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v23[1] = 0;
  v24 = 0;
  v25 = 0;
  v23[0] = &CRegistry::`vftable';
  v18[0] = &CRegistry::`vftable';
  v26 = -1;
  v27 = -1;
  v18[1] = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = -1;
  v17 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v28, 1, "RpcStartListener");
  if ( !a1 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hListener", "RpcStartListener");
    v2 = -2147024809;
    goto LABEL_35;
  }
  SmartPtr<ITerminal>::operator=(&v17, *(_QWORD *)(a1 + 1592));
  v3 = RpcImpersonateClient(0);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "RpcImpersonateClient failed: 0x%x in %s";
LABEL_7:
    _DbgPrintMessage(8, v4, (unsigned int)v2, "RpcStartListener");
    goto LABEL_35;
  }
  v5 = v17;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 96LL))(v17, 5);
  v6 = RpcRevertToSelf();
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    v2 = -2147024891;
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v6);
    goto LABEL_35;
  }
  if ( v2 < 0 )
  {
    v4 = "AccessCheck( RESET ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  v8 = CRegistry::OpenKey(
         (CRegistry *)v23,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0x20019u,
         v14);
  v2 = v8;
  if ( v8 > 0 )
    v2 = (unsigned __int16)v8 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "OpenKey failed: 0x%x in %s";
    goto LABEL_7;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)v5 + 72LL))(v5, v29, 32);
  v2 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "Listener->getName failed: 0x%x in %s", (unsigned int)v9, "RpcStartListener");
    goto LABEL_35;
  }
  if ( (g_DebugTraceComponent & 1) != 0 )
    _DbgPrintMessage(2, "Starting Listener %ws", v29);
  v10 = CRegistry::OpenKey((CRegistry *)v18, v25, v29, 0x20019u, v15);
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "OpenKey( ListenerName ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  v16 = 0;
  v11 = CRegistry::ReadRegDWord((CRegistry *)v18, L"fEnableWinStation", &v16);
  v2 = v11;
  if ( v11 > 0 )
    v2 = (unsigned __int16)v11 | 0x80070000;
  if ( v2 < 0 )
  {
    v4 = "ReadRegDWord( WIN_ENABLEWINSTATION ) failed: 0x%x in %s";
    goto LABEL_7;
  }
  if ( !v16 )
  {
    _DbgPrintMessage(4, "Listener->Start is denied because of local policy");
    v2 = -2147023636;
    goto LABEL_35;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v2 = v12;
  if ( v12 < 0 )
  {
    CHelper::LogErrorEvent(0xC000040B, v12);
    _DbgPrintMessage(8, "Failed to start listener: %ws, 0x%x", v29, (unsigned int)v2);
    v4 = "Listener->Start failed: 0x%x in %s";
    goto LABEL_7;
  }
LABEL_35:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v28);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  CRegistry::~CRegistry((CRegistry *)v18);
  CRegistry::~CRegistry((CRegistry *)v23);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800274e0  mov     [rsp-8+arg_8], rbx
0x1800274e5  mov     [rsp-8+arg_10], rdi
0x1800274ea  push    rbp
0x1800274eb  push    r14
0x1800274ed  push    r15
0x1800274ef  lea     rbp, [rsp-230h]
0x1800274f7  sub     rsp, 330h
0x1800274fe  mov     rax, cs:__security_cookie
0x180027505  xor     rax, rsp
0x180027508  mov     [rbp+240h+var_20], rax
0x18002750f  or      eax, 0FFFFFFFFh
0x180027512  mov     [rsp+340h+var_2D0], 0
0x18002751b  mov     rbx, rcx
0x18002751e  mov     [rsp+340h+var_2C8], 0
0x180027526  lea     rcx, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18002752d  mov     [rbp+240h+var_2C0], 0
0x180027535  mov     [rsp+340h+var_2D8], rcx
0x18002753a  lea     r14, aRpcstartlisten; "RpcStartListener"
0x180027541  mov     [rsp+340h+var_300], rcx
0x180027546  lea     edx, [rax+2]; int
0x180027549  mov     r8, r14; char *
0x18002754c  mov     [rbp+240h+var_2B8], eax
0x18002754f  lea     rcx, [rbp+240h+var_2B0]; this
0x180027553  mov     [rbp+240h+var_2B4], eax
0x180027556  mov     [rsp+340h+var_2F8], 0
0x18002755f  mov     [rsp+340h+var_2F0], 0
0x180027567  mov     [rsp+340h+var_2E8], 0
0x180027570  mov     [rsp+340h+var_2E0], eax
0x180027574  mov     [rsp+340h+var_2DC], eax
0x180027578  mov     [rsp+340h+var_308], 0
0x180027581  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180027586  test    rbx, rbx
0x180027589  jnz     short loc_1800275AE
0x18002758b  mov     r9, r14
0x18002758e  lea     r8, aHlistener; "hListener"
0x180027595  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002759c  lea     ecx, [rbx+8]; int
0x18002759f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800275a4  mov     edi, 80070057h
0x1800275a9  jmp     loc_1800277B5
0x1800275ae  mov     rdx, [rbx+638h]
0x1800275b5  lea     rcx, [rsp+340h+var_308]
0x1800275ba  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x1800275bf  xor     ecx, ecx; BindingHandle
0x1800275c1  call    cs:__imp_RpcImpersonateClient
0x1800275c7  mov     edi, eax
0x1800275c9  mov     r15d, 80070000h
0x1800275cf  test    eax, eax
0x1800275d1  jle     short loc_1800275D9
0x1800275d3  movzx   edi, ax
0x1800275d6  or      edi, r15d
0x1800275d9  test    edi, edi
0x1800275db  jns     short loc_1800275F9
0x1800275dd  lea     rdx, aRpcimpersonate; "RpcImpersonateClient failed: 0x%x in %s"
0x1800275e4  mov     r8d, edi
0x1800275e7  mov     r9, r14
0x1800275ea  mov     ecx, 8; int
0x1800275ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800275f4  jmp     loc_1800277B5
0x1800275f9  mov     rbx, [rsp+340h+var_308]
0x1800275fe  mov     edx, 5
0x180027603  mov     rcx, rbx
0x180027606  mov     rax, [rbx]
0x180027609  mov     rax, [rax+60h]
0x18002760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027612  mov     edi, eax
0x180027614  call    cs:__imp_RpcRevertToSelf
0x18002761a  test    eax, eax
0x18002761c  jle     short loc_180027626
0x18002761e  movzx   eax, ax
0x180027621  or      eax, r15d
0x180027624  test    eax, eax
0x180027626  jns     short loc_180027646
0x180027628  mov     r8d, eax
0x18002762b  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x180027632  mov     ecx, 8; int
0x180027637  mov     edi, 80070005h
0x18002763c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027641  jmp     loc_1800277B5
0x180027646  test    edi, edi
0x180027648  jns     short loc_180027653
0x18002764a  lea     rdx, aAccesscheckRes; "AccessCheck( RESET ) failed: 0x%x in %s"
0x180027651  jmp     short loc_1800275E4
0x180027653  mov     r9d, 20019h; unsigned int
0x180027659  lea     r8, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\Ter"...
0x180027660  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180027667  lea     rcx, [rsp+340h+var_2D8]; this
0x18002766c  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180027671  mov     edi, eax
0x180027673  test    eax, eax
0x180027675  jle     short loc_18002767D
0x180027677  movzx   edi, ax
0x18002767a  or      edi, r15d
0x18002767d  test    edi, edi
0x18002767f  jns     short loc_18002768D
0x180027681  lea     rdx, aOpenkeyFailed0; "OpenKey failed: 0x%x in %s"
0x180027688  jmp     loc_1800275E4
0x18002768d  mov     rax, [rbx]
0x180027690  lea     rdx, [rbp+240h+var_60]
0x180027697  mov     r8d, 20h ; ' '
0x18002769d  mov     rcx, rbx
0x1800276a0  mov     rax, [rax+48h]
0x1800276a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276a9  mov     edi, eax
0x1800276ab  test    eax, eax
0x1800276ad  jns     short loc_1800276BE
0x1800276af  mov     r8d, eax
0x1800276b2  lea     rdx, aListenerGetnam; "Listener->getName failed: 0x%x in %s"
0x1800276b9  jmp     loc_1800275E7
0x1800276be  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 1; ulong g_DebugTraceComponent
0x1800276c5  jz      short loc_1800276DF
0x1800276c7  lea     r8, [rbp+240h+var_60]
0x1800276ce  mov     ecx, 2; int
0x1800276d3  lea     rdx, aStartingListen; "Starting Listener %ws"
0x1800276da  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800276df  mov     rdx, [rbp+240h+var_2C0]; HKEY
0x1800276e3  lea     r8, [rbp+240h+var_60]; unsigned __int16 *
0x1800276ea  mov     r9d, 20019h; unsigned int
0x1800276f0  lea     rcx, [rsp+340h+var_300]; this
0x1800276f5  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x1800276fa  mov     edi, eax
0x1800276fc  test    eax, eax
0x1800276fe  jle     short loc_180027706
0x180027700  movzx   edi, ax
0x180027703  or      edi, r15d
0x180027706  test    edi, edi
0x180027708  jns     short loc_180027716
0x18002770a  lea     rdx, aOpenkeyListene; "OpenKey( ListenerName ) failed: 0x%x in"...
0x180027711  jmp     loc_1800275E4
0x180027716  lea     r8, [rsp+340h+var_310]; unsigned int *
0x18002771b  mov     [rsp+340h+var_310], 0
0x180027723  lea     rdx, aFenablewinstat; "fEnableWinStation"
0x18002772a  lea     rcx, [rsp+340h+var_300]; this
0x18002772f  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180027734  mov     edi, eax
0x180027736  test    eax, eax
0x180027738  jle     short loc_180027740
0x18002773a  movzx   edi, ax
0x18002773d  or      edi, r15d
0x180027740  test    edi, edi
0x180027742  jns     short loc_180027750
0x180027744  lea     rdx, aReadregdwordWi; "ReadRegDWord( WIN_ENABLEWINSTATION ) fa"...
0x18002774b  jmp     loc_1800275E4
0x180027750  cmp     [rsp+340h+var_310], 0
0x180027755  jz      short loc_18002779F
0x180027757  mov     rax, [rbx]
0x18002775a  mov     rcx, rbx
0x18002775d  mov     rax, [rax+18h]
0x180027761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027766  mov     edi, eax
0x180027768  test    eax, eax
0x18002776a  jns     short loc_1800277B5
0x18002776c  mov     edx, eax; int
0x18002776e  mov     ecx, 0C000040Bh; unsigned int
0x180027773  call    ?LogErrorEvent@CHelper@@SAJIJ@Z; CHelper::LogErrorEvent(uint,long)
0x180027778  mov     r9d, edi
0x18002777b  lea     r8, [rbp+240h+var_60]
0x180027782  lea     rdx, aFailedToStartL; "Failed to start listener: %ws, 0x%x"
0x180027789  mov     ecx, 8; int
0x18002778e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027793  lea     rdx, aListenerStartF; "Listener->Start failed: 0x%x in %s"
0x18002779a  jmp     loc_1800275E4
0x18002779f  lea     rdx, aListenerStartI; "Listener->Start is denied because of lo"...
0x1800277a6  mov     ecx, 4; int
0x1800277ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800277b0  mov     edi, 800704ECh
0x1800277b5  lea     rcx, [rbp+240h+var_2B0]; this
0x1800277b9  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x1800277be  lea     rcx, [rsp+340h+var_308]; void *
0x1800277c3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800277c8  lea     rcx, [rsp+340h+var_300]; this
0x1800277cd  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800277d2  lea     rcx, [rsp+340h+var_2D8]; this
0x1800277d7  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800277dc  mov     eax, edi
0x1800277de  mov     rcx, [rbp+240h+var_20]
0x1800277e5  xor     rcx, rsp; StackCookie
0x1800277e8  call    __security_check_cookie
0x1800277ed  lea     r11, [rsp+340h+var_10]
0x1800277f5  mov     rbx, [r11+28h]
0x1800277f9  mov     rdi, [r11+30h]
0x1800277fd  mov     rsp, r11
0x180027800  pop     r15
0x180027802  pop     r14
0x180027804  pop     rbp
0x180027805  retn
```
