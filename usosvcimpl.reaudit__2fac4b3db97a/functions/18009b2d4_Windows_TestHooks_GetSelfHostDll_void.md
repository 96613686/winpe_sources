# Windows::TestHooks::GetSelfHostDll(void)

- ea: `0x18009b2d4`
- end: `0x18009b3f6`
- name: `?GetSelfHostDll@TestHooks@Windows@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009b400`
- `0x18009ce80`

## callees

- `0x180036f98`
- `0x180062598`
- `0x18007d30c`
- `0x18009b2d4`
- `0x18009d92c`
- `0x18009d9b0`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b3cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009b3cc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009b3b9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009b3b9`

## string_xrefs

- `0x18009b308`: `%WINDIR%\System32\UsoSelfhost.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE *__fastcall Windows::TestHooks::GetSelfHostDll(__int64 a1, HMODULE *a2)
{
  __int64 v3; // rcx
  LPCWSTR lpLibFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v7[34]; // [rsp+50h] [rbp-B0h] BYREF

  lpLibFileName[0] = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    lpLibFileName,
    L"%WINDIR%\\System32\\UsoSelfhost.dll");
  memset(v7, 0, sizeof(v7));
  std::ifstream::ifstream(v7, lpLibFileName[0]);
  if ( *(_DWORD *)((char *)&v7[2] + *(int *)(v7[0] + 4LL)) )
  {
    *a2 = 0;
    std::ifstream::~ifstream<char,std::char_traits<char>>(&v7[22]);
    v7[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v7[22]);
  }
  else
  {
    std::ifstream::~ifstream<char,std::char_traits<char>>(&v7[22]);
    v7[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v7[22]);
    v3 = -1;
    do
      ++v3;
    while ( lpLibFileName[0][v3] );
    v6[0] = lpLibFileName[0];
    v6[1] = v3;
    if ( (unsigned __int8)Windows::Trust::IsFileSelfSigned(v6) )
      *a2 = LoadLibraryW(lpLibFileName[0]);
    else
      *a2 = 0;
  }
  if ( lpLibFileName[0] )
    CoTaskMemFree((LPVOID)lpLibFileName[0]);
  return a2;
}

```

## disassembly

```asm
0x18009b2d4  mov     [rsp-8+arg_0], rbx
0x18009b2d9  mov     [rsp-8+arg_10], rdi
0x18009b2de  push    rbp
0x18009b2df  lea     rbp, [rsp-70h]
0x18009b2e4  sub     rsp, 170h
0x18009b2eb  mov     rax, cs:__security_cookie
0x18009b2f2  xor     rax, rsp
0x18009b2f5  mov     [rbp+70h+var_10], rax
0x18009b2f9  mov     rbx, rdx
0x18009b2fc  mov     [rsp+170h+lpLibFileName], rdx
0x18009b301  xor     edi, edi
0x18009b303  mov     [rsp+170h+lpLibFileName], rdi
0x18009b308  lea     rdx, aWindirSystem32; "%WINDIR%\\System32\\UsoSelfhost.dll"
0x18009b30f  lea     rcx, [rsp+170h+lpLibFileName]
0x18009b314  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18009b319  nop
0x18009b31a  xor     edx, edx; Val
0x18009b31c  mov     r8d, 110h; Size
0x18009b322  lea     rcx, [rsp+170h+var_120]; void *
0x18009b327  call    memset
0x18009b32c  mov     rdx, [rsp+170h+lpLibFileName]
0x18009b331  lea     rcx, [rsp+170h+var_120]
0x18009b336  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ifstream::ifstream(wchar_t const *,int,int)
0x18009b33b  mov     rax, [rsp+170h+var_120]
0x18009b340  movsxd  rcx, dword ptr [rax+4]
0x18009b344  cmp     [rsp+rcx+170h+var_110], edi
0x18009b348  lea     rcx, [rbp+70h+var_70]
0x18009b34c  jz      short loc_18009B36C
0x18009b34e  mov     [rbx], rdi
0x18009b351  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009b356  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009b35d  mov     [rbp+70h+var_70], rax
0x18009b361  lea     rcx, [rbp+70h+var_70]; this
0x18009b365  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009b36a  jmp     short loc_18009B3C2
0x18009b36c  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18009b371  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18009b378  mov     [rbp+70h+var_70], rax
0x18009b37c  lea     rcx, [rbp+70h+var_70]; this
0x18009b380  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18009b385  mov     rax, [rsp+170h+lpLibFileName]
0x18009b38a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009b38e  inc     rcx
0x18009b391  cmp     [rax+rcx*2], di
0x18009b395  jnz     short loc_18009B38E
0x18009b397  mov     [rsp+170h+var_130], rax
0x18009b39c  mov     [rsp+170h+var_128], rcx
0x18009b3a1  lea     rcx, [rsp+170h+var_130]
0x18009b3a6  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x18009b3ab  test    al, al
0x18009b3ad  jnz     short loc_18009B3B4
0x18009b3af  mov     [rbx], rdi
0x18009b3b2  jmp     short loc_18009B3C2
0x18009b3b4  mov     rcx, [rsp+170h+lpLibFileName]; lpLibFileName
0x18009b3b9  call    cs:__imp_LoadLibraryW
0x18009b3bf  mov     [rbx], rax
0x18009b3c2  mov     rcx, [rsp+170h+lpLibFileName]; pv
0x18009b3c7  test    rcx, rcx
0x18009b3ca  jz      short loc_18009B3D2
0x18009b3cc  call    cs:__imp_CoTaskMemFree
0x18009b3d2  mov     rax, rbx
0x18009b3d5  mov     rcx, [rbp+70h+var_10]
0x18009b3d9  xor     rcx, rsp; StackCookie
0x18009b3dc  call    __security_check_cookie
0x18009b3e1  lea     r11, [rsp+170h+var_s0]
0x18009b3e9  mov     rbx, [r11+10h]
0x18009b3ed  mov     rdi, [r11+20h]
0x18009b3f1  mov     rsp, r11
0x18009b3f4  pop     rbp
0x18009b3f5  retn
```
