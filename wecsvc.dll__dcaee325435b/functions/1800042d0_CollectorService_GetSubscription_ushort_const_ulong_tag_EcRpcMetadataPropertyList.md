# CollectorService::GetSubscription(ushort const *,ulong,tag_EcRpcMetadataPropertyList &)

- ea: `0x1800042d0`
- end: `0x18000442c`
- name: `?GetSubscription@CollectorService@@QEAAXPEBGKAEAUtag_EcRpcMetadataPropertyList@@@Z`
- size: `348`
- prototype: `void __fastcall(CollectorService *this, const unsigned __int16 *, __int64, struct tag_EcRpcMetadataPropertyList *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800035a0`

## callees

- `0x18000195c`
- `0x1800024f0`
- `0x180002510`
- `0x1800032dc`
- `0x180003be8`
- `0x180003c94`
- `0x1800042d0`
- `0x180005d7c`
- `0x1800145cc`
- `0x18001483c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180004386`
- `RPCRT4!RpcImpersonateClient` at `0x1800042f3`
- `RPCRT4!RpcImpersonateClient` at `0x1800042f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800043b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004404`

## string_xrefs

- `0x18000433e`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CollectorService::GetSubscription(
        CollectorService *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct tag_EcRpcMetadataPropertyList *a4)
{
  unsigned int v7; // ebx
  HKEY v8; // r8
  const unsigned __int16 *v9; // r9
  char v10[8]; // [rsp+40h] [rbp-69h] BYREF
  void (__fastcall *v11)(struct tag_EcRpcMetadataPropertyList *); // [rsp+48h] [rbp-61h]
  struct tag_EcRpcMetadataPropertyList *v12; // [rsp+50h] [rbp-59h]
  _BYTE v13[8]; // [rsp+58h] [rbp-51h] BYREF
  RPC_STATUS (__stdcall *v14)(); // [rsp+60h] [rbp-49h]
  void **pExceptionObject; // [rsp+68h] [rbp-41h] BYREF
  char v16; // [rsp+70h] [rbp-39h]
  const char *v17; // [rsp+78h] [rbp-31h]
  __int64 v18; // [rsp+80h] [rbp-29h]
  __int64 v19; // [rsp+88h] [rbp-21h]
  unsigned int v20; // [rsp+90h] [rbp-19h]
  int v21; // [rsp+94h] [rbp-15h]
  int v22; // [rsp+98h] [rbp-11h]
  char *v23; // [rsp+A0h] [rbp-9h]
  _BYTE v24[24]; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v25[64]; // [rsp+C0h] [rbp+17h] BYREF

  CollectorService::WaitForInit(this);
  v7 = RpcImpersonateClient(0);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v7);
    }
    v16 = 0;
    v17 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v18 = 0;
    v19 = 0;
    v20 = v7;
    v21 = -1;
    v22 = 410;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v13[0] = 0;
  v14 = RpcRevertToSelf;
  v11 = CleanupMetadataPropList;
  v12 = a4;
  v23 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  SubscriptionConfigReader::SubscriptionConfigReader((SubscriptionConfigReader *)v24, a2, v8, v9);
  SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(
    (SubscriptionConfigSnapshot *)v25,
    (const struct SubscriptionConfigReader *)v24,
    0,
    a4,
    1,
    0,
    0);
  v10[0] = 1;
  SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot((SubscriptionConfigSnapshot *)v25);
  ConfigBase::~ConfigBase((ConfigBase *)v24);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v10);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v13);
}

