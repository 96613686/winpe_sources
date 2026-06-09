# CIEBrowserModeFilter::createCacheContainer(FilePathStore::BROWSERPROFILEDATA_FILEPATHID,ushort const *,ushort const *,ushort const *)

- ea: `0x1800ad604`
- end: `0x1800ad835`
- name: `?createCacheContainer@CIEBrowserModeFilter@@AEAAJUBROWSERPROFILEDATA_FILEPATHID@FilePathStore@@PEBG11@Z`
- size: `561`
- prototype: `int __high(struct FilePathStore::BROWSERPROFILEDATA_FILEPATHID, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ada48`

## callees

- `0x18008a620`
- `0x1800ad604`
- `0x1800ae500`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad63d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad64c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad703`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad779`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad788`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad7ec`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad63d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad64c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad703`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad779`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad788`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800ad7ec`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800ad67d`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800ad67d`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800ad7a0`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800ad7a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ad72d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800ad72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad6c9`
- `WININET!DeleteUrlCacheContainerW` at `0x1800ad7fb`
- `WININET!DeleteUrlCacheContainerW` at `0x1800ad806`
- `WININET!DeleteUrlCacheContainerW` at `0x1800ad7fb`
- `WININET!DeleteUrlCacheContainerW` at `0x1800ad806`
- `WININET!UrlCacheCreateContainer` at `0x1800ad754`
- `WININET!UrlCacheCreateContainer` at `0x1800ad81e`
- `WININET!UrlCacheCreateContainer` at `0x1800ad754`
- `WININET!UrlCacheCreateContainer` at `0x1800ad81e`
- `WININET!CreateUrlCacheContainerW` at `0x1800ad6bf`
- `WININET!CreateUrlCacheContainerW` at `0x1800ad6bf`

## pseudocode

