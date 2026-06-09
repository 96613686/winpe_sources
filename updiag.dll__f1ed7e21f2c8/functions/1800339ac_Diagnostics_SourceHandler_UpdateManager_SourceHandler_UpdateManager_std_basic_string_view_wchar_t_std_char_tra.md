# Diagnostics::SourceHandler_UpdateManager::SourceHandler_UpdateManager(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800339ac`
- end: `0x180033c0a`
- name: `??0SourceHandler_UpdateManager@Diagnostics@@AEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `606`
- prototype: `IUnknown *__fastcall(IUnknown *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x180009548`
- `0x180019080`
- `0x1800339ac`
- `0x18008fe00`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180033a12`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180033a12`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033a4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033a4f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180033b0a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180033b0a`

## string_xrefs

- `0x180033ba4`: `C:\__w\1\s\src\Calliope\libs\diag\SourceHandler_UpdateManager.hpp`
- `0x180033bb9`: `C:\__w\1\s\src\Calliope\libs\diag\SourceHandler_UpdateManager.hpp`
- `0x180033bf8`: `C:\__w\1\s\src\Calliope\libs\diag\SourceHandler_UpdateManager.hpp`
- `0x180033bce`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x180033be3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
IUnknown *__fastcall Diagnostics::SourceHandler_UpdateManager::SourceHandler_UpdateManager(IUnknown *a1, __int64 a2)
{
  IUnknown *v3; // rcx
  HRESULT v4; // eax
  HRESULT v5; // eax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  HRESULT v9; // eax
  IUnknown *v10; // rax
  IUnknown *v11; // rcx
  struct IUnknownVtbl *lpVtbl; // rdx
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int ppvb; // [rsp+20h] [rbp-50h]
  IUnknown *pProxy[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 *v18; // [rsp+58h] [rbp-18h] BYREF
  LPVOID v19; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  pProxy[1] = a1;
  a1->lpVtbl = (struct IUnknownVtbl *)&Diagnostics::SourceHandler_UpdateManager::`vftable';
  v3 = a1 + 1;
  *(_OWORD *)&v3->lpVtbl = 0;
  v3[2].lpVtbl = 0;
  v3[3].lpVtbl = 0;
  std::wstring::_Construct<1,wchar_t const *>(v3, *(const void **)a2, *(_QWORD *)(a2 + 8));
  a1[5].lpVtbl = 0;
  v4 = CoInitializeEx(0, 0);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x149,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_UpdateManager.hpp",
      (const char *)(unsigned int)v4,
      ppv);
  v19 = 0;
  v5 = CoCreateInstance(
         &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
         0,
         4u,
         &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
         &v19);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v5,
      ppva);
  v18 = 0;
  v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))v19)(
         v19,
         &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
         &v18);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v6,
      ppva);
  pProxy[0] = 0;
  v7 = *v18;
  pProxy[0] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *, const wchar_t *, IUnknown **))(v7 + 24))(
         v18,
         Diagnostics::SourceHandler_UpdateManager::_clientId,
         &psz,
         pProxy);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_UpdateManager.hpp",
      (const char *)(unsigned int)v8,
      ppva);
  v9 = CoSetProxyBlanket(pProxy[0], 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_UpdateManager.hpp",
      (const char *)(unsigned int)v9,
      ppvb);
  if ( v18 )
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  v10 = pProxy[0];
  v11 = 0;
  pProxy[0] = 0;
  lpVtbl = a1[5].lpVtbl;
  a1[5].lpVtbl = (struct IUnknownVtbl *)v10;
  if ( lpVtbl )
  {
    (*((void (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    v11 = pProxy[0];
  }
  if ( v11 )
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
  return a1;
}

```

## disassembly

```asm
0x1800339ac  mov     [rsp-8+arg_10], rbx
0x1800339b1  push    rbp
0x1800339b2  mov     rbp, rsp
0x1800339b5  sub     rsp, 70h
0x1800339b9  mov     rax, cs:__security_cookie
0x1800339c0  xor     rax, rsp
0x1800339c3  mov     [rbp+var_8], rax
0x1800339c7  mov     rbx, rcx
0x1800339ca  mov     [rbp+var_20], rcx
0x1800339ce  mov     [rbp+var_30], 0
0x1800339d5  lea     rax, ??_7SourceHandler_UpdateManager@Diagnostics@@6B@; const Diagnostics::SourceHandler_UpdateManager::`vftable'
0x1800339dc  mov     [rcx], rax
0x1800339df  add     rcx, 8
0x1800339e3  xorps   xmm0, xmm0
0x1800339e6  movups  xmmword ptr [rcx], xmm0
0x1800339e9  mov     qword ptr [rcx+10h], 0
0x1800339f1  mov     qword ptr [rcx+18h], 0
0x1800339f9  mov     r8, [rdx+8]
0x1800339fd  mov     rdx, [rdx]
0x180033a00  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180033a05  nop
0x180033a06  mov     qword ptr [rbx+28h], 0
0x180033a0e  xor     edx, edx; dwCoInit
0x180033a10  xor     ecx, ecx; pvReserved
0x180033a12  call    cs:__imp_CoInitializeEx
0x180033a18  mov     rcx, [rbp+8]; this
0x180033a1c  test    eax, eax
0x180033a1e  js      loc_180033BB6
0x180033a24  mov     r8d, 4; dwClsContext
0x180033a2a  mov     [rbp+var_30], r8d
0x180033a2e  mov     [rbp+var_10], 0
0x180033a36  lea     rax, [rbp+var_10]
0x180033a3a  mov     [rsp+70h+ppv], rax; int
0x180033a3f  lea     r9, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0; riid
0x180033a46  xor     edx, edx; pUnkOuter
0x180033a48  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180033a4f  call    cs:__imp_CoCreateInstance
0x180033a55  mov     rcx, [rbp+8]; this
0x180033a59  test    eax, eax
0x180033a5b  js      loc_180033BCB
0x180033a61  mov     [rbp+var_30], 2
0x180033a68  mov     rcx, [rbp+var_10]
0x180033a6c  mov     [rbp+var_18], 0
0x180033a74  mov     rax, [rcx]
0x180033a77  lea     r8, [rbp+var_18]
0x180033a7b  lea     rdx, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a
0x180033a82  mov     rax, [rax]
0x180033a85  call    _guard_dispatch_icall
0x180033a8a  mov     rcx, [rbp+8]; this
0x180033a8e  test    eax, eax
0x180033a90  js      loc_180033BE0
0x180033a96  mov     [rbp+pProxy], 0
0x180033a9e  mov     [rbp+var_30], 0Bh
0x180033aa5  mov     rcx, [rbp+var_18]
0x180033aa9  mov     rax, [rcx]
0x180033aac  mov     [rbp+pProxy], 0
0x180033ab4  lea     r9, [rbp+pProxy]
0x180033ab8  lea     r8, psz
0x180033abf  mov     rdx, cs:?_clientId@SourceHandler_UpdateManager@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; std::wstring_view const Diagnostics::SourceHandler_UpdateManager::_clientId
0x180033ac6  mov     rax, [rax+18h]
0x180033aca  call    _guard_dispatch_icall
0x180033acf  mov     rcx, [rbp+8]; this
0x180033ad3  test    eax, eax
0x180033ad5  js      loc_180033BF5
0x180033adb  mov     [rsp+70h+dwCapabilities], 0; dwCapabilities
0x180033ae3  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x180033aec  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x180033af4  mov     dword ptr [rsp+70h+ppv], 0; int
0x180033afc  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180033b00  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180033b03  mov     r8d, edx; dwAuthzSvc
0x180033b06  mov     rcx, [rbp+pProxy]; pProxy
0x180033b0a  call    cs:__imp_CoSetProxyBlanket
0x180033b10  mov     rcx, [rbp+8]; this
0x180033b14  test    eax, eax
0x180033b16  js      loc_180033BA1
0x180033b1c  mov     rcx, [rbp+var_18]
0x180033b20  test    rcx, rcx
0x180033b23  jz      short loc_180033B32
0x180033b25  mov     rax, [rcx]
0x180033b28  mov     rax, [rax+10h]
0x180033b2c  call    _guard_dispatch_icall
0x180033b31  nop
0x180033b32  mov     rcx, [rbp+var_10]
0x180033b36  test    rcx, rcx
0x180033b39  jz      short loc_180033B48
0x180033b3b  mov     rax, [rcx]
0x180033b3e  mov     rax, [rax+10h]
0x180033b42  call    _guard_dispatch_icall
0x180033b47  nop
0x180033b48  mov     rax, [rbp+pProxy]
0x180033b4c  xor     ecx, ecx
0x180033b4e  mov     [rbp+pProxy], rcx
0x180033b52  mov     rdx, [rbx+28h]
0x180033b56  mov     [rbx+28h], rax
0x180033b5a  test    rdx, rdx
0x180033b5d  jz      short loc_180033B72
0x180033b5f  mov     rax, [rdx]
0x180033b62  mov     rcx, rdx
0x180033b65  mov     rax, [rax+10h]
0x180033b69  call    _guard_dispatch_icall
0x180033b6e  mov     rcx, [rbp+pProxy]
0x180033b72  test    rcx, rcx
0x180033b75  jz      short loc_180033B84
0x180033b77  mov     rdx, [rcx]
0x180033b7a  mov     rax, [rdx+10h]
0x180033b7e  call    _guard_dispatch_icall
0x180033b83  nop
0x180033b84  mov     rax, rbx
0x180033b87  mov     rcx, [rbp+var_8]
0x180033b8b  xor     rcx, rsp; StackCookie
0x180033b8e  call    __security_check_cookie
0x180033b93  mov     rbx, [rsp+70h+arg_10]
0x180033b9b  add     rsp, 70h
0x180033b9f  pop     rbp
0x180033ba0  retn
0x180033ba1  mov     r9d, eax; char *
0x180033ba4  lea     r8, aCW1SSrcCalliop_20; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180033bab  mov     edx, 162h; void *
0x180033bb0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033bb6  mov     r9d, eax; char *
0x180033bb9  lea     r8, aCW1SSrcCalliop_20; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180033bc0  mov     edx, 149h; void *
0x180033bc5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033bcb  mov     r9d, eax; char *
0x180033bce  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180033bd5  mov     edx, 1C96h; void *
0x180033bda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033be0  mov     r9d, eax; char *
0x180033be3  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180033bea  mov     edx, 1C96h; void *
0x180033bef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033bf5  mov     r9d, eax; char *
0x180033bf8  lea     r8, aCW1SSrcCalliop_20; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180033bff  mov     edx, 157h; void *
0x180033c04  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
