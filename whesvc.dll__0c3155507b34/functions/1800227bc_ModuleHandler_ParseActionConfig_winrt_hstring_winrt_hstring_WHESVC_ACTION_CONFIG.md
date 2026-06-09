# ModuleHandler::ParseActionConfig(winrt::hstring,winrt::hstring *,_WHESVC_ACTION_CONFIG * *)

- ea: `0x1800227bc`
- end: `0x180022fc6`
- name: `?ParseActionConfig@ModuleHandler@@AEAAJUhstring@winrt@@PEAU23@PEAPEAU_WHESVC_ACTION_CONFIG@@@Z`
- size: `2058`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 **, volatile signed __int32 **, _QWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c32c`

## callees

- `0x1800032e0`
- `0x18000370c`
- `0x180003be4`
- `0x180003da4`
- `0x180003e10`
- `0x180003e34`
- `0x1800066dc`
- `0x180009044`
- `0x1800115e0`
- `0x180016b28`
- `0x180017b60`
- `0x180018780`
- `0x18001a868`
- `0x18001c0e4`
- `0x1800202a8`
- `0x180020a8c`
- `0x1800227bc`
- `0x180022fcc`
- `0x1800256ac`
- `0x180025dcc`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800228b5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022915`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022abc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022ce3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e68`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e73`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022f13`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022f94`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800228b5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022915`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022abc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022ce3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e68`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022e73`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022f13`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022f94`

## string_xrefs

- `0x1800228d3`: `actionPath`
- `0x18002298a`: `actionPath`
- `0x180022932`: `actionConfig`
- `0x180022ad9`: `actionConfig`

## pseudocode

```c
__int64 __fastcall ModuleHandler::ParseActionConfig(
        __int64 a1,
        volatile signed __int32 **a2,
        volatile signed __int32 **a3,
        _QWORD *a4)
{
  _QWORD *v4; // r12
  int v7; // eax
  __int64 v8; // r15
  volatile signed __int32 **NamedString; // rax
  volatile signed __int32 *v10; // r12
  volatile signed __int32 *v11; // rbx
  int v12; // eax
  HANDLE v13; // rax
  void *v14; // rbx
  int v15; // eax
  HANDLE v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // r12d
  int v22; // eax
  __int64 v23; // rcx
  __int64 *v24; // r15
  int v25; // eax
  unsigned int v26; // r13d
  void *v27; // rbx
  int v28; // eax
  HANDLE v29; // rax
  volatile signed __int32 *v30; // rbx
  int v31; // esi
  HANDLE v32; // rax
  volatile signed __int32 *v34; // rbx
  const wchar_t *v35; // rdx
  __int64 v36; // r13
  __int128 v37; // xmm6
  __int64 v38; // xmm7_8
  __int64 v39; // rax
  int v40; // eax
  HANDLE v41; // rax
  volatile signed __int32 *v42; // rbx
  int v43; // esi
  HANDLE v44; // rax
  volatile signed __int32 *v45; // rbx
  int v46; // esi
  HANDLE v47; // rax
  volatile signed __int32 *v48; // rbx
  int v49; // esi
  HANDLE ProcessHeap; // rax
  __int64 v51; // [rsp+20h] [rbp-148h] BYREF
  __int64 *v52; // [rsp+28h] [rbp-140h] BYREF
  LPVOID v53; // [rsp+30h] [rbp-138h] BYREF
  LPVOID v54; // [rsp+38h] [rbp-130h] BYREF
  __int64 v55; // [rsp+40h] [rbp-128h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-120h] BYREF
  __int64 v57; // [rsp+50h] [rbp-118h] BYREF
  _BYTE v58[24]; // [rsp+58h] [rbp-110h] BYREF
  _QWORD *v59; // [rsp+70h] [rbp-F8h]
  volatile signed __int32 **v60; // [rsp+78h] [rbp-F0h]
  LPVOID *v61; // [rsp+80h] [rbp-E8h] BYREF
  int v62; // [rsp+88h] [rbp-E0h]
  _DWORD *v63; // [rsp+90h] [rbp-D8h]
  _DWORD v64[4]; // [rsp+98h] [rbp-D0h] BYREF
  const wchar_t *v65; // [rsp+A8h] [rbp-C0h]
  char v66[8]; // [rsp+B8h] [rbp-B0h] BYREF
  int v67; // [rsp+C0h] [rbp-A8h]
  _QWORD v68[4]; // [rsp+C8h] [rbp-A0h] BYREF
  __int128 *v69; // [rsp+E8h] [rbp-80h] BYREF
  __int128 v70; // [rsp+F0h] [rbp-78h] BYREF
  const wchar_t *v71; // [rsp+100h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v4 = a4;
  v59 = a4;
  v60 = a2;
  v68[0] = *a2;
  lpMem = v68;
  v52 = &qword_180034AF8;
  _InterlockedIncrement64(&qword_180034AF8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    v55 = 0;
    *(_DWORD *)v58 = 0;
    *(_OWORD *)&v58[8] = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
                                                               + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
           v68[0],
           &v55);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, v58);
    v8 = v55;
    v51 = v55;
    _InterlockedAdd64(&qword_180034AF8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_180034AF8, 0xFFFFFFFFFFFFFFFFuLL);
    winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_ &>(
      0,
      &v51,
      &lpMem);
    v8 = v51;
    v55 = v51;
  }
  if ( aActionpath[10] )
    abort();
  *(_QWORD *)&v70 = 0xA00000001LL;
  v71 = L"actionPath";
  v69 = &v70;
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v51,
                           &v69) )
    goto LABEL_84;
  if ( aActionconfig[12] )
    abort();
  *(_QWORD *)&v70 = 0xC00000001LL;
  v71 = L"actionConfig";
  v69 = &v70;
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           &v51,
                           &v69) )
  {
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x80070057LL,
      v51);
    if ( v8 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v51);
    v48 = *a2;
    if ( *a2 )
    {
      v49 = _InterlockedDecrement(v48 + 6);
      if ( v49 )
      {
        if ( v49 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v48);
      }
      *a2 = 0;
    }
    return 2147942487LL;
  }
  if ( aActionpath[10] )
    goto LABEL_81;
  *(_QWORD *)&v70 = 0xA00000001LL;
  v71 = L"actionPath";
  v69 = &v70;
  NamedString = (volatile signed __int32 **)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                              &v51,
                                              &lpMem,
                                              &v69);
  if ( a3 != NamedString )
  {
    v10 = *NamedString;
    *NamedString = 0;
    v11 = *a3;
    if ( *a3 )
    {
      v12 = _InterlockedDecrement(v11 + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          goto LABEL_81;
      }
      else
      {
        v13 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v13, 0, (LPVOID)v11);
      }
    }
    *a3 = v10;
    v4 = v59;
  }
  v14 = lpMem;
  if ( !lpMem )
    goto LABEL_22;
  v15 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
  if ( !v15 )
  {
    v16 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v16, 0, v14);
    goto LABEL_22;
  }
  if ( v15 < 0 )
