# ClusApi::Facade::ActionFactory::CreateGroupDeleteExecutor(std::shared_ptr<ClusApi::Facade::GroupFacade> const &,bool,std::shared_ptr<ClusApi::Facade::ActionExecutor> *)

- ea: `0x180095ef4`
- end: `0x180096540`
- name: `?CreateGroupDeleteExecutor@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@_NPEAV?$shared_ptr@VActionExecutor@Facade@ClusApi@@@5@@Z`
- size: `1612`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x18008f99c`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x1800034a4`
- `0x180005d94`
- `0x180005e68`
- `0x18000c168`
- `0x18000c284`
- `0x18000d33c`
- `0x1800192f0`
- `0x18004f834`
- `0x180056400`
- `0x180090b5c`
- `0x180092bc8`
- `0x180095848`
- `0x1800958f0`
- `0x1800959b4`
- `0x180095a5c`
- `0x180095b30`
- `0x180095cb8`
- `0x180095ef4`
- `0x18009669c`
- `0x1800a9010`

## string_xrefs

- `0x1800962e4`: `CreateDeleteGroupActionItem( ptrGroup, force, &ptrDeleteGroupItem )`
- `0x1800961d9`: `CreateActionExecutor( &ptrActionExec )`
- `0x180096033`: `CreateDeleteVmActionItem( ptrGroup->Cluster, ptrGroup, &ptrGroupActionItem )`
- `0x180096110`: `CreateDeleteStorageActionItem( ptrGroup->Cluster, &ptrStorageItem )`
- `0x1800960a4`: `CreateDeleteDfsnActionItem( ptrGroup->Cluster, &ptrGroupActionItem )`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall ClusApi::Facade::ActionFactory::CreateGroupDeleteExecutor(
        ClusApi::Facade::GroupFacade **a1,
        char a2,
        __int64 a3)
{
  __int64 v3; // r12
  ClusApi::Facade::GroupFacade **v4; // r14
  unsigned int v5; // edi
  enum CLUSGROUP_TYPE type; // ebx
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ebx
  __int64 v16; // rax
  std::_Ref_count_base *v17; // rsi
  std::_Ref_count_base *v18; // rbx
  std::_Ref_count_base *v19; // r15
  std::_Ref_count_base *v20; // r13
  _DWORD *v21; // rbx
  __int64 v22; // rax
  int v23; // edi
  __int64 v24; // rax
  std::_Ref_count_base *v25; // rcx
  __int64 result; // rax
  int v27; // r12d
  __int64 v28; // rax
  int v29; // r12d
  __int64 v30; // rax
  const cxl::Exception *v31; // rbx
  unsigned int Hr; // [rsp+20h] [rbp-448h] BYREF
  int v33; // [rsp+24h] [rbp-444h]
  char v34[8]; // [rsp+28h] [rbp-440h] BYREF
  __int64 v35; // [rsp+30h] [rbp-438h] BYREF
  std::_Ref_count_base *v36[2]; // [rsp+38h] [rbp-430h] BYREF
  std::_Ref_count_base *v37[2]; // [rsp+48h] [rbp-420h] BYREF
  _DWORD v38[2]; // [rsp+58h] [rbp-410h] BYREF
  _DWORD v39[2]; // [rsp+60h] [rbp-408h] BYREF
  std::_Ref_count_base *v40; // [rsp+68h] [rbp-400h]
  std::_Ref_count_base *v41[2]; // [rsp+70h] [rbp-3F8h] BYREF
  std::_Ref_count_base *v42[2]; // [rsp+80h] [rbp-3E8h] BYREF
  ClusApi::Facade::GroupFacade **v43; // [rsp+90h] [rbp-3D8h]
  __int64 v44; // [rsp+98h] [rbp-3D0h]
  std::_Ref_count_base *v45[2]; // [rsp+A0h] [rbp-3C8h] BYREF
  std::_Ref_count_base *v46; // [rsp+B0h] [rbp-3B8h] BYREF
  const cxl::Exception *v47; // [rsp+C0h] [rbp-3A8h] BYREF
  std::_Ref_count_base **v48; // [rsp+C8h] [rbp-3A0h] BYREF
  std::_Ref_count_base *v49[2]; // [rsp+D0h] [rbp-398h] BYREF
  _BYTE v50[32]; // [rsp+F0h] [rbp-378h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+110h] [rbp-358h] BYREF
  _BYTE v52[112]; // [rsp+180h] [rbp-2E8h] BYREF
  _BYTE v53[112]; // [rsp+1F0h] [rbp-278h] BYREF
  _BYTE v54[112]; // [rsp+260h] [rbp-208h] BYREF
  _BYTE v55[112]; // [rsp+2D0h] [rbp-198h] BYREF
  _BYTE v56[112]; // [rsp+340h] [rbp-128h] BYREF
  _BYTE v57[112]; // [rsp+3B0h] [rbp-B8h] BYREF

  v3 = a3;
  v35 = a3;
  v4 = a1;
  v43 = a1;
  v44 = a3;
  v5 = 0;
  Hr = 0;
  if ( !*a1 || !a3 )
    return 2147942487LL;
  try
  {
    *(_OWORD *)v42 = 0;
    type = ClusApi::Facade::GroupFacade::get_type(*a1);
    *(_OWORD *)v49 = 0;
    ClusApi::Facade::GroupFacade::GetResources(*v4, &v46, v49);
    if ( v49[1] )
      std::_Ref_count_base::_Decref(v49[1]);
    *(_OWORD *)v37 = 0;
    *(_OWORD *)v41 = 0;
    *(_OWORD *)v45 = 0;
    if ( type == ClusGroupTypeVirtualMachine )
    {
      v7 = (**(__int64 (__fastcall ***)(ClusApi::Facade::GroupFacade *))*v4)(*v4);
      *(_OWORD *)v36 = 0;
      v8 = ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteVmActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,std::shared_ptr<ClusApi::Facade::GroupFacade>>(
             v7,
             (__int64)v4,
             v36);
      if ( v8 >= 0 )
      {
        v9 = std::dynamic_pointer_cast<ClusApi::Facade::IResourceActionItem,ClusApi::Facade::IActionItem>(v49, v36);
        std::shared_ptr<ClusWmi::DataStore>::operator=(v37, v9);
        if ( v49[1] )
          std::_Ref_count_base::_Decref(v49[1]);
      }
      if ( v36[1] )
        std::_Ref_count_base::_Decref(v36[1]);
      if ( v8 < 0 )
      {
        Hr = v8;
        v33 = 2;
        v10 = std::wstring::wstring(
                v49,
                L"CreateDeleteVmActionItem( ptrGroup->Cluster, ptrGroup, &ptrGroupActionItem )");
        cxl::Exception::Exception(pExceptionObject, &Hr, v10);
        throw (cxl::Exception *)pExceptionObject;
      }
    }
    else if ( type == ClusGroupTypeStandAloneDfs )
    {
      v11 = (**(__int64 (__fastcall ***)(ClusApi::Facade::GroupFacade *))*v4)(*v4);
      v12 = ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteDfsnActionItem>::CreateResourceActionItem<std::shared_ptr<ClusApi::ICluster>>(
              v11,
              (__int64)v37);
      if ( v12 < 0 )
      {
        v13 = std::wstring::wstring(v49, L"CreateDeleteDfsnActionItem( ptrGroup->Cluster, &ptrGroupActionItem )");
        Hr = v12;
        v33 = 2;
        cxl::Exception::Exception(v52, &Hr, v13);
        throw (cxl::Exception *)v52;
      }
    }
    v14 = (**(__int64 (__fastcall ***)(ClusApi::Facade::GroupFacade *))*v4)(*v4);
    v15 = ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteStorageActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,ClusApi::Facade::StorageMoveGroupLogic>(
            v14,
            v41);
    if ( v15 < 0 )
    {
      v16 = std::wstring::wstring(v49, L"CreateDeleteStorageActionItem( ptrGroup->Cluster, &ptrStorageItem )");
      Hr = v15;
      v33 = 2;
      cxl::Exception::Exception(v53, &Hr, v16);
      throw (cxl::Exception *)v53;
    }
    v17 = v46;
    v18 = *(std::_Ref_count_base **)v46;
    v36[0] = v46;
    v19 = v37[0];
    v20 = v41[0];
    while ( 1 )
    {
      v40 = v18;
      if ( v18 == v17 )
        break;
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v49, (_QWORD *)v18 + 2);
      try
      {
        if ( v19 )
        {
          v27 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v19 + 16LL))(
                  v19,
                  v49);
          if ( v27 < 0 )
          {
            v28 = std::wstring::wstring(v50, L"ptrGroupActionItem->AddResource( ptrRes )");
            v38[0] = v27;
            v38[1] = 2;
            cxl::Exception::Exception(v56, v38, v28);
            Hr = v5 | 8;
            throw (cxl::Exception *)v56;
          }
        }
        v29 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base **))(*(_QWORD *)v20 + 16LL))(
                v20,
                v49);
        if ( v29 < 0 )
        {
          v30 = std::wstring::wstring(v50, L"ptrStorageItem->AddResource( ptrRes )");
          v39[0] = v29;
          v39[1] = 2;
          cxl::Exception::Exception(v57, v39, v30);
          Hr = v5 | 0x10;
          throw (cxl::Exception *)v57;
        }
      }
      catch ( const cxl::Exception *v47 )
      {
        v31 = v47;
        v35 = *((_QWORD *)v47 + 11);
        if ( cxl::ErrorCode::GetWinError((cxl::ErrorCode *)&v35) != 5007 )
        {
          v35 = *((_QWORD *)v31 + 11);
          if ( cxl::ErrorCode::GetWinError((cxl::ErrorCode *)&v35) != 5006 )
            throw;
        }
        v19 = v37[0];
        v20 = v41[0];
        v18 = v40;
        v5 = Hr;
        v4 = v43;
        v3 = v44;
        v35 = v44;
        v17 = v36[0];
        goto LABEL_48;
      }
      v3 = v35;
