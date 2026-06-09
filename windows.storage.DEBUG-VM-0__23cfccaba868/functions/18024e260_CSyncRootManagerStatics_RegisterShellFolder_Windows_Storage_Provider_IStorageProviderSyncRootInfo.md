# CSyncRootManagerStatics::RegisterShellFolder(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x18024e260`
- end: `0x18024e671`
- name: `?RegisterShellFolder@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1041`
- prototype: `void __fastcall(CSyncRootManagerStatics *__hidden this, struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18033b6e0`

## callees

- `0x18000d6cc`
- `0x18001c14c`
- `0x18024e260`
- `0x18024e678`
- `0x18034fc00`
- `0x18035aca0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18024e503`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18024e503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024e46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024e64c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024e46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18024e64c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024e57b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18024e57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e4ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e5b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e5c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e4ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e5b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18024e5c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e2ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e4aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e52e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e2ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e4aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e52e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024e639`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18024e398`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18024e398`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CSyncRootManagerStatics::RegisterShellFolder(
        CSyncRootManagerStatics *this,
        struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *a2)
{
  __int64 (__fastcall *v3)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *); // rbx
  int v4; // eax
  __int64 (__fastcall *v5)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *); // rbx
  int v6; // eax
  int v7; // eax
  unsigned __int16 *v8; // rbx
  int v9; // eax
  __int64 v10; // rax
  void *v11; // rcx
  WCHAR *v12; // rdx
  __int64 v13; // r8
  WCHAR *v14; // r10
  WCHAR v15; // r9
  const char *v16; // r9
  WCHAR *v17; // rdx
  __int64 v18; // rcx
  __int64 (__fastcall *v19)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, LPBC *); // rdi
  int v20; // eax
  const WCHAR *StringRawBuffer; // rax
  HRESULT v22; // eax
  int RegistryRedirectionBehaviorPolicy; // edi
  DWORD v24; // r8d
  HRESULT v25; // eax
  LPVOID v26; // r14
  __int64 (__fastcall *v27)(LPVOID, PCWSTR, unsigned __int16 *, PCWSTR); // rsi
  PCWSTR v28; // rdi
  PCWSTR v29; // rax
  int v30; // eax
  LPVOID v31; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35[8]; // [rsp+38h] [rbp-C8h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v37; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszOutBuf[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v34 = 0;
  CSyncRootManagerStatics::GetNavPanePathFromSyncRoot(this, a2, &v34);
  v39 = 0;
  v3 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v39 = 0;
  v4 = v3(a2, &v39);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40C,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *))(*(_QWORD *)a2 + 112LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  v35[0] = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, char *))(*(_QWORD *)a2 + 208LL))(
         a2,
         v35);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x413,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v7,
      ppv);
  v8 = v34;
  ppbc = 0;
  if ( v35[0] )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
    CreateBindCtx(0, &ppbc);
    wil::GetItemFromParsingName(&v40, v8, ppbc);
    pv = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v40 + 40LL))(v40, 0, &pv);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x419,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    v10 = 2147483646;
    v11 = pv;
    v12 = (WCHAR *)pv;
    v13 = 255;
    v14 = pszOutBuf;
    do
    {
      if ( !v10 )
        break;
      v15 = *v12;
      if ( !*v12 )
        break;
      ++v12;
      *v14++ = v15;
      --v10;
      --v13;
    }
    while ( v13 );
    v16 = v13 == 0 ? (const char *)0x8007007ALL : 0LL;
    v17 = v14 - 1;
    if ( v13 )
      v17 = v14;
    *v17 = 0;
    if ( !v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41A,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        v16,
        ppv);
    if ( v11 )
      CoTaskMemFree(v11);
    v18 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64, WCHAR *, __int64, const char *))(*(_QWORD *)v18 + 16LL))(v18, v17, v13, v16);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
  }
  else
  {
    v19 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, LPBC *))(*(_QWORD *)a2 + 96LL);
    WindowsDeleteString(0);
    ppbc = 0;
    v20 = v19(a2, &ppbc);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x41F,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v20,
        ppv);
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)ppbc, 0);
    v22 = SHLoadIndirectString(StringRawBuffer, pszOutBuf, 0xFFu, 0);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x420,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v22,
        ppv);
    WindowsDeleteString((HSTRING)ppbc);
  }
  RegistryRedirectionBehaviorPolicy = AppModelPolicy::GetRegistryRedirectionBehaviorPolicy(-6);
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v24 = 4;
  if ( RegistryRedirectionBehaviorPolicy != 2359297 )
    v24 = 1;
  v25 = CoCreateInstance(
          &GUID_c6a50e1e_d34c_45e9_9b0c_1d92eb71e49c,
          0,
          v24,
          &GUID_2a63f440_f88b_4358_b651_47423675e67e,
          &v37);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x426,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v25,
      ppva);
  v26 = v37;
  v27 = *(__int64 (__fastcall **)(LPVOID, PCWSTR, unsigned __int16 *, PCWSTR))(*(_QWORD *)v37 + 24LL);
  v28 = WindowsGetStringRawBuffer(string, 0);
  v29 = WindowsGetStringRawBuffer(v39, 0);
  v30 = v27(v26, v29, v8, v28);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x427,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v30,
      (int)pszOutBuf);
  v31 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v39);
  v39 = 0;
  if ( v8 )
    CoTaskMemFree(v8);
}

```

