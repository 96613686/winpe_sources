# browser::uri_reputation::create_urlrep(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140003cd8`
- end: `0x140004040`
- name: `?create_urlrep@uri_reputation@browser@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000342c`

## callees

- `0x1400024d8`
- `0x140002658`
- `0x140002d28`
- `0x140003258`
- `0x140003cd8`
- `0x140004190`
- `0x1400048a0`
- `0x14000f834`
- `0x140015be0`
- `0x140015dbc`
- `0x1400160f0`
- `0x140018a9c`
- `0x140018b58`
- `0x14001dfb8`
- `0x140025aa0`

## import_xrefs

- `SmartScreen!UriReputationFactory` at `0x140003f74`
- `SmartScreen!UriReputationFactory` at `0x140003f74`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall browser::uri_reputation::create_urlrep(_QWORD *a1)
{
  const WCHAR *v2; // rax
  const WCHAR *v3; // rax
  const WCHAR *v4; // rax
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rsi
  char v10; // bl
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int128 *v13; // rax
  __m128i si128; // xmm0
  __int128 v15; // [rsp+20h] [rbp-E0h] BYREF
  __m128i v16; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+80h] [rbp-80h]
  unsigned __int64 v22[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v23[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v24[5]; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v25[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v26; // [rsp+100h] [rbp+0h]
  _BYTE v27[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v28[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v29[32]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v30; // [rsp+170h] [rbp+70h] BYREF
  __m128i v31; // [rsp+180h] [rbp+80h]
  _QWORD v32[2]; // [rsp+190h] [rbp+90h] BYREF
  __m128i v33; // [rsp+1A0h] [rbp+A0h]
  _QWORD v34[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v35[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v36[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v37[40]; // [rsp+200h] [rbp+100h] BYREF
  char v38[56]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v39; // [rsp+260h] [rbp+160h]
  char v40; // [rsp+268h] [rbp+168h]

  *(_QWORD *)&v15 = L"remote";
  *((_QWORD *)&v15 + 1) = 6;
  v24[0] = (unsigned __int64)L"edge";
  v24[1] = 4;
  v23[0] = (unsigned __int64)L"Safety";
  v23[1] = 6;
  v22[0] = (unsigned __int64)L"Windows";
  v22[1] = 7;
  v17[0] = (unsigned __int64)L"Microsoft";
  v17[1] = 9;
  v2 = (const WCHAR *)path::known_folder((__int64)&v18);
  v3 = (const WCHAR *)operator/((__int64)v25, v2, v17);
  v4 = (const WCHAR *)operator/((__int64)v29, v3, v22);
  v5 = (const WCHAR *)operator/((__int64)v28, v4, v23);
  v6 = (const WCHAR *)operator/((__int64)v27, v5, v24);
  operator/((__int64)v34, v6, (unsigned __int64 *)&v15);
  path::~path((path *)v27);
  path::~path((path *)v28);
  path::~path((path *)v29);
  path::~path((path *)v25);
  path::~path((path *)&v18);
  v7 = (_QWORD *)path::current_module(v24);
  v15 = 0;
  v16 = 0u;
  v8 = v7[2];
  if ( v7[3] > 7u )
    v7 = (_QWORD *)*v7;
  std::wstring::_Construct<2,unsigned short const *>(&v15, v7, v8);
  file_info::file_info((struct std::filesystem::path *)v35, (path *)&v15);
  path::~path((path *)v24);
  v9 = v39;
  v10 = v40;
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"0", 1);
  if ( v10 )
  {
    std::_Integral_to_string<unsigned short,__int64>(&v15, v9);
    std::wstring::_Tidy_deallocate(&v30);
    v30 = v15;
    v31 = v16;
  }
  std::operator+<unsigned short>(v32, L"SmartScreen/", &v30);
  v18 = 1u;
  v11 = v34;
  if ( v34[3] > 7u )
    v11 = (_QWORD *)v34[0];
  *(_QWORD *)&v19 = v11;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  *((_QWORD *)&v19 + 1) = a1;
  v12 = v32;
  if ( v33.m128i_i64[1] > 7uLL )
    v12 = (_QWORD *)v32[0];
  *(_QWORD *)&v20 = v12;
  v13 = &v30;
  if ( v31.m128i_i64[1] > 7uLL )
    v13 = (__int128 *)v30;
  *((_QWORD *)&v20 + 1) = v13;
  v21 = 5;
  v25[0] = v18;
  v25[1] = v19;
  v25[2] = v20;
  v26 = 5;
  UriReputationFactory(v25);
  if ( v33.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v32[0], 2 * v33.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v33 = si128;
  LOWORD(v32[0]) = 0;
  if ( v31.m128i_i64[1] > 7uLL )
  {
    std::_Deallocate<16>(v30, 2 * v31.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v31 = si128;
  LOWORD(v30) = 0;
  std::optional<std::wstring>::~optional<std::wstring>(v38);
  std::optional<std::wstring>::~optional<std::wstring>(v37);
  std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&long PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>>,0>(v36);
  path::~path((path *)v35);
  path::~path((path *)v34);
}

```

## disassembly

```asm
0x140003cd8  push    rbp
0x140003cda  push    rbx
0x140003cdb  push    rsi
0x140003cdc  push    rdi
0x140003cdd  lea     rbp, [rsp-188h]
0x140003ce5  sub     rsp, 288h
0x140003cec  mov     rax, cs:__security_cookie
0x140003cf3  xor     rax, rsp
0x140003cf6  mov     [rbp+1A0h+var_30], rax
0x140003cfd  mov     rdi, rcx
0x140003d00  lea     rax, aRemote; "remote"
0x140003d07  mov     qword ptr [rsp+2A0h+var_280], rax
0x140003d0c  mov     ecx, 6
0x140003d11  mov     qword ptr [rsp+2A0h+var_280+8], rcx
0x140003d16  lea     rax, aEdge; "edge"
0x140003d1d  mov     [rbp+1A0h+var_1F8], rax
0x140003d21  mov     [rbp+1A0h+var_1F0], 4
0x140003d29  lea     rax, aSafety; "Safety"
0x140003d30  mov     [rbp+1A0h+var_208], rax
0x140003d34  mov     [rbp+1A0h+var_200], rcx
0x140003d38  lea     rax, aWindows; "Windows"
0x140003d3f  mov     [rbp+1A0h+var_218], rax
0x140003d43  mov     [rbp+1A0h+var_210], 7
0x140003d4b  lea     rax, aMicrosoft; "Microsoft"
0x140003d52  mov     [rsp+2A0h+var_260], rax
0x140003d57  mov     [rsp+2A0h+var_258], 9
0x140003d60  lea     rcx, [rsp+2A0h+var_250]
0x140003d65  call    ?known_folder@path@@SA?AV1@AEBU_GUID@@@Z; path::known_folder(_GUID const &)
0x140003d6a  nop
0x140003d6b  lea     r8, [rsp+2A0h+var_260]
0x140003d70  mov     rdx, rax
0x140003d73  lea     rcx, [rbp+1A0h+var_1D0]
0x140003d77  call    ??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; operator/(path const &,std::basic_string_view<ushort> const &)
0x140003d7c  nop
0x140003d7d  lea     r8, [rbp+1A0h+var_218]
0x140003d81  mov     rdx, rax
0x140003d84  lea     rcx, [rbp+1A0h+var_150]
0x140003d88  call    ??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; operator/(path const &,std::basic_string_view<ushort> const &)
0x140003d8d  nop
0x140003d8e  lea     r8, [rbp+1A0h+var_208]
0x140003d92  mov     rdx, rax
0x140003d95  lea     rcx, [rbp+1A0h+var_170]
0x140003d99  call    ??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; operator/(path const &,std::basic_string_view<ushort> const &)
0x140003d9e  nop
0x140003d9f  lea     r8, [rbp+1A0h+var_1F8]
0x140003da3  mov     rdx, rax
0x140003da6  lea     rcx, [rbp+1A0h+var_190]
0x140003daa  call    ??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; operator/(path const &,std::basic_string_view<ushort> const &)
0x140003daf  nop
0x140003db0  lea     r8, [rsp+2A0h+var_280]
0x140003db5  mov     rdx, rax
0x140003db8  lea     rcx, [rbp+1A0h+var_F0]
0x140003dbf  call    ??K@YA?AVpath@@AEBV0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; operator/(path const &,std::basic_string_view<ushort> const &)
0x140003dc4  nop
0x140003dc5  lea     rcx, [rbp+1A0h+var_190]; this
0x140003dc9  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003dce  nop
0x140003dcf  lea     rcx, [rbp+1A0h+var_170]; this
0x140003dd3  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003dd8  nop
0x140003dd9  lea     rcx, [rbp+1A0h+var_150]; this
0x140003ddd  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003de2  nop
0x140003de3  lea     rcx, [rbp+1A0h+var_1D0]; this
0x140003de7  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003dec  nop
0x140003ded  lea     rcx, [rsp+2A0h+var_250]; this
0x140003df2  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003df7  lea     rcx, [rbp+1A0h+var_1F8]
0x140003dfb  call    ?current_module@path@@SA?AV1@XZ; path::current_module(void)
0x140003e00  nop
0x140003e01  xorps   xmm0, xmm0
0x140003e04  movups  [rsp+2A0h+var_280], xmm0
0x140003e09  mov     qword ptr [rsp+2A0h+var_270], 0
0x140003e12  mov     qword ptr [rsp+2A0h+var_270+8], 0
0x140003e1b  mov     r8, [rax+10h]
0x140003e1f  cmp     qword ptr [rax+18h], 7
0x140003e24  jbe     short loc_140003E29
0x140003e26  mov     rax, [rax]
0x140003e29  mov     rdx, rax
0x140003e2c  lea     rcx, [rsp+2A0h+var_280]
0x140003e31  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140003e36  lea     rdx, [rsp+2A0h+var_280]; this
0x140003e3b  lea     rcx, [rbp+1A0h+var_D0]; struct std::filesystem::path *
0x140003e42  call    ??0file_info@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; file_info::file_info(std::wstring)
0x140003e47  nop
0x140003e48  lea     rcx, [rbp+1A0h+var_1F8]; this
0x140003e4c  call    ??1path@@QEAA@XZ; path::~path(void)
0x140003e51  mov     rsi, [rbp+1A0h+var_40]
0x140003e58  mov     bl, [rbp+1A0h+var_38]
0x140003e5e  xorps   xmm0, xmm0
0x140003e61  movups  [rbp+1A0h+var_130], xmm0
0x140003e65  xorps   xmm1, xmm1
0x140003e68  movdqu  [rbp+1A0h+var_120], xmm1
0x140003e70  mov     r8d, 1
0x140003e76  lea     rdx, a0; "0"
0x140003e7d  lea     rcx, [rbp+1A0h+var_130]
0x140003e81  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003e86  nop
0x140003e87  test    bl, bl
0x140003e89  jz      short loc_140003EB6
0x140003e8b  mov     rdx, rsi
0x140003e8e  lea     rcx, [rsp+2A0h+var_280]
0x140003e93  call    ??$_Integral_to_string@G_J@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_J@Z; std::_Integral_to_string<ushort,__int64>(__int64)
0x140003e98  lea     rcx, [rbp+1A0h+var_130]
0x140003e9c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140003ea1  movups  xmm0, [rsp+2A0h+var_280]
0x140003ea6  movups  [rbp+1A0h+var_130], xmm0
0x140003eaa  movups  xmm1, [rsp+2A0h+var_270]
0x140003eaf  movups  [rbp+1A0h+var_120], xmm1
0x140003eb6  lea     r8, [rbp+1A0h+var_130]
0x140003eba  lea     rdx, aSmartscreen; "SmartScreen/"
0x140003ec1  lea     rcx, [rbp+1A0h+var_110]
0x140003ec8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x140003ecd  mov     byte ptr [rsp+2A0h+var_250], 1
0x140003ed2  xor     eax, eax
0x140003ed4  mov     dword ptr [rsp+2A0h+var_250+1], eax
0x140003ed8  mov     word ptr [rsp+2A0h+var_250+5], ax
0x140003edd  mov     byte ptr [rsp+2A0h+var_250+7], al
0x140003ee1  mov     qword ptr [rsp+2A0h+var_250+8], rax
0x140003ee6  lea     rax, [rbp+1A0h+var_F0]
0x140003eed  cmp     [rbp+1A0h+var_D8], 7
0x140003ef5  cmova   rax, [rbp+1A0h+var_F0]
0x140003efd  mov     qword ptr [rsp+2A0h+var_240], rax
0x140003f02  cmp     qword ptr [rdi+18h], 7
0x140003f07  jbe     short loc_140003F0C
0x140003f09  mov     rdi, [rdi]
0x140003f0c  mov     qword ptr [rsp+2A0h+var_240+8], rdi
0x140003f11  lea     rax, [rbp+1A0h+var_110]
0x140003f18  cmp     [rbp+1A0h+var_F8], 7
0x140003f20  cmova   rax, [rbp+1A0h+var_110]
0x140003f28  mov     qword ptr [rsp+2A0h+var_230], rax
0x140003f2d  lea     rax, [rbp+1A0h+var_130]
0x140003f31  cmp     qword ptr [rbp+1A0h+var_120+8], 7
0x140003f39  cmova   rax, qword ptr [rbp+1A0h+var_130]
0x140003f3e  mov     qword ptr [rsp+2A0h+var_230+8], rax
0x140003f43  mov     [rbp+1A0h+var_220], 5
0x140003f4b  movups  xmm0, [rsp+2A0h+var_250]
0x140003f50  movaps  [rbp+1A0h+var_1D0], xmm0
0x140003f54  movups  xmm1, [rsp+2A0h+var_240]
0x140003f59  movaps  [rbp+1A0h+var_1C0], xmm1
0x140003f5d  movups  xmm0, [rsp+2A0h+var_230]
0x140003f62  movaps  [rbp+1A0h+var_1B0], xmm0
0x140003f66  movsd   xmm1, [rbp+1A0h+var_220]
0x140003f6b  movsd   [rbp+1A0h+var_1A0], xmm1
0x140003f70  lea     rcx, [rbp+1A0h+var_1D0]
0x140003f74  call    cs:__imp_UriReputationFactory
0x140003f7a  mov     rdx, [rbp+1A0h+var_F8]
0x140003f81  cmp     rdx, 7
0x140003f85  jbe     short loc_140003F9B
0x140003f87  lea     rdx, ds:2[rdx*2]
0x140003f8f  mov     rcx, [rbp+1A0h+var_110]
0x140003f96  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003f9b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140003fa3  movdqu  xmmword ptr [rbp+0A0h], xmm0
0x140003fab  xor     eax, eax
0x140003fad  mov     word ptr [rbp+1A0h+var_110], ax
0x140003fb4  mov     rdx, qword ptr [rbp+1A0h+var_120+8]
0x140003fbb  cmp     rdx, 7
0x140003fbf  jbe     short loc_140003FDA
0x140003fc1  lea     rdx, ds:2[rdx*2]
0x140003fc9  mov     rcx, qword ptr [rbp+1A0h+var_130]
0x140003fcd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140003fd2  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140003fda  movdqu  [rbp+1A0h+var_120], xmm0
0x140003fe2  xor     eax, eax
0x140003fe4  mov     word ptr [rbp+1A0h+var_130], ax
0x140003fe8  lea     rcx, [rbp+1A0h+var_78]
0x140003fef  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x140003ff4  lea     rcx, [rbp+1A0h+var_A0]
0x140003ffb  call    ??1?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x140004000  lea     rcx, [rbp+1A0h+var_B0]
0x140004007  call    ??1?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_FILE_INFO@@P6AJPEAU1@@Z$1?PicFreeFileInfo@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FILE_INFO *,long (*)(_FILE_INFO *),&PicFreeFileInfo(_FILE_INFO *),wistd::integral_constant<unsigned __int64,0>,_FILE_INFO *,_FILE_INFO *,0,std::nullptr_t>>>,0>(void)
0x14000400c  lea     rcx, [rbp+1A0h+var_D0]; this
0x140004013  call    ??1path@@QEAA@XZ; path::~path(void)
0x140004018  nop
0x140004019  lea     rcx, [rbp+1A0h+var_F0]; this
0x140004020  call    ??1path@@QEAA@XZ; path::~path(void)
0x140004025  mov     rcx, [rbp+1A0h+var_30]
0x14000402c  xor     rcx, rsp; StackCookie
0x14000402f  call    __security_check_cookie
0x140004034  add     rsp, 288h
0x14000403b  pop     rdi
0x14000403c  pop     rsi
0x14000403d  pop     rbx
0x14000403e  pop     rbp
0x14000403f  retn
```
