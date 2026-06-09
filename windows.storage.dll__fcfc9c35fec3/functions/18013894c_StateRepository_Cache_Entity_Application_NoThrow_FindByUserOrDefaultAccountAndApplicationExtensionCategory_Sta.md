# StateRepository::Cache::Entity::Application_NoThrow::FindByUserOrDefaultAccountAndApplicationExtensionCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,long (*)(void *,__int64,StateRepository::Cache::Entity::Application_NoThrow &),void *)

- ea: `0x18013894c`
- end: `0x1801391e4`
- name: `?FindByUserOrDefaultAccountAndApplicationExtensionCategory@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@P6AJPEAX1AEAV1234@@Z4@Z`
- size: `2200`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x18056c7e0`

## callees

- `0x180038f50`
- `0x180077880`
- `0x180135b18`
- `0x180136834`
- `0x180136e90`
- `0x180137810`
- `0x18013894c`
- `0x1801391ec`
- `0x180139314`
- `0x1801393e8`
- `0x180323a94`
- `0x18036ec44`
- `0x1803b1f60`
- `0x18056b398`
- `0x18056b480`
- `0x18056caa4`
- `0x18056cc2c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138a73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138c3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138cb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138d4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138dc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138e08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138f06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013909e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180139114`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180139190`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138a73`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138c3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138cb0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138d4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138dc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138e08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180138f06`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18013909e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180139114`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180139190`

## string_xrefs