LABEL_81:
    abort();
LABEL_22:
  v17 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 0x40u);
    *(_DWORD *)v18 = 0;
    v19 = operator new(0x48u);
    *v19 = v19;
    v19[1] = v19;
    v18[1] = v19;
    v18[3] = 0;
    v18[4] = 0;
    v18[5] = 0;
    v18[6] = 7;
    v18[7] = 8;
    *(_DWORD *)v18 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
      v18 + 3,
      16,
      v18[1]);
    *v4 = v18;
    if ( aActionconfig[12] )
      abort();
    v64[0] = 1;
    v64[1] = 12;
    v65 = L"actionConfig";
    v63 = v64;
    v54 = 0;
    *(_DWORD *)v58 = 0;
    *(_OWORD *)&v58[8] = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _DWORD *, LPVOID *))(*(_QWORD *)v8 + 72LL))(v8, v64, &v54);
    if ( v20 < 0 )
      winrt::throw_hresult((unsigned int)v20, v58);
    v53 = v54;
    v61 = &v53;
    v21 = 0;
    v62 = 0;
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
      &v53,
      v66);
    while ( 1 )
    {
      if ( v21 == v67 )
      {
        if ( v53 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v53);
        if ( v55 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v51);
        v42 = *a2;
        if ( *a2 )
        {
          v43 = _InterlockedDecrement(v42 + 6);
          if ( v43 )
          {
            if ( v43 < 0 )
              abort();
          }
          else
          {
            v44 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v44, 0, (LPVOID)v42);
          }
          *a2 = 0;
        }
        return 0;
      }
      winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v61, &v57);
      memset(v58, 0, sizeof(v58));
      v54 = 0;
      v52 = 0;
      LODWORD(v69) = 0;
      v70 = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v57 + 96LL))(v57, &v52);
      if ( v22 < 0 )
        winrt::throw_hresult((unsigned int)v22, &v69);
      v24 = v52;
      lpMem = v52;
      if ( v52 )
        (*(void (__fastcall **)(__int64 *))(*v52 + 8))(v52);
      v25 = ModuleHandler::ParseConfigValue(v23, &v52, &v54, v58);
      v26 = v25;
      if ( v25 < 0 )
        break;
      v34 = (volatile signed __int32 *)v54;
      if ( v54 )
        v35 = (const wchar_t *)*((_QWORD *)v54 + 2);
      else
        v35 = &WideCharStr;
      v36 = *v59;
      v37 = *(_OWORD *)v58;
      v38 = *(_QWORD *)&v58[16];
      std::wstring::wstring(&v69, v35);
      v39 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Try_emplace<std::wstring,>(
                         v36,
                         v68,
                         &v69);
      *(_OWORD *)(v39 + 48) = v37;
      *(_QWORD *)(v39 + 64) = v38;
      std::wstring::~wstring(&v69);
      if ( v24 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&lpMem);
      if ( v34 )
      {
        v40 = _InterlockedDecrement(v34 + 6);
        if ( v40 )
        {
          if ( v40 < 0 )
            goto LABEL_63;
        }
        else
        {
          v41 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v41, 0, (LPVOID)v34);
        }
      }
      if ( v57 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v57);
      v62 = ++v21;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)(unsigned int)v25,
      v51);
    if ( v24 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&lpMem);
    v27 = v54;
    if ( v54 )
    {
      v28 = _InterlockedDecrement((volatile signed __int32 *)v54 + 6);
      if ( v28 )
      {
        if ( v28 < 0 )
LABEL_63:
          abort();
      }
      else
      {
        v29 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v29, 0, v27);
      }
    }
    if ( v57 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v57);
    if ( v53 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v53);
    if ( v55 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v51);
    v30 = *a2;
    if ( *a2 )
    {
      v31 = _InterlockedDecrement(v30 + 6);
      if ( v31 )
      {
        if ( v31 < 0 )
          abort();
      }
      else
      {
        v32 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v32, 0, (LPVOID)v30);
      }
      *a2 = 0;
    }
    return v26;
  }
  else
  {
    *v4 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
      (const char *)0x8007000ELL,
      v51);
    if ( v8 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v51);
    v45 = *a2;
    if ( *a2 )
    {
      v46 = _InterlockedDecrement(v45 + 6);
      if ( v46 )
      {
        if ( v46 < 0 )
          abort();
      }
      else
      {
        v47 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v47, 0, (LPVOID)v45);
      }
      *a2 = 0;
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800227bc  mov     r11, rsp
0x1800227bf  push    rbx
0x1800227c0  push    rsi
0x1800227c1  push    rdi
0x1800227c2  push    r12
0x1800227c4  push    r13
0x1800227c6  push    r14
0x1800227c8  push    r15
0x1800227ca  sub     rsp, 130h
0x1800227d1  movaps  xmmword ptr [r11-48h], xmm6
0x1800227d6  movaps  xmmword ptr [r11-58h], xmm7
0x1800227db  mov     rax, cs:__security_cookie
0x1800227e2  xor     rax, rsp
0x1800227e5  mov     [rsp+168h+var_60], rax
0x1800227ed  mov     r12, r9
0x1800227f0  mov     [rsp+168h+var_F8], r9
0x1800227f5  mov     r13, r8
0x1800227f8  mov     r14, rdx
0x1800227fb  mov     [rsp+168h+var_F0], rdx
0x180022800  xor     edi, edi
0x180022802  mov     rax, [rdx]
0x180022805  mov     [r11-0A0h], rax
0x18002280c  lea     rax, [r11-0A0h]
0x180022813  mov     [rsp+168h+lpMem], rax
0x180022818  lea     rax, qword_180034AF8
0x18002281f  mov     [rsp+168h+var_140], rax
0x180022824  lock inc cs:qword_180034AF8
0x18002282c  mov     rcx, cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x180022833  test    rcx, rcx
0x180022836  jz      short loc_180022887
0x180022838  mov     [rsp+168h+var_128], rdi
0x18002283d  mov     dword ptr [rsp+168h+var_110], edi
0x180022841  xorps   xmm0, xmm0
0x180022844  movdqu  [rsp+168h+var_110+8], xmm0
0x18002284a  mov     rax, [rcx]
0x18002284d  lea     r8, [rsp+168h+var_128]
0x180022852  mov     rdx, [r11-0A0h]
0x180022859  mov     rax, [rax+30h]
0x18002285d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022862  test    eax, eax
0x180022864  js      loc_180022F9B
0x18002286a  mov     r15, [rsp+168h+var_128]
0x18002286f  mov     [rsp+168h+var_128], r15
0x180022874  mov     [rsp+168h+var_148], r15
0x180022879  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002287d  lock add cs:qword_180034AF8, rsi
0x180022885  jmp     short loc_1800228AC
0x180022887  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002288b  lock add cs:qword_180034AF8, rsi
0x180022893  lea     r8, [rsp+168h+lpMem]
0x180022898  lea     rdx, [rsp+168h+var_148]
0x18002289d  call    ??$call@AEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_6572cb39eb053ecf8aa601a8cecd7f9b_@@@Z
0x1800228a2  mov     r15, [rsp+168h+var_148]
0x1800228a7  mov     [rsp+168h+var_128], r15
0x1800228ac  cmp     word ptr cs:aActionpath+14h, di; ""
0x1800228b3  jz      short loc_1800228BC
0x1800228b5  call    cs:__imp_abort
0x1800228bc  mov     dword ptr [rsp+168h+var_78], 1
0x1800228c7  mov     ebx, 0Ah
0x1800228cc  mov     dword ptr [rsp+168h+var_78+4], ebx
0x1800228d3  lea     rax, aActionpath; "actionPath"
0x1800228da  mov     [rsp+168h+var_68], rax
0x1800228e2  lea     rax, [rsp+168h+var_78]
0x1800228ea  mov     [rsp+168h+var_80], rax
0x1800228f2  lea     rdx, [rsp+168h+var_80]
0x1800228fa  lea     rcx, [rsp+168h+var_148]
0x1800228ff  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180022904  test    al, al
0x180022906  jz      loc_180022E7A
0x18002290c  cmp     word ptr cs:aActionconfig+18h, di; ""
0x180022913  jz      short loc_18002291C
0x180022915  call    cs:__imp_abort
0x18002291c  mov     dword ptr [rsp+168h+var_78], 1
0x180022927  mov     dword ptr [rsp+168h+var_78+4], 0Ch
0x180022932  lea     rax, aActionconfig; "actionConfig"
0x180022939  mov     [rsp+168h+var_68], rax
0x180022941  lea     rax, [rsp+168h+var_78]
0x180022949  mov     [rsp+168h+var_80], rax
0x180022951  lea     rdx, [rsp+168h+var_80]
0x180022959  lea     rcx, [rsp+168h+var_148]
0x18002295e  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x180022963  test    al, al
0x180022965  jz      loc_180022E7A
0x18002296b  cmp     word ptr cs:aActionpath+14h, di; ""
0x180022972  jnz     loc_180022E68
0x180022978  mov     dword ptr [rsp+168h+var_78], 1
0x180022983  mov     dword ptr [rsp+168h+var_78+4], ebx
0x18002298a  lea     rax, aActionpath; "actionPath"
0x180022991  mov     [rsp+168h+var_68], rax
0x180022999  lea     rax, [rsp+168h+var_78]
0x1800229a1  mov     [rsp+168h+var_80], rax
0x1800229a9  lea     r8, [rsp+168h+var_80]
0x1800229b1  lea     rdx, [rsp+168h+lpMem]
0x1800229b6  lea     rcx, [rsp+168h+var_148]
0x1800229bb  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1800229c0  cmp     r13, rax
0x1800229c3  jz      short loc_180022A06
0x1800229c5  mov     r12, [rax]
0x1800229c8  mov     [rax], rdi
0x1800229cb  mov     rbx, [r13+0]
0x1800229cf  test    rbx, rbx
0x1800229d2  jz      short loc_1800229FD
0x1800229d4  mov     eax, esi
0x1800229d6  lock xadd [rbx+18h], eax
0x1800229db  sub     eax, 1
0x1800229de  jnz     short loc_1800229F5
0x1800229e0  nop
0x1800229e1  call    WINRT_IMPL_GetProcessHeap
0x1800229e6  mov     rcx, rax; hHeap
0x1800229e9  mov     r8, rbx; lpMem
0x1800229ec  xor     edx, edx; dwFlags
0x1800229ee  call    WINRT_IMPL_HeapFree
0x1800229f3  jmp     short loc_1800229FD
0x1800229f5  test    eax, eax
0x1800229f7  js      loc_180022E68
0x1800229fd  mov     [r13+0], r12
0x180022a01  mov     r12, [rsp+168h+var_F8]
0x180022a06  mov     rbx, [rsp+168h+lpMem]
0x180022a0b  test    rbx, rbx
0x180022a0e  jz      short loc_180022A39
0x180022a10  mov     eax, esi
0x180022a12  lock xadd [rbx+18h], eax
0x180022a17  sub     eax, 1
0x180022a1a  jnz     short loc_180022A31
0x180022a1c  nop
0x180022a1d  call    WINRT_IMPL_GetProcessHeap
0x180022a22  mov     rcx, rax; hHeap
0x180022a25  mov     r8, rbx; lpMem
0x180022a28  xor     edx, edx; dwFlags
0x180022a2a  call    WINRT_IMPL_HeapFree
0x180022a2f  jmp     short loc_180022A39
0x180022a31  test    eax, eax
0x180022a33  js      loc_180022E68
0x180022a39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022a40  mov     r13d, 40h ; '@'
0x180022a46  mov     ecx, r13d; unsigned __int64
0x180022a49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022a4e  mov     rbx, rax
0x180022a51  test    rax, rax
0x180022a54  jz      loc_180022E01
0x180022a5a  mov     r8d, r13d; Size
0x180022a5d  xor     edx, edx; Val
0x180022a5f  mov     rcx, rax; void *
0x180022a62  call    memset_0
0x180022a67  mov     [rbx], edi
0x180022a69  lea     ecx, [r13+8]; Size
0x180022a6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022a72  mov     [rax], rax
0x180022a75  mov     [rax+8], rax
0x180022a79  mov     [rbx+8], rax
0x180022a7d  lea     rcx, [rbx+18h]
0x180022a81  mov     [rcx], rdi
0x180022a84  mov     [rcx+8], rdi
0x180022a88  mov     [rcx+10h], rdi
0x180022a8c  mov     qword ptr [rbx+30h], 7
0x180022a94  mov     qword ptr [rbx+38h], 8
0x180022a9c  mov     dword ptr [rbx], 3F800000h
0x180022aa2  mov     r8, [rbx+8]
0x180022aa6  lea     edx, [r13-30h]
0x180022aaa  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180022aaf  mov     [r12], rbx
0x180022ab3  cmp     word ptr cs:aActionconfig+18h, di; ""
0x180022aba  jz      short loc_180022AC3
0x180022abc  call    cs:__imp_abort
0x180022ac3  mov     [rsp+168h+var_D0], 1
0x180022ace  mov     [rsp+168h+var_CC], 0Ch
0x180022ad9  lea     rax, aActionconfig; "actionConfig"
0x180022ae0  mov     [rsp+168h+var_C0], rax
0x180022ae8  lea     rax, [rsp+168h+var_D0]
0x180022af0  mov     [rsp+168h+var_D8], rax
0x180022af8  mov     [rsp+168h+var_130], rdi
0x180022afd  mov     dword ptr [rsp+168h+var_110], edi
0x180022b01  xorps   xmm0, xmm0
0x180022b04  movdqu  [rsp+168h+var_110+8], xmm0
0x180022b0a  mov     rax, [r15]
0x180022b0d  lea     r8, [rsp+168h+var_130]
0x180022b12  lea     rdx, [rsp+168h+var_D0]
0x180022b1a  mov     rcx, r15
0x180022b1d  mov     rax, [rax+48h]
0x180022b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b26  test    eax, eax
0x180022b28  js      loc_180022FA8
0x180022b2e  mov     rax, [rsp+168h+var_130]
0x180022b33  mov     [rsp+168h+var_138], rax
0x180022b38  lea     rax, [rsp+168h+var_138]
0x180022b3d  mov     [rsp+168h+var_E8], rax
0x180022b45  mov     r12d, edi
0x180022b48  mov     [rsp+168h+var_E0], edi
0x180022b4f  lea     rdx, [rsp+168h+var_B0]
0x180022b57  lea     rcx, [rsp+168h+var_138]
0x180022b5c  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(void)
0x180022b61  cmp     r12d, [rsp+168h+var_A8]
0x180022b69  jz      loc_180022DA4
0x180022b6f  lea     rdx, [rsp+168h+var_118]
0x180022b74  lea     rcx, [rsp+168h+var_E8]
0x180022b7c  call    ??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)
0x180022b81  nop
0x180022b82  mov     qword ptr [rsp+168h+var_110], rdi
0x180022b87  xorps   xmm0, xmm0
0x180022b8a  movups  [rsp+168h+var_110+8], xmm0
0x180022b8f  mov     [rsp+168h+var_130], rdi
0x180022b94  mov     [rsp+168h+var_140], rdi
0x180022b99  mov     rcx, [rsp+168h+var_118]
0x180022b9e  mov     dword ptr [rsp+168h+var_80], edi
0x180022ba5  movdqu  [rsp+168h+var_78], xmm0
0x180022bae  mov     rax, [rcx]
0x180022bb1  lea     rdx, [rsp+168h+var_140]
0x180022bb6  mov     rax, [rax+60h]
0x180022bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bbf  test    eax, eax
0x180022bc1  js      loc_180022FB5
0x180022bc7  mov     r15, [rsp+168h+var_140]
0x180022bcc  mov     [rsp+168h+lpMem], r15
0x180022bd1  mov     [rsp+168h+var_140], r15
0x180022bd6  test    r15, r15
0x180022bd9  jz      short loc_180022BEA
0x180022bdb  mov     rax, [r15]
0x180022bde  mov     rcx, r15
0x180022be1  mov     rax, [rax+8]
0x180022be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bea  lea     r9, [rsp+168h+var_110]
0x180022bef  lea     r8, [rsp+168h+var_130]
0x180022bf4  lea     rdx, [rsp+168h+var_140]
0x180022bf9  call    ?ParseConfigValue@ModuleHandler@@AEAAJUIJsonObject@Json@Data@Windows@winrt@@AEAUhstring@6@AEAU_WHESVC_ACTION_CONFIG_VALUE@@@Z; ModuleHandler::ParseConfigValue(winrt::Windows::Data::Json::IJsonObject,winrt::hstring &,_WHESVC_ACTION_CONFIG_VALUE &)
0x180022bfe  mov     r13d, eax
0x180022c01  test    eax, eax
0x180022c03  jns     loc_180022CCF
0x180022c09  mov     rcx, [rsp+168h]; this
0x180022c11  mov     r9d, eax; char *
0x180022c14  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180022c1b  mov     edx, 39Ch; void *
0x180022c20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c25  nop
0x180022c26  test    r15, r15
0x180022c29  jz      short loc_180022C36
0x180022c2b  lea     rcx, [rsp+168h+lpMem]
0x180022c30  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180022c35  nop
0x180022c36  mov     rbx, [rsp+168h+var_130]
0x180022c3b  test    rbx, rbx
0x180022c3e  jz      short loc_180022C69
0x180022c40  mov     eax, esi
0x180022c42  lock xadd [rbx+18h], eax
0x180022c47  sub     eax, 1
0x180022c4a  jnz     short loc_180022C61
0x180022c4c  nop
0x180022c4d  call    WINRT_IMPL_GetProcessHeap
0x180022c52  mov     rcx, rax; hHeap
0x180022c55  mov     r8, rbx; lpMem
0x180022c58  xor     edx, edx; dwFlags
0x180022c5a  call    WINRT_IMPL_HeapFree
0x180022c5f  jmp     short loc_180022C69
0x180022c61  test    eax, eax
0x180022c63  js      loc_180022D9D
0x180022c69  cmp     [rsp+168h+var_118], rdi
0x180022c6e  jz      short loc_180022C7B
0x180022c70  lea     rcx, [rsp+168h+var_118]
0x180022c75  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180022c7a  nop
0x180022c7b  cmp     [rsp+168h+var_138], rdi
0x180022c80  jz      short loc_180022C8D
0x180022c82  lea     rcx, [rsp+168h+var_138]
0x180022c87  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180022c8c  nop
0x180022c8d  cmp     [rsp+168h+var_128], rdi
0x180022c92  jz      short loc_180022C9F
0x180022c94  lea     rcx, [rsp+168h+var_148]
0x180022c99  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180022c9e  nop
0x180022c9f  mov     rbx, [r14]
0x180022ca2  test    rbx, rbx
0x180022ca5  jz      short loc_180022CC7
0x180022ca7  lock xadd [rbx+18h], esi
0x180022cac  sub     esi, 1
0x180022caf  jnz     short loc_180022CDF
0x180022cb1  nop
0x180022cb2  call    WINRT_IMPL_GetProcessHeap
0x180022cb7  mov     rcx, rax; hHeap
0x180022cba  mov     r8, rbx; lpMem
0x180022cbd  xor     edx, edx; dwFlags
0x180022cbf  call    WINRT_IMPL_HeapFree
0x180022cc4  mov     [r14], rdi
0x180022cc7  mov     eax, r13d
0x180022cca  jmp     loc_180022F5F
0x180022ccf  mov     rbx, [rsp+168h+var_130]
0x180022cd4  test    rbx, rbx
0x180022cd7  jz      short loc_180022CEA
0x180022cd9  mov     rdx, [rbx+10h]
0x180022cdd  jmp     short loc_180022CF1
0x180022cdf  test    esi, esi
0x180022ce1  jns     short loc_180022CC4
0x180022ce3  call    cs:__imp_abort
0x180022cea  lea     rdx, WideCharStr
0x180022cf1  mov     rax, [rsp+168h+var_F8]
0x180022cf6  mov     r13, [rax]
0x180022cf9  movups  xmm6, [rsp+168h+var_110]
0x180022cfe  movsd   xmm7, [rsp+168h+var_100]
0x180022d04  lea     rcx, [rsp+168h+var_80]
0x180022d0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022d11  lea     r8, [rsp+168h+var_80]
  ... truncated ...
```
