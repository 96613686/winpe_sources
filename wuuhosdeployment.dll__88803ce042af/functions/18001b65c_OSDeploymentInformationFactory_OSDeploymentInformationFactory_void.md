# OSDeploymentInformationFactory::~OSDeploymentInformationFactory(void)

- ea: `0x18001b65c`
- end: `0x18001b846`
- name: `??1OSDeploymentInformationFactory@@UEAA@XZ`
- size: `490`
- prototype: `void __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b620`
- `0x18004b990`
- `0x18004ba10`

## callees

- `0x18000c0b4`
- `0x18001b65c`
- `0x18001c408`
- `0x18001c830`
- `0x18001cb68`
- `0x18003100c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b7f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b80f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b7f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b80f`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18001b6e8`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18001b757`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18001b6e8`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18001b757`

## pseudocode

```c
void __fastcall OSDeploymentInformationFactory::~OSDeploymentInformationFactory(OSDeploymentInformationFactory *this)
{
  char *v2; // rsi
  unsigned int v3; // ebp
  char *i; // rdi
  IUnknown *v5; // rcx
  HRESULT v6; // eax
  char *v7; // rbp
  unsigned int j; // esi
  IUnknown *v9; // rcx
  HRESULT v10; // eax
  char *v11; // rcx
  char *v12; // r12
  char *v13; // r14
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &OSDeploymentInformationFactory::`vftable';
  *((_QWORD *)this + 6) = &OSDeploymentInformationFactory::`vftable'{for `IDeploymentInformationFactory'};
  *((_QWORD *)this + 7) = &OSDeploymentInformationFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWUInternalDeploymentInformationFactory>'};
  v2 = (char *)this + 152;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl'::`2'::impl) )
  {
    v3 = 0;
    for ( i = v2; v3 < *((_DWORD *)v2 + 5); ++v3 )
    {
      v5 = *(IUnknown **)(*((_QWORD *)v2 + 1) + 16LL * v3);
      if ( v5 )
      {
        v6 = CoDisconnectObject(v5, 0);
        if ( v6 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeployment"
                          "InformationFactory.cpp",
            (const char *)(unsigned int)v6,
            v14);
      }
    }
    CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
      v2,
      0,
      0xFFFFFFFFLL,
      1);
    v7 = (char *)this + 264;
    for ( j = 0; j < *((_DWORD *)this + 71); ++j )
    {
      v9 = *(IUnknown **)(*((_QWORD *)this + 34) + 16LL * j);
      if ( v9 )
      {
        v10 = CoDisconnectObject(v9, 0);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeployment"
                          "InformationFactory.cpp",
            (const char *)(unsigned int)v10,
            v14);
      }
    }
    v11 = (char *)this + 264;
    v12 = (char *)this + 232;
    v13 = (char *)this + 120;
  }
  else
  {
    v13 = (char *)this + 120;
    CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
      (char *)this + 120,
      0,
      0xFFFFFFFFLL,
      1);
    v11 = (char *)this + 232;
    v7 = (char *)this + 264;
    v12 = (char *)this + 232;
    i = v2;
  }
  CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
    v11,
    0,
    0xFFFFFFFFLL,
    1);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v7);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v12);
  *((_QWORD *)this + 23) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(i);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v13);
  *((_QWORD *)this + 9) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  *((_DWORD *)this + 17) = -1073741823;
  *(_QWORD *)this = &CWuaSingletonClassFactory::`vftable';
  CWuaClassFactoryBase::~CWuaClassFactoryBase(this);
}

```

## disassembly

