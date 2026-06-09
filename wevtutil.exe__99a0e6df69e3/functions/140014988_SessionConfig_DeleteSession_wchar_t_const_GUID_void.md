# SessionConfig::DeleteSession(wchar_t const *,_GUID,void *)

- ea: `0x140014988`
- end: `0x1400151e5`
- name: `?DeleteSession@SessionConfig@@CAXPEB_WU_GUID@@PEAX@Z`
- size: `2141`
- prototype: `void __fastcall(const wchar_t *, struct _GUID *__struct_ptr, void *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013658`
- `0x14002ddb0`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140006db0`
- `0x140007fd0`
- `0x14000a4d8`
- `0x14000d2ec`
- `0x140014988`
- `0x140015898`
- `0x14001a814`
- `0x14001a9b8`
- `0x140022cec`
- `0x14002ba08`
- `0x14002e7ec`
- `0x14002f018`
- `0x14002f0d8`
- `0x14002f198`
- `0x14002f384`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140014b80`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140014b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014c76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014c76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014e69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015152`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140015163`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014c1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400150d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140014c1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400150d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall SessionConfig::DeleteSession(const wchar_t *a1, struct _GUID *a2, void *a3)
{
  __int64 v5; // rcx
  unsigned int AutoLoggerSecurityRegPath; // eax
  unsigned int v7; // r15d
  HKEY *v8; // rax
  HKEY v9; // r12
  unsigned int v10; // eax
  const char *v11; // r8
  unsigned int v12; // r15d
  int v13; // eax
  int v14; // r15d
  LSTATUS v15; // eax
  __int64 v16; // rcx
  int AutoLoggersRegPath; // eax
  int v18; // r15d
  HKEY *v19; // rax
  void *v20; // r12
  unsigned int v21; // eax
  const char *v22; // r8
  unsigned int v23; // r15d
  unsigned int v24; // eax
  const char *v25; // r8
  unsigned int v26; // r15d
  const char *v27; // r8
  HKEY *v28; // rax
  unsigned int v29; // eax
  const char *v30; // r8
  unsigned int v31; // r15d
  __int64 v32; // rax
  unsigned int PersistedAutoLoggerRegPath; // eax
  unsigned int v34; // r15d
  HKEY *v35; // rax
  unsigned int RegKey; // eax
  int v37; // r8d
  unsigned int v38; // r15d
  unsigned int v39; // eax
  unsigned int v40; // r15d
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  __int16 *v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  __int64 v46; // [rsp+68h] [rbp-98h]
  unsigned int v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+74h] [rbp-8Ch]
  char v49; // [rsp+7Ch] [rbp-84h]
  struct _GUID *v50; // [rsp+80h] [rbp-80h]
  LPCWSTR pExceptionObject[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v52; // [rsp+A0h] [rbp-60h]
  __int64 v53; // [rsp+A4h] [rbp-5Ch]
  char v54; // [rsp+ACh] [rbp-54h]
  void *v55[2]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v56[4]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v57[4]; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v59[10]; // [rsp+120h] [rbp+20h] BYREF

  v55[0] = a3;
  v50 = a2;
  hkey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v59);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  AutoLoggerSecurityRegPath = RegistryPaths::GetAutoLoggerSecurityRegPath(v5, &hkey, v59, lpSubKey);
  v7 = AutoLoggerSecurityRegPath;
  if ( AutoLoggerSecurityRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        AutoLoggerSecurityRegPath);
    }
    pExceptionObject[0] = (LPCWSTR)word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v52 = v7;
    v53 = -1;
    v54 = 0;
    throw (EvtException *)pExceptionObject;
  }
  hKey = 0;
  v8 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v9 = hkey;
  v10 = OpenRegKey(hkey, v59[0], 0x20006u, v8, a3);
  v12 = v10;
  if ( v10 )
  {
    if ( v10 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v10);
      }
      EvtException::EvtException((EvtException *)&v44, v12, v11, 976);
      throw (EvtException *)&v44;
    }
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject);
    v13 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject, v50, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
          (unsigned int)v13);
      }
      v44 = word_14003838A;
      v45 = 0;
      v46 = 0;
      v47 = v14;
      v48 = -1;
      v49 = 0;
      throw (EvtException *)&v44;
    }
    RegDeleteValueW(hKey, pExceptionObject[0]);
    if ( lpSubKey[0] != lpSubKey[1] )
    {
      pcbData[0] = 0;
      hkey = 0;
      if ( !(unsigned int)RegReadByteArrayValueNoThrow(v9, lpSubKey[0], pExceptionObject[0], pcbData, (__int64)&hkey) )
      {
        if ( pcbData[0] )
        {
          if ( !(unsigned int)RegReadByteArrayValueNoThrow(
                                v9,
                                lpSubKey[0],
                                L"0811c1af-7a07-4a06-82ed-869455cdf713",
                                pcbData,
                                (__int64)&hkey) )
          {
            if ( pcbData[0] )
            {
              v15 = RegSetValueExW(hKey, pExceptionObject[0], 0, 3u, (const BYTE *)hkey, pcbData[0]);
              if ( v15 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_SD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    61,
                    (unsigned int)&WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
                    pExceptionObject[0],
                    v15);
                }
              }
            }
          }
        }
      }
      utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&hkey);
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pExceptionObject);
  }
  if ( hKey )
    RegCloseKey(hKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v59);
  *(_QWORD *)pcbData = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v57);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v56);
  AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v16, pcbData, v57, v56);
  v18 = AutoLoggersRegPath;
  if ( AutoLoggersRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        (unsigned int)AutoLoggersRegPath);
    }
    v44 = word_14003838A;
    v45 = 0;
    v46 = 0;
    v47 = v18;
    v48 = -1;
    v49 = 0;
    throw (EvtException *)&v44;
  }
  hKey = 0;
  v19 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v20 = v55[0];
  v21 = OpenRegKey(*(HKEY *)pcbData, v57[0], 0x2001Fu, v19, v55[0]);
  v23 = v21;
  if ( v21 )
  {
    if ( v21 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v21);
      }
      EvtException::EvtException((EvtException *)&v44, v23, v22, 1028);
      throw (EvtException *)&v44;
    }
  }
  else
  {
    v24 = RegDeleteKeyRecursive(hKey, a1, v20);
    v26 = v24;
    if ( (v24 & 0xFFFFFFFD) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v24);
      }
      EvtException::EvtException((EvtException *)&v44, v26, v25, 1036);
      throw (EvtException *)&v44;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S_guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, (_DWORD)v25, (_DWORD)a1, (__int64)v50, (__int64)v57[0]);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v56[0] != v56[1] )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v56,
                             92)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v56, a1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&v44, 0xEu, v27, 1050);
      throw (EvtException *)&v44;
    }
    hkey = 0;
    v28 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    v29 = OpenRegKey(*(HKEY *)pcbData, v56[0], 0x2001Fu, v28, v20);
    v31 = v29;
    if ( v29 )
    {
      if ( v29 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v29);
        }
        EvtException::EvtException((EvtException *)&v44, v31, v30, 1057);
        throw (EvtException *)&v44;
      }
    }
    else
    {
      v32 = -1;
      do
        ++v32;
      while ( a1[v32] );
      v55[0] = (void *)a1;
      v55[1] = (void *)v32;
      PersistedAutoLoggerRegPath = RegistryPaths::GetPersistedAutoLoggerRegPath(0, v55, pcbData, v57);
      v34 = PersistedAutoLoggerRegPath;
      if ( PersistedAutoLoggerRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
            PersistedAutoLoggerRegPath);
        }
        v44 = word_14003838A;
        v45 = 0;
        v46 = 0;
        v47 = v34;
        v48 = -1;
        v49 = 0;
        throw (EvtException *)&v44;
      }
      hKey = 0;
      v35 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      RegKey = CreateRegKey(*(HKEY *)pcbData, v57[0], 0x2001Fu, 0, v35, 0, v20);
      v38 = RegKey;
      if ( RegKey )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, RegKey);
        }
        v44 = word_14003838A;
        v45 = 0;
        v46 = 0;
        v47 = v38;
        v48 = -1;
        v49 = 0;
        throw (EvtException *)&v44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S_guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, v37, (_DWORD)a1, (__int64)v50, (__int64)v57[0]);
      }
      pcbData[0] = 0;
      v39 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)pcbData, 4u);
      v40 = v39;
      if ( v39 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v39);
        }
        v44 = word_14003838A;
        v45 = 0;
        v46 = 0;
        v47 = v40;
        v48 = -1;
        v49 = 0;
        throw (EvtException *)&v44;
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
    if ( hkey )
      RegCloseKey(hkey);
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v56);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v57);
}

