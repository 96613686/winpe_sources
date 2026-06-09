# SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)

- ea: `0x18009642c`
- end: `0x180097164`
- name: `?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z`
- size: `3384`
- prototype: `void __fastcall(struct _GUID *, const struct ChannelConfigSnapshot *, unsigned int, bool, void *)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059508`
- `0x18008302c`

## callees

- `0x180006600`
- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x180017e28`
- `0x18002afa8`
- `0x18002d1dc`
- `0x18002d6dc`
- `0x18003a2c8`
- `0x18005c2d4`
- `0x18005c600`
- `0x18006ea98`
- `0x180071db8`
- `0x1800778a4`
- `0x18008df50`
- `0x180092008`
- `0x18009642c`
- `0x18009aee0`
- `0x1800c064c`
- `0x1800c06d0`
- `0x1800d334c`
- `0x1800d3364`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096b68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096c10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096d6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096e14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096eb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096f61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096b68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096c10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096d6d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096e14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096eb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096f61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180096954`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180096954`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SessionConfig::UpdateProvider(
        struct _GUID *a1,
        const struct ChannelConfigSnapshot *a2,
        unsigned int a3,
        char a4,
        void *a5)
{
  HKEY v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // r8
  int v11; // eax
  int v12; // esi
  __int64 v13; // rcx
  int AutoLoggersRegPath; // eax
  int v15; // esi
  HKEY *v16; // rax
  unsigned int RegKey; // r15d
  HKEY v18; // rax
  HKEY *v19; // rax
  __int64 v20; // r13
  __int64 v21; // rbx
  char v22; // dl
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rcx
  unsigned __int8 v26; // si
  HKEY v27; // r10
  int v28; // edx
  int v29; // r8d
  HKEY *v30; // rax
  struct _SECURITY_ATTRIBUTES *const v31; // r9
  void *v32; // r15
  unsigned int v33; // eax
  unsigned int v34; // esi
  unsigned int v35; // eax
  unsigned int v36; // esi
  unsigned int v37; // eax
  int v38; // esi
  unsigned int v39; // eax
  unsigned int v40; // esi
  unsigned int v41; // eax
  unsigned int v42; // esi
  unsigned int v43; // eax
  unsigned int v44; // esi
  unsigned int v45; // eax
  unsigned int v46; // esi
  unsigned int v47; // eax
  int v48; // esi
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  int v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+64h] [rbp-9Ch]
  char v54; // [rsp+6Ch] [rbp-94h]
  HKEY v55[2]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h]
  BYTE Data[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h]
  void *Buf1; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v62; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v64; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v65; // [rsp+E0h] [rbp-20h]
  wchar_t *v66[4]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v67; // [rsp+118h] [rbp+18h] BYREF
  __int128 Buf2; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v69[10]; // [rsp+150h] [rbp+50h] BYREF

  Buf1 = a1;
  *(_QWORD *)Data = a5;
  v8 = (HKEY)*((_QWORD *)a2 + 25);
  v9 = (__int64)(*((_QWORD *)a2 + 26) - (_QWORD)v8) >> 1;
  hKey = v8;
  v57 = v9;
  if ( !(unsigned __int8)IsSecurityChannel(&hKey) )
  {
    if ( a3 > 8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 13);
      }
      pExceptionObject = 0;
      v51 = 0;
      v52 = 13;
      v53 = 0x4E1FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    hKey = v8;
    v57 = v9;
    SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
      v69,
      &hKey,
      *((unsigned __int8 *)a2 + 249),
      *((unsigned __int8 *)a2 + 248));
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v64);
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v64,
                             v69[0]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
      }
      pExceptionObject = 0;
      v51 = 0;
      v52 = 14;
      v53 = 0x4E8FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    Buf2 = *(_OWORD *)((char *)a2 + 8);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v67);
    LOBYTE(v10) = 1;
    v11 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v67, a1, v10);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          (unsigned int)v11);
      }
      *(_QWORD *)&pExceptionObject = &byte_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v51 = 0;
      v52 = v12;
      v53 = -1;
      v54 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    hKey = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v66);
    AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v13, &hKey, lpSubKey, v66);
    v15 = AutoLoggersRegPath;
    if ( AutoLoggersRegPath < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          (unsigned int)AutoLoggersRegPath);
      }
      *(_QWORD *)&pExceptionObject = &byte_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v51 = 0;
      v52 = v15;
      v53 = -1;
      v54 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             lpSubKey,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             lpSubKey,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
      }
      pExceptionObject = 0;
      v51 = 0;
      v52 = 14;
      v53 = 0x4FCFFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v55[0] = 0;
    v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v55);
    RegKey = OpenRegKey(hKey, lpSubKey[0], 0x2001Fu, v16, a5);
    v18 = 0;
    v62 = 0;
    if ( v66[0] != v66[1] )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               v66,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v66)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               v66,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v66) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
        }
        pExceptionObject = 0;
        v51 = 0;
        v52 = 14;
        v53 = 0x50AFFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
      v19 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v62);
      RegKey = OpenRegKey(hKey, v66[0], 0x20019u, v19, a5);
      v18 = v62;
    }
    v61 = 0;
    v20 = 0;
    v21 = 1LL << (63 - (unsigned __int8)a3);
    if ( (unsigned __int8)(*((_BYTE *)a2 + 249) - 2) <= 1u || *((_BYTE *)a2 + 248) == 2 )
    {
      v22 = a4;
      if ( !*((_BYTE *)a2 + 251) || !a4 )
        goto LABEL_49;
      v25 = *(_QWORD *)a2;
      v20 = 1LL << (63 - (unsigned __int8)a3);
      v24 = *(_QWORD *)a2;
    }
    else
    {
      RegReadQWORDValueWithFallbackNoThrow(v55[0], 0, v18, 0, L"MatchAnyKeyword", &v61);
      v22 = a4;
      if ( *((_BYTE *)a2 + 251) && a4 )
        v23 = v61 | v21;
      else
        v23 = v61 & ~v21;
      v24 = v23 & 0xFF00000000000000uLL;
      v25 = v24;
      v18 = v62;
    }
    v61 = v25;
    if ( v24 || v20 )
    {
      v26 = 0;
      goto LABEL_50;
    }
LABEL_49:
    v26 = 1;
LABEL_50:
    v27 = v55[0];
    if ( !v22 || v26 )
    {
      if ( !v18 && !v55[0] )
      {
LABEL_62:
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v62);
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v55);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v66);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v67);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v64);
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v69);
        return;
      }
      if ( v26 )
      {
        if ( !v55[0] )
          goto LABEL_65;
        if ( !v18 )
        {
          if ( !RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, (_DWORD)Buf1, (__int64)lpSubKey[0]);
          }
          goto LABEL_62;
        }
      }
    }
    if ( v55[0] )
    {
LABEL_66:
      if ( RegKey )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, RegKey);
        }
        *(_QWORD *)&pExceptionObject = &byte_1800EC961;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        v51 = 0;
        v52 = RegKey;
        v53 = -1;
        v54 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v32 = Buf1;
      }
      else
      {
        v32 = Buf1;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          *(LPCWSTR *)Data = lpSubKey[0];
          v59 = lpSubKey[1] - lpSubKey[0];
          hKey = (HKEY)*((_QWORD *)a2 + 25);
          v57 = (__int64)(*((_QWORD *)a2 + 26) - (_QWORD)hKey) >> 1;
          WPP_SF__guid__utlwsv__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&hKey, (__int64)Data);
          v27 = v55[0];
        }
      }
      LODWORD(hKey) = v26 ^ 1;
      v33 = RegSetValueExW(v27, L"Enabled", 0, 4u, (const BYTE *)&hKey, 4u);
      v34 = v33;
      if ( v33 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v33);
        }
        *(_QWORD *)&pExceptionObject = &byte_1800EC961;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        v51 = 0;
        v52 = v34;
        v53 = -1;
        v54 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      LODWORD(hKey) = *((unsigned __int8 *)a2 + 50);
      v35 = RegSetValueExW(v55[0], L"EnableLevel", 0, 4u, (const BYTE *)&hKey, 4u);
      v36 = v35;
      if ( v35 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v35);
        }
        *(_QWORD *)&pExceptionObject = &byte_1800EC961;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        v51 = 0;
        v52 = v36;
        v53 = -1;
        v54 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_QWORD *)Data = v64;
      v59 = (v65 - v64) >> 1;
      v37 = RegWriteStringValueNoThrow(v55[0], L"LoggerName", Data);
      v38 = v37;
      if ( v37 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v37);
        }
        *(_QWORD *)&pExceptionObject = &byte_1800EC961;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        v51 = 0;
        v52 = v38;
        v53 = -1;
        v54 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      if ( !memcmp_0(v32, &Buf2, 0x10u) )
      {
        LODWORD(hKey) = *(_DWORD *)a2;
        v39 = RegSetValueExW(v55[0], L"EnableFlags", 0, 4u, (const BYTE *)&hKey, 4u);
        v40 = v39;
        if ( v39 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v39);
          }
          *(_QWORD *)&pExceptionObject = &byte_1800EC961;
          *((_QWORD *)&pExceptionObject + 1) = 0;
          v51 = 0;
          v52 = v40;
          v53 = -1;
          v54 = 0;
          throw (EvtException *)&pExceptionObject;
        }
      }
      else
      {
        *(_QWORD *)Data = v61;
        v41 = RegSetValueExW(v55[0], L"MatchAnyKeyword", 0, 0xBu, Data, 8u);
        v42 = v41;
        if ( v41 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v41);
          }
          *(_QWORD *)&pExceptionObject = &byte_1800EC961;
          *((_QWORD *)&pExceptionObject + 1) = 0;
          v51 = 0;
          v52 = v42;
          v53 = -1;
          v54 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        *(_QWORD *)Data = v20;
        v43 = RegSetValueExW(v55[0], L"MatchAllKeyword", 0, 0xBu, Data, 8u);
        v44 = v43;
        if ( v43 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v43);
          }
          *(_QWORD *)&pExceptionObject = &byte_1800EC961;
          *((_QWORD *)&pExceptionObject + 1) = 0;
          v51 = 0;
          v52 = v44;
          v53 = -1;
          v54 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        LODWORD(hKey) = *((_BYTE *)a2 + 49) != 0;
        v45 = RegSetValueExW(v55[0], L"EnableProperty", 0, 4u, (const BYTE *)&hKey, 4u);
        v46 = v45;
        if ( v45 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v45);
          }
          *(_QWORD *)&pExceptionObject = &byte_1800EC961;
          *((_QWORD *)&pExceptionObject + 1) = 0;
          v51 = 0;
          v52 = v46;
          v53 = -1;
          v54 = 0;
          throw (EvtException *)&pExceptionObject;
        }
        *(_QWORD *)Data = v64;
        v59 = (v65 - v64) >> 1;
        v47 = RegWriteStringValueNoThrow(v55[0], L"LoggerName", Data);
        v48 = v47;
        if ( v47 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v47);
          }
          *(_QWORD *)&pExceptionObject = &byte_1800EC961;
          *((_QWORD *)&pExceptionObject + 1) = 0;
          v51 = 0;
          v52 = v48;
          v53 = -1;
          v54 = 0;
          throw (EvtException *)&pExceptionObject;
        }
      }
      goto LABEL_62;
    }
LABEL_65:
    v30 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v55);
    RegKey = CreateRegKey(hKey, lpSubKey[0], 0x2001Fu, v31, v30, 0, *(void **)Data);
    v27 = v55[0];
    goto LABEL_66;
  }
}

```

