# CommandImpl::GetExternalCommandFunction(wchar_t const *,char const *)

- ea: `0x18000892c`
- end: `0x180008b86`
- name: `?GetExternalCommandFunction@CommandImpl@@CA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AJPEB_W@Z@std@@PEB_WPEBD@Z`
- size: `602`
- prototype: `HMODULE *__fastcall(HMODULE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180008f30`

## callees

- `0x18000892c`
- `0x180009224`
- `0x18000b44c`
- `0x18000c188`
- `0x18000c1f0`
- `0x18000c2d0`
- `0x18000c2e0`
- `0x18000d3b4`
- `0x18000d5ac`
- `0x18000d9fc`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008aa4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008aa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b3f`

## string_xrefs

- `0x180008a52`: `updiag.dll`
- `0x180008b00`: `ProcessAnalyzeCommand`
- `0x180008aef`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`
- `0x180008b73`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`

## pseudocode

```c
HMODULE *__fastcall CommandImpl::GetExternalCommandFunction(HMODULE *a1)
{
  __int64 v2; // r8
  const wchar_t *v3; // r8
  std::filesystem *v4; // rcx
  const wchar_t *i; // rax
  const wchar_t *v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // r11
  const wchar_t *v9; // r8
  unsigned __int64 v10; // rdx
  std::filesystem **v11; // rax
  const WCHAR *v12; // rcx
  HMODULE Library; // rax
  HMODULE v14; // rdi
  LPCWSTR *v15; // rdx
  FARPROC ProcAddress; // rax
  const char *v17; // r9
  unsigned int ErrorCode; // eax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rax
  std::filesystem *v23[2]; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-88h]
  unsigned __int64 v25; // [rsp+48h] [rbp-80h]
  HMODULE v26; // [rsp+50h] [rbp-78h]
  __int128 v27; // [rsp+60h] [rbp-68h] BYREF
  __int64 v28; // [rsp+70h] [rbp-58h]
  __int64 v29; // [rsp+78h] [rbp-50h]
  const wil::ResultException *v30; // [rsp+80h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[3]; // [rsp+90h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  pv = 0;
  try
  {
    wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>();
    v2 = -1;
    do
      ++v2;
    while ( *((_WORD *)pv + v2) );
    *(_OWORD *)v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v23, pv);
    v4 = (std::filesystem *)v23;
    if ( v25 > 7 )
      v4 = v23[0];
    for ( i = std::filesystem::_Find_root_name_end(v4, (const wchar_t *const)v4 + v24, v3);
          i != v6 && (*i == 92 || *i == 47);
          ++i )
    {
      ;
    }
    if ( i != v6 )
    {
      do
      {
        v9 = v6 - 1;
        if ( *(v6 - 1) == 92 )
          break;
        if ( *v9 == 47 )
          break;
        --v6;
      }
      while ( i != v9 );
    }
    v10 = ((__int64)v6 - v7) >> 1;
    if ( v8 < v10 )
      std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
    v24 = v10;
    v11 = v23;
    if ( v25 > 7 )
      v11 = (std::filesystem **)v23[0];
    *((_WORD *)v11 + v10) = 0;
    std::wstring::wstring(lpLibFileName, v23);
    std::wstring::~wstring(v23);
    v27 = 0;
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v27, L"updiag.dll");
    std::filesystem::path::operator/=(lpLibFileName, &v27);
    std::wstring::~wstring(&v27);
    v12 = (const WCHAR *)lpLibFileName;
    if ( v33 > 7 )
      v12 = lpLibFileName[0];
    Library = LoadLibraryExW(v12, 0, 0x88u);
    v14 = Library;
    v26 = Library;
    v15 = lpLibFileName;
    if ( v33 > 7 )
      v15 = (LPCWSTR *)lpLibFileName[0];
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x9C,
      (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
      (const char *)(Library == 0),
      "Error loading library %ws",
      (const char *)v15);
    ProcAddress = GetProcAddress(v14, "ProcessAnalyzeCommand");
    if ( !ProcAddress )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x9F,
        (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
        v17);
    *a1 = v14;
    a1[1] = (HMODULE)ProcAddress;
    std::wstring::~wstring(lpLibFileName);
    if ( pv )
      CoTaskMemFree(pv);
  }
  catch ( const wil::ResultException *v30 )
  {
    ErrorCode = wil::ResultException::GetErrorCode(v30);
    LOBYTE(v20) = 1;
    CommandImpl::GetMessageW(&pv, ErrorCode, v20);
    if ( wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::get(&pv) )
    {
      v21 = wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::get(&pv);
      v22 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(&std::wcerr, v21);
      std::wostream::operator<<(v22);
    }
    throw;
  }
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>();
}

