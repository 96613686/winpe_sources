# CreateArchiveThread::ThreadProc(void *)

- ea: `0x18005e420`
- end: `0x18005e5fd`
- name: `?ThreadProc@CreateArchiveThread@@CAKPEAX@Z`
- size: `477`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180021f0c`
- `0x180030a3c`
- `0x180036f50`
- `0x18003edd4`
- `0x180046cbc`
- `0x18004cd94`
- `0x180059fe8`
- `0x18005b2c4`
- `0x18005b680`
- `0x18005b760`
- `0x18005cb10`
- `0x18005e420`
- `0x18006ea0c`
- `0x180071010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x18005e530`
- `SHELL32!SHParseDisplayName` at `0x18005e530`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005e5bf`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005e5bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e568`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18005e4a3`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18005e4a3`

## string_xrefs

- `0x18005e4b4`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateArchiveThread::ThreadProc(PVOID Parameter)
{
  signed int Archive; // eax
  unsigned int v3; // edi
  IStream *v4; // rcx
  HRESULT v5; // eax
  int v6; // eax
  wchar_t *v7; // rbx
  int v8; // eax
  int psfgaoOut; // [rsp+20h] [rbp-E0h]
  wchar_t *String1; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[208]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v13[0] = Parameter;
  CreateArchiveImpl::CreateArchiveImpl(
    (unsigned int)v14,
    (_DWORD)Parameter + 16,
    (_DWORD)Parameter + 48,
    (_DWORD)Parameter + 56,
    *((_QWORD *)Parameter + 1),
    *((_BYTE *)Parameter + 88));
  Archive = (unsigned int)CreateArchiveImpl::CreateArchive((CreateArchive *)v14);
  v3 = Archive;
  if ( Archive < 0 )
  {
    if ( Archive != -2147023673 )
    {
      TryFormatErrorMessage((LPWSTR)&String1, Archive);
      if ( String1 )
        ShellMessageBoxW(&_ImageBase, *((HWND *)Parameter + 1), String1, (LPCWSTR)0x2941, 0x30u);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String1);
    }
  }
  else
  {
    ppv = 0;
    v4 = (IStream *)*((_QWORD *)Parameter + 10);
    if ( v4 )
    {
      v5 = CoUnmarshalInterface(v4, &GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0, &ppv);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34F,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v5,
          psfgaoOut);
      if ( ppv )
      {
        String1 = 0;
        v6 = wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
               *((_QWORD *)Parameter + 6),
               &String1);
        v7 = String1;
        if ( v6 >= 0 )
        {
          v8 = wcsncmp_0(String1, L"\\\\?\\", 4u);
          String1 = 0;
          if ( SHParseDisplayName((wchar_t *)((char *)v7 + (v8 == 0 ? 8 : 0)), 0, (LPITEMIDLIST *)&String1, 0, 0) >= 0 )
            (*(void (__fastcall **)(LPVOID, wchar_t *, __int64))(*(_QWORD *)ppv + 32LL))(ppv, String1, 3);
          wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&String1);
        }
        if ( v7 )
          CoTaskMemFree(v7);
        if ( ppv )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      }
    }
  }
  CreateArchiveImpl::~CreateArchiveImpl((CreateArchiveImpl *)v14);
  std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(v13);
  return v3;
}

```

## disassembly