```

## disassembly

```asm
0x1800042d0  push    rbp
0x1800042d2  push    rbx
0x1800042d3  push    rsi
0x1800042d4  push    rdi
0x1800042d5  push    r14
0x1800042d7  lea     rbp, [rsp-37h]
0x1800042dc  sub     rsp, 0E0h
0x1800042e3  mov     rsi, r9
0x1800042e6  mov     r14, rdx
0x1800042e9  mov     rdi, rcx
0x1800042ec  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x1800042f1  xor     ecx, ecx; BindingHandle
0x1800042f3  call    cs:__imp_RpcImpersonateClient
0x1800042f9  mov     ebx, eax
0x1800042fb  test    eax, eax
0x1800042fd  jz      loc_180004386
0x180004303  lea     rax, WPP_GLOBAL_Control
0x18000430a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004311  cmp     rcx, rax
0x180004314  jz      short loc_18000433A
0x180004316  test    byte ptr [rcx+1Ch], 10h
0x18000431a  jz      short loc_18000433A
0x18000431c  cmp     byte ptr [rcx+19h], 2
0x180004320  jb      short loc_18000433A
0x180004322  mov     edx, 0Dh
0x180004327  mov     r9d, ebx
0x18000432a  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004331  mov     rcx, [rcx+10h]
0x180004335  call    WPP_SF_D
0x18000433a  mov     [rbp+57h+var_90], 0
0x18000433e  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004345  mov     [rbp+57h+var_88], rax
0x180004349  mov     [rbp+57h+var_80], 0
0x180004351  mov     [rbp+57h+var_78], 0
0x180004359  mov     [rbp+57h+var_70], ebx
0x18000435c  mov     [rbp+57h+var_6C], 0FFFFFFFFh
0x180004363  mov     [rbp+57h+var_68], 19Ah
0x18000436a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004371  mov     [rbp+57h+pExceptionObject], rax
0x180004375  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000437c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180004380  call    _CxxThrowException_0
0x180004386  mov     rax, cs:__imp_RpcRevertToSelf
0x18000438d  mov     [rbp+57h+var_A8], 0
0x180004391  mov     [rbp+57h+var_A0], rax
0x180004395  mov     [rbp+57h+var_C0], 0
0x180004399  lea     rax, ?CleanupMetadataPropList@@YAXPEAUtag_EcRpcMetadataPropertyList@@@Z; CleanupMetadataPropList(tag_EcRpcMetadataPropertyList *)
0x1800043a0  mov     [rbp+57h+var_B8], rax
0x1800043a4  mov     [rbp+57h+var_B0], rsi
0x1800043a8  lea     rbx, [rdi+18h]
0x1800043ac  mov     [rbp+57h+var_60], rbx
0x1800043b0  mov     rcx, rbx; lpCriticalSection
0x1800043b3  call    cs:__imp_EnterCriticalSection
0x1800043b9  nop
0x1800043ba  mov     rdx, r14; unsigned __int16 *
0x1800043bd  lea     rcx, [rbp+57h+var_58]; this
0x1800043c1  call    ??0SubscriptionConfigReader@@QEAA@PEBGPEAUHKEY__@@0@Z; SubscriptionConfigReader::SubscriptionConfigReader(ushort const *,HKEY__ *,ushort const *)
0x1800043c6  nop
0x1800043c7  mov     [rsp+100h+var_D0], 0; bool
0x1800043cc  mov     [rsp+100h+var_D8], 0; bool
0x1800043d1  mov     [rsp+100h+var_E0], 1; bool
0x1800043d6  mov     r9, rsi; struct tag_EcRpcMetadataPropertyList *
0x1800043d9  xor     r8d, r8d; unsigned __int16 *
0x1800043dc  lea     rdx, [rbp+57h+var_58]; struct SubscriptionConfigReader *
0x1800043e0  lea     rcx, [rbp+57h+var_40]; this
0x1800043e4  call    ??0SubscriptionConfigSnapshot@@QEAA@AEBVSubscriptionConfigReader@@PEBGAEAUtag_EcRpcMetadataPropertyList@@_N33@Z; SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(SubscriptionConfigReader const &,ushort const *,tag_EcRpcMetadataPropertyList &,bool,bool,bool)
0x1800043e9  mov     [rbp+57h+var_C0], 1
0x1800043ed  lea     rcx, [rbp+57h+var_40]; this
0x1800043f1  call    ??1SubscriptionConfigSnapshot@@UEAA@XZ; SubscriptionConfigSnapshot::~SubscriptionConfigSnapshot(void)
0x1800043f6  nop
0x1800043f7  lea     rcx, [rbp+57h+var_58]; this
0x1800043fb  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
0x180004400  nop
0x180004401  mov     rcx, rbx; lpCriticalSection
0x180004404  call    cs:__imp_LeaveCriticalSection
0x18000440a  nop
0x18000440b  lea     rcx, [rbp+57h+var_C0]
0x18000440f  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x180004414  nop
0x180004415  lea     rcx, [rbp+57h+var_A8]
0x180004419  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18000441e  add     rsp, 0E0h
0x180004425  pop     r14
0x180004427  pop     rdi
0x180004428  pop     rsi
0x180004429  pop     rbx
0x18000442a  pop     rbp
0x18000442b  retn
```
