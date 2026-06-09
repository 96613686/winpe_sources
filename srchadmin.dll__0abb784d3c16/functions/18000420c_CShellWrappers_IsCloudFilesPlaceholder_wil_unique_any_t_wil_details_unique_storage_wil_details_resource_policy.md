# CShellWrappers::IsCloudFilesPlaceholder(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000420c`
- end: `0x180004333`
- name: `?IsCloudFilesPlaceholder@CShellWrappers@@QEAAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001681c`
- `0x180025b24`

## callees

- `0x18000420c`
- `0x18000433c`
- `0x180016ba0`
- `0x180016ccc`
- `0x180026c70`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18000427f`
- `SHLWAPI!SHStrDupW` at `0x18000427f`
- `SHLWAPI!StrCmpNW` at `0x18000425f`
- `SHLWAPI!StrCmpNW` at `0x18000425f`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x1800042e8`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x1800042e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800042af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800042af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004320`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004241`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004241`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800042d8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800042d8`

## pseudocode

```c
__int64 __fastcall CShellWrappers::IsCloudFilesPlaceholder(WCHAR *a1, const WCHAR **a2)
{
  int v3; // eax
  const WCHAR *v4; // rcx
  __int64 v5; // rdi
  HANDLE FileW; // rax
  LPWSTR ppwsz; // [rsp+60h] [rbp+20h] BYREF
  HANDLE v9; // [rsp+68h] [rbp+28h] BYREF
  __int64 FileInformation; // [rsp+70h] [rbp+30h] BYREF

  ppwsz = a1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddingCloudFileCheck>::GetImpl'::`2'::impl) )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60654889>::GetImpl'::`2'::impl);
  v3 = lstrlenW(L"file:///");
  v4 = *a2;
  v5 = v3;
  ppwsz = 0;
  if ( !StrCmpNW(v4, L"file:///", v3) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppwsz,
      0);
    if ( SHStrDupW(&(*a2)[v5], &ppwsz) < 0 )
      goto LABEL_9;
  }
  FileW = CreateFileW(ppwsz, 0, 7u, 0, 3u, 0x2200000u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL
    || (FileInformation = 0, !GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u))
    || !(unsigned __int8)RtlIsCloudFilesPlaceholder((unsigned int)FileInformation, HIDWORD(FileInformation)) )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
LABEL_9:
    if ( ppwsz )
      CoTaskMemFree(ppwsz);
    return 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  if ( ppwsz )
    CoTaskMemFree(ppwsz);
  return 1;
}

```

## disassembly

```asm
0x18000420c  mov     [rsp-18h+ppwsz], rcx
0x180004211  push    rbp
0x180004212  push    rbx
0x180004213  push    rdi
0x180004214  mov     rbp, rsp
0x180004217  sub     rsp, 40h
0x18000421b  mov     rbx, rdx
0x18000421e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck> `wil::Feature<__WilFeatureTraits_Feature_AddingCloudFileCheck>::GetImpl(void)'::`2'::impl
0x180004225  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck>::__private_IsEnabled(void)
0x18000422a  test    al, al
0x18000422c  jnz     short loc_18000423A
0x18000422e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60654889@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60654889@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889> `wil::Feature<__WilFeatureTraits_Feature_60654889>::GetImpl(void)'::`2'::impl
0x180004235  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60654889@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60654889>::__private_IsEnabled(void)
0x18000423a  lea     rcx, aFile_1; "file:///"
0x180004241  call    cs:__imp_lstrlenW
0x180004247  mov     rcx, [rbx]; psz1
0x18000424a  lea     rdx, aFile_1; "file:///"
0x180004251  movsxd  rdi, eax
0x180004254  mov     r8d, edi; nChar
0x180004257  mov     [rbp+ppwsz], 0
0x18000425f  call    cs:__imp_StrCmpNW
0x180004265  test    eax, eax
0x180004267  jnz     short loc_180004289
0x180004269  xor     edx, edx
0x18000426b  lea     rcx, [rbp+ppwsz]
0x18000426f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180004274  mov     rax, [rbx]
0x180004277  lea     rdx, [rbp+ppwsz]; ppwsz
0x18000427b  lea     rcx, [rax+rdi*2]; psz
0x18000427f  call    cs:__imp_SHStrDupW
0x180004285  test    eax, eax
0x180004287  js      short loc_1800042FB
0x180004289  mov     rcx, [rbp+ppwsz]; lpFileName
0x18000428d  xor     r9d, r9d; lpSecurityAttributes
0x180004290  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180004299  xor     edx, edx; dwDesiredAccess
0x18000429b  mov     [rsp+40h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800042a3  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1800042ab  lea     r8d, [r9+7]; dwShareMode
0x1800042af  call    cs:__imp_CreateFileW
0x1800042b5  mov     [rbp+arg_8], rax
0x1800042b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800042bd  jz      short loc_1800042F2
0x1800042bf  mov     r9d, 8; dwBufferSize
0x1800042c5  mov     [rbp+FileInformation], 0
0x1800042cd  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800042d1  mov     rcx, rax; hFile
0x1800042d4  lea     edx, [r9+1]; FileInformationClass
0x1800042d8  call    cs:__imp_GetFileInformationByHandleEx
0x1800042de  test    eax, eax
0x1800042e0  jz      short loc_1800042F2
0x1800042e2  mov     edx, dword ptr [rbp+FileInformation+4]
0x1800042e5  mov     ecx, dword ptr [rbp+FileInformation]
0x1800042e8  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x1800042ee  test    al, al
0x1800042f0  jnz     short loc_18000430E
0x1800042f2  lea     rcx, [rbp+arg_8]
0x1800042f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800042fb  mov     rcx, [rbp+ppwsz]; pv
0x1800042ff  test    rcx, rcx
0x180004302  jz      short loc_18000430A
0x180004304  call    cs:__imp_CoTaskMemFree
0x18000430a  xor     eax, eax
0x18000430c  jmp     short loc_18000432B
0x18000430e  lea     rcx, [rbp+arg_8]
0x180004312  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004317  mov     rcx, [rbp+ppwsz]; pv
0x18000431b  test    rcx, rcx
0x18000431e  jz      short loc_180004326
0x180004320  call    cs:__imp_CoTaskMemFree
0x180004326  mov     eax, 1
0x18000432b  add     rsp, 40h
0x18000432f  pop     rdi
0x180004330  pop     rbx
0x180004331  pop     rbp
0x180004332  retn
```
