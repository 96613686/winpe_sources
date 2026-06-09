# ClusApi::Facade::ActionFactory::CreateGroupDeleteExecutor(std::shared_ptr<ClusApi::Facade::GroupFacade> const &,bool,std::shared_ptr<ClusApi::Facade::ActionExecutor> *)

- ea: `0x180097ff4`
- end: `0x180098641`
- name: `?CreateGroupDeleteExecutor@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@_NPEAV?$shared_ptr@VActionExecutor@Facade@ClusApi@@@5@@Z`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180091c20`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180003534`
- `0x180005e64`
- `0x180005fdc`
- `0x18000c4ac`
- `0x18000c5c4`
- `0x18000d6a4`
- `0x180019d00`
- `0x180050914`
- `0x180057488`
- `0x180092df8`
- `0x180094d3c`
- `0x180097940`
- `0x1800979ec`
- `0x180097ab0`
- `0x180097b58`
- `0x180097c2c`
- `0x180097db4`
- `0x180097ff4`
- `0x18009883c`
- `0x1800ab010`

## string_xrefs

- `0x1800981a4`: `CreateDeleteDfsnActionItem( ptrGroup->Cluster, &ptrGroupActionItem )`
- `0x180098133`: `CreateDeleteVmActionItem( ptrGroup->Cluster, ptrGroup, &ptrGroupActionItem )`
- `0x180098210`: `CreateDeleteStorageActionItem( ptrGroup->Cluster, &ptrStorageItem )`
- `0x1800982d9`: `CreateActionExecutor( &ptrActionExec )`
- `0x1800983e4`: `CreateDeleteGroupActionItem( ptrGroup, force, &ptrDeleteGroupItem )`

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
             v4,
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
              v37);
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
      std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(v49, (char *)v18 + 16);
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
            v34,
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
    std::_Deallocate<16>(v46, 32);
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
0x180097ff4  mov     [rsp+arg_8], dl
0x180097ff8  push    rbx
0x180097ff9  push    rsi
0x180097ffa  push    rdi
0x180097ffb  push    r12
0x180097ffd  push    r13
0x180097fff  push    r14
0x180098001  push    r15
0x180098003  sub     rsp, 430h
0x18009800a  mov     rax, cs:__security_cookie
0x180098011  xor     rax, rsp
0x180098014  mov     [rsp+468h+var_48], rax
0x18009801c  mov     r12, r8
0x18009801f  mov     [rsp+468h+var_438], r8
0x180098024  mov     r14, rcx
0x180098027  mov     [rsp+468h+var_3D8], rcx
0x18009802f  mov     [rsp+468h+var_3D0], r8
0x180098037  xor     edi, edi
0x180098039  mov     [rsp+468h+var_448], edi
0x18009803d  cmp     [rcx], rdi
0x180098040  jz      loc_180098618
0x180098046  test    r8, r8
0x180098049  jz      loc_180098618
0x18009804f  xorps   xmm0, xmm0
0x180098052  movdqu  xmmword ptr [rsp+468h+var_3E8], xmm0
0x18009805b  mov     rcx, [rcx]; this
0x18009805e  call    ?get_type@GroupFacade@Facade@ClusApi@@QEBA?AW4CLUSGROUP_TYPE@@XZ; ClusApi::Facade::GroupFacade::get_type(void)
0x180098063  mov     ebx, eax
0x180098065  xorps   xmm0, xmm0
0x180098068  movdqu  xmmword ptr [rsp+468h+var_398], xmm0
0x180098071  lea     r8, [rsp+468h+var_398]
0x180098079  lea     rdx, [rsp+468h+var_3B8]
0x180098081  mov     rcx, [r14]
0x180098084  call    ?GetResources@GroupFacade@Facade@ClusApi@@QEBA?AV?$list@V?$shared_ptr@UIResource@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UIResource@ClusApi@@@std@@@2@@std@@AEBV?$shared_ptr@UIResourceFilter@Facade@ClusApi@@@5@@Z; ClusApi::Facade::GroupFacade::GetResources(std::shared_ptr<ClusApi::Facade::IResourceFilter> const &)
0x180098089  nop
0x18009808a  mov     rcx, [rsp+468h+var_398+8]; this
0x180098092  test    rcx, rcx
0x180098095  jz      short loc_18009809C
0x180098097  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009809c  xorps   xmm0, xmm0
0x18009809f  movdqu  xmmword ptr [rsp+468h+var_420], xmm0
0x1800980a5  movdqu  xmmword ptr [rsp+468h+var_3F8], xmm0
0x1800980ab  movdqu  xmmword ptr [rsp+468h+var_3C8], xmm0
0x1800980b4  cmp     ebx, 6Fh ; 'o'
0x1800980b7  jnz     loc_18009817E
0x1800980bd  mov     rcx, [r14]
0x1800980c0  mov     rax, [rcx]
0x1800980c3  mov     rax, [rax]
0x1800980c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980cb  xorps   xmm0, xmm0
0x1800980ce  movdqu  xmmword ptr [rsp+468h+var_430], xmm0
0x1800980d4  lea     r8, [rsp+468h+var_430]
0x1800980d9  mov     rdx, r14
0x1800980dc  mov     rcx, rax
0x1800980df  call    ??$CreateActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@V?$shared_ptr@VGroupFacade@Facade@ClusApi@@@2@@?$ActionFactoryCreator@VDeleteVmActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@AEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@5@PEAV?$shared_ptr@UIActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteVmActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,std::shared_ptr<ClusApi::Facade::GroupFacade>>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::GroupFacade> const &,std::shared_ptr<ClusApi::Facade::IActionItem> *)
0x1800980e4  mov     ebx, eax
0x1800980e6  test    eax, eax
0x1800980e8  js      short loc_18009811C
0x1800980ea  lea     rdx, [rsp+468h+var_430]
0x1800980ef  lea     rcx, [rsp+468h+var_398]
0x1800980f7  call    ??$dynamic_pointer_cast@UIResourceActionItem@Facade@ClusApi@@UIActionItem@23@@std@@YA?AV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@0@AEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@0@@Z; std::dynamic_pointer_cast<ClusApi::Facade::IResourceActionItem,ClusApi::Facade::IActionItem>(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x1800980fc  mov     rdx, rax
0x1800980ff  lea     rcx, [rsp+468h+var_420]
0x180098104  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x180098109  mov     rcx, [rsp+468h+var_398+8]; this
0x180098111  test    rcx, rcx
0x180098114  jz      short loc_18009811C
0x180098116  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009811b  nop
0x18009811c  mov     rcx, [rsp+468h+var_430+8]; this
0x180098121  test    rcx, rcx
0x180098124  jz      short loc_18009812B
0x180098126  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009812b  test    ebx, ebx
0x18009812d  jns     loc_1800981EF
0x180098133  lea     rdx, aCreatedeletevm; "CreateDeleteVmActionItem( ptrGroup->Clu"...
0x18009813a  lea     rcx, [rsp+468h+var_398]
0x180098142  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180098147  nop
0x180098148  mov     [rsp+468h+var_448], ebx
0x18009814c  mov     [rsp+468h+var_444], 2
0x180098154  mov     r8, rax
0x180098157  lea     rdx, [rsp+468h+var_448]
0x18009815c  lea     rcx, [rsp+468h+pExceptionObject]
0x180098164  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180098169  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180098170  lea     rcx, [rsp+468h+pExceptionObject]; pExceptionObject
0x180098178  call    _CxxThrowException_0
0x18009817e  cmp     ebx, 6Ah ; 'j'
0x180098181  jnz     short loc_1800981EF
0x180098183  mov     rcx, [r14]
0x180098186  mov     rax, [rcx]
0x180098189  mov     rax, [rax]
0x18009818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098191  lea     rdx, [rsp+468h+var_420]
0x180098196  mov     rcx, rax
0x180098199  call    ??$CreateResourceActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@@?$ActionFactoryCreator@VDeleteDfsnActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteDfsnActionItem>::CreateResourceActionItem<std::shared_ptr<ClusApi::ICluster>>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::IResourceActionItem> *)
0x18009819e  mov     ebx, eax
0x1800981a0  test    eax, eax
0x1800981a2  jns     short loc_1800981EF
0x1800981a4  lea     rdx, aCreatedeletedf; "CreateDeleteDfsnActionItem( ptrGroup->C"...
0x1800981ab  lea     rcx, [rsp+468h+var_398]
0x1800981b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800981b8  nop
0x1800981b9  mov     [rsp+468h+var_448], ebx
0x1800981bd  mov     [rsp+468h+var_444], 2
0x1800981c5  mov     r8, rax
0x1800981c8  lea     rdx, [rsp+468h+var_448]
0x1800981cd  lea     rcx, [rsp+468h+var_2E8]
0x1800981d5  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800981da  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800981e1  lea     rcx, [rsp+468h+var_2E8]; pExceptionObject
0x1800981e9  call    _CxxThrowException_0
0x1800981ef  mov     rcx, [r14]
0x1800981f2  mov     rax, [rcx]
0x1800981f5  mov     rax, [rax]
0x1800981f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800981fd  lea     rdx, [rsp+468h+var_3F8]
0x180098202  mov     rcx, rax
0x180098205  call    ??$CreateActionItem@V?$shared_ptr@UICluster@ClusApi@@@std@@VStorageMoveGroupLogic@Facade@ClusApi@@@?$ActionFactoryCreator@VDeleteStorageActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@PEAV?$shared_ptr@UIResourceActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteStorageActionItem>::CreateActionItem<std::shared_ptr<ClusApi::ICluster>,ClusApi::Facade::StorageMoveGroupLogic>(std::shared_ptr<ClusApi::ICluster> const &,std::shared_ptr<ClusApi::Facade::IResourceActionItem> *)
0x18009820a  mov     ebx, eax
0x18009820c  test    eax, eax
0x18009820e  jns     short loc_18009825B
0x180098210  lea     rdx, aCreatedeletest; "CreateDeleteStorageActionItem( ptrGroup"...
0x180098217  lea     rcx, [rsp+468h+var_398]
0x18009821f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180098224  nop
0x180098225  mov     [rsp+468h+var_448], ebx
0x180098229  mov     [rsp+468h+var_444], 2
0x180098231  mov     r8, rax
0x180098234  lea     rdx, [rsp+468h+var_448]
0x180098239  lea     rcx, [rsp+468h+var_278]
0x180098241  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180098246  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009824d  lea     rcx, [rsp+468h+var_278]; pExceptionObject
0x180098255  call    _CxxThrowException_0
0x18009825b  mov     rsi, [rsp+468h+var_3B8]
0x180098263  mov     rbx, [rsi]
0x180098266  mov     [rsp+468h+var_430], rsi
0x18009826b  mov     r15, [rsp+468h+var_420]
0x180098270  mov     r13, [rsp+468h+var_3F8]
0x180098275  mov     [rsp+468h+var_400], rbx
0x18009827a  cmp     rbx, rsi
0x18009827d  jnz     loc_1800984B8
0x180098283  mov     ecx, 38h ; '8'; Size
0x180098288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009828d  mov     rbx, rax
0x180098290  mov     [rsp+468h+var_430], rax
0x180098295  mov     eax, 1
0x18009829a  mov     [rbx+8], eax
0x18009829d  mov     [rbx+0Ch], eax
0x1800982a0  lea     rax, ??_7?$_Ref_count_obj2@VActionExecutor@Facade@ClusApi@@@std@@6B@; const std::_Ref_count_obj2<ClusApi::Facade::ActionExecutor>::`vftable'
0x1800982a7  mov     [rbx], rax
0x1800982aa  lea     rsi, [rbx+10h]
0x1800982ae  mov     rcx, rsi
0x1800982b1  call    ??$_Construct_in_place@VActionExecutor@Facade@ClusApi@@Uprivate_make_shared_tag@123@@std@@YAXAEAVActionExecutor@Facade@ClusApi@@$$QEAUprivate_make_shared_tag@123@@Z; std::_Construct_in_place<ClusApi::Facade::ActionExecutor,ClusApi::Facade::ActionExecutor::private_make_shared_tag>(ClusApi::Facade::ActionExecutor &,ClusApi::Facade::ActionExecutor::private_make_shared_tag &&)
0x1800982b6  nop
0x1800982b7  mov     [rsp+468h+var_3E8], rsi
0x1800982bf  mov     [rsp+468h+var_3E8+8], rbx
0x1800982c7  mov     rax, rsi
0x1800982ca  neg     rax
0x1800982cd  sbb     edi, edi
0x1800982cf  not     edi
0x1800982d1  and     edi, 8007000Eh
0x1800982d7  jge     short loc_180098324
0x1800982d9  lea     rdx, aCreateactionex; "CreateActionExecutor( &ptrActionExec )"
0x1800982e0  lea     rcx, [rsp+468h+var_398]
0x1800982e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800982ed  nop
0x1800982ee  mov     [rsp+468h+var_448], edi
0x1800982f2  mov     [rsp+468h+var_444], 2
0x1800982fa  mov     r8, rax
0x1800982fd  lea     rdx, [rsp+468h+var_448]
0x180098302  lea     rcx, [rsp+468h+var_208]
0x18009830a  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009830f  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180098316  lea     rcx, [rsp+468h+var_208]; pExceptionObject
0x18009831e  call    _CxxThrowException_0
0x180098324  test    r15, r15
0x180098327  jz      short loc_180098373
0x180098329  mov     rax, [r15]
0x18009832c  mov     rcx, r15
0x18009832f  mov     rax, [rax+18h]
0x180098333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098338  test    rax, rax
0x18009833b  jz      short loc_180098373
0x18009833d  lea     rdx, [rsp+468h+var_420]
0x180098342  lea     rcx, [rsp+468h+var_398]
0x18009834a  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18009834f  nop
0x180098350  lea     rdx, [rsp+468h+var_398]
0x180098358  mov     rcx, rsi
0x18009835b  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x180098360  nop
0x180098361  mov     rcx, [rsp+468h+var_398+8]; this
0x180098369  test    rcx, rcx
0x18009836c  jz      short loc_180098373
0x18009836e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180098373  mov     rax, [r13+0]
0x180098377  mov     rcx, r13
0x18009837a  mov     rax, [rax+18h]
0x18009837e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098383  test    rax, rax
0x180098386  jz      short loc_1800983BE
0x180098388  lea     rdx, [rsp+468h+var_3F8]
0x18009838d  lea     rcx, [rsp+468h+var_398]
0x180098395  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x18009839a  nop
0x18009839b  lea     rdx, [rsp+468h+var_398]
0x1800983a3  mov     rcx, rsi
0x1800983a6  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x1800983ab  nop
0x1800983ac  mov     rcx, [rsp+468h+var_398+8]; this
0x1800983b4  test    rcx, rcx
0x1800983b7  jz      short loc_1800983BE
0x1800983b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800983be  mov     al, [rsp+468h+arg_8]
0x1800983c5  mov     [rsp+468h+var_440], al
0x1800983c9  lea     r8, [rsp+468h+var_3C8]
0x1800983d1  lea     rdx, [rsp+468h+var_440]
0x1800983d6  mov     rcx, r14
0x1800983d9  call    ??$CreateActionItem@V?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@_N@?$ActionFactoryCreator@VDeleteGroupActionItem@Facade@ClusApi@@@ActionFactory@Facade@ClusApi@@SAJAEBV?$shared_ptr@VGroupFacade@Facade@ClusApi@@@std@@AEB_NPEAV?$shared_ptr@UIActionItem@Facade@ClusApi@@@5@@Z; ClusApi::Facade::ActionFactory::ActionFactoryCreator<ClusApi::Facade::DeleteGroupActionItem>::CreateActionItem<std::shared_ptr<ClusApi::Facade::GroupFacade>,bool>(std::shared_ptr<ClusApi::Facade::GroupFacade> const &,bool const &,std::shared_ptr<ClusApi::Facade::IActionItem> *)
0x1800983de  mov     edi, eax
0x1800983e0  test    eax, eax
0x1800983e2  jns     short loc_18009842F
0x1800983e4  lea     rdx, aCreatedeletegr; "CreateDeleteGroupActionItem( ptrGroup, "...
0x1800983eb  lea     rcx, [rsp+468h+var_398]
0x1800983f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800983f8  nop
0x1800983f9  mov     [rsp+468h+var_448], edi
0x1800983fd  mov     [rsp+468h+var_444], 2
0x180098405  mov     r8, rax
0x180098408  lea     rdx, [rsp+468h+var_448]
0x18009840d  lea     rcx, [rsp+468h+var_198]
0x180098415  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18009841a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180098421  lea     rcx, [rsp+468h+var_198]; pExceptionObject
0x180098429  call    _CxxThrowException_0
0x18009842f  lea     rdx, [rsp+468h+var_3C8]
0x180098437  mov     rcx, rsi
0x18009843a  call    ?AddAction@ActionExecutor@Facade@ClusApi@@QEAAXAEBV?$shared_ptr@UIActionItem@Facade@ClusApi@@@std@@@Z; ClusApi::Facade::ActionExecutor::AddAction(std::shared_ptr<ClusApi::Facade::IActionItem> const &)
0x18009843f  nop
0x180098440  mov     rcx, [rsp+468h+var_3C8+8]; this
0x180098448  test    rcx, rcx
0x18009844b  jz      short loc_180098453
0x18009844d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180098452  nop
0x180098453  mov     rcx, [rsp+468h+var_3F8+8]; this
0x180098458  test    rcx, rcx
0x18009845b  jz      short loc_180098463
0x18009845d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180098462  nop
0x180098463  mov     rcx, [rsp+468h+var_420+8]; this
0x180098468  test    rcx, rcx
0x18009846b  jz      short loc_180098473
0x18009846d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180098472  nop
0x180098473  mov     rdx, [rsp+468h+var_3B8]
0x18009847b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@UIResource@ClusApi@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<ClusApi::IResource>,void *>> &,std::_List_node<std::shared_ptr<ClusApi::IResource>,void *> *)
0x180098480  mov     edx, 20h ; ' '
0x180098485  mov     rcx, [rsp+468h+var_3B8]
0x18009848d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180098492  nop
0x180098493  lea     rdx, [rsp+468h+var_3E8]
0x18009849b  mov     rcx, r12
0x18009849e  call    ??4?$shared_ptr@VVolumeFacade@Facade@Wsp@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Wsp::Facade::VolumeFacade>::operator=(std::shared_ptr<Wsp::Facade::VolumeFacade> const &)
0x1800984a3  nop
0x1800984a4  test    rbx, rbx
0x1800984a7  jz      short loc_1800984B1
0x1800984a9  mov     rcx, rbx; this
0x1800984ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800984b1  xor     eax, eax
0x1800984b3  jmp     loc_18009861D
0x1800984b8  lea     rdx, [rbx+10h]
0x1800984bc  lea     rcx, [rsp+468h+var_398]
0x1800984c4  call    ??$?0UIAvailableDisk@ClusApi@@$0A@@?$shared_ptr@UIStorage@ClusApi@@@std@@QEAA@AEBV?$shared_ptr@UIAvailableDisk@ClusApi@@@1@@Z; std::shared_ptr<ClusApi::IStorage>::shared_ptr<ClusApi::IStorage>(std::shared_ptr<ClusApi::IAvailableDisk> const &)
0x1800984c9  nop
0x1800984ca  test    r15, r15
0x1800984cd  jz      short loc_180098540
0x1800984cf  mov     rax, [r15]
0x1800984d2  lea     rdx, [rsp+468h+var_398]
0x1800984da  mov     rcx, r15
0x1800984dd  mov     rax, [rax+10h]
0x1800984e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800984e6  mov     r12d, eax
0x1800984e9  test    eax, eax
0x1800984eb  jns     short loc_180098540
0x1800984ed  lea     rdx, aPtrgroupaction; "ptrGroupActionItem->AddResource( ptrRes"...
0x1800984f4  lea     rcx, [rsp+468h+var_378]
0x1800984fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180098501  nop
0x180098502  mov     [rsp+468h+var_410], r12d
0x180098507  mov     [rsp+468h+var_40C], 2
0x18009850f  mov     r8, rax
0x180098512  lea     rdx, [rsp+468h+var_410]
0x180098517  lea     rcx, [rsp+468h+var_128]
0x18009851f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180098524  or      edi, 8
0x180098527  mov     [rsp+468h+var_448], edi
0x18009852b  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
  ... truncated ...
```
