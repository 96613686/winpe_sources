# EnsureDNTExceptionCache

- ea: `0x180120e70`
- end: `0x1801210b1`
- name: `EnsureDNTExceptionCache`
- size: `577`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180120c50`
- `0x1801210c0`
- `0x1801212e0`

## callees

- `0x180120480`
- `0x180120e70`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180120f63`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180120f7c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18012100e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180120f63`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180120f7c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18012100e`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180120eb3`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180120eb3`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x180120f9a`
- `iertutil!__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z` at `0x180120f9a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180120edb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180120edb`
- `WININET!DeleteUrlCacheContainerW` at `0x180121023`
- `WININET!DeleteUrlCacheContainerW` at `0x18012103c`
- `WININET!DeleteUrlCacheContainerW` at `0x180121023`
- `WININET!DeleteUrlCacheContainerW` at `0x18012103c`
- `WININET!UrlCacheCreateContainer` at `0x180120f2f`
- `WININET!UrlCacheCreateContainer` at `0x180121071`
- `WININET!UrlCacheCreateContainer` at `0x180120f2f`
- `WININET!UrlCacheCreateContainer` at `0x180121071`

## pseudocode

```c
signed int EnsureDNTExceptionCache()
{
  signed int result; // eax
  DWORD dwOptions; // esi
  wchar_t *v2; // rbx
  wchar_t *v3; // rax
  void (__fastcall *v4)(struct IBrowserBrokerFactory *, wchar_t *, wchar_t *, const OLECHAR *, __int64, DWORD, _DWORD); // rdi
  wchar_t *v5; // rbx
  wchar_t *v6; // rax
  wchar_t *v7; // rax
  wchar_t *v8; // rbx
  wchar_t *v9; // rax
  bool v10; // cc
  struct IBrowserBrokerFactory *v11; // [rsp+40h] [rbp-258h] BYREF
  WCHAR pwszDirectory[264]; // [rsp+50h] [rbp-248h] BYREF

  result = 0;
  if ( !dword_18016BC90 )
  {
    result = GetBrowserProfileDataFilePath(
               FilePathStore::BROWSERPROFILEDATA_FILEPATH_DNTException,
               0,
               pwszDirectory,
               260);
    if ( result >= 0 )
    {
      InitOnceExecuteOnce(&stru_18016BB00, InitOnceDeviceFamily, 0, 0);
      dwOptions = byte_18016AF34 == 0 ? 0x300 : 0;
      v2 = DNTCacheContainerString((wchar_t *)L"DNTException:");
      v3 = DNTCacheContainerString((wchar_t *)L"DNTException");
      result = UrlCacheCreateContainer(v3, v2, pwszDirectory, 0x400u, dwOptions);
      if ( !result )
      {
        dword_18016BC90 = 1;
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
              v4 = *(void (__fastcall **)(struct IBrowserBrokerFactory *, wchar_t *, wchar_t *, const OLECHAR *, __int64, DWORD, _DWORD))(*(_QWORD *)v11 + 120LL);
              v5 = DNTCacheContainerString((wchar_t *)L"DNTException:");
              v6 = DNTCacheContainerString((wchar_t *)L"DNTException");
              v4(v11, v6, v5, &pszFormat, 1024, dwOptions, 0);
              (*(void (__fastcall **)(struct IBrowserBrokerFactory *))(*(_QWORD *)v11 + 16LL))(v11);
            }
          }
          if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
            DeleteUrlCacheContainerW(L"DNTException", 0);
        }
        v7 = DNTCacheContainerString((wchar_t *)L"DNTException");
        DeleteUrlCacheContainerW(v7, 0);
        v8 = DNTCacheContainerString((wchar_t *)L"DNTException:");
        v9 = DNTCacheContainerString((wchar_t *)L"DNTException");
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
0x180120e70  push    rbx
0x180120e72  push    rsi
0x180120e73  push    rdi
0x180120e74  push    r12
0x180120e76  push    r14
0x180120e78  sub     rsp, 270h
0x180120e7f  mov     rax, cs:__security_cookie
0x180120e86  xor     rax, rsp
0x180120e89  mov     [rsp+298h+var_38], rax
0x180120e91  xor     eax, eax
0x180120e93  cmp     cs:dword_18016BC90, eax
0x180120e99  jnz     loc_180121091
0x180120e9f  mov     rcx, cs:?BROWSERPROFILEDATA_FILEPATH_DNTException@FilePathStore@@3UBROWSERPROFILEDATA_FILEPATHID@1@B; FilePathStore::BROWSERPROFILEDATA_FILEPATHID const FilePathStore::BROWSERPROFILEDATA_FILEPATH_DNTException
0x180120ea6  lea     r8, [rsp+298h+pwszDirectory]
0x180120eab  mov     r9d, 104h
0x180120eb1  xor     edx, edx
0x180120eb3  call    cs:__imp_GetBrowserProfileDataFilePath
0x180120eba  nop     dword ptr [rax+rax+00h]
0x180120ebf  test    eax, eax
0x180120ec1  js      loc_180121091
0x180120ec7  xor     r9d, r9d; Context
0x180120eca  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180120ed1  xor     r8d, r8d; Parameter
0x180120ed4  lea     rcx, stru_18016BB00; InitOnce
0x180120edb  call    cs:__imp_InitOnceExecuteOnce
0x180120ee2  nop     dword ptr [rax+rax+00h]
0x180120ee7  mov     al, cs:byte_18016AF34
0x180120eed  lea     rcx, aDntexception_0; "DNTException:"
0x180120ef4  neg     al
0x180120ef6  sbb     esi, esi
0x180120ef8  not     esi
0x180120efa  and     esi, 300h
0x180120f00  call    DNTCacheContainerString
0x180120f05  lea     r14, aDntexception; "DNTException"
0x180120f0c  mov     rbx, rax
0x180120f0f  mov     rcx, r14; Source
0x180120f12  call    DNTCacheContainerString
0x180120f17  mov     r12d, 400h
0x180120f1d  mov     [rsp+298h+dwOptions], esi; dwOptions
0x180120f21  mov     r9d, r12d; ullLimit
0x180120f24  lea     r8, [rsp+298h+pwszDirectory]; pwszDirectory
0x180120f29  mov     rdx, rbx; pwszPrefix
0x180120f2c  mov     rcx, rax; pwszName
0x180120f2f  call    cs:__imp_UrlCacheCreateContainer
0x180120f36  nop     dword ptr [rax+rax+00h]
0x180120f3b  test    eax, eax
0x180120f3d  jnz     short loc_180120F4E
0x180120f3f  mov     cs:dword_18016BC90, 1
0x180120f49  jmp     loc_180121081
0x180120f4e  cmp     eax, 0B7h
0x180120f53  jz      short loc_180120F5E
0x180120f55  cmp     eax, 5
0x180120f58  jnz     loc_180121085
0x180120f5e  mov     ecx, 1000003Fh
0x180120f63  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180120f6a  nop     dword ptr [rax+rax+00h]
0x180120f6f  test    al, al
0x180120f71  jz      loc_18012102F
0x180120f77  mov     ecx, 20000001h
0x180120f7c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180120f83  nop     dword ptr [rax+rax+00h]
0x180120f88  test    al, al
0x180120f8a  jz      short loc_180121009
0x180120f8c  lea     rcx, [rsp+298h+var_258]
0x180120f91  mov     [rsp+298h+var_258], 0
0x180120f9a  call    cs:__imp_?GetBrowserBrokerInterface@@YAJPEAPEAUIBrowserBrokerFactory@@@Z; GetBrowserBrokerInterface(IBrowserBrokerFactory * *)
0x180120fa1  nop     dword ptr [rax+rax+00h]
0x180120fa6  test    eax, eax
0x180120fa8  js      short loc_180121009
0x180120faa  mov     rax, [rsp+298h+var_258]
0x180120faf  mov     rcx, [rax]
0x180120fb2  mov     rdi, [rcx+78h]
0x180120fb6  lea     rcx, aDntexception_0; "DNTException:"
0x180120fbd  call    DNTCacheContainerString
0x180120fc2  mov     rcx, r14; Source
0x180120fc5  mov     rbx, rax
0x180120fc8  call    DNTCacheContainerString
0x180120fcd  mov     rcx, [rsp+298h+var_258]
0x180120fd2  lea     r9, pszFormat
0x180120fd9  mov     rdx, rax
0x180120fdc  mov     [rsp+298h+var_268], 0
0x180120fe4  mov     rax, rdi
0x180120fe7  mov     [rsp+298h+var_270], esi
0x180120feb  mov     r8, rbx
0x180120fee  mov     qword ptr [rsp+298h+dwOptions], r12
0x180120ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120ff8  mov     rcx, [rsp+298h+var_258]
0x180120ffd  mov     rax, [rcx]
0x180121000  mov     rax, [rax+10h]
0x180121004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121009  mov     ecx, 20000003h
0x18012100e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180121015  nop     dword ptr [rax+rax+00h]
0x18012101a  test    al, al
0x18012101c  jz      short loc_18012102F
0x18012101e  xor     edx, edx; dwOptions
0x180121020  mov     rcx, r14; Name
0x180121023  call    cs:__imp_DeleteUrlCacheContainerW
0x18012102a  nop     dword ptr [rax+rax+00h]
0x18012102f  mov     rcx, r14; Source
0x180121032  call    DNTCacheContainerString
0x180121037  mov     rcx, rax; Name
0x18012103a  xor     edx, edx; dwOptions
0x18012103c  call    cs:__imp_DeleteUrlCacheContainerW
0x180121043  nop     dword ptr [rax+rax+00h]
0x180121048  lea     rcx, aDntexception_0; "DNTException:"
0x18012104f  call    DNTCacheContainerString
0x180121054  mov     rcx, r14; Source
0x180121057  mov     rbx, rax
0x18012105a  call    DNTCacheContainerString
0x18012105f  mov     r9, r12; ullLimit
0x180121062  mov     [rsp+298h+dwOptions], esi; dwOptions
0x180121066  lea     r8, [rsp+298h+pwszDirectory]; pwszDirectory
0x18012106b  mov     rdx, rbx; pwszPrefix
0x18012106e  mov     rcx, rax; pwszName
0x180121071  call    cs:__imp_UrlCacheCreateContainer
0x180121078  nop     dword ptr [rax+rax+00h]
0x18012107d  test    eax, eax
0x18012107f  jnz     short loc_180121087
0x180121081  xor     eax, eax
0x180121083  jmp     short loc_180121091
0x180121085  test    eax, eax
0x180121087  jle     short loc_180121091
0x180121089  movzx   eax, ax
0x18012108c  or      eax, 80070000h
0x180121091  mov     rcx, [rsp+298h+var_38]
0x180121099  xor     rcx, rsp; StackCookie
0x18012109c  call    __security_check_cookie
0x1801210a1  add     rsp, 270h
0x1801210a8  pop     r14
0x1801210aa  pop     r12
0x1801210ac  pop     rdi
0x1801210ad  pop     rsi
0x1801210ae  pop     rbx
0x1801210af  retn
```
