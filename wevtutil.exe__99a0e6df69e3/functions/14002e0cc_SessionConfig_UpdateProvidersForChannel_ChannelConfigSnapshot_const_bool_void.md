# SessionConfig::UpdateProvidersForChannel(ChannelConfigSnapshot const &,bool,void *)

- ea: `0x14002e0cc`
- end: `0x14002e754`
- name: `?UpdateProvidersForChannel@SessionConfig@@CAXAEBVChannelConfigSnapshot@@_NPEAX@Z`
- size: `1672`
- prototype: `void __fastcall(const struct ChannelConfigSnapshot *, bool, void *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140013658`
- `0x14002ddb0`

## callees

- `0x140004ae0`
- `0x140004ec0`
- `0x140005620`
- `0x140006a30`
- `0x140006db0`
- `0x140007d00`
- `0x140007fd0`
- `0x140008170`
- `0x140008870`
- `0x140008bc0`
- `0x14000b6d0`
- `0x14000d62c`
- `0x14000d6e8`
- `0x140014960`
- `0x140019348`
- `0x14001b324`
- `0x14001b5b4`
- `0x140021b00`
- `0x140022cec`
- `0x14002d8e4`
- `0x14002e0cc`
- `0x14002f69c`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e490`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e52c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e490`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002e52c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e44b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e4a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e59d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e5b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e5f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e231`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e44b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e4a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e59d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e5b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002e5f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall SessionConfig::UpdateProvidersForChannel(const struct ChannelConfigSnapshot *a1, char a2, void *a3)
{
  __int64 v4; // rcx
  unsigned int WinevtRegPath; // eax
  unsigned int v6; // ebx
  const char *v7; // r8
  void *v8; // rbx
  HKEY *v9; // rax
  unsigned int v10; // ebx
  unsigned int i; // eax
  HKEY *phkResult; // rbx
  HKEY *CurrentPublisherKey; // rax
  const wchar_t *v14; // rdx
  LSTATUS v15; // ebx
  unsigned int v16; // eax
  unsigned __int16 j; // bx
  HKEY *v18; // rax
  bool v19; // [rsp+30h] [rbp-418h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-410h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-408h] BYREF
  WCHAR SubKey[2]; // [rsp+44h] [rbp-404h] BYREF
  HKEY v23; // [rsp+48h] [rbp-400h] BYREF
  HKEY v24; // [rsp+50h] [rbp-3F8h] BYREF
  void *v25; // [rsp+58h] [rbp-3F0h] BYREF
  _WORD *v26; // [rsp+60h] [rbp-3E8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-3E0h]
  _WORD v28[8]; // [rsp+70h] [rbp-3D8h] BYREF
  HKEY v29[2]; // [rsp+80h] [rbp-3C8h] BYREF
  __int128 v30; // [rsp+90h] [rbp-3B8h] BYREF
  _WORD *v31; // [rsp+A0h] [rbp-3A8h] BYREF
  _WORD *v32; // [rsp+A8h] [rbp-3A0h]
  _WORD v33[8]; // [rsp+B0h] [rbp-398h] BYREF
  HKEY v34; // [rsp+C0h] [rbp-388h] BYREF
  _QWORD v35[2]; // [rsp+C8h] [rbp-380h] BYREF
  _QWORD v36[6]; // [rsp+D8h] [rbp-370h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+108h] [rbp-340h] BYREF
  _BYTE v38[40]; // [rsp+130h] [rbp-318h] BYREF
  _BYTE v39[40]; // [rsp+158h] [rbp-2F0h] BYREF
  wchar_t *v40[2]; // [rsp+180h] [rbp-2C8h] BYREF
  _WORD v41[8]; // [rsp+190h] [rbp-2B8h] BYREF
  _BYTE v42[80]; // [rsp+1A0h] [rbp-2A8h] BYREF
  HKEY v43[3]; // [rsp+1F0h] [rbp-258h] BYREF
  __int64 v44; // [rsp+208h] [rbp-240h]
  int v45; // [rsp+210h] [rbp-238h]
  int v46; // [rsp+214h] [rbp-234h]
  char v47; // [rsp+458h] [rbp+10h] BYREF

  v47 = a2;
  v25 = a3;
  *(_QWORD *)&v30 = *((_QWORD *)a1 + 25);
  *((_QWORD *)&v30 + 1) = (__int64)(*((_QWORD *)a1 + 26) - v30) >> 1;
  *(_OWORD *)v40 = v30;
  if ( !(unsigned __int8)IsSecurityChannel(v40) )
  {
    *(_OWORD *)v40 = v30;
    if ( !(unsigned __int8)ShouldSkipLegacyChannelKey(v40) )
    {
      v23 = 0;
      v40[0] = v41;
      v40[1] = v41;
      v41[0] = 0;
      v26 = v28;
      v27 = (__int64)v28;
      v28[0] = 0;
      WinevtRegPath = RegistryPaths::GetWinevtRegPath(v4, &v23, v40, &v26);
      v6 = WinevtRegPath;
      if ( WinevtRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids,
            WinevtRegPath);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v6);
        throw (EvtException *)pExceptionObject;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               v40,
                               L"\\Publishers",
                               11) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)v38, 0xEu, v7, 590);
        throw (EvtException *)v38;
      }
      hKey = 0;
      v8 = v25;
      v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v10 = OpenRegKey(v23, v40[0], 0x20019u, v9, v8);
      if ( v10 == 2 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v26);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
      }
      else
      {
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids, v10);
          }
          EvtException::EvtException((EvtException *)v39, v10);
          throw (EvtException *)v39;
        }
        if ( hKey )
          RegCloseKey(hKey);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v26);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
        *(_OWORD *)v40 = v30;
        v19 = (unsigned __int8)IsCoreChannel(v40) != 0;
        v29[0] = *((HKEY *)a1 + 25);
        v29[1] = (HKEY)((__int64)(*((_QWORD *)a1 + 26) - (unsigned __int64)v29[0]) >> 1);
        SessionConfig::EtwSessionForChannel::EtwSessionForChannel(
          v42,
          v29,
          *((unsigned __int8 *)a1 + 249),
          *((unsigned __int8 *)a1 + 248));
        v36[0] = &v30;
        v36[1] = a1;
        v36[2] = &v47;
        v36[3] = &v25;
        v36[4] = &v19;
        v36[5] = v42;
        v31 = v33;
        v32 = v33;
        v33[0] = 0;
        PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)v43, v25);
        v45 = v46;
        for ( i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v43);
              i != 259;
              i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v43) )
        {
          *(_OWORD *)v40 = 0;
          v35[0] = v43[2];
          v35[1] = v44;
          if ( v44 && tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(v40, v35) )
          {
            try
            {
              v23 = 0;
              PublisherConfigEnumerator::GetCurrentPublisherKey(v43, &v34);
              wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v23);
              v23 = 0;
              hKey = 0;
              wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&hKey);
              if ( v34 )
                RegCloseKey(v34);
              hKey = 0;
              phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
              CurrentPublisherKey = (HKEY *)PublisherConfigEnumerator::GetCurrentPublisherKey(v43, v29);
              v15 = RegOpenKeyExW(*CurrentPublisherKey, L"ChannelReferences", 0, 0x20019u, phkResult);
              if ( v29[0] )
                RegCloseKey(v29[0]);
              if ( !v15 )
              {
                v21 = 0;
                if ( !RegReadDWORDValueNoThrow(hKey, v14, L"Count", &v21) )
                {
                  v16 = v21;
                  if ( v21 >= 8 )
                  {
                    v16 = 8;
                    v21 = 8;
                  }
                  wcscpy(SubKey, L"0");
                  for ( j = 0; j < v16; ++j )
                  {
                    SubKey[0] = j + 48;
                    v24 = 0;
                    v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
                    if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, v18) && !(unsigned int)RegReadStringValueNoThrow(v24) )
                    {
                      v26 = v31;
                      v27 = v32 - v31;
                      SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()(v36, v40, &v26, j);
                    }
                    if ( v24 )
                      RegCloseKey(v24);
                    v16 = v21;
                  }
                }
              }
              if ( hKey )
                RegCloseKey(hKey);
              wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v23);
            }
            catch ( ... )
            {
              continue;
            }
          }
        }
        if ( v43[0] )
          RegCloseKey(v43[0]);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31);
        SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)v42);
      }
    }
  }
}

```

