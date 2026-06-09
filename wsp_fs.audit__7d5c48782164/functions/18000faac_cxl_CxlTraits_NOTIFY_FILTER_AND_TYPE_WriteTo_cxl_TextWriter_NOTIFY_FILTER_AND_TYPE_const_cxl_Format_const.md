# cxl::CxlTraits<_NOTIFY_FILTER_AND_TYPE>::WriteTo(cxl::TextWriter &,_NOTIFY_FILTER_AND_TYPE const &,cxl::Format const &)

- ea: `0x18000faac`
- end: `0x1800105e5`
- name: `?WriteTo@?$CxlTraits@U_NOTIFY_FILTER_AND_TYPE@@@cxl@@SAXAEAVTextWriter@2@AEBU_NOTIFY_FILTER_AND_TYPE@@AEBUFormat@2@@Z`
- size: `2873`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022200`
- `0x180022220`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d600`
- `0x18000f2c4`
- `0x18000f5a8`
- `0x18000faac`
- `0x180010b90`

## string_xrefs

- `0x18000fc5e`: `{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_COMMON_PROPERTY_V2 )`
- `0x18000fcec`: `{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RENAME_V2 )`
- `0x18000fd1a`: `{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_DELETED_V2 )`
- `0x18000fd48`: `{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_COMMON_PROPERTY_V2 )`
- `0x18000feec`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_COMMON_PROPERTY_V2 )`
- `0x18001002e`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DELETED_V2 )`
- `0x18001005c`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DLL_UPGRADED_V2 )`
- `0x1800100be`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DELETED_V2 )`
- `0x1800100ec`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_COMMON_PROPERTY_V2 )`
- `0x18001016a`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DLL_UPGRADED_V2 )`
- `0x180010198`: `{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_DELETED_V2 )`
- `0x1800101c6`: `{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_COMMON_PROPERTY_V2 )`
- `0x180010272`: `{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_DELETED_V2 )`
- `0x1800102a0`: `{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_COMMON_PROPERTY_V2 )`
- `0x180010380`: `{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_DELETED_V2 )`
- `0x1800103ae`: `{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_COMMON_PROPERTY_V2 )`
- `0x1800104b6`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_ATTRIBUTES_V2 )`
- `0x1800104e4`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_NAME_V2 )`
- `0x18001050e`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_SUBTREE_V2 )`
- `0x180010538`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_VALUE_V2 )`
- `0x180010562`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_HANDLE_CLOSE_V2 )`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall cxl::CxlTraits<_NOTIFY_FILTER_AND_TYPE>::WriteTo(struct cxl::TextWriter *a1, __int64 a2)
{
  __int64 v4; // rdx
  _BYTE v6[32]; // [rsp+20h] [rbp-30h] BYREF

  if ( !*(_DWORD *)a2 || !*(_QWORD *)(a2 + 8) )
    return cxl::TextWriter::WriteFmt<33>(a1, "<Invalid NOTIFY_FILTER_AND_TYPE>");
  std::wstring::wstring(v6);
  if ( *(_DWORD *)v4 == 1 )
  {
    if ( (*(_BYTE *)(v4 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RECONNECT_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_STATE_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 1 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_GROUP_ADDED_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 1 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_HANDLE_CLOSE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 1 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_NETWORK_ADDED_V2 )");
              std::wstring::assign(v6, L" + ");
            }
            if ( *(_DWORD *)a2 == 1 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_NODE_ADDED_V2 )");
                std::wstring::assign(v6, L" + ");
              }
              if ( *(_DWORD *)a2 == 1 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RESOURCE_TYPE_ADDED_V2 )");
                  std::wstring::assign(v6, L" + ");
                }
                if ( *(_DWORD *)a2 == 1 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_COMMON_PROPERTY_V2 )");
                    std::wstring::assign(v6, L" + ");
                  }
                  if ( *(_DWORD *)a2 == 1 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_PRIVATE_PROPERTY_V2 )");
                      std::wstring::assign(v6, L" + ");
                    }
                    if ( *(_DWORD *)a2 == 1 )
                    {
                      if ( (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                      {
                        cxl::TextWriter::Write<char,std::wstring,>(
                          a1,
                          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_LOST_NOTIFICATIONS_V2 )");
                        std::wstring::assign(v6, L" + ");
                      }
                      if ( *(_DWORD *)a2 == 1 && (*(_DWORD *)(a2 + 8) & 0x400LL) != 0 )
                      {
                        cxl::TextWriter::Write<char,std::wstring,>(
                          a1,
                          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RENAME_V2 )");
                        std::wstring::assign(v6, L" + ");
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 2 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(a1, "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_DELETED_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 2 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_COMMON_PROPERTY_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 2 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_PRIVATE_PROPERTY_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 2 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_STATE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 2 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_OWNER_NODE_V2 )");
              std::wstring::assign(v6, L" + ");
            }
            if ( *(_DWORD *)a2 == 2 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_PREFERRED_OWNERS_V2 )");
                std::wstring::assign(v6, L" + ");
              }
              if ( *(_DWORD *)a2 == 2 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_ADDED_V2 )");
                  std::wstring::assign(v6, L" + ");
                }
                if ( *(_DWORD *)a2 == 2 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_GAINED_V2 )");
                    std::wstring::assign(v6, L" + ");
                  }
                  if ( *(_DWORD *)a2 == 2 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_LOST_V2 )");
                      std::wstring::assign(v6, L" + ");
                    }
                    if ( *(_DWORD *)a2 == 2 && (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_HANDLE_CLOSE_V2 )");
                      std::wstring::assign(v6, L" + ");
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 3 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_COMMON_PROPERTY_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 3 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_PRIVATE_PROPERTY_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 3 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_STATE_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 3 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_OWNER_GROUP_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 3 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DEPENDENCIES_V2 )");
              std::wstring::assign(v6, L" + ");
            }
            if ( *(_DWORD *)a2 == 3 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DEPENDENTS_V2 )");
                std::wstring::assign(v6, L" + ");
              }
              if ( *(_DWORD *)a2 == 3 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_POSSIBLE_OWNERS_V2 )");
                  std::wstring::assign(v6, L" + ");
                }
                if ( *(_DWORD *)a2 == 3 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DELETED_V2 )");
                    std::wstring::assign(v6, L" + ");
                  }
                  if ( *(_DWORD *)a2 == 3 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DLL_UPGRADED_V2 )");
                      std::wstring::assign(v6, L" + ");
                    }
                    if ( *(_DWORD *)a2 == 3 && (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_HANDLE_CLOSE_V2 )");
                      std::wstring::assign(v6, L" + ");
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 4 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DELETED_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 4 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_COMMON_PROPERTY_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 4 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_PRIVATE_PROPERTY_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 4 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_POSSIBLE_OWNERS_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 4 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DLL_UPGRADED_V2 )");
            std::wstring::assign(v6, L" + ");
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 5 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_DELETED_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 5 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_COMMON_PROPERTY_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 5 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_PRIVATE_PROPERTY_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 5 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_STATE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 5 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_HANDLE_CLOSE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 6 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_DELETED_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 6 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_COMMON_PROPERTY_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 6 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_PRIVATE_PROPERTY_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 6 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_STATE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 6 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_HANDLE_CLOSE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 7 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_NETINTERFACE_ADDED_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 7 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(a1, "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_DELETED_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 7 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_COMMON_PROPERTY_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 7 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_PRIVATE_PROPERTY_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 7 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_STATE_V2 )");
              std::wstring::assign(v6, L" + ");
            }
            if ( *(_DWORD *)a2 == 7 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_GROUP_GAINED_V2 )");
                std::wstring::assign(v6, L" + ");
              }
              if ( *(_DWORD *)a2 == 7 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_GROUP_LOST_V2 )");
                  std::wstring::assign(v6, L" + ");
                }
                if ( *(_DWORD *)a2 == 7 && *(char *)(a2 + 8) < 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_HANDLE_CLOSE_V2 )");
                  std::wstring::assign(v6, L" + ");
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 8 )
  {
    if ( (*(_BYTE *)(a2 + 8) & 1) != 0 )
    {
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_ATTRIBUTES_V2 )");
      std::wstring::assign(v6, L" + ");
    }
    if ( *(_DWORD *)a2 == 8 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_NAME_V2 )");
        std::wstring::assign(v6, L" + ");
      }
      if ( *(_DWORD *)a2 == 8 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_SUBTREE_V2 )");
          std::wstring::assign(v6, L" + ");
        }
        if ( *(_DWORD *)a2 == 8 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_VALUE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
          if ( *(_DWORD *)a2 == 8 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_HANDLE_CLOSE_V2 )");
            std::wstring::assign(v6, L" + ");
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 9 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
  {
    cxl::TextWriter::Write<char,std::wstring,>(a1, "{0}CLUSTER_OBJECT_TYPE_QUORUM( CLUSTER_CHANGE_QUORUM_STATE_V2 )");
    std::wstring::assign(v6, L" + ");
  }
  return std::wstring::_Tidy_deallocate(v6);
}

```

