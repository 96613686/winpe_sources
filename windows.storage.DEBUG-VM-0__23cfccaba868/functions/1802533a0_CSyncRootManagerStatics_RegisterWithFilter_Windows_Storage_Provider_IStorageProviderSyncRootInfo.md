# CSyncRootManagerStatics::RegisterWithFilter(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x1802533a0`
- end: `0x18025385d`
- name: `?RegisterWithFilter@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1213`
- prototype: `void __fastcall(CSyncRootManagerStatics *__hidden this, struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18033b6e0`

## callees

- `0x18000ee84`
- `0x18001c14c`
- `0x1800d13a0`
- `0x1801234e0`
- `0x1802533a0`
- `0x180253b88`
- `0x18033c4cc`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180253802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180253802`
- `cldapi!CfRegisterSyncRoot` at `0x1802537d5`
- `cldapi!CfRegisterSyncRoot` at `0x1802537d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025364b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802536ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802537c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025364b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802536ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802537c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802533ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802533ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025383f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802533ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802533ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253823`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180253831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025383f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CSyncRootManagerStatics::RegisterWithFilter(
        CSyncRootManagerStatics *this,
        struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *a2)
{
  CSyncRootManagerStatics *v3; // rcx
  __int64 (__fastcall *v4)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *); // rbx
  int v5; // eax
  __int64 (__fastcall *v6)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *); // rbx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const unsigned __int16 *v17; // rbx
  Windows::Internal::SyncRootHelpers *StringRawBuffer; // rax
  unsigned __int16 **v19; // r8
  int v20; // eax
  unsigned __int16 v21; // dx
  __int16 v22; // cx
  __int16 v23; // ax
  int v24; // ecx
  unsigned int v25; // eax
  PCWSTR v26; // rax
  int v27; // eax
  LPVOID pv; // [rsp+20h] [rbp-89h] BYREF
  __int64 v29; // [rsp+28h] [rbp-81h] BYREF
  int v30; // [rsp+30h] [rbp-79h] BYREF
  LPVOID v31; // [rsp+38h] [rbp-71h]
  PCWSTR v32; // [rsp+40h] [rbp-69h]
  __int64 v33; // [rsp+48h] [rbp-61h]
  int v34; // [rsp+50h] [rbp-59h]
  int v35; // [rsp+80h] [rbp-29h] BYREF
  int v36; // [rsp+84h] [rbp-25h] BYREF
  int v37; // [rsp+88h] [rbp-21h] BYREF
  int v38; // [rsp+8Ch] [rbp-1Dh] BYREF
  int v39; // [rsp+90h] [rbp-19h] BYREF
  int v40; // [rsp+94h] [rbp-15h] BYREF
  __int64 v41; // [rsp+98h] [rbp-11h] BYREF
  HSTRING v42; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING v44; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v45; // [rsp+B8h] [rbp+Fh] BYREF
  int v46; // [rsp+C0h] [rbp+17h]
  __int64 v47; // [rsp+C4h] [rbp+1Bh]
  int v48; // [rsp+CCh] [rbp+23h]
  __int64 v49; // [rsp+D0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v44 = 0;
  WindowsDeleteString(0);
  v44 = 0;
  CSyncRootManagerStatics::GetPathFromSyncRoot(v3, a2, &v44);
  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v5,
      (int)pv);
  v42 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, HSTRING *))(*(_QWORD *)a2 + 224LL);
  WindowsDeleteString(0);
  v42 = 0;
  v7 = v6(a2, &v42);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D3,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v7,
      (int)pv);
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, int *))(*(_QWORD *)a2 + 128LL))(
         a2,
         &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D5,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v8,
      (int)pv);
  v36 = 0;
  v9 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, int *))(*(_QWORD *)a2 + 144LL))(
         a2,
         &v36);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v9,
      (int)pv);
  v38 = 0;
  v10 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, int *))(*(_QWORD *)a2 + 160LL))(
          a2,
          &v38);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D9,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v10,
      (int)pv);
  v39 = 0;
  v11 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, int *))(*(_QWORD *)a2 + 176LL))(
          a2,
          &v39);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v11,
      (int)pv);
  v40 = 0;
  v12 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, int *))(*(_QWORD *)a2 + 192LL))(
          a2,
          &v40);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3DD,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v12,
      (int)pv);
  v13 = *(_QWORD *)a2;
  v41 = 0;
  v14 = (*(__int64 (__fastcall **)(struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *, __int64 *))(v13 + 64))(
          a2,
          &v41);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v14,
      (int)pv);
  v29 = 0;
  v35 = 0;
  if ( v41 )
  {
    wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(
      &v41,
      &v49);
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 24LL))(v49, &v29);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E7,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v15,
        (int)pv);
    v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 56LL))(v41, &v35);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E8,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
        (const char *)(unsigned int)v16,
        (int)pv);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v49);
  }
  pv = 0;
  v17 = (const unsigned __int16 *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  StringRawBuffer = (Windows::Internal::SyncRootHelpers *)WindowsGetStringRawBuffer(string, 0);
  v20 = Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(StringRawBuffer, v17, v19);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3EC,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v20,
      (int)pv);
  memset_0(&v30, 0, 0x48u);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v30 = 72;
  v31 = pv;
  v32 = WindowsGetStringRawBuffer(v42, 0);
  v33 = v29;
  v34 = v35;
  LODWORD(v45) = 24;
  v21 = 3;
  if ( v37 )
  {
    switch ( v37 )
    {
      case 1:
        v22 = 1;
        goto LABEL_33;
      case 2:
        v22 = 2;
        goto LABEL_33;
      case 3:
        v22 = 3;
        goto LABEL_33;
    }
  }
  v22 = 0;
LABEL_33:
  v23 = v36 & 1;
  if ( (v36 & 2) != 0 )
    v23 |= 2u;
  if ( (v36 & 4) != 0 )
    v23 |= 4u;
  if ( (v36 & 8) != 0 )
    v23 |= 8u;
  WORD2(v45) = v22;
  HIWORD(v45) = v23;
  if ( v38 == 1 )
    v21 = 2;
  v46 = v21;
  v24 = v39 & 1;
  if ( (v39 & 2) != 0 )
    v24 |= 2u;
  if ( (v39 & 4) != 0 )
    v24 |= 4u;
  if ( (v39 & 8) != 0 )
    v24 |= 8u;
  if ( (v39 & 0x100) != 0 )
    v24 |= 0x100u;
  if ( (v39 & 0x10) != 0 )
    v24 |= 0x10u;
  if ( (v39 & 0x20) != 0 )
    v24 |= 0x20u;
  if ( (v39 & 0x40) != 0 )
    v24 |= 0x40u;
  if ( (v39 & 0x80u) != 0 )
    v24 |= 0x80u;
  if ( (v39 & 0x200) != 0 )
    v24 |= 0x200u;
  v25 = v24 | 0x80000000;
  if ( v39 >= 0 )
    v25 = v24;
  LODWORD(v47) = v25;
  HIDWORD(v47) = v40 & 1;
  v26 = WindowsGetStringRawBuffer(v44, 0);
  v27 = CfRegisterSyncRoot(v26, &v30, &v45, 1);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x400,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\storageproviderregistration.cpp",
      (const char *)(unsigned int)v27,
      (int)pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  WindowsDeleteString(v42);
  v42 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v44);
}

```

