# Wsp::Facade::FileShareFactory::GetCnoToken(void)

- ea: `0x18005a170`
- end: `0x18005a6d0`
- name: `?GetCnoToken@FileShareFactory@Facade@Wsp@@UEAA?AVToken@cxl@@XZ`
- size: `1376`
- prototype: `struct cxl::Token __high(void)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002ad0`
- `0x180005e64`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c4ac`
- `0x18000c5c4`
- `0x18000cd24`
- `0x18000eb18`
- `0x180015be4`
- `0x18001c8f0`
- `0x18001cf18`
- `0x1800310a8`
- `0x18003873c`
- `0x18004acc8`
- `0x1800569fc`
- `0x180056c40`
- `0x180056c80`
- `0x180057488`
- `0x180057984`
- `0x18005a170`
- `0x180075734`
- `0x180075c60`
- `0x1800760ac`
- `0x18007800c`
- `0x1800780f8`
- `0x18008f664`
- `0x18008f75c`
- `0x1800920d4`
- `0x180092458`
- `0x1800925c8`
- `0x180092df8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005a587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005a587`

## string_xrefs

- `0x18005a22f`: `In wsp_fs.dll - domain:{0} code:{1} reason: Failed to get cluster instance in GetCnoToken`
- `0x18005a287`: `AdminAccessPoint`
- `0x18005a3d1`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find local cluster node in GetCnoToken.`
- `0x18005a43a`: `Warning occurred in wsp_fs.dll - reason: Could not get the core cluster group type in GetCnoToken.`
- `0x18005a304`: `In wsp_fs.dll - domain:{0} code:{1} reason: Could not determine cluster management point type, assume no CNO token available for GetCnoToken.`
- `0x18005a5a9`: `storwmi!FileShareFactory::GetCnoToken`
- `0x18005a629`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not get virtual server token in GetCnoToken.`
- `0x18005a551`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find any {2} resources in GetCnoToken.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
cxl::Token *__fastcall Wsp::Facade::FileShareFactory::GetCnoToken(__int64 a1, cxl::Token *a2)
{
  struct cxl::TraceManager *v3; // rax
  _QWORD *Instance; // rax
  int Cluster; // ebx
  struct cxl::TraceManager *v6; // rax
  __int64 v7; // rax
  std::_Ref_count_base *v8; // rdi
  __int64 v9; // rax
  char v10; // bl
  struct cxl::TraceManager *v11; // rax
  unsigned int value; // ebx
  struct cxl::TraceManager *v13; // rax
  __int64 Node; // rax
  std::_Ref_count_base *v15; // rsi
  struct cxl::TraceManager *v16; // rax
  __int64 CoreClusterGroup; // rax
  std::_Ref_count_base *v18; // rbx
  char *v19; // rbx
  std::_Ref_count_base **v20; // rax
  std::_Ref_count_base *v21; // rcx
  __int64 ResourceFacade; // rax
  std::_Ref_count_base *v23; // rbx
  struct cxl::TextWriter *v24; // rbx
  __int64 v25; // rax
  int v26; // edi
  __int64 v27; // rbx
  struct cxl::TraceManager *v28; // rax
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  _QWORD *v32; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v33; // [rsp+68h] [rbp-98h]
  std::_Ref_count_base *v34[2]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch] BYREF
  std::_Ref_count_base *v38[2]; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v39[2]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v40[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[40]; // [rsp+E0h] [rbp-20h] BYREF
  cxl::Token *v44; // [rsp+108h] [rbp+8h]
  _BYTE v45[8]; // [rsp+110h] [rbp+10h] BYREF
  std::_Ref_count_base *v46; // [rsp+118h] [rbp+18h]
  _QWORD v47[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[8]; // [rsp+130h] [rbp+30h] BYREF
  std::_Ref_count_base *v49; // [rsp+138h] [rbp+38h]
  _BYTE v50[144]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v51[144]; // [rsp+1E0h] [rbp+E0h] BYREF

  v44 = a2;
  *((_QWORD *)a2 + 1) = 0;
  v36 = 1;
  *(_OWORD *)v34 = 0;
  *(_OWORD *)v35 = 0;
  *(_OWORD *)v38 = 0;
  *(_OWORD *)v40 = 0;
  *(_OWORD *)v42 = 0;
  v3 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [43],>((struct cxl::TraceManager *)((char *)v3 + 120));
  Instance = (_QWORD *)ClusWmi::DataStore::GetInstance(&v32);
  Cluster = ClusWmi::DataStore::GetCluster(*Instance, v34);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  if ( Cluster < 0 )
  {
    v6 = cxl::TraceManager::Instance();
    v31 = Cluster;
    LODWORD(v30) = 2;
    cxl::TextWriter::WriteLine<wchar_t,int,int>(
      (struct cxl::TraceManager *)((char *)v6 + 80),
      (wchar_t *)L"In wsp_fs.dll - domain:{0} code:{1} reason: Failed to get cluster instance in GetCnoToken");
    goto LABEL_41;
  }
  v7 = ClusApi::Facade::FacadeFactory::CreateClusterFacade(&v32, v34);
  std::shared_ptr<ClusWmi::DataStore>::operator=(v35, v7);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v43);
  v8 = v35[0];
  ClusApi::Facade::FacadeObject::GetProperties(v35[0], 1, v43);
  std::wstring::wstring(v48, L"AdminAccessPoint");
  cxl::PropertyList::find(v43, v50, v48);
  std::wstring::_Tidy_deallocate(v48);
  v9 = cxl::PropertyList::end(v43, v51);
  v10 = cxl::PropertyList::property_iterator::operator==(v50, v9);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v51);
  if ( v10 )
  {
    v11 = cxl::TraceManager::Instance();
    LODWORD(v30) = -2147024846;
    v31 = 2;
    cxl::TextWriter::WriteLine<wchar_t,int,int>(
      (struct cxl::TraceManager *)((char *)v11 + 120),
      (wchar_t *)L"In wsp_fs.dll - domain:{0} code:{1} reason: Could not determine cluster management point type, assume n"
                  "o CNO token available for GetCnoToken.");
  }
  else
  {
    value = cxl::property_data_trait<unsigned long>::get_value(v50);
    if ( ((value - 1) & 0xFFFFFFFD) == 0 )
    {
      Node = ClusApi::Facade::ClusterFacade::GetNode(v8, &v32, cxl::EmptyLiteral);
      std::shared_ptr<ClusWmi::DataStore>::operator=(v38, Node);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      v15 = v38[0];
      if ( v38[0] )
      {
        CoreClusterGroup = ClusApi::Facade::ClusterFacade::GetCoreClusterGroup(v8, &v32);
        std::shared_ptr<ClusWmi::DataStore>::operator=(v40, CoreClusterGroup);
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        v18 = v40[0];
        if ( v40[0] )
        {
          v20 = (std::_Ref_count_base **)std::make_shared<ClusApi::Facade::ResourceTypeFilter,wchar_t const (&)[13]>(v45);
          *(_OWORD *)v39 = 0;
          v39[0] = *v20;
          v39[1] = v20[1];
          *v20 = 0;
          v20[1] = 0;
          if ( v46 )
            std::_Ref_count_base::_Decref(v46);
          ClusApi::Facade::GroupFacade::GetResources(v18, &v32, v39);
          if ( (_QWORD *)*v32 != v32 )
          {
            ResourceFacade = ClusApi::Facade::FacadeFactory::CreateResourceFacade(v48, *v32 + 16LL);
            std::shared_ptr<ClusWmi::DataStore>::operator=(v42, ResourceFacade);
            v21 = v49;
            if ( v49 )
              std::_Ref_count_base::_Decref(v49);
          }
          std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(
            v21,
            v32);
          std::_Deallocate<16>(v32, 32);
          v23 = v42[0];
          if ( v42[0] )
          {
            v41 = -1;
            v37 = 0;
            memset(v47, 0, 12);
            LODWORD(v47[0]) = GetCurrentProcessId();
            *(_QWORD *)((char *)v47 + 4) = 14;
            v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, __int64 *, int, int *, __int64, const wchar_t *))(**((_QWORD **)v23 + 7) + 40LL))(
                    *((_QWORD *)v23 + 7),
                    16777581,
                    v47,
                    12,
                    &v41,
                    8,
                    &v37,
                    (__int64)v15 + 40,
                    L"storwmi!FileShareFactory::GetCnoToken");
            if ( v26 < 0 || (v27 = v41, v41 == -1) )
            {
              v28 = cxl::TraceManager::Instance();
              HIDWORD(v30) = v26;
              LODWORD(v30) = 2;
              cxl::TextWriter::WriteLine<wchar_t,int,int>(
                (struct cxl::TraceManager *)((char *)v28 + 80),
                (wchar_t *)L"Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not get virtual server tok"
                            "en in GetCnoToken.");
            }
            else
            {
              cxl::Token::Clear(a2);
              *((_QWORD *)a2 + 1) = v27;
            }
          }
          else
          {
            v24 = (struct cxl::TraceManager *)((char *)cxl::TraceManager::Instance() + 80);
            v25 = std::wstring::wstring(v48, L"Network Name");
            v30 = 0x800713D600000002uLL;
            cxl::TextWriter::WriteLine<wchar_t,int,int,std::wstring>(
              v24,
              (wchar_t *)L"Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find any {2} resources in GetCnoToken.",
              v25);
            std::wstring::_Tidy_deallocate(v48);
          }
          if ( v39[1] )
            std::_Ref_count_base::_Decref(v39[1]);
          cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v50);
          cxl::PropertyList::~PropertyList((cxl::PropertyList *)v43);
          if ( v42[1] )
            std::_Ref_count_base::_Decref(v42[1]);
        }
        else
        {
          v19 = (char *)cxl::TraceManager::Instance() + 80;
          (*(void (__fastcall **)(char *, const wchar_t *, __int64))(*(_QWORD *)v19 + 24LL))(
            v19,
            L"Warning occurred in wsp_fs.dll - reason: Could not get the core cluster group type in GetCnoToken.",
            98);
          cxl::TextWriter::operator<<<cxl::ENDL>(v19);
          cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v50);
          cxl::PropertyList::~PropertyList((cxl::PropertyList *)v43);
        }
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
      }
      else
      {
        v16 = cxl::TraceManager::Instance();
        v30 = 0x800713B300000002uLL;
        cxl::TextWriter::WriteLine<wchar_t,int,int>(
          (struct cxl::TraceManager *)((char *)v16 + 80),
          (wchar_t *)L"Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find local cluster node in GetCnoToken.");
        cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v50);
        cxl::PropertyList::~PropertyList((cxl::PropertyList *)v43);
      }
      if ( v38[1] )
        std::_Ref_count_base::_Decref(v38[1]);
      goto LABEL_39;
    }
    v13 = cxl::TraceManager::Instance();
    v30 = value | 0x200000000LL;
    v31 = -2147024846;
    cxl::TextWriter::WriteLine<wchar_t,int,int,unsigned long>(
      (struct cxl::TraceManager *)((char *)v13 + 120),
      (__int64)&v30);
  }
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v50);
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v43);
LABEL_39:
  if ( v35[1] )
    std::_Ref_count_base::_Decref(v35[1]);
LABEL_41:
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  return a2;
}

```

