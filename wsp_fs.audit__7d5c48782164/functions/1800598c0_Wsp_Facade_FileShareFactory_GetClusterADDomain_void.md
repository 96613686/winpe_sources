# Wsp::Facade::FileShareFactory::GetClusterADDomain(void)

- ea: `0x1800598c0`
- end: `0x180059b19`
- name: `?GetClusterADDomain@FileShareFactory@Facade@Wsp@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000cd24`
- `0x18000d5b8`
- `0x18000d6a4`
- `0x18000eb18`
- `0x180010b90`
- `0x18001c8f0`
- `0x18001cf18`
- `0x180038a7c`
- `0x180038b4c`
- `0x180038c1c`
- `0x18003dbcc`
- `0x180056c40`
- `0x180056cd0`
- `0x1800598c0`
- `0x1800ab010`

## import_xrefs

- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180059941`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180059941`
- `DSROLE!DsRoleFreeMemory` at `0x180059ac6`
- `DSROLE!DsRoleFreeMemory` at `0x180059ac6`

## string_xrefs

- `0x180059981`: `In wsp_fs.dll - GetClusterADDomain - AD Domain name is NULL`
- `0x180059a8e`: `In wsp_fs.dll - domain:{0} code:{1} GetClusterADDomain - AD domain could not be read from clusdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Wsp::Facade::FileShareFactory::GetClusterADDomain(__int64 a1, __int64 a2)
{
  struct cxl::TraceManager *v3; // rax
  __int64 v4; // rdx
  char *v5; // rbx
  __int64 *Instance; // rax
  int Cluster; // ebx
  __int64 v8; // rax
  int String; // ebx
  struct cxl::TraceManager *v10; // rax
  struct cxl::TraceManager *v11; // rax
  PBYTE Buffer; // [rsp+30h] [rbp-D0h] BYREF
  int v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v19; // [rsp+68h] [rbp-98h]
  _BYTE v20[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  v17 = a2;
  Buffer = 0;
  v3 = cxl::TraceManager::Instance();
  cxl::TextWriter::WriteLine<wchar_t,char [50],>(
    (struct cxl::TraceManager *)((char *)v3 + 120),
    (wchar_t *)L"{0}: Querying cluster for AD Domain.");
  std::wstring::wstring(a2, cxl::EmptyLiteral);
  if ( DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) )
  {
    v11 = cxl::TraceManager::Instance();
    v18[0] = 0;
    cxl::TextWriter::WriteLine<wchar_t,int,unsigned long>((struct cxl::TraceManager *)((char *)v11 + 80));
  }
  else
  {
    if ( (*(_DWORD *)Buffer & 0xFFFFFFFD) != 0 )
    {
      v4 = *((_QWORD *)Buffer + 2);
      if ( v4 )
      {
        std::wstring::assign(a2, v4);
      }
      else
      {
        v5 = (char *)cxl::TraceManager::Instance() + 80;
        (*(void (__fastcall **)(char *, const wchar_t *, __int64))(*(_QWORD *)v5 + 24LL))(
          v5,
          L"In wsp_fs.dll - GetClusterADDomain - AD Domain name is NULL",
          59);
        cxl::TextWriter::operator<<<cxl::ENDL>(v5);
      }
    }
    else
    {
      *(_OWORD *)v16 = 0;
      Instance = (__int64 *)ClusWmi::DataStore::GetInstance(v18);
      Cluster = ClusWmi::DataStore::GetCluster(*Instance, (__int64)v16);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      if ( Cluster < 0 )
      {
        v8 = std::wstring::wstring(v20, L"ClusWmi::DataStore::GetInstance()->GetCluster( &ptrCluster )");
        v18[0] = Cluster;
        v18[1] = 2;
        cxl::Exception::Exception(pExceptionObject, v18, v8);
        throw (cxl::Exception *)pExceptionObject;
      }
      ClusApi::ClusterClusterRegistry::ClusterClusterRegistry(v14, v16);
      std::wstring::wstring(v18, L"ADDomainName");
      String = ClusApi::ClusterRegistry::QueryString((int)v14, (int)v18);
      std::wstring::_Tidy_deallocate(v18);
      if ( String < 0 )
      {
        v10 = cxl::TraceManager::Instance();
        v18[0] = 2;
        cxl::TextWriter::WriteLine<wchar_t,int,int>(
          (struct cxl::TraceManager *)((char *)v10 + 120),
          (wchar_t *)L"In wsp_fs.dll - domain:{0} code:{1} GetClusterADDomain - AD domain could not be read from clusdb");
      }
      *(_QWORD *)v14 = &ClusApi::ClusterRegistry::`vftable';
      cxl::AutoHandle<HKEY__ *,long,&long ClusterRegCloseKey(HKEY__ *),0>::Close(v15);
      if ( v16[1] )
        std::_Ref_count_base::_Decref(v16[1]);
    }
    DsRoleFreeMemory(Buffer);
  }
  return a2;
}

