# ManifestProcessor::RetractProvider(_GUID,StringSet const &)

- ea: `0x14001e0c0`
- end: `0x14001e44f`
- name: `?RetractProvider@ManifestProcessor@@AEAAXU_GUID@@AEBVStringSet@@@Z`
- size: `911`
- prototype: `void(ManifestProcessor *__hidden this, struct _GUID *__struct_ptr, const struct StringSet *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a6a0`

## callees

- `0x140003b50`
- `0x140004ae0`
- `0x140004cb0`
- `0x1400050a0`
- `0x140005600`
- `0x140005c9c`
- `0x140006db0`
- `0x140007f00`
- `0x140007fd0`
- `0x1400099c8`
- `0x14000d62c`
- `0x14000d6e8`
- `0x14001a814`
- `0x14001b244`
- `0x14001b47c`
- `0x14001d828`
- `0x14001e0c0`
- `0x14001e458`
- `0x140021b00`
- `0x14002a19c`
- `0x14002a55c`
- `0x14002ba08`
- `0x14002bb2c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001e2ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14001e2ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001e2bd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14001e2bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e40a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001e40a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ManifestProcessor::RetractProvider(
        ManifestProcessor *this,
        struct _GUID *a2,
        const struct StringSet *a3)
{
  const struct StringSet *v3; // r13
  const struct _GUID *v4; // r14
  HKEY v5; // rsi
  __int64 v6; // rcx
  void **v7; // r12
  void **p_Ptr; // r15
  void *v9; // rbx
  HKEY *v10; // rax
  LSTATUS v11; // eax
  __int64 *v12; // rbx
  unsigned int v13; // ebx
  const struct std::nothrow_t *i; // r9
  int v15; // r8d
  HKEY hKey; // [rsp+30h] [rbp-1C8h] BYREF
  WINBOOL fPending[2]; // [rsp+38h] [rbp-1C0h] BYREF
  LPVOID Context; // [rsp+40h] [rbp-1B8h] BYREF
  union _RTL_RUN_ONCE *v19; // [rsp+48h] [rbp-1B0h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-1A8h] BYREF
  const struct std::nothrow_t *v21; // [rsp+60h] [rbp-198h] BYREF
  __int64 v22; // [rsp+68h] [rbp-190h]
  const struct StringSet *v23; // [rsp+78h] [rbp-180h]
  wchar_t *v24[4]; // [rsp+80h] [rbp-178h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-158h] BYREF
  struct _GUID *v26; // [rsp+C0h] [rbp-138h]
  _BYTE v27[144]; // [rsp+D0h] [rbp-128h] BYREF
  wchar_t v28; // [rsp+160h] [rbp-98h] BYREF
  _BYTE v29[72]; // [rsp+162h] [rbp-96h] BYREF
  int v30; // [rsp+1AAh] [rbp-4Eh]

  v3 = a3;
  v4 = a2;
  v5 = (HKEY)this;
  Context = this;
  v26 = a2;
  v23 = a3;
  if ( *(_BYTE *)tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get() )
  {
    *(_QWORD *)fPending = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v24);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
    if ( !(unsigned int)RegistryPaths::GetWinevtRegPath(v6, fPending, v24, v25)
      && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            v24,
                            L"\\Publishers",
                            11) )
    {
      v28 = 123;
      tlx::guid_to_string_lower<wchar_t>(v29, v4, 0);
      v30 = 125;
      hKey = 0;
      v7 = (void **)(v5 + 2);
      p_Ptr = (void **)(v5 + 2);
      v19 = (union _RTL_RUN_ONCE *)(v5 + 2);
      v9 = (void *)*((_QWORD *)v5 + 1);
      v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
      v11 = OpenRegKey(*(HKEY *)fPending, v24[0], 0xF003Fu, v10, v9);
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
            v24[0],
            v11);
        }
      }
      else
      {
        utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(&v21);
        try
        {
          PublisherConfigReader::PublisherConfigReader((PublisherConfigReader *)v27, v4, hKey, *v7);
          PublisherConfigReader::GetAndValidateManifestedChannelReferences((__int64)v27, &v21);
          PublisherConfigReader::~PublisherConfigReader((PublisherConfigReader *)v27);
        }
        catch ( EvtException )
        {
          p_Ptr = &v19->Ptr;
          v5 = (HKEY)Context;
          v3 = v23;
          v4 = v26;
          v7 = &v19->Ptr;
        }
        SessionConfig::DeleteProvider(v4, *v7);
        fPending[0] = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_140042660, 0, fPending, &Context);
        v12 = (__int64 *)Context;
        if ( !Context )
        {
          v19 = &stru_140042660;
          v12 = &qword_140042668;
          ChannelsKeyExists::ChannelsKeyExists((ChannelsKeyExists *)&qword_140042668);
          v19 = 0;
          InitOnceComplete(&stru_140042660, 0, &qword_140042668);
          tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(&v19);
        }
        if ( *(_BYTE *)v12 )
        {
          v13 = 0;
          for ( i = v21; v13 < 0xAAAAAAAAAAAAAAABuLL * ((v22 - (__int64)v21) >> 4); i = v21 )
          {
            v20[0] = *((_QWORD *)i + 6 * v13);
            v20[1] = (__int64)(*((_QWORD *)i + 6 * v13 + 1) - v20[0]) >> 1;
            ManifestProcessor::RetractChannel(v5, v20, *((_BYTE *)i + 48 * v13++ + 40) & 1, (__int64)v3);
          }
        }
        if ( *(_BYTE *)v5 )
          utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<wchar_t (&)[39],0>(
            *((_QWORD *)v5 + 4),
            v20,
            &v28);
        RegDeleteKeyRecursive(hKey, &v28, *p_Ptr);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&WPP_GLOBAL_Control,
            v15,
            v24[0],
            (__int64)&v28,
            0);
        }
        utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(&v21);
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v24);
  }
}

```

