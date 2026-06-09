# WFDSConMgr::CInfraCastHelper::~CInfraCastHelper(void)

- ea: `0x180037f18`
- end: `0x180037fc1`
- name: `??1CInfraCastHelper@WFDSConMgr@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(WFDSConMgr::CInfraCastHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800389f0`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x1800069d0`
- `0x180036dcc`
- `0x180037f18`
- `0x18005dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037f5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180037f5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CInfraCastHelper::~CInfraCastHelper(WFDSConMgr::CInfraCastHelper *this)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx

  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>((_QWORD *)this + 21);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 19);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 17);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 15);
  WFDSConMgr::CEventWrapper::~CEventWrapper((void **)this + 14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<WFDSConMgr::CFirewallConfigurationToken>>>(
      v2,
      *((_QWORD *)this + 6));
    std::_Deallocate<16>(
      *((_QWORD **)this + 5),
      (*((_QWORD *)this + 7) - *((_QWORD *)this + 5)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
  }
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
}

```

## disassembly

```asm
0x180037f18  push    rbx
0x180037f1a  sub     rsp, 20h
0x180037f1e  mov     rbx, rcx
0x180037f21  add     rcx, 0A8h
0x180037f28  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x180037f2d  lea     rcx, [rbx+98h]; this
0x180037f34  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180037f39  lea     rcx, [rbx+88h]; this
0x180037f40  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180037f45  lea     rcx, [rbx+78h]; this
0x180037f49  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180037f4e  lea     rcx, [rbx+70h]; this
0x180037f52  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180037f57  lea     rcx, [rbx+48h]; lpCriticalSection
0x180037f5b  call    cs:__imp_DeleteCriticalSection
0x180037f61  mov     rcx, [rbx+28h]
0x180037f65  test    rcx, rcx
0x180037f68  jz      short loc_180037F9F
0x180037f6a  mov     rdx, [rbx+30h]
0x180037f6e  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VCFirewallConfigurationToken@WFDSConMgr@@U?$default_delete@VCFirewallConfigurationToken@WFDSConMgr@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VCFirewallConfigurationToken@WFDSConMgr@@U?$default_delete@VCFirewallConfigurationToken@WFDSConMgr@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VCFirewallConfigurationToken@WFDSConMgr@@U?$default_delete@VCFirewallConfigurationToken@WFDSConMgr@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<WFDSConMgr::CFirewallConfigurationToken>>>(std::unique_ptr<WFDSConMgr::CFirewallConfigurationToken> *,std::unique_ptr<WFDSConMgr::CFirewallConfigurationToken> * const,std::allocator<std::unique_ptr<WFDSConMgr::CFirewallConfigurationToken>> &)
0x180037f73  mov     rcx, [rbx+28h]
0x180037f77  mov     rdx, [rbx+38h]
0x180037f7b  sub     rdx, rcx
0x180037f7e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180037f82  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180037f87  mov     qword ptr [rbx+28h], 0
0x180037f8f  mov     qword ptr [rbx+30h], 0
0x180037f97  mov     qword ptr [rbx+38h], 0
0x180037f9f  mov     rcx, [rbx+20h]; this
0x180037fa3  test    rcx, rcx
0x180037fa6  jz      short loc_180037FAD
0x180037fa8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037fad  mov     rcx, [rbx+10h]; this
0x180037fb1  test    rcx, rcx
0x180037fb4  jz      short loc_180037FBB
0x180037fb6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180037fbb  add     rsp, 20h
0x180037fbf  pop     rbx
0x180037fc0  retn
```