```

## disassembly

```asm
0x18000892c  mov     r11, rsp
0x18000892f  mov     [r11+10h], rbx
0x180008933  mov     [r11+18h], rsi
0x180008937  push    rdi
0x180008938  sub     rsp, 0C0h
0x18000893f  mov     rax, cs:__security_cookie
0x180008946  xor     rax, rsp
0x180008949  mov     [rsp+0C8h+var_18], rax
0x180008951  mov     rbx, rcx
0x180008954  mov     [rsp+0C8h+pv], rcx
0x18000895c  xor     esi, esi
0x18000895e  mov     [r11-40h], rsi
0x180008962  lea     rcx, [r11-40h]
0x180008966  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18000896b  nop
0x18000896c  mov     rdx, [rsp+0C8h+pv]
0x180008974  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008978  inc     r8
0x18000897b  cmp     [rdx+r8*2], si
0x180008980  jnz     short loc_180008978
0x180008982  xorps   xmm0, xmm0
0x180008985  movups  xmmword ptr [rsp+0C8h+var_98], xmm0
0x18000898a  mov     [rsp+0C8h+var_88], rsi
0x18000898f  mov     [rsp+0C8h+var_80], rsi
0x180008994  lea     rcx, [rsp+0C8h+var_98]
0x180008999  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000899e  nop
0x18000899f  lea     rcx, [rsp+0C8h+var_98]
0x1800089a4  cmp     [rsp+0C8h+var_80], 7
0x1800089aa  cmova   rcx, [rsp+0C8h+var_98]; this
0x1800089b0  mov     r11, [rsp+0C8h+var_88]
0x1800089b5  lea     rdx, [rcx+r11*2]; wchar_t *
0x1800089b9  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x1800089be  jmp     short loc_1800089D0
0x1800089c0  cmp     word ptr [rax], 5Ch ; '\'
0x1800089c4  jz      short loc_1800089CC
0x1800089c6  cmp     word ptr [rax], 2Fh ; '/'
0x1800089ca  jnz     short loc_1800089D5
0x1800089cc  add     rax, 2
0x1800089d0  cmp     rax, rdx
0x1800089d3  jnz     short loc_1800089C0
0x1800089d5  cmp     rax, rdx
0x1800089d8  jz      short loc_1800089F4
0x1800089da  lea     r8, [rdx-2]
0x1800089de  cmp     word ptr [r8], 5Ch ; '\'
0x1800089e3  jz      short loc_1800089F4
0x1800089e5  cmp     word ptr [r8], 2Fh ; '/'
0x1800089ea  jz      short loc_1800089F4
0x1800089ec  mov     rdx, r8
0x1800089ef  cmp     rax, r8
0x1800089f2  jnz     short loc_1800089DA
0x1800089f4  sub     rdx, rcx
0x1800089f7  sar     rdx, 1
0x1800089fa  cmp     r11, rdx
0x1800089fd  jb      loc_180008B6D
0x180008a03  mov     [rsp+0C8h+var_88], rdx
0x180008a08  lea     rax, [rsp+0C8h+var_98]
0x180008a0d  cmp     [rsp+0C8h+var_80], 7
0x180008a13  cmova   rax, [rsp+0C8h+var_98]
0x180008a19  mov     [rax+rdx*2], si
0x180008a1d  lea     rdx, [rsp+0C8h+var_98]
0x180008a22  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180008a2a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180008a2f  nop
0x180008a30  lea     rcx, [rsp+0C8h+var_98]
0x180008a35  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a3a  xorps   xmm0, xmm0
0x180008a3d  movups  [rsp+0C8h+var_68], xmm0
0x180008a42  mov     [rsp+0C8h+var_58], rsi
0x180008a47  mov     [rsp+0C8h+var_50], rsi
0x180008a4c  mov     r8d, 0Ah
0x180008a52  lea     rdx, aUpdiagDll; "updiag.dll"
0x180008a59  lea     rcx, [rsp+0C8h+var_68]
0x180008a5e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008a63  nop
0x180008a64  lea     rdx, [rsp+0C8h+var_68]; void *
0x180008a69  lea     rcx, [rsp+0C8h+lpLibFileName]; Src
0x180008a71  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180008a76  nop
0x180008a77  lea     rcx, [rsp+0C8h+var_68]
0x180008a7c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a81  nop
0x180008a82  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180008a8a  cmp     [rsp+0C8h+var_20], 7
0x180008a93  cmova   rcx, [rsp+0C8h+lpLibFileName]; lpLibFileName
0x180008a9c  xor     edx, edx; hFile
0x180008a9e  mov     r8d, 88h; dwFlags
0x180008aa4  call    cs:__imp_LoadLibraryExW
0x180008aaa  mov     rdi, rax
0x180008aad  mov     [rsp+0C8h+var_78], rax
0x180008ab2  lea     rdx, [rsp+0C8h+lpLibFileName]
0x180008aba  cmp     [rsp+0C8h+var_20], 7
0x180008ac3  cmova   rdx, [rsp+0C8h+lpLibFileName]
0x180008acc  test    rax, rax
0x180008acf  setz    al
0x180008ad2  mov     rcx, [rsp+0C8h]; this
0x180008ada  mov     [rsp+0C8h+var_A0], rdx; char *
0x180008adf  lea     rdx, aErrorLoadingLi; "Error loading library %ws"
0x180008ae6  mov     [rsp+0C8h+var_A8], rdx; void *
0x180008aeb  movzx   r9d, al; char *
0x180008aef  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180008af6  mov     edx, 9Ch; void *
0x180008afb  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180008b00  lea     rdx, aProcessanalyze; "ProcessAnalyzeCommand"
0x180008b07  mov     rcx, rdi; hModule
0x180008b0a  call    cs:__imp_GetProcAddress
0x180008b10  mov     rcx, [rsp+0C8h]; this
0x180008b18  test    rax, rax
0x180008b1b  jz      short loc_180008B73
0x180008b1d  mov     [rbx], rdi
0x180008b20  mov     [rbx+8], rax
0x180008b24  lea     rcx, [rsp+0C8h+lpLibFileName]
0x180008b2c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b31  nop
0x180008b32  mov     rcx, [rsp+0C8h+pv]; pv
0x180008b3a  test    rcx, rcx
0x180008b3d  jz      short loc_180008B45
0x180008b3f  call    cs:__imp_CoTaskMemFree
0x180008b45  mov     rax, rbx
0x180008b48  mov     rcx, [rsp+0C8h+var_18]
0x180008b50  xor     rcx, rsp; StackCookie
0x180008b53  call    __security_check_cookie
0x180008b58  lea     r11, [rsp+0C8h+var_8]
0x180008b60  mov     rbx, [r11+18h]
0x180008b64  mov     rsi, [r11+20h]
0x180008b68  mov     rsp, r11
0x180008b6b  pop     rdi
0x180008b6c  retn
0x180008b6d  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
0x180008b73  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180008b7a  mov     edx, 9Fh; void *
0x180008b7f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
