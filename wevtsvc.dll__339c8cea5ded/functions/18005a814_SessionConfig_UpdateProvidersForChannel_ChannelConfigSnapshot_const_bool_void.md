# SessionConfig::UpdateProvidersForChannel(ChannelConfigSnapshot const &,bool,void *)

- ea: `0x18005a814`
- end: `0x18005af76`
- name: `?UpdateProvidersForChannel@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z`
- size: `1890`
- prototype: `void __fastcall(const struct ChannelConfigSnapshot *, bool, void *)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180059508`
- `0x180084c98`

## callees

- `0x180003de0`
- `0x180006600`
- `0x180006650`
- `0x180006770`
- `0x180008870`
- `0x180009260`
- `0x1800092c4`
- `0x180017b60`
- `0x180017b98`
- `0x180017e28`
- `0x18002c6f4`
- `0x18002d6dc`
- `0x18003bb7c`
- `0x18003d1dc`
- `0x180054848`
- `0x18005a814`
- `0x18005c600`
- `0x18005d854`
- `0x18006c144`
- `0x18006ea98`
- `0x180075f00`
- `0x18008302c`
- `0x180083b84`
- `0x180092008`
- `0x180092c6c`
- `0x180092d78`
- `0x18009aee0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ad56`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
void __fastcall SessionConfig::UpdateProvidersForChannel(const struct ChannelConfigSnapshot *a1, char a2, void *a3)
{
  __int128 v4; // xmm0
  __int64 v5; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v7; // ebx
  const char *v8; // r8
  void *v9; // rbx
  HKEY *v10; // rax
  unsigned int v11; // ebx
  unsigned int i; // eax
  HKEY v13; // rbx
  __int64 v14; // r8
  HKEY *v15; // rdi
  __int64 v16; // rdi
  unsigned int v17; // r12d
  unsigned int j; // ebx
  HKEY *phkResult; // rdi
  HKEY *CurrentPublisherKey; // rax
  __int64 v21; // rdi
  unsigned int v22; // r12d
  unsigned int k; // ebx
  unsigned int v24; // eax
  unsigned __int16 m; // bx
  HKEY *v26; // rax
  bool v27; // [rsp+30h] [rbp-438h] BYREF
  unsigned int v28; // [rsp+34h] [rbp-434h] BYREF
  HKEY v29; // [rsp+38h] [rbp-430h] BYREF
  wchar_t SubKey[4]; // [rsp+40h] [rbp-428h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-420h] BYREF
  HKEY v32[2]; // [rsp+50h] [rbp-418h] BYREF
  wchar_t *v33[2]; // [rsp+60h] [rbp-408h] BYREF
  _WORD v34[8]; // [rsp+70h] [rbp-3F8h] BYREF
  void *v35; // [rsp+80h] [rbp-3E8h] BYREF
  _WORD *v36; // [rsp+88h] [rbp-3E0h] BYREF
  _WORD *v37; // [rsp+90h] [rbp-3D8h]
  _WORD v38[12]; // [rsp+98h] [rbp-3D0h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-3B8h] BYREF
  wchar_t *v40; // [rsp+C0h] [rbp-3A8h] BYREF
  _WORD *v41; // [rsp+C8h] [rbp-3A0h]
  _WORD v42[8]; // [rsp+D0h] [rbp-398h] BYREF
  _BYTE v43[8]; // [rsp+E0h] [rbp-388h] BYREF
  _BYTE v44[8]; // [rsp+E8h] [rbp-380h] BYREF
  _BYTE v45[8]; // [rsp+F0h] [rbp-378h] BYREF
  _QWORD v46[6]; // [rsp+F8h] [rbp-370h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+128h] [rbp-340h] BYREF
  _BYTE v48[40]; // [rsp+150h] [rbp-318h] BYREF
  _BYTE v49[40]; // [rsp+178h] [rbp-2F0h] BYREF
  __int128 v50; // [rsp+1A0h] [rbp-2C8h] BYREF
  _QWORD v51[10]; // [rsp+1B0h] [rbp-2B8h] BYREF
  _BYTE v52[16]; // [rsp+200h] [rbp-268h] BYREF
  _WORD *v53; // [rsp+210h] [rbp-258h]
  _WORD *v54; // [rsp+218h] [rbp-250h]
  int v55; // [rsp+220h] [rbp-248h]
  int v56; // [rsp+224h] [rbp-244h]
  char v57; // [rsp+478h] [rbp+10h] BYREF

  v57 = a2;
  v35 = (void *)-1LL;
  *(_QWORD *)&v39 = *((_QWORD *)a1 + 25);
  *((_QWORD *)&v39 + 1) = (__int64)(*((_QWORD *)a1 + 26) - v39) >> 1;
  v4 = v39;
  *(_OWORD *)v33 = v39;
  if ( !(unsigned __int8)IsSecurityChannel(v33) )
  {
    *(_OWORD *)v33 = v4;
    if ( !(unsigned __int8)ShouldSkipLegacyChannelKey(v33) )
    {
      v32[0] = 0;
      v33[0] = v34;
      v33[1] = v34;
      v34[0] = 0;
      v36 = v38;
      v37 = v38;
      v38[0] = 0;
      WinevtRegPath = RegistryPaths::GetWinevtRegPath(v5, v32, (__int64 *)v33, (__int64)&v36);
      v7 = WinevtRegPath;
      if ( WinevtRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            &WPP_b172996960853cbcad4882dc20a972f5_Traceguids,
            WinevtRegPath);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v7);
        throw (EvtException *)pExceptionObject;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v33) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)v48, 14, v8, 590);
        throw (EvtException *)v48;
      }
      v29 = 0;
      v9 = v35;
      v10 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
      v11 = OpenRegKey(v32[0], v33[0], 0x20019u, v10, v9);
      if ( v11 == 2 )
      {
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v36);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
      }
      else
      {
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_b172996960853cbcad4882dc20a972f5_Traceguids, v11);
          }
          EvtException::EvtException((EvtException *)v49, v11);
          throw (EvtException *)v49;
        }
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v36);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v33);
        *(_OWORD *)v33 = v39;
        v27 = (unsigned __int8)IsCoreChannel(v33) != 0;
        *(_QWORD *)&v50 = *((_QWORD *)a1 + 25);
        *((_QWORD *)&v50 + 1) = (__int64)(*((_QWORD *)a1 + 26) - v50) >> 1;
        SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
          v51,
          &v50,
          *((unsigned __int8 *)a1 + 249),
          *((unsigned __int8 *)a1 + 248));
        v46[0] = &v39;
        v46[1] = a1;
        v46[2] = &v57;
        v46[3] = &v35;
        v46[4] = &v27;
        v46[5] = v51;
        v40 = v42;
        v41 = v42;
        v42[0] = 0;
        PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)v52, v35);
        v55 = v56;
        for ( i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v52);
              i != 259;
              i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v52) )
        {
          v50 = 0;
          v36 = v53;
          v37 = v54;
          if ( v54 && tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(&v50, &v36) )
          {
            GetRegCacheProviderNodebyGuid(&v29, &v50);
            v13 = v29;
            if ( !v29 )
            {
              v14 = *(_QWORD *)PublisherConfigEnumerator::GetCurrentPublisherKey(v52, v44);
              v15 = (HKEY *)AddRegCacheProviderNode(v43, &v50, v14);
              wmi::AutoRef<PublisherMetadata>::Release(&v29);
              v29 = *v15;
              v13 = v29;
              *v15 = 0;
              wmi::AutoRef<PublisherMetadata>::Release(v43);
              tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v44);
              if ( !v13 )
                goto LABEL_18;
            }
            v16 = *((_QWORD *)v13 + 23);
            if ( v16 )
            {
              v17 = *(_DWORD *)(v16 + 8);
              for ( j = 0; j < v17; ++j )
              {
                *(_OWORD *)v32 = *(_OWORD *)(*(_QWORD *)v16 + 24LL * j);
                SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()(v46, &v50, v32, j);
              }
            }
            else
            {
LABEL_18:
              hKey = 0;
              phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
              CurrentPublisherKey = (HKEY *)PublisherConfigEnumerator::GetCurrentPublisherKey(v52, v45);
              LODWORD(phkResult) = RegOpenKeyExW(*CurrentPublisherKey, L"ChannelReferences", 0, 0x20019u, phkResult);
              tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v45);
              if ( !(_DWORD)phkResult )
              {
                if ( v13
                  && !AddRegCacheProviderNodeChannelReferences(hKey, (struct REG_CACHE_PROVIDERNODE *)v13)
                  && (v21 = *((_QWORD *)v13 + 23)) != 0 )
                {
                  v22 = *(_DWORD *)(v21 + 8);
                  for ( k = 0; k < v22; ++k )
                  {
                    *(_OWORD *)v32 = *(_OWORD *)(*(_QWORD *)v21 + 24LL * k);
                    SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()(v46, &v50, v32, k);
                  }
                }
                else
                {
                  v28 = 0;
                  if ( !(unsigned int)RegReadDWORDValueNoThrow(hKey, 0, L"Count", &v28) )
                  {
                    v24 = v28;
                    if ( v28 >= 8 )
                    {
                      v24 = 8;
                      v28 = 8;
                    }
                    wcscpy(SubKey, L"0");
                    for ( m = 0; m < v24; ++m )
                    {
                      SubKey[0] = m + 48;
                      v32[0] = 0;
                      v26 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v32);
                      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, v26)
                        && !(unsigned int)RegReadStringValueNoThrow(v32[0]) )
                      {
                        v33[0] = v40;
                        v33[1] = (wchar_t *)(v41 - v40);
                        SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()(v46, &v50, v33, m);
                      }
                      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v32);
                      v24 = v28;
                    }
                  }
                }
              }
              tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            }
            wmi::AutoRef<PublisherMetadata>::Release(&v29);
          }
        }
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v52);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v40);
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(v51);
      }
    }
  }
}

