# CKeyboardOcclusionMitigation::_GetForegroundAppId(HWND__ *)

- ea: `0x180107ca4`
- end: `0x180107e0a`
- name: `?_GetForegroundAppId@CKeyboardOcclusionMitigation@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHWND__@@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800771ac`

## callees

- `0x18000b25c`
- `0x1800456b0`
- `0x1800542a8`
- `0x180107ca4`
- `0x180107e10`
- `0x18036fbe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180107cd8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180107cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107dc7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180107cc6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180107cc6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180107d4d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180107d4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKeyboardOcclusionMitigation::_GetForegroundAppId(__int64 a1, CallerIdentity *a2)
{
  char *v4; // rbx
  unsigned __int16 **v5; // r8
  unsigned __int16 **v6; // r8
  LPWSTR FileNameW; // rax
  __int64 result; // rax
  void *v9; // rbx
  LPVOID pv; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR pszPath; // [rsp+78h] [rbp+20h] BYREF

  dwProcessId = 0;
  try
  {
    GetWindowThreadProcessId((HWND)a2, &dwProcessId);
    v4 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
    v11[0] = v4;
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      pv = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      if ( CallerIdentity::GetImmersiveAppIdFromWindow(a2, (HWND)&pv, v5) >= 0 )
      {
        v9 = pv;
        std::wstring::wstring(a1, pv);
        if ( v9 )
          CoTaskMemFree(v9);
        goto LABEL_10;
      }
      pszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszPath,
        0);
      if ( (int)CallerIdentity::GetProcessAppIdWithAppResolverFallback(v4, &pszPath, v6) >= 0 && pszPath )
      {
        FileNameW = PathFindFileNameW(pszPath);
        std::wstring::wstring(a1, FileNameW);
        if ( pszPath )
          CoTaskMemFree((LPVOID)pszPath);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_10:
        Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v11);
        return a1;
      }
      if ( pszPath )
        CoTaskMemFree((LPVOID)pszPath);
      if ( pv )
        CoTaskMemFree(pv);
    }
    std::wstring::wstring(a1, &pszDefault);
    Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v11);
    result = a1;
  }
  catch ( ... )
  {
    std::wstring::wstring(a1, &pszDefault);
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180107ca4  mov     [rsp+arg_0], rcx
0x180107ca9  push    rbx
0x180107caa  push    rsi
0x180107cab  push    rdi
0x180107cac  sub     rsp, 40h
0x180107cb0  mov     rsi, rdx
0x180107cb3  mov     rdi, rcx
0x180107cb6  mov     [rsp+58h+dwProcessId], 0
0x180107cbe  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x180107cc3  mov     rcx, rsi; hWnd
0x180107cc6  call    cs:__imp_GetWindowThreadProcessId
0x180107ccc  mov     r8d, [rsp+58h+dwProcessId]; dwProcessId
0x180107cd1  xor     edx, edx; bInheritHandle
0x180107cd3  mov     ecx, 1000h; dwDesiredAccess
0x180107cd8  call    cs:__imp_OpenProcess
0x180107cde  mov     rbx, rax
0x180107ce1  mov     [rsp+58h+var_28], rax
0x180107ce6  dec     rax
0x180107ce9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180107ced  ja      loc_180107DDD
0x180107cf3  mov     [rsp+58h+pv], 0
0x180107cfc  xor     edx, edx
0x180107cfe  lea     rcx, [rsp+58h+pv]
0x180107d03  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180107d08  lea     rdx, [rsp+58h+pv]; HWND
0x180107d0d  mov     rcx, rsi; this
0x180107d10  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x180107d15  test    eax, eax
0x180107d17  jns     loc_180107DAE
0x180107d1d  mov     [rsp+58h+pszPath], 0
0x180107d26  xor     edx, edx
0x180107d28  lea     rcx, [rsp+58h+pszPath]
0x180107d2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180107d32  lea     rdx, [rsp+58h+pszPath]; void *
0x180107d37  mov     rcx, rbx; Process
0x180107d3a  call    ?GetProcessAppIdWithAppResolverFallback@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppIdWithAppResolverFallback(void *,ushort * *)
0x180107d3f  mov     rcx, [rsp+58h+pszPath]; pv
0x180107d44  test    eax, eax
0x180107d46  js      short loc_180107D90
0x180107d48  test    rcx, rcx
0x180107d4b  jz      short loc_180107D90
0x180107d4d  call    cs:__imp_PathFindFileNameW
0x180107d53  mov     rdx, rax
0x180107d56  mov     rcx, rdi
0x180107d59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180107d5e  nop
0x180107d5f  mov     rcx, [rsp+58h+pszPath]; pv
0x180107d64  test    rcx, rcx
0x180107d67  jz      short loc_180107D70
0x180107d69  call    cs:__imp_CoTaskMemFree
0x180107d6f  nop
0x180107d70  mov     rcx, [rsp+58h+pv]; pv
0x180107d75  test    rcx, rcx
0x180107d78  jz      short loc_180107D81
0x180107d7a  call    cs:__imp_CoTaskMemFree
0x180107d80  nop
0x180107d81  lea     rcx, [rsp+58h+var_28]
0x180107d86  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180107d8b  mov     rax, rdi
0x180107d8e  jmp     short loc_180107E01
0x180107d90  test    rcx, rcx
0x180107d93  jz      short loc_180107D9C
0x180107d95  call    cs:__imp_CoTaskMemFree
0x180107d9b  nop
0x180107d9c  mov     rcx, [rsp+58h+pv]; pv
0x180107da1  test    rcx, rcx
0x180107da4  jz      short loc_180107DDD
0x180107da6  call    cs:__imp_CoTaskMemFree
0x180107dac  jmp     short loc_180107DDD
0x180107dae  mov     rbx, [rsp+58h+pv]
0x180107db3  mov     rdx, rbx
0x180107db6  mov     rcx, rdi
0x180107db9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180107dbe  nop
0x180107dbf  test    rbx, rbx
0x180107dc2  jz      short loc_180107DCE
0x180107dc4  mov     rcx, rbx; pv
0x180107dc7  call    cs:__imp_CoTaskMemFree
0x180107dcd  nop
0x180107dce  lea     rcx, [rsp+58h+var_28]
0x180107dd3  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180107dd8  mov     rax, rdi
0x180107ddb  jmp     short loc_180107E01
0x180107ddd  lea     rdx, pszDefault
0x180107de4  mov     rcx, rdi
0x180107de7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180107dec  nop
0x180107ded  lea     rcx, [rsp+58h+var_28]
0x180107df2  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180107df7  mov     rax, rdi
0x180107dfa  jmp     short loc_180107E01
0x180107dfc  mov     rax, [rsp+58h+arg_0]
0x180107e01  add     rsp, 40h
0x180107e05  pop     rdi
0x180107e06  pop     rsi
0x180107e07  pop     rbx
0x180107e08  retn
```
