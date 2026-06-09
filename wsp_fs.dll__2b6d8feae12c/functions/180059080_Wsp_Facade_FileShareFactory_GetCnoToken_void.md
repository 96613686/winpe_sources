# Wsp::Facade::FileShareFactory::GetCnoToken(void)

- ea: `0x180059080`
- end: `0x1800595d9`
- name: `?GetCnoToken@FileShareFactory@Facade@Wsp@@UEAA?AVToken@cxl@@XZ`
- size: `1369`
- prototype: `struct cxl::Token __high(void)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002a70`
- `0x180005d94`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c168`
- `0x18000c284`
- `0x18000c9dc`
- `0x18000e6f4`
- `0x1800154e0`
- `0x18001be30`
- `0x18001c424`
- `0x18003011c`
- `0x1800373cc`
- `0x180049b18`
- `0x18005597c`
- `0x180055bc0`
- `0x180055c00`
- `0x180056400`
- `0x1800568f8`
- `0x180059080`
- `0x180073ba4`
- `0x1800740c4`
- `0x180074508`
- `0x1800763a4`
- `0x18007648c`
- `0x18008d3b4`
- `0x18008d4a8`
- `0x18008fe50`
- `0x1800901c4`
- `0x180090334`
- `0x180090b5c`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180059497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180059497`

## string_xrefs

