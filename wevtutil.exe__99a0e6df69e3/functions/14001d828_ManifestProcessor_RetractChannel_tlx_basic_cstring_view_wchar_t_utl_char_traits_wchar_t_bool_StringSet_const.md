# ManifestProcessor::RetractChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,StringSet const &)

- ea: `0x14001d828`
- end: `0x14001e023`
- name: `?RetractChannel@ManifestProcessor@@AEAAXV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_NAEBVStringSet@@@Z`
- size: `2043`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x14000a6a0`
- `0x14001e0c0`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140006008`
- `0x1400098cc`
- `0x14000d62c`
- `0x14000d6e8`
- `0x140019094`
- `0x140019348`
- `0x14001a814`
- `0x14001a9b8`
- `0x14001d828`
- `0x14001e02c`
- `0x140022cec`
- `0x140023c6c`
- `0x14002a0ec`
- `0x14002ba08`
- `0x14002ddb0`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001db70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001dd0d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001db70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001dd0d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001db68`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001dd05`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001db68`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x14001dd05`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
PVOID *__fastcall ManifestProcessor::RetractChannel(HKEY a1, _QWORD *a2, char a3, __int64 a4)
{
  PVOID *v8; // rbx
  PVOID *result; // rax
  __int64 v10; // r13
  __int64 v11; // r12
  const char *v12; // r8
  __int64 v13; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v15; // r15d
  const char *v16; // r8
  void *hTransaction; // rax
  LSTATUS v18; // eax
  LSTATUS v19; // r15d
  PVOID v20; // rcx
  const char *v21; // r8
  unsigned int LegacyChannelRegPath; // eax
  unsigned int v23; // r15d
  void *v24; // rax
  LSTATUS v25; // eax
  LSTATUS v26; // r15d
  const char *v27; // r8
  __int64 v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // r14d
  const char *v31; // r8
  char v32; // al
  __int128 v33; // [rsp+30h] [rbp-288h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+40h] [rbp-278h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-258h]
  __int64 v36; // [rsp+68h] [rbp-250h]
  __int64 v37; // [rsp+70h] [rbp-248h]
  __int64 v38; // [rsp+78h] [rbp-240h]
  _QWORD v39[3]; // [rsp+80h] [rbp-238h] BYREF
  unsigned int v40; // [rsp+98h] [rbp-220h]
  __int64 v41; // [rsp+9Ch] [rbp-21Ch]
  char v42; // [rsp+A4h] [rbp-214h]
  _QWORD v43[3]; // [rsp+A8h] [rbp-210h] BYREF
  unsigned int v44; // [rsp+C0h] [rbp-1F8h]
  __int64 v45; // [rsp+C4h] [rbp-1F4h]
  char v46; // [rsp+CCh] [rbp-1ECh]
  _QWORD v47[3]; // [rsp+D0h] [rbp-1E8h] BYREF
  unsigned int v48; // [rsp+E8h] [rbp-1D0h]
  __int64 v49; // [rsp+ECh] [rbp-1CCh]
  char v50; // [rsp+F4h] [rbp-1C4h]
  EvtException *v51; // [rsp+F8h] [rbp-1C0h] BYREF
  _BYTE v52[32]; // [rsp+100h] [rbp-1B8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+120h] [rbp-198h] BYREF
  _BYTE v54[40]; // [rsp+148h] [rbp-170h] BYREF
  _BYTE v55[40]; // [rsp+170h] [rbp-148h] BYREF
  _BYTE v56[40]; // [rsp+198h] [rbp-120h] BYREF
  _BYTE v57[48]; // [rsp+1C0h] [rbp-F8h] BYREF
  _BYTE v58[136]; // [rsp+1F0h] [rbp-C8h] BYREF
  int v59; // [rsp+278h] [rbp-40h]
  HKEY hKey; // [rsp+2C0h] [rbp+8h] BYREF
  _QWORD *v61; // [rsp+2C8h] [rbp+10h]
  __int64 v62; // [rsp+2D8h] [rbp+20h]

  v62 = a4;
  v61 = a2;
  hKey = a1;
  v35 = a1 + 10;
  v8 = (PVOID *)*((_QWORD *)a1 + 5);
  result = (PVOID *)utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(v8);
  if ( result != v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      return (PVOID *)WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        74,
                        &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids);
    }
    return result;
  }
  v36 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(a4);
  v10 = a2[1];
  v38 = v10;
  v11 = *a2;
  v37 = v11;
  *(_QWORD *)&v33 = v11;
  *((_QWORD *)&v33 + 1) = v10;
  result = (PVOID *)IsCoreChannel(&v33);
  try
  {
    if ( !(_BYTE)result )
    {
      if ( a3 )
        return result;
      if ( a4 != v36 && *(_BYTE *)a1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids);
        }
        *(_QWORD *)&v33 = v11;
        *((_QWORD *)&v33 + 1) = v10;
        ChannelConfigReader::ChannelConfigReader((__int64)v58, &v33, *((_QWORD *)a1 + 1));
        if ( (unsigned int)(v59 - 2) <= 1 )
        {
          utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
            *v35,
            &v33,
            a2);
          if ( !(_QWORD)v33 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v12, 1291);
            throw (EvtException *)pExceptionObject;
          }
        }
        ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v58);
      }
      *(_QWORD *)&v33 = v11;
      *((_QWORD *)&v33 + 1) = v10;
      result = (PVOID *)SessionConfig::DeleteChannel(&v33, *((_QWORD *)a1 + 1));
      if ( a4 != v36 )
        return result;
      hKey = 0;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
      WinevtRegPath = RegistryPaths::GetWinevtRegPath(v13, &hKey, lpSubKey, v52);
      v15 = WinevtRegPath;
      if ( WinevtRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
            WinevtRegPath);
        }
        v39[0] = word_14003838A;
        v39[1] = 0;
        v39[2] = 0;
        v40 = v15;
        v41 = -1;
        v42 = 0;
        throw (EvtException *)v39;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               lpSubKey,
                               L"\\Channels\\",
                               10)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               lpSubKey,
                               v11,
                               v10) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)v56, 0xEu, v16, 1319);
        throw (EvtException *)v56;
      }
      hTransaction = (void *)*((_QWORD *)a1 + 1);
      if ( hTransaction == (void *)-1LL )
        v18 = RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
      else
        v18 = RegDeleteKeyTransactedW(hKey, lpSubKey[0], 0, 0, hTransaction, 0);
      v19 = v18;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
          lpSubKey[0],
          v18);
      }
      if ( !v19 )
      {
        if ( *(_BYTE *)a1 )
        {
          utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
            *v35,
            &v33,
            a2);
          if ( !(_QWORD)v33 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)v54, 0xEu, v21, 1338);
            throw (EvtException *)v54;
          }
        }
      }
      *(_QWORD *)&v33 = v11;
      *((_QWORD *)&v33 + 1) = v10;
      LegacyChannelRegPath = RegistryPaths::GetLegacyChannelRegPath(v20, &v33, &hKey, lpSubKey);
      v23 = LegacyChannelRegPath;
      if ( LegacyChannelRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            81,
            &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
            LegacyChannelRegPath);
        }
        v43[0] = word_14003838A;
        v43[1] = 0;
        v43[2] = 0;
        v44 = v23;
        v45 = -1;
        v46 = 0;
        throw (EvtException *)v43;
      }
      v24 = (void *)*((_QWORD *)a1 + 1);
      if ( v24 == (void *)-1LL )
        v25 = RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
      else
        v25 = RegDeleteKeyTransactedW(hKey, lpSubKey[0], 0, 0, v24, 0);
      v26 = v25;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
          lpSubKey[0],
          v25);
      }
      if ( !v26 )
      {
        if ( *(_BYTE *)a1 )
        {
          utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
            *v35,
            &v33,
            a2);
          if ( !(_QWORD)v33 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)v55, 0xEu, v27, 1359);
            throw (EvtException *)v55;
          }
        }
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v52);
      goto LABEL_89;
    }
    if ( a3 )
    {
      result = (PVOID *)*((_QWORD *)a1 + 7);
      if ( *((PVOID **)a1 + 6) != result )
      {
        hKey = 0;
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
        *(_QWORD *)&v33 = v11;
        *((_QWORD *)&v33 + 1) = v10;
        v29 = RegistryPaths::GetLegacyChannelRegPath(v28, &v33, &hKey, lpSubKey);
        v30 = v29;
        if ( v29 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v29);
          }
          v47[0] = word_14003838A;
          v47[1] = 0;
          v47[2] = 0;
          v48 = v30;
          v49 = -1;
          v50 = 0;
          throw (EvtException *)v47;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 lpSubKey,
                                 92)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 *((_QWORD *)a1 + 6),
                                 (__int64)(*((_QWORD *)a1 + 7) - *((_QWORD *)a1 + 6)) >> 1) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)v57, 0xEu, v31, 1376);
          throw (EvtException *)v57;
        }
        v32 = RegDeleteKeyRecursive(hKey, lpSubKey[0], *((void **)a1 + 1));
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
            lpSubKey[0],
            v32);
        }
