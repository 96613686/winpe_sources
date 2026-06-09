# COfflineSync::EnumSyncMgrItems(ISyncMgrEnumItems * *)

- ea: `0x180011080`
- end: `0x180011132`
- name: `?EnumSyncMgrItems@COfflineSync@@UEAAJPEAPEAUISyncMgrEnumItems@@@Z`
- size: `178`
- prototype: `int(COfflineSync *__hidden this, struct ISyncMgrEnumItems **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010d8c`
- `0x180011080`
- `0x180011354`
- `0x18001ba08`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800110c3`
- `ole32!CoCreateInstance` at `0x1800110c3`

## pseudocode

```c
__int64 __fastcall COfflineSync::EnumSyncMgrItems(COfflineSync *this, struct ISyncMgrEnumItems **a2)
{
  struct ISubscriptionMgr2 **v5; // rdi
  HRESULT Instance; // ebx
  COfflineEnum *v7; // rax
  COfflineEnum *v8; // r14

  if ( !a2 )
    return 2147942487LL;
  v5 = (struct ISubscriptionMgr2 **)((char *)this + 32);
  if ( *((_QWORD *)this + 4)
    || (Instance = CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr2, (LPVOID *)this + 4),
        Instance >= 0) )
  {
    v7 = (COfflineEnum *)operator new(0x20u);
    if ( v7 && (v8 = COfflineEnum::COfflineEnum(v7)) != 0 )
    {
      Instance = COfflineEnum::Init(
                   v8,
                   *v5,
                   *((_DWORD *)this + 17),
                   *((const struct _GUID **)this + 10),
                   a2,
                   *((_DWORD *)this + 10));
      (*(void (__fastcall **)(COfflineEnum *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180011080  push    rbx
0x180011082  push    rbp
0x180011083  push    rsi
0x180011084  push    rdi
0x180011085  push    r14
0x180011087  sub     rsp, 30h
0x18001108b  mov     rbp, rdx
0x18001108e  mov     rsi, rcx
0x180011091  test    rdx, rdx
0x180011094  jnz     short loc_1800110A0
0x180011096  mov     eax, 80070057h
0x18001109b  jmp     loc_180011127
0x1800110a0  lea     rdi, [rcx+20h]
0x1800110a4  cmp     qword ptr [rdi], 0
0x1800110a8  jnz     short loc_1800110CF
0x1800110aa  xor     edx, edx; pUnkOuter
0x1800110ac  mov     [rsp+58h+ppv], rdi; ppv
0x1800110b1  lea     r9, IID_ISubscriptionMgr2; riid
0x1800110b8  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x1800110bf  lea     r8d, [rdx+1]; dwClsContext
0x1800110c3  call    cs:__imp_CoCreateInstance
0x1800110c9  mov     ebx, eax
0x1800110cb  test    eax, eax
0x1800110cd  js      short loc_180011125
0x1800110cf  mov     ecx, 20h ; ' '; dwBytes
0x1800110d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110d9  test    rax, rax
0x1800110dc  jz      short loc_180011120
0x1800110de  mov     rcx, rax; this
0x1800110e1  call    ??0COfflineEnum@@QEAA@XZ; COfflineEnum::COfflineEnum(void)
0x1800110e6  mov     r14, rax
0x1800110e9  test    rax, rax
0x1800110ec  jz      short loc_180011120
0x1800110ee  mov     eax, [rsi+28h]
0x1800110f1  mov     rcx, r14; this
0x1800110f4  mov     r9, [rsi+50h]; struct _GUID *
0x1800110f8  mov     r8d, [rsi+44h]; unsigned int
0x1800110fc  mov     rdx, [rdi]; struct ISubscriptionMgr2 *
0x1800110ff  mov     [rsp+58h+var_30], eax; unsigned int
0x180011103  mov     [rsp+58h+ppv], rbp; struct ISyncMgrEnumItems **
0x180011108  call    ?Init@COfflineEnum@@QEAAJPEAUISubscriptionMgr2@@KPEBU_GUID@@PEAPEAUISyncMgrEnumItems@@K@Z; COfflineEnum::Init(ISubscriptionMgr2 *,ulong,_GUID const *,ISyncMgrEnumItems * *,ulong)
0x18001110d  mov     rcx, [r14]
0x180011110  mov     ebx, eax
0x180011112  mov     rax, [rcx+10h]
0x180011116  mov     rcx, r14
0x180011119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111e  jmp     short loc_180011125
0x180011120  mov     ebx, 8007000Eh
0x180011125  mov     eax, ebx
0x180011127  add     rsp, 30h
0x18001112b  pop     r14
0x18001112d  pop     rdi
0x18001112e  pop     rsi
0x18001112f  pop     rbp
0x180011130  pop     rbx
0x180011131  retn
```
