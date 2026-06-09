# CThumbnailMoniker::_NormalizeUrl(IPropertyStore *,ushort const *,ushort * *)

- ea: `0x180021e40`
- end: `0x180021ecb`
- name: `?_NormalizeUrl@CThumbnailMoniker@@CAJPEAUIPropertyStore@@PEBGPEAPEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct IPropertyStore *, LPCWSTR lpLocalPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800085c0`

## callees

- `0x180021e40`
- `0x180021ed4`
- `0x180022040`
- `0x1800225f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180021e86`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180021e86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180021e7b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180021e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021eab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailMoniker::_NormalizeUrl(
        struct IPropertyStore *a1,
        LPCWSTR lpLocalPath,
        unsigned __int16 **a3)
{
  int v6; // edi
  int v7; // eax
  LPWSTR pszPath; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  pszPath = 0;
  v6 = _AllocString<CTCoAllocPolicy>(a1, lpLocalPath, lpLocalPath, &pszPath);
  if ( v6 >= 0 )
  {
    PathStripToRootW(pszPath);
    if ( GetDriveTypeW(pszPath) == 4 )
      v7 = CThumbnailMoniker::_ConvertToUNCPathUrl(lpLocalPath, a3);
    else
      v7 = CThumbnailMoniker::_NormalizeNonUNCPathUrl(a1, lpLocalPath, pszPath, a3);
    v6 = v7;
  }
  CoTaskMemFree(pszPath);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180021e40  push    rbp
0x180021e42  push    rsi
0x180021e43  push    rdi
0x180021e44  push    r14
0x180021e46  sub     rsp, 28h
0x180021e4a  mov     rsi, r8
0x180021e4d  mov     rbp, rdx
0x180021e50  mov     r14, rcx
0x180021e53  mov     qword ptr [r8], 0
0x180021e5a  mov     [rsp+48h+pszPath], 0
0x180021e63  lea     r9, [rsp+48h+pszPath]
0x180021e68  mov     r8, rdx
0x180021e6b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180021e70  mov     edi, eax
0x180021e72  test    eax, eax
0x180021e74  js      short loc_180021EA6
0x180021e76  mov     rcx, [rsp+48h+pszPath]; pszPath
0x180021e7b  call    cs:__imp_PathStripToRootW
0x180021e81  mov     rcx, [rsp+48h+pszPath]; lpRootPathName
0x180021e86  call    cs:__imp_GetDriveTypeW
0x180021e8c  cmp     eax, 4
0x180021e8f  jz      short loc_180021EBD
0x180021e91  mov     r9, rsi; unsigned __int16 **
0x180021e94  mov     r8, [rsp+48h+pszPath]; unsigned __int16 *
0x180021e99  mov     rdx, rbp; unsigned __int16 *
0x180021e9c  mov     rcx, r14; struct IPropertyStore *
0x180021e9f  call    ?_NormalizeNonUNCPathUrl@CThumbnailMoniker@@CAJPEAUIPropertyStore@@PEBG1PEAPEAG@Z; CThumbnailMoniker::_NormalizeNonUNCPathUrl(IPropertyStore *,ushort const *,ushort const *,ushort * *)
0x180021ea4  mov     edi, eax
0x180021ea6  mov     rcx, [rsp+48h+pszPath]; pv
0x180021eab  call    cs:__imp_CoTaskMemFree
0x180021eb1  mov     eax, edi
0x180021eb3  add     rsp, 28h
0x180021eb7  pop     r14
0x180021eb9  pop     rdi
0x180021eba  pop     rsi
0x180021ebb  pop     rbp
0x180021ebc  retn
0x180021ebd  mov     rdx, rsi; unsigned __int16 **
0x180021ec0  mov     rcx, rbp; lpLocalPath
0x180021ec3  call    ?_ConvertToUNCPathUrl@CThumbnailMoniker@@CAJPEBGPEAPEAG@Z; CThumbnailMoniker::_ConvertToUNCPathUrl(ushort const *,ushort * *)
0x180021ec8  jmp     short loc_180021EA4
```
