# Diagnostics::SourceHandler_Ctac::ConvertData(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18002e380`
- end: `0x18002ea79`
- name: `?ConvertData@SourceHandler_Ctac@Diagnostics@@UEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@4@0@Z`
- size: `1785`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e3e4`
- `0x18000e7ec`
- `0x18001613c`
- `0x180018eec`
- `0x180019080`
- `0x18002a018`
- `0x18002a204`
- `0x18002d4ac`
- `0x18002d73c`
- `0x18002d990`
- `0x18002da90`
- `0x18002e110`
- `0x18002e380`
- `0x18002ea80`
- `0x18002ec64`
- `0x18003b3d0`
- `0x18003b680`
- `0x180046a7c`
- `0x18004723c`
- `0x1800547fc`
- `0x1800674d4`
- `0x1800680a0`
- `0x18008f963`
- `0x18008f96f`
- `0x18008fc40`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002e6be`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002e6be`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Diagnostics::SourceHandler_Ctac::ConvertData(
        __int64 a1,
        __int128 *a2,
        const struct std::filesystem::path *a3,
        __int64 a4)
{
  __int64 v8; // rax
  const wchar_t *v9; // rdx
  LPVOID v10; // rax
  void *v11; // rbx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  LPVOID v15; // rax
  void *v16; // rbx
  int v17; // eax
  HANDLE v18; // rax
  __int64 v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64 *, _QWORD *); // rdi
  __int64 v21; // rbx
  int v22; // eax
  int v23; // esi
  unsigned int v24; // esi
  __int64 v25; // rax
  __int64 *v26; // rbx
  int v27; // esi
  int v28; // eax
  unsigned int v29; // esi
  int v30; // eax
  const wchar_t *v31; // rdx
  unsigned __int64 v32; // r8
  unsigned int v33; // esi
  void *v34; // r14
  int v35; // eax
  HANDLE v36; // rax
  int v37; // esi
  int v38; // eax
  const wchar_t *v39; // rdx
  unsigned __int64 v40; // r8
  void *v41; // r14
  int v42; // eax
  HANDLE v43; // rax
  __int128 *v44; // rax
  __int128 *v45; // rcx
  int v46; // eax
  unsigned int v47; // ebx
  __int64 *v48; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  char v52; // [rsp+40h] [rbp-C0h]
  void (__fastcall ***v53)(_QWORD, __int64 *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int128 v54; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v57[8]; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v58; // [rsp+80h] [rbp-80h] BYREF
  __int128 v59; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h]
  __int64 v61; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v62[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v63[2]; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v64; // [rsp+C0h] [rbp-40h]
  __int128 v65; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v69; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v70; // [rsp+100h] [rbp+0h]
  _OWORD v71[2]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v72[30]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v73[336]; // [rsp+220h] [rbp+120h] BYREF
  _DWORD v74[176]; // [rsp+370h] [rbp+270h] BYREF

  LODWORD(lpMem) = 0;
  if ( !*(_QWORD *)(a4 + 8) )
    return 0;
  v59 = 0;
  v60 = 0;
  memset(v71, 0, sizeof(v71));
  std::wstring::_Construct<1,wchar_t const *>(v71, *(const void **)a4, *(_QWORD *)(a4 + 8));
  memset(v72, 0, sizeof(v72));
  std::wistringstream::wistringstream(v72, v71);
  *(_OWORD *)v62 = 0;
  *(_QWORD *)v63 = 0;
  v64 = 7;
  LOWORD(v62[0]) = 0;
  v8 = std::operator>><wchar_t>(v72, v62);
  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v8 + 4LL) + v8 + 16) & 6) == 0 )
  {
    do
    {
      if ( *(_QWORD *)v63 )
      {
        v9 = (const wchar_t *)v62;
        if ( v64 > 7 )
          v9 = v62[0];
        winrt::hstring::hstring((winrt::hstring *)&lpMem, v9, v63[0]);
        if ( *((_QWORD *)&v59 + 1) == v60 )
        {
          std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(&v59, *((_QWORD *)&v59 + 1), &lpMem);
        }
        else
        {
          v10 = lpMem;
          lpMem = 0;
          **((_QWORD **)&v59 + 1) = v10;
          *((_QWORD *)&v59 + 1) += 8LL;
        }
        v11 = lpMem;
        if ( lpMem )
        {
          v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v12 )
          {
            if ( v12 < 0 )
              goto LABEL_76;
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v11);
          }
          lpMem = 0;
        }
      }
      v14 = std::operator>><wchar_t>(v72, v62);
    }
    while ( (*(_BYTE *)(*(int *)(*(_QWORD *)v14 + 4LL) + v14 + 16) & 6) == 0 );
  }
  if ( (_QWORD)v59 == *((_QWORD *)&v59 + 1) )
  {
    winrt::hstring::hstring((winrt::hstring *)&v58, *(const wchar_t **)a4, *(_DWORD *)(a4 + 8));
    if ( *((_QWORD *)&v59 + 1) == v60 )
    {
      std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(&v59, *((_QWORD *)&v59 + 1), &v58);
    }
    else
    {
      v15 = v58;
      v58 = 0;
      **((_QWORD **)&v59 + 1) = v15;
      *((_QWORD *)&v59 + 1) += 8LL;
    }
    v16 = v58;
    if ( v58 )
    {
      v17 = _InterlockedDecrement((volatile signed __int32 *)v58 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
LABEL_76:
          abort();
      }
      else
      {
        v18 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v18, 0, v16);
      }
    }
  }
  winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(&v53, (__int64 *)&v59);
  v19 = 0;
  v51 = 0;
  v52 = 1;
  v20 = v53;
  if ( v53 )
  {
    v56 = 0;
    (**v53)(v53, &winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>, &v56);
    v21 = v56;
    v19 = v51;
  }
  else
  {
    v21 = 0;
  }
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
  v51 = v21;
  v48 = &v51;
  v50 = &qword_180185208;
  _InterlockedIncrement64(&qword_180185208);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2> )
  {
    v56 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2>
                                                                 + 48LL))(
            winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2>,
            v51,
            &v56);
    if ( v22 < 0 )
      winrt::throw_hresult((unsigned int)v22);
    v23 = 224;
    _InterlockedDecrement64(&qword_180185208);
  }
  else
  {
    _InterlockedDecrement64(&qword_180185208);
    ___call_AEAV_lambda_1___1__GetSystemPropertiesAsync_AnalyticsInfo_Profile_System_Windows_winrt__SA_AEBU__async_iterable_Uhstring_winrt___param_7__Z____factory_cache_entry_UAnalyticsInfo_Profile_System_Windows_winrt__UIAnalyticsInfoStatics2_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetSystemPropertiesAsync_AnalyticsInfo_Profile_System_Windows_2_SA_AEBU__async_iterable_Uhstring_winrt___param_2__Z__Z(
      0,
      &v56,
      &v48);
    v23 = 32;
  }
  v24 = v23 | 0x10;
  if ( v52 )
  {
    v25 = v51;
  }
  else
  {
    v25 = 0;
    v51 = 0;
  }
  if ( v25 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>>::get(
    &v56,
    &v61);
  memset(v74, 0, sizeof(v74));
  Diagnostics::OTelFile::OTelFile((Diagnostics::OTelFile *)v74, a3);
  v48 = 0;
  GetSystemTimePreciseAsFileTime(&v48);
  v48 = (__int64 *)(((unsigned __int64)HIDWORD(v48) << 32) - 116444736000000000LL + (unsigned int)v48);
  memset(v73, 0, sizeof(v73));
  v55 = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
  v54 = *a2;
  Diagnostics::OTelLogRecord::OTelLogRecord(v73, &v48, &v54, &v55);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>::begin(
    &v61,
    &v48);
  v51 = 0;
  v26 = v48;
  while ( v26 )
  {
    v58 = 0;
    v27 = v24 | 8;
    LODWORD(lpMem) = v27;
    v28 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v26 + 48))(v26, &v58);
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28);
    v50 = 0;
    v29 = v27 & 0xFFFFFFF2 | 5;
    LODWORD(lpMem) = v29;
    v30 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v58 + 48LL))(v58, &v50);
    if ( v30 < 0 )
      winrt::throw_hresult((unsigned int)v30);
    v68 = 0;
    v69 = 0;
    v70 = 0;
    if ( v50 )
    {
      v31 = (const wchar_t *)*((_QWORD *)v50 + 2);
      v32 = *((unsigned int *)v50 + 1);
    }
    else
    {
      v31 = &psz;
      v32 = 0;
    }
    std::wstring::_Construct<1,wchar_t const *>(&v68, v31, v32);
    v33 = v29 & 0xFFFFFFFE;
    v34 = v50;
    if ( v50 )
    {
      v35 = _InterlockedDecrement((volatile signed __int32 *)v50 + 6);
      if ( v35 )
      {
        if ( v35 < 0 )
          abort();
      }
      else
      {
        v36 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v36, 0, v34);
      }
    }
    v50 = 0;
    v37 = v33 | 2;
    LODWORD(lpMem) = v37;
    v38 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v58 + 56LL))(v58, &v50);
    if ( v38 < 0 )
      winrt::throw_hresult((unsigned int)v38);
    v65 = 0;
    v66 = 0;
    v67 = 0;
    if ( v50 )
    {
      v39 = (const wchar_t *)*((_QWORD *)v50 + 2);
      v40 = *((unsigned int *)v50 + 1);
    }
    else
    {
      v39 = &psz;
      v40 = 0;
    }
    std::wstring::_Construct<1,wchar_t const *>(&v65, v39, v40);
    v24 = v37 & 0xFFFFFFFD;
    v41 = v50;
    if ( v50 )
    {
      v42 = _InterlockedDecrement((volatile signed __int32 *)v50 + 6);
      if ( v42 )
      {
        if ( v42 < 0 )
          abort();
      }
      else
      {
        v43 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v43, 0, v41);
      }
      v50 = 0;
    }
    v44 = &v65;
    if ( v67 > 7 )
      v44 = (__int128 *)v65;
    v45 = &v68;
    if ( v70 > 7 )
      v45 = (__int128 *)v68;
    *(_QWORD *)&v54 = v44;
    *((_QWORD *)&v54 + 1) = v66;
    *(_QWORD *)&v55 = v45;
    *((_QWORD *)&v55 + 1) = v69;
    Diagnostics::OTelLogRecord::AddAttribute(v73, &v55, &v54);
    std::wstring::~wstring((__int64)&v65);
    std::wstring::~wstring((__int64)&v68);
    if ( v58 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
    v57[0] = 0;
    v46 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(*v26 + 64))(v26, v57);
    if ( v46 < 0 )
      winrt::throw_hresult((unsigned int)v46);
    if ( !v57[0] )
    {
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
      v26 = 0;
      v48 = 0;
    }
  }
  Diagnostics::OTelFile::AppendLogRecord((Diagnostics::OTelFile *)v74, (const struct Diagnostics::OTelLogRecord *)v73);
  v47 = v74[174];
  Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v73);
  Diagnostics::OTelFile::~OTelFile((Diagnostics::OTelFile *)v74);
  if ( v61 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v61);
  if ( v56 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v56);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v53);
  std::wstring::~wstring((__int64)v62);
  std::wistringstream::~wistringstream(&v72[18]);
  v72[18] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v72[18]);
  std::wstring::~wstring((__int64)v71);
  std::vector<winrt::hstring>::~vector<winrt::hstring>(&v59);
  return v47;
}

```

