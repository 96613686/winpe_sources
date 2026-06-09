# winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::LoadExtensions(winrt::hstring const &)

- ea: `0x1800b8c74`
- end: `0x1800b900d`
- name: `?LoadExtensions@ExtensionCache@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEAA?AV?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@AEBUhstring@6@@Z`
- size: `921`
- prototype: `__int64 __fastcall(__int64, __int64, winrt::hstring *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b73bc`

## callees

- `0x180025348`
- `0x180028978`
- `0x1800483f4`
- `0x18006996c`
- `0x18006def0`
- `0x1800b8c74`
- `0x1800e488c`
- `0x18015cb00`
- `0x18015d868`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtension_FindByUserAndName` at `0x1800b8ce3`
- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtension_FindByUserAndName` at `0x1800b8ce3`
- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtensionIterator_GetNext` at `0x1800b8d34`
- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtensionIterator_GetNext` at `0x1800b8d34`
- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtensionIterator_Close` at `0x1800b8d7c`
- `ext-ms-onecore-appmodel-staterepository-appextension-l1-1-0!SRAppExtensionIterator_Close` at `0x1800b8d7c`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtensionIterator_GetNext` at `0x1800b8e14`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtensionIterator_GetNext` at `0x1800b8e14`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtension_FindByUserAndName` at `0x1800b8db6`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtension_FindByUserAndName` at `0x1800b8db6`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtensionIterator_Close` at `0x1800b8e58`
- `ext-ms-onecore-appmodel-staterepository-pkgextension-l1-1-0!SRPkgExtensionIterator_Close` at `0x1800b8e58`

## string_xrefs

- `0x1800b8d56`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b8e36`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b8fb4`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b8fc9`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b8fde`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`
- `0x1800b8ffb`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\ExtensionCache_impl.h`

## pseudocode

```c
__int64 __fastcall winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionCache::LoadExtensions(
        __int64 a1,
        __int64 a2,
        winrt::hstring *a3)
{
  winrt::hstring *v3; // r14
  __int64 v4; // rdi
  const wchar_t *v5; // rax
  int v6; // eax
  char v7; // si
  int Next; // eax
  int v9; // eax
  const wchar_t *v10; // rax
  int v11; // eax
  char v12; // si
  int v13; // eax
  int v14; // eax
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 v18; // rdx
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-F8h]
  _BYTE v23[8]; // [rsp+38h] [rbp-E0h] BYREF
  std::_Ref_count_base *v24; // [rsp+40h] [rbp-D8h]
  __int64 v25; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+50h] [rbp-C8h] BYREF
  _QWORD v27[6]; // [rsp+60h] [rbp-B8h] BYREF
  int v28; // [rsp+90h] [rbp-88h]
  int v29; // [rsp+94h] [rbp-84h]
  __int64 v30; // [rsp+98h] [rbp-80h]
  _DWORD v31[4]; // [rsp+A0h] [rbp-78h] BYREF
  _QWORD v32[7]; // [rsp+B0h] [rbp-68h] BYREF
  int v33; // [rsp+E8h] [rbp-30h]
  int v34; // [rsp+ECh] [rbp-2Ch]
  __int64 v35; // [rsp+F0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v25 = 0;
  v5 = winrt::hstring::c_str(a3);
  v6 = SRAppExtension_FindByUserAndName(0, v5, &v25);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v6,
      v20);
  v7 = 0;
  LOBYTE(v20) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      memset_0(v32, 0, 0x48u);
      v31[0] = 0;
      Next = SRAppExtensionIterator_GetNext(v25, v32, v31);
      if ( Next >= 0 )
        break;
      if ( !v7 )
      {
        v7 = 1;
        LOBYTE(v20) = 1;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x755,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          (const char *)(unsigned int)Next,
          v20);
      }
    }
    if ( !v31[0] )
      break;
    try
    {
      v18 = std::make_shared<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo,winrt::hstring const &,SRAppExtensionData &>(
              v23,
              v3,
              v32);
      std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::push_back(
        v4,
        v18);
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x767,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        v19);
      v7 = v20;
      v4 = a2;
      v3 = a3;
      continue;
    }
  }
  v9 = SRAppExtensionIterator_Close(v25);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x769,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v9,
      v20);
  v25 = 0;
  v26 = 0;
  v10 = winrt::hstring::c_str(v3);
  v11 = SRPkgExtension_FindByUserAndName(0, v10, &v26);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x76C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v11,
      v20);
  v12 = 0;
  LOBYTE(v20) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      memset_0(v27, 0, 0x40u);
      memset_0(v32, 0, 0x48u);
      v31[0] = 0;
      v13 = SRPkgExtensionIterator_GetNext(v26, v27, v31);
      if ( v13 >= 0 )
        break;
      if ( !v12 )
      {
        v12 = 1;
        LOBYTE(v20) = 1;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x77A,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
          (const char *)(unsigned int)v13,
          v20);
      }
    }
    if ( !v31[0] )
      break;
    try
    {
      v32[0] = v27[0];
      v32[1] = 0;
      v32[2] = v27[1];
      v32[3] = v27[2];
      v32[4] = v27[3];
      v32[5] = v27[4];
      v32[6] = v27[5];
      v33 = v28;
      v34 = v29;
      v35 = v30;
      v16 = std::make_shared<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo,winrt::hstring const &,SRAppExtensionData &>(
              v23,
              v3,
              v32);
      std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::push_back(
        v4,
        v16);
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x798,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
        v17);
      v12 = v20;
      v4 = a2;
      v3 = a3;
      continue;
    }
  }
  v14 = SRPkgExtensionIterator_Close(v26);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79A,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\ExtensionCache_impl.h",
      (const char *)(unsigned int)v14,
      v20);
  return v4;
}

```

