# SystemSettingEntryPointUtils::GetLocalizedValue(std::unordered_map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::unique_ptr<ShellMRTHelper::MRTHelperBase,std::default_delete<ShellMRTHelper::MRTHelperBase>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::unique_ptr<ShellMRTHelper::MRTHelperBase,std::default_delete<ShellMRTHelper::MRTHelperBase>>>>> &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x180046fac`
- end: `0x180047666`
- name: `?GetLocalizedValue@SystemSettingEntryPointUtils@@YA?AUhstring@winrt@@AEAV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$unique_ptr@VMRTHelperBase@ShellMRTHelper@@U?$default_delete@VMRTHelperBase@ShellMRTHelper@@@std@@@2@@std@@@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `1722`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x180460b54`

## callees

- `0x18000dfa8`
- `0x18000e814`
- `0x180027af0`
- `0x180046fac`
- `0x18004766c`
- `0x180047c60`
- `0x1800483f4`
- `0x180048888`
- `0x1800488d0`
- `0x180048a20`
- `0x1800497d0`
- `0x180049968`
- `0x18005f00c`
- `0x1800e3a88`
- `0x18010e1f8`
- `0x18015c570`
- `0x18015cb00`
- `0x18015d5b6`
- `0x18015d65e`
- `0x18015d850`
- `0x18015d868`
- `0x18015d898`
- `0x18015db30`
- `0x18015db60`
- `0x1802777c0`
- `0x1802db264`
- `0x18044e1fc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047518`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180047518`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180047626`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180047626`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18004716c`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180047258`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180047334`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800473ad`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18004716c`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180047258`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180047334`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800473ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180047228`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180047228`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047093`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047564`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047093`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180047564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004706e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800470e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004706e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800470e2`

## string_xrefs

