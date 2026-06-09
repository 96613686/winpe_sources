# StateRepository::Cache::Entity::Protocol_NoThrow::ExistsByUserOrDefaultAccountAndProgID(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,bool &)

- ea: `0x18000c398`
- end: `0x18000cab4`
- name: `?ExistsByUserOrDefaultAccountAndProgID@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_N@Z`
- size: `1820`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000da60`

## callees

- `0x18000b1fc`
- `0x18000b2c4`
- `0x18000c350`
- `0x18000c398`
- `0x18000cabc`
- `0x18000d2f4`
- `0x18000d60c`
- `0x180010610`
- `0x180010c04`
- `0x180014090`
- `0x180014af8`
- `0x1800170f0`
- `0x180019810`
- `0x18001a528`
- `0x180031980`
- `0x180067258`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c47d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c47d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c4cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c4e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c55d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c4cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c4e4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c55d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c572`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c4f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c5bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c6ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c6dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c4f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c5bf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c667`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c6ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000c6dc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-1!SRCache_GetDefaultAccountSid` at `0x18000c434`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-1!SRCache_GetDefaultAccountSid` at `0x18000c434`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c450`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c450`

## string_xrefs

- `0x18000c48c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000c51a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000c7f7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000c53a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c581`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c59c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c6ee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c7a6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c7d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c84d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000c897`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000ca38`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000ca6a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x18000ca97`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Protocol_NoThrow::ExistsByUserOrDefaultAccountAndProgID(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  int v8; // eax
  int DefaultAccountSid; // edi
  int v10; // eax
  const char *v11; // r9
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+38h] [rbp-C8h]
  __int64 v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v42; // [rsp+70h] [rbp-90h]
  LPWSTR StringSid; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  __int128 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  __int128 v48; // [rsp+B0h] [rbp-50h]
  __int128 v49; // [rsp+C0h] [rbp-40h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+D8h] [rbp-28h]
  _OWORD v52[2]; // [rsp+E0h] [rbp-20h] BYREF
  PSID Sid[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  __int128 v57; // [rsp+130h] [rbp+30h]
  __int128 v58; // [rsp+140h] [rbp+40h]
  __int128 v59; // [rsp+150h] [rbp+50h]
  __int128 v60; // [rsp+160h] [rbp+60h]
  __int128 v61; // [rsp+170h] [rbp+70h] BYREF
  __int64 v62; // [rsp+180h] [rbp+80h]
  __int128 v63; // [rsp+188h] [rbp+88h]
  __int64 v64; // [rsp+198h] [rbp+98h]
  __int64 v65; // [rsp+1A0h] [rbp+A0h]
  __int64 v66; // [rsp+1A8h] [rbp+A8h]
  __int128 v67; // [rsp+1B0h] [rbp+B0h]
  int v68; // [rsp+1C0h] [rbp+C0h]
  __int64 v69; // [rsp+1C8h] [rbp+C8h]
  __int64 v70; // [rsp+1D0h] [rbp+D0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v35 = 0;
  v36 = 0;
  v37 = 0;
  v8 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByProgID(
         (StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *)&v35,
         a1,
         a3);
  DefaultAccountSid = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v8,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)DefaultAccountSid,
      v33);
    goto LABEL_24;
  }
  v41 = 0;
  v42 = 0;
  v10 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(&v35, 1, &v41, a4);
  DefaultAccountSid = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v10,
      v31);
    goto LABEL_34;
  }
  while ( *a4 )
  {
    v46 = 0;
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v47 = 0;
    v50 = 0;
    v51 = 0;
    DefaultAccountSid = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(
                          (__int64 *)a1,
                          *((__int64 *)&v41 + 1),
                          1,
                          (__int64)&v45,
                          a4);
    if ( DefaultAccountSid < 0 )
    {
      v25 = 941;
      goto LABEL_52;
    }
    if ( *a4 )
    {
      v55 = 0;
      *(_OWORD *)v54 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v56 = 0;
      DefaultAccountSid = StateRepository::Cache::Entity::Application_NoThrow::Get(
                            (__int64 *)a1,
                            *((__int64 *)&v45 + 1),
                            1,
                            (__int64)v54,
                            a4);
      if ( DefaultAccountSid < 0 )
      {
        v24 = 946;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
          (const char *)(unsigned int)DefaultAccountSid,
          v31);
        StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
LABEL_53:
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
LABEL_34:
        StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)&v41);