LABEL_48:
      if ( v49[1] )
        std::_Ref_count_base::_Decref(v49[1]);
      v18 = *(std::_Ref_count_base **)v18;
    }
    v21 = operator new(0x38u);
    v36[0] = (std::_Ref_count_base *)v21;
    v21[2] = 1;
    v21[3] = 1;
    *(_QWORD *)v21 = &std::_Ref_count_obj2<ClusApi::Facade::ActionExecutor>::`vftable';
    std::_Construct_in_place<ClusApi::Facade::ActionExecutor,ClusApi::Facade::ActionExecutor::private_make_shared_tag>(v21 + 4);
    v42[0] = (std::_Ref_count_base *)(v21 + 4);
    v42[1] = (std::_Ref_count_base *)v21;
    if ( v21 == (_DWORD *)-16LL )
    {
      v22 = std::wstring::wstring(v49, L"CreateActionExecutor( &ptrActionExec )");
      Hr = -2147024882;
      v33 = 2;
      cxl::Exception::Exception(v54, &Hr, v22);
      throw (cxl::Exception *)v54;
    }
    if ( v19 )
    {
      if ( (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v19 + 24LL))(v19) )
      {
        std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v49, v37);
        ClusApi::Facade::ActionExecutor::AddAction(v21 + 4, v49);
        if ( v49[1] )
          std::_Ref_count_base::_Decref(v49[1]);
      }
    }
    if ( (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v20 + 24LL))(v20) )
    {
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v49, v41);
      ClusApi::Facade::ActionExecutor::AddAction(v21 + 4, v49);
      if ( v49[1] )
        std::_Ref_count_base::_Decref(v49[1]);
    }
    v34[0] = a2;
    v23 = ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteGroupActionItem>::CreateActionItem<std::shared_ptr<ClusApi::Facade::GroupFacade>,bool>(
            v4,
            (__int64)v34,
            v45);
    if ( v23 < 0 )
    {
      v24 = std::wstring::wstring(v49, L"CreateDeleteGroupActionItem( ptrGroup, force, &ptrDeleteGroupItem )");
      Hr = v23;
      v33 = 2;
      cxl::Exception::Exception(v55, &Hr, v24);
      throw (cxl::Exception *)v55;
    }
    ClusApi::Facade::ActionExecutor::AddAction(v21 + 4, v45);
    if ( v45[1] )
      std::_Ref_count_base::_Decref(v45[1]);
    if ( v41[1] )
      std::_Ref_count_base::_Decref(v41[1]);
    v25 = v37[1];
    if ( v37[1] )
      std::_Ref_count_base::_Decref(v37[1]);
    std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(
      v25,
      v46);
    std::_Deallocate<16>(v46, 0x20u);
    std::shared_ptr<Wsp::Facade::VolumeFacade>::operator=(v3, v42);
    if ( v21 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v21);
    result = 0;
  }
  catch ( const cxl::Exception *v48 )
  {
    v36[0] = v48[11];
    Hr = cxl::ErrorCode::GetHr((cxl::ErrorCode *)v36);
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
    return Hr;
  }
  return result;
}

```

