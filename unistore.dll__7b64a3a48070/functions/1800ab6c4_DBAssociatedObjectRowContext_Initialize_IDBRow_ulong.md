# DBAssociatedObjectRowContext::Initialize(IDBRow *,ulong)

- ea: `0x1800ab6c4`
- end: `0x1800ac1e2`
- name: `?Initialize@DBAssociatedObjectRowContext@@AEAAJPEAVIDBRow@@K@Z`
- size: `2846`
- prototype: `__int64 __fastcall(DBAssociatedObjectRowContext *__hidden this, struct IDBRow *, unsigned int)`
- caller_count: `1`
- callee_count: `25`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800ab5d0`

## callees

- `0x180004220`
- `0x180004440`
- `0x180006224`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180009a90`
- `0x18000b350`
- `0x18000b9ac`
- `0x18000f2f0`
- `0x180010030`
- `0x180010ea0`
- `0x180012100`
- `0x18001a810`
- `0x180028ef4`
- `0x1800325d0`
- `0x180035d40`
- `0x180044ca8`
- `0x180045e44`
- `0x180053360`
- `0x18006fa74`
- `0x18006fde4`
- `0x1800ab6c4`
- `0x1800c50f0`
- `0x1800c6010`

## string_xrefs

- `0x1800ab755`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ab7c1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ab832`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ab8bc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ab93d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ab9c6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800aba54`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abc9e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abd2f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abdb9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abe41`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abec3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abf43`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800abff8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ac07f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800ac184`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`

## pseudocode

