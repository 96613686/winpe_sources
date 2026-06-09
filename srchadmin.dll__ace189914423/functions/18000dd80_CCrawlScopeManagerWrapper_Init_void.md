# CCrawlScopeManagerWrapper::Init(void)

- ea: `0x18000dd80`
- end: `0x18000de74`
- name: `?Init@CCrawlScopeManagerWrapper@@QEAAJXZ`
- size: `244`
- prototype: `__int64 __fastcall(struct IUnknown **this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002270`
- `0x180025fac`
- `0x1800277ac`
- `0x180027abc`

## callees

- `0x1800038ac`
- `0x18000d530`
- `0x18000dd80`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000de50`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000de50`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ddb7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ddb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCrawlScopeManagerWrapper::Init(struct IUnknown **this)
{
  struct IUnknown *v2; // rdx
  HRESULT v3; // edi
  struct IUnknown *v4; // rdx
  LPVOID v6; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  v3 = CoCreateInstance(&CLSID_CSearchManager, 0, 0x15u, &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69, &v6);
  if ( v3 >= 0 )
  {
    if ( this[1] )
      ATL::AtlComPtrAssign(this + 1, v2);
    v3 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, struct IUnknown **))(*(_QWORD *)v6 + 80LL))(
           v6,
           L"SystemIndex",
           this + 1);
    if ( v3 >= 0 )
    {
      if ( *this )
        ATL::AtlComPtrAssign(this, v4);
      v3 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))this[1]->lpVtbl[9].AddRef)(this[1], this);
      if ( v3 >= 0 )
        v3 = CoSetProxyBlanket(*this, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000dd80  mov     r11, rsp
0x18000dd83  mov     [r11+8], rbx
0x18000dd87  mov     [r11+18h], rsi
0x18000dd8b  push    rdi
0x18000dd8c  sub     rsp, 40h
0x18000dd90  mov     rbx, rcx
0x18000dd93  mov     qword ptr [r11+10h], 0
0x18000dd9b  lea     rax, [r11+10h]
0x18000dd9f  mov     [r11-28h], rax
0x18000dda3  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18000ddaa  xor     edx, edx; pUnkOuter
0x18000ddac  lea     r8d, [rdx+15h]; dwClsContext
0x18000ddb0  lea     rcx, CLSID_CSearchManager; rclsid
0x18000ddb7  call    cs:__imp_CoCreateInstance
0x18000ddbd  mov     edi, eax
0x18000ddbf  test    eax, eax
0x18000ddc1  js      loc_18000DE58
0x18000ddc7  lea     rsi, [rbx+8]
0x18000ddcb  cmp     qword ptr [rsi], 0
0x18000ddcf  jz      short loc_18000DDD9
0x18000ddd1  mov     rcx, rsi; struct IUnknown **
0x18000ddd4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000ddd9  mov     rcx, [rsp+48h+arg_8]
0x18000ddde  mov     rax, [rcx]
0x18000dde1  mov     r8, rsi
0x18000dde4  lea     rdx, aSystemindex; "SystemIndex"
0x18000ddeb  mov     rax, [rax+50h]
0x18000ddef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf4  mov     edi, eax
0x18000ddf6  test    eax, eax
0x18000ddf8  js      short loc_18000DE58
0x18000ddfa  cmp     qword ptr [rbx], 0
0x18000ddfe  jz      short loc_18000DE08
0x18000de00  mov     rcx, rbx; struct IUnknown **
0x18000de03  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000de08  mov     rcx, [rsi]
0x18000de0b  mov     rax, [rcx]
0x18000de0e  mov     rdx, rbx
0x18000de11  mov     rax, [rax+0E0h]
0x18000de18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1d  mov     edi, eax
0x18000de1f  test    eax, eax
0x18000de21  js      short loc_18000DE58
0x18000de23  mov     [rsp+48h+dwCapabilities], 0; dwCapabilities
0x18000de2b  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x18000de34  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18000de3c  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x18000de44  xor     r9d, r9d; pServerPrincName
0x18000de47  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000de4a  mov     r8d, edx; dwAuthzSvc
0x18000de4d  mov     rcx, [rbx]; pProxy
0x18000de50  call    cs:__imp_CoSetProxyBlanket
0x18000de56  mov     edi, eax
0x18000de58  lea     rcx, [rsp+48h+arg_8]
0x18000de5d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000de62  mov     eax, edi
0x18000de64  mov     rbx, [rsp+48h+arg_0]
0x18000de69  mov     rsi, [rsp+48h+arg_10]
0x18000de6e  add     rsp, 40h
0x18000de72  pop     rdi
0x18000de73  retn
```
