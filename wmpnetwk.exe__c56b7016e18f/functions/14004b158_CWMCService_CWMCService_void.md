# CWMCService::~CWMCService(void)

- ea: `0x14004b158`
- end: `0x14004b2a7`
- name: `??1CWMCService@@UEAA@XZ`
- size: `335`
- prototype: `void __fastcall(CWMCService *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400479b0`
- `0x14004b580`

## callees

- `0x1400028cc`
- `0x140024688`
- `0x14003a8ec`
- `0x140047798`
- `0x140048258`
- `0x14004b158`
- `0x1400518a8`
- `0x140053b70`
- `0x14008aac0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14004b1ac`
- `KERNEL32!DeleteCriticalSection` at `0x14004b246`
- `KERNEL32!DeleteCriticalSection` at `0x14004b28f`
- `KERNEL32!DeleteCriticalSection` at `0x14004b1ac`
- `KERNEL32!DeleteCriticalSection` at `0x14004b246`
- `KERNEL32!DeleteCriticalSection` at `0x14004b28f`
- `KERNEL32!CloseHandle` at `0x14004b1f0`
- `KERNEL32!CloseHandle` at `0x14004b1f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CWMCService::~CWMCService(CWMCService *this)
{
  *(_QWORD *)this = &CWMCService::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  CWMCService::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( *((_QWORD *)this + 80) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    }
    CloseHandle(*((HANDLE *)this + 80));
    *((_QWORD *)this + 80) = 0;
  }
  g_WMCService = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 86);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 648));
  CHMESharedLibraryMonitor::~CHMESharedLibraryMonitor((LPCRITICAL_SECTION)((char *)this + 368));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 45);
  ShellAggregateResultItem::~ShellAggregateResultItem((CWMCService *)((char *)this + 352));
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAll((char *)this + 272);
  ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::RemoveAll((char *)this + 184);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  CNTService::~CNTService(this);
}

```

## disassembly

```asm
0x14004b158  mov     [rsp+arg_0], rbx
0x14004b15d  push    rsi
0x14004b15e  sub     rsp, 20h
0x14004b162  mov     rbx, rcx
0x14004b165  lea     rax, ??_7CWMCService@@6B@; const CWMCService::`vftable'
0x14004b16c  mov     [rcx], rax
0x14004b16f  lea     rsi, WPP_GLOBAL_Control
0x14004b176  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b17d  cmp     rcx, rsi
0x14004b180  jz      short loc_14004B19D
0x14004b182  test    byte ptr [rcx+1Ch], 1
0x14004b186  jz      short loc_14004B19D
0x14004b188  mov     edx, 3Bh ; ';'
0x14004b18d  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b194  mov     rcx, [rcx+10h]
0x14004b198  call    WPP_SF_
0x14004b19d  mov     rcx, rbx; this
0x14004b1a0  call    ?Shutdown@CWMCService@@AEAAXXZ; CWMCService::Shutdown(void)
0x14004b1a5  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x14004b1ac  call    cs:__imp_DeleteCriticalSection
0x14004b1b2  cmp     qword ptr [rbx+280h], 0
0x14004b1ba  jz      short loc_14004B201
0x14004b1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b1c3  cmp     rcx, rsi
0x14004b1c6  jz      short loc_14004B1E9
0x14004b1c8  test    byte ptr [rcx+1Ch], 2
0x14004b1cc  jz      short loc_14004B1E9
0x14004b1ce  cmp     byte ptr [rcx+19h], 5
0x14004b1d2  jb      short loc_14004B1E9
0x14004b1d4  mov     edx, 3Ch ; '<'
0x14004b1d9  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b1e0  mov     rcx, [rcx+10h]
0x14004b1e4  call    WPP_SF_
0x14004b1e9  mov     rcx, [rbx+280h]; hObject
0x14004b1f0  call    cs:__imp_CloseHandle
0x14004b1f6  mov     qword ptr [rbx+280h], 0
0x14004b201  mov     cs:g_WMCService, 0
0x14004b20c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b213  cmp     rcx, rsi
0x14004b216  jz      short loc_14004B233
0x14004b218  test    byte ptr [rcx+1Ch], 1
0x14004b21c  jz      short loc_14004B233
0x14004b21e  mov     edx, 3Dh ; '='
0x14004b223  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14004b22a  mov     rcx, [rcx+10h]
0x14004b22e  call    WPP_SF_
0x14004b233  lea     rcx, [rbx+2B0h]
0x14004b23a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004b23f  lea     rcx, [rbx+288h]; lpCriticalSection
0x14004b246  call    cs:__imp_DeleteCriticalSection
0x14004b24c  lea     rcx, [rbx+170h]; lpCriticalSection
0x14004b253  call    ??1CHMESharedLibraryMonitor@@QEAA@XZ; CHMESharedLibraryMonitor::~CHMESharedLibraryMonitor(void)
0x14004b258  lea     rcx, [rbx+168h]
0x14004b25f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004b264  lea     rcx, [rbx+160h]; this
0x14004b26b  call    ??1ShellAggregateResultItem@@QEAA@XZ; ShellAggregateResultItem::~ShellAggregateResultItem(void)
0x14004b270  lea     rcx, [rbx+110h]
0x14004b277  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::RemoveAll(void)
0x14004b27c  lea     rcx, [rbx+0B8h]
0x14004b283  call    ?RemoveAll@?$CAtlList@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCSecurityNotification@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComPtr<IWMCSecurityNotification>,ATL::CElementTraits<ATL::CComPtr<IWMCSecurityNotification>>>::RemoveAll(void)
0x14004b288  lea     rcx, [rbx+90h]; lpCriticalSection
0x14004b28f  call    cs:__imp_DeleteCriticalSection
0x14004b295  mov     rcx, rbx; this
0x14004b298  mov     rbx, [rsp+28h+arg_0]
0x14004b29d  add     rsp, 20h
0x14004b2a1  pop     rsi
0x14004b2a2  jmp     ??1CNTService@@UEAA@XZ; CNTService::~CNTService(void)
```