```

## disassembly

```asm
0x18005a814  mov     r11, rsp
0x18005a817  mov     [r11+18h], rbx
0x18005a81b  mov     [rsp+arg_8], dl
0x18005a81f  push    rsi
0x18005a820  push    rdi
0x18005a821  push    r12
0x18005a823  push    r14
0x18005a825  push    r15
0x18005a827  sub     rsp, 440h
0x18005a82e  mov     rax, cs:__security_cookie
0x18005a835  xor     rax, rsp
0x18005a838  mov     [rsp+468h+var_38], rax
0x18005a840  mov     rdi, rcx
0x18005a843  mov     qword ptr [r11-3E8h], 0FFFFFFFFFFFFFFFFh
0x18005a84e  mov     rax, [rcx+0C8h]
0x18005a855  mov     [r11-3B8h], rax
0x18005a85c  mov     rdx, [rcx+0D0h]
0x18005a863  sub     rdx, rax
0x18005a866  sar     rdx, 1
0x18005a869  mov     [r11-3B0h], rdx
0x18005a870  movaps  xmm0, [rsp+468h+var_3B8]
0x18005a878  movdqa  xmmword ptr [rsp+468h+var_408], xmm0
0x18005a87e  lea     rcx, [rsp+468h+var_408]
0x18005a883  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005a888  xor     esi, esi
0x18005a88a  test    al, al
0x18005a88c  jnz     loc_18005AE33
0x18005a892  movdqa  xmmword ptr [rsp+468h+var_408], xmm0
0x18005a898  lea     rcx, [rsp+468h+var_408]
0x18005a89d  call    ?ShouldSkipLegacyChannelKey@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ShouldSkipLegacyChannelKey(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005a8a2  test    al, al
0x18005a8a4  jnz     loc_18005AE33
0x18005a8aa  mov     [rsp+468h+var_418], rsi
0x18005a8af  lea     rax, [rsp+468h+var_3F8]
0x18005a8b4  mov     [rsp+468h+var_408], rax
0x18005a8b9  lea     rax, [rsp+468h+var_3F8]
0x18005a8be  mov     [rsp+468h+var_408+8], rax
0x18005a8c3  mov     [rsp+468h+var_3F8], si
0x18005a8c8  lea     rax, [rsp+468h+var_3D0]
0x18005a8d0  mov     [rsp+468h+var_3E0], rax
0x18005a8d8  lea     rax, [rsp+468h+var_3D0]
0x18005a8e0  mov     [rsp+468h+var_3D8], rax
0x18005a8e8  mov     [rsp+468h+var_3D0], si
0x18005a8f0  lea     r9, [rsp+468h+var_3E0]
0x18005a8f8  lea     r8, [rsp+468h+var_408]
0x18005a8fd  lea     rdx, [rsp+468h+var_418]
0x18005a902  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005a907  mov     ebx, eax
0x18005a909  test    eax, eax
0x18005a90b  jnz     loc_18005AE5B
0x18005a911  mov     r8d, 0Bh
0x18005a917  lea     rdx, aPublishers; "\\Publishers"
0x18005a91e  lea     rcx, [rsp+468h+var_408]
0x18005a923  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18005a928  test    al, al
0x18005a92a  jz      loc_18005AEB6
0x18005a930  mov     [rsp+468h+var_430], rsi
0x18005a935  mov     rbx, [rsp+468h+var_3E8]
0x18005a93d  lea     rcx, [rsp+468h+var_430]
0x18005a942  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005a947  mov     [rsp+468h+phkResult], rbx; void *
0x18005a94c  mov     r9, rax; HKEY *
0x18005a94f  mov     r8d, 20019h; unsigned int
0x18005a955  mov     rdx, [rsp+468h+var_408]; wchar_t *
0x18005a95a  mov     rcx, [rsp+468h+var_418]; HKEY
0x18005a95f  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18005a964  mov     ebx, eax
0x18005a966  cmp     eax, 2
0x18005a969  jnz     short loc_18005A993
0x18005a96b  lea     rcx, [rsp+468h+var_430]
0x18005a970  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005a975  nop
0x18005a976  lea     rcx, [rsp+468h+var_3E0]; void *
0x18005a97e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005a983  nop
0x18005a984  lea     rcx, [rsp+468h+var_408]; void *
0x18005a989  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005a98e  jmp     loc_18005AE33
0x18005a993  test    ebx, ebx
0x18005a995  jnz     loc_18005AF1B
0x18005a99b  lea     rcx, [rsp+468h+var_430]
0x18005a9a0  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005a9a5  nop
0x18005a9a6  lea     rcx, [rsp+468h+var_3E0]; void *
0x18005a9ae  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005a9b3  nop
0x18005a9b4  lea     rcx, [rsp+468h+var_408]; void *
0x18005a9b9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005a9be  mov     [rsp+468h+var_438], sil
0x18005a9c3  movaps  xmm0, [rsp+468h+var_3B8]
0x18005a9cb  movdqa  xmmword ptr [rsp+468h+var_408], xmm0
0x18005a9d1  lea     rcx, [rsp+468h+var_408]
0x18005a9d6  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005a9db  mov     r14d, 1
0x18005a9e1  test    al, al
0x18005a9e3  jz      short loc_18005A9EA
0x18005a9e5  mov     [rsp+468h+var_438], r14b
0x18005a9ea  mov     rax, [rdi+0C8h]
0x18005a9f1  mov     qword ptr [rsp+468h+var_2C8], rax
0x18005a9f9  mov     rcx, [rdi+0D0h]
0x18005aa00  sub     rcx, rax
0x18005aa03  sar     rcx, 1
0x18005aa06  mov     qword ptr [rsp+468h+var_2C8+8], rcx
0x18005aa0e  movzx   r9d, byte ptr [rdi+0F8h]
0x18005aa16  movzx   r8d, byte ptr [rdi+0F9h]
0x18005aa1e  lea     rdx, [rsp+468h+var_2C8]
0x18005aa26  lea     rcx, [rsp+468h+var_2B8]
0x18005aa2e  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x18005aa33  nop
0x18005aa34  lea     rax, [rsp+468h+var_3B8]
0x18005aa3c  mov     [rsp+468h+var_370], rax
0x18005aa44  mov     [rsp+468h+var_368], rdi
0x18005aa4c  lea     rax, [rsp+468h+arg_8]
0x18005aa54  mov     [rsp+468h+var_360], rax
0x18005aa5c  lea     rax, [rsp+468h+var_3E8]
0x18005aa64  mov     [rsp+468h+var_358], rax
0x18005aa6c  lea     rax, [rsp+468h+var_438]
0x18005aa71  mov     [rsp+468h+var_350], rax
0x18005aa79  lea     rax, [rsp+468h+var_2B8]
0x18005aa81  mov     [rsp+468h+var_348], rax
0x18005aa89  lea     rax, [rsp+468h+var_398]
0x18005aa91  mov     [rsp+468h+var_3A8], rax
0x18005aa99  lea     rax, [rsp+468h+var_398]
0x18005aaa1  mov     [rsp+468h+var_3A0], rax
0x18005aaa9  mov     [rsp+468h+var_398], si
0x18005aab1  mov     rdx, [rsp+468h+var_3E8]; void *
0x18005aab9  lea     rcx, [rsp+468h+var_268]; this
0x18005aac1  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x18005aac6  nop
0x18005aac7  mov     eax, [rsp+468h+var_244]
0x18005aace  mov     [rsp+468h+var_248], eax
0x18005aad5  lea     rcx, [rsp+468h+var_268]; this
0x18005aadd  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18005aae2  mov     r15d, 30h ; '0'
0x18005aae8  cmp     eax, 103h
0x18005aaed  jz      loc_18005AE0A
0x18005aaf3  xorps   xmm0, xmm0
0x18005aaf6  movups  [rsp+468h+var_2C8], xmm0
0x18005aafe  mov     rax, [rsp+468h+var_258]
0x18005ab06  mov     [rsp+468h+var_3E0], rax
0x18005ab0e  mov     rax, [rsp+468h+var_250]
0x18005ab16  mov     [rsp+468h+var_3D8], rax
0x18005ab1e  test    rax, rax
0x18005ab21  jz      loc_18005ADEC
0x18005ab27  lea     rdx, [rsp+468h+var_3E0]
0x18005ab2f  lea     rcx, [rsp+468h+var_2C8]
0x18005ab37  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18005ab3c  test    rax, rax
0x18005ab3f  jz      loc_18005ADEC
0x18005ab45  lea     rdx, [rsp+468h+var_2C8]
0x18005ab4d  lea     rcx, [rsp+468h+var_430]
0x18005ab52  call    ?GetRegCacheProviderNodebyGuid@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@@Z; GetRegCacheProviderNodebyGuid(_GUID const *)
0x18005ab57  nop
0x18005ab58  mov     rbx, [rsp+468h+var_430]
0x18005ab5d  test    rbx, rbx
0x18005ab60  jnz     short loc_18005ABC8
0x18005ab62  lea     rdx, [rsp+468h+var_380]
0x18005ab6a  lea     rcx, [rsp+468h+var_268]
0x18005ab72  call    ?GetCurrentPublisherKey@PublisherConfigEnumerator@@QEAA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; PublisherConfigEnumerator::GetCurrentPublisherKey(ulong)
0x18005ab77  nop
0x18005ab78  mov     r8, [rax]
0x18005ab7b  lea     rdx, [rsp+468h+var_2C8]
0x18005ab83  lea     rcx, [rsp+468h+var_388]
0x18005ab8b  call    ?AddRegCacheProviderNode@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@PEAUHKEY__@@@Z; AddRegCacheProviderNode(_GUID const *,HKEY__ *)
0x18005ab90  mov     rdi, rax
0x18005ab93  lea     rcx, [rsp+468h+var_430]
0x18005ab98  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18005ab9d  mov     rbx, [rdi]
0x18005aba0  mov     [rsp+468h+var_430], rbx
0x18005aba5  mov     [rdi], rsi
0x18005aba8  lea     rcx, [rsp+468h+var_388]
0x18005abb0  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18005abb5  nop
0x18005abb6  lea     rcx, [rsp+468h+var_380]
0x18005abbe  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005abc3  test    rbx, rbx
0x18005abc6  jz      short loc_18005AC18
0x18005abc8  mov     rdi, [rbx+0B8h]
0x18005abcf  test    rdi, rdi
0x18005abd2  jz      short loc_18005AC18
0x18005abd4  mov     r12d, [rdi+8]
0x18005abd8  mov     ebx, esi
0x18005abda  cmp     ebx, r12d
0x18005abdd  jnb     loc_18005ADDF
0x18005abe3  mov     eax, ebx
0x18005abe5  lea     rcx, [rax+rax*2]
0x18005abe9  mov     rax, [rdi]
0x18005abec  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18005abf0  movdqu  xmmword ptr [rsp+468h+var_418], xmm0
0x18005abf6  mov     r9d, ebx
0x18005abf9  lea     r8, [rsp+468h+var_418]
0x18005abfe  lea     rdx, [rsp+468h+var_2C8]
0x18005ac06  lea     rcx, [rsp+468h+var_370]
0x18005ac0e  call    _SessionConfig__UpdateProvidersForChannel____2____lambda_1___operator__
0x18005ac13  add     ebx, r14d
0x18005ac16  jmp     short loc_18005ABDA
0x18005ac18  mov     [rsp+468h+hKey], rsi
0x18005ac1d  lea     rcx, [rsp+468h+hKey]
0x18005ac22  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005ac27  mov     rdi, rax
0x18005ac2a  lea     rdx, [rsp+468h+var_378]
0x18005ac32  lea     rcx, [rsp+468h+var_268]
0x18005ac3a  call    ?GetCurrentPublisherKey@PublisherConfigEnumerator@@QEAA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; PublisherConfigEnumerator::GetCurrentPublisherKey(ulong)
0x18005ac3f  mov     [rsp+468h+phkResult], rdi; phkResult
0x18005ac44  mov     r9d, 20019h; samDesired
0x18005ac4a  xor     r8d, r8d; ulOptions
0x18005ac4d  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x18005ac54  mov     rcx, [rax]; hKey
0x18005ac57  call    cs:__imp_RegOpenKeyExW
0x18005ac5d  mov     edi, eax
0x18005ac5f  lea     rcx, [rsp+468h+var_378]
0x18005ac67  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005ac6c  test    edi, edi
0x18005ac6e  jnz     loc_18005ADD4
0x18005ac74  test    rbx, rbx
0x18005ac77  jz      short loc_18005ACDA
0x18005ac79  mov     rdx, rbx; struct REG_CACHE_PROVIDERNODE *
0x18005ac7c  mov     rcx, [rsp+468h+hKey]; HKEY
0x18005ac81  call    ?AddRegCacheProviderNodeChannelReferences@@YAKPEAUHKEY__@@PEAUREG_CACHE_PROVIDERNODE@@@Z; AddRegCacheProviderNodeChannelReferences(HKEY__ *,REG_CACHE_PROVIDERNODE *)
0x18005ac86  test    eax, eax
0x18005ac88  jnz     short loc_18005ACDA
0x18005ac8a  mov     rdi, [rbx+0B8h]
0x18005ac91  test    rdi, rdi
0x18005ac94  jz      short loc_18005ACDA
0x18005ac96  mov     r12d, [rdi+8]
0x18005ac9a  mov     ebx, esi
0x18005ac9c  cmp     ebx, r12d
0x18005ac9f  jnb     loc_18005ADD4
0x18005aca5  mov     eax, ebx
0x18005aca7  lea     rcx, [rax+rax*2]
0x18005acab  mov     rax, [rdi]
0x18005acae  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18005acb2  movdqu  xmmword ptr [rsp+468h+var_418], xmm0
0x18005acb8  mov     r9d, ebx
0x18005acbb  lea     r8, [rsp+468h+var_418]
0x18005acc0  lea     rdx, [rsp+468h+var_2C8]
0x18005acc8  lea     rcx, [rsp+468h+var_370]
0x18005acd0  call    _SessionConfig__UpdateProvidersForChannel____2____lambda_1___operator__
0x18005acd5  add     ebx, r14d
0x18005acd8  jmp     short loc_18005AC9C
0x18005acda  mov     [rsp+468h+var_434], esi
0x18005acde  lea     r9, [rsp+468h+var_434]; unsigned int *
0x18005ace3  lea     r8, aCount_1; "Count"
0x18005acea  xor     edx, edx; wchar_t *
0x18005acec  mov     rcx, [rsp+468h+hKey]; HKEY
0x18005acf1  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18005acf6  test    eax, eax
0x18005acf8  jnz     loc_18005ADD4
0x18005acfe  mov     eax, [rsp+468h+var_434]
0x18005ad02  cmp     eax, 8
0x18005ad05  jb      short loc_18005AD10
0x18005ad07  mov     eax, 8
0x18005ad0c  mov     [rsp+468h+var_434], eax
0x18005ad10  mov     dword ptr [rsp+468h+SubKey], 30h ; '0'
0x18005ad18  movzx   ebx, si
0x18005ad1b  movzx   edi, bx
0x18005ad1e  cmp     edi, eax
0x18005ad20  jnb     loc_18005ADD4
0x18005ad26  lea     eax, [r15+rbx]
0x18005ad2a  mov     [rsp+468h+SubKey], ax
0x18005ad2f  mov     [rsp+468h+var_418], rsi
0x18005ad34  lea     rcx, [rsp+468h+var_418]
0x18005ad39  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18005ad3e  mov     [rsp+468h+phkResult], rax; phkResult
0x18005ad43  mov     r9d, 20019h; samDesired
0x18005ad49  xor     r8d, r8d; ulOptions
0x18005ad4c  lea     rdx, [rsp+468h+SubKey]; lpSubKey
0x18005ad51  mov     rcx, [rsp+468h+hKey]; hKey
0x18005ad56  call    cs:__imp_RegOpenKeyExW
0x18005ad5c  test    eax, eax
0x18005ad5e  jnz     short loc_18005ADBD
0x18005ad60  lea     r9, [rsp+468h+var_3A8]
0x18005ad68  lea     r8, pszFormat
0x18005ad6f  xor     edx, edx
0x18005ad71  mov     rcx, [rsp+468h+var_418]; hKey
0x18005ad76  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005ad7b  test    eax, eax
0x18005ad7d  jnz     short loc_18005ADBD
0x18005ad7f  mov     rax, [rsp+468h+var_3A8]
0x18005ad87  mov     [rsp+468h+var_408], rax
0x18005ad8c  mov     rcx, [rsp+468h+var_3A0]
0x18005ad94  sub     rcx, rax
0x18005ad97  sar     rcx, 1
0x18005ad9a  mov     [rsp+468h+var_408+8], rcx
0x18005ad9f  mov     r9d, edi
0x18005ada2  lea     r8, [rsp+468h+var_408]
0x18005ada7  lea     rdx, [rsp+468h+var_2C8]
0x18005adaf  lea     rcx, [rsp+468h+var_370]
0x18005adb7  call    _SessionConfig__UpdateProvidersForChannel____2____lambda_1___operator__
0x18005adbc  nop
0x18005adbd  lea     rcx, [rsp+468h+var_418]
0x18005adc2  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005adc7  add     bx, r14w
0x18005adcb  mov     eax, [rsp+468h+var_434]
0x18005adcf  jmp     loc_18005AD1B
0x18005add4  lea     rcx, [rsp+468h+hKey]
0x18005add9  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005adde  nop
0x18005addf  lea     rcx, [rsp+468h+var_430]
0x18005ade4  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
  ... truncated ...
```
