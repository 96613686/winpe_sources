# StartupNotification::GetFileDescription(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005dca0`
- end: `0x18005e3c7`
- name: `?GetFileDescription@StartupNotification@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1831`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e470`

## callees

- `0x18001c294`
- `0x18001c7b0`
- `0x1800358f0`
- `0x180041aa4`
- `0x18005d9b0`
- `0x18005db20`
- `0x18005dca0`
- `0x18005f410`
- `0x18005f480`
- `0x18005f540`
- `0x18005fb9c`
- `0x18005fbb4`
- `0x18005fe10`
- `0x18006634c`
- `0x18007f488`
- `0x18012edd0`
- `0x180199324`
- `0x180271618`
- `0x180271658`
- `0x18027d188`
- `0x180303644`
- `0x180356360`
- `0x180365b8c`
- `0x1803b9954`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e13a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e13a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e0fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e0fb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005e3ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18005e3ab`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x18005df15`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x18005dff5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x18005df15`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetFileDescriptionW` at `0x18005dff5`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18005dedc`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18005dedc`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall StartupNotification::GetFileDescription(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  PCWSTR *v4; // rdx
  char v5; // bl
  __int64 v6; // rax
  unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r10
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rdx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rdx
  unsigned __int16 *v13; // r8
  __int64 v14; // rax
  _WORD *v15; // rdx
  __int128 *v16; // rax
  char v17; // di
  const WCHAR *v18; // rcx
  const char *v19; // r9
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // r15
  __int64 v24; // rbx
  __int64 size_of; // rax
  void *v26; // r12
  unsigned __int64 v27; // r9
  LPVOID v28; // rbx
  LPVOID *v29; // r9
  const char *v30; // r9
  PWSTR v31; // rcx
  __int64 v33; // r8
  __int64 v34; // rax
  HRESULT Instance; // eax
  __int64 (__fastcall **v36)(LPVOID, GUID *, __int64 *); // rax
  int v37; // eax
  PCWSTR *v38; // rcx
  PCWSTR *v39; // rdx
  int v40; // eax
  LPVOID *v41; // rcx
  __int64 v42; // r8
  LPVOID *v43; // r10
  __int64 v44; // r10
  __int16 v45; // cx
  unsigned __int16 v46; // ax
  int ppv; // [rsp+20h] [rbp-B9h]
  int ppva; // [rsp+20h] [rbp-B9h]
  __int64 v49; // [rsp+30h] [rbp-A9h] BYREF
  PWSTR ppszApplication; // [rsp+38h] [rbp-A1h] BYREF
  PWSTR ppszParameters; // [rsp+40h] [rbp-99h] BYREF
  int v52; // [rsp+48h] [rbp-91h]
  LPVOID v53[2]; // [rsp+50h] [rbp-89h] BYREF
  unsigned __int64 v54; // [rsp+60h] [rbp-79h]
  unsigned __int64 v55; // [rsp+68h] [rbp-71h]
  PCWSTR pszCmdTemplate[2]; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int64 v57; // [rsp+80h] [rbp-59h]
  unsigned __int64 v58; // [rsp+88h] [rbp-51h]
  std::filesystem *v59[2]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-39h]
  unsigned __int64 v61; // [rsp+A8h] [rbp-31h]
  __int128 v62; // [rsp+B0h] [rbp-29h] BYREF
  void *v63; // [rsp+C0h] [rbp-19h]
  unsigned __int64 v64; // [rsp+C8h] [rbp-11h]
  __int128 v65; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v66; // [rsp+E0h] [rbp+7h]
  __int64 v67; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v2 = a2;
  ppszParameters = (PWSTR)a1;
  v52 = 0;
  *(_OWORD *)pszCmdTemplate = 0;
  v57 = 0;
  v58 = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::_Construct<2,unsigned short const *>(pszCmdTemplate, a2, v2[2]);
  v4 = pszCmdTemplate;
  if ( v58 > 7 )
    v4 = (PCWSTR *)pszCmdTemplate[0];
  *(_OWORD *)v59 = 0;
  v60 = 0;
  v61 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v59, v4, v57);
  v5 = 24;
  if ( !std::filesystem::path::has_extension((std::filesystem::path *)v59) )
    goto LABEL_25;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v6 = std::_WChar_traits<unsigned short>::length(L".lnk");
  std::wstring::_Construct<1,unsigned short const *>(&v62, L".lnk", v6);
  v52 = 121;
  v7 = (unsigned __int16 *)v59;
  if ( v61 > 7 )
    v7 = (unsigned __int16 *)v59[0];
  v8 = &v7[v60];
  v9 = v8;
  if ( (2 * v60) >> 1 < 2 )
    goto LABEL_11;
  if ( std::filesystem::_Is_drive_prefix((std::filesystem *)v7, v7) )
  {
    v7 = v10 + 2;
    goto LABEL_11;
  }
  if ( !(unsigned __int8)std::filesystem::_Is_slash_oper::operator()(*v10) )
    goto LABEL_11;
  if ( v33 >= 4 )
  {
    if ( (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(v7[3])
      && (v42 == 4 || !(unsigned __int8)std::filesystem::_Is_slash_oper::operator()(v7[4])) )
    {
      if ( (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(v7[1])
        && ((v46 = v7[2], v46 == 63) || v46 == 46)
        || v45 == 63 && v7[2] == 63 )
      {
        v7 += 3;
        goto LABEL_11;
      }
    }
  }
  else if ( v33 < 3 )
  {
    goto LABEL_11;
  }
  if ( !(unsigned __int8)std::filesystem::_Is_slash_oper::operator()(v7[1])
    || (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(v7[2]) )
  {
LABEL_11:
    if ( v7 != v8 )
    {
      while ( (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(*v7) )
      {
        v7 = (unsigned __int16 *)(v11 + 2);
        if ( v7 == v8 )
          goto LABEL_17;
      }
      do
      {
        if ( (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(*(v9 - 1)) )
          break;
        v9 = v13;
      }
      while ( v12 != v13 );
    }
    goto LABEL_17;
  }
  v7 += 3;
  if ( v7 != v8 )
  {
    do
    {
      if ( (unsigned __int8)std::filesystem::_Is_slash_oper::operator()(*v7) )
        break;
      ++v7;
    }
    while ( v7 != v8 );
    goto LABEL_11;
  }
LABEL_17:
  v14 = std::_Find_vectorized<unsigned short const,unsigned short>(v9, v8, 58);
  if ( v9 == (unsigned __int16 *)v14 )
    goto LABEL_92;
  v15 = (_WORD *)(v14 - 2);
  if ( v9 == (unsigned __int16 *)(v14 - 2) )
    goto LABEL_92;
  if ( *v15 != 46 )
  {
    while ( 1 )
    {
      if ( v9 == --v15 )
        goto LABEL_92;
      if ( *v15 == 46 )
        goto LABEL_22;
    }
  }
  if ( v9 == (unsigned __int16 *)(v14 - 4) && *(_WORD *)(v14 - 4) == 46 )
LABEL_92:
    v15 = (_WORD *)v14;
LABEL_22:
  v65 = 0;
  v66 = 0;
  v67 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v65, v15, (v14 - (__int64)v15) >> 1);
  v5 = -5;
  v16 = &v62;
  if ( v64 > 7 )
    v16 = (__int128 *)v62;
  v53[0] = v16;
  v53[1] = v63;
  if ( (unsigned int)std::filesystem::path::compare(&v65, v53) )
  {
LABEL_25:
    v17 = 0;
    goto LABEL_26;
  }
  v17 = 1;
LABEL_26:
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    std::wstring::_Tidy_deallocate(&v65);
  }
  if ( (v5 & 1) != 0 )
    std::wstring::_Tidy_deallocate(&v62);
  if ( v17 )
  {
    v53[0] = 0;
    Instance = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, v53);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
    v49 = 0;
    v36 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v53[0];
    v49 = 0;
    v37 = (*v36)(v53[0], &GUID_0000010b_0000_0000_c000_000000000046, &v49);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
        (const char *)(unsigned int)v37,
        ppva);
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    if ( (*(int (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v49 + 40LL))(v49, v2, 0) < 0 )
    {
      std::wstring::wstring(a1, &pvData);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&v49);
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(v53);
      goto LABEL_48;
    }
    v38 = pszCmdTemplate;
    if ( v57 >= 0x104 )
    {
      v57 = 260;
      if ( v58 > 7 )
        v38 = (PCWSTR *)pszCmdTemplate[0];
      *((_WORD *)v38 + 260) = 0;
    }
    else
    {
      std::wstring::append(pszCmdTemplate, 260 - v57, 0);
    }
    v39 = pszCmdTemplate;
    if ( v58 > 7 )
      v39 = (PCWSTR *)pszCmdTemplate[0];
    v40 = (*(__int64 (__fastcall **)(LPVOID, PCWSTR *, __int64, _QWORD))(*(_QWORD *)v53[0] + 24LL))(v53[0], v39, 260, 0);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
        (const char *)(unsigned int)v40,
        4);
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v53[0] )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53[0] + 16LL))(v53[0]);
  }
  ppszParameters = 0;
  ppszApplication = 0;
  v18 = (const WCHAR *)pszCmdTemplate;
  if ( v58 > 7 )
    v18 = pszCmdTemplate[0];
  if ( SHEvaluateSystemCommandTemplate(v18, &ppszApplication, 0, &ppszParameters) < 0 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v34 = std::_WChar_traits<unsigned short>::length(&pvData);
    std::wstring::_Construct<1,unsigned short const *>(a1, &pvData, v34);
    if ( ppszParameters )
      CoTaskMemFree(ppszParameters);
    v31 = ppszApplication;
    if ( ppszApplication )
      goto LABEL_47;
  }
  else
  {
    std::wstring::wstring(v53);
    LODWORD(v49) = 0;
    if ( !(unsigned int)SHGetFileDescriptionW(ppszApplication, 0, 0, 0, &v49) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x71,
        (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
        v19);
    v20 = (unsigned int)v49;
    v21 = v54;
    if ( (unsigned int)v49 <= v54 )
    {
      v54 = (unsigned int)v49;
      v41 = v53;
      if ( v55 > 7 )
        v41 = (LPVOID *)v53[0];
      *((_WORD *)v41 + (unsigned int)v49) = 0;
    }
    else
    {
      v22 = (unsigned int)v49 - v54;
      v23 = v55;
      if ( v22 <= v55 - v54 )
      {
        v54 = (unsigned int)v49;
        v43 = v53;
        if ( v55 > 7 )
          v43 = (LPVOID *)v53[0];
        wmemset((wchar_t *)v43 + v21, 0, (unsigned int)v49 - v21);
        *(_WORD *)(v44 + 2 * v20) = 0;
      }
      else
      {
        if ( 0x7FFFFFFFFFFFFFFELL - v54 < v22 )
          std::_Xlength_error("string too long");
        v24 = std::wstring::_Calculate_growth((unsigned int)v49, v55);
        size_of = std::_Get_size_of_n<2>(v24 + 1);
        v26 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
        v54 = v20;
        v55 = v24;
        v27 = (unsigned int)v20 - v21;
        if ( v23 <= 7 )
        {
          LOWORD(ppv) = 0;
          _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v26, v53, v21, v27, ppv);
        }
        else
        {
          v28 = v53[0];
          LOWORD(ppv) = 0;
          _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(v26, v53[0], v21, v27, ppv);
          std::_Deallocate<16>(v28, 2 * v23 + 2);
        }
        v53[0] = v26;
      }
    }
    v29 = v53;
    if ( v55 > 7 )
      v29 = (LPVOID *)v53[0];
    if ( !(unsigned int)SHGetFileDescriptionW(ppszApplication, 0, 0, v29, &v49) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x73,
        (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
        v30);
    std::wstring::wstring(a1, v53);
    std::wstring::_Tidy_deallocate(v53);
    if ( ppszParameters )
      CoTaskMemFree(ppszParameters);
    v31 = ppszApplication;
    if ( ppszApplication )
LABEL_47:
      CoTaskMemFree(v31);
  }
LABEL_48:
  std::wstring::_Tidy_deallocate(v59);
  std::wstring::_Tidy_deallocate(pszCmdTemplate);
  return a1;
}

```