## disassembly

```asm
0x180095ef4  mov     [rsp+arg_8], dl
0x180095ef8  push    rbx
0x180095ef9  push    rsi
0x180095efa  push    rdi
0x180095efb  push    r12
0x180095efd  push    r13
0x180095eff  push    r14
0x180095f01  push    r15
0x180095f03  sub     rsp, 430h
0x180095f0a  mov     rax, cs:__security_cookie
0x180095f11  xor     rax, rsp
0x180095f14  mov     [rsp+468h+var_48], rax
0x180095f1c  mov     r12, r8
0x180095f1f  mov     [rsp+468h+var_438], r8
0x180095f24  mov     r14, rcx
0x180095f27  mov     [rsp+468h+var_3D8], rcx
0x180095f2f  mov     [rsp+468h+var_3D0], r8
0x180095f37  xor     edi, edi
0x180095f39  mov     [rsp+468h+var_448], edi
0x180095f3d  cmp     [rcx], rdi
0x180095f40  jz      loc_180096518
0x180095f46  test    r8, r8
0x180095f49  jz      loc_180096518
0x180095f4f  xorps   xmm0, xmm0
0x180095f52  movdqu  xmmword ptr [rsp+468h+var_3E8], xmm0
0x180095f5b  mov     rcx, [rcx]; this
0x180095f5e  call    ?get_type@GroupFacade@Facade@ClusApi@@QEBA?AW4CLUSGROUP_TYPE@@XZ; ClusApi::Facade::GroupFacade::get_type(void)
0x180095f63  mov     ebx, eax
0x180095f65  xorps   xmm0, xmm0
0x180095f68  movdqu  xmmword ptr [rsp+468h+var_398], xmm0
0x180095f71  lea     r8, [rsp+468h+var_398]
0x180095f79  lea     rdx, [rsp+468h+var_3B8]
0x180095f81  mov     rcx, [r14]
0x180095f84  call    ?GetResources@GroupFacade@Facade@ClusApi@@QEBA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIResourceFilter@Facade@ClusApi@@@5@@Z; ClusApi::Facade::GroupFacade::GetResources(std::shared_ptr<ClusApi::Facade::IResourceFilter> const &)
0x180095f89  nop
0x180095f8a  mov     rcx, [rsp+468h+var_398+8]; this
0x180095f92  test    rcx, rcx
0x180095f95  jz      short loc_180095F9C
0x180095f97  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180095f9c  xorps   xmm0, xmm0
0x180095f9f  movdqu  xmmword ptr [rsp+468h+var_420], xmm0
0x180095fa5  movdqu  xmmword ptr [rsp+468h+var_3F8], xmm0
0x180095fab  movdqu  xmmword ptr [rsp+468h+var_3C8], xmm0
0x180095fb4  cmp     ebx, 6Fh ; 'o'
0x180095fb7  jnz     loc_18009607E
0x180095fbd  mov     rcx, [r14]
0x180095fc0  mov     rax, [rcx]
0x180095fc3  mov     rax, [rax]
0x180095fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095fcb  xorps   xmm0, xmm0
0x180095fce  movdqu  xmmword ptr [rsp+468h+var_430], xmm0
0x180095fd4  lea     r8, [rsp+468h+var_430]
0x180095fd9  mov     rdx, r14
0x180095fdc  mov     rcx, rax
0x180095fdf  call    ??$CreateActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@V?$shared_ptr@VGroupFacade@Facade@ClusApi@@@2@@?$ActionFactoryCreator@VDeleteVmActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@AEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@5@PEAV?$shared_ptr@UIActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteVmActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,std::shared_ptr<ClusApi::Facade::GroupFacade>>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::GroupFacade> const &,std::shared_ptr<ClusApi::Facade::IActionItem> *)
0x180095fe4  mov     ebx, eax
0x180095fe6  test    eax, eax
0x180095fe8  js      short loc_18009601C
0x180095fea  lea     rdx, [rsp+468h+var_430]
0x180095fef  lea     rcx, [rsp+468h+var_398]
0x180095ff7  call    ??$dynamic_pointer_cast@UIResourceActionItem@Facade@ClusApi@@UIActionItem@23@@std@@YA?AV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@0@AEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@0@@Z; std::dynamic_pointer_cast<ClusApi::Facade::IResourceActionItem,ClusApi::Facade::IActionItem>(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x180095ffc  mov     rdx, rax
0x180095fff  lea     rcx, [rsp+468h+var_420]
0x180096004  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x180096009  mov     rcx, [rsp+468h+var_398+8]; this
0x180096011  test    rcx, rcx
0x180096014  jz      short loc_18009601C
0x180096016  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009601b  nop
0x18009601c  mov     rcx, [rsp+468h+var_430+8]; this
0x180096021  test    rcx, rcx
0x180096024  jz      short loc_18009602B
0x180096026  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009602b  test    ebx, ebx
0x18009602d  jns     loc_1800960EF
0x180096033  lea     rdx, aCreatedeletevm; "CreateDeleteVmActionItem( ptrGroup->Clu"...
0x18009603a  lea     rcx, [rsp+468h+var_398]
0x180096042  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180096047  nop
0x180096048  mov     [rsp+468h+var_448], ebx
0x18009604c  mov     [rsp+468h+var_444], 2
0x180096054  mov     r8, rax
0x180096057  lea     rdx, [rsp+468h+var_448]
0x18009605c  lea     rcx, [rsp+468h+pExceptionObject]
0x180096064  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180096069  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180096070  lea     rcx, [rsp+468h+pExceptionObject]; pExceptionObject
0x180096078  call    _CxxThrowException_0
0x18009607e  cmp     ebx, 6Ah ; 'j'
0x180096081  jnz     short loc_1800960EF
0x180096083  mov     rcx, [r14]
0x180096086  mov     rax, [rcx]
0x180096089  mov     rax, [rax]
0x18009608c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096091  lea     rdx, [rsp+468h+var_420]
0x180096096  mov     rcx, rax
0x180096099  call    ??$CreateResourceActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@@?$ActionFactoryCreator@VDeleteDfsnActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteDfsnActionItem>::CreateResourceActionItem<std::shared_ptr<ClusApi::ICluster>>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::IResourceActionItem> *)
0x18009609e  mov     ebx, eax
0x1800960a0  test    eax, eax
0x1800960a2  jns     short loc_1800960EF
0x1800960a4  lea     rdx, aCreatedeletedf; "CreateDeleteDfsnActionItem( ptrGroup->C"...
0x1800960ab  lea     rcx, [rsp+468h+var_398]
0x1800960b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800960b8  nop
0x1800960b9  mov     [rsp+468h+var_448], ebx
0x1800960bd  mov     [rsp+468h+var_444], 2
0x1800960c5  mov     r8, rax
0x1800960c8  lea     rdx, [rsp+468h+var_448]
0x1800960cd  lea     rcx, [rsp+468h+var_2E8]
0x1800960d5  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800960da  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800960e1  lea     rcx, [rsp+468h+var_2E8]; pExceptionObject
0x1800960e9  call    _CxxThrowException_0
0x1800960ef  mov     rcx, [r14]
0x1800960f2  mov     rax, [rcx]
0x1800960f5  mov     rax, [rax]
0x1800960f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800960fd  lea     rdx, [rsp+468h+var_3F8]
0x180096102  mov     rcx, rax
0x180096105  call    ??$CreateActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@VStorageMoveGroupLogic@Facade@ClusApi@@@?$ActionFactoryCreator@VDeleteStorageActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteStorageActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,ClusApi::Facade::StorageMoveGroupLogic>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::IResourceActionItem> *)
0x18009610a  mov     ebx, eax
0x18009610c  test    eax, eax
0x18009610e  jns     short loc_18009615B
0x180096110  lea     rdx, aCreatedeletest; "CreateDeleteStorageActionItem( ptrGroup"...
0x180096117  lea     rcx, [rsp+468h+var_398]
0x18009611f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180096124  nop
0x180096125  mov     [rsp+468h+var_448], ebx
0x180096129  mov     [rsp+468h+var_444], 2
0x180096131  mov     r8, rax
0x180096134  lea     rdx, [rsp+468h+var_448]
0x180096139  lea     rcx, [rsp+468h+var_278]
0x180096141  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180096146  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009614d  lea     rcx, [rsp+468h+var_278]; pExceptionObject
0x180096155  call    _CxxThrowException_0
0x18009615b  mov     rsi, [rsp+468h+var_3B8]
0x180096163  mov     rbx, [rsi]
0x180096166  mov     [rsp+468h+var_430], rsi
0x18009616b  mov     r15, [rsp+468h+var_420]
0x180096170  mov     r13, [rsp+468h+var_3F8]
0x180096175  mov     [rsp+468h+var_400], rbx
0x18009617a  cmp     rbx, rsi
0x18009617d  jnz     loc_1800963B8
0x180096183  mov     ecx, 38h ; '8'; Size
0x180096188  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009618d  mov     rbx, rax
0x180096190  mov     [rsp+468h+var_430], rax
0x180096195  mov     eax, 1
0x18009619a  mov     [rbx+8], eax
0x18009619d  mov     [rbx+0Ch], eax
0x1800961a0  lea     rax, ??_7?$_Ref_count_obj2@VActionExecutor@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::ActionExecutor>::`vftable'
0x1800961a7  mov     [rbx], rax
0x1800961aa  lea     rsi, [rbx+10h]
0x1800961ae  mov     rcx, rsi
0x1800961b1  call    ??$_Construct_in_place@VActionExecutor@Facade@ClusApi@@Uprivate_make_shared_tag@123@@std@@YAXAEAVActionExecutor@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@@Z; std::_Construct_in_place<ClusApi::Facade::ActionExecutor,ClusApi::Facade::ActionExecutor::private_make_shared_tag>(ClusApi::Facade::ActionExecutor &,ClusApi::Facade::ActionExecutor::private_make_shared_tag &&)
0x1800961b6  nop
0x1800961b7  mov     [rsp+468h+var_3E8], rsi
0x1800961bf  mov     [rsp+468h+var_3E8+8], rbx
0x1800961c7  mov     rax, rsi
0x1800961ca  neg     rax
0x1800961cd  sbb     edi, edi
0x1800961cf  not     edi
0x1800961d1  and     edi, 8007000Eh
0x1800961d7  jge     short loc_180096224
0x1800961d9  lea     rdx, aCreateactionex; "CreateActionExecutor( &ptrActionExec )"
0x1800961e0  lea     rcx, [rsp+468h+var_398]
0x1800961e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800961ed  nop
0x1800961ee  mov     [rsp+468h+var_448], edi
0x1800961f2  mov     [rsp+468h+var_444], 2
0x1800961fa  mov     r8, rax
0x1800961fd  lea     rdx, [rsp+468h+var_448]
0x180096202  lea     rcx, [rsp+468h+var_208]
0x18009620a  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009620f  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180096216  lea     rcx, [rsp+468h+var_208]; pExceptionObject
0x18009621e  call    _CxxThrowException_0
0x180096224  test    r15, r15
0x180096227  jz      short loc_180096273
0x180096229  mov     rax, [r15]
0x18009622c  mov     rcx, r15
0x18009622f  mov     rax, [rax+18h]
0x180096233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096238  test    rax, rax
0x18009623b  jz      short loc_180096273
0x18009623d  lea     rdx, [rsp+468h+var_420]
0x180096242  lea     rcx, [rsp+468h+var_398]
0x18009624a  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18009624f  nop
0x180096250  lea     rdx, [rsp+468h+var_398]
0x180096258  mov     rcx, rsi
0x18009625b  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x180096260  nop
0x180096261  mov     rcx, [rsp+468h+var_398+8]; this
0x180096269  test    rcx, rcx
0x18009626c  jz      short loc_180096273
0x18009626e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180096273  mov     rax, [r13+0]
0x180096277  mov     rcx, r13
0x18009627a  mov     rax, [rax+18h]
0x18009627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096283  test    rax, rax
0x180096286  jz      short loc_1800962BE
0x180096288  lea     rdx, [rsp+468h+var_3F8]
0x18009628d  lea     rcx, [rsp+468h+var_398]
0x180096295  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18009629a  nop
0x18009629b  lea     rdx, [rsp+468h+var_398]
0x1800962a3  mov     rcx, rsi
0x1800962a6  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x1800962ab  nop
0x1800962ac  mov     rcx, [rsp+468h+var_398+8]; this
0x1800962b4  test    rcx, rcx
0x1800962b7  jz      short loc_1800962BE
0x1800962b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800962be  mov     al, [rsp+468h+arg_8]
0x1800962c5  mov     [rsp+468h+var_440], al
0x1800962c9  lea     r8, [rsp+468h+var_3C8]
0x1800962d1  lea     rdx, [rsp+468h+var_440]
0x1800962d6  mov     rcx, r14
0x1800962d9  call    ??$CreateActionItem@V?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@_N@?$ActionFactoryCreator@VDeleteGroupActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@AEB_NPEAV?$shared_ptr@UIActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteGroupActionItem>::CreateActionItem<std::shared_ptr<ClusApi::Facade::GroupFacade>,bool>(std::shared_ptr<ClusApi::Facade::GroupFacade> const &,bool const &,std::shared_ptr<ClusApi::Facade::IActionItem> *)
0x1800962de  mov     edi, eax
0x1800962e0  test    eax, eax
0x1800962e2  jns     short loc_18009632F
0x1800962e4  lea     rdx, aCreatedeletegr; "CreateDeleteGroupActionItem( ptrGroup, "...
0x1800962eb  lea     rcx, [rsp+468h+var_398]
0x1800962f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800962f8  nop
0x1800962f9  mov     [rsp+468h+var_448], edi
0x1800962fd  mov     [rsp+468h+var_444], 2
0x180096305  mov     r8, rax
0x180096308  lea     rdx, [rsp+468h+var_448]
0x18009630d  lea     rcx, [rsp+468h+var_198]
0x180096315  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009631a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180096321  lea     rcx, [rsp+468h+var_198]; pExceptionObject
0x180096329  call    _CxxThrowException_0
0x18009632f  lea     rdx, [rsp+468h+var_3C8]
0x180096337  mov     rcx, rsi
0x18009633a  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x18009633f  nop
0x180096340  mov     rcx, [rsp+468h+var_3C8+8]; this
0x180096348  test    rcx, rcx
0x18009634b  jz      short loc_180096353
0x18009634d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180096352  nop
0x180096353  mov     rcx, [rsp+468h+var_3F8+8]; this
0x180096358  test    rcx, rcx
0x18009635b  jz      short loc_180096363
0x18009635d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180096362  nop
0x180096363  mov     rcx, [rsp+468h+var_420+8]; this
0x180096368  test    rcx, rcx
0x18009636b  jz      short loc_180096373
0x18009636d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180096372  nop
0x180096373  mov     rdx, [rsp+468h+var_3B8]
0x18009637b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x180096380  mov     edx, 20h ; ' '
0x180096385  mov     rcx, [rsp+468h+var_3B8]
0x18009638d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180096392  nop
0x180096393  lea     rdx, [rsp+468h+var_3E8]
0x18009639b  mov     rcx, r12
0x18009639e  call    ??4?$shared_ptr@VVolumeFacade@Facade@Wsp@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Wsp::Facade::VolumeFacade>::operator=(std::shared_ptr<Wsp::Facade::VolumeFacade> const &)
0x1800963a3  nop
0x1800963a4  test    rbx, rbx
0x1800963a7  jz      short loc_1800963B1
0x1800963a9  mov     rcx, rbx; this
0x1800963ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800963b1  xor     eax, eax
0x1800963b3  jmp     loc_18009651D
0x1800963b8  lea     rdx, [rbx+10h]
0x1800963bc  lea     rcx, [rsp+468h+var_398]
0x1800963c4  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x1800963c9  nop
0x1800963ca  test    r15, r15
0x1800963cd  jz      short loc_180096440
0x1800963cf  mov     rax, [r15]
0x1800963d2  lea     rdx, [rsp+468h+var_398]
0x1800963da  mov     rcx, r15
0x1800963dd  mov     rax, [rax+10h]
0x1800963e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800963e6  mov     r12d, eax
0x1800963e9  test    eax, eax
0x1800963eb  jns     short loc_180096440
0x1800963ed  lea     rdx, aPtrgroupaction; "ptrGroupActionItem->AddResource( ptrRes"...
0x1800963f4  lea     rcx, [rsp+468h+var_378]
0x1800963fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180096401  nop
0x180096402  mov     [rsp+468h+var_410], r12d
0x180096407  mov     [rsp+468h+var_40C], 2
0x18009640f  mov     r8, rax
0x180096412  lea     rdx, [rsp+468h+var_410]
0x180096417  lea     rcx, [rsp+468h+var_128]
0x18009641f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180096424  or      edi, 8
0x180096427  mov     [rsp+468h+var_448], edi
0x18009642b  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
  ... truncated ...
```
