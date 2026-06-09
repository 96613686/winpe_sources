# WslSession::RegisterDistribution(ushort const *)

- ea: `0x180007344`
- end: `0x18000751a`
- name: `?RegisterDistribution@WslSession@@QEBAJPEBG@Z`
- size: `470`
- prototype: `__int64 __fastcall(WslSession *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000710c`

## callees

- `0x180001dc0`
- `0x180004fb4`
- `0x180004fd4`
- `0x180006968`
- `0x18000698c`
- `0x1800070ec`
- `0x180007344`
- `0x180007590`
- `0x180008a48`
- `0x180008bd8`
- `0x1800093ec`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180007425`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180007425`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007477`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007477`

## pseudocode

```c
__int64 __fastcall WslSession::RegisterDistribution(WslSession *this, const unsigned __int16 *a2)
{
  int StoreInstallPath; // eax
  unsigned int v5; // ebx
  int DistroPackagePath; // eax
  int CallingExePath; // eax
  HRESULT v8; // eax
  HANDLE FileW; // rax
  const char *v10; // r9
  unsigned int LastError; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  PCWSTR pszPathIn; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h] BYREF
  HANDLE v16; // [rsp+50h] [rbp-20h] BYREF
  PWSTR ppszPathOut; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v15 = 0;
  StoreInstallPath = GetStoreInstallPath(&v15);
  v5 = StoreInstallPath;
  if ( StoreInstallPath == -2147221164 || StoreInstallPath == -2147009196 )
  {
    CallingExePath = _GetCallingExePath(&v15);
    v5 = CallingExePath;
    if ( CallingExePath >= 0 )
      goto LABEL_4;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
      (const char *)(unsigned int)CallingExePath,
      dwCreationDisposition);
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\register.cpp",
      (const char *)v5,
      dwCreationDisposition);
    goto LABEL_17;
  }
  if ( StoreInstallPath < 0 )
    goto LABEL_8;
LABEL_4:
  pszPathIn = 0;
  DistroPackagePath = WslSession::s_GetDistroPackagePath(&pszPathIn);
  v5 = DistroPackagePath;
  if ( DistroPackagePath >= 0 )
  {
    ppszPathOut = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v8 = PathAllocCombine(pszPathIn, a2, 0, &ppszPathOut);
    v5 = v8;
    if ( v8 >= 0 )
    {
      FileW = CreateFileW(ppszPathOut, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      v16 = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, HANDLE, _QWORD, __int64))(**((_QWORD **)this + 2)
                                                                                               + 24LL))(
                      *((_QWORD *)this + 2),
                      *(_QWORD *)this,
                      0,
                      FileW,
                      0,
                      v15);
      else
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x78,
                      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\register.cpp",
                      v10);
      v5 = LastError;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\register.cpp",
        (const char *)(unsigned int)v8,
        dwCreationDisposition);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\vm\\wsl\\lxss\\wslapi\\register.cpp",
      (const char *)(unsigned int)DistroPackagePath,
      dwCreationDisposition);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return v5;
}

```

## disassembly

