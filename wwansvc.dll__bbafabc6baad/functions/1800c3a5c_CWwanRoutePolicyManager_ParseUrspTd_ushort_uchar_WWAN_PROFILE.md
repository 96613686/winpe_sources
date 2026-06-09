# CWwanRoutePolicyManager::_ParseUrspTd(ushort,uchar *,WWAN_PROFILE *)

- ea: `0x1800c3a5c`
- end: `0x1800c4237`
- name: `?_ParseUrspTd@CWwanRoutePolicyManager@@SAKGPEAEPEAUWWAN_PROFILE@@@Z`
- size: `2011`
- prototype: `unsigned int __fastcall(unsigned __int16, unsigned __int8 *, struct WWAN_PROFILE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180053328`
- `0x1800c30c8`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001a27c`
- `0x1800c3a5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c402c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c415b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c402c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c415b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3be2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3d0d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3f93`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3be2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3d0d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800c3f93`

## string_xrefs

- `0x1800c3a81`: `Traffic Descriptor header exceeds remaining buffer (%u)`
- `0x1800c420d`: `Traffic Descriptor ID field is greater than remaining blob size (%u)`
- `0x1800c3ac2`: `Traffic Descriptor length (%u) is greater than remaining blob size (%u)`
- `0x1800c4062`: `osIdOsAppId TD component header length exceeds remaining buffer (%u)`
- `0x1800c40ad`: `Traffic Descriptor has more than 1 match-all component`
- `0x1800c3c28`: `Multiple OsIDAppID/OsAppID-typed components. Upsupported and ignored current one`
- `0x1800c3d45`: `Multiple OsIDAppID/OsAppID-typed components. Upsupported and ignored current one`
- `0x1800c404f`: `osIdOsAppId TD component size %u exceeds remaining buffer %u`
- `0x1800c3baf`: `Non-Windows OSId in OsIDAppID-typed component, un-supported and the component ignored`
- `0x1800c3c1f`: `OsIDAppID TD Component ID set, but AppID length is zero. Ignoring`
- `0x1800c3c01`: `  OsIDAppID TD Component: [%s]`
- `0x1800c4109`: `OsAppID TD component size %u exceeds remaining buffer %u`
- `0x1800c4115`: `OsAppID TD component header length exceeds remaining buffer (%u)`
- `0x1800c3d3c`: `OsAppID TD Component ID set, but AppID length is zero. Ignoring`
- `0x1800c3d23`: `  OsAppID TD Component: [%s]`
- `0x1800c4089`: `TrafficDescriptorComponentType::ipv6Addr not supported. Ignoring current TD`
- `0x1800c4092`: `TrafficDescriptorComponentType::ipv4Addr not supported. Ignoring current TD`
- `0x1800c40c3`: `TrafficDescriptorComponentType::portNumber not supported. Ignoring current TD`
- `0x1800c4080`: `TrafficDescriptorComponentType::protocolId not supported. Ignoring current TD`
- `0x1800c40f7`: `TrafficDescriptorComponentType::ipSecParam not supported. Ignoring current TD`
- `0x1800c4100`: `TrafficDescriptorComponentType::portRange not supported. Ignoring current TD`
- `0x1800c40e5`: `TrafficDescriptorComponentType::flowLabel not supported. Ignoring current TD`
- `0x1800c40ee`: `TrafficDescriptorComponentType::serviceClass not supported. Ignoring current TD`
- `0x1800c3e22`: `Multiple DNN-typed components. Upsupported and ignored current one`
- `0x1800c4201`: `Non-IP descriptors are not supported. Ignoring current TD`
- `0x1800c41ec`: `DNN Traffic Descriptor size %u exceeds remaining buffer %u`
- `0x1800c41f8`: `DNN Traffic Descriptor header length exceeds remaining buffer (%u)`
- `0x1800c41dd`: `size of the value of a DNN Traffic Descriptor component is 0`
- `0x1800c4187`: `APN in TD DNN component is too long in buffer of %d chars`
- `0x1800c414f`: `Capabilities Traffic Descriptor header length exceeds remaining buffer (%u)`
- `0x1800c3fc9`: `  DNN TD Component: [%s]`
- `0x1800c3e0a`: `Connection Capabilities Component ID set, but count is zero. Ignoring`
- `0x1800c3dfb`: `  ConnCap TD Component: [0x%x]`
- `0x1800c4121`: `Unrecognized Traffic Descriptor Type %d`
- `0x1800c412d`: `TrafficDescriptorComponentType::fqdn not supported. Ignoring current TD`
- `0x1800c41d1`: `Too many Traffic Descriptor components for given length`

## pseudocode