```

## disassembly

```asm
0x1800598c0  mov     [rsp-8+arg_0], rbx
0x1800598c5  mov     [rsp-8+arg_10], rdi
0x1800598ca  push    rbp
0x1800598cb  lea     rbp, [rsp-20h]
0x1800598d0  sub     rsp, 120h
0x1800598d7  mov     rax, cs:__security_cookie
0x1800598de  xor     rax, rsp
0x1800598e1  mov     [rbp+20h+var_10], rax
0x1800598e5  mov     rdi, rdx
0x1800598e8  mov     [rsp+120h+var_C8], rdx
0x1800598ed  mov     [rsp+120h+var_100], 0
0x1800598f5  mov     [rsp+120h+var_FC], 0
0x1800598fd  mov     [rsp+120h+Buffer], 0
0x180059906  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005990b  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x18005990f  lea     r8, aWspFacadeFiles_8; "Wsp::Facade::FileShareFactory::GetClust"...
0x180059916  lea     rdx, a0QueryingClust_2; "{0}: Querying cluster for AD Domain."
0x18005991d  call    ??$WriteLine@_W$$BY0DC@D$$V@TextWriter@cxl@@QEAAXPEB_WAEAY0DC@$$CBD@Z; cxl::TextWriter::WriteLine<wchar_t,char [50],>(wchar_t const *,char const (&)[50])
0x180059922  lea     rdx, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x180059929  mov     rcx, rdi
0x18005992c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180059931  mov     edx, 1; InfoLevel
0x180059936  mov     [rsp+120h+var_100], edx
0x18005993a  lea     r8, [rsp+120h+Buffer]; Buffer
0x18005993f  xor     ecx, ecx; lpServer
0x180059941  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180059948  nop     dword ptr [rax+rax+00h]
0x18005994d  mov     [rsp+120h+var_FC], eax
0x180059951  test    eax, eax
0x180059953  jnz     loc_180059AD4
0x180059959  mov     rax, [rsp+120h+Buffer]
0x18005995e  test    dword ptr [rax], 0FFFFFFFDh
0x180059964  jz      short loc_1800599AE
0x180059966  mov     rdx, [rax+10h]
0x18005996a  test    rdx, rdx
0x18005996d  jnz     short loc_1800599A1
0x18005996f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059974  lea     rbx, [rax+50h]
0x180059978  mov     rax, [rbx]
0x18005997b  mov     r8d, 3Bh ; ';'
0x180059981  lea     rdx, aInWspFsDllGetc; "In wsp_fs.dll - GetClusterADDomain - AD"...
0x180059988  mov     rcx, rbx
0x18005998b  mov     rax, [rax+18h]
0x18005998f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059994  mov     rcx, rbx
0x180059997  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18005999c  jmp     loc_180059AC1
0x1800599a1  mov     rcx, rdi
0x1800599a4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800599a9  jmp     loc_180059AC1
0x1800599ae  xorps   xmm0, xmm0
0x1800599b1  movdqu  xmmword ptr [rsp+120h+var_D8], xmm0
0x1800599b7  lea     rcx, [rsp+120h+var_C0]
0x1800599bc  call    ?GetInstance@DataStore@ClusWmi@@SA?AV?$shared_ptr@VDataStore@ClusWmi@@@std@@XZ; ClusWmi::DataStore::GetInstance(void)
0x1800599c1  nop
0x1800599c2  lea     rdx, [rsp+120h+var_D8]
0x1800599c7  mov     rcx, [rax]
0x1800599ca  call    ?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z; ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)
0x1800599cf  mov     ebx, eax
0x1800599d1  mov     rcx, [rsp+120h+var_B8]; this
0x1800599d6  test    rcx, rcx
0x1800599d9  jz      short loc_1800599E0
0x1800599db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800599e0  test    ebx, ebx
0x1800599e2  jns     short loc_180059A2B
0x1800599e4  lea     rdx, aCluswmiDatasto; "ClusWmi::DataStore::GetInstance()->GetC"...
0x1800599eb  lea     rcx, [rbp+20h+var_A0]
0x1800599ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800599f4  nop
0x1800599f5  mov     [rsp+120h+var_C0], ebx
0x1800599f9  mov     [rsp+120h+var_BC], 2
0x180059a01  mov     r8, rax
0x180059a04  lea     rdx, [rsp+120h+var_C0]
0x180059a09  lea     rcx, [rbp+20h+pExceptionObject]
0x180059a0d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180059a12  mov     [rsp+120h+var_100], 3
0x180059a1a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180059a21  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x180059a25  call    _CxxThrowException_0
0x180059a2b  lea     rdx, [rsp+120h+var_D8]
0x180059a30  lea     rcx, [rsp+120h+var_E8]
0x180059a35  call    ??0ClusterClusterRegistry@ClusApi@@QEAA@AEBV?$shared_ptr@UICluster@ClusApi@@@std@@K@Z; ClusApi::ClusterClusterRegistry::ClusterClusterRegistry(std::shared_ptr<ClusApi::ICluster> const &,ulong)
0x180059a3a  nop
0x180059a3b  lea     rdx, aAddomainname; "ADDomainName"
0x180059a42  lea     rcx, [rsp+120h+var_C0]
0x180059a47  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180059a4c  nop
0x180059a4d  mov     r8, rdi
0x180059a50  lea     rdx, [rsp+120h+var_C0]; int
0x180059a55  lea     rcx, [rsp+120h+var_E8]; int
0x180059a5a  call    ?QueryString@ClusterRegistry@ClusApi@@QEBAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV34@@Z; ClusApi::ClusterRegistry::QueryString(std::wstring const &,std::wstring *)
0x180059a5f  mov     ebx, eax
0x180059a61  lea     rcx, [rsp+120h+var_C0]
0x180059a66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180059a6b  test    ebx, ebx
0x180059a6d  jns     short loc_180059A9B
0x180059a6f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059a74  lea     rcx, [rax+78h]; struct cxl::TextWriter *
0x180059a78  mov     [rsp+120h+var_F8], ebx
0x180059a7c  mov     [rsp+120h+var_C0], 2
0x180059a84  lea     r9, [rsp+120h+var_F8]
0x180059a89  lea     r8, [rsp+120h+var_C0]
0x180059a8e  lea     rdx, aInWspFsDllDoma_3; "In wsp_fs.dll - domain:{0} code:{1} Get"...
0x180059a95  call    ??$WriteLine@_WHH@TextWriter@cxl@@QEAAXPEB_WAEBH1@Z; cxl::TextWriter::WriteLine<wchar_t,int,int>(wchar_t const *,int const &,int const &)
0x180059a9a  nop
0x180059a9b  lea     rax, ??_7ClusterRegistry@ClusApi@@6B@; const ClusApi::ClusterRegistry::`vftable'
0x180059aa2  mov     qword ptr [rsp+120h+var_E8], rax
0x180059aa7  lea     rcx, [rsp+120h+var_E0]
0x180059aac  call    ?Close@?$AutoHandle@PEAUHKEY__@@J$1?ClusterRegCloseKey@@YAJPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<HKEY__ *,long,&ClusterRegCloseKey(HKEY__ *),0>::Close(void)
0x180059ab1  nop
0x180059ab2  mov     rcx, [rsp+120h+var_D8+8]; this
0x180059ab7  test    rcx, rcx
0x180059aba  jz      short loc_180059AC1
0x180059abc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180059ac1  mov     rcx, [rsp+120h+Buffer]; Buffer
0x180059ac6  call    cs:__imp_DsRoleFreeMemory
0x180059acd  nop     dword ptr [rax+rax+00h]
0x180059ad2  jmp     short loc_180059AF4
0x180059ad4  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180059ad9  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180059add  mov     [rsp+120h+var_C0], 0
0x180059ae5  lea     r9, [rsp+120h+var_FC]
0x180059aea  lea     r8, [rsp+120h+var_C0]
0x180059aef  call    ??$WriteLine@_WHK@TextWriter@cxl@@QEAAXPEB_WAEBHAEBK@Z; cxl::TextWriter::WriteLine<wchar_t,int,ulong>(wchar_t const *,int const &,ulong const &)
0x180059af4  mov     rax, rdi
0x180059af7  mov     rcx, [rbp+20h+var_10]
0x180059afb  xor     rcx, rsp; StackCookie
0x180059afe  call    __security_check_cookie
0x180059b03  lea     r11, [rsp+120h+var_s0]
0x180059b0b  mov     rbx, [r11+10h]
0x180059b0f  mov     rdi, [r11+20h]
0x180059b13  mov     rsp, r11
0x180059b16  pop     rbp
0x180059b17  retn
```