## disassembly

```asm
0x1802533a0  push    rbp
0x1802533a2  push    rbx
0x1802533a3  push    rsi
0x1802533a4  push    rdi
0x1802533a5  lea     rbp, [rsp-3Fh]
0x1802533aa  sub     rsp, 0E8h
0x1802533b1  mov     rax, cs:__security_cookie
0x1802533b8  xor     rax, rsp
0x1802533bb  mov     [rbp+57h+var_28], rax
0x1802533bf  mov     rdi, rdx
0x1802533c2  xor     esi, esi
0x1802533c4  mov     [rbp+57h+var_50], rsi
0x1802533c8  xor     ecx, ecx; string
0x1802533ca  call    cs:__imp_WindowsDeleteString
0x1802533d0  mov     [rbp+57h+var_50], rsi
0x1802533d4  lea     r8, [rbp+57h+var_50]; HSTRING *
0x1802533d8  mov     rdx, rdi; struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *
0x1802533db  call    ?GetPathFromSyncRoot@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@PEAPEAUHSTRING__@@@Z; CSyncRootManagerStatics::GetPathFromSyncRoot(Windows::Storage::Provider::IStorageProviderSyncRootInfo *,HSTRING__ * *)
0x1802533e0  mov     [rbp+57h+string], rsi
0x1802533e4  mov     rax, [rdi]
0x1802533e7  mov     rbx, [rax+30h]
0x1802533eb  xor     ecx, ecx; string
0x1802533ed  call    cs:__imp_WindowsDeleteString
0x1802533f3  mov     [rbp+57h+string], rsi
0x1802533f7  lea     rdx, [rbp+57h+string]
0x1802533fb  mov     rcx, rdi
0x1802533fe  mov     rax, rbx
0x180253401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180253406  mov     rcx, [rbp+5Fh]; this
0x18025340a  test    eax, eax
0x18025340c  jns     short loc_180253423
0x18025340e  mov     r9d, eax; char *
0x180253411  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180253418  mov     edx, 3D1h; void *
0x18025341d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180253423  mov     [rbp+57h+var_60], rsi
0x180253427  mov     rax, [rdi]
0x18025342a  mov     rbx, [rax+0E0h]
0x180253431  xor     ecx, ecx; string
0x180253433  call    cs:__imp_WindowsDeleteString
0x180253439  mov     [rbp+57h+var_60], rsi
0x18025343d  lea     rdx, [rbp+57h+var_60]
0x180253441  mov     rcx, rdi
0x180253444  mov     rax, rbx
0x180253447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025344c  mov     rcx, [rbp+5Fh]; this
0x180253450  test    eax, eax
0x180253452  jns     short loc_180253469
0x180253454  mov     r9d, eax; char *
0x180253457  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025345e  mov     edx, 3D3h; void *
0x180253463  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180253469  mov     [rbp+57h+var_78], esi
0x18025346c  mov     rax, [rdi]
0x18025346f  lea     rdx, [rbp+57h+var_78]
0x180253473  mov     rcx, rdi
0x180253476  mov     rax, [rax+80h]
0x18025347d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180253482  mov     rcx, [rbp+5Fh]; this
0x180253486  test    eax, eax
0x180253488  jns     short loc_18025349F
0x18025348a  mov     r9d, eax; char *
0x18025348d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180253494  mov     edx, 3D5h; void *
0x180253499  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025349f  mov     [rbp+57h+var_7C], esi
0x1802534a2  mov     rax, [rdi]
0x1802534a5  lea     rdx, [rbp+57h+var_7C]
0x1802534a9  mov     rcx, rdi
0x1802534ac  mov     rax, [rax+90h]
0x1802534b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802534b8  mov     rcx, [rbp+5Fh]; this
0x1802534bc  test    eax, eax
0x1802534be  jns     short loc_1802534D5
0x1802534c0  mov     r9d, eax; char *
0x1802534c3  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802534ca  mov     edx, 3D7h; void *
0x1802534cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802534d5  mov     [rbp+57h+var_74], esi
0x1802534d8  mov     rax, [rdi]
0x1802534db  lea     rdx, [rbp+57h+var_74]
0x1802534df  mov     rcx, rdi
0x1802534e2  mov     rax, [rax+0A0h]
0x1802534e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802534ee  mov     rcx, [rbp+5Fh]; this
0x1802534f2  test    eax, eax
0x1802534f4  jns     short loc_18025350B
0x1802534f6  mov     r9d, eax; char *
0x1802534f9  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180253500  mov     edx, 3D9h; void *
0x180253505  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025350b  mov     [rbp+57h+var_70], esi
0x18025350e  mov     rax, [rdi]
0x180253511  lea     rdx, [rbp+57h+var_70]
0x180253515  mov     rcx, rdi
0x180253518  mov     rax, [rax+0B0h]
0x18025351f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180253524  mov     rcx, [rbp+5Fh]; this
0x180253528  test    eax, eax
0x18025352a  jns     short loc_180253541
0x18025352c  mov     r9d, eax; char *
0x18025352f  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x180253536  mov     edx, 3DBh; void *
0x18025353b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180253541  mov     [rbp+57h+var_6C], esi
0x180253544  mov     rax, [rdi]
0x180253547  lea     rdx, [rbp+57h+var_6C]
0x18025354b  mov     rcx, rdi
0x18025354e  mov     rax, [rax+0C0h]
0x180253555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025355a  mov     rcx, [rbp+5Fh]; this
0x18025355e  test    eax, eax
0x180253560  jns     short loc_180253577
0x180253562  mov     r9d, eax; char *
0x180253565  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025356c  mov     edx, 3DDh; void *
0x180253571  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180253577  mov     rax, [rdi]
0x18025357a  mov     [rbp+57h+var_68], rsi
0x18025357e  lea     rdx, [rbp+57h+var_68]
0x180253582  mov     rcx, rdi
0x180253585  mov     rax, [rax+40h]
0x180253589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025358e  mov     rcx, [rbp+5Fh]; this
0x180253592  test    eax, eax
0x180253594  jns     short loc_1802535AB
0x180253596  mov     r9d, eax; char *
0x180253599  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802535a0  mov     edx, 3E1h; void *
0x1802535a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802535ab  mov     [rsp+100h+var_D8], rsi
0x1802535b0  mov     [rbp+57h+var_80], esi
0x1802535b3  cmp     [rbp+57h+var_68], rsi
0x1802535b7  jz      short loc_180253633
0x1802535b9  lea     rdx, [rbp+57h+var_30]
0x1802535bd  lea     rcx, [rbp+57h+var_68]
0x1802535c1  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x1802535c6  nop
0x1802535c7  mov     rcx, [rbp+57h+var_30]
0x1802535cb  mov     rax, [rcx]
0x1802535ce  lea     rdx, [rsp+100h+var_D8]
0x1802535d3  mov     rax, [rax+18h]
0x1802535d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802535dc  mov     rcx, [rbp+5Fh]; this
0x1802535e0  test    eax, eax
0x1802535e2  jns     short loc_1802535F9
0x1802535e4  mov     r9d, eax; char *
0x1802535e7  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802535ee  mov     edx, 3E7h; void *
0x1802535f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802535f9  mov     rcx, [rbp+57h+var_68]
0x1802535fd  mov     rax, [rcx]
0x180253600  lea     rdx, [rbp+57h+var_80]
0x180253604  mov     rax, [rax+38h]
0x180253608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025360d  mov     rcx, [rbp+5Fh]; this
0x180253611  test    eax, eax
0x180253613  jns     short loc_18025362A
0x180253615  mov     r9d, eax; char *
0x180253618  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025361f  mov     edx, 3E8h; void *
0x180253624  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025362a  lea     rcx, [rbp+57h+var_30]
0x18025362e  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180253633  mov     [rsp+100h+pv], rsi; int
0x180253638  lea     rcx, [rsp+100h+pv]
0x18025363d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180253642  mov     rbx, rax
0x180253645  xor     edx, edx; length
0x180253647  mov     rcx, [rbp+57h+string]; string
0x18025364b  call    cs:__imp_WindowsGetStringRawBuffer
0x180253651  mov     rdx, rbx; unsigned __int16 *
0x180253654  mov     rcx, rax; this
0x180253657  call    ?ConvertFullIdentifierToProviderIdentifier@SyncRootHelpers@Internal@Windows@@YAJPEBGPEAPEAG@Z; Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(ushort const *,ushort * *)
0x18025365c  mov     rcx, [rbp+5Fh]; this
0x180253660  test    eax, eax
0x180253662  jns     short loc_180253679
0x180253664  mov     r9d, eax; char *
0x180253667  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x18025366e  mov     edx, 3ECh; void *
0x180253673  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180253679  mov     ebx, 48h ; 'H'
0x18025367e  mov     r8d, ebx; Size
0x180253681  xor     edx, edx; Val
0x180253683  lea     rcx, [rbp+57h+var_D0]; void *
0x180253687  call    memset_0
0x18025368c  xor     eax, eax
0x18025368e  mov     [rbp+57h+var_48], rax
0x180253692  mov     [rbp+57h+var_40], esi
0x180253695  mov     [rbp+57h+var_3C], rax
0x180253699  mov     [rbp+57h+var_34], eax
0x18025369c  mov     [rbp+57h+var_D0], ebx
0x18025369f  mov     rax, [rsp+100h+pv]
0x1802536a4  mov     [rbp+57h+var_C8], rax
0x1802536a8  xor     edx, edx; length
0x1802536aa  mov     rcx, [rbp+57h+var_60]; string
0x1802536ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1802536b4  mov     [rbp+57h+var_C0], rax
0x1802536b8  mov     rax, [rsp+100h+var_D8]
0x1802536bd  mov     [rbp+57h+var_B8], rax
0x1802536c1  mov     eax, [rbp+57h+var_80]
0x1802536c4  mov     [rbp+57h+var_B0], eax
0x1802536c7  mov     dword ptr [rbp+57h+var_48], 18h
0x1802536ce  mov     r8d, [rbp+57h+var_7C]
0x1802536d2  mov     ecx, [rbp+57h+var_78]
0x1802536d5  lea     edx, [rbx-45h]
0x1802536d8  lea     ebx, [rdx-2]
0x1802536db  lea     r9d, [rdx-1]
0x1802536df  test    ecx, ecx
0x1802536e1  jz      short loc_1802536FF
0x1802536e3  sub     ecx, ebx
0x1802536e5  jz      short loc_1802536FA
0x1802536e7  sub     ecx, ebx
0x1802536e9  jz      short loc_1802536F4
0x1802536eb  cmp     ecx, ebx
0x1802536ed  jnz     short loc_1802536FF
0x1802536ef  movzx   ecx, dx
0x1802536f2  jmp     short loc_180253701
0x1802536f4  movzx   ecx, r9w
0x1802536f8  jmp     short loc_180253701
0x1802536fa  movzx   ecx, bx
0x1802536fd  jmp     short loc_180253701
0x1802536ff  mov     ecx, esi
0x180253701  movzx   eax, r8w
0x180253705  and     ax, bx
0x180253708  test    r9b, r8b
0x18025370b  jz      short loc_180253711
0x18025370d  or      ax, r9w
0x180253711  mov     r11d, 4
0x180253717  test    r11b, r8b
0x18025371a  jz      short loc_180253720
0x18025371c  or      ax, r11w
0x180253720  mov     r10d, 8
0x180253726  test    r10b, r8b
0x180253729  jz      short loc_18025372F
0x18025372b  or      ax, r10w
0x18025372f  mov     word ptr [rbp+57h+var_48+4], cx
0x180253733  mov     word ptr [rbp+57h+var_48+6], ax
0x180253737  mov     ecx, [rbp+57h+var_74]
0x18025373a  sub     ecx, ebx
0x18025373c  jnz     short loc_180253742
0x18025373e  movzx   edx, r9w
0x180253742  mov     word ptr [rbp+57h+var_40], dx
0x180253746  mov     word ptr [rbp+57h+var_40+2], si
0x18025374a  mov     edx, [rbp+57h+var_70]
0x18025374d  mov     ecx, edx
0x18025374f  and     ecx, ebx
0x180253751  test    r9b, dl
0x180253754  jz      short loc_180253759
0x180253756  or      ecx, r9d
0x180253759  test    r11b, dl
0x18025375c  jz      short loc_180253761
0x18025375e  or      ecx, r11d
0x180253761  test    r10b, dl
0x180253764  jz      short loc_180253769
0x180253766  or      ecx, r10d
0x180253769  mov     eax, 100h
0x18025376e  test    eax, edx
0x180253770  jz      short loc_180253774
0x180253772  or      ecx, eax
0x180253774  test    dl, 10h
0x180253777  jz      short loc_18025377C
0x180253779  or      ecx, 10h
0x18025377c  test    dl, 20h
0x18025377f  jz      short loc_180253784
0x180253781  or      ecx, 20h
0x180253784  test    dl, 40h
0x180253787  jz      short loc_18025378C
0x180253789  or      ecx, 40h
0x18025378c  test    dl, dl
0x18025378e  jns     short loc_180253794
0x180253790  bts     ecx, 7
0x180253794  mov     eax, 200h
0x180253799  test    eax, edx
0x18025379b  jz      short loc_18025379F
0x18025379d  or      ecx, eax
0x18025379f  mov     eax, ecx
0x1802537a1  or      eax, 80000000h
0x1802537a6  test    [rbp+57h+var_70], 80000000h
0x1802537ad  cmovz   eax, ecx
0x1802537b0  mov     dword ptr [rbp+57h+var_3C], eax
0x1802537b3  mov     eax, [rbp+57h+var_6C]
0x1802537b6  and     eax, ebx
0x1802537b8  mov     dword ptr [rbp+57h+var_3C+4], eax
0x1802537bb  xor     edx, edx; length
0x1802537bd  mov     rcx, [rbp+57h+var_50]; string
0x1802537c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1802537c7  mov     r9d, ebx
0x1802537ca  lea     r8, [rbp+57h+var_48]
0x1802537ce  lea     rdx, [rbp+57h+var_D0]
0x1802537d2  mov     rcx, rax
0x1802537d5  call    cs:__imp_CfRegisterSyncRoot
0x1802537db  mov     rcx, [rbp+5Fh]; this
0x1802537df  test    eax, eax
0x1802537e1  jns     short loc_1802537F8
0x1802537e3  mov     r9d, eax; char *
0x1802537e6  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1802537ed  mov     edx, 400h; void *
0x1802537f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802537f8  mov     rcx, [rsp+100h+pv]; pv
  ... truncated ...
```
