# CFSFolder::`vector deleting destructor'(uint)

- ea: `0x18004b950`
- end: `0x18004bfcf`
- name: `??_ECFSFolder@@MEAAPEAXI@Z`
- size: `1663`
- prototype: `void *__fastcall(CFSFolder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180526e00`

## callees

- `0x18004b950`
- `0x18004bfd8`
- `0x18004c090`
- `0x1803b1f84`
- `0x1803b1f90`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bc9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bf4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bc9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bf4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bb48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bd6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bd6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bb7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bb7a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbf9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bcc4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bcd7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbf9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bc52`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bcc4`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bcd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bbae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bcb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bb94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bbae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bbdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bcb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf3e`

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
0x18004b950  push    rbx
0x18004b952  push    rbp
0x18004b953  push    rsi
0x18004b954  push    rdi
0x18004b955  push    r12
0x18004b957  push    r13
0x18004b959  push    r14
0x18004b95b  push    r15
0x18004b95d  sub     rsp, 28h
0x18004b961  mov     r13d, edx
0x18004b964  mov     rbx, rcx
0x18004b967  lea     rax, ??_7CFSFolder@@6BCAggregatedUnknown@@@; const CFSFolder::`vftable'{for `CAggregatedUnknown'}
0x18004b96e  mov     [rcx], rax
0x18004b971  lea     rax, ??_7CFSFolder@@6BCObjectWithSite@@@; const CFSFolder::`vftable'{for `CObjectWithSite'}
0x18004b978  mov     [rcx+20h], rax
0x18004b97c  lea     rax, ??_7CFSFolder@@6BIShellFolder2@@@; const CFSFolder::`vftable'{for `IShellFolder2'}
0x18004b983  mov     [rcx+30h], rax
0x18004b987  lea     rax, ??_7CFSFolder@@6BIShellIcon@@@; const CFSFolder::`vftable'{for `IShellIcon'}
0x18004b98e  mov     [rcx+38h], rax
0x18004b992  lea     rax, ??_7CFSFolder@@6BIShellIconOverlay@@@; const CFSFolder::`vftable'{for `IShellIconOverlay'}
0x18004b999  mov     [rcx+40h], rax
0x18004b99d  lea     rax, ??_7CFSFolder@@6BIPersistFolder3@@@; const CFSFolder::`vftable'{for `IPersistFolder3'}
0x18004b9a4  mov     [rcx+48h], rax
0x18004b9a8  lea     rax, ??_7CFSFolder@@6BIStorage@@@; const CFSFolder::`vftable'{for `IStorage'}
0x18004b9af  mov     [rcx+50h], rax
0x18004b9b3  lea     rax, ??_7CFSFolder@@6BILocalizableItemParent@@@; const CFSFolder::`vftable'{for `ILocalizableItemParent'}
0x18004b9ba  mov     [rcx+58h], rax
0x18004b9be  lea     rax, ??_7CFSFolder@@6BIItemNameLimits@@@; const CFSFolder::`vftable'{for `IItemNameLimits'}
0x18004b9c5  mov     [rcx+60h], rax
0x18004b9c9  lea     rax, ??_7CFSFolder@@6BIContextMenuCB@@@; const CFSFolder::`vftable'{for `IContextMenuCB'}
0x18004b9d0  mov     [rcx+68h], rax
0x18004b9d4  lea     rax, ??_7CFSFolder@@6BISetFolderEnumRestriction@@@; const CFSFolder::`vftable'{for `ISetFolderEnumRestriction'}
0x18004b9db  mov     [rcx+70h], rax
0x18004b9df  lea     rax, ??_7CFSFolder@@6BISetWrapperFolder@@@; const CFSFolder::`vftable'{for `ISetWrapperFolder'}
0x18004b9e6  mov     [rcx+78h], rax
0x18004b9ea  lea     rax, ??_7CFSFolder@@6BIOleCommandTarget@@@; const CFSFolder::`vftable'{for `IOleCommandTarget'}
0x18004b9f1  mov     [rcx+80h], rax
0x18004b9f8  lea     rax, ??_7CFSFolder@@6BIPersistPropertyBag@@@; const CFSFolder::`vftable'{for `IPersistPropertyBag'}
0x18004b9ff  mov     [rcx+88h], rax
0x18004ba06  lea     rax, ??_7CFSFolder@@6BIParentAndItem@@@; const CFSFolder::`vftable'{for `IParentAndItem'}
0x18004ba0d  mov     [rcx+90h], rax
0x18004ba14  lea     rax, ??_7CFSFolder@@6BIDelegateFolder@@@; const CFSFolder::`vftable'{for `IDelegateFolder'}
0x18004ba1b  mov     [rcx+98h], rax
0x18004ba22  lea     rax, ??_7CFSFolder@@6BIObjectProvider@@@; const CFSFolder::`vftable'{for `IObjectProvider'}
0x18004ba29  mov     [rcx+0A0h], rax
0x18004ba30  lea     rax, ??_7CFSFolder@@6BIObjectWithBackReferences@@@; const CFSFolder::`vftable'{for `IObjectWithBackReferences'}
0x18004ba37  mov     [rcx+0A8h], rax
0x18004ba3e  lea     rax, ??_7CFSFolder@@6BIRemoteComputer@@@; const CFSFolder::`vftable'{for `IRemoteComputer'}
0x18004ba45  mov     [rcx+0B0h], rax
0x18004ba4c  lea     rax, ??_7CFSFolder@@6BIThumbnailHandlerFactory@@@; const CFSFolder::`vftable'{for `IThumbnailHandlerFactory'}
0x18004ba53  mov     [rcx+0B8h], rax
0x18004ba5a  lea     rax, ??_7CFSFolder@@6BIContextMenuFactory@@@; const CFSFolder::`vftable'{for `IContextMenuFactory'}
0x18004ba61  mov     [rcx+0C0h], rax
0x18004ba68  lea     rax, ??_7CFSFolder@@6BIFolderType@@@; const CFSFolder::`vftable'{for `IFolderType'}
0x18004ba6f  mov     [rcx+0C8h], rax
0x18004ba76  lea     rax, ??_7CFSFolder@@6BIExplorerPaneVisibility@@@; const CFSFolder::`vftable'{for `IExplorerPaneVisibility'}
0x18004ba7d  mov     [rcx+0D0h], rax
0x18004ba84  lea     rax, ??_7CFSFolder@@6BIFolderWithViewPreferences@@@; const CFSFolder::`vftable'{for `IFolderWithViewPreferences'}
0x18004ba8b  mov     [rcx+0D8h], rax
0x18004ba92  lea     rax, ??_7CFSFolder@@6BIFolderSetNameOf@@@; const CFSFolder::`vftable'{for `IFolderSetNameOf'}
0x18004ba99  mov     [rcx+0E0h], rax
0x18004baa0  lea     rax, ??_7CFSFolder@@6BIBackReferencedObject@@@; const CFSFolder::`vftable'{for `IBackReferencedObject'}
0x18004baa7  mov     [rcx+0E8h], rax
0x18004baae  lea     rax, ??_7CFSFolder@@6BIShellFolderPropertyInformation@@@; const CFSFolder::`vftable'{for `IShellFolderPropertyInformation'}
0x18004bab5  mov     [rcx+0F0h], rax
0x18004babc  lea     rax, ??_7CFSFolder@@6BIShellFolderItemFactory@@@; const CFSFolder::`vftable'{for `IShellFolderItemFactory'}
0x18004bac3  mov     [rcx+0F8h], rax
0x18004baca  lea     rax, ??_7CFSFolder@@6BIAliasedNamespace@@@; const CFSFolder::`vftable'{for `IAliasedNamespace'}
0x18004bad1  mov     [rcx+100h], rax
0x18004bad8  lea     rax, ??_7CFSFolder@@6BIFolderWithSearchRoot@@@; const CFSFolder::`vftable'{for `IFolderWithSearchRoot'}
0x18004badf  mov     [rcx+108h], rax
0x18004bae6  lea     rax, ??_7CFSFolder@@6BINameSpaceTreeControlFolderCapabilities@@@; const CFSFolder::`vftable'{for `INameSpaceTreeControlFolderCapabilities'}
0x18004baed  mov     [rcx+110h], rax
0x18004baf4  lea     rax, ??_7CFSFolder@@6BIFolderWithElevationAttributes@@@; const CFSFolder::`vftable'{for `IFolderWithElevationAttributes'}
0x18004bafb  mov     [rcx+118h], rax
0x18004bb02  lea     rax, ??_7CFSFolder@@6BIFolderWithJunctions@@@; const CFSFolder::`vftable'{for `IFolderWithJunctions'}
0x18004bb09  mov     [rcx+120h], rax
0x18004bb10  lea     rax, ??_7CFSFolder@@6BIPropertyInfoProvider@@@; const CFSFolder::`vftable'{for `IPropertyInfoProvider'}
0x18004bb17  mov     [rcx+128h], rax
0x18004bb1e  lea     rax, ??_7CFSFolder@@6BIColumnPreference@@@; const CFSFolder::`vftable'{for `IColumnPreference'}
0x18004bb25  mov     [rcx+130h], rax
0x18004bb2c  lea     rax, ??_7CFSFolder@@6BIFSFolderPriv@@@; const CFSFolder::`vftable'{for `IFSFolderPriv'}
0x18004bb33  mov     [rcx+138h], rax
0x18004bb3a  lea     rax, ??_7CFSFolder@@6BIObjectWithRegistryKey@@@; const CFSFolder::`vftable'{for `IObjectWithRegistryKey'}
0x18004bb41  mov     [rcx+140h], rax
0x18004bb48  call    cs:__imp_GetLastError
0x18004bb4f  nop     dword ptr [rax+rax+00h]
0x18004bb54  mov     r12d, eax
0x18004bb57  mov     rcx, [rbx+1B0h]; pv
0x18004bb5e  call    cs:__imp_CoTaskMemFree
0x18004bb65  nop     dword ptr [rax+rax+00h]
0x18004bb6a  xor     edi, edi
0x18004bb6c  mov     [rbx+1B0h], rdi
0x18004bb73  mov     rcx, [rbx+1D0h]; hMem
0x18004bb7a  call    cs:__imp_LocalFree
0x18004bb81  nop     dword ptr [rax+rax+00h]
0x18004bb86  mov     [rbx+1D0h], rdi
0x18004bb8d  mov     rcx, [rbx+1D8h]; pv
0x18004bb94  call    cs:__imp_CoTaskMemFree
0x18004bb9b  nop     dword ptr [rax+rax+00h]
0x18004bba0  mov     [rbx+1D8h], rdi
0x18004bba7  mov     rcx, [rbx+1E0h]; pv
0x18004bbae  call    cs:__imp_CoTaskMemFree
0x18004bbb5  nop     dword ptr [rax+rax+00h]
0x18004bbba  mov     [rbx+1E0h], rdi
0x18004bbc1  mov     dword ptr [rbx+1E8h], 0FFFFFFFEh
0x18004bbcb  test    byte ptr [rbx+218h], 10h
0x18004bbd2  jnz     loc_18004BC65
0x18004bbd8  mov     rcx, [rbx+1B8h]; pv
0x18004bbdf  call    cs:__imp_CoTaskMemFree
0x18004bbe6  nop     dword ptr [rax+rax+00h]
0x18004bbeb  mov     [rbx+1B8h], rdi
0x18004bbf2  mov     rcx, [rbx+1C0h]; bstrString
0x18004bbf9  call    cs:__imp_SysFreeString
0x18004bc00  nop     dword ptr [rax+rax+00h]
0x18004bc05  mov     [rbx+1C0h], rdi
0x18004bc0c  mov     rbp, [rbx+1C8h]
0x18004bc13  test    rbp, rbp
0x18004bc16  jnz     loc_18004BF2D
0x18004bc1c  mov     [rbx+1C8h], rdi
0x18004bc23  mov     dword ptr [rbx+1ECh], 0FFFFFFFFh
0x18004bc2d  and     dword ptr [rbx+218h], 0FFFFFDFFh
0x18004bc37  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004bc3e  movups  xmmword ptr [rbx+1F0h], xmm0
0x18004bc45  mov     [rbx+208h], edi
0x18004bc4b  mov     rcx, [rbx+210h]; bstrString
0x18004bc52  call    cs:__imp_SysFreeString
0x18004bc59  nop     dword ptr [rax+rax+00h]
0x18004bc5e  mov     [rbx+210h], rdi
0x18004bc65  mov     rcx, [rbx+270h]
0x18004bc6c  mov     [rbx+270h], rdi
0x18004bc73  test    rcx, rcx
0x18004bc76  jz      short loc_18004BC84
0x18004bc78  mov     rax, [rcx]
0x18004bc7b  mov     rax, [rax+10h]
0x18004bc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc84  mov     rax, [rbx+0A8h]
0x18004bc8b  lea     rcx, [rbx+0A8h]
0x18004bc92  mov     rax, [rax+18h]
0x18004bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bc9b  mov     ecx, r12d; dwErrCode
0x18004bc9e  call    cs:__imp_SetLastError
0x18004bca5  nop     dword ptr [rax+rax+00h]
0x18004bcaa  mov     rcx, [rbx+1B8h]; pv
0x18004bcb1  call    cs:__imp_CoTaskMemFree
0x18004bcb8  nop     dword ptr [rax+rax+00h]
0x18004bcbd  mov     rcx, [rbx+1C0h]; bstrString
0x18004bcc4  call    cs:__imp_SysFreeString
0x18004bccb  nop     dword ptr [rax+rax+00h]
0x18004bcd0  mov     rcx, [rbx+210h]; bstrString
0x18004bcd7  call    cs:__imp_SysFreeString
0x18004bcde  nop     dword ptr [rax+rax+00h]
0x18004bce3  mov     rcx, [rbx+268h]
0x18004bcea  mov     [rbx+268h], rdi
0x18004bcf1  test    rcx, rcx
0x18004bcf4  jz      short loc_18004BD02
0x18004bcf6  mov     rax, [rcx]
0x18004bcf9  mov     rax, [rax+10h]
0x18004bcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd02  mov     rcx, [rbx+288h]
0x18004bd09  mov     [rbx+288h], rdi
0x18004bd10  test    rcx, rcx
0x18004bd13  jz      short loc_18004BD21
0x18004bd15  mov     rax, [rcx]
0x18004bd18  mov     rax, [rax+10h]
0x18004bd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd21  mov     rcx, [rbx+290h]
0x18004bd28  mov     [rbx+290h], rdi
0x18004bd2f  test    rcx, rcx
0x18004bd32  jz      short loc_18004BD40
0x18004bd34  mov     rax, [rcx]
0x18004bd37  mov     rax, [rax+10h]
0x18004bd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd40  mov     rcx, [rbx+388h]
0x18004bd47  mov     [rbx+388h], rdi
0x18004bd4e  test    rcx, rcx
0x18004bd51  jz      short loc_18004BD5F
0x18004bd53  mov     rax, [rcx]
0x18004bd56  mov     rax, [rax+10h]
0x18004bd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd5f  mov     rcx, [rbx+3A8h]; hKey
0x18004bd66  test    rcx, rcx
0x18004bd69  jz      short loc_18004BD78
0x18004bd6b  call    cs:__imp_RegCloseKey
0x18004bd72  nop     dword ptr [rax+rax+00h]
0x18004bd77  nop
0x18004bd78  mov     rcx, [rbx+398h]
0x18004bd7f  test    rcx, rcx
0x18004bd82  jz      short loc_18004BD91
0x18004bd84  mov     rax, [rcx]
0x18004bd87  mov     rax, [rax+10h]
0x18004bd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd90  nop
0x18004bd91  lea     rcx, [rbx+2C8h]; void *
0x18004bd98  lea     r9, ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; void (*)(void *)
0x18004bd9f  mov     edx, 18h; unsigned __int64
0x18004bda4  mov     r8d, 8; unsigned __int64
0x18004bdaa  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004bdaf  nop
0x18004bdb0  mov     rcx, [rbx+2B8h]
0x18004bdb7  test    rcx, rcx
0x18004bdba  jnz     loc_18004BFA0
0x18004bdc0  lea     rax, ??_7CComTaskContext@@6B@; const CComTaskContext::`vftable'
0x18004bdc7  mov     [rbx+298h], rax
0x18004bdce  mov     rcx, [rbx+1C8h]; pv
0x18004bdd5  test    rcx, rcx
0x18004bdd8  jz      short loc_18004BDE7
0x18004bdda  call    cs:__imp_CoTaskMemFree
0x18004bde1  nop     dword ptr [rax+rax+00h]
0x18004bde6  nop
0x18004bde7  mov     rcx, [rbx+1A8h]
0x18004bdee  mov     [rbx+1A8h], rdi
0x18004bdf5  test    rcx, rcx
0x18004bdf8  jz      short loc_18004BE07
0x18004bdfa  mov     rax, [rcx]
0x18004bdfd  mov     rax, [rax+10h]
0x18004be01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be06  nop
0x18004be07  mov     rcx, [rbx+198h]
0x18004be0e  mov     [rbx+198h], rdi
0x18004be15  test    rcx, rcx
0x18004be18  jnz     loc_18004BF7E
0x18004be1e  mov     rcx, [rbx+190h]
0x18004be25  mov     [rbx+190h], rdi
0x18004be2c  test    rcx, rcx
0x18004be2f  jz      short loc_18004BE3E
0x18004be31  mov     rax, [rcx]
0x18004be34  mov     rax, [rax+10h]
0x18004be38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be3d  nop
0x18004be3e  mov     rcx, [rbx+180h]
0x18004be45  mov     [rbx+180h], rdi
0x18004be4c  test    rcx, rcx
0x18004be4f  jnz     loc_18004BF8F
0x18004be55  mov     rcx, [rbx+178h]
0x18004be5c  mov     [rbx+178h], rdi
0x18004be63  test    rcx, rcx
0x18004be66  jz      short loc_18004BE75
0x18004be68  mov     rax, [rcx]
0x18004be6b  mov     rax, [rax+10h]
0x18004be6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be74  nop
0x18004be75  mov     rcx, [rbx+168h]
0x18004be7c  mov     [rbx+168h], rdi
0x18004be83  test    rcx, rcx
0x18004be86  jnz     loc_18004BFBD
0x18004be8c  mov     rcx, [rbx+160h]
0x18004be93  mov     [rbx+160h], rdi
0x18004be9a  test    rcx, rcx
0x18004be9d  jz      short loc_18004BEAC
0x18004be9f  mov     rax, [rcx]
0x18004bea2  mov     rax, [rax+10h]
0x18004bea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beab  nop
0x18004beac  mov     rcx, [rbx+150h]
0x18004beb3  mov     [rbx+150h], rdi
0x18004beba  test    rcx, rcx
0x18004bebd  jnz     loc_18004BF6D
0x18004bec3  mov     rcx, [rbx+148h]
0x18004beca  mov     [rbx+148h], rdi
0x18004bed1  test    rcx, rcx
0x18004bed4  jz      short loc_18004BEE3
0x18004bed6  mov     rax, [rcx]
0x18004bed9  mov     rax, [rax+10h]
0x18004bedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bee2  nop
0x18004bee3  lea     rax, ??_7CObjectWithSite@@6B@; const CObjectWithSite::`vftable'
0x18004beea  mov     [rbx+20h], rax
0x18004beee  mov     rcx, [rbx+28h]
0x18004bef2  mov     [rbx+28h], rdi
0x18004bef6  test    rcx, rcx
0x18004bef9  jnz     short loc_18004BF5F
0x18004befb  lea     rax, ??_7CAggregatedUnknown@@6B@; const CAggregatedUnknown::`vftable'
0x18004bf02  mov     [rbx], rax
0x18004bf05  test    r13b, 1
0x18004bf09  jz      short loc_18004BF18
0x18004bf0b  mov     edx, 3B8h; struct std::nothrow_t *
0x18004bf10  mov     rcx, rbx; void *
0x18004bf13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004bf18  mov     rax, rbx
0x18004bf1b  add     rsp, 28h
0x18004bf1f  pop     r15
0x18004bf21  pop     r14
0x18004bf23  pop     r13
0x18004bf25  pop     r12
0x18004bf27  pop     rdi
0x18004bf28  pop     rsi
0x18004bf29  pop     rbp
0x18004bf2a  pop     rbx
0x18004bf2b  retn
0x18004bf2d  call    cs:__imp_GetLastError
0x18004bf34  nop     dword ptr [rax+rax+00h]
0x18004bf39  mov     edi, eax
0x18004bf3b  mov     rcx, rbp; pv
0x18004bf3e  call    cs:__imp_CoTaskMemFree
0x18004bf45  nop     dword ptr [rax+rax+00h]
0x18004bf4a  mov     ecx, edi; dwErrCode
0x18004bf4c  call    cs:__imp_SetLastError
0x18004bf53  nop     dword ptr [rax+rax+00h]
0x18004bf58  xor     edi, edi
  ... truncated ...
```