## disassembly

```asm
0x18002e380  push    rbp
0x18002e382  push    rbx
0x18002e383  push    rsi
0x18002e384  push    rdi
0x18002e385  push    r12
0x18002e387  push    r14
0x18002e389  push    r15
0x18002e38b  lea     rbp, [rsp-540h]
0x18002e393  sub     rsp, 640h
0x18002e39a  mov     rax, cs:__security_cookie
0x18002e3a1  xor     rax, rsp
0x18002e3a4  mov     [rbp+570h+var_40], rax
0x18002e3ab  mov     rdi, r9
0x18002e3ae  mov     r15, r8
0x18002e3b1  mov     r14, rdx
0x18002e3b4  xor     r12d, r12d
0x18002e3b7  mov     esi, r12d
0x18002e3ba  mov     dword ptr [rsp+670h+lpMem], r12d
0x18002e3bf  cmp     [r9+8], r12
0x18002e3c3  jnz     short loc_18002E3CC
0x18002e3c5  xor     eax, eax
0x18002e3c7  jmp     loc_18002EA1E
0x18002e3cc  xorps   xmm0, xmm0
0x18002e3cf  xorps   xmm1, xmm1
0x18002e3d2  movdqu  [rbp+570h+var_5E8], xmm1
0x18002e3d7  mov     [rbp+570h+var_5D8], r12
0x18002e3db  movups  [rbp+570h+var_568], xmm0
0x18002e3df  movdqu  [rbp+570h+var_558], xmm1
0x18002e3e4  mov     r8, [r9+8]
0x18002e3e8  mov     rdx, [r9]
0x18002e3eb  lea     rcx, [rbp+570h+var_568]
0x18002e3ef  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002e3f4  nop
0x18002e3f5  xor     edx, edx; Val
0x18002e3f7  mov     r8d, 0F0h; Size
0x18002e3fd  lea     rcx, [rbp+570h+var_540]; void *
0x18002e401  call    memset
0x18002e406  lea     rdx, [rbp+570h+var_568]
0x18002e40a  lea     rcx, [rbp+570h+var_540]
0x18002e40e  call    ??0?$basic_istringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wistringstream::wistringstream(std::wstring const &,int)
0x18002e413  nop
0x18002e414  xorps   xmm0, xmm0
0x18002e417  movups  xmmword ptr [rbp+570h+var_5C8], xmm0
0x18002e41b  mov     qword ptr [rbp+570h+var_5B8], r12
0x18002e41f  mov     [rbp+570h+var_5B0], 7
0x18002e427  mov     word ptr [rbp+570h+var_5C8], r12w
0x18002e42c  lea     rdx, [rbp+570h+var_5C8]
0x18002e430  lea     rcx, [rbp+570h+var_540]
0x18002e434  call    ??$?5_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@AEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator>><wchar_t>(std::wistream &,std::wstring &)
0x18002e439  mov     rcx, [rax]
0x18002e43c  movsxd  rdx, dword ptr [rcx+4]
0x18002e440  test    byte ptr [rdx+rax+10h], 6
0x18002e445  jnz     loc_18002E4F8
0x18002e44b  cmp     qword ptr [rbp+570h+var_5B8], r12
0x18002e44f  jz      loc_18002E4D8
0x18002e455  lea     rdx, [rbp+570h+var_5C8]
0x18002e459  cmp     [rbp+570h+var_5B0], 7
0x18002e45e  cmova   rdx, [rbp+570h+var_5C8]; wchar_t *
0x18002e463  mov     r8d, [rbp+570h+var_5B8]; unsigned int
0x18002e467  lea     rcx, [rsp+670h+lpMem]; this
0x18002e46c  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x18002e471  nop
0x18002e472  mov     rdx, qword ptr [rbp+570h+var_5E8+8]
0x18002e476  cmp     rdx, [rbp+570h+var_5D8]
0x18002e47a  jz      short loc_18002E490
0x18002e47c  mov     rax, [rsp+670h+lpMem]
0x18002e481  mov     [rsp+670h+lpMem], r12
0x18002e486  mov     [rdx], rax
0x18002e489  add     qword ptr [rbp+570h+var_5E8+8], 8
0x18002e48e  jmp     short loc_18002E49F
0x18002e490  lea     r8, [rsp+670h+lpMem]
0x18002e495  lea     rcx, [rbp+570h+var_5E8]
0x18002e499  call    ??$_Emplace_reallocate@Uhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@$$QEAU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(winrt::hstring * const,winrt::hstring &&)
0x18002e49e  nop
0x18002e49f  mov     rbx, [rsp+670h+lpMem]
0x18002e4a4  test    rbx, rbx
0x18002e4a7  jz      short loc_18002E4D8
0x18002e4a9  or      eax, 0FFFFFFFFh
0x18002e4ac  lock xadd [rbx+18h], eax
0x18002e4b1  sub     eax, 1
0x18002e4b4  jnz     short loc_18002E4CB
0x18002e4b6  nop
0x18002e4b7  call    WINRT_IMPL_GetProcessHeap
0x18002e4bc  mov     rcx, rax; hHeap
0x18002e4bf  mov     r8, rbx; lpMem
0x18002e4c2  xor     edx, edx; dwFlags
0x18002e4c4  call    WINRT_IMPL_HeapFree
0x18002e4c9  jmp     short loc_18002E4D3
0x18002e4cb  test    eax, eax
0x18002e4cd  js      loc_18002EA47
0x18002e4d3  mov     [rsp+670h+lpMem], r12
0x18002e4d8  lea     rdx, [rbp+570h+var_5C8]
0x18002e4dc  lea     rcx, [rbp+570h+var_540]
0x18002e4e0  call    ??$?5_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@AEAV10@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator>><wchar_t>(std::wistream &,std::wstring &)
0x18002e4e5  mov     rcx, [rax]
0x18002e4e8  movsxd  r8, dword ptr [rcx+4]
0x18002e4ec  test    byte ptr [r8+rax+10h], 6
0x18002e4f2  jz      loc_18002E44B
0x18002e4f8  mov     rax, qword ptr [rbp+570h+var_5E8+8]
0x18002e4fc  cmp     qword ptr [rbp+570h+var_5E8], rax
0x18002e500  jnz     short loc_18002E566
0x18002e502  mov     r8d, [rdi+8]; unsigned int
0x18002e506  mov     rdx, [rdi]; wchar_t *
0x18002e509  lea     rcx, [rbp+570h+var_5F0]; this
0x18002e50d  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x18002e512  nop
0x18002e513  mov     rdx, qword ptr [rbp+570h+var_5E8+8]
0x18002e517  cmp     rdx, [rbp+570h+var_5D8]
0x18002e51b  jz      short loc_18002E52F
0x18002e51d  mov     rax, [rbp+570h+var_5F0]
0x18002e521  mov     [rbp+570h+var_5F0], r12
0x18002e525  mov     [rdx], rax
0x18002e528  add     qword ptr [rbp+570h+var_5E8+8], 8
0x18002e52d  jmp     short loc_18002E53D
0x18002e52f  lea     r8, [rbp+570h+var_5F0]
0x18002e533  lea     rcx, [rbp+570h+var_5E8]
0x18002e537  call    ??$_Emplace_reallocate@Uhstring@winrt@@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAPEAUhstring@winrt@@QEAU23@$$QEAU23@@Z; std::vector<winrt::hstring>::_Emplace_reallocate<winrt::hstring>(winrt::hstring * const,winrt::hstring &&)
0x18002e53c  nop
0x18002e53d  mov     rbx, [rbp+570h+var_5F0]
0x18002e541  test    rbx, rbx
0x18002e544  jz      short loc_18002E566
0x18002e546  or      eax, 0FFFFFFFFh
0x18002e549  lock xadd [rbx+18h], eax
0x18002e54e  sub     eax, 1
0x18002e551  jnz     short loc_18002E591
0x18002e553  nop
0x18002e554  call    WINRT_IMPL_GetProcessHeap
0x18002e559  mov     rcx, rax; hHeap
0x18002e55c  mov     r8, rbx; lpMem
0x18002e55f  xor     edx, edx; dwFlags
0x18002e561  call    WINRT_IMPL_HeapFree
0x18002e566  lea     rdx, [rbp+570h+var_5E8]
0x18002e56a  lea     rcx, [rsp+670h+var_628]
0x18002e56f  call    ??$single_threaded_vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@winrt@@YA?AU?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(std::vector<winrt::hstring> &&)
0x18002e574  nop
0x18002e575  mov     rax, r12
0x18002e578  mov     [rsp+670h+var_638], rax
0x18002e57d  mov     [rsp+670h+var_630], 1
0x18002e582  mov     rdi, [rsp+670h+var_628]
0x18002e587  test    rdi, rdi
0x18002e58a  jnz     short loc_18002E59B
0x18002e58c  mov     rbx, r12
0x18002e58f  jmp     short loc_18002E5C4
0x18002e591  test    eax, eax
0x18002e593  js      loc_18002EA47
0x18002e599  jmp     short loc_18002E566
0x18002e59b  mov     [rsp+670h+var_600], r12
0x18002e5a0  mov     rax, [rdi]
0x18002e5a3  lea     r8, [rsp+670h+var_600]
0x18002e5a8  lea     rdx, ??$guid_v@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>
0x18002e5af  mov     rcx, rdi
0x18002e5b2  mov     rax, [rax]
0x18002e5b5  call    _guard_dispatch_icall
0x18002e5ba  mov     rbx, [rsp+670h+var_600]
0x18002e5bf  mov     rax, [rsp+670h+var_638]
0x18002e5c4  test    rax, rax
0x18002e5c7  jz      short loc_18002E5D3
0x18002e5c9  lea     rcx, [rsp+670h+var_638]
0x18002e5ce  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002e5d3  mov     [rsp+670h+var_638], rbx
0x18002e5d8  lea     rax, [rsp+670h+var_638]
0x18002e5dd  mov     [rsp+670h+var_650], rax
0x18002e5e2  lea     rax, qword_180185208
0x18002e5e9  mov     [rsp+670h+var_640], rax
0x18002e5ee  lock inc cs:qword_180185208
0x18002e5f6  mov     rcx, cs:??$factory_cache_entry_v@UAnalyticsInfo@Profile@System@Windows@winrt@@UIAnalyticsInfoStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAnalyticsInfo@Profile@System@Windows@winrt@@UIAnalyticsInfoStatics2@2345@@12@A; factory_cache_entry<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2>::winrt::factory_cache_entry<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::AnalyticsInfo,winrt::Windows::System::Profile::IAnalyticsInfoStatics2>
0x18002e5fd  test    rcx, rcx
0x18002e600  jz      short loc_18002E63F
0x18002e602  mov     [rsp+670h+var_600], r12
0x18002e607  mov     rax, [rcx]
0x18002e60a  lea     r8, [rsp+670h+var_600]
0x18002e60f  mov     rdx, [rsp+670h+var_638]
0x18002e614  mov     rax, [rax+30h]
0x18002e618  call    _guard_dispatch_icall
0x18002e61d  test    eax, eax
0x18002e61f  js      loc_18002EA4D
0x18002e625  mov     rax, [rsp+670h+var_600]
0x18002e62a  mov     [rsp+670h+var_600], rax
0x18002e62f  or      esi, 0E0h
0x18002e635  lock dec cs:qword_180185208
0x18002e63d  jmp     short loc_18002E659
0x18002e63f  lock dec cs:qword_180185208
0x18002e647  lea     r8, [rsp+670h+var_650]
0x18002e64c  lea     rdx, [rsp+670h+var_600]
0x18002e651  call    ??$call@AEAV_lambda_1_@?1??GetSystemPropertiesAsync@AnalyticsInfo@Profile@System@Windows@winrt@@SA@AEBU?$async_iterable@Uhstring@winrt@@@param@7@@Z@@?$factory_cache_entry@UAnalyticsInfo@Profile@System@Windows@winrt@@UIAnalyticsInfoStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetSystemPropertiesAsync@AnalyticsInfo@Profile@System@Windows@2@SA@AEBU?$async_iterable@Uhstring@winrt@@@param@2@@Z@@Z
0x18002e656  or      esi, 20h
0x18002e659  or      esi, 10h
0x18002e65c  cmp     [rsp+670h+var_630], r12b
0x18002e661  jnz     short loc_18002E66D
0x18002e663  mov     rax, r12
0x18002e666  mov     [rsp+670h+var_638], rax
0x18002e66b  jmp     short loc_18002E672
0x18002e66d  mov     rax, [rsp+670h+var_638]
0x18002e672  test    rax, rax
0x18002e675  jz      short loc_18002E681
0x18002e677  lea     rcx, [rsp+670h+var_638]
0x18002e67c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002e681  lea     rdx, [rbp+570h+var_5D0]
0x18002e685  lea     rcx, [rsp+670h+var_600]
0x18002e68a  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@U?$IMapView@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@U?$IMapView@Uhstring@winrt@@U12@@Collections@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>>::get(void)
0x18002e68f  nop
0x18002e690  xor     edx, edx; Val
0x18002e692  mov     r8d, 2C0h; Size
0x18002e698  lea     rcx, [rbp+570h+var_300]; void *
0x18002e69f  call    memset
0x18002e6a4  mov     rdx, r15; struct std::filesystem::path *
0x18002e6a7  lea     rcx, [rbp+570h+var_300]; this
0x18002e6ae  call    ??0OTelFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@@Z; Diagnostics::OTelFile::OTelFile(std::filesystem::path const &)
0x18002e6b3  nop
0x18002e6b4  mov     [rsp+670h+var_650], r12
0x18002e6b9  lea     rcx, [rsp+670h+var_650]
0x18002e6be  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18002e6c4  mov     eax, dword ptr [rsp+670h+var_650+4]
0x18002e6c8  shl     rax, 20h
0x18002e6cc  mov     ecx, dword ptr [rsp+670h+var_650]
0x18002e6d0  mov     rdx, 0FE624E212AC18000h
0x18002e6da  add     rax, rdx
0x18002e6dd  add     rcx, rax
0x18002e6e0  mov     [rsp+670h+var_650], rcx
0x18002e6e5  xor     edx, edx; Val
0x18002e6e7  mov     r8d, 150h; Size
0x18002e6ed  lea     rcx, [rbp+570h+var_450]; void *
0x18002e6f4  call    memset
0x18002e6f9  movups  xmm0, xmmword ptr cs:?DefaultVersion@OTelLogRecord@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const Diagnostics::OTelLogRecord::DefaultVersion
0x18002e700  movdqu  [rsp+670h+var_610], xmm0
0x18002e706  movups  xmm0, xmmword ptr [r14]
0x18002e70a  movdqu  [rsp+670h+var_620], xmm0
0x18002e710  lea     r9, [rsp+670h+var_610]
0x18002e715  lea     r8, [rsp+670h+var_620]
0x18002e71a  lea     rdx, [rsp+670h+var_650]
0x18002e71f  lea     rcx, [rbp+570h+var_450]
0x18002e726  call    ??0OTelLogRecord@Diagnostics@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@4@1@Z; Diagnostics::OTelLogRecord::OTelLogRecord(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &,std::wstring_view,std::wstring_view)
0x18002e72b  nop
0x18002e72c  lea     rdx, [rsp+670h+var_650]
0x18002e731  lea     rcx, [rbp+570h+var_5D0]
0x18002e735  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IMapView@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@U12@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::hstring>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>::begin(void)
0x18002e73a  nop
0x18002e73b  mov     [rsp+670h+var_638], r12
0x18002e740  mov     rbx, [rsp+670h+var_650]
0x18002e745  test    rbx, rbx
0x18002e748  jz      loc_18002E964
0x18002e74e  mov     [rbp+570h+var_5F0], r12
0x18002e752  or      esi, 8
0x18002e755  mov     dword ptr [rsp+670h+lpMem], esi
0x18002e759  mov     rax, [rbx]
0x18002e75c  lea     rdx, [rbp+570h+var_5F0]
0x18002e760  mov     rcx, rbx
0x18002e763  mov     rax, [rax+30h]
0x18002e767  call    _guard_dispatch_icall
0x18002e76c  test    eax, eax
0x18002e76e  js      loc_18002EA3F
0x18002e774  and     esi, 0FFFFFFF7h
0x18002e777  or      esi, 4
0x18002e77a  mov     [rsp+670h+var_640], r12
0x18002e77f  or      esi, 1
0x18002e782  mov     dword ptr [rsp+670h+lpMem], esi
0x18002e786  mov     rcx, [rbp+570h+var_5F0]
0x18002e78a  mov     rax, [rcx]
0x18002e78d  lea     rdx, [rsp+670h+var_640]
0x18002e792  mov     rax, [rax+30h]
0x18002e796  call    _guard_dispatch_icall
0x18002e79b  test    eax, eax
0x18002e79d  js      loc_18002EA71
0x18002e7a3  xorps   xmm0, xmm0
0x18002e7a6  movups  [rbp+570h+var_588], xmm0
0x18002e7aa  mov     [rbp+570h+var_578], r12
0x18002e7ae  mov     [rbp+570h+var_570], r12
0x18002e7b2  mov     rax, [rsp+670h+var_640]
0x18002e7b7  test    rax, rax
0x18002e7ba  jz      short loc_18002E7C6
0x18002e7bc  mov     rdx, [rax+10h]
0x18002e7c0  mov     r8d, [rax+4]
0x18002e7c4  jmp     short loc_18002E7D0
0x18002e7c6  lea     rdx, psz
0x18002e7cd  mov     r8, r12
0x18002e7d0  lea     rcx, [rbp+570h+var_588]
0x18002e7d4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002e7d9  nop
0x18002e7da  and     esi, 0FFFFFFFEh
0x18002e7dd  mov     r14, [rsp+670h+var_640]
0x18002e7e2  test    r14, r14
0x18002e7e5  jz      short loc_18002E812
0x18002e7e7  or      eax, 0FFFFFFFFh
0x18002e7ea  lock xadd [r14+18h], eax
0x18002e7f0  sub     eax, 1
0x18002e7f3  jnz     short loc_18002E80A
0x18002e7f5  nop
0x18002e7f6  call    WINRT_IMPL_GetProcessHeap
0x18002e7fb  mov     rcx, rax; hHeap
0x18002e7fe  mov     r8, r14; lpMem
0x18002e801  xor     edx, edx; dwFlags
0x18002e803  call    WINRT_IMPL_HeapFree
0x18002e808  jmp     short loc_18002E812
0x18002e80a  test    eax, eax
0x18002e80c  js      loc_18002EA55
0x18002e812  mov     [rsp+670h+var_640], r12
0x18002e817  or      esi, 2
0x18002e81a  mov     dword ptr [rsp+670h+lpMem], esi
0x18002e81e  mov     rcx, [rbp+570h+var_5F0]
0x18002e822  mov     rax, [rcx]
  ... truncated ...
```
