# CFSFolder::`vector deleting destructor'(uint)

- ea: `0x18009a9c0`
- end: `0x18009afd4`
- name: `??_ECFSFolder@@MEAAPEAXI@Z`
- size: `1556`
- prototype: `void *__fastcall(CFSFolder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180510930`

## callees

- `0x18009a9c0`
- `0x18009afdc`
- `0x18009b074`
- `0x1803a4cd4`
- `0x1803a4ce0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009acda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009af57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009acda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009af57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009abb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009abb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ad8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ad8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009abde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009abde`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ac41`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ac94`
- `OLEAUT32!__imp_SysFreeString` at `0x18009acf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ad01`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ac41`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ac94`
- `OLEAUT32!__imp_SysFreeString` at `0x18009acf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18009ad01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ace7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009adf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009af4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009abf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ac2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ace7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009adf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009af4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CFSFolder *__fastcall CFSFolder::`vector deleting destructor'(CFSFolder *this, char a2)
{
  DWORD LastError; // r12d
  void *v5; // rbp
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  HKEY v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  DWORD v25; // edi

  *(_QWORD *)this = &CFSFolder::`vftable'{for `CAggregatedUnknown'};
  *((_QWORD *)this + 4) = &CFSFolder::`vftable'{for `CObjectWithSite'};
  *((_QWORD *)this + 6) = &CFSFolder::`vftable'{for `IShellFolder2'};
  *((_QWORD *)this + 7) = &CFSFolder::`vftable'{for `IShellIcon'};
  *((_QWORD *)this + 8) = &CFSFolder::`vftable'{for `IShellIconOverlay'};
  *((_QWORD *)this + 9) = &CFSFolder::`vftable'{for `IPersistFolder3'};
  *((_QWORD *)this + 10) = &CFSFolder::`vftable'{for `IStorage'};
  *((_QWORD *)this + 11) = &CFSFolder::`vftable'{for `ILocalizableItemParent'};
  *((_QWORD *)this + 12) = &CFSFolder::`vftable'{for `IItemNameLimits'};
  *((_QWORD *)this + 13) = &CFSFolder::`vftable'{for `IContextMenuCB'};
  *((_QWORD *)this + 14) = &CFSFolder::`vftable'{for `ISetFolderEnumRestriction'};
  *((_QWORD *)this + 15) = &CFSFolder::`vftable'{for `ISetWrapperFolder'};
  *((_QWORD *)this + 16) = &CFSFolder::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 17) = &CFSFolder::`vftable'{for `IPersistPropertyBag'};
  *((_QWORD *)this + 18) = &CFSFolder::`vftable'{for `IParentAndItem'};
  *((_QWORD *)this + 19) = &CFSFolder::`vftable'{for `IDelegateFolder'};
  *((_QWORD *)this + 20) = &CFSFolder::`vftable'{for `IObjectProvider'};
  *((_QWORD *)this + 21) = &CFSFolder::`vftable'{for `IObjectWithBackReferences'};
  *((_QWORD *)this + 22) = &CFSFolder::`vftable'{for `IRemoteComputer'};
  *((_QWORD *)this + 23) = &CFSFolder::`vftable'{for `IThumbnailHandlerFactory'};
  *((_QWORD *)this + 24) = &CFSFolder::`vftable'{for `IContextMenuFactory'};
  *((_QWORD *)this + 25) = &CFSFolder::`vftable'{for `IFolderType'};
  *((_QWORD *)this + 26) = &CFSFolder::`vftable'{for `IExplorerPaneVisibility'};
  *((_QWORD *)this + 27) = &CFSFolder::`vftable'{for `IFolderWithViewPreferences'};
  *((_QWORD *)this + 28) = &CFSFolder::`vftable'{for `IFolderSetNameOf'};
  *((_QWORD *)this + 29) = &CFSFolder::`vftable'{for `IBackReferencedObject'};
  *((_QWORD *)this + 30) = &CFSFolder::`vftable'{for `IShellFolderPropertyInformation'};
  *((_QWORD *)this + 31) = &CFSFolder::`vftable'{for `IShellFolderItemFactory'};
  *((_QWORD *)this + 32) = &CFSFolder::`vftable'{for `IAliasedNamespace'};
  *((_QWORD *)this + 33) = &CFSFolder::`vftable'{for `IFolderWithSearchRoot'};
  *((_QWORD *)this + 34) = &CFSFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'};
  *((_QWORD *)this + 35) = &CFSFolder::`vftable'{for `IFolderWithElevationAttributes'};
  *((_QWORD *)this + 36) = &CFSFolder::`vftable'{for `IFolderWithJunctions'};
  *((_QWORD *)this + 37) = &CFSFolder::`vftable'{for `IPropertyInfoProvider'};
  *((_QWORD *)this + 38) = &CFSFolder::`vftable'{for `IColumnPreference'};
  *((_QWORD *)this + 39) = &CFSFolder::`vftable'{for `IFSFolderPriv'};
  *((_QWORD *)this + 40) = &CFSFolder::`vftable'{for `IObjectWithRegistryKey'};
  LastError = GetLastError();
  CoTaskMemFree(*((LPVOID *)this + 54));
  *((_QWORD *)this + 54) = 0;
  LocalFree(*((HLOCAL *)this + 58));
  *((_QWORD *)this + 58) = 0;
  CoTaskMemFree(*((LPVOID *)this + 59));
  *((_QWORD *)this + 59) = 0;
  CoTaskMemFree(*((LPVOID *)this + 60));
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 122) = -2;
  if ( (*((_BYTE *)this + 536) & 0x10) == 0 )
  {
    CoTaskMemFree(*((LPVOID *)this + 55));
    *((_QWORD *)this + 55) = 0;
    SysFreeString(*((BSTR *)this + 56));
    *((_QWORD *)this + 56) = 0;
    v5 = (void *)*((_QWORD *)this + 57);
    if ( v5 )
    {
      v25 = GetLastError();
      CoTaskMemFree(v5);
      SetLastError(v25);
    }
    *((_QWORD *)this + 57) = 0;
    *((_DWORD *)this + 123) = -1;
    *((_DWORD *)this + 134) &= ~0x200u;
    *((GUID *)this + 31) = GUID_NULL;
    *((_DWORD *)this + 130) = 0;
    SysFreeString(*((BSTR *)this + 66));
    *((_QWORD *)this + 66) = 0;
  }
  v6 = *((_QWORD *)this + 78);
  *((_QWORD *)this + 78) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 21) + 24LL))((char *)this + 168);
  SetLastError(LastError);
  CoTaskMemFree(*((LPVOID *)this + 55));
  SysFreeString(*((BSTR *)this + 56));
  SysFreeString(*((BSTR *)this + 66));
  v7 = *((_QWORD *)this + 77);
  *((_QWORD *)this + 77) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 81);
  *((_QWORD *)this + 81) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 82);
  *((_QWORD *)this + 82) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 113);
  *((_QWORD *)this + 113) = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = (HKEY)*((_QWORD *)this + 117);
  if ( v11 )
    RegCloseKey(v11);
  v12 = *((_QWORD *)this + 115);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  `eh vector destructor iterator'(
    (char *)this + 712,
    0x18u,
    8u,
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free);
  if ( *((_QWORD *)this + 87) )
  {
    CComTaskThread<CCscComTaskContext>::TerminateThread();
    CComTaskThread<CCscComTaskContext>::Release(*((void **)this + 87));
    *((_QWORD *)this + 87) = 0;
  }
  *((_QWORD *)this + 83) = &CComTaskContext::`vftable';
  v13 = (void *)*((_QWORD *)this + 57);
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = *((_QWORD *)this + 53);
  *((_QWORD *)this + 53) = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v15 = *((_QWORD *)this + 51);
  *((_QWORD *)this + 51) = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = *((_QWORD *)this + 50);
  *((_QWORD *)this + 50) = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = *((_QWORD *)this + 48);
  *((_QWORD *)this + 48) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = *((_QWORD *)this + 47);
  *((_QWORD *)this + 47) = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v19 = *((_QWORD *)this + 45);
  *((_QWORD *)this + 45) = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = *((_QWORD *)this + 44);
  *((_QWORD *)this + 44) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = *((_QWORD *)this + 42);
  *((_QWORD *)this + 42) = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  *((_QWORD *)this + 4) = &CObjectWithSite::`vftable';
  v23 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  *(_QWORD *)this = &CAggregatedUnknown::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x3B8);
  return this;
}

```