```c
__int64 __fastcall CWwanRoutePolicyManager::_ParseUrspTd(
        unsigned __int16 a1,
        unsigned __int8 *a2,
        struct WWAN_PROFILE *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // r9
  const unsigned __int16 *v7; // r8
  unsigned __int16 v9; // cx
  __int64 v10; // r9
  const unsigned __int16 *v11; // r8
  unsigned __int8 *v12; // r14
  __int16 v13; // bx
  int v14; // r15d
  unsigned int v15; // eax
  unsigned __int16 v16; // bx
  unsigned __int16 v17; // bp
  int v18; // r9d
  __int64 v19; // rax
  int v20; // r9d
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // r15d
  int v24; // ecx
  unsigned __int8 *v25; // r13
  unsigned __int16 v26; // bp
  int v27; // edx
  unsigned __int8 v28; // r8
  _BYTE *v29; // r9
  __int64 v30; // r10
  char v31; // al
  unsigned __int16 v32; // ax
  WCHAR *v33; // rcx
  int v34; // eax
  const CHAR *v35; // r11
  unsigned __int16 v36; // cx
  __int64 v37; // rcx
  __int64 LastError; // rbx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-48h]
  __int64 cchWideChar; // [rsp+28h] [rbp-40h]
  int v41; // [rsp+70h] [rbp+8h]
  unsigned __int64 v42; // [rsp+88h] [rbp+20h] BYREF

  v3 = a1;
  if ( a1 < 3u )
  {
    v6 = a1;
    v7 = L"Traffic Descriptor header exceeds remaining buffer (%u)";
LABEL_3:
    WwanLog::Error("CWwanRoutePolicyManager::_ParseUrspTd", 0, v7, v6);
    return 87;
  }
  v9 = (*(_WORD *)a2 << 8) | a2[1];
  v10 = v9;
  *(_WORD *)a2 = v9;
  if ( v3 < (unsigned int)v9 + 2 )
  {
    v11 = L"Traffic Descriptor length (%u) is greater than remaining blob size (%u)";
    goto LABEL_7;
  }
  v12 = a2 + 2;
  v13 = v3 - 2;
  v14 = 0;
  v41 = 0;
  while ( 1 )
  {
    if ( !v13 || (unsigned __int16)v14 >= *(_WORD *)a2 )
      return 0;
    v15 = *v12;
    v16 = v13 - 1;
    if ( v16 )
      ++v12;
    v17 = 0;
    if ( (unsigned __int8)v15 > 0x81u )
    {
      v10 = v15;
      switch ( v15 )
      {
        case 0x83u:
        case 0x84u:
        case 0x85u:
        case 0x86u:
        case 0x87u:
LABEL_134:
          WwanLog::Info(
            "CWwanRoutePolicyManager::_ParseUrspTd",
            0,
            L"Non-IP descriptors are not supported. Ignoring current TD",
            v10);
          return 50;
        case 0x88u:
          if ( (*((_DWORD *)a3 + 1314) & 0x1000) != 0 )
          {
            WwanLog::Warning(
              "CWwanRoutePolicyManager::_ParseUrspTd",
              0,
              L"Multiple DNN-typed components. Upsupported and ignored current one",
              v15);
            goto LABEL_96;
          }
          if ( v16 >= 3u )
          {
            v23 = *v12;
            if ( v16 >= v23 + 1 )
            {
              if ( (_BYTE)v23 )
              {
                v24 = 1;
                v25 = v12 + 1;
                v26 = 1;
                while ( 1 )
                {
                  if ( !v23 )
                  {
                    WwanLog::Info(
                      "CWwanRoutePolicyManager::_ParseUrspTd",
                      0,
                      L"  DNN TD Component: [%s]",
                      (char *)a3 + 5540);
                    *((_DWORD *)a3 + 1314) |= 0x1000u;
                    v14 = v41;
                    goto LABEL_94;
                  }
                  if ( !*v25 )
                    break;
                  v27 = *v25;
                  if ( v23 < v27 + 1 )
                  {
                    LODWORD(cchWideChar) = *v25;
                    LODWORD(lpWideCharStr) = v26;
                    WwanLog::Error(
                      "CWwanRoutePolicyManager::_ParseUrspTd",
                      0,
                      L"remaining bytes %d is not enough for the label#%d (length %d)",
                      v23,
                      lpWideCharStr,
                      cchWideChar);
                    return 87;
                  }
                  if ( *v25 >= 0x64u )
                  {
LABEL_85:
                    WwanLog::Error(
                      "CWwanRoutePolicyManager::_ParseUrspTd",
                      0,
                      L"APN label#%d contains invalid ascii char",
                      v26);
                    return 87;
                  }
                  v28 = 0;
                  v29 = v25 + 1;
                  while ( v28 < *v25 )
                  {
                    LOBYTE(v24) = *v29;
                    if ( (unsigned __int8)(*v29 - 45) <= 0x2Du
                      && (v30 = 0x3FFFFFF01FF9LL, _bittest64(&v30, (unsigned int)(v24 - 45)))
                      || (unsigned __int8)(v24 - 97) <= 0x19u )
                    {
                      v24 = 1;
                      v31 = 1;
                    }
                    else
                    {
                      v31 = 0;
                      v24 = 1;
                    }
                    ++v28;
                    ++v29;
                    if ( !v31 )
                      goto LABEL_85;
                  }
                  v32 = v26;
                  v42 = 0;
                  ++v26;
                  v33 = (WCHAR *)((char *)a3 + 5540);
                  if ( v32 == 1 )
                  {
                    v34 = MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v25 + 1, v27, v33, 101);
                  }
                  else
                  {
                    if ( (int)StringCchLengthW(v33, 0x65u, &v42) < 0 )
                    {
                      WwanLog::Error(
                        "CWwanRoutePolicyManager::_ParseUrspTd",
                        0,
                        L"Label#%d StringCchLengthW failed",
                        v26);
                      return 87;
                    }
                    v36 = v42;
                    if ( v42 >= 0x62 )
                    {
                      WwanLog::Error(
                        "CWwanRoutePolicyManager::_ParseUrspTd",
                        0,
                        L"APN in TD DNN component is too long in buffer of %d chars",
                        101);
                      return 87;
                    }
                    *((_WORD *)a3 + v42 + 2770) = 46;
                    v34 = MultiByteToWideChar(0xFDE9u, 8u, v35, *v25, (LPWSTR)a3 + v36 + 2771, 100 - v36);
                  }
                  if ( !v34 )
                  {
                    LODWORD(lpWideCharStr) = GetLastError();
                    LODWORD(LastError) = (_DWORD)lpWideCharStr;
                    WwanLog::Error(
                      "CWwanRoutePolicyManager::_ParseUrspTd",
                      0,
                      L"Label#%d MultiByteToWideChar error %u",
                      v26,
                      lpWideCharStr);
                    return (unsigned int)LastError;
                  }
                  v37 = *v25;
                  v23 += -1 - v37;
                  v25 += v37 + 1;
                  v24 = 1;
                }
                WwanLog::Error("CWwanRoutePolicyManager::_ParseUrspTd", 0, L"the label#%d length is 0", v26);
              }
              else
              {
                WwanLog::Error(
                  "CWwanRoutePolicyManager::_ParseUrspTd",
                  0,
                  L"size of the value of a DNN Traffic Descriptor component is 0",
                  v15);
              }
              return 87;
            }
            v11 = L"DNN Traffic Descriptor size %u exceeds remaining buffer %u";
LABEL_7:
            WwanLog::Error("CWwanRoutePolicyManager::_ParseUrspTd", 0, v11);
            return 87;
          }
          v7 = L"DNN Traffic Descriptor header length exceeds remaining buffer (%u)";
LABEL_135:
          v6 = v16;
          goto LABEL_3;
        case 0x90u:
          if ( v16 < 2u )
          {
            v7 = L"Capabilities Traffic Descriptor header length exceeds remaining buffer (%u)";
            goto LABEL_135;
          }
          v21 = *v12;
          if ( v16 < (unsigned __int64)(v21 + 1) )
          {
            v11 = L"Capabilities length (%u) is greater than remaining blob size (%u)";
            goto LABEL_7;
          }
          if ( (_BYTE)v21 )
          {
            do
            {
              v10 = v12[(unsigned __int8)v17 + 1];
              switch ( v12[(unsigned __int8)v17 + 1] )
              {
                case 1u:
                  *((_DWORD *)a3 + 1384) |= 1u;
                  break;
                case 2u:
                  *((_DWORD *)a3 + 1384) |= 2u;
                  break;
                case 4u:
                  *((_DWORD *)a3 + 1384) |= 4u;
                  break;
                case 8u:
                  *((_DWORD *)a3 + 1384) |= 8u;
                  break;
                default:
                  WwanLog::Error(
                    "CWwanRoutePolicyManager::_ParseUrspTd",
                    0,
                    L"Unrecognized Connection Capabilitiy Type %d");
                  break;
              }
              LOBYTE(v17) = v17 + 1;
            }
            while ( (unsigned __int8)v17 < *v12 );
            v22 = *((_DWORD *)a3 + 1384);
            if ( v22 )
            {
              *((_DWORD *)a3 + 1314) |= 0x10000u;
              WwanLog::Info("CWwanRoutePolicyManager::_ParseUrspTd", 0, L"  ConnCap TD Component: [0x%x]", v22);
            }
          }
          else
          {
            WwanLog::Warning(
              "CWwanRoutePolicyManager::_ParseUrspTd",
              0,
              L"Connection Capabilities Component ID set, but count is zero. Ignoring");
          }
          break;
        case 0x91u:
          WwanLog::Info(
            "CWwanRoutePolicyManager::_ParseUrspTd",
            0,
            L"TrafficDescriptorComponentType::fqdn not supported. Ignoring current TD",
            145);
          return 50;
        case 0xA0u:
          if ( v16 < 2u )
          {
            v7 = L"OsAppID TD component header length exceeds remaining buffer (%u)";
            goto LABEL_135;
          }
          v20 = *v12;
          if ( v16 < (unsigned int)(v20 + 1) )
          {
            v11 = L"OsAppID TD component size %u exceeds remaining buffer %u";
            goto LABEL_7;
          }
          if ( (*((_DWORD *)a3 + 1314) & 0x8800) != 0 )
          {
            WwanLog::Warning(
              "CWwanRoutePolicyManager::_ParseUrspTd",
              0,
              L"Multiple OsIDAppID/OsAppID-typed components. Upsupported and ignored current one");
          }
          else if ( (_BYTE)v20 )
          {
            if ( !MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v12 + 1, v20, (LPWSTR)a3 + 2640, 128) )
            {
LABEL_98:
              LastError = GetLastError();
              WwanLog::Error("CWwanRoutePolicyManager::_ParseUrspTd", 0, L"MultiByteToWideChar error %u", LastError);
              return (unsigned int)LastError;
            }
            *((_DWORD *)a3 + 1314) |= 0x800u;
            WwanLog::Info(
              "CWwanRoutePolicyManager::_ParseUrspTd",
              0,
              L"  OsAppID TD Component: [%s]",
              (char *)a3 + 5280);
          }
          else
          {
            WwanLog::Warning(
              "CWwanRoutePolicyManager::_ParseUrspTd",
              0,
              L"OsAppID TD Component ID set, but AppID length is zero. Ignoring");
          }
          break;
        default:
          goto LABEL_121;
      }
LABEL_94:
      v17 = *v12 + 1;
      goto LABEL_95;
    }
    if ( (_BYTE)v15 == 0x81 )
      goto LABEL_134;
    if ( (unsigned __int8)v15 > 0x50u )
      break;
    if ( (_BYTE)v15 == 80 )
    {
      WwanLog::Info(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"TrafficDescriptorComponentType::portNumber not supported. Ignoring current TD",
        v10);
      return 50;
    }
    v10 = v15;
    if ( v15 == 1 )
    {
      if ( *((_DWORD *)a3 + 1315) )
      {
        WwanLog::Error(
          "CWwanRoutePolicyManager::_ParseUrspTd",
          0,
          L"Traffic Descriptor has more than 1 match-all component",
          v15);
        return 87;
      }
      *((_DWORD *)a3 + 1315) = 1;
      goto LABEL_96;
    }
    if ( v15 != 8 )
    {
      switch ( v15 )
      {
        case 0x10u:
          WwanLog::Info(
            "CWwanRoutePolicyManager::_ParseUrspTd",
            0,
            L"TrafficDescriptorComponentType::ipv4Addr not supported. Ignoring current TD",
            16);
          break;
        case 0x21u:
          WwanLog::Info(
            "CWwanRoutePolicyManager::_ParseUrspTd",
            0,
            L"TrafficDescriptorComponentType::ipv6Addr not supported. Ignoring current TD",
            33);
          break;
        case 0x30u:
          WwanLog::Info(
            "CWwanRoutePolicyManager::_ParseUrspTd",
            0,
            L"TrafficDescriptorComponentType::protocolId not supported. Ignoring current TD",
            48);
          break;
        default:
          goto LABEL_121;
      }
      return 50;
    }
    if ( v16 < 0x11u )
    {
      v7 = L"osIdOsAppId TD component header length exceeds remaining buffer (%u)";
      goto LABEL_135;
    }
    v18 = v12[16];
    if ( v16 < (unsigned int)(v18 + 17) )
    {
      v11 = L"osIdOsAppId TD component size %u exceeds remaining buffer %u";
      goto LABEL_7;
    }
    if ( (*((_DWORD *)a3 + 1314) & 0x8800) != 0 )
    {
      WwanLog::Warning(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"Multiple OsIDAppID/OsAppID-typed components. Upsupported and ignored current one");
    }
    else
    {
      v19 = *(_QWORD *)v12 - *(_QWORD *)&WWAN_5G_URSP_WINDOWS_OSID_GUID.Data1;
      if ( *(_QWORD *)v12 == *(_QWORD *)&WWAN_5G_URSP_WINDOWS_OSID_GUID.Data1 )
        v19 = *((_QWORD *)v12 + 1) - *(_QWORD *)WWAN_5G_URSP_WINDOWS_OSID_GUID.Data4;
      if ( v19 )
      {
        WwanLog::Warning(
          "CWwanRoutePolicyManager::_ParseUrspTd",
          (const struct _GUID *)v12,
          L"Non-Windows OSId in OsIDAppID-typed component, un-supported and the component ignored");
      }
      else if ( (_BYTE)v18 )
      {
        if ( !MultiByteToWideChar(0xFDE9u, 8u, (LPCCH)v12 + 17, v18, (LPWSTR)a3 + 2640, 128) )
          goto LABEL_98;
        *((_DWORD *)a3 + 1314) |= 0x8800u;
        *((GUID *)a3 + 329) = WWAN_5G_URSP_WINDOWS_OSID_GUID;
        WwanLog::Info("CWwanRoutePolicyManager::_ParseUrspTd", 0, L"  OsIDAppID TD Component: [%s]", (char *)a3 + 5280);
      }
      else
      {
        WwanLog::Warning(
          "CWwanRoutePolicyManager::_ParseUrspTd",
          0,
          L"OsIDAppID TD Component ID set, but AppID length is zero. Ignoring");
      }
    }
    v17 = v12[16] + 17;
LABEL_95:
    if ( v16 < v17 )
    {
      WwanLog::Error(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"Too many Traffic Descriptor components for given length",
        v10);
      return 87;
    }
LABEL_96:
    LOWORD(v14) = v17 + 1 + v14;
    v41 = v14;
    v13 = v16 - v17;
    if ( v13 )
      v12 += v17;
  }
  v10 = v15;
  switch ( v15 )
  {
    case 0x51u:
      WwanLog::Info(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"TrafficDescriptorComponentType::portRange not supported. Ignoring current TD",
        81);
      return 50;
    case 0x60u:
      WwanLog::Info(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"TrafficDescriptorComponentType::ipSecParam not supported. Ignoring current TD",
        96);
      return 50;
    case 0x70u:
      WwanLog::Info(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"TrafficDescriptorComponentType::serviceClass not supported. Ignoring current TD",
        112);
      return 50;
    case 0x80u:
      WwanLog::Info(
        "CWwanRoutePolicyManager::_ParseUrspTd",
        0,
        L"TrafficDescriptorComponentType::flowLabel not supported. Ignoring current TD",
        128);
      return 50;
  }
LABEL_121:
  WwanLog::Error("CWwanRoutePolicyManager::_ParseUrspTd", 0, L"Unrecognized Traffic Descriptor Type %d", v10);
  return 87;
}

```

