# std::optional<UpdateDiagnostics::hstring_view>::~optional<UpdateDiagnostics::hstring_view>(void)

- ea: `0x180010690`
- end: `0x1800106ad`
- name: `??1?$optional@Uhstring_view@UpdateDiagnostics@@@std@@QEAA@XZ`
- size: `29`
- prototype: `HRESULT __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180097b5c`
- `0x180097b6e`

## callees

- `0x180010690`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800106a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800106a2`

## pseudocode

```c
HRESULT __fastcall std::optional<UpdateDiagnostics::hstring_view>::~optional<UpdateDiagnostics::hstring_view>(
        __int64 a1)
{
  HSTRING v1; // rcx
  HRESULT result; // eax

  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = *(HSTRING *)a1;
    if ( v1 )
      return WindowsDeleteString(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180010690  sub     rsp, 28h
0x180010694  cmp     byte ptr [rcx+8], 0
0x180010698  jz      short loc_1800106A8
0x18001069a  mov     rcx, [rcx]; string
0x18001069d  test    rcx, rcx
0x1800106a0  jz      short loc_1800106A8
0x1800106a2  call    cs:__imp_WindowsDeleteString
0x1800106a8  add     rsp, 28h
0x1800106ac  retn
```
