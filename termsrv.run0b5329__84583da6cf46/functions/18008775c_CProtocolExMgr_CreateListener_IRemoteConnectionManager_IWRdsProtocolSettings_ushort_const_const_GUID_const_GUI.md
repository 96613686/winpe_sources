# CProtocolExMgr::CreateListener(IRemoteConnectionManager *,IWRdsProtocolSettings *,ushort const * const,_GUID const &,_GUID const &,IListenerItem * *)

- ea: `0x18008775c`
- end: `0x1800879b5`
- name: `?CreateListener@CProtocolExMgr@@QEAAJPEAVIRemoteConnectionManager@@PEAUIWRdsProtocolSettings@@QEBGAEBU_GUID@@3PEAPEAVIListenerItem@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(CProtocolExMgr *__hidden this, struct IRemoteConnectionManager *, struct IWRdsProtocolSettings *, const unsigned __int16 *const, const struct _GUID *, const struct _GUID *, struct IListenerItem **)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004aeb0`
- `0x18004c040`
- `0x18004c584`
- `0x18004c908`

## callees

- `0x180009ee0`
- `0x18000a210`
- `0x180011f80`
- `0x180013150`
- `0x1800241f0`
- `0x1800321f0`
- `0x1800326dc`
- `0x1800330c4`
- `0x180087414`
- `0x1800874a0`
- `0x18008775c`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x18008780b`
- `ntdll!RtlLookupElementGenericTable` at `0x18008780b`
- `ntdll!RtlInsertElementGenericTable` at `0x1800878f6`
- `ntdll!RtlInsertElementGenericTable` at `0x1800878f6`

## string_xrefs

- `0x18008795f`: `CProtocolExMgr::CreateListener`
- `0x1800878a2`: `new CProtocolManager failed: 0x%x in %s`
- `0x1800878cd`: `ptrProtocolMgr->Initialize failed: 0x%x in %s`
- `0x180087950`: `this->ProtocolMgrList.Add failed: 0x%x in %s`
- `0x180087947`: `ptrProtocolMgr->CreateListener failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CProtocolExMgr::CreateListener(
        struct _RTL_GENERIC_TABLE *this,
        struct IRemoteConnectionManager *a2,
        struct IWRdsProtocolSettings *a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        const struct _GUID *a6,
        struct IListenerItem **a7)
{
  struct _RTL_GENERIC_TABLE *v11; // r14
  __int64 **v12; // rax
  __int64 *v13; // rdi
  __int64 v14; // rax
  __int64 *v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  CProtocolManager *v18; // rax
  const char *v19; // rdx
  int v20; // eax
  int v21; // eax
  unsigned __int8 NewElement[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID Buffer; // [rsp+40h] [rbp-C0h] BYREF
  struct IListenerItem **v26; // [rsp+50h] [rbp-B0h]
  _BYTE v27[24]; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[144]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[1616]; // [rsp+110h] [rbp+10h] BYREF

  v26 = a7;
  Buffer = *a5;
  CProtocolManager::CProtocolManager((CProtocolManager *)v30, &Buffer);
  v24 = 0;
  memset_0(v29, 0, 0x84u);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v27, (struct CResource *)&this[22].CompareRoutine);
  v11 = this + 24;
  *(_QWORD *)&Buffer.Data1 = v30;
  v12 = (__int64 **)RtlLookupElementGenericTable(this + 24, &Buffer);
  if ( v12 )
  {
    v13 = *v12;
    v24 = v13;
    v14 = *v13;
    v15 = v13;
    goto LABEL_13;
  }
  v16 = ((__int64 (__fastcall *)(struct IWRdsProtocolSettings *, __int64, __int64, _BYTE *))a3->lpVtbl->GetSettings)(
          a3,
          1,
          1,
          v29);
  v17 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(
      8,
      "pIWRdsSettings->GetSettings failed: 0x%x in %s",
      (unsigned int)v16,
      "CProtocolExMgr::CreateListener");
    goto LABEL_17;
  }
  v18 = (CProtocolManager *)operator new(0x650u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)&Buffer.Data1 = v18;
  if ( v18 )
  {
    v28 = *a5;
    v18 = CProtocolManager::CProtocolManager(v18, &v28);
  }
  SmartPtr<ITerminal>::operator=(&v24, v18);
  v13 = v24;
  if ( !v24 )
  {
    v19 = "new CProtocolManager failed: 0x%x in %s";
LABEL_16:
    v17 = -2147024882;
    _DbgPrintMessage(8, v19, 2147942414LL, "CProtocolExMgr::CreateListener");
    goto LABEL_17;
  }
  v20 = (*(__int64 (__fastcall **)(__int64 *, struct IWRdsProtocolSettings *, _BYTE *))(*v24 + 24))(v24, a3, v29);
  v17 = v20;
  if ( v20 < 0 )
  {
    _DbgPrintMessage(
      8,
      "ptrProtocolMgr->Initialize failed: 0x%x in %s",
      (unsigned int)v20,
      "CProtocolExMgr::CreateListener");
    goto LABEL_17;
  }
  *(_QWORD *)&Buffer.Data1 = v13;
  NewElement[0] = 0;
  if ( !RtlInsertElementGenericTable(v11, &Buffer, 8u, NewElement) )
  {
    v19 = "this->ProtocolMgrList.Add failed: 0x%x in %s";
    goto LABEL_16;
  }
  v15 = *(__int64 **)&Buffer.Data1;
  v14 = **(_QWORD **)&Buffer.Data1;
