# CIEEnterpriseModeFilter::_s_InitializeCacheContainer(SCacheContainerMetaData const *)

- ea: `0x1800b9d24`
- end: `0x1800b9f85`
- name: `?_s_InitializeCacheContainer@CIEEnterpriseModeFilter@@CAJPEBUSCacheContainerMetaData@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(const struct SCacheContainerMetaData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b841c`

## callees

- `0x180014500`
- `0x180023130`
- `0x18008f4f8`
- `0x1800b5980`
- `0x1800b9d24`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9d60`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9d78`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e0b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e9d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9f02`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9d60`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9d78`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e0b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9e9d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b9f02`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800b9dd3`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x1800b9dd3`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b9db0`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b9db0`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b9eb7`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b9eb7`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800b9dbe`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800b9dbe`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b9f18`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b9f29`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b9f18`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b9f29`
- `WININET!UrlCacheCreateContainer` at `0x1800b9e50`
- `WININET!UrlCacheCreateContainer` at `0x1800b9f47`
- `WININET!UrlCacheCreateContainer` at `0x1800b9e50`
- `WININET!UrlCacheCreateContainer` at `0x1800b9f47`

## pseudocode

```c
__int64 __fastcall CIEEnterpriseModeFilter::_s_InitializeCacheContainer(const struct SCacheContainerMetaData *a1)
{
  unsigned int IEBrowserModeFilterSpartanMediumILPath; // eax
  unsigned int BrowserProfileDataFilePath; // ebx
  const unsigned __int16 *String; // rax
  DWORD dwOptions; // ebp
  wchar_t *v6; // rsi
  wchar_t *v7; // r14
  signed int Container; // eax
  signed int v9; // eax
  struct IBrowserBrokerFactory *v11[2]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR pwszDirectory[264]; // [rsp+50h] [rbp-258h] BYREF

  memset_0(pwszDirectory, 0, 0x208u);
  if ( (unsigned __int8)IEConfiguration_GetBool(268435519) && (unsigned __int8)IEConfiguration_GetBool(536870923) )
  {
    IEBrowserModeFilterSpartanMediumILPath = GetIEBrowserModeFilterSpartanMediumILPath(
                                               0,
                                               *((_QWORD *)a1 + 1),
                                               pwszDirectory,
                                               260);
LABEL_8:
    BrowserProfileDataFilePath = IEBrowserModeFilterSpartanMediumILPath;
    goto LABEL_9;
  }
  BrowserProfileDataFilePath = GetBrowserProfileDataFilePath(*(_QWORD *)a1, 0, pwszDirectory, 260);
  if ( IsDualEngineProcess() )
  {
    String = (const unsigned __int16 *)IEConfiguration_GetString(268435540);
    if ( String )
    {
      if ( *String )
      {
        IEBrowserModeFilterSpartanMediumILPath = StringCchCatW(pwszDirectory, 0x104u, String);
        goto LABEL_8;
      }
    }
  }
LABEL_9:
  if ( !BrowserProfileDataFilePath )
  {
    dwOptions = (((unsigned __int8)IEConfiguration_GetBool(268435519) ^ 1) << 9) + 256;
    v6 = EMIECacheContainerString(*((wchar_t **)a1 + 1));
    v7 = EMIECacheContainerString(*((wchar_t **)a1 + 2));
    Container = UrlCacheCreateContainer(v6, v7, pwszDirectory, 0, dwOptions);
    BrowserProfileDataFilePath = Container;
    if ( Container > 0 )
      BrowserProfileDataFilePath = (unsigned __int16)Container | 0x80070000;
    if ( BrowserProfileDataFilePath == -2147024713 || BrowserProfileDataFilePath == -2147024891 )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        {
          v11[0] = 0;
          if ( (int)GetBrowserBrokerInterface(v11) >= 0 )
            (*(void (__fastcall **)(struct IBrowserBrokerFactory *, wchar_t *, wchar_t *, const OLECHAR *, _QWORD, DWORD, _DWORD))(*(_QWORD *)v11[0] + 120LL))(
              v11[0],
              v6,
              v7,
              &pszFormat,
              0,
              dwOptions,
              0);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11);
        }
        if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
          DeleteUrlCacheContainerW(*((LPCWSTR *)a1 + 1), 0);
      }
      DeleteUrlCacheContainerW(v6, 0);
      v9 = UrlCacheCreateContainer(v6, v7, pwszDirectory, 0, dwOptions);
      BrowserProfileDataFilePath = v9;
      if ( v9 > 0 )
        return (unsigned __int16)v9 | 0x80070000;
    }
  }
  return BrowserProfileDataFilePath;
}

```

