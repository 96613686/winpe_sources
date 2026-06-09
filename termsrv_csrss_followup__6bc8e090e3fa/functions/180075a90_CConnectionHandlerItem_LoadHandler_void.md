# CConnectionHandlerItem::LoadHandler(void)

- ea: `0x180075a90`
- end: `0x180075e42`
- name: `?LoadHandler@CConnectionHandlerItem@@QEAAJXZ`
- size: `946`
- prototype: `__int64 __fastcall(CConnectionHandlerItem *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007593c`

## callees

- `0x180009940`
- `0x18000c2a0`
- `0x1800139c0`
- `0x180027f14`
- `0x180028e44`
- `0x180028e88`
- `0x180028f88`
- `0x180033f60`
- `0x18003444c`
- `0x180046f00`
- `0x180049490`
- `0x180074740`
- `0x180074d84`
- `0x180075a90`
- `0x18007a3a0`
- `0x180090a90`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180075c42`
- `RPCRT4!UuidFromStringW` at `0x180075c42`
- `RPCRT4!RpcStringFreeW` at `0x180075de7`
- `RPCRT4!RpcStringFreeW` at `0x180075de7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075cfe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075cfe`

## string_xrefs

- `0x180075c11`: `CLSID`
- `0x180075c31`: `CLSID`
- `0x180075b94`: `OpenHandlerRegistryKey failed: 0x%x in %s`
- `0x180075d23`: `CoCreateInstance() on handler %ws failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CConnectionHandlerItem::LoadHandler(CConnectionHandlerItem *this)
{
  int InstanceOfRemoteConnectionManager; // eax
  signed int v3; // edi
  const char *v4; // rdx
  struct IRemoteConnectionManager *v5; // rbx
  int RegDWord; // eax
  const unsigned __int16 *v7; // r9
  int v8; // eax
  RPC_STATUS v9; // eax
  _QWORD *v10; // r14
  HRESULT v11; // eax
  unsigned __int16 *v12; // rax
  __int64 v13; // rsi
  int v14; // eax
  RPC_WSTR String; // [rsp+30h] [rbp-29h] BYREF
  struct ITSEventDispatcher *v17; // [rsp+38h] [rbp-21h] BYREF
  struct IRemoteConnectionManager *v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v22[2]; // [rsp+60h] [rbp+7h] BYREF
  int v23; // [rsp+70h] [rbp+17h]
  __int64 v24; // [rsp+78h] [rbp+1Fh]
  int v25; // [rsp+80h] [rbp+27h]
  int v26; // [rsp+84h] [rbp+2Bh]
  UUID Uuid; // [rsp+88h] [rbp+2Fh] BYREF

  v22[0] = &CRegistry::`vftable';
  v22[1] = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = -1;
  Uuid = 0;
  StringUuid = 0;
  String = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager(&v18);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetInstanceOfRemoteConnectionManager failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v4, (unsigned int)InstanceOfRemoteConnectionManager, "CConnectionHandlerItem::LoadHandler");
    goto LABEL_43;
  }
  v5 = v18;
  InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v18 + 64LL))(
                                        v18,
                                        &v19);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetInstanceOfSessionManager failed: 0x%x in %s";
    goto LABEL_3;
  }
  InstanceOfRemoteConnectionManager = CHelper::GetGlobalDispatcher(&v17);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "GetGlobalDispatcher failed: 0x%x in %s";
    goto LABEL_3;
  }
  InstanceOfRemoteConnectionManager = CConnectionHandlerItem::OpenHandlerRegistryKey(this, (struct CRegistry *)v22);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "OpenHandlerRegistryKey failed: 0x%x in %s";
    goto LABEL_3;
  }
  InstanceOfRemoteConnectionManager = CConnectionHandlerItem::GetConnectionGUID(this, &String);
  v3 = InstanceOfRemoteConnectionManager;
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    v4 = "this->GetConnectionGUID failed: 0x%x in %s";
    goto LABEL_3;
  }
  RegDWord = CRegistry::ReadRegDWord((CRegistry *)v22, L"fAcceptConnection", (unsigned int *)this + 406);
  v3 = RegDWord;
  if ( RegDWord > 0 )
    v3 = (unsigned __int16)RegDWord | 0x80070000;
  if ( v3 < 0 )
  {
    v7 = L"fAcceptConnection";
LABEL_17:
    _DbgPrintMessage(8, "Handler %ws missing %ws reg value", String, v7);
    goto LABEL_43;
  }
  v8 = CRegistry::ReadRegString((CRegistry *)v22, L"CLSID", &StringUuid, &v21);
  v3 = v8;
  if ( v8 > 0 )
    v3 = (unsigned __int16)v8 | 0x80070000;
  if ( v3 < 0 )
  {
    v7 = L"CLSID";
    goto LABEL_17;
  }
  v9 = UuidFromStringW(StringUuid, &Uuid);
  v3 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    if ( v3 < 0 )
    {
      _DbgPrintMessage(8, "UuidFromString failed: 0x%x in %s", (unsigned int)v3, "CConnectionHandlerItem::LoadHandler");
      goto LABEL_43;
    }
  }
  if ( !memcmp_0(&Uuid, qword_1800F3DE0, 0x10u) )
  {
    v10 = (_QWORD *)((char *)this + 1608);
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
    v10 = (_QWORD *)((char *)this + 1608);
    if ( !memcmp_0(&Uuid, qword_1800F3DF0, 0x10u) )
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
      v11 = CoCreateInstance(&Uuid, 0, 5u, &IID_IConnectionHandler, (LPVOID *)this + 201);
      v3 = v11;
      if ( v11 < 0 )
      {
        CHelper::LogErrorEvent(0xC0000400, v11);
        _DbgPrintMessage(8, "CoCreateInstance() on handler %ws failed with 0x%x", String, (unsigned int)v3);
        goto LABEL_43;
      }
    }
  }
  v12 = (unsigned __int16 *)operator new(0x648u, (const struct std::nothrow_t *)std::nothrow);
  StringUuid = v12;
  if ( v12 )
    v13 = CConnectionHandlerItem::CConnHandlerKeepAliveObject::CConnHandlerKeepAliveObject(
            (CConnectionHandlerItem::CConnHandlerKeepAliveObject *)v12,
            this);
  else
    v13 = 0;
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IRemoteConnectionManager *, struct ITSEventDispatcher *, __int64))(*(_QWORD *)*v10 + 24LL))(
            *v10,
            v19,
            v5,
            v17,
            v13);
    v3 = v14;
    if ( v14 < 0 )
      _DbgPrintMessage(
        8,
        "m_pConnectionHandlerObject->Initialize failed: 0x%x in %s",
        v14,
        "CConnectionHandlerItem::LoadHandler");
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
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
LABEL_43:
  if ( String )
    RpcStringFreeW(&String);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v18);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v19);
  CRegistry::~CRegistry((CRegistry *)v22);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180075a90  mov     [rsp-8+arg_8], rbx
0x180075a95  mov     [rsp-8+arg_10], rsi
0x180075a9a  push    rbp
0x180075a9b  push    rdi
0x180075a9c  push    r14
0x180075a9e  lea     rbp, [rsp-47h]
0x180075aa3  sub     rsp, 0A0h
0x180075aaa  mov     rax, cs:__security_cookie
0x180075ab1  xor     rax, rsp
0x180075ab4  mov     [rbp+57h+var_18], rax
0x180075ab8  mov     rsi, rcx
0x180075abb  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180075ac2  mov     [rbp+57h+var_50], rax
0x180075ac6  mov     [rbp+57h+var_48], 0
0x180075ace  mov     [rbp+57h+var_40], 0
0x180075ad5  mov     [rbp+57h+var_38], 0
0x180075add  or      eax, 0FFFFFFFFh
0x180075ae0  mov     [rbp+57h+var_30], eax
0x180075ae3  mov     [rbp+57h+var_2C], eax
0x180075ae6  xorps   xmm0, xmm0
0x180075ae9  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180075aed  mov     [rbp+57h+StringUuid], 0
0x180075af5  mov     [rbp+57h+String], 0
0x180075afd  mov     [rbp+57h+var_68], 0
0x180075b05  mov     [rbp+57h+var_70], 0
0x180075b0d  mov     [rbp+57h+var_78], 0
0x180075b15  lea     rcx, [rbp+57h+var_70]; struct IRemoteConnectionManager **
0x180075b19  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180075b1e  mov     edi, eax
0x180075b20  test    eax, eax
0x180075b22  jns     short loc_180075B44
0x180075b24  lea     rdx, aGetinstanceofr; "GetInstanceOfRemoteConnectionManager fa"...
0x180075b2b  mov     r8d, eax
0x180075b2e  lea     r9, aCconnectionhan_0; "CConnectionHandlerItem::LoadHandler"
0x180075b35  mov     ecx, 8; int
0x180075b3a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180075b3f  jmp     loc_180075DDC
0x180075b44  mov     rbx, [rbp+57h+var_70]
0x180075b48  mov     rax, [rbx]
0x180075b4b  lea     rdx, [rbp+57h+var_68]
0x180075b4f  mov     rcx, rbx
0x180075b52  mov     rax, [rax+40h]
0x180075b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b5b  mov     edi, eax
0x180075b5d  test    eax, eax
0x180075b5f  jns     short loc_180075B6A
0x180075b61  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180075b68  jmp     short loc_180075B2B
0x180075b6a  lea     rcx, [rbp+57h+var_78]; struct ITSEventDispatcher **
0x180075b6e  call    ?GetGlobalDispatcher@CHelper@@SAJPEAPEAUITSEventDispatcher@@@Z; CHelper::GetGlobalDispatcher(ITSEventDispatcher * *)
0x180075b73  mov     edi, eax
0x180075b75  test    eax, eax
0x180075b77  jns     short loc_180075B82
0x180075b79  lea     rdx, aGetglobaldispa; "GetGlobalDispatcher failed: 0x%x in %s"
0x180075b80  jmp     short loc_180075B2B
0x180075b82  lea     rdx, [rbp+57h+var_50]; struct CRegistry *
0x180075b86  mov     rcx, rsi; this
0x180075b89  call    ?OpenHandlerRegistryKey@CConnectionHandlerItem@@AEAAJAEAVCRegistry@@@Z; CConnectionHandlerItem::OpenHandlerRegistryKey(CRegistry &)
0x180075b8e  mov     edi, eax
0x180075b90  test    eax, eax
0x180075b92  jns     short loc_180075B9D
0x180075b94  lea     rdx, aOpenhandlerreg; "OpenHandlerRegistryKey failed: 0x%x in "...
0x180075b9b  jmp     short loc_180075B2B
0x180075b9d  lea     rdx, [rbp+57h+String]; unsigned __int16 **
0x180075ba1  mov     rcx, rsi; this
0x180075ba4  call    ?GetConnectionGUID@CConnectionHandlerItem@@QEAAJPEAPEAG@Z; CConnectionHandlerItem::GetConnectionGUID(ushort * *)
0x180075ba9  mov     edi, eax
0x180075bab  test    eax, eax
0x180075bad  jns     short loc_180075BBB
0x180075baf  lea     rdx, aThisGetconnect_0; "this->GetConnectionGUID failed: 0x%x in"...
0x180075bb6  jmp     loc_180075B2B
0x180075bbb  lea     r8, [rsi+658h]; unsigned int *
0x180075bc2  lea     rdx, aFacceptconnect; "fAcceptConnection"
0x180075bc9  lea     rcx, [rbp+57h+var_50]; this
0x180075bcd  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180075bd2  mov     edi, eax
0x180075bd4  mov     r14d, 80070000h
0x180075bda  test    eax, eax
0x180075bdc  jle     short loc_180075BE4
0x180075bde  movzx   edi, ax
0x180075be1  or      edi, r14d
0x180075be4  test    edi, edi
0x180075be6  jns     short loc_180075C09
0x180075be8  lea     r9, aFacceptconnect; "fAcceptConnection"
0x180075bef  mov     r8, [rbp+57h+String]
0x180075bf3  lea     rdx, aHandlerWsMissi; "Handler %ws missing %ws reg value"
0x180075bfa  mov     ecx, 8; int
0x180075bff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180075c04  jmp     loc_180075DDC
0x180075c09  lea     r9, [rbp+57h+var_58]; unsigned int *
0x180075c0d  lea     r8, [rbp+57h+StringUuid]; unsigned __int16 **
0x180075c11  lea     rdx, aClsid; "CLSID"
0x180075c18  lea     rcx, [rbp+57h+var_50]; this
0x180075c1c  call    ?ReadRegString@CRegistry@@QEAAKPEBGPEAPEAGPEAK@Z; CRegistry::ReadRegString(ushort const *,ushort * *,ulong *)
0x180075c21  mov     edi, eax
0x180075c23  test    eax, eax
0x180075c25  jle     short loc_180075C2D
0x180075c27  movzx   edi, ax
0x180075c2a  or      edi, r14d
0x180075c2d  test    edi, edi
0x180075c2f  jns     short loc_180075C3A
0x180075c31  lea     r9, aClsid; "CLSID"
0x180075c38  jmp     short loc_180075BEF
0x180075c3a  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180075c3e  mov     rcx, [rbp+57h+StringUuid]; StringUuid
0x180075c42  call    cs:__imp_UuidFromStringW
0x180075c49  nop     dword ptr [rax+rax+00h]
0x180075c4e  mov     edi, eax
0x180075c50  test    eax, eax
0x180075c52  jz      short loc_180075C6F
0x180075c54  jle     short loc_180075C5C
0x180075c56  movzx   edi, ax
0x180075c59  or      edi, r14d
0x180075c5c  test    edi, edi
0x180075c5e  jns     short loc_180075C6F
0x180075c60  mov     r8d, edi
0x180075c63  lea     rdx, aUuidfromstring_0; "UuidFromString failed: 0x%x in %s"
0x180075c6a  jmp     loc_180075B2E
0x180075c6f  mov     edi, 10h
0x180075c74  mov     r8d, edi; Size
0x180075c77  lea     rdx, qword_1800F3DE0; Buf2
0x180075c7e  lea     rcx, [rbp+57h+Uuid]; Buf1
0x180075c82  call    memcmp_0
0x180075c87  test    eax, eax
0x180075c89  jnz     short loc_180075CB0
0x180075c8b  lea     r14, [rsi+648h]
0x180075c92  mov     rcx, r14
0x180075c95  call    GetInstanceOfHybridHandler
0x180075c9a  mov     edi, eax
0x180075c9c  test    eax, eax
0x180075c9e  jns     loc_180075D39
0x180075ca4  lea     rdx, aGetinstanceofh_0; "GetInstanceOfHybridHandler failed: 0x%x"...
0x180075cab  jmp     loc_180075B2B
0x180075cb0  mov     r8, rdi; Size
0x180075cb3  lea     rdx, qword_1800F3DF0; Buf2
0x180075cba  lea     rcx, [rbp+57h+Uuid]; Buf1
0x180075cbe  call    memcmp_0
0x180075cc3  lea     r14, [rsi+648h]
0x180075cca  test    eax, eax
0x180075ccc  jnz     short loc_180075CE8
0x180075cce  mov     rcx, r14
0x180075cd1  call    GetInstanceOfDefaultDesktopHandler
0x180075cd6  mov     edi, eax
0x180075cd8  test    eax, eax
0x180075cda  jns     short loc_180075D39
0x180075cdc  lea     rdx, aGetinstanceofd; "GetInstanceOfDefaultDesktopHandler fail"...
0x180075ce3  jmp     loc_180075B2B
0x180075ce8  mov     [rsp+0B0h+ppv], r14; ppv
0x180075ced  lea     r9, IID_IConnectionHandler; riid
0x180075cf4  xor     edx, edx; pUnkOuter
0x180075cf6  lea     r8d, [rdx+5]; dwClsContext
0x180075cfa  lea     rcx, [rbp+57h+Uuid]; rclsid
0x180075cfe  call    cs:__imp_CoCreateInstance
0x180075d05  nop     dword ptr [rax+rax+00h]
0x180075d0a  mov     edi, eax
0x180075d0c  test    eax, eax
0x180075d0e  jns     short loc_180075D39
0x180075d10  mov     edx, eax; int
0x180075d12  mov     ecx, 0C0000400h; unsigned int
0x180075d17  call    ?LogErrorEvent@CHelper@@SAJIJ@Z; CHelper::LogErrorEvent(uint,long)
0x180075d1c  mov     r9d, edi
0x180075d1f  mov     r8, [rbp+57h+String]
0x180075d23  lea     rdx, aCocreateinstan_1; "CoCreateInstance() on handler %ws faile"...
0x180075d2a  mov     ecx, 8; int
0x180075d2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180075d34  jmp     loc_180075DDC
0x180075d39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180075d40  mov     ecx, 648h; unsigned __int64
0x180075d45  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180075d4a  mov     [rbp+57h+StringUuid], rax
0x180075d4e  test    rax, rax
0x180075d51  jz      short loc_180075D63
0x180075d53  mov     rdx, rsi; struct CConnectionHandlerItem *
0x180075d56  mov     rcx, rax; this
0x180075d59  call    ??0CConnHandlerKeepAliveObject@CConnectionHandlerItem@@QEAA@PEAV1@@Z; CConnectionHandlerItem::CConnHandlerKeepAliveObject::CConnHandlerKeepAliveObject(CConnectionHandlerItem *)
0x180075d5e  mov     rsi, rax
0x180075d61  jmp     short loc_180075D65
0x180075d63  xor     esi, esi
0x180075d65  test    rsi, rsi
0x180075d68  jnz     short loc_180075D7E
0x180075d6a  mov     edi, 8007000Eh
0x180075d6f  mov     r8d, edi
0x180075d72  lea     rdx, aNewCconnection_3; "new CConnectionHandlerKeepAliveObject f"...
0x180075d79  jmp     loc_180075B2E
0x180075d7e  mov     rax, [rsi]
0x180075d81  mov     rcx, rsi
0x180075d84  mov     rax, [rax+8]
0x180075d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d8d  mov     rcx, [r14]
0x180075d90  mov     rax, [rcx]
0x180075d93  mov     [rsp+0B0h+ppv], rsi
0x180075d98  mov     r9, [rbp+57h+var_78]
0x180075d9c  mov     r8, rbx
0x180075d9f  mov     rdx, [rbp+57h+var_68]
0x180075da3  mov     rax, [rax+18h]
0x180075da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dac  mov     edi, eax
0x180075dae  test    eax, eax
0x180075db0  jns     short loc_180075DCD
0x180075db2  lea     r9, aCconnectionhan_0; "CConnectionHandlerItem::LoadHandler"
0x180075db9  mov     r8d, eax
0x180075dbc  lea     rdx, aMPconnectionha; "m_pConnectionHandlerObject->Initialize "...
0x180075dc3  mov     ecx, 8; int
0x180075dc8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180075dcd  mov     rax, [rsi]
0x180075dd0  mov     rcx, rsi
0x180075dd3  mov     rax, [rax+10h]
0x180075dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ddc  cmp     [rbp+57h+String], 0
0x180075de1  jz      short loc_180075DF4
0x180075de3  lea     rcx, [rbp+57h+String]; String
0x180075de7  call    cs:__imp_RpcStringFreeW
0x180075dee  nop     dword ptr [rax+rax+00h]
0x180075df3  nop
0x180075df4  lea     rcx, [rbp+57h+var_78]; void *
0x180075df8  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180075dfd  nop
0x180075dfe  lea     rcx, [rbp+57h+var_70]; void *
0x180075e02  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180075e07  nop
0x180075e08  lea     rcx, [rbp+57h+var_68]; void *
0x180075e0c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180075e11  nop
0x180075e12  lea     rcx, [rbp+57h+var_50]; this
0x180075e16  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180075e1b  mov     eax, edi
0x180075e1d  mov     rcx, [rbp+57h+var_18]
0x180075e21  xor     rcx, rsp; StackCookie
0x180075e24  call    __security_check_cookie
0x180075e29  lea     r11, [rsp+0B0h+var_10]
0x180075e31  mov     rbx, [r11+28h]
0x180075e35  mov     rsi, [r11+30h]
0x180075e39  mov     rsp, r11
0x180075e3c  pop     r14
0x180075e3e  pop     rdi
0x180075e3f  pop     rbp
0x180075e40  retn
```
