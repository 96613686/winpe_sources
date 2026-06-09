# ArchiveItemContextMenu::OpenExploreDirectory(unsigned __int64,ArchiveIdList *)

- ea: `0x180058e4c`
- end: `0x180058ff8`
- name: `?OpenExploreDirectory@ArchiveItemContextMenu@@AEAAJ_KPEAUArchiveIdList@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(ArchiveItemContextMenu *this, __int64, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058a20`

## callees

- `0x18000d7a8`
- `0x180021f0c`
- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180036f50`
- `0x180037958`
- `0x18003edd4`
- `0x180058e4c`
- `0x180071010`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180058f89`
- `SHELL32!ShellExecuteExW` at `0x180058f89`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180058ed7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180058ed7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArchiveItemContextMenu::OpenExploreDirectory(
        ArchiveItemContextMenu *this,
        __int64 a2,
        const struct _ITEMIDLIST *a3)
{
  int v5; // eax
  unsigned int LastError; // ebx
  HRESULT v7; // eax
  struct _ITEMIDLIST *v8; // rbx
  __int64 v9; // r8
  int v10; // eax
  const WCHAR *v11; // rax
  const char *v12; // r9
  struct _ITEMIDLIST *v14[2]; // [rsp+20h] [rbp-49h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-39h] BYREF
  void *ppvOut; // [rsp+A0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v14[0] = 0;
  v5 = SHILCombine(*(const struct _ITEMIDLIST **)(*((_QWORD *)this + 8) + 128LL), a3, v14);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
      (const char *)(unsigned int)v5);
    goto LABEL_16;
  }
  ppvOut = 0;
  v7 = IUnknown_QueryService(
         *((IUnknown **)this + 10),
         &IID_IShellBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut);
  v8 = v14[0];
  if ( v7 >= 0 )
  {
    v9 = 16;
    if ( a2 != 102 )
      v9 = 32;
    v10 = (*(__int64 (__fastcall **)(void *, struct _ITEMIDLIST *, __int64))(*(_QWORD *)ppvOut + 88LL))(
            ppvOut,
            v14[0],
            v9);
    if ( v10 >= 0 )
      goto LABEL_13;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
      (const char *)(unsigned int)v10,
      (int)v14[0]);
  }
  pExecInfo.cbSize = 112;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.fMask = 5;
  pExecInfo.hwnd = *(HWND *)(*((_QWORD *)this + 8) + 136LL);
  v11 = L"open";
  if ( a2 != 102 )
    v11 = L"explore";
  pExecInfo.lpVerb = v11;
  pExecInfo.nShow = 1;
  pExecInfo.lpIDList = v8;
  pExecInfo.lpClass = L"Folder";
  if ( !ShellExecuteExW(&pExecInfo) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD0,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveitemcontextmenu.cpp",
                  v12);
    if ( ppvOut )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppvOut);
    goto LABEL_16;
  }
LABEL_13:
  if ( ppvOut )
    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppvOut);
  LastError = 0;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(v14);
  return LastError;
}

