# CHMESharedLibraryMonitor::~CHMESharedLibraryMonitor(void)

- ea: `0x14008aac0`
- end: `0x14008ab44`
- name: `??1CHMESharedLibraryMonitor@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004b158`
- `0x14009bfab`

## callees

- `0x140008eac`
- `0x14003e46c`
- `0x140045988`
- `0x14008a9d8`
- `0x14008aac0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14008aaec`
- `KERNEL32!WaitForSingleObject` at `0x14008aaec`
- `KERNEL32!SetEvent` at `0x14008aadc`
- `KERNEL32!SetEvent` at `0x14008aadc`
- `KERNEL32!DeleteCriticalSection` at `0x14008ab0f`
- `KERNEL32!DeleteCriticalSection` at `0x14008ab0f`
- `KERNEL32!CloseHandle` at `0x14008aaf9`
- `KERNEL32!CloseHandle` at `0x14008ab06`
- `KERNEL32!CloseHandle` at `0x14008aaf9`
- `KERNEL32!CloseHandle` at `0x14008ab06`

## pseudocode

```c
void __fastcall CHMESharedLibraryMonitor::~CHMESharedLibraryMonitor(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  LOBYTE(lpCriticalSection[4].OwningThread) = 1;
  DebugInfo = lpCriticalSection[4].DebugInfo;
  if ( DebugInfo )
  {
    SetEvent(DebugInfo);
    WaitForSingleObject(*(HANDLE *)&lpCriticalSection[4].LockCount, 0xFFFFFFFF);
    CloseHandle(*(HANDLE *)&lpCriticalSection[4].LockCount);
    CloseHandle(lpCriticalSection[4].DebugInfo);
  }
  DeleteCriticalSection(lpCriticalSection);
  ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::~CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>((__int64)&lpCriticalSection[4].LockSemaphore);
  ATL::CRegKey::Close((ATL::CRegKey *)&lpCriticalSection[3].OwningThread);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::~CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>(&lpCriticalSection[2].LockCount);
  ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::~CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>(&lpCriticalSection[1]);
}

```

## disassembly

```asm
0x14008aac0  push    rbx
0x14008aac2  sub     rsp, 20h
0x14008aac6  mov     rbx, rcx
0x14008aac9  mov     byte ptr [rcx+0B0h], 1
0x14008aad0  mov     rcx, [rcx+0A0h]; hEvent
0x14008aad7  test    rcx, rcx
0x14008aada  jz      short loc_14008AB0C
0x14008aadc  call    cs:__imp_SetEvent
0x14008aae2  mov     rcx, [rbx+0A8h]; hHandle
0x14008aae9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14008aaec  call    cs:__imp_WaitForSingleObject
0x14008aaf2  mov     rcx, [rbx+0A8h]; hObject
0x14008aaf9  call    cs:__imp_CloseHandle
0x14008aaff  mov     rcx, [rbx+0A0h]; hObject
0x14008ab06  call    cs:__imp_CloseHandle
0x14008ab0c  mov     rcx, rbx; lpCriticalSection
0x14008ab0f  call    cs:__imp_DeleteCriticalSection
0x14008ab15  lea     rcx, [rbx+0B8h]
0x14008ab1c  call    ??1?$CAtlArray@V?$CComQIPtr@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryPathEventHandler@@$1?_GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b@@3U__s_GUID@@B@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>::~CAtlArray<ATL::CComQIPtr<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>,ATL::CComQIPtrElementTraits<IHMELibraryPathEventHandler,&__s_GUID const _GUID_ad2c05eb_40d6_46f4_a158_610b27d6e14b>>(void)
0x14008ab21  lea     rcx, [rbx+88h]; this
0x14008ab28  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14008ab2d  lea     rcx, [rbx+58h]
0x14008ab31  call    ??1?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@ULibraryParams@CHMESharedLibraryMonitor@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@ULibraryParams@CHMESharedLibraryMonitor@@@2@@ATL@@QEAA@XZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>::~CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CHMESharedLibraryMonitor::LibraryParams,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<CHMESharedLibraryMonitor::LibraryParams>>(void)
0x14008ab36  lea     rcx, [rbx+28h]
0x14008ab3a  add     rsp, 20h
0x14008ab3e  pop     rbx
0x14008ab3f  jmp     ??1?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAA@XZ; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::~CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>(void)
```