## disassembly

```asm
0x18005a170  mov     [rsp-8+arg_0], rbx
0x18005a175  mov     [rsp-8+arg_10], rsi
0x18005a17a  push    rbp
0x18005a17b  push    rdi
0x18005a17c  push    r14
0x18005a17e  lea     rbp, [rsp-180h]
0x18005a186  sub     rsp, 280h
0x18005a18d  mov     rax, cs:__security_cookie
0x18005a194  xor     rax, rsp
0x18005a197  mov     [rbp+190h+var_20], rax
0x18005a19e  mov     r14, rdx
0x18005a1a1  mov     [rbp+190h+var_188], rdx
0x18005a1a5  mov     edi, 1
0x18005a1aa  mov     [rbp+190h+var_200], edi
0x18005a1ad  mov     qword ptr [rdx+8], 0
0x18005a1b5  mov     [rbp+190h+var_200], edi
0x18005a1b8  xorps   xmm0, xmm0
0x18005a1bb  movdqu  xmmword ptr [rsp+290h+var_220], xmm0
0x18005a1c1  movdqu  xmmword ptr [rbp+190h+var_210], xmm0
0x18005a1c6  movdqu  xmmword ptr [rbp+190h+var_1F8], xmm0
0x18005a1cb  movdqu  xmmword ptr [rbp+190h+var_1D8], xmm0
0x18005a1d0  movdqu  xmmword ptr [rbp+190h+var_1C0], xmm0
0x18005a1d5  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a1da  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18005a1de  call    ??$WriteLine@_W$$BY0CL@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CL@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [43],>(wchar_t const *,char const (&)[43])
0x18005a1e3  lea     rcx, [rsp+290h+var_230]
0x18005a1e8  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x18005a1ed  nop
0x18005a1ee  lea     rdx, [rsp+290h+var_220]
0x18005a1f3  mov     rcx, [rax]
0x18005a1f6  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x18005a1fb  mov     ebx, eax
0x18005a1fd  mov     rcx, [rsp+290h+var_228]; this
0x18005a202  test    rcx, rcx
0x18005a205  jz      short loc_18005A20C
0x18005a207  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a20c  test    ebx, ebx
0x18005a20e  jns     short loc_18005A241
0x18005a210  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a215  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18005a219  mov     [rsp+290h+var_238], ebx
0x18005a21d  mov     dword ptr [rsp+290h+var_240], 2
0x18005a225  lea     r9, [rsp+290h+var_238]
0x18005a22a  lea     r8, [rsp+290h+var_240]
0x18005a22f  lea     rdx, aInWspFsDllDoma_14; "In wsp_fs.dll - domain:{0} code:{1} rea"...
0x18005a236  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005a23b  nop
0x18005a23c  jmp     loc_18005A695
0x18005a241  lea     rdx, [rsp+290h+var_220]
0x18005a246  lea     rcx, [rsp+290h+var_230]
0x18005a24b  call    ?CreateClusterFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VClusterFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UICluster@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateClusterFacade(std::shared_ptr<ClusApi::ICluster> const &)
0x18005a250  mov     rdx, rax
0x18005a253  lea     rcx, [rbp+190h+var_210]
0x18005a257  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18005a25c  mov     rcx, [rsp+290h+var_228]; this
0x18005a261  test    rcx, rcx
0x18005a264  jz      short loc_18005A26B
0x18005a266  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a26b  lea     rcx, [rbp+190h+var_1B0]; this
0x18005a26f  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18005a274  nop
0x18005a275  lea     r8, [rbp+190h+var_1B0]
0x18005a279  mov     edx, edi
0x18005a27b  mov     rdi, [rbp+190h+var_210]
0x18005a27f  mov     rcx, rdi
0x18005a282  call    ?GetProperties@FacadeObject@Facade@ClusApi@@QEBAXW4_PropertyType@3@PEAVPropertyList@cxl@@@Z; ClusApi::Facade::FacadeObject::GetProperties(ClusApi::_PropertyType,cxl::PropertyList *)
0x18005a287  lea     rdx, aAdminaccesspoi; "AdminAccessPoint"
0x18005a28e  lea     rcx, [rbp+190h+var_160]
0x18005a292  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005a297  nop
0x18005a298  lea     r8, [rbp+190h+var_160]
0x18005a29c  lea     rdx, [rbp+190h+var_140]
0x18005a2a0  lea     rcx, [rbp+190h+var_1B0]
0x18005a2a4  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x18005a2a9  nop
0x18005a2aa  lea     rcx, [rbp+190h+var_160]
0x18005a2ae  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a2b3  lea     rdx, [rbp+190h+var_B0]
0x18005a2ba  lea     rcx, [rbp+190h+var_1B0]
0x18005a2be  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x18005a2c3  mov     rdx, rax
0x18005a2c6  lea     rcx, [rbp+190h+var_140]
0x18005a2ca  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x18005a2cf  mov     bl, al
0x18005a2d1  lea     rcx, [rbp+190h+var_B0]; this
0x18005a2d8  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005a2dd  test    bl, bl
0x18005a2df  jz      short loc_18005A32A
0x18005a2e1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a2e6  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18005a2ea  mov     dword ptr [rsp+290h+var_240], 80070032h
0x18005a2f2  mov     [rsp+290h+var_238], 2
0x18005a2fa  lea     r9, [rsp+290h+var_240]
0x18005a2ff  lea     r8, [rsp+290h+var_238]
0x18005a304  lea     rdx, aInWspFsDllDoma_12; "In wsp_fs.dll - domain:{0} code:{1} rea"...
0x18005a30b  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005a310  nop
0x18005a311  lea     rcx, [rbp+190h+var_140]; this
0x18005a315  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005a31a  nop
0x18005a31b  lea     rcx, [rbp+190h+var_1B0]; this
0x18005a31f  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18005a324  nop
0x18005a325  jmp     loc_18005A686
0x18005a32a  lea     rcx, [rbp+190h+var_140]
0x18005a32e  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x18005a333  mov     ebx, eax
0x18005a335  dec     eax
0x18005a337  test    eax, 0FFFFFFFDh
0x18005a33c  jz      short loc_18005A376
0x18005a33e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a343  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18005a347  mov     dword ptr [rsp+290h+var_240], ebx
0x18005a34b  mov     [rsp+290h+var_238], 80070032h
0x18005a353  mov     dword ptr [rsp+290h+var_240+4], 2
0x18005a35b  lea     rax, [rsp+290h+var_240]
0x18005a360  mov     [rsp+290h+var_270], rax; __int64
0x18005a365  lea     r9, [rsp+290h+var_238]
0x18005a36a  lea     r8, [rsp+290h+var_240+4]
0x18005a36f  call    ??$WriteLine@_WHHK@TextWriter@cxl@@QEAAXPEB_WAEBH1AEBK@Z; cxl::TextWriter::WriteLine<wchar_t,int,int,ulong>(wchar_t const *,int const &,int const &,ulong const &)
0x18005a374  jmp     short loc_18005A311
0x18005a376  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x18005a37d  lea     rdx, [rsp+290h+var_230]
0x18005a382  mov     rcx, rdi
0x18005a385  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x18005a38a  mov     rdx, rax
0x18005a38d  lea     rcx, [rbp+190h+var_1F8]
0x18005a391  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18005a396  mov     rcx, [rsp+290h+var_228]; this
0x18005a39b  test    rcx, rcx
0x18005a39e  jz      short loc_18005A3A5
0x18005a3a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a3a5  mov     rsi, [rbp+190h+var_1F8]
0x18005a3a9  test    rsi, rsi
0x18005a3ac  jnz     short loc_18005A3F7
0x18005a3ae  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a3b3  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18005a3b7  mov     dword ptr [rsp+290h+var_240+4], 800713B3h
0x18005a3bf  mov     dword ptr [rsp+290h+var_240], 2
0x18005a3c7  lea     r9, [rsp+290h+var_240+4]
0x18005a3cc  lea     r8, [rsp+290h+var_240]
0x18005a3d1  lea     rdx, aWarningOccurre_1; "Warning occurred in wsp_fs.dll - domain"...
0x18005a3d8  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005a3dd  nop
0x18005a3de  lea     rcx, [rbp+190h+var_140]; this
0x18005a3e2  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005a3e7  nop
0x18005a3e8  lea     rcx, [rbp+190h+var_1B0]; this
0x18005a3ec  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18005a3f1  nop
0x18005a3f2  jmp     loc_18005A677
0x18005a3f7  lea     rdx, [rsp+290h+var_230]
0x18005a3fc  mov     rcx, rdi
0x18005a3ff  call    ?GetCoreClusterGroup@ClusterFacade@Facade@ClusApi@@QEBA?AV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@XZ; ClusApi::Facade::ClusterFacade::GetCoreClusterGroup(void)
0x18005a404  mov     rdx, rax
0x18005a407  lea     rcx, [rbp+190h+var_1D8]
0x18005a40b  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18005a410  mov     rcx, [rsp+290h+var_228]; this
0x18005a415  test    rcx, rcx
0x18005a418  jz      short loc_18005A41F
0x18005a41a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a41f  mov     rbx, [rbp+190h+var_1D8]
0x18005a423  test    rbx, rbx
0x18005a426  jnz     short loc_18005A46F
0x18005a428  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a42d  lea     rbx, [rax+50h]
0x18005a431  mov     rax, [rbx]
0x18005a434  mov     r8d, 62h ; 'b'
0x18005a43a  lea     rdx, aWarningOccurre; "Warning occurred in wsp_fs.dll - reason"...
0x18005a441  mov     rcx, rbx
0x18005a444  mov     rax, [rax+18h]
0x18005a448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a44d  mov     rcx, rbx
0x18005a450  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18005a455  nop
0x18005a456  lea     rcx, [rbp+190h+var_140]; this
0x18005a45a  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005a45f  nop
0x18005a460  lea     rcx, [rbp+190h+var_1B0]; this
0x18005a464  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18005a469  nop
0x18005a46a  jmp     loc_18005A668
0x18005a46f  lea     rcx, [rbp+190h+var_180]
0x18005a473  call    ??$make_shared@VResourceTypeFilter@Facade@ClusApi@@AEAY0N@$$CB_W@std@@YA?AV?$shared_ptr@VResourceTypeFilter@Facade@ClusApi@@@0@AEAY0N@$$CB_W@Z; std::make_shared<ClusApi::Facade::ResourceTypeFilter,wchar_t const (&)[13]>(wchar_t const (&)[13])
0x18005a478  mov     rdx, rax
0x18005a47b  xorps   xmm0, xmm0
0x18005a47e  movdqu  xmmword ptr [rbp+190h+var_1E8], xmm0
0x18005a483  mov     rax, [rax]
0x18005a486  mov     [rbp+190h+var_1E8], rax
0x18005a48a  mov     rax, [rdx+8]
0x18005a48e  mov     [rbp+190h+var_1E8+8], rax
0x18005a492  mov     qword ptr [rdx], 0
0x18005a499  mov     qword ptr [rdx+8], 0
0x18005a4a1  mov     rcx, [rbp+190h+var_178]; this
0x18005a4a5  test    rcx, rcx
0x18005a4a8  jz      short loc_18005A4AF
0x18005a4aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a4af  lea     r8, [rbp+190h+var_1E8]
0x18005a4b3  lea     rdx, [rsp+290h+var_230]
0x18005a4b8  mov     rcx, rbx
0x18005a4bb  call    ?GetResources@GroupFacade@Facade@ClusApi@@QEBA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIResourceFilter@Facade@ClusApi@@@5@@Z; ClusApi::Facade::GroupFacade::GetResources(std::shared_ptr<ClusApi::Facade::IResourceFilter> const &)
0x18005a4c0  nop
0x18005a4c1  mov     rax, [rsp+290h+var_230]
0x18005a4c6  mov     rdx, [rax]
0x18005a4c9  cmp     rdx, rax
0x18005a4cc  jz      short loc_18005A4F6
0x18005a4ce  add     rdx, 10h
0x18005a4d2  lea     rcx, [rbp+190h+var_160]
0x18005a4d6  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x18005a4db  mov     rdx, rax
0x18005a4de  lea     rcx, [rbp+190h+var_1C0]
0x18005a4e2  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18005a4e7  mov     rcx, [rbp+190h+var_158]; this
0x18005a4eb  test    rcx, rcx
0x18005a4ee  jz      short loc_18005A4F6
0x18005a4f0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a4f5  nop
0x18005a4f6  mov     rdx, [rsp+290h+var_230]
0x18005a4fb  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x18005a500  mov     edx, 20h ; ' '
0x18005a505  mov     rcx, [rsp+290h+var_230]
0x18005a50a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005a50f  mov     rbx, [rbp+190h+var_1C0]
0x18005a513  test    rbx, rbx
0x18005a516  jnz     short loc_18005A56F
0x18005a518  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a51d  lea     rbx, [rax+50h]
0x18005a521  lea     rdx, aNetworkName; "Network Name"
0x18005a528  lea     rcx, [rbp+190h+var_160]
0x18005a52c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005a531  nop
0x18005a532  mov     dword ptr [rsp+290h+var_240+4], 800713D6h
0x18005a53a  mov     dword ptr [rsp+290h+var_240], 2
0x18005a542  mov     [rsp+290h+var_270], rax; __int64
0x18005a547  lea     r9, [rsp+290h+var_240+4]
0x18005a54c  lea     r8, [rsp+290h+var_240]
0x18005a551  lea     rdx, aWarningOccurre_0; "Warning occurred in wsp_fs.dll - domain"...
0x18005a558  mov     rcx, rbx; struct cxl::TextWriter *
0x18005a55b  call    ??$WriteLine@_WHHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEBH1AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,int,int,std::wstring>(wchar_t const *,int const &,int const &,std::wstring const &)
0x18005a560  nop
0x18005a561  lea     rcx, [rbp+190h+var_160]
0x18005a565  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a56a  jmp     loc_18005A636
0x18005a56f  mov     [rbp+190h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x18005a577  mov     [rbp+190h+var_1FC], 0
0x18005a57e  xor     eax, eax
0x18005a580  mov     [rbp+190h+var_170], rax
0x18005a584  mov     [rbp+190h+var_168], eax
0x18005a587  call    cs:__imp_GetCurrentProcessId
0x18005a58e  nop     dword ptr [rax+rax+00h]
0x18005a593  mov     dword ptr [rbp+190h+var_170], eax
0x18005a596  mov     [rbp+190h+var_170+4], 0Eh
0x18005a59e  mov     rcx, [rbx+38h]
0x18005a5a2  mov     rax, [rcx]
0x18005a5a5  lea     rdx, [rsi+28h]
0x18005a5a9  lea     r8, aStorwmiFilesha; "storwmi!FileShareFactory::GetCnoToken"
0x18005a5b0  mov     [rsp+290h+var_250], r8
0x18005a5b5  mov     [rsp+290h+var_258], rdx
0x18005a5ba  lea     rdx, [rbp+190h+var_1FC]
0x18005a5be  mov     [rsp+290h+var_260], rdx
0x18005a5c3  mov     [rsp+290h+var_268], 8
0x18005a5cb  lea     rdx, [rbp+190h+var_1C8]
0x18005a5cf  mov     [rsp+290h+var_270], rdx
0x18005a5d4  mov     r9d, 0Ch
0x18005a5da  lea     r8, [rbp+190h+var_170]
0x18005a5de  mov     edx, 100016Dh
0x18005a5e3  mov     rax, [rax+28h]
0x18005a5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5ec  mov     edi, eax
0x18005a5ee  test    eax, eax
0x18005a5f0  js      short loc_18005A60A
0x18005a5f2  mov     rbx, [rbp+190h+var_1C8]
0x18005a5f6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005a5fa  jz      short loc_18005A60A
0x18005a5fc  mov     rcx, r14; this
0x18005a5ff  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005a604  mov     [r14+8], rbx
0x18005a608  jmp     short loc_18005A636
0x18005a60a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005a60f  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18005a613  mov     dword ptr [rsp+290h+var_240+4], edi
0x18005a617  mov     dword ptr [rsp+290h+var_240], 2
0x18005a61f  lea     r9, [rsp+290h+var_240+4]
0x18005a624  lea     r8, [rsp+290h+var_240]
0x18005a629  lea     rdx, aWarningOccurre_2; "Warning occurred in wsp_fs.dll - domain"...
0x18005a630  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005a635  nop
0x18005a636  mov     rcx, [rbp+190h+var_1E8+8]; this
0x18005a63a  test    rcx, rcx
0x18005a63d  jz      short loc_18005A645
0x18005a63f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a644  nop
0x18005a645  lea     rcx, [rbp+190h+var_140]; this
0x18005a649  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005a64e  nop
0x18005a64f  lea     rcx, [rbp+190h+var_1B0]; this
0x18005a653  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18005a658  nop
0x18005a659  mov     rcx, [rbp+190h+var_1C0+8]; this
0x18005a65d  test    rcx, rcx
  ... truncated ...
```
