# ATL::CComObject<CPreflistFolder>::~CComObject<CPreflistFolder>(void)

- ea: `0x180003298`
- end: `0x18000333a`
- name: `??1?$CComObject@VCPreflistFolder@@@ATL@@UEAA@XZ`
- size: `162`
- prototype: `__int64 __fastcall(CPreflistFolder *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003dc0`

## callees

- `0x180003620`
- `0x18000e0a0`
- `0x180030010`

## pseudocode

```c
void __fastcall ATL::CComObject<CPreflistFolder>::~CComObject<CPreflistFolder>(CPreflistFolder *this)
{
  *(_QWORD *)this = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IPersistFolder2'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IShellFolder2'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IShellFolderViewCB'};
  *((_QWORD *)this + 3) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IFolderViewSettings'};
  *((_QWORD *)this + 4) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IFolderType'};
  *((_QWORD *)this + 5) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 6) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IInfoPaneProvider'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `ProfileStoreListener'};
  *((_QWORD *)this + 8) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IUICommandHelper'};
  *((_QWORD *)this + 9) = &ATL::CComObject<CPreflistFolder>::`vftable'{for `IExplorerPaneVisibility'};
  *((_DWORD *)this + 20) = -1073741823;
  CPreflistFolder::FinalRelease(this);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPreflistFolder::~CPreflistFolder(this);
}

```

## disassembly

```asm
0x180003298  push    rbx
0x18000329a  sub     rsp, 20h
0x18000329e  mov     rbx, rcx
0x1800032a1  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIPersistFolder2@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IPersistFolder2'}
0x1800032a8  mov     [rcx], rax
0x1800032ab  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIShellFolder2@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IShellFolder2'}
0x1800032b2  mov     [rcx+8], rax
0x1800032b6  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIShellFolderViewCB@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IShellFolderViewCB'}
0x1800032bd  mov     [rcx+10h], rax
0x1800032c1  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIFolderViewSettings@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IFolderViewSettings'}
0x1800032c8  mov     [rcx+18h], rax
0x1800032cc  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIFolderType@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IFolderType'}
0x1800032d3  mov     [rcx+20h], rax
0x1800032d7  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IObjectWithSite'}
0x1800032de  mov     [rcx+28h], rax
0x1800032e2  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIInfoPaneProvider@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IInfoPaneProvider'}
0x1800032e9  mov     [rcx+30h], rax
0x1800032ed  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BProfileStoreListener@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `ProfileStoreListener'}
0x1800032f4  mov     [rcx+38h], rax
0x1800032f8  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIUICommandHelper@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IUICommandHelper'}
0x1800032ff  mov     [rcx+40h], rax
0x180003303  lea     rax, ??_7?$CComObject@VCPreflistFolder@@@ATL@@6BIExplorerPaneVisibility@@@; const ATL::CComObject<CPreflistFolder>::`vftable'{for `IExplorerPaneVisibility'}
0x18000330a  mov     [rcx+48h], rax
0x18000330e  mov     dword ptr [rcx+50h], 0C0000001h
0x180003315  call    ?FinalRelease@CPreflistFolder@@QEAAXXZ; CPreflistFolder::FinalRelease(void)
0x18000331a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003321  mov     rax, [rcx]
0x180003324  mov     rax, [rax+10h]
0x180003328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332d  mov     rcx, rbx; this
0x180003330  add     rsp, 20h
0x180003334  pop     rbx
0x180003335  jmp     ??1CPreflistFolder@@QEAA@XZ; CPreflistFolder::~CPreflistFolder(void)
```
