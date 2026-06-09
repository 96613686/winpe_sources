# CConnectionHandlerItem::LoadHandler(void)

- ea: `0x18007250c`
- end: `0x1800728bd`
- name: `?LoadHandler@CConnectionHandlerItem@@QEAAJXZ`
- size: `945`
- prototype: `__int64 __fastcall(CConnectionHandlerItem *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800723b8`

## callees

- `0x18000a210`
- `0x18000c2f0`
- `0x180013150`
- `0x180026b00`
- `0x180027a04`
- `0x180027a44`
- `0x180027b44`
- `0x1800321f0`
- `0x1800326dc`
- `0x180044b50`
- `0x180047040`
- `0x18007120c`
- `0x18007250c`
- `0x180076dc0`
- `0x18008ce60`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800726d0`
- `RPCRT4!UuidFromStringW` at `0x1800726d0`
- `RPCRT4!UuidToStringW` at `0x180072624`
- `RPCRT4!UuidToStringW` at `0x180072624`
- `RPCRT4!RpcStringFreeW` at `0x180072869`
- `RPCRT4!RpcStringFreeW` at `0x180072869`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072786`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180072786`

## string_xrefs

- `0x18007269f`: `CLSID`
- `0x1800726bf`: `CLSID`
- `0x180072610`: `OpenHandlerRegistryKey failed: 0x%x in %s`
- `0x1800727a5`: `CoCreateInstance() on handler %ws failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CConnectionHandlerItem::LoadHandler(CConnectionHandlerItem *this)
{
  int InstanceOfRemoteConnectionManager; // eax
  signed int v3; // edi
  const char *v4; // rdx
  struct IRemoteConnectionManager *v5; // rbx
  RPC_STATUS v6; // eax
  int RegDWord; // eax
  const unsigned __int16 *v8; // r9
  int v9; // eax
  RPC_STATUS v10; // eax
  _QWORD *v11; // r14
  HRESULT v12; // eax
  unsigned __int16 *v13; // rax
  __int64 v14; // rsi
  int v15; // eax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-29h] BYREF
  struct ITSEventDispatcher *v18; // [rsp+38h] [rbp-21h] BYREF
  struct IRemoteConnectionManager *v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+48h] [rbp-11h] BYREF
  RPC_WSTR v21; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp+7h] BYREF
  int v24; // [rsp+70h] [rbp+17h]
  __int64 v25; // [rsp+78h] [rbp+1Fh]
  int v26; // [rsp+80h] [rbp+27h]
  int v27; // [rsp+84h] [rbp+2Bh]
  UUID Uuid; // [rsp+88h] [rbp+2Fh] BYREF

  v23[0] = &CRegistry::`vftable';
  v23[1] = 0;
  v24 = 0;
  v25 = 0;
  v26 = -1;
  v27 = -1;
  Uuid = 0;
  v21 = 0;
  StringUuid = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager(&v19);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetInstanceOfRemoteConnectionManager failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v4, (unsigned int)InstanceOfRemoteConnectionManager, "CConnectionHandlerItem::LoadHandler");
    goto LABEL_45;
  }
  v5 = v19;
  InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v19 + 64LL))(
                                        v19,
                                        &v20);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetInstanceOfSessionManager failed: 0x%x in %s";
    goto LABEL_3;
  }
  InstanceOfRemoteConnectionManager = CHelper::GetGlobalDispatcher(&v18);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetGlobalDispatcher failed: 0x%x in %s";
    goto LABEL_3;
  }
  InstanceOfRemoteConnectionManager = CConnectionHandlerItem::OpenHandlerRegistryKey(this, (struct CRegistry *)v23);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "OpenHandlerRegistryKey failed: 0x%x in %s";
    goto LABEL_3;
  }
  v6 = UuidToStringW((const UUID *)((char *)this + 1592), &StringUuid);
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->GetConnectionGUID failed: 0x%x in %s",
      (unsigned int)v3,
      "CConnectionHandlerItem::LoadHandler");
    goto LABEL_45;
  }
  RegDWord = CRegistry::ReadRegDWord((CRegistry *)v23, L"fAcceptConnection", (unsigned int *)this + 406);
  v3 = RegDWord;
  if ( RegDWord > 0 )
    v3 = (unsigned __int16)RegDWord | 0x80070000;
  if ( v3 < 0 )
  {
    v8 = L"fAcceptConnection";
LABEL_19:
    _DbgPrintMessage(8, "Handler %ws missing %ws reg value", StringUuid, v8);
    goto LABEL_45;
  }
  v9 = CRegistry::ReadRegString((CRegistry *)v23, L"CLSID", &v21, &v22);
  v3 = v9;
  if ( v9 > 0 )
    v3 = (unsigned __int16)v9 | 0x80070000;
  if ( v3 < 0 )
  {
    v8 = L"CLSID";
    goto LABEL_19;
  }
  v10 = UuidFromStringW(v21, &Uuid);
  v3 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 < 0 )
    {
      _DbgPrintMessage(8, "UuidFromString failed: 0x%x in %s", (unsigned int)v3, "CConnectionHandlerItem::LoadHandler");
      goto LABEL_45;
    }
  }
  if ( !memcmp_0(&Uuid, qword_1800EDD90, 0x10u) )
  {
    v11 = (_QWORD *)((char *)this + 1608);
    InstanceOfRemoteConnectionManager = GetInstanceOfHybridHandler((char *)this + 1608);
    v3 = InstanceOfRemoteConnectionManager;
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      v4 = "GetInstanceOfHybridHandler failed: 0x%x in %s";
      goto LABEL_3;
    }
  }
  else
  {
    v11 = (_QWORD *)((char *)this + 1608);
    if ( !memcmp_0(&Uuid, qword_1800EDDA0, 0x10u) )
    {
      InstanceOfRemoteConnectionManager = GetInstanceOfDefaultDesktopHandler((char *)this + 1608);
      v3 = InstanceOfRemoteConnectionManager;
      if ( InstanceOfRemoteConnectionManager < 0 )
      {
        v4 = "GetInstanceOfDefaultDesktopHandler failed: 0x%x in %s";
        goto LABEL_3;
      }
    }
    else
    {
      v12 = CoCreateInstance(&Uuid, 0, 5u, &IID_IConnectionHandler, (LPVOID *)this + 201);
      v3 = v12;
      if ( v12 < 0 )
      {
        CHelper::LogErrorEvent(0xC0000400, v12);
        _DbgPrintMessage(8, "CoCreateInstance() on handler %ws failed with 0x%x", StringUuid, (unsigned int)v3);
        goto LABEL_45;
      }
    }
  }
  v13 = (unsigned __int16 *)operator new(0x648u, (const struct std::nothrow_t *)std::nothrow);
  v21 = v13;
  if ( v13 )
    v14 = CConnectionHandlerItem::CConnHandlerKeepAliveObject::CConnHandlerKeepAliveObject(
            (CConnectionHandlerItem::CConnHandlerKeepAliveObject *)v13,
            this);
  else
    v14 = 0;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IRemoteConnectionManager *, struct ITSEventDispatcher *, __int64))(*(_QWORD *)*v11 + 24LL))(
            *v11,
            v20,
            v5,
            v18,
            v14);
    v3 = v15;
    if ( v15 < 0 )
      _DbgPrintMessage(
        8,
        "m_pConnectionHandlerObject->Initialize failed: 0x%x in %s",
        v15,
        "CConnectionHandlerItem::LoadHandler");
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  else
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "new CConnectionHandlerKeepAliveObject failed: 0x%x in %s",
      2147942414LL,
      "CConnectionHandlerItem::LoadHandler");
  }
LABEL_45:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v18);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v19);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v20);
  CRegistry::~CRegistry((CRegistry *)v23);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007250c  mov     [rsp-8+arg_8], rbx
0x180072511  mov     [rsp-8+arg_10], rsi
0x180072516  push    rbp
0x180072517  push    rdi
0x180072518  push    r14
0x18007251a  lea     rbp, [rsp-47h]
0x18007251f  sub     rsp, 0A0h
0x180072526  mov     rax, cs:__security_cookie
0x18007252d  xor     rax, rsp
0x180072530  mov     [rbp+57h+var_18], rax
0x180072534  mov     rsi, rcx
0x180072537  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18007253e  mov     [rbp+57h+var_50], rax
0x180072542  mov     [rbp+57h+var_48], 0
0x18007254a  mov     [rbp+57h+var_40], 0
0x180072551  mov     [rbp+57h+var_38], 0
0x180072559  or      eax, 0FFFFFFFFh
0x18007255c  mov     [rbp+57h+var_30], eax
0x18007255f  mov     [rbp+57h+var_2C], eax
0x180072562  xorps   xmm0, xmm0
0x180072565  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180072569  mov     [rbp+57h+var_60], 0
0x180072571  mov     [rbp+57h+StringUuid], 0
0x180072579  mov     [rbp+57h+var_68], 0
0x180072581  mov     [rbp+57h+var_70], 0
0x180072589  mov     [rbp+57h+var_78], 0
0x180072591  lea     rcx, [rbp+57h+var_70]; struct IRemoteConnectionManager **
0x180072595  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x18007259a  mov     edi, eax
0x18007259c  test    eax, eax
0x18007259e  jns     short loc_1800725C0
0x1800725a0  lea     rdx, aGetinstanceofr; "GetInstanceOfRemoteConnectionManager fa"...
0x1800725a7  mov     r8d, eax
0x1800725aa  lea     r9, aCconnectionhan_0; "CConnectionHandlerItem::LoadHandler"
0x1800725b1  mov     ecx, 8; int
0x1800725b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800725bb  jmp     loc_18007285E
0x1800725c0  mov     rbx, [rbp+57h+var_70]
0x1800725c4  mov     rax, [rbx]
0x1800725c7  lea     rdx, [rbp+57h+var_68]
0x1800725cb  mov     rcx, rbx
0x1800725ce  mov     rax, [rax+40h]
0x1800725d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725d7  mov     edi, eax
0x1800725d9  test    eax, eax
0x1800725db  jns     short loc_1800725E6
0x1800725dd  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x1800725e4  jmp     short loc_1800725A7
0x1800725e6  lea     rcx, [rbp+57h+var_78]; struct ITSEventDispatcher **
0x1800725ea  call    ?GetGlobalDispatcher@CHelper@@SAJPEAPEAUITSEventDispatcher@@@Z; CHelper::GetGlobalDispatcher(ITSEventDispatcher * *)
0x1800725ef  mov     edi, eax
0x1800725f1  test    eax, eax
0x1800725f3  jns     short loc_1800725FE
0x1800725f5  lea     rdx, aGetglobaldispa; "GetGlobalDispatcher failed: 0x%x in %s"
0x1800725fc  jmp     short loc_1800725A7
0x1800725fe  lea     rdx, [rbp+57h+var_50]; struct CRegistry *
0x180072602  mov     rcx, rsi; this
0x180072605  call    ?OpenHandlerRegistryKey@CConnectionHandlerItem@@AEAAJAEAVCRegistry@@@Z; CConnectionHandlerItem::OpenHandlerRegistryKey(CRegistry &)
0x18007260a  mov     edi, eax
0x18007260c  test    eax, eax
0x18007260e  jns     short loc_180072619
0x180072610  lea     rdx, aOpenhandlerreg; "OpenHandlerRegistryKey failed: 0x%x in "...
0x180072617  jmp     short loc_1800725A7
0x180072619  lea     rcx, [rsi+638h]; Uuid
0x180072620  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180072624  call    cs:__imp_UuidToStringW
0x18007262a  mov     edi, eax
0x18007262c  mov     r14d, 80070000h
0x180072632  test    eax, eax
0x180072634  jle     short loc_18007263C
0x180072636  movzx   edi, ax
0x180072639  or      edi, r14d
0x18007263c  test    edi, edi
0x18007263e  jns     short loc_18007264F
0x180072640  mov     r8d, edi
0x180072643  lea     rdx, aThisGetconnect_0; "this->GetConnectionGUID failed: 0x%x in"...
0x18007264a  jmp     loc_1800725AA
0x18007264f  lea     r8, [rsi+658h]; unsigned int *
0x180072656  lea     rdx, aFacceptconnect; "fAcceptConnection"
0x18007265d  lea     rcx, [rbp+57h+var_50]; this
0x180072661  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180072666  mov     edi, eax
0x180072668  test    eax, eax
0x18007266a  jle     short loc_180072672
0x18007266c  movzx   edi, ax
0x18007266f  or      edi, r14d
0x180072672  test    edi, edi
0x180072674  jns     short loc_180072697
0x180072676  lea     r9, aFacceptconnect; "fAcceptConnection"
0x18007267d  mov     r8, [rbp+57h+StringUuid]
0x180072681  lea     rdx, aHandlerWsMissi; "Handler %ws missing %ws reg value"
0x180072688  mov     ecx, 8; int
0x18007268d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072692  jmp     loc_18007285E
0x180072697  lea     r9, [rbp+57h+var_58]; unsigned int *
0x18007269b  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x18007269f  lea     rdx, aClsid; "CLSID"
0x1800726a6  lea     rcx, [rbp+57h+var_50]; this
0x1800726aa  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x1800726af  mov     edi, eax
0x1800726b1  test    eax, eax
0x1800726b3  jle     short loc_1800726BB
0x1800726b5  movzx   edi, ax
0x1800726b8  or      edi, r14d
0x1800726bb  test    edi, edi
0x1800726bd  jns     short loc_1800726C8
0x1800726bf  lea     r9, aClsid; "CLSID"
0x1800726c6  jmp     short loc_18007267D
0x1800726c8  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800726cc  mov     rcx, [rbp+57h+var_60]; StringUuid
0x1800726d0  call    cs:__imp_UuidFromStringW
0x1800726d6  mov     edi, eax
0x1800726d8  test    eax, eax
0x1800726da  jz      short loc_1800726F7
0x1800726dc  jle     short loc_1800726E4
0x1800726de  movzx   edi, ax
0x1800726e1  or      edi, r14d
0x1800726e4  test    edi, edi
0x1800726e6  jns     short loc_1800726F7
0x1800726e8  mov     r8d, edi
0x1800726eb  lea     rdx, aUuidfromstring_0; "UuidFromString failed: 0x%x in %s"
0x1800726f2  jmp     loc_1800725AA
0x1800726f7  mov     edi, 10h
0x1800726fc  mov     r8d, edi; Size
0x1800726ff  lea     rdx, qword_1800EDD90; Buf2
0x180072706  lea     rcx, [rbp+57h+Uuid]; Buf1
0x18007270a  call    memcmp_0
0x18007270f  test    eax, eax
0x180072711  jnz     short loc_180072738
0x180072713  lea     r14, [rsi+648h]
0x18007271a  mov     rcx, r14
0x18007271d  call    GetInstanceOfHybridHandler
0x180072722  mov     edi, eax
0x180072724  test    eax, eax
0x180072726  jns     loc_1800727BB
0x18007272c  lea     rdx, aGetinstanceofh_0; "GetInstanceOfHybridHandler failed: 0x%x"...
0x180072733  jmp     loc_1800725A7
0x180072738  mov     r8, rdi; Size
0x18007273b  lea     rdx, qword_1800EDDA0; Buf2
0x180072742  lea     rcx, [rbp+57h+Uuid]; Buf1
0x180072746  call    memcmp_0
0x18007274b  lea     r14, [rsi+648h]
0x180072752  test    eax, eax
0x180072754  jnz     short loc_180072770
0x180072756  mov     rcx, r14
0x180072759  call    GetInstanceOfDefaultDesktopHandler
0x18007275e  mov     edi, eax
0x180072760  test    eax, eax
0x180072762  jns     short loc_1800727BB
0x180072764  lea     rdx, aGetinstanceofd; "GetInstanceOfDefaultDesktopHandler fail"...
0x18007276b  jmp     loc_1800725A7
0x180072770  mov     [rsp+0B0h+ppv], r14; ppv
0x180072775  lea     r9, IID_IConnectionHandler; riid
0x18007277c  xor     edx, edx; pUnkOuter
0x18007277e  lea     r8d, [rdx+5]; dwClsContext
0x180072782  lea     rcx, [rbp+57h+Uuid]; rclsid
0x180072786  call    cs:__imp_CoCreateInstance
0x18007278c  mov     edi, eax
0x18007278e  test    eax, eax
0x180072790  jns     short loc_1800727BB
0x180072792  mov     edx, eax; int
0x180072794  mov     ecx, 0C0000400h; unsigned int
0x180072799  call    ?LogErrorEvent@CHelper@@SAJIJ@Z; CHelper::LogErrorEvent(uint,long)
0x18007279e  mov     r9d, edi
0x1800727a1  mov     r8, [rbp+57h+StringUuid]
0x1800727a5  lea     rdx, aCocreateinstan_1; "CoCreateInstance() on handler %ws faile"...
0x1800727ac  mov     ecx, 8; int
0x1800727b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800727b6  jmp     loc_18007285E
0x1800727bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800727c2  mov     ecx, 648h; unsigned __int64
0x1800727c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800727cc  mov     [rbp+57h+var_60], rax
0x1800727d0  test    rax, rax
0x1800727d3  jz      short loc_1800727E5
0x1800727d5  mov     rdx, rsi; struct CConnectionHandlerItem *
0x1800727d8  mov     rcx, rax; this
0x1800727db  call    ??0CConnHandlerKeepAliveObject@CConnectionHandlerItem@@QEAA@PEAV1@@Z; CConnectionHandlerItem::CConnHandlerKeepAliveObject::CConnHandlerKeepAliveObject(CConnectionHandlerItem *)
0x1800727e0  mov     rsi, rax
0x1800727e3  jmp     short loc_1800727E7
0x1800727e5  xor     esi, esi
0x1800727e7  test    rsi, rsi
0x1800727ea  jnz     short loc_180072800
0x1800727ec  mov     edi, 8007000Eh
0x1800727f1  mov     r8d, edi
0x1800727f4  lea     rdx, aNewCconnection_3; "new CConnectionHandlerKeepAliveObject f"...
0x1800727fb  jmp     loc_1800725AA
0x180072800  mov     rax, [rsi]
0x180072803  mov     rcx, rsi
0x180072806  mov     rax, [rax+8]
0x18007280a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007280f  mov     rcx, [r14]
0x180072812  mov     rax, [rcx]
0x180072815  mov     [rsp+0B0h+ppv], rsi
0x18007281a  mov     r9, [rbp+57h+var_78]
0x18007281e  mov     r8, rbx
0x180072821  mov     rdx, [rbp+57h+var_68]
0x180072825  mov     rax, [rax+18h]
0x180072829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007282e  mov     edi, eax
0x180072830  test    eax, eax
0x180072832  jns     short loc_18007284F
0x180072834  lea     r9, aCconnectionhan_0; "CConnectionHandlerItem::LoadHandler"
0x18007283b  mov     r8d, eax
0x18007283e  lea     rdx, aMPconnectionha; "m_pConnectionHandlerObject->Initialize "...
0x180072845  mov     ecx, 8; int
0x18007284a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007284f  mov     rax, [rsi]
0x180072852  mov     rcx, rsi
0x180072855  mov     rax, [rax+10h]
0x180072859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007285e  cmp     [rbp+57h+StringUuid], 0
0x180072863  jz      short loc_180072870
0x180072865  lea     rcx, [rbp+57h+StringUuid]; String
0x180072869  call    cs:__imp_RpcStringFreeW
0x18007286f  nop
0x180072870  lea     rcx, [rbp+57h+var_78]; void *
0x180072874  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180072879  nop
0x18007287a  lea     rcx, [rbp+57h+var_70]; void *
0x18007287e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180072883  nop
0x180072884  lea     rcx, [rbp+57h+var_68]; void *
0x180072888  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18007288d  nop
0x18007288e  lea     rcx, [rbp+57h+var_50]; this
0x180072892  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180072897  mov     eax, edi
0x180072899  mov     rcx, [rbp+57h+var_18]
0x18007289d  xor     rcx, rsp; StackCookie
0x1800728a0  call    __security_check_cookie
0x1800728a5  lea     r11, [rsp+0B0h+var_10]
0x1800728ad  mov     rbx, [r11+28h]
0x1800728b1  mov     rsi, [r11+30h]
0x1800728b5  mov     rsp, r11
0x1800728b8  pop     r14
0x1800728ba  pop     rdi
0x1800728bb  pop     rbp
0x1800728bc  retn
```