LABEL_24:
        v20 = v35;
        v35 = 0;
        if ( v20 )
          SRCacheContext_Close(v20);
        return (unsigned int)DefaultAccountSid;
      }
      if ( *a4 )
      {
        DefaultAccountSid = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                              a1,
                              a2,
                              v54[1],
                              a4);
        if ( DefaultAccountSid < 0 )
        {
          v24 = 950;
          goto LABEL_49;
        }
        if ( *a4 )
        {
          StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
          StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
          goto LABEL_37;
        }
      }
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
    }
    ++v36;
    DefaultAccountSid = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(&v35, 1, &v41, a4);
    if ( DefaultAccountSid < 0 )
    {
      v25 = 960;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
        (const char *)(unsigned int)DefaultAccountSid,
        v31);
      goto LABEL_53;
    }
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
  }
  v44 = 0;
  Sid[0] = 0;
  DefaultAccountSid = SRCache_GetDefaultAccountSid(Sid);
  if ( DefaultAccountSid < 0 )
  {
    v17 = 363;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)DefaultAccountSid,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)DefaultAccountSid,
      v32);
    v18 = *((_QWORD *)&v42 + 1);
    *((_QWORD *)&v42 + 1) = 0;
    if ( v18 )
      SRCache_Free(v18);
    v19 = v42;
    *(_QWORD *)&v42 = 0;
    if ( v19 )
      SRCache_Free(v19);
    goto LABEL_24;
  }
  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
  {
    v12 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, StringSid, &v44);
    DefaultAccountSid = v12;
    if ( v12 >= 0 )
    {
      if ( StringSid )
        LocalFree(StringSid);
      goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v12,
      v31);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    goto LABEL_55;
  }
  DefaultAccountSid = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xAA,
                        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                        v11);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
  if ( DefaultAccountSid < 0 )
  {
LABEL_55:
    v17 = 364;
    goto LABEL_19;
  }
LABEL_10:
  if ( !v44 )
  {
LABEL_11:
    v13 = *((_QWORD *)&v42 + 1);
    *a4 = 0;
    *((_QWORD *)&v42 + 1) = 0;
    if ( v13 )
      SRCache_Free(v13);
    v14 = v42;
    *(_QWORD *)&v42 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_15;
  }
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v26 = StateRepository::Cache::Entity::Protocol_NoThrow::FindByProgID(
          a1,
          a3,
          (struct StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow *)&v38);
  DefaultAccountSid = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CA,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v26,
      v31);
LABEL_32:
    v21 = v38;
    v38 = 0;
    if ( v21 )
      SRCacheContext_Close(v21);
    goto LABEL_34;
  }
  memset(v52, 0, sizeof(v52));
  v27 = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(&v38, 1, v52, a4);
  DefaultAccountSid = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v27,
      v31);
LABEL_31:
    StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v52);
    goto LABEL_32;
  }
  while ( 1 )
  {
    if ( !*a4 )
    {
      StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v52);
      v23 = v38;
      v38 = 0;
      if ( v23 )
        SRCacheContext_Close(v23);
      goto LABEL_11;
    }
    v46 = 0;
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v47 = 0;
    v50 = 0;
    v51 = 0;
    DefaultAccountSid = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(
                          (__int64 *)a1,
                          *((__int64 *)&v52[0] + 1),
                          1,
                          (__int64)&v45,
                          a4);
    if ( DefaultAccountSid < 0 )
    {
      v30 = 979;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
        (const char *)(unsigned int)DefaultAccountSid,
        v34);
      goto LABEL_81;
    }
    if ( !*a4 )
      goto LABEL_71;
    v55 = 0;
    *(_OWORD *)v54 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v56 = 0;
    DefaultAccountSid = StateRepository::Cache::Entity::Application_NoThrow::Get(
                          (__int64 *)a1,
                          *((__int64 *)&v45 + 1),
                          1,
                          (__int64)v54,
                          a4);
    if ( DefaultAccountSid < 0 )
    {
      v29 = 984;
LABEL_76:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
        (const char *)(unsigned int)DefaultAccountSid,
        v34);
