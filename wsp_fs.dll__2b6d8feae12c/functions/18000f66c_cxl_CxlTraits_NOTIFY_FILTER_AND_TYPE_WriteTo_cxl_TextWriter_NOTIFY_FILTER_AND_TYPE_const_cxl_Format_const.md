# cxl::CxlTraits<_NOTIFY_FILTER_AND_TYPE>::WriteTo(cxl::TextWriter &,_NOTIFY_FILTER_AND_TYPE const &,cxl::Format const &)

- ea: `0x18000f66c`
- end: `0x1800101a4`
- name: `?WriteTo@?$CxlTraits@U_NOTIFY_FILTER_AND_TYPE@@@cxl@@SAXAEAVTextWriter@2@AEBU_NOTIFY_FILTER_AND_TYPE@@AEBUFormat@2@@Z`
- size: `2872`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021550`
- `0x180021570`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d298`
- `0x18000ee84`
- `0x18000f168`
- `0x18000f66c`
- `0x18001072c`

## string_xrefs

- `0x18000f81e`: `{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_COMMON_PROPERTY_V2 )`
- `0x18000f8ac`: `{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RENAME_V2 )`
- `0x18000f8da`: `{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_DELETED_V2 )`
- `0x18000f908`: `{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_COMMON_PROPERTY_V2 )`
- `0x18000faac`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_COMMON_PROPERTY_V2 )`
- `0x18000fbee`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DELETED_V2 )`
- `0x18000fc1c`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DLL_UPGRADED_V2 )`
- `0x18000fc7e`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DELETED_V2 )`
- `0x18000fcac`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_COMMON_PROPERTY_V2 )`
- `0x18000fd2a`: `{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DLL_UPGRADED_V2 )`
- `0x18000fd58`: `{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_DELETED_V2 )`
- `0x18000fd86`: `{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_COMMON_PROPERTY_V2 )`
- `0x18000fe32`: `{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_DELETED_V2 )`
- `0x18000fe60`: `{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_COMMON_PROPERTY_V2 )`
- `0x18000ff40`: `{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_DELETED_V2 )`
- `0x18000ff6e`: `{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_COMMON_PROPERTY_V2 )`
- `0x180010076`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_ATTRIBUTES_V2 )`
- `0x1800100a4`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_NAME_V2 )`
- `0x1800100ce`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_SUBTREE_V2 )`
- `0x1800100f8`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_VALUE_V2 )`
- `0x180010122`: `{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_HANDLE_CLOSE_V2 )`

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
        "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RECONNECT_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_STATE_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 1 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_GROUP_ADDED_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 1 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_HANDLE_CLOSE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 1 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_NETWORK_ADDED_V2 )",
                (__int64)v6);
              std::wstring::assign(v6);
            }
            if ( *(_DWORD *)a2 == 1 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_NODE_ADDED_V2 )",
                  (__int64)v6);
                std::wstring::assign(v6);
              }
              if ( *(_DWORD *)a2 == 1 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RESOURCE_TYPE_ADDED_V2 )",
                    (__int64)v6);
                  std::wstring::assign(v6);
                }
                if ( *(_DWORD *)a2 == 1 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_COMMON_PROPERTY_V2 )",
                      (__int64)v6);
                    std::wstring::assign(v6);
                  }
                  if ( *(_DWORD *)a2 == 1 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_PRIVATE_PROPERTY_V2 )",
                        (__int64)v6);
                      std::wstring::assign(v6);
                    }
                    if ( *(_DWORD *)a2 == 1 )
                    {
                      if ( (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                      {
                        cxl::TextWriter::Write<char,std::wstring,>(
                          a1,
                          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_LOST_NOTIFICATIONS_V2 )",
                          (__int64)v6);
                        std::wstring::assign(v6);
                      }
                      if ( *(_DWORD *)a2 == 1 && (*(_DWORD *)(a2 + 8) & 0x400LL) != 0 )
                      {
                        cxl::TextWriter::Write<char,std::wstring,>(
                          a1,
                          "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER_CHANGE_CLUSTER_RENAME_V2 )",
                          (__int64)v6);
                        std::wstring::assign(v6);
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
      cxl::TextWriter::Write<char,std::wstring,>(
        a1,
        "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_DELETED_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 2 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_COMMON_PROPERTY_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 2 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_PRIVATE_PROPERTY_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 2 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_STATE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 2 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_OWNER_NODE_V2 )",
                (__int64)v6);
              std::wstring::assign(v6);
            }
            if ( *(_DWORD *)a2 == 2 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_PREFERRED_OWNERS_V2 )",
                  (__int64)v6);
                std::wstring::assign(v6);
              }
              if ( *(_DWORD *)a2 == 2 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_ADDED_V2 )",
                    (__int64)v6);
                  std::wstring::assign(v6);
                }
                if ( *(_DWORD *)a2 == 2 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_GAINED_V2 )",
                      (__int64)v6);
                    std::wstring::assign(v6);
                  }
                  if ( *(_DWORD *)a2 == 2 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_RESOURCE_LOST_V2 )",
                        (__int64)v6);
                      std::wstring::assign(v6);
                    }
                    if ( *(_DWORD *)a2 == 2 && (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_CHANGE_GROUP_HANDLE_CLOSE_V2 )",
                        (__int64)v6);
                      std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_COMMON_PROPERTY_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 3 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_PRIVATE_PROPERTY_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 3 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_STATE_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 3 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_OWNER_GROUP_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 3 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DEPENDENCIES_V2 )",
                (__int64)v6);
              std::wstring::assign(v6);
            }
            if ( *(_DWORD *)a2 == 3 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DEPENDENTS_V2 )",
                  (__int64)v6);
                std::wstring::assign(v6);
              }
              if ( *(_DWORD *)a2 == 3 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_POSSIBLE_OWNERS_V2 )",
                    (__int64)v6);
                  std::wstring::assign(v6);
                }
                if ( *(_DWORD *)a2 == 3 )
                {
                  if ( *(char *)(a2 + 8) < 0 )
                  {
                    cxl::TextWriter::Write<char,std::wstring,>(
                      a1,
                      "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DELETED_V2 )",
                      (__int64)v6);
                    std::wstring::assign(v6);
                  }
                  if ( *(_DWORD *)a2 == 3 )
                  {
                    if ( (*(_DWORD *)(a2 + 8) & 0x100LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_DLL_UPGRADED_V2 )",
                        (__int64)v6);
                      std::wstring::assign(v6);
                    }
                    if ( *(_DWORD *)a2 == 3 && (*(_DWORD *)(a2 + 8) & 0x200LL) != 0 )
                    {
                      cxl::TextWriter::Write<char,std::wstring,>(
                        a1,
                        "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTER_CHANGE_RESOURCE_HANDLE_CLOSE_V2 )",
                        (__int64)v6);
                      std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DELETED_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 4 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_COMMON_PROPERTY_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 4 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_PRIVATE_PROPERTY_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 4 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_POSSIBLE_OWNERS_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 4 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_RESOURCE_TYPE( CLUSTER_CHANGE_RESOURCE_TYPE_DLL_UPGRADED_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_DELETED_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 5 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_COMMON_PROPERTY_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 5 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_PRIVATE_PROPERTY_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 5 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_STATE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 5 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK_INTERFACE( CLUSTER_CHANGE_NETINTERFACE_HANDLE_CLOSE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_DELETED_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 6 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_COMMON_PROPERTY_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 6 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_PRIVATE_PROPERTY_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 6 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_STATE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 6 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NETWORK( CLUSTER_CHANGE_NETWORK_HANDLE_CLOSE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_NETINTERFACE_ADDED_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 7 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_DELETED_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 7 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_COMMON_PROPERTY_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 7 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_PRIVATE_PROPERTY_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 7 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
            {
              cxl::TextWriter::Write<char,std::wstring,>(
                a1,
                "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_STATE_V2 )",
                (__int64)v6);
              std::wstring::assign(v6);
            }
            if ( *(_DWORD *)a2 == 7 )
            {
              if ( (*(_BYTE *)(a2 + 8) & 0x20) != 0 )
              {
                cxl::TextWriter::Write<char,std::wstring,>(
                  a1,
                  "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_GROUP_GAINED_V2 )",
                  (__int64)v6);
                std::wstring::assign(v6);
              }
              if ( *(_DWORD *)a2 == 7 )
              {
                if ( (*(_BYTE *)(a2 + 8) & 0x40) != 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_GROUP_LOST_V2 )",
                    (__int64)v6);
                  std::wstring::assign(v6);
                }
                if ( *(_DWORD *)a2 == 7 && *(char *)(a2 + 8) < 0 )
                {
                  cxl::TextWriter::Write<char,std::wstring,>(
                    a1,
                    "{0}CLUSTER_OBJECT_TYPE_NODE( CLUSTER_CHANGE_NODE_HANDLE_CLOSE_V2 )",
                    (__int64)v6);
                  std::wstring::assign(v6);
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
        "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_ATTRIBUTES_V2 )",
        (__int64)v6);
      std::wstring::assign(v6);
    }
    if ( *(_DWORD *)a2 == 8 )
    {
      if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
      {
        cxl::TextWriter::Write<char,std::wstring,>(
          a1,
          "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_NAME_V2 )",
          (__int64)v6);
        std::wstring::assign(v6);
      }
      if ( *(_DWORD *)a2 == 8 )
      {
        if ( (*(_BYTE *)(a2 + 8) & 4) != 0 )
        {
          cxl::TextWriter::Write<char,std::wstring,>(
            a1,
            "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_SUBTREE_V2 )",
            (__int64)v6);
          std::wstring::assign(v6);
        }
        if ( *(_DWORD *)a2 == 8 )
        {
          if ( (*(_BYTE *)(a2 + 8) & 8) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_VALUE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
          if ( *(_DWORD *)a2 == 8 && (*(_BYTE *)(a2 + 8) & 0x10) != 0 )
          {
            cxl::TextWriter::Write<char,std::wstring,>(
              a1,
              "{0}CLUSTER_OBJECT_TYPE_REGISTRY( CLUSTER_CHANGE_REGISTRY_HANDLE_CLOSE_V2 )",
              (__int64)v6);
            std::wstring::assign(v6);
          }
        }
      }
    }
  }
  if ( *(_DWORD *)a2 == 9 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
  {
    cxl::TextWriter::Write<char,std::wstring,>(
      a1,
      "{0}CLUSTER_OBJECT_TYPE_QUORUM( CLUSTER_CHANGE_QUORUM_STATE_V2 )",
      (__int64)v6);
    std::wstring::assign(v6);
  }
  return std::wstring::_Tidy_deallocate(v6);
}

```