```c
__int64 __fastcall DBAssociatedObjectRowContext::Initialize(
        DBAssociatedObjectRowContext *this,
        struct IDBRow *a2,
        int a3)
{
  __int64 *v6; // rdx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(struct IDBRow *, char *, _QWORD); // rax
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  int Key; // eax
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rdx
  _QWORD *v36; // rcx
  __int64 v37; // rax
  void **v38; // rax
  _WORD *v39; // rbx
  unsigned int v40; // r14d
  int ObjectTypeFromTable; // eax
  int v42; // edi
  __int64 v43; // rdi
  int v44; // eax
  int v45; // eax
  int updated; // eax
  __int64 v47; // rcx
  unsigned int v48; // r8d
  __int64 v49; // rdx
  _QWORD *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rdx
  _QWORD *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rdx
  _QWORD *v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rdx
  _QWORD *v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rdx
  _QWORD *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  _QWORD *v65; // rcx
  __int64 v66; // rax
  __int64 v68; // rdx
  _QWORD *v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rdx
  _QWORD *v72; // rcx
  __int64 v73; // rax
  __int64 v74; // rdx
  _QWORD *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdx
  _QWORD *v78; // rcx
  __int64 v79; // rax
  struct IDBVolume *v80; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+48h] [rbp-B8h] BYREF
  _WORD *v82; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v83; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  struct TableHandleInfo *v85; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v86[8]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v87[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v88[5]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v89; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v90; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v91; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v92; // [rsp+C4h] [rbp-3Ch] BYREF
  int v93; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v94; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v95; // [rsp+E0h] [rbp-20h]
  __int128 v96; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v97; // [rsp+F8h] [rbp-8h]
  _BYTE v98[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v99[16]; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v100[4]; // [rsp+118h] [rbp+18h] BYREF

  v97 = 0;
  v95 = 0;
  v96 = 0;
  v94 = 0;
  utl::unordered_map<enum US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<enum US_TABLEID>,utl::equal_to<enum US_TABLEID>,utl::allocator<utl::pair<enum US_TABLEID const,ATL::CComPtr<IDBTable>>>>::unordered_map<enum US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<enum US_TABLEID>,utl::equal_to<enum US_TABLEID>,utl::allocator<utl::pair<enum US_TABLEID const,ATL::CComPtr<IDBTable>>>>(v88);
  v7 = *v6;
  v80 = 0;
  v81 = 0;
  LODWORD(v96) = 270336031;
  v8 = *(__int64 (__fastcall **)(struct IDBRow *, char *, _QWORD))(v7 + 120);
  LODWORD(v94) = 537198611;
  v9 = v8(a2, (char *)&v94 + 8, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(struct IDBRow *, struct IDBVolume **))(*(_QWORD *)a2 + 24LL))(a2, &v80);
    v10 = v14;
    if ( v14 >= 0 )
    {
      v87[0] = 0;
      v87[1] = 0;
      v18 = auto_DBSession::Open((auto_DBSession *)v87, v80);
      v10 = v18;
      if ( v18 >= 0 )
      {
        v85 = 0;
        ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v86, v87[0]);
        v22 = auto_TableHandle::Open(&v85, 10, 2);
        v10 = v22;
        if ( v22 >= 0 )
        {
          Key = UnistoreJetMakeKey(v85, (const struct _USPROPVAL *)&v94, 0x101u);
          v10 = Key;
          if ( Key >= 0 )
          {
            v30 = UnistoreJetSeek(v85, 1u);
            v10 = v30;
            if ( v30 == -2147024871 )
            {
LABEL_72:
              v10 = 0;
              auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
              auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
              while ( 1 )
              {
                v74 = v88[0];
                if ( (_QWORD *)v88[0] == v88 )
                  break;
                v75 = *(_QWORD **)(v88[0] + 8LL);
                v76 = *(_QWORD *)v88[0];
                *v75 = *(_QWORD *)v88[0];
                *(_QWORD *)(v76 + 8) = v75;
                utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                  (__int64)v75,
                  v74);
              }
            }
            else if ( v30 >= 0 )
            {
              v34 = UnistoreJetSetIndexRange(v85, (const struct _USPROPVAL *)&v94, 1u, 0x200u, 1, 0, 1);
              v10 = v34;
              if ( v34 >= 0 )
              {
                while ( 1 )
                {
                  v100[0] = 537067539;
                  v100[1] = 537133075;
                  v100[2] = 65539;
                  v82 = 0;
                  v91 = 0;
                  v92 = 3;
                  v93 = 0;
                  v84 = 0;
                  v83 = 0;
                  v38 = tlx::replace<_USPROPVALEx *,void * (*)(void *),&void * LocalFree(void *),0>((void **)&v82);
                  v10 = ESEReadRecordProps(v85, 0, &v92, v100, (unsigned __int8 **)v38, &v91);
                  if ( v10 < 0 )
                    break;
                  v39 = v82;
                  if ( (v82[3] & 0x100) != 0 )
                  {
                    v10 = -2147418113;
                    Log_UnistoreHREvent_0(
                      2147549183LL,
                      0,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                      3049);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                    auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                    while ( 1 )
                    {
                      v71 = v88[0];
                      if ( (_QWORD *)v88[0] == v88 )
                        break;
                      v72 = *(_QWORD **)(v88[0] + 8LL);
                      v73 = *(_QWORD *)v88[0];
                      *v72 = *(_QWORD *)v88[0];
                      *(_QWORD *)(v73 + 8) = v72;
                      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                        (__int64)v72,
                        v71);
                    }
                    goto LABEL_64;
                  }
                  if ( (v82[15] & 0x100) != 0 )
                  {
                    v10 = -2147418113;
                    Log_UnistoreHREvent_0(
                      2147549183LL,
                      0,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                      3050);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                    auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                    while ( 1 )
                    {
                      v68 = v88[0];
                      if ( (_QWORD *)v88[0] == v88 )
                        break;
                      v69 = *(_QWORD **)(v88[0] + 8LL);
                      v70 = *(_QWORD *)v88[0];
                      *v69 = *(_QWORD *)v88[0];
                      *(_QWORD *)(v70 + 8) = v69;
                      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                        (__int64)v69,
                        v68);
                    }
                    goto LABEL_64;
                  }
                  v89 = *((_DWORD *)v82 + 2);
                  v40 = v89;
                  ObjectTypeFromTable = DBManager::GetObjectTypeFromTable(v89, &v93);
                  v42 = ObjectTypeFromTable;
                  if ( ObjectTypeFromTable < 0 )
                  {
                    Log_UnistoreHREvent_0(
                      (unsigned int)ObjectTypeFromTable,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                      3055);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                    auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                    while ( 1 )
                    {
                      v64 = v88[0];
                      if ( (_QWORD *)v88[0] == v88 )
                        break;
                      v65 = *(_QWORD **)(v88[0] + 8LL);
                      v66 = *(_QWORD *)v88[0];
                      *v65 = *(_QWORD *)v88[0];
                      *(_QWORD *)(v66 + 8) = v65;
                      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                        (__int64)v65,
                        v64);
                    }
                    v10 = v42;
                    goto LABEL_64;
                  }
                  v43 = *(_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,ScopeKnowledgeStatistics>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ScopeKnowledgeStatistics>>,0>::_FindFirst<utl::_HashTable<unsigned long,utl::pair<unsigned long const,ScopeKnowledgeStatistics>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ScopeKnowledgeStatistics>>,0>::_FindFirstFind,unsigned long>(
                                     v88,
                                     v98,
                                     &v89);
                  if ( v88 == (_QWORD *)v43 )
                  {
                    v90 = 0;
                    v44 = (*(__int64 (__fastcall **)(struct IDBVolume *, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v80 + 32LL))(
                            v80,
                            v40,
                            0,
                            0,
                            &v90);
                    v10 = v44;
                    if ( v44 < 0 )
                    {
                      Log_UnistoreHREvent_0(
                        (unsigned int)v44,
                        1,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                        3063);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v90);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                      auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                      while ( 1 )
                      {
                        v52 = v88[0];
                        if ( (_QWORD *)v88[0] == v88 )
                          break;
                        v53 = *(_QWORD **)(v88[0] + 8LL);
                        v54 = *(_QWORD *)v88[0];
                        *v53 = *(_QWORD *)v88[0];
                        *(_QWORD *)(v54 + 8) = v53;
                        utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                          (__int64)v53,
                          v52);
                      }
                      goto LABEL_64;
                    }
                    v43 = *(_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<ISyncKnowledge>>>,0>::emplace<unsigned long &,ATL::CComPtr<ISyncKnowledge> &,0>(
                                       (__int64)v88,
                                       (__int64)v99,
                                       &v89,
                                       &v90);
                    if ( !v43 )
                    {
                      v10 = -2147024882;
                      Log_UnistoreHREvent_0(
                        2147942414LL,
                        0,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                        3066);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v90);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                      auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                      while ( 1 )
                      {
                        v49 = v88[0];
                        if ( (_QWORD *)v88[0] == v88 )
                          break;
                        v50 = *(_QWORD **)(v88[0] + 8LL);
                        v51 = *(_QWORD *)v88[0];
                        *v50 = *(_QWORD *)v88[0];
                        *(_QWORD *)(v51 + 8) = v50;
                        utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                          (__int64)v50,
                          v49);
                      }
                      goto LABEL_64;
                    }
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v90);
                    v39 = v82;
                  }
                  *((_DWORD *)v39 + 6) = 65539;
                  v45 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64 *))(**(_QWORD **)(v43 + 32) + 72LL))(
                          *(_QWORD *)(v43 + 32),
                          (char *)v82 + 24,
                          &v84);
                  v10 = v45;
                  if ( v45 < 0 )
                  {
                    Log_UnistoreHREvent_0(
                      (unsigned int)v45,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                      3072);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                    auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                    while ( 1 )
                    {
                      v61 = v88[0];
                      if ( (_QWORD *)v88[0] == v88 )
                        break;
                      v62 = *(_QWORD **)(v88[0] + 8LL);
                      v63 = *(_QWORD *)v88[0];
                      *v62 = *(_QWORD *)v88[0];
                      *(_QWORD *)(v63 + 8) = v62;
                      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                        (__int64)v62,
                        v61);
                    }
                    goto LABEL_64;
                  }
                  updated = DBGetRowUpdateContext(v84, 1, (unsigned int)&v96, a3, 0, (__int64)&v83);
                  v10 = updated;
                  if ( updated < 0 )
                  {
                    Log_UnistoreHREvent_0(
                      (unsigned int)updated,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                      3075);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                    auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                    while ( 1 )
                    {
                      v58 = v88[0];
                      if ( (_QWORD *)v88[0] == v88 )
                        break;
                      v59 = *(_QWORD **)(v88[0] + 8LL);
                      v60 = *(_QWORD *)v88[0];
                      *v59 = *(_QWORD *)v88[0];
                      *(_QWORD *)(v60 + 8) = v59;
                      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                        (__int64)v59,
                        v58);
                    }
                    goto LABEL_64;
                  }
                  v47 = *((_QWORD *)this + 4);
                  if ( v47 == *((_QWORD *)this + 5) )
                  {
                    if ( !utl::vector<ATL::CComPtr<IDBRowUpdateContext>,utl::allocator<ATL::CComPtr<IDBRowUpdateContext>>>::_PushBackOne2<ATL::CComPtr<IDBRowUpdateContext> const &>(
                            (__int64 *)this + 3,
                            &v83) )
                    {
                      v10 = -2147024882;
                      Log_UnistoreHREvent_0(
                        2147942414LL,
                        0,
                        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                        3077);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                      auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                      while ( 1 )
                      {
                        v55 = v88[0];
                        if ( (_QWORD *)v88[0] == v88 )
                          break;
                        v56 = *(_QWORD **)(v88[0] + 8LL);
                        v57 = *(_QWORD *)v88[0];
                        *v56 = *(_QWORD *)v88[0];
                        *(_QWORD *)(v57 + 8) = v56;
                        utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                          (__int64)v56,
                          v55);
                      }
                      goto LABEL_64;
                    }
                  }
                  else
                  {
                    ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(v47, v83);
                    *((_QWORD *)this + 4) += 8LL;
                  }
                  v10 = UnistoreJetMove(v85, 1, v48);
                  if ( v10 < 0 )
                    break;
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                  auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                }
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v83);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v84);
                auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v82);
                if ( v10 == -2147024871 )
                  goto LABEL_72;
                Log_UnistoreHREvent_0(
                  (unsigned int)v10,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                  3092);
                auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                while ( 1 )
                {
                  v77 = v88[0];
                  if ( (_QWORD *)v88[0] == v88 )
                    break;
                  v78 = *(_QWORD **)(v88[0] + 8LL);
                  v79 = *(_QWORD *)v88[0];
                  *v78 = *(_QWORD *)v88[0];
                  *(_QWORD *)(v79 + 8) = v78;
                  utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                    (__int64)v78,
                    v77);
                }
              }
              else
              {
                Log_UnistoreHREvent_0(
                  (unsigned int)v34,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                  3030);
                auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
                auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
                while ( 1 )
                {
                  v35 = v88[0];
                  if ( (_QWORD *)v88[0] == v88 )
                    break;
                  v36 = *(_QWORD **)(v88[0] + 8LL);
                  v37 = *(_QWORD *)v88[0];
                  *v36 = *(_QWORD *)v88[0];
                  *(_QWORD *)(v37 + 8) = v36;
                  utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                    (__int64)v36,
                    v35);
                }
              }
            }
            else
            {
              Log_UnistoreHREvent_0(
                (unsigned int)v30,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
                3028);
              auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
              auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
              while ( 1 )
              {
                v31 = v88[0];
                if ( (_QWORD *)v88[0] == v88 )
                  break;
                v32 = *(_QWORD **)(v88[0] + 8LL);
                v33 = *(_QWORD *)v88[0];
                *v32 = *(_QWORD *)v88[0];
                *(_QWORD *)(v33 + 8) = v32;
                utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                  (__int64)v32,
                  v31);
              }
            }
          }
          else
          {
            Log_UnistoreHREvent_0(
              (unsigned int)Key,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
              3016);
            auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
            auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
            while ( 1 )
            {
              v27 = v88[0];
              if ( (_QWORD *)v88[0] == v88 )
                break;
              v28 = *(_QWORD **)(v88[0] + 8LL);
              v29 = *(_QWORD *)v88[0];
              *v28 = *(_QWORD *)v88[0];
              *(_QWORD *)(v29 + 8) = v28;
              utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
                (__int64)v28,
                v27);
            }
          }
        }
        else
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v22,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
            3014);
          auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v85);
          auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
          while ( 1 )
          {
            v23 = v88[0];
            if ( (_QWORD *)v88[0] == v88 )
              break;
            v24 = *(_QWORD **)(v88[0] + 8LL);
            v25 = *(_QWORD *)v88[0];
            *v24 = *(_QWORD *)v88[0];
            *(_QWORD *)(v25 + 8) = v24;
            utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
              (__int64)v24,
              v23);
          }
        }
      }
      else
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v18,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
          3011);
        auto_DBSession::~auto_DBSession((auto_DBSession *)v87);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
        while ( 1 )
        {
          v19 = v88[0];
          if ( (_QWORD *)v88[0] == v88 )
            break;
          v20 = *(_QWORD **)(v88[0] + 8LL);
          v21 = *(_QWORD *)v88[0];
          *v20 = *(_QWORD *)v88[0];
          *(_QWORD *)(v21 + 8) = v20;
          utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
            (__int64)v20,
            v19);
        }
      }
    }
    else
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
        3008);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
      while ( 1 )
      {
        v15 = v88[0];
        if ( (_QWORD *)v88[0] == v88 )
          break;
        v16 = *(_QWORD **)(v88[0] + 8LL);
        v17 = *(_QWORD *)v88[0];
        *v16 = *(_QWORD *)v88[0];
        *(_QWORD *)(v17 + 8) = v16;
        utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
          (__int64)v16,
          v15);
      }
    }
  }
  else
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      3005);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v81);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v80);
    while ( 1 )
    {
      v11 = v88[0];
      if ( (_QWORD *)v88[0] == v88 )
        break;
      v12 = *(_QWORD **)(v88[0] + 8LL);
      v13 = *(_QWORD *)v88[0];
      *v12 = *(_QWORD *)v88[0];
      *(_QWORD *)(v13 + 8) = v12;
      utl::_ContainerBase<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned long const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(
        (__int64)v12,
        v11);
    }
  }
LABEL_64:
  v88[3] = 0;
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,ColumnDetails>,ColumnIdMappings::ColumnIdHashTraits,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,ColumnDetails>>,0>::_FreeBuckets(v88);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ab6c4  mov     [rsp-8+arg_18], rbx
0x1800ab6c9  push    rbp
0x1800ab6ca  push    rsi
0x1800ab6cb  push    rdi
0x1800ab6cc  push    r12
0x1800ab6ce  push    r13
0x1800ab6d0  push    r14
0x1800ab6d2  push    r15
0x1800ab6d4  lea     rbp, [rsp-30h]
0x1800ab6d9  sub     rsp, 130h
0x1800ab6e0  mov     rax, cs:__security_cookie
0x1800ab6e7  xor     rax, rsp
0x1800ab6ea  mov     [rbp+60h+var_38], rax
0x1800ab6ee  xor     eax, eax
0x1800ab6f0  mov     r15, rcx
0x1800ab6f3  xorps   xmm0, xmm0
0x1800ab6f6  mov     [rbp+60h+var_68], rax
0x1800ab6fa  xorps   xmm1, xmm1
0x1800ab6fd  mov     [rbp+60h+var_80], rax
0x1800ab701  lea     rcx, [rbp+60h+var_D8]
0x1800ab705  mov     r12d, r8d
0x1800ab708  movups  [rbp+60h+var_78], xmm0
0x1800ab70c  mov     rdi, rdx
0x1800ab70f  movups  [rbp+60h+var_90], xmm1
0x1800ab713  call    ??0?$unordered_map@W4US_TABLEID@@V?$CComPtr@VIDBTable@@@ATL@@U?$hash@W4US_TABLEID@@@utl@@U?$equal_to@W4US_TABLEID@@@5@V?$allocator@U?$pair@$$CBW4US_TABLEID@@V?$CComPtr@VIDBTable@@@ATL@@@utl@@@5@@utl@@QEAA@XZ; utl::unordered_map<US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<US_TABLEID>,utl::equal_to<US_TABLEID>,utl::allocator<utl::pair<US_TABLEID const,ATL::CComPtr<IDBTable>>>>::unordered_map<US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<US_TABLEID>,utl::equal_to<US_TABLEID>,utl::allocator<utl::pair<US_TABLEID const,ATL::CComPtr<IDBTable>>>>(void)
0x1800ab718  mov     rax, [rdx]
0x1800ab71b  xor     r13d, r13d
0x1800ab71e  xor     r8d, r8d
0x1800ab721  mov     [rsp+160h+var_120], r13
0x1800ab726  lea     rdx, [rbp+60h+var_90+8]
0x1800ab72a  mov     [rsp+160h+var_118], r13
0x1800ab72f  mov     rcx, rdi
0x1800ab732  mov     dword ptr [rbp+60h+var_78], 101D001Fh
0x1800ab739  mov     rax, [rax+78h]
0x1800ab73d  mov     dword ptr [rbp+60h+var_90], 20050013h
0x1800ab744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab749  mov     ebx, eax
0x1800ab74b  test    eax, eax
0x1800ab74d  jns     short loc_1800AB7A1
0x1800ab74f  mov     r9d, 0BBDh
0x1800ab755  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab75c  lea     edx, [r13+1]
0x1800ab760  mov     ecx, eax
0x1800ab762  call    Log_UnistoreHREvent_0
0x1800ab767  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab76c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab771  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab776  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab77b  mov     rdx, [rbp+60h+var_D8]
0x1800ab77f  lea     rax, [rbp+60h+var_D8]
0x1800ab783  cmp     rdx, rax
0x1800ab786  jz      loc_1800ABFBD
0x1800ab78c  mov     rcx, [rdx+8]
0x1800ab790  mov     rax, [rdx]
0x1800ab793  mov     [rcx], rax
0x1800ab796  mov     [rax+8], rcx
0x1800ab79a  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800ab79f  jmp     short loc_1800AB77B
0x1800ab7a1  mov     rax, [rdi]
0x1800ab7a4  lea     rdx, [rsp+160h+var_120]
0x1800ab7a9  mov     rcx, rdi
0x1800ab7ac  mov     rax, [rax+18h]
0x1800ab7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab7b5  mov     ebx, eax
0x1800ab7b7  test    eax, eax
0x1800ab7b9  jns     short loc_1800AB80E
0x1800ab7bb  mov     r9d, 0BC0h
0x1800ab7c1  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab7c8  mov     edx, 1
0x1800ab7cd  mov     ecx, eax
0x1800ab7cf  call    Log_UnistoreHREvent_0
0x1800ab7d4  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab7d9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab7de  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab7e3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab7e8  mov     rdx, [rbp+60h+var_D8]
0x1800ab7ec  lea     rax, [rbp+60h+var_D8]
0x1800ab7f0  cmp     rdx, rax
0x1800ab7f3  jz      loc_1800ABFBD
0x1800ab7f9  mov     rcx, [rdx+8]
0x1800ab7fd  mov     rax, [rdx]
0x1800ab800  mov     [rcx], rax
0x1800ab803  mov     [rax+8], rcx
0x1800ab807  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800ab80c  jmp     short loc_1800AB7E8
0x1800ab80e  mov     rdx, [rsp+160h+var_120]; struct IDBVolume *
0x1800ab813  lea     rcx, [rsp+160h+var_E8]; this
0x1800ab818  mov     [rsp+160h+var_E8], r13
0x1800ab81d  mov     [rbp+60h+var_E0], r13
0x1800ab821  call    ?Open@auto_DBSession@@QEAAJPEAVIDBVolume@@@Z; auto_DBSession::Open(IDBVolume *)
0x1800ab826  mov     ebx, eax
0x1800ab828  test    eax, eax
0x1800ab82a  jns     short loc_1800AB889
0x1800ab82c  mov     r9d, 0BC3h
0x1800ab832  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab839  mov     edx, 1
0x1800ab83e  mov     ecx, eax
0x1800ab840  call    Log_UnistoreHREvent_0
0x1800ab845  lea     rcx, [rsp+160h+var_E8]; this
0x1800ab84a  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800ab84f  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab854  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab859  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab85e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab863  mov     rdx, [rbp+60h+var_D8]
0x1800ab867  lea     rax, [rbp+60h+var_D8]
0x1800ab86b  cmp     rdx, rax
0x1800ab86e  jz      loc_1800ABFBD
0x1800ab874  mov     rcx, [rdx+8]
0x1800ab878  mov     rax, [rdx]
0x1800ab87b  mov     [rcx], rax
0x1800ab87e  mov     [rax+8], rcx
0x1800ab882  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800ab887  jmp     short loc_1800AB863
0x1800ab889  mov     rdx, [rsp+160h+var_E8]
0x1800ab88e  lea     rcx, [rsp+160h+var_F0]
0x1800ab893  mov     [rsp+160h+var_F8], r13
0x1800ab898  call    ??0?$CComPtrBase@VIDBVolume@@@ATL@@IEAA@PEAVIDBVolume@@@Z; ATL::CComPtrBase<IDBVolume>::CComPtrBase<IDBVolume>(IDBVolume *)
0x1800ab89d  mov     edx, 0Ah
0x1800ab8a2  lea     rcx, [rsp+160h+var_F8]
0x1800ab8a7  lea     r8d, [rdx-8]
0x1800ab8ab  call    ?Open@auto_TableHandle@@QEAAJW4US_TABLEID@@K@Z; auto_TableHandle::Open(US_TABLEID,ulong)
0x1800ab8b0  mov     ebx, eax
0x1800ab8b2  test    eax, eax
0x1800ab8b4  jns     short loc_1800AB91D
0x1800ab8b6  mov     r9d, 0BC6h
0x1800ab8bc  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab8c3  mov     edx, 1
0x1800ab8c8  mov     ecx, eax
0x1800ab8ca  call    Log_UnistoreHREvent_0
0x1800ab8cf  lea     rcx, [rsp+160h+var_F8]; this
0x1800ab8d4  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800ab8d9  lea     rcx, [rsp+160h+var_E8]; this
0x1800ab8de  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800ab8e3  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab8e8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab8ed  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab8f2  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab8f7  mov     rdx, [rbp+60h+var_D8]
0x1800ab8fb  lea     rax, [rbp+60h+var_D8]
0x1800ab8ff  cmp     rdx, rax
0x1800ab902  jz      loc_1800ABFBD
0x1800ab908  mov     rcx, [rdx+8]
0x1800ab90c  mov     rax, [rdx]
0x1800ab90f  mov     [rcx], rax
0x1800ab912  mov     [rax+8], rcx
0x1800ab916  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800ab91b  jmp     short loc_1800AB8F7
0x1800ab91d  mov     rcx, [rsp+160h+var_F8]; struct TableHandleInfo *
0x1800ab922  lea     rdx, [rbp+60h+var_90]; struct _USPROPVAL *
0x1800ab926  mov     r8d, 101h; unsigned int
0x1800ab92c  call    ?UnistoreJetMakeKey@@YAJPEAUTableHandleInfo@@PEBU_USPROPVAL@@K@Z; UnistoreJetMakeKey(TableHandleInfo *,_USPROPVAL const *,ulong)
0x1800ab931  mov     ebx, eax
0x1800ab933  test    eax, eax
0x1800ab935  jns     short loc_1800AB99E
0x1800ab937  mov     r9d, 0BC8h
0x1800ab93d  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab944  mov     edx, 1
0x1800ab949  mov     ecx, eax
0x1800ab94b  call    Log_UnistoreHREvent_0
0x1800ab950  lea     rcx, [rsp+160h+var_F8]; this
0x1800ab955  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800ab95a  lea     rcx, [rsp+160h+var_E8]; this
0x1800ab95f  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800ab964  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab969  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab96e  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab973  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab978  mov     rdx, [rbp+60h+var_D8]
0x1800ab97c  lea     rax, [rbp+60h+var_D8]
0x1800ab980  cmp     rdx, rax
0x1800ab983  jz      loc_1800ABFBD
0x1800ab989  mov     rcx, [rdx+8]
0x1800ab98d  mov     rax, [rdx]
0x1800ab990  mov     [rcx], rax
0x1800ab993  mov     [rax+8], rcx
0x1800ab997  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800ab99c  jmp     short loc_1800AB978
0x1800ab99e  mov     rcx, [rsp+160h+var_F8]; struct TableHandleInfo *
0x1800ab9a3  mov     esi, 1
0x1800ab9a8  mov     edx, esi; unsigned int
0x1800ab9aa  call    ?UnistoreJetSeek@@YAJPEAUTableHandleInfo@@K@Z; UnistoreJetSeek(TableHandleInfo *,ulong)
0x1800ab9af  mov     ebx, eax
0x1800ab9b1  cmp     eax, 80070019h
0x1800ab9b6  jz      loc_1800AC12D
0x1800ab9bc  test    eax, eax
0x1800ab9be  jns     short loc_1800ABA24
0x1800ab9c0  mov     r9d, 0BD4h
0x1800ab9c6  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ab9cd  mov     edx, esi
0x1800ab9cf  mov     ecx, eax
0x1800ab9d1  call    Log_UnistoreHREvent_0
0x1800ab9d6  lea     rcx, [rsp+160h+var_F8]; this
0x1800ab9db  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800ab9e0  lea     rcx, [rsp+160h+var_E8]; this
0x1800ab9e5  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800ab9ea  lea     rcx, [rsp+160h+var_118]; void *
0x1800ab9ef  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab9f4  lea     rcx, [rsp+160h+var_120]; void *
0x1800ab9f9  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800ab9fe  mov     rdx, [rbp+60h+var_D8]
0x1800aba02  lea     rax, [rbp+60h+var_D8]
0x1800aba06  cmp     rdx, rax
0x1800aba09  jz      loc_1800ABFBD
0x1800aba0f  mov     rcx, [rdx+8]
0x1800aba13  mov     rax, [rdx]
0x1800aba16  mov     [rcx], rax
0x1800aba19  mov     [rax+8], rcx
0x1800aba1d  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800aba22  jmp     short loc_1800AB9FE
0x1800aba24  mov     rcx, [rsp+160h+var_F8]; struct TableHandleInfo *
0x1800aba29  lea     rdx, [rbp+60h+var_90]; struct _USPROPVAL *
0x1800aba2d  mov     [rsp+160h+var_130], esi; int
0x1800aba31  mov     r9d, 200h; unsigned int
0x1800aba37  mov     dword ptr [rsp+160h+var_138], r13d; int
0x1800aba3c  mov     r8d, esi; unsigned int
0x1800aba3f  mov     dword ptr [rsp+160h+var_140], esi; int
0x1800aba43  call    ?UnistoreJetSetIndexRange@@YAJPEAUTableHandleInfo@@PEBU_USPROPVAL@@KKHHH@Z; UnistoreJetSetIndexRange(TableHandleInfo *,_USPROPVAL const *,ulong,ulong,int,int,int)
0x1800aba48  mov     ebx, eax
0x1800aba4a  test    eax, eax
0x1800aba4c  jns     short loc_1800ABAB2
0x1800aba4e  mov     r9d, 0BD6h
0x1800aba54  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800aba5b  mov     edx, esi
0x1800aba5d  mov     ecx, eax
0x1800aba5f  call    Log_UnistoreHREvent_0
0x1800aba64  lea     rcx, [rsp+160h+var_F8]; this
0x1800aba69  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x1800aba6e  lea     rcx, [rsp+160h+var_E8]; this
0x1800aba73  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800aba78  lea     rcx, [rsp+160h+var_118]; void *
0x1800aba7d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800aba82  lea     rcx, [rsp+160h+var_120]; void *
0x1800aba87  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800aba8c  mov     rdx, [rbp+60h+var_D8]
0x1800aba90  lea     rax, [rbp+60h+var_D8]
0x1800aba94  cmp     rdx, rax
0x1800aba97  jz      loc_1800ABFBD
0x1800aba9d  mov     rcx, [rdx+8]
0x1800abaa1  mov     rax, [rdx]
0x1800abaa4  mov     [rcx], rax
0x1800abaa7  mov     [rax+8], rcx
0x1800abaab  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@V?$allocator@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBKV?$CComPtr@VUnifiedStoreRundownProtection@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>,utl::allocator<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>::_DeleteNode<utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>>>(utl::_HashNode<utl::pair<ulong const,ATL::CComPtr<UnifiedStoreRundownProtection>>> *)
0x1800abab0  jmp     short loc_1800ABA8C
0x1800abab2  lea     rcx, [rsp+160h+var_110]
0x1800abab7  mov     [rbp+60h+var_48], 20030013h
0x1800ababe  mov     edi, 100h
0x1800abac3  mov     [rbp+60h+var_44], 20040013h
0x1800abaca  mov     [rbp+60h+var_40], 10003h
0x1800abad1  mov     [rsp+160h+var_110], r13
0x1800abad6  mov     [rbp+60h+var_A0], r13d
0x1800abada  mov     [rbp+60h+var_9C], 3
0x1800abae1  mov     [rbp+60h+var_98], r13d
0x1800abae5  mov     [rsp+160h+var_100], r13
0x1800abaea  mov     [rsp+160h+var_108], r13
0x1800abaef  call    ??$replace@PEAU_USPROPVALEx@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAU_USPROPVALEx@@AEAV?$auto_xxx@PEAU_USPROPVALEx@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<_USPROPVALEx *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<_USPROPVALEx *,void * (*)(void *),&LocalFree(void *),0> &)
0x1800abaf4  lea     rcx, [rbp+60h+var_A0]
0x1800abaf8  xor     edx, edx; unsigned int
0x1800abafa  mov     [rsp+160h+var_138], rcx; unsigned int *
0x1800abaff  lea     r9, [rbp+60h+var_48]; unsigned int *
0x1800abb03  mov     rcx, [rsp+160h+var_F8]; struct TableHandleInfo *
0x1800abb08  lea     r8, [rbp+60h+var_9C]; unsigned int *
0x1800abb0c  mov     [rsp+160h+var_140], rax; unsigned __int8 **
0x1800abb11  call    ?ESEReadRecordProps@@YAJPEAUTableHandleInfo@@KPEAK1PEAPEAE1@Z; ESEReadRecordProps(TableHandleInfo *,ulong,ulong *,ulong *,uchar * *,ulong *)
0x1800abb16  mov     ebx, eax
0x1800abb18  test    eax, eax
0x1800abb1a  js      loc_1800AC101
0x1800abb20  mov     rbx, [rsp+160h+var_110]
0x1800abb25  test    [rbx+6], di
0x1800abb29  jnz     loc_1800AC07A
0x1800abb2f  test    [rbx+1Eh], di
0x1800abb33  jnz     loc_1800ABFF3
0x1800abb39  mov     r14d, [rbx+8]
0x1800abb3d  lea     rdx, [rbp+60h+var_98]
0x1800abb41  mov     ecx, r14d
0x1800abb44  mov     [rbp+60h+var_B0], r14d
0x1800abb48  call    ?GetObjectTypeFromTable@DBManager@@SAJW4US_TABLEID@@PEAW4US_OBJECTTYPE@@@Z; DBManager::GetObjectTypeFromTable(US_TABLEID,US_OBJECTTYPE *)
0x1800abb4d  mov     edi, eax
0x1800abb4f  test    eax, eax
0x1800abb51  js      loc_1800ABF3D
0x1800abb57  lea     r8, [rbp+60h+var_B0]
0x1800abb5b  lea     rdx, [rbp+60h+var_60]
0x1800abb5f  lea     rcx, [rbp+60h+var_D8]
0x1800abb63  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@KU?$pair@$$CBKUScopeKnowledgeStatistics@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUScopeKnowledgeStatistics@@@utl@@@2@$0A@@utl@@K@?$_HashTable@KU?$pair@$$CBKUScopeKnowledgeStatistics@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUScopeKnowledgeStatistics@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,ScopeKnowledgeStatistics>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ScopeKnowledgeStatistics>>,0>::_FindFirst<utl::_HashTable<ulong,utl::pair<ulong const,ScopeKnowledgeStatistics>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,ScopeKnowledgeStatistics>>,0>::_FindFirstFind,ulong>(ulong const &)
0x1800abb68  mov     rdi, [rax]
0x1800abb6b  lea     rax, [rbp+60h+var_D8]
0x1800abb6f  cmp     rax, rdi
0x1800abb72  jnz     short loc_1800ABBD4
0x1800abb74  mov     rcx, [rsp+160h+var_120]
0x1800abb79  lea     rdx, [rbp+60h+var_A8]
0x1800abb7d  mov     [rbp+60h+var_A8], r13
0x1800abb81  xor     r9d, r9d
0x1800abb84  mov     [rsp+160h+var_140], rdx
0x1800abb89  xor     r8d, r8d
0x1800abb8c  mov     edx, r14d
0x1800abb8f  mov     rax, [rcx]
0x1800abb92  mov     rax, [rax+20h]
0x1800abb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abb9b  mov     ebx, eax
0x1800abb9d  test    eax, eax
  ... truncated ...
```