## disassembly

```asm
0x18009642c  mov     [rsp-8+arg_18], rbx
0x180096431  push    rbp
0x180096432  push    rsi
0x180096433  push    rdi
0x180096434  push    r12
0x180096436  push    r13
0x180096438  push    r14
0x18009643a  push    r15
0x18009643c  lea     rbp, [rsp-0B0h]
0x180096444  sub     rsp, 1B0h
0x18009644b  mov     rax, cs:__security_cookie
0x180096452  xor     rax, rsp
0x180096455  mov     [rbp+0E0h+var_40], rax
0x18009645c  mov     [rsp+1E0h+var_1A0], r9b
0x180096461  mov     r12d, r8d
0x180096464  mov     r14, rdx
0x180096467  mov     rsi, rcx
0x18009646a  mov     [rbp+0E0h+Buf1], rcx
0x18009646e  mov     r13, [rbp+0E0h+arg_20]
0x180096475  mov     qword ptr [rbp+0E0h+Data], r13
0x180096479  mov     rdi, [rdx+0C8h]
0x180096480  mov     rbx, [rdx+0D0h]
0x180096487  sub     rbx, rdi
0x18009648a  sar     rbx, 1
0x18009648d  mov     [rbp+0E0h+hKey], rdi
0x180096491  mov     [rbp+0E0h+var_158], rbx
0x180096495  lea     rcx, [rbp+0E0h+hKey]
0x180096499  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18009649e  xor     r15d, r15d
0x1800964a1  test    al, al
0x1800964a3  jnz     loc_1800969DA
0x1800964a9  cmp     r12d, 8
0x1800964ad  jbe     short loc_18009651F
0x1800964af  lea     rbx, WPP_GLOBAL_Control
0x1800964b6  lea     esi, [r15+0Dh]
0x1800964ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800964c1  cmp     rcx, rbx
0x1800964c4  jz      short loc_1800964EB
0x1800964c6  test    byte ptr [rcx+1Ch], 4
0x1800964ca  jz      short loc_1800964EB
0x1800964cc  mov     dil, 2
0x1800964cf  cmp     [rcx+19h], dil
0x1800964d3  jb      short loc_1800964EB
0x1800964d5  lea     edx, [rsi+42h]
0x1800964d8  mov     r9d, esi
0x1800964db  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800964e2  mov     rcx, [rcx+10h]
0x1800964e6  call    WPP_SF_d
0x1800964eb  xorps   xmm0, xmm0
0x1800964ee  movdqu  [rsp+1E0h+pExceptionObject], xmm0
0x1800964f4  mov     [rsp+1E0h+var_188], r15
0x1800964f9  mov     [rsp+1E0h+var_180], esi
0x1800964fd  mov     dword ptr [rsp+1E0h+var_17C], 0FFFFFFFFh
0x180096505  mov     dword ptr [rsp+1E0h+var_17C+4], 4E1h
0x18009650d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180096514  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x180096519  call    _CxxThrowException_0
0x18009651f  mov     [rbp+0E0h+hKey], rdi
0x180096523  mov     [rbp+0E0h+var_158], rbx
0x180096527  movzx   r9d, byte ptr [r14+0F8h]
0x18009652f  movzx   r8d, byte ptr [r14+0F9h]
0x180096537  lea     rdx, [rbp+0E0h+hKey]
0x18009653b  lea     rcx, [rbp+0E0h+var_90]
0x18009653f  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x180096544  nop
0x180096545  lea     rcx, [rbp+0E0h+var_108]; void *
0x180096549  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009654e  nop
0x18009654f  mov     rdx, [rbp+0E0h+var_90]
0x180096553  lea     rcx, [rbp+0E0h+var_108]
0x180096557  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18009655c  test    al, al
0x18009655e  jnz     short loc_1800965D1
0x180096560  lea     rbx, WPP_GLOBAL_Control
0x180096567  mov     esi, 0Eh
0x18009656c  mov     rcx, cs:WPP_GLOBAL_Control
0x180096573  cmp     rcx, rbx
0x180096576  jz      short loc_18009659D
0x180096578  test    byte ptr [rcx+1Ch], 4
0x18009657c  jz      short loc_18009659D
0x18009657e  mov     dil, 2
0x180096581  cmp     [rcx+19h], dil
0x180096585  jb      short loc_18009659D
0x180096587  lea     edx, [rsi+42h]
0x18009658a  mov     r9d, esi
0x18009658d  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x180096594  mov     rcx, [rcx+10h]
0x180096598  call    WPP_SF_d
0x18009659d  xorps   xmm0, xmm0
0x1800965a0  movdqu  [rsp+1E0h+pExceptionObject], xmm0
0x1800965a6  mov     [rsp+1E0h+var_188], r15
0x1800965ab  mov     [rsp+1E0h+var_180], esi
0x1800965af  mov     dword ptr [rsp+1E0h+var_17C], 0FFFFFFFFh
0x1800965b7  mov     dword ptr [rsp+1E0h+var_17C+4], 4E8h
0x1800965bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800965c6  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x1800965cb  call    _CxxThrowException_0
0x1800965d1  movups  xmm0, xmmword ptr [r14+8]
0x1800965d6  movdqu  [rbp+0E0h+Buf2], xmm0
0x1800965db  lea     rcx, [rbp+0E0h+var_C8]; void *
0x1800965df  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800965e4  nop
0x1800965e5  mov     r8b, 1
0x1800965e8  mov     rdx, rsi
0x1800965eb  lea     rcx, [rbp+0E0h+var_C8]
0x1800965ef  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x1800965f4  mov     esi, eax
0x1800965f6  test    eax, eax
0x1800965f8  jns     short loc_18009666E
0x1800965fa  lea     rbx, WPP_GLOBAL_Control
0x180096601  mov     rcx, cs:WPP_GLOBAL_Control
0x180096608  cmp     rcx, rbx
0x18009660b  jz      short loc_180096634
0x18009660d  test    byte ptr [rcx+1Ch], 4
0x180096611  jz      short loc_180096634
0x180096613  mov     dil, 2
0x180096616  cmp     [rcx+19h], dil
0x18009661a  jb      short loc_180096634
0x18009661c  mov     edx, 51h ; 'Q'
0x180096621  mov     r9d, eax
0x180096624  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x18009662b  mov     rcx, [rcx+10h]
0x18009662f  call    WPP_SF_d
0x180096634  lea     rax, byte_1800EC961
0x18009663b  mov     qword ptr [rsp+1E0h+pExceptionObject], rax
0x180096640  mov     qword ptr [rsp+1E0h+pExceptionObject+8], r15
0x180096645  mov     [rsp+1E0h+var_188], r15
0x18009664a  mov     [rsp+1E0h+var_180], esi
0x18009664e  mov     [rsp+1E0h+var_17C], 0FFFFFFFFFFFFFFFFh
0x180096657  mov     [rsp+1E0h+var_174], r15b
0x18009665c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180096663  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x180096668  call    _CxxThrowException_0
0x18009666e  mov     [rbp+0E0h+hKey], r15
0x180096672  lea     rcx, [rbp+0E0h+lpSubKey]; void *
0x180096676  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009667b  nop
0x18009667c  lea     rcx, [rbp+0E0h+var_E8]; void *
0x180096680  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180096685  nop
0x180096686  lea     r9, [rbp+0E0h+var_E8]
0x18009668a  lea     r8, [rbp+0E0h+lpSubKey]
0x18009668e  lea     rdx, [rbp+0E0h+hKey]
0x180096692  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180096697  mov     esi, eax
0x180096699  test    eax, eax
0x18009669b  jns     short loc_180096711
0x18009669d  lea     rbx, WPP_GLOBAL_Control
0x1800966a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800966ab  cmp     rcx, rbx
0x1800966ae  jz      short loc_1800966D7
0x1800966b0  test    byte ptr [rcx+1Ch], 4
0x1800966b4  jz      short loc_1800966D7
0x1800966b6  mov     dil, 2
0x1800966b9  cmp     [rcx+19h], dil
0x1800966bd  jb      short loc_1800966D7
0x1800966bf  mov     edx, 52h ; 'R'
0x1800966c4  mov     r9d, eax
0x1800966c7  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800966ce  mov     rcx, [rcx+10h]
0x1800966d2  call    WPP_SF_d
0x1800966d7  lea     rax, byte_1800EC961
0x1800966de  mov     qword ptr [rsp+1E0h+pExceptionObject], rax
0x1800966e3  mov     qword ptr [rsp+1E0h+pExceptionObject+8], r15
0x1800966e8  mov     [rsp+1E0h+var_188], r15
0x1800966ed  mov     [rsp+1E0h+var_180], esi
0x1800966f1  mov     [rsp+1E0h+var_17C], 0FFFFFFFFFFFFFFFFh
0x1800966fa  mov     [rsp+1E0h+var_174], r15b
0x1800966ff  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180096706  lea     rcx, [rsp+1E0h+pExceptionObject]; pExceptionObject
0x18009670b  call    _CxxThrowException_0
0x180096711  mov     ebx, 5Ch ; '\'
0x180096716  mov     edx, ebx
0x180096718  lea     rcx, [rbp+0E0h+lpSubKey]
0x18009671c  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180096721  test    al, al
0x180096723  jz      loc_1800970F3
0x180096729  mov     r8, [rbp+0E0h+var_100]
0x18009672d  mov     rdx, [rbp+0E0h+var_108]
0x180096731  sub     r8, rdx
0x180096734  sar     r8, 1
0x180096737  lea     rcx, [rbp+0E0h+lpSubKey]
0x18009673b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180096740  test    al, al
0x180096742  jz      loc_1800970F3
0x180096748  mov     edx, ebx
0x18009674a  lea     rcx, [rbp+0E0h+lpSubKey]
0x18009674e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180096753  test    al, al
0x180096755  jz      loc_1800970F3
0x18009675b  mov     r8, [rbp+0E0h+var_C0]
0x18009675f  mov     rdx, [rbp+0E0h+var_C8]
0x180096763  sub     r8, rdx
0x180096766  sar     r8, 1
0x180096769  lea     rcx, [rbp+0E0h+lpSubKey]
0x18009676d  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180096772  test    al, al
0x180096774  jz      loc_1800970F3
0x18009677a  mov     [rsp+1E0h+var_170], r15
0x18009677f  lea     rcx, [rsp+1E0h+var_170]
0x180096784  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180096789  mov     [rsp+1E0h+lpData], r13; void *
0x18009678e  mov     r9, rax; HKEY *
0x180096791  mov     r8d, 2001Fh; unsigned int
0x180096797  mov     rdx, [rbp+0E0h+lpSubKey]; wchar_t *
0x18009679b  mov     rcx, [rbp+0E0h+hKey]; HKEY
0x18009679f  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1800967a4  mov     r15d, eax
0x1800967a7  xor     eax, eax
0x1800967a9  mov     [rbp+0E0h+var_130], rax
0x1800967ad  mov     rcx, [rbp+0E0h+var_E0]
0x1800967b1  cmp     [rbp+0E0h+var_E8], rcx
0x1800967b5  jz      loc_18009684A
0x1800967bb  mov     edx, ebx
0x1800967bd  lea     rcx, [rbp+0E0h+var_E8]
0x1800967c1  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800967c6  test    al, al
0x1800967c8  jz      loc_18009707E
0x1800967ce  mov     r8, [rbp+0E0h+var_100]
0x1800967d2  mov     rdx, [rbp+0E0h+var_108]
0x1800967d6  sub     r8, rdx
0x1800967d9  sar     r8, 1
0x1800967dc  lea     rcx, [rbp+0E0h+var_E8]
0x1800967e0  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800967e5  test    al, al
0x1800967e7  jz      loc_18009707E
0x1800967ed  mov     edx, ebx
0x1800967ef  lea     rcx, [rbp+0E0h+var_E8]
0x1800967f3  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800967f8  test    al, al
0x1800967fa  jz      loc_18009707E
0x180096800  mov     r8, [rbp+0E0h+var_C0]
0x180096804  mov     rdx, [rbp+0E0h+var_C8]
0x180096808  sub     r8, rdx
0x18009680b  sar     r8, 1
0x18009680e  lea     rcx, [rbp+0E0h+var_E8]
0x180096812  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180096817  test    al, al
0x180096819  jz      loc_18009707E
0x18009681f  lea     rcx, [rbp+0E0h+var_130]
0x180096823  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180096828  mov     [rsp+1E0h+lpData], r13; void *
0x18009682d  mov     r9, rax; HKEY *
0x180096830  mov     r8d, 20019h; unsigned int
0x180096836  mov     rdx, [rbp+0E0h+var_E8]; wchar_t *
0x18009683a  mov     rcx, [rbp+0E0h+hKey]; HKEY
0x18009683e  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x180096843  mov     r15d, eax
0x180096846  mov     rax, [rbp+0E0h+var_130]
0x18009684a  mov     [rbp+0E0h+var_138], 0
0x180096852  xor     r13d, r13d
0x180096855  lea     ecx, [r13+3Fh]
0x180096859  sub     ecx, r12d
0x18009685c  lea     ebx, [r13+1]
0x180096860  shl     rbx, cl
0x180096863  mov     cl, [r14+0F9h]
0x18009686a  mov     dil, 2
0x18009686d  sub     cl, dil
0x180096870  lea     rdx, aMatchanykeywor; "MatchAnyKeyword"
0x180096877  cmp     cl, 1
0x18009687a  jbe     short loc_1800968DC
0x18009687c  cmp     [r14+0F8h], dil
0x180096883  jz      short loc_1800968DC
0x180096885  lea     rcx, [rbp+0E0h+var_138]
0x180096889  mov     qword ptr [rsp+1E0h+cbData], rcx; unsigned __int64 *
0x18009688e  mov     [rsp+1E0h+lpData], rdx; wchar_t *
0x180096893  xor     r9d, r9d; wchar_t *
0x180096896  mov     r8, rax; HKEY
0x180096899  xor     edx, edx; wchar_t *
0x18009689b  mov     rcx, [rsp+1E0h+var_170]; HKEY
0x1800968a0  call    ?RegReadQWORDValueWithFallbackNoThrow@@YAJPEAUHKEY__@@PEB_W011AEA_K@Z; RegReadQWORDValueWithFallbackNoThrow(HKEY__ *,wchar_t const *,HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64 &)
0x1800968a5  xor     r12d, r12d
0x1800968a8  mov     dl, [rsp+1E0h+var_1A0]
0x1800968ac  cmp     [r14+0FBh], r12b
0x1800968b3  jz      short loc_1800968BF
0x1800968b5  test    dl, dl
0x1800968b7  jz      short loc_1800968BF
0x1800968b9  or      rbx, [rbp+0E0h+var_138]
0x1800968bd  jmp     short loc_1800968C6
0x1800968bf  not     rbx
0x1800968c2  and     rbx, [rbp+0E0h+var_138]
0x1800968c6  mov     rax, 0FF00000000000000h
0x1800968d0  and     rbx, rax
0x1800968d3  mov     rcx, rbx
0x1800968d6  mov     rax, [rbp+0E0h+var_130]
0x1800968da  jmp     short loc_1800968F9
0x1800968dc  xor     r12d, r12d
0x1800968df  mov     dl, [rsp+1E0h+var_1A0]
0x1800968e3  cmp     [r14+0FBh], r12b
0x1800968ea  jz      short loc_18009690C
0x1800968ec  test    dl, dl
0x1800968ee  jz      short loc_18009690C
0x1800968f0  mov     rcx, [r14]
0x1800968f3  mov     r13, rbx
0x1800968f6  mov     rbx, rcx
0x1800968f9  mov     [rbp+0E0h+var_138], rcx
0x1800968fd  test    rbx, rbx
0x180096900  jnz     short loc_180096907
0x180096902  test    r13, r13
0x180096905  jz      short loc_18009690C
  ... truncated ...
```
