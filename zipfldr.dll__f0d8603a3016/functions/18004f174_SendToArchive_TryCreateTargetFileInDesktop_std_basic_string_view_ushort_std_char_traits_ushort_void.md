# SendToArchive::TryCreateTargetFileInDesktop(std::basic_string_view<ushort,std::char_traits<ushort>>,void * *)

- ea: `0x18004f174`
- end: `0x18004f2a4`
- name: `?TryCreateTargetFileInDesktop@SendToArchive@@AEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAPEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004dfcc`

## callees

- `0x180024a24`
- `0x180031e94`
- `0x180036f50`
- `0x18004eff0`
- `0x18004f174`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18004f1c0`
- `SHELL32!SHGetKnownFolderPath` at `0x18004f1c0`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004f1f5`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004f1f5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004f21a`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18004f21a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f22e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f22e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f27c`

## pseudocode

```c
__int64 __fastcall SendToArchive::TryCreateTargetFileInDesktop(__int64 a1, __int128 *a2, _QWORD *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // r8
  __int64 v10; // rax
  UINT fuStyle; // [rsp+20h] [rbp-50h]
  _QWORD v12[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  HWND phwnd; // [rsp+50h] [rbp-20h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v6 = SHGetKnownFolderPath(&FOLDERID_Desktop, 0, 0, &ppszPath);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
      (const char *)(unsigned int)v6,
      fuStyle);
    goto LABEL_10;
  }
  phwnd = 0;
  IUnknown_GetWindow(*(IUnknown **)(a1 + 88), &phwnd);
  if ( ShellMessageBoxW(&_ImageBase, phwnd, (LPCWSTR)0x28D4, (LPCWSTR)0x2796, 0x34u) == 6 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 8LL);
    v10 = -1;
    do
      ++v10;
    while ( ppszPath[v10] );
    v13 = *a2;
    v12[0] = ppszPath;
    v12[1] = v10;
    v7 = TryCreateTargetFile((__int64)v12, &v13, v9, a3);
LABEL_10:
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return v7;
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 2147943623LL;
}

```

## disassembly

```asm
0x18004f174  mov     [rsp-28h+arg_18], rbx
0x18004f179  push    rbp
0x18004f17a  push    rsi
0x18004f17b  push    rdi
0x18004f17c  push    r14
0x18004f17e  push    r15
0x18004f180  mov     rbp, rsp
0x18004f183  sub     rsp, 70h
0x18004f187  mov     rax, cs:__security_cookie
0x18004f18e  xor     rax, rsp
0x18004f191  mov     [rbp+var_10], rax
0x18004f195  mov     r14, r8
0x18004f198  mov     rsi, rdx
0x18004f19b  mov     rdi, rcx
0x18004f19e  xor     r15d, r15d
0x18004f1a1  mov     [rbp+ppszPath], r15
0x18004f1a5  xor     edx, edx
0x18004f1a7  lea     rcx, [rbp+ppszPath]
0x18004f1ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004f1b0  lea     r9, [rbp+ppszPath]; ppszPath
0x18004f1b4  xor     r8d, r8d; hToken
0x18004f1b7  xor     edx, edx; dwFlags
0x18004f1b9  lea     rcx, FOLDERID_Desktop; rfid
0x18004f1c0  call    cs:__imp_SHGetKnownFolderPath
0x18004f1c6  mov     ebx, eax
0x18004f1c8  test    eax, eax
0x18004f1ca  jns     short loc_18004F1E9
0x18004f1cc  mov     rcx, [rbp+28h]; this
0x18004f1d0  mov     r9d, eax; char *
0x18004f1d3  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004f1da  mov     edx, 151h; void *
0x18004f1df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f1e4  jmp     loc_18004F273
0x18004f1e9  mov     [rbp+phwnd], r15
0x18004f1ed  lea     rdx, [rbp+phwnd]; phwnd
0x18004f1f1  mov     rcx, [rdi+58h]; punk
0x18004f1f5  call    cs:__imp_IUnknown_GetWindow
0x18004f1fb  mov     [rsp+70h+fuStyle], 34h ; '4'; fuStyle
0x18004f203  mov     r9d, 2796h; lpcTitle
0x18004f209  mov     r8d, 28D4h; lpcText
0x18004f20f  mov     rdx, [rbp+phwnd]; hWnd
0x18004f213  lea     rcx, __ImageBase; hAppInst
0x18004f21a  call    cs:__imp_ShellMessageBoxW
0x18004f220  mov     rcx, [rbp+ppszPath]; pv
0x18004f224  cmp     eax, 6
0x18004f227  jz      short loc_18004F23B
0x18004f229  test    rcx, rcx
0x18004f22c  jz      short loc_18004F234
0x18004f22e  call    cs:__imp_CoTaskMemFree
0x18004f234  mov     eax, 800704C7h
0x18004f239  jmp     short loc_18004F284
0x18004f23b  mov     rax, [rdi+38h]
0x18004f23f  mov     r8, [rax+8]
0x18004f243  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f247  inc     rax
0x18004f24a  cmp     [rcx+rax*2], r15w
0x18004f24f  jnz     short loc_18004F247
0x18004f251  movaps  xmm0, xmmword ptr [rsi]
0x18004f254  movdqa  [rbp+var_30], xmm0
0x18004f259  mov     [rbp+var_40], rcx
0x18004f25d  mov     [rbp+var_38], rax
0x18004f261  mov     r9, r14
0x18004f264  lea     rdx, [rbp+var_30]
0x18004f268  lea     rcx, [rbp+var_40]
0x18004f26c  call    ?TryCreateTargetFile@@YAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0PEBGPEAPEAX@Z; TryCreateTargetFile(std::basic_string_view<ushort>,std::basic_string_view<ushort>,ushort const *,void * *)
0x18004f271  mov     ebx, eax
0x18004f273  mov     rcx, [rbp+ppszPath]; pv
0x18004f277  test    rcx, rcx
0x18004f27a  jz      short loc_18004F282
0x18004f27c  call    cs:__imp_CoTaskMemFree
0x18004f282  mov     eax, ebx
0x18004f284  mov     rcx, [rbp+var_10]
0x18004f288  xor     rcx, rsp; StackCookie
0x18004f28b  call    __security_check_cookie
0x18004f290  mov     rbx, [rsp+70h+arg_18]
0x18004f298  add     rsp, 70h
0x18004f29c  pop     r15
0x18004f29e  pop     r14
0x18004f2a0  pop     rdi
0x18004f2a1  pop     rsi
0x18004f2a2  pop     rbp
0x18004f2a3  retn
```