## disassembly

```asm
0x1800b8c74  mov     [rsp+arg_0], rsi
0x1800b8c79  mov     [rsp+arg_18], rdi
0x1800b8c7e  push    r14
0x1800b8c80  sub     rsp, 110h
0x1800b8c87  mov     rax, cs:__security_cookie
0x1800b8c8e  xor     rax, rsp
0x1800b8c91  mov     [rsp+118h+var_18], rax
0x1800b8c99  mov     r14, r8
0x1800b8c9c  mov     rdi, rdx
0x1800b8c9f  mov     [rsp+118h+var_F0], rdx
0x1800b8ca4  mov     [rsp+118h+var_E8], r8
0x1800b8ca9  mov     [rsp+118h+var_F4], 0
0x1800b8cb1  xorps   xmm0, xmm0
0x1800b8cb4  xor     eax, eax
0x1800b8cb6  movups  xmmword ptr [rdx], xmm0
0x1800b8cb9  mov     [rdx], rax
0x1800b8cbc  mov     [rdx+8], rax
0x1800b8cc0  mov     [rdx+10h], rax
0x1800b8cc4  mov     [rsp+118h+var_F4], 1
0x1800b8ccc  mov     [rsp+118h+var_D0], rax
0x1800b8cd1  mov     rcx, r8; this
0x1800b8cd4  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b8cd9  mov     rdx, rax
0x1800b8cdc  lea     r8, [rsp+118h+var_D0]
0x1800b8ce1  xor     ecx, ecx
0x1800b8ce3  call    cs:__imp_SRAppExtension_FindByUserAndName
0x1800b8ce9  mov     rcx, [rsp+118h]; this
0x1800b8cf1  test    eax, eax
0x1800b8cf3  js      loc_1800B8FB1
0x1800b8cf9  xor     sil, sil
0x1800b8cfc  mov     byte ptr [rsp+118h+var_F8], sil; int
0x1800b8d01  xor     edx, edx; Val
0x1800b8d03  lea     r8d, [rdx+48h]; Size
0x1800b8d07  lea     rcx, [rsp+118h+var_68]; void *
0x1800b8d0f  call    memset_0
0x1800b8d14  mov     [rsp+118h+var_78], 0
0x1800b8d1f  lea     r8, [rsp+118h+var_78]
0x1800b8d27  lea     rdx, [rsp+118h+var_68]
0x1800b8d2f  mov     rcx, [rsp+118h+var_D0]
0x1800b8d34  call    cs:__imp_SRAppExtensionIterator_GetNext
0x1800b8d3a  test    eax, eax
0x1800b8d3c  jns     short loc_1800B8D69
0x1800b8d3e  test    sil, sil
0x1800b8d41  jnz     short loc_1800B8D01
0x1800b8d43  mov     sil, 1
0x1800b8d46  mov     byte ptr [rsp+118h+var_F8], sil; int
0x1800b8d4b  mov     rcx, [rsp+118h]; this
0x1800b8d53  mov     r9d, eax; char *
0x1800b8d56  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b8d5d  mov     edx, 755h; void *
0x1800b8d62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b8d67  jmp     short loc_1800B8D01
0x1800b8d69  cmp     [rsp+118h+var_78], 0
0x1800b8d71  jnz     loc_1800B8F66
0x1800b8d77  mov     rcx, [rsp+118h+var_D0]
0x1800b8d7c  call    cs:__imp_SRAppExtensionIterator_Close
0x1800b8d82  mov     rcx, [rsp+118h]; this
0x1800b8d8a  test    eax, eax
0x1800b8d8c  js      loc_1800B8FC6
0x1800b8d92  mov     [rsp+118h+var_D0], 0
0x1800b8d9b  mov     [rsp+118h+var_C8], 0
0x1800b8da4  mov     rcx, r14; this
0x1800b8da7  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800b8dac  mov     rdx, rax
0x1800b8daf  lea     r8, [rsp+118h+var_C8]
0x1800b8db4  xor     ecx, ecx
0x1800b8db6  call    cs:__imp_SRPkgExtension_FindByUserAndName
0x1800b8dbc  mov     rcx, [rsp+118h]; this
0x1800b8dc4  test    eax, eax
0x1800b8dc6  js      loc_1800B8FDB
0x1800b8dcc  xor     sil, sil
0x1800b8dcf  mov     byte ptr [rsp+118h+var_F8], sil; int
0x1800b8dd4  xor     edx, edx; Val
0x1800b8dd6  lea     r8d, [rdx+40h]; Size
0x1800b8dda  lea     rcx, [rsp+118h+var_B8]; void *
0x1800b8ddf  call    memset_0
0x1800b8de4  xor     edx, edx; Val
0x1800b8de6  lea     r8d, [rdx+48h]; Size
0x1800b8dea  lea     rcx, [rsp+118h+var_68]; void *
0x1800b8df2  call    memset_0
0x1800b8df7  mov     [rsp+118h+var_78], 0
0x1800b8e02  lea     r8, [rsp+118h+var_78]
0x1800b8e0a  lea     rdx, [rsp+118h+var_B8]
0x1800b8e0f  mov     rcx, [rsp+118h+var_C8]
0x1800b8e14  call    cs:__imp_SRPkgExtensionIterator_GetNext
0x1800b8e1a  test    eax, eax
0x1800b8e1c  jns     short loc_1800B8E49
0x1800b8e1e  test    sil, sil
0x1800b8e21  jnz     short loc_1800B8DD4
0x1800b8e23  mov     sil, 1
0x1800b8e26  mov     byte ptr [rsp+118h+var_F8], sil; int
0x1800b8e2b  mov     rcx, [rsp+118h]; this
0x1800b8e33  mov     r9d, eax; char *
0x1800b8e36  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b8e3d  mov     edx, 77Ah; void *
0x1800b8e42  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b8e47  jmp     short loc_1800B8DD4
0x1800b8e49  cmp     [rsp+118h+var_78], 0
0x1800b8e51  jnz     short loc_1800B8E8F
0x1800b8e53  mov     rcx, [rsp+118h+var_C8]
0x1800b8e58  call    cs:__imp_SRPkgExtensionIterator_Close
0x1800b8e5e  test    eax, eax
0x1800b8e60  js      loc_1800B8FF0
0x1800b8e66  mov     rax, rdi
0x1800b8e69  mov     rcx, [rsp+118h+var_18]
0x1800b8e71  xor     rcx, rsp; StackCookie
0x1800b8e74  call    __security_check_cookie
0x1800b8e79  lea     r11, [rsp+118h+var_8]
0x1800b8e81  mov     rsi, [r11+10h]
0x1800b8e85  mov     rdi, [r11+28h]
0x1800b8e89  mov     rsp, r11
0x1800b8e8c  pop     r14
0x1800b8e8e  retn
0x1800b8e8f  mov     rax, [rsp+118h+var_B8]
0x1800b8e94  mov     [rsp+118h+var_68], rax
0x1800b8e9c  mov     [rsp+118h+var_60], 0
0x1800b8ea8  mov     rax, [rsp+118h+var_B0]
0x1800b8ead  mov     [rsp+118h+var_58], rax
0x1800b8eb5  mov     rax, [rsp+118h+var_A8]
0x1800b8eba  mov     [rsp+118h+var_50], rax
0x1800b8ec2  mov     rax, [rsp+118h+var_A0]
0x1800b8ec7  mov     [rsp+118h+var_48], rax
0x1800b8ecf  mov     rax, [rsp+118h+var_98]
0x1800b8ed7  mov     [rsp+118h+var_40], rax
0x1800b8edf  mov     rax, [rsp+118h+var_90]
0x1800b8ee7  mov     [rsp+118h+var_38], rax
0x1800b8eef  mov     eax, [rsp+118h+var_88]
0x1800b8ef6  mov     [rsp+118h+var_30], eax
0x1800b8efd  mov     eax, [rsp+118h+var_84]
0x1800b8f04  mov     [rsp+118h+var_2C], eax
0x1800b8f0b  mov     rax, [rsp+118h+var_80]
0x1800b8f13  mov     [rsp+118h+var_28], rax
0x1800b8f1b  lea     r8, [rsp+118h+var_68]
0x1800b8f23  mov     rdx, r14
0x1800b8f26  lea     rcx, [rsp+118h+var_E0]
0x1800b8f2b  call    ??$make_shared@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEBUhstring@6@AEAUSRAppExtensionData@@@std@@YA?AV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@0@AEBUhstring@winrt@@AEAUSRAppExtensionData@@@Z; std::make_shared<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo,winrt::hstring const &,SRAppExtensionData &>(winrt::hstring const &,SRAppExtensionData &)
0x1800b8f30  nop
0x1800b8f31  mov     rdx, rax
0x1800b8f34  mov     rcx, rdi
0x1800b8f37  call    ?push_back@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@2@@Z; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::push_back(std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> &&)
0x1800b8f3c  nop
0x1800b8f3d  mov     rcx, [rsp+118h+var_D8]; this
0x1800b8f42  test    rcx, rcx
0x1800b8f45  jz      short loc_1800B8F4D
0x1800b8f47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b8f4c  nop
0x1800b8f4d  jmp     loc_1800B8DD4
0x1800b8f52  mov     sil, byte ptr [rsp+118h+var_F8]
0x1800b8f57  mov     rdi, [rsp+118h+var_F0]
0x1800b8f5c  mov     r14, [rsp+118h+var_E8]
0x1800b8f61  jmp     loc_1800B8DD4
0x1800b8f66  lea     r8, [rsp+118h+var_68]
0x1800b8f6e  mov     rdx, r14
0x1800b8f71  lea     rcx, [rsp+118h+var_E0]
0x1800b8f76  call    ??$make_shared@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@AEBUhstring@6@AEAUSRAppExtensionData@@@std@@YA?AV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@0@AEBUhstring@winrt@@AEAUSRAppExtensionData@@@Z; std::make_shared<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo,winrt::hstring const &,SRAppExtensionData &>(winrt::hstring const &,SRAppExtensionData &)
0x1800b8f7b  nop
0x1800b8f7c  mov     rdx, rax
0x1800b8f7f  mov     rcx, rdi
0x1800b8f82  call    ?push_back@?$vector@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@V?$allocator@V?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VExtensionInfo@implementation@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@2@@Z; std::vector<std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo>>::push_back(std::shared_ptr<winrt::WindowsUdk::ApplicationModel::AppExtensions::implementation::ExtensionInfo> &&)
0x1800b8f87  nop
0x1800b8f88  mov     rcx, [rsp+118h+var_D8]; this
0x1800b8f8d  test    rcx, rcx
0x1800b8f90  jz      short loc_1800B8F98
0x1800b8f92  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b8f97  nop
0x1800b8f98  jmp     loc_1800B8D01
0x1800b8f9d  mov     sil, byte ptr [rsp+118h+var_F8]
0x1800b8fa2  mov     rdi, [rsp+118h+var_F0]
0x1800b8fa7  mov     r14, [rsp+118h+var_E8]
0x1800b8fac  jmp     loc_1800B8D01
0x1800b8fb1  mov     r9d, eax; char *
0x1800b8fb4  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b8fbb  mov     edx, 748h; void *
0x1800b8fc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8fc6  mov     r9d, eax; char *
0x1800b8fc9  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b8fd0  mov     edx, 769h; void *
0x1800b8fd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8fdb  mov     r9d, eax; char *
0x1800b8fde  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b8fe5  mov     edx, 76Ch; void *
0x1800b8fea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8ff0  mov     rcx, [rsp+118h]; this
0x1800b8ff8  mov     r9d, eax; char *
0x1800b8ffb  lea     r8, aShellcommonUnd_119; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800b9002  mov     edx, 79Ah; void *
0x1800b9007  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