```asm
0x180007344  mov     [rsp-18h+arg_10], rbx
0x180007349  push    rbp
0x18000734a  push    rsi
0x18000734b  push    rdi
0x18000734c  mov     rbp, rsp
0x18000734f  sub     rsp, 70h
0x180007353  mov     rax, cs:__security_cookie
0x18000735a  xor     rax, rsp
0x18000735d  mov     [rbp+var_10], rax
0x180007361  mov     rdi, rdx
0x180007364  mov     rsi, rcx
0x180007367  mov     [rbp+var_28], 0
0x18000736f  lea     rcx, [rbp+var_28]
0x180007373  call    _GetStoreInstallPath
0x180007378  mov     ebx, eax
0x18000737a  cmp     eax, 80040154h
0x18000737f  jz      short loc_1800073C0
0x180007381  cmp     eax, 80073D54h
0x180007386  jz      short loc_1800073C0
0x180007388  test    eax, eax
0x18000738a  js      short loc_1800073E7
0x18000738c  mov     [rbp+pszPathIn], 0
0x180007394  lea     rcx, [rbp+pszPathIn]
0x180007398  call    ?s_GetDistroPackagePath@WslSession@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; WslSession::s_GetDistroPackagePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000739d  mov     ebx, eax
0x18000739f  test    eax, eax
0x1800073a1  jns     short loc_180007404
0x1800073a3  mov     rcx, [rbp+18h]; this
0x1800073a7  mov     r9d, eax; char *
0x1800073aa  lea     r8, aOnecoreVmWslLx_5; "onecore\\vm\\wsl\\lxss\\wslapi\\registe"...
0x1800073b1  mov     edx, 68h ; 'h'; void *
0x1800073b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073bb  jmp     loc_1800074E9
0x1800073c0  lea     rcx, [rbp+var_28]
0x1800073c4  call    ?_GetCallingExePath@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetCallingExePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800073c9  mov     ebx, eax
0x1800073cb  test    eax, eax
0x1800073cd  jns     short loc_18000738C
0x1800073cf  mov     rcx, [rbp+18h]; this
0x1800073d3  mov     r9d, eax; char *
0x1800073d6  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x1800073dd  mov     edx, 0E9h; void *
0x1800073e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073e7  mov     rcx, [rbp+18h]; this
0x1800073eb  mov     r9d, ebx; char *
0x1800073ee  lea     r8, aOnecoreVmWslLx_5; "onecore\\vm\\wsl\\lxss\\wslapi\\registe"...
0x1800073f5  mov     edx, 65h ; 'e'; void *
0x1800073fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ff  jmp     loc_1800074F3
0x180007404  mov     [rbp+ppszPathOut], 0
0x18000740c  xor     edx, edx
0x18000740e  lea     rcx, [rbp+ppszPathOut]
0x180007412  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180007417  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18000741b  xor     r8d, r8d; dwFlags
0x18000741e  mov     rdx, rdi; pszMore
0x180007421  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x180007425  call    cs:__imp_PathAllocCombine
0x18000742b  mov     ebx, eax
0x18000742d  test    eax, eax
0x18000742f  jns     short loc_18000744E
0x180007431  mov     rcx, [rbp+18h]; this
0x180007435  mov     r9d, eax; char *
0x180007438  lea     r8, aOnecoreVmWslLx_5; "onecore\\vm\\wsl\\lxss\\wslapi\\registe"...
0x18000743f  mov     edx, 6Eh ; 'n'; void *
0x180007444  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007449  jmp     loc_1800074DF
0x18000744e  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180007457  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000745f  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180007467  xor     r9d, r9d; lpSecurityAttributes
0x18000746a  mov     edx, 80000000h; dwDesiredAccess
0x18000746f  lea     r8d, [r9+5]; dwShareMode
0x180007473  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180007477  call    cs:__imp_CreateFileW
0x18000747d  mov     [rbp+var_20], rax
0x180007481  lea     rcx, [rax+1]
0x180007485  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000748c  jnz     short loc_1800074A5
0x18000748e  mov     rcx, [rbp+18h]; this
0x180007492  lea     r8, aOnecoreVmWslLx_5; "onecore\\vm\\wsl\\lxss\\wslapi\\registe"...
0x180007499  mov     edx, 78h ; 'x'; void *
0x18000749e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800074a3  jmp     short loc_1800074D3
0x1800074a5  mov     rcx, [rsi+10h]
0x1800074a9  mov     rdx, [rcx]
0x1800074ac  mov     r10, [rdx+18h]
0x1800074b0  mov     rdx, [rbp+var_28]
0x1800074b4  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rdx
0x1800074b9  mov     qword ptr [rsp+70h+dwCreationDisposition], 0
0x1800074c2  mov     r9, rax
0x1800074c5  xor     r8d, r8d
0x1800074c8  mov     rdx, [rsi]
0x1800074cb  mov     rax, r10
0x1800074ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d3  mov     ebx, eax
0x1800074d5  lea     rcx, [rbp+var_20]
0x1800074d9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800074de  nop
0x1800074df  lea     rcx, [rbp+ppszPathOut]
0x1800074e3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800074e8  nop
0x1800074e9  lea     rcx, [rbp+pszPathIn]
0x1800074ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800074f2  nop
0x1800074f3  lea     rcx, [rbp+var_28]
0x1800074f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800074fc  mov     eax, ebx
0x1800074fe  mov     rcx, [rbp+var_10]
0x180007502  xor     rcx, rsp; StackCookie
0x180007505  call    __security_check_cookie
0x18000750a  mov     rbx, [rsp+70h+arg_10]
0x180007512  add     rsp, 70h
0x180007516  pop     rdi
0x180007517  pop     rsi
0x180007518  pop     rbp
0x180007519  retn
```
