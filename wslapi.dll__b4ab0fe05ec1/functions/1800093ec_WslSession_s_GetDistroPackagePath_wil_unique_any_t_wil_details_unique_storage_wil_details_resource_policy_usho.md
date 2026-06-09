# WslSession::s_GetDistroPackagePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800093ec`
- end: `0x1800094e6`
- name: `?s_GetDistroPackagePath@WslSession@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `250`
- prototype: `int __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180007344`

## callees

- `0x180001dc0`
- `0x180004fd4`
- `0x18000698c`
- `0x180006b80`
- `0x180008454`
- `0x180008678`
- `0x18000897c`
- `0x180008a48`
- `0x1800093ec`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackagePath` at `0x180009413`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackagePath` at `0x180009476`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackagePath` at `0x180009413`
- `api-ms-win-appmodel-runtime-l1-1-0!GetCurrentPackagePath` at `0x180009476`

## string_xrefs

- `0x180009445`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
int __fastcall WslSession::s_GetDistroPackagePath(void **a1)
{
  unsigned int CurrentPackagePath; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // r9
  const char *v6; // r9
  __int64 v7; // rdx
  int CallingExePath; // eax
  int v10; // ebx
  unsigned int v11[2]; // [rsp+20h] [rbp-28h] BYREF
  UINT32 pathLength; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pathLength = 0;
  CurrentPackagePath = GetCurrentPackagePath(&pathLength, 0);
  if ( CurrentPackagePath == 122 )
  {
    *(_QWORD *)v11 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      v11,
      0,
      pathLength,
      v5);
    if ( !*(_QWORD *)v11 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0xFDC,
        (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1,
      v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v11);
    CurrentPackagePath = GetCurrentPackagePath(&pathLength, (PWSTR)*a1);
    if ( CurrentPackagePath )
    {
      v7 = 181;
      return wil::details::in1diag3::Return_Win32(retaddr, (void *)v7, v4, (const char *)CurrentPackagePath, v11[0]);
    }
  }
  else if ( CurrentPackagePath == 15700 )
  {
    CallingExePath = _GetCallingExePath(a1, v3, v4, v5);
    v10 = CallingExePath;
    if ( CallingExePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (int)"onecore\\vm\\wsl\\lxss\\wslapi\\wslsession.cpp",
        (const char *)(unsigned int)CallingExePath);
      return v10;
    }
  }
  else if ( CurrentPackagePath )
  {
    v7 = 193;
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)v7, v4, (const char *)CurrentPackagePath, v11[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x1800093ec  push    rbx
0x1800093ee  sub     rsp, 40h
0x1800093f2  mov     rax, cs:__security_cookie
0x1800093f9  xor     rax, rsp
0x1800093fc  mov     [rsp+48h+var_18], rax
0x180009401  mov     rbx, rcx
0x180009404  mov     [rsp+48h+pathLength], 0
0x18000940c  lea     rcx, [rsp+48h+pathLength]; pathLength
0x180009411  xor     edx, edx; path
0x180009413  call    cs:__imp_GetCurrentPackagePath
0x180009419  cmp     eax, 7Ah ; 'z'
0x18000941c  jnz     short loc_180009494
0x18000941e  mov     r8d, [rsp+48h+pathLength]
0x180009423  lea     rcx, [rsp+48h+var_28]
0x180009428  xor     edx, edx
0x18000942a  mov     qword ptr [rsp+48h+var_28], 0; unsigned int
0x180009433  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009438  cmp     qword ptr [rsp+48h+var_28], 0
0x18000943e  mov     rcx, [rsp+48h]; this
0x180009443  jnz     short loc_180009457
0x180009445  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000944c  mov     edx, 0FDCh; void *
0x180009451  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180009457  lea     rdx, [rsp+48h+var_28]
0x18000945c  mov     rcx, rbx
0x18000945f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180009464  lea     rcx, [rsp+48h+var_28]
0x180009469  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000946e  mov     rdx, [rbx]; path
0x180009471  lea     rcx, [rsp+48h+pathLength]; pathLength
0x180009476  call    cs:__imp_GetCurrentPackagePath
0x18000947c  test    eax, eax
0x18000947e  jz      short loc_1800094D1
0x180009480  mov     edx, 0B5h; void *
0x180009485  mov     rcx, [rsp+48h]; this
0x18000948a  mov     r9d, eax; char *
0x18000948d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009492  jmp     short loc_1800094D3
0x180009494  cmp     eax, 3D54h
0x180009499  jnz     short loc_1800094C6
0x18000949b  mov     rcx, rbx
0x18000949e  call    ?_GetCallingExePath@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetCallingExePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800094a3  mov     ebx, eax
0x1800094a5  test    eax, eax
0x1800094a7  jns     short loc_1800094D1
0x1800094a9  mov     rcx, [rsp+48h]; this
0x1800094ae  lea     r8, aOnecoreVmWslLx_3; "onecore\\vm\\wsl\\lxss\\wslapi\\wslsess"...
0x1800094b5  mov     r9d, eax; char *
0x1800094b8  mov     edx, 0BBh; void *
0x1800094bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094c2  mov     eax, ebx
0x1800094c4  jmp     short loc_1800094D3
0x1800094c6  test    eax, eax
0x1800094c8  jz      short loc_1800094D1
0x1800094ca  mov     edx, 0C1h
0x1800094cf  jmp     short loc_180009485
0x1800094d1  xor     eax, eax
0x1800094d3  mov     rcx, [rsp+48h+var_18]
0x1800094d8  xor     rcx, rsp; StackCookie
0x1800094db  call    __security_check_cookie
0x1800094e0  add     rsp, 40h
0x1800094e4  pop     rbx
0x1800094e5  retn
```
