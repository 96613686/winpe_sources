# Wsp::Facade::FileShareFactory::GetClusterADDomain(void)

- ea: `0x1800587d0`
- end: `0x180058a1d`
- name: `?GetClusterADDomain@FileShareFactory@Facade@Wsp@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000c9dc`
- `0x18000d250`
- `0x18000d33c`
- `0x18000e6f4`
- `0x18001072c`
- `0x18001be30`
- `0x18001c424`
- `0x1800377a4`
- `0x180037868`
- `0x180037928`
- `0x18003c880`
- `0x180055bc0`
- `0x180055c50`
- `0x1800587d0`
- `0x1800a9010`

## import_xrefs

- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180058851`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180058851`
- `DSROLE!DsRoleFreeMemory` at `0x1800589d0`
- `DSROLE!DsRoleFreeMemory` at `0x1800589d0`

## string_xrefs

- `0x180058998`: `In wsp_fs.dll - domain:{0} code:{1} GetClusterADDomain - AD domain could not be read from clusdb`
- `0x18005888b`: `In wsp_fs.dll - GetClusterADDomain - AD Domain name is NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Wsp::Facade::FileShareFactory::GetClusterADDomain(__int64 a1, __int64 a2)
{
  struct cxl::TraceManager *v3; // rax
  char *v4; // rbx
  __int64 *Instance; // rax
  int Cluster; // ebx
  __int64 v7; // rax
  int String; // ebx
  struct cxl::TraceManager *v9; // rax
  struct cxl::TraceManager *v10; // rax
  PBYTE Buffer; // [rsp+30h] [rbp-D0h] BYREF
  int v13[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h]
  int v17[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  v16 = a2;
  Buffer = 0;
  v3 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [50],>(
    (struct cxl::TraceManager *)((char *)v3 + 120),
    (wchar_t *)L"{0}: Querying cluster for AD Domain.");
  std::wstring::wstring(a2);
  if ( DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) )
  {
    v10 = cxl::TraceManager::Instance();
    v17[0] = 0;
    cxl::TextWriter::WriteLine<wchar_t,int,unsigned long>((struct cxl::TraceManager *)((char *)v10 + 80));
  }
  else
  {
    if ( (*(_DWORD *)Buffer & 0xFFFFFFFD) != 0 )
    {
      if ( *((_QWORD *)Buffer + 2) )
      {
        std::wstring::assign(a2);
      }
      else
      {
        v4 = (char *)cxl::TraceManager::Instance() + 80;
        (*(void (__fastcall **)(char *, const wchar_t *, __int64))(*(_QWORD *)v4 + 24LL))(
          v4,
          L"In wsp_fs.dll - GetClusterADDomain - AD Domain name is NULL",
          59);
        cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v4);
      }
    }
    else
    {
      *(_OWORD *)v15 = 0;
      Instance = (__int64 *)ClusWmi::DataStore::GetInstance(v17);
      Cluster = ClusWmi::DataStore::GetCluster(*Instance, (__int64)v15);
      if ( v18 )
        std::_Ref_count_base::_Decref(v18);
      if ( Cluster < 0 )
      {
        v7 = std::wstring::wstring(v19, L"ClusWmi::DataStore::GetInstance()->GetCluster( &ptrCluster )");
        v17[0] = Cluster;
        v17[1] = 2;
        cxl::Exception::Exception(pExceptionObject, v17, v7);
        throw (cxl::Exception *)pExceptionObject;
      }
      ClusApi::ClusterClusterRegistry::ClusterClusterRegistry(v13, v15);
      std::wstring::wstring(v17, L"ADDomainName");
      String = ClusApi::ClusterRegistry::QueryString((int)v13, (int)v17);
      std::wstring::_Tidy_deallocate(v17);
      if ( String < 0 )
      {
        v9 = cxl::TraceManager::Instance();
        v17[0] = 2;
        cxl::TextWriter::WriteLine<wchar_t,int,int>(
          (struct cxl::TraceManager *)((char *)v9 + 120),
          (wchar_t *)L"In wsp_fs.dll - domain:{0} code:{1} GetClusterADDomain - AD domain could not be read from clusdb");
      }
      *(_QWORD *)v13 = &ClusApi::ClusterRegistry::`vftable';
      cxl::AutoHandle<HKEY__ *,long,&long ClusterRegCloseKey(HKEY__ *),0>::Close(v14);
      if ( v15[1] )
        std::_Ref_count_base::_Decref(v15[1]);
    }
    DsRoleFreeMemory(Buffer);
  }
  return a2;
}

