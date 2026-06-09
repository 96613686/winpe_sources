# OSDeploymentInformationFactory::~OSDeploymentInformationFactory(void)

- ea: `0x140018ddc`
- end: `0x140018fc6`
- name: `??1OSDeploymentInformationFactory@@UEAA@XZ`
- size: `490`
- prototype: `void __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140011d2c`
- `0x140018da0`

## callees

- `0x14000b1f4`
- `0x14000beac`
- `0x140018ddc`
- `0x140019a84`
- `0x140019ddc`
- `0x14001a0dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140018e68`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140018ed7`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140018e68`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x140018ed7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018f71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018f8f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018f71`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140018f8f`

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
0x140018ddc  mov     [rsp+arg_0], rbx
0x140018de1  mov     [rsp+arg_8], rbp
0x140018de6  mov     [rsp+arg_10], rsi
0x140018deb  push    rdi
0x140018dec  push    r12
0x140018dee  push    r14; int
0x140018df0  sub     rsp, 20h
0x140018df4  mov     rbx, rcx
0x140018df7  lea     rax, ??_7OSDeploymentInformationFactory@@6B@; const OSDeploymentInformationFactory::`vftable'
0x140018dfe  mov     [rcx], rax
0x140018e01  lea     rax, ??_7OSDeploymentInformationFactory@@6BIDeploymentInformationFactory@@@; const OSDeploymentInformationFactory::`vftable'{for `IDeploymentInformationFactory'}
0x140018e08  mov     [rcx+30h], rax
0x140018e0c  lea     rax, ??_7OSDeploymentInformationFactory@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWUInternalDeploymentInformationFactory@@@Details@WRL@Microsoft@@@; const OSDeploymentInformationFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWUInternalDeploymentInformationFactory>'}
0x140018e13  mov     [rcx+38h], rax
0x140018e17  lea     rsi, [rcx+98h]
0x140018e1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x140018e25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x140018e2a  test    al, al
0x140018e2c  jz      loc_140018F0F
0x140018e32  xor     ebp, ebp
0x140018e34  mov     eax, [rsi+14h]
0x140018e37  mov     rdi, rsi
0x140018e3a  lea     r12, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x140018e41  test    eax, eax
0x140018e43  jz      short loc_140018E90
0x140018e45  cmp     ebp, eax
0x140018e47  jb      short loc_140018E54
0x140018e49  mov     r9d, 80240007h
0x140018e4f  lea     edx, [rbp+27h]
0x140018e52  jmp     short loc_140018E7A
0x140018e54  mov     ecx, ebp
0x140018e56  add     rcx, rcx
0x140018e59  mov     rax, [rsi+8]
0x140018e5d  mov     rcx, [rax+rcx*8]; pUnk
0x140018e61  test    rcx, rcx
0x140018e64  jz      short loc_140018E87
0x140018e66  xor     edx, edx; dwReserved
0x140018e68  call    cs:__imp_CoDisconnectObject
0x140018e6e  test    eax, eax
0x140018e70  jns     short loc_140018E87
0x140018e72  mov     r9d, eax; char *
0x140018e75  mov     edx, 29h ; ')'; void *
0x140018e7a  mov     r8, r12; unsigned int
0x140018e7d  mov     rcx, [rsp+38h]; this
0x140018e82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140018e87  inc     ebp
0x140018e89  mov     eax, [rsi+14h]
0x140018e8c  cmp     ebp, eax
0x140018e8e  jb      short loc_140018E54
0x140018e90  mov     r9d, 1
0x140018e96  or      r8d, 0FFFFFFFFh
0x140018e9a  xor     edx, edx
0x140018e9c  mov     rcx, rsi
0x140018e9f  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x140018ea4  lea     rbp, [rbx+108h]
0x140018eab  xor     esi, esi
0x140018ead  mov     eax, [rbp+14h]
0x140018eb0  test    eax, eax
0x140018eb2  jz      short loc_140018EFF
0x140018eb4  cmp     esi, eax
0x140018eb6  jb      short loc_140018EC3
0x140018eb8  mov     r9d, 80240007h
0x140018ebe  lea     edx, [rsi+27h]
0x140018ec1  jmp     short loc_140018EE9
0x140018ec3  mov     ecx, esi
0x140018ec5  add     rcx, rcx
0x140018ec8  mov     rax, [rbp+8]
0x140018ecc  mov     rcx, [rax+rcx*8]; pUnk
0x140018ed0  test    rcx, rcx
0x140018ed3  jz      short loc_140018EF6
0x140018ed5  xor     edx, edx; dwReserved
0x140018ed7  call    cs:__imp_CoDisconnectObject
0x140018edd  test    eax, eax
0x140018edf  jns     short loc_140018EF6
0x140018ee1  mov     r9d, eax; char *
0x140018ee4  mov     edx, 29h ; ')'; void *
0x140018ee9  mov     r8, r12; unsigned int
0x140018eec  mov     rcx, [rsp+38h]; this
0x140018ef1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140018ef6  inc     esi
0x140018ef8  mov     eax, [rbp+14h]
0x140018efb  cmp     esi, eax
0x140018efd  jb      short loc_140018EC3
0x140018eff  mov     rcx, rbp
0x140018f02  lea     r12, [rbx+0E8h]
0x140018f09  lea     r14, [rbx+78h]
0x140018f0d  jmp     short loc_140018F3B
0x140018f0f  lea     r14, [rbx+78h]
0x140018f13  mov     r9d, 1
0x140018f19  or      r8d, 0FFFFFFFFh
0x140018f1d  xor     edx, edx
0x140018f1f  mov     rcx, r14
0x140018f22  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x140018f27  lea     rcx, [rbx+0E8h]
0x140018f2e  lea     rbp, [rbx+108h]
0x140018f35  mov     r12, rcx
0x140018f38  mov     rdi, rsi
0x140018f3b  mov     r9d, 1
0x140018f41  or      r8d, 0FFFFFFFFh
0x140018f45  xor     edx, edx
0x140018f47  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x140018f4c  mov     rcx, rbp
0x140018f4f  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x140018f54  mov     rcx, r12
0x140018f57  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x140018f5c  lea     rsi, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x140018f63  mov     [rbx+0B8h], rsi
0x140018f6a  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x140018f71  call    cs:__imp_DeleteCriticalSection
0x140018f77  mov     rcx, rdi
0x140018f7a  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x140018f7f  mov     rcx, r14
0x140018f82  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x140018f87  mov     [rbx+48h], rsi
0x140018f8b  lea     rcx, [rbx+50h]; lpCriticalSection
0x140018f8f  call    cs:__imp_DeleteCriticalSection
0x140018f95  mov     dword ptr [rbx+44h], 0C0000001h
0x140018f9c  lea     rax, ??_7CWuaSingletonClassFactory@@6B@; const CWuaSingletonClassFactory::`vftable'
0x140018fa3  mov     [rbx], rax
0x140018fa6  mov     rcx, rbx; this
0x140018fa9  mov     rbx, [rsp+38h+arg_0]
0x140018fae  mov     rbp, [rsp+38h+arg_8]
0x140018fb3  mov     rsi, [rsp+38h+arg_10]
0x140018fb8  add     rsp, 20h
0x140018fbc  pop     r14
0x140018fbe  pop     r12
0x140018fc0  pop     rdi
0x140018fc1  jmp     ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
```