LABEL_89:
        result = (PVOID *)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
      }
    }
  }
  catch ( EvtException *v51 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      return (PVOID *)WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        87,
                        &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
                        *((unsigned int *)v51 + 6));
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001d828  mov     [rsp+arg_18], r9
0x14001d82d  mov     [rsp+arg_8], rdx
0x14001d832  mov     [rsp+hKey], rcx
0x14001d837  push    rbx
0x14001d838  push    rsi
0x14001d839  push    rdi
0x14001d83a  push    r12
0x14001d83c  push    r13
0x14001d83e  push    r14
0x14001d840  push    r15
0x14001d842  sub     rsp, 280h
0x14001d849  mov     r15, r9
0x14001d84c  mov     dil, r8b
0x14001d84f  mov     r14, rdx
0x14001d852  mov     rsi, rcx
0x14001d855  lea     rax, [rcx+28h]
0x14001d859  mov     [rsp+2B8h+var_258], rax
0x14001d85e  mov     rbx, [rax]
0x14001d861  mov     rcx, rbx
0x14001d864  call    ??$_FindImpl@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x14001d869  cmp     rax, rbx
0x14001d86c  jz      short loc_14001D8AA
0x14001d86e  lea     rdi, WPP_GLOBAL_Control
0x14001d875  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d87c  cmp     rcx, rdi
0x14001d87f  jz      short loc_14001D8A5
0x14001d881  test    byte ptr [rcx+1Ch], 4
0x14001d885  jz      short loc_14001D8A5
0x14001d887  cmp     byte ptr [rcx+19h], 5
0x14001d88b  jb      short loc_14001D8A5
0x14001d88d  mov     edx, 4Ah ; 'J'
0x14001d892  mov     r9, [r14]
0x14001d895  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001d89c  mov     rcx, [rcx+10h]
0x14001d8a0  call    WPP_SF_S
0x14001d8a5  jmp     loc_14001E00F
0x14001d8aa  mov     rdx, r14
0x14001d8ad  mov     rcx, r15
0x14001d8b0  call    ??$_FindImpl@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x14001d8b5  mov     [rsp+2B8h+var_250], rax
0x14001d8ba  mov     r13, [r14+8]
0x14001d8be  mov     [rsp+2B8h+var_240], r13
0x14001d8c3  mov     r12, [r14]
0x14001d8c6  mov     [rsp+2B8h+var_248], r12
0x14001d8cb  mov     [rsp+2B8h+var_288], r12
0x14001d8d0  mov     [rsp+2B8h+var_280], r13
0x14001d8d5  lea     rcx, [rsp+2B8h+var_288]
0x14001d8da  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14001d8df  xor     ebx, ebx
0x14001d8e1  test    al, al
0x14001d8e3  jnz     loc_14001DE3F
0x14001d8e9  test    dil, dil
0x14001d8ec  jnz     loc_14001DFA8
0x14001d8f2  cmp     r15, [rsp+2B8h+var_250]
0x14001d8f7  jz      loc_14001DA18
0x14001d8fd  cmp     [rsi], bl
0x14001d8ff  jz      loc_14001DA18
0x14001d905  lea     rdi, WPP_GLOBAL_Control
0x14001d90c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d913  cmp     rcx, rdi
0x14001d916  jz      short loc_14001D93A
0x14001d918  test    byte ptr [rcx+1Ch], 4
0x14001d91c  jz      short loc_14001D93A
0x14001d91e  cmp     byte ptr [rcx+19h], 5
0x14001d922  jb      short loc_14001D93A
0x14001d924  lea     edx, [rbx+4Bh]
0x14001d927  mov     r9, r12
0x14001d92a  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001d931  mov     rcx, [rcx+10h]
0x14001d935  call    WPP_SF_S
0x14001d93a  mov     [rsp+2B8h+var_288], r12
0x14001d93f  mov     [rsp+2B8h+var_280], r13
0x14001d944  mov     r8, [rsi+8]
0x14001d948  lea     rdx, [rsp+2B8h+var_288]
0x14001d94d  lea     rcx, [rsp+2B8h+var_C8]
0x14001d955  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14001d95a  nop
0x14001d95b  mov     eax, [rsp+2B8h+var_40]
0x14001d962  add     eax, 0FFFFFFFEh
0x14001d965  cmp     eax, 1
0x14001d968  ja      short loc_14001D9E4
0x14001d96a  mov     r8, r14
0x14001d96d  lea     rdx, [rsp+2B8h+var_288]
0x14001d972  mov     rcx, [rsp+2B8h+var_258]
0x14001d977  mov     rcx, [rcx]
0x14001d97a  call    ??$emplace@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@_N@1@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &)
0x14001d97f  cmp     [rsp+2B8h+var_288], rbx
0x14001d984  jnz     short loc_14001D9E4
0x14001d986  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d98d  cmp     rcx, rdi
0x14001d990  jz      short loc_14001D9B7
0x14001d992  test    byte ptr [rcx+1Ch], 4
0x14001d996  jz      short loc_14001D9B7
0x14001d998  cmp     byte ptr [rcx+19h], 2
0x14001d99c  jb      short loc_14001D9B7
0x14001d99e  mov     edx, 4Ch ; 'L'
0x14001d9a3  lea     r9d, [rdx-3Eh]
0x14001d9a7  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001d9ae  mov     rcx, [rcx+10h]
0x14001d9b2  call    WPP_SF_d
0x14001d9b7  mov     edx, 0Eh; unsigned int
0x14001d9bc  mov     r9d, 50Bh; int
0x14001d9c2  lea     rcx, [rsp+2B8h+pExceptionObject]; this
0x14001d9ca  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001d9cf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d9d6  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x14001d9de  call    _CxxThrowException_0
0x14001d9e4  lea     rcx, [rsp+2B8h+var_C8]; this
0x14001d9ec  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x14001d9f1  nop
0x14001d9f2  jmp     short loc_14001DA1F
0x14001d9f4  xor     ebx, ebx
0x14001d9f6  mov     rsi, [rsp+2B8h+hKey]
0x14001d9fe  mov     r15, [rsp+2B8h+arg_18]
0x14001da06  mov     r14, [rsp+2B8h+arg_8]
0x14001da0e  mov     r12, [rsp+2B8h+var_248]
0x14001da13  mov     r13, [rsp+2B8h+var_240]
0x14001da18  lea     rdi, WPP_GLOBAL_Control
0x14001da1f  mov     [rsp+2B8h+var_288], r12
0x14001da24  mov     [rsp+2B8h+var_280], r13
0x14001da29  mov     rdx, [rsi+8]
0x14001da2d  lea     rcx, [rsp+2B8h+var_288]
0x14001da32  call    ?DeleteChannel@SessionConfig@@SAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; SessionConfig::DeleteChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14001da37  cmp     r15, [rsp+2B8h+var_250]
0x14001da3c  jnz     loc_14001DFA8
0x14001da42  mov     [rsp+2B8h+hKey], rbx
0x14001da4a  lea     rcx, [rsp+2B8h+lpSubKey]
0x14001da4f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001da54  nop
0x14001da55  lea     rcx, [rsp+2B8h+var_1B8]
0x14001da5d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001da62  nop
0x14001da63  lea     r9, [rsp+2B8h+var_1B8]
0x14001da6b  lea     r8, [rsp+2B8h+lpSubKey]
0x14001da70  lea     rdx, [rsp+2B8h+hKey]
0x14001da78  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001da7d  mov     r15d, eax
0x14001da80  test    eax, eax
0x14001da82  jz      loc_14001DB0A
0x14001da88  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da8f  cmp     rcx, rdi
0x14001da92  jz      short loc_14001DAB8
0x14001da94  test    byte ptr [rcx+1Ch], 4
0x14001da98  jz      short loc_14001DAB8
0x14001da9a  cmp     byte ptr [rcx+19h], 2
0x14001da9e  jb      short loc_14001DAB8
0x14001daa0  mov     edx, 4Dh ; 'M'
0x14001daa5  mov     r9d, eax
0x14001daa8  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001daaf  mov     rcx, [rcx+10h]
0x14001dab3  call    WPP_SF_d
0x14001dab8  lea     rax, word_14003838A
0x14001dabf  mov     [rsp+2B8h+var_238], rax
0x14001dac7  mov     [rsp+2B8h+var_230], rbx
0x14001dacf  mov     [rsp+2B8h+var_228], 0
0x14001dadb  mov     [rsp+2B8h+var_220], r15d
0x14001dae3  mov     [rsp+2B8h+var_21C], 0FFFFFFFFFFFFFFFFh
0x14001daef  mov     [rsp+2B8h+var_214], bl
0x14001daf6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001dafd  lea     rcx, [rsp+2B8h+var_238]; pExceptionObject
0x14001db05  call    _CxxThrowException_0
0x14001db0a  mov     r8d, 0Ah
0x14001db10  lea     rdx, aChannels_1; "\\Channels\\"
0x14001db17  lea     rcx, [rsp+2B8h+lpSubKey]
0x14001db1c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14001db21  test    al, al
0x14001db23  jz      loc_14001DDE1
0x14001db29  mov     r8, r13
0x14001db2c  mov     rdx, r12
0x14001db2f  lea     rcx, [rsp+2B8h+lpSubKey]
0x14001db34  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14001db39  test    al, al
0x14001db3b  jz      loc_14001DDE1
0x14001db41  mov     rax, [rsi+8]
0x14001db45  xor     r9d, r9d; Reserved
0x14001db48  xor     r8d, r8d; samDesired
0x14001db4b  mov     rdx, [rsp+2B8h+lpSubKey]; lpSubKey
0x14001db50  mov     rcx, [rsp+2B8h+hKey]; hKey
0x14001db58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001db5c  jz      short loc_14001DB70
0x14001db5e  mov     [rsp+2B8h+pExtendedParameter], rbx; pExtendedParameter
0x14001db63  mov     [rsp+2B8h+hTransaction], rax; hTransaction
0x14001db68  call    cs:__imp_RegDeleteKeyTransactedW
0x14001db6e  jmp     short loc_14001DB76
0x14001db70  call    cs:__imp_RegDeleteKeyExW
0x14001db76  mov     r15d, eax
0x14001db79  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db80  cmp     rcx, rdi
0x14001db83  jz      short loc_14001DBAF
0x14001db85  test    byte ptr [rcx+1Ch], 4
0x14001db89  jz      short loc_14001DBAF
0x14001db8b  cmp     byte ptr [rcx+19h], 5
0x14001db8f  jb      short loc_14001DBAF
0x14001db91  mov     edx, 4Fh ; 'O'
0x14001db96  mov     dword ptr [rsp+2B8h+hTransaction], eax
0x14001db9a  mov     r9, [rsp+2B8h+lpSubKey]
0x14001db9f  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001dba6  mov     rcx, [rcx+10h]
0x14001dbaa  call    WPP_SF_SD
0x14001dbaf  test    r15d, r15d
0x14001dbb2  jnz     short loc_14001DC30
0x14001dbb4  cmp     [rsi], bl
0x14001dbb6  jz      short loc_14001DC30
0x14001dbb8  mov     r8, r14
0x14001dbbb  lea     rdx, [rsp+2B8h+var_288]
0x14001dbc0  mov     rax, [rsp+2B8h+var_258]
0x14001dbc5  mov     rcx, [rax]
0x14001dbc8  call    ??$emplace@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@_N@1@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &)
0x14001dbcd  cmp     [rsp+2B8h+var_288], rbx
0x14001dbd2  jnz     short loc_14001DC30
0x14001dbd4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dbdb  cmp     rcx, rdi
0x14001dbde  jz      short loc_14001DC04
0x14001dbe0  test    byte ptr [rcx+1Ch], 4
0x14001dbe4  jz      short loc_14001DC04
0x14001dbe6  cmp     byte ptr [rcx+19h], 2
0x14001dbea  jb      short loc_14001DC04
0x14001dbec  lea     edx, [r15+50h]
0x14001dbf0  lea     r9d, [r15+0Eh]
0x14001dbf4  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001dbfb  mov     rcx, [rcx+10h]
0x14001dbff  call    WPP_SF_d
0x14001dc04  mov     edx, 0Eh; unsigned int
0x14001dc09  mov     r9d, 53Ah; int
0x14001dc0f  lea     rcx, [rsp+2B8h+var_170]; this
0x14001dc17  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001dc1c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001dc23  lea     rcx, [rsp+2B8h+var_170]; pExceptionObject
0x14001dc2b  call    _CxxThrowException_0
0x14001dc30  mov     [rsp+2B8h+var_288], r12
0x14001dc35  mov     [rsp+2B8h+var_280], r13
0x14001dc3a  lea     r9, [rsp+2B8h+lpSubKey]
0x14001dc3f  lea     r8, [rsp+2B8h+hKey]
0x14001dc47  lea     rdx, [rsp+2B8h+var_288]
0x14001dc4c  call    ?GetLegacyChannelRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetLegacyChannelRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001dc51  mov     r15d, eax
0x14001dc54  test    eax, eax
0x14001dc56  jz      loc_14001DCDE
0x14001dc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc63  cmp     rcx, rdi
0x14001dc66  jz      short loc_14001DC8C
0x14001dc68  test    byte ptr [rcx+1Ch], 4
0x14001dc6c  jz      short loc_14001DC8C
0x14001dc6e  cmp     byte ptr [rcx+19h], 2
0x14001dc72  jb      short loc_14001DC8C
0x14001dc74  mov     edx, 51h ; 'Q'
0x14001dc79  mov     r9d, eax
0x14001dc7c  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001dc83  mov     rcx, [rcx+10h]
0x14001dc87  call    WPP_SF_d
0x14001dc8c  lea     rax, word_14003838A
0x14001dc93  mov     [rsp+2B8h+var_210], rax
0x14001dc9b  mov     [rsp+2B8h+var_208], rbx
0x14001dca3  mov     [rsp+2B8h+var_200], 0
0x14001dcaf  mov     [rsp+2B8h+var_1F8], r15d
0x14001dcb7  mov     [rsp+2B8h+var_1F4], 0FFFFFFFFFFFFFFFFh
0x14001dcc3  mov     [rsp+2B8h+var_1EC], bl
0x14001dcca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001dcd1  lea     rcx, [rsp+2B8h+var_210]; pExceptionObject
0x14001dcd9  call    _CxxThrowException_0
0x14001dcde  mov     rax, [rsi+8]
0x14001dce2  xor     r9d, r9d; Reserved
0x14001dce5  xor     r8d, r8d; samDesired
0x14001dce8  mov     rdx, [rsp+2B8h+lpSubKey]; lpSubKey
0x14001dced  mov     rcx, [rsp+2B8h+hKey]; hKey
0x14001dcf5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001dcf9  jz      short loc_14001DD0D
0x14001dcfb  mov     [rsp+2B8h+pExtendedParameter], rbx; pExtendedParameter
0x14001dd00  mov     [rsp+2B8h+hTransaction], rax; hTransaction
0x14001dd05  call    cs:__imp_RegDeleteKeyTransactedW
0x14001dd0b  jmp     short loc_14001DD13
0x14001dd0d  call    cs:__imp_RegDeleteKeyExW
0x14001dd13  mov     r15d, eax
0x14001dd16  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd1d  cmp     rcx, rdi
0x14001dd20  jz      short loc_14001DD4C
0x14001dd22  test    byte ptr [rcx+1Ch], 4
0x14001dd26  jz      short loc_14001DD4C
0x14001dd28  cmp     byte ptr [rcx+19h], 5
0x14001dd2c  jb      short loc_14001DD4C
0x14001dd2e  mov     edx, 52h ; 'R'
0x14001dd33  mov     dword ptr [rsp+2B8h+hTransaction], eax
0x14001dd37  mov     r9, [rsp+2B8h+lpSubKey]
0x14001dd3c  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001dd43  mov     rcx, [rcx+10h]
0x14001dd47  call    WPP_SF_SD
0x14001dd4c  test    r15d, r15d
0x14001dd4f  jnz     short loc_14001DDCE
0x14001dd51  cmp     [rsi], bl
0x14001dd53  jz      short loc_14001DDCE
0x14001dd55  mov     r8, r14
0x14001dd58  lea     rdx, [rsp+2B8h+var_288]
0x14001dd5d  mov     rax, [rsp+2B8h+var_258]
0x14001dd62  mov     rcx, [rax]
0x14001dd65  call    ??$emplace@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@_N@1@AEAV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &,0>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> &)
0x14001dd6a  cmp     [rsp+2B8h+var_288], rbx
0x14001dd6f  jnz     short loc_14001DDCE
0x14001dd71  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd78  cmp     rcx, rdi
0x14001dd7b  jz      short loc_14001DDA1
  ... truncated ...
```