## disassembly

```asm
0x18000f66c  mov     [rsp-28h+arg_8], rbx
0x18000f671  mov     [rsp-28h+arg_10], rsi
0x18000f676  push    rbp
0x18000f677  push    rdi
0x18000f678  push    r12
0x18000f67a  push    r14
0x18000f67c  push    r15
0x18000f67e  mov     rbp, rsp
0x18000f681  sub     rsp, 50h
0x18000f685  mov     rax, cs:__security_cookie
0x18000f68c  xor     rax, rsp
0x18000f68f  mov     [rbp+var_10], rax
0x18000f693  mov     rbx, rdx
0x18000f696  mov     rdi, rcx
0x18000f699  cmp     dword ptr [rdx], 0
0x18000f69c  jz      loc_180010173
0x18000f6a2  cmp     qword ptr [rdx+8], 0
0x18000f6a7  jz      loc_180010173
0x18000f6ad  lea     rcx, [rbp+var_30]
0x18000f6b1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f6b6  nop
0x18000f6b7  lea     rsi, asc_180126D00; " + "
0x18000f6be  mov     r12d, 2
0x18000f6c4  lea     r15d, [r12-1]
0x18000f6c9  cmp     [rdx], r15d
0x18000f6cc  jnz     loc_18000F8C7
0x18000f6d2  test    [rdx+8], r15b
0x18000f6d6  jz      short loc_18000F6F7
0x18000f6d8  lea     r8, [rbp+var_30]
0x18000f6dc  lea     rdx, a0ClusterObject_36; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f6e3  mov     rcx, rdi
0x18000f6e6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f6eb  mov     rdx, rsi
0x18000f6ee  lea     rcx, [rbp+var_30]
0x18000f6f2  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f6f7  cmp     [rbx], r15d
0x18000f6fa  jnz     loc_18000F8C7
0x18000f700  test    [rbx+8], r12b
0x18000f704  jz      short loc_18000F725
0x18000f706  lea     r8, [rbp+var_30]
0x18000f70a  lea     rdx, a0ClusterObject_46; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f711  mov     rcx, rdi
0x18000f714  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f719  mov     rdx, rsi
0x18000f71c  lea     rcx, [rbp+var_30]
0x18000f720  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f725  cmp     [rbx], r15d
0x18000f728  jnz     loc_18000F8C7
0x18000f72e  test    byte ptr [rbx+8], 4
0x18000f732  jz      short loc_18000F753
0x18000f734  lea     r8, [rbp+var_30]
0x18000f738  lea     rdx, a0ClusterObject_56; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f73f  mov     rcx, rdi
0x18000f742  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f747  mov     rdx, rsi
0x18000f74a  lea     rcx, [rbp+var_30]
0x18000f74e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f753  cmp     [rbx], r15d
0x18000f756  jnz     loc_18000F8C7
0x18000f75c  test    byte ptr [rbx+8], 8
0x18000f760  jz      short loc_18000F781
0x18000f762  lea     r8, [rbp+var_30]
0x18000f766  lea     rdx, a0ClusterObject_44; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f76d  mov     rcx, rdi
0x18000f770  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f775  mov     rdx, rsi
0x18000f778  lea     rcx, [rbp+var_30]
0x18000f77c  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f781  cmp     [rbx], r15d
0x18000f784  jnz     loc_18000F8C7
0x18000f78a  test    byte ptr [rbx+8], 10h
0x18000f78e  jz      short loc_18000F7AF
0x18000f790  lea     r8, [rbp+var_30]
0x18000f794  lea     rdx, a0ClusterObject_45; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f79b  mov     rcx, rdi
0x18000f79e  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f7a3  mov     rdx, rsi
0x18000f7a6  lea     rcx, [rbp+var_30]
0x18000f7aa  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f7af  cmp     [rbx], r15d
0x18000f7b2  jnz     loc_18000F8C7
0x18000f7b8  test    byte ptr [rbx+8], 20h
0x18000f7bc  jz      short loc_18000F7DD
0x18000f7be  lea     r8, [rbp+var_30]
0x18000f7c2  lea     rdx, a0ClusterObject_26; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f7c9  mov     rcx, rdi
0x18000f7cc  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f7d1  mov     rdx, rsi
0x18000f7d4  lea     rcx, [rbp+var_30]
0x18000f7d8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f7dd  cmp     [rbx], r15d
0x18000f7e0  jnz     loc_18000F8C7
0x18000f7e6  test    byte ptr [rbx+8], 40h
0x18000f7ea  jz      short loc_18000F80B
0x18000f7ec  lea     r8, [rbp+var_30]
0x18000f7f0  lea     rdx, a0ClusterObject_16; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f7f7  mov     rcx, rdi
0x18000f7fa  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f7ff  mov     rdx, rsi
0x18000f802  lea     rcx, [rbp+var_30]
0x18000f806  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f80b  cmp     [rbx], r15d
0x18000f80e  jnz     loc_18000F8C7
0x18000f814  test    byte ptr [rbx+8], 80h
0x18000f818  jz      short loc_18000F839
0x18000f81a  lea     r8, [rbp+var_30]
0x18000f81e  lea     rdx, a0ClusterObject_5; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f825  mov     rcx, rdi
0x18000f828  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f82d  mov     rdx, rsi
0x18000f830  lea     rcx, [rbp+var_30]
0x18000f834  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f839  cmp     [rbx], r15d
0x18000f83c  jnz     loc_18000F8C7
0x18000f842  mov     eax, [rbx+8]
0x18000f845  bt      rax, 8
0x18000f84a  jnb     short loc_18000F86B
0x18000f84c  lea     r8, [rbp+var_30]
0x18000f850  lea     rdx, a0ClusterObject_42; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f857  mov     rcx, rdi
0x18000f85a  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f85f  mov     rdx, rsi
0x18000f862  lea     rcx, [rbp+var_30]
0x18000f866  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f86b  cmp     [rbx], r15d
0x18000f86e  jnz     short loc_18000F8C7
0x18000f870  mov     eax, [rbx+8]
0x18000f873  bt      rax, 9
0x18000f878  jnb     short loc_18000F899
0x18000f87a  lea     r8, [rbp+var_30]
0x18000f87e  lea     rdx, a0ClusterObject_53; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f885  mov     rcx, rdi
0x18000f888  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f88d  mov     rdx, rsi
0x18000f890  lea     rcx, [rbp+var_30]
0x18000f894  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f899  cmp     [rbx], r15d
0x18000f89c  jnz     short loc_18000F8C7
0x18000f89e  mov     eax, [rbx+8]
0x18000f8a1  bt      rax, 0Ah
0x18000f8a6  jnb     short loc_18000F8C7
0x18000f8a8  lea     r8, [rbp+var_30]
0x18000f8ac  lea     rdx, a0ClusterObject_8; "{0}CLUSTER_OBJECT_TYPE_CLUSTER( CLUSTER"...
0x18000f8b3  mov     rcx, rdi
0x18000f8b6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f8bb  mov     rdx, rsi
0x18000f8be  lea     rcx, [rbp+var_30]
0x18000f8c2  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f8c7  cmp     [rbx], r12d
0x18000f8ca  jnz     loc_18000FA93
0x18000f8d0  test    [rbx+8], r15b
0x18000f8d4  jz      short loc_18000F8F5
0x18000f8d6  lea     r8, [rbp+var_30]
0x18000f8da  lea     rdx, a0ClusterObject_57; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f8e1  mov     rcx, rdi
0x18000f8e4  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f8e9  mov     rdx, rsi
0x18000f8ec  lea     rcx, [rbp+var_30]
0x18000f8f0  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f8f5  cmp     [rbx], r12d
0x18000f8f8  jnz     loc_18000FA93
0x18000f8fe  test    [rbx+8], r12b
0x18000f902  jz      short loc_18000F923
0x18000f904  lea     r8, [rbp+var_30]
0x18000f908  lea     rdx, a0ClusterObject_19; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f90f  mov     rcx, rdi
0x18000f912  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f917  mov     rdx, rsi
0x18000f91a  lea     rcx, [rbp+var_30]
0x18000f91e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f923  cmp     [rbx], r12d
0x18000f926  jnz     loc_18000FA93
0x18000f92c  test    byte ptr [rbx+8], 4
0x18000f930  jz      short loc_18000F951
0x18000f932  lea     r8, [rbp+var_30]
0x18000f936  lea     rdx, a0ClusterObject_27; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f93d  mov     rcx, rdi
0x18000f940  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f945  mov     rdx, rsi
0x18000f948  lea     rcx, [rbp+var_30]
0x18000f94c  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f951  cmp     [rbx], r12d
0x18000f954  jnz     loc_18000FA93
0x18000f95a  test    byte ptr [rbx+8], 8
0x18000f95e  jz      short loc_18000F97F
0x18000f960  lea     r8, [rbp+var_30]
0x18000f964  lea     rdx, a0ClusterObject_51; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f96b  mov     rcx, rdi
0x18000f96e  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f973  mov     rdx, rsi
0x18000f976  lea     rcx, [rbp+var_30]
0x18000f97a  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f97f  cmp     [rbx], r12d
0x18000f982  jnz     loc_18000FA93
0x18000f988  test    byte ptr [rbx+8], 10h
0x18000f98c  jz      short loc_18000F9AD
0x18000f98e  lea     r8, [rbp+var_30]
0x18000f992  lea     rdx, a0ClusterObject_34; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f999  mov     rcx, rdi
0x18000f99c  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f9a1  mov     rdx, rsi
0x18000f9a4  lea     rcx, [rbp+var_30]
0x18000f9a8  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f9ad  cmp     [rbx], r12d
0x18000f9b0  jnz     loc_18000FA93
0x18000f9b6  test    byte ptr [rbx+8], 20h
0x18000f9ba  jz      short loc_18000F9DB
0x18000f9bc  lea     r8, [rbp+var_30]
0x18000f9c0  lea     rdx, a0ClusterObject_39; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f9c7  mov     rcx, rdi
0x18000f9ca  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f9cf  mov     rdx, rsi
0x18000f9d2  lea     rcx, [rbp+var_30]
0x18000f9d6  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000f9db  cmp     [rbx], r12d
0x18000f9de  jnz     loc_18000FA93
0x18000f9e4  test    byte ptr [rbx+8], 40h
0x18000f9e8  jz      short loc_18000FA09
0x18000f9ea  lea     r8, [rbp+var_30]
0x18000f9ee  lea     rdx, a0ClusterObject_2; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000f9f5  mov     rcx, rdi
0x18000f9f8  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000f9fd  mov     rdx, rsi
0x18000fa00  lea     rcx, [rbp+var_30]
0x18000fa04  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fa09  cmp     [rbx], r12d
0x18000fa0c  jnz     loc_18000FA93
0x18000fa12  test    byte ptr [rbx+8], 80h
0x18000fa16  jz      short loc_18000FA37
0x18000fa18  lea     r8, [rbp+var_30]
0x18000fa1c  lea     rdx, a0ClusterObject_13; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fa23  mov     rcx, rdi
0x18000fa26  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fa2b  mov     rdx, rsi
0x18000fa2e  lea     rcx, [rbp+var_30]
0x18000fa32  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fa37  cmp     [rbx], r12d
0x18000fa3a  jnz     short loc_18000FA93
0x18000fa3c  mov     eax, [rbx+8]
0x18000fa3f  bt      rax, 8
0x18000fa44  jnb     short loc_18000FA65
0x18000fa46  lea     r8, [rbp+var_30]
0x18000fa4a  lea     rdx, a0ClusterObject_20; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fa51  mov     rcx, rdi
0x18000fa54  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fa59  mov     rdx, rsi
0x18000fa5c  lea     rcx, [rbp+var_30]
0x18000fa60  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fa65  cmp     [rbx], r12d
0x18000fa68  jnz     short loc_18000FA93
0x18000fa6a  mov     eax, [rbx+8]
0x18000fa6d  bt      rax, 9
0x18000fa72  jnb     short loc_18000FA93
0x18000fa74  lea     r8, [rbp+var_30]
0x18000fa78  lea     rdx, a0ClusterObject_21; "{0}CLUSTER_OBJECT_TYPE_GROUP( CLUSTER_C"...
0x18000fa7f  mov     rcx, rdi
0x18000fa82  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fa87  mov     rdx, rsi
0x18000fa8a  lea     rcx, [rbp+var_30]
0x18000fa8e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fa93  mov     r14d, 3
0x18000fa99  cmp     [rbx], r14d
0x18000fa9c  jnz     loc_18000FC65
0x18000faa2  test    [rbx+8], r15b
0x18000faa6  jz      short loc_18000FAC7
0x18000faa8  lea     r8, [rbp+var_30]
0x18000faac  lea     rdx, a0ClusterObject_32; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000fab3  mov     rcx, rdi
0x18000fab6  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fabb  mov     rdx, rsi
0x18000fabe  lea     rcx, [rbp+var_30]
0x18000fac2  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fac7  cmp     [rbx], r14d
0x18000faca  jnz     loc_18000FC65
0x18000fad0  test    [rbx+8], r12b
0x18000fad4  jz      short loc_18000FAF5
0x18000fad6  lea     r8, [rbp+var_30]
0x18000fada  lea     rdx, a0ClusterObject_25; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000fae1  mov     rcx, rdi
0x18000fae4  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fae9  mov     rdx, rsi
0x18000faec  lea     rcx, [rbp+var_30]
0x18000faf0  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000faf5  cmp     [rbx], r14d
0x18000faf8  jnz     loc_18000FC65
0x18000fafe  test    byte ptr [rbx+8], 4
0x18000fb02  jz      short loc_18000FB23
0x18000fb04  lea     r8, [rbp+var_30]
0x18000fb08  lea     rdx, a0ClusterObject_38; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
0x18000fb0f  mov     rcx, rdi
0x18000fb12  call    ??$Write@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<char,std::wstring,>(char const *,std::wstring const &)
0x18000fb17  mov     rdx, rsi
0x18000fb1a  lea     rcx, [rbp+var_30]
0x18000fb1e  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18000fb23  cmp     [rbx], r14d
0x18000fb26  jnz     loc_18000FC65
0x18000fb2c  test    byte ptr [rbx+8], 8
0x18000fb30  jz      short loc_18000FB51
0x18000fb32  lea     r8, [rbp+var_30]
0x18000fb36  lea     rdx, a0ClusterObject_15; "{0}CLUSTER_OBJECT_TYPE_RESOURCE( CLUSTE"...
  ... truncated ...
```
