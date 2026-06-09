# ClientState::~ClientState(void)

- ea: `0x18000a2e8`
- end: `0x18000a432`
- name: `??1ClientState@@QEAA@XZ`
- size: `330`
- prototype: `void __fastcall(ClientState *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000aac8`

## callees

- `0x18000847c`
- `0x180009e38`
- `0x180009f90`
- `0x18000a230`
- `0x18000a2e8`
- `0x18000fe24`
- `0x180010130`
- `0x180010278`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a35b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a35b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3cc`

## pseudocode

```c
void __fastcall ClientState::~ClientState(ClientState *this)
{
  std::_Ref_count_base *v2; // rcx

  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    (char *)this + 496,
    (char *)this + 496);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)this + 57);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)this + 54);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)this + 52);
  WindowsDeleteString(*((HSTRING *)this + 49));
  *((_QWORD *)this + 49) = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 368);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 344);
  WindowsDeleteString(*((HSTRING *)this + 42));
  *((_QWORD *)this + 42) = 0;
  WindowsDeleteString(*((HSTRING *)this + 41));
  *((_QWORD *)this + 41) = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 304);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 37);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 256);
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  WindowsDeleteString(*((HSTRING *)this + 30));
  *((_QWORD *)this + 30) = 0;
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)this + 28);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 160);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 136);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 112);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 96);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 72);
  std::wstring::_Tidy_deallocate((char *)this + 40);
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x18000a2e8  push    rbx
0x18000a2ea  sub     rsp, 20h
0x18000a2ee  mov     rbx, rcx
0x18000a2f1  add     rcx, 1F0h
0x18000a2f8  mov     rdx, rcx
0x18000a2fb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x18000a300  lea     rcx, [rbx+1C8h]
0x18000a307  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000a30c  lea     rcx, [rbx+1B0h]
0x18000a313  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000a318  lea     rcx, [rbx+1A0h]
0x18000a31f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a324  mov     rcx, [rbx+188h]; string
0x18000a32b  call    cs:__imp_WindowsDeleteString
0x18000a331  lea     rcx, [rbx+170h]
0x18000a338  mov     qword ptr [rbx+188h], 0
0x18000a343  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a348  lea     rcx, [rbx+158h]
0x18000a34f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a354  mov     rcx, [rbx+150h]; string
0x18000a35b  call    cs:__imp_WindowsDeleteString
0x18000a361  mov     qword ptr [rbx+150h], 0
0x18000a36c  mov     rcx, [rbx+148h]; string
0x18000a373  call    cs:__imp_WindowsDeleteString
0x18000a379  lea     rcx, [rbx+130h]
0x18000a380  mov     qword ptr [rbx+148h], 0
0x18000a38b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a390  mov     rcx, [rbx+128h]; this
0x18000a397  test    rcx, rcx
0x18000a39a  jz      short loc_18000A3A1
0x18000a39c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a3a1  lea     rcx, [rbx+100h]
0x18000a3a8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a3ad  mov     rcx, [rbx+0F8h]; string
0x18000a3b4  call    cs:__imp_WindowsDeleteString
0x18000a3ba  mov     qword ptr [rbx+0F8h], 0
0x18000a3c5  mov     rcx, [rbx+0F0h]; string
0x18000a3cc  call    cs:__imp_WindowsDeleteString
0x18000a3d2  lea     rcx, [rbx+0E0h]
0x18000a3d9  mov     qword ptr [rbx+0F0h], 0
0x18000a3e4  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000a3e9  lea     rcx, [rbx+0A0h]
0x18000a3f0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a3f5  lea     rcx, [rbx+88h]
0x18000a3fc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a401  lea     rcx, [rbx+70h]
0x18000a405  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a40a  lea     rcx, [rbx+60h]
0x18000a40e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000a413  lea     rcx, [rbx+48h]
0x18000a417  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a41c  lea     rcx, [rbx+28h]
0x18000a420  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a425  mov     rcx, rbx
0x18000a428  add     rsp, 20h
0x18000a42c  pop     rbx
0x18000a42d  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