```asm
0x18005e420  push    rbp
0x18005e422  push    rbx
0x18005e423  push    rsi
0x18005e424  push    rdi
0x18005e425  lea     rbp, [rsp-38h]
0x18005e42a  sub     rsp, 138h
0x18005e431  mov     rax, cs:__security_cookie
0x18005e438  xor     rax, rsp
0x18005e43b  mov     [rbp+50h+var_30], rax
0x18005e43f  mov     rbx, rcx
0x18005e442  mov     [rsp+150h+var_110], rcx
0x18005e447  lea     r9, [rcx+38h]
0x18005e44b  lea     rdx, [rcx+10h]
0x18005e44f  mov     al, [rcx+58h]
0x18005e452  mov     [rsp+150h+var_128], al
0x18005e456  mov     rax, [rcx+8]
0x18005e45a  mov     [rsp+150h+psfgaoOut], rax; int
0x18005e45f  lea     r8, [rcx+30h]
0x18005e463  lea     rcx, [rsp+150h+var_100]
0x18005e468  call    ??0CreateArchiveImpl@@QEAA@AEBUCreateArchiveOptions@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAUHWND__@@_N@Z; CreateArchiveImpl::CreateArchiveImpl(CreateArchiveOptions const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> const &,HWND__ *,bool)
0x18005e46d  lea     rcx, [rsp+150h+var_100]; this
0x18005e472  call    ?CreateArchive@CreateArchiveImpl@@QEAAJXZ; CreateArchiveImpl::CreateArchive(void)
0x18005e477  mov     edi, eax
0x18005e479  test    eax, eax
0x18005e47b  js      loc_18005E582
0x18005e481  mov     [rsp+150h+ppv], 0
0x18005e48a  mov     rcx, [rbx+50h]; pStm
0x18005e48e  test    rcx, rcx
0x18005e491  jz      loc_18005E5CF
0x18005e497  lea     r8, [rsp+150h+ppv]; ppv
0x18005e49c  lea     rdx, _GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0; riid
0x18005e4a3  call    cs:__imp_CoUnmarshalInterface
0x18005e4a9  mov     rcx, [rbp+58h]; this
0x18005e4ad  test    eax, eax
0x18005e4af  jns     short loc_18005E4C5
0x18005e4b1  mov     r9d, eax; char *
0x18005e4b4  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005e4bb  mov     edx, 34Fh; void *
0x18005e4c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005e4c5  cmp     [rsp+150h+ppv], 0
0x18005e4cb  jz      loc_18005E5CF
0x18005e4d1  mov     [rsp+150h+String1], 0
0x18005e4da  lea     rdx, [rsp+150h+String1]
0x18005e4df  mov     rcx, [rbx+30h]
0x18005e4e3  call    ??$GetFinalPathNameByHandleW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@W4VolumePrefix@0@W4PathOptions@0@@Z; wil::GetFinalPathNameByHandleW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::VolumePrefix,wil::PathOptions)
0x18005e4e8  mov     rbx, [rsp+150h+String1]
0x18005e4ed  test    eax, eax
0x18005e4ef  js      short loc_18005E560
0x18005e4f1  mov     r8d, 4; MaxCount
0x18005e4f7  lea     rdx, S2; "\\\\?\\"
0x18005e4fe  mov     rcx, rbx; String1
0x18005e501  call    wcsncmp_0
0x18005e506  mov     [rsp+150h+String1], 0
0x18005e50f  neg     eax
0x18005e511  sbb     rcx, rcx
0x18005e514  not     rcx
0x18005e517  and     ecx, 8
0x18005e51a  add     rcx, rbx; pszName
0x18005e51d  mov     [rsp+150h+psfgaoOut], 0; psfgaoOut
0x18005e526  xor     r9d, r9d; sfgaoIn
0x18005e529  lea     r8, [rsp+150h+String1]; ppidl
0x18005e52e  xor     edx, edx; pbc
0x18005e530  call    cs:__imp_SHParseDisplayName
0x18005e536  test    eax, eax
0x18005e538  js      short loc_18005E556
0x18005e53a  mov     rcx, [rsp+150h+ppv]
0x18005e53f  mov     rax, [rcx]
0x18005e542  mov     r8d, 3
0x18005e548  mov     rdx, [rsp+150h+String1]
0x18005e54d  mov     rax, [rax+20h]
0x18005e551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e556  lea     rcx, [rsp+150h+String1]
0x18005e55b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x18005e560  test    rbx, rbx
0x18005e563  jz      short loc_18005E56E
0x18005e565  mov     rcx, rbx; pv
0x18005e568  call    cs:__imp_CoTaskMemFree
0x18005e56e  cmp     [rsp+150h+ppv], 0
0x18005e574  jz      short loc_18005E5CF
0x18005e576  lea     rcx, [rsp+150h+ppv]
0x18005e57b  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005e580  jmp     short loc_18005E5CF
0x18005e582  cmp     edi, 800704C7h
0x18005e588  jz      short loc_18005E5CF
0x18005e58a  mov     r8d, 2950h
0x18005e590  mov     edx, edi; dwMessageId
0x18005e592  lea     rcx, [rsp+150h+String1]; lpBuffer
0x18005e597  call    ?TryFormatErrorMessage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@JI@Z; TryFormatErrorMessage(long,uint)
0x18005e59c  mov     r8, [rsp+150h+String1]; lpcText
0x18005e5a1  test    r8, r8
0x18005e5a4  jz      short loc_18005E5C5
0x18005e5a6  mov     dword ptr [rsp+150h+psfgaoOut], 30h ; '0'; fuStyle
0x18005e5ae  mov     r9d, 2941h; lpcTitle
0x18005e5b4  mov     rdx, [rbx+8]; hWnd
0x18005e5b8  lea     rcx, __ImageBase; hAppInst
0x18005e5bf  call    cs:__imp_ShellMessageBoxW
0x18005e5c5  lea     rcx, [rsp+150h+String1]
0x18005e5ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005e5cf  lea     rcx, [rsp+150h+var_100]; this
0x18005e5d4  call    ??1CreateArchiveImpl@@QEAA@XZ; CreateArchiveImpl::~CreateArchiveImpl(void)
0x18005e5d9  lea     rcx, [rsp+150h+var_110]
0x18005e5de  call    ??1?$unique_ptr@UCreateArchiveThread@@U?$default_delete@UCreateArchiveThread@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(void)
0x18005e5e3  mov     eax, edi
0x18005e5e5  mov     rcx, [rbp+50h+var_30]
0x18005e5e9  xor     rcx, rsp; StackCookie
0x18005e5ec  call    __security_check_cookie
0x18005e5f1  add     rsp, 138h
0x18005e5f8  pop     rdi
0x18005e5f9  pop     rsi
0x18005e5fa  pop     rbx
0x18005e5fb  pop     rbp
0x18005e5fc  retn
```