```

## disassembly

```asm
0x180058e4c  mov     [rsp-8+arg_8], rbx
0x180058e51  push    rbp
0x180058e52  push    rsi
0x180058e53  push    rdi
0x180058e54  lea     rbp, [rsp-47h]
0x180058e59  sub     rsp, 0B0h
0x180058e60  mov     rax, cs:__security_cookie
0x180058e67  xor     rax, rsp
0x180058e6a  mov     [rbp+57h+var_18], rax
0x180058e6e  mov     rax, r8
0x180058e71  mov     rsi, rdx
0x180058e74  mov     rdi, rcx
0x180058e77  mov     [rbp+57h+var_A0], 0
0x180058e7f  mov     rcx, [rcx+40h]
0x180058e83  lea     r8, [rbp+57h+var_A0]; struct _ITEMIDLIST **
0x180058e87  mov     rdx, rax; struct _ITEMIDLIST *
0x180058e8a  mov     rcx, [rcx+80h]; struct _ITEMIDLIST *
0x180058e91  call    ?SHILCombine@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z; SHILCombine(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180058e96  mov     ebx, eax
0x180058e98  test    eax, eax
0x180058e9a  jns     short loc_180058EB9
0x180058e9c  mov     rcx, [rbp+5Fh]
0x180058ea0  mov     r9d, eax
0x180058ea3  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180058eaa  mov     edx, 0BAh
0x180058eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058eb4  jmp     loc_180058FCE
0x180058eb9  mov     [rbp+57h+ppvOut], 0
0x180058ec1  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180058ec5  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180058ecc  lea     rdx, IID_IShellBrowser; guidService
0x180058ed3  mov     rcx, [rdi+50h]; punk
0x180058ed7  call    cs:__imp_IUnknown_QueryService
0x180058edd  mov     rbx, [rbp+57h+var_A0]
0x180058ee1  test    eax, eax
0x180058ee3  js      short loc_180058F29
0x180058ee5  mov     rcx, [rbp+57h+ppvOut]
0x180058ee9  mov     rax, [rcx]
0x180058eec  mov     edx, 20h ; ' '
0x180058ef1  lea     r8d, [rdx-10h]
0x180058ef5  cmp     rsi, 66h ; 'f'
0x180058ef9  cmovnz  r8d, edx
0x180058efd  mov     rdx, rbx
0x180058f00  mov     rax, [rax+58h]
0x180058f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f09  test    eax, eax
0x180058f0b  jns     loc_180058FBC
0x180058f11  mov     rcx, [rbp+5Fh]; this
0x180058f15  mov     r9d, eax; char *
0x180058f18  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180058f1f  mov     edx, 0C2h; void *
0x180058f24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058f29  mov     [rbp+57h+pExecInfo.cbSize], 70h ; 'p'
0x180058f30  xor     edx, edx; Val
0x180058f32  lea     r8d, [rdx+6Ch]; Size
0x180058f36  lea     rcx, [rbp+57h+pExecInfo.fMask]; void *
0x180058f3a  call    memset_0
0x180058f3f  mov     [rbp+57h+pExecInfo.fMask], 5
0x180058f46  mov     rax, [rdi+40h]
0x180058f4a  mov     rcx, [rax+88h]
0x180058f51  mov     [rbp+57h+pExecInfo.hwnd], rcx
0x180058f55  lea     rax, aOpen; "open"
0x180058f5c  lea     rcx, aExplore; "explore"
0x180058f63  cmp     rsi, 66h ; 'f'
0x180058f67  cmovnz  rax, rcx
0x180058f6b  mov     [rbp+57h+pExecInfo.lpVerb], rax
0x180058f6f  mov     [rbp+57h+pExecInfo.nShow], 1
0x180058f76  mov     [rbp+57h+pExecInfo.lpIDList], rbx
0x180058f7a  lea     rax, aFolder; "Folder"
0x180058f81  mov     [rbp+57h+pExecInfo.lpClass], rax
0x180058f85  lea     rcx, [rbp+57h+pExecInfo]; pExecInfo
0x180058f89  call    cs:__imp_ShellExecuteExW
0x180058f8f  test    eax, eax
0x180058f91  jnz     short loc_180058FBC
0x180058f93  mov     rcx, [rbp+5Fh]; this
0x180058f97  lea     r8, aShellExtZipArc_12; "shell\\ext\\zip\\archive\\archiveitemco"...
0x180058f9e  mov     edx, 0D0h; void *
0x180058fa3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058fa8  mov     ebx, eax
0x180058faa  cmp     [rbp+57h+ppvOut], 0
0x180058faf  jz      short loc_180058FCE
0x180058fb1  lea     rcx, [rbp+57h+ppvOut]
0x180058fb5  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180058fba  jmp     short loc_180058FCE
0x180058fbc  cmp     [rbp+57h+ppvOut], 0
0x180058fc1  jz      short loc_180058FCC
0x180058fc3  lea     rcx, [rbp+57h+ppvOut]
0x180058fc7  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180058fcc  xor     ebx, ebx
0x180058fce  lea     rcx, [rbp+57h+var_A0]
0x180058fd2  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180058fd7  mov     eax, ebx
0x180058fd9  mov     rcx, [rbp+57h+var_18]
0x180058fdd  xor     rcx, rsp; StackCookie
0x180058fe0  call    __security_check_cookie
0x180058fe5  mov     rbx, [rsp+0C0h+arg_8]
0x180058fed  add     rsp, 0B0h
0x180058ff4  pop     rdi
0x180058ff5  pop     rsi
0x180058ff6  pop     rbp
0x180058ff7  retn
```