## disassembly

```asm
0x1800b9d24  push    rbx
0x1800b9d26  push    rbp
0x1800b9d27  push    rsi
0x1800b9d28  push    rdi
0x1800b9d29  push    r14
0x1800b9d2b  push    r15
0x1800b9d2d  sub     rsp, 278h
0x1800b9d34  mov     rax, cs:__security_cookie
0x1800b9d3b  xor     rax, rsp
0x1800b9d3e  mov     [rsp+2A8h+var_48], rax
0x1800b9d46  mov     rdi, rcx
0x1800b9d49  xor     edx, edx; Val
0x1800b9d4b  lea     rcx, [rsp+2A8h+pwszDirectory]; void *
0x1800b9d50  mov     r8d, 208h; Size
0x1800b9d56  call    memset_0
0x1800b9d5b  mov     ecx, 1000003Fh
0x1800b9d60  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9d67  nop     dword ptr [rax+rax+00h]
0x1800b9d6c  xor     r15d, r15d
0x1800b9d6f  test    al, al
0x1800b9d71  jz      short loc_1800B9DA0
0x1800b9d73  mov     ecx, 2000000Bh
0x1800b9d78  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9d7f  nop     dword ptr [rax+rax+00h]
0x1800b9d84  test    al, al
0x1800b9d86  jz      short loc_1800B9DA0
0x1800b9d88  mov     rdx, [rdi+8]
0x1800b9d8c  lea     r8, [rsp+2A8h+pwszDirectory]
0x1800b9d91  mov     r9d, 104h
0x1800b9d97  xor     ecx, ecx
0x1800b9d99  call    GetIEBrowserModeFilterSpartanMediumILPath
0x1800b9d9e  jmp     short loc_1800B9DFC
0x1800b9da0  mov     rcx, [rdi]
0x1800b9da3  lea     r8, [rsp+2A8h+pwszDirectory]
0x1800b9da8  mov     r9d, 104h
0x1800b9dae  xor     edx, edx
0x1800b9db0  call    cs:__imp_GetBrowserProfileDataFilePath
0x1800b9db7  nop     dword ptr [rax+rax+00h]
0x1800b9dbc  mov     ebx, eax
0x1800b9dbe  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1800b9dc5  nop     dword ptr [rax+rax+00h]
0x1800b9dca  test    al, al
0x1800b9dcc  jz      short loc_1800B9DFE
0x1800b9dce  mov     ecx, 10000054h
0x1800b9dd3  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800b9dda  nop     dword ptr [rax+rax+00h]
0x1800b9ddf  test    rax, rax
0x1800b9de2  jz      short loc_1800B9DFE
0x1800b9de4  cmp     [rax], r15w
0x1800b9de8  jz      short loc_1800B9DFE
0x1800b9dea  mov     r8, rax; unsigned __int16 *
0x1800b9ded  lea     rcx, [rsp+2A8h+pwszDirectory]; unsigned __int16 *
0x1800b9df2  mov     edx, 104h; unsigned __int64
0x1800b9df7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b9dfc  mov     ebx, eax
0x1800b9dfe  test    ebx, ebx
0x1800b9e00  jnz     loc_1800B9F62
0x1800b9e06  mov     ecx, 1000003Fh
0x1800b9e0b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9e12  nop     dword ptr [rax+rax+00h]
0x1800b9e17  mov     rcx, [rdi+8]
0x1800b9e1b  movzx   ebp, al
0x1800b9e1e  xor     ebp, 1
0x1800b9e21  shl     ebp, 9
0x1800b9e24  add     ebp, 100h
0x1800b9e2a  call    EMIECacheContainerString
0x1800b9e2f  mov     rcx, [rdi+10h]
0x1800b9e33  mov     rsi, rax
0x1800b9e36  call    EMIECacheContainerString
0x1800b9e3b  xor     r9d, r9d; ullLimit
0x1800b9e3e  mov     [rsp+2A8h+dwOptions], ebp; dwOptions
0x1800b9e42  lea     r8, [rsp+2A8h+pwszDirectory]; pwszDirectory
0x1800b9e47  mov     rdx, rax; pwszPrefix
0x1800b9e4a  mov     rcx, rsi; pwszName
0x1800b9e4d  mov     r14, rax
0x1800b9e50  call    cs:__imp_UrlCacheCreateContainer
0x1800b9e57  nop     dword ptr [rax+rax+00h]
0x1800b9e5c  mov     ebx, eax
0x1800b9e5e  test    eax, eax
0x1800b9e60  jle     short loc_1800B9E6B
0x1800b9e62  movzx   ebx, ax
0x1800b9e65  or      ebx, 80070000h
0x1800b9e6b  cmp     ebx, 800700B7h
0x1800b9e71  jz      short loc_1800B9E7F
0x1800b9e73  cmp     ebx, 80070005h
0x1800b9e79  jnz     loc_1800B9F62
0x1800b9e7f  mov     ecx, 1000003Fh
0x1800b9e84  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9e8b  nop     dword ptr [rax+rax+00h]
0x1800b9e90  test    al, al
0x1800b9e92  jz      loc_1800B9F24
0x1800b9e98  mov     ecx, 20000001h
0x1800b9e9d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9ea4  nop     dword ptr [rax+rax+00h]
0x1800b9ea9  test    al, al
0x1800b9eab  jz      short loc_1800B9EFD
0x1800b9ead  lea     rcx, [rsp+2A8h+var_268]
0x1800b9eb2  mov     [rsp+2A8h+var_268], r15
0x1800b9eb7  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x1800b9ebe  nop     dword ptr [rax+rax+00h]
0x1800b9ec3  test    eax, eax
0x1800b9ec5  js      short loc_1800B9EF3
0x1800b9ec7  mov     rcx, [rsp+2A8h+var_268]
0x1800b9ecc  lea     r9, pszFormat
0x1800b9ed3  mov     [rsp+2A8h+var_278], r15d
0x1800b9ed8  mov     r8, r14
0x1800b9edb  mov     [rsp+2A8h+var_280], ebp
0x1800b9edf  mov     rdx, rsi
0x1800b9ee2  mov     qword ptr [rsp+2A8h+dwOptions], r15
0x1800b9ee7  mov     rax, [rcx]
0x1800b9eea  mov     rax, [rax+78h]
0x1800b9eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ef3  lea     rcx, [rsp+2A8h+var_268]
0x1800b9ef8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b9efd  mov     ecx, 20000003h
0x1800b9f02  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b9f09  nop     dword ptr [rax+rax+00h]
0x1800b9f0e  test    al, al
0x1800b9f10  jz      short loc_1800B9F24
0x1800b9f12  mov     rcx, [rdi+8]; Name
0x1800b9f16  xor     edx, edx; dwOptions
0x1800b9f18  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b9f1f  nop     dword ptr [rax+rax+00h]
0x1800b9f24  xor     edx, edx; dwOptions
0x1800b9f26  mov     rcx, rsi; Name
0x1800b9f29  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b9f30  nop     dword ptr [rax+rax+00h]
0x1800b9f35  xor     r9d, r9d; ullLimit
0x1800b9f38  mov     [rsp+2A8h+dwOptions], ebp; dwOptions
0x1800b9f3c  lea     r8, [rsp+2A8h+pwszDirectory]; pwszDirectory
0x1800b9f41  mov     rdx, r14; pwszPrefix
0x1800b9f44  mov     rcx, rsi; pwszName
0x1800b9f47  call    cs:__imp_UrlCacheCreateContainer
0x1800b9f4e  nop     dword ptr [rax+rax+00h]
0x1800b9f53  mov     ebx, eax
0x1800b9f55  test    eax, eax
0x1800b9f57  jle     short loc_1800B9F62
0x1800b9f59  movzx   ebx, ax
0x1800b9f5c  or      ebx, 80070000h
0x1800b9f62  mov     eax, ebx
0x1800b9f64  mov     rcx, [rsp+2A8h+var_48]
0x1800b9f6c  xor     rcx, rsp; StackCookie
0x1800b9f6f  call    __security_check_cookie
0x1800b9f74  add     rsp, 278h
0x1800b9f7b  pop     r15
0x1800b9f7d  pop     r14
0x1800b9f7f  pop     rdi
0x1800b9f80  pop     rsi
0x1800b9f81  pop     rbp
0x1800b9f82  pop     rbx
0x1800b9f83  retn
```