- `0x180047050`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x1800470ab`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x18004749e`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x1800474e1`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x1800475d2`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`
- `0x18004764b`: `shellcommon\undockeddevkit\libs\helpers\systemsettingentrypointutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
winrt::hstring *__fastcall SystemSettingEntryPointUtils::GetLocalizedValue(winrt::hstring *a1, __int64 a2, __int64 a3)
{
  winrt::hstring *v4; // r12
  __int64 MRTHelperForFullyQualifiedResource; // rax
  const WCHAR *v6; // rcx
  int v7; // eax
  unsigned __int16 *v8; // rdi
  _WORD *v9; // r14
  HRESULT v10; // eax
  __int64 v11; // rax
  unsigned __int64 v13; // rbx
  unsigned int v14; // r14d
  __int64 v15; // r15
  __int64 v16; // rbx
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  char *v19; // r14
  void *v20; // rcx
  size_t v21; // r8
  unsigned __int64 v22; // rbx
  unsigned int v23; // edi
  __int64 v24; // r14
  __int64 v25; // r15
  __int64 v26; // rdx
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rcx
  size_t v31; // r8
  HRESULT v32; // eax
  size_t v33; // rdx
  size_t v34; // rcx
  size_t *v35; // r8
  __int64 v36; // r9
  HRESULT v37; // eax
  __int64 v38; // rdx
  unsigned __int64 v39; // rax
  _WORD *v40; // r15
  HRESULT v41; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  int cchToCopy; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h]
  void **pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v48; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv[3]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszOutBuf[2048]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11B8h] [rbp+10B8h]

  v4 = a1;
  v45 = (unsigned __int64)a1;
  pv[0] = a1;
  if ( *(_QWORD *)(a3 + 8) < 2u || **(_WORD **)a3 != 64 )
    goto LABEL_11;
  MRTHelperForFullyQualifiedResource = SystemSettingEntryPointUtils::_anonymous_namespace_::TryGetOrCreateMRTHelperForFullyQualifiedResource(
                                         a2,
                                         a3);
  v6 = *(const WCHAR **)a3;
  if ( !MRTHelperForFullyQualifiedResource )
  {
    v9 = v6 + 1;
    if ( v6[1] != 64 )
    {
      v10 = SHLoadIndirectString(v6, pszOutBuf, 0x800u, 0);
      if ( v10 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16E,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
          (const char *)(unsigned int)v10,
          cchToCopy);
LABEL_11:
        v11 = winrt::hstring::hstring(&v45, a3);
        SystemSettingEntryPointUtils::SanitizeKeyword(v4, v11);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v45);
        return v4;
      }
      v22 = -1;
      do
        ++v22;
      while ( pszOutBuf[v22] );
      if ( v22 + 1 > 0x800 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
          (const char *)0x8000000BLL,
          cchToCopy);
        v46 = v22;
      }
      else
      {
        v23 = 0;
        LODWORD(v24) = 0;
        if ( v22 )
        {
          while ( 1 )
          {
            v25 = (unsigned int)v24;
            if ( !(unsigned int)_o_iswspace(pszOutBuf[(unsigned int)v24]) )
              break;
            do
              v24 = (unsigned int)(v24 + 1);
            while ( (unsigned int)_o_iswspace(pszOutBuf[v24]) );
            if ( (unsigned int)v24 >= v22 )
            {
LABEL_51:
              v4 = (winrt::hstring *)v45;
              goto LABEL_52;
            }
            if ( v23 )
            {
              pszOutBuf[v23] = 32;
              goto LABEL_49;
            }
LABEL_50:
            if ( (unsigned int)v24 >= v22 )
              goto LABEL_51;
          }
          LODWORD(v24) = v24 + 1;
          pszOutBuf[v23] = pszOutBuf[v25];
LABEL_49:
          ++v23;
          goto LABEL_50;
        }
LABEL_52:
        v26 = v23;
        pszOutBuf[v23] = 0;
        if ( v23 && pszDest[v23 + 127] == 59 )
        {
          v26 = v23 - 1LL;
          pszOutBuf[v26] = 0;
        }
        v46 = v26;
      }
      v45 = (unsigned __int64)pszOutBuf;
      winrt::hstring::hstring(v4, &v45);
      return v4;
    }
    v27 = *(_QWORD *)(a3 + 8) - 1LL;
    std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(&pExceptionObject);
    v28 = _std_count_trivial_2(v9, &v9[v27], 64);
    v45 = v28;
    if ( v28 > (__int64)(*((_QWORD *)&v48 + 1) - (_QWORD)pExceptionObject) >> 3 )
    {
      if ( v28 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<winrt::hstring>::_Reallocate<0>(&pExceptionObject, &v45);
    }
    while ( 1 )
    {
      if ( !v27 )
      {
        v45 = (unsigned __int64)L";";
        v46 = 1;
        SystemSettingEntryPointUtils::Join(v4);
        std::vector<winrt::hstring>::_Tidy(&pExceptionObject);
        return v4;
      }
      v29 = std::_Traits_find_ch<std::char_traits<wchar_t>>(v9, v27, 1, 64);
      v30 = v29;
      if ( v29 == -1 )
        break;
      if ( v27 < v29 )
      {
        std::_Xout_of_range("invalid string_view position");
        __debugbreak();
      }
      v39 = v27 - v29;
      v27 = -1;
      if ( v39 != -1 )
        v27 = v39;
      v40 = &v9[v30];
      if ( v30 )
      {
        v31 = (size_t)v9;
        v9 += v30;
LABEL_67:
        v32 = StringValidateDestW((STRSAFE_PCNZWCH)v30, 0x80u, v31);
        v36 = (unsigned int)v32;
        if ( v32 < 0 )
          goto LABEL_89;
        if ( v34 > 0x7FFFFFFE )
        {
          v36 = 2147942487LL;
LABEL_89:
          pszDest[0] = 0;
LABEL_70:
          v38 = 346;
          goto LABEL_71;
        }
        v37 = StringCopyWorkerW_0(pszDest, v33, v35, (STRSAFE_PCNZWCH)v35, v34);
        v36 = (unsigned int)v37;
        if ( v37 < 0 )
          goto LABEL_70;
        v41 = SHLoadIndirectString(pszDest, pszOutBuf, 0x200u, 0);
        if ( v41 >= 0 )
        {
          v45 = (unsigned __int64)pszOutBuf;
          v42 = -1;
          do
            ++v42;
          while ( pszOutBuf[v42] );
          v46 = v42;
          v43 = SystemSettingEntryPointUtils::SanitizeKeyword(pv, &v45, pszOutBuf, 512);
          std::vector<winrt::hstring>::emplace_back<std::wstring_view>(&pExceptionObject, v43);
        }
        else
        {
          v36 = (unsigned int)v41;
          v38 = 353;
LABEL_71:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
            (const char *)v36,
            cchToCopy);
        }
      }
      else
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
          (const char *)0x80070057LL,
          cchToCopy);
        v9 = v40;
      }
    }
    v31 = (size_t)v9;
    v30 = v27;
    v9 = 0;
    v27 = 0;
    goto LABEL_67;
  }
  pv[0] = 0;
  v7 = ShellMRTHelper::MRTHelperBase::Resolve(MRTHelperForFullyQualifiedResource, 0, (__int64)v6, (LPWSTR *)pv);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
      (const char *)(unsigned int)v7,
      cchToCopy);
    v8 = (unsigned __int16 *)pv[0];
    goto LABEL_6;
  }
  v8 = (unsigned __int16 *)pv[0];
  if ( !pv[0] )
  {
LABEL_6:
    if ( v8 )
      CoTaskMemFree(v8);
    goto LABEL_11;
  }
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)pv[0] + v13) );
  v46 = v13;
  if ( v13 + 1 > (unsigned int)(v13 + 1) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\helpers\\systemsettingentrypointutils.cpp",
      (const char *)0x8000000BLL,
      cchToCopy);
    LODWORD(v16) = v46;
  }
  else
  {
    v14 = 0;
    LODWORD(v15) = 0;
    if ( v13 )
    {
      while ( 1 )
      {
        v45 = (unsigned int)v15;
        if ( !(unsigned int)_o_iswspace(v8[(unsigned int)v15]) )
          break;
        do
          v15 = (unsigned int)(v15 + 1);
        while ( (unsigned int)_o_iswspace(v8[v15]) );
        if ( (unsigned int)v15 >= v13 )
          goto LABEL_23;
        if ( v14 )
        {
          v8[v14] = 32;
          goto LABEL_21;
        }
LABEL_22:
        if ( (unsigned int)v15 >= v13 )
          goto LABEL_23;
      }
      LODWORD(v15) = v15 + 1;
      v8[v14] = v8[v45];
LABEL_21:
      ++v14;
      goto LABEL_22;
    }
LABEL_23:
    LODWORD(v16) = v14;
    v8[v14] = 0;
    if ( v14 && v8[v14 - 1] == 59 )
    {
      v16 = v14 - 1LL;
      v8[v16] = 0;
    }
  }
  if ( (_DWORD)v16 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)v16 + 32 > 0xFFFFFFFF )
    {
      pExceptionObject = &std::exception::`vftable';
      v48 = 0;
      v45 = (unsigned __int64)"length";
      v46 = 1;
      o___std_exception_copy_0(&v45, &v48);
      pExceptionObject = &std::logic_error::`vftable';
      throw (std::invalid_argument *)&pExceptionObject;
    }
    ProcessHeap = WINRT_IMPL_GetProcessHeap();
    v18 = (char *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, 2LL * (unsigned int)v16 + 32);
    v19 = v18;
    if ( !v18 )
    {
      *((_QWORD *)&v48 + 1) = 0;
      *(_QWORD *)&v48 = "bad allocation";
      pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    *(_DWORD *)v18 = 0;
    *((_DWORD *)v18 + 1) = v16;
    v20 = v18 + 28;
    *((_QWORD *)v18 + 2) = v18 + 28;
    _InterlockedExchange((volatile __int32 *)v18 + 6, 1);
    *(_WORD *)&v18[2 * (unsigned int)v16 + 28] = 0;
    v21 = 2LL * (unsigned int)v16;
    if ( !v21 )
      goto LABEL_34;
    if ( v18 == (char *)-28LL )
      goto LABEL_33;
    if ( !v8 )
    {
      memset_0(v20, 0, v21);
LABEL_33:
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      goto LABEL_34;
    }
    memcpy_0(v20, v8, v21);
  }
  else
  {
    v19 = 0;
  }
