# CIEBrowserModeFilter::createCacheContainer(FilePathStore::BROWSERPROFILEDATA_FILEPATHID,ushort const *,ushort const *,ushort const *)

- ea: `0x1800b494c`
- end: `0x1800b4bdc`
- name: `?createCacheContainer@CIEBrowserModeFilter@@AEAAJUBROWSERPROFILEDATA_FILEPATHID@FilePathStore@@PEBG11@Z`
- size: `656`
- prototype: `int __high(struct FilePathStore::BROWSERPROFILEDATA_FILEPATHID, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b4df4`

## callees

- `0x18008f4f8`
- `0x1800b494c`
- `0x1800b5980`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4985`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b499a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4a6a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4af2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4b0b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4b7b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4985`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b499a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4a6a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4af2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4b0b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800b4b7b`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b49d1`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x1800b49d1`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b4b29`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x1800b4b29`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b4a9a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b4a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4a29`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b4b90`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b4ba1`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b4b90`
- `WININET!DeleteUrlCacheContainerW` at `0x1800b4ba1`
- `WININET!UrlCacheCreateContainer` at `0x1800b4ac7`
- `WININET!UrlCacheCreateContainer` at `0x1800b4bbf`
- `WININET!UrlCacheCreateContainer` at `0x1800b4ac7`
- `WININET!UrlCacheCreateContainer` at `0x1800b4bbf`
- `WININET!CreateUrlCacheContainerW` at `0x1800b4a19`
- `WININET!CreateUrlCacheContainerW` at `0x1800b4a19`

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
      InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
      if ( !byte_18016AF34 )
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
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
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
0x1800b494c  push    rbx
0x1800b494e  push    rbp
0x1800b494f  push    rsi
0x1800b4950  push    rdi
0x1800b4951  push    r14
0x1800b4953  sub     rsp, 270h
0x1800b495a  mov     rax, cs:__security_cookie
0x1800b4961  xor     rax, rsp
0x1800b4964  mov     [rsp+298h+var_38], rax
0x1800b496c  mov     r14, [rsp+298h+Name]
0x1800b4974  mov     rdi, rcx
0x1800b4977  mov     ecx, 1000003Fh
0x1800b497c  mov     rbp, r9
0x1800b497f  mov     rsi, r8
0x1800b4982  mov     rbx, rdx
0x1800b4985  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b498c  nop     dword ptr [rax+rax+00h]
0x1800b4991  test    al, al
0x1800b4993  jz      short loc_1800B49C1
0x1800b4995  mov     ecx, 2000000Bh
0x1800b499a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b49a1  nop     dword ptr [rax+rax+00h]
0x1800b49a6  test    al, al
0x1800b49a8  jz      short loc_1800B49C1
0x1800b49aa  mov     r9d, 104h
0x1800b49b0  lea     r8, [rsp+298h+szCachePath]
0x1800b49b5  mov     rdx, rsi
0x1800b49b8  xor     ecx, ecx
0x1800b49ba  call    GetIEBrowserModeFilterSpartanMediumILPath
0x1800b49bf  jmp     short loc_1800B49DD
0x1800b49c1  mov     r9d, 104h
0x1800b49c7  lea     r8, [rsp+298h+szCachePath]
0x1800b49cc  xor     edx, edx
0x1800b49ce  mov     rcx, rbx
0x1800b49d1  call    cs:__imp_GetBrowserProfileDataFilePath
0x1800b49d8  nop     dword ptr [rax+rax+00h]
0x1800b49dd  mov     ebx, eax
0x1800b49df  test    eax, eax
0x1800b49e1  js      short loc_1800B4A44
0x1800b49e3  cmp     dword ptr [rdi+38h], 0
0x1800b49e7  jz      short loc_1800B4A65
0x1800b49e9  mov     [rsp+298h+cbBuffer], 0; cbBuffer
0x1800b49f2  lea     r8, [rsp+298h+szCachePath]; lpszCachePath
0x1800b49f7  mov     [rsp+298h+pvBuffer], 0; pvBuffer
0x1800b4a00  xor     r9d, r9d; KBCacheLimit
0x1800b4a03  mov     [rsp+298h+dwOptions], 9; dwOptions
0x1800b4a0b  mov     rdx, rbp; lpCachePrefix
0x1800b4a0e  mov     rcx, rsi; Name
0x1800b4a11  mov     [rsp+298h+dwContainerType], 0; dwContainerType
0x1800b4a19  call    cs:__imp_CreateUrlCacheContainerW
0x1800b4a20  nop     dword ptr [rax+rax+00h]
0x1800b4a25  test    eax, eax
0x1800b4a27  jnz     short loc_1800B4A44
0x1800b4a29  call    cs:__imp_GetLastError
0x1800b4a30  nop     dword ptr [rax+rax+00h]
0x1800b4a35  mov     ebx, eax
0x1800b4a37  test    eax, eax
0x1800b4a39  jle     short loc_1800B4A44
0x1800b4a3b  movzx   ebx, ax
0x1800b4a3e  or      ebx, 80070000h
0x1800b4a44  mov     eax, ebx
0x1800b4a46  mov     rcx, [rsp+298h+var_38]
0x1800b4a4e  xor     rcx, rsp; StackCookie
0x1800b4a51  call    __security_check_cookie
0x1800b4a56  add     rsp, 270h
0x1800b4a5d  pop     r14
0x1800b4a5f  pop     rdi
0x1800b4a60  pop     rsi
0x1800b4a61  pop     rbp
0x1800b4a62  pop     rbx
0x1800b4a63  retn
0x1800b4a65  mov     ecx, 1000003Fh
0x1800b4a6a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b4a71  nop     dword ptr [rax+rax+00h]
0x1800b4a76  test    al, al
0x1800b4a78  jz      short loc_1800B4A81
0x1800b4a7a  mov     edi, 109h
0x1800b4a7f  jmp     short loc_1800B4AB5
0x1800b4a81  xor     r9d, r9d; Context
0x1800b4a84  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800b4a8b  xor     r8d, r8d; Parameter
0x1800b4a8e  lea     rcx, stru_18016BB00; InitOnce
0x1800b4a95  mov     edi, 9
0x1800b4a9a  call    cs:__imp_InitOnceExecuteOnce
0x1800b4aa1  nop     dword ptr [rax+rax+00h]
0x1800b4aa6  cmp     cs:byte_18016AF34, 0
0x1800b4aad  mov     eax, 309h
0x1800b4ab2  cmovz   edi, eax
0x1800b4ab5  xor     r9d, r9d; ullLimit
0x1800b4ab8  mov     [rsp+298h+dwContainerType], edi; dwOptions
0x1800b4abc  lea     r8, [rsp+298h+szCachePath]; pwszDirectory
0x1800b4ac1  mov     rdx, rbp; pwszPrefix
0x1800b4ac4  mov     rcx, rsi; pwszName
0x1800b4ac7  call    cs:__imp_UrlCacheCreateContainer
0x1800b4ace  nop     dword ptr [rax+rax+00h]
0x1800b4ad3  mov     ebx, eax
0x1800b4ad5  test    eax, eax
0x1800b4ad7  jz      loc_1800B4BD5
0x1800b4add  cmp     eax, 0B7h
0x1800b4ae2  jz      short loc_1800B4AED
0x1800b4ae4  cmp     eax, 5
0x1800b4ae7  jnz     loc_1800B4A37
0x1800b4aed  mov     ecx, 1000003Fh
0x1800b4af2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b4af9  nop     dword ptr [rax+rax+00h]
0x1800b4afe  test    al, al
0x1800b4b00  jz      loc_1800B4B9C
0x1800b4b06  mov     ecx, 20000001h
0x1800b4b0b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b4b12  nop     dword ptr [rax+rax+00h]
0x1800b4b17  test    al, al
0x1800b4b19  jz      short loc_1800B4B76
0x1800b4b1b  lea     rcx, [rsp+298h+var_258]
0x1800b4b20  mov     [rsp+298h+var_258], 0
0x1800b4b29  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x1800b4b30  nop     dword ptr [rax+rax+00h]
0x1800b4b35  test    eax, eax
0x1800b4b37  js      short loc_1800B4B6C
0x1800b4b39  mov     rcx, [rsp+298h+var_258]
0x1800b4b3e  lea     r9, pszFormat
0x1800b4b45  mov     dword ptr [rsp+298h+pvBuffer], 0
0x1800b4b4d  mov     r8, rbp
0x1800b4b50  mov     [rsp+298h+dwOptions], edi
0x1800b4b54  mov     rdx, rsi
0x1800b4b57  mov     qword ptr [rsp+298h+dwContainerType], 0
0x1800b4b60  mov     rax, [rcx]
0x1800b4b63  mov     rax, [rax+78h]
0x1800b4b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4b6c  lea     rcx, [rsp+298h+var_258]
0x1800b4b71  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b4b76  mov     ecx, 20000003h
0x1800b4b7b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800b4b82  nop     dword ptr [rax+rax+00h]
0x1800b4b87  test    al, al
0x1800b4b89  jz      short loc_1800B4B9C
0x1800b4b8b  xor     edx, edx; dwOptions
0x1800b4b8d  mov     rcx, r14; Name
0x1800b4b90  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b4b97  nop     dword ptr [rax+rax+00h]
0x1800b4b9c  xor     edx, edx; dwOptions
0x1800b4b9e  mov     rcx, rsi; Name
0x1800b4ba1  call    cs:__imp_DeleteUrlCacheContainerW
0x1800b4ba8  nop     dword ptr [rax+rax+00h]
0x1800b4bad  xor     r9d, r9d; ullLimit
0x1800b4bb0  mov     [rsp+298h+dwContainerType], edi; dwOptions
0x1800b4bb4  lea     r8, [rsp+298h+szCachePath]; pwszDirectory
0x1800b4bb9  mov     rdx, rbp; pwszPrefix
0x1800b4bbc  mov     rcx, rsi; pwszName
0x1800b4bbf  call    cs:__imp_UrlCacheCreateContainer
0x1800b4bc6  nop     dword ptr [rax+rax+00h]
0x1800b4bcb  mov     ebx, eax
0x1800b4bcd  test    eax, eax
0x1800b4bcf  jnz     loc_1800B4A39
0x1800b4bd5  xor     ebx, ebx
0x1800b4bd7  jmp     loc_1800B4A44
```