```

## disassembly

```asm
0x140014988  push    rbp
0x14001498a  push    rbx
0x14001498b  push    rsi
0x14001498c  push    r12
0x14001498e  push    r13
0x140014990  push    r14
0x140014992  push    r15
0x140014994  lea     rbp, [rsp-40h]
0x140014999  sub     rsp, 140h
0x1400149a0  mov     rbx, r8
0x1400149a3  mov     [rbp+70h+var_C0], rbx
0x1400149a7  mov     [rbp+70h+var_F0], rdx
0x1400149ab  mov     r13, rcx
0x1400149ae  xor     r12d, r12d
0x1400149b1  mov     [rsp+170h+hkey], r12
0x1400149b6  lea     rcx, [rbp+70h+var_50]
0x1400149ba  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400149bf  nop
0x1400149c0  lea     rcx, [rbp+70h+lpSubKey]
0x1400149c4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400149c9  nop
0x1400149ca  lea     r9, [rbp+70h+lpSubKey]
0x1400149ce  lea     r8, [rbp+70h+var_50]
0x1400149d2  lea     rdx, [rsp+170h+hkey]
0x1400149d7  call    ?GetAutoLoggerSecurityRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggerSecurityRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400149dc  mov     r15d, eax
0x1400149df  test    eax, eax
0x1400149e1  jz      short loc_140014A50
0x1400149e3  lea     rsi, WPP_GLOBAL_Control
0x1400149ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149f1  cmp     rcx, rsi
0x1400149f4  jz      short loc_140014A1C
0x1400149f6  lea     ebx, [r12+4]
0x1400149fb  test    [rcx+1Ch], bl
0x1400149fe  jz      short loc_140014A1C
0x140014a00  cmp     byte ptr [rcx+19h], 2
0x140014a04  jb      short loc_140014A1C
0x140014a06  lea     edx, [rbx+36h]
0x140014a09  mov     r9d, eax
0x140014a0c  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140014a13  mov     rcx, [rcx+10h]
0x140014a17  call    WPP_SF_d
0x140014a1c  lea     rax, word_14003838A
0x140014a23  mov     [rbp+70h+pExceptionObject], rax
0x140014a27  mov     [rbp+70h+var_E0], r12
0x140014a2b  mov     [rbp+70h+var_D8], r12
0x140014a2f  mov     [rbp+70h+var_D0], r15d
0x140014a33  mov     [rbp+70h+var_CC], 0FFFFFFFFFFFFFFFFh
0x140014a3b  mov     [rbp+70h+var_C4], r12b
0x140014a3f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014a46  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x140014a4a  call    _CxxThrowException_0
0x140014a50  mov     [rsp+170h+hKey], r12
0x140014a55  lea     rcx, [rsp+170h+hKey]
0x140014a5a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140014a5f  mov     [rsp+170h+lpData], rbx; void *
0x140014a64  mov     r9, rax; HKEY *
0x140014a67  mov     r8d, 20006h; unsigned int
0x140014a6d  mov     rdx, [rbp+70h+var_50]; wchar_t *
0x140014a71  mov     r12, [rsp+170h+hkey]
0x140014a76  mov     rcx, r12; HKEY
0x140014a79  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140014a7e  mov     r15d, eax
0x140014a81  lea     rsi, WPP_GLOBAL_Control
0x140014a88  mov     ebx, 4
0x140014a8d  lea     r14, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x140014a94  test    eax, eax
0x140014a96  jz      short loc_140014AEF
0x140014a98  cmp     eax, 2
0x140014a9b  jz      loc_140014C69
0x140014aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140014aa8  cmp     rcx, rsi
0x140014aab  jz      short loc_140014ACA
0x140014aad  test    [rcx+1Ch], bl
0x140014ab0  jz      short loc_140014ACA
0x140014ab2  cmp     byte ptr [rcx+19h], 2
0x140014ab6  jb      short loc_140014ACA
0x140014ab8  lea     edx, [rbx+37h]
0x140014abb  mov     r9d, eax
0x140014abe  mov     r8, r14
0x140014ac1  mov     rcx, [rcx+10h]
0x140014ac5  call    WPP_SF_d
0x140014aca  mov     r9d, 3D0h; int
0x140014ad0  mov     edx, r15d; unsigned int
0x140014ad3  lea     rcx, [rsp+170h+var_118]; this
0x140014ad8  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140014add  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014ae4  lea     rcx, [rsp+170h+var_118]; pExceptionObject
0x140014ae9  call    _CxxThrowException_0
0x140014aef  lea     rcx, [rbp+70h+pExceptionObject]
0x140014af3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014af8  nop
0x140014af9  xor     r8d, r8d
0x140014afc  mov     rdx, [rbp+70h+var_F0]
0x140014b00  lea     rcx, [rbp+70h+pExceptionObject]
0x140014b04  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x140014b09  mov     r15d, eax
0x140014b0c  test    eax, eax
0x140014b0e  jns     short loc_140014B77
0x140014b10  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b17  cmp     rcx, rsi
0x140014b1a  jz      short loc_140014B3B
0x140014b1c  test    [rcx+1Ch], bl
0x140014b1f  jz      short loc_140014B3B
0x140014b21  cmp     byte ptr [rcx+19h], 2
0x140014b25  jb      short loc_140014B3B
0x140014b27  mov     edx, 3Ch ; '<'
0x140014b2c  mov     r9d, eax
0x140014b2f  mov     r8, r14
0x140014b32  mov     rcx, [rcx+10h]
0x140014b36  call    WPP_SF_d
0x140014b3b  lea     rax, word_14003838A
0x140014b42  mov     [rsp+170h+var_118], rax
0x140014b47  xor     eax, eax
0x140014b49  mov     [rsp+170h+var_110], rax
0x140014b4e  mov     [rsp+170h+var_108], rax
0x140014b53  mov     [rsp+170h+var_100], r15d
0x140014b58  mov     [rsp+170h+var_FC], 0FFFFFFFFFFFFFFFFh
0x140014b61  mov     [rsp+170h+var_F4], al
0x140014b65  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014b6c  lea     rcx, [rsp+170h+var_118]; pExceptionObject
0x140014b71  call    _CxxThrowException_0
0x140014b77  mov     rdx, [rbp+70h+pExceptionObject]; lpValueName
0x140014b7b  mov     rcx, [rsp+170h+hKey]; hKey
0x140014b80  call    cs:__imp_RegDeleteValueW
0x140014b86  mov     rdx, [rbp+70h+lpSubKey]; lpSubKey
0x140014b8a  cmp     rdx, [rbp+70h+var_68]
0x140014b8e  jz      loc_140014C5F
0x140014b94  xor     r15d, r15d
0x140014b97  mov     [rsp+170h+pcbData], r15d
0x140014b9c  mov     [rsp+170h+hkey], r15
0x140014ba1  lea     rax, [rsp+170h+hkey]
0x140014ba6  mov     [rsp+170h+lpData], rax; __int64
0x140014bab  lea     r9, [rsp+170h+pcbData]; pcbData
0x140014bb0  mov     r8, [rbp+70h+pExceptionObject]; lpValue
0x140014bb4  mov     rcx, r12; hkey
0x140014bb7  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x140014bbc  test    eax, eax
0x140014bbe  jnz     loc_140014C54
0x140014bc4  cmp     [rsp+170h+pcbData], r15d
0x140014bc9  jbe     loc_140014C54
0x140014bcf  lea     rax, [rsp+170h+hkey]
0x140014bd4  mov     [rsp+170h+lpData], rax; __int64
0x140014bd9  lea     r9, [rsp+170h+pcbData]; pcbData
0x140014bde  lea     r8, a0811c1af7a074a; "0811c1af-7a07-4a06-82ed-869455cdf713"
0x140014be5  mov     rdx, [rbp+70h+lpSubKey]; lpSubKey
0x140014be9  mov     rcx, r12; hkey
0x140014bec  call    ?RegReadByteArrayValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; RegReadByteArrayValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &)
0x140014bf1  test    eax, eax
0x140014bf3  jnz     short loc_140014C54
0x140014bf5  mov     eax, [rsp+170h+pcbData]
0x140014bf9  test    eax, eax
0x140014bfb  jz      short loc_140014C54
0x140014bfd  mov     [rsp+170h+cbData], eax; cbData
0x140014c01  mov     rax, [rsp+170h+hkey]
0x140014c06  mov     [rsp+170h+lpData], rax; lpData
0x140014c0b  lea     r9d, [r15+3]; dwType
0x140014c0f  xor     r8d, r8d; Reserved
0x140014c12  mov     rdx, [rbp+70h+pExceptionObject]; lpValueName
0x140014c16  mov     rcx, [rsp+170h+hKey]; hKey
0x140014c1b  call    cs:__imp_RegSetValueExW
0x140014c21  test    eax, eax
0x140014c23  jz      short loc_140014C54
0x140014c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c2c  cmp     rcx, rsi
0x140014c2f  jz      short loc_140014C54
0x140014c31  test    [rcx+1Ch], bl
0x140014c34  jz      short loc_140014C54
0x140014c36  cmp     byte ptr [rcx+19h], 3
0x140014c3a  jb      short loc_140014C54
0x140014c3c  lea     edx, [r15+3Dh]
0x140014c40  mov     dword ptr [rsp+170h+lpData], eax
0x140014c44  mov     r9, [rbp+70h+pExceptionObject]
0x140014c48  mov     r8, r14
0x140014c4b  mov     rcx, [rcx+10h]
0x140014c4f  call    WPP_SF_SD
0x140014c54  lea     rcx, [rsp+170h+hkey]
0x140014c59  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x140014c5e  nop
0x140014c5f  lea     rcx, [rbp+70h+pExceptionObject]
0x140014c63  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014c68  nop
0x140014c69  mov     rcx, [rsp+170h+hKey]; hKey
0x140014c6e  xor     r12d, r12d
0x140014c71  test    rcx, rcx
0x140014c74  jz      short loc_140014C7D
0x140014c76  call    cs:__imp_RegCloseKey
0x140014c7c  nop
0x140014c7d  lea     rcx, [rbp+70h+lpSubKey]
0x140014c81  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014c86  nop
0x140014c87  lea     rcx, [rbp+70h+var_50]
0x140014c8b  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014c90  mov     qword ptr [rsp+170h+pcbData], r12
0x140014c95  lea     rcx, [rbp+70h+var_90]
0x140014c99  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014c9e  nop
0x140014c9f  lea     rcx, [rbp+70h+var_B0]
0x140014ca3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014ca8  nop
0x140014ca9  lea     r9, [rbp+70h+var_B0]
0x140014cad  lea     r8, [rbp+70h+var_90]
0x140014cb1  lea     rdx, [rsp+170h+pcbData]
0x140014cb6  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140014cbb  mov     r15d, eax
0x140014cbe  test    eax, eax
0x140014cc0  jns     short loc_140014D28
0x140014cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cc9  cmp     rcx, rsi
0x140014ccc  jz      short loc_140014CED
0x140014cce  test    [rcx+1Ch], bl
0x140014cd1  jz      short loc_140014CED
0x140014cd3  cmp     byte ptr [rcx+19h], 2
0x140014cd7  jb      short loc_140014CED
0x140014cd9  mov     edx, 3Eh ; '>'
0x140014cde  mov     r9d, eax
0x140014ce1  mov     r8, r14
0x140014ce4  mov     rcx, [rcx+10h]
0x140014ce8  call    WPP_SF_d
0x140014ced  lea     rax, word_14003838A
0x140014cf4  mov     [rsp+170h+var_118], rax
0x140014cf9  mov     [rsp+170h+var_110], r12
0x140014cfe  mov     [rsp+170h+var_108], r12
0x140014d03  mov     [rsp+170h+var_100], r15d
0x140014d08  mov     [rsp+170h+var_FC], 0FFFFFFFFFFFFFFFFh
0x140014d11  mov     [rsp+170h+var_F4], r12b
0x140014d16  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014d1d  lea     rcx, [rsp+170h+var_118]; pExceptionObject
0x140014d22  call    _CxxThrowException_0
0x140014d28  mov     [rsp+170h+hKey], r12
0x140014d2d  lea     rcx, [rsp+170h+hKey]
0x140014d32  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140014d37  mov     r12, [rbp+70h+var_C0]
0x140014d3b  mov     [rsp+170h+lpData], r12; void *
0x140014d40  mov     r9, rax; HKEY *
0x140014d43  mov     r8d, 2001Fh; unsigned int
0x140014d49  mov     rdx, [rbp+70h+var_90]; wchar_t *
0x140014d4d  mov     rcx, qword ptr [rsp+170h+pcbData]; HKEY
0x140014d52  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140014d57  mov     r15d, eax
0x140014d5a  test    eax, eax
0x140014d5c  jz      short loc_140014DB7
0x140014d5e  cmp     eax, 2
0x140014d61  jz      loc_140014E5C
0x140014d67  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d6e  cmp     rcx, rsi
0x140014d71  jz      short loc_140014D92
0x140014d73  test    [rcx+1Ch], bl
0x140014d76  jz      short loc_140014D92
0x140014d78  cmp     byte ptr [rcx+19h], 2
0x140014d7c  jb      short loc_140014D92
0x140014d7e  mov     edx, 3Fh ; '?'
0x140014d83  mov     r9d, eax
0x140014d86  mov     r8, r14
0x140014d89  mov     rcx, [rcx+10h]
0x140014d8d  call    WPP_SF_d
0x140014d92  mov     r9d, 404h; int
0x140014d98  mov     edx, r15d; unsigned int
0x140014d9b  lea     rcx, [rsp+170h+var_118]; this
0x140014da0  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140014da5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014dac  lea     rcx, [rsp+170h+var_118]; pExceptionObject
0x140014db1  call    _CxxThrowException_0
0x140014db7  mov     r8, r12; void *
0x140014dba  mov     rdx, r13; wchar_t *
0x140014dbd  mov     rcx, [rsp+170h+hKey]; HKEY
0x140014dc2  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x140014dc7  mov     r15d, eax
0x140014dca  test    eax, 0FFFFFFFDh
0x140014dcf  jz      short loc_140014E21
0x140014dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dd8  cmp     rcx, rsi
0x140014ddb  jz      short loc_140014DFC
0x140014ddd  test    [rcx+1Ch], bl
0x140014de0  jz      short loc_140014DFC
0x140014de2  cmp     byte ptr [rcx+19h], 2
0x140014de6  jb      short loc_140014DFC
0x140014de8  mov     edx, 40h ; '@'
0x140014ded  mov     r9d, eax
0x140014df0  mov     r8, r14
0x140014df3  mov     rcx, [rcx+10h]
0x140014df7  call    WPP_SF_d
0x140014dfc  mov     r9d, 40Ch; int
0x140014e02  mov     edx, r15d; unsigned int
0x140014e05  lea     rcx, [rsp+170h+var_118]; this
0x140014e0a  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140014e0f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140014e16  lea     rcx, [rsp+170h+var_118]; pExceptionObject
0x140014e1b  call    _CxxThrowException_0
0x140014e21  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e28  cmp     rcx, rsi
0x140014e2b  jz      short loc_140014E5C
0x140014e2d  test    [rcx+1Ch], bl
0x140014e30  jz      short loc_140014E5C
0x140014e32  cmp     byte ptr [rcx+19h], 5
0x140014e36  jb      short loc_140014E5C
0x140014e38  mov     edx, 41h ; 'A'
0x140014e3d  mov     rax, [rbp+70h+var_90]
0x140014e41  mov     qword ptr [rsp+170h+cbData], rax
0x140014e46  mov     rax, [rbp+70h+var_F0]
  ... truncated ...
```
