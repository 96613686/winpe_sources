# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18002a9e0`
- end: `0x18002aa15`
- name: `?GetRuntimeClassName@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@UDisableCausality@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002aa20`

## callees

- `0x18002a9e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aa0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aa0a`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::DisableCausality>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  HRESULT result; // eax
  const WCHAR *v4; // rcx
  __int64 v5; // rdx

  *a2 = 0;
  result = 0;
  v4 = *(const WCHAR **)(a1 + 232);
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    return WindowsCreateString(v4, v5, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18002a9e0  sub     rsp, 28h
0x18002a9e4  xor     r9d, r9d
0x18002a9e7  mov     r8, rdx; string
0x18002a9ea  mov     [rdx], r9
0x18002a9ed  mov     eax, r9d
0x18002a9f0  mov     rcx, [rcx+0E8h]; sourceString
0x18002a9f7  test    rcx, rcx
0x18002a9fa  jz      short loc_18002AA10
0x18002a9fc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002aa00  inc     rdx; length
0x18002aa03  cmp     [rcx+rdx*2], r9w
0x18002aa08  jnz     short loc_18002AA00
0x18002aa0a  call    cs:__imp_WindowsCreateString
0x18002aa10  add     rsp, 28h
0x18002aa14  retn
```
