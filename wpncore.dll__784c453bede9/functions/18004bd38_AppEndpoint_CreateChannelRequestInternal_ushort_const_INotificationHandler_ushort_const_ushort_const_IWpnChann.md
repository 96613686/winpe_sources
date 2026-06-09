# AppEndpoint::CreateChannelRequestInternal(ushort const *,INotificationHandler *,ushort const *,ushort const *,IWpnChannelRequest *)

- ea: `0x18004bd38`
- end: `0x18004c0fc`
- name: `?CreateChannelRequestInternal@AppEndpoint@@AEAAJPEBGPEAUINotificationHandler@@00PEAUIWpnChannelRequest@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(AppEndpoint *__hidden this, const unsigned __int16 *, struct INotificationHandler *, const unsigned __int16 *, const unsigned __int16 *, struct IWpnChannelRequest *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008bae0`
- `0x1800cd710`
- `0x1800ce330`

## callees

- `0x18000e5f4`
- `0x180013360`
- `0x180014160`
- `0x18001bf30`
- `0x18004aefc`
- `0x18004bd38`
- `0x18004c9e4`
- `0x18004ca20`
- `0x18004d75c`
- `0x18004d8c4`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bdee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bdee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004be01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004be01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c04d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c05e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bdf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c04d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c05e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppEndpoint::CreateChannelRequestInternal(
        AppEndpoint *this,
        unsigned __int16 *a2,
        struct INotificationHandler *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWpnChannelRequest *a6)
{
  const unsigned __int16 *v6; // rsi
  const unsigned __int16 *v8; // r12
  unsigned int v9; // ebx
  int v10; // eax
  __int64 (__fastcall *v11)(struct INotificationHandler *, LPVOID *); // r13
  int v12; // eax
  int v13; // eax
  unsigned __int64 v14; // rdx
  wil *v15; // rcx
  const wchar_t *v16; // r14
  const wchar_t *v17; // r15
  unsigned __int8 v18; // cl
  __int64 v19; // rcx
  int v20; // r12d
  __int64 v21; // rbx
  __int64 v22; // r8
  __int64 v23; // r8
  int v24; // r8d
  int v25; // edx
  __m128i si128; // xmm0
  __int64 v28; // rcx
  int v29; // eax
  int v30; // [rsp+20h] [rbp-128h]
  int v31; // [rsp+20h] [rbp-128h]
  bool v32; // [rsp+40h] [rbp-108h] BYREF
  bool v33; // [rsp+41h] [rbp-107h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-104h]
  LPVOID pv; // [rsp+48h] [rbp-100h] BYREF
  LPCWSTR pszPath[2]; // [rsp+50h] [rbp-F8h] BYREF
  AppEndpoint *v37; // [rsp+60h] [rbp-E8h] BYREF
  int v38; // [rsp+68h] [rbp-E0h]
  struct IWpnChannelRequest *v39; // [rsp+70h] [rbp-D8h]
  unsigned __int16 *v40; // [rsp+78h] [rbp-D0h]
  unsigned __int16 *v41; // [rsp+80h] [rbp-C8h]
  struct IWpnChannelRequest *v42; // [rsp+88h] [rbp-C0h]
  const unsigned __int16 *v43; // [rsp+90h] [rbp-B8h]
  __int128 v44; // [rsp+A0h] [rbp-A8h] BYREF
  __m128i v45; // [rsp+B0h] [rbp-98h]
  __int128 v46; // [rsp+C0h] [rbp-88h] BYREF
  __m128i v47; // [rsp+D0h] [rbp-78h]
  __int128 v48; // [rsp+E0h] [rbp-68h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  try
  {
    v6 = a4;
    v41 = a2;
    v37 = this;
    v8 = a4;
    v43 = a4;
    v40 = a5;
    v39 = a6;
    v42 = a6;
    v9 = 0;
    v34 = 0;
    v33 = 0;
    v32 = 0;
    pv = 0;
    pszPath[0] = 0;
    v10 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPCWSTR *))(*(_QWORD *)a3 + 24LL))(a3, pszPath);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1235,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v10,
        v30);
    v11 = *(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a3 + 48LL);
    pv = 0;
    v12 = v11(a3, &pv);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1237,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v12,
        v30);
    v13 = AppEndpoint::CreateChannelRequestHelper(v37, v41, a3, v6, v40, v39, &v33, &v32);
    v15 = retaddr;
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1240,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
        (const char *)(unsigned int)v13,
        v31);
  }
  catch ( ... )
  {
    v34 = wil::ResultFromCaughtException(v15);
    if ( v34 == -2143419896 )
    {
      if ( byte_18015DE45 < 0 )
        McTemplateU0z_EventWriteTransfer(v28, WPNEND_ACCESS_DENIED, pszPath[0]);
      CRPCTimeout::CRPCTimeout((CRPCTimeout *)&v44, 0x3A98u);
      v37 = 0;
      v38 = 0;
      v29 = (*(__int64 (__fastcall **)(struct IWpnChannelRequest *, __int64, _QWORD, _QWORD))(*(_QWORD *)v42 + 24LL))(
              v42,
              2151547400LL,
              0,
              0);
      v34 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1250,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\appendpoint.cpp",
          (const char *)(unsigned int)v29,
          (int)&v37);
        CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&v44);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pszPath);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
        return v34;
      }
      v34 = 0;
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&v44);
      CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&v44);
    }
    v9 = v34;
    v8 = v43;
    v6 = v43;
  }
  v16 = L"Unknown";
  v17 = L"Unknown";
  if ( pv )
    v17 = (const wchar_t *)pv;
  if ( !v8 )
    v6 = L"Unknown";
  v18 = (unsigned __int8)pszPath[0];
  if ( pszPath[0] )
    v16 = CensorFilePath(pszPath[0]);
  if ( WpncoreTelemetry::IsEnabled(v18, v14) )
  {
    v20 = wil::details::static_lazy<WpncoreTelemetry>::get(
            v19,
            _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
    v48 = 0;
    v49 = 0;
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( v17[v22] );
    std::wstring::_Construct<1,unsigned short const *>(&v48, v17);
    v46 = 0;
    v47 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v6[v23] );
    std::wstring::_Construct<1,unsigned short const *>(&v46, v6);
    v44 = 0;
    v45 = 0;
    do
      ++v21;
    while ( v16[v21] );
    std::wstring::_Construct<1,unsigned short const *>(&v44, v16);
    v9 = v34;
    LOBYTE(v24) = v32;
    LOBYTE(v25) = v33;
    WpncoreTelemetry::ChannelRequestedByPlatform_(v20, v25, v24, v34, (__int64)&v44, (__int64)&v46, (__int64)&v48);
    if ( v45.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v44, 2 * v45.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v45 = si128;
    LOWORD(v44) = 0;
    if ( v47.m128i_i64[1] > 7uLL )
    {
      std::_Deallocate<16>(v46, 2 * v47.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v47 = si128;
    LOWORD(v46) = 0;
    if ( *((_QWORD *)&v49 + 1) > 7u )
      std::_Deallocate<16>(v48, 2LL * *((_QWORD *)&v49 + 1) + 2);
  }
  if ( pszPath[0] )
    CoTaskMemFree((LPVOID)pszPath[0]);
  if ( pv )
    CoTaskMemFree(pv);
  return v9;
}

```

## disassembly

```asm
0x18004bd38  push    rbx
0x18004bd3a  push    rsi
0x18004bd3b  push    rdi
0x18004bd3c  push    r12
0x18004bd3e  push    r13
0x18004bd40  push    r14
0x18004bd42  push    r15
0x18004bd44  sub     rsp, 110h
0x18004bd4b  mov     rax, cs:__security_cookie
0x18004bd52  xor     rax, rsp
0x18004bd55  mov     [rsp+148h+var_48], rax
0x18004bd5d  mov     rsi, r9
0x18004bd60  mov     r14, r8
0x18004bd63  mov     [rsp+148h+var_C8], rdx
0x18004bd6b  mov     [rsp+148h+var_E8], rcx
0x18004bd70  mov     r12, r9
0x18004bd73  mov     [rsp+148h+var_B8], r9
0x18004bd7b  mov     rax, [rsp+148h+arg_20]
0x18004bd83  mov     [rsp+148h+var_D0], rax
0x18004bd88  mov     rax, [rsp+148h+arg_28]
0x18004bd90  mov     [rsp+148h+var_D8], rax
0x18004bd95  mov     [rsp+148h+var_C0], rax
0x18004bd9d  xor     edi, edi
0x18004bd9f  mov     ebx, edi
0x18004bda1  mov     [rsp+148h+var_104], ebx
0x18004bda5  mov     [rsp+148h+var_107], dil
0x18004bdaa  mov     [rsp+148h+var_108], dil
0x18004bdaf  mov     [rsp+148h+pv], rdi
0x18004bdb4  mov     [rsp+148h+pszPath], rdi
0x18004bdb9  mov     rax, [r8]
0x18004bdbc  lea     rdx, [rsp+148h+pszPath]
0x18004bdc1  mov     rcx, r8
0x18004bdc4  mov     rax, [rax+18h]
0x18004bdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdcd  mov     rcx, [rsp+148h]; this
0x18004bdd5  test    eax, eax
0x18004bdd7  js      loc_18004C089
0x18004bddd  mov     rax, [r14]
0x18004bde0  mov     r13, [rax+30h]
0x18004bde4  mov     r15, [rsp+148h+pv]
0x18004bde9  test    r15, r15
0x18004bdec  jz      short loc_18004BE09
0x18004bdee  call    cs:__imp_GetLastError
0x18004bdf4  mov     ebx, eax
0x18004bdf6  mov     rcx, r15; pv
0x18004bdf9  call    cs:__imp_CoTaskMemFree
0x18004bdff  mov     ecx, ebx; dwErrCode
0x18004be01  call    cs:__imp_SetLastError
0x18004be07  mov     ebx, edi
0x18004be09  mov     [rsp+148h+pv], rdi
0x18004be0e  lea     rdx, [rsp+148h+pv]
0x18004be13  mov     rcx, r14
0x18004be16  mov     rax, r13
0x18004be19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be1e  mov     rcx, [rsp+148h]; this
0x18004be26  test    eax, eax
0x18004be28  js      loc_18004C09D
0x18004be2e  lea     rax, [rsp+148h+var_108]
0x18004be33  mov     [rsp+148h+var_110], rax; bool *
0x18004be38  lea     rax, [rsp+148h+var_107]
0x18004be3d  mov     [rsp+148h+var_118], rax; bool *
0x18004be42  mov     rax, [rsp+148h+var_D8]
0x18004be47  mov     [rsp+148h+var_120], rax; struct IWpnChannelRequest *
0x18004be4c  mov     rax, [rsp+148h+var_D0]
0x18004be51  mov     [rsp+148h+var_128], rax; int
0x18004be56  mov     r9, rsi; unsigned __int16 *
0x18004be59  mov     r8, r14; struct INotificationHandler *
0x18004be5c  mov     rdx, [rsp+148h+var_C8]; unsigned __int16 *
0x18004be64  mov     rcx, [rsp+148h+var_E8]; this
0x18004be69  call    ?CreateChannelRequestHelper@AppEndpoint@@AEAAJPEBGPEAUINotificationHandler@@00PEAUIWpnChannelRequest@@AEA_N3@Z; AppEndpoint::CreateChannelRequestHelper(ushort const *,INotificationHandler *,ushort const *,ushort const *,IWpnChannelRequest *,bool &,bool &)
0x18004be6e  mov     rcx, [rsp+148h]; this
0x18004be76  test    eax, eax
0x18004be78  js      loc_18004C0B1
0x18004be7e  lea     r14, aUnknown_0; "Unknown"
0x18004be85  mov     r15, r14
0x18004be88  cmp     [rsp+148h+pv], rdi
0x18004be8d  cmovnz  r15, [rsp+148h+pv]
0x18004be93  test    r12, r12
0x18004be96  cmovz   rsi, r14
0x18004be9a  mov     rcx, [rsp+148h+pszPath]; pszPath
0x18004be9f  test    rcx, rcx
0x18004bea2  jz      short loc_18004BEAC
0x18004bea4  call    ?CensorFilePath@@YAPEBGPEBG@Z; CensorFilePath(ushort const *)
0x18004bea9  mov     r14, rax
0x18004beac  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18004beb1  test    al, al
0x18004beb3  jz      loc_18004C043
0x18004beb9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x18004bec0  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x18004bec5  mov     r12, rax
0x18004bec8  xorps   xmm0, xmm0
0x18004becb  movups  [rsp+148h+var_68], xmm0
0x18004bed3  xorps   xmm1, xmm1
0x18004bed6  movdqu  [rsp+148h+var_58], xmm1
0x18004bedf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004bee3  mov     r8, rbx
0x18004bee6  inc     r8
0x18004bee9  cmp     [r15+r8*2], di
0x18004beee  jnz     short loc_18004BEE6
0x18004bef0  mov     rdx, r15
0x18004bef3  lea     rcx, [rsp+148h+var_68]
0x18004befb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004bf00  xorps   xmm0, xmm0
0x18004bf03  movups  [rsp+148h+var_88], xmm0
0x18004bf0b  xorps   xmm1, xmm1
0x18004bf0e  movdqu  [rsp+148h+var_78], xmm1
0x18004bf17  mov     r8, rbx
0x18004bf1a  inc     r8
0x18004bf1d  cmp     [rsi+r8*2], di
0x18004bf22  jnz     short loc_18004BF1A
0x18004bf24  mov     rdx, rsi
0x18004bf27  lea     rcx, [rsp+148h+var_88]
0x18004bf2f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004bf34  xorps   xmm0, xmm0
0x18004bf37  movups  [rsp+148h+var_A8], xmm0
0x18004bf3f  xorps   xmm1, xmm1
0x18004bf42  movdqu  [rsp+148h+var_98], xmm1
0x18004bf4b  inc     rbx
0x18004bf4e  cmp     [r14+rbx*2], di
0x18004bf53  jnz     short loc_18004BF4B
0x18004bf55  mov     r8, rbx
0x18004bf58  mov     rdx, r14
0x18004bf5b  lea     rcx, [rsp+148h+var_A8]
0x18004bf63  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004bf68  lea     rax, [rsp+148h+var_68]
0x18004bf70  mov     [rsp+148h+var_118], rax
0x18004bf75  lea     rax, [rsp+148h+var_88]
0x18004bf7d  mov     [rsp+148h+var_120], rax
0x18004bf82  lea     rax, [rsp+148h+var_A8]
0x18004bf8a  mov     [rsp+148h+var_128], rax
0x18004bf8f  mov     ebx, [rsp+148h+var_104]
0x18004bf93  mov     r9d, ebx
0x18004bf96  mov     r8b, [rsp+148h+var_108]
0x18004bf9b  mov     dl, [rsp+148h+var_107]
0x18004bf9f  mov     rcx, r12
0x18004bfa2  call    ?ChannelRequestedByPlatform_@WpncoreTelemetry@@QEAAX_N0JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; WpncoreTelemetry::ChannelRequestedByPlatform_(bool,bool,long,std::wstring const &,std::wstring const &,std::wstring const &)
0x18004bfa7  mov     rdx, qword ptr [rsp+148h+var_98+8]
0x18004bfaf  cmp     rdx, 7
0x18004bfb3  jbe     short loc_18004BFCA
0x18004bfb5  lea     rdx, ds:2[rdx*2]
0x18004bfbd  mov     rcx, qword ptr [rsp+148h+var_A8]
0x18004bfc5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004bfca  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18004bfd2  movdqu  [rsp+148h+var_98], xmm0
0x18004bfdb  mov     word ptr [rsp+148h+var_A8], di
0x18004bfe3  mov     rdx, qword ptr [rsp+148h+var_78+8]
0x18004bfeb  cmp     rdx, 7
0x18004bfef  jbe     short loc_18004C00E
0x18004bff1  lea     rdx, ds:2[rdx*2]
0x18004bff9  mov     rcx, qword ptr [rsp+148h+var_88]
0x18004c001  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004c006  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18004c00e  movdqu  [rsp+148h+var_78], xmm0
0x18004c017  mov     word ptr [rsp+148h+var_88], di
0x18004c01f  mov     rdx, qword ptr [rsp+148h+var_58+8]
0x18004c027  cmp     rdx, 7
0x18004c02b  jbe     short loc_18004C043
0x18004c02d  lea     rdx, ds:2[rdx*2]
0x18004c035  mov     rcx, qword ptr [rsp+148h+var_68]
0x18004c03d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004c042  nop
0x18004c043  mov     rcx, [rsp+148h+pszPath]; pv
0x18004c048  test    rcx, rcx
0x18004c04b  jz      short loc_18004C054
0x18004c04d  call    cs:__imp_CoTaskMemFree
0x18004c053  nop
0x18004c054  mov     rcx, [rsp+148h+pv]; pv
0x18004c059  test    rcx, rcx
0x18004c05c  jz      short loc_18004C064
0x18004c05e  call    cs:__imp_CoTaskMemFree
0x18004c064  mov     eax, ebx
0x18004c066  mov     rcx, [rsp+148h+var_48]
0x18004c06e  xor     rcx, rsp; StackCookie
0x18004c071  call    __security_check_cookie
0x18004c076  add     rsp, 110h
0x18004c07d  pop     r15
0x18004c07f  pop     r14
0x18004c081  pop     r13
0x18004c083  pop     r12
0x18004c085  pop     rdi
0x18004c086  pop     rsi
0x18004c087  pop     rbx
0x18004c088  retn
0x18004c089  mov     r9d, eax; char *
0x18004c08c  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004c093  mov     edx, 1235h; void *
0x18004c098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c09d  mov     r9d, eax; char *
0x18004c0a0  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004c0a7  mov     edx, 1237h; void *
0x18004c0ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c0b1  mov     r9d, eax; char *
0x18004c0b4  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004c0bb  mov     edx, 1240h; void *
0x18004c0c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c0c6  lea     rcx, [rsp+148h+pszPath]
0x18004c0cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c0d0  nop
0x18004c0d1  lea     rcx, [rsp+148h+pv]
0x18004c0d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c0db  mov     eax, [rsp+148h+var_104]
0x18004c0df  jmp     short loc_18004C066
0x18004c0e1  xor     edi, edi
0x18004c0e3  mov     ebx, [rsp+148h+var_104]
0x18004c0e7  mov     [rsp+148h+var_104], ebx
0x18004c0eb  mov     r12, [rsp+148h+var_B8]
0x18004c0f3  mov     rsi, r12
0x18004c0f6  jmp     loc_18004BE7E
```
