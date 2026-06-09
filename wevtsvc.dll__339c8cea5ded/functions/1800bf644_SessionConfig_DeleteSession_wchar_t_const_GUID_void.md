# SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)

- ea: `0x1800bf644`
- end: `0x1800bff13`
- name: `?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z`
- size: `2255`
- prototype: `void __fastcall(const wchar_t *, struct _GUID *__struct_ptr, void *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059508`
- `0x180084c98`

## callees

- `0x180004a3c`
- `0x180006600`
- `0x180006770`
- `0x180006fb0`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18002afa8`
- `0x18002c668`
- `0x18003a2c8`
- `0x18005c2d4`
- `0x180088854`
- `0x18008df50`
- `0x180092008`
- `0x18009fac8`
- `0x1800be098`
- `0x1800be1ec`
- `0x1800be3ac`
- `0x1800bf644`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800bf85d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800bf85d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bf8f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bfdf2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bf8f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bfdf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall SessionConfig::DeleteSession(wchar_t *a1, struct _GUID *a2, void *a3)
{
  __int64 v3; // rcx
  unsigned int AutoLoggerSecurityRegPath; // eax
  unsigned int v5; // r15d
  HKEY *v6; // rax
  HKEY v7; // r13
  unsigned int v8; // eax
  unsigned int v9; // r12d
  int v10; // eax
  int v11; // r12d
  LSTATUS v12; // eax
  __int64 v13; // rcx
  int AutoLoggersRegPath; // eax
  int v15; // r12d
  HKEY *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // r12d
  wchar_t *v19; // r13
  unsigned int v20; // eax
  int v21; // r12d
  HKEY *v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // r12d
  __int64 v26; // rax
  unsigned int PersistedAutoLoggerRegPath; // eax
  int v28; // r12d
  HKEY *v29; // rax
  struct _SECURITY_ATTRIBUTES *const v30; // r9
  unsigned int RegKey; // eax
  unsigned int v32; // r12d
  unsigned int v33; // eax
  unsigned int v34; // r12d
  __int128 v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  int v37; // [rsp+58h] [rbp-A8h]
  int v38; // [rsp+5Ch] [rbp-A4h]
  int v39; // [rsp+60h] [rbp-A0h]
  char v40; // [rsp+64h] [rbp-9Ch]
  DWORD pcbData[2]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v43; // [rsp+78h] [rbp-88h] BYREF
  HKEY hkey[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v45; // [rsp+90h] [rbp-70h]
  LPCWSTR pExceptionObject[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B4h] [rbp-4Ch]
  int v49; // [rsp+B8h] [rbp-48h]
  char v50; // [rsp+BCh] [rbp-44h]
  wchar_t *v51[4]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v52[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v54[4]; // [rsp+120h] [rbp+20h] BYREF

  v45 = a2;
  v43 = a1;
  hkey[0] = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v54);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  AutoLoggerSecurityRegPath = RegistryPaths::GetAutoLoggerSecurityRegPath(v3, hkey, v54, lpSubKey);
  v5 = AutoLoggerSecurityRegPath;
  if ( AutoLoggerSecurityRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        AutoLoggerSecurityRegPath);
    }
    pExceptionObject[0] = &byte_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v47 = v5;
    v48 = -1;
    v49 = -1;
    v50 = 0;
    throw (EvtException *)pExceptionObject;
  }
  hKey = 0;
  v6 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v7 = hkey[0];
  v8 = OpenRegKey(hkey[0], v54[0], 0x20006u, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v8);
      }
      v35 = 0;
      v36 = 0;
      v37 = v9;
      v38 = -1;
      v39 = 976;
      throw (EvtException *)&v35;
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject);
    v10 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject, v45, 0);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          (unsigned int)v10);
      }
      *(_QWORD *)&v35 = &byte_1800EC961;
      *((_QWORD *)&v35 + 1) = 0;
      v36 = 0;
      v37 = v11;
      v38 = -1;
      v39 = -1;
      v40 = 0;
      throw (EvtException *)&v35;
    }
    RegDeleteValueW(hKey, pExceptionObject[0]);
    if ( lpSubKey[0] != lpSubKey[1] )
    {
      pcbData[0] = 0;
      hkey[0] = 0;
      if ( !(unsigned int)RegReadByteArrayValueNoThrow(v7, lpSubKey[0], pExceptionObject[0], pcbData, (__int64)hkey) )
      {
        if ( pcbData[0] )
        {
          if ( !(unsigned int)RegReadByteArrayValueNoThrow(
                                v7,
                                lpSubKey[0],
                                L"0811c1af-7a07-4a06-82ed-869455cdf713",
                                pcbData,
                                (__int64)hkey) )
          {
            if ( pcbData[0] )
            {
              v12 = RegSetValueExW(hKey, pExceptionObject[0], 0, 3u, (const BYTE *)hkey[0], pcbData[0]);
              if ( v12 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    61,
                    (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
                    pExceptionObject[0],
                    v12);
                }
              }
            }
          }
        }
      }
      utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(hkey);
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pExceptionObject);
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v54);
  *(_QWORD *)pcbData = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v51);
  AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v13, pcbData, v52, v51);
  v15 = AutoLoggersRegPath;
  if ( AutoLoggersRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        (unsigned int)AutoLoggersRegPath);
    }
    *(_QWORD *)&v35 = &byte_1800EC961;
    *((_QWORD *)&v35 + 1) = 0;
    v36 = 0;
    v37 = v15;
    v38 = -1;
    v39 = -1;
    v40 = 0;
    throw (EvtException *)&v35;
  }
  hKey = 0;
  v16 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v17 = OpenRegKey(*(HKEY *)pcbData, v52[0], 0x2001Fu, v16, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v18 = v17;
  if ( v17 )
  {
    if ( v17 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v17);
      }
      v35 = 0;
      v36 = 0;
      v37 = v18;
      v38 = -1;
      v39 = 1028;
      throw (EvtException *)&v35;
    }
    v19 = v43;
  }
  else
  {
    v19 = v43;
    v20 = RegDeleteKeyRecursive(hKey, v43, (void *)0xFFFFFFFFFFFFFFFFLL);
    v21 = v20;
    if ( (v20 & 0xFFFFFFFD) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v20);
      }
      v35 = 0;
      v36 = 0;
      v37 = v21;
      v38 = -1;
      v39 = 1036;
      throw (EvtException *)&v35;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S_guid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
        (_DWORD)v19,
        (__int64)v45,
        (__int64)v52[0]);
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( v51[0] != v51[1] )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v51,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             v51,
                             v19) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
      }
      v35 = 0;
      v36 = 0;
      v37 = 14;
      v38 = -1;
      v39 = 1050;
      throw (EvtException *)&v35;
    }
    v43 = 0;
    v22 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>((HKEY *)&v43);
    v23 = OpenRegKey(*(HKEY *)pcbData, v51[0], 0x2001Fu, v22, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v25 = v23;
    if ( v23 )
    {
      if ( v23 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v23);
        }
        v35 = 0;
        v36 = 0;
        v37 = v25;
        v38 = -1;
        v39 = 1057;
        throw (EvtException *)&v35;
      }
    }
    else
    {
      v26 = -1;
      do
        ++v26;
      while ( v19[v26] );
      hkey[0] = (HKEY)v19;
      hkey[1] = (HKEY)v26;
      PersistedAutoLoggerRegPath = RegistryPaths::GetPersistedAutoLoggerRegPath(v24, hkey, pcbData, v52);
      v28 = PersistedAutoLoggerRegPath;
      if ( PersistedAutoLoggerRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
            PersistedAutoLoggerRegPath);
        }
        *(_QWORD *)&v35 = &byte_1800EC961;
        *((_QWORD *)&v35 + 1) = 0;
        v36 = 0;
        v37 = v28;
        v38 = -1;
        v39 = -1;
        v40 = 0;
        throw (EvtException *)&v35;
      }
      hKey = 0;
      v29 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      RegKey = CreateRegKey(*(HKEY *)pcbData, v52[0], 0x2001Fu, v30, v29, 0, (void *)0xFFFFFFFFFFFFFFFFLL);
      v32 = RegKey;
      if ( RegKey )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, RegKey);
        }
        *(_QWORD *)&v35 = &byte_1800EC961;
        *((_QWORD *)&v35 + 1) = 0;
        v36 = 0;
        v37 = v32;
        v38 = -1;
        v39 = -1;
        v40 = 0;
        throw (EvtException *)&v35;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S_guid_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          (unsigned int)&WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
          (_DWORD)v19,
          (__int64)v45,
          (__int64)v52[0]);
      }
      pcbData[0] = 0;
      v33 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)pcbData, 4u);
      v34 = v33;
      if ( v33 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v33);
        }
        *(_QWORD *)&v35 = &byte_1800EC961;
        *((_QWORD *)&v35 + 1) = 0;
        v36 = 0;
        v37 = v34;
        v38 = -1;
        v39 = -1;
        v40 = 0;
        throw (EvtException *)&v35;
      }
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v43);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v51);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v52);
}

```