LABEL_77:
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
LABEL_81:
      StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
      goto LABEL_31;
    }
    if ( *a4 )
    {
      DefaultAccountSid = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                            a1,
                            v44,
                            v54[1],
                            a4);
      if ( DefaultAccountSid < 0 )
      {
        v29 = 988;
        goto LABEL_76;
      }
      if ( *a4 )
        break;
    }
LABEL_70:
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
LABEL_71:
    ++v39;
    DefaultAccountSid = StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(&v38, 1, v52, a4);
    if ( DefaultAccountSid < 0 )
    {
      v30 = 1005;
      goto LABEL_80;
    }
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
  }
  v62 = 0;
  v61 = 0;
  v67 = 0;
  v64 = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v28 = StateRepository::Cache::Entity::Package_NoThrow::Get((__int64 *)a1, v54[1], 2, (__int64 *)&v61, a4);
  DefaultAccountSid = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Protocol.hpp",
      (const char *)(unsigned int)v28,
      v34);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v61);
    goto LABEL_77;
  }
  if ( !*a4 )
  {
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v61);
    goto LABEL_70;
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v61);
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v54);
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v45);
  StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)v52);
  v22 = v38;
  v38 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
LABEL_37:
  StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow((StateRepository::Cache::Entity::FileTypeAssociation_NoThrow *)&v41);
LABEL_15:
  v15 = v35;
  v35 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18000c398  push    rbp
