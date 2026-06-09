# SessionConfig::DeleteProvider(_GUID const &,void *)

- ea: `0x14001e458`
- end: `0x14001eb93`
- name: `?DeleteProvider@SessionConfig@@SAXAEBU_GUID@@PEAX@Z`
- size: `1851`
- prototype: `static void(const struct _GUID *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x14001e0c0`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140006db0`
- `0x140007d00`
- `0x140007fd0`
- `0x140008be0`
- `0x140009860`
- `0x14000a4d8`
- `0x140018e60`
- `0x14001e458`
- `0x140021b00`
- `0x140022cec`
- `0x14002e930`
- `0x14002e9bc`
- `0x14002f0d8`
- `0x14002f198`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e74a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001eb34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001eb44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e74a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e770`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001ea57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001eb34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001eb44`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001e6f3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001e6f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001e9a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001e9a7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001e6eb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001e6eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall SessionConfig::DeleteProvider(const struct _GUID *a1, void *a2)
{
  __int64 v4; // r8
  int v5; // eax
  int v6; // edi
  __int64 v7; // rcx
  int AutoLoggersRegPath; // eax
  int v9; // edi
  HKEY *v10; // rax
  unsigned int v11; // eax
  const char *v12; // r8
  unsigned int v13; // edi
  LSTATUS v14; // eax
  int v15; // r8d
  HKEY *v16; // rax
  unsigned int v17; // eax
  const char *v18; // r8
  unsigned int v19; // edi
  HKEY *v20; // rax
  unsigned int PersistedAutoLoggerRegPath; // eax
  unsigned int v22; // edi
  HKEY *v23; // rax
  HKEY *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // edi
  HKEY v27; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v29; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+74h] [rbp-8Ch]
  char v35; // [rsp+7Ch] [rbp-84h]
  __int16 *v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  unsigned int v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+9Ch] [rbp-64h]
  char v41; // [rsp+A4h] [rbp-5Ch]
  HKEY v42; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v44[2]; // [rsp+C0h] [rbp-40h] BYREF
  HKEY v45[2]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v47[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v48[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v49[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v50[2]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t *v51[4]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v52[4]; // [rsp+160h] [rbp+60h] BYREF
  HKEY v53[2]; // [rsp+180h] [rbp+80h] BYREF
  HKEY v54; // [rsp+190h] [rbp+90h]
  HKEY v55; // [rsp+198h] [rbp+98h]
  int v56; // [rsp+1A0h] [rbp+A0h]
  int v57; // [rsp+1A4h] [rbp+A4h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  LOBYTE(v4) = 1;
  v5 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey, a1, v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        (unsigned int)v5);
    }
    pExceptionObject = (const wchar_t *)word_14003838A;
    v31 = 0;
    v32 = 0;
    v33 = v6;
    v34 = -1;
    v35 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v29 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v51);
  AutoLoggersRegPath = RegistryPaths::GetAutoLoggersRegPath(v7, &v29, v52, v51);
  v9 = AutoLoggersRegPath;
  if ( AutoLoggersRegPath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
        (unsigned int)AutoLoggersRegPath);
    }
    pExceptionObject = (const wchar_t *)word_14003838A;
    v31 = 0;
    v32 = 0;
    v33 = v9;
    v34 = -1;
    v35 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v27 = 0;
  v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v27);
  v11 = OpenRegKey(v29, v52[0], 0x20019u, v10, a2);
  v13 = v11;
  if ( v11 )
  {
    if ( v11 != 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v11);
      }
      EvtException::EvtException((EvtException *)&v36, v13, v12, 847);
      throw (EvtException *)&v36;
    }
  }
  else
  {
    RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v53, v27, a2);
    v56 = v57;
    while ( !RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v53) )
    {
      v44[0] = v54;
      v44[1] = v55;
      v45[0] = (HKEY)L"EventLog-";
      v45[1] = (HKEY)9;
      if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                              v44,
                              v45) )
      {
        RegistryKeyEnumerator::GetCurrentSubKey(v53, &hKey);
        if ( a2 == (void *)-1LL )
          v14 = RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
        else
          v14 = RegDeleteKeyTransactedW(hKey, lpSubKey[0], 0, 0, a2, 0);
        if ( !v14
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v43[0] = v54;
          v43[1] = v55;
          WPP_SF__guid__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v55, v15, (_DWORD)a1, (__int64)v43);
        }
        if ( hKey )
          RegCloseKey(hKey);
      }
    }
    if ( v53[0] )
      RegCloseKey(v53[0]);
  }
  if ( v27 )
    RegCloseKey(v27);
  if ( v51[0] != v51[1] )
  {
    v43[0] = 0;
    v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v43);
    v17 = OpenRegKey(v29, v51[0], 0x20019u, v16, a2);
    v19 = v17;
    if ( v17 )
    {
      if ( v17 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v17);
        }
        EvtException::EvtException((EvtException *)&v36, v19, v18, 892);
        throw (EvtException *)&v36;
      }
    }
    else
    {
      RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v53, v43[0], a2);
      v56 = v57;
      while ( !RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v53) )
      {
        v48[0] = v54;
        v48[1] = v55;
        v47[0] = L"EventLog-";
        v47[1] = 9;
        if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                                v48,
                                v47) )
        {
          RegistryKeyEnumerator::GetCurrentSubKey(v53, v45);
          v44[0] = 0;
          v20 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v44);
          if ( !OpenRegKey(v45[0], lpSubKey[0], 0x20019u, v20, a2) )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
            v49[0] = v54;
            v49[1] = v55;
            PersistedAutoLoggerRegPath = RegistryPaths::GetPersistedAutoLoggerRegPath(v55, v49, &v29, &pExceptionObject);
            v22 = PersistedAutoLoggerRegPath;
            if ( PersistedAutoLoggerRegPath )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  55,
                  &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
                  PersistedAutoLoggerRegPath);
              }
              v36 = word_14003838A;
              v37 = 0;
              v38 = 0;
              v39 = v22;
              v40 = -1;
              v41 = 0;
              throw (EvtException *)&v36;
            }
            v42 = 0;
            v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v42);
            if ( !CreateRegKey(v29, pExceptionObject, 0x2001Fu, 0, v23, 0, a2) )
            {
              v27 = 0;
              v24 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v27);
              if ( !CreateRegKey(v42, lpSubKey[0], 0x2001Fu, 0, v24, 0, a2) )
              {
                LODWORD(hKey) = 0;
                v25 = RegSetValueExW(v27, L"Enabled", 0, v22 + 4, (const BYTE *)&hKey, 4u);
                v26 = v25;
                if ( v25 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      56,
                      &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
                      v25);
                  }
                  v36 = word_14003838A;
                  v37 = 0;
                  v38 = 0;
                  v39 = v26;
                  v40 = -1;
                  v41 = 0;
                  throw (EvtException *)&v36;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  v50[0] = (__int64)v54;
                  v50[1] = (__int64)v55;
                  WPP_SF__guid__utlwsv_SS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (__int64)v50,
                    (__int64)pExceptionObject,
                    (__int64)lpSubKey[0]);
                }
              }
              if ( v27 )
                RegCloseKey(v27);
            }
            if ( v42 )
              RegCloseKey(v42);
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
          }
          if ( v44[0] )
            RegCloseKey(v44[0]);
          if ( v45[0] )
            RegCloseKey(v45[0]);
        }
      }
      if ( v53[0] )
        RegCloseKey(v53[0]);
    }
    if ( v43[0] )
      RegCloseKey(v43[0]);
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v51);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
}

```