## disassembly

```asm
0x1800c3a5c  mov     [rsp+arg_8], rbx
0x1800c3a61  push    rbp
0x1800c3a62  push    rsi
0x1800c3a63  push    rdi
0x1800c3a64  push    r12
0x1800c3a66  push    r13
0x1800c3a68  push    r14
0x1800c3a6a  push    r15
0x1800c3a6c  sub     rsp, 30h
0x1800c3a70  movzx   ebx, cx
0x1800c3a73  mov     rsi, r8
0x1800c3a76  mov     r12, rdx
0x1800c3a79  cmp     ebx, 3
0x1800c3a7c  jnb     short loc_1800C3AA0
0x1800c3a7e  mov     r9d, ebx
0x1800c3a81  lea     r8, aTrafficDescrip_0; "Traffic Descriptor header exceeds remai"...
0x1800c3a88  lea     rcx, aCwwanroutepoli_0; "CWwanRoutePolicyManager::_ParseUrspTd"
0x1800c3a8f  xor     edx, edx; struct _GUID *
0x1800c3a91  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c3a96  mov     eax, 57h ; 'W'
0x1800c3a9b  jmp     loc_1800C4222
0x1800c3aa0  movzx   eax, word ptr [rdx]
0x1800c3aa3  movzx   ecx, byte ptr [rdx+1]
0x1800c3aa7  shl     ax, 8
0x1800c3aab  or      cx, ax
0x1800c3aae  movzx   r9d, cx
0x1800c3ab2  mov     [rdx], r9w
0x1800c3ab6  lea     eax, [r9+2]
0x1800c3aba  cmp     ebx, eax
0x1800c3abc  jnb     short loc_1800C3AD9
0x1800c3abe  mov     dword ptr [rsp+68h+lpWideCharStr], ebx
0x1800c3ac2  lea     r8, aTrafficDescrip_2; "Traffic Descriptor length (%u) is great"...
0x1800c3ac9  lea     rcx, aCwwanroutepoli_0; "CWwanRoutePolicyManager::_ParseUrspTd"
0x1800c3ad0  xor     edx, edx; struct _GUID *
0x1800c3ad2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c3ad7  jmp     short loc_1800C3A96
0x1800c3ad9  mov     r8d, 2
0x1800c3adf  lea     r14, [rdx+2]
0x1800c3ae3  sub     bx, r8w
0x1800c3ae7  lea     rdi, aCwwanroutepoli_0; "CWwanRoutePolicyManager::_ParseUrspTd"
0x1800c3aee  xor     r10d, r10d
0x1800c3af1  mov     r15d, r10d
0x1800c3af4  mov     [rsp+68h+arg_0], r10d
0x1800c3af9  lea     edx, [r8+0Fh]
0x1800c3afd  lea     r13d, [r8-1]
0x1800c3b01  test    bx, bx
0x1800c3b04  jz      loc_1800C4220
0x1800c3b0a  cmp     r15w, [r12]
0x1800c3b0f  jnb     loc_1800C4220
0x1800c3b15  cmp     bx, r13w
0x1800c3b19  jb      loc_1800C420D
0x1800c3b1f  movzx   eax, byte ptr [r14]
0x1800c3b23  mov     ecx, 0FFFFh
0x1800c3b28  add     bx, cx
0x1800c3b2b  jz      short loc_1800C3B30
0x1800c3b2d  add     r14, r13
0x1800c3b30  mov     ebp, r10d
0x1800c3b33  cmp     al, 81h
0x1800c3b35  ja      loc_1800C3C64
0x1800c3b3b  jz      loc_1800C4201
0x1800c3b41  cmp     al, 50h ; 'P'
0x1800c3b43  ja      loc_1800C40CC
0x1800c3b49  jz      loc_1800C40C3
0x1800c3b4f  mov     ecx, eax
0x1800c3b51  mov     r9d, eax
0x1800c3b54  sub     ecx, 1
0x1800c3b57  jz      loc_1800C3C4B
0x1800c3b5d  sub     ecx, 7
0x1800c3b60  jnz     loc_1800C406E
0x1800c3b66  cmp     bx, dx
0x1800c3b69  jb      loc_1800C4062
0x1800c3b6f  movzx   r9d, byte ptr [r14+10h]; cbMultiByte
0x1800c3b74  movzx   ecx, bx
0x1800c3b77  lea     eax, [r9+11h]
0x1800c3b7b  cmp     ecx, eax
0x1800c3b7d  jb      loc_1800C404F
0x1800c3b83  test    dword ptr [rsi+1488h], 8800h
0x1800c3b8d  jnz     loc_1800C3C28
0x1800c3b93  mov     rax, [r14]
0x1800c3b96  sub     rax, qword ptr cs:?WWAN_5G_URSP_WINDOWS_OSID_GUID@@3U_GUID@@B.Data1; _GUID const WWAN_5G_URSP_WINDOWS_OSID_GUID ...
0x1800c3b9d  jnz     short loc_1800C3BAA
0x1800c3b9f  mov     rax, [r14+8]
0x1800c3ba3  sub     rax, qword ptr cs:?WWAN_5G_URSP_WINDOWS_OSID_GUID@@3U_GUID@@B.Data4; _GUID const WWAN_5G_URSP_WINDOWS_OSID_GUID ...
0x1800c3baa  test    rax, rax
0x1800c3bad  jz      short loc_1800C3BBB
0x1800c3baf  lea     r8, aNonWindowsOsid; "Non-Windows OSId in OsIDAppID-typed com"...
0x1800c3bb6  mov     rdx, r14
0x1800c3bb9  jmp     short loc_1800C3C31
0x1800c3bbb  test    r9b, r9b
0x1800c3bbe  jz      short loc_1800C3C1F
0x1800c3bc0  lea     rbp, [rsi+14A0h]
0x1800c3bc7  mov     dword ptr [rsp+68h+cchWideChar], 80h; cchWideChar
0x1800c3bcf  lea     r8, [r14+11h]; lpMultiByteStr
0x1800c3bd3  mov     [rsp+68h+lpWideCharStr], rbp; lpWideCharStr
0x1800c3bd8  mov     edx, 8; dwFlags
0x1800c3bdd  mov     ecx, 0FDE9h; CodePage
0x1800c3be2  call    cs:__imp_MultiByteToWideChar
0x1800c3be8  test    eax, eax
0x1800c3bea  jz      loc_1800C402C
0x1800c3bf0  movups  xmm0, xmmword ptr cs:?WWAN_5G_URSP_WINDOWS_OSID_GUID@@3U_GUID@@B.Data1; _GUID const WWAN_5G_URSP_WINDOWS_OSID_GUID ...
0x1800c3bf7  or      dword ptr [rsi+1488h], 8800h
0x1800c3c01  lea     r8, aOsidappidTdCom; "  OsIDAppID TD Component: [%s]"
0x1800c3c08  mov     r9, rbp
0x1800c3c0b  xor     edx, edx; struct _GUID *
0x1800c3c0d  mov     rcx, rdi; char *
0x1800c3c10  movdqu  xmmword ptr [rsi+1490h], xmm0
0x1800c3c18  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c3c1d  jmp     short loc_1800C3C39
0x1800c3c1f  lea     r8, aOsidappidTdCom_0; "OsIDAppID TD Component ID set, but AppI"...
0x1800c3c26  jmp     short loc_1800C3C2F
0x1800c3c28  lea     r8, aMultipleOsidap; "Multiple OsIDAppID/OsAppID-typed compon"...
0x1800c3c2f  xor     edx, edx; struct _GUID *
0x1800c3c31  mov     rcx, rdi; char *
0x1800c3c34  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800c3c39  movzx   ebp, byte ptr [r14+10h]
0x1800c3c3e  mov     edx, 11h
0x1800c3c43  add     bp, dx
0x1800c3c46  jmp     loc_1800C3FF8
0x1800c3c4b  cmp     [rsi+148Ch], r10d
0x1800c3c52  jnz     loc_1800C40AD
0x1800c3c58  mov     [rsi+148Ch], r13d
0x1800c3c5f  jmp     loc_1800C400A
0x1800c3c64  mov     ecx, eax
0x1800c3c66  mov     r9d, eax
0x1800c3c69  sub     ecx, 83h
0x1800c3c6f  jz      loc_1800C4201
0x1800c3c75  sub     ecx, 1
0x1800c3c78  jz      loc_1800C4201
0x1800c3c7e  sub     ecx, 1
0x1800c3c81  jz      loc_1800C4201
0x1800c3c87  sub     ecx, 1
0x1800c3c8a  jz      loc_1800C4201
0x1800c3c90  sub     ecx, 1
0x1800c3c93  jz      loc_1800C4201
0x1800c3c99  sub     ecx, 1
0x1800c3c9c  jz      loc_1800C3E16
0x1800c3ca2  sub     ecx, 8
0x1800c3ca5  jz      loc_1800C3D5B
0x1800c3cab  sub     ecx, 1
0x1800c3cae  jz      loc_1800C412D
0x1800c3cb4  cmp     ecx, 0Fh
0x1800c3cb7  jnz     loc_1800C4121
0x1800c3cbd  cmp     bx, r8w
0x1800c3cc1  jb      loc_1800C4115
0x1800c3cc7  movzx   r9d, byte ptr [r14]; cbMultiByte
0x1800c3ccb  movzx   ecx, bx
0x1800c3cce  lea     eax, [r9+1]
0x1800c3cd2  cmp     ecx, eax
0x1800c3cd4  jb      loc_1800C4109
0x1800c3cda  test    dword ptr [rsi+1488h], 8800h
0x1800c3ce4  jnz     short loc_1800C3D45
0x1800c3ce6  test    r9b, r9b
0x1800c3ce9  jz      short loc_1800C3D3C
0x1800c3ceb  lea     rbp, [rsi+14A0h]
0x1800c3cf2  mov     dword ptr [rsp+68h+cchWideChar], 80h; cchWideChar
0x1800c3cfa  lea     r8, [r14+1]; lpMultiByteStr
0x1800c3cfe  mov     [rsp+68h+lpWideCharStr], rbp; lpWideCharStr
0x1800c3d03  mov     edx, 8; dwFlags
0x1800c3d08  mov     ecx, 0FDE9h; CodePage
0x1800c3d0d  call    cs:__imp_MultiByteToWideChar
0x1800c3d13  test    eax, eax
0x1800c3d15  jz      loc_1800C402C
0x1800c3d1b  bts     dword ptr [rsi+1488h], 0Bh
0x1800c3d23  lea     r8, aOsappidTdCompo_1; "  OsAppID TD Component: [%s]"
0x1800c3d2a  mov     r9, rbp
0x1800c3d2d  xor     edx, edx; struct _GUID *
0x1800c3d2f  mov     rcx, rdi; char *
0x1800c3d32  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800c3d37  jmp     loc_1800C3FEB
0x1800c3d3c  lea     r8, aOsappidTdCompo_2; "OsAppID TD Component ID set, but AppID "...
0x1800c3d43  jmp     short loc_1800C3D4C
0x1800c3d45  lea     r8, aMultipleOsidap; "Multiple OsIDAppID/OsAppID-typed compon"...
0x1800c3d4c  xor     edx, edx; struct _GUID *
0x1800c3d4e  mov     rcx, rdi; char *
0x1800c3d51  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800c3d56  jmp     loc_1800C3FEB
0x1800c3d5b  cmp     bx, r8w
0x1800c3d5f  jb      loc_1800C414F
0x1800c3d65  movzx   edx, byte ptr [r14]
0x1800c3d69  movzx   eax, bx
0x1800c3d6c  lea     rcx, [rdx+r13]
0x1800c3d70  cmp     rax, rcx
0x1800c3d73  jb      loc_1800C4139
0x1800c3d79  test    dl, dl
0x1800c3d7b  jz      loc_1800C3E0A
0x1800c3d81  movzx   eax, bpl
0x1800c3d85  movzx   r9d, byte ptr [rax+r14+1]
0x1800c3d8b  mov     ecx, r9d
0x1800c3d8e  sub     ecx, 1
0x1800c3d91  jz      short loc_1800C3DD6
0x1800c3d93  sub     ecx, 1
0x1800c3d96  jz      short loc_1800C3DCD
0x1800c3d98  sub     ecx, r8d
0x1800c3d9b  jz      short loc_1800C3DC4
0x1800c3d9d  cmp     ecx, 4
0x1800c3da0  jz      short loc_1800C3DBB
0x1800c3da2  lea     r8, aUnrecognizedCo; "Unrecognized Connection Capabilitiy Typ"...
0x1800c3da9  xor     edx, edx; struct _GUID *
0x1800c3dab  mov     rcx, rdi; char *
0x1800c3dae  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c3db3  mov     r8d, 2
0x1800c3db9  jmp     short loc_1800C3DDD
0x1800c3dbb  or      dword ptr [rsi+15A0h], 8
0x1800c3dc2  jmp     short loc_1800C3DDD
0x1800c3dc4  or      dword ptr [rsi+15A0h], 4
0x1800c3dcb  jmp     short loc_1800C3DDD
0x1800c3dcd  or      [rsi+15A0h], r8d
0x1800c3dd4  jmp     short loc_1800C3DDD
0x1800c3dd6  or      [rsi+15A0h], r13d
0x1800c3ddd  add     bpl, r13b
0x1800c3de0  cmp     bpl, [r14]
0x1800c3de3  jb      short loc_1800C3D81
0x1800c3de5  mov     eax, [rsi+15A0h]
0x1800c3deb  test    eax, eax
0x1800c3ded  jz      loc_1800C3FEB
0x1800c3df3  bts     dword ptr [rsi+1488h], 10h
0x1800c3dfb  lea     r8, aConncapTdCompo; "  ConnCap TD Component: [0x%x]"
0x1800c3e02  mov     r9d, eax
0x1800c3e05  jmp     loc_1800C3D2D
0x1800c3e0a  lea     r8, aConnectionCapa; "Connection Capabilities Component ID se"...
0x1800c3e11  jmp     loc_1800C3D4C
0x1800c3e16  test    dword ptr [rsi+1488h], 1000h
0x1800c3e20  jz      short loc_1800C3E3D
0x1800c3e22  lea     r8, aMultipleDnnTyp; "Multiple DNN-typed components. Upsuppor"...
0x1800c3e29  xor     edx, edx; struct _GUID *
0x1800c3e2b  mov     rcx, rdi; char *
0x1800c3e2e  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800c3e33  mov     edx, 11h
0x1800c3e38  jmp     loc_1800C4001
0x1800c3e3d  cmp     bx, 3
0x1800c3e41  jb      loc_1800C41F8
0x1800c3e47  movzx   r15d, byte ptr [r14]
0x1800c3e4b  movzx   ecx, bx
0x1800c3e4e  lea     eax, [r15+1]
0x1800c3e52  cmp     ecx, eax
0x1800c3e54  jb      loc_1800C41E9
0x1800c3e5a  test    r15b, r15b
0x1800c3e5d  jz      loc_1800C41DD
0x1800c3e63  mov     ecx, 1
0x1800c3e68  lea     r13, [r14+1]
0x1800c3e6c  movzx   ebp, cx
0x1800c3e6f  test    r15d, r15d
0x1800c3e72  jz      loc_1800C3FC0
0x1800c3e78  cmp     [r13+0], r10b
0x1800c3e7c  jz      loc_1800C41C4
0x1800c3e82  movzx   edx, byte ptr [r13+0]
0x1800c3e87  lea     eax, [rdx+1]
0x1800c3e8a  cmp     r15d, eax
0x1800c3e8d  jb      loc_1800C41A0
0x1800c3e93  cmp     byte ptr [r13+0], 64h ; 'd'
0x1800c3e98  jnb     short loc_1800C3EED
0x1800c3e9a  lea     r11, [r13+1]
0x1800c3e9e  mov     r8b, r10b
0x1800c3ea1  mov     r9, r11
0x1800c3ea4  cmp     r8b, [r13+0]
0x1800c3ea8  jnb     short loc_1800C3EFD
0x1800c3eaa  mov     cl, [r9]
0x1800c3ead  lea     eax, [rcx-2Dh]
0x1800c3eb0  cmp     al, 2Dh ; '-'
0x1800c3eb2  ja      short loc_1800C3EC7
0x1800c3eb4  mov     r10, 3FFFFFF01FF9h
0x1800c3ebe  bt      r10, rax
0x1800c3ec2  jb      short loc_1800C3ED9
0x1800c3ec4  xor     r10d, r10d
0x1800c3ec7  sub     cl, 61h ; 'a'
0x1800c3eca  cmp     cl, 19h
0x1800c3ecd  jbe     short loc_1800C3ED9
0x1800c3ecf  mov     al, r10b
0x1800c3ed2  mov     ecx, 1
0x1800c3ed7  jmp     short loc_1800C3EE3
0x1800c3ed9  mov     ecx, 1
0x1800c3ede  xor     r10d, r10d
0x1800c3ee1  mov     al, cl
0x1800c3ee3  add     r8b, cl
0x1800c3ee6  add     r9, rcx
0x1800c3ee9  test    al, al
0x1800c3eeb  jnz     short loc_1800C3EA4
0x1800c3eed  movzx   r9d, bp
0x1800c3ef1  lea     r8, aApnLabelDConta; "APN label#%d contains invalid ascii cha"...
0x1800c3ef8  jmp     loc_1800C4218
0x1800c3efd  movzx   eax, bp
0x1800c3f00  mov     [rsp+68h+arg_18], r10
0x1800c3f08  add     bp, cx
0x1800c3f0b  mov     r8d, 1
0x1800c3f11  lea     rcx, [rsi+15A4h]; unsigned __int16 *
0x1800c3f18  cmp     r8w, ax
0x1800c3f1c  jnz     short loc_1800C3F2B
0x1800c3f1e  mov     dword ptr [rsp+68h+cchWideChar], 65h ; 'e'
0x1800c3f26  mov     r9d, edx
0x1800c3f29  jmp     short loc_1800C3F81
0x1800c3f2b  lea     r8, [rsp+68h+arg_18]; unsigned __int64 *
0x1800c3f33  mov     edx, 65h ; 'e'; unsigned __int64
0x1800c3f38  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c3f3d  test    eax, eax
0x1800c3f3f  js      loc_1800C4193
0x1800c3f45  mov     rcx, [rsp+68h+arg_18]
0x1800c3f4d  cmp     rcx, 62h ; 'b'
0x1800c3f51  jnb     loc_1800C4181
0x1800c3f57  movzx   eax, cx
0x1800c3f5a  mov     edx, 64h ; 'd'
  ... truncated ...
```