0x18000c39a  push    rbx
0x18000c39b  push    rsi
0x18000c39c  push    rdi
0x18000c39d  push    r12
0x18000c39f  push    r13
0x18000c3a1  push    r14
0x18000c3a3  push    r15
0x18000c3a5  lea     rbp, [rsp-0E8h]
0x18000c3ad  sub     rsp, 1E8h
0x18000c3b4  xor     r12d, r12d
0x18000c3b7  mov     rsi, rdx
0x18000c3ba  mov     rdx, rcx; struct StateRepository::Cache::Manager_NoThrow *
0x18000c3bd  mov     [rsp+220h+var_1F0], r12
0x18000c3c2  mov     r14, rcx
0x18000c3c5  mov     [rsp+220h+var_1E8], r12d
0x18000c3ca  lea     rcx, [rsp+220h+var_1F0]; this
0x18000c3cf  mov     [rsp+220h+var_1E0], r12
0x18000c3d4  mov     rbx, r9
0x18000c3d7  mov     r15, r8
0x18000c3da  call    ?OpenByProgID@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@PEBG@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::OpenByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *)
0x18000c3df  mov     edi, eax
0x18000c3e1  test    eax, eax
0x18000c3e3  js      loc_18000C57A
0x18000c3e9  xorps   xmm0, xmm0
0x18000c3ec  lea     r13d, [r12+1]
0x18000c3f1  xorps   xmm1, xmm1
0x18000c3f4  lea     r8, [rsp+220h+var_1C0]
0x18000c3f9  mov     edx, r13d
0x18000c3fc  lea     rcx, [rsp+220h+var_1F0]
0x18000c401  mov     r9, rbx
0x18000c404  movdqu  [rsp+220h+var_1C0], xmm0
0x18000c40a  movdqu  [rsp+220h+var_1B0], xmm1
0x18000c410  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x18000c415  mov     edi, eax
0x18000c417  test    eax, eax
0x18000c419  js      loc_18000C6E7
0x18000c41f  cmp     [rbx], r12b
0x18000c422  jnz     loc_18000C5CC
0x18000c428  lea     rcx, [rbp+120h+Sid]
0x18000c42c  mov     [rbp+120h+var_198], r12
0x18000c430  mov     [rbp+120h+Sid], r12
0x18000c434  call    cs:__imp_SRCache_GetDefaultAccountSid
0x18000c43a  mov     edi, eax
0x18000c43c  test    eax, eax
0x18000c43e  js      loc_18000C515
0x18000c444  mov     rcx, [rbp+120h+Sid]; Sid
0x18000c448  lea     rdx, [rbp+120h+StringSid]; StringSid
0x18000c44c  mov     [rbp+120h+StringSid], r12
0x18000c450  call    cs:__imp_ConvertSidToStringSidW
0x18000c456  test    eax, eax
0x18000c458  jz      short loc_18000C485
0x18000c45a  mov     rdx, [rbp+120h+StringSid]; unsigned __int16 *
0x18000c45e  lea     r8, [rbp+120h+var_198]; __int64 *
0x18000c462  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18000c465  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000c46a  mov     edi, eax
0x18000c46c  test    eax, eax
0x18000c46e  js      loc_18000C7F0
0x18000c474  mov     rcx, [rbp+120h+StringSid]; hMem
0x18000c478  test    rcx, rcx
0x18000c47b  jz      short loc_18000C4B3
0x18000c47d  call    cs:__imp_LocalFree
0x18000c483  jmp     short loc_18000C4B3
0x18000c485  mov     rcx, [rbp+128h]; this
0x18000c48c  lea     rsi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c493  mov     r8, rsi; unsigned int
0x18000c496  mov     edx, 0AAh; void *
0x18000c49b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c4a0  lea     rcx, [rbp+120h+StringSid]
0x18000c4a4  mov     edi, eax
0x18000c4a6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000c4ab  test    edi, edi
0x18000c4ad  js      loc_18000C817
0x18000c4b3  cmp     [rbp+120h+var_198], r12
0x18000c4b7  jnz     loc_18000C821
0x18000c4bd  mov     rcx, qword ptr [rsp+220h+var_1B0+8]
0x18000c4c2  mov     [rbx], r12b
0x18000c4c5  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x18000c4ca  test    rcx, rcx
0x18000c4cd  jz      short loc_18000C4D5
0x18000c4cf  call    cs:__imp_SRCache_Free
0x18000c4d5  mov     rcx, qword ptr [rsp+220h+var_1B0]
0x18000c4da  mov     qword ptr [rsp+220h+var_1B0], r12
0x18000c4df  test    rcx, rcx
0x18000c4e2  jz      short loc_18000C4EA
0x18000c4e4  call    cs:__imp_SRCache_Free
0x18000c4ea  mov     rcx, [rsp+220h+var_1F0]
0x18000c4ef  mov     [rsp+220h+var_1F0], r12
0x18000c4f4  test    rcx, rcx
0x18000c4f7  jz      short loc_18000C4FF
0x18000c4f9  call    cs:__imp_SRCacheContext_Close
0x18000c4ff  xor     eax, eax
0x18000c501  add     rsp, 1E8h
0x18000c508  pop     r15
0x18000c50a  pop     r14
0x18000c50c  pop     r13
0x18000c50e  pop     r12
0x18000c510  pop     rdi
0x18000c511  pop     rsi
0x18000c512  pop     rbx
0x18000c513  pop     rbp
0x18000c514  retn
0x18000c515  mov     edx, 16Bh; void *
0x18000c51a  lea     rsi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c521  mov     rcx, [rbp+128h]; this
0x18000c528  mov     r9d, edi; char *
0x18000c52b  mov     r8, rsi; unsigned int
0x18000c52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c533  mov     rcx, [rbp+128h]; this
0x18000c53a  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c541  mov     r9d, edi; char *
0x18000c544  mov     edx, 3C5h; void *
0x18000c549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c54e  mov     rcx, qword ptr [rsp+220h+var_1B0+8]
0x18000c553  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x18000c558  test    rcx, rcx
0x18000c55b  jz      short loc_18000C563
0x18000c55d  call    cs:__imp_SRCache_Free
0x18000c563  mov     rcx, qword ptr [rsp+220h+var_1B0]
0x18000c568  mov     qword ptr [rsp+220h+var_1B0], r12
0x18000c56d  test    rcx, rcx
0x18000c570  jz      short loc_18000C5B0
0x18000c572  call    cs:__imp_SRCache_Free
0x18000c578  jmp     short loc_18000C5B0
0x18000c57a  mov     rcx, [rbp+128h]; this
0x18000c581  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c588  mov     r9d, edi; char *
0x18000c58b  mov     edx, 33Eh; void *
0x18000c590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c595  mov     rcx, [rbp+128h]; this
0x18000c59c  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c5a3  mov     r9d, edi; char *
0x18000c5a6  mov     edx, 3A4h; void *
0x18000c5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5b0  mov     rcx, [rsp+220h+var_1F0]
0x18000c5b5  mov     [rsp+220h+var_1F0], r12
0x18000c5ba  test    rcx, rcx
0x18000c5bd  jz      short loc_18000C5C5
0x18000c5bf  call    cs:__imp_SRCacheContext_Close
0x18000c5c5  mov     eax, edi
0x18000c5c7  jmp     loc_18000C501
0x18000c5cc  mov     rdx, qword ptr [rsp+220h+var_1C0+8]
0x18000c5d1  lea     r9, [rbp+120h+var_190]
0x18000c5d5  xorps   xmm0, xmm0
0x18000c5d8  mov     [rbp+120h+var_180], r12
0x18000c5dc  xorps   xmm1, xmm1
0x18000c5df  movdqa  [rbp+120h+var_190], xmm0
0x18000c5e4  mov     r8, r13
0x18000c5e7  movdqa  [rbp+120h+var_170], xmm0
0x18000c5ec  mov     rcx, r14
0x18000c5ef  movdqa  [rbp+120h+var_160], xmm1
0x18000c5f4  mov     [rbp+120h+var_178], r12
0x18000c5f8  mov     [rbp+120h+var_150], r12
0x18000c5fc  mov     [rbp+120h+var_148], r12d
0x18000c600  mov     qword ptr [rsp+220h+var_200], rbx; int
0x18000c605  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18000c60a  mov     edi, eax
0x18000c60c  test    eax, eax
0x18000c60e  js      loc_18000C7C7
0x18000c614  cmp     [rbx], r12b
0x18000c617  jnz     loc_18000C707
0x18000c61d  add     [rsp+220h+var_1E8], r13d
0x18000c622  lea     r8, [rsp+220h+var_1C0]
0x18000c627  mov     r9, rbx
0x18000c62a  lea     rcx, [rsp+220h+var_1F0]
0x18000c62f  mov     rdx, r13
0x18000c632  call    ?Get@ProtocolIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Protocol_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x18000c637  mov     edi, eax
0x18000c639  test    eax, eax
0x18000c63b  js      loc_18000C7C0
0x18000c641  lea     rcx, [rbp+120h+var_190]; this
0x18000c645  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000c64a  jmp     loc_18000C41F
0x18000c64f  lea     rcx, [rbp+120h+var_140]; this
0x18000c653  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x18000c658  mov     rcx, [rsp+220h+var_1D8]
0x18000c65d  mov     [rsp+220h+var_1D8], r12
0x18000c662  test    rcx, rcx
0x18000c665  jz      short loc_18000C66D
0x18000c667  call    cs:__imp_SRCacheContext_Close
0x18000c66d  lea     rcx, [rsp+220h+var_1C0]; this
0x18000c672  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x18000c677  jmp     loc_18000C5B0
0x18000c67c  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18000c681  lea     rcx, [rbp+120h+var_110]; this
0x18000c685  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000c68a  lea     rcx, [rbp+120h+var_190]; this
0x18000c68e  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000c693  lea     rcx, [rbp+120h+var_140]; this
0x18000c697  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x18000c69c  mov     rcx, [rsp+220h+var_1D8]
0x18000c6a1  mov     [rsp+220h+var_1D8], r12
0x18000c6a6  test    rcx, rcx
0x18000c6a9  jz      short loc_18000C6B1
0x18000c6ab  call    cs:__imp_SRCacheContext_Close
0x18000c6b1  lea     rcx, [rsp+220h+var_1C0]; this
0x18000c6b6  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x18000c6bb  jmp     loc_18000C4EA
0x18000c6c0  lea     rcx, [rbp+120h+var_140]; this
0x18000c6c4  call    ??1FileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::FileTypeAssociation_NoThrow::~FileTypeAssociation_NoThrow(void)
0x18000c6c9  mov     rcx, [rsp+220h+var_1D8]
0x18000c6ce  mov     [rsp+220h+var_1D8], r12
0x18000c6d3  test    rcx, rcx
0x18000c6d6  jz      loc_18000C4BD
0x18000c6dc  call    cs:__imp_SRCacheContext_Close
0x18000c6e2  jmp     loc_18000C4BD
0x18000c6e7  mov     rcx, [rbp+128h]; this
0x18000c6ee  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c6f5  mov     r9d, edi; char *
0x18000c6f8  mov     edx, 3A7h; void *
0x18000c6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c702  jmp     loc_18000C66D
0x18000c707  mov     rdx, qword ptr [rbp+120h+var_190+8]
0x18000c70b  lea     r9, [rbp+120h+var_110]
0x18000c70f  xorps   xmm0, xmm0
0x18000c712  mov     [rbp+120h+var_100], r12
0x18000c716  xorps   xmm1, xmm1
0x18000c719  movdqa  xmmword ptr [rbp+120h+var_110], xmm0
0x18000c71e  mov     r8, r13
0x18000c721  movdqa  [rbp+120h+var_F0], xmm0
0x18000c726  mov     rcx, r14
0x18000c729  movdqa  [rbp+120h+var_E0], xmm1
0x18000c72e  movdqa  [rbp+120h+var_D0], xmm0
0x18000c733  movdqa  [rbp+120h+var_C0], xmm1
0x18000c738  mov     [rbp+120h+var_F8], r12
0x18000c73c  mov     qword ptr [rsp+220h+var_200], rbx; int
0x18000c741  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18000c746  mov     edi, eax
0x18000c748  test    eax, eax
0x18000c74a  js      short loc_18000C79A
0x18000c74c  cmp     [rbx], r12b
0x18000c74f  jz      short loc_18000C785
0x18000c751  mov     r8, [rbp+120h+var_110+8]; __int64
0x18000c755  mov     r9, rbx; bool *
0x18000c758  mov     rdx, rsi; __int64
0x18000c75b  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18000c75e  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18000c763  mov     edi, eax
0x18000c765  test    eax, eax
0x18000c767  js      short loc_18000C793
0x18000c769  cmp     [rbx], r12b
0x18000c76c  jz      short loc_18000C785
0x18000c76e  lea     rcx, [rbp+120h+var_110]; this
0x18000c772  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000c777  lea     rcx, [rbp+120h+var_190]; this
0x18000c77b  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000c780  jmp     loc_18000C6B1
0x18000c785  lea     rcx, [rbp+120h+var_110]; this
0x18000c789  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000c78e  jmp     loc_18000C61D
0x18000c793  mov     edx, 3B6h
0x18000c798  jmp     short loc_18000C79F
0x18000c79a  mov     edx, 3B2h; void *
0x18000c79f  mov     rcx, [rbp+128h]; this
0x18000c7a6  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c7ad  mov     r9d, edi; char *
0x18000c7b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7b5  lea     rcx, [rbp+120h+var_110]; this
0x18000c7b9  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000c7be  jmp     short loc_18000C7E2
0x18000c7c0  mov     edx, 3C0h
0x18000c7c5  jmp     short loc_18000C7CC
0x18000c7c7  mov     edx, 3ADh; void *
0x18000c7cc  mov     rcx, [rbp+128h]; this
0x18000c7d3  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c7da  mov     r9d, edi; char *
0x18000c7dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7e2  lea     rcx, [rbp+120h+var_190]; this
0x18000c7e6  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000c7eb  jmp     loc_18000C66D
0x18000c7f0  mov     rcx, [rbp+128h]; this
0x18000c7f7  lea     rsi, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c7fe  mov     r8, rsi; unsigned int
0x18000c801  mov     r9d, eax; char *
0x18000c804  mov     edx, 0ACh; void *
0x18000c809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c80e  lea     rcx, [rbp+120h+StringSid]
0x18000c812  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000c817  mov     edx, 16Ch
0x18000c81c  jmp     loc_18000C521
0x18000c821  lea     r8, [rsp+220h+var_1D8]; this
0x18000c826  mov     [rsp+220h+var_1D8], r12
0x18000c82b  mov     rdx, r15; unsigned __int16 *
0x18000c82e  mov     [rsp+220h+var_1D0], r12d
0x18000c833  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x18000c836  mov     [rsp+220h+var_1C8], r12
0x18000c83b  call    ?FindByProgID@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAVProtocolIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Protocol_NoThrow::FindByProgID(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::ProtocolIndexIterator_NoThrow &)
0x18000c840  mov     edi, eax
0x18000c842  test    eax, eax
0x18000c844  jns     short loc_18000C866
0x18000c846  mov     rcx, [rbp+128h]; this
0x18000c84d  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000c854  mov     r9d, eax; char *
0x18000c857  mov     edx, 3CAh; void *
0x18000c85c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c861  jmp     loc_18000C658
0x18000c866  xorps   xmm0, xmm0
0x18000c869  lea     r8, [rbp+120h+var_140]
0x18000c86d  xorps   xmm1, xmm1
  ... truncated ...
```
