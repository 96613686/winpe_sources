# CreatePlaceholderPidl(ushort const *,IShellItem * *)

- ea: `0x18067b618`
- end: `0x18067b99e`
- name: `?CreatePlaceholderPidl@@YAJPEBGPEAPEAUIShellItem@@@Z`
- size: `902`
- prototype: `int(const unsigned __int16 *, struct IShellItem **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18067ceb8`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x1802789e0`
- `0x180285b6c`
- `0x1802cf9f0`
- `0x180300620`
- `0x180356360`
- `0x18067b4e0`
- `0x18067b618`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b74d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b8e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b8fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b965`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b74d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b8e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b8fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b965`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067b983`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18067b87b`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18067b87b`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18067b653`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18067b653`
- `Windows.Storage!ILCombine` at `0x18067b83a`
- `Windows.Storage!ILCombine` at `0x18067b83a`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067b70e`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067b70e`
- `Windows.Storage!SHBindToObject` at `0x18067b77e`
- `Windows.Storage!SHBindToObject` at `0x18067b77e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CreatePlaceholderPidl(const unsigned __int16 *a1, struct IShellItem **a2)
{
  HRESULT v4; // eax
  const struct _GUID *v5; // rcx
  HRESULT v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  void *v9; // rcx
  HRESULT v10; // eax
  __int64 v11; // rax
  ITEMIDLIST *v12; // rcx
  LPITEMIDLIST v13; // rax
  const ITEMIDLIST *v14; // rax
  HRESULT v15; // eax
  ITEMIDLIST *v16; // rcx
  void *v17; // rcx
  ITEMIDLIST *v19; // rcx
  void *v20; // rcx
  int ppv; // [rsp+20h] [rbp-39h]
  int ppva; // [rsp+20h] [rbp-39h]
  void *p_pv; // [rsp+40h] [rbp-19h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-11h] BYREF
  char v25; // [rsp+50h] [rbp-9h]
  LPVOID pv; // [rsp+58h] [rbp-1h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+60h] [rbp+7h] BYREF
  void *v28; // [rsp+68h] [rbp+Fh] BYREF
  void *v29; // [rsp+70h] [rbp+17h] BYREF
  __int64 v30; // [rsp+78h] [rbp+1Fh] BYREF
  LPBC ppbc; // [rsp+80h] [rbp+27h] BYREF
  const ITEMIDLIST *v32; // [rsp+88h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  ppbc = 0;
  v4 = CreateBindCtx(0, &ppbc);
  v6 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    goto LABEL_29;
  }
  v28 = 0;
  v7 = CreateFileSystemBindData(v5, &v28);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 369;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v7,
      ppv);
LABEL_6:
    wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(&v28);
    goto LABEL_29;
  }
  if ( !ppbc )
    goto LABEL_28;
  v7 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, void *))ppbc->lpVtbl->RegisterObjectParam)(
         ppbc,
         L"File System Bind Data",
         v28);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 373;
    goto LABEL_5;
  }
  pv = 0;
  p_pv = &pv;
  ppidl = 0;
  v25 = 1;
  v6 = SHGetKnownFolderIDList(&FOLDERID_AppsFolder, 0x4000u, 0, &ppidl);
  wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_12;
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v10 = SHBindToObject(0, (LPCITEMIDLIST)pv, 0, &GUID_000214e6_0000_0000_c000_000000000046, &v29);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v10,
      ppva);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
LABEL_12:
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    goto LABEL_6;
  }
  pidl2 = 0;
  v11 = *(_QWORD *)v29;
  p_pv = &pidl2;
  ppidl = 0;
  v25 = 1;
  v6 = (*(__int64 (__fastcall **)(void *, _QWORD, LPBC, const unsigned __int16 *))(v11 + 24))(v29, 0, ppbc, a1);
  wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v6,
      0);
    goto LABEL_19;
  }
  v30 = 0;
  v13 = ILCombine((LPCITEMIDLIST)pv, pidl2);
  wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v30,
    v13);
  v14 = (const ITEMIDLIST *)ILAppendHiddenStringW(v30, 3203334173LL, a1);
  v32 = v14;
  if ( v14 )
  {
    v30 = 0;
    v15 = SHCreateItemFromIDList(v14, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)a2);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
        (const char *)(unsigned int)v15,
        0);
      wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v32,
        0);
      wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v30,
        0);
LABEL_19:
      v12 = (ITEMIDLIST *)pidl2;
      pidl2 = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      goto LABEL_16;
    }
    wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v32,
      0);
    wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v30,
      0);
    v16 = (ITEMIDLIST *)pidl2;
    pidl2 = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v17 = pv;
    pv = 0;
    if ( v17 )
      CoTaskMemFree(v17);
LABEL_28:
    wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(&v28);
    v6 = 0;
    goto LABEL_29;
  }
  wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v32,
    0);
  wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v30,
    0);
  v19 = (ITEMIDLIST *)pidl2;
  pidl2 = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v20 = pv;
  pv = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(&v28);
  v6 = -2147024882;
LABEL_29:
  wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(&ppbc);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18067b618  mov     [rsp-8+arg_10], rbx
0x18067b61d  mov     [rsp-8+arg_18], rsi
0x18067b622  push    rbp
0x18067b623  push    rdi
0x18067b624  push    r14
0x18067b626  lea     rbp, [rsp-47h]
0x18067b62b  sub     rsp, 0A0h
0x18067b632  mov     rax, cs:__security_cookie
0x18067b639  xor     rax, rsp
0x18067b63c  mov     [rbp+57h+var_20], rax
0x18067b640  mov     rsi, rdx
0x18067b643  mov     rdi, rcx
0x18067b646  xor     r14d, r14d
0x18067b649  mov     [rbp+57h+ppbc], r14
0x18067b64d  lea     rdx, [rbp+57h+ppbc]; ppbc
0x18067b651  xor     ecx, ecx; reserved
0x18067b653  call    cs:__imp_CreateBindCtx
0x18067b659  mov     ebx, eax
0x18067b65b  test    eax, eax
0x18067b65d  jns     short loc_18067B67C
0x18067b65f  mov     rcx, [rbp+5Fh]; this
0x18067b663  mov     r9d, eax; char *
0x18067b666  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b66d  mov     edx, 16Eh; void *
0x18067b672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b677  jmp     loc_18067B911
0x18067b67c  mov     [rbp+57h+var_48], r14
0x18067b680  lea     rdx, [rbp+57h+var_48]; void **
0x18067b684  call    ?CreateFileSystemBindData@@YAJAEBU_GUID@@PEAPEAX@Z; CreateFileSystemBindData(_GUID const &,void * *)
0x18067b689  mov     ebx, eax
0x18067b68b  test    eax, eax
0x18067b68d  jns     short loc_18067B6B6
0x18067b68f  mov     edx, 171h; void *
0x18067b694  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b69b  mov     r9d, eax; char *
0x18067b69e  mov     rcx, [rbp+5Fh]; this
0x18067b6a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b6a7  nop
0x18067b6a8  lea     rcx, [rbp+57h+var_48]
0x18067b6ac  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x18067b6b1  jmp     loc_18067B911
0x18067b6b6  mov     rcx, [rbp+57h+ppbc]
0x18067b6ba  test    rcx, rcx
0x18067b6bd  jz      loc_18067B905
0x18067b6c3  mov     rax, [rcx]
0x18067b6c6  mov     r8, [rbp+57h+var_48]
0x18067b6ca  lea     rdx, aFileSystemBind; "File System Bind Data"
0x18067b6d1  mov     rax, [rax+48h]
0x18067b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067b6da  mov     ebx, eax
0x18067b6dc  test    eax, eax
0x18067b6de  jns     short loc_18067B6E7
0x18067b6e0  mov     edx, 175h
0x18067b6e5  jmp     short loc_18067B694
0x18067b6e7  mov     [rbp+57h+pv], r14
0x18067b6eb  lea     rax, [rbp+57h+pv]
0x18067b6ef  mov     [rbp+57h+var_70], rax
0x18067b6f3  mov     [rbp+57h+ppidl], r14
0x18067b6f7  mov     [rbp+57h+var_60], 1
0x18067b6fb  lea     r9, [rbp+57h+ppidl]; ppidl
0x18067b6ff  xor     r8d, r8d; hToken
0x18067b702  mov     edx, 4000h; dwFlags
0x18067b707  lea     rcx, FOLDERID_AppsFolder; rfid
0x18067b70e  call    cs:__imp_SHGetKnownFolderIDList
0x18067b714  mov     ebx, eax
0x18067b716  lea     rcx, [rbp+57h+var_70]
0x18067b71a  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18067b71f  test    ebx, ebx
0x18067b721  jns     short loc_18067B758
0x18067b723  mov     rcx, [rbp+5Fh]; this
0x18067b727  mov     r9d, ebx; char *
0x18067b72a  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b731  mov     edx, 178h; void *
0x18067b736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b73b  nop
0x18067b73c  mov     rcx, [rbp+57h+pv]; pv
0x18067b740  mov     [rbp+57h+pv], r14
0x18067b744  test    rcx, rcx
0x18067b747  jz      loc_18067B6A8
0x18067b74d  call    cs:__imp_CoTaskMemFree
0x18067b753  jmp     loc_18067B6A8
0x18067b758  mov     [rbp+57h+var_40], r14
0x18067b75c  lea     rcx, [rbp+57h+var_40]
0x18067b760  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067b765  lea     rax, [rbp+57h+var_40]
0x18067b769  mov     [rsp+0B0h+ppv], rax; int
0x18067b76e  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18067b775  xor     r8d, r8d; pbc
0x18067b778  mov     rdx, [rbp+57h+pv]; pidl
0x18067b77c  xor     ecx, ecx; psf
0x18067b77e  call    cs:__imp_SHBindToObject
0x18067b784  mov     ebx, eax
0x18067b786  test    eax, eax
0x18067b788  jns     short loc_18067B7AE
0x18067b78a  mov     rcx, [rbp+5Fh]; this
0x18067b78e  mov     r9d, eax; char *
0x18067b791  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b798  mov     edx, 17Bh; void *
0x18067b79d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b7a2  nop
0x18067b7a3  lea     rcx, [rbp+57h+var_40]
0x18067b7a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067b7ac  jmp     short loc_18067B73C
0x18067b7ae  mov     [rbp+57h+pidl2], r14
0x18067b7b2  mov     rcx, [rbp+57h+var_40]
0x18067b7b6  mov     rax, [rcx]
0x18067b7b9  lea     rdx, [rbp+57h+pidl2]
0x18067b7bd  mov     [rbp+57h+var_70], rdx
0x18067b7c1  mov     [rbp+57h+ppidl], r14
0x18067b7c5  mov     [rbp+57h+var_60], 1
0x18067b7c9  mov     [rsp+0B0h+var_80], r14
0x18067b7ce  lea     rdx, [rbp+57h+ppidl]
0x18067b7d2  mov     [rsp+0B0h+var_88], rdx
0x18067b7d7  mov     [rsp+0B0h+ppv], r14; int
0x18067b7dc  mov     r9, rdi
0x18067b7df  mov     r8, [rbp+57h+ppbc]
0x18067b7e3  xor     edx, edx
0x18067b7e5  mov     rax, [rax+18h]
0x18067b7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067b7ee  mov     ebx, eax
0x18067b7f0  lea     rcx, [rbp+57h+var_70]
0x18067b7f4  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18067b7f9  test    ebx, ebx
0x18067b7fb  jns     short loc_18067B82E
0x18067b7fd  mov     rcx, [rbp+5Fh]; this
0x18067b801  mov     r9d, ebx; char *
0x18067b804  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b80b  mov     edx, 17Fh; void *
0x18067b810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b815  nop
0x18067b816  mov     rcx, [rbp+57h+pidl2]; pv
0x18067b81a  mov     [rbp+57h+pidl2], r14
0x18067b81e  test    rcx, rcx
0x18067b821  jz      short loc_18067B7A3
0x18067b823  call    cs:__imp_CoTaskMemFree
0x18067b829  jmp     loc_18067B7A3
0x18067b82e  mov     [rbp+57h+var_38], r14
0x18067b832  mov     rdx, [rbp+57h+pidl2]; pidl2
0x18067b836  mov     rcx, [rbp+57h+pv]; pidl1
0x18067b83a  call    cs:__imp_ILCombine
0x18067b840  mov     rdx, rax
0x18067b843  lea     rcx, [rbp+57h+var_38]
0x18067b847  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b84c  mov     r8, rdi
0x18067b84f  mov     edx, 0BEEF001Dh
0x18067b854  mov     rcx, [rbp+57h+var_38]
0x18067b858  call    ?ILAppendHiddenStringW@@YAPEFAU_ITEMIDLIST@@PEFAU1@W4IDLHID@@PEBG@Z; ILAppendHiddenStringW(_ITEMIDLIST *,IDLHID,ushort const *)
0x18067b85d  mov     [rbp+57h+var_28], rax
0x18067b861  test    rax, rax
0x18067b864  jz      loc_18067B940
0x18067b86a  mov     [rbp+57h+var_38], r14
0x18067b86e  mov     r8, rsi; ppv
0x18067b871  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18067b878  mov     rcx, rax; pidl
0x18067b87b  call    cs:__imp_SHCreateItemFromIDList
0x18067b881  mov     ebx, eax
0x18067b883  test    eax, eax
0x18067b885  jns     short loc_18067B8BB
0x18067b887  mov     rcx, [rbp+5Fh]; this
0x18067b88b  mov     r9d, eax; char *
0x18067b88e  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x18067b895  mov     edx, 189h; void *
0x18067b89a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18067b89f  xor     edx, edx
0x18067b8a1  lea     rcx, [rbp+57h+var_28]
0x18067b8a5  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b8aa  nop
0x18067b8ab  xor     edx, edx
0x18067b8ad  lea     rcx, [rbp+57h+var_38]
0x18067b8b1  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b8b6  jmp     loc_18067B816
0x18067b8bb  xor     edx, edx
0x18067b8bd  lea     rcx, [rbp+57h+var_28]
0x18067b8c1  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b8c6  nop
0x18067b8c7  xor     edx, edx
0x18067b8c9  lea     rcx, [rbp+57h+var_38]
0x18067b8cd  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b8d2  nop
0x18067b8d3  mov     rcx, [rbp+57h+pidl2]; pv
0x18067b8d7  mov     [rbp+57h+pidl2], r14
0x18067b8db  test    rcx, rcx
0x18067b8de  jz      short loc_18067B8E7
0x18067b8e0  call    cs:__imp_CoTaskMemFree
0x18067b8e6  nop
0x18067b8e7  lea     rcx, [rbp+57h+var_40]
0x18067b8eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067b8f0  nop
0x18067b8f1  mov     rcx, [rbp+57h+pv]; pv
0x18067b8f5  mov     [rbp+57h+pv], r14
0x18067b8f9  test    rcx, rcx
0x18067b8fc  jz      short loc_18067B905
0x18067b8fe  call    cs:__imp_CoTaskMemFree
0x18067b904  nop
0x18067b905  lea     rcx, [rbp+57h+var_48]
0x18067b909  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x18067b90e  mov     ebx, r14d
0x18067b911  lea     rcx, [rbp+57h+ppbc]
0x18067b915  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x18067b91a  mov     eax, ebx
0x18067b91c  mov     rcx, [rbp+57h+var_20]
0x18067b920  xor     rcx, rsp; StackCookie
0x18067b923  call    __security_check_cookie
0x18067b928  lea     r11, [rsp+0B0h+var_10]
0x18067b930  mov     rbx, [r11+30h]
0x18067b934  mov     rsi, [r11+38h]
0x18067b938  mov     rsp, r11
0x18067b93b  pop     r14
0x18067b93d  pop     rdi
0x18067b93e  pop     rbp
0x18067b93f  retn
0x18067b940  xor     edx, edx
0x18067b942  lea     rcx, [rbp+57h+var_28]
0x18067b946  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b94b  nop
0x18067b94c  xor     edx, edx
0x18067b94e  lea     rcx, [rbp+57h+var_38]
0x18067b952  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x18067b957  nop
0x18067b958  mov     rcx, [rbp+57h+pidl2]; pv
0x18067b95c  mov     [rbp+57h+pidl2], r14
0x18067b960  test    rcx, rcx
0x18067b963  jz      short loc_18067B96C
0x18067b965  call    cs:__imp_CoTaskMemFree
0x18067b96b  nop
0x18067b96c  lea     rcx, [rbp+57h+var_40]
0x18067b970  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067b975  nop
0x18067b976  mov     rcx, [rbp+57h+pv]; pv
0x18067b97a  mov     [rbp+57h+pv], r14
0x18067b97e  test    rcx, rcx
0x18067b981  jz      short loc_18067B98A
0x18067b983  call    cs:__imp_CoTaskMemFree
0x18067b989  nop
0x18067b98a  lea     rcx, [rbp+57h+var_48]
0x18067b98e  call    ??1?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>::~com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>(void)
0x18067b993  mov     ebx, 8007000Eh
0x18067b998  jmp     loc_18067B911
```