LABEL_13:
  (*(void (__fastcall **)(__int64 *))(v14 + 8))(v15);
  CAutoLock::Unlock((CAutoLock *)v27);
  v21 = (*(__int64 (__fastcall **)(__int64 *, struct IRemoteConnectionManager *, const unsigned __int16 *, const struct _GUID *, struct IListenerItem **))(*v13 + 32))(
          v13,
          a2,
          a4,
          a6,
          v26);
  v17 = v21;
  if ( v21 < 0 )
    _DbgPrintMessage(
      8,
      "ptrProtocolMgr->CreateListener failed: 0x%x in %s",
      (unsigned int)v21,
      "CProtocolExMgr::CreateListener");
LABEL_17:
  CAutoLock::Unlock((CAutoLock *)v27);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v24);
  CProtocolManager::~CProtocolManager((CProtocolManager *)v30);
  return v17;
}

```

## disassembly

```asm
0x18008775c  push    rbp
0x18008775e  push    rbx
0x18008775f  push    rsi
0x180087760  push    rdi
0x180087761  push    r12
0x180087763  push    r13
0x180087765  push    r14
0x180087767  push    r15
0x180087769  lea     rbp, [rsp-678h]
0x180087771  sub     rsp, 778h
0x180087778  mov     rax, cs:__security_cookie
0x18008777f  xor     rax, rsp
0x180087782  mov     [rbp+6B0h+var_50], rax
0x180087789  mov     r12, r9
0x18008778c  mov     rsi, r8
0x18008778f  mov     r15, rdx
0x180087792  mov     rbx, rcx
0x180087795  mov     rdi, [rbp+6B0h+arg_20]
0x18008779c  mov     r13, [rbp+6B0h+arg_28]
0x1800877a3  mov     rax, [rbp+6B0h+arg_30]
0x1800877aa  mov     [rsp+7B0h+var_760], rax
0x1800877af  movups  xmm0, xmmword ptr [rdi]
0x1800877b2  movdqu  [rsp+7B0h+Buffer], xmm0
0x1800877b8  lea     rdx, [rsp+7B0h+Buffer]; struct _GUID
0x1800877bd  lea     rcx, [rbp+6B0h+var_6A0]; this
0x1800877c1  call    ??0CProtocolManager@@QEAA@U_GUID@@@Z; CProtocolManager::CProtocolManager(_GUID)
0x1800877c6  nop
0x1800877c7  mov     [rsp+7B0h+var_778], 0
0x1800877d0  xor     edx, edx; Val
0x1800877d2  mov     r8d, 84h; Size
0x1800877d8  lea     rcx, [rbp+6B0h+var_730]; void *
0x1800877dc  call    memset_0
0x1800877e1  lea     rdx, [rbx+658h]; struct CResource *
0x1800877e8  lea     rcx, [rsp+7B0h+var_758]; this
0x1800877ed  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800877f2  nop
0x1800877f3  lea     r14, [rbx+6C0h]
0x1800877fa  lea     rax, [rbp+6B0h+var_6A0]
0x1800877fe  mov     qword ptr [rsp+7B0h+Buffer], rax
0x180087803  lea     rdx, [rsp+7B0h+Buffer]; Buffer
0x180087808  mov     rcx, r14; Table
0x18008780b  call    cs:__imp_RtlLookupElementGenericTable
0x180087811  test    rax, rax
0x180087814  jz      short loc_180087829
0x180087816  mov     rdi, [rax]
0x180087819  mov     [rsp+7B0h+var_778], rdi
0x18008781e  mov     rax, [rdi]
0x180087821  mov     rcx, rdi
0x180087824  jmp     loc_180087909
0x180087829  mov     rax, [rsi]
0x18008782c  lea     r9, [rbp+6B0h+var_730]
0x180087830  mov     edx, 1
0x180087835  mov     r8d, edx
0x180087838  mov     rcx, rsi
0x18008783b  mov     rax, [rax+18h]
0x18008783f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087844  mov     ebx, eax
0x180087846  test    eax, eax
0x180087848  jns     short loc_180087859
0x18008784a  mov     r8d, eax
0x18008784d  lea     rdx, aPiwrdssettings; "pIWRdsSettings->GetSettings failed: 0x%"...
0x180087854  jmp     loc_18008795F
0x180087859  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180087860  mov     ecx, 650h; unsigned __int64
0x180087865  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008786a  mov     qword ptr [rsp+7B0h+Buffer], rax
0x18008786f  test    rax, rax
0x180087872  jz      short loc_18008788B
0x180087874  movups  xmm0, xmmword ptr [rdi]
0x180087877  movdqu  xmmword ptr [rsp+7B0h+var_740.Data1], xmm0
0x18008787d  lea     rdx, [rsp+7B0h+var_740]; struct _GUID
0x180087882  mov     rcx, rax; this
0x180087885  call    ??0CProtocolManager@@QEAA@U_GUID@@@Z; CProtocolManager::CProtocolManager(_GUID)
0x18008788a  nop
0x18008788b  mov     rdx, rax
0x18008788e  lea     rcx, [rsp+7B0h+var_778]
0x180087893  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180087898  mov     rdi, [rsp+7B0h+var_778]
0x18008789d  test    rdi, rdi
0x1800878a0  jnz     short loc_1800878AE
0x1800878a2  lea     rdx, aNewCprotocolma; "new CProtocolManager failed: 0x%x in %s"
0x1800878a9  jmp     loc_180087957
0x1800878ae  mov     rax, [rdi]
0x1800878b1  lea     r8, [rbp+6B0h+var_730]
0x1800878b5  mov     rdx, rsi
0x1800878b8  mov     rcx, rdi
0x1800878bb  mov     rax, [rax+18h]
0x1800878bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800878c4  mov     ebx, eax
0x1800878c6  test    eax, eax
0x1800878c8  jns     short loc_1800878D9
0x1800878ca  mov     r8d, eax
0x1800878cd  lea     rdx, aPtrprotocolmgr; "ptrProtocolMgr->Initialize failed: 0x%x"...
0x1800878d4  jmp     loc_18008795F
0x1800878d9  mov     qword ptr [rsp+7B0h+Buffer], rdi
0x1800878de  mov     [rsp+7B0h+NewElement], 0
0x1800878e3  lea     r9, [rsp+7B0h+NewElement]; NewElement
0x1800878e8  mov     r8d, 8; BufferSize
0x1800878ee  lea     rdx, [rsp+7B0h+Buffer]; Buffer
0x1800878f3  mov     rcx, r14; Table
0x1800878f6  call    cs:__imp_RtlInsertElementGenericTable
0x1800878fc  test    rax, rax
0x1800878ff  jz      short loc_180087950
0x180087901  mov     rcx, qword ptr [rsp+7B0h+Buffer]
0x180087906  mov     rax, [rcx]
0x180087909  mov     rax, [rax+8]
0x18008790d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087912  lea     rcx, [rsp+7B0h+var_758]; this
0x180087917  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008791c  mov     rax, [rdi]
0x18008791f  mov     rcx, [rsp+7B0h+var_760]
0x180087924  mov     [rsp+7B0h+var_790], rcx
0x180087929  mov     r9, r13
0x18008792c  mov     r8, r12
0x18008792f  mov     rdx, r15
0x180087932  mov     rcx, rdi
0x180087935  mov     rax, [rax+20h]
0x180087939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008793e  mov     ebx, eax
0x180087940  test    eax, eax
0x180087942  jns     short loc_180087971
0x180087944  mov     r8d, eax
0x180087947  lea     rdx, aPtrprotocolmgr_0; "ptrProtocolMgr->CreateListener failed: "...
0x18008794e  jmp     short loc_18008795F
0x180087950  lea     rdx, aThisProtocolmg; "this->ProtocolMgrList.Add failed: 0x%x "...
0x180087957  mov     ebx, 8007000Eh
0x18008795c  mov     r8d, ebx
0x18008795f  lea     r9, aCprotocolexmgr_15; "CProtocolExMgr::CreateListener"
0x180087966  mov     ecx, 8; int
0x18008796b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180087970  nop
0x180087971  lea     rcx, [rsp+7B0h+var_758]; this
0x180087976  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008797b  nop
0x18008797c  lea     rcx, [rsp+7B0h+var_778]; void *
0x180087981  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180087986  nop
0x180087987  lea     rcx, [rbp+6B0h+var_6A0]; this
0x18008798b  call    ??1CProtocolManager@@UEAA@XZ; CProtocolManager::~CProtocolManager(void)
0x180087990  mov     eax, ebx
0x180087992  mov     rcx, [rbp+6B0h+var_50]
0x180087999  xor     rcx, rsp; StackCookie
0x18008799c  call    __security_check_cookie
0x1800879a1  add     rsp, 778h
0x1800879a8  pop     r15
0x1800879aa  pop     r14
0x1800879ac  pop     r13
0x1800879ae  pop     r12
0x1800879b0  pop     rdi
0x1800879b1  pop     rsi
0x1800879b2  pop     rbx
0x1800879b3  pop     rbp
0x1800879b4  retn
```