## disassembly

```asm
0x18000faac  mov     [rsp-28h+arg_8], rbx
0x18000fab1  mov     [rsp-28h+arg_10], rsi
0x18000fab6  push    rbp
0x18000fab7  push    rdi
0x18000fab8  push    r12
0x18000faba  push    r14
0x18000fabc  push    r15
0x18000fabe  mov     rbp, rsp
0x18000fac1  sub     rsp, 50h
0x18000fac5  mov     rax, cs:__security_cookie
0x18000facc  xor     rax, rsp
0x18000facf  mov     [rbp+var_10], rax
0x18000fad3  mov     rbx, rdx
0x18000fad6  mov     rdi, rcx
0x18000fad9  cmp     dword ptr [rdx], 0
0x18000fadc  jz      loc_1800105B3
0x18000fae2  cmp     qword ptr [rdx+8], 0
0x18000fae7  jz      loc_1800105B3
0x18000faed  lea     rcx, [rbp+var_30]
0x18000faf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000faf6  nop
0x18000faf7  lea     rsi, asc_180128D00; " + "
0x18000fafe  mov     r12d, 2
0x18000fb04  lea     r15d, [r12-1]
0x18000fb09  cmp     [rdx], r15d
0x18000fb0c  jnz     loc_18000FD07
0x18000fb12  test    [rdx+8], r15b
0x18000fb16  jz      short loc_18000FB37
0x18000fb18  lea     r8, [rbp+var_30]
0x18000fb1c  lea     rdx, a0ClusterObject_36; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fb23  mov     rcx, rdi
0x18000fb26  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fb2b  mov     rdx, rsi
0x18000fb2e  lea     rcx, [rbp+var_30]
0x18000fb32  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fb37  cmp     [rbx], r15d
0x18000fb3a  jnz     loc_18000FD07
0x18000fb40  test    [rbx+8], r12b
0x18000fb44  jz      short loc_18000FB65
0x18000fb46  lea     r8, [rbp+var_30]
0x18000fb4a  lea     rdx, a0ClusterObject_46; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fb51  mov     rcx, rdi
0x18000fb54  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fb59  mov     rdx, rsi
0x18000fb5c  lea     rcx, [rbp+var_30]
0x18000fb60  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fb65  cmp     [rbx], r15d
0x18000fb68  jnz     loc_18000FD07
0x18000fb6e  test    byte ptr [rbx+8], 4
0x18000fb72  jz      short loc_18000FB93
0x18000fb74  lea     r8, [rbp+var_30]
0x18000fb78  lea     rdx, a0ClusterObject_56; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fb7f  mov     rcx, rdi
0x18000fb82  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fb87  mov     rdx, rsi
0x18000fb8a  lea     rcx, [rbp+var_30]
0x18000fb8e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fb93  cmp     [rbx], r15d
0x18000fb96  jnz     loc_18000FD07
0x18000fb9c  test    byte ptr [rbx+8], 8
0x18000fba0  jz      short loc_18000FBC1
0x18000fba2  lea     r8, [rbp+var_30]
0x18000fba6  lea     rdx, a0ClusterObject_44; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fbad  mov     rcx, rdi
0x18000fbb0  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fbb5  mov     rdx, rsi
0x18000fbb8  lea     rcx, [rbp+var_30]
0x18000fbbc  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fbc1  cmp     [rbx], r15d
0x18000fbc4  jnz     loc_18000FD07
0x18000fbca  test    byte ptr [rbx+8], 10h
0x18000fbce  jz      short loc_18000FBEF
0x18000fbd0  lea     r8, [rbp+var_30]
0x18000fbd4  lea     rdx, a0ClusterObject_45; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fbdb  mov     rcx, rdi
0x18000fbde  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fbe3  mov     rdx, rsi
0x18000fbe6  lea     rcx, [rbp+var_30]
0x18000fbea  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fbef  cmp     [rbx], r15d
0x18000fbf2  jnz     loc_18000FD07
0x18000fbf8  test    byte ptr [rbx+8], 20h
0x18000fbfc  jz      short loc_18000FC1D
0x18000fbfe  lea     r8, [rbp+var_30]
0x18000fc02  lea     rdx, a0ClusterObject_26; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fc09  mov     rcx, rdi
0x18000fc0c  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fc11  mov     rdx, rsi
0x18000fc14  lea     rcx, [rbp+var_30]
0x18000fc18  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fc1d  cmp     [rbx], r15d
0x18000fc20  jnz     loc_18000FD07
0x18000fc26  test    byte ptr [rbx+8], 40h
0x18000fc2a  jz      short loc_18000FC4B
0x18000fc2c  lea     r8, [rbp+var_30]
0x18000fc30  lea     rdx, a0ClusterObject_16; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fc37  mov     rcx, rdi
0x18000fc3a  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fc3f  mov     rdx, rsi
0x18000fc42  lea     rcx, [rbp+var_30]
0x18000fc46  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fc4b  cmp     [rbx], r15d
0x18000fc4e  jnz     loc_18000FD07
0x18000fc54  test    byte ptr [rbx+8], 80h
0x18000fc58  jz      short loc_18000FC79
0x18000fc5a  lea     r8, [rbp+var_30]
0x18000fc5e  lea     rdx, a0ClusterObject_5; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fc65  mov     rcx, rdi
0x18000fc68  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fc6d  mov     rdx, rsi
0x18000fc70  lea     rcx, [rbp+var_30]
0x18000fc74  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fc79  cmp     [rbx], r15d
0x18000fc7c  jnz     loc_18000FD07
0x18000fc82  mov     eax, [rbx+8]
0x18000fc85  bt      rax, 8
0x18000fc8a  jnb     short loc_18000FCAB
0x18000fc8c  lea     r8, [rbp+var_30]
0x18000fc90  lea     rdx, a0ClusterObject_42; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fc97  mov     rcx, rdi
0x18000fc9a  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fc9f  mov     rdx, rsi
0x18000fca2  lea     rcx, [rbp+var_30]
0x18000fca6  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fcab  cmp     [rbx], r15d
0x18000fcae  jnz     short loc_18000FD07
0x18000fcb0  mov     eax, [rbx+8]
0x18000fcb3  bt      rax, 9
0x18000fcb8  jnb     short loc_18000FCD9
0x18000fcba  lea     r8, [rbp+var_30]
0x18000fcbe  lea     rdx, a0ClusterObject_53; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fcc5  mov     rcx, rdi
0x18000fcc8  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fccd  mov     rdx, rsi
0x18000fcd0  lea     rcx, [rbp+var_30]
0x18000fcd4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fcd9  cmp     [rbx], r15d
0x18000fcdc  jnz     short loc_18000FD07
0x18000fcde  mov     eax, [rbx+8]
0x18000fce1  bt      rax, 0Ah
0x18000fce6  jnb     short loc_18000FD07
0x18000fce8  lea     r8, [rbp+var_30]
0x18000fcec  lea     rdx, a0ClusterObject_8; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000fcf3  mov     rcx, rdi
0x18000fcf6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fcfb  mov     rdx, rsi
0x18000fcfe  lea     rcx, [rbp+var_30]
0x18000fd02  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fd07  cmp     [rbx], r12d
0x18000fd0a  jnz     loc_18000FED3
0x18000fd10  test    [rbx+8], r15b
0x18000fd14  jz      short loc_18000FD35
0x18000fd16  lea     r8, [rbp+var_30]
0x18000fd1a  lea     rdx, a0ClusterObject_57; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fd21  mov     rcx, rdi
0x18000fd24  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fd29  mov     rdx, rsi
0x18000fd2c  lea     rcx, [rbp+var_30]
0x18000fd30  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fd35  cmp     [rbx], r12d
0x18000fd38  jnz     loc_18000FED3
0x18000fd3e  test    [rbx+8], r12b
0x18000fd42  jz      short loc_18000FD63
0x18000fd44  lea     r8, [rbp+var_30]
0x18000fd48  lea     rdx, a0ClusterObject_19; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fd4f  mov     rcx, rdi
0x18000fd52  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fd57  mov     rdx, rsi
0x18000fd5a  lea     rcx, [rbp+var_30]
0x18000fd5e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fd63  cmp     [rbx], r12d
0x18000fd66  jnz     loc_18000FED3
0x18000fd6c  test    byte ptr [rbx+8], 4
0x18000fd70  jz      short loc_18000FD91
0x18000fd72  lea     r8, [rbp+var_30]
0x18000fd76  lea     rdx, a0ClusterObject_27; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fd7d  mov     rcx, rdi
0x18000fd80  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fd85  mov     rdx, rsi
0x18000fd88  lea     rcx, [rbp+var_30]
0x18000fd8c  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fd91  cmp     [rbx], r12d
0x18000fd94  jnz     loc_18000FED3
0x18000fd9a  test    byte ptr [rbx+8], 8
0x18000fd9e  jz      short loc_18000FDBF
0x18000fda0  lea     r8, [rbp+var_30]
0x18000fda4  lea     rdx, a0ClusterObject_51; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fdab  mov     rcx, rdi
0x18000fdae  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fdb3  mov     rdx, rsi
0x18000fdb6  lea     rcx, [rbp+var_30]
0x18000fdba  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fdbf  cmp     [rbx], r12d
0x18000fdc2  jnz     loc_18000FED3
0x18000fdc8  test    byte ptr [rbx+8], 10h
0x18000fdcc  jz      short loc_18000FDED
0x18000fdce  lea     r8, [rbp+var_30]
0x18000fdd2  lea     rdx, a0ClusterObject_34; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fdd9  mov     rcx, rdi
0x18000fddc  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fde1  mov     rdx, rsi
0x18000fde4  lea     rcx, [rbp+var_30]
0x18000fde8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fded  cmp     [rbx], r12d
0x18000fdf0  jnz     loc_18000FED3
0x18000fdf6  test    byte ptr [rbx+8], 20h
0x18000fdfa  jz      short loc_18000FE1B
0x18000fdfc  lea     r8, [rbp+var_30]
0x18000fe00  lea     rdx, a0ClusterObject_39; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fe07  mov     rcx, rdi
0x18000fe0a  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fe0f  mov     rdx, rsi
0x18000fe12  lea     rcx, [rbp+var_30]
0x18000fe16  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fe1b  cmp     [rbx], r12d
0x18000fe1e  jnz     loc_18000FED3
0x18000fe24  test    byte ptr [rbx+8], 40h
0x18000fe28  jz      short loc_18000FE49
0x18000fe2a  lea     r8, [rbp+var_30]
0x18000fe2e  lea     rdx, a0ClusterObject_2; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fe35  mov     rcx, rdi
0x18000fe38  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fe3d  mov     rdx, rsi
0x18000fe40  lea     rcx, [rbp+var_30]
0x18000fe44  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fe49  cmp     [rbx], r12d
0x18000fe4c  jnz     loc_18000FED3
0x18000fe52  test    byte ptr [rbx+8], 80h
0x18000fe56  jz      short loc_18000FE77
0x18000fe58  lea     r8, [rbp+var_30]
0x18000fe5c  lea     rdx, a0ClusterObject_13; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fe63  mov     rcx, rdi
0x18000fe66  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fe6b  mov     rdx, rsi
0x18000fe6e  lea     rcx, [rbp+var_30]
0x18000fe72  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fe77  cmp     [rbx], r12d
0x18000fe7a  jnz     short loc_18000FED3
0x18000fe7c  mov     eax, [rbx+8]
0x18000fe7f  bt      rax, 8
0x18000fe84  jnb     short loc_18000FEA5
0x18000fe86  lea     r8, [rbp+var_30]
0x18000fe8a  lea     rdx, a0ClusterObject_20; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fe91  mov     rcx, rdi
0x18000fe94  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fe99  mov     rdx, rsi
0x18000fe9c  lea     rcx, [rbp+var_30]
0x18000fea0  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fea5  cmp     [rbx], r12d
0x18000fea8  jnz     short loc_18000FED3
0x18000feaa  mov     eax, [rbx+8]
0x18000fead  bt      rax, 9
0x18000feb2  jnb     short loc_18000FED3
0x18000feb4  lea     r8, [rbp+var_30]
0x18000feb8  lea     rdx, a0ClusterObject_21; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000febf  mov     rcx, rdi
0x18000fec2  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fec7  mov     rdx, rsi
0x18000feca  lea     rcx, [rbp+var_30]
0x18000fece  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fed3  mov     r14d, 3
0x18000fed9  cmp     [rbx], r14d
0x18000fedc  jnz     loc_1800100A5
0x18000fee2  test    [rbx+8], r15b
0x18000fee6  jz      short loc_18000FF07
0x18000fee8  lea     r8, [rbp+var_30]
0x18000feec  lea     rdx, a0ClusterObject_32; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000fef3  mov     rcx, rdi
0x18000fef6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fefb  mov     rdx, rsi
0x18000fefe  lea     rcx, [rbp+var_30]
0x18000ff02  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000ff07  cmp     [rbx], r14d
0x18000ff0a  jnz     loc_1800100A5
0x18000ff10  test    [rbx+8], r12b
0x18000ff14  jz      short loc_18000FF35
0x18000ff16  lea     r8, [rbp+var_30]
0x18000ff1a  lea     rdx, a0ClusterObject_25; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000ff21  mov     rcx, rdi
0x18000ff24  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000ff29  mov     rdx, rsi
0x18000ff2c  lea     rcx, [rbp+var_30]
0x18000ff30  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000ff35  cmp     [rbx], r14d
0x18000ff38  jnz     loc_1800100A5
0x18000ff3e  test    byte ptr [rbx+8], 4
0x18000ff42  jz      short loc_18000FF63
0x18000ff44  lea     r8, [rbp+var_30]
0x18000ff48  lea     rdx, a0ClusterObject_38; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000ff4f  mov     rcx, rdi
0x18000ff52  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000ff57  mov     rdx, rsi
0x18000ff5a  lea     rcx, [rbp+var_30]
0x18000ff5e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000ff63  cmp     [rbx], r14d
0x18000ff66  jnz     loc_1800100A5
0x18000ff6c  test    byte ptr [rbx+8], 8
0x18000ff70  jz      short loc_18000FF91
0x18000ff72  lea     r8, [rbp+var_30]
0x18000ff76  lea     rdx, a0ClusterObject_15; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
  ... truncated ...
```