- `0x180059214`: `In wsp_fs.dll - domain:{0} code:{1} reason: Could not determine cluster management point type, assume no CNO token available for GetCnoToken.`
- `0x18005913f`: `In wsp_fs.dll - domain:{0} code:{1} reason: Failed to get cluster instance in GetCnoToken`
- `0x180059197`: `AdminAccessPoint`
- `0x180059461`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find any {2} resources in GetCnoToken.`
- `0x1800592e1`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not find local cluster node in GetCnoToken.`
- `0x18005934a`: `Warning occurred in wsp_fs.dll - reason: Could not get the core cluster group type in GetCnoToken.`
- `0x1800594b3`: `storwmi!FileShareFactory::GetCnoToken`
- `0x180059533`: `Warning occurred in wsp_fs.dll - domain:{0} code:{1} reason: Could not get virtual server token in GetCnoToken.`

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
          std::_Deallocate<16>(v32, 0x20u);
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
          cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v19);
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
0x180059080  mov     [rsp-8+arg_0], rbx
0x180059085  mov     [rsp-8+arg_10], rsi
0x18005908a  push    rbp
0x18005908b  push    rdi
0x18005908c  push    r14
0x18005908e  lea     rbp, [rsp-180h]
0x180059096  sub     rsp, 280h
0x18005909d  mov     rax, cs:__security_cookie
0x1800590a4  xor     rax, rsp
0x1800590a7  mov     [rbp+190h+var_20], rax
0x1800590ae  mov     r14, rdx
0x1800590b1  mov     [rbp+190h+var_188], rdx
0x1800590b5  mov     edi, 1
0x1800590ba  mov     [rbp+190h+var_200], edi
0x1800590bd  mov     qword ptr [rdx+8], 0
0x1800590c5  mov     [rbp+190h+var_200], edi
0x1800590c8  xorps   xmm0, xmm0
0x1800590cb  movdqu  xmmword ptr [rsp+290h+var_220], xmm0
0x1800590d1  movdqu  xmmword ptr [rbp+190h+var_210], xmm0
0x1800590d6  movdqu  xmmword ptr [rbp+190h+var_1F8], xmm0
0x1800590db  movdqu  xmmword ptr [rbp+190h+var_1D8], xmm0
0x1800590e0  movdqu  xmmword ptr [rbp+190h+var_1C0], xmm0
0x1800590e5  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800590ea  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800590ee  call    ??$WriteLine@_W$$BY0CL@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0CL@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [43],>(wchar_t const *,char const (&)[43])
0x1800590f3  lea     rcx, [rsp+290h+var_230]
0x1800590f8  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800590fd  nop
0x1800590fe  lea     rdx, [rsp+290h+var_220]
0x180059103  mov     rcx, [rax]
0x180059106  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x18005910b  mov     ebx, eax
0x18005910d  mov     rcx, [rsp+290h+var_228]; this
0x180059112  test    rcx, rcx
0x180059115  jz      short loc_18005911C
0x180059117  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005911c  test    ebx, ebx
0x18005911e  jns     short loc_180059151
0x180059120  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059125  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180059129  mov     [rsp+290h+var_238], ebx
0x18005912d  mov     dword ptr [rsp+290h+var_240], 2
0x180059135  lea     r9, [rsp+290h+var_238]
0x18005913a  lea     r8, [rsp+290h+var_240]
0x18005913f  lea     rdx, aInWspFsDllDoma_14; "In wsp_fs.dll - domain:{0} code:{1} rea"...
0x180059146  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005914b  nop
0x18005914c  jmp     loc_18005959F
0x180059151  lea     rdx, [rsp+290h+var_220]
0x180059156  lea     rcx, [rsp+290h+var_230]
0x18005915b  call    ?CreateClusterFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VClusterFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UICluster@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateClusterFacade(std::shared_ptr<ClusApi::ICluster> const &)
0x180059160  mov     rdx, rax
0x180059163  lea     rcx, [rbp+190h+var_210]
0x180059167  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x18005916c  mov     rcx, [rsp+290h+var_228]; this
0x180059171  test    rcx, rcx
0x180059174  jz      short loc_18005917B
0x180059176  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005917b  lea     rcx, [rbp+190h+var_1B0]; this
0x18005917f  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x180059184  nop
0x180059185  lea     r8, [rbp+190h+var_1B0]
0x180059189  mov     edx, edi
0x18005918b  mov     rdi, [rbp+190h+var_210]
0x18005918f  mov     rcx, rdi
0x180059192  call    ?GetProperties@FacadeObject@Facade@ClusApi@@QEBAXW4_PropertyType@3@PEAVPropertyList@cxl@@@Z; ClusApi::Facade::FacadeObject::GetProperties(ClusApi::_PropertyType,cxl::PropertyList *)
0x180059197  lea     rdx, aAdminaccesspoi; "AdminAccessPoint"
0x18005919e  lea     rcx, [rbp+190h+var_160]
0x1800591a2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800591a7  nop
0x1800591a8  lea     r8, [rbp+190h+var_160]
0x1800591ac  lea     rdx, [rbp+190h+var_140]
0x1800591b0  lea     rcx, [rbp+190h+var_1B0]
0x1800591b4  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x1800591b9  nop
0x1800591ba  lea     rcx, [rbp+190h+var_160]
0x1800591be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800591c3  lea     rdx, [rbp+190h+var_B0]
0x1800591ca  lea     rcx, [rbp+190h+var_1B0]
0x1800591ce  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x1800591d3  mov     rdx, rax
0x1800591d6  lea     rcx, [rbp+190h+var_140]
0x1800591da  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x1800591df  mov     bl, al
0x1800591e1  lea     rcx, [rbp+190h+var_B0]; this
0x1800591e8  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x1800591ed  test    bl, bl
0x1800591ef  jz      short loc_18005923A
0x1800591f1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800591f6  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x1800591fa  mov     dword ptr [rsp+290h+var_240], 80070032h
0x180059202  mov     [rsp+290h+var_238], 2
0x18005920a  lea     r9, [rsp+290h+var_240]
0x18005920f  lea     r8, [rsp+290h+var_238]
0x180059214  lea     rdx, aInWspFsDllDoma_12; "In wsp_fs.dll - domain:{0} code:{1} rea"...
0x18005921b  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x180059220  nop
0x180059221  lea     rcx, [rbp+190h+var_140]; this
0x180059225  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005922a  nop
0x18005922b  lea     rcx, [rbp+190h+var_1B0]; this
0x18005922f  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180059234  nop
0x180059235  jmp     loc_180059590
0x18005923a  lea     rcx, [rbp+190h+var_140]
0x18005923e  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x180059243  mov     ebx, eax
0x180059245  dec     eax
0x180059247  test    eax, 0FFFFFFFDh
0x18005924c  jz      short loc_180059286
0x18005924e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059253  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x180059257  mov     dword ptr [rsp+290h+var_240], ebx
0x18005925b  mov     [rsp+290h+var_238], 80070032h
0x180059263  mov     dword ptr [rsp+290h+var_240+4], 2
0x18005926b  lea     rax, [rsp+290h+var_240]
0x180059270  mov     [rsp+290h+var_270], rax; __int64
0x180059275  lea     r9, [rsp+290h+var_238]
0x18005927a  lea     r8, [rsp+290h+var_240+4]
0x18005927f  call    ??$WriteLine@_WHHK@TextWriter@cxl@@QEAAXPEB_WAEBH1AEBK@Z; cxl::TextWriter::WriteLine<wchar_t,int,int,ulong>(wchar_t const *,int const &,int const &,ulong const &)
0x180059284  jmp     short loc_180059221
0x180059286  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x18005928d  lea     rdx, [rsp+290h+var_230]
0x180059292  mov     rcx, rdi
0x180059295  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x18005929a  mov     rdx, rax
0x18005929d  lea     rcx, [rbp+190h+var_1F8]
0x1800592a1  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x1800592a6  mov     rcx, [rsp+290h+var_228]; this
0x1800592ab  test    rcx, rcx
0x1800592ae  jz      short loc_1800592B5
0x1800592b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800592b5  mov     rsi, [rbp+190h+var_1F8]
0x1800592b9  test    rsi, rsi
0x1800592bc  jnz     short loc_180059307
0x1800592be  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800592c3  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x1800592c7  mov     dword ptr [rsp+290h+var_240+4], 800713B3h
0x1800592cf  mov     dword ptr [rsp+290h+var_240], 2
0x1800592d7  lea     r9, [rsp+290h+var_240+4]
0x1800592dc  lea     r8, [rsp+290h+var_240]
0x1800592e1  lea     rdx, aWarningOccurre_1; "Warning occurred in wsp_fs.dll - domain"...
0x1800592e8  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x1800592ed  nop
0x1800592ee  lea     rcx, [rbp+190h+var_140]; this
0x1800592f2  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x1800592f7  nop
0x1800592f8  lea     rcx, [rbp+190h+var_1B0]; this
0x1800592fc  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180059301  nop
0x180059302  jmp     loc_180059581
0x180059307  lea     rdx, [rsp+290h+var_230]
0x18005930c  mov     rcx, rdi
0x18005930f  call    ?GetCoreClusterGroup@ClusterFacade@Facade@ClusApi@@QEBA?AV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@XZ; ClusApi::Facade::ClusterFacade::GetCoreClusterGroup(void)
0x180059314  mov     rdx, rax
0x180059317  lea     rcx, [rbp+190h+var_1D8]
0x18005931b  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x180059320  mov     rcx, [rsp+290h+var_228]; this
0x180059325  test    rcx, rcx
0x180059328  jz      short loc_18005932F
0x18005932a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005932f  mov     rbx, [rbp+190h+var_1D8]
0x180059333  test    rbx, rbx
0x180059336  jnz     short loc_18005937F
0x180059338  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005933d  lea     rbx, [rax+50h]
0x180059341  mov     rax, [rbx]
0x180059344  mov     r8d, 62h ; 'b'
0x18005934a  lea     rdx, aWarningOccurre; "Warning occurred in wsp_fs.dll - reason"...
0x180059351  mov     rcx, rbx
0x180059354  mov     rax, [rax+18h]
0x180059358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005935d  mov     rcx, rbx
0x180059360  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180059365  nop
0x180059366  lea     rcx, [rbp+190h+var_140]; this
0x18005936a  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18005936f  nop
0x180059370  lea     rcx, [rbp+190h+var_1B0]; this
0x180059374  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180059379  nop
0x18005937a  jmp     loc_180059572
0x18005937f  lea     rcx, [rbp+190h+var_180]
0x180059383  call    ??$make_shared@VResourceTypeFilter@Facade@ClusApi@@AEAY0N@$$CB_W@std@@YA?AV?$shared_ptr@VResourceTypeFilter@Facade@ClusApi@@@0@AEAY0N@$$CB_W@Z; std::make_shared<ClusApi::Facade::ResourceTypeFilter,wchar_t const (&)[13]>(wchar_t const (&)[13])
0x180059388  mov     rdx, rax
0x18005938b  xorps   xmm0, xmm0
0x18005938e  movdqu  xmmword ptr [rbp+190h+var_1E8], xmm0
0x180059393  mov     rax, [rax]
0x180059396  mov     [rbp+190h+var_1E8], rax
0x18005939a  mov     rax, [rdx+8]
0x18005939e  mov     [rbp+190h+var_1E8+8], rax
0x1800593a2  mov     qword ptr [rdx], 0
0x1800593a9  mov     qword ptr [rdx+8], 0
0x1800593b1  mov     rcx, [rbp+190h+var_178]; this
0x1800593b5  test    rcx, rcx
0x1800593b8  jz      short loc_1800593BF
0x1800593ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800593bf  lea     r8, [rbp+190h+var_1E8]
0x1800593c3  lea     rdx, [rsp+290h+var_230]
0x1800593c8  mov     rcx, rbx
0x1800593cb  call    ?GetResources@GroupFacade@Facade@ClusApi@@QEBA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIResourceFilter@Facade@ClusApi@@@5@@Z; ClusApi::Facade::GroupFacade::GetResources(std::shared_ptr<ClusApi::Facade::IResourceFilter> const &)
0x1800593d0  nop
0x1800593d1  mov     rax, [rsp+290h+var_230]
0x1800593d6  mov     rdx, [rax]
0x1800593d9  cmp     rdx, rax
0x1800593dc  jz      short loc_180059406
0x1800593de  add     rdx, 10h
0x1800593e2  lea     rcx, [rbp+190h+var_160]
0x1800593e6  call    ?CreateResourceFacade@FacadeFactory@Facade@ClusApi@@SA?AV?$shared_ptr@VResourceFacade@Facade@ClusApi@@@std@@AEBV?$shared_ptr@UIResource@ClusApi@@@5@@Z; ClusApi::Facade::FacadeFactory::CreateResourceFacade(std::shared_ptr<ClusApi::IResource> const &)
0x1800593eb  mov     rdx, rax
0x1800593ee  lea     rcx, [rbp+190h+var_1C0]
0x1800593f2  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x1800593f7  mov     rcx, [rbp+190h+var_158]; this
0x1800593fb  test    rcx, rcx
0x1800593fe  jz      short loc_180059406
0x180059400  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180059405  nop
0x180059406  mov     rdx, [rsp+290h+var_230]
0x18005940b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x180059410  mov     edx, 20h ; ' '
0x180059415  mov     rcx, [rsp+290h+var_230]
0x18005941a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005941f  mov     rbx, [rbp+190h+var_1C0]
0x180059423  test    rbx, rbx
0x180059426  jnz     short loc_18005947F
0x180059428  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005942d  lea     rbx, [rax+50h]
0x180059431  lea     rdx, aNetworkName; "Network Name"
0x180059438  lea     rcx, [rbp+190h+var_160]
0x18005943c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180059441  nop
0x180059442  mov     dword ptr [rsp+290h+var_240+4], 800713D6h
0x18005944a  mov     dword ptr [rsp+290h+var_240], 2
0x180059452  mov     [rsp+290h+var_270], rax; __int64
0x180059457  lea     r9, [rsp+290h+var_240+4]
0x18005945c  lea     r8, [rsp+290h+var_240]
0x180059461  lea     rdx, aWarningOccurre_0; "Warning occurred in wsp_fs.dll - domain"...
0x180059468  mov     rcx, rbx; struct cxl::TextWriter *
0x18005946b  call    ??$WriteLine@_WHHV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEBH1AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::WriteLine<wchar_t,int,int,std::wstring>(wchar_t const *,int const &,int const &,std::wstring const &)
0x180059470  nop
0x180059471  lea     rcx, [rbp+190h+var_160]
0x180059475  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005947a  jmp     loc_180059540
0x18005947f  mov     [rbp+190h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x180059487  mov     [rbp+190h+var_1FC], 0
0x18005948e  xor     eax, eax
0x180059490  mov     [rbp+190h+var_170], rax
0x180059494  mov     [rbp+190h+var_168], eax
0x180059497  call    cs:__imp_GetCurrentProcessId
0x18005949d  mov     dword ptr [rbp+190h+var_170], eax
0x1800594a0  mov     [rbp+190h+var_170+4], 0Eh
0x1800594a8  mov     rcx, [rbx+38h]
0x1800594ac  mov     rax, [rcx]
0x1800594af  lea     rdx, [rsi+28h]
0x1800594b3  lea     r8, aStorwmiFilesha; "storwmi!FileShareFactory::GetCnoToken"
0x1800594ba  mov     [rsp+290h+var_250], r8
0x1800594bf  mov     [rsp+290h+var_258], rdx
0x1800594c4  lea     rdx, [rbp+190h+var_1FC]
0x1800594c8  mov     [rsp+290h+var_260], rdx
0x1800594cd  mov     [rsp+290h+var_268], 8
0x1800594d5  lea     rdx, [rbp+190h+var_1C8]
0x1800594d9  mov     [rsp+290h+var_270], rdx
0x1800594de  mov     r9d, 0Ch
0x1800594e4  lea     r8, [rbp+190h+var_170]
0x1800594e8  mov     edx, 100016Dh
0x1800594ed  mov     rax, [rax+28h]
0x1800594f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f6  mov     edi, eax
0x1800594f8  test    eax, eax
0x1800594fa  js      short loc_180059514
0x1800594fc  mov     rbx, [rbp+190h+var_1C8]
0x180059500  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180059504  jz      short loc_180059514
0x180059506  mov     rcx, r14; this
0x180059509  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005950e  mov     [r14+8], rbx
0x180059512  jmp     short loc_180059540
0x180059514  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059519  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18005951d  mov     dword ptr [rsp+290h+var_240+4], edi
0x180059521  mov     dword ptr [rsp+290h+var_240], 2
0x180059529  lea     r9, [rsp+290h+var_240+4]
0x18005952e  lea     r8, [rsp+290h+var_240]
0x180059533  lea     rdx, aWarningOccurre_2; "Warning occurred in wsp_fs.dll - domain"...
0x18005953a  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x18005953f  nop
0x180059540  mov     rcx, [rbp+190h+var_1E8+8]; this
0x180059544  test    rcx, rcx
0x180059547  jz      short loc_18005954F
0x180059549  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005954e  nop
0x18005954f  lea     rcx, [rbp+190h+var_140]; this
0x180059553  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x180059558  nop
0x180059559  lea     rcx, [rbp+190h+var_1B0]; this
0x18005955d  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180059562  nop
0x180059563  mov     rcx, [rbp+190h+var_1C0+8]; this
0x180059567  test    rcx, rcx
0x18005956a  jz      short loc_180059572
  ... truncated ...
```
