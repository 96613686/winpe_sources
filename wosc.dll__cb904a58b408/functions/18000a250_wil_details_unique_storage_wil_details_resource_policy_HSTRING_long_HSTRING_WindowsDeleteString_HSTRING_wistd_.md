# wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)

- ea: `0x18000a250`
- end: `0x18000a267`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `HRESULT __fastcall(HSTRING *)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a188`
- `0x18000dea0`
- `0x1800156e4`
- `0x180015a4c`
- `0x1800321f0`
- `0x180032458`
- `0x1800369f4`
- `0x18003c3e0`
- `0x18003cd38`
- `0x180042404`
- `0x18004e144`

## callees

- `0x18000a250`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a25c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a25c`

## pseudocode

```c
HRESULT __fastcall wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(
        HSTRING *a1)
{
  HSTRING v1; // rcx
  HRESULT result; // eax

  v1 = *a1;
  if ( v1 )
    return WindowsDeleteString(v1);
  return result;
}

```

## disassembly

```asm
0x18000a250  sub     rsp, 28h
0x18000a254  mov     rcx, [rcx]; string
0x18000a257  test    rcx, rcx
0x18000a25a  jz      short loc_18000A262
0x18000a25c  call    cs:__imp_WindowsDeleteString
0x18000a262  add     rsp, 28h
0x18000a266  retn
```
