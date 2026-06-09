# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(void)

- ea: `0x180006f70`
- end: `0x180006f87`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016a1f`
- `0x180016b0e`
- `0x180016b8a`
- `0x180016b9c`

## callees

- `0x180006f70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006f7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006f7c`

## pseudocode

```c
BOOL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(
        HMODULE *a1)
{
  HMODULE v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return FreeLibrary(v1);
  return result;
}

```

## disassembly

```asm
0x180006f70  sub     rsp, 28h
0x180006f74  mov     rcx, [rcx]; hLibModule
0x180006f77  test    rcx, rcx
0x180006f7a  jz      short loc_180006F82
0x180006f7c  call    cs:__imp_FreeLibrary
0x180006f82  add     rsp, 28h
0x180006f86  retn
```
