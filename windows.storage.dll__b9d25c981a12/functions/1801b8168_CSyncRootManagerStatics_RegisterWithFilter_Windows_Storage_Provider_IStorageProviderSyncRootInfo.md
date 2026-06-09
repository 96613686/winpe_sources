# CSyncRootManagerStatics::RegisterWithFilter(Windows::Storage::Provider::IStorageProviderSyncRootInfo *)

- ea: `0x1801b8168`
- end: `0x1801b8668`
- name: `?RegisterWithFilter@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@@Z`
- size: `1280`
- prototype: `void __fastcall(CSyncRootManagerStatics *__hidden this, struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18034d450`

## callees

- `0x180033c60`
- `0x180063050`
- `0x180079ccc`
- `0x1801b7e34`
- `0x1801b8168`
- `0x1801b8e84`
- `0x18034e1fc`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b85f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b85f4`
- `cldapi!CfRegisterSyncRoot` at `0x1801b85c1`
- `cldapi!CfRegisterSyncRoot` at `0x1801b85c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b8425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b848e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b85a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b8425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b848e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b85a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8192`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b81bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b861b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b862f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8192`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b81bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b861b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b862f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801b8643`

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
0x1801b8168  push    rbp
0x1801b816a  push    rbx
0x1801b816b  push    rsi
0x1801b816c  push    rdi
0x1801b816d  lea     rbp, [rsp-3Fh]
0x1801b8172  sub     rsp, 0E8h
0x1801b8179  mov     rax, cs:__security_cookie
0x1801b8180  xor     rax, rsp
0x1801b8183  mov     [rbp+57h+var_28], rax
0x1801b8187  mov     rdi, rdx
0x1801b818a  xor     esi, esi
0x1801b818c  mov     [rbp+57h+var_50], rsi
0x1801b8190  xor     ecx, ecx; string
0x1801b8192  call    cs:__imp_WindowsDeleteString
0x1801b8199  nop     dword ptr [rax+rax+00h]
0x1801b819e  mov     [rbp+57h+var_50], rsi
0x1801b81a2  lea     r8, [rbp+57h+var_50]; HSTRING *
0x1801b81a6  mov     rdx, rdi; struct Windows::Storage::Provider::IStorageProviderSyncRootInfo *
0x1801b81a9  call    ?GetPathFromSyncRoot@CSyncRootManagerStatics@@AEAAXPEAUIStorageProviderSyncRootInfo@Provider@Storage@Windows@@PEAPEAUHSTRING__@@@Z; CSyncRootManagerStatics::GetPathFromSyncRoot(Windows::Storage::Provider::IStorageProviderSyncRootInfo *,HSTRING__ * *)
0x1801b81ae  mov     [rbp+57h+string], rsi
0x1801b81b2  mov     rax, [rdi]
0x1801b81b5  mov     rbx, [rax+30h]
0x1801b81b9  xor     ecx, ecx; string
0x1801b81bb  call    cs:__imp_WindowsDeleteString
0x1801b81c2  nop     dword ptr [rax+rax+00h]
0x1801b81c7  mov     [rbp+57h+string], rsi
0x1801b81cb  lea     rdx, [rbp+57h+string]
0x1801b81cf  mov     rcx, rdi
0x1801b81d2  mov     rax, rbx
0x1801b81d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b81da  mov     rcx, [rbp+5Fh]; this
0x1801b81de  test    eax, eax
0x1801b81e0  jns     short loc_1801B81F7
0x1801b81e2  mov     r9d, eax; char *
0x1801b81e5  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b81ec  mov     edx, 3D1h; void *
0x1801b81f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b81f7  mov     [rbp+57h+var_60], rsi
0x1801b81fb  mov     rax, [rdi]
0x1801b81fe  mov     rbx, [rax+0E0h]
0x1801b8205  xor     ecx, ecx; string
0x1801b8207  call    cs:__imp_WindowsDeleteString
0x1801b820e  nop     dword ptr [rax+rax+00h]
0x1801b8213  mov     [rbp+57h+var_60], rsi
0x1801b8217  lea     rdx, [rbp+57h+var_60]
0x1801b821b  mov     rcx, rdi
0x1801b821e  mov     rax, rbx
0x1801b8221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8226  mov     rcx, [rbp+5Fh]; this
0x1801b822a  test    eax, eax
0x1801b822c  jns     short loc_1801B8243
0x1801b822e  mov     r9d, eax; char *
0x1801b8231  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b8238  mov     edx, 3D3h; void *
0x1801b823d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8243  mov     [rbp+57h+var_78], esi
0x1801b8246  mov     rax, [rdi]
0x1801b8249  lea     rdx, [rbp+57h+var_78]
0x1801b824d  mov     rcx, rdi
0x1801b8250  mov     rax, [rax+80h]
0x1801b8257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b825c  mov     rcx, [rbp+5Fh]; this
0x1801b8260  test    eax, eax
0x1801b8262  jns     short loc_1801B8279
0x1801b8264  mov     r9d, eax; char *
0x1801b8267  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b826e  mov     edx, 3D5h; void *
0x1801b8273  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8279  mov     [rbp+57h+var_7C], esi
0x1801b827c  mov     rax, [rdi]
0x1801b827f  lea     rdx, [rbp+57h+var_7C]
0x1801b8283  mov     rcx, rdi
0x1801b8286  mov     rax, [rax+90h]
0x1801b828d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8292  mov     rcx, [rbp+5Fh]; this
0x1801b8296  test    eax, eax
0x1801b8298  jns     short loc_1801B82AF
0x1801b829a  mov     r9d, eax; char *
0x1801b829d  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b82a4  mov     edx, 3D7h; void *
0x1801b82a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b82af  mov     [rbp+57h+var_74], esi
0x1801b82b2  mov     rax, [rdi]
0x1801b82b5  lea     rdx, [rbp+57h+var_74]
0x1801b82b9  mov     rcx, rdi
0x1801b82bc  mov     rax, [rax+0A0h]
0x1801b82c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b82c8  mov     rcx, [rbp+5Fh]; this
0x1801b82cc  test    eax, eax
0x1801b82ce  jns     short loc_1801B82E5
0x1801b82d0  mov     r9d, eax; char *
0x1801b82d3  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b82da  mov     edx, 3D9h; void *
0x1801b82df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b82e5  mov     [rbp+57h+var_70], esi
0x1801b82e8  mov     rax, [rdi]
0x1801b82eb  lea     rdx, [rbp+57h+var_70]
0x1801b82ef  mov     rcx, rdi
0x1801b82f2  mov     rax, [rax+0B0h]
0x1801b82f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b82fe  mov     rcx, [rbp+5Fh]; this
0x1801b8302  test    eax, eax
0x1801b8304  jns     short loc_1801B831B
0x1801b8306  mov     r9d, eax; char *
0x1801b8309  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b8310  mov     edx, 3DBh; void *
0x1801b8315  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b831b  mov     [rbp+57h+var_6C], esi
0x1801b831e  mov     rax, [rdi]
0x1801b8321  lea     rdx, [rbp+57h+var_6C]
0x1801b8325  mov     rcx, rdi
0x1801b8328  mov     rax, [rax+0C0h]
0x1801b832f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8334  mov     rcx, [rbp+5Fh]; this
0x1801b8338  test    eax, eax
0x1801b833a  jns     short loc_1801B8351
0x1801b833c  mov     r9d, eax; char *
0x1801b833f  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b8346  mov     edx, 3DDh; void *
0x1801b834b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8351  mov     rax, [rdi]
0x1801b8354  mov     [rbp+57h+var_68], rsi
0x1801b8358  lea     rdx, [rbp+57h+var_68]
0x1801b835c  mov     rcx, rdi
0x1801b835f  mov     rax, [rax+40h]
0x1801b8363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8368  mov     rcx, [rbp+5Fh]; this
0x1801b836c  test    eax, eax
0x1801b836e  jns     short loc_1801B8385
0x1801b8370  mov     r9d, eax; char *
0x1801b8373  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b837a  mov     edx, 3E1h; void *
0x1801b837f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8385  mov     [rsp+100h+var_D8], rsi
0x1801b838a  mov     [rbp+57h+var_80], esi
0x1801b838d  cmp     [rbp+57h+var_68], rsi
0x1801b8391  jz      short loc_1801B840D
0x1801b8393  lea     rdx, [rbp+57h+var_30]
0x1801b8397  lea     rcx, [rbp+57h+var_68]
0x1801b839b  call    ??$query@UIBufferByteAccess@Streams@Storage@Windows@@@?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIBufferByteAccess@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::query<Windows::Storage::Streams::IBufferByteAccess>(void)
0x1801b83a0  nop
0x1801b83a1  mov     rcx, [rbp+57h+var_30]
0x1801b83a5  mov     rax, [rcx]
0x1801b83a8  lea     rdx, [rsp+100h+var_D8]
0x1801b83ad  mov     rax, [rax+18h]
0x1801b83b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b83b6  mov     rcx, [rbp+5Fh]; this
0x1801b83ba  test    eax, eax
0x1801b83bc  jns     short loc_1801B83D3
0x1801b83be  mov     r9d, eax; char *
0x1801b83c1  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b83c8  mov     edx, 3E7h; void *
0x1801b83cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b83d3  mov     rcx, [rbp+57h+var_68]
0x1801b83d7  mov     rax, [rcx]
0x1801b83da  lea     rdx, [rbp+57h+var_80]
0x1801b83de  mov     rax, [rax+38h]
0x1801b83e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b83e7  mov     rcx, [rbp+5Fh]; this
0x1801b83eb  test    eax, eax
0x1801b83ed  jns     short loc_1801B8404
0x1801b83ef  mov     r9d, eax; char *
0x1801b83f2  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b83f9  mov     edx, 3E8h; void *
0x1801b83fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8404  lea     rcx, [rbp+57h+var_30]
0x1801b8408  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1801b840d  mov     [rsp+100h+pv], rsi; int
0x1801b8412  lea     rcx, [rsp+100h+pv]
0x1801b8417  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801b841c  mov     rbx, rax
0x1801b841f  xor     edx, edx; length
0x1801b8421  mov     rcx, [rbp+57h+string]; string
0x1801b8425  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b842c  nop     dword ptr [rax+rax+00h]
0x1801b8431  mov     rdx, rbx; unsigned __int16 *
0x1801b8434  mov     rcx, rax; this
0x1801b8437  call    ?ConvertFullIdentifierToProviderIdentifier@SyncRootHelpers@Internal@Windows@@YAJPEBGPEAPEAG@Z; Windows::Internal::SyncRootHelpers::ConvertFullIdentifierToProviderIdentifier(ushort const *,ushort * *)
0x1801b843c  mov     rcx, [rbp+5Fh]; this
0x1801b8440  test    eax, eax
0x1801b8442  jns     short loc_1801B8459
0x1801b8444  mov     r9d, eax; char *
0x1801b8447  lea     r8, aOnecoreuapShel_128; "onecoreuap\\shell\\windows.storage\\sto"...
0x1801b844e  mov     edx, 3ECh; void *
0x1801b8453  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801b8459  mov     ebx, 48h ; 'H'
0x1801b845e  mov     r8d, ebx; Size
0x1801b8461  xor     edx, edx; Val
0x1801b8463  lea     rcx, [rbp+57h+var_D0]; void *
0x1801b8467  call    memset_0
0x1801b846c  xor     eax, eax
0x1801b846e  mov     [rbp+57h+var_48], rax
0x1801b8472  mov     [rbp+57h+var_40], esi
0x1801b8475  mov     [rbp+57h+var_3C], rax
0x1801b8479  mov     [rbp+57h+var_34], eax
0x1801b847c  mov     [rbp+57h+var_D0], ebx
0x1801b847f  mov     rax, [rsp+100h+pv]
0x1801b8484  mov     [rbp+57h+var_C8], rax
0x1801b8488  xor     edx, edx; length
0x1801b848a  mov     rcx, [rbp+57h+var_60]; string
0x1801b848e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b8495  nop     dword ptr [rax+rax+00h]
0x1801b849a  mov     [rbp+57h+var_C0], rax
0x1801b849e  mov     rax, [rsp+100h+var_D8]
0x1801b84a3  mov     [rbp+57h+var_B8], rax
0x1801b84a7  mov     eax, [rbp+57h+var_80]
0x1801b84aa  mov     [rbp+57h+var_B0], eax
0x1801b84ad  mov     dword ptr [rbp+57h+var_48], 18h
0x1801b84b4  mov     r8d, [rbp+57h+var_7C]
0x1801b84b8  mov     ecx, [rbp+57h+var_78]
0x1801b84bb  lea     edx, [rbx-45h]
0x1801b84be  lea     ebx, [rdx-2]
0x1801b84c1  lea     r9d, [rdx-1]
0x1801b84c5  test    ecx, ecx
0x1801b84c7  jz      short loc_1801B84E5
0x1801b84c9  sub     ecx, ebx
0x1801b84cb  jz      short loc_1801B84E0
0x1801b84cd  sub     ecx, ebx
0x1801b84cf  jz      short loc_1801B84DA
0x1801b84d1  cmp     ecx, ebx
0x1801b84d3  jnz     short loc_1801B84E5
0x1801b84d5  movzx   ecx, dx
0x1801b84d8  jmp     short loc_1801B84E7
0x1801b84da  movzx   ecx, r9w
0x1801b84de  jmp     short loc_1801B84E7
0x1801b84e0  movzx   ecx, bx
0x1801b84e3  jmp     short loc_1801B84E7
0x1801b84e5  mov     ecx, esi
0x1801b84e7  movzx   eax, r8w
0x1801b84eb  and     ax, bx
0x1801b84ee  test    r9b, r8b
0x1801b84f1  jz      short loc_1801B84F7
0x1801b84f3  or      ax, r9w
0x1801b84f7  mov     r11d, 4
0x1801b84fd  test    r11b, r8b
0x1801b8500  jz      short loc_1801B8506
0x1801b8502  or      ax, r11w
0x1801b8506  mov     r10d, 8
0x1801b850c  test    r10b, r8b
0x1801b850f  jz      short loc_1801B8515
0x1801b8511  or      ax, r10w
0x1801b8515  mov     word ptr [rbp+57h+var_48+4], cx
0x1801b8519  mov     word ptr [rbp+57h+var_48+6], ax
0x1801b851d  mov     ecx, [rbp+57h+var_74]
0x1801b8520  sub     ecx, ebx
0x1801b8522  jnz     short loc_1801B8528
0x1801b8524  movzx   edx, r9w
0x1801b8528  mov     word ptr [rbp+57h+var_40], dx
0x1801b852c  mov     word ptr [rbp+57h+var_40+2], si
0x1801b8530  mov     edx, [rbp+57h+var_70]
0x1801b8533  mov     ecx, edx
0x1801b8535  and     ecx, ebx
0x1801b8537  test    r9b, dl
0x1801b853a  jz      short loc_1801B853F
0x1801b853c  or      ecx, r9d
0x1801b853f  test    r11b, dl
0x1801b8542  jz      short loc_1801B8547
0x1801b8544  or      ecx, r11d
0x1801b8547  test    r10b, dl
0x1801b854a  jz      short loc_1801B854F
0x1801b854c  or      ecx, r10d
0x1801b854f  mov     eax, 100h
0x1801b8554  test    eax, edx
0x1801b8556  jz      short loc_1801B855A
0x1801b8558  or      ecx, eax
0x1801b855a  test    dl, 10h
0x1801b855d  jz      short loc_1801B8562
0x1801b855f  or      ecx, 10h
0x1801b8562  test    dl, 20h
0x1801b8565  jz      short loc_1801B856A
0x1801b8567  or      ecx, 20h
0x1801b856a  test    dl, 40h
0x1801b856d  jz      short loc_1801B8572
0x1801b856f  or      ecx, 40h
0x1801b8572  test    dl, dl
0x1801b8574  jns     short loc_1801B857A
0x1801b8576  bts     ecx, 7
0x1801b857a  mov     eax, 200h
0x1801b857f  test    eax, edx
0x1801b8581  jz      short loc_1801B8585
0x1801b8583  or      ecx, eax
0x1801b8585  mov     eax, ecx
0x1801b8587  or      eax, 80000000h
0x1801b858c  test    [rbp+57h+var_70], 80000000h
0x1801b8593  cmovz   eax, ecx
0x1801b8596  mov     dword ptr [rbp+57h+var_3C], eax
0x1801b8599  mov     eax, [rbp+57h+var_6C]
0x1801b859c  and     eax, ebx
0x1801b859e  mov     dword ptr [rbp+57h+var_3C+4], eax
0x1801b85a1  xor     edx, edx; length
0x1801b85a3  mov     rcx, [rbp+57h+var_50]; string
0x1801b85a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801b85ae  nop     dword ptr [rax+rax+00h]
0x1801b85b3  mov     r9d, ebx
0x1801b85b6  lea     r8, [rbp+57h+var_48]
0x1801b85ba  lea     rdx, [rbp+57h+var_D0]
0x1801b85be  mov     rcx, rax
0x1801b85c1  call    cs:__imp_CfRegisterSyncRoot
0x1801b85c8  nop     dword ptr [rax+rax+00h]
0x1801b85cd  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