## disassembly

```asm
0x18009a9c0  push    rbx
0x18009a9c2  push    rbp
0x18009a9c3  push    rsi
0x18009a9c4  push    rdi
0x18009a9c5  push    r12
0x18009a9c7  push    r13
0x18009a9c9  push    r14
0x18009a9cb  push    r15
0x18009a9cd  sub     rsp, 28h
0x18009a9d1  mov     r13d, edx
0x18009a9d4  mov     rbx, rcx
0x18009a9d7  lea     rax, ??_7CFSFolder@@6BCAggregatedUnknown@@@; const CFSFolder::`vftable'{for `CAggregatedUnknown'}
0x18009a9de  mov     [rcx], rax
0x18009a9e1  lea     rax, ??_7CFSFolder@@6BCObjectWithSite@@@; const CFSFolder::`vftable'{for `CObjectWithSite'}
0x18009a9e8  mov     [rcx+20h], rax
0x18009a9ec  lea     rax, ??_7CFSFolder@@6BIShellFolder2@@@; const CFSFolder::`vftable'{for `IShellFolder2'}
0x18009a9f3  mov     [rcx+30h], rax
0x18009a9f7  lea     rax, ??_7CFSFolder@@6BIShellIcon@@@; const CFSFolder::`vftable'{for `IShellIcon'}
0x18009a9fe  mov     [rcx+38h], rax
0x18009aa02  lea     rax, ??_7CFSFolder@@6BIShellIconOverlay@@@; const CFSFolder::`vftable'{for `IShellIconOverlay'}
0x18009aa09  mov     [rcx+40h], rax
0x18009aa0d  lea     rax, ??_7CFSFolder@@6BIPersistFolder3@@@; const CFSFolder::`vftable'{for `IPersistFolder3'}
0x18009aa14  mov     [rcx+48h], rax
0x18009aa18  lea     rax, ??_7CFSFolder@@6BIStorage@@@; const CFSFolder::`vftable'{for `IStorage'}
0x18009aa1f  mov     [rcx+50h], rax
0x18009aa23  lea     rax, ??_7CFSFolder@@6BILocalizableItemParent@@@; const CFSFolder::`vftable'{for `ILocalizableItemParent'}
0x18009aa2a  mov     [rcx+58h], rax
0x18009aa2e  lea     rax, ??_7CFSFolder@@6BIItemNameLimits@@@; const CFSFolder::`vftable'{for `IItemNameLimits'}
0x18009aa35  mov     [rcx+60h], rax
0x18009aa39  lea     rax, ??_7CFSFolder@@6BIContextMenuCB@@@; const CFSFolder::`vftable'{for `IContextMenuCB'}
0x18009aa40  mov     [rcx+68h], rax
0x18009aa44  lea     rax, ??_7CFSFolder@@6BISetFolderEnumRestriction@@@; const CFSFolder::`vftable'{for `ISetFolderEnumRestriction'}
0x18009aa4b  mov     [rcx+70h], rax
0x18009aa4f  lea     rax, ??_7CFSFolder@@6BISetWrapperFolder@@@; const CFSFolder::`vftable'{for `ISetWrapperFolder'}
0x18009aa56  mov     [rcx+78h], rax
0x18009aa5a  lea     rax, ??_7CFSFolder@@6BIOleCommandTarget@@@; const CFSFolder::`vftable'{for `IOleCommandTarget'}
0x18009aa61  mov     [rcx+80h], rax
0x18009aa68  lea     rax, ??_7CFSFolder@@6BIPersistPropertyBag@@@; const CFSFolder::`vftable'{for `IPersistPropertyBag'}
0x18009aa6f  mov     [rcx+88h], rax
0x18009aa76  lea     rax, ??_7CFSFolder@@6BIParentAndItem@@@; const CFSFolder::`vftable'{for `IParentAndItem'}
0x18009aa7d  mov     [rcx+90h], rax
0x18009aa84  lea     rax, ??_7CFSFolder@@6BIDelegateFolder@@@; const CFSFolder::`vftable'{for `IDelegateFolder'}
0x18009aa8b  mov     [rcx+98h], rax
0x18009aa92  lea     rax, ??_7CFSFolder@@6BIObjectProvider@@@; const CFSFolder::`vftable'{for `IObjectProvider'}
0x18009aa99  mov     [rcx+0A0h], rax
0x18009aaa0  lea     rax, ??_7CFSFolder@@6BIObjectWithBackReferences@@@; const CFSFolder::`vftable'{for `IObjectWithBackReferences'}
0x18009aaa7  mov     [rcx+0A8h], rax
0x18009aaae  lea     rax, ??_7CFSFolder@@6BIRemoteComputer@@@; const CFSFolder::`vftable'{for `IRemoteComputer'}
0x18009aab5  mov     [rcx+0B0h], rax
0x18009aabc  lea     rax, ??_7CFSFolder@@6BIThumbnailHandlerFactory@@@; const CFSFolder::`vftable'{for `IThumbnailHandlerFactory'}
0x18009aac3  mov     [rcx+0B8h], rax
0x18009aaca  lea     rax, ??_7CFSFolder@@6BIContextMenuFactory@@@; const CFSFolder::`vftable'{for `IContextMenuFactory'}
0x18009aad1  mov     [rcx+0C0h], rax
0x18009aad8  lea     rax, ??_7CFSFolder@@6BIFolderType@@@; const CFSFolder::`vftable'{for `IFolderType'}
0x18009aadf  mov     [rcx+0C8h], rax
0x18009aae6  lea     rax, ??_7CFSFolder@@6BIExplorerPaneVisibility@@@; const CFSFolder::`vftable'{for `IExplorerPaneVisibility'}
0x18009aaed  mov     [rcx+0D0h], rax
0x18009aaf4  lea     rax, ??_7CFSFolder@@6BIFolderWithViewPreferences@@@; const CFSFolder::`vftable'{for `IFolderWithViewPreferences'}
0x18009aafb  mov     [rcx+0D8h], rax
0x18009ab02  lea     rax, ??_7CFSFolder@@6BIFolderSetNameOf@@@; const CFSFolder::`vftable'{for `IFolderSetNameOf'}
0x18009ab09  mov     [rcx+0E0h], rax
0x18009ab10  lea     rax, ??_7CFSFolder@@6BIBackReferencedObject@@@; const CFSFolder::`vftable'{for `IBackReferencedObject'}
0x18009ab17  mov     [rcx+0E8h], rax
0x18009ab1e  lea     rax, ??_7CFSFolder@@6BIShellFolderPropertyInformation@@@; const CFSFolder::`vftable'{for `IShellFolderPropertyInformation'}
0x18009ab25  mov     [rcx+0F0h], rax
0x18009ab2c  lea     rax, ??_7CFSFolder@@6BIShellFolderItemFactory@@@; const CFSFolder::`vftable'{for `IShellFolderItemFactory'}
0x18009ab33  mov     [rcx+0F8h], rax
0x18009ab3a  lea     rax, ??_7CFSFolder@@6BIAliasedNamespace@@@; const CFSFolder::`vftable'{for `IAliasedNamespace'}
0x18009ab41  mov     [rcx+100h], rax
0x18009ab48  lea     rax, ??_7CFSFolder@@6BIFolderWithSearchRoot@@@; const CFSFolder::`vftable'{for `IFolderWithSearchRoot'}
0x18009ab4f  mov     [rcx+108h], rax
0x18009ab56  lea     rax, ??_7CFSFolder@@6BINameSpaceTreeControlFolderCapabilities@@@; const CFSFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'}
0x18009ab5d  mov     [rcx+110h], rax
0x18009ab64  lea     rax, ??_7CFSFolder@@6BIFolderWithElevationAttributes@@@; const CFSFolder::`vftable'{for `IFolderWithElevationAttributes'}
0x18009ab6b  mov     [rcx+118h], rax
0x18009ab72  lea     rax, ??_7CFSFolder@@6BIFolderWithJunctions@@@; const CFSFolder::`vftable'{for `IFolderWithJunctions'}
0x18009ab79  mov     [rcx+120h], rax
0x18009ab80  lea     rax, ??_7CFSFolder@@6BIPropertyInfoProvider@@@; const CFSFolder::`vftable'{for `IPropertyInfoProvider'}
0x18009ab87  mov     [rcx+128h], rax
0x18009ab8e  lea     rax, ??_7CFSFolder@@6BIColumnPreference@@@; const CFSFolder::`vftable'{for `IColumnPreference'}
0x18009ab95  mov     [rcx+130h], rax
0x18009ab9c  lea     rax, ??_7CFSFolder@@6BIFSFolderPriv@@@; const CFSFolder::`vftable'{for `IFSFolderPriv'}
0x18009aba3  mov     [rcx+138h], rax
0x18009abaa  lea     rax, ??_7CFSFolder@@6BIObjectWithRegistryKey@@@; const CFSFolder::`vftable'{for `IObjectWithRegistryKey'}
0x18009abb1  mov     [rcx+140h], rax
0x18009abb8  call    cs:__imp_GetLastError
0x18009abbe  mov     r12d, eax
0x18009abc1  mov     rcx, [rbx+1B0h]; pv
0x18009abc8  call    cs:__imp_CoTaskMemFree
0x18009abce  xor     edi, edi
0x18009abd0  mov     [rbx+1B0h], rdi
0x18009abd7  mov     rcx, [rbx+1D0h]; hMem
0x18009abde  call    cs:__imp_LocalFree
0x18009abe4  mov     [rbx+1D0h], rdi
0x18009abeb  mov     rcx, [rbx+1D8h]; pv
0x18009abf2  call    cs:__imp_CoTaskMemFree
0x18009abf8  mov     [rbx+1D8h], rdi
0x18009abff  mov     rcx, [rbx+1E0h]; pv
0x18009ac06  call    cs:__imp_CoTaskMemFree
0x18009ac0c  mov     [rbx+1E0h], rdi
0x18009ac13  mov     dword ptr [rbx+1E8h], 0FFFFFFFEh
0x18009ac1d  test    byte ptr [rbx+218h], 10h
0x18009ac24  jnz     short loc_18009ACA1
0x18009ac26  mov     rcx, [rbx+1B8h]; pv
0x18009ac2d  call    cs:__imp_CoTaskMemFree
0x18009ac33  mov     [rbx+1B8h], rdi
0x18009ac3a  mov     rcx, [rbx+1C0h]; bstrString
0x18009ac41  call    cs:__imp_SysFreeString
0x18009ac47  mov     [rbx+1C0h], rdi
0x18009ac4e  mov     rbp, [rbx+1C8h]
0x18009ac55  test    rbp, rbp
0x18009ac58  jnz     loc_18009AF44
0x18009ac5e  mov     [rbx+1C8h], rdi
0x18009ac65  mov     dword ptr [rbx+1ECh], 0FFFFFFFFh
0x18009ac6f  and     dword ptr [rbx+218h], 0FFFFFDFFh
0x18009ac79  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009ac80  movups  xmmword ptr [rbx+1F0h], xmm0
0x18009ac87  mov     [rbx+208h], edi
0x18009ac8d  mov     rcx, [rbx+210h]; bstrString
0x18009ac94  call    cs:__imp_SysFreeString
0x18009ac9a  mov     [rbx+210h], rdi
0x18009aca1  mov     rcx, [rbx+270h]
0x18009aca8  mov     [rbx+270h], rdi
0x18009acaf  test    rcx, rcx
0x18009acb2  jz      short loc_18009ACC0
0x18009acb4  mov     rax, [rcx]
0x18009acb7  mov     rax, [rax+10h]
0x18009acbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acc0  mov     rax, [rbx+0A8h]
0x18009acc7  lea     rcx, [rbx+0A8h]
0x18009acce  mov     rax, [rax+18h]
0x18009acd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acd7  mov     ecx, r12d; dwErrCode
0x18009acda  call    cs:__imp_SetLastError
0x18009ace0  mov     rcx, [rbx+1B8h]; pv
0x18009ace7  call    cs:__imp_CoTaskMemFree
0x18009aced  mov     rcx, [rbx+1C0h]; bstrString
0x18009acf4  call    cs:__imp_SysFreeString
0x18009acfa  mov     rcx, [rbx+210h]; bstrString
0x18009ad01  call    cs:__imp_SysFreeString
0x18009ad07  mov     rcx, [rbx+268h]
0x18009ad0e  mov     [rbx+268h], rdi
0x18009ad15  test    rcx, rcx
0x18009ad18  jz      short loc_18009AD26
0x18009ad1a  mov     rax, [rcx]
0x18009ad1d  mov     rax, [rax+10h]
0x18009ad21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad26  mov     rcx, [rbx+288h]
0x18009ad2d  mov     [rbx+288h], rdi
0x18009ad34  test    rcx, rcx
0x18009ad37  jz      short loc_18009AD45
0x18009ad39  mov     rax, [rcx]
0x18009ad3c  mov     rax, [rax+10h]
0x18009ad40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad45  mov     rcx, [rbx+290h]
0x18009ad4c  mov     [rbx+290h], rdi
0x18009ad53  test    rcx, rcx
0x18009ad56  jz      short loc_18009AD64
0x18009ad58  mov     rax, [rcx]
0x18009ad5b  mov     rax, [rax+10h]
0x18009ad5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad64  mov     rcx, [rbx+388h]
0x18009ad6b  mov     [rbx+388h], rdi
0x18009ad72  test    rcx, rcx
0x18009ad75  jz      short loc_18009AD83
0x18009ad77  mov     rax, [rcx]
0x18009ad7a  mov     rax, [rax+10h]
0x18009ad7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad83  mov     rcx, [rbx+3A8h]; hKey
0x18009ad8a  test    rcx, rcx
0x18009ad8d  jz      short loc_18009AD96
0x18009ad8f  call    cs:__imp_RegCloseKey
0x18009ad95  nop
0x18009ad96  mov     rcx, [rbx+398h]
0x18009ad9d  test    rcx, rcx
0x18009ada0  jz      short loc_18009ADAF
0x18009ada2  mov     rax, [rcx]
0x18009ada5  mov     rax, [rax+10h]
0x18009ada9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adae  nop
0x18009adaf  lea     rcx, [rbx+2C8h]; void *
0x18009adb6  lea     r9, ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; void (*)(void *)
0x18009adbd  mov     edx, 18h; unsigned __int64
0x18009adc2  mov     r8d, 8; unsigned __int64
0x18009adc8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18009adcd  nop
0x18009adce  mov     rcx, [rbx+2B8h]
0x18009add5  test    rcx, rcx
0x18009add8  jnz     loc_18009AFA5
0x18009adde  lea     rax, ??_7CComTaskContext@@6B@; const CComTaskContext::`vftable'
0x18009ade5  mov     [rbx+298h], rax
0x18009adec  mov     rcx, [rbx+1C8h]; pv
0x18009adf3  test    rcx, rcx
0x18009adf6  jz      short loc_18009ADFF
0x18009adf8  call    cs:__imp_CoTaskMemFree
0x18009adfe  nop
0x18009adff  mov     rcx, [rbx+1A8h]
0x18009ae06  mov     [rbx+1A8h], rdi
0x18009ae0d  test    rcx, rcx
0x18009ae10  jz      short loc_18009AE1F
0x18009ae12  mov     rax, [rcx]
0x18009ae15  mov     rax, [rax+10h]
0x18009ae19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae1e  nop
0x18009ae1f  mov     rcx, [rbx+198h]
0x18009ae26  mov     [rbx+198h], rdi
0x18009ae2d  test    rcx, rcx
0x18009ae30  jnz     loc_18009AF83
0x18009ae36  mov     rcx, [rbx+190h]
0x18009ae3d  mov     [rbx+190h], rdi
0x18009ae44  test    rcx, rcx
0x18009ae47  jz      short loc_18009AE56
0x18009ae49  mov     rax, [rcx]
0x18009ae4c  mov     rax, [rax+10h]
0x18009ae50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae55  nop
0x18009ae56  mov     rcx, [rbx+180h]
0x18009ae5d  mov     [rbx+180h], rdi
0x18009ae64  test    rcx, rcx
0x18009ae67  jnz     loc_18009AF94
0x18009ae6d  mov     rcx, [rbx+178h]
0x18009ae74  mov     [rbx+178h], rdi
0x18009ae7b  test    rcx, rcx
0x18009ae7e  jz      short loc_18009AE8D
0x18009ae80  mov     rax, [rcx]
0x18009ae83  mov     rax, [rax+10h]
0x18009ae87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ae8c  nop
0x18009ae8d  mov     rcx, [rbx+168h]
0x18009ae94  mov     [rbx+168h], rdi
0x18009ae9b  test    rcx, rcx
0x18009ae9e  jnz     loc_18009AFC2
0x18009aea4  mov     rcx, [rbx+160h]
0x18009aeab  mov     [rbx+160h], rdi
0x18009aeb2  test    rcx, rcx
0x18009aeb5  jz      short loc_18009AEC4
0x18009aeb7  mov     rax, [rcx]
0x18009aeba  mov     rax, [rax+10h]
0x18009aebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aec3  nop
0x18009aec4  mov     rcx, [rbx+150h]
0x18009aecb  mov     [rbx+150h], rdi
0x18009aed2  test    rcx, rcx
0x18009aed5  jnz     loc_18009AF72
0x18009aedb  mov     rcx, [rbx+148h]
0x18009aee2  mov     [rbx+148h], rdi
0x18009aee9  test    rcx, rcx
0x18009aeec  jz      short loc_18009AEFB
0x18009aeee  mov     rax, [rcx]
0x18009aef1  mov     rax, [rax+10h]
0x18009aef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aefa  nop
0x18009aefb  lea     rax, ??_7CObjectWithSite@@6B@; const CObjectWithSite::`vftable'
0x18009af02  mov     [rbx+20h], rax
0x18009af06  mov     rcx, [rbx+28h]
0x18009af0a  mov     [rbx+28h], rdi
0x18009af0e  test    rcx, rcx
0x18009af11  jnz     short loc_18009AF64
0x18009af13  lea     rax, ??_7CAggregatedUnknown@@6B@; const CAggregatedUnknown::`vftable'
0x18009af1a  mov     [rbx], rax
0x18009af1d  test    r13b, 1
0x18009af21  jz      short loc_18009AF30
0x18009af23  mov     edx, 3B8h; struct std::nothrow_t *
0x18009af28  mov     rcx, rbx; void *
0x18009af2b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18009af30  mov     rax, rbx
0x18009af33  add     rsp, 28h
0x18009af37  pop     r15
0x18009af39  pop     r14
0x18009af3b  pop     r13
0x18009af3d  pop     r12
0x18009af3f  pop     rdi
0x18009af40  pop     rsi
0x18009af41  pop     rbp
0x18009af42  pop     rbx
0x18009af43  retn
0x18009af44  call    cs:__imp_GetLastError
0x18009af4a  mov     edi, eax
0x18009af4c  mov     rcx, rbp; pv
0x18009af4f  call    cs:__imp_CoTaskMemFree
0x18009af55  mov     ecx, edi; dwErrCode
0x18009af57  call    cs:__imp_SetLastError
0x18009af5d  xor     edi, edi
0x18009af5f  jmp     loc_18009AC5E
0x18009af64  mov     rax, [rcx]
0x18009af67  mov     rax, [rax+10h]
0x18009af6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af70  jmp     short loc_18009AF13
0x18009af72  mov     rax, [rcx]
0x18009af75  mov     rax, [rax+10h]
0x18009af79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af7e  jmp     loc_18009AEDB
0x18009af83  mov     rax, [rcx]
0x18009af86  mov     rax, [rax+10h]
0x18009af8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af8f  jmp     loc_18009AE36
0x18009af94  mov     rax, [rcx]
0x18009af97  mov     rax, [rax+10h]
0x18009af9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009afa0  jmp     loc_18009AE6D
  ... truncated ...
```
