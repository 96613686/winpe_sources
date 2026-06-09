# StorSvc::TreeWalker::RegistryHelper::ReadRegistry(std::list<StorSvc::TreeWalker::RegistryEntry,std::allocator<StorSvc::TreeWalker::RegistryEntry>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180048708`
- end: `0x180048a5d`
- name: `?ReadRegistry@RegistryHelper@TreeWalker@StorSvc@@CAJAEAV?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@_N@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180048a64`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180019bc4`
- `0x180019cd4`
- `0x180019d34`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x180039f6c`
- `0x180041fc8`
- `0x180048708`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048858`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004896c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048a0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048858`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004896c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180048a0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048798`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800487d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800487d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800488d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800488d8`
- `RPCRT4!RpcRevertToSelf` at `0x1800487df`
- `RPCRT4!RpcRevertToSelf` at `0x1800487df`
- `RPCRT4!RpcImpersonateClient` at `0x180048762`
- `RPCRT4!RpcImpersonateClient` at `0x180048762`

## string_xrefs

- `0x180048818`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x180048876`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x180048919`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`
- `0x18004898a`: `OneCore\Private\Drivers\inc\storageregistryhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::ReadRegistry(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 result; // rax
  const WCHAR *v7; // rax
  int v8; // ebx
  int ValueW; // eax
  DWORD i; // ebx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int phkResult; // [rsp+20h] [rbp-2D8h]
  int phkResulta; // [rsp+20h] [rbp-2D8h]
  int phkResultb; // [rsp+20h] [rbp-2D8h]
  int phkResultc; // [rsp+20h] [rbp-2D8h]
  HKEY hKey; // [rsp+40h] [rbp-2B8h] BYREF
  DWORD cchName[4]; // [rsp+48h] [rbp-2B0h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-2A0h] BYREF
  _BYTE v21[8]; // [rsp+78h] [rbp-280h] BYREF
  _BYTE v22[32]; // [rsp+80h] [rbp-278h] BYREF
  WCHAR Name; // [rsp+A0h] [rbp-258h] BYREF
  __int128 v24; // [rsp+A2h] [rbp-256h]
  _BYTE v25[22]; // [rsp+B2h] [rbp-246h] BYREF
  _BYTE pvData[528]; // [rsp+D0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  try
  {
    hKey = 0;
    Name = 0;
    v24 = 0;
    memset(v25, 0, sizeof(v25));
    if ( RpcImpersonateClient(0) )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
      result = 2147500037LL;
    }
    else
    {
      hKey = 0;
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v8 = RegOpenKeyExW(HKEY_CURRENT_USER, v7, 0, 0x20119u, &hKey);
      RpcRevertToSelf();
      if ( v8 == 2 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
        result = 0;
      }
      else
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xC7,
            (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
            (const char *)(unsigned int)v8,
            phkResult);
        ValueW = RegGetValueW(hKey, 0, L"timeStamp", 0x40u, 0, 0, 0);
        if ( ValueW > 0 )
          ValueW = (unsigned __int16)ValueW | 0x80070000;
        if ( ValueW < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xC9,
            (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
            (const char *)(unsigned int)ValueW,
            phkResulta);
        for ( i = 0; ; ++i )
        {
          cchName[2] = i;
          cchName[0] = 20;
          std::wstring::wstring(v20);
          v11 = RegEnumKeyExW(hKey, i, &Name, cchName, 0, 0, 0, 0);
          if ( v11 == 259 )
            break;
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
          if ( v11 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xE0,
              (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
              (const char *)(unsigned int)v11,
              phkResultb);
          cchName[0] = 520;
          v12 = RegGetValueW(hKey, &Name, L"path", 2u, 0, pvData, cchName);
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          if ( v12 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0xE9,
              (unsigned int)"OneCore\\Private\\Drivers\\inc\\storageregistryhelper.h",
              (const char *)(unsigned int)v12,
              phkResultc);
          v13 = std::wstring::wstring(v22, pvData);
          std::wstring::operator=(v20, v13);
          std::wstring::_Tidy_deallocate(v22);
          cchName[0] = 4;
          RegGetValueW(hKey, &Name, L"rate", 0x18u, 0, v21, cchName);
          std::list<StorSvc::TreeWalker::RegistryEntry>::_Emplace<StorSvc::TreeWalker::RegistryEntry const &>(
            a1,
            *a1,
            v20);
          SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v20);
        }
        SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v20);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&hKey);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xFB, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180048708  mov     [rsp+arg_10], rbx
0x18004870d  mov     [rsp+arg_18], rsi
0x180048712  push    rdi
0x180048713  sub     rsp, 2F0h
0x18004871a  mov     rax, cs:__security_cookie
0x180048721  xor     rax, rsp
0x180048724  mov     [rsp+2F8h+var_18], rax
0x18004872c  mov     rdi, rdx
0x18004872f  mov     rsi, rcx
0x180048732  mov     [rsp+2F8h+hKey], 0
0x18004873b  xor     eax, eax
0x18004873d  mov     [rsp+2F8h+Name], ax
0x180048745  xorps   xmm0, xmm0
0x180048748  movups  [rsp+2F8h+var_256], xmm0
0x180048750  movups  xmmword ptr [rsp+2F8h+var_246], xmm0
0x180048758  mov     qword ptr [rsp+2F8h+var_246+0Eh], rax
0x180048760  xor     ecx, ecx; BindingHandle
0x180048762  call    cs:__imp_RpcImpersonateClient
0x180048768  test    eax, eax
0x18004876a  jz      short loc_180048780
0x18004876c  lea     rcx, [rsp+2F8h+hKey]
0x180048771  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x180048776  mov     eax, 80004005h
0x18004877b  jmp     loc_180048A37
0x180048780  mov     rbx, [rsp+2F8h+hKey]
0x180048785  test    rbx, rbx
0x180048788  jz      short loc_1800487A9
0x18004878a  lea     rcx, [rsp+2F8h+cchName]; this
0x18004878f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180048794  nop
0x180048795  mov     rcx, rbx; hKey
0x180048798  call    cs:__imp_RegCloseKey
0x18004879e  nop
0x18004879f  lea     rcx, [rsp+2F8h+cchName]; this
0x1800487a4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800487a9  mov     [rsp+2F8h+hKey], 0
0x1800487b2  mov     rcx, rdi
0x1800487b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800487ba  lea     rcx, [rsp+2F8h+hKey]
0x1800487bf  mov     [rsp+2F8h+phkResult], rcx; int
0x1800487c4  mov     r9d, 20119h; samDesired
0x1800487ca  xor     r8d, r8d; ulOptions
0x1800487cd  mov     rdx, rax; lpSubKey
0x1800487d0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800487d7  call    cs:__imp_RegOpenKeyExW
0x1800487dd  mov     ebx, eax
0x1800487df  call    cs:__imp_RpcRevertToSelf
0x1800487e5  cmp     ebx, 2
0x1800487e8  jnz     short loc_1800487FB
0x1800487ea  lea     rcx, [rsp+2F8h+hKey]
0x1800487ef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800487f4  xor     eax, eax
0x1800487f6  jmp     loc_180048A37
0x1800487fb  mov     edi, 80070000h
0x180048800  test    ebx, ebx
0x180048802  jle     short loc_180048809
0x180048804  movzx   ebx, bx
0x180048807  or      ebx, edi
0x180048809  mov     rcx, [rsp+2F8h]; this
0x180048811  test    ebx, ebx
0x180048813  jns     short loc_180048829
0x180048815  mov     r9d, ebx; char *
0x180048818  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004881f  mov     edx, 0C7h; void *
0x180048824  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180048829  mov     [rsp+2F8h+pcbData], 0; pcbData
0x180048832  mov     [rsp+2F8h+pvData], 0; pvData
0x18004883b  mov     [rsp+2F8h+phkResult], 0; int
0x180048844  mov     r9d, 40h ; '@'; dwFlags
0x18004884a  lea     r8, aTimestamp; "timeStamp"
0x180048851  xor     edx, edx; lpSubKey
0x180048853  mov     rcx, [rsp+2F8h+hKey]; hkey
0x180048858  call    cs:__imp_RegGetValueW
0x18004885e  test    eax, eax
0x180048860  jle     short loc_180048867
0x180048862  movzx   eax, ax
0x180048865  or      eax, edi
0x180048867  mov     rcx, [rsp+2F8h]; this
0x18004886f  test    eax, eax
0x180048871  jns     short loc_180048887
0x180048873  mov     r9d, eax; char *
0x180048876  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x18004887d  mov     edx, 0C9h; void *
0x180048882  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180048887  xor     ebx, ebx
0x180048889  mov     [rsp+2F8h+var_2A8], ebx
0x18004888d  mov     [rsp+2F8h+cchName], 14h
0x180048895  lea     rcx, [rsp+2F8h+var_2A0]
0x18004889a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004889f  nop
0x1800488a0  mov     [rsp+2F8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800488a9  mov     [rsp+2F8h+pcbData], 0; lpcchClass
0x1800488b2  mov     [rsp+2F8h+pvData], 0; lpClass
0x1800488bb  mov     [rsp+2F8h+phkResult], 0; int
0x1800488c4  lea     r9, [rsp+2F8h+cchName]; lpcchName
0x1800488c9  lea     r8, [rsp+2F8h+Name]; lpName
0x1800488d1  mov     edx, ebx; dwIndex
0x1800488d3  mov     rcx, [rsp+2F8h+hKey]; hKey
0x1800488d8  call    cs:__imp_RegEnumKeyExW
0x1800488de  cmp     eax, 103h
0x1800488e3  jnz     short loc_180048901
0x1800488e5  lea     rcx, [rsp+2F8h+var_2A0]; this
0x1800488ea  call    ??1SYNC_ROOT_INFO@@QEAA@XZ; SYNC_ROOT_INFO::~SYNC_ROOT_INFO(void)
0x1800488ef  nop
0x1800488f0  lea     rcx, [rsp+2F8h+hKey]
0x1800488f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x1800488fa  xor     eax, eax
0x1800488fc  jmp     loc_180048A37
0x180048901  test    eax, eax
0x180048903  jle     short loc_18004890A
0x180048905  movzx   eax, ax
0x180048908  or      eax, edi
0x18004890a  mov     rcx, [rsp+2F8h]; this
0x180048912  test    eax, eax
0x180048914  jns     short loc_18004892A
0x180048916  mov     r9d, eax; char *
0x180048919  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180048920  mov     edx, 0E0h; void *
0x180048925  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004892a  mov     [rsp+2F8h+cchName], 208h
0x180048932  lea     rax, [rsp+2F8h+cchName]
0x180048937  mov     [rsp+2F8h+pcbData], rax; pcbData
0x18004893c  lea     rax, [rsp+2F8h+var_228]
0x180048944  mov     [rsp+2F8h+pvData], rax; pvData
0x180048949  mov     [rsp+2F8h+phkResult], 0; int
0x180048952  mov     r9d, 2; dwFlags
0x180048958  lea     r8, aPath; "path"
0x18004895f  lea     rdx, [rsp+2F8h+Name]; lpSubKey
0x180048967  mov     rcx, [rsp+2F8h+hKey]; hkey
0x18004896c  call    cs:__imp_RegGetValueW
0x180048972  test    eax, eax
0x180048974  jle     short loc_18004897B
0x180048976  movzx   eax, ax
0x180048979  or      eax, edi
0x18004897b  mov     rcx, [rsp+2F8h]; this
0x180048983  test    eax, eax
0x180048985  jns     short loc_18004899B
0x180048987  mov     r9d, eax; char *
0x18004898a  lea     r8, aOnecorePrivate; "OneCore\\Private\\Drivers\\inc\\storage"...
0x180048991  mov     edx, 0E9h; void *
0x180048996  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004899b  lea     rdx, [rsp+2F8h+var_228]
0x1800489a3  lea     rcx, [rsp+2F8h+var_278]
0x1800489ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800489b0  nop
0x1800489b1  mov     rdx, rax
0x1800489b4  lea     rcx, [rsp+2F8h+var_2A0]
0x1800489b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800489be  nop
0x1800489bf  lea     rcx, [rsp+2F8h+var_278]
0x1800489c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800489cc  mov     [rsp+2F8h+cchName], 4
0x1800489d4  lea     rax, [rsp+2F8h+cchName]
0x1800489d9  mov     [rsp+2F8h+pcbData], rax; pcbData
0x1800489de  lea     rax, [rsp+2F8h+var_280]
0x1800489e3  mov     [rsp+2F8h+pvData], rax; pvData
0x1800489e8  mov     [rsp+2F8h+phkResult], 0; pdwType
0x1800489f1  mov     r9d, 18h; dwFlags
0x1800489f7  lea     r8, aRate; "rate"
0x1800489fe  lea     rdx, [rsp+2F8h+Name]; lpSubKey
0x180048a06  mov     rcx, [rsp+2F8h+hKey]; hkey
0x180048a0b  call    cs:__imp_RegGetValueW
0x180048a11  lea     r8, [rsp+2F8h+var_2A0]
0x180048a16  mov     rdx, [rsi]
0x180048a19  mov     rcx, rsi
0x180048a1c  call    ??$_Emplace@AEBURegistryEntry@TreeWalker@StorSvc@@@?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@QEAAPEAU?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@1@QEAU21@AEBURegistryEntry@TreeWalker@StorSvc@@@Z; std::list<StorSvc::TreeWalker::RegistryEntry>::_Emplace<StorSvc::TreeWalker::RegistryEntry const &>(std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *> * const,StorSvc::TreeWalker::RegistryEntry const &)
0x180048a21  nop
0x180048a22  lea     rcx, [rsp+2F8h+var_2A0]; this
0x180048a27  call    ??1SYNC_ROOT_INFO@@QEAA@XZ; SYNC_ROOT_INFO::~SYNC_ROOT_INFO(void)
0x180048a2c  inc     ebx
0x180048a2e  jmp     loc_180048889
0x180048a33  mov     eax, [rsp+2F8h+cchName]
0x180048a37  mov     rcx, [rsp+2F8h+var_18]
0x180048a3f  xor     rcx, rsp; StackCookie
0x180048a42  call    __security_check_cookie
0x180048a47  lea     r11, [rsp+2F8h+var_8]
0x180048a4f  mov     rbx, [r11+20h]
0x180048a53  mov     rsi, [r11+28h]
0x180048a57  mov     rsp, r11
0x180048a5a  pop     rdi
0x180048a5b  retn
```