```asm
0x18001b65c  mov     [rsp+arg_0], rbx
0x18001b661  mov     [rsp+arg_8], rbp
0x18001b666  mov     [rsp+arg_10], rsi
0x18001b66b  push    rdi
0x18001b66c  push    r12
0x18001b66e  push    r14; int
0x18001b670  sub     rsp, 20h
0x18001b674  mov     rbx, rcx
0x18001b677  lea     rax, ??_7OSDeploymentInformationFactory@@6B@; const OSDeploymentInformationFactory::`vftable'
0x18001b67e  mov     [rcx], rax
0x18001b681  lea     rax, ??_7OSDeploymentInformationFactory@@6BIDeploymentInformationFactory@@@; const OSDeploymentInformationFactory::`vftable'{for `IDeploymentInformationFactory'}
0x18001b688  mov     [rcx+30h], rax
0x18001b68c  lea     rax, ??_7OSDeploymentInformationFactory@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWUInternalDeploymentInformationFactory@@@Details@WRL@Microsoft@@@; const OSDeploymentInformationFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWUInternalDeploymentInformationFactory>'}
0x18001b693  mov     [rcx+38h], rax
0x18001b697  lea     rsi, [rcx+98h]
0x18001b69e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x18001b6a5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x18001b6aa  test    al, al
0x18001b6ac  jz      loc_18001B78F
0x18001b6b2  xor     ebp, ebp
0x18001b6b4  mov     eax, [rsi+14h]
0x18001b6b7  mov     rdi, rsi
0x18001b6ba  lea     r12, aCW1SSrcClientE_11; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001b6c1  test    eax, eax
0x18001b6c3  jz      short loc_18001B710
0x18001b6c5  cmp     ebp, eax
0x18001b6c7  jb      short loc_18001B6D4
0x18001b6c9  mov     r9d, 80240007h
0x18001b6cf  lea     edx, [rbp+27h]
0x18001b6d2  jmp     short loc_18001B6FA
0x18001b6d4  mov     ecx, ebp
0x18001b6d6  add     rcx, rcx
0x18001b6d9  mov     rax, [rsi+8]
0x18001b6dd  mov     rcx, [rax+rcx*8]; pUnk
0x18001b6e1  test    rcx, rcx
0x18001b6e4  jz      short loc_18001B707
0x18001b6e6  xor     edx, edx; dwReserved
0x18001b6e8  call    cs:__imp_CoDisconnectObject
0x18001b6ee  test    eax, eax
0x18001b6f0  jns     short loc_18001B707
0x18001b6f2  mov     r9d, eax; char *
0x18001b6f5  mov     edx, 29h ; ')'; void *
0x18001b6fa  mov     r8, r12; unsigned int
0x18001b6fd  mov     rcx, [rsp+38h]; this
0x18001b702  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b707  inc     ebp
0x18001b709  mov     eax, [rsi+14h]
0x18001b70c  cmp     ebp, eax
0x18001b70e  jb      short loc_18001B6D4
0x18001b710  mov     r9d, 1
0x18001b716  or      r8d, 0FFFFFFFFh
0x18001b71a  xor     edx, edx
0x18001b71c  mov     rcx, rsi
0x18001b71f  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001b724  lea     rbp, [rbx+108h]
0x18001b72b  xor     esi, esi
0x18001b72d  mov     eax, [rbp+14h]
0x18001b730  test    eax, eax
0x18001b732  jz      short loc_18001B77F
0x18001b734  cmp     esi, eax
0x18001b736  jb      short loc_18001B743
0x18001b738  mov     r9d, 80240007h
0x18001b73e  lea     edx, [rsi+27h]
0x18001b741  jmp     short loc_18001B769
0x18001b743  mov     ecx, esi
0x18001b745  add     rcx, rcx
0x18001b748  mov     rax, [rbp+8]
0x18001b74c  mov     rcx, [rax+rcx*8]; pUnk
0x18001b750  test    rcx, rcx
0x18001b753  jz      short loc_18001B776
0x18001b755  xor     edx, edx; dwReserved
0x18001b757  call    cs:__imp_CoDisconnectObject
0x18001b75d  test    eax, eax
0x18001b75f  jns     short loc_18001B776
0x18001b761  mov     r9d, eax; char *
0x18001b764  mov     edx, 29h ; ')'; void *
0x18001b769  mov     r8, r12; unsigned int
0x18001b76c  mov     rcx, [rsp+38h]; this
0x18001b771  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b776  inc     esi
0x18001b778  mov     eax, [rbp+14h]
0x18001b77b  cmp     esi, eax
0x18001b77d  jb      short loc_18001B743
0x18001b77f  mov     rcx, rbp
0x18001b782  lea     r12, [rbx+0E8h]
0x18001b789  lea     r14, [rbx+78h]
0x18001b78d  jmp     short loc_18001B7BB
0x18001b78f  lea     r14, [rbx+78h]
0x18001b793  mov     r9d, 1
0x18001b799  or      r8d, 0FFFFFFFFh
0x18001b79d  xor     edx, edx
0x18001b79f  mov     rcx, r14
0x18001b7a2  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001b7a7  lea     rcx, [rbx+0E8h]
0x18001b7ae  lea     rbp, [rbx+108h]
0x18001b7b5  mov     r12, rcx
0x18001b7b8  mov     rdi, rsi
0x18001b7bb  mov     r9d, 1
0x18001b7c1  or      r8d, 0FFFFFFFFh
0x18001b7c5  xor     edx, edx
0x18001b7c7  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001b7cc  mov     rcx, rbp
0x18001b7cf  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18001b7d4  mov     rcx, r12
0x18001b7d7  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18001b7dc  lea     rsi, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18001b7e3  mov     [rbx+0B8h], rsi
0x18001b7ea  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18001b7f1  call    cs:__imp_DeleteCriticalSection
0x18001b7f7  mov     rcx, rdi
0x18001b7fa  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18001b7ff  mov     rcx, r14
0x18001b802  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18001b807  mov     [rbx+48h], rsi
0x18001b80b  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001b80f  call    cs:__imp_DeleteCriticalSection
0x18001b815  mov     dword ptr [rbx+44h], 0C0000001h
0x18001b81c  lea     rax, ??_7CWuaSingletonClassFactory@@6B@; const CWuaSingletonClassFactory::`vftable'
0x18001b823  mov     [rbx], rax
0x18001b826  mov     rcx, rbx; this
0x18001b829  mov     rbx, [rsp+38h+arg_0]
0x18001b82e  mov     rbp, [rsp+38h+arg_8]
0x18001b833  mov     rsi, [rsp+38h+arg_10]
0x18001b838  add     rsp, 20h
0x18001b83c  pop     r14
0x18001b83e  pop     r12
0x18001b840  pop     rdi
0x18001b841  jmp     ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
```
