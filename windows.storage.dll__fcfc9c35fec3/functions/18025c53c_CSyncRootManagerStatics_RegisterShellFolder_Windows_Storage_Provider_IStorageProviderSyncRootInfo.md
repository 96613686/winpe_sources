# CSyncRootManagerStatics::RegisterShellFolder(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x18025c53c`
- end: `0x18025c9a2`
- name: `?RegisterShellFolder@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1126`
- prototype: `void __fastcall(CSyncRootManagerStatics *__hidden this, struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18034d450`

## callees

- `0x180009fc0`
- `0x180079ccc`
- `0x18025c53c`
- `0x18025c9a8`
- `0x180362e70`
- `0x18036c78c`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18025c803`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18025c803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025c75d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025c976`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025c75d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025c976`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025c887`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025c887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c7e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c8c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c7e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c8c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025c8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c95d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025c95d`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18025c680`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18025c680`

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
0x18025c53c  push    rbp
0x18025c53e  push    rbx
0x18025c53f  push    rsi
0x18025c540  push    rdi
0x18025c541  push    r14
0x18025c543  push    r15
0x18025c545  lea     rbp, [rsp-188h]
0x18025c54d  sub     rsp, 288h
0x18025c554  mov     rax, cs:__security_cookie
0x18025c55b  xor     rax, rsp
0x18025c55e  mov     [rbp+1B0h+var_40], rax
0x18025c565  mov     rsi, rdx
0x18025c568  xor     r15d, r15d
0x18025c56b  mov     [rsp+2B0h+var_280], r15
0x18025c570  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 **
0x18025c575  call    ?GetNavPanePathFromSyncRoot@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@PEAPEAG@Z; CSyncRootManagerStatics::GetNavPanePathFromSyncRoot(Windows::Storage::Provider::IStorageProviderSyncRootInfo *,ushort * *)
0x18025c57a  mov     [rsp+2B0h+var_258], r15
0x18025c57f  mov     rax, [rsi]
0x18025c582  mov     rbx, [rax+30h]
0x18025c586  xor     ecx, ecx; string
0x18025c588  call    cs:__imp_WindowsDeleteString
0x18025c58f  nop     dword ptr [rax+rax+00h]
0x18025c594  mov     [rsp+2B0h+var_258], r15
0x18025c599  lea     rdx, [rsp+2B0h+var_258]
0x18025c59e  mov     rcx, rsi
0x18025c5a1  mov     rax, rbx
0x18025c5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c5a9  mov     rcx, [rbp+1B8h]; this
0x18025c5b0  test    eax, eax
0x18025c5b2  jns     short loc_18025C5C9
0x18025c5b4  mov     r9d, eax; char *
0x18025c5b7  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c5be  mov     edx, 40Ch; void *
0x18025c5c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c5c9  mov     [rsp+2B0h+string], r15
0x18025c5ce  mov     rax, [rsi]
0x18025c5d1  mov     rbx, [rax+70h]
0x18025c5d5  xor     ecx, ecx; string
0x18025c5d7  call    cs:__imp_WindowsDeleteString
0x18025c5de  nop     dword ptr [rax+rax+00h]
0x18025c5e3  mov     [rsp+2B0h+string], r15
0x18025c5e8  lea     rdx, [rsp+2B0h+string]
0x18025c5ed  mov     rcx, rsi
0x18025c5f0  mov     rax, rbx
0x18025c5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c5f8  mov     rcx, [rbp+1B8h]; this
0x18025c5ff  test    eax, eax
0x18025c601  jns     short loc_18025C618
0x18025c603  mov     r9d, eax; char *
0x18025c606  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c60d  mov     edx, 40Fh; void *
0x18025c612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c618  mov     [rsp+2B0h+var_278], r15b
0x18025c61d  mov     rax, [rsi]
0x18025c620  lea     rdx, [rsp+2B0h+var_278]
0x18025c625  mov     rcx, rsi
0x18025c628  mov     rax, [rax+0D0h]
0x18025c62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c634  mov     rcx, [rbp+1B8h]; this
0x18025c63b  test    eax, eax
0x18025c63d  jns     short loc_18025C654
0x18025c63f  mov     r9d, eax; char *
0x18025c642  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c649  mov     edx, 413h; void *
0x18025c64e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c654  mov     r14d, 1
0x18025c65a  mov     rbx, [rsp+2B0h+var_280]
0x18025c65f  mov     [rsp+2B0h+ppbc], r15
0x18025c664  cmp     [rsp+2B0h+var_278], r15b
0x18025c669  jz      loc_18025C795
0x18025c66f  lea     rcx, [rsp+2B0h+ppbc]
0x18025c674  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025c679  lea     rdx, [rsp+2B0h+ppbc]; ppbc
0x18025c67e  xor     ecx, ecx; reserved
0x18025c680  call    cs:__imp_CreateBindCtx
0x18025c687  nop     dword ptr [rax+rax+00h]
0x18025c68c  nop
0x18025c68d  mov     r8, [rsp+2B0h+ppbc]
0x18025c692  mov     rdx, rbx
0x18025c695  lea     rcx, [rsp+2B0h+var_250]
0x18025c69a  call    ?GetItemFromParsingName@wil@@YA?AV?$ComPtr@UIShellItem2@@@WRL@Microsoft@@PEBGPEAUIBindCtx@@@Z; wil::GetItemFromParsingName(ushort const *,IBindCtx *)
0x18025c69f  nop
0x18025c6a0  mov     [rsp+2B0h+pv], r15
0x18025c6a5  mov     rcx, [rsp+2B0h+var_250]
0x18025c6aa  mov     rax, [rcx]
0x18025c6ad  lea     r8, [rsp+2B0h+pv]
0x18025c6b2  xor     edx, edx
0x18025c6b4  mov     rax, [rax+28h]
0x18025c6b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c6bd  mov     rcx, [rbp+1B8h]; this
0x18025c6c4  test    eax, eax
0x18025c6c6  jns     short loc_18025C6DD
0x18025c6c8  mov     r9d, eax; char *
0x18025c6cb  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c6d2  mov     edx, 419h; void *
0x18025c6d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c6dd  mov     eax, 7FFFFFFEh
0x18025c6e2  mov     rcx, [rsp+2B0h+pv]; pv
0x18025c6e7  mov     rdx, rcx
0x18025c6ea  mov     r8d, 0FFh
0x18025c6f0  lea     r10, [rsp+2B0h+pszOutBuf]
0x18025c6f5  test    rax, rax
0x18025c6f8  jz      short loc_18025C718
0x18025c6fa  movzx   r9d, word ptr [rdx]
0x18025c6fe  test    r9w, r9w
0x18025c702  jz      short loc_18025C718
0x18025c704  add     rdx, 2
0x18025c708  mov     [r10], r9w
0x18025c70c  add     r10, 2
0x18025c710  sub     rax, r14
0x18025c713  sub     r8, r14
0x18025c716  jnz     short loc_18025C6F5
0x18025c718  mov     rax, r8
0x18025c71b  neg     rax
0x18025c71e  sbb     r9d, r9d
0x18025c721  not     r9d
0x18025c724  and     r9d, 8007007Ah; char *
0x18025c72b  lea     rdx, [r10-2]
0x18025c72f  test    r8, r8
0x18025c732  cmovnz  rdx, r10
0x18025c736  mov     [rdx], r15w
0x18025c73a  mov     rax, [rbp+1B8h]
0x18025c741  jnz     short loc_18025C758
0x18025c743  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c74a  mov     edx, 41Ah; void *
0x18025c74f  mov     rcx, rax; this
0x18025c752  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c758  test    rcx, rcx
0x18025c75b  jz      short loc_18025C76A
0x18025c75d  call    cs:__imp_CoTaskMemFree
0x18025c764  nop     dword ptr [rax+rax+00h]
0x18025c769  nop
0x18025c76a  mov     rcx, [rsp+2B0h+var_250]
0x18025c76f  test    rcx, rcx
0x18025c772  jz      short loc_18025C786
0x18025c774  mov     [rsp+2B0h+var_250], r15
0x18025c779  mov     rax, [rcx]
0x18025c77c  mov     rax, [rax+10h]
0x18025c780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c785  nop
0x18025c786  lea     rcx, [rsp+2B0h+ppbc]
0x18025c78b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025c790  jmp     loc_18025C840
0x18025c795  mov     rax, [rsi]
0x18025c798  mov     rdi, [rax+60h]
0x18025c79c  xor     ecx, ecx; string
0x18025c79e  call    cs:__imp_WindowsDeleteString
0x18025c7a5  nop     dword ptr [rax+rax+00h]
0x18025c7aa  mov     [rsp+2B0h+ppbc], r15
0x18025c7af  lea     rdx, [rsp+2B0h+ppbc]
0x18025c7b4  mov     rcx, rsi
0x18025c7b7  mov     rax, rdi
0x18025c7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c7bf  mov     rcx, [rbp+1B8h]; this
0x18025c7c6  test    eax, eax
0x18025c7c8  jns     short loc_18025C7DF
0x18025c7ca  mov     r9d, eax; char *
0x18025c7cd  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c7d4  mov     edx, 41Fh; void *
0x18025c7d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c7df  xor     edx, edx; length
0x18025c7e1  mov     rcx, [rsp+2B0h+ppbc]; string
0x18025c7e6  call    cs:__imp_WindowsGetStringRawBuffer
0x18025c7ed  nop     dword ptr [rax+rax+00h]
0x18025c7f2  xor     r9d, r9d; ppvReserved
0x18025c7f5  mov     r8d, 0FFh; cchOutBuf
0x18025c7fb  lea     rdx, [rsp+2B0h+pszOutBuf]; pszOutBuf
0x18025c800  mov     rcx, rax; pszSource
0x18025c803  call    cs:__imp_SHLoadIndirectString
0x18025c80a  nop     dword ptr [rax+rax+00h]
0x18025c80f  mov     rcx, [rbp+1B8h]; this
0x18025c816  test    eax, eax
0x18025c818  jns     short loc_18025C82F
0x18025c81a  mov     r9d, eax; char *
0x18025c81d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c824  mov     edx, 420h; void *
0x18025c829  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c82f  mov     rcx, [rsp+2B0h+ppbc]; string
0x18025c834  call    cs:__imp_WindowsDeleteString
0x18025c83b  nop     dword ptr [rax+rax+00h]
0x18025c840  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18025c847  call    ?GetRegistryRedirectionBehaviorPolicy@AppModelPolicy@@YA?AW4RegistryRedirectionBehaviorPolicy@1@PEAX@Z; AppModelPolicy::GetRegistryRedirectionBehaviorPolicy(void *)
0x18025c84c  mov     edi, eax
0x18025c84e  mov     [rsp+2B0h+var_268], r15
0x18025c853  lea     rcx, [rsp+2B0h+var_268]
0x18025c858  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025c85d  mov     r8d, 4
0x18025c863  cmp     edi, 240001h
0x18025c869  cmovnz  r8d, r14d; dwClsContext
0x18025c86d  lea     rax, [rsp+2B0h+var_268]
0x18025c872  mov     qword ptr [rsp+2B0h+ppv], rax; int
0x18025c877  lea     r9, _GUID_2a63f440_f88b_4358_b651_47423675e67e; riid
0x18025c87e  xor     edx, edx; pUnkOuter
0x18025c880  lea     rcx, _GUID_c6a50e1e_d34c_45e9_9b0c_1d92eb71e49c; rclsid
0x18025c887  call    cs:__imp_CoCreateInstance
0x18025c88e  nop     dword ptr [rax+rax+00h]
0x18025c893  mov     rcx, [rbp+1B8h]; this
0x18025c89a  test    eax, eax
0x18025c89c  jns     short loc_18025C8B3
0x18025c89e  mov     r9d, eax; char *
0x18025c8a1  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c8a8  mov     edx, 426h; void *
0x18025c8ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c8b3  mov     r14, [rsp+2B0h+var_268]
0x18025c8b8  mov     rax, [r14]
0x18025c8bb  mov     rsi, [rax+18h]
0x18025c8bf  xor     edx, edx; length
0x18025c8c1  mov     rcx, [rsp+2B0h+string]; string
0x18025c8c6  call    cs:__imp_WindowsGetStringRawBuffer
0x18025c8cd  nop     dword ptr [rax+rax+00h]
0x18025c8d2  mov     rdi, rax
0x18025c8d5  xor     edx, edx; length
0x18025c8d7  mov     rcx, [rsp+2B0h+var_258]; string
0x18025c8dc  call    cs:__imp_WindowsGetStringRawBuffer
0x18025c8e3  nop     dword ptr [rax+rax+00h]
0x18025c8e8  lea     rcx, [rsp+2B0h+pszOutBuf]
0x18025c8ed  mov     qword ptr [rsp+2B0h+ppv], rcx; int
0x18025c8f2  mov     r9, rdi
0x18025c8f5  mov     r8, rbx
0x18025c8f8  mov     rdx, rax
0x18025c8fb  mov     rcx, r14
0x18025c8fe  mov     rax, rsi
0x18025c901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c906  mov     rcx, [rbp+1B8h]; this
0x18025c90d  test    eax, eax
0x18025c90f  jns     short loc_18025C926
0x18025c911  mov     r9d, eax; char *
0x18025c914  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025c91b  mov     edx, 427h; void *
0x18025c920  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025c926  mov     rcx, [rsp+2B0h+var_268]
0x18025c92b  test    rcx, rcx
0x18025c92e  jz      short loc_18025C942
0x18025c930  mov     [rsp+2B0h+var_268], r15
0x18025c935  mov     rax, [rcx]
0x18025c938  mov     rax, [rax+10h]
0x18025c93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025c941  nop
0x18025c942  mov     rcx, [rsp+2B0h+string]; string
0x18025c947  call    cs:__imp_WindowsDeleteString
0x18025c94e  nop     dword ptr [rax+rax+00h]
0x18025c953  mov     [rsp+2B0h+string], r15
0x18025c958  mov     rcx, [rsp+2B0h+var_258]; string
0x18025c95d  call    cs:__imp_WindowsDeleteString
0x18025c964  nop     dword ptr [rax+rax+00h]
0x18025c969  mov     [rsp+2B0h+var_258], r15
0x18025c96e  test    rbx, rbx
0x18025c971  jz      short loc_18025C982
0x18025c973  mov     rcx, rbx; pv
0x18025c976  call    cs:__imp_CoTaskMemFree
0x18025c97d  nop     dword ptr [rax+rax+00h]
0x18025c982  mov     rcx, [rbp+1B0h+var_40]
0x18025c989  xor     rcx, rsp; StackCookie
0x18025c98c  call    __security_check_cookie
0x18025c991  add     rsp, 288h
0x18025c998  pop     r15
0x18025c99a  pop     r14
0x18025c99c  pop     rdi
0x18025c99d  pop     rsi
0x18025c99e  pop     rbx
0x18025c99f  pop     rbp
0x18025c9a0  retn
```