## disassembly

```asm
0x18024e260  push    rbp
0x18024e262  push    rbx
0x18024e263  push    rsi
0x18024e264  push    rdi
0x18024e265  push    r14
0x18024e267  push    r15
0x18024e269  lea     rbp, [rsp-188h]
0x18024e271  sub     rsp, 288h
0x18024e278  mov     rax, cs:__security_cookie
0x18024e27f  xor     rax, rsp
0x18024e282  mov     [rbp+1B0h+var_40], rax
0x18024e289  mov     rsi, rdx
0x18024e28c  xor     r15d, r15d
0x18024e28f  mov     [rsp+2B0h+var_280], r15
0x18024e294  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 **
0x18024e299  call    ?GetNavPanePathFromSyncRoot@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@PEAPEAG@Z; CSyncRootManagerStatics::GetNavPanePathFromSyncRoot(Windows::Storage::Provider::IStorageProviderSyncRootInfo *,ushort * *)
0x18024e29e  mov     [rsp+2B0h+var_258], r15
0x18024e2a3  mov     rax, [rsi]
0x18024e2a6  mov     rbx, [rax+30h]
0x18024e2aa  xor     ecx, ecx; string
0x18024e2ac  call    cs:__imp_WindowsDeleteString
0x18024e2b2  mov     [rsp+2B0h+var_258], r15
0x18024e2b7  lea     rdx, [rsp+2B0h+var_258]
0x18024e2bc  mov     rcx, rsi
0x18024e2bf  mov     rax, rbx
0x18024e2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e2c7  mov     rcx, [rbp+1B8h]; this
0x18024e2ce  test    eax, eax
0x18024e2d0  jns     short loc_18024E2E7
0x18024e2d2  mov     r9d, eax; char *
0x18024e2d5  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e2dc  mov     edx, 40Ch; void *
0x18024e2e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e2e7  mov     [rsp+2B0h+string], r15
0x18024e2ec  mov     rax, [rsi]
0x18024e2ef  mov     rbx, [rax+70h]
0x18024e2f3  xor     ecx, ecx; string
0x18024e2f5  call    cs:__imp_WindowsDeleteString
0x18024e2fb  mov     [rsp+2B0h+string], r15
0x18024e300  lea     rdx, [rsp+2B0h+string]
0x18024e305  mov     rcx, rsi
0x18024e308  mov     rax, rbx
0x18024e30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e310  mov     rcx, [rbp+1B8h]; this
0x18024e317  test    eax, eax
0x18024e319  jns     short loc_18024E330
0x18024e31b  mov     r9d, eax; char *
0x18024e31e  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e325  mov     edx, 40Fh; void *
0x18024e32a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e330  mov     [rsp+2B0h+var_278], r15b
0x18024e335  mov     rax, [rsi]
0x18024e338  lea     rdx, [rsp+2B0h+var_278]
0x18024e33d  mov     rcx, rsi
0x18024e340  mov     rax, [rax+0D0h]
0x18024e347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e34c  mov     rcx, [rbp+1B8h]; this
0x18024e353  test    eax, eax
0x18024e355  jns     short loc_18024E36C
0x18024e357  mov     r9d, eax; char *
0x18024e35a  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e361  mov     edx, 413h; void *
0x18024e366  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e36c  mov     r14d, 1
0x18024e372  mov     rbx, [rsp+2B0h+var_280]
0x18024e377  mov     [rsp+2B0h+ppbc], r15
0x18024e37c  cmp     [rsp+2B0h+var_278], r15b
0x18024e381  jz      loc_18024E4A1
0x18024e387  lea     rcx, [rsp+2B0h+ppbc]
0x18024e38c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024e391  lea     rdx, [rsp+2B0h+ppbc]; ppbc
0x18024e396  xor     ecx, ecx; reserved
0x18024e398  call    cs:__imp_CreateBindCtx
0x18024e39e  nop
0x18024e39f  mov     r8, [rsp+2B0h+ppbc]
0x18024e3a4  mov     rdx, rbx
0x18024e3a7  lea     rcx, [rsp+2B0h+var_250]
0x18024e3ac  call    ?GetItemFromParsingName@wil@@YA?AV?$ComPtr@UIShellItem2@@@WRL@Microsoft@@PEBGPEAUIBindCtx@@@Z; wil::GetItemFromParsingName(ushort const *,IBindCtx *)
0x18024e3b1  nop
0x18024e3b2  mov     [rsp+2B0h+pv], r15
0x18024e3b7  mov     rcx, [rsp+2B0h+var_250]
0x18024e3bc  mov     rax, [rcx]
0x18024e3bf  lea     r8, [rsp+2B0h+pv]
0x18024e3c4  xor     edx, edx
0x18024e3c6  mov     rax, [rax+28h]
0x18024e3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e3cf  mov     rcx, [rbp+1B8h]; this
0x18024e3d6  test    eax, eax
0x18024e3d8  jns     short loc_18024E3EF
0x18024e3da  mov     r9d, eax; char *
0x18024e3dd  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e3e4  mov     edx, 419h; void *
0x18024e3e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e3ef  mov     eax, 7FFFFFFEh
0x18024e3f4  mov     rcx, [rsp+2B0h+pv]; pv
0x18024e3f9  mov     rdx, rcx
0x18024e3fc  mov     r8d, 0FFh
0x18024e402  lea     r10, [rsp+2B0h+pszOutBuf]
0x18024e407  test    rax, rax
0x18024e40a  jz      short loc_18024E42A
0x18024e40c  movzx   r9d, word ptr [rdx]
0x18024e410  test    r9w, r9w
0x18024e414  jz      short loc_18024E42A
0x18024e416  add     rdx, 2
0x18024e41a  mov     [r10], r9w
0x18024e41e  add     r10, 2
0x18024e422  sub     rax, r14
0x18024e425  sub     r8, r14
0x18024e428  jnz     short loc_18024E407
0x18024e42a  mov     rax, r8
0x18024e42d  neg     rax
0x18024e430  sbb     r9d, r9d
0x18024e433  not     r9d
0x18024e436  and     r9d, 8007007Ah; char *
0x18024e43d  lea     rdx, [r10-2]
0x18024e441  test    r8, r8
0x18024e444  cmovnz  rdx, r10
0x18024e448  mov     [rdx], r15w
0x18024e44c  mov     rax, [rbp+1B8h]
0x18024e453  jnz     short loc_18024E46A
0x18024e455  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e45c  mov     edx, 41Ah; void *
0x18024e461  mov     rcx, rax; this
0x18024e464  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e46a  test    rcx, rcx
0x18024e46d  jz      short loc_18024E476
0x18024e46f  call    cs:__imp_CoTaskMemFree
0x18024e475  nop
0x18024e476  mov     rcx, [rsp+2B0h+var_250]
0x18024e47b  test    rcx, rcx
0x18024e47e  jz      short loc_18024E492
0x18024e480  mov     [rsp+2B0h+var_250], r15
0x18024e485  mov     rax, [rcx]
0x18024e488  mov     rax, [rax+10h]
0x18024e48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e491  nop
0x18024e492  lea     rcx, [rsp+2B0h+ppbc]
0x18024e497  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024e49c  jmp     loc_18024E534
0x18024e4a1  mov     rax, [rsi]
0x18024e4a4  mov     rdi, [rax+60h]
0x18024e4a8  xor     ecx, ecx; string
0x18024e4aa  call    cs:__imp_WindowsDeleteString
0x18024e4b0  mov     [rsp+2B0h+ppbc], r15
0x18024e4b5  lea     rdx, [rsp+2B0h+ppbc]
0x18024e4ba  mov     rcx, rsi
0x18024e4bd  mov     rax, rdi
0x18024e4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e4c5  mov     rcx, [rbp+1B8h]; this
0x18024e4cc  test    eax, eax
0x18024e4ce  jns     short loc_18024E4E5
0x18024e4d0  mov     r9d, eax; char *
0x18024e4d3  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e4da  mov     edx, 41Fh; void *
0x18024e4df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e4e5  xor     edx, edx; length
0x18024e4e7  mov     rcx, [rsp+2B0h+ppbc]; string
0x18024e4ec  call    cs:__imp_WindowsGetStringRawBuffer
0x18024e4f2  xor     r9d, r9d; ppvReserved
0x18024e4f5  mov     r8d, 0FFh; cchOutBuf
0x18024e4fb  lea     rdx, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x18024e500  mov     rcx, rax; pszSource
0x18024e503  call    cs:__imp_SHLoadIndirectString
0x18024e509  mov     rcx, [rbp+1B8h]; this
0x18024e510  test    eax, eax
0x18024e512  jns     short loc_18024E529
0x18024e514  mov     r9d, eax; char *
0x18024e517  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e51e  mov     edx, 420h; void *
0x18024e523  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e529  mov     rcx, [rsp+2B0h+ppbc]; string
0x18024e52e  call    cs:__imp_WindowsDeleteString
0x18024e534  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18024e53b  call    ?GetRegistryRedirectionBehaviorPolicy@AppModelPolicy@@YA?AW4RegistryRedirectionBehaviorPolicy@1@PEAX@Z; AppModelPolicy::GetRegistryRedirectionBehaviorPolicy(void *)
0x18024e540  mov     edi, eax
0x18024e542  mov     [rsp+2B0h+var_268], r15
0x18024e547  lea     rcx, [rsp+2B0h+var_268]
0x18024e54c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024e551  mov     r8d, 4
0x18024e557  cmp     edi, 240001h
0x18024e55d  cmovnz  r8d, r14d; dwClsContext
0x18024e561  lea     rax, [rsp+2B0h+var_268]
0x18024e566  mov     qword ptr [rsp+2B0h+ppv], rax; int
0x18024e56b  lea     r9, _GUID_2a63f440_f88b_4358_b651_47423675e67e; riid
0x18024e572  xor     edx, edx; pUnkOuter
0x18024e574  lea     rcx, _GUID_c6a50e1e_d34c_45e9_9b0c_1d92eb71e49c; rclsid
0x18024e57b  call    cs:__imp_CoCreateInstance
0x18024e581  mov     rcx, [rbp+1B8h]; this
0x18024e588  test    eax, eax
0x18024e58a  jns     short loc_18024E5A1
0x18024e58c  mov     r9d, eax; char *
0x18024e58f  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e596  mov     edx, 426h; void *
0x18024e59b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e5a1  mov     r14, [rsp+2B0h+var_268]
0x18024e5a6  mov     rax, [r14]
0x18024e5a9  mov     rsi, [rax+18h]
0x18024e5ad  xor     edx, edx; length
0x18024e5af  mov     rcx, [rsp+2B0h+string]; string
0x18024e5b4  call    cs:__imp_WindowsGetStringRawBuffer
0x18024e5ba  mov     rdi, rax
0x18024e5bd  xor     edx, edx; length
0x18024e5bf  mov     rcx, [rsp+2B0h+var_258]; string
0x18024e5c4  call    cs:__imp_WindowsGetStringRawBuffer
0x18024e5ca  lea     rcx, [rsp+2B0h+pszOutBuf]
0x18024e5cf  mov     qword ptr [rsp+2B0h+ppv], rcx; int
0x18024e5d4  mov     r9, rdi
0x18024e5d7  mov     r8, rbx
0x18024e5da  mov     rdx, rax
0x18024e5dd  mov     rcx, r14
0x18024e5e0  mov     rax, rsi
0x18024e5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e5e8  mov     rcx, [rbp+1B8h]; this
0x18024e5ef  test    eax, eax
0x18024e5f1  jns     short loc_18024E608
0x18024e5f3  mov     r9d, eax; char *
0x18024e5f6  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18024e5fd  mov     edx, 427h; void *
0x18024e602  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18024e608  mov     rcx, [rsp+2B0h+var_268]
0x18024e60d  test    rcx, rcx
0x18024e610  jz      short loc_18024E624
0x18024e612  mov     [rsp+2B0h+var_268], r15
0x18024e617  mov     rax, [rcx]
0x18024e61a  mov     rax, [rax+10h]
0x18024e61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e623  nop
0x18024e624  mov     rcx, [rsp+2B0h+string]; string
0x18024e629  call    cs:__imp_WindowsDeleteString
0x18024e62f  mov     [rsp+2B0h+string], r15
0x18024e634  mov     rcx, [rsp+2B0h+var_258]; string
0x18024e639  call    cs:__imp_WindowsDeleteString
0x18024e63f  mov     [rsp+2B0h+var_258], r15
0x18024e644  test    rbx, rbx
0x18024e647  jz      short loc_18024E652
0x18024e649  mov     rcx, rbx; pv
0x18024e64c  call    cs:__imp_CoTaskMemFree
0x18024e652  mov     rcx, [rbp+1B0h+var_40]
0x18024e659  xor     rcx, rsp; StackCookie
0x18024e65c  call    __security_check_cookie
0x18024e661  add     rsp, 288h
0x18024e668  pop     r15
0x18024e66a  pop     r14
0x18024e66c  pop     rdi
0x18024e66d  pop     rsi
0x18024e66e  pop     rbx
0x18024e66f  pop     rbp
0x18024e670  retn
```