```c
__int64 __fastcall CIEBrowserModeFilter::createCacheContainer(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *Name)
{
  int IEBrowserModeFilterSpartanMediumILPath; // eax
  unsigned int v10; // ebx
  signed int LastError; // eax
  bool v12; // cc
  DWORD v14; // edi
  struct IBrowserBrokerFactory *v15[2]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR szCachePath[264]; // [rsp+50h] [rbp-248h] BYREF

  if ( (unsigned __int8)IEConfiguration_GetBool(268435519) && (unsigned __int8)IEConfiguration_GetBool(536870923) )
    IEBrowserModeFilterSpartanMediumILPath = GetIEBrowserModeFilterSpartanMediumILPath(0, a3, szCachePath, 260);
  else
    IEBrowserModeFilterSpartanMediumILPath = GetBrowserProfileDataFilePath(a2, 0, szCachePath, 260);
  v10 = IEBrowserModeFilterSpartanMediumILPath;
  if ( IEBrowserModeFilterSpartanMediumILPath >= 0 )
  {
    if ( *(_DWORD *)(a1 + 56) )
    {
      if ( CreateUrlCacheContainerW(a3, a4, szCachePath, 0, 0, 9u, 0, 0) )
        return v10;
      LastError = GetLastError();
      v10 = LastError;
      goto LABEL_9;
    }
    if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
    {
      v14 = 265;
    }
    else
    {
      v14 = 9;
      InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
      if ( !byte_18015DE34 )
        v14 = 777;
    }
    LastError = UrlCacheCreateContainer(a3, a4, szCachePath, 0, v14);
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError != 183 && LastError != 5 )
      {
LABEL_9:
        v12 = LastError <= 0;
LABEL_10:
        if ( !v12 )
          return (unsigned __int16)LastError | 0x80070000;
        return v10;
      }
      if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        {
          v15[0] = 0;
          if ( (int)GetBrowserBrokerInterface(v15) >= 0 )
            (*(void (__fastcall **)(struct IBrowserBrokerFactory *, const WCHAR *, const WCHAR *, const OLECHAR *, _QWORD, DWORD, _DWORD))(*(_QWORD *)v15[0] + 120LL))(
              v15[0],
              a3,
              a4,
              &pszFormat,
              0,
              v14,
              0);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v15);
        }
        if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
          DeleteUrlCacheContainerW(Name, 0);
      }
      DeleteUrlCacheContainerW(a3, 0);
      LastError = UrlCacheCreateContainer(a3, a4, szCachePath, 0, v14);
      v10 = LastError;
      v12 = LastError <= 0;
      if ( LastError )
        goto LABEL_10;
    }
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x1800ad604  push    rbx
0x1800ad606  push    rbp
0x1800ad607  push    rsi
0x1800ad608  push    rdi
0x1800ad609  push    r14
0x1800ad60b  sub     rsp, 270h
0x1800ad612  mov     rax, cs:__security_cookie
0x1800ad619  xor     rax, rsp
0x1800ad61c  mov     [rsp+298h+var_38], rax
0x1800ad624  mov     r14, [rsp+298h+Name]
0x1800ad62c  mov     rdi, rcx
0x1800ad62f  mov     ecx, 1000003Fh
0x1800ad634  mov     rbp, r9
0x1800ad637  mov     rsi, r8
0x1800ad63a  mov     rbx, rdx
0x1800ad63d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad643  test    al, al
0x1800ad645  jz      short loc_1800AD66D
0x1800ad647  mov     ecx, 2000000Bh
0x1800ad64c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad652  test    al, al
0x1800ad654  jz      short loc_1800AD66D
0x1800ad656  mov     r9d, 104h
0x1800ad65c  lea     r8, [rsp+298h+szCachePath]
0x1800ad661  mov     rdx, rsi
0x1800ad664  xor     ecx, ecx
0x1800ad666  call    GetIEBrowserModeFilterSpartanMediumILPath
0x1800ad66b  jmp     short loc_1800AD683
0x1800ad66d  mov     r9d, 104h
0x1800ad673  lea     r8, [rsp+298h+szCachePath]
0x1800ad678  xor     edx, edx
0x1800ad67a  mov     rcx, rbx
0x1800ad67d  call    cs:__imp_GetBrowserProfileDataFilePath
0x1800ad683  mov     ebx, eax
0x1800ad685  test    eax, eax
0x1800ad687  js      short loc_1800AD6DE
0x1800ad689  cmp     dword ptr [rdi+38h], 0
0x1800ad68d  jz      short loc_1800AD6FE
0x1800ad68f  mov     [rsp+298h+cbBuffer], 0; cbBuffer
0x1800ad698  lea     r8, [rsp+298h+szCachePath]; lpszCachePath
0x1800ad69d  mov     [rsp+298h+pvBuffer], 0; pvBuffer
0x1800ad6a6  xor     r9d, r9d; KBCacheLimit
0x1800ad6a9  mov     [rsp+298h+dwOptions], 9; dwOptions
0x1800ad6b1  mov     rdx, rbp; lpCachePrefix
0x1800ad6b4  mov     rcx, rsi; Name
0x1800ad6b7  mov     [rsp+298h+dwContainerType], 0; dwContainerType
0x1800ad6bf  call    cs:__imp_CreateUrlCacheContainerW
0x1800ad6c5  test    eax, eax
0x1800ad6c7  jnz     short loc_1800AD6DE
0x1800ad6c9  call    cs:__imp_GetLastError
0x1800ad6cf  mov     ebx, eax
0x1800ad6d1  test    eax, eax
0x1800ad6d3  jle     short loc_1800AD6DE
0x1800ad6d5  movzx   ebx, ax
0x1800ad6d8  or      ebx, 80070000h
0x1800ad6de  mov     eax, ebx
0x1800ad6e0  mov     rcx, [rsp+298h+var_38]
0x1800ad6e8  xor     rcx, rsp; StackCookie
0x1800ad6eb  call    __security_check_cookie
0x1800ad6f0  add     rsp, 270h
0x1800ad6f7  pop     r14
0x1800ad6f9  pop     rdi
0x1800ad6fa  pop     rsi
0x1800ad6fb  pop     rbp
0x1800ad6fc  pop     rbx
0x1800ad6fd  retn
0x1800ad6fe  mov     ecx, 1000003Fh
0x1800ad703  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad709  test    al, al
0x1800ad70b  jz      short loc_1800AD714
0x1800ad70d  mov     edi, 109h
0x1800ad712  jmp     short loc_1800AD742
0x1800ad714  xor     r9d, r9d; Context
0x1800ad717  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800ad71e  xor     r8d, r8d; Parameter
0x1800ad721  lea     rcx, stru_18015EA38; InitOnce
0x1800ad728  mov     edi, 9
0x1800ad72d  call    cs:__imp_InitOnceExecuteOnce
0x1800ad733  cmp     cs:byte_18015DE34, 0
0x1800ad73a  mov     eax, 309h
0x1800ad73f  cmovz   edi, eax
0x1800ad742  xor     r9d, r9d; ullLimit
0x1800ad745  mov     [rsp+298h+dwContainerType], edi; dwOptions
0x1800ad749  lea     r8, [rsp+298h+szCachePath]; pwszDirectory
0x1800ad74e  mov     rdx, rbp; pwszPrefix
0x1800ad751  mov     rcx, rsi; pwszName
0x1800ad754  call    cs:__imp_UrlCacheCreateContainer
0x1800ad75a  mov     ebx, eax
0x1800ad75c  test    eax, eax
0x1800ad75e  jz      loc_1800AD82E
0x1800ad764  cmp     eax, 0B7h
0x1800ad769  jz      short loc_1800AD774
0x1800ad76b  cmp     eax, 5
0x1800ad76e  jnz     loc_1800AD6D1
0x1800ad774  mov     ecx, 1000003Fh
0x1800ad779  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad77f  test    al, al
0x1800ad781  jz      short loc_1800AD801
0x1800ad783  mov     ecx, 20000001h
0x1800ad788  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad78e  test    al, al
0x1800ad790  jz      short loc_1800AD7E7
0x1800ad792  lea     rcx, [rsp+298h+var_258]
0x1800ad797  mov     [rsp+298h+var_258], 0
0x1800ad7a0  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x1800ad7a6  test    eax, eax
0x1800ad7a8  js      short loc_1800AD7DD
0x1800ad7aa  mov     rcx, [rsp+298h+var_258]
0x1800ad7af  lea     r9, pszFormat
0x1800ad7b6  mov     dword ptr [rsp+298h+pvBuffer], 0
0x1800ad7be  mov     r8, rbp
0x1800ad7c1  mov     [rsp+298h+dwOptions], edi
0x1800ad7c5  mov     rdx, rsi
0x1800ad7c8  mov     qword ptr [rsp+298h+dwContainerType], 0
0x1800ad7d1  mov     rax, [rcx]
0x1800ad7d4  mov     rax, [rax+78h]
0x1800ad7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7dd  lea     rcx, [rsp+298h+var_258]
0x1800ad7e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800ad7e7  mov     ecx, 20000003h
0x1800ad7ec  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800ad7f2  test    al, al
0x1800ad7f4  jz      short loc_1800AD801
0x1800ad7f6  xor     edx, edx; dwOptions
0x1800ad7f8  mov     rcx, r14; Name
0x1800ad7fb  call    cs:__imp_DeleteUrlCacheContainerW
0x1800ad801  xor     edx, edx; dwOptions
0x1800ad803  mov     rcx, rsi; Name
0x1800ad806  call    cs:__imp_DeleteUrlCacheContainerW
0x1800ad80c  xor     r9d, r9d; ullLimit
0x1800ad80f  mov     [rsp+298h+dwContainerType], edi; dwOptions
0x1800ad813  lea     r8, [rsp+298h+szCachePath]; pwszDirectory
0x1800ad818  mov     rdx, rbp; pwszPrefix
0x1800ad81b  mov     rcx, rsi; pwszName
0x1800ad81e  call    cs:__imp_UrlCacheCreateContainer
0x1800ad824  mov     ebx, eax
0x1800ad826  test    eax, eax
0x1800ad828  jnz     loc_1800AD6D3
0x1800ad82e  xor     ebx, ebx
0x1800ad830  jmp     loc_1800AD6DE
```
