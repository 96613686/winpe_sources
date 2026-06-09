# s_wscIcfEnable

- ea: `0x180033750`
- end: `0x1800337c5`
- name: `s_wscIcfEnable`
- size: `117`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180002e30`
- `0x1800037ac`
- `0x18001bb90`
- `0x18001fb24`
- `0x180033750`

## import_xrefs

- `ntdll!ShipAssertMsgA` at `0x180033788`
- `ntdll!ShipAssertMsgA` at `0x180033788`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033794`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033794`
- `FirewallAPI!FwActivate` at `0x18003376e`
- `FirewallAPI!FwActivate` at `0x18003376e`

## string_xrefs

- `0x18003377a`: `admin\wsc\src\client\service\wscsvclib\firewallstatus.cpp`

## pseudocode

```c
__int64 __fastcall s_wscIcfEnable(void *a1)
{
  CThirdPartyManager *v1; // rdi
  int v2; // eax
  unsigned __int16 v3; // bx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  CRpcImpersonateClient::CRpcImpersonateClient((CRpcImpersonateClient *)&v5, a1);
  v1 = WscServiceUtils::g_pFirewallManager;
  v2 = FwActivate();
  v3 = v2;
  if ( v2 >= 0 )
    SetEvent(*((HANDLE *)v1 + 11));
  else
    ShipAssertMsgA(2010051, (unsigned int)v2, "admin\\wsc\\src\\client\\service\\wscsvclib\\firewallstatus.cpp");
  CRpcImpersonateClient::~CRpcImpersonateClient((CRpcImpersonateClient *)&v5);
  PollForChanges();
  CAlertStatus::FireNotificationEvents(g_pAlertStatus, 0);
  return v3;
}

```

## disassembly

```asm
0x180033750  mov     [rsp+arg_0], rbx
0x180033755  push    rdi
0x180033756  sub     rsp, 20h
0x18003375a  mov     rdx, rcx; void *
0x18003375d  lea     rcx, [rsp+28h+arg_8]; this
0x180033762  call    ??0CRpcImpersonateClient@@QEAA@PEAX@Z; CRpcImpersonateClient::CRpcImpersonateClient(void *)
0x180033767  mov     rdi, cs:?g_pFirewallManager@WscServiceUtils@@3PEAVCFirewallManager@@EA; CFirewallManager * WscServiceUtils::g_pFirewallManager
0x18003376e  call    cs:__imp_FwActivate
0x180033774  mov     ebx, eax
0x180033776  test    eax, eax
0x180033778  jns     short loc_180033790
0x18003377a  lea     r8, aAdminWscSrcCli_1; "admin\\wsc\\src\\client\\service\\wscsv"...
0x180033781  mov     edx, eax
0x180033783  mov     ecx, 1EABC3h
0x180033788  call    cs:__imp_ShipAssertMsgA
0x18003378e  jmp     short loc_18003379A
0x180033790  mov     rcx, [rdi+58h]; hEvent
0x180033794  call    cs:__imp_SetEvent
0x18003379a  lea     rcx, [rsp+28h+arg_8]; this
0x18003379f  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x1800337a4  call    ?PollForChanges@@YAHXZ; PollForChanges(void)
0x1800337a9  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; lpCriticalSection
0x1800337b0  xor     edx, edx; int
0x1800337b2  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x1800337b7  movzx   eax, bx
0x1800337ba  mov     rbx, [rsp+28h+arg_0]
0x1800337bf  add     rsp, 20h
0x1800337c3  pop     rdi
0x1800337c4  retn
```
