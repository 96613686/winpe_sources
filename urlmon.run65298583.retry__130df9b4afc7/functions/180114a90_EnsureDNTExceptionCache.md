# EnsureDNTExceptionCache

- ea: `0x180114a90`
- end: `0x180114c94`
- name: `EnsureDNTExceptionCache`
- size: `516`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180114880`
- `0x180114ca0`
- `0x180114eb0`

## callees

- `0x180114118`
- `0x180114a90`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114b71`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114b84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114c0a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114b71`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114b84`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180114c0a`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180114ad3`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180114ad3`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x180114b9c`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x180114b9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180114af5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180114af5`
- `WININET!DeleteUrlCacheContainerW` at `0x180114c19`
- `WININET!DeleteUrlCacheContainerW` at `0x180114c2c`
- `WININET!DeleteUrlCacheContainerW` at `0x180114c19`
- `WININET!DeleteUrlCacheContainerW` at `0x180114c2c`
- `WININET!UrlCacheCreateContainer` at `0x180114b43`
- `WININET!UrlCacheCreateContainer` at `0x180114c5b`
- `WININET!UrlCacheCreateContainer` at `0x180114b43`
- `WININET!UrlCacheCreateContainer` at `0x180114c5b`

## pseudocode

```c
signed int EnsureDNTExceptionCache()
{
  signed int result; // eax
  DWORD dwOptions; // esi
  const WCHAR *v2; // rbx
  const WCHAR *v3; // rax
  void (__fastcall *v4)(struct IBrowserBrokerFactory *, __int64, __int64, const OLECHAR *, __int64, DWORD, _DWORD); // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  const WCHAR *v7; // rax
  const WCHAR *v8; // rbx
  const WCHAR *v9; // rax
  bool v10; // cc
  struct IBrowserBrokerFactory *v11; // [rsp+40h] [rbp-258h] BYREF
  WCHAR pwszDirectory[264]; // [rsp+50h] [rbp-248h] BYREF

  result = 0;
  if ( !dword_18015EBC8 )
  {
    result = GetBrowserProfileDataFilePath(
               FilePathStore::BROWSERPROFILEDATA_FILEPATH_DNTException,
               0,
               pwszDirectory,
               260);
    if ( result >= 0 )
    {
      InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
      dwOptions = byte_18015DE34 == 0 ? 0x300 : 0;
      v2 = (const WCHAR *)DNTCacheContainerString((wchar_t *)L"DNTException:");
      v3 = (const WCHAR *)DNTCacheContainerString((wchar_t *)L"DNTException");
      result = UrlCacheCreateContainer(v3, v2, pwszDirectory, 0x400u, dwOptions);
      if ( !result )
      {
        dword_18015EBC8 = 1;
        return 0;
      }
      if ( result == 183 || result == 5 )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
        {
          if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
          {
            v11 = 0;
            if ( (int)GetBrowserBrokerInterface(&v11) >= 0 )
            {
              v4 = *(void (__fastcall **)(struct IBrowserBrokerFactory *, __int64, __int64, const OLECHAR *, __int64, DWORD, _DWORD))(*(_QWORD *)v11 + 120LL);
              v5 = DNTCacheContainerString((wchar_t *)L"DNTException:");
              v6 = DNTCacheContainerString((wchar_t *)L"DNTException");
              v4(v11, v6, v5, &pszFormat, 1024, dwOptions, 0);
              (*(void (__fastcall **)(struct IBrowserBrokerFactory *))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
            DeleteUrlCacheContainerW(L"DNTException", 0);
        }
        v7 = (const WCHAR *)DNTCacheContainerString((wchar_t *)L"DNTException");
        DeleteUrlCacheContainerW(v7, 0);
        v8 = (const WCHAR *)DNTCacheContainerString((wchar_t *)L"DNTException:");
        v9 = (const WCHAR *)DNTCacheContainerString((wchar_t *)L"DNTException");
        result = UrlCacheCreateContainer(v9, v8, pwszDirectory, 0x400u, dwOptions);
        v10 = result <= 0;
        if ( !result )
          return 0;
      }
      else
      {
        v10 = result <= 0;
      }
      if ( !v10 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180114a90  push    rbx
0x180114a92  push    rsi
0x180114a93  push    rdi
0x180114a94  push    r12
0x180114a96  push    r14
0x180114a98  sub     rsp, 270h
0x180114a9f  mov     rax, cs:__security_cookie
0x180114aa6  xor     rax, rsp
0x180114aa9  mov     [rsp+298h+var_38], rax
0x180114ab1  xor     eax, eax
0x180114ab3  cmp     cs:dword_18015EBC8, eax
0x180114ab9  jnz     loc_180114C75
0x180114abf  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_DNTException@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_DNTException
0x180114ac6  lea     r8, [rsp+298h+pwszDirectory]
0x180114acb  mov     r9d, 104h
0x180114ad1  xor     edx, edx
0x180114ad3  call    cs:__imp_GetBrowserProfileDataFilePath
0x180114ad9  test    eax, eax
0x180114adb  js      loc_180114C75
0x180114ae1  xor     r9d, r9d; Context
0x180114ae4  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180114aeb  xor     r8d, r8d; Parameter
0x180114aee  lea     rcx, stru_18015EA38; InitOnce
0x180114af5  call    cs:__imp_InitOnceExecuteOnce
0x180114afb  mov     al, cs:byte_18015DE34
0x180114b01  lea     rcx, aDntexception_0; "DNTException:"
0x180114b08  neg     al
0x180114b0a  sbb     esi, esi
0x180114b0c  not     esi
0x180114b0e  and     esi, 300h
0x180114b14  call    DNTCacheContainerString
0x180114b19  lea     r14, aDntexception; "DNTException"
0x180114b20  mov     rbx, rax
0x180114b23  mov     rcx, r14; Source
0x180114b26  call    DNTCacheContainerString
0x180114b2b  mov     r12d, 400h
0x180114b31  mov     [rsp+298h+dwOptions], esi; dwOptions
0x180114b35  mov     r9d, r12d; ullLimit
0x180114b38  lea     r8, [rsp+298h+pwszDirectory]; pwszDirectory
0x180114b3d  mov     rdx, rbx; pwszPrefix
0x180114b40  mov     rcx, rax; pwszName
0x180114b43  call    cs:__imp_UrlCacheCreateContainer
0x180114b49  test    eax, eax
0x180114b4b  jnz     short loc_180114B5C
0x180114b4d  mov     cs:dword_18015EBC8, 1
0x180114b57  jmp     loc_180114C65
0x180114b5c  cmp     eax, 0B7h
0x180114b61  jz      short loc_180114B6C
0x180114b63  cmp     eax, 5
0x180114b66  jnz     loc_180114C69
0x180114b6c  mov     ecx, 1000003Fh
0x180114b71  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180114b77  test    al, al
0x180114b79  jz      loc_180114C1F
0x180114b7f  mov     ecx, 20000001h
0x180114b84  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180114b8a  test    al, al
0x180114b8c  jz      short loc_180114C05
0x180114b8e  lea     rcx, [rsp+298h+var_258]
0x180114b93  mov     [rsp+298h+var_258], 0
0x180114b9c  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x180114ba2  test    eax, eax
0x180114ba4  js      short loc_180114C05
0x180114ba6  mov     rax, [rsp+298h+var_258]
0x180114bab  mov     rcx, [rax]
0x180114bae  mov     rdi, [rcx+78h]
0x180114bb2  lea     rcx, aDntexception_0; "DNTException:"
0x180114bb9  call    DNTCacheContainerString
0x180114bbe  mov     rcx, r14; Source
0x180114bc1  mov     rbx, rax
0x180114bc4  call    DNTCacheContainerString
0x180114bc9  mov     rcx, [rsp+298h+var_258]
0x180114bce  lea     r9, pszFormat
0x180114bd5  mov     rdx, rax
0x180114bd8  mov     [rsp+298h+var_268], 0
0x180114be0  mov     rax, rdi
0x180114be3  mov     [rsp+298h+var_270], esi
0x180114be7  mov     r8, rbx
0x180114bea  mov     qword ptr [rsp+298h+dwOptions], r12
0x180114bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114bf4  mov     rcx, [rsp+298h+var_258]
0x180114bf9  mov     rax, [rcx]
0x180114bfc  mov     rax, [rax+10h]
0x180114c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114c05  mov     ecx, 20000003h
0x180114c0a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180114c10  test    al, al
0x180114c12  jz      short loc_180114C1F
0x180114c14  xor     edx, edx; dwOptions
0x180114c16  mov     rcx, r14; Name
0x180114c19  call    cs:__imp_DeleteUrlCacheContainerW
0x180114c1f  mov     rcx, r14; Source
0x180114c22  call    DNTCacheContainerString
0x180114c27  mov     rcx, rax; Name
0x180114c2a  xor     edx, edx; dwOptions
0x180114c2c  call    cs:__imp_DeleteUrlCacheContainerW
0x180114c32  lea     rcx, aDntexception_0; "DNTException:"
0x180114c39  call    DNTCacheContainerString
0x180114c3e  mov     rcx, r14; Source
0x180114c41  mov     rbx, rax
0x180114c44  call    DNTCacheContainerString
0x180114c49  mov     r9, r12; ullLimit
0x180114c4c  mov     [rsp+298h+dwOptions], esi; dwOptions
0x180114c50  lea     r8, [rsp+298h+pwszDirectory]; pwszDirectory
0x180114c55  mov     rdx, rbx; pwszPrefix
0x180114c58  mov     rcx, rax; pwszName
0x180114c5b  call    cs:__imp_UrlCacheCreateContainer
0x180114c61  test    eax, eax
0x180114c63  jnz     short loc_180114C6B
0x180114c65  xor     eax, eax
0x180114c67  jmp     short loc_180114C75
0x180114c69  test    eax, eax
0x180114c6b  jle     short loc_180114C75
0x180114c6d  movzx   eax, ax
0x180114c70  or      eax, 80070000h
0x180114c75  mov     rcx, [rsp+298h+var_38]
0x180114c7d  xor     rcx, rsp; StackCookie
0x180114c80  call    __security_check_cookie
0x180114c85  add     rsp, 270h
0x180114c8c  pop     r14
0x180114c8e  pop     r12
0x180114c90  pop     rdi
0x180114c91  pop     rsi
0x180114c92  pop     rbx
0x180114c93  retn
```