## disassembly

```asm
0x14002e0cc  mov     r11, rsp
0x14002e0cf  mov     [r11+20h], rbx
0x14002e0d3  mov     [rsp+arg_8], dl
0x14002e0d7  push    rsi
0x14002e0d8  push    rdi
0x14002e0d9  push    r14
0x14002e0db  sub     rsp, 430h
0x14002e0e2  mov     rax, cs:__security_cookie
0x14002e0e9  xor     rax, rsp
0x14002e0ec  mov     [rsp+448h+var_28], rax
0x14002e0f4  mov     rsi, rcx
0x14002e0f7  mov     [rsp+448h+var_3F0], r8
0x14002e0fc  mov     rax, [rcx+0C8h]
0x14002e103  mov     [r11-3B8h], rax
0x14002e10a  mov     rdx, [rcx+0D0h]
0x14002e111  sub     rdx, rax
0x14002e114  sar     rdx, 1
0x14002e117  mov     [r11-3B0h], rdx
0x14002e11e  movaps  xmm0, [rsp+448h+var_3B8]
0x14002e126  movdqa  xmmword ptr [rsp+448h+var_2C8], xmm0
0x14002e12f  lea     rcx, [r11-2C8h]
0x14002e136  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002e13b  xor     edi, edi
0x14002e13d  test    al, al
0x14002e13f  jnz     loc_14002E615
0x14002e145  movdqa  xmmword ptr [rsp+448h+var_2C8], xmm0
0x14002e14e  lea     rcx, [rsp+448h+var_2C8]
0x14002e156  call    ?ShouldSkipLegacyChannelKey@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ShouldSkipLegacyChannelKey(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002e15b  test    al, al
0x14002e15d  jnz     loc_14002E615
0x14002e163  mov     [rsp+448h+var_400], rdi
0x14002e168  lea     rax, [rsp+448h+var_2B8]
0x14002e170  mov     [rsp+448h+var_2C8], rax
0x14002e178  lea     rax, [rsp+448h+var_2B8]
0x14002e180  mov     [rsp+448h+var_2C8+8], rax
0x14002e188  mov     [rsp+448h+var_2B8], di
0x14002e190  lea     rax, [rsp+448h+var_3D8]
0x14002e195  mov     [rsp+448h+var_3E8], rax
0x14002e19a  lea     rax, [rsp+448h+var_3D8]
0x14002e19f  mov     [rsp+448h+var_3E0], rax
0x14002e1a4  mov     [rsp+448h+var_3D8], di
0x14002e1a9  lea     r9, [rsp+448h+var_3E8]
0x14002e1ae  lea     r8, [rsp+448h+var_2C8]
0x14002e1b6  lea     rdx, [rsp+448h+var_400]
0x14002e1bb  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002e1c0  mov     ebx, eax
0x14002e1c2  test    eax, eax
0x14002e1c4  jnz     loc_14002E639
0x14002e1ca  mov     r8d, 0Bh
0x14002e1d0  lea     rdx, aPublishers; "\\Publishers"
0x14002e1d7  lea     rcx, [rsp+448h+var_2C8]
0x14002e1df  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002e1e4  test    al, al
0x14002e1e6  jz      loc_14002E694
0x14002e1ec  mov     [rsp+448h+hKey], rdi
0x14002e1f1  mov     rbx, [rsp+448h+var_3F0]
0x14002e1f6  lea     rcx, [rsp+448h+hKey]
0x14002e1fb  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002e200  mov     [rsp+448h+phkResult], rbx; void *
0x14002e205  mov     r9, rax; HKEY *
0x14002e208  mov     r8d, 20019h; unsigned int
0x14002e20e  mov     rdx, [rsp+448h+var_2C8]; wchar_t *
0x14002e216  mov     rcx, [rsp+448h+var_400]; HKEY
0x14002e21b  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14002e220  mov     ebx, eax
0x14002e222  cmp     eax, 2
0x14002e225  jnz     short loc_14002E255
0x14002e227  mov     rcx, [rsp+448h+hKey]; hKey
0x14002e22c  test    rcx, rcx
0x14002e22f  jz      short loc_14002E238
0x14002e231  call    cs:__imp_RegCloseKey
0x14002e237  nop
0x14002e238  lea     rcx, [rsp+448h+var_3E8]
0x14002e23d  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002e242  nop
0x14002e243  lea     rcx, [rsp+448h+var_2C8]
0x14002e24b  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002e250  jmp     loc_14002E615
0x14002e255  test    ebx, ebx
0x14002e257  jnz     loc_14002E6F9
0x14002e25d  mov     rcx, [rsp+448h+hKey]; hKey
0x14002e262  test    rcx, rcx
0x14002e265  jz      short loc_14002E26E
0x14002e267  call    cs:__imp_RegCloseKey
0x14002e26d  nop
0x14002e26e  lea     rcx, [rsp+448h+var_3E8]
0x14002e273  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002e278  nop
0x14002e279  lea     rcx, [rsp+448h+var_2C8]
0x14002e281  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002e286  mov     [rsp+448h+var_418], dil
0x14002e28b  movaps  xmm0, [rsp+448h+var_3B8]
0x14002e293  movdqa  xmmword ptr [rsp+448h+var_2C8], xmm0
0x14002e29c  lea     rcx, [rsp+448h+var_2C8]
0x14002e2a4  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002e2a9  test    al, al
0x14002e2ab  jz      short loc_14002E2B2
0x14002e2ad  mov     [rsp+448h+var_418], 1
0x14002e2b2  mov     rax, [rsi+0C8h]
0x14002e2b9  mov     [rsp+448h+var_3C8], rax
0x14002e2c1  mov     rcx, [rsi+0D0h]
0x14002e2c8  sub     rcx, rax
0x14002e2cb  sar     rcx, 1
0x14002e2ce  mov     [rsp+448h+var_3C0], rcx
0x14002e2d6  movzx   r9d, byte ptr [rsi+0F8h]
0x14002e2de  movzx   r8d, byte ptr [rsi+0F9h]
0x14002e2e6  lea     rdx, [rsp+448h+var_3C8]
0x14002e2ee  lea     rcx, [rsp+448h+var_2A8]
0x14002e2f6  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x14002e2fb  nop
0x14002e2fc  lea     rax, [rsp+448h+var_3B8]
0x14002e304  mov     [rsp+448h+var_370], rax
0x14002e30c  mov     [rsp+448h+var_368], rsi
0x14002e314  lea     rax, [rsp+448h+arg_8]
0x14002e31c  mov     [rsp+448h+var_360], rax
0x14002e324  lea     rax, [rsp+448h+var_3F0]
0x14002e329  mov     [rsp+448h+var_358], rax
0x14002e331  lea     rax, [rsp+448h+var_418]
0x14002e336  mov     [rsp+448h+var_350], rax
0x14002e33e  lea     rax, [rsp+448h+var_2A8]
0x14002e346  mov     [rsp+448h+var_348], rax
0x14002e34e  lea     rax, [rsp+448h+var_398]
0x14002e356  mov     [rsp+448h+var_3A8], rax
0x14002e35e  lea     rax, [rsp+448h+var_398]
0x14002e366  mov     [rsp+448h+var_3A0], rax
0x14002e36e  mov     [rsp+448h+var_398], di
0x14002e376  mov     rdx, [rsp+448h+var_3F0]; void *
0x14002e37b  lea     rcx, [rsp+448h+var_258]; this
0x14002e383  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x14002e388  nop
0x14002e389  mov     eax, [rsp+448h+var_234]
0x14002e390  mov     [rsp+448h+var_238], eax
0x14002e397  lea     rcx, [rsp+448h+var_258]; this
0x14002e39f  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14002e3a4  mov     esi, 30h ; '0'
0x14002e3a9  cmp     eax, 103h
0x14002e3ae  jz      loc_14002E5E6
0x14002e3b4  xorps   xmm0, xmm0
0x14002e3b7  movups  xmmword ptr [rsp+448h+var_2C8], xmm0
0x14002e3bf  mov     rax, [rsp+448h+var_248]
0x14002e3c7  mov     [rsp+448h+var_380], rax
0x14002e3cf  mov     rax, [rsp+448h+var_240]
0x14002e3d7  mov     [rsp+448h+var_378], rax
0x14002e3df  test    rax, rax
0x14002e3e2  jz      loc_14002E5CD
0x14002e3e8  lea     rdx, [rsp+448h+var_380]
0x14002e3f0  lea     rcx, [rsp+448h+var_2C8]
0x14002e3f8  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x14002e3fd  test    rax, rax
0x14002e400  jz      loc_14002E5CD
0x14002e406  mov     [rsp+448h+var_400], rdi
0x14002e40b  lea     rdx, [rsp+448h+var_388]
0x14002e413  lea     rcx, [rsp+448h+var_258]
0x14002e41b  call    ?GetCurrentPublisherKey@PublisherConfigEnumerator@@QEAA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; PublisherConfigEnumerator::GetCurrentPublisherKey(ulong)
0x14002e420  lea     rcx, [rsp+448h+var_400]
0x14002e425  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14002e42a  mov     [rsp+448h+var_400], rdi
0x14002e42f  mov     [rsp+448h+hKey], rdi
0x14002e434  lea     rcx, [rsp+448h+hKey]
0x14002e439  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14002e43e  mov     rcx, [rsp+448h+var_388]; hKey
0x14002e446  test    rcx, rcx
0x14002e449  jz      short loc_14002E451
0x14002e44b  call    cs:__imp_RegCloseKey
0x14002e451  mov     [rsp+448h+hKey], rdi
0x14002e456  lea     rcx, [rsp+448h+hKey]
0x14002e45b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002e460  mov     rbx, rax
0x14002e463  lea     rdx, [rsp+448h+var_3C8]
0x14002e46b  lea     rcx, [rsp+448h+var_258]
0x14002e473  call    ?GetCurrentPublisherKey@PublisherConfigEnumerator@@QEAA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; PublisherConfigEnumerator::GetCurrentPublisherKey(ulong)
0x14002e478  mov     [rsp+448h+phkResult], rbx; phkResult
0x14002e47d  mov     r9d, 20019h; samDesired
0x14002e483  xor     r8d, r8d; ulOptions
0x14002e486  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x14002e48d  mov     rcx, [rax]; hKey
0x14002e490  call    cs:__imp_RegOpenKeyExW
0x14002e496  mov     ebx, eax
0x14002e498  mov     rcx, [rsp+448h+var_3C8]; hKey
0x14002e4a0  test    rcx, rcx
0x14002e4a3  jz      short loc_14002E4AB
0x14002e4a5  call    cs:__imp_RegCloseKey
0x14002e4ab  test    ebx, ebx
0x14002e4ad  jnz     loc_14002E5AF
0x14002e4b3  mov     [rsp+448h+var_408], edi
0x14002e4b7  lea     r9, [rsp+448h+var_408]; unsigned int *
0x14002e4bc  lea     r8, aCount_0; "Count"
0x14002e4c3  mov     rcx, [rsp+448h+hKey]; HKEY
0x14002e4c8  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x14002e4cd  test    eax, eax
0x14002e4cf  jnz     loc_14002E5AF
0x14002e4d5  mov     eax, [rsp+448h+var_408]
0x14002e4d9  cmp     eax, 8
0x14002e4dc  jb      short loc_14002E4E5
0x14002e4de  lea     eax, [rbx+8]
0x14002e4e1  mov     [rsp+448h+var_408], eax
0x14002e4e5  mov     dword ptr [rsp+448h+SubKey], 30h ; '0'
0x14002e4ed  movzx   ebx, di
0x14002e4f0  movzx   r14d, bx
0x14002e4f4  cmp     r14d, eax
0x14002e4f7  jnb     loc_14002E5AF
0x14002e4fd  lea     eax, [rsi+rbx]
0x14002e500  mov     [rsp+448h+SubKey], ax
0x14002e505  mov     [rsp+448h+var_3F8], rdi
0x14002e50a  lea     rcx, [rsp+448h+var_3F8]
0x14002e50f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002e514  mov     [rsp+448h+phkResult], rax; phkResult
0x14002e519  mov     r9d, 20019h; samDesired
0x14002e51f  xor     r8d, r8d; ulOptions
0x14002e522  lea     rdx, [rsp+448h+SubKey]; lpSubKey
0x14002e527  mov     rcx, [rsp+448h+hKey]; hKey
0x14002e52c  call    cs:__imp_RegOpenKeyExW
0x14002e532  test    eax, eax
0x14002e534  jnz     short loc_14002E593
0x14002e536  lea     r9, [rsp+448h+var_3A8]
0x14002e53e  lea     r8, ValueName
0x14002e545  xor     edx, edx
0x14002e547  mov     rcx, [rsp+448h+var_3F8]; hKey
0x14002e54c  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002e551  test    eax, eax
0x14002e553  jnz     short loc_14002E593
0x14002e555  mov     rax, [rsp+448h+var_3A8]
0x14002e55d  mov     [rsp+448h+var_3E8], rax
0x14002e562  mov     rcx, [rsp+448h+var_3A0]
0x14002e56a  sub     rcx, rax
0x14002e56d  sar     rcx, 1
0x14002e570  mov     [rsp+448h+var_3E0], rcx
0x14002e575  mov     r9d, r14d
0x14002e578  lea     r8, [rsp+448h+var_3E8]
0x14002e57d  lea     rdx, [rsp+448h+var_2C8]
0x14002e585  lea     rcx, [rsp+448h+var_370]
0x14002e58d  call    _SessionConfig__UpdateProvidersForChannel____2____lambda_1___operator__
0x14002e592  nop
0x14002e593  mov     rcx, [rsp+448h+var_3F8]; hKey
0x14002e598  test    rcx, rcx
0x14002e59b  jz      short loc_14002E5A3
0x14002e59d  call    cs:__imp_RegCloseKey
0x14002e5a3  inc     bx
0x14002e5a6  mov     eax, [rsp+448h+var_408]
0x14002e5aa  jmp     loc_14002E4F0
0x14002e5af  mov     rcx, [rsp+448h+hKey]; hKey
0x14002e5b4  test    rcx, rcx
0x14002e5b7  jz      short loc_14002E5C0
0x14002e5b9  call    cs:__imp_RegCloseKey
0x14002e5bf  nop
0x14002e5c0  lea     rcx, [rsp+448h+var_400]
0x14002e5c5  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14002e5ca  nop
0x14002e5cb  jmp     short loc_14002E5D4
0x14002e5cd  jmp     short loc_14002E5D4
0x14002e5cf  xor     edi, edi
0x14002e5d1  lea     esi, [rdi+30h]
0x14002e5d4  lea     rcx, [rsp+448h+var_258]; this
0x14002e5dc  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x14002e5e1  jmp     loc_14002E3A9
0x14002e5e6  mov     rcx, [rsp+448h+var_258]; hKey
0x14002e5ee  test    rcx, rcx
0x14002e5f1  jz      short loc_14002E5FA
0x14002e5f3  call    cs:__imp_RegCloseKey
0x14002e5f9  nop
0x14002e5fa  lea     rcx, [rsp+448h+var_3A8]
0x14002e602  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002e607  nop
0x14002e608  lea     rcx, [rsp+448h+var_2A8]; this
0x14002e610  call    ??1EtwSessionForChannel@SessionConfig@@QEAA@XZ; SessionConfig::EtwSessionForChannel::~EtwSessionForChannel(void)
0x14002e615  mov     rcx, [rsp+448h+var_28]
0x14002e61d  xor     rcx, rsp; StackCookie
0x14002e620  call    __security_check_cookie
0x14002e625  mov     rbx, [rsp+448h+arg_18]
0x14002e62d  add     rsp, 430h
0x14002e634  pop     r14
0x14002e636  pop     rdi
0x14002e637  pop     rsi
0x14002e638  retn
0x14002e639  lea     rcx, WPP_GLOBAL_Control
0x14002e640  mov     r10, cs:WPP_GLOBAL_Control
0x14002e647  cmp     r10, rcx
0x14002e64a  jz      short loc_14002E670
0x14002e64c  test    byte ptr [r10+1Ch], 4
0x14002e651  jz      short loc_14002E670
0x14002e653  cmp     byte ptr [r10+19h], 2
0x14002e658  jb      short loc_14002E670
0x14002e65a  lea     edx, [rdi+2Eh]
0x14002e65d  mov     r9d, eax
0x14002e660  lea     r8, WPP_33076ad79c433cf7ec704f0ac8373f62_Traceguids
0x14002e667  mov     rcx, [r10+10h]
0x14002e66b  call    WPP_SF_d
0x14002e670  mov     edx, ebx; unsigned int
0x14002e672  lea     rcx, [rsp+448h+pExceptionObject]; this
0x14002e67a  call    ??0EvtException@@QEAA@K@Z; EvtException::EvtException(ulong)
0x14002e67f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002e686  lea     rcx, [rsp+448h+pExceptionObject]; pExceptionObject
0x14002e68e  call    _CxxThrowException_0
0x14002e694  lea     rcx, WPP_GLOBAL_Control
0x14002e69b  mov     rax, cs:WPP_GLOBAL_Control
0x14002e6a2  cmp     rax, rcx
0x14002e6a5  jz      short loc_14002E6CC
0x14002e6a7  test    byte ptr [rax+1Ch], 4
0x14002e6ab  jz      short loc_14002E6CC
0x14002e6ad  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
