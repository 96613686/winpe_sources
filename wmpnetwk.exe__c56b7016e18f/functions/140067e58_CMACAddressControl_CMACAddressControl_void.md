# CMACAddressControl::~CMACAddressControl(void)

- ea: `0x140067e58`
- end: `0x140067f56`
- name: `??1CMACAddressControl@@QEAA@XZ`
- size: `254`
- prototype: `void __fastcall(CMACAddressControl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400694f0`

## callees

- `0x14000dd98`
- `0x14003c324`
- `0x140047798`
- `0x1400518a8`
- `0x140067df4`
- `0x140067e58`
- `0x140097244`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140067eac`
- `KERNEL32!DeleteCriticalSection` at `0x140067eb6`
- `KERNEL32!DeleteCriticalSection` at `0x140067ef6`
- `KERNEL32!DeleteCriticalSection` at `0x140067f03`
- `KERNEL32!DeleteCriticalSection` at `0x140067f3d`
- `KERNEL32!DeleteCriticalSection` at `0x140067eac`
- `KERNEL32!DeleteCriticalSection` at `0x140067eb6`
- `KERNEL32!DeleteCriticalSection` at `0x140067ef6`
- `KERNEL32!DeleteCriticalSection` at `0x140067f03`
- `KERNEL32!DeleteCriticalSection` at `0x140067f3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMACAddressControl::~CMACAddressControl(CMACAddressControl *this)
{
  *(_QWORD *)this = &CMACAddressControl::`vftable'{for `ATL::IWorkerThreadClient'};
  *((_QWORD *)this + 1) = &CMACAddressControl::`vftable'{for `IUnknown'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids);
  ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::RemoveAll((char *)this + 568);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CMACAddressControl::_DRM_DEVICE_CACHE_INFO *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<CMACAddressControl::_DRM_DEVICE_CACHE_INFO *>>::RemoveAll((char *)this + 416);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CMACAddressControl::_DRM_DEVICE_CACHE_INFO *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<CMACAddressControl::_DRM_DEVICE_CACHE_INFO *>>::RemoveAll((char *)this + 344);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::RemoveAll((char *)this + 272);
  ATL::CWorkerThread<ATL::Win32ThreadTraits>::~CWorkerThread<ATL::Win32ThreadTraits>((__int64)this + 160);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  CEventsDB::~CEventsDB((CMACAddressControl *)((char *)this + 24));
}

```

## disassembly

```asm
0x140067e58  mov     [rsp+arg_0], rbx
0x140067e5d  push    rdi
0x140067e5e  sub     rsp, 20h
0x140067e62  lea     rax, ??_7CMACAddressControl@@6BIWorkerThreadClient@ATL@@@; const CMACAddressControl::`vftable'{for `ATL::IWorkerThreadClient'}
0x140067e69  mov     rbx, rcx
0x140067e6c  mov     [rcx], rax
0x140067e6f  lea     rax, ??_7CMACAddressControl@@6BIUnknown@@@; const CMACAddressControl::`vftable'{for `IUnknown'}
0x140067e76  mov     [rcx+8], rax
0x140067e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e81  lea     rdi, WPP_GLOBAL_Control
0x140067e88  cmp     rcx, rdi
0x140067e8b  jz      short loc_140067EA8
0x140067e8d  test    byte ptr [rcx+1Ch], 1
0x140067e91  jz      short loc_140067EA8
0x140067e93  mov     rcx, [rcx+10h]
0x140067e97  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x140067e9e  mov     edx, 16h
0x140067ea3  call    WPP_SF_
0x140067ea8  lea     rcx, [rbx+28h]; lpCriticalSection
0x140067eac  call    cs:__imp_DeleteCriticalSection
0x140067eb2  lea     rcx, [rbx+50h]; lpCriticalSection
0x140067eb6  call    cs:__imp_DeleteCriticalSection
0x140067ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ec3  cmp     rcx, rdi
0x140067ec6  jz      short loc_140067EE3
0x140067ec8  test    byte ptr [rcx+1Ch], 1
0x140067ecc  jz      short loc_140067EE3
0x140067ece  mov     rcx, [rcx+10h]
0x140067ed2  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x140067ed9  mov     edx, 17h
0x140067ede  call    WPP_SF_
0x140067ee3  lea     rcx, [rbx+238h]
0x140067eea  call    ?RemoveAll@?$CAtlList@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::RemoveAll(void)
0x140067eef  lea     rcx, [rbx+210h]; lpCriticalSection
0x140067ef6  call    cs:__imp_DeleteCriticalSection
0x140067efc  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x140067f03  call    cs:__imp_DeleteCriticalSection
0x140067f09  lea     rcx, [rbx+1A0h]
0x140067f10  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAU_DRM_DEVICE_CACHE_INFO@CMACAddressControl@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAU_DRM_DEVICE_CACHE_INFO@CMACAddressControl@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CMACAddressControl::_DRM_DEVICE_CACHE_INFO *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<CMACAddressControl::_DRM_DEVICE_CACHE_INFO *>>::RemoveAll(void)
0x140067f15  lea     rcx, [rbx+158h]
0x140067f1c  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAU_DRM_DEVICE_CACHE_INFO@CMACAddressControl@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAU_DRM_DEVICE_CACHE_INFO@CMACAddressControl@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CMACAddressControl::_DRM_DEVICE_CACHE_INFO *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<CMACAddressControl::_DRM_DEVICE_CACHE_INFO *>>::RemoveAll(void)
0x140067f21  lea     rcx, [rbx+110h]
0x140067f28  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::RemoveAll(void)
0x140067f2d  lea     rcx, [rbx+0A0h]
0x140067f34  call    ??1?$CWorkerThread@VWin32ThreadTraits@ATL@@@ATL@@QEAA@XZ; ATL::CWorkerThread<ATL::Win32ThreadTraits>::~CWorkerThread<ATL::Win32ThreadTraits>(void)
0x140067f39  lea     rcx, [rbx+78h]; lpCriticalSection
0x140067f3d  call    cs:__imp_DeleteCriticalSection
0x140067f43  lea     rcx, [rbx+18h]; this
0x140067f47  mov     rbx, [rsp+28h+arg_0]
0x140067f4c  add     rsp, 20h
0x140067f50  pop     rdi
0x140067f51  jmp     ??1CEventsDB@@QEAA@XZ; CEventsDB::~CEventsDB(void)
```
