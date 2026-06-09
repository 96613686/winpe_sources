# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(void)

- ea: `0x1800024c0`
- end: `0x1800024d7`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(HMODULE *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015510`
- `0x180015522`
- `0x18001586e`
- `0x1800158ec`
- `0x180015ab4`

## callees

- `0x1800024c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024cc`

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
0x1800024c0  sub     rsp, 28h
0x1800024c4  mov     rcx, [rcx]; hLibModule
0x1800024c7  test    rcx, rcx
0x1800024ca  jz      short loc_1800024D2
0x1800024cc  call    cs:__imp_FreeLibrary
0x1800024d2  add     rsp, 28h
0x1800024d6  retn
```
