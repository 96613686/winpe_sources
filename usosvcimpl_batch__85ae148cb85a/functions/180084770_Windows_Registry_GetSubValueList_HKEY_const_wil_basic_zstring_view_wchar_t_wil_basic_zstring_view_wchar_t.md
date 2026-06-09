# Windows::Registry::GetSubValueList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180084770`
- end: `0x180084ccc`
- name: `?GetSubValueList@Registry@Windows@@QEAA?AV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task`

## callers

- `0x18006e4a0`

## callees

- `0x1800108b4`
- `0x180010e80`
- `0x1800112d0`
- `0x180011320`
- `0x180011680`
- `0x18001171c`
- `0x18002c7c0`
- `0x180037d48`
- `0x180038694`
- `0x180039074`
- `0x180083744`
- `0x180083c20`
- `0x180084770`
- `0x1800dd930`
- `0x1800de12c`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084c4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084c4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800848a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800848a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084851`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084851`

## string_xrefs

- `0x180084c8d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180084ca2`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x180084cba`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 *__fastcall Windows::Registry::GetSubValueList(__int64 a1, __int64 *a2, __int64 a3, __int128 *a4, _OWORD *a5)
{
  __int128 *v5; // rbx
  _OWORD *v8; // rdi
  _QWORD *v9; // rax
  HKEY *v10; // rax
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  DWORD v13; // r12d
  unsigned int v14; // eax
  __int64 v15; // r8
  int v16; // r8d
  wchar_t **v17; // rax
  __int64 inserted; // rdi
  __int64 v19; // rbx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rdx
  size_t v22; // rsi
  size_t v23; // r14
  size_t v24; // r8
  int v25; // eax
  char v26; // al
  const wchar_t *v27; // rdx
  size_t v28; // rbx
  const wchar_t *v29; // rcx
  size_t v30; // rsi
  size_t v31; // r8
  int v32; // eax
  char v33; // al
  __int64 v34; // rdi
  _DWORD *v35; // rsi
  _QWORD *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h] BYREF
  __int128 *v45; // [rsp+70h] [rbp-90h]
  _OWORD *v46; // [rsp+78h] [rbp-88h]
  __int64 *v47; // [rsp+80h] [rbp-80h]
  __int128 v48; // [rsp+90h] [rbp-70h] BYREF
  int v49[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v51; // [rsp+C0h] [rbp-40h]
  wchar_t *S2[2]; // [rsp+D0h] [rbp-30h] BYREF
  size_t N; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v54; // [rsp+E8h] [rbp-18h]
  DWORD cchValueName; // [rsp+F0h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+F8h] [rbp-8h] BYREF
  char *v57; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v58[4]; // [rsp+108h] [rbp+8h] BYREF
  char v59; // [rsp+128h] [rbp+28h]
  char v60; // [rsp+130h] [rbp+30h]
  LPCWSTR lpSubKey[5]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR ValueName[256]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v5 = a4;
  v45 = a4;
  v47 = a2;
  v8 = a5;
  v46 = a5;
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  v9 = operator new(0x68u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *a2 = (__int64)v9;
  v44 = *a5;
  v43 = *v5;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, (__int64)lpSubKey, (const char **)&v43, (__int64)&v44);
  hKey = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator&(&hKey);
  v11 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v11 = lpSubKey[0];
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, v10);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v12,
      phkResult);
  v13 = 0;
  memset(ValueName, 0, sizeof(ValueName));
  while ( 1 )
  {
    cchValueName = 256;
    v14 = RegEnumValueW(hKey, v13, ValueName, &cchValueName, 0, 0, 0, 0);
    if ( v14 == 259 )
      break;
    if ( v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x205,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v14,
        phkResulta);
    *(_OWORD *)S2 = 0;
    N = 0;
    v54 = 0;
    v15 = -1;
    do
      ++v15;
    while ( ValueName[v15] );
    std::wstring::_Construct<1,wchar_t const *>(S2, ValueName);
    v17 = S2;
    if ( v54 > 7 )
      v17 = (wchar_t **)S2[0];
    *(_QWORD *)&v44 = v17;
    *((_QWORD *)&v44 + 1) = N;
    v48 = v44;
    *(_OWORD *)v49 = *v8;
    v50 = *v5;
    Windows::Registry::GetValue(a1, (unsigned int)&v57, v16, (unsigned int)&v50, (__int64)v49, (__int64)&v48);
    if ( (int)v57 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)(unsigned int)v57,
        phkResultb);
    inserted = *a2;
    v19 = *(_QWORD *)(*a2 + 8);
    v50 = (unsigned __int64)v19;
    while ( !*(_BYTE *)(v19 + 25) )
    {
      *(_QWORD *)&v50 = v19;
      v20 = (const wchar_t *)(v19 + 32);
      v21 = (const wchar_t *)S2;
      if ( v54 > 7 )
        v21 = S2[0];
      v22 = *(_QWORD *)(v19 + 48);
      if ( *(_QWORD *)(v19 + 56) > 7u )
        v20 = *(const wchar_t **)v20;
      v23 = N;
      v24 = *(_QWORD *)(v19 + 48);
      if ( N < v22 )
        v24 = N;
      v25 = wmemcmp(v20, v21, v24);
      if ( v25 )
      {
        if ( v25 >= 0 )
          goto LABEL_25;
      }
      else if ( v22 >= v23 )
      {
        if ( v22 <= v23 )
          goto LABEL_28;
LABEL_25:
        v26 = 1;
        goto LABEL_26;
      }
      v26 = -1;
LABEL_26:
      if ( v26 >= 0 )
      {
LABEL_28:
        DWORD2(v50) = 1;
        inserted = v19;
        v19 = *(_QWORD *)v19;
      }
      else
      {
        DWORD2(v50) = 0;
        v19 = *(_QWORD *)(v19 + 16);
      }
    }
    if ( *(_BYTE *)(inserted + 25) )
      goto LABEL_45;
    v27 = (const wchar_t *)(inserted + 32);
    v28 = *(_QWORD *)(inserted + 48);
    if ( *(_QWORD *)(inserted + 56) > 7u )
      v27 = *(const wchar_t **)v27;
    v29 = (const wchar_t *)S2;
    if ( v54 > 7 )
      v29 = S2[0];
    v30 = N;
    v31 = N;
    if ( v28 < N )
      v31 = *(_QWORD *)(inserted + 48);
    v32 = wmemcmp(v29, v27, v31);
    if ( v32 )
    {
      if ( v32 < 0 )
      {
LABEL_41:
        v33 = -1;
        goto LABEL_44;
      }
LABEL_43:
      v33 = 1;
LABEL_44:
      if ( v33 < 0 )
      {
LABEL_45:
        if ( a2[1] == 0x276276276276276LL )
          std::_Throw_tree_length_error();
        v34 = *a2;
        v43 = (unsigned __int64)a2;
        v35 = operator new(0x68u);
        *((_QWORD *)&v43 + 1) = v35;
        std::wstring::wstring(v35 + 8, S2);
        v35[16] = 0;
        *((_BYTE *)v35 + 96) = 0;
        *(_QWORD *)v35 = v34;
        *((_QWORD *)v35 + 1) = v34;
        *((_QWORD *)v35 + 2) = v34;
        *((_WORD *)v35 + 12) = 0;
        *((_QWORD *)&v43 + 1) = 0;
        inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(
                     a2,
                     &v50,
                     v35);
      }
    }
    else
    {
      if ( v30 < v28 )
        goto LABEL_41;
      if ( v30 > v28 )
        goto LABEL_43;
    }
    v36 = (_QWORD *)(inserted + 64);
    if ( v59 == -1 )
    {
      if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
        std::wstring::~wstring((void *)(inserted + 64));
      *(_BYTE *)(inserted + 96) = -1;
    }
    else if ( v59 )
    {
      if ( v59 == 1 )
      {
        if ( *(_BYTE *)(inserted + 96) == 1 )
        {
          *v36 = v58[0];
        }
        else
        {
          if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
            std::wstring::~wstring((void *)(inserted + 64));
          *(_BYTE *)(inserted + 96) = -1;
          *v36 = v58[0];
          *(_BYTE *)(inserted + 96) = 1;
        }
      }
      else if ( *(_BYTE *)(inserted + 96) == 2 )
      {
        std::wstring::operator=((void *)(inserted + 64));
      }
      else
      {
        std::wstring::wstring(&v50, v58);
        if ( *(char *)(inserted + 96) != -1 && (unsigned __int64)*(char *)(inserted + 96) >= 2 )
          std::wstring::~wstring((void *)(inserted + 64));
        *(_BYTE *)(inserted + 96) = -1;
        *(_OWORD *)v36 = v50;
        *(_OWORD *)(inserted + 80) = v51;
        *(_QWORD *)&v51 = 0;
        *((_QWORD *)&v51 + 1) = 7;
        LOWORD(v50) = 0;
        std::wstring::~wstring(&v50);
        *(_BYTE *)(inserted + 96) = 2;
      }
    }
    else
    {
      v37 = *(char *)(inserted + 96);
      if ( (_BYTE)v37 )
      {
        v38 = v37 + 1;
        if ( v38 && (unsigned __int64)(v38 - 1) >= 2 )
          std::wstring::~wstring((void *)(inserted + 64));
        *(_BYTE *)(inserted + 96) = -1;
        *(_DWORD *)v36 = v58[0];
        *(_BYTE *)(inserted + 96) = 0;
      }
      else
      {
        *(_DWORD *)v36 = v58[0];
      }
    }
    if ( v60 && v59 != -1 && v59 && v59 != 1 )
      std::wstring::~wstring(v58);
    std::wstring::~wstring(S2);
    ++v13;
    memset(ValueName, 0, sizeof(ValueName));
    v5 = v45;
    v8 = v46;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x180084770  mov     [rsp-8+arg_0], rbx
0x180084775  push    rbp
0x180084776  push    rsi
0x180084777  push    rdi
0x180084778  push    r12
0x18008477a  push    r13
0x18008477c  push    r14
0x18008477e  push    r15
0x180084780  lea     rbp, [rsp-270h]
0x180084788  sub     rsp, 370h
0x18008478f  mov     rax, cs:__security_cookie
0x180084796  xor     rax, rsp
0x180084799  mov     [rbp+2A0h+var_40], rax
0x1800847a0  mov     rbx, r9
0x1800847a3  mov     [rsp+3A0h+var_330], rbx
0x1800847a8  mov     r15, rdx
0x1800847ab  mov     r13, rcx
0x1800847ae  mov     [rbp+2A0h+var_320], rdx
0x1800847b2  mov     rdi, [rbp+2A0h+arg_20]
0x1800847b9  mov     [rsp+3A0h+var_328], rdi
0x1800847be  xor     r14d, r14d
0x1800847c1  mov     [rsp+3A0h+var_360], r14d
0x1800847c6  xorps   xmm0, xmm0
0x1800847c9  movups  xmmword ptr [rdx], xmm0
0x1800847cc  mov     [rdx], r14
0x1800847cf  mov     [rdx+8], r14
0x1800847d3  lea     ecx, [r14+68h]; Size
0x1800847d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800847dc  mov     [rax], rax
0x1800847df  mov     [rax+8], rax
0x1800847e3  mov     [rax+10h], rax
0x1800847e7  mov     word ptr [rax+18h], 101h
0x1800847ed  mov     [r15], rax
0x1800847f0  mov     [rsp+3A0h+var_360], 1
0x1800847f8  movaps  xmm0, xmmword ptr [rdi]
0x1800847fb  movdqa  [rsp+3A0h+var_340], xmm0
0x180084801  movaps  xmm1, xmmword ptr [rbx]
0x180084804  movdqa  [rsp+3A0h+var_350], xmm1
0x18008480a  lea     r9, [rsp+3A0h+var_340]
0x18008480f  lea     r8, [rsp+3A0h+var_350]
0x180084814  lea     rdx, [rbp+2A0h+lpSubKey]
0x180084818  mov     rcx, r13
0x18008481b  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180084820  nop
0x180084821  mov     [rbp+2A0h+hKey], r14
0x180084825  lea     rcx, [rbp+2A0h+hKey]
0x180084829  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator&(void)
0x18008482e  lea     rdx, [rbp+2A0h+lpSubKey]
0x180084832  cmp     [rbp+2A0h+var_250], 7
0x180084837  cmova   rdx, [rbp+2A0h+lpSubKey]; lpSubKey
0x18008483c  mov     [rsp+3A0h+phkResult], rax; unsigned int
0x180084841  mov     r9d, 20019h; samDesired
0x180084847  xor     r8d, r8d; ulOptions
0x18008484a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084851  call    cs:__imp_RegOpenKeyExW
0x180084857  mov     rcx, [rbp+2A8h]; this
0x18008485e  test    eax, eax
0x180084860  jnz     loc_180084C9F
0x180084866  mov     r12d, r14d
0x180084869  xor     edx, edx; Val
0x18008486b  mov     r8d, 200h; Size
0x180084871  lea     rcx, [rbp+2A0h+ValueName]; void *
0x180084875  call    memset
0x18008487a  mov     [rbp+2A0h+cchValueName], 100h
0x180084881  mov     [rsp+3A0h+lpcbData], r14; lpcbData
0x180084886  mov     [rsp+3A0h+lpData], r14; lpData
0x18008488b  mov     [rsp+3A0h+lpType], r14; lpType
0x180084890  mov     [rsp+3A0h+phkResult], r14; unsigned int
0x180084895  lea     r9, [rbp+2A0h+cchValueName]; lpcchValueName
0x180084899  lea     r8, [rbp+2A0h+ValueName]; lpValueName
0x18008489d  mov     edx, r12d; dwIndex
0x1800848a0  mov     rcx, [rbp+2A0h+hKey]; hKey
0x1800848a4  call    cs:__imp_RegEnumValueW
0x1800848aa  cmp     eax, 103h
0x1800848af  jz      loc_180084C44
0x1800848b5  mov     rcx, [rbp+2A8h]; this
0x1800848bc  test    eax, eax
0x1800848be  jnz     loc_180084C8A
0x1800848c4  xorps   xmm0, xmm0
0x1800848c7  movups  xmmword ptr [rbp+2A0h+S2], xmm0
0x1800848cb  mov     [rbp+2A0h+N], r14
0x1800848cf  mov     [rbp+2A0h+var_2B8], r14
0x1800848d3  lea     rax, [rbp+2A0h+ValueName]
0x1800848d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800848db  inc     r8
0x1800848de  cmp     [rax+r8*2], r14w
0x1800848e3  jnz     short loc_1800848DB
0x1800848e5  lea     rdx, [rbp+2A0h+ValueName]
0x1800848e9  lea     rcx, [rbp+2A0h+S2]
0x1800848ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800848f2  nop
0x1800848f3  lea     rax, [rbp+2A0h+S2]
0x1800848f7  cmp     [rbp+2A0h+var_2B8], 7
0x1800848fc  cmova   rax, [rbp+2A0h+S2]
0x180084901  mov     qword ptr [rsp+3A0h+var_340], rax
0x180084906  mov     rax, [rbp+2A0h+N]
0x18008490a  mov     qword ptr [rsp+3A0h+var_340+8], rax
0x18008490f  movaps  xmm0, [rsp+3A0h+var_340]
0x180084914  movdqa  [rbp+2A0h+var_310], xmm0
0x180084919  movaps  xmm1, xmmword ptr [rdi]
0x18008491c  movdqa  xmmword ptr [rbp+2A0h+var_300], xmm1
0x180084921  movaps  xmm0, xmmword ptr [rbx]
0x180084924  movdqa  [rbp+2A0h+var_2F0], xmm0
0x180084929  lea     rax, [rbp+2A0h+var_310]
0x18008492d  mov     [rsp+3A0h+lpType], rax
0x180084932  lea     rax, [rbp+2A0h+var_300]
0x180084936  mov     [rsp+3A0h+phkResult], rax; int
0x18008493b  lea     r9, [rbp+2A0h+var_2F0]
0x18008493f  lea     rdx, [rbp+2A0h+var_2A0]
0x180084943  mov     rcx, r13
0x180084946  call    ?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z; Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18008494b  nop
0x18008494c  mov     rcx, [rbp+2A8h]; this
0x180084953  mov     r9d, dword ptr [rbp+2A0h+var_2A0]; char *
0x180084957  test    r9d, r9d
0x18008495a  js      loc_180084CBA
0x180084960  mov     rdi, [r15]
0x180084963  mov     rbx, [rdi+8]
0x180084967  mov     qword ptr [rbp+2A0h+var_2F0], rbx
0x18008496b  mov     qword ptr [rbp+2A0h+var_2F0+8], 0
0x180084973  jmp     short loc_1800849EA
0x180084975  mov     qword ptr [rbp+2A0h+var_2F0], rbx
0x180084979  lea     rcx, [rbx+20h]
0x18008497d  lea     rdx, [rbp+2A0h+S2]
0x180084981  cmp     [rbp+2A0h+var_2B8], 7
0x180084986  cmova   rdx, [rbp+2A0h+S2]; S2
0x18008498b  mov     rsi, [rcx+10h]
0x18008498f  cmp     qword ptr [rcx+18h], 7
0x180084994  jbe     short loc_180084999
0x180084996  mov     rcx, [rcx]; S1
0x180084999  mov     r14, [rbp+2A0h+N]
0x18008499d  mov     r8, rsi
0x1800849a0  cmp     r14, rsi
0x1800849a3  cmovb   r8, r14; N
0x1800849a7  call    wmemcmp
0x1800849ac  test    eax, eax
0x1800849ae  jz      short loc_1800849B9
0x1800849b0  xor     r14d, r14d
0x1800849b3  test    eax, eax
0x1800849b5  jns     short loc_1800849CA
0x1800849b7  jmp     short loc_1800849C1
0x1800849b9  cmp     rsi, r14
0x1800849bc  jnb     short loc_1800849C5
0x1800849be  xor     r14d, r14d
0x1800849c1  mov     al, 0FFh
0x1800849c3  jmp     short loc_1800849CC
0x1800849c5  jbe     short loc_1800849DA
0x1800849c7  xor     r14d, r14d
0x1800849ca  mov     al, 1
0x1800849cc  test    al, al
0x1800849ce  jns     short loc_1800849DD
0x1800849d0  mov     dword ptr [rbp+2A0h+var_2F0+8], r14d
0x1800849d4  mov     rbx, [rbx+10h]
0x1800849d8  jmp     short loc_1800849EA
0x1800849da  xor     r14d, r14d
0x1800849dd  mov     dword ptr [rbp+2A0h+var_2F0+8], 1
0x1800849e4  mov     rdi, rbx
0x1800849e7  mov     rbx, [rbx]
0x1800849ea  cmp     [rbx+19h], r14b
0x1800849ee  jz      short loc_180084975
0x1800849f0  cmp     [rdi+19h], r14b
0x1800849f4  jnz     short loc_180084A42
0x1800849f6  lea     rdx, [rdi+20h]
0x1800849fa  mov     rbx, [rdx+10h]
0x1800849fe  cmp     qword ptr [rdx+18h], 7
0x180084a03  jbe     short loc_180084A08
0x180084a05  mov     rdx, [rdx]; S2
0x180084a08  lea     rcx, [rbp+2A0h+S2]
0x180084a0c  cmp     [rbp+2A0h+var_2B8], 7
0x180084a11  cmova   rcx, [rbp+2A0h+S2]; S1
0x180084a16  mov     rsi, [rbp+2A0h+N]
0x180084a1a  mov     r8, rsi
0x180084a1d  cmp     rbx, rsi
0x180084a20  cmovb   r8, rbx; N
0x180084a24  call    wmemcmp
0x180084a29  test    eax, eax
0x180084a2b  jz      short loc_180084A31
0x180084a2d  jns     short loc_180084A3C
0x180084a2f  jmp     short loc_180084A36
0x180084a31  cmp     rsi, rbx
0x180084a34  jnb     short loc_180084A3A
0x180084a36  mov     al, 0FFh
0x180084a38  jmp     short loc_180084A3E
0x180084a3a  jbe     short loc_180084ABB
0x180084a3c  mov     al, 1
0x180084a3e  test    al, al
0x180084a40  jns     short loc_180084ABB
0x180084a42  mov     rax, 276276276276276h
0x180084a4c  cmp     [r15+8], rax
0x180084a50  jz      loc_180084CB4
0x180084a56  mov     rdi, [r15]
0x180084a59  mov     qword ptr [rsp+3A0h+var_350], r15
0x180084a5e  mov     qword ptr [rsp+3A0h+var_350+8], r14
0x180084a63  mov     ecx, 68h ; 'h'; Size
0x180084a68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180084a6d  mov     rsi, rax
0x180084a70  mov     qword ptr [rsp+3A0h+var_350+8], rax
0x180084a75  lea     rdx, [rbp+2A0h+S2]
0x180084a79  lea     rcx, [rax+20h]
0x180084a7d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180084a82  mov     [rsi+40h], r14d
0x180084a86  mov     [rsi+60h], r14b
0x180084a8a  mov     [rsi], rdi
0x180084a8d  mov     [rsi+8], rdi
0x180084a91  mov     [rsi+10h], rdi
0x180084a95  mov     word ptr [rsi+18h], 0
0x180084a9b  mov     qword ptr [rsp+3A0h+var_350+8], r14
0x180084aa0  movups  xmm0, [rbp+2A0h+var_2F0]
0x180084aa4  movdqu  [rbp+2A0h+var_2F0], xmm0
0x180084aa9  mov     r8, rsi
0x180084aac  lea     rdx, [rbp+2A0h+var_2F0]
0x180084ab0  mov     rcx, r15
0x180084ab3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@U12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@U12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@U12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::hstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<winrt::hstring const,winrt::hstring>,void *> *>,std::_Tree_node<std::pair<winrt::hstring const,winrt::hstring>,void *> * const)
0x180084ab8  mov     rdi, rax
0x180084abb  lea     rbx, [rdi+40h]
0x180084abf  movsx   rax, [rbp+2A0h+var_278]
0x180084ac4  add     rax, 1
0x180084ac8  jz      loc_180084BCE
0x180084ace  sub     rax, 1
0x180084ad2  jz      loc_180084B95
0x180084ad8  cmp     rax, 1
0x180084adc  jz      short loc_180084B53
0x180084ade  lea     rdx, [rbp+2A0h+var_298]
0x180084ae2  cmp     byte ptr [rbx+20h], 2
0x180084ae6  jnz     short loc_180084AF5
0x180084ae8  mov     rcx, rbx; void *
0x180084aeb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180084af0  jmp     loc_180084BF1
0x180084af5  lea     rcx, [rbp+2A0h+var_2F0]
0x180084af9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180084afe  movsx   rax, byte ptr [rbx+20h]
0x180084b03  add     rax, 1
0x180084b07  jz      short loc_180084B1D
0x180084b09  sub     rax, 1
0x180084b0d  jz      short loc_180084B1D
0x180084b0f  cmp     rax, 1
0x180084b13  jz      short loc_180084B1D
0x180084b15  mov     rcx, rbx; void *
0x180084b18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084b1d  mov     byte ptr [rbx+20h], 0FFh
0x180084b21  movups  xmm0, [rbp+2A0h+var_2F0]
0x180084b25  movups  xmmword ptr [rbx], xmm0
0x180084b28  movups  xmm1, [rbp+2A0h+var_2E0]
0x180084b2c  movups  xmmword ptr [rbx+10h], xmm1
0x180084b30  mov     qword ptr [rbp+2A0h+var_2E0], r14
0x180084b34  mov     qword ptr [rbp+2A0h+var_2E0+8], 7
0x180084b3c  mov     word ptr [rbp+2A0h+var_2F0], r14w
0x180084b41  lea     rcx, [rbp+2A0h+var_2F0]; void *
0x180084b45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084b4a  mov     byte ptr [rbx+20h], 2
0x180084b4e  jmp     loc_180084BF1
0x180084b53  cmp     byte ptr [rbx+20h], 1
0x180084b57  jnz     short loc_180084B65
0x180084b59  mov     rax, [rbp+2A0h+var_298]
0x180084b5d  mov     [rbx], rax
0x180084b60  jmp     loc_180084BF1
0x180084b65  movsx   rax, byte ptr [rbx+20h]
0x180084b6a  add     rax, 1
0x180084b6e  jz      short loc_180084B84
0x180084b70  sub     rax, 1
0x180084b74  jz      short loc_180084B84
0x180084b76  cmp     rax, 1
0x180084b7a  jz      short loc_180084B84
0x180084b7c  mov     rcx, rbx; void *
0x180084b7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084b84  mov     byte ptr [rbx+20h], 0FFh
0x180084b88  mov     rax, [rbp+2A0h+var_298]
0x180084b8c  mov     [rbx], rax
0x180084b8f  mov     byte ptr [rbx+20h], 1
0x180084b93  jmp     short loc_180084BF1
0x180084b95  movsx   rax, byte ptr [rbx+20h]
0x180084b9a  test    al, al
0x180084b9c  jnz     short loc_180084BA5
0x180084b9e  mov     eax, dword ptr [rbp+2A0h+var_298]
0x180084ba1  mov     [rbx], eax
0x180084ba3  jmp     short loc_180084BF1
0x180084ba5  add     rax, 1
0x180084ba9  jz      short loc_180084BBF
0x180084bab  sub     rax, 1
0x180084baf  jz      short loc_180084BBF
0x180084bb1  cmp     rax, 1
0x180084bb5  jz      short loc_180084BBF
0x180084bb7  mov     rcx, rbx; void *
0x180084bba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084bbf  mov     byte ptr [rbx+20h], 0FFh
0x180084bc3  mov     eax, dword ptr [rbp+2A0h+var_298]
0x180084bc6  mov     [rbx], eax
0x180084bc8  mov     [rbx+20h], r14b
0x180084bcc  jmp     short loc_180084BF1
0x180084bce  movsx   rax, byte ptr [rbx+20h]
0x180084bd3  add     rax, 1
0x180084bd7  jz      short loc_180084BED
0x180084bd9  sub     rax, 1
0x180084bdd  jz      short loc_180084BED
0x180084bdf  cmp     rax, 1
0x180084be3  jz      short loc_180084BED
0x180084be5  mov     rcx, rbx; void *
0x180084be8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180084bed  mov     byte ptr [rbx+20h], 0FFh
0x180084bf1  cmp     [rbp+2A0h+var_270], r14b
  ... truncated ...
```