## disassembly

```asm
0x18005dca0  mov     [rsp-8+arg_10], rbx
0x18005dca5  push    rbp
0x18005dca6  push    rsi
0x18005dca7  push    rdi
0x18005dca8  push    r12
0x18005dcaa  push    r13
0x18005dcac  push    r14
0x18005dcae  push    r15
0x18005dcb0  lea     rbp, [rsp-27h]
0x18005dcb5  sub     rsp, 100h
0x18005dcbc  mov     rax, cs:__security_cookie
0x18005dcc3  xor     rax, rsp
0x18005dcc6  mov     [rbp+57h+var_40], rax
0x18005dcca  mov     rsi, rdx
0x18005dccd  mov     r13, rcx
0x18005dcd0  mov     [rsp+130h+ppszParameters], rcx
0x18005dcd5  xor     r12d, r12d
0x18005dcd8  mov     [rsp+130h+var_E8], r12d
0x18005dcdd  xorps   xmm0, xmm0
0x18005dce0  movups  xmmword ptr [rbp+57h+pszCmdTemplate], xmm0
0x18005dce4  mov     [rbp+57h+var_B0], r12
0x18005dce8  mov     [rbp+57h+var_A8], r12
0x18005dcec  cmp     qword ptr [rdx+18h], 7
0x18005dcf1  jbe     short loc_18005DCF6
0x18005dcf3  mov     rdx, [rdx]
0x18005dcf6  mov     r8, [rsi+10h]
0x18005dcfa  lea     rcx, [rbp+57h+pszCmdTemplate]
0x18005dcfe  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18005dd03  nop
0x18005dd04  lea     rdx, [rbp+57h+pszCmdTemplate]
0x18005dd08  cmp     [rbp+57h+var_A8], 7
0x18005dd0d  cmova   rdx, [rbp+57h+pszCmdTemplate]
0x18005dd12  xorps   xmm0, xmm0
0x18005dd15  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18005dd19  mov     [rbp+57h+var_90], r12
0x18005dd1d  mov     [rbp+57h+var_88], r12
0x18005dd21  mov     r8, [rbp+57h+var_B0]
0x18005dd25  lea     rcx, [rbp+57h+var_A0]
0x18005dd29  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005dd2e  mov     ebx, 18h
0x18005dd33  lea     rcx, [rbp+57h+var_A0]; this
0x18005dd37  call    ?has_extension@path@filesystem@std@@QEBA_NXZ; std::filesystem::path::has_extension(void)
0x18005dd3c  test    al, al
0x18005dd3e  jz      loc_18005DE8B
0x18005dd44  xorps   xmm0, xmm0
0x18005dd47  movups  [rbp+57h+var_80], xmm0
0x18005dd4b  mov     [rbp+57h+var_70], r12
0x18005dd4f  mov     [rbp+57h+var_68], r12
0x18005dd53  lea     rcx, pszExt; ".lnk"
0x18005dd5a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005dd5f  mov     r8, rax
0x18005dd62  lea     rdx, pszExt; ".lnk"
0x18005dd69  lea     rcx, [rbp+57h+var_80]
0x18005dd6d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005dd72  nop
0x18005dd73  mov     [rsp+130h+var_E8], 79h ; 'y'
0x18005dd7b  lea     rdx, [rbp+57h+var_A0]
0x18005dd7f  cmp     [rbp+57h+var_88], 7
0x18005dd84  cmova   rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18005dd89  mov     rax, [rbp+57h+var_90]
0x18005dd8d  lea     r8, [rax+rax]
0x18005dd91  lea     r10, [r8+rdx]
0x18005dd95  mov     rbx, r10
0x18005dd98  sar     r8, 1
0x18005dd9b  cmp     r8, 2
0x18005dd9f  jl      short loc_18005DDB5
0x18005dda1  mov     rcx, rdx; this
0x18005dda4  call    ?_Is_drive_prefix@filesystem@std@@YA_NQEBG@Z; std::filesystem::_Is_drive_prefix(ushort const * const)
0x18005dda9  test    al, al
0x18005ddab  jz      loc_18005E099
0x18005ddb1  add     rdx, 4
0x18005ddb5  cmp     rdx, r10
0x18005ddb8  jz      short loc_18005DDEA
0x18005ddba  movzx   ecx, word ptr [rdx]
0x18005ddbd  call    ??R_Is_slash_oper@filesystem@std@@SA_NG@Z; std::filesystem::_Is_slash_oper::operator()(ushort)
0x18005ddc2  test    al, al
0x18005ddc4  jz      short loc_18005DDD1
0x18005ddc6  add     rdx, 2
0x18005ddca  cmp     rdx, r10
0x18005ddcd  jnz     short loc_18005DDBA
0x18005ddcf  jmp     short loc_18005DDEA
0x18005ddd1  lea     r8, [rbx-2]
0x18005ddd5  movzx   ecx, word ptr [r8]
0x18005ddd9  call    ??R_Is_slash_oper@filesystem@std@@SA_NG@Z; std::filesystem::_Is_slash_oper::operator()(ushort)
0x18005ddde  test    al, al
0x18005dde0  jnz     short loc_18005DDEA
0x18005dde2  mov     rbx, r8
0x18005dde5  cmp     rdx, r8
0x18005dde8  jnz     short loc_18005DDD1
0x18005ddea  mov     r8d, 3Ah ; ':'
0x18005ddf0  mov     rdx, r10
0x18005ddf3  mov     rcx, rbx
0x18005ddf6  call    ??$_Find_vectorized@$$CBGG@std@@YAPEBGQEBG0G@Z; std::_Find_vectorized<ushort const,ushort>(ushort const * const,ushort const * const,ushort)
0x18005ddfb  cmp     rbx, rax
0x18005ddfe  jz      loc_18005E332
0x18005de04  lea     rdx, [rax-2]
0x18005de08  cmp     rbx, rdx
0x18005de0b  jz      loc_18005E332
0x18005de11  cmp     word ptr [rdx], 2Eh ; '.'
0x18005de15  jz      loc_18005E31B
0x18005de1b  nop     dword ptr [rax+rax+00h]
0x18005de20  sub     rdx, 2
0x18005de24  cmp     rbx, rdx
0x18005de27  jz      loc_18005E332
0x18005de2d  cmp     word ptr [rdx], 2Eh ; '.'
0x18005de31  jnz     short loc_18005DE20
0x18005de33  xorps   xmm0, xmm0
0x18005de36  movups  [rbp+57h+var_60], xmm0
0x18005de3a  mov     [rbp+57h+var_50], r12
0x18005de3e  mov     [rbp+57h+var_48], r12
0x18005de42  sub     rax, rdx
0x18005de45  sar     rax, 1
0x18005de48  mov     r8, rax
0x18005de4b  lea     rcx, [rbp+57h+var_60]
0x18005de4f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005de54  mov     ebx, 3FBh
0x18005de59  lea     rax, [rbp+57h+var_80]
0x18005de5d  cmp     [rbp+57h+var_68], 7
0x18005de62  cmova   rax, qword ptr [rbp+57h+var_80]
0x18005de67  mov     [rsp+130h+var_E0], rax
0x18005de6c  mov     rax, [rbp+57h+var_70]
0x18005de70  mov     [rsp+130h+var_D8], rax
0x18005de75  lea     rdx, [rsp+130h+var_E0]
0x18005de7a  lea     rcx, [rbp+57h+var_60]
0x18005de7e  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; std::filesystem::path::compare(std::basic_string_view<ushort>)
0x18005de83  test    eax, eax
0x18005de85  jz      loc_18005E07B
0x18005de8b  xor     dil, dil
0x18005de8e  test    bl, 2
0x18005de91  jz      short loc_18005DEA0
0x18005de93  and     ebx, 0FFFFFFFDh
0x18005de96  lea     rcx, [rbp+57h+var_60]
0x18005de9a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005de9f  nop
0x18005dea0  test    bl, 1
0x18005dea3  jz      short loc_18005DEAE
0x18005dea5  lea     rcx, [rbp+57h+var_80]
0x18005dea9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005deae  test    dil, dil
0x18005deb1  jnz     loc_18005E115
0x18005deb7  mov     [rsp+130h+ppszParameters], r12
0x18005debc  mov     [rsp+130h+ppszApplication], r12
0x18005dec1  lea     rcx, [rbp+57h+pszCmdTemplate]
0x18005dec5  cmp     [rbp+57h+var_A8], 7
0x18005deca  cmova   rcx, [rbp+57h+pszCmdTemplate]; pszCmdTemplate
0x18005decf  lea     r9, [rsp+130h+ppszParameters]; ppszParameters
0x18005ded4  xor     r8d, r8d; ppszCommandLine
0x18005ded7  lea     rdx, [rsp+130h+ppszApplication]; ppszApplication
0x18005dedc  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18005dee2  test    eax, eax
0x18005dee4  js      loc_18005E0C2
0x18005deea  lea     rcx, [rsp+130h+var_E0]
0x18005deef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005def4  nop
0x18005def5  mov     dword ptr [rsp+130h+var_100], r12d
0x18005defa  mov     rbx, [rbp+5Fh]
0x18005defe  lea     rax, [rsp+130h+var_100]
0x18005df03  mov     qword ptr [rsp+130h+ppv], rax
0x18005df08  xor     r9d, r9d
0x18005df0b  xor     r8d, r8d
0x18005df0e  xor     edx, edx
0x18005df10  mov     rcx, [rsp+130h+ppszApplication]
0x18005df15  call    cs:__imp_SHGetFileDescriptionW
0x18005df1b  test    eax, eax
0x18005df1d  jz      loc_18005E364
0x18005df23  mov     r14d, dword ptr [rsp+130h+var_100]
0x18005df28  mov     rdi, [rbp+57h+var_D0]
0x18005df2c  cmp     r14, rdi
0x18005df2f  jbe     loc_18005E243
0x18005df35  mov     esi, r14d
0x18005df38  sub     rsi, rdi
0x18005df3b  mov     r15, [rbp+57h+var_C8]
0x18005df3f  mov     rax, r15
0x18005df42  sub     rax, rdi
0x18005df45  cmp     rsi, rax
0x18005df48  jbe     loc_18005E379
0x18005df4e  mov     r8, 7FFFFFFFFFFFFFFEh
0x18005df58  mov     rax, r8
0x18005df5b  sub     rax, rdi
0x18005df5e  cmp     rax, rsi
0x18005df61  jb      loc_18005E3A4
0x18005df67  mov     rdx, r15
0x18005df6a  mov     ecx, r14d
0x18005df6d  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18005df72  mov     rbx, rax
0x18005df75  lea     rcx, [rax+1]
0x18005df79  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x18005df7e  mov     rcx, rax
0x18005df81  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18005df86  mov     r12, rax
0x18005df89  mov     [rbp+57h+var_D0], r14
0x18005df8d  mov     [rbp+57h+var_C8], rbx
0x18005df91  mov     r9, rsi
0x18005df94  mov     r8, rdi
0x18005df97  mov     rcx, rax
0x18005df9a  cmp     r15, 7
0x18005df9e  jbe     loc_18005E083
0x18005dfa4  mov     rbx, [rsp+130h+var_E0]
0x18005dfa9  xor     edx, edx
0x18005dfab  mov     word ptr [rsp+130h+ppv], dx
0x18005dfb0  mov     rdx, rbx
0x18005dfb3  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18005dfb8  lea     rdx, ds:2[r15*2]
0x18005dfc0  mov     rcx, rbx
0x18005dfc3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dfc8  mov     [rsp+130h+var_E0], r12
0x18005dfcd  lea     r9, [rsp+130h+var_E0]
0x18005dfd2  cmp     [rbp+57h+var_C8], 7
0x18005dfd7  cmova   r9, [rsp+130h+var_E0]
0x18005dfdd  mov     rbx, [rbp+5Fh]
0x18005dfe1  lea     rax, [rsp+130h+var_100]
0x18005dfe6  mov     qword ptr [rsp+130h+ppv], rax
0x18005dfeb  xor     r8d, r8d
0x18005dfee  xor     edx, edx
0x18005dff0  mov     rcx, [rsp+130h+ppszApplication]
0x18005dff5  call    cs:__imp_SHGetFileDescriptionW
0x18005dffb  test    eax, eax
0x18005dffd  jz      loc_18005E3B2
0x18005e003  lea     rdx, [rsp+130h+var_E0]
0x18005e008  mov     rcx, r13
0x18005e00b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18005e010  nop
0x18005e011  lea     rcx, [rsp+130h+var_E0]
0x18005e016  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e01b  nop
0x18005e01c  mov     rcx, [rsp+130h+ppszParameters]; pv
0x18005e021  test    rcx, rcx
0x18005e024  jz      short loc_18005E02D
0x18005e026  call    cs:__imp_CoTaskMemFree
0x18005e02c  nop
0x18005e02d  mov     rcx, [rsp+130h+ppszApplication]; pv
0x18005e032  test    rcx, rcx
0x18005e035  jz      short loc_18005E03E
0x18005e037  call    cs:__imp_CoTaskMemFree
0x18005e03d  nop
0x18005e03e  lea     rcx, [rbp+57h+var_A0]
0x18005e042  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e047  nop
0x18005e048  lea     rcx, [rbp+57h+pszCmdTemplate]
0x18005e04c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e051  mov     rax, r13
0x18005e054  mov     rcx, [rbp+57h+var_40]
0x18005e058  xor     rcx, rsp; StackCookie
0x18005e05b  call    __security_check_cookie
0x18005e060  mov     rbx, [rsp+130h+arg_10]
0x18005e068  add     rsp, 100h
0x18005e06f  pop     r15
0x18005e071  pop     r14
0x18005e073  pop     r13
0x18005e075  pop     r12
0x18005e077  pop     rdi
0x18005e078  pop     rsi
0x18005e079  pop     rbp
0x18005e07a  retn
0x18005e07b  mov     dil, 1
0x18005e07e  jmp     loc_18005DE8E
0x18005e083  xor     eax, eax
0x18005e085  mov     word ptr [rsp+130h+ppv], ax
0x18005e08a  lea     rdx, [rsp+130h+var_E0]
0x18005e08f  call    ??R_lambda_b70241e9b5ebaad244db3e52d52cab17_@@SA@QEAGQEBG_K2G@Z; _lambda_b70241e9b5ebaad244db3e52d52cab17_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18005e094  jmp     loc_18005DFC8
0x18005e099  movzx   ecx, word ptr [rdx]
0x18005e09c  call    ??R_Is_slash_oper@filesystem@std@@SA_NG@Z; std::filesystem::_Is_slash_oper::operator()(ushort)
0x18005e0a1  test    al, al
0x18005e0a3  jz      loc_18005DDB5
0x18005e0a9  cmp     r8, 4
0x18005e0ad  jge     loc_18005E2BF
0x18005e0b3  cmp     r8, 3
0x18005e0b7  jl      loc_18005DDB5
0x18005e0bd  jmp     loc_18005E2E7
0x18005e0c2  xorps   xmm0, xmm0
0x18005e0c5  movups  xmmword ptr [r13+0], xmm0
0x18005e0ca  mov     [r13+10h], r12
0x18005e0ce  mov     [r13+18h], r12
0x18005e0d2  lea     rcx, pvData
0x18005e0d9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005e0de  mov     r8, rax
0x18005e0e1  lea     rdx, pvData
0x18005e0e8  mov     rcx, r13
0x18005e0eb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005e0f0  nop
0x18005e0f1  mov     rcx, [rsp+130h+ppszParameters]; pv
0x18005e0f6  test    rcx, rcx
0x18005e0f9  jz      short loc_18005E102
0x18005e0fb  call    cs:__imp_CoTaskMemFree
0x18005e101  nop
0x18005e102  mov     rcx, [rsp+130h+ppszApplication]
0x18005e107  test    rcx, rcx
0x18005e10a  jz      loc_18005E03E
0x18005e110  jmp     loc_18005E037
0x18005e115  mov     [rsp+130h+var_E0], r12
0x18005e11a  lea     rax, [rsp+130h+var_E0]
0x18005e11f  mov     qword ptr [rsp+130h+ppv], rax; int
0x18005e124  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18005e12b  xor     edx, edx; pUnkOuter
0x18005e12d  mov     r8d, 1; dwClsContext
0x18005e133  lea     rcx, CLSID_ShellLink; rclsid
0x18005e13a  call    cs:__imp_CoCreateInstance
0x18005e140  mov     rcx, [rbp+5Fh]; this
0x18005e144  test    eax, eax
  ... truncated ...
```