- `0x1801389ff`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138a4e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138c8b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138cd7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138d14`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138d98`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138e41`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138e8e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180138ee1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1801390ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18013912e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18013915c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1801389e4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180138cf9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-IdList.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::FindByUserOrDefaultAccountAndApplicationExtensionCategory(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        void *a6)
{
  _QWORD *v9; // rbx
  unsigned __int64 v10; // r14
  int v11; // eax
  __int64 v12; // rdx
  int appended; // edi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v17; // rdx
  unsigned __int64 j; // rax
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rdx
  bool v23; // zf
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int DefaultAccount; // eax
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  unsigned __int64 i; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rcx
  int *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int *v44; // [rsp+20h] [rbp-E0h]
  bool v45[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  int v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  __int128 v49; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v50; // [rsp+60h] [rbp-A0h]
  __int128 v51; // [rsp+70h] [rbp-90h]
  int v52[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v53; // [rsp+90h] [rbp-70h]
  int v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v56[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h]
  __int128 v62; // [rsp+100h] [rbp+0h]
  __int128 v63; // [rsp+110h] [rbp+10h] BYREF
  __int64 v64; // [rsp+120h] [rbp+20h]
  __int128 v65; // [rsp+128h] [rbp+28h]
  __int64 v66; // [rsp+138h] [rbp+38h]
  __int64 v67; // [rsp+140h] [rbp+40h]
  __int64 v68; // [rsp+148h] [rbp+48h]
  __int128 v69; // [rsp+150h] [rbp+50h]
  int v70; // [rsp+160h] [rbp+60h]
  __int64 v71; // [rsp+168h] [rbp+68h]
  __int64 v72; // [rsp+170h] [rbp+70h]
  void *lpMem; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v74; // [rsp+188h] [rbp+88h]
  __int64 v75; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v9 = 0;
  lpMem = 0;
  v10 = 0;
  v74 = 0;
  v75 = 0;
  v45[0] = 0;
  if ( !a2 )
  {
LABEL_55:
    v55 = 0;
    DefaultAccount = StateRepository::Cache::Entity::User_NoThrow::GetDefaultAccount(a1, &v55);
    appended = DefaultAccount;
    if ( DefaultAccount < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5EA,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
        (const char *)(unsigned int)DefaultAccount,
        (int)v41);
      goto LABEL_50;
    }
    if ( v55 )
    {
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v29 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::FindByUser(
              a1,
              v55,
              (struct StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow *)&v46);
      appended = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5EF,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
          (const char *)(unsigned int)v29,
          (int)v41);
        goto LABEL_49;
      }
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v31 = StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(&v46, v30, &v49, v45);
      appended = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F2,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
          (const char *)(unsigned int)v31,
          (int)v41);
LABEL_63:
        v32 = *((_QWORD *)&v51 + 1);
        *((_QWORD *)&v51 + 1) = 0;
        if ( v32 )
          goto LABEL_48;
        goto LABEL_49;
      }
      while ( v45[0] )
      {
        *(_OWORD *)v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v62 = 0;
        v44 = (int *)v45;
        appended = StateRepository::Cache::Entity::Application_NoThrow::Get(a1, *((_QWORD *)&v50 + 1), 17, v56);
        if ( appended < 0 )
        {
          v39 = 1527;
          goto LABEL_95;
        }
        if ( v45[0] )
        {
          v63 = 0;
          v64 = 0;
          v65 = 0;
          v66 = 0;
          v67 = 0;
          v68 = 0;
          v69 = 0;
          v70 = 0;
          v71 = 0;
          v72 = 0;
          v44 = (int *)v45;
          appended = StateRepository::Cache::Entity::Package_NoThrow::Get(a1, v56[1], 3, &v63);
          if ( appended < 0 )
          {
            v38 = 1532;
LABEL_91:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v38,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
              (const char *)(unsigned int)appended,
              (int)v45);
            goto LABEL_92;
          }
          if ( v45[0] )
          {
            for ( i = 0; i < v10; ++i )
            {
              if ( v9[i] == v64 )
                goto LABEL_82;
            }
            appended = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ExistsByApplicationAndCategory(
                         a1,
                         v56[0],
                         a3,
                         v45);
            if ( appended < 0 )
            {
              v38 = 1538;
              goto LABEL_91;
            }
            if ( v45[0] )
            {
              *(_OWORD *)v52 = 0;
              v53 = 0;
              v54 = 0;
              v44 = v52;
              appended = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(
                           a1,
                           a2,
                           *((_QWORD *)&v63 + 1));
              if ( appended < 0 )
              {
                v36 = 1544;
                goto LABEL_87;
              }
              if ( !v45[0] || (v54 & 0x10000000) == 0 )
              {
                appended = ApplicationUserModelIdSetAppendHandler(
                             a6,
                             v55,
                             (struct StateRepository::Cache::Entity::Application_NoThrow *)v56);
                if ( appended < 0 )
                {
                  v36 = 1547;
LABEL_87:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v36,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
                    (const char *)(unsigned int)appended,
                    (int)v52);
                  v37 = *((_QWORD *)&v53 + 1);
                  *((_QWORD *)&v53 + 1) = 0;
                  if ( v37 )
                    SRCache_Free();
LABEL_92:
                  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
LABEL_96:
                  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v56);
                  goto LABEL_63;
                }
              }
              v35 = *((_QWORD *)&v53 + 1);
              *((_QWORD *)&v53 + 1) = 0;
              if ( v35 )
                SRCache_Free();
            }
          }
LABEL_82:
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
        }
        ++v47;
        appended = StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(&v46, v33, &v49, v45);
        if ( appended < 0 )
        {
          v39 = 1554;
LABEL_95:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
            (const char *)(unsigned int)appended,
            (int)v44);
          goto LABEL_96;
        }
        StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v56);
      }
      v40 = *((_QWORD *)&v51 + 1);
      *((_QWORD *)&v51 + 1) = 0;
      if ( v40 )
        SRCache_Free();
      wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v46, 0);
    }
    if ( v9 )
      CZeroInitNew::operator delete(v9);
    return 0;
  }
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v11 = StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::OpenByUser(
          (StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow *)&v46,
          a1,
          a2);
  appended = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x449,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)(unsigned int)v11,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)appended,
      v42);
LABEL_7:
    wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v46, 0);
    return (unsigned int)appended;
  }
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v14 = StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(&v46, v12, &v49, v45);
  appended = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v14,
      (int)v41);
    v15 = *((_QWORD *)&v51 + 1);
    *((_QWORD *)&v51 + 1) = 0;
    if ( v15 )
      SRCache_Free();
    goto LABEL_7;
  }
  while ( 1 )
  {
    if ( !v45[0] )
    {
      v27 = *((_QWORD *)&v51 + 1);
      *((_QWORD *)&v51 + 1) = 0;
      if ( v27 )
        SRCache_Free();
      wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v46, 0);
      goto LABEL_55;
    }
    *(_OWORD *)v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v41 = (int *)v45;
    appended = StateRepository::Cache::Entity::Application_NoThrow::Get(a1, *((_QWORD *)&v50 + 1), 17, v56);
    if ( appended < 0 )
    {
      v26 = 1482;
      goto LABEL_46;
    }
    if ( v45[0] )
    {
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v41 = (int *)v45;
      appended = StateRepository::Cache::Entity::Package_NoThrow::Get(a1, v56[1], 3, &v63);
      if ( appended < 0 )
      {
        v24 = 1487;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
          (const char *)(unsigned int)appended,
          (int)v45);
LABEL_34:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
        goto LABEL_47;
      }
      if ( v45[0] )
      {
        for ( j = 0; j < v10; ++j )
        {
          if ( v9[j] == v64 )
            goto LABEL_20;
        }
        v19 = StateRepository::Cache::IdList_NoThrow::Add((StateRepository::Cache::IdList_NoThrow *)&lpMem, v64);
        v20 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-IdList.hpp",
            (const char *)(unsigned int)v19,
            (int)v45);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D2,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
            (const char *)v20,
            v43);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
          StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v56);
          v25 = *((_QWORD *)&v51 + 1);
          *((_QWORD *)&v51 + 1) = 0;
          if ( v25 )
            SRCache_Free();
          wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v46, 0);
          if ( lpMem )
            CZeroInitNew::operator delete(lpMem);
          return v20;
        }
        v10 = v74;
        v9 = lpMem;
LABEL_20:
        appended = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ExistsByApplicationAndCategory(
                     a1,
                     v56[0],
                     a3,
                     v45);
        if ( appended < 0 )
        {
          v24 = 1493;
          goto LABEL_37;
        }
        if ( !v45[0] )
          goto LABEL_28;
        *(_OWORD *)v52 = 0;
        v53 = 0;
        v54 = 0;
        v41 = v52;
        appended = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(
                     a1,
                     a2,
                     *((_QWORD *)&v63 + 1));
        if ( appended < 0 )
        {
          v22 = 1499;
        }
        else
        {
          if ( v45[0] && (v54 & 0x10000000) != 0
            || (appended = ApplicationUserModelIdSetAppendHandler(
                             a6,
                             a2,
                             (struct StateRepository::Cache::Entity::Application_NoThrow *)v56),
                appended >= 0) )
          {
            v21 = *((_QWORD *)&v53 + 1);
            *((_QWORD *)&v53 + 1) = 0;
            if ( v21 )
              SRCache_Free();
            goto LABEL_28;
          }
          v22 = 1502;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
          (const char *)(unsigned int)appended,
          (int)v52);
        v23 = *((_QWORD *)&v53 + 1) == 0;
        *((_QWORD *)&v53 + 1) = 0;
        if ( !v23 )
          SRCache_Free();
        goto LABEL_34;
      }
LABEL_28:
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
    }
    ++v47;
    appended = StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(&v46, v17, &v49, v45);
    if ( appended < 0 )
      break;
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v56);
  }
  v26 = 1508;
LABEL_46:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
    (const char *)(unsigned int)appended,
    (int)v41);
LABEL_47:
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v56);
  v23 = *((_QWORD *)&v51 + 1) == 0;
  *((_QWORD *)&v51 + 1) = 0;
  if ( v23 )
    goto LABEL_49;
LABEL_48:
  SRCache_Free();
LABEL_49:
  wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v46, 0);
LABEL_50:
  if ( v9 )
    CZeroInitNew::operator delete(v9);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18013894c  mov     [rsp-8+arg_18], rbx
0x180138951  push    rbp
0x180138952  push    rsi
0x180138953  push    rdi
0x180138954  push    r12
0x180138956  push    r13
0x180138958  push    r14
0x18013895a  push    r15
0x18013895c  lea     rbp, [rsp-0A0h]
0x180138964  sub     rsp, 1A0h
0x18013896b  mov     rax, cs:__security_cookie
0x180138972  xor     rax, rsp
0x180138975  mov     [rbp+0D0h+var_38], rax
0x18013897c  mov     r13, r8
0x18013897f  mov     r15, rdx
0x180138982  mov     rsi, rcx
0x180138985  mov     r12, [rbp+0D0h+arg_28]
0x18013898c  xor     edi, edi
0x18013898e  mov     ebx, edi
0x180138990  mov     [rbp+0D0h+lpMem], rbx
0x180138997  mov     r14d, edi
0x18013899a  mov     [rbp+0D0h+var_48], rdi
0x1801389a1  mov     [rbp+0D0h+var_40], rdi
0x1801389a8  mov     [rsp+1D0h+var_1A0], dil
0x1801389ad  test    rdx, rdx
0x1801389b0  jz      loc_180138E21
0x1801389b6  mov     [rsp+1D0h+var_198], rdi
0x1801389bb  mov     [rsp+1D0h+var_190], edi
0x1801389bf  mov     [rsp+1D0h+var_188], rdi
0x1801389c4  mov     r8, rdx; __int64
0x1801389c7  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x1801389ca  lea     rcx, [rsp+1D0h+var_198]; this
0x1801389cf  call    ?OpenByUser@ApplicationUserIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::OpenByUser(StateRepository::Cache::Manager_NoThrow &,__int64)
0x1801389d4  mov     edi, eax
0x1801389d6  test    eax, eax
0x1801389d8  jns     short loc_180138A12
0x1801389da  mov     rcx, [rbp+0D8h]; this
0x1801389e1  mov     r9d, eax; char *
0x1801389e4  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1801389eb  mov     edx, 449h; void *
0x1801389f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801389f5  mov     rcx, [rbp+0D8h]; this
0x1801389fc  mov     r9d, edi; char *
0x1801389ff  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138a06  mov     edx, 5C2h; void *
0x180138a0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138a10  jmp     short loc_180138A80
0x180138a12  xorps   xmm0, xmm0
0x180138a15  movdqu  [rsp+1D0h+var_180], xmm0
0x180138a1b  xorps   xmm1, xmm1
0x180138a1e  movdqu  [rsp+1D0h+var_170], xmm1
0x180138a24  movdqu  [rsp+1D0h+var_160], xmm0
0x180138a2a  lea     r9, [rsp+1D0h+var_1A0]
0x180138a2f  lea     r8, [rsp+1D0h+var_180]
0x180138a34  lea     rcx, [rsp+1D0h+var_198]
0x180138a39  call    ?Get@ApplicationUserIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationUser_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x180138a3e  mov     edi, eax
0x180138a40  test    eax, eax
0x180138a42  jns     short loc_180138A94
0x180138a44  mov     rcx, [rbp+0D8h]; this
0x180138a4b  mov     r9d, eax; char *
0x180138a4e  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138a55  mov     edx, 5C5h; void *
0x180138a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138a5f  nop
0x180138a60  mov     rcx, qword ptr [rsp+1D0h+var_160+8]
0x180138a65  mov     qword ptr [rsp+1D0h+var_160+8], 0
0x180138a6e  test    rcx, rcx
0x180138a71  jz      short loc_180138A80
0x180138a73  call    cs:__imp_SRCache_Free
0x180138a7a  nop     dword ptr [rax+rax+00h]
0x180138a7f  nop
0x180138a80  xor     edx, edx
0x180138a82  lea     rcx, [rsp+1D0h+var_198]
0x180138a87  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x180138a8c  nop
0x180138a8d  mov     eax, edi
0x180138a8f  jmp     loc_1801391B9
0x180138a94  xor     edi, edi
0x180138a96  cmp     [rsp+1D0h+var_1A0], dil
0x180138a9b  jz      loc_180138DF9
0x180138aa1  xorps   xmm0, xmm0
0x180138aa4  movdqa  xmmword ptr [rbp+0D0h+var_120], xmm0
0x180138aa9  mov     [rbp+0D0h+var_110], rdi
0x180138aad  mov     [rbp+0D0h+var_108], rdi
0x180138ab1  movdqa  [rbp+0D0h+var_100], xmm0
0x180138ab6  xorps   xmm1, xmm1
0x180138ab9  movdqa  [rbp+0D0h+var_F0], xmm1
0x180138abe  movdqa  [rbp+0D0h+var_E0], xmm0
0x180138ac3  movdqa  [rbp+0D0h+var_D0], xmm1
0x180138ac8  lea     rax, [rsp+1D0h+var_1A0]
0x180138acd  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x180138ad2  lea     r9, [rbp+0D0h+var_120]
0x180138ad6  lea     r8d, [rdi+11h]
0x180138ada  mov     rdx, qword ptr [rsp+1D0h+var_170+8]
0x180138adf  mov     rcx, rsi
0x180138ae2  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180138ae7  mov     edi, eax
0x180138ae9  xor     eax, eax
0x180138aeb  test    edi, edi
0x180138aed  js      loc_180138D90
0x180138af3  cmp     [rsp+1D0h+var_1A0], al
0x180138af7  jz      loc_180138C53
0x180138afd  xorps   xmm0, xmm0
0x180138b00  movdqa  [rbp+0D0h+var_C0], xmm0
0x180138b05  mov     [rbp+0D0h+var_B0], rax
0x180138b09  xorps   xmm1, xmm1
0x180138b0c  movups  [rbp+0D0h+var_A8], xmm1
0x180138b10  mov     [rbp+0D0h+var_98], rax
0x180138b14  mov     [rbp+0D0h+var_90], rax
0x180138b18  mov     [rbp+0D0h+var_88], rax
0x180138b1c  movdqa  [rbp+0D0h+var_80], xmm0
0x180138b21  mov     [rbp+0D0h+var_70], eax
0x180138b24  mov     [rbp+0D0h+var_68], rax
0x180138b28  mov     [rbp+0D0h+var_60], rax
0x180138b2c  lea     rax, [rsp+1D0h+var_1A0]
0x180138b31  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x180138b36  lea     r9, [rbp+0D0h+var_C0]
0x180138b3a  mov     r8d, 3
0x180138b40  mov     rdx, [rbp+0D0h+var_120+8]
0x180138b44  mov     rcx, rsi
0x180138b47  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180138b4c  mov     edi, eax
0x180138b4e  test    eax, eax
0x180138b50  js      loc_180138D7F
0x180138b56  cmp     [rsp+1D0h+var_1A0], 0
0x180138b5b  jz      loc_180138C4A
0x180138b61  mov     rdx, [rbp+0D0h+var_B0]; __int64
0x180138b65  xor     eax, eax
0x180138b67  cmp     rax, r14
0x180138b6a  jnb     short loc_180138B77
0x180138b6c  cmp     [rbx+rax*8], rdx
0x180138b70  jz      short loc_180138B9B
0x180138b72  inc     rax
0x180138b75  jmp     short loc_180138B67
0x180138b77  lea     rcx, [rbp+0D0h+lpMem]; this
0x180138b7e  call    ?Add@IdList_NoThrow@Cache@StateRepository@@QEAAJ_J@Z; StateRepository::Cache::IdList_NoThrow::Add(__int64)
0x180138b83  mov     ebx, eax
0x180138b85  test    eax, eax
0x180138b87  js      loc_180138CEF
0x180138b8d  mov     r14, [rbp+0D0h+var_48]
0x180138b94  mov     rbx, [rbp+0D0h+lpMem]
0x180138b9b  lea     r9, [rsp+1D0h+var_1A0]; bool *
0x180138ba0  mov     r8, r13; unsigned __int16 *
0x180138ba3  mov     rdx, [rbp+0D0h+var_120]; __int64
0x180138ba7  mov     rcx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180138baa  call    ?ExistsByApplicationAndCategory@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ExistsByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)
0x180138baf  mov     edi, eax
0x180138bb1  test    eax, eax
0x180138bb3  js      loc_180138CD2
0x180138bb9  cmp     [rsp+1D0h+var_1A0], 0
0x180138bbe  jz      loc_180138C4A
0x180138bc4  xorps   xmm0, xmm0
0x180138bc7  movdqu  xmmword ptr [rbp+0D0h+var_150], xmm0
0x180138bcc  xorps   xmm1, xmm1
0x180138bcf  movdqu  [rbp+0D0h+var_140], xmm1
0x180138bd4  mov     [rbp+0D0h+var_130], 0
0x180138bdb  lea     rax, [rsp+1D0h+var_1A0]
0x180138be0  mov     [rsp+1D0h+var_1A8], rax
0x180138be5  lea     rax, [rbp+0D0h+var_150]
0x180138be9  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x180138bee  mov     r8, qword ptr [rbp+0D0h+var_C0+8]
0x180138bf2  mov     rdx, r15
0x180138bf5  mov     rcx, rsi
0x180138bf8  call    ?GetByUserAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetByUserAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)
0x180138bfd  mov     edi, eax
0x180138bff  test    eax, eax
0x180138c01  js      loc_180138CCB
0x180138c07  cmp     [rsp+1D0h+var_1A0], 0
0x180138c0c  jz      short loc_180138C17
0x180138c0e  test    [rbp+0D0h+var_130], 10000000h
0x180138c15  jnz     short loc_180138C2C
0x180138c17  lea     r8, [rbp+0D0h+var_120]; struct StateRepository::Cache::Entity::Application_NoThrow *
0x180138c1b  mov     rdx, r15; __int64
0x180138c1e  mov     rcx, r12; void *
0x180138c21  call    ?ApplicationUserModelIdSetAppendHandler@@YAJPEAX_JAEAVApplication_NoThrow@Entity@Cache@StateRepository@@@Z; ApplicationUserModelIdSetAppendHandler(void *,__int64,StateRepository::Cache::Entity::Application_NoThrow &)
0x180138c26  mov     edi, eax
0x180138c28  test    eax, eax
0x180138c2a  js      short loc_180138C83
0x180138c2c  mov     rcx, qword ptr [rbp+0D0h+var_140+8]
0x180138c30  mov     qword ptr [rbp+0D0h+var_140+8], 0
0x180138c38  test    rcx, rcx
0x180138c3b  jz      short loc_180138C4A
0x180138c3d  call    cs:__imp_SRCache_Free
0x180138c44  nop     dword ptr [rax+rax+00h]
0x180138c49  nop
0x180138c4a  lea     rcx, [rbp+0D0h+var_C0]; this
0x180138c4e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180138c53  inc     [rsp+1D0h+var_190]
0x180138c57  lea     r9, [rsp+1D0h+var_1A0]
0x180138c5c  lea     r8, [rsp+1D0h+var_180]
0x180138c61  lea     rcx, [rsp+1D0h+var_198]
0x180138c66  call    ?Get@ApplicationUserIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationUser_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUserIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)
0x180138c6b  mov     edi, eax
0x180138c6d  test    eax, eax
0x180138c6f  js      loc_180138D89
0x180138c75  lea     rcx, [rbp+0D0h+var_120]; this
0x180138c79  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180138c7e  jmp     loc_180138A94
0x180138c83  mov     edx, 5DEh; void *
0x180138c88  mov     r9d, edi; char *
0x180138c8b  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138c92  mov     rcx, [rbp+0D8h]; this
0x180138c99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138c9e  nop
0x180138c9f  mov     rcx, qword ptr [rbp+0D0h+var_140+8]
0x180138ca3  test    rcx, rcx
0x180138ca6  mov     qword ptr [rbp+0D0h+var_140+8], 0
0x180138cae  jz      short loc_180138CBD
0x180138cb0  call    cs:__imp_SRCache_Free
0x180138cb7  nop     dword ptr [rax+rax+00h]
0x180138cbc  nop
0x180138cbd  lea     rcx, [rbp+0D0h+var_C0]; this
0x180138cc1  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180138cc6  jmp     loc_180138DAC
0x180138ccb  mov     edx, 5DBh
0x180138cd0  jmp     short loc_180138C88
0x180138cd2  mov     edx, 5D5h; void *
0x180138cd7  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138cde  mov     r9d, edi; char *
0x180138ce1  mov     rcx, [rbp+0D8h]; this
0x180138ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138ced  jmp     short loc_180138CBD
0x180138cef  mov     rcx, [rbp+0D8h]; this
0x180138cf6  mov     r9d, ebx; char *
0x180138cf9  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138d00  mov     edx, 2Ch ; ','; void *
0x180138d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138d0a  mov     rcx, [rbp+0D8h]; this
0x180138d11  mov     r9d, ebx; char *
0x180138d14  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138d1b  mov     edx, 5D2h; void *
0x180138d20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138d25  nop
0x180138d26  lea     rcx, [rbp+0D0h+var_C0]; this
0x180138d2a  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180138d2f  nop
0x180138d30  lea     rcx, [rbp+0D0h+var_120]; this
0x180138d34  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180138d39  nop
0x180138d3a  mov     rcx, qword ptr [rsp+1D0h+var_160+8]
0x180138d3f  mov     qword ptr [rsp+1D0h+var_160+8], 0
0x180138d48  test    rcx, rcx
0x180138d4b  jz      short loc_180138D5A
0x180138d4d  call    cs:__imp_SRCache_Free
0x180138d54  nop     dword ptr [rax+rax+00h]
0x180138d59  nop
0x180138d5a  xor     edx, edx
0x180138d5c  lea     rcx, [rsp+1D0h+var_198]
0x180138d61  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x180138d66  nop
0x180138d67  mov     rcx, [rbp+0D0h+lpMem]; lpMem
0x180138d6e  test    rcx, rcx
0x180138d71  jz      short loc_180138D78
0x180138d73  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180138d78  mov     eax, ebx
0x180138d7a  jmp     loc_1801391B9
0x180138d7f  mov     edx, 5CFh
0x180138d84  jmp     loc_180138CD7
0x180138d89  mov     edx, 5E4h
0x180138d8e  jmp     short loc_180138D95
0x180138d90  mov     edx, 5CAh; void *
0x180138d95  mov     r9d, edi; char *
0x180138d98  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180138d9f  mov     rcx, [rbp+0D8h]; this
0x180138da6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138dab  nop
0x180138dac  lea     rcx, [rbp+0D0h+var_120]; this
0x180138db0  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180138db5  nop
0x180138db6  mov     rcx, qword ptr [rsp+1D0h+var_160+8]
0x180138dbb  test    rcx, rcx
0x180138dbe  mov     qword ptr [rsp+1D0h+var_160+8], 0
0x180138dc7  jz      short loc_180138DD6
0x180138dc9  call    cs:__imp_SRCache_Free
0x180138dd0  nop     dword ptr [rax+rax+00h]
0x180138dd5  nop
0x180138dd6  xor     edx, edx
0x180138dd8  lea     rcx, [rsp+1D0h+var_198]
0x180138ddd  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x180138de2  nop
0x180138de3  test    rbx, rbx
0x180138de6  jz      loc_180138A8D
0x180138dec  mov     rcx, rbx; lpMem
0x180138def  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180138df4  jmp     loc_180138A8D
0x180138df9  mov     rcx, qword ptr [rsp+1D0h+var_160+8]
0x180138dfe  mov     qword ptr [rsp+1D0h+var_160+8], rdi
0x180138e03  test    rcx, rcx
0x180138e06  jz      short loc_180138E15
0x180138e08  call    cs:__imp_SRCache_Free
0x180138e0f  nop     dword ptr [rax+rax+00h]
0x180138e14  nop
0x180138e15  xor     edx, edx
0x180138e17  lea     rcx, [rsp+1D0h+var_198]
0x180138e1c  call    ?reset@?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheContext@@@Z; wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(SRCacheContext *)
0x180138e21  mov     [rbp+0D0h+var_128], rdi
0x180138e25  lea     rdx, [rbp+0D0h+var_128]; __int64 *
0x180138e29  mov     rcx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180138e2c  call    ?GetDefaultAccount@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@AEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetDefaultAccount(StateRepository::Cache::Manager_NoThrow &,__int64 &)
  ... truncated ...
```
