# LocationDataSource::Initialize(void)

- ea: `0x1800116bc`
- end: `0x1800117c3`
- name: `?Initialize@LocationDataSource@@AEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(LocationDataSource *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010784`
- `0x180012628`

## callees

- `0x1800011e4`
- `0x18000166c`
- `0x180006844`
- `0x18000885c`
- `0x1800116bc`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800116f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800116f3`

## string_xrefs

- `0x180011704`: `onecore\base\win32\winnls\tzautoupdate\locationdatasource.cpp`

## pseudocode

```c
__int64 __fastcall LocationDataSource::Initialize(LocationDataSource *this)
{
  LPVOID *v1; // rdi
  HRESULT Instance; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  LPVOID v11; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  _QWORD v13[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF

  v1 = (LPVOID *)((char *)this + 24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 24);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, v1);
  v6 = Instance;
  if ( Instance >= 0 )
  {
    if ( (unsigned int)dword_180030000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
      {
        v16 = 0x1000000;
        v15 = L"LocationDataSource Initialized";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v8,
          (__int64)&byte_18002909F,
          v9,
          v10,
          (__int64)&v16,
          &v15);
      }
    }
    v11 = *v1;
    v13[0] = 0;
    v13[1] = this;
    return (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *, int, _QWORD))(*(_QWORD *)v11 + 24LL))(
             v11,
             LocationDataSource::InitializeInDisconnectableContext,
             v13,
             &IID_IContextCallback,
             5,
             0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\locationdatasource.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    return v6;
  }
}

```

## disassembly

```asm
0x1800116bc  mov     [rsp+arg_10], rbx
0x1800116c1  mov     [rsp+arg_18], rsi
0x1800116c6  push    rdi
0x1800116c7  sub     rsp, 50h
0x1800116cb  lea     rdi, [rcx+18h]
0x1800116cf  mov     rsi, rcx
0x1800116d2  mov     rcx, rdi
0x1800116d5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800116da  xor     edx, edx; pUnkOuter
0x1800116dc  mov     [rsp+58h+ppv], rdi; int
0x1800116e1  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800116e8  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800116ef  lea     r8d, [rdx+1]; dwClsContext
0x1800116f3  call    cs:__imp_CoCreateInstance
0x1800116f9  mov     ebx, eax
0x1800116fb  test    eax, eax
0x1800116fd  jns     short loc_18001171F
0x1800116ff  mov     rcx, [rsp+58h]; this
0x180011704  lea     r8, aOnecoreBaseWin_5; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18001170b  mov     r9d, eax; char *
0x18001170e  mov     edx, 52h ; 'R'; void *
0x180011713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011718  mov     eax, ebx
0x18001171a  jmp     loc_1800117B3
0x18001171f  mov     eax, cs:dword_180030000
0x180011725  cmp     eax, 5
0x180011728  jbe     short loc_180011772
0x18001172a  mov     rdx, 200000000000h
0x180011734  call    _tlgKeywordOn
0x180011739  test    al, al
0x18001173b  jz      short loc_180011772
0x18001173d  lea     rax, aLocationdataso; "LocationDataSource Initialized"
0x180011744  mov     [rsp+58h+arg_8], 1000000h
0x18001174d  mov     [rsp+58h+arg_0], rax
0x180011752  lea     rdx, byte_18002909F
0x180011759  lea     rax, [rsp+58h+arg_0]
0x18001175e  mov     [rsp+58h+var_30], rax
0x180011763  lea     rax, [rsp+58h+arg_8]
0x180011768  mov     [rsp+58h+ppv], rax
0x18001176d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180011772  mov     rcx, [rdi]
0x180011775  lea     r9, IID_IContextCallback
0x18001177c  mov     [rsp+58h+var_18], 0
0x180011785  lea     r8, [rsp+58h+var_18]
0x18001178a  mov     [rsp+58h+var_10], rsi
0x18001178f  lea     rdx, ?InitializeInDisconnectableContext@LocationDataSource@@CAJPEAUtagComCallData@@@Z; LocationDataSource::InitializeInDisconnectableContext(tagComCallData *)
0x180011796  mov     [rsp+58h+var_30], 0
0x18001179f  mov     rax, [rcx]
0x1800117a2  mov     dword ptr [rsp+58h+ppv], 5
0x1800117aa  mov     rax, [rax+18h]
0x1800117ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b3  mov     rbx, [rsp+58h+arg_10]
0x1800117b8  mov     rsi, [rsp+58h+arg_18]
0x1800117bd  add     rsp, 50h
0x1800117c1  pop     rdi
0x1800117c2  retn
```