## disassembly

```asm
0x14001e458  mov     [rsp-8+arg_10], rbx
0x14001e45d  mov     [rsp-8+arg_18], rsi
0x14001e462  push    rbp
0x14001e463  push    rdi
0x14001e464  push    r13
0x14001e466  push    r14
0x14001e468  push    r15
0x14001e46a  lea     rbp, [rsp-2C0h]
0x14001e472  sub     rsp, 3C0h
0x14001e479  mov     rax, cs:__security_cookie
0x14001e480  xor     rax, rsp
0x14001e483  mov     [rbp+2E0h+var_30], rax
0x14001e48a  mov     rsi, rdx
0x14001e48d  mov     r14, rcx
0x14001e490  lea     rcx, [rbp+2E0h+lpSubKey]
0x14001e494  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e499  nop
0x14001e49a  mov     r8b, 1
0x14001e49d  mov     rdx, r14
0x14001e4a0  lea     rcx, [rbp+2E0h+lpSubKey]
0x14001e4a4  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x14001e4a9  mov     edi, eax
0x14001e4ab  xor     r15d, r15d
0x14001e4ae  test    eax, eax
0x14001e4b0  jns     short loc_14001E522
0x14001e4b2  lea     rbx, WPP_GLOBAL_Control
0x14001e4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4c0  cmp     rcx, rbx
0x14001e4c3  jz      short loc_14001E4E8
0x14001e4c5  test    byte ptr [rcx+1Ch], 4
0x14001e4c9  jz      short loc_14001E4E8
0x14001e4cb  cmp     byte ptr [rcx+19h], 2
0x14001e4cf  jb      short loc_14001E4E8
0x14001e4d1  lea     edx, [r15+32h]
0x14001e4d5  mov     r9d, eax
0x14001e4d8  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001e4df  mov     rcx, [rcx+10h]
0x14001e4e3  call    WPP_SF_d
0x14001e4e8  lea     rax, word_14003838A
0x14001e4ef  mov     [rsp+3E0h+pExceptionObject], rax
0x14001e4f4  mov     [rsp+3E0h+var_380], r15
0x14001e4f9  mov     [rsp+3E0h+var_378], r15
0x14001e4fe  mov     [rsp+3E0h+var_370], edi
0x14001e502  mov     [rsp+3E0h+var_36C], 0FFFFFFFFFFFFFFFFh
0x14001e50b  mov     [rsp+3E0h+var_364], r15b
0x14001e510  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001e517  lea     rcx, [rsp+3E0h+pExceptionObject]; pExceptionObject
0x14001e51c  call    _CxxThrowException_0
0x14001e522  mov     [rsp+3E0h+var_390], r15
0x14001e527  lea     rcx, [rbp+2E0h+var_280]
0x14001e52b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e530  nop
0x14001e531  lea     rcx, [rbp+2E0h+var_2A0]
0x14001e535  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e53a  nop
0x14001e53b  lea     r9, [rbp+2E0h+var_2A0]
0x14001e53f  lea     r8, [rbp+2E0h+var_280]
0x14001e543  lea     rdx, [rsp+3E0h+var_390]
0x14001e548  call    ?GetAutoLoggersRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetAutoLoggersRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001e54d  mov     edi, eax
0x14001e54f  test    eax, eax
0x14001e551  jns     short loc_14001E5C4
0x14001e553  lea     rbx, WPP_GLOBAL_Control
0x14001e55a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e561  cmp     rcx, rbx
0x14001e564  jz      short loc_14001E58A
0x14001e566  test    byte ptr [rcx+1Ch], 4
0x14001e56a  jz      short loc_14001E58A
0x14001e56c  cmp     byte ptr [rcx+19h], 2
0x14001e570  jb      short loc_14001E58A
0x14001e572  mov     edx, 33h ; '3'
0x14001e577  mov     r9d, eax
0x14001e57a  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001e581  mov     rcx, [rcx+10h]
0x14001e585  call    WPP_SF_d
0x14001e58a  lea     rax, word_14003838A
0x14001e591  mov     [rsp+3E0h+pExceptionObject], rax
0x14001e596  mov     [rsp+3E0h+var_380], r15
0x14001e59b  mov     [rsp+3E0h+var_378], r15
0x14001e5a0  mov     [rsp+3E0h+var_370], edi
0x14001e5a4  mov     [rsp+3E0h+var_36C], 0FFFFFFFFFFFFFFFFh
0x14001e5ad  mov     [rsp+3E0h+var_364], r15b
0x14001e5b2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001e5b9  lea     rcx, [rsp+3E0h+pExceptionObject]; pExceptionObject
0x14001e5be  call    _CxxThrowException_0
0x14001e5c4  mov     [rsp+3E0h+var_3A0], r15
0x14001e5c9  lea     rcx, [rsp+3E0h+var_3A0]
0x14001e5ce  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e5d3  mov     [rsp+3E0h+hTransaction], rsi; void *
0x14001e5d8  mov     r9, rax; HKEY *
0x14001e5db  mov     r8d, 20019h; unsigned int
0x14001e5e1  mov     rdx, [rbp+2E0h+var_280]; wchar_t *
0x14001e5e5  mov     rcx, [rsp+3E0h+var_390]; HKEY
0x14001e5ea  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14001e5ef  mov     edi, eax
0x14001e5f1  lea     rbx, WPP_GLOBAL_Control
0x14001e5f8  lea     r13, aEventlog; "EventLog-"
0x14001e5ff  test    eax, eax
0x14001e601  jz      short loc_14001E65E
0x14001e603  cmp     eax, 2
0x14001e606  jz      loc_14001E777
0x14001e60c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e613  cmp     rcx, rbx
0x14001e616  jz      short loc_14001E63C
0x14001e618  test    byte ptr [rcx+1Ch], 4
0x14001e61c  jz      short loc_14001E63C
0x14001e61e  cmp     byte ptr [rcx+19h], 2
0x14001e622  jb      short loc_14001E63C
0x14001e624  mov     edx, 34h ; '4'
0x14001e629  mov     r9d, eax
0x14001e62c  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001e633  mov     rcx, [rcx+10h]
0x14001e637  call    WPP_SF_d
0x14001e63c  mov     r9d, 34Fh; int
0x14001e642  mov     edx, edi; unsigned int
0x14001e644  lea     rcx, [rbp+2E0h+var_360]; this
0x14001e648  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001e64d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001e654  lea     rcx, [rbp+2E0h+var_360]; pExceptionObject
0x14001e658  call    _CxxThrowException_0
0x14001e65e  mov     r8, rsi; void *
0x14001e661  mov     rdx, [rsp+3E0h+var_3A0]; HKEY
0x14001e666  lea     rcx, [rbp+2E0h+var_260]; this
0x14001e66d  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEAX@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,void *)
0x14001e672  nop
0x14001e673  mov     eax, [rbp+2E0h+var_23C]
0x14001e679  mov     [rbp+2E0h+var_240], eax
0x14001e67f  jmp     loc_14001E750
0x14001e684  mov     rax, [rbp+2E0h+var_250]
0x14001e68b  mov     rcx, [rbp+2E0h+var_248]
0x14001e692  mov     [rbp+2E0h+var_320], rax
0x14001e696  mov     [rbp+2E0h+var_318], rcx
0x14001e69a  mov     [rbp+2E0h+var_310], r13
0x14001e69e  mov     [rbp+2E0h+var_308], 9
0x14001e6a6  lea     rdx, [rbp+2E0h+var_310]
0x14001e6aa  lea     rcx, [rbp+2E0h+var_320]
0x14001e6ae  call    ?starts_with@?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@QEBA_NV12@@Z; utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x14001e6b3  test    al, al
0x14001e6b5  jz      loc_14001E750
0x14001e6bb  lea     rdx, [rsp+3E0h+hKey]
0x14001e6c0  lea     rcx, [rbp+2E0h+var_260]
0x14001e6c7  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x14001e6cc  xor     r9d, r9d; Reserved
0x14001e6cf  xor     r8d, r8d; samDesired
0x14001e6d2  mov     rdx, [rbp+2E0h+lpSubKey]; lpSubKey
0x14001e6d6  mov     rcx, [rsp+3E0h+hKey]; hKey
0x14001e6db  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14001e6df  jz      short loc_14001E6F3
0x14001e6e1  mov     [rsp+3E0h+pExtendedParameter], r15; pExtendedParameter
0x14001e6e6  mov     [rsp+3E0h+hTransaction], rsi; hTransaction
0x14001e6eb  call    cs:__imp_RegDeleteKeyTransactedW
0x14001e6f1  jmp     short loc_14001E6F9
0x14001e6f3  call    cs:__imp_RegDeleteKeyExW
0x14001e6f9  test    eax, eax
0x14001e6fb  jnz     short loc_14001E740
0x14001e6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e704  cmp     rcx, rbx
0x14001e707  jz      short loc_14001E740
0x14001e709  test    byte ptr [rcx+1Ch], 4
0x14001e70d  jz      short loc_14001E740
0x14001e70f  cmp     byte ptr [rcx+19h], 5
0x14001e713  jb      short loc_14001E740
0x14001e715  mov     rax, [rbp+2E0h+var_250]
0x14001e71c  mov     rdx, [rbp+2E0h+var_248]
0x14001e723  mov     [rbp+2E0h+var_330], rax
0x14001e727  mov     [rbp+2E0h+var_328], rdx
0x14001e72b  lea     rax, [rbp+2E0h+var_330]
0x14001e72f  mov     [rsp+3E0h+hTransaction], rax
0x14001e734  mov     r9, r14
0x14001e737  mov     rcx, [rcx+10h]
0x14001e73b  call    WPP_SF__guid__utlwsv_
0x14001e740  mov     rcx, [rsp+3E0h+hKey]; hKey
0x14001e745  test    rcx, rcx
0x14001e748  jz      short loc_14001E750
0x14001e74a  call    cs:__imp_RegCloseKey
0x14001e750  lea     rcx, [rbp+2E0h+var_260]; this
0x14001e757  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14001e75c  test    eax, eax
0x14001e75e  jz      loc_14001E684
0x14001e764  mov     rcx, [rbp+2E0h+var_260]; hKey
0x14001e76b  test    rcx, rcx
0x14001e76e  jz      short loc_14001E777
0x14001e770  call    cs:__imp_RegCloseKey
0x14001e776  nop
0x14001e777  mov     rcx, [rsp+3E0h+var_3A0]; hKey
0x14001e77c  test    rcx, rcx
0x14001e77f  jz      short loc_14001E787
0x14001e781  call    cs:__imp_RegCloseKey
0x14001e787  mov     rax, [rbp+2E0h+var_298]
0x14001e78b  cmp     [rbp+2E0h+var_2A0], rax
0x14001e78f  jz      loc_14001EB4B
0x14001e795  mov     [rbp+2E0h+var_330], r15
0x14001e799  lea     rcx, [rbp+2E0h+var_330]
0x14001e79d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e7a2  mov     [rsp+3E0h+hTransaction], rsi; void *
0x14001e7a7  mov     r9, rax; HKEY *
0x14001e7aa  mov     r8d, 20019h; unsigned int
0x14001e7b0  mov     rdx, [rbp+2E0h+var_2A0]; wchar_t *
0x14001e7b4  mov     rcx, [rsp+3E0h+var_390]; HKEY
0x14001e7b9  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14001e7be  mov     edi, eax
0x14001e7c0  test    eax, eax
0x14001e7c2  jz      short loc_14001E81F
0x14001e7c4  cmp     eax, 2
0x14001e7c7  jz      loc_14001EB3B
0x14001e7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7d4  cmp     rcx, rbx
0x14001e7d7  jz      short loc_14001E7FD
0x14001e7d9  test    byte ptr [rcx+1Ch], 4
0x14001e7dd  jz      short loc_14001E7FD
0x14001e7df  cmp     byte ptr [rcx+19h], 2
0x14001e7e3  jb      short loc_14001E7FD
0x14001e7e5  mov     edx, 36h ; '6'
0x14001e7ea  mov     r9d, eax
0x14001e7ed  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14001e7f4  mov     rcx, [rcx+10h]
0x14001e7f8  call    WPP_SF_d
0x14001e7fd  mov     r9d, 37Ch; int
0x14001e803  mov     edx, edi; unsigned int
0x14001e805  lea     rcx, [rbp+2E0h+var_360]; this
0x14001e809  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001e80e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001e815  lea     rcx, [rbp+2E0h+var_360]; pExceptionObject
0x14001e819  call    _CxxThrowException_0
0x14001e81f  mov     r8, rsi; void *
0x14001e822  mov     rdx, [rbp+2E0h+var_330]; HKEY
0x14001e826  lea     rcx, [rbp+2E0h+var_260]; this
0x14001e82d  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEAX@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,void *)
0x14001e832  nop
0x14001e833  mov     eax, [rbp+2E0h+var_23C]
0x14001e839  mov     [rbp+2E0h+var_240], eax
0x14001e83f  lea     rcx, [rbp+2E0h+var_260]; this
0x14001e846  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14001e84b  test    eax, eax
0x14001e84d  jnz     loc_14001EB28
0x14001e853  mov     rax, [rbp+2E0h+var_250]
0x14001e85a  mov     rcx, [rbp+2E0h+var_248]
0x14001e861  mov     [rbp+2E0h+var_2D0], rax
0x14001e865  mov     [rbp+2E0h+var_2C8], rcx
0x14001e869  mov     [rbp+2E0h+var_2E0], r13
0x14001e86d  mov     [rbp+2E0h+var_2D8], 9
0x14001e875  lea     rdx, [rbp+2E0h+var_2E0]
0x14001e879  lea     rcx, [rbp+2E0h+var_2D0]
0x14001e87d  call    ?starts_with@?$basic_string_view@_WU?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@QEBA_NV12@@Z; utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>)
0x14001e882  test    al, al
0x14001e884  jz      short loc_14001E83F
0x14001e886  lea     rdx, [rbp+2E0h+var_310]
0x14001e88a  lea     rcx, [rbp+2E0h+var_260]
0x14001e891  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x14001e896  nop
0x14001e897  mov     [rbp+2E0h+var_320], r15
0x14001e89b  lea     rcx, [rbp+2E0h+var_320]
0x14001e89f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e8a4  mov     [rsp+3E0h+hTransaction], rsi; void *
0x14001e8a9  mov     r9, rax; HKEY *
0x14001e8ac  mov     r8d, 20019h; unsigned int
0x14001e8b2  mov     rdx, [rbp+2E0h+lpSubKey]; wchar_t *
0x14001e8b6  mov     rcx, [rbp+2E0h+var_310]; HKEY
0x14001e8ba  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14001e8bf  test    eax, eax
0x14001e8c1  jnz     loc_14001EA3A
0x14001e8c7  lea     rcx, [rsp+3E0h+pExceptionObject]
0x14001e8cc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e8d1  nop
0x14001e8d2  mov     rax, [rbp+2E0h+var_250]
0x14001e8d9  mov     rcx, [rbp+2E0h+var_248]
0x14001e8e0  mov     [rbp+2E0h+var_2C0], rax
0x14001e8e4  mov     [rbp+2E0h+var_2B8], rcx
0x14001e8e8  lea     r9, [rsp+3E0h+pExceptionObject]
0x14001e8ed  lea     r8, [rsp+3E0h+var_390]
0x14001e8f2  lea     rdx, [rbp+2E0h+var_2C0]
0x14001e8f6  call    ?GetPersistedAutoLoggerRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetPersistedAutoLoggerRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001e8fb  mov     edi, eax
0x14001e8fd  test    eax, eax
0x14001e8ff  jnz     loc_14001EAC5
0x14001e905  mov     [rbp+2E0h+var_338], r15
0x14001e909  lea     rcx, [rbp+2E0h+var_338]
0x14001e90d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e912  mov     [rsp+3E0h+var_3B0], rsi; void *
0x14001e917  mov     [rsp+3E0h+pExtendedParameter], r15; unsigned int *
0x14001e91c  mov     [rsp+3E0h+hTransaction], rax; HKEY *
0x14001e921  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x14001e924  mov     r8d, 2001Fh; unsigned int
0x14001e92a  mov     rdx, [rsp+3E0h+pExceptionObject]; wchar_t *
0x14001e92f  mov     rcx, [rsp+3E0h+var_390]; HKEY
0x14001e934  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x14001e939  test    eax, eax
0x14001e93b  jnz     loc_14001EA1F
0x14001e941  mov     [rsp+3E0h+var_3A0], r15
0x14001e946  lea     rcx, [rsp+3E0h+var_3A0]
0x14001e94b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e950  mov     [rsp+3E0h+var_3B0], rsi; void *
0x14001e955  mov     [rsp+3E0h+pExtendedParameter], r15; unsigned int *
0x14001e95a  mov     [rsp+3E0h+hTransaction], rax; HKEY *
0x14001e95f  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x14001e962  mov     r8d, 2001Fh; unsigned int
0x14001e968  mov     rdx, [rbp+2E0h+lpSubKey]; wchar_t *
0x14001e96c  mov     rcx, [rbp+2E0h+var_338]; HKEY
0x14001e970  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x14001e975  test    eax, eax
  ... truncated ...
```