LABEL_34:
  *(_QWORD *)v4 = v19;
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return v4;
}

```

## disassembly

```asm
0x180046fac  mov     [rsp-8+arg_18], rbx
0x180046fb1  push    rbp
0x180046fb2  push    rsi
0x180046fb3  push    rdi
0x180046fb4  push    r12
0x180046fb6  push    r13
0x180046fb8  push    r14
0x180046fba  push    r15
0x180046fbc  lea     rbp, [rsp-1080h]
0x180046fc4  mov     eax, 1180h
0x180046fc9  call    _alloca_probe
0x180046fce  sub     rsp, rax
0x180046fd1  mov     rax, cs:__security_cookie
0x180046fd8  xor     rax, rsp
0x180046fdb  mov     [rbp+10B0h+var_40], rax
0x180046fe2  mov     rbx, r8
0x180046fe5  mov     r8, rdx
0x180046fe8  mov     r12, rcx
0x180046feb  mov     [rsp+11B0h+var_1180], rcx
0x180046ff0  mov     [rsp+11B0h+pv], rcx
0x180046ff5  xor     r13d, r13d
0x180046ff8  cmp     qword ptr [rbx+8], 2
0x180046ffd  jb      loc_1800470BC
0x180047003  mov     rax, [rbx]
0x180047006  lea     r15d, [r13+40h]
0x18004700a  cmp     [rax], r15w
0x18004700e  jnz     loc_1800470BC
0x180047014  mov     rdx, rbx
0x180047017  mov     rcx, r8
0x18004701a  call    SystemSettingEntryPointUtils___anonymous_namespace___TryGetOrCreateMRTHelperForFullyQualifiedResource
0x18004701f  mov     rcx, [rbx]; pszSource
0x180047022  test    rax, rax
0x180047025  jz      short loc_180047076
0x180047027  mov     [rsp+11B0h+pv], r13
0x18004702c  lea     r9, [rsp+11B0h+pv]
0x180047031  mov     r8, rcx
0x180047034  xor     edx, edx
0x180047036  mov     rcx, rax
0x180047039  call    ?Resolve@MRTHelperBase@ShellMRTHelper@@AEAAJW4MRTResolutionType@12@PEB_WPEAPEA_W@Z; ShellMRTHelper::MRTHelperBase::Resolve(ShellMRTHelper::MRTHelperBase::MRTResolutionType,wchar_t const *,wchar_t * *)
0x18004703e  mov     rcx, [rbp+10B8h]; this
0x180047045  test    eax, eax
0x180047047  jns     loc_180047115
0x18004704d  mov     r9d, eax; char *
0x180047050  lea     r8, aShellcommonUnd_41; "shellcommon\\undockeddevkit\\libs\\help"...
0x180047057  mov     edx, 133h; void *
0x18004705c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047061  mov     rdi, [rsp+11B0h+pv]
0x180047066  test    rdi, rdi
0x180047069  jz      short loc_1800470BC
0x18004706b  mov     rcx, rdi; pv
0x18004706e  call    cs:__imp_CoTaskMemFree
0x180047074  jmp     short loc_1800470BC
0x180047076  lea     r14, [rcx+2]
0x18004707a  cmp     [r14], r15w
0x18004707e  jz      loc_1800473CA
0x180047084  xor     r9d, r9d; ppvReserved
0x180047087  mov     edi, 800h
0x18004708c  mov     r8d, edi; cchOutBuf
0x18004708f  lea     rdx, [rbp+10B0h+pszOutBuf]; pszOutBuf
0x180047093  call    cs:__imp_SHLoadIndirectString
0x180047099  mov     rcx, [rbp+10B8h]; this
0x1800470a0  test    eax, eax
0x1800470a2  jns     loc_1800472F8
0x1800470a8  mov     r9d, eax; char *
0x1800470ab  lea     r8, aShellcommonUnd_41; "shellcommon\\undockeddevkit\\libs\\help"...
0x1800470b2  mov     edx, 16Eh; void *
0x1800470b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800470bc  mov     rdx, rbx
0x1800470bf  lea     rcx, [rsp+11B0h+var_1180]
0x1800470c4  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x1800470c9  nop
0x1800470ca  mov     rdx, rax
0x1800470cd  mov     rcx, r12
0x1800470d0  call    ?SanitizeKeyword@SystemSettingEntryPointUtils@@YA?AUhstring@winrt@@AEBU23@@Z; SystemSettingEntryPointUtils::SanitizeKeyword(winrt::hstring const &)
0x1800470d5  nop
0x1800470d6  lea     rcx, [rsp+11B0h+var_1180]
0x1800470db  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800470e0  jmp     short loc_1800470E8
0x1800470e2  call    cs:__imp_CoTaskMemFree
0x1800470e8  mov     rax, r12
0x1800470eb  mov     rcx, [rbp+10B0h+var_40]
0x1800470f2  xor     rcx, rsp; StackCookie
0x1800470f5  call    __security_check_cookie
0x1800470fa  mov     rbx, [rsp+11B0h+arg_18]
0x180047102  add     rsp, 1180h
0x180047109  pop     r15
0x18004710b  pop     r14
0x18004710d  pop     r13
0x18004710f  pop     r12
0x180047111  pop     rdi
0x180047112  pop     rsi
0x180047113  pop     rbp
0x180047114  retn
0x180047115  mov     rdi, [rsp+11B0h+pv]
0x18004711a  test    rdi, rdi
0x18004711d  jz      loc_180047066
0x180047123  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047127  inc     rbx
0x18004712a  cmp     [rdi+rbx*2], r13w
0x18004712f  jnz     short loc_180047127
0x180047131  mov     dword ptr [rsp+11B0h+var_1178], ebx
0x180047135  mov     rax, rbx
0x180047138  shr     rax, 20h
0x18004713c  mov     dword ptr [rsp+11B0h+var_1178+4], eax
0x180047140  lea     ecx, [rbx+1]
0x180047143  lea     rax, [rbx+1]
0x180047147  mov     esi, 1
0x18004714c  cmp     rax, rcx
0x18004714f  ja      loc_1800475C5
0x180047155  mov     r14d, r13d
0x180047158  mov     r15d, r13d
0x18004715b  test    rbx, rbx
0x18004715e  jz      short loc_18004719B
0x180047160  mov     eax, r15d
0x180047163  mov     [rsp+11B0h+var_1180], rax
0x180047168  movzx   ecx, word ptr [rdi+rax*2]
0x18004716c  call    cs:__imp__o_iswspace
0x180047172  test    eax, eax
0x180047174  jnz     loc_180047250
0x18004717a  add     r15d, esi
0x18004717d  mov     ecx, r14d
0x180047180  mov     rax, [rsp+11B0h+var_1180]
0x180047185  movzx   eax, word ptr [rdi+rax*2]
0x180047189  mov     [rdi+rcx*2], ax
0x18004718d  add     r14d, esi
0x180047190  mov     eax, r15d
0x180047193  cmp     rax, rbx
0x180047196  jb      short loc_180047160
0x180047198  xor     r13d, r13d
0x18004719b  mov     ebx, r14d
0x18004719e  mov     [rdi+rbx*2], r13w
0x1800471a3  test    r14d, r14d
0x1800471a6  jz      short loc_1800471B8
0x1800471a8  cmp     word ptr [rdi+rbx*2-2], 3Bh ; ';'
0x1800471ae  jnz     short loc_1800471B8
0x1800471b0  sub     rbx, rsi
0x1800471b3  mov     [rdi+rbx*2], r13w
0x1800471b8  test    ebx, ebx
0x1800471ba  jz      loc_1800472F0
0x1800471c0  mov     r15d, ebx
0x1800471c3  lea     r14, ds:20h[r15*2]
0x1800471cb  mov     eax, 0FFFFFFFFh
0x1800471d0  cmp     r14, rax
0x1800471d3  ja      loc_18004728F
0x1800471d9  call    WINRT_IMPL_GetProcessHeap
0x1800471de  mov     rcx, rax; hHeap
0x1800471e1  mov     r8, r14; dwBytes
0x1800471e4  xor     edx, edx; dwFlags
0x1800471e6  call    WINRT_IMPL_HeapAlloc
0x1800471eb  mov     r14, rax
0x1800471ee  test    rax, rax
0x1800471f1  jz      loc_1800475ED
0x1800471f7  mov     [rax], r13d
0x1800471fa  mov     [rax+4], ebx
0x1800471fd  lea     rcx, [rax+1Ch]; void *
0x180047201  mov     [rax+10h], rcx
0x180047205  xchg    esi, [rax+18h]
0x180047208  mov     [rax+r15*2+1Ch], r13w
0x18004720e  lea     r8, [r15+r15]; Size
0x180047212  test    r8, r8
0x180047215  jz      short loc_180047239
0x180047217  test    rcx, rcx
0x18004721a  jz      short loc_180047228
0x18004721c  test    rdi, rdi
0x18004721f  jnz     short loc_180047285
0x180047221  xor     edx, edx; Val
0x180047223  call    memset_0
0x180047228  call    cs:__imp__o__errno
0x18004722e  mov     dword ptr [rax], 16h
0x180047234  call    _invalid_parameter_noinfo
0x180047239  mov     [r12], r14
0x18004723d  mov     rcx, [rsp+11B0h+pv]; pv
0x180047242  test    rcx, rcx
0x180047245  jnz     loc_1800470E2
0x18004724b  jmp     loc_1800470E8
0x180047250  add     r15d, esi
0x180047253  movzx   ecx, word ptr [rdi+r15*2]
0x180047258  call    cs:__imp__o_iswspace
0x18004725e  test    eax, eax
0x180047260  jnz     short loc_180047250
0x180047262  mov     eax, r15d
0x180047265  cmp     rax, rbx
0x180047268  jnb     loc_180047198
0x18004726e  test    r14d, r14d
0x180047271  jz      loc_180047190
0x180047277  mov     eax, r14d
0x18004727a  mov     word ptr [rdi+rax*2], 20h ; ' '
0x180047280  jmp     loc_18004718D
0x180047285  mov     rdx, rdi; Src
0x180047288  call    memcpy_0
0x18004728d  jmp     short loc_180047239
0x18004728f  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180047296  mov     [rsp+11B0h+pExceptionObject], rax
0x18004729b  xorps   xmm0, xmm0
0x18004729e  movups  [rsp+11B0h+var_1168], xmm0
0x1800472a3  lea     rax, aLength; "length"
0x1800472aa  mov     [rsp+11B0h+var_1180], rax
0x1800472af  mov     byte ptr [rsp+11B0h+var_1178], sil
0x1800472b4  xor     eax, eax
0x1800472b6  mov     dword ptr [rsp+11B0h+var_1178+1], eax
0x1800472ba  mov     word ptr [rsp+11B0h+var_1178+5], ax
0x1800472bf  mov     byte ptr [rsp+11B0h+var_1178+7], al
0x1800472c3  lea     rdx, [rsp+11B0h+var_1168]
0x1800472c8  lea     rcx, [rsp+11B0h+var_1180]
0x1800472cd  call    _o___std_exception_copy_0
0x1800472d2  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x1800472d9  mov     [rsp+11B0h+pExceptionObject], rax
0x1800472de  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800472e5  lea     rcx, [rsp+11B0h+pExceptionObject]; pExceptionObject
0x1800472ea  call    _CxxThrowException_0
0x1800472f0  mov     r14, r13
0x1800472f3  jmp     loc_180047239
0x1800472f8  lea     rax, [rbp+10B0h+pszOutBuf]
0x1800472fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047300  inc     rbx
0x180047303  cmp     [rax+rbx*2], r13w
0x180047308  jnz     short loc_180047300
0x18004730a  lea     rax, [rbx+1]
0x18004730e  cmp     rax, rdi
0x180047311  ja      loc_18004763E
0x180047317  mov     edi, r13d
0x18004731a  mov     r14d, r13d
0x18004731d  test    rbx, rbx
0x180047320  jz      short loc_180047360
0x180047322  mov     esi, 1
0x180047327  lea     r13d, [rsi+1Fh]
0x18004732b  mov     r15d, r14d
0x18004732e  movzx   ecx, [rbp+r15*2+10B0h+pszOutBuf]
0x180047334  call    cs:__imp__o_iswspace
0x18004733a  test    eax, eax
0x18004733c  jnz     short loc_1800473A1
0x18004733e  add     r14d, esi
0x180047341  mov     ecx, edi
0x180047343  movzx   eax, [rbp+r15*2+10B0h+pszOutBuf]
0x180047349  mov     [rbp+rcx*2+10B0h+pszOutBuf], ax
0x18004734e  add     edi, esi
0x180047350  mov     eax, r14d
0x180047353  cmp     rax, rbx
0x180047356  jb      short loc_18004732B
0x180047358  mov     r12, [rsp+11B0h+var_1180]
0x18004735d  xor     r13d, r13d
0x180047360  mov     edx, edi
0x180047362  mov     [rbp+rdx*2+10B0h+pszOutBuf], r13w
0x180047368  test    edi, edi
0x18004736a  jz      short loc_180047381
0x18004736c  cmp     [rbp+rdx*2+10B0h+var_1042], 3Bh ; ';'
0x180047372  jnz     short loc_180047381
0x180047374  lea     rcx, [rdx-1]
0x180047378  mov     rdx, rcx
0x18004737b  mov     [rbp+rcx*2+10B0h+pszOutBuf], r13w
0x180047381  mov     [rsp+11B0h+var_1178], rdx
0x180047386  lea     rax, [rbp+10B0h+pszOutBuf]
0x18004738a  mov     [rsp+11B0h+var_1180], rax
0x18004738f  lea     rdx, [rsp+11B0h+var_1180]
0x180047394  mov     rcx, r12
0x180047397  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18004739c  jmp     loc_1800470E8
0x1800473a1  add     r14d, esi
0x1800473a4  mov     r15d, r14d
0x1800473a7  movzx   ecx, [rbp+r14*2+10B0h+pszOutBuf]
0x1800473ad  call    cs:__imp__o_iswspace
0x1800473b3  test    eax, eax
0x1800473b5  jnz     short loc_1800473A1
0x1800473b7  cmp     r15, rbx
0x1800473ba  jnb     short loc_180047358
0x1800473bc  test    edi, edi
0x1800473be  jz      short loc_180047350
0x1800473c0  mov     eax, edi
0x1800473c2  mov     [rbp+rax*2+10B0h+pszOutBuf], r13w
0x1800473c8  jmp     short loc_18004734E
0x1800473ca  mov     rdi, [rbx+8]
0x1800473ce  dec     rdi
0x1800473d1  lea     rcx, [rsp+11B0h+pExceptionObject]
0x1800473d6  call    ??0?$vector@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@V?$allocator@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(void)
0x1800473db  nop
0x1800473dc  mov     r8d, r15d
0x1800473df  lea     rdx, [r14+rdi*2]
0x1800473e3  mov     rcx, r14
0x1800473e6  call    __std_count_trivial_2
0x1800473eb  mov     [rsp+11B0h+var_1180], rax
0x1800473f0  mov     rcx, qword ptr [rsp+11B0h+var_1168+8]
0x1800473f5  sub     rcx, [rsp+11B0h+pExceptionObject]
0x1800473fa  sar     rcx, 3
0x1800473fe  cmp     rax, rcx
0x180047401  jbe     short loc_180047425
0x180047403  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18004740d  cmp     rax, rcx
0x180047410  ja      loc_18004761F
0x180047416  lea     rdx, [rsp+11B0h+var_1180]
0x18004741b  lea     rcx, [rsp+11B0h+pExceptionObject]
0x180047420  call    ??$_Reallocate@$0A@@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAXAEA_K@Z; std::vector<winrt::hstring>::_Reallocate<0>(unsigned __int64 &)
0x180047425  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047429  lea     esi, [rbx+2]
0x18004742c  test    rdi, rdi
0x18004742f  jz      loc_18004751F
0x180047435  mov     r9d, r15d
0x180047438  mov     r8, rsi
0x18004743b  mov     rdx, rdi
0x18004743e  mov     rcx, r14
0x180047441  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
  ... truncated ...
```