## disassembly

```asm
0x14001e0c0  push    rbx
0x14001e0c2  push    rsi
0x14001e0c3  push    rdi
0x14001e0c4  push    r12
0x14001e0c6  push    r13
0x14001e0c8  push    r14
0x14001e0ca  push    r15
0x14001e0cc  sub     rsp, 1C0h
0x14001e0d3  mov     rax, cs:__security_cookie
0x14001e0da  xor     rax, rsp
0x14001e0dd  mov     [rsp+1F8h+var_48], rax
0x14001e0e5  mov     r13, r8
0x14001e0e8  mov     r14, rdx
0x14001e0eb  mov     rsi, rcx
0x14001e0ee  mov     [rsp+1F8h+Context], rcx
0x14001e0f3  mov     [rsp+1F8h+var_138], rdx
0x14001e0fb  mov     [rsp+1F8h+var_180], r8
0x14001e100  call    ?get@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAAAEAVPublishersKeyExists@@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::get(void)
0x14001e105  xor     edi, edi
0x14001e107  cmp     [rax], dil
0x14001e10a  jz      loc_14001E42C
0x14001e110  mov     qword ptr [rsp+1F8h+fPending], rdi
0x14001e115  lea     rcx, [rsp+1F8h+var_178]
0x14001e11d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e122  nop
0x14001e123  lea     rcx, [rsp+1F8h+var_158]
0x14001e12b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e130  nop
0x14001e131  lea     r9, [rsp+1F8h+var_158]
0x14001e139  lea     r8, [rsp+1F8h+var_178]
0x14001e141  lea     rdx, [rsp+1F8h+fPending]
0x14001e146  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001e14b  test    eax, eax
0x14001e14d  jnz     loc_14001E411
0x14001e153  lea     r8d, [rdi+0Bh]
0x14001e157  lea     rdx, aPublishers; "\\Publishers"
0x14001e15e  lea     rcx, [rsp+1F8h+var_178]
0x14001e166  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14001e16b  test    al, al
0x14001e16d  jz      loc_14001E411
0x14001e173  lea     eax, [rdi+7Bh]
0x14001e176  mov     [rsp+1F8h+var_98], ax
0x14001e17e  xor     r8d, r8d
0x14001e181  mov     rdx, r14
0x14001e184  lea     rcx, [rsp+1F8h+var_96]
0x14001e18c  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x14001e191  mov     [rsp+1F8h+var_4E], 7Dh ; '}'
0x14001e19c  mov     [rsp+1F8h+hKey], rdi
0x14001e1a1  lea     r12, [rsi+8]
0x14001e1a5  mov     r15, r12
0x14001e1a8  mov     [rsp+1F8h+var_1B0], r12
0x14001e1ad  mov     rbx, [r12]
0x14001e1b1  lea     rcx, [rsp+1F8h+hKey]
0x14001e1b6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14001e1bb  mov     [rsp+1F8h+var_1D8], rbx; void *
0x14001e1c0  mov     r9, rax; HKEY *
0x14001e1c3  mov     r8d, 0F003Fh; unsigned int
0x14001e1c9  mov     rdx, [rsp+1F8h+var_178]; wchar_t *
0x14001e1d1  mov     rcx, qword ptr [rsp+1F8h+fPending]; HKEY
0x14001e1d6  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x14001e1db  test    eax, eax
0x14001e1dd  jz      short loc_14001E22E
0x14001e1df  lea     rdx, WPP_GLOBAL_Control
0x14001e1e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1ed  cmp     rcx, rdx
0x14001e1f0  jz      loc_14001E400
0x14001e1f6  test    byte ptr [rcx+1Ch], 4
0x14001e1fa  jz      loc_14001E400
0x14001e200  cmp     byte ptr [rcx+19h], 2
0x14001e204  jb      loc_14001E400
0x14001e20a  lea     edx, [rdi+5Ch]
0x14001e20d  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x14001e211  mov     r9, [rsp+1F8h+var_178]
0x14001e219  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001e220  mov     rcx, [rcx+10h]
0x14001e224  call    WPP_SF_SD
0x14001e229  jmp     loc_14001E400
0x14001e22e  lea     rcx, [rsp+1F8h+var_198]
0x14001e233  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x14001e238  nop
0x14001e239  mov     r9, [r12]; void *
0x14001e23d  mov     r8, [rsp+1F8h+hKey]; HKEY
0x14001e242  mov     rdx, r14; struct _GUID *
0x14001e245  lea     rcx, [rsp+1F8h+var_128]; this
0x14001e24d  call    ??0PublisherConfigReader@@IEAA@AEBU_GUID@@PEAUHKEY__@@PEAX@Z; PublisherConfigReader::PublisherConfigReader(_GUID const &,HKEY__ *,void *)
0x14001e252  nop
0x14001e253  lea     rdx, [rsp+1F8h+var_198]
0x14001e258  lea     rcx, [rsp+1F8h+var_128]
0x14001e260  call    ?GetAndValidateManifestedChannelReferences@PublisherConfigReader@@QEBA_NAEAV?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@@Z; PublisherConfigReader::GetAndValidateManifestedChannelReferences(utl::vector<ChannelReference,utl::allocator<ChannelReference>> &)
0x14001e265  nop
0x14001e266  lea     rcx, [rsp+1F8h+var_128]; this
0x14001e26e  call    ??1PublisherConfigReader@@QEAA@XZ; PublisherConfigReader::~PublisherConfigReader(void)
0x14001e273  nop
0x14001e274  jmp     short loc_14001E292
0x14001e276  xor     edi, edi
0x14001e278  mov     r15, [rsp+1F8h+var_1B0]
0x14001e27d  mov     rsi, [rsp+1F8h+Context]
0x14001e282  mov     r13, [rsp+1F8h+var_180]
0x14001e287  mov     r14, [rsp+1F8h+var_138]
0x14001e28f  mov     r12, r15
0x14001e292  mov     rdx, [r12]; void *
0x14001e296  mov     rcx, r14; struct _GUID *
0x14001e299  call    ?DeleteProvider@SessionConfig@@SAXAEBU_GUID@@PEAX@Z; SessionConfig::DeleteProvider(_GUID const &,void *)
0x14001e29e  mov     [rsp+1F8h+fPending], edi
0x14001e2a2  mov     [rsp+1F8h+Context], rdi
0x14001e2a7  lea     r9, [rsp+1F8h+Context]; lpContext
0x14001e2ac  lea     r8, [rsp+1F8h+fPending]; fPending
0x14001e2b1  xor     edx, edx; dwFlags
0x14001e2b3  lea     r14, stru_140042660
0x14001e2ba  mov     rcx, r14; lpInitOnce
0x14001e2bd  call    cs:__imp_InitOnceBeginInitialize
0x14001e2c3  mov     rbx, [rsp+1F8h+Context]
0x14001e2c8  test    rbx, rbx
0x14001e2cb  jnz     short loc_14001E2FF
0x14001e2cd  mov     [rsp+1F8h+var_1B0], r14
0x14001e2d2  lea     rbx, qword_140042668
0x14001e2d9  mov     rcx, rbx; this
0x14001e2dc  call    ??0ChannelsKeyExists@@QEAA@XZ; ChannelsKeyExists::ChannelsKeyExists(void)
0x14001e2e1  mov     [rsp+1F8h+var_1B0], rdi
0x14001e2e6  mov     r8, rbx; lpContext
0x14001e2e9  xor     edx, edx; dwFlags
0x14001e2eb  mov     rcx, r14; lpInitOnce
0x14001e2ee  call    cs:__imp_InitOnceComplete
0x14001e2f4  nop
0x14001e2f5  lea     rcx, [rsp+1F8h+var_1B0]
0x14001e2fa  call    ??1_Initializer@?$_LazyImpl@VPublishersKeyExists@@V?$lazy_construct@VPublishersKeyExists@@@tlx@@V?$static_lazy@VPublishersKeyExists@@$00V?$lazy_construct@VPublishersKeyExists@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<PublishersKeyExists,tlx::lazy_construct<PublishersKeyExists>,tlx::static_lazy<PublishersKeyExists,1,tlx::lazy_construct<PublishersKeyExists>>>::_Initializer::~_Initializer(void)
0x14001e2ff  cmp     [rbx], dil
0x14001e302  jz      short loc_14001E383
0x14001e304  mov     ebx, edi
0x14001e306  mov     rax, [rsp+1F8h+var_190]
0x14001e30b  mov     r9, [rsp+1F8h+var_198]
0x14001e310  sub     rax, r9
0x14001e313  sar     rax, 4
0x14001e317  mov     r14, 0AAAAAAAAAAAAAAABh
0x14001e321  imul    rax, r14
0x14001e325  test    rax, rax
0x14001e328  jz      short loc_14001E383
0x14001e32a  mov     eax, ebx
0x14001e32c  lea     r8, [rax+rax*2]
0x14001e330  add     r8, r8
0x14001e333  mov     rax, [r9+r8*8]
0x14001e337  mov     [rsp+1F8h+var_1A8], rax
0x14001e33c  mov     rcx, [r9+r8*8+8]
0x14001e341  sub     rcx, rax
0x14001e344  sar     rcx, 1
0x14001e347  mov     [rsp+1F8h+var_1A0], rcx
0x14001e34c  mov     r8b, [r9+r8*8+28h]
0x14001e351  and     r8b, 1
0x14001e355  mov     r9, r13
0x14001e358  lea     rdx, [rsp+1F8h+var_1A8]
0x14001e35d  mov     rcx, rsi
0x14001e360  call    ?RetractChannel@ManifestProcessor@@AEAAXV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@_NAEBVStringSet@@@Z; ManifestProcessor::RetractChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,bool,StringSet const &)
0x14001e365  inc     ebx
0x14001e367  mov     rdx, [rsp+1F8h+var_190]
0x14001e36c  mov     r9, [rsp+1F8h+var_198]
0x14001e371  sub     rdx, r9
0x14001e374  sar     rdx, 4
0x14001e378  imul    rdx, r14
0x14001e37c  mov     eax, ebx
0x14001e37e  cmp     rax, rdx
0x14001e381  jb      short loc_14001E32A
0x14001e383  cmp     [rsi], dil
0x14001e386  jz      short loc_14001E39E
0x14001e388  lea     r8, [rsp+1F8h+var_98]
0x14001e390  lea     rdx, [rsp+1F8h+var_1A8]
0x14001e395  mov     rcx, [rsi+20h]
0x14001e399  call    ??$emplace@AEAY0CH@_W$0A@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@_N@1@AEAY0CH@_W@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<wchar_t (&)[39],0>(wchar_t (&)[39])
0x14001e39e  mov     r8, [r15]; void *
0x14001e3a1  lea     rdx, [rsp+1F8h+var_98]; wchar_t *
0x14001e3a9  mov     rcx, [rsp+1F8h+hKey]; HKEY
0x14001e3ae  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x14001e3b3  lea     rdx, WPP_GLOBAL_Control
0x14001e3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3c1  cmp     rcx, rdx
0x14001e3c4  jz      short loc_14001E3F5
0x14001e3c6  test    byte ptr [rcx+1Ch], 4
0x14001e3ca  jz      short loc_14001E3F5
0x14001e3cc  cmp     byte ptr [rcx+19h], 5
0x14001e3d0  jb      short loc_14001E3F5
0x14001e3d2  mov     [rsp+1F8h+var_1D0], edi
0x14001e3d6  lea     rax, [rsp+1F8h+var_98]
0x14001e3de  mov     [rsp+1F8h+var_1D8], rax
0x14001e3e3  mov     r9, [rsp+1F8h+var_178]
0x14001e3eb  mov     rcx, [rcx+10h]
0x14001e3ef  call    WPP_SF_SSD
0x14001e3f4  nop
0x14001e3f5  lea     rcx, [rsp+1F8h+var_198]
0x14001e3fa  call    ?_Uninit@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@AEAAXXZ; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(void)
0x14001e3ff  nop
0x14001e400  mov     rcx, [rsp+1F8h+hKey]; hKey
0x14001e405  test    rcx, rcx
0x14001e408  jz      short loc_14001E411
0x14001e40a  call    cs:__imp_RegCloseKey
0x14001e410  nop
0x14001e411  lea     rcx, [rsp+1F8h+var_158]
0x14001e419  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e41e  nop
0x14001e41f  lea     rcx, [rsp+1F8h+var_178]
0x14001e427  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001e42c  mov     rcx, [rsp+1F8h+var_48]
0x14001e434  xor     rcx, rsp; StackCookie
0x14001e437  call    __security_check_cookie
0x14001e43c  add     rsp, 1C0h
0x14001e443  pop     r15
0x14001e445  pop     r14
0x14001e447  pop     r13
0x14001e449  pop     r12
0x14001e44b  pop     rdi
0x14001e44c  pop     rsi
0x14001e44d  pop     rbx
0x14001e44e  retn
```
