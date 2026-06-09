# CThemeManager2::_WriteInboxThemeToPropStore(ITheme *,int,IPropertyStore *)

- ea: `0x180056c4c`
- end: `0x180056d0b`
- name: `?_WriteInboxThemeToPropStore@CThemeManager2@@AEAAJPEAUITheme@@HPEAUIPropertyStore@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, struct ITheme *, int, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180056d14`

## callees

- `0x180056c4c`
- `0x180061de8`
- `0x180061e78`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180056cbc`
- `SHCORE!SHStrDupW` at `0x180056cbc`
- `SHLWAPI!PathFindFileNameW` at `0x180056cae`
- `SHLWAPI!PathFindFileNameW` at `0x180056cae`
- `SHLWAPI!PathRemoveExtensionW` at `0x180056ccd`
- `SHLWAPI!PathRemoveExtensionW` at `0x180056ccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ce7`
- `OLEAUT32!__imp_SysFreeString` at `0x180056cf3`
- `OLEAUT32!__imp_SysFreeString` at `0x180056cf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeManager2::_WriteInboxThemeToPropStore(
        WCHAR *this,
        struct ITheme *a2,
        __int64 a3,
        struct IPropertyStore *a4)
{
  HRESULT v6; // ebx
  const WCHAR *FileNameW; // rax
  __int64 v8; // rdx
  LPCWSTR pszPath[3]; // [rsp+20h] [rbp-18h] BYREF
  LPWSTR ppwsz; // [rsp+40h] [rbp+8h] BYREF

  ppwsz = this;
  v6 = IPropertyStore_SetInt(a4, a2, a3);
  if ( v6 >= 0 )
  {
    pszPath[0] = 0;
    v6 = (*(__int64 (__fastcall **)(struct ITheme *, _QWORD, LPCWSTR *))(*(_QWORD *)a2 + 288LL))(a2, 0, pszPath);
    if ( v6 >= 0 )
    {
      ppwsz = 0;
      FileNameW = PathFindFileNameW(pszPath[0]);
      v6 = SHStrDupW(FileNameW, &ppwsz);
      if ( v6 >= 0 )
      {
        PathRemoveExtensionW(ppwsz);
        v6 = IPropertyStore_SetString(a4, v8, ppwsz);
        CoTaskMemFree(ppwsz);
      }
    }
    SysFreeString((BSTR)pszPath[0]);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180056c4c  mov     [rsp+arg_8], rbx
0x180056c51  mov     [rsp+arg_10], rsi
0x180056c56  mov     [rsp+ppwsz], rcx
0x180056c5b  push    rdi
0x180056c5c  sub     rsp, 30h
0x180056c60  mov     rdi, r9
0x180056c63  mov     rsi, rdx
0x180056c66  mov     rcx, r9
0x180056c69  call    IPropertyStore_SetInt
0x180056c6e  mov     ebx, eax
0x180056c70  test    eax, eax
0x180056c72  js      loc_180056CF9
0x180056c78  mov     [rsp+38h+pszPath], 0
0x180056c81  mov     rax, [rsi]
0x180056c84  xor     edx, edx
0x180056c86  lea     r8, [rsp+38h+pszPath]
0x180056c8b  mov     rcx, rsi
0x180056c8e  mov     rax, [rax+120h]
0x180056c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c9a  mov     ebx, eax
0x180056c9c  test    eax, eax
0x180056c9e  js      short loc_180056CEE
0x180056ca0  mov     [rsp+38h+ppwsz], 0
0x180056ca9  mov     rcx, [rsp+38h+pszPath]; pszPath
0x180056cae  call    cs:__imp_PathFindFileNameW
0x180056cb4  lea     rdx, [rsp+38h+ppwsz]; ppwsz
0x180056cb9  mov     rcx, rax; psz
0x180056cbc  call    cs:__imp_SHStrDupW
0x180056cc2  mov     ebx, eax
0x180056cc4  test    eax, eax
0x180056cc6  js      short loc_180056CEE
0x180056cc8  mov     rcx, [rsp+38h+ppwsz]; pszPath
0x180056ccd  call    cs:__imp_PathRemoveExtensionW
0x180056cd3  mov     r8, [rsp+38h+ppwsz]
0x180056cd8  mov     rcx, rdi
0x180056cdb  call    IPropertyStore_SetString
0x180056ce0  mov     ebx, eax
0x180056ce2  mov     rcx, [rsp+38h+ppwsz]; pv
0x180056ce7  call    cs:__imp_CoTaskMemFree
0x180056ced  nop
0x180056cee  mov     rcx, [rsp+38h+pszPath]; bstrString
0x180056cf3  call    cs:__imp_SysFreeString
0x180056cf9  mov     eax, ebx
0x180056cfb  mov     rbx, [rsp+38h+arg_8]
0x180056d00  mov     rsi, [rsp+38h+arg_10]
0x180056d05  add     rsp, 30h
0x180056d09  pop     rdi
0x180056d0a  retn
```
