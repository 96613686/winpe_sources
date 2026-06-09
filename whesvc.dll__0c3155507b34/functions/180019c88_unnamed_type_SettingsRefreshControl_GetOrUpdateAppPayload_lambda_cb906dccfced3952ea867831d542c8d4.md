# _unnamed_type_SettingsRefreshControl_::GetOrUpdateAppPayload__lambda_cb906dccfced3952ea867831d542c8d4___

- ea: `0x180019c88`
- end: `0x180019fd0`
- name: `_unnamed_type_SettingsRefreshControl_::GetOrUpdateAppPayload__lambda_cb906dccfced3952ea867831d542c8d4___`
- size: `840`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020634`

## callees

- `0x1800032e0`
- `0x180003e10`
- `0x180003e34`
- `0x180006424`
- `0x1800066dc`
- `0x18000f944`
- `0x1800104f8`
- `0x1800115e0`
- `0x18001399c`
- `0x18001997c`
- `0x180019c88`
- `0x18001a310`
- `0x18001aa34`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180019f4c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180019f4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e89`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180019e89`
- `msvcp_win!_Mtx_unlock` at `0x180019e15`
- `msvcp_win!_Mtx_unlock` at `0x180019f99`
- `msvcp_win!_Mtx_unlock` at `0x180019e15`
- `msvcp_win!_Mtx_unlock` at `0x180019f99`
- `msvcp_win!_Mtx_lock` at `0x180019cdd`
- `msvcp_win!_Mtx_lock` at `0x180019e31`
- `msvcp_win!_Mtx_lock` at `0x180019cdd`
- `msvcp_win!_Mtx_lock` at `0x180019e31`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019cea`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019d0c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019e40`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019e5c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019cea`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019d0c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019e40`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180019e5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall unnamed_type_SettingsRefreshControl_::GetOrUpdateAppPayload__lambda_cb906dccfced3952ea867831d542c8d4___(
        __int64 a1,
        _QWORD *a2,
        _WORD *a3,
        winrt::impl ***a4)
{
  _QWORD *v6; // r12
  unsigned __int64 v7; // r8
  __int64 v8; // rbx
  const wchar_t *v9; // rdx
  size_t v10; // rsi
  size_t v11; // r14
  const wchar_t *v12; // rcx
  size_t v13; // r8
  int v14; // eax
  struct _Mtx_internal_imp_t *v15; // rsi
  winrt::impl *v16; // rcx
  __int64 v17; // rdx
  struct winrt::impl::hstring_header *hstring_on_heap; // r14
  int v19; // r15d
  HANDLE ProcessHeap; // rax
  __int64 *v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 *v26; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+28h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD *v29; // [rsp+40h] [rbp-98h]
  struct _Mtx_internal_imp_t *v30; // [rsp+48h] [rbp-90h]
  void *v31; // [rsp+50h] [rbp-88h]
  char v32; // [rsp+58h] [rbp-80h]
  _QWORD v33[2]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v34; // [rsp+70h] [rbp-68h]
  __int64 v35; // [rsp+78h] [rbp-60h]
  wchar_t *S1[2]; // [rsp+80h] [rbp-58h] BYREF
  size_t v37; // [rsp+90h] [rbp-48h]
  unsigned __int64 v38; // [rsp+98h] [rbp-40h]

  v6 = a2;
  v29 = a2;
  v28 = (__int64)a3;
  v31 = &SettingsRefreshControl;
  v32 = 0;
  if ( _Mtx_lock((_Mtx_t)&SettingsRefreshControl) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_18003476C == 0x7FFFFFFF )
  {
    dword_18003476C = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v32 = 1;
  *(_OWORD *)S1 = 0;
  v37 = 0;
  v38 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  std::wstring::_Construct<1,unsigned short const *>(S1, a3, v7);
  std::_Tree<std::_Tmap_traits<std::wstring,_unnamed_tag_::AppRefreshState,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>>,0>>::_Find_lower_bound<std::wstring>(
    &qword_180034770,
    v33,
    S1);
  v8 = v34;
  if ( !*(_BYTE *)(v34 + 25) )
  {
    v9 = (const wchar_t *)(v34 + 32);
    v10 = *(_QWORD *)(v34 + 48);
    if ( *(_QWORD *)(v34 + 56) > 7u )
      v9 = *(const wchar_t **)v9;
    v11 = v37;
    v12 = (const wchar_t *)S1;
    if ( v38 > 7 )
      v12 = S1[0];
    v13 = v37;
    if ( v10 < v37 )
      v13 = *(_QWORD *)(v34 + 48);
    v14 = wmemcmp(v12, v9, v13);
    if ( v14 )
    {
      if ( v14 >= 0 )
        goto LABEL_19;
    }
    else if ( v11 >= v10 )
    {
      goto LABEL_19;
    }
  }
  v8 = qword_180034770;
LABEL_19:
  std::wstring::~wstring((char **)S1);
  if ( v8 == qword_180034770 )
  {
    LODWORD(v26) = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,_unnamed_tag_::AppRefreshState,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>>,0>>::emplace<unsigned short const * &,int>(
      &qword_180034770,
      v33,
      &v28,
      &v26);
    v8 = v33[0];
  }
  v28 = v8;
  _Mtx_unlock((_Mtx_t)&SettingsRefreshControl);
  v32 = 0;
  v15 = (struct _Mtx_internal_imp_t *)(v8 + 64);
  v30 = (struct _Mtx_internal_imp_t *)(v8 + 64);
  v35 = v8 + 64;
  if ( _Mtx_lock((_Mtx_t)(v8 + 64)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v8 + 140) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 140) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  try
  {
    if ( !*(_QWORD *)(v8 + 144) || *(_QWORD *)(v8 + 144) + 60000LL < GetTickCount64() )
    {
      *(_QWORD *)(v8 + 144) = GetTickCount64();
      winrt::get_activation_factory<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>(&v26);
      v16 = **a4;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)v16 + v17) );
      hstring_on_heap = winrt::impl::create_hstring_on_heap(v16, (const char *)v17);
      v33[0] = hstring_on_heap;
      S1[0] = (wchar_t *)hstring_on_heap;
      winrt::impl::consume_Windows_Internal_Flighting_OneSettings_IOneSettingsPayloadStatics<winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::GetCachedPayload(
        &v26,
        &v27,
        (__int64 *)S1);
      if ( hstring_on_heap )
      {
        v19 = _InterlockedDecrement((volatile signed __int32 *)hstring_on_heap + 6);
        if ( v19 )
        {
          if ( v19 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, hstring_on_heap);
        }
      }
      if ( v26 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((__int64 *)&v26);
      v21 = (__int64 *)(v8 + 152);
      if ( (__int64 *)(v8 + 152) == &v27 )
      {
        v23 = v27;
      }
      else
      {
        if ( *v21 )
          winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((__int64 *)(v8 + 152));
        v22 = v27;
        v23 = 0;
        v27 = 0;
        *v21 = v22;
      }
      if ( v23 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v27);
    }
  }
  catch ( winrt::hresult_error )
  {
    v8 = v28;
    v6 = v29;
    v15 = v30;
  }
  v24 = *(_QWORD *)(v8 + 152);
  *v6 = v24;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
  _Mtx_unlock(v15);
  return v6;
}

```

