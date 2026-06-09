# DiagUtils::GetFilesFromPattern(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800661dc`
- end: `0x180066466`
- name: `?GetFilesFromPattern@DiagUtils@@SA?AV?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035a44`

## callees

- `0x180018b04`
- `0x180018c00`
- `0x180018d28`
- `0x180018eec`
- `0x180028ed4`
- `0x180065c40`
- `0x180066034`
- `0x1800661dc`
- `0x18008fe00`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066435`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006629c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006629c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006641a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006641a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800663f3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800663f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *__fastcall DiagUtils::GetFilesFromPattern(__int64 *a1, __int64 *a2)
{
  __int64 v3; // rcx
  const WCHAR *v4; // rcx
  char *FirstFileW; // rbx
  const wchar_t *v6; // r8
  LPCWSTR *v7; // rcx
  const wchar_t *i; // rax
  const wchar_t *v9; // rdx
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  int v13; // esi
  __int64 v14; // rax
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  char *v19; // [rsp+50h] [rbp-B0h]
  __int64 *v20; // [rsp+58h] [rbp-A8h]
  _BYTE v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v23; // [rsp+98h] [rbp-68h]
  _BYTE Src[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  v20 = a1;
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  pv = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    (char *)&pv,
    *a2);
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)pv + v3) );
  *(_QWORD *)&v17 = pv;
  *((_QWORD *)&v17 + 1) = v3;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(lpFileName, &v17);
  memset(&FindFileData, 0, sizeof(FindFileData));
  v4 = (const WCHAR *)lpFileName;
  if ( v23 > 7 )
    v4 = lpFileName[0];
  FirstFileW = (char *)FindFirstFileW(v4, &FindFileData);
  v19 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v7 = lpFileName;
    if ( v23 > 7 )
      v7 = (LPCWSTR *)lpFileName[0];
    for ( i = std::filesystem::_Find_root_name_end(
                (std::filesystem *)v7,
                (const wchar_t *const)v7 + (__int64)lpFileName[2],
                v6); i != v9 && (*i == 92 || *i == 47); ++i )
      ;
    if ( i != v9 )
    {
      do
      {
        v11 = v9 - 1;
        if ( *(v9 - 1) == 92 )
          break;
        if ( *v11 == 47 )
          break;
        --v9;
      }
      while ( i != v11 );
      if ( i != v9 )
      {
        do
        {
          v12 = v9 - 1;
          if ( *(v9 - 1) != 92 && *v12 != 47 )
            break;
          --v9;
        }
        while ( i != v12 );
      }
    }
    *(_QWORD *)&v17 = v10;
    *((_QWORD *)&v17 + 1) = ((__int64)v9 - v10) >> 1;
    v18 = v17;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v25, &v18);
    v13 = 57;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v14 = -1;
        do
          ++v14;
        while ( FindFileData.cFileName[v14] );
        *(_QWORD *)&v18 = FindFileData.cFileName;
        *((_QWORD *)&v18 + 1) = v14;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v21, &v18);
        v13 |= 2u;
        std::filesystem::operator/(Src, v25, v21);
        std::wstring::~wstring((__int64)v21);
        if ( a1[1] == a1[2] )
        {
          std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
            a1,
            a1[1],
            (__int64)Src);
        }
        else
        {
          std::wstring::wstring(a1[1], (__int64)Src);
          a1[1] += 32;
        }
        std::wstring::~wstring((__int64)Src);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    std::wstring::~wstring((__int64)v25);
    FindClose(FirstFileW);
  }
  std::wstring::~wstring((__int64)lpFileName);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x1800661dc  mov     [rsp-8+arg_10], rbx
0x1800661e1  mov     [rsp-8+arg_18], rsi
0x1800661e6  push    rbp
0x1800661e7  push    rdi
0x1800661e8  push    r14
0x1800661ea  lea     rbp, [rsp-240h]
0x1800661f2  sub     rsp, 340h
0x1800661f9  mov     rax, cs:__security_cookie
0x180066200  xor     rax, rsp
0x180066203  mov     [rbp+250h+var_20], rax
0x18006620a  mov     rdi, rcx
0x18006620d  mov     [rsp+350h+var_2F8], rcx
0x180066212  mov     ecx, 1
0x180066217  mov     [rsp+350h+var_330], ecx
0x18006621b  xorps   xmm0, xmm0
0x18006621e  movups  xmmword ptr [rdi], xmm0
0x180066221  xor     r14d, r14d
0x180066224  mov     [rdi], r14
0x180066227  mov     [rdi+8], r14
0x18006622b  mov     [rdi+10h], r14
0x18006622f  mov     [rsp+350h+var_330], ecx
0x180066233  mov     [rsp+350h+pv], r14
0x180066238  mov     rdx, [rdx]
0x18006623b  lea     rcx, [rsp+350h+pv]
0x180066240  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180066245  nop
0x180066246  mov     rax, [rsp+350h+pv]
0x18006624b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006624f  inc     rcx
0x180066252  cmp     [rax+rcx*2], r14w
0x180066257  jnz     short loc_18006624F
0x180066259  mov     qword ptr [rsp+350h+var_320], rax
0x18006625e  mov     qword ptr [rsp+350h+var_320+8], rcx
0x180066263  lea     rdx, [rsp+350h+var_320]
0x180066268  lea     rcx, [rbp+250h+lpFileName]
0x18006626c  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180066271  mov     [rsp+350h+var_330], 9
0x180066279  xor     edx, edx; Val
0x18006627b  mov     r8d, 250h; Size
0x180066281  lea     rcx, [rbp+250h+FindFileData]; void *
0x180066285  call    memset
0x18006628a  lea     rcx, [rbp+250h+lpFileName]
0x18006628e  cmp     [rbp+250h+var_2B8], 7
0x180066293  cmova   rcx, [rbp+250h+lpFileName]; lpFileName
0x180066298  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18006629c  call    cs:__imp_FindFirstFileW
0x1800662a2  mov     rbx, rax
0x1800662a5  mov     [rsp+350h+var_300], rax
0x1800662aa  dec     rax
0x1800662ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800662b1  ja      loc_18006640D
0x1800662b7  lea     rcx, [rbp+250h+lpFileName]
0x1800662bb  cmp     [rbp+250h+var_2B8], 7
0x1800662c0  cmova   rcx, [rbp+250h+lpFileName]; this
0x1800662c5  mov     rax, [rbp+250h+var_2C0]
0x1800662c9  lea     rdx, [rcx+rax*2]; wchar_t *
0x1800662cd  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800662d2  jmp     short loc_1800662E4
0x1800662d4  cmp     word ptr [rax], 5Ch ; '\'
0x1800662d8  jz      short loc_1800662E0
0x1800662da  cmp     word ptr [rax], 2Fh ; '/'
0x1800662de  jnz     short loc_1800662E9
0x1800662e0  add     rax, 2
0x1800662e4  cmp     rax, rdx
0x1800662e7  jnz     short loc_1800662D4
0x1800662e9  cmp     rax, rdx
0x1800662ec  jz      short loc_180066327
0x1800662ee  lea     r8, [rdx-2]
0x1800662f2  cmp     word ptr [r8], 5Ch ; '\'
0x1800662f7  jz      short loc_180066308
0x1800662f9  cmp     word ptr [r8], 2Fh ; '/'
0x1800662fe  jz      short loc_180066308
0x180066300  mov     rdx, r8
0x180066303  cmp     rax, r8
0x180066306  jnz     short loc_1800662EE
0x180066308  cmp     rax, rdx
0x18006630b  jz      short loc_180066327
0x18006630d  lea     r8, [rdx-2]
0x180066311  cmp     word ptr [r8], 5Ch ; '\'
0x180066316  jz      short loc_18006631F
0x180066318  cmp     word ptr [r8], 2Fh ; '/'
0x18006631d  jnz     short loc_180066327
0x18006631f  mov     rdx, r8
0x180066322  cmp     rax, r8
0x180066325  jnz     short loc_18006630D
0x180066327  mov     qword ptr [rsp+350h+var_320], rcx
0x18006632c  sub     rdx, rcx
0x18006632f  sar     rdx, 1
0x180066332  mov     qword ptr [rsp+350h+var_320+8], rdx
0x180066337  movaps  xmm0, [rsp+350h+var_320]
0x18006633c  movdqa  [rsp+350h+var_310], xmm0
0x180066342  lea     rdx, [rsp+350h+var_310]
0x180066347  lea     rcx, [rbp+250h+var_290]
0x18006634b  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180066350  mov     esi, 39h ; '9'
0x180066355  mov     [rsp+350h+var_330], esi
0x180066359  test    byte ptr [rbp+250h+FindFileData.dwFileAttributes], 10h
0x18006635d  jnz     loc_1800663EC
0x180066363  lea     rcx, [rbp+250h+FindFileData.cFileName]
0x180066367  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006636b  inc     rax
0x18006636e  cmp     [rcx+rax*2], r14w
0x180066373  jnz     short loc_18006636B
0x180066375  lea     rcx, [rbp+250h+FindFileData.cFileName]
0x180066379  mov     qword ptr [rsp+350h+var_310], rcx
0x18006637e  mov     qword ptr [rsp+350h+var_310+8], rax
0x180066383  lea     rdx, [rsp+350h+var_310]
0x180066388  lea     rcx, [rsp+350h+var_2F0]
0x18006638d  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180066392  or      esi, 2
0x180066395  mov     [rsp+350h+var_330], esi
0x180066399  lea     r8, [rsp+350h+var_2F0]; void *
0x18006639e  lea     rdx, [rbp+250h+var_290]; void *
0x1800663a2  lea     rcx, [rbp+250h+Src]; Src
0x1800663a6  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800663ab  nop
0x1800663ac  lea     rcx, [rsp+350h+var_2F0]
0x1800663b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800663b6  mov     rax, [rdi+8]
0x1800663ba  cmp     rax, [rdi+10h]
0x1800663be  jz      short loc_1800663D3
0x1800663c0  lea     rdx, [rbp+250h+Src]
0x1800663c4  mov     rcx, rax
0x1800663c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800663cc  add     qword ptr [rdi+8], 20h ; ' '
0x1800663d1  jmp     short loc_1800663E3
0x1800663d3  lea     r8, [rbp+250h+Src]
0x1800663d7  mov     rdx, rax
0x1800663da  mov     rcx, rdi
0x1800663dd  call    ??$_Emplace_reallocate@AEBVpath@filesystem@std@@@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAPEAVpath@filesystem@1@QEAV231@AEBV231@@Z; std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(std::filesystem::path * const,std::filesystem::path const &)
0x1800663e2  nop
0x1800663e3  lea     rcx, [rbp+250h+Src]
0x1800663e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800663ec  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1800663f0  mov     rcx, rbx; hFindFile
0x1800663f3  call    cs:__imp_FindNextFileW
0x1800663f9  test    eax, eax
0x1800663fb  jnz     loc_180066359
0x180066401  lea     rcx, [rbp+250h+var_290]
0x180066405  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006640a  nop
0x18006640b  jmp     short loc_180066417
0x18006640d  lea     rax, [rbx-1]
0x180066411  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180066415  ja      short loc_180066421
0x180066417  mov     rcx, rbx; hFindFile
0x18006641a  call    cs:__imp_FindClose
0x180066420  nop
0x180066421  lea     rcx, [rbp+250h+lpFileName]
0x180066425  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006642a  nop
0x18006642b  mov     rcx, [rsp+350h+pv]; pv
0x180066430  test    rcx, rcx
0x180066433  jz      short loc_18006643C
0x180066435  call    cs:__imp_CoTaskMemFree
0x18006643b  nop
0x18006643c  mov     rax, rdi
0x18006643f  mov     rcx, [rbp+250h+var_20]
0x180066446  xor     rcx, rsp; StackCookie
0x180066449  call    __security_check_cookie
0x18006644e  lea     r11, [rsp+350h+var_10]
0x180066456  mov     rbx, [r11+30h]
0x18006645a  mov     rsi, [r11+38h]
0x18006645e  mov     rsp, r11
0x180066461  pop     r14
0x180066463  pop     rdi
0x180066464  pop     rbp
0x180066465  retn
```