## disassembly

```asm
0x1800bf644  mov     [rsp-8+arg_10], rbx
0x1800bf649  mov     [rsp-8+arg_18], rsi
0x1800bf64e  push    rbp
0x1800bf64f  push    r12
0x1800bf651  push    r13
0x1800bf653  push    r14
0x1800bf655  push    r15
0x1800bf657  lea     rbp, [rsp-40h]
0x1800bf65c  sub     rsp, 140h
0x1800bf663  mov     [rbp+60h+var_D0], rdx
0x1800bf667  mov     [rsp+160h+var_E8], rcx
0x1800bf66c  xor     r12d, r12d
0x1800bf66f  mov     [rbp+60h+hkey], r12
0x1800bf673  lea     rcx, [rbp+60h+var_40]; void *
0x1800bf677  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bf67c  nop
0x1800bf67d  lea     rcx, [rbp+60h+lpSubKey]; void *
0x1800bf681  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bf686  nop
0x1800bf687  lea     r9, [rbp+60h+lpSubKey]
0x1800bf68b  lea     r8, [rbp+60h+var_40]
0x1800bf68f  lea     rdx, [rbp+60h+hkey]
0x1800bf693  call    ?GetAutoLoggerSecurityRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggerSecurityRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800bf698  mov     r15d, eax
0x1800bf69b  test    eax, eax
0x1800bf69d  jz      short loc_1800BF713
0x1800bf69f  lea     rsi, WPP_GLOBAL_Control
0x1800bf6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf6ad  cmp     rcx, rsi
0x1800bf6b0  jz      short loc_1800BF6D8
0x1800bf6b2  lea     ebx, [r12+4]
0x1800bf6b7  test    [rcx+1Ch], bl
0x1800bf6ba  jz      short loc_1800BF6D8
0x1800bf6bc  cmp     byte ptr [rcx+19h], 2
0x1800bf6c0  jb      short loc_1800BF6D8
0x1800bf6c2  lea     edx, [rbx+36h]
0x1800bf6c5  mov     r9d, eax
0x1800bf6c8  lea     r8, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800bf6cf  mov     rcx, [rcx+10h]
0x1800bf6d3  call    WPP_SF_d
0x1800bf6d8  lea     rax, byte_1800EC961
0x1800bf6df  mov     [rbp+60h+pExceptionObject], rax
0x1800bf6e3  mov     [rbp+60h+var_C0], r12
0x1800bf6e7  mov     [rbp+60h+var_B8], r12
0x1800bf6eb  mov     [rbp+60h+var_B0], r15d
0x1800bf6ef  mov     [rbp+60h+var_AC], 0FFFFFFFFh
0x1800bf6f6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bf6fa  mov     [rbp+60h+var_A8], r15d
0x1800bf6fe  mov     [rbp+60h+var_A4], r12b
0x1800bf702  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bf709  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800bf70d  call    _CxxThrowException_0
0x1800bf713  mov     [rsp+160h+hKey], r12
0x1800bf718  lea     rcx, [rsp+160h+hKey]
0x1800bf71d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800bf722  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bf726  mov     [rsp+160h+lpData], r15; void *
0x1800bf72b  mov     r9, rax; HKEY *
0x1800bf72e  mov     r8d, 20006h; unsigned int
0x1800bf734  mov     rdx, [rbp+60h+var_40]; wchar_t *
0x1800bf738  mov     r13, [rbp+60h+hkey]
0x1800bf73c  mov     rcx, r13; HKEY
0x1800bf73f  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1800bf744  mov     r12d, eax
0x1800bf747  lea     rsi, WPP_GLOBAL_Control
0x1800bf74e  lea     ebx, [r15+5]
0x1800bf752  lea     r14, WPP_b172996960853cbcad4882dc20a972f5_Traceguids
0x1800bf759  test    eax, eax
0x1800bf75b  jz      short loc_1800BF7C8
0x1800bf75d  cmp     eax, 2
0x1800bf760  jz      loc_1800BF943
0x1800bf766  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf76d  cmp     rcx, rsi
0x1800bf770  jz      short loc_1800BF78F
0x1800bf772  test    [rcx+1Ch], bl
0x1800bf775  jz      short loc_1800BF78F
0x1800bf777  cmp     byte ptr [rcx+19h], 2
0x1800bf77b  jb      short loc_1800BF78F
0x1800bf77d  lea     edx, [rbx+37h]
0x1800bf780  mov     r9d, eax
0x1800bf783  mov     r8, r14
0x1800bf786  mov     rcx, [rcx+10h]
0x1800bf78a  call    WPP_SF_d
0x1800bf78f  xorps   xmm0, xmm0
0x1800bf792  movdqu  [rsp+160h+var_120], xmm0
0x1800bf798  mov     [rsp+160h+var_110], 0
0x1800bf7a1  mov     [rsp+160h+var_108], r12d
0x1800bf7a6  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x1800bf7ae  mov     [rsp+160h+var_100], 3D0h
0x1800bf7b6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bf7bd  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x1800bf7c2  call    _CxxThrowException_0
0x1800bf7c8  lea     rcx, [rbp+60h+pExceptionObject]; void *
0x1800bf7cc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bf7d1  nop
0x1800bf7d2  xor     r8d, r8d
0x1800bf7d5  mov     rdx, [rbp+60h+var_D0]
0x1800bf7d9  lea     rcx, [rbp+60h+pExceptionObject]
0x1800bf7dd  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x1800bf7e2  mov     r12d, eax
0x1800bf7e5  test    eax, eax
0x1800bf7e7  jns     short loc_1800BF854
0x1800bf7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf7f0  cmp     rcx, rsi
0x1800bf7f3  jz      short loc_1800BF814
0x1800bf7f5  test    [rcx+1Ch], bl
0x1800bf7f8  jz      short loc_1800BF814
0x1800bf7fa  cmp     byte ptr [rcx+19h], 2
0x1800bf7fe  jb      short loc_1800BF814
0x1800bf800  mov     edx, 3Ch ; '<'
0x1800bf805  mov     r9d, eax
0x1800bf808  mov     r8, r14
0x1800bf80b  mov     rcx, [rcx+10h]
0x1800bf80f  call    WPP_SF_d
0x1800bf814  lea     rax, byte_1800EC961
0x1800bf81b  mov     qword ptr [rsp+160h+var_120], rax
0x1800bf820  xor     eax, eax
0x1800bf822  mov     qword ptr [rsp+160h+var_120+8], rax
0x1800bf827  mov     [rsp+160h+var_110], rax
0x1800bf82c  mov     [rsp+160h+var_108], r12d
0x1800bf831  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x1800bf839  mov     [rsp+160h+var_100], r15d
0x1800bf83e  mov     [rsp+160h+var_FC], al
0x1800bf842  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bf849  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x1800bf84e  call    _CxxThrowException_0
0x1800bf854  mov     rdx, [rbp+60h+pExceptionObject]; lpValueName
0x1800bf858  mov     rcx, [rsp+160h+hKey]; hKey
0x1800bf85d  call    cs:__imp_RegDeleteValueW
0x1800bf863  mov     rdx, [rbp+60h+lpSubKey]; lpSubKey
0x1800bf867  cmp     rdx, [rbp+60h+var_58]
0x1800bf86b  jz      loc_1800BF939
0x1800bf871  xor     r12d, r12d
0x1800bf874  mov     [rsp+160h+pcbData], r12d
0x1800bf879  mov     [rbp+60h+hkey], r12
0x1800bf87d  lea     rax, [rbp+60h+hkey]
0x1800bf881  mov     [rsp+160h+lpData], rax; __int64
0x1800bf886  lea     r9, [rsp+160h+pcbData]; pcbData
0x1800bf88b  mov     r8, [rbp+60h+pExceptionObject]; lpValue
0x1800bf88f  mov     rcx, r13; hkey
0x1800bf892  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x1800bf897  test    eax, eax
0x1800bf899  jnz     loc_1800BF92F
0x1800bf89f  cmp     [rsp+160h+pcbData], r12d
0x1800bf8a4  jbe     loc_1800BF92F
0x1800bf8aa  lea     rax, [rbp+60h+hkey]
0x1800bf8ae  mov     [rsp+160h+lpData], rax; __int64
0x1800bf8b3  lea     r9, [rsp+160h+pcbData]; pcbData
0x1800bf8b8  lea     r8, a0811c1af7a074a; "0811c1af-7a07-4a06-82ed-869455cdf713"
0x1800bf8bf  mov     rdx, [rbp+60h+lpSubKey]; lpSubKey
0x1800bf8c3  mov     rcx, r13; hkey
0x1800bf8c6  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x1800bf8cb  test    eax, eax
0x1800bf8cd  jnz     short loc_1800BF92F
0x1800bf8cf  mov     eax, [rsp+160h+pcbData]
0x1800bf8d3  test    eax, eax
0x1800bf8d5  jz      short loc_1800BF92F
0x1800bf8d7  mov     [rsp+160h+cbData], eax; cbData
0x1800bf8db  mov     rax, [rbp+60h+hkey]
0x1800bf8df  mov     [rsp+160h+lpData], rax; lpData
0x1800bf8e4  lea     r9d, [r12+3]; dwType
0x1800bf8e9  xor     r8d, r8d; Reserved
0x1800bf8ec  mov     rdx, [rbp+60h+pExceptionObject]; lpValueName
0x1800bf8f0  mov     rcx, [rsp+160h+hKey]; hKey
0x1800bf8f5  call    cs:__imp_RegSetValueExW
0x1800bf8fb  test    eax, eax
0x1800bf8fd  jz      short loc_1800BF92F
0x1800bf8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf906  cmp     rcx, rsi
0x1800bf909  jz      short loc_1800BF92F
0x1800bf90b  test    [rcx+1Ch], bl
0x1800bf90e  jz      short loc_1800BF92F
0x1800bf910  cmp     byte ptr [rcx+19h], 3
0x1800bf914  jb      short loc_1800BF92F
0x1800bf916  lea     edx, [r12+3Dh]
0x1800bf91b  mov     dword ptr [rsp+160h+lpData], eax
0x1800bf91f  mov     r9, [rbp+60h+pExceptionObject]
0x1800bf923  mov     r8, r14
0x1800bf926  mov     rcx, [rcx+10h]
0x1800bf92a  call    WPP_SF_Sd
0x1800bf92f  lea     rcx, [rbp+60h+hkey]
0x1800bf933  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800bf938  nop
0x1800bf939  lea     rcx, [rbp+60h+pExceptionObject]; void *
0x1800bf93d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800bf942  nop
0x1800bf943  lea     rcx, [rsp+160h+hKey]
0x1800bf948  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800bf94d  nop
0x1800bf94e  lea     rcx, [rbp+60h+lpSubKey]; void *
0x1800bf952  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800bf957  nop
0x1800bf958  lea     rcx, [rbp+60h+var_40]; void *
0x1800bf95c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800bf961  xor     r13d, r13d
0x1800bf964  mov     qword ptr [rsp+160h+pcbData], r13
0x1800bf969  lea     rcx, [rbp+60h+var_80]; void *
0x1800bf96d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bf972  nop
0x1800bf973  lea     rcx, [rbp+60h+var_A0]; void *
0x1800bf977  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800bf97c  nop
0x1800bf97d  lea     r9, [rbp+60h+var_A0]
0x1800bf981  lea     r8, [rbp+60h+var_80]
0x1800bf985  lea     rdx, [rsp+160h+pcbData]
0x1800bf98a  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800bf98f  mov     r12d, eax
0x1800bf992  test    eax, eax
0x1800bf994  jns     short loc_1800BF9FF
0x1800bf996  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf99d  cmp     rcx, rsi
0x1800bf9a0  jz      short loc_1800BF9C0
0x1800bf9a2  test    [rcx+1Ch], bl
0x1800bf9a5  jz      short loc_1800BF9C0
0x1800bf9a7  cmp     byte ptr [rcx+19h], 2
0x1800bf9ab  jb      short loc_1800BF9C0
0x1800bf9ad  lea     edx, [r13+3Eh]
0x1800bf9b1  mov     r9d, eax
0x1800bf9b4  mov     r8, r14
0x1800bf9b7  mov     rcx, [rcx+10h]
0x1800bf9bb  call    WPP_SF_d
0x1800bf9c0  lea     rax, byte_1800EC961
0x1800bf9c7  mov     qword ptr [rsp+160h+var_120], rax
0x1800bf9cc  mov     qword ptr [rsp+160h+var_120+8], r13
0x1800bf9d1  mov     [rsp+160h+var_110], r13
0x1800bf9d6  mov     [rsp+160h+var_108], r12d
0x1800bf9db  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x1800bf9e3  mov     [rsp+160h+var_100], r15d
0x1800bf9e8  mov     [rsp+160h+var_FC], r13b
0x1800bf9ed  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bf9f4  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x1800bf9f9  call    _CxxThrowException_0
0x1800bf9ff  mov     [rsp+160h+hKey], r13
0x1800bfa04  lea     rcx, [rsp+160h+hKey]
0x1800bfa09  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800bfa0e  mov     [rsp+160h+lpData], r15; void *
0x1800bfa13  mov     r9, rax; HKEY *
0x1800bfa16  mov     r8d, 2001Fh; unsigned int
0x1800bfa1c  mov     rdx, [rbp+60h+var_80]; wchar_t *
0x1800bfa20  mov     rcx, qword ptr [rsp+160h+pcbData]; HKEY
0x1800bfa25  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1800bfa2a  mov     r12d, eax
0x1800bfa2d  test    eax, eax
0x1800bfa2f  jz      short loc_1800BFA9A
0x1800bfa31  cmp     eax, 2
0x1800bfa34  jz      loc_1800BFB5A
0x1800bfa3a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfa41  cmp     rcx, rsi
0x1800bfa44  jz      short loc_1800BFA65
0x1800bfa46  test    [rcx+1Ch], bl
0x1800bfa49  jz      short loc_1800BFA65
0x1800bfa4b  cmp     byte ptr [rcx+19h], 2
0x1800bfa4f  jb      short loc_1800BFA65
0x1800bfa51  mov     edx, 3Fh ; '?'
0x1800bfa56  mov     r9d, eax
0x1800bfa59  mov     r8, r14
0x1800bfa5c  mov     rcx, [rcx+10h]
0x1800bfa60  call    WPP_SF_d
0x1800bfa65  xorps   xmm0, xmm0
0x1800bfa68  movdqu  [rsp+160h+var_120], xmm0
0x1800bfa6e  mov     [rsp+160h+var_110], r13
0x1800bfa73  mov     [rsp+160h+var_108], r12d
0x1800bfa78  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x1800bfa80  mov     [rsp+160h+var_100], 404h
0x1800bfa88  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bfa8f  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x1800bfa94  call    _CxxThrowException_0
0x1800bfa9a  mov     r8, r15; void *
0x1800bfa9d  mov     r13, [rsp+160h+var_E8]
0x1800bfaa2  mov     rdx, r13; wchar_t *
0x1800bfaa5  mov     rcx, [rsp+160h+hKey]; HKEY
0x1800bfaaa  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x1800bfaaf  mov     r12d, eax
0x1800bfab2  test    eax, 0FFFFFFFDh
0x1800bfab7  jz      short loc_1800BFB1B
0x1800bfab9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfac0  cmp     rcx, rsi
0x1800bfac3  jz      short loc_1800BFAE4
0x1800bfac5  test    [rcx+1Ch], bl
0x1800bfac8  jz      short loc_1800BFAE4
0x1800bfaca  cmp     byte ptr [rcx+19h], 2
0x1800bface  jb      short loc_1800BFAE4
0x1800bfad0  mov     edx, 40h ; '@'
0x1800bfad5  mov     r9d, eax
0x1800bfad8  mov     r8, r14
0x1800bfadb  mov     rcx, [rcx+10h]
0x1800bfadf  call    WPP_SF_d
0x1800bfae4  xorps   xmm0, xmm0
0x1800bfae7  movdqu  [rsp+160h+var_120], xmm0
0x1800bfaed  xor     eax, eax
0x1800bfaef  mov     [rsp+160h+var_110], rax
0x1800bfaf4  mov     [rsp+160h+var_108], r12d
0x1800bfaf9  mov     [rsp+160h+var_104], 0FFFFFFFFh
0x1800bfb01  mov     [rsp+160h+var_100], 40Ch
0x1800bfb09  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800bfb10  lea     rcx, [rsp+160h+var_120]; pExceptionObject
0x1800bfb15  call    _CxxThrowException_0
0x1800bfb1b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfb22  cmp     rcx, rsi
0x1800bfb25  jz      short loc_1800BFB5F
  ... truncated ...
```