## disassembly

```asm
0x180019c88  mov     [rsp+arg_0], rbx
0x180019c8d  mov     [rsp+arg_18], rsi
0x180019c92  push    rdi
0x180019c93  push    r12
0x180019c95  push    r13
0x180019c97  push    r14
0x180019c99  push    r15
0x180019c9b  sub     rsp, 0B0h
0x180019ca2  mov     rax, cs:__security_cookie
0x180019ca9  xor     rax, rsp
0x180019cac  mov     [rsp+0D8h+var_38], rax
0x180019cb4  mov     r13, r9
0x180019cb7  mov     rbx, r8
0x180019cba  mov     r12, rdx
0x180019cbd  mov     [rsp+0D8h+var_98], rdx
0x180019cc2  mov     [rsp+0D8h+var_A8], rbx
0x180019cc7  xor     edi, edi
0x180019cc9  lea     rax, ?SettingsRefreshControl@@3U_unnamed_type_SettingsRefreshControl_@@A; _unnamed_type_SettingsRefreshControl_ SettingsRefreshControl
0x180019cd0  mov     [rsp+0D8h+var_88], rax
0x180019cd5  mov     [rsp+0D8h+var_80], dil
0x180019cda  mov     rcx, rax; _Mtx_t
0x180019cdd  call    cs:__imp__Mtx_lock
0x180019ce3  test    eax, eax
0x180019ce5  jz      short loc_180019CF1
0x180019ce7  lea     ecx, [rdi+5]
0x180019cea  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019cf0  int     3; Trap to Debugger
0x180019cf1  cmp     cs:dword_18003476C, 7FFFFFFFh
0x180019cfb  jnz     short loc_180019D13
0x180019cfd  mov     cs:dword_18003476C, 7FFFFFFEh
0x180019d07  mov     ecx, 6
0x180019d0c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019d12  int     3; Trap to Debugger
0x180019d13  mov     [rsp+0D8h+var_80], 1
0x180019d18  xorps   xmm0, xmm0
0x180019d1b  movups  xmmword ptr [rsp+0D8h+S1], xmm0
0x180019d23  mov     [rsp+0D8h+var_48], rdi
0x180019d2b  mov     [rsp+0D8h+var_40], rdi
0x180019d33  or      r15, 0FFFFFFFFFFFFFFFFh
0x180019d37  mov     r8, r15
0x180019d3a  inc     r8
0x180019d3d  cmp     [rbx+r8*2], di
0x180019d42  jnz     short loc_180019D3A
0x180019d44  mov     rdx, rbx
0x180019d47  lea     rcx, [rsp+0D8h+S1]
0x180019d4f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019d54  lea     r8, [rsp+0D8h+S1]
0x180019d5c  lea     rdx, [rsp+0D8h+var_78]
0x180019d61  lea     rcx, qword_180034770
0x180019d68  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_unnamed_tag_::AppRefreshState,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180019d6d  mov     rbx, [rsp+0D8h+var_68]
0x180019d72  cmp     [rbx+19h], dil
0x180019d76  jnz     short loc_180019DC8
0x180019d78  lea     rdx, [rbx+20h]
0x180019d7c  mov     rsi, [rdx+10h]
0x180019d80  cmp     qword ptr [rdx+18h], 7
0x180019d85  jbe     short loc_180019D8A
0x180019d87  mov     rdx, [rdx]; S2
0x180019d8a  mov     r14, [rsp+0D8h+var_48]
0x180019d92  lea     rcx, [rsp+0D8h+S1]
0x180019d9a  cmp     [rsp+0D8h+var_40], 7
0x180019da3  cmova   rcx, [rsp+0D8h+S1]; S1
0x180019dac  mov     r8, r14
0x180019daf  cmp     rsi, r14
0x180019db2  cmovb   r8, rsi; N
0x180019db6  call    wmemcmp
0x180019dbb  test    eax, eax
0x180019dbd  jnz     short loc_180019DC6
0x180019dbf  cmp     r14, rsi
0x180019dc2  jnb     short loc_180019DCF
0x180019dc4  jmp     short loc_180019DC8
0x180019dc6  jns     short loc_180019DCF
0x180019dc8  mov     rbx, cs:qword_180034770
0x180019dcf  lea     rcx, [rsp+0D8h+S1]
0x180019dd7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019ddc  cmp     rbx, cs:qword_180034770
0x180019de3  jnz     short loc_180019E09
0x180019de5  mov     dword ptr [rsp+0D8h+var_B8], edi
0x180019de9  lea     r9, [rsp+0D8h+var_B8]
0x180019dee  lea     r8, [rsp+0D8h+var_A8]
0x180019df3  lea     rdx, [rsp+0D8h+var_78]
0x180019df8  lea     rcx, qword_180034770
0x180019dff  call    ??$emplace@AEAPEBGH@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UAppRefreshState@_unnamed_tag_@@@std@@@std@@@std@@@std@@_N@1@AEAPEBG$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,_unnamed_tag_::AppRefreshState,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_unnamed_tag_::AppRefreshState>>,0>>::emplace<ushort const * &,int>(ushort const * &,int &&)
0x180019e04  mov     rbx, [rsp+0D8h+var_78]
0x180019e09  mov     [rsp+0D8h+var_A8], rbx
0x180019e0e  lea     rcx, ?SettingsRefreshControl@@3U_unnamed_type_SettingsRefreshControl_@@A; _Mtx_t
0x180019e15  call    cs:__imp__Mtx_unlock
0x180019e1b  mov     [rsp+0D8h+var_80], dil
0x180019e20  lea     rsi, [rbx+40h]
0x180019e24  mov     [rsp+0D8h+var_90], rsi
0x180019e29  mov     [rsp+0D8h+var_60], rsi
0x180019e2e  mov     rcx, rsi; _Mtx_t
0x180019e31  call    cs:__imp__Mtx_lock
0x180019e37  test    eax, eax
0x180019e39  jz      short loc_180019E47
0x180019e3b  mov     ecx, 5
0x180019e40  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019e46  int     3; Trap to Debugger
0x180019e47  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180019e4e  jnz     short loc_180019E63
0x180019e50  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180019e57  mov     ecx, 6
0x180019e5c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180019e62  nop
0x180019e63  cmp     [rbx+90h], rdi
0x180019e6a  jz      short loc_180019E89
0x180019e6c  call    cs:__imp_GetTickCount64
0x180019e72  mov     rcx, [rbx+90h]
0x180019e79  add     rcx, 0EA60h
0x180019e80  cmp     rcx, rax
0x180019e83  jnb     loc_180019F68
0x180019e89  call    cs:__imp_GetTickCount64
0x180019e8f  mov     [rbx+90h], rax
0x180019e96  lea     rcx, [rsp+0D8h+var_B8]
0x180019e9b  call    ??$get_activation_factory@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@winrt@@YA?A_PXZ
0x180019ea0  nop
0x180019ea1  mov     rax, [r13+0]
0x180019ea5  mov     rcx, [rax]; this
0x180019ea8  mov     rdx, r15
0x180019eab  inc     rdx; unsigned __int16 *
0x180019eae  cmp     [rcx+rdx*2], di
0x180019eb2  jnz     short loc_180019EAB
0x180019eb4  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x180019eb9  mov     r14, rax
0x180019ebc  mov     [rsp+0D8h+var_78], rax
0x180019ec1  mov     [rsp+0D8h+S1], rax
0x180019ec9  lea     r8, [rsp+0D8h+S1]
0x180019ed1  lea     rdx, [rsp+0D8h+var_B0]
0x180019ed6  lea     rcx, [rsp+0D8h+var_B8]
0x180019edb  call    ?GetCachedPayload@?$consume_Windows_Internal_Flighting_OneSettings_IOneSettingsPayloadStatics@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_Flighting_OneSettings_IOneSettingsPayloadStatics<winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::GetCachedPayload(winrt::param::hstring const &)
0x180019ee0  nop
0x180019ee1  test    r14, r14
0x180019ee4  jz      short loc_180019F06
0x180019ee6  lock xadd [r14+18h], r15d
0x180019eec  sub     r15d, 1
0x180019ef0  jnz     short loc_180019F47
0x180019ef2  nop
0x180019ef3  call    WINRT_IMPL_GetProcessHeap
0x180019ef8  mov     rcx, rax; hHeap
0x180019efb  mov     r8, r14; lpMem
0x180019efe  xor     edx, edx; dwFlags
0x180019f00  call    WINRT_IMPL_HeapFree
0x180019f05  nop
0x180019f06  cmp     [rsp+0D8h+var_B8], rdi
0x180019f0b  jz      short loc_180019F17
0x180019f0d  lea     rcx, [rsp+0D8h+var_B8]
0x180019f12  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180019f17  lea     r14, [rbx+98h]
0x180019f1e  lea     rax, [rsp+0D8h+var_B0]
0x180019f23  cmp     r14, rax
0x180019f26  jz      short loc_180019F53
0x180019f28  cmp     [r14], rdi
0x180019f2b  jz      short loc_180019F35
0x180019f2d  mov     rcx, r14
0x180019f30  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180019f35  mov     rcx, [rsp+0D8h+var_B0]
0x180019f3a  mov     rax, rdi
0x180019f3d  mov     [rsp+0D8h+var_B0], rax
0x180019f42  mov     [r14], rcx
0x180019f45  jmp     short loc_180019F58
0x180019f47  test    r15d, r15d
0x180019f4a  jns     short loc_180019F06
0x180019f4c  call    cs:__imp_abort
0x180019f53  mov     rax, [rsp+0D8h+var_B0]
0x180019f58  test    rax, rax
0x180019f5b  jz      short loc_180019F68
0x180019f5d  lea     rcx, [rsp+0D8h+var_B0]
0x180019f62  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180019f67  nop
0x180019f68  jmp     short loc_180019F79
0x180019f6a  mov     rbx, [rsp+0D8h+var_A8]
0x180019f6f  mov     r12, [rsp+0D8h+var_98]
0x180019f74  mov     rsi, [rsp+0D8h+var_90]
0x180019f79  mov     rcx, [rbx+98h]
0x180019f80  mov     [r12], rcx
0x180019f84  test    rcx, rcx
0x180019f87  jz      short loc_180019F96
0x180019f89  mov     rdx, [rcx]
0x180019f8c  mov     rax, [rdx+8]
0x180019f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f95  nop
0x180019f96  mov     rcx, rsi; _Mtx_t
0x180019f99  call    cs:__imp__Mtx_unlock
0x180019f9f  nop
0x180019fa0  mov     rax, r12
0x180019fa3  mov     rcx, [rsp+0D8h+var_38]
0x180019fab  xor     rcx, rsp; StackCookie
0x180019fae  call    __security_check_cookie
0x180019fb3  lea     r11, [rsp+0D8h+var_28]
0x180019fbb  mov     rbx, [r11+30h]
0x180019fbf  mov     rsi, [r11+48h]
0x180019fc3  mov     rsp, r11
0x180019fc6  pop     r15
0x180019fc8  pop     r14
0x180019fca  pop     r13
0x180019fcc  pop     r12
0x180019fce  pop     rdi
0x180019fcf  retn
```