```

## disassembly

```asm
0x1800587d0  mov     [rsp-8+arg_0], rbx
0x1800587d5  mov     [rsp-8+arg_10], rdi
0x1800587da  push    rbp
0x1800587db  lea     rbp, [rsp-20h]
0x1800587e0  sub     rsp, 120h
0x1800587e7  mov     rax, cs:__security_cookie
0x1800587ee  xor     rax, rsp
0x1800587f1  mov     [rbp+20h+var_10], rax
0x1800587f5  mov     rdi, rdx
0x1800587f8  mov     [rsp+120h+var_C8], rdx
0x1800587fd  mov     [rsp+120h+var_100], 0
0x180058805  mov     [rsp+120h+var_FC], 0
0x18005880d  mov     [rsp+120h+Buffer], 0
0x180058816  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005881b  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18005881f  lea     r8, aWspFacadeFiles_8; "Wsp::Facade::FileShareFactory::GetClust"...
0x180058826  lea     rdx, a0QueryingClust_2; "{0}: Querying cluster for AD Domain."
0x18005882d  call    ??$WriteLine@_W$$BY0DC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0DC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [50],>(wchar_t const *,char const (&)[50])
0x180058832  lea     rdx, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x180058839  mov     rcx, rdi
0x18005883c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180058841  mov     edx, 1; InfoLevel
0x180058846  mov     [rsp+120h+var_100], edx
0x18005884a  lea     r8, [rsp+120h+Buffer]; Buffer
0x18005884f  xor     ecx, ecx; lpServer
0x180058851  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180058857  mov     [rsp+120h+var_FC], eax
0x18005885b  test    eax, eax
0x18005885d  jnz     loc_1800589D8
0x180058863  mov     rax, [rsp+120h+Buffer]
0x180058868  test    dword ptr [rax], 0FFFFFFFDh
0x18005886e  jz      short loc_1800588B8
0x180058870  mov     rdx, [rax+10h]
0x180058874  test    rdx, rdx
0x180058877  jnz     short loc_1800588AB
0x180058879  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005887e  lea     rbx, [rax+50h]
0x180058882  mov     rax, [rbx]
0x180058885  mov     r8d, 3Bh ; ';'
0x18005888b  lea     rdx, aInWspFsDllGetc; "In wsp_fs.dll - GetClusterADDomain - AD"...
0x180058892  mov     rcx, rbx
0x180058895  mov     rax, [rax+18h]
0x180058899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005889e  mov     rcx, rbx
0x1800588a1  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x1800588a6  jmp     loc_1800589CB
0x1800588ab  mov     rcx, rdi
0x1800588ae  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800588b3  jmp     loc_1800589CB
0x1800588b8  xorps   xmm0, xmm0
0x1800588bb  movdqu  xmmword ptr [rsp+120h+var_D8], xmm0
0x1800588c1  lea     rcx, [rsp+120h+var_C0]
0x1800588c6  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800588cb  nop
0x1800588cc  lea     rdx, [rsp+120h+var_D8]
0x1800588d1  mov     rcx, [rax]
0x1800588d4  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x1800588d9  mov     ebx, eax
0x1800588db  mov     rcx, [rsp+120h+var_B8]; this
0x1800588e0  test    rcx, rcx
0x1800588e3  jz      short loc_1800588EA
0x1800588e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800588ea  test    ebx, ebx
0x1800588ec  jns     short loc_180058935
0x1800588ee  lea     rdx, aCluswmiDatasto; "ClusWmi::DataStore::GetInstance()->GetC"...
0x1800588f5  lea     rcx, [rbp+20h+var_A0]
0x1800588f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800588fe  nop
0x1800588ff  mov     [rsp+120h+var_C0], ebx
0x180058903  mov     [rsp+120h+var_BC], 2
0x18005890b  mov     r8, rax
0x18005890e  lea     rdx, [rsp+120h+var_C0]
0x180058913  lea     rcx, [rbp+20h+pExceptionObject]
0x180058917  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18005891c  mov     [rsp+120h+var_100], 3
0x180058924  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005892b  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005892f  call    _CxxThrowException_0
0x180058935  lea     rdx, [rsp+120h+var_D8]
0x18005893a  lea     rcx, [rsp+120h+var_E8]
0x18005893f  call    ??0ClusterClusterRegistry@ClusApi@@QEAA@AEBV?$shared_ptr@UICluster@ClusApi@@@std@@K@Z; ClusApi::ClusterClusterRegistry::ClusterClusterRegistry(std::shared_ptr<ClusApi::ICluster> const &,ulong)
0x180058944  nop
0x180058945  lea     rdx, aAddomainname; "ADDomainName"
0x18005894c  lea     rcx, [rsp+120h+var_C0]
0x180058951  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180058956  nop
0x180058957  mov     r8, rdi
0x18005895a  lea     rdx, [rsp+120h+var_C0]; int
0x18005895f  lea     rcx, [rsp+120h+var_E8]; int
0x180058964  call    ?QueryString@ClusterRegistry@ClusApi@@QEBAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV34@@Z; ClusApi::ClusterRegistry::QueryString(std::wstring const &,std::wstring *)
0x180058969  mov     ebx, eax
0x18005896b  lea     rcx, [rsp+120h+var_C0]
0x180058970  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058975  test    ebx, ebx
0x180058977  jns     short loc_1800589A5
0x180058979  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005897e  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x180058982  mov     [rsp+120h+var_F8], ebx
0x180058986  mov     [rsp+120h+var_C0], 2
0x18005898e  lea     r9, [rsp+120h+var_F8]
0x180058993  lea     r8, [rsp+120h+var_C0]
0x180058998  lea     rdx, aInWspFsDllDoma_3; "In wsp_fs.dll - domain:{0} code:{1} Get"...
0x18005899f  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x1800589a4  nop
0x1800589a5  lea     rax, ??_7ClusterRegistry@ClusApi@@6B@; const ClusApi::ClusterRegistry::`vftable'
0x1800589ac  mov     qword ptr [rsp+120h+var_E8], rax
0x1800589b1  lea     rcx, [rsp+120h+var_E0]
0x1800589b6  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?ClusterRegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&ClusterRegCloseKey(HKEY__ *),0>::Close(void)
0x1800589bb  nop
0x1800589bc  mov     rcx, [rsp+120h+var_D8+8]; this
0x1800589c1  test    rcx, rcx
0x1800589c4  jz      short loc_1800589CB
0x1800589c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800589cb  mov     rcx, [rsp+120h+Buffer]; Buffer
0x1800589d0  call    cs:__imp_DsRoleFreeMemory
0x1800589d6  jmp     short loc_1800589F8
0x1800589d8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800589dd  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x1800589e1  mov     [rsp+120h+var_C0], 0
0x1800589e9  lea     r9, [rsp+120h+var_FC]
0x1800589ee  lea     r8, [rsp+120h+var_C0]
0x1800589f3  call    ??$WriteLine@_WHK@TextWriter@cxl@@QEAAXPEB_WAEBHAEBK@Z; cxl::TextWriter::WriteLine<wchar_t,int,ulong>(wchar_t const *,int const &,ulong const &)
0x1800589f8  mov     rax, rdi
0x1800589fb  mov     rcx, [rbp+20h+var_10]
0x1800589ff  xor     rcx, rsp; StackCookie
0x180058a02  call    __security_check_cookie
0x180058a07  lea     r11, [rsp+120h+var_s0]
0x180058a0f  mov     rbx, [r11+10h]
0x180058a13  mov     rdi, [r11+20h]
0x180058a17  mov     rsp, r11
0x180058a1a  pop     rbp
0x180058a1b  retn
```
