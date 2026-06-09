# CProtocolExMgr::CreateListener(IRemoteConnectionManager *,IWRdsProtocolSettings *,ushort const * const,_GUID const &,_GUID const &,IListenerItem * *)

- ea: `0x18008b1bc`
- end: `0x18008b422`
- name: `?CreateListener@CProtocolExMgr@@QEAAJPEAVIRemoteConnectionManager@@PEAUIWRdsProtocolSettings@@QEBGAEBU_GUID@@3PEAPEAVIListenerItem@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(CProtocolExMgr *__hidden this, struct IRemoteConnectionManager *, struct IWRdsProtocolSettings *, const unsigned __int16 *const, const struct _GUID *, const struct _GUID *, struct IListenerItem **)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d4d0`
- `0x18004e670`
- `0x18004ebb4`
- `0x18004ef38`

## callees

- `0x1800095a0`
- `0x180009940`
- `0x180012750`
- `0x1800139c0`
- `0x18002558c`
- `0x180033f60`
- `0x18003444c`
- `0x180034e64`
- `0x18008ae54`
- `0x18008aee0`
- `0x18008b1bc`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x18008b26b`
- `ntdll!RtlLookupElementGenericTable` at `0x18008b26b`
- `ntdll!RtlInsertElementGenericTable` at `0x18008b35c`
- `ntdll!RtlInsertElementGenericTable` at `0x18008b35c`

## string_xrefs

- `0x18008b3cb`: `CProtocolExMgr::CreateListener`
- `0x18008b308`: `new CProtocolManager failed: 0x%x in %s`
- `0x18008b333`: `ptrProtocolMgr->Initialize failed: 0x%x in %s`
- `0x18008b3bc`: `this->ProtocolMgrList.Add failed: 0x%x in %s`
- `0x18008b3b3`: `ptrProtocolMgr->CreateListener failed: 0x%x in %s`

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
0x18008b1bc  push    rbp
0x18008b1be  push    rbx
0x18008b1bf  push    rsi
0x18008b1c0  push    rdi
0x18008b1c1  push    r12
0x18008b1c3  push    r13
0x18008b1c5  push    r14
0x18008b1c7  push    r15
0x18008b1c9  lea     rbp, [rsp-678h]
0x18008b1d1  sub     rsp, 778h
0x18008b1d8  mov     rax, cs:__security_cookie
0x18008b1df  xor     rax, rsp
0x18008b1e2  mov     [rbp+6B0h+var_50], rax
0x18008b1e9  mov     r12, r9
0x18008b1ec  mov     rsi, r8
0x18008b1ef  mov     r15, rdx
0x18008b1f2  mov     rbx, rcx
0x18008b1f5  mov     rdi, [rbp+6B0h+arg_20]
0x18008b1fc  mov     r13, [rbp+6B0h+arg_28]
0x18008b203  mov     rax, [rbp+6B0h+arg_30]
0x18008b20a  mov     [rsp+7B0h+var_760], rax
0x18008b20f  movups  xmm0, xmmword ptr [rdi]
0x18008b212  movdqu  [rsp+7B0h+Buffer], xmm0
0x18008b218  lea     rdx, [rsp+7B0h+Buffer]; struct _GUID
0x18008b21d  lea     rcx, [rbp+6B0h+var_6A0]; this
0x18008b221  call    ??0CProtocolManager@@QEAA@U_GUID@@@Z; CProtocolManager::CProtocolManager(_GUID)
0x18008b226  nop
0x18008b227  mov     [rsp+7B0h+var_778], 0
0x18008b230  xor     edx, edx; Val
0x18008b232  mov     r8d, 84h; Size
0x18008b238  lea     rcx, [rbp+6B0h+var_730]; void *
0x18008b23c  call    memset_0
0x18008b241  lea     rdx, [rbx+658h]; struct CResource *
0x18008b248  lea     rcx, [rsp+7B0h+var_758]; this
0x18008b24d  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18008b252  nop
0x18008b253  lea     r14, [rbx+6C0h]
0x18008b25a  lea     rax, [rbp+6B0h+var_6A0]
0x18008b25e  mov     qword ptr [rsp+7B0h+Buffer], rax
0x18008b263  lea     rdx, [rsp+7B0h+Buffer]; Buffer
0x18008b268  mov     rcx, r14; Table
0x18008b26b  call    cs:__imp_RtlLookupElementGenericTable
0x18008b272  nop     dword ptr [rax+rax+00h]
0x18008b277  test    rax, rax
0x18008b27a  jz      short loc_18008B28F
0x18008b27c  mov     rdi, [rax]
0x18008b27f  mov     [rsp+7B0h+var_778], rdi
0x18008b284  mov     rax, [rdi]
0x18008b287  mov     rcx, rdi
0x18008b28a  jmp     loc_18008B375
0x18008b28f  mov     rax, [rsi]
0x18008b292  lea     r9, [rbp+6B0h+var_730]
0x18008b296  mov     edx, 1
0x18008b29b  mov     r8d, edx
0x18008b29e  mov     rcx, rsi
0x18008b2a1  mov     rax, [rax+18h]
0x18008b2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2aa  mov     ebx, eax
0x18008b2ac  test    eax, eax
0x18008b2ae  jns     short loc_18008B2BF
0x18008b2b0  mov     r8d, eax
0x18008b2b3  lea     rdx, aPiwrdssettings; "pIWRdsSettings->GetSettings failed: 0x%"...
0x18008b2ba  jmp     loc_18008B3CB
0x18008b2bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008b2c6  mov     ecx, 650h; unsigned __int64
0x18008b2cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008b2d0  mov     qword ptr [rsp+7B0h+Buffer], rax
0x18008b2d5  test    rax, rax
0x18008b2d8  jz      short loc_18008B2F1
0x18008b2da  movups  xmm0, xmmword ptr [rdi]
0x18008b2dd  movdqu  xmmword ptr [rsp+7B0h+var_740.Data1], xmm0
0x18008b2e3  lea     rdx, [rsp+7B0h+var_740]; struct _GUID
0x18008b2e8  mov     rcx, rax; this
0x18008b2eb  call    ??0CProtocolManager@@QEAA@U_GUID@@@Z; CProtocolManager::CProtocolManager(_GUID)
0x18008b2f0  nop
0x18008b2f1  mov     rdx, rax
0x18008b2f4  lea     rcx, [rsp+7B0h+var_778]
0x18008b2f9  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18008b2fe  mov     rdi, [rsp+7B0h+var_778]
0x18008b303  test    rdi, rdi
0x18008b306  jnz     short loc_18008B314
0x18008b308  lea     rdx, aNewCprotocolma; "new CProtocolManager failed: 0x%x in %s"
0x18008b30f  jmp     loc_18008B3C3
0x18008b314  mov     rax, [rdi]
0x18008b317  lea     r8, [rbp+6B0h+var_730]
0x18008b31b  mov     rdx, rsi
0x18008b31e  mov     rcx, rdi
0x18008b321  mov     rax, [rax+18h]
0x18008b325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b32a  mov     ebx, eax
0x18008b32c  test    eax, eax
0x18008b32e  jns     short loc_18008B33F
0x18008b330  mov     r8d, eax
0x18008b333  lea     rdx, aPtrprotocolmgr; "ptrProtocolMgr->Initialize failed: 0x%x"...
0x18008b33a  jmp     loc_18008B3CB
0x18008b33f  mov     qword ptr [rsp+7B0h+Buffer], rdi
0x18008b344  mov     [rsp+7B0h+NewElement], 0
0x18008b349  lea     r9, [rsp+7B0h+NewElement]; NewElement
0x18008b34e  mov     r8d, 8; BufferSize
0x18008b354  lea     rdx, [rsp+7B0h+Buffer]; Buffer
0x18008b359  mov     rcx, r14; Table
0x18008b35c  call    cs:__imp_RtlInsertElementGenericTable
0x18008b363  nop     dword ptr [rax+rax+00h]
0x18008b368  test    rax, rax
0x18008b36b  jz      short loc_18008B3BC
0x18008b36d  mov     rcx, qword ptr [rsp+7B0h+Buffer]
0x18008b372  mov     rax, [rcx]
0x18008b375  mov     rax, [rax+8]
0x18008b379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b37e  lea     rcx, [rsp+7B0h+var_758]; this
0x18008b383  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008b388  mov     rax, [rdi]
0x18008b38b  mov     rcx, [rsp+7B0h+var_760]
0x18008b390  mov     [rsp+7B0h+var_790], rcx
0x18008b395  mov     r9, r13
0x18008b398  mov     r8, r12
0x18008b39b  mov     rdx, r15
0x18008b39e  mov     rcx, rdi
0x18008b3a1  mov     rax, [rax+20h]
0x18008b3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b3aa  mov     ebx, eax
0x18008b3ac  test    eax, eax
0x18008b3ae  jns     short loc_18008B3DD
0x18008b3b0  mov     r8d, eax
0x18008b3b3  lea     rdx, aPtrprotocolmgr_0; "ptrProtocolMgr->CreateListener failed: "...
0x18008b3ba  jmp     short loc_18008B3CB
0x18008b3bc  lea     rdx, aThisProtocolmg; "this->ProtocolMgrList.Add failed: 0x%x "...
0x18008b3c3  mov     ebx, 8007000Eh
0x18008b3c8  mov     r8d, ebx
0x18008b3cb  lea     r9, aCprotocolexmgr_15; "CProtocolExMgr::CreateListener"
0x18008b3d2  mov     ecx, 8; int
0x18008b3d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008b3dc  nop
0x18008b3dd  lea     rcx, [rsp+7B0h+var_758]; this
0x18008b3e2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18008b3e7  nop
0x18008b3e8  lea     rcx, [rsp+7B0h+var_778]; void *
0x18008b3ed  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008b3f2  nop
0x18008b3f3  lea     rcx, [rbp+6B0h+var_6A0]; this
0x18008b3f7  call    ??1CProtocolManager@@UEAA@XZ; CProtocolManager::~CProtocolManager(void)
0x18008b3fc  mov     eax, ebx
0x18008b3fe  mov     rcx, [rbp+6B0h+var_50]
0x18008b405  xor     rcx, rsp; StackCookie
0x18008b408  call    __security_check_cookie
0x18008b40d  add     rsp, 778h
0x18008b414  pop     r15
0x18008b416  pop     r14
0x18008b418  pop     r13
0x18008b41a  pop     r12
0x18008b41c  pop     rdi
0x18008b41d  pop     rsi
0x18008b41e  pop     rbx
0x18008b41f  pop     rbp
0x18008b420  retn
```
