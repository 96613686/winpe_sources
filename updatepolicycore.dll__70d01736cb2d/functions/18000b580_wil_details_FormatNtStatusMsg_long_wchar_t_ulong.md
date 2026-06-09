# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x18000b580`
- end: `0x18000b5f0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b580`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b5aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b5aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b5da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b5da`

## string_xrefs

- `0x18000b5a3`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::FormatNtStatusMsg(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  HMODULE ModuleHandleW; // rax

  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  FormatMessageW(0x1A00u, ModuleHandleW, dwMessageId, 0x400u, lpBuffer, nSize, 0);
}

```

## disassembly

```asm
0x18000b580  mov     [rsp+arg_0], rbx
0x18000b585  mov     [rsp+arg_8], rsi
0x18000b58a  push    rdi
0x18000b58b  sub     rsp, 40h
0x18000b58f  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b596  mov     ebx, r8d
0x18000b599  mov     rdi, rdx
0x18000b59c  mov     esi, ecx
0x18000b59e  test    rax, rax
0x18000b5a1  jnz     short loc_18000B5B7
0x18000b5a3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000b5aa  call    cs:__imp_GetModuleHandleW
0x18000b5b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b5b7  mov     [rsp+48h+Arguments], 0; Arguments
0x18000b5c0  mov     r9d, 400h; dwLanguageId
0x18000b5c6  mov     [rsp+48h+nSize], ebx; nSize
0x18000b5ca  mov     r8d, esi; dwMessageId
0x18000b5cd  mov     rdx, rax; lpSource
0x18000b5d0  mov     [rsp+48h+lpBuffer], rdi; lpBuffer
0x18000b5d5  mov     ecx, 1A00h; dwFlags
0x18000b5da  call    cs:__imp_FormatMessageW
0x18000b5e0  mov     rbx, [rsp+48h+arg_0]
0x18000b5e5  mov     rsi, [rsp+48h+arg_8]
0x18000b5ea  add     rsp, 40h
0x18000b5ee  pop     rdi
0x18000b5ef  retn
```
